# __scrt_initialize_thread_safe_statics

- ea: `0x180019550`
- end: `0x180019620`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180019318`
- `0x1800194e8`
- `0x180019550`
- `0x180019cc8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019573`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019588`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019573`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019588`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800195a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800195b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800195a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800195b3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180019566`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180019566`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800195df`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800195df`

## string_xrefs

- `0x18001956c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180019581`: `kernel32.dll`

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
    qword_18025A358 = (__int64)ProcAddress;
    qword_18025A360 = (__int64)v2;
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
0x180019550  mov     [rsp+arg_0], rbx
0x180019555  push    rdi
0x180019556  sub     rsp, 20h
0x18001955a  mov     edx, 0FA0h; dwSpinCount
0x18001955f  lea     rcx, CriticalSection; lpCriticalSection
0x180019566  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18001956c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180019573  call    cs:__imp_GetModuleHandleW
0x180019579  mov     rbx, rax
0x18001957c  test    rax, rax
0x18001957f  jnz     short loc_180019596
0x180019581  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180019588  call    cs:__imp_GetModuleHandleW
0x18001958e  mov     rbx, rax
0x180019591  test    rax, rax
0x180019594  jz      short loc_180019615
0x180019596  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18001959d  mov     rcx, rbx; hModule
0x1800195a0  call    cs:__imp_GetProcAddress
0x1800195a6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800195ad  mov     rcx, rbx; hModule
0x1800195b0  mov     rdi, rax
0x1800195b3  call    cs:__imp_GetProcAddress
0x1800195b9  test    rdi, rdi
0x1800195bc  jz      short loc_1800195D3
0x1800195be  test    rax, rax
0x1800195c1  jz      short loc_1800195D3
0x1800195c3  mov     cs:qword_18025A358, rdi
0x1800195ca  mov     cs:qword_18025A360, rax
0x1800195d1  jmp     short loc_1800195F1
0x1800195d3  xor     r9d, r9d; lpName
0x1800195d6  xor     r8d, r8d; bInitialState
0x1800195d9  xor     ecx, ecx; lpEventAttributes
0x1800195db  lea     edx, [r9+1]; bManualReset
0x1800195df  call    cs:__imp_CreateEventW
0x1800195e5  mov     cs:hHandle, rax
0x1800195ec  test    rax, rax
0x1800195ef  jz      short loc_180019615
0x1800195f1  xor     ecx, ecx
0x1800195f3  call    __scrt_initialize_onexit_tables
0x1800195f8  test    al, al
0x1800195fa  jz      short loc_180019615
0x1800195fc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180019603  call    atexit
0x180019608  mov     rbx, [rsp+28h+arg_0]
0x18001960d  xor     eax, eax
0x18001960f  add     rsp, 20h
0x180019613  pop     rdi
0x180019614  retn
0x180019615  mov     ecx, 7
0x18001961a  call    __scrt_fastfail
```
