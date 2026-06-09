# DbTable::Insert(JET_SETCOLUMN *,ulong,int)

- ea: `0x180014eb0`
- end: `0x1800150c3`
- name: `?Insert@DbTable@@QEAAJPEAUJET_SETCOLUMN@@KH@Z`
- size: `531`
- prototype: `__int64 __fastcall(DbTable *this, struct JET_SETCOLUMN *, unsigned int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800163ec`
- `0x180017ae0`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x1800114e4`
- `0x180014eb0`

## import_xrefs

- `ESENT!JetUpdate` at `0x180014ff6`
- `ESENT!JetUpdate` at `0x180014ff6`
- `ESENT!JetCommitTransaction` at `0x180015041`
- `ESENT!JetCommitTransaction` at `0x180015041`
- `ESENT!JetRollback` at `0x180015092`
- `ESENT!JetRollback` at `0x180015092`
- `ESENT!JetBeginTransaction` at `0x180014eec`
- `ESENT!JetBeginTransaction` at `0x180014eec`
- `ESENT!JetSetColumns` at `0x180014f9b`
- `ESENT!JetSetColumns` at `0x180014f9b`
- `ESENT!JetPrepareUpdate` at `0x180014f44`
- `ESENT!JetPrepareUpdate` at `0x1800150aa`
- `ESENT!JetPrepareUpdate` at `0x180014f44`
- `ESENT!JetPrepareUpdate` at `0x1800150aa`

## pseudocode

```c
__int64 __fastcall DbTable::Insert(DbTable *this, struct JET_SETCOLUMN *a2, unsigned int a3, int a4)
{
  int v7; // edi
  JET_SESID *v8; // rbx
  __int64 v9; // rcx
  JET_ERR v10; // ebx
  int *v11; // rax
  int v12; // ebp
  int v13; // r15d
  __int64 v14; // rcx
  JET_ERR v15; // r13d
  int *v16; // rax
  __int64 v17; // rcx
  JET_ERR v18; // r12d
  int *v19; // rax
  __int64 v20; // rcx
  JET_ERR v21; // r12d
  int *v22; // rax
  __int64 v23; // rcx
  JET_ERR v24; // ebp
  int *v25; // rax
  unsigned int *pcbActual; // [rsp+20h] [rbp-58h]
  unsigned int *pcbActuala; // [rsp+20h] [rbp-58h]

  if ( !a2 )
  {
    v7 = -2147024809;
    v8 = (JET_SESID *)((char *)this + 40);
    goto LABEL_15;
  }
  v7 = 0;
  if ( a4 )
  {
    v10 = JetBeginTransaction(*((_QWORD *)this + 5));
    if ( v10 < 0 )
    {
      v11 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v9);
      DSLogger::LogError((DSLogger *)v11, L"DbTable::Insert", 0x1E3u, L"JET_ERR : %d", v10);
      v7 = JetToHResult(v10);
      if ( v7 < 0 )
        return (unsigned int)v7;
    }
  }
  v8 = (JET_SESID *)((char *)this + 40);
  v12 = 1;
  v13 = 1;
  v15 = JetPrepareUpdate(*((_QWORD *)this + 5), *((_QWORD *)this + 9), 0);
  if ( v15 >= 0
    || (v16 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v14),
        LODWORD(pcbActual) = v15,
        DSLogger::LogError((DSLogger *)v16, L"DbTable::Insert", 0x1EAu, L"JET_ERR : %d", pcbActual),
        v7 = JetToHResult(v15),
        v7 >= 0) )
  {
    v18 = JetSetColumns(*v8, *((_QWORD *)this + 9), a2, a3);
    if ( v18 >= 0
      || (v19 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v17),
          LODWORD(pcbActual) = v18,
          DSLogger::LogError((DSLogger *)v19, L"DbTable::Insert", 0x1EDu, L"JET_ERR : %d", pcbActual),
          v7 = JetToHResult(v18),
          v7 >= 0) )
    {
      v21 = JetUpdate(*v8, *((_QWORD *)this + 9), 0, 0, 0);
      if ( v21 >= 0
        || (v22 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v20),
            LODWORD(pcbActuala) = v21,
            DSLogger::LogError((DSLogger *)v22, L"DbTable::Insert", 0x1F3u, L"JET_ERR : %d", pcbActuala),
            v7 = JetToHResult(v21),
            v7 >= 0) )
      {
        if ( !a4 )
        {
LABEL_16:
          v13 = 0;
          goto LABEL_17;
        }
        v24 = JetCommitTransaction(*v8, 0);
        if ( v24 < 0 )
        {
          v25 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v23);
          LODWORD(pcbActuala) = v24;
          DSLogger::LogError((DSLogger *)v25, L"DbTable::Insert", 0x1F7u, L"JET_ERR : %d", pcbActuala);
          v7 = JetToHResult(v24);
          if ( v7 < 0 )
            goto LABEL_19;
        }
LABEL_15:
        v12 = 0;
        goto LABEL_16;
      }
    }
  }
LABEL_17:
  if ( a4 && v12 )
LABEL_19:
    JetRollback(*v8, 0);
  if ( v13 )
    JetPrepareUpdate(*v8, *((_QWORD *)this + 9), 3u);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180014eb0  mov     [rsp+csetcolumn], r8d
0x180014eb5  push    rbx
0x180014eb6  push    rbp
0x180014eb7  push    rsi
0x180014eb8  push    rdi
0x180014eb9  push    r12
0x180014ebb  push    r13
0x180014ebd  push    r14
0x180014ebf  push    r15
0x180014ec1  sub     rsp, 38h
0x180014ec5  mov     r14d, r9d
0x180014ec8  mov     r12, rdx
0x180014ecb  mov     rsi, rcx
0x180014ece  test    rdx, rdx
0x180014ed1  jnz     short loc_180014EE1
0x180014ed3  mov     edi, 80070057h
0x180014ed8  lea     rbx, [rcx+28h]
0x180014edc  jmp     loc_18001507F
0x180014ee1  xor     edi, edi
0x180014ee3  test    r14d, r14d
0x180014ee6  jz      short loc_180014F2E
0x180014ee8  mov     rcx, [rcx+28h]; sesid
0x180014eec  call    cs:__imp_JetBeginTransaction
0x180014ef2  mov     ebx, eax
0x180014ef4  test    eax, eax
0x180014ef6  jns     short loc_180014F2E
0x180014ef8  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180014efd  lea     r9, aJetErrD; "JET_ERR : %d"
0x180014f04  mov     dword ptr [rsp+78h+pcbActual], ebx
0x180014f08  mov     r8d, 1E3h; unsigned int
0x180014f0e  lea     rdx, aDbtableInsert; "DbTable::Insert"
0x180014f15  mov     rcx, rax; this
0x180014f18  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180014f1d  mov     ecx, ebx; int
0x180014f1f  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x180014f24  mov     edi, eax
0x180014f26  test    eax, eax
0x180014f28  js      loc_1800150B0
0x180014f2e  mov     rdx, [rsi+48h]; tableid
0x180014f32  lea     rbx, [rsi+28h]
0x180014f36  mov     rcx, [rbx]; sesid
0x180014f39  mov     ebp, 1
0x180014f3e  xor     r8d, r8d; prep
0x180014f41  mov     r15d, ebp
0x180014f44  call    cs:__imp_JetPrepareUpdate
0x180014f4a  mov     r13d, eax
0x180014f4d  test    eax, eax
0x180014f4f  jns     short loc_180014F89
0x180014f51  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180014f56  lea     r9, aJetErrD; "JET_ERR : %d"
0x180014f5d  mov     dword ptr [rsp+78h+pcbActual], r13d
0x180014f62  mov     r8d, 1EAh; unsigned int
0x180014f68  lea     rdx, aDbtableInsert; "DbTable::Insert"
0x180014f6f  mov     rcx, rax; this
0x180014f72  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180014f77  mov     ecx, r13d; int
0x180014f7a  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x180014f7f  mov     edi, eax
0x180014f81  test    eax, eax
0x180014f83  js      loc_180015084
0x180014f89  mov     r9d, [rsp+78h+csetcolumn]; csetcolumn
0x180014f91  mov     r8, r12; psetcolumn
0x180014f94  mov     rdx, [rsi+48h]; tableid
0x180014f98  mov     rcx, [rbx]; sesid
0x180014f9b  call    cs:__imp_JetSetColumns
0x180014fa1  mov     r12d, eax
0x180014fa4  test    eax, eax
0x180014fa6  jns     short loc_180014FE0
0x180014fa8  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180014fad  lea     r9, aJetErrD; "JET_ERR : %d"
0x180014fb4  mov     dword ptr [rsp+78h+pcbActual], r12d
0x180014fb9  mov     r8d, 1EDh; unsigned int
0x180014fbf  lea     rdx, aDbtableInsert; "DbTable::Insert"
0x180014fc6  mov     rcx, rax; this
0x180014fc9  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180014fce  mov     ecx, r12d; int
0x180014fd1  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x180014fd6  mov     edi, eax
0x180014fd8  test    eax, eax
0x180014fda  js      loc_180015084
0x180014fe0  mov     rdx, [rsi+48h]; tableid
0x180014fe4  xor     r9d, r9d; cbBookmark
0x180014fe7  mov     rcx, [rbx]; sesid
0x180014fea  xor     r8d, r8d; pvBookmark
0x180014fed  mov     [rsp+78h+pcbActual], 0; pcbActual
0x180014ff6  call    cs:__imp_JetUpdate
0x180014ffc  mov     r12d, eax
0x180014fff  test    eax, eax
0x180015001  jns     short loc_180015037
0x180015003  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180015008  lea     r9, aJetErrD; "JET_ERR : %d"
0x18001500f  mov     dword ptr [rsp+78h+pcbActual], r12d
0x180015014  mov     r8d, 1F3h; unsigned int
0x18001501a  lea     rdx, aDbtableInsert; "DbTable::Insert"
0x180015021  mov     rcx, rax; this
0x180015024  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180015029  mov     ecx, r12d; int
0x18001502c  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x180015031  mov     edi, eax
0x180015033  test    eax, eax
0x180015035  js      short loc_180015084
0x180015037  test    r14d, r14d
0x18001503a  jz      short loc_180015081
0x18001503c  mov     rcx, [rbx]; sesid
0x18001503f  xor     edx, edx; grbit
0x180015041  call    cs:__imp_JetCommitTransaction
0x180015047  mov     ebp, eax
0x180015049  test    eax, eax
0x18001504b  jns     short loc_18001507F
0x18001504d  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180015052  lea     r9, aJetErrD; "JET_ERR : %d"
0x180015059  mov     dword ptr [rsp+78h+pcbActual], ebp
0x18001505d  mov     r8d, 1F7h; unsigned int
0x180015063  lea     rdx, aDbtableInsert; "DbTable::Insert"
0x18001506a  mov     rcx, rax; this
0x18001506d  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180015072  mov     ecx, ebp; int
0x180015074  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x180015079  mov     edi, eax
0x18001507b  test    eax, eax
0x18001507d  js      short loc_18001508D
0x18001507f  xor     ebp, ebp
0x180015081  xor     r15d, r15d
0x180015084  test    r14d, r14d
0x180015087  jz      short loc_180015098
0x180015089  test    ebp, ebp
0x18001508b  jz      short loc_180015098
0x18001508d  mov     rcx, [rbx]; sesid
0x180015090  xor     edx, edx; grbit
0x180015092  call    cs:__imp_JetRollback
0x180015098  test    r15d, r15d
0x18001509b  jz      short loc_1800150B0
0x18001509d  mov     rdx, [rsi+48h]; tableid
0x1800150a1  mov     r8d, 3; prep
0x1800150a7  mov     rcx, [rbx]; sesid
0x1800150aa  call    cs:__imp_JetPrepareUpdate
0x1800150b0  mov     eax, edi
0x1800150b2  add     rsp, 38h
0x1800150b6  pop     r15
0x1800150b8  pop     r14
0x1800150ba  pop     r13
0x1800150bc  pop     r12
0x1800150be  pop     rdi
0x1800150bf  pop     rsi
0x1800150c0  pop     rbp
0x1800150c1  pop     rbx
0x1800150c2  retn
```
