# LowerSharedDLLRefCount(HKEY__ *,ushort *,ulong,DELETEDATA_TYPE)

- ea: `0x1801983c0`
- end: `0x180198d19`
- name: `?LowerSharedDLLRefCount@@YAIPEAUHKEY__@@PEAGKW4DELETEDATA_TYPE@@@Z`
- size: `2393`
- prototype: `unsigned int __high(HKEY, unsigned __int16 *, unsigned int, enum DELETEDATA_TYPE)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000c4bc`
- `0x180014160`
- `0x1800141e0`
- `0x180040908`
- `0x18006c9fc`
- `0x1800e2a64`
- `0x1801983c0`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1801986e8`
- `msvcrt!_wcsnicmp` at `0x1801986e8`
- `ADVAPI32!RegQueryValueExW` at `0x1801989a2`
- `ADVAPI32!RegQueryValueExW` at `0x1801989a2`
- `ADVAPI32!RegCloseKey` at `0x180198c3d`
- `ADVAPI32!RegCloseKey` at `0x180198c5b`
- `ADVAPI32!RegCloseKey` at `0x180198c77`
- `ADVAPI32!RegCloseKey` at `0x180198c3d`
- `ADVAPI32!RegCloseKey` at `0x180198c5b`
- `ADVAPI32!RegCloseKey` at `0x180198c77`
- `ADVAPI32!RegSetValueExW` at `0x180198a8a`
- `ADVAPI32!RegSetValueExW` at `0x180198a8a`
- `KERNEL32!lstrlenW` at `0x1801986ca`
- `KERNEL32!lstrlenW` at `0x180198897`
- `KERNEL32!lstrlenW` at `0x1801986ca`
- `KERNEL32!lstrlenW` at `0x180198897`
- `KERNEL32!GlobalFree` at `0x180198c93`
- `KERNEL32!GlobalFree` at `0x180198cbe`
- `KERNEL32!GlobalFree` at `0x180198ce0`
- `KERNEL32!GlobalFree` at `0x180198c93`
- `KERNEL32!GlobalFree` at `0x180198cbe`
- `KERNEL32!GlobalFree` at `0x180198ce0`

## string_xrefs

- `0x1801984d3`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SharedDLLs`
- `0x18019855c`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SharedDLLs`
- `0x18019848b`: `LowerSharedDLLRefCount: RegOpenKeyEx returned %08x.`
- `0x180198513`: `LowerSharedDLLRefCount: MsiRegOpen64bitKey returned %08x.`
- `0x180198586`: `LowerSharedDLLRefCount: RegOpenKeyAPI returned %08x.`
- `0x18019873c`: `LowerSharedDLLRefCount: RegOpenKeyAPI returned %08x.`
- `0x18019863d`: `\nLowerSharedDLLRefCount: Found shared DLL %s in component %s`
- `0x18019879e`: `Not special path`
- `0x1801988fe`: `Special 64 bit path`
- `0x180198825`: `Special 32 bit path`
- `0x180198a28`: `LowerSharedDllRefCount: RegQueryValueEx: Can not decrement the ref count for shared dll %s with error %08x.`
- `0x180198b14`: `LowerSharedDllRefCount: RegSetValueEx: Can not decrement the ref count for shared dll %s with error %s.`
- `0x180198b2d`: `LowerSharedDllRefCount: ref count for %s decremented.`
- `0x180198bfb`: `LowerSharedDLLRefCount <%s>: MsiRegEnumValue returned %d.`

## pseudocode

```c
__int64 __fastcall LowerSharedDLLRefCount(HKEY a1, const unsigned __int16 *a2, unsigned int a3)
{
  const unsigned __int16 *v3; // r15
  unsigned int v4; // eax
  unsigned int v5; // r8d
  unsigned int v6; // esi
  unsigned int v7; // eax
  unsigned int v8; // r14d
  unsigned int v9; // eax
  unsigned int v10; // ebx
  DWORD v11; // r14d
  unsigned int v12; // ebx
  void *v13; // rdx
  __int64 *v14; // r11
  int v15; // ecx
  int v16; // r13d
  int v17; // r14d
  int i; // r15d
  __int64 v19; // rbx
  int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // ebx
  int v23; // ebx
  int v24; // ebx
  __int64 v25; // r10
  __int64 v26; // r11
  int v27; // eax
  const WCHAR *v28; // rdx
  unsigned int v29; // eax
  unsigned int v30; // ebx
  const unsigned __int16 *v31; // rax
  const unsigned __int16 *v32; // r9
  const WCHAR *v33; // rdx
  unsigned int v34; // eax
  HKEY v35; // rcx
  HKEY *lpData; // [rsp+20h] [rbp-E0h]
  int lpDataa; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *lpcbData; // [rsp+28h] [rbp-D8h]
  int v40; // [rsp+60h] [rbp-A0h]
  int v41; // [rsp+64h] [rbp-9Ch]
  BYTE Data[4]; // [rsp+68h] [rbp-98h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp-94h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbData; // [rsp+78h] [rbp-88h] BYREF
  DWORD v46; // [rsp+7Ch] [rbp-84h]
  HKEY v47; // [rsp+80h] [rbp-80h] BYREF
  HKEY v48; // [rsp+88h] [rbp-78h] BYREF
  HKEY v49; // [rsp+90h] [rbp-70h] BYREF
  const unsigned __int16 *v50; // [rsp+98h] [rbp-68h]
  HGLOBAL v51; // [rsp+A0h] [rbp-60h]
  int v52; // [rsp+A8h] [rbp-58h]
  int v53; // [rsp+ACh] [rbp-54h]
  char v54; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t *String2; // [rsp+100h] [rbp+0h] BYREF
  int v56; // [rsp+108h] [rbp+8h]
  int v57; // [rsp+10Ch] [rbp+Ch]
  _BYTE v58[528]; // [rsp+110h] [rbp+10h] BYREF
  HGLOBAL hMem; // [rsp+320h] [rbp+220h]
  int v60; // [rsp+328h] [rbp+228h]
  _BYTE v61[528]; // [rsp+330h] [rbp+230h] BYREF

  v50 = a2;
  v49 = 0;
  v51 = &v54;
  hKey = 0;
  String2 = (wchar_t *)v58;
  v47 = 0;
  hMem = v61;
  v3 = a2;
  v48 = 0;
  v52 = 33;
  Type = 0;
  v56 = 260;
  v60 = 260;
  *(_DWORD *)Data = 0;
  cbData = 4;
  v4 = MsiRegOpen64bitKey(a1, a2, a3, 0x20019u, &v49);
  v6 = v4;
  if ( v4 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        10,
        0,
        0,
        L"LowerSharedDLLRefCount: RegOpenKeyEx returned %08x.",
        (const unsigned __int16 *)v4,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    goto LABEL_93;
  }
  v6 = 0;
  if ( g_fWinNT64 )
  {
    v7 = MsiRegOpen64bitKey(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SharedDLLs",
           v5,
           0xF003Fu,
           &v47);
    v8 = v7;
    if ( v7 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          5,
          0,
          0,
          L"LowerSharedDLLRefCount: MsiRegOpen64bitKey returned %08x.",
          (const unsigned __int16 *)v7,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      v6 = v8;
    }
    lpData = &v48;
    v9 = ((__int64 (__fastcall *)(__int64, const unsigned __int16 *, _QWORD, __int64))RegOpenKeyAPI)(
           -2147483646,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SharedDLLs",
           0,
           983615);
    v10 = v9;
    if ( v9 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          5,
          0,
          0,
          L"LowerSharedDLLRefCount: RegOpenKeyAPI returned %08x.",
          (const unsigned __int16 *)v9,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      if ( !v6 )
        v6 = v10;
    }
    if ( !v47 && !v48 )
      goto LABEL_93;
  }
  else
  {
    lpData = &hKey;
    v21 = ((__int64 (__fastcall *)(__int64, const unsigned __int16 *, _QWORD, __int64))RegOpenKeyAPI)(
            -2147483646,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SharedDLLs",
            0,
            983103);
    v22 = v21;
    if ( v21 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          5,
          0,
          0,
          L"LowerSharedDLLRefCount: RegOpenKeyAPI returned %08x.",
          (const unsigned __int16 *)v21,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      v6 = v22;
      goto LABEL_93;
    }
  }
  v57 = 260;
  v11 = 0;
  v46 = 0;
  v53 = 33;
  v12 = MsiRegEnumValueW(v49, 0, (int)lpData, &Type, (DWORD)&String2);
  if ( !v12 )
  {
    while ( 1 )
    {
      if ( !(unsigned int)RemoveSharedDllCountToken<unsigned short>(String2, 0) )
        goto LABEL_86;
      if ( g_dmDiagnosticMode != (_DWORD)v13 )
      {
        DebugString(
          (_DWORD)v13 + 9,
          (unsigned __int16)v13,
          0,
          L"\nLowerSharedDLLRefCount: Found shared DLL %s in component %s",
          String2,
          (const unsigned __int16 *)v51,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          (unsigned int)v13,
          v13);
        v14 = SpecialFolders;
      }
      v15 = 1;
      v41 = 0;
      v40 = 1;
      v16 = 0;
LABEL_21:
      while ( v15 )
      {
        if ( g_fWinNT64 )
        {
          v17 = 0;
LABEL_24:
          for ( i = 0; ; ++i )
          {
            if ( i >= 2 )
            {
              if ( (unsigned int)++v17 < 3 )
                goto LABEL_24;
              if ( g_dmDiagnosticMode )
                DebugString(
                  9,
                  0,
                  0,
                  L"Not special path",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  0,
                  0);
              v23 = v41;
              if ( !v41 )
              {
                hKey = v48;
                if ( v48 )
                  goto LABEL_57;
                v15 = v40;
                v14 = SpecialFolders;
                v41 = 1;
                goto LABEL_21;
              }
              hKey = v47;
              if ( v47 )
                goto LABEL_57;
              v15 = v40;
              goto LABEL_84;
            }
            v19 = 67 * (i + 2LL * v17);
            v20 = lstrlenW((LPCWSTR)v14[v19]);
            if ( !_wcsnicmp((const wchar_t *)SpecialFolders[v19], String2, v20) )
              break;
            v14 = SpecialFolders;
          }
          if ( i != 1 )
          {
            v24 = 0;
            if ( g_dmDiagnosticMode )
              DebugString(
                9,
                0,
                0,
                L"Special 32 bit path",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
            if ( !v17 )
            {
              if ( (int)StringCchCopyW((unsigned __int16 *)hMem, v60, (const unsigned __int16 *)SpecialFolders[67]) < 0
                || (v27 = lstrlenW(*(LPCWSTR *)(v25 + v26)),
                    (int)StringCchCatW((unsigned __int16 *)hMem, v60, &String2[v27]) < 0) )
              {
                v24 = 1;
              }
              v16 = 1;
            }
            hKey = v48;
            if ( !v48 )
              v24 = 1;
            v15 = 0;
            v40 = 0;
            if ( v24 )
              goto LABEL_83;
            goto LABEL_57;
          }
          v15 = 0;
          v40 = 0;
          if ( g_dmDiagnosticMode )
          {
            DebugString(
              9,
              0,
              0,
              L"Special 64 bit path",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
            v15 = 0;
          }
          hKey = v47;
          if ( v47 )
            goto LABEL_57;
          goto LABEL_83;
        }
        v40 = 0;
LABEL_57:
        v28 = (const WCHAR *)hMem;
        cbData = 4;
        if ( !v16 )
          v28 = String2;
        v29 = RegQueryValueExW(hKey, v28, 0, &Type, Data, &cbData);
        v30 = v29;
        if ( v29 )
        {
          if ( v16 )
          {
            if ( g_dmDiagnosticMode )
            {
              lpcbData = (const unsigned __int16 *)v29;
              v31 = (const unsigned __int16 *)hMem;
              goto LABEL_65;
            }
LABEL_67:
            if ( v6 )
              v30 = v6;
            v6 = v30;
            goto LABEL_82;
          }
          if ( !g_dmDiagnosticMode )
            goto LABEL_67;
          lpcbData = (const unsigned __int16 *)v29;
          v31 = String2;
LABEL_65:
          v32 = L"LowerSharedDllRefCount: RegQueryValueEx: Can not decrement the ref count for shared dll %s with error %08x.";
LABEL_66:
          DebugString(5, 0, 0, v32, v31, lpcbData, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
          goto LABEL_67;
        }
        if ( *(_DWORD *)Data )
        {
          v33 = (const WCHAR *)hMem;
          --*(_DWORD *)Data;
          if ( !v16 )
            v33 = String2;
          v34 = RegSetValueExW(hKey, v33, 0, Type, Data, 4u);
          v30 = v34;
          if ( !v34 )
          {
            if ( g_dmDiagnosticMode )
              DebugString(
                5,
                0,
                0,
                L"LowerSharedDllRefCount: ref count for %s decremented.",
                String2,
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
            goto LABEL_82;
          }
          if ( v16 )
          {
            if ( !g_dmDiagnosticMode )
              goto LABEL_67;
            lpcbData = (const unsigned __int16 *)v34;
            v31 = (const unsigned __int16 *)hMem;
          }
          else
          {
            if ( !g_dmDiagnosticMode )
              goto LABEL_67;
            lpcbData = (const unsigned __int16 *)v34;
            v31 = String2;
          }
          v32 = L"LowerSharedDllRefCount: RegSetValueEx: Can not decrement the ref count for shared dll %s with error %s.";
          goto LABEL_66;
        }
LABEL_82:
        v15 = v40;
LABEL_83:
        v23 = v41;
LABEL_84:
        v14 = SpecialFolders;
        v41 = v23 + 1;
        if ( v23 + 1 >= 2 )
          break;
      }
      v11 = v46;
LABEL_86:
      ++v11;
      v57 = 260;
      v46 = v11;
      v53 = 33;
      v12 = MsiRegEnumValueW(v49, v11, lpDataa, &Type, (DWORD)&String2);
      if ( v12 )
      {
        v3 = v50;
        break;
      }
    }
  }
  if ( v12 != 259 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        5,
        0,
        0,
        L"LowerSharedDLLRefCount <%s>: MsiRegEnumValue returned %d.",
        v3,
        (const unsigned __int16 *)v12,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    if ( !v6 )
      v6 = v12;
  }
LABEL_93:
  if ( v49 )
    RegCloseKey(v49);
  if ( g_fWinNT64 )
  {
    if ( v47 )
      RegCloseKey(v47);
    v35 = v48;
  }
  else
  {
    v35 = hKey;
  }
  if ( v35 )
    RegCloseKey(v35);
  if ( v60 > 260 )
    GlobalFree(hMem);
  v60 = 260;
  hMem = v61;
  if ( v56 > 260 )
    GlobalFree(String2);
  String2 = (wchar_t *)v58;
  v56 = 260;
  if ( v52 > 33 )
    GlobalFree(v51);
  return v6;
}

```

## disassembly

```asm
0x1801983c0  mov     [rsp-8+arg_10], rbx
0x1801983c5  push    rbp
0x1801983c6  push    rsi
0x1801983c7  push    rdi
0x1801983c8  push    r12
0x1801983ca  push    r13
0x1801983cc  push    r14
0x1801983ce  push    r15
0x1801983d0  lea     rbp, [rsp-450h]
0x1801983d8  sub     rsp, 550h
0x1801983df  mov     rax, cs:__security_cookie
0x1801983e6  xor     rax, rsp
0x1801983e9  mov     [rbp+480h+var_40], rax
0x1801983f0  xor     r12d, r12d
0x1801983f3  mov     [rbp+480h+var_4E8], rdx
0x1801983f7  lea     rax, [rbp+480h+var_4D0]
0x1801983fb  mov     [rbp+480h+var_4F0], r12
0x1801983ff  mov     [rbp+480h+var_4E0], rax
0x180198403  mov     r13d, 104h
0x180198409  lea     rax, [rbp+480h+var_470]
0x18019840d  mov     [rsp+580h+hKey], r12
0x180198412  mov     [rbp+480h+String2], rax
0x180198416  mov     r9d, 20019h; unsigned int
0x18019841c  lea     rax, [rbp+480h+var_250]
0x180198423  mov     [rbp+480h+var_500], r12
0x180198427  mov     [rbp+480h+hMem], rax
0x18019842e  mov     r15, rdx
0x180198431  lea     rax, [rbp+480h+var_4F0]
0x180198435  mov     [rbp+480h+var_4F8], r12
0x180198439  mov     [rsp+580h+lpData], rax; HKEY *
0x18019843e  mov     [rbp+480h+var_4D8], 21h ; '!'
0x180198445  mov     [rsp+580h+Type], r12d
0x18019844a  mov     [rbp+480h+var_478], r13d
0x18019844e  mov     [rbp+480h+var_258], r13d
0x180198455  mov     dword ptr [rsp+580h+Data], r12d
0x18019845a  mov     [rsp+580h+cbData], 4
0x180198462  call    ?MsiRegOpen64bitKey@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; MsiRegOpen64bitKey(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180198467  mov     esi, eax
0x180198469  test    eax, eax
0x18019846b  jz      short loc_1801984C2
0x18019846d  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180198474  jz      loc_180198C34
0x18019847a  mov     [rsp+580h+var_528], r12; void *
0x18019847f  lea     rdi, aNull; "(NULL)"
0x180198486  mov     [rsp+580h+var_530], r12d; unsigned int
0x18019848b  lea     r9, aLowershareddll; "LowerSharedDLLRefCount: RegOpenKeyEx re"...
0x180198492  mov     [rsp+580h+var_538], rdi; unsigned __int16 *
0x180198497  xor     edx, edx; unsigned __int16
0x180198499  mov     [rsp+580h+var_540], rdi; unsigned __int16 *
0x18019849e  xor     r8d, r8d; int
0x1801984a1  mov     [rsp+580h+var_548], rdi; unsigned __int16 *
0x1801984a6  mov     qword ptr [rsp+580h+cbMaxValueLen], rdi; unsigned __int16 *
0x1801984ab  mov     [rsp+580h+lpcbData], rdi; unsigned __int16 *
0x1801984b0  lea     ecx, [rdx+0Ah]; int
0x1801984b3  mov     [rsp+580h+lpData], rsi; unsigned __int16 *
0x1801984b8  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801984bd  jmp     loc_180198C34
0x1801984c2  cmp     cs:?g_fWinNT64@@3_NA, r12b; bool g_fWinNT64
0x1801984c9  lea     rdi, aNull; "(NULL)"
0x1801984d0  mov     esi, r12d
0x1801984d3  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1801984da  mov     r9d, 0F003Fh; unsigned int
0x1801984e0  jz      loc_180198708
0x1801984e6  lea     rax, [rbp+480h+var_500]
0x1801984ea  mov     rbx, 0FFFFFFFF80000002h
0x1801984f1  mov     rcx, rbx; HKEY
0x1801984f4  mov     [rsp+580h+lpData], rax; HKEY *
0x1801984f9  call    ?MsiRegOpen64bitKey@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; MsiRegOpen64bitKey(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x1801984fe  mov     r14d, eax
0x180198501  test    eax, eax
0x180198503  jz      short loc_18019854D
0x180198505  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x18019850c  jz      short loc_18019854A
0x18019850e  mov     [rsp+580h+var_528], r12; void *
0x180198513  lea     r9, aLowershareddll_2; "LowerSharedDLLRefCount: MsiRegOpen64bit"...
0x18019851a  mov     [rsp+580h+var_530], r12d; unsigned int
0x18019851f  xor     edx, edx; unsigned __int16
0x180198521  mov     [rsp+580h+var_538], rdi; unsigned __int16 *
0x180198526  xor     r8d, r8d; int
0x180198529  mov     [rsp+580h+var_540], rdi; unsigned __int16 *
0x18019852e  mov     [rsp+580h+var_548], rdi; unsigned __int16 *
0x180198533  mov     qword ptr [rsp+580h+cbMaxValueLen], rdi; unsigned __int16 *
0x180198538  lea     ecx, [rdx+5]; int
0x18019853b  mov     [rsp+580h+lpcbData], rdi; unsigned __int16 *
0x180198540  mov     [rsp+580h+lpData], r14; unsigned __int16 *
0x180198545  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18019854a  mov     esi, r14d
0x18019854d  lea     rax, [rbp+480h+var_4F8]
0x180198551  mov     r9d, 0F023Fh
0x180198557  mov     [rsp+580h+lpData], rax
0x18019855c  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180198563  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x18019856a  xor     r8d, r8d
0x18019856d  mov     rcx, rbx
0x180198570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198575  mov     ebx, eax
0x180198577  test    eax, eax
0x180198579  jz      short loc_1801985C4
0x18019857b  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180198582  jz      short loc_1801985BF
0x180198584  xor     edx, edx; unsigned __int16
0x180198586  lea     r9, aLowershareddll_4; "LowerSharedDLLRefCount: RegOpenKeyAPI r"...
0x18019858d  mov     [rsp+580h+var_528], rdx; void *
0x180198592  xor     r8d, r8d; int
0x180198595  mov     [rsp+580h+var_530], edx; unsigned int
0x180198599  mov     [rsp+580h+var_538], rdi; unsigned __int16 *
0x18019859e  mov     [rsp+580h+var_540], rdi; unsigned __int16 *
0x1801985a3  lea     ecx, [rdx+5]; int
0x1801985a6  mov     [rsp+580h+var_548], rdi; unsigned __int16 *
0x1801985ab  mov     qword ptr [rsp+580h+cbMaxValueLen], rdi; unsigned __int16 *
0x1801985b0  mov     [rsp+580h+lpcbData], rdi; unsigned __int16 *
0x1801985b5  mov     [rsp+580h+lpData], rbx; int
0x1801985ba  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801985bf  test    esi, esi
0x1801985c1  cmovz   esi, ebx
0x1801985c4  cmp     [rbp+480h+var_500], r12
0x1801985c8  jnz     short loc_1801985D4
0x1801985ca  cmp     [rbp+480h+var_4F8], r12
0x1801985ce  jz      loc_180198C34
0x1801985d4  mov     rcx, [rbp+480h+var_4F0]; hKey
0x1801985d8  lea     rax, [rbp+480h+String2]
0x1801985dc  mov     qword ptr [rsp+580h+cbMaxValueLen], rax; cbMaxValueLen
0x1801985e1  lea     r8, [rbp+480h+var_4E0]
0x1801985e5  lea     rax, [rsp+580h+Type]
0x1801985ea  mov     [rbp+480h+var_474], r13d
0x1801985ee  xor     r14d, r14d
0x1801985f1  mov     [rsp+580h+lpcbData], rax; lpType
0x1801985f6  xor     edx, edx; dwIndex
0x1801985f8  mov     [rsp+580h+var_504], r14d
0x1801985fd  mov     [rbp+480h+var_4D4], 21h ; '!'
0x180198604  call    ?MsiRegEnumValueW@@YAJPEAUHKEY__@@KAEAV?$CAPITempBufferRef@G@@PEAK2212@Z; MsiRegEnumValueW(HKEY__ *,ulong,CAPITempBufferRef<ushort> &,ulong *,ulong *,ulong *,CAPITempBufferRef<ushort> &,ulong *)
0x180198609  mov     ebx, eax
0x18019860b  test    eax, eax
0x18019860d  jnz     loc_180198BDD
0x180198613  lea     r15d, [r14+1]
0x180198617  lea     r11, ?SpecialFolders@@3PAY01V?$CAPITempBuffer@G$0BAE@@@A; CAPITempBuffer<ushort,260> (near * SpecialFolders)[2]
0x18019861e  mov     rcx, [rbp+480h+String2]
0x180198622  xor     edx, edx
0x180198624  call    ??$RemoveSharedDllCountToken@G@@YAHPEAGPEAK@Z; RemoveSharedDllCountToken<ushort>(ushort *,ulong *)
0x180198629  test    eax, eax
0x18019862b  jz      loc_180198B92
0x180198631  cmp     cs:?g_dmDiagnosticMode@@3HA, edx; int g_dmDiagnosticMode
0x180198637  jz      short loc_180198681
0x180198639  mov     rax, [rbp+480h+var_4E0]
0x18019863d  lea     r9, aLowershareddll_0; "\nLowerSharedDLLRefCount: Found shared "...
0x180198644  mov     [rsp+580h+var_528], rdx; void *
0x180198649  lea     ecx, [rdx+9]; int
0x18019864c  mov     [rsp+580h+var_530], edx; unsigned int
0x180198650  xor     r8d, r8d; int
0x180198653  mov     [rsp+580h+var_538], rdi; unsigned __int16 *
0x180198658  mov     [rsp+580h+var_540], rdi; unsigned __int16 *
0x18019865d  mov     [rsp+580h+var_548], rdi; unsigned __int16 *
0x180198662  mov     qword ptr [rsp+580h+cbMaxValueLen], rdi; unsigned __int16 *
0x180198667  mov     [rsp+580h+lpcbData], rax; unsigned __int16 *
0x18019866c  mov     rax, [rbp+480h+String2]
0x180198670  mov     [rsp+580h+lpData], rax; unsigned __int16 *
0x180198675  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18019867a  lea     r11, ?SpecialFolders@@3PAY01V?$CAPITempBuffer@G$0BAE@@@A; CAPITempBuffer<ushort,260> (near * SpecialFolders)[2]
0x180198681  mov     ecx, r15d
0x180198684  mov     [rsp+580h+var_51C], r12d
0x180198689  mov     [rsp+580h+var_520], ecx
0x18019868d  xor     r13d, r13d
0x180198690  test    ecx, ecx
0x180198692  jz      loc_180198B87
0x180198698  cmp     cs:?g_fWinNT64@@3_NA, r12b; bool g_fWinNT64
0x18019869f  jz      loc_180198961
0x1801986a5  xor     r14d, r14d
0x1801986a8  xor     r15d, r15d
0x1801986ab  cmp     r15d, 2
0x1801986af  jge     loc_18019877C
0x1801986b5  movsxd  rax, r15d
0x1801986b8  movsxd  rcx, r14d
0x1801986bb  lea     rcx, [rax+rcx*2]
0x1801986bf  imul    rbx, rcx, 218h
0x1801986c6  mov     rcx, [rbx+r11]; lpString
0x1801986ca  call    cs:__imp_lstrlenW
0x1801986d1  nop     dword ptr [rax+rax+00h]
0x1801986d6  mov     rdx, [rbp+480h+String2]; String2
0x1801986da  lea     rcx, ?SpecialFolders@@3PAY01V?$CAPITempBuffer@G$0BAE@@@A; CAPITempBuffer<ushort,260> (near * SpecialFolders)[2]
0x1801986e1  mov     rcx, [rbx+rcx]; String1
0x1801986e5  movsxd  r8, eax; MaxCount
0x1801986e8  call    cs:__imp__wcsnicmp
0x1801986ef  nop     dword ptr [rax+rax+00h]
0x1801986f4  test    eax, eax
0x1801986f6  jz      loc_180198809
0x1801986fc  inc     r15d
0x1801986ff  lea     r11, ?SpecialFolders@@3PAY01V?$CAPITempBuffer@G$0BAE@@@A; CAPITempBuffer<ushort,260> (near * SpecialFolders)[2]
0x180198706  jmp     short loc_1801986AB
0x180198708  lea     rax, [rsp+580h+hKey]
0x18019870d  xor     r8d, r8d
0x180198710  mov     [rsp+580h+lpData], rax
0x180198715  mov     rcx, 0FFFFFFFF80000002h
0x18019871c  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180198723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198728  mov     ebx, eax
0x18019872a  test    eax, eax
0x18019872c  jz      loc_1801985D4
0x180198732  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x180198738  jz      short loc_180198775
0x18019873a  xor     edx, edx; unsigned __int16
0x18019873c  lea     r9, aLowershareddll_4; "LowerSharedDLLRefCount: RegOpenKeyAPI r"...
0x180198743  mov     [rsp+580h+var_528], rdx; void *
0x180198748  xor     r8d, r8d; int
0x18019874b  mov     [rsp+580h+var_530], edx; unsigned int
0x18019874f  mov     [rsp+580h+var_538], rdi; unsigned __int16 *
0x180198754  mov     [rsp+580h+var_540], rdi; unsigned __int16 *
0x180198759  lea     ecx, [rdx+5]; int
0x18019875c  mov     [rsp+580h+var_548], rdi; unsigned __int16 *
0x180198761  mov     qword ptr [rsp+580h+cbMaxValueLen], rdi; unsigned __int16 *
0x180198766  mov     [rsp+580h+lpcbData], rdi; unsigned __int16 *
0x18019876b  mov     [rsp+580h+lpData], rbx; unsigned __int16 *
0x180198770  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180198775  mov     esi, ebx
0x180198777  jmp     loc_180198C34
0x18019877c  mov     r15d, 1
0x180198782  add     r14d, r15d
0x180198785  cmp     r14d, 3
0x180198789  jb      loc_1801986A8
0x18019878f  xor     eax, eax
0x180198791  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x180198797  jz      short loc_1801987D4
0x180198799  mov     [rsp+580h+var_528], rax; void *
0x18019879e  lea     r9, aNotSpecialPath; "Not special path"
0x1801987a5  mov     [rsp+580h+var_530], eax; unsigned int
0x1801987a9  lea     ecx, [rax+9]; int
0x1801987ac  mov     [rsp+580h+var_538], rdi; unsigned __int16 *
0x1801987b1  xor     edx, edx; unsigned __int16
0x1801987b3  mov     [rsp+580h+var_540], rdi; unsigned __int16 *
0x1801987b8  xor     r8d, r8d; int
0x1801987bb  mov     [rsp+580h+var_548], rdi; unsigned __int16 *
0x1801987c0  mov     qword ptr [rsp+580h+cbMaxValueLen], rdi; unsigned __int16 *
0x1801987c5  mov     [rsp+580h+lpcbData], rdi; unsigned __int16 *
0x1801987ca  mov     [rsp+580h+lpData], rdi; unsigned __int16 *
0x1801987cf  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801987d4  mov     ebx, [rsp+580h+var_51C]
0x1801987d8  test    ebx, ebx
0x1801987da  jnz     loc_18019894A
0x1801987e0  mov     rax, [rbp+480h+var_4F8]
0x1801987e4  mov     [rsp+580h+hKey], rax
0x1801987e9  test    rax, rax
0x1801987ec  jnz     loc_180198966
0x1801987f2  mov     ecx, [rsp+580h+var_520]
0x1801987f6  lea     r11, ?SpecialFolders@@3PAY01V?$CAPITempBuffer@G$0BAE@@@A; CAPITempBuffer<ushort,260> (near * SpecialFolders)[2]
0x1801987fd  mov     ebx, r15d
0x180198800  mov     [rsp+580h+var_51C], ebx
0x180198804  jmp     loc_180198690
0x180198809  cmp     r15d, 1
0x18019880d  mov     r15d, 1
0x180198813  jz      loc_1801988EB
0x180198819  xor     ebx, ebx
0x18019881b  cmp     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x180198821  jz      short loc_18019885E
0x180198823  xor     edx, edx; unsigned __int16
0x180198825  lea     r9, aSpecial32BitPa; "Special 32 bit path"
0x18019882c  mov     [rsp+580h+var_528], rdx; void *
0x180198831  lea     ecx, [rbx+9]; int
0x180198834  mov     [rsp+580h+var_530], edx; unsigned int
0x180198838  xor     r8d, r8d; int
0x18019883b  mov     [rsp+580h+var_538], rdi; unsigned __int16 *
0x180198840  mov     [rsp+580h+var_540], rdi; unsigned __int16 *
0x180198845  mov     [rsp+580h+var_548], rdi; unsigned __int16 *
0x18019884a  mov     qword ptr [rsp+580h+cbMaxValueLen], rdi; unsigned __int16 *
0x18019884f  mov     [rsp+580h+lpcbData], rdi; unsigned __int16 *
0x180198854  mov     [rsp+580h+lpData], rdi; unsigned __int16 *
0x180198859  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18019885e  test    r14d, r14d
0x180198861  jnz     short loc_1801988CB
0x180198863  movsxd  rdx, [rbp+480h+var_258]; unsigned __int64
0x18019886a  lea     r11, ?SpecialFolders@@3PAY01V?$CAPITempBuffer@G$0BAE@@@A; CAPITempBuffer<ushort,260> (near * SpecialFolders)[2]
0x180198871  mov     rcx, [rbp+480h+hMem]; unsigned __int16 *
0x180198878  movsxd  rax, r14d
0x18019887b  imul    r10, rax, 430h
0x180198882  mov     r8, [r10+r11+218h]; unsigned __int16 *
0x18019888a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18019888f  test    eax, eax
0x180198891  js      short loc_1801988C5
0x180198893  mov     rcx, [r10+r11]; lpString
0x180198897  call    cs:__imp_lstrlenW
0x18019889e  nop     dword ptr [rax+rax+00h]
0x1801988a3  mov     rcx, [rbp+480h+hMem]; unsigned __int16 *
0x1801988aa  movsxd  rdx, eax
0x1801988ad  mov     rax, [rbp+480h+String2]
0x1801988b1  lea     r8, [rax+rdx*2]; unsigned __int16 *
0x1801988b5  movsxd  rdx, [rbp+480h+var_258]; unsigned __int64
0x1801988bc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801988c1  test    eax, eax
0x1801988c3  jns     short loc_1801988C8
0x1801988c5  mov     ebx, r15d
0x1801988c8  mov     r13d, r15d
0x1801988cb  mov     rax, [rbp+480h+var_4F8]
0x1801988cf  test    rax, rax
0x1801988d2  mov     [rsp+580h+hKey], rax
0x1801988d7  cmovz   ebx, r15d
0x1801988db  xor     ecx, ecx
0x1801988dd  mov     [rsp+580h+var_520], ecx
0x1801988e1  test    ebx, ebx
0x1801988e3  jnz     loc_180198B6C
0x1801988e9  jmp     short loc_180198966
0x1801988eb  xor     ecx, ecx
0x1801988ed  cmp     cs:?g_dmDiagnosticMode@@3HA, ecx; int g_dmDiagnosticMode
  ... truncated ...
```
