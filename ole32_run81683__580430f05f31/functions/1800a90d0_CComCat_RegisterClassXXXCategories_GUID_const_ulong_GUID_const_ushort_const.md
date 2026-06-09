# CComCat::RegisterClassXXXCategories(_GUID const &,ulong,_GUID * const,ushort const *)

- ea: `0x1800a90d0`
- end: `0x1800a9440`
- name: `?RegisterClassXXXCategories@CComCat@@AEAAJAEBU_GUID@@KQEAU2@PEBG@Z`
- size: `880`
- prototype: `HRESULT __fastcall(CComCat *this, const _GUID *rclsid, unsigned int cCategories, _GUID *rgcatid, const wchar_t *szImplReq)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800a9090`
- `0x1800a90b0`

## callees

- `0x18001775c`
- `0x18001a0d0`
- `0x18001c1d0`
- `0x180052390`
- `0x1800a90d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a9219`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a9354`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a93df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a9407`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a9219`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a9354`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a93df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a9407`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a91f7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a927c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a9345`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a93d0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a91f7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a927c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a9345`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a93d0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800a917b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800a9368`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800a917b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800a9368`

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
  __int64 v16; // rax
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
0x1800a90d0  mov     [rsp-8+arg_0], rbx
0x1800a90d5  push    rbp
0x1800a90d6  push    rsi
0x1800a90d7  push    rdi
0x1800a90d8  push    r12
0x1800a90da  push    r13
0x1800a90dc  push    r14
0x1800a90de  push    r15
0x1800a90e0  lea     rbp, [rsp-640h]
0x1800a90e8  sub     rsp, 740h
0x1800a90ef  mov     rax, cs:__security_cookie
0x1800a90f6  xor     rax, rsp
0x1800a90f9  mov     [rbp+670h+var_40], rax
0x1800a9100  mov     rbx, [rbp+670h+arg_20]
0x1800a9107  mov     r10, rclsid
0x1800a910a  mov     edx, 68h ; 'h'; cb
0x1800a910f  mov     esi, cCategories
0x1800a9112  mov     r14, rgcatid
0x1800a9115  call    ?IsValidPtrOut@@YAHPEAX_K@Z; IsValidPtrOut(void *,unsigned __int64)
0x1800a911a  xor     r15d, r15d
0x1800a911d  test    eax, eax
0x1800a911f  jnz     short loc_1800A912B
0x1800a9121  mov     eax, 80004003h
0x1800a9126  jmp     loc_1800A9416
0x1800a912b  mov     edx, 10h; cb
0x1800a9130  mov     this, r10; pv
0x1800a9133  call    ?IsValidReadPtrIn@@YAHPEBX_K@Z; IsValidReadPtrIn(void const *,unsigned __int64)
0x1800a9138  test    eax, eax
0x1800a913a  jz      loc_1800A9411
0x1800a9140  mov     rclsid, rsi
0x1800a9143  mov     this, r14; pv
0x1800a9146  shl     rclsid, 4; cb
0x1800a914a  call    ?IsValidReadPtrIn@@YAHPEBX_K@Z; IsValidReadPtrIn(void const *,unsigned __int64)
0x1800a914f  test    eax, eax
0x1800a9151  jz      loc_1800A9411
0x1800a9157  mov     [rsp+770h+hkCatKey], r15
0x1800a915c  mov     [rsp+770h+hKey], r15
0x1800a9161  test    cCategories, cCategories
0x1800a9164  jnz     short loc_1800A916D
0x1800a9166  xor     eax, eax
0x1800a9168  jmp     loc_1800A9416
0x1800a916d  mov     cCategories, 28h ; '('; cchMax
0x1800a9173  lea     rclsid, [rsp+770h+wszclsid]; lpsz
0x1800a9178  mov     this, r10; rguid
0x1800a917b  call    cs:__imp_StringFromGUID2
0x1800a9181  test    eax, eax
0x1800a9183  jnz     short loc_1800A918F
0x1800a9185  mov     eax, 8007000Eh
0x1800a918a  jmp     loc_1800A9416
0x1800a918f  lea     rax, [rsp+770h+wszclsid]
0x1800a9194  mov     r13d, 104h
0x1800a919a  mov     edx, r13d; cchDest
0x1800a919d  mov     qword ptr [rsp+770h+dwOptions], rax
0x1800a91a2  lea     rgcatid, ?CLSID@Constants@Catalog@Com@@3QBGB; ushort const near * const Com::Catalog::Constants::CLSID
0x1800a91a9  lea     r8, aSS_0; "%s\\%s"
0x1800a91b0  lea     this, [rbp+670h+szCatKey]; pszDest
0x1800a91b4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a91b9  test    eax, eax
0x1800a91bb  js      loc_1800A9416
0x1800a91c1  mov     [rsp+770h+lpdwDisposition], r15; lpdwDisposition
0x1800a91c6  lea     rax, [rsp+770h+hkCatKey]
0x1800a91cb  mov     [rsp+770h+phkResult], rax; phkResult
0x1800a91d0  lea     rclsid, [rbp+670h+szCatKey]; lpSubKey
0x1800a91d4  mov     [rsp+770h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800a91d9  mov     edi, 20006h
0x1800a91de  mov     r12, 0FFFFFFFF80000000h
0x1800a91e5  mov     [rsp+770h+samDesired], edi; samDesired
0x1800a91e9  xor     r9d, r9d; lpClass
0x1800a91ec  mov     [rsp+770h+dwOptions], r15d; dwOptions
0x1800a91f1  xor     cCategories, cCategories; Reserved
0x1800a91f4  mov     this, r12; hKey
0x1800a91f7  call    cs:__imp_RegCreateKeyExW
0x1800a91fd  test    eax, eax
0x1800a91ff  jz      short loc_1800A9214
0x1800a9201  jle     loc_1800A9416
0x1800a9207  movzx   eax, ax
0x1800a920a  or      eax, 80070000h
0x1800a920f  jmp     loc_1800A9416
0x1800a9214  mov     this, [rsp+770h+hkCatKey]; hKey
0x1800a9219  call    cs:__imp_RegCloseKey
0x1800a921f  lea     rax, [rsp+770h+wszclsid]
0x1800a9224  mov     qword ptr [rsp+770h+samDesired], rbx
0x1800a9229  lea     rgcatid, ?CLSID@Constants@Catalog@Com@@3QBGB; ushort const near * const Com::Catalog::Constants::CLSID
0x1800a9230  mov     qword ptr [rsp+770h+dwOptions], rax
0x1800a9235  lea     r8, aSSS; "%s\\%s\\%s"
0x1800a923c  mov     rclsid, r13; cchDest
0x1800a923f  lea     this, [rbp+670h+szCatKey]; pszDest
0x1800a9243  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a9248  mov     ebx, eax
0x1800a924a  test    eax, eax
0x1800a924c  js      loc_1800A9416
0x1800a9252  mov     [rsp+770h+lpdwDisposition], r15; lpdwDisposition
0x1800a9257  lea     rax, [rsp+770h+hkCatKey]
0x1800a925c  mov     [rsp+770h+phkResult], rax; phkResult
0x1800a9261  lea     rclsid, [rbp+670h+szCatKey]; lpSubKey
0x1800a9265  mov     [rsp+770h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800a926a  xor     r9d, r9d; lpClass
0x1800a926d  mov     [rsp+770h+samDesired], edi; samDesired
0x1800a9271  xor     cCategories, cCategories; Reserved
0x1800a9274  mov     this, r12; hKey
0x1800a9277  mov     [rsp+770h+dwOptions], r15d; dwOptions
0x1800a927c  call    cs:__imp_RegCreateKeyExW
0x1800a9282  test    eax, eax
0x1800a9284  jnz     loc_1800A9201
0x1800a928a  mov     edi, r15d
0x1800a928d  lea     r10, g_oldkeyinfo
0x1800a9294  cmp     edi, esi
0x1800a9296  jnb     loc_1800A9402
0x1800a929c  mov     ebx, edi
0x1800a929e  mov     ecx, r15d
0x1800a92a1  add     rbx, rbx
0x1800a92a4  mov     r9d, edi
0x1800a92a7  cmp     ecx, 5
0x1800a92aa  jge     loc_1800A935A
0x1800a92b0  movsxd  rax, ecx
0x1800a92b3  mov     rclsid, rgcatid
0x1800a92b6  imul    r8, rax, 114h
0x1800a92bd  add     rclsid, rclsid
0x1800a92c0  mov     rax, [r14+rclsid*8]
0x1800a92c4  sub     rax, [r8+r10]
0x1800a92c8  jnz     short loc_1800A92D4
0x1800a92ca  mov     rax, [r14+rclsid*8+8]
0x1800a92cf  sub     rax, [r8+r10+8]
0x1800a92d4  test    rax, rax
0x1800a92d7  jz      short loc_1800A92DD
0x1800a92d9  inc     ecx
0x1800a92db  jmp     short loc_1800A92A7
0x1800a92dd  lea     rax, [r10+14h]
0x1800a92e1  mov     rclsid, r13; cchDest
0x1800a92e4  add     rax, r8
0x1800a92e7  lea     rgcatid, ?CLSID@Constants@Catalog@Com@@3QBGB; ushort const near * const Com::Catalog::Constants::CLSID
0x1800a92ee  mov     qword ptr [rsp+770h+samDesired], rax
0x1800a92f3  lea     r8, aSSS; "%s\\%s\\%s"
0x1800a92fa  lea     rax, [rsp+770h+wszclsid]
0x1800a92ff  lea     this, [rbp+670h+szCatKeyOld]; pszDest
0x1800a9306  mov     qword ptr [rsp+770h+dwOptions], rax
0x1800a930b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a9310  test    eax, eax
0x1800a9312  js      short loc_1800A935A
0x1800a9314  mov     [rsp+770h+lpdwDisposition], r15; lpdwDisposition
0x1800a9319  lea     rax, [rsp+770h+hKey]
0x1800a931e  mov     [rsp+770h+phkResult], rax; phkResult
0x1800a9323  lea     rclsid, [rbp+670h+szCatKeyOld]; lpSubKey
0x1800a932a  mov     [rsp+770h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800a932f  xor     r9d, r9d; lpClass
0x1800a9332  mov     [rsp+770h+samDesired], 20019h; samDesired
0x1800a933a  xor     cCategories, cCategories; Reserved
0x1800a933d  mov     this, r12; hKey
0x1800a9340  mov     [rsp+770h+dwOptions], r15d; dwOptions
0x1800a9345  call    cs:__imp_RegCreateKeyExW
0x1800a934b  test    eax, eax
0x1800a934d  jnz     short loc_1800A935A
0x1800a934f  mov     this, [rsp+770h+hKey]; hKey
0x1800a9354  call    cs:__imp_RegCloseKey
0x1800a935a  lea     this, [r14+rbx*8]; rguid
0x1800a935e  mov     cCategories, 28h ; '('; cchMax
0x1800a9364  lea     rclsid, [rbp+670h+wszguid]; lpsz
0x1800a9368  call    cs:__imp_StringFromGUID2
0x1800a936e  test    eax, eax
0x1800a9370  jz      loc_1800A93FD
0x1800a9376  lea     rax, [rbp+670h+wszguid]
0x1800a937a  mov     rclsid, r13; cchDest
0x1800a937d  lea     rgcatid, [rbp+670h+szCatKey]
0x1800a9381  mov     qword ptr [rsp+770h+dwOptions], rax
0x1800a9386  lea     r8, aSS_0; "%s\\%s"
0x1800a938d  lea     this, [rbp+670h+szCat]; pszDest
0x1800a9394  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a9399  mov     ebx, eax
0x1800a939b  test    eax, eax
0x1800a939d  js      short loc_1800A9402
0x1800a939f  mov     [rsp+770h+lpdwDisposition], r15; lpdwDisposition
0x1800a93a4  lea     rax, [rsp+770h+hKey]
0x1800a93a9  mov     [rsp+770h+phkResult], rax; phkResult
0x1800a93ae  lea     rclsid, [rbp+670h+szCat]; lpSubKey
0x1800a93b5  mov     [rsp+770h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800a93ba  xor     r9d, r9d; lpClass
0x1800a93bd  mov     [rsp+770h+samDesired], 20006h; samDesired
0x1800a93c5  xor     cCategories, cCategories; Reserved
0x1800a93c8  mov     this, r12; hKey
0x1800a93cb  mov     [rsp+770h+dwOptions], r15d; dwOptions
0x1800a93d0  call    cs:__imp_RegCreateKeyExW
0x1800a93d6  test    eax, eax
0x1800a93d8  jnz     short loc_1800A93EC
0x1800a93da  mov     this, [rsp+770h+hKey]; hKey
0x1800a93df  call    cs:__imp_RegCloseKey
0x1800a93e5  inc     edi
0x1800a93e7  jmp     loc_1800A928D
0x1800a93ec  jg      short loc_1800A93F2
0x1800a93ee  mov     ebx, eax
0x1800a93f0  jmp     short loc_1800A9402
0x1800a93f2  movzx   ebx, ax
0x1800a93f5  or      ebx, 80070000h
0x1800a93fb  jmp     short loc_1800A9402
0x1800a93fd  mov     ebx, 8007000Eh
0x1800a9402  mov     this, [rsp+770h+hkCatKey]; hKey
0x1800a9407  call    cs:__imp_RegCloseKey
0x1800a940d  mov     eax, ebx
0x1800a940f  jmp     short loc_1800A9416
0x1800a9411  mov     eax, 80070057h
0x1800a9416  mov     this, [rbp+670h+var_40]
0x1800a941d  xor     this, rsp; StackCookie
0x1800a9420  call    __security_check_cookie
0x1800a9425  mov     rbx, [rsp+770h+arg_0]
0x1800a942d  add     rsp, 740h
0x1800a9434  pop     r15
0x1800a9436  pop     r14
0x1800a9438  pop     r13
0x1800a943a  pop     r12
0x1800a943c  pop     rdi
0x1800a943d  pop     rsi
0x1800a943e  pop     rbp
0x1800a943f  retn
```
