# __scrt_initialize_thread_safe_statics

- ea: `0x1800f0b10`
- end: `0x1800f0be0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800f0184`
- `0x1800f0354`
- `0x1800f0384`
- `0x1800f0b10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800f0b33`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800f0b48`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800f0b33`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800f0b48`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800f0b60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800f0b73`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800f0b60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800f0b73`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800f0b26`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800f0b26`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f0b9f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f0b9f`

## string_xrefs

- `0x1800f0b2c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800f0b41`: `kernel32.dll`

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
    qword_180243270 = (__int64)ProcAddress;
    qword_180243278 = (__int64)v2;
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
0x1800f0b10  mov     [rsp+arg_0], rbx
0x1800f0b15  push    rdi
0x1800f0b16  sub     rsp, 20h
0x1800f0b1a  mov     edx, 0FA0h; dwSpinCount
0x1800f0b1f  lea     rcx, CriticalSection; lpCriticalSection
0x1800f0b26  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800f0b2c  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x1800f0b33  call    cs:__imp_GetModuleHandleW
0x1800f0b39  mov     rbx, rax
0x1800f0b3c  test    rax, rax
0x1800f0b3f  jnz     short loc_1800F0B56
0x1800f0b41  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800f0b48  call    cs:__imp_GetModuleHandleW
0x1800f0b4e  mov     rbx, rax
0x1800f0b51  test    rax, rax
0x1800f0b54  jz      short loc_1800F0BD5
0x1800f0b56  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x1800f0b5d  mov     rcx, rbx; hModule
0x1800f0b60  call    cs:__imp_GetProcAddress
0x1800f0b66  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800f0b6d  mov     rcx, rbx; hModule
0x1800f0b70  mov     rdi, rax
0x1800f0b73  call    cs:__imp_GetProcAddress
0x1800f0b79  test    rdi, rdi
0x1800f0b7c  jz      short loc_1800F0B93
0x1800f0b7e  test    rax, rax
0x1800f0b81  jz      short loc_1800F0B93
0x1800f0b83  mov     cs:qword_180243270, rdi
0x1800f0b8a  mov     cs:qword_180243278, rax
0x1800f0b91  jmp     short loc_1800F0BB1
0x1800f0b93  xor     r9d, r9d; lpName
0x1800f0b96  xor     r8d, r8d; bInitialState
0x1800f0b99  xor     ecx, ecx; lpEventAttributes
0x1800f0b9b  lea     edx, [r9+1]; bManualReset
0x1800f0b9f  call    cs:__imp_CreateEventW
0x1800f0ba5  mov     cs:hHandle, rax
0x1800f0bac  test    rax, rax
0x1800f0baf  jz      short loc_1800F0BD5
0x1800f0bb1  xor     ecx, ecx
0x1800f0bb3  call    __scrt_initialize_onexit_tables
0x1800f0bb8  test    al, al
0x1800f0bba  jz      short loc_1800F0BD5
0x1800f0bbc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800f0bc3  call    atexit
0x1800f0bc8  mov     rbx, [rsp+28h+arg_0]
0x1800f0bcd  xor     eax, eax
0x1800f0bcf  add     rsp, 20h
0x1800f0bd3  pop     rdi
0x1800f0bd4  retn
0x1800f0bd5  mov     ecx, 7
0x1800f0bda  call    __scrt_fastfail
```
