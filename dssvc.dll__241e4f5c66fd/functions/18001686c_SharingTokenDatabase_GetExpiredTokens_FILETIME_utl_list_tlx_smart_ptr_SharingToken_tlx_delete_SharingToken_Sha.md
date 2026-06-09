# SharingTokenDatabase::GetExpiredTokens(_FILETIME,utl::list<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>>> &)

- ea: `0x18001686c`
- end: `0x180016a8c`
- name: `?GetExpiredTokens@SharingTokenDatabase@@QEAAJU_FILETIME@@AEAV?$list@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@@Z`
- size: `544`
- prototype: `__int64 __fastcall(SharingTokenDatabase *this, FILETIME, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x18000d68c`

## callees

- `0x180006f78`
- `0x18000be3c`
- `0x18000bf80`
- `0x18000c65c`
- `0x18000f120`
- `0x18000f254`
- `0x18000f4f8`
- `0x18000f5e4`
- `0x180015e68`
- `0x180015ff4`
- `0x180016044`
- `0x1800160bc`
- `0x1800160e8`
- `0x180016140`
- `0x1800161c4`
- `0x180016340`
- `0x18001686c`
- `0x180016b40`
- `0x180016c60`
- `0x180016cd0`
- `0x180016dec`
- `0x180017a68`
- `0x180017b5c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800169ad`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800169ad`

## string_xrefs

- `0x180016a00`: `SharingTokenDatabase::GetExpiredTokens`

## pseudocode

```c
__int64 __fastcall SharingTokenDatabase::GetExpiredTokens(SharingTokenDatabase *this, FILETIME a2, __int64 a3)
{
  int SCBasedOnFileTime; // ebx
  __int64 v6; // rax
  __int64 v7; // rax
  int v8; // ebx
  __int64 v9; // rax
  int Iterator; // eax
  DbTableIterator *v11; // rbx
  int Next; // eax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  DSLogger *v18; // rax
  __int64 v20; // [rsp+20h] [rbp-40h]
  PVOID P; // [rsp+30h] [rbp-30h] BYREF
  __int64 v22; // [rsp+38h] [rbp-28h] BYREF
  PVOID v23; // [rsp+40h] [rbp-20h] BYREF
  PVOID v24; // [rsp+48h] [rbp-18h] BYREF
  utl::_RefCountBase *v25[2]; // [rsp+50h] [rbp-10h] BYREF
  FILETIME FileTime2; // [rsp+88h] [rbp+28h] BYREF
  int v27; // [rsp+98h] [rbp+38h] BYREF

  FileTime2 = a2;
  v24 = 0;
  v23 = 0;
  v22 = 0;
  *(_OWORD *)v25 = 0;
  utl::list<tlx::smart_ptr<SharingToken,&void tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingToken,&void tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>>>::clear(a3);
  P = 0;
  v27 = 0;
  SCBasedOnFileTime = SharingTokenDatabase::Initialize(
                        this,
                        L"\\Data\\Users\\System\\AppData\\Local\\DataSharing\\Storage\\");
  if ( SCBasedOnFileTime < 0 )
    goto LABEL_14;
  v6 = tlx::replace<_jetSeekCriteria,&void tlx::_delete<_jetSeekCriteria>(_jetSeekCriteria *)>(&P);
  SCBasedOnFileTime = GetSCBasedOnFileTime(&FileTime2, v6, &v27);
  if ( SCBasedOnFileTime < 0
    || (v7 = tlx::replace<DbTableAccess<SharingToken>,&void tlx::_delete<DbTableAccess<SharingToken>>(DbTableAccess<SharingToken> *)>(&v24),
        SCBasedOnFileTime = Database::GetTableAccess<SharingToken>(this, v7),
        SCBasedOnFileTime < 0)
    || (v8 = (int)v24,
        v9 = tlx::replace<DbObjectIterator<SharingTargetTableAdapter>,&void tlx::_delete<DbObjectIterator<SharingTargetTableAdapter>>(DbObjectIterator<SharingTargetTableAdapter> *)>(&v23),
        Iterator = DbTableAccess<SharingToken>::GetIterator(v8, 16, 1, (_DWORD)P, v27, v9),
        SCBasedOnFileTime = Iterator,
        Iterator < 0) )
  {
LABEL_14:
    utl::list<tlx::smart_ptr<SharingToken,&void tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingToken,&void tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>>>::clear(a3);
    v18 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        v15,
                        v14,
                        v16,
                        v17);
    LODWORD(v20) = SCBasedOnFileTime;
    DSLogger::LogError(v18, L"SharingTokenDatabase::GetExpiredTokens", 0x283u, L"hr=0x%x.", v20);
    SharingTokenDatabase::CheckAndSetRecoveryState(this, SCBasedOnFileTime);
  }
  else if ( Iterator != 1 )
  {
    while ( 1 )
    {
      v11 = (DbTableIterator *)v23;
      tlx::replace<SharingToken,&void tlx::_delete<SharingToken>(SharingToken *)>(&v22);
      Next = DbObjectIterator<SharingToken>::GetNext(v11);
      SCBasedOnFileTime = Next;
      if ( Next == 1 )
        break;
      if ( Next < 0 )
        goto LABEL_14;
      v13 = v22;
      if ( !v22 )
      {
        SCBasedOnFileTime = -2147024809;
        goto LABEL_14;
      }
      v22 = 0;
      if ( (unsigned __int8)tlx::smart_xxx<SharingToken *,void (*)(SharingToken *),&void tlx::_delete<SharingToken>(SharingToken *),0,utl::allocator<int>>::reset(
                              v25,
                              v13) )
      {
        if ( CompareFileTime((const FILETIME *)v25[0] + 12, &FileTime2) > 0 )
          continue;
        SCBasedOnFileTime = SharingTokenDatabase::GetShareScope(this, v25);
        if ( SCBasedOnFileTime < 0 )
          goto LABEL_14;
        if ( (unsigned __int8)utl::list<tlx::smart_ptr<SharingTargetTableAdapter,&void tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTargetTableAdapter,&void tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>>>>::push_back(
                                a3,
                                v25) )
          continue;
      }
      SCBasedOnFileTime = -2147024882;
      goto LABEL_14;
    }
    SCBasedOnFileTime = 0;
  }
  ReleaseSC(P, &v27);
  if ( P )
    Common::GlobalHeap::Free(P);
  if ( v25[1] )
    utl::_RefCountBase::_DecStrong(v25[1]);
  if ( v22 )
    tlx::_delete<DbEnumFilter>(v22);
  if ( v23 )
    tlx::_delete<DbObjectIterator<SharingToken>>(v23);
  if ( v24 )
    tlx::_delete<DbTableAccess<SharingToken>>(v24);
  return (unsigned int)SCBasedOnFileTime;
}

```

## disassembly

```asm
0x18001686c  mov     [rsp-18h+arg_0], rbx
0x180016871  mov     qword ptr [rsp-18h+FileTime2.dwLowDateTime], rdx
0x180016876  push    rbp
0x180016877  push    rsi
0x180016878  push    rdi
0x180016879  mov     rbp, rsp
0x18001687c  sub     rsp, 60h
0x180016880  mov     rdi, rcx
0x180016883  mov     [rbp+var_18], 0
0x18001688b  xorps   xmm0, xmm0
0x18001688e  mov     [rbp+var_20], 0
0x180016896  mov     rcx, r8
0x180016899  mov     [rbp+var_28], 0
0x1800168a1  movdqu  xmmword ptr [rbp+var_10], xmm0
0x1800168a6  mov     rsi, r8
0x1800168a9  call    ?clear@?$list@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAAXXZ; utl::list<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>>>::clear(void)
0x1800168ae  lea     rdx, pszPathIn; "\\Data\\Users\\System\\AppData\\Local\\"...
0x1800168b5  mov     [rbp+P], 0
0x1800168bd  mov     rcx, rdi; this
0x1800168c0  mov     [rbp+arg_18], 0
0x1800168c7  call    ?Initialize@SharingTokenDatabase@@QEAAJPEBG@Z; SharingTokenDatabase::Initialize(ushort const *)
0x1800168cc  mov     ebx, eax
0x1800168ce  test    eax, eax
0x1800168d0  js      loc_1800169E2
0x1800168d6  lea     rcx, [rbp+P]
0x1800168da  call    ??$replace@U_jetSeekCriteria@@$1??$_delete@U_jetSeekCriteria@@@tlx@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_jetSeekCriteria@@AEAV?$auto_ptr@U_jetSeekCriteria@@$1??$_delete@U_jetSeekCriteria@@@tlx@@YAXPEAU1@@Z@0@@Z; tlx::replace<_jetSeekCriteria,&tlx::_delete<_jetSeekCriteria>(_jetSeekCriteria *)>(tlx::auto_ptr<_jetSeekCriteria,&tlx::_delete<_jetSeekCriteria>(_jetSeekCriteria *)> &)
0x1800168df  mov     rdx, rax
0x1800168e2  lea     r8, [rbp+arg_18]
0x1800168e6  lea     rcx, [rbp+FileTime2]
0x1800168ea  call    GetSCBasedOnFileTime
0x1800168ef  mov     ebx, eax
0x1800168f1  test    eax, eax
0x1800168f3  js      loc_1800169E2
0x1800168f9  lea     rcx, [rbp+var_18]
0x1800168fd  call    ??$replace@V?$DbTableAccess@VSharingToken@@@@$1??$_delete@V?$DbTableAccess@VSharingToken@@@@@tlx@@YAXPEAV1@@Z@tlx@@YAPEAPEAV?$DbTableAccess@VSharingToken@@@@AEAV?$auto_ptr@V?$DbTableAccess@VSharingToken@@@@$1??$_delete@V?$DbTableAccess@VSharingToken@@@@@tlx@@YAXPEAV1@@Z@0@@Z; tlx::replace<DbTableAccess<SharingToken>,&tlx::_delete<DbTableAccess<SharingToken>>(DbTableAccess<SharingToken> *)>(tlx::auto_ptr<DbTableAccess<SharingToken>,&tlx::_delete<DbTableAccess<SharingToken>>(DbTableAccess<SharingToken> *)> &)
0x180016902  mov     rdx, rax
0x180016905  mov     rcx, rdi
0x180016908  call    ??$GetTableAccess@VSharingToken@@@Database@@QEAAJPEAPEAV?$DbTableAccess@VSharingToken@@@@@Z; Database::GetTableAccess<SharingToken>(DbTableAccess<SharingToken> * *)
0x18001690d  mov     ebx, eax
0x18001690f  test    eax, eax
0x180016911  js      loc_1800169E2
0x180016917  mov     rbx, [rbp+var_18]
0x18001691b  lea     rcx, [rbp+var_20]
0x18001691f  call    ??$replace@V?$DbObjectIterator@VSharingTargetTableAdapter@@@@$1??$_delete@V?$DbObjectIterator@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV1@@Z@tlx@@YAPEAPEAV?$DbObjectIterator@VSharingTargetTableAdapter@@@@AEAV?$auto_ptr@V?$DbObjectIterator@VSharingTargetTableAdapter@@@@$1??$_delete@V?$DbObjectIterator@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV1@@Z@0@@Z; tlx::replace<DbObjectIterator<SharingTargetTableAdapter>,&tlx::_delete<DbObjectIterator<SharingTargetTableAdapter>>(DbObjectIterator<SharingTargetTableAdapter> *)>(tlx::auto_ptr<DbObjectIterator<SharingTargetTableAdapter>,&tlx::_delete<DbObjectIterator<SharingTargetTableAdapter>>(DbObjectIterator<SharingTargetTableAdapter> *)> &)
0x180016924  mov     r9, [rbp+P]
0x180016928  mov     edx, 10h
0x18001692d  mov     [rsp+60h+var_38], rax
0x180016932  mov     rcx, rbx
0x180016935  mov     eax, [rbp+arg_18]
0x180016938  mov     dword ptr [rsp+60h+var_40], eax
0x18001693c  lea     r8d, [rdx-0Fh]
0x180016940  call    ?GetIterator@?$DbTableAccess@VSharingToken@@@@QEAAJKHPEAU_jetSeekCriteria@@KPEAPEAV?$DbObjectIterator@VSharingToken@@@@@Z; DbTableAccess<SharingToken>::GetIterator(ulong,int,_jetSeekCriteria *,ulong,DbObjectIterator<SharingToken> * *)
0x180016945  mov     ebx, eax
0x180016947  test    eax, eax
0x180016949  js      loc_1800169E2
0x18001694f  cmp     eax, 1
0x180016952  jz      loc_180016A19
0x180016958  mov     rbx, [rbp+var_20]
0x18001695c  lea     rcx, [rbp+var_28]
0x180016960  call    ??$replace@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@Z@tlx@@YAPEAPEAVSharingToken@@AEAV?$auto_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@Z@0@@Z; tlx::replace<SharingToken,&tlx::_delete<SharingToken>(SharingToken *)>(tlx::auto_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *)> &)
0x180016965  mov     rdx, rax
0x180016968  mov     rcx, rbx; this
0x18001696b  call    ?GetNext@?$DbObjectIterator@VSharingToken@@@@QEAAJPEAPEAVSharingToken@@@Z; DbObjectIterator<SharingToken>::GetNext(SharingToken * *)
0x180016970  mov     ebx, eax
0x180016972  cmp     eax, 1
0x180016975  jz      loc_180016A88
0x18001697b  test    eax, eax
0x18001697d  js      short loc_1800169E2
0x18001697f  mov     rdx, [rbp+var_28]
0x180016983  test    rdx, rdx
0x180016986  jz      loc_180016A7E
0x18001698c  lea     rcx, [rbp+var_10]
0x180016990  mov     [rbp+var_28], 0
0x180016998  call    ?reset@?$smart_xxx@PEAVSharingToken@@P6AXPEAV1@@Z$1??$_delete@VSharingToken@@@tlx@@YAX0@Z$0A@V?$allocator@H@utl@@@tlx@@QEAA_NPEAVSharingToken@@@Z; tlx::smart_xxx<SharingToken *,void (*)(SharingToken *),&tlx::_delete<SharingToken>(SharingToken *),0,utl::allocator<int>>::reset(SharingToken *)
0x18001699d  test    al, al
0x18001699f  jz      short loc_1800169DD
0x1800169a1  mov     rcx, [rbp+var_10]
0x1800169a5  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x1800169a9  add     rcx, 60h ; '`'; lpFileTime1
0x1800169ad  call    cs:__imp_CompareFileTime
0x1800169b3  test    eax, eax
0x1800169b5  jg      short loc_180016958
0x1800169b7  lea     rdx, [rbp+var_10]
0x1800169bb  mov     rcx, rdi
0x1800169be  call    ?GetShareScope@SharingTokenDatabase@@AEAAJAEAV?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@Z; SharingTokenDatabase::GetShareScope(tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>> &)
0x1800169c3  mov     ebx, eax
0x1800169c5  test    eax, eax
0x1800169c7  js      short loc_1800169E2
0x1800169c9  lea     rdx, [rbp+var_10]
0x1800169cd  mov     rcx, rsi
0x1800169d0  call    ?push_back@?$list@V?$smart_ptr@VSharingTargetTableAdapter@@$1??$_delete@VSharingTargetTableAdapter@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTargetTableAdapter@@$1??$_delete@VSharingTargetTableAdapter@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAA_NAEBV?$smart_ptr@VSharingTargetTableAdapter@@$1??$_delete@VSharingTargetTableAdapter@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@Z; utl::list<tlx::smart_ptr<SharingTargetTableAdapter,&tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTargetTableAdapter,&tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>>>>::push_back(tlx::smart_ptr<SharingTargetTableAdapter,&tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>> const &)
0x1800169d5  test    al, al
0x1800169d7  jnz     loc_180016958
0x1800169dd  mov     ebx, 8007000Eh
0x1800169e2  mov     rcx, rsi
0x1800169e5  call    ?clear@?$list@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAAXXZ; utl::list<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>>>::clear(void)
0x1800169ea  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800169ef  lea     r9, aHr0xX; "hr=0x%x."
0x1800169f6  mov     dword ptr [rsp+60h+var_40], ebx
0x1800169fa  mov     r8d, 283h; unsigned int
0x180016a00  lea     rdx, aSharingtokenda_3; "SharingTokenDatabase::GetExpiredTokens"
0x180016a07  mov     rcx, rax; this
0x180016a0a  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180016a0f  mov     edx, ebx; int
0x180016a11  mov     rcx, rdi; this
0x180016a14  call    ?CheckAndSetRecoveryState@SharingTokenDatabase@@AEAAXJ@Z; SharingTokenDatabase::CheckAndSetRecoveryState(long)
0x180016a19  mov     rcx, [rbp+P]
0x180016a1d  lea     rdx, [rbp+arg_18]
0x180016a21  call    ReleaseSC
0x180016a26  mov     rcx, [rbp+P]; P
0x180016a2a  test    rcx, rcx
0x180016a2d  jz      short loc_180016A34
0x180016a2f  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180016a34  mov     rcx, [rbp+var_10+8]; this
0x180016a38  test    rcx, rcx
0x180016a3b  jz      short loc_180016A42
0x180016a3d  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180016a42  mov     rcx, [rbp+var_28]
0x180016a46  test    rcx, rcx
0x180016a49  jz      short loc_180016A50
0x180016a4b  call    ??$_delete@VDbEnumFilter@@@tlx@@YAXPEAVDbEnumFilter@@@Z; tlx::_delete<DbEnumFilter>(DbEnumFilter *)
0x180016a50  mov     rcx, [rbp+var_20]; P
0x180016a54  test    rcx, rcx
0x180016a57  jz      short loc_180016A5E
0x180016a59  call    ??$_delete@V?$DbObjectIterator@VSharingToken@@@@@tlx@@YAXPEAV?$DbObjectIterator@VSharingToken@@@@@Z; tlx::_delete<DbObjectIterator<SharingToken>>(DbObjectIterator<SharingToken> *)
0x180016a5e  mov     rcx, [rbp+var_18]; P
0x180016a62  test    rcx, rcx
0x180016a65  jz      short loc_180016A6C
0x180016a67  call    ??$_delete@V?$DbTableAccess@VSharingToken@@@@@tlx@@YAXPEAV?$DbTableAccess@VSharingToken@@@@@Z; tlx::_delete<DbTableAccess<SharingToken>>(DbTableAccess<SharingToken> *)
0x180016a6c  mov     eax, ebx
0x180016a6e  mov     rbx, [rsp+60h+arg_0]
0x180016a76  add     rsp, 60h
0x180016a7a  pop     rdi
0x180016a7b  pop     rsi
0x180016a7c  pop     rbp
0x180016a7d  retn
0x180016a7e  mov     ebx, 80070057h
0x180016a83  jmp     loc_1800169E2
0x180016a88  xor     ebx, ebx
0x180016a8a  jmp     short loc_180016A19
```
