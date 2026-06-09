# _lambda_c6c19a4c9de569e7370a7344dfab68e1_::operator()

- ea: `0x180027fc8`
- end: `0x180028123`
- name: `_lambda_c6c19a4c9de569e7370a7344dfab68e1_::operator()`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800817a0`

## callees

- `0x1800108cc`
- `0x180027fc8`
- `0x18002812c`
- `0x180081770`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800280c2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800280c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002802d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028087`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800280ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028112`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002802d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028087`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800280ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028112`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002805d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002805d`

## string_xrefs

- `0x180027ff9`: `Configs`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_c6c19a4c9de569e7370a7344dfab68e1_::operator()(_BYTE **a1)
{
  unsigned int v2; // ebx
  HKEY *phkResult; // rax
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  LPCWSTR lpSubKey[4]; // [rsp+30h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+20h] BYREF
  DWORD Type; // [rsp+78h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+30h] BYREF

  hKey = 0;
  memset(lpSubKey, 0, 24);
  v2 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         lpSubKey,
         L"%s\\%s",
         *((_QWORD *)*a1 + 1),
         L"Configs");
  if ( (v2 & 0x80000000) != 0 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
    if ( hKey )
      RegCloseKey(hKey);
    return v2;
  }
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x20019u, phkResult);
  v2 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v2 = (unsigned __int16)v5 | 0x80070000;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
    if ( hKey )
      RegCloseKey(hKey);
    return v2;
  }
  Type = 0;
  cbData = 0;
  v6 = RegQueryValueExW(hKey, L"GlobalProfileId", 0, &Type, 0, &cbData);
  v2 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v2 = (unsigned __int16)v6 | 0x80070000;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
    if ( hKey )
      RegCloseKey(hKey);
    return v2;
  }
  *a1[1] = 1;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180027fc8  push    rbp
0x180027fca  push    rbx
0x180027fcb  push    rdi
0x180027fcc  mov     rbp, rsp
0x180027fcf  sub     rsp, 50h
0x180027fd3  mov     rdi, rcx
0x180027fd6  mov     [rbp+hKey], 0
0x180027fde  mov     [rbp+lpSubKey], 0
0x180027fe6  mov     [rbp+var_18], 0
0x180027fee  mov     [rbp+var_10], 0
0x180027ff6  mov     r8, [rcx]
0x180027ff9  lea     r9, aConfigs; "Configs"
0x180028000  mov     r8, [r8+8]
0x180028004  lea     rdx, aSS; "%s\\%s"
0x18002800b  lea     rcx, [rbp+lpSubKey]
0x18002800f  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180028014  mov     ebx, eax
0x180028016  test    eax, eax
0x180028018  jns     short loc_18002803B
0x18002801a  lea     rcx, [rbp+lpSubKey]
0x18002801e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180028023  nop
0x180028024  mov     rcx, [rbp+hKey]; hKey
0x180028028  test    rcx, rcx
0x18002802b  jz      short loc_180028034
0x18002802d  call    cs:__imp_RegCloseKey
0x180028033  nop
0x180028034  mov     eax, ebx
0x180028036  jmp     loc_18002811B
0x18002803b  lea     rcx, [rbp+hKey]
0x18002803f  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180028044  mov     [rsp+50h+phkResult], rax; phkResult
0x180028049  mov     r9d, 20019h; samDesired
0x18002804f  xor     r8d, r8d; ulOptions
0x180028052  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180028056  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002805d  call    cs:__imp_RegOpenKeyExW
0x180028063  mov     ebx, eax
0x180028065  test    eax, eax
0x180028067  jz      short loc_180028090
0x180028069  jle     short loc_180028074
0x18002806b  movzx   ebx, ax
0x18002806e  or      ebx, 80070000h
0x180028074  lea     rcx, [rbp+lpSubKey]
0x180028078  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002807d  nop
0x18002807e  mov     rcx, [rbp+hKey]; hKey
0x180028082  test    rcx, rcx
0x180028085  jz      short loc_18002808E
0x180028087  call    cs:__imp_RegCloseKey
0x18002808d  nop
0x18002808e  jmp     short loc_180028034
0x180028090  mov     [rbp+Type], 0
0x180028097  mov     [rbp+cbData], 0
0x18002809e  lea     rax, [rbp+cbData]
0x1800280a2  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800280a7  mov     [rsp+50h+phkResult], 0; lpData
0x1800280b0  lea     r9, [rbp+Type]; lpType
0x1800280b4  xor     r8d, r8d; lpReserved
0x1800280b7  lea     rdx, aGlobalprofilei; "GlobalProfileId"
0x1800280be  mov     rcx, [rbp+hKey]; hKey
0x1800280c2  call    cs:__imp_RegQueryValueExW
0x1800280c8  mov     ebx, eax
0x1800280ca  test    eax, eax
0x1800280cc  jz      short loc_1800280F8
0x1800280ce  jle     short loc_1800280D9
0x1800280d0  movzx   ebx, ax
0x1800280d3  or      ebx, 80070000h
0x1800280d9  lea     rcx, [rbp+lpSubKey]
0x1800280dd  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800280e2  nop
0x1800280e3  mov     rcx, [rbp+hKey]; hKey
0x1800280e7  test    rcx, rcx
0x1800280ea  jz      short loc_1800280F3
0x1800280ec  call    cs:__imp_RegCloseKey
0x1800280f2  nop
0x1800280f3  jmp     loc_180028034
0x1800280f8  mov     rax, [rdi+8]
0x1800280fc  mov     byte ptr [rax], 1
0x1800280ff  lea     rcx, [rbp+lpSubKey]
0x180028103  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180028108  nop
0x180028109  mov     rcx, [rbp+hKey]; hKey
0x18002810d  test    rcx, rcx
0x180028110  jz      short loc_180028119
0x180028112  call    cs:__imp_RegCloseKey
0x180028118  nop
0x180028119  xor     eax, eax
0x18002811b  add     rsp, 50h
0x18002811f  pop     rdi
0x180028120  pop     rbx
0x180028121  pop     rbp
0x180028122  retn
```
