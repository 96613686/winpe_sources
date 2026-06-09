# __scrt_initialize_thread_safe_statics

- ea: `0x18002bac0`
- end: `0x18002bb90`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18002b894`
- `0x18002ba64`
- `0x18002bac0`
- `0x18002c2b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002bae3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002baf8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002bae3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002baf8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002bb10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002bb23`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002bb10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002bb23`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18002bad6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18002bad6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002bb4f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002bb4f`

## string_xrefs

- `0x18002badc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18002baf1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800B6910, 0xFA0u);
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
    qword_1800B6938 = (__int64)ProcAddress;
    qword_1800B6940 = (__int64)v2;
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
0x18002bac0  mov     [rsp+arg_0], rbx
0x18002bac5  push    rdi
0x18002bac6  sub     rsp, 20h
0x18002baca  mov     edx, 0FA0h; dwSpinCount
0x18002bacf  lea     rcx, stru_1800B6910; lpCriticalSection
0x18002bad6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18002badc  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x18002bae3  call    cs:__imp_GetModuleHandleW
0x18002bae9  mov     rbx, rax
0x18002baec  test    rax, rax
0x18002baef  jnz     short loc_18002BB06
0x18002baf1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18002baf8  call    cs:__imp_GetModuleHandleW
0x18002bafe  mov     rbx, rax
0x18002bb01  test    rax, rax
0x18002bb04  jz      short loc_18002BB85
0x18002bb06  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18002bb0d  mov     rcx, rbx; hModule
0x18002bb10  call    cs:__imp_GetProcAddress
0x18002bb16  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18002bb1d  mov     rcx, rbx; hModule
0x18002bb20  mov     rdi, rax
0x18002bb23  call    cs:__imp_GetProcAddress
0x18002bb29  test    rdi, rdi
0x18002bb2c  jz      short loc_18002BB43
0x18002bb2e  test    rax, rax
0x18002bb31  jz      short loc_18002BB43
0x18002bb33  mov     cs:qword_1800B6938, rdi
0x18002bb3a  mov     cs:qword_1800B6940, rax
0x18002bb41  jmp     short loc_18002BB61
0x18002bb43  xor     r9d, r9d; lpName
0x18002bb46  xor     r8d, r8d; bInitialState
0x18002bb49  xor     ecx, ecx; lpEventAttributes
0x18002bb4b  lea     edx, [r9+1]; bManualReset
0x18002bb4f  call    cs:__imp_CreateEventW
0x18002bb55  mov     cs:hHandle, rax
0x18002bb5c  test    rax, rax
0x18002bb5f  jz      short loc_18002BB85
0x18002bb61  xor     ecx, ecx
0x18002bb63  call    __scrt_initialize_onexit_tables
0x18002bb68  test    al, al
0x18002bb6a  jz      short loc_18002BB85
0x18002bb6c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18002bb73  call    atexit
0x18002bb78  mov     rbx, [rsp+28h+arg_0]
0x18002bb7d  xor     eax, eax
0x18002bb7f  add     rsp, 20h
0x18002bb83  pop     rdi
0x18002bb84  retn
0x18002bb85  mov     ecx, 7
0x18002bb8a  call    __scrt_fastfail
```
