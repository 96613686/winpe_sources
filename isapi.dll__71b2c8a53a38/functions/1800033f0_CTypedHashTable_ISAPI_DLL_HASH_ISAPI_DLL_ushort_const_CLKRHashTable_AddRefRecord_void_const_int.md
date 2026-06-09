# CTypedHashTable<ISAPI_DLL_HASH,ISAPI_DLL,ushort const *,CLKRHashTable>::_AddRefRecord(void const *,int)

- ea: `0x1800033f0`
- end: `0x18000342c`
- name: `?_AddRefRecord@?$CTypedHashTable@VISAPI_DLL_HASH@@VISAPI_DLL@@PEBGVCLKRHashTable@@@@CAXPEBXH@Z`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180001ddc`
- `0x1800033f0`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x180003416`

## pseudocode

```c
void __fastcall CTypedHashTable<ISAPI_DLL_HASH,ISAPI_DLL,unsigned short const *,CLKRHashTable>::_AddRefRecord(
        volatile signed __int32 *a1,
        int a2)
{
  __int64 v2; // rdx

  if ( a2 == 1 )
  {
    v2 = (unsigned int)_InterlockedIncrement(a1 + 1);
    if ( ISAPI_DLL::sm_pTraceLog )
      WriteRefTraceLog(ISAPI_DLL::sm_pTraceLog, v2, a1);
  }
  else if ( a2 == -1 )
  {
    ISAPI_DLL::DereferenceIsapiDll((ISAPI_DLL *)a1);
  }
}

```

## disassembly

```asm
0x1800033f0  sub     rsp, 28h
0x1800033f4  cmp     edx, 1
0x1800033f7  jnz     short loc_18000341D
0x1800033f9  lock xadd [rcx+4], edx
0x1800033fe  mov     rax, cs:?sm_pTraceLog@ISAPI_DLL@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * ISAPI_DLL::sm_pTraceLog
0x180003405  inc     edx
0x180003407  test    rax, rax
0x18000340a  jz      short loc_180003427
0x18000340c  mov     r8, rcx
0x18000340f  mov     rcx, rax; this
0x180003412  add     rsp, 28h
0x180003416  jmp     cs:__imp_WriteRefTraceLog
0x18000341d  cmp     edx, 0FFFFFFFFh
0x180003420  jnz     short loc_180003427
0x180003422  call    ?DereferenceIsapiDll@ISAPI_DLL@@QEAAXXZ; ISAPI_DLL::DereferenceIsapiDll(void)
0x180003427  add     rsp, 28h
0x18000342b  retn
```
