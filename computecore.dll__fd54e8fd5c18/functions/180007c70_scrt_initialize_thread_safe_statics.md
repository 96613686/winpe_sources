# __scrt_initialize_thread_safe_statics

- ea: `0x180007c70`
- end: `0x180007d40`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180006a08`
- `0x180006bd8`
- `0x180006f30`
- `0x180007c70`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007c93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007ca8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007c93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007ca8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007cc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007cd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007cc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007cd3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180007c86`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180007c86`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007cff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007cff`

## string_xrefs

- `0x180007c8c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180007ca1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800E3CC0, 0xFA0u);
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
    qword_1800E3CE8 = (__int64)ProcAddress;
    qword_1800E3CF0 = (__int64)v2;
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
0x180007c70  mov     [rsp+arg_0], rbx
0x180007c75  push    rdi
0x180007c76  sub     rsp, 20h
0x180007c7a  mov     edx, 0FA0h; dwSpinCount
0x180007c7f  lea     rcx, stru_1800E3CC0; lpCriticalSection
0x180007c86  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180007c8c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180007c93  call    cs:__imp_GetModuleHandleW
0x180007c99  mov     rbx, rax
0x180007c9c  test    rax, rax
0x180007c9f  jnz     short loc_180007CB6
0x180007ca1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180007ca8  call    cs:__imp_GetModuleHandleW
0x180007cae  mov     rbx, rax
0x180007cb1  test    rax, rax
0x180007cb4  jz      short loc_180007D35
0x180007cb6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180007cbd  mov     rcx, rbx; hModule
0x180007cc0  call    cs:__imp_GetProcAddress
0x180007cc6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180007ccd  mov     rcx, rbx; hModule
0x180007cd0  mov     rdi, rax
0x180007cd3  call    cs:__imp_GetProcAddress
0x180007cd9  test    rdi, rdi
0x180007cdc  jz      short loc_180007CF3
0x180007cde  test    rax, rax
0x180007ce1  jz      short loc_180007CF3
0x180007ce3  mov     cs:qword_1800E3CE8, rdi
0x180007cea  mov     cs:qword_1800E3CF0, rax
0x180007cf1  jmp     short loc_180007D11
0x180007cf3  xor     r9d, r9d; lpName
0x180007cf6  xor     r8d, r8d; bInitialState
0x180007cf9  xor     ecx, ecx; lpEventAttributes
0x180007cfb  lea     edx, [r9+1]; bManualReset
0x180007cff  call    cs:__imp_CreateEventW
0x180007d05  mov     cs:hHandle, rax
0x180007d0c  test    rax, rax
0x180007d0f  jz      short loc_180007D35
0x180007d11  xor     ecx, ecx
0x180007d13  call    __scrt_initialize_onexit_tables
0x180007d18  test    al, al
0x180007d1a  jz      short loc_180007D35
0x180007d1c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180007d23  call    atexit
0x180007d28  mov     rbx, [rsp+28h+arg_0]
0x180007d2d  xor     eax, eax
0x180007d2f  add     rsp, 20h
0x180007d33  pop     rdi
0x180007d34  retn
0x180007d35  mov     ecx, 7
0x180007d3a  call    __scrt_fastfail
```
