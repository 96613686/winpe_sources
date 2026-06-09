# IsSafeorAuditMode

- ea: `0x18000b52c`
- end: `0x18000b7b1`
- name: `IsSafeorAuditMode`
- size: `645`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000b3d0`

## callees

- `0x1800077a0`
- `0x18000b52c`
- `0x18000b7b8`
- `0x180097e68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b5f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b63a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b5f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b63a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b67c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b6c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b73b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b67c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b6c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b73b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b6fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b7a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b6fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b7a0`
- `api-ms-win-core-sysinfo-l1-2-0!GetOsSafeBootMode` at `0x18000b556`
- `api-ms-win-core-sysinfo-l1-2-0!GetOsSafeBootMode` at `0x18000b556`

## string_xrefs

- `0x18000b610`: `AUINSTALLAGENT_REG_CONTROL_USER failed with 0x%08x`
- `0x18000b5ea`: `Software\Microsoft\AllUserInstallAgent`
- `0x18000b758`: `AUINSTALLAGENT_REG_STAGINGINPROGRESS in progress`

## pseudocode

```c
__int64 IsSafeorAuditMode()
{
  const char *v0; // rdx
  unsigned int v1; // edi
  LSTATUS v2; // eax
  LSTATUS v3; // eax
  const char *v5; // rdx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-10h] BYREF
  int Data; // [rsp+70h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+30h] BYREF
  DWORD Type; // [rsp+80h] [rbp+38h] BYREF
  int v11; // [rsp+88h] [rbp+40h] BYREF

  cbData = 4;
  v11 = 0;
  hKey = 0;
  Type = 0;
  Data = 0;
  phkResult = 0;
  if ( (unsigned int)GetOsSafeBootMode(&v11) && v11 )
  {
    v0 = "Safe Mode boot";
    goto LABEL_8;
  }
  if ( (unsigned int)RegExists(-2147483646, L"System\\Setup\\Status", L"AuditBoot")
    && (unsigned int)RegGetDword(-2147483646, L"System\\Setup\\Status")
    || (unsigned int)RegExists(-2147483646, L"System\\Setup\\Status\\AuditBootVolatile", 0) )
  {
    v0 = "Audit Mode boot";
LABEL_8:
    _DbgPrintMessage(1, v0);
    v1 = 1;
    goto LABEL_15;
  }
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\AllUserInstallAgent", 0, 0x20019u, &phkResult);
  if ( v2 )
  {
    _DbgPrintMessage(1, "AUINSTALLAGENT_REG_CONTROL_USER failed with 0x%08x", v2);
  }
  else
  {
    cbData = 4;
    Data = 0;
    if ( !RegQueryValueExW(phkResult, L"StagingInProgress", 0, &Type, (LPBYTE)&Data, &cbData) && Data )
    {
      v5 = "AUINSTALLAGENT_REG_STAGINGINPROGRESS in progress";
LABEL_27:
      v1 = 1;
      _DbgPrintMessage(1, v5);
      goto LABEL_15;
    }
  }
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup", 0, 0x20019u, &hKey);
  if ( v3 )
  {
    _DbgPrintMessage(1, "TS_SYSPREP_KEY failed with 0x%08x", v3);
    v1 = 0;
    goto LABEL_15;
  }
  cbData = 4;
  Data = 0;
  if ( !RegQueryValueExW(hKey, L"SystemSetupInProgress", 0, &Type, (LPBYTE)&Data, &cbData) && Data )
  {
    v5 = "TS_SYSPREP_INPROGRESS in progress";
    goto LABEL_27;
  }
  cbData = 4;
  Data = 0;
  v1 = 0;
  if ( !RegQueryValueExW(hKey, L"OOBEInProgress", 0, &Type, (LPBYTE)&Data, &cbData) && Data )
  {
    v5 = "TS_OOBE_INPROGRESS in progress";
    goto LABEL_27;
  }
LABEL_15:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return v1;
}

```

## disassembly

```asm
0x18000b52c  push    rbp
0x18000b52e  push    rbx
0x18000b52f  push    rsi
0x18000b530  push    rdi
0x18000b531  mov     rbp, rsp
0x18000b534  sub     rsp, 48h
0x18000b538  xor     esi, esi
0x18000b53a  mov     [rbp+cbData], 4
0x18000b541  lea     rcx, [rbp+arg_18]
0x18000b545  mov     [rbp+arg_18], esi
0x18000b548  mov     [rbp+hKey], rsi
0x18000b54c  mov     [rbp+Type], esi
0x18000b54f  mov     [rbp+Data], esi
0x18000b552  mov     [rbp+var_10], rsi
0x18000b556  call    cs:__imp_GetOsSafeBootMode
0x18000b55d  nop     dword ptr [rax+rax+00h]
0x18000b562  test    eax, eax
0x18000b564  jz      short loc_18000B56B
0x18000b566  cmp     [rbp+arg_18], esi
0x18000b569  jnz     short loc_18000B5BE
0x18000b56b  mov     rdi, 0FFFFFFFF80000002h
0x18000b572  lea     r8, aAuditboot; "AuditBoot"
0x18000b579  mov     rcx, rdi
0x18000b57c  lea     rdx, aSystemSetupSta; "System\\Setup\\Status"
0x18000b583  call    RegExists
0x18000b588  test    eax, eax
0x18000b58a  jz      short loc_18000B59F
0x18000b58c  lea     rdx, aSystemSetupSta; "System\\Setup\\Status"
0x18000b593  mov     rcx, rdi
0x18000b596  call    RegGetDword
0x18000b59b  test    eax, eax
0x18000b59d  jnz     short loc_18000B5B5
0x18000b59f  xor     r8d, r8d
0x18000b5a2  lea     rdx, aSystemSetupSta_0; "System\\Setup\\Status\\AuditBootVolatil"...
0x18000b5a9  mov     rcx, rdi
0x18000b5ac  call    RegExists
0x18000b5b1  test    eax, eax
0x18000b5b3  jz      short loc_18000B5D8
0x18000b5b5  lea     rdx, aAuditModeBoot; "Audit Mode boot"
0x18000b5bc  jmp     short loc_18000B5C5
0x18000b5be  lea     rdx, aSafeModeBoot; "Safe Mode boot"
0x18000b5c5  mov     ebx, 1
0x18000b5ca  mov     ecx, ebx; int
0x18000b5cc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b5d1  mov     edi, ebx
0x18000b5d3  jmp     loc_18000B6D9
0x18000b5d8  lea     rax, [rbp+var_10]
0x18000b5dc  mov     r9d, 20019h; samDesired
0x18000b5e2  xor     r8d, r8d; ulOptions
0x18000b5e5  mov     [rsp+48h+phkResult], rax; phkResult
0x18000b5ea  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\AllUserInstallAgen"...
0x18000b5f1  mov     rcx, rdi; hKey
0x18000b5f4  call    cs:__imp_RegOpenKeyExW
0x18000b5fb  nop     dword ptr [rax+rax+00h]
0x18000b600  mov     ebx, 1
0x18000b605  test    eax, eax
0x18000b607  jz      loc_18000B70D
0x18000b60d  mov     r8d, eax
0x18000b610  lea     rdx, aAuinstallagent; "AUINSTALLAGENT_REG_CONTROL_USER failed "...
0x18000b617  mov     ecx, ebx; int
0x18000b619  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b61e  lea     rax, [rbp+hKey]
0x18000b622  mov     r9d, 20019h; samDesired
0x18000b628  xor     r8d, r8d; ulOptions
0x18000b62b  mov     [rsp+48h+phkResult], rax; phkResult
0x18000b630  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x18000b637  mov     rcx, rdi; hKey
0x18000b63a  call    cs:__imp_RegOpenKeyExW
0x18000b641  nop     dword ptr [rax+rax+00h]
0x18000b646  test    eax, eax
0x18000b648  jnz     loc_18000B761
0x18000b64e  mov     rcx, [rbp+hKey]; hKey
0x18000b652  lea     rax, [rbp+cbData]
0x18000b656  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000b65b  lea     r9, [rbp+Type]; lpType
0x18000b65f  lea     rax, [rbp+Data]
0x18000b663  mov     [rbp+cbData], 4
0x18000b66a  xor     r8d, r8d; lpReserved
0x18000b66d  mov     [rsp+48h+phkResult], rax; lpData
0x18000b672  lea     rdx, aSystemsetupinp; "SystemSetupInProgress"
0x18000b679  mov     [rbp+Data], esi
0x18000b67c  call    cs:__imp_RegQueryValueExW
0x18000b683  nop     dword ptr [rax+rax+00h]
0x18000b688  test    eax, eax
0x18000b68a  jz      loc_18000B779
0x18000b690  mov     rcx, [rbp+hKey]; hKey
0x18000b694  lea     rax, [rbp+cbData]
0x18000b698  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000b69d  lea     r9, [rbp+Type]; lpType
0x18000b6a1  lea     rax, [rbp+Data]
0x18000b6a5  mov     [rbp+cbData], 4
0x18000b6ac  xor     r8d, r8d; lpReserved
0x18000b6af  mov     [rsp+48h+phkResult], rax; lpData
0x18000b6b4  lea     rdx, aOobeinprogress; "OOBEInProgress"
0x18000b6bb  mov     [rbp+Data], esi
0x18000b6be  mov     edi, esi
0x18000b6c0  call    cs:__imp_RegQueryValueExW
0x18000b6c7  nop     dword ptr [rax+rax+00h]
0x18000b6cc  test    eax, eax
0x18000b6ce  jnz     short loc_18000B6D9
0x18000b6d0  cmp     [rbp+Data], esi
0x18000b6d3  jnz     loc_18000B78B
0x18000b6d9  mov     rcx, [rbp+hKey]; hKey
0x18000b6dd  test    rcx, rcx
0x18000b6e0  jnz     short loc_18000B6FB
0x18000b6e2  mov     rcx, [rbp+var_10]; hKey
0x18000b6e6  test    rcx, rcx
0x18000b6e9  jnz     loc_18000B7A0
0x18000b6ef  mov     eax, edi
0x18000b6f1  add     rsp, 48h
0x18000b6f5  pop     rdi
0x18000b6f6  pop     rsi
0x18000b6f7  pop     rbx
0x18000b6f8  pop     rbp
0x18000b6f9  retn
0x18000b6fb  call    cs:__imp_RegCloseKey
0x18000b702  nop     dword ptr [rax+rax+00h]
0x18000b707  mov     [rbp+hKey], rsi
0x18000b70b  jmp     short loc_18000B6E2
0x18000b70d  mov     rcx, [rbp+var_10]; hKey
0x18000b711  lea     rax, [rbp+cbData]
0x18000b715  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000b71a  lea     r9, [rbp+Type]; lpType
0x18000b71e  lea     rax, [rbp+Data]
0x18000b722  mov     [rbp+cbData], 4
0x18000b729  xor     r8d, r8d; lpReserved
0x18000b72c  mov     [rsp+48h+phkResult], rax; lpData
0x18000b731  lea     rdx, aStaginginprogr; "StagingInProgress"
0x18000b738  mov     [rbp+Data], esi
0x18000b73b  call    cs:__imp_RegQueryValueExW
0x18000b742  nop     dword ptr [rax+rax+00h]
0x18000b747  test    eax, eax
0x18000b749  jnz     loc_18000B61E
0x18000b74f  cmp     [rbp+Data], esi
0x18000b752  jz      loc_18000B61E
0x18000b758  lea     rdx, aAuinstallagent_0; "AUINSTALLAGENT_REG_STAGINGINPROGRESS in"...
0x18000b75f  jmp     short loc_18000B792
0x18000b761  mov     r8d, eax
0x18000b764  lea     rdx, aTsSysprepKeyFa; "TS_SYSPREP_KEY failed with 0x%08x"
0x18000b76b  mov     ecx, ebx; int
0x18000b76d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b772  mov     edi, esi
0x18000b774  jmp     loc_18000B6D9
0x18000b779  cmp     [rbp+Data], esi
0x18000b77c  jz      loc_18000B690
0x18000b782  lea     rdx, aTsSysprepInpro; "TS_SYSPREP_INPROGRESS in progress"
0x18000b789  jmp     short loc_18000B792
0x18000b78b  lea     rdx, aTsOobeInprogre; "TS_OOBE_INPROGRESS in progress"
0x18000b792  mov     ecx, ebx; int
0x18000b794  mov     edi, ebx
0x18000b796  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b79b  jmp     loc_18000B6D9
0x18000b7a0  call    cs:__imp_RegCloseKey
0x18000b7a7  nop     dword ptr [rax+rax+00h]
0x18000b7ac  jmp     loc_18000B6EF
```
