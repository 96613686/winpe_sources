# DllMain

- ea: `0x1800075fc`
- end: `0x18000767d`
- name: `DllMain`
- size: `129`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d664`

## callees

- `0x1800075fc`
- `0x180007684`
- `0x1800076a8`
- `0x1800076c0`
- `0x180007770`
- `0x1800077a0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180007615`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180007615`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  HMODULE v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // rdx
  __int64 v7; // rdx
  __int64 v8; // r8

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      g_hDwmApiInstance = hinstDLL;
      MilDisableInstrumentationBreaks();
      DisableThreadLibraryCalls(v3);
      McGenEventRegister_EtwEventRegister(
        Microsoft_Windows_Dwm_Api_Provider,
        v4,
        Microsoft_Windows_Dwm_Api_Provider_Context,
        Microsoft_Windows_Dwm_Api_Provider_Context);
      McGenEventRegister_EtwEventRegister(
        Microsoft_Windows_Shell_Core_Provider,
        v5,
        Microsoft_Windows_Shell_Core_Provider_Context,
        Microsoft_Windows_Shell_Core_Provider_Context);
      TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation();
    }
  }
  else
  {
    McGenEventUnregister_EtwEventUnregister(Microsoft_Windows_Dwm_Api_Provider_Context, fdwReason, lpvReserved);
    McGenEventUnregister_EtwEventUnregister(Microsoft_Windows_Shell_Core_Provider_Context, v7, v8);
    TraceLoggingUnregister_EtwEventUnregister();
  }
  return 1;
}

```

## disassembly

```asm
0x1800075fc  sub     rsp, 28h
0x180007600  test    edx, edx
0x180007602  jz      short loc_18000765E
0x180007604  cmp     edx, 1
0x180007607  jnz     short loc_180007654
0x180007609  mov     cs:?g_hDwmApiInstance@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hDwmApiInstance
0x180007610  call    ?MilDisableInstrumentationBreaks@@YAXXZ; MilDisableInstrumentationBreaks(void)
0x180007615  call    cs:__imp_DisableThreadLibraryCalls
0x18000761b  lea     r9, Microsoft_Windows_Dwm_Api_Provider_Context
0x180007622  lea     r8, Microsoft_Windows_Dwm_Api_Provider_Context
0x180007629  lea     rcx, Microsoft_Windows_Dwm_Api_Provider
0x180007630  call    McGenEventRegister_EtwEventRegister
0x180007635  lea     r9, Microsoft_Windows_Shell_Core_Provider_Context
0x18000763c  lea     r8, Microsoft_Windows_Shell_Core_Provider_Context
0x180007643  lea     rcx, Microsoft_Windows_Shell_Core_Provider
0x18000764a  call    McGenEventRegister_EtwEventRegister
0x18000764f  call    TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation
0x180007654  mov     eax, 1
0x180007659  add     rsp, 28h
0x18000765d  retn
0x18000765e  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x180007665  call    McGenEventUnregister_EtwEventUnregister
0x18000766a  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x180007671  call    McGenEventUnregister_EtwEventUnregister
0x180007676  call    TraceLoggingUnregister_EtwEventUnregister
0x18000767b  jmp     short loc_180007654
```
