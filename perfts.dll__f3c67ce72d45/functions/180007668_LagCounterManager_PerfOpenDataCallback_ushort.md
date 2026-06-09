# LagCounterManager::PerfOpenDataCallback(ushort *)

- ea: `0x180007668`
- end: `0x180007b04`
- name: `?PerfOpenDataCallback@LagCounterManager@@SAKPEAG@Z`
- size: `1180`
- prototype: `unsigned int __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180003bc0`

## callees

- `0x180001008`
- `0x180001140`
- `0x180001da8`
- `0x1800047c4`
- `0x1800047fc`
- `0x180004be0`
- `0x180005378`
- `0x1800058b8`
- `0x1800064ac`
- `0x180006d0c`
- `0x180007668`
- `0x180008af0`
- `0x180008bac`
- `0x1800098f6`
- `0x180009930`

## import_xrefs

- `KERNEL32!WaitForMultipleObjects` at `0x180007a9e`
- `KERNEL32!WaitForMultipleObjects` at `0x180007a9e`
- `KERNEL32!CreateEventExW` at `0x180007968`
- `KERNEL32!CreateEventExW` at `0x180007968`
- `KERNEL32!GetCurrentProcessId` at `0x1800076c7`
- `KERNEL32!GetCurrentProcessId` at `0x1800076c7`
- `KERNEL32!CloseHandle` at `0x180007adc`
- `KERNEL32!CloseHandle` at `0x180007adc`
- `KERNEL32!LoadLibraryW` at `0x180007ac0`
- `KERNEL32!LoadLibraryW` at `0x180007ac0`
- `KERNEL32!CreateThread` at `0x1800079f7`
- `KERNEL32!CreateThread` at `0x1800079f7`
- `ADVAPI32!RegCloseKey` at `0x1800077ed`
- `ADVAPI32!RegCloseKey` at `0x1800077ed`
- `ADVAPI32!RegOpenKeyExW` at `0x180007751`
- `ADVAPI32!RegOpenKeyExW` at `0x180007751`
- `ADVAPI32!RegQueryValueExW` at `0x180007794`
- `ADVAPI32!RegQueryValueExW` at `0x1800077d7`
- `ADVAPI32!RegQueryValueExW` at `0x180007794`
- `ADVAPI32!RegQueryValueExW` at `0x1800077d7`
- `WTSAPI32!WTSEnumerateProcessesW` at `0x180007862`
- `WTSAPI32!WTSEnumerateProcessesW` at `0x180007862`
- `WTSAPI32!WTSFreeMemory` at `0x180007950`
- `WTSAPI32!WTSFreeMemory` at `0x180007950`

## string_xrefs

- `0x1800076d1`: `Terminal-Services-LSM-ApplicationLag`
- `0x180007716`: `SYSTEM\CurrentControlSet\Services\%s\Performance`
- `0x180007985`: `Failed to create hStartedEvent`
- `0x1800079b3`: `Starting Lag Counter thread...`
- `0x180007a14`: `Failed to start all threads for lag counter, force exiting all of them.`
- `0x180007a4a`: `Done starting Lag Counter threads...`
- `0x180007ab9`: `pdh.dll`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
BOOL __fastcall LagCounterManager::PerfOpenDataCallback(unsigned __int16 *a1)
{
  BOOL result; // eax
  int v2; // ecx
  int v3; // r8d
  int v4; // r9d
  DWORD v5; // edi
  PWTS_PROCESS_INFOW v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rdx
  void *v9; // rax
  __int64 v10; // rsi
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  DWORD phkResult; // [rsp+20h] [rbp-4A8h]
  DWORD cbData; // [rsp+30h] [rbp-498h] BYREF
  const char *v19; // [rsp+38h] [rbp-490h] BYREF
  PWTS_PROCESS_INFOW ppProcessInfo; // [rsp+40h] [rbp-488h] BYREF
  DWORD Type; // [rsp+48h] [rbp-480h] BYREF
  DWORD pCount; // [rsp+4Ch] [rbp-47Ch] BYREF
  DWORD ThreadId; // [rsp+50h] [rbp-478h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-470h] BYREF
  const char *v25; // [rsp+60h] [rbp-468h] BYREF
  HANDLE Handles[3]; // [rsp+68h] [rbp-460h] BYREF
  WCHAR SubKey[256]; // [rsp+80h] [rbp-448h] BYREF
  _BYTE v28[528]; // [rsp+280h] [rbp-248h] BYREF

  pCount = 0;
  ppProcessInfo = 0;
  hKey = 0;
  cbData = 0;
  Type = 0;
  if ( LagCounterManager::dwOpenPerfCount > 1 )
    return 0;
  if ( CounterHelper::LagCounterCleanZombie )
    CleanUpZombieLagCounters();
  phkResult = GetCurrentProcessId();
  if ( (int)StringCchPrintfW(
              LagCounterManager::EtwSessionName,
              0xC8u,
              L"%s-%u",
              L"Terminal-Services-LSM-ApplicationLag",
              phkResult) < 0 )
    return 0;
  memset_0(&LagCounterManager::ProcessDef, 0, 0x90u);
  StringCchPrintfW(SubKey, 0x100u, L"SYSTEM\\CurrentControlSet\\Services\\%s\\Performance", L"LSM");
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0xF003Fu, &hKey) )
    return 0;
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"First Counter", 0, &Type, &LagCounterManager::dwFirstCounter, &cbData) )
    return 0;
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"First Help", 0, &Type, &LagCounterManager::dwFirstHelp, &cbData) )
    return 0;
  RegCloseKey(hKey);
  InitDefinition((struct _USER_INPUT_DELAY_DEFINITION *)&LagCounterManager::ProcessDef, 1u);
  InitDefinition((struct _USER_INPUT_DELAY_DEFINITION *)&LagCounterManager::SessionDef, 2u);
  LagCounterManager::bPendingShutdown = 0;
  if ( (unsigned int)dword_180012020 > 4 )
  {
    v19 = "Lag Counter is being registered";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v2,
      (unsigned int)&unk_18000F32F,
      v3,
      v4,
      (__int64)&v19);
  }
  UpdateLagCounterSettings();
  result = WTSEnumerateProcessesW(0, 0, 1u, &ppProcessInfo, &pCount);
  if ( result )
  {
    v5 = 0;
    v6 = ppProcessInfo;
    while ( v5 < pCount )
    {
      CreateOrGetProcCounter(v6[v5].ProcessId);
      v6 = ppProcessInfo;
      v7 = *(_QWORD *)(CounterHelper::SessionToCounter + 8);
      v8 = CounterHelper::SessionToCounter;
      while ( !*(_BYTE *)(v7 + 25) )
      {
        if ( *(_DWORD *)(v7 + 32) >= ppProcessInfo[v5].SessionId )
        {
          v8 = v7;
          v7 = *(_QWORD *)v7;
        }
        else
        {
          v7 = *(_QWORD *)(v7 + 16);
        }
      }
      if ( v8 == CounterHelper::SessionToCounter || ppProcessInfo[v5].SessionId < *(_DWORD *)(v8 + 32) )
        v8 = CounterHelper::SessionToCounter;
      if ( v8 == CounterHelper::SessionToCounter )
      {
        swprintf_s<260>(v28, L"%u", ppProcessInfo[v5].SessionId);
        v9 = operator new(0x1B0u);
        if ( v9 )
          v10 = CounterHelper::CounterHelper(v9, v28, 1);
        else
          v10 = 0;
        *(_QWORD *)std::map<unsigned long,CounterHelper *>::operator[](
                     &CounterHelper::SessionToCounter,
                     &ppProcessInfo[v5]) = v10;
        v6 = ppProcessInfo;
      }
      ++v5;
    }
    WTSFreeMemory(v6);
    LagCounterManager::hStartedEvent = CreateEventExW(0, LagCounterManager::EtwSessionName, 1u, 0x1F0003u);
    if ( LagCounterManager::hStartedEvent )
    {
      if ( (unsigned int)dword_180012020 > 4 )
      {
        v19 = "Starting Lag Counter thread...";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v11,
          (unsigned int)&unk_18000F54A,
          v12,
          v13,
          (__int64)&v19);
      }
      ThreadId = 0;
      LagCounterManager::hEtwThread = CreateThread(0, 0, BlockOnProcessTrace, 0, 0, &ThreadId);
      if ( LagCounterManager::hEtwThread )
      {
        if ( (unsigned int)dword_180012020 > 4 )
        {
          v19 = (const char *)ThreadId;
          v25 = "Done starting Lag Counter threads...";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            v14,
            (unsigned int)&unk_18000F1B1,
            v15,
            v16,
            (__int64)&v25,
            (__int64)&v19);
        }
        Handles[0] = LagCounterManager::hStartedEvent;
        Handles[1] = LagCounterManager::hEtwThread;
        if ( WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF) )
        {
          if ( LagCounterManager::hEtwThread )
            LagCounterManager::PerfCloseDataCallback();
        }
        else
        {
          LagCounterManager::hPdhLib = LoadLibraryW(L"pdh.dll");
          _InterlockedAdd((volatile signed __int32 *)&LagCounterManager::dwOpenPerfCount, 1u);
        }
      }
      else if ( (unsigned int)dword_180012020 > 2 )
      {
        v19 = "Failed to start all threads for lag counter, force exiting all of them.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v14,
          (unsigned int)&unk_18000F02C,
          v15,
          v16,
          (__int64)&v19);
      }
      CloseHandle(LagCounterManager::hStartedEvent);
      return 0;
    }
    else
    {
      if ( (unsigned int)dword_180012020 > 2 )
      {
        v19 = "Failed to create hStartedEvent";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v11,
          (unsigned int)&unk_18000F075,
          v12,
          v13,
          (__int64)&v19);
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007668  push    rbx
0x18000766a  push    rsi
0x18000766b  push    rdi
0x18000766c  push    r14
0x18000766e  push    r15
0x180007670  sub     rsp, 4A0h
0x180007677  mov     rax, cs:__security_cookie
0x18000767e  xor     rax, rsp
0x180007681  mov     [rsp+4C8h+var_38], rax
0x180007689  xor     r14d, r14d
0x18000768c  mov     [rsp+4C8h+pCount], r14d
0x180007691  mov     [rsp+4C8h+ppProcessInfo], r14
0x180007696  mov     [rsp+4C8h+hKey], r14
0x18000769b  mov     [rsp+4C8h+cbData], r14d
0x1800076a0  mov     [rsp+4C8h+Type], r14d
0x1800076a5  lea     r15d, [r14+1]
0x1800076a9  cmp     cs:?dwOpenPerfCount@LagCounterManager@@2KA, r15d; ulong LagCounterManager::dwOpenPerfCount
0x1800076b0  jbe     short loc_1800076B9
0x1800076b2  xor     eax, eax
0x1800076b4  jmp     loc_180007AE4
0x1800076b9  cmp     cs:?LagCounterCleanZombie@CounterHelper@@2HA, r14d; int CounterHelper::LagCounterCleanZombie
0x1800076c0  jz      short loc_1800076C7
0x1800076c2  call    ?CleanUpZombieLagCounters@@YAXXZ; CleanUpZombieLagCounters(void)
0x1800076c7  call    cs:__imp_GetCurrentProcessId
0x1800076cd  mov     dword ptr [rsp+4C8h+phkResult], eax
0x1800076d1  lea     r9, aTerminalServic; "Terminal-Services-LSM-ApplicationLag"
0x1800076d8  lea     r8, aSU; "%s-%u"
0x1800076df  mov     edx, 0C8h; unsigned __int64
0x1800076e4  lea     rcx, ?EtwSessionName@LagCounterManager@@2PAGA; unsigned __int16 *
0x1800076eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800076f0  test    eax, eax
0x1800076f2  jns     short loc_1800076FB
0x1800076f4  xor     eax, eax
0x1800076f6  jmp     loc_180007AE4
0x1800076fb  xor     edx, edx; Val
0x1800076fd  mov     r8d, 90h; Size
0x180007703  lea     rcx, ?ProcessDef@LagCounterManager@@2U_USER_INPUT_DELAY_DEFINITION@@A; void *
0x18000770a  call    memset_0
0x18000770f  lea     r9, aLsm; "LSM"
0x180007716  lea     r8, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\%s"...
0x18000771d  mov     edx, 100h; unsigned __int64
0x180007722  lea     rcx, [rsp+4C8h+SubKey]; unsigned __int16 *
0x18000772a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000772f  lea     rax, [rsp+4C8h+hKey]
0x180007734  mov     [rsp+4C8h+phkResult], rax; phkResult
0x180007739  mov     r9d, 0F003Fh; samDesired
0x18000773f  xor     r8d, r8d; ulOptions
0x180007742  lea     rdx, [rsp+4C8h+SubKey]; lpSubKey
0x18000774a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007751  call    cs:__imp_RegOpenKeyExW
0x180007757  test    eax, eax
0x180007759  jz      short loc_180007762
0x18000775b  xor     eax, eax
0x18000775d  jmp     loc_180007AE4
0x180007762  mov     [rsp+4C8h+cbData], 4
0x18000776a  lea     rax, [rsp+4C8h+cbData]
0x18000776f  mov     [rsp+4C8h+lpcbData], rax; lpcbData
0x180007774  lea     rax, ?dwFirstCounter@LagCounterManager@@2KA; ulong LagCounterManager::dwFirstCounter
0x18000777b  mov     [rsp+4C8h+phkResult], rax; lpData
0x180007780  lea     r9, [rsp+4C8h+Type]; lpType
0x180007785  xor     r8d, r8d; lpReserved
0x180007788  lea     rdx, ValueName; "First Counter"
0x18000778f  mov     rcx, [rsp+4C8h+hKey]; hKey
0x180007794  call    cs:__imp_RegQueryValueExW
0x18000779a  test    eax, eax
0x18000779c  jz      short loc_1800077A5
0x18000779e  xor     eax, eax
0x1800077a0  jmp     loc_180007AE4
0x1800077a5  mov     [rsp+4C8h+cbData], 4
0x1800077ad  lea     rax, [rsp+4C8h+cbData]
0x1800077b2  mov     [rsp+4C8h+lpcbData], rax; lpcbData
0x1800077b7  lea     rax, ?dwFirstHelp@LagCounterManager@@2KA; ulong LagCounterManager::dwFirstHelp
0x1800077be  mov     [rsp+4C8h+phkResult], rax; lpData
0x1800077c3  lea     r9, [rsp+4C8h+Type]; lpType
0x1800077c8  xor     r8d, r8d; lpReserved
0x1800077cb  lea     rdx, aFirstHelp; "First Help"
0x1800077d2  mov     rcx, [rsp+4C8h+hKey]; hKey
0x1800077d7  call    cs:__imp_RegQueryValueExW
0x1800077dd  test    eax, eax
0x1800077df  jz      short loc_1800077E8
0x1800077e1  xor     eax, eax
0x1800077e3  jmp     loc_180007AE4
0x1800077e8  mov     rcx, [rsp+4C8h+hKey]; hKey
0x1800077ed  call    cs:__imp_RegCloseKey
0x1800077f3  mov     edx, r15d; unsigned int
0x1800077f6  lea     rcx, ?ProcessDef@LagCounterManager@@2U_USER_INPUT_DELAY_DEFINITION@@A; struct _USER_INPUT_DELAY_DEFINITION *
0x1800077fd  call    ?InitDefinition@@YAXPEAU_USER_INPUT_DELAY_DEFINITION@@K@Z; InitDefinition(_USER_INPUT_DELAY_DEFINITION *,ulong)
0x180007802  mov     edx, 2; unsigned int
0x180007807  lea     rcx, ?SessionDef@LagCounterManager@@2U_USER_INPUT_DELAY_DEFINITION@@A; struct _USER_INPUT_DELAY_DEFINITION *
0x18000780e  call    ?InitDefinition@@YAXPEAU_USER_INPUT_DELAY_DEFINITION@@K@Z; InitDefinition(_USER_INPUT_DELAY_DEFINITION *,ulong)
0x180007813  mov     cs:?bPendingShutdown@LagCounterManager@@2HA, r14d; int LagCounterManager::bPendingShutdown
0x18000781a  mov     eax, cs:dword_180012020
0x180007820  cmp     eax, 4
0x180007823  jbe     short loc_180007847
0x180007825  lea     rax, aLagCounterIsBe; "Lag Counter is being registered"
0x18000782c  mov     [rsp+4C8h+var_490], rax
0x180007831  lea     rax, [rsp+4C8h+var_490]
0x180007836  mov     [rsp+4C8h+phkResult], rax
0x18000783b  lea     rdx, unk_18000F32F
0x180007842  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180007847  call    ?UpdateLagCounterSettings@@YAXXZ; UpdateLagCounterSettings(void)
0x18000784c  lea     rax, [rsp+4C8h+pCount]
0x180007851  mov     [rsp+4C8h+phkResult], rax; pCount
0x180007856  lea     r9, [rsp+4C8h+ppProcessInfo]; ppProcessInfo
0x18000785b  mov     r8d, r15d; Version
0x18000785e  xor     edx, edx; Reserved
0x180007860  xor     ecx, ecx; hServer
0x180007862  call    cs:__imp_WTSEnumerateProcessesW
0x180007868  test    eax, eax
0x18000786a  jz      loc_180007AE4
0x180007870  mov     edi, r14d
0x180007873  mov     rcx, [rsp+4C8h+ppProcessInfo]; pMemory
0x180007878  cmp     edi, [rsp+4C8h+pCount]
0x18000787c  jnb     loc_180007950
0x180007882  mov     eax, edi
0x180007884  lea     rbx, [rax+rax*2]
0x180007888  mov     ecx, [rcx+rbx*8+4]; dwProcessId
0x18000788c  call    ?CreateOrGetProcCounter@@YAPEAVCounterHelper@@K@Z; CreateOrGetProcCounter(ulong)
0x180007891  mov     rcx, [rsp+4C8h+ppProcessInfo]
0x180007896  mov     r8, cs:?SessionToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::SessionToCounter
0x18000789d  mov     rax, [r8+8]
0x1800078a1  mov     rdx, r8
0x1800078a4  cmp     [rax+19h], r14b
0x1800078a8  jnz     short loc_1800078C6
0x1800078aa  mov     r9d, [rcx+rbx*8]
0x1800078ae  cmp     [rax+20h], r9d
0x1800078b2  jnb     short loc_1800078BA
0x1800078b4  mov     rax, [rax+10h]
0x1800078b8  jmp     short loc_1800078C0
0x1800078ba  mov     rdx, rax
0x1800078bd  mov     rax, [rax]
0x1800078c0  cmp     [rax+19h], r14b
0x1800078c4  jz      short loc_1800078AE
0x1800078c6  cmp     rdx, r8
0x1800078c9  jz      short loc_1800078D3
0x1800078cb  mov     eax, [rdx+20h]
0x1800078ce  cmp     [rcx+rbx*8], eax
0x1800078d1  jnb     short loc_1800078D6
0x1800078d3  mov     rdx, r8
0x1800078d6  cmp     rdx, r8
0x1800078d9  jnz     short loc_180007948
0x1800078db  mov     r8d, [rcx+rbx*8]
0x1800078df  lea     rdx, aU; "%u"
0x1800078e6  lea     rcx, [rsp+4C8h+var_248]
0x1800078ee  call    ??$swprintf_s@$0BAE@@@YAHAEAY0BAE@GPEBGZZ; swprintf_s<260>(ushort (&)[260],ushort const *,...)
0x1800078f3  mov     ecx, 1B0h; Size
0x1800078f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800078fd  test    rax, rax
0x180007900  jz      short loc_180007928
0x180007902  mov     rcx, [rsp+4C8h+ppProcessInfo]
0x180007907  mov     r9d, [rcx+rbx*8]
0x18000790b  mov     dword ptr [rsp+4C8h+phkResult], r9d
0x180007910  mov     r8d, r15d
0x180007913  lea     rdx, [rsp+4C8h+var_248]
0x18000791b  mov     rcx, rax
0x18000791e  call    ??0CounterHelper@@QEAA@PEAGW4COUNTER_HELPER_TYPE@@KK@Z; CounterHelper::CounterHelper(ushort *,COUNTER_HELPER_TYPE,ulong,ulong)
0x180007923  mov     rsi, rax
0x180007926  jmp     short loc_18000792B
0x180007928  mov     rsi, r14
0x18000792b  mov     rax, [rsp+4C8h+ppProcessInfo]
0x180007930  lea     rdx, [rax+rbx*8]
0x180007934  lea     rcx, ?SessionToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::SessionToCounter
0x18000793b  call    ??A?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@QEAAAEAPEAVCounterHelper@@AEBK@Z; std::map<ulong,CounterHelper *>::operator[](ulong const &)
0x180007940  mov     [rax], rsi
0x180007943  mov     rcx, [rsp+4C8h+ppProcessInfo]
0x180007948  add     edi, r15d
0x18000794b  jmp     loc_180007878
0x180007950  call    cs:__imp_WTSFreeMemory
0x180007956  mov     r9d, 1F0003h; dwDesiredAccess
0x18000795c  mov     r8d, r15d; dwFlags
0x18000795f  lea     rdx, ?EtwSessionName@LagCounterManager@@2PAGA; lpName
0x180007966  xor     ecx, ecx; lpEventAttributes
0x180007968  call    cs:__imp_CreateEventExW
0x18000796e  mov     cs:?hStartedEvent@LagCounterManager@@2PEAXEA, rax; void * LagCounterManager::hStartedEvent
0x180007975  test    rax, rax
0x180007978  mov     eax, cs:dword_180012020
0x18000797e  jnz     short loc_1800079AE
0x180007980  cmp     eax, 2
0x180007983  jbe     short loc_1800079A7
0x180007985  lea     rax, aFailedToCreate; "Failed to create hStartedEvent"
0x18000798c  mov     [rsp+4C8h+var_490], rax
0x180007991  lea     rax, [rsp+4C8h+var_490]
0x180007996  mov     [rsp+4C8h+phkResult], rax
0x18000799b  lea     rdx, unk_18000F075
0x1800079a2  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800079a7  xor     eax, eax
0x1800079a9  jmp     loc_180007AE4
0x1800079ae  cmp     eax, 4
0x1800079b1  jbe     short loc_1800079D5
0x1800079b3  lea     rax, aStartingLagCou; "Starting Lag Counter thread..."
0x1800079ba  mov     [rsp+4C8h+var_490], rax
0x1800079bf  lea     rax, [rsp+4C8h+var_490]
0x1800079c4  mov     [rsp+4C8h+phkResult], rax
0x1800079c9  lea     rdx, unk_18000F54A
0x1800079d0  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800079d5  mov     [rsp+4C8h+ThreadId], r14d
0x1800079da  lea     rax, [rsp+4C8h+ThreadId]
0x1800079df  mov     [rsp+4C8h+lpcbData], rax; lpThreadId
0x1800079e4  mov     dword ptr [rsp+4C8h+phkResult], r14d; dwCreationFlags
0x1800079e9  xor     r9d, r9d; lpParameter
0x1800079ec  lea     r8, ?BlockOnProcessTrace@@YAKPEAX@Z; lpStartAddress
0x1800079f3  xor     edx, edx; dwStackSize
0x1800079f5  xor     ecx, ecx; lpThreadAttributes
0x1800079f7  call    cs:__imp_CreateThread
0x1800079fd  mov     cs:?hEtwThread@LagCounterManager@@2PEAXEA, rax; void * LagCounterManager::hEtwThread
0x180007a04  test    rax, rax
0x180007a07  mov     eax, cs:dword_180012020
0x180007a0d  jnz     short loc_180007A3C
0x180007a0f  cmp     eax, 2
0x180007a12  jbe     short loc_180007A37
0x180007a14  lea     rax, aFailedToStartA; "Failed to start all threads for lag cou"...
0x180007a1b  mov     [rsp+4C8h+var_490], rax
0x180007a20  lea     rax, [rsp+4C8h+var_490]
0x180007a25  mov     [rsp+4C8h+phkResult], rax
0x180007a2a  lea     rdx, unk_18000F02C
0x180007a31  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180007a36  nop
0x180007a37  jmp     loc_180007AD5
0x180007a3c  cmp     eax, 4
0x180007a3f  jbe     short loc_180007A76
0x180007a41  mov     eax, [rsp+4C8h+ThreadId]
0x180007a45  mov     [rsp+4C8h+var_490], rax
0x180007a4a  lea     rax, aDoneStartingLa; "Done starting Lag Counter threads..."
0x180007a51  mov     [rsp+4C8h+var_468], rax
0x180007a56  lea     rax, [rsp+4C8h+var_490]
0x180007a5b  mov     [rsp+4C8h+lpcbData], rax
0x180007a60  lea     rax, [rsp+4C8h+var_468]
0x180007a65  mov     [rsp+4C8h+phkResult], rax
0x180007a6a  lea     rdx, unk_18000F1B1
0x180007a71  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180007a76  mov     rax, cs:?hStartedEvent@LagCounterManager@@2PEAXEA; void * LagCounterManager::hStartedEvent
0x180007a7d  mov     [rsp+4C8h+Handles], rax
0x180007a82  mov     rax, cs:?hEtwThread@LagCounterManager@@2PEAXEA; void * LagCounterManager::hEtwThread
0x180007a89  mov     [rsp+4C8h+var_458], rax
0x180007a8e  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180007a92  xor     r8d, r8d; bWaitAll
0x180007a95  lea     rdx, [rsp+4C8h+Handles]; lpHandles
0x180007a9a  lea     ecx, [r8+2]; nCount
0x180007a9e  call    cs:__imp_WaitForMultipleObjects
0x180007aa4  test    eax, eax
0x180007aa6  jz      short loc_180007AB9
0x180007aa8  cmp     cs:?hEtwThread@LagCounterManager@@2PEAXEA, r14; void * LagCounterManager::hEtwThread
0x180007aaf  jz      short loc_180007AB7
0x180007ab1  call    ?PerfCloseDataCallback@LagCounterManager@@SAKXZ; LagCounterManager::PerfCloseDataCallback(void)
0x180007ab6  nop
0x180007ab7  jmp     short loc_180007AD5
0x180007ab9  lea     rcx, LibFileName; "pdh.dll"
0x180007ac0  call    cs:__imp_LoadLibraryW
0x180007ac6  mov     cs:?hPdhLib@LagCounterManager@@2PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * LagCounterManager::hPdhLib
0x180007acd  lock add cs:?dwOpenPerfCount@LagCounterManager@@2KA, r15d; ulong LagCounterManager::dwOpenPerfCount
0x180007ad5  mov     rcx, cs:?hStartedEvent@LagCounterManager@@2PEAXEA; hObject
0x180007adc  call    cs:__imp_CloseHandle
0x180007ae2  xor     eax, eax
0x180007ae4  mov     rcx, [rsp+4C8h+var_38]
0x180007aec  xor     rcx, rsp; StackCookie
0x180007aef  call    __security_check_cookie
0x180007af4  add     rsp, 4A0h
0x180007afb  pop     r15
0x180007afd  pop     r14
0x180007aff  pop     rdi
0x180007b00  pop     rsi
0x180007b01  pop     rbx
0x180007b02  retn
```
