# CTSPerfProvider::Initialize(void)

- ea: `0x180073238`
- end: `0x1800733b3`
- name: `?Initialize@CTSPerfProvider@@SAJXZ`
- size: `379`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180060a60`

## callees

- `0x1800074c0`
- `0x180073208`
- `0x180073238`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800732c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800732c0`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x1800732e8`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x180073318`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x180073348`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x1800732e8`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x180073318`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x180073348`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x1800732ae`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x1800732ae`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x180073364`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x180073364`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterSetInfo` at `0x18007327d`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterSetInfo` at `0x18007327d`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStartProvider` at `0x180073259`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStartProvider` at `0x180073259`

## string_xrefs

- `0x1800732c8`: `PerfCreateInstance FAILED with error: 0x%x`

## pseudocode

```c
__int64 CTSPerfProvider::Initialize(void)
{
  unsigned int v0; // edi
  ULONG started; // ebx
  struct _PERF_COUNTERSET_INSTANCE *Instance; // rax

  v0 = 0;
  started = PerfStartProvider(&ProviderGuid_tsperf_1, ControlCallback_tsperf_1, &hDataSource_tsperf_1);
  if ( started || (started = PerfSetCounterSetInfo(hDataSource_tsperf_1, &CtrSet_tsperf_1_1, 0x88u)) != 0 )
  {
    PerfStopProvider(hDataSource_tsperf_1);
    _DbgPrintMessage(8, "PerfAutoInitialize FAILED with error: 0x%x", started);
  }
  else
  {
    CTSPerfProvider::bInitialized = 1;
    Instance = PerfCreateInstance(hDataSource_tsperf_1, &CtrSetGuid_tsperf_1_1, L"_Default", 0);
    CTSPerfProvider::pInstance = Instance;
    if ( Instance )
    {
      started = PerfSetCounterRefValue(hDataSource_tsperf_1, Instance, 1u, (PVOID)&CTSPerfProvider::ActiveSessions);
      if ( started )
      {
        _DbgPrintMessage(8, "PerfSetCounterRefValue FAILED to set the active sessions counter: 0x%x", started);
      }
      else
      {
        started = PerfSetCounterRefValue(
                    hDataSource_tsperf_1,
                    CTSPerfProvider::pInstance,
                    2u,
                    (PVOID)&CTSPerfProvider::InactiveSessions);
        if ( started )
        {
          _DbgPrintMessage(8, "PerfSetCounterRefValue FAILED to set the inactive sessions counter: 0x%x", started);
        }
        else
        {
          started = PerfSetCounterRefValue(
                      hDataSource_tsperf_1,
                      CTSPerfProvider::pInstance,
                      3u,
                      (PVOID)&CTSPerfProvider::TotalSessions);
          if ( !started )
            return v0;
          _DbgPrintMessage(8, "PerfSetCounterRefValue FAILED to set the total sessions counter: 0x%x", started);
        }
      }
    }
    else
    {
      started = GetLastError();
      _DbgPrintMessage(8, "PerfCreateInstance FAILED with error: 0x%x", started);
    }
  }
  if ( started )
  {
    if ( CTSPerfProvider::bInitialized )
    {
      CTSPerfProvider::Cleanup();
      CTSPerfProvider::bInitialized = 0;
    }
    if ( (int)started > 0 )
      return (unsigned __int16)started | 0x80070000;
    else
      return started;
  }
  return v0;
}

```

## disassembly

```asm
0x180073238  mov     [rsp+arg_0], rbx
0x18007323d  push    rdi
0x18007323e  sub     rsp, 20h
0x180073242  lea     r8, ?hDataSource_tsperf_1@@3PEAXEA; phProvider
0x180073249  xor     edi, edi
0x18007324b  lea     rdx, ?ControlCallback_tsperf_1@@YAKKPEAXK@Z; ControlCallback
0x180073252  lea     rcx, ?ProviderGuid_tsperf_1@@3U_GUID@@A; ProviderGuid
0x180073259  call    cs:__imp_PerfStartProvider
0x18007325f  mov     ebx, eax
0x180073261  test    eax, eax
0x180073263  jnz     loc_18007335D
0x180073269  mov     rcx, cs:?hDataSource_tsperf_1@@3PEAXEA; ProviderHandle
0x180073270  lea     rdx, ?CtrSet_tsperf_1_1@@3U_CTRSET_tsperf_1_1@@A; Template
0x180073277  mov     r8d, 88h; TemplateSize
0x18007327d  call    cs:__imp_PerfSetCounterSetInfo
0x180073283  mov     ebx, eax
0x180073285  test    eax, eax
0x180073287  jnz     loc_18007335D
0x18007328d  mov     rcx, cs:?hDataSource_tsperf_1@@3PEAXEA; ProviderHandle
0x180073294  lea     ebx, [rdi+1]
0x180073297  xor     r9d, r9d; Id
0x18007329a  mov     cs:?bInitialized@CTSPerfProvider@@0HA, ebx; int CTSPerfProvider::bInitialized
0x1800732a0  lea     r8, aDefault_0; "_Default"
0x1800732a7  lea     rdx, ?CtrSetGuid_tsperf_1_1@@3U_GUID@@A; CounterSetGuid
0x1800732ae  call    cs:__imp_PerfCreateInstance
0x1800732b4  mov     cs:?pInstance@CTSPerfProvider@@0PEAU_PERF_COUNTERSET_INSTANCE@@EA, rax; _PERF_COUNTERSET_INSTANCE * CTSPerfProvider::pInstance
0x1800732bb  test    rax, rax
0x1800732be  jnz     short loc_1800732D4
0x1800732c0  call    cs:__imp_GetLastError
0x1800732c6  mov     ebx, eax
0x1800732c8  lea     rdx, aPerfcreateinst; "PerfCreateInstance FAILED with error: 0"...
0x1800732cf  jmp     loc_180073371
0x1800732d4  mov     rcx, cs:?hDataSource_tsperf_1@@3PEAXEA; Provider
0x1800732db  lea     r9, ?ActiveSessions@CTSPerfProvider@@0JC; Address
0x1800732e2  mov     r8d, ebx; CounterId
0x1800732e5  mov     rdx, rax; Instance
0x1800732e8  call    cs:__imp_PerfSetCounterRefValue
0x1800732ee  mov     ebx, eax
0x1800732f0  test    eax, eax
0x1800732f2  jz      short loc_1800732FD
0x1800732f4  lea     rdx, aPerfsetcounter_1; "PerfSetCounterRefValue FAILED to set th"...
0x1800732fb  jmp     short loc_180073371
0x1800732fd  mov     rdx, cs:?pInstance@CTSPerfProvider@@0PEAU_PERF_COUNTERSET_INSTANCE@@EA; Instance
0x180073304  lea     r9, ?InactiveSessions@CTSPerfProvider@@0JC; Address
0x18007330b  mov     rcx, cs:?hDataSource_tsperf_1@@3PEAXEA; Provider
0x180073312  mov     r8d, 2; CounterId
0x180073318  call    cs:__imp_PerfSetCounterRefValue
0x18007331e  mov     ebx, eax
0x180073320  test    eax, eax
0x180073322  jz      short loc_18007332D
0x180073324  lea     rdx, aPerfsetcounter_0; "PerfSetCounterRefValue FAILED to set th"...
0x18007332b  jmp     short loc_180073371
0x18007332d  mov     rdx, cs:?pInstance@CTSPerfProvider@@0PEAU_PERF_COUNTERSET_INSTANCE@@EA; Instance
0x180073334  lea     r9, ?TotalSessions@CTSPerfProvider@@0JC; Address
0x18007333b  mov     rcx, cs:?hDataSource_tsperf_1@@3PEAXEA; Provider
0x180073342  mov     r8d, 3; CounterId
0x180073348  call    cs:__imp_PerfSetCounterRefValue
0x18007334e  mov     ebx, eax
0x180073350  test    eax, eax
0x180073352  jz      short loc_1800733A6
0x180073354  lea     rdx, aPerfsetcounter; "PerfSetCounterRefValue FAILED to set th"...
0x18007335b  jmp     short loc_180073371
0x18007335d  mov     rcx, cs:?hDataSource_tsperf_1@@3PEAXEA; ProviderHandle
0x180073364  call    cs:__imp_PerfStopProvider
0x18007336a  lea     rdx, aPerfautoinitia; "PerfAutoInitialize FAILED with error: 0"...
0x180073371  mov     ecx, 8; int
0x180073376  mov     r8d, ebx
0x180073379  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18007337e  test    ebx, ebx
0x180073380  jz      short loc_1800733A6
0x180073382  cmp     cs:?bInitialized@CTSPerfProvider@@0HA, edi; int CTSPerfProvider::bInitialized
0x180073388  jz      short loc_180073395
0x18007338a  call    ?Cleanup@CTSPerfProvider@@SAXXZ; CTSPerfProvider::Cleanup(void)
0x18007338f  mov     cs:?bInitialized@CTSPerfProvider@@0HA, edi; int CTSPerfProvider::bInitialized
0x180073395  test    ebx, ebx
0x180073397  jg      short loc_18007339D
0x180073399  mov     edi, ebx
0x18007339b  jmp     short loc_1800733A6
0x18007339d  movzx   edi, bx
0x1800733a0  or      edi, 80070000h
0x1800733a6  mov     rbx, [rsp+28h+arg_0]
0x1800733ab  mov     eax, edi
0x1800733ad  add     rsp, 20h
0x1800733b1  pop     rdi
0x1800733b2  retn
```
