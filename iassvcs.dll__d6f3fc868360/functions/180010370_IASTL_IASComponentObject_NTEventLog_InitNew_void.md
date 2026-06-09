# IASTL::IASComponentObject<NTEventLog>::InitNew(void)

- ea: `0x180010370`
- end: `0x180010377`
- name: `?InitNew@?$IASComponentObject@VNTEventLog@@@IASTL@@UEAAJXZ`
- size: `7`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014fa0`

## pseudocode

```c
__int64 __fastcall IASTL::IASComponentObject<NTEventLog>::InitNew(__int64 a1)
{
  return IASTL::IASComponent::fireEvent(a1, 0);
}

```

## disassembly

```asm
0x180010370  xor     edx, edx
0x180010372  jmp     ?fireEvent@IASComponent@IASTL@@QEAAJW4Event@12@@Z; IASTL::IASComponent::fireEvent(IASTL::IASComponent::Event)
```
