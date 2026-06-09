# DbTable::Update(_jetSeekCriteria *,ulong,JET_SETCOLUMN *,int,int,int)

- ea: `0x180015468`
- end: `0x180015738`
- name: `?Update@DbTable@@QEAAJPEAU_jetSeekCriteria@@KPEAUJET_SETCOLUMN@@HHH@Z`
- size: `720`
- prototype: `__int64 __fastcall(DbTable *__hidden this, struct _jetSeekCriteria *, unsigned int, struct JET_SETCOLUMN *, unsigned int csetcolumn, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180015468`
- `0x180017ba8`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x1800114e4`
- `0x18001526c`
- `0x180015468`

## import_xrefs

- `ESENT!JetUpdate` at `0x180015624`
- `ESENT!JetUpdate` at `0x180015624`
- `ESENT!JetCommitTransaction` at `0x1800156dd`
- `ESENT!JetCommitTransaction` at `0x1800156dd`
- `ESENT!JetRollback` at `0x1800154aa`
- `ESENT!JetRollback` at `0x18001563e`
- `ESENT!JetRollback` at `0x1800154aa`
- `ESENT!JetRollback` at `0x18001563e`
- `ESENT!JetBeginTransaction` at `0x18001550f`
- `ESENT!JetBeginTransaction` at `0x18001550f`
- `ESENT!JetSetColumns` at `0x1800155cc`
- `ESENT!JetSetColumns` at `0x1800155cc`
- `ESENT!JetPrepareUpdate` at `0x1800154c3`
- `ESENT!JetPrepareUpdate` at `0x180015574`
- `ESENT!JetPrepareUpdate` at `0x180015655`
- `ESENT!JetPrepareUpdate` at `0x1800154c3`
- `ESENT!JetPrepareUpdate` at `0x180015574`
- `ESENT!JetPrepareUpdate` at `0x180015655`

## string_xrefs

- `0x180015533`: `DbTable::Update`
- `0x180015598`: `DbTable::Update`
- `0x1800155f0`: `DbTable::Update`
- `0x1800156b2`: `DbTable::Update`
- `0x180015701`: `DbTable::Update`

## pseudocode

```c
__int64 __fastcall DbTable::Update(
        JET_SESID *this,
        struct _jetSeekCriteria *a2,
        unsigned int a3,
        struct JET_SETCOLUMN *a4,
        unsigned int csetcolumn,
        int a6,
        int a7)
{
  int v7; // ebp
  int v8; // r13d
  int v12; // edi
  int v13; // ebx
  int v15; // eax
  __int64 v16; // rcx
  JET_ERR v17; // r14d
  int *v18; // rax
  __int64 v19; // rcx
  JET_ERR v20; // r14d
  int *v21; // rax
  __int64 v22; // rcx
  JET_ERR v23; // r14d
  int *v24; // rax
  __int64 v25; // rcx
  JET_ERR v26; // r14d
  int *v27; // rax
  __int64 v28; // rcx
  JET_ERR v29; // r14d
  int *v30; // rax
  unsigned int *pcbActual; // [rsp+20h] [rbp-68h]
  unsigned int *pcbActuala; // [rsp+20h] [rbp-68h]

  v7 = 0;
  v8 = 0;
  if ( !a2 || !a4 )
  {
    v12 = -2147024809;
LABEL_3:
    v13 = a6;
    goto LABEL_4;
  }
  v15 = DbTable::Seek((DbTable *)this, a2, a3, 0, 1u);
  v12 = v15;
  if ( v15 < 0 )
    goto LABEL_3;
  if ( v15 == 1 )
  {
    v7 = 1;
    v13 = a6;
    goto LABEL_32;
  }
  v13 = a6;
  if ( !a6
    || (v17 = JetBeginTransaction(this[5]), v17 >= 0)
    || (v18 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v16),
        LODWORD(pcbActual) = v17,
        DSLogger::LogError((DSLogger *)v18, L"DbTable::Update", 557, L"JET_ERR : %d", pcbActual),
        v12 = JetToHResult(v17),
        v12 >= 0) )
  {
    v8 = 1;
    v20 = JetPrepareUpdate(this[5], this[9], a7 != 0 ? 7 : 2);
    if ( v20 >= 0
      || (v21 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v19),
          LODWORD(pcbActual) = v20,
          DSLogger::LogError((DSLogger *)v21, L"DbTable::Update", 564, L"JET_ERR : %d", pcbActual),
          v12 = JetToHResult(v20),
          v12 >= 0) )
    {
      v23 = JetSetColumns(this[5], this[9], a4, csetcolumn);
      if ( v23 >= 0
        || (v24 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v22),
            LODWORD(pcbActual) = v23,
            DSLogger::LogError((DSLogger *)v24, L"DbTable::Update", 567, L"JET_ERR : %d", pcbActual),
            v12 = JetToHResult(v23),
            v12 >= 0) )
      {
        v26 = JetUpdate(this[5], this[9], 0, 0, 0);
        if ( v26 == -1604 )
        {
          if ( a6 )
          {
            JetRollback(this[5], 0);
            v7 = 1;
          }
          JetPrepareUpdate(this[5], this[9], 3u);
          v12 = DbTable::Update((DbTable *)this, a2, a3, a4, csetcolumn, a6, 1);
          if ( v12 >= 0 )
          {
            v13 = 0;
LABEL_32:
            v8 = 0;
          }
        }
        else if ( v26 >= 0
               || (v27 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v25),
                   LODWORD(pcbActuala) = v26,
                   DSLogger::LogError((DSLogger *)v27, L"DbTable::Update", 597, L"JET_ERR : %d", pcbActuala),
                   v12 = JetToHResult(v26),
                   v12 >= 0) )
        {
          if ( a6 )
          {
            v29 = JetCommitTransaction(this[5], 0);
            if ( v29 < 0 )
            {
              v30 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v28);
              LODWORD(pcbActuala) = v29;
              DSLogger::LogError((DSLogger *)v30, L"DbTable::Update", 601, L"JET_ERR : %d", pcbActuala);
              v12 = JetToHResult(v29);
              if ( v12 < 0 )
                goto LABEL_5;
            }
            v7 = 1;
          }
          goto LABEL_32;
        }
      }
    }
LABEL_4:
    if ( !v13 )
      goto LABEL_7;
LABEL_5:
    if ( v7 )
      goto LABEL_7;
  }
  JetRollback(this[5], 0);
LABEL_7:
  if ( v8 )
    JetPrepareUpdate(this[5], this[9], 3u);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180015468  mov     [rsp+arg_10], r8d
0x18001546d  push    rbx
0x18001546e  push    rbp
0x18001546f  push    rsi
0x180015470  push    rdi
0x180015471  push    r12
0x180015473  push    r13
0x180015475  push    r14
0x180015477  push    r15
0x180015479  sub     rsp, 48h
0x18001547d  xor     ebp, ebp
0x18001547f  xor     r13d, r13d
0x180015482  mov     r12, r9
0x180015485  mov     r15, rdx
0x180015488  mov     rsi, rcx
0x18001548b  test    rdx, rdx
0x18001548e  jnz     short loc_1800154DC
0x180015490  mov     edi, 80070057h
0x180015495  mov     ebx, [rsp+88h+arg_28]
0x18001549c  test    ebx, ebx
0x18001549e  jz      short loc_1800154B0
0x1800154a0  test    ebp, ebp
0x1800154a2  jnz     short loc_1800154B0
0x1800154a4  mov     rcx, [rsi+28h]; sesid
0x1800154a8  xor     edx, edx; grbit
0x1800154aa  call    cs:__imp_JetRollback
0x1800154b0  test    r13d, r13d
0x1800154b3  jz      short loc_1800154C9
0x1800154b5  mov     rdx, [rsi+48h]; tableid
0x1800154b9  mov     r8d, 3; prep
0x1800154bf  mov     rcx, [rsi+28h]; sesid
0x1800154c3  call    cs:__imp_JetPrepareUpdate
0x1800154c9  mov     eax, edi
0x1800154cb  add     rsp, 48h
0x1800154cf  pop     r15
0x1800154d1  pop     r14
0x1800154d3  pop     r13
0x1800154d5  pop     r12
0x1800154d7  pop     rdi
0x1800154d8  pop     rsi
0x1800154d9  pop     rbp
0x1800154da  pop     rbx
0x1800154db  retn
0x1800154dc  test    r12, r12
0x1800154df  jz      short loc_180015490
0x1800154e1  mov     ebx, 1
0x1800154e6  xor     r9d, r9d; int
0x1800154e9  mov     dword ptr [rsp+88h+pcbActual], ebx; unsigned int
0x1800154ed  call    ?Seek@DbTable@@AEAAJPEAU_jetSeekCriteria@@KHK@Z; DbTable::Seek(_jetSeekCriteria *,ulong,int,ulong)
0x1800154f2  mov     edi, eax
0x1800154f4  test    eax, eax
0x1800154f6  js      short loc_180015495
0x1800154f8  cmp     eax, ebx
0x1800154fa  jz      loc_180015727
0x180015500  mov     ebx, [rsp+88h+arg_28]
0x180015507  test    ebx, ebx
0x180015509  jz      short loc_180015554
0x18001550b  mov     rcx, [rsi+28h]; sesid
0x18001550f  call    cs:__imp_JetBeginTransaction
0x180015515  mov     r14d, eax
0x180015518  test    eax, eax
0x18001551a  jns     short loc_180015554
0x18001551c  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180015521  lea     r9, aJetErrD; "JET_ERR : %d"
0x180015528  mov     dword ptr [rsp+88h+pcbActual], r14d
0x18001552d  mov     r8d, 22Dh; unsigned int
0x180015533  lea     rdx, aDbtableUpdate; "DbTable::Update"
0x18001553a  mov     rcx, rax; this
0x18001553d  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180015542  mov     ecx, r14d; int
0x180015545  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x18001554a  mov     edi, eax
0x18001554c  test    eax, eax
0x18001554e  js      loc_1800154A4
0x180015554  neg     [rsp+88h+arg_30]
0x18001555b  mov     r13d, 1
0x180015561  mov     rdx, [rsi+48h]; tableid
0x180015565  mov     rcx, [rsi+28h]; sesid
0x180015569  sbb     r8d, r8d
0x18001556c  and     r8d, 5
0x180015570  add     r8d, 2; prep
0x180015574  call    cs:__imp_JetPrepareUpdate
0x18001557a  mov     r14d, eax
0x18001557d  test    eax, eax
0x18001557f  jns     short loc_1800155B9
0x180015581  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180015586  lea     r9, aJetErrD; "JET_ERR : %d"
0x18001558d  mov     dword ptr [rsp+88h+pcbActual], r14d
0x180015592  mov     r8d, 234h; unsigned int
0x180015598  lea     rdx, aDbtableUpdate; "DbTable::Update"
0x18001559f  mov     rcx, rax; this
0x1800155a2  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800155a7  mov     ecx, r14d; int
0x1800155aa  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x1800155af  mov     edi, eax
0x1800155b1  test    eax, eax
0x1800155b3  js      loc_18001549C
0x1800155b9  mov     r9d, [rsp+88h+csetcolumn]; csetcolumn
0x1800155c1  mov     r8, r12; psetcolumn
0x1800155c4  mov     rdx, [rsi+48h]; tableid
0x1800155c8  mov     rcx, [rsi+28h]; sesid
0x1800155cc  call    cs:__imp_JetSetColumns
0x1800155d2  mov     r14d, eax
0x1800155d5  test    eax, eax
0x1800155d7  jns     short loc_180015611
0x1800155d9  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800155de  lea     r9, aJetErrD; "JET_ERR : %d"
0x1800155e5  mov     dword ptr [rsp+88h+pcbActual], r14d
0x1800155ea  mov     r8d, 237h; unsigned int
0x1800155f0  lea     rdx, aDbtableUpdate; "DbTable::Update"
0x1800155f7  mov     rcx, rax; this
0x1800155fa  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800155ff  mov     ecx, r14d; int
0x180015602  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x180015607  mov     edi, eax
0x180015609  test    eax, eax
0x18001560b  js      loc_18001549C
0x180015611  mov     rdx, [rsi+48h]; tableid
0x180015615  xor     r9d, r9d; cbBookmark
0x180015618  mov     rcx, [rsi+28h]; sesid
0x18001561c  xor     r8d, r8d; pvBookmark
0x18001561f  mov     [rsp+88h+pcbActual], rbp; pcbActual
0x180015624  call    cs:__imp_JetUpdate
0x18001562a  mov     r14d, eax
0x18001562d  cmp     eax, 0FFFFF9BCh
0x180015632  jnz     short loc_180015696
0x180015634  test    ebx, ebx
0x180015636  jz      short loc_180015647
0x180015638  mov     rcx, [rsi+28h]; sesid
0x18001563c  xor     edx, edx; grbit
0x18001563e  call    cs:__imp_JetRollback
0x180015644  mov     ebp, r13d
0x180015647  mov     rdx, [rsi+48h]; tableid
0x18001564b  mov     r8d, 3; prep
0x180015651  mov     rcx, [rsi+28h]; sesid
0x180015655  call    cs:__imp_JetPrepareUpdate
0x18001565b  mov     eax, [rsp+88h+csetcolumn]
0x180015662  mov     r9, r12; struct JET_SETCOLUMN *
0x180015665  mov     r8d, [rsp+88h+arg_10]; unsigned int
0x18001566d  mov     rdx, r15; struct _jetSeekCriteria *
0x180015670  mov     [rsp+88h+var_58], r13d; int
0x180015675  mov     rcx, rsi; this
0x180015678  mov     [rsp+88h+var_60], ebx; int
0x18001567c  mov     dword ptr [rsp+88h+pcbActual], eax; csetcolumn
0x180015680  call    ?Update@DbTable@@QEAAJPEAU_jetSeekCriteria@@KPEAUJET_SETCOLUMN@@HHH@Z; DbTable::Update(_jetSeekCriteria *,ulong,JET_SETCOLUMN *,int,int,int)
0x180015685  mov     edi, eax
0x180015687  test    eax, eax
0x180015689  js      loc_18001549C
0x18001568f  xor     ebx, ebx
0x180015691  jmp     loc_180015730
0x180015696  test    r14d, r14d
0x180015699  jns     short loc_1800156D3
0x18001569b  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800156a0  lea     r9, aJetErrD; "JET_ERR : %d"
0x1800156a7  mov     dword ptr [rsp+88h+pcbActual], r14d
0x1800156ac  mov     r8d, 255h; unsigned int
0x1800156b2  lea     rdx, aDbtableUpdate; "DbTable::Update"
0x1800156b9  mov     rcx, rax; this
0x1800156bc  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800156c1  mov     ecx, r14d; int
0x1800156c4  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x1800156c9  mov     edi, eax
0x1800156cb  test    eax, eax
0x1800156cd  js      loc_18001549C
0x1800156d3  test    ebx, ebx
0x1800156d5  jz      short loc_180015730
0x1800156d7  mov     rcx, [rsi+28h]; sesid
0x1800156db  xor     edx, edx; grbit
0x1800156dd  call    cs:__imp_JetCommitTransaction
0x1800156e3  mov     r14d, eax
0x1800156e6  test    eax, eax
0x1800156e8  jns     short loc_180015722
0x1800156ea  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800156ef  lea     r9, aJetErrD; "JET_ERR : %d"
0x1800156f6  mov     dword ptr [rsp+88h+pcbActual], r14d
0x1800156fb  mov     r8d, 259h; unsigned int
0x180015701  lea     rdx, aDbtableUpdate; "DbTable::Update"
0x180015708  mov     rcx, rax; this
0x18001570b  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180015710  mov     ecx, r14d; int
0x180015713  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x180015718  mov     edi, eax
0x18001571a  test    eax, eax
0x18001571c  js      loc_1800154A0
0x180015722  mov     ebp, r13d
0x180015725  jmp     short loc_180015730
0x180015727  mov     ebp, ebx
0x180015729  mov     ebx, [rsp+88h+arg_28]
0x180015730  xor     r13d, r13d
0x180015733  jmp     loc_18001549C
```
