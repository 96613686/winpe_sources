# __scrt_initialize_thread_safe_statics

- ea: `0x18000d270`
- end: `0x18000d340`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180003130`
- `0x180003300`
- `0x18000399c`
- `0x18000d270`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d293`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d2a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d293`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d2a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d2c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d2d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d2c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d2d3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000d286`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000d286`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d2ff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d2ff`

## string_xrefs

- `0x18000d28c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18000d2a1`: `kernel32.dll`

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
    qword_180123BB8 = (__int64)ProcAddress;
    qword_180123BC0 = (__int64)v2;
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
0x18000d270  mov     [rsp+arg_0], rbx
0x18000d275  push    rdi
0x18000d276  sub     rsp, 20h
0x18000d27a  mov     edx, 0FA0h; dwSpinCount
0x18000d27f  lea     rcx, CriticalSection; lpCriticalSection
0x18000d286  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000d28c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x18000d293  call    cs:__imp_GetModuleHandleW
0x18000d299  mov     rbx, rax
0x18000d29c  test    rax, rax
0x18000d29f  jnz     short loc_18000D2B6
0x18000d2a1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18000d2a8  call    cs:__imp_GetModuleHandleW
0x18000d2ae  mov     rbx, rax
0x18000d2b1  test    rax, rax
0x18000d2b4  jz      short loc_18000D335
0x18000d2b6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000d2bd  mov     rcx, rbx; hModule
0x18000d2c0  call    cs:__imp_GetProcAddress
0x18000d2c6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000d2cd  mov     rcx, rbx; hModule
0x18000d2d0  mov     rdi, rax
0x18000d2d3  call    cs:__imp_GetProcAddress
0x18000d2d9  test    rdi, rdi
0x18000d2dc  jz      short loc_18000D2F3
0x18000d2de  test    rax, rax
0x18000d2e1  jz      short loc_18000D2F3
0x18000d2e3  mov     cs:qword_180123BB8, rdi
0x18000d2ea  mov     cs:qword_180123BC0, rax
0x18000d2f1  jmp     short loc_18000D311
0x18000d2f3  xor     r9d, r9d; lpName
0x18000d2f6  xor     r8d, r8d; bInitialState
0x18000d2f9  xor     ecx, ecx; lpEventAttributes
0x18000d2fb  lea     edx, [r9+1]; bManualReset
0x18000d2ff  call    cs:__imp_CreateEventW
0x18000d305  mov     cs:hHandle, rax
0x18000d30c  test    rax, rax
0x18000d30f  jz      short loc_18000D335
0x18000d311  xor     ecx, ecx
0x18000d313  call    __scrt_initialize_onexit_tables
0x18000d318  test    al, al
0x18000d31a  jz      short loc_18000D335
0x18000d31c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18000d323  call    atexit
0x18000d328  mov     rbx, [rsp+28h+arg_0]
0x18000d32d  xor     eax, eax
0x18000d32f  add     rsp, 20h
0x18000d333  pop     rdi
0x18000d334  retn
0x18000d335  mov     ecx, 7
0x18000d33a  call    __scrt_fastfail
```
