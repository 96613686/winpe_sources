# DsRolepRestoreDnsRegistrationSettings

- ea: `0x18000fb64`
- end: `0x18000fdaa`
- name: `DsRolepRestoreDnsRegistrationSettings`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180012460`

## callees

- `0x18000fb64`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fcb3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fcb3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fc0d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fc64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fc0d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fc64`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000fce1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000fce1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fd4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fd6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fd4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fd6a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fd10`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fd10`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000fd7e`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000fd7e`

## string_xrefs

- `0x18000fb72`: `SYSTEM\CurrentControlSet\Services\Dnscache\Parameters`
- `0x18000fba5`: `SYSTEM\CurrentControlSet\Services\Netlogon\Parameters`
- `0x18000fbcc`: `SYSTEM\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18000fbd7`: `DisableDynamicUpdate`
- `0x18000fbff`: `SYSTEM\CurrentControlSet\Services\NTDS\Parameters\PostCloningRestore`
- `0x18000fc1c`: `SYSTEM\CurrentControlSet\Services\NTDS\Parameters\PostCloningRestore`
- `0x18000fd70`: `SYSTEM\CurrentControlSet\Services\NTDS\Parameters\PostCloningRestore`
- `0x18000fd84`: `SYSTEM\CurrentControlSet\Services\NTDS\Parameters\PostCloningRestore`
- `0x18000fc23`: `vDC Cloning: RegOpenKeyExW(%ws) status 0x%x\n`
- `0x18000fc71`: `vDC Cloning: RegOpenKeyExW(%ws) status 0x%x\n`
- `0x18000fd16`: `vDC Cloning: delete %ws value, status 0x%x\n`
- `0x18000fd91`: `vDC Cloning: delete %ws key, status 0x%x\n`

## pseudocode

```c
__int64 DsRolepRestoreDnsRegistrationSettings()
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  __int64 i; // rbx
  const WCHAR *v4; // rsi
  unsigned int v5; // eax
  const WCHAR *v6; // rdi
  unsigned int v7; // eax
  const char *v8; // rdx
  __int64 v9; // rcx
  unsigned int v10; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-50h]
  HKEY hKey; // [rsp+30h] [rbp-40h] BYREF
  LPCWSTR lpSubKey; // [rsp+38h] [rbp-38h]
  LPCWSTR lpValueName[6]; // [rsp+40h] [rbp-30h]
  unsigned int Data; // [rsp+A0h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+A8h] [rbp+38h] BYREF
  DWORD Type; // [rsp+B0h] [rbp+40h] BYREF
  HKEY v18; // [rsp+B8h] [rbp+48h] BYREF

  v18 = 0;
  lpSubKey = L"SYSTEM\\CurrentControlSet\\Services\\Dnscache\\Parameters";
  hKey = 0;
  lpValueName[0] = L"RegistrationEnabled";
  cbData = 0;
  lpValueName[1] = L"SYSTEM\\CurrentControlSet\\Services\\Netlogon\\Parameters";
  Type = 0;
  lpValueName[2] = L"UseDynamicDns";
  lpValueName[3] = L"SYSTEM\\CurrentControlSet\\Services\\Tcpip\\Parameters";
  lpValueName[4] = L"DisableDynamicUpdate";
  Data = 0;
  DsRolepLogPrintRoutine(4, "vDC Cloning: DsRolepRestoreDnsRegistrationSettings\n");
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\NTDS\\Parameters\\PostCloningRestore",
         0,
         1u,
         &hKey);
  v1 = v0;
  if ( v0 )
  {
    DsRolepLogPrintRoutine(
      1,
      "vDC Cloning: RegOpenKeyExW(%ws) status 0x%x\n",
      L"SYSTEM\\CurrentControlSet\\Services\\NTDS\\Parameters\\PostCloningRestore",
      v0);
    return v1;
  }
  for ( i = 0; i != 3; ++i )
  {
    v4 = lpValueName[2 * i - 1];
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 2u, &v18);
    if ( v5 )
    {
      DsRolepLogPrintRoutine(1, "vDC Cloning: RegOpenKeyExW(%ws) status 0x%x\n", v4, v5);
      continue;
    }
    v6 = lpValueName[2 * i];
    cbData = 4;
    v7 = RegQueryValueExW(hKey, v6, 0, &Type, (LPBYTE)&Data, &cbData);
    if ( v7 )
    {
      v8 = "vDC Cloning: RegQueryValueExW(%ws) status 0x%x\n";
      v9 = 1;
      goto LABEL_13;
    }
    if ( Type != 4 )
    {
      if ( Type != 3 )
      {
        DsRolepLogPrintRoutine(1, "vDC Cloning: RegQueryValueExW(%ws), unexpected value type %d\n", v6, Type);
        goto LABEL_14;
      }
      v7 = RegDeleteValueW(v18, v6);
      v8 = "vDC Cloning: delete %ws value, status 0x%x\n";
      v9 = 4;
LABEL_13:
      DsRolepLogPrintRoutine(v9, v8, v6, v7);
      goto LABEL_14;
    }
    LODWORD(phkResult) = RegSetValueExW(v18, v6, 0, 4u, (const BYTE *)&Data, 4u);
    DsRolepLogPrintRoutine(4, "vDC Cloning: restore %ws value (0x%x), status 0x%x\n", v6, Data, phkResult);
LABEL_14:
    RegCloseKey(v18);
    v18 = 0;
  }
  RegCloseKey(hKey);
  v10 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\NTDS\\Parameters\\PostCloningRestore");
  DsRolepLogPrintRoutine(
    4,
    "vDC Cloning: delete %ws key, status 0x%x\n",
    L"SYSTEM\\CurrentControlSet\\Services\\NTDS\\Parameters\\PostCloningRestore",
    v10);
  return 0;
}

```

## disassembly

```asm
0x18000fb64  push    rbp
0x18000fb66  push    rbx
0x18000fb67  push    rsi
0x18000fb68  push    rdi
0x18000fb69  push    r12
0x18000fb6b  mov     rbp, rsp
0x18000fb6e  sub     rsp, 70h
0x18000fb72  lea     rax, aSystemCurrentc_9; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18000fb79  mov     [rbp+arg_18], 0
0x18000fb81  mov     [rbp+lpSubKey], rax
0x18000fb85  lea     rdx, aVdcCloningDsro; "vDC Cloning: DsRolepRestoreDnsRegistrat"...
0x18000fb8c  lea     rax, aRegistrationen; "RegistrationEnabled"
0x18000fb93  mov     [rbp+hKey], 0
0x18000fb9b  mov     [rbp+lpValueName], rax
0x18000fb9f  mov     r12d, 4
0x18000fba5  lea     rax, aSystemCurrentc_10; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x18000fbac  mov     [rbp+cbData], 0
0x18000fbb3  mov     [rbp+var_28], rax
0x18000fbb7  mov     ecx, r12d
0x18000fbba  lea     rax, aUsedynamicdns; "UseDynamicDns"
0x18000fbc1  mov     [rbp+Type], 0
0x18000fbc8  mov     [rbp+var_20], rax
0x18000fbcc  lea     rax, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Services\\Tc"...
0x18000fbd3  mov     [rbp+var_18], rax
0x18000fbd7  lea     rax, aDisabledynamic; "DisableDynamicUpdate"
0x18000fbde  mov     [rbp+var_10], rax
0x18000fbe2  mov     [rbp+Data], 0
0x18000fbe9  call    DsRolepLogPrintRoutine
0x18000fbee  lea     rax, [rbp+hKey]
0x18000fbf2  xor     r8d, r8d; ulOptions
0x18000fbf5  lea     r9d, [r12-3]; samDesired
0x18000fbfa  mov     [rsp+70h+phkResult], rax; phkResult
0x18000fbff  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\NT"...
0x18000fc06  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000fc0d  call    cs:__imp_RegOpenKeyExW
0x18000fc13  mov     ebx, eax
0x18000fc15  test    eax, eax
0x18000fc17  jz      short loc_18000FC3B
0x18000fc19  mov     r9d, eax
0x18000fc1c  lea     r8, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\NT"...
0x18000fc23  lea     rdx, aVdcCloningRego; "vDC Cloning: RegOpenKeyExW(%ws) status "...
0x18000fc2a  lea     ecx, [r12-3]
0x18000fc2f  call    DsRolepLogPrintRoutine
0x18000fc34  mov     eax, ebx
0x18000fc36  jmp     loc_18000FD9F
0x18000fc3b  xor     ebx, ebx
0x18000fc3d  lea     rax, [rbp+arg_18]
0x18000fc41  mov     rdi, rbx
0x18000fc44  add     rdi, rdi
0x18000fc47  mov     [rsp+70h+phkResult], rax; phkResult
0x18000fc4c  mov     r9d, 2; samDesired
0x18000fc52  xor     r8d, r8d; ulOptions
0x18000fc55  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000fc5c  mov     rsi, [rbp+rdi*8+lpSubKey]
0x18000fc61  mov     rdx, rsi; lpSubKey
0x18000fc64  call    cs:__imp_RegOpenKeyExW
0x18000fc6a  test    eax, eax
0x18000fc6c  jz      short loc_18000FC8A
0x18000fc6e  mov     r9d, eax
0x18000fc71  lea     rdx, aVdcCloningRego; "vDC Cloning: RegOpenKeyExW(%ws) status "...
0x18000fc78  mov     r8, rsi
0x18000fc7b  mov     ecx, 1
0x18000fc80  call    DsRolepLogPrintRoutine
0x18000fc85  jmp     loc_18000FD59
0x18000fc8a  mov     rdi, [rbp+rdi*8+lpValueName]
0x18000fc8f  lea     rax, [rbp+cbData]
0x18000fc93  mov     rcx, [rbp+hKey]; hKey
0x18000fc97  lea     r9, [rbp+Type]; lpType
0x18000fc9b  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18000fca0  xor     r8d, r8d; lpReserved
0x18000fca3  lea     rax, [rbp+Data]
0x18000fca7  mov     [rbp+cbData], r12d
0x18000fcab  mov     rdx, rdi; lpValueName
0x18000fcae  mov     [rsp+70h+phkResult], rax; lpData
0x18000fcb3  call    cs:__imp_RegQueryValueExW
0x18000fcb9  test    eax, eax
0x18000fcbb  jnz     short loc_18000FD30
0x18000fcbd  mov     r9d, [rbp+Type]
0x18000fcc1  cmp     r9d, r12d
0x18000fcc4  jnz     short loc_18000FD03
0x18000fcc6  mov     rcx, [rbp+arg_18]; hKey
0x18000fcca  lea     rax, [rbp+Data]
0x18000fcce  mov     dword ptr [rsp+70h+lpcbData], r12d; cbData
0x18000fcd3  mov     r9d, r12d; dwType
0x18000fcd6  xor     r8d, r8d; Reserved
0x18000fcd9  mov     [rsp+70h+phkResult], rax; lpData
0x18000fcde  mov     rdx, rdi; lpValueName
0x18000fce1  call    cs:__imp_RegSetValueExW
0x18000fce7  mov     r9d, [rbp+Data]
0x18000fceb  lea     rdx, aVdcCloningRest; "vDC Cloning: restore %ws value (0x%x), "...
0x18000fcf2  mov     r8, rdi
0x18000fcf5  mov     dword ptr [rsp+70h+phkResult], eax
0x18000fcf9  mov     ecx, r12d
0x18000fcfc  call    DsRolepLogPrintRoutine
0x18000fd01  jmp     short loc_18000FD47
0x18000fd03  cmp     r9d, 3
0x18000fd07  jnz     short loc_18000FD22
0x18000fd09  mov     rcx, [rbp+arg_18]; hKey
0x18000fd0d  mov     rdx, rdi; lpValueName
0x18000fd10  call    cs:__imp_RegDeleteValueW
0x18000fd16  lea     rdx, aVdcCloningDele_2; "vDC Cloning: delete %ws value, status 0"...
0x18000fd1d  mov     ecx, r12d
0x18000fd20  jmp     short loc_18000FD3C
0x18000fd22  lea     rdx, aVdcCloningRegq; "vDC Cloning: RegQueryValueExW(%ws), une"...
0x18000fd29  mov     ecx, 1
0x18000fd2e  jmp     short loc_18000FD3F
0x18000fd30  lea     rdx, aVdcCloningRegq_0; "vDC Cloning: RegQueryValueExW(%ws) stat"...
0x18000fd37  mov     ecx, 1
0x18000fd3c  mov     r9d, eax
0x18000fd3f  mov     r8, rdi
0x18000fd42  call    DsRolepLogPrintRoutine
0x18000fd47  mov     rcx, [rbp+arg_18]; hKey
0x18000fd4b  call    cs:__imp_RegCloseKey
0x18000fd51  mov     [rbp+arg_18], 0
0x18000fd59  inc     rbx
0x18000fd5c  cmp     rbx, 3
0x18000fd60  jnz     loc_18000FC3D
0x18000fd66  mov     rcx, [rbp+hKey]; hKey
0x18000fd6a  call    cs:__imp_RegCloseKey
0x18000fd70  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\NT"...
0x18000fd77  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000fd7e  call    cs:__imp_RegDeleteKeyW
0x18000fd84  lea     r8, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\NT"...
0x18000fd8b  mov     ecx, r12d
0x18000fd8e  mov     r9d, eax
0x18000fd91  lea     rdx, aVdcCloningDele_1; "vDC Cloning: delete %ws key, status 0x%"...
0x18000fd98  call    DsRolepLogPrintRoutine
0x18000fd9d  xor     eax, eax
0x18000fd9f  add     rsp, 70h
0x18000fda3  pop     r12
0x18000fda5  pop     rdi
0x18000fda6  pop     rsi
0x18000fda7  pop     rbx
0x18000fda8  pop     rbp
0x18000fda9  retn
```
