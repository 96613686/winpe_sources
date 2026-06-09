# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)

- ea: `0x18000c3bc`
- end: `0x18000c3d5`
- name: `?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ`
- size: `25`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `10`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007550`
- `0x18000bb20`
- `0x18000be70`
- `0x18000c3b0`
- `0x18000d1c4`
- `0x18000d318`
- `0x18000d4b8`
- `0x18000d754`
- `0x18000d9b0`
- `0x18000dbe0`

## callees

- `0x18000ed50`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(
        __int64 a1)
{
  return (const struct _tlgProvider_t *)*((_QWORD *)wil::details::static_lazy<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry>::get(
                                                      a1,
                                                      (void (__cdecl *)())_lambda_bf0cab7e367b92d194d9a1ba31b40746_::_lambda_invoker_cdecl_)
                                        + 1);
}

```

## disassembly

```asm
0x18000c3bc  sub     rsp, 28h
0x18000c3c0  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_bf0cab7e367b92d194d9a1ba31b40746_@@CA@XZ; _lambda_bf0cab7e367b92d194d9a1ba31b40746_::_lambda_invoker_cdecl_(void)
0x18000c3c7  call    ?get@?$static_lazy@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@@details@wil@@QEAAPEAVPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@P6AXXZ@Z; wil::details::static_lazy<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry>::get(void (*)(void))
0x18000c3cc  mov     rax, [rax+8]
0x18000c3d0  add     rsp, 28h
0x18000c3d4  retn
```
