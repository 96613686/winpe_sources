# FontSubsettingTelemetryProvider::Provider(void)

- ea: `0x1800055ac`
- end: `0x1800055c5`
- name: `?Provider@FontSubsettingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ`
- size: `25`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800052a0`
- `0x1800055a0`
- `0x180005f70`
- `0x18000600c`
- `0x18000611c`
- `0x180006378`
- `0x1800065e0`
- `0x180006820`

## callees

- `0x18000714c`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall FontSubsettingTelemetryProvider::Provider(__int64 a1)
{
  return *(const struct _tlgProvider_t **)(wil::details::static_lazy<FontSubsettingTelemetryProvider>::get(
                                             a1,
                                             _lambda_627dddc769a2b013bfc919d3d4860246_::_lambda_invoker_cdecl_)
                                         + 8);
}

```

## disassembly

```asm
0x1800055ac  sub     rsp, 28h
0x1800055b0  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_627dddc769a2b013bfc919d3d4860246_@@CA@XZ; _lambda_627dddc769a2b013bfc919d3d4860246_::_lambda_invoker_cdecl_(void)
0x1800055b7  call    ?get@?$static_lazy@VFontSubsettingTelemetryProvider@@@details@wil@@QEAAPEAVFontSubsettingTelemetryProvider@@P6AXXZ@Z; wil::details::static_lazy<FontSubsettingTelemetryProvider>::get(void (*)(void))
0x1800055bc  mov     rax, [rax+8]
0x1800055c0  add     rsp, 28h
0x1800055c4  retn
```
