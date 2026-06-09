# DbTransactedTableAccess<SharingToken>::Commit(void)

- ea: `0x180016388`
- end: `0x1800163e3`
- name: `?Commit@?$DbTransactedTableAccess@VSharingToken@@@@QEAAJXZ`
- size: `91`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800163ec`
- `0x18001669c`
- `0x180017c90`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x1800114e4`
- `0x180016388`

## import_xrefs

- `ESENT!JetCommitTransaction` at `0x18001639e`
- `ESENT!JetCommitTransaction` at `0x18001639e`

## string_xrefs

- `0x1800163c1`: `DbTransaction::Commit`

## pseudocode

```c
__int64 __fastcall DbTransactedTableAccess<SharingToken>::Commit(__int64 a1)
{
  unsigned int v1; // ebx
  __int64 v2; // rdx
  __int64 v3; // rcx
  JET_ERR v4; // edi
  __int64 v5; // r8
  __int64 v6; // r9
  DSLogger *v7; // rax
  JET_ERR v9; // [rsp+20h] [rbp-18h]

  v1 = 0;
  v4 = JetCommitTransaction(**(_QWORD **)(a1 + 40), 1u);
  if ( v4 < 0 )
  {
    v7 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                       v3,
                       v2,
                       v5,
                       v6);
    v9 = v4;
    DSLogger::LogError(v7, L"DbTransaction::Commit", 0x4Du, L"JET_ERR : %d", v9);
    return (unsigned int)JetToHResult(v4);
  }
  return v1;
}

```

## disassembly

```asm
0x180016388  mov     [rsp+arg_0], rbx
0x18001638d  push    rdi
0x18001638e  sub     rsp, 30h
0x180016392  mov     rcx, [rcx+28h]
0x180016396  xor     ebx, ebx
0x180016398  mov     rcx, [rcx]; sesid
0x18001639b  lea     edx, [rbx+1]; grbit
0x18001639e  call    cs:__imp_JetCommitTransaction
0x1800163a4  mov     edi, eax
0x1800163a6  test    eax, eax
0x1800163a8  jns     short loc_1800163D6
0x1800163aa  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800163af  lea     r9, aJetErrD; "JET_ERR : %d"
0x1800163b6  mov     [rsp+38h+var_18], edi
0x1800163ba  lea     r8d, [rbx+4Dh]; unsigned int
0x1800163be  mov     rcx, rax; this
0x1800163c1  lea     rdx, aDbtransactionC; "DbTransaction::Commit"
0x1800163c8  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800163cd  mov     ecx, edi; int
0x1800163cf  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x1800163d4  mov     ebx, eax
0x1800163d6  mov     eax, ebx
0x1800163d8  mov     rbx, [rsp+38h+arg_0]
0x1800163dd  add     rsp, 30h
0x1800163e1  pop     rdi
0x1800163e2  retn
```
