# CRdlsDBManager::LogSettingsTelemetryData(int)

- ea: `0x18007e864`
- end: `0x18007ea70`
- name: `?LogSettingsTelemetryData@CRdlsDBManager@@QEAAXH@Z`
- size: `524`
- prototype: `void __fastcall(CRdlsDBManager *__hidden this, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180037a5c`

## callees

- `0x18007e864`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18007e8fa`
- `ADVAPI32!RegQueryValueExW` at `0x18007e930`
- `ADVAPI32!RegQueryValueExW` at `0x18007e966`
- `ADVAPI32!RegQueryValueExW` at `0x18007e994`
- `ADVAPI32!RegQueryValueExW` at `0x18007e9cb`
- `ADVAPI32!RegQueryValueExW` at `0x18007ea00`
- `ADVAPI32!RegQueryValueExW` at `0x18007e8fa`
- `ADVAPI32!RegQueryValueExW` at `0x18007e930`
- `ADVAPI32!RegQueryValueExW` at `0x18007e966`
- `ADVAPI32!RegQueryValueExW` at `0x18007e994`
- `ADVAPI32!RegQueryValueExW` at `0x18007e9cb`
- `ADVAPI32!RegQueryValueExW` at `0x18007ea00`
- `ADVAPI32!RegOpenKeyExW` at `0x18007e8bc`
- `ADVAPI32!RegOpenKeyExW` at `0x18007e8bc`
- `ADVAPI32!RegCloseKey` at `0x18007ea20`
- `ADVAPI32!RegCloseKey` at `0x18007ea20`
- `lstelemetry!LogRDLSSettingsTelemetryData` at `0x18007ea4f`
- `lstelemetry!LogRDLSSettingsTelemetryData` at `0x18007ea4f`

## string_xrefs

- `0x18007e89c`: `SYSTEM\CurrentControlSet\Services\TermServLicensing\Parameters`

## pseudocode

```c
void __fastcall CRdlsDBManager::LogSettingsTelemetryData(CRdlsDBManager *this, int a2)
{
  LPBYTE v2; // r14
  int v3; // ebx
  int v5; // edi
  BYTE Data[4]; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-8h] BYREF
  CRdlsDBManager *cbData; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v9; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v10; // [rsp+98h] [rbp+48h] BYREF

  cbData = this;
  v2 = g_RdlsDBManager;
  v3 = 0;
  v10 = 2;
  hKey = 0;
  *(_DWORD *)Data = 0;
  v9 = 1;
  v5 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\TermServLicensing\\Parameters",
          0,
          1u,
          &hKey) )
  {
    LODWORD(cbData) = 4;
    RegQueryValueExW(hKey, L"IsSQLDB", 0, 0, Data, (LPDWORD)&cbData);
    LODWORD(cbData) = 4;
    RegQueryValueExW(hKey, L"TransactionLockMethod", 0, 0, (LPBYTE)&v10, (LPDWORD)&cbData);
    LODWORD(cbData) = 4;
    RegQueryValueExW(hKey, L"UseIntegratedAuth", 0, 0, (LPBYTE)&v9, (LPDWORD)&cbData);
  }
  LODWORD(cbData) = 0;
  if ( !RegQueryValueExW(hKey, L"SqlConnString", 0, 0, 0, (LPDWORD)&cbData) && (unsigned int)cbData > 2 )
    v5 = 1;
  if ( RegQueryValueExW(hKey, L"SqlServerUserName", 0, 0, 0, (LPDWORD)&cbData)
    || (unsigned int)cbData <= 2
    || RegQueryValueExW(hKey, L"SqlServerUserPwd", 0, 0, 0, (LPDWORD)&cbData)
    || (unsigned int)cbData <= 2 )
  {
    v3 = 1;
  }
  v9 = v3;
  RegCloseKey(hKey);
  LogRDLSSettingsTelemetryData(3, *(unsigned int *)Data, v10, v9, v5, *((_DWORD *)v2 + 655), a2);
}

```

## disassembly

```asm
0x18007e864  mov     [rsp-28h+arg_8], rbx
0x18007e869  mov     [rsp-28h+cbData], rcx
0x18007e86e  push    rbp
0x18007e86f  push    rsi
0x18007e870  push    rdi
0x18007e871  push    r13
0x18007e873  push    r14
0x18007e875  mov     rbp, rsp
0x18007e878  sub     rsp, 50h
0x18007e87c  mov     r14, cs:?g_RdlsDBManager@@3PEAVCRdlsDBManager@@EA; CRdlsDBManager * g_RdlsDBManager
0x18007e883  lea     rax, [rbp+hKey]
0x18007e887  xor     ebx, ebx
0x18007e889  mov     [rbp+arg_18], 2
0x18007e890  mov     esi, edx
0x18007e892  mov     [rbp+hKey], rbx
0x18007e896  xor     r8d, r8d; ulOptions
0x18007e899  mov     dword ptr [rbp+Data], ebx
0x18007e89c  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Te"...
0x18007e8a3  mov     [rsp+50h+phkResult], rax; phkResult
0x18007e8a8  lea     r13d, [rbx+1]
0x18007e8ac  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007e8b3  mov     r9d, r13d; samDesired
0x18007e8b6  mov     [rbp+arg_10], r13d
0x18007e8ba  mov     edi, ebx
0x18007e8bc  call    cs:__imp_RegOpenKeyExW
0x18007e8c3  nop     dword ptr [rax+rax+00h]
0x18007e8c8  test    eax, eax
0x18007e8ca  jnz     loc_18007E972
0x18007e8d0  mov     rcx, [rbp+hKey]; hKey
0x18007e8d4  lea     rax, [rbp+cbData]
0x18007e8d8  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18007e8dd  lea     rdx, aIssqldb; "IsSQLDB"
0x18007e8e4  lea     rax, [rbp+Data]
0x18007e8e8  mov     dword ptr [rbp+cbData], 4
0x18007e8ef  xor     r9d, r9d; lpType
0x18007e8f2  mov     [rsp+50h+phkResult], rax; lpData
0x18007e8f7  xor     r8d, r8d; lpReserved
0x18007e8fa  call    cs:__imp_RegQueryValueExW
0x18007e901  nop     dword ptr [rax+rax+00h]
0x18007e906  mov     rcx, [rbp+hKey]; hKey
0x18007e90a  lea     rax, [rbp+cbData]
0x18007e90e  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18007e913  lea     rdx, aTransactionloc; "TransactionLockMethod"
0x18007e91a  lea     rax, [rbp+arg_18]
0x18007e91e  mov     dword ptr [rbp+cbData], 4
0x18007e925  xor     r9d, r9d; lpType
0x18007e928  mov     [rsp+50h+phkResult], rax; lpData
0x18007e92d  xor     r8d, r8d; lpReserved
0x18007e930  call    cs:__imp_RegQueryValueExW
0x18007e937  nop     dword ptr [rax+rax+00h]
0x18007e93c  mov     rcx, [rbp+hKey]; hKey
0x18007e940  lea     rax, [rbp+cbData]
0x18007e944  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18007e949  lea     rdx, aUseintegrateda; "UseIntegratedAuth"
0x18007e950  lea     rax, [rbp+arg_10]
0x18007e954  mov     dword ptr [rbp+cbData], 4
0x18007e95b  xor     r9d, r9d; lpType
0x18007e95e  mov     [rsp+50h+phkResult], rax; lpData
0x18007e963  xor     r8d, r8d; lpReserved
0x18007e966  call    cs:__imp_RegQueryValueExW
0x18007e96d  nop     dword ptr [rax+rax+00h]
0x18007e972  mov     rcx, [rbp+hKey]; hKey
0x18007e976  lea     rax, [rbp+cbData]
0x18007e97a  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18007e97f  lea     rdx, aSqlconnstring; "SqlConnString"
0x18007e986  xor     r9d, r9d; lpType
0x18007e989  mov     [rsp+50h+phkResult], rbx; lpData
0x18007e98e  xor     r8d, r8d; lpReserved
0x18007e991  mov     dword ptr [rbp+cbData], ebx
0x18007e994  call    cs:__imp_RegQueryValueExW
0x18007e99b  nop     dword ptr [rax+rax+00h]
0x18007e9a0  test    eax, eax
0x18007e9a2  jnz     short loc_18007E9AC
0x18007e9a4  cmp     dword ptr [rbp+cbData], 2
0x18007e9a8  cmova   edi, r13d
0x18007e9ac  mov     rcx, [rbp+hKey]; hKey
0x18007e9b0  lea     rax, [rbp+cbData]
0x18007e9b4  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18007e9b9  lea     rdx, aSqlserverusern; "SqlServerUserName"
0x18007e9c0  xor     r9d, r9d; lpType
0x18007e9c3  mov     [rsp+50h+phkResult], rbx; lpData
0x18007e9c8  xor     r8d, r8d; lpReserved
0x18007e9cb  call    cs:__imp_RegQueryValueExW
0x18007e9d2  nop     dword ptr [rax+rax+00h]
0x18007e9d7  test    eax, eax
0x18007e9d9  jnz     short loc_18007EA16
0x18007e9db  cmp     dword ptr [rbp+cbData], 2
0x18007e9df  jbe     short loc_18007EA16
0x18007e9e1  mov     rcx, [rbp+hKey]; hKey
0x18007e9e5  lea     rax, [rbp+cbData]
0x18007e9e9  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18007e9ee  lea     rdx, aSqlserveruserp; "SqlServerUserPwd"
0x18007e9f5  xor     r9d, r9d; lpType
0x18007e9f8  mov     [rsp+50h+phkResult], rbx; lpData
0x18007e9fd  xor     r8d, r8d; lpReserved
0x18007ea00  call    cs:__imp_RegQueryValueExW
0x18007ea07  nop     dword ptr [rax+rax+00h]
0x18007ea0c  test    eax, eax
0x18007ea0e  jnz     short loc_18007EA16
0x18007ea10  cmp     dword ptr [rbp+cbData], 2
0x18007ea14  ja      short loc_18007EA19
0x18007ea16  mov     ebx, r13d
0x18007ea19  mov     rcx, [rbp+hKey]; hKey
0x18007ea1d  mov     [rbp+arg_10], ebx
0x18007ea20  call    cs:__imp_RegCloseKey
0x18007ea27  nop     dword ptr [rax+rax+00h]
0x18007ea2c  mov     eax, [r14+0A3Ch]
0x18007ea33  mov     ecx, 3
0x18007ea38  mov     r9d, [rbp+arg_10]
0x18007ea3c  mov     r8d, [rbp+arg_18]
0x18007ea40  mov     edx, dword ptr [rbp+Data]
0x18007ea43  mov     [rsp+50h+var_20], esi
0x18007ea47  mov     dword ptr [rsp+50h+lpcbData], eax
0x18007ea4b  mov     dword ptr [rsp+50h+phkResult], edi
0x18007ea4f  call    cs:__imp_?LogRDLSSettingsTelemetryData@@YAKW4TelemetryLogLevel@@KKKKKK@Z; LogRDLSSettingsTelemetryData(TelemetryLogLevel,ulong,ulong,ulong,ulong,ulong,ulong)
0x18007ea56  nop     dword ptr [rax+rax+00h]
0x18007ea5b  mov     rbx, [rsp+50h+arg_8]
0x18007ea63  add     rsp, 50h
0x18007ea67  pop     r14
0x18007ea69  pop     r13
0x18007ea6b  pop     rdi
0x18007ea6c  pop     rsi
0x18007ea6d  pop     rbp
0x18007ea6e  retn
```
