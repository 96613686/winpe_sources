# __scrt_initialize_thread_safe_statics

- ea: `0x1800195d0`
- end: `0x1800196a0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180019398`
- `0x180019568`
- `0x1800195d0`
- `0x180019d48`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800195f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019608`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800195f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019608`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019620`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019633`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019620`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019633`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800195e6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800195e6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001965f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001965f`

## string_xrefs

- `0x1800195ec`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180019601`: `kernel32.dll`

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
    qword_18025C458 = (__int64)ProcAddress;
    qword_18025C460 = (__int64)v2;
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
0x1800195d0  mov     [rsp+arg_0], rbx
0x1800195d5  push    rdi
0x1800195d6  sub     rsp, 20h
0x1800195da  mov     edx, 0FA0h; dwSpinCount
0x1800195df  lea     rcx, CriticalSection; lpCriticalSection
0x1800195e6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800195ec  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800195f3  call    cs:__imp_GetModuleHandleW
0x1800195f9  mov     rbx, rax
0x1800195fc  test    rax, rax
0x1800195ff  jnz     short loc_180019616
0x180019601  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180019608  call    cs:__imp_GetModuleHandleW
0x18001960e  mov     rbx, rax
0x180019611  test    rax, rax
0x180019614  jz      short loc_180019695
0x180019616  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18001961d  mov     rcx, rbx; hModule
0x180019620  call    cs:__imp_GetProcAddress
0x180019626  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18001962d  mov     rcx, rbx; hModule
0x180019630  mov     rdi, rax
0x180019633  call    cs:__imp_GetProcAddress
0x180019639  test    rdi, rdi
0x18001963c  jz      short loc_180019653
0x18001963e  test    rax, rax
0x180019641  jz      short loc_180019653
0x180019643  mov     cs:qword_18025C458, rdi
0x18001964a  mov     cs:qword_18025C460, rax
0x180019651  jmp     short loc_180019671
0x180019653  xor     r9d, r9d; lpName
0x180019656  xor     r8d, r8d; bInitialState
0x180019659  xor     ecx, ecx; lpEventAttributes
0x18001965b  lea     edx, [r9+1]; bManualReset
0x18001965f  call    cs:__imp_CreateEventW
0x180019665  mov     cs:hHandle, rax
0x18001966c  test    rax, rax
0x18001966f  jz      short loc_180019695
0x180019671  xor     ecx, ecx
0x180019673  call    __scrt_initialize_onexit_tables
0x180019678  test    al, al
0x18001967a  jz      short loc_180019695
0x18001967c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180019683  call    atexit
0x180019688  mov     rbx, [rsp+28h+arg_0]
0x18001968d  xor     eax, eax
0x18001968f  add     rsp, 20h
0x180019693  pop     rdi
0x180019694  retn
0x180019695  mov     ecx, 7
0x18001969a  call    __scrt_fastfail
```
