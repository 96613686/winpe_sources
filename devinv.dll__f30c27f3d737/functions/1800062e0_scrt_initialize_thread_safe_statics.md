# __scrt_initialize_thread_safe_statics

- ea: `0x1800062e0`
- end: `0x1800063b0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180006020`
- `0x1800061f0`
- `0x1800062e0`
- `0x180006bb8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006303`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006318`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006303`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006318`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006330`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006343`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006330`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006343`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800062f6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800062f6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000636f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000636f`

## string_xrefs

- `0x1800062fc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180006311`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180156B28, 0xFA0u);
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
    qword_180156B50 = (__int64)ProcAddress;
    qword_180156B58 = (__int64)v2;
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
0x1800062e0  mov     [rsp+arg_0], rbx
0x1800062e5  push    rdi
0x1800062e6  sub     rsp, 20h
0x1800062ea  mov     edx, 0FA0h; dwSpinCount
0x1800062ef  lea     rcx, stru_180156B28; lpCriticalSection
0x1800062f6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800062fc  lea     rcx, aApiMsWinCoreSy_4; "api-ms-win-core-synch-l1-2-0.dll"
0x180006303  call    cs:__imp_GetModuleHandleW
0x180006309  mov     rbx, rax
0x18000630c  test    rax, rax
0x18000630f  jnz     short loc_180006326
0x180006311  lea     rcx, SourceString; "kernel32.dll"
0x180006318  call    cs:__imp_GetModuleHandleW
0x18000631e  mov     rbx, rax
0x180006321  test    rax, rax
0x180006324  jz      short loc_1800063A5
0x180006326  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18000632d  mov     rcx, rbx; hModule
0x180006330  call    cs:__imp_GetProcAddress
0x180006336  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000633d  mov     rcx, rbx; hModule
0x180006340  mov     rdi, rax
0x180006343  call    cs:__imp_GetProcAddress
0x180006349  test    rdi, rdi
0x18000634c  jz      short loc_180006363
0x18000634e  test    rax, rax
0x180006351  jz      short loc_180006363
0x180006353  mov     cs:qword_180156B50, rdi
0x18000635a  mov     cs:qword_180156B58, rax
0x180006361  jmp     short loc_180006381
0x180006363  xor     r9d, r9d; lpName
0x180006366  xor     r8d, r8d; bInitialState
0x180006369  xor     ecx, ecx; lpEventAttributes
0x18000636b  lea     edx, [r9+1]; bManualReset
0x18000636f  call    cs:__imp_CreateEventW
0x180006375  mov     cs:hHandle, rax
0x18000637c  test    rax, rax
0x18000637f  jz      short loc_1800063A5
0x180006381  xor     ecx, ecx
0x180006383  call    __scrt_initialize_onexit_tables
0x180006388  test    al, al
0x18000638a  jz      short loc_1800063A5
0x18000638c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180006393  call    atexit
0x180006398  mov     rbx, [rsp+28h+arg_0]
0x18000639d  xor     eax, eax
0x18000639f  add     rsp, 20h
0x1800063a3  pop     rdi
0x1800063a4  retn
0x1800063a5  mov     ecx, 7
0x1800063aa  call    __scrt_fastfail
```
