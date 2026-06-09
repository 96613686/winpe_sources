# __scrt_initialize_thread_safe_statics

- ea: `0x18004dd10`
- end: `0x18004dde0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18004daec`
- `0x18004dcbc`
- `0x18004dd10`
- `0x18004e0e4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004dd33`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004dd48`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004dd33`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004dd48`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004dd60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004dd73`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004dd60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004dd73`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004dd9f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004dd9f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18004dd26`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18004dd26`

## string_xrefs

- `0x18004dd2c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18004dd41`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800C2C08, 0xFA0u);
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
    qword_1800C2C30 = (__int64)ProcAddress;
    qword_1800C2C38 = (__int64)v2;
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
0x18004dd10  mov     [rsp+arg_0], rbx
0x18004dd15  push    rdi
0x18004dd16  sub     rsp, 20h
0x18004dd1a  mov     edx, 0FA0h; dwSpinCount
0x18004dd1f  lea     rcx, stru_1800C2C08; lpCriticalSection
0x18004dd26  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18004dd2c  lea     rcx, aApiMsWinCoreSy_2; "api-ms-win-core-synch-l1-2-0.dll"
0x18004dd33  call    cs:__imp_GetModuleHandleW
0x18004dd39  mov     rbx, rax
0x18004dd3c  test    rax, rax
0x18004dd3f  jnz     short loc_18004DD56
0x18004dd41  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18004dd48  call    cs:__imp_GetModuleHandleW
0x18004dd4e  mov     rbx, rax
0x18004dd51  test    rax, rax
0x18004dd54  jz      short loc_18004DDD5
0x18004dd56  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18004dd5d  mov     rcx, rbx; hModule
0x18004dd60  call    cs:__imp_GetProcAddress
0x18004dd66  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18004dd6d  mov     rcx, rbx; hModule
0x18004dd70  mov     rdi, rax
0x18004dd73  call    cs:__imp_GetProcAddress
0x18004dd79  test    rdi, rdi
0x18004dd7c  jz      short loc_18004DD93
0x18004dd7e  test    rax, rax
0x18004dd81  jz      short loc_18004DD93
0x18004dd83  mov     cs:qword_1800C2C30, rdi
0x18004dd8a  mov     cs:qword_1800C2C38, rax
0x18004dd91  jmp     short loc_18004DDB1
0x18004dd93  xor     r9d, r9d; lpName
0x18004dd96  xor     r8d, r8d; bInitialState
0x18004dd99  xor     ecx, ecx; lpEventAttributes
0x18004dd9b  lea     edx, [r9+1]; bManualReset
0x18004dd9f  call    cs:__imp_CreateEventW
0x18004dda5  mov     cs:hHandle, rax
0x18004ddac  test    rax, rax
0x18004ddaf  jz      short loc_18004DDD5
0x18004ddb1  xor     ecx, ecx
0x18004ddb3  call    __scrt_initialize_onexit_tables
0x18004ddb8  test    al, al
0x18004ddba  jz      short loc_18004DDD5
0x18004ddbc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18004ddc3  call    atexit
0x18004ddc8  mov     rbx, [rsp+28h+arg_0]
0x18004ddcd  xor     eax, eax
0x18004ddcf  add     rsp, 20h
0x18004ddd3  pop     rdi
0x18004ddd4  retn
0x18004ddd5  mov     ecx, 7
0x18004ddda  call    __scrt_fastfail
```
