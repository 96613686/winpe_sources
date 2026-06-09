# [thunk]:ATL::CComObject<CSinkWrapAnchor>::Release`adjustor{8}' (void)

- ea: `0x18000a9e0`
- end: `0x18000a9e9`
- name: `?Release@?$CComObject@VCSinkWrapAnchor@@@ATL@@W7EAAKXZ`
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
  return ATL::CComObject<CSinkWrapAnchor>::Release((_DWORD *)(a1 - 8));
}

```

## disassembly

```asm
0x18000a9e0  sub     rcx, 8
0x18000a9e4  jmp     ?Release@?$CComObject@VCSinkWrapAnchor@@@ATL@@UEAAKXZ; ATL::CComObject<CSinkWrapAnchor>::Release(void)
```
