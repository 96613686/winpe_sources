# CHttpAgent::IsProxyConfiguredForUrl(char const *,void *)

- ea: `0x1800cb564`
- end: `0x1800cb861`
- name: `?IsProxyConfiguredForUrl@CHttpAgent@@SA_NPEBDPEAX@Z`
- size: `765`
- prototype: `bool __fastcall(const char *, void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c32f4`

## callees

- `0x180009ab4`
- `0x18000ef98`
- `0x1800a1ea4`
- `0x1800a1f08`
- `0x1800a979c`
- `0x1800ac858`
- `0x1800ae518`
- `0x1800cb564`
- `0x1800cf07c`
- `0x1800cf748`
- `0x1800d0174`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cb815`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cb82a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cb815`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cb82a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cb803`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cb803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb6d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb6d0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800cb66b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800cb682`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800cb692`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800cb6a5`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800cb66b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800cb682`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800cb692`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800cb6a5`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x1800cb61e`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x1800cb61e`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800cb6c6`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800cb6c6`
- `WINHTTP!WinHttpCloseHandle` at `0x1800cb7e7`
- `WINHTTP!WinHttpCloseHandle` at `0x1800cb7e7`
- `WINHTTP!WinHttpOpen` at `0x1800cb70e`
- `WINHTTP!WinHttpOpen` at `0x1800cb70e`

## string_xrefs

- `0x1800cb5c7`: `Failed to impersonate the HTTP token`
- `0x1800cb5dc`: `CHttpAgent::IsProxyConfiguredForUrl`
- `0x1800cb653`: `CHttpAgent::IsProxyConfiguredForUrl`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall CHttpAgent::IsProxyConfiguredForUrl(const char *a1, void *a2)
{
  int v3; // eax
  char v4; // si
  signed int LastError; // eax
  unsigned int v6; // ecx
  void *v7; // rdi
  LPWSTR lpszAutoConfigUrl; // r9
  _QWORD *v9; // r8
  __int64 v10; // rax
  int v11; // ecx
  int v12; // edx
  unsigned int v13; // ecx
  int v14; // eax
  _QWORD *v15; // r8
  _BYTE v17[8]; // [rsp+38h] [rbp-51h] BYREF
  void *v18; // [rsp+40h] [rbp-49h]
  WINHTTP_PROXY_INFO pProxyInfo; // [rsp+48h] [rbp-41h] BYREF
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+60h] [rbp-29h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp-1h] BYREF
  _QWORD v22[3]; // [rsp+90h] [rbp+7h] BYREF
  unsigned __int64 v23; // [rsp+A8h] [rbp+1Fh]

  hObject = 0;
  CHttpAgent::_AcquireSessionToken(&hObject, a2);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v3 = wil::impersonate_token_nothrow(hObject);
    if ( v3 < 0 )
    {
      LogResult(5u, "CHttpAgent::IsProxyConfiguredForUrl", 0xB5u, v3, "Failed to impersonate the HTTP token");
      v4 = 0;
      goto LABEL_44;
    }
  }
  v4 = 1;
  if ( !IsUserSystemAccount() )
  {
LABEL_17:
    memset(&pProxyConfig, 0, sizeof(pProxyConfig));
    *(_QWORD *)&pProxyInfo.dwAccessType = &pProxyConfig;
    LOBYTE(pProxyInfo.lpszProxy) = 1;
    if ( !WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_25;
      v6 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v6 = LastError;
      if ( v6 != -2147024894 )
      {
LABEL_25:
        v4 = 0;
LABEL_43:
        wil::details::lambda_call__CHttpAgent::IsProxyConfiguredForUrl_::_2_::_lambda_2___::_lambda_call__CHttpAgent::IsProxyConfiguredForUrl_::_2_::_lambda_2___(&pProxyInfo);
        goto LABEL_44;
      }
      pProxyConfig.fAutoDetect = 1;
    }
    v7 = WinHttpOpen(L"Microsoft-Delivery-Optimization/10.1", 0, 0, 0, 0x10000000u);
    v18 = v7;
    if ( v7 )
    {
      UTF8toWstr(v22, a1, 0);
      if ( !pProxyConfig.fAutoDetect )
      {
        lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
        if ( pProxyConfig.lpszAutoConfigUrl )
          goto LABEL_37;
      }
      v9 = v22;
      if ( v23 > 7 )
        v9 = (_QWORD *)v22[0];
      v10 = IsProxyConfiguredForAutoOrStaticSettings(v17, v7, v9, 0);
      v11 = *(_DWORD *)v10;
      v4 = *(_BYTE *)(v10 + 4);
      if ( *(int *)v10 < 0 )
      {
        if ( (unsigned int)(v11 + 2147012730) <= 0xE && (v12 = 20483, _bittest(&v12, v11 + 2147012730))
          || v11 == -2147024809
          || (v13 = v11 + 2147012894, v13 <= 0xF) && (v14 = 40977, _bittest(&v14, v13)) )
        {
          lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
          if ( pProxyConfig.lpszAutoConfigUrl )
          {
LABEL_37:
            v15 = v22;
            if ( v23 > 7 )
              v15 = (_QWORD *)v22[0];
            v4 = *(_BYTE *)(IsProxyConfiguredForAutoOrStaticSettings(v17, v7, v15, lpszAutoConfigUrl) + 4);
          }
        }
      }
      std::wstring::~wstring((__int64)v22);
    }
    else
    {
      v4 = 0;
    }
    if ( v7 )
      WinHttpCloseHandle(v7);
    goto LABEL_43;
  }
  memset(&pProxyInfo, 0, sizeof(pProxyInfo));
  if ( !WinHttpGetDefaultProxyConfiguration(&pProxyInfo) || pProxyInfo.dwAccessType == 1 )
    goto LABEL_13;
  if ( !pProxyInfo.lpszProxy )
  {
LABEL_15:
    if ( pProxyInfo.lpszProxyBypass )
      GlobalFree(pProxyInfo.lpszProxyBypass);
    goto LABEL_17;
  }
  if ( !*pProxyInfo.lpszProxy )
  {
LABEL_13:
    if ( pProxyInfo.lpszProxy )
    {
      GlobalFree(pProxyInfo.lpszProxy);
      pProxyInfo.lpszProxy = 0;
    }
    goto LABEL_15;
  }
  LogMessage(5u, "CHttpAgent::IsProxyConfiguredForUrl", 0xCEu, "Proxies for URL %s: %ls", a1, pProxyInfo.lpszProxy);
  if ( pProxyInfo.lpszProxy )
  {
    GlobalFree(pProxyInfo.lpszProxy);
    pProxyInfo.lpszProxy = 0;
  }
  if ( pProxyInfo.lpszProxyBypass )
    GlobalFree(pProxyInfo.lpszProxyBypass);
LABEL_44:
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return v4;
}

```

## disassembly

```asm
0x1800cb564  mov     [rsp-8+arg_10], rbx
0x1800cb569  mov     [rsp-8+arg_18], rsi
0x1800cb56e  push    rbp
0x1800cb56f  push    rdi
0x1800cb570  push    r12
0x1800cb572  push    r14
0x1800cb574  push    r15
0x1800cb576  lea     rbp, [rsp-37h]
0x1800cb57b  sub     rsp, 0C0h
0x1800cb582  mov     rax, cs:__security_cookie
0x1800cb589  xor     rax, rsp
0x1800cb58c  mov     [rbp+57h+var_30], rax
0x1800cb590  mov     r14, rcx
0x1800cb593  xor     r12d, r12d
0x1800cb596  mov     [rbp+57h+hObject], r12
0x1800cb59a  lea     rcx, [rbp+57h+hObject]; DuplicateTokenHandle
0x1800cb59e  call    ?_AcquireSessionToken@CHttpAgent@@CA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAX@Z; CHttpAgent::_AcquireSessionToken(void *)
0x1800cb5a3  nop
0x1800cb5a4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800cb5a8  mov     [rbp+57h+Token], rbx
0x1800cb5ac  mov     rcx, [rbp+57h+hObject]; Token
0x1800cb5b0  lea     rax, [rcx-1]
0x1800cb5b4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800cb5b8  ja      short loc_1800CB5FB
0x1800cb5ba  lea     rdx, [rbp+57h+Token]
0x1800cb5be  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x1800cb5c3  test    eax, eax
0x1800cb5c5  jns     short loc_1800CB5F7
0x1800cb5c7  lea     rcx, aFailedToImpers; "Failed to impersonate the HTTP token"
0x1800cb5ce  mov     qword ptr [rsp+0E0h+dwFlags], rcx; char *
0x1800cb5d3  mov     r9d, eax; int
0x1800cb5d6  mov     r8d, 0B5h; unsigned int
0x1800cb5dc  lea     rdx, aChttpagentIspr; "CHttpAgent::IsProxyConfiguredForUrl"
0x1800cb5e3  lea     ecx, [rbx+6]; unsigned __int8
0x1800cb5e6  call    ?LogResult@@YAXEPEBDIJ0ZZ; LogResult(uchar,char const *,uint,long,char const *,...)
0x1800cb5eb  mov     sil, r12b
0x1800cb5ee  mov     rbx, [rbp+57h+Token]
0x1800cb5f2  jmp     loc_1800CB7F8
0x1800cb5f7  mov     rbx, [rbp+57h+Token]
0x1800cb5fb  call    ?IsUserSystemAccount@@YA_NXZ; IsUserSystemAccount(void)
0x1800cb600  mov     esi, 1
0x1800cb605  test    al, al
0x1800cb607  jz      loc_1800CB6AB
0x1800cb60d  xorps   xmm0, xmm0
0x1800cb610  xor     eax, eax
0x1800cb612  movups  xmmword ptr [rbp+57h+pProxyInfo.dwAccessType], xmm0
0x1800cb616  mov     [rbp+57h+pProxyInfo.lpszProxyBypass], rax
0x1800cb61a  lea     rcx, [rbp+57h+pProxyInfo]; pProxyInfo
0x1800cb61e  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x1800cb624  mov     rcx, [rbp+57h+pProxyInfo.lpszProxy]; hMem
0x1800cb628  test    eax, eax
0x1800cb62a  jz      short loc_1800CB68D
0x1800cb62c  cmp     [rbp+57h+pProxyInfo.dwAccessType], esi
0x1800cb62f  jz      short loc_1800CB68D
0x1800cb631  test    rcx, rcx
0x1800cb634  jz      short loc_1800CB69C
0x1800cb636  cmp     [rcx], r12w
0x1800cb63a  jz      short loc_1800CB68D
0x1800cb63c  mov     [rsp+0E0h+var_B8], rcx
0x1800cb641  mov     qword ptr [rsp+0E0h+dwFlags], r14
0x1800cb646  lea     r9, aProxiesForUrlS_0; "Proxies for URL %s: %ls"
0x1800cb64d  mov     r8d, 0CEh; unsigned int
0x1800cb653  lea     rdx, aChttpagentIspr; "CHttpAgent::IsProxyConfiguredForUrl"
0x1800cb65a  lea     ecx, [rsi+4]; unsigned __int8
0x1800cb65d  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800cb662  mov     rcx, [rbp+57h+pProxyInfo.lpszProxy]; hMem
0x1800cb666  test    rcx, rcx
0x1800cb669  jz      short loc_1800CB675
0x1800cb66b  call    cs:__imp_GlobalFree
0x1800cb671  mov     [rbp+57h+pProxyInfo.lpszProxy], r12
0x1800cb675  mov     rcx, [rbp+57h+pProxyInfo.lpszProxyBypass]; hMem
0x1800cb679  test    rcx, rcx
0x1800cb67c  jz      loc_1800CB7F8
0x1800cb682  call    cs:__imp_GlobalFree
0x1800cb688  jmp     loc_1800CB7F8
0x1800cb68d  test    rcx, rcx
0x1800cb690  jz      short loc_1800CB69C
0x1800cb692  call    cs:__imp_GlobalFree
0x1800cb698  mov     [rbp+57h+pProxyInfo.lpszProxy], r12
0x1800cb69c  mov     rcx, [rbp+57h+pProxyInfo.lpszProxyBypass]; hMem
0x1800cb6a0  test    rcx, rcx
0x1800cb6a3  jz      short loc_1800CB6AB
0x1800cb6a5  call    cs:__imp_GlobalFree
0x1800cb6ab  xorps   xmm0, xmm0
0x1800cb6ae  movups  xmmword ptr [rbp+57h+pProxyConfig.fAutoDetect], xmm0
0x1800cb6b2  movups  xmmword ptr [rbp+57h+pProxyConfig.lpszProxy], xmm0
0x1800cb6b6  lea     rax, [rbp+57h+pProxyConfig]
0x1800cb6ba  mov     qword ptr [rbp+57h+pProxyInfo.dwAccessType], rax
0x1800cb6be  mov     byte ptr [rbp+57h+pProxyInfo.lpszProxy], sil
0x1800cb6c2  lea     rcx, [rbp+57h+pProxyConfig]; pProxyConfig
0x1800cb6c6  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x1800cb6cc  test    eax, eax
0x1800cb6ce  jnz     short loc_1800CB6F7
0x1800cb6d0  call    cs:__imp_GetLastError
0x1800cb6d6  test    eax, eax
0x1800cb6d8  jz      short loc_1800CB72F
0x1800cb6da  movzx   ecx, ax
0x1800cb6dd  or      ecx, 80070000h
0x1800cb6e3  test    eax, eax
0x1800cb6e5  cmovle  ecx, eax
0x1800cb6e8  test    ecx, ecx
0x1800cb6ea  jns     short loc_1800CB6F7
0x1800cb6ec  cmp     ecx, 80070002h
0x1800cb6f2  jnz     short loc_1800CB72F
0x1800cb6f4  mov     [rbp+57h+pProxyConfig.fAutoDetect], esi
0x1800cb6f7  mov     [rsp+0E0h+dwFlags], 10000000h; dwFlags
0x1800cb6ff  xor     r9d, r9d; pszProxyBypassW
0x1800cb702  xor     r8d, r8d; pszProxyW
0x1800cb705  xor     edx, edx; dwAccessType
0x1800cb707  lea     rcx, pszAgentW; "Microsoft-Delivery-Optimization/10.1"
0x1800cb70e  call    cs:__imp_WinHttpOpen
0x1800cb714  mov     rdi, rax
0x1800cb717  mov     [rbp+57h+var_A0], rax
0x1800cb71b  test    rax, rax
0x1800cb71e  setnz   r15b
0x1800cb722  test    rax, rax
0x1800cb725  jnz     short loc_1800CB737
0x1800cb727  mov     sil, r12b
0x1800cb72a  jmp     loc_1800CB7DF
0x1800cb72f  mov     sil, r12b
0x1800cb732  jmp     loc_1800CB7EE
0x1800cb737  xor     r8d, r8d
0x1800cb73a  mov     rdx, r14
0x1800cb73d  lea     rcx, [rbp+57h+var_50]
0x1800cb741  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x1800cb746  nop
0x1800cb747  cmp     [rbp+57h+pProxyConfig.fAutoDetect], esi
0x1800cb74a  jz      short loc_1800CB755
0x1800cb74c  mov     r9, [rbp+57h+pProxyConfig.lpszAutoConfigUrl]
0x1800cb750  test    r9, r9
0x1800cb753  jnz     short loc_1800CB7B7
0x1800cb755  lea     r8, [rbp+57h+var_50]
0x1800cb759  cmp     [rbp+57h+var_38], 7
0x1800cb75e  cmova   r8, [rbp+57h+var_50]
0x1800cb763  xor     r9d, r9d
0x1800cb766  mov     rdx, rdi
0x1800cb769  lea     rcx, [rbp+57h+var_A8]
0x1800cb76d  call    IsProxyConfiguredForAutoOrStaticSettings
0x1800cb772  mov     ecx, [rax]
0x1800cb774  mov     sil, [rax+4]
0x1800cb778  test    ecx, ecx
0x1800cb77a  jns     short loc_1800CB7D5
0x1800cb77c  lea     eax, [rcx+7FF8D07Ah]
0x1800cb782  cmp     eax, 0Eh
0x1800cb785  ja      short loc_1800CB791
0x1800cb787  mov     edx, 5003h
0x1800cb78c  bt      edx, eax
0x1800cb78f  jb      short loc_1800CB7AE
0x1800cb791  cmp     ecx, 80070057h
0x1800cb797  jz      short loc_1800CB7AE
0x1800cb799  add     ecx, 7FF8D11Eh
0x1800cb79f  cmp     ecx, 0Fh
0x1800cb7a2  ja      short loc_1800CB7D5
0x1800cb7a4  mov     eax, 0A011h
0x1800cb7a9  bt      eax, ecx
0x1800cb7ac  jnb     short loc_1800CB7D5
0x1800cb7ae  mov     r9, [rbp+57h+pProxyConfig.lpszAutoConfigUrl]
0x1800cb7b2  test    r9, r9
0x1800cb7b5  jz      short loc_1800CB7D5
0x1800cb7b7  lea     r8, [rbp+57h+var_50]
0x1800cb7bb  cmp     [rbp+57h+var_38], 7
0x1800cb7c0  cmova   r8, [rbp+57h+var_50]
0x1800cb7c5  mov     rdx, rdi
0x1800cb7c8  lea     rcx, [rbp+57h+var_A8]
0x1800cb7cc  call    IsProxyConfiguredForAutoOrStaticSettings
0x1800cb7d1  mov     sil, [rax+4]
0x1800cb7d5  lea     rcx, [rbp+57h+var_50]
0x1800cb7d9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800cb7de  nop
0x1800cb7df  test    r15b, r15b
0x1800cb7e2  jz      short loc_1800CB7EE
0x1800cb7e4  mov     rcx, rdi; hInternet
0x1800cb7e7  call    cs:__imp_WinHttpCloseHandle
0x1800cb7ed  nop
0x1800cb7ee  lea     rcx, [rbp+57h+pProxyInfo]
0x1800cb7f2  call    wil__details__lambda_call__CHttpAgent__IsProxyConfiguredForUrl____2____lambda_2______lambda_call__CHttpAgent__IsProxyConfiguredForUrl____2____lambda_2___
0x1800cb7f7  nop
0x1800cb7f8  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800cb7fc  jz      short loc_1800CB81C
0x1800cb7fe  mov     rdx, rbx; Token
0x1800cb801  xor     ecx, ecx; Thread
0x1800cb803  call    cs:__imp_SetThreadToken
0x1800cb809  test    eax, eax
0x1800cb80b  jz      short loc_1800CB85B
0x1800cb80d  test    rbx, rbx
0x1800cb810  jz      short loc_1800CB81C
0x1800cb812  mov     rcx, rbx; hObject
0x1800cb815  call    cs:__imp_CloseHandle
0x1800cb81b  nop
0x1800cb81c  mov     rcx, [rbp+57h+hObject]; hObject
0x1800cb820  lea     rdx, [rcx-1]
0x1800cb824  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800cb828  ja      short loc_1800CB830
0x1800cb82a  call    cs:__imp_CloseHandle
0x1800cb830  mov     al, sil
0x1800cb833  mov     rcx, [rbp+57h+var_30]
0x1800cb837  xor     rcx, rsp; StackCookie
0x1800cb83a  call    __security_check_cookie
0x1800cb83f  lea     r11, [rsp+0E0h+var_20]
0x1800cb847  mov     rbx, [r11+40h]
0x1800cb84b  mov     rsi, [r11+48h]
0x1800cb84f  mov     rsp, r11
0x1800cb852  pop     r15
0x1800cb854  pop     r14
0x1800cb856  pop     r12
0x1800cb858  pop     rdi
0x1800cb859  pop     rbp
0x1800cb85a  retn
0x1800cb85b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
