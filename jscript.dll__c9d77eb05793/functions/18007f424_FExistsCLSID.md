# FExistsCLSID

- ea: `0x18007f424`
- end: `0x18007f4e1`
- name: `FExistsCLSID`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007fc64`

## callees

- `0x18007f424`
- `0x18007fbcc`
- `0x1800942d0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x18007f476`
- `ADVAPI32!RegOpenKeyExA` at `0x18007f4a1`
- `ADVAPI32!RegOpenKeyExA` at `0x18007f476`
- `ADVAPI32!RegOpenKeyExA` at `0x18007f4a1`
- `ADVAPI32!RegCloseKey` at `0x18007f4b0`
- `ADVAPI32!RegCloseKey` at `0x18007f4c0`
- `ADVAPI32!RegCloseKey` at `0x18007f4b0`
- `ADVAPI32!RegCloseKey` at `0x18007f4c0`

## string_xrefs

- `0x18007f468`: `CLSID`

## pseudocode

```c
__int64 __fastcall FExistsCLSID(const struct _GUID *a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // ebx
  HKEY hKey; // [rsp+30h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-90h] BYREF
  CHAR SubKey[112]; // [rsp+40h] [rbp-88h] BYREF

  v3 = 0;
  hKey = 0;
  phkResult = 0;
  StringFromGuidA(a1, SubKey, a3);
  if ( RegOpenKeyExA(HKEY_CLASSES_ROOT, "CLSID", 0, 0x2000000u, &hKey) )
    return 0;
  if ( !RegOpenKeyExA(hKey, SubKey, 0, 0x2000000u, &phkResult) )
  {
    RegCloseKey(phkResult);
    v3 = 1;
  }
  RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x18007f424  push    rbx
0x18007f426  sub     rsp, 0C0h
0x18007f42d  mov     rax, cs:__security_cookie
0x18007f434  xor     rax, rsp
0x18007f437  mov     [rsp+0C8h+var_18], rax
0x18007f43f  xor     ebx, ebx
0x18007f441  lea     rdx, [rsp+0C8h+SubKey]; char *
0x18007f446  mov     [rsp+0C8h+hKey], rbx
0x18007f44b  mov     [rsp+0C8h+var_90], rbx
0x18007f450  call    ?StringFromGuidA@@YAHAEBU_GUID@@PEADI@Z; StringFromGuidA(_GUID const &,char *,uint)
0x18007f455  lea     rax, [rsp+0C8h+hKey]
0x18007f45a  mov     r9d, 2000000h; samDesired
0x18007f460  xor     r8d, r8d; ulOptions
0x18007f463  mov     [rsp+0C8h+phkResult], rax; phkResult
0x18007f468  lea     rdx, aClsid; "CLSID"
0x18007f46f  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18007f476  call    cs:__imp_RegOpenKeyExA
0x18007f47c  test    eax, eax
0x18007f47e  jz      short loc_18007F484
0x18007f480  xor     eax, eax
0x18007f482  jmp     short loc_18007F4C8
0x18007f484  mov     rcx, [rsp+0C8h+hKey]; hKey
0x18007f489  lea     rax, [rsp+0C8h+var_90]
0x18007f48e  mov     r9d, 2000000h; samDesired
0x18007f494  mov     [rsp+0C8h+phkResult], rax; phkResult
0x18007f499  xor     r8d, r8d; ulOptions
0x18007f49c  lea     rdx, [rsp+0C8h+SubKey]; lpSubKey
0x18007f4a1  call    cs:__imp_RegOpenKeyExA
0x18007f4a7  test    eax, eax
0x18007f4a9  jnz     short loc_18007F4BB
0x18007f4ab  mov     rcx, [rsp+0C8h+var_90]; hKey
0x18007f4b0  call    cs:__imp_RegCloseKey
0x18007f4b6  mov     ebx, 1
0x18007f4bb  mov     rcx, [rsp+0C8h+hKey]; hKey
0x18007f4c0  call    cs:__imp_RegCloseKey
0x18007f4c6  mov     eax, ebx
0x18007f4c8  mov     rcx, [rsp+0C8h+var_18]
0x18007f4d0  xor     rcx, rsp; StackCookie
0x18007f4d3  call    __security_check_cookie
0x18007f4d8  add     rsp, 0C0h
0x18007f4df  pop     rbx
0x18007f4e0  retn
```
