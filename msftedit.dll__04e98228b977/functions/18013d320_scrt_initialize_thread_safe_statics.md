# __scrt_initialize_thread_safe_statics

- ea: `0x18013d320`
- end: `0x18013d3f0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18013d060`
- `0x18013d230`
- `0x18013d320`
- `0x18013da14`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18013d370`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18013d383`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18013d370`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18013d383`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18013d343`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18013d358`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18013d343`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18013d358`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18013d3af`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18013d3af`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18013d336`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18013d336`

## string_xrefs

- `0x18013d33c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18013d351`: `kernel32.dll`

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
    qword_1802E1E88 = (__int64)ProcAddress;
    qword_1802E1E90 = (__int64)v2;
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
0x18013d320  mov     [rsp+arg_0], rbx
0x18013d325  push    rdi
0x18013d326  sub     rsp, 20h
0x18013d32a  mov     edx, 0FA0h; dwSpinCount
0x18013d32f  lea     rcx, CriticalSection; lpCriticalSection
0x18013d336  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18013d33c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x18013d343  call    cs:__imp_GetModuleHandleW
0x18013d349  mov     rbx, rax
0x18013d34c  test    rax, rax
0x18013d34f  jnz     short loc_18013D366
0x18013d351  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18013d358  call    cs:__imp_GetModuleHandleW
0x18013d35e  mov     rbx, rax
0x18013d361  test    rax, rax
0x18013d364  jz      short loc_18013D3E5
0x18013d366  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18013d36d  mov     rcx, rbx; hModule
0x18013d370  call    cs:__imp_GetProcAddress
0x18013d376  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18013d37d  mov     rcx, rbx; hModule
0x18013d380  mov     rdi, rax
0x18013d383  call    cs:__imp_GetProcAddress
0x18013d389  test    rdi, rdi
0x18013d38c  jz      short loc_18013D3A3
0x18013d38e  test    rax, rax
0x18013d391  jz      short loc_18013D3A3
0x18013d393  mov     cs:qword_1802E1E88, rdi
0x18013d39a  mov     cs:qword_1802E1E90, rax
0x18013d3a1  jmp     short loc_18013D3C1
0x18013d3a3  xor     r9d, r9d; lpName
0x18013d3a6  xor     r8d, r8d; bInitialState
0x18013d3a9  xor     ecx, ecx; lpEventAttributes
0x18013d3ab  lea     edx, [r9+1]; bManualReset
0x18013d3af  call    cs:__imp_CreateEventW
0x18013d3b5  mov     cs:hHandle, rax
0x18013d3bc  test    rax, rax
0x18013d3bf  jz      short loc_18013D3E5
0x18013d3c1  xor     ecx, ecx
0x18013d3c3  call    __scrt_initialize_onexit_tables
0x18013d3c8  test    al, al
0x18013d3ca  jz      short loc_18013D3E5
0x18013d3cc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18013d3d3  call    atexit
0x18013d3d8  mov     rbx, [rsp+28h+arg_0]
0x18013d3dd  xor     eax, eax
0x18013d3df  add     rsp, 20h
0x18013d3e3  pop     rdi
0x18013d3e4  retn
0x18013d3e5  mov     ecx, 7
0x18013d3ea  call    __scrt_fastfail
```
