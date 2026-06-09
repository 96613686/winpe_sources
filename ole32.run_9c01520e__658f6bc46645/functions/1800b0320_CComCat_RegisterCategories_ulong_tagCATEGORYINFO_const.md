# CComCat::RegisterCategories(ulong,tagCATEGORYINFO * const)

- ea: `0x1800b0320`
- end: `0x1800b056d`
- name: `?RegisterCategories@CComCat@@UEAAJKQEAUtagCATEGORYINFO@@@Z`
- size: `589`
- prototype: `HRESULT __fastcall(CComCat *this, unsigned int cCategories, tagCATEGORYINFO *rgCategoryInfo)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000f660`
- `0x18001d110`
- `0x180046460`
- `0x180047484`
- `0x180072fd8`
- `0x1800b0320`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b03cd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b0475`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b03cd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b0475`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b04f9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b04f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b050c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b0535`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b050c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b0535`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800b04b8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800b04b8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b0431`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b0431`

## string_xrefs

- `0x1800b039a`: `Component Categories`

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
  v6 = 0;
  hkey = 0;
  hkeyCat = 0;
  if ( RegCreateKeyExW(HKEY_CLASSES_ROOT, L"Component Categories", 0, 0, 0, 0x20006u, 0, &hkey, 0) )
    return 1;
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
0x1800b0320  mov     [rsp-8+arg_0], rbx
0x1800b0325  mov     [rsp-8+arg_8], rsi
0x1800b032a  push    rbp
0x1800b032b  push    r12
0x1800b032d  push    r13
0x1800b032f  push    r14
0x1800b0331  push    r15
0x1800b0333  lea     rbp, [rsp-40h]
0x1800b0338  sub     rsp, 140h
0x1800b033f  mov     rax, cs:__security_cookie
0x1800b0346  xor     rax, rsp
0x1800b0349  mov     [rbp+60h+var_30], rax
0x1800b034d  mov     r15d, cCategories
0x1800b0350  mov     r12, rgCategoryInfo
0x1800b0353  mov     cCategories, 68h ; 'h'; cb
0x1800b0358  call    ?IsValidPtrOut@@YAHPEAX_K@Z; IsValidPtrOut(void *,unsigned __int64)
0x1800b035d  xor     r13d, r13d
0x1800b0360  test    eax, eax
0x1800b0362  jnz     short loc_1800B036E
0x1800b0364  mov     eax, 80004003h
0x1800b0369  jmp     loc_1800B0543
0x1800b036e  imul    rdx, r15, 114h; cb
0x1800b0375  mov     this, r12; pv
0x1800b0378  call    ?IsValidReadPtrIn@@YAHPEBX_K@Z; IsValidReadPtrIn(void const *,unsigned __int64)
0x1800b037d  test    eax, eax
0x1800b037f  jnz     short loc_1800B038B
0x1800b0381  mov     eax, 80070057h
0x1800b0386  jmp     loc_1800B0543
0x1800b038b  mov     [rsp+160h+lpdwDisposition], r13; lpdwDisposition
0x1800b0390  lea     rax, [rsp+160h+hkey]
0x1800b0395  mov     [rsp+160h+phkResult], rax; phkResult
0x1800b039a  lea     rdx, aComponentCateg; "Component Categories"
0x1800b03a1  mov     [rsp+160h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1800b03a6  xor     r9d, r9d; lpClass
0x1800b03a9  mov     [rsp+160h+samDesired], 20006h; samDesired
0x1800b03b1  xor     r8d, r8d; Reserved
0x1800b03b4  mov     this, 0FFFFFFFF80000000h; hKey
0x1800b03bb  mov     [rsp+160h+dwOptions], r13d; dwOptions
0x1800b03c0  mov     esi, r13d
0x1800b03c3  mov     [rsp+160h+hkey], r13
0x1800b03c8  mov     [rsp+160h+hkeyCat], r13
0x1800b03cd  call    cs:__imp_RegCreateKeyExW
0x1800b03d4  nop     dword ptr [rax+rax+00h]
0x1800b03d9  test    eax, eax
0x1800b03db  jz      short loc_1800B03E7
0x1800b03dd  mov     eax, 1
0x1800b03e2  jmp     loc_1800B0543
0x1800b03e7  mov     r14d, r13d
0x1800b03ea  cmp     r14d, r15d
0x1800b03ed  jnb     loc_1800B0530
0x1800b03f3  mov     eax, r14d
0x1800b03f6  lea     rgCategoryInfo, aLx; "%lX"
0x1800b03fd  imul    rbx, rax, 114h
0x1800b0404  mov     cCategories, 10h; cchDest
0x1800b0409  lea     this, [rsp+160h+szlcid]; pszDest
0x1800b040e  add     rbx, r12
0x1800b0411  mov     r9d, [rbx+10h]
0x1800b0415  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800b041a  mov     esi, eax
0x1800b041c  test    eax, eax
0x1800b041e  js      loc_1800B0530
0x1800b0424  mov     r8d, 28h ; '('; cchMax
0x1800b042a  lea     rdx, [rbp+60h+wszcatid]; lpsz
0x1800b042e  mov     this, rbx; rguid
0x1800b0431  call    cs:__imp_StringFromGUID2
0x1800b0438  nop     dword ptr [rax+rax+00h]
0x1800b043d  test    eax, eax
0x1800b043f  jz      loc_1800B052B
0x1800b0445  mov     this, [rsp+160h+hkey]; hKey
0x1800b044a  lea     rax, [rsp+160h+hkeyCat]
0x1800b044f  mov     [rsp+160h+lpdwDisposition], r13; lpdwDisposition
0x1800b0454  lea     rdx, [rbp+60h+wszcatid]; lpSubKey
0x1800b0458  mov     [rsp+160h+phkResult], rax; phkResult
0x1800b045d  xor     r9d, r9d; lpClass
0x1800b0460  mov     [rsp+160h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1800b0465  xor     r8d, r8d; Reserved
0x1800b0468  mov     [rsp+160h+samDesired], 20006h; samDesired
0x1800b0470  mov     [rsp+160h+dwOptions], r13d; dwOptions
0x1800b0475  call    cs:__imp_RegCreateKeyExW
0x1800b047c  nop     dword ptr [rax+rax+00h]
0x1800b0481  test    eax, eax
0x1800b0483  jnz     loc_1800B0524
0x1800b0489  xor     cCategories, cCategories; Val
0x1800b048b  lea     r8d, [rax+64h]; Size
0x1800b048f  lea     this, [rsp+160h+wszlcid]; void *
0x1800b0494  call    memset_0
0x1800b0499  lea     rax, [rsp+160h+wszlcid]
0x1800b049e  mov     [rsp+160h+samDesired], 32h ; '2'; cchWideChar
0x1800b04a6  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800b04aa  mov     qword ptr [rsp+160h+dwOptions], rax; lpWideCharStr
0x1800b04af  lea     rgCategoryInfo, [rsp+160h+szlcid]; lpMultiByteStr
0x1800b04b4  xor     cCategories, cCategories; dwFlags
0x1800b04b6  xor     ecx, ecx; CodePage
0x1800b04b8  call    cs:__imp_MultiByteToWideChar
0x1800b04bf  nop     dword ptr [rax+rax+00h]
0x1800b04c4  add     rbx, 14h
0x1800b04c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b04cc  inc     rax
0x1800b04cf  cmp     [rbx+rax*2], r13w
0x1800b04d4  jnz     short loc_1800B04CC
0x1800b04d6  mov     this, [rsp+160h+hkeyCat]; hKey
0x1800b04db  lea     eax, ds:2[rax*2]
0x1800b04e2  mov     [rsp+160h+samDesired], eax; cbData
0x1800b04e6  lea     rdx, [rsp+160h+wszlcid]; lpValueName
0x1800b04eb  mov     r9d, 1; dwType
0x1800b04f1  mov     qword ptr [rsp+160h+dwOptions], rbx; lpData
0x1800b04f6  xor     r8d, r8d; Reserved
0x1800b04f9  call    cs:__imp_RegSetValueExW
0x1800b0500  nop     dword ptr [rax+rax+00h]
0x1800b0505  mov     this, [rsp+160h+hkeyCat]; hKey
0x1800b050a  mov     ebx, eax
0x1800b050c  call    cs:__imp_RegCloseKey
0x1800b0513  nop     dword ptr [rax+rax+00h]
0x1800b0518  test    ebx, ebx
0x1800b051a  jnz     short loc_1800B0524
0x1800b051c  inc     r14d
0x1800b051f  jmp     loc_1800B03EA
0x1800b0524  mov     esi, 1
0x1800b0529  jmp     short loc_1800B0530
0x1800b052b  mov     esi, 8007000Eh
0x1800b0530  mov     this, [rsp+160h+hkey]; hKey
0x1800b0535  call    cs:__imp_RegCloseKey
0x1800b053c  nop     dword ptr [rax+rax+00h]
0x1800b0541  mov     eax, esi
0x1800b0543  mov     this, [rbp+60h+var_30]
0x1800b0547  xor     this, rsp; StackCookie
0x1800b054a  call    __security_check_cookie
0x1800b054f  lea     r11, [rsp+160h+var_20]
0x1800b0557  mov     rbx, [r11+30h]
0x1800b055b  mov     rsi, [r11+38h]
0x1800b055f  mov     rsp, r11
0x1800b0562  pop     r15
0x1800b0564  pop     r14
0x1800b0566  pop     r13
0x1800b0568  pop     r12
0x1800b056a  pop     rbp
0x1800b056b  retn
```
