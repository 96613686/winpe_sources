# DWriteRenderingParams::DetermineCompatibleSmoothingMode(void)

- ea: `0x1801307f4`
- end: `0x180130867`
- name: `?DetermineCompatibleSmoothingMode@DWriteRenderingParams@@SA?AW4CompatibleSmoothingMode@@XZ`
- size: `115`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18012ec40`
- `0x180130738`
- `0x180186b94`
- `0x1801881a0`

## callees

- `0x1801307f4`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180130820`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180130848`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180130820`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180130848`

## pseudocode

```c
__int64 DWriteRenderingParams::DetermineCompatibleSmoothingMode()
{
  __int64 result; // rax
  int pvParam; // [rsp+30h] [rbp+8h] BYREF
  int v2; // [rsp+38h] [rbp+10h] BYREF

  if ( GlyphRenderingParams::overrideSystemRenderingParams_ )
    return 3;
  pvParam = 0;
  if ( SystemParametersInfoW(0x4Au, 0, &pvParam, 0) && !pvParam )
    return 1;
  v2 = 0;
  if ( !SystemParametersInfoW(0x200Au, 0, &v2, 0) )
    return 3;
  result = 2;
  if ( v2 != 1 )
    return 3;
  return result;
}

```

## disassembly

```asm
0x1801307f4  sub     rsp, 28h
0x1801307f8  cmp     cs:?overrideSystemRenderingParams_@GlyphRenderingParams@@0_NA, 0; bool GlyphRenderingParams::overrideSystemRenderingParams_
0x1801307ff  jz      short loc_18013080B
0x180130801  mov     eax, 3
0x180130806  add     rsp, 28h
0x18013080a  retn
0x18013080b  xor     edx, edx; uiParam
0x18013080d  mov     [rsp+28h+pvParam], 0
0x180130815  xor     r9d, r9d; fWinIni
0x180130818  lea     r8, [rsp+28h+pvParam]; pvParam
0x18013081d  lea     ecx, [rdx+4Ah]; uiAction
0x180130820  call    cs:__imp_SystemParametersInfoW
0x180130826  test    eax, eax
0x180130828  jz      short loc_180130831
0x18013082a  cmp     [rsp+28h+pvParam], 0
0x18013082f  jz      short loc_180130860
0x180130831  xor     r9d, r9d; fWinIni
0x180130834  mov     [rsp+28h+arg_8], 0
0x18013083c  lea     r8, [rsp+28h+arg_8]; pvParam
0x180130841  xor     edx, edx; uiParam
0x180130843  mov     ecx, 200Ah; uiAction
0x180130848  call    cs:__imp_SystemParametersInfoW
0x18013084e  test    eax, eax
0x180130850  jz      short loc_180130801
0x180130852  cmp     [rsp+28h+arg_8], 1
0x180130857  mov     eax, 2
0x18013085c  jz      short loc_180130806
0x18013085e  jmp     short loc_180130801
0x180130860  mov     eax, 1
0x180130865  jmp     short loc_180130806
```
