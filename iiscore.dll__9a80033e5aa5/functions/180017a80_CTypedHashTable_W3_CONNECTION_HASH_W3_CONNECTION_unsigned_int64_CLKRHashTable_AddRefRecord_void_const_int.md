# CTypedHashTable<W3_CONNECTION_HASH,W3_CONNECTION,unsigned __int64 *,CLKRHashTable>::_AddRefRecord(void const *,int)

- ea: `0x180017a80`
- end: `0x180017ab0`
- name: `?_AddRefRecord@?$CTypedHashTable@VW3_CONNECTION_HASH@@VW3_CONNECTION@@PEA_KVCLKRHashTable@@@@CAXPEBXH@Z`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180017a80`
- `0x1800240e8`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x180017a9f`

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
0x180017a80  cmp     edx, 1
0x180017a83  jnz     short loc_180017AA6
0x180017a85  lock xadd [rcx+18h], edx
0x180017a8a  mov     rax, cs:?sm_pTraceLog@W3_CONNECTION@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONNECTION::sm_pTraceLog
0x180017a91  inc     edx
0x180017a93  test    rax, rax
0x180017a96  jnz     short loc_180017A99
0x180017a98  retn
0x180017a99  mov     r8, rcx
0x180017a9c  mov     rcx, rax; this
0x180017a9f  jmp     cs:__imp_WriteRefTraceLog
0x180017aa6  cmp     edx, 0FFFFFFFFh
0x180017aa9  jnz     short locret_180017A98
0x180017aab  jmp     ?DereferenceConnection@W3_CONNECTION@@QEAAXXZ; W3_CONNECTION::DereferenceConnection(void)
```
