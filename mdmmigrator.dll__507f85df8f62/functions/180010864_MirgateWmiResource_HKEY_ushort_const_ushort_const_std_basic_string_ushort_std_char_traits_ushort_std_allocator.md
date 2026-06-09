# MirgateWmiResource(HKEY__ *,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180010864`
- end: `0x180010db9`
- name: `?MirgateWmiResource@@YAJPEAUHKEY__@@PEBG1AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1365`
- prototype: `__int64 __fastcall(HKEY, _WORD *, const WCHAR *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000f5c4`

## callees

- `0x1800022e0`
- `0x1800026b0`
- `0x180002cbc`
- `0x1800034ac`
- `0x1800034f0`
- `0x1800035e6`
- `0x180006c98`
- `0x1800076a4`
- `0x180007720`
- `0x180007ac0`
- `0x180007b38`
- `0x180007f40`
- `0x18000974c`
- `0x18000d9ec`
- `0x18000da88`
- `0x18000de8c`
- `0x18000eae0`
- `0x18000ee18`
- `0x18000f004`
- `0x180010864`
- `0x180010dc0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a94`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010a58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010aa7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010a58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010aa7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800108ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800108fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010921`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010932`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010a50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010a9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010d77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010d88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800108ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800108fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010921`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010932`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010a50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010a9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010d77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010d88`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800108d3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010ad3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800108d3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010ad3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180010979`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180010979`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800109f1`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180010d38`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800109f1`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180010d38`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180010bf3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180010bf3`
- `DMCmnUtils!DmRevertToSelf` at `0x180010a2a`
- `DMCmnUtils!DmRevertToSelf` at `0x180010a2a`

## string_xrefs

- `0x180010a68`: `Software\Microsoft\Windows\EnterpriseResourceManager\AllowedNodePaths\WMI`

## pseudocode

```c
__int64 __fastcall MirgateWmiResource(HKEY a1, _WORD *a2, const WCHAR *a3, unsigned __int16 *a4)
{
  unsigned __int16 *v4; // r14
  _WORD *v5; // r15
  LSTATUS v6; // eax
  int v7; // ebx
  bool v9; // cc
  int WmiKeysFromRegistry; // edi
  DWORD v11; // r12d
  size_t v12; // rbx
  _WORD *v13; // r13
  const struct std::nothrow_t *v14; // rdx
  HKEY v15; // rdi
  DWORD LastError; // ebx
  HKEY v17; // r14
  DWORD v18; // ebx
  LSTATUS v19; // eax
  unsigned __int64 v20; // r8
  size_t v21; // rbx
  void **v22; // r12
  __int64 v23; // rcx
  size_t v24; // r15
  __int64 v25; // rax
  unsigned __int64 v26; // rax
  WCHAR *v27; // r14
  size_t v28; // rbx
  const WCHAR *v29; // rdx
  wchar_t *v30; // rbx
  _QWORD *v31; // rax
  struct IConfigManager2URI *v32; // rcx
  const unsigned __int16 *v33; // rcx
  const unsigned __int16 *v34; // r8
  unsigned __int16 *v35; // rdx
  struct IConfigManager2URI *v36; // rcx
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchValueName; // [rsp+6Ch] [rbp-94h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  DWORD v41; // [rsp+78h] [rbp-88h]
  struct IConfigManager2URI *v42; // [rsp+80h] [rbp-80h] BYREF
  int v43; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v44; // [rsp+90h] [rbp-70h] BYREF
  _WORD *v45; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v46; // [rsp+A0h] [rbp-60h]
  void *v47[2]; // [rsp+A8h] [rbp-58h] BYREF
  _WORD *v48; // [rsp+B8h] [rbp-48h]
  __int128 v49; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v50; // [rsp+D0h] [rbp-30h]
  PCWSTR pszSrch[2]; // [rsp+D8h] [rbp-28h] BYREF
  size_t v52; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v53; // [rsp+F0h] [rbp-10h]
  void *Src[2]; // [rsp+F8h] [rbp-8h] BYREF
  size_t v55; // [rsp+108h] [rbp+8h]
  unsigned __int64 v56; // [rsp+110h] [rbp+10h]
  _BYTE v57[40]; // [rsp+118h] [rbp+18h] BYREF
  WCHAR SubKey[264]; // [rsp+140h] [rbp+40h] BYREF

  v4 = a4;
  v46 = a4;
  v5 = a2;
  v45 = a2;
  hKey = 0;
  cbMaxValueNameLen = 0;
  cchValueName = 0;
  v48 = 0;
  v43 = 0;
  phkResult = 0;
  v6 = RegOpenKeyExW(a1, a3, 0, 0x20019u, &phkResult);
  v7 = v6;
  if ( v6 == 2 )
  {
    if ( phkResult )
      RegCloseKey(phkResult);
    return 0;
  }
  v9 = v6 <= 0;
  if ( v6
    || (v6 = RegQueryInfoKeyW(phkResult, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueNameLen, 0, 0, 0), v7 = v6, v9 = v6 <= 0, v6) )
  {
    if ( !v9 )
      v7 = (unsigned __int16)v6 | 0x80070000;
  }
  else
  {
    WmiKeysFromRegistry = 0;
    v11 = 0;
    v41 = 0;
    v12 = saturated_mul(cbMaxValueNameLen + 1, 2u);
    v13 = operator new[](v12);
    memset_0(v13, 0, v12);
    v48 = v13;
    cchValueName = cbMaxValueNameLen + 1;
    v7 = RegEnumValueW(phkResult, 0, v13, &cchValueName, 0, 0, 0, 0);
    if ( v7 == 259 )
    {
LABEL_64:
      operator delete(v13, v14);
      if ( hKey )
        RegCloseKey(hKey);
      if ( phkResult )
        RegCloseKey(phkResult);
      return (unsigned int)WmiKeysFromRegistry;
    }
    while ( !v7 )
    {
      std::wstring::wstring((__int64)v57, (__int64)v4);
      if ( byte_18002B7D8 )
        DmRevertToSelf();
      byte_18002B7D8 = 0;
      v42 = 0;
      v15 = hKey;
      if ( hKey )
      {
        LastError = GetLastError();
        RegCloseKey(v15);
        SetLastError(LastError);
      }
      hKey = 0;
      WmiKeysFromRegistry = StringCchPrintfW(
                              SubKey,
                              0x104u,
                              L"%s\\%s",
                              L"Software\\Microsoft\\Windows\\EnterpriseResourceManager\\AllowedNodePaths\\WMI",
                              v5);
      if ( WmiKeysFromRegistry >= 0 )
      {
        v17 = hKey;
        if ( hKey )
        {
          v18 = GetLastError();
          RegCloseKey(v17);
          SetLastError(v18);
        }
        hKey = 0;
        v19 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
        if ( v19 )
        {
          if ( v19 > 0 )
            WmiKeysFromRegistry = (unsigned __int16)v19 | 0x80070000;
          else
            WmiKeysFromRegistry = v19;
        }
      }
      if ( WmiKeysFromRegistry >= 0 )
      {
        v49 = 0;
        v50 = 0;
        WmiKeysFromRegistry = GetWmiKeysFromRegistry(hKey, (__int64)&v49);
        if ( WmiKeysFromRegistry >= 0 )
        {
          *(_OWORD *)Src = 0;
          v55 = 0;
          v56 = 0;
          v20 = -1;
          do
            ++v20;
          while ( v5[v20] );
          std::wstring::_Construct<1,unsigned short const *>(Src, v5, v20);
          v21 = v55;
          if ( v55 == 0x7FFFFFFFFFFFFFFELL )
            std::_Xlen_string();
          v22 = Src;
          v23 = 7;
          if ( v56 > 7 )
            v22 = (void **)Src[0];
          *(_OWORD *)pszSrch = 0;
          v52 = 0;
          v53 = 0;
          v24 = v55 + 1;
          v25 = 7;
          if ( v55 + 1 <= 7 )
          {
            v27 = (WCHAR *)pszSrch;
          }
          else
          {
            v26 = v24 | 7;
            if ( (v24 | 7) <= 0x7FFFFFFFFFFFFFFELL )
            {
              v23 = 10;
              if ( v26 < 0xA )
                v26 = 10;
            }
            else
            {
              v26 = 0x7FFFFFFFFFFFFFFELL;
            }
            v44 = v26;
            v27 = (WCHAR *)std::wstring::_Allocate_for_capacity<0>(v23, &v44);
            pszSrch[0] = v27;
            v25 = v44;
          }
          v52 = v21 + 1;
          v53 = v25;
          v28 = v21;
          memcpy_0(v27, v22, v28 * 2);
          v27[v28] = 46;
          v27[v24] = 0;
          v29 = (const WCHAR *)pszSrch;
          if ( v53 > 7 )
            v29 = pszSrch[0];
          v30 = StrStrIW(v13, v29);
          std::wstring::~wstring((char **)pszSrch);
          if ( v30 )
          {
            v47[0] = 0;
            v47[1] = 0;
            v31 = operator new(0x60u);
            *v31 = v31;
            v31[1] = v31;
            v31[2] = v31;
            *((_WORD *)v31 + 12) = 257;
            v47[0] = v31;
            WmiKeysFromRegistry = CreateMapofWmiUri(v30, v47);
            if ( WmiKeysFromRegistry >= 0 )
            {
              v32 = v42;
              if ( v42 )
              {
                v42 = 0;
                (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v32 + 16LL))(v32);
              }
              WmiKeysFromRegistry = CreateWmiPath(v45, (__int64 *)&v49, v47, (__int64)&v42);
              if ( WmiKeysFromRegistry >= 0 )
              {
                WmiKeysFromRegistry = IsWmiResourceProvisioned(v42, &v43);
                if ( WmiKeysFromRegistry >= 0 && !v43 )
                {
                  if ( *((_QWORD *)v46 + 3) <= 7u )
                    v35 = v46;
                  else
                    v35 = *(unsigned __int16 **)v46;
                  WmiKeysFromRegistry = WriteToERMTracked(v33, v35, v34, v42);
                }
              }
            }
            std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v47);
          }
          std::wstring::~wstring((char **)Src);
          v5 = v45;
          v11 = v41;
        }
        std::vector<std::wstring>::~vector<std::wstring>(&v49);
      }
      *v13 = 0;
      cchValueName = cbMaxValueNameLen + 1;
      v41 = ++v11;
      v36 = v42;
      if ( v42 )
      {
        v42 = 0;
        (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v36 + 16LL))(v36);
      }
      ErmRevertImpersonate::~ErmRevertImpersonate((ErmRevertImpersonate *)v57);
      v7 = RegEnumValueW(phkResult, v11, v13, &cchValueName, 0, 0, 0, 0);
      if ( v7 == 259 )
        goto LABEL_64;
      v4 = v46;
    }
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    operator delete(v13, v14);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180010864  push    rbp
0x180010866  push    rbx
0x180010867  push    rsi
0x180010868  push    rdi
0x180010869  push    r12
0x18001086b  push    r13
0x18001086d  push    r14
0x18001086f  push    r15
0x180010871  lea     rbp, [rsp-268h]
0x180010879  sub     rsp, 368h
0x180010880  mov     rax, cs:__security_cookie
0x180010887  xor     rax, rsp
0x18001088a  mov     [rbp+2A0h+var_50], rax
0x180010891  mov     r14, r9
0x180010894  mov     [rbp+2A0h+var_300], r9
0x180010898  mov     rax, r8
0x18001089b  mov     r15, rdx
0x18001089e  mov     [rbp+2A0h+var_308], rdx
0x1800108a2  xor     esi, esi
0x1800108a4  mov     [rsp+3A0h+hKey], rsi
0x1800108a9  mov     [rsp+3A0h+cbMaxValueNameLen], esi
0x1800108ad  mov     [rsp+3A0h+cchValueName], esi
0x1800108b1  mov     [rbp+2A0h+var_2E8], rsi
0x1800108b5  mov     [rbp+2A0h+var_318], esi
0x1800108b8  mov     [rsp+3A0h+var_330], rsi
0x1800108bd  lea     rdx, [rsp+3A0h+var_330]
0x1800108c2  mov     [rsp+3A0h+phkResult], rdx; phkResult
0x1800108c7  mov     r9d, 20019h; samDesired
0x1800108cd  xor     r8d, r8d; ulOptions
0x1800108d0  mov     rdx, rax; lpSubKey
0x1800108d3  call    cs:__imp_RegOpenKeyExW
0x1800108d9  mov     ebx, eax
0x1800108db  cmp     eax, 2
0x1800108de  jnz     short loc_180010908
0x1800108e0  mov     rcx, [rsp+3A0h+hKey]; hKey
0x1800108e5  test    rcx, rcx
0x1800108e8  jz      short loc_1800108F1
0x1800108ea  call    cs:__imp_RegCloseKey
0x1800108f0  nop
0x1800108f1  mov     rcx, [rsp+3A0h+var_330]; hKey
0x1800108f6  test    rcx, rcx
0x1800108f9  jz      short loc_180010901
0x1800108fb  call    cs:__imp_RegCloseKey
0x180010901  xor     eax, eax
0x180010903  jmp     loc_180010D90
0x180010908  test    eax, eax
0x18001090a  jz      short loc_18001093F
0x18001090c  jle     short loc_180010917
0x18001090e  movzx   ebx, ax
0x180010911  or      ebx, 80070000h
0x180010917  mov     rcx, [rsp+3A0h+hKey]; hKey
0x18001091c  test    rcx, rcx
0x18001091f  jz      short loc_180010928
0x180010921  call    cs:__imp_RegCloseKey
0x180010927  nop
0x180010928  mov     rcx, [rsp+3A0h+var_330]; hKey
0x18001092d  test    rcx, rcx
0x180010930  jz      short loc_180010938
0x180010932  call    cs:__imp_RegCloseKey
0x180010938  mov     eax, ebx
0x18001093a  jmp     loc_180010D90
0x18001093f  mov     [rsp+3A0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180010944  mov     [rsp+3A0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x180010949  mov     [rsp+3A0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x18001094e  lea     rax, [rsp+3A0h+cbMaxValueNameLen]
0x180010953  mov     [rsp+3A0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180010958  mov     [rsp+3A0h+lpcValues], rsi; lpcValues
0x18001095d  mov     [rsp+3A0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x180010962  mov     [rsp+3A0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x180010967  mov     [rsp+3A0h+phkResult], rsi; lpcSubKeys
0x18001096c  xor     r9d, r9d; lpReserved
0x18001096f  xor     r8d, r8d; lpcchClass
0x180010972  xor     edx, edx; lpClass
0x180010974  mov     rcx, [rsp+3A0h+var_330]; hKey
0x180010979  call    cs:__imp_RegQueryInfoKeyW
0x18001097f  mov     ebx, eax
0x180010981  test    eax, eax
0x180010983  jnz     short loc_18001090C
0x180010985  mov     edi, esi
0x180010987  mov     r12d, esi
0x18001098a  mov     [rsp+3A0h+var_328], esi
0x18001098e  mov     edx, [rsp+3A0h+cbMaxValueNameLen]
0x180010992  inc     edx
0x180010994  lea     eax, [rbx+2]
0x180010997  mul     rdx
0x18001099a  mov     rbx, rax
0x18001099d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800109a4  cmovb   rbx, rax
0x1800109a8  mov     rcx, rbx; unsigned __int64
0x1800109ab  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800109b0  mov     r13, rax
0x1800109b3  mov     r8, rbx; Size
0x1800109b6  xor     edx, edx; Val
0x1800109b8  mov     rcx, rax; void *
0x1800109bb  call    memset_0
0x1800109c0  mov     [rbp+2A0h+var_2E8], r13
0x1800109c4  mov     ecx, [rsp+3A0h+cbMaxValueNameLen]
0x1800109c8  inc     ecx
0x1800109ca  mov     [rsp+3A0h+cchValueName], ecx
0x1800109ce  mov     [rsp+3A0h+lpcValues], rsi; lpcbData
0x1800109d3  mov     [rsp+3A0h+lpcbMaxClassLen], rsi; lpData
0x1800109d8  mov     [rsp+3A0h+lpcbMaxSubKeyLen], rsi; lpType
0x1800109dd  mov     [rsp+3A0h+phkResult], rsi; lpReserved
0x1800109e2  lea     r9, [rsp+3A0h+cchValueName]; lpcchValueName
0x1800109e7  mov     r8, r13; lpValueName
0x1800109ea  xor     edx, edx; dwIndex
0x1800109ec  mov     rcx, [rsp+3A0h+var_330]; hKey
0x1800109f1  call    cs:__imp_RegEnumValueW
0x1800109f7  mov     ebx, eax
0x1800109f9  cmp     eax, 103h
0x1800109fe  jz      loc_180010D64
0x180010a04  mov     esi, 80070000h
0x180010a09  test    ebx, ebx
0x180010a0b  jnz     loc_180010D50
0x180010a11  mov     rdx, r14
0x180010a14  lea     rcx, [rbp+2A0h+var_288]
0x180010a18  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180010a1d  nop
0x180010a1e  xor     r14d, r14d
0x180010a21  cmp     cs:byte_18002B7D8, r14b
0x180010a28  jz      short loc_180010A30
0x180010a2a  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180010a30  mov     cs:byte_18002B7D8, r14b
0x180010a37  mov     [rbp+2A0h+var_320], r14
0x180010a3b  mov     rdi, [rsp+3A0h+hKey]
0x180010a40  test    rdi, rdi
0x180010a43  jz      short loc_180010A5E
0x180010a45  call    cs:__imp_GetLastError
0x180010a4b  mov     ebx, eax
0x180010a4d  mov     rcx, rdi; hKey
0x180010a50  call    cs:__imp_RegCloseKey
0x180010a56  mov     ecx, ebx; dwErrCode
0x180010a58  call    cs:__imp_SetLastError
0x180010a5e  mov     [rsp+3A0h+hKey], r14
0x180010a63  mov     [rsp+3A0h+phkResult], r15
0x180010a68  lea     r9, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\Enterpris"...
0x180010a6f  lea     r8, aSS; "%s\\%s"
0x180010a76  mov     edx, 104h; unsigned __int64
0x180010a7b  lea     rcx, [rbp+2A0h+SubKey]; unsigned __int16 *
0x180010a7f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010a84  mov     edi, eax
0x180010a86  test    eax, eax
0x180010a88  js      short loc_180010AE8
0x180010a8a  mov     r14, [rsp+3A0h+hKey]
0x180010a8f  test    r14, r14
0x180010a92  jz      short loc_180010AAD
0x180010a94  call    cs:__imp_GetLastError
0x180010a9a  mov     ebx, eax
0x180010a9c  mov     rcx, r14; hKey
0x180010a9f  call    cs:__imp_RegCloseKey
0x180010aa5  mov     ecx, ebx; dwErrCode
0x180010aa7  call    cs:__imp_SetLastError
0x180010aad  xor     r14d, r14d
0x180010ab0  mov     [rsp+3A0h+hKey], r14
0x180010ab5  lea     rax, [rsp+3A0h+hKey]
0x180010aba  mov     [rsp+3A0h+phkResult], rax; phkResult
0x180010abf  mov     r9d, 20019h; samDesired
0x180010ac5  xor     r8d, r8d; ulOptions
0x180010ac8  lea     rdx, [rbp+2A0h+SubKey]; lpSubKey
0x180010acc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010ad3  call    cs:__imp_RegOpenKeyExW
0x180010ad9  test    eax, eax
0x180010adb  jz      short loc_180010AE8
0x180010add  jg      short loc_180010AE3
0x180010adf  mov     edi, eax
0x180010ae1  jmp     short loc_180010AE8
0x180010ae3  movzx   edi, ax
0x180010ae6  or      edi, esi
0x180010ae8  test    edi, edi
0x180010aea  js      loc_180010CDA
0x180010af0  xorps   xmm0, xmm0
0x180010af3  movdqu  [rbp+2A0h+var_2E0], xmm0
0x180010af8  mov     [rbp+2A0h+var_2D0], r14
0x180010afc  lea     rdx, [rbp+2A0h+var_2E0]
0x180010b00  mov     rcx, [rsp+3A0h+hKey]; hkey
0x180010b05  call    ?GetWmiKeysFromRegistry@@YAJPEAUHKEY__@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; GetWmiKeysFromRegistry(HKEY__ *,std::vector<std::wstring> &)
0x180010b0a  mov     edi, eax
0x180010b0c  test    eax, eax
0x180010b0e  js      loc_180010CD1
0x180010b14  xorps   xmm0, xmm0
0x180010b17  movups  xmmword ptr [rbp+2A0h+Src], xmm0
0x180010b1b  mov     [rbp+2A0h+var_298], r14
0x180010b1f  mov     [rbp+2A0h+var_290], r14
0x180010b23  or      r8, 0FFFFFFFFFFFFFFFFh
0x180010b27  inc     r8
0x180010b2a  cmp     [r15+r8*2], r14w
0x180010b2f  jnz     short loc_180010B27
0x180010b31  mov     rdx, r15
0x180010b34  lea     rcx, [rbp+2A0h+Src]
0x180010b38  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180010b3d  nop
0x180010b3e  mov     rbx, [rbp+2A0h+var_298]
0x180010b42  mov     rdx, 7FFFFFFFFFFFFFFEh
0x180010b4c  cmp     rbx, rdx
0x180010b4f  jz      loc_180010DB3
0x180010b55  lea     r12, [rbp+2A0h+Src]
0x180010b59  mov     ecx, 7
0x180010b5e  cmp     [rbp+2A0h+var_290], rcx
0x180010b62  cmova   r12, [rbp+2A0h+Src]
0x180010b67  xorps   xmm0, xmm0
0x180010b6a  movups  xmmword ptr [rbp+2A0h+pszSrch], xmm0
0x180010b6e  mov     [rbp+2A0h+var_2B8], r14
0x180010b72  mov     [rbp+2A0h+var_2B0], r14
0x180010b76  lea     r15, [rbx+1]
0x180010b7a  mov     eax, ecx
0x180010b7c  cmp     r15, rcx
0x180010b7f  jbe     short loc_180010BB7
0x180010b81  mov     rax, r15
0x180010b84  or      rax, rcx
0x180010b87  cmp     rax, rdx
0x180010b8a  jbe     short loc_180010B91
0x180010b8c  mov     rax, rdx
0x180010b8f  jmp     short loc_180010B9D
0x180010b91  mov     ecx, 0Ah
0x180010b96  cmp     rax, rcx
0x180010b99  cmovb   rax, rcx
0x180010b9d  mov     [rbp+2A0h+var_310], rax
0x180010ba1  lea     rdx, [rbp+2A0h+var_310]
0x180010ba5  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x180010baa  mov     r14, rax
0x180010bad  mov     [rbp+2A0h+pszSrch], rax
0x180010bb1  mov     rax, [rbp+2A0h+var_310]
0x180010bb5  jmp     short loc_180010BBB
0x180010bb7  lea     r14, [rbp+2A0h+pszSrch]
0x180010bbb  mov     [rbp+2A0h+var_2B8], r15
0x180010bbf  mov     [rbp+2A0h+var_2B0], rax
0x180010bc3  add     rbx, rbx
0x180010bc6  mov     r8, rbx; Size
0x180010bc9  mov     rdx, r12; Src
0x180010bcc  mov     rcx, r14; void *
0x180010bcf  call    memcpy_0
0x180010bd4  mov     word ptr [r14+rbx], 2Eh ; '.'
0x180010bdb  xor     eax, eax
0x180010bdd  mov     [r14+r15*2], ax
0x180010be2  lea     rdx, [rbp+2A0h+pszSrch]
0x180010be6  cmp     [rbp+2A0h+var_2B0], 7
0x180010beb  cmova   rdx, [rbp+2A0h+pszSrch]; pszSrch
0x180010bf0  mov     rcx, r13; pszFirst
0x180010bf3  call    cs:__imp_StrStrIW
0x180010bf9  mov     rbx, rax
0x180010bfc  lea     rcx, [rbp+2A0h+pszSrch]; void *
0x180010c00  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010c05  xor     r14d, r14d
0x180010c08  test    rbx, rbx
0x180010c0b  jz      loc_180010CBF
0x180010c11  mov     [rbp+2A0h+var_2F8], r14
0x180010c15  mov     [rbp+2A0h+var_2F0], r14
0x180010c19  lea     ecx, [r14+60h]; Size
0x180010c1d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010c22  mov     [rax], rax
0x180010c25  mov     [rax+8], rax
0x180010c29  mov     [rax+10h], rax
0x180010c2d  mov     word ptr [rax+18h], 101h
0x180010c33  mov     [rbp+2A0h+var_2F8], rax
0x180010c37  lea     rdx, [rbp+2A0h+var_2F8]
0x180010c3b  mov     rcx, rbx; Str
0x180010c3e  call    ?CreateMapofWmiUri@@YAJPEBGAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z; CreateMapofWmiUri(ushort const *,std::map<std::wstring,std::wstring> &)
0x180010c43  mov     edi, eax
0x180010c45  test    eax, eax
0x180010c47  js      short loc_180010CB5
0x180010c49  mov     rcx, [rbp+2A0h+var_320]
0x180010c4d  test    rcx, rcx
0x180010c50  jz      short loc_180010C63
0x180010c52  mov     [rbp+2A0h+var_320], r14
0x180010c56  mov     rax, [rcx]
0x180010c59  mov     rax, [rax+10h]
0x180010c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c62  nop
0x180010c63  lea     r9, [rbp+2A0h+var_320]
0x180010c67  lea     r8, [rbp+2A0h+var_2F8]
0x180010c6b  lea     rdx, [rbp+2A0h+var_2E0]
0x180010c6f  mov     rcx, [rbp+2A0h+var_308]
0x180010c73  call    ?CreateWmiPath@@YAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@2@PEAPEAUIConfigManager2URI@@@Z; CreateWmiPath(ushort const *,std::vector<std::wstring> &,std::map<std::wstring,std::wstring> &,IConfigManager2URI * *)
0x180010c78  mov     edi, eax
0x180010c7a  test    eax, eax
0x180010c7c  js      short loc_180010CB5
0x180010c7e  lea     rdx, [rbp+2A0h+var_318]; int *
0x180010c82  mov     rcx, [rbp+2A0h+var_320]; struct IConfigManager2URI *
0x180010c86  call    ?IsWmiResourceProvisioned@@YAJPEAUIConfigManager2URI@@PEAH@Z; IsWmiResourceProvisioned(IConfigManager2URI *,int *)
0x180010c8b  mov     edi, eax
0x180010c8d  test    eax, eax
0x180010c8f  js      short loc_180010CB5
0x180010c91  cmp     [rbp+2A0h+var_318], r14d
0x180010c95  jnz     short loc_180010CB5
0x180010c97  mov     rax, [rbp+2A0h+var_300]
0x180010c9b  cmp     qword ptr [rax+18h], 7
0x180010ca0  jbe     short loc_180010CA7
0x180010ca2  mov     rdx, [rax]
0x180010ca5  jmp     short loc_180010CAA
0x180010ca7  mov     rdx, rax; unsigned __int16 *
0x180010caa  mov     r9, [rbp+2A0h+var_320]; struct IConfigManager2URI *
0x180010cae  call    ?WriteToERMTracked@@YAJPEBG00PEAUIConfigManager2URI@@@Z; WriteToERMTracked(ushort const *,ushort const *,ushort const *,IConfigManager2URI *)
0x180010cb3  mov     edi, eax
0x180010cb5  lea     rcx, [rbp+2A0h+var_2F8]
0x180010cb9  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x180010cbe  nop
0x180010cbf  lea     rcx, [rbp+2A0h+Src]; void *
0x180010cc3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010cc8  mov     r15, [rbp+2A0h+var_308]
0x180010ccc  mov     r12d, [rsp+3A0h+var_328]
  ... truncated ...
```
