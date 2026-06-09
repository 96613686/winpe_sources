# SetRegistryValues(_CONSOLE_STATE_INFO *,ulong)

- ea: `0x180011f44`
- end: `0x18001288c`
- name: `?SetRegistryValues@@YAXPEAU_CONSOLE_STATE_INFO@@K@Z`
- size: `2376`
- prototype: `void __fastcall(struct _CONSOLE_STATE_INFO *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x180007e0c`

## callees

- `0x1800015b0`
- `0x180005ea4`
- `0x180008714`
- `0x18000b254`
- `0x180011eac`
- `0x180011f44`
- `0x18001851c`
- `0x180018544`
- `0x180018580`
- `0x180018760`
- `0x1800187a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012842`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012851`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012861`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012842`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012851`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012861`

## string_xrefs

- `0x180011fc4`: `onecore\windows\core\console\open\src\propsheet\registry.cpp`
- `0x18001272b`: `InterceptCopyPaste`

## pseudocode

```c
void __fastcall SetRegistryValues(struct _CONSOLE_STATE_INFO *a1)
{
  struct _CONSOLE_STATE_INFO *v1; // rdi
  HKEY v2; // rbx
  LSTATUS v3; // eax
  HKEY v4; // rdx
  int updated; // eax
  int v6; // eax
  unsigned int i; // esi
  int v8; // eax
  int v9; // eax
  int v10; // eax
  const char *v11; // r9
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  __int64 v16; // rdx
  int v17; // eax
  int v18; // eax
  int v19; // eax
  __int64 v20; // rax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  int v36; // eax
  int Buf1; // [rsp+20h] [rbp-69h]
  int Buf1a; // [rsp+20h] [rbp-69h]
  int Buf1b; // [rsp+20h] [rbp-69h]
  int Buf1c; // [rsp+20h] [rbp-69h]
  int Buf1d; // [rsp+20h] [rbp-69h]
  int Buf1e; // [rsp+20h] [rbp-69h]
  int Buf1f; // [rsp+20h] [rbp-69h]
  int Buf1g; // [rsp+20h] [rbp-69h]
  int Buf1h; // [rsp+20h] [rbp-69h]
  int Buf1i; // [rsp+20h] [rbp-69h]
  int Buf1j; // [rsp+20h] [rbp-69h]
  int Buf1k; // [rsp+20h] [rbp-69h]
  int Buf1l; // [rsp+20h] [rbp-69h]
  int Buf1m; // [rsp+20h] [rbp-69h]
  int Buf1n; // [rsp+20h] [rbp-69h]
  int Buf1o; // [rsp+20h] [rbp-69h]
  int Buf1p; // [rsp+20h] [rbp-69h]
  int Buf1q; // [rsp+20h] [rbp-69h]
  int Buf1r; // [rsp+20h] [rbp-69h]
  int Buf1s; // [rsp+20h] [rbp-69h]
  int Buf1t; // [rsp+20h] [rbp-69h]
  int Buf1u; // [rsp+20h] [rbp-69h]
  int Buf1v; // [rsp+20h] [rbp-69h]
  int Buf1w; // [rsp+20h] [rbp-69h]
  int Buf1x; // [rsp+20h] [rbp-69h]
  int Buf1y; // [rsp+20h] [rbp-69h]
  int Buf1z; // [rsp+20h] [rbp-69h]
  int Buf1ba; // [rsp+20h] [rbp-69h]
  size_t Size; // [rsp+28h] [rbp-61h]
  size_t Sizea; // [rsp+28h] [rbp-61h]
  size_t Sizeb; // [rsp+28h] [rbp-61h]
  size_t Sizec; // [rsp+28h] [rbp-61h]
  size_t Sized; // [rsp+28h] [rbp-61h]
  size_t Sizee; // [rsp+28h] [rbp-61h]
  size_t Sizef; // [rsp+28h] [rbp-61h]
  size_t Sizeg; // [rsp+28h] [rbp-61h]
  size_t Sizeh; // [rsp+28h] [rbp-61h]
  size_t Sizei; // [rsp+28h] [rbp-61h]
  size_t Sizej; // [rsp+28h] [rbp-61h]
  size_t Sizek; // [rsp+28h] [rbp-61h]
  size_t Sizel; // [rsp+28h] [rbp-61h]
  size_t Sizem; // [rsp+28h] [rbp-61h]
  size_t Sizen; // [rsp+28h] [rbp-61h]
  size_t Sizeo; // [rsp+28h] [rbp-61h]
  size_t Sizep; // [rsp+28h] [rbp-61h]
  size_t Sizeq; // [rsp+28h] [rbp-61h]
  size_t Sizer; // [rsp+28h] [rbp-61h]
  size_t Sizes; // [rsp+28h] [rbp-61h]
  size_t Sizet; // [rsp+28h] [rbp-61h]
  size_t Sizeu; // [rsp+28h] [rbp-61h]
  size_t Sizev; // [rsp+28h] [rbp-61h]
  size_t Sizew; // [rsp+28h] [rbp-61h]
  size_t Sizex; // [rsp+28h] [rbp-61h]
  unsigned __int8 v90[8]; // [rsp+30h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-51h] BYREF
  unsigned __int8 v92[8]; // [rsp+40h] [rbp-49h] BYREF
  HKEY v93; // [rsp+48h] [rbp-41h] BYREF
  HKEY v94; // [rsp+50h] [rbp-39h] BYREF
  wchar_t v95[32]; // [rsp+60h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v1 = gpStateInfo;
  *(_DWORD *)v92 = gnCurrentPage;
  v93 = 0;
  v94 = 0;
  hKey = 0;
  *(_DWORD *)v90 = 0;
  if ( (int)RegistrySerialization::s_OpenConsoleKey(&v93, &v94) >= 0 )
  {
    v2 = v94;
    v3 = RegistrySerialization::s_SetValue(v94, L"CurrentPage", 4u, v92, 4u);
    if ( v3 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2C4,
        (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
        (const char *)(unsigned int)v3,
        Buf1);
    if ( *((char *)v1 + 96) >= 0 )
    {
      if ( RegistrySerialization::s_CreateKey(v2, *((const WCHAR **)v1 + 24), &hKey) < 0 )
      {
LABEL_79:
        RegCloseKey(v2);
        RegCloseKey(v93);
        return;
      }
      v4 = hKey;
    }
    else
    {
      v4 = v2;
      hKey = v2;
    }
    *(_DWORD *)v90 = *((unsigned __int16 *)v1 + 50);
    LODWORD(Size) = 4;
    updated = RegistrySerialization::s_UpdateValue(v2, v4, L"ScreenColors", 4u, v90, Size);
    if ( updated < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2E4,
        (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
        (const char *)(unsigned int)updated,
        Buf1a);
    *(_DWORD *)v90 = *((unsigned __int16 *)v1 + 51);
    LODWORD(Sizea) = 4;
    v6 = RegistrySerialization::s_UpdateValue(v2, hKey, L"PopupColors", 4u, v90, Sizea);
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2EB,
        (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
        (const char *)(unsigned int)v6,
        Buf1b);
    for ( i = 0; i < 0x10; ++i )
    {
      *(_DWORD *)v90 = *((_DWORD *)v1 + i + 28);
      if ( StringCchPrintfW(v95, 0x20u, L"ColorTable%02u", i) >= 0 )
      {
        LODWORD(Sizeb) = 4;
        v8 = RegistrySerialization::s_UpdateValue(v2, hKey, v95, 4u, v90, Sizeb);
        if ( v8 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2F6,
            (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
            (const char *)(unsigned int)v8,
            Buf1c);
      }
    }
    LODWORD(Sizeb) = 4;
    *(_DWORD *)v90 = (*((_DWORD *)v1 + 24) >> 3) & 1;
    v9 = RegistrySerialization::s_UpdateValue(v2, hKey, L"InsertMode", 4u, v90, Sizeb);
    if ( v9 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x304,
        (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
        (const char *)(unsigned int)v9,
        Buf1d);
    LODWORD(Sizec) = 4;
    *(_DWORD *)v90 = (*((_DWORD *)v1 + 24) >> 1) & 1;
    v10 = RegistrySerialization::s_UpdateValue(v2, hKey, L"QuickEdit", 4u, v90, Sizec);
    if ( v10 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x30B,
        (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
        (const char *)(unsigned int)v10,
        Buf1e);
    if ( !OEMCP )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x30D,
        (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
        v11);
    if ( g_fEastAsianSystem )
    {
      *(_DWORD *)v90 = *((_DWORD *)v1 + 52);
      LODWORD(Sized) = 4;
      v12 = RegistrySerialization::s_UpdateValue(v2, hKey, L"CodePage", 4u, v90, Sized);
      if ( v12 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x316,
          (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
          (const char *)(unsigned int)v12,
          Buf1f);
    }
    LODWORD(Sized) = 4;
    *(_DWORD *)v90 = *(_DWORD *)v1;
    v13 = RegistrySerialization::s_UpdateValue(v2, hKey, L"ScreenBufferSize", 4u, v90, Sized);
    if ( v13 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x324,
        (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
        (const char *)(unsigned int)v13,
        Buf1g);
    LODWORD(Sizee) = 4;
    *(_DWORD *)v90 = *((_DWORD *)v1 + 1);
    v14 = RegistrySerialization::s_UpdateValue(v2, hKey, L"WindowSize", 4u, v90, Sizee);
    if ( v14 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x331,
        (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
        (const char *)(unsigned int)v14,
        Buf1h);
    if ( (*((_BYTE *)v1 + 96) & 4) != 0 )
    {
      v15 = RegistrySerialization::s_DeleteValue(hKey, L"WindowPosition");
      if ( v15 < 0 )
      {
        v16 = 825;
LABEL_35:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
          (const char *)(unsigned int)v15,
          Buf1h);
      }
    }
    else
    {
      LODWORD(Sizef) = 4;
      *(_DWORD *)v90 = *((unsigned __int16 *)v1 + 4) | (*((unsigned __int16 *)v1 + 6) << 16);
      v15 = RegistrySerialization::s_UpdateValue(v2, hKey, L"WindowPosition", 4u, v90, Sizef);
      if ( v15 < 0 )
      {
        v16 = 836;
        goto LABEL_35;
      }
    }
    LODWORD(Sizef) = 4;
    *(_DWORD *)v90 = *((_DWORD *)v1 + 4);
    v17 = RegistrySerialization::s_UpdateValue(v2, hKey, L"FontSize", 4u, v90, Sizef);
    if ( v17 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x352,
        (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
        (const char *)(unsigned int)v17,
        Buf1i);
    *(_DWORD *)v90 = *((_DWORD *)v1 + 5);
    LODWORD(Sizeg) = 4;
    v18 = RegistrySerialization::s_UpdateValue(v2, hKey, L"FontFamily", 4u, v90, Sizeg);
    if ( v18 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x359,
        (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
        (const char *)(unsigned int)v18,
        Buf1j);
    *(_DWORD *)v90 = *((_DWORD *)v1 + 6);
    LODWORD(Sizeh) = 4;
    v19 = RegistrySerialization::s_UpdateValue(v2, hKey, L"FontWeight", 4u, v90, Sizeh);
    if ( v19 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x360,
        (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
        (const char *)(unsigned int)v19,
        Buf1k);
    v20 = -1;
    do
      ++v20;
    while ( *((_WORD *)v1 + v20 + 14) );
    LODWORD(Sizei) = 2 * v20 + 2;
    v21 = RegistrySerialization::s_UpdateValue(v2, hKey, L"FaceName", 1u, (unsigned __int8 *)v1 + 28, Sizei);
    if ( v21 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x366,
        (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
        (const char *)(unsigned int)v21,
        Buf1l);
    *(_DWORD *)v90 = *((_DWORD *)v1 + 23);
    LODWORD(Sizej) = 4;
    v22 = RegistrySerialization::s_UpdateValue(v2, hKey, L"CursorSize", 4u, v90, Sizej);
    if ( v22 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x372,
        (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
        (const char *)(unsigned int)v22,
        Buf1m);
    *(_DWORD *)v90 = *((_DWORD *)v1 + 26);
    LODWORD(Sizek) = 4;
    v23 = RegistrySerialization::s_UpdateValue(v2, hKey, L"HistoryBufferSize", 4u, v90, Sizek);
    if ( v23 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x37E,
        (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
        (const char *)(unsigned int)v23,
        Buf1n);
    *(_DWORD *)v90 = *((_DWORD *)v1 + 27);
    LODWORD(Sizel) = 4;
    v24 = RegistrySerialization::s_UpdateValue(v2, hKey, L"NumberOfHistoryBuffers", 4u, v90, Sizel);
    if ( v24 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x385,
        (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
        (const char *)(unsigned int)v24,
        Buf1o);
    LODWORD(Sizem) = 4;
    *(_DWORD *)v90 = (*((_DWORD *)v1 + 24) >> 4) & 1;
    v25 = RegistrySerialization::s_UpdateValue(v2, hKey, L"HistoryNoDup", 4u, v90, Sizem);
    if ( v25 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x38C,
        (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
        (const char *)(unsigned int)v25,
        Buf1p);
    *(_DWORD *)v90 = *((_DWORD *)v1 + 54);
    LODWORD(Sizen) = 4;
    v26 = RegistrySerialization::s_UpdateValue(v2, hKey, L"LineWrap", 4u, v90, Sizen);
    if ( v26 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x395,
        (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
        (const char *)(unsigned int)v26,
        Buf1q);
    *(_DWORD *)v90 = *((_DWORD *)v1 + 55);
    LODWORD(Sizeo) = 4;
    v27 = RegistrySerialization::s_UpdateValue(v2, hKey, L"FilterOnPaste", 4u, v90, Sizeo);
    if ( v27 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x39C,
        (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
        (const char *)(unsigned int)v27,
        Buf1r);
    *(_DWORD *)v90 = *((_DWORD *)v1 + 56);
    LODWORD(Sizep) = 4;
    v28 = RegistrySerialization::s_UpdateValue(v2, hKey, L"CtrlKeyShortcutsDisabled", 4u, v90, Sizep);
    if ( v28 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3A3,
        (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
        (const char *)(unsigned int)v28,
        Buf1s);
    *(_DWORD *)v90 = *((_DWORD *)v1 + 57);
    LODWORD(Sizeq) = 4;
    v29 = RegistrySerialization::s_UpdateValue(v2, hKey, L"LineSelection", 4u, v90, Sizeq);
    if ( v29 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3AA,
        (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
        (const char *)(unsigned int)v29,
        Buf1t);
    *(_DWORD *)v90 = *((unsigned __int8 *)v1 + 232);
    LODWORD(Sizer) = 4;
    v30 = RegistrySerialization::s_UpdateValue(v2, hKey, L"WindowAlpha", 4u, v90, Sizer);
    if ( v30 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3B1,
        (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
        (const char *)(unsigned int)v30,
        Buf1u);
    SetGlobalRegistryValues();
    if ( *((_DWORD *)gpStateInfo + 53) )
    {
      *(_DWORD *)v90 = *((_DWORD *)v1 + 60);
      LODWORD(Sizes) = 4;
      v31 = RegistrySerialization::s_UpdateValue(v2, hKey, L"CursorType", 4u, v90, Sizes);
      if ( v31 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x3C2,
          (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
          (const char *)(unsigned int)v31,
          Buf1v);
      *(_DWORD *)v90 = *((_DWORD *)v1 + 61);
      LODWORD(Sizet) = 4;
      v32 = RegistrySerialization::s_UpdateValue(v2, hKey, L"CursorColor", 4u, v90, Sizet);
      if ( v32 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x3CA,
          (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
          (const char *)(unsigned int)v32,
          Buf1w);
      *(_DWORD *)v90 = *((_DWORD *)v1 + 62);
      LODWORD(Sizeu) = 4;
      v33 = RegistrySerialization::s_UpdateValue(v2, hKey, L"InterceptCopyPaste", 4u, v90, Sizeu);
      if ( v33 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x3D2,
          (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
          (const char *)(unsigned int)v33,
          Buf1x);
      *(_DWORD *)v90 = *((_DWORD *)v1 + 65);
      LODWORD(Sizev) = 4;
      v34 = RegistrySerialization::s_UpdateValue(v2, hKey, L"TerminalScrolling", 4u, v90, Sizev);
      if ( v34 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x3DA,
          (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
          (const char *)(unsigned int)v34,
          Buf1y);
      *(_DWORD *)v90 = *((_DWORD *)v1 + 63);
      LODWORD(Sizew) = 4;
      v35 = RegistrySerialization::s_UpdateValue(v2, hKey, L"DefaultForeground", 4u, v90, Sizew);
      if ( v35 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x3E1,
          (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
          (const char *)(unsigned int)v35,
          Buf1z);
      *(_DWORD *)v90 = *((_DWORD *)v1 + 64);
      LODWORD(Sizex) = 4;
      v36 = RegistrySerialization::s_UpdateValue(v2, hKey, L"DefaultBackground", 4u, v90, Sizex);
      if ( v36 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x3E8,
          (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\registry.cpp",
          (const char *)(unsigned int)v36,
          Buf1ba);
    }
    if ( hKey != v2 )
      RegCloseKey(hKey);
    goto LABEL_79;
  }
}

```

## disassembly

```asm
0x180011f44  push    rbp
0x180011f46  push    rbx
0x180011f47  push    rsi
0x180011f48  push    rdi
0x180011f49  push    r12
0x180011f4b  push    r14
0x180011f4d  push    r15
0x180011f4f  lea     rbp, [rsp-27h]
0x180011f54  sub     rsp, 0B0h
0x180011f5b  mov     rax, cs:__security_cookie
0x180011f62  xor     rax, rsp
0x180011f65  mov     [rbp+57h+var_40], rax
0x180011f69  mov     eax, cs:?gnCurrentPage@@3IA; uint gnCurrentPage
0x180011f6f  lea     rdx, [rbp+57h+var_90]; HKEY *
0x180011f73  mov     rdi, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180011f7a  lea     rcx, [rbp+57h+var_98]; HKEY *
0x180011f7e  xor     r15d, r15d
0x180011f81  mov     dword ptr [rbp+57h+var_A0], eax
0x180011f84  mov     [rbp+57h+var_98], r15
0x180011f88  mov     [rbp+57h+var_90], r15
0x180011f8c  mov     [rbp+57h+hKey], r15
0x180011f90  mov     dword ptr [rbp+57h+var_B0], r15d
0x180011f94  call    ?s_OpenConsoleKey@RegistrySerialization@@SAJPEAPEAUHKEY__@@0@Z; RegistrySerialization::s_OpenConsoleKey(HKEY__ * *,HKEY__ * *)
0x180011f99  test    eax, eax
0x180011f9b  js      loc_18001286D
0x180011fa1  mov     rbx, [rbp+57h+var_90]
0x180011fa5  lea     r14d, [r15+4]
0x180011fa9  mov     r8d, r14d; unsigned int
0x180011fac  mov     dword ptr [rsp+0E0h+Buf1], r14d; int
0x180011fb1  mov     rcx, rbx; HKEY
0x180011fb4  lea     r9, [rbp+57h+var_A0]; unsigned __int8 *
0x180011fb8  lea     rdx, aCurrentpage; "CurrentPage"
0x180011fbf  call    ?s_SetValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WKQEAEK@Z; RegistrySerialization::s_SetValue(HKEY__ * const,wchar_t const * const,ulong,uchar * const,ulong)
0x180011fc4  lea     r12, aOnecoreWindows_1; "onecore\\windows\\core\\console\\open\\"...
0x180011fcb  test    eax, eax
0x180011fcd  jns     short loc_180011FE3
0x180011fcf  mov     rcx, [rbp+5Fh]; this
0x180011fd3  mov     r9d, eax; char *
0x180011fd6  mov     r8, r12; unsigned int
0x180011fd9  mov     edx, 2C4h; void *
0x180011fde  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180011fe3  test    byte ptr [rdi+60h], 80h
0x180011fe7  jz      short loc_180011FF2
0x180011fe9  mov     rdx, rbx
0x180011fec  mov     [rbp+57h+hKey], rbx
0x180011ff0  jmp     short loc_180012011
0x180011ff2  mov     rdx, [rdi+0C0h]; wchar_t *
0x180011ff9  lea     r8, [rbp+57h+hKey]; HKEY *
0x180011ffd  mov     rcx, rbx; HKEY
0x180012000  call    ?s_CreateKey@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WQEAPEAU2@@Z; RegistrySerialization::s_CreateKey(HKEY__ * const,wchar_t const * const,HKEY__ * * const)
0x180012005  test    eax, eax
0x180012007  js      loc_18001284E
0x18001200d  mov     rdx, [rbp+57h+hKey]; HKEY
0x180012011  movzx   eax, word ptr [rdi+64h]
0x180012015  lea     r8, aScreencolors; "ScreenColors"
0x18001201c  mov     dword ptr [rbp+57h+var_B0], eax
0x18001201f  mov     r9d, r14d; unsigned int
0x180012022  lea     rax, [rbp+57h+var_B0]
0x180012026  mov     dword ptr [rsp+0E0h+Size], r14d; Size
0x18001202b  mov     rcx, rbx; HKEY
0x18001202e  mov     [rsp+0E0h+Buf1], rax; int
0x180012033  call    ?s_UpdateValue@RegistrySerialization@@SAJQEAUHKEY__@@0QEB_WKPEAEK@Z; RegistrySerialization::s_UpdateValue(HKEY__ * const,HKEY__ * const,wchar_t const * const,ulong,uchar *,ulong)
0x180012038  test    eax, eax
0x18001203a  jns     short loc_180012050
0x18001203c  mov     rcx, [rbp+5Fh]; this
0x180012040  mov     r9d, eax; char *
0x180012043  mov     r8, r12; unsigned int
0x180012046  mov     edx, 2E4h; void *
0x18001204b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012050  movzx   eax, word ptr [rdi+66h]
0x180012054  lea     r8, aPopupcolors; "PopupColors"
0x18001205b  mov     rdx, [rbp+57h+hKey]; HKEY
0x18001205f  mov     r9d, r14d; unsigned int
0x180012062  mov     dword ptr [rbp+57h+var_B0], eax
0x180012065  mov     rcx, rbx; HKEY
0x180012068  lea     rax, [rbp+57h+var_B0]
0x18001206c  mov     dword ptr [rsp+0E0h+Size], r14d; Size
0x180012071  mov     [rsp+0E0h+Buf1], rax; int
0x180012076  call    ?s_UpdateValue@RegistrySerialization@@SAJQEAUHKEY__@@0QEB_WKPEAEK@Z; RegistrySerialization::s_UpdateValue(HKEY__ * const,HKEY__ * const,wchar_t const * const,ulong,uchar *,ulong)
0x18001207b  test    eax, eax
0x18001207d  jns     short loc_180012093
0x18001207f  mov     rcx, [rbp+5Fh]; this
0x180012083  mov     r9d, eax; char *
0x180012086  mov     r8, r12; unsigned int
0x180012089  mov     edx, 2EBh; void *
0x18001208e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012093  mov     esi, r15d
0x180012096  mov     eax, esi
0x180012098  lea     r8, aColortable02u; "ColorTable%02u"
0x18001209f  mov     r9d, esi
0x1800120a2  mov     edx, 20h ; ' '; unsigned __int64
0x1800120a7  mov     ecx, [rdi+rax*4+70h]
0x1800120ab  mov     dword ptr [rbp+57h+var_B0], ecx
0x1800120ae  lea     rcx, [rbp+57h+var_80]; wchar_t *
0x1800120b2  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800120b7  test    eax, eax
0x1800120b9  js      short loc_1800120F4
0x1800120bb  mov     rdx, [rbp+57h+hKey]; HKEY
0x1800120bf  lea     rax, [rbp+57h+var_B0]
0x1800120c3  mov     dword ptr [rsp+0E0h+Size], r14d; Size
0x1800120c8  lea     r8, [rbp+57h+var_80]; wchar_t *
0x1800120cc  mov     r9d, r14d; unsigned int
0x1800120cf  mov     [rsp+0E0h+Buf1], rax; int
0x1800120d4  mov     rcx, rbx; HKEY
0x1800120d7  call    ?s_UpdateValue@RegistrySerialization@@SAJQEAUHKEY__@@0QEB_WKPEAEK@Z; RegistrySerialization::s_UpdateValue(HKEY__ * const,HKEY__ * const,wchar_t const * const,ulong,uchar *,ulong)
0x1800120dc  test    eax, eax
0x1800120de  jns     short loc_1800120F4
0x1800120e0  mov     rcx, [rbp+5Fh]; this
0x1800120e4  mov     r9d, eax; char *
0x1800120e7  mov     r8, r12; unsigned int
0x1800120ea  mov     edx, 2F6h; void *
0x1800120ef  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800120f4  inc     esi
0x1800120f6  cmp     esi, 10h
0x1800120f9  jb      short loc_180012096
0x1800120fb  mov     eax, [rdi+60h]
0x1800120fe  lea     r8, aInsertmode; "InsertMode"
0x180012105  mov     rdx, [rbp+57h+hKey]; HKEY
0x180012109  mov     r9d, r14d; unsigned int
0x18001210c  shr     eax, 3
0x18001210f  mov     rcx, rbx; HKEY
0x180012112  and     eax, 1
0x180012115  mov     dword ptr [rsp+0E0h+Size], r14d; Size
0x18001211a  mov     dword ptr [rbp+57h+var_B0], eax
0x18001211d  lea     rax, [rbp+57h+var_B0]
0x180012121  mov     [rsp+0E0h+Buf1], rax; int
0x180012126  call    ?s_UpdateValue@RegistrySerialization@@SAJQEAUHKEY__@@0QEB_WKPEAEK@Z; RegistrySerialization::s_UpdateValue(HKEY__ * const,HKEY__ * const,wchar_t const * const,ulong,uchar *,ulong)
0x18001212b  test    eax, eax
0x18001212d  jns     short loc_180012143
0x18001212f  mov     rcx, [rbp+5Fh]; this
0x180012133  mov     r9d, eax; char *
0x180012136  mov     r8, r12; unsigned int
0x180012139  mov     edx, 304h; void *
0x18001213e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012143  mov     eax, [rdi+60h]
0x180012146  lea     r8, aQuickedit; "QuickEdit"
0x18001214d  mov     rdx, [rbp+57h+hKey]; HKEY
0x180012151  mov     r9d, r14d; unsigned int
0x180012154  shr     eax, 1
0x180012156  mov     rcx, rbx; HKEY
0x180012159  and     eax, 1
0x18001215c  mov     dword ptr [rsp+0E0h+Size], r14d; Size
0x180012161  mov     dword ptr [rbp+57h+var_B0], eax
0x180012164  lea     rax, [rbp+57h+var_B0]
0x180012168  mov     [rsp+0E0h+Buf1], rax; int
0x18001216d  call    ?s_UpdateValue@RegistrySerialization@@SAJQEAUHKEY__@@0QEB_WKPEAEK@Z; RegistrySerialization::s_UpdateValue(HKEY__ * const,HKEY__ * const,wchar_t const * const,ulong,uchar *,ulong)
0x180012172  test    eax, eax
0x180012174  jns     short loc_18001218A
0x180012176  mov     rcx, [rbp+5Fh]; this
0x18001217a  mov     r9d, eax; char *
0x18001217d  mov     r8, r12; unsigned int
0x180012180  mov     edx, 30Bh; void *
0x180012185  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001218a  cmp     cs:?OEMCP@@3IA, r15d; uint OEMCP
0x180012191  jnz     short loc_1800121A5
0x180012193  mov     rcx, [rbp+5Fh]; this
0x180012197  mov     r8, r12; unsigned int
0x18001219a  mov     edx, 30Dh; void *
0x18001219f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800121a5  cmp     cs:?g_fEastAsianSystem@@3HA, r15d; int g_fEastAsianSystem
0x1800121ac  jz      short loc_1800121F3
0x1800121ae  mov     eax, [rdi+0D0h]
0x1800121b4  lea     r8, aCodepage; "CodePage"
0x1800121bb  mov     rdx, [rbp+57h+hKey]; HKEY
0x1800121bf  mov     r9d, r14d; unsigned int
0x1800121c2  mov     dword ptr [rbp+57h+var_B0], eax
0x1800121c5  mov     rcx, rbx; HKEY
0x1800121c8  lea     rax, [rbp+57h+var_B0]
0x1800121cc  mov     dword ptr [rsp+0E0h+Size], r14d; Size
0x1800121d1  mov     [rsp+0E0h+Buf1], rax; int
0x1800121d6  call    ?s_UpdateValue@RegistrySerialization@@SAJQEAUHKEY__@@0QEB_WKPEAEK@Z; RegistrySerialization::s_UpdateValue(HKEY__ * const,HKEY__ * const,wchar_t const * const,ulong,uchar *,ulong)
0x1800121db  test    eax, eax
0x1800121dd  jns     short loc_1800121F3
0x1800121df  mov     rcx, [rbp+5Fh]; this
0x1800121e3  mov     r9d, eax; char *
0x1800121e6  mov     r8, r12; unsigned int
0x1800121e9  mov     edx, 316h; void *
0x1800121ee  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800121f3  movzx   ecx, word ptr [rdi+2]
0x1800121f7  lea     r8, aScreenbuffersi; "ScreenBufferSize"
0x1800121fe  movzx   eax, word ptr [rdi]
0x180012201  mov     r9d, r14d; unsigned int
0x180012204  mov     rdx, [rbp+57h+hKey]; HKEY
0x180012208  shl     ecx, 10h
0x18001220b  or      ecx, eax
0x18001220d  mov     dword ptr [rsp+0E0h+Size], r14d; Size
0x180012212  mov     dword ptr [rbp+57h+var_B0], ecx
0x180012215  lea     rax, [rbp+57h+var_B0]
0x180012219  mov     rcx, rbx; HKEY
0x18001221c  mov     [rsp+0E0h+Buf1], rax; int
0x180012221  call    ?s_UpdateValue@RegistrySerialization@@SAJQEAUHKEY__@@0QEB_WKPEAEK@Z; RegistrySerialization::s_UpdateValue(HKEY__ * const,HKEY__ * const,wchar_t const * const,ulong,uchar *,ulong)
0x180012226  test    eax, eax
0x180012228  jns     short loc_18001223E
0x18001222a  mov     rcx, [rbp+5Fh]; this
0x18001222e  mov     r9d, eax; char *
0x180012231  mov     r8, r12; unsigned int
0x180012234  mov     edx, 324h; void *
0x180012239  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001223e  movzx   ecx, word ptr [rdi+6]
0x180012242  lea     r8, aWindowsize; "WindowSize"
0x180012249  movzx   eax, word ptr [rdi+4]
0x18001224d  mov     r9d, r14d; unsigned int
0x180012250  mov     rdx, [rbp+57h+hKey]; HKEY
0x180012254  shl     ecx, 10h
0x180012257  or      ecx, eax
0x180012259  mov     dword ptr [rsp+0E0h+Size], r14d; Size
0x18001225e  mov     dword ptr [rbp+57h+var_B0], ecx
0x180012261  lea     rax, [rbp+57h+var_B0]
0x180012265  mov     rcx, rbx; HKEY
0x180012268  mov     [rsp+0E0h+Buf1], rax; int
0x18001226d  call    ?s_UpdateValue@RegistrySerialization@@SAJQEAUHKEY__@@0QEB_WKPEAEK@Z; RegistrySerialization::s_UpdateValue(HKEY__ * const,HKEY__ * const,wchar_t const * const,ulong,uchar *,ulong)
0x180012272  test    eax, eax
0x180012274  jns     short loc_18001228A
0x180012276  mov     rcx, [rbp+5Fh]; this
0x18001227a  mov     r9d, eax; char *
0x18001227d  mov     r8, r12; unsigned int
0x180012280  mov     edx, 331h; void *
0x180012285  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001228a  test    [rdi+60h], r14b
0x18001228e  jz      short loc_1800122AB
0x180012290  mov     rcx, [rbp+57h+hKey]; HKEY
0x180012294  lea     rdx, aWindowposition; "WindowPosition"
0x18001229b  call    ?s_DeleteValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_W@Z; RegistrySerialization::s_DeleteValue(HKEY__ * const,wchar_t const * const)
0x1800122a0  test    eax, eax
0x1800122a2  jns     short loc_1800122F7
0x1800122a4  mov     edx, 339h
0x1800122a9  jmp     short loc_1800122E8
0x1800122ab  movzx   ecx, word ptr [rdi+0Ch]
0x1800122af  lea     r8, aWindowposition; "WindowPosition"
0x1800122b6  movzx   eax, word ptr [rdi+8]
0x1800122ba  mov     r9d, r14d; unsigned int
0x1800122bd  mov     rdx, [rbp+57h+hKey]; HKEY
0x1800122c1  shl     ecx, 10h
0x1800122c4  or      ecx, eax
0x1800122c6  mov     dword ptr [rsp+0E0h+Size], r14d; Size
0x1800122cb  mov     dword ptr [rbp+57h+var_B0], ecx
0x1800122ce  lea     rax, [rbp+57h+var_B0]
0x1800122d2  mov     rcx, rbx; HKEY
0x1800122d5  mov     [rsp+0E0h+Buf1], rax; int
0x1800122da  call    ?s_UpdateValue@RegistrySerialization@@SAJQEAUHKEY__@@0QEB_WKPEAEK@Z; RegistrySerialization::s_UpdateValue(HKEY__ * const,HKEY__ * const,wchar_t const * const,ulong,uchar *,ulong)
0x1800122df  test    eax, eax
0x1800122e1  jns     short loc_1800122F7
0x1800122e3  mov     edx, 344h; void *
0x1800122e8  mov     rcx, [rbp+5Fh]; this
0x1800122ec  mov     r9d, eax; char *
0x1800122ef  mov     r8, r12; unsigned int
0x1800122f2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800122f7  movzx   ecx, word ptr [rdi+12h]
0x1800122fb  lea     r8, aFontsize; "FontSize"
0x180012302  movzx   eax, word ptr [rdi+10h]
0x180012306  mov     r9d, r14d; unsigned int
0x180012309  mov     rdx, [rbp+57h+hKey]; HKEY
0x18001230d  shl     ecx, 10h
0x180012310  or      ecx, eax
0x180012312  mov     dword ptr [rsp+0E0h+Size], r14d; Size
0x180012317  mov     dword ptr [rbp+57h+var_B0], ecx
0x18001231a  lea     rax, [rbp+57h+var_B0]
0x18001231e  mov     rcx, rbx; HKEY
0x180012321  mov     [rsp+0E0h+Buf1], rax; int
0x180012326  call    ?s_UpdateValue@RegistrySerialization@@SAJQEAUHKEY__@@0QEB_WKPEAEK@Z; RegistrySerialization::s_UpdateValue(HKEY__ * const,HKEY__ * const,wchar_t const * const,ulong,uchar *,ulong)
0x18001232b  test    eax, eax
0x18001232d  jns     short loc_180012343
0x18001232f  mov     rcx, [rbp+5Fh]; this
0x180012333  mov     r9d, eax; char *
0x180012336  mov     r8, r12; unsigned int
0x180012339  mov     edx, 352h; void *
0x18001233e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012343  mov     eax, [rdi+14h]
0x180012346  lea     r8, aFontfamily; "FontFamily"
0x18001234d  mov     rdx, [rbp+57h+hKey]; HKEY
0x180012351  mov     r9d, r14d; unsigned int
0x180012354  mov     dword ptr [rbp+57h+var_B0], eax
0x180012357  mov     rcx, rbx; HKEY
0x18001235a  lea     rax, [rbp+57h+var_B0]
0x18001235e  mov     dword ptr [rsp+0E0h+Size], r14d; Size
0x180012363  mov     [rsp+0E0h+Buf1], rax; int
0x180012368  call    ?s_UpdateValue@RegistrySerialization@@SAJQEAUHKEY__@@0QEB_WKPEAEK@Z; RegistrySerialization::s_UpdateValue(HKEY__ * const,HKEY__ * const,wchar_t const * const,ulong,uchar *,ulong)
0x18001236d  test    eax, eax
0x18001236f  jns     short loc_180012385
0x180012371  mov     rcx, [rbp+5Fh]; this
0x180012375  mov     r9d, eax; char *
0x180012378  mov     r8, r12; unsigned int
0x18001237b  mov     edx, 359h; void *
0x180012380  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012385  mov     eax, [rdi+18h]
0x180012388  lea     r8, aFontweight; "FontWeight"
0x18001238f  mov     rdx, [rbp+57h+hKey]; HKEY
0x180012393  mov     r9d, r14d; unsigned int
0x180012396  mov     dword ptr [rbp+57h+var_B0], eax
0x180012399  mov     rcx, rbx; HKEY
0x18001239c  lea     rax, [rbp+57h+var_B0]
0x1800123a0  mov     dword ptr [rsp+0E0h+Size], r14d; Size
0x1800123a5  mov     [rsp+0E0h+Buf1], rax; int
0x1800123aa  call    ?s_UpdateValue@RegistrySerialization@@SAJQEAUHKEY__@@0QEB_WKPEAEK@Z; RegistrySerialization::s_UpdateValue(HKEY__ * const,HKEY__ * const,wchar_t const * const,ulong,uchar *,ulong)
0x1800123af  test    eax, eax
0x1800123b1  jns     short loc_1800123C7
0x1800123b3  mov     rcx, [rbp+5Fh]; this
0x1800123b7  mov     r9d, eax; char *
0x1800123ba  mov     r8, r12; unsigned int
0x1800123bd  mov     edx, 360h; void *
  ... truncated ...
```
