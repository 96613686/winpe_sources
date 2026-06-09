# ExtractPixelFormatFromHDC(HDC__ *)

- ea: `0x1800415b8`
- end: `0x1800417af`
- name: `?ExtractPixelFormatFromHDC@@YAHPEAUHDC__@@@Z`
- size: `503`
- prototype: `__int64 __fastcall(HDC hdc)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003f9f0`
- `0x180041c3c`
- `0x180042348`
- `0x18009d238`

## callees

- `0x1800415b8`
- `0x1800fe680`
- `0x1800ff04c`

## import_xrefs

- `GDI32!CreateCompatibleBitmap` at `0x1800415fd`
- `GDI32!CreateCompatibleBitmap` at `0x1800415fd`
- `GDI32!GetDIBits` at `0x180041636`
- `GDI32!GetDIBits` at `0x180041678`
- `GDI32!GetDIBits` at `0x180041636`
- `GDI32!GetDIBits` at `0x180041678`
- `GDI32!DeleteObject` at `0x1800416c1`
- `GDI32!DeleteObject` at `0x1800416c1`

## pseudocode

```c
__int64 __fastcall ExtractPixelFormatFromHDC(HDC hdc)
{
  unsigned int v2; // ebx
  HBITMAP CompatibleBitmap; // rdi
  WORD biBitCount; // ax
  struct tagBITMAPINFO bmi; // [rsp+40h] [rbp-C0h] BYREF
  int v7; // [rsp+6Ch] [rbp-94h]
  int v8; // [rsp+70h] [rbp-90h]

  v2 = 0;
  memset_0(&bmi, 0, 0x428u);
  CompatibleBitmap = CreateCompatibleBitmap(hdc, 1, 1);
  if ( CompatibleBitmap )
  {
    bmi.bmiHeader.biSize = 40;
    GetDIBits(hdc, CompatibleBitmap, 0, 0, 0, &bmi, 0);
    biBitCount = bmi.bmiHeader.biBitCount;
    if ( bmi.bmiHeader.biBitCount <= 8u )
    {
      switch ( bmi.bmiHeader.biBitCount )
      {
        case 1u:
          v2 = 196865;
          break;
        case 4u:
          v2 = 197634;
          break;
        case 8u:
          v2 = 198659;
          break;
      }
      goto LABEL_11;
    }
    if ( bmi.bmiHeader.biCompression == 3 )
    {
      GetDIBits(hdc, CompatibleBitmap, 0, bmi.bmiHeader.biHeight, 0, &bmi, 0);
      if ( *(_DWORD *)bmi.bmiColors != 16711680 )
      {
        if ( *(_DWORD *)bmi.bmiColors == 255 )
        {
          if ( v7 == 65280 && v8 == 16711680 && bmi.bmiHeader.biBitCount == 24 )
            v2 = 137232;
        }
        else if ( *(_DWORD *)bmi.bmiColors == 31744 )
        {
          if ( v7 == 992 && v8 == 31 && bmi.bmiHeader.biBitCount == 16 )
            v2 = 135173;
        }
        else if ( *(_DWORD *)bmi.bmiColors == 63488 && v7 == 2016 && v8 == 31 && bmi.bmiHeader.biBitCount == 16 )
        {
          v2 = 135174;
        }
        goto LABEL_11;
      }
      if ( v7 == 65280 && v8 == 255 )
      {
        biBitCount = bmi.bmiHeader.biBitCount;
        goto LABEL_8;
      }
    }
    else if ( !bmi.bmiHeader.biCompression )
    {
LABEL_8:
      if ( biBitCount == 24 )
      {
        v2 = 137224;
      }
      else if ( biBitCount == 32 )
      {
        v2 = 139273;
      }
    }
LABEL_11:
    DeleteObject(CompatibleBitmap);
  }
  return v2;
}

```

## disassembly

```asm
0x1800415b8  push    rbp
0x1800415ba  push    rbx
0x1800415bb  push    rsi
0x1800415bc  push    rdi
0x1800415bd  lea     rbp, [rsp-388h]
0x1800415c5  sub     rsp, 488h
0x1800415cc  mov     rax, cs:__security_cookie
0x1800415d3  xor     rax, rsp
0x1800415d6  mov     [rbp+3A0h+var_30], rax
0x1800415dd  mov     rsi, rcx
0x1800415e0  xor     edx, edx; Val
0x1800415e2  lea     rcx, [rsp+4A0h+bmi]; void *
0x1800415e7  mov     r8d, 428h; Size
0x1800415ed  xor     ebx, ebx
0x1800415ef  call    memset_0
0x1800415f4  lea     edx, [rbx+1]; cx
0x1800415f7  mov     rcx, rsi; hdc
0x1800415fa  mov     r8d, edx; cy
0x1800415fd  call    cs:__imp_CreateCompatibleBitmap
0x180041603  mov     rdi, rax
0x180041606  test    rax, rax
0x180041609  jz      loc_1800416C7
0x18004160f  lea     rax, [rsp+4A0h+bmi]
0x180041614  mov     [rsp+4A0h+usage], ebx; usage
0x180041618  mov     [rsp+4A0h+lpbmi], rax; lpbmi
0x18004161d  xor     r9d, r9d; cLines
0x180041620  xor     r8d, r8d; start
0x180041623  mov     [rsp+4A0h+lpvBits], rbx; lpvBits
0x180041628  mov     rdx, rdi; hbm
0x18004162b  mov     [rsp+4A0h+bmi.bmiHeader.biSize], 28h ; '('
0x180041633  mov     rcx, rsi; hdc
0x180041636  call    cs:__imp_GetDIBits
0x18004163c  movzx   eax, [rsp+4A0h+bmi.bmiHeader.biBitCount]
0x180041641  cmp     eax, 8
0x180041644  jbe     loc_180041719
0x18004164a  mov     edx, [rsp+4A0h+bmi.bmiHeader.biCompression]
0x18004164e  cmp     edx, 3
0x180041651  jnz     loc_180041798
0x180041657  mov     r9d, [rsp+4A0h+bmi.bmiHeader.biHeight]; cLines
0x18004165c  lea     rax, [rsp+4A0h+bmi]
0x180041661  mov     [rsp+4A0h+usage], ebx; usage
0x180041665  xor     r8d, r8d; start
0x180041668  mov     [rsp+4A0h+lpbmi], rax; lpbmi
0x18004166d  mov     rdx, rdi; hbm
0x180041670  mov     rcx, rsi; hdc
0x180041673  mov     [rsp+4A0h+lpvBits], rbx; lpvBits
0x180041678  call    cs:__imp_GetDIBits
0x18004167e  mov     edx, dword ptr [rsp+4A0h+bmi.bmiColors.rgbBlue]
0x180041682  mov     r8d, 0FF0000h
0x180041688  mov     ecx, [rsp+4A0h+var_434]
0x18004168c  mov     eax, [rsp+4A0h+var_430]
0x180041690  cmp     edx, r8d
0x180041693  jnz     short loc_1800416E4
0x180041695  cmp     ecx, 0FF00h
0x18004169b  jnz     short loc_1800416BE
0x18004169d  cmp     eax, 0FFh
0x1800416a2  jnz     short loc_1800416BE
0x1800416a4  movzx   eax, [rsp+4A0h+bmi.bmiHeader.biBitCount]
0x1800416a9  cmp     ax, 18h
0x1800416ad  jz      loc_1800417A5
0x1800416b3  cmp     ax, 20h ; ' '
0x1800416b7  jnz     short loc_1800416BE
0x1800416b9  mov     ebx, 22009h
0x1800416be  mov     rcx, rdi; ho
0x1800416c1  call    cs:__imp_DeleteObject
0x1800416c7  mov     eax, ebx
0x1800416c9  mov     rcx, [rbp+3A0h+var_30]
0x1800416d0  xor     rcx, rsp; StackCookie
0x1800416d3  call    __security_check_cookie
0x1800416d8  add     rsp, 488h
0x1800416df  pop     rdi
0x1800416e0  pop     rsi
0x1800416e1  pop     rbx
0x1800416e2  pop     rbp
0x1800416e3  retn
0x1800416e4  cmp     edx, 0FFh
0x1800416ea  jz      short loc_180041742
0x1800416ec  cmp     edx, 7C00h
0x1800416f2  jz      short loc_18004176D
0x1800416f4  cmp     edx, 0F800h
0x1800416fa  jnz     short loc_1800416BE
0x1800416fc  cmp     ecx, 7E0h
0x180041702  jnz     short loc_1800416BE
0x180041704  cmp     eax, 1Fh
0x180041707  jnz     short loc_1800416BE
0x180041709  cmp     [rsp+4A0h+bmi.bmiHeader.biBitCount], 10h
0x18004170f  mov     eax, 21006h
0x180041714  cmovz   ebx, eax
0x180041717  jmp     short loc_1800416BE
0x180041719  mov     ecx, eax
0x18004171b  sub     ecx, 1
0x18004171e  jz      short loc_180041738
0x180041720  sub     ecx, 3
0x180041723  jz      short loc_180041731
0x180041725  cmp     ecx, 4
0x180041728  jnz     short loc_1800416BE
0x18004172a  mov     ebx, 30803h
0x18004172f  jmp     short loc_1800416BE
0x180041731  mov     ebx, 30402h
0x180041736  jmp     short loc_1800416BE
0x180041738  mov     ebx, 30101h
0x18004173d  jmp     loc_1800416BE
0x180041742  cmp     ecx, 0FF00h
0x180041748  jnz     loc_1800416BE
0x18004174e  cmp     eax, r8d
0x180041751  jnz     loc_1800416BE
0x180041757  cmp     [rsp+4A0h+bmi.bmiHeader.biBitCount], 18h
0x18004175d  jnz     loc_1800416BE
0x180041763  mov     ebx, 21810h
0x180041768  jmp     loc_1800416BE
0x18004176d  cmp     ecx, 3E0h
0x180041773  jnz     loc_1800416BE
0x180041779  cmp     eax, 1Fh
0x18004177c  jnz     loc_1800416BE
0x180041782  cmp     [rsp+4A0h+bmi.bmiHeader.biBitCount], 10h
0x180041788  jnz     loc_1800416BE
0x18004178e  mov     ebx, 21005h
0x180041793  jmp     loc_1800416BE
0x180041798  test    edx, edx
0x18004179a  jnz     loc_1800416BE
0x1800417a0  jmp     loc_1800416A9
0x1800417a5  mov     ebx, 21808h
0x1800417aa  jmp     loc_1800416BE
```
