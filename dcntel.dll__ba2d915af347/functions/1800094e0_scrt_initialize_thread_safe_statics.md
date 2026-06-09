# __scrt_initialize_thread_safe_statics

- ea: `0x1800094e0`
- end: `0x1800095b0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180009070`
- `0x180009240`
- `0x1800094e0`
- `0x180009c30`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009530`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009543`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009530`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009543`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009503`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009518`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009503`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009518`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800094f6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800094f6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000956f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000956f`

## string_xrefs

- `0x1800094fc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180009511`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1801FEFF0, 0xFA0u);
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
    qword_1801FF018 = (__int64)ProcAddress;
    qword_1801FF020 = (__int64)v2;
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
0x1800094e0  mov     [rsp+arg_0], rbx
0x1800094e5  push    rdi
0x1800094e6  sub     rsp, 20h
0x1800094ea  mov     edx, 0FA0h; dwSpinCount
0x1800094ef  lea     rcx, stru_1801FEFF0; lpCriticalSection
0x1800094f6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800094fc  lea     rcx, aApiMsWinCoreSy_5; "api-ms-win-core-synch-l1-2-0.dll"
0x180009503  call    cs:__imp_GetModuleHandleW
0x180009509  mov     rbx, rax
0x18000950c  test    rax, rax
0x18000950f  jnz     short loc_180009526
0x180009511  lea     rcx, SourceString; "kernel32.dll"
0x180009518  call    cs:__imp_GetModuleHandleW
0x18000951e  mov     rbx, rax
0x180009521  test    rax, rax
0x180009524  jz      short loc_1800095A5
0x180009526  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18000952d  mov     rcx, rbx; hModule
0x180009530  call    cs:__imp_GetProcAddress
0x180009536  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000953d  mov     rcx, rbx; hModule
0x180009540  mov     rdi, rax
0x180009543  call    cs:__imp_GetProcAddress
0x180009549  test    rdi, rdi
0x18000954c  jz      short loc_180009563
0x18000954e  test    rax, rax
0x180009551  jz      short loc_180009563
0x180009553  mov     cs:qword_1801FF018, rdi
0x18000955a  mov     cs:qword_1801FF020, rax
0x180009561  jmp     short loc_180009581
0x180009563  xor     r9d, r9d; lpName
0x180009566  xor     r8d, r8d; bInitialState
0x180009569  xor     ecx, ecx; lpEventAttributes
0x18000956b  lea     edx, [r9+1]; bManualReset
0x18000956f  call    cs:__imp_CreateEventW
0x180009575  mov     cs:hHandle, rax
0x18000957c  test    rax, rax
0x18000957f  jz      short loc_1800095A5
0x180009581  xor     ecx, ecx
0x180009583  call    __scrt_initialize_onexit_tables
0x180009588  test    al, al
0x18000958a  jz      short loc_1800095A5
0x18000958c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180009593  call    atexit
0x180009598  mov     rbx, [rsp+28h+arg_0]
0x18000959d  xor     eax, eax
0x18000959f  add     rsp, 20h
0x1800095a3  pop     rdi
0x1800095a4  retn
0x1800095a5  mov     ecx, 7
0x1800095aa  call    __scrt_fastfail
```
