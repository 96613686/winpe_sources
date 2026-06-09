# _threadstartex

- ea: `0x18003e630`
- end: `0x18003e6ad`
- name: `_threadstartex`
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
- `0x18003e5b8`
- `0x18003e630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e667`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e667`
- `api-ms-win-core-fibers-l1-1-0!FlsSetValue` at `0x18003e65d`
- `api-ms-win-core-fibers-l1-1-0!FlsSetValue` at `0x18003e65d`
- `api-ms-win-core-fibers-l1-1-0!FlsGetValue` at `0x18003e645`
- `api-ms-win-core-fibers-l1-1-0!FlsGetValue` at `0x18003e645`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x18003e66f`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x18003e66f`

## pseudocode

```c
void __fastcall __noreturn threadstartex(_QWORD *Parameter)
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
  callthreadstartex();
}

```

## disassembly

```asm
0x18003e630  push    rbx
0x18003e632  sub     rsp, 20h
0x18003e636  mov     rbx, rcx
0x18003e639  call    _CrtSetReportMode
0x18003e63e  call    __get_flsindex
0x18003e643  mov     ecx, eax; dwFlsIndex
0x18003e645  call    cs:__imp_FlsGetValue
0x18003e64b  mov     rcx, rax
0x18003e64e  test    rax, rax
0x18003e651  jnz     short loc_18003E676
0x18003e653  call    __get_flsindex
0x18003e658  mov     ecx, eax; dwFlsIndex
0x18003e65a  mov     rdx, rbx; lpFlsData
0x18003e65d  call    cs:__imp_FlsSetValue
0x18003e663  test    eax, eax
0x18003e665  jnz     short loc_18003E6A2
0x18003e667  call    cs:__imp_GetLastError
0x18003e66d  mov     ecx, eax; dwExitCode
0x18003e66f  call    cs:__imp_ExitThread
0x18003e676  mov     rax, [rbx+90h]
0x18003e67d  mov     [rcx+90h], rax
0x18003e684  mov     rax, [rbx+98h]
0x18003e68b  mov     [rcx+98h], rax
0x18003e692  mov     rax, [rbx+8]
0x18003e696  mov     [rcx+8], rax
0x18003e69a  mov     rcx, rbx; lpFlsData
0x18003e69d  call    _freefls
0x18003e6a2  call    _CrtSetDbgBlockType
0x18003e6a7  call    _callthreadstartex
```
