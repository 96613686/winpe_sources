# __scrt_initialize_thread_safe_statics

- ea: `0x1801211f0`
- end: `0x1801212c0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18012074c`
- `0x18012091c`
- `0x18012094c`
- `0x1801211f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180121240`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180121253`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180121240`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180121253`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180121213`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180121228`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180121213`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180121228`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18012127f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18012127f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180121206`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180121206`

## string_xrefs

- `0x18012120c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180121221`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1801FBC20, 0xFA0u);
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
    qword_1801FBC48 = (__int64)ProcAddress;
    qword_1801FBC50 = (__int64)v2;
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
0x1801211f0  mov     [rsp+arg_0], rbx
0x1801211f5  push    rdi
0x1801211f6  sub     rsp, 20h
0x1801211fa  mov     edx, 0FA0h; dwSpinCount
0x1801211ff  lea     rcx, stru_1801FBC20; lpCriticalSection
0x180121206  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18012120c  lea     rcx, aApiMsWinCoreSy_4; "api-ms-win-core-synch-l1-2-0.dll"
0x180121213  call    cs:__imp_GetModuleHandleW
0x180121219  mov     rbx, rax
0x18012121c  test    rax, rax
0x18012121f  jnz     short loc_180121236
0x180121221  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180121228  call    cs:__imp_GetModuleHandleW
0x18012122e  mov     rbx, rax
0x180121231  test    rax, rax
0x180121234  jz      short loc_1801212B5
0x180121236  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18012123d  mov     rcx, rbx; hModule
0x180121240  call    cs:__imp_GetProcAddress
0x180121246  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18012124d  mov     rcx, rbx; hModule
0x180121250  mov     rdi, rax
0x180121253  call    cs:__imp_GetProcAddress
0x180121259  test    rdi, rdi
0x18012125c  jz      short loc_180121273
0x18012125e  test    rax, rax
0x180121261  jz      short loc_180121273
0x180121263  mov     cs:qword_1801FBC48, rdi
0x18012126a  mov     cs:qword_1801FBC50, rax
0x180121271  jmp     short loc_180121291
0x180121273  xor     r9d, r9d; lpName
0x180121276  xor     r8d, r8d; bInitialState
0x180121279  xor     ecx, ecx; lpEventAttributes
0x18012127b  lea     edx, [r9+1]; bManualReset
0x18012127f  call    cs:__imp_CreateEventW
0x180121285  mov     cs:hHandle, rax
0x18012128c  test    rax, rax
0x18012128f  jz      short loc_1801212B5
0x180121291  xor     ecx, ecx
0x180121293  call    __scrt_initialize_onexit_tables
0x180121298  test    al, al
0x18012129a  jz      short loc_1801212B5
0x18012129c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1801212a3  call    atexit
0x1801212a8  mov     rbx, [rsp+28h+arg_0]
0x1801212ad  xor     eax, eax
0x1801212af  add     rsp, 20h
0x1801212b3  pop     rdi
0x1801212b4  retn
0x1801212b5  mov     ecx, 7
0x1801212ba  call    __scrt_fastfail
```
