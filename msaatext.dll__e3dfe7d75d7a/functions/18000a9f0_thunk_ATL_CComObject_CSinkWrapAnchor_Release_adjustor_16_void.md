# [thunk]:ATL::CComObject<CSinkWrapAnchor>::Release`adjustor{16}' (void)

- ea: `0x18000a9f0`
- end: `0x18000a9f9`
- name: `?Release@?$CComObject@VCSinkWrapAnchor@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a950`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CSinkWrapAnchor>::Release(__int64 a1)
{
  return ATL::CComObject<CSinkWrapAnchor>::Release((_DWORD *)(a1 - 16));
}

```

## disassembly

```asm
0x18000a9f0  sub     rcx, 10h
0x18000a9f4  jmp     ?Release@?$CComObject@VCSinkWrapAnchor@@@ATL@@UEAAKXZ; ATL::CComObject<CSinkWrapAnchor>::Release(void)
```
