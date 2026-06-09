# MoveLogonPreferences

- ea: `0x18005a83c`
- end: `0x18005a916`
- name: `MoveLogonPreferences`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005a480`

## callees

- `0x18005a39c`
- `0x18005a55c`
- `0x18005a83c`
- `0x18005aa0c`
- `0x18005b240`
- `0x1800e7206`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005a88b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005a8b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005a88b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005a8b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a8c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a907`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a8c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a907`

## pseudocode

```c
LSTATUS MoveLogonPreferences()
{
  LSTATUS result; // eax
  char v1[192]; // [rsp+30h] [rbp-69h] BYREF
  HKEY phkResult; // [rsp+100h] [rbp+67h] BYREF
  HKEY hKey; // [rsp+108h] [rbp+6Fh] BYREF

  phkResult = 0;
  hKey = 0;
  memset_0(v1, 0, 0xB8u);
  result = RegOpenKeyExW(HKEY_USERS, L".DEFAULT\\Software\\Microsoft\\RAS Phonebook", 0, 0x20019u, &phkResult);
  if ( !result )
  {
    if ( RegOpenKeyExW(HKEY_USERS, L".DEFAULT\\Software\\Microsoft\\RAS Logon Phonebook", 0, 0x20019u, &hKey) )
    {
      if ( !(unsigned int)SetDefaultUserPreferences(v1) && !(unsigned int)ReadUserPreferences(phkResult, v1) )
        DwSetUserPreferences(v1, 1);
      DestroyUserPreferences(v1);
    }
    else
    {
      RegCloseKey(hKey);
    }
    return RegCloseKey(phkResult);
  }
  return result;
}

```

## disassembly

```asm
0x18005a83c  push    rbp
0x18005a83e  lea     rbp, [rsp-57h]
0x18005a843  sub     rsp, 0F0h
0x18005a84a  xor     edx, edx; Val
0x18005a84c  mov     [rbp+57h+arg_0], 0
0x18005a854  mov     r8d, 0B8h; Size
0x18005a85a  mov     [rbp+57h+hKey], 0
0x18005a862  lea     rcx, [rbp+57h+var_C0]; void *
0x18005a866  call    memset_0
0x18005a86b  lea     rax, [rbp+57h+arg_0]
0x18005a86f  mov     r9d, 20019h; samDesired
0x18005a875  xor     r8d, r8d; ulOptions
0x18005a878  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18005a87d  lea     rdx, aDefaultSoftwar_0; ".DEFAULT\\Software\\Microsoft\\RAS Phon"...
0x18005a884  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18005a88b  call    cs:__imp_RegOpenKeyExW
0x18005a891  test    eax, eax
0x18005a893  jnz     short loc_18005A90D
0x18005a895  lea     rax, [rbp+57h+hKey]
0x18005a899  mov     r9d, 20019h; samDesired
0x18005a89f  xor     r8d, r8d; ulOptions
0x18005a8a2  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18005a8a7  lea     rdx, aDefaultSoftwar; ".DEFAULT\\Software\\Microsoft\\RAS Logo"...
0x18005a8ae  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18005a8b5  call    cs:__imp_RegOpenKeyExW
0x18005a8bb  test    eax, eax
0x18005a8bd  jnz     short loc_18005A8CB
0x18005a8bf  mov     rcx, [rbp+57h+hKey]; hKey
0x18005a8c3  call    cs:__imp_RegCloseKey
0x18005a8c9  jmp     short loc_18005A903
0x18005a8cb  mov     edx, 1
0x18005a8d0  lea     rcx, [rbp+57h+var_C0]; void *
0x18005a8d4  call    SetDefaultUserPreferences
0x18005a8d9  test    eax, eax
0x18005a8db  jnz     short loc_18005A8FA
0x18005a8dd  mov     rcx, [rbp+57h+arg_0]; hKey
0x18005a8e1  lea     rdx, [rbp+57h+var_C0]; void *
0x18005a8e5  call    ReadUserPreferences
0x18005a8ea  test    eax, eax
0x18005a8ec  jnz     short loc_18005A8FA
0x18005a8ee  lea     edx, [rax+1]
0x18005a8f1  lea     rcx, [rbp+57h+var_C0]
0x18005a8f5  call    DwSetUserPreferences
0x18005a8fa  lea     rcx, [rbp+57h+var_C0]; void *
0x18005a8fe  call    DestroyUserPreferences
0x18005a903  mov     rcx, [rbp+57h+arg_0]; hKey
0x18005a907  call    cs:__imp_RegCloseKey
0x18005a90d  add     rsp, 0F0h
0x18005a914  pop     rbp
0x18005a915  retn
```
