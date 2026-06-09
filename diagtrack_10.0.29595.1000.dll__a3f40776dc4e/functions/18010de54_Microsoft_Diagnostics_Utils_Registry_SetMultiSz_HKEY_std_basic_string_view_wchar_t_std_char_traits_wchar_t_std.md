# Microsoft::Diagnostics::Utils::Registry::SetMultiSz(HKEY__ *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,ulong)

- ea: `0x18010de54`
- end: `0x18010e472`
- name: `?SetMultiSz@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@7@K@Z`
- size: `1566`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18010db7c`

## callees

- `0x18001d9a0`
- `0x180020db8`
- `0x18002b7c0`
- `0x18002df00`
- `0x180064e8c`
- `0x18010de54`
- `0x18010e478`
- `0x18010e55c`
- `0x18010f8f4`
- `0x18010f9b8`
- `0x18013732c`
- `0x1801385c0`
- `0x18020aac0`
- `0x18020bab8`
- `0x18025f6ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010df63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010df95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010df63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010df95`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18010dff8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18010dff8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010e35d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010e35d`

## string_xrefs

- `0x18010df23`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x18010e020`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x18010e1d7`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x18010e243`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x18010e2c2`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x18010e393`: `onecore\base\telemetry\utc\include\RegistryUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Diagnostics::Utils::Registry::SetMultiSz(HKEY a1, __int64 a2, __int64 a3, __int64 *a4)
{
  HKEY v6; // r12
  const char *v7; // r9
  __int64 result; // rax
  const WCHAR *v9; // rdx
  LSTATUS v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rcx
  char *v13; // rsi
  unsigned __int64 v14; // rcx
  BYTE *v15; // rax
  size_t v16; // rbx
  unsigned __int64 v17; // rbx
  wchar_t *v18; // rcx
  BYTE *v19; // rsi
  unsigned __int64 v20; // rdx
  size_t v21; // rbx
  unsigned __int64 v22; // rsi
  __int64 v23; // rbx
  __int64 v24; // r15
  const wchar_t *v25; // r8
  int v26; // eax
  unsigned int v27; // esi
  BYTE *v28; // rsi
  signed __int64 v29; // rbx
  __int64 v30; // rax
  int v31; // eax
  unsigned int v32; // ebx
  int dwOptions; // [rsp+20h] [rbp-128h]
  int dwOptionsa; // [rsp+20h] [rbp-128h]
  REGSAM samDesired; // [rsp+28h] [rbp-120h]
  HKEY hKey; // [rsp+50h] [rbp-F8h] BYREF
  char *v37; // [rsp+58h] [rbp-F0h] BYREF
  BYTE *lpData; // [rsp+60h] [rbp-E8h] BYREF
  void *v39; // [rsp+68h] [rbp-E0h]
  __int64 v40; // [rsp+70h] [rbp-D8h]
  unsigned __int64 v41; // [rsp+78h] [rbp-D0h] BYREF
  int v42; // [rsp+80h] [rbp-C8h] BYREF
  HKEY v43; // [rsp+88h] [rbp-C0h] BYREF
  _QWORD v44[5]; // [rsp+90h] [rbp-B8h] BYREF
  char v45; // [rsp+B8h] [rbp-90h]
  LPCWSTR lpSubKey[4]; // [rsp+C0h] [rbp-88h] BYREF
  wchar_t *v47[4]; // [rsp+E0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  try
  {
    v43 = a1;
    LODWORD(v37) = 0;
    hKey = 0;
    v42 = (a4[1] - *a4) >> 5;
    v44[0] = &v43;
    v44[1] = a2;
    v44[2] = a3;
    v44[3] = &v42;
    v44[4] = &v37;
    v45 = 1;
    *(_OWORD *)v47 = *(_OWORD *)a2;
    Microsoft::Diagnostics::Utils::Registry::TryExpandKeyName((LPCWSTR)lpSubKey);
    if ( *(_QWORD *)(a2 + 8) )
    {
      hKey = 0;
      v9 = (const WCHAR *)lpSubKey;
      if ( lpSubKey[3] > (LPCWSTR)7 )
        v9 = lpSubKey[0];
      v10 = RegCreateKeyExW(v43, v9, 0, 0, 0, 2u, 0, &hKey, 0);
      v11 = v10;
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
      LODWORD(v37) = v11;
      if ( (v11 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x22F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
          (const char *)v11,
          dwOptions);
        std::wstring::_Tidy_deallocate(lpSubKey);
        v45 = 0;
        `Microsoft::Diagnostics::Utils::Registry::SetMultiSz'::`2'::_lambda_1_::operator()(v44);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v11;
      }
      v6 = hKey;
    }
    else
    {
      v6 = v43;
      if ( !v43 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x235,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
          (const char *)0x80070057LL,
          dwOptions);
        std::wstring::_Tidy_deallocate(lpSubKey);
        v45 = 0;
        `Microsoft::Diagnostics::Utils::Registry::SetMultiSz'::`2'::_lambda_1_::operator()(v44);
        return 2147942487LL;
      }
    }
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(&lpData);
    v12 = *a4;
    if ( *a4 == a4[1] )
    {
      v13 = (char *)v39;
      v14 = ((_BYTE *)v39 - lpData) >> 1;
      if ( v14 > 2 )
      {
        v15 = lpData + 4;
LABEL_19:
        v39 = v15;
        goto LABEL_20;
      }
      if ( v14 < 2 )
      {
        if ( (unsigned __int64)((v40 - (__int64)lpData) >> 1) >= 2 )
        {
          v16 = 2 * (2 - v14);
          memset_0(v39, 0, v16);
          v15 = (BYTE *)&v13[v16];
          goto LABEL_19;
        }
        std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(&lpData, 2);
      }
LABEL_20:
      *(_WORD *)lpData = 0;
      *((_WORD *)lpData + 1) = 0;
LABEL_43:
      v28 = lpData;
      v29 = ((_BYTE *)v39 - lpData) >> 1;
      v30 = std::wstring::wstring(v47);
      if ( *(_QWORD *)(v30 + 24) > 7u )
        v30 = *(_QWORD *)v30;
      v31 = RegSetValueExW(v6, (LPCWSTR)v30, 0, 7u, v28, 2 * v29);
      if ( v31 > 0 )
        v31 = (unsigned __int16)v31 | 0x80070000;
      LODWORD(v37) = v31;
      std::wstring::_Tidy_deallocate(v47);
      v32 = (unsigned int)v37;
      if ( (int)v37 >= 0 )
      {
        std::vector<wchar_t>::_Tidy(&lpData);
        std::wstring::_Tidy_deallocate(lpSubKey);
        v45 = 0;
        `Microsoft::Diagnostics::Utils::Registry::SetMultiSz'::`2'::_lambda_1_::operator()(v44);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x263,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
          (const char *)(unsigned int)v37,
          dwOptionsa);
        std::vector<wchar_t>::_Tidy(&lpData);
        std::wstring::_Tidy_deallocate(lpSubKey);
        v45 = 0;
        `Microsoft::Diagnostics::Utils::Registry::SetMultiSz'::`2'::_lambda_1_::operator()(v44);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v32;
      }
    }
    v17 = 1;
    do
    {
      v17 += *(_QWORD *)(v12 + 16) + 1LL;
      v12 += 32;
    }
    while ( v12 != a4[1] );
    v18 = (wchar_t *)lpData;
    v19 = (BYTE *)v39;
    v20 = ((_BYTE *)v39 - lpData) >> 1;
    if ( v17 >= v20 )
    {
      if ( v17 <= v20 )
        goto LABEL_30;
      if ( v17 > (v40 - (__int64)lpData) >> 1 )
      {
        std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(&lpData, v17);
        v19 = (BYTE *)v39;
        v18 = (wchar_t *)lpData;
        goto LABEL_30;
      }
      v21 = 2 * (v17 - v20);
      memset_0(v39, 0, v21);
      v19 += v21;
      v18 = (wchar_t *)lpData;
    }
    else
    {
      v19 = &lpData[2 * v17];
    }
    v39 = v19;
LABEL_30:
    v22 = (v19 - (BYTE *)v18) >> 1;
    v23 = *a4;
    v24 = a4[1];
    while ( 1 )
    {
      v41 = v22;
      v47[0] = v18;
      if ( v23 == v24 )
        break;
      if ( *(_QWORD *)(v23 + 24) <= 7u )
        v25 = (const wchar_t *)v23;
      else
        v25 = *(const wchar_t **)v23;
      v26 = StringCchCopyExW(v18, v22, v25, v47, &v41, samDesired);
      v27 = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x251,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
          (const char *)(unsigned int)v26,
          dwOptions);
        std::vector<wchar_t>::_Tidy(&lpData);
        std::wstring::_Tidy_deallocate(lpSubKey);
        v45 = 0;
        `Microsoft::Diagnostics::Utils::Registry::SetMultiSz'::`2'::_lambda_1_::operator()(v44);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v27;
      }
      if ( !v41 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x253,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
          (const char *)0x80004005LL,
          dwOptions);
        std::vector<wchar_t>::_Tidy(&lpData);
        std::wstring::_Tidy_deallocate(lpSubKey);
        v45 = 0;
        `Microsoft::Diagnostics::Utils::Registry::SetMultiSz'::`2'::_lambda_1_::operator()(v44);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return 2147500037LL;
      }
      v22 = v41 - 1;
      v18 = v47[0] + 1;
      v23 += 32;
    }
    if ( v22 != 1 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x259,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
        (const char *)0x80004005LL,
        dwOptions);
      std::vector<wchar_t>::_Tidy(&lpData);
      std::wstring::_Tidy_deallocate(lpSubKey);
      v45 = 0;
      `Microsoft::Diagnostics::Utils::Registry::SetMultiSz'::`2'::_lambda_1_::operator()(v44);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return 2147500037LL;
    }
    *v18 = 0;
    goto LABEL_43;
  }
  catch ( ... )
  {
    LODWORD(v41) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x267,
                     (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
                     v7);
    if ( v45 )
    {
      v45 = 0;
      `Microsoft::Diagnostics::Utils::Registry::SetMultiSz'::`2'::_lambda_1_::operator()(v44);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return (unsigned int)v41;
  }
  return result;
}

```

## disassembly

```asm
0x18010de54  mov     r11, rsp
0x18010de57  push    rbx
0x18010de58  push    rsi
0x18010de59  push    rdi
0x18010de5a  push    r12
0x18010de5c  push    r13
0x18010de5e  push    r14
0x18010de60  push    r15
0x18010de62  sub     rsp, 110h
0x18010de69  mov     rax, cs:__security_cookie
0x18010de70  xor     rax, rsp
0x18010de73  mov     [rsp+148h+var_48], rax
0x18010de7b  mov     r15, r9
0x18010de7e  mov     r13, r8
0x18010de81  mov     rbx, rdx
0x18010de84  mov     [r11-0C0h], rcx
0x18010de8b  xor     edi, edi
0x18010de8d  mov     dword ptr [rsp+148h+var_F0], edi
0x18010de91  mov     [rsp+148h+hKey], rdi
0x18010de96  mov     rax, [r9+8]
0x18010de9a  sub     rax, [r9]
0x18010de9d  sar     rax, 5
0x18010dea1  mov     [rsp+148h+var_C8], eax
0x18010dea8  lea     rax, [r11-0C0h]
0x18010deaf  mov     [r11-0B8h], rax
0x18010deb6  mov     [r11-0B0h], rdx
0x18010debd  mov     [r11-0A8h], r8
0x18010dec4  lea     rax, [r11-0C8h]
0x18010decb  mov     [r11-0A0h], rax
0x18010ded2  lea     rax, [rsp+148h+var_F0]
0x18010ded7  mov     [r11-98h], rax
0x18010dede  mov     [rsp+148h+var_90], 1
0x18010dee6  movups  xmm0, xmmword ptr [rdx]
0x18010dee9  movdqu  xmmword ptr [r11-68h], xmm0
0x18010deef  lea     rdx, [r11-68h]
0x18010def3  lea     rcx, [r11-88h]
0x18010defa  call    ?TryExpandKeyName@Registry@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::Utils::Registry::TryExpandKeyName(std::wstring_view)
0x18010deff  nop
0x18010df00  cmp     [rbx+8], rdi
0x18010df04  jnz     short loc_18010DF7B
0x18010df06  mov     r12, [rsp+148h+var_C0]
0x18010df0e  test    r12, r12
0x18010df11  jnz     short loc_18010DF70
0x18010df13  mov     rcx, [rsp+148h]; this
0x18010df1b  mov     ebx, 80070057h
0x18010df20  mov     r9d, ebx; char *
0x18010df23  lea     r8, aOnecoreBaseTel_198; "onecore\\base\\telemetry\\utc\\include"...
0x18010df2a  mov     edx, 235h; void *
0x18010df2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010df34  nop
0x18010df35  lea     rcx, [rsp+148h+lpSubKey]
0x18010df3d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010df42  nop
0x18010df43  mov     [rsp+148h+var_90], dil
0x18010df4b  lea     rcx, [rsp+148h+var_B8]
0x18010df53  call    ??R_lambda_1_@?1??SetMultiSz@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@8@K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetMultiSz(HKEY__ *,std::wstring_view,std::wstring_view,std::vector<std::wstring> const &,ulong)'::`2'::_lambda_1_::operator()(void)
0x18010df58  nop
0x18010df59  mov     rcx, [rsp+148h+hKey]; hKey
0x18010df5e  test    rcx, rcx
0x18010df61  jz      short loc_18010DF69
0x18010df63  call    cs:__imp_RegCloseKey
0x18010df69  mov     eax, ebx
0x18010df6b  jmp     loc_18010E44F
0x18010df70  mov     r14d, 2
0x18010df76  jmp     loc_18010E06C
0x18010df7b  mov     rbx, [rsp+148h+hKey]
0x18010df80  test    rbx, rbx
0x18010df83  jz      short loc_18010DFA8
0x18010df85  lea     rcx, [rsp+148h+var_68]; this
0x18010df8d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18010df92  mov     rcx, rbx; hKey
0x18010df95  call    cs:__imp_RegCloseKey
0x18010df9b  lea     rcx, [rsp+148h+var_68]; this
0x18010dfa3  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18010dfa8  mov     [rsp+148h+hKey], rdi
0x18010dfad  lea     rdx, [rsp+148h+lpSubKey]
0x18010dfb5  cmp     [rsp+148h+var_70], 7
0x18010dfbe  cmova   rdx, [rsp+148h+lpSubKey]; lpSubKey
0x18010dfc7  mov     [rsp+148h+lpdwDisposition], rdi; lpdwDisposition
0x18010dfcc  lea     rax, [rsp+148h+hKey]
0x18010dfd1  mov     [rsp+148h+phkResult], rax; phkResult
0x18010dfd6  mov     [rsp+148h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18010dfdb  mov     r14d, 2
0x18010dfe1  mov     [rsp+148h+samDesired], r14d; unsigned int
0x18010dfe6  mov     [rsp+148h+dwOptions], edi; int
0x18010dfea  xor     r9d, r9d; lpClass
0x18010dfed  xor     r8d, r8d; Reserved
0x18010dff0  mov     rcx, [rsp+148h+var_C0]; hKey
0x18010dff8  call    cs:__imp_RegCreateKeyExW
0x18010dffe  mov     ebx, eax
0x18010e000  test    eax, eax
0x18010e002  jle     short loc_18010E00D
0x18010e004  movzx   ebx, ax
0x18010e007  or      ebx, 80070000h
0x18010e00d  mov     dword ptr [rsp+148h+var_F0], ebx
0x18010e011  test    ebx, ebx
0x18010e013  jns     short loc_18010E067
0x18010e015  mov     rcx, [rsp+148h]; this
0x18010e01d  mov     r9d, ebx; char *
0x18010e020  lea     r8, aOnecoreBaseTel_198; "onecore\\base\\telemetry\\utc\\include"...
0x18010e027  mov     edx, 22Fh; void *
0x18010e02c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010e031  nop
0x18010e032  lea     rcx, [rsp+148h+lpSubKey]
0x18010e03a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010e03f  nop
0x18010e040  mov     [rsp+148h+var_90], dil
0x18010e048  lea     rcx, [rsp+148h+var_B8]
0x18010e050  call    ??R_lambda_1_@?1??SetMultiSz@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@8@K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetMultiSz(HKEY__ *,std::wstring_view,std::wstring_view,std::vector<std::wstring> const &,ulong)'::`2'::_lambda_1_::operator()(void)
0x18010e055  nop
0x18010e056  lea     rcx, [rsp+148h+hKey]
0x18010e05b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010e060  mov     eax, ebx
0x18010e062  jmp     loc_18010E44F
0x18010e067  mov     r12, [rsp+148h+hKey]
0x18010e06c  lea     rcx, [rsp+148h+lpData]; void *
0x18010e071  call    ??$?0AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(std::allocator<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>> const &)
0x18010e076  nop
0x18010e077  mov     rcx, [r15]
0x18010e07a  cmp     rcx, [r15+8]
0x18010e07e  jnz     short loc_18010E0F5
0x18010e080  mov     rdx, [rsp+148h+lpData]
0x18010e085  mov     rsi, [rsp+148h+var_E0]
0x18010e08a  mov     rcx, rsi
0x18010e08d  sub     rcx, rdx
0x18010e090  sar     rcx, 1
0x18010e093  cmp     rcx, r14
0x18010e096  jbe     short loc_18010E09E
0x18010e098  lea     rax, [rdx+4]
0x18010e09c  jmp     short loc_18010E0DA
0x18010e09e  jnb     short loc_18010E0DF
0x18010e0a0  mov     rax, [rsp+148h+var_D8]
0x18010e0a5  sub     rax, rdx
0x18010e0a8  sar     rax, 1
0x18010e0ab  cmp     rax, r14
0x18010e0ae  jnb     short loc_18010E0BF
0x18010e0b0  mov     rdx, r14
0x18010e0b3  lea     rcx, [rsp+148h+lpData]
0x18010e0b8  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18010e0bd  jmp     short loc_18010E0DF
0x18010e0bf  mov     rax, r14
0x18010e0c2  sub     rax, rcx
0x18010e0c5  lea     rbx, [rax+rax]
0x18010e0c9  mov     r8, rbx; Size
0x18010e0cc  xor     edx, edx; Val
0x18010e0ce  mov     rcx, rsi; void *
0x18010e0d1  call    memset_0
0x18010e0d6  lea     rax, [rbx+rsi]
0x18010e0da  mov     [rsp+148h+var_E0], rax
0x18010e0df  mov     rax, [rsp+148h+lpData]
0x18010e0e4  mov     [rax], di
0x18010e0e7  mov     rax, [rsp+148h+lpData]
0x18010e0ec  mov     [rax+2], di
0x18010e0f0  jmp     loc_18010E317
0x18010e0f5  mov     ebx, 1
0x18010e0fa  inc     rbx
0x18010e0fd  add     rbx, [rcx+10h]
0x18010e101  add     rcx, 20h ; ' '
0x18010e105  cmp     rcx, [r15+8]
0x18010e109  jnz     short loc_18010E0FA
0x18010e10b  mov     rcx, [rsp+148h+lpData]
0x18010e110  mov     rsi, [rsp+148h+var_E0]
0x18010e115  mov     rdx, rsi
0x18010e118  sub     rdx, rcx
0x18010e11b  sar     rdx, 1
0x18010e11e  cmp     rbx, rdx
0x18010e121  jnb     short loc_18010E129
0x18010e123  lea     rsi, [rcx+rbx*2]
0x18010e127  jmp     short loc_18010E16F
0x18010e129  jbe     short loc_18010E174
0x18010e12b  mov     rax, [rsp+148h+var_D8]
0x18010e130  sub     rax, rcx
0x18010e133  sar     rax, 1
0x18010e136  cmp     rbx, rax
0x18010e139  jbe     short loc_18010E154
0x18010e13b  mov     rdx, rbx
0x18010e13e  lea     rcx, [rsp+148h+lpData]
0x18010e143  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18010e148  mov     rsi, [rsp+148h+var_E0]
0x18010e14d  mov     rcx, [rsp+148h+lpData]
0x18010e152  jmp     short loc_18010E174
0x18010e154  sub     rbx, rdx
0x18010e157  add     rbx, rbx
0x18010e15a  mov     r8, rbx; Size
0x18010e15d  xor     edx, edx; Val
0x18010e15f  mov     rcx, rsi; void *
0x18010e162  call    memset_0
0x18010e167  add     rsi, rbx
0x18010e16a  mov     rcx, [rsp+148h+lpData]
0x18010e16f  mov     [rsp+148h+var_E0], rsi
0x18010e174  sub     rsi, rcx
0x18010e177  sar     rsi, 1
0x18010e17a  mov     rbx, [r15]
0x18010e17d  mov     r15, [r15+8]
0x18010e181  mov     rax, rcx
0x18010e184  mov     [rsp+148h+var_D0], rsi
0x18010e189  mov     [rsp+148h+var_68], rcx
0x18010e191  cmp     rbx, r15
0x18010e194  jz      loc_18010E2AC
0x18010e19a  cmp     qword ptr [rbx+18h], 7
0x18010e19f  jbe     short loc_18010E1A6
0x18010e1a1  mov     r8, [rbx]
0x18010e1a4  jmp     short loc_18010E1A9
0x18010e1a6  mov     r8, rbx; wchar_t *
0x18010e1a9  lea     rcx, [rsp+148h+var_D0]
0x18010e1ae  mov     qword ptr [rsp+148h+dwOptions], rcx; int
0x18010e1b3  lea     r9, [rsp+148h+var_68]; wchar_t **
0x18010e1bb  mov     rdx, rsi; unsigned __int64
0x18010e1be  mov     rcx, rax; wchar_t *
0x18010e1c1  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18010e1c6  mov     esi, eax
0x18010e1c8  test    eax, eax
0x18010e1ca  jns     short loc_18010E229
0x18010e1cc  mov     rcx, [rsp+148h]; this
0x18010e1d4  mov     r9d, eax; char *
0x18010e1d7  lea     r8, aOnecoreBaseTel_198; "onecore\\base\\telemetry\\utc\\include"...
0x18010e1de  mov     edx, 251h; void *
0x18010e1e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010e1e8  nop
0x18010e1e9  lea     rcx, [rsp+148h+lpData]
0x18010e1ee  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x18010e1f3  nop
0x18010e1f4  lea     rcx, [rsp+148h+lpSubKey]
0x18010e1fc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010e201  nop
0x18010e202  mov     [rsp+148h+var_90], dil
0x18010e20a  lea     rcx, [rsp+148h+var_B8]
0x18010e212  call    ??R_lambda_1_@?1??SetMultiSz@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@8@K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetMultiSz(HKEY__ *,std::wstring_view,std::wstring_view,std::vector<std::wstring> const &,ulong)'::`2'::_lambda_1_::operator()(void)
0x18010e217  nop
0x18010e218  lea     rcx, [rsp+148h+hKey]
0x18010e21d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010e222  mov     eax, esi
0x18010e224  jmp     loc_18010E44F
0x18010e229  mov     rsi, [rsp+148h+var_D0]
0x18010e22e  test    rsi, rsi
0x18010e231  jnz     short loc_18010E295
0x18010e233  mov     rcx, [rsp+148h]; this
0x18010e23b  mov     ebx, 80004005h
0x18010e240  mov     r9d, ebx; char *
0x18010e243  lea     r8, aOnecoreBaseTel_198; "onecore\\base\\telemetry\\utc\\include"...
0x18010e24a  mov     edx, 253h; void *
0x18010e24f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010e254  nop
0x18010e255  lea     rcx, [rsp+148h+lpData]
0x18010e25a  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x18010e25f  nop
0x18010e260  lea     rcx, [rsp+148h+lpSubKey]
0x18010e268  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010e26d  nop
0x18010e26e  mov     [rsp+148h+var_90], dil
0x18010e276  lea     rcx, [rsp+148h+var_B8]
0x18010e27e  call    ??R_lambda_1_@?1??SetMultiSz@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@8@K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetMultiSz(HKEY__ *,std::wstring_view,std::wstring_view,std::vector<std::wstring> const &,ulong)'::`2'::_lambda_1_::operator()(void)
0x18010e283  nop
0x18010e284  lea     rcx, [rsp+148h+hKey]
0x18010e289  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010e28e  mov     eax, ebx
0x18010e290  jmp     loc_18010E44F
0x18010e295  dec     rsi
0x18010e298  mov     rcx, [rsp+148h+var_68]
0x18010e2a0  add     rcx, r14
0x18010e2a3  add     rbx, 20h ; ' '
0x18010e2a7  jmp     loc_18010E181
0x18010e2ac  cmp     rsi, 1
0x18010e2b0  jz      short loc_18010E314
0x18010e2b2  mov     rcx, [rsp+148h]; this
0x18010e2ba  mov     ebx, 80004005h
0x18010e2bf  mov     r9d, ebx; char *
0x18010e2c2  lea     r8, aOnecoreBaseTel_198; "onecore\\base\\telemetry\\utc\\include"...
0x18010e2c9  mov     edx, 259h; void *
0x18010e2ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010e2d3  nop
0x18010e2d4  lea     rcx, [rsp+148h+lpData]
0x18010e2d9  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x18010e2de  nop
0x18010e2df  lea     rcx, [rsp+148h+lpSubKey]
0x18010e2e7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010e2ec  nop
0x18010e2ed  mov     [rsp+148h+var_90], dil
0x18010e2f5  lea     rcx, [rsp+148h+var_B8]
0x18010e2fd  call    ??R_lambda_1_@?1??SetMultiSz@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@8@K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetMultiSz(HKEY__ *,std::wstring_view,std::wstring_view,std::vector<std::wstring> const &,ulong)'::`2'::_lambda_1_::operator()(void)
0x18010e302  nop
0x18010e303  lea     rcx, [rsp+148h+hKey]
0x18010e308  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010e30d  mov     eax, ebx
0x18010e30f  jmp     loc_18010E44F
0x18010e314  mov     [rcx], di
0x18010e317  mov     rsi, [rsp+148h+lpData]
0x18010e31c  mov     rbx, [rsp+148h+var_E0]
0x18010e321  sub     rbx, rsi
0x18010e324  sar     rbx, 1
0x18010e327  mov     rdx, r13
0x18010e32a  lea     rcx, [rsp+148h+var_68]
0x18010e332  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18010e337  cmp     qword ptr [rax+18h], 7
0x18010e33c  jbe     short loc_18010E341
0x18010e33e  mov     rax, [rax]
0x18010e341  imul    ebx, r14d
0x18010e345  mov     [rsp+148h+samDesired], ebx; cbData
0x18010e349  mov     qword ptr [rsp+148h+dwOptions], rsi; int
0x18010e34e  mov     r9d, 7; dwType
  ... truncated ...
```
