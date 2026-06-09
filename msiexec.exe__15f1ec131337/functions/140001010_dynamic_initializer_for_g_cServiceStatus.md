# _dynamic_initializer_for__g_cServiceStatus__

- ea: `0x140001010`
- end: `0x14000105b`
- name: `_dynamic_initializer_for__g_cServiceStatus__`
- size: `75`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140003570`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x14000101b`
- `KERNEL32!InitializeCriticalSection` at `0x14000101b`

## pseudocode

```c
int dynamic_initializer_for__g_cServiceStatus__()
{
  InitializeCriticalSection(&g_cServiceStatus);
  *(_OWORD *)&ServiceStatus.dwServiceType = 0;
  ServiceStatus.dwServiceType = 16;
  *(_OWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  ServiceStatus.dwServiceSpecificExitCode = 0;
  hServiceStatus = 0;
  return atexit(dynamic_atexit_destructor_for__g_cServiceStatus__);
}

```

## disassembly

```asm
0x140001010  sub     rsp, 28h
0x140001014  lea     rcx, ?g_cServiceStatus@@3VServiceStatus@@A; lpCriticalSection
0x14000101b  call    cs:__imp_InitializeCriticalSection
0x140001021  xorps   xmm0, xmm0
0x140001024  lea     rcx, _dynamic_atexit_destructor_for__g_cServiceStatus__
0x14000102b  movups  xmmword ptr cs:ServiceStatus.dwServiceType, xmm0
0x140001032  xor     eax, eax
0x140001034  mov     cs:ServiceStatus.dwServiceType, 10h
0x14000103e  movups  xmmword ptr cs:ServiceStatus.dwWin32ExitCode, xmm0
0x140001045  mov     cs:ServiceStatus.dwServiceSpecificExitCode, eax
0x14000104b  mov     cs:hServiceStatus, rax
0x140001052  add     rsp, 28h
0x140001056  jmp     atexit
```
