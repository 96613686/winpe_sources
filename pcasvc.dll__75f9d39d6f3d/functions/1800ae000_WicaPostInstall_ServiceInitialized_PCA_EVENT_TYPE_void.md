# WicaPostInstall_ServiceInitialized(_PCA_EVENT_TYPE,void *)

- ea: `0x1800ae000`
- end: `0x1800ae28d`
- name: `?WicaPostInstall_ServiceInitialized@@YAKW4_PCA_EVENT_TYPE@@PEAX@Z`
- size: `653`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180012920`
- `0x18001b320`
- `0x1800aded8`
- `0x1800ae000`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x1800ae1b5`
- `ntdll!RtlInitializeSRWLock` at `0x1800ae1b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae202`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae202`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ae263`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ae27a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ae263`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ae27a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ae06b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ae0fc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ae06b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ae0fc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ae0ac`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ae133`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ae0ac`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ae133`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800ae1f8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800ae1f8`

## string_xrefs

- `0x1800ae05d`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\UpgradeCompatibility`
- `0x1800ae0ee`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\PendingNotifications`
- `0x1800ae118`: `PostInstallInitialized`
- `0x1800ae0b2`: `WicaPostInstallInitialized %d`
- `0x1800ae245`: `RegOpenKeyEx failed [%d]`
- `0x1800ae030`: `WicaPostInstall_ServiceInitialized`
- `0x1800ae071`: `WicaPostInstall_ServiceInitialized`
- `0x1800ae09f`: `WicaPostInstallInitialized`
- `0x1800ae219`: `Worker thread created. Service initialized.`
- `0x1800ae139`: `PendingNotifications PostInstallInitialized %d`
- `0x1800ae16d`: `UpgradeCompatibility and PendingNotifications registry key not present. Disabling monitor.`

## pseudocode

```c
__int64 __fastcall WicaPostInstall_ServiceInitialized(__int64 a1, __int64 a2)
{
  unsigned int v2; // ebx
  LSTATUS v3; // eax
  char v4; // r14
  LSTATUS v5; // eax
  char v6; // bl
  const char *v7; // r9
  int v8; // r8d
  DWORD LastError; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-10h]
  int Data; // [rsp+68h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+40h] BYREF
  HKEY v14; // [rsp+78h] [rbp+48h] BYREF

  hKey = 0;
  v14 = 0;
  if ( !a2 )
  {
    v2 = 1359;
    AslLogCallPrintf(
      1,
      (unsigned int)"WicaPostInstall_ServiceInitialized",
      1487,
      (unsigned int)"Null EventParam argument passed in.");
    goto LABEL_24;
  }
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\UpgradeCompatibility",
         0,
         0x2001Fu,
         &hKey);
  v2 = v3;
  if ( v3 )
  {
    if ( v3 != 2 )
    {
      v8 = 1513;
      goto LABEL_22;
    }
    v4 = 0;
  }
  else
  {
    Data = 1;
    v4 = 1;
    RegSetValueExW(hKey, L"WicaPostInstallInitialized", 0, 4u, (const BYTE *)&Data, 4u);
    AslLogCallPrintf(
      3,
      (unsigned int)"WicaPostInstall_ServiceInitialized",
      1504,
      (unsigned int)"WicaPostInstallInitialized %d");
  }
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\PendingNotifications",
         0,
         0x2001Fu,
         &v14);
  v2 = v5;
  if ( !v5 )
  {
    Data = 1;
    v6 = 1;
    LODWORD(phkResult) = RegSetValueExW(v14, L"PostInstallInitialized", 0, 4u, (const BYTE *)&Data, 4u);
    AslLogCallPrintf(
      3,
      (unsigned int)"WicaPostInstall_ServiceInitialized",
      1524,
      (unsigned int)"PendingNotifications PostInstallInitialized %d");
    goto LABEL_11;
  }
  if ( v5 != 2 )
  {
    v8 = 1532;
LABEL_22:
    v7 = "RegOpenKeyEx failed [%d]";
    goto LABEL_23;
  }
  v6 = 0;
LABEL_11:
  if ( !v4 && !v6 )
  {
    AslLogCallPrintf(
      3,
      (unsigned int)"WicaPostInstall_ServiceInitialized",
      1538,
      (unsigned int)"UpgradeCompatibility and PendingNotifications registry key not present. Disabling monitor.");
    dword_1801598BC = 0;
LABEL_19:
    v2 = 0;
    goto LABEL_24;
  }
  PcaTracePrintf("WicaPostUpgrade", 0, 0, "Activated", phkResult);
  RtlInitializeSRWLock(&WicaGlobals);
  dword_1801598B8 = 0;
  dword_1801598BC = 1;
  v2 = RtlArray<_ExeEntry>::Initialize(&xmmword_1801598C8);
  if ( v2 )
  {
    v7 = "ExeEntries.Initialize Failed [%d]";
    v8 = 1558;
  }
  else
  {
    if ( QueueUserWorkItem(WicaPostInstallp_WorkerThread, 0, 0) )
    {
      AslLogCallPrintf(
        3,
        (unsigned int)"WicaPostInstall_ServiceInitialized",
        1580,
        (unsigned int)"Worker thread created. Service initialized.");
      goto LABEL_19;
    }
    LastError = GetLastError();
    v7 = "QueueUserWorkItem Failed [%d]";
    v8 = 1576;
    v2 = LastError;
  }
LABEL_23:
  AslLogCallPrintf(1, (unsigned int)"WicaPostInstall_ServiceInitialized", v8, (_DWORD)v7);
LABEL_24:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v14 )
    RegCloseKey(v14);
  return v2;
}

```

## disassembly

```asm
0x1800ae000  push    rbp
0x1800ae002  push    rbx
0x1800ae003  push    rsi
0x1800ae004  push    rdi
0x1800ae005  push    r14
0x1800ae007  mov     rbp, rsp
0x1800ae00a  sub     rsp, 30h
0x1800ae00e  mov     [rbp+hKey], 0
0x1800ae016  mov     [rbp+arg_18], 0
0x1800ae01e  test    rdx, rdx
0x1800ae021  jnz     short loc_1800AE04B
0x1800ae023  lea     r9, aNullEventparam; "Null EventParam argument passed in."
0x1800ae02a  mov     r8d, 5CFh
0x1800ae030  lea     rdx, aWicapostinstal_2; "WicaPostInstall_ServiceInitialized"
0x1800ae037  mov     ecx, 1
0x1800ae03c  mov     ebx, 54Fh
0x1800ae041  call    AslLogCallPrintf
0x1800ae046  jmp     loc_1800AE25A
0x1800ae04b  lea     rax, [rbp+hKey]
0x1800ae04f  mov     r9d, 2001Fh; samDesired
0x1800ae055  xor     r8d, r8d; ulOptions
0x1800ae058  mov     [rsp+30h+phkResult], rax; phkResult
0x1800ae05d  lea     rdx, aSoftwareMicros_13; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800ae064  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ae06b  call    cs:__imp_RegOpenKeyExW
0x1800ae071  lea     rdi, aWicapostinstal_2; "WicaPostInstall_ServiceInitialized"
0x1800ae078  mov     esi, 1
0x1800ae07d  mov     ebx, eax
0x1800ae07f  test    eax, eax
0x1800ae081  jnz     short loc_1800AE0D0
0x1800ae083  mov     rcx, [rbp+hKey]; hKey
0x1800ae087  lea     rax, [rbp+Data]
0x1800ae08b  mov     [rsp+30h+cbData], 4; cbData
0x1800ae093  lea     r9d, [rbx+4]; dwType
0x1800ae097  xor     r8d, r8d; Reserved
0x1800ae09a  mov     [rsp+30h+phkResult], rax; lpData
0x1800ae09f  lea     rdx, aWicapostinstal_18; "WicaPostInstallInitialized"
0x1800ae0a6  mov     [rbp+Data], esi
0x1800ae0a9  mov     r14b, sil
0x1800ae0ac  call    cs:__imp_RegSetValueExW
0x1800ae0b2  lea     r9, aWicapostinstal_9; "WicaPostInstallInitialized %d"
0x1800ae0b9  mov     r8d, 5E0h
0x1800ae0bf  lea     ecx, [rbx+3]
0x1800ae0c2  mov     dword ptr [rsp+30h+phkResult], eax
0x1800ae0c6  mov     rdx, rdi
0x1800ae0c9  call    AslLogCallPrintf
0x1800ae0ce  jmp     short loc_1800AE0DC
0x1800ae0d0  cmp     eax, 2
0x1800ae0d3  jnz     loc_1800AE23F
0x1800ae0d9  xor     r14b, r14b
0x1800ae0dc  lea     rax, [rbp+arg_18]
0x1800ae0e0  mov     r9d, 2001Fh; samDesired
0x1800ae0e6  xor     r8d, r8d; ulOptions
0x1800ae0e9  mov     [rsp+30h+phkResult], rax; phkResult
0x1800ae0ee  lea     rdx, aSoftwareMicros_16; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800ae0f5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ae0fc  call    cs:__imp_RegOpenKeyExW
0x1800ae102  mov     ebx, eax
0x1800ae104  test    eax, eax
0x1800ae106  jnz     short loc_1800AE159
0x1800ae108  mov     rcx, [rbp+arg_18]; hKey
0x1800ae10c  lea     rax, [rbp+Data]
0x1800ae110  mov     [rsp+30h+cbData], 4; cbData
0x1800ae118  lea     rdx, aPostinstallini; "PostInstallInitialized"
0x1800ae11f  mov     r9d, 4; dwType
0x1800ae125  mov     [rsp+30h+phkResult], rax; lpData
0x1800ae12a  xor     r8d, r8d; Reserved
0x1800ae12d  mov     [rbp+Data], esi
0x1800ae130  mov     bl, sil
0x1800ae133  call    cs:__imp_RegSetValueExW
0x1800ae139  lea     r9, aPendingnotific; "PendingNotifications PostInstallInitial"...
0x1800ae140  mov     r8d, 5F4h
0x1800ae146  mov     rdx, rdi
0x1800ae149  mov     dword ptr [rsp+30h+phkResult], eax
0x1800ae14d  mov     ecx, 3
0x1800ae152  call    AslLogCallPrintf
0x1800ae157  jmp     short loc_1800AE164
0x1800ae159  cmp     eax, 2
0x1800ae15c  jnz     loc_1800AE237
0x1800ae162  xor     bl, bl
0x1800ae164  test    r14b, r14b
0x1800ae167  jnz     short loc_1800AE196
0x1800ae169  test    bl, bl
0x1800ae16b  jnz     short loc_1800AE196
0x1800ae16d  lea     r9, aUpgradecompati; "UpgradeCompatibility and PendingNotific"...
0x1800ae174  mov     r8d, 602h
0x1800ae17a  mov     rdx, rdi
0x1800ae17d  mov     ecx, 3
0x1800ae182  call    AslLogCallPrintf
0x1800ae187  mov     cs:dword_1801598BC, 0
0x1800ae191  jmp     loc_1800AE233
0x1800ae196  lea     r9, aActivated; "Activated"
0x1800ae19d  xor     r8d, r8d; unsigned int
0x1800ae1a0  xor     edx, edx; unsigned int
0x1800ae1a2  lea     rcx, aWicapostupgrad; "WicaPostUpgrade"
0x1800ae1a9  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800ae1ae  lea     rcx, ?WicaGlobals@@3U_WicaGlobals@@A; _WicaGlobals WicaGlobals
0x1800ae1b5  call    cs:__imp_RtlInitializeSRWLock
0x1800ae1bb  lea     rcx, xmmword_1801598C8
0x1800ae1c2  mov     cs:dword_1801598B8, 0
0x1800ae1cc  mov     cs:dword_1801598BC, esi
0x1800ae1d2  call    ?Initialize@?$RtlArray@U_ExeEntry@@@@QEAAJPEAX_K1H@Z; RtlArray<_ExeEntry>::Initialize(void *,unsigned __int64,unsigned __int64,int)
0x1800ae1d7  mov     ebx, eax
0x1800ae1d9  test    eax, eax
0x1800ae1db  jz      short loc_1800AE1EC
0x1800ae1dd  lea     r9, aExeentriesInit; "ExeEntries.Initialize Failed [%d]"
0x1800ae1e4  mov     r8d, 616h
0x1800ae1ea  jmp     short loc_1800AE24C
0x1800ae1ec  xor     r8d, r8d; Flags
0x1800ae1ef  lea     rcx, ?WicaPostInstallp_WorkerThread@@YAKPEAX@Z; Function
0x1800ae1f6  xor     edx, edx; Context
0x1800ae1f8  call    cs:__imp_QueueUserWorkItem
0x1800ae1fe  test    eax, eax
0x1800ae200  jnz     short loc_1800AE219
0x1800ae202  call    cs:__imp_GetLastError
0x1800ae208  lea     r9, aQueueuserworki; "QueueUserWorkItem Failed [%d]"
0x1800ae20f  mov     r8d, 628h
0x1800ae215  mov     ebx, eax
0x1800ae217  jmp     short loc_1800AE24C
0x1800ae219  lea     r9, aWorkerThreadCr; "Worker thread created. Service initiali"...
0x1800ae220  mov     r8d, 62Ch
0x1800ae226  mov     rdx, rdi
0x1800ae229  mov     ecx, 3
0x1800ae22e  call    AslLogCallPrintf
0x1800ae233  xor     ebx, ebx
0x1800ae235  jmp     short loc_1800AE25A
0x1800ae237  mov     r8d, 5FCh
0x1800ae23d  jmp     short loc_1800AE245
0x1800ae23f  mov     r8d, 5E9h
0x1800ae245  lea     r9, aRegopenkeyexFa_0; "RegOpenKeyEx failed [%d]"
0x1800ae24c  mov     rdx, rdi
0x1800ae24f  mov     dword ptr [rsp+30h+phkResult], eax
0x1800ae253  mov     ecx, esi
0x1800ae255  call    AslLogCallPrintf
0x1800ae25a  mov     rcx, [rbp+hKey]; hKey
0x1800ae25e  test    rcx, rcx
0x1800ae261  jz      short loc_1800AE271
0x1800ae263  call    cs:__imp_RegCloseKey
0x1800ae269  mov     [rbp+hKey], 0
0x1800ae271  mov     rcx, [rbp+arg_18]; hKey
0x1800ae275  test    rcx, rcx
0x1800ae278  jz      short loc_1800AE280
0x1800ae27a  call    cs:__imp_RegCloseKey
0x1800ae280  mov     eax, ebx
0x1800ae282  add     rsp, 30h
0x1800ae286  pop     r14
0x1800ae288  pop     rdi
0x1800ae289  pop     rsi
0x1800ae28a  pop     rbx
0x1800ae28b  pop     rbp
0x1800ae28c  retn
```
