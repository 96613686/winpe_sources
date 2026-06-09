# __scrt_initialize_thread_safe_statics

- ea: `0x180004ab0`
- end: `0x180004b80`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180003498`
- `0x180003668`
- `0x180003b34`
- `0x180004ab0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004ad3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004ae8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004ad3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004ae8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004b00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004b13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004b00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004b13`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004ac6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004ac6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004b3f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004b3f`

## string_xrefs

- `0x180004acc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004ae1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180032A78, 0xFA0u);
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
    qword_180032AA0 = (__int64)ProcAddress;
    qword_180032AA8 = (__int64)v2;
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
0x180004ab0  mov     [rsp+arg_0], rbx
0x180004ab5  push    rdi
0x180004ab6  sub     rsp, 20h
0x180004aba  mov     edx, 0FA0h; dwSpinCount
0x180004abf  lea     rcx, stru_180032A78; lpCriticalSection
0x180004ac6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180004acc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180004ad3  call    cs:__imp_GetModuleHandleW
0x180004ad9  mov     rbx, rax
0x180004adc  test    rax, rax
0x180004adf  jnz     short loc_180004AF6
0x180004ae1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180004ae8  call    cs:__imp_GetModuleHandleW
0x180004aee  mov     rbx, rax
0x180004af1  test    rax, rax
0x180004af4  jz      short loc_180004B75
0x180004af6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180004afd  mov     rcx, rbx; hModule
0x180004b00  call    cs:__imp_GetProcAddress
0x180004b06  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180004b0d  mov     rcx, rbx; hModule
0x180004b10  mov     rdi, rax
0x180004b13  call    cs:__imp_GetProcAddress
0x180004b19  test    rdi, rdi
0x180004b1c  jz      short loc_180004B33
0x180004b1e  test    rax, rax
0x180004b21  jz      short loc_180004B33
0x180004b23  mov     cs:qword_180032AA0, rdi
0x180004b2a  mov     cs:qword_180032AA8, rax
0x180004b31  jmp     short loc_180004B51
0x180004b33  xor     r9d, r9d; lpName
0x180004b36  xor     r8d, r8d; bInitialState
0x180004b39  xor     ecx, ecx; lpEventAttributes
0x180004b3b  lea     edx, [r9+1]; bManualReset
0x180004b3f  call    cs:__imp_CreateEventW
0x180004b45  mov     cs:hHandle, rax
0x180004b4c  test    rax, rax
0x180004b4f  jz      short loc_180004B75
0x180004b51  xor     ecx, ecx
0x180004b53  call    __scrt_initialize_onexit_tables
0x180004b58  test    al, al
0x180004b5a  jz      short loc_180004B75
0x180004b5c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180004b63  call    atexit
0x180004b68  mov     rbx, [rsp+28h+arg_0]
0x180004b6d  xor     eax, eax
0x180004b6f  add     rsp, 20h
0x180004b73  pop     rdi
0x180004b74  retn
0x180004b75  mov     ecx, 7
0x180004b7a  call    __scrt_fastfail
```
