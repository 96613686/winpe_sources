# CMCreateProfile

- ea: `0x18001d4d0`
- end: `0x18001d4e6`
- name: `CMCreateProfile`
- size: `22`
- prototype: `BOOL __stdcall(HCMTRANSFORM hcmTransform, LPVOID lpSrcBits, BMFORMAT bmInput, DWORD dwWidth, DWORD dwHeight, DWORD dwStride, LPVOID lpDestBits, BMFORMAT bmOutput, DWORD dwTranslateDirection)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d4d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d4d9`

## pseudocode

```c
BOOL __stdcall CMCreateProfile(
        HCMTRANSFORM hcmTransform,
        LPVOID lpSrcBits,
        BMFORMAT bmInput,
        DWORD dwWidth,
        DWORD dwHeight,
        DWORD dwStride,
        LPVOID lpDestBits,
        BMFORMAT bmOutput,
        DWORD dwTranslateDirection)
{
  SetLastError(0x32u);
  return 0;
}

```

## disassembly

```asm
0x18001d4d0  sub     rsp, 28h; CMCheckColorsInGamut
0x18001d4d4  mov     ecx, 32h ; '2'; dwErrCode
0x18001d4d9  call    cs:__imp_SetLastError
0x18001d4df  xor     eax, eax
0x18001d4e1  add     rsp, 28h
0x18001d4e5  retn
```
