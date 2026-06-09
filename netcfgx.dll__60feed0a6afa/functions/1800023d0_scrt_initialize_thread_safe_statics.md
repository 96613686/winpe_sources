# __scrt_initialize_thread_safe_statics

- ea: `0x1800023d0`
- end: `0x1800024a0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800021dc`
- `0x1800023ac`
- `0x1800023d0`
- `0x1800025f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000245f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000245f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800023e6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800023e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800023f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002408`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800023f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002408`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002420`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002433`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002420`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002433`

## string_xrefs

- `0x1800023ec`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180002401`: `kernel32.dll`

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
    qword_18001A550 = (__int64)ProcAddress;
    qword_18001A558 = (__int64)v2;
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
0x1800023d0  mov     [rsp+arg_0], rbx
0x1800023d5  push    rdi
0x1800023d6  sub     rsp, 20h
0x1800023da  mov     edx, 0FA0h; dwSpinCount
0x1800023df  lea     rcx, CriticalSection; lpCriticalSection
0x1800023e6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800023ec  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800023f3  call    cs:__imp_GetModuleHandleW
0x1800023f9  mov     rbx, rax
0x1800023fc  test    rax, rax
0x1800023ff  jnz     short loc_180002416
0x180002401  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180002408  call    cs:__imp_GetModuleHandleW
0x18000240e  mov     rbx, rax
0x180002411  test    rax, rax
0x180002414  jz      short loc_180002495
0x180002416  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000241d  mov     rcx, rbx; hModule
0x180002420  call    cs:__imp_GetProcAddress
0x180002426  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000242d  mov     rcx, rbx; hModule
0x180002430  mov     rdi, rax
0x180002433  call    cs:__imp_GetProcAddress
0x180002439  test    rdi, rdi
0x18000243c  jz      short loc_180002453
0x18000243e  test    rax, rax
0x180002441  jz      short loc_180002453
0x180002443  mov     cs:qword_18001A550, rdi
0x18000244a  mov     cs:qword_18001A558, rax
0x180002451  jmp     short loc_180002471
0x180002453  xor     r9d, r9d; lpName
0x180002456  xor     r8d, r8d; bInitialState
0x180002459  xor     ecx, ecx; lpEventAttributes
0x18000245b  lea     edx, [r9+1]; bManualReset
0x18000245f  call    cs:__imp_CreateEventW
0x180002465  mov     cs:hObject, rax
0x18000246c  test    rax, rax
0x18000246f  jz      short loc_180002495
0x180002471  xor     ecx, ecx
0x180002473  call    __scrt_initialize_onexit_tables
0x180002478  test    al, al
0x18000247a  jz      short loc_180002495
0x18000247c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180002483  call    atexit
0x180002488  mov     rbx, [rsp+28h+arg_0]
0x18000248d  xor     eax, eax
0x18000248f  add     rsp, 20h
0x180002493  pop     rdi
0x180002494  retn
0x180002495  mov     ecx, 7
0x18000249a  call    __scrt_fastfail
```
