# __scrt_initialize_thread_safe_statics

- ea: `0x180012110`
- end: `0x1800121e0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180012110`
- `0x180012680`
- `0x180012850`
- `0x180012a38`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012133`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012148`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012133`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012148`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012160`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012173`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012160`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012173`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001219f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001219f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180012126`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180012126`

## string_xrefs

- `0x18001212c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180012141`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_18005FD68, 0xFA0u);
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
    qword_18005FD90 = (__int64)ProcAddress;
    qword_18005FD98 = (__int64)v2;
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
0x180012110  mov     [rsp+arg_0], rbx
0x180012115  push    rdi
0x180012116  sub     rsp, 20h
0x18001211a  mov     edx, 0FA0h; dwSpinCount
0x18001211f  lea     rcx, stru_18005FD68; lpCriticalSection
0x180012126  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18001212c  lea     rcx, aApiMsWinCoreSy_1; "api-ms-win-core-synch-l1-2-0.dll"
0x180012133  call    cs:__imp_GetModuleHandleW
0x180012139  mov     rbx, rax
0x18001213c  test    rax, rax
0x18001213f  jnz     short loc_180012156
0x180012141  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180012148  call    cs:__imp_GetModuleHandleW
0x18001214e  mov     rbx, rax
0x180012151  test    rax, rax
0x180012154  jz      short loc_1800121D5
0x180012156  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18001215d  mov     rcx, rbx; hModule
0x180012160  call    cs:__imp_GetProcAddress
0x180012166  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18001216d  mov     rcx, rbx; hModule
0x180012170  mov     rdi, rax
0x180012173  call    cs:__imp_GetProcAddress
0x180012179  test    rdi, rdi
0x18001217c  jz      short loc_180012193
0x18001217e  test    rax, rax
0x180012181  jz      short loc_180012193
0x180012183  mov     cs:qword_18005FD90, rdi
0x18001218a  mov     cs:qword_18005FD98, rax
0x180012191  jmp     short loc_1800121B1
0x180012193  xor     r9d, r9d; lpName
0x180012196  xor     r8d, r8d; bInitialState
0x180012199  xor     ecx, ecx; lpEventAttributes
0x18001219b  lea     edx, [r9+1]; bManualReset
0x18001219f  call    cs:__imp_CreateEventW
0x1800121a5  mov     cs:hHandle, rax
0x1800121ac  test    rax, rax
0x1800121af  jz      short loc_1800121D5
0x1800121b1  xor     ecx, ecx
0x1800121b3  call    __scrt_initialize_onexit_tables
0x1800121b8  test    al, al
0x1800121ba  jz      short loc_1800121D5
0x1800121bc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800121c3  call    atexit
0x1800121c8  mov     rbx, [rsp+28h+arg_0]
0x1800121cd  xor     eax, eax
0x1800121cf  add     rsp, 20h
0x1800121d3  pop     rdi
0x1800121d4  retn
0x1800121d5  mov     ecx, 7
0x1800121da  call    __scrt_fastfail
```
