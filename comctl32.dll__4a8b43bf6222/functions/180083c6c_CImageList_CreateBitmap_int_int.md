# CImageList::_CreateBitmap(int,int)

- ea: `0x180083c6c`
- end: `0x180083ec7`
- name: `?_CreateBitmap@CImageList@@QEAAPEAUHBITMAP__@@HH@Z`
- size: `603`
- prototype: `HBITMAP __fastcall(CImageList *this, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180084468`

## callees

- `0x1800115f0`
- `0x180083c6c`
- `0x18008ea60`

## import_xrefs

- `GDI32!GetPaletteEntries` at `0x180083dec`
- `GDI32!GetPaletteEntries` at `0x180083dec`
- `GDI32!CreateDIBSection` at `0x180083e7f`
- `GDI32!CreateDIBSection` at `0x180083e7f`
- `GDI32!CreateCompatibleBitmap` at `0x180083ccf`
- `GDI32!CreateCompatibleBitmap` at `0x180083e8f`
- `GDI32!CreateCompatibleBitmap` at `0x180083ccf`
- `GDI32!CreateCompatibleBitmap` at `0x180083e8f`
- `GDI32!DeleteObject` at `0x180083df7`
- `GDI32!DeleteObject` at `0x180083df7`
- `GDI32!CreateHalftonePalette` at `0x180083dce`
- `GDI32!CreateHalftonePalette` at `0x180083dce`
- `USER32!GetDC` at `0x180083cdc`
- `USER32!GetDC` at `0x180083cdc`
- `USER32!ReleaseDC` at `0x180083e9d`
- `USER32!ReleaseDC` at `0x180083e9d`

## pseudocode

```c
HBITMAP __fastcall CImageList::_CreateBitmap(CImageList *this, int a2, int a3)
{
  HDC v6; // rcx
  HDC DC; // rax
  int v9; // ecx
  HDC v10; // r14
  __int16 v11; // ax
  HPALETTE HalftonePalette; // rax
  HPALETTE v13; // rdi
  signed int PaletteEntries; // ebx
  int v15; // r8d
  __int64 v16; // rdx
  unsigned int v17; // ecx
  __int64 v18; // rax
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v20; // rbx
  void *ppvBits; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE pbmi[1064]; // [rsp+40h] [rbp-C0h] BYREF

  ppvBits = 0;
  memset(pbmi, 0, sizeof(pbmi));
  if ( *((_QWORD *)this + 13) )
  {
    v6 = (HDC)*((_QWORD *)this + 15);
    if ( v6 )
      return CreateCompatibleBitmap(v6, a2, a3);
  }
  DC = GetDC(0);
  v9 = *((_DWORD *)this + 20);
  v10 = DC;
  if ( (v9 & 0xFE) == 0 )
  {
    v9 |= 4u;
    *((_DWORD *)this + 20) = v9;
  }
  if ( (v9 & 0xFE) == 0xFE )
  {
    CompatibleBitmap = CreateCompatibleBitmap(DC, a2, a3);
  }
  else
  {
    *(_DWORD *)&pbmi[8] = a3;
    v11 = *((_WORD *)this + 40) & 0xFE;
    *(_DWORD *)pbmi = 40;
    *(_DWORD *)&pbmi[4] = a2;
    *(_WORD *)&pbmi[12] = 1;
    *(_WORD *)&pbmi[14] = v11;
    *(_QWORD *)&pbmi[16] = 0;
    *(_QWORD *)&pbmi[24] = 0;
    *(_QWORD *)&pbmi[32] = 16;
    *(_DWORD *)&pbmi[40] = 0;
    *(_DWORD *)&pbmi[44] = 0x800000;
    *(_DWORD *)&pbmi[48] = 0x8000;
    *(_DWORD *)&pbmi[52] = 8421376;
    *(_DWORD *)&pbmi[56] = 128;
    *(_DWORD *)&pbmi[60] = 8388736;
    *(_DWORD *)&pbmi[64] = 32896;
    *(_DWORD *)&pbmi[68] = 12632256;
    *(_DWORD *)&pbmi[72] = 8421504;
    *(_DWORD *)&pbmi[76] = 16711680;
    *(_DWORD *)&pbmi[80] = 65280;
    *(_DWORD *)&pbmi[84] = 16776960;
    *(_DWORD *)&pbmi[88] = 255;
    *(_DWORD *)&pbmi[92] = 16711935;
    *(_DWORD *)&pbmi[96] = 0xFFFF;
    *(_DWORD *)&pbmi[100] = 0xFFFFFF;
    if ( v11 == 8 )
    {
      HalftonePalette = CreateHalftonePalette(0);
      v13 = HalftonePalette;
      if ( HalftonePalette )
      {
        PaletteEntries = GetPaletteEntries(HalftonePalette, 0, 0x100u, (LPPALETTEENTRY)&pbmi[40]);
        DeleteObject(v13);
        if ( PaletteEntries <= 64 )
        {
          v17 = *(_DWORD *)&pbmi[32];
        }
        else
        {
          *(_DWORD *)&pbmi[32] = PaletteEntries;
          v15 = 0;
          do
          {
            v16 = v15++;
            *(_DWORD *)&pbmi[4 * v16 + 40] = ((unsigned __int8)pbmi[4 * v16 + 40] << 16)
                                           | (unsigned __int8)pbmi[4 * v16 + 42]
                                           | ((unsigned __int8)pbmi[4 * v16 + 41] << 8);
            v17 = *(_DWORD *)&pbmi[32];
          }
          while ( v15 < *(int *)&pbmi[32] );
        }
      }
      else
      {
        v17 = 256;
        v18 = *((_WORD *)this + 40) & 0xFE;
        *(_DWORD *)&pbmi[32] = 256;
        *(_WORD *)&pbmi[14] = v18;
      }
      if ( v17 <= 0x10 )
        *(_WORD *)&pbmi[14] = 4;
    }
    CompatibleBitmap = CreateDIBSection(v10, (const BITMAPINFO *)pbmi, 0, &ppvBits, 0, 0);
  }
  v20 = CompatibleBitmap;
  ReleaseDC(0, v10);
  return v20;
}

```

## disassembly

```asm
0x180083c6c  push    rbp
0x180083c6e  push    rbx
0x180083c6f  push    rsi
0x180083c70  push    rdi
0x180083c71  push    r12
0x180083c73  push    r13
0x180083c75  push    r14
0x180083c77  lea     rbp, [rsp-380h]
0x180083c7f  sub     rsp, 480h
0x180083c86  mov     rax, cs:__security_cookie
0x180083c8d  xor     rax, rsp
0x180083c90  mov     [rbp+3B0h+var_40], rax
0x180083c97  mov     esi, r8d
0x180083c9a  mov     [rsp+4B0h+ppvBits], 0
0x180083ca3  mov     edi, edx
0x180083ca5  mov     rbx, rcx
0x180083ca8  xor     edx, edx; Val
0x180083caa  lea     rcx, [rsp+4B0h+pbmi]; void *
0x180083caf  mov     r8d, 428h; Size
0x180083cb5  call    memset
0x180083cba  cmp     qword ptr [rbx+68h], 0
0x180083cbf  jz      short loc_180083CDA
0x180083cc1  mov     rcx, [rbx+78h]; hdc
0x180083cc5  test    rcx, rcx
0x180083cc8  jz      short loc_180083CDA
0x180083cca  mov     r8d, esi; cy
0x180083ccd  mov     edx, edi; cx
0x180083ccf  call    cs:__imp_CreateCompatibleBitmap
0x180083cd5  jmp     loc_180083EA6
0x180083cda  xor     ecx, ecx; hWnd
0x180083cdc  call    cs:__imp_GetDC
0x180083ce2  mov     ecx, [rbx+50h]
0x180083ce5  mov     r12d, 0FEh
0x180083ceb  mov     r14, rax
0x180083cee  mov     r13d, 4
0x180083cf4  test    r12b, cl
0x180083cf7  jnz     short loc_180083CFF
0x180083cf9  or      ecx, r13d
0x180083cfc  mov     [rbx+50h], ecx
0x180083cff  and     ecx, r12d
0x180083d02  cmp     cl, r12b
0x180083d05  jz      loc_180083E87
0x180083d0b  mov     eax, r12d
0x180083d0e  mov     [rsp+4B0h+pbmi.bmiHeader.biHeight], esi
0x180083d12  and     ax, [rbx+50h]
0x180083d16  mov     esi, 1
0x180083d1b  mov     [rsp+4B0h+pbmi.bmiHeader.biSize], 28h ; '('
0x180083d23  mov     [rsp+4B0h+pbmi.bmiHeader.biWidth], edi
0x180083d27  mov     [rsp+4B0h+pbmi.bmiHeader.biPlanes], si
0x180083d2c  mov     [rsp+4B0h+pbmi.bmiHeader.biBitCount], ax
0x180083d31  mov     qword ptr [rsp+4B0h+pbmi.bmiHeader.biCompression], 0
0x180083d3a  mov     qword ptr [rsp+4B0h+pbmi.bmiHeader.biXPelsPerMeter], 0
0x180083d43  mov     qword ptr [rsp+4B0h+pbmi.bmiHeader.biClrUsed], 10h
0x180083d4c  mov     dword ptr [rsp+4B0h+pbmi.bmiColors.rgbBlue], 0
0x180083d54  mov     [rsp+4B0h+var_444], 800000h
0x180083d5c  mov     [rsp+4B0h+var_440], 8000h
0x180083d64  mov     [rsp+4B0h+var_43C], 808000h
0x180083d6c  mov     [rsp+4B0h+var_438], 80h
0x180083d74  mov     [rsp+4B0h+var_434], 800080h
0x180083d7c  mov     [rbp+3B0h+var_430], 8080h
0x180083d83  mov     [rbp+3B0h+var_42C], 0C0C0C0h
0x180083d8a  mov     [rbp+3B0h+var_428], 808080h
0x180083d91  mov     [rbp+3B0h+var_424], 0FF0000h
0x180083d98  mov     [rbp+3B0h+var_420], 0FF00h
0x180083d9f  mov     [rbp+3B0h+var_41C], 0FFFF00h
0x180083da6  mov     [rbp+3B0h+var_418], 0FFh
0x180083dad  mov     [rbp+3B0h+var_414], 0FF00FFh
0x180083db4  mov     [rbp+3B0h+var_410], 0FFFFh
0x180083dbb  mov     [rbp+3B0h+var_40C], 0FFFFFFh
0x180083dc2  cmp     ax, 8
0x180083dc6  jnz     loc_180083E5E
0x180083dcc  xor     ecx, ecx; hdc
0x180083dce  call    cs:__imp_CreateHalftonePalette
0x180083dd4  mov     rdi, rax
0x180083dd7  test    rax, rax
0x180083dda  jz      short loc_180083E3D
0x180083ddc  lea     r9, [rsp+4B0h+pbmi.bmiColors]; pPalEntries
0x180083de1  xor     edx, edx; iStart
0x180083de3  mov     r8d, 100h; cEntries
0x180083de9  mov     rcx, rax; hpal
0x180083dec  call    cs:__imp_GetPaletteEntries
0x180083df2  mov     rcx, rdi; ho
0x180083df5  mov     ebx, eax
0x180083df7  call    cs:__imp_DeleteObject
0x180083dfd  cmp     ebx, 40h ; '@'
0x180083e00  jle     short loc_180083E37
0x180083e02  mov     [rsp+4B0h+pbmi.bmiHeader.biClrUsed], ebx
0x180083e06  xor     r8d, r8d
0x180083e09  movsxd  rdx, r8d
0x180083e0c  add     r8d, esi
0x180083e0f  movzx   eax, [rsp+rdx*4+4B0h+pbmi.bmiColors.rgbRed]
0x180083e14  movzx   ecx, [rsp+rdx*4+4B0h+pbmi.bmiColors.rgbGreen]
0x180083e19  shl     ecx, 8
0x180083e1c  or      ecx, eax
0x180083e1e  movzx   eax, [rsp+rdx*4+4B0h+pbmi.bmiColors.rgbBlue]
0x180083e23  shl     eax, 10h
0x180083e26  or      ecx, eax
0x180083e28  mov     dword ptr [rsp+rdx*4+4B0h+pbmi.bmiColors.rgbBlue], ecx
0x180083e2c  mov     ecx, [rsp+4B0h+pbmi.bmiHeader.biClrUsed]
0x180083e30  cmp     r8d, ecx
0x180083e33  jl      short loc_180083E09
0x180083e35  jmp     short loc_180083E53
0x180083e37  mov     ecx, [rsp+4B0h+pbmi.bmiHeader.biClrUsed]
0x180083e3b  jmp     short loc_180083E53
0x180083e3d  movzx   eax, word ptr [rbx+50h]
0x180083e41  mov     ecx, 100h
0x180083e46  and     ax, r12w
0x180083e4a  mov     [rsp+4B0h+pbmi.bmiHeader.biClrUsed], ecx
0x180083e4e  mov     [rsp+4B0h+pbmi.bmiHeader.biBitCount], ax
0x180083e53  cmp     ecx, 10h
0x180083e56  ja      short loc_180083E5E
0x180083e58  mov     [rsp+4B0h+pbmi.bmiHeader.biBitCount], r13w
0x180083e5e  mov     [rsp+4B0h+offset], 0; offset
0x180083e66  lea     r9, [rsp+4B0h+ppvBits]; ppvBits
0x180083e6b  xor     r8d, r8d; usage
0x180083e6e  mov     [rsp+4B0h+hSection], 0; hSection
0x180083e77  lea     rdx, [rsp+4B0h+pbmi]; pbmi
0x180083e7c  mov     rcx, r14; hdc
0x180083e7f  call    cs:__imp_CreateDIBSection
0x180083e85  jmp     short loc_180083E95
0x180083e87  mov     r8d, esi; cy
0x180083e8a  mov     edx, edi; cx
0x180083e8c  mov     rcx, r14; hdc
0x180083e8f  call    cs:__imp_CreateCompatibleBitmap
0x180083e95  mov     rdx, r14; hDC
0x180083e98  xor     ecx, ecx; hWnd
0x180083e9a  mov     rbx, rax
0x180083e9d  call    cs:__imp_ReleaseDC
0x180083ea3  mov     rax, rbx
0x180083ea6  mov     rcx, [rbp+3B0h+var_40]
0x180083ead  xor     rcx, rsp; StackCookie
0x180083eb0  call    __security_check_cookie
0x180083eb5  add     rsp, 480h
0x180083ebc  pop     r14
0x180083ebe  pop     r13
0x180083ec0  pop     r12
0x180083ec2  pop     rdi
0x180083ec3  pop     rsi
0x180083ec4  pop     rbx
0x180083ec5  pop     rbp
0x180083ec6  retn
```
