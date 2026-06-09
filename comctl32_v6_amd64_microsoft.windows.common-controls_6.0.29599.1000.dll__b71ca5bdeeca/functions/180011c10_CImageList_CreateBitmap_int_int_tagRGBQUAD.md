# CImageList::_CreateBitmap(int,int,tagRGBQUAD * *)

- ea: `0x180011c10`
- end: `0x180011eab`
- name: `?_CreateBitmap@CImageList@@IEAAPEAUHBITMAP__@@HHPEAPEAUtagRGBQUAD@@@Z`
- size: `667`
- prototype: `HBITMAP(CImageList *__hidden this, int, int, struct tagRGBQUAD **)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800118a4`
- `0x1800d3848`
- `0x1800d63e8`

## callees

- `0x180011c10`
- `0x180114520`
- `0x180114ebc`

## import_xrefs

- `GDI32!DeleteObject` at `0x180011e34`
- `GDI32!DeleteObject` at `0x180011e34`
- `GDI32!GetObjectW` at `0x180011de7`
- `GDI32!GetObjectW` at `0x180011de7`
- `GDI32!CreateCompatibleBitmap` at `0x180011c89`
- `GDI32!CreateCompatibleBitmap` at `0x180011c89`
- `GDI32!CreateDIBSection` at `0x180011d9d`
- `GDI32!CreateDIBSection` at `0x180011d9d`
- `GDI32!CreateHalftonePalette` at `0x180011e0b`
- `GDI32!CreateHalftonePalette` at `0x180011e0b`
- `GDI32!GetPaletteEntries` at `0x180011e29`
- `GDI32!GetPaletteEntries` at `0x180011e29`
- `USER32!GetDC` at `0x180011c5c`
- `USER32!GetDC` at `0x180011c5c`
- `USER32!ReleaseDC` at `0x180011ca2`
- `USER32!ReleaseDC` at `0x180011ca2`

## pseudocode

```c
HBITMAP __fastcall CImageList::_CreateBitmap(CImageList *this, int a2, int a3, struct tagRGBQUAD **a4)
{
  HDC DC; // rax
  int v9; // ecx
  HDC v10; // r15
  HBITMAP CompatibleBitmap; // rax
  int v12; // ebx
  HBITMAP v13; // rdi
  WORD v15; // ax
  HPALETTE HalftonePalette; // rax
  HPALETTE v17; // rdi
  signed int PaletteEntries; // esi
  DWORD biClrUsed; // ecx
  __int64 v20; // rax
  int v21; // r8d
  __int64 v22; // rdx
  __int128 pv; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v24; // [rsp+40h] [rbp-C0h]
  BITMAPINFO pbmi; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+7Ch] [rbp-84h]
  int v27; // [rsp+80h] [rbp-80h]
  int v28; // [rsp+84h] [rbp-7Ch]
  int v29; // [rsp+88h] [rbp-78h]
  int v30; // [rsp+8Ch] [rbp-74h]
  int v31; // [rsp+90h] [rbp-70h]
  int v32; // [rsp+94h] [rbp-6Ch]
  int v33; // [rsp+98h] [rbp-68h]
  int v34; // [rsp+9Ch] [rbp-64h]
  int v35; // [rsp+A0h] [rbp-60h]
  int v36; // [rsp+A4h] [rbp-5Ch]
  int v37; // [rsp+A8h] [rbp-58h]
  int v38; // [rsp+ACh] [rbp-54h]
  int v39; // [rsp+B0h] [rbp-50h]
  int v40; // [rsp+B4h] [rbp-4Ch]

  memset_0(&pbmi, 0, 0x428u);
  DC = GetDC(0);
  v9 = *((_DWORD *)this + 34);
  v10 = DC;
  if ( (v9 & 0xFE) == 0 )
  {
    v9 |= 4u;
    *((_DWORD *)this + 34) = v9;
  }
  if ( (v9 & 0xFE) == 0xFE )
  {
    CompatibleBitmap = CreateCompatibleBitmap(DC, a2, a3);
    v12 = 0;
    v13 = CompatibleBitmap;
    if ( CompatibleBitmap )
    {
      pv = 0;
      v24 = 0;
      if ( GetObjectW(CompatibleBitmap, 32, &pv) )
      {
        LOBYTE(v12) = WORD1(v24) == 32;
        *((_DWORD *)this + 144) = v12;
      }
    }
  }
  else
  {
    pbmi.bmiHeader.biWidth = a2;
    v15 = *((_WORD *)this + 68) & 0xFE;
    pbmi.bmiHeader.biSize = 40;
    pbmi.bmiHeader.biHeight = a3;
    pbmi.bmiHeader.biPlanes = 1;
    pbmi.bmiHeader.biBitCount = v15;
    *(_QWORD *)&pbmi.bmiHeader.biCompression = 0;
    *(_QWORD *)&pbmi.bmiHeader.biXPelsPerMeter = 0;
    *(_QWORD *)&pbmi.bmiHeader.biClrUsed = 16;
    pbmi.bmiColors[0] = 0;
    v26 = 0x800000;
    v27 = 0x8000;
    v28 = 8421376;
    v29 = 128;
    v30 = 8388736;
    v31 = 32896;
    v32 = 12632256;
    v33 = 8421504;
    v34 = 16711680;
    v35 = 65280;
    v36 = 16776960;
    v37 = 255;
    v38 = 16711935;
    v39 = 0xFFFF;
    v40 = 0xFFFFFF;
    if ( v15 == 8 )
    {
      HalftonePalette = CreateHalftonePalette(0);
      v17 = HalftonePalette;
      if ( HalftonePalette )
      {
        PaletteEntries = GetPaletteEntries(HalftonePalette, 0, 0x100u, (LPPALETTEENTRY)pbmi.bmiColors);
        DeleteObject(v17);
        if ( PaletteEntries > 64 )
        {
          pbmi.bmiHeader.biClrUsed = PaletteEntries;
          v21 = 0;
          do
          {
            v22 = v21++;
            pbmi.bmiColors[v22] = (RGBQUAD)((pbmi.bmiColors[v22].rgbBlue << 16)
                                          | pbmi.bmiColors[v22].rgbRed
                                          | (pbmi.bmiColors[v22].rgbGreen << 8));
            biClrUsed = pbmi.bmiHeader.biClrUsed;
          }
          while ( v21 < (int)pbmi.bmiHeader.biClrUsed );
        }
        else
        {
          biClrUsed = pbmi.bmiHeader.biClrUsed;
        }
      }
      else
      {
        biClrUsed = 256;
        v20 = *((_WORD *)this + 68) & 0xFE;
        pbmi.bmiHeader.biClrUsed = 256;
        pbmi.bmiHeader.biBitCount = v20;
      }
      if ( biClrUsed <= 0x10 )
        pbmi.bmiHeader.biBitCount = 4;
    }
    v13 = CreateDIBSection(v10, &pbmi, 0, (void **)a4, 0, 0);
    *((_DWORD *)this + 144) = *((_DWORD *)this + 34) & 0x20;
  }
  ReleaseDC(0, v10);
  return v13;
}

```

## disassembly

```asm
0x180011c10  push    rbp
0x180011c12  push    rbx
0x180011c13  push    rsi
0x180011c14  push    rdi
0x180011c15  push    r12
0x180011c17  push    r13
0x180011c19  push    r14
0x180011c1b  push    r15
0x180011c1d  lea     rbp, [rsp-398h]
0x180011c25  sub     rsp, 498h
0x180011c2c  mov     rax, cs:__security_cookie
0x180011c33  xor     rax, rsp
0x180011c36  mov     [rbp+3D0h+var_50], rax
0x180011c3d  mov     edi, r8d
0x180011c40  mov     ebx, edx
0x180011c42  mov     r14, rcx
0x180011c45  xor     edx, edx; Val
0x180011c47  mov     r8d, 428h; Size
0x180011c4d  lea     rcx, [rsp+4D0h+pbmi]; void *
0x180011c52  mov     r12, r9
0x180011c55  call    memset_0
0x180011c5a  xor     ecx, ecx; hWnd
0x180011c5c  call    cs:__imp_GetDC
0x180011c62  mov     ecx, [r14+88h]
0x180011c69  mov     esi, 0FEh
0x180011c6e  mov     r15, rax
0x180011c71  test    sil, cl
0x180011c74  jz      loc_180011DBC
0x180011c7a  and     ecx, esi
0x180011c7c  cmp     cl, sil
0x180011c7f  jnz     short loc_180011CCE
0x180011c81  mov     r8d, edi; cy
0x180011c84  mov     edx, ebx; cx
0x180011c86  mov     rcx, r15; hdc
0x180011c89  call    cs:__imp_CreateCompatibleBitmap
0x180011c8f  xor     ebx, ebx
0x180011c91  mov     rdi, rax
0x180011c94  test    rax, rax
0x180011c97  jnz     loc_180011DCB
0x180011c9d  mov     rdx, r15; hDC
0x180011ca0  xor     ecx, ecx; hWnd
0x180011ca2  call    cs:__imp_ReleaseDC
0x180011ca8  mov     rax, rdi
0x180011cab  mov     rcx, [rbp+3D0h+var_50]
0x180011cb2  xor     rcx, rsp; StackCookie
0x180011cb5  call    __security_check_cookie
0x180011cba  add     rsp, 498h
0x180011cc1  pop     r15
0x180011cc3  pop     r14
0x180011cc5  pop     r13
0x180011cc7  pop     r12
0x180011cc9  pop     rdi
0x180011cca  pop     rsi
0x180011ccb  pop     rbx
0x180011ccc  pop     rbp
0x180011ccd  retn
0x180011cce  mov     eax, esi
0x180011cd0  mov     [rsp+4D0h+pbmi.bmiHeader.biWidth], ebx
0x180011cd4  and     ax, [r14+88h]
0x180011cdc  xor     ebx, ebx
0x180011cde  mov     [rsp+4D0h+pbmi.bmiHeader.biSize], 28h ; '('
0x180011ce6  mov     r13d, 1
0x180011cec  mov     [rsp+4D0h+pbmi.bmiHeader.biHeight], edi
0x180011cf0  mov     [rsp+4D0h+pbmi.bmiHeader.biPlanes], r13w
0x180011cf6  mov     [rsp+4D0h+pbmi.bmiHeader.biBitCount], ax
0x180011cfb  mov     qword ptr [rsp+4D0h+pbmi.bmiHeader.biCompression], rbx
0x180011d00  mov     qword ptr [rsp+4D0h+pbmi.bmiHeader.biXPelsPerMeter], rbx
0x180011d05  mov     qword ptr [rsp+4D0h+pbmi.bmiHeader.biClrUsed], 10h
0x180011d0e  mov     dword ptr [rsp+4D0h+pbmi.bmiColors.rgbBlue], ebx
0x180011d12  mov     [rsp+4D0h+var_454], 800000h
0x180011d1a  mov     [rbp+3D0h+var_450], 8000h
0x180011d21  mov     [rbp+3D0h+var_44C], 808000h
0x180011d28  mov     [rbp+3D0h+var_448], 80h
0x180011d2f  mov     [rbp+3D0h+var_444], 800080h
0x180011d36  mov     [rbp+3D0h+var_440], 8080h
0x180011d3d  mov     [rbp+3D0h+var_43C], 0C0C0C0h
0x180011d44  mov     [rbp+3D0h+var_438], 808080h
0x180011d4b  mov     [rbp+3D0h+var_434], 0FF0000h
0x180011d52  mov     [rbp+3D0h+var_430], 0FF00h
0x180011d59  mov     [rbp+3D0h+var_42C], 0FFFF00h
0x180011d60  mov     [rbp+3D0h+var_428], 0FFh
0x180011d67  mov     [rbp+3D0h+var_424], 0FF00FFh
0x180011d6e  mov     [rbp+3D0h+var_420], 0FFFFh
0x180011d75  mov     [rbp+3D0h+var_41C], 0FFFFFFh
0x180011d7c  cmp     ax, 8
0x180011d80  jz      loc_180011E09
0x180011d86  mov     [rsp+4D0h+offset], ebx; offset
0x180011d8a  lea     rdx, [rsp+4D0h+pbmi]; pbmi
0x180011d8f  mov     r9, r12; ppvBits
0x180011d92  mov     [rsp+4D0h+hSection], rbx; hSection
0x180011d97  xor     r8d, r8d; usage
0x180011d9a  mov     rcx, r15; hdc
0x180011d9d  call    cs:__imp_CreateDIBSection
0x180011da3  mov     ecx, [r14+88h]
0x180011daa  mov     rdi, rax
0x180011dad  and     ecx, 20h
0x180011db0  mov     [r14+240h], ecx
0x180011db7  jmp     loc_180011C9D
0x180011dbc  or      ecx, 4
0x180011dbf  mov     [r14+88h], ecx
0x180011dc6  jmp     loc_180011C7A
0x180011dcb  xorps   xmm0, xmm0
0x180011dce  lea     r8, [rsp+4D0h+pv]; pv
0x180011dd3  mov     esi, 20h ; ' '
0x180011dd8  mov     rcx, rax; h
0x180011ddb  mov     edx, esi; c
0x180011ddd  movups  [rsp+4D0h+pv], xmm0
0x180011de2  movups  [rsp+4D0h+var_490], xmm0
0x180011de7  call    cs:__imp_GetObjectW
0x180011ded  test    eax, eax
0x180011def  jz      loc_180011C9D
0x180011df5  cmp     word ptr [rsp+4D0h+var_490+2], si
0x180011dfa  setz    bl
0x180011dfd  mov     [r14+240h], ebx
0x180011e04  jmp     loc_180011C9D
0x180011e09  xor     ecx, ecx; hdc
0x180011e0b  call    cs:__imp_CreateHalftonePalette
0x180011e11  mov     rdi, rax
0x180011e14  test    rax, rax
0x180011e17  jz      short loc_180011E5B
0x180011e19  lea     r9, [rsp+4D0h+pbmi.bmiColors]; pPalEntries
0x180011e1e  xor     edx, edx; iStart
0x180011e20  mov     r8d, 100h; cEntries
0x180011e26  mov     rcx, rax; hpal
0x180011e29  call    cs:__imp_GetPaletteEntries
0x180011e2f  mov     rcx, rdi; ho
0x180011e32  mov     esi, eax
0x180011e34  call    cs:__imp_DeleteObject
0x180011e3a  cmp     esi, 40h ; '@'
0x180011e3d  jg      short loc_180011E76
0x180011e3f  mov     ecx, [rsp+4D0h+pbmi.bmiHeader.biClrUsed]
0x180011e43  cmp     ecx, 10h
0x180011e46  ja      loc_180011D86
0x180011e4c  mov     eax, 4
0x180011e51  mov     [rsp+4D0h+pbmi.bmiHeader.biBitCount], ax
0x180011e56  jmp     loc_180011D86
0x180011e5b  movzx   eax, word ptr [r14+88h]
0x180011e63  mov     ecx, 100h
0x180011e68  and     ax, si
0x180011e6b  mov     [rsp+4D0h+pbmi.bmiHeader.biClrUsed], ecx
0x180011e6f  mov     [rsp+4D0h+pbmi.bmiHeader.biBitCount], ax
0x180011e74  jmp     short loc_180011E43
0x180011e76  mov     [rsp+4D0h+pbmi.bmiHeader.biClrUsed], esi
0x180011e7a  mov     r8d, ebx
0x180011e7d  movsxd  rdx, r8d
0x180011e80  add     r8d, r13d
0x180011e83  movzx   eax, [rsp+rdx*4+4D0h+pbmi.bmiColors.rgbRed]
0x180011e88  movzx   ecx, [rsp+rdx*4+4D0h+pbmi.bmiColors.rgbGreen]
0x180011e8d  shl     ecx, 8
0x180011e90  or      ecx, eax
0x180011e92  movzx   eax, [rsp+rdx*4+4D0h+pbmi.bmiColors.rgbBlue]
0x180011e97  shl     eax, 10h
0x180011e9a  or      ecx, eax
0x180011e9c  mov     dword ptr [rsp+rdx*4+4D0h+pbmi.bmiColors.rgbBlue], ecx
0x180011ea0  mov     ecx, [rsp+4D0h+pbmi.bmiHeader.biClrUsed]
0x180011ea4  cmp     r8d, ecx
0x180011ea7  jl      short loc_180011E7D
0x180011ea9  jmp     short loc_180011E43
```
