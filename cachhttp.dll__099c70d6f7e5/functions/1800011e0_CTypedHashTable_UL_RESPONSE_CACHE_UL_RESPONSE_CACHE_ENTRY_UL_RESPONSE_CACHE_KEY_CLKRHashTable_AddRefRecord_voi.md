# CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::_AddRefRecord(void const *,int)

- ea: `0x1800011e0`
- end: `0x1800011f4`
- name: `?_AddRefRecord@?$CTypedHashTable@VUL_RESPONSE_CACHE@@VUL_RESPONSE_CACHE_ENTRY@@PEAVUL_RESPONSE_CACHE_KEY@@VCLKRHashTable@@@@CAXPEBXH@Z`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800011e0`
- `0x1800025e4`

## pseudocode

```c
void __fastcall CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::_AddRefRecord(
        volatile signed __int32 *a1,
        int a2)
{
  if ( a2 == 1 )
  {
    _InterlockedIncrement(a1 + 3);
  }
  else if ( a2 == -1 )
  {
    UL_RESPONSE_CACHE_ENTRY::DereferenceCacheData((UL_RESPONSE_CACHE_ENTRY *)a1);
  }
}

```

## disassembly

```asm
0x1800011e0  cmp     edx, 1
0x1800011e3  jnz     short loc_1800011EA
0x1800011e5  lock inc dword ptr [rcx+0Ch]
0x1800011e9  retn
0x1800011ea  cmp     edx, 0FFFFFFFFh
0x1800011ed  jnz     short locret_1800011E9
0x1800011ef  jmp     ?DereferenceCacheData@UL_RESPONSE_CACHE_ENTRY@@QEAAXXZ; UL_RESPONSE_CACHE_ENTRY::DereferenceCacheData(void)
```
