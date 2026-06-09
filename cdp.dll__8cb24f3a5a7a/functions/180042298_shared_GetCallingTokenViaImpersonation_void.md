# shared::GetCallingTokenViaImpersonation(void)

- ea: `0x180042298`
- end: `0x18004251d`
- name: `?GetCallingTokenViaImpersonation@shared@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ`
- size: `645`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800420c4`
- `0x1800ec360`

## callees

- `0x180042298`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800df1dc`
- `0x180101ac4`
- `0x180102d00`
- `0x180143248`
- `0x1801fcb36`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180042465`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180042465`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800423aa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800423aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180042454`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180042454`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800422fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800423e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004249d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800422fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800423e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004249d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180042395`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180042395`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800423b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042473`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800423b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042473`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800422c4`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800422c4`

## string_xrefs

- `0x180042322`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180042408`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800424c3`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
PHANDLE __fastcall shared::GetCallingTokenViaImpersonation(PHANDLE TokenHandle)
{
  HRESULT v2; // edi
  int v3; // ecx
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rax
  HANDLE CurrentThread; // rax
  signed int v9; // eax
  unsigned int v10; // ebx
  int v11; // ecx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rax
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v18; // ebx
  int v19; // ecx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rax
  const char *v25; // [rsp+38h] [rbp-41h] BYREF
  _DWORD v26[4]; // [rsp+40h] [rbp-39h] BYREF
  const char *v27; // [rsp+50h] [rbp-29h] BYREF
  int v28; // [rsp+58h] [rbp-21h] BYREF
  HRESULT *v29; // [rsp+60h] [rbp-19h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+68h] [rbp-11h] BYREF
  _BYTE v31[48]; // [rsp+A0h] [rbp+27h] BYREF
  unsigned int v32; // [rsp+E8h] [rbp+6Fh] BYREF
  HRESULT v33; // [rsp+F0h] [rbp+77h] BYREF
  __int64 CurrentThreadId; // [rsp+F8h] [rbp+7Fh] BYREF

  *TokenHandle = 0;
  v2 = CoImpersonateClient();
  v33 = v2;
  if ( (int)(v2 + 0x80000000) >= 0 && v2 != -2147417833 )
  {
    v27 = ".\\platformshared.cpp";
    v28 = 355;
    v32 = v2;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v3,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v32,
      (unsigned int)&v27,
      (__int64)&v28,
      (__int64)&CurrentThreadId);
    v4 = cdp::ExceptionStackFromSourceLocationInfo(&v25, &v27);
    v7 = cdp::ErrorCodeToString((unsigned int)v2, v5, v6, v4);
    ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v2, v7);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v29 = &v33;
  v27 = (const char *)&v29;
  if ( v2 < 0 )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      TokenHandle,
      0);
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, TokenHandle) )
    {
      LastError = GetLastError();
      v18 = LastError;
      if ( LastError > 0 )
        v18 = (unsigned __int16)LastError | 0x80070000;
      v25 = ".\\platformshared.cpp";
      v26[0] = 377;
      v32 = v18;
      CurrentThreadId = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v19,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v32,
        (unsigned int)&v25,
        (__int64)v26,
        (__int64)&CurrentThreadId);
      v20 = cdp::ExceptionStackFromSourceLocationInfo(v31, &v25);
      v23 = cdp::ErrorCodeToString(v18, v21, v22, v20);
      ConnectedDevices::Exception::Exception(pExceptionObject, v18, v23);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
  }
  else
  {
    if ( (char *)*TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*TokenHandle);
    *TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, TokenHandle) )
    {
      v9 = GetLastError();
      v10 = v9;
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      v25 = ".\\platformshared.cpp";
      v26[0] = 368;
      v32 = v10;
      CurrentThreadId = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v11,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v32,
        (unsigned int)&v25,
        (__int64)v26,
        (__int64)&CurrentThreadId);
      v12 = cdp::ExceptionStackFromSourceLocationInfo(v31, &v25);
      v15 = cdp::ErrorCodeToString(v10, v13, v14, v12);
      ConnectedDevices::Exception::Exception(pExceptionObject, v10, v15);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
  }
  ScopeWarden__lambda_64090bc2e00f2c074a72f014dd27c79f___::_ScopeWarden__lambda_64090bc2e00f2c074a72f014dd27c79f___(&v27);
  return TokenHandle;
}

```

## disassembly

```asm
0x180042298  mov     [rsp-8+arg_0], rcx
0x18004229d  push    rbp
0x18004229e  push    rbx
0x18004229f  push    rdi
0x1800422a0  lea     rbp, [rsp-47h]
0x1800422a5  sub     rsp, 0C0h
0x1800422ac  mov     rbx, rcx
0x1800422af  mov     [rbp+57h+var_A0], 0
0x1800422b6  mov     qword ptr [rcx], 0
0x1800422bd  mov     [rbp+57h+var_A0], 1
0x1800422c4  call    cs:__imp_CoImpersonateClient
0x1800422ca  mov     edi, eax
0x1800422cc  mov     [rbp+57h+arg_10], eax
0x1800422cf  mov     eax, 80000000h
0x1800422d4  lea     ecx, [rdi+rax]
0x1800422d7  test    eax, ecx
0x1800422d9  jnz     loc_180042364
0x1800422df  cmp     edi, 80010117h
0x1800422e5  jz      short loc_180042364
0x1800422e7  lea     rax, aPlatformshared; ".\\platformshared.cpp"
0x1800422ee  mov     [rbp+57h+var_80], rax
0x1800422f2  mov     [rbp+57h+var_78], 163h
0x1800422f9  mov     [rbp+57h+arg_8], edi
0x1800422fc  call    cs:__imp_GetCurrentThreadId
0x180042302  mov     eax, eax
0x180042304  mov     [rbp+57h+arg_18], rax
0x180042308  lea     rax, [rbp+57h+arg_18]
0x18004230c  mov     [rsp+0D0h+var_A8], rax
0x180042311  lea     rax, [rbp+57h+var_78]
0x180042315  mov     [rsp+0D0h+var_B0], rax
0x18004231a  lea     r9, [rbp+57h+var_80]
0x18004231e  lea     r8, [rbp+57h+arg_8]
0x180042322  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180042329  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18004232e  lea     rdx, [rbp+57h+var_80]
0x180042332  lea     rcx, [rbp+57h+var_98]
0x180042336  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18004233b  mov     r9, rax
0x18004233e  mov     ecx, edi
0x180042340  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180042345  mov     r8, rax
0x180042348  mov     edx, edi
0x18004234a  lea     rcx, [rbp+57h+pExceptionObject]
0x18004234e  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180042353  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18004235a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004235e  call    _CxxThrowException_0
0x180042364  lea     rax, [rbp+57h+arg_10]
0x180042368  mov     [rbp+57h+var_70], rax
0x18004236c  lea     rax, [rbp+57h+var_70]
0x180042370  mov     [rbp+57h+var_80], rax
0x180042374  test    edi, edi
0x180042376  js      loc_18004244A
0x18004237c  mov     rcx, [rbx]; hObject
0x18004237f  lea     rax, [rcx-1]
0x180042383  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180042387  ja      short loc_18004238E
0x180042389  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18004238e  mov     qword ptr [rbx], 0
0x180042395  call    cs:__imp_GetCurrentThread
0x18004239b  mov     r9, rbx; TokenHandle
0x18004239e  mov     edx, 8; DesiredAccess
0x1800423a3  lea     r8d, [rdx-7]; OpenAsSelf
0x1800423a7  mov     rcx, rax; ThreadHandle
0x1800423aa  call    cs:__imp_OpenThreadToken
0x1800423b0  test    eax, eax
0x1800423b2  jnz     loc_180042505
0x1800423b8  call    cs:__imp_GetLastError
0x1800423be  mov     ebx, eax
0x1800423c0  test    eax, eax
0x1800423c2  jle     short loc_1800423CD
0x1800423c4  movzx   ebx, ax
0x1800423c7  or      ebx, 80070000h
0x1800423cd  lea     rax, aPlatformshared; ".\\platformshared.cpp"
0x1800423d4  mov     [rbp+57h+var_98], rax
0x1800423d8  mov     [rbp+57h+var_90], 170h
0x1800423df  mov     [rbp+57h+arg_8], ebx
0x1800423e2  call    cs:__imp_GetCurrentThreadId
0x1800423e8  mov     eax, eax
0x1800423ea  mov     [rbp+57h+arg_18], rax
0x1800423ee  lea     rax, [rbp+57h+arg_18]
0x1800423f2  mov     [rsp+0D0h+var_A8], rax
0x1800423f7  lea     rax, [rbp+57h+var_90]
0x1800423fb  mov     [rsp+0D0h+var_B0], rax
0x180042400  lea     r9, [rbp+57h+var_98]
0x180042404  lea     r8, [rbp+57h+arg_8]
0x180042408  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18004240f  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180042414  lea     rdx, [rbp+57h+var_98]
0x180042418  lea     rcx, [rbp+57h+var_30]
0x18004241c  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180042421  mov     r9, rax
0x180042424  mov     ecx, ebx
0x180042426  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18004242b  mov     r8, rax
0x18004242e  mov     edx, ebx
0x180042430  lea     rcx, [rbp+57h+pExceptionObject]
0x180042434  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180042439  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180042440  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180042444  call    _CxxThrowException_0
0x18004244a  xor     edx, edx
0x18004244c  mov     rcx, rbx
0x18004244f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180042454  call    cs:__imp_GetCurrentProcess
0x18004245a  mov     r8, rbx; TokenHandle
0x18004245d  mov     edx, 8; DesiredAccess
0x180042462  mov     rcx, rax; ProcessHandle
0x180042465  call    cs:__imp_OpenProcessToken
0x18004246b  test    eax, eax
0x18004246d  jnz     loc_180042505
0x180042473  call    cs:__imp_GetLastError
0x180042479  mov     ebx, eax
0x18004247b  test    eax, eax
0x18004247d  jle     short loc_180042488
0x18004247f  movzx   ebx, ax
0x180042482  or      ebx, 80070000h
0x180042488  lea     rax, aPlatformshared; ".\\platformshared.cpp"
0x18004248f  mov     [rbp+57h+var_98], rax
0x180042493  mov     [rbp+57h+var_90], 179h
0x18004249a  mov     [rbp+57h+arg_8], ebx
0x18004249d  call    cs:__imp_GetCurrentThreadId
0x1800424a3  mov     eax, eax
0x1800424a5  mov     [rbp+57h+arg_18], rax
0x1800424a9  lea     rax, [rbp+57h+arg_18]
0x1800424ad  mov     [rsp+0D0h+var_A8], rax
0x1800424b2  lea     rax, [rbp+57h+var_90]
0x1800424b6  mov     [rsp+0D0h+var_B0], rax
0x1800424bb  lea     r9, [rbp+57h+var_98]
0x1800424bf  lea     r8, [rbp+57h+arg_8]
0x1800424c3  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800424ca  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800424cf  lea     rdx, [rbp+57h+var_98]
0x1800424d3  lea     rcx, [rbp+57h+var_30]
0x1800424d7  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800424dc  mov     r9, rax
0x1800424df  mov     ecx, ebx
0x1800424e1  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800424e6  mov     r8, rax
0x1800424e9  mov     edx, ebx
0x1800424eb  lea     rcx, [rbp+57h+pExceptionObject]
0x1800424ef  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800424f4  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800424fb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800424ff  call    _CxxThrowException_0
0x180042505  lea     rcx, [rbp+57h+var_80]
0x180042509  call    ScopeWarden__lambda_64090bc2e00f2c074a72f014dd27c79f______ScopeWarden__lambda_64090bc2e00f2c074a72f014dd27c79f___
0x18004250e  mov     rax, rbx
0x180042511  add     rsp, 0C0h
0x180042518  pop     rdi
0x180042519  pop     rbx
0x18004251a  pop     rbp
0x18004251b  retn
```
