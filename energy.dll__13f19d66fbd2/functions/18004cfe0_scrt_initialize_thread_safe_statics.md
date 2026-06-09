# __scrt_initialize_thread_safe_statics

- ea: `0x18004cfe0`
- end: `0x18004d0b0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18004cca8`
- `0x18004ce78`
- `0x18004cfe0`
- `0x18004d6ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004d06f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004d06f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18004cff6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18004cff6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004d003`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004d018`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004d003`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004d018`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004d030`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004d043`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004d030`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004d043`

## string_xrefs

- `0x18004cffc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18004d011`: `kernel32.dll`

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
    qword_1800C8758 = (__int64)ProcAddress;
    qword_1800C8760 = (__int64)v2;
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
0x18004cfe0  mov     [rsp+arg_0], rbx
0x18004cfe5  push    rdi
0x18004cfe6  sub     rsp, 20h
0x18004cfea  mov     edx, 0FA0h; dwSpinCount
0x18004cfef  lea     rcx, CriticalSection; lpCriticalSection
0x18004cff6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18004cffc  lea     rcx, aApiMsWinCoreSy_2; "api-ms-win-core-synch-l1-2-0.dll"
0x18004d003  call    cs:__imp_GetModuleHandleW
0x18004d009  mov     rbx, rax
0x18004d00c  test    rax, rax
0x18004d00f  jnz     short loc_18004D026
0x18004d011  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18004d018  call    cs:__imp_GetModuleHandleW
0x18004d01e  mov     rbx, rax
0x18004d021  test    rax, rax
0x18004d024  jz      short loc_18004D0A5
0x18004d026  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18004d02d  mov     rcx, rbx; hModule
0x18004d030  call    cs:__imp_GetProcAddress
0x18004d036  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18004d03d  mov     rcx, rbx; hModule
0x18004d040  mov     rdi, rax
0x18004d043  call    cs:__imp_GetProcAddress
0x18004d049  test    rdi, rdi
0x18004d04c  jz      short loc_18004D063
0x18004d04e  test    rax, rax
0x18004d051  jz      short loc_18004D063
0x18004d053  mov     cs:qword_1800C8758, rdi
0x18004d05a  mov     cs:qword_1800C8760, rax
0x18004d061  jmp     short loc_18004D081
0x18004d063  xor     r9d, r9d; lpName
0x18004d066  xor     r8d, r8d; bInitialState
0x18004d069  xor     ecx, ecx; lpEventAttributes
0x18004d06b  lea     edx, [r9+1]; bManualReset
0x18004d06f  call    cs:__imp_CreateEventW
0x18004d075  mov     cs:hHandle, rax
0x18004d07c  test    rax, rax
0x18004d07f  jz      short loc_18004D0A5
0x18004d081  xor     ecx, ecx
0x18004d083  call    __scrt_initialize_onexit_tables
0x18004d088  test    al, al
0x18004d08a  jz      short loc_18004D0A5
0x18004d08c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18004d093  call    atexit
0x18004d098  mov     rbx, [rsp+28h+arg_0]
0x18004d09d  xor     eax, eax
0x18004d09f  add     rsp, 20h
0x18004d0a3  pop     rdi
0x18004d0a4  retn
0x18004d0a5  mov     ecx, 7
0x18004d0aa  call    __scrt_fastfail
```
