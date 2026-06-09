# Microsoft::Diagnostics::Utils::Registry::SetQword(HKEY__ *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,unsigned __int64,ulong)

- ea: `0x18001ef98`
- end: `0x18001f2fe`
- name: `?SetQword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1_KK@Z`
- size: `870`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD)`
- caller_count: `24`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d49c`
- `0x18001e1a0`
- `0x18001e290`
- `0x180032498`
- `0x18010e61c`
- `0x180128fc0`
- `0x1801411b0`
- `0x1801418d8`
- `0x180148d5c`
- `0x18014cffc`
- `0x180150580`
- `0x180154d78`
- `0x1801b0664`
- `0x1801e02b4`
- `0x1801f5b00`
- `0x180201b08`
- `0x180204e10`
- `0x1802457fc`
- `0x18026d280`
- `0x18027afc0`
- `0x1802d2e70`
- `0x1802dd9d0`
- `0x1803236d0`
- `0x18032cdf0`

## callees

- `0x18001ef98`
- `0x18001f304`
- `0x180020db8`
- `0x18002be90`
- `0x18002df00`
- `0x180064e8c`
- `0x18010f8f4`
- `0x18020aac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f1c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f1c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f1af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f1af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f17b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f1ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f215`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f26f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f17b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f1ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f215`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f26f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f098`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f098`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f121`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f121`

## string_xrefs

- `0x18001f1d8`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x18001f232`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x18001f2ad`: `onecore\base\telemetry\utc\include\RegistryUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::Utils::Registry::SetQword(
        HKEY a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        DWORD a5)
{
  HKEY v7; // rsi
  const WCHAR *v8; // rdx
  LSTATUS v9; // eax
  unsigned int v10; // ebx
  HKEY v11; // rbx
  const WCHAR *v12; // rdx
  int v13; // eax
  unsigned int v14; // ebx
  DWORD LastError; // ebx
  int dwOptions; // [rsp+20h] [rbp-F8h]
  int dwOptionsa; // [rsp+20h] [rbp-F8h]
  int dwOptionsb; // [rsp+20h] [rbp-F8h]
  char *v20; // [rsp+50h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-B0h] BYREF
  BYTE Data[8]; // [rsp+70h] [rbp-A8h] BYREF
  _QWORD v24[5]; // [rsp+78h] [rbp-A0h] BYREF
  char v25; // [rsp+A0h] [rbp-78h]
  LPCWSTR lpValueName[2]; // [rsp+B0h] [rbp-68h] BYREF
  __int128 v27; // [rsp+C0h] [rbp-58h]
  LPCWSTR lpSubKey[4]; // [rsp+D0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  hKey = a1;
  *(_QWORD *)Data = a4;
  LODWORD(v20) = 0;
  phkResult = 0;
  v24[0] = &hKey;
  v24[1] = a2;
  v24[2] = a3;
  v24[3] = Data;
  v24[4] = &v20;
  v25 = 1;
  *(_OWORD *)lpValueName = *(_OWORD *)a2;
  Microsoft::Diagnostics::Utils::Registry::TryExpandKeyName((LPCWSTR)lpSubKey);
  if ( *(_QWORD *)(a2 + 8) )
  {
    v7 = phkResult;
    if ( phkResult )
    {
      LastError = GetLastError();
      RegCloseKey(v7);
      SetLastError(LastError);
    }
    phkResult = 0;
    v8 = (const WCHAR *)lpSubKey;
    if ( lpSubKey[3] > (LPCWSTR)7 )
      v8 = lpSubKey[0];
    v9 = RegCreateKeyExW(hKey, v8, 0, 0, a5, 2u, 0, &phkResult, 0);
    v10 = v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    LODWORD(v20) = v10;
    if ( (v10 & 0x80000000) == 0 )
    {
      v11 = phkResult;
LABEL_10:
      *(_OWORD *)lpValueName = 0;
      v27 = 0;
      std::wstring::_Construct<1,wchar_t *>(lpValueName, *a3, a3[1]);
      v12 = (const WCHAR *)lpValueName;
      if ( *((_QWORD *)&v27 + 1) > 7u )
        v12 = lpValueName[0];
      v13 = RegSetValueExW(v11, v12, 0, 0xBu, Data, 8u);
      if ( v13 > 0 )
        v13 = (unsigned __int16)v13 | 0x80070000;
      LODWORD(v20) = v13;
      std::wstring::_Tidy_deallocate(lpValueName);
      v14 = (unsigned int)v20;
      if ( (int)v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x509,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
          (const char *)(unsigned int)v20,
          dwOptionsb);
        std::wstring::_Tidy_deallocate(lpSubKey);
        v25 = 0;
        `Microsoft::Diagnostics::Utils::Registry::SetQword'::`2'::_lambda_1_::operator()(v24);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        return v14;
      }
      else
      {
        std::wstring::_Tidy_deallocate(lpSubKey);
        v25 = 0;
        `Microsoft::Diagnostics::Utils::Registry::SetQword'::`2'::_lambda_1_::operator()(v24);
        if ( phkResult )
          RegCloseKey(phkResult);
        return 0;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4FF,
      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
      (const char *)v10,
      dwOptionsa);
    std::wstring::_Tidy_deallocate(lpSubKey);
    v25 = 0;
    `Microsoft::Diagnostics::Utils::Registry::SetQword'::`2'::_lambda_1_::operator()(v24);
    if ( phkResult )
      RegCloseKey(phkResult);
    return v10;
  }
  else
  {
    v11 = hKey;
    if ( hKey )
      goto LABEL_10;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x505,
      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
      (const char *)0x80070057LL,
      dwOptions);
    std::wstring::_Tidy_deallocate(lpSubKey);
    v25 = 0;
    `Microsoft::Diagnostics::Utils::Registry::SetQword'::`2'::_lambda_1_::operator()(v24);
    if ( phkResult )
      RegCloseKey(phkResult);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18001ef98  mov     r11, rsp
0x18001ef9b  push    rbx
0x18001ef9c  push    rsi
0x18001ef9d  push    r14
0x18001ef9f  sub     rsp, 100h
0x18001efa6  mov     rax, cs:__security_cookie
0x18001efad  xor     rax, rsp
0x18001efb0  mov     [rsp+118h+var_28], rax
0x18001efb8  mov     r14, r8
0x18001efbb  mov     rbx, rdx
0x18001efbe  mov     [rsp+118h+hKey], rcx
0x18001efc3  mov     qword ptr [rsp+118h+Data], r9
0x18001efc8  mov     dword ptr [rsp+118h+var_C8], 0
0x18001efd0  mov     [rsp+118h+var_C0], 0
0x18001efd9  lea     rax, [rsp+118h+hKey]
0x18001efde  mov     [rsp+118h+var_A0], rax
0x18001efe3  mov     [r11-98h], rdx
0x18001efea  mov     [r11-90h], r8
0x18001eff1  lea     rax, [rsp+118h+Data]
0x18001eff6  mov     [r11-88h], rax
0x18001effd  lea     rax, [rsp+118h+var_C8]
0x18001f002  mov     [r11-80h], rax
0x18001f006  mov     byte ptr [r11-78h], 1
0x18001f00b  movups  xmm0, xmmword ptr [rdx]
0x18001f00e  movdqu  xmmword ptr [r11-68h], xmm0
0x18001f014  lea     rdx, [r11-68h]
0x18001f018  lea     rcx, [r11-48h]
0x18001f01c  call    ?TryExpandKeyName@Registry@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::Utils::Registry::TryExpandKeyName(std::wstring_view)
0x18001f021  nop
0x18001f022  cmp     qword ptr [rbx+8], 0
0x18001f027  jz      loc_18001F19F
0x18001f02d  mov     rsi, [rsp+118h+var_C0]
0x18001f032  test    rsi, rsi
0x18001f035  jnz     loc_18001F1AF
0x18001f03b  mov     [rsp+118h+var_C0], 0
0x18001f044  lea     rdx, [rsp+118h+lpSubKey]
0x18001f04c  cmp     [rsp+118h+var_30], 7
0x18001f055  cmova   rdx, [rsp+118h+lpSubKey]; lpSubKey
0x18001f05e  mov     [rsp+118h+lpdwDisposition], 0; lpdwDisposition
0x18001f067  lea     rax, [rsp+118h+var_C0]
0x18001f06c  mov     [rsp+118h+phkResult], rax; phkResult
0x18001f071  mov     [rsp+118h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001f07a  mov     [rsp+118h+samDesired], 2; samDesired
0x18001f082  mov     eax, [rsp+118h+arg_20]
0x18001f089  mov     [rsp+118h+dwOptions], eax; int
0x18001f08d  xor     r9d, r9d; lpClass
0x18001f090  xor     r8d, r8d; Reserved
0x18001f093  mov     rcx, [rsp+118h+hKey]; hKey
0x18001f098  call    cs:__imp_RegCreateKeyExW
0x18001f09e  mov     ebx, eax
0x18001f0a0  test    eax, eax
0x18001f0a2  jle     short loc_18001F0AD
0x18001f0a4  movzx   ebx, ax
0x18001f0a7  or      ebx, 80070000h
0x18001f0ad  mov     dword ptr [rsp+118h+var_C8], ebx
0x18001f0b1  test    ebx, ebx
0x18001f0b3  js      loc_18001F1CD
0x18001f0b9  mov     rbx, [rsp+118h+var_C0]
0x18001f0be  xorps   xmm0, xmm0
0x18001f0c1  movups  xmmword ptr [rsp+118h+lpValueName], xmm0
0x18001f0c9  xorps   xmm1, xmm1
0x18001f0cc  movdqu  [rsp+118h+var_58], xmm1
0x18001f0d5  mov     r8, [r14+8]
0x18001f0d9  mov     rdx, [r14]
0x18001f0dc  lea     rcx, [rsp+118h+lpValueName]
0x18001f0e4  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x18001f0e9  lea     rdx, [rsp+118h+lpValueName]
0x18001f0f1  cmp     qword ptr [rsp+118h+var_58+8], 7
0x18001f0fa  cmova   rdx, [rsp+118h+lpValueName]; lpValueName
0x18001f103  mov     [rsp+118h+samDesired], 8; cbData
0x18001f10b  lea     rax, [rsp+118h+Data]
0x18001f110  mov     qword ptr [rsp+118h+dwOptions], rax; int
0x18001f115  mov     r9d, 0Bh; dwType
0x18001f11b  xor     r8d, r8d; Reserved
0x18001f11e  mov     rcx, rbx; hKey
0x18001f121  call    cs:__imp_RegSetValueExW
0x18001f127  test    eax, eax
0x18001f129  jle     short loc_18001F133
0x18001f12b  movzx   eax, ax
0x18001f12e  or      eax, 80070000h
0x18001f133  mov     dword ptr [rsp+118h+var_C8], eax
0x18001f137  lea     rcx, [rsp+118h+lpValueName]
0x18001f13f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f144  mov     ebx, dword ptr [rsp+118h+var_C8]
0x18001f148  test    ebx, ebx
0x18001f14a  js      loc_18001F2A2
0x18001f150  lea     rcx, [rsp+118h+lpSubKey]
0x18001f158  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f15d  nop
0x18001f15e  mov     [rsp+118h+var_78], 0
0x18001f166  lea     rcx, [rsp+118h+var_A0]
0x18001f16b  call    ??R_lambda_1_@?1??SetQword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1_KK@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetQword(HKEY__ *,std::wstring_view,std::wstring_view,unsigned __int64,ulong)'::`2'::_lambda_1_::operator()(void)
0x18001f170  nop
0x18001f171  mov     rcx, [rsp+118h+var_C0]; hKey
0x18001f176  test    rcx, rcx
0x18001f179  jz      short loc_18001F181
0x18001f17b  call    cs:__imp_RegCloseKey
0x18001f181  xor     eax, eax
0x18001f183  mov     rcx, [rsp+118h+var_28]
0x18001f18b  xor     rcx, rsp; StackCookie
0x18001f18e  call    __security_check_cookie
0x18001f193  add     rsp, 100h
0x18001f19a  pop     r14
0x18001f19c  pop     rsi
0x18001f19d  pop     rbx
0x18001f19e  retn
0x18001f19f  mov     rbx, [rsp+118h+hKey]
0x18001f1a4  test    rbx, rbx
0x18001f1a7  jnz     loc_18001F0BE
0x18001f1ad  jmp     short loc_18001F222
0x18001f1af  call    cs:__imp_GetLastError
0x18001f1b5  mov     ebx, eax
0x18001f1b7  mov     rcx, rsi; hKey
0x18001f1ba  call    cs:__imp_RegCloseKey
0x18001f1c0  mov     ecx, ebx; dwErrCode
0x18001f1c2  call    cs:__imp_SetLastError
0x18001f1c8  jmp     loc_18001F03B
0x18001f1cd  mov     rcx, [rsp+118h]; this
0x18001f1d5  mov     r9d, ebx; char *
0x18001f1d8  lea     r8, aOnecoreBaseTel_198; "onecore\\base\\telemetry\\utc\\include"...
0x18001f1df  mov     edx, 4FFh; void *
0x18001f1e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f1e9  nop
0x18001f1ea  lea     rcx, [rsp+118h+lpSubKey]
0x18001f1f2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f1f7  nop
0x18001f1f8  mov     [rsp+118h+var_78], 0
0x18001f200  lea     rcx, [rsp+118h+var_A0]
0x18001f205  call    ??R_lambda_1_@?1??SetQword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1_KK@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetQword(HKEY__ *,std::wstring_view,std::wstring_view,unsigned __int64,ulong)'::`2'::_lambda_1_::operator()(void)
0x18001f20a  nop
0x18001f20b  mov     rcx, [rsp+118h+var_C0]; hKey
0x18001f210  test    rcx, rcx
0x18001f213  jz      short loc_18001F21B
0x18001f215  call    cs:__imp_RegCloseKey
0x18001f21b  mov     eax, ebx
0x18001f21d  jmp     loc_18001F183
0x18001f222  mov     rcx, [rsp+118h]; this
0x18001f22a  mov     ebx, 80070057h
0x18001f22f  mov     r9d, ebx; char *
0x18001f232  lea     r8, aOnecoreBaseTel_198; "onecore\\base\\telemetry\\utc\\include"...
0x18001f239  mov     edx, 505h; void *
0x18001f23e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f243  nop
0x18001f244  lea     rcx, [rsp+118h+lpSubKey]
0x18001f24c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f251  nop
0x18001f252  mov     [rsp+118h+var_78], 0
0x18001f25a  lea     rcx, [rsp+118h+var_A0]
0x18001f25f  call    ??R_lambda_1_@?1??SetQword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1_KK@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetQword(HKEY__ *,std::wstring_view,std::wstring_view,unsigned __int64,ulong)'::`2'::_lambda_1_::operator()(void)
0x18001f264  nop
0x18001f265  mov     rcx, [rsp+118h+var_C0]; hKey
0x18001f26a  test    rcx, rcx
0x18001f26d  jz      short loc_18001F275
0x18001f26f  call    cs:__imp_RegCloseKey
0x18001f275  mov     eax, ebx
0x18001f277  jmp     loc_18001F183
0x18001f27c  mov     [rsp+118h+var_78], 0
0x18001f284  lea     rcx, [rsp+118h+var_A0]
0x18001f289  call    ??R_lambda_1_@?1??SetQword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1_KK@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetQword(HKEY__ *,std::wstring_view,std::wstring_view,unsigned __int64,ulong)'::`2'::_lambda_1_::operator()(void)
0x18001f28e  nop
0x18001f28f  lea     rcx, [rsp+118h+var_C0]
0x18001f294  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001f299  mov     eax, [rsp+118h+var_B8]
0x18001f29d  jmp     loc_18001F183
0x18001f2a2  mov     rcx, [rsp+118h]; this
0x18001f2aa  mov     r9d, ebx; char *
0x18001f2ad  lea     r8, aOnecoreBaseTel_198; "onecore\\base\\telemetry\\utc\\include"...
0x18001f2b4  mov     edx, 509h; void *
0x18001f2b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f2be  nop
0x18001f2bf  lea     rcx, [rsp+118h+lpSubKey]
0x18001f2c7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f2cc  nop
0x18001f2cd  mov     [rsp+118h+var_78], 0
0x18001f2d5  lea     rcx, [rsp+118h+var_A0]
0x18001f2da  call    ??R_lambda_1_@?1??SetQword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1_KK@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetQword(HKEY__ *,std::wstring_view,std::wstring_view,unsigned __int64,ulong)'::`2'::_lambda_1_::operator()(void)
0x18001f2df  nop
0x18001f2e0  lea     rcx, [rsp+118h+var_C0]
0x18001f2e5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001f2ea  mov     eax, ebx
0x18001f2ec  jmp     loc_18001F183
0x18001f2f1  cmp     [rsp+118h+var_78], 0
0x18001f2f9  jnz     short loc_18001F27C
0x18001f2fb  jmp     short loc_18001F28F
```
