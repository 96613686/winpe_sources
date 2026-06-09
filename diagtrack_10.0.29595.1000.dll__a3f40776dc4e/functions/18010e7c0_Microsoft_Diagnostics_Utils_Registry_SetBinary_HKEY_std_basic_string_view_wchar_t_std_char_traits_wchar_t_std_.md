# Microsoft::Diagnostics::Utils::Registry::SetBinary(HKEY__ *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,gsl::span<gsl::byte const,-1>,ulong)

- ea: `0x18010e7c0`
- end: `0x18010eb06`
- name: `?SetBinary@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1V?$span@$$CBW4byte@gsl@@$0?0@gsl@@K@Z`
- size: `838`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18010e61c`
- `0x180252390`
- `0x1802549f8`
- `0x1803236d0`

## callees

- `0x180020db8`
- `0x18002be90`
- `0x18002df00`
- `0x180064e8c`
- `0x18010e7c0`
- `0x18010eb0c`
- `0x18010f8f4`
- `0x18020aac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010e86f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010e86f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010e85c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010e85c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010e867`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010e937`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010eaac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010e867`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010e937`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010eaac`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18010e8d2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18010e8d2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010ea0a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010ea0a`

## string_xrefs

- `0x18010e8fa`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x18010e965`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x18010ea40`: `onecore\base\telemetry\utc\include\RegistryUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Diagnostics::Utils::Registry::SetBinary(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 *a4,
        DWORD a5)
{
  HKEY v8; // rsi
  DWORD LastError; // ebx
  const WCHAR *v10; // rdx
  LSTATUS v11; // eax
  unsigned int v12; // ebx
  const char *v13; // r9
  __int64 result; // rax
  HKEY v15; // rbx
  __int64 v16; // rsi
  const BYTE *v17; // r15
  const WCHAR *v18; // rdx
  int v19; // eax
  unsigned int v20; // ebx
  int dwOptions; // [rsp+20h] [rbp-E8h]
  int dwOptionsa; // [rsp+20h] [rbp-E8h]
  int dwOptionsb; // [rsp+20h] [rbp-E8h]
  char *v24; // [rsp+50h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v26; // [rsp+60h] [rbp-A8h]
  HKEY v27; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v28[5]; // [rsp+70h] [rbp-98h] BYREF
  char v29; // [rsp+98h] [rbp-70h]
  LPCWSTR lpValueName[2]; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v31; // [rsp+B0h] [rbp-58h]
  LPCWSTR lpSubKey[4]; // [rsp+C0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  try
  {
    v27 = HKEY_LOCAL_MACHINE;
    LODWORD(v24) = 0;
    hKey = 0;
    v28[0] = &v27;
    v28[1] = a2;
    v28[2] = a3;
    v28[3] = a4;
    v28[4] = &v24;
    v29 = 1;
    *(_OWORD *)lpValueName = *(_OWORD *)a2;
    Microsoft::Diagnostics::Utils::Registry::TryExpandKeyName((LPCWSTR)lpSubKey);
    if ( *(_QWORD *)(a2 + 8) )
    {
      v8 = hKey;
      if ( hKey )
      {
        LastError = GetLastError();
        RegCloseKey(v8);
        SetLastError(LastError);
      }
      hKey = 0;
      v10 = (const WCHAR *)lpSubKey;
      if ( lpSubKey[3] > (LPCWSTR)7 )
        v10 = lpSubKey[0];
      v11 = RegCreateKeyExW(v27, v10, 0, 0, a5, 2u, 0, &hKey, 0);
      v12 = v11;
      if ( v11 > 0 )
        v12 = (unsigned __int16)v11 | 0x80070000;
      LODWORD(v24) = v12;
      if ( (v12 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5AB,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
          (const char *)v12,
          dwOptionsa);
        std::wstring::_Tidy_deallocate(lpSubKey);
        v29 = 0;
        `Microsoft::Diagnostics::Utils::Registry::SetBinary'::`2'::_lambda_1_::operator()(v28);
        if ( hKey )
          RegCloseKey(hKey);
        return v12;
      }
      v15 = hKey;
    }
    else
    {
      v15 = v27;
      if ( !v27 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5B1,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
          (const char *)0x80070057LL,
          dwOptions);
        std::wstring::_Tidy_deallocate(lpSubKey);
        v29 = 0;
        `Microsoft::Diagnostics::Utils::Registry::SetBinary'::`2'::_lambda_1_::operator()(v28);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return 2147942487LL;
      }
    }
    v16 = *a4;
    v17 = (const BYTE *)a4[1];
    *(_OWORD *)lpValueName = 0;
    v31 = 0;
    std::wstring::_Construct<1,wchar_t *>(lpValueName, *a3, a3[1]);
    v18 = (const WCHAR *)lpValueName;
    if ( *((_QWORD *)&v31 + 1) > 7u )
      v18 = lpValueName[0];
    v19 = RegSetValueExW(v15, v18, 0, 3u, v17, v16);
    if ( v19 > 0 )
      v19 = (unsigned __int16)v19 | 0x80070000;
    LODWORD(v24) = v19;
    std::wstring::_Tidy_deallocate(lpValueName);
    v20 = (unsigned int)v24;
    if ( (int)v24 >= 0 )
    {
      std::wstring::_Tidy_deallocate(lpSubKey);
      v29 = 0;
      `Microsoft::Diagnostics::Utils::Registry::SetBinary'::`2'::_lambda_1_::operator()(v28);
      if ( hKey )
        RegCloseKey(hKey);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5B6,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
        (const char *)(unsigned int)v24,
        dwOptionsb);
      std::wstring::_Tidy_deallocate(lpSubKey);
      v29 = 0;
      `Microsoft::Diagnostics::Utils::Registry::SetBinary'::`2'::_lambda_1_::operator()(v28);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      result = v20;
    }
  }
  catch ( ... )
  {
    v26 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x5BA,
            (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
            v13);
    if ( v29 )
    {
      v29 = 0;
      `Microsoft::Diagnostics::Utils::Registry::SetBinary'::`2'::_lambda_1_::operator()(v28);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v26;
  }
  return result;
}

```

## disassembly

```asm
0x18010e7c0  mov     r11, rsp
0x18010e7c3  mov     [r11+8], rbx
0x18010e7c7  push    rsi
0x18010e7c8  push    r14
0x18010e7ca  push    r15
0x18010e7cc  sub     rsp, 0F0h
0x18010e7d3  mov     rax, cs:__security_cookie
0x18010e7da  xor     rax, rsp
0x18010e7dd  mov     [rsp+108h+var_28], rax
0x18010e7e5  mov     r15, r9
0x18010e7e8  mov     r14, r8
0x18010e7eb  mov     rbx, rdx
0x18010e7ee  mov     [rsp+108h+var_A0], 0FFFFFFFF80000002h
0x18010e7f7  mov     dword ptr [rsp+108h+var_B8], 0
0x18010e7ff  mov     [rsp+108h+hKey], 0
0x18010e808  lea     rax, [rsp+108h+var_A0]
0x18010e80d  mov     [rsp+108h+var_98], rax
0x18010e812  mov     [rsp+108h+var_90], rdx
0x18010e817  mov     [r11-88h], r8
0x18010e81e  mov     [r11-80h], r9
0x18010e822  lea     rax, [rsp+108h+var_B8]
0x18010e827  mov     [r11-78h], rax
0x18010e82b  mov     byte ptr [r11-70h], 1
0x18010e830  movups  xmm0, xmmword ptr [rdx]
0x18010e833  movdqu  xmmword ptr [r11-68h], xmm0
0x18010e839  lea     rdx, [r11-68h]
0x18010e83d  lea     rcx, [r11-48h]
0x18010e841  call    ?TryExpandKeyName@Registry@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::Utils::Registry::TryExpandKeyName(std::wstring_view)
0x18010e846  nop
0x18010e847  cmp     qword ptr [rbx+8], 0
0x18010e84c  jz      loc_18010E94B
0x18010e852  mov     rsi, [rsp+108h+hKey]
0x18010e857  test    rsi, rsi
0x18010e85a  jz      short loc_18010E875
0x18010e85c  call    cs:__imp_GetLastError
0x18010e862  mov     ebx, eax
0x18010e864  mov     rcx, rsi; hKey
0x18010e867  call    cs:__imp_RegCloseKey
0x18010e86d  mov     ecx, ebx; dwErrCode
0x18010e86f  call    cs:__imp_SetLastError
0x18010e875  mov     [rsp+108h+hKey], 0
0x18010e87e  lea     rdx, [rsp+108h+lpSubKey]
0x18010e886  cmp     [rsp+108h+var_30], 7
0x18010e88f  cmova   rdx, [rsp+108h+lpSubKey]; lpSubKey
0x18010e898  mov     [rsp+108h+lpdwDisposition], 0; lpdwDisposition
0x18010e8a1  lea     rax, [rsp+108h+hKey]
0x18010e8a6  mov     [rsp+108h+phkResult], rax; phkResult
0x18010e8ab  mov     [rsp+108h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18010e8b4  mov     [rsp+108h+samDesired], 2; samDesired
0x18010e8bc  mov     eax, [rsp+108h+arg_20]
0x18010e8c3  mov     [rsp+108h+dwOptions], eax; int
0x18010e8c7  xor     r9d, r9d; lpClass
0x18010e8ca  xor     r8d, r8d; Reserved
0x18010e8cd  mov     rcx, [rsp+108h+var_A0]; hKey
0x18010e8d2  call    cs:__imp_RegCreateKeyExW
0x18010e8d8  mov     ebx, eax
0x18010e8da  test    eax, eax
0x18010e8dc  jle     short loc_18010E8E7
0x18010e8de  movzx   ebx, ax
0x18010e8e1  or      ebx, 80070000h
0x18010e8e7  mov     dword ptr [rsp+108h+var_B8], ebx
0x18010e8eb  test    ebx, ebx
0x18010e8ed  jns     short loc_18010E944
0x18010e8ef  mov     rcx, [rsp+108h]; this
0x18010e8f7  mov     r9d, ebx; char *
0x18010e8fa  lea     r8, aOnecoreBaseTel_198; "onecore\\base\\telemetry\\utc\\include"...
0x18010e901  mov     edx, 5ABh; void *
0x18010e906  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010e90b  nop
0x18010e90c  lea     rcx, [rsp+108h+lpSubKey]
0x18010e914  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010e919  nop
0x18010e91a  mov     [rsp+108h+var_70], 0
0x18010e922  lea     rcx, [rsp+108h+var_98]
0x18010e927  call    ??R_lambda_1_@?1??SetBinary@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1V?$span@$$CBW4byte@gsl@@$0?0@gsl@@K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetBinary(HKEY__ *,std::wstring_view,std::wstring_view,gsl::span<gsl::byte const,-1>,ulong)'::`2'::_lambda_1_::operator()(void)
0x18010e92c  nop
0x18010e92d  mov     rcx, [rsp+108h+hKey]; hKey
0x18010e932  test    rcx, rcx
0x18010e935  jz      short loc_18010E93D
0x18010e937  call    cs:__imp_RegCloseKey
0x18010e93d  mov     eax, ebx
0x18010e93f  jmp     loc_18010EAE1
0x18010e944  mov     rbx, [rsp+108h+hKey]
0x18010e949  jmp     short loc_18010E9A9
0x18010e94b  mov     rbx, [rsp+108h+var_A0]
0x18010e950  test    rbx, rbx
0x18010e953  jnz     short loc_18010E9A9
0x18010e955  mov     rcx, [rsp+108h]; this
0x18010e95d  mov     ebx, 80070057h
0x18010e962  mov     r9d, ebx; char *
0x18010e965  lea     r8, aOnecoreBaseTel_198; "onecore\\base\\telemetry\\utc\\include"...
0x18010e96c  mov     edx, 5B1h; void *
0x18010e971  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010e976  nop
0x18010e977  lea     rcx, [rsp+108h+lpSubKey]
0x18010e97f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010e984  nop
0x18010e985  mov     [rsp+108h+var_70], 0
0x18010e98d  lea     rcx, [rsp+108h+var_98]
0x18010e992  call    ??R_lambda_1_@?1??SetBinary@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1V?$span@$$CBW4byte@gsl@@$0?0@gsl@@K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetBinary(HKEY__ *,std::wstring_view,std::wstring_view,gsl::span<gsl::byte const,-1>,ulong)'::`2'::_lambda_1_::operator()(void)
0x18010e997  nop
0x18010e998  lea     rcx, [rsp+108h+hKey]
0x18010e99d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010e9a2  mov     eax, ebx
0x18010e9a4  jmp     loc_18010EAE1
0x18010e9a9  mov     rsi, [r15]
0x18010e9ac  mov     r15, [r15+8]
0x18010e9b0  xorps   xmm0, xmm0
0x18010e9b3  movups  xmmword ptr [rsp+108h+lpValueName], xmm0
0x18010e9bb  xorps   xmm1, xmm1
0x18010e9be  movdqu  [rsp+108h+var_58], xmm1
0x18010e9c7  mov     r8, [r14+8]
0x18010e9cb  mov     rdx, [r14]
0x18010e9ce  lea     rcx, [rsp+108h+lpValueName]
0x18010e9d6  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x18010e9db  lea     rdx, [rsp+108h+lpValueName]
0x18010e9e3  cmp     qword ptr [rsp+108h+var_58+8], 7
0x18010e9ec  cmova   rdx, [rsp+108h+lpValueName]; lpValueName
0x18010e9f5  mov     [rsp+108h+samDesired], esi; cbData
0x18010e9f9  mov     qword ptr [rsp+108h+dwOptions], r15; int
0x18010e9fe  mov     r9d, 3; dwType
0x18010ea04  xor     r8d, r8d; Reserved
0x18010ea07  mov     rcx, rbx; hKey
0x18010ea0a  call    cs:__imp_RegSetValueExW
0x18010ea10  test    eax, eax
0x18010ea12  jle     short loc_18010EA1C
0x18010ea14  movzx   eax, ax
0x18010ea17  or      eax, 80070000h
0x18010ea1c  mov     dword ptr [rsp+108h+var_B8], eax
0x18010ea20  lea     rcx, [rsp+108h+lpValueName]
0x18010ea28  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ea2d  mov     ebx, dword ptr [rsp+108h+var_B8]
0x18010ea31  test    ebx, ebx
0x18010ea33  jns     short loc_18010EA81
0x18010ea35  mov     rcx, [rsp+108h]; this
0x18010ea3d  mov     r9d, ebx; char *
0x18010ea40  lea     r8, aOnecoreBaseTel_198; "onecore\\base\\telemetry\\utc\\include"...
0x18010ea47  mov     edx, 5B6h; void *
0x18010ea4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010ea51  nop
0x18010ea52  lea     rcx, [rsp+108h+lpSubKey]
0x18010ea5a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ea5f  nop
0x18010ea60  mov     [rsp+108h+var_70], 0
0x18010ea68  lea     rcx, [rsp+108h+var_98]
0x18010ea6d  call    ??R_lambda_1_@?1??SetBinary@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1V?$span@$$CBW4byte@gsl@@$0?0@gsl@@K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetBinary(HKEY__ *,std::wstring_view,std::wstring_view,gsl::span<gsl::byte const,-1>,ulong)'::`2'::_lambda_1_::operator()(void)
0x18010ea72  nop
0x18010ea73  lea     rcx, [rsp+108h+hKey]
0x18010ea78  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010ea7d  mov     eax, ebx
0x18010ea7f  jmp     short loc_18010EAE1
0x18010ea81  lea     rcx, [rsp+108h+lpSubKey]
0x18010ea89  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ea8e  nop
0x18010ea8f  mov     [rsp+108h+var_70], 0
0x18010ea97  lea     rcx, [rsp+108h+var_98]
0x18010ea9c  call    ??R_lambda_1_@?1??SetBinary@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1V?$span@$$CBW4byte@gsl@@$0?0@gsl@@K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetBinary(HKEY__ *,std::wstring_view,std::wstring_view,gsl::span<gsl::byte const,-1>,ulong)'::`2'::_lambda_1_::operator()(void)
0x18010eaa1  nop
0x18010eaa2  mov     rcx, [rsp+108h+hKey]; hKey
0x18010eaa7  test    rcx, rcx
0x18010eaaa  jz      short loc_18010EAB2
0x18010eaac  call    cs:__imp_RegCloseKey
0x18010eab2  xor     eax, eax
0x18010eab4  jmp     short loc_18010EAE1
0x18010eab6  cmp     [rsp+108h+var_70], 0
0x18010eabe  jz      short loc_18010EAD3
0x18010eac0  mov     [rsp+108h+var_70], 0
0x18010eac8  lea     rcx, [rsp+108h+var_98]
0x18010eacd  call    ??R_lambda_1_@?1??SetBinary@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1V?$span@$$CBW4byte@gsl@@$0?0@gsl@@K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetBinary(HKEY__ *,std::wstring_view,std::wstring_view,gsl::span<gsl::byte const,-1>,ulong)'::`2'::_lambda_1_::operator()(void)
0x18010ead2  nop
0x18010ead3  lea     rcx, [rsp+108h+hKey]
0x18010ead8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010eadd  mov     eax, [rsp+108h+var_A8]
0x18010eae1  mov     rcx, [rsp+108h+var_28]
0x18010eae9  xor     rcx, rsp; StackCookie
0x18010eaec  call    __security_check_cookie
0x18010eaf1  mov     rbx, [rsp+108h+arg_0]
0x18010eaf9  add     rsp, 0F0h
0x18010eb00  pop     r15
0x18010eb02  pop     r14
0x18010eb04  pop     rsi
0x18010eb05  retn
```
