# [thunk]:ATL::CComObject<CSinkWrapACP>::Release`adjustor{8}' (void)

- ea: `0x18000a930`
- end: `0x18000a939`
- name: `?Release@?$CComObject@VCSinkWrapACP@@@ATL@@W7EAAKXZ`
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
  return ATL::CComObject<CSinkWrapACP>::Release((_DWORD *)(a1 - 8));
}

```

## disassembly

```asm
0x18000a930  sub     rcx, 8
0x18000a934  jmp     ?Release@?$CComObject@VCSinkWrapACP@@@ATL@@UEAAKXZ; ATL::CComObject<CSinkWrapACP>::Release(void)
```
