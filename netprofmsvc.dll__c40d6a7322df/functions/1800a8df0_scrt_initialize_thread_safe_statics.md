# __scrt_initialize_thread_safe_statics

- ea: `0x1800a8df0`
- end: `0x1800a8ec0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800a8b74`
- `0x1800a8d44`
- `0x1800a8df0`
- `0x1800a91dc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a8e40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a8e53`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a8e40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a8e53`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a8e13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a8e28`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a8e13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a8e28`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a8e7f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a8e7f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800a8e06`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800a8e06`

## string_xrefs

- `0x1800a8e0c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800a8e21`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1801C7328, 0xFA0u);
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
    qword_1801C7350 = (__int64)ProcAddress;
    qword_1801C7358 = (__int64)v2;
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
0x1800a8df0  mov     [rsp+arg_0], rbx
0x1800a8df5  push    rdi
0x1800a8df6  sub     rsp, 20h
0x1800a8dfa  mov     edx, 0FA0h; dwSpinCount
0x1800a8dff  lea     rcx, stru_1801C7328; lpCriticalSection
0x1800a8e06  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800a8e0c  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x1800a8e13  call    cs:__imp_GetModuleHandleW
0x1800a8e19  mov     rbx, rax
0x1800a8e1c  test    rax, rax
0x1800a8e1f  jnz     short loc_1800A8E36
0x1800a8e21  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800a8e28  call    cs:__imp_GetModuleHandleW
0x1800a8e2e  mov     rbx, rax
0x1800a8e31  test    rax, rax
0x1800a8e34  jz      short loc_1800A8EB5
0x1800a8e36  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x1800a8e3d  mov     rcx, rbx; hModule
0x1800a8e40  call    cs:__imp_GetProcAddress
0x1800a8e46  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800a8e4d  mov     rcx, rbx; hModule
0x1800a8e50  mov     rdi, rax
0x1800a8e53  call    cs:__imp_GetProcAddress
0x1800a8e59  test    rdi, rdi
0x1800a8e5c  jz      short loc_1800A8E73
0x1800a8e5e  test    rax, rax
0x1800a8e61  jz      short loc_1800A8E73
0x1800a8e63  mov     cs:qword_1801C7350, rdi
0x1800a8e6a  mov     cs:qword_1801C7358, rax
0x1800a8e71  jmp     short loc_1800A8E91
0x1800a8e73  xor     r9d, r9d; lpName
0x1800a8e76  xor     r8d, r8d; bInitialState
0x1800a8e79  xor     ecx, ecx; lpEventAttributes
0x1800a8e7b  lea     edx, [r9+1]; bManualReset
0x1800a8e7f  call    cs:__imp_CreateEventW
0x1800a8e85  mov     cs:hHandle, rax
0x1800a8e8c  test    rax, rax
0x1800a8e8f  jz      short loc_1800A8EB5
0x1800a8e91  xor     ecx, ecx
0x1800a8e93  call    __scrt_initialize_onexit_tables
0x1800a8e98  test    al, al
0x1800a8e9a  jz      short loc_1800A8EB5
0x1800a8e9c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800a8ea3  call    atexit
0x1800a8ea8  mov     rbx, [rsp+28h+arg_0]
0x1800a8ead  xor     eax, eax
0x1800a8eaf  add     rsp, 20h
0x1800a8eb3  pop     rdi
0x1800a8eb4  retn
0x1800a8eb5  mov     ecx, 7
0x1800a8eba  call    __scrt_fastfail
```
