# Ext_GetModulePath(_GUID const &,ushort *,unsigned __int64,ulong,_EXT_ARCHITECTURE *)

- ea: `0x18009a024`
- end: `0x18009a3ec`
- name: `?Ext_GetModulePath@@YAJAEBU_GUID@@PEAG_KKPEAW4_EXT_ARCHITECTURE@@@Z`
- size: `968`
- prototype: `int(const struct _GUID *, unsigned __int16 *, unsigned __int64, unsigned int, enum _EXT_ARCHITECTURE *)`
- caller_count: `13`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18018f5ec`
- `0x180192bb4`
- `0x1803c31ac`
- `0x1803c332c`
- `0x1803c7a3c`
- `0x1803cfdc0`
- `0x1803cfe50`
- `0x1803d05c0`
- `0x1804e0288`
- `0x1804e0e34`
- `0x1804e11e4`
- `0x1804f0850`
- `0x18054641c`

## callees

- `0x18000c530`
- `0x180011230`
- `0x1800231c4`
- `0x18009a024`
- `0x1804e03e4`
- `0x18054e310`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x18009a1c3`
- `SHLWAPI!__imp_StrCmpICW` at `0x18009a1c3`
- `KERNEL32!GetLongPathNameW` at `0x18009a394`
- `KERNEL32!GetLongPathNameW` at `0x18009a394`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18009a272`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18009a365`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18009a272`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18009a365`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x18009a13a`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x18009a30f`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x18009a13a`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x18009a30f`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathUnquoteSpacesW` at `0x18009a37e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathUnquoteSpacesW` at `0x18009a37e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x18009a1b3`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x18009a1b3`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x18009a247`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x18009a247`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetTreatAsClass` at `0x18009a071`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetTreatAsClass` at `0x18009a071`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x18009a0bf`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x18009a0bf`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x18009a18c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x18009a20a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x18009a34e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x18009a18c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x18009a20a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x18009a34e`

## string_xrefs

- `0x18009a0eb`: `CLSID\%s\%s`
- `0x18009a2ac`: `CLSID\%s\%s`
- `0x18009a1bc`: `mscoree.dll`

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
0x18009a024  mov     [rsp-8+arg_18], rbx
0x18009a029  push    rbp
0x18009a02a  push    rsi
0x18009a02b  push    rdi
0x18009a02c  push    r12
0x18009a02e  push    r13
0x18009a030  push    r14
0x18009a032  push    r15
0x18009a034  lea     rbp, [rsp-600h]
0x18009a03c  sub     rsp, 700h
0x18009a043  mov     rax, cs:__security_cookie
0x18009a04a  xor     rax, rsp
0x18009a04d  mov     [rbp+630h+var_40], rax
0x18009a054  mov     r12, [rbp+630h+arg_20]
0x18009a05b  mov     r14, rdx
0x18009a05e  xorps   xmm0, xmm0
0x18009a061  lea     rdx, [rsp+730h+pClsidNew]; pClsidNew
0x18009a066  movups  xmmword ptr [rsp+730h+pClsidNew.Data1], xmm0
0x18009a06b  mov     r15d, r9d
0x18009a06e  mov     rdi, r8
0x18009a071  call    cs:__imp_CoGetTreatAsClass
0x18009a077  xor     r13d, r13d
0x18009a07a  mov     ebx, eax
0x18009a07c  test    r12, r12
0x18009a07f  jz      short loc_18009A085
0x18009a081  mov     [r12], r13d
0x18009a085  test    r14, r14
0x18009a088  mov     esi, 104h
0x18009a08d  cmovnz  rsi, rdi
0x18009a091  lea     rdi, [rbp+630h+szLongPath]
0x18009a098  cmovnz  rdi, r14
0x18009a09c  test    eax, eax
0x18009a09e  js      loc_18009A3C0
0x18009a0a4  mov     r8d, 27h ; '''; cchMax
0x18009a0aa  mov     [rsp+730h+hkey], r13
0x18009a0af  lea     rdx, [rsp+730h+sz]; lpsz
0x18009a0b4  mov     [rsp+730h+sz], r13w
0x18009a0ba  lea     rcx, [rsp+730h+pClsidNew]; rguid
0x18009a0bf  call    cs:__imp_StringFromGUID2
0x18009a0c5  mov     ebx, eax
0x18009a0c7  mov     r14d, 80070000h
0x18009a0cd  test    eax, eax
0x18009a0cf  js      loc_18009A278
0x18009a0d5  lea     rax, aInprocserver32; "InProcServer32"
0x18009a0dc  mov     edx, 104h; unsigned __int64
0x18009a0e1  lea     r9, [rsp+730h+sz]
0x18009a0e6  mov     [rsp+730h+phkResult], rax
0x18009a0eb  lea     r8, aClsidSS; "CLSID\\%s\\%s"
0x18009a0f2  lea     rcx, [rbp+630h+SubKey]; unsigned __int16 *
0x18009a0f6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009a0fb  mov     ebx, eax
0x18009a0fd  test    eax, eax
0x18009a0ff  js      loc_18009A278
0x18009a105  lea     rdx, [rbp+630h+SubKey]; lpSubKey
0x18009a109  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18009a110  test    r15b, 10h
0x18009a114  jz      short loc_18009A127
0x18009a116  mov     r9, r12; enum _EXT_ARCHITECTURE *
0x18009a119  lea     r8, [rsp+730h+hkey]; HKEY *
0x18009a11e  call    ?Ext_GetArchitectureHelper@@YAJPEAUHKEY__@@PEBGPEAPEAU1@PEAW4_EXT_ARCHITECTURE@@@Z; Ext_GetArchitectureHelper(HKEY__ *,ushort const *,HKEY__ * *,_EXT_ARCHITECTURE *)
0x18009a123  mov     ebx, eax
0x18009a125  jmp     short loc_18009A14C
0x18009a127  lea     rax, [rsp+730h+hkey]
0x18009a12c  mov     r9d, 1; samDesired
0x18009a132  xor     r8d, r8d; ulOptions
0x18009a135  mov     [rsp+730h+phkResult], rax; phkResult
0x18009a13a  call    cs:__imp_RegOpenKeyExW
0x18009a140  mov     ebx, eax
0x18009a142  test    eax, eax
0x18009a144  jle     short loc_18009A14C
0x18009a146  movzx   ebx, ax
0x18009a149  or      ebx, r14d
0x18009a14c  test    ebx, ebx
0x18009a14e  js      loc_18009A27A
0x18009a154  mov     rcx, [rsp+730h+hkey]; hkey
0x18009a159  lea     eax, [rsi+rsi]
0x18009a15c  mov     [rsp+730h+var_6DC], eax
0x18009a160  mov     r9d, 2; srrfFlags
0x18009a166  lea     rax, [rsp+730h+var_6DC]
0x18009a16b  mov     [rsp+730h+pdwType], 1
0x18009a173  mov     [rsp+730h+pcbData], rax; pcbData
0x18009a178  xor     r8d, r8d; pszValue
0x18009a17b  lea     rax, [rsp+730h+pdwType]
0x18009a180  mov     [rsp+730h+pvData], rdi; pvData
0x18009a185  xor     edx, edx; pszSubKey
0x18009a187  mov     [rsp+730h+phkResult], rax; pdwType
0x18009a18c  call    cs:__imp_SHRegGetValueW
0x18009a192  mov     ebx, eax
0x18009a194  test    eax, eax
0x18009a196  jle     short loc_18009A19E
0x18009a198  movzx   ebx, ax
0x18009a19b  or      ebx, r14d
0x18009a19e  test    ebx, ebx
0x18009a1a0  js      loc_18009A26D
0x18009a1a6  test    r15b, 7
0x18009a1aa  jz      loc_18009A26D
0x18009a1b0  mov     rcx, rdi; pszPath
0x18009a1b3  call    cs:__imp_PathFindFileNameW
0x18009a1b9  mov     rcx, rax; pszStr1
0x18009a1bc  lea     rdx, aMscoreeDll; "mscoree.dll"
0x18009a1c3  call    cs:__imp_StrCmpICW
0x18009a1c9  test    eax, eax
0x18009a1cb  jnz     loc_18009A26D
0x18009a1d1  mov     rcx, [rsp+730h+hkey]; hkey
0x18009a1d6  lea     rax, [rsp+730h+var_6E8]
0x18009a1db  mov     [rsp+730h+pcbData], rax; pcbData
0x18009a1e0  lea     r8, aCodebase; "CodeBase"
0x18009a1e7  lea     rax, [rbp+630h+SubKey]
0x18009a1eb  mov     [rsp+730h+var_6E8], 208h
0x18009a1f3  mov     [rsp+730h+pvData], rax; pvData
0x18009a1f8  mov     r9d, 2; srrfFlags
0x18009a1fe  lea     rax, [rsp+730h+pdwType]
0x18009a203  xor     edx, edx; pszSubKey
0x18009a205  mov     [rsp+730h+phkResult], rax; pdwType
0x18009a20a  call    cs:__imp_SHRegGetValueW
0x18009a210  test    eax, eax
0x18009a212  jle     short loc_18009A21C
0x18009a214  movzx   eax, ax
0x18009a217  or      eax, r14d
0x18009a21a  test    eax, eax
0x18009a21c  js      short loc_18009A26D
0x18009a21e  lea     rcx, [rbp+630h+SubKey]
0x18009a222  call    GetUrlSchemeW
0x18009a227  cmp     eax, 9
0x18009a22a  jnz     short loc_18009A25C
0x18009a22c  xor     r9d, r9d; dwFlags
0x18009a22f  mov     [rsp+730h+pcchPath], 104h
0x18009a237  lea     r8, [rsp+730h+pcchPath]; pcchPath
0x18009a23c  lea     rdx, [rbp+630h+pszPath]; pszPath
0x18009a243  lea     rcx, [rbp+630h+SubKey]; pszUrl
0x18009a247  call    cs:__imp_PathCreateFromUrlW
0x18009a24d  mov     ebx, eax
0x18009a24f  test    eax, eax
0x18009a251  js      short loc_18009A26D
0x18009a253  lea     r8, [rbp+630h+pszPath]
0x18009a25a  jmp     short loc_18009A260
0x18009a25c  lea     r8, [rbp+630h+SubKey]; unsigned __int16 *
0x18009a260  mov     rdx, rsi; unsigned __int64
0x18009a263  mov     rcx, rdi; unsigned __int16 *
0x18009a266  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009a26b  mov     ebx, eax
0x18009a26d  mov     rcx, [rsp+730h+hkey]; hKey
0x18009a272  call    cs:__imp_RegCloseKey
0x18009a278  test    ebx, ebx
0x18009a27a  jz      loc_18009A36F
0x18009a280  cmp     [rsp+730h+sz], r13w
0x18009a286  jz      loc_18009A3C0
0x18009a28c  test    r15b, 6
0x18009a290  jz      loc_18009A3C0
0x18009a296  lea     rax, aLocalserver32; "LocalServer32"
0x18009a29d  mov     edx, 104h; unsigned __int64
0x18009a2a2  lea     r9, [rsp+730h+sz]
0x18009a2a7  mov     [rsp+730h+phkResult], rax
0x18009a2ac  lea     r8, aClsidSS; "CLSID\\%s\\%s"
0x18009a2b3  lea     rcx, [rbp+630h+SubKey]; unsigned __int16 *
0x18009a2b7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009a2bc  mov     ebx, eax
0x18009a2be  test    eax, eax
0x18009a2c0  js      loc_18009A36B
0x18009a2c6  lea     eax, [rsi+rsi]
0x18009a2c9  mov     ecx, 1
0x18009a2ce  mov     [rsp+730h+pcchPath], eax
0x18009a2d2  lea     rdx, [rbp+630h+SubKey]; lpSubKey
0x18009a2d6  mov     [rsp+730h+var_6E8], ecx
0x18009a2da  test    r15b, 10h
0x18009a2de  jz      short loc_18009A2F8
0x18009a2e0  mov     r9, r12; enum _EXT_ARCHITECTURE *
0x18009a2e3  lea     r8, [rsp+730h+hkey]; HKEY *
0x18009a2e8  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18009a2ef  call    ?Ext_GetArchitectureHelper@@YAJPEAUHKEY__@@PEBGPEAPEAU1@PEAW4_EXT_ARCHITECTURE@@@Z; Ext_GetArchitectureHelper(HKEY__ *,ushort const *,HKEY__ * *,_EXT_ARCHITECTURE *)
0x18009a2f4  mov     ebx, eax
0x18009a2f6  jmp     short loc_18009A321
0x18009a2f8  lea     rax, [rsp+730h+hkey]
0x18009a2fd  mov     r9d, ecx; samDesired
0x18009a300  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18009a307  mov     [rsp+730h+phkResult], rax; phkResult
0x18009a30c  xor     r8d, r8d; ulOptions
0x18009a30f  call    cs:__imp_RegOpenKeyExW
0x18009a315  mov     ebx, eax
0x18009a317  test    eax, eax
0x18009a319  jle     short loc_18009A321
0x18009a31b  movzx   ebx, ax
0x18009a31e  or      ebx, r14d
0x18009a321  test    ebx, ebx
0x18009a323  js      short loc_18009A36D
0x18009a325  mov     rcx, [rsp+730h+hkey]; hkey
0x18009a32a  lea     rax, [rsp+730h+pcchPath]
0x18009a32f  mov     [rsp+730h+pcbData], rax; pcbData
0x18009a334  mov     r9d, 2; srrfFlags
0x18009a33a  lea     rax, [rsp+730h+var_6E8]
0x18009a33f  mov     [rsp+730h+pvData], rdi; pvData
0x18009a344  xor     r8d, r8d; pszValue
0x18009a347  mov     [rsp+730h+phkResult], rax; pdwType
0x18009a34c  xor     edx, edx; pszSubKey
0x18009a34e  call    cs:__imp_SHRegGetValueW
0x18009a354  mov     ebx, eax
0x18009a356  test    eax, eax
0x18009a358  jle     short loc_18009A360
0x18009a35a  movzx   ebx, ax
0x18009a35d  or      ebx, r14d
0x18009a360  mov     rcx, [rsp+730h+hkey]; hKey
0x18009a365  call    cs:__imp_RegCloseKey
0x18009a36b  test    ebx, ebx
0x18009a36d  jnz     short loc_18009A3C0
0x18009a36f  lea     rax, [rbp+630h+szLongPath]
0x18009a376  cmp     rdi, rax
0x18009a379  jz      short loc_18009A3C0
0x18009a37b  mov     rcx, rdi; lpsz
0x18009a37e  call    cs:__imp_PathUnquoteSpacesW
0x18009a384  mov     r8d, 104h; cchBuffer
0x18009a38a  lea     rdx, [rbp+630h+szLongPath]; lpszLongPath
0x18009a391  mov     rcx, rdi; lpszShortPath
0x18009a394  call    cs:__imp_GetLongPathNameW
0x18009a39a  lea     r8d, [rax-1]
0x18009a39e  cmp     r8d, 102h
0x18009a3a5  ja      short loc_18009A3C0
0x18009a3a7  mov     eax, eax
0x18009a3a9  cmp     rax, rsi
0x18009a3ac  jnb     short loc_18009A3C0
0x18009a3ae  lea     r8, [rbp+630h+szLongPath]; unsigned __int16 *
0x18009a3b5  mov     rdx, rsi; unsigned __int64
0x18009a3b8  mov     rcx, rdi; unsigned __int16 *
0x18009a3bb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009a3c0  mov     eax, ebx
0x18009a3c2  mov     rcx, [rbp+630h+var_40]
0x18009a3c9  xor     rcx, rsp; StackCookie
0x18009a3cc  call    __security_check_cookie
0x18009a3d1  mov     rbx, [rsp+730h+arg_18]
0x18009a3d9  add     rsp, 700h
0x18009a3e0  pop     r15
0x18009a3e2  pop     r14
0x18009a3e4  pop     r13
0x18009a3e6  pop     r12
0x18009a3e8  pop     rdi
0x18009a3e9  pop     rsi
0x18009a3ea  pop     rbp
0x18009a3eb  retn
```
