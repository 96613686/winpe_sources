# CComCat::UnRegisterClassXXXCategories(_GUID const &,ulong,_GUID * const,ushort const *)

- ea: `0x1800a95b0`
- end: `0x1800a9888`
- name: `?UnRegisterClassXXXCategories@CComCat@@AEAAJAEBU_GUID@@KQEAU2@PEBG@Z`
- size: `728`
- prototype: `HRESULT __fastcall(CComCat *this, const _GUID *rclsid, unsigned int cCategories, _GUID *rgcatid, const wchar_t *szImplReq)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800a9570`
- `0x1800a9590`

## callees

- `0x18001775c`
- `0x18001a0d0`
- `0x18001c1d0`
- `0x180052390`
- `0x180052a30`
- `0x1800a8d50`
- `0x1800a95b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a9841`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a9841`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800a9760`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800a9760`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a96a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a96a8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800a97be`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800a981e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800a97be`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800a981e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800a9645`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800a9774`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800a9645`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800a9774`

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
  int j; // ecx
  __int64 v14; // r8
  __int64 v15; // rax
  int cbMultiByte; // edx
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  void *v19; // rsp
  void *v20; // rsp
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
        for ( j = 0; j < 5; ++j )
        {
          v14 = j;
          v15 = *(_QWORD *)&rgcatid[i].Data1 - *(_QWORD *)&g_oldkeyinfo[v14].catid.Data1;
          if ( !v15 )
            v15 = *(_QWORD *)rgcatid[i].Data4 - *(_QWORD *)g_oldkeyinfo[v14].catid.Data4;
          if ( !v15 )
          {
            if ( StringCchPrintfW(
                   szCatKey,
                   0x104u,
                   L"%s\\%s\\%s",
                   Com::Catalog::Constants::CLSID,
                   wszclsid,
                   g_oldkeyinfo[v14].szDescription) >= 0 )
              RegDeleteKeyExW(HKEY_CLASSES_ROOT, szCatKey, 0, 0);
            break;
          }
        }
        if ( !StringFromGUID2(&rgcatid[i], wszguid, 40) )
          return -2147024882;
        usedDefaultChar = 0;
        cbMultiByte = WideCharToMultiByte(0, 0x400u, wszguid, -1, 0, 0, "?", &usedDefaultChar) + 1;
        v17 = cbMultiByte + 15LL;
        if ( v17 <= cbMultiByte )
          v17 = 0xFFFFFFFFFFFFFF0LL;
        v18 = v17 & 0xFFFFFFFFFFFFFFF0uLL;
        v19 = alloca(v18);
        v20 = alloca(v18);
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
0x1800a95b0  push    rbp
0x1800a95b2  push    rsi
0x1800a95b3  push    rdi
0x1800a95b4  push    r13
0x1800a95b6  push    r14
0x1800a95b8  sub     rsp, 310h
0x1800a95bf  lea     rbp, [rsp+40h]
0x1800a95c4  mov     [rbp+2F0h+arg_0], rbx
0x1800a95cb  mov     rax, cs:__security_cookie
0x1800a95d2  xor     rax, rbp
0x1800a95d5  mov     [rbp+2F0h+var_30], rax
0x1800a95dc  mov     rbx, [rbp+2F0h+szImplReq]
0x1800a95e3  mov     r10, rclsid
0x1800a95e6  mov     edx, 68h ; 'h'; cb
0x1800a95eb  mov     r14d, cCategories
0x1800a95ee  mov     rsi, rgcatid
0x1800a95f1  call    ?IsValidPtrOut@@YAHPEAX_K@Z; IsValidPtrOut(void *,unsigned __int64)
0x1800a95f6  test    eax, eax
0x1800a95f8  jnz     short loc_1800A9604
0x1800a95fa  mov     eax, 80004003h
0x1800a95ff  jmp     loc_1800A9863
0x1800a9604  mov     edx, 10h; cb
0x1800a9609  mov     this, r10; pv
0x1800a960c  call    ?IsValidReadPtrIn@@YAHPEBX_K@Z; IsValidReadPtrIn(void const *,unsigned __int64)
0x1800a9611  test    eax, eax
0x1800a9613  jz      loc_1800A985E
0x1800a9619  mov     rclsid, r14
0x1800a961c  mov     this, rsi; pv
0x1800a961f  shl     rclsid, 4; cb
0x1800a9623  call    ?IsValidReadPtrIn@@YAHPEBX_K@Z; IsValidReadPtrIn(void const *,unsigned __int64)
0x1800a9628  test    eax, eax
0x1800a962a  jz      loc_1800A985E
0x1800a9630  mov     cCategories, 28h ; '('; cchMax
0x1800a9636  mov     [rbp+2F0h+hkCatKey], 0
0x1800a963e  lea     rclsid, [rbp+2F0h+wszclsid]; lpsz
0x1800a9642  mov     this, r10; rguid
0x1800a9645  call    cs:__imp_StringFromGUID2
0x1800a964b  test    eax, eax
0x1800a964d  jz      loc_1800A9857
0x1800a9653  lea     rax, [rbp+2F0h+wszclsid]
0x1800a9657  mov     qword ptr [rsp+330h+cbMultiByte], rbx
0x1800a965c  lea     rgcatid, ?CLSID@Constants@Catalog@Com@@3QBGB; ushort const near * const Com::Catalog::Constants::CLSID
0x1800a9663  mov     [rsp+330h+phkResult], rax
0x1800a9668  lea     r8, aSSS; "%s\\%s\\%s"
0x1800a966f  mov     edx, 104h; cchDest
0x1800a9674  lea     this, [rbp+2F0h+szCatKey]; pszDest
0x1800a967b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a9680  test    eax, eax
0x1800a9682  js      loc_1800A9863
0x1800a9688  lea     rax, [rbp+2F0h+hkCatKey]
0x1800a968c  mov     r9d, 0F003Fh; samDesired
0x1800a9692  xor     cCategories, cCategories; ulOptions
0x1800a9695  mov     [rsp+330h+phkResult], rax; phkResult
0x1800a969a  lea     rclsid, [rbp+2F0h+szCatKey]; lpSubKey
0x1800a96a1  mov     this, 0FFFFFFFF80000000h; hKey
0x1800a96a8  call    cs:__imp_RegOpenKeyExW
0x1800a96ae  mov     ebx, eax
0x1800a96b0  test    eax, eax
0x1800a96b2  jz      short loc_1800A96C6
0x1800a96b4  jle     short loc_1800A96BF
0x1800a96b6  movzx   ebx, ax
0x1800a96b9  or      ebx, 80070000h
0x1800a96bf  mov     eax, ebx
0x1800a96c1  jmp     loc_1800A9863
0x1800a96c6  xor     edi, edi
0x1800a96c8  lea     r13, g_oldkeyinfo
0x1800a96cf  cmp     edi, r14d
0x1800a96d2  jnb     loc_1800A983D
0x1800a96d8  xor     ecx, ecx
0x1800a96da  mov     ebx, edi
0x1800a96dc  add     rbx, rbx
0x1800a96df  mov     r9d, edi
0x1800a96e2  cmp     ecx, 5
0x1800a96e5  jge     short loc_1800A9766
0x1800a96e7  movsxd  rax, ecx
0x1800a96ea  mov     rclsid, rgcatid
0x1800a96ed  imul    r8, rax, 114h
0x1800a96f4  add     rclsid, rclsid
0x1800a96f7  mov     rax, [rsi+rclsid*8]
0x1800a96fb  sub     rax, [r8+r13]
0x1800a96ff  jnz     short loc_1800A970B
0x1800a9701  mov     rax, [rsi+rclsid*8+8]
0x1800a9706  sub     rax, [r8+r13+8]
0x1800a970b  test    rax, rax
0x1800a970e  jz      short loc_1800A9714
0x1800a9710  inc     ecx
0x1800a9712  jmp     short loc_1800A96E2
0x1800a9714  lea     rax, [r13+14h]
0x1800a9718  mov     edx, 104h; cchDest
0x1800a971d  add     rax, r8
0x1800a9720  lea     rgcatid, ?CLSID@Constants@Catalog@Com@@3QBGB; ushort const near * const Com::Catalog::Constants::CLSID
0x1800a9727  mov     qword ptr [rsp+330h+cbMultiByte], rax
0x1800a972c  lea     r8, aSSS; "%s\\%s\\%s"
0x1800a9733  lea     rax, [rbp+2F0h+wszclsid]
0x1800a9737  lea     this, [rbp+2F0h+szCatKey]; pszDest
0x1800a973e  mov     [rsp+330h+phkResult], rax
0x1800a9743  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a9748  test    eax, eax
0x1800a974a  js      short loc_1800A9766
0x1800a974c  xor     r9d, r9d; Reserved
0x1800a974f  lea     rclsid, [rbp+2F0h+szCatKey]; lpSubKey
0x1800a9756  xor     cCategories, cCategories; samDesired
0x1800a9759  mov     this, 0FFFFFFFF80000000h; hKey
0x1800a9760  call    cs:__imp_RegDeleteKeyExW
0x1800a9766  lea     this, [rsi+rbx*8]; rguid
0x1800a976a  mov     cCategories, 28h ; '('; cchMax
0x1800a9770  lea     rclsid, [rbp+2F0h+wszguid]; lpsz
0x1800a9774  call    cs:__imp_StringFromGUID2
0x1800a977a  test    eax, eax
0x1800a977c  jz      loc_1800A9857
0x1800a9782  lea     rax, [rbp+2F0h+usedDefaultChar]
0x1800a9786  mov     [rbp+2F0h+usedDefaultChar], 0
0x1800a978d  mov     [rsp+330h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x1800a9792  lea     r8, [rbp+2F0h+wszguid]; lpWideCharStr
0x1800a9796  lea     rax, DefaultChar; "?"
0x1800a979d  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800a97a1  mov     [rsp+330h+lpDefaultChar], rax; lpDefaultChar
0x1800a97a6  mov     edx, 400h; dwFlags
0x1800a97ab  mov     [rsp+330h+cbMultiByte], 0; cbMultiByte
0x1800a97b3  xor     ecx, ecx; CodePage
0x1800a97b5  mov     [rsp+330h+phkResult], 0; lpMultiByteStr
0x1800a97be  call    cs:__imp_WideCharToMultiByte
0x1800a97c4  lea     edx, [rax+1]
0x1800a97c7  movsxd  rax, edx
0x1800a97ca  lea     this, [rax+0Fh]
0x1800a97ce  cmp     this, rax
0x1800a97d1  ja      short loc_1800A97DD
0x1800a97d3  mov     this, 0FFFFFFFFFFFFFF0h
0x1800a97dd  and     this, 0FFFFFFFFFFFFFFF0h
0x1800a97e1  mov     rax, this
0x1800a97e4  call    _alloca_probe
0x1800a97e9  sub     rsp, this
0x1800a97ec  lea     rax, [rbp+2F0h+usedDefaultChar]
0x1800a97f0  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800a97f4  lea     r8, [rbp+2F0h+wszguid]; lpWideCharStr
0x1800a97f8  xor     ecx, ecx; CodePage
0x1800a97fa  mov     [rsp+330h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x1800a97ff  lea     rbx, [rsp+330h+usedDefaultChar]
0x1800a9804  lea     rax, DefaultChar; "?"
0x1800a980b  mov     [rsp+330h+lpDefaultChar], rax; lpDefaultChar
0x1800a9810  mov     [rsp+330h+cbMultiByte], edx; cbMultiByte
0x1800a9814  mov     edx, 400h; dwFlags
0x1800a9819  mov     [rsp+330h+phkResult], rbx; lpMultiByteStr
0x1800a981e  call    cs:__imp_WideCharToMultiByte
0x1800a9824  mov     this, [rbp+2F0h+hkCatKey]; hParentKey
0x1800a9828  mov     rclsid, rbx; szKeyName
0x1800a982b  call    ?RecursiveRegDeleteKey@@YAJPEAUHKEY__@@PEAD@Z; RecursiveRegDeleteKey(HKEY__ *,char *)
0x1800a9830  mov     ebx, eax
0x1800a9832  test    eax, eax
0x1800a9834  jnz     short loc_1800A983D
0x1800a9836  inc     edi
0x1800a9838  jmp     loc_1800A96CF
0x1800a983d  mov     this, [rbp+2F0h+hkCatKey]; hKey
0x1800a9841  call    cs:__imp_RegCloseKey
0x1800a9847  test    ebx, ebx
0x1800a9849  jle     loc_1800A96BF
0x1800a984f  movzx   ebx, bx
0x1800a9852  jmp     loc_1800A96B9
0x1800a9857  mov     eax, 8007000Eh
0x1800a985c  jmp     short loc_1800A9863
0x1800a985e  mov     eax, 80070057h
0x1800a9863  mov     this, [rbp+2F0h+var_30]
0x1800a986a  xor     this, rbp; StackCookie
0x1800a986d  call    __security_check_cookie
0x1800a9872  mov     rbx, [rbp+2F0h+arg_0]
0x1800a9879  lea     rsp, [rbp+2D0h]
0x1800a9880  pop     r14
0x1800a9882  pop     r13
0x1800a9884  pop     rdi
0x1800a9885  pop     rsi
0x1800a9886  pop     rbp
0x1800a9887  retn
```
