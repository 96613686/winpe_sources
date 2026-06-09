# __scrt_initialize_thread_safe_statics

- ea: `0x1800764f0`
- end: `0x1800765c0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180076250`
- `0x180076420`
- `0x1800764f0`
- `0x180076c90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180076540`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180076553`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180076540`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180076553`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180076513`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180076528`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180076513`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180076528`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007657f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007657f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180076506`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180076506`

## string_xrefs

- `0x18007650c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180076521`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180108D68, 0xFA0u);
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
    qword_180108D90 = (__int64)ProcAddress;
    qword_180108D98 = (__int64)v2;
  }
  else
  {
    hEvent = CreateEventW(0, 1, 0, 0);
    if ( !hEvent )
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
0x1800764f0  mov     [rsp+arg_0], rbx
0x1800764f5  push    rdi
0x1800764f6  sub     rsp, 20h
0x1800764fa  mov     edx, 0FA0h; dwSpinCount
0x1800764ff  lea     rcx, stru_180108D68; lpCriticalSection
0x180076506  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18007650c  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x180076513  call    cs:__imp_GetModuleHandleW
0x180076519  mov     rbx, rax
0x18007651c  test    rax, rax
0x18007651f  jnz     short loc_180076536
0x180076521  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180076528  call    cs:__imp_GetModuleHandleW
0x18007652e  mov     rbx, rax
0x180076531  test    rax, rax
0x180076534  jz      short loc_1800765B5
0x180076536  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18007653d  mov     rcx, rbx; hModule
0x180076540  call    cs:__imp_GetProcAddress
0x180076546  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18007654d  mov     rcx, rbx; hModule
0x180076550  mov     rdi, rax
0x180076553  call    cs:__imp_GetProcAddress
0x180076559  test    rdi, rdi
0x18007655c  jz      short loc_180076573
0x18007655e  test    rax, rax
0x180076561  jz      short loc_180076573
0x180076563  mov     cs:qword_180108D90, rdi
0x18007656a  mov     cs:qword_180108D98, rax
0x180076571  jmp     short loc_180076591
0x180076573  xor     r9d, r9d; lpName
0x180076576  xor     r8d, r8d; bInitialState
0x180076579  xor     ecx, ecx; lpEventAttributes
0x18007657b  lea     edx, [r9+1]; bManualReset
0x18007657f  call    cs:__imp_CreateEventW
0x180076585  mov     cs:hEvent, rax
0x18007658c  test    rax, rax
0x18007658f  jz      short loc_1800765B5
0x180076591  xor     ecx, ecx
0x180076593  call    __scrt_initialize_onexit_tables
0x180076598  test    al, al
0x18007659a  jz      short loc_1800765B5
0x18007659c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800765a3  call    atexit
0x1800765a8  mov     rbx, [rsp+28h+arg_0]
0x1800765ad  xor     eax, eax
0x1800765af  add     rsp, 20h
0x1800765b3  pop     rdi
0x1800765b4  retn
0x1800765b5  mov     ecx, 7
0x1800765ba  call    __scrt_fastfail
```
