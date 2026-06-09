# __scrt_initialize_thread_safe_statics

- ea: `0x180002af0`
- end: `0x180002bc0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800019b8`
- `0x180001b88`
- `0x180001d04`
- `0x180002af0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002b40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002b53`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002b40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002b53`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002b13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002b28`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002b13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002b28`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002b7f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002b7f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002b06`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002b06`

## string_xrefs

- `0x180002b0c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180002b21`: `kernel32.dll`

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
    qword_180020370 = (__int64)ProcAddress;
    qword_180020378 = (__int64)v2;
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
0x180002af0  mov     [rsp+arg_0], rbx
0x180002af5  push    rdi
0x180002af6  sub     rsp, 20h
0x180002afa  mov     edx, 0FA0h; dwSpinCount
0x180002aff  lea     rcx, CriticalSection; lpCriticalSection
0x180002b06  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180002b0c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180002b13  call    cs:__imp_GetModuleHandleW
0x180002b19  mov     rbx, rax
0x180002b1c  test    rax, rax
0x180002b1f  jnz     short loc_180002B36
0x180002b21  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180002b28  call    cs:__imp_GetModuleHandleW
0x180002b2e  mov     rbx, rax
0x180002b31  test    rax, rax
0x180002b34  jz      short loc_180002BB5
0x180002b36  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180002b3d  mov     rcx, rbx; hModule
0x180002b40  call    cs:__imp_GetProcAddress
0x180002b46  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180002b4d  mov     rcx, rbx; hModule
0x180002b50  mov     rdi, rax
0x180002b53  call    cs:__imp_GetProcAddress
0x180002b59  test    rdi, rdi
0x180002b5c  jz      short loc_180002B73
0x180002b5e  test    rax, rax
0x180002b61  jz      short loc_180002B73
0x180002b63  mov     cs:qword_180020370, rdi
0x180002b6a  mov     cs:qword_180020378, rax
0x180002b71  jmp     short loc_180002B91
0x180002b73  xor     r9d, r9d; lpName
0x180002b76  xor     r8d, r8d; bInitialState
0x180002b79  xor     ecx, ecx; lpEventAttributes
0x180002b7b  lea     edx, [r9+1]; bManualReset
0x180002b7f  call    cs:__imp_CreateEventW
0x180002b85  mov     cs:hHandle, rax
0x180002b8c  test    rax, rax
0x180002b8f  jz      short loc_180002BB5
0x180002b91  xor     ecx, ecx
0x180002b93  call    __scrt_initialize_onexit_tables
0x180002b98  test    al, al
0x180002b9a  jz      short loc_180002BB5
0x180002b9c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180002ba3  call    atexit
0x180002ba8  mov     rbx, [rsp+28h+arg_0]
0x180002bad  xor     eax, eax
0x180002baf  add     rsp, 20h
0x180002bb3  pop     rdi
0x180002bb4  retn
0x180002bb5  mov     ecx, 7
0x180002bba  call    __scrt_fastfail
```
