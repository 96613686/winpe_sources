# PendingDriverUpgrades

- ea: `0x180028360`
- end: `0x180028803`
- name: `PendingDriverUpgrades`
- size: `1187`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x180071b90`
- `0x180078110`
- `0x18007e088`

## callees

- `0x180008520`
- `0x180008560`
- `0x180009630`
- `0x18000a100`
- `0x18000bb60`
- `0x18000d40c`
- `0x18000d944`
- `0x180028360`
- `0x18002880c`
- `0x1800288e4`
- `0x1800402c8`
- `0x180046650`
- `0x18006c1c0`
- `0x18006d430`
- `0x18006f624`
- `0x180070584`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800285c4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800285d9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800285c4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800285d9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002878a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002878a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800283f1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002842b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800283f1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002842b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028735`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028795`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800287c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800287d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028735`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028795`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800287c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800287d5`
- `SPOOLSS!DllFreeSplMem` at `0x1800286bc`
- `SPOOLSS!DllFreeSplMem` at `0x18002879f`
- `SPOOLSS!DllFreeSplMem` at `0x1800287a8`
- `SPOOLSS!DllFreeSplMem` at `0x1800286bc`
- `SPOOLSS!DllFreeSplMem` at `0x18002879f`
- `SPOOLSS!DllFreeSplMem` at `0x1800287a8`
- `SPOOLSS!DllAllocSplMem` at `0x18002869e`
- `SPOOLSS!DllAllocSplMem` at `0x18002869e`

## pseudocode

```c
void __fastcall PendingDriverUpgrades(__int64 a1)
{
  __int64 v1; // rcx
  struct _INIENVIRONMENT *v2; // r14
  struct _INIVERSION *v3; // r15
  struct _INIDRIVER *DriverEntry; // r13
  _QWORD *v5; // rbx
  unsigned int v6; // r12d
  unsigned int i; // edx
  DWORD j; // edx
  struct _INISPOOLER *v9; // rsi
  struct _DRIVER_INFO_8W *v10; // rdi
  LPWSTR pEnvironment; // rax
  LPWSTR v12; // rdx
  __int64 IniKey; // rax
  struct _INIVERSION *VersionEntry; // rax
  unsigned __int16 *v15; // rsi
  __int64 v16; // rax
  _QWORD *v17; // rsi
  HKEY v18; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v19; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v20; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v21; // [rsp+80h] [rbp-80h] BYREF
  int v22; // [rsp+84h] [rbp-7Ch]
  DWORD v23; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v24; // [rsp+90h] [rbp-70h] BYREF
  HKEY phkResult; // [rsp+98h] [rbp-68h] BYREF
  __int64 v26; // [rsp+A0h] [rbp-60h]
  struct _INTERNAL_DRV_FILE *v27; // [rsp+A8h] [rbp-58h] BYREF
  struct _DRIVER_INFO_8W *v28; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v29; // [rsp+B8h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v31[528]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v32[528]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v33[528]; // [rsp+4F0h] [rbp+3F0h] BYREF

  v26 = a1;
  v20 = 0;
  v21 = 0;
  v24 = 0;
  v29 = 0;
  hKey = 0;
  v18 = 0;
  phkResult = 0;
  v22 = 0;
  v28 = 0;
  EnterSplSem(0);
  if ( !RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Control\\Print",
          0,
          0,
          0,
          0x30019u,
          0,
          &hKey,
          0)
    && !RegCreateKeyExW(hKey, L"PendingUpgrades", 0, 0, 0, 0x30019u, 0, &phkResult, 0) )
  {
    v2 = 0;
    v3 = 0;
    DriverEntry = 0;
    v5 = 0;
    v6 = 0;
    for ( i = 0; ; i = v6 )
    {
      v18 = 0;
      if ( !(unsigned int)RestoreVersionKey(phkResult, i, (void **)&v18) )
        break;
      v23 = 0;
      for ( j = 0; ; j = v23 )
      {
        v27 = 0;
        v19 = 0;
        if ( !(unsigned int)RestoreParametersForUpgrade(
                              v18,
                              j,
                              &v24,
                              (unsigned __int8 **)&v29,
                              (unsigned __int8 *)&v20,
                              (unsigned __int8 *)&v21,
                              &v28) )
          break;
        v9 = pLocalIniSpooler;
        v10 = v28;
        if ( pLocalIniSpooler )
        {
          if ( v28->cVersion == 2 )
            goto LABEL_23;
          pEnvironment = v28->pEnvironment;
          v12 = szEnvironment;
          if ( pEnvironment && *pEnvironment )
            v12 = v28->pEnvironment;
          IniKey = FindIniKey(*((_QWORD *)pLocalIniSpooler + 6), v12, 0);
          v2 = (struct _INIENVIRONMENT *)IniKey;
          if ( IniKey )
          {
            VersionEntry = (struct _INIVERSION *)FindVersionEntry(IniKey, v10->cVersion);
            v3 = VersionEntry;
            if ( VersionEntry )
            {
              DriverEntry = FindDriverEntry(VersionEntry, v10->pName);
              if ( DriverEntry )
              {
                if ( !v26
                  || !(unsigned int)StrNCatBuff(v31, 260, *((_QWORD *)v9 + 4), L"\\drivers\\")
                  && (FindFileName(*((_QWORD *)DriverEntry + 4)), !(unsigned int)StrNCatBuff(v32, 260, v31, L"\\"))
                  && (FindFileName(*((_QWORD *)DriverEntry + 5)), !(unsigned int)StrNCatBuff(v33, 260, v31, L"\\"))
                  && (!(unsigned int)_o__wcsicmp(v26, v32) || !(unsigned int)_o__wcsicmp(v26, v33)) )
                {
                  if ( (unsigned int)CreateInternalDriverFileArray(v20, (unsigned __int8 *)v10, &v27, &v19, 0, v2, 1)
                    && (v10->cVersion == 2
                     || !(unsigned int)WaitRequiredForDriverUnload(v9, v2, v3, DriverEntry, v20, v10, 1, v27, v19)
                     && v22) )
                  {
LABEL_23:
                    RemoveDriverTempFiles(v9, v2, v3, DriverEntry);
                    v15 = v24;
                    if ( v24 && (v16 = DllAllocSplMem(24)) != 0 )
                    {
                      *(_QWORD *)v16 = v5;
                      v5 = (_QWORD *)v16;
                      *(_QWORD *)(v16 + 8) = v15;
                      *(_DWORD *)(v16 + 16) = v6;
                    }
                    else
                    {
                      DllFreeSplMem(v15);
                    }
                    v24 = 0;
                  }
                }
              }
            }
          }
        }
        CleanUpResources(v24, v29, v10, &v27, v19);
        ++v23;
      }
      RegCloseKey(v18);
      ++v6;
    }
    while ( 1 )
    {
      v17 = v5;
      if ( !v5 )
        break;
      v5 = (_QWORD *)*v5;
      v18 = 0;
      if ( (unsigned int)RestoreVersionKey(phkResult, *((_DWORD *)v17 + 4), (void **)&v18) )
      {
        RegDeleteKeyExW(v18, (LPCWSTR)v17[1], 0, 0);
        RegCloseKey(v18);
      }
      DllFreeSplMem(v17[1]);
      DllFreeSplMem(v17);
    }
  }
  LeaveSplSem(v1);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  CleanUpgradeDirectories();
}

```

## disassembly

```asm
0x180028360  push    rbp
0x180028362  push    rbx
0x180028363  push    rsi
0x180028364  push    rdi
0x180028365  push    r12
0x180028367  push    r13
0x180028369  push    r14
0x18002836b  push    r15
0x18002836d  lea     rbp, [rsp-618h]
0x180028375  sub     rsp, 718h
0x18002837c  mov     rax, cs:__security_cookie
0x180028383  xor     rax, rsp
0x180028386  mov     [rbp+650h+var_50], rax
0x18002838d  xor     edi, edi
0x18002838f  mov     [rbp+650h+var_6B0], rcx
0x180028393  xor     ecx, ecx
0x180028395  mov     [rsp+750h+var_6D4], edi
0x180028399  mov     [rbp+650h+var_6D0], edi
0x18002839c  mov     [rbp+650h+var_6C0], rdi
0x1800283a0  mov     [rbp+650h+var_698], rdi
0x1800283a4  mov     [rbp+650h+hKey], rdi
0x1800283a8  mov     [rsp+750h+var_6E0], rdi
0x1800283ad  mov     [rbp+650h+var_6B8], rdi
0x1800283b1  mov     [rbp+650h+var_6CC], edi
0x1800283b4  mov     [rbp+650h+var_6A0], rdi
0x1800283b8  call    EnterSplSem
0x1800283bd  mov     [rsp+750h+lpdwDisposition], rdi; lpdwDisposition
0x1800283c2  lea     rax, [rbp+650h+hKey]
0x1800283c6  mov     [rsp+750h+phkResult], rax; phkResult
0x1800283cb  lea     rdx, szRegistryRoot; "System\\CurrentControlSet\\Control\\Pri"...
0x1800283d2  mov     [rsp+750h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800283d7  mov     ebx, 30019h
0x1800283dc  mov     [rsp+750h+samDesired], ebx; samDesired
0x1800283e0  xor     r9d, r9d; lpClass
0x1800283e3  xor     r8d, r8d; Reserved
0x1800283e6  mov     [rsp+750h+dwOptions], edi; dwOptions
0x1800283ea  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800283f1  call    cs:__imp_RegCreateKeyExW
0x1800283f7  test    eax, eax
0x1800283f9  jnz     loc_1800287B8
0x1800283ff  mov     rcx, [rbp+650h+hKey]; hKey
0x180028403  lea     rax, [rbp+650h+var_6B8]
0x180028407  mov     [rsp+750h+lpdwDisposition], rdi; lpdwDisposition
0x18002840c  lea     rdx, szPendingUpgrades; "PendingUpgrades"
0x180028413  mov     [rsp+750h+phkResult], rax; phkResult
0x180028418  xor     r9d, r9d; lpClass
0x18002841b  mov     [rsp+750h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180028420  xor     r8d, r8d; Reserved
0x180028423  mov     [rsp+750h+samDesired], ebx; samDesired
0x180028427  mov     [rsp+750h+dwOptions], edi; dwOptions
0x18002842b  call    cs:__imp_RegCreateKeyExW
0x180028431  test    eax, eax
0x180028433  jnz     loc_1800287B8
0x180028439  mov     r14d, edi
0x18002843c  mov     r15d, edi
0x18002843f  mov     r13d, edi
0x180028442  mov     ebx, edi
0x180028444  mov     r12d, edi
0x180028447  xor     edx, edx
0x180028449  jmp     loc_180028741
0x18002844e  lea     rax, [rbp+650h+var_6A0]
0x180028452  mov     [rbp+650h+var_6C8], edi
0x180028455  mov     [rsp+750h+lpSecurityAttributes], rax
0x18002845a  xor     edx, edx
0x18002845c  lea     rax, [rbp+650h+var_6D0]
0x180028460  mov     qword ptr [rsp+750h+samDesired], rax
0x180028465  lea     rax, [rsp+750h+var_6D4]
0x18002846a  mov     qword ptr [rsp+750h+dwOptions], rax
0x18002846f  jmp     loc_18002870E
0x180028474  mov     rsi, cs:pLocalIniSpooler
0x18002847b  xor     ecx, ecx
0x18002847d  mov     rdi, [rbp+650h+var_6A0]
0x180028481  test    rsi, rsi
0x180028484  jz      loc_1800286CA
0x18002848a  cmp     dword ptr [rdi], 2
0x18002848d  jz      loc_18002867F
0x180028493  mov     rax, [rdi+10h]
0x180028497  lea     rdx, szEnvironment; "Windows x64"
0x18002849e  test    rax, rax
0x1800284a1  jz      short loc_1800284AA
0x1800284a3  cmp     [rax], cx
0x1800284a6  cmovnz  rdx, rax
0x1800284aa  mov     rcx, [rsi+30h]
0x1800284ae  xor     r8d, r8d
0x1800284b1  call    FindIniKey
0x1800284b6  mov     r14, rax
0x1800284b9  test    rax, rax
0x1800284bc  jz      loc_1800286CA
0x1800284c2  mov     edx, [rdi]
0x1800284c4  mov     rcx, rax
0x1800284c7  call    FindVersionEntry
0x1800284cc  mov     r15, rax
0x1800284cf  test    rax, rax
0x1800284d2  jz      loc_1800286CA
0x1800284d8  mov     rdx, [rdi+8]; unsigned __int16 *
0x1800284dc  mov     rcx, rax; struct _INIVERSION *
0x1800284df  call    ?FindDriverEntry@@YAPEAU_INIDRIVER@@PEAU_INIVERSION@@PEBG@Z; FindDriverEntry(_INIVERSION *,ushort const *)
0x1800284e4  mov     r13, rax
0x1800284e7  test    rax, rax
0x1800284ea  jz      loc_1800286CA
0x1800284f0  cmp     [rbp+650h+var_6B0], 0
0x1800284f5  jz      loc_1800285E7
0x1800284fb  mov     rcx, [r15+18h]
0x1800284ff  lea     rax, SubBlock; "\\"
0x180028506  mov     r8, [rsi+20h]
0x18002850a  lea     r9, aDrivers; "\\drivers\\"
0x180028511  mov     [rsp+750h+phkResult], 0
0x18002851a  mov     edx, 104h
0x18002851f  mov     [rsp+750h+lpSecurityAttributes], rcx
0x180028524  mov     rcx, [r14+28h]
0x180028528  mov     qword ptr [rsp+750h+samDesired], rax
0x18002852d  mov     qword ptr [rsp+750h+dwOptions], rcx
0x180028532  lea     rcx, [rbp+650h+var_680]
0x180028536  call    StrNCatBuff
0x18002853b  test    eax, eax
0x18002853d  jnz     loc_1800286CA
0x180028543  mov     rcx, [r13+20h]
0x180028547  call    FindFileName
0x18002854c  lea     r9, SubBlock; "\\"
0x180028553  mov     qword ptr [rsp+750h+samDesired], 0
0x18002855c  lea     r8, [rbp+650h+var_680]
0x180028560  mov     qword ptr [rsp+750h+dwOptions], rax
0x180028565  mov     edx, 104h
0x18002856a  lea     rcx, [rbp+650h+var_470]
0x180028571  call    StrNCatBuff
0x180028576  test    eax, eax
0x180028578  jnz     loc_1800286CA
0x18002857e  mov     rcx, [r13+28h]
0x180028582  call    FindFileName
0x180028587  lea     r9, SubBlock; "\\"
0x18002858e  mov     qword ptr [rsp+750h+samDesired], 0
0x180028597  lea     r8, [rbp+650h+var_680]
0x18002859b  mov     qword ptr [rsp+750h+dwOptions], rax
0x1800285a0  mov     edx, 104h
0x1800285a5  lea     rcx, [rbp+650h+var_260]
0x1800285ac  call    StrNCatBuff
0x1800285b1  test    eax, eax
0x1800285b3  jnz     loc_1800286CA
0x1800285b9  mov     rcx, [rbp+650h+var_6B0]
0x1800285bd  lea     rdx, [rbp+650h+var_470]
0x1800285c4  call    cs:__imp__o__wcsicmp
0x1800285ca  test    eax, eax
0x1800285cc  jz      short loc_1800285E7
0x1800285ce  mov     rcx, [rbp+650h+var_6B0]
0x1800285d2  lea     rdx, [rbp+650h+var_260]
0x1800285d9  call    cs:__imp__o__wcsicmp
0x1800285df  test    eax, eax
0x1800285e1  jnz     loc_1800286CA
0x1800285e7  mov     ecx, [rsp+750h+var_6D4]; unsigned int
0x1800285eb  lea     r9, [rsp+750h+var_6D8]; unsigned int *
0x1800285f0  mov     dword ptr [rsp+750h+lpSecurityAttributes], 1; int
0x1800285f8  lea     r8, [rbp+650h+var_6A8]; struct _INTERNAL_DRV_FILE **
0x1800285fc  mov     qword ptr [rsp+750h+samDesired], r14; struct _INIENVIRONMENT *
0x180028601  mov     rdx, rdi; unsigned __int8 *
0x180028604  mov     [rsp+750h+dwOptions], 0; int
0x18002860c  call    ?CreateInternalDriverFileArray@@YAHKPEAEPEAPEAU_INTERNAL_DRV_FILE@@PEAKHPEAU_INIENVIRONMENT@@H@Z; CreateInternalDriverFileArray(ulong,uchar *,_INTERNAL_DRV_FILE * *,ulong *,int,_INIENVIRONMENT *,int)
0x180028611  test    eax, eax
0x180028613  jz      loc_1800286CA
0x180028619  cmp     dword ptr [rdi], 2
0x18002861c  jz      short loc_18002867F
0x18002861e  mov     rax, [rbp+650h+var_6B0]
0x180028622  mov     r9, r13
0x180028625  neg     rax
0x180028628  mov     r8, r15
0x18002862b  lea     rax, [rbp+650h+var_6CC]
0x18002862f  mov     rdx, r14
0x180028632  sbb     ecx, ecx
0x180028634  neg     ecx
0x180028636  inc     ecx
0x180028638  mov     [rsp+750h+var_6F0], ecx
0x18002863c  mov     rcx, rsi
0x18002863f  mov     [rsp+750h+var_6F8], rax
0x180028644  mov     eax, [rbp+650h+var_6D0]
0x180028647  mov     [rsp+750h+var_700], eax
0x18002864b  mov     eax, [rsp+750h+var_6D8]
0x18002864f  mov     dword ptr [rsp+750h+lpdwDisposition], eax
0x180028653  mov     rax, [rbp+650h+var_6A8]
0x180028657  mov     [rsp+750h+phkResult], rax
0x18002865c  mov     eax, [rsp+750h+var_6D4]
0x180028660  mov     dword ptr [rsp+750h+lpSecurityAttributes], 1
0x180028668  mov     qword ptr [rsp+750h+samDesired], rdi
0x18002866d  mov     [rsp+750h+dwOptions], eax
0x180028671  call    ?WaitRequiredForDriverUnload@@YAHPEAU_INISPOOLER@@PEAU_INIENVIRONMENT@@PEAU_INIVERSION@@PEAU_INIDRIVER@@KPEAEKPEAU_INTERNAL_DRV_FILE@@KKHPEAHW4EMoveFileOptions@@@Z; WaitRequiredForDriverUnload(_INISPOOLER *,_INIENVIRONMENT *,_INIVERSION *,_INIDRIVER *,ulong,uchar *,ulong,_INTERNAL_DRV_FILE *,ulong,ulong,int,int *,EMoveFileOptions)
0x180028676  test    eax, eax
0x180028678  jnz     short loc_1800286CA
0x18002867a  cmp     [rbp+650h+var_6CC], eax
0x18002867d  jz      short loc_1800286CA
0x18002867f  mov     r9, r13; struct _INIDRIVER *
0x180028682  mov     r8, r15; struct _INIVERSION *
0x180028685  mov     rdx, r14; struct _INIENVIRONMENT *
0x180028688  mov     rcx, rsi; struct _INISPOOLER *
0x18002868b  call    ?RemoveDriverTempFiles@@YAXPEAU_INISPOOLER@@PEAU_INIENVIRONMENT@@PEAU_INIVERSION@@PEAU_INIDRIVER@@@Z; RemoveDriverTempFiles(_INISPOOLER *,_INIENVIRONMENT *,_INIVERSION *,_INIDRIVER *)
0x180028690  mov     rsi, [rbp+650h+var_6C0]
0x180028694  test    rsi, rsi
0x180028697  jz      short loc_1800286B9
0x180028699  mov     ecx, 18h
0x18002869e  call    cs:__imp_DllAllocSplMem
0x1800286a4  test    rax, rax
0x1800286a7  jz      short loc_1800286B9
0x1800286a9  mov     [rax], rbx
0x1800286ac  mov     rbx, rax
0x1800286af  mov     [rax+8], rsi
0x1800286b3  mov     [rax+10h], r12d
0x1800286b7  jmp     short loc_1800286C2
0x1800286b9  mov     rcx, rsi
0x1800286bc  call    cs:__imp_DllFreeSplMem
0x1800286c2  mov     [rbp+650h+var_6C0], 0
0x1800286ca  mov     eax, [rsp+750h+var_6D8]
0x1800286ce  lea     r9, [rbp+650h+var_6A8]; struct _INTERNAL_DRV_FILE **
0x1800286d2  mov     rdx, [rbp+650h+var_698]; unsigned __int16 *
0x1800286d6  mov     r8, rdi; struct _DRIVER_INFO_8W *
0x1800286d9  mov     rcx, [rbp+650h+var_6C0]; unsigned __int16 *
0x1800286dd  mov     [rsp+750h+dwOptions], eax; unsigned int
0x1800286e1  call    ?CleanUpResources@@YAXPEAG0PEAU_DRIVER_INFO_8W@@PEAPEAU_INTERNAL_DRV_FILE@@K@Z; CleanUpResources(ushort *,ushort *,_DRIVER_INFO_8W *,_INTERNAL_DRV_FILE * *,ulong)
0x1800286e6  mov     eax, [rbp+650h+var_6C8]
0x1800286e9  lea     rcx, [rbp+650h+var_6A0]
0x1800286ed  mov     [rsp+750h+lpSecurityAttributes], rcx; struct _DRIVER_INFO_8W **
0x1800286f2  inc     eax
0x1800286f4  lea     rcx, [rbp+650h+var_6D0]
0x1800286f8  mov     [rbp+650h+var_6C8], eax
0x1800286fb  mov     qword ptr [rsp+750h+samDesired], rcx; unsigned int *
0x180028700  xor     edi, edi
0x180028702  lea     rcx, [rsp+750h+var_6D4]
0x180028707  mov     edx, eax; dwIndex
0x180028709  mov     qword ptr [rsp+750h+dwOptions], rcx; unsigned int *
0x18002870e  mov     rcx, [rsp+750h+var_6E0]; hKey
0x180028713  lea     r9, [rbp+650h+var_698]; unsigned __int16 **
0x180028717  lea     r8, [rbp+650h+var_6C0]; unsigned __int16 **
0x18002871b  mov     [rbp+650h+var_6A8], rdi
0x18002871f  mov     [rsp+750h+var_6D8], edi
0x180028723  call    ?RestoreParametersForUpgrade@@YAHPEAXKPEAPEAG1PEAK2PEAPEAU_DRIVER_INFO_8W@@@Z; RestoreParametersForUpgrade(void *,ulong,ushort * *,ushort * *,ulong *,ulong *,_DRIVER_INFO_8W * *)
0x180028728  test    eax, eax
0x18002872a  jnz     loc_180028474
0x180028730  mov     rcx, [rsp+750h+var_6E0]; hKey
0x180028735  call    cs:__imp_RegCloseKey
0x18002873b  inc     r12d
0x18002873e  mov     edx, r12d; unsigned int
0x180028741  mov     rcx, [rbp+650h+var_6B8]; hKey
0x180028745  lea     r8, [rsp+750h+var_6E0]; void **
0x18002874a  mov     [rsp+750h+var_6E0], rdi
0x18002874f  call    ?RestoreVersionKey@@YAHPEAXKPEAPEAX@Z; RestoreVersionKey(void *,ulong,void * *)
0x180028754  test    eax, eax
0x180028756  jnz     loc_18002844E
0x18002875c  jmp     short loc_1800287B0
0x18002875e  mov     rbx, [rbx]
0x180028761  lea     r8, [rsp+750h+var_6E0]; void **
0x180028766  mov     rcx, [rbp+650h+var_6B8]; hKey
0x18002876a  mov     [rsp+750h+var_6E0], rdi
0x18002876f  mov     edx, [rsi+10h]; unsigned int
0x180028772  call    ?RestoreVersionKey@@YAHPEAXKPEAPEAX@Z; RestoreVersionKey(void *,ulong,void * *)
0x180028777  test    eax, eax
0x180028779  jz      short loc_18002879B
0x18002877b  mov     rdx, [rsi+8]; lpSubKey
0x18002877f  xor     r9d, r9d; Reserved
0x180028782  mov     rcx, [rsp+750h+var_6E0]; hKey
0x180028787  xor     r8d, r8d; samDesired
0x18002878a  call    cs:__imp_RegDeleteKeyExW
0x180028790  mov     rcx, [rsp+750h+var_6E0]; hKey
0x180028795  call    cs:__imp_RegCloseKey
0x18002879b  mov     rcx, [rsi+8]
0x18002879f  call    cs:__imp_DllFreeSplMem
0x1800287a5  mov     rcx, rsi
0x1800287a8  call    cs:__imp_DllFreeSplMem
0x1800287ae  xor     edi, edi
0x1800287b0  mov     rsi, rbx
0x1800287b3  test    rbx, rbx
0x1800287b6  jnz     short loc_18002875E
0x1800287b8  call    LeaveSplSem
0x1800287bd  mov     rcx, [rbp+650h+var_6B8]; hKey
0x1800287c1  test    rcx, rcx
0x1800287c4  jz      short loc_1800287CC
0x1800287c6  call    cs:__imp_RegCloseKey
0x1800287cc  mov     rcx, [rbp+650h+hKey]; hKey
0x1800287d0  test    rcx, rcx
0x1800287d3  jz      short loc_1800287DB
0x1800287d5  call    cs:__imp_RegCloseKey
0x1800287db  call    ?CleanUpgradeDirectories@@YAXXZ; CleanUpgradeDirectories(void)
0x1800287e0  mov     rcx, [rbp+650h+var_50]
0x1800287e7  xor     rcx, rsp; StackCookie
0x1800287ea  call    __security_check_cookie
0x1800287ef  add     rsp, 718h
0x1800287f6  pop     r15
0x1800287f8  pop     r14
0x1800287fa  pop     r13
0x1800287fc  pop     r12
0x1800287fe  pop     rdi
0x1800287ff  pop     rsi
0x180028800  pop     rbx
0x180028801  pop     rbp
0x180028802  retn
```
