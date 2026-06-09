# __scrt_initialize_thread_safe_statics

- ea: `0x180025a60`
- end: `0x180025b30`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18002579c`
- `0x18002596c`
- `0x180025a60`
- `0x1800261c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025a83`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025a98`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025a83`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025a98`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025ab0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025ac3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025ab0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025ac3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180025a76`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180025a76`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180025aef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180025aef`

## string_xrefs

- `0x180025a7c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180025a91`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180095FE8, 0xFA0u);
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
    qword_180096010 = (__int64)ProcAddress;
    qword_180096018 = (__int64)v2;
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
0x180025a60  mov     [rsp+arg_0], rbx
0x180025a65  push    rdi
0x180025a66  sub     rsp, 20h
0x180025a6a  mov     edx, 0FA0h; dwSpinCount
0x180025a6f  lea     rcx, stru_180095FE8; lpCriticalSection
0x180025a76  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180025a7c  lea     rcx, aApiMsWinCoreSy_2; "api-ms-win-core-synch-l1-2-0.dll"
0x180025a83  call    cs:__imp_GetModuleHandleW
0x180025a89  mov     rbx, rax
0x180025a8c  test    rax, rax
0x180025a8f  jnz     short loc_180025AA6
0x180025a91  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x180025a98  call    cs:__imp_GetModuleHandleW
0x180025a9e  mov     rbx, rax
0x180025aa1  test    rax, rax
0x180025aa4  jz      short loc_180025B25
0x180025aa6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x180025aad  mov     rcx, rbx; hModule
0x180025ab0  call    cs:__imp_GetProcAddress
0x180025ab6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180025abd  mov     rcx, rbx; hModule
0x180025ac0  mov     rdi, rax
0x180025ac3  call    cs:__imp_GetProcAddress
0x180025ac9  test    rdi, rdi
0x180025acc  jz      short loc_180025AE3
0x180025ace  test    rax, rax
0x180025ad1  jz      short loc_180025AE3
0x180025ad3  mov     cs:qword_180096010, rdi
0x180025ada  mov     cs:qword_180096018, rax
0x180025ae1  jmp     short loc_180025B01
0x180025ae3  xor     r9d, r9d; lpName
0x180025ae6  xor     r8d, r8d; bInitialState
0x180025ae9  xor     ecx, ecx; lpEventAttributes
0x180025aeb  lea     edx, [r9+1]; bManualReset
0x180025aef  call    cs:__imp_CreateEventW
0x180025af5  mov     cs:hHandle, rax
0x180025afc  test    rax, rax
0x180025aff  jz      short loc_180025B25
0x180025b01  xor     ecx, ecx
0x180025b03  call    __scrt_initialize_onexit_tables
0x180025b08  test    al, al
0x180025b0a  jz      short loc_180025B25
0x180025b0c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180025b13  call    atexit
0x180025b18  mov     rbx, [rsp+28h+arg_0]
0x180025b1d  xor     eax, eax
0x180025b1f  add     rsp, 20h
0x180025b23  pop     rdi
0x180025b24  retn
0x180025b25  mov     ecx, 7
0x180025b2a  call    __scrt_fastfail
```
