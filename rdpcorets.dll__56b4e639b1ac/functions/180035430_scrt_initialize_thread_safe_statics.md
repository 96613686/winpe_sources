# __scrt_initialize_thread_safe_statics

- ea: `0x180035430`
- end: `0x180035500`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180033f8c`
- `0x18003415c`
- `0x180034348`
- `0x180035430`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180035453`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180035468`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180035453`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180035468`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035480`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035493`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035480`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035493`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800354bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800354bf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180035446`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180035446`

## string_xrefs

- `0x18003544c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180035461`: `kernel32.dll`

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
    qword_1801B8908 = (__int64)ProcAddress;
    qword_1801B8910 = (__int64)v2;
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
0x180035430  mov     [rsp+arg_0], rbx
0x180035435  push    rdi
0x180035436  sub     rsp, 20h
0x18003543a  mov     edx, 0FA0h; dwSpinCount
0x18003543f  lea     rcx, CriticalSection; lpCriticalSection
0x180035446  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18003544c  lea     rcx, aApiMsWinCoreSy_4; "api-ms-win-core-synch-l1-2-0.dll"
0x180035453  call    cs:__imp_GetModuleHandleW
0x180035459  mov     rbx, rax
0x18003545c  test    rax, rax
0x18003545f  jnz     short loc_180035476
0x180035461  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180035468  call    cs:__imp_GetModuleHandleW
0x18003546e  mov     rbx, rax
0x180035471  test    rax, rax
0x180035474  jz      short loc_1800354F5
0x180035476  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18003547d  mov     rcx, rbx; hModule
0x180035480  call    cs:__imp_GetProcAddress
0x180035486  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18003548d  mov     rcx, rbx; hModule
0x180035490  mov     rdi, rax
0x180035493  call    cs:__imp_GetProcAddress
0x180035499  test    rdi, rdi
0x18003549c  jz      short loc_1800354B3
0x18003549e  test    rax, rax
0x1800354a1  jz      short loc_1800354B3
0x1800354a3  mov     cs:qword_1801B8908, rdi
0x1800354aa  mov     cs:qword_1801B8910, rax
0x1800354b1  jmp     short loc_1800354D1
0x1800354b3  xor     r9d, r9d; lpName
0x1800354b6  xor     r8d, r8d; bInitialState
0x1800354b9  xor     ecx, ecx; lpEventAttributes
0x1800354bb  lea     edx, [r9+1]; bManualReset
0x1800354bf  call    cs:__imp_CreateEventW
0x1800354c5  mov     cs:hHandle, rax
0x1800354cc  test    rax, rax
0x1800354cf  jz      short loc_1800354F5
0x1800354d1  xor     ecx, ecx
0x1800354d3  call    __scrt_initialize_onexit_tables
0x1800354d8  test    al, al
0x1800354da  jz      short loc_1800354F5
0x1800354dc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800354e3  call    atexit
0x1800354e8  mov     rbx, [rsp+28h+arg_0]
0x1800354ed  xor     eax, eax
0x1800354ef  add     rsp, 20h
0x1800354f3  pop     rdi
0x1800354f4  retn
0x1800354f5  mov     ecx, 7
0x1800354fa  call    __scrt_fastfail
```
