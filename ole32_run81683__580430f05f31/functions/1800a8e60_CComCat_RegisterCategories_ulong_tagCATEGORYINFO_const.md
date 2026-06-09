# CComCat::RegisterCategories(ulong,tagCATEGORYINFO * const)

- ea: `0x1800a8e60`
- end: `0x1800a9082`
- name: `?RegisterCategories@CComCat@@UEAAJKQEAUtagCATEGORYINFO@@@Z`
- size: `546`
- prototype: `HRESULT __fastcall(CComCat *this, unsigned int cCategories, tagCATEGORYINFO *rgCategoryInfo)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001a0d0`
- `0x18001c1d0`
- `0x180052390`
- `0x180053014`
- `0x18007a330`
- `0x1800a8e60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a902e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a9051`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a902e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a9051`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a8f0a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a8fa9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a8f0a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a8fa9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a9021`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a9021`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800a8fe6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800a8fe6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800a8f6b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800a8f6b`

## string_xrefs

- `0x1800a8eda`: `Component Categories`

## pseudocode

```c
__int64 __fastcall CComCat::RegisterCategories(
        CComCat *this,
        unsigned int cCategories,
        tagCATEGORYINFO *rgCategoryInfo)
{
  __int64 v3; // r15
  int v6; // esi
  unsigned int i; // r14d
  tagCATEGORYINFO *v8; // rbx
  const BYTE *szDescription; // rbx
  __int64 v10; // rax
  LSTATUS v11; // ebx
  HKEY__ *hkeyCat; // [rsp+50h] [rbp-B0h] BYREF
  HKEY__ *hkey; // [rsp+58h] [rbp-A8h] BYREF
  char szlcid[16]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t wszlcid[56]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t wszcatid[40]; // [rsp+E0h] [rbp-20h] BYREF

  v3 = cCategories;
  if ( !IsValidPtrOut(this, 0x68u) )
    return 2147500035LL;
  if ( !IsValidReadPtrIn(rgCategoryInfo, 276 * v3) )
    return 2147942487LL;
  hkey = 0;
  hkeyCat = 0;
  if ( RegCreateKeyExW(HKEY_CLASSES_ROOT, L"Component Categories", 0, 0, 0, 0x20006u, 0, &hkey, 0) )
    return 1;
  v6 = 0;
  for ( i = 0; i < (unsigned int)v3; ++i )
  {
    v8 = &rgCategoryInfo[i];
    v6 = StringCchPrintfA(szlcid, 0x10u, "%lX", v8->lcid);
    if ( v6 < 0 )
      break;
    if ( !StringFromGUID2(&v8->catid, wszcatid, 40) )
    {
      v6 = -2147024882;
      break;
    }
    if ( RegCreateKeyExW(hkey, wszcatid, 0, 0, 0, 0x20006u, 0, &hkeyCat, 0) )
      goto LABEL_16;
    memset_0(wszlcid, 0, 0x64u);
    MultiByteToWideChar(0, 0, szlcid, -1, wszlcid, 50);
    szDescription = (const BYTE *)v8->szDescription;
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)&szDescription[2 * v10] );
    v11 = RegSetValueExW(hkeyCat, wszlcid, 0, 1u, szDescription, 2 * v10 + 2);
    RegCloseKey(hkeyCat);
    if ( v11 )
    {
LABEL_16:
      v6 = 1;
      break;
    }
  }
  RegCloseKey(hkey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800a8e60  mov     [rsp-8+arg_0], rbx
0x1800a8e65  mov     [rsp-8+arg_8], rsi
0x1800a8e6a  push    rbp
0x1800a8e6b  push    r12
0x1800a8e6d  push    r13
0x1800a8e6f  push    r14
0x1800a8e71  push    r15
0x1800a8e73  lea     rbp, [rsp-40h]
0x1800a8e78  sub     rsp, 140h
0x1800a8e7f  mov     rax, cs:__security_cookie
0x1800a8e86  xor     rax, rsp
0x1800a8e89  mov     [rbp+60h+var_30], rax
0x1800a8e8d  mov     r15d, cCategories
0x1800a8e90  mov     r12, rgCategoryInfo
0x1800a8e93  mov     cCategories, 68h ; 'h'; cb
0x1800a8e98  call    ?IsValidPtrOut@@YAHPEAX_K@Z; IsValidPtrOut(void *,unsigned __int64)
0x1800a8e9d  xor     r13d, r13d
0x1800a8ea0  test    eax, eax
0x1800a8ea2  jnz     short loc_1800A8EAE
0x1800a8ea4  mov     eax, 80004003h
0x1800a8ea9  jmp     loc_1800A9059
0x1800a8eae  imul    rdx, r15, 114h; cb
0x1800a8eb5  mov     this, r12; pv
0x1800a8eb8  call    ?IsValidReadPtrIn@@YAHPEBX_K@Z; IsValidReadPtrIn(void const *,unsigned __int64)
0x1800a8ebd  test    eax, eax
0x1800a8ebf  jnz     short loc_1800A8ECB
0x1800a8ec1  mov     eax, 80070057h
0x1800a8ec6  jmp     loc_1800A9059
0x1800a8ecb  mov     [rsp+160h+lpdwDisposition], r13; lpdwDisposition
0x1800a8ed0  lea     rax, [rsp+160h+hkey]
0x1800a8ed5  mov     [rsp+160h+phkResult], rax; phkResult
0x1800a8eda  lea     rdx, aComponentCateg; "Component Categories"
0x1800a8ee1  mov     [rsp+160h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1800a8ee6  xor     r9d, r9d; lpClass
0x1800a8ee9  mov     [rsp+160h+samDesired], 20006h; samDesired
0x1800a8ef1  xor     r8d, r8d; Reserved
0x1800a8ef4  mov     this, 0FFFFFFFF80000000h; hKey
0x1800a8efb  mov     [rsp+160h+dwOptions], r13d; dwOptions
0x1800a8f00  mov     [rsp+160h+hkey], r13
0x1800a8f05  mov     [rsp+160h+hkeyCat], r13
0x1800a8f0a  call    cs:__imp_RegCreateKeyExW
0x1800a8f10  test    eax, eax
0x1800a8f12  jz      short loc_1800A8F1E
0x1800a8f14  mov     eax, 1
0x1800a8f19  jmp     loc_1800A9059
0x1800a8f1e  mov     esi, r13d
0x1800a8f21  mov     r14d, r13d
0x1800a8f24  cmp     r14d, r15d
0x1800a8f27  jnb     loc_1800A904C
0x1800a8f2d  mov     eax, r14d
0x1800a8f30  lea     rgCategoryInfo, aLx; "%lX"
0x1800a8f37  imul    rbx, rax, 114h
0x1800a8f3e  mov     cCategories, 10h; cchDest
0x1800a8f43  lea     this, [rsp+160h+szlcid]; pszDest
0x1800a8f48  add     rbx, r12
0x1800a8f4b  mov     r9d, [rbx+10h]
0x1800a8f4f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800a8f54  mov     esi, eax
0x1800a8f56  test    eax, eax
0x1800a8f58  js      loc_1800A904C
0x1800a8f5e  mov     r8d, 28h ; '('; cchMax
0x1800a8f64  lea     rdx, [rbp+60h+wszcatid]; lpsz
0x1800a8f68  mov     this, rbx; rguid
0x1800a8f6b  call    cs:__imp_StringFromGUID2
0x1800a8f71  test    eax, eax
0x1800a8f73  jz      loc_1800A9047
0x1800a8f79  mov     this, [rsp+160h+hkey]; hKey
0x1800a8f7e  lea     rax, [rsp+160h+hkeyCat]
0x1800a8f83  mov     [rsp+160h+lpdwDisposition], r13; lpdwDisposition
0x1800a8f88  lea     rdx, [rbp+60h+wszcatid]; lpSubKey
0x1800a8f8c  mov     [rsp+160h+phkResult], rax; phkResult
0x1800a8f91  xor     r9d, r9d; lpClass
0x1800a8f94  mov     [rsp+160h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1800a8f99  xor     r8d, r8d; Reserved
0x1800a8f9c  mov     [rsp+160h+samDesired], 20006h; samDesired
0x1800a8fa4  mov     [rsp+160h+dwOptions], r13d; dwOptions
0x1800a8fa9  call    cs:__imp_RegCreateKeyExW
0x1800a8faf  test    eax, eax
0x1800a8fb1  jnz     loc_1800A9040
0x1800a8fb7  xor     cCategories, cCategories; Val
0x1800a8fb9  lea     r8d, [rax+64h]; Size
0x1800a8fbd  lea     this, [rsp+160h+wszlcid]; void *
0x1800a8fc2  call    memset_0
0x1800a8fc7  lea     rax, [rsp+160h+wszlcid]
0x1800a8fcc  mov     [rsp+160h+samDesired], 32h ; '2'; cchWideChar
0x1800a8fd4  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800a8fd8  mov     qword ptr [rsp+160h+dwOptions], rax; lpWideCharStr
0x1800a8fdd  lea     rgCategoryInfo, [rsp+160h+szlcid]; lpMultiByteStr
0x1800a8fe2  xor     cCategories, cCategories; dwFlags
0x1800a8fe4  xor     ecx, ecx; CodePage
0x1800a8fe6  call    cs:__imp_MultiByteToWideChar
0x1800a8fec  add     rbx, 14h
0x1800a8ff0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a8ff4  inc     rax
0x1800a8ff7  cmp     [rbx+rax*2], r13w
0x1800a8ffc  jnz     short loc_1800A8FF4
0x1800a8ffe  mov     this, [rsp+160h+hkeyCat]; hKey
0x1800a9003  lea     eax, ds:2[rax*2]
0x1800a900a  mov     [rsp+160h+samDesired], eax; cbData
0x1800a900e  lea     rdx, [rsp+160h+wszlcid]; lpValueName
0x1800a9013  mov     r9d, 1; dwType
0x1800a9019  mov     qword ptr [rsp+160h+dwOptions], rbx; lpData
0x1800a901e  xor     r8d, r8d; Reserved
0x1800a9021  call    cs:__imp_RegSetValueExW
0x1800a9027  mov     this, [rsp+160h+hkeyCat]; hKey
0x1800a902c  mov     ebx, eax
0x1800a902e  call    cs:__imp_RegCloseKey
0x1800a9034  test    ebx, ebx
0x1800a9036  jnz     short loc_1800A9040
0x1800a9038  inc     r14d
0x1800a903b  jmp     loc_1800A8F24
0x1800a9040  mov     esi, 1
0x1800a9045  jmp     short loc_1800A904C
0x1800a9047  mov     esi, 8007000Eh
0x1800a904c  mov     this, [rsp+160h+hkey]; hKey
0x1800a9051  call    cs:__imp_RegCloseKey
0x1800a9057  mov     eax, esi
0x1800a9059  mov     this, [rbp+60h+var_30]
0x1800a905d  xor     this, rsp; StackCookie
0x1800a9060  call    __security_check_cookie
0x1800a9065  lea     r11, [rsp+160h+var_20]
0x1800a906d  mov     rbx, [r11+30h]
0x1800a9071  mov     rsi, [r11+38h]
0x1800a9075  mov     rsp, r11
0x1800a9078  pop     r15
0x1800a907a  pop     r14
0x1800a907c  pop     r13
0x1800a907e  pop     r12
0x1800a9080  pop     rbp
0x1800a9081  retn
```
