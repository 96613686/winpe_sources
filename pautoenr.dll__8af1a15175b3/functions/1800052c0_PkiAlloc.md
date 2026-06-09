# PkiAlloc

- ea: `0x1800052c0`
- end: `0x1800052f0`
- name: `PkiAlloc`
- size: `48`
- prototype: `HLOCAL __fastcall(SIZE_T uBytes)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001100`
- `0x180004e70`
- `0x180007798`

## callees

- `0x1800052c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800052e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800052e1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800052ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800052ce`

## pseudocode

```c
HLOCAL __fastcall PkiAlloc(SIZE_T uBytes)
{
  HLOCAL result; // rax

  result = LocalAlloc(0x40u, uBytes);
  if ( !result )
  {
    SetLastError(0x8007000E);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800052c0  push    rbx
0x1800052c2  sub     rsp, 20h
0x1800052c6  mov     rdx, rcx; uBytes
0x1800052c9  mov     ecx, 40h ; '@'; uFlags
0x1800052ce  call    cs:__imp_LocalAlloc
0x1800052d4  mov     rbx, rax
0x1800052d7  test    rax, rax
0x1800052da  jnz     short loc_1800052EA
0x1800052dc  mov     ecx, 8007000Eh; dwErrCode
0x1800052e1  call    cs:__imp_SetLastError
0x1800052e7  mov     rax, rbx
0x1800052ea  add     rsp, 20h
0x1800052ee  pop     rbx
0x1800052ef  retn
```
