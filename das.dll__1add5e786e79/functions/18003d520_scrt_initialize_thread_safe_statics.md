# __scrt_initialize_thread_safe_statics

- ea: `0x18003d520`
- end: `0x18003d5f0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18003bf3c`
- `0x18003c10c`
- `0x18003c284`
- `0x18003d520`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003d570`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003d583`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003d570`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003d583`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003d543`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003d558`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003d543`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003d558`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003d536`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003d536`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003d5af`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003d5af`

## string_xrefs

- `0x18003d53c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18003d551`: `kernel32.dll`

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
    qword_1800A4310 = (__int64)ProcAddress;
    qword_1800A4318 = (__int64)v2;
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
0x18003d520  mov     [rsp+arg_0], rbx
0x18003d525  push    rdi
0x18003d526  sub     rsp, 20h
0x18003d52a  mov     edx, 0FA0h; dwSpinCount
0x18003d52f  lea     rcx, CriticalSection; lpCriticalSection
0x18003d536  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18003d53c  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x18003d543  call    cs:__imp_GetModuleHandleW
0x18003d549  mov     rbx, rax
0x18003d54c  test    rax, rax
0x18003d54f  jnz     short loc_18003D566
0x18003d551  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18003d558  call    cs:__imp_GetModuleHandleW
0x18003d55e  mov     rbx, rax
0x18003d561  test    rax, rax
0x18003d564  jz      short loc_18003D5E5
0x18003d566  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18003d56d  mov     rcx, rbx; hModule
0x18003d570  call    cs:__imp_GetProcAddress
0x18003d576  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18003d57d  mov     rcx, rbx; hModule
0x18003d580  mov     rdi, rax
0x18003d583  call    cs:__imp_GetProcAddress
0x18003d589  test    rdi, rdi
0x18003d58c  jz      short loc_18003D5A3
0x18003d58e  test    rax, rax
0x18003d591  jz      short loc_18003D5A3
0x18003d593  mov     cs:qword_1800A4310, rdi
0x18003d59a  mov     cs:qword_1800A4318, rax
0x18003d5a1  jmp     short loc_18003D5C1
0x18003d5a3  xor     r9d, r9d; lpName
0x18003d5a6  xor     r8d, r8d; bInitialState
0x18003d5a9  xor     ecx, ecx; lpEventAttributes
0x18003d5ab  lea     edx, [r9+1]; bManualReset
0x18003d5af  call    cs:__imp_CreateEventW
0x18003d5b5  mov     cs:hObject, rax
0x18003d5bc  test    rax, rax
0x18003d5bf  jz      short loc_18003D5E5
0x18003d5c1  xor     ecx, ecx
0x18003d5c3  call    __scrt_initialize_onexit_tables
0x18003d5c8  test    al, al
0x18003d5ca  jz      short loc_18003D5E5
0x18003d5cc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18003d5d3  call    atexit
0x18003d5d8  mov     rbx, [rsp+28h+arg_0]
0x18003d5dd  xor     eax, eax
0x18003d5df  add     rsp, 20h
0x18003d5e3  pop     rdi
0x18003d5e4  retn
0x18003d5e5  mov     ecx, 7
0x18003d5ea  call    __scrt_fastfail
```
