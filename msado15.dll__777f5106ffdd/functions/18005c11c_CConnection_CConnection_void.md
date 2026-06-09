# CConnection::~CConnection(void)

- ea: `0x18005c11c`
- end: `0x18005c36b`
- name: `??1CConnection@@UEAA@XZ`
- size: `591`
- prototype: `void __fastcall(CConnection *__hidden this)`
- caller_count: `3`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005b668`
- `0x180065728`
- `0x1800c4a9c`

## callees

- `0x180001a30`
- `0x1800196c0`
- `0x18004f2e8`
- `0x180057b64`
- `0x18005a314`
- `0x18005c11c`
- `0x18005c374`
- `0x18005c398`
- `0x18005c3d4`
- `0x18005c420`
- `0x1800d0010`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18005c247`
- `MSDART!MPDeleteCriticalSection` at `0x18005c261`
- `MSDART!MPDeleteCriticalSection` at `0x18005c247`
- `MSDART!MPDeleteCriticalSection` at `0x18005c261`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CConnection::~CConnection(CConnection *this)
{
  char *v2; // r15
  CObjectWithSiteAndSecurity *v3; // rdi
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx

  *(_QWORD *)this = &CConnection::`vftable'{for `ADOIDispatchImpl<_ADOConnection>'};
  *((_QWORD *)this + 1) = &CConnection::`vftable'{for `ADOIDispatchImpl<ADOConnectionEx>'};
  *((_QWORD *)this + 2) = &CConnection::`vftable'{for `ADOIDispatchImpl<ADOConnectionConstruction>'};
  *((_QWORD *)this + 3) = &CConnection::`vftable'{for `ISupportErrorInfoImpl4<&_GUID const IID_IADOConnection,&_GUID const IID_IADOConnection15,&_GUID const IID_IADOConnection_Deprecated,&_GUID const IID_IADOConnection15_Deprecated>'};
  *((_QWORD *)this + 4) = &CConnection::`vftable'{for `CStdComObjectRoot'};
  *((_QWORD *)this + 11) = &CConnection::`vftable'{for `ATL::IConnectionPointContainerImpl<CConnection>'};
  *((_QWORD *)this + 12) = &CConnection::`vftable'{for `CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>'};
  v2 = (char *)this + 144;
  *((_QWORD *)this + 18) = &CConnection::`vftable'{for `CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents_Deprecated,&_GUID const IID_IADOConnectionEventsVt_Deprecated>'};
  *((_QWORD *)this + 24) = &CConnection::`vftable'{for `ADODebugging'};
  *((_QWORD *)this + 25) = &CConnection::`vftable'{for `IObjectSafety'};
  v3 = (CConnection *)((char *)this + 208);
  *((_QWORD *)this + 26) = &CStream::`vftable'{for `IObjectWithSite'};
  *((_QWORD *)this + 27) = &CStream::`vftable'{for `IADOSecurity'};
  *((_QWORD *)this + 31) = &CConnection::`vftable'{for `IADOClass'};
  v4 = *((_QWORD *)this + 121);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *((_QWORD *)this + 123);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v6 = *((_QWORD *)this + 126);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = *((_QWORD *)this + 124);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  *((_QWORD *)this + 152) = &CSemExclusive::`vftable';
  MPDeleteCriticalSection((char *)this + 1224);
  *((_QWORD *)this + 149) = &CSemExclusive::`vftable';
  MPDeleteCriticalSection((char *)this + 1200);
  CConnectionInfo::~CConnectionInfo((CConnection *)((char *)this + 1080));
  CADOStackComObject<CErrors>::~CADOStackComObject<CErrors>((char *)this + 856);
  CADOStackComObject<CStdActiveLockableCollection>::~CADOStackComObject<CStdActiveLockableCollection>((char *)this + 768);
  CADOStackComObject<CStdActiveLockableCollection>::~CADOStackComObject<CStdActiveLockableCollection>((char *)this + 680);
  CCollectionList::~CCollectionList((CConnection *)((char *)this + 632));
  CADOStackComObject<CStdActiveLockableCollection>::~CADOStackComObject<CStdActiveLockableCollection>((char *)this + 544);
  CADOStackComObject<CConnProperties>::~CADOStackComObject<CConnProperties>((char *)this + 416);
  CConnectionInfo::~CConnectionInfo((CConnection *)((char *)this + 304));
  *((_QWORD *)this + 32) = &CConnection::CNotUpdt_BidGeneric::`vftable';
  if ( *((_DWORD *)this + 66) && bidID != -1 )
    ((void (__fastcall *)(__int64, wchar_t *, __int64, _QWORD, _QWORD))off_180121278)(
      bidID,
      `CConnection::CNotUpdt_BidGeneric::BidRecycleID'::`7'::_bidPtrSA_053_625[0],
      7,
      *((int *)this + 66),
      0);
  *((_DWORD *)this + 66) = 0;
  *(_QWORD *)v3 = &CStream::`vftable'{for `IObjectWithSite'};
  *((_QWORD *)v3 + 1) = &CStream::`vftable'{for `IADOSecurity'};
  CObjectWithSiteAndSecurity::ReleaseTheSite(v3);
  ATL::IConnectionPointImpl<CRecordset,&_GUID const IID_DataSourceListener,CADOComDynamicUnkArray>::~IConnectionPointImpl<CRecordset,&_GUID const IID_DataSourceListener,CADOComDynamicUnkArray>(v2);
  ATL::IConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,CADOComDynamicUnkArray>::~IConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,CADOComDynamicUnkArray>((char *)this + 96);
  CStdComObjectRoot::~CStdComObjectRoot((CConnection *)((char *)this + 32));
}

```

## disassembly

```asm
0x18005c11c  push    rbx
0x18005c11e  push    rbp
0x18005c11f  push    rsi
0x18005c120  push    rdi
0x18005c121  push    r14
0x18005c123  push    r15
0x18005c125  sub     rsp, 38h
0x18005c129  mov     rbx, rcx
0x18005c12c  lea     rax, ??_7CConnection@@6B?$ADOIDispatchImpl@U_ADOConnection@@@@@; const CConnection::`vftable'{for `ADOIDispatchImpl<_ADOConnection>'}
0x18005c133  mov     [rcx], rax
0x18005c136  lea     rax, ??_7CConnection@@6B?$ADOIDispatchImpl@UADOConnectionEx@@@@@; const CConnection::`vftable'{for `ADOIDispatchImpl<ADOConnectionEx>'}
0x18005c13d  mov     [rcx+8], rax
0x18005c141  lea     rax, ??_7CConnection@@6B?$ADOIDispatchImpl@UADOConnectionConstruction@@@@@; const CConnection::`vftable'{for `ADOIDispatchImpl<ADOConnectionConstruction>'}
0x18005c148  mov     [rcx+10h], rax
0x18005c14c  lea     rax, ??_7CConnection@@6B?$ISupportErrorInfoImpl4@$1?IID_IADOConnection@@3U_GUID@@B$1?IID_IADOConnection15@@3U2@B$1?IID_IADOConnection_Deprecated@@3U2@B$1?IID_IADOConnection15_Deprecated@@3U2@B@@@; const CConnection::`vftable'{for `ISupportErrorInfoImpl4<&_GUID const IID_IADOConnection,&_GUID const IID_IADOConnection15,&_GUID const IID_IADOConnection_Deprecated,&_GUID const IID_IADOConnection15_Deprecated>'}
0x18005c153  mov     [rcx+18h], rax
0x18005c157  lea     rax, ??_7CConnection@@6BCStdComObjectRoot@@@; const CConnection::`vftable'{for `CStdComObjectRoot'}
0x18005c15e  mov     [rcx+20h], rax
0x18005c162  lea     rax, ??_7CConnection@@6B?$IConnectionPointContainerImpl@VCConnection@@@ATL@@@; const CConnection::`vftable'{for `ATL::IConnectionPointContainerImpl<CConnection>'}
0x18005c169  mov     [rcx+58h], rax
0x18005c16d  lea     rax, ??_7CConnection@@6B?$CADOConnectionPointImpl@VCConnection@@$1?IID_IADOConnectionEvents@@3U_GUID@@B$1?IID_IADOConnectionEventsVt@@3U3@B@@@; const CConnection::`vftable'{for `CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>'}
0x18005c174  mov     [rcx+60h], rax
0x18005c178  lea     r15, [rcx+90h]
0x18005c17f  lea     rax, ??_7CConnection@@6B?$CADOConnectionPointImpl@VCConnection@@$1?IID_IADOConnectionEvents_Deprecated@@3U_GUID@@B$1?IID_IADOConnectionEventsVt_Deprecated@@3U3@B@@@; const CConnection::`vftable'{for `CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents_Deprecated,&_GUID const IID_IADOConnectionEventsVt_Deprecated>'}
0x18005c186  mov     [r15], rax
0x18005c189  lea     rax, ??_7CConnection@@6BADODebugging@@@; const CConnection::`vftable'{for `ADODebugging'}
0x18005c190  mov     [rcx+0C0h], rax
0x18005c197  lea     rax, ??_7CConnection@@6BIObjectSafety@@@; const CConnection::`vftable'{for `IObjectSafety'}
0x18005c19e  mov     [rcx+0C8h], rax
0x18005c1a5  lea     rdi, [rcx+0D0h]
0x18005c1ac  lea     rax, ??_7CStream@@6BIObjectWithSite@@@; const CStream::`vftable'{for `IObjectWithSite'}
0x18005c1b3  mov     [rdi], rax
0x18005c1b6  lea     rax, ??_7CStream@@6BIADOSecurity@@@; const CStream::`vftable'{for `IADOSecurity'}
0x18005c1bd  mov     [rcx+0D8h], rax
0x18005c1c4  lea     rax, ??_7CConnection@@6BIADOClass@@@; const CConnection::`vftable'{for `IADOClass'}
0x18005c1cb  mov     [rcx+0F8h], rax
0x18005c1d2  mov     rcx, [rcx+3C8h]
0x18005c1d9  test    rcx, rcx
0x18005c1dc  jz      short loc_18005C1EA
0x18005c1de  mov     rax, [rcx]
0x18005c1e1  mov     rax, [rax+10h]
0x18005c1e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c1ea  mov     rcx, [rbx+3D8h]
0x18005c1f1  test    rcx, rcx
0x18005c1f4  jz      short loc_18005C202
0x18005c1f6  mov     rax, [rcx]
0x18005c1f9  mov     rax, [rax+10h]
0x18005c1fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c202  mov     rcx, [rbx+3F0h]
0x18005c209  test    rcx, rcx
0x18005c20c  jz      short loc_18005C21A
0x18005c20e  mov     rax, [rcx]
0x18005c211  mov     rax, [rax+10h]
0x18005c215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c21a  mov     rcx, [rbx+3E0h]
0x18005c221  test    rcx, rcx
0x18005c224  jz      short loc_18005C232
0x18005c226  mov     rax, [rcx]
0x18005c229  mov     rax, [rax+10h]
0x18005c22d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c232  lea     rbp, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x18005c239  mov     [rbx+4C0h], rbp
0x18005c240  lea     rcx, [rbx+4C8h]
0x18005c247  call    cs:__imp_MPDeleteCriticalSection
0x18005c24e  nop     dword ptr [rax+rax+00h]
0x18005c253  mov     [rbx+4A8h], rbp
0x18005c25a  lea     rcx, [rbx+4B0h]
0x18005c261  call    cs:__imp_MPDeleteCriticalSection
0x18005c268  nop     dword ptr [rax+rax+00h]
0x18005c26d  lea     rcx, [rbx+438h]; this
0x18005c274  call    ??1CConnectionInfo@@QEAA@XZ; CConnectionInfo::~CConnectionInfo(void)
0x18005c279  lea     rcx, [rbx+358h]
0x18005c280  call    ??1?$CADOStackComObject@VCErrors@@@@UEAA@XZ; CADOStackComObject<CErrors>::~CADOStackComObject<CErrors>(void)
0x18005c285  lea     rcx, [rbx+300h]
0x18005c28c  call    ??1?$CADOStackComObject@VCStdActiveLockableCollection@@@@UEAA@XZ; CADOStackComObject<CStdActiveLockableCollection>::~CADOStackComObject<CStdActiveLockableCollection>(void)
0x18005c291  lea     rcx, [rbx+2A8h]
0x18005c298  call    ??1?$CADOStackComObject@VCStdActiveLockableCollection@@@@UEAA@XZ; CADOStackComObject<CStdActiveLockableCollection>::~CADOStackComObject<CStdActiveLockableCollection>(void)
0x18005c29d  lea     rcx, [rbx+278h]; this
0x18005c2a4  call    ??1CCollectionList@@QEAA@XZ; CCollectionList::~CCollectionList(void)
0x18005c2a9  lea     rcx, [rbx+220h]
0x18005c2b0  call    ??1?$CADOStackComObject@VCStdActiveLockableCollection@@@@UEAA@XZ; CADOStackComObject<CStdActiveLockableCollection>::~CADOStackComObject<CStdActiveLockableCollection>(void)
0x18005c2b5  lea     rcx, [rbx+1A0h]
0x18005c2bc  call    ??1?$CADOStackComObject@VCConnProperties@@@@UEAA@XZ; CADOStackComObject<CConnProperties>::~CADOStackComObject<CConnProperties>(void)
0x18005c2c1  lea     rcx, [rbx+130h]; this
0x18005c2c8  call    ??1CConnectionInfo@@QEAA@XZ; CConnectionInfo::~CConnectionInfo(void)
0x18005c2cd  nop
0x18005c2ce  lea     rax, ??_7CNotUpdt_BidGeneric@CConnection@@6B@; const CConnection::CNotUpdt_BidGeneric::`vftable'
0x18005c2d5  mov     [rbx+100h], rax
0x18005c2dc  movsxd  rcx, dword ptr [rbx+108h]
0x18005c2e3  test    ecx, ecx
0x18005c2e5  jz      short loc_18005C31D
0x18005c2e7  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x18005c2ef  jz      short loc_18005C31D
0x18005c2f1  mov     rax, cs:off_180121278
0x18005c2f8  mov     r9, rcx
0x18005c2fb  mov     [rsp+68h+var_48], 0
0x18005c304  mov     r8d, 7
0x18005c30a  mov     rdx, cs:?_bidPtrSA_053_625@?6??BidRecycleID@CNotUpdt_BidGeneric@CConnection@@AEAAHXZ@4REBGEB; ushort const * const `CConnection::CNotUpdt_BidGeneric::BidRecycleID(void)'::`7'::_bidPtrSA_053_625
0x18005c311  mov     rcx, cs:_bidID
0x18005c318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c31d  mov     dword ptr [rbx+108h], 0
0x18005c327  lea     rax, ??_7CStream@@6BIObjectWithSite@@@; const CStream::`vftable'{for `IObjectWithSite'}
0x18005c32e  mov     [rdi], rax
0x18005c331  lea     rax, ??_7CStream@@6BIADOSecurity@@@; const CStream::`vftable'{for `IADOSecurity'}
0x18005c338  mov     [rdi+8], rax
0x18005c33c  mov     rcx, rdi; this
0x18005c33f  call    ?ReleaseTheSite@CObjectWithSiteAndSecurity@@IEAAJXZ; CObjectWithSiteAndSecurity::ReleaseTheSite(void)
0x18005c344  nop
0x18005c345  mov     rcx, r15
0x18005c348  call    ??1?$IConnectionPointImpl@VCRecordset@@$1?IID_DataSourceListener@@3U_GUID@@BVCADOComDynamicUnkArray@@@ATL@@QEAA@XZ; ATL::IConnectionPointImpl<CRecordset,&_GUID const IID_DataSourceListener,CADOComDynamicUnkArray>::~IConnectionPointImpl<CRecordset,&_GUID const IID_DataSourceListener,CADOComDynamicUnkArray>(void)
0x18005c34d  lea     rcx, [rbx+60h]
0x18005c351  call    ??1?$IConnectionPointImpl@VCConnection@@$1?IID_IADOConnectionEvents@@3U_GUID@@BVCADOComDynamicUnkArray@@@ATL@@QEAA@XZ; ATL::IConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,CADOComDynamicUnkArray>::~IConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,CADOComDynamicUnkArray>(void)
0x18005c356  lea     rcx, [rbx+20h]; this
0x18005c35a  add     rsp, 38h
0x18005c35e  pop     r15
0x18005c360  pop     r14
0x18005c362  pop     rdi
0x18005c363  pop     rsi
0x18005c364  pop     rbp
0x18005c365  pop     rbx
0x18005c366  jmp     ??1CStdComObjectRoot@@UEAA@XZ; CStdComObjectRoot::~CStdComObjectRoot(void)
```
