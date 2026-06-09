# __scrt_initialize_thread_safe_statics

- ea: `0x180002630`
- end: `0x180002700`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001e54`
- `0x180002024`
- `0x180002054`
- `0x180002630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800026bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800026bf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002646`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002646`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002680`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002693`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002680`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002693`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002653`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002668`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002653`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002668`

## string_xrefs

- `0x18000264c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180002661`: `kernel32.dll`

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
    qword_18001C700 = (__int64)ProcAddress;
    qword_18001C708 = (__int64)v2;
  }
  else
  {
    hObject = CreateEventW(0, 1, 0, 0);
    if ( !hObject )
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
0x180002630  mov     [rsp+arg_0], rbx
0x180002635  push    rdi
0x180002636  sub     rsp, 20h
0x18000263a  mov     edx, 0FA0h; dwSpinCount
0x18000263f  lea     rcx, CriticalSection; lpCriticalSection
0x180002646  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000264c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180002653  call    cs:__imp_GetModuleHandleW
0x180002659  mov     rbx, rax
0x18000265c  test    rax, rax
0x18000265f  jnz     short loc_180002676
0x180002661  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180002668  call    cs:__imp_GetModuleHandleW
0x18000266e  mov     rbx, rax
0x180002671  test    rax, rax
0x180002674  jz      short loc_1800026F5
0x180002676  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000267d  mov     rcx, rbx; hModule
0x180002680  call    cs:__imp_GetProcAddress
0x180002686  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000268d  mov     rcx, rbx; hModule
0x180002690  mov     rdi, rax
0x180002693  call    cs:__imp_GetProcAddress
0x180002699  test    rdi, rdi
0x18000269c  jz      short loc_1800026B3
0x18000269e  test    rax, rax
0x1800026a1  jz      short loc_1800026B3
0x1800026a3  mov     cs:qword_18001C700, rdi
0x1800026aa  mov     cs:qword_18001C708, rax
0x1800026b1  jmp     short loc_1800026D1
0x1800026b3  xor     r9d, r9d; lpName
0x1800026b6  xor     r8d, r8d; bInitialState
0x1800026b9  xor     ecx, ecx; lpEventAttributes
0x1800026bb  lea     edx, [r9+1]; bManualReset
0x1800026bf  call    cs:__imp_CreateEventW
0x1800026c5  mov     cs:hObject, rax
0x1800026cc  test    rax, rax
0x1800026cf  jz      short loc_1800026F5
0x1800026d1  xor     ecx, ecx
0x1800026d3  call    __scrt_initialize_onexit_tables
0x1800026d8  test    al, al
0x1800026da  jz      short loc_1800026F5
0x1800026dc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800026e3  call    atexit
0x1800026e8  mov     rbx, [rsp+28h+arg_0]
0x1800026ed  xor     eax, eax
0x1800026ef  add     rsp, 20h
0x1800026f3  pop     rdi
0x1800026f4  retn
0x1800026f5  mov     ecx, 7
0x1800026fa  call    __scrt_fastfail
```
