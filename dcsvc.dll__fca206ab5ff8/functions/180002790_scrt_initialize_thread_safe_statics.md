# __scrt_initialize_thread_safe_statics

- ea: `0x180002790`
- end: `0x180002860`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001f08`
- `0x1800020d8`
- `0x18000223c`
- `0x180002790`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800027e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800027f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800027e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800027f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800027b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800027c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800027b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800027c8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000281f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000281f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800027a6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800027a6`

## string_xrefs

- `0x1800027ac`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800027c1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_18001B688, 0xFA0u);
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
    qword_18001B6B0 = (__int64)ProcAddress;
    qword_18001B6B8 = (__int64)v2;
  }
  else
  {
    hHandle = CreateEventW(0, 1, 0, 0);
    if ( !hHandle )
      goto LABEL_9;
  }
  if ( !(unsigned __int8)_scrt_initialize_onexit_tables(0) )
LABEL_9:
    _scrt_fastfail(7u);
  atexit(_scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x180002790  mov     [rsp+arg_0], rbx
0x180002795  push    rdi
0x180002796  sub     rsp, 20h
0x18000279a  mov     edx, 0FA0h; dwSpinCount
0x18000279f  lea     rcx, stru_18001B688; lpCriticalSection
0x1800027a6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800027ac  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800027b3  call    cs:__imp_GetModuleHandleW
0x1800027b9  mov     rbx, rax
0x1800027bc  test    rax, rax
0x1800027bf  jnz     short loc_1800027D6
0x1800027c1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800027c8  call    cs:__imp_GetModuleHandleW
0x1800027ce  mov     rbx, rax
0x1800027d1  test    rax, rax
0x1800027d4  jz      short loc_180002855
0x1800027d6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800027dd  mov     rcx, rbx; hModule
0x1800027e0  call    cs:__imp_GetProcAddress
0x1800027e6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800027ed  mov     rcx, rbx; hModule
0x1800027f0  mov     rdi, rax
0x1800027f3  call    cs:__imp_GetProcAddress
0x1800027f9  test    rdi, rdi
0x1800027fc  jz      short loc_180002813
0x1800027fe  test    rax, rax
0x180002801  jz      short loc_180002813
0x180002803  mov     cs:qword_18001B6B0, rdi
0x18000280a  mov     cs:qword_18001B6B8, rax
0x180002811  jmp     short loc_180002831
0x180002813  xor     r9d, r9d; lpName
0x180002816  xor     r8d, r8d; bInitialState
0x180002819  xor     ecx, ecx; lpEventAttributes
0x18000281b  lea     edx, [r9+1]; bManualReset
0x18000281f  call    cs:__imp_CreateEventW
0x180002825  mov     cs:hHandle, rax
0x18000282c  test    rax, rax
0x18000282f  jz      short loc_180002855
0x180002831  xor     ecx, ecx
0x180002833  call    __scrt_initialize_onexit_tables
0x180002838  test    al, al
0x18000283a  jz      short loc_180002855
0x18000283c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180002843  call    atexit
0x180002848  mov     rbx, [rsp+28h+arg_0]
0x18000284d  xor     eax, eax
0x18000284f  add     rsp, 20h
0x180002853  pop     rdi
0x180002854  retn
0x180002855  mov     ecx, 7
0x18000285a  call    __scrt_fastfail
```
