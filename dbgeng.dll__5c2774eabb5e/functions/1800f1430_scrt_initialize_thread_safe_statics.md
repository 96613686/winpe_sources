# __scrt_initialize_thread_safe_statics

- ea: `0x1800f1430`
- end: `0x1800f1500`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800f11fc`
- `0x1800f13cc`
- `0x1800f1430`
- `0x1800f1be4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800f1453`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800f1468`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800f1453`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800f1468`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800f1480`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800f1493`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800f1480`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800f1493`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f14bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f14bf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800f1446`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800f1446`

## string_xrefs

- `0x1800f144c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800f1461`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1807C1358, 0xFA0u);
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
    qword_1807C1380 = (__int64)ProcAddress;
    qword_1807C1388 = (__int64)v2;
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
0x1800f1430  mov     [rsp+arg_0], rbx
0x1800f1435  push    rdi
0x1800f1436  sub     rsp, 20h
0x1800f143a  mov     edx, 0FA0h; dwSpinCount
0x1800f143f  lea     rcx, stru_1807C1358; lpCriticalSection
0x1800f1446  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800f144c  lea     rcx, aApiMsWinCoreSy_2; "api-ms-win-core-synch-l1-2-0.dll"
0x1800f1453  call    cs:__imp_GetModuleHandleW
0x1800f1459  mov     rbx, rax
0x1800f145c  test    rax, rax
0x1800f145f  jnz     short loc_1800F1476
0x1800f1461  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1800f1468  call    cs:__imp_GetModuleHandleW
0x1800f146e  mov     rbx, rax
0x1800f1471  test    rax, rax
0x1800f1474  jz      short loc_1800F14F5
0x1800f1476  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x1800f147d  mov     rcx, rbx; hModule
0x1800f1480  call    cs:__imp_GetProcAddress
0x1800f1486  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800f148d  mov     rcx, rbx; hModule
0x1800f1490  mov     rdi, rax
0x1800f1493  call    cs:__imp_GetProcAddress
0x1800f1499  test    rdi, rdi
0x1800f149c  jz      short loc_1800F14B3
0x1800f149e  test    rax, rax
0x1800f14a1  jz      short loc_1800F14B3
0x1800f14a3  mov     cs:qword_1807C1380, rdi
0x1800f14aa  mov     cs:qword_1807C1388, rax
0x1800f14b1  jmp     short loc_1800F14D1
0x1800f14b3  xor     r9d, r9d; lpName
0x1800f14b6  xor     r8d, r8d; bInitialState
0x1800f14b9  xor     ecx, ecx; lpEventAttributes
0x1800f14bb  lea     edx, [r9+1]; bManualReset
0x1800f14bf  call    cs:__imp_CreateEventW
0x1800f14c5  mov     cs:hHandle, rax
0x1800f14cc  test    rax, rax
0x1800f14cf  jz      short loc_1800F14F5
0x1800f14d1  xor     ecx, ecx
0x1800f14d3  call    __scrt_initialize_onexit_tables
0x1800f14d8  test    al, al
0x1800f14da  jz      short loc_1800F14F5
0x1800f14dc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800f14e3  call    atexit
0x1800f14e8  mov     rbx, [rsp+28h+arg_0]
0x1800f14ed  xor     eax, eax
0x1800f14ef  add     rsp, 20h
0x1800f14f3  pop     rdi
0x1800f14f4  retn
0x1800f14f5  mov     ecx, 7
0x1800f14fa  call    __scrt_fastfail
```
