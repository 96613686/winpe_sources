# SharingTokenDatabase::GetShareScope(tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>> &)

- ea: `0x180016dec`
- end: `0x180017017`
- name: `?GetShareScope@SharingTokenDatabase@@AEAAJAEAV?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@Z`
- size: `555`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `3`
- callee_count: `25`
- tags: `broker_com_uri`

## callers

- `0x18001686c`
- `0x180017140`
- `0x180017318`

## callees

- `0x180002ac8`
- `0x180006f78`
- `0x18000be3c`
- `0x18000bf80`
- `0x18000c758`
- `0x18000c794`
- `0x18000df34`
- `0x18000f120`
- `0x18000f218`
- `0x18000f4f8`
- `0x18000f5e4`
- `0x18000fbfc`
- `0x180015a64`
- `0x180015da4`
- `0x180015ff4`
- `0x18001601c`
- `0x1800160bc`
- `0x1800160e8`
- `0x180016114`
- `0x180016198`
- `0x180016a94`
- `0x180016bf0`
- `0x180016d68`
- `0x180016dec`
- `0x180017b5c`

## string_xrefs

- `0x180016f9a`: `SharingTokenDatabase::GetShareScope`

## pseudocode

```c
__int64 __fastcall SharingTokenDatabase::GetShareScope(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rdx
  utl::_RefCountBase *v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  bool v8; // zf
  __int64 v9; // rax
  int SCBasedOnGuid; // ebx
  __int64 v11; // rax
  int v12; // ebx
  __int64 v13; // rax
  int v14; // edx
  int Iterator; // eax
  DbTableIterator *v16; // rbx
  int Next; // eax
  char *v18; // rbx
  SharingTarget *v19; // rax
  DSLogger *v20; // rax
  __int64 v22; // [rsp+20h] [rbp-50h]
  PVOID v23; // [rsp+30h] [rbp-40h] BYREF
  PVOID v24; // [rsp+38h] [rbp-38h] BYREF
  utl::_RefCountBase *v25[2]; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v26[32]; // [rsp+50h] [rbp-20h] BYREF
  int v27; // [rsp+98h] [rbp+28h] BYREF
  PVOID P; // [rsp+A0h] [rbp+30h] BYREF
  PVOID v29; // [rsp+A8h] [rbp+38h] BYREF

  utl::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>(v26);
  v8 = *v4 == 0;
  *(_OWORD *)v25 = 0;
  v24 = 0;
  v23 = 0;
  v29 = 0;
  P = 0;
  v27 = 0;
  if ( v8 )
  {
LABEL_19:
    SCBasedOnGuid = -2147024809;
    goto LABEL_20;
  }
  v9 = tlx::replace<_jetSeekCriteria,&void tlx::_delete<_jetSeekCriteria>(_jetSeekCriteria *)>(&P);
  SCBasedOnGuid = GetSCBasedOnGuid(*a2 + 12LL, v9, &v27);
  if ( SCBasedOnGuid < 0 )
    goto LABEL_20;
  v11 = tlx::replace<DbTableAccess<SharingTargetTableAdapter>,&void tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(DbTableAccess<SharingTargetTableAdapter> *)>(&v24);
  SCBasedOnGuid = Database::GetTableAccess<SharingTargetTableAdapter>(a1, v11);
  if ( SCBasedOnGuid < 0 )
    goto LABEL_20;
  v12 = (int)v24;
  v13 = tlx::replace<DbObjectIterator<SharingTargetTableAdapter>,&void tlx::_delete<DbObjectIterator<SharingTargetTableAdapter>>(DbObjectIterator<SharingTargetTableAdapter> *)>(&v23);
  Iterator = DbTableAccess<SharingTargetTableAdapter>::GetIterator(v12, v14, 0, (_DWORD)P, v27, v13);
  SCBasedOnGuid = Iterator;
  if ( Iterator == 1 )
  {
    SCBasedOnGuid = -1055719418;
LABEL_20:
    v20 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        v5,
                        v4,
                        v6,
                        v7);
    LODWORD(v22) = SCBasedOnGuid;
    DSLogger::LogError(v20, L"SharingTokenDatabase::GetShareScope", 0x11Eu, L"hr=0x%x.", v22);
    goto LABEL_21;
  }
  if ( Iterator < 0 )
    goto LABEL_20;
  while ( 1 )
  {
    v16 = (DbTableIterator *)v23;
    tlx::replace<SharingTargetTableAdapter,&void tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *)>(&v29);
    Next = DbObjectIterator<SharingTargetTableAdapter>::GetNext(v16);
    SCBasedOnGuid = Next;
    if ( Next == 1 )
      break;
    if ( Next < 0 )
      goto LABEL_20;
    v18 = (char *)v29;
    if ( !v29 )
      goto LABEL_19;
    v19 = (SharingTarget *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v19 )
      v19 = SharingTarget::SharingTarget(v19);
    if ( (unsigned __int8)tlx::smart_xxx<SharingToken *,void (*)(SharingToken *),&void tlx::_delete<SharingToken>(SharingToken *),0,utl::allocator<int>>::reset(
                            v25,
                            v19) )
    {
      v5 = v25[0];
      if ( !v25[0] )
        goto LABEL_19;
      SCBasedOnGuid = SharingTarget::Initialize(
                        v25[0],
                        *((const unsigned __int16 **)v18 + 3),
                        (const enum _DS_SHARE_TARGET_TYPE *)(v18 + 56),
                        (const struct _GUID *)(v18 + 60));
      if ( SCBasedOnGuid < 0 )
        goto LABEL_20;
      if ( (unsigned __int8)utl::list<tlx::smart_ptr<SharingTargetTableAdapter,&void tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTargetTableAdapter,&void tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>>>>::push_back(
                              v26,
                              v25) )
        continue;
    }
    SCBasedOnGuid = -2147024882;
    goto LABEL_20;
  }
  SCBasedOnGuid = ShareAccessControl::InitializeScope(*a2 + 120LL, v26);
  if ( SCBasedOnGuid < 0 )
    goto LABEL_20;
LABEL_21:
  ReleaseSC(P, &v27);
  if ( P )
    Common::GlobalHeap::Free(P);
  if ( v25[1] )
    utl::_RefCountBase::_DecStrong(v25[1]);
  if ( v29 )
    tlx::_delete<SharingTargetTableAdapter>(v29);
  if ( v23 )
    tlx::_delete<DbObjectIterator<SharingToken>>(v23);
  if ( v24 )
    tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(v24);
  utl::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::clear(v26);
  return (unsigned int)SCBasedOnGuid;
}

```

## disassembly

```asm
0x180016dec  mov     [rsp-18h+arg_0], rbx
0x180016df1  push    rbp
0x180016df2  push    rsi
0x180016df3  push    rdi
0x180016df4  mov     rbp, rsp
0x180016df7  sub     rsp, 70h
0x180016dfb  mov     rsi, rcx
0x180016dfe  mov     rdi, rdx
0x180016e01  lea     rcx, [rbp+var_20]
0x180016e05  call    ??0?$list@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAA@XZ; utl::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>(void)
0x180016e0a  cmp     qword ptr [rdx], 0
0x180016e0e  xorps   xmm0, xmm0
0x180016e11  movdqu  xmmword ptr [rbp+var_30], xmm0
0x180016e16  mov     [rbp+var_38], 0
0x180016e1e  mov     [rbp+var_40], 0
0x180016e26  mov     [rbp+arg_18], 0
0x180016e2e  mov     [rbp+P], 0
0x180016e36  mov     [rbp+arg_8], 0
0x180016e3d  jz      loc_180016F7F
0x180016e43  lea     rcx, [rbp+P]
0x180016e47  call    ??$replace@U_jetSeekCriteria@@$1??$_delete@U_jetSeekCriteria@@@tlx@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_jetSeekCriteria@@AEAV?$auto_ptr@U_jetSeekCriteria@@$1??$_delete@U_jetSeekCriteria@@@tlx@@YAXPEAU1@@Z@0@@Z; tlx::replace<_jetSeekCriteria,&tlx::_delete<_jetSeekCriteria>(_jetSeekCriteria *)>(tlx::auto_ptr<_jetSeekCriteria,&tlx::_delete<_jetSeekCriteria>(_jetSeekCriteria *)> &)
0x180016e4c  mov     rcx, [rdi]
0x180016e4f  lea     r8, [rbp+arg_8]
0x180016e53  add     rcx, 0Ch
0x180016e57  mov     rdx, rax
0x180016e5a  call    GetSCBasedOnGuid
0x180016e5f  mov     ebx, eax
0x180016e61  test    eax, eax
0x180016e63  js      loc_180016F84
0x180016e69  lea     rcx, [rbp+var_38]
0x180016e6d  call    ??$replace@V?$DbTableAccess@VSharingTargetTableAdapter@@@@$1??$_delete@V?$DbTableAccess@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV1@@Z@tlx@@YAPEAPEAV?$DbTableAccess@VSharingTargetTableAdapter@@@@AEAV?$auto_ptr@V?$DbTableAccess@VSharingTargetTableAdapter@@@@$1??$_delete@V?$DbTableAccess@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV1@@Z@0@@Z; tlx::replace<DbTableAccess<SharingTargetTableAdapter>,&tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(DbTableAccess<SharingTargetTableAdapter> *)>(tlx::auto_ptr<DbTableAccess<SharingTargetTableAdapter>,&tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(DbTableAccess<SharingTargetTableAdapter> *)> &)
0x180016e72  mov     rdx, rax
0x180016e75  mov     rcx, rsi
0x180016e78  call    ??$GetTableAccess@VSharingTargetTableAdapter@@@Database@@QEAAJPEAPEAV?$DbTableAccess@VSharingTargetTableAdapter@@@@@Z; Database::GetTableAccess<SharingTargetTableAdapter>(DbTableAccess<SharingTargetTableAdapter> * *)
0x180016e7d  mov     ebx, eax
0x180016e7f  test    eax, eax
0x180016e81  js      loc_180016F84
0x180016e87  mov     rbx, [rbp+var_38]
0x180016e8b  lea     rcx, [rbp+var_40]
0x180016e8f  call    ??$replace@V?$DbObjectIterator@VSharingTargetTableAdapter@@@@$1??$_delete@V?$DbObjectIterator@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV1@@Z@tlx@@YAPEAPEAV?$DbObjectIterator@VSharingTargetTableAdapter@@@@AEAV?$auto_ptr@V?$DbObjectIterator@VSharingTargetTableAdapter@@@@$1??$_delete@V?$DbObjectIterator@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV1@@Z@0@@Z; tlx::replace<DbObjectIterator<SharingTargetTableAdapter>,&tlx::_delete<DbObjectIterator<SharingTargetTableAdapter>>(DbObjectIterator<SharingTargetTableAdapter> *)>(tlx::auto_ptr<DbObjectIterator<SharingTargetTableAdapter>,&tlx::_delete<DbObjectIterator<SharingTargetTableAdapter>>(DbObjectIterator<SharingTargetTableAdapter> *)> &)
0x180016e94  mov     r9, [rbp+P]
0x180016e98  xor     r8d, r8d
0x180016e9b  mov     [rsp+70h+var_48], rax
0x180016ea0  mov     rcx, rbx
0x180016ea3  mov     eax, [rbp+arg_8]
0x180016ea6  mov     dword ptr [rsp+70h+var_50], eax
0x180016eaa  call    ?GetIterator@?$DbTableAccess@VSharingTargetTableAdapter@@@@QEAAJKHPEAU_jetSeekCriteria@@KPEAPEAV?$DbObjectIterator@VSharingTargetTableAdapter@@@@@Z; DbTableAccess<SharingTargetTableAdapter>::GetIterator(ulong,int,_jetSeekCriteria *,ulong,DbObjectIterator<SharingTargetTableAdapter> * *)
0x180016eaf  mov     ebx, eax
0x180016eb1  cmp     eax, 1
0x180016eb4  jz      loc_180016F78
0x180016eba  test    eax, eax
0x180016ebc  js      loc_180016F84
0x180016ec2  mov     rbx, [rbp+var_40]
0x180016ec6  lea     rcx, [rbp+arg_18]
0x180016eca  call    ??$replace@VSharingTargetTableAdapter@@$1??$_delete@VSharingTargetTableAdapter@@@tlx@@YAXPEAV1@@Z@tlx@@YAPEAPEAVSharingTargetTableAdapter@@AEAV?$auto_ptr@VSharingTargetTableAdapter@@$1??$_delete@VSharingTargetTableAdapter@@@tlx@@YAXPEAV1@@Z@0@@Z; tlx::replace<SharingTargetTableAdapter,&tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *)>(tlx::auto_ptr<SharingTargetTableAdapter,&tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *)> &)
0x180016ecf  mov     rdx, rax
0x180016ed2  mov     rcx, rbx; this
0x180016ed5  call    ?GetNext@?$DbObjectIterator@VSharingTargetTableAdapter@@@@QEAAJPEAPEAVSharingTargetTableAdapter@@@Z; DbObjectIterator<SharingTargetTableAdapter>::GetNext(SharingTargetTableAdapter * *)
0x180016eda  mov     ebx, eax
0x180016edc  cmp     eax, 1
0x180016edf  jz      short loc_180016F60
0x180016ee1  test    eax, eax
0x180016ee3  js      loc_180016F84
0x180016ee9  mov     rbx, [rbp+arg_18]
0x180016eed  test    rbx, rbx
0x180016ef0  jz      loc_180016F7F
0x180016ef6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016efd  mov     ecx, 40h ; '@'; unsigned __int64
0x180016f02  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180016f07  test    rax, rax
0x180016f0a  jz      short loc_180016F14
0x180016f0c  mov     rcx, rax; this
0x180016f0f  call    ??0SharingTarget@@QEAA@XZ; SharingTarget::SharingTarget(void)
0x180016f14  mov     rdx, rax
0x180016f17  lea     rcx, [rbp+var_30]
0x180016f1b  call    ?reset@?$smart_xxx@PEAVSharingToken@@P6AXPEAV1@@Z$1??$_delete@VSharingToken@@@tlx@@YAX0@Z$0A@V?$allocator@H@utl@@@tlx@@QEAA_NPEAVSharingToken@@@Z; tlx::smart_xxx<SharingToken *,void (*)(SharingToken *),&tlx::_delete<SharingToken>(SharingToken *),0,utl::allocator<int>>::reset(SharingToken *)
0x180016f20  test    al, al
0x180016f22  jz      short loc_180016F59
0x180016f24  mov     rcx, [rbp+var_30]; this
0x180016f28  test    rcx, rcx
0x180016f2b  jz      short loc_180016F7F
0x180016f2d  mov     rdx, [rbx+18h]; unsigned __int16 *
0x180016f31  lea     r9, [rbx+3Ch]; struct _GUID *
0x180016f35  lea     r8, [rbx+38h]; enum _DS_SHARE_TARGET_TYPE *
0x180016f39  call    ?Initialize@SharingTarget@@QEAAJPEBGAEBW4_DS_SHARE_TARGET_TYPE@@AEBU_GUID@@@Z; SharingTarget::Initialize(ushort const *,_DS_SHARE_TARGET_TYPE const &,_GUID const &)
0x180016f3e  mov     ebx, eax
0x180016f40  test    eax, eax
0x180016f42  js      short loc_180016F84
0x180016f44  lea     rdx, [rbp+var_30]
0x180016f48  lea     rcx, [rbp+var_20]
0x180016f4c  call    ?push_back@?$list@V?$smart_ptr@VSharingTargetTableAdapter@@$1??$_delete@VSharingTargetTableAdapter@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTargetTableAdapter@@$1??$_delete@VSharingTargetTableAdapter@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAA_NAEBV?$smart_ptr@VSharingTargetTableAdapter@@$1??$_delete@VSharingTargetTableAdapter@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@Z; utl::list<tlx::smart_ptr<SharingTargetTableAdapter,&tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTargetTableAdapter,&tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>>>>::push_back(tlx::smart_ptr<SharingTargetTableAdapter,&tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>> const &)
0x180016f51  test    al, al
0x180016f53  jnz     loc_180016EC2
0x180016f59  mov     ebx, 8007000Eh
0x180016f5e  jmp     short loc_180016F84
0x180016f60  mov     rcx, [rdi]
0x180016f63  lea     rdx, [rbp+var_20]
0x180016f67  add     rcx, 78h ; 'x'
0x180016f6b  call    ?InitializeScope@ShareAccessControl@@QEAAJAEBV?$list@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@@Z; ShareAccessControl::InitializeScope(utl::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>> const &)
0x180016f70  mov     ebx, eax
0x180016f72  test    eax, eax
0x180016f74  js      short loc_180016F84
0x180016f76  jmp     short loc_180016FA9
0x180016f78  mov     ebx, 0C1130006h
0x180016f7d  jmp     short loc_180016F84
0x180016f7f  mov     ebx, 80070057h
0x180016f84  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180016f89  lea     r9, aHr0xX; "hr=0x%x."
0x180016f90  mov     dword ptr [rsp+70h+var_50], ebx
0x180016f94  mov     r8d, 11Eh; unsigned int
0x180016f9a  lea     rdx, aSharingtokenda_0; "SharingTokenDatabase::GetShareScope"
0x180016fa1  mov     rcx, rax; this
0x180016fa4  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180016fa9  mov     rcx, [rbp+P]
0x180016fad  lea     rdx, [rbp+arg_8]
0x180016fb1  call    ReleaseSC
0x180016fb6  mov     rcx, [rbp+P]; P
0x180016fba  test    rcx, rcx
0x180016fbd  jz      short loc_180016FC4
0x180016fbf  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180016fc4  mov     rcx, [rbp+var_30+8]; this
0x180016fc8  test    rcx, rcx
0x180016fcb  jz      short loc_180016FD2
0x180016fcd  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180016fd2  mov     rcx, [rbp+arg_18]; P
0x180016fd6  test    rcx, rcx
0x180016fd9  jz      short loc_180016FE0
0x180016fdb  call    ??$_delete@VSharingTargetTableAdapter@@@tlx@@YAXPEAVSharingTargetTableAdapter@@@Z; tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *)
0x180016fe0  mov     rcx, [rbp+var_40]; P
0x180016fe4  test    rcx, rcx
0x180016fe7  jz      short loc_180016FEE
0x180016fe9  call    ??$_delete@V?$DbObjectIterator@VSharingToken@@@@@tlx@@YAXPEAV?$DbObjectIterator@VSharingToken@@@@@Z; tlx::_delete<DbObjectIterator<SharingToken>>(DbObjectIterator<SharingToken> *)
0x180016fee  mov     rcx, [rbp+var_38]; P
0x180016ff2  test    rcx, rcx
0x180016ff5  jz      short loc_180016FFC
0x180016ff7  call    ??$_delete@V?$DbTableAccess@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV?$DbTableAccess@VSharingTargetTableAdapter@@@@@Z; tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(DbTableAccess<SharingTargetTableAdapter> *)
0x180016ffc  lea     rcx, [rbp+var_20]
0x180017000  call    ?clear@?$list@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAAXXZ; utl::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::clear(void)
0x180017005  mov     eax, ebx
0x180017007  mov     rbx, [rsp+70h+arg_0]
0x18001700f  add     rsp, 70h
0x180017013  pop     rdi
0x180017014  pop     rsi
0x180017015  pop     rbp
0x180017016  retn
```
