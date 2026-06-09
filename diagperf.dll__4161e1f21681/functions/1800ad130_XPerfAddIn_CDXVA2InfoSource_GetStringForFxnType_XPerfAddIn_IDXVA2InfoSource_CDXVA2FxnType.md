# XPerfAddIn::CDXVA2InfoSource::GetStringForFxnType(XPerfAddIn::IDXVA2InfoSource::CDXVA2FxnType)

- ea: `0x1800ad130`
- end: `0x1800ad1ac`
- name: `?GetStringForFxnType@CDXVA2InfoSource@XPerfAddIn@@UEBAPEBGW4CDXVA2FxnType@IDXVA2InfoSource@2@@Z`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800ad130`

## string_xrefs

- `0x1800ad1a4`: `DXVA2FxnType_Decode_Create`
- `0x1800ad174`: `DXVA2FxnType_VP_Create`

## pseudocode

```c
const wchar_t *__fastcall XPerfAddIn::CDXVA2InfoSource::GetStringForFxnType(__int64 a1, int a2)
{
  int v2; // edx
  int v3; // edx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx

  if ( !a2 )
    return L"DXVA2FxnType_Decode_Create";
  v2 = a2 - 1;
  if ( !v2 )
    return L"DXVA2FxnType_Decode_GetBuffer";
  v3 = v2 - 1;
  if ( !v3 )
    return L"DXVA2FxnType_Decode_BeginFrame";
  v4 = v3 - 1;
  if ( !v4 )
    return L"DXVA2FxnType_Decode_EndFrame";
  v5 = v4 - 1;
  if ( !v5 )
    return L"DXVA2FxnType_Decode_Execute";
  v6 = v5 - 1;
  if ( !v6 )
    return L"DXVA2FxnType_Decode_Destroy";
  v7 = v6 - 1;
  if ( !v7 )
    return L"DXVA2FxnType_VP_Create";
  v8 = v7 - 1;
  if ( !v8 )
    return L"DXVA2FxnType_VP_Blt";
  if ( v8 == 1 )
    return L"DXVA2FxnType_VP_Destroy";
  return L"(Unknown)";
}

```

## disassembly

```asm
0x1800ad130  test    edx, edx
0x1800ad132  jz      short loc_1800AD1A4
0x1800ad134  sub     edx, 1
0x1800ad137  jz      short loc_1800AD19C
0x1800ad139  sub     edx, 1
0x1800ad13c  jz      short loc_1800AD194
0x1800ad13e  sub     edx, 1
0x1800ad141  jz      short loc_1800AD18C
0x1800ad143  sub     edx, 1
0x1800ad146  jz      short loc_1800AD184
0x1800ad148  sub     edx, 1
0x1800ad14b  jz      short loc_1800AD17C
0x1800ad14d  sub     edx, 1
0x1800ad150  jz      short loc_1800AD174
0x1800ad152  sub     edx, 1
0x1800ad155  jz      short loc_1800AD16C
0x1800ad157  cmp     edx, 1
0x1800ad15a  jz      short loc_1800AD164
0x1800ad15c  lea     rax, aUnknown_2; "(Unknown)"
0x1800ad163  retn
0x1800ad164  lea     rax, aDxva2fxntypeVp_0; "DXVA2FxnType_VP_Destroy"
0x1800ad16b  retn
0x1800ad16c  lea     rax, aDxva2fxntypeVp_1; "DXVA2FxnType_VP_Blt"
0x1800ad173  retn
0x1800ad174  lea     rax, aDxva2fxntypeVp; "DXVA2FxnType_VP_Create"
0x1800ad17b  retn
0x1800ad17c  lea     rax, aDxva2fxntypeDe_2; "DXVA2FxnType_Decode_Destroy"
0x1800ad183  retn
0x1800ad184  lea     rax, aDxva2fxntypeDe_0; "DXVA2FxnType_Decode_Execute"
0x1800ad18b  retn
0x1800ad18c  lea     rax, aDxva2fxntypeDe; "DXVA2FxnType_Decode_EndFrame"
0x1800ad193  retn
0x1800ad194  lea     rax, aDxva2fxntypeDe_1; "DXVA2FxnType_Decode_BeginFrame"
0x1800ad19b  retn
0x1800ad19c  lea     rax, aDxva2fxntypeDe_4; "DXVA2FxnType_Decode_GetBuffer"
0x1800ad1a3  retn
0x1800ad1a4  lea     rax, aDxva2fxntypeDe_3; "DXVA2FxnType_Decode_Create"
0x1800ad1ab  retn
```
