# IASTL::IASComponentObject<InfoBase>::Resume(void)

- ea: `0x180011e90`
- end: `0x180011e9a`
- name: `?Resume@?$IASComponentObject@VInfoBase@@@IASTL@@UEAAJXZ`
- size: `10`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014fa0`

## pseudocode

```c
__int64 __fastcall IASTL::IASComponentObject<InfoBase>::Resume(__int64 a1)
{
  return IASTL::IASComponent::fireEvent(a1, 3);
}

```

## disassembly

```asm
0x180011e90  mov     edx, 3
0x180011e95  jmp     ?fireEvent@IASComponent@IASTL@@QEAAJW4Event@12@@Z; IASTL::IASComponent::fireEvent(IASTL::IASComponent::Event)
```
