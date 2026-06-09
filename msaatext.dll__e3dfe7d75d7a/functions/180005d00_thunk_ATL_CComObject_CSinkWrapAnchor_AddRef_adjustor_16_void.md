# [thunk]:ATL::CComObject<CSinkWrapAnchor>::AddRef`adjustor{16}' (void)

- ea: `0x180005d00`
- end: `0x180005d09`
- name: `?AddRef@?$CComObject@VCSinkWrapAnchor@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005cd0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CSinkWrapAnchor>::AddRef(__int64 a1)
{
  return ATL::CComObject<CSinkWrapAnchor>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x180005d00  sub     rcx, 10h
0x180005d04  jmp     ?AddRef@?$CComObject@VCSinkWrapAnchor@@@ATL@@UEAAKXZ; ATL::CComObject<CSinkWrapAnchor>::AddRef(void)
```
