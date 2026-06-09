# PerformWSManPluginReportCompletion(void)

- ea: `0x180003a50`
- end: `0x180003a60`
- name: `?PerformWSManPluginReportCompletion@@YAXXZ`
- size: `16`
- prototype: `void(void)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `WsmSvc!WSManPluginReportCompletion` at `0x180003a59`

## pseudocode

```c
void PerformWSManPluginReportCompletion(void)
{
  WSManPluginReportCompletion(g_pPluginContext, 0);
}

```

## disassembly

```asm
0x180003a50  mov     rcx, cs:?g_pPluginContext@@3PEAVPwrshPlugIn@@EA; PwrshPlugIn * g_pPluginContext
0x180003a57  xor     edx, edx
0x180003a59  jmp     cs:__imp_WSManPluginReportCompletion
```
