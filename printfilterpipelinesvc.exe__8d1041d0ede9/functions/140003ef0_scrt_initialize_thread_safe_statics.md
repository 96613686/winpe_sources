# __scrt_initialize_thread_safe_statics

- ea: `0x140003ef0`
- end: `0x140003fc0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140002250`
- `0x140002420`
- `0x1400025d4`
- `0x140003ef0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140003f40`
- `KERNEL32!GetProcAddress` at `0x140003f53`
- `KERNEL32!GetProcAddress` at `0x140003f40`
- `KERNEL32!GetProcAddress` at `0x140003f53`
- `KERNEL32!GetModuleHandleW` at `0x140003f13`
- `KERNEL32!GetModuleHandleW` at `0x140003f28`
- `KERNEL32!GetModuleHandleW` at `0x140003f13`
- `KERNEL32!GetModuleHandleW` at `0x140003f28`
- `KERNEL32!CreateEventW` at `0x140003f7f`
- `KERNEL32!CreateEventW` at `0x140003f7f`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x140003f06`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x140003f06`

## string_xrefs

- `0x140003f0c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x140003f21`: `kernel32.dll`

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
    qword_140080B38 = (__int64)ProcAddress;
    qword_140080B40 = (__int64)v2;
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
0x140003ef0  mov     [rsp+arg_0], rbx
0x140003ef5  push    rdi
0x140003ef6  sub     rsp, 20h
0x140003efa  mov     edx, 0FA0h; dwSpinCount
0x140003eff  lea     rcx, CriticalSection; lpCriticalSection
0x140003f06  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x140003f0c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x140003f13  call    cs:__imp_GetModuleHandleW
0x140003f19  mov     rbx, rax
0x140003f1c  test    rax, rax
0x140003f1f  jnz     short loc_140003F36
0x140003f21  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x140003f28  call    cs:__imp_GetModuleHandleW
0x140003f2e  mov     rbx, rax
0x140003f31  test    rax, rax
0x140003f34  jz      short loc_140003FB5
0x140003f36  lea     rdx, ProcName; "SleepConditionVariableCS"
0x140003f3d  mov     rcx, rbx; hModule
0x140003f40  call    cs:__imp_GetProcAddress
0x140003f46  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x140003f4d  mov     rcx, rbx; hModule
0x140003f50  mov     rdi, rax
0x140003f53  call    cs:__imp_GetProcAddress
0x140003f59  test    rdi, rdi
0x140003f5c  jz      short loc_140003F73
0x140003f5e  test    rax, rax
0x140003f61  jz      short loc_140003F73
0x140003f63  mov     cs:qword_140080B38, rdi
0x140003f6a  mov     cs:qword_140080B40, rax
0x140003f71  jmp     short loc_140003F91
0x140003f73  xor     r9d, r9d; lpName
0x140003f76  xor     r8d, r8d; bInitialState
0x140003f79  xor     ecx, ecx; lpEventAttributes
0x140003f7b  lea     edx, [r9+1]; bManualReset
0x140003f7f  call    cs:__imp_CreateEventW
0x140003f85  mov     cs:hHandle, rax
0x140003f8c  test    rax, rax
0x140003f8f  jz      short loc_140003FB5
0x140003f91  xor     ecx, ecx
0x140003f93  call    __scrt_initialize_onexit_tables
0x140003f98  test    al, al
0x140003f9a  jz      short loc_140003FB5
0x140003f9c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x140003fa3  call    atexit
0x140003fa8  mov     rbx, [rsp+28h+arg_0]
0x140003fad  xor     eax, eax
0x140003faf  add     rsp, 20h
0x140003fb3  pop     rdi
0x140003fb4  retn
0x140003fb5  mov     ecx, 7
0x140003fba  call    __scrt_fastfail
```
