# [thunk]:ATL::CComObject<CSinkWrapACP>::AddRef`adjustor{8}' (void)

- ea: `0x180005cf0`
- end: `0x180005cf9`
- name: `?AddRef@?$CComObject@VCSinkWrapACP@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005cd0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CSinkWrapACP>::AddRef(__int64 a1)
{
  return ATL::CComObject<CSinkWrapAnchor>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180005cf0  sub     rcx, 8
0x180005cf4  jmp     ?AddRef@?$CComObject@VCSinkWrapAnchor@@@ATL@@UEAAKXZ; ATL::CComObject<CSinkWrapAnchor>::AddRef(void)
```
