# __scrt_initialize_thread_safe_statics

- ea: `0x1800071b0`
- end: `0x180007280`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180006450`
- `0x180006620`
- `0x1800068e8`
- `0x1800071b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007200`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007213`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007200`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007213`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800071d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800071e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800071d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800071e8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800071c6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800071c6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000723f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000723f`

## string_xrefs

- `0x1800071cc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800071e1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180054188, 0xFA0u);
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
    qword_1800541B0 = (__int64)ProcAddress;
    qword_1800541B8 = (__int64)v2;
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
0x1800071b0  mov     [rsp+arg_0], rbx
0x1800071b5  push    rdi
0x1800071b6  sub     rsp, 20h
0x1800071ba  mov     edx, 0FA0h; dwSpinCount
0x1800071bf  lea     rcx, stru_180054188; lpCriticalSection
0x1800071c6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800071cc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800071d3  call    cs:__imp_GetModuleHandleW
0x1800071d9  mov     rbx, rax
0x1800071dc  test    rax, rax
0x1800071df  jnz     short loc_1800071F6
0x1800071e1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800071e8  call    cs:__imp_GetModuleHandleW
0x1800071ee  mov     rbx, rax
0x1800071f1  test    rax, rax
0x1800071f4  jz      short loc_180007275
0x1800071f6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800071fd  mov     rcx, rbx; hModule
0x180007200  call    cs:__imp_GetProcAddress
0x180007206  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000720d  mov     rcx, rbx; hModule
0x180007210  mov     rdi, rax
0x180007213  call    cs:__imp_GetProcAddress
0x180007219  test    rdi, rdi
0x18000721c  jz      short loc_180007233
0x18000721e  test    rax, rax
0x180007221  jz      short loc_180007233
0x180007223  mov     cs:qword_1800541B0, rdi
0x18000722a  mov     cs:qword_1800541B8, rax
0x180007231  jmp     short loc_180007251
0x180007233  xor     r9d, r9d; lpName
0x180007236  xor     r8d, r8d; bInitialState
0x180007239  xor     ecx, ecx; lpEventAttributes
0x18000723b  lea     edx, [r9+1]; bManualReset
0x18000723f  call    cs:__imp_CreateEventW
0x180007245  mov     cs:hObject, rax
0x18000724c  test    rax, rax
0x18000724f  jz      short loc_180007275
0x180007251  xor     ecx, ecx
0x180007253  call    __scrt_initialize_onexit_tables
0x180007258  test    al, al
0x18000725a  jz      short loc_180007275
0x18000725c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180007263  call    atexit
0x180007268  mov     rbx, [rsp+28h+arg_0]
0x18000726d  xor     eax, eax
0x18000726f  add     rsp, 20h
0x180007273  pop     rdi
0x180007274  retn
0x180007275  mov     ecx, 7
0x18000727a  call    __scrt_fastfail
```
