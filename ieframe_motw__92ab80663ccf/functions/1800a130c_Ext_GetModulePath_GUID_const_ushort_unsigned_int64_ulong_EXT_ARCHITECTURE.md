# Ext_GetModulePath(_GUID const &,ushort *,unsigned __int64,ulong,_EXT_ARCHITECTURE *)

- ea: `0x1800a130c`
- end: `0x1800a1729`
- name: `?Ext_GetModulePath@@YAJAEBU_GUID@@PEAG_KKPEAW4_EXT_ARCHITECTURE@@@Z`
- size: `1053`
- prototype: `int(const struct _GUID *, unsigned __int16 *, unsigned __int64, unsigned int, enum _EXT_ARCHITECTURE *)`
- caller_count: `13`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801a2f5c`
- `0x1801a67fc`
- `0x1803f60f8`
- `0x1803f6278`
- `0x1803fae14`
- `0x1804038f0`
- `0x180403980`
- `0x180404130`
- `0x18051df70`
- `0x18051ebfc`
- `0x18051efc8`
- `0x18052fb60`
- `0x180589a38`

## callees

- `0x180009610`
- `0x1800144d0`
- `0x180024b74`
- `0x1800a130c`
- `0x18051e0e8`
- `0x180591f80`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x1800a14c9`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800a14c9`
- `KERNEL32!GetLongPathNameW` at `0x1800a16ca`
- `KERNEL32!GetLongPathNameW` at `0x1800a16ca`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1800a158a`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1800a168f`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1800a158a`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1800a168f`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1800a142e`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1800a162d`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1800a142e`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1800a162d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathUnquoteSpacesW` at `0x1800a16ae`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathUnquoteSpacesW` at `0x1800a16ae`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1800a14b3`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1800a14b3`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x1800a1559`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x1800a1559`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetTreatAsClass` at `0x1800a1359`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetTreatAsClass` at `0x1800a1359`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x1800a13ad`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x1800a13ad`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x1800a1486`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x1800a1516`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x1800a1672`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x1800a1486`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x1800a1516`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x1800a1672`

## string_xrefs

- `0x1800a14c2`: `mscoree.dll`
- `0x1800a13df`: `CLSID\%s\%s`
- `0x1800a15ca`: `CLSID\%s\%s`

## pseudocode

```c
__int64 __fastcall Ext_GetModulePath(
        const struct _GUID *a1,
        unsigned __int16 *a2,
        unsigned __int64 a3,
        char a4,
        enum _EXT_ARCHITECTURE *a5)
{
  HRESULT TreatAsClass; // eax
  int ArchitectureHelper; // ebx
  unsigned __int64 v10; // rsi
  unsigned __int16 *pvData; // rdi
  LSTATUS v12; // eax
  bool v13; // zf
  LSTATUS v14; // eax
  const WCHAR *FileNameW; // rax
  LSTATUS v16; // eax
  bool v17; // sf
  WCHAR *v18; // r8
  LSTATUS v19; // eax
  bool v20; // zf
  LSTATUS ValueW; // eax
  DWORD LongPathNameW; // eax
  HKEY hkey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v25; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcchPath; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD pdwType; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+54h] [rbp-ACh] BYREF
  GUID pClsidNew; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR sz[40]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR szLongPath[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR pszPath[264]; // [rsp+4E0h] [rbp+3E0h] BYREF

  pClsidNew = 0;
  TreatAsClass = CoGetTreatAsClass(a1, &pClsidNew);
  ArchitectureHelper = TreatAsClass;
  if ( a5 )
    *(_DWORD *)a5 = 0;
  v10 = 260;
  if ( a2 )
    v10 = a3;
  pvData = szLongPath;
  if ( a2 )
    pvData = a2;
  if ( TreatAsClass >= 0 )
  {
    hkey = 0;
    sz[0] = 0;
    ArchitectureHelper = StringFromGUID2(&pClsidNew, sz, 39);
    if ( ArchitectureHelper < 0 )
      goto LABEL_29;
    ArchitectureHelper = StringCchPrintfW(SubKey, 0x104u, L"CLSID\\%s\\%s", sz, L"InProcServer32");
    if ( ArchitectureHelper < 0 )
      goto LABEL_29;
    if ( (a4 & 0x10) != 0 )
    {
      ArchitectureHelper = Ext_GetArchitectureHelper(HKEY_CLASSES_ROOT, SubKey, &hkey, a5);
    }
    else
    {
      v12 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 1u, &hkey);
      ArchitectureHelper = v12;
      if ( v12 > 0 )
        ArchitectureHelper = (unsigned __int16)v12 | 0x80070000;
    }
    v13 = ArchitectureHelper == 0;
    if ( ArchitectureHelper < 0 )
    {
LABEL_30:
      if ( v13 )
      {
LABEL_44:
        if ( pvData != szLongPath )
        {
          PathUnquoteSpacesW(pvData);
          LongPathNameW = GetLongPathNameW(pvData, szLongPath, 0x104u);
          if ( LongPathNameW - 1 <= 0x102 && LongPathNameW < v10 )
            StringCchCopyW(pvData, v10, szLongPath);
        }
        return (unsigned int)ArchitectureHelper;
      }
      if ( !sz[0] || (a4 & 6) == 0 )
        return (unsigned int)ArchitectureHelper;
      ArchitectureHelper = StringCchPrintfW(SubKey, 0x104u, L"CLSID\\%s\\%s", sz, L"LocalServer32");
      if ( ArchitectureHelper >= 0 )
      {
        pcchPath = 2 * v10;
        v25 = 1;
        if ( (a4 & 0x10) != 0 )
        {
          ArchitectureHelper = Ext_GetArchitectureHelper(HKEY_CLASSES_ROOT, SubKey, &hkey, a5);
        }
        else
        {
          v19 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 1u, &hkey);
          ArchitectureHelper = v19;
          if ( v19 > 0 )
            ArchitectureHelper = (unsigned __int16)v19 | 0x80070000;
        }
        v20 = ArchitectureHelper == 0;
        if ( ArchitectureHelper < 0 )
        {
LABEL_43:
          if ( !v20 )
            return (unsigned int)ArchitectureHelper;
          goto LABEL_44;
        }
        ValueW = SHRegGetValueW(hkey, 0, 0, 2, &v25, pvData, &pcchPath);
        ArchitectureHelper = ValueW;
        if ( ValueW > 0 )
          ArchitectureHelper = (unsigned __int16)ValueW | 0x80070000;
        RegCloseKey(hkey);
      }
      v20 = ArchitectureHelper == 0;
      goto LABEL_43;
    }
    pcbData = 2 * v10;
    pdwType = 1;
    v14 = SHRegGetValueW(hkey, 0, 0, 2, &pdwType, pvData, &pcbData);
    ArchitectureHelper = v14;
    if ( v14 > 0 )
      ArchitectureHelper = (unsigned __int16)v14 | 0x80070000;
    if ( ArchitectureHelper >= 0 && (a4 & 7) != 0 )
    {
      FileNameW = PathFindFileNameW(pvData);
      if ( !StrCmpICW(FileNameW, L"mscoree.dll") )
      {
        v25 = 520;
        v16 = SHRegGetValueW(hkey, 0, L"CodeBase", 2, &pdwType, SubKey, &v25);
        v17 = v16 < 0;
        if ( v16 > 0 )
          v17 = 1;
        if ( !v17 )
        {
          if ( (unsigned int)GetUrlSchemeW(SubKey) != 9 )
          {
            v18 = SubKey;
            goto LABEL_27;
          }
          pcchPath = 260;
          ArchitectureHelper = PathCreateFromUrlW(SubKey, pszPath, &pcchPath, 0);
          if ( ArchitectureHelper >= 0 )
          {
            v18 = pszPath;
LABEL_27:
            ArchitectureHelper = StringCchCopyW(pvData, v10, v18);
          }
        }
      }
    }
    RegCloseKey(hkey);
LABEL_29:
    v13 = ArchitectureHelper == 0;
    goto LABEL_30;
  }
  return (unsigned int)ArchitectureHelper;
}

```

## disassembly

```asm
0x1800a130c  mov     [rsp-8+arg_18], rbx
0x1800a1311  push    rbp
0x1800a1312  push    rsi
0x1800a1313  push    rdi
0x1800a1314  push    r12
0x1800a1316  push    r13
0x1800a1318  push    r14
0x1800a131a  push    r15
0x1800a131c  lea     rbp, [rsp-600h]
0x1800a1324  sub     rsp, 700h
0x1800a132b  mov     rax, cs:__security_cookie
0x1800a1332  xor     rax, rsp
0x1800a1335  mov     [rbp+630h+var_40], rax
0x1800a133c  mov     r12, [rbp+630h+arg_20]
0x1800a1343  mov     r14, rdx
0x1800a1346  xorps   xmm0, xmm0
0x1800a1349  lea     rdx, [rsp+730h+pClsidNew]; pClsidNew
0x1800a134e  movups  xmmword ptr [rsp+730h+pClsidNew.Data1], xmm0
0x1800a1353  mov     r15d, r9d
0x1800a1356  mov     rdi, r8
0x1800a1359  call    cs:__imp_CoGetTreatAsClass
0x1800a1360  nop     dword ptr [rax+rax+00h]
0x1800a1365  xor     r13d, r13d
0x1800a1368  mov     ebx, eax
0x1800a136a  test    r12, r12
0x1800a136d  jz      short loc_1800A1373
0x1800a136f  mov     [r12], r13d
0x1800a1373  test    r14, r14
0x1800a1376  mov     esi, 104h
0x1800a137b  cmovnz  rsi, rdi
0x1800a137f  lea     rdi, [rbp+630h+szLongPath]
0x1800a1386  cmovnz  rdi, r14
0x1800a138a  test    eax, eax
0x1800a138c  js      loc_1800A16FC
0x1800a1392  mov     r8d, 27h ; '''; cchMax
0x1800a1398  mov     [rsp+730h+hkey], r13
0x1800a139d  lea     rdx, [rsp+730h+sz]; lpsz
0x1800a13a2  mov     [rsp+730h+sz], r13w
0x1800a13a8  lea     rcx, [rsp+730h+pClsidNew]; rguid
0x1800a13ad  call    cs:__imp_StringFromGUID2
0x1800a13b4  nop     dword ptr [rax+rax+00h]
0x1800a13b9  mov     ebx, eax
0x1800a13bb  mov     r14d, 80070000h
0x1800a13c1  test    eax, eax
0x1800a13c3  js      loc_1800A1596
0x1800a13c9  lea     rax, aInprocserver32; "InProcServer32"
0x1800a13d0  mov     edx, 104h; unsigned __int64
0x1800a13d5  lea     r9, [rsp+730h+sz]
0x1800a13da  mov     [rsp+730h+phkResult], rax
0x1800a13df  lea     r8, aClsidSS; "CLSID\\%s\\%s"
0x1800a13e6  lea     rcx, [rbp+630h+SubKey]; unsigned __int16 *
0x1800a13ea  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a13ef  mov     ebx, eax
0x1800a13f1  test    eax, eax
0x1800a13f3  js      loc_1800A1596
0x1800a13f9  lea     rdx, [rbp+630h+SubKey]; lpSubKey
0x1800a13fd  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800a1404  test    r15b, 10h
0x1800a1408  jz      short loc_1800A141B
0x1800a140a  mov     r9, r12; enum _EXT_ARCHITECTURE *
0x1800a140d  lea     r8, [rsp+730h+hkey]; HKEY *
0x1800a1412  call    ?Ext_GetArchitectureHelper@@YAJPEAUHKEY__@@PEBGPEAPEAU1@PEAW4_EXT_ARCHITECTURE@@@Z; Ext_GetArchitectureHelper(HKEY__ *,ushort const *,HKEY__ * *,_EXT_ARCHITECTURE *)
0x1800a1417  mov     ebx, eax
0x1800a1419  jmp     short loc_1800A1446
0x1800a141b  lea     rax, [rsp+730h+hkey]
0x1800a1420  mov     r9d, 1; samDesired
0x1800a1426  xor     r8d, r8d; ulOptions
0x1800a1429  mov     [rsp+730h+phkResult], rax; phkResult
0x1800a142e  call    cs:__imp_RegOpenKeyExW
0x1800a1435  nop     dword ptr [rax+rax+00h]
0x1800a143a  mov     ebx, eax
0x1800a143c  test    eax, eax
0x1800a143e  jle     short loc_1800A1446
0x1800a1440  movzx   ebx, ax
0x1800a1443  or      ebx, r14d
0x1800a1446  test    ebx, ebx
0x1800a1448  js      loc_1800A1598
0x1800a144e  mov     rcx, [rsp+730h+hkey]; hkey
0x1800a1453  lea     eax, [rsi+rsi]
0x1800a1456  mov     [rsp+730h+var_6DC], eax
0x1800a145a  mov     r9d, 2; srrfFlags
0x1800a1460  lea     rax, [rsp+730h+var_6DC]
0x1800a1465  mov     [rsp+730h+pdwType], 1
0x1800a146d  mov     [rsp+730h+pcbData], rax; pcbData
0x1800a1472  xor     r8d, r8d; pszValue
0x1800a1475  lea     rax, [rsp+730h+pdwType]
0x1800a147a  mov     [rsp+730h+pvData], rdi; pvData
0x1800a147f  xor     edx, edx; pszSubKey
0x1800a1481  mov     [rsp+730h+phkResult], rax; pdwType
0x1800a1486  call    cs:__imp_SHRegGetValueW
0x1800a148d  nop     dword ptr [rax+rax+00h]
0x1800a1492  mov     ebx, eax
0x1800a1494  test    eax, eax
0x1800a1496  jle     short loc_1800A149E
0x1800a1498  movzx   ebx, ax
0x1800a149b  or      ebx, r14d
0x1800a149e  test    ebx, ebx
0x1800a14a0  js      loc_1800A1585
0x1800a14a6  test    r15b, 7
0x1800a14aa  jz      loc_1800A1585
0x1800a14b0  mov     rcx, rdi; pszPath
0x1800a14b3  call    cs:__imp_PathFindFileNameW
0x1800a14ba  nop     dword ptr [rax+rax+00h]
0x1800a14bf  mov     rcx, rax; pszStr1
0x1800a14c2  lea     rdx, aMscoreeDll; "mscoree.dll"
0x1800a14c9  call    cs:__imp_StrCmpICW
0x1800a14d0  nop     dword ptr [rax+rax+00h]
0x1800a14d5  test    eax, eax
0x1800a14d7  jnz     loc_1800A1585
0x1800a14dd  mov     rcx, [rsp+730h+hkey]; hkey
0x1800a14e2  lea     rax, [rsp+730h+var_6E8]
0x1800a14e7  mov     [rsp+730h+pcbData], rax; pcbData
0x1800a14ec  lea     r8, aCodebase; "CodeBase"
0x1800a14f3  lea     rax, [rbp+630h+SubKey]
0x1800a14f7  mov     [rsp+730h+var_6E8], 208h
0x1800a14ff  mov     [rsp+730h+pvData], rax; pvData
0x1800a1504  mov     r9d, 2; srrfFlags
0x1800a150a  lea     rax, [rsp+730h+pdwType]
0x1800a150f  xor     edx, edx; pszSubKey
0x1800a1511  mov     [rsp+730h+phkResult], rax; pdwType
0x1800a1516  call    cs:__imp_SHRegGetValueW
0x1800a151d  nop     dword ptr [rax+rax+00h]
0x1800a1522  test    eax, eax
0x1800a1524  jle     short loc_1800A152E
0x1800a1526  movzx   eax, ax
0x1800a1529  or      eax, r14d
0x1800a152c  test    eax, eax
0x1800a152e  js      short loc_1800A1585
0x1800a1530  lea     rcx, [rbp+630h+SubKey]
0x1800a1534  call    GetUrlSchemeW
0x1800a1539  cmp     eax, 9
0x1800a153c  jnz     short loc_1800A1574
0x1800a153e  xor     r9d, r9d; dwFlags
0x1800a1541  mov     [rsp+730h+pcchPath], 104h
0x1800a1549  lea     r8, [rsp+730h+pcchPath]; pcchPath
0x1800a154e  lea     rdx, [rbp+630h+pszPath]; pszPath
0x1800a1555  lea     rcx, [rbp+630h+SubKey]; pszUrl
0x1800a1559  call    cs:__imp_PathCreateFromUrlW
0x1800a1560  nop     dword ptr [rax+rax+00h]
0x1800a1565  mov     ebx, eax
0x1800a1567  test    eax, eax
0x1800a1569  js      short loc_1800A1585
0x1800a156b  lea     r8, [rbp+630h+pszPath]
0x1800a1572  jmp     short loc_1800A1578
0x1800a1574  lea     r8, [rbp+630h+SubKey]; unsigned __int16 *
0x1800a1578  mov     rdx, rsi; unsigned __int64
0x1800a157b  mov     rcx, rdi; unsigned __int16 *
0x1800a157e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a1583  mov     ebx, eax
0x1800a1585  mov     rcx, [rsp+730h+hkey]; hKey
0x1800a158a  call    cs:__imp_RegCloseKey
0x1800a1591  nop     dword ptr [rax+rax+00h]
0x1800a1596  test    ebx, ebx
0x1800a1598  jz      loc_1800A169F
0x1800a159e  cmp     [rsp+730h+sz], r13w
0x1800a15a4  jz      loc_1800A16FC
0x1800a15aa  test    r15b, 6
0x1800a15ae  jz      loc_1800A16FC
0x1800a15b4  lea     rax, aLocalserver32; "LocalServer32"
0x1800a15bb  mov     edx, 104h; unsigned __int64
0x1800a15c0  lea     r9, [rsp+730h+sz]
0x1800a15c5  mov     [rsp+730h+phkResult], rax
0x1800a15ca  lea     r8, aClsidSS; "CLSID\\%s\\%s"
0x1800a15d1  lea     rcx, [rbp+630h+SubKey]; unsigned __int16 *
0x1800a15d5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a15da  mov     ebx, eax
0x1800a15dc  test    eax, eax
0x1800a15de  js      loc_1800A169B
0x1800a15e4  lea     eax, [rsi+rsi]
0x1800a15e7  mov     ecx, 1
0x1800a15ec  mov     [rsp+730h+pcchPath], eax
0x1800a15f0  lea     rdx, [rbp+630h+SubKey]; lpSubKey
0x1800a15f4  mov     [rsp+730h+var_6E8], ecx
0x1800a15f8  test    r15b, 10h
0x1800a15fc  jz      short loc_1800A1616
0x1800a15fe  mov     r9, r12; enum _EXT_ARCHITECTURE *
0x1800a1601  lea     r8, [rsp+730h+hkey]; HKEY *
0x1800a1606  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800a160d  call    ?Ext_GetArchitectureHelper@@YAJPEAUHKEY__@@PEBGPEAPEAU1@PEAW4_EXT_ARCHITECTURE@@@Z; Ext_GetArchitectureHelper(HKEY__ *,ushort const *,HKEY__ * *,_EXT_ARCHITECTURE *)
0x1800a1612  mov     ebx, eax
0x1800a1614  jmp     short loc_1800A1645
0x1800a1616  lea     rax, [rsp+730h+hkey]
0x1800a161b  mov     r9d, ecx; samDesired
0x1800a161e  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800a1625  mov     [rsp+730h+phkResult], rax; phkResult
0x1800a162a  xor     r8d, r8d; ulOptions
0x1800a162d  call    cs:__imp_RegOpenKeyExW
0x1800a1634  nop     dword ptr [rax+rax+00h]
0x1800a1639  mov     ebx, eax
0x1800a163b  test    eax, eax
0x1800a163d  jle     short loc_1800A1645
0x1800a163f  movzx   ebx, ax
0x1800a1642  or      ebx, r14d
0x1800a1645  test    ebx, ebx
0x1800a1647  js      short loc_1800A169D
0x1800a1649  mov     rcx, [rsp+730h+hkey]; hkey
0x1800a164e  lea     rax, [rsp+730h+pcchPath]
0x1800a1653  mov     [rsp+730h+pcbData], rax; pcbData
0x1800a1658  mov     r9d, 2; srrfFlags
0x1800a165e  lea     rax, [rsp+730h+var_6E8]
0x1800a1663  mov     [rsp+730h+pvData], rdi; pvData
0x1800a1668  xor     r8d, r8d; pszValue
0x1800a166b  mov     [rsp+730h+phkResult], rax; pdwType
0x1800a1670  xor     edx, edx; pszSubKey
0x1800a1672  call    cs:__imp_SHRegGetValueW
0x1800a1679  nop     dword ptr [rax+rax+00h]
0x1800a167e  mov     ebx, eax
0x1800a1680  test    eax, eax
0x1800a1682  jle     short loc_1800A168A
0x1800a1684  movzx   ebx, ax
0x1800a1687  or      ebx, r14d
0x1800a168a  mov     rcx, [rsp+730h+hkey]; hKey
0x1800a168f  call    cs:__imp_RegCloseKey
0x1800a1696  nop     dword ptr [rax+rax+00h]
0x1800a169b  test    ebx, ebx
0x1800a169d  jnz     short loc_1800A16FC
0x1800a169f  lea     rax, [rbp+630h+szLongPath]
0x1800a16a6  cmp     rdi, rax
0x1800a16a9  jz      short loc_1800A16FC
0x1800a16ab  mov     rcx, rdi; lpsz
0x1800a16ae  call    cs:__imp_PathUnquoteSpacesW
0x1800a16b5  nop     dword ptr [rax+rax+00h]
0x1800a16ba  mov     r8d, 104h; cchBuffer
0x1800a16c0  lea     rdx, [rbp+630h+szLongPath]; lpszLongPath
0x1800a16c7  mov     rcx, rdi; lpszShortPath
0x1800a16ca  call    cs:__imp_GetLongPathNameW
0x1800a16d1  nop     dword ptr [rax+rax+00h]
0x1800a16d6  lea     r8d, [rax-1]
0x1800a16da  cmp     r8d, 102h
0x1800a16e1  ja      short loc_1800A16FC
0x1800a16e3  mov     eax, eax
0x1800a16e5  cmp     rax, rsi
0x1800a16e8  jnb     short loc_1800A16FC
0x1800a16ea  lea     r8, [rbp+630h+szLongPath]; unsigned __int16 *
0x1800a16f1  mov     rdx, rsi; unsigned __int64
0x1800a16f4  mov     rcx, rdi; unsigned __int16 *
0x1800a16f7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a16fc  mov     eax, ebx
0x1800a16fe  mov     rcx, [rbp+630h+var_40]
0x1800a1705  xor     rcx, rsp; StackCookie
0x1800a1708  call    __security_check_cookie
0x1800a170d  mov     rbx, [rsp+730h+arg_18]
0x1800a1715  add     rsp, 700h
0x1800a171c  pop     r15
0x1800a171e  pop     r14
0x1800a1720  pop     r13
0x1800a1722  pop     r12
0x1800a1724  pop     rdi
0x1800a1725  pop     rsi
0x1800a1726  pop     rbp
0x1800a1727  retn
```
