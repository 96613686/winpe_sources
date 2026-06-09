# GetHardwareProfileKey

- ea: `0x18000793c`
- end: `0x180007a50`
- name: `GetHardwareProfileKey`
- size: `276`
- prototype: `__int64 __fastcall(HKEY hKey, PHKEY phkResult)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180007a58`

## callees

- `0x18000793c`
- `0x1800080b0`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007989`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800079cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007a1a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007989`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800079cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007a1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800079da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800079da`

## pseudocode

```c
LSTATUS __fastcall GetHardwareProfileKey(HKEY hKey, PHKEY phkResult)
{
  unsigned int v4; // ebx
  LSTATUS result; // eax
  HKEY hKeya; // [rsp+30h] [rbp-238h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-228h] BYREF

  hKeya = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v4 = 1;
  result = RegOpenKeyExW(hKey, L"Hardware Profiles\\Current", 0, 0xF003Fu, phkResult);
  if ( result )
  {
    while ( 1 )
    {
      StringCchPrintfW(pszDest, 0x104u, L"Hardware Profiles\\%04d", v4);
      if ( RegOpenKeyExW(hKey, pszDest, 0, 0x20019u, &hKeya) )
        break;
      RegCloseKey(hKeya);
      if ( (int)++v4 >= 4 )
        goto LABEL_6;
    }
    --v4;
LABEL_6:
    StringCchPrintfW(pszDest, 0x104u, L"Hardware Profiles\\%04d", v4);
    result = RegOpenKeyExW(hKey, pszDest, 0, 0xF003Fu, phkResult);
    if ( result )
      *phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000793c  mov     [rsp+arg_10], rbx
0x180007941  mov     [rsp+arg_18], rsi
0x180007946  push    rdi
0x180007947  sub     rsp, 260h
0x18000794e  mov     rax, cs:__security_cookie
0x180007955  xor     rax, rsp
0x180007958  mov     [rsp+268h+var_18], rax
0x180007960  mov     rdi, rdx
0x180007963  mov     [rsp+268h+phkResult], rdx; phkResult
0x180007968  lea     rdx, aHardwareProfil; "Hardware Profiles\\Current"
0x18000796f  mov     [rsp+268h+hKey], 0FFFFFFFFFFFFFFFFh
0x180007978  mov     r9d, 0F003Fh; samDesired
0x18000797e  xor     r8d, r8d; ulOptions
0x180007981  mov     rsi, rcx
0x180007984  mov     ebx, 1
0x180007989  call    cs:__imp_RegOpenKeyExW
0x18000798f  test    eax, eax
0x180007991  jz      loc_180007A2B
0x180007997  mov     r9d, ebx
0x18000799a  lea     r8, aHardwareProfil_0; "Hardware Profiles\\%04d"
0x1800079a1  mov     edx, 104h; cchDest
0x1800079a6  lea     rcx, [rsp+268h+pszDest]; pszDest
0x1800079ab  call    StringCchPrintfW
0x1800079b0  lea     rax, [rsp+268h+hKey]
0x1800079b5  mov     r9d, 20019h; samDesired
0x1800079bb  xor     r8d, r8d; ulOptions
0x1800079be  mov     [rsp+268h+phkResult], rax; phkResult
0x1800079c3  lea     rdx, [rsp+268h+pszDest]; lpSubKey
0x1800079c8  mov     rcx, rsi; hKey
0x1800079cb  call    cs:__imp_RegOpenKeyExW
0x1800079d1  test    eax, eax
0x1800079d3  jnz     short loc_1800079E9
0x1800079d5  mov     rcx, [rsp+268h+hKey]; hKey
0x1800079da  call    cs:__imp_RegCloseKey
0x1800079e0  inc     ebx
0x1800079e2  cmp     ebx, 4
0x1800079e5  jl      short loc_180007997
0x1800079e7  jmp     short loc_1800079EB
0x1800079e9  dec     ebx
0x1800079eb  mov     r9d, ebx
0x1800079ee  lea     r8, aHardwareProfil_0; "Hardware Profiles\\%04d"
0x1800079f5  mov     edx, 104h; cchDest
0x1800079fa  lea     rcx, [rsp+268h+pszDest]; pszDest
0x1800079ff  call    StringCchPrintfW
0x180007a04  mov     r9d, 0F003Fh; samDesired
0x180007a0a  mov     [rsp+268h+phkResult], rdi; phkResult
0x180007a0f  xor     r8d, r8d; ulOptions
0x180007a12  lea     rdx, [rsp+268h+pszDest]; lpSubKey
0x180007a17  mov     rcx, rsi; hKey
0x180007a1a  call    cs:__imp_RegOpenKeyExW
0x180007a20  test    eax, eax
0x180007a22  jz      short loc_180007A2B
0x180007a24  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180007a2b  mov     rcx, [rsp+268h+var_18]
0x180007a33  xor     rcx, rsp; StackCookie
0x180007a36  call    __security_check_cookie
0x180007a3b  lea     r11, [rsp+268h+var_8]
0x180007a43  mov     rbx, [r11+20h]
0x180007a47  mov     rsi, [r11+28h]
0x180007a4b  mov     rsp, r11
0x180007a4e  pop     rdi
0x180007a4f  retn
```
