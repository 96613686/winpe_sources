# FExistsCLSID

- ea: `0x180080dfc`
- end: `0x180080ed2`
- name: `FExistsCLSID`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008172c`

## callees

- `0x180080dfc`
- `0x180081690`
- `0x1800966e0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x180080e4e`
- `ADVAPI32!RegOpenKeyExA` at `0x180080e7f`
- `ADVAPI32!RegOpenKeyExA` at `0x180080e4e`
- `ADVAPI32!RegOpenKeyExA` at `0x180080e7f`
- `ADVAPI32!RegCloseKey` at `0x180080e94`
- `ADVAPI32!RegCloseKey` at `0x180080eaa`
- `ADVAPI32!RegCloseKey` at `0x180080e94`
- `ADVAPI32!RegCloseKey` at `0x180080eaa`

## string_xrefs

- `0x180080e40`: `CLSID`

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
0x180080dfc  push    rbx
0x180080dfe  sub     rsp, 0C0h
0x180080e05  mov     rax, cs:__security_cookie
0x180080e0c  xor     rax, rsp
0x180080e0f  mov     [rsp+0C8h+var_18], rax
0x180080e17  xor     ebx, ebx
0x180080e19  lea     rdx, [rsp+0C8h+SubKey]; char *
0x180080e1e  mov     [rsp+0C8h+hKey], rbx
0x180080e23  mov     [rsp+0C8h+var_90], rbx
0x180080e28  call    ?StringFromGuidA@@YAHAEBU_GUID@@PEADI@Z; StringFromGuidA(_GUID const &,char *,uint)
0x180080e2d  lea     rax, [rsp+0C8h+hKey]
0x180080e32  mov     r9d, 2000000h; samDesired
0x180080e38  xor     r8d, r8d; ulOptions
0x180080e3b  mov     [rsp+0C8h+phkResult], rax; phkResult
0x180080e40  lea     rdx, aClsid; "CLSID"
0x180080e47  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180080e4e  call    cs:__imp_RegOpenKeyExA
0x180080e55  nop     dword ptr [rax+rax+00h]
0x180080e5a  test    eax, eax
0x180080e5c  jz      short loc_180080E62
0x180080e5e  xor     eax, eax
0x180080e60  jmp     short loc_180080EB8
0x180080e62  mov     rcx, [rsp+0C8h+hKey]; hKey
0x180080e67  lea     rax, [rsp+0C8h+var_90]
0x180080e6c  mov     r9d, 2000000h; samDesired
0x180080e72  mov     [rsp+0C8h+phkResult], rax; phkResult
0x180080e77  xor     r8d, r8d; ulOptions
0x180080e7a  lea     rdx, [rsp+0C8h+SubKey]; lpSubKey
0x180080e7f  call    cs:__imp_RegOpenKeyExA
0x180080e86  nop     dword ptr [rax+rax+00h]
0x180080e8b  test    eax, eax
0x180080e8d  jnz     short loc_180080EA5
0x180080e8f  mov     rcx, [rsp+0C8h+var_90]; hKey
0x180080e94  call    cs:__imp_RegCloseKey
0x180080e9b  nop     dword ptr [rax+rax+00h]
0x180080ea0  mov     ebx, 1
0x180080ea5  mov     rcx, [rsp+0C8h+hKey]; hKey
0x180080eaa  call    cs:__imp_RegCloseKey
0x180080eb1  nop     dword ptr [rax+rax+00h]
0x180080eb6  mov     eax, ebx
0x180080eb8  mov     rcx, [rsp+0C8h+var_18]
0x180080ec0  xor     rcx, rsp; StackCookie
0x180080ec3  call    __security_check_cookie
0x180080ec8  add     rsp, 0C0h
0x180080ecf  pop     rbx
0x180080ed0  retn
```
