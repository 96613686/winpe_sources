# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CCoreWebViewTaskHelpers::WebViewTaskAsyncOpDefaultName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(void)

- ea: `0x18001ed48`
- end: `0x18001ee17`
- name: `?TraceOperationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$1?WebViewTaskAsyncOpDefaultName@CCoreWebViewTaskHelpers@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180006b00`

## callees

- `0x18001ed48`
- `0x18002b530`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ed9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ed9b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001edb1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001edb1`

## string_xrefs

- `0x18001ed94`: `WebViewTaskHelperAsyncOp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *__fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&unsigned short const near * const CCoreWebViewTaskHelpers::WebViewTaskAsyncOpDefaultName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(
        __int64 a1)
{
  struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *result; // rax
  __int64 v3; // rdi
  __int64 v4; // rsi
  HRESULT v5; // eax
  GUID v6; // [rsp+40h] [rbp-48h] BYREF
  HSTRING_HEADER v7; // [rsp+50h] [rbp-38h] BYREF
  HSTRING v8; // [rsp+68h] [rbp-20h] BYREF

  result = Microsoft::WRL::gCausality;
  if ( Microsoft::WRL::gCausality )
  {
    v3 = *(_QWORD *)Microsoft::WRL::gCausality;
    v8 = 0;
    v4 = *(unsigned int *)(a1 + 64);
    v5 = WindowsCreateStringReference(L"WebViewTaskHelperAsyncOp", 0x18u, &v7, &v8);
    if ( v5 < 0 )
      RaiseException(v5, 1u, 0, 0);
    v6 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
    return (struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *)(*(__int64 (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, __int64, HSTRING, __int64))(v3 + 48))(
                                                                                      Microsoft::WRL::gCausality,
                                                                                      0,
                                                                                      2,
                                                                                      &v6,
                                                                                      a1,
                                                                                      v8,
                                                                                      v4);
  }
  return result;
}

```

## disassembly

```asm
0x18001ed48  mov     r11, rsp
0x18001ed4b  mov     [r11+10h], rbx
0x18001ed4f  mov     [r11+18h], rsi
0x18001ed53  push    rdi
0x18001ed54  sub     rsp, 80h
0x18001ed5b  mov     rax, cs:__security_cookie
0x18001ed62  xor     rax, rsp
0x18001ed65  mov     [rsp+88h+var_18], rax
0x18001ed6a  mov     rbx, rcx
0x18001ed6d  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18001ed74  test    rax, rax
0x18001ed77  jz      short loc_18001EDF5
0x18001ed79  mov     rdi, [rax]
0x18001ed7c  mov     qword ptr [r11-20h], 0
0x18001ed84  mov     esi, [rcx+40h]
0x18001ed87  lea     r9, [r11-20h]; string
0x18001ed8b  lea     r8, [r11-38h]; hstringHeader
0x18001ed8f  mov     edx, 18h; length
0x18001ed94  lea     rcx, ?WebViewTaskAsyncOpDefaultName@CCoreWebViewTaskHelpers@@3QBGB; "WebViewTaskHelperAsyncOp"
0x18001ed9b  call    cs:__imp_WindowsCreateStringReference
0x18001eda1  test    eax, eax
0x18001eda3  jns     short loc_18001EDB8
0x18001eda5  xor     r9d, r9d; lpArguments
0x18001eda8  xor     r8d, r8d; nNumberOfArguments
0x18001edab  lea     edx, [r9+1]; dwExceptionFlags
0x18001edaf  mov     ecx, eax; dwExceptionCode
0x18001edb1  call    cs:__imp_RaiseException
0x18001edb7  nop
0x18001edb8  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18001edbf  movdqu  [rsp+88h+var_48], xmm0
0x18001edc5  mov     [rsp+88h+var_58], rsi
0x18001edca  mov     rcx, [rsp+88h+var_20]
0x18001edcf  mov     [rsp+88h+var_60], rcx
0x18001edd4  mov     [rsp+88h+var_68], rbx
0x18001edd9  lea     r9, [rsp+88h+var_48]
0x18001edde  xor     edx, edx
0x18001ede0  lea     r8d, [rdx+2]
0x18001ede4  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18001edeb  mov     rax, [rdi+30h]
0x18001edef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edf4  nop
0x18001edf5  mov     rcx, [rsp+88h+var_18]
0x18001edfa  xor     rcx, rsp; StackCookie
0x18001edfd  call    __security_check_cookie
0x18001ee02  lea     r11, [rsp+88h+var_8]
0x18001ee0a  mov     rbx, [r11+18h]
0x18001ee0e  mov     rsi, [r11+20h]
0x18001ee12  mov     rsp, r11
0x18001ee15  pop     rdi
0x18001ee16  retn
```
