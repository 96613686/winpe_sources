# FExistsCLSID

- ea: `0x1801dcf20`
- end: `0x1801dcfe5`
- name: `FExistsCLSID`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801dd6b4`

## callees

- `0x1801dcf20`
- `0x180341dd0`

## import_xrefs

- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1801dcfb4`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1801dcfc4`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1801dcfb4`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1801dcfc4`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1801dcf7a`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1801dcfa5`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1801dcf7a`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1801dcfa5`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x1801dcf53`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x1801dcf53`

## string_xrefs

- `0x1801dcf6c`: `CLSID`

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
0x1801dcf20  mov     r11, rsp
0x1801dcf23  mov     [r11+8], rcx
0x1801dcf27  push    rbx
0x1801dcf28  sub     rsp, 0A0h
0x1801dcf2f  mov     rax, cs:__security_cookie
0x1801dcf36  xor     rax, rsp
0x1801dcf39  mov     [rsp+0A8h+var_18], rax
0x1801dcf41  xor     ebx, ebx
0x1801dcf43  lea     rdx, [r11-68h]; lpsz
0x1801dcf47  mov     [r11-78h], rbx
0x1801dcf4b  mov     [r11-70h], rbx
0x1801dcf4f  lea     r8d, [rbx+27h]; cchMax
0x1801dcf53  call    cs:__imp_StringFromGUID2
0x1801dcf59  lea     rax, [rsp+0A8h+hKey]
0x1801dcf5e  mov     r9d, 20019h; samDesired
0x1801dcf64  xor     r8d, r8d; ulOptions
0x1801dcf67  mov     [rsp+0A8h+phkResult], rax; phkResult
0x1801dcf6c  lea     rdx, aClsid; "CLSID"
0x1801dcf73  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1801dcf7a  call    cs:__imp_RegOpenKeyExW
0x1801dcf80  test    eax, eax
0x1801dcf82  jz      short loc_1801DCF88
0x1801dcf84  xor     eax, eax
0x1801dcf86  jmp     short loc_1801DCFCC
0x1801dcf88  mov     rcx, [rsp+0A8h+hKey]; hKey
0x1801dcf8d  lea     rax, [rsp+0A8h+var_70]
0x1801dcf92  mov     r9d, 20019h; samDesired
0x1801dcf98  mov     [rsp+0A8h+phkResult], rax; phkResult
0x1801dcf9d  xor     r8d, r8d; ulOptions
0x1801dcfa0  lea     rdx, [rsp+0A8h+SubKey]; lpSubKey
0x1801dcfa5  call    cs:__imp_RegOpenKeyExW
0x1801dcfab  test    eax, eax
0x1801dcfad  jnz     short loc_1801DCFBF
0x1801dcfaf  mov     rcx, [rsp+0A8h+var_70]; hKey
0x1801dcfb4  call    cs:__imp_RegCloseKey
0x1801dcfba  mov     ebx, 1
0x1801dcfbf  mov     rcx, [rsp+0A8h+hKey]; hKey
0x1801dcfc4  call    cs:__imp_RegCloseKey
0x1801dcfca  mov     eax, ebx
0x1801dcfcc  mov     rcx, [rsp+0A8h+var_18]
0x1801dcfd4  xor     rcx, rsp; StackCookie
0x1801dcfd7  call    __security_check_cookie
0x1801dcfdc  add     rsp, 0A0h
0x1801dcfe3  pop     rbx
0x1801dcfe4  retn
```
