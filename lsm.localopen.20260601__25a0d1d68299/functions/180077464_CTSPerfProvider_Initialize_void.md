# CTSPerfProvider::Initialize(void)

- ea: `0x180077464`
- end: `0x180077613`
- name: `?Initialize@CTSPerfProvider@@SAJXZ`
- size: `431`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180064570`

## callees

- `0x1800077a0`
- `0x18007742c`
- `0x180077464`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800774fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800774fe`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18007752c`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x180077565`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18007759b`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18007752c`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x180077565`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18007759b`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x1800774e6`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x1800774e6`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x1800775bd`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x1800775bd`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterSetInfo` at `0x1800774af`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterSetInfo` at `0x1800774af`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStartProvider` at `0x180077485`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStartProvider` at `0x180077485`

## string_xrefs

- `0x18007750c`: `PerfCreateInstance FAILED with error: 0x%x`

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
0x180077464  mov     [rsp+arg_0], rbx
0x180077469  push    rdi
0x18007746a  sub     rsp, 20h
0x18007746e  lea     r8, ?hDataSource_tsperf_1@@3PEAXEA; phProvider
0x180077475  xor     edi, edi
0x180077477  lea     rdx, ?ControlCallback_tsperf_1@@YAKKPEAXK@Z; ControlCallback
0x18007747e  lea     rcx, ?ProviderGuid_tsperf_1@@3U_GUID@@A; ProviderGuid
0x180077485  call    cs:__imp_PerfStartProvider
0x18007748c  nop     dword ptr [rax+rax+00h]
0x180077491  mov     ebx, eax
0x180077493  test    eax, eax
0x180077495  jnz     loc_1800775B6
0x18007749b  mov     rcx, cs:?hDataSource_tsperf_1@@3PEAXEA; ProviderHandle
0x1800774a2  lea     rdx, ?CtrSet_tsperf_1_1@@3U_CTRSET_tsperf_1_1@@A; Template
0x1800774a9  mov     r8d, 88h; TemplateSize
0x1800774af  call    cs:__imp_PerfSetCounterSetInfo
0x1800774b6  nop     dword ptr [rax+rax+00h]
0x1800774bb  mov     ebx, eax
0x1800774bd  test    eax, eax
0x1800774bf  jnz     loc_1800775B6
0x1800774c5  mov     rcx, cs:?hDataSource_tsperf_1@@3PEAXEA; ProviderHandle
0x1800774cc  lea     ebx, [rdi+1]
0x1800774cf  xor     r9d, r9d; Id
0x1800774d2  mov     cs:?bInitialized@CTSPerfProvider@@0HA, ebx; int CTSPerfProvider::bInitialized
0x1800774d8  lea     r8, aDefault_0; "_Default"
0x1800774df  lea     rdx, ?CtrSetGuid_tsperf_1_1@@3U_GUID@@A; CounterSetGuid
0x1800774e6  call    cs:__imp_PerfCreateInstance
0x1800774ed  nop     dword ptr [rax+rax+00h]
0x1800774f2  mov     cs:?pInstance@CTSPerfProvider@@0PEAU_PERF_COUNTERSET_INSTANCE@@EA, rax; _PERF_COUNTERSET_INSTANCE * CTSPerfProvider::pInstance
0x1800774f9  test    rax, rax
0x1800774fc  jnz     short loc_180077518
0x1800774fe  call    cs:__imp_GetLastError
0x180077505  nop     dword ptr [rax+rax+00h]
0x18007750a  mov     ebx, eax
0x18007750c  lea     rdx, aPerfcreateinst; "PerfCreateInstance FAILED with error: 0"...
0x180077513  jmp     loc_1800775D0
0x180077518  mov     rcx, cs:?hDataSource_tsperf_1@@3PEAXEA; Provider
0x18007751f  lea     r9, ?ActiveSessions@CTSPerfProvider@@0JC; Address
0x180077526  mov     r8d, ebx; CounterId
0x180077529  mov     rdx, rax; Instance
0x18007752c  call    cs:__imp_PerfSetCounterRefValue
0x180077533  nop     dword ptr [rax+rax+00h]
0x180077538  mov     ebx, eax
0x18007753a  test    eax, eax
0x18007753c  jz      short loc_18007754A
0x18007753e  lea     rdx, aPerfsetcounter_1; "PerfSetCounterRefValue FAILED to set th"...
0x180077545  jmp     loc_1800775D0
0x18007754a  mov     rdx, cs:?pInstance@CTSPerfProvider@@0PEAU_PERF_COUNTERSET_INSTANCE@@EA; Instance
0x180077551  lea     r9, ?InactiveSessions@CTSPerfProvider@@0JC; Address
0x180077558  mov     rcx, cs:?hDataSource_tsperf_1@@3PEAXEA; Provider
0x18007755f  mov     r8d, 2; CounterId
0x180077565  call    cs:__imp_PerfSetCounterRefValue
0x18007756c  nop     dword ptr [rax+rax+00h]
0x180077571  mov     ebx, eax
0x180077573  test    eax, eax
0x180077575  jz      short loc_180077580
0x180077577  lea     rdx, aPerfsetcounter_0; "PerfSetCounterRefValue FAILED to set th"...
0x18007757e  jmp     short loc_1800775D0
0x180077580  mov     rdx, cs:?pInstance@CTSPerfProvider@@0PEAU_PERF_COUNTERSET_INSTANCE@@EA; Instance
0x180077587  lea     r9, ?TotalSessions@CTSPerfProvider@@0JC; Address
0x18007758e  mov     rcx, cs:?hDataSource_tsperf_1@@3PEAXEA; Provider
0x180077595  mov     r8d, 3; CounterId
0x18007759b  call    cs:__imp_PerfSetCounterRefValue
0x1800775a2  nop     dword ptr [rax+rax+00h]
0x1800775a7  mov     ebx, eax
0x1800775a9  test    eax, eax
0x1800775ab  jz      short loc_180077605
0x1800775ad  lea     rdx, aPerfsetcounter; "PerfSetCounterRefValue FAILED to set th"...
0x1800775b4  jmp     short loc_1800775D0
0x1800775b6  mov     rcx, cs:?hDataSource_tsperf_1@@3PEAXEA; ProviderHandle
0x1800775bd  call    cs:__imp_PerfStopProvider
0x1800775c4  nop     dword ptr [rax+rax+00h]
0x1800775c9  lea     rdx, aPerfautoinitia; "PerfAutoInitialize FAILED with error: 0"...
0x1800775d0  mov     ecx, 8; int
0x1800775d5  mov     r8d, ebx
0x1800775d8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800775dd  test    ebx, ebx
0x1800775df  jz      short loc_180077605
0x1800775e1  cmp     cs:?bInitialized@CTSPerfProvider@@0HA, edi; int CTSPerfProvider::bInitialized
0x1800775e7  jz      short loc_1800775F4
0x1800775e9  call    ?Cleanup@CTSPerfProvider@@SAXXZ; CTSPerfProvider::Cleanup(void)
0x1800775ee  mov     cs:?bInitialized@CTSPerfProvider@@0HA, edi; int CTSPerfProvider::bInitialized
0x1800775f4  test    ebx, ebx
0x1800775f6  jg      short loc_1800775FC
0x1800775f8  mov     edi, ebx
0x1800775fa  jmp     short loc_180077605
0x1800775fc  movzx   edi, bx
0x1800775ff  or      edi, 80070000h
0x180077605  mov     rbx, [rsp+28h+arg_0]
0x18007760a  mov     eax, edi
0x18007760c  add     rsp, 20h
0x180077610  pop     rdi
0x180077611  retn
```
