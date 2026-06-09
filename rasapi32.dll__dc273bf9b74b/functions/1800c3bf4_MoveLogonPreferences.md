# MoveLogonPreferences

- ea: `0x1800c3bf4`
- end: `0x1800c3d03`
- name: `MoveLogonPreferences`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c3608`

## callees

- `0x18003ff38`
- `0x1800c353c`
- `0x1800c3744`
- `0x1800c3bf4`
- `0x1800c3e70`
- `0x1800ded06`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c3c49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c3c74`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c3c49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c3c74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3c82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3cec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3c82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3cec`
- `rtutils!TracePrintfExA` at `0x1800c3ce2`
- `rtutils!TracePrintfExA` at `0x1800c3ce2`

## string_xrefs

- `0x1800c3cd6`: `MoveLogonPreferences=%d`

## pseudocode

```c
LSTATUS MoveLogonPreferences()
{
  LSTATUS result; // eax
  int UserPreferences; // ebx
  _BYTE v2[192]; // [rsp+30h] [rbp-69h] BYREF
  HKEY phkResult; // [rsp+100h] [rbp+67h] BYREF
  HKEY hKey; // [rsp+108h] [rbp+6Fh] BYREF

  phkResult = 0;
  hKey = 0;
  memset_0(v2, 0, 0xB8u);
  result = RegOpenKeyExW(HKEY_USERS, L".DEFAULT\\Software\\Microsoft\\RAS Phonebook", 0, 0x20019u, &phkResult);
  if ( !result )
  {
    if ( RegOpenKeyExW(HKEY_USERS, L".DEFAULT\\Software\\Microsoft\\RAS Logon Phonebook", 0, 0x20019u, &hKey) )
    {
      UserPreferences = SetDefaultUserPreferences(v2);
      if ( !UserPreferences )
      {
        UserPreferences = ReadUserPreferences(phkResult, v2);
        if ( !UserPreferences )
          UserPreferences = DwSetUserPreferences(v2, 1);
      }
      DestroyUserPreferences(v2);
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "MoveLogonPreferences=%d", UserPreferences);
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
0x1800c3bf4  mov     [rsp-8+arg_10], rbx
0x1800c3bf9  push    rbp
0x1800c3bfa  lea     rbp, [rsp-57h]
0x1800c3bff  sub     rsp, 0F0h
0x1800c3c06  xor     edx, edx; Val
0x1800c3c08  mov     [rbp+57h+arg_0], 0
0x1800c3c10  mov     r8d, 0B8h; Size
0x1800c3c16  mov     [rbp+57h+hKey], 0
0x1800c3c1e  lea     rcx, [rbp+57h+var_C0]; void *
0x1800c3c22  call    memset_0
0x1800c3c27  lea     rax, [rbp+57h+arg_0]
0x1800c3c2b  mov     ebx, 20019h
0x1800c3c30  mov     r9d, ebx; samDesired
0x1800c3c33  mov     [rsp+0F0h+phkResult], rax; phkResult
0x1800c3c38  xor     r8d, r8d; ulOptions
0x1800c3c3b  lea     rdx, aDefaultSoftwar_0; ".DEFAULT\\Software\\Microsoft\\RAS Phon"...
0x1800c3c42  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800c3c49  call    cs:__imp_RegOpenKeyExW
0x1800c3c4f  test    eax, eax
0x1800c3c51  jnz     loc_1800C3CF2
0x1800c3c57  lea     rax, [rbp+57h+hKey]
0x1800c3c5b  mov     r9d, ebx; samDesired
0x1800c3c5e  xor     r8d, r8d; ulOptions
0x1800c3c61  mov     [rsp+0F0h+phkResult], rax; phkResult
0x1800c3c66  lea     rdx, aDefaultSoftwar; ".DEFAULT\\Software\\Microsoft\\RAS Logo"...
0x1800c3c6d  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800c3c74  call    cs:__imp_RegOpenKeyExW
0x1800c3c7a  test    eax, eax
0x1800c3c7c  jnz     short loc_1800C3C8A
0x1800c3c7e  mov     rcx, [rbp+57h+hKey]; hKey
0x1800c3c82  call    cs:__imp_RegCloseKey
0x1800c3c88  jmp     short loc_1800C3CE8
0x1800c3c8a  mov     edx, 1
0x1800c3c8f  lea     rcx, [rbp+57h+var_C0]; void *
0x1800c3c93  call    SetDefaultUserPreferences
0x1800c3c98  mov     ebx, eax
0x1800c3c9a  test    eax, eax
0x1800c3c9c  jnz     short loc_1800C3CBF
0x1800c3c9e  mov     rcx, [rbp+57h+arg_0]; hKey
0x1800c3ca2  lea     rdx, [rbp+57h+var_C0]; void *
0x1800c3ca6  call    ReadUserPreferences
0x1800c3cab  mov     ebx, eax
0x1800c3cad  test    eax, eax
0x1800c3caf  jnz     short loc_1800C3CBF
0x1800c3cb1  lea     edx, [rax+1]
0x1800c3cb4  lea     rcx, [rbp+57h+var_C0]
0x1800c3cb8  call    DwSetUserPreferences
0x1800c3cbd  mov     ebx, eax
0x1800c3cbf  lea     rcx, [rbp+57h+var_C0]; void *
0x1800c3cc3  call    DestroyUserPreferences
0x1800c3cc8  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c3cce  cmp     ecx, 0FFFFFFFFh
0x1800c3cd1  jz      short loc_1800C3CE8
0x1800c3cd3  mov     r9d, ebx
0x1800c3cd6  lea     r8, aMovelogonprefe; "MoveLogonPreferences=%d"
0x1800c3cdd  mov     edx, 0Ch; dwFlags
0x1800c3ce2  call    cs:__imp_TracePrintfExA
0x1800c3ce8  mov     rcx, [rbp+57h+arg_0]; hKey
0x1800c3cec  call    cs:__imp_RegCloseKey
0x1800c3cf2  mov     rbx, [rsp+0F0h+arg_10]
0x1800c3cfa  add     rsp, 0F0h
0x1800c3d01  pop     rbp
0x1800c3d02  retn
```
