# DbTable::Initialize(tagJET_TABLECREATE_W *,tlx::smart_ptr<DbSession,&tlx::_delete<DbSession>(DbSession *),utl::allocator<int>> const &,int)

- ea: `0x180014a18`
- end: `0x180014dca`
- name: `?Initialize@DbTable@@QEAAJPEAUtagJET_TABLECREATE_W@@AEBV?$smart_ptr@VDbSession@@$1??$_delete@VDbSession@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@H@Z`
- size: `946`
- prototype: `__int64 __fastcall(DbTable *this)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x1800177b0`
- `0x1800178c0`

## callees

- `0x180006b84`
- `0x180006f78`
- `0x18000bf80`
- `0x18000f120`
- `0x1800114e4`
- `0x1800144d4`
- `0x1800144e8`
- `0x180014a18`
- `0x1800150cc`
- `0x18001b340`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180014ab2`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180014ab2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014ae3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014ae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d59`
- `ESENT!JetOpenTableW` at `0x180014b51`
- `ESENT!JetOpenTableW` at `0x180014b51`
- `ESENT!JetGetTableColumnInfoW` at `0x180014be5`
- `ESENT!JetGetTableColumnInfoW` at `0x180014be5`
- `ESENT!JetAddColumnW` at `0x180014c6c`
- `ESENT!JetAddColumnW` at `0x180014c6c`

## pseudocode

```c
__int64 __fastcall DbTable::Initialize(DbTable *this, __int64 a2, __int64 *a3, int a4)
{
  __int64 v7; // rdx
  utl::_RefCountBase *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r10
  __int128 v11; // xmm0
  signed int v12; // ebx
  HANDLE *v13; // rsi
  HANDLE MutexW; // rbx
  __int64 v15; // rax
  __int64 v16; // rcx
  JET_SESID v17; // rcx
  JET_TABLEID *v18; // r12
  __int64 v19; // r8
  JET_DBID v20; // edx
  __int64 v21; // rcx
  JET_ERR TableColumnInfoW; // esi
  DSLogger *v23; // rax
  int v24; // r14d
  __int64 v25; // r15
  __int64 v26; // rcx
  __int64 v27; // r8
  JET_TABLEID v28; // rdx
  JET_SESID v29; // rcx
  DSLogger *v30; // rax
  DSLogger *v31; // rax
  DSLogger *v32; // rax
  signed int LastError; // eax
  DSLogger *v34; // rax
  unsigned int cbParameters[2]; // [rsp+20h] [rbp-79h]
  __int64 grbit; // [rsp+28h] [rbp-71h]
  int v38; // [rsp+40h] [rbp-59h] BYREF
  __int128 v39; // [rsp+48h] [rbp-51h] BYREF
  char v40; // [rsp+58h] [rbp-41h]
  _OWORD v41[2]; // [rsp+60h] [rbp-39h] BYREF
  JET_COLUMNDEF pvResult; // [rsp+80h] [rbp-19h] BYREF

  v38 = 0;
  v11 = *(_OWORD *)lambda_0a2a10e62160711fcf676b028abd7e24_::_lambda_0a2a10e62160711fcf676b028abd7e24_(&v39, &v38, this);
  v40 = 1;
  v39 = v11;
  if ( !v10 || !*(_QWORD *)(v10 + 32) || !*(_QWORD *)(v10 + 48) )
  {
    v12 = -2147024809;
LABEL_34:
    v34 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        v8,
                        v7,
                        v9);
    LODWORD(grbit) = v12;
    DSLogger::LogError(
      v34,
      L"DbTable::Initialize",
      0x1A3u,
      L"DbTable::Initialize for table=%s failed! hr=0x%x.",
      *(_QWORD *)(*(_QWORD *)this + 8LL),
      grbit);
    goto LABEL_35;
  }
  *(_QWORD *)this = v10;
  *((_QWORD *)this + 1) = *(_QWORD *)(v10 + 32);
  *((_DWORD *)this + 4) = *(_DWORD *)(v10 + 40);
  *((_QWORD *)this + 3) = *(_QWORD *)(v10 + 48);
  *((_DWORD *)this + 8) = *(_DWORD *)(v10 + 56);
  v13 = (HANDLE *)((char *)this + 80);
  MutexW = CreateMutexW(0, 0, *(LPCWSTR *)(v10 + 8));
  if ( MutexW == *((HANDLE *)this + 10) )
  {
    MutexW = *v13;
  }
  else
  {
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete((char *)this + 80);
    *v13 = MutexW;
  }
  if ( !MutexW )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_34;
  }
  WaitForSingleObject(MutexW, 0xFFFFFFFF);
  v15 = a3[1];
  v16 = *a3;
  v38 = 1;
  if ( v15 )
    _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
  *((_QWORD *)this + 7) = v16;
  v8 = (utl::_RefCountBase *)*((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = v15;
  if ( v8 )
    utl::_RefCountBase::_DecStrong(v8);
  v7 = *((_QWORD *)this + 7);
  if ( !v7 )
  {
    v12 = -2147024882;
    goto LABEL_34;
  }
  v17 = *(_QWORD *)(v7 + 40);
  v18 = (JET_TABLEID *)((char *)this + 72);
  v19 = *(_QWORD *)this;
  *((_QWORD *)this + 5) = v17;
  v12 = 0;
  v20 = *(_DWORD *)(v7 + 48);
  *((_DWORD *)this + 12) = v20;
  TableColumnInfoW = JetOpenTableW(v17, v20, *(JET_PCWSTR *)(v19 + 8), 0, 0, 0, (JET_TABLEID *)this + 9);
  if ( TableColumnInfoW < 0 )
  {
    v23 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        v21,
                        v7,
                        v9);
    cbParameters[0] = TableColumnInfoW;
    DSLogger::LogError(v23, L"DbTable::Initialize", 0x168u, L"JET_ERR : %d", *(_QWORD *)cbParameters);
    v12 = JetToHResult(TableColumnInfoW);
    if ( v12 < 0 )
      goto LABEL_34;
  }
  v8 = (utl::_RefCountBase *)*((_QWORD *)this + 1);
  if ( !*((_DWORD *)v8 + 12) )
  {
    v24 = 0;
    memset(&pvResult, 0, sizeof(pvResult));
    if ( *((int *)this + 4) > 0 )
    {
      do
      {
        v25 = 56LL * v24;
        TableColumnInfoW = JetGetTableColumnInfoW(
                             *((_QWORD *)this + 5),
                             *v18,
                             *(JET_PCWSTR *)(v25 + *((_QWORD *)this + 1) + 8),
                             &pvResult,
                             0x1Cu,
                             0);
        if ( TableColumnInfoW == -1507 )
        {
          v27 = *((_QWORD *)this + 1);
          v28 = *v18;
          v29 = *((_QWORD *)this + 5);
          memset(v41, 0, 28);
          *(_OWORD *)&pvResult.cbStruct = v41[0];
          *(_OWORD *)&pvResult.wCountry = 0;
          pvResult.cbStruct = *(_DWORD *)(v25 + v27);
          pvResult.coltyp = *(_DWORD *)(v25 + v27 + 16);
          pvResult.cbMax = *(_DWORD *)(v25 + v27 + 20);
          pvResult.cp = *(_WORD *)(v25 + v27 + 44);
          pvResult.grbit = *(_DWORD *)(v25 + v27 + 24);
          TableColumnInfoW = JetAddColumnW(
                               v29,
                               v28,
                               *(JET_PCWSTR *)(v25 + v27 + 8),
                               &pvResult,
                               *(const void **)(v25 + v27 + 32),
                               *(_DWORD *)(v25 + v27 + 40),
                               (JET_COLUMNID *)(v25 + v27 + 48));
          if ( TableColumnInfoW < 0 )
          {
            v30 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                                v8,
                                v7,
                                v9);
            cbParameters[0] = TableColumnInfoW;
            DSLogger::LogError(v30, L"DbTable::Initialize", 0x18Cu, L"JET_ERR : %d", *(_QWORD *)cbParameters);
            v12 = JetToHResult(TableColumnInfoW);
            if ( v12 < 0 )
              goto LABEL_34;
          }
        }
        else
        {
          if ( TableColumnInfoW < 0 )
          {
            v31 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                                v26,
                                v7,
                                v9);
            cbParameters[0] = TableColumnInfoW;
            DSLogger::LogError(v31, L"DbTable::Initialize", 0x190u, L"JET_ERR : %d", *(_QWORD *)cbParameters);
            v12 = JetToHResult(TableColumnInfoW);
            if ( v12 < 0 )
              goto LABEL_34;
          }
          v8 = (utl::_RefCountBase *)*((_QWORD *)this + 1);
          *(_DWORD *)((char *)v8 + v25 + 48) = pvResult.columnid;
        }
      }
      while ( ++v24 < *((_DWORD *)this + 4) );
    }
  }
  if ( a4 )
  {
    v12 = DbTable::RebuildSecondaryIndexes(this);
    if ( v12 < 0 )
      goto LABEL_34;
  }
  if ( TableColumnInfoW < 0 )
  {
    v32 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        v8,
                        v7,
                        v9);
    cbParameters[0] = TableColumnInfoW;
    DSLogger::LogError(v32, L"DbTable::Initialize", 0x19Du, L"JET_ERR : %d", *(_QWORD *)cbParameters);
    v12 = JetToHResult(TableColumnInfoW);
    if ( v12 < 0 )
      goto LABEL_34;
  }
LABEL_35:
  tlx::_UndoSolo__lambda_0a2a10e62160711fcf676b028abd7e24___::__UndoSolo__lambda_0a2a10e62160711fcf676b028abd7e24___(&v39);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180014a18  push    rbp
0x180014a1a  push    rbx
0x180014a1b  push    rsi
0x180014a1c  push    rdi
0x180014a1d  push    r12
0x180014a1f  push    r13
0x180014a21  push    r14
0x180014a23  push    r15
0x180014a25  lea     rbp, [rsp-1Fh]
0x180014a2a  sub     rsp, 0B8h
0x180014a31  mov     rax, cs:__security_cookie
0x180014a38  xor     rax, rsp
0x180014a3b  mov     [rbp+57h+var_50], rax
0x180014a3f  mov     r14, r8
0x180014a42  mov     r10, rdx
0x180014a45  mov     r8, rcx
0x180014a48  lea     rdx, [rbp+57h+var_B0]
0x180014a4c  mov     rdi, rcx
0x180014a4f  xor     r15d, r15d
0x180014a52  lea     rcx, [rbp+57h+var_A8]
0x180014a56  mov     [rbp+57h+var_B0], r15d
0x180014a5a  mov     r13d, r9d
0x180014a5d  call    _lambda_0a2a10e62160711fcf676b028abd7e24____lambda_0a2a10e62160711fcf676b028abd7e24_
0x180014a62  movups  xmm0, xmmword ptr [rax]
0x180014a65  mov     [rbp+57h+var_98], 1
0x180014a69  movdqu  [rbp+57h+var_A8], xmm0
0x180014a6e  test    r10, r10
0x180014a71  jnz     short loc_180014A7D
0x180014a73  mov     ebx, 80070057h
0x180014a78  jmp     loc_180014D6E
0x180014a7d  cmp     [r10+20h], r15
0x180014a81  jz      short loc_180014A73
0x180014a83  cmp     [r10+30h], r15
0x180014a87  jz      short loc_180014A73
0x180014a89  mov     [rdi], r10
0x180014a8c  xor     edx, edx; bInitialOwner
0x180014a8e  mov     rax, [r10+20h]
0x180014a92  xor     ecx, ecx; lpMutexAttributes
0x180014a94  mov     [rdi+8], rax
0x180014a98  mov     eax, [r10+28h]
0x180014a9c  mov     [rdi+10h], eax
0x180014a9f  mov     rax, [r10+30h]
0x180014aa3  mov     [rdi+18h], rax
0x180014aa7  mov     eax, [r10+38h]
0x180014aab  mov     [rdi+20h], eax
0x180014aae  mov     r8, [r10+8]; lpName
0x180014ab2  call    cs:__imp_CreateMutexW
0x180014ab8  lea     rsi, [rdi+50h]
0x180014abc  mov     rbx, rax
0x180014abf  cmp     rax, [rsi]
0x180014ac2  jz      short loc_180014AD1
0x180014ac4  mov     rcx, rsi
0x180014ac7  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x180014acc  mov     [rsi], rbx
0x180014acf  jmp     short loc_180014AD4
0x180014ad1  mov     rbx, [rsi]
0x180014ad4  test    rbx, rbx
0x180014ad7  jz      loc_180014D59
0x180014add  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180014ae0  mov     rcx, rbx; hHandle
0x180014ae3  call    cs:__imp_WaitForSingleObject
0x180014ae9  mov     rax, [r14+8]
0x180014aed  mov     rcx, [r14]
0x180014af0  mov     [rbp+57h+var_B0], 1
0x180014af7  test    rax, rax
0x180014afa  jz      short loc_180014B00
0x180014afc  lock inc dword ptr [rax+8]
0x180014b00  mov     [rdi+38h], rcx
0x180014b04  mov     rcx, [rdi+40h]; this
0x180014b08  mov     [rdi+40h], rax
0x180014b0c  test    rcx, rcx
0x180014b0f  jz      short loc_180014B16
0x180014b11  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180014b16  mov     rdx, [rdi+38h]
0x180014b1a  test    rdx, rdx
0x180014b1d  jz      loc_180014D52
0x180014b23  mov     rcx, [rdx+28h]; sesid
0x180014b27  lea     r12, [rdi+48h]
0x180014b2b  mov     r8, [rdi]
0x180014b2e  xor     r9d, r9d; pvParameters
0x180014b31  mov     [rdi+28h], rcx
0x180014b35  mov     ebx, r15d
0x180014b38  mov     edx, [rdx+30h]; dbid
0x180014b3b  mov     [rdi+30h], edx
0x180014b3e  mov     r8, [r8+8]; szTableName
0x180014b42  mov     [rsp+0F0h+ptableid], r12; ptableid
0x180014b47  mov     dword ptr [rsp+0F0h+grbit], r15d; grbit
0x180014b4c  mov     [rsp+0F0h+cbParameters], r15d; cbParameters
0x180014b51  call    cs:__imp_JetOpenTableW
0x180014b57  mov     esi, eax
0x180014b59  test    eax, eax
0x180014b5b  jns     short loc_180014B93
0x180014b5d  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180014b62  lea     r9, aJetErrD; "JET_ERR : %d"
0x180014b69  mov     [rsp+0F0h+cbParameters], esi
0x180014b6d  mov     r8d, 168h; unsigned int
0x180014b73  lea     rdx, aDbtableInitial_0; "DbTable::Initialize"
0x180014b7a  mov     rcx, rax; this
0x180014b7d  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180014b82  mov     ecx, esi; int
0x180014b84  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x180014b89  mov     ebx, eax
0x180014b8b  test    eax, eax
0x180014b8d  js      loc_180014D6E
0x180014b93  mov     rcx, [rdi+8]
0x180014b97  cmp     [rcx+30h], r15d
0x180014b9b  jnz     loc_180014D03
0x180014ba1  xorps   xmm0, xmm0
0x180014ba4  mov     r14d, r15d
0x180014ba7  movups  [rbp+57h+pvResult], xmm0
0x180014bab  movups  [rbp+57h+pvResult+0Ch], xmm0
0x180014baf  cmp     [rdi+10h], r15d
0x180014bb3  jle     loc_180014D03
0x180014bb9  mov     r8, [rdi+8]
0x180014bbd  lea     r9, [rbp+57h+pvResult]; pvResult
0x180014bc1  mov     rdx, [r12]; tableid
0x180014bc5  mov     rcx, [rdi+28h]; sesid
0x180014bc9  movsxd  rax, r14d
0x180014bcc  imul    r15, rax, 38h ; '8'
0x180014bd0  mov     dword ptr [rsp+0F0h+grbit], 0; InfoLevel
0x180014bd8  mov     [rsp+0F0h+cbParameters], 1Ch; cbMax
0x180014be0  mov     r8, [r15+r8+8]; szColumnName
0x180014be5  call    cs:__imp_JetGetTableColumnInfoW
0x180014beb  mov     esi, eax
0x180014bed  cmp     eax, 0FFFFFA1Dh
0x180014bf2  jnz     loc_180014CB0
0x180014bf8  mov     r8, [rdi+8]
0x180014bfc  lea     r9, [rbp+57h+pvResult]; pcolumndef
0x180014c00  mov     rdx, [r12]; tableid
0x180014c04  xorps   xmm1, xmm1
0x180014c07  mov     rcx, [rdi+28h]; sesid
0x180014c0b  movups  xmmword ptr [rbp+57h+var_90], xmm1
0x180014c0f  movups  xmmword ptr [rbp+57h+var_90+0Ch], xmm1
0x180014c13  movups  xmm0, xmmword ptr [rbp+57h+var_90]
0x180014c17  movups  [rbp+57h+pvResult], xmm0
0x180014c1b  movups  [rbp+57h+pvResult+0Ch], xmm1
0x180014c1f  mov     eax, [r15+r8]
0x180014c23  mov     dword ptr [rbp+57h+pvResult], eax
0x180014c26  mov     eax, [r15+r8+10h]
0x180014c2b  mov     dword ptr [rbp+57h+pvResult+8], eax
0x180014c2e  mov     eax, [r15+r8+14h]
0x180014c33  mov     [rbp+57h+var_5C], eax
0x180014c36  movzx   eax, word ptr [r15+r8+2Ch]
0x180014c3c  mov     [rbp+57h+var_60], ax
0x180014c40  mov     eax, [r15+r8+18h]
0x180014c45  mov     [rbp+57h+var_58], eax
0x180014c48  lea     rax, [r8+30h]
0x180014c4c  add     rax, r15
0x180014c4f  mov     [rsp+0F0h+ptableid], rax; pcolumnid
0x180014c54  mov     eax, [r15+r8+28h]
0x180014c59  mov     dword ptr [rsp+0F0h+grbit], eax; cbDefault
0x180014c5d  mov     rax, [r15+r8+20h]
0x180014c62  mov     r8, [r15+r8+8]; szColumnName
0x180014c67  mov     qword ptr [rsp+0F0h+cbParameters], rax; pvDefault
0x180014c6c  call    cs:__imp_JetAddColumnW
0x180014c72  mov     esi, eax
0x180014c74  test    eax, eax
0x180014c76  jns     short loc_180014CF6
0x180014c78  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180014c7d  lea     r9, aJetErrD; "JET_ERR : %d"
0x180014c84  mov     [rsp+0F0h+cbParameters], esi
0x180014c88  mov     r8d, 18Ch; unsigned int
0x180014c8e  lea     rdx, aDbtableInitial_0; "DbTable::Initialize"
0x180014c95  mov     rcx, rax; this
0x180014c98  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180014c9d  mov     ecx, esi; int
0x180014c9f  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x180014ca4  mov     ebx, eax
0x180014ca6  test    eax, eax
0x180014ca8  js      loc_180014D6E
0x180014cae  jmp     short loc_180014CF6
0x180014cb0  test    esi, esi
0x180014cb2  jns     short loc_180014CEA
0x180014cb4  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180014cb9  lea     r9, aJetErrD; "JET_ERR : %d"
0x180014cc0  mov     [rsp+0F0h+cbParameters], esi
0x180014cc4  mov     r8d, 190h; unsigned int
0x180014cca  lea     rdx, aDbtableInitial_0; "DbTable::Initialize"
0x180014cd1  mov     rcx, rax; this
0x180014cd4  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180014cd9  mov     ecx, esi; int
0x180014cdb  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x180014ce0  mov     ebx, eax
0x180014ce2  test    eax, eax
0x180014ce4  js      loc_180014D6E
0x180014cea  mov     rcx, [rdi+8]
0x180014cee  mov     eax, dword ptr [rbp+57h+pvResult+4]
0x180014cf1  mov     [r15+rcx+30h], eax
0x180014cf6  inc     r14d
0x180014cf9  cmp     r14d, [rdi+10h]
0x180014cfd  jl      loc_180014BB9
0x180014d03  test    r13d, r13d
0x180014d06  jz      short loc_180014D16
0x180014d08  mov     rcx, rdi; this
0x180014d0b  call    ?RebuildSecondaryIndexes@DbTable@@AEAAJXZ; DbTable::RebuildSecondaryIndexes(void)
0x180014d10  mov     ebx, eax
0x180014d12  test    eax, eax
0x180014d14  js      short loc_180014D6E
0x180014d16  test    esi, esi
0x180014d18  jns     loc_180014D9F
0x180014d1e  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180014d23  lea     r9, aJetErrD; "JET_ERR : %d"
0x180014d2a  mov     [rsp+0F0h+cbParameters], esi
0x180014d2e  mov     r8d, 19Dh; unsigned int
0x180014d34  lea     rdx, aDbtableInitial_0; "DbTable::Initialize"
0x180014d3b  mov     rcx, rax; this
0x180014d3e  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180014d43  mov     ecx, esi; int
0x180014d45  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x180014d4a  mov     ebx, eax
0x180014d4c  test    eax, eax
0x180014d4e  js      short loc_180014D6E
0x180014d50  jmp     short loc_180014D9F
0x180014d52  mov     ebx, 8007000Eh
0x180014d57  jmp     short loc_180014D6E
0x180014d59  call    cs:__imp_GetLastError
0x180014d5f  mov     ebx, eax
0x180014d61  test    eax, eax
0x180014d63  jle     short loc_180014D6E
0x180014d65  movzx   ebx, ax
0x180014d68  or      ebx, 80070000h
0x180014d6e  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180014d73  mov     rcx, [rdi]
0x180014d76  lea     r9, aDbtableInitial; "DbTable::Initialize for table=%s failed"...
0x180014d7d  mov     dword ptr [rsp+0F0h+grbit], ebx
0x180014d81  lea     rdx, aDbtableInitial_0; "DbTable::Initialize"
0x180014d88  mov     r8d, 1A3h; unsigned int
0x180014d8e  mov     rcx, [rcx+8]
0x180014d92  mov     qword ptr [rsp+0F0h+cbParameters], rcx
0x180014d97  mov     rcx, rax; this
0x180014d9a  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180014d9f  lea     rcx, [rbp+57h+var_A8]
0x180014da3  call    tlx___UndoSolo__lambda_0a2a10e62160711fcf676b028abd7e24_______UndoSolo__lambda_0a2a10e62160711fcf676b028abd7e24___
0x180014da8  mov     eax, ebx
0x180014daa  mov     rcx, [rbp+57h+var_50]
0x180014dae  xor     rcx, rsp; StackCookie
0x180014db1  call    __security_check_cookie
0x180014db6  add     rsp, 0B8h
0x180014dbd  pop     r15
0x180014dbf  pop     r14
0x180014dc1  pop     r13
0x180014dc3  pop     r12
0x180014dc5  pop     rdi
0x180014dc6  pop     rsi
0x180014dc7  pop     rbx
0x180014dc8  pop     rbp
0x180014dc9  retn
```
