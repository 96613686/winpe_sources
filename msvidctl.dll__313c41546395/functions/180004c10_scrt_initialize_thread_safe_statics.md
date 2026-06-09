# __scrt_initialize_thread_safe_statics

- ea: `0x180004c10`
- end: `0x180004ce0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180004958`
- `0x180004b28`
- `0x180004c10`
- `0x180004fb8`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180004c9f`
- `KERNEL32!CreateEventW` at `0x180004c9f`
- `KERNEL32!GetProcAddress` at `0x180004c60`
- `KERNEL32!GetProcAddress` at `0x180004c73`
- `KERNEL32!GetProcAddress` at `0x180004c60`
- `KERNEL32!GetProcAddress` at `0x180004c73`
- `KERNEL32!GetModuleHandleW` at `0x180004c33`
- `KERNEL32!GetModuleHandleW` at `0x180004c48`
- `KERNEL32!GetModuleHandleW` at `0x180004c33`
- `KERNEL32!GetModuleHandleW` at `0x180004c48`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180004c26`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180004c26`

## string_xrefs

- `0x180004c2c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004c41`: `kernel32.dll`

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
    qword_18021CC30 = (__int64)ProcAddress;
    qword_18021CC38 = (__int64)v2;
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
0x180004c10  mov     [rsp+arg_0], rbx
0x180004c15  push    rdi
0x180004c16  sub     rsp, 20h
0x180004c1a  mov     edx, 0FA0h; dwSpinCount
0x180004c1f  lea     rcx, CriticalSection; lpCriticalSection
0x180004c26  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180004c2c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180004c33  call    cs:__imp_GetModuleHandleW
0x180004c39  mov     rbx, rax
0x180004c3c  test    rax, rax
0x180004c3f  jnz     short loc_180004C56
0x180004c41  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x180004c48  call    cs:__imp_GetModuleHandleW
0x180004c4e  mov     rbx, rax
0x180004c51  test    rax, rax
0x180004c54  jz      short loc_180004CD5
0x180004c56  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x180004c5d  mov     rcx, rbx; hModule
0x180004c60  call    cs:__imp_GetProcAddress
0x180004c66  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180004c6d  mov     rcx, rbx; hModule
0x180004c70  mov     rdi, rax
0x180004c73  call    cs:__imp_GetProcAddress
0x180004c79  test    rdi, rdi
0x180004c7c  jz      short loc_180004C93
0x180004c7e  test    rax, rax
0x180004c81  jz      short loc_180004C93
0x180004c83  mov     cs:qword_18021CC30, rdi
0x180004c8a  mov     cs:qword_18021CC38, rax
0x180004c91  jmp     short loc_180004CB1
0x180004c93  xor     r9d, r9d; lpName
0x180004c96  xor     r8d, r8d; bInitialState
0x180004c99  xor     ecx, ecx; lpEventAttributes
0x180004c9b  lea     edx, [r9+1]; bManualReset
0x180004c9f  call    cs:__imp_CreateEventW
0x180004ca5  mov     cs:hHandle, rax
0x180004cac  test    rax, rax
0x180004caf  jz      short loc_180004CD5
0x180004cb1  xor     ecx, ecx
0x180004cb3  call    __scrt_initialize_onexit_tables
0x180004cb8  test    al, al
0x180004cba  jz      short loc_180004CD5
0x180004cbc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180004cc3  call    atexit
0x180004cc8  mov     rbx, [rsp+28h+arg_0]
0x180004ccd  xor     eax, eax
0x180004ccf  add     rsp, 20h
0x180004cd3  pop     rdi
0x180004cd4  retn
0x180004cd5  mov     ecx, 7
0x180004cda  call    __scrt_fastfail
```
