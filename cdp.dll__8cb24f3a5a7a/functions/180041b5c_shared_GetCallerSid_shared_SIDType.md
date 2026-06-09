# shared::GetCallerSid(shared::SIDType)

- ea: `0x180041b5c`
- end: `0x180041e56`
- name: `?GetCallerSid@shared@@YA?AV?$vector@EV?$allocator@E@std@@@std@@W4SIDType@1@@Z`
- size: `762`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180041880`
- `0x180092490`
- `0x1800ec200`

## callees

- `0x180041b5c`
- `0x180041e5c`
- `0x18008dbc0`
- `0x180094c90`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800df1dc`
- `0x1801026d4`
- `0x180102d00`
- `0x180143248`
- `0x1801fcb36`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180041d97`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180041d97`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180041bea`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180041bea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180041d85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180041d85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041c66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041cf3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041dee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041c66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041cf3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041dee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180041bd2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180041bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041c41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041cce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041c41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041cce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041db8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041db8`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180041b80`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180041b80`

## string_xrefs

- `0x180041c8c`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180041d19`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180041e14`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180041dc3`: `{"text":"Unable to decide how to get calling token."}`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall shared::GetCallerSid(_QWORD *a1, int a2)
{
  HRESULT v4; // eax
  HANDLE CurrentThread; // rax
  signed int v7; // eax
  unsigned int v8; // ebx
  int v9; // ecx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rax
  signed int LastError; // eax
  unsigned int v15; // ebx
  int v16; // ecx
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rax
  HANDLE CurrentProcess; // rax
  int v22; // ecx
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rax
  int v27; // [rsp+30h] [rbp-49h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-41h] BYREF
  const char *v29; // [rsp+40h] [rbp-39h] BYREF
  int v30; // [rsp+48h] [rbp-31h] BYREF
  __int64 CurrentThreadId; // [rsp+50h] [rbp-29h] BYREF
  _QWORD *v32; // [rsp+58h] [rbp-21h] BYREF
  _QWORD v33[2]; // [rsp+68h] [rbp-11h] BYREF
  _BYTE v34[24]; // [rsp+78h] [rbp-1h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+90h] [rbp+17h] BYREF
  bool v36; // [rsp+F0h] [rbp+77h] BYREF
  HRESULT v37; // [rsp+F8h] [rbp+7Fh] BYREF

  TokenHandle = 0;
  v4 = CoImpersonateClient();
  v37 = v4;
  v36 = v4 >= 0;
  v33[0] = &v36;
  v33[1] = &v37;
  v32 = v33;
  if ( v4 < 0 )
  {
    if ( v4 != -2147417833 )
    {
      Log<>(1, "{\"text\":\"Unable to decide how to get calling token.\"}");
      v29 = ".\\platformshared.cpp";
      v30 = 663;
      v27 = -2147418113;
      CurrentThreadId = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v22,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v27,
        (unsigned int)&v29,
        (__int64)&v30,
        (__int64)&CurrentThreadId);
      v23 = cdp::ExceptionStackFromSourceLocationInfo(v34, &v29);
      v26 = cdp::ErrorCodeToString(2147549183LL, v24, v25, v23);
      ConnectedDevices::Exception::Exception(pExceptionObject, 2147549183LL, v26);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
    {
      LastError = GetLastError();
      v15 = LastError;
      if ( LastError > 0 )
        v15 = (unsigned __int16)LastError | 0x80070000;
      v29 = ".\\platformshared.cpp";
      v30 = 657;
      v27 = v15;
      CurrentThreadId = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v16,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v27,
        (unsigned int)&v29,
        (__int64)&v30,
        (__int64)&CurrentThreadId);
      v17 = cdp::ExceptionStackFromSourceLocationInfo(v34, &v29);
      v20 = cdp::ErrorCodeToString(v15, v18, v19, v17);
      ConnectedDevices::Exception::Exception(pExceptionObject, v15, v20);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
  }
  else
  {
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(TokenHandle);
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
    {
      v7 = GetLastError();
      v8 = v7;
      if ( v7 > 0 )
        v8 = (unsigned __int16)v7 | 0x80070000;
      v29 = ".\\platformshared.cpp";
      v30 = 647;
      v27 = v8;
      CurrentThreadId = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v9,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v27,
        (unsigned int)&v29,
        (__int64)&v30,
        (__int64)&CurrentThreadId);
      v10 = cdp::ExceptionStackFromSourceLocationInfo(v34, &v29);
      v13 = cdp::ErrorCodeToString(v8, v11, v12, v10);
      ConnectedDevices::Exception::Exception(pExceptionObject, v8, v13);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
  }
  if ( a2 )
    shared::GetLogonSessionSidFromToken(a1, TokenHandle);
  else
    shared::GetUserSidFromToken(a1, TokenHandle);
  ScopeWarden__lambda_5aa063b9d9a6bbd28ff940b8a2c95ce9___::_ScopeWarden__lambda_5aa063b9d9a6bbd28ff940b8a2c95ce9___(&v32);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return a1;
}

```

## disassembly

```asm
0x180041b5c  mov     [rsp-8+arg_0], rbx
0x180041b61  mov     [rsp-8+arg_8], rdi
0x180041b66  push    rbp
0x180041b67  lea     rbp, [rsp-57h]
0x180041b6c  sub     rsp, 0D0h
0x180041b73  mov     ebx, edx
0x180041b75  mov     rdi, rcx
0x180041b78  mov     [rbp+57h+TokenHandle], 0
0x180041b80  call    cs:__imp_CoImpersonateClient
0x180041b86  mov     [rbp+57h+arg_18], eax
0x180041b89  mov     r8d, eax
0x180041b8c  shr     r8d, 1Fh
0x180041b90  xor     r8b, 1
0x180041b94  mov     [rbp+57h+arg_10], r8b
0x180041b98  lea     rcx, [rbp+57h+arg_10]
0x180041b9c  mov     [rbp+57h+var_68], rcx
0x180041ba0  lea     rcx, [rbp+57h+arg_18]
0x180041ba4  mov     [rbp+57h+var_60], rcx
0x180041ba8  lea     rcx, [rbp+57h+var_68]
0x180041bac  mov     [rbp+57h+var_78], rcx
0x180041bb0  test    eax, eax
0x180041bb2  js      loc_180041D73
0x180041bb8  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180041bbc  lea     rax, [rcx-1]
0x180041bc0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180041bc4  jbe     loc_180041D5B
0x180041bca  mov     [rbp+57h+TokenHandle], 0
0x180041bd2  call    cs:__imp_GetCurrentThread
0x180041bd8  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180041bdc  mov     edx, 20008h; DesiredAccess
0x180041be1  mov     r8d, 1; OpenAsSelf
0x180041be7  mov     rcx, rax; ThreadHandle
0x180041bea  call    cs:__imp_OpenThreadToken
0x180041bf0  test    eax, eax
0x180041bf2  jz      short loc_180041C41
0x180041bf4  mov     rdx, [rbp+57h+TokenHandle]
0x180041bf8  mov     rcx, rdi
0x180041bfb  test    ebx, ebx
0x180041bfd  jnz     short loc_180041C39
0x180041bff  call    ?GetUserSidFromToken@shared@@YA?AV?$vector@EV?$allocator@E@std@@@std@@PEAX@Z; shared::GetUserSidFromToken(void *)
0x180041c04  nop
0x180041c05  lea     rcx, [rbp+57h+var_78]
0x180041c09  call    ScopeWarden__lambda_5aa063b9d9a6bbd28ff940b8a2c95ce9______ScopeWarden__lambda_5aa063b9d9a6bbd28ff940b8a2c95ce9___
0x180041c0e  nop
0x180041c0f  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180041c13  lea     rax, [rcx-1]
0x180041c17  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180041c1b  jbe     loc_180041DB8
0x180041c21  mov     rax, rdi
0x180041c24  lea     r11, [rsp+0D0h+var_s0]
0x180041c2c  mov     rbx, [r11+10h]
0x180041c30  mov     rdi, [r11+18h]
0x180041c34  mov     rsp, r11
0x180041c37  pop     rbp
0x180041c38  retn
0x180041c39  call    ?GetLogonSessionSidFromToken@shared@@YA?AV?$vector@EV?$allocator@E@std@@@std@@PEAX@Z; shared::GetLogonSessionSidFromToken(void *)
0x180041c3e  nop
0x180041c3f  jmp     short loc_180041C05
0x180041c41  call    cs:__imp_GetLastError
0x180041c47  mov     ebx, eax
0x180041c49  test    eax, eax
0x180041c4b  jg      loc_180041D65
0x180041c51  lea     rax, aPlatformshared; ".\\platformshared.cpp"
0x180041c58  mov     [rbp+57h+var_90], rax
0x180041c5c  mov     [rbp+57h+var_88], 287h
0x180041c63  mov     [rbp+57h+var_A0], ebx
0x180041c66  call    cs:__imp_GetCurrentThreadId
0x180041c6c  mov     eax, eax
0x180041c6e  mov     [rbp+57h+var_80], rax
0x180041c72  lea     rax, [rbp+57h+var_80]
0x180041c76  mov     [rsp+0D0h+var_A8], rax
0x180041c7b  lea     rax, [rbp+57h+var_88]
0x180041c7f  mov     [rsp+0D0h+var_B0], rax
0x180041c84  lea     r9, [rbp+57h+var_90]
0x180041c88  lea     r8, [rbp+57h+var_A0]
0x180041c8c  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180041c93  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180041c98  lea     rdx, [rbp+57h+var_90]
0x180041c9c  lea     rcx, [rbp+57h+var_58]
0x180041ca0  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180041ca5  mov     r9, rax
0x180041ca8  mov     ecx, ebx
0x180041caa  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180041caf  mov     r8, rax
0x180041cb2  mov     edx, ebx
0x180041cb4  lea     rcx, [rbp+57h+pExceptionObject]
0x180041cb8  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180041cbd  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180041cc4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180041cc8  call    _CxxThrowException_0
0x180041cce  call    cs:__imp_GetLastError
0x180041cd4  mov     ebx, eax
0x180041cd6  test    eax, eax
0x180041cd8  jg      loc_180041DAA
0x180041cde  lea     rax, aPlatformshared; ".\\platformshared.cpp"
0x180041ce5  mov     [rbp+57h+var_90], rax
0x180041ce9  mov     [rbp+57h+var_88], 291h
0x180041cf0  mov     [rbp+57h+var_A0], ebx
0x180041cf3  call    cs:__imp_GetCurrentThreadId
0x180041cf9  mov     eax, eax
0x180041cfb  mov     [rbp+57h+var_80], rax
0x180041cff  lea     rax, [rbp+57h+var_80]
0x180041d03  mov     [rsp+0D0h+var_A8], rax
0x180041d08  lea     rax, [rbp+57h+var_88]
0x180041d0c  mov     [rsp+0D0h+var_B0], rax
0x180041d11  lea     r9, [rbp+57h+var_90]
0x180041d15  lea     r8, [rbp+57h+var_A0]
0x180041d19  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180041d20  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180041d25  lea     rdx, [rbp+57h+var_90]
0x180041d29  lea     rcx, [rbp+57h+var_58]
0x180041d2d  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180041d32  mov     r9, rax
0x180041d35  mov     ecx, ebx
0x180041d37  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180041d3c  mov     r8, rax
0x180041d3f  mov     edx, ebx
0x180041d41  lea     rcx, [rbp+57h+pExceptionObject]
0x180041d45  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180041d4a  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180041d51  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180041d55  call    _CxxThrowException_0
0x180041d5b  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x180041d60  jmp     loc_180041BCA
0x180041d65  movzx   ebx, ax
0x180041d68  or      ebx, 80070000h
0x180041d6e  jmp     loc_180041C51
0x180041d73  cmp     eax, 80010117h
0x180041d78  jnz     short loc_180041DC3
0x180041d7a  xor     edx, edx
0x180041d7c  lea     rcx, [rbp+57h+TokenHandle]
0x180041d80  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180041d85  call    cs:__imp_GetCurrentProcess
0x180041d8b  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180041d8f  mov     edx, 20008h; DesiredAccess
0x180041d94  mov     rcx, rax; ProcessHandle
0x180041d97  call    cs:__imp_OpenProcessToken
0x180041d9d  test    eax, eax
0x180041d9f  jnz     loc_180041BF4
0x180041da5  jmp     loc_180041CCE
0x180041daa  movzx   ebx, ax
0x180041dad  or      ebx, 80070000h
0x180041db3  jmp     loc_180041CDE
0x180041db8  call    cs:__imp_CloseHandle
0x180041dbe  jmp     loc_180041C21
0x180041dc3  lea     rdx, aTextUnableToDe; "{\"text\":\"Unable to decide how to get"...
0x180041dca  mov     ecx, 1
0x180041dcf  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x180041dd4  lea     rax, aPlatformshared; ".\\platformshared.cpp"
0x180041ddb  mov     [rbp+57h+var_90], rax
0x180041ddf  mov     [rbp+57h+var_88], 297h
0x180041de6  mov     ebx, 8000FFFFh
0x180041deb  mov     [rbp+57h+var_A0], ebx
0x180041dee  call    cs:__imp_GetCurrentThreadId
0x180041df4  mov     eax, eax
0x180041df6  mov     [rbp+57h+var_80], rax
0x180041dfa  lea     rax, [rbp+57h+var_80]
0x180041dfe  mov     [rsp+0D0h+var_A8], rax
0x180041e03  lea     rax, [rbp+57h+var_88]
0x180041e07  mov     [rsp+0D0h+var_B0], rax
0x180041e0c  lea     r9, [rbp+57h+var_90]
0x180041e10  lea     r8, [rbp+57h+var_A0]
0x180041e14  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180041e1b  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180041e20  lea     rdx, [rbp+57h+var_90]
0x180041e24  lea     rcx, [rbp+57h+var_58]
0x180041e28  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180041e2d  mov     r9, rax
0x180041e30  mov     ecx, ebx
0x180041e32  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180041e37  mov     r8, rax
0x180041e3a  mov     edx, ebx
0x180041e3c  lea     rcx, [rbp+57h+pExceptionObject]
0x180041e40  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180041e45  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180041e4c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180041e50  call    _CxxThrowException_0
```
