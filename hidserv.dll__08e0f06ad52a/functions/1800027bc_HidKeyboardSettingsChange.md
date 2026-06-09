# HidKeyboardSettingsChange

- ea: `0x1800027bc`
- end: `0x180002830`
- name: `HidKeyboardSettingsChange`
- size: `116`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180002e40`

## callees

- `0x1800027bc`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x1800027e9`
- `USER32!SystemParametersInfoW` at `0x180002813`
- `USER32!SystemParametersInfoW` at `0x1800027e9`
- `USER32!SystemParametersInfoW` at `0x180002813`

## pseudocode

```c
__int64 __fastcall HidKeyboardSettingsChange(__int64 a1)
{
  __int64 result; // rax
  int pvParam; // [rsp+30h] [rbp+8h] BYREF
  int v3; // [rsp+38h] [rbp+10h] BYREF

  if ( a1 == 11 || a1 == 23 )
  {
    pvParam = 0;
    v3 = 0;
    SystemParametersInfoW(0xAu, 0, &pvParam, 0);
    REPEAT_INTERVAL = 400 - 12 * pvParam;
    SystemParametersInfoW(0x16u, 0, &v3, 0);
    result = (unsigned int)(v3 + 1);
    INITIAL_WAIT = 250 * result;
  }
  return result;
}

```

## disassembly

```asm
0x1800027bc  sub     rsp, 28h
0x1800027c0  cmp     rcx, 0Bh
0x1800027c4  jz      short loc_1800027CC
0x1800027c6  cmp     rcx, 17h
0x1800027ca  jnz     short loc_18000282B
0x1800027cc  xor     edx, edx; uiParam
0x1800027ce  mov     [rsp+28h+pvParam], 0
0x1800027d6  xor     r9d, r9d; fWinIni
0x1800027d9  mov     [rsp+28h+arg_8], 0
0x1800027e1  lea     r8, [rsp+28h+pvParam]; pvParam
0x1800027e6  lea     ecx, [rdx+0Ah]; uiAction
0x1800027e9  call    cs:__imp_SystemParametersInfoW
0x1800027ef  mov     eax, [rsp+28h+pvParam]
0x1800027f3  lea     r8, [rsp+28h+arg_8]; pvParam
0x1800027f8  xor     edx, edx; uiParam
0x1800027fa  xor     r9d, r9d; fWinIni
0x1800027fd  lea     ecx, [rax+rax*2]
0x180002800  mov     eax, 190h
0x180002805  shl     ecx, 2
0x180002808  sub     eax, ecx
0x18000280a  lea     ecx, [rdx+16h]; uiAction
0x18000280d  mov     cs:REPEAT_INTERVAL, eax
0x180002813  call    cs:__imp_SystemParametersInfoW
0x180002819  mov     eax, [rsp+28h+arg_8]
0x18000281d  inc     eax
0x18000281f  imul    ecx, eax, 0FAh
0x180002825  mov     cs:INITIAL_WAIT, ecx
0x18000282b  add     rsp, 28h
0x18000282f  retn
```
