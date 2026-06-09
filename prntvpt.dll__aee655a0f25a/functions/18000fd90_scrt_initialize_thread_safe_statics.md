# __scrt_initialize_thread_safe_statics

- ea: `0x18000fd90`
- end: `0x18000fe60`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000fb7c`
- `0x18000fd4c`
- `0x18000fd90`
- `0x18000ffb8`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000fdb3`
- `KERNEL32!GetModuleHandleW` at `0x18000fdc8`
- `KERNEL32!GetModuleHandleW` at `0x18000fdb3`
- `KERNEL32!GetModuleHandleW` at `0x18000fdc8`
- `KERNEL32!GetProcAddress` at `0x18000fde0`
- `KERNEL32!GetProcAddress` at `0x18000fdf3`
- `KERNEL32!GetProcAddress` at `0x18000fde0`
- `KERNEL32!GetProcAddress` at `0x18000fdf3`
- `KERNEL32!CreateEventW` at `0x18000fe1f`
- `KERNEL32!CreateEventW` at `0x18000fe1f`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18000fda6`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18000fda6`

## string_xrefs

- `0x18000fdac`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18000fdc1`: `kernel32.dll`

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
    qword_180031F10 = (__int64)ProcAddress;
    qword_180031F18 = (__int64)v2;
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
0x18000fd90  mov     [rsp+arg_0], rbx
0x18000fd95  push    rdi
0x18000fd96  sub     rsp, 20h
0x18000fd9a  mov     edx, 0FA0h; dwSpinCount
0x18000fd9f  lea     rcx, CriticalSection; lpCriticalSection
0x18000fda6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000fdac  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x18000fdb3  call    cs:__imp_GetModuleHandleW
0x18000fdb9  mov     rbx, rax
0x18000fdbc  test    rax, rax
0x18000fdbf  jnz     short loc_18000FDD6
0x18000fdc1  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x18000fdc8  call    cs:__imp_GetModuleHandleW
0x18000fdce  mov     rbx, rax
0x18000fdd1  test    rax, rax
0x18000fdd4  jz      short loc_18000FE55
0x18000fdd6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18000fddd  mov     rcx, rbx; hModule
0x18000fde0  call    cs:__imp_GetProcAddress
0x18000fde6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000fded  mov     rcx, rbx; hModule
0x18000fdf0  mov     rdi, rax
0x18000fdf3  call    cs:__imp_GetProcAddress
0x18000fdf9  test    rdi, rdi
0x18000fdfc  jz      short loc_18000FE13
0x18000fdfe  test    rax, rax
0x18000fe01  jz      short loc_18000FE13
0x18000fe03  mov     cs:qword_180031F10, rdi
0x18000fe0a  mov     cs:qword_180031F18, rax
0x18000fe11  jmp     short loc_18000FE31
0x18000fe13  xor     r9d, r9d; lpName
0x18000fe16  xor     r8d, r8d; bInitialState
0x18000fe19  xor     ecx, ecx; lpEventAttributes
0x18000fe1b  lea     edx, [r9+1]; bManualReset
0x18000fe1f  call    cs:__imp_CreateEventW
0x18000fe25  mov     cs:hObject, rax
0x18000fe2c  test    rax, rax
0x18000fe2f  jz      short loc_18000FE55
0x18000fe31  xor     ecx, ecx
0x18000fe33  call    __scrt_initialize_onexit_tables
0x18000fe38  test    al, al
0x18000fe3a  jz      short loc_18000FE55
0x18000fe3c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18000fe43  call    atexit
0x18000fe48  mov     rbx, [rsp+28h+arg_0]
0x18000fe4d  xor     eax, eax
0x18000fe4f  add     rsp, 20h
0x18000fe53  pop     rdi
0x18000fe54  retn
0x18000fe55  mov     ecx, 7
0x18000fe5a  call    __scrt_fastfail
```
