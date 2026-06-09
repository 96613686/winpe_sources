# DllMain

- ea: `0x180015bd0`
- end: `0x180015c9c`
- name: `DllMain`
- size: `204`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180053fb4`

## callees

- `0x1800018f0`
- `0x180015bd0`
- `0x180015cd8`
- `0x180016a0c`
- `0x180016f94`
- `0x180016fec`
- `0x180017074`
- `0x180017218`
- `0x180017514`
- `0x1800358e8`
- `0x180036440`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180015c91`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180015c91`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  Microsoft::WRL::Details *v14; // rax
  struct Microsoft::WRL::Details::ModuleBase *v15; // rdx
  bool v16; // r9

  if ( fdwReason == 1 )
  {
    if ( hinstDLL )
      DisableThreadLibraryCalls(hinstDLL);
    Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(
      hinstDLL,
      *(_QWORD *)&fdwReason,
      lpvReserved);
    Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(v5, v4, v6);
    McGenEventRegister_EventRegister(
      Microsoft_Windows_MediaFoundation_Performance,
      v7,
      Microsoft_Windows_MediaFoundation_Performance_Context,
      Microsoft_Windows_MediaFoundation_Performance_Context);
    WPP_INIT_CONTROL_ARRAY();
    WPP_INIT_GUID_ARRAY();
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WppInitUm();
    McGenEventRegister_EventRegister(
      Microsoft_Windows_MediaFoundation_MSVProc,
      v8,
      Microsoft_Windows_MediaFoundation_MSVProc_Context,
      Microsoft_Windows_MediaFoundation_MSVProc_Context);
    TraceLoggingRegisterEx_EventRegister_EventSetInformation();
    return 1;
  }
  else
  {
    if ( !fdwReason )
    {
      McGenEventUnregister_EventUnregister(
        Microsoft_Windows_MediaFoundation_Performance_Context,
        fdwReason,
        lpvReserved);
      WppCleanupUm();
      McGenEventUnregister_EventUnregister(Microsoft_Windows_MediaFoundation_MSVProc_Context, v9, v10);
      TraceLoggingUnregister_EventUnregister();
      v14 = (Microsoft::WRL::Details *)Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(
                                         v12,
                                         v11,
                                         v13);
      Microsoft::WRL::Details::TerminateMap(v14, v15, 0, v16);
    }
    return 1;
  }
}

```

## disassembly

```asm
0x180015bd0  sub     rsp, 28h
0x180015bd4  cmp     edx, 1
0x180015bd7  jz      short loc_180015BE7
0x180015bd9  test    edx, edx
0x180015bdb  jz      short loc_180015C5A
0x180015bdd  mov     eax, 1
0x180015be2  add     rsp, 28h
0x180015be6  retn
0x180015be7  test    rcx, rcx
0x180015bea  jnz     loc_180015C91
0x180015bf0  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x180015bf5  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x180015bfa  lea     r9, Microsoft_Windows_MediaFoundation_Performance_Context
0x180015c01  lea     r8, Microsoft_Windows_MediaFoundation_Performance_Context
0x180015c08  lea     rcx, Microsoft_Windows_MediaFoundation_Performance
0x180015c0f  call    McGenEventRegister_EventRegister
0x180015c14  call    WPP_INIT_CONTROL_ARRAY
0x180015c19  call    WPP_INIT_GUID_ARRAY
0x180015c1e  lea     rcx, WPP_MAIN_CB
0x180015c25  mov     cs:WPP_GLOBAL_Control, rcx
0x180015c2c  call    WppInitUm
0x180015c31  lea     r9, Microsoft_Windows_MediaFoundation_MSVProc_Context
0x180015c38  lea     r8, Microsoft_Windows_MediaFoundation_MSVProc_Context
0x180015c3f  lea     rcx, Microsoft_Windows_MediaFoundation_MSVProc
0x180015c46  call    McGenEventRegister_EventRegister
0x180015c4b  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180015c50  mov     eax, 1
0x180015c55  add     rsp, 28h
0x180015c59  retn
0x180015c5a  lea     rcx, Microsoft_Windows_MediaFoundation_Performance_Context
0x180015c61  call    McGenEventUnregister_EventUnregister
0x180015c66  call    WppCleanupUm
0x180015c6b  lea     rcx, Microsoft_Windows_MediaFoundation_MSVProc_Context
0x180015c72  call    McGenEventUnregister_EventUnregister
0x180015c77  call    TraceLoggingUnregister_EventUnregister
0x180015c7c  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x180015c81  xor     r8d, r8d; unsigned __int16 *
0x180015c84  mov     rcx, rax; this
0x180015c87  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x180015c8c  jmp     loc_180015BDD
0x180015c91  call    cs:__imp_DisableThreadLibraryCalls
0x180015c97  jmp     loc_180015BF0
```
