# IASTL::IASComponentObject<NTEventLog>::Initialize(void)

- ea: `0x180010380`
- end: `0x18001038a`
- name: `?Initialize@?$IASComponentObject@VNTEventLog@@@IASTL@@UEAAJXZ`
- size: `10`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014fa0`

## pseudocode

```c
__int64 __fastcall IASTL::IASComponentObject<NTEventLog>::Initialize(__int64 a1)
{
  return IASTL::IASComponent::fireEvent(a1, 1);
}

```

## disassembly

```asm
0x180010380  mov     edx, 1
0x180010385  jmp     ?fireEvent@IASComponent@IASTL@@QEAAJW4Event@12@@Z; IASTL::IASComponent::fireEvent(IASTL::IASComponent::Event)
```
