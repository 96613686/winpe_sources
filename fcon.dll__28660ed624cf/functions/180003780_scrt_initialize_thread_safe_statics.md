# __scrt_initialize_thread_safe_statics

- ea: `0x180003780`
- end: `0x180003850`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800034d0`
- `0x1800036a0`
- `0x180003780`
- `0x180003bf4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800037a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800037b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800037a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800037b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800037d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800037e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800037d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800037e3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003796`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003796`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000380f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000380f`

## string_xrefs

- `0x18000379c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800037b1`: `kernel32.dll`

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
    qword_1800FB450 = (__int64)ProcAddress;
    qword_1800FB458 = (__int64)v2;
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
0x180003780  mov     [rsp+arg_0], rbx
0x180003785  push    rdi
0x180003786  sub     rsp, 20h
0x18000378a  mov     edx, 0FA0h; dwSpinCount
0x18000378f  lea     rcx, CriticalSection; lpCriticalSection
0x180003796  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000379c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800037a3  call    cs:__imp_GetModuleHandleW
0x1800037a9  mov     rbx, rax
0x1800037ac  test    rax, rax
0x1800037af  jnz     short loc_1800037C6
0x1800037b1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800037b8  call    cs:__imp_GetModuleHandleW
0x1800037be  mov     rbx, rax
0x1800037c1  test    rax, rax
0x1800037c4  jz      short loc_180003845
0x1800037c6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800037cd  mov     rcx, rbx; hModule
0x1800037d0  call    cs:__imp_GetProcAddress
0x1800037d6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800037dd  mov     rcx, rbx; hModule
0x1800037e0  mov     rdi, rax
0x1800037e3  call    cs:__imp_GetProcAddress
0x1800037e9  test    rdi, rdi
0x1800037ec  jz      short loc_180003803
0x1800037ee  test    rax, rax
0x1800037f1  jz      short loc_180003803
0x1800037f3  mov     cs:qword_1800FB450, rdi
0x1800037fa  mov     cs:qword_1800FB458, rax
0x180003801  jmp     short loc_180003821
0x180003803  xor     r9d, r9d; lpName
0x180003806  xor     r8d, r8d; bInitialState
0x180003809  xor     ecx, ecx; lpEventAttributes
0x18000380b  lea     edx, [r9+1]; bManualReset
0x18000380f  call    cs:__imp_CreateEventW
0x180003815  mov     cs:hHandle, rax
0x18000381c  test    rax, rax
0x18000381f  jz      short loc_180003845
0x180003821  xor     ecx, ecx
0x180003823  call    __scrt_initialize_onexit_tables
0x180003828  test    al, al
0x18000382a  jz      short loc_180003845
0x18000382c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180003833  call    atexit
0x180003838  mov     rbx, [rsp+28h+arg_0]
0x18000383d  xor     eax, eax
0x18000383f  add     rsp, 20h
0x180003843  pop     rdi
0x180003844  retn
0x180003845  mov     ecx, 7
0x18000384a  call    __scrt_fastfail
```
