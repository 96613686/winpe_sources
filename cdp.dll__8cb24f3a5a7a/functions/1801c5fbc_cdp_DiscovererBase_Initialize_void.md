# cdp::DiscovererBase::Initialize(void)

- ea: `0x1801c5fbc`
- end: `0x1801c6327`
- name: `?Initialize@DiscovererBase@cdp@@QEAAXXZ`
- size: `875`
- prototype: `void __fastcall(cdp::DiscovererBase *__hidden this)`
- caller_count: `4`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1801c5a70`
- `0x1801c5be4`
- `0x1801c5d68`
- `0x1802612b0`

## callees

- `0x180013da0`
- `0x1800376a8`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800f2550`
- `0x180143248`
- `0x1801c5fbc`
- `0x1801c63cc`
- `0x1801c6498`
- `0x1801fcb36`
- `0x180210ff0`
- `0x180253760`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801c6001`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801c610f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801c61a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801c62a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801c6001`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801c610f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801c61a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801c62a8`

## string_xrefs

- `0x1801c6027`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1801c6135`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1801c61c7`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1801c62ce`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall cdp::DiscovererBase::Initialize(cdp::DiscovererBase *this)
{
  _QWORD *v2; // rsi
  int v3; // eax
  unsigned int v4; // edi
  DWORD CurrentThreadId; // eax
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // r15
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  unsigned int v14; // edi
  DWORD v15; // eax
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rax
  int v20; // eax
  unsigned int v21; // edi
  DWORD v22; // eax
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rax
  __int64 v27; // r14
  __int64 v28; // rcx
  int v29; // eax
  int v30; // eax
  unsigned int v31; // ebx
  DWORD v32; // eax
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rax
  int v37; // [rsp+20h] [rbp-39h]
  const char *v38; // [rsp+30h] [rbp-29h] BYREF
  std::_Ref_count_base *v39; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v40[24]; // [rsp+40h] [rbp-19h] BYREF
  _BYTE pExceptionObject[88]; // [rsp+58h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  int v43; // [rsp+C0h] [rbp+67h] BYREF
  __int64 v44; // [rsp+C8h] [rbp+6Fh] BYREF

  v2 = (_QWORD *)((char *)this + 440);
  v3 = CDPCreateLoggedOnUserChangedNotifier((char *)this + 440);
  v4 = v3;
  if ( v3 < 0 )
  {
    v38 = "..\\discovererbase.cpp";
    LODWORD(v39) = 35;
    v43 = v3;
    CurrentThreadId = GetCurrentThreadId();
    v44 = CurrentThreadId;
    Log<long &,char const * &,int &,unsigned __int64>(
      CurrentThreadId,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v43,
      (unsigned int)&v38,
      (__int64)&v39,
      (__int64)&v44);
    v6 = cdp::ExceptionStackFromSourceLocationInfo(v40, &v38);
    v9 = cdp::ErrorCodeToString(v4, v7, v8, v6);
    ConnectedDevices::Exception::Exception(pExceptionObject, v4, v9);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v10 = std::enable_shared_from_this<cdp::DiscovererBase>::shared_from_this((char *)this + 136, &v38);
  v11 = *((_QWORD *)this + 58);
  *((_QWORD *)this + 58) = 0;
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  v12 = Microsoft::WRL::Details::MakeAndInitialize<cdp::DiscovererBase::CDPLoggedOnUserCallback,cdp::DiscovererBase::CDPLoggedOnUserCallback,std::shared_ptr<cdp::DiscovererBase>>(
          (char *)this + 464,
          v10);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"..\\discovererbase.cpp",
      (const char *)(unsigned int)v12,
      v37);
  if ( v39 )
    std::_Ref_count_base::_Decref(v39);
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(*(_QWORD *)*v2 + 32LL))(
          *v2,
          *((_QWORD *)this + 58),
          (char *)this + 472);
  v14 = v13;
  if ( v13 < 0 )
  {
    v38 = "..\\discovererbase.cpp";
    LODWORD(v39) = 37;
    v43 = v13;
    v15 = GetCurrentThreadId();
    v44 = v15;
    Log<long &,char const * &,int &,unsigned __int64>(
      v15,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v43,
      (unsigned int)&v38,
      (__int64)&v39,
      (__int64)&v44);
    v16 = cdp::ExceptionStackFromSourceLocationInfo(v40, &v38);
    v19 = cdp::ErrorCodeToString(v14, v17, v18, v16);
    ConnectedDevices::Exception::Exception(pExceptionObject, v14, v19);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v20 = CDPCreateLoggedOnUserFamilyChangedNotifier((char *)this + 448);
  v21 = v20;
  if ( v20 < 0 )
  {
    v38 = "..\\discovererbase.cpp";
    LODWORD(v39) = 39;
    v43 = v20;
    v22 = GetCurrentThreadId();
    v44 = v22;
    Log<long &,char const * &,int &,unsigned __int64>(
      v22,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v43,
      (unsigned int)&v38,
      (__int64)&v39,
      (__int64)&v44);
    v23 = cdp::ExceptionStackFromSourceLocationInfo(v40, &v38);
    v26 = cdp::ErrorCodeToString(v21, v24, v25, v23);
    ConnectedDevices::Exception::Exception(pExceptionObject, v21, v26);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v27 = std::enable_shared_from_this<cdp::DiscovererBase>::shared_from_this((char *)this + 136, &v38);
  v28 = *((_QWORD *)this + 57);
  *((_QWORD *)this + 57) = 0;
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  v29 = Microsoft::WRL::Details::MakeAndInitialize<cdp::DiscovererBase::CDPLoggedOnUserSetFamilyInfoCallback,cdp::DiscovererBase::CDPLoggedOnUserSetFamilyInfoCallback,std::shared_ptr<cdp::DiscovererBase>>(
          (char *)this + 456,
          v27);
  if ( v29 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"..\\discovererbase.cpp",
      (const char *)(unsigned int)v29,
      v37);
  if ( v39 )
    std::_Ref_count_base::_Decref(v39);
  v30 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(**((_QWORD **)this + 56) + 32LL))(
          *((_QWORD *)this + 56),
          *((_QWORD *)this + 57),
          (char *)this + 476);
  v31 = v30;
  if ( v30 < 0 )
  {
    v38 = "..\\discovererbase.cpp";
    LODWORD(v39) = 42;
    v43 = v30;
    v32 = GetCurrentThreadId();
    v44 = v32;
    Log<long &,char const * &,int &,unsigned __int64>(
      v32,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v43,
      (unsigned int)&v38,
      (__int64)&v39,
      (__int64)&v44);
    v33 = cdp::ExceptionStackFromSourceLocationInfo(v40, &v38);
    v36 = cdp::ErrorCodeToString(v31, v34, v35, v33);
    ConnectedDevices::Exception::Exception(pExceptionObject, v31, v36);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x1801c5fbc  mov     [rsp-8+arg_10], rbx
0x1801c5fc1  push    rbp
0x1801c5fc2  push    rsi
0x1801c5fc3  push    rdi
0x1801c5fc4  push    r14
0x1801c5fc6  push    r15
0x1801c5fc8  lea     rbp, [rsp-37h]
0x1801c5fcd  sub     rsp, 90h
0x1801c5fd4  mov     rbx, rcx
0x1801c5fd7  lea     rsi, [rcx+1B8h]
0x1801c5fde  mov     rcx, rsi
0x1801c5fe1  call    CDPCreateLoggedOnUserChangedNotifier
0x1801c5fe6  mov     edi, eax
0x1801c5fe8  test    eax, eax
0x1801c5fea  jns     short loc_1801C6069
0x1801c5fec  lea     rcx, aDiscovererbase; "..\\discovererbase.cpp"
0x1801c5ff3  mov     [rbp+57h+var_80], rcx
0x1801c5ff7  mov     dword ptr [rbp+57h+var_78], 23h ; '#'
0x1801c5ffe  mov     [rbp+57h+arg_0], eax
0x1801c6001  call    cs:__imp_GetCurrentThreadId
0x1801c6007  mov     ecx, eax
0x1801c6009  mov     [rbp+57h+arg_8], rcx
0x1801c600d  lea     rax, [rbp+57h+arg_8]
0x1801c6011  mov     [rsp+0B0h+var_88], rax
0x1801c6016  lea     rax, [rbp+57h+var_78]
0x1801c601a  mov     [rsp+0B0h+var_90], rax
0x1801c601f  lea     r9, [rbp+57h+var_80]
0x1801c6023  lea     r8, [rbp+57h+arg_0]
0x1801c6027  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1801c602e  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1801c6033  lea     rdx, [rbp+57h+var_80]
0x1801c6037  lea     rcx, [rbp+57h+var_70]
0x1801c603b  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1801c6040  mov     r9, rax
0x1801c6043  mov     ecx, edi
0x1801c6045  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1801c604a  mov     r8, rax
0x1801c604d  mov     edx, edi
0x1801c604f  lea     rcx, [rbp+57h+pExceptionObject]
0x1801c6053  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1801c6058  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1801c605f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1801c6063  call    _CxxThrowException_0
0x1801c6069  lea     r14, [rbx+88h]
0x1801c6070  lea     rdx, [rbp+57h+var_80]
0x1801c6074  mov     rcx, r14
0x1801c6077  call    ?shared_from_this@?$enable_shared_from_this@VDiscovererBase@cdp@@@std@@QEAA?AV?$shared_ptr@VDiscovererBase@cdp@@@2@XZ; std::enable_shared_from_this<cdp::DiscovererBase>::shared_from_this(void)
0x1801c607c  mov     r15, rax
0x1801c607f  lea     rdi, [rbx+1D0h]
0x1801c6086  mov     rcx, [rdi]
0x1801c6089  mov     qword ptr [rdi], 0
0x1801c6090  test    rcx, rcx
0x1801c6093  jz      short loc_1801C60A2
0x1801c6095  mov     rdx, [rcx]
0x1801c6098  mov     rax, [rdx+10h]
0x1801c609c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c60a1  nop
0x1801c60a2  mov     rdx, r15
0x1801c60a5  mov     rcx, rdi
0x1801c60a8  call    ??$MakeAndInitialize@VCDPLoggedOnUserCallback@DiscovererBase@cdp@@V123@V?$shared_ptr@VDiscovererBase@cdp@@@std@@@Details@WRL@Microsoft@@YAJPEAPEAVCDPLoggedOnUserCallback@DiscovererBase@cdp@@$$QEAV?$shared_ptr@VDiscovererBase@cdp@@@std@@@Z; Microsoft::WRL::Details::MakeAndInitialize<cdp::DiscovererBase::CDPLoggedOnUserCallback,cdp::DiscovererBase::CDPLoggedOnUserCallback,std::shared_ptr<cdp::DiscovererBase>>(cdp::DiscovererBase::CDPLoggedOnUserCallback * *,std::shared_ptr<cdp::DiscovererBase> &&)
0x1801c60ad  mov     r10, [rbp+5Fh]
0x1801c60b1  test    eax, eax
0x1801c60b3  jns     short loc_1801C60CD
0x1801c60b5  mov     r9d, eax; char *
0x1801c60b8  lea     r8, aDiscovererbase; "..\\discovererbase.cpp"
0x1801c60bf  mov     edx, 24h ; '$'; void *
0x1801c60c4  mov     rcx, r10; this
0x1801c60c7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1801c60cd  mov     rcx, [rbp+57h+var_78]; this
0x1801c60d1  test    rcx, rcx
0x1801c60d4  jz      short loc_1801C60DB
0x1801c60d6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801c60db  mov     rcx, [rsi]
0x1801c60de  mov     rax, [rcx]
0x1801c60e1  lea     r8, [rbx+1D8h]
0x1801c60e8  mov     rdx, [rdi]
0x1801c60eb  mov     rax, [rax+20h]
0x1801c60ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c60f4  mov     edi, eax
0x1801c60f6  test    eax, eax
0x1801c60f8  jns     short loc_1801C6177
0x1801c60fa  lea     rcx, aDiscovererbase; "..\\discovererbase.cpp"
0x1801c6101  mov     [rbp+57h+var_80], rcx
0x1801c6105  mov     dword ptr [rbp+57h+var_78], 25h ; '%'
0x1801c610c  mov     [rbp+57h+arg_0], eax
0x1801c610f  call    cs:__imp_GetCurrentThreadId
0x1801c6115  mov     ecx, eax
0x1801c6117  mov     [rbp+57h+arg_8], rcx
0x1801c611b  lea     rax, [rbp+57h+arg_8]
0x1801c611f  mov     [rsp+0B0h+var_88], rax
0x1801c6124  lea     rax, [rbp+57h+var_78]
0x1801c6128  mov     [rsp+0B0h+var_90], rax
0x1801c612d  lea     r9, [rbp+57h+var_80]
0x1801c6131  lea     r8, [rbp+57h+arg_0]
0x1801c6135  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1801c613c  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1801c6141  lea     rdx, [rbp+57h+var_80]
0x1801c6145  lea     rcx, [rbp+57h+var_70]
0x1801c6149  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1801c614e  mov     r9, rax
0x1801c6151  mov     ecx, edi
0x1801c6153  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1801c6158  mov     r8, rax
0x1801c615b  mov     edx, edi
0x1801c615d  lea     rcx, [rbp+57h+pExceptionObject]
0x1801c6161  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1801c6166  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1801c616d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1801c6171  call    _CxxThrowException_0
0x1801c6177  lea     rsi, [rbx+1C0h]
0x1801c617e  mov     rcx, rsi
0x1801c6181  call    CDPCreateLoggedOnUserFamilyChangedNotifier
0x1801c6186  mov     edi, eax
0x1801c6188  test    eax, eax
0x1801c618a  jns     short loc_1801C6209
0x1801c618c  lea     rcx, aDiscovererbase; "..\\discovererbase.cpp"
0x1801c6193  mov     [rbp+57h+var_80], rcx
0x1801c6197  mov     dword ptr [rbp+57h+var_78], 27h ; '''
0x1801c619e  mov     [rbp+57h+arg_0], eax
0x1801c61a1  call    cs:__imp_GetCurrentThreadId
0x1801c61a7  mov     ecx, eax
0x1801c61a9  mov     [rbp+57h+arg_8], rcx
0x1801c61ad  lea     rax, [rbp+57h+arg_8]
0x1801c61b1  mov     [rsp+0B0h+var_88], rax
0x1801c61b6  lea     rax, [rbp+57h+var_78]
0x1801c61ba  mov     [rsp+0B0h+var_90], rax
0x1801c61bf  lea     r9, [rbp+57h+var_80]
0x1801c61c3  lea     r8, [rbp+57h+arg_0]
0x1801c61c7  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1801c61ce  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1801c61d3  lea     rdx, [rbp+57h+var_80]
0x1801c61d7  lea     rcx, [rbp+57h+var_70]
0x1801c61db  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1801c61e0  mov     r9, rax
0x1801c61e3  mov     ecx, edi
0x1801c61e5  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1801c61ea  mov     r8, rax
0x1801c61ed  mov     edx, edi
0x1801c61ef  lea     rcx, [rbp+57h+pExceptionObject]
0x1801c61f3  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1801c61f8  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1801c61ff  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1801c6203  call    _CxxThrowException_0
0x1801c6209  lea     rdx, [rbp+57h+var_80]
0x1801c620d  mov     rcx, r14
0x1801c6210  call    ?shared_from_this@?$enable_shared_from_this@VDiscovererBase@cdp@@@std@@QEAA?AV?$shared_ptr@VDiscovererBase@cdp@@@2@XZ; std::enable_shared_from_this<cdp::DiscovererBase>::shared_from_this(void)
0x1801c6215  mov     r14, rax
0x1801c6218  lea     rdi, [rbx+1C8h]
0x1801c621f  mov     rcx, [rdi]
0x1801c6222  mov     qword ptr [rdi], 0
0x1801c6229  test    rcx, rcx
0x1801c622c  jz      short loc_1801C623B
0x1801c622e  mov     rdx, [rcx]
0x1801c6231  mov     rax, [rdx+10h]
0x1801c6235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c623a  nop
0x1801c623b  mov     rdx, r14
0x1801c623e  mov     rcx, rdi
0x1801c6241  call    ??$MakeAndInitialize@VCDPLoggedOnUserSetFamilyInfoCallback@DiscovererBase@cdp@@V123@V?$shared_ptr@VDiscovererBase@cdp@@@std@@@Details@WRL@Microsoft@@YAJPEAPEAVCDPLoggedOnUserSetFamilyInfoCallback@DiscovererBase@cdp@@$$QEAV?$shared_ptr@VDiscovererBase@cdp@@@std@@@Z; Microsoft::WRL::Details::MakeAndInitialize<cdp::DiscovererBase::CDPLoggedOnUserSetFamilyInfoCallback,cdp::DiscovererBase::CDPLoggedOnUserSetFamilyInfoCallback,std::shared_ptr<cdp::DiscovererBase>>(cdp::DiscovererBase::CDPLoggedOnUserSetFamilyInfoCallback * *,std::shared_ptr<cdp::DiscovererBase> &&)
0x1801c6246  mov     r10, [rbp+5Fh]
0x1801c624a  test    eax, eax
0x1801c624c  jns     short loc_1801C6266
0x1801c624e  mov     r9d, eax; char *
0x1801c6251  lea     r8, aDiscovererbase; "..\\discovererbase.cpp"
0x1801c6258  mov     edx, 28h ; '('; void *
0x1801c625d  mov     rcx, r10; this
0x1801c6260  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1801c6266  mov     rcx, [rbp+57h+var_78]; this
0x1801c626a  test    rcx, rcx
0x1801c626d  jz      short loc_1801C6274
0x1801c626f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801c6274  mov     rcx, [rsi]
0x1801c6277  mov     rax, [rcx]
0x1801c627a  lea     r8, [rbx+1DCh]
0x1801c6281  mov     rdx, [rdi]
0x1801c6284  mov     rax, [rax+20h]
0x1801c6288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c628d  mov     ebx, eax
0x1801c628f  test    eax, eax
0x1801c6291  jns     short loc_1801C6310
0x1801c6293  lea     rcx, aDiscovererbase; "..\\discovererbase.cpp"
0x1801c629a  mov     [rbp+57h+var_80], rcx
0x1801c629e  mov     dword ptr [rbp+57h+var_78], 2Ah ; '*'
0x1801c62a5  mov     [rbp+57h+arg_0], eax
0x1801c62a8  call    cs:__imp_GetCurrentThreadId
0x1801c62ae  mov     ecx, eax
0x1801c62b0  mov     [rbp+57h+arg_8], rcx
0x1801c62b4  lea     rax, [rbp+57h+arg_8]
0x1801c62b8  mov     [rsp+0B0h+var_88], rax
0x1801c62bd  lea     rax, [rbp+57h+var_78]
0x1801c62c1  mov     [rsp+0B0h+var_90], rax
0x1801c62c6  lea     r9, [rbp+57h+var_80]
0x1801c62ca  lea     r8, [rbp+57h+arg_0]
0x1801c62ce  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1801c62d5  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1801c62da  lea     rdx, [rbp+57h+var_80]
0x1801c62de  lea     rcx, [rbp+57h+var_70]
0x1801c62e2  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1801c62e7  mov     r9, rax
0x1801c62ea  mov     ecx, ebx
0x1801c62ec  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1801c62f1  mov     r8, rax
0x1801c62f4  mov     edx, ebx
0x1801c62f6  lea     rcx, [rbp+57h+pExceptionObject]
0x1801c62fa  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1801c62ff  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1801c6306  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1801c630a  call    _CxxThrowException_0
0x1801c6310  mov     rbx, [rsp+0B0h+arg_10]
0x1801c6318  add     rsp, 90h
0x1801c631f  pop     r15
0x1801c6321  pop     r14
0x1801c6323  pop     rdi
0x1801c6324  pop     rsi
0x1801c6325  pop     rbp
0x1801c6326  retn
```
