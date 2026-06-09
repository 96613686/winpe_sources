# __scrt_initialize_thread_safe_statics

- ea: `0x1800a6060`
- end: `0x1800a6130`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800a3638`
- `0x1800a3808`
- `0x1800a3940`
- `0x1800a6060`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a60b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a60c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a60b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a60c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a6083`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a6098`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a6083`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a6098`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800a6076`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800a6076`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a60ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a60ef`

## string_xrefs

- `0x1800a607c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800a6091`: `kernel32.dll`

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
    qword_180145348 = (__int64)ProcAddress;
    qword_180145350 = (__int64)v2;
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
0x1800a6060  mov     [rsp+arg_0], rbx
0x1800a6065  push    rdi
0x1800a6066  sub     rsp, 20h
0x1800a606a  mov     edx, 0FA0h; dwSpinCount
0x1800a606f  lea     rcx, CriticalSection; lpCriticalSection
0x1800a6076  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800a607c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800a6083  call    cs:__imp_GetModuleHandleW
0x1800a6089  mov     rbx, rax
0x1800a608c  test    rax, rax
0x1800a608f  jnz     short loc_1800A60A6
0x1800a6091  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800a6098  call    cs:__imp_GetModuleHandleW
0x1800a609e  mov     rbx, rax
0x1800a60a1  test    rax, rax
0x1800a60a4  jz      short loc_1800A6125
0x1800a60a6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x1800a60ad  mov     rcx, rbx; hModule
0x1800a60b0  call    cs:__imp_GetProcAddress
0x1800a60b6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800a60bd  mov     rcx, rbx; hModule
0x1800a60c0  mov     rdi, rax
0x1800a60c3  call    cs:__imp_GetProcAddress
0x1800a60c9  test    rdi, rdi
0x1800a60cc  jz      short loc_1800A60E3
0x1800a60ce  test    rax, rax
0x1800a60d1  jz      short loc_1800A60E3
0x1800a60d3  mov     cs:qword_180145348, rdi
0x1800a60da  mov     cs:qword_180145350, rax
0x1800a60e1  jmp     short loc_1800A6101
0x1800a60e3  xor     r9d, r9d; lpName
0x1800a60e6  xor     r8d, r8d; bInitialState
0x1800a60e9  xor     ecx, ecx; lpEventAttributes
0x1800a60eb  lea     edx, [r9+1]; bManualReset
0x1800a60ef  call    cs:__imp_CreateEventW
0x1800a60f5  mov     cs:hHandle, rax
0x1800a60fc  test    rax, rax
0x1800a60ff  jz      short loc_1800A6125
0x1800a6101  xor     ecx, ecx
0x1800a6103  call    __scrt_initialize_onexit_tables
0x1800a6108  test    al, al
0x1800a610a  jz      short loc_1800A6125
0x1800a610c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800a6113  call    atexit
0x1800a6118  mov     rbx, [rsp+28h+arg_0]
0x1800a611d  xor     eax, eax
0x1800a611f  add     rsp, 20h
0x1800a6123  pop     rdi
0x1800a6124  retn
0x1800a6125  mov     ecx, 7
0x1800a612a  call    __scrt_fastfail
```
