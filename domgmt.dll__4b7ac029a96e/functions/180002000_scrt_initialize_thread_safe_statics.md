# __scrt_initialize_thread_safe_statics

- ea: `0x180002000`
- end: `0x1800020d0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001d80`
- `0x180001f50`
- `0x180002000`
- `0x180002498`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002050`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002063`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002050`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002063`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002023`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002038`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002023`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002038`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000208f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000208f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002016`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002016`

## string_xrefs

- `0x18000201c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180002031`: `kernel32.dll`

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
    qword_180018610 = (__int64)ProcAddress;
    qword_180018618 = (__int64)v2;
  }
  else
  {
    hHandle = CreateEventW(0, 1, 0, 0);
    if ( !hHandle )
      goto LABEL_9;
  }
  if ( !(unsigned __int8)_scrt_initialize_onexit_tables(0) )
LABEL_9:
    _scrt_fastfail(7u);
  atexit(_scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x180002000  mov     [rsp+arg_0], rbx
0x180002005  push    rdi
0x180002006  sub     rsp, 20h
0x18000200a  mov     edx, 0FA0h; dwSpinCount
0x18000200f  lea     rcx, CriticalSection; lpCriticalSection
0x180002016  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000201c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180002023  call    cs:__imp_GetModuleHandleW
0x180002029  mov     rbx, rax
0x18000202c  test    rax, rax
0x18000202f  jnz     short loc_180002046
0x180002031  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180002038  call    cs:__imp_GetModuleHandleW
0x18000203e  mov     rbx, rax
0x180002041  test    rax, rax
0x180002044  jz      short loc_1800020C5
0x180002046  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000204d  mov     rcx, rbx; hModule
0x180002050  call    cs:__imp_GetProcAddress
0x180002056  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000205d  mov     rcx, rbx; hModule
0x180002060  mov     rdi, rax
0x180002063  call    cs:__imp_GetProcAddress
0x180002069  test    rdi, rdi
0x18000206c  jz      short loc_180002083
0x18000206e  test    rax, rax
0x180002071  jz      short loc_180002083
0x180002073  mov     cs:qword_180018610, rdi
0x18000207a  mov     cs:qword_180018618, rax
0x180002081  jmp     short loc_1800020A1
0x180002083  xor     r9d, r9d; lpName
0x180002086  xor     r8d, r8d; bInitialState
0x180002089  xor     ecx, ecx; lpEventAttributes
0x18000208b  lea     edx, [r9+1]; bManualReset
0x18000208f  call    cs:__imp_CreateEventW
0x180002095  mov     cs:hHandle, rax
0x18000209c  test    rax, rax
0x18000209f  jz      short loc_1800020C5
0x1800020a1  xor     ecx, ecx
0x1800020a3  call    __scrt_initialize_onexit_tables
0x1800020a8  test    al, al
0x1800020aa  jz      short loc_1800020C5
0x1800020ac  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800020b3  call    atexit
0x1800020b8  mov     rbx, [rsp+28h+arg_0]
0x1800020bd  xor     eax, eax
0x1800020bf  add     rsp, 20h
0x1800020c3  pop     rdi
0x1800020c4  retn
0x1800020c5  mov     ecx, 7
0x1800020ca  call    __scrt_fastfail
```
