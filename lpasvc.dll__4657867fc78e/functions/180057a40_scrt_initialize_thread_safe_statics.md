# __scrt_initialize_thread_safe_statics

- ea: `0x180057a40`
- end: `0x180057b10`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000e240`
- `0x18000e410`
- `0x18000e960`
- `0x180057a40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180057a63`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180057a78`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180057a63`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180057a78`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180057a90`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180057aa3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180057a90`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180057aa3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180057acf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180057acf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180057a56`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180057a56`

## string_xrefs

- `0x180057a5c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180057a71`: `kernel32.dll`

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
    qword_1801738A8 = (__int64)ProcAddress;
    qword_1801738B0 = (__int64)v2;
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
0x180057a40  mov     [rsp+arg_0], rbx
0x180057a45  push    rdi
0x180057a46  sub     rsp, 20h
0x180057a4a  mov     edx, 0FA0h; dwSpinCount
0x180057a4f  lea     rcx, CriticalSection; lpCriticalSection
0x180057a56  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180057a5c  lea     rcx, aApiMsWinCoreSy_4; "api-ms-win-core-synch-l1-2-0.dll"
0x180057a63  call    cs:__imp_GetModuleHandleW
0x180057a69  mov     rbx, rax
0x180057a6c  test    rax, rax
0x180057a6f  jnz     short loc_180057A86
0x180057a71  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180057a78  call    cs:__imp_GetModuleHandleW
0x180057a7e  mov     rbx, rax
0x180057a81  test    rax, rax
0x180057a84  jz      short loc_180057B05
0x180057a86  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180057a8d  mov     rcx, rbx; hModule
0x180057a90  call    cs:__imp_GetProcAddress
0x180057a96  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180057a9d  mov     rcx, rbx; hModule
0x180057aa0  mov     rdi, rax
0x180057aa3  call    cs:__imp_GetProcAddress
0x180057aa9  test    rdi, rdi
0x180057aac  jz      short loc_180057AC3
0x180057aae  test    rax, rax
0x180057ab1  jz      short loc_180057AC3
0x180057ab3  mov     cs:qword_1801738A8, rdi
0x180057aba  mov     cs:qword_1801738B0, rax
0x180057ac1  jmp     short loc_180057AE1
0x180057ac3  xor     r9d, r9d; lpName
0x180057ac6  xor     r8d, r8d; bInitialState
0x180057ac9  xor     ecx, ecx; lpEventAttributes
0x180057acb  lea     edx, [r9+1]; bManualReset
0x180057acf  call    cs:__imp_CreateEventW
0x180057ad5  mov     cs:hHandle, rax
0x180057adc  test    rax, rax
0x180057adf  jz      short loc_180057B05
0x180057ae1  xor     ecx, ecx
0x180057ae3  call    __scrt_initialize_onexit_tables
0x180057ae8  test    al, al
0x180057aea  jz      short loc_180057B05
0x180057aec  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180057af3  call    atexit
0x180057af8  mov     rbx, [rsp+28h+arg_0]
0x180057afd  xor     eax, eax
0x180057aff  add     rsp, 20h
0x180057b03  pop     rdi
0x180057b04  retn
0x180057b05  mov     ecx, 7
0x180057b0a  call    __scrt_fastfail
```
