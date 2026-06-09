# PkiRealloc

- ea: `0x1800077e4`
- end: `0x18000781f`
- name: `PkiRealloc`
- size: `59`
- prototype: `HLOCAL __fastcall(void *, SIZE_T)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001100`
- `0x180004e70`

## callees

- `0x1800077e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007810`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007810`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800077fd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800077fd`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1800077f5`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1800077f5`

## pseudocode

```c
HLOCAL __fastcall PkiRealloc(void *a1, SIZE_T a2)
{
  HLOCAL v2; // rax
  HLOCAL v3; // rbx

  if ( a1 )
    v2 = LocalReAlloc(a1, a2, 2u);
  else
    v2 = LocalAlloc(0, a2);
  v3 = v2;
  if ( !v2 )
    SetLastError(0x8007000E);
  return v3;
}

```

## disassembly

```asm
0x1800077e4  push    rbx
0x1800077e6  sub     rsp, 20h
0x1800077ea  test    rcx, rcx
0x1800077ed  jz      short loc_1800077FD
0x1800077ef  mov     r8d, 2; uFlags
0x1800077f5  call    cs:__imp_LocalReAlloc
0x1800077fb  jmp     short loc_180007803
0x1800077fd  call    cs:__imp_LocalAlloc
0x180007803  mov     rbx, rax
0x180007806  test    rax, rax
0x180007809  jnz     short loc_180007816
0x18000780b  mov     ecx, 8007000Eh; dwErrCode
0x180007810  call    cs:__imp_SetLastError
0x180007816  mov     rax, rbx
0x180007819  add     rsp, 20h
0x18000781d  pop     rbx
0x18000781e  retn
```
