# CMCreateTransformExt

- ea: `0x18001d780`
- end: `0x18001d799`
- name: `CMCreateTransformExt`
- size: `25`
- prototype: `HCMTRANSFORM __stdcall(LPLOGCOLORSPACEW lpColorSpace, LPDEVCHARACTER lpDevCharacter, LPDEVCHARACTER lpTargetDevCharacter)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d789`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d789`

## pseudocode

```c
HCMTRANSFORM __stdcall CMCreateTransformExt(
        LPLOGCOLORSPACEW lpColorSpace,
        LPDEVCHARACTER lpDevCharacter,
        LPDEVCHARACTER lpTargetDevCharacter)
{
  SetLastError(0x32u);
  return (HCMTRANSFORM)50;
}

```

## disassembly

```asm
0x18001d780  sub     rsp, 28h; CMCreateTransform
0x18001d784  mov     ecx, 32h ; '2'; dwErrCode
0x18001d789  call    cs:__imp_SetLastError
0x18001d78f  mov     eax, 32h ; '2'
0x18001d794  add     rsp, 28h
0x18001d798  retn
```
