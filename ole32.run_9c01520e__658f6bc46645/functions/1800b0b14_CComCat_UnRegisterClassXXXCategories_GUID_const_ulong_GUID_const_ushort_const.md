# CComCat::UnRegisterClassXXXCategories(_GUID const &,ulong,_GUID * const,ushort const *)

- ea: `0x1800b0b14`
- end: `0x1800b0e11`
- name: `?UnRegisterClassXXXCategories@CComCat@@AEAAJAEBU_GUID@@KQEAU2@PEBG@Z`
- size: `765`
- prototype: `HRESULT __fastcall(CComCat *this, const _GUID *rclsid, unsigned int cCategories, _GUID *rgcatid, const wchar_t *szImplReq)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800b0ac0`
- `0x1800b0af0`

## callees

- `0x18000f660`
- `0x180010fac`
- `0x18001d110`
- `0x180046460`
- `0x180046de0`
- `0x1800b0210`
- `0x1800b0b14`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800b0cd3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800b0cd3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b0c0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b0c0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b0dc3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b0dc3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800b0d34`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800b0d9a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800b0d34`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800b0d9a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b0ba6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b0ced`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b0ba6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b0ced`

## pseudocode

```c
HRESULT __fastcall CComCat::UnRegisterClassXXXCategories(
        CComCat *this,
        const _GUID *rclsid,
        unsigned int cCategories,
        _GUID *rgcatid,
        const wchar_t *szImplReq)
{
  __int64 v5; // r14
  const void *v7; // r10
  HRESULT result; // eax
  const GUID *v9; // r10
  LSTATUS v10; // eax
  int v11; // ebx
  unsigned int i; // edi
  int v13; // ecx
  __int64 v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // rax
  int cbMultiByte; // edx
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rcx
  void *v20; // rsp
  void *v21; // rsp
  int usedDefaultChar; // [rsp+40h] [rbp+0h] BYREF
  HKEY__ *hkCatKey; // [rsp+48h] [rbp+8h] BYREF
  wchar_t wszclsid[40]; // [rsp+50h] [rbp+10h] BYREF
  wchar_t wszguid[40]; // [rsp+A0h] [rbp+60h] BYREF
  wchar_t szCatKey[264]; // [rsp+F0h] [rbp+B0h] BYREF

  v5 = cCategories;
  if ( !IsValidPtrOut(this, 0x68u) )
    return -2147467261;
  if ( !IsValidReadPtrIn(v7, 0x10u) || !IsValidReadPtrIn(rgcatid, 16 * v5) )
    return -2147024809;
  hkCatKey = 0;
  if ( StringFromGUID2(v9, wszclsid, 40) )
  {
    result = StringCchPrintfW(szCatKey, 0x104u, L"%s\\%s\\%s", Com::Catalog::Constants::CLSID, wszclsid, szImplReq);
    if ( result < 0 )
      return result;
    v10 = RegOpenKeyExW(HKEY_CLASSES_ROOT, szCatKey, 0, 0xF003Fu, &hkCatKey);
    v11 = v10;
    if ( v10 )
    {
      if ( v10 <= 0 )
        return v11;
      v11 = (unsigned __int16)v10;
    }
    else
    {
      for ( i = 0; i < (unsigned int)v5; ++i )
      {
        v13 = 0;
        v14 = i;
        while ( v13 < 5 )
        {
          v15 = v13;
          v14 = i;
          v16 = *(_QWORD *)&rgcatid[v14].Data1 - *(_QWORD *)&g_oldkeyinfo[v15].catid.Data1;
          if ( !v16 )
            v16 = *(_QWORD *)rgcatid[v14].Data4 - *(_QWORD *)g_oldkeyinfo[v15].catid.Data4;
          if ( !v16 )
          {
            if ( StringCchPrintfW(
                   szCatKey,
                   0x104u,
                   L"%s\\%s\\%s",
                   Com::Catalog::Constants::CLSID,
                   wszclsid,
                   g_oldkeyinfo[v15].szDescription) >= 0 )
              RegDeleteKeyExW(HKEY_CLASSES_ROOT, szCatKey, 0, 0);
            break;
          }
          ++v13;
        }
        if ( !StringFromGUID2(&rgcatid[v14], wszguid, 40) )
          return -2147024882;
        usedDefaultChar = 0;
        cbMultiByte = WideCharToMultiByte(0, 0x400u, wszguid, -1, 0, 0, "?", &usedDefaultChar) + 1;
        v18 = cbMultiByte + 15LL;
        if ( v18 <= cbMultiByte )
          v18 = 0xFFFFFFFFFFFFFF0LL;
        v19 = v18 & 0xFFFFFFFFFFFFFFF0uLL;
        v20 = alloca(v19);
        v21 = alloca(v19);
        WideCharToMultiByte(0, 0x400u, wszguid, -1, (LPSTR)&usedDefaultChar, cbMultiByte, "?", &usedDefaultChar);
        v11 = RecursiveRegDeleteKey(hkCatKey, (char *)&usedDefaultChar);
        if ( v11 )
          break;
      }
      RegCloseKey(hkCatKey);
      if ( v11 <= 0 )
        return v11;
      v11 = (unsigned __int16)v11;
    }
    return v11 | 0x80070000;
  }
  return -2147024882;
}

```

## disassembly

```asm
0x1800b0b14  push    rbp
0x1800b0b16  push    rsi
0x1800b0b17  push    rdi
0x1800b0b18  push    r13
0x1800b0b1a  push    r14
0x1800b0b1c  sub     rsp, 310h
0x1800b0b23  lea     rbp, [rsp+40h]
0x1800b0b28  mov     [rbp+2F0h+arg_0], rbx
0x1800b0b2f  mov     rax, cs:__security_cookie
0x1800b0b36  xor     rax, rbp
0x1800b0b39  mov     [rbp+2F0h+var_30], rax
0x1800b0b40  mov     rbx, [rbp+2F0h+szImplReq]
0x1800b0b47  mov     r10, rclsid
0x1800b0b4a  mov     edx, 68h ; 'h'; cb
0x1800b0b4f  mov     r14d, cCategories
0x1800b0b52  mov     rsi, rgcatid
0x1800b0b55  call    ?IsValidPtrOut@@YAHPEAX_K@Z; IsValidPtrOut(void *,unsigned __int64)
0x1800b0b5a  test    eax, eax
0x1800b0b5c  jnz     short loc_1800B0B68
0x1800b0b5e  mov     eax, 80004003h
0x1800b0b63  jmp     loc_1800B0DEB
0x1800b0b68  mov     edx, 10h; cb
0x1800b0b6d  mov     this, r10; pv
0x1800b0b70  call    ?IsValidReadPtrIn@@YAHPEBX_K@Z; IsValidReadPtrIn(void const *,unsigned __int64)
0x1800b0b75  test    eax, eax
0x1800b0b77  jz      loc_1800B0DE6
0x1800b0b7d  mov     rclsid, r14
0x1800b0b80  mov     this, rsi; pv
0x1800b0b83  shl     rclsid, 4; cb
0x1800b0b87  call    ?IsValidReadPtrIn@@YAHPEBX_K@Z; IsValidReadPtrIn(void const *,unsigned __int64)
0x1800b0b8c  test    eax, eax
0x1800b0b8e  jz      loc_1800B0DE6
0x1800b0b94  and     [rbp+2F0h+hkCatKey], 0
0x1800b0b99  lea     rclsid, [rbp+2F0h+wszclsid]; lpsz
0x1800b0b9d  mov     cCategories, 28h ; '('; cchMax
0x1800b0ba3  mov     this, r10; rguid
0x1800b0ba6  call    cs:__imp_StringFromGUID2
0x1800b0bad  nop     dword ptr [rax+rax+00h]
0x1800b0bb2  test    eax, eax
0x1800b0bb4  jz      loc_1800B0DDF
0x1800b0bba  lea     rax, [rbp+2F0h+wszclsid]
0x1800b0bbe  mov     qword ptr [rsp+330h+cbMultiByte], rbx
0x1800b0bc3  lea     rgcatid, ?CLSID@Constants@Catalog@Com@@3QBGB; ushort const near * const Com::Catalog::Constants::CLSID
0x1800b0bca  mov     [rsp+330h+phkResult], rax
0x1800b0bcf  lea     r8, aSSS; "%s\\%s\\%s"
0x1800b0bd6  mov     edx, 104h; cchDest
0x1800b0bdb  lea     this, [rbp+2F0h+szCatKey]; pszDest
0x1800b0be2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b0be7  test    eax, eax
0x1800b0be9  js      loc_1800B0DEB
0x1800b0bef  lea     rax, [rbp+2F0h+hkCatKey]
0x1800b0bf3  mov     r9d, 0F003Fh; samDesired
0x1800b0bf9  xor     cCategories, cCategories; ulOptions
0x1800b0bfc  mov     [rsp+330h+phkResult], rax; phkResult
0x1800b0c01  lea     rclsid, [rbp+2F0h+szCatKey]; lpSubKey
0x1800b0c08  mov     this, 0FFFFFFFF80000000h; hKey
0x1800b0c0f  call    cs:__imp_RegOpenKeyExW
0x1800b0c16  nop     dword ptr [rax+rax+00h]
0x1800b0c1b  mov     ebx, eax
0x1800b0c1d  test    eax, eax
0x1800b0c1f  jz      short loc_1800B0C33
0x1800b0c21  jle     short loc_1800B0C2C
0x1800b0c23  movzx   ebx, ax
0x1800b0c26  or      ebx, 80070000h
0x1800b0c2c  mov     eax, ebx
0x1800b0c2e  jmp     loc_1800B0DEB
0x1800b0c33  xor     edi, edi
0x1800b0c35  lea     r13, g_oldkeyinfo
0x1800b0c3c  cmp     edi, r14d
0x1800b0c3f  jnb     loc_1800B0DBF
0x1800b0c45  xor     ecx, ecx
0x1800b0c47  mov     ebx, edi
0x1800b0c49  shl     rbx, 4
0x1800b0c4d  mov     cCategories, edi
0x1800b0c50  cmp     ecx, 5
0x1800b0c53  jge     loc_1800B0CDF
0x1800b0c59  movsxd  rax, ecx
0x1800b0c5c  mov     rbx, r8
0x1800b0c5f  imul    rclsid, rax, 114h
0x1800b0c66  shl     rbx, 4
0x1800b0c6a  mov     rax, [rbx+rsi]
0x1800b0c6e  sub     rax, [rclsid+r13]
0x1800b0c72  jnz     short loc_1800B0C7E
0x1800b0c74  mov     rax, [rbx+rsi+8]
0x1800b0c79  sub     rax, [rclsid+r13+8]
0x1800b0c7e  test    rax, rax
0x1800b0c81  jz      short loc_1800B0C87
0x1800b0c83  inc     ecx
0x1800b0c85  jmp     short loc_1800B0C50
0x1800b0c87  lea     rax, [r13+14h]
0x1800b0c8b  add     rax, rclsid
0x1800b0c8e  lea     rgcatid, ?CLSID@Constants@Catalog@Com@@3QBGB; ushort const near * const Com::Catalog::Constants::CLSID
0x1800b0c95  mov     qword ptr [rsp+330h+cbMultiByte], rax; cbMultiByte
0x1800b0c9a  lea     r8, aSSS; "%s\\%s\\%s"
0x1800b0ca1  lea     rax, [rbp+2F0h+wszclsid]
0x1800b0ca5  mov     edx, 104h; cchDest
0x1800b0caa  lea     this, [rbp+2F0h+szCatKey]; pszDest
0x1800b0cb1  mov     [rsp+330h+phkResult], rax; lpMultiByteStr
0x1800b0cb6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b0cbb  test    eax, eax
0x1800b0cbd  js      short loc_1800B0CDF
0x1800b0cbf  xor     r9d, r9d; Reserved
0x1800b0cc2  lea     rclsid, [rbp+2F0h+szCatKey]; lpSubKey
0x1800b0cc9  xor     cCategories, cCategories; samDesired
0x1800b0ccc  mov     this, 0FFFFFFFF80000000h; hKey
0x1800b0cd3  call    cs:__imp_RegDeleteKeyExW
0x1800b0cda  nop     dword ptr [rax+rax+00h]
0x1800b0cdf  lea     this, [rbx+rsi]; rguid
0x1800b0ce3  mov     cCategories, 28h ; '('; cchMax
0x1800b0ce9  lea     rclsid, [rbp+2F0h+wszguid]; lpsz
0x1800b0ced  call    cs:__imp_StringFromGUID2
0x1800b0cf4  nop     dword ptr [rax+rax+00h]
0x1800b0cf9  test    eax, eax
0x1800b0cfb  jz      loc_1800B0DDF
0x1800b0d01  and     [rbp+2F0h+usedDefaultChar], 0
0x1800b0d05  lea     rax, [rbp+2F0h+usedDefaultChar]
0x1800b0d09  mov     [rsp+330h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x1800b0d0e  lea     r8, [rbp+2F0h+wszguid]; lpWideCharStr
0x1800b0d12  lea     rax, DefaultChar; "?"
0x1800b0d19  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800b0d1d  mov     [rsp+330h+lpDefaultChar], rax; lpDefaultChar
0x1800b0d22  mov     edx, 400h; dwFlags
0x1800b0d27  and     [rsp+330h+cbMultiByte], 0
0x1800b0d2c  xor     ecx, ecx; CodePage
0x1800b0d2e  and     [rsp+330h+phkResult], 0
0x1800b0d34  call    cs:__imp_WideCharToMultiByte
0x1800b0d3b  nop     dword ptr [rax+rax+00h]
0x1800b0d40  lea     edx, [rax+1]
0x1800b0d43  movsxd  rax, edx
0x1800b0d46  lea     this, [rax+0Fh]
0x1800b0d4a  cmp     this, rax
0x1800b0d4d  ja      short loc_1800B0D59
0x1800b0d4f  mov     this, 0FFFFFFFFFFFFFF0h
0x1800b0d59  and     this, 0FFFFFFFFFFFFFFF0h
0x1800b0d5d  mov     rax, this
0x1800b0d60  call    _alloca_probe
0x1800b0d65  sub     rsp, this
0x1800b0d68  lea     rax, [rbp+2F0h+usedDefaultChar]
0x1800b0d6c  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800b0d70  lea     r8, [rbp+2F0h+wszguid]; lpWideCharStr
0x1800b0d74  xor     ecx, ecx; CodePage
0x1800b0d76  mov     [rsp+330h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x1800b0d7b  lea     rbx, [rsp+330h+usedDefaultChar]
0x1800b0d80  lea     rax, DefaultChar; "?"
0x1800b0d87  mov     [rsp+330h+lpDefaultChar], rax; lpDefaultChar
0x1800b0d8c  mov     [rsp+330h+cbMultiByte], edx; cbMultiByte
0x1800b0d90  mov     edx, 400h; dwFlags
0x1800b0d95  mov     [rsp+330h+phkResult], rbx; lpMultiByteStr
0x1800b0d9a  call    cs:__imp_WideCharToMultiByte
0x1800b0da1  nop     dword ptr [rax+rax+00h]
0x1800b0da6  mov     this, [rbp+2F0h+hkCatKey]; hParentKey
0x1800b0daa  mov     rclsid, rbx; szKeyName
0x1800b0dad  call    ?RecursiveRegDeleteKey@@YAJPEAUHKEY__@@PEAD@Z; RecursiveRegDeleteKey(HKEY__ *,char *)
0x1800b0db2  mov     ebx, eax
0x1800b0db4  test    eax, eax
0x1800b0db6  jnz     short loc_1800B0DBF
0x1800b0db8  inc     edi
0x1800b0dba  jmp     loc_1800B0C3C
0x1800b0dbf  mov     this, [rbp+2F0h+hkCatKey]; hKey
0x1800b0dc3  call    cs:__imp_RegCloseKey
0x1800b0dca  nop     dword ptr [rax+rax+00h]
0x1800b0dcf  test    ebx, ebx
0x1800b0dd1  jle     loc_1800B0C2C
0x1800b0dd7  movzx   ebx, bx
0x1800b0dda  jmp     loc_1800B0C26
0x1800b0ddf  mov     eax, 8007000Eh
0x1800b0de4  jmp     short loc_1800B0DEB
0x1800b0de6  mov     eax, 80070057h
0x1800b0deb  mov     this, [rbp+2F0h+var_30]
0x1800b0df2  xor     this, rbp; StackCookie
0x1800b0df5  call    __security_check_cookie
0x1800b0dfa  mov     rbx, [rbp+2F0h+arg_0]
0x1800b0e01  lea     rsp, [rbp+2D0h]
0x1800b0e08  pop     r14
0x1800b0e0a  pop     r13
0x1800b0e0c  pop     rdi
0x1800b0e0d  pop     rsi
0x1800b0e0e  pop     rbp
0x1800b0e0f  retn
```
