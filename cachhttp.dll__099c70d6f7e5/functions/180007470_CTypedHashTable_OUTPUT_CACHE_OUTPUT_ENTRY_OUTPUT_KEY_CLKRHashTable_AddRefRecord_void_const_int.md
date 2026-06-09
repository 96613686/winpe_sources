# CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_AddRefRecord(void const *,int)

- ea: `0x180007470`
- end: `0x180007490`
- name: `?_AddRefRecord@?$CTypedHashTable@VOUTPUT_CACHE@@VOUTPUT_ENTRY@@PEAVOUTPUT_KEY@@VCLKRHashTable@@@@CAXPEBXH@Z`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000657c`
- `0x180007470`

## pseudocode

```c
void __fastcall CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_AddRefRecord(
        volatile signed __int32 *a1,
        int a2)
{
  if ( a2 == 1 )
  {
    _InterlockedIncrement(a1);
  }
  else if ( a2 == -1 )
  {
    OUTPUT_ENTRY::DereferenceOutputEntry((OUTPUT_ENTRY *)a1);
  }
}

```

## disassembly

```asm
0x180007470  sub     rsp, 28h
0x180007474  cmp     edx, 1
0x180007477  jnz     short loc_180007481
0x180007479  lock inc dword ptr [rcx]
0x18000747c  add     rsp, 28h
0x180007480  retn
0x180007481  cmp     edx, 0FFFFFFFFh
0x180007484  jnz     short loc_18000748B
0x180007486  call    ?DereferenceOutputEntry@OUTPUT_ENTRY@@QEAAXXZ; OUTPUT_ENTRY::DereferenceOutputEntry(void)
0x18000748b  add     rsp, 28h
0x18000748f  retn
```
