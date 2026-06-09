# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CCoreWebViewTaskHelpers::WebViewTaskAsyncOpDefaultName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::InitCausality(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180007670`
- end: `0x1800076f4`
- name: `?InitCausality@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$1?WebViewTaskAsyncOpDefaultName@CCoreWebViewTaskHelpers@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `132`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180007670`
- `0x18002b530`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800076a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800076a2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800076b9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800076b9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800076d3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800076d3`

## pseudocode

```c
_BOOL8 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,&unsigned short const near * const CCoreWebViewTaskHelpers::WebViewTaskAsyncOpDefaultName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::InitCausality(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  HRESULT v3; // eax
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-38h] BYREF
  HSTRING string; // [rsp+38h] [rbp-20h] BYREF

  string = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Foundation.Diagnostics.AsyncCausalityTracer",
         0x33u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  return (int)RoGetActivationFactory(string, &GUID_50850b26_267e_451b_a890_ab6a370245ee, &Microsoft::WRL::gCausality) >= 0;
}

```

## disassembly

```asm
0x180007670  sub     rsp, 58h
0x180007674  mov     rax, cs:__security_cookie
0x18000767b  xor     rax, rsp
0x18000767e  mov     [rsp+58h+var_18], rax
0x180007683  lea     r9, [rsp+58h+string]; string
0x180007688  mov     [rsp+58h+string], 0
0x180007691  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x180007696  mov     edx, 33h ; '3'; length
0x18000769b  lea     rcx, ?RuntimeClass_Windows_Foundation_Diagnostics_AsyncCausalityTracer@@3QBGB; "Windows.Foundation.Diagnostics.AsyncCau"...
0x1800076a2  call    cs:__imp_WindowsCreateStringReference
0x1800076a8  test    eax, eax
0x1800076aa  jns     short loc_1800076C0
0x1800076ac  xor     r9d, r9d; lpArguments
0x1800076af  xor     r8d, r8d; nNumberOfArguments
0x1800076b2  mov     edx, 1; dwExceptionFlags
0x1800076b7  mov     ecx, eax; dwExceptionCode
0x1800076b9  call    cs:__imp_RaiseException
0x1800076bf  int     3; Trap to Debugger
0x1800076c0  mov     rcx, [rsp+58h+string]
0x1800076c5  lea     r8, ?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1800076cc  lea     rdx, _GUID_50850b26_267e_451b_a890_ab6a370245ee
0x1800076d3  call    cs:__imp_RoGetActivationFactory
0x1800076d9  xor     ecx, ecx
0x1800076db  test    eax, eax
0x1800076dd  setns   cl
0x1800076e0  mov     eax, ecx
0x1800076e2  mov     rcx, [rsp+58h+var_18]
0x1800076e7  xor     rcx, rsp; StackCookie
0x1800076ea  call    __security_check_cookie
0x1800076ef  add     rsp, 58h
0x1800076f3  retn
```
