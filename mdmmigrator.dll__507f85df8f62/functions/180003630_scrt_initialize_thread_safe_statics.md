# __scrt_initialize_thread_safe_statics

- ea: `0x180003630`
- end: `0x180003700`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800024c0`
- `0x180002690`
- `0x180002804`
- `0x180003630`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003653`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003668`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003653`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003668`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003680`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003693`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003680`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003693`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800036bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800036bf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003646`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003646`

## string_xrefs

- `0x18000364c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180003661`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_18002B5C8, 0xFA0u);
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
    qword_18002B5F0 = (__int64)ProcAddress;
    qword_18002B5F8 = (__int64)v2;
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
0x180003630  mov     [rsp+arg_0], rbx
0x180003635  push    rdi
0x180003636  sub     rsp, 20h
0x18000363a  mov     edx, 0FA0h; dwSpinCount
0x18000363f  lea     rcx, stru_18002B5C8; lpCriticalSection
0x180003646  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000364c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180003653  call    cs:__imp_GetModuleHandleW
0x180003659  mov     rbx, rax
0x18000365c  test    rax, rax
0x18000365f  jnz     short loc_180003676
0x180003661  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180003668  call    cs:__imp_GetModuleHandleW
0x18000366e  mov     rbx, rax
0x180003671  test    rax, rax
0x180003674  jz      short loc_1800036F5
0x180003676  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000367d  mov     rcx, rbx; hModule
0x180003680  call    cs:__imp_GetProcAddress
0x180003686  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000368d  mov     rcx, rbx; hModule
0x180003690  mov     rdi, rax
0x180003693  call    cs:__imp_GetProcAddress
0x180003699  test    rdi, rdi
0x18000369c  jz      short loc_1800036B3
0x18000369e  test    rax, rax
0x1800036a1  jz      short loc_1800036B3
0x1800036a3  mov     cs:qword_18002B5F0, rdi
0x1800036aa  mov     cs:qword_18002B5F8, rax
0x1800036b1  jmp     short loc_1800036D1
0x1800036b3  xor     r9d, r9d; lpName
0x1800036b6  xor     r8d, r8d; bInitialState
0x1800036b9  xor     ecx, ecx; lpEventAttributes
0x1800036bb  lea     edx, [r9+1]; bManualReset
0x1800036bf  call    cs:__imp_CreateEventW
0x1800036c5  mov     cs:hHandle, rax
0x1800036cc  test    rax, rax
0x1800036cf  jz      short loc_1800036F5
0x1800036d1  xor     ecx, ecx
0x1800036d3  call    __scrt_initialize_onexit_tables
0x1800036d8  test    al, al
0x1800036da  jz      short loc_1800036F5
0x1800036dc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800036e3  call    atexit
0x1800036e8  mov     rbx, [rsp+28h+arg_0]
0x1800036ed  xor     eax, eax
0x1800036ef  add     rsp, 20h
0x1800036f3  pop     rdi
0x1800036f4  retn
0x1800036f5  mov     ecx, 7
0x1800036fa  call    __scrt_fastfail
```
