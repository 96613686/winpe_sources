# [thunk]:ATL::CComObject<CDocWrapAnchor>::AddRef`adjustor{16}' (void)

- ea: `0x180005c80`
- end: `0x180005c89`
- name: `?AddRef@?$CComObject@VCDocWrapAnchor@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005c50`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDocWrapAnchor>::AddRef(__int64 a1)
{
  return ATL::CComObject<CDocWrapACP>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x180005c80  sub     rcx, 10h
0x180005c84  jmp     ?AddRef@?$CComObject@VCDocWrapACP@@@ATL@@UEAAKXZ; ATL::CComObject<CDocWrapACP>::AddRef(void)
```
