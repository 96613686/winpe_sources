# __scrt_initialize_thread_safe_statics

- ea: `0x180010280`
- end: `0x180010350`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000ffd0`
- `0x1800101a0`
- `0x180010280`
- `0x180010664`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800102d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800102e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800102d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800102e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800102a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800102b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800102a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800102b8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180010296`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180010296`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001030f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001030f`

## string_xrefs

- `0x18001029c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800102b1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180035EA8, 0xFA0u);
  ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-synch-l1-2-0.dll");
  if ( !ModuleHandleW )
  {
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    if ( !ModuleHandleW )
      goto LABEL_9;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "SleepConditionVariableCS");
  v2 = GetProcAddress(ModuleHandleW, "WakeAllConditionVariable");
  if ( ProcAddress && v2 )
  {
    qword_180035ED0 = (__int64)ProcAddress;
    qword_180035ED8 = (__int64)v2;
  }
  else
  {
    hHandle = CreateEventW(0, 1, 0, 0);
    if ( !hHandle )
      goto LABEL_9;
  }
  if ( !(unsigned __int8)_scrt_initialize_onexit_tables(0) )
LABEL_9:
    _scrt_fastfail(7);
  atexit(_scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x180010280  mov     [rsp+arg_0], rbx
0x180010285  push    rdi
0x180010286  sub     rsp, 20h
0x18001028a  mov     edx, 0FA0h; dwSpinCount
0x18001028f  lea     rcx, stru_180035EA8; lpCriticalSection
0x180010296  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18001029c  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x1800102a3  call    cs:__imp_GetModuleHandleW
0x1800102a9  mov     rbx, rax
0x1800102ac  test    rax, rax
0x1800102af  jnz     short loc_1800102C6
0x1800102b1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800102b8  call    cs:__imp_GetModuleHandleW
0x1800102be  mov     rbx, rax
0x1800102c1  test    rax, rax
0x1800102c4  jz      short loc_180010345
0x1800102c6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800102cd  mov     rcx, rbx; hModule
0x1800102d0  call    cs:__imp_GetProcAddress
0x1800102d6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800102dd  mov     rcx, rbx; hModule
0x1800102e0  mov     rdi, rax
0x1800102e3  call    cs:__imp_GetProcAddress
0x1800102e9  test    rdi, rdi
0x1800102ec  jz      short loc_180010303
0x1800102ee  test    rax, rax
0x1800102f1  jz      short loc_180010303
0x1800102f3  mov     cs:qword_180035ED0, rdi
0x1800102fa  mov     cs:qword_180035ED8, rax
0x180010301  jmp     short loc_180010321
0x180010303  xor     r9d, r9d; lpName
0x180010306  xor     r8d, r8d; bInitialState
0x180010309  xor     ecx, ecx; lpEventAttributes
0x18001030b  lea     edx, [r9+1]; bManualReset
0x18001030f  call    cs:__imp_CreateEventW
0x180010315  mov     cs:hHandle, rax
0x18001031c  test    rax, rax
0x18001031f  jz      short loc_180010345
0x180010321  xor     ecx, ecx
0x180010323  call    __scrt_initialize_onexit_tables
0x180010328  test    al, al
0x18001032a  jz      short loc_180010345
0x18001032c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180010333  call    atexit
0x180010338  mov     rbx, [rsp+28h+arg_0]
0x18001033d  xor     eax, eax
0x18001033f  add     rsp, 20h
0x180010343  pop     rdi
0x180010344  retn
0x180010345  mov     ecx, 7
0x18001034a  call    __scrt_fastfail
```
