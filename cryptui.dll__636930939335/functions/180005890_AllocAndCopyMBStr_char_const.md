# AllocAndCopyMBStr(char const *)

- ea: `0x180005890`
- end: `0x180005903`
- name: `?AllocAndCopyMBStr@@YAPEADPEBD@Z`
- size: `115`
- prototype: `char *__fastcall(const char *Src)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180026608`
- `0x180027a80`

## callees

- `0x180001f66`
- `0x180005890`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800058c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800058c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800058d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800058d8`

## pseudocode

```c
char *__fastcall AllocAndCopyMBStr(const char *Src)
{
  __int64 v2; // rax
  SIZE_T v3; // rsi
  HLOCAL v4; // rax
  HLOCAL v5; // rdi

  if ( Src )
  {
    v2 = -1;
    do
      ++v2;
    while ( Src[v2] );
  }
  else
  {
    LODWORD(v2) = 0;
  }
  v3 = (int)v2 + 1;
  v4 = LocalAlloc(0x40u, v3);
  v5 = v4;
  if ( v4 )
  {
    memcpy_0(v4, Src, v3);
    return (char *)v5;
  }
  else
  {
    SetLastError(0x8007000E);
    return 0;
  }
}

```

## disassembly

```asm
0x180005890  mov     [rsp+arg_0], rbx
0x180005895  mov     [rsp+arg_8], rsi
0x18000589a  push    rdi
0x18000589b  sub     rsp, 20h
0x18000589f  mov     rbx, rcx
0x1800058a2  test    rcx, rcx
0x1800058a5  jz      short loc_1800058B6
0x1800058a7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800058ab  inc     rax
0x1800058ae  cmp     byte ptr [rcx+rax], 0
0x1800058b2  jnz     short loc_1800058AB
0x1800058b4  jmp     short loc_1800058B8
0x1800058b6  xor     eax, eax
0x1800058b8  inc     eax
0x1800058ba  mov     ecx, 40h ; '@'; uFlags
0x1800058bf  movsxd  rsi, eax
0x1800058c2  mov     rdx, rsi; uBytes
0x1800058c5  call    cs:__imp_LocalAlloc
0x1800058cb  mov     rdi, rax
0x1800058ce  test    rax, rax
0x1800058d1  jnz     short loc_1800058E2
0x1800058d3  mov     ecx, 8007000Eh; dwErrCode
0x1800058d8  call    cs:__imp_SetLastError
0x1800058de  xor     eax, eax
0x1800058e0  jmp     short loc_1800058F3
0x1800058e2  mov     r8, rsi; Size
0x1800058e5  mov     rdx, rbx; Src
0x1800058e8  mov     rcx, rdi; void *
0x1800058eb  call    memcpy_0
0x1800058f0  mov     rax, rdi
0x1800058f3  mov     rbx, [rsp+28h+arg_0]
0x1800058f8  mov     rsi, [rsp+28h+arg_8]
0x1800058fd  add     rsp, 20h
0x180005901  pop     rdi
0x180005902  retn
```
