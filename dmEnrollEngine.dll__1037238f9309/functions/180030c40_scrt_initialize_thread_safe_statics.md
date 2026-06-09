# __scrt_initialize_thread_safe_statics

- ea: `0x180030c40`
- end: `0x180030d10`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18002e380`
- `0x18002e550`
- `0x18002e774`
- `0x180030c40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030c90`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030ca3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030c90`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030ca3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180030c63`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180030c78`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180030c63`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180030c78`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180030c56`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180030c56`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180030ccf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180030ccf`

## string_xrefs

- `0x180030c5c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180030c71`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800B0168, 0xFA0u);
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
    qword_1800B0190 = (__int64)ProcAddress;
    qword_1800B0198 = (__int64)v2;
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
0x180030c40  mov     [rsp+arg_0], rbx
0x180030c45  push    rdi
0x180030c46  sub     rsp, 20h
0x180030c4a  mov     edx, 0FA0h; dwSpinCount
0x180030c4f  lea     rcx, stru_1800B0168; lpCriticalSection
0x180030c56  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180030c5c  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x180030c63  call    cs:__imp_GetModuleHandleW
0x180030c69  mov     rbx, rax
0x180030c6c  test    rax, rax
0x180030c6f  jnz     short loc_180030C86
0x180030c71  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180030c78  call    cs:__imp_GetModuleHandleW
0x180030c7e  mov     rbx, rax
0x180030c81  test    rax, rax
0x180030c84  jz      short loc_180030D05
0x180030c86  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x180030c8d  mov     rcx, rbx; hModule
0x180030c90  call    cs:__imp_GetProcAddress
0x180030c96  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180030c9d  mov     rcx, rbx; hModule
0x180030ca0  mov     rdi, rax
0x180030ca3  call    cs:__imp_GetProcAddress
0x180030ca9  test    rdi, rdi
0x180030cac  jz      short loc_180030CC3
0x180030cae  test    rax, rax
0x180030cb1  jz      short loc_180030CC3
0x180030cb3  mov     cs:qword_1800B0190, rdi
0x180030cba  mov     cs:qword_1800B0198, rax
0x180030cc1  jmp     short loc_180030CE1
0x180030cc3  xor     r9d, r9d; lpName
0x180030cc6  xor     r8d, r8d; bInitialState
0x180030cc9  xor     ecx, ecx; lpEventAttributes
0x180030ccb  lea     edx, [r9+1]; bManualReset
0x180030ccf  call    cs:__imp_CreateEventW
0x180030cd5  mov     cs:hHandle, rax
0x180030cdc  test    rax, rax
0x180030cdf  jz      short loc_180030D05
0x180030ce1  xor     ecx, ecx
0x180030ce3  call    __scrt_initialize_onexit_tables
0x180030ce8  test    al, al
0x180030cea  jz      short loc_180030D05
0x180030cec  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180030cf3  call    atexit
0x180030cf8  mov     rbx, [rsp+28h+arg_0]
0x180030cfd  xor     eax, eax
0x180030cff  add     rsp, 20h
0x180030d03  pop     rdi
0x180030d04  retn
0x180030d05  mov     ecx, 7
0x180030d0a  call    __scrt_fastfail
```
