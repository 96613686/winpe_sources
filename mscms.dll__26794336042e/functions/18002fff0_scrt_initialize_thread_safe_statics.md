# __scrt_initialize_thread_safe_statics

- ea: `0x18002fff0`
- end: `0x1800300c0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18002e870`
- `0x18002ea40`
- `0x18002efc4`
- `0x18002fff0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030040`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030053`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030040`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030053`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180030013`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180030028`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180030013`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180030028`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180030006`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180030006`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003007f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003007f`

## string_xrefs

- `0x18003000c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180030021`: `kernel32.dll`

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
    qword_18009F128 = (__int64)ProcAddress;
    qword_18009F130 = (__int64)v2;
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
0x18002fff0  mov     [rsp+arg_0], rbx
0x18002fff5  push    rdi
0x18002fff6  sub     rsp, 20h
0x18002fffa  mov     edx, 0FA0h; dwSpinCount
0x18002ffff  lea     rcx, CriticalSection; lpCriticalSection
0x180030006  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18003000c  lea     rcx, aApiMsWinCoreSy_2; "api-ms-win-core-synch-l1-2-0.dll"
0x180030013  call    cs:__imp_GetModuleHandleW
0x180030019  mov     rbx, rax
0x18003001c  test    rax, rax
0x18003001f  jnz     short loc_180030036
0x180030021  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180030028  call    cs:__imp_GetModuleHandleW
0x18003002e  mov     rbx, rax
0x180030031  test    rax, rax
0x180030034  jz      short loc_1800300B5
0x180030036  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18003003d  mov     rcx, rbx; hModule
0x180030040  call    cs:__imp_GetProcAddress
0x180030046  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18003004d  mov     rcx, rbx; hModule
0x180030050  mov     rdi, rax
0x180030053  call    cs:__imp_GetProcAddress
0x180030059  test    rdi, rdi
0x18003005c  jz      short loc_180030073
0x18003005e  test    rax, rax
0x180030061  jz      short loc_180030073
0x180030063  mov     cs:qword_18009F128, rdi
0x18003006a  mov     cs:qword_18009F130, rax
0x180030071  jmp     short loc_180030091
0x180030073  xor     r9d, r9d; lpName
0x180030076  xor     r8d, r8d; bInitialState
0x180030079  xor     ecx, ecx; lpEventAttributes
0x18003007b  lea     edx, [r9+1]; bManualReset
0x18003007f  call    cs:__imp_CreateEventW
0x180030085  mov     cs:hObject, rax
0x18003008c  test    rax, rax
0x18003008f  jz      short loc_1800300B5
0x180030091  xor     ecx, ecx
0x180030093  call    __scrt_initialize_onexit_tables
0x180030098  test    al, al
0x18003009a  jz      short loc_1800300B5
0x18003009c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800300a3  call    atexit
0x1800300a8  mov     rbx, [rsp+28h+arg_0]
0x1800300ad  xor     eax, eax
0x1800300af  add     rsp, 20h
0x1800300b3  pop     rdi
0x1800300b4  retn
0x1800300b5  mov     ecx, 7
0x1800300ba  call    __scrt_fastfail
```
