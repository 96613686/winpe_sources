# __scrt_initialize_thread_safe_statics

- ea: `0x18002e070`
- end: `0x18002e140`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18002de00`
- `0x18002dfd0`
- `0x18002e070`
- `0x18002e320`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002e0c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002e0d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002e0c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002e0d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002e093`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002e0a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002e093`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002e0a8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002e0ff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002e0ff`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18002e086`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18002e086`

## string_xrefs

- `0x18002e08c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18002e0a1`: `kernel32.dll`

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
    qword_18006EA80 = (__int64)ProcAddress;
    qword_18006EA88 = (__int64)v2;
  }
  else
  {
    hObject = CreateEventW(0, 1, 0, 0);
    if ( !hObject )
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
0x18002e070  mov     [rsp+arg_0], rbx
0x18002e075  push    rdi
0x18002e076  sub     rsp, 20h
0x18002e07a  mov     edx, 0FA0h; dwSpinCount
0x18002e07f  lea     rcx, CriticalSection; lpCriticalSection
0x18002e086  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18002e08c  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x18002e093  call    cs:__imp_GetModuleHandleW
0x18002e099  mov     rbx, rax
0x18002e09c  test    rax, rax
0x18002e09f  jnz     short loc_18002E0B6
0x18002e0a1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18002e0a8  call    cs:__imp_GetModuleHandleW
0x18002e0ae  mov     rbx, rax
0x18002e0b1  test    rax, rax
0x18002e0b4  jz      short loc_18002E135
0x18002e0b6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18002e0bd  mov     rcx, rbx; hModule
0x18002e0c0  call    cs:__imp_GetProcAddress
0x18002e0c6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18002e0cd  mov     rcx, rbx; hModule
0x18002e0d0  mov     rdi, rax
0x18002e0d3  call    cs:__imp_GetProcAddress
0x18002e0d9  test    rdi, rdi
0x18002e0dc  jz      short loc_18002E0F3
0x18002e0de  test    rax, rax
0x18002e0e1  jz      short loc_18002E0F3
0x18002e0e3  mov     cs:qword_18006EA80, rdi
0x18002e0ea  mov     cs:qword_18006EA88, rax
0x18002e0f1  jmp     short loc_18002E111
0x18002e0f3  xor     r9d, r9d; lpName
0x18002e0f6  xor     r8d, r8d; bInitialState
0x18002e0f9  xor     ecx, ecx; lpEventAttributes
0x18002e0fb  lea     edx, [r9+1]; bManualReset
0x18002e0ff  call    cs:__imp_CreateEventW
0x18002e105  mov     cs:hObject, rax
0x18002e10c  test    rax, rax
0x18002e10f  jz      short loc_18002E135
0x18002e111  xor     ecx, ecx
0x18002e113  call    __scrt_initialize_onexit_tables
0x18002e118  test    al, al
0x18002e11a  jz      short loc_18002E135
0x18002e11c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18002e123  call    atexit
0x18002e128  mov     rbx, [rsp+28h+arg_0]
0x18002e12d  xor     eax, eax
0x18002e12f  add     rsp, 20h
0x18002e133  pop     rdi
0x18002e134  retn
0x18002e135  mov     ecx, 7
0x18002e13a  call    __scrt_fastfail
```
