# DllMain

- ea: `0x18000fb18`
- end: `0x18000fc37`
- name: `DllMain`
- size: `287`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002ef4`

## callees

- `0x180003080`
- `0x180003bc8`
- `0x18000bc50`
- `0x18000fb18`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000fb42`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000fb42`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000fbf7`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000fbf7`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000fbb4`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000fbb4`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000fb95`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000fb95`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  REGHANDLE v3; // rcx
  const struct wil::FailureInfo *v5; // rdx
  _BYTE v6[160]; // [rsp+20h] [rbp-C8h] BYREF
  GUID ProviderId; // [rsp+C0h] [rbp-28h] BYREF

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      ProviderId = (GUID)*((_OWORD *)off_180075008 - 1);
      if ( RegHandle )
        __fastfail(5u);
      xmmword_180075028 = 0;
      if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_180075000, &RegHandle) )
        EventSetInformation(RegHandle, 2, off_180075008, *(unsigned __int16 *)off_180075008);
      if ( wil::details::g_pfnLoggingCallback
        && (__int64 (__fastcall *)())wil::details::g_pfnLoggingCallback != DllMain_::_4_::_lambda_1_::_lambda_invoker_cdecl_ )
      {
        memset_0(v6, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v6, v5);
      }
      wil::details::g_pfnLoggingCallback = (__int64)DllMain_::_4_::_lambda_1_::_lambda_invoker_cdecl_;
    }
  }
  else
  {
    v3 = RegHandle;
    dword_180075000 = 0;
    RegHandle = 0;
    EventUnregister(v3);
  }
  return 1;
}

```

## disassembly

```asm
0x18000fb18  sub     rsp, 0E8h
0x18000fb1f  mov     rax, cs:__security_cookie
0x18000fb26  xor     rax, rsp
0x18000fb29  mov     [rsp+0E8h+var_18], rax
0x18000fb31  test    edx, edx
0x18000fb33  jz      loc_18000FBDB
0x18000fb39  cmp     edx, 1
0x18000fb3c  jnz     loc_18000FBFD
0x18000fb42  call    cs:__imp_DisableThreadLibraryCalls
0x18000fb48  cmp     cs:RegHandle, 0
0x18000fb50  mov     rax, cs:off_180075008
0x18000fb57  movups  xmm0, xmmword ptr [rax-10h]
0x18000fb5b  movdqu  xmmword ptr [rsp+0E8h+ProviderId.Data1], xmm0
0x18000fb64  jz      short loc_18000FB6D
0x18000fb66  mov     ecx, 5
0x18000fb6b  int     29h; Win8: RtlFailFast(ecx)
0x18000fb6d  xorps   xmm0, xmm0
0x18000fb70  lea     r9, RegHandle; RegHandle
0x18000fb77  lea     r8, dword_180075000; CallbackContext
0x18000fb7e  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000fb85  lea     rcx, [rsp+0E8h+ProviderId]; ProviderId
0x18000fb8d  movdqu  cs:xmmword_180075028, xmm0
0x18000fb95  call    cs:__imp_EventRegister
0x18000fb9b  test    eax, eax
0x18000fb9d  jnz     short loc_18000FBBA
0x18000fb9f  mov     r8, cs:off_180075008
0x18000fba6  lea     edx, [rax+2]
0x18000fba9  mov     rcx, cs:RegHandle
0x18000fbb0  movzx   r9d, word ptr [r8]
0x18000fbb4  call    cs:__imp_EventSetInformation
0x18000fbba  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000fbc1  lea     rcx, _DllMain____4____lambda_1____lambda_invoker_cdecl_
0x18000fbc8  test    rax, rax
0x18000fbcb  jz      short loc_18000FBD2
0x18000fbcd  cmp     rax, rcx
0x18000fbd0  jnz     short loc_18000FC1A
0x18000fbd2  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rcx
0x18000fbd9  jmp     short loc_18000FBFD
0x18000fbdb  mov     rcx, cs:RegHandle; RegHandle
0x18000fbe2  mov     cs:dword_180075000, 0
0x18000fbec  mov     cs:RegHandle, 0
0x18000fbf7  call    cs:__imp_EventUnregister
0x18000fbfd  mov     eax, 1
0x18000fc02  mov     rcx, [rsp+0E8h+var_18]
0x18000fc0a  xor     rcx, rsp; StackCookie
0x18000fc0d  call    __security_check_cookie
0x18000fc12  add     rsp, 0E8h
0x18000fc19  retn
0x18000fc1a  xor     edx, edx; Val
0x18000fc1c  lea     rcx, [rsp+0E8h+var_C8]; void *
0x18000fc21  mov     r8d, 98h; Size
0x18000fc27  call    memset_0
0x18000fc2c  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000fc31  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
