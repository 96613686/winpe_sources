# __scrt_initialize_thread_safe_statics

- ea: `0x180003950`
- end: `0x180003a20`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002670`
- `0x180002840`
- `0x180002a24`
- `0x180003950`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003973`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003988`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003973`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003988`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800039a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800039b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800039a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800039b3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800039df`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800039df`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003966`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003966`

## string_xrefs

- `0x18000396c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180003981`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_18003F658, 0xFA0u);
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
    qword_18003F680 = (__int64)ProcAddress;
    qword_18003F688 = (__int64)v2;
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
0x180003950  mov     [rsp+arg_0], rbx
0x180003955  push    rdi
0x180003956  sub     rsp, 20h
0x18000395a  mov     edx, 0FA0h; dwSpinCount
0x18000395f  lea     rcx, stru_18003F658; lpCriticalSection
0x180003966  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000396c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180003973  call    cs:__imp_GetModuleHandleW
0x180003979  mov     rbx, rax
0x18000397c  test    rax, rax
0x18000397f  jnz     short loc_180003996
0x180003981  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180003988  call    cs:__imp_GetModuleHandleW
0x18000398e  mov     rbx, rax
0x180003991  test    rax, rax
0x180003994  jz      short loc_180003A15
0x180003996  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000399d  mov     rcx, rbx; hModule
0x1800039a0  call    cs:__imp_GetProcAddress
0x1800039a6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800039ad  mov     rcx, rbx; hModule
0x1800039b0  mov     rdi, rax
0x1800039b3  call    cs:__imp_GetProcAddress
0x1800039b9  test    rdi, rdi
0x1800039bc  jz      short loc_1800039D3
0x1800039be  test    rax, rax
0x1800039c1  jz      short loc_1800039D3
0x1800039c3  mov     cs:qword_18003F680, rdi
0x1800039ca  mov     cs:qword_18003F688, rax
0x1800039d1  jmp     short loc_1800039F1
0x1800039d3  xor     r9d, r9d; lpName
0x1800039d6  xor     r8d, r8d; bInitialState
0x1800039d9  xor     ecx, ecx; lpEventAttributes
0x1800039db  lea     edx, [r9+1]; bManualReset
0x1800039df  call    cs:__imp_CreateEventW
0x1800039e5  mov     cs:hHandle, rax
0x1800039ec  test    rax, rax
0x1800039ef  jz      short loc_180003A15
0x1800039f1  xor     ecx, ecx
0x1800039f3  call    __scrt_initialize_onexit_tables
0x1800039f8  test    al, al
0x1800039fa  jz      short loc_180003A15
0x1800039fc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180003a03  call    atexit
0x180003a08  mov     rbx, [rsp+28h+arg_0]
0x180003a0d  xor     eax, eax
0x180003a0f  add     rsp, 20h
0x180003a13  pop     rdi
0x180003a14  retn
0x180003a15  mov     ecx, 7
0x180003a1a  call    __scrt_fastfail
```
