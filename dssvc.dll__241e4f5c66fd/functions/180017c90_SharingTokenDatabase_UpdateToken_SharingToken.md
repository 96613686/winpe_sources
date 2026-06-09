# SharingTokenDatabase::UpdateToken(SharingToken *)

- ea: `0x180017c90`
- end: `0x180017e51`
- name: `?UpdateToken@SharingTokenDatabase@@QEAAJPEAVSharingToken@@@Z`
- size: `449`
- prototype: `__int64 __fastcall(SharingTokenDatabase *__hidden this, struct SharingToken *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180012310`

## callees

- `0x180002bac`
- `0x180006f78`
- `0x18000bf80`
- `0x18000c758`
- `0x18000f120`
- `0x180015cfc`
- `0x180015f2c`
- `0x18001601c`
- `0x18001606c`
- `0x180016114`
- `0x18001616c`
- `0x180016340`
- `0x180016388`
- `0x1800165c0`
- `0x180017020`
- `0x180017a68`
- `0x180017ae0`
- `0x180017ba8`
- `0x180017c90`

## string_xrefs

- `0x180017dcb`: `SharingTokenDatabase::UpdateToken`

## pseudocode

```c
__int64 __fastcall SharingTokenDatabase::UpdateToken(RTL_SRWLOCK *this, struct SharingToken *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdx
  int TransactedTable; // edi
  void **v7; // rax
  int v8; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  PVOID v11; // rbx
  void **v12; // rax
  void **i; // rbx
  void **j; // rbx
  int *v15; // rax
  _QWORD *v16; // rbx
  _QWORD *v17; // rdx
  __int64 v18; // rax
  utl::_RefCountBase *v19; // rcx
  void *v21[4]; // [rsp+30h] [rbp-20h] BYREF
  PVOID v22; // [rsp+78h] [rbp+28h] BYREF
  PVOID P; // [rsp+80h] [rbp+30h] BYREF

  v22 = 0;
  P = 0;
  utl::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>(v21);
  if ( !v5 )
  {
    TransactedTable = -2147024809;
LABEL_19:
    v15 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v4);
    DSLogger::LogError((DSLogger *)v15, L"SharingTokenDatabase::UpdateToken", 482, L"hr=0x%x.", TransactedTable);
    SharingTokenDatabase::CheckAndSetRecoveryState(this, TransactedTable);
    goto LABEL_20;
  }
  TransactedTable = SharingTokenDatabase::Initialize(
                      (SharingTokenDatabase *)this,
                      L"\\Data\\Users\\System\\AppData\\Local\\DataSharing\\Storage\\");
  if ( TransactedTable < 0 )
    goto LABEL_19;
  v7 = tlx::replace<DbTransactedTableAccess<SharingToken>,&void tlx::_delete<DbTransactedTableAccess<SharingToken>>(DbTransactedTableAccess<SharingToken> *)>(&v22);
  TransactedTable = Database::GetTransactedTableAccess<SharingToken>((__int64)this, v7);
  if ( TransactedTable < 0 )
    goto LABEL_19;
  v8 = DbTableAccess<SharingToken>::Update(v22, a2, a2);
  TransactedTable = v8;
  if ( v8 == 1 )
  {
    TransactedTable = -1055719418;
    goto LABEL_19;
  }
  if ( v8 < 0 )
    goto LABEL_19;
  TransactedTable = GetSharingTargets(a2, (__int64)v21, v9, v10);
  if ( TransactedTable < 0 )
    goto LABEL_19;
  v11 = v22;
  v12 = tlx::replace<DbTableAccess<SharingTargetTableAdapter>,&void tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(DbTableAccess<SharingTargetTableAdapter> *)>(&P);
  TransactedTable = DbTableAccess<SharingToken>::GetDependentTableAccess<SharingTargetTableAdapter>((__int64)v11, v12);
  if ( TransactedTable < 0 )
    goto LABEL_19;
  for ( i = (void **)v21[0]; i != v21; i = (void **)*i )
  {
    TransactedTable = DbTableAccess<SharingTargetTableAdapter>::Delete((__int64)P, i[2]);
    if ( TransactedTable < 0 )
      goto LABEL_19;
  }
  for ( j = (void **)v21[0]; j != v21; j = (void **)*j )
  {
    TransactedTable = DbTableAccess<SharingTargetTableAdapter>::Insert((__int64)P, (__int64)j[2]);
    if ( TransactedTable < 0 )
      goto LABEL_19;
  }
  TransactedTable = DbTransactedTableAccess<SharingToken>::Commit((__int64)v22);
  if ( TransactedTable < 0 )
    goto LABEL_19;
LABEL_20:
  while ( 1 )
  {
    v16 = v21[0];
    if ( v21[0] == v21 )
      break;
    v17 = (_QWORD *)*((_QWORD *)v21[0] + 1);
    v18 = *(_QWORD *)v21[0];
    *v17 = *(_QWORD *)v21[0];
    *(_QWORD *)(v18 + 8) = v17;
    v19 = (utl::_RefCountBase *)v16[3];
    if ( v19 )
      utl::_RefCountBase::_DecStrong(v19);
    operator delete(v16, (const struct std::nothrow_t *)&std::nothrow);
  }
  v21[2] = 0;
  if ( P )
    tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(P);
  if ( v22 )
    tlx::_delete<DbTransactedTableAccess<SharingToken>>(v22);
  return (unsigned int)TransactedTable;
}

```

## disassembly

```asm
0x180017c90  mov     [rsp-18h+arg_0], rbx
0x180017c95  push    rbp
0x180017c96  push    rsi
0x180017c97  push    rdi
0x180017c98  mov     rbp, rsp
0x180017c9b  sub     rsp, 50h
0x180017c9f  mov     rsi, rcx
0x180017ca2  mov     [rbp+arg_8], 0
0x180017caa  lea     rcx, [rbp+var_20]
0x180017cae  mov     [rbp+P], 0
0x180017cb6  mov     rbx, rdx
0x180017cb9  call    ??0?$list@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAA@XZ; utl::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>(void)
0x180017cbe  test    rdx, rdx
0x180017cc1  jnz     short loc_180017CCD
0x180017cc3  mov     edi, 80070057h
0x180017cc8  jmp     loc_180017DB5
0x180017ccd  lea     rdx, pszPathIn; "\\Data\\Users\\System\\AppData\\Local\\"...
0x180017cd4  mov     rcx, rsi; this
0x180017cd7  call    ?Initialize@SharingTokenDatabase@@QEAAJPEBG@Z; SharingTokenDatabase::Initialize(ushort const *)
0x180017cdc  mov     edi, eax
0x180017cde  test    eax, eax
0x180017ce0  js      loc_180017DB5
0x180017ce6  lea     rcx, [rbp+arg_8]
0x180017cea  call    ??$replace@V?$DbTransactedTableAccess@VSharingToken@@@@$1??$_delete@V?$DbTransactedTableAccess@VSharingToken@@@@@tlx@@YAXPEAV1@@Z@tlx@@YAPEAPEAV?$DbTransactedTableAccess@VSharingToken@@@@AEAV?$auto_ptr@V?$DbTransactedTableAccess@VSharingToken@@@@$1??$_delete@V?$DbTransactedTableAccess@VSharingToken@@@@@tlx@@YAXPEAV1@@Z@0@@Z; tlx::replace<DbTransactedTableAccess<SharingToken>,&tlx::_delete<DbTransactedTableAccess<SharingToken>>(DbTransactedTableAccess<SharingToken> *)>(tlx::auto_ptr<DbTransactedTableAccess<SharingToken>,&tlx::_delete<DbTransactedTableAccess<SharingToken>>(DbTransactedTableAccess<SharingToken> *)> &)
0x180017cef  mov     rdx, rax
0x180017cf2  mov     rcx, rsi
0x180017cf5  call    ??$GetTransactedTableAccess@VSharingToken@@@Database@@QEAAJPEAPEAV?$DbTransactedTableAccess@VSharingToken@@@@@Z; Database::GetTransactedTableAccess<SharingToken>(DbTransactedTableAccess<SharingToken> * *)
0x180017cfa  mov     edi, eax
0x180017cfc  test    eax, eax
0x180017cfe  js      loc_180017DB5
0x180017d04  mov     rcx, [rbp+arg_8]
0x180017d08  mov     r8, rbx
0x180017d0b  mov     rdx, rbx
0x180017d0e  call    ?Update@?$DbTableAccess@VSharingToken@@@@QEAAJPEAVSharingToken@@0@Z; DbTableAccess<SharingToken>::Update(SharingToken *,SharingToken *)
0x180017d13  mov     edi, eax
0x180017d15  cmp     eax, 1
0x180017d18  jnz     short loc_180017D24
0x180017d1a  mov     edi, 0C1130006h
0x180017d1f  jmp     loc_180017DB5
0x180017d24  test    eax, eax
0x180017d26  js      loc_180017DB5
0x180017d2c  lea     rdx, [rbp+var_20]
0x180017d30  mov     rcx, rbx
0x180017d33  call    GetSharingTargets
0x180017d38  mov     edi, eax
0x180017d3a  test    eax, eax
0x180017d3c  js      short loc_180017DB5
0x180017d3e  mov     rbx, [rbp+arg_8]
0x180017d42  lea     rcx, [rbp+P]
0x180017d46  call    ??$replace@V?$DbTableAccess@VSharingTargetTableAdapter@@@@$1??$_delete@V?$DbTableAccess@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV1@@Z@tlx@@YAPEAPEAV?$DbTableAccess@VSharingTargetTableAdapter@@@@AEAV?$auto_ptr@V?$DbTableAccess@VSharingTargetTableAdapter@@@@$1??$_delete@V?$DbTableAccess@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV1@@Z@0@@Z; tlx::replace<DbTableAccess<SharingTargetTableAdapter>,&tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(DbTableAccess<SharingTargetTableAdapter> *)>(tlx::auto_ptr<DbTableAccess<SharingTargetTableAdapter>,&tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(DbTableAccess<SharingTargetTableAdapter> *)> &)
0x180017d4b  mov     rdx, rax
0x180017d4e  mov     rcx, rbx
0x180017d51  call    ??$GetDependentTableAccess@VSharingTargetTableAdapter@@@?$DbTableAccess@VSharingToken@@@@QEAAJPEAPEAV?$DbTableAccess@VSharingTargetTableAdapter@@@@@Z; DbTableAccess<SharingToken>::GetDependentTableAccess<SharingTargetTableAdapter>(DbTableAccess<SharingTargetTableAdapter> * *)
0x180017d56  mov     edi, eax
0x180017d58  test    eax, eax
0x180017d5a  js      short loc_180017DB5
0x180017d5c  mov     rbx, [rbp+var_20]
0x180017d60  lea     rax, [rbp+var_20]
0x180017d64  cmp     rbx, rax
0x180017d67  jz      short loc_180017D81
0x180017d69  mov     rdx, [rbx+10h]
0x180017d6d  mov     rcx, [rbp+P]
0x180017d71  call    ?Delete@?$DbTableAccess@VSharingTargetTableAdapter@@@@QEAAJPEAVSharingTargetTableAdapter@@@Z; DbTableAccess<SharingTargetTableAdapter>::Delete(SharingTargetTableAdapter *)
0x180017d76  mov     edi, eax
0x180017d78  test    eax, eax
0x180017d7a  js      short loc_180017DB5
0x180017d7c  mov     rbx, [rbx]
0x180017d7f  jmp     short loc_180017D60
0x180017d81  mov     rbx, [rbp+var_20]
0x180017d85  lea     rax, [rbp+var_20]
0x180017d89  cmp     rbx, rax
0x180017d8c  jz      short loc_180017DA6
0x180017d8e  mov     rdx, [rbx+10h]
0x180017d92  mov     rcx, [rbp+P]
0x180017d96  call    ?Insert@?$DbTableAccess@VSharingTargetTableAdapter@@@@QEAAJPEAVSharingTargetTableAdapter@@@Z; DbTableAccess<SharingTargetTableAdapter>::Insert(SharingTargetTableAdapter *)
0x180017d9b  mov     edi, eax
0x180017d9d  test    eax, eax
0x180017d9f  js      short loc_180017DB5
0x180017da1  mov     rbx, [rbx]
0x180017da4  jmp     short loc_180017D85
0x180017da6  mov     rcx, [rbp+arg_8]
0x180017daa  call    ?Commit@?$DbTransactedTableAccess@VSharingToken@@@@QEAAJXZ; DbTransactedTableAccess<SharingToken>::Commit(void)
0x180017daf  mov     edi, eax
0x180017db1  test    eax, eax
0x180017db3  jns     short loc_180017DE4
0x180017db5  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180017dba  lea     r9, aHr0xX; "hr=0x%x."
0x180017dc1  mov     [rsp+50h+var_30], edi
0x180017dc5  mov     r8d, 1E2h; unsigned int
0x180017dcb  lea     rdx, aSharingtokenda; "SharingTokenDatabase::UpdateToken"
0x180017dd2  mov     rcx, rax; this
0x180017dd5  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180017dda  mov     edx, edi; int
0x180017ddc  mov     rcx, rsi; this
0x180017ddf  call    ?CheckAndSetRecoveryState@SharingTokenDatabase@@AEAAXJ@Z; SharingTokenDatabase::CheckAndSetRecoveryState(long)
0x180017de4  mov     rbx, [rbp+var_20]
0x180017de8  lea     rax, [rbp+var_20]
0x180017dec  cmp     rbx, rax
0x180017def  jz      short loc_180017E1E
0x180017df1  mov     rdx, [rbx+8]
0x180017df5  mov     rax, [rbx]
0x180017df8  mov     [rdx], rax
0x180017dfb  mov     [rax+8], rdx
0x180017dff  mov     rcx, [rbx+18h]; this
0x180017e03  test    rcx, rcx
0x180017e06  jz      short loc_180017E0D
0x180017e08  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180017e0d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017e14  mov     rcx, rbx; void *
0x180017e17  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017e1c  jmp     short loc_180017DE4
0x180017e1e  mov     rcx, [rbp+P]; P
0x180017e22  mov     [rbp+var_10], 0
0x180017e2a  test    rcx, rcx
0x180017e2d  jz      short loc_180017E34
0x180017e2f  call    ??$_delete@V?$DbTableAccess@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV?$DbTableAccess@VSharingTargetTableAdapter@@@@@Z; tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(DbTableAccess<SharingTargetTableAdapter> *)
0x180017e34  mov     rcx, [rbp+arg_8]; P
0x180017e38  test    rcx, rcx
0x180017e3b  jz      short loc_180017E42
0x180017e3d  call    ??$_delete@V?$DbTransactedTableAccess@VSharingToken@@@@@tlx@@YAXPEAV?$DbTransactedTableAccess@VSharingToken@@@@@Z; tlx::_delete<DbTransactedTableAccess<SharingToken>>(DbTransactedTableAccess<SharingToken> *)
0x180017e42  mov     rbx, [rsp+50h+arg_0]
0x180017e47  mov     eax, edi
0x180017e49  add     rsp, 50h
0x180017e4d  pop     rdi
0x180017e4e  pop     rsi
0x180017e4f  pop     rbp
0x180017e50  retn
```
