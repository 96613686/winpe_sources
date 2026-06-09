# GetGuidFromRegistry

- ea: `0x18006a86c`
- end: `0x18006a943`
- name: `GetGuidFromRegistry`
- size: `215`
- prototype: `__int64 __fastcall(LPCOLESTR lpsz)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006a978`

## callees

- `0x18006a86c`
- `0x1800cca00`

## import_xrefs

- `SHLWAPI!SHQueryValueExW` at `0x18006a8ed`
- `SHLWAPI!SHQueryValueExW` at `0x18006a8ed`
- `ADVAPI32!RegCloseKey` at `0x18006a91d`
- `ADVAPI32!RegCloseKey` at `0x18006a91d`
- `ADVAPI32!RegOpenKeyExW` at `0x18006a8b9`
- `ADVAPI32!RegOpenKeyExW` at `0x18006a8b9`
- `ole32!CLSIDFromString` at `0x18006a90a`
- `ole32!CLSIDFromString` at `0x18006a90a`

## pseudocode

```c
__int64 __fastcall GetGuidFromRegistry(OLECHAR *lpsz)
{
  unsigned int v2; // ebx
  DWORD pdwType; // [rsp+30h] [rbp-30h] BYREF
  DWORD pcbData; // [rsp+34h] [rbp-2Ch] BYREF
  HKEY hkey; // [rsp+38h] [rbp-28h] BYREF
  CLSID pclsid; // [rsp+40h] [rbp-20h] BYREF

  hkey = 0;
  pclsid = 0;
  if ( RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows Mail", 0, 1u, &hkey) )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    pdwType = 0;
    pcbData = 78;
    if ( !SHQueryValueExW(hkey, L"mhtml guid", 0, &pdwType, lpsz, &pcbData) && pdwType == 1 && pcbData == 78 )
      v2 = CLSIDFromString(lpsz, &pclsid);
    else
      v2 = -2147467259;
    RegCloseKey(hkey);
  }
  return v2;
}

```

## disassembly

```asm
0x18006a86c  mov     [rsp-8+arg_8], rbx
0x18006a871  push    rbp
0x18006a872  mov     rbp, rsp
0x18006a875  sub     rsp, 60h
0x18006a879  mov     rax, cs:__security_cookie
0x18006a880  xor     rax, rsp
0x18006a883  mov     [rbp+var_10], rax
0x18006a887  mov     rbx, rcx
0x18006a88a  mov     [rbp+hkey], 0
0x18006a892  xorps   xmm0, xmm0
0x18006a895  lea     rax, [rbp+hkey]
0x18006a899  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18006a8a0  mov     [rsp+60h+phkResult], rax; phkResult
0x18006a8a5  mov     r9d, 1; samDesired
0x18006a8ab  lea     rdx, c_szwRegFlat; "Software\\Microsoft\\Windows Mail"
0x18006a8b2  xor     r8d, r8d; ulOptions
0x18006a8b5  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x18006a8b9  call    cs:__imp_RegOpenKeyExW
0x18006a8bf  test    eax, eax
0x18006a8c1  jnz     short loc_18006A925
0x18006a8c3  mov     rcx, [rbp+hkey]; hkey
0x18006a8c7  lea     r9, [rbp+pdwType]; pdwType
0x18006a8cb  mov     [rbp+pdwType], eax
0x18006a8ce  lea     rdx, aMhtmlGuid; "mhtml guid"
0x18006a8d5  lea     rax, [rbp+var_2C]
0x18006a8d9  mov     [rbp+var_2C], 4Eh ; 'N'
0x18006a8e0  mov     [rsp+60h+pcbData], rax; pcbData
0x18006a8e5  xor     r8d, r8d; pdwReserved
0x18006a8e8  mov     [rsp+60h+phkResult], rbx; pvData
0x18006a8ed  call    cs:__imp_SHQueryValueExW
0x18006a8f3  test    eax, eax
0x18006a8f5  jnz     short loc_18006A914
0x18006a8f7  cmp     [rbp+pdwType], 1
0x18006a8fb  jnz     short loc_18006A914
0x18006a8fd  cmp     [rbp+var_2C], 4Eh ; 'N'
0x18006a901  jnz     short loc_18006A914
0x18006a903  lea     rdx, [rbp+pclsid]; pclsid
0x18006a907  mov     rcx, rbx; lpsz
0x18006a90a  call    cs:__imp_CLSIDFromString
0x18006a910  mov     ebx, eax
0x18006a912  jmp     short loc_18006A919
0x18006a914  mov     ebx, 80004005h
0x18006a919  mov     rcx, [rbp+hkey]; hKey
0x18006a91d  call    cs:__imp_RegCloseKey
0x18006a923  jmp     short loc_18006A92A
0x18006a925  mov     ebx, 80004005h
0x18006a92a  mov     eax, ebx
0x18006a92c  mov     rcx, [rbp+var_10]
0x18006a930  xor     rcx, rsp; StackCookie
0x18006a933  call    __security_check_cookie
0x18006a938  mov     rbx, [rsp+60h+arg_8]
0x18006a93d  add     rsp, 60h
0x18006a941  pop     rbp
0x18006a942  retn
```
