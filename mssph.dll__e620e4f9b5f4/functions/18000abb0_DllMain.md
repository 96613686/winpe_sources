# DllMain

- ea: `0x18000abb0`
- end: `0x18000ac80`
- name: `DllMain`
- size: `208`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fb34`

## callees

- `0x18000abb0`
- `0x18000ac88`
- `0x18000db5c`
- `0x18000e8dc`
- `0x180010b2c`
- `0x18001b9ec`
- `0x18001cb80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000abcd`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000abcd`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  const struct _GUID *v3; // r9
  __int64 v5; // rdx
  __int64 v6; // rdx
  const struct wil::FailureInfo *v7; // rdx
  __int64 v9; // rdx
  __int64 v10; // r8
  ATL::CComModule *v11; // rcx
  _BYTE v12[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( fdwReason == 1 )
  {
    ATL::CComModule::Init(
      (ATL::CComModule *)hinstDLL,
      *(struct ATL::_ATL_OBJMAP_ENTRY30 **)&fdwReason,
      (HINSTANCE)lpvReserved,
      v3);
    DisableThreadLibraryCalls(hinstDLL);
    McGenEventRegister_EventRegister(
      Microsoft_Windows_Search_Core,
      v5,
      &Microsoft_Windows_Search_Core_Context,
      &Microsoft_Windows_Search_Core_Context);
    McGenEventRegister_EventRegister(
      Microsoft_Windows_Search_ProtocolHandlers,
      v6,
      Microsoft_Windows_Search_ProtocolHandlers_Context,
      Microsoft_Windows_Search_ProtocolHandlers_Context);
    if ( wil::details::g_pfnTelemetryCallback )
    {
      if ( (char *)wil::details::g_pfnTelemetryCallback != (char *)SearchIndexerTelemetry::FallbackTelemetryCallback )
      {
        memset_0(v12, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v12, v7);
      }
    }
    wil::details::g_pfnTelemetryCallback = (__int64 (__fastcall *)(_QWORD, _QWORD))SearchIndexerTelemetry::FallbackTelemetryCallback;
    return 1;
  }
  else
  {
    if ( !fdwReason )
    {
      McGenEventUnregister_EventUnregister(&Microsoft_Windows_Search_Core_Context, fdwReason, lpvReserved);
      McGenEventUnregister_EventUnregister(Microsoft_Windows_Search_ProtocolHandlers_Context, v9, v10);
      ATL::CComModule::Term(v11);
    }
    return 1;
  }
}

```

## disassembly

```asm
0x18000abb0  push    rbx
0x18000abb2  sub     rsp, 0C0h
0x18000abb9  mov     rbx, rcx
0x18000abbc  cmp     edx, 1
0x18000abbf  jnz     loc_18000AC51
0x18000abc5  call    ?Init@CComModule@ATL@@QEAAJPEAU_ATL_OBJMAP_ENTRY30@2@PEAUHINSTANCE__@@PEBU_GUID@@@Z; ATL::CComModule::Init(ATL::_ATL_OBJMAP_ENTRY30 *,HINSTANCE__ *,_GUID const *)
0x18000abca  mov     rcx, rbx; hLibModule
0x18000abcd  call    cs:__imp_DisableThreadLibraryCalls
0x18000abd3  lea     r9, Microsoft_Windows_Search_Core_Context
0x18000abda  lea     r8, Microsoft_Windows_Search_Core_Context
0x18000abe1  lea     rcx, Microsoft_Windows_Search_Core
0x18000abe8  call    McGenEventRegister_EventRegister
0x18000abed  lea     r9, Microsoft_Windows_Search_ProtocolHandlers_Context
0x18000abf4  lea     r8, Microsoft_Windows_Search_ProtocolHandlers_Context
0x18000abfb  lea     rcx, Microsoft_Windows_Search_ProtocolHandlers
0x18000ac02  call    McGenEventRegister_EventRegister
0x18000ac07  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000ac0e  lea     rcx, ?FallbackTelemetryCallback@SearchIndexerTelemetry@@SAX_NAEBUFailureInfo@wil@@@Z; SearchIndexerTelemetry::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x18000ac15  test    rax, rax
0x18000ac18  jz      short loc_18000AC3C
0x18000ac1a  cmp     rax, rcx
0x18000ac1d  jz      short loc_18000AC3C
0x18000ac1f  xor     edx, edx; Val
0x18000ac21  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000ac26  mov     r8d, 98h; Size
0x18000ac2c  call    memset_0
0x18000ac31  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000ac36  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000ac3c  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x18000ac43  mov     eax, 1
0x18000ac48  add     rsp, 0C0h
0x18000ac4f  pop     rbx
0x18000ac50  retn
0x18000ac51  test    edx, edx
0x18000ac53  jnz     short loc_18000AC72
0x18000ac55  lea     rcx, Microsoft_Windows_Search_Core_Context
0x18000ac5c  call    McGenEventUnregister_EventUnregister
0x18000ac61  lea     rcx, Microsoft_Windows_Search_ProtocolHandlers_Context
0x18000ac68  call    McGenEventUnregister_EventUnregister
0x18000ac6d  call    ?Term@CComModule@ATL@@QEAAXXZ; ATL::CComModule::Term(void)
0x18000ac72  mov     eax, 1
0x18000ac77  add     rsp, 0C0h
0x18000ac7e  pop     rbx
0x18000ac7f  retn
```
