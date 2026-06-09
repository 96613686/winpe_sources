# IASTL::IASComponentObject<InfoBase>::Suspend(void)

- ea: `0x180011f70`
- end: `0x180011f7a`
- name: `?Suspend@?$IASComponentObject@VInfoBase@@@IASTL@@UEAAJXZ`
- size: `10`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014fa0`

## pseudocode

```c
__int64 __fastcall IASTL::IASComponentObject<InfoBase>::Suspend(__int64 a1)
{
  return IASTL::IASComponent::fireEvent(a1, 2);
}

```

## disassembly

```asm
0x180011f70  mov     edx, 2
0x180011f75  jmp     ?fireEvent@IASComponent@IASTL@@QEAAJW4Event@12@@Z; IASTL::IASComponent::fireEvent(IASTL::IASComponent::Event)
```
