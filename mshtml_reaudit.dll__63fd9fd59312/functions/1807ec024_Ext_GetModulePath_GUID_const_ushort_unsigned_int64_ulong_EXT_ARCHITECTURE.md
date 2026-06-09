# Ext_GetModulePath(_GUID const &,ushort *,unsigned __int64,ulong,_EXT_ARCHITECTURE *)

- ea: `0x1807ec024`
- end: `0x1807ec3c8`
- name: `?Ext_GetModulePath@@YAJAEBU_GUID@@PEAG_KKPEAW4_EXT_ARCHITECTURE@@@Z`
- size: `932`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned __int16 *, unsigned __int64, unsigned int, enum _EXT_ARCHITECTURE *)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18063a554`
- `0x180873128`
- `0x181065a94`

## callees

- `0x18028ecdc`
- `0x1802e5024`
- `0x1804f89cc`
- `0x1807ec024`
- `0x180839ff9`
- `0x181065340`
- `0x1810c2d60`

## import_xrefs

- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1807ec139`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1807ec302`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1807ec139`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1807ec302`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1807ec26d`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1807ec358`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1807ec26d`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1807ec358`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathUnquoteSpacesW` at `0x1807ec371`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathUnquoteSpacesW` at `0x1807ec371`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1807ec1c1`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1807ec1c1`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x1807ec242`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x1807ec242`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1807ec384`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1807ec384`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x1807ec0b5`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x1807ec0b5`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetTreatAsClass` at `0x1807ec07b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetTreatAsClass` at `0x1807ec07b`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x1807ec18c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x1807ec208`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x1807ec341`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x1807ec18c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x1807ec208`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x1807ec341`

## string_xrefs

- `0x1807ec1b7`: `mscoree.dll`
- `0x1807ec0eb`: `CLSID\%s\%s`
- `0x1807ec2a4`: `CLSID\%s\%s`

## pseudocode

```c
__int64 __fastcall Ext_GetModulePath(const struct _GUID *a1, unsigned __int16 *a2, __int64 a3, char a4)
{
  HRESULT TreatAsClass; // eax
  unsigned __int16 *pvData; // rsi
  int ArchitectureHelper; // edi
  LSTATUS v8; // eax
  bool v9; // zf
  LSTATUS v10; // eax
  const WCHAR *FileNameW_0; // rax
  LSTATUS v12; // eax
  bool v13; // sf
  WCHAR *v14; // r8
  LSTATUS v15; // eax
  bool v16; // zf
  LSTATUS ValueW; // eax
  HKEY hkey; // [rsp+48h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-B8h] BYREF
  DWORD pcchPath; // [rsp+54h] [rbp-B4h] BYREF
  _QWORD pClsidNew[3]; // [rsp+58h] [rbp-B0h] BYREF
  OLECHAR sz[40]; // [rsp+78h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+C8h] [rbp-40h] BYREF
  WCHAR szLongPath[264]; // [rsp+2D8h] [rbp+1D0h] BYREF
  WCHAR v26[264]; // [rsp+4E8h] [rbp+3E0h] BYREF

  *(_OWORD *)&pClsidNew[1] = 0;
  TreatAsClass = CoGetTreatAsClass(a1, (LPCLSID)&pClsidNew[1]);
  pvData = szLongPath;
  ArchitectureHelper = TreatAsClass;
  if ( a2 )
    pvData = a2;
  if ( TreatAsClass >= 0 )
  {
    hkey = 0;
    sz[0] = 0;
    ArchitectureHelper = StringFromGUID2((const GUID *const)&pClsidNew[1], sz, 39);
    if ( ArchitectureHelper < 0 )
      goto LABEL_25;
    ArchitectureHelper = StringCchPrintfW(SubKey, 0x104u, L"CLSID\\%s\\%s", sz, L"InProcServer32");
    if ( ArchitectureHelper < 0 )
      goto LABEL_25;
    if ( (a4 & 0x10) != 0 )
    {
      ArchitectureHelper = Ext_GetArchitectureHelper(HKEY_CLASSES_ROOT, SubKey, &hkey, 0);
    }
    else
    {
      v8 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 1u, &hkey);
      ArchitectureHelper = v8;
      if ( v8 > 0 )
        ArchitectureHelper = (unsigned __int16)v8 | 0x80070000;
    }
    v9 = ArchitectureHelper == 0;
    if ( ArchitectureHelper < 0 )
    {
LABEL_26:
      if ( v9 )
      {
LABEL_40:
        if ( pvData != szLongPath )
        {
          PathUnquoteSpacesW(pvData);
          if ( GetLongPathNameW(pvData, szLongPath, 0x104u) - 1 <= 0x102 )
            StringCchCopyW(pvData, 0x104u, szLongPath);
        }
        return (unsigned int)ArchitectureHelper;
      }
      if ( !sz[0] || (a4 & 6) == 0 )
        return (unsigned int)ArchitectureHelper;
      ArchitectureHelper = StringCchPrintfW(SubKey, 0x104u, L"CLSID\\%s\\%s", sz, L"LocalServer32");
      if ( ArchitectureHelper >= 0 )
      {
        pcchPath = 520;
        pcbData = 1;
        if ( (a4 & 0x10) != 0 )
        {
          ArchitectureHelper = Ext_GetArchitectureHelper(HKEY_CLASSES_ROOT, SubKey, &hkey, 0);
        }
        else
        {
          v15 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 1u, &hkey);
          ArchitectureHelper = v15;
          if ( v15 > 0 )
            ArchitectureHelper = (unsigned __int16)v15 | 0x80070000;
        }
        v16 = ArchitectureHelper == 0;
        if ( ArchitectureHelper < 0 )
        {
LABEL_39:
          if ( !v16 )
            return (unsigned int)ArchitectureHelper;
          goto LABEL_40;
        }
        ValueW = SHRegGetValueW(hkey, 0, 0, 2, &pcbData, pvData, &pcchPath);
        ArchitectureHelper = ValueW;
        if ( ValueW > 0 )
          ArchitectureHelper = (unsigned __int16)ValueW | 0x80070000;
        RegCloseKey(hkey);
      }
      v16 = ArchitectureHelper == 0;
      goto LABEL_39;
    }
    pClsidNew[0] = 0x20800000001LL;
    v10 = SHRegGetValueW(hkey, 0, 0, 2, (DWORD *)pClsidNew, pvData, (DWORD *)pClsidNew + 1);
    ArchitectureHelper = v10;
    if ( v10 > 0 )
      ArchitectureHelper = (unsigned __int16)v10 | 0x80070000;
    if ( ArchitectureHelper >= 0 && (a4 & 7) != 0 )
    {
      FileNameW_0 = PathFindFileNameW_0(pvData);
      if ( !StrCmpICW(FileNameW_0, L"mscoree.dll") )
      {
        pcbData = 520;
        v12 = SHRegGetValueW(hkey, 0, L"CodeBase", 2, (DWORD *)pClsidNew, SubKey, &pcbData);
        v13 = v12 < 0;
        if ( v12 > 0 )
          v13 = 1;
        if ( !v13 )
        {
          if ( (unsigned int)GetUrlSchemeW(SubKey) != 9 )
          {
            v14 = SubKey;
            goto LABEL_23;
          }
          pcchPath = 260;
          ArchitectureHelper = PathCreateFromUrlW(SubKey, v26, &pcchPath, 0);
          if ( ArchitectureHelper >= 0 )
          {
            v14 = v26;
LABEL_23:
            ArchitectureHelper = StringCchCopyW(pvData, 0x104u, v14);
          }
        }
      }
    }
    RegCloseKey(hkey);
LABEL_25:
    v9 = ArchitectureHelper == 0;
    goto LABEL_26;
  }
  return (unsigned int)ArchitectureHelper;
}

```

## disassembly

```asm
0x1807ec024  mov     rax, rsp
0x1807ec027  mov     [rax+20h], r9d
0x1807ec02b  mov     [rax+18h], r8
0x1807ec02f  mov     [rax+10h], rdx
0x1807ec033  mov     [rax+8], rcx
0x1807ec037  push    rbp
0x1807ec038  push    rbx
0x1807ec039  push    rsi
0x1807ec03a  push    rdi
0x1807ec03b  push    r12
0x1807ec03d  push    r14
0x1807ec03f  push    r15
0x1807ec041  lea     rbp, [rax-638h]
0x1807ec048  sub     rsp, 700h
0x1807ec04f  mov     rax, cs:__security_cookie
0x1807ec056  xor     rax, rsp
0x1807ec059  mov     [rbp+630h+var_40], rax
0x1807ec060  mov     rcx, [rbp+630h+clsidOld]; clsidOld
0x1807ec067  lea     rdx, [rsp+730h+pClsidNew+8]; pClsidNew
0x1807ec06c  mov     rbx, [rbp+630h+pszPath]
0x1807ec073  xorps   xmm0, xmm0
0x1807ec076  movups  xmmword ptr [rsp+730h+pClsidNew+8], xmm0
0x1807ec07b  call    cs:__imp_CoGetTreatAsClass
0x1807ec081  xor     r14d, r14d
0x1807ec084  lea     rsi, [rbp+630h+szLongPath]
0x1807ec08b  test    rbx, rbx
0x1807ec08e  mov     edi, eax
0x1807ec090  cmovnz  rsi, rbx
0x1807ec094  test    eax, eax
0x1807ec096  js      loc_1807EC3A5
0x1807ec09c  lea     r8d, [r14+27h]; cchMax
0x1807ec0a0  mov     [rsp+730h+hkey], r14
0x1807ec0a5  lea     rdx, [rsp+730h+sz]; lpsz
0x1807ec0aa  mov     [rsp+730h+sz], r14w
0x1807ec0b0  lea     rcx, [rsp+730h+pClsidNew+8]; rguid
0x1807ec0b5  call    cs:__imp_StringFromGUID2
0x1807ec0bb  mov     ebx, [rbp+630h+arg_18]
0x1807ec0c1  mov     r12d, 80070000h
0x1807ec0c7  mov     edi, eax
0x1807ec0c9  mov     r15d, 104h
0x1807ec0cf  test    eax, eax
0x1807ec0d1  js      loc_1807EC273
0x1807ec0d7  lea     rax, aInprocserver32_0; "InProcServer32"
0x1807ec0de  mov     edx, r15d; unsigned __int64
0x1807ec0e1  lea     r9, [rsp+730h+sz]
0x1807ec0e6  mov     [rsp+730h+phkResult], rax
0x1807ec0eb  lea     r8, aClsidSS; "CLSID\\%s\\%s"
0x1807ec0f2  lea     rcx, [rbp+630h+SubKey]; unsigned __int16 *
0x1807ec0f6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1807ec0fb  mov     edi, eax
0x1807ec0fd  test    eax, eax
0x1807ec0ff  js      loc_1807EC273
0x1807ec105  lea     rdx, [rbp+630h+SubKey]; unsigned __int16 *
0x1807ec109  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x1807ec110  test    bl, 10h
0x1807ec113  jz      short loc_1807EC126
0x1807ec115  xor     r9d, r9d; enum _EXT_ARCHITECTURE *
0x1807ec118  lea     r8, [rsp+730h+hkey]; HKEY *
0x1807ec11d  call    ?Ext_GetArchitectureHelper@@YAJPEAUHKEY__@@PEBGPEAPEAU1@PEAW4_EXT_ARCHITECTURE@@@Z; Ext_GetArchitectureHelper(HKEY__ *,ushort const *,HKEY__ * *,_EXT_ARCHITECTURE *)
0x1807ec122  mov     edi, eax
0x1807ec124  jmp     short loc_1807EC14B
0x1807ec126  lea     rax, [rsp+730h+hkey]
0x1807ec12b  mov     r9d, 1; samDesired
0x1807ec131  xor     r8d, r8d; ulOptions
0x1807ec134  mov     [rsp+730h+phkResult], rax; phkResult
0x1807ec139  call    cs:__imp_RegOpenKeyExW
0x1807ec13f  mov     edi, eax
0x1807ec141  test    eax, eax
0x1807ec143  jle     short loc_1807EC14B
0x1807ec145  movzx   edi, ax
0x1807ec148  or      edi, r12d
0x1807ec14b  test    edi, edi
0x1807ec14d  js      loc_1807EC275
0x1807ec153  mov     rcx, [rsp+730h+hkey]; hkey
0x1807ec158  lea     rax, [rsp+730h+pClsidNew+4]
0x1807ec15d  mov     [rsp+30h], rax; pcbData
0x1807ec162  mov     r9d, 2; srrfFlags
0x1807ec168  lea     rax, [rsp+730h+pClsidNew]
0x1807ec16d  mov     [rsp+730h+pvData], rsi; pvData
0x1807ec172  xor     r8d, r8d; pszValue
0x1807ec175  mov     [rsp+730h+phkResult], rax; pdwType
0x1807ec17a  xor     edx, edx; pszSubKey
0x1807ec17c  mov     dword ptr [rsp+730h+pClsidNew+4], 208h
0x1807ec184  mov     dword ptr [rsp+730h+pClsidNew], 1
0x1807ec18c  call    cs:__imp_SHRegGetValueW
0x1807ec192  mov     edi, eax
0x1807ec194  test    eax, eax
0x1807ec196  jle     short loc_1807EC19E
0x1807ec198  movzx   edi, ax
0x1807ec19b  or      edi, r12d
0x1807ec19e  test    edi, edi
0x1807ec1a0  js      loc_1807EC268
0x1807ec1a6  test    bl, 7
0x1807ec1a9  jz      loc_1807EC268
0x1807ec1af  mov     rcx, rsi; pszPath
0x1807ec1b2  call    PathFindFileNameW_0
0x1807ec1b7  lea     rdx, aMscoreeDll; "mscoree.dll"
0x1807ec1be  mov     rcx, rax; pszStr1
0x1807ec1c1  call    cs:__imp_StrCmpICW
0x1807ec1c7  test    eax, eax
0x1807ec1c9  jnz     loc_1807EC268
0x1807ec1cf  mov     rcx, [rsp+730h+hkey]; hkey
0x1807ec1d4  lea     rax, [rsp+730h+pcbData]
0x1807ec1d9  mov     [rsp+30h], rax; pcbData
0x1807ec1de  lea     r8, aCodebase_0; "CodeBase"
0x1807ec1e5  lea     rax, [rbp+630h+SubKey]
0x1807ec1e9  mov     [rsp+730h+pcbData], 208h
0x1807ec1f1  mov     [rsp+730h+pvData], rax; pvData
0x1807ec1f6  mov     r9d, 2; srrfFlags
0x1807ec1fc  lea     rax, [rsp+730h+pClsidNew]
0x1807ec201  xor     edx, edx; pszSubKey
0x1807ec203  mov     [rsp+730h+phkResult], rax; pdwType
0x1807ec208  call    cs:__imp_SHRegGetValueW
0x1807ec20e  test    eax, eax
0x1807ec210  jle     short loc_1807EC21A
0x1807ec212  movzx   eax, ax
0x1807ec215  or      eax, r12d
0x1807ec218  test    eax, eax
0x1807ec21a  js      short loc_1807EC268
0x1807ec21c  lea     rcx, [rbp+630h+SubKey]
0x1807ec220  call    GetUrlSchemeW
0x1807ec225  cmp     eax, 9
0x1807ec228  jnz     short loc_1807EC257
0x1807ec22a  xor     r9d, r9d; dwFlags
0x1807ec22d  mov     [rsp+730h+pcchPath], r15d
0x1807ec232  lea     r8, [rsp+730h+pcchPath]; pcchPath
0x1807ec237  lea     rdx, [rbp+630h+var_250]; pszPath
0x1807ec23e  lea     rcx, [rbp+630h+SubKey]; pszUrl
0x1807ec242  call    cs:__imp_PathCreateFromUrlW
0x1807ec248  mov     edi, eax
0x1807ec24a  test    eax, eax
0x1807ec24c  js      short loc_1807EC268
0x1807ec24e  lea     r8, [rbp+630h+var_250]
0x1807ec255  jmp     short loc_1807EC25B
0x1807ec257  lea     r8, [rbp+630h+SubKey]; unsigned __int16 *
0x1807ec25b  mov     rdx, r15; unsigned __int64
0x1807ec25e  mov     rcx, rsi; unsigned __int16 *
0x1807ec261  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1807ec266  mov     edi, eax
0x1807ec268  mov     rcx, [rsp+730h+hkey]; hKey
0x1807ec26d  call    cs:__imp_RegCloseKey
0x1807ec273  test    edi, edi
0x1807ec275  jz      loc_1807EC362
0x1807ec27b  cmp     [rsp+730h+sz], r14w
0x1807ec281  jz      loc_1807EC3A5
0x1807ec287  test    bl, 6
0x1807ec28a  jz      loc_1807EC3A5
0x1807ec290  lea     rax, aLocalserver32; "LocalServer32"
0x1807ec297  mov     rdx, r15; unsigned __int64
0x1807ec29a  lea     r9, [rsp+730h+sz]
0x1807ec29f  mov     [rsp+730h+phkResult], rax
0x1807ec2a4  lea     r8, aClsidSS; "CLSID\\%s\\%s"
0x1807ec2ab  lea     rcx, [rbp+630h+SubKey]; unsigned __int16 *
0x1807ec2af  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1807ec2b4  mov     edi, eax
0x1807ec2b6  test    eax, eax
0x1807ec2b8  js      loc_1807EC35E
0x1807ec2be  mov     [rsp+730h+pcchPath], 208h
0x1807ec2c6  lea     rdx, [rbp+630h+SubKey]; unsigned __int16 *
0x1807ec2ca  mov     [rsp+730h+pcbData], 1
0x1807ec2d2  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x1807ec2d9  test    bl, 10h
0x1807ec2dc  jz      short loc_1807EC2EF
0x1807ec2de  xor     r9d, r9d; enum _EXT_ARCHITECTURE *
0x1807ec2e1  lea     r8, [rsp+730h+hkey]; HKEY *
0x1807ec2e6  call    ?Ext_GetArchitectureHelper@@YAJPEAUHKEY__@@PEBGPEAPEAU1@PEAW4_EXT_ARCHITECTURE@@@Z; Ext_GetArchitectureHelper(HKEY__ *,ushort const *,HKEY__ * *,_EXT_ARCHITECTURE *)
0x1807ec2eb  mov     edi, eax
0x1807ec2ed  jmp     short loc_1807EC314
0x1807ec2ef  lea     rax, [rsp+730h+hkey]
0x1807ec2f4  mov     r9d, 1; samDesired
0x1807ec2fa  xor     r8d, r8d; ulOptions
0x1807ec2fd  mov     [rsp+730h+phkResult], rax; phkResult
0x1807ec302  call    cs:__imp_RegOpenKeyExW
0x1807ec308  mov     edi, eax
0x1807ec30a  test    eax, eax
0x1807ec30c  jle     short loc_1807EC314
0x1807ec30e  movzx   edi, ax
0x1807ec311  or      edi, r12d
0x1807ec314  test    edi, edi
0x1807ec316  js      short loc_1807EC360
0x1807ec318  mov     rcx, [rsp+730h+hkey]; hkey
0x1807ec31d  lea     rax, [rsp+730h+pcchPath]
0x1807ec322  mov     [rsp+30h], rax; pcbData
0x1807ec327  mov     r9d, 2; srrfFlags
0x1807ec32d  lea     rax, [rsp+730h+pcbData]
0x1807ec332  mov     [rsp+730h+pvData], rsi; pvData
0x1807ec337  xor     r8d, r8d; pszValue
0x1807ec33a  mov     [rsp+730h+phkResult], rax; pdwType
0x1807ec33f  xor     edx, edx; pszSubKey
0x1807ec341  call    cs:__imp_SHRegGetValueW
0x1807ec347  mov     edi, eax
0x1807ec349  test    eax, eax
0x1807ec34b  jle     short loc_1807EC353
0x1807ec34d  movzx   edi, ax
0x1807ec350  or      edi, r12d
0x1807ec353  mov     rcx, [rsp+730h+hkey]; hKey
0x1807ec358  call    cs:__imp_RegCloseKey
0x1807ec35e  test    edi, edi
0x1807ec360  jnz     short loc_1807EC3A5
0x1807ec362  lea     rax, [rbp+630h+szLongPath]
0x1807ec369  cmp     rsi, rax
0x1807ec36c  jz      short loc_1807EC3A5
0x1807ec36e  mov     rcx, rsi; lpsz
0x1807ec371  call    cs:__imp_PathUnquoteSpacesW
0x1807ec377  mov     r8d, r15d; cchBuffer
0x1807ec37a  lea     rdx, [rbp+630h+szLongPath]; lpszLongPath
0x1807ec381  mov     rcx, rsi; lpszShortPath
0x1807ec384  call    cs:__imp_GetLongPathNameW
0x1807ec38a  dec     eax
0x1807ec38c  cmp     eax, 102h
0x1807ec391  ja      short loc_1807EC3A5
0x1807ec393  lea     r8, [rbp+630h+szLongPath]; unsigned __int16 *
0x1807ec39a  mov     rdx, r15; unsigned __int64
0x1807ec39d  mov     rcx, rsi; unsigned __int16 *
0x1807ec3a0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1807ec3a5  mov     eax, edi
0x1807ec3a7  mov     rcx, [rbp+630h+var_40]
0x1807ec3ae  xor     rcx, rsp; StackCookie
0x1807ec3b1  call    __security_check_cookie
0x1807ec3b6  add     rsp, 700h
0x1807ec3bd  pop     r15
0x1807ec3bf  pop     r14
0x1807ec3c1  pop     r12
0x1807ec3c3  pop     rdi
0x1807ec3c4  pop     rsi
0x1807ec3c5  pop     rbx
0x1807ec3c6  pop     rbp
0x1807ec3c7  retn
```
