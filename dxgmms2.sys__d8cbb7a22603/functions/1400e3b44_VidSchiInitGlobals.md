# VidSchiInitGlobals

- ea: `0x1400e3b44`
- end: `0x1400e3c94`
- name: `VidSchiInitGlobals`
- size: `336`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14012d078`

## callees

- `0x140004268`
- `0x1400e3b44`

## import_xrefs

- `ntoskrnl!PcwRegister` at `0x1400e3bab`
- `ntoskrnl!PcwRegister` at `0x1400e3bab`
- `watchdog!WdLogSingleEntry1` at `0x1400e3bc8`
- `watchdog!WdLogSingleEntry1` at `0x1400e3c36`
- `watchdog!WdLogSingleEntry1` at `0x1400e3bc8`
- `watchdog!WdLogSingleEntry1` at `0x1400e3c36`
- `dxgkrnl!DxgCreateLiveDumpWithWdLogs` at `0x1400e3c1d`
- `dxgkrnl!DxgCreateLiveDumpWithWdLogs` at `0x1400e3c1d`

## string_xrefs

- `0x1400e3c47`: `Failed to DxgCreateLiveDumpWithWdLogs, error: 0x%I64x`
- `0x1400e3bd9`: `Failed to create RegisterGpuPerformanceCounterSetEngine, returning 0x%I64x`

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
  qword_140087990 = (__int64)&gAdapterListHead;
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
0x1400e3b44  mov     r11, rsp
0x1400e3b47  mov     [r11+8], rbx
0x1400e3b4b  mov     [r11+10h], rsi
0x1400e3b4f  push    rdi
0x1400e3b50  sub     rsp, 90h
0x1400e3b57  lea     rax, gAdapterListHead
0x1400e3b5e  mov     qword ptr [r11-48h], 200h
0x1400e3b66  mov     cs:qword_140087990, rax
0x1400e3b6d  lea     rdx, [r11-48h]; Info
0x1400e3b71  mov     cs:gAdapterListHead, rax
0x1400e3b78  lea     rcx, GpuPerformanceCounterSetEngine; Registration
0x1400e3b7f  xor     esi, esi
0x1400e3b81  mov     qword ptr [r11-38h], 2
0x1400e3b89  lea     rax, ?Name@?1??InitRegistrationInformationGpuPerformanceCounterSetEngine@@9@4U_UNICODE_STRING@@B; _UNICODE_STRING const `InitRegistrationInformationGpuPerformanceCounterSetEngine'::`2'::Name
0x1400e3b90  mov     [r11-18h], rsi
0x1400e3b94  mov     [r11-40h], rax
0x1400e3b98  lea     rax, ?Descriptors@?1??InitRegistrationInformationGpuPerformanceCounterSetEngine@@9@4QBU_PCW_COUNTER_DESCRIPTOR@@B; _PCW_COUNTER_DESCRIPTOR const near * const `InitRegistrationInformationGpuPerformanceCounterSetEngine'::`2'::Descriptors
0x1400e3b9f  mov     [r11-30h], rax
0x1400e3ba3  mov     [r11-28h], rsi
0x1400e3ba7  mov     [r11-20h], rsi
0x1400e3bab  call    cs:__imp_PcwRegister
0x1400e3bb2  nop     dword ptr [rax+rax+00h]
0x1400e3bb7  movsxd  rdi, eax
0x1400e3bba  test    eax, eax
0x1400e3bbc  jns     loc_1400E3C75
0x1400e3bc2  mov     rdx, rdi
0x1400e3bc5  lea     ecx, [rsi+1]
0x1400e3bc8  call    cs:__imp_WdLogSingleEntry1
0x1400e3bcf  nop     dword ptr [rax+rax+00h]
0x1400e3bd4  mov     [rsp+98h+var_60], rsi
0x1400e3bd9  lea     r9, aFailedToCreate_9; "Failed to create RegisterGpuPerformance"...
0x1400e3be0  mov     [rsp+98h+var_68], rsi
0x1400e3be5  mov     edx, 40000h
0x1400e3bea  mov     [rsp+98h+var_70], rsi
0x1400e3bef  mov     [rsp+98h+var_78], rdi
0x1400e3bf4  mov     cs:WdLogGlobalForLineNumber, 0B9h
0x1400e3bfe  call    DxgkLogInternalTriageEvent
0x1400e3c03  mov     byte ptr [rsp+98h+var_70], sil
0x1400e3c08  xor     r9d, r9d
0x1400e3c0b  mov     r8, rdi
0x1400e3c0e  mov     [rsp+98h+var_78], rsi
0x1400e3c13  mov     edx, 811h
0x1400e3c18  mov     ecx, 193h
0x1400e3c1d  call    cs:__imp_?DxgCreateLiveDumpWithWdLogs@@YAJK_K000T_WD_LIVEREPORT_FLAGS@@@Z; DxgCreateLiveDumpWithWdLogs(ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,_WD_LIVEREPORT_FLAGS)
0x1400e3c24  nop     dword ptr [rax+rax+00h]
0x1400e3c29  test    eax, eax
0x1400e3c2b  jns     short loc_1400E3C71
0x1400e3c2d  movsxd  rbx, eax
0x1400e3c30  lea     ecx, [rsi+1]
0x1400e3c33  mov     rdx, rbx
0x1400e3c36  call    cs:__imp_WdLogSingleEntry1
0x1400e3c3d  nop     dword ptr [rax+rax+00h]
0x1400e3c42  mov     [rsp+98h+var_60], rsi
0x1400e3c47  lea     r9, aFailedToDxgcre; "Failed to DxgCreateLiveDumpWithWdLogs, "...
0x1400e3c4e  mov     [rsp+98h+var_68], rsi
0x1400e3c53  mov     edx, 40000h
0x1400e3c58  mov     [rsp+98h+var_70], rsi
0x1400e3c5d  mov     [rsp+98h+var_78], rbx
0x1400e3c62  mov     cs:WdLogGlobalForLineNumber, 0CEh
0x1400e3c6c  call    DxgkLogInternalTriageEvent
0x1400e3c71  mov     eax, edi
0x1400e3c73  jmp     short loc_1400E3C7E
0x1400e3c75  mov     cs:?PerfCounterSetEngineRegistered@@3_NA, 1; bool PerfCounterSetEngineRegistered
0x1400e3c7c  xor     eax, eax
0x1400e3c7e  lea     r11, [rsp+98h+var_8]
0x1400e3c86  mov     rbx, [r11+10h]
0x1400e3c8a  mov     rsi, [r11+18h]
0x1400e3c8e  mov     rsp, r11
0x1400e3c91  pop     rdi
0x1400e3c92  retn
```
