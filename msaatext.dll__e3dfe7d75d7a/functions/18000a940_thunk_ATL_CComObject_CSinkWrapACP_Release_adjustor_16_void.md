# [thunk]:ATL::CComObject<CSinkWrapACP>::Release`adjustor{16}' (void)

- ea: `0x18000a940`
- end: `0x18000a949`
- name: `?Release@?$CComObject@VCSinkWrapACP@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a8a0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CSinkWrapACP>::Release(__int64 a1)
{
  return ATL::CComObject<CSinkWrapACP>::Release((_DWORD *)(a1 - 16));
}

```

## disassembly

```asm
0x18000a940  sub     rcx, 10h
0x18000a944  jmp     ?Release@?$CComObject@VCSinkWrapACP@@@ATL@@UEAAKXZ; ATL::CComObject<CSinkWrapACP>::Release(void)
```
