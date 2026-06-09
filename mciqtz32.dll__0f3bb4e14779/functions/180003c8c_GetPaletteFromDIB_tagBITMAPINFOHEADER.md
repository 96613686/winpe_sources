# GetPaletteFromDIB(tagBITMAPINFOHEADER *)

- ea: `0x180003c8c`
- end: `0x180003d3a`
- name: `?GetPaletteFromDIB@@YAPEAUHPALETTE__@@PEAUtagBITMAPINFOHEADER@@@Z`
- size: `174`
- prototype: `HPALETTE __fastcall(struct tagBITMAPINFOHEADER *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003d40`

## callees

- `0x180001008`
- `0x180001014`
- `0x180003c8c`

## import_xrefs

- `GDI32!CreatePalette` at `0x180003d19`
- `GDI32!CreatePalette` at `0x180003d19`

## pseudocode

```c
HPALETTE __fastcall GetPaletteFromDIB(struct tagBITMAPINFOHEADER *a1)
{
  WORD biBitCount; // cx
  HPALETTE Palette; // rbp
  WORD biClrUsed; // bx
  __int64 biSize; // r14
  LOGPALETTE *v6; // rax
  LOGPALETTE *v7; // rdi
  BYTE *v8; // rcx
  PALETTEENTRY *palPalEntry; // rdx
  BYTE v10; // al

  biBitCount = a1->biBitCount;
  Palette = 0;
  if ( biBitCount >= 0x10u || a1->biClrUsed )
    biClrUsed = a1->biClrUsed;
  else
    biClrUsed = 1 << biBitCount;
  if ( biClrUsed )
  {
    biSize = a1->biSize;
    v6 = (LOGPALETTE *)operator new[](4LL * biClrUsed + 4);
    v7 = v6;
    if ( v6 )
    {
      v8 = (BYTE *)a1 + biSize;
      v6->palVersion = 768;
      v6->palNumEntries = biClrUsed;
      palPalEntry = v6->palPalEntry;
      do
      {
        palPalEntry->peFlags = 4;
        palPalEntry->peRed = v8[2];
        ++palPalEntry;
        palPalEntry[-1].peGreen = v8[1];
        v10 = *v8;
        v8 += 4;
        palPalEntry[-1].peBlue = v10;
        --biClrUsed;
      }
      while ( biClrUsed );
      Palette = CreatePalette(v7);
    }
    operator delete[](v7);
  }
  return Palette;
}

```

## disassembly

```asm
0x180003c8c  push    rbx
0x180003c8e  push    rbp
0x180003c8f  push    rsi
0x180003c90  push    rdi
0x180003c91  push    r14
0x180003c93  push    r15
0x180003c95  sub     rsp, 28h
0x180003c99  xor     r15d, r15d
0x180003c9c  mov     rsi, rcx
0x180003c9f  movzx   ecx, word ptr [rcx+0Eh]
0x180003ca3  mov     ebp, r15d
0x180003ca6  cmp     cx, 10h
0x180003caa  jnb     short loc_180003CBB
0x180003cac  cmp     [rsi+20h], r15d
0x180003cb0  jnz     short loc_180003CBB
0x180003cb2  lea     ebx, [r15+1]
0x180003cb6  shl     bx, cl
0x180003cb9  jmp     short loc_180003CBF
0x180003cbb  movzx   ebx, word ptr [rsi+20h]
0x180003cbf  test    bx, bx
0x180003cc2  jz      short loc_180003D2A
0x180003cc4  mov     r14d, [rsi]
0x180003cc7  movzx   ecx, bx
0x180003cca  lea     rcx, ds:4[rcx*4]; unsigned __int64
0x180003cd2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003cd7  mov     rdi, rax
0x180003cda  test    rax, rax
0x180003cdd  jz      short loc_180003D22
0x180003cdf  lea     rcx, [rsi+r14]
0x180003ce3  mov     word ptr [rax], 300h
0x180003ce8  mov     [rax+2], bx
0x180003cec  lea     rdx, [rax+4]
0x180003cf0  mov     byte ptr [rdx+3], 4
0x180003cf4  mov     al, [rcx+2]
0x180003cf7  mov     [rdx], al
0x180003cf9  lea     rdx, [rdx+4]
0x180003cfd  mov     al, [rcx+1]
0x180003d00  mov     [rdx-3], al
0x180003d03  mov     al, [rcx]
0x180003d05  lea     rcx, [rcx+4]
0x180003d09  mov     [rdx-2], al
0x180003d0c  mov     eax, 0FFFFh
0x180003d11  add     bx, ax
0x180003d14  jnz     short loc_180003CF0
0x180003d16  mov     rcx, rdi; plpal
0x180003d19  call    cs:__imp_CreatePalette
0x180003d1f  mov     rbp, rax
0x180003d22  mov     rcx, rdi; void *
0x180003d25  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180003d2a  mov     rax, rbp
0x180003d2d  add     rsp, 28h
0x180003d31  pop     r15
0x180003d33  pop     r14
0x180003d35  pop     rdi
0x180003d36  pop     rsi
0x180003d37  pop     rbp
0x180003d38  pop     rbx
0x180003d39  retn
```
