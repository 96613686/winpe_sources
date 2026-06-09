# DllMain

- ea: `0x18001c8e4`
- end: `0x18001c956`
- name: `DllMain`
- size: `114`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180024094`

## callees

- `0x1800145c8`
- `0x180014680`
- `0x18001c8e4`
- `0x18001c95c`
- `0x18001c990`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v5; // rdx
  __int64 v6; // r8

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CD_MJPEG_MFT_Decoder>::__private_IsEnabled(
                              hinstDLL,
                              fdwReason,
                              lpvReserved) )
        TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18009C060);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18009C028);
    }
  }
  else
  {
    TraceLoggingUnregister_EventUnregister(&dword_18009C028, fdwReason, lpvReserved);
    if ( (unsigned __int8)((__int64 (*)(void))wil::details::FeatureImpl<__WilFeatureTraits_Feature_CD_MJPEG_MFT_Decoder>::__private_IsEnabled)() )
      TraceLoggingUnregister_EventUnregister(&dword_18009C060, v5, v6);
  }
  return DllEntryPoint(hinstDLL, fdwReason);
}

```

## disassembly

```asm
0x18001c8e4  mov     [rsp+arg_0], rbx
0x18001c8e9  push    rdi
0x18001c8ea  sub     rsp, 20h
0x18001c8ee  mov     ebx, edx
0x18001c8f0  mov     rdi, rcx
0x18001c8f3  mov     eax, edx
0x18001c8f5  test    edx, edx
0x18001c8f7  jz      short loc_18001C921
0x18001c8f9  cmp     eax, 1
0x18001c8fc  jnz     short loc_18001C942
0x18001c8fe  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CD_MJPEG_MFT_Decoder@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CD_MJPEG_MFT_Decoder>::__private_IsEnabled(void)
0x18001c903  test    al, al
0x18001c905  jz      short loc_18001C913
0x18001c907  lea     rcx, dword_18009C060; CallbackContext
0x18001c90e  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001c913  lea     rcx, dword_18009C028; CallbackContext
0x18001c91a  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001c91f  jmp     short loc_18001C942
0x18001c921  lea     rcx, dword_18009C028
0x18001c928  call    TraceLoggingUnregister_EventUnregister
0x18001c92d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CD_MJPEG_MFT_Decoder@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CD_MJPEG_MFT_Decoder>::__private_IsEnabled(void)
0x18001c932  test    al, al
0x18001c934  jz      short loc_18001C942
0x18001c936  lea     rcx, dword_18009C060
0x18001c93d  call    TraceLoggingUnregister_EventUnregister
0x18001c942  mov     edx, ebx
0x18001c944  mov     rcx, rdi
0x18001c947  mov     rbx, [rsp+28h+arg_0]
0x18001c94c  add     rsp, 20h
0x18001c950  pop     rdi
0x18001c951  jmp     _DllEntryPoint
```
