# IsProfileInUse(ushort const *,bool *)

- ea: `0x1800312b4`
- end: `0x1800313dd`
- name: `?IsProfileInUse@@YAJPEBGPEA_N@Z`
- size: `297`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180030008`

## callees

- `0x18000d030`
- `0x18000e1a0`
- `0x1800130d0`
- `0x180013770`
- `0x180030ad0`
- `0x1800312b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800312fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003139a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800312fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003139a`

## string_xrefs

- `0x18003134b`: `onecore\ds\security\gina\profile\profsvc\util.cpp`

## pseudocode

```c
__int64 __fastcall IsProfileInUse(LPCWSTR lpSubKey, bool *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int phkResult; // [rsp+20h] [rbp-30h]
  LPCWSTR lpSubKeya[4]; // [rsp+30h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  HKEY v10; // [rsp+68h] [rbp+18h] BYREF
  HKEY v11; // [rsp+70h] [rbp+20h] BYREF

  *a2 = 0;
  v11 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v11,
    0);
  if ( !RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0x20019u, &v11) )
  {
    *a2 = 1;
LABEL_6:
    v5 = 0;
    goto LABEL_7;
  }
  memset(lpSubKeya, 0, 24);
  v4 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
         lpSubKeya,
         L"%s_Classes",
         lpSubKey);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v10 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v10,
      0);
    *a2 = RegOpenKeyExW(HKEY_USERS, lpSubKeya[0], 0, 0x20019u, &v10) == 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v10);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKeya);
    goto LABEL_6;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x31C,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
    (const char *)(unsigned int)v4,
    phkResult);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKeya);
LABEL_7:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v11);
  return v5;
}

```

## disassembly

```asm
0x1800312b4  mov     [rsp-8+arg_0], rbx
0x1800312b9  mov     [rsp-8+arg_18], rdi
0x1800312be  push    rbp
0x1800312bf  mov     rbp, rsp
0x1800312c2  sub     rsp, 50h
0x1800312c6  mov     rdi, rdx
0x1800312c9  mov     byte ptr [rdx], 0
0x1800312cc  mov     rbx, rcx
0x1800312cf  mov     [rbp+arg_10], 0
0x1800312d7  xor     edx, edx
0x1800312d9  lea     rcx, [rbp+arg_10]
0x1800312dd  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800312e2  lea     rax, [rbp+arg_10]
0x1800312e6  mov     r9d, 20019h; samDesired
0x1800312ec  xor     r8d, r8d; ulOptions
0x1800312ef  mov     qword ptr [rsp+50h+phkResult], rax; int
0x1800312f4  mov     rdx, rbx; lpSubKey
0x1800312f7  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800312fe  call    cs:__imp_RegOpenKeyExW
0x180031305  nop     dword ptr [rax+rax+00h]
0x18003130a  test    eax, eax
0x18003130c  jnz     short loc_180031316
0x18003130e  mov     byte ptr [rdi], 1
0x180031311  jmp     loc_1800313BF
0x180031316  mov     r8, rbx
0x180031319  mov     [rbp+lpSubKey], 0
0x180031321  lea     rdx, aSClasses; "%s_Classes"
0x180031328  mov     [rbp+var_18], 0
0x180031330  lea     rcx, [rbp+lpSubKey]
0x180031334  mov     [rbp+var_10], 0
0x18003133c  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180031341  mov     ebx, eax
0x180031343  test    eax, eax
0x180031345  jns     short loc_18003136A
0x180031347  mov     rcx, [rbp+8]; this
0x18003134b  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031352  mov     r9d, eax; char *
0x180031355  mov     edx, 31Ch; void *
0x18003135a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003135f  lea     rcx, [rbp+lpSubKey]
0x180031363  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180031368  jmp     short loc_1800313C1
0x18003136a  xor     edx, edx
0x18003136c  mov     [rbp+arg_8], 0
0x180031374  lea     rcx, [rbp+arg_8]
0x180031378  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003137d  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180031381  lea     rax, [rbp+arg_8]
0x180031385  mov     r9d, 20019h; samDesired
0x18003138b  mov     qword ptr [rsp+50h+phkResult], rax; phkResult
0x180031390  xor     r8d, r8d; ulOptions
0x180031393  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18003139a  call    cs:__imp_RegOpenKeyExW
0x1800313a1  nop     dword ptr [rax+rax+00h]
0x1800313a6  test    eax, eax
0x1800313a8  lea     rcx, [rbp+arg_8]
0x1800313ac  setz    al
0x1800313af  mov     [rdi], al
0x1800313b1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800313b6  lea     rcx, [rbp+lpSubKey]
0x1800313ba  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800313bf  xor     ebx, ebx
0x1800313c1  lea     rcx, [rbp+arg_10]
0x1800313c5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800313ca  mov     rdi, [rsp+50h+arg_18]
0x1800313cf  mov     eax, ebx
0x1800313d1  mov     rbx, [rsp+50h+arg_0]
0x1800313d6  add     rsp, 50h
0x1800313da  pop     rbp
0x1800313db  retn
```
