# __scrt_initialize_thread_safe_statics

- ea: `0x180054540`
- end: `0x180054610`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180054344`
- `0x180054514`
- `0x180054540`
- `0x180054980`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180054563`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180054578`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180054563`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180054578`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180054590`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800545a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180054590`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800545a3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180054556`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180054556`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800545cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800545cf`

## string_xrefs

- `0x18005455c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180054571`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180152FB8, 0xFA0u);
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
    qword_180152FE0 = (__int64)ProcAddress;
    qword_180152FE8 = (__int64)v2;
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
0x180054540  mov     [rsp+arg_0], rbx
0x180054545  push    rdi
0x180054546  sub     rsp, 20h
0x18005454a  mov     edx, 0FA0h; dwSpinCount
0x18005454f  lea     rcx, stru_180152FB8; lpCriticalSection
0x180054556  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18005455c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180054563  call    cs:__imp_GetModuleHandleW
0x180054569  mov     rbx, rax
0x18005456c  test    rax, rax
0x18005456f  jnz     short loc_180054586
0x180054571  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180054578  call    cs:__imp_GetModuleHandleW
0x18005457e  mov     rbx, rax
0x180054581  test    rax, rax
0x180054584  jz      short loc_180054605
0x180054586  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18005458d  mov     rcx, rbx; hModule
0x180054590  call    cs:__imp_GetProcAddress
0x180054596  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18005459d  mov     rcx, rbx; hModule
0x1800545a0  mov     rdi, rax
0x1800545a3  call    cs:__imp_GetProcAddress
0x1800545a9  test    rdi, rdi
0x1800545ac  jz      short loc_1800545C3
0x1800545ae  test    rax, rax
0x1800545b1  jz      short loc_1800545C3
0x1800545b3  mov     cs:qword_180152FE0, rdi
0x1800545ba  mov     cs:qword_180152FE8, rax
0x1800545c1  jmp     short loc_1800545E1
0x1800545c3  xor     r9d, r9d; lpName
0x1800545c6  xor     r8d, r8d; bInitialState
0x1800545c9  xor     ecx, ecx; lpEventAttributes
0x1800545cb  lea     edx, [r9+1]; bManualReset
0x1800545cf  call    cs:__imp_CreateEventW
0x1800545d5  mov     cs:hHandle, rax
0x1800545dc  test    rax, rax
0x1800545df  jz      short loc_180054605
0x1800545e1  xor     ecx, ecx
0x1800545e3  call    __scrt_initialize_onexit_tables
0x1800545e8  test    al, al
0x1800545ea  jz      short loc_180054605
0x1800545ec  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800545f3  call    atexit
0x1800545f8  mov     rbx, [rsp+28h+arg_0]
0x1800545fd  xor     eax, eax
0x1800545ff  add     rsp, 20h
0x180054603  pop     rdi
0x180054604  retn
0x180054605  mov     ecx, 7
0x18005460a  call    __scrt_fastfail
```
