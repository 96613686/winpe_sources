# __scrt_initialize_thread_safe_statics

- ea: `0x180002240`
- end: `0x180002310`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001770`
- `0x180001940`
- `0x180001ae0`
- `0x180002240`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180002290`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800022a3`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180002290`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800022a3`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180002263`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180002278`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180002263`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180002278`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002256`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002256`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800022cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800022cf`

## string_xrefs

- `0x18000225c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180002271`: `kernel32.dll`

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
    qword_18001F318 = (__int64)ProcAddress;
    qword_18001F320 = (__int64)v2;
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
0x180002240  mov     [rsp+arg_0], rbx
0x180002245  push    rdi
0x180002246  sub     rsp, 20h
0x18000224a  mov     edx, 0FA0h; dwSpinCount
0x18000224f  lea     rcx, CriticalSection; lpCriticalSection
0x180002256  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000225c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180002263  call    cs:__imp_GetModuleHandleW
0x180002269  mov     rbx, rax
0x18000226c  test    rax, rax
0x18000226f  jnz     short loc_180002286
0x180002271  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180002278  call    cs:__imp_GetModuleHandleW
0x18000227e  mov     rbx, rax
0x180002281  test    rax, rax
0x180002284  jz      short loc_180002305
0x180002286  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000228d  mov     rcx, rbx; hModule
0x180002290  call    cs:__imp_GetProcAddress
0x180002296  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000229d  mov     rcx, rbx; hModule
0x1800022a0  mov     rdi, rax
0x1800022a3  call    cs:__imp_GetProcAddress
0x1800022a9  test    rdi, rdi
0x1800022ac  jz      short loc_1800022C3
0x1800022ae  test    rax, rax
0x1800022b1  jz      short loc_1800022C3
0x1800022b3  mov     cs:qword_18001F318, rdi
0x1800022ba  mov     cs:qword_18001F320, rax
0x1800022c1  jmp     short loc_1800022E1
0x1800022c3  xor     r9d, r9d; lpName
0x1800022c6  xor     r8d, r8d; bInitialState
0x1800022c9  xor     ecx, ecx; lpEventAttributes
0x1800022cb  lea     edx, [r9+1]; bManualReset
0x1800022cf  call    cs:__imp_CreateEventW
0x1800022d5  mov     cs:hHandle, rax
0x1800022dc  test    rax, rax
0x1800022df  jz      short loc_180002305
0x1800022e1  xor     ecx, ecx
0x1800022e3  call    __scrt_initialize_onexit_tables
0x1800022e8  test    al, al
0x1800022ea  jz      short loc_180002305
0x1800022ec  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800022f3  call    atexit
0x1800022f8  mov     rbx, [rsp+28h+arg_0]
0x1800022fd  xor     eax, eax
0x1800022ff  add     rsp, 20h
0x180002303  pop     rdi
0x180002304  retn
0x180002305  mov     ecx, 7
0x18000230a  call    __scrt_fastfail
```
