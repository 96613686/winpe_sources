# __scrt_initialize_thread_safe_statics

- ea: `0x1800060e0`
- end: `0x1800061b0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180003c08`
- `0x180003dd8`
- `0x180003f10`
- `0x1800060e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006103`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006118`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006103`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006118`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006130`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006143`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006130`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006143`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800060f6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800060f6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000616f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000616f`

## string_xrefs

- `0x1800060fc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180006111`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800509F8, 0xFA0u);
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
    qword_180050A20 = (__int64)ProcAddress;
    qword_180050A28 = (__int64)v2;
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
0x1800060e0  mov     [rsp+arg_0], rbx
0x1800060e5  push    rdi
0x1800060e6  sub     rsp, 20h
0x1800060ea  mov     edx, 0FA0h; dwSpinCount
0x1800060ef  lea     rcx, stru_1800509F8; lpCriticalSection
0x1800060f6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800060fc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180006103  call    cs:__imp_GetModuleHandleW
0x180006109  mov     rbx, rax
0x18000610c  test    rax, rax
0x18000610f  jnz     short loc_180006126
0x180006111  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180006118  call    cs:__imp_GetModuleHandleW
0x18000611e  mov     rbx, rax
0x180006121  test    rax, rax
0x180006124  jz      short loc_1800061A5
0x180006126  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000612d  mov     rcx, rbx; hModule
0x180006130  call    cs:__imp_GetProcAddress
0x180006136  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000613d  mov     rcx, rbx; hModule
0x180006140  mov     rdi, rax
0x180006143  call    cs:__imp_GetProcAddress
0x180006149  test    rdi, rdi
0x18000614c  jz      short loc_180006163
0x18000614e  test    rax, rax
0x180006151  jz      short loc_180006163
0x180006153  mov     cs:qword_180050A20, rdi
0x18000615a  mov     cs:qword_180050A28, rax
0x180006161  jmp     short loc_180006181
0x180006163  xor     r9d, r9d; lpName
0x180006166  xor     r8d, r8d; bInitialState
0x180006169  xor     ecx, ecx; lpEventAttributes
0x18000616b  lea     edx, [r9+1]; bManualReset
0x18000616f  call    cs:__imp_CreateEventW
0x180006175  mov     cs:hHandle, rax
0x18000617c  test    rax, rax
0x18000617f  jz      short loc_1800061A5
0x180006181  xor     ecx, ecx
0x180006183  call    __scrt_initialize_onexit_tables
0x180006188  test    al, al
0x18000618a  jz      short loc_1800061A5
0x18000618c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180006193  call    atexit
0x180006198  mov     rbx, [rsp+28h+arg_0]
0x18000619d  xor     eax, eax
0x18000619f  add     rsp, 20h
0x1800061a3  pop     rdi
0x1800061a4  retn
0x1800061a5  mov     ecx, 7
0x1800061aa  call    __scrt_fastfail
```
