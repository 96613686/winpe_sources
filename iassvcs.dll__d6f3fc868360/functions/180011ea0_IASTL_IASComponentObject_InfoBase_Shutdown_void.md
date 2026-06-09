# IASTL::IASComponentObject<InfoBase>::Shutdown(void)

- ea: `0x180011ea0`
- end: `0x180011eaa`
- name: `?Shutdown@?$IASComponentObject@VInfoBase@@@IASTL@@UEAAJXZ`
- size: `10`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014fa0`

## pseudocode

```c
__int64 __fastcall IASTL::IASComponentObject<InfoBase>::Shutdown(__int64 a1)
{
  return IASTL::IASComponent::fireEvent(a1, 4);
}

```

## disassembly

```asm
0x180011ea0  mov     edx, 4
0x180011ea5  jmp     ?fireEvent@IASComponent@IASTL@@QEAAJW4Event@12@@Z; IASTL::IASComponent::fireEvent(IASTL::IASComponent::Event)
```
