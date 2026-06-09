# GetRegistryValues(_CONSOLE_STATE_INFO *)

- ea: `0x1800114d4`
- end: `0x180011c61`
- name: `?GetRegistryValues@@YAKPEAU_CONSOLE_STATE_INFO@@@Z`
- size: `1933`
- prototype: `unsigned int __fastcall(struct _CONSOLE_STATE_INFO *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000752c`
- `0x180013ce0`

## callees

- `0x1800015b0`
- `0x180005ea4`
- `0x18000b254`
- `0x1800114d4`
- `0x180018580`
- `0x1800186bc`
- `0x1800186e4`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x180011776`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x180011776`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800115e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800115f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011c0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011c19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011c29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800115e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800115f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011c0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011c19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011c29`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegGetBoolUSValueW` at `0x18001152c`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegGetBoolUSValueW` at `0x180011554`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegGetBoolUSValueW` at `0x18001152c`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegGetBoolUSValueW` at `0x180011554`

## string_xrefs

- `0x180011739`: `onecore\windows\core\console\open\src\propsheet\registry.cpp`
- `0x180011b43`: `InterceptCopyPaste`

## pseudocode

```c
__int64 __fastcall GetRegistryValues(struct _CONSOLE_STATE_INFO *a1)
{
  HKEY v3; // r14
  UINT v4; // r15d
  HKEY v5; // rcx
  unsigned int i; // esi
  int v7; // ecx
  const char *v8; // r9
  int v9; // ecx
  __int16 v10; // eax^2
  __int16 v11; // eax^2
  int v12; // eax
  UINT v13; // ecx
  __int16 v14; // eax^2
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  char v18; // al
  UINT CodePage; // [rsp+30h] [rbp-39h] BYREF
  HKEY v20; // [rsp+38h] [rbp-31h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-29h] BYREF
  HKEY v22; // [rsp+48h] [rbp-21h] BYREF
  wchar_t v23[8]; // [rsp+50h] [rbp-19h] BYREF
  __int128 v24; // [rsp+60h] [rbp-9h]
  __int128 v25; // [rsp+70h] [rbp+7h]
  __int128 v26; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v22 = 0;
  hKey = 0;
  v20 = 0;
  CodePage = 0;
  g_fForceV2 = SHRegGetBoolUSValueW(L"Console", L"ForceV2", 0, 1);
  g_fEditKeys = SHRegGetBoolUSValueW(L"Console", L"ExtendedEditKey", 0, 1);
  if ( (int)RegistrySerialization::s_OpenConsoleKey(&v22, &hKey) < 0 )
    return 0;
  v3 = hKey;
  v4 = 0;
  v5 = hKey;
  if ( a1 )
  {
    if ( *((char *)a1 + 96) >= 0 )
    {
      if ( RegistrySerialization::s_OpenKey(hKey, *((const WCHAR **)a1 + 24), &v20) < 0 )
      {
        RegCloseKey(v3);
        RegCloseKey(v22);
        return 0;
      }
      v5 = v20;
    }
    else
    {
      v20 = hKey;
    }
    if ( (int)RegistrySerialization::s_QueryValue(v5, L"ScreenColors", 4u, 4u, (unsigned __int8 *const)&CodePage, 0) >= 0 )
      *((_WORD *)a1 + 50) = CodePage;
    if ( (int)RegistrySerialization::s_QueryValue(v20, L"PopupColors", 4u, 4u, (unsigned __int8 *const)&CodePage, 0) >= 0 )
      *((_WORD *)a1 + 51) = CodePage;
    for ( i = 0; i < 0x10; ++i )
    {
      StringCchPrintfW(v23, 0x20u, L"ColorTable%02u", i);
      if ( (int)RegistrySerialization::s_QueryValue(v20, v23, 4u, 4u, (unsigned __int8 *const)&CodePage, 0) >= 0 )
        *((_DWORD *)a1 + i + 28) = CodePage;
    }
    if ( (int)RegistrySerialization::s_QueryValue(v20, L"InsertMode", 4u, 4u, (unsigned __int8 *const)&CodePage, 0) >= 0 )
    {
      v7 = -(CodePage != 0);
      *((_DWORD *)a1 + 24) &= ~8u;
      *((_DWORD *)a1 + 24) |= v7 & 8;
    }
    if ( (int)RegistrySerialization::s_QueryValue(v20, L"QuickEdit", 4u, 4u, (unsigned __int8 *const)&CodePage, 0) >= 0 )
    {
      v9 = -(CodePage != 0);
      *((_DWORD *)a1 + 24) &= ~2u;
      *((_DWORD *)a1 + 24) |= v9 & 2;
    }
    if ( !OEMCP )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x135,
        (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
        v8);
    if ( (int)RegistrySerialization::s_QueryValue(v20, L"CodePage", 4u, 4u, (unsigned __int8 *const)&CodePage, 0) >= 0
      && IsValidCodePage(CodePage) )
    {
      *((_DWORD *)a1 + 52) = CodePage;
    }
    if ( (int)RegistrySerialization::s_QueryValue(
                v20,
                L"ScreenBufferSize",
                4u,
                4u,
                (unsigned __int8 *const)&CodePage,
                0) >= 0 )
    {
      v10 = HIWORD(CodePage);
      *(_WORD *)a1 = CodePage;
      *((_WORD *)a1 + 1) = v10;
    }
    if ( (int)RegistrySerialization::s_QueryValue(v20, L"WindowSize", 4u, 4u, (unsigned __int8 *const)&CodePage, 0) >= 0 )
    {
      v11 = HIWORD(CodePage);
      *((_WORD *)a1 + 2) = CodePage;
      *((_WORD *)a1 + 3) = v11;
    }
    if ( (int)RegistrySerialization::s_QueryValue(v20, L"WindowPosition", 4u, 4u, (unsigned __int8 *const)&CodePage, 0) >= 0 )
    {
      v12 = (__int16)CodePage;
      v13 = HIWORD(CodePage);
      *((_DWORD *)a1 + 24) &= ~4u;
      *((_DWORD *)a1 + 2) = v12;
      *((_DWORD *)a1 + 3) = (__int16)v13;
    }
    if ( (int)RegistrySerialization::s_QueryValue(v20, L"FontSize", 4u, 4u, (unsigned __int8 *const)&CodePage, 0) >= 0 )
    {
      v14 = HIWORD(CodePage);
      *((_WORD *)a1 + 8) = CodePage;
      *((_WORD *)a1 + 9) = v14;
    }
    if ( (int)RegistrySerialization::s_QueryValue(v20, L"FontFamily", 4u, 4u, (unsigned __int8 *const)&CodePage, 0) >= 0 )
      *((_DWORD *)a1 + 5) = CodePage;
    if ( (int)RegistrySerialization::s_QueryValue(v20, L"FontWeight", 4u, 4u, (unsigned __int8 *const)&CodePage, 0) >= 0 )
      *((_DWORD *)a1 + 6) = CodePage;
    if ( (int)RegistrySerialization::s_QueryValue(v20, L"FaceName", 0x40u, 1u, (unsigned __int8 *const)v23, 0) >= 0 )
    {
      v15 = v24;
      *(_OWORD *)((char *)a1 + 28) = *(_OWORD *)v23;
      v16 = v25;
      *(_OWORD *)((char *)a1 + 44) = v15;
      v17 = v26;
      *(_OWORD *)((char *)a1 + 60) = v16;
      *(_OWORD *)((char *)a1 + 76) = v17;
    }
    if ( (int)RegistrySerialization::s_QueryValue(v20, L"CursorSize", 4u, 4u, (unsigned __int8 *const)&CodePage, 0) >= 0 )
      *((_DWORD *)a1 + 23) = CodePage;
    if ( (int)RegistrySerialization::s_QueryValue(
                v20,
                L"HistoryBufferSize",
                4u,
                4u,
                (unsigned __int8 *const)&CodePage,
                0) >= 0 )
      *((_DWORD *)a1 + 26) = CodePage;
    if ( (int)RegistrySerialization::s_QueryValue(
                v20,
                L"NumberOfHistoryBuffers",
                4u,
                4u,
                (unsigned __int8 *const)&CodePage,
                0) >= 0 )
      *((_DWORD *)a1 + 27) = CodePage;
    if ( (int)RegistrySerialization::s_QueryValue(v20, L"HistoryNoDup", 4u, 4u, (unsigned __int8 *const)&CodePage, 0) >= 0 )
    {
      v18 = CodePage;
      *((_DWORD *)a1 + 24) &= ~0x10u;
      *((_DWORD *)a1 + 24) |= 16 * (v18 & 1);
    }
    if ( (int)RegistrySerialization::s_QueryValue(v20, L"LineWrap", 4u, 4u, (unsigned __int8 *const)&CodePage, 0) >= 0 )
      *((_DWORD *)a1 + 54) = CodePage;
    if ( (int)RegistrySerialization::s_QueryValue(v20, L"FilterOnPaste", 4u, 4u, (unsigned __int8 *const)&CodePage, 0) >= 0 )
      *((_DWORD *)a1 + 55) = CodePage;
    if ( (int)RegistrySerialization::s_QueryValue(
                v20,
                L"CtrlKeyShortcutsDisabled",
                4u,
                4u,
                (unsigned __int8 *const)&CodePage,
                0) >= 0 )
      *((_DWORD *)a1 + 56) = CodePage;
    if ( (int)RegistrySerialization::s_QueryValue(v20, L"LineSelection", 4u, 4u, (unsigned __int8 *const)&CodePage, 0) >= 0 )
      *((_DWORD *)a1 + 57) = CodePage;
    if ( (int)RegistrySerialization::s_QueryValue(v20, L"WindowAlpha", 4u, 4u, (unsigned __int8 *const)&CodePage, 0) >= 0
      && CodePage <= 0xFF )
    {
      *((_BYTE *)a1 + 232) = CodePage;
    }
    if ( (int)RegistrySerialization::s_QueryValue(v20, L"CursorColor", 4u, 4u, (unsigned __int8 *const)&CodePage, 0) >= 0 )
      *((_DWORD *)a1 + 61) = CodePage;
    if ( (int)RegistrySerialization::s_QueryValue(v20, L"CursorType", 4u, 4u, (unsigned __int8 *const)&CodePage, 0) >= 0 )
      *((_DWORD *)a1 + 60) = CodePage;
    if ( (int)RegistrySerialization::s_QueryValue(
                v20,
                L"InterceptCopyPaste",
                4u,
                4u,
                (unsigned __int8 *const)&CodePage,
                0) >= 0 )
      *((_DWORD *)a1 + 62) = CodePage != 0;
    if ( (int)RegistrySerialization::s_QueryValue(
                v20,
                L"DefaultForeground",
                4u,
                4u,
                (unsigned __int8 *const)&CodePage,
                0) >= 0 )
      *((_DWORD *)a1 + 63) = CodePage;
    if ( (int)RegistrySerialization::s_QueryValue(
                v20,
                L"DefaultBackground",
                4u,
                4u,
                (unsigned __int8 *const)&CodePage,
                0) >= 0 )
      *((_DWORD *)a1 + 64) = CodePage;
    if ( (int)RegistrySerialization::s_QueryValue(
                v20,
                L"TerminalScrolling",
                4u,
                4u,
                (unsigned __int8 *const)&CodePage,
                0) >= 0 )
      *((_DWORD *)a1 + 65) = CodePage;
    if ( v20 != v3 )
      RegCloseKey(v20);
  }
  else if ( (int)RegistrySerialization::s_QueryValue(hKey, L"CurrentPage", 4u, 4u, (unsigned __int8 *const)&CodePage, 0) >= 0 )
  {
    v4 = CodePage;
  }
  RegCloseKey(v3);
  RegCloseKey(v22);
  return v4;
}

```

## disassembly

```asm
0x1800114d4  mov     [rsp-8+arg_8], rbx
0x1800114d9  mov     [rsp-8+arg_10], rsi
0x1800114de  push    rbp
0x1800114df  push    rdi
0x1800114e0  push    r12
0x1800114e2  push    r14
0x1800114e4  push    r15
0x1800114e6  lea     rbp, [rsp-37h]
0x1800114eb  sub     rsp, 0A0h
0x1800114f2  mov     rax, cs:__security_cookie
0x1800114f9  xor     rax, rsp
0x1800114fc  mov     [rbp+57h+var_30], rax
0x180011500  xor     r12d, r12d
0x180011503  lea     rdx, pszValue; "ForceV2"
0x18001150a  mov     rbx, rcx
0x18001150d  mov     [rbp+57h+var_78], r12
0x180011511  xor     r8d, r8d; fIgnoreHKCU
0x180011514  mov     [rbp+57h+hKey], r12
0x180011518  lea     rcx, aConsole; "Console"
0x18001151f  mov     [rbp+57h+var_88], r12
0x180011523  lea     r9d, [r12+1]; fDefault
0x180011528  mov     [rbp+57h+CodePage], r12d
0x18001152c  call    cs:__imp_SHRegGetBoolUSValueW
0x180011533  nop     dword ptr [rax+rax+00h]
0x180011538  lea     r9d, [r12+1]; fDefault
0x18001153d  xor     r8d, r8d; fIgnoreHKCU
0x180011540  lea     rdx, aExtendededitke; "ExtendedEditKey"
0x180011547  mov     cs:?g_fForceV2@@3HA, eax; int g_fForceV2
0x18001154d  lea     rcx, aConsole; "Console"
0x180011554  call    cs:__imp_SHRegGetBoolUSValueW
0x18001155b  nop     dword ptr [rax+rax+00h]
0x180011560  lea     rdx, [rbp+57h+hKey]; HKEY *
0x180011564  mov     cs:?g_fEditKeys@@3HA, eax; int g_fEditKeys
0x18001156a  lea     rcx, [rbp+57h+var_78]; HKEY *
0x18001156e  call    ?s_OpenConsoleKey@RegistrySerialization@@SAJPEAPEAUHKEY__@@0@Z; RegistrySerialization::s_OpenConsoleKey(HKEY__ * *,HKEY__ * *)
0x180011573  test    eax, eax
0x180011575  jns     short loc_18001157E
0x180011577  xor     eax, eax
0x180011579  jmp     loc_180011C38
0x18001157e  mov     r14, [rbp+57h+hKey]
0x180011582  mov     r15d, r12d
0x180011585  mov     rcx, r14; HKEY
0x180011588  test    rbx, rbx
0x18001158b  jnz     short loc_1800115C1
0x18001158d  lea     edi, [rbx+4]
0x180011590  mov     [rsp+0C0h+var_98], r12; unsigned int *
0x180011595  lea     rax, [rbp+57h+CodePage]
0x180011599  mov     r9d, edi; unsigned int
0x18001159c  mov     r8d, edi; unsigned int
0x18001159f  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 *
0x1800115a4  lea     rdx, aCurrentpage; "CurrentPage"
0x1800115ab  call    ?s_QueryValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WKKQEAEQEAK@Z; RegistrySerialization::s_QueryValue(HKEY__ * const,wchar_t const * const,ulong,ulong,uchar * const,ulong * const)
0x1800115b0  test    eax, eax
0x1800115b2  js      loc_180011C16
0x1800115b8  mov     r15d, [rbp+57h+CodePage]
0x1800115bc  jmp     loc_180011C16
0x1800115c1  test    byte ptr [rbx+60h], 80h
0x1800115c5  jz      short loc_1800115CD
0x1800115c7  mov     [rbp+57h+var_88], rcx
0x1800115cb  jmp     short loc_180011609
0x1800115cd  mov     rdx, [rbx+0C0h]; wchar_t *
0x1800115d4  lea     r8, [rbp+57h+var_88]; HKEY *
0x1800115d8  call    ?s_OpenKey@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WQEAPEAU2@@Z; RegistrySerialization::s_OpenKey(HKEY__ * const,wchar_t const * const,HKEY__ * * const)
0x1800115dd  test    eax, eax
0x1800115df  jns     short loc_180011605
0x1800115e1  mov     rcx, r14; hKey
0x1800115e4  call    cs:__imp_RegCloseKey
0x1800115eb  nop     dword ptr [rax+rax+00h]
0x1800115f0  mov     rcx, [rbp+57h+var_78]; hKey
0x1800115f4  call    cs:__imp_RegCloseKey
0x1800115fb  nop     dword ptr [rax+rax+00h]
0x180011600  jmp     loc_180011577
0x180011605  mov     rcx, [rbp+57h+var_88]; HKEY
0x180011609  mov     edi, 4
0x18001160e  mov     [rsp+0C0h+var_98], r12; unsigned int *
0x180011613  lea     rax, [rbp+57h+CodePage]
0x180011617  mov     r9d, edi; unsigned int
0x18001161a  mov     r8d, edi; unsigned int
0x18001161d  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 *
0x180011622  lea     rdx, aScreencolors; "ScreenColors"
0x180011629  call    ?s_QueryValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WKKQEAEQEAK@Z; RegistrySerialization::s_QueryValue(HKEY__ * const,wchar_t const * const,ulong,ulong,uchar * const,ulong * const)
0x18001162e  test    eax, eax
0x180011630  js      short loc_18001163A
0x180011632  movzx   eax, word ptr [rbp+57h+CodePage]
0x180011636  mov     [rbx+64h], ax
0x18001163a  mov     rcx, [rbp+57h+var_88]; HKEY
0x18001163e  lea     rax, [rbp+57h+CodePage]
0x180011642  mov     [rsp+0C0h+var_98], r12; unsigned int *
0x180011647  lea     rdx, aPopupcolors; "PopupColors"
0x18001164e  mov     r9d, edi; unsigned int
0x180011651  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 *
0x180011656  mov     r8d, edi; unsigned int
0x180011659  call    ?s_QueryValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WKKQEAEQEAK@Z; RegistrySerialization::s_QueryValue(HKEY__ * const,wchar_t const * const,ulong,ulong,uchar * const,ulong * const)
0x18001165e  test    eax, eax
0x180011660  js      short loc_18001166A
0x180011662  movzx   eax, word ptr [rbp+57h+CodePage]
0x180011666  mov     [rbx+66h], ax
0x18001166a  mov     esi, r12d
0x18001166d  mov     r9d, esi
0x180011670  lea     r8, aColortable02u; "ColorTable%02u"
0x180011677  mov     edx, 20h ; ' '; unsigned __int64
0x18001167c  lea     rcx, [rbp+57h+var_70]; wchar_t *
0x180011680  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180011685  mov     rcx, [rbp+57h+var_88]; HKEY
0x180011689  lea     rax, [rbp+57h+CodePage]
0x18001168d  mov     [rsp+0C0h+var_98], r12; unsigned int *
0x180011692  lea     rdx, [rbp+57h+var_70]; wchar_t *
0x180011696  mov     r9d, edi; unsigned int
0x180011699  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 *
0x18001169e  mov     r8d, edi; unsigned int
0x1800116a1  call    ?s_QueryValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WKKQEAEQEAK@Z; RegistrySerialization::s_QueryValue(HKEY__ * const,wchar_t const * const,ulong,ulong,uchar * const,ulong * const)
0x1800116a6  test    eax, eax
0x1800116a8  js      short loc_1800116B3
0x1800116aa  mov     eax, [rbp+57h+CodePage]
0x1800116ad  mov     ecx, esi
0x1800116af  mov     [rbx+rcx*4+70h], eax
0x1800116b3  inc     esi
0x1800116b5  cmp     esi, 10h
0x1800116b8  jb      short loc_18001166D
0x1800116ba  mov     rcx, [rbp+57h+var_88]; HKEY
0x1800116be  lea     rax, [rbp+57h+CodePage]
0x1800116c2  mov     [rsp+0C0h+var_98], r12; unsigned int *
0x1800116c7  lea     rdx, aInsertmode; "InsertMode"
0x1800116ce  mov     r9d, edi; unsigned int
0x1800116d1  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 *
0x1800116d6  mov     r8d, edi; unsigned int
0x1800116d9  call    ?s_QueryValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WKKQEAEQEAK@Z; RegistrySerialization::s_QueryValue(HKEY__ * const,wchar_t const * const,ulong,ulong,uchar * const,ulong * const)
0x1800116de  test    eax, eax
0x1800116e0  js      short loc_1800116F3
0x1800116e2  mov     eax, [rbp+57h+CodePage]
0x1800116e5  neg     eax
0x1800116e7  sbb     ecx, ecx
0x1800116e9  and     dword ptr [rbx+60h], 0FFFFFFF7h
0x1800116ed  and     ecx, 8
0x1800116f0  or      [rbx+60h], ecx
0x1800116f3  mov     rcx, [rbp+57h+var_88]; HKEY
0x1800116f7  lea     rax, [rbp+57h+CodePage]
0x1800116fb  mov     [rsp+0C0h+var_98], r12; unsigned int *
0x180011700  lea     rdx, aQuickedit; "QuickEdit"
0x180011707  mov     r9d, edi; unsigned int
0x18001170a  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 *
0x18001170f  mov     r8d, edi; unsigned int
0x180011712  call    ?s_QueryValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WKKQEAEQEAK@Z; RegistrySerialization::s_QueryValue(HKEY__ * const,wchar_t const * const,ulong,ulong,uchar * const,ulong * const)
0x180011717  test    eax, eax
0x180011719  js      short loc_18001172C
0x18001171b  mov     eax, [rbp+57h+CodePage]
0x18001171e  neg     eax
0x180011720  sbb     ecx, ecx
0x180011722  and     dword ptr [rbx+60h], 0FFFFFFFDh
0x180011726  and     ecx, 2
0x180011729  or      [rbx+60h], ecx
0x18001172c  cmp     cs:?OEMCP@@3IA, r12d; uint OEMCP
0x180011733  jnz     short loc_18001174B
0x180011735  mov     rcx, [rbp+5Fh]; this
0x180011739  lea     r8, aOnecoreWindows_1; "onecore\\windows\\core\\console\\open\\"...
0x180011740  mov     edx, 135h; void *
0x180011745  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001174b  mov     rcx, [rbp+57h+var_88]; HKEY
0x18001174f  lea     rax, [rbp+57h+CodePage]
0x180011753  mov     [rsp+0C0h+var_98], r12; unsigned int *
0x180011758  lea     rdx, aCodepage; "CodePage"
0x18001175f  mov     r9d, edi; unsigned int
0x180011762  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 *
0x180011767  mov     r8d, edi; unsigned int
0x18001176a  call    ?s_QueryValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WKKQEAEQEAK@Z; RegistrySerialization::s_QueryValue(HKEY__ * const,wchar_t const * const,ulong,ulong,uchar * const,ulong * const)
0x18001176f  test    eax, eax
0x180011771  js      short loc_18001178F
0x180011773  mov     ecx, [rbp+57h+CodePage]; CodePage
0x180011776  call    cs:__imp_IsValidCodePage
0x18001177d  nop     dword ptr [rax+rax+00h]
0x180011782  test    eax, eax
0x180011784  jz      short loc_18001178F
0x180011786  mov     eax, [rbp+57h+CodePage]
0x180011789  mov     [rbx+0D0h], eax
0x18001178f  mov     rcx, [rbp+57h+var_88]; HKEY
0x180011793  lea     rax, [rbp+57h+CodePage]
0x180011797  mov     [rsp+0C0h+var_98], r12; unsigned int *
0x18001179c  lea     rdx, aScreenbuffersi; "ScreenBufferSize"
0x1800117a3  mov     r9d, edi; unsigned int
0x1800117a6  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 *
0x1800117ab  mov     r8d, edi; unsigned int
0x1800117ae  call    ?s_QueryValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WKKQEAEQEAK@Z; RegistrySerialization::s_QueryValue(HKEY__ * const,wchar_t const * const,ulong,ulong,uchar * const,ulong * const)
0x1800117b3  test    eax, eax
0x1800117b5  js      short loc_1800117C4
0x1800117b7  mov     eax, [rbp+57h+CodePage]
0x1800117ba  mov     [rbx], ax
0x1800117bd  shr     eax, 10h
0x1800117c0  mov     [rbx+2], ax
0x1800117c4  mov     rcx, [rbp+57h+var_88]; HKEY
0x1800117c8  lea     rax, [rbp+57h+CodePage]
0x1800117cc  mov     [rsp+0C0h+var_98], r12; unsigned int *
0x1800117d1  lea     rdx, aWindowsize; "WindowSize"
0x1800117d8  mov     r9d, edi; unsigned int
0x1800117db  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 *
0x1800117e0  mov     r8d, edi; unsigned int
0x1800117e3  call    ?s_QueryValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WKKQEAEQEAK@Z; RegistrySerialization::s_QueryValue(HKEY__ * const,wchar_t const * const,ulong,ulong,uchar * const,ulong * const)
0x1800117e8  test    eax, eax
0x1800117ea  js      short loc_1800117FA
0x1800117ec  mov     eax, [rbp+57h+CodePage]
0x1800117ef  mov     [rbx+4], ax
0x1800117f3  shr     eax, 10h
0x1800117f6  mov     [rbx+6], ax
0x1800117fa  mov     rcx, [rbp+57h+var_88]; HKEY
0x1800117fe  lea     rax, [rbp+57h+CodePage]
0x180011802  mov     [rsp+0C0h+var_98], r12; unsigned int *
0x180011807  lea     rdx, aWindowposition; "WindowPosition"
0x18001180e  mov     r9d, edi; unsigned int
0x180011811  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 *
0x180011816  mov     r8d, edi; unsigned int
0x180011819  call    ?s_QueryValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WKKQEAEQEAK@Z; RegistrySerialization::s_QueryValue(HKEY__ * const,wchar_t const * const,ulong,ulong,uchar * const,ulong * const)
0x18001181e  test    eax, eax
0x180011820  js      short loc_180011838
0x180011822  mov     ecx, [rbp+57h+CodePage]
0x180011825  movsx   eax, cx
0x180011828  shr     ecx, 10h
0x18001182b  and     dword ptr [rbx+60h], 0FFFFFFFBh
0x18001182f  mov     [rbx+8], eax
0x180011832  movsx   eax, cx
0x180011835  mov     [rbx+0Ch], eax
0x180011838  mov     rcx, [rbp+57h+var_88]; HKEY
0x18001183c  lea     rax, [rbp+57h+CodePage]
0x180011840  mov     [rsp+0C0h+var_98], r12; unsigned int *
0x180011845  lea     rdx, aFontsize; "FontSize"
0x18001184c  mov     r9d, edi; unsigned int
0x18001184f  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 *
0x180011854  mov     r8d, edi; unsigned int
0x180011857  call    ?s_QueryValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WKKQEAEQEAK@Z; RegistrySerialization::s_QueryValue(HKEY__ * const,wchar_t const * const,ulong,ulong,uchar * const,ulong * const)
0x18001185c  test    eax, eax
0x18001185e  js      short loc_18001186E
0x180011860  mov     eax, [rbp+57h+CodePage]
0x180011863  mov     [rbx+10h], ax
0x180011867  shr     eax, 10h
0x18001186a  mov     [rbx+12h], ax
0x18001186e  mov     rcx, [rbp+57h+var_88]; HKEY
0x180011872  lea     rax, [rbp+57h+CodePage]
0x180011876  mov     [rsp+0C0h+var_98], r12; unsigned int *
0x18001187b  lea     rdx, aFontfamily; "FontFamily"
0x180011882  mov     r9d, edi; unsigned int
0x180011885  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 *
0x18001188a  mov     r8d, edi; unsigned int
0x18001188d  call    ?s_QueryValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WKKQEAEQEAK@Z; RegistrySerialization::s_QueryValue(HKEY__ * const,wchar_t const * const,ulong,ulong,uchar * const,ulong * const)
0x180011892  test    eax, eax
0x180011894  js      short loc_18001189C
0x180011896  mov     eax, [rbp+57h+CodePage]
0x180011899  mov     [rbx+14h], eax
0x18001189c  mov     rcx, [rbp+57h+var_88]; HKEY
0x1800118a0  lea     rax, [rbp+57h+CodePage]
0x1800118a4  mov     [rsp+0C0h+var_98], r12; unsigned int *
0x1800118a9  lea     rdx, aFontweight; "FontWeight"
0x1800118b0  mov     r9d, edi; unsigned int
0x1800118b3  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 *
0x1800118b8  mov     r8d, edi; unsigned int
0x1800118bb  call    ?s_QueryValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WKKQEAEQEAK@Z; RegistrySerialization::s_QueryValue(HKEY__ * const,wchar_t const * const,ulong,ulong,uchar * const,ulong * const)
0x1800118c0  test    eax, eax
0x1800118c2  js      short loc_1800118CA
0x1800118c4  mov     eax, [rbp+57h+CodePage]
0x1800118c7  mov     [rbx+18h], eax
0x1800118ca  mov     rcx, [rbp+57h+var_88]; HKEY
0x1800118ce  lea     rax, [rbp+57h+var_70]
0x1800118d2  mov     r9d, 1; unsigned int
0x1800118d8  mov     [rsp+0C0h+var_98], r12; unsigned int *
0x1800118dd  lea     rdx, aFacename; "FaceName"
0x1800118e4  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 *
0x1800118e9  lea     r8d, [r9+3Fh]; unsigned int
0x1800118ed  call    ?s_QueryValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WKKQEAEQEAK@Z; RegistrySerialization::s_QueryValue(HKEY__ * const,wchar_t const * const,ulong,ulong,uchar * const,ulong * const)
0x1800118f2  test    eax, eax
0x1800118f4  js      short loc_180011916
0x1800118f6  movaps  xmm0, xmmword ptr [rbp+57h+var_70]
0x1800118fa  movaps  xmm1, [rbp+57h+var_60]
0x1800118fe  movups  xmmword ptr [rbx+1Ch], xmm0
0x180011902  movaps  xmm0, [rbp+57h+var_50]
0x180011906  movups  xmmword ptr [rbx+2Ch], xmm1
0x18001190a  movaps  xmm1, [rbp+57h+var_40]
0x18001190e  movups  xmmword ptr [rbx+3Ch], xmm0
0x180011912  movups  xmmword ptr [rbx+4Ch], xmm1
0x180011916  mov     rcx, [rbp+57h+var_88]; HKEY
0x18001191a  lea     rax, [rbp+57h+CodePage]
0x18001191e  mov     [rsp+0C0h+var_98], r12; unsigned int *
0x180011923  lea     rdx, aCursorsize; "CursorSize"
0x18001192a  mov     r9d, edi; unsigned int
0x18001192d  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 *
0x180011932  mov     r8d, edi; unsigned int
0x180011935  call    ?s_QueryValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WKKQEAEQEAK@Z; RegistrySerialization::s_QueryValue(HKEY__ * const,wchar_t const * const,ulong,ulong,uchar * const,ulong * const)
0x18001193a  test    eax, eax
0x18001193c  js      short loc_180011944
0x18001193e  mov     eax, [rbp+57h+CodePage]
0x180011941  mov     [rbx+5Ch], eax
0x180011944  mov     rcx, [rbp+57h+var_88]; HKEY
0x180011948  lea     rax, [rbp+57h+CodePage]
0x18001194c  mov     [rsp+0C0h+var_98], r12; unsigned int *
0x180011951  lea     rdx, aHistorybuffers; "HistoryBufferSize"
0x180011958  mov     r9d, edi; unsigned int
0x18001195b  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 *
0x180011960  mov     r8d, edi; unsigned int
0x180011963  call    ?s_QueryValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WKKQEAEQEAK@Z; RegistrySerialization::s_QueryValue(HKEY__ * const,wchar_t const * const,ulong,ulong,uchar * const,ulong * const)
0x180011968  test    eax, eax
0x18001196a  js      short loc_180011972
0x18001196c  mov     eax, [rbp+57h+CodePage]
0x18001196f  mov     [rbx+68h], eax
0x180011972  mov     rcx, [rbp+57h+var_88]; HKEY
  ... truncated ...
```
