# Ext_GetModulePath(_GUID const &,ushort *,unsigned __int64,ulong,_EXT_ARCHITECTURE *)

- ea: `0x1807f8074`
- end: `0x1807f8467`
- name: `?Ext_GetModulePath@@YAJAEBU_GUID@@PEAG_KKPEAW4_EXT_ARCHITECTURE@@@Z`
- size: `1011`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned __int16 *, __int64, char)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180635a10`
- `0x1808796e0`
- `0x181096438`

## callees

- `0x180214b84`
- `0x18040ac58`
- `0x1804e4c1c`
- `0x1807f8074`
- `0x18083cb29`
- `0x181095c30`
- `0x1810f65c0`

## import_xrefs

- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1807f8195`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1807f8382`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1807f8195`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1807f8382`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1807f82e7`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1807f83e4`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1807f82e7`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1807f83e4`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathUnquoteSpacesW` at `0x1807f8403`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathUnquoteSpacesW` at `0x1807f8403`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1807f8229`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1807f8229`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x1807f82b6`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x1807f82b6`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1807f841c`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1807f841c`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x1807f810b`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x1807f810b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetTreatAsClass` at `0x1807f80cb`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetTreatAsClass` at `0x1807f80cb`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x1807f81ee`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x1807f8276`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x1807f83c7`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x1807f81ee`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x1807f8276`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x1807f83c7`

## string_xrefs

- `0x1807f821f`: `mscoree.dll`
- `0x1807f8147`: `CLSID\%s\%s`
- `0x1807f8324`: `CLSID\%s\%s`

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
  unsigned __int16 *v14; // r8
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
0x1807f8074  mov     rax, rsp
0x1807f8077  mov     [rax+20h], r9d
0x1807f807b  mov     [rax+18h], r8
0x1807f807f  mov     [rax+10h], rdx
0x1807f8083  mov     [rax+8], rcx
0x1807f8087  push    rbp
0x1807f8088  push    rbx
0x1807f8089  push    rsi
0x1807f808a  push    rdi
0x1807f808b  push    r12
0x1807f808d  push    r14
0x1807f808f  push    r15
0x1807f8091  lea     rbp, [rax-638h]
0x1807f8098  sub     rsp, 700h
0x1807f809f  mov     rax, cs:__security_cookie
0x1807f80a6  xor     rax, rsp
0x1807f80a9  mov     [rbp+630h+var_40], rax
0x1807f80b0  mov     rcx, [rbp+630h+clsidOld]; clsidOld
0x1807f80b7  lea     rdx, [rsp+730h+pClsidNew+8]; pClsidNew
0x1807f80bc  mov     rbx, [rbp+630h+pszPath]
0x1807f80c3  xorps   xmm0, xmm0
0x1807f80c6  movups  xmmword ptr [rsp+730h+pClsidNew+8], xmm0
0x1807f80cb  call    cs:__imp_CoGetTreatAsClass
0x1807f80d2  nop     dword ptr [rax+rax+00h]
0x1807f80d7  xor     r14d, r14d
0x1807f80da  lea     rsi, [rbp+630h+szLongPath]
0x1807f80e1  test    rbx, rbx
0x1807f80e4  mov     edi, eax
0x1807f80e6  cmovnz  rsi, rbx
0x1807f80ea  test    eax, eax
0x1807f80ec  js      loc_1807F8443
0x1807f80f2  lea     r8d, [r14+27h]; cchMax
0x1807f80f6  mov     [rsp+730h+hkey], r14
0x1807f80fb  lea     rdx, [rsp+730h+sz]; lpsz
0x1807f8100  mov     [rsp+730h+sz], r14w
0x1807f8106  lea     rcx, [rsp+730h+pClsidNew+8]; rguid
0x1807f810b  call    cs:__imp_StringFromGUID2
0x1807f8112  nop     dword ptr [rax+rax+00h]
0x1807f8117  mov     ebx, [rbp+630h+arg_18]
0x1807f811d  mov     r12d, 80070000h
0x1807f8123  mov     edi, eax
0x1807f8125  mov     r15d, 104h
0x1807f812b  test    eax, eax
0x1807f812d  js      loc_1807F82F3
0x1807f8133  lea     rax, aInprocserver32_0; "InProcServer32"
0x1807f813a  mov     edx, r15d; unsigned __int64
0x1807f813d  lea     r9, [rsp+730h+sz]
0x1807f8142  mov     [rsp+730h+phkResult], rax
0x1807f8147  lea     r8, aClsidSS; "CLSID\\%s\\%s"
0x1807f814e  lea     rcx, [rbp+630h+SubKey]; unsigned __int16 *
0x1807f8152  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1807f8157  mov     edi, eax
0x1807f8159  test    eax, eax
0x1807f815b  js      loc_1807F82F3
0x1807f8161  lea     rdx, [rbp+630h+SubKey]; unsigned __int16 *
0x1807f8165  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x1807f816c  test    bl, 10h
0x1807f816f  jz      short loc_1807F8182
0x1807f8171  xor     r9d, r9d; enum _EXT_ARCHITECTURE *
0x1807f8174  lea     r8, [rsp+730h+hkey]; HKEY *
0x1807f8179  call    ?Ext_GetArchitectureHelper@@YAJPEAUHKEY__@@PEBGPEAPEAU1@PEAW4_EXT_ARCHITECTURE@@@Z; Ext_GetArchitectureHelper(HKEY__ *,ushort const *,HKEY__ * *,_EXT_ARCHITECTURE *)
0x1807f817e  mov     edi, eax
0x1807f8180  jmp     short loc_1807F81AD
0x1807f8182  lea     rax, [rsp+730h+hkey]
0x1807f8187  mov     r9d, 1; samDesired
0x1807f818d  xor     r8d, r8d; ulOptions
0x1807f8190  mov     [rsp+730h+phkResult], rax; phkResult
0x1807f8195  call    cs:__imp_RegOpenKeyExW
0x1807f819c  nop     dword ptr [rax+rax+00h]
0x1807f81a1  mov     edi, eax
0x1807f81a3  test    eax, eax
0x1807f81a5  jle     short loc_1807F81AD
0x1807f81a7  movzx   edi, ax
0x1807f81aa  or      edi, r12d
0x1807f81ad  test    edi, edi
0x1807f81af  js      loc_1807F82F5
0x1807f81b5  mov     rcx, [rsp+730h+hkey]; hkey
0x1807f81ba  lea     rax, [rsp+730h+pClsidNew+4]
0x1807f81bf  mov     [rsp+30h], rax; pcbData
0x1807f81c4  mov     r9d, 2; srrfFlags
0x1807f81ca  lea     rax, [rsp+730h+pClsidNew]
0x1807f81cf  mov     [rsp+730h+pvData], rsi; pvData
0x1807f81d4  xor     r8d, r8d; pszValue
0x1807f81d7  mov     [rsp+730h+phkResult], rax; pdwType
0x1807f81dc  xor     edx, edx; pszSubKey
0x1807f81de  mov     dword ptr [rsp+730h+pClsidNew+4], 208h
0x1807f81e6  mov     dword ptr [rsp+730h+pClsidNew], 1
0x1807f81ee  call    cs:__imp_SHRegGetValueW
0x1807f81f5  nop     dword ptr [rax+rax+00h]
0x1807f81fa  mov     edi, eax
0x1807f81fc  test    eax, eax
0x1807f81fe  jle     short loc_1807F8206
0x1807f8200  movzx   edi, ax
0x1807f8203  or      edi, r12d
0x1807f8206  test    edi, edi
0x1807f8208  js      loc_1807F82E2
0x1807f820e  test    bl, 7
0x1807f8211  jz      loc_1807F82E2
0x1807f8217  mov     rcx, rsi; pszPath
0x1807f821a  call    PathFindFileNameW_0
0x1807f821f  lea     rdx, aMscoreeDll; "mscoree.dll"
0x1807f8226  mov     rcx, rax; pszStr1
0x1807f8229  call    cs:__imp_StrCmpICW
0x1807f8230  nop     dword ptr [rax+rax+00h]
0x1807f8235  test    eax, eax
0x1807f8237  jnz     loc_1807F82E2
0x1807f823d  mov     rcx, [rsp+730h+hkey]; hkey
0x1807f8242  lea     rax, [rsp+730h+pcbData]
0x1807f8247  mov     [rsp+30h], rax; pcbData
0x1807f824c  lea     r8, aCodebase_0; "CodeBase"
0x1807f8253  lea     rax, [rbp+630h+SubKey]
0x1807f8257  mov     [rsp+730h+pcbData], 208h
0x1807f825f  mov     [rsp+730h+pvData], rax; pvData
0x1807f8264  mov     r9d, 2; srrfFlags
0x1807f826a  lea     rax, [rsp+730h+pClsidNew]
0x1807f826f  xor     edx, edx; pszSubKey
0x1807f8271  mov     [rsp+730h+phkResult], rax; pdwType
0x1807f8276  call    cs:__imp_SHRegGetValueW
0x1807f827d  nop     dword ptr [rax+rax+00h]
0x1807f8282  test    eax, eax
0x1807f8284  jle     short loc_1807F828E
0x1807f8286  movzx   eax, ax
0x1807f8289  or      eax, r12d
0x1807f828c  test    eax, eax
0x1807f828e  js      short loc_1807F82E2
0x1807f8290  lea     rcx, [rbp+630h+SubKey]
0x1807f8294  call    GetUrlSchemeW
0x1807f8299  cmp     eax, 9
0x1807f829c  jnz     short loc_1807F82D1
0x1807f829e  xor     r9d, r9d; dwFlags
0x1807f82a1  mov     [rsp+730h+pcchPath], r15d
0x1807f82a6  lea     r8, [rsp+730h+pcchPath]; pcchPath
0x1807f82ab  lea     rdx, [rbp+630h+var_250]; pszPath
0x1807f82b2  lea     rcx, [rbp+630h+SubKey]; pszUrl
0x1807f82b6  call    cs:__imp_PathCreateFromUrlW
0x1807f82bd  nop     dword ptr [rax+rax+00h]
0x1807f82c2  mov     edi, eax
0x1807f82c4  test    eax, eax
0x1807f82c6  js      short loc_1807F82E2
0x1807f82c8  lea     r8, [rbp+630h+var_250]
0x1807f82cf  jmp     short loc_1807F82D5
0x1807f82d1  lea     r8, [rbp+630h+SubKey]; unsigned __int16 *
0x1807f82d5  mov     rdx, r15; unsigned __int64
0x1807f82d8  mov     rcx, rsi; unsigned __int16 *
0x1807f82db  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1807f82e0  mov     edi, eax
0x1807f82e2  mov     rcx, [rsp+730h+hkey]; hKey
0x1807f82e7  call    cs:__imp_RegCloseKey
0x1807f82ee  nop     dword ptr [rax+rax+00h]
0x1807f82f3  test    edi, edi
0x1807f82f5  jz      loc_1807F83F4
0x1807f82fb  cmp     [rsp+730h+sz], r14w
0x1807f8301  jz      loc_1807F8443
0x1807f8307  test    bl, 6
0x1807f830a  jz      loc_1807F8443
0x1807f8310  lea     rax, aLocalserver32; "LocalServer32"
0x1807f8317  mov     rdx, r15; unsigned __int64
0x1807f831a  lea     r9, [rsp+730h+sz]
0x1807f831f  mov     [rsp+730h+phkResult], rax
0x1807f8324  lea     r8, aClsidSS; "CLSID\\%s\\%s"
0x1807f832b  lea     rcx, [rbp+630h+SubKey]; unsigned __int16 *
0x1807f832f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1807f8334  mov     edi, eax
0x1807f8336  test    eax, eax
0x1807f8338  js      loc_1807F83F0
0x1807f833e  mov     [rsp+730h+pcchPath], 208h
0x1807f8346  lea     rdx, [rbp+630h+SubKey]; unsigned __int16 *
0x1807f834a  mov     [rsp+730h+pcbData], 1
0x1807f8352  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x1807f8359  test    bl, 10h
0x1807f835c  jz      short loc_1807F836F
0x1807f835e  xor     r9d, r9d; enum _EXT_ARCHITECTURE *
0x1807f8361  lea     r8, [rsp+730h+hkey]; HKEY *
0x1807f8366  call    ?Ext_GetArchitectureHelper@@YAJPEAUHKEY__@@PEBGPEAPEAU1@PEAW4_EXT_ARCHITECTURE@@@Z; Ext_GetArchitectureHelper(HKEY__ *,ushort const *,HKEY__ * *,_EXT_ARCHITECTURE *)
0x1807f836b  mov     edi, eax
0x1807f836d  jmp     short loc_1807F839A
0x1807f836f  lea     rax, [rsp+730h+hkey]
0x1807f8374  mov     r9d, 1; samDesired
0x1807f837a  xor     r8d, r8d; ulOptions
0x1807f837d  mov     [rsp+730h+phkResult], rax; phkResult
0x1807f8382  call    cs:__imp_RegOpenKeyExW
0x1807f8389  nop     dword ptr [rax+rax+00h]
0x1807f838e  mov     edi, eax
0x1807f8390  test    eax, eax
0x1807f8392  jle     short loc_1807F839A
0x1807f8394  movzx   edi, ax
0x1807f8397  or      edi, r12d
0x1807f839a  test    edi, edi
0x1807f839c  js      short loc_1807F83F2
0x1807f839e  mov     rcx, [rsp+730h+hkey]; hkey
0x1807f83a3  lea     rax, [rsp+730h+pcchPath]
0x1807f83a8  mov     [rsp+30h], rax; pcbData
0x1807f83ad  mov     r9d, 2; srrfFlags
0x1807f83b3  lea     rax, [rsp+730h+pcbData]
0x1807f83b8  mov     [rsp+730h+pvData], rsi; pvData
0x1807f83bd  xor     r8d, r8d; pszValue
0x1807f83c0  mov     [rsp+730h+phkResult], rax; pdwType
0x1807f83c5  xor     edx, edx; pszSubKey
0x1807f83c7  call    cs:__imp_SHRegGetValueW
0x1807f83ce  nop     dword ptr [rax+rax+00h]
0x1807f83d3  mov     edi, eax
0x1807f83d5  test    eax, eax
0x1807f83d7  jle     short loc_1807F83DF
0x1807f83d9  movzx   edi, ax
0x1807f83dc  or      edi, r12d
0x1807f83df  mov     rcx, [rsp+730h+hkey]; hKey
0x1807f83e4  call    cs:__imp_RegCloseKey
0x1807f83eb  nop     dword ptr [rax+rax+00h]
0x1807f83f0  test    edi, edi
0x1807f83f2  jnz     short loc_1807F8443
0x1807f83f4  lea     rax, [rbp+630h+szLongPath]
0x1807f83fb  cmp     rsi, rax
0x1807f83fe  jz      short loc_1807F8443
0x1807f8400  mov     rcx, rsi; lpsz
0x1807f8403  call    cs:__imp_PathUnquoteSpacesW
0x1807f840a  nop     dword ptr [rax+rax+00h]
0x1807f840f  mov     r8d, r15d; cchBuffer
0x1807f8412  lea     rdx, [rbp+630h+szLongPath]; lpszLongPath
0x1807f8419  mov     rcx, rsi; lpszShortPath
0x1807f841c  call    cs:__imp_GetLongPathNameW
0x1807f8423  nop     dword ptr [rax+rax+00h]
0x1807f8428  dec     eax
0x1807f842a  cmp     eax, 102h
0x1807f842f  ja      short loc_1807F8443
0x1807f8431  lea     r8, [rbp+630h+szLongPath]; unsigned __int16 *
0x1807f8438  mov     rdx, r15; unsigned __int64
0x1807f843b  mov     rcx, rsi; unsigned __int16 *
0x1807f843e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1807f8443  mov     eax, edi
0x1807f8445  mov     rcx, [rbp+630h+var_40]
0x1807f844c  xor     rcx, rsp; StackCookie
0x1807f844f  call    __security_check_cookie
0x1807f8454  add     rsp, 700h
0x1807f845b  pop     r15
0x1807f845d  pop     r14
0x1807f845f  pop     r12
0x1807f8461  pop     rdi
0x1807f8462  pop     rsi
0x1807f8463  pop     rbx
0x1807f8464  pop     rbp
0x1807f8465  retn
```
