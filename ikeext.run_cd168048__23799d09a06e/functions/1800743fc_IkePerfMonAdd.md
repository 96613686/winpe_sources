# IkePerfMonAdd

- ea: `0x1800743fc`
- end: `0x18007449f`
- name: `IkePerfMonAdd`
- size: `163`
- prototype: `__int64 __fastcall(LPCGUID CounterSetGuid, ULONG TemplateSize)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800744a8`

## callees

- `0x1800061ec`
- `0x180008388`
- `0x1800743fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074463`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074463`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterSetInfo` at `0x180074425`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterSetInfo` at `0x180074425`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180074455`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180074455`

## string_xrefs

- `0x180074469`: `PerfCreateInstance`

## pseudocode

```c
__int64 __fastcall IkePerfMonAdd(
        struct _PERF_COUNTERSET_INFO *CounterSetGuid,
        ULONG TemplateSize,
        PPERF_COUNTERSET_INSTANCE *a3)
{
  ULONG LastError; // eax
  __int64 v6; // rcx
  const char *v7; // rdx
  __int64 v8; // rbx
  PPERF_COUNTERSET_INSTANCE Instance; // rax

  LastError = PerfSetCounterSetInfo(*(HANDLE *)&gIkeExtGlobals[83].LockCount, CounterSetGuid, TemplateSize);
  if ( LastError )
  {
    v7 = "PerfSetCounterSetInfo";
LABEL_5:
    v8 = WfpReportSysErrorAsWinError(v6, v7, LastError, 1);
    return IkeReturnError(v8, "IkePerfMonAdd");
  }
  v8 = 0;
  Instance = PerfCreateInstance(
               *(HANDLE *)&gIkeExtGlobals[83].LockCount,
               &CounterSetGuid->CounterSetGuid,
               L"_Default",
               0);
  *a3 = Instance;
  if ( !Instance )
  {
    LastError = GetLastError();
    v7 = "PerfCreateInstance";
    goto LABEL_5;
  }
  return IkeReturnError(v8, "IkePerfMonAdd");
}

```

## disassembly

```asm
0x1800743fc  mov     [rsp+arg_0], rbx
0x180074401  mov     [rsp+arg_8], rsi
0x180074406  push    rdi
0x180074407  sub     rsp, 20h
0x18007440b  mov     rdi, rcx
0x18007440e  mov     rsi, r8
0x180074411  mov     r8d, edx; TemplateSize
0x180074414  mov     rdx, rcx; Template
0x180074417  mov     rcx, cs:gIkeExtGlobals
0x18007441e  mov     rcx, [rcx+0D00h]; ProviderHandle
0x180074425  call    cs:__imp_PerfSetCounterSetInfo
0x18007442b  test    eax, eax
0x18007442d  jz      short loc_180074438
0x18007442f  lea     rdx, aPerfsetcounter; "PerfSetCounterSetInfo"
0x180074436  jmp     short loc_180074470
0x180074438  mov     rcx, cs:gIkeExtGlobals
0x18007443f  lea     r8, Name; "_Default"
0x180074446  xor     r9d, r9d; Id
0x180074449  mov     rdx, rdi; CounterSetGuid
0x18007444c  xor     ebx, ebx
0x18007444e  mov     rcx, [rcx+0D00h]; ProviderHandle
0x180074455  call    cs:__imp_PerfCreateInstance
0x18007445b  mov     [rsi], rax
0x18007445e  test    rax, rax
0x180074461  jnz     short loc_180074481
0x180074463  call    cs:__imp_GetLastError
0x180074469  lea     rdx, aPerfcreateinst; "PerfCreateInstance"
0x180074470  mov     r9d, 1
0x180074476  mov     r8d, eax
0x180074479  call    WfpReportSysErrorAsWinError
0x18007447e  mov     rbx, rax
0x180074481  lea     rdx, aIkeperfmonadd; "IkePerfMonAdd"
0x180074488  mov     rcx, rbx
0x18007448b  mov     rbx, [rsp+28h+arg_0]
0x180074490  mov     rsi, [rsp+28h+arg_8]
0x180074495  add     rsp, 20h
0x180074499  pop     rdi
0x18007449a  jmp     IkeReturnError
```
