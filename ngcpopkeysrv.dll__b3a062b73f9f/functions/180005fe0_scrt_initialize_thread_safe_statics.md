# __scrt_initialize_thread_safe_statics

- ea: `0x180005fe0`
- end: `0x1800060b0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180004fc0`
- `0x180005190`
- `0x180005348`
- `0x180005fe0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006003`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006018`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006003`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006018`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006030`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006043`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006030`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006043`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000606f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000606f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180005ff6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180005ff6`

## string_xrefs

- `0x180005ffc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180006011`: `kernel32.dll`

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
    qword_1800375F8 = (__int64)ProcAddress;
    qword_180037600 = (__int64)v2;
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
0x180005fe0  mov     [rsp+arg_0], rbx
0x180005fe5  push    rdi
0x180005fe6  sub     rsp, 20h
0x180005fea  mov     edx, 0FA0h; dwSpinCount
0x180005fef  lea     rcx, CriticalSection; lpCriticalSection
0x180005ff6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180005ffc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180006003  call    cs:__imp_GetModuleHandleW
0x180006009  mov     rbx, rax
0x18000600c  test    rax, rax
0x18000600f  jnz     short loc_180006026
0x180006011  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180006018  call    cs:__imp_GetModuleHandleW
0x18000601e  mov     rbx, rax
0x180006021  test    rax, rax
0x180006024  jz      short loc_1800060A5
0x180006026  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000602d  mov     rcx, rbx; hModule
0x180006030  call    cs:__imp_GetProcAddress
0x180006036  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000603d  mov     rcx, rbx; hModule
0x180006040  mov     rdi, rax
0x180006043  call    cs:__imp_GetProcAddress
0x180006049  test    rdi, rdi
0x18000604c  jz      short loc_180006063
0x18000604e  test    rax, rax
0x180006051  jz      short loc_180006063
0x180006053  mov     cs:qword_1800375F8, rdi
0x18000605a  mov     cs:qword_180037600, rax
0x180006061  jmp     short loc_180006081
0x180006063  xor     r9d, r9d; lpName
0x180006066  xor     r8d, r8d; bInitialState
0x180006069  xor     ecx, ecx; lpEventAttributes
0x18000606b  lea     edx, [r9+1]; bManualReset
0x18000606f  call    cs:__imp_CreateEventW
0x180006075  mov     cs:hHandle, rax
0x18000607c  test    rax, rax
0x18000607f  jz      short loc_1800060A5
0x180006081  xor     ecx, ecx
0x180006083  call    __scrt_initialize_onexit_tables
0x180006088  test    al, al
0x18000608a  jz      short loc_1800060A5
0x18000608c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180006093  call    atexit
0x180006098  mov     rbx, [rsp+28h+arg_0]
0x18000609d  xor     eax, eax
0x18000609f  add     rsp, 20h
0x1800060a3  pop     rdi
0x1800060a4  retn
0x1800060a5  mov     ecx, 7
0x1800060aa  call    __scrt_fastfail
```
