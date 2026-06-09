# WSTExceptionFilter(void)

- ea: `0x18001a390`
- end: `0x18001a3ae`
- name: `?WSTExceptionFilter@@YAKXZ`
- size: `30`
- prototype: `unsigned int(void)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800070d0`
- `0x180008c58`
- `0x180008e2c`
- `0x180008e60`
- `0x18000c7d0`
- `0x18000ca08`
- `0x18000ea54`
- `0x180016f70`
- `0x180018964`
- `0x18001a3b4`
- `0x18001b9b0`
- `0x18001bba4`

## callees

- `0x180019e60`
- `0x18001eb24`

## pseudocode

```c
__int64 WSTExceptionFilter(void)
{
  __int64 v0; // rdx

  MicrosoftTelemetryAssertTriggeredNoArgs();
  LOBYTE(v0) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoexPassesStructuredExceptions>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_NegoexPassesStructuredExceptions>::GetImpl'::`2'::impl,
    v0);
  return 0;
}

```

## disassembly

```asm
0x18001a390  sub     rsp, 28h
0x18001a394  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001a399  mov     dl, 1
0x18001a39b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NegoexPassesStructuredExceptions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NegoexPassesStructuredExceptions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoexPassesStructuredExceptions> `wil::Feature<__WilFeatureTraits_Feature_NegoexPassesStructuredExceptions>::GetImpl(void)'::`2'::impl
0x18001a3a2  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_NegoexPassesStructuredExceptions@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoexPassesStructuredExceptions>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001a3a7  xor     eax, eax
0x18001a3a9  add     rsp, 28h
0x18001a3ad  retn
```
