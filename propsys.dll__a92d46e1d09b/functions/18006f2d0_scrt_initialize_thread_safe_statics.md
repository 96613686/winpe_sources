# __scrt_initialize_thread_safe_statics

- ea: `0x18006f2d0`
- end: `0x18006f3a0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18006efdc`
- `0x18006f1ac`
- `0x18006f2d0`
- `0x18006f994`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006f320`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006f333`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006f320`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006f333`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006f2f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006f308`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006f2f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006f308`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18006f2e6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18006f2e6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f35f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f35f`

## string_xrefs

- `0x18006f2ec`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18006f301`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800F1068, 0xFA0u);
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
    qword_1800F1090 = (__int64)ProcAddress;
    qword_1800F1098 = (__int64)v2;
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
0x18006f2d0  mov     [rsp+arg_0], rbx
0x18006f2d5  push    rdi
0x18006f2d6  sub     rsp, 20h
0x18006f2da  mov     edx, 0FA0h; dwSpinCount
0x18006f2df  lea     rcx, stru_1800F1068; lpCriticalSection
0x18006f2e6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18006f2ec  lea     rcx, aApiMsWinCoreSy_2; "api-ms-win-core-synch-l1-2-0.dll"
0x18006f2f3  call    cs:__imp_GetModuleHandleW
0x18006f2f9  mov     rbx, rax
0x18006f2fc  test    rax, rax
0x18006f2ff  jnz     short loc_18006F316
0x18006f301  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18006f308  call    cs:__imp_GetModuleHandleW
0x18006f30e  mov     rbx, rax
0x18006f311  test    rax, rax
0x18006f314  jz      short loc_18006F395
0x18006f316  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18006f31d  mov     rcx, rbx; hModule
0x18006f320  call    cs:__imp_GetProcAddress
0x18006f326  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18006f32d  mov     rcx, rbx; hModule
0x18006f330  mov     rdi, rax
0x18006f333  call    cs:__imp_GetProcAddress
0x18006f339  test    rdi, rdi
0x18006f33c  jz      short loc_18006F353
0x18006f33e  test    rax, rax
0x18006f341  jz      short loc_18006F353
0x18006f343  mov     cs:qword_1800F1090, rdi
0x18006f34a  mov     cs:qword_1800F1098, rax
0x18006f351  jmp     short loc_18006F371
0x18006f353  xor     r9d, r9d; lpName
0x18006f356  xor     r8d, r8d; bInitialState
0x18006f359  xor     ecx, ecx; lpEventAttributes
0x18006f35b  lea     edx, [r9+1]; bManualReset
0x18006f35f  call    cs:__imp_CreateEventW
0x18006f365  mov     cs:hHandle, rax
0x18006f36c  test    rax, rax
0x18006f36f  jz      short loc_18006F395
0x18006f371  xor     ecx, ecx
0x18006f373  call    __scrt_initialize_onexit_tables
0x18006f378  test    al, al
0x18006f37a  jz      short loc_18006F395
0x18006f37c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18006f383  call    atexit
0x18006f388  mov     rbx, [rsp+28h+arg_0]
0x18006f38d  xor     eax, eax
0x18006f38f  add     rsp, 20h
0x18006f393  pop     rdi
0x18006f394  retn
0x18006f395  mov     ecx, 7
0x18006f39a  call    __scrt_fastfail
```
