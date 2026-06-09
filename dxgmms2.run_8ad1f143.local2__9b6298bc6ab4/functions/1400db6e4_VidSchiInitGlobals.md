# VidSchiInitGlobals

- ea: `0x1400db6e4`
- end: `0x1400db834`
- name: `VidSchiInitGlobals`
- size: `336`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140127078`

## callees

- `0x1400045ec`
- `0x1400db6e4`

## import_xrefs

- `ntoskrnl!PcwRegister` at `0x1400db74b`
- `ntoskrnl!PcwRegister` at `0x1400db74b`
- `watchdog!WdLogSingleEntry1` at `0x1400db768`
- `watchdog!WdLogSingleEntry1` at `0x1400db7d6`
- `watchdog!WdLogSingleEntry1` at `0x1400db768`
- `watchdog!WdLogSingleEntry1` at `0x1400db7d6`
- `dxgkrnl!DxgCreateLiveDumpWithWdLogs` at `0x1400db7bd`
- `dxgkrnl!DxgCreateLiveDumpWithWdLogs` at `0x1400db7bd`

## string_xrefs

- `0x1400db7e7`: `Failed to DxgCreateLiveDumpWithWdLogs, error: 0x%I64x`
- `0x1400db779`: `Failed to create RegisterGpuPerformanceCounterSetEngine, returning 0x%I64x`

## pseudocode

```c
__int64 VidSchiInitGlobals()
{
  NTSTATUS v0; // eax
  __int64 v1; // rdi
  int v2; // ecx
  int v3; // r8d
  int LiveDumpWithWdLogs; // eax
  __int64 v5; // rbx
  int v6; // ecx
  int v7; // r8d
  int v9; // [rsp+28h] [rbp-70h]
  struct _PCW_REGISTRATION_INFORMATION v10; // [rsp+50h] [rbp-48h] BYREF
  __int64 v11; // [rsp+80h] [rbp-18h]

  *(_QWORD *)&v10.Version = 512;
  qword_140086988 = (__int64)&gAdapterListHead;
  gAdapterListHead = &gAdapterListHead;
  *(_QWORD *)&v10.CounterCount = 2;
  v11 = 0;
  v10.Name = (PCUNICODE_STRING)&`InitRegistrationInformationGpuPerformanceCounterSetEngine'::`2'::Name;
  v10.Counters = (PPCW_COUNTER_DESCRIPTOR)`InitRegistrationInformationGpuPerformanceCounterSetEngine'::`2'::Descriptors;
  v10.Callback = 0;
  v10.CallbackContext = 0;
  v0 = PcwRegister(&GpuPerformanceCounterSetEngine, &v10);
  v1 = v0;
  if ( v0 >= 0 )
  {
    PerfCounterSetEngineRegistered = 1;
    return 0;
  }
  else
  {
    WdLogSingleEntry1(1, v0);
    WdLogGlobalForLineNumber = 185;
    DxgkLogInternalTriageEvent(
      v2,
      0x40000,
      v3,
      (unsigned int)L"Failed to create RegisterGpuPerformanceCounterSetEngine, returning 0x%I64x",
      v1,
      0,
      0,
      0);
    LOBYTE(v9) = 0;
    LiveDumpWithWdLogs = DxgCreateLiveDumpWithWdLogs(403, 2065, v1, 0, 0, v9);
    if ( LiveDumpWithWdLogs < 0 )
    {
      v5 = LiveDumpWithWdLogs;
      WdLogSingleEntry1(1, LiveDumpWithWdLogs);
      WdLogGlobalForLineNumber = 206;
      DxgkLogInternalTriageEvent(
        v6,
        0x40000,
        v7,
        (unsigned int)L"Failed to DxgCreateLiveDumpWithWdLogs, error: 0x%I64x",
        v5,
        0,
        0,
        0);
    }
    return (unsigned int)v1;
  }
}

```

## disassembly

```asm
0x1400db6e4  mov     r11, rsp
0x1400db6e7  mov     [r11+8], rbx
0x1400db6eb  mov     [r11+10h], rsi
0x1400db6ef  push    rdi
0x1400db6f0  sub     rsp, 90h
0x1400db6f7  lea     rax, gAdapterListHead
0x1400db6fe  mov     qword ptr [r11-48h], 200h
0x1400db706  mov     cs:qword_140086988, rax
0x1400db70d  lea     rdx, [r11-48h]; Info
0x1400db711  mov     cs:gAdapterListHead, rax
0x1400db718  lea     rcx, GpuPerformanceCounterSetEngine; Registration
0x1400db71f  xor     esi, esi
0x1400db721  mov     qword ptr [r11-38h], 2
0x1400db729  lea     rax, ?Name@?1??InitRegistrationInformationGpuPerformanceCounterSetEngine@@9@4U_UNICODE_STRING@@B; _UNICODE_STRING const `InitRegistrationInformationGpuPerformanceCounterSetEngine'::`2'::Name
0x1400db730  mov     [r11-18h], rsi
0x1400db734  mov     [r11-40h], rax
0x1400db738  lea     rax, ?Descriptors@?1??InitRegistrationInformationGpuPerformanceCounterSetEngine@@9@4QBU_PCW_COUNTER_DESCRIPTOR@@B; _PCW_COUNTER_DESCRIPTOR const near * const `InitRegistrationInformationGpuPerformanceCounterSetEngine'::`2'::Descriptors
0x1400db73f  mov     [r11-30h], rax
0x1400db743  mov     [r11-28h], rsi
0x1400db747  mov     [r11-20h], rsi
0x1400db74b  call    cs:__imp_PcwRegister
0x1400db752  nop     dword ptr [rax+rax+00h]
0x1400db757  movsxd  rdi, eax
0x1400db75a  test    eax, eax
0x1400db75c  jns     loc_1400DB815
0x1400db762  mov     rdx, rdi
0x1400db765  lea     ecx, [rsi+1]
0x1400db768  call    cs:__imp_WdLogSingleEntry1
0x1400db76f  nop     dword ptr [rax+rax+00h]
0x1400db774  mov     [rsp+98h+var_60], rsi
0x1400db779  lea     r9, aFailedToCreate_9; "Failed to create RegisterGpuPerformance"...
0x1400db780  mov     [rsp+98h+var_68], rsi
0x1400db785  mov     edx, 40000h
0x1400db78a  mov     [rsp+98h+var_70], rsi
0x1400db78f  mov     [rsp+98h+var_78], rdi
0x1400db794  mov     cs:WdLogGlobalForLineNumber, 0B9h
0x1400db79e  call    DxgkLogInternalTriageEvent
0x1400db7a3  mov     byte ptr [rsp+98h+var_70], sil
0x1400db7a8  xor     r9d, r9d
0x1400db7ab  mov     r8, rdi
0x1400db7ae  mov     [rsp+98h+var_78], rsi
0x1400db7b3  mov     edx, 811h
0x1400db7b8  mov     ecx, 193h
0x1400db7bd  call    cs:__imp_?DxgCreateLiveDumpWithWdLogs@@YAJK_K000T_WD_LIVEREPORT_FLAGS@@@Z; DxgCreateLiveDumpWithWdLogs(ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,_WD_LIVEREPORT_FLAGS)
0x1400db7c4  nop     dword ptr [rax+rax+00h]
0x1400db7c9  test    eax, eax
0x1400db7cb  jns     short loc_1400DB811
0x1400db7cd  movsxd  rbx, eax
0x1400db7d0  lea     ecx, [rsi+1]
0x1400db7d3  mov     rdx, rbx
0x1400db7d6  call    cs:__imp_WdLogSingleEntry1
0x1400db7dd  nop     dword ptr [rax+rax+00h]
0x1400db7e2  mov     [rsp+98h+var_60], rsi
0x1400db7e7  lea     r9, aFailedToDxgcre; "Failed to DxgCreateLiveDumpWithWdLogs, "...
0x1400db7ee  mov     [rsp+98h+var_68], rsi
0x1400db7f3  mov     edx, 40000h
0x1400db7f8  mov     [rsp+98h+var_70], rsi
0x1400db7fd  mov     [rsp+98h+var_78], rbx
0x1400db802  mov     cs:WdLogGlobalForLineNumber, 0CEh
0x1400db80c  call    DxgkLogInternalTriageEvent
0x1400db811  mov     eax, edi
0x1400db813  jmp     short loc_1400DB81E
0x1400db815  mov     cs:?PerfCounterSetEngineRegistered@@3_NA, 1; bool PerfCounterSetEngineRegistered
0x1400db81c  xor     eax, eax
0x1400db81e  lea     r11, [rsp+98h+var_8]
0x1400db826  mov     rbx, [r11+10h]
0x1400db82a  mov     rsi, [r11+18h]
0x1400db82e  mov     rsp, r11
0x1400db831  pop     rdi
0x1400db832  retn
```
