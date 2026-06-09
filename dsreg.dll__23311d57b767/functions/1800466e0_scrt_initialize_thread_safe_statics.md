# __scrt_initialize_thread_safe_statics

- ea: `0x1800466e0`
- end: `0x1800467b0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800445e8`
- `0x1800447b8`
- `0x1800447e8`
- `0x1800466e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046730`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046743`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046730`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046743`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180046703`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180046718`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180046703`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180046718`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004676f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004676f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800466f6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800466f6`

## string_xrefs

- `0x1800466fc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180046711`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180142008, 0xFA0u);
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
    qword_180142030 = (__int64)ProcAddress;
    qword_180142038 = (__int64)v2;
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
0x1800466e0  mov     [rsp+arg_0], rbx
0x1800466e5  push    rdi
0x1800466e6  sub     rsp, 20h
0x1800466ea  mov     edx, 0FA0h; dwSpinCount
0x1800466ef  lea     rcx, stru_180142008; lpCriticalSection
0x1800466f6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800466fc  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x180046703  call    cs:__imp_GetModuleHandleW
0x180046709  mov     rbx, rax
0x18004670c  test    rax, rax
0x18004670f  jnz     short loc_180046726
0x180046711  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180046718  call    cs:__imp_GetModuleHandleW
0x18004671e  mov     rbx, rax
0x180046721  test    rax, rax
0x180046724  jz      short loc_1800467A5
0x180046726  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18004672d  mov     rcx, rbx; hModule
0x180046730  call    cs:__imp_GetProcAddress
0x180046736  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18004673d  mov     rcx, rbx; hModule
0x180046740  mov     rdi, rax
0x180046743  call    cs:__imp_GetProcAddress
0x180046749  test    rdi, rdi
0x18004674c  jz      short loc_180046763
0x18004674e  test    rax, rax
0x180046751  jz      short loc_180046763
0x180046753  mov     cs:qword_180142030, rdi
0x18004675a  mov     cs:qword_180142038, rax
0x180046761  jmp     short loc_180046781
0x180046763  xor     r9d, r9d; lpName
0x180046766  xor     r8d, r8d; bInitialState
0x180046769  xor     ecx, ecx; lpEventAttributes
0x18004676b  lea     edx, [r9+1]; bManualReset
0x18004676f  call    cs:__imp_CreateEventW
0x180046775  mov     cs:hHandle, rax
0x18004677c  test    rax, rax
0x18004677f  jz      short loc_1800467A5
0x180046781  xor     ecx, ecx
0x180046783  call    __scrt_initialize_onexit_tables
0x180046788  test    al, al
0x18004678a  jz      short loc_1800467A5
0x18004678c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180046793  call    atexit
0x180046798  mov     rbx, [rsp+28h+arg_0]
0x18004679d  xor     eax, eax
0x18004679f  add     rsp, 20h
0x1800467a3  pop     rdi
0x1800467a4  retn
0x1800467a5  mov     ecx, 7
0x1800467aa  call    __scrt_fastfail
```
