# IsProfileInUse(ushort const *,bool *)

- ea: `0x180031320`
- end: `0x180031457`
- name: `?IsProfileInUse@@YAJPEBGPEA_N@Z`
- size: `311`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f89c`

## callees

- `0x180010f30`
- `0x1800111a0`
- `0x18001f060`
- `0x18002d2d8`
- `0x180031320`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003136a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031411`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003136a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031411`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800313d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031427`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003143f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800313d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031427`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003143f`

## string_xrefs

- `0x1800313b1`: `onecore\ds\security\gina\profile\profsvc\util.cpp`

## pseudocode

```c
__int64 __fastcall IsProfileInUse(LPCWSTR lpSubKey, bool *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  LSTATUS v7; // eax
  HKEY v8; // rcx
  int phkResult; // [rsp+20h] [rbp-30h]
  LPCWSTR lpSubKeya[4]; // [rsp+30h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  HKEY hKey; // [rsp+68h] [rbp+18h] BYREF
  HKEY v13; // [rsp+70h] [rbp+20h] BYREF

  *a2 = 0;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  if ( !RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0x20019u, &hKey) )
  {
    *a2 = 1;
LABEL_10:
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  memset(lpSubKeya, 0, 24);
  v4 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
         lpSubKeya,
         L"%s_Classes",
         lpSubKey);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v13 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v13,
      0);
    v7 = RegOpenKeyExW(HKEY_USERS, lpSubKeya[0], 0, 0x20019u, &v13);
    v8 = v13;
    *a2 = v7 == 0;
    if ( v8 )
      RegCloseKey(v8);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpSubKeya);
    goto LABEL_10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x31C,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
    (const char *)(unsigned int)v4,
    phkResult);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpSubKeya);
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x180031320  mov     [rsp-8+arg_0], rbx
0x180031325  mov     [rsp-8+arg_18], rdi
0x18003132a  push    rbp
0x18003132b  mov     rbp, rsp
0x18003132e  sub     rsp, 50h
0x180031332  mov     rdi, rdx
0x180031335  mov     byte ptr [rdx], 0
0x180031338  mov     rbx, rcx
0x18003133b  mov     [rbp+hKey], 0
0x180031343  xor     edx, edx
0x180031345  lea     rcx, [rbp+hKey]
0x180031349  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003134e  lea     rax, [rbp+hKey]
0x180031352  mov     r9d, 20019h; samDesired
0x180031358  xor     r8d, r8d; ulOptions
0x18003135b  mov     qword ptr [rsp+50h+phkResult], rax; int
0x180031360  mov     rdx, rbx; lpSubKey
0x180031363  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18003136a  call    cs:__imp_RegOpenKeyExW
0x180031370  test    eax, eax
0x180031372  jnz     short loc_18003137C
0x180031374  mov     byte ptr [rdi], 1
0x180031377  jmp     loc_180031436
0x18003137c  mov     r8, rbx
0x18003137f  mov     [rbp+lpSubKey], 0
0x180031387  lea     rdx, aSClasses; "%s_Classes"
0x18003138e  mov     [rbp+var_18], 0
0x180031396  lea     rcx, [rbp+lpSubKey]
0x18003139a  mov     [rbp+var_10], 0
0x1800313a2  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800313a7  mov     ebx, eax
0x1800313a9  test    eax, eax
0x1800313ab  jns     short loc_1800313E1
0x1800313ad  mov     rcx, [rbp+8]; this
0x1800313b1  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800313b8  mov     r9d, eax; char *
0x1800313bb  mov     edx, 31Ch; void *
0x1800313c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800313c5  lea     rcx, [rbp+lpSubKey]
0x1800313c9  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800313ce  mov     rcx, [rbp+hKey]; hKey
0x1800313d2  test    rcx, rcx
0x1800313d5  jz      short loc_1800313DD
0x1800313d7  call    cs:__imp_RegCloseKey
0x1800313dd  mov     eax, ebx
0x1800313df  jmp     short loc_180031447
0x1800313e1  xor     edx, edx
0x1800313e3  mov     [rbp+arg_10], 0
0x1800313eb  lea     rcx, [rbp+arg_10]
0x1800313ef  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800313f4  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800313f8  lea     rax, [rbp+arg_10]
0x1800313fc  mov     r9d, 20019h; samDesired
0x180031402  mov     qword ptr [rsp+50h+phkResult], rax; phkResult
0x180031407  xor     r8d, r8d; ulOptions
0x18003140a  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180031411  call    cs:__imp_RegOpenKeyExW
0x180031417  mov     rcx, [rbp+arg_10]; hKey
0x18003141b  test    eax, eax
0x18003141d  setz    al
0x180031420  mov     [rdi], al
0x180031422  test    rcx, rcx
0x180031425  jz      short loc_18003142D
0x180031427  call    cs:__imp_RegCloseKey
0x18003142d  lea     rcx, [rbp+lpSubKey]
0x180031431  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180031436  mov     rcx, [rbp+hKey]; hKey
0x18003143a  test    rcx, rcx
0x18003143d  jz      short loc_180031445
0x18003143f  call    cs:__imp_RegCloseKey
0x180031445  xor     eax, eax
0x180031447  mov     rbx, [rsp+50h+arg_0]
0x18003144c  mov     rdi, [rsp+50h+arg_18]
0x180031451  add     rsp, 50h
0x180031455  pop     rbp
0x180031456  retn
```
