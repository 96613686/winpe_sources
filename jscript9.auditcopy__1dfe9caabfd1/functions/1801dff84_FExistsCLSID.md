# FExistsCLSID

- ea: `0x1801dff84`
- end: `0x1801e0068`
- name: `FExistsCLSID`
- size: `228`
- prototype: `__int64 __fastcall(const GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801e07d4`

## callees

- `0x1801dff84`
- `0x1803481f0`

## import_xrefs

- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1801e002a`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1801e0040`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1801e002a`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1801e0040`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1801dffe4`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1801e0015`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1801dffe4`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1801e0015`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x1801dffb7`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x1801dffb7`

## string_xrefs

- `0x1801dffd6`: `CLSID`

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
0x1801dff84  mov     r11, rsp
0x1801dff87  mov     [r11+8], rcx
0x1801dff8b  push    rbx
0x1801dff8c  sub     rsp, 0A0h
0x1801dff93  mov     rax, cs:__security_cookie
0x1801dff9a  xor     rax, rsp
0x1801dff9d  mov     [rsp+0A8h+var_18], rax
0x1801dffa5  xor     ebx, ebx
0x1801dffa7  lea     rdx, [r11-68h]; lpsz
0x1801dffab  mov     [r11-78h], rbx
0x1801dffaf  mov     [r11-70h], rbx
0x1801dffb3  lea     r8d, [rbx+27h]; cchMax
0x1801dffb7  call    cs:__imp_StringFromGUID2
0x1801dffbe  nop     dword ptr [rax+rax+00h]
0x1801dffc3  lea     rax, [rsp+0A8h+hKey]
0x1801dffc8  mov     r9d, 20019h; samDesired
0x1801dffce  xor     r8d, r8d; ulOptions
0x1801dffd1  mov     [rsp+0A8h+phkResult], rax; phkResult
0x1801dffd6  lea     rdx, aClsid; "CLSID"
0x1801dffdd  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1801dffe4  call    cs:__imp_RegOpenKeyExW
0x1801dffeb  nop     dword ptr [rax+rax+00h]
0x1801dfff0  test    eax, eax
0x1801dfff2  jz      short loc_1801DFFF8
0x1801dfff4  xor     eax, eax
0x1801dfff6  jmp     short loc_1801E004E
0x1801dfff8  mov     rcx, [rsp+0A8h+hKey]; hKey
0x1801dfffd  lea     rax, [rsp+0A8h+var_70]
0x1801e0002  mov     r9d, 20019h; samDesired
0x1801e0008  mov     [rsp+0A8h+phkResult], rax; phkResult
0x1801e000d  xor     r8d, r8d; ulOptions
0x1801e0010  lea     rdx, [rsp+0A8h+SubKey]; lpSubKey
0x1801e0015  call    cs:__imp_RegOpenKeyExW
0x1801e001c  nop     dword ptr [rax+rax+00h]
0x1801e0021  test    eax, eax
0x1801e0023  jnz     short loc_1801E003B
0x1801e0025  mov     rcx, [rsp+0A8h+var_70]; hKey
0x1801e002a  call    cs:__imp_RegCloseKey
0x1801e0031  nop     dword ptr [rax+rax+00h]
0x1801e0036  mov     ebx, 1
0x1801e003b  mov     rcx, [rsp+0A8h+hKey]; hKey
0x1801e0040  call    cs:__imp_RegCloseKey
0x1801e0047  nop     dword ptr [rax+rax+00h]
0x1801e004c  mov     eax, ebx
0x1801e004e  mov     rcx, [rsp+0A8h+var_18]
0x1801e0056  xor     rcx, rsp; StackCookie
0x1801e0059  call    __security_check_cookie
0x1801e005e  add     rsp, 0A0h
0x1801e0065  pop     rbx
0x1801e0066  retn
```
