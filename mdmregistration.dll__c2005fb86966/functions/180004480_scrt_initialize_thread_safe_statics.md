# __scrt_initialize_thread_safe_statics

- ea: `0x180004480`
- end: `0x180004550`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800028f0`
- `0x180002ac0`
- `0x180002c34`
- `0x180004480`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800044a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800044b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800044a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800044b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800044d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800044e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800044d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800044e3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000450f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000450f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004496`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004496`

## string_xrefs

- `0x18000449c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800044b1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180070A58, 0xFA0u);
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
    qword_180070A80 = (__int64)ProcAddress;
    qword_180070A88 = (__int64)v2;
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
0x180004480  mov     [rsp+arg_0], rbx
0x180004485  push    rdi
0x180004486  sub     rsp, 20h
0x18000448a  mov     edx, 0FA0h; dwSpinCount
0x18000448f  lea     rcx, stru_180070A58; lpCriticalSection
0x180004496  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000449c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800044a3  call    cs:__imp_GetModuleHandleW
0x1800044a9  mov     rbx, rax
0x1800044ac  test    rax, rax
0x1800044af  jnz     short loc_1800044C6
0x1800044b1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800044b8  call    cs:__imp_GetModuleHandleW
0x1800044be  mov     rbx, rax
0x1800044c1  test    rax, rax
0x1800044c4  jz      short loc_180004545
0x1800044c6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800044cd  mov     rcx, rbx; hModule
0x1800044d0  call    cs:__imp_GetProcAddress
0x1800044d6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800044dd  mov     rcx, rbx; hModule
0x1800044e0  mov     rdi, rax
0x1800044e3  call    cs:__imp_GetProcAddress
0x1800044e9  test    rdi, rdi
0x1800044ec  jz      short loc_180004503
0x1800044ee  test    rax, rax
0x1800044f1  jz      short loc_180004503
0x1800044f3  mov     cs:qword_180070A80, rdi
0x1800044fa  mov     cs:qword_180070A88, rax
0x180004501  jmp     short loc_180004521
0x180004503  xor     r9d, r9d; lpName
0x180004506  xor     r8d, r8d; bInitialState
0x180004509  xor     ecx, ecx; lpEventAttributes
0x18000450b  lea     edx, [r9+1]; bManualReset
0x18000450f  call    cs:__imp_CreateEventW
0x180004515  mov     cs:hHandle, rax
0x18000451c  test    rax, rax
0x18000451f  jz      short loc_180004545
0x180004521  xor     ecx, ecx
0x180004523  call    __scrt_initialize_onexit_tables
0x180004528  test    al, al
0x18000452a  jz      short loc_180004545
0x18000452c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180004533  call    atexit
0x180004538  mov     rbx, [rsp+28h+arg_0]
0x18000453d  xor     eax, eax
0x18000453f  add     rsp, 20h
0x180004543  pop     rdi
0x180004544  retn
0x180004545  mov     ecx, 7
0x18000454a  call    __scrt_fastfail
```
