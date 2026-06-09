# MoveLogonPreferences

- ea: `0x18005d77c`
- end: `0x18005d873`
- name: `MoveLogonPreferences`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005d1c0`

## callees

- `0x18005d0c4`
- `0x18005d2a8`
- `0x18005d77c`
- `0x18005d988`
- `0x18005e0d8`
- `0x1800e8e96`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d7cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d7ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d7cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d7ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d813`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d85d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d813`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d85d`

## pseudocode

```c
LSTATUS MoveLogonPreferences()
{
  LSTATUS result; // eax
  _BYTE v1[192]; // [rsp+30h] [rbp-69h] BYREF
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
0x18005d77c  push    rbp
0x18005d77e  lea     rbp, [rsp-57h]
0x18005d783  sub     rsp, 0F0h
0x18005d78a  xor     edx, edx; Val
0x18005d78c  mov     [rbp+57h+arg_0], 0
0x18005d794  mov     r8d, 0B8h; Size
0x18005d79a  mov     [rbp+57h+hKey], 0
0x18005d7a2  lea     rcx, [rbp+57h+var_C0]; void *
0x18005d7a6  call    memset_0
0x18005d7ab  lea     rax, [rbp+57h+arg_0]
0x18005d7af  mov     r9d, 20019h; samDesired
0x18005d7b5  xor     r8d, r8d; ulOptions
0x18005d7b8  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18005d7bd  lea     rdx, aDefaultSoftwar_0; ".DEFAULT\\Software\\Microsoft\\RAS Phon"...
0x18005d7c4  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18005d7cb  call    cs:__imp_RegOpenKeyExW
0x18005d7d2  nop     dword ptr [rax+rax+00h]
0x18005d7d7  test    eax, eax
0x18005d7d9  jnz     loc_18005D869
0x18005d7df  lea     rax, [rbp+57h+hKey]
0x18005d7e3  mov     r9d, 20019h; samDesired
0x18005d7e9  xor     r8d, r8d; ulOptions
0x18005d7ec  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18005d7f1  lea     rdx, aDefaultSoftwar; ".DEFAULT\\Software\\Microsoft\\RAS Logo"...
0x18005d7f8  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18005d7ff  call    cs:__imp_RegOpenKeyExW
0x18005d806  nop     dword ptr [rax+rax+00h]
0x18005d80b  test    eax, eax
0x18005d80d  jnz     short loc_18005D821
0x18005d80f  mov     rcx, [rbp+57h+hKey]; hKey
0x18005d813  call    cs:__imp_RegCloseKey
0x18005d81a  nop     dword ptr [rax+rax+00h]
0x18005d81f  jmp     short loc_18005D859
0x18005d821  mov     edx, 1
0x18005d826  lea     rcx, [rbp+57h+var_C0]; void *
0x18005d82a  call    SetDefaultUserPreferences
0x18005d82f  test    eax, eax
0x18005d831  jnz     short loc_18005D850
0x18005d833  mov     rcx, [rbp+57h+arg_0]; hKey
0x18005d837  lea     rdx, [rbp+57h+var_C0]; void *
0x18005d83b  call    ReadUserPreferences
0x18005d840  test    eax, eax
0x18005d842  jnz     short loc_18005D850
0x18005d844  lea     edx, [rax+1]
0x18005d847  lea     rcx, [rbp+57h+var_C0]
0x18005d84b  call    DwSetUserPreferences
0x18005d850  lea     rcx, [rbp+57h+var_C0]; void *
0x18005d854  call    DestroyUserPreferences
0x18005d859  mov     rcx, [rbp+57h+arg_0]; hKey
0x18005d85d  call    cs:__imp_RegCloseKey
0x18005d864  nop     dword ptr [rax+rax+00h]
0x18005d869  add     rsp, 0F0h
0x18005d870  pop     rbp
0x18005d871  retn
```
