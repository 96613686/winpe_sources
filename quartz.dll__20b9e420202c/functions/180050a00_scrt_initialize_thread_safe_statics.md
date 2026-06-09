# __scrt_initialize_thread_safe_statics

- ea: `0x180050a00`
- end: `0x180050ad0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180038b88`
- `0x180038d58`
- `0x180038d88`
- `0x180050a00`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180050a16`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180050a16`
- `KERNEL32!CreateEventW` at `0x180050a8f`
- `KERNEL32!CreateEventW` at `0x180050a8f`
- `KERNEL32!GetProcAddress` at `0x180050a50`
- `KERNEL32!GetProcAddress` at `0x180050a63`
- `KERNEL32!GetProcAddress` at `0x180050a50`
- `KERNEL32!GetProcAddress` at `0x180050a63`
- `KERNEL32!GetModuleHandleW` at `0x180050a23`
- `KERNEL32!GetModuleHandleW` at `0x180050a38`
- `KERNEL32!GetModuleHandleW` at `0x180050a23`
- `KERNEL32!GetModuleHandleW` at `0x180050a38`

## string_xrefs

- `0x180050a1c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180050a31`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_18019E618, 0xFA0u);
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
    qword_18019E640 = (__int64)ProcAddress;
    qword_18019E648 = (__int64)v2;
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
0x180050a00  mov     [rsp+arg_0], rbx
0x180050a05  push    rdi
0x180050a06  sub     rsp, 20h
0x180050a0a  mov     edx, 0FA0h; dwSpinCount
0x180050a0f  lea     rcx, stru_18019E618; lpCriticalSection
0x180050a16  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180050a1c  lea     rcx, aApiMsWinCoreSy_1; "api-ms-win-core-synch-l1-2-0.dll"
0x180050a23  call    cs:__imp_GetModuleHandleW
0x180050a29  mov     rbx, rax
0x180050a2c  test    rax, rax
0x180050a2f  jnz     short loc_180050A46
0x180050a31  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x180050a38  call    cs:__imp_GetModuleHandleW
0x180050a3e  mov     rbx, rax
0x180050a41  test    rax, rax
0x180050a44  jz      short loc_180050AC5
0x180050a46  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x180050a4d  mov     rcx, rbx; hModule
0x180050a50  call    cs:__imp_GetProcAddress
0x180050a56  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180050a5d  mov     rcx, rbx; hModule
0x180050a60  mov     rdi, rax
0x180050a63  call    cs:__imp_GetProcAddress
0x180050a69  test    rdi, rdi
0x180050a6c  jz      short loc_180050A83
0x180050a6e  test    rax, rax
0x180050a71  jz      short loc_180050A83
0x180050a73  mov     cs:qword_18019E640, rdi
0x180050a7a  mov     cs:qword_18019E648, rax
0x180050a81  jmp     short loc_180050AA1
0x180050a83  xor     r9d, r9d; lpName
0x180050a86  xor     r8d, r8d; bInitialState
0x180050a89  xor     ecx, ecx; lpEventAttributes
0x180050a8b  lea     edx, [r9+1]; bManualReset
0x180050a8f  call    cs:__imp_CreateEventW
0x180050a95  mov     cs:hHandle, rax
0x180050a9c  test    rax, rax
0x180050a9f  jz      short loc_180050AC5
0x180050aa1  xor     ecx, ecx
0x180050aa3  call    __scrt_initialize_onexit_tables
0x180050aa8  test    al, al
0x180050aaa  jz      short loc_180050AC5
0x180050aac  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180050ab3  call    atexit
0x180050ab8  mov     rbx, [rsp+28h+arg_0]
0x180050abd  xor     eax, eax
0x180050abf  add     rsp, 20h
0x180050ac3  pop     rdi
0x180050ac4  retn
0x180050ac5  mov     ecx, 7
0x180050aca  call    __scrt_fastfail
```
