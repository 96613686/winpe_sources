# PaletteFromBmp

- ea: `0x18001e31c`
- end: `0x18001e423`
- name: `PaletteFromBmp`
- size: `263`
- prototype: `__int64 __fastcall(HGDIOBJ h)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001c47c`

## callees

- `0x1800115f0`
- `0x18001e31c`
- `0x18008ea60`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x18001e359`
- `GDI32!CreateCompatibleDC` at `0x18001e359`
- `GDI32!SelectObject` at `0x18001e371`
- `GDI32!SelectObject` at `0x18001e371`
- `GDI32!DeleteDC` at `0x18001e3f5`
- `GDI32!DeleteDC` at `0x18001e3f5`
- `GDI32!GetDIBColorTable` at `0x18001e387`
- `GDI32!GetDIBColorTable` at `0x18001e387`
- `GDI32!CreatePalette` at `0x18001e3de`
- `GDI32!CreatePalette` at `0x18001e3de`
- `GDI32!CreateHalftonePalette` at `0x18001e3e9`
- `GDI32!CreateHalftonePalette` at `0x18001e3e9`

## pseudocode

```c
HPALETTE __fastcall PaletteFromBmp(HGDIOBJ h)
{
  HPALETTE v2; // rbx
  HDC CompatibleDC; // rax
  HDC v4; // rdi
  signed int DIBColorTable; // eax
  __int64 i; // r8
  HPALETTE Palette; // rax
  PALETTEENTRY v9; // [rsp+20h] [rbp-438h]
  LOGPALETTE plpal[130]; // [rsp+30h] [rbp-428h] BYREF

  memset(plpal, 0, 0x404u);
  v2 = 0;
  CompatibleDC = CreateCompatibleDC(0);
  v4 = CompatibleDC;
  if ( CompatibleDC )
  {
    SelectObject(CompatibleDC, h);
    DIBColorTable = GetDIBColorTable(v4, 0, 0x100u, (RGBQUAD *)plpal[0].palPalEntry);
    if ( DIBColorTable )
    {
      for ( i = 0; (int)i < DIBColorTable; i = (unsigned int)(i + 1) )
      {
        v9.peRed = plpal[0].palPalEntry[i].peBlue;
        v9.peGreen = plpal[0].palPalEntry[i].peGreen;
        *(_WORD *)&v9.peBlue = plpal[0].palPalEntry[i].peRed;
        plpal[0].palPalEntry[i] = v9;
      }
      plpal[0].palNumEntries = DIBColorTable;
      plpal[0].palVersion = 768;
      Palette = CreatePalette(plpal);
    }
    else
    {
      Palette = CreateHalftonePalette(v4);
    }
    v2 = Palette;
    DeleteDC(v4);
  }
  return v2;
}

```

## disassembly

```asm
0x18001e31c  mov     [rsp+arg_8], rbx
0x18001e321  mov     [rsp+arg_10], rsi
0x18001e326  push    rdi
0x18001e327  sub     rsp, 450h
0x18001e32e  mov     rax, cs:__security_cookie
0x18001e335  xor     rax, rsp
0x18001e338  mov     [rsp+458h+var_18], rax
0x18001e340  mov     rsi, rcx
0x18001e343  xor     edx, edx; Val
0x18001e345  lea     rcx, [rsp+458h+plpal]; void *
0x18001e34a  mov     r8d, 404h; Size
0x18001e350  call    memset
0x18001e355  xor     ecx, ecx; hdc
0x18001e357  xor     ebx, ebx
0x18001e359  call    cs:__imp_CreateCompatibleDC
0x18001e35f  mov     rdi, rax
0x18001e362  test    rax, rax
0x18001e365  jz      loc_18001E3FB
0x18001e36b  mov     rdx, rsi; h
0x18001e36e  mov     rcx, rax; hdc
0x18001e371  call    cs:__imp_SelectObject
0x18001e377  lea     r9, [rsp+458h+plpal.palPalEntry]; prgbq
0x18001e37c  xor     edx, edx; iStart
0x18001e37e  mov     r8d, 100h; cEntries
0x18001e384  mov     rcx, rdi; hdc
0x18001e387  call    cs:__imp_GetDIBColorTable
0x18001e38d  mov     edx, eax
0x18001e38f  test    eax, eax
0x18001e391  jz      short loc_18001E3E6
0x18001e393  xor     r8d, r8d
0x18001e396  test    eax, eax
0x18001e398  jle     short loc_18001E3CA
0x18001e39a  mov     al, [rsp+r8*4+458h+plpal.palPalEntry.peBlue]
0x18001e39f  mov     [rsp+458h+var_438.peRed], al
0x18001e3a3  mov     al, [rsp+r8*4+458h+plpal.palPalEntry.peGreen]
0x18001e3a8  mov     [rsp+458h+var_438.peGreen], al
0x18001e3ac  mov     al, [rsp+r8*4+458h+plpal.palPalEntry.peRed]
0x18001e3b1  mov     [rsp+458h+var_438.peBlue], al
0x18001e3b5  mov     [rsp+458h+var_438.peFlags], bl
0x18001e3b9  mov     eax, dword ptr [rsp+458h+var_438.peRed]
0x18001e3bd  mov     dword ptr [rsp+r8*4+458h+plpal.palPalEntry.peRed], eax
0x18001e3c2  inc     r8d
0x18001e3c5  cmp     r8d, edx
0x18001e3c8  jl      short loc_18001E39A
0x18001e3ca  mov     eax, 300h
0x18001e3cf  mov     [rsp+458h+plpal.palNumEntries], dx
0x18001e3d4  lea     rcx, [rsp+458h+plpal]; plpal
0x18001e3d9  mov     [rsp+458h+plpal.palVersion], ax
0x18001e3de  call    cs:__imp_CreatePalette
0x18001e3e4  jmp     short loc_18001E3EF
0x18001e3e6  mov     rcx, rdi; hdc
0x18001e3e9  call    cs:__imp_CreateHalftonePalette
0x18001e3ef  mov     rcx, rdi; hdc
0x18001e3f2  mov     rbx, rax
0x18001e3f5  call    cs:__imp_DeleteDC
0x18001e3fb  mov     rax, rbx
0x18001e3fe  mov     rcx, [rsp+458h+var_18]
0x18001e406  xor     rcx, rsp; StackCookie
0x18001e409  call    __security_check_cookie
0x18001e40e  lea     r11, [rsp+458h+var_8]
0x18001e416  mov     rbx, [r11+18h]
0x18001e41a  mov     rsi, [r11+20h]
0x18001e41e  mov     rsp, r11
0x18001e421  pop     rdi
0x18001e422  retn
```
