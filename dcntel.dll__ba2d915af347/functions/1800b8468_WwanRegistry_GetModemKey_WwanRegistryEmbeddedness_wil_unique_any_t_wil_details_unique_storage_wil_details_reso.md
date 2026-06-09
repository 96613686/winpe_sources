# WwanRegistry::GetModemKey(WwanRegistryEmbeddedness,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)

- ea: `0x1800b8468`
- end: `0x1800b85ef`
- name: `?GetModemKey@WwanRegistry@@CA_NW4WwanRegistryEmbeddedness@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `391`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800b7a90`
- `0x1800b7db0`
- `0x1800b8600`
- `0x1800b8690`
- `0x1800b88e0`
- `0x1800b8970`

## callees

- `0x180008dc0`
- `0x1800b79f0`
- `0x1800b8468`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b84e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b84e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b84d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b84d4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800b8590`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800b8590`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b84df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b85a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b85e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b84df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b85a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b85e5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b854e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b854e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b8508`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b8508`

## pseudocode

```c
char __fastcall WwanRegistry::GetModemKey(int a1, HKEY *a2)
{
  DWORD v4; // r14d
  DWORD i; // edx
  HKEY v6; // rdi
  DWORD LastError; // ebx
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  int pvData; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD pcbData[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  cchName = 260;
  if ( (unsigned __int8)WwanRegistry::GetBaseKey(&hKey) )
  {
    v4 = 0;
    for ( i = 0; !RegEnumKeyExW(hKey, i, SubKey, &cchName, 0, 0, 0, 0); i = v4 )
    {
      v6 = *a2;
      if ( *a2 )
      {
        LastError = GetLastError();
        RegCloseKey(v6);
        SetLastError(LastError);
      }
      *a2 = 0;
      if ( RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, a2) )
        break;
      pvData = 0;
      pcbData[0] = 4;
      if ( RegGetValueW(*a2, 0, L"Embeddedness", 0x18u, 0, &pvData, pcbData) )
        break;
      if ( pvData == a1 )
      {
        if ( hKey )
          RegCloseKey(hKey);
        return 1;
      }
      ++v4;
      cchName = 260;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1800b8468  mov     [rsp-8+arg_0], rbx
0x1800b846d  mov     [rsp-8+arg_10], rsi
0x1800b8472  push    rbp
0x1800b8473  push    rdi
0x1800b8474  push    r12
0x1800b8476  push    r14
0x1800b8478  push    r15
0x1800b847a  lea     rbp, [rsp-180h]
0x1800b8482  sub     rsp, 280h
0x1800b8489  mov     rax, cs:__security_cookie
0x1800b8490  xor     rax, rsp
0x1800b8493  mov     [rbp+1A0h+var_30], rax
0x1800b849a  mov     rsi, rdx
0x1800b849d  mov     r15d, ecx
0x1800b84a0  xor     r12d, r12d
0x1800b84a3  mov     [rsp+2A0h+hKey], r12
0x1800b84a8  mov     [rsp+2A0h+cchName], 104h
0x1800b84b0  lea     rcx, [rsp+2A0h+hKey]; phkResult
0x1800b84b5  call    ?GetBaseKey@WwanRegistry@@CA_NAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; WwanRegistry::GetBaseKey(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)
0x1800b84ba  test    al, al
0x1800b84bc  jz      loc_1800B859E
0x1800b84c2  mov     r14d, r12d
0x1800b84c5  xor     edx, edx
0x1800b84c7  jmp     loc_1800B856D
0x1800b84cc  mov     rdi, [rsi]
0x1800b84cf  test    rdi, rdi
0x1800b84d2  jz      short loc_1800B84ED
0x1800b84d4  call    cs:__imp_GetLastError
0x1800b84da  mov     ebx, eax
0x1800b84dc  mov     rcx, rdi; hKey
0x1800b84df  call    cs:__imp_RegCloseKey
0x1800b84e5  mov     ecx, ebx; dwErrCode
0x1800b84e7  call    cs:__imp_SetLastError
0x1800b84ed  mov     [rsi], r12
0x1800b84f0  mov     [rsp+2A0h+phkResult], rsi; phkResult
0x1800b84f5  mov     r9d, 20019h; samDesired
0x1800b84fb  xor     r8d, r8d; ulOptions
0x1800b84fe  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x1800b8503  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800b8508  call    cs:__imp_RegOpenKeyExW
0x1800b850e  test    eax, eax
0x1800b8510  jnz     loc_1800B859E
0x1800b8516  mov     [rsp+2A0h+var_254], r12d
0x1800b851b  mov     [rsp+2A0h+var_250], 4
0x1800b8523  lea     rax, [rsp+2A0h+var_250]
0x1800b8528  mov     [rsp+2A0h+pcbData], rax; pcbData
0x1800b852d  lea     rax, [rsp+2A0h+var_254]
0x1800b8532  mov     [rsp+2A0h+pvData], rax; pvData
0x1800b8537  mov     [rsp+2A0h+phkResult], r12; pdwType
0x1800b853c  mov     r9d, 18h; dwFlags
0x1800b8542  lea     r8, aEmbeddedness; "Embeddedness"
0x1800b8549  xor     edx, edx; lpSubKey
0x1800b854b  mov     rcx, [rsi]; hkey
0x1800b854e  call    cs:__imp_RegGetValueW
0x1800b8554  test    eax, eax
0x1800b8556  jnz     short loc_1800B859E
0x1800b8558  cmp     [rsp+2A0h+var_254], r15d
0x1800b855d  jz      short loc_1800B85DB
0x1800b855f  inc     r14d
0x1800b8562  mov     [rsp+2A0h+cchName], 104h
0x1800b856a  mov     edx, r14d; dwIndex
0x1800b856d  mov     [rsp+2A0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800b8572  mov     [rsp+2A0h+pcbData], r12; lpcchClass
0x1800b8577  mov     [rsp+2A0h+pvData], r12; lpClass
0x1800b857c  mov     [rsp+2A0h+phkResult], r12; lpReserved
0x1800b8581  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x1800b8586  lea     r8, [rsp+2A0h+SubKey]; lpName
0x1800b858b  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800b8590  call    cs:__imp_RegEnumKeyExW
0x1800b8596  test    eax, eax
0x1800b8598  jz      loc_1800B84CC
0x1800b859e  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800b85a3  test    rcx, rcx
0x1800b85a6  jz      short loc_1800B85AE
0x1800b85a8  call    cs:__imp_RegCloseKey
0x1800b85ae  xor     al, al
0x1800b85b0  mov     rcx, [rbp+1A0h+var_30]
0x1800b85b7  xor     rcx, rsp; StackCookie
0x1800b85ba  call    __security_check_cookie
0x1800b85bf  lea     r11, [rsp+2A0h+var_20]
0x1800b85c7  mov     rbx, [r11+30h]
0x1800b85cb  mov     rsi, [r11+40h]
0x1800b85cf  mov     rsp, r11
0x1800b85d2  pop     r15
0x1800b85d4  pop     r14
0x1800b85d6  pop     r12
0x1800b85d8  pop     rdi
0x1800b85d9  pop     rbp
0x1800b85da  retn
0x1800b85db  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800b85e0  test    rcx, rcx
0x1800b85e3  jz      short loc_1800B85EB
0x1800b85e5  call    cs:__imp_RegCloseKey
0x1800b85eb  mov     al, 1
0x1800b85ed  jmp     short loc_1800B85B0
```
