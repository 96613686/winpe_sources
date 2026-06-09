# [thunk]:ATL::CComObject<CIsoBurn>::Release`adjustor{8}' (void)

- ea: `0x1400078c0`
- end: `0x1400078c9`
- name: `?Release@?$CComObject@VCIsoBurn@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007830`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIsoBurn>::Release(__int64 a1)
{
  return ATL::CComObject<CIsoBurn>::Release((volatile signed __int32 *)(a1 - 8));
}

```

## disassembly

```asm
0x1400078c0  sub     rcx, 8
0x1400078c4  jmp     ?Release@?$CComObject@VCIsoBurn@@@ATL@@UEAAKXZ; ATL::CComObject<CIsoBurn>::Release(void)
```
