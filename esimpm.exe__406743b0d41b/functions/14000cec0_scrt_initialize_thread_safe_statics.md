# __scrt_initialize_thread_safe_statics

- ea: `0x14000cec0`
- end: `0x14000cf90`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140003048`
- `0x140003218`
- `0x14000372c`
- `0x14000cec0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000cf10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000cf23`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000cf10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000cf23`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000cee3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000cef8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000cee3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000cef8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000cf4f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000cf4f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14000ced6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14000ced6`

## string_xrefs

- `0x14000cedc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x14000cef1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1400759B8, 0xFA0u);
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
    qword_1400759E0 = (__int64)ProcAddress;
    qword_1400759E8 = (__int64)v2;
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
0x14000cec0  mov     [rsp+arg_0], rbx
0x14000cec5  push    rdi
0x14000cec6  sub     rsp, 20h
0x14000ceca  mov     edx, 0FA0h; dwSpinCount
0x14000cecf  lea     rcx, stru_1400759B8; lpCriticalSection
0x14000ced6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14000cedc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x14000cee3  call    cs:__imp_GetModuleHandleW
0x14000cee9  mov     rbx, rax
0x14000ceec  test    rax, rax
0x14000ceef  jnz     short loc_14000CF06
0x14000cef1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x14000cef8  call    cs:__imp_GetModuleHandleW
0x14000cefe  mov     rbx, rax
0x14000cf01  test    rax, rax
0x14000cf04  jz      short loc_14000CF85
0x14000cf06  lea     rdx, ProcName; "SleepConditionVariableCS"
0x14000cf0d  mov     rcx, rbx; hModule
0x14000cf10  call    cs:__imp_GetProcAddress
0x14000cf16  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x14000cf1d  mov     rcx, rbx; hModule
0x14000cf20  mov     rdi, rax
0x14000cf23  call    cs:__imp_GetProcAddress
0x14000cf29  test    rdi, rdi
0x14000cf2c  jz      short loc_14000CF43
0x14000cf2e  test    rax, rax
0x14000cf31  jz      short loc_14000CF43
0x14000cf33  mov     cs:qword_1400759E0, rdi
0x14000cf3a  mov     cs:qword_1400759E8, rax
0x14000cf41  jmp     short loc_14000CF61
0x14000cf43  xor     r9d, r9d; lpName
0x14000cf46  xor     r8d, r8d; bInitialState
0x14000cf49  xor     ecx, ecx; lpEventAttributes
0x14000cf4b  lea     edx, [r9+1]; bManualReset
0x14000cf4f  call    cs:__imp_CreateEventW
0x14000cf55  mov     cs:hHandle, rax
0x14000cf5c  test    rax, rax
0x14000cf5f  jz      short loc_14000CF85
0x14000cf61  xor     ecx, ecx
0x14000cf63  call    __scrt_initialize_onexit_tables
0x14000cf68  test    al, al
0x14000cf6a  jz      short loc_14000CF85
0x14000cf6c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x14000cf73  call    atexit
0x14000cf78  mov     rbx, [rsp+28h+arg_0]
0x14000cf7d  xor     eax, eax
0x14000cf7f  add     rsp, 20h
0x14000cf83  pop     rdi
0x14000cf84  retn
0x14000cf85  mov     ecx, 7
0x14000cf8a  call    __scrt_fastfail
```
