# __scrt_initialize_thread_safe_statics

- ea: `0x140005530`
- end: `0x140005600`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1400034f4`
- `0x1400036c4`
- `0x140003870`
- `0x140005530`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005580`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005593`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005580`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005593`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005553`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005568`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005553`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005568`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400055bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400055bf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140005546`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140005546`

## string_xrefs

- `0x14000554c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x140005561`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_140084CD0, 0xFA0u);
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
    qword_140084CF8 = (__int64)ProcAddress;
    qword_140084D00 = (__int64)v2;
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
0x140005530  mov     [rsp+arg_0], rbx
0x140005535  push    rdi
0x140005536  sub     rsp, 20h
0x14000553a  mov     edx, 0FA0h; dwSpinCount
0x14000553f  lea     rcx, stru_140084CD0; lpCriticalSection
0x140005546  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14000554c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x140005553  call    cs:__imp_GetModuleHandleW
0x140005559  mov     rbx, rax
0x14000555c  test    rax, rax
0x14000555f  jnz     short loc_140005576
0x140005561  lea     rcx, aKernel32Dll; "kernel32.dll"
0x140005568  call    cs:__imp_GetModuleHandleW
0x14000556e  mov     rbx, rax
0x140005571  test    rax, rax
0x140005574  jz      short loc_1400055F5
0x140005576  lea     rdx, ProcName; "SleepConditionVariableCS"
0x14000557d  mov     rcx, rbx; hModule
0x140005580  call    cs:__imp_GetProcAddress
0x140005586  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x14000558d  mov     rcx, rbx; hModule
0x140005590  mov     rdi, rax
0x140005593  call    cs:__imp_GetProcAddress
0x140005599  test    rdi, rdi
0x14000559c  jz      short loc_1400055B3
0x14000559e  test    rax, rax
0x1400055a1  jz      short loc_1400055B3
0x1400055a3  mov     cs:qword_140084CF8, rdi
0x1400055aa  mov     cs:qword_140084D00, rax
0x1400055b1  jmp     short loc_1400055D1
0x1400055b3  xor     r9d, r9d; lpName
0x1400055b6  xor     r8d, r8d; bInitialState
0x1400055b9  xor     ecx, ecx; lpEventAttributes
0x1400055bb  lea     edx, [r9+1]; bManualReset
0x1400055bf  call    cs:__imp_CreateEventW
0x1400055c5  mov     cs:hHandle, rax
0x1400055cc  test    rax, rax
0x1400055cf  jz      short loc_1400055F5
0x1400055d1  xor     ecx, ecx
0x1400055d3  call    __scrt_initialize_onexit_tables
0x1400055d8  test    al, al
0x1400055da  jz      short loc_1400055F5
0x1400055dc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1400055e3  call    atexit
0x1400055e8  mov     rbx, [rsp+28h+arg_0]
0x1400055ed  xor     eax, eax
0x1400055ef  add     rsp, 20h
0x1400055f3  pop     rdi
0x1400055f4  retn
0x1400055f5  mov     ecx, 7
0x1400055fa  call    __scrt_fastfail
```
