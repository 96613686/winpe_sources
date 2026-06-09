# CreateBIPalette

- ea: `0x18000824c`
- end: `0x180008376`
- name: `CreateBIPalette`
- size: `298`
- prototype: `__int64 __fastcall(HPALETTE hpal)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008400`

## callees

- `0x1800014b0`
- `0x180001d62`
- `0x18000824c`

## import_xrefs

- `GDI32!ResizePalette` at `0x18000831f`
- `GDI32!ResizePalette` at `0x18000831f`
- `GDI32!CreatePalette` at `0x180008342`
- `GDI32!CreatePalette` at `0x180008342`
- `GDI32!SetPaletteEntries` at `0x180008335`
- `GDI32!SetPaletteEntries` at `0x180008335`

## pseudocode

```c
HPALETTE __fastcall CreateBIPalette(HPALETTE hpal, __int64 a2)
{
  WORD palNumEntries; // r8
  unsigned __int16 v5; // cx
  int v6; // edx
  __int64 v7; // rcx
  LOGPALETTE plpal; // [rsp+20h] [rbp-E0h] BYREF

  memset_0(&plpal.palNumEntries, 0, 0x402u);
  palNumEntries = *(_WORD *)(a2 + 32);
  plpal.palNumEntries = palNumEntries;
  plpal.palVersion = 768;
  if ( !palNumEntries )
  {
    v5 = *(_WORD *)(a2 + 14);
    if ( v5 <= 8u )
    {
      palNumEntries = 1 << v5;
      plpal.palNumEntries = 1 << v5;
    }
  }
  if ( (unsigned __int16)(palNumEntries - 1) > 0xFFu )
    return 0;
  v6 = 0;
  if ( palNumEntries )
  {
    do
    {
      v7 = v6++;
      plpal.palPalEntry[v7].peRed = *(_BYTE *)(a2 + 4 * v7 + 42);
      plpal.palPalEntry[v7].peGreen = *(_BYTE *)(a2 + 4 * v7 + 41);
      plpal.palPalEntry[v7].peBlue = *(_BYTE *)(a2 + 4 * v7 + 40);
      plpal.palPalEntry[v7].peFlags = 0;
      palNumEntries = plpal.palNumEntries;
    }
    while ( v6 < plpal.palNumEntries );
  }
  if ( !hpal )
    return CreatePalette(&plpal);
  ResizePalette(hpal, palNumEntries);
  SetPaletteEntries(hpal, 0, plpal.palNumEntries, plpal.palPalEntry);
  return hpal;
}

```

## disassembly

```asm
0x18000824c  mov     [rsp-8+arg_10], rbx
0x180008251  mov     [rsp-8+arg_18], rdi
0x180008256  push    rbp
0x180008257  lea     rbp, [rsp-340h]
0x18000825f  sub     rsp, 440h
0x180008266  mov     rax, cs:__security_cookie
0x18000826d  xor     rax, rsp
0x180008270  mov     [rbp+340h+var_10], rax
0x180008277  mov     rdi, rdx
0x18000827a  mov     rbx, rcx
0x18000827d  xor     edx, edx; Val
0x18000827f  lea     rcx, [rsp+440h+plpal.palNumEntries]; void *
0x180008284  mov     r8d, 402h; Size
0x18000828a  call    memset_0
0x18000828f  movzx   r8d, word ptr [rdi+20h]
0x180008294  xor     r9d, r9d
0x180008297  mov     [rsp+440h+plpal.palNumEntries], r8w
0x18000829d  mov     eax, 300h
0x1800082a2  mov     [rsp+440h+plpal.palVersion], ax
0x1800082a7  mov     r10d, 1
0x1800082ad  test    r8w, r8w
0x1800082b1  jnz     short loc_1800082CA
0x1800082b3  movzx   ecx, word ptr [rdi+0Eh]
0x1800082b7  cmp     cx, 8
0x1800082bb  ja      short loc_1800082CA
0x1800082bd  mov     r8d, r10d
0x1800082c0  shl     r8w, cl
0x1800082c4  mov     [rsp+440h+plpal.palNumEntries], r8w
0x1800082ca  movzx   eax, r8w
0x1800082ce  mov     ecx, 0FFh
0x1800082d3  sub     ax, r10w
0x1800082d7  cmp     ax, cx
0x1800082da  ja      short loc_180008350
0x1800082dc  mov     edx, r9d
0x1800082df  cmp     r9w, r8w
0x1800082e3  jnb     short loc_180008313
0x1800082e5  movsxd  rcx, edx
0x1800082e8  add     edx, r10d
0x1800082eb  mov     al, [rdi+rcx*4+2Ah]
0x1800082ef  mov     [rsp+rcx*4+440h+plpal.palPalEntry.peRed], al
0x1800082f3  mov     al, [rdi+rcx*4+29h]
0x1800082f7  mov     [rsp+rcx*4+440h+plpal.palPalEntry.peGreen], al
0x1800082fb  mov     al, [rdi+rcx*4+28h]
0x1800082ff  mov     [rsp+rcx*4+440h+plpal.palPalEntry.peBlue], al
0x180008303  mov     [rsp+rcx*4+440h+plpal.palPalEntry.peFlags], r9b
0x180008308  movzx   r8d, [rsp+440h+plpal.palNumEntries]
0x18000830e  cmp     edx, r8d
0x180008311  jl      short loc_1800082E5
0x180008313  test    rbx, rbx
0x180008316  jz      short loc_18000833D
0x180008318  movzx   edx, r8w; n
0x18000831c  mov     rcx, rbx; hpal
0x18000831f  call    cs:__imp_ResizePalette
0x180008325  movzx   r8d, [rsp+440h+plpal.palNumEntries]; cEntries
0x18000832b  lea     r9, [rsp+440h+plpal.palPalEntry]; pPalEntries
0x180008330  xor     edx, edx; iStart
0x180008332  mov     rcx, rbx; hpal
0x180008335  call    cs:__imp_SetPaletteEntries
0x18000833b  jmp     short loc_18000834B
0x18000833d  lea     rcx, [rsp+440h+plpal]; plpal
0x180008342  call    cs:__imp_CreatePalette
0x180008348  mov     rbx, rax
0x18000834b  mov     rax, rbx
0x18000834e  jmp     short loc_180008352
0x180008350  xor     eax, eax
0x180008352  mov     rcx, [rbp+340h+var_10]
0x180008359  xor     rcx, rsp; StackCookie
0x18000835c  call    __security_check_cookie
0x180008361  lea     r11, [rsp+440h+var_s0]
0x180008369  mov     rbx, [r11+20h]
0x18000836d  mov     rdi, [r11+28h]
0x180008371  mov     rsp, r11
0x180008374  pop     rbp
0x180008375  retn
```
