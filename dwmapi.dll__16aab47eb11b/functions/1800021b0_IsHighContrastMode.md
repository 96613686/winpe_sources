# IsHighContrastMode

- ea: `0x1800021b0`
- end: `0x1800021f5`
- name: `IsHighContrastMode`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002110`

## callees

- `0x1800021b0`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x1800021d6`
- `USER32!SystemParametersInfoW` at `0x1800021d6`

## pseudocode

```c
_BOOL8 IsHighContrastMode()
{
  __int128 pvParam; // [rsp+20h] [rbp-18h] BYREF

  pvParam = 0;
  LODWORD(pvParam) = 16;
  return SystemParametersInfoW(0x42u, 0x10u, &pvParam, 0) && (BYTE4(pvParam) & 1) != 0;
}

```

## disassembly

```asm
0x1800021b0  sub     rsp, 38h
0x1800021b4  xorps   xmm0, xmm0
0x1800021b7  lea     r8, [rsp+38h+pvParam]; pvParam
0x1800021bc  movups  [rsp+38h+pvParam], xmm0
0x1800021c1  xor     r9d, r9d; fWinIni
0x1800021c4  mov     dword ptr [rsp+38h+pvParam], 10h
0x1800021cc  mov     edx, 10h; uiParam
0x1800021d1  mov     ecx, 42h ; 'B'; uiAction
0x1800021d6  call    cs:__imp_SystemParametersInfoW
0x1800021dc  test    eax, eax
0x1800021de  jz      short loc_1800021F1
0x1800021e0  test    byte ptr [rsp+38h+pvParam+4], 1
0x1800021e5  jz      short loc_1800021F1
0x1800021e7  mov     eax, 1
0x1800021ec  add     rsp, 38h
0x1800021f0  retn
0x1800021f1  xor     eax, eax
0x1800021f3  jmp     short loc_1800021EC
```
