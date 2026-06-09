# __scrt_initialize_thread_safe_statics

- ea: `0x180014360`
- end: `0x180014430`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180014360`
- `0x1800149b4`
- `0x180014b84`
- `0x180014bb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180014376`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180014376`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800143ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800143ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800143b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800143c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800143b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800143c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014383`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014398`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014383`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014398`

## string_xrefs

- `0x18001437c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180014391`: `kernel32.dll`

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
    qword_18003E9D0 = (__int64)ProcAddress;
    qword_18003E9D8 = (__int64)v2;
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
0x180014360  mov     [rsp+arg_0], rbx
0x180014365  push    rdi
0x180014366  sub     rsp, 20h
0x18001436a  mov     edx, 0FA0h; dwSpinCount
0x18001436f  lea     rcx, CriticalSection; lpCriticalSection
0x180014376  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18001437c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180014383  call    cs:__imp_GetModuleHandleW
0x180014389  mov     rbx, rax
0x18001438c  test    rax, rax
0x18001438f  jnz     short loc_1800143A6
0x180014391  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180014398  call    cs:__imp_GetModuleHandleW
0x18001439e  mov     rbx, rax
0x1800143a1  test    rax, rax
0x1800143a4  jz      short loc_180014425
0x1800143a6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800143ad  mov     rcx, rbx; hModule
0x1800143b0  call    cs:__imp_GetProcAddress
0x1800143b6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800143bd  mov     rcx, rbx; hModule
0x1800143c0  mov     rdi, rax
0x1800143c3  call    cs:__imp_GetProcAddress
0x1800143c9  test    rdi, rdi
0x1800143cc  jz      short loc_1800143E3
0x1800143ce  test    rax, rax
0x1800143d1  jz      short loc_1800143E3
0x1800143d3  mov     cs:qword_18003E9D0, rdi
0x1800143da  mov     cs:qword_18003E9D8, rax
0x1800143e1  jmp     short loc_180014401
0x1800143e3  xor     r9d, r9d; lpName
0x1800143e6  xor     r8d, r8d; bInitialState
0x1800143e9  xor     ecx, ecx; lpEventAttributes
0x1800143eb  lea     edx, [r9+1]; bManualReset
0x1800143ef  call    cs:__imp_CreateEventW
0x1800143f5  mov     cs:hHandle, rax
0x1800143fc  test    rax, rax
0x1800143ff  jz      short loc_180014425
0x180014401  xor     ecx, ecx
0x180014403  call    __scrt_initialize_onexit_tables
0x180014408  test    al, al
0x18001440a  jz      short loc_180014425
0x18001440c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180014413  call    atexit
0x180014418  mov     rbx, [rsp+28h+arg_0]
0x18001441d  xor     eax, eax
0x18001441f  add     rsp, 20h
0x180014423  pop     rdi
0x180014424  retn
0x180014425  mov     ecx, 7
0x18001442a  call    __scrt_fastfail
```
