# TranslateAndSaveInterfaceKey

- ea: `0x1800294a4`
- end: `0x1800295dd`
- name: `TranslateAndSaveInterfaceKey`
- size: `313`
- prototype: `__int64 __fastcall(HANDLE hMprConfig, LPCWSTR lpFile)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x180025e20`

## callees

- `0x180017c34`
- `0x180017df8`
- `0x180017f30`
- `0x1800294a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800295a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800295a9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800295c0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800295c0`
- `api-ms-win-core-registry-l1-1-0!RegRestoreKeyW` at `0x18002955a`
- `api-ms-win-core-registry-l1-1-0!RegRestoreKeyW` at `0x18002955a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002951c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002951c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180029534`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180029567`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180029534`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180029567`
- `api-ms-win-core-registry-l2-1-0!RegSaveKeyW` at `0x180029544`
- `api-ms-win-core-registry-l2-1-0!RegSaveKeyW` at `0x18002958f`
- `api-ms-win-core-registry-l2-1-0!RegSaveKeyW` at `0x180029544`
- `api-ms-win-core-registry-l2-1-0!RegSaveKeyW` at `0x18002958f`

## pseudocode

```c
DWORD __fastcall TranslateAndSaveInterfaceKey(HKEY *hMprConfig, LPCWSTR lpFile, __int64 a3)
{
  DWORD result; // eax
  DWORD dwDisposition; // [rsp+70h] [rbp+18h] BYREF
  int v7; // [rsp+74h] [rbp+1Ch]
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  v7 = HIDWORD(a3);
  dwDisposition = 0;
  hKey = 0;
  result = EnableBackupPrivilege(1, 18);
  if ( !result )
  {
    result = RegCreateKeyExW(hMprConfig[3], L"BackupInterfaces", 0, 0, 0, 0x3001Fu, 0, &hKey, &dwDisposition);
    if ( !result )
    {
      if ( dwDisposition != 2 )
      {
        DeleteFileW(lpFile);
        if ( !RegSaveKeyW(hMprConfig[7], lpFile, 0) && !RegRestoreKeyW(hKey, lpFile, 8u) )
        {
          DeleteFileW(lpFile);
          if ( !(unsigned int)EnumLanInterfaces(hMprConfig, hKey) )
            RegSaveKeyW(hKey, lpFile, 0);
        }
      }
      if ( hKey )
      {
        DeleteRegistryTree();
        RegCloseKey(hKey);
        RegDeleteKeyExW(hMprConfig[3], L"BackupInterfaces", 0, 0);
      }
      return EnableBackupPrivilege(0, 18);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800294a4  mov     rax, rsp
0x1800294a7  mov     [rax+8], rbx
0x1800294ab  mov     [rax+18h], r8
0x1800294af  push    rdi
0x1800294b0  sub     rsp, 50h
0x1800294b4  mov     rbx, rdx
0x1800294b7  mov     dword ptr [rax+18h], 0
0x1800294be  mov     edx, 12h
0x1800294c3  mov     qword ptr [rax+20h], 0
0x1800294cb  mov     rdi, rcx
0x1800294ce  lea     ecx, [rdx-11h]
0x1800294d1  call    EnableBackupPrivilege
0x1800294d6  test    eax, eax
0x1800294d8  jnz     loc_1800295D2
0x1800294de  mov     rcx, [rdi+18h]; hKey
0x1800294e2  lea     rax, [rsp+58h+dwDisposition]
0x1800294e7  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x1800294ec  lea     rdx, aBackupinterfac; "BackupInterfaces"
0x1800294f3  lea     rax, [rsp+58h+hKey]
0x1800294f8  xor     r9d, r9d; lpClass
0x1800294fb  mov     [rsp+58h+phkResult], rax; phkResult
0x180029500  xor     r8d, r8d; Reserved
0x180029503  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002950c  mov     [rsp+58h+samDesired], 3001Fh; samDesired
0x180029514  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18002951c  call    cs:__imp_RegCreateKeyExW
0x180029522  test    eax, eax
0x180029524  jnz     loc_1800295D2
0x18002952a  cmp     [rsp+58h+dwDisposition], 2
0x18002952f  jz      short loc_180029595
0x180029531  mov     rcx, rbx; lpFileName
0x180029534  call    cs:__imp_DeleteFileW
0x18002953a  mov     rcx, [rdi+38h]; hKey
0x18002953e  xor     r8d, r8d; lpSecurityAttributes
0x180029541  mov     rdx, rbx; lpFile
0x180029544  call    cs:__imp_RegSaveKeyW
0x18002954a  test    eax, eax
0x18002954c  jnz     short loc_180029595
0x18002954e  mov     rcx, [rsp+58h+hKey]; hKey
0x180029553  lea     r8d, [rax+8]; dwFlags
0x180029557  mov     rdx, rbx; lpFile
0x18002955a  call    cs:__imp_RegRestoreKeyW
0x180029560  test    eax, eax
0x180029562  jnz     short loc_180029595
0x180029564  mov     rcx, rbx; lpFileName
0x180029567  call    cs:__imp_DeleteFileW
0x18002956d  mov     rdx, [rsp+58h+hKey]; hKey
0x180029572  mov     r9d, 1
0x180029578  mov     rcx, rdi; hMprConfig
0x18002957b  call    EnumLanInterfaces
0x180029580  test    eax, eax
0x180029582  jnz     short loc_180029595
0x180029584  mov     rcx, [rsp+58h+hKey]; hKey
0x180029589  xor     r8d, r8d; lpSecurityAttributes
0x18002958c  mov     rdx, rbx; lpFile
0x18002958f  call    cs:__imp_RegSaveKeyW
0x180029595  mov     rcx, [rsp+58h+hKey]
0x18002959a  test    rcx, rcx
0x18002959d  jz      short loc_1800295C6
0x18002959f  call    DeleteRegistryTree
0x1800295a4  mov     rcx, [rsp+58h+hKey]; hKey
0x1800295a9  call    cs:__imp_RegCloseKey
0x1800295af  mov     rcx, [rdi+18h]; hKey
0x1800295b3  lea     rdx, aBackupinterfac; "BackupInterfaces"
0x1800295ba  xor     r9d, r9d; Reserved
0x1800295bd  xor     r8d, r8d; samDesired
0x1800295c0  call    cs:__imp_RegDeleteKeyExW
0x1800295c6  mov     edx, 12h
0x1800295cb  xor     ecx, ecx
0x1800295cd  call    EnableBackupPrivilege
0x1800295d2  mov     rbx, [rsp+58h+arg_0]
0x1800295d7  add     rsp, 50h
0x1800295db  pop     rdi
0x1800295dc  retn
```
