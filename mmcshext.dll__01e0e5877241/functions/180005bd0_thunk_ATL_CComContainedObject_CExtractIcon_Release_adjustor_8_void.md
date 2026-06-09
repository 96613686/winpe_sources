# [thunk]:ATL::CComContainedObject<CExtractIcon>::Release`adjustor{8}' (void)

- ea: `0x180005bd0`
- end: `0x180005bd9`
- name: `?Release@?$CComContainedObject@VCExtractIcon@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005bb0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CExtractIcon>::Release(__int64 a1)
{
  return ATL::CComContainedObject<CExtractIcon>::Release(a1 - 8);
}

```

## disassembly

```asm
0x180005bd0  sub     rcx, 8
0x180005bd4  jmp     ?Release@?$CComContainedObject@VCExtractIcon@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CExtractIcon>::Release(void)
```
