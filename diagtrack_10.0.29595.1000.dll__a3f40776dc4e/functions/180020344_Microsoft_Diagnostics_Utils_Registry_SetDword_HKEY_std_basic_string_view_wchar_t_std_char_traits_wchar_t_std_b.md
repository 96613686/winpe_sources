# Microsoft::Diagnostics::Utils::Registry::SetDword(HKEY__ *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,ulong,ulong)

- ea: `0x180020344`
- end: `0x1800206ad`
- name: `?SetDword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1KK@Z`
- size: `873`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD dwOptions)`
- caller_count: `33`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e290`
- `0x18001eb58`
- `0x18001ef10`
- `0x18005ea74`
- `0x180087e20`
- `0x18008815c`
- `0x180088560`
- `0x1800886d8`
- `0x1801203ec`
- `0x180128fc0`
- `0x180139d20`
- `0x18014cffc`
- `0x18016211c`
- `0x1801666cc`
- `0x180166884`
- `0x18017a690`
- `0x1801aeb58`
- `0x1801b4520`
- `0x1801e02b4`
- `0x1801e53e8`
- `0x1801e59e8`
- `0x1801e8348`
- `0x1801eb220`
- `0x1801f5b00`
- `0x1801f7008`
- `0x180240be0`
- `0x18026f11c`
- `0x1802835c8`
- `0x1802b2190`
- `0x1802ef7c0`
- `0x1802efa10`
- `0x18030d394`
- `0x1803236d0`

## callees

- `0x180020344`
- `0x1800206b4`
- `0x180020db8`
- `0x18002be90`
- `0x18002df00`
- `0x180064e8c`
- `0x18010f8f4`
- `0x18020aac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002056e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002056e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002055b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002055b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800204a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020566`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800205c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002061b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800204a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020566`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800205c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002061b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020530`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020530`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020447`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020447`

## string_xrefs

- `0x180020589`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x1800205de`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x180020659`: `onecore\base\telemetry\utc\include\RegistryUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::Utils::Registry::SetDword(
        HKEY a1,
        __int64 a2,
        _QWORD *a3,
        int a4,
        DWORD dwOptions)
{
  HKEY v7; // rbx
  const WCHAR *v8; // rdx
  int v9; // eax
  unsigned int v10; // ebx
  HKEY v12; // rsi
  const WCHAR *v13; // rdx
  LSTATUS v14; // eax
  unsigned int v15; // ebx
  DWORD LastError; // ebx
  int lpData; // [rsp+20h] [rbp-F8h]
  int lpDataa; // [rsp+20h] [rbp-F8h]
  int lpDatab; // [rsp+20h] [rbp-F8h]
  char *v20; // [rsp+50h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-C0h] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-A8h] BYREF
  _QWORD v24[5]; // [rsp+78h] [rbp-A0h] BYREF
  char v25; // [rsp+A0h] [rbp-78h]
  LPCWSTR lpValueName[2]; // [rsp+B0h] [rbp-68h] BYREF
  __int128 v27; // [rsp+C0h] [rbp-58h]
  LPCWSTR lpSubKey[4]; // [rsp+D0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  hKey = a1;
  *(_DWORD *)Data = a4;
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
    v12 = phkResult;
    if ( phkResult )
    {
      LastError = GetLastError();
      RegCloseKey(v12);
      SetLastError(LastError);
    }
    phkResult = 0;
    v13 = (const WCHAR *)lpSubKey;
    if ( lpSubKey[3] > (LPCWSTR)7 )
      v13 = lpSubKey[0];
    v14 = RegCreateKeyExW(hKey, v13, 0, 0, dwOptions, 2u, 0, &phkResult, 0);
    v15 = v14;
    if ( v14 > 0 )
      v15 = (unsigned __int16)v14 | 0x80070000;
    LODWORD(v20) = v15;
    if ( (v15 & 0x80000000) == 0 )
    {
      v7 = phkResult;
      goto LABEL_3;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3EC,
      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
      (const char *)v15,
      lpDatab);
    std::wstring::_Tidy_deallocate(lpSubKey);
    v25 = 0;
    `Microsoft::Diagnostics::Utils::Registry::SetDword'::`2'::_lambda_1_::operator()(v24);
    if ( phkResult )
      RegCloseKey(phkResult);
    return v15;
  }
  else
  {
    v7 = hKey;
    if ( hKey )
    {
LABEL_3:
      *(_OWORD *)lpValueName = 0;
      v27 = 0;
      std::wstring::_Construct<1,wchar_t *>(lpValueName, *a3, a3[1]);
      v8 = (const WCHAR *)lpValueName;
      if ( *((_QWORD *)&v27 + 1) > 7u )
        v8 = lpValueName[0];
      v9 = RegSetValueExW(v7, v8, 0, 4u, Data, 4u);
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      LODWORD(v20) = v9;
      std::wstring::_Tidy_deallocate(lpValueName);
      v10 = (unsigned int)v20;
      if ( (int)v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3FC,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
          (const char *)(unsigned int)v20,
          lpDataa);
        std::wstring::_Tidy_deallocate(lpSubKey);
        v25 = 0;
        `Microsoft::Diagnostics::Utils::Registry::SetDword'::`2'::_lambda_1_::operator()(v24);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        return v10;
      }
      else
      {
        std::wstring::_Tidy_deallocate(lpSubKey);
        v25 = 0;
        `Microsoft::Diagnostics::Utils::Registry::SetDword'::`2'::_lambda_1_::operator()(v24);
        if ( phkResult )
          RegCloseKey(phkResult);
        return 0;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F2,
      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
      (const char *)0x80070057LL,
      lpData);
    std::wstring::_Tidy_deallocate(lpSubKey);
    v25 = 0;
    `Microsoft::Diagnostics::Utils::Registry::SetDword'::`2'::_lambda_1_::operator()(v24);
    if ( phkResult )
      RegCloseKey(phkResult);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180020344  mov     r11, rsp
0x180020347  push    rbx
0x180020348  push    rsi
0x180020349  push    r14
0x18002034b  sub     rsp, 100h
0x180020352  mov     rax, cs:__security_cookie
0x180020359  xor     rax, rsp
0x18002035c  mov     [rsp+118h+var_28], rax
0x180020364  mov     r14, r8
0x180020367  mov     rbx, rdx
0x18002036a  mov     [rsp+118h+hKey], rcx
0x18002036f  mov     dword ptr [rsp+118h+Data], r9d
0x180020374  mov     dword ptr [rsp+118h+var_C8], 0
0x18002037c  mov     [rsp+118h+var_C0], 0
0x180020385  lea     rax, [rsp+118h+hKey]
0x18002038a  mov     [rsp+118h+var_A0], rax
0x18002038f  mov     [r11-98h], rdx
0x180020396  mov     [r11-90h], r8
0x18002039d  lea     rax, [rsp+118h+Data]
0x1800203a2  mov     [r11-88h], rax
0x1800203a9  lea     rax, [rsp+118h+var_C8]
0x1800203ae  mov     [r11-80h], rax
0x1800203b2  mov     byte ptr [r11-78h], 1
0x1800203b7  movups  xmm0, xmmword ptr [rdx]
0x1800203ba  movdqu  xmmword ptr [r11-68h], xmm0
0x1800203c0  lea     rdx, [r11-68h]
0x1800203c4  lea     rcx, [r11-48h]
0x1800203c8  call    ?TryExpandKeyName@Registry@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::Utils::Registry::TryExpandKeyName(std::wstring_view)
0x1800203cd  nop
0x1800203ce  cmp     qword ptr [rbx+8], 0
0x1800203d3  jnz     loc_1800204C5
0x1800203d9  mov     rbx, [rsp+118h+hKey]
0x1800203de  test    rbx, rbx
0x1800203e1  jz      loc_180020579
0x1800203e7  xorps   xmm0, xmm0
0x1800203ea  movups  xmmword ptr [rsp+118h+lpValueName], xmm0
0x1800203f2  xorps   xmm1, xmm1
0x1800203f5  movdqu  [rsp+118h+var_58], xmm1
0x1800203fe  mov     r8, [r14+8]
0x180020402  mov     rdx, [r14]
0x180020405  lea     rcx, [rsp+118h+lpValueName]
0x18002040d  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x180020412  lea     rdx, [rsp+118h+lpValueName]
0x18002041a  cmp     qword ptr [rsp+118h+var_58+8], 7
0x180020423  cmova   rdx, [rsp+118h+lpValueName]; lpValueName
0x18002042c  mov     r9d, 4; dwType
0x180020432  mov     [rsp+118h+cbData], r9d; cbData
0x180020437  lea     rax, [rsp+118h+Data]
0x18002043c  mov     [rsp+118h+lpData], rax; int
0x180020441  xor     r8d, r8d; Reserved
0x180020444  mov     rcx, rbx; hKey
0x180020447  call    cs:__imp_RegSetValueExW
0x18002044d  test    eax, eax
0x18002044f  jle     short loc_180020459
0x180020451  movzx   eax, ax
0x180020454  or      eax, 80070000h
0x180020459  mov     dword ptr [rsp+118h+var_C8], eax
0x18002045d  lea     rcx, [rsp+118h+lpValueName]
0x180020465  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002046a  mov     ebx, dword ptr [rsp+118h+var_C8]
0x18002046e  test    ebx, ebx
0x180020470  js      loc_18002064E
0x180020476  lea     rcx, [rsp+118h+lpSubKey]
0x18002047e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020483  nop
0x180020484  mov     [rsp+118h+var_78], 0
0x18002048c  lea     rcx, [rsp+118h+var_A0]
0x180020491  call    ??R_lambda_1_@?1??SetDword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1KK@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetDword(HKEY__ *,std::wstring_view,std::wstring_view,ulong,ulong)'::`2'::_lambda_1_::operator()(void)
0x180020496  nop
0x180020497  mov     rcx, [rsp+118h+var_C0]; hKey
0x18002049c  test    rcx, rcx
0x18002049f  jz      short loc_1800204A7
0x1800204a1  call    cs:__imp_RegCloseKey
0x1800204a7  xor     eax, eax
0x1800204a9  mov     rcx, [rsp+118h+var_28]
0x1800204b1  xor     rcx, rsp; StackCookie
0x1800204b4  call    __security_check_cookie
0x1800204b9  add     rsp, 100h
0x1800204c0  pop     r14
0x1800204c2  pop     rsi
0x1800204c3  pop     rbx
0x1800204c4  retn
0x1800204c5  mov     rsi, [rsp+118h+var_C0]
0x1800204ca  test    rsi, rsi
0x1800204cd  jnz     loc_18002055B
0x1800204d3  mov     [rsp+118h+var_C0], 0
0x1800204dc  lea     rdx, [rsp+118h+lpSubKey]
0x1800204e4  cmp     [rsp+118h+var_30], 7
0x1800204ed  cmova   rdx, [rsp+118h+lpSubKey]; lpSubKey
0x1800204f6  mov     [rsp+118h+lpdwDisposition], 0; lpdwDisposition
0x1800204ff  lea     rax, [rsp+118h+var_C0]
0x180020504  mov     [rsp+118h+phkResult], rax; phkResult
0x180020509  mov     [rsp+118h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180020512  mov     [rsp+118h+cbData], 2; samDesired
0x18002051a  mov     eax, [rsp+118h+dwOptions]
0x180020521  mov     dword ptr [rsp+118h+lpData], eax; int
0x180020525  xor     r9d, r9d; lpClass
0x180020528  xor     r8d, r8d; Reserved
0x18002052b  mov     rcx, [rsp+118h+hKey]; hKey
0x180020530  call    cs:__imp_RegCreateKeyExW
0x180020536  mov     ebx, eax
0x180020538  test    eax, eax
0x18002053a  jle     short loc_180020545
0x18002053c  movzx   ebx, ax
0x18002053f  or      ebx, 80070000h
0x180020545  mov     dword ptr [rsp+118h+var_C8], ebx
0x180020549  test    ebx, ebx
0x18002054b  js      loc_1800205D3
0x180020551  mov     rbx, [rsp+118h+var_C0]
0x180020556  jmp     loc_1800203E7
0x18002055b  call    cs:__imp_GetLastError
0x180020561  mov     ebx, eax
0x180020563  mov     rcx, rsi; hKey
0x180020566  call    cs:__imp_RegCloseKey
0x18002056c  mov     ecx, ebx; dwErrCode
0x18002056e  call    cs:__imp_SetLastError
0x180020574  jmp     loc_1800204D3
0x180020579  mov     rcx, [rsp+118h]; this
0x180020581  mov     ebx, 80070057h
0x180020586  mov     r9d, ebx; char *
0x180020589  lea     r8, aOnecoreBaseTel_198; "onecore\\base\\telemetry\\utc\\include"...
0x180020590  mov     edx, 3F2h; void *
0x180020595  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002059a  nop
0x18002059b  lea     rcx, [rsp+118h+lpSubKey]
0x1800205a3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800205a8  nop
0x1800205a9  mov     [rsp+118h+var_78], 0
0x1800205b1  lea     rcx, [rsp+118h+var_A0]
0x1800205b6  call    ??R_lambda_1_@?1??SetDword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1KK@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetDword(HKEY__ *,std::wstring_view,std::wstring_view,ulong,ulong)'::`2'::_lambda_1_::operator()(void)
0x1800205bb  nop
0x1800205bc  mov     rcx, [rsp+118h+var_C0]; hKey
0x1800205c1  test    rcx, rcx
0x1800205c4  jz      short loc_1800205CC
0x1800205c6  call    cs:__imp_RegCloseKey
0x1800205cc  mov     eax, ebx
0x1800205ce  jmp     loc_1800204A9
0x1800205d3  mov     rcx, [rsp+118h]; this
0x1800205db  mov     r9d, ebx; char *
0x1800205de  lea     r8, aOnecoreBaseTel_198; "onecore\\base\\telemetry\\utc\\include"...
0x1800205e5  mov     edx, 3ECh; void *
0x1800205ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800205ef  nop
0x1800205f0  lea     rcx, [rsp+118h+lpSubKey]
0x1800205f8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800205fd  nop
0x1800205fe  mov     [rsp+118h+var_78], 0
0x180020606  lea     rcx, [rsp+118h+var_A0]
0x18002060b  call    ??R_lambda_1_@?1??SetDword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1KK@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetDword(HKEY__ *,std::wstring_view,std::wstring_view,ulong,ulong)'::`2'::_lambda_1_::operator()(void)
0x180020610  nop
0x180020611  mov     rcx, [rsp+118h+var_C0]; hKey
0x180020616  test    rcx, rcx
0x180020619  jz      short loc_180020621
0x18002061b  call    cs:__imp_RegCloseKey
0x180020621  mov     eax, ebx
0x180020623  jmp     loc_1800204A9
0x180020628  mov     [rsp+118h+var_78], 0
0x180020630  lea     rcx, [rsp+118h+var_A0]
0x180020635  call    ??R_lambda_1_@?1??SetDword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1KK@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetDword(HKEY__ *,std::wstring_view,std::wstring_view,ulong,ulong)'::`2'::_lambda_1_::operator()(void)
0x18002063a  nop
0x18002063b  lea     rcx, [rsp+118h+var_C0]
0x180020640  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180020645  mov     eax, [rsp+118h+var_B0]
0x180020649  jmp     loc_1800204A9
0x18002064e  mov     rcx, [rsp+118h]; this
0x180020656  mov     r9d, ebx; char *
0x180020659  lea     r8, aOnecoreBaseTel_198; "onecore\\base\\telemetry\\utc\\include"...
0x180020660  mov     edx, 3FCh; void *
0x180020665  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002066a  nop
0x18002066b  lea     rcx, [rsp+118h+lpSubKey]
0x180020673  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020678  nop
0x180020679  mov     [rsp+118h+var_78], 0
0x180020681  lea     rcx, [rsp+118h+var_A0]
0x180020686  call    ??R_lambda_1_@?1??SetDword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1KK@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetDword(HKEY__ *,std::wstring_view,std::wstring_view,ulong,ulong)'::`2'::_lambda_1_::operator()(void)
0x18002068b  nop
0x18002068c  lea     rcx, [rsp+118h+var_C0]
0x180020691  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180020696  mov     eax, ebx
0x180020698  jmp     loc_1800204A9
0x18002069d  cmp     [rsp+118h+var_78], 0
0x1800206a5  jz      short loc_18002063B
0x1800206a7  jmp     loc_180020628
```
