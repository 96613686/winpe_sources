# __scrt_initialize_thread_safe_statics

- ea: `0x180107b70`
- end: `0x180107c40`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800f857c`
- `0x1800f874c`
- `0x1800f8f78`
- `0x180107b70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180107bff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180107bff`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180107b86`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180107b86`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180107bc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180107bd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180107bc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180107bd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180107b93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180107ba8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180107b93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180107ba8`

## string_xrefs

- `0x180107b8c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180107ba1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1801950F8, 0xFA0u);
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
    qword_180195120 = (__int64)ProcAddress;
    qword_180195128 = (__int64)v2;
    goto LABEL_7;
  }
  hHandle = CreateEventW(0, 1, 0, 0);
  if ( !hHandle )
  {
LABEL_9:
    _scrt_fastfail(7);
    JUMPOUT(0x180107C3FLL);
  }
LABEL_7:
  if ( !(unsigned __int8)_scrt_initialize_onexit_tables(0) )
    goto LABEL_9;
  atexit(_scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x180107b70  mov     [rsp+arg_0], rbx
0x180107b75  push    rdi
0x180107b76  sub     rsp, 20h
0x180107b7a  mov     edx, 0FA0h; dwSpinCount
0x180107b7f  lea     rcx, stru_1801950F8; lpCriticalSection
0x180107b86  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180107b8c  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x180107b93  call    cs:__imp_GetModuleHandleW
0x180107b99  mov     rbx, rax
0x180107b9c  test    rax, rax
0x180107b9f  jnz     short loc_180107BB6
0x180107ba1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180107ba8  call    cs:__imp_GetModuleHandleW
0x180107bae  mov     rbx, rax
0x180107bb1  test    rax, rax
0x180107bb4  jz      short loc_180107C35
0x180107bb6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x180107bbd  mov     rcx, rbx; hModule
0x180107bc0  call    cs:__imp_GetProcAddress
0x180107bc6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180107bcd  mov     rcx, rbx; hModule
0x180107bd0  mov     rdi, rax
0x180107bd3  call    cs:__imp_GetProcAddress
0x180107bd9  test    rdi, rdi
0x180107bdc  jz      short loc_180107BF3
0x180107bde  test    rax, rax
0x180107be1  jz      short loc_180107BF3
0x180107be3  mov     cs:qword_180195120, rdi
0x180107bea  mov     cs:qword_180195128, rax
0x180107bf1  jmp     short loc_180107C11
0x180107bf3  xor     r9d, r9d; lpName
0x180107bf6  xor     r8d, r8d; bInitialState
0x180107bf9  xor     ecx, ecx; lpEventAttributes
0x180107bfb  lea     edx, [r9+1]; bManualReset
0x180107bff  call    cs:__imp_CreateEventW
0x180107c05  mov     cs:hHandle, rax
0x180107c0c  test    rax, rax
0x180107c0f  jz      short loc_180107C35
0x180107c11  xor     ecx, ecx
0x180107c13  call    __scrt_initialize_onexit_tables
0x180107c18  test    al, al
0x180107c1a  jz      short loc_180107C35
0x180107c1c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180107c23  call    atexit
0x180107c28  mov     rbx, [rsp+28h+arg_0]
0x180107c2d  xor     eax, eax
0x180107c2f  add     rsp, 20h
0x180107c33  pop     rdi
0x180107c34  retn
0x180107c35  mov     ecx, 7
0x180107c3a  call    __scrt_fastfail
```
