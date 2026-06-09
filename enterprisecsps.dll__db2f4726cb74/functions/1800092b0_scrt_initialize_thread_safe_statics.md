# __scrt_initialize_thread_safe_statics

- ea: `0x1800092b0`
- end: `0x180009380`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180008fc0`
- `0x180009190`
- `0x1800092b0`
- `0x180009a20`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800092d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800092e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800092d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800092e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009300`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009313`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009300`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009313`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000933f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000933f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800092c6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800092c6`

## string_xrefs

- `0x1800092cc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800092e1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&CriticalSection, 0xFA0u);
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
    qword_180156F18 = (__int64)ProcAddress;
    qword_180156F20 = (__int64)v2;
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
0x1800092b0  mov     [rsp+arg_0], rbx
0x1800092b5  push    rdi
0x1800092b6  sub     rsp, 20h
0x1800092ba  mov     edx, 0FA0h; dwSpinCount
0x1800092bf  lea     rcx, CriticalSection; lpCriticalSection
0x1800092c6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800092cc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800092d3  call    cs:__imp_GetModuleHandleW
0x1800092d9  mov     rbx, rax
0x1800092dc  test    rax, rax
0x1800092df  jnz     short loc_1800092F6
0x1800092e1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800092e8  call    cs:__imp_GetModuleHandleW
0x1800092ee  mov     rbx, rax
0x1800092f1  test    rax, rax
0x1800092f4  jz      short loc_180009375
0x1800092f6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800092fd  mov     rcx, rbx; hModule
0x180009300  call    cs:__imp_GetProcAddress
0x180009306  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000930d  mov     rcx, rbx; hModule
0x180009310  mov     rdi, rax
0x180009313  call    cs:__imp_GetProcAddress
0x180009319  test    rdi, rdi
0x18000931c  jz      short loc_180009333
0x18000931e  test    rax, rax
0x180009321  jz      short loc_180009333
0x180009323  mov     cs:qword_180156F18, rdi
0x18000932a  mov     cs:qword_180156F20, rax
0x180009331  jmp     short loc_180009351
0x180009333  xor     r9d, r9d; lpName
0x180009336  xor     r8d, r8d; bInitialState
0x180009339  xor     ecx, ecx; lpEventAttributes
0x18000933b  lea     edx, [r9+1]; bManualReset
0x18000933f  call    cs:__imp_CreateEventW
0x180009345  mov     cs:hHandle, rax
0x18000934c  test    rax, rax
0x18000934f  jz      short loc_180009375
0x180009351  xor     ecx, ecx
0x180009353  call    __scrt_initialize_onexit_tables
0x180009358  test    al, al
0x18000935a  jz      short loc_180009375
0x18000935c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180009363  call    atexit
0x180009368  mov     rbx, [rsp+28h+arg_0]
0x18000936d  xor     eax, eax
0x18000936f  add     rsp, 20h
0x180009373  pop     rdi
0x180009374  retn
0x180009375  mov     ecx, 7
0x18000937a  call    __scrt_fastfail
```
