# IsSafeorAuditMode

- ea: `0x180017664`
- end: `0x1800178b8`
- name: `IsSafeorAuditMode`
- size: `596`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180017520`

## callees

- `0x1800074c0`
- `0x180017664`
- `0x1800178c0`
- `0x180092a64`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017726`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017766`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017726`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017766`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800177a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800177e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001784e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800177a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800177e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001784e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017814`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800178ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017814`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800178ad`
- `api-ms-win-core-sysinfo-l1-2-0!GetOsSafeBootMode` at `0x18001768e`
- `api-ms-win-core-sysinfo-l1-2-0!GetOsSafeBootMode` at `0x18001768e`

## string_xrefs

- `0x18001773c`: `AUINSTALLAGENT_REG_CONTROL_USER failed with 0x%08x`
- `0x18001771c`: `Software\Microsoft\AllUserInstallAgent`
- `0x180017865`: `AUINSTALLAGENT_REG_STAGINGINPROGRESS in progress`

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
0x180017664  push    rbp
0x180017666  push    rbx
0x180017667  push    rsi
0x180017668  push    rdi
0x180017669  mov     rbp, rsp
0x18001766c  sub     rsp, 48h
0x180017670  xor     esi, esi
0x180017672  mov     [rbp+cbData], 4
0x180017679  lea     rcx, [rbp+arg_18]
0x18001767d  mov     [rbp+arg_18], esi
0x180017680  mov     [rbp+hKey], rsi
0x180017684  mov     [rbp+Type], esi
0x180017687  mov     [rbp+Data], esi
0x18001768a  mov     [rbp+var_10], rsi
0x18001768e  call    cs:__imp_GetOsSafeBootMode
0x180017694  test    eax, eax
0x180017696  jz      short loc_18001769D
0x180017698  cmp     [rbp+arg_18], esi
0x18001769b  jnz     short loc_1800176F0
0x18001769d  mov     rdi, 0FFFFFFFF80000002h
0x1800176a4  lea     r8, aAuditboot; "AuditBoot"
0x1800176ab  mov     rcx, rdi
0x1800176ae  lea     rdx, aSystemSetupSta; "System\\Setup\\Status"
0x1800176b5  call    RegExists
0x1800176ba  test    eax, eax
0x1800176bc  jz      short loc_1800176D1
0x1800176be  lea     rdx, aSystemSetupSta; "System\\Setup\\Status"
0x1800176c5  mov     rcx, rdi
0x1800176c8  call    RegGetDword
0x1800176cd  test    eax, eax
0x1800176cf  jnz     short loc_1800176E7
0x1800176d1  xor     r8d, r8d
0x1800176d4  lea     rdx, aSystemSetupSta_0; "System\\Setup\\Status\\AuditBootVolatil"...
0x1800176db  mov     rcx, rdi
0x1800176de  call    RegExists
0x1800176e3  test    eax, eax
0x1800176e5  jz      short loc_18001770A
0x1800176e7  lea     rdx, aAuditModeBoot; "Audit Mode boot"
0x1800176ee  jmp     short loc_1800176F7
0x1800176f0  lea     rdx, aSafeModeBoot; "Safe Mode boot"
0x1800176f7  mov     ebx, 1
0x1800176fc  mov     ecx, ebx; int
0x1800176fe  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180017703  mov     edi, ebx
0x180017705  jmp     loc_1800177F3
0x18001770a  lea     rax, [rbp+var_10]
0x18001770e  mov     r9d, 20019h; samDesired
0x180017714  xor     r8d, r8d; ulOptions
0x180017717  mov     [rsp+48h+phkResult], rax; phkResult
0x18001771c  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\AllUserInstallAgen"...
0x180017723  mov     rcx, rdi; hKey
0x180017726  call    cs:__imp_RegOpenKeyExW
0x18001772c  mov     ebx, 1
0x180017731  test    eax, eax
0x180017733  jz      loc_180017820
0x180017739  mov     r8d, eax
0x18001773c  lea     rdx, aAuinstallagent; "AUINSTALLAGENT_REG_CONTROL_USER failed "...
0x180017743  mov     ecx, ebx; int
0x180017745  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001774a  lea     rax, [rbp+hKey]
0x18001774e  mov     r9d, 20019h; samDesired
0x180017754  xor     r8d, r8d; ulOptions
0x180017757  mov     [rsp+48h+phkResult], rax; phkResult
0x18001775c  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x180017763  mov     rcx, rdi; hKey
0x180017766  call    cs:__imp_RegOpenKeyExW
0x18001776c  test    eax, eax
0x18001776e  jnz     loc_18001786E
0x180017774  mov     rcx, [rbp+hKey]; hKey
0x180017778  lea     rax, [rbp+cbData]
0x18001777c  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180017781  lea     r9, [rbp+Type]; lpType
0x180017785  lea     rax, [rbp+Data]
0x180017789  mov     [rbp+cbData], 4
0x180017790  xor     r8d, r8d; lpReserved
0x180017793  mov     [rsp+48h+phkResult], rax; lpData
0x180017798  lea     rdx, aSystemsetupinp; "SystemSetupInProgress"
0x18001779f  mov     [rbp+Data], esi
0x1800177a2  call    cs:__imp_RegQueryValueExW
0x1800177a8  test    eax, eax
0x1800177aa  jz      loc_180017886
0x1800177b0  mov     rcx, [rbp+hKey]; hKey
0x1800177b4  lea     rax, [rbp+cbData]
0x1800177b8  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800177bd  lea     r9, [rbp+Type]; lpType
0x1800177c1  lea     rax, [rbp+Data]
0x1800177c5  mov     [rbp+cbData], 4
0x1800177cc  xor     r8d, r8d; lpReserved
0x1800177cf  mov     [rsp+48h+phkResult], rax; lpData
0x1800177d4  lea     rdx, aOobeinprogress; "OOBEInProgress"
0x1800177db  mov     [rbp+Data], esi
0x1800177de  mov     edi, esi
0x1800177e0  call    cs:__imp_RegQueryValueExW
0x1800177e6  test    eax, eax
0x1800177e8  jnz     short loc_1800177F3
0x1800177ea  cmp     [rbp+Data], esi
0x1800177ed  jnz     loc_180017898
0x1800177f3  mov     rcx, [rbp+hKey]; hKey
0x1800177f7  test    rcx, rcx
0x1800177fa  jnz     short loc_180017814
0x1800177fc  mov     rcx, [rbp+var_10]; hKey
0x180017800  test    rcx, rcx
0x180017803  jnz     loc_1800178AD
0x180017809  mov     eax, edi
0x18001780b  add     rsp, 48h
0x18001780f  pop     rdi
0x180017810  pop     rsi
0x180017811  pop     rbx
0x180017812  pop     rbp
0x180017813  retn
0x180017814  call    cs:__imp_RegCloseKey
0x18001781a  mov     [rbp+hKey], rsi
0x18001781e  jmp     short loc_1800177FC
0x180017820  mov     rcx, [rbp+var_10]; hKey
0x180017824  lea     rax, [rbp+cbData]
0x180017828  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18001782d  lea     r9, [rbp+Type]; lpType
0x180017831  lea     rax, [rbp+Data]
0x180017835  mov     [rbp+cbData], 4
0x18001783c  xor     r8d, r8d; lpReserved
0x18001783f  mov     [rsp+48h+phkResult], rax; lpData
0x180017844  lea     rdx, aStaginginprogr; "StagingInProgress"
0x18001784b  mov     [rbp+Data], esi
0x18001784e  call    cs:__imp_RegQueryValueExW
0x180017854  test    eax, eax
0x180017856  jnz     loc_18001774A
0x18001785c  cmp     [rbp+Data], esi
0x18001785f  jz      loc_18001774A
0x180017865  lea     rdx, aAuinstallagent_0; "AUINSTALLAGENT_REG_STAGINGINPROGRESS in"...
0x18001786c  jmp     short loc_18001789F
0x18001786e  mov     r8d, eax
0x180017871  lea     rdx, aTsSysprepKeyFa; "TS_SYSPREP_KEY failed with 0x%08x"
0x180017878  mov     ecx, ebx; int
0x18001787a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001787f  mov     edi, esi
0x180017881  jmp     loc_1800177F3
0x180017886  cmp     [rbp+Data], esi
0x180017889  jz      loc_1800177B0
0x18001788f  lea     rdx, aTsSysprepInpro; "TS_SYSPREP_INPROGRESS in progress"
0x180017896  jmp     short loc_18001789F
0x180017898  lea     rdx, aTsOobeInprogre; "TS_OOBE_INPROGRESS in progress"
0x18001789f  mov     ecx, ebx; int
0x1800178a1  mov     edi, ebx
0x1800178a3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800178a8  jmp     loc_1800177F3
0x1800178ad  call    cs:__imp_RegCloseKey
0x1800178b3  jmp     loc_180017809
```
