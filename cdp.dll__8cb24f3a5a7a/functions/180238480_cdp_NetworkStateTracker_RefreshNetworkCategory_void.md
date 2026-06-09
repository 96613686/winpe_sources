# cdp::NetworkStateTracker::RefreshNetworkCategory(void)

- ea: `0x180238480`
- end: `0x180238940`
- name: `?RefreshNetworkCategory@NetworkStateTracker@cdp@@UEAAXXZ`
- size: `1216`
- prototype: `void __fastcall(cdp::NetworkStateTracker *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800110f8`
- `0x18001ce80`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x180143248`
- `0x1801fcb36`
- `0x180238480`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802384f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180238582`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18023862c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802386bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180238765`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802387f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18023888e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802384f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180238582`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18023862c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802386bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180238765`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802387f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18023888e`
- `msvcp_win!_Mtx_unlock` at `0x18023892c`
- `msvcp_win!_Mtx_unlock` at `0x18023892c`

## string_xrefs

- `0x180238519`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1802385a8`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180238652`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1802386e1`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18023878b`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18023881a`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1802388b4`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall cdp::NetworkStateTracker::RefreshNetworkCategory(cdp::NetworkStateTracker *this)
{
  struct _Mtx_internal_imp_t *v2; // r14
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, __int64 *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rax
  __int64 v12; // rbx
  int v13; // ecx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rax
  __int64 (__fastcall *v18)(__int64, __int64 *); // rdi
  int v19; // eax
  unsigned int v20; // ebx
  DWORD v21; // eax
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rax
  __int64 v26; // rbx
  int v27; // ecx
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rax
  __int64 (__fastcall *v32)(__int64, __int64 *); // rdi
  int v33; // eax
  unsigned int v34; // ebx
  DWORD v35; // eax
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rax
  int v40; // ecx
  __int64 v41; // rax
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // rax
  int v45; // eax
  unsigned int v46; // ebx
  DWORD v47; // eax
  __int64 v48; // rax
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // rax
  int v52; // eax
  const char *v53; // [rsp+30h] [rbp-49h] BYREF
  int v54; // [rsp+38h] [rbp-41h] BYREF
  __int64 v55; // [rsp+40h] [rbp-39h] BYREF
  __int64 v56; // [rsp+48h] [rbp-31h] BYREF
  _BYTE v57[24]; // [rsp+50h] [rbp-29h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+68h] [rbp-11h] BYREF
  char *v59; // [rsp+A0h] [rbp+27h]
  int v60; // [rsp+E0h] [rbp+67h] BYREF
  int v61; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 v62; // [rsp+F0h] [rbp+77h] BYREF
  __int64 v63; // [rsp+F8h] [rbp+7Fh] BYREF

  v2 = (cdp::NetworkStateTracker *)((char *)this + 160);
  v59 = (char *)this + 160;
  std::_Mutex_base::lock((cdp::NetworkStateTracker *)((char *)this + 160));
  v56 = 0;
  v3 = *((_QWORD *)this + 31);
  v4 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 56LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
  v5 = v4(v3, &v56);
  v6 = v5;
  if ( v5 < 0 )
  {
    v53 = ".\\networkstatetracker.cpp";
    v54 = 108;
    v61 = v5;
    CurrentThreadId = GetCurrentThreadId();
    v55 = CurrentThreadId;
    Log<long &,char const * &,int &,unsigned __int64>(
      CurrentThreadId,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v61,
      (unsigned int)&v53,
      (__int64)&v54,
      (__int64)&v55);
    v8 = cdp::ExceptionStackFromSourceLocationInfo(v57, &v53);
    v11 = cdp::ErrorCodeToString(v6, v9, v10, v8);
    ConnectedDevices::Exception::Exception(pExceptionObject, v6, v11);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v12 = v56;
  if ( !v56 )
  {
    v53 = ".\\networkstatetracker.cpp";
    v54 = 109;
    v61 = -2147467261;
    v55 = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v13,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v61,
      (unsigned int)&v53,
      (__int64)&v54,
      (__int64)&v55);
    v14 = cdp::ExceptionStackFromSourceLocationInfo(v57, &v53);
    v17 = cdp::ErrorCodeToString(2147500035LL, v15, v16, v14);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147500035LL, v17);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v63 = 0;
  v18 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v56 + 88LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
  v19 = v18(v12, &v63);
  v20 = v19;
  if ( v19 < 0 )
  {
    v53 = ".\\networkstatetracker.cpp";
    v54 = 113;
    v61 = v19;
    v21 = GetCurrentThreadId();
    v55 = v21;
    Log<long &,char const * &,int &,unsigned __int64>(
      v21,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v61,
      (unsigned int)&v53,
      (__int64)&v54,
      (__int64)&v55);
    v22 = cdp::ExceptionStackFromSourceLocationInfo(v57, &v53);
    v25 = cdp::ErrorCodeToString(v20, v23, v24, v22);
    ConnectedDevices::Exception::Exception(pExceptionObject, v20, v25);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v26 = v63;
  if ( !v63 )
  {
    v53 = ".\\networkstatetracker.cpp";
    v54 = 114;
    v61 = -2147467261;
    v55 = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v27,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v61,
      (unsigned int)&v53,
      (__int64)&v54,
      (__int64)&v55);
    v28 = cdp::ExceptionStackFromSourceLocationInfo(v57, &v53);
    v31 = cdp::ErrorCodeToString(2147500035LL, v29, v30, v28);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147500035LL, v31);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v62 = 0;
  v32 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v63 + 72LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v62);
  v33 = v32(v26, &v62);
  v34 = v33;
  if ( v33 < 0 )
  {
    v53 = ".\\networkstatetracker.cpp";
    v54 = 118;
    v61 = v33;
    v35 = GetCurrentThreadId();
    v55 = v35;
    Log<long &,char const * &,int &,unsigned __int64>(
      v35,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v61,
      (unsigned int)&v53,
      (__int64)&v54,
      (__int64)&v55);
    v36 = cdp::ExceptionStackFromSourceLocationInfo(v57, &v53);
    v39 = cdp::ErrorCodeToString(v34, v37, v38, v36);
    ConnectedDevices::Exception::Exception(pExceptionObject, v34, v39);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  if ( !v62 )
  {
    v53 = ".\\networkstatetracker.cpp";
    v54 = 119;
    v61 = -2147467261;
    v55 = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v40,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v61,
      (unsigned int)&v53,
      (__int64)&v54,
      (__int64)&v55);
    v41 = cdp::ExceptionStackFromSourceLocationInfo(v57, &v53);
    v44 = cdp::ErrorCodeToString(2147500035LL, v42, v43, v41);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147500035LL, v44);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v60 = 0;
  v45 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v62 + 56LL))(v62, &v60);
  v46 = v45;
  if ( v45 < 0 )
  {
    v53 = ".\\networkstatetracker.cpp";
    v54 = 123;
    v61 = v45;
    v47 = GetCurrentThreadId();
    v55 = v47;
    Log<long &,char const * &,int &,unsigned __int64>(
      v47,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v61,
      (unsigned int)&v53,
      (__int64)&v54,
      (__int64)&v55);
    v48 = cdp::ExceptionStackFromSourceLocationInfo(v57, &v53);
    v51 = cdp::ErrorCodeToString(v46, v49, v50, v48);
    ConnectedDevices::Exception::Exception(pExceptionObject, v46, v51);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v52 = v60 & 1;
  if ( (v60 & 2) != 0 )
    v52 |= 2u;
  *((_DWORD *)this + 60) = v52;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v62);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
  _Mtx_unlock(v2);
}

```

## disassembly

```asm
0x180238480  push    rbp
0x180238482  push    rbx
0x180238483  push    rsi
0x180238484  push    rdi
0x180238485  push    r14
0x180238487  lea     rbp, [rsp-37h]
0x18023848c  sub     rsp, 0B0h
0x180238493  mov     rsi, rcx
0x180238496  lea     r14, [rcx+0A0h]
0x18023849d  mov     [rbp+57h+var_30], r14
0x1802384a1  mov     rcx, r14; this
0x1802384a4  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1802384a9  nop
0x1802384aa  mov     [rbp+57h+var_88], 0
0x1802384b2  mov     rdi, [rsi+0F8h]
0x1802384b9  mov     rax, [rdi]
0x1802384bc  mov     rbx, [rax+38h]
0x1802384c0  lea     rcx, [rbp+57h+var_88]
0x1802384c4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1802384c9  lea     rdx, [rbp+57h+var_88]
0x1802384cd  mov     rcx, rdi
0x1802384d0  mov     rax, rbx
0x1802384d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802384d8  mov     ebx, eax
0x1802384da  test    eax, eax
0x1802384dc  jns     short loc_18023855B
0x1802384de  lea     rcx, aNetworkstatetr; ".\\networkstatetracker.cpp"
0x1802384e5  mov     [rbp+57h+var_A0], rcx
0x1802384e9  mov     [rbp+57h+var_98], 6Ch ; 'l'
0x1802384f0  mov     [rbp+57h+arg_8], eax
0x1802384f3  call    cs:__imp_GetCurrentThreadId
0x1802384f9  mov     ecx, eax
0x1802384fb  mov     [rbp+57h+var_90], rcx
0x1802384ff  lea     rax, [rbp+57h+var_90]
0x180238503  mov     [rsp+0D0h+var_A8], rax
0x180238508  lea     rax, [rbp+57h+var_98]
0x18023850c  mov     [rsp+0D0h+var_B0], rax
0x180238511  lea     r9, [rbp+57h+var_A0]
0x180238515  lea     r8, [rbp+57h+arg_8]
0x180238519  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180238520  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180238525  lea     rdx, [rbp+57h+var_A0]
0x180238529  lea     rcx, [rbp+57h+var_80]
0x18023852d  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180238532  mov     r9, rax
0x180238535  mov     ecx, ebx
0x180238537  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18023853c  mov     r8, rax
0x18023853f  mov     edx, ebx
0x180238541  lea     rcx, [rbp+57h+pExceptionObject]
0x180238545  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18023854a  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180238551  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180238555  call    _CxxThrowException_0
0x18023855b  mov     rbx, [rbp+57h+var_88]
0x18023855f  test    rbx, rbx
0x180238562  jnz     loc_1802385EA
0x180238568  lea     rcx, aNetworkstatetr; ".\\networkstatetracker.cpp"
0x18023856f  mov     [rbp+57h+var_A0], rcx
0x180238573  mov     [rbp+57h+var_98], 6Dh ; 'm'
0x18023857a  mov     ebx, 80004003h
0x18023857f  mov     [rbp+57h+arg_8], ebx
0x180238582  call    cs:__imp_GetCurrentThreadId
0x180238588  mov     eax, eax
0x18023858a  mov     [rbp+57h+var_90], rax
0x18023858e  lea     rax, [rbp+57h+var_90]
0x180238592  mov     [rsp+0D0h+var_A8], rax
0x180238597  lea     rax, [rbp+57h+var_98]
0x18023859b  mov     [rsp+0D0h+var_B0], rax
0x1802385a0  lea     r9, [rbp+57h+var_A0]
0x1802385a4  lea     r8, [rbp+57h+arg_8]
0x1802385a8  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1802385af  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1802385b4  lea     rdx, [rbp+57h+var_A0]
0x1802385b8  lea     rcx, [rbp+57h+var_80]
0x1802385bc  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1802385c1  mov     r9, rax
0x1802385c4  mov     ecx, ebx
0x1802385c6  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1802385cb  mov     r8, rax
0x1802385ce  mov     edx, ebx
0x1802385d0  lea     rcx, [rbp+57h+pExceptionObject]
0x1802385d4  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1802385d9  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1802385e0  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1802385e4  call    _CxxThrowException_0
0x1802385ea  mov     [rbp+57h+arg_18], 0
0x1802385f2  mov     rax, [rbx]
0x1802385f5  mov     rdi, [rax+58h]
0x1802385f9  lea     rcx, [rbp+57h+arg_18]
0x1802385fd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180238602  lea     rdx, [rbp+57h+arg_18]
0x180238606  mov     rcx, rbx
0x180238609  mov     rax, rdi
0x18023860c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180238611  mov     ebx, eax
0x180238613  test    eax, eax
0x180238615  jns     short loc_180238694
0x180238617  lea     rcx, aNetworkstatetr; ".\\networkstatetracker.cpp"
0x18023861e  mov     [rbp+57h+var_A0], rcx
0x180238622  mov     [rbp+57h+var_98], 71h ; 'q'
0x180238629  mov     [rbp+57h+arg_8], eax
0x18023862c  call    cs:__imp_GetCurrentThreadId
0x180238632  mov     ecx, eax
0x180238634  mov     [rbp+57h+var_90], rcx
0x180238638  lea     rax, [rbp+57h+var_90]
0x18023863c  mov     [rsp+0D0h+var_A8], rax
0x180238641  lea     rax, [rbp+57h+var_98]
0x180238645  mov     [rsp+0D0h+var_B0], rax
0x18023864a  lea     r9, [rbp+57h+var_A0]
0x18023864e  lea     r8, [rbp+57h+arg_8]
0x180238652  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180238659  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18023865e  lea     rdx, [rbp+57h+var_A0]
0x180238662  lea     rcx, [rbp+57h+var_80]
0x180238666  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18023866b  mov     r9, rax
0x18023866e  mov     ecx, ebx
0x180238670  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180238675  mov     r8, rax
0x180238678  mov     edx, ebx
0x18023867a  lea     rcx, [rbp+57h+pExceptionObject]
0x18023867e  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180238683  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18023868a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18023868e  call    _CxxThrowException_0
0x180238694  mov     rbx, [rbp+57h+arg_18]
0x180238698  test    rbx, rbx
0x18023869b  jnz     loc_180238723
0x1802386a1  lea     rcx, aNetworkstatetr; ".\\networkstatetracker.cpp"
0x1802386a8  mov     [rbp+57h+var_A0], rcx
0x1802386ac  mov     [rbp+57h+var_98], 72h ; 'r'
0x1802386b3  mov     ebx, 80004003h
0x1802386b8  mov     [rbp+57h+arg_8], ebx
0x1802386bb  call    cs:__imp_GetCurrentThreadId
0x1802386c1  mov     eax, eax
0x1802386c3  mov     [rbp+57h+var_90], rax
0x1802386c7  lea     rax, [rbp+57h+var_90]
0x1802386cb  mov     [rsp+0D0h+var_A8], rax
0x1802386d0  lea     rax, [rbp+57h+var_98]
0x1802386d4  mov     [rsp+0D0h+var_B0], rax
0x1802386d9  lea     r9, [rbp+57h+var_A0]
0x1802386dd  lea     r8, [rbp+57h+arg_8]
0x1802386e1  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1802386e8  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1802386ed  lea     rdx, [rbp+57h+var_A0]
0x1802386f1  lea     rcx, [rbp+57h+var_80]
0x1802386f5  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1802386fa  mov     r9, rax
0x1802386fd  mov     ecx, ebx
0x1802386ff  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180238704  mov     r8, rax
0x180238707  mov     edx, ebx
0x180238709  lea     rcx, [rbp+57h+pExceptionObject]
0x18023870d  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180238712  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180238719  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18023871d  call    _CxxThrowException_0
0x180238723  mov     [rbp+57h+arg_10], 0
0x18023872b  mov     rax, [rbx]
0x18023872e  mov     rdi, [rax+48h]
0x180238732  lea     rcx, [rbp+57h+arg_10]
0x180238736  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18023873b  lea     rdx, [rbp+57h+arg_10]
0x18023873f  mov     rcx, rbx
0x180238742  mov     rax, rdi
0x180238745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023874a  mov     ebx, eax
0x18023874c  test    eax, eax
0x18023874e  jns     short loc_1802387CD
0x180238750  lea     rcx, aNetworkstatetr; ".\\networkstatetracker.cpp"
0x180238757  mov     [rbp+57h+var_A0], rcx
0x18023875b  mov     [rbp+57h+var_98], 76h ; 'v'
0x180238762  mov     [rbp+57h+arg_8], eax
0x180238765  call    cs:__imp_GetCurrentThreadId
0x18023876b  mov     ecx, eax
0x18023876d  mov     [rbp+57h+var_90], rcx
0x180238771  lea     rax, [rbp+57h+var_90]
0x180238775  mov     [rsp+0D0h+var_A8], rax
0x18023877a  lea     rax, [rbp+57h+var_98]
0x18023877e  mov     [rsp+0D0h+var_B0], rax
0x180238783  lea     r9, [rbp+57h+var_A0]
0x180238787  lea     r8, [rbp+57h+arg_8]
0x18023878b  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180238792  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180238797  lea     rdx, [rbp+57h+var_A0]
0x18023879b  lea     rcx, [rbp+57h+var_80]
0x18023879f  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1802387a4  mov     r9, rax
0x1802387a7  mov     ecx, ebx
0x1802387a9  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1802387ae  mov     r8, rax
0x1802387b1  mov     edx, ebx
0x1802387b3  lea     rcx, [rbp+57h+pExceptionObject]
0x1802387b7  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1802387bc  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1802387c3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1802387c7  call    _CxxThrowException_0
0x1802387cd  mov     rcx, [rbp+57h+arg_10]
0x1802387d1  test    rcx, rcx
0x1802387d4  jnz     loc_18023885C
0x1802387da  lea     rcx, aNetworkstatetr; ".\\networkstatetracker.cpp"
0x1802387e1  mov     [rbp+57h+var_A0], rcx
0x1802387e5  mov     [rbp+57h+var_98], 77h ; 'w'
0x1802387ec  mov     ebx, 80004003h
0x1802387f1  mov     [rbp+57h+arg_8], ebx
0x1802387f4  call    cs:__imp_GetCurrentThreadId
0x1802387fa  mov     eax, eax
0x1802387fc  mov     [rbp+57h+var_90], rax
0x180238800  lea     rax, [rbp+57h+var_90]
0x180238804  mov     [rsp+0D0h+var_A8], rax
0x180238809  lea     rax, [rbp+57h+var_98]
0x18023880d  mov     [rsp+0D0h+var_B0], rax
0x180238812  lea     r9, [rbp+57h+var_A0]
0x180238816  lea     r8, [rbp+57h+arg_8]
0x18023881a  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180238821  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180238826  lea     rdx, [rbp+57h+var_A0]
0x18023882a  lea     rcx, [rbp+57h+var_80]
0x18023882e  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180238833  mov     r9, rax
0x180238836  mov     ecx, ebx
0x180238838  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18023883d  mov     r8, rax
0x180238840  mov     edx, ebx
0x180238842  lea     rcx, [rbp+57h+pExceptionObject]
0x180238846  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18023884b  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180238852  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180238856  call    _CxxThrowException_0
0x18023885c  mov     [rbp+57h+arg_0], 0
0x180238863  mov     rax, [rcx]
0x180238866  lea     rdx, [rbp+57h+arg_0]
0x18023886a  mov     rax, [rax+38h]
0x18023886e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180238873  mov     ebx, eax
0x180238875  test    eax, eax
0x180238877  jns     short loc_1802388F6
0x180238879  lea     rcx, aNetworkstatetr; ".\\networkstatetracker.cpp"
0x180238880  mov     [rbp+57h+var_A0], rcx
0x180238884  mov     [rbp+57h+var_98], 7Bh ; '{'
0x18023888b  mov     [rbp+57h+arg_8], eax
0x18023888e  call    cs:__imp_GetCurrentThreadId
0x180238894  mov     ecx, eax
0x180238896  mov     [rbp+57h+var_90], rcx
0x18023889a  lea     rax, [rbp+57h+var_90]
0x18023889e  mov     [rsp+0D0h+var_A8], rax
0x1802388a3  lea     rax, [rbp+57h+var_98]
0x1802388a7  mov     [rsp+0D0h+var_B0], rax
0x1802388ac  lea     r9, [rbp+57h+var_A0]
0x1802388b0  lea     r8, [rbp+57h+arg_8]
0x1802388b4  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1802388bb  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1802388c0  lea     rdx, [rbp+57h+var_A0]
0x1802388c4  lea     rcx, [rbp+57h+var_80]
0x1802388c8  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1802388cd  mov     r9, rax
0x1802388d0  mov     ecx, ebx
0x1802388d2  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1802388d7  mov     r8, rax
0x1802388da  mov     edx, ebx
0x1802388dc  lea     rcx, [rbp+57h+pExceptionObject]
0x1802388e0  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1802388e5  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1802388ec  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1802388f0  call    _CxxThrowException_0
0x1802388f6  mov     eax, [rbp+57h+arg_0]
0x1802388f9  and     eax, 1
0x1802388fc  test    byte ptr [rbp+57h+arg_0], 2
0x180238900  jz      short loc_180238905
0x180238902  or      eax, 2
0x180238905  mov     [rsi+0F0h], eax
0x18023890b  lea     rcx, [rbp+57h+arg_10]
0x18023890f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180238914  nop
0x180238915  lea     rcx, [rbp+57h+arg_18]
0x180238919  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18023891e  nop
0x18023891f  lea     rcx, [rbp+57h+var_88]
0x180238923  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180238928  nop
0x180238929  mov     rcx, r14; _Mtx_t
0x18023892c  call    cs:__imp__Mtx_unlock
0x180238932  add     rsp, 0B0h
0x180238939  pop     r14
0x18023893b  pop     rdi
0x18023893c  pop     rsi
0x18023893d  pop     rbx
0x18023893e  pop     rbp
0x18023893f  retn
```
