# __scrt_initialize_thread_safe_statics

- ea: `0x180012ce0`
- end: `0x180012db0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180011c04`
- `0x180011dd4`
- `0x180011f44`
- `0x180012ce0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180012cf6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180012cf6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012d6f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012d6f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012d30`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012d43`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012d30`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012d43`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012d03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012d18`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012d03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012d18`

## string_xrefs

- `0x180012cfc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180012d11`: `kernel32.dll`

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
    qword_180049440 = (__int64)ProcAddress;
    qword_180049448 = (__int64)v2;
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
0x180012ce0  mov     [rsp+arg_0], rbx
0x180012ce5  push    rdi
0x180012ce6  sub     rsp, 20h
0x180012cea  mov     edx, 0FA0h; dwSpinCount
0x180012cef  lea     rcx, CriticalSection; lpCriticalSection
0x180012cf6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180012cfc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180012d03  call    cs:__imp_GetModuleHandleW
0x180012d09  mov     rbx, rax
0x180012d0c  test    rax, rax
0x180012d0f  jnz     short loc_180012D26
0x180012d11  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180012d18  call    cs:__imp_GetModuleHandleW
0x180012d1e  mov     rbx, rax
0x180012d21  test    rax, rax
0x180012d24  jz      short loc_180012DA5
0x180012d26  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180012d2d  mov     rcx, rbx; hModule
0x180012d30  call    cs:__imp_GetProcAddress
0x180012d36  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180012d3d  mov     rcx, rbx; hModule
0x180012d40  mov     rdi, rax
0x180012d43  call    cs:__imp_GetProcAddress
0x180012d49  test    rdi, rdi
0x180012d4c  jz      short loc_180012D63
0x180012d4e  test    rax, rax
0x180012d51  jz      short loc_180012D63
0x180012d53  mov     cs:qword_180049440, rdi
0x180012d5a  mov     cs:qword_180049448, rax
0x180012d61  jmp     short loc_180012D81
0x180012d63  xor     r9d, r9d; lpName
0x180012d66  xor     r8d, r8d; bInitialState
0x180012d69  xor     ecx, ecx; lpEventAttributes
0x180012d6b  lea     edx, [r9+1]; bManualReset
0x180012d6f  call    cs:__imp_CreateEventW
0x180012d75  mov     cs:hHandle, rax
0x180012d7c  test    rax, rax
0x180012d7f  jz      short loc_180012DA5
0x180012d81  xor     ecx, ecx
0x180012d83  call    __scrt_initialize_onexit_tables
0x180012d88  test    al, al
0x180012d8a  jz      short loc_180012DA5
0x180012d8c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180012d93  call    atexit
0x180012d98  mov     rbx, [rsp+28h+arg_0]
0x180012d9d  xor     eax, eax
0x180012d9f  add     rsp, 20h
0x180012da3  pop     rdi
0x180012da4  retn
0x180012da5  mov     ecx, 7
0x180012daa  call    __scrt_fastfail
```
