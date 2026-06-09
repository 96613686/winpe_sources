# _threadstart

- ea: `0x18003e420`
- end: `0x18003e49d`
- name: `_threadstart`
- size: `125`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180007d70`
- `0x180017b50`
- `0x18003de50`
- `0x18003deb0`
- `0x18003e3a8`
- `0x18003e420`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e457`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e457`
- `api-ms-win-core-fibers-l1-1-0!FlsSetValue` at `0x18003e44d`
- `api-ms-win-core-fibers-l1-1-0!FlsSetValue` at `0x18003e44d`
- `api-ms-win-core-fibers-l1-1-0!FlsGetValue` at `0x18003e435`
- `api-ms-win-core-fibers-l1-1-0!FlsGetValue` at `0x18003e435`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x18003e45f`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x18003e45f`

## pseudocode

```c
void __fastcall __noreturn threadstart(_QWORD *Parameter)
{
  DWORD flsindex; // eax
  _QWORD *Value; // rax
  DWORD v4; // eax
  DWORD LastError; // eax

  CrtSetReportMode();
  flsindex = _get_flsindex();
  Value = FlsGetValue(flsindex);
  if ( Value )
  {
    Value[18] = Parameter[18];
    Value[19] = Parameter[19];
    Value[1] = Parameter[1];
    freefls(Parameter);
  }
  else
  {
    v4 = _get_flsindex();
    if ( !FlsSetValue(v4, Parameter) )
    {
      LastError = GetLastError();
      ExitThread(LastError);
    }
  }
  CrtSetDbgBlockType();
  callthreadstart();
}

```

## disassembly

```asm
0x18003e420  push    rbx
0x18003e422  sub     rsp, 20h
0x18003e426  mov     rbx, rcx
0x18003e429  call    _CrtSetReportMode
0x18003e42e  call    __get_flsindex
0x18003e433  mov     ecx, eax; dwFlsIndex
0x18003e435  call    cs:__imp_FlsGetValue
0x18003e43b  mov     rcx, rax
0x18003e43e  test    rax, rax
0x18003e441  jnz     short loc_18003E466
0x18003e443  call    __get_flsindex
0x18003e448  mov     ecx, eax; dwFlsIndex
0x18003e44a  mov     rdx, rbx; lpFlsData
0x18003e44d  call    cs:__imp_FlsSetValue
0x18003e453  test    eax, eax
0x18003e455  jnz     short loc_18003E492
0x18003e457  call    cs:__imp_GetLastError
0x18003e45d  mov     ecx, eax; dwExitCode
0x18003e45f  call    cs:__imp_ExitThread
0x18003e466  mov     rax, [rbx+90h]
0x18003e46d  mov     [rcx+90h], rax
0x18003e474  mov     rax, [rbx+98h]
0x18003e47b  mov     [rcx+98h], rax
0x18003e482  mov     rax, [rbx+8]
0x18003e486  mov     [rcx+8], rax
0x18003e48a  mov     rcx, rbx; lpFlsData
0x18003e48d  call    _freefls
0x18003e492  call    _CrtSetDbgBlockType
0x18003e497  call    _callthreadstart
```
