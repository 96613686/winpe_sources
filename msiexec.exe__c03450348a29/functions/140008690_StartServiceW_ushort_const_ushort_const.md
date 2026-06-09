# StartServiceW(ushort const *,ushort const *)

- ea: `0x140008690`
- end: `0x1400086f0`
- name: `?StartServiceW@@YAHPEBG0@Z`
- size: `96`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x1400011e4`

## callees

- `0x140007110`
- `0x140008690`

## import_xrefs

- `ADVAPI32!StartServiceCtrlDispatcherW` at `0x1400086c1`
- `ADVAPI32!StartServiceCtrlDispatcherW` at `0x1400086c1`
- `KERNEL32!GetLastError` at `0x1400086cb`
- `KERNEL32!GetLastError` at `0x1400086cb`

## string_xrefs

- `0x140008697`: `MSIServer`
- `0x1400086d3`: `StartServiceCtrlDispatcher failed.`

## pseudocode

```c
__int64 __fastcall StartServiceW(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  DWORD LastError; // eax
  SERVICE_TABLE_ENTRYW v4; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+30h] [rbp-18h]
  __int64 v6; // [rsp+38h] [rbp-10h]

  v5 = 0;
  v4.lpServiceName = (LPWSTR)L"MSIServer";
  v6 = 0;
  v4.lpServiceProc = (LPSERVICE_MAIN_FUNCTIONW)ServiceMain;
  if ( StartServiceCtrlDispatcherW(&v4) )
    return 0x8000;
  LastError = GetLastError();
  ReportErrorToDebugOutput((const WCHAR *)L"StartServiceCtrlDispatcher failed.", LastError);
  return 1;
}

```

## disassembly

```asm
0x140008690  mov     r11, rsp
0x140008693  sub     rsp, 48h
0x140008697  lea     rax, ServiceName; "MSIServer"
0x14000869e  mov     qword ptr [r11-18h], 0
0x1400086a6  mov     [r11-28h], rax
0x1400086aa  lea     rcx, [r11-28h]; lpServiceStartTable
0x1400086ae  lea     rax, ?ServiceMain@@YAXKPEAPEAG@Z; ServiceMain(ulong,ushort * *)
0x1400086b5  mov     qword ptr [r11-10h], 0
0x1400086bd  mov     [r11-20h], rax
0x1400086c1  call    cs:__imp_StartServiceCtrlDispatcherW
0x1400086c7  test    eax, eax
0x1400086c9  jnz     short loc_1400086E6
0x1400086cb  call    cs:__imp_GetLastError
0x1400086d1  mov     edx, eax; unsigned int
0x1400086d3  lea     rcx, aStartservicect; "StartServiceCtrlDispatcher failed."
0x1400086da  call    ?ReportErrorToDebugOutput@@YAXPEBGK@Z; ReportErrorToDebugOutput(ushort const *,ulong)
0x1400086df  mov     eax, 1
0x1400086e4  jmp     short loc_1400086EB
0x1400086e6  mov     eax, 8000h
0x1400086eb  add     rsp, 48h
0x1400086ef  retn
```
