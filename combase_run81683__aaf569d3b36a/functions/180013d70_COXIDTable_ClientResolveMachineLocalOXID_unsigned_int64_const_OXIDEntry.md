# COXIDTable::ClientResolveMachineLocalOXID(unsigned __int64 const &,OXIDEntry * *)

- ea: `0x180013d70`
- end: `0x1800142ea`
- name: `?ClientResolveMachineLocalOXID@COXIDTable@@QEAAJAEB_KPEAPEAVOXIDEntry@@@Z`
- size: `1402`
- prototype: `HRESULT __fastcall(COXIDTable *this, const unsigned __int64 *oxid, OXIDEntry **ppOXIDEntry)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180013840`
- `0x1800dc950`

## callees

- `0x180006250`
- `0x18000712c`
- `0x180012828`
- `0x18001295c`
- `0x180013230`
- `0x180013d70`
- `0x1800142f0`
- `0x1800158a0`
- `0x180030afc`
- `0x18003a8bc`
- `0x18003c7ec`
- `0x180075da4`
- `0x180077af0`
- `0x1800792c8`
- `0x1800865b8`
- `0x18008ce08`
- `0x18008db2c`
- `0x1801999b0`
- `0x18019a654`
- `0x1801c9248`
- `0x1801c9298`

## import_xrefs

- `RPCRT4!NdrClientCall2` at `0x180013f68`
- `RPCRT4!NdrClientCall2` at `0x180013f68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800142cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800142df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800142cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800142df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180013faf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180013faf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013e8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013e8f`

## string_xrefs

- `0x180013dad`: `onecore\com\combase\dcomrem\ipidtbl.cxx`
- `0x18001419c`: `onecore\com\combase\dcomrem\ipidtbl.cxx`
- `0x1800141cd`: `onecore\com\combase\dcomrem\ipidtbl.cxx`
- `0x180245a6c`: `onecore\com\combase\dcomrem\ipidtbl.cxx`
- `0x180245a8e`: `onecore\com\combase\dcomrem\ipidtbl.cxx`
- `0x180014184`: `onecore\com\combase\dcomrem\resolver.cxx`

## pseudocode

```c
__int64 __fastcall COXIDTable::ClientResolveMachineLocalOXID(
        COXIDTable *this,
        unsigned __int64 *oxid,
        OXIDEntry **ppOXIDEntry,
        const char *a4)
{
  unsigned __int64 v6; // rbx
  unsigned int v7; // edi
  int v8; // r14d
  CListElement *first; // rcx
  __int64 v10; // rcx
  _DWORD *ReservedForOle; // rdi
  int v12; // ebx
  TraceLevel v13; // r9d
  unsigned __int64 v15; // rdi
  void *m_hRpc; // r14
  int Pointer; // ebx
  HRESULT v18; // ebx
  HRESULT v19; // eax
  const char *v20; // rcx
  TraceLevel v21; // r9d
  CListElement *i; // rcx
  unsigned __int8 *Myval2; // rax
  TraceLevel v24; // r9d
  __int64 v25; // rcx
  OXIDEntry *ptr; // rcx
  CListElement *last; // rdx
  OXIDEntry *v28; // rcx
  bool v29; // zf
  unsigned int v30; // edx
  unsigned int v31; // edx
  _GUID *p_moxid; // rax
  TraceLevel v33; // r9d
  tagDUALSTRINGARRAY *psaResolver; // [rsp+20h] [rbp-E0h]
  ObjectLibrary::ReferencedPtr<OXIDEntry> ulMarshaledTargetInfoLength; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 usAuthnSvc; // [rsp+68h] [rbp-98h] BYREF
  std::unique_ptr<unsigned char [0],DeleteMarshaledTargetInfo> marshaledTargetInfo; // [rsp+70h] [rbp-90h] BYREF
  _TOKEN_USER *__p; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v39; // [rsp+80h] [rbp-80h] BYREF
  wil::unique_struct<__MIDL_ILocalObjectExporter_0007,void (__cdecl*)(__MIDL_ILocalObjectExporter_0007 *),&ClearOxidInfo,std::nullptr_t,0> oxidInfo; // [rsp+90h] [rbp-70h] BYREF
  void *retaddr; // [rsp+178h] [rbp+78h]

  COleStaticMutexSem::Request(&gOXIDLock, "onecore\\com\\combase\\dcomrem\\ipidtbl.cxx", 0xC79u, a4);
  v6 = *oxid;
  v7 = gLocalMid;
  v8 = HIDWORD(gLocalMid);
  first = COXIDTable::_InUseList._first;
  v39 = *oxid;
  while ( first )
  {
    if ( __PAIR128__(gLocalMid, __PAIR64__(HIDWORD(v39), v6)) == *(_OWORD *)&first[8]._blink )
    {
      ulMarshaledTargetInfoLength.ptr_ = (OXIDEntry *)first;
      OXIDEntry::IncRefCnt((OXIDEntry *)first);
      goto LABEL_6;
    }
    first = first->_flink;
  }
  ulMarshaledTargetInfoLength.ptr_ = 0;
LABEL_6:
  if ( !ulMarshaledTargetInfoLength.ptr_ )
  {
    for ( i = COXIDTable::_ExpireList._first; i; i = i->_flink )
    {
      if ( (_DWORD)v6 == LODWORD(i[8]._blink)
        && (CListElement *)__PAIR64__(v7, HIDWORD(v39)) == *(CListElement **)((char *)&i[8]._blink + 4)
        && v8 == *((_DWORD *)&i[8].m_isInList + 1) )
      {
        marshaledTargetInfo._Mypair._Myval2 = (unsigned __int8 *)i;
        OXIDEntry::IncRefCnt((OXIDEntry *)i);
        Myval2 = marshaledTargetInfo._Mypair._Myval2;
        goto LABEL_34;
      }
    }
    Myval2 = 0;
LABEL_34:
    __p = (_TOKEN_USER *)ulMarshaledTargetInfoLength.ptr_;
    marshaledTargetInfo._Mypair._Myval2 = 0;
    ulMarshaledTargetInfoLength.ptr_ = (OXIDEntry *)Myval2;
    ObjectLibrary::ReferencedPtr<OXIDEntry>::~ReferencedPtr<OXIDEntry>((ObjectLibrary::ReferencedPtr<OXIDEntry> *)&__p);
    ObjectLibrary::ReferencedPtr<OXIDEntry>::~ReferencedPtr<OXIDEntry>((ObjectLibrary::ReferencedPtr<OXIDEntry> *)&marshaledTargetInfo);
    if ( ulMarshaledTargetInfoLength.ptr_ )
    {
      if ( ulMarshaledTargetInfoLength.ptr_ == COXIDTable::_ExpireList._first )
        COXIDTable::_ExpireList._first = COXIDTable::_ExpireList._first->_flink;
      if ( ulMarshaledTargetInfoLength.ptr_ == COXIDTable::_ExpireList._last )
        COXIDTable::_ExpireList._last = COXIDTable::_ExpireList._last->_blink;
      CListElement::Unlink(ulMarshaledTargetInfoLength.ptr_);
      *(_BYTE *)(v25 + 16) = 0;
      ulMarshaledTargetInfoLength.ptr_->_pendingRelease._Storage._Value = 0;
      ptr = ulMarshaledTargetInfoLength.ptr_;
      ulMarshaledTargetInfoLength.ptr_->_dwExpiredTime = 0;
      ptr->_cRefs = 1;
      last = COXIDTable::_InUseList._last;
      v28 = ulMarshaledTargetInfoLength.ptr_;
      if ( COXIDTable::_InUseList._last )
      {
        if ( COXIDTable::_InUseList._last->_flink )
          COXIDTable::_InUseList._last->_flink->_blink = ulMarshaledTargetInfoLength.ptr_;
        v28->_flink = last->_flink;
        v28->_blink = last;
        last->_flink = v28;
      }
      else
      {
        COXIDTable::_InUseList._first = ulMarshaledTargetInfoLength.ptr_;
      }
      v29 = gfEnableTracing == 0;
      COXIDTable::_InUseList._last = v28;
      v28->m_isInList = 1;
      if ( !v29 && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
        ComTraceMessageT<unsigned __int64,_GUID *>(
          (const char *)v28,
          "COXIDTable::LookupOXID",
          2587,
          v24,
          L"Expired oxid %I64X returned to in-use list, moxid: %!GUID!",
          *oxid,
          &ulMarshaledTargetInfoLength.ptr_->_moxid);
      --COXIDTable::_cExpired;
    }
  }
  *ppOXIDEntry = ulMarshaledTargetInfoLength.ptr_;
  ulMarshaledTargetInfoLength.ptr_ = 0;
  ObjectLibrary::ReferencedPtr<OXIDEntry>::~ReferencedPtr<OXIDEntry>(&ulMarshaledTargetInfoLength);
  if ( !--gOXIDLock._cLocks && gOXIDLock._lockOrder != Highest )
  {
    ReservedForOle = NtCurrentTeb()->ReservedForOle;
    if ( ReservedForOle )
    {
      LOBYTE(v10) = gOXIDLock._lockOrder;
      v12 = 1 << gOXIDLock._lockOrder;
      if ( ((1 << gOXIDLock._lockOrder) & ReservedForOle[144]) == 0 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v10);
      ReservedForOle[144] &= ~v12;
    }
  }
  LeaveCriticalSection(&gOXIDLock._cs);
  if ( *ppOXIDEntry )
  {
    if ( gfEnableTracing )
    {
      if ( (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
        ComTraceMessageT<unsigned __int64,_GUID *>(
          (const char *)*ppOXIDEntry,
          "COXIDTable::ClientResolveMachineLocalOXID",
          3205,
          v13,
          L"Oxid %I64X known to this process, moxid: %!GUID!",
          *oxid,
          &(*ppOXIDEntry)->_moxid);
    }
    return 0;
  }
  v15 = *oxid;
  LODWORD(ulMarshaledTargetInfoLength.ptr_) = 0;
  marshaledTargetInfo._Mypair._Myval2 = 0;
  usAuthnSvc = 0;
  memset_0((void *)&oxidInfo, 0, sizeof(oxidInfo));
  m_hRpc = gResolver._fbhILocalObjectExporter._Mypair._Myval2->m_hRpc;
  __p = 0;
  do
  {
    v39 = 0;
    Pointer = (unsigned int)NdrClientCall2(
                              &ILocalObjectExporter_StubDesc,
                              &lclor__MIDL_ProcFormatString.Format[504],
                              m_hRpc,
                              CRpcResolver::_ph,
                              v15,
                              0,
                              &oxidInfo,
                              &v39,
                              &ulMarshaledTargetInfoLength,
                              &__p,
                              &usAuthnSvc).Pointer;
  }
  while ( CRpcResolver::RetryRPC(Pointer) );
  v18 = CRpcResolver::CheckStatus(Pointer);
  std::unique_ptr<unsigned char [0],DeleteMarshaledTargetInfo>::reset<unsigned char *,0>(
    (wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> *)&marshaledTargetInfo,
    __p);
  if ( v18 < 0 )
  {
    v30 = 1340;
LABEL_48:
    wil::details::in1diag3::Return_Hr(retaddr, v30, "onecore\\com\\combase\\dcomrem\\resolver.cxx", v18);
    v31 = 3219;
    goto LABEL_49;
  }
  v18 = ValidateOxidInfoFromResolver(&oxidInfo);
  if ( v18 < 0 )
  {
    v30 = 1341;
    goto LABEL_48;
  }
  if ( oxidInfo.dwPid == GetCurrentProcessId() )
  {
    if ( gfEnableTracing && IsWppLevelEnabled(INFO) )
      ComTraceMessageT<void *>(
        "onecore\\com\\combase\\dcomrem\\ipidtbl.cxx",
        "COXIDTable::ClientResolveMachineLocalOXID",
        3234,
        v33,
        L"Oxid %I64X is in the same process as the client",
        (wchar_t *)*oxid);
    v18 = wil::details::in1diag3::Return_Win32(retaddr, 0xCA4u, "onecore\\com\\combase\\dcomrem\\ipidtbl.cxx", 0x776u);
    std::unique_ptr<unsigned char [0],DeleteMarshaledTargetInfo>::~unique_ptr<unsigned char [0],DeleteMarshaledTargetInfo>(&marshaledTargetInfo);
    goto LABEL_51;
  }
  v19 = COXIDTable::FindOrCreateOXIDEntry(
          &gOXIDTbl,
          (OXIDEntry *)*oxid,
          &oxidInfo,
          (const char *)1,
          0,
          gLocalMid,
          (unsigned int)ulMarshaledTargetInfoLength.ptr_,
          &marshaledTargetInfo,
          usAuthnSvc,
          ppOXIDEntry);
  v18 = v19;
  if ( v19 >= 0 )
  {
    if ( gfEnableTracing && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
    {
      if ( *ppOXIDEntry )
        p_moxid = &(*ppOXIDEntry)->_moxid;
      else
        p_moxid = &GUID_NULL;
      ComTraceMessageT<unsigned __int64,_GUID const *>(
        v20,
        "COXIDTable::ClientResolveMachineLocalOXID",
        3245,
        v21,
        &psaResolver->wNumEntries,
        *oxid,
        p_moxid);
    }
    if ( marshaledTargetInfo._Mypair._Myval2 )
      HeapFree(g_hHeap, 0, marshaledTargetInfo._Mypair._Myval2);
    ClearOxidInfo(&oxidInfo.__MIDL_ILocalObjectExporter_0007);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, 0xD1Cu, "onecore\\com\\combase\\dcomrem\\ipidtbl.cxx", v19);
  v31 = 3240;
LABEL_49:
  wil::details::in1diag3::Return_Hr(retaddr, v31, "onecore\\com\\combase\\dcomrem\\ipidtbl.cxx", v18);
  if ( marshaledTargetInfo._Mypair._Myval2 )
    HeapFree(g_hHeap, 0, marshaledTargetInfo._Mypair._Myval2);
LABEL_51:
  ClearOxidInfo(&oxidInfo.__MIDL_ILocalObjectExporter_0007);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180013d70  mov     [rsp-8+arg_0], rbx
0x180013d75  push    rbp
0x180013d76  push    rsi
0x180013d77  push    rdi
0x180013d78  push    r12
0x180013d7a  push    r13
0x180013d7c  push    r14
0x180013d7e  push    r15
0x180013d80  lea     rbp, [rsp-40h]
0x180013d85  sub     rsp, 140h
0x180013d8c  mov     rax, cs:__security_cookie
0x180013d93  xor     rax, rsp
0x180013d96  mov     [rbp+70h+var_40], rax
0x180013d9a  mov     r12, ppOXIDEntry
0x180013d9d  lea     rcx, ?gOXIDLock@@3VCOleStaticMutexSem@@A; this
0x180013da4  mov     rsi, oxid
0x180013da7  mov     r8d, 0C79h; dwLine
0x180013dad  lea     oxid, aOnecoreComComb_23; "onecore\\com\\combase\\dcomrem\\ipidtbl"...
0x180013db4  call    ?Request@COleStaticMutexSem@@QEAAXPEBDK0@Z; COleStaticMutexSem::Request(char const *,ulong,char const *)
0x180013db9  mov     rbx, [rsi]
0x180013dbc  xor     r13d, r13d
0x180013dbf  mov     edi, dword ptr cs:?gLocalMid@@3_KA; unsigned __int64 gLocalMid
0x180013dc5  mov     r14d, dword ptr cs:?gLocalMid@@3_KA+4; unsigned __int64 gLocalMid
0x180013dcc  mov     rcx, cs:?_InUseList@COXIDTable@@0V?$CListBase@$0A@$0A@@@A._first; this
0x180013dd3  mov     [rbp+70h+var_F0], rbx
0x180013dd7  mov     r15d, dword ptr [rbp+70h+var_F0+4]
0x180013ddb  test    rcx, rcx
0x180013dde  jz      loc_180013ED4
0x180013de4  cmp     ebx, [rcx+0C8h]
0x180013dea  jz      short loc_180013DF1
0x180013dec  mov     rcx, [rcx]
0x180013def  jmp     short loc_180013DDB
0x180013df1  cmp     r15d, [rcx+0CCh]
0x180013df8  jnz     short loc_180013DEC
0x180013dfa  cmp     edi, [rcx+0D0h]
0x180013e00  jnz     short loc_180013DEC
0x180013e02  cmp     r14d, [rcx+0D4h]
0x180013e09  jnz     short loc_180013DEC
0x180013e0b  mov     [rsp+170h+ulMarshaledTargetInfoLength], rcx
0x180013e10  call    ?IncRefCnt@OXIDEntry@@QEAAKXZ; OXIDEntry::IncRefCnt(void)
0x180013e15  cmp     [rsp+170h+ulMarshaledTargetInfoLength], r13
0x180013e1a  jz      loc_18001403B
0x180013e20  mov     rax, [rsp+170h+ulMarshaledTargetInfoLength]
0x180013e25  lea     rcx, [rsp+170h+ulMarshaledTargetInfoLength]; this
0x180013e2a  mov     [r12], rax
0x180013e2e  mov     [rsp+170h+ulMarshaledTargetInfoLength], r13
0x180013e33  call    ??1?$ReferencedPtr@VOXIDEntry@@@ObjectLibrary@@QEAA@XZ; ObjectLibrary::ReferencedPtr<OXIDEntry>::~ReferencedPtr<OXIDEntry>(void)
0x180013e38  mov     eax, cs:?gOXIDLock@@3VCOleStaticMutexSem@@A._cLocks; COleStaticMutexSem gOXIDLock ...
0x180013e3e  add     eax, 0FFFFFFFFh
0x180013e41  mov     cs:?gOXIDLock@@3VCOleStaticMutexSem@@A._cLocks, eax; COleStaticMutexSem gOXIDLock ...
0x180013e47  jnz     short loc_180013E88
0x180013e49  cmp     cs:?gOXIDLock@@3VCOleStaticMutexSem@@A._lockOrder, 13h; COleStaticMutexSem gOXIDLock ...
0x180013e50  jz      short loc_180013E88
0x180013e52  mov     rax, gs:30h
0x180013e5b  mov     rdi, [rax+1758h]
0x180013e62  test    rdi, rdi
0x180013e65  jz      short loc_180013E88
0x180013e67  mov     cl, cs:?gOXIDLock@@3VCOleStaticMutexSem@@A._lockOrder; COleStaticMutexSem gOXIDLock ...
0x180013e6d  mov     ebx, 1
0x180013e72  shl     ebx, cl
0x180013e74  test    [rdi+240h], ebx
0x180013e7a  jz      loc_1800141E8
0x180013e80  not     ebx
0x180013e82  and     [rdi+240h], ebx
0x180013e88  lea     rcx, ?gOXIDLock@@3VCOleStaticMutexSem@@A._cs; lpCriticalSection
0x180013e8f  call    cs:__imp_LeaveCriticalSection
0x180013e95  mov     rcx, [r12]; function
0x180013e99  test    rcx, rcx
0x180013e9c  jz      short loc_180013EDE
0x180013e9e  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x180013ea5  jnz     loc_1800141FB
0x180013eab  xor     eax, eax
0x180013ead  mov     rcx, [rbp+70h+var_40]
0x180013eb1  xor     rcx, rsp; StackCookie
0x180013eb4  call    __security_check_cookie
0x180013eb9  mov     rbx, [rsp+170h+arg_0]
0x180013ec1  add     rsp, 140h
0x180013ec8  pop     r15
0x180013eca  pop     r14
0x180013ecc  pop     r13
0x180013ece  pop     r12
0x180013ed0  pop     rdi
0x180013ed1  pop     rsi
0x180013ed2  pop     rbp
0x180013ed3  retn
0x180013ed4  mov     [rsp+170h+ulMarshaledTargetInfoLength], r13
0x180013ed9  jmp     loc_180013E15
0x180013ede  mov     rdi, [rsi]
0x180013ee1  lea     rcx, [rbp+70h+oxidInfo]; void *
0x180013ee5  xor     edx, edx; Val
0x180013ee7  mov     dword ptr [rsp+170h+ulMarshaledTargetInfoLength], r13d
0x180013eec  mov     r8d, 98h; Size
0x180013ef2  mov     [rsp+170h+marshaledTargetInfo._Mypair._Myval2], r13
0x180013ef7  mov     [rsp+170h+usAuthnSvc], r13w
0x180013efd  call    memset_0
0x180013f02  mov     rax, cs:?gResolver@@3VCRpcResolver@@A._fbhILocalObjectExporter._Mypair._Myval2; CRpcResolver gResolver ...
0x180013f09  mov     r14, [rax+10h]
0x180013f0d  mov     [rsp+170h+__p], r13
0x180013f12  mov     r9, cs:?_ph@CRpcResolver@@0PEAXEA; void * CRpcResolver::_ph
0x180013f19  lea     rax, [rsp+170h+usAuthnSvc]
0x180013f1e  mov     [rsp+170h+var_120], rax
0x180013f23  lea     oxid, lclor__MIDL_ProcFormatString.Format+1F8h; pFormat
0x180013f2a  lea     rax, [rsp+170h+__p]
0x180013f2f  mov     [rbp+70h+var_F0], r13
0x180013f33  mov     [rsp+170h+var_128], rax
0x180013f38  lea     rcx, ILocalObjectExporter_StubDesc; pStubDescriptor
0x180013f3f  lea     rax, [rsp+170h+ulMarshaledTargetInfoLength]
0x180013f44  mov     ppOXIDEntry, r14
0x180013f47  mov     qword ptr [rsp+170h+dwAuthSvcToUseIfOxidNotFound], rax
0x180013f4c  lea     rax, [rbp+70h+var_F0]
0x180013f50  mov     [rsp+170h+var_138], rax
0x180013f55  lea     rax, [rbp+70h+oxidInfo]
0x180013f59  mov     [rsp+170h+function], rax
0x180013f5e  mov     [rsp+170h+mid], r13
0x180013f63  mov     [rsp+170h+psaResolver], rdi
0x180013f68  call    cs:__imp_NdrClientCall2
0x180013f6e  mov     ecx, eax; sc
0x180013f70  mov     rbx, rax
0x180013f73  call    ?RetryRPC@CRpcResolver@@CAHJ@Z; CRpcResolver::RetryRPC(long)
0x180013f78  test    eax, eax
0x180013f7a  jnz     short loc_180013F12
0x180013f7c  mov     ecx, ebx; sc
0x180013f7e  call    ?CheckStatus@CRpcResolver@@CAJJ@Z; CRpcResolver::CheckStatus(long)
0x180013f83  mov     oxid, [rsp+170h+__p]; __p
0x180013f88  lea     rcx, [rsp+170h+marshaledTargetInfo]; this
0x180013f8d  mov     ebx, eax
0x180013f8f  call    ??$reset@PEAE$0A@@?$unique_ptr@$$BY0A@EUDeleteMarshaledTargetInfo@@@std@@QEAAXPEAE@Z; std::unique_ptr<uchar [0],DeleteMarshaledTargetInfo>::reset<uchar *,0>(uchar *)
0x180013f94  test    ebx, ebx
0x180013f96  js      loc_18001417B
0x180013f9c  lea     rcx, [rbp+70h+oxidInfo]; oxidInfo
0x180013fa0  call    ?ValidateOxidInfoFromResolver@@YAJAEBU__MIDL_ILocalObjectExporter_0007@@@Z; ValidateOxidInfoFromResolver(__MIDL_ILocalObjectExporter_0007 const &)
0x180013fa5  mov     ebx, eax
0x180013fa7  test    eax, eax
0x180013fa9  js      loc_1800142B8
0x180013faf  call    cs:__imp_GetCurrentProcessId
0x180013fb5  cmp     [rbp+70h+oxidInfo.dwPid], eax
0x180013fb8  jz      loc_180245A42
0x180013fbe  movzx   eax, [rsp+170h+usAuthnSvc]
0x180013fc3  lea     ppOXIDEntry, [rbp+70h+oxidInfo]; oxidInfo
0x180013fc7  mov     ecx, dword ptr [rsp+170h+ulMarshaledTargetInfoLength]
0x180013fcb  mov     r9d, 1; eResolverRef
0x180013fd1  mov     oxid, cs:?gLocalMid@@3_KA; unsigned __int64 gLocalMid
0x180013fd8  mov     [rsp+170h+var_128], r12; ppOXIDEntry
0x180013fdd  mov     [rsp+170h+dwAuthSvcToUseIfOxidNotFound], eax; dwAuthSvcToUseIfOxidNotFound
0x180013fe1  lea     rax, [rsp+170h+marshaledTargetInfo]
0x180013fe6  mov     [rsp+170h+var_138], rax; marshaledTargetInfo
0x180013feb  mov     dword ptr [rsp+170h+function], ecx; ulMarshaledTargetInfoLength
0x180013fef  lea     rcx, ?gOXIDTbl@@3VCOXIDTable@@A; this
0x180013ff6  mov     [rsp+170h+mid], oxid; mid
0x180013ffb  mov     oxid, [rsi]; oxid
0x180013ffe  mov     [rsp+170h+psaResolver], r13; file
0x180014003  call    ?FindOrCreateOXIDEntry@COXIDTable@@QEAAJ_K$$QEAV?$unique_struct@U__MIDL_ILocalObjectExporter_0007@@P6AXPEAU1@@Z$1?ClearOxidInfo@@YAX0@Z$$T$0A@@wil@@W4tagFOCOXID@@PEBUtagDUALSTRINGARRAY@@0KAEBV?$unique_ptr@$$BY0A@EUDeleteMarshaledTargetInfo@@@std@@KPEAPEAVOXIDEntry@@@Z; COXIDTable::FindOrCreateOXIDEntry(unsigned __int64,wil::unique_struct<__MIDL_ILocalObjectExporter_0007,void (*)(__MIDL_ILocalObjectExporter_0007 *),&ClearOxidInfo(__MIDL_ILocalObjectExporter_0007 *),std::nullptr_t,0> &&,tagFOCOXID,tagDUALSTRINGARRAY const *,unsigned __int64,ulong,std::unique_ptr<uchar [0],DeleteMarshaledTargetInfo> const &,ulong,OXIDEntry * *)
0x180014008  mov     ebx, eax
0x18001400a  test    eax, eax
0x18001400c  js      loc_1800141C9
0x180014012  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x180014019  jnz     loc_180014243
0x18001401f  mov     ppOXIDEntry, [rsp+170h+marshaledTargetInfo._Mypair._Myval2]; lpMem
0x180014024  test    ppOXIDEntry, ppOXIDEntry
0x180014027  jnz     loc_1800142D6
0x18001402d  lea     rcx, [rbp+70h+oxidInfo]; oxidInfo
0x180014031  call    ?ClearOxidInfo@@YAXPEAU__MIDL_ILocalObjectExporter_0007@@@Z; ClearOxidInfo(__MIDL_ILocalObjectExporter_0007 *)
0x180014036  jmp     loc_180013EAB
0x18001403b  mov     rcx, cs:?_ExpireList@COXIDTable@@0V?$CListBase@$0A@$0A@@@A._first; this
0x180014042  test    rcx, rcx
0x180014045  jz      loc_180014173
0x18001404b  cmp     ebx, [rcx+0C8h]
0x180014051  jz      short loc_180014058
0x180014053  mov     rcx, [rcx]
0x180014056  jmp     short loc_180014042
0x180014058  cmp     r15d, [rcx+0CCh]
0x18001405f  jnz     short loc_180014053
0x180014061  cmp     edi, [rcx+0D0h]
0x180014067  jnz     short loc_180014053
0x180014069  cmp     r14d, [rcx+0D4h]
0x180014070  jnz     short loc_180014053
0x180014072  mov     [rsp+170h+marshaledTargetInfo._Mypair._Myval2], rcx
0x180014077  call    ?IncRefCnt@OXIDEntry@@QEAAKXZ; OXIDEntry::IncRefCnt(void)
0x18001407c  mov     rax, [rsp+170h+marshaledTargetInfo._Mypair._Myval2]
0x180014081  mov     rcx, [rsp+170h+ulMarshaledTargetInfoLength]
0x180014086  mov     [rsp+170h+__p], rcx
0x18001408b  lea     rcx, [rsp+170h+__p]; this
0x180014090  mov     [rsp+170h+marshaledTargetInfo._Mypair._Myval2], r13
0x180014095  mov     [rsp+170h+ulMarshaledTargetInfoLength], rax
0x18001409a  call    ??1?$ReferencedPtr@VOXIDEntry@@@ObjectLibrary@@QEAA@XZ; ObjectLibrary::ReferencedPtr<OXIDEntry>::~ReferencedPtr<OXIDEntry>(void)
0x18001409f  cmp     [rsp+170h+ulMarshaledTargetInfoLength], r13
0x1800140a4  lea     rcx, [rsp+170h+marshaledTargetInfo]; this
0x1800140a9  setnz   bl
0x1800140ac  call    ??1?$ReferencedPtr@VOXIDEntry@@@ObjectLibrary@@QEAA@XZ; ObjectLibrary::ReferencedPtr<OXIDEntry>::~ReferencedPtr<OXIDEntry>(void)
0x1800140b1  test    bl, bl
0x1800140b3  jz      loc_180013E20
0x1800140b9  mov     rcx, [rsp+170h+ulMarshaledTargetInfoLength]; this
0x1800140be  test    rcx, rcx
0x1800140c1  jz      short loc_1800140FE
0x1800140c3  mov     rax, cs:?_ExpireList@COXIDTable@@0V?$CListBase@$0A@$0A@@@A._first; CListBase<0,0> COXIDTable::_ExpireList ...
0x1800140ca  cmp     rcx, rax
0x1800140cd  jnz     short loc_1800140D9
0x1800140cf  mov     rax, [rax]
0x1800140d2  mov     cs:?_ExpireList@COXIDTable@@0V?$CListBase@$0A@$0A@@@A._first, rax; CListBase<0,0> COXIDTable::_ExpireList ...
0x1800140d9  mov     rax, cs:?_ExpireList@COXIDTable@@0V?$CListBase@$0A@$0A@@@A._last; CListBase<0,0> COXIDTable::_ExpireList ...
0x1800140e0  cmp     rcx, rax
0x1800140e3  jnz     short loc_1800140F0
0x1800140e5  mov     rax, [rax+8]
0x1800140e9  mov     cs:?_ExpireList@COXIDTable@@0V?$CListBase@$0A@$0A@@@A._last, rax; CListBase<0,0> COXIDTable::_ExpireList ...
0x1800140f0  call    ?Unlink@CListElement@@IEAAXXZ; CListElement::Unlink(void)
0x1800140f5  mov     [rcx+10h], r13b
0x1800140f9  mov     rcx, [rsp+170h+ulMarshaledTargetInfoLength]
0x1800140fe  mov     eax, r13d
0x180014101  xchg    al, [rcx+0DAh]
0x180014107  mov     rcx, [rsp+170h+ulMarshaledTargetInfoLength]
0x18001410c  mov     [rcx+130h], r13d
0x180014113  mov     dword ptr [rcx+118h], 1
0x18001411d  mov     oxid, cs:?_InUseList@COXIDTable@@0V?$CListBase@$0A@$0A@@@A._last; CListBase<0,0> COXIDTable::_InUseList ...
0x180014124  mov     rcx, [rsp+170h+ulMarshaledTargetInfoLength]; function
0x180014129  test    oxid, oxid
0x18001412c  jz      short loc_18001416A
0x18001412e  mov     rax, [oxid]
0x180014131  test    rax, rax
0x180014134  jnz     loc_1800141F2
0x18001413a  mov     rax, [oxid]
0x18001413d  mov     [rcx], rax
0x180014140  mov     [rcx+8], oxid
0x180014144  mov     [oxid], rcx
0x180014147  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x18001414e  mov     cs:?_InUseList@COXIDTable@@0V?$CListBase@$0A@$0A@@@A._last, rcx; CListBase<0,0> COXIDTable::_InUseList ...
0x180014155  mov     byte ptr [rcx+10h], 1
0x180014159  jnz     loc_18001426C
0x18001415f  dec     cs:?_cExpired@COXIDTable@@0KA; ulong COXIDTable::_cExpired
0x180014165  jmp     loc_180013E20
0x18001416a  mov     cs:?_InUseList@COXIDTable@@0V?$CListBase@$0A@$0A@@@A._first, rcx; CListBase<0,0> COXIDTable::_InUseList ...
0x180014171  jmp     short loc_180014147
0x180014173  mov     rax, r13
0x180014176  jmp     loc_180014081
0x18001417b  mov     edx, 53Ch; lineNumber
0x180014180  mov     rcx, [rbp+78h]; callerReturnAddress
0x180014184  lea     ppOXIDEntry, aOnecoreComComb_138; "onecore\\com\\combase\\dcomrem\\resolve"...
0x18001418b  mov     r9d, ebx; hr
0x18001418e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014193  mov     edx, 0C93h; lineNumber
0x180014198  mov     rcx, [rbp+78h]; callerReturnAddress
0x18001419c  lea     ppOXIDEntry, aOnecoreComComb_23; "onecore\\com\\combase\\dcomrem\\ipidtbl"...
0x1800141a3  mov     r9d, ebx; hr
0x1800141a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800141ab  mov     ppOXIDEntry, [rsp+170h+marshaledTargetInfo._Mypair._Myval2]; lpMem
0x1800141b0  test    ppOXIDEntry, ppOXIDEntry
0x1800141b3  jnz     loc_1800142C2
0x1800141b9  lea     rcx, [rbp+70h+oxidInfo]; oxidInfo
0x1800141bd  call    ?ClearOxidInfo@@YAXPEAU__MIDL_ILocalObjectExporter_0007@@@Z; ClearOxidInfo(__MIDL_ILocalObjectExporter_0007 *)
0x1800141c2  mov     eax, ebx
0x1800141c4  jmp     loc_180013EAD
0x1800141c9  mov     rcx, [rbp+78h]; callerReturnAddress
0x1800141cd  lea     ppOXIDEntry, aOnecoreComComb_23; "onecore\\com\\combase\\dcomrem\\ipidtbl"...
0x1800141d4  mov     r9d, ebx; hr
0x1800141d7  mov     edx, 0D1Ch; lineNumber
0x1800141dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800141e1  mov     edx, 0CA8h
0x1800141e6  jmp     short loc_180014198
0x1800141e8  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "lockFlag & _locksHeldByThread")
0x1800141ed  jmp     loc_180013E80
0x1800141f2  mov     [rax+8], rcx
0x1800141f6  jmp     loc_18001413A
0x1800141fb  mov     rax, cs:WPP_GLOBAL_Control
0x180014202  test    byte ptr [rax+1Ch], 4
0x180014206  jz      loc_180013EAB
0x18001420c  lea     rax, [rcx+0C8h]
0x180014213  mov     r8d, 0C85h; format
0x180014219  mov     [rsp+170h+function], rax; function
0x18001421e  lea     oxid, aCoxidtableClie_0; "COXIDTable::ClientResolveMachineLocalOX"...
0x180014225  mov     rax, [rsi]
0x180014228  mov     [rsp+170h+mid], rax; file
0x18001422d  lea     rax, aOxidI64xKnownT; "Oxid %I64X known to this process, moxid"...
0x180014234  mov     [rsp+170h+psaResolver], rax; <args_1>
0x180014239  call    ??$ComTraceMessageT@_KPEAU_GUID@@@@YAXPEBD0HW4TraceLevel@@PEBG_KPEAU_GUID@@@Z; ComTraceMessageT<unsigned __int64,_GUID *>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,_GUID *)
0x18001423e  jmp     loc_180013EAB
0x180014243  mov     rax, cs:WPP_GLOBAL_Control
0x18001424a  test    byte ptr [rax+1Ch], 4
0x18001424e  jz      loc_18001401F
0x180014254  mov     rax, [r12]
0x180014258  test    rax, rax
0x18001425b  jz      loc_180245AB7
0x180014261  add     rax, 0C8h
0x180014267  jmp     loc_180245ABE
0x18001426c  mov     rax, cs:WPP_GLOBAL_Control
0x180014273  test    byte ptr [rax+1Ch], 4
0x180014277  jz      loc_18001415F
0x18001427d  mov     rax, [rsp+170h+ulMarshaledTargetInfoLength]
0x180014282  lea     oxid, aCoxidtableLook; "COXIDTable::LookupOXID"
0x180014289  add     rax, 0C8h
0x18001428f  mov     r8d, 0A1Bh; format
0x180014295  mov     [rsp+170h+function], rax; function
0x18001429a  mov     rax, [rsi]
0x18001429d  mov     [rsp+170h+mid], rax; file
0x1800142a2  lea     rax, aExpiredOxidI64; "Expired oxid %I64X returned to in-use l"...
0x1800142a9  mov     [rsp+170h+psaResolver], rax; <args_1>
0x1800142ae  call    ??$ComTraceMessageT@_KPEAU_GUID@@@@YAXPEBD0HW4TraceLevel@@PEBG_KPEAU_GUID@@@Z; ComTraceMessageT<unsigned __int64,_GUID *>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,_GUID *)
0x1800142b3  jmp     loc_18001415F
0x1800142b8  mov     edx, 53Dh
0x1800142bd  jmp     loc_180014180
0x1800142c2  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800142c9  xor     edx, edx; dwFlags
  ... truncated ...
```
