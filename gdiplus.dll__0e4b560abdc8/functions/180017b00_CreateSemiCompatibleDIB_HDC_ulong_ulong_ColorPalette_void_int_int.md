# CreateSemiCompatibleDIB(HDC__ *,ulong,ulong,ColorPalette *,void * *,int *,int)

- ea: `0x180017b00`
- end: `0x180017d37`
- name: `?CreateSemiCompatibleDIB@@YAPEAUHBITMAP__@@PEAUHDC__@@KKPEAUColorPalette@@PEAPEAXPEAHH@Z`
- size: `567`
- prototype: `HBITMAP __fastcall(HDC hdc, LONG, int, struct ColorPalette *, void **ppvBits, int *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800902e0`
- `0x18009571c`

## callees

- `0x180017b00`
- `0x180017d40`
- `0x1800e9380`
- `0x1800ea0ec`

## import_xrefs

- `GDI32!CreateDIBSection` at `0x180017c81`
- `GDI32!CreateDIBSection` at `0x180017c81`
- `GDI32!GetDeviceCaps` at `0x180017b85`
- `GDI32!GetDeviceCaps` at `0x180017b85`

## pseudocode

```c
HBITMAP __fastcall CreateSemiCompatibleDIB(
        HDC hdc,
        LONG a2,
        int a3,
        struct ColorPalette *a4,
        void **ppvBits,
        int *a6,
        int a7)
{
  int PixelFormatFromHDC; // eax
  int v12; // eax
  WORD biBitCount; // r8
  DWORD biCompression; // edx
  DWORD v15; // ebx
  __int64 v17; // r9
  BYTE *p_rgbGreen; // rdx
  int *v19; // r8
  int v20; // ecx
  unsigned int v21; // eax
  BITMAPINFO pbmi; // [rsp+30h] [rbp-D0h] BYREF
  int v23; // [rsp+5Ch] [rbp-A4h]
  int v24; // [rsp+60h] [rbp-A0h]

  memset_0(&pbmi, 0, 0x428u);
  PixelFormatFromHDC = a7;
  if ( !a7 )
    PixelFormatFromHDC = ExtractPixelFormatFromHDC(hdc);
  *a6 = PixelFormatFromHDC;
  if ( (PixelFormatFromHDC & 0x10000) != 0 )
    *a6 = 198659;
  if ( GetDeviceCaps(hdc, 2) == 2 && (*a6 & 0x10000) != 0 || (v12 = *a6) == 0 )
  {
    v12 = 139273;
    *a6 = 139273;
  }
  pbmi.bmiHeader.biSize = 40;
  pbmi.bmiHeader.biPlanes = 1;
  biBitCount = BYTE1(v12);
  biCompression = 0;
  pbmi.bmiHeader.biBitCount = BYTE1(v12);
  pbmi.bmiHeader.biCompression = 0;
  if ( (v12 & 0x10000) != 0 )
  {
    if ( a4 && *((_DWORD *)a4 + 1) )
    {
      v17 = *((unsigned int *)a4 + 1);
      p_rgbGreen = &pbmi.bmiColors[0].rgbGreen;
      v19 = (int *)((char *)a4 + 8);
      do
      {
        v20 = *v19;
        v21 = HIWORD(*v19++);
        p_rgbGreen[1] = v21;
        *(_WORD *)(p_rgbGreen - 1) = v20;
        p_rgbGreen += 4;
        --v17;
      }
      while ( v17 );
      biCompression = pbmi.bmiHeader.biCompression;
      biBitCount = pbmi.bmiHeader.biBitCount;
    }
  }
  else
  {
    if ( ((BYTE1(v12) - 16) & 0xFFFFFFEF) == 0 )
    {
      biCompression = 3;
      pbmi.bmiHeader.biCompression = 3;
    }
    pbmi.bmiColors[0] = (RGBQUAD)dword_18018BAA0[(unsigned __int8)v12];
    v23 = dword_18018BA50[(unsigned __int8)v12];
    v24 = dword_18018BA00[(unsigned __int8)v12];
  }
  pbmi.bmiHeader.biWidth = a2;
  if ( a3 >= 0 )
  {
    pbmi.bmiHeader.biHeight = -a3;
    if ( biCompression )
    {
      if ( biBitCount == 16 )
      {
        v15 = 2 * a3 * a2;
        goto LABEL_16;
      }
      if ( biBitCount == 32 )
      {
        v15 = 4 * a3 * a2;
LABEL_16:
        pbmi.bmiHeader.biSizeImage = v15;
LABEL_17:
        pbmi.bmiHeader.biClrUsed = 0;
        pbmi.bmiHeader.biClrImportant = 0;
        return CreateDIBSection(hdc, &pbmi, 0, ppvBits, 0, 0);
      }
    }
    pbmi.bmiHeader.biSizeImage = 0;
    goto LABEL_17;
  }
  return 0;
}

```

## disassembly

```asm
0x180017b00  mov     [rsp-8+arg_8], rbx
0x180017b05  mov     [rsp-8+arg_10], rsi
0x180017b0a  push    rbp
0x180017b0b  push    rdi
0x180017b0c  push    r12
0x180017b0e  push    r14
0x180017b10  push    r15
0x180017b12  lea     rbp, [rsp-370h]
0x180017b1a  sub     rsp, 470h
0x180017b21  mov     rax, cs:__security_cookie
0x180017b28  xor     rax, rsp
0x180017b2b  mov     [rbp+390h+var_30], rax
0x180017b32  mov     r12, [rbp+390h+ppvBits]
0x180017b39  mov     esi, r8d
0x180017b3c  mov     rdi, [rbp+390h+arg_28]
0x180017b43  mov     ebx, edx
0x180017b45  mov     r15, rcx
0x180017b48  xor     edx, edx; Val
0x180017b4a  mov     r8d, 428h; Size
0x180017b50  lea     rcx, [rsp+490h+pbmi]; void *
0x180017b55  mov     r14, r9
0x180017b58  call    memset_0
0x180017b5d  mov     eax, [rbp+390h+arg_30]
0x180017b63  test    eax, eax
0x180017b65  jnz     short loc_180017B6F
0x180017b67  mov     rcx, r15; hdc
0x180017b6a  call    ?ExtractPixelFormatFromHDC@@YAHPEAUHDC__@@@Z; ExtractPixelFormatFromHDC(HDC__ *)
0x180017b6f  mov     [rdi], eax
0x180017b71  bt      eax, 10h
0x180017b75  jnb     short loc_180017B7D
0x180017b77  mov     dword ptr [rdi], 30803h
0x180017b7d  mov     edx, 2; index
0x180017b82  mov     rcx, r15; hdc
0x180017b85  call    cs:__imp_GetDeviceCaps
0x180017b8c  nop     dword ptr [rax+rax+00h]
0x180017b91  cmp     eax, 2
0x180017b94  jz      loc_180017CC4
0x180017b9a  mov     eax, [rdi]
0x180017b9c  test    eax, eax
0x180017b9e  jz      loc_180017CD0
0x180017ba4  mov     edx, 0FFh
0x180017ba9  mov     r9d, eax
0x180017bac  mov     r11d, 1
0x180017bb2  mov     [rsp+490h+pbmi.bmiHeader.biSize], 28h ; '('
0x180017bba  mov     ecx, eax
0x180017bbc  mov     [rsp+490h+pbmi.bmiHeader.biPlanes], r11w
0x180017bc2  sar     ecx, 8
0x180017bc5  movzx   r8d, cx
0x180017bc9  and     r8w, dx
0x180017bcd  lea     r10d, [r11+0Fh]
0x180017bd1  xor     edx, edx
0x180017bd3  mov     [rsp+490h+pbmi.bmiHeader.biBitCount], r8w
0x180017bd9  mov     [rsp+490h+pbmi.bmiHeader.biCompression], edx
0x180017bdd  bt      eax, 10h
0x180017be1  jb      loc_180017CDC
0x180017be7  movzx   eax, cl
0x180017bea  sub     eax, r10d
0x180017bed  test    eax, 0FFFFFFEFh
0x180017bf2  jnz     short loc_180017BFC
0x180017bf4  lea     edx, [r11+2]
0x180017bf8  mov     [rsp+490h+pbmi.bmiHeader.biCompression], edx
0x180017bfc  movzx   ecx, r9b
0x180017c00  lea     r9, __ImageBase
0x180017c07  mov     eax, ds:rva dword_18018BAA0[r9+rcx*4]
0x180017c0f  mov     dword ptr [rsp+490h+pbmi.bmiColors.rgbBlue], eax
0x180017c13  mov     eax, ds:rva dword_18018BA50[r9+rcx*4]
0x180017c1b  mov     [rsp+490h+var_434], eax
0x180017c1f  mov     eax, ds:rva dword_18018BA00[r9+rcx*4]
0x180017c27  mov     [rsp+490h+var_430], eax
0x180017c2b  mov     [rsp+490h+pbmi.bmiHeader.biWidth], ebx
0x180017c2f  test    esi, esi
0x180017c31  js      loc_180017CC0
0x180017c37  mov     eax, esi
0x180017c39  neg     eax
0x180017c3b  mov     [rsp+490h+pbmi.bmiHeader.biHeight], eax
0x180017c3f  test    edx, edx
0x180017c41  jz      short loc_180017CB9
0x180017c43  cmp     r8w, r10w
0x180017c47  jz      loc_180017D2D
0x180017c4d  cmp     r8w, 20h ; ' '
0x180017c52  jnz     short loc_180017CB9
0x180017c54  imul    ebx, esi
0x180017c57  shl     ebx, 2
0x180017c5a  mov     [rsp+490h+pbmi.bmiHeader.biSizeImage], ebx
0x180017c5e  and     [rsp+490h+var_468], 0
0x180017c63  lea     rdx, [rsp+490h+pbmi]; pbmi
0x180017c68  and     [rsp+490h+var_470], 0
0x180017c6e  mov     r9, r12; ppvBits
0x180017c71  and     [rsp+490h+pbmi.bmiHeader.biClrUsed], 0
0x180017c76  xor     r8d, r8d; usage
0x180017c79  and     [rsp+490h+pbmi.bmiHeader.biClrImportant], 0
0x180017c7e  mov     rcx, r15; hdc
0x180017c81  call    cs:__imp_CreateDIBSection
0x180017c88  nop     dword ptr [rax+rax+00h]
0x180017c8d  mov     rcx, [rbp+390h+var_30]
0x180017c94  xor     rcx, rsp; StackCookie
0x180017c97  call    __security_check_cookie
0x180017c9c  lea     r11, [rsp+490h+var_20]
0x180017ca4  mov     rbx, [r11+38h]
0x180017ca8  mov     rsi, [r11+40h]
0x180017cac  mov     rsp, r11
0x180017caf  pop     r15
0x180017cb1  pop     r14
0x180017cb3  pop     r12
0x180017cb5  pop     rdi
0x180017cb6  pop     rbp
0x180017cb7  retn
0x180017cb9  and     [rsp+490h+pbmi.bmiHeader.biSizeImage], 0
0x180017cbe  jmp     short loc_180017C5E
0x180017cc0  xor     eax, eax
0x180017cc2  jmp     short loc_180017C8D
0x180017cc4  test    dword ptr [rdi], 10000h
0x180017cca  jz      loc_180017B9A
0x180017cd0  mov     eax, 22009h
0x180017cd5  mov     [rdi], eax
0x180017cd7  jmp     loc_180017BA4
0x180017cdc  test    r14, r14
0x180017cdf  jz      loc_180017C2B
0x180017ce5  cmp     [r14+4], edx
0x180017ce9  jbe     loc_180017C2B
0x180017cef  mov     r9d, [r14+4]
0x180017cf3  lea     rdx, [rsp+490h+pbmi.bmiColors.rgbGreen]
0x180017cf8  lea     r8, [r14+8]
0x180017cfc  mov     ecx, [r8]
0x180017cff  mov     eax, ecx
0x180017d01  shr     eax, 10h
0x180017d04  lea     r8, [r8+4]
0x180017d08  mov     [rdx+1], al
0x180017d0b  mov     eax, ecx
0x180017d0d  shr     eax, 8
0x180017d10  mov     [rdx], al
0x180017d12  mov     [rdx-1], cl
0x180017d15  lea     rdx, [rdx+4]
0x180017d19  sub     r9, r11
0x180017d1c  jnz     short loc_180017CFC
0x180017d1e  mov     edx, [rsp+490h+pbmi.bmiHeader.biCompression]
0x180017d22  movzx   r8d, [rsp+490h+pbmi.bmiHeader.biBitCount]
0x180017d28  jmp     loc_180017C2B
0x180017d2d  imul    ebx, esi
0x180017d30  add     ebx, ebx
0x180017d32  jmp     loc_180017C5A
```
