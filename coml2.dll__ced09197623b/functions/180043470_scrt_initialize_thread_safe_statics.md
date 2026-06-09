# __scrt_initialize_thread_safe_statics

- ea: `0x180043470`
- end: `0x180043540`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800429e0`
- `0x180042bb0`
- `0x180042cf4`
- `0x180043470`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180043493`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800434a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180043493`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800434a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800434c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800434d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800434c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800434d3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180043486`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180043486`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800434ff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800434ff`

## string_xrefs

- `0x18004348c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800434a1`: `kernel32.dll`

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
    qword_1800714A8 = (__int64)ProcAddress;
    qword_1800714B0 = (__int64)v2;
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
0x180043470  mov     [rsp+arg_0], rbx
0x180043475  push    rdi
0x180043476  sub     rsp, 20h
0x18004347a  mov     edx, 0FA0h; dwSpinCount
0x18004347f  lea     rcx, CriticalSection; lpCriticalSection
0x180043486  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18004348c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180043493  call    cs:__imp_GetModuleHandleW
0x180043499  mov     rbx, rax
0x18004349c  test    rax, rax
0x18004349f  jnz     short loc_1800434B6
0x1800434a1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800434a8  call    cs:__imp_GetModuleHandleW
0x1800434ae  mov     rbx, rax
0x1800434b1  test    rax, rax
0x1800434b4  jz      short loc_180043535
0x1800434b6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800434bd  mov     rcx, rbx; hModule
0x1800434c0  call    cs:__imp_GetProcAddress
0x1800434c6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800434cd  mov     rcx, rbx; hModule
0x1800434d0  mov     rdi, rax
0x1800434d3  call    cs:__imp_GetProcAddress
0x1800434d9  test    rdi, rdi
0x1800434dc  jz      short loc_1800434F3
0x1800434de  test    rax, rax
0x1800434e1  jz      short loc_1800434F3
0x1800434e3  mov     cs:qword_1800714A8, rdi
0x1800434ea  mov     cs:qword_1800714B0, rax
0x1800434f1  jmp     short loc_180043511
0x1800434f3  xor     r9d, r9d; lpName
0x1800434f6  xor     r8d, r8d; bInitialState
0x1800434f9  xor     ecx, ecx; lpEventAttributes
0x1800434fb  lea     edx, [r9+1]; bManualReset
0x1800434ff  call    cs:__imp_CreateEventW
0x180043505  mov     cs:hHandle, rax
0x18004350c  test    rax, rax
0x18004350f  jz      short loc_180043535
0x180043511  xor     ecx, ecx
0x180043513  call    __scrt_initialize_onexit_tables
0x180043518  test    al, al
0x18004351a  jz      short loc_180043535
0x18004351c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180043523  call    atexit
0x180043528  mov     rbx, [rsp+28h+arg_0]
0x18004352d  xor     eax, eax
0x18004352f  add     rsp, 20h
0x180043533  pop     rdi
0x180043534  retn
0x180043535  mov     ecx, 7
0x18004353a  call    __scrt_fastfail
```
