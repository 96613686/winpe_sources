# shared::GetUserSidFromToken(void *)

- ea: `0x1801026d4`
- end: `0x1801029c9`
- name: `?GetUserSidFromToken@shared@@YA?AV?$vector@EV?$allocator@E@std@@@std@@PEAX@Z`
- size: `757`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180041b5c`

## callees

- `0x18000f8d0`
- `0x1800113bc`
- `0x180030190`
- `0x18003d0e0`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x180095934`
- `0x1801026d4`
- `0x180143248`
- `0x1801f6fb0`
- `0x1801fcb36`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180102803`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801028c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18010294d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180102803`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801028c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18010294d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801027d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010289b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801027d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010289b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18010273a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18010279c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18010273a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18010279c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1801027cb`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1801027cb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801027b1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801027b1`

## string_xrefs

- `0x180102829`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1801028eb`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180102964`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall shared::GetUserSidFromToken(__int64 a1, void *a2)
{
  BOOL v4; // ebx
  signed int LastError; // eax
  unsigned int v6; // edi
  PSID *v7; // rdi
  __int64 LengthSid; // rbx
  signed int v9; // eax
  unsigned int v10; // ebx
  int v11; // ecx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rax
  signed int v17; // eax
  unsigned int v18; // ebx
  int v19; // ecx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rax
  DWORD CurrentThreadId; // eax
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-69h] BYREF
  unsigned int v30; // [rsp+34h] [rbp-65h] BYREF
  const char *v31; // [rsp+38h] [rbp-61h] BYREF
  int v32; // [rsp+40h] [rbp-59h] BYREF
  int v33; // [rsp+48h] [rbp-51h]
  __int64 v34; // [rsp+50h] [rbp-49h] BYREF
  LPVOID TokenInformation[2]; // [rsp+58h] [rbp-41h] BYREF
  __int64 v36; // [rsp+68h] [rbp-31h]
  __int64 v37; // [rsp+70h] [rbp-29h]
  _BYTE pExceptionObject[56]; // [rsp+78h] [rbp-21h] BYREF
  _BYTE v39[32]; // [rsp+B0h] [rbp+17h] BYREF

  v37 = a1;
  v33 = 0;
  TokenInformationLength = 0;
  *(_OWORD *)TokenInformation = 0;
  v36 = 0;
  v4 = GetTokenInformation(a2, TokenUser, 0, 0, &TokenInformationLength);
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  v33 = 1;
  LastError = GetLastError();
  v6 = LastError;
  if ( v4 || LastError != 122 )
  {
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v31 = ".\\platformshared.cpp";
    v32 = 601;
    CurrentThreadId = GetCurrentThreadId();
    cdp::detail::StringFormat(
      v39,
      "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      v6,
      ".\\platformshared.cpp",
      601,
      CurrentThreadId);
    v33 = 3;
    shared::LogMessage(1, v39);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v39);
    v25 = cdp::ExceptionStackFromSourceLocationInfo(v39, &v31);
    v28 = cdp::ErrorCodeToString(v6, v26, v27, v25);
    ConnectedDevices::Exception::Exception(pExceptionObject, v6, v28);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  std::vector<unsigned char>::_Resize<std::_Value_init_tag>(TokenInformation, TokenInformationLength);
  if ( !GetTokenInformation(
          a2,
          (TOKEN_INFORMATION_CLASS)(v6 - 121),
          TokenInformation[0],
          TokenInformationLength,
          &TokenInformationLength) )
  {
    v17 = GetLastError();
    v18 = v17;
    if ( v17 > 0 )
      v18 = (unsigned __int16)v17 | 0x80070000;
    v31 = ".\\platformshared.cpp";
    v32 = 596;
    v30 = v18;
    v34 = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v19,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v30,
      (unsigned int)&v31,
      (__int64)&v32,
      (__int64)&v34);
    v20 = cdp::ExceptionStackFromSourceLocationInfo(v39, &v31);
    v23 = cdp::ErrorCodeToString(v18, v21, v22, v20);
    ConnectedDevices::Exception::Exception(pExceptionObject, v18, v23);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v7 = (PSID *)TokenInformation[0];
  LengthSid = GetLengthSid(*(PSID *)TokenInformation[0]);
  std::vector<unsigned char>::_Resize<std::_Value_init_tag>(a1, LengthSid);
  if ( !CopySid(LengthSid, *(PSID *)a1, *v7) )
  {
    v9 = GetLastError();
    v10 = v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    v31 = ".\\platformshared.cpp";
    v32 = 591;
    v30 = v10;
    v34 = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v11,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v30,
      (unsigned int)&v31,
      (__int64)&v32,
      (__int64)&v34);
    v12 = cdp::ExceptionStackFromSourceLocationInfo(v39, &v31);
    v15 = cdp::ErrorCodeToString(v10, v13, v14, v12);
    ConnectedDevices::Exception::Exception(pExceptionObject, v10, v15);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  std::vector<unsigned char>::_Tidy(TokenInformation);
  return a1;
}

```

## disassembly

```asm
0x1801026d4  mov     [rsp-8+arg_10], rbx
0x1801026d9  mov     [rsp-8+arg_18], rsi
0x1801026de  push    rbp
0x1801026df  push    rdi
0x1801026e0  push    r14
0x1801026e2  lea     rbp, [rsp-47h]
0x1801026e7  sub     rsp, 0E0h
0x1801026ee  mov     rax, cs:__security_cookie
0x1801026f5  xor     rax, rsp
0x1801026f8  mov     [rbp+57h+var_20], rax
0x1801026fc  mov     r14, rdx
0x1801026ff  mov     rsi, rcx
0x180102702  mov     [rbp+57h+var_80], rcx
0x180102706  mov     [rbp+57h+var_A8], 0
0x18010270d  mov     [rbp+57h+TokenInformationLength], 0
0x180102714  xorps   xmm0, xmm0
0x180102717  movdqu  xmmword ptr [rbp+57h+TokenInformation], xmm0
0x18010271c  mov     [rbp+57h+var_88], 0
0x180102724  lea     rax, [rbp+57h+TokenInformationLength]
0x180102728  mov     [rsp+0F0h+ReturnLength], rax; ReturnLength
0x18010272d  xor     r9d, r9d; TokenInformationLength
0x180102730  xor     r8d, r8d; TokenInformation
0x180102733  lea     edx, [r9+1]; TokenInformationClass
0x180102737  mov     rcx, r14; TokenHandle
0x18010273a  call    cs:__imp_GetTokenInformation
0x180102740  mov     ebx, eax
0x180102742  mov     qword ptr [rsi], 0
0x180102749  mov     qword ptr [rsi+8], 0
0x180102751  mov     qword ptr [rsi+10h], 0
0x180102759  mov     [rbp+57h+var_A8], 1
0x180102760  call    cs:__imp_GetLastError
0x180102766  mov     edi, eax
0x180102768  test    ebx, ebx
0x18010276a  jnz     loc_18010292D
0x180102770  cmp     eax, 7Ah ; 'z'
0x180102773  jnz     loc_18010292D
0x180102779  mov     edx, [rbp+57h+TokenInformationLength]
0x18010277c  lea     rcx, [rbp+57h+TokenInformation]
0x180102780  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180102785  lea     rax, [rbp+57h+TokenInformationLength]
0x180102789  mov     [rsp+0F0h+ReturnLength], rax; ReturnLength
0x18010278e  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x180102792  mov     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180102796  lea     edx, [rdi-79h]; TokenInformationClass
0x180102799  mov     rcx, r14; TokenHandle
0x18010279c  call    cs:__imp_GetTokenInformation
0x1801027a2  test    eax, eax
0x1801027a4  jz      loc_18010289B
0x1801027aa  mov     rdi, [rbp+57h+TokenInformation]
0x1801027ae  mov     rcx, [rdi]; pSid
0x1801027b1  call    cs:__imp_GetLengthSid
0x1801027b7  mov     ebx, eax
0x1801027b9  mov     edx, eax
0x1801027bb  mov     rcx, rsi
0x1801027be  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1801027c3  mov     r8, [rdi]; pSourceSid
0x1801027c6  mov     rdx, [rsi]; pDestinationSid
0x1801027c9  mov     ecx, ebx; nDestinationSidLength
0x1801027cb  call    cs:__imp_CopySid
0x1801027d1  test    eax, eax
0x1801027d3  jnz     loc_18010286B
0x1801027d9  call    cs:__imp_GetLastError
0x1801027df  mov     ebx, eax
0x1801027e1  test    eax, eax
0x1801027e3  jle     short loc_1801027EE
0x1801027e5  movzx   ebx, ax
0x1801027e8  or      ebx, 80070000h
0x1801027ee  lea     rsi, aPlatformshared; ".\\platformshared.cpp"
0x1801027f5  mov     [rbp+57h+var_B8], rsi
0x1801027f9  mov     [rbp+57h+var_B0], 24Fh
0x180102800  mov     [rbp+57h+var_BC], ebx
0x180102803  call    cs:__imp_GetCurrentThreadId
0x180102809  mov     eax, eax
0x18010280b  mov     [rbp+57h+var_A0], rax
0x18010280f  lea     rax, [rbp+57h+var_A0]
0x180102813  mov     [rsp+0F0h+var_C8], rax
0x180102818  lea     rax, [rbp+57h+var_B0]
0x18010281c  mov     [rsp+0F0h+ReturnLength], rax
0x180102821  lea     r9, [rbp+57h+var_B8]
0x180102825  lea     r8, [rbp+57h+var_BC]
0x180102829  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180102830  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180102835  lea     rdx, [rbp+57h+var_B8]
0x180102839  lea     rcx, [rbp+57h+var_40]
0x18010283d  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180102842  mov     r9, rax
0x180102845  mov     ecx, ebx
0x180102847  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18010284c  mov     r8, rax
0x18010284f  mov     edx, ebx
0x180102851  lea     rcx, [rbp+57h+pExceptionObject]
0x180102855  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18010285a  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180102861  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180102865  call    _CxxThrowException_0
0x18010286b  lea     rcx, [rbp+57h+TokenInformation]
0x18010286f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180102874  mov     rax, rsi
0x180102877  mov     rcx, [rbp+57h+var_20]
0x18010287b  xor     rcx, rsp; StackCookie
0x18010287e  call    __security_check_cookie
0x180102883  lea     r11, [rsp+0F0h+var_10]
0x18010288b  mov     rbx, [r11+30h]
0x18010288f  mov     rsi, [r11+38h]
0x180102893  mov     rsp, r11
0x180102896  pop     r14
0x180102898  pop     rdi
0x180102899  pop     rbp
0x18010289a  retn
0x18010289b  call    cs:__imp_GetLastError
0x1801028a1  mov     ebx, eax
0x1801028a3  test    eax, eax
0x1801028a5  jle     short loc_1801028B0
0x1801028a7  movzx   ebx, ax
0x1801028aa  or      ebx, 80070000h
0x1801028b0  lea     rsi, aPlatformshared; ".\\platformshared.cpp"
0x1801028b7  mov     [rbp+57h+var_B8], rsi
0x1801028bb  mov     [rbp+57h+var_B0], 254h
0x1801028c2  mov     [rbp+57h+var_BC], ebx
0x1801028c5  call    cs:__imp_GetCurrentThreadId
0x1801028cb  mov     eax, eax
0x1801028cd  mov     [rbp+57h+var_A0], rax
0x1801028d1  lea     rax, [rbp+57h+var_A0]
0x1801028d5  mov     [rsp+0F0h+var_C8], rax
0x1801028da  lea     rax, [rbp+57h+var_B0]
0x1801028de  mov     [rsp+0F0h+ReturnLength], rax
0x1801028e3  lea     r9, [rbp+57h+var_B8]
0x1801028e7  lea     r8, [rbp+57h+var_BC]
0x1801028eb  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1801028f2  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1801028f7  lea     rdx, [rbp+57h+var_B8]
0x1801028fb  lea     rcx, [rbp+57h+var_40]
0x1801028ff  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180102904  mov     r9, rax
0x180102907  mov     ecx, ebx
0x180102909  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18010290e  mov     r8, rax
0x180102911  mov     edx, ebx
0x180102913  lea     rcx, [rbp+57h+pExceptionObject]
0x180102917  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18010291c  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180102923  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180102927  call    _CxxThrowException_0
0x18010292d  test    eax, eax
0x18010292f  jle     short loc_18010293A
0x180102931  movzx   edi, ax
0x180102934  or      edi, 80070000h
0x18010293a  lea     rsi, aPlatformshared; ".\\platformshared.cpp"
0x180102941  mov     [rbp+57h+var_B8], rsi
0x180102945  mov     ebx, 259h
0x18010294a  mov     [rbp+57h+var_B0], ebx
0x18010294d  call    cs:__imp_GetCurrentThreadId
0x180102953  mov     eax, eax
0x180102955  mov     [rsp+0F0h+var_C8], rax
0x18010295a  mov     dword ptr [rsp+0F0h+ReturnLength], ebx
0x18010295e  mov     r9, rsi
0x180102961  mov     r8d, edi
0x180102964  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18010296b  lea     rcx, [rbp+57h+var_40]
0x18010296f  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x180102974  mov     [rbp+57h+var_A8], 3
0x18010297b  lea     rdx, [rbp+57h+var_40]
0x18010297f  mov     ecx, 1
0x180102984  call    ?LogMessage@shared@@YAXW4CDPLogLevel@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; shared::LogMessage(CDPLogLevel,std::string &)
0x180102989  nop
0x18010298a  lea     rcx, [rbp+57h+var_40]; void *
0x18010298e  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180102993  lea     rdx, [rbp+57h+var_B8]
0x180102997  lea     rcx, [rbp+57h+var_40]
0x18010299b  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1801029a0  mov     r9, rax
0x1801029a3  mov     ecx, edi
0x1801029a5  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1801029aa  mov     r8, rax
0x1801029ad  mov     edx, edi
0x1801029af  lea     rcx, [rbp+57h+pExceptionObject]
0x1801029b3  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1801029b8  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1801029bf  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1801029c3  call    _CxxThrowException_0
```
