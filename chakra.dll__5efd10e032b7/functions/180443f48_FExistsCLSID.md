# FExistsCLSID

- ea: `0x180443f48`
- end: `0x18044402c`
- name: `FExistsCLSID`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1804446cc`

## callees

- `0x180443f48`
- `0x1805a9e80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180443fee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180444004`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180443fee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180444004`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180443fa8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180443fd9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180443fa8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180443fd9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180443f7b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180443f7b`

## string_xrefs

- `0x180443f9a`: `CLSID`

## pseudocode

```c
__int64 __fastcall FExistsCLSID(const GUID *a1)
{
  unsigned int v1; // ebx
  HKEY hKey; // [rsp+30h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-70h] BYREF
  WCHAR SubKey[40]; // [rsp+40h] [rbp-68h] BYREF

  v1 = 0;
  hKey = 0;
  phkResult = 0;
  StringFromGUID2(a1, SubKey, 39);
  if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0x20019u, &hKey) )
    return 0;
  if ( !RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &phkResult) )
  {
    RegCloseKey(phkResult);
    v1 = 1;
  }
  RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x180443f48  mov     r11, rsp
0x180443f4b  mov     [r11+8], rcx
0x180443f4f  push    rbx
0x180443f50  sub     rsp, 0A0h
0x180443f57  mov     rax, cs:__security_cookie
0x180443f5e  xor     rax, rsp
0x180443f61  mov     [rsp+0A8h+var_18], rax
0x180443f69  xor     ebx, ebx
0x180443f6b  lea     rdx, [r11-68h]; lpsz
0x180443f6f  mov     [r11-78h], rbx
0x180443f73  mov     [r11-70h], rbx
0x180443f77  lea     r8d, [rbx+27h]; cchMax
0x180443f7b  call    cs:__imp_StringFromGUID2
0x180443f82  nop     dword ptr [rax+rax+00h]
0x180443f87  lea     rax, [rsp+0A8h+hKey]
0x180443f8c  mov     r9d, 20019h; samDesired
0x180443f92  xor     r8d, r8d; ulOptions
0x180443f95  mov     [rsp+0A8h+phkResult], rax; phkResult
0x180443f9a  lea     rdx, aClsid; "CLSID"
0x180443fa1  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180443fa8  call    cs:__imp_RegOpenKeyExW
0x180443faf  nop     dword ptr [rax+rax+00h]
0x180443fb4  test    eax, eax
0x180443fb6  jz      short loc_180443FBC
0x180443fb8  xor     eax, eax
0x180443fba  jmp     short loc_180444012
0x180443fbc  mov     rcx, [rsp+0A8h+hKey]; hKey
0x180443fc1  lea     rax, [rsp+0A8h+var_70]
0x180443fc6  mov     r9d, 20019h; samDesired
0x180443fcc  mov     [rsp+0A8h+phkResult], rax; phkResult
0x180443fd1  xor     r8d, r8d; ulOptions
0x180443fd4  lea     rdx, [rsp+0A8h+SubKey]; lpSubKey
0x180443fd9  call    cs:__imp_RegOpenKeyExW
0x180443fe0  nop     dword ptr [rax+rax+00h]
0x180443fe5  test    eax, eax
0x180443fe7  jnz     short loc_180443FFF
0x180443fe9  mov     rcx, [rsp+0A8h+var_70]; hKey
0x180443fee  call    cs:__imp_RegCloseKey
0x180443ff5  nop     dword ptr [rax+rax+00h]
0x180443ffa  mov     ebx, 1
0x180443fff  mov     rcx, [rsp+0A8h+hKey]; hKey
0x180444004  call    cs:__imp_RegCloseKey
0x18044400b  nop     dword ptr [rax+rax+00h]
0x180444010  mov     eax, ebx
0x180444012  mov     rcx, [rsp+0A8h+var_18]
0x18044401a  xor     rcx, rsp; StackCookie
0x18044401d  call    __security_check_cookie
0x180444022  add     rsp, 0A0h
0x180444029  pop     rbx
0x18044402a  retn
```
