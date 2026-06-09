# Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)

- ea: `0x180008ca0`
- end: `0x180008cb9`
- name: `?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ`
- size: `25`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `38`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008960`
- `0x180008c94`
- `0x180008de0`
- `0x1800090a4`
- `0x1800091c4`
- `0x1800092a0`
- `0x18000becc`
- `0x18000bf70`
- `0x18000ec88`
- `0x18000ed5c`
- `0x18000ede0`
- `0x18000ee44`
- `0x18000eea8`
- `0x18000ef0c`
- `0x18000ef70`
- `0x18000efd4`
- `0x18000f058`
- `0x18000f0bc`
- `0x18000f120`
- `0x18000f184`
- `0x18000f208`
- `0x180012110`
- `0x180013648`
- `0x180013778`
- `0x180013818`
- `0x1800138b8`
- `0x180013958`
- `0x1800139f8`
- `0x180013a98`
- `0x180013b38`
- `0x180013c20`
- `0x180013e50`
- `0x180014090`
- `0x1800142d0`
- `0x180014510`
- `0x180014750`
- `0x180014990`
- `0x180014bd0`

## callees

- `0x180007970`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(__int64 a1)
{
  return *(const struct _tlgProvider_t **)(wil::details::static_lazy<Microsoft::IoT::ShellExtension::CTelemetryProvider>::get(
                                             a1,
                                             _lambda_ed6b8be98d12cad784f36964ea54eaf3_::_lambda_invoker_cdecl_)
                                         + 8);
}

```

## disassembly

```asm
0x180008ca0  sub     rsp, 28h
0x180008ca4  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_ed6b8be98d12cad784f36964ea54eaf3_@@CA@XZ; _lambda_ed6b8be98d12cad784f36964ea54eaf3_::_lambda_invoker_cdecl_(void)
0x180008cab  call    ?get@?$static_lazy@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@@details@wil@@QEAAPEAVCTelemetryProvider@ShellExtension@IoT@Microsoft@@P6AXXZ@Z; wil::details::static_lazy<Microsoft::IoT::ShellExtension::CTelemetryProvider>::get(void (*)(void))
0x180008cb0  mov     rax, [rax+8]
0x180008cb4  add     rsp, 28h
0x180008cb8  retn
```
