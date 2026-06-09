# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(void)

- ea: `0x180078984`
- end: `0x180078a53`
- name: `?TraceOperationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180058a90`

## callees

- `0x180078984`
- `0x1800862f0`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180078a4c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180078a4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800789d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800789d7`

## string_xrefs

- `0x1800789d0`: `Windows.Foundation.AsyncOperationCompletedHandler`1<Windows.Storage.Streams.IRandomAccessStream>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *__fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(
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
    v5 = WindowsCreateStringReference(
           L"Windows.Foundation.AsyncOperationCompletedHandler`1<Windows.Storage.Streams.IRandomAccessStream>",
           0x60u,
           &v7,
           &v8);
    if ( v5 < 0 )
    {
      RaiseException(v5, 1u, 0, 0);
      JUMPOUT(0x180078A52LL);
    }
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
0x180078984  mov     r11, rsp
0x180078987  mov     [r11+10h], rbx
0x18007898b  mov     [r11+18h], rsi
0x18007898f  push    rdi
0x180078990  sub     rsp, 80h
0x180078997  mov     rax, cs:__security_cookie
0x18007899e  xor     rax, rsp
0x1800789a1  mov     [rsp+88h+var_18], rax
0x1800789a6  mov     rbx, rcx
0x1800789a9  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1800789b0  test    rax, rax
0x1800789b3  jz      short loc_180078A1E
0x1800789b5  mov     rdi, [rax]
0x1800789b8  mov     qword ptr [r11-20h], 0
0x1800789c0  mov     esi, [rcx+40h]
0x1800789c3  lea     r9, [r11-20h]; string
0x1800789c7  lea     r8, [r11-38h]; hstringHeader
0x1800789cb  mov     edx, 60h ; '`'; length
0x1800789d0  lea     rcx, sourceString; "Windows.Foundation.AsyncOperationComple"...
0x1800789d7  call    cs:__imp_WindowsCreateStringReference
0x1800789dd  test    eax, eax
0x1800789df  js      short loc_180078A40
0x1800789e1  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x1800789e8  movdqu  [rsp+88h+var_48], xmm0
0x1800789ee  mov     [rsp+88h+var_58], rsi
0x1800789f3  mov     rcx, [rsp+88h+var_20]
0x1800789f8  mov     [rsp+88h+var_60], rcx
0x1800789fd  mov     [rsp+88h+var_68], rbx
0x180078a02  lea     r9, [rsp+88h+var_48]
0x180078a07  xor     edx, edx
0x180078a09  lea     r8d, [rdx+2]
0x180078a0d  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180078a14  mov     rax, [rdi+30h]
0x180078a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078a1d  nop
0x180078a1e  mov     rcx, [rsp+88h+var_18]
0x180078a23  xor     rcx, rsp; StackCookie
0x180078a26  call    __security_check_cookie
0x180078a2b  lea     r11, [rsp+88h+var_8]
0x180078a33  mov     rbx, [r11+18h]
0x180078a37  mov     rsi, [r11+20h]
0x180078a3b  mov     rsp, r11
0x180078a3e  pop     rdi
0x180078a3f  retn
0x180078a40  xor     r9d, r9d; lpArguments
0x180078a43  xor     r8d, r8d; nNumberOfArguments
0x180078a46  lea     edx, [r9+1]; dwExceptionFlags
0x180078a4a  mov     ecx, eax; dwExceptionCode
0x180078a4c  call    cs:__imp_RaiseException
```
