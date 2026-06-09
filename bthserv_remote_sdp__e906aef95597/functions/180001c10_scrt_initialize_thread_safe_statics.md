# __scrt_initialize_thread_safe_statics

- ea: `0x180001c10`
- end: `0x180001ce0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800019a4`
- `0x180001b74`
- `0x180001c10`
- `0x180001fe4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180001c33`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180001c48`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180001c33`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180001c48`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001c60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001c73`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001c60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001c73`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180001c26`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180001c26`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001c9f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001c9f`

## string_xrefs

- `0x180001c2c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180001c41`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800465A8, 0xFA0u);
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
    qword_1800465D0 = (__int64)ProcAddress;
    qword_1800465D8 = (__int64)v2;
    goto LABEL_7;
  }
  hHandle = CreateEventW(0, 1, 0, 0);
  if ( !hHandle )
  {
LABEL_9:
    _scrt_fastfail(7);
    JUMPOUT(0x180001CDFLL);
  }
LABEL_7:
  if ( !(unsigned __int8)_scrt_initialize_onexit_tables(0) )
    goto LABEL_9;
  atexit(_scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x180001c10  mov     [rsp+arg_0], rbx
0x180001c15  push    rdi
0x180001c16  sub     rsp, 20h
0x180001c1a  mov     edx, 0FA0h; dwSpinCount
0x180001c1f  lea     rcx, stru_1800465A8; lpCriticalSection
0x180001c26  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180001c2c  lea     rcx, ModuleName
0x180001c33  call    cs:__imp_GetModuleHandleW
0x180001c39  mov     rbx, rax
0x180001c3c  test    rax, rax
0x180001c3f  jnz     short loc_180001C56
0x180001c41  lea     rcx, aKernel32Dll
0x180001c48  call    cs:__imp_GetModuleHandleW
0x180001c4e  mov     rbx, rax
0x180001c51  test    rax, rax
0x180001c54  jz      short loc_180001CD5
0x180001c56  lea     rdx, ProcName
0x180001c5d  mov     rcx, rbx; hModule
0x180001c60  call    cs:__imp_GetProcAddress
0x180001c66  lea     rdx, aWakeallconditi
0x180001c6d  mov     rcx, rbx; hModule
0x180001c70  mov     rdi, rax
0x180001c73  call    cs:__imp_GetProcAddress
0x180001c79  test    rdi, rdi
0x180001c7c  jz      short loc_180001C93
0x180001c7e  test    rax, rax
0x180001c81  jz      short loc_180001C93
0x180001c83  mov     cs:qword_1800465D0, rdi
0x180001c8a  mov     cs:qword_1800465D8, rax
0x180001c91  jmp     short loc_180001CB1
0x180001c93  xor     r9d, r9d; lpName
0x180001c96  xor     r8d, r8d; bInitialState
0x180001c99  xor     ecx, ecx; lpEventAttributes
0x180001c9b  lea     edx, [r9+1]; bManualReset
0x180001c9f  call    cs:__imp_CreateEventW
0x180001ca5  mov     cs:hHandle, rax
0x180001cac  test    rax, rax
0x180001caf  jz      short loc_180001CD5
0x180001cb1  xor     ecx, ecx
0x180001cb3  call    __scrt_initialize_onexit_tables
0x180001cb8  test    al, al
0x180001cba  jz      short loc_180001CD5
0x180001cbc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180001cc3  call    atexit
0x180001cc8  mov     rbx, [rsp+28h+arg_0]
0x180001ccd  xor     eax, eax
0x180001ccf  add     rsp, 20h
0x180001cd3  pop     rdi
0x180001cd4  retn
0x180001cd5  mov     ecx, 7
0x180001cda  call    __scrt_fastfail
```
