# DllMain

- ea: `0x180013dfc`
- end: `0x180013fb2`
- name: `DllMain`
- size: `438`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002344`

## callees

- `0x1800015b4`
- `0x1800024e0`
- `0x180002efc`
- `0x18000ab80`
- `0x180013dfc`
- `0x1800142d8`
- `0x180014340`
- `0x18001438c`
- `0x1800143bc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180013ec6`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180013ec6`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180013f03`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180013f03`

## string_xrefs

- `0x180013e5f`: `DllMain`
- `0x180013f12`: `DllMain`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v3; // edi
  __int64 v5; // r8
  REGHANDLE v6; // rcx
  __int64 v7; // r8
  const struct wil::FailureInfo *v9; // rdx
  _BYTE v10[160]; // [rsp+30h] [rbp-D8h] BYREF
  const char *v11; // [rsp+E0h] [rbp-28h]
  __int64 v12; // [rsp+E8h] [rbp-20h]

  v3 = 1;
  if ( fdwReason == 1 )
  {
    hProxyDll = hinstDLL;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_180084238);
    McGenEventRegister_EventRegister();
    McGenEventRegisterContext_EventRegister_EventSetInformation();
    if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 1) != 0 )
    {
      v12 = 8;
      v11 = "DllMain";
      McGenEventWrite_EventWriteTransfer(&CtlGuid_Context, mbaeapi_cpp78, v5, 2);
    }
    if ( wil::details::g_pfnLoggingCallback
      && (char *)wil::details::g_pfnLoggingCallback != (char *)MbaeApiResultLoggingCallback )
    {
      memset_0(v10, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v10, v9);
    }
    wil::details::g_pfnLoggingCallback = (__int64 (__fastcall *)(_QWORD))MbaeApiResultLoggingCallback;
    DisableThreadLibraryCalls(hinstDLL);
    g_hInstance = hinstDLL;
    if ( ATL::CAtlBaseModule::m_bInitFailed )
      return 0;
  }
  else
  {
    if ( !fdwReason )
    {
      v6 = RegHandle;
      dword_180084238 = 0;
      RegHandle = 0;
      EventUnregister(v6);
      if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 1) != 0 )
      {
        v12 = 8;
        v11 = "DllMain";
        McGenEventWrite_EventWriteTransfer(&CtlGuid_Context, mbaeapi_cpp88, v7, 2);
      }
      McGenEventUnregister_EventUnregister(&CtlGuid_Context);
      McGenEventUnregister_EventUnregister(&MBAE_Api_Internal_Context);
    }
    g_hInstance = hinstDLL;
  }
  return v3;
}

```

## disassembly

```asm
0x180013dfc  mov     [rsp+arg_8], rbx
0x180013e01  push    rdi
0x180013e02  sub     rsp, 100h
0x180013e09  mov     rax, cs:__security_cookie
0x180013e10  xor     rax, rsp
0x180013e13  mov     [rsp+108h+var_18], rax
0x180013e1b  mov     edi, 1
0x180013e20  mov     rbx, rcx
0x180013e23  cmp     edx, edi
0x180013e25  jnz     short loc_180013E30
0x180013e27  mov     cs:hProxyDll, rcx
0x180013e2e  jmp     short loc_180013E40
0x180013e30  test    edx, edx
0x180013e32  jz      loc_180013EE7
0x180013e38  cmp     edx, edi
0x180013e3a  jnz     loc_180013F6B
0x180013e40  lea     rcx, dword_180084238; CallbackContext
0x180013e47  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180013e4c  call    McGenEventRegister_EventRegister
0x180013e51  call    McGenEventRegisterContext_EventRegister_EventSetInformation
0x180013e56  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, dil
0x180013e5d  jz      short loc_180013EA0
0x180013e5f  lea     rax, aDllmain; "DllMain"
0x180013e66  mov     [rsp+108h+var_20], 8
0x180013e72  mov     [rsp+108h+var_28], rax
0x180013e7a  lea     rdx, mbaeapi_cpp78
0x180013e81  lea     rax, [rsp+108h+var_38]
0x180013e89  mov     r9d, 2
0x180013e8f  lea     rcx, CtlGuid_Context
0x180013e96  mov     [rsp+108h+var_E8], rax
0x180013e9b  call    McGenEventWrite_EventWriteTransfer
0x180013ea0  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180013ea7  lea     rcx, ?MbaeApiResultLoggingCallback@@YAXAEBUFailureInfo@wil@@@Z; MbaeApiResultLoggingCallback(wil::FailureInfo const &)
0x180013eae  test    rax, rax
0x180013eb1  jz      short loc_180013EBC
0x180013eb3  cmp     rax, rcx
0x180013eb6  jnz     loc_180013F95
0x180013ebc  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rcx
0x180013ec3  mov     rcx, rbx; hLibModule
0x180013ec6  call    cs:__imp_DisableThreadLibraryCalls
0x180013ecc  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 0; bool ATL::CAtlBaseModule::m_bInitFailed
0x180013ed3  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hInstance
0x180013eda  jz      loc_180013F72
0x180013ee0  xor     edi, edi
0x180013ee2  jmp     loc_180013F72
0x180013ee7  mov     rcx, cs:RegHandle; RegHandle
0x180013eee  mov     cs:dword_180084238, 0
0x180013ef8  mov     cs:RegHandle, 0
0x180013f03  call    cs:__imp_EventUnregister
0x180013f09  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, dil
0x180013f10  jz      short loc_180013F53
0x180013f12  lea     rax, aDllmain; "DllMain"
0x180013f19  mov     [rsp+108h+var_20], 8
0x180013f25  mov     [rsp+108h+var_28], rax
0x180013f2d  lea     rdx, mbaeapi_cpp88
0x180013f34  lea     rax, [rsp+108h+var_38]
0x180013f3c  mov     r9d, 2
0x180013f42  lea     rcx, CtlGuid_Context
0x180013f49  mov     [rsp+108h+var_E8], rax
0x180013f4e  call    McGenEventWrite_EventWriteTransfer
0x180013f53  lea     rcx, CtlGuid_Context
0x180013f5a  call    McGenEventUnregister_EventUnregister
0x180013f5f  lea     rcx, MBAE_Api_Internal_Context
0x180013f66  call    McGenEventUnregister_EventUnregister
0x180013f6b  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hInstance
0x180013f72  mov     eax, edi
0x180013f74  mov     rcx, [rsp+108h+var_18]
0x180013f7c  xor     rcx, rsp; StackCookie
0x180013f7f  call    __security_check_cookie
0x180013f84  mov     rbx, [rsp+108h+arg_8]
0x180013f8c  add     rsp, 100h
0x180013f93  pop     rdi
0x180013f94  retn
0x180013f95  xor     edx, edx; Val
0x180013f97  lea     rcx, [rsp+108h+var_D8]; void *
0x180013f9c  mov     r8d, 98h; Size
0x180013fa2  call    memset_0
0x180013fa7  lea     rcx, [rsp+108h+var_D8]; this
0x180013fac  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
