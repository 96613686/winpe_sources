# __scrt_initialize_thread_safe_statics

- ea: `0x180003880`
- end: `0x180003950`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002984`
- `0x180002b54`
- `0x180002ce8`
- `0x180003880`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800038a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800038b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800038a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800038b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800038d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800038e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800038d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800038e3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000390f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000390f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003896`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003896`

## string_xrefs

- `0x18000389c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800038b1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_18005F938, 0xFA0u);
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
    qword_18005F960 = (__int64)ProcAddress;
    qword_18005F968 = (__int64)v2;
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
0x180003880  mov     [rsp+arg_0], rbx
0x180003885  push    rdi
0x180003886  sub     rsp, 20h
0x18000388a  mov     edx, 0FA0h; dwSpinCount
0x18000388f  lea     rcx, stru_18005F938; lpCriticalSection
0x180003896  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000389c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800038a3  call    cs:__imp_GetModuleHandleW
0x1800038a9  mov     rbx, rax
0x1800038ac  test    rax, rax
0x1800038af  jnz     short loc_1800038C6
0x1800038b1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800038b8  call    cs:__imp_GetModuleHandleW
0x1800038be  mov     rbx, rax
0x1800038c1  test    rax, rax
0x1800038c4  jz      short loc_180003945
0x1800038c6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800038cd  mov     rcx, rbx; hModule
0x1800038d0  call    cs:__imp_GetProcAddress
0x1800038d6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800038dd  mov     rcx, rbx; hModule
0x1800038e0  mov     rdi, rax
0x1800038e3  call    cs:__imp_GetProcAddress
0x1800038e9  test    rdi, rdi
0x1800038ec  jz      short loc_180003903
0x1800038ee  test    rax, rax
0x1800038f1  jz      short loc_180003903
0x1800038f3  mov     cs:qword_18005F960, rdi
0x1800038fa  mov     cs:qword_18005F968, rax
0x180003901  jmp     short loc_180003921
0x180003903  xor     r9d, r9d; lpName
0x180003906  xor     r8d, r8d; bInitialState
0x180003909  xor     ecx, ecx; lpEventAttributes
0x18000390b  lea     edx, [r9+1]; bManualReset
0x18000390f  call    cs:__imp_CreateEventW
0x180003915  mov     cs:hHandle, rax
0x18000391c  test    rax, rax
0x18000391f  jz      short loc_180003945
0x180003921  xor     ecx, ecx
0x180003923  call    __scrt_initialize_onexit_tables
0x180003928  test    al, al
0x18000392a  jz      short loc_180003945
0x18000392c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180003933  call    atexit
0x180003938  mov     rbx, [rsp+28h+arg_0]
0x18000393d  xor     eax, eax
0x18000393f  add     rsp, 20h
0x180003943  pop     rdi
0x180003944  retn
0x180003945  mov     ecx, 7
0x18000394a  call    __scrt_fastfail
```
