# DoProperties(HWND__ *,ushort const *)

- ea: `0x180014c90`
- end: `0x180015248`
- name: `?DoProperties@@YAXPEAUHWND__@@PEBG@Z`
- size: `1464`
- prototype: `void __fastcall(HWND, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800141a0`

## callees

- `0x18000dce0`
- `0x18000f4d4`
- `0x180012f38`
- `0x1800130b4`
- `0x18001319c`
- `0x180013544`
- `0x180014c90`
- `0x180016d40`
- `0x180016e00`
- `0x180017c28`
- `0x180017c60`
- `0x1800201d8`
- `0x1800243f8`
- `0x180029cd4`
- `0x18002a112`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014e50`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014e7b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014ea8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014ede`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014f13`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014f4b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014f7d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014fb2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014e50`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014e7b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014ea8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014ede`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014f13`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014f4b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014f7d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014fb2`
- `KERNEL32!NlsCheckPolicy` at `0x18001517a`
- `KERNEL32!NlsCheckPolicy` at `0x1800151af`
- `KERNEL32!NlsCheckPolicy` at `0x18001517a`
- `KERNEL32!NlsCheckPolicy` at `0x1800151af`
- `ntdll!WinSqmIsOptedIn` at `0x1800151d5`
- `ntdll!WinSqmIsOptedIn` at `0x1800151d5`
- `ntdll!WinSqmIncrementDWORD` at `0x1800151ef`
- `ntdll!WinSqmIncrementDWORD` at `0x1800151ef`
- `SHELL32!ShellExecuteW` at `0x180014fec`
- `SHELL32!ShellExecuteW` at `0x180014fec`
- `USER32!SetProcessDPIAware` at `0x180014d1f`
- `USER32!SetProcessDPIAware` at `0x180014d1f`

## string_xrefs

- `0x180014cfa`: `OpeningIntlCpl`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DoProperties(HWND a1, unsigned __int16 *a2)
{
  __int64 v4; // rsi
  int v5; // r14d
  int v6; // edi
  __int64 v7; // r8
  unsigned __int16 v8; // ax
  WCHAR *v9; // rdx
  WCHAR v10; // ax
  unsigned int v11; // ecx
  unsigned __int16 v12; // ax
  unsigned __int16 *v13; // rdx
  unsigned __int16 v14; // ax
  unsigned int v15; // ecx
  int v16; // eax
  unsigned int v17; // edi
  __int64 v18; // rdx
  unsigned int v19; // ecx
  unsigned __int16 v20; // ax
  __int64 v21; // r8
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  PROPSHEETHEADERW_V2 v23; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v24; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v25[42]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR String1[88]; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned __int16 v27[520]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6F8h] [rbp+5F8h]

  v4 = 0;
  memset_0(v27, 0, sizeof(v27));
  memset_0(String1, 0, 0xAAu);
  v5 = 0;
  v6 = 0;
  wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v25,
    "OpeningIntlCpl");
  v25[0] = &IntlCplTraceLoggingTelemetry::OpeningIntlCpl::`vftable';
  IntlCplTraceLoggingTelemetry::OpeningIntlCpl::StartActivity((IntlCplTraceLoggingTelemetry::OpeningIntlCpl *)v25);
  SetProcessDPIAware();
  Input_LoadAndInitFunctions();
  McGenEventRegister_EventRegister();
  memset_0(&v23, 0, sizeof(v23));
  v23.nStartPage = -1;
LABEL_2:
  v7 = 85;
  while ( a2 && *a2 )
  {
    if ( *a2 != 47 )
    {
      if ( *a2 != 32 )
        break;
      goto LABEL_56;
    }
    switch ( *++a2 )
    {
      case 'F':
        goto LABEL_43;
      case 'P':
        goto LABEL_16;
      case 'R':
        goto LABEL_15;
      case 'U':
        goto LABEL_14;
      case 'f':
LABEL_43:
        v6 = 1;
        g_fDoNotShowUI = 1;
        v12 = *++a2;
        if ( *a2 == 58 )
        {
          if ( *++a2 == 34 )
          {
            ++a2;
            v13 = v27;
            v14 = *a2;
            if ( !*a2 )
            {
LABEL_52:
              *v13 = 0;
              v12 = *a2;
              goto LABEL_53;
            }
            v15 = 0;
            do
            {
              if ( v14 == 34 )
                break;
              if ( v15 >= 0x208 )
                goto LABEL_51;
              *v13++ = v14;
              ++a2;
              ++v15;
              v14 = *a2;
            }
            while ( *a2 );
            if ( v15 < 0x208 )
              goto LABEL_52;
LABEL_51:
            v27[0] = 0;
          }
        }
        else
        {
LABEL_53:
          if ( v12 == 34 )
            goto LABEL_56;
        }
        break;
      case 'p':
LABEL_16:
        v8 = *++a2;
        if ( *a2 != 58 )
          goto LABEL_26;
        if ( *++a2 != 34 )
          goto LABEL_27;
        ++a2;
        v9 = String1;
        v10 = *a2;
        if ( *a2 )
        {
          v11 = 0;
          do
          {
            if ( v10 == 34 )
              break;
            if ( v11 >= 0x55 )
              goto LABEL_24;
            *v9++ = v10;
            ++a2;
            ++v11;
            v10 = *a2;
          }
          while ( *a2 );
          if ( v11 < 0x55 )
            goto LABEL_25;
LABEL_24:
          String1[0] = 0;
        }
        else
        {
LABEL_25:
          *v9 = 0;
          v8 = *a2;
LABEL_26:
          if ( v8 != 34 )
          {
LABEL_27:
            if ( CompareStringOrdinal(String1, -1, szLanguagePage, -1, 1) == 2
              || CompareStringOrdinal(String1, -1, szKeyboardPage, -1, 1) == 2 )
            {
              ShellExecuteW(0, 0, L"ms-settings:regionlanguage", 0, 0, 1);
            }
            else if ( CompareStringOrdinal(String1, -1, szAdminPage, -1, 1) == 2 )
            {
              v23.nStartPage = 1;
            }
            else
            {
              if ( CompareStringOrdinal(String1, -1, szNumbersPage, -1, 1) == 2 )
              {
                g_dwCustomizeStartPage = 0;
              }
              else if ( CompareStringOrdinal(String1, -1, szCurrencyPage, -1, 1) == 2 )
              {
                g_dwCustomizeStartPage = 1;
              }
              else if ( CompareStringOrdinal(String1, -1, szTimePage, -1, 1) == 2 )
              {
                g_dwCustomizeStartPage = 2;
              }
              else if ( CompareStringOrdinal(String1, -1, szDatePage, -1, 1) == 2 )
              {
                g_dwCustomizeStartPage = 3;
              }
              else if ( CompareStringOrdinal(String1, -1, szSortPage, -1, 1) == 2 )
              {
                g_dwCustomizeStartPage = 4;
              }
              v23.nStartPage = 0;
            }
            goto LABEL_2;
          }
LABEL_56:
          ++a2;
        }
        break;
      case 'r':
LABEL_15:
        v4 |= 1uLL;
        v23.nStartPage = 0;
        goto LABEL_56;
      case 'u':
LABEL_14:
        v5 = 1;
        g_fDoNotShowUI = 1;
        break;
    }
  }
  if ( v6 && (v16 = SetRegionalAndLanguageSettings(v27), v17 = v16, v16 < 0) )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x34B,
      (unsigned int)"shell\\osshell\\cpls\\intl\\intl.cpp",
      (const char *)(unsigned int)v16,
      bIgnoreCase);
    Input_Unload();
    v18 = v17;
  }
  else
  {
    if ( v5 )
      Region_UpdateShortDate();
    if ( !g_fDoNotShowUI )
    {
      if ( v23.nStartPage == -1 )
      {
        v19 = 0;
        v23.nStartPage = 0;
        if ( a2 )
        {
          v20 = *a2;
          if ( *a2 >= 0x30u )
          {
            do
            {
              if ( v20 > 0x39u )
                break;
              v19 = v20 + 2 * (5 * v19 - 24);
              v20 = *++a2;
            }
            while ( *a2 >= 0x30u );
            v23.nStartPage = v19 < 2 ? v19 : 0;
          }
        }
      }
      v24 = 0;
      v23.dwSize = 96;
      v23.dwFlags = 33554688;
      v23.hwndParent = a1;
      v23.hInstance = hInstance;
      v23.nPages = 0;
      v23.ppsp = (LPCPROPSHEETPAGEW)&v24;
      v23.pfnCallback = (PFNPROPSHEETCALLBACK)IntlCPLPropSheetCallback;
      v23.pszCaption = (LPCWSTR)1;
      if ( !(unsigned int)NlsCheckPolicy(L"HideLocaleSelectAndCustomize", 256, v7) )
      {
        Intl_AddPage(&v23, 0x65u, (__int64 (*)(HWND, unsigned int, unsigned __int64, __int64))GeneralDlgProc, v4, 2u);
        g_bIsFormatsEnabled = 1;
      }
      if ( !(unsigned int)NlsCheckPolicy(L"HideAdminOptions", 256, v21) )
        Intl_AddPage(&v23, 0x68u, (__int64 (*)(HWND, unsigned int, unsigned __int64, __int64))AdvancedDlgProc, v4, 2u);
      if ( (unsigned int)WinSqmIsOptedIn() )
      {
        g_fWinSqmIsOptedIn = 1;
        WinSqmIncrementDWORD(0, 3767, 1);
      }
      PropertySheetW(&v23);
    }
    Input_Unload();
    v18 = 0;
  }
  wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v25, v18);
  McGenEventUnregister_EventUnregister();
  IntlCplTraceLoggingTelemetry::OpeningIntlCpl::~OpeningIntlCpl((IntlCplTraceLoggingTelemetry::OpeningIntlCpl *)v25);
}

```

## disassembly

```asm
0x180014c90  mov     [rsp-8+arg_10], rbx
0x180014c95  push    rbp
0x180014c96  push    rsi
0x180014c97  push    rdi
0x180014c98  push    r12
0x180014c9a  push    r13
0x180014c9c  push    r14
0x180014c9e  push    r15
0x180014ca0  lea     rbp, [rsp-5C0h]
0x180014ca8  sub     rsp, 6C0h
0x180014caf  mov     rax, cs:__security_cookie
0x180014cb6  xor     rax, rsp
0x180014cb9  mov     [rbp+5F0h+var_40], rax
0x180014cc0  mov     rbx, rdx
0x180014cc3  mov     r15, rcx
0x180014cc6  xor     r12d, r12d
0x180014cc9  mov     esi, r12d
0x180014ccc  xor     edx, edx; Val
0x180014cce  mov     r8d, 410h; Size
0x180014cd4  lea     rcx, [rbp+5F0h+var_450]; void *
0x180014cdb  call    memset_0
0x180014ce0  xor     edx, edx; Val
0x180014ce2  mov     r8d, 0AAh; Size
0x180014ce8  lea     rcx, [rbp+5F0h+String1]; void *
0x180014cef  call    memset_0
0x180014cf4  mov     r14d, r12d
0x180014cf7  mov     edi, r12d
0x180014cfa  lea     rdx, aOpeningintlcpl; "OpeningIntlCpl"
0x180014d01  lea     rcx, [rbp+5F0h+var_650]
0x180014d05  call    ??0?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180014d0a  lea     rax, ??_7OpeningIntlCpl@IntlCplTraceLoggingTelemetry@@6B@; const IntlCplTraceLoggingTelemetry::OpeningIntlCpl::`vftable'
0x180014d11  mov     [rbp+5F0h+var_650], rax
0x180014d15  lea     rcx, [rbp+5F0h+var_650]; this
0x180014d19  call    ?StartActivity@OpeningIntlCpl@IntlCplTraceLoggingTelemetry@@QEAAXXZ; IntlCplTraceLoggingTelemetry::OpeningIntlCpl::StartActivity(void)
0x180014d1e  nop
0x180014d1f  call    cs:__imp_SetProcessDPIAware
0x180014d25  call    ?Input_LoadAndInitFunctions@@YAHXZ; Input_LoadAndInitFunctions(void)
0x180014d2a  call    McGenEventRegister_EventRegister
0x180014d2f  xor     edx, edx; Val
0x180014d31  lea     r8d, [r12+60h]; Size
0x180014d36  lea     rcx, [rsp+6F0h+var_6C0]; void *
0x180014d3b  call    memset_0
0x180014d40  mov     dword ptr [rsp+6F0h+var_6C0.30h], 0FFFFFFFFh
0x180014d48  lea     r13d, [r12+2]
0x180014d4d  mov     r8d, 55h ; 'U'
0x180014d53  test    rbx, rbx
0x180014d56  jz      loc_180015087
0x180014d5c  cmp     [rbx], r12w
0x180014d60  jz      loc_180015087
0x180014d66  cmp     word ptr [rbx], 2Fh ; '/'
0x180014d6a  jnz     loc_180015079
0x180014d70  add     rbx, r13
0x180014d73  cmp     word ptr [rbx], 46h ; 'F'
0x180014d77  jz      loc_180014FF7
0x180014d7d  cmp     word ptr [rbx], 50h ; 'P'
0x180014d81  jz      short loc_180014DC8
0x180014d83  cmp     word ptr [rbx], 52h ; 'R'
0x180014d87  jz      short loc_180014DBA
0x180014d89  cmp     [rbx], r8w
0x180014d8d  jz      short loc_180014DAB
0x180014d8f  cmp     word ptr [rbx], 66h ; 'f'
0x180014d93  jz      loc_180014FF7
0x180014d99  cmp     word ptr [rbx], 70h ; 'p'
0x180014d9d  jz      short loc_180014DC8
0x180014d9f  cmp     word ptr [rbx], 72h ; 'r'
0x180014da3  jz      short loc_180014DBA
0x180014da5  cmp     word ptr [rbx], 75h ; 'u'
0x180014da9  jnz     short loc_180014D53
0x180014dab  mov     r14d, 1
0x180014db1  mov     cs:?g_fDoNotShowUI@@3HA, r14d; int g_fDoNotShowUI
0x180014db8  jmp     short loc_180014D53
0x180014dba  or      rsi, 1
0x180014dbe  mov     dword ptr [rsp+6F0h+var_6C0.30h], r12d
0x180014dc3  jmp     loc_18001507F
0x180014dc8  add     rbx, r13
0x180014dcb  movzx   eax, word ptr [rbx]
0x180014dce  cmp     ax, 3Ah ; ':'
0x180014dd2  jnz     short loc_180014E29
0x180014dd4  add     rbx, r13
0x180014dd7  cmp     word ptr [rbx], 22h ; '"'
0x180014ddb  jnz     short loc_180014E33
0x180014ddd  add     rbx, r13
0x180014de0  lea     rdx, [rbp+5F0h+String1]
0x180014de7  movzx   eax, word ptr [rbx]
0x180014dea  test    ax, ax
0x180014ded  jz      short loc_180014E22
0x180014def  mov     ecx, r12d
0x180014df2  cmp     ax, 22h ; '"'
0x180014df6  jz      short loc_180014E10
0x180014df8  cmp     ecx, r8d
0x180014dfb  jnb     short loc_180014E15
0x180014dfd  mov     [rdx], ax
0x180014e00  add     rdx, r13
0x180014e03  add     rbx, r13
0x180014e06  inc     ecx
0x180014e08  movzx   eax, word ptr [rbx]
0x180014e0b  test    ax, ax
0x180014e0e  jnz     short loc_180014DF2
0x180014e10  cmp     ecx, r8d
0x180014e13  jb      short loc_180014E22
0x180014e15  mov     [rbp+5F0h+String1], r12w
0x180014e1d  jmp     loc_180014D53
0x180014e22  mov     [rdx], r12w
0x180014e26  movzx   eax, word ptr [rbx]
0x180014e29  cmp     ax, 22h ; '"'
0x180014e2d  jz      loc_18001507F
0x180014e33  mov     [rsp+6F0h+bIgnoreCase], 1; bIgnoreCase
0x180014e3b  or      r9d, 0FFFFFFFFh; cchCount2
0x180014e3f  lea     r8, ?szLanguagePage@@3PAGA; "language"
0x180014e46  or      edx, r9d; cchCount1
0x180014e49  lea     rcx, [rbp+5F0h+String1]; lpString1
0x180014e50  call    cs:__imp_CompareStringOrdinal
0x180014e56  cmp     eax, r13d
0x180014e59  jz      loc_180014FD1
0x180014e5f  mov     [rsp+6F0h+bIgnoreCase], 1; bIgnoreCase
0x180014e67  or      edx, 0FFFFFFFFh; cchCount1
0x180014e6a  mov     r9d, edx; cchCount2
0x180014e6d  lea     r8, ?szKeyboardPage@@3PAGA; "keyboard"
0x180014e74  lea     rcx, [rbp+5F0h+String1]; lpString1
0x180014e7b  call    cs:__imp_CompareStringOrdinal
0x180014e81  cmp     eax, r13d
0x180014e84  jz      loc_180014FD1
0x180014e8a  mov     [rsp+6F0h+bIgnoreCase], 1; bIgnoreCase
0x180014e92  or      eax, 0FFFFFFFFh
0x180014e95  mov     r9d, eax; cchCount2
0x180014e98  lea     r8, ?szAdminPage@@3PAGA; "administrative"
0x180014e9f  mov     edx, eax; cchCount1
0x180014ea1  lea     rcx, [rbp+5F0h+String1]; lpString1
0x180014ea8  call    cs:__imp_CompareStringOrdinal
0x180014eae  cmp     eax, r13d
0x180014eb1  jnz     short loc_180014EC0
0x180014eb3  mov     dword ptr [rsp+6F0h+var_6C0.30h], 1
0x180014ebb  jmp     loc_180014D4D
0x180014ec0  mov     [rsp+6F0h+bIgnoreCase], 1; bIgnoreCase
0x180014ec8  or      eax, 0FFFFFFFFh
0x180014ecb  mov     r9d, eax; cchCount2
0x180014ece  lea     r8, ?szNumbersPage@@3PAGA; "numbers"
0x180014ed5  mov     edx, eax; cchCount1
0x180014ed7  lea     rcx, [rbp+5F0h+String1]; lpString1
0x180014ede  call    cs:__imp_CompareStringOrdinal
0x180014ee4  cmp     eax, r13d
0x180014ee7  jnz     short loc_180014EF5
0x180014ee9  mov     cs:?g_dwCustomizeStartPage@@3KA, r12d; ulong g_dwCustomizeStartPage
0x180014ef0  jmp     loc_180014FC7
0x180014ef5  mov     [rsp+6F0h+bIgnoreCase], 1; bIgnoreCase
0x180014efd  or      eax, 0FFFFFFFFh
0x180014f00  mov     r9d, eax; cchCount2
0x180014f03  lea     r8, ?szCurrencyPage@@3PAGA; "currency"
0x180014f0a  mov     edx, eax; cchCount1
0x180014f0c  lea     rcx, [rbp+5F0h+String1]; lpString1
0x180014f13  call    cs:__imp_CompareStringOrdinal
0x180014f19  cmp     eax, r13d
0x180014f1c  jnz     short loc_180014F2D
0x180014f1e  mov     cs:?g_dwCustomizeStartPage@@3KA, 1; ulong g_dwCustomizeStartPage
0x180014f28  jmp     loc_180014FC7
0x180014f2d  mov     [rsp+6F0h+bIgnoreCase], 1; bIgnoreCase
0x180014f35  or      eax, 0FFFFFFFFh
0x180014f38  mov     r9d, eax; cchCount2
0x180014f3b  lea     r8, ?szTimePage@@3PAGA; "time"
0x180014f42  mov     edx, eax; cchCount1
0x180014f44  lea     rcx, [rbp+5F0h+String1]; lpString1
0x180014f4b  call    cs:__imp_CompareStringOrdinal
0x180014f51  cmp     eax, r13d
0x180014f54  jnz     short loc_180014F5F
0x180014f56  mov     cs:?g_dwCustomizeStartPage@@3KA, r13d; ulong g_dwCustomizeStartPage
0x180014f5d  jmp     short loc_180014FC7
0x180014f5f  mov     [rsp+6F0h+bIgnoreCase], 1; bIgnoreCase
0x180014f67  or      eax, 0FFFFFFFFh
0x180014f6a  mov     r9d, eax; cchCount2
0x180014f6d  lea     r8, ?szDatePage@@3PAGA; "date"
0x180014f74  mov     edx, eax; cchCount1
0x180014f76  lea     rcx, [rbp+5F0h+String1]; lpString1
0x180014f7d  call    cs:__imp_CompareStringOrdinal
0x180014f83  cmp     eax, r13d
0x180014f86  jnz     short loc_180014F94
0x180014f88  mov     cs:?g_dwCustomizeStartPage@@3KA, 3; ulong g_dwCustomizeStartPage
0x180014f92  jmp     short loc_180014FC7
0x180014f94  mov     [rsp+6F0h+bIgnoreCase], 1; bIgnoreCase
0x180014f9c  or      eax, 0FFFFFFFFh
0x180014f9f  mov     r9d, eax; cchCount2
0x180014fa2  lea     r8, ?szSortPage@@3PAGA; "sorting"
0x180014fa9  mov     edx, eax; cchCount1
0x180014fab  lea     rcx, [rbp+5F0h+String1]; lpString1
0x180014fb2  call    cs:__imp_CompareStringOrdinal
0x180014fb8  cmp     eax, r13d
0x180014fbb  jnz     short loc_180014FC7
0x180014fbd  mov     cs:?g_dwCustomizeStartPage@@3KA, 4; ulong g_dwCustomizeStartPage
0x180014fc7  mov     dword ptr [rsp+6F0h+var_6C0.30h], r12d
0x180014fcc  jmp     loc_180014D4D
0x180014fd1  mov     [rsp+6F0h+nShowCmd], 1; nShowCmd
0x180014fd9  mov     qword ptr [rsp+6F0h+bIgnoreCase], r12; lpDirectory
0x180014fde  xor     r9d, r9d; lpParameters
0x180014fe1  lea     r8, File; "ms-settings:regionlanguage"
0x180014fe8  xor     edx, edx; lpOperation
0x180014fea  xor     ecx, ecx; hwnd
0x180014fec  call    cs:__imp_ShellExecuteW
0x180014ff2  jmp     loc_180014D4D
0x180014ff7  mov     edi, 1
0x180014ffc  mov     cs:?g_fDoNotShowUI@@3HA, edi; int g_fDoNotShowUI
0x180015002  add     rbx, r13
0x180015005  movzx   eax, word ptr [rbx]
0x180015008  cmp     ax, 3Ah ; ':'
0x18001500c  jnz     short loc_18001506D
0x18001500e  add     rbx, r13
0x180015011  cmp     word ptr [rbx], 22h ; '"'
0x180015015  jnz     loc_180014D53
0x18001501b  add     rbx, r13
0x18001501e  lea     rdx, [rbp+5F0h+var_450]
0x180015025  movzx   eax, word ptr [rbx]
0x180015028  test    ax, ax
0x18001502b  jz      short loc_180015066
0x18001502d  mov     ecx, r12d
0x180015030  cmp     ax, 22h ; '"'
0x180015034  jz      short loc_180015051
0x180015036  cmp     ecx, 208h
0x18001503c  jnb     short loc_180015059
0x18001503e  mov     [rdx], ax
0x180015041  add     rdx, r13
0x180015044  add     rbx, r13
0x180015047  inc     ecx
0x180015049  movzx   eax, word ptr [rbx]
0x18001504c  test    ax, ax
0x18001504f  jnz     short loc_180015030
0x180015051  cmp     ecx, 208h
0x180015057  jb      short loc_180015066
0x180015059  mov     [rbp+5F0h+var_450], r12w
0x180015061  jmp     loc_180014D53
0x180015066  mov     [rdx], r12w
0x18001506a  movzx   eax, word ptr [rbx]
0x18001506d  cmp     ax, 22h ; '"'
0x180015071  jnz     loc_180014D53
0x180015077  jmp     short loc_18001507F
0x180015079  cmp     word ptr [rbx], 20h ; ' '
0x18001507d  jnz     short loc_180015087
0x18001507f  add     rbx, r13
0x180015082  jmp     loc_180014D53
0x180015087  test    edi, edi
0x180015089  jz      short loc_1800150C4
0x18001508b  lea     rcx, [rbp+5F0h+var_450]; unsigned __int16 *
0x180015092  call    ?SetRegionalAndLanguageSettings@@YAJPEAG@Z; SetRegionalAndLanguageSettings(ushort *)
0x180015097  mov     edi, eax
0x180015099  mov     rcx, [rbp+5F8h]; this
0x1800150a0  test    eax, eax
0x1800150a2  jns     short loc_1800150C4
0x1800150a4  mov     r9d, eax; char *
0x1800150a7  lea     r8, aShellOsshellCp; "shell\\osshell\\cpls\\intl\\intl.cpp"
0x1800150ae  mov     edx, 34Bh; void *
0x1800150b3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800150b8  call    ?Input_Unload@@YAXXZ; Input_Unload(void)
0x1800150bd  mov     edx, edi
0x1800150bf  jmp     loc_180015206
0x1800150c4  test    r14d, r14d
0x1800150c7  jz      short loc_1800150CE
0x1800150c9  call    ?Region_UpdateShortDate@@YAXXZ; Region_UpdateShortDate(void)
0x1800150ce  cmp     cs:?g_fDoNotShowUI@@3HA, r12d; int g_fDoNotShowUI
0x1800150d5  jnz     loc_1800151FF
0x1800150db  cmp     dword ptr [rsp+6F0h+var_6C0.30h], 0FFFFFFFFh
0x1800150e0  jnz     short loc_180015120
0x1800150e2  mov     ecx, r12d
0x1800150e5  mov     dword ptr [rsp+6F0h+var_6C0.30h], ecx
0x1800150e9  test    rbx, rbx
0x1800150ec  jz      short loc_180015120
0x1800150ee  movzx   eax, word ptr [rbx]
0x1800150f1  cmp     ax, 30h ; '0'
0x1800150f5  jb      short loc_180015120
0x1800150f7  cmp     ax, 39h ; '9'
0x1800150fb  ja      short loc_180015115
0x1800150fd  lea     ecx, [rcx+rcx*4]
0x180015100  movzx   eax, ax
0x180015103  lea     ecx, [rcx-18h]
0x180015106  lea     ecx, [rax+rcx*2]
0x180015109  add     rbx, r13
0x18001510c  movzx   eax, word ptr [rbx]
0x18001510f  cmp     ax, 30h ; '0'
0x180015113  jnb     short loc_1800150F7
0x180015115  cmp     ecx, r13d
0x180015118  sbb     eax, eax
0x18001511a  and     eax, ecx
0x18001511c  mov     dword ptr [rsp+6F0h+var_6C0.30h], eax
0x180015120  xorps   xmm0, xmm0
0x180015123  movups  [rbp+5F0h+var_660], xmm0
0x180015127  mov     [rsp+6F0h+var_6C0.dwSize], 60h ; '`'
0x18001512f  mov     [rsp+6F0h+var_6C0.dwFlags], 2000100h
0x180015137  mov     [rsp+6F0h+var_6C0.hwndParent], r15
0x18001513c  mov     rax, cs:?hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * hInstance
0x180015143  mov     [rsp+6F0h+var_6C0.hInstance], rax
0x180015148  mov     [rsp+6F0h+var_6C0.nPages], r12d
0x18001514d  lea     rax, [rbp+5F0h+var_660]
0x180015151  mov     qword ptr [rsp+6F0h+var_6C0.38h], rax
0x180015156  lea     rax, ?IntlCPLPropSheetCallback@@YAHPEAUHWND__@@I_J@Z; IntlCPLPropSheetCallback(HWND__ *,uint,__int64)
0x18001515d  mov     [rsp+6F0h+var_6C0.pfnCallback], rax
0x180015162  mov     ebx, 1
0x180015167  mov     [rsp+6F0h+var_6C0.pszCaption], rbx
0x18001516c  mov     edi, 100h
0x180015171  mov     edx, edi
0x180015173  lea     rcx, ?c_szNlsPolicyHideLocaleTab@@3QBGB; "HideLocaleSelectAndCustomize"
0x18001517a  call    cs:__imp_NlsCheckPolicy
0x180015180  test    eax, eax
0x180015182  jnz     short loc_1800151A6
0x180015184  mov     [rsp+6F0h+bIgnoreCase], r13d; unsigned int
  ... truncated ...
```
