# __scrt_initialize_thread_safe_statics

- ea: `0x140001b90`
- end: `0x140001c60`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140001b90`
- `0x140001edc`
- `0x1400020ac`
- `0x1400021f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140001c1f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140001c1f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140001ba6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140001ba6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140001be0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140001bf3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140001be0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140001bf3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140001bb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140001bc8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140001bb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140001bc8`

## string_xrefs

- `0x140001bac`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x140001bc1`: `kernel32.dll`

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
    qword_140045EC8 = (__int64)ProcAddress;
    qword_140045ED0 = (__int64)v2;
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
0x140001b90  mov     [rsp+arg_0], rbx
0x140001b95  push    rdi
0x140001b96  sub     rsp, 20h
0x140001b9a  mov     edx, 0FA0h; dwSpinCount
0x140001b9f  lea     rcx, CriticalSection; lpCriticalSection
0x140001ba6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x140001bac  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x140001bb3  call    cs:__imp_GetModuleHandleW
0x140001bb9  mov     rbx, rax
0x140001bbc  test    rax, rax
0x140001bbf  jnz     short loc_140001BD6
0x140001bc1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x140001bc8  call    cs:__imp_GetModuleHandleW
0x140001bce  mov     rbx, rax
0x140001bd1  test    rax, rax
0x140001bd4  jz      short loc_140001C55
0x140001bd6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x140001bdd  mov     rcx, rbx; hModule
0x140001be0  call    cs:__imp_GetProcAddress
0x140001be6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x140001bed  mov     rcx, rbx; hModule
0x140001bf0  mov     rdi, rax
0x140001bf3  call    cs:__imp_GetProcAddress
0x140001bf9  test    rdi, rdi
0x140001bfc  jz      short loc_140001C13
0x140001bfe  test    rax, rax
0x140001c01  jz      short loc_140001C13
0x140001c03  mov     cs:qword_140045EC8, rdi
0x140001c0a  mov     cs:qword_140045ED0, rax
0x140001c11  jmp     short loc_140001C31
0x140001c13  xor     r9d, r9d; lpName
0x140001c16  xor     r8d, r8d; bInitialState
0x140001c19  xor     ecx, ecx; lpEventAttributes
0x140001c1b  lea     edx, [r9+1]; bManualReset
0x140001c1f  call    cs:__imp_CreateEventW
0x140001c25  mov     cs:hHandle, rax
0x140001c2c  test    rax, rax
0x140001c2f  jz      short loc_140001C55
0x140001c31  xor     ecx, ecx
0x140001c33  call    __scrt_initialize_onexit_tables
0x140001c38  test    al, al
0x140001c3a  jz      short loc_140001C55
0x140001c3c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x140001c43  call    atexit
0x140001c48  mov     rbx, [rsp+28h+arg_0]
0x140001c4d  xor     eax, eax
0x140001c4f  add     rsp, 20h
0x140001c53  pop     rdi
0x140001c54  retn
0x140001c55  mov     ecx, 7
0x140001c5a  call    __scrt_fastfail
```
