# SharingTokenDatabase::GetToken(_GUID const &,tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>> &)

- ea: `0x180017140`
- end: `0x18001730f`
- name: `?GetToken@SharingTokenDatabase@@QEAAJAEBU_GUID@@AEAV?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@Z`
- size: `463`
- prototype: `__int64 __fastcall(SharingTokenDatabase *this, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x18000da68`
- `0x180017518`

## callees

- `0x180006f78`
- `0x18000be3c`
- `0x18000bf80`
- `0x18000c65c`
- `0x18000f5e4`
- `0x18000f674`
- `0x180015e68`
- `0x180015ff4`
- `0x180016044`
- `0x1800160bc`
- `0x1800160e8`
- `0x180016140`
- `0x1800161c4`
- `0x180016340`
- `0x180016b40`
- `0x180016c60`
- `0x180016d68`
- `0x180016dec`
- `0x180017140`
- `0x180017a68`
- `0x180017b5c`

## string_xrefs

- `0x18001729c`: `SharingTokenDatabase::GetToken`

## pseudocode

```c
__int64 __fastcall SharingTokenDatabase::GetToken(SharingTokenDatabase *this, _QWORD *a2, _QWORD *a3)
{
  int SCBasedOnGuid; // ebx
  void **v7; // rax
  void **v8; // rax
  PVOID v9; // rbx
  DbTableIterator **v10; // rax
  int Iterator; // eax
  DbTableIterator *v12; // rbx
  SharedFileToken **v13; // rax
  int Next; // eax
  __int64 (__fastcall ***v15)(_QWORD, __int64); // rdx
  char *v16; // rax
  __int64 v17; // rcx
  int *v18; // rax
  __int64 v20; // [rsp+20h] [rbp-30h]
  PVOID P; // [rsp+30h] [rbp-20h] BYREF
  __int64 (__fastcall ***v22)(_QWORD, __int64); // [rsp+38h] [rbp-18h] BYREF
  PVOID v23; // [rsp+40h] [rbp-10h] BYREF
  PVOID v24; // [rsp+48h] [rbp-8h] BYREF
  int v25; // [rsp+88h] [rbp+38h] BYREF

  v24 = 0;
  v23 = 0;
  v22 = 0;
  P = 0;
  v25 = 0;
  SCBasedOnGuid = SharingTokenDatabase::Initialize(
                    this,
                    L"\\Data\\Users\\System\\AppData\\Local\\DataSharing\\Storage\\");
  if ( SCBasedOnGuid < 0 )
    goto LABEL_15;
  v7 = tlx::replace<_jetSeekCriteria,&void tlx::_delete<_jetSeekCriteria>(_jetSeekCriteria *)>(&P);
  SCBasedOnGuid = GetSCBasedOnGuid(a2, v7, &v25);
  if ( SCBasedOnGuid < 0 )
    goto LABEL_15;
  v8 = tlx::replace<DbTableAccess<SharingToken>,&void tlx::_delete<DbTableAccess<SharingToken>>(DbTableAccess<SharingToken> *)>(&v24);
  SCBasedOnGuid = Database::GetTableAccess<SharingToken>((__int64)this, v8);
  if ( SCBasedOnGuid < 0 )
    goto LABEL_15;
  v9 = v24;
  v10 = tlx::replace<DbObjectIterator<SharingTargetTableAdapter>,&void tlx::_delete<DbObjectIterator<SharingTargetTableAdapter>>(DbObjectIterator<SharingTargetTableAdapter> *)>((DbTableIterator **)&v23);
  Iterator = DbTableAccess<SharingToken>::GetIterator((__int64)v9, 1u, 0, (__int64)P, v25, v10);
  SCBasedOnGuid = Iterator;
  if ( Iterator == 1 )
    goto LABEL_5;
  if ( Iterator < 0 )
    goto LABEL_15;
  v12 = (DbTableIterator *)v23;
  v13 = (SharedFileToken **)tlx::replace<SharingToken,&void tlx::_delete<SharingToken>(SharingToken *)>(&v22);
  Next = DbObjectIterator<SharingToken>::GetNext(v12, v13);
  SCBasedOnGuid = Next;
  if ( Next == 1 )
    goto LABEL_5;
  if ( Next < 0 )
    goto LABEL_15;
  v15 = v22;
  v16 = *(char **)((char *)v22 + 12) - *a2;
  if ( !v16 )
    v16 = *(char **)((char *)v22 + 20) - a2[1];
  if ( v16 )
  {
LABEL_5:
    SCBasedOnGuid = -1055719418;
  }
  else
  {
    v22 = 0;
    if ( (unsigned __int8)tlx::smart_xxx<SharingToken *,void (*)(SharingToken *),&void tlx::_delete<SharingToken>(SharingToken *),0,utl::allocator<int>>::reset(
                            a3,
                            v15) )
    {
      SCBasedOnGuid = SharingTokenDatabase::GetShareScope((__int64)this, a3);
      if ( SCBasedOnGuid >= 0 )
        goto LABEL_16;
    }
    else
    {
      SCBasedOnGuid = -2147024882;
    }
  }
LABEL_15:
  tlx::smart_xxx<SharingToken *,void (*)(SharingToken *),&void tlx::_delete<SharingToken>(SharingToken *),0,utl::allocator<int>>::reset(a3);
  v18 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v17);
  LODWORD(v20) = SCBasedOnGuid;
  DSLogger::LogError((DSLogger *)v18, L"SharingTokenDatabase::GetToken", 0x15Bu, L"hr=0x%x.", v20);
  SharingTokenDatabase::CheckAndSetRecoveryState((RTL_SRWLOCK *)this, SCBasedOnGuid);
LABEL_16:
  ReleaseSC(P, &v25);
  if ( P )
    Common::GlobalHeap::Free(P);
  if ( v22 )
    tlx::_delete<DbEnumFilter>(v22);
  if ( v23 )
    tlx::_delete<DbObjectIterator<SharingToken>>((DbTableIterator *)v23);
  if ( v24 )
    tlx::_delete<DbTableAccess<SharingToken>>(v24);
  return (unsigned int)SCBasedOnGuid;
}

```

## disassembly

```asm
0x180017140  mov     [rsp-18h+arg_0], rbx
0x180017145  mov     [rsp-18h+arg_8], rsi
0x18001714a  push    rbp
0x18001714b  push    rdi
0x18001714c  push    r14
0x18001714e  mov     rbp, rsp
0x180017151  sub     rsp, 50h
0x180017155  mov     rsi, rdx
0x180017158  mov     [rbp+var_8], 0
0x180017160  lea     rdx, pszPathIn; "\\Data\\Users\\System\\AppData\\Local\\"...
0x180017167  mov     [rbp+var_10], 0
0x18001716f  mov     r14, r8
0x180017172  mov     [rbp+var_18], 0
0x18001717a  mov     rdi, rcx
0x18001717d  mov     [rbp+P], 0
0x180017185  mov     [rbp+arg_18], 0
0x18001718c  call    ?Initialize@SharingTokenDatabase@@QEAAJPEBG@Z; SharingTokenDatabase::Initialize(ushort const *)
0x180017191  mov     ebx, eax
0x180017193  test    eax, eax
0x180017195  js      loc_18001727E
0x18001719b  lea     rcx, [rbp+P]
0x18001719f  call    ??$replace@U_jetSeekCriteria@@$1??$_delete@U_jetSeekCriteria@@@tlx@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_jetSeekCriteria@@AEAV?$auto_ptr@U_jetSeekCriteria@@$1??$_delete@U_jetSeekCriteria@@@tlx@@YAXPEAU1@@Z@0@@Z; tlx::replace<_jetSeekCriteria,&tlx::_delete<_jetSeekCriteria>(_jetSeekCriteria *)>(tlx::auto_ptr<_jetSeekCriteria,&tlx::_delete<_jetSeekCriteria>(_jetSeekCriteria *)> &)
0x1800171a4  mov     rdx, rax
0x1800171a7  lea     r8, [rbp+arg_18]
0x1800171ab  mov     rcx, rsi
0x1800171ae  call    GetSCBasedOnGuid
0x1800171b3  mov     ebx, eax
0x1800171b5  test    eax, eax
0x1800171b7  js      loc_18001727E
0x1800171bd  lea     rcx, [rbp+var_8]
0x1800171c1  call    ??$replace@V?$DbTableAccess@VSharingToken@@@@$1??$_delete@V?$DbTableAccess@VSharingToken@@@@@tlx@@YAXPEAV1@@Z@tlx@@YAPEAPEAV?$DbTableAccess@VSharingToken@@@@AEAV?$auto_ptr@V?$DbTableAccess@VSharingToken@@@@$1??$_delete@V?$DbTableAccess@VSharingToken@@@@@tlx@@YAXPEAV1@@Z@0@@Z; tlx::replace<DbTableAccess<SharingToken>,&tlx::_delete<DbTableAccess<SharingToken>>(DbTableAccess<SharingToken> *)>(tlx::auto_ptr<DbTableAccess<SharingToken>,&tlx::_delete<DbTableAccess<SharingToken>>(DbTableAccess<SharingToken> *)> &)
0x1800171c6  mov     rdx, rax
0x1800171c9  mov     rcx, rdi
0x1800171cc  call    ??$GetTableAccess@VSharingToken@@@Database@@QEAAJPEAPEAV?$DbTableAccess@VSharingToken@@@@@Z; Database::GetTableAccess<SharingToken>(DbTableAccess<SharingToken> * *)
0x1800171d1  mov     ebx, eax
0x1800171d3  test    eax, eax
0x1800171d5  js      loc_18001727E
0x1800171db  mov     rbx, [rbp+var_8]
0x1800171df  lea     rcx, [rbp+var_10]
0x1800171e3  call    ??$replace@V?$DbObjectIterator@VSharingTargetTableAdapter@@@@$1??$_delete@V?$DbObjectIterator@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV1@@Z@tlx@@YAPEAPEAV?$DbObjectIterator@VSharingTargetTableAdapter@@@@AEAV?$auto_ptr@V?$DbObjectIterator@VSharingTargetTableAdapter@@@@$1??$_delete@V?$DbObjectIterator@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV1@@Z@0@@Z; tlx::replace<DbObjectIterator<SharingTargetTableAdapter>,&tlx::_delete<DbObjectIterator<SharingTargetTableAdapter>>(DbObjectIterator<SharingTargetTableAdapter> *)>(tlx::auto_ptr<DbObjectIterator<SharingTargetTableAdapter>,&tlx::_delete<DbObjectIterator<SharingTargetTableAdapter>>(DbObjectIterator<SharingTargetTableAdapter> *)> &)
0x1800171e8  mov     r9, [rbp+P]
0x1800171ec  xor     r8d, r8d
0x1800171ef  mov     [rsp+50h+var_28], rax
0x1800171f4  mov     rcx, rbx
0x1800171f7  mov     eax, [rbp+arg_18]
0x1800171fa  mov     dword ptr [rsp+50h+var_30], eax
0x1800171fe  lea     edx, [r8+1]
0x180017202  call    ?GetIterator@?$DbTableAccess@VSharingToken@@@@QEAAJKHPEAU_jetSeekCriteria@@KPEAPEAV?$DbObjectIterator@VSharingToken@@@@@Z; DbTableAccess<SharingToken>::GetIterator(ulong,int,_jetSeekCriteria *,ulong,DbObjectIterator<SharingToken> * *)
0x180017207  mov     ebx, eax
0x180017209  cmp     eax, 1
0x18001720c  jnz     short loc_180017215
0x18001720e  mov     ebx, 0C1130006h
0x180017213  jmp     short loc_18001727E
0x180017215  test    eax, eax
0x180017217  js      short loc_18001727E
0x180017219  mov     rbx, [rbp+var_10]
0x18001721d  lea     rcx, [rbp+var_18]
0x180017221  call    ??$replace@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@Z@tlx@@YAPEAPEAVSharingToken@@AEAV?$auto_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@Z@0@@Z; tlx::replace<SharingToken,&tlx::_delete<SharingToken>(SharingToken *)>(tlx::auto_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *)> &)
0x180017226  mov     rdx, rax
0x180017229  mov     rcx, rbx; this
0x18001722c  call    ?GetNext@?$DbObjectIterator@VSharingToken@@@@QEAAJPEAPEAVSharingToken@@@Z; DbObjectIterator<SharingToken>::GetNext(SharingToken * *)
0x180017231  mov     ebx, eax
0x180017233  cmp     eax, 1
0x180017236  jz      short loc_18001720E
0x180017238  test    eax, eax
0x18001723a  js      short loc_18001727E
0x18001723c  mov     rdx, [rbp+var_18]
0x180017240  mov     rax, [rdx+0Ch]
0x180017244  sub     rax, [rsi]
0x180017247  jnz     short loc_180017251
0x180017249  mov     rax, [rdx+14h]
0x18001724d  sub     rax, [rsi+8]
0x180017251  test    rax, rax
0x180017254  jnz     short loc_18001720E
0x180017256  mov     rcx, r14
0x180017259  mov     [rbp+var_18], rax
0x18001725d  call    ?reset@?$smart_xxx@PEAVSharingToken@@P6AXPEAV1@@Z$1??$_delete@VSharingToken@@@tlx@@YAX0@Z$0A@V?$allocator@H@utl@@@tlx@@QEAA_NPEAVSharingToken@@@Z; tlx::smart_xxx<SharingToken *,void (*)(SharingToken *),&tlx::_delete<SharingToken>(SharingToken *),0,utl::allocator<int>>::reset(SharingToken *)
0x180017262  test    al, al
0x180017264  jnz     short loc_18001726D
0x180017266  mov     ebx, 8007000Eh
0x18001726b  jmp     short loc_18001727E
0x18001726d  mov     rdx, r14
0x180017270  mov     rcx, rdi
0x180017273  call    ?GetShareScope@SharingTokenDatabase@@AEAAJAEAV?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@Z; SharingTokenDatabase::GetShareScope(tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>> &)
0x180017278  mov     ebx, eax
0x18001727a  test    eax, eax
0x18001727c  jns     short loc_1800172B5
0x18001727e  mov     rcx, r14
0x180017281  call    ?reset@?$smart_xxx@PEAVSharingToken@@P6AXPEAV1@@Z$1??$_delete@VSharingToken@@@tlx@@YAX0@Z$0A@V?$allocator@H@utl@@@tlx@@QEAAXXZ; tlx::smart_xxx<SharingToken *,void (*)(SharingToken *),&tlx::_delete<SharingToken>(SharingToken *),0,utl::allocator<int>>::reset(void)
0x180017286  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18001728b  lea     r9, aHr0xX; "hr=0x%x."
0x180017292  mov     dword ptr [rsp+50h+var_30], ebx
0x180017296  mov     r8d, 15Bh; unsigned int
0x18001729c  lea     rdx, aSharingtokenda_8; "SharingTokenDatabase::GetToken"
0x1800172a3  mov     rcx, rax; this
0x1800172a6  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800172ab  mov     edx, ebx; int
0x1800172ad  mov     rcx, rdi; this
0x1800172b0  call    ?CheckAndSetRecoveryState@SharingTokenDatabase@@AEAAXJ@Z; SharingTokenDatabase::CheckAndSetRecoveryState(long)
0x1800172b5  mov     rcx, [rbp+P]
0x1800172b9  lea     rdx, [rbp+arg_18]
0x1800172bd  call    ReleaseSC
0x1800172c2  mov     rcx, [rbp+P]; P
0x1800172c6  test    rcx, rcx
0x1800172c9  jz      short loc_1800172D0
0x1800172cb  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800172d0  mov     rcx, [rbp+var_18]
0x1800172d4  test    rcx, rcx
0x1800172d7  jz      short loc_1800172DE
0x1800172d9  call    ??$_delete@VDbEnumFilter@@@tlx@@YAXPEAVDbEnumFilter@@@Z; tlx::_delete<DbEnumFilter>(DbEnumFilter *)
0x1800172de  mov     rcx, [rbp+var_10]; P
0x1800172e2  test    rcx, rcx
0x1800172e5  jz      short loc_1800172EC
0x1800172e7  call    ??$_delete@V?$DbObjectIterator@VSharingToken@@@@@tlx@@YAXPEAV?$DbObjectIterator@VSharingToken@@@@@Z; tlx::_delete<DbObjectIterator<SharingToken>>(DbObjectIterator<SharingToken> *)
0x1800172ec  mov     rcx, [rbp+var_8]; P
0x1800172f0  test    rcx, rcx
0x1800172f3  jz      short loc_1800172FA
0x1800172f5  call    ??$_delete@V?$DbTableAccess@VSharingToken@@@@@tlx@@YAXPEAV?$DbTableAccess@VSharingToken@@@@@Z; tlx::_delete<DbTableAccess<SharingToken>>(DbTableAccess<SharingToken> *)
0x1800172fa  mov     rsi, [rsp+50h+arg_8]
0x1800172ff  mov     eax, ebx
0x180017301  mov     rbx, [rsp+50h+arg_0]
0x180017306  add     rsp, 50h
0x18001730a  pop     r14
0x18001730c  pop     rdi
0x18001730d  pop     rbp
0x18001730e  retn
```
