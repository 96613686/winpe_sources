# __scrt_initialize_thread_safe_statics

- ea: `0x1800428b0`
- end: `0x180042980`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800425f0`
- `0x1800427c0`
- `0x1800428b0`
- `0x180042c58`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800428d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800428e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800428d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800428e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042900`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042913`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042900`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042913`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004293f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004293f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800428c6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800428c6`

## string_xrefs

- `0x1800428cc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800428e1`: `kernel32.dll`

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
    qword_18009A890 = (__int64)ProcAddress;
    qword_18009A898 = (__int64)v2;
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
0x1800428b0  mov     [rsp+arg_0], rbx
0x1800428b5  push    rdi
0x1800428b6  sub     rsp, 20h
0x1800428ba  mov     edx, 0FA0h; dwSpinCount
0x1800428bf  lea     rcx, CriticalSection; lpCriticalSection
0x1800428c6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800428cc  lea     rcx, aApiMsWinCoreSy_2; "api-ms-win-core-synch-l1-2-0.dll"
0x1800428d3  call    cs:__imp_GetModuleHandleW
0x1800428d9  mov     rbx, rax
0x1800428dc  test    rax, rax
0x1800428df  jnz     short loc_1800428F6
0x1800428e1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800428e8  call    cs:__imp_GetModuleHandleW
0x1800428ee  mov     rbx, rax
0x1800428f1  test    rax, rax
0x1800428f4  jz      short loc_180042975
0x1800428f6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x1800428fd  mov     rcx, rbx; hModule
0x180042900  call    cs:__imp_GetProcAddress
0x180042906  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18004290d  mov     rcx, rbx; hModule
0x180042910  mov     rdi, rax
0x180042913  call    cs:__imp_GetProcAddress
0x180042919  test    rdi, rdi
0x18004291c  jz      short loc_180042933
0x18004291e  test    rax, rax
0x180042921  jz      short loc_180042933
0x180042923  mov     cs:qword_18009A890, rdi
0x18004292a  mov     cs:qword_18009A898, rax
0x180042931  jmp     short loc_180042951
0x180042933  xor     r9d, r9d; lpName
0x180042936  xor     r8d, r8d; bInitialState
0x180042939  xor     ecx, ecx; lpEventAttributes
0x18004293b  lea     edx, [r9+1]; bManualReset
0x18004293f  call    cs:__imp_CreateEventW
0x180042945  mov     cs:hHandle, rax
0x18004294c  test    rax, rax
0x18004294f  jz      short loc_180042975
0x180042951  xor     ecx, ecx
0x180042953  call    __scrt_initialize_onexit_tables
0x180042958  test    al, al
0x18004295a  jz      short loc_180042975
0x18004295c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180042963  call    atexit
0x180042968  mov     rbx, [rsp+28h+arg_0]
0x18004296d  xor     eax, eax
0x18004296f  add     rsp, 20h
0x180042973  pop     rdi
0x180042974  retn
0x180042975  mov     ecx, 7
0x18004297a  call    __scrt_fastfail
```
