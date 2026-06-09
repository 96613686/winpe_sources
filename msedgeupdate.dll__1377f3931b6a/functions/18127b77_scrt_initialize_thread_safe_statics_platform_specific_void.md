# __scrt_initialize_thread_safe_statics_platform_specific(void)

- ea: `0x18127b77`
- end: `0x18127bf8`
- name: `?__scrt_initialize_thread_safe_statics_platform_specific@@YAXXZ`
- size: `129`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18127b50`

## callees

- `0x18127b77`
- `0x18128693`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18127b83`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18127b83`
- `KERNEL32!GetProcAddress` at `0x18127bb1`
- `KERNEL32!GetProcAddress` at `0x18127bbf`
- `KERNEL32!GetProcAddress` at `0x18127bb1`
- `KERNEL32!GetProcAddress` at `0x18127bbf`
- `KERNEL32!GetModuleHandleW` at `0x18127b8e`
- `KERNEL32!GetModuleHandleW` at `0x18127b9f`
- `KERNEL32!GetModuleHandleW` at `0x18127b8e`
- `KERNEL32!GetModuleHandleW` at `0x18127b9f`
- `KERNEL32!CreateEventW` at `0x18127be2`
- `KERNEL32!CreateEventW` at `0x18127be2`

## string_xrefs

- `0x18127b89`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18127b9a`: `kernel32.dll`

## pseudocode

```c
void __cdecl __scrt_initialize_thread_safe_statics_platform_specific()
{
  HMODULE ModuleHandleW; // esi
  BOOL (__stdcall *SleepConditionVariableCS)(PCONDITION_VARIABLE, PCRITICAL_SECTION, DWORD); // edi
  void (__stdcall *WakeAllConditionVariable)(PCONDITION_VARIABLE); // eax

  InitializeCriticalSectionAndSpinCount(&stru_181ECA0C, 0xFA0u);
  ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-synch-l1-2-0.dll");
  if ( !ModuleHandleW )
  {
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    if ( !ModuleHandleW )
      goto LABEL_8;
  }
  SleepConditionVariableCS = (BOOL (__stdcall *)(PCONDITION_VARIABLE, PCRITICAL_SECTION, DWORD))GetProcAddress(
                                                                                                  ModuleHandleW,
                                                                                                  "SleepConditionVariableCS");
  WakeAllConditionVariable = (void (__stdcall *)(PCONDITION_VARIABLE))GetProcAddress(
                                                                        ModuleHandleW,
                                                                        "WakeAllConditionVariable");
  if ( SleepConditionVariableCS && WakeAllConditionVariable )
  {
    dword_181ECA24 = (int)SleepConditionVariableCS;
    dword_181ECA28 = (int)WakeAllConditionVariable;
    return;
  }
  hObject = CreateEventW(0, 1, 0, 0);
  if ( !hObject )
  {
LABEL_8:
    __scrt_fastfail(7);
    JUMPOUT(0x18127BF8);
  }
}

```

## disassembly

```asm
0x18127b77  push    esi
0x18127b78  push    edi
0x18127b79  push    0FA0h; dwSpinCount
0x18127b7e  push    offset stru_181ECA0C; lpCriticalSection
0x18127b83  call    ds:InitializeCriticalSectionAndSpinCount
0x18127b89  push    offset aApiMsWinCoreSy
0x18127b8e  call    ds:GetModuleHandleW
0x18127b94  mov     esi, eax
0x18127b96  test    esi, esi
0x18127b98  jnz     short loc_18127BAB
0x18127b9a  push    offset aKernel32Dll_0
0x18127b9f  call    ds:GetModuleHandleW
0x18127ba5  mov     esi, eax
0x18127ba7  test    esi, esi
0x18127ba9  jz      short loc_18127BF1
0x18127bab  push    offset aSleepcondition
0x18127bb0  push    esi; hModule
0x18127bb1  call    ds:GetProcAddress
0x18127bb7  push    offset aWakeallconditi
0x18127bbc  push    esi; hModule
0x18127bbd  mov     edi, eax
0x18127bbf  call    ds:GetProcAddress
0x18127bc5  test    edi, edi
0x18127bc7  jz      short loc_18127BDB
0x18127bc9  test    eax, eax
0x18127bcb  jz      short loc_18127BDB
0x18127bcd  mov     dword_181ECA24, edi
0x18127bd3  mov     dword_181ECA28, eax
0x18127bd8  pop     edi
0x18127bd9  pop     esi
0x18127bda  retn
0x18127bdb  xor     eax, eax
0x18127bdd  push    eax; lpName
0x18127bde  push    eax; bInitialState
0x18127bdf  push    1; bManualReset
0x18127be1  push    eax; lpEventAttributes
0x18127be2  call    ds:CreateEventW
0x18127be8  mov     hObject, eax
0x18127bed  test    eax, eax
0x18127bef  jnz     short loc_18127BD8
0x18127bf1  push    7
0x18127bf3  call    ___scrt_fastfail
```
