# QueryServicePackUpgradeValues

- ea: `0x18009c348`
- end: `0x18009c5c5`
- name: `QueryServicePackUpgradeValues`
- size: `637`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x18007e088`

## callees

- `0x18003e984`
- `0x18004ede0`
- `0x18009c1f8`
- `0x18009c2a0`
- `0x18009c348`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18009c56c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18009c56c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c469`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18009c548`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18009c586`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18009c548`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18009c586`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009c3fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009c446`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009c4d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009c3fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009c446`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009c4d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009c4f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009c4f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009c3cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009c3cb`
- `SPOOLSS!DllFreeSplMem` at `0x18009c455`
- `SPOOLSS!DllFreeSplMem` at `0x18009c455`
- `SPOOLSS!DllAllocSplMem` at `0x18009c418`
- `SPOOLSS!DllAllocSplMem` at `0x18009c418`

## string_xrefs

- `0x18009c596`: `Retry failed to remove PostSPUpgrade key with error: %lu.`
- `0x18009c370`: `QueryServicePackUpgradeValues`
- `0x18009c514`: `No valid drivers to Upgrade, clear the Service Pack flag`

## pseudocode

```c
__int64 __fastcall QueryServicePackUpgradeValues(BYTE **a1, int *a2)
{
  BYTE *v4; // rdi
  unsigned int v5; // ebx
  DWORD LastError; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-20h]
  unsigned int v11; // [rsp+30h] [rbp-10h] BYREF
  LSTATUS v12; // [rsp+34h] [rbp-Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  DWORD Type; // [rsp+80h] [rbp+40h] BYREF
  int Data; // [rsp+88h] [rbp+48h] BYREF

  hKey = 0;
  cbData = 0;
  Type = 0;
  v4 = 0;
  Data = 0;
  LocalSpoolerTelemetry::WriteDbgTraceInfo("QueryServicePackUpgradeValues", L"Enter");
  if ( !a1 || !a2 )
  {
    v5 = 87;
    goto LABEL_21;
  }
  *a2 = 3;
  *a1 = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Print\\PostSPUpgrade", 0, 1u, &hKey);
  if ( !v5 )
  {
    v12 = RegQueryValueExW(hKey, L"UpgradedDrivers", 0, &Type, 0, &cbData);
    v5 = v12;
    if ( v12 || Type != 7 || cbData <= 2 )
    {
      v11 = 0;
      LocalSpoolerTelemetry::CleanupSPUpgradeRegistry<unsigned long &,int,unsigned short const (&)[14]>(&v12, &v11);
      LODWORD(phkResult) = cbData;
      LocalSpoolerTelemetry::WriteDbgTraceInfo(
        "QueryServicePackUpgradeValues",
        L"Querying 'UpgradedDrivers' failed: Error: %lu Type: %lu Size: %lu",
        v5,
        Type,
        phkResult);
    }
    else
    {
      v4 = (BYTE *)DllAllocSplMem(cbData);
      if ( !v4 )
      {
        LastError = GetLastError();
        v5 = LastError;
        goto LABEL_14;
      }
      v5 = RegQueryValueExW(hKey, L"UpgradedDrivers", 0, &Type, v4, &cbData);
      if ( v5 )
      {
        DllFreeSplMem(v4);
        v4 = 0;
      }
      else
      {
        LocalSpoolerTelemetry::UpgradedDrivers((const unsigned __int16 *)v4, cbData);
      }
    }
    LastError = v5;
LABEL_14:
    if ( !LastError )
    {
      if ( v4 )
      {
        cbData = 4;
        if ( RegQueryValueExW(hKey, L"UpgradedDrvVer", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
          Data = 3;
      }
    }
    RegCloseKey(hKey);
  }
LABEL_21:
  if ( v5 || !v4 )
  {
    LocalSpoolerTelemetry::WriteDbgTraceInfo(
      "QueryServicePackUpgradeValues",
      L"No valid drivers to Upgrade, clear the Service Pack flag");
    dwSPUpgradeFlag = 0;
    v11 = 0;
    v7 = RegDeleteKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Print\\PostSPUpgrade", 0, 0);
    v12 = v7;
    if ( v7 )
    {
      LocalSpoolerTelemetry::WriteDbgTraceInfo(
        "QueryServicePackUpgradeValues",
        L"Removing PostSPUpgrade key failed with error: %lu. Retrying...",
        v7);
      Sleep(0x1F4u);
      v8 = RegDeleteKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Print\\PostSPUpgrade", 0, 0);
      v11 = v8;
      if ( v8 )
        LocalSpoolerTelemetry::WriteDbgTraceInfo(
          "QueryServicePackUpgradeValues",
          L"Retry failed to remove PostSPUpgrade key with error: %lu.",
          v8);
    }
    LocalSpoolerTelemetry::CleanupSPUpgradeRegistry<unsigned long &,unsigned long &,unsigned short const (&)[30]>(
      &v12,
      &v11);
  }
  else
  {
    *a2 = Data;
    *a1 = v4;
  }
  return v5;
}

```

## disassembly

```asm
0x18009c348  mov     [rsp-28h+arg_8], rbx
0x18009c34d  push    rbp
0x18009c34e  push    rsi
0x18009c34f  push    rdi
0x18009c350  push    r12
0x18009c352  push    r14
0x18009c354  mov     rbp, rsp
0x18009c357  sub     rsp, 40h
0x18009c35b  mov     rsi, rdx
0x18009c35e  mov     [rbp+hKey], 0
0x18009c366  mov     r14, rcx
0x18009c369  mov     [rbp+cbData], 0
0x18009c370  lea     r12, aQueryservicepa; "QueryServicePackUpgradeValues"
0x18009c377  mov     [rbp+Type], 0
0x18009c37e  xor     edi, edi
0x18009c380  lea     rdx, aEnter; "Enter"
0x18009c387  mov     rcx, r12; char *
0x18009c38a  mov     [rbp+Data], edi
0x18009c38d  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18009c392  test    r14, r14
0x18009c395  jz      loc_18009C4F9
0x18009c39b  test    rsi, rsi
0x18009c39e  jz      loc_18009C4F9
0x18009c3a4  lea     rax, [rbp+hKey]
0x18009c3a8  mov     dword ptr [rsi], 3
0x18009c3ae  lea     r9d, [rdi+1]; samDesired
0x18009c3b2  mov     [rsp+40h+phkResult], rax; phkResult
0x18009c3b7  xor     r8d, r8d; ulOptions
0x18009c3ba  mov     [r14], rdi
0x18009c3bd  lea     rdx, szPostSPUpgradePath; "System\\CurrentControlSet\\Control\\Pri"...
0x18009c3c4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009c3cb  call    cs:__imp_RegOpenKeyExW
0x18009c3d1  mov     ebx, eax
0x18009c3d3  test    eax, eax
0x18009c3d5  jnz     loc_18009C4FE
0x18009c3db  mov     rcx, [rbp+hKey]; hKey
0x18009c3df  lea     rax, [rbp+cbData]
0x18009c3e3  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18009c3e8  lea     r9, [rbp+Type]; lpType
0x18009c3ec  xor     r8d, r8d; lpReserved
0x18009c3ef  mov     [rsp+40h+phkResult], rdi; lpData
0x18009c3f4  lea     rdx, szPostSPUpgradeString; "UpgradedDrivers"
0x18009c3fb  call    cs:__imp_RegQueryValueExW
0x18009c401  mov     [rbp+var_C], eax
0x18009c404  mov     ebx, eax
0x18009c406  test    eax, eax
0x18009c408  jnz     short loc_18009C473
0x18009c40a  cmp     [rbp+Type], 7
0x18009c40e  jnz     short loc_18009C473
0x18009c410  mov     ecx, [rbp+cbData]
0x18009c413  cmp     ecx, 2
0x18009c416  jbe     short loc_18009C473
0x18009c418  call    cs:__imp_DllAllocSplMem
0x18009c41e  mov     rdi, rax
0x18009c421  test    rax, rax
0x18009c424  jz      short loc_18009C469
0x18009c426  mov     rcx, [rbp+hKey]; hKey
0x18009c42a  lea     rax, [rbp+cbData]
0x18009c42e  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18009c433  lea     r9, [rbp+Type]; lpType
0x18009c437  xor     r8d, r8d; lpReserved
0x18009c43a  mov     [rsp+40h+phkResult], rdi; lpData
0x18009c43f  lea     rdx, szPostSPUpgradeString; "UpgradedDrivers"
0x18009c446  call    cs:__imp_RegQueryValueExW
0x18009c44c  mov     ebx, eax
0x18009c44e  mov     rcx, rdi; Src
0x18009c451  test    eax, eax
0x18009c453  jz      short loc_18009C45F
0x18009c455  call    cs:__imp_DllFreeSplMem
0x18009c45b  xor     edi, edi
0x18009c45d  jmp     short loc_18009C4A0
0x18009c45f  mov     edx, [rbp+cbData]; unsigned int
0x18009c462  call    ?UpgradedDrivers@LocalSpoolerTelemetry@@SAXPEBGK@Z; LocalSpoolerTelemetry::UpgradedDrivers(ushort const *,ulong)
0x18009c467  jmp     short loc_18009C4A0
0x18009c469  call    cs:__imp_GetLastError
0x18009c46f  mov     ebx, eax
0x18009c471  jmp     short loc_18009C4A2
0x18009c473  lea     rdx, [rbp+var_10]
0x18009c477  mov     [rbp+var_10], edi
0x18009c47a  lea     rcx, [rbp+var_C]
0x18009c47e  call    ??$CleanupSPUpgradeRegistry@AEAKHAEAY0O@$$CBG@LocalSpoolerTelemetry@@SAXAEAK$$QEAHAEAY0O@$$CBG@Z; LocalSpoolerTelemetry::CleanupSPUpgradeRegistry<ulong &,int,ushort const (&)[14]>(ulong &,int &&,ushort const (&)[14])
0x18009c483  mov     eax, [rbp+cbData]
0x18009c486  lea     rdx, aQueryingUpgrad; "Querying 'UpgradedDrivers' failed: Erro"...
0x18009c48d  mov     r9d, [rbp+Type]
0x18009c491  mov     r8d, ebx
0x18009c494  mov     rcx, r12; char *
0x18009c497  mov     dword ptr [rsp+40h+phkResult], eax
0x18009c49b  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18009c4a0  mov     eax, ebx
0x18009c4a2  test    eax, eax
0x18009c4a4  jnz     short loc_18009C4ED
0x18009c4a6  test    rdi, rdi
0x18009c4a9  jz      short loc_18009C4ED
0x18009c4ab  mov     rcx, [rbp+hKey]; hKey
0x18009c4af  lea     rax, [rbp+cbData]
0x18009c4b3  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18009c4b8  lea     r9, [rbp+Type]; lpType
0x18009c4bc  lea     rax, [rbp+Data]
0x18009c4c0  mov     [rbp+cbData], 4
0x18009c4c7  xor     r8d, r8d; lpReserved
0x18009c4ca  mov     [rsp+40h+phkResult], rax; lpData
0x18009c4cf  lea     rdx, szPostSPUpgradeVersion; "UpgradedDrvVer"
0x18009c4d6  call    cs:__imp_RegQueryValueExW
0x18009c4dc  test    eax, eax
0x18009c4de  jnz     short loc_18009C4E6
0x18009c4e0  cmp     [rbp+Type], 4
0x18009c4e4  jz      short loc_18009C4ED
0x18009c4e6  mov     [rbp+Data], 3
0x18009c4ed  mov     rcx, [rbp+hKey]; hKey
0x18009c4f1  call    cs:__imp_RegCloseKey
0x18009c4f7  jmp     short loc_18009C4FE
0x18009c4f9  mov     ebx, 57h ; 'W'
0x18009c4fe  test    ebx, ebx
0x18009c500  jnz     short loc_18009C514
0x18009c502  test    rdi, rdi
0x18009c505  jz      short loc_18009C514
0x18009c507  mov     eax, [rbp+Data]
0x18009c50a  mov     [rsi], eax
0x18009c50c  mov     [r14], rdi
0x18009c50f  jmp     loc_18009C5B2
0x18009c514  lea     rdx, aNoValidDrivers; "No valid drivers to Upgrade, clear the "...
0x18009c51b  mov     rcx, r12; char *
0x18009c51e  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18009c523  xor     r9d, r9d; Reserved
0x18009c526  mov     cs:dwSPUpgradeFlag, 0
0x18009c530  xor     r8d, r8d; samDesired
0x18009c533  mov     [rbp+var_10], 0
0x18009c53a  lea     rdx, szPostSPUpgradePath; "System\\CurrentControlSet\\Control\\Pri"...
0x18009c541  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009c548  call    cs:__imp_RegDeleteKeyExW
0x18009c54e  mov     [rbp+var_C], eax
0x18009c551  test    eax, eax
0x18009c553  jz      short loc_18009C5A5
0x18009c555  mov     r8d, eax
0x18009c558  lea     rdx, aRemovingPostsp; "Removing PostSPUpgrade key failed with "...
0x18009c55f  mov     rcx, r12; char *
0x18009c562  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18009c567  mov     ecx, 1F4h; dwMilliseconds
0x18009c56c  call    cs:__imp_Sleep
0x18009c572  xor     r9d, r9d; Reserved
0x18009c575  lea     rdx, szPostSPUpgradePath; "System\\CurrentControlSet\\Control\\Pri"...
0x18009c57c  xor     r8d, r8d; samDesired
0x18009c57f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009c586  call    cs:__imp_RegDeleteKeyExW
0x18009c58c  mov     [rbp+var_10], eax
0x18009c58f  test    eax, eax
0x18009c591  jz      short loc_18009C5A5
0x18009c593  mov     r8d, eax
0x18009c596  lea     rdx, aRetryFailedToR; "Retry failed to remove PostSPUpgrade ke"...
0x18009c59d  mov     rcx, r12; char *
0x18009c5a0  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18009c5a5  lea     rdx, [rbp+var_10]
0x18009c5a9  lea     rcx, [rbp+var_C]
0x18009c5ad  call    ??$CleanupSPUpgradeRegistry@AEAKAEAKAEAY0BO@$$CBG@LocalSpoolerTelemetry@@SAXAEAK0AEAY0BO@$$CBG@Z; LocalSpoolerTelemetry::CleanupSPUpgradeRegistry<ulong &,ulong &,ushort const (&)[30]>(ulong &,ulong &,ushort const (&)[30])
0x18009c5b2  mov     eax, ebx
0x18009c5b4  mov     rbx, [rsp+40h+arg_8]
0x18009c5b9  add     rsp, 40h
0x18009c5bd  pop     r14
0x18009c5bf  pop     r12
0x18009c5c1  pop     rdi
0x18009c5c2  pop     rsi
0x18009c5c3  pop     rbp
0x18009c5c4  retn
```
