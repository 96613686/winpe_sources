# __scrt_initialize_thread_safe_statics

- ea: `0x18025c7a0`
- end: `0x18025c870`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18025b310`
- `0x18025b4e0`
- `0x18025b618`
- `0x18025c7a0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18025c7f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18025c803`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18025c7f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18025c803`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18025c7c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18025c7d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18025c7c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18025c7d8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18025c7b6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18025c7b6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18025c82f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18025c82f`

## string_xrefs

- `0x18025c7bc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18025c7d1`: `kernel32.dll`

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
    qword_1805DBBF8 = (__int64)ProcAddress;
    qword_1805DBC00 = (__int64)v2;
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
0x18025c7a0  mov     [rsp+arg_0], rbx
0x18025c7a5  push    rdi
0x18025c7a6  sub     rsp, 20h
0x18025c7aa  mov     edx, 0FA0h; dwSpinCount
0x18025c7af  lea     rcx, CriticalSection; lpCriticalSection
0x18025c7b6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18025c7bc  lea     rcx, aApiMsWinCoreSy_1; "api-ms-win-core-synch-l1-2-0.dll"
0x18025c7c3  call    cs:__imp_GetModuleHandleW
0x18025c7c9  mov     rbx, rax
0x18025c7cc  test    rax, rax
0x18025c7cf  jnz     short loc_18025C7E6
0x18025c7d1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18025c7d8  call    cs:__imp_GetModuleHandleW
0x18025c7de  mov     rbx, rax
0x18025c7e1  test    rax, rax
0x18025c7e4  jz      short loc_18025C865
0x18025c7e6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18025c7ed  mov     rcx, rbx; hModule
0x18025c7f0  call    cs:__imp_GetProcAddress
0x18025c7f6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18025c7fd  mov     rcx, rbx; hModule
0x18025c800  mov     rdi, rax
0x18025c803  call    cs:__imp_GetProcAddress
0x18025c809  test    rdi, rdi
0x18025c80c  jz      short loc_18025C823
0x18025c80e  test    rax, rax
0x18025c811  jz      short loc_18025C823
0x18025c813  mov     cs:qword_1805DBBF8, rdi
0x18025c81a  mov     cs:qword_1805DBC00, rax
0x18025c821  jmp     short loc_18025C841
0x18025c823  xor     r9d, r9d; lpName
0x18025c826  xor     r8d, r8d; bInitialState
0x18025c829  xor     ecx, ecx; lpEventAttributes
0x18025c82b  lea     edx, [r9+1]; bManualReset
0x18025c82f  call    cs:__imp_CreateEventW
0x18025c835  mov     cs:hObject, rax
0x18025c83c  test    rax, rax
0x18025c83f  jz      short loc_18025C865
0x18025c841  xor     ecx, ecx
0x18025c843  call    __scrt_initialize_onexit_tables
0x18025c848  test    al, al
0x18025c84a  jz      short loc_18025C865
0x18025c84c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18025c853  call    atexit
0x18025c858  mov     rbx, [rsp+28h+arg_0]
0x18025c85d  xor     eax, eax
0x18025c85f  add     rsp, 20h
0x18025c863  pop     rdi
0x18025c864  retn
0x18025c865  mov     ecx, 7
0x18025c86a  call    __scrt_fastfail
```
