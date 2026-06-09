# CComCat::RegisterClassXXXCategories(_GUID const &,ulong,_GUID * const,ushort const *)

- ea: `0x1800b05d4`
- end: `0x1800b0989`
- name: `?RegisterClassXXXCategories@CComCat@@AEAAJAEBU_GUID@@KQEAU2@PEBG@Z`
- size: `949`
- prototype: `HRESULT __fastcall(CComCat *this, const _GUID *rclsid, unsigned int cCategories, _GUID *rgcatid, const wchar_t *szImplReq)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800b0580`
- `0x1800b05b0`

## callees

- `0x18000f660`
- `0x180010fac`
- `0x18001d110`
- `0x180046460`
- `0x1800b05d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b0701`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b0792`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b0869`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b0906`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b0701`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b0792`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b0869`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b0906`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b0729`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b087e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b091b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b0949`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b0729`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b087e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b091b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b0949`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b067f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b0898`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b067f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b0898`

## pseudocode

```c
HRESULT __fastcall CComCat::RegisterClassXXXCategories(
        CComCat *this,
        const _GUID *rclsid,
        unsigned int cCategories,
        _GUID *rgcatid,
        const wchar_t *szImplReq)
{
  __int64 v5; // rsi
  const void *v7; // r10
  HRESULT result; // eax
  int v9; // r8d
  const GUID *v10; // r10
  bool v11; // cc
  signed int v12; // ebx
  unsigned int i; // edi
  int j; // ecx
  __int64 v15; // r8
  __int64 v16; // rdx
  LSTATUS v17; // eax
  HKEY__ *hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY__ *hkCatKey; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t wszclsid[40]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t wszguid[40]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t szCatKey[264]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t szCatKeyOld[264]; // [rsp+310h] [rbp+210h] BYREF
  wchar_t szCat[264]; // [rsp+520h] [rbp+420h] BYREF

  v5 = cCategories;
  if ( !IsValidPtrOut(this, 0x68u) )
    return -2147467261;
  if ( !IsValidReadPtrIn(v7, 0x10u) || !IsValidReadPtrIn(rgcatid, 16 * v5) )
    return -2147024809;
  hkCatKey = 0;
  hKey = 0;
  if ( !v9 )
    return 0;
  if ( !StringFromGUID2(v10, wszclsid, 40) )
    return -2147024882;
  result = StringCchPrintfW(szCatKey, 0x104u, L"%s\\%s", Com::Catalog::Constants::CLSID, wszclsid);
  if ( result >= 0 )
  {
    result = RegCreateKeyExW(HKEY_CLASSES_ROOT, szCatKey, 0, 0, 0, 0x20006u, 0, &hkCatKey, 0);
    v11 = result <= 0;
    if ( result )
      goto LABEL_11;
    RegCloseKey(hkCatKey);
    result = StringCchPrintfW(szCatKey, 0x104u, L"%s\\%s\\%s", Com::Catalog::Constants::CLSID, wszclsid, szImplReq);
    v12 = result;
    if ( result < 0 )
      return result;
    result = RegCreateKeyExW(HKEY_CLASSES_ROOT, szCatKey, 0, 0, 0, 0x20006u, 0, &hkCatKey, 0);
    v11 = result <= 0;
    if ( result )
    {
LABEL_11:
      if ( !v11 )
        return (unsigned __int16)result | 0x80070000;
    }
    else
    {
      for ( i = 0; i < (unsigned int)v5; ++i )
      {
        for ( j = 0; j < 5; ++j )
        {
          v15 = j;
          v16 = *(_QWORD *)&rgcatid[i].Data1 - *(_QWORD *)&g_oldkeyinfo[v15].catid.Data1;
          if ( !v16 )
            v16 = *(_QWORD *)rgcatid[i].Data4 - *(_QWORD *)g_oldkeyinfo[v15].catid.Data4;
          if ( !v16 )
          {
            if ( StringCchPrintfW(
                   szCatKeyOld,
                   0x104u,
                   L"%s\\%s\\%s",
                   Com::Catalog::Constants::CLSID,
                   wszclsid,
                   g_oldkeyinfo[v15].szDescription) >= 0
              && !RegCreateKeyExW(HKEY_CLASSES_ROOT, szCatKeyOld, 0, 0, 0, 0x20019u, 0, &hKey, 0) )
            {
              RegCloseKey(hKey);
            }
            break;
          }
        }
        if ( !StringFromGUID2(&rgcatid[i], wszguid, 40) )
        {
          v12 = -2147024882;
          break;
        }
        v12 = StringCchPrintfW(szCat, 0x104u, L"%s\\%s", szCatKey, wszguid);
        if ( v12 < 0 )
          break;
        v17 = RegCreateKeyExW(HKEY_CLASSES_ROOT, szCat, 0, 0, 0, 0x20006u, 0, &hKey, 0);
        if ( v17 )
        {
          if ( v17 > 0 )
            v12 = (unsigned __int16)v17 | 0x80070000;
          else
            v12 = v17;
          break;
        }
        RegCloseKey(hKey);
      }
      RegCloseKey(hkCatKey);
      return v12;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800b05d4  mov     [rsp-8+arg_0], rbx
0x1800b05d9  push    rbp
0x1800b05da  push    rsi
0x1800b05db  push    rdi
0x1800b05dc  push    r12
0x1800b05de  push    r13
0x1800b05e0  push    r14
0x1800b05e2  push    r15
0x1800b05e4  lea     rbp, [rsp-640h]
0x1800b05ec  sub     rsp, 740h
0x1800b05f3  mov     rax, cs:__security_cookie
0x1800b05fa  xor     rax, rsp
0x1800b05fd  mov     [rbp+670h+var_40], rax
0x1800b0604  mov     rbx, [rbp+670h+arg_20]
0x1800b060b  mov     r10, rclsid
0x1800b060e  mov     edx, 68h ; 'h'; cb
0x1800b0613  mov     esi, cCategories
0x1800b0616  mov     r14, rgcatid
0x1800b0619  call    ?IsValidPtrOut@@YAHPEAX_K@Z; IsValidPtrOut(void *,unsigned __int64)
0x1800b061e  xor     r15d, r15d
0x1800b0621  test    eax, eax
0x1800b0623  jnz     short loc_1800B062F
0x1800b0625  mov     eax, 80004003h
0x1800b062a  jmp     loc_1800B095E
0x1800b062f  mov     edx, 10h; cb
0x1800b0634  mov     this, r10; pv
0x1800b0637  call    ?IsValidReadPtrIn@@YAHPEBX_K@Z; IsValidReadPtrIn(void const *,unsigned __int64)
0x1800b063c  test    eax, eax
0x1800b063e  jz      loc_1800B0959
0x1800b0644  mov     rclsid, rsi
0x1800b0647  mov     this, r14; pv
0x1800b064a  shl     rclsid, 4; cb
0x1800b064e  call    ?IsValidReadPtrIn@@YAHPEBX_K@Z; IsValidReadPtrIn(void const *,unsigned __int64)
0x1800b0653  test    eax, eax
0x1800b0655  jz      loc_1800B0959
0x1800b065b  mov     [rsp+770h+hkCatKey], r15
0x1800b0660  mov     [rsp+770h+hKey], r15
0x1800b0665  test    cCategories, cCategories
0x1800b0668  jnz     short loc_1800B0671
0x1800b066a  xor     eax, eax
0x1800b066c  jmp     loc_1800B095E
0x1800b0671  mov     cCategories, 28h ; '('; cchMax
0x1800b0677  lea     rclsid, [rsp+770h+wszclsid]; lpsz
0x1800b067c  mov     this, r10; rguid
0x1800b067f  call    cs:__imp_StringFromGUID2
0x1800b0686  nop     dword ptr [rax+rax+00h]
0x1800b068b  test    eax, eax
0x1800b068d  jnz     short loc_1800B0699
0x1800b068f  mov     eax, 8007000Eh
0x1800b0694  jmp     loc_1800B095E
0x1800b0699  lea     rax, [rsp+770h+wszclsid]
0x1800b069e  mov     r13d, 104h
0x1800b06a4  mov     edx, r13d; cchDest
0x1800b06a7  mov     qword ptr [rsp+770h+dwOptions], rax
0x1800b06ac  lea     rgcatid, ?CLSID@Constants@Catalog@Com@@3QBGB; ushort const near * const Com::Catalog::Constants::CLSID
0x1800b06b3  lea     r8, aSS_0; "%s\\%s"
0x1800b06ba  lea     this, [rbp+670h+szCatKey]; pszDest
0x1800b06be  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b06c3  test    eax, eax
0x1800b06c5  js      loc_1800B095E
0x1800b06cb  mov     [rsp+770h+lpdwDisposition], r15; lpdwDisposition
0x1800b06d0  lea     rax, [rsp+770h+hkCatKey]
0x1800b06d5  mov     [rsp+770h+phkResult], rax; phkResult
0x1800b06da  lea     rclsid, [rbp+670h+szCatKey]; lpSubKey
0x1800b06de  mov     [rsp+770h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800b06e3  mov     edi, 20006h
0x1800b06e8  mov     r12, 0FFFFFFFF80000000h
0x1800b06ef  mov     [rsp+770h+samDesired], edi; samDesired
0x1800b06f3  xor     r9d, r9d; lpClass
0x1800b06f6  mov     [rsp+770h+dwOptions], r15d; dwOptions
0x1800b06fb  xor     cCategories, cCategories; Reserved
0x1800b06fe  mov     this, r12; hKey
0x1800b0701  call    cs:__imp_RegCreateKeyExW
0x1800b0708  nop     dword ptr [rax+rax+00h]
0x1800b070d  test    eax, eax
0x1800b070f  jz      short loc_1800B0724
0x1800b0711  jle     loc_1800B095E
0x1800b0717  movzx   eax, ax
0x1800b071a  or      eax, 80070000h
0x1800b071f  jmp     loc_1800B095E
0x1800b0724  mov     this, [rsp+770h+hkCatKey]; hKey
0x1800b0729  call    cs:__imp_RegCloseKey
0x1800b0730  nop     dword ptr [rax+rax+00h]
0x1800b0735  lea     rax, [rsp+770h+wszclsid]
0x1800b073a  mov     qword ptr [rsp+770h+samDesired], rbx
0x1800b073f  lea     rgcatid, ?CLSID@Constants@Catalog@Com@@3QBGB; ushort const near * const Com::Catalog::Constants::CLSID
0x1800b0746  mov     qword ptr [rsp+770h+dwOptions], rax
0x1800b074b  lea     r8, aSSS; "%s\\%s\\%s"
0x1800b0752  mov     rclsid, r13; cchDest
0x1800b0755  lea     this, [rbp+670h+szCatKey]; pszDest
0x1800b0759  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b075e  mov     ebx, eax
0x1800b0760  test    eax, eax
0x1800b0762  js      loc_1800B095E
0x1800b0768  mov     [rsp+770h+lpdwDisposition], r15; lpdwDisposition
0x1800b076d  lea     rax, [rsp+770h+hkCatKey]
0x1800b0772  mov     [rsp+770h+phkResult], rax; phkResult
0x1800b0777  lea     rclsid, [rbp+670h+szCatKey]; lpSubKey
0x1800b077b  mov     [rsp+770h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800b0780  xor     r9d, r9d; lpClass
0x1800b0783  mov     [rsp+770h+samDesired], edi; samDesired
0x1800b0787  xor     cCategories, cCategories; Reserved
0x1800b078a  mov     this, r12; hKey
0x1800b078d  mov     [rsp+770h+dwOptions], r15d; dwOptions
0x1800b0792  call    cs:__imp_RegCreateKeyExW
0x1800b0799  nop     dword ptr [rax+rax+00h]
0x1800b079e  test    eax, eax
0x1800b07a0  jnz     loc_1800B0711
0x1800b07a6  mov     edi, r15d
0x1800b07a9  lea     r10, g_oldkeyinfo
0x1800b07b0  cmp     edi, esi
0x1800b07b2  jnb     loc_1800B0944
0x1800b07b8  mov     ebx, edi
0x1800b07ba  mov     ecx, r15d
0x1800b07bd  add     rbx, rbx
0x1800b07c0  mov     r9d, edi
0x1800b07c3  cmp     ecx, 5
0x1800b07c6  jge     loc_1800B088A
0x1800b07cc  movsxd  rax, ecx
0x1800b07cf  imul    r8, rax, 114h
0x1800b07d6  mov     rax, rgcatid
0x1800b07d9  add     rax, rax
0x1800b07dc  mov     rclsid, [r14+rax*8]
0x1800b07e0  sub     rclsid, [r8+r10]
0x1800b07e4  jnz     short loc_1800B07F0
0x1800b07e6  mov     rclsid, [r14+rax*8+8]
0x1800b07eb  sub     rclsid, [r8+r10+8]
0x1800b07f0  test    rclsid, rclsid
0x1800b07f3  mov     eax, r15d
0x1800b07f6  setz    al
0x1800b07f9  test    eax, eax
0x1800b07fb  jnz     short loc_1800B0801
0x1800b07fd  inc     ecx
0x1800b07ff  jmp     short loc_1800B07C3
0x1800b0801  lea     rax, [r10+14h]
0x1800b0805  mov     rclsid, r13; cchDest
0x1800b0808  add     rax, r8
0x1800b080b  lea     rgcatid, ?CLSID@Constants@Catalog@Com@@3QBGB; ushort const near * const Com::Catalog::Constants::CLSID
0x1800b0812  mov     qword ptr [rsp+770h+samDesired], rax
0x1800b0817  lea     r8, aSSS; "%s\\%s\\%s"
0x1800b081e  lea     rax, [rsp+770h+wszclsid]
0x1800b0823  lea     this, [rbp+670h+szCatKeyOld]; pszDest
0x1800b082a  mov     qword ptr [rsp+770h+dwOptions], rax
0x1800b082f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b0834  test    eax, eax
0x1800b0836  js      short loc_1800B088A
0x1800b0838  mov     [rsp+770h+lpdwDisposition], r15; lpdwDisposition
0x1800b083d  lea     rax, [rsp+770h+hKey]
0x1800b0842  mov     [rsp+770h+phkResult], rax; phkResult
0x1800b0847  lea     rclsid, [rbp+670h+szCatKeyOld]; lpSubKey
0x1800b084e  mov     [rsp+770h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800b0853  xor     r9d, r9d; lpClass
0x1800b0856  mov     [rsp+770h+samDesired], 20019h; samDesired
0x1800b085e  xor     cCategories, cCategories; Reserved
0x1800b0861  mov     this, r12; hKey
0x1800b0864  mov     [rsp+770h+dwOptions], r15d; dwOptions
0x1800b0869  call    cs:__imp_RegCreateKeyExW
0x1800b0870  nop     dword ptr [rax+rax+00h]
0x1800b0875  test    eax, eax
0x1800b0877  jnz     short loc_1800B088A
0x1800b0879  mov     this, [rsp+770h+hKey]; hKey
0x1800b087e  call    cs:__imp_RegCloseKey
0x1800b0885  nop     dword ptr [rax+rax+00h]
0x1800b088a  lea     this, [r14+rbx*8]; rguid
0x1800b088e  mov     cCategories, 28h ; '('; cchMax
0x1800b0894  lea     rclsid, [rbp+670h+wszguid]; lpsz
0x1800b0898  call    cs:__imp_StringFromGUID2
0x1800b089f  nop     dword ptr [rax+rax+00h]
0x1800b08a4  test    eax, eax
0x1800b08a6  jz      loc_1800B093F
0x1800b08ac  lea     rax, [rbp+670h+wszguid]
0x1800b08b0  mov     rclsid, r13; cchDest
0x1800b08b3  lea     rgcatid, [rbp+670h+szCatKey]
0x1800b08b7  mov     qword ptr [rsp+770h+dwOptions], rax
0x1800b08bc  lea     r8, aSS_0; "%s\\%s"
0x1800b08c3  lea     this, [rbp+670h+szCat]; pszDest
0x1800b08ca  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b08cf  mov     ebx, eax
0x1800b08d1  test    eax, eax
0x1800b08d3  js      short loc_1800B0944
0x1800b08d5  mov     [rsp+770h+lpdwDisposition], r15; lpdwDisposition
0x1800b08da  lea     rax, [rsp+770h+hKey]
0x1800b08df  mov     [rsp+770h+phkResult], rax; phkResult
0x1800b08e4  lea     rclsid, [rbp+670h+szCat]; lpSubKey
0x1800b08eb  mov     [rsp+770h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800b08f0  xor     r9d, r9d; lpClass
0x1800b08f3  mov     [rsp+770h+samDesired], 20006h; samDesired
0x1800b08fb  xor     cCategories, cCategories; Reserved
0x1800b08fe  mov     this, r12; hKey
0x1800b0901  mov     [rsp+770h+dwOptions], r15d; dwOptions
0x1800b0906  call    cs:__imp_RegCreateKeyExW
0x1800b090d  nop     dword ptr [rax+rax+00h]
0x1800b0912  test    eax, eax
0x1800b0914  jnz     short loc_1800B092E
0x1800b0916  mov     this, [rsp+770h+hKey]; hKey
0x1800b091b  call    cs:__imp_RegCloseKey
0x1800b0922  nop     dword ptr [rax+rax+00h]
0x1800b0927  inc     edi
0x1800b0929  jmp     loc_1800B07A9
0x1800b092e  jg      short loc_1800B0934
0x1800b0930  mov     ebx, eax
0x1800b0932  jmp     short loc_1800B0944
0x1800b0934  movzx   ebx, ax
0x1800b0937  or      ebx, 80070000h
0x1800b093d  jmp     short loc_1800B0944
0x1800b093f  mov     ebx, 8007000Eh
0x1800b0944  mov     this, [rsp+770h+hkCatKey]; hKey
0x1800b0949  call    cs:__imp_RegCloseKey
0x1800b0950  nop     dword ptr [rax+rax+00h]
0x1800b0955  mov     eax, ebx
0x1800b0957  jmp     short loc_1800B095E
0x1800b0959  mov     eax, 80070057h
0x1800b095e  mov     this, [rbp+670h+var_40]
0x1800b0965  xor     this, rsp; StackCookie
0x1800b0968  call    __security_check_cookie
0x1800b096d  mov     rbx, [rsp+770h+arg_0]
0x1800b0975  add     rsp, 740h
0x1800b097c  pop     r15
0x1800b097e  pop     r14
0x1800b0980  pop     r13
0x1800b0982  pop     r12
0x1800b0984  pop     rdi
0x1800b0985  pop     rsi
0x1800b0986  pop     rbp
0x1800b0987  retn
```
