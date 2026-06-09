# CHttpAgent::CHttpAgent(IHttpAgentEvents &,void *,char const *,char const *,void const *,uint,bool,TraceLoggingCorrelationVector *,uint,DOHttpRedirectionPolicy)

- ea: `0x1800cacd4`
- end: `0x1800cb31a`
- name: `??0CHttpAgent@@QEAA@AEAVIHttpAgentEvents@@PEAXPEBD2PEBXI_NPEAVTraceLoggingCorrelationVector@@IW4DOHttpRedirectionPolicy@@@Z`
- size: `1606`
- prototype: `__int64 __fastcall(__int64, __int64, void *, __int64, __int64, const CERT_CONTEXT *pCertContext, int, char, TraceLoggingCorrelationVector *, int, int)`
- caller_count: `3`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800bcd00`
- `0x1800c4078`
- `0x1800e5a04`

## callees

- `0x1800095a0`
- `0x180009ab4`
- `0x18000ef98`
- `0x180019010`
- `0x1800190d4`
- `0x18001dffc`
- `0x180023c88`
- `0x180026ea8`
- `0x180027188`
- `0x1800604f8`
- `0x18007ca54`
- `0x1800a979c`
- `0x1800bbbec`
- `0x1800bdab8`
- `0x1800cacd4`
- `0x1800cf07c`
- `0x1800cf144`
- `0x1800d0d90`
- `0x1800d0eac`
- `0x1800db900`
- `0x1800dd9cc`
- `0x1800f82f0`
- `0x1800f8314`
- `0x1800f8320`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cb019`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cb2ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cb019`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cb2ac`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cb29a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cb29a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cafb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb0f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cafb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb0f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cafc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cb109`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cafc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cb109`
- `CRYPT32!CertFreeCertificateContext` at `0x1800cafc1`
- `CRYPT32!CertFreeCertificateContext` at `0x1800cafc1`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800cafa4`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800cafa4`
- `WINHTTP!WinHttpSetTimeouts` at `0x1800cb142`
- `WINHTTP!WinHttpSetTimeouts` at `0x1800cb142`
- `WINHTTP!WinHttpSetOption` at `0x1800cb0ba`
- `WINHTTP!WinHttpSetOption` at `0x1800cb165`
- `WINHTTP!WinHttpSetOption` at `0x1800cb1a1`
- `WINHTTP!WinHttpSetOption` at `0x1800cb1e0`
- `WINHTTP!WinHttpSetOption` at `0x1800cb223`
- `WINHTTP!WinHttpSetOption` at `0x1800cb254`
- `WINHTTP!WinHttpSetOption` at `0x1800cb0ba`
- `WINHTTP!WinHttpSetOption` at `0x1800cb165`
- `WINHTTP!WinHttpSetOption` at `0x1800cb1a1`
- `WINHTTP!WinHttpSetOption` at `0x1800cb1e0`
- `WINHTTP!WinHttpSetOption` at `0x1800cb223`
- `WINHTTP!WinHttpSetOption` at `0x1800cb254`
- `WINHTTP!WinHttpCloseHandle` at `0x1800cb101`
- `WINHTTP!WinHttpCloseHandle` at `0x1800cb283`
- `WINHTTP!WinHttpCloseHandle` at `0x1800cb101`
- `WINHTTP!WinHttpCloseHandle` at `0x1800cb283`
- `WINHTTP!WinHttpOpen` at `0x1800cb060`
- `WINHTTP!WinHttpOpen` at `0x1800cb060`

## string_xrefs

- `0x1800cb16f`: `Failed to set WINHTTP_OPTION_SECURE_PROTOCOLS`
- `0x1800cb078`: `WinHttpOpen failed`
- `0x1800cb088`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\HttpAgent.cpp`
- `0x1800cb10f`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\HttpAgent.cpp`

## pseudocode

```c
__int64 __fastcall CHttpAgent::CHttpAgent(
        __int64 a1,
        __int64 a2,
        void *a3,
        __int64 a4,
        __int64 a5,
        const CERT_CONTEXT *pCertContext,
        int a7,
        char a8,
        TraceLoggingCorrelationVector *a9,
        int a10,
        int a11)
{
  _QWORD *v14; // rax
  __int64 v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rax
  PCCERT_CONTEXT v18; // r14
  const CERT_CONTEXT *v19; // rdi
  DWORD LastError; // ebx
  __int64 v21; // rax
  CDeviceProfile *v22; // rax
  bool IsPlatformXbox; // al
  void *v24; // rbx
  unsigned int v25; // eax
  HINTERNET *v26; // r14
  void *v27; // r15
  DWORD v28; // edi
  int Config; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  HANDLE v35; // rbx
  wil::details::in1diag3 *v36; // rcx
  bool v37; // dl
  struct TraceLoggingCorrelationVector *v38; // rax
  void *v39; // rcx
  const char *v41; // [rsp+28h] [rbp-D8h]
  const char *v42; // [rsp+28h] [rbp-D8h]
  const char *v43; // [rsp+28h] [rbp-D8h]
  const char *v44; // [rsp+28h] [rbp-D8h]
  const char *v45; // [rsp+28h] [rbp-D8h]
  __int128 v46; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v47; // [rsp+40h] [rbp-C0h]
  __int64 v48; // [rsp+48h] [rbp-B8h]
  __int64 Buffer; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v50; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-A0h] BYREF
  int v52; // [rsp+68h] [rbp-98h] BYREF
  int v53; // [rsp+6Ch] [rbp-94h] BYREF
  void *v54; // [rsp+70h] [rbp-90h] BYREF
  char v55[40]; // [rsp+78h] [rbp-88h] BYREF
  char v56[144]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  hObject = a3;
  v48 = a1;
  *(_QWORD *)a1 = &CHttpAgent::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  v14 = operator new(0x98u);
  *v14 = v14;
  v14[1] = v14;
  v14[2] = v14;
  *((_WORD *)v14 + 12) = 257;
  *(_QWORD *)(a1 + 24) = v14;
  *(_OWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 7;
  *(_WORD *)(a1 + 40) = 0;
  *(_OWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 7;
  *(_WORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 30000000000LL;
  *(_DWORD *)(a1 + 152) = a7;
  *(_DWORD *)(a1 + 156) = 0;
  *(_OWORD *)(a1 + 160) = 0;
  *(_QWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = 7;
  *(_WORD *)(a1 + 160) = 0;
  *(_OWORD *)(a1 + 192) = 0;
  *(_QWORD *)(a1 + 208) = 0;
  *(_QWORD *)(a1 + 216) = 15;
  *(_BYTE *)(a1 + 192) = 0;
  *(_QWORD *)(a1 + 224) = 0;
  *(_QWORD *)(a1 + 232) = 0;
  *(_DWORD *)(a1 + 244) = 15000;
  *(_QWORD *)(a1 + 248) = a2;
  *(_QWORD *)(a1 + 256) = 0;
  *(_QWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 272) = 1;
  *(_QWORD *)(a1 + 280) = 258;
  *(_OWORD *)(a1 + 304) = 0;
  *(_OWORD *)(a1 + 320) = 0;
  *(_OWORD *)(a1 + 336) = 0;
  *(_QWORD *)(a1 + 288) = 0;
  *(_QWORD *)(a1 + 296) = 0;
  *(_DWORD *)(a1 + 352) = -1;
  *(_DWORD *)(a1 + 356) = 0;
  *(_QWORD *)(a1 + 360) = 0;
  *(_QWORD *)(a1 + 368) = 0;
  *(_QWORD *)(a1 + 376) = 0;
  *(_WORD *)(a1 + 385) = 0;
  *(_BYTE *)(a1 + 387) = 0;
  *(_BYTE *)(a1 + 388) = a8;
  *(_BYTE *)(a1 + 389) = 0;
  v15 = *((_QWORD *)CGlobalObjects::Instance() + 2);
  v50 = v15;
  *(_DWORD *)(a1 + 240) = CGlobalConfigManager::GetConfigValue<unsigned int>(v15, 192, 0);
  CGlobalConfigManager::GetConfigValue<std::string>(v15, (__int64)v55, 18, 0);
  StringSplit(&v46, v55);
  std::string::~string(v55);
  if ( (__int128 *)(a1 + 360) != &v46 )
  {
    std::vector<std::string>::_Tidy(a1 + 360);
    *(_OWORD *)(a1 + 360) = v46;
    *(_QWORD *)(a1 + 376) = v47;
    v46 = 0;
    v47 = 0;
  }
  std::vector<std::string>::_Tidy(&v46);
  if ( a4 )
  {
    v16 = UTF8toWstr(v55, a4, 0);
    std::wstring::operator=(a1 + 40, v16);
    std::wstring::~wstring(v55);
  }
  if ( a5 )
  {
    v17 = UTF8toWstr(v55, a5, 0);
    std::wstring::operator=(a1 + 72, v17);
    std::wstring::~wstring(v55);
  }
  if ( pCertContext )
  {
    v18 = CertDuplicateCertificateContext(pCertContext);
    v19 = *(const CERT_CONTEXT **)(a1 + 104);
    if ( v19 )
    {
      LastError = GetLastError();
      CertFreeCertificateContext(v19);
      SetLastError(LastError);
    }
    *(_QWORD *)(a1 + 104) = v18;
  }
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    a1 + 232,
    0,
    0,
    0,
    0);
  v21 = CHttpAgent::_AcquireSessionToken(&hObject, hObject);
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    a1 + 224,
    v21);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  hObject = (HANDLE)-1LL;
  CHttpAgent::_ImpersonateUserToken(a1);
  v22 = CGlobalObjects::Instance();
  IsPlatformXbox = CDeviceProfile::IsPlatformXbox(v22);
  v24 = WinHttpOpen(L"Microsoft-Delivery-Optimization/10.1", 4 * !IsPlatformXbox, 0, 0, 0x10000000u);
  v54 = v24;
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x59,
    (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
    (const char *)(v24 == 0),
    "WinHttpOpen failed",
    v41);
  Buffer = *(_QWORD *)(a1 + 232);
  v25 = WinHttpSetOption(v24, 0x63u, &Buffer, 8u);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x5F,
    (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
    (const char *)v25,
    (__int64)"Failed to set WINHTTP_OPTION_UNLOAD_NOTIFY_EVENT",
    v42);
  v26 = (HINTERNET *)(a1 + 8);
  if ( (void **)(a1 + 8) != &v54 )
  {
    v27 = *v26;
    if ( *v26 )
    {
      v28 = GetLastError();
      WinHttpCloseHandle(v27);
      SetLastError(v28);
    }
    *v26 = v24;
    v24 = 0;
    v54 = 0;
  }
  Config = CGlobalConfigManager::GetConfigValue<unsigned int>(v50, 191, 0);
  WinHttpSetTimeouts(*v26, Config, Config, Config, Config);
  v52 = 2048;
  v30 = WinHttpSetOption(*v26, 0x54u, &v52, 4u);
  wil::details::in1diag3::Log_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x6B,
    (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
    (const char *)v30,
    (int)"Failed to set WINHTTP_OPTION_SECURE_PROTOCOLS",
    v43);
  v53 = 1;
  v31 = WinHttpSetOption(*v26, 0x6Fu, &v53, 4u);
  wil::details::in1diag3::Log_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x72,
    (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
    (const char *)v31,
    (int)"Failed to set WINHTTP_OPTION_ASSURED_NON_BLOCKING_CALLBACKS",
    v44);
  if ( a10 )
  {
    v32 = WinHttpSetOption(*v26, 0x49u, &a10, 4u);
    wil::details::in1diag3::Log_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x79,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
      (const char *)v32,
      (int)"Failed to set WINHTTP_OPTION_MAX_CONNS_PER_SERVER",
      v45);
  }
  if ( a11 )
  {
    if ( a11 == 2 )
    {
      LODWORD(v50) = 2;
      v34 = WinHttpSetOption(*(HINTERNET *)(a1 + 8), 0x58u, &v50, 4u);
      wil::details::in1diag3::Log_IfWin32BoolFalseMsg(
        retaddr,
        (void *)0x88,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
        (const char *)v34,
        (int)"Failed to set WINHTTP_OPTION_REDIRECT_POLICY (Allow HTTPS)",
        v45);
    }
  }
  else
  {
    LODWORD(v50) = 0;
    v33 = WinHttpSetOption(*(HINTERNET *)(a1 + 8), 0x58u, &v50, 4u);
    wil::details::in1diag3::Log_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x81,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
      (const char *)v33,
      (int)"Failed to set WINHTTP_OPTION_REDIRECT_POLICY (NEVER)",
      v45);
  }
  if ( v24 )
    WinHttpCloseHandle(v24);
  v35 = hObject;
  if ( hObject != (HANDLE)-1LL )
  {
    if ( !SetThreadToken(0, hObject) )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v36);
    if ( v35 )
      CloseHandle(v35);
  }
  if ( a9 )
  {
    TraceLoggingCorrelationVector::Increment(a9, v56);
    v38 = TraceLoggingCorrelationVector::Extend(v56, v37);
    v39 = *(void **)(a1 + 256);
    *(_QWORD *)(a1 + 256) = v38;
    if ( v39 )
      operator delete(v39);
  }
  return a1;
}

```

## disassembly

```asm
0x1800cacd4  mov     [rsp-8+arg_8], rbx
0x1800cacd9  push    rbp
0x1800cacda  push    rsi
0x1800cacdb  push    rdi
0x1800cacdc  push    r12
0x1800cacde  push    r13
0x1800cace0  push    r14
0x1800cace2  push    r15
0x1800cace4  lea     rbp, [rsp-40h]
0x1800cace9  sub     rsp, 140h
0x1800cacf0  mov     rax, cs:__security_cookie
0x1800cacf7  xor     rax, rsp
0x1800cacfa  mov     [rbp+70h+var_40], rax
0x1800cacfe  mov     r12, r9
0x1800cad01  mov     [rsp+170h+hObject], r8
0x1800cad06  mov     rdi, rdx
0x1800cad09  mov     rsi, rcx
0x1800cad0c  mov     [rsp+170h+var_128], rcx
0x1800cad11  mov     r15, [rbp+70h+arg_20]
0x1800cad18  mov     r14, [rbp+70h+pCertContext]
0x1800cad1f  mov     r13, [rbp+70h+arg_40]
0x1800cad26  xor     ecx, ecx
0x1800cad28  lea     rax, ??_7CHttpAgent@@6B@; const CHttpAgent::`vftable'
0x1800cad2f  mov     [rsi], rax
0x1800cad32  mov     [rsi+8], rcx
0x1800cad36  mov     [rsi+10h], rcx
0x1800cad3a  mov     [rsi+18h], rcx
0x1800cad3e  mov     [rsi+20h], rcx
0x1800cad42  mov     ecx, 98h; Size
0x1800cad47  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800cad4c  mov     [rax], rax
0x1800cad4f  mov     [rax+8], rax
0x1800cad53  mov     [rax+10h], rax
0x1800cad57  mov     word ptr [rax+18h], 101h
0x1800cad5d  mov     [rsi+18h], rax
0x1800cad61  xorps   xmm0, xmm0
0x1800cad64  movups  xmmword ptr [rsi+28h], xmm0
0x1800cad68  xor     edx, edx
0x1800cad6a  mov     [rsi+38h], rdx
0x1800cad6e  lea     ecx, [rdx+7]
0x1800cad71  mov     [rsi+40h], rcx
0x1800cad75  mov     [rsi+28h], dx
0x1800cad79  movups  xmmword ptr [rsi+48h], xmm0
0x1800cad7d  mov     [rsi+58h], rdx
0x1800cad81  mov     [rsi+60h], rcx
0x1800cad85  mov     [rsi+48h], dx
0x1800cad89  mov     [rsi+68h], rdx
0x1800cad8d  mov     [rsi+70h], rdx
0x1800cad91  mov     [rsi+78h], rdx
0x1800cad95  mov     [rsi+80h], rdx
0x1800cad9c  mov     [rsi+88h], rdx
0x1800cada3  mov     rax, 6FC23AC00h
0x1800cadad  mov     [rsi+90h], rax
0x1800cadb4  mov     eax, [rbp+70h+arg_30]
0x1800cadba  mov     [rsi+98h], eax
0x1800cadc0  mov     [rsi+9Ch], edx
0x1800cadc6  movups  xmmword ptr [rsi+0A0h], xmm0
0x1800cadcd  mov     [rsi+0B0h], rdx
0x1800cadd4  mov     [rsi+0B8h], rcx
0x1800caddb  mov     [rsi+0A0h], dx
0x1800cade2  movups  xmmword ptr [rsi+0C0h], xmm0
0x1800cade9  mov     [rsi+0D0h], rdx
0x1800cadf0  mov     qword ptr [rsi+0D8h], 0Fh
0x1800cadfb  mov     [rsi+0C0h], dl
0x1800cae01  mov     [rsi+0E0h], rdx
0x1800cae08  mov     [rsi+0E8h], rdx
0x1800cae0f  mov     dword ptr [rsi+0F4h], 3A98h
0x1800cae19  mov     [rsi+0F8h], rdi
0x1800cae20  mov     [rsi+100h], rdx
0x1800cae27  mov     [rsi+108h], rdx
0x1800cae2e  mov     qword ptr [rsi+110h], 1
0x1800cae39  mov     qword ptr [rsi+118h], 102h
0x1800cae44  movups  xmmword ptr [rsi+130h], xmm0
0x1800cae4b  movups  xmmword ptr [rsi+140h], xmm0
0x1800cae52  movups  xmmword ptr [rsi+150h], xmm0
0x1800cae59  mov     [rsi+120h], rdx
0x1800cae60  mov     [rsi+128h], rdx
0x1800cae67  mov     dword ptr [rsi+160h], 0FFFFFFFFh
0x1800cae71  mov     [rsi+164h], edx
0x1800cae77  lea     rbx, [rsi+168h]
0x1800cae7e  mov     [rbx], rdx
0x1800cae81  mov     [rbx+8], rdx
0x1800cae85  mov     [rbx+10h], rdx
0x1800cae89  mov     [rsi+181h], dx
0x1800cae90  mov     [rsi+183h], dl
0x1800cae96  mov     al, [rbp+70h+arg_38]
0x1800cae9c  mov     [rsi+184h], al
0x1800caea2  mov     [rsi+185h], dl
0x1800caea8  call    ?Instance@CGlobalObjects@@SAAEAV1@XZ; CGlobalObjects::Instance(void)
0x1800caead  mov     rdi, [rax+10h]
0x1800caeb1  mov     [rsp+170h+var_118], rdi
0x1800caeb6  xor     r8d, r8d
0x1800caeb9  mov     edx, 0C0h
0x1800caebe  mov     rcx, rdi
0x1800caec1  call    ??$GetConfigValue@I@CGlobalConfigManager@@QEBAIW4Index@DOConfig@@PEAW4_ConfigProviderType@@@Z; CGlobalConfigManager::GetConfigValue<uint>(DOConfig::Index,_ConfigProviderType *)
0x1800caec6  mov     [rsi+0F0h], eax
0x1800caecc  xor     r9d, r9d
0x1800caecf  lea     r8d, [r9+12h]
0x1800caed3  lea     rdx, [rsp+170h+var_F8]
0x1800caed8  mov     rcx, rdi
0x1800caedb  call    ??$GetConfigValue@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@CGlobalConfigManager@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Index@DOConfig@@PEAW4_ConfigProviderType@@@Z; CGlobalConfigManager::GetConfigValue<std::string>(DOConfig::Index,_ConfigProviderType *)
0x1800caee0  nop
0x1800caee1  lea     rdx, [rsp+170h+var_F8]
0x1800caee6  lea     rcx, [rsp+170h+var_140]
0x1800caeeb  call    ?StringSplit@@YA?AV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@D@Z; StringSplit(std::string const &,char)
0x1800caef0  nop
0x1800caef1  lea     rcx, [rsp+170h+var_F8]; void *
0x1800caef6  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800caefb  lea     rax, [rsp+170h+var_140]
0x1800caf00  cmp     rbx, rax
0x1800caf03  jz      short loc_1800CAF39
0x1800caf05  mov     rcx, rbx
0x1800caf08  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x1800caf0d  mov     rax, qword ptr [rsp+170h+var_140]
0x1800caf12  mov     [rbx], rax
0x1800caf15  mov     rax, qword ptr [rsp+170h+var_140+8]
0x1800caf1a  mov     [rbx+8], rax
0x1800caf1e  mov     rax, [rsp+170h+var_130]
0x1800caf23  mov     [rbx+10h], rax
0x1800caf27  xorps   xmm0, xmm0
0x1800caf2a  movdqu  [rsp+170h+var_140], xmm0
0x1800caf30  mov     [rsp+170h+var_130], 0
0x1800caf39  lea     rcx, [rsp+170h+var_140]
0x1800caf3e  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x1800caf43  test    r12, r12
0x1800caf46  jz      short loc_1800CAF6E
0x1800caf48  xor     r8d, r8d
0x1800caf4b  mov     rdx, r12
0x1800caf4e  lea     rcx, [rsp+170h+var_F8]
0x1800caf53  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x1800caf58  mov     rdx, rax
0x1800caf5b  lea     rcx, [rsi+28h]
0x1800caf5f  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800caf64  lea     rcx, [rsp+170h+var_F8]
0x1800caf69  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800caf6e  xor     r12d, r12d
0x1800caf71  test    r15, r15
0x1800caf74  jz      short loc_1800CAF9C
0x1800caf76  xor     r8d, r8d
0x1800caf79  mov     rdx, r15
0x1800caf7c  lea     rcx, [rsp+170h+var_F8]
0x1800caf81  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x1800caf86  mov     rdx, rax
0x1800caf89  lea     rcx, [rsi+48h]
0x1800caf8d  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800caf92  lea     rcx, [rsp+170h+var_F8]
0x1800caf97  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800caf9c  test    r14, r14
0x1800caf9f  jz      short loc_1800CAFD3
0x1800cafa1  mov     rcx, r14; pCertContext
0x1800cafa4  call    cs:__imp_CertDuplicateCertificateContext
0x1800cafaa  mov     r14, rax
0x1800cafad  mov     rdi, [rsi+68h]
0x1800cafb1  test    rdi, rdi
0x1800cafb4  jz      short loc_1800CAFCF
0x1800cafb6  call    cs:__imp_GetLastError
0x1800cafbc  mov     ebx, eax
0x1800cafbe  mov     rcx, rdi; pCertContext
0x1800cafc1  call    cs:__imp_CertFreeCertificateContext
0x1800cafc7  mov     ecx, ebx; dwErrCode
0x1800cafc9  call    cs:__imp_SetLastError
0x1800cafcf  mov     [rsi+68h], r14
0x1800cafd3  mov     qword ptr [rsp+170h+dwFlags], r12
0x1800cafd8  xor     r9d, r9d
0x1800cafdb  xor     r8d, r8d
0x1800cafde  xor     edx, edx
0x1800cafe0  lea     rcx, [rsi+0E8h]
0x1800cafe7  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800cafec  mov     rdx, [rsp+170h+hObject]; ExistingTokenHandle
0x1800caff1  lea     rcx, [rsp+170h+hObject]; DuplicateTokenHandle
0x1800caff6  call    ?_AcquireSessionToken@CHttpAgent@@CA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAX@Z; CHttpAgent::_AcquireSessionToken(void *)
0x1800caffb  mov     rdx, rax
0x1800caffe  lea     rcx, [rsi+0E0h]
0x1800cb005  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1800cb00a  mov     rcx, [rsp+170h+hObject]; hObject
0x1800cb00f  lea     rax, [rcx-1]
0x1800cb013  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800cb017  ja      short loc_1800CB01F
0x1800cb019  call    cs:__imp_CloseHandle
0x1800cb01f  mov     [rsp+170h+hObject], 0FFFFFFFFFFFFFFFFh
0x1800cb028  lea     rdx, [rsp+170h+hObject]
0x1800cb02d  mov     rcx, rsi
0x1800cb030  call    ?_ImpersonateUserToken@CHttpAgent@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@@Z; CHttpAgent::_ImpersonateUserToken(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x1800cb035  call    ?Instance@CGlobalObjects@@SAAEAV1@XZ; CGlobalObjects::Instance(void)
0x1800cb03a  mov     rcx, rax; this
0x1800cb03d  call    ?IsPlatformXbox@CDeviceProfile@@QEAA_NXZ; CDeviceProfile::IsPlatformXbox(void)
0x1800cb042  movzx   edx, al
0x1800cb045  xor     edx, 1
0x1800cb048  shl     edx, 2; dwAccessType
0x1800cb04b  mov     [rsp+170h+dwFlags], 10000000h; dwFlags
0x1800cb053  xor     r9d, r9d; pszProxyBypassW
0x1800cb056  xor     r8d, r8d; pszProxyW
0x1800cb059  lea     rcx, pszAgentW; "Microsoft-Delivery-Optimization/10.1"
0x1800cb060  call    cs:__imp_WinHttpOpen
0x1800cb066  mov     rbx, rax
0x1800cb069  mov     [rsp+170h+var_100], rax
0x1800cb06e  test    rax, rax
0x1800cb071  setz    al
0x1800cb074  mov     rcx, [rbp+78h]; this
0x1800cb078  lea     rdx, aWinhttpopenFai; "WinHttpOpen failed"
0x1800cb07f  mov     qword ptr [rsp+170h+dwFlags], rdx; void *
0x1800cb084  movzx   r9d, al; char *
0x1800cb088  lea     rdi, aCW1SSrcDeliver_73; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800cb08f  mov     r8, rdi; unsigned int
0x1800cb092  mov     edx, 59h ; 'Y'; void *
0x1800cb097  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1800cb09c  mov     rax, [rsi+0E8h]
0x1800cb0a3  mov     [rsp+170h+Buffer], rax
0x1800cb0a8  mov     r9d, 8; dwBufferLength
0x1800cb0ae  lea     r8, [rsp+170h+Buffer]; lpBuffer
0x1800cb0b3  lea     edx, [r9+5Bh]; dwOption
0x1800cb0b7  mov     rcx, rbx; hInternet
0x1800cb0ba  call    cs:__imp_WinHttpSetOption
0x1800cb0c0  mov     rcx, [rbp+78h]; this
0x1800cb0c4  lea     rdx, aFailedToSetWin_4; "Failed to set WINHTTP_OPTION_UNLOAD_NOT"...
0x1800cb0cb  mov     qword ptr [rsp+170h+dwFlags], rdx; __int64
0x1800cb0d0  mov     r9d, eax; char *
0x1800cb0d3  mov     r8, rdi; unsigned int
0x1800cb0d6  mov     edx, 5Fh ; '_'; void *
0x1800cb0db  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1800cb0e0  lea     r14, [rsi+8]
0x1800cb0e4  lea     rax, [rsp+170h+var_100]
0x1800cb0e9  cmp     r14, rax
0x1800cb0ec  jz      short loc_1800CB121
0x1800cb0ee  mov     r15, [r14]
0x1800cb0f1  test    r15, r15
0x1800cb0f4  jz      short loc_1800CB116
0x1800cb0f6  call    cs:__imp_GetLastError
0x1800cb0fc  mov     edi, eax
0x1800cb0fe  mov     rcx, r15; hInternet
0x1800cb101  call    cs:__imp_WinHttpCloseHandle
0x1800cb107  mov     ecx, edi; dwErrCode
0x1800cb109  call    cs:__imp_SetLastError
0x1800cb10f  lea     rdi, aCW1SSrcDeliver_73; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800cb116  mov     [r14], rbx
0x1800cb119  mov     rbx, r12
0x1800cb11c  mov     [rsp+170h+var_100], rbx
0x1800cb121  xor     r8d, r8d
0x1800cb124  mov     edx, 0BFh
0x1800cb129  mov     rcx, [rsp+170h+var_118]
0x1800cb12e  call    ??$GetConfigValue@I@CGlobalConfigManager@@QEBAIW4Index@DOConfig@@PEAW4_ConfigProviderType@@@Z; CGlobalConfigManager::GetConfigValue<uint>(DOConfig::Index,_ConfigProviderType *)
0x1800cb133  mov     [rsp+170h+dwFlags], eax; nReceiveTimeout
0x1800cb137  mov     r9d, eax; nSendTimeout
0x1800cb13a  mov     r8d, eax; nConnectTimeout
0x1800cb13d  mov     edx, eax; nResolveTimeout
0x1800cb13f  mov     rcx, [r14]; hInternet
0x1800cb142  call    cs:__imp_WinHttpSetTimeouts
0x1800cb148  mov     [rsp+170h+var_108], 800h
0x1800cb150  mov     r15d, 4
0x1800cb156  mov     r9d, r15d; dwBufferLength
0x1800cb159  lea     r8, [rsp+170h+var_108]; lpBuffer
0x1800cb15e  lea     edx, [r15+50h]; dwOption
0x1800cb162  mov     rcx, [r14]; hInternet
0x1800cb165  call    cs:__imp_WinHttpSetOption
0x1800cb16b  mov     rcx, [rbp+78h]; this
0x1800cb16f  lea     rdx, aFailedToSetWin_1; "Failed to set WINHTTP_OPTION_SECURE_PRO"...
0x1800cb176  mov     qword ptr [rsp+170h+dwFlags], rdx; int
0x1800cb17b  mov     r9d, eax; char *
0x1800cb17e  mov     r8, rdi; unsigned int
0x1800cb181  lea     edx, [r15+67h]; void *
0x1800cb185  call    ?Log_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Log_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1800cb18a  mov     [rsp+170h+var_104], 1
0x1800cb192  mov     r9d, r15d; dwBufferLength
0x1800cb195  lea     r8, [rsp+170h+var_104]; lpBuffer
0x1800cb19a  lea     edx, [r15+6Bh]; dwOption
0x1800cb19e  mov     rcx, [r14]; hInternet
0x1800cb1a1  call    cs:__imp_WinHttpSetOption
0x1800cb1a7  mov     rcx, [rbp+78h]; this
0x1800cb1ab  lea     rdx, aFailedToSetWin_3; "Failed to set WINHTTP_OPTION_ASSURED_NO"...
0x1800cb1b2  mov     qword ptr [rsp+170h+dwFlags], rdx; int
0x1800cb1b7  mov     r9d, eax; char *
0x1800cb1ba  mov     r8, rdi; unsigned int
0x1800cb1bd  lea     edx, [r15+6Eh]; void *
0x1800cb1c1  call    ?Log_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Log_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1800cb1c6  cmp     [rbp+70h+arg_48], r12d
0x1800cb1cd  jz      short loc_1800CB205
0x1800cb1cf  mov     r9d, r15d; dwBufferLength
0x1800cb1d2  lea     r8, [rbp+70h+arg_48]; lpBuffer
0x1800cb1d9  lea     edx, [r15+45h]; dwOption
0x1800cb1dd  mov     rcx, [r14]; hInternet
0x1800cb1e0  call    cs:__imp_WinHttpSetOption
0x1800cb1e6  mov     rcx, [rbp+78h]; this
0x1800cb1ea  lea     rdx, aFailedToSetWin_2; "Failed to set WINHTTP_OPTION_MAX_CONNS_"...
0x1800cb1f1  mov     qword ptr [rsp+170h+dwFlags], rdx; int
0x1800cb1f6  mov     r9d, eax; char *
0x1800cb1f9  mov     r8, rdi; unsigned int
0x1800cb1fc  lea     edx, [r15+75h]; void *
0x1800cb200  call    ?Log_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Log_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1800cb205  mov     eax, [rbp+70h+arg_50]
0x1800cb20b  test    eax, eax
0x1800cb20d  jnz     short loc_1800CB23C
0x1800cb20f  mov     dword ptr [rsp+170h+var_118], r12d
0x1800cb214  mov     r9d, r15d; dwBufferLength
0x1800cb217  lea     r8, [rsp+170h+var_118]; lpBuffer
0x1800cb21c  lea     edx, [rax+58h]; dwOption
0x1800cb21f  mov     rcx, [rsi+8]; hInternet
0x1800cb223  call    cs:__imp_WinHttpSetOption
0x1800cb229  lea     rdx, aFailedToSetWin; "Failed to set WINHTTP_OPTION_REDIRECT_P"...
0x1800cb230  mov     qword ptr [rsp+170h+dwFlags], rdx
0x1800cb235  mov     edx, 81h
  ... truncated ...
```
