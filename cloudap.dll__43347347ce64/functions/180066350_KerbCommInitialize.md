# KerbCommInitialize

- ea: `0x180066350`
- end: `0x1800664c4`
- name: `KerbCommInitialize`
- size: `372`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004b1e0`

## callees

- `0x18003dd9c`
- `0x180040024`
- `0x180066350`
- `0x180066f24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180066390`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006642b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180066390`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006642b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800663dd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180066479`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800663dd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180066479`

## pseudocode

```c
__int64 KerbCommInitialize()
{
  LSTATUS v0; // eax
  unsigned int v1; // ebx
  signed int Value; // eax
  __int64 v3; // rcx
  HKEY v4; // rax
  bool v5; // cc
  HKEY hKey; // [rsp+40h] [rbp+10h] BYREF

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System\\Kerberos\\Parameters",
         0,
         0x20019u,
         &hKey);
  v1 = v0;
  if ( (v0 & 0xFFFFFFFD) != 0 )
  {
    if ( v0 > 0 )
      v1 = (unsigned __int16)v0 | 0x80070000;
    goto LABEL_22;
  }
  if ( hKey )
  {
    Value = RegQueryValueExW(hKey, L"SupportedEncryptionTypes", 0, 0, 0, 0);
    if ( Value == 2 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKey,
        0);
    }
    else
    {
      v5 = Value <= 0;
      if ( Value )
        goto LABEL_11;
    }
    v4 = hKey;
    if ( hKey )
    {
LABEL_19:
      if ( (unsigned __int8)KerberosCryptoPolicy::InitializeCiphers(v3, v4) )
        v1 = 0;
      else
        v1 = -2147467259;
      goto LABEL_22;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  Value = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Control\\Lsa\\Kerberos\\Parameters",
            0,
            0x20019u,
            &hKey);
  if ( (Value & 0xFFFFFFFD) == 0 )
  {
    v4 = hKey;
    if ( hKey )
    {
      Value = RegQueryValueExW(hKey, L"SupportedEncryptionTypes", 0, 0, 0, 0);
      if ( Value == 2 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &hKey,
          0);
      }
      else
      {
        v5 = Value <= 0;
        if ( Value )
          goto LABEL_11;
      }
      v4 = hKey;
    }
    goto LABEL_19;
  }
  v5 = Value <= 0;
LABEL_11:
  if ( !v5 )
    Value = (unsigned __int16)Value | 0x80070000;
  v1 = Value;
LABEL_22:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v1;
}

```

## disassembly

```asm
0x180066350  mov     [rsp-8+arg_8], rbx
0x180066355  push    rbp
0x180066356  mov     rbp, rsp
0x180066359  sub     rsp, 30h
0x18006635d  xor     edx, edx
0x18006635f  mov     [rbp+hKey], 0
0x180066367  lea     rcx, [rbp+hKey]
0x18006636b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180066370  lea     rax, [rbp+hKey]
0x180066374  mov     r9d, 20019h; samDesired
0x18006637a  xor     r8d, r8d; ulOptions
0x18006637d  mov     [rsp+30h+phkResult], rax; phkResult
0x180066382  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180066389  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180066390  call    cs:__imp_RegOpenKeyExW
0x180066396  mov     ebx, eax
0x180066398  test    eax, 0FFFFFFFDh
0x18006639d  jz      short loc_1800663B5
0x18006639f  test    eax, eax
0x1800663a1  jle     loc_1800664AE
0x1800663a7  movzx   ebx, ax
0x1800663aa  or      ebx, 80070000h
0x1800663b0  jmp     loc_1800664AE
0x1800663b5  mov     rcx, [rbp+hKey]; hKey
0x1800663b9  test    rcx, rcx
0x1800663bc  jz      short loc_180066400
0x1800663be  mov     [rsp+30h+lpcbData], 0; lpcbData
0x1800663c7  lea     rdx, aSupportedencry; "SupportedEncryptionTypes"
0x1800663ce  xor     r9d, r9d; lpType
0x1800663d1  mov     [rsp+30h+phkResult], 0; lpData
0x1800663da  xor     r8d, r8d; lpReserved
0x1800663dd  call    cs:__imp_RegQueryValueExW
0x1800663e3  cmp     eax, 2
0x1800663e6  jnz     short loc_18006643C
0x1800663e8  xor     edx, edx
0x1800663ea  lea     rcx, [rbp+hKey]
0x1800663ee  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800663f3  mov     rax, [rbp+hKey]
0x1800663f7  test    rax, rax
0x1800663fa  jnz     loc_180066499
0x180066400  xor     edx, edx
0x180066402  lea     rcx, [rbp+hKey]
0x180066406  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18006640b  lea     rax, [rbp+hKey]
0x18006640f  mov     r9d, 20019h; samDesired
0x180066415  xor     r8d, r8d; ulOptions
0x180066418  mov     [rsp+30h+phkResult], rax; phkResult
0x18006641d  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Lsa"...
0x180066424  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006642b  call    cs:__imp_RegOpenKeyExW
0x180066431  test    eax, 0FFFFFFFDh
0x180066436  jz      short loc_18006644E
0x180066438  test    eax, eax
0x18006643a  jmp     short loc_180066440
0x18006643c  test    eax, eax
0x18006643e  jz      short loc_1800663F3
0x180066440  jle     short loc_18006644A
0x180066442  movzx   eax, ax
0x180066445  or      eax, 80070000h
0x18006644a  mov     ebx, eax
0x18006644c  jmp     short loc_1800664AE
0x18006644e  mov     rax, [rbp+hKey]
0x180066452  test    rax, rax
0x180066455  jz      short loc_180066499
0x180066457  mov     [rsp+30h+lpcbData], 0; lpcbData
0x180066460  lea     rdx, aSupportedencry; "SupportedEncryptionTypes"
0x180066467  xor     r9d, r9d; lpType
0x18006646a  mov     [rsp+30h+phkResult], 0; lpData
0x180066473  xor     r8d, r8d; lpReserved
0x180066476  mov     rcx, rax; hKey
0x180066479  call    cs:__imp_RegQueryValueExW
0x18006647f  cmp     eax, 2
0x180066482  jnz     short loc_180066491
0x180066484  xor     edx, edx
0x180066486  lea     rcx, [rbp+hKey]
0x18006648a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18006648f  jmp     short loc_180066495
0x180066491  test    eax, eax
0x180066493  jnz     short loc_180066440
0x180066495  mov     rax, [rbp+hKey]
0x180066499  mov     rdx, rax
0x18006649c  call    ?InitializeCiphers@KerberosCryptoPolicy@@SA_NW4Kerb3961PolicyType@@PEAUHKEY__@@@Z; KerberosCryptoPolicy::InitializeCiphers(Kerb3961PolicyType,HKEY__ *)
0x1800664a1  test    al, al
0x1800664a3  jz      short loc_1800664A9
0x1800664a5  xor     ebx, ebx
0x1800664a7  jmp     short loc_1800664AE
0x1800664a9  mov     ebx, 80004005h
0x1800664ae  lea     rcx, [rbp+hKey]
0x1800664b2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800664b7  mov     eax, ebx
0x1800664b9  mov     rbx, [rsp+30h+arg_8]
0x1800664be  add     rsp, 30h
0x1800664c2  pop     rbp
0x1800664c3  retn
```
