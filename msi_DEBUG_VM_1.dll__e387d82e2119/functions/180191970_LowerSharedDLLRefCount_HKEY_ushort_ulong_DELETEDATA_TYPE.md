# LowerSharedDLLRefCount(HKEY__ *,ushort *,ulong,DELETEDATA_TYPE)

- ea: `0x180191970`
- end: `0x180192286`
- name: `?LowerSharedDLLRefCount@@YAIPEAUHKEY__@@PEAGKW4DELETEDATA_TYPE@@@Z`
- size: `2326`
- prototype: `unsigned int __high(HKEY, unsigned __int16 *, unsigned int, enum DELETEDATA_TYPE)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180019bb4`
- `0x180025560`
- `0x1800255e0`
- `0x180025a18`
- `0x180072450`
- `0x1800e1864`
- `0x180191970`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180191c92`
- `msvcrt!_wcsnicmp` at `0x180191c92`
- `ADVAPI32!RegQueryValueExW` at `0x180191f40`
- `ADVAPI32!RegQueryValueExW` at `0x180191f40`
- `ADVAPI32!RegCloseKey` at `0x1801921cf`
- `ADVAPI32!RegCloseKey` at `0x1801921e7`
- `ADVAPI32!RegCloseKey` at `0x1801921fd`
- `ADVAPI32!RegCloseKey` at `0x1801921cf`
- `ADVAPI32!RegCloseKey` at `0x1801921e7`
- `ADVAPI32!RegCloseKey` at `0x1801921fd`
- `ADVAPI32!RegSetValueExW` at `0x180192022`
- `ADVAPI32!RegSetValueExW` at `0x180192022`
- `KERNEL32!lstrlenW` at `0x180191c7a`
- `KERNEL32!lstrlenW` at `0x180191e3b`
- `KERNEL32!lstrlenW` at `0x180191c7a`
- `KERNEL32!lstrlenW` at `0x180191e3b`
- `KERNEL32!GlobalFree` at `0x180192213`
- `KERNEL32!GlobalFree` at `0x180192238`
- `KERNEL32!GlobalFree` at `0x180192254`
- `KERNEL32!GlobalFree` at `0x180192213`
- `KERNEL32!GlobalFree` at `0x180192238`
- `KERNEL32!GlobalFree` at `0x180192254`

## string_xrefs

- `0x180191a83`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SharedDLLs`
- `0x180191b0c`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SharedDLLs`
- `0x180191a3b`: `LowerSharedDLLRefCount: RegOpenKeyEx returned %08x.`
- `0x180191ac3`: `LowerSharedDLLRefCount: MsiRegOpen64bitKey returned %08x.`
- `0x180191b36`: `LowerSharedDLLRefCount: RegOpenKeyAPI returned %08x.`
- `0x180191ce0`: `LowerSharedDLLRefCount: RegOpenKeyAPI returned %08x.`
- `0x180191bed`: `\nLowerSharedDLLRefCount: Found shared DLL %s in component %s`
- `0x180191d42`: `Not special path`
- `0x180191e9c`: `Special 64 bit path`
- `0x180191dc9`: `Special 32 bit path`
- `0x180191fc0`: `LowerSharedDllRefCount: RegQueryValueEx: Can not decrement the ref count for shared dll %s with error %08x.`
- `0x1801920a6`: `LowerSharedDllRefCount: RegSetValueEx: Can not decrement the ref count for shared dll %s with error %s.`
- `0x1801920bf`: `LowerSharedDllRefCount: ref count for %s decremented.`
- `0x18019218d`: `LowerSharedDLLRefCount <%s>: MsiRegEnumValue returned %d.`

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
0x180191970  mov     [rsp-8+arg_10], rbx
0x180191975  push    rbp
0x180191976  push    rsi
0x180191977  push    rdi
0x180191978  push    r12
0x18019197a  push    r13
0x18019197c  push    r14
0x18019197e  push    r15
0x180191980  lea     rbp, [rsp-450h]
0x180191988  sub     rsp, 550h
0x18019198f  mov     rax, cs:__security_cookie
0x180191996  xor     rax, rsp
0x180191999  mov     [rbp+480h+var_40], rax
0x1801919a0  xor     r12d, r12d
0x1801919a3  mov     [rbp+480h+var_4E8], rdx
0x1801919a7  lea     rax, [rbp+480h+var_4D0]
0x1801919ab  mov     [rbp+480h+var_4F0], r12
0x1801919af  mov     [rbp+480h+var_4E0], rax
0x1801919b3  mov     r13d, 104h
0x1801919b9  lea     rax, [rbp+480h+var_470]
0x1801919bd  mov     [rsp+580h+hKey], r12
0x1801919c2  mov     [rbp+480h+String2], rax
0x1801919c6  mov     r9d, 20019h; unsigned int
0x1801919cc  lea     rax, [rbp+480h+var_250]
0x1801919d3  mov     [rbp+480h+var_500], r12
0x1801919d7  mov     [rbp+480h+hMem], rax
0x1801919de  mov     r15, rdx
0x1801919e1  lea     rax, [rbp+480h+var_4F0]
0x1801919e5  mov     [rbp+480h+var_4F8], r12
0x1801919e9  mov     [rsp+580h+lpData], rax; HKEY *
0x1801919ee  mov     [rbp+480h+var_4D8], 21h ; '!'
0x1801919f5  mov     [rsp+580h+Type], r12d
0x1801919fa  mov     [rbp+480h+var_478], r13d
0x1801919fe  mov     [rbp+480h+var_258], r13d
0x180191a05  mov     dword ptr [rsp+580h+Data], r12d
0x180191a0a  mov     [rsp+580h+cbData], 4
0x180191a12  call    ?MsiRegOpen64bitKey@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; MsiRegOpen64bitKey(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180191a17  mov     esi, eax
0x180191a19  test    eax, eax
0x180191a1b  jz      short loc_180191A72
0x180191a1d  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180191a24  jz      loc_1801921C6
0x180191a2a  mov     [rsp+580h+var_528], r12; void *
0x180191a2f  lea     rdi, aNull; "(NULL)"
0x180191a36  mov     [rsp+580h+var_530], r12d; unsigned int
0x180191a3b  lea     r9, aLowershareddll; "LowerSharedDLLRefCount: RegOpenKeyEx re"...
0x180191a42  mov     [rsp+580h+var_538], rdi; unsigned __int16 *
0x180191a47  xor     edx, edx; unsigned __int16
0x180191a49  mov     [rsp+580h+var_540], rdi; unsigned __int16 *
0x180191a4e  xor     r8d, r8d; int
0x180191a51  mov     [rsp+580h+var_548], rdi; unsigned __int16 *
0x180191a56  mov     qword ptr [rsp+580h+cbMaxValueLen], rdi; unsigned __int16 *
0x180191a5b  mov     [rsp+580h+lpcbData], rdi; unsigned __int16 *
0x180191a60  lea     ecx, [rdx+0Ah]; int
0x180191a63  mov     [rsp+580h+lpData], rsi; unsigned __int16 *
0x180191a68  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180191a6d  jmp     loc_1801921C6
0x180191a72  cmp     cs:?g_fWinNT64@@3_NA, r12b; bool g_fWinNT64
0x180191a79  lea     rdi, aNull; "(NULL)"
0x180191a80  mov     esi, r12d
0x180191a83  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180191a8a  mov     r9d, 0F003Fh; unsigned int
0x180191a90  jz      loc_180191CAC
0x180191a96  lea     rax, [rbp+480h+var_500]
0x180191a9a  mov     rbx, 0FFFFFFFF80000002h
0x180191aa1  mov     rcx, rbx; HKEY
0x180191aa4  mov     [rsp+580h+lpData], rax; HKEY *
0x180191aa9  call    ?MsiRegOpen64bitKey@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; MsiRegOpen64bitKey(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180191aae  mov     r14d, eax
0x180191ab1  test    eax, eax
0x180191ab3  jz      short loc_180191AFD
0x180191ab5  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180191abc  jz      short loc_180191AFA
0x180191abe  mov     [rsp+580h+var_528], r12; void *
0x180191ac3  lea     r9, aLowershareddll_2; "LowerSharedDLLRefCount: MsiRegOpen64bit"...
0x180191aca  mov     [rsp+580h+var_530], r12d; unsigned int
0x180191acf  xor     edx, edx; unsigned __int16
0x180191ad1  mov     [rsp+580h+var_538], rdi; unsigned __int16 *
0x180191ad6  xor     r8d, r8d; int
0x180191ad9  mov     [rsp+580h+var_540], rdi; unsigned __int16 *
0x180191ade  mov     [rsp+580h+var_548], rdi; unsigned __int16 *
0x180191ae3  mov     qword ptr [rsp+580h+cbMaxValueLen], rdi; unsigned __int16 *
0x180191ae8  lea     ecx, [rdx+5]; int
0x180191aeb  mov     [rsp+580h+lpcbData], rdi; unsigned __int16 *
0x180191af0  mov     [rsp+580h+lpData], r14; unsigned __int16 *
0x180191af5  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180191afa  mov     esi, r14d
0x180191afd  lea     rax, [rbp+480h+var_4F8]
0x180191b01  mov     r9d, 0F023Fh
0x180191b07  mov     [rsp+580h+lpData], rax
0x180191b0c  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180191b13  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180191b1a  xor     r8d, r8d
0x180191b1d  mov     rcx, rbx
0x180191b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180191b25  mov     ebx, eax
0x180191b27  test    eax, eax
0x180191b29  jz      short loc_180191B74
0x180191b2b  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180191b32  jz      short loc_180191B6F
0x180191b34  xor     edx, edx; unsigned __int16
0x180191b36  lea     r9, aLowershareddll_4; "LowerSharedDLLRefCount: RegOpenKeyAPI r"...
0x180191b3d  mov     [rsp+580h+var_528], rdx; void *
0x180191b42  xor     r8d, r8d; int
0x180191b45  mov     [rsp+580h+var_530], edx; unsigned int
0x180191b49  mov     [rsp+580h+var_538], rdi; unsigned __int16 *
0x180191b4e  mov     [rsp+580h+var_540], rdi; unsigned __int16 *
0x180191b53  lea     ecx, [rdx+5]; int
0x180191b56  mov     [rsp+580h+var_548], rdi; unsigned __int16 *
0x180191b5b  mov     qword ptr [rsp+580h+cbMaxValueLen], rdi; unsigned __int16 *
0x180191b60  mov     [rsp+580h+lpcbData], rdi; unsigned __int16 *
0x180191b65  mov     [rsp+580h+lpData], rbx; int
0x180191b6a  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180191b6f  test    esi, esi
0x180191b71  cmovz   esi, ebx
0x180191b74  cmp     [rbp+480h+var_500], r12
0x180191b78  jnz     short loc_180191B84
0x180191b7a  cmp     [rbp+480h+var_4F8], r12
0x180191b7e  jz      loc_1801921C6
0x180191b84  mov     rcx, [rbp+480h+var_4F0]; hKey
0x180191b88  lea     rax, [rbp+480h+String2]
0x180191b8c  mov     qword ptr [rsp+580h+cbMaxValueLen], rax; cbMaxValueLen
0x180191b91  lea     r8, [rbp+480h+var_4E0]
0x180191b95  lea     rax, [rsp+580h+Type]
0x180191b9a  mov     [rbp+480h+var_474], r13d
0x180191b9e  xor     r14d, r14d
0x180191ba1  mov     [rsp+580h+lpcbData], rax; lpType
0x180191ba6  xor     edx, edx; dwIndex
0x180191ba8  mov     [rsp+580h+var_504], r14d
0x180191bad  mov     [rbp+480h+var_4D4], 21h ; '!'
0x180191bb4  call    ?MsiRegEnumValueW@@YAJPEAUHKEY__@@KAEAV?$CAPITempBufferRef@G@@PEAK2212@Z; MsiRegEnumValueW(HKEY__ *,ulong,CAPITempBufferRef<ushort> &,ulong *,ulong *,ulong *,CAPITempBufferRef<ushort> &,ulong *)
0x180191bb9  mov     ebx, eax
0x180191bbb  test    eax, eax
0x180191bbd  jnz     loc_18019216F
0x180191bc3  lea     r15d, [r14+1]
0x180191bc7  lea     r11, ?SpecialFolders@@3PAY01V?$CAPITempBuffer@G$0BAE@@@A; CAPITempBuffer<ushort,260> (near * SpecialFolders)[2]
0x180191bce  mov     rcx, [rbp+480h+String2]
0x180191bd2  xor     edx, edx
0x180191bd4  call    ??$RemoveSharedDllCountToken@G@@YAHPEAGPEAK@Z; RemoveSharedDllCountToken<ushort>(ushort *,ulong *)
0x180191bd9  test    eax, eax
0x180191bdb  jz      loc_180192124
0x180191be1  cmp     cs:?g_dmDiagnosticMode@@3HA, edx; int g_dmDiagnosticMode
0x180191be7  jz      short loc_180191C31
0x180191be9  mov     rax, [rbp+480h+var_4E0]
0x180191bed  lea     r9, aLowershareddll_0; "\nLowerSharedDLLRefCount: Found shared "...
0x180191bf4  mov     [rsp+580h+var_528], rdx; void *
0x180191bf9  lea     ecx, [rdx+9]; int
0x180191bfc  mov     [rsp+580h+var_530], edx; unsigned int
0x180191c00  xor     r8d, r8d; int
0x180191c03  mov     [rsp+580h+var_538], rdi; unsigned __int16 *
0x180191c08  mov     [rsp+580h+var_540], rdi; unsigned __int16 *
0x180191c0d  mov     [rsp+580h+var_548], rdi; unsigned __int16 *
0x180191c12  mov     qword ptr [rsp+580h+cbMaxValueLen], rdi; unsigned __int16 *
0x180191c17  mov     [rsp+580h+lpcbData], rax; unsigned __int16 *
0x180191c1c  mov     rax, [rbp+480h+String2]
0x180191c20  mov     [rsp+580h+lpData], rax; unsigned __int16 *
0x180191c25  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180191c2a  lea     r11, ?SpecialFolders@@3PAY01V?$CAPITempBuffer@G$0BAE@@@A; CAPITempBuffer<ushort,260> (near * SpecialFolders)[2]
0x180191c31  mov     ecx, r15d
0x180191c34  mov     [rsp+580h+var_51C], r12d
0x180191c39  mov     [rsp+580h+var_520], ecx
0x180191c3d  xor     r13d, r13d
0x180191c40  test    ecx, ecx
0x180191c42  jz      loc_180192119
0x180191c48  cmp     cs:?g_fWinNT64@@3_NA, r12b; bool g_fWinNT64
0x180191c4f  jz      loc_180191EFF
0x180191c55  xor     r14d, r14d
0x180191c58  xor     r15d, r15d
0x180191c5b  cmp     r15d, 2
0x180191c5f  jge     loc_180191D20
0x180191c65  movsxd  rax, r15d
0x180191c68  movsxd  rcx, r14d
0x180191c6b  lea     rcx, [rax+rcx*2]
0x180191c6f  imul    rbx, rcx, 218h
0x180191c76  mov     rcx, [rbx+r11]; lpString
0x180191c7a  call    cs:__imp_lstrlenW
0x180191c80  mov     rdx, [rbp+480h+String2]; String2
0x180191c84  lea     rcx, ?SpecialFolders@@3PAY01V?$CAPITempBuffer@G$0BAE@@@A; CAPITempBuffer<ushort,260> (near * SpecialFolders)[2]
0x180191c8b  mov     rcx, [rbx+rcx]; String1
0x180191c8f  movsxd  r8, eax; MaxCount
0x180191c92  call    cs:__imp__wcsnicmp
0x180191c98  test    eax, eax
0x180191c9a  jz      loc_180191DAD
0x180191ca0  inc     r15d
0x180191ca3  lea     r11, ?SpecialFolders@@3PAY01V?$CAPITempBuffer@G$0BAE@@@A; CAPITempBuffer<ushort,260> (near * SpecialFolders)[2]
0x180191caa  jmp     short loc_180191C5B
0x180191cac  lea     rax, [rsp+580h+hKey]
0x180191cb1  xor     r8d, r8d
0x180191cb4  mov     [rsp+580h+lpData], rax
0x180191cb9  mov     rcx, 0FFFFFFFF80000002h
0x180191cc0  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180191cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180191ccc  mov     ebx, eax
0x180191cce  test    eax, eax
0x180191cd0  jz      loc_180191B84
0x180191cd6  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x180191cdc  jz      short loc_180191D19
0x180191cde  xor     edx, edx; unsigned __int16
0x180191ce0  lea     r9, aLowershareddll_4; "LowerSharedDLLRefCount: RegOpenKeyAPI r"...
0x180191ce7  mov     [rsp+580h+var_528], rdx; void *
0x180191cec  xor     r8d, r8d; int
0x180191cef  mov     [rsp+580h+var_530], edx; unsigned int
0x180191cf3  mov     [rsp+580h+var_538], rdi; unsigned __int16 *
0x180191cf8  mov     [rsp+580h+var_540], rdi; unsigned __int16 *
0x180191cfd  lea     ecx, [rdx+5]; int
0x180191d00  mov     [rsp+580h+var_548], rdi; unsigned __int16 *
0x180191d05  mov     qword ptr [rsp+580h+cbMaxValueLen], rdi; unsigned __int16 *
0x180191d0a  mov     [rsp+580h+lpcbData], rdi; unsigned __int16 *
0x180191d0f  mov     [rsp+580h+lpData], rbx; unsigned __int16 *
0x180191d14  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180191d19  mov     esi, ebx
0x180191d1b  jmp     loc_1801921C6
0x180191d20  mov     r15d, 1
0x180191d26  add     r14d, r15d
0x180191d29  cmp     r14d, 3
0x180191d2d  jb      loc_180191C58
0x180191d33  xor     eax, eax
0x180191d35  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x180191d3b  jz      short loc_180191D78
0x180191d3d  mov     [rsp+580h+var_528], rax; void *
0x180191d42  lea     r9, aNotSpecialPath; "Not special path"
0x180191d49  mov     [rsp+580h+var_530], eax; unsigned int
0x180191d4d  lea     ecx, [rax+9]; int
0x180191d50  mov     [rsp+580h+var_538], rdi; unsigned __int16 *
0x180191d55  xor     edx, edx; unsigned __int16
0x180191d57  mov     [rsp+580h+var_540], rdi; unsigned __int16 *
0x180191d5c  xor     r8d, r8d; int
0x180191d5f  mov     [rsp+580h+var_548], rdi; unsigned __int16 *
0x180191d64  mov     qword ptr [rsp+580h+cbMaxValueLen], rdi; unsigned __int16 *
0x180191d69  mov     [rsp+580h+lpcbData], rdi; unsigned __int16 *
0x180191d6e  mov     [rsp+580h+lpData], rdi; unsigned __int16 *
0x180191d73  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180191d78  mov     ebx, [rsp+580h+var_51C]
0x180191d7c  test    ebx, ebx
0x180191d7e  jnz     loc_180191EE8
0x180191d84  mov     rax, [rbp+480h+var_4F8]
0x180191d88  mov     [rsp+580h+hKey], rax
0x180191d8d  test    rax, rax
0x180191d90  jnz     loc_180191F04
0x180191d96  mov     ecx, [rsp+580h+var_520]
0x180191d9a  lea     r11, ?SpecialFolders@@3PAY01V?$CAPITempBuffer@G$0BAE@@@A; CAPITempBuffer<ushort,260> (near * SpecialFolders)[2]
0x180191da1  mov     ebx, r15d
0x180191da4  mov     [rsp+580h+var_51C], ebx
0x180191da8  jmp     loc_180191C40
0x180191dad  cmp     r15d, 1
0x180191db1  mov     r15d, 1
0x180191db7  jz      loc_180191E89
0x180191dbd  xor     ebx, ebx
0x180191dbf  cmp     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x180191dc5  jz      short loc_180191E02
0x180191dc7  xor     edx, edx; unsigned __int16
0x180191dc9  lea     r9, aSpecial32BitPa; "Special 32 bit path"
0x180191dd0  mov     [rsp+580h+var_528], rdx; void *
0x180191dd5  lea     ecx, [rbx+9]; int
0x180191dd8  mov     [rsp+580h+var_530], edx; unsigned int
0x180191ddc  xor     r8d, r8d; int
0x180191ddf  mov     [rsp+580h+var_538], rdi; unsigned __int16 *
0x180191de4  mov     [rsp+580h+var_540], rdi; unsigned __int16 *
0x180191de9  mov     [rsp+580h+var_548], rdi; unsigned __int16 *
0x180191dee  mov     qword ptr [rsp+580h+cbMaxValueLen], rdi; unsigned __int16 *
0x180191df3  mov     [rsp+580h+lpcbData], rdi; unsigned __int16 *
0x180191df8  mov     [rsp+580h+lpData], rdi; unsigned __int16 *
0x180191dfd  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180191e02  test    r14d, r14d
0x180191e05  jnz     short loc_180191E69
0x180191e07  movsxd  rdx, [rbp+480h+var_258]; unsigned __int64
0x180191e0e  lea     r11, ?SpecialFolders@@3PAY01V?$CAPITempBuffer@G$0BAE@@@A; CAPITempBuffer<ushort,260> (near * SpecialFolders)[2]
0x180191e15  mov     rcx, [rbp+480h+hMem]; unsigned __int16 *
0x180191e1c  movsxd  rax, r14d
0x180191e1f  imul    r10, rax, 430h
0x180191e26  mov     r8, [r10+r11+218h]; unsigned __int16 *
0x180191e2e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180191e33  test    eax, eax
0x180191e35  js      short loc_180191E63
0x180191e37  mov     rcx, [r10+r11]; lpString
0x180191e3b  call    cs:__imp_lstrlenW
0x180191e41  mov     rcx, [rbp+480h+hMem]; unsigned __int16 *
0x180191e48  movsxd  rdx, eax
0x180191e4b  mov     rax, [rbp+480h+String2]
0x180191e4f  lea     r8, [rax+rdx*2]; unsigned __int16 *
0x180191e53  movsxd  rdx, [rbp+480h+var_258]; unsigned __int64
0x180191e5a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180191e5f  test    eax, eax
0x180191e61  jns     short loc_180191E66
0x180191e63  mov     ebx, r15d
0x180191e66  mov     r13d, r15d
0x180191e69  mov     rax, [rbp+480h+var_4F8]
0x180191e6d  test    rax, rax
0x180191e70  mov     [rsp+580h+hKey], rax
0x180191e75  cmovz   ebx, r15d
0x180191e79  xor     ecx, ecx
0x180191e7b  mov     [rsp+580h+var_520], ecx
0x180191e7f  test    ebx, ebx
0x180191e81  jnz     loc_1801920FE
0x180191e87  jmp     short loc_180191F04
0x180191e89  xor     ecx, ecx
0x180191e8b  cmp     cs:?g_dmDiagnosticMode@@3HA, ecx; int g_dmDiagnosticMode
0x180191e91  mov     [rsp+580h+var_520], ecx
0x180191e95  jz      short loc_180191ED5
0x180191e97  mov     [rsp+580h+var_528], rcx; void *
  ... truncated ...
```
