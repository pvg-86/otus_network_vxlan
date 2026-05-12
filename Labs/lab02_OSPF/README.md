# ДЗ_2. Underlay OSPF
### Цель:
- настроить OSPF для Underlay сети.
- описать.

### Выполнение.

1) Схема сети.

![alt text](image.png)

[Описание именования и адресного пространства, описаноа в ДЗ_1.](../lab01_architect/README.md)

2) Описание схемы.

- 

3) Конфигурация обрудования.

```
C1_S1# show running-config ospf

version 9.3(1) Bios:version
feature ospf

router ospf UNDERLAY
  router-id 10.10.10.10
  area 0.0.0.0 authentication
  passive-interface default

interface loopback0
  ip router ospf UNDERLAY area 0.0.0.0

interface Ethernet1/1
  ip ospf authentication-key 3 9198394a11c0fa40
  ip ospf network point-to-point
  no ip ospf passive-interface
  ip router ospf UNDERLAY area 0.0.0.0

interface Ethernet1/2
  ip ospf authentication-key 3 9198394a11c0fa40
  ip ospf network point-to-point
  no ip ospf passive-interface
  ip router ospf UNDERLAY area 0.0.0.0

interface Ethernet1/3
  ip ospf authentication-key 3 9198394a11c0fa40
  ip ospf network point-to-point
  no ip ospf passive-interface
  ip router ospf UNDERLAY area 0.0.0.0
```