# DasEvaluateUserSessionStartTrigger(void)

- ea: `0x18002c700`
- end: `0x18002cb4f`
- name: `?DasEvaluateUserSessionStartTrigger@@YAJXZ`
- size: `1103`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180042f44`

## callees

- `0x1800153e0`
- `0x180019f78`
- `0x180024bec`
- `0x18002a948`
- `0x18002aa34`
- `0x18002c700`
- `0x18003bc80`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002caa1`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002caa1`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002ca65`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002ca65`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18002cae3`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18002cae3`

## string_xrefs

- `0x18002ca5c`: `ServicesActive`
- `0x18002ca97`: `DeviceAssociationService`
- `0x18002c769`: `onecore\base\devices\association\service\lib\srventry.cpp`
- `0x18002ca7c`: `onecore\base\devices\association\service\lib\srventry.cpp`
- `0x18002cabd`: `onecore\base\devices\association\service\lib\srventry.cpp`

## pseudocode

```c
__int64 DasEvaluateUserSessionStartTrigger(void)
{
  int v0; // eax
  int v1; // r8d
  unsigned int LastError; // ebx
  __int64 v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  SC_HANDLE v7; // rax
  const char *v8; // r9
  SC_HANDLE v9; // rax
  const char *v10; // r9
  __int64 v11; // rdx
  int v12; // edx
  int v13; // r8d
  int MessageGuid; // [rsp+20h] [rbp-E0h]
  char v16; // [rsp+30h] [rbp-D0h] BYREF
  SC_HANDLE v17; // [rsp+38h] [rbp-C8h] BYREF
  SC_HANDLE v18; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v19[2]; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD *v20; // [rsp+50h] [rbp-B0h]
  _DWORD v21[2]; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD *v22; // [rsp+60h] [rbp-A0h]
  _DWORD v23[2]; // [rsp+68h] [rbp-98h] BYREF
  _OWORD *v24; // [rsp+70h] [rbp-90h]
  _DWORD v25[2]; // [rsp+78h] [rbp-88h] BYREF
  _OWORD *v26; // [rsp+80h] [rbp-80h]
  _DWORD v27[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 *v28; // [rsp+90h] [rbp-70h]
  _DWORD Info[2]; // [rsp+98h] [rbp-68h] BYREF
  _DWORD *v30; // [rsp+A0h] [rbp-60h]
  __int64 v31; // [rsp+A8h] [rbp-58h]
  _QWORD v32[8]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v33; // [rsp+F0h] [rbp-10h] BYREF
  _DWORD v34[2]; // [rsp+100h] [rbp+0h] BYREF
  const GUID *v35; // [rsp+108h] [rbp+8h]
  int v36; // [rsp+110h] [rbp+10h]
  _DWORD *v37; // [rsp+118h] [rbp+18h]
  int v38; // [rsp+120h] [rbp+20h]
  int v39; // [rsp+124h] [rbp+24h]
  const GUID *v40; // [rsp+128h] [rbp+28h]
  int v41; // [rsp+130h] [rbp+30h]
  _DWORD *v42; // [rsp+138h] [rbp+38h]
  int v43; // [rsp+140h] [rbp+40h]
  int v44; // [rsp+144h] [rbp+44h]
  const GUID *v45; // [rsp+148h] [rbp+48h]
  int v46; // [rsp+150h] [rbp+50h]
  _DWORD *v47; // [rsp+158h] [rbp+58h]
  int v48; // [rsp+160h] [rbp+60h]
  int v49; // [rsp+164h] [rbp+64h]
  const GUID *v50; // [rsp+168h] [rbp+68h]
  int v51; // [rsp+170h] [rbp+70h]
  _DWORD *v52; // [rsp+178h] [rbp+78h]
  int v53; // [rsp+180h] [rbp+80h]
  int v54; // [rsp+184h] [rbp+84h]
  const GUID *v55; // [rsp+188h] [rbp+88h]
  int v56; // [rsp+190h] [rbp+90h]
  _DWORD *v57; // [rsp+198h] [rbp+98h]
  _OWORD v58[3]; // [rsp+1A0h] [rbp+A0h] BYREF
  _OWORD v59[2]; // [rsp+1D0h] [rbp+D0h]
  _OWORD v60[3]; // [rsp+1F0h] [rbp+F0h] BYREF
  _OWORD v61[2]; // [rsp+220h] [rbp+120h]
  _OWORD v62[3]; // [rsp+240h] [rbp+140h] BYREF
  _OWORD v63[2]; // [rsp+270h] [rbp+170h]
  _OWORD v64[3]; // [rsp+290h] [rbp+190h] BYREF
  _OWORD v65[2]; // [rsp+2C0h] [rbp+1C0h]
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  v32[0] = off_180083538;
  v32[1] = &v16;
  v32[7] = v32;
  v16 = 0;
  v0 = DAS::ProviderManagement::ProviderManager::ForEach(g_providerManager, v32);
  LastError = v0;
  if ( v0 >= 0 )
  {
    v3 = -1;
    v58[0] = *(_OWORD *)L"bd84cd86-9825-4376-813d-334c543f89b1";
    v58[1] = *(_OWORD *)L"-9825-4376-813d-334c543f89b1";
    v59[0] = *(_OWORD *)L"334c543f89b1";
    v58[2] = *(_OWORD *)L"76-813d-334c543f89b1";
    v33 = WNF_UMGR_USER_LOGIN;
    v4 = -1;
    v60[0] = *(_OWORD *)L"850cee52-3038-4277-b9b4-e05db8b2c35c";
    *(_OWORD *)((char *)v59 + 10) = *(_OWORD *)L"43f89b1";
    v19[0] = 2;
    v60[2] = *(_OWORD *)L"77-b9b4-e05db8b2c35c";
    v60[1] = *(_OWORD *)L"-3038-4277-b9b4-e05db8b2c35c";
    v61[0] = *(_OWORD *)L"e05db8b2c35c";
    *(_OWORD *)((char *)v61 + 10) = *(_OWORD *)L"8b2c35c";
    v62[0] = *(_OWORD *)L"2e7d4935-59d2-4312-a2c8-41900aa5495f";
    v62[1] = *(_OWORD *)L"-59d2-4312-a2c8-41900aa5495f";
    v63[0] = *(_OWORD *)L"41900aa5495f";
    v62[2] = *(_OWORD *)L"12-a2c8-41900aa5495f";
    v64[0] = *(_OWORD *)L"a1d4eae7-39f8-4bca-8e72-832767f5082a";
    *(_OWORD *)((char *)v63 + 10) = *(_OWORD *)L"aa5495f";
    v64[2] = *(_OWORD *)L"ca-8e72-832767f5082a";
    v64[1] = *(_OWORD *)L"-39f8-4bca-8e72-832767f5082a";
    v65[0] = *(_OWORD *)L"832767f5082a";
    *(_OWORD *)((char *)v65 + 10) = *(_OWORD *)L"7f5082a";
    do
      ++v4;
    while ( *((_WORD *)v58 + v4) );
    v21[0] = 2;
    v19[1] = 2 * v4 + 2;
    v20 = v58;
    v5 = -1;
    do
      ++v5;
    while ( *((_WORD *)v60 + v5) );
    v23[0] = 2;
    v21[1] = 2 * v5 + 2;
    v22 = v60;
    v6 = -1;
    do
      ++v6;
    while ( *((_WORD *)v62 + v6) );
    v25[0] = 2;
    v23[1] = 2 * v6 + 2;
    v24 = v62;
    do
      ++v3;
    while ( *((_WORD *)v64 + v3) );
    v27[1] = 8;
    v27[0] = 1;
    v25[1] = 2 * v3 + 2;
    v35 = &RPC_INTERFACE_EVENT_GUID;
    v26 = v64;
    v40 = &RPC_INTERFACE_EVENT_GUID;
    v28 = &v33;
    v37 = v19;
    v42 = v21;
    v47 = v23;
    v52 = v25;
    v55 = &CUSTOM_SYSTEM_STATE_CHANGE_EVENT_GUID;
    v57 = v27;
    v45 = &RPC_INTERFACE_EVENT_GUID;
    v50 = &RPC_INTERFACE_EVENT_GUID;
    v34[0] = 6;
    v34[1] = 1;
    v36 = 1;
    v38 = 6;
    Info[1] = 0;
    v30 = v34;
    v39 = 1;
    v41 = 1;
    v43 = 6;
    v44 = 1;
    v46 = 1;
    v48 = 6;
    v49 = 1;
    v51 = 1;
    v53 = 7;
    v54 = 1;
    v56 = 1;
    Info[0] = (v16 != 0) + 4;
    v31 = 0;
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(*((_QWORD *)WPP_GLOBAL_Control + 5), 6, v1, 13, &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
    v7 = OpenSCManagerW(0, L"ServicesActive", 1u);
    v18 = v7;
    if ( v7 )
    {
      v9 = OpenServiceW(v7, L"DeviceAssociationService", 2u);
      v17 = v9;
      if ( v9 )
      {
        if ( ChangeServiceConfig2W(v9, 8u, Info) )
        {
          if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_(
              *((_QWORD *)WPP_GLOBAL_Control + 5),
              v12,
              v13,
              14,
              &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
          wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v17);
          LastError = 0;
          goto LABEL_23;
        }
        v11 = 149;
      }
      else
      {
        v11 = 148;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v11,
                    (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\srventry.cpp",
                    v10);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x92,
                    (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\srventry.cpp",
                    v8);
    }
LABEL_23:
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v18);
    return LastError;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x76,
    (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\srventry.cpp",
    (const char *)(unsigned int)v0,
    MessageGuid);
  return LastError;
}

```

## disassembly

```asm
0x18002c700  push    rbp
0x18002c702  push    rbx
0x18002c703  push    rsi
0x18002c704  push    rdi
0x18002c705  push    r14
0x18002c707  push    r15
0x18002c709  lea     rbp, [rsp-1F8h]
0x18002c711  sub     rsp, 2F8h
0x18002c718  mov     rax, cs:__security_cookie
0x18002c71f  xor     rax, rsp
0x18002c722  mov     [rbp+220h+var_40], rax
0x18002c729  mov     rcx, cs:?g_providerManager@@3V?$unique_ptr@VProviderManager@ProviderManagement@DAS@@U?$default_delete@VProviderManager@ProviderManagement@DAS@@@std@@@std@@A; std::unique_ptr<DAS::ProviderManagement::ProviderManager> g_providerManager
0x18002c730  lea     rax, off_180083538
0x18002c737  mov     [rbp+220h+var_270], rax
0x18002c73b  lea     rdx, [rbp+220h+var_270]
0x18002c73f  lea     rax, [rsp+320h+var_2F0]
0x18002c744  xor     edi, edi
0x18002c746  mov     [rbp+220h+var_268], rax
0x18002c74a  lea     rax, [rbp+220h+var_270]
0x18002c74e  mov     [rbp+220h+var_238], rax
0x18002c752  mov     [rsp+320h+var_2F0], dil
0x18002c757  call    ?ForEach@ProviderManager@ProviderManagement@DAS@@QEAAJV?$function@$$A6AJV?$shared_ptr@VProviderContext@@@std@@AEA_N@Z@std@@@Z; DAS::ProviderManagement::ProviderManager::ForEach(std::function<long (std::shared_ptr<ProviderContext>,bool &)>)
0x18002c75c  mov     ebx, eax
0x18002c75e  test    eax, eax
0x18002c760  jns     short loc_18002C780
0x18002c762  mov     rcx, [rbp+228h]; this
0x18002c769  lea     r8, aOnecoreBaseDev_9; "onecore\\base\\devices\\association\\se"...
0x18002c770  mov     r9d, eax; char *
0x18002c773  lea     edx, [rdi+76h]; void *
0x18002c776  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c77b  jmp     loc_18002CB2E
0x18002c780  movaps  xmm0, xmmword ptr cs:aBd84cd86982543; "bd84cd86-9825-4376-813d-334c543f89b1"
0x18002c787  lea     rdx, [rbp+220h+var_180]
0x18002c78e  movaps  xmm1, xmmword ptr cs:aBd84cd86982543+10h; "-9825-4376-813d-334c543f89b1"
0x18002c795  mov     esi, 2
0x18002c79a  mov     rax, cs:WNF_UMGR_USER_LOGIN
0x18002c7a1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002c7a5  movaps  [rbp+220h+var_180], xmm0
0x18002c7ac  movaps  xmm0, xmmword ptr cs:aBd84cd86982543+20h; "76-813d-334c543f89b1"
0x18002c7b3  movaps  [rbp+220h+var_170], xmm1
0x18002c7ba  movaps  xmm1, xmmword ptr cs:aBd84cd86982543+30h; "334c543f89b1"
0x18002c7c1  movaps  xmmword ptr [rbp+220h+var_150], xmm1
0x18002c7c8  movaps  xmm1, xmmword ptr cs:a850cee52303842; "850cee52-3038-4277-b9b4-e05db8b2c35c"
0x18002c7cf  movaps  [rbp+220h+var_160], xmm0
0x18002c7d6  movups  xmm0, xmmword ptr cs:aBd84cd86982543+3Ah; "43f89b1"
0x18002c7dd  mov     [rbp+220h+var_230], rax
0x18002c7e1  mov     rax, rcx
0x18002c7e4  movaps  [rbp+220h+var_130], xmm1
0x18002c7eb  movaps  xmm1, xmmword ptr cs:a850cee52303842+20h; "77-b9b4-e05db8b2c35c"
0x18002c7f2  movups  xmmword ptr [rbp+220h+var_150+0Ah], xmm0
0x18002c7f9  mov     [rsp+320h+var_2D8], esi
0x18002c7fd  movaps  xmm0, xmmword ptr cs:a850cee52303842+10h; "-3038-4277-b9b4-e05db8b2c35c"
0x18002c804  movaps  [rbp+220h+var_110], xmm1
0x18002c80b  movups  xmm1, xmmword ptr cs:a850cee52303842+3Ah; "8b2c35c"
0x18002c812  movaps  [rbp+220h+var_120], xmm0
0x18002c819  movaps  xmm0, xmmword ptr cs:a850cee52303842+30h; "e05db8b2c35c"
0x18002c820  movaps  xmmword ptr [rbp+220h+var_100], xmm0
0x18002c827  movaps  xmm0, xmmword ptr cs:a2e7d493559d243; "2e7d4935-59d2-4312-a2c8-41900aa5495f"
0x18002c82e  movups  xmmword ptr [rbp+220h+var_100+0Ah], xmm1
0x18002c835  movaps  xmm1, xmmword ptr cs:a2e7d493559d243+10h; "-59d2-4312-a2c8-41900aa5495f"
0x18002c83c  movaps  [rbp+220h+var_E0], xmm0
0x18002c843  movaps  xmm0, xmmword ptr cs:a2e7d493559d243+20h; "12-a2c8-41900aa5495f"
0x18002c84a  movaps  [rbp+220h+var_D0], xmm1
0x18002c851  movaps  xmm1, xmmword ptr cs:a2e7d493559d243+30h; "41900aa5495f"
0x18002c858  movaps  xmmword ptr [rbp+220h+var_B0], xmm1
0x18002c85f  movaps  xmm1, xmmword ptr cs:aA1d4eae739f84b; "a1d4eae7-39f8-4bca-8e72-832767f5082a"
0x18002c866  movaps  [rbp+220h+var_C0], xmm0
0x18002c86d  movups  xmm0, xmmword ptr cs:a2e7d493559d243+3Ah; "aa5495f"
0x18002c874  movaps  [rbp+220h+var_90], xmm1
0x18002c87b  movaps  xmm1, xmmword ptr cs:aA1d4eae739f84b+20h; "ca-8e72-832767f5082a"
0x18002c882  movups  xmmword ptr [rbp+220h+var_B0+0Ah], xmm0
0x18002c889  movaps  xmm0, xmmword ptr cs:aA1d4eae739f84b+10h; "-39f8-4bca-8e72-832767f5082a"
0x18002c890  movaps  [rbp+220h+var_70], xmm1
0x18002c897  movups  xmm1, xmmword ptr cs:aA1d4eae739f84b+3Ah; "7f5082a"
0x18002c89e  movaps  [rbp+220h+var_80], xmm0
0x18002c8a5  movaps  xmm0, xmmword ptr cs:aA1d4eae739f84b+30h; "832767f5082a"
0x18002c8ac  movaps  xmmword ptr [rbp+220h+var_60], xmm0
0x18002c8b3  movups  xmmword ptr [rbp+220h+var_60+0Ah], xmm1
0x18002c8ba  inc     rax
0x18002c8bd  cmp     [rdx+rax*2], di
0x18002c8c1  jnz     short loc_18002C8BA
0x18002c8c3  lea     eax, ds:2[rax*2]
0x18002c8ca  mov     [rsp+320h+var_2C8], esi
0x18002c8ce  mov     [rsp+320h+var_2D4], eax
0x18002c8d2  lea     rdx, [rbp+220h+var_130]
0x18002c8d9  lea     rax, [rbp+220h+var_180]
0x18002c8e0  mov     [rsp+320h+var_2D0], rax
0x18002c8e5  mov     rax, rcx
0x18002c8e8  inc     rax
0x18002c8eb  cmp     [rdx+rax*2], di
0x18002c8ef  jnz     short loc_18002C8E8
0x18002c8f1  lea     eax, ds:2[rax*2]
0x18002c8f8  mov     [rsp+320h+var_2B8], esi
0x18002c8fc  mov     [rsp+320h+var_2C4], eax
0x18002c900  lea     rdx, [rbp+220h+var_E0]
0x18002c907  lea     rax, [rbp+220h+var_130]
0x18002c90e  mov     [rsp+320h+var_2C0], rax
0x18002c913  mov     rax, rcx
0x18002c916  inc     rax
0x18002c919  cmp     [rdx+rax*2], di
0x18002c91d  jnz     short loc_18002C916
0x18002c91f  lea     eax, ds:2[rax*2]
0x18002c926  mov     [rsp+320h+var_2A8], esi
0x18002c92a  mov     [rsp+320h+var_2B4], eax
0x18002c92e  lea     rax, [rbp+220h+var_E0]
0x18002c935  mov     [rsp+320h+var_2B0], rax
0x18002c93a  lea     rax, [rbp+220h+var_90]
0x18002c941  inc     rcx
0x18002c944  cmp     [rax+rcx*2], di
0x18002c948  jnz     short loc_18002C941
0x18002c94a  mov     ebx, 1
0x18002c94f  mov     [rbp+220h+var_294], 8
0x18002c956  lea     eax, ds:2[rcx*2]
0x18002c95d  mov     [rbp+220h+var_298], ebx
0x18002c960  mov     [rsp+320h+var_2A4], eax
0x18002c964  lea     rcx, RPC_INTERFACE_EVENT_GUID
0x18002c96b  mov     [rbp+220h+var_218], rcx
0x18002c96f  lea     rax, [rbp+220h+var_90]
0x18002c976  mov     [rbp+220h+var_2A0], rax
0x18002c97a  lea     edx, [rbx+5]; int
0x18002c97d  mov     [rbp+220h+var_1F8], rcx
0x18002c981  lea     rax, [rbp+220h+var_230]
0x18002c985  mov     [rbp+220h+var_290], rax
0x18002c989  lea     rax, [rsp+320h+var_2D8]
0x18002c98e  mov     [rbp+220h+var_208], rax
0x18002c992  lea     rax, [rsp+320h+var_2C8]
0x18002c997  mov     [rbp+220h+var_1E8], rax
0x18002c99b  lea     rax, [rsp+320h+var_2B8]
0x18002c9a0  mov     [rbp+220h+var_1C8], rax
0x18002c9a4  lea     rax, [rsp+320h+var_2A8]
0x18002c9a9  mov     [rbp+220h+var_1A8], rax
0x18002c9ad  lea     rax, CUSTOM_SYSTEM_STATE_CHANGE_EVENT_GUID
0x18002c9b4  mov     [rbp+220h+var_198], rax
0x18002c9bb  lea     rax, [rbp+220h+var_298]
0x18002c9bf  mov     [rbp+220h+var_188], rax
0x18002c9c6  mov     al, [rsp+320h+var_2F0]
0x18002c9ca  neg     al
0x18002c9cc  mov     [rbp+220h+var_1D8], rcx
0x18002c9d0  mov     [rbp+220h+var_1B8], rcx
0x18002c9d4  sbb     ecx, ecx
0x18002c9d6  mov     [rbp+220h+var_220], edx
0x18002c9d9  neg     ecx
0x18002c9db  mov     [rbp+220h+var_21C], ebx
0x18002c9de  add     ecx, 4
0x18002c9e1  mov     [rbp+220h+var_210], ebx
0x18002c9e4  xor     eax, eax
0x18002c9e6  mov     [rbp+220h+var_200], edx
0x18002c9e9  mov     [rbp+220h+var_284], eax
0x18002c9ec  lea     rax, [rbp+220h+var_220]
0x18002c9f0  mov     [rbp+220h+var_280], rax
0x18002c9f4  mov     [rbp+220h+var_1FC], ebx
0x18002c9f7  mov     [rbp+220h+var_1F0], ebx
0x18002c9fa  mov     [rbp+220h+var_1E0], edx
0x18002c9fd  mov     [rbp+220h+var_1DC], ebx
0x18002ca00  mov     [rbp+220h+var_1D0], ebx
0x18002ca03  mov     [rbp+220h+var_1C0], edx
0x18002ca06  mov     [rbp+220h+var_1BC], ebx
0x18002ca09  mov     [rbp+220h+var_1B0], ebx
0x18002ca0c  mov     [rbp+220h+var_1A0], 7
0x18002ca16  mov     [rbp+220h+var_19C], ebx
0x18002ca1c  mov     [rbp+220h+var_190], ebx
0x18002ca22  mov     [rbp+220h+Info], ecx
0x18002ca25  mov     [rbp+220h+var_278], rdi
0x18002ca29  lea     r15, WPP_RECORDER_INITIALIZED
0x18002ca30  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002ca37  lea     r14, WPP_f5243b9130583a582cae89f06194ea2b_Traceguids
0x18002ca3e  jz      short loc_18002CA59
0x18002ca40  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ca47  lea     r9d, [rbx+0Ch]; int
0x18002ca4b  mov     qword ptr [rsp+320h+MessageGuid], r14; MessageGuid
0x18002ca50  mov     rcx, [rcx+28h]; int
0x18002ca54  call    WPP_RECORDER_SF_
0x18002ca59  mov     r8d, ebx; dwDesiredAccess
0x18002ca5c  lea     rdx, DatabaseName; "ServicesActive"
0x18002ca63  xor     ecx, ecx; lpMachineName
0x18002ca65  call    cs:__imp_OpenSCManagerW
0x18002ca6b  mov     [rsp+320h+var_2E0], rax
0x18002ca70  test    rax, rax
0x18002ca73  jnz     short loc_18002CA94
0x18002ca75  mov     rcx, [rbp+228h]; this
0x18002ca7c  lea     r8, aOnecoreBaseDev_9; "onecore\\base\\devices\\association\\se"...
0x18002ca83  mov     edx, 92h; void *
0x18002ca88  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002ca8d  mov     ebx, eax
0x18002ca8f  jmp     loc_18002CB24
0x18002ca94  mov     r8d, esi; dwDesiredAccess
0x18002ca97  lea     rdx, ServiceName; "DeviceAssociationService"
0x18002ca9e  mov     rcx, rax; hSCManager
0x18002caa1  call    cs:__imp_OpenServiceW
0x18002caa7  mov     [rsp+320h+var_2E8], rax
0x18002caac  test    rax, rax
0x18002caaf  jnz     short loc_18002CAD7
0x18002cab1  mov     edx, 94h; void *
0x18002cab6  mov     rcx, [rbp+228h]; this
0x18002cabd  lea     r8, aOnecoreBaseDev_9; "onecore\\base\\devices\\association\\se"...
0x18002cac4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002cac9  lea     rcx, [rsp+320h+var_2E8]
0x18002cace  mov     ebx, eax
0x18002cad0  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18002cad5  jmp     short loc_18002CB24
0x18002cad7  lea     r8, [rbp+220h+Info]; lpInfo
0x18002cadb  mov     edx, 8; dwInfoLevel
0x18002cae0  mov     rcx, rax; hService
0x18002cae3  call    cs:__imp_ChangeServiceConfig2W
0x18002cae9  test    eax, eax
0x18002caeb  jnz     short loc_18002CAF4
0x18002caed  mov     edx, 95h
0x18002caf2  jmp     short loc_18002CAB6
0x18002caf4  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002cafb  jz      short loc_18002CB18
0x18002cafd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cb04  mov     r9d, 0Eh; int
0x18002cb0a  mov     qword ptr [rsp+320h+MessageGuid], r14; MessageGuid
0x18002cb0f  mov     rcx, [rcx+28h]; int
0x18002cb13  call    WPP_RECORDER_SF_
0x18002cb18  lea     rcx, [rsp+320h+var_2E8]
0x18002cb1d  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18002cb22  mov     ebx, edi
0x18002cb24  lea     rcx, [rsp+320h+var_2E0]
0x18002cb29  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18002cb2e  mov     eax, ebx
0x18002cb30  mov     rcx, [rbp+220h+var_40]
0x18002cb37  xor     rcx, rsp; StackCookie
0x18002cb3a  call    __security_check_cookie
0x18002cb3f  add     rsp, 2F8h
0x18002cb46  pop     r15
0x18002cb48  pop     r14
0x18002cb4a  pop     rdi
0x18002cb4b  pop     rsi
0x18002cb4c  pop     rbx
0x18002cb4d  pop     rbp
0x18002cb4e  retn
```
