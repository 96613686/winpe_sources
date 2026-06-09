# shared::CallbackNotifierListener::ListenerInternal::GetTokenNamedObjectPathInternal(void)

- ea: `0x1800969f8`
- end: `0x180096cef`
- name: `?GetTokenNamedObjectPathInternal@ListenerInternal@CallbackNotifierListener@shared@@CA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ`
- size: `759`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800966d8`

## callees

- `0x18000aec4`
- `0x18000d02c`
- `0x18000d070`
- `0x18000d350`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800969f8`
- `0x180143248`
- `0x1801f6fb0`
- `0x1801fcb36`
- `0x1801fcb4e`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180096a44`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180096a44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180096a32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180096a32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180096a7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180096b48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180096a7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180096b48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096a52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096a52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180096cbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180096cbe`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180096be7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180096be7`
- `ntdll!RtlNtStatusToDosError` at `0x180096b1e`
- `ntdll!RtlNtStatusToDosError` at `0x180096b1e`
- `ntdll!RtlFreeUnicodeString` at `0x180096ca9`
- `ntdll!RtlFreeUnicodeString` at `0x180096ca9`
- `ntdll!RtlGetTokenNamedObjectPath` at `0x180096afe`
- `ntdll!RtlGetTokenNamedObjectPath` at `0x180096b16`
- `ntdll!RtlGetTokenNamedObjectPath` at `0x180096afe`
- `ntdll!RtlGetTokenNamedObjectPath` at `0x180096b16`

## string_xrefs

- `0x180096aa2`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180096b6e`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall shared::CallbackNotifierListener::ListenerInternal::GetTokenNamedObjectPathInternal(__int64 a1)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v4; // ebx
  int v5; // ecx
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  NTSTATUS TokenNamedObjectPath; // eax
  signed int v11; // eax
  unsigned int v12; // ebx
  int v13; // ecx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rax
  const void *v18; // r15
  unsigned __int64 v19; // rbx
  __int64 v20; // rsi
  size_t v21; // rbx
  __int64 size_of; // rax
  char *v23; // rdi
  size_t v24; // rbx
  unsigned int v26; // [rsp+30h] [rbp-69h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-61h] BYREF
  __int64 CurrentThreadId; // [rsp+40h] [rbp-59h] BYREF
  const char *v29; // [rsp+48h] [rbp-51h] BYREF
  int v30; // [rsp+50h] [rbp-49h] BYREF
  void *Src[2]; // [rsp+58h] [rbp-41h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+70h] [rbp-29h] BYREF
  __int128 v33; // [rsp+A8h] [rbp+Fh] BYREF
  __m128i si128; // [rsp+B8h] [rbp+1Fh]

  CurrentThreadId = a1;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v29 = ".\\callbacknotifierlistener.cpp";
    v30 = 286;
    v26 = v4;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v5,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v26,
      (unsigned int)&v29,
      (__int64)&v30,
      (__int64)&CurrentThreadId);
    v6 = cdp::ExceptionStackFromSourceLocationInfo(&v33, &v29);
    v9 = cdp::ErrorCodeToString(v4, v7, v8, v6);
    ConnectedDevices::Exception::Exception(pExceptionObject, v4, v9);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  Src[0] = 0;
  Src[1] = 0;
  if ( (int)RtlGetTokenNamedObjectPath(TokenHandle, 0, Src) < 0 )
  {
    TokenNamedObjectPath = RtlGetTokenNamedObjectPath(TokenHandle, 0, Src);
    v11 = RtlNtStatusToDosError(TokenNamedObjectPath);
    v12 = v11;
    if ( v11 > 0 )
      v12 = (unsigned __int16)v11 | 0x80070000;
    v29 = ".\\callbacknotifierlistener.cpp";
    v30 = 297;
    v26 = v12;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v13,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v26,
      (unsigned int)&v29,
      (__int64)&v30,
      (__int64)&CurrentThreadId);
    v14 = cdp::ExceptionStackFromSourceLocationInfo(&v33, &v29);
    v17 = cdp::ErrorCodeToString(v12, v15, v16, v14);
    ConnectedDevices::Exception::Exception(pExceptionObject, v12, v17);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v18 = Src[1];
  v33 = 0;
  si128 = 0;
  v19 = -1;
  do
    ++v19;
  while ( *((_WORD *)Src[1] + v19) );
  v20 = 0x7FFFFFFFFFFFFFFELL;
  if ( v19 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v19 > 7 )
  {
    if ( (v19 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v20 = v19 | 7;
      if ( (v19 | 7) < 0xA )
        v20 = 10;
    }
    size_of = std::_Get_size_of_n<2>(v20 + 1);
    v23 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    *(_QWORD *)&v33 = v23;
    si128.m128i_i64[0] = v19;
    si128.m128i_i64[1] = v20;
    v24 = 2 * v19;
    memcpy_0(v23, v18, v24);
    *(_WORD *)&v23[v24] = 0;
  }
  else
  {
    si128.m128i_i64[0] = v19;
    si128.m128i_i64[1] = 7;
    v21 = 2 * v19;
    memcpy_0(&v33, Src[1], v21);
    *(_WORD *)((char *)&v33 + v21) = 0;
  }
  cdp::ToUtf8(a1, &v33);
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v33, 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v33) = 0;
  RtlFreeUnicodeString((PUNICODE_STRING)Src);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return a1;
}

```

## disassembly

```asm
0x1800969f8  mov     [rsp-8+arg_8], rbx
0x1800969fd  mov     [rsp-8+arg_10], rsi
0x180096a02  push    rbp
0x180096a03  push    rdi
0x180096a04  push    r12
0x180096a06  push    r14
0x180096a08  push    r15
0x180096a0a  lea     rbp, [rsp-37h]
0x180096a0f  sub     rsp, 0D0h
0x180096a16  mov     rax, cs:__security_cookie
0x180096a1d  xor     rax, rsp
0x180096a20  mov     [rbp+57h+var_28], rax
0x180096a24  mov     r14, rcx
0x180096a27  mov     [rbp+57h+var_B0], rcx
0x180096a2b  xor     r12d, r12d
0x180096a2e  mov     [rbp+57h+TokenHandle], r12
0x180096a32  call    cs:__imp_GetCurrentProcess
0x180096a38  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180096a3c  mov     edx, 20008h; DesiredAccess
0x180096a41  mov     rcx, rax; ProcessHandle
0x180096a44  call    cs:__imp_OpenProcessToken
0x180096a4a  test    eax, eax
0x180096a4c  jnz     loc_180096AE4
0x180096a52  call    cs:__imp_GetLastError
0x180096a58  mov     ebx, eax
0x180096a5a  test    eax, eax
0x180096a5c  jle     short loc_180096A67
0x180096a5e  movzx   ebx, ax
0x180096a61  or      ebx, 80070000h
0x180096a67  lea     rax, aCallbacknotifi; ".\\callbacknotifierlistener.cpp"
0x180096a6e  mov     [rbp+57h+var_A8], rax
0x180096a72  mov     [rbp+57h+var_A0], 11Eh
0x180096a79  mov     [rbp+57h+var_C0], ebx
0x180096a7c  call    cs:__imp_GetCurrentThreadId
0x180096a82  mov     eax, eax
0x180096a84  mov     [rbp+57h+var_B0], rax
0x180096a88  lea     rax, [rbp+57h+var_B0]
0x180096a8c  mov     [rsp+0F0h+var_C8], rax
0x180096a91  lea     rax, [rbp+57h+var_A0]
0x180096a95  mov     [rsp+0F0h+var_D0], rax
0x180096a9a  lea     r9, [rbp+57h+var_A8]
0x180096a9e  lea     r8, [rbp+57h+var_C0]
0x180096aa2  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180096aa9  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180096aae  lea     rdx, [rbp+57h+var_A8]
0x180096ab2  lea     rcx, [rbp+57h+var_48]
0x180096ab6  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180096abb  mov     r9, rax
0x180096abe  mov     ecx, ebx
0x180096ac0  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180096ac5  mov     r8, rax
0x180096ac8  mov     edx, ebx
0x180096aca  lea     rcx, [rbp+57h+pExceptionObject]
0x180096ace  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180096ad3  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180096ada  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180096ade  call    _CxxThrowException_0
0x180096ae4  xorps   xmm0, xmm0
0x180096ae7  movups  xmmword ptr [rbp+57h+Src], xmm0
0x180096aeb  mov     word ptr [rbp+57h+Src+2], r12w
0x180096af0  mov     [rbp+57h+Src+8], r12
0x180096af4  lea     r8, [rbp+57h+Src]
0x180096af8  xor     edx, edx
0x180096afa  mov     rcx, [rbp+57h+TokenHandle]
0x180096afe  call    cs:__imp_RtlGetTokenNamedObjectPath
0x180096b04  test    eax, eax
0x180096b06  jns     loc_180096BB0
0x180096b0c  lea     r8, [rbp+57h+Src]
0x180096b10  xor     edx, edx
0x180096b12  mov     rcx, [rbp+57h+TokenHandle]
0x180096b16  call    cs:__imp_RtlGetTokenNamedObjectPath
0x180096b1c  mov     ecx, eax; Status
0x180096b1e  call    cs:__imp_RtlNtStatusToDosError
0x180096b24  mov     ebx, eax
0x180096b26  test    eax, eax
0x180096b28  jle     short loc_180096B33
0x180096b2a  movzx   ebx, ax
0x180096b2d  or      ebx, 80070000h
0x180096b33  lea     rax, aCallbacknotifi; ".\\callbacknotifierlistener.cpp"
0x180096b3a  mov     [rbp+57h+var_A8], rax
0x180096b3e  mov     [rbp+57h+var_A0], 129h
0x180096b45  mov     [rbp+57h+var_C0], ebx
0x180096b48  call    cs:__imp_GetCurrentThreadId
0x180096b4e  mov     eax, eax
0x180096b50  mov     [rbp+57h+var_B0], rax
0x180096b54  lea     rax, [rbp+57h+var_B0]
0x180096b58  mov     [rsp+0F0h+var_C8], rax
0x180096b5d  lea     rax, [rbp+57h+var_A0]
0x180096b61  mov     [rsp+0F0h+var_D0], rax
0x180096b66  lea     r9, [rbp+57h+var_A8]
0x180096b6a  lea     r8, [rbp+57h+var_C0]
0x180096b6e  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180096b75  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180096b7a  lea     rdx, [rbp+57h+var_A8]
0x180096b7e  lea     rcx, [rbp+57h+var_48]
0x180096b82  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180096b87  mov     r9, rax
0x180096b8a  mov     ecx, ebx
0x180096b8c  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180096b91  mov     r8, rax
0x180096b94  mov     edx, ebx
0x180096b96  lea     rcx, [rbp+57h+pExceptionObject]
0x180096b9a  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180096b9f  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180096ba6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180096baa  call    _CxxThrowException_0
0x180096bb0  mov     r15, [rbp+57h+Src+8]
0x180096bb4  xorps   xmm0, xmm0
0x180096bb7  movups  [rbp+57h+var_48], xmm0
0x180096bbb  xorps   xmm1, xmm1
0x180096bbe  movdqu  [rbp+57h+var_38], xmm1
0x180096bc3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180096bc7  inc     rbx
0x180096bca  cmp     [r15+rbx*2], r12w
0x180096bcf  jnz     short loc_180096BC7
0x180096bd1  mov     rsi, 7FFFFFFFFFFFFFFEh
0x180096bdb  cmp     rbx, rsi
0x180096bde  jbe     short loc_180096BEE
0x180096be0  lea     rcx, aStringTooLong; "string too long"
0x180096be7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180096bee  cmp     rbx, 7
0x180096bf2  ja      short loc_180096C1A
0x180096bf4  mov     qword ptr [rbp+57h+var_38], rbx
0x180096bf8  mov     qword ptr [rbp+57h+var_38+8], 7
0x180096c00  add     rbx, rbx
0x180096c03  mov     r8, rbx; Size
0x180096c06  mov     rdx, r15; Src
0x180096c09  lea     rcx, [rbp+57h+var_48]; void *
0x180096c0d  call    memcpy_0
0x180096c12  mov     word ptr [rbp+rbx+57h+var_48], r12w
0x180096c18  jmp     short loc_180096C6B
0x180096c1a  mov     rax, rbx
0x180096c1d  or      rax, 7
0x180096c21  cmp     rax, rsi
0x180096c24  ja      short loc_180096C35
0x180096c26  mov     rsi, rax
0x180096c29  mov     ecx, 0Ah
0x180096c2e  cmp     rax, rcx
0x180096c31  cmovb   rsi, rcx
0x180096c35  lea     rcx, [rsi+1]
0x180096c39  call    ??$_Get_size_of_n@$01@std@@YA_K_K@Z; std::_Get_size_of_n<2>(unsigned __int64)
0x180096c3e  mov     rcx, rax
0x180096c41  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180096c46  mov     rdi, rax
0x180096c49  mov     qword ptr [rbp+57h+var_48], rax
0x180096c4d  mov     qword ptr [rbp+57h+var_38], rbx
0x180096c51  mov     qword ptr [rbp+57h+var_38+8], rsi
0x180096c55  add     rbx, rbx
0x180096c58  mov     r8, rbx; Size
0x180096c5b  mov     rdx, r15; Src
0x180096c5e  mov     rcx, rax; void *
0x180096c61  call    memcpy_0
0x180096c66  mov     [rbx+rdi], r12w
0x180096c6b  lea     rdx, [rbp+57h+var_48]
0x180096c6f  mov     rcx, r14
0x180096c72  call    ?ToUtf8@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; cdp::ToUtf8(std::wstring const &)
0x180096c77  nop
0x180096c78  mov     rdx, qword ptr [rbp+57h+var_38+8]
0x180096c7c  cmp     rdx, 7
0x180096c80  jbe     short loc_180096C93
0x180096c82  lea     rdx, ds:2[rdx*2]
0x180096c8a  mov     rcx, qword ptr [rbp+57h+var_48]
0x180096c8e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180096c93  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180096c9b  movdqu  [rbp+57h+var_38], xmm0
0x180096ca0  mov     word ptr [rbp+57h+var_48], r12w
0x180096ca5  lea     rcx, [rbp+57h+Src]; UnicodeString
0x180096ca9  call    cs:__imp_RtlFreeUnicodeString
0x180096caf  nop
0x180096cb0  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180096cb4  lea     rdx, [rcx-1]
0x180096cb8  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180096cbc  ja      short loc_180096CC4
0x180096cbe  call    cs:__imp_CloseHandle
0x180096cc4  mov     rax, r14
0x180096cc7  mov     rcx, [rbp+57h+var_28]
0x180096ccb  xor     rcx, rsp; StackCookie
0x180096cce  call    __security_check_cookie
0x180096cd3  lea     r11, [rsp+0F0h+var_20]
0x180096cdb  mov     rbx, [r11+38h]
0x180096cdf  mov     rsi, [r11+40h]
0x180096ce3  mov     rsp, r11
0x180096ce6  pop     r15
0x180096ce8  pop     r14
0x180096cea  pop     r12
0x180096cec  pop     rdi
0x180096ced  pop     rbp
0x180096cee  retn
```
