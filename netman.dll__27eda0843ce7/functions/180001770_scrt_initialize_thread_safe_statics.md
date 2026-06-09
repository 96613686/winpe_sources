# __scrt_initialize_thread_safe_statics

- ea: `0x180001770`
- end: `0x180001840`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001770`
- `0x180001bdc`
- `0x180001dac`
- `0x180001ee4`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1800017ff`
- `KERNEL32!CreateEventW` at `0x1800017ff`
- `KERNEL32!GetModuleHandleW` at `0x180001793`
- `KERNEL32!GetModuleHandleW` at `0x1800017a8`
- `KERNEL32!GetModuleHandleW` at `0x180001793`
- `KERNEL32!GetModuleHandleW` at `0x1800017a8`
- `KERNEL32!GetProcAddress` at `0x1800017c0`
- `KERNEL32!GetProcAddress` at `0x1800017d3`
- `KERNEL32!GetProcAddress` at `0x1800017c0`
- `KERNEL32!GetProcAddress` at `0x1800017d3`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180001786`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180001786`

## string_xrefs

- `0x18000178c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800017a1`: `kernel32.dll`

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
    qword_180044BB0 = (__int64)ProcAddress;
    qword_180044BB8 = (__int64)v2;
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
0x180001770  mov     [rsp+arg_0], rbx
0x180001775  push    rdi
0x180001776  sub     rsp, 20h
0x18000177a  mov     edx, 0FA0h; dwSpinCount
0x18000177f  lea     rcx, CriticalSection; lpCriticalSection
0x180001786  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000178c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180001793  call    cs:__imp_GetModuleHandleW
0x180001799  mov     rbx, rax
0x18000179c  test    rax, rax
0x18000179f  jnz     short loc_1800017B6
0x1800017a1  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1800017a8  call    cs:__imp_GetModuleHandleW
0x1800017ae  mov     rbx, rax
0x1800017b1  test    rax, rax
0x1800017b4  jz      short loc_180001835
0x1800017b6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800017bd  mov     rcx, rbx; hModule
0x1800017c0  call    cs:__imp_GetProcAddress
0x1800017c6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800017cd  mov     rcx, rbx; hModule
0x1800017d0  mov     rdi, rax
0x1800017d3  call    cs:__imp_GetProcAddress
0x1800017d9  test    rdi, rdi
0x1800017dc  jz      short loc_1800017F3
0x1800017de  test    rax, rax
0x1800017e1  jz      short loc_1800017F3
0x1800017e3  mov     cs:qword_180044BB0, rdi
0x1800017ea  mov     cs:qword_180044BB8, rax
0x1800017f1  jmp     short loc_180001811
0x1800017f3  xor     r9d, r9d; lpName
0x1800017f6  xor     r8d, r8d; bInitialState
0x1800017f9  xor     ecx, ecx; lpEventAttributes
0x1800017fb  lea     edx, [r9+1]; bManualReset
0x1800017ff  call    cs:__imp_CreateEventW
0x180001805  mov     cs:hHandle, rax
0x18000180c  test    rax, rax
0x18000180f  jz      short loc_180001835
0x180001811  xor     ecx, ecx
0x180001813  call    __scrt_initialize_onexit_tables
0x180001818  test    al, al
0x18000181a  jz      short loc_180001835
0x18000181c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180001823  call    atexit
0x180001828  mov     rbx, [rsp+28h+arg_0]
0x18000182d  xor     eax, eax
0x18000182f  add     rsp, 20h
0x180001833  pop     rdi
0x180001834  retn
0x180001835  mov     ecx, 7
0x18000183a  call    __scrt_fastfail
```
