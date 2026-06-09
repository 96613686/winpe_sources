# __scrt_initialize_thread_safe_statics

- ea: `0x1800029c0`
- end: `0x180002a90`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002794`
- `0x180002964`
- `0x1800029c0`
- `0x180002e78`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002a10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002a23`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002a10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002a23`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800029e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800029f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800029e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800029f8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800029d6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800029d6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002a4f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002a4f`

## string_xrefs

- `0x1800029dc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800029f1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180021DA8, 0xFA0u);
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
    qword_180021DD0 = (__int64)ProcAddress;
    qword_180021DD8 = (__int64)v2;
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
0x1800029c0  mov     [rsp+arg_0], rbx
0x1800029c5  push    rdi
0x1800029c6  sub     rsp, 20h
0x1800029ca  mov     edx, 0FA0h; dwSpinCount
0x1800029cf  lea     rcx, stru_180021DA8; lpCriticalSection
0x1800029d6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800029dc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800029e3  call    cs:__imp_GetModuleHandleW
0x1800029e9  mov     rbx, rax
0x1800029ec  test    rax, rax
0x1800029ef  jnz     short loc_180002A06
0x1800029f1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800029f8  call    cs:__imp_GetModuleHandleW
0x1800029fe  mov     rbx, rax
0x180002a01  test    rax, rax
0x180002a04  jz      short loc_180002A85
0x180002a06  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180002a0d  mov     rcx, rbx; hModule
0x180002a10  call    cs:__imp_GetProcAddress
0x180002a16  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180002a1d  mov     rcx, rbx; hModule
0x180002a20  mov     rdi, rax
0x180002a23  call    cs:__imp_GetProcAddress
0x180002a29  test    rdi, rdi
0x180002a2c  jz      short loc_180002A43
0x180002a2e  test    rax, rax
0x180002a31  jz      short loc_180002A43
0x180002a33  mov     cs:qword_180021DD0, rdi
0x180002a3a  mov     cs:qword_180021DD8, rax
0x180002a41  jmp     short loc_180002A61
0x180002a43  xor     r9d, r9d; lpName
0x180002a46  xor     r8d, r8d; bInitialState
0x180002a49  xor     ecx, ecx; lpEventAttributes
0x180002a4b  lea     edx, [r9+1]; bManualReset
0x180002a4f  call    cs:__imp_CreateEventW
0x180002a55  mov     cs:hHandle, rax
0x180002a5c  test    rax, rax
0x180002a5f  jz      short loc_180002A85
0x180002a61  xor     ecx, ecx
0x180002a63  call    __scrt_initialize_onexit_tables
0x180002a68  test    al, al
0x180002a6a  jz      short loc_180002A85
0x180002a6c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180002a73  call    atexit
0x180002a78  mov     rbx, [rsp+28h+arg_0]
0x180002a7d  xor     eax, eax
0x180002a7f  add     rsp, 20h
0x180002a83  pop     rdi
0x180002a84  retn
0x180002a85  mov     ecx, 7
0x180002a8a  call    __scrt_fastfail
```
