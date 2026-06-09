# __scrt_initialize_thread_safe_statics

- ea: `0x180074120`
- end: `0x1800741f0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180070860`
- `0x180070a30`
- `0x180070ba4`
- `0x180074120`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180074143`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180074158`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180074143`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180074158`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180074170`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180074183`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180074170`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180074183`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800741af`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800741af`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180074136`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180074136`

## string_xrefs

- `0x18007413c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180074151`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180140930, 0xFA0u);
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
    qword_180140958 = (__int64)ProcAddress;
    qword_180140960 = (__int64)v2;
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
0x180074120  mov     [rsp+arg_0], rbx
0x180074125  push    rdi
0x180074126  sub     rsp, 20h
0x18007412a  mov     edx, 0FA0h; dwSpinCount
0x18007412f  lea     rcx, stru_180140930; lpCriticalSection
0x180074136  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18007413c  lea     rcx, aApiMsWinCoreSy_2; "api-ms-win-core-synch-l1-2-0.dll"
0x180074143  call    cs:__imp_GetModuleHandleW
0x180074149  mov     rbx, rax
0x18007414c  test    rax, rax
0x18007414f  jnz     short loc_180074166
0x180074151  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180074158  call    cs:__imp_GetModuleHandleW
0x18007415e  mov     rbx, rax
0x180074161  test    rax, rax
0x180074164  jz      short loc_1800741E5
0x180074166  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18007416d  mov     rcx, rbx; hModule
0x180074170  call    cs:__imp_GetProcAddress
0x180074176  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18007417d  mov     rcx, rbx; hModule
0x180074180  mov     rdi, rax
0x180074183  call    cs:__imp_GetProcAddress
0x180074189  test    rdi, rdi
0x18007418c  jz      short loc_1800741A3
0x18007418e  test    rax, rax
0x180074191  jz      short loc_1800741A3
0x180074193  mov     cs:qword_180140958, rdi
0x18007419a  mov     cs:qword_180140960, rax
0x1800741a1  jmp     short loc_1800741C1
0x1800741a3  xor     r9d, r9d; lpName
0x1800741a6  xor     r8d, r8d; bInitialState
0x1800741a9  xor     ecx, ecx; lpEventAttributes
0x1800741ab  lea     edx, [r9+1]; bManualReset
0x1800741af  call    cs:__imp_CreateEventW
0x1800741b5  mov     cs:hHandle, rax
0x1800741bc  test    rax, rax
0x1800741bf  jz      short loc_1800741E5
0x1800741c1  xor     ecx, ecx
0x1800741c3  call    __scrt_initialize_onexit_tables
0x1800741c8  test    al, al
0x1800741ca  jz      short loc_1800741E5
0x1800741cc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800741d3  call    atexit
0x1800741d8  mov     rbx, [rsp+28h+arg_0]
0x1800741dd  xor     eax, eax
0x1800741df  add     rsp, 20h
0x1800741e3  pop     rdi
0x1800741e4  retn
0x1800741e5  mov     ecx, 7
0x1800741ea  call    __scrt_fastfail
```
