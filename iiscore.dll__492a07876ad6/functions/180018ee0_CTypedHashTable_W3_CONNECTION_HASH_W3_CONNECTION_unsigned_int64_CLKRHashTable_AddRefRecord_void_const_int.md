# CTypedHashTable<W3_CONNECTION_HASH,W3_CONNECTION,unsigned __int64 *,CLKRHashTable>::_AddRefRecord(void const *,int)

- ea: `0x180018ee0`
- end: `0x180018f16`
- name: `?_AddRefRecord@?$CTypedHashTable@VW3_CONNECTION_HASH@@VW3_CONNECTION@@PEA_KVCLKRHashTable@@@@CAXPEBXH@Z`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180018ee0`
- `0x180025f88`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x180018f00`

## pseudocode

```c
void __fastcall CTypedHashTable<W3_CONNECTION_HASH,W3_CONNECTION,unsigned __int64 *,CLKRHashTable>::_AddRefRecord(
        volatile signed __int32 *a1,
        int a2)
{
  __int64 v2; // rdx

  if ( a2 == 1 )
  {
    v2 = (unsigned int)_InterlockedIncrement(a1 + 6);
    if ( W3_CONNECTION::sm_pTraceLog )
      WriteRefTraceLog(W3_CONNECTION::sm_pTraceLog, v2, a1);
  }
  else if ( a2 == -1 )
  {
    W3_CONNECTION::DereferenceConnection((W3_CONNECTION *)a1);
  }
}

```

## disassembly

```asm
0x180018ee0  cmp     edx, 1
0x180018ee3  jnz     short loc_180018F0C
0x180018ee5  lock xadd [rcx+18h], edx
0x180018eea  mov     rax, cs:?sm_pTraceLog@W3_CONNECTION@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONNECTION::sm_pTraceLog
0x180018ef1  inc     edx
0x180018ef3  test    rax, rax
0x180018ef6  jnz     short loc_180018EFA
0x180018ef8  retn
0x180018efa  mov     r8, rcx
0x180018efd  mov     rcx, rax; this
0x180018f00  jmp     cs:__imp_WriteRefTraceLog
0x180018f0c  cmp     edx, 0FFFFFFFFh
0x180018f0f  jnz     short locret_180018EF8
0x180018f11  jmp     ?DereferenceConnection@W3_CONNECTION@@QEAAXXZ; W3_CONNECTION::DereferenceConnection(void)
```
