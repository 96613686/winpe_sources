# __scrt_initialize_thread_safe_statics

- ea: `0x140002240`
- end: `0x140002310`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140002050`
- `0x140002220`
- `0x140002240`
- `0x14000261c`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140002290`
- `KERNEL32!GetProcAddress` at `0x1400022a3`
- `KERNEL32!GetProcAddress` at `0x140002290`
- `KERNEL32!GetProcAddress` at `0x1400022a3`
- `KERNEL32!GetModuleHandleW` at `0x140002263`
- `KERNEL32!GetModuleHandleW` at `0x140002278`
- `KERNEL32!GetModuleHandleW` at `0x140002263`
- `KERNEL32!GetModuleHandleW` at `0x140002278`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400022cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400022cf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140002256`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140002256`

## string_xrefs

- `0x14000225c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x140002271`: `kernel32.dll`

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
    qword_140016550 = (__int64)ProcAddress;
    qword_140016558 = (__int64)v2;
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
0x140002240  mov     [rsp+arg_0], rbx
0x140002245  push    rdi
0x140002246  sub     rsp, 20h
0x14000224a  mov     edx, 0FA0h; dwSpinCount
0x14000224f  lea     rcx, CriticalSection; lpCriticalSection
0x140002256  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14000225c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x140002263  call    cs:__imp_GetModuleHandleW
0x140002269  mov     rbx, rax
0x14000226c  test    rax, rax
0x14000226f  jnz     short loc_140002286
0x140002271  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x140002278  call    cs:__imp_GetModuleHandleW
0x14000227e  mov     rbx, rax
0x140002281  test    rax, rax
0x140002284  jz      short loc_140002305
0x140002286  lea     rdx, ProcName; "SleepConditionVariableCS"
0x14000228d  mov     rcx, rbx; hModule
0x140002290  call    cs:__imp_GetProcAddress
0x140002296  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x14000229d  mov     rcx, rbx; hModule
0x1400022a0  mov     rdi, rax
0x1400022a3  call    cs:__imp_GetProcAddress
0x1400022a9  test    rdi, rdi
0x1400022ac  jz      short loc_1400022C3
0x1400022ae  test    rax, rax
0x1400022b1  jz      short loc_1400022C3
0x1400022b3  mov     cs:qword_140016550, rdi
0x1400022ba  mov     cs:qword_140016558, rax
0x1400022c1  jmp     short loc_1400022E1
0x1400022c3  xor     r9d, r9d; lpName
0x1400022c6  xor     r8d, r8d; bInitialState
0x1400022c9  xor     ecx, ecx; lpEventAttributes
0x1400022cb  lea     edx, [r9+1]; bManualReset
0x1400022cf  call    cs:__imp_CreateEventW
0x1400022d5  mov     cs:hHandle, rax
0x1400022dc  test    rax, rax
0x1400022df  jz      short loc_140002305
0x1400022e1  xor     ecx, ecx
0x1400022e3  call    __scrt_initialize_onexit_tables
0x1400022e8  test    al, al
0x1400022ea  jz      short loc_140002305
0x1400022ec  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1400022f3  call    atexit
0x1400022f8  mov     rbx, [rsp+28h+arg_0]
0x1400022fd  xor     eax, eax
0x1400022ff  add     rsp, 20h
0x140002303  pop     rdi
0x140002304  retn
0x140002305  mov     ecx, 7
0x14000230a  call    __scrt_fastfail
```
