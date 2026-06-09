# ExtractPixelFormatFromHDC(HDC__ *)

- ea: `0x180017d40`
- end: `0x180017f6d`
- name: `?ExtractPixelFormatFromHDC@@YAHPEAUHDC__@@@Z`
- size: `557`
- prototype: `__int64 __fastcall(HDC hdc)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017060`
- `0x180017b00`
- `0x180018178`
- `0x180094ee4`

## callees

- `0x180017d40`
- `0x1800e9380`
- `0x1800ea0ec`

## import_xrefs

- `GDI32!CreateCompatibleBitmap` at `0x180017d8f`
- `GDI32!CreateCompatibleBitmap` at `0x180017d8f`
- `GDI32!GetDIBits` at `0x180017dce`
- `GDI32!GetDIBits` at `0x180017e14`
- `GDI32!GetDIBits` at `0x180017dce`
- `GDI32!GetDIBits` at `0x180017e14`
- `GDI32!DeleteObject` at `0x180017e63`
- `GDI32!DeleteObject` at `0x180017e63`

## pseudocode

```c
__int64 __fastcall ExtractPixelFormatFromHDC(HDC hdc)
{
  unsigned int v2; // ebx
  HBITMAP CompatibleBitmap; // rdi
  WORD biBitCount; // ax
  struct tagBITMAPINFO bmi; // [rsp+48h] [rbp-C0h] BYREF
  int v7; // [rsp+74h] [rbp-94h]
  int v8; // [rsp+78h] [rbp-90h]

  v2 = 0;
  memset_0(&bmi.bmiHeader.biWidth, 0, 0x424u);
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
0x180017d40  mov     rax, rsp
0x180017d43  mov     [rax+10h], rbx
0x180017d47  mov     [rax+18h], rsi
0x180017d4b  mov     [rax+20h], rdi
0x180017d4f  push    rbp
0x180017d50  lea     rbp, [rax-388h]
0x180017d57  sub     rsp, 480h
0x180017d5e  mov     rax, cs:__security_cookie
0x180017d65  xor     rax, rsp
0x180017d68  mov     [rbp+380h+var_10], rax
0x180017d6f  mov     rsi, rcx
0x180017d72  xor     edx, edx; Val
0x180017d74  lea     rcx, [rsp+480h+bmi.bmiHeader.biWidth]; void *
0x180017d79  mov     r8d, 424h; Size
0x180017d7f  xor     ebx, ebx
0x180017d81  call    memset_0
0x180017d86  lea     edx, [rbx+1]; cx
0x180017d89  mov     rcx, rsi; hdc
0x180017d8c  mov     r8d, edx; cy
0x180017d8f  call    cs:__imp_CreateCompatibleBitmap
0x180017d96  nop     dword ptr [rax+rax+00h]
0x180017d9b  mov     rdi, rax
0x180017d9e  test    rax, rax
0x180017da1  jz      loc_180017E6F
0x180017da7  lea     rax, [rsp+480h+bmi]
0x180017dac  mov     [rsp+480h+usage], ebx; usage
0x180017db0  mov     [rsp+480h+lpbmi], rax; lpbmi
0x180017db5  xor     r9d, r9d; cLines
0x180017db8  xor     r8d, r8d; start
0x180017dbb  mov     [rsp+480h+lpvBits], rbx; lpvBits
0x180017dc0  mov     rdx, rdi; hbm
0x180017dc3  mov     [rsp+480h+bmi.bmiHeader.biSize], 28h ; '('
0x180017dcb  mov     rcx, rsi; hdc
0x180017dce  call    cs:__imp_GetDIBits
0x180017dd5  nop     dword ptr [rax+rax+00h]
0x180017dda  movzx   eax, [rsp+480h+bmi.bmiHeader.biBitCount]
0x180017ddf  cmp     eax, 8
0x180017de2  jbe     loc_180017ECF
0x180017de8  cmp     [rsp+480h+bmi.bmiHeader.biCompression], 3
0x180017ded  jnz     loc_180017F54
0x180017df3  mov     r9d, [rsp+480h+bmi.bmiHeader.biHeight]; cLines
0x180017df8  lea     rax, [rsp+480h+bmi]
0x180017dfd  mov     [rsp+480h+usage], ebx; usage
0x180017e01  xor     r8d, r8d; start
0x180017e04  mov     [rsp+480h+lpbmi], rax; lpbmi
0x180017e09  mov     rdx, rdi; hbm
0x180017e0c  mov     rcx, rsi; hdc
0x180017e0f  mov     [rsp+480h+lpvBits], rbx; lpvBits
0x180017e14  call    cs:__imp_GetDIBits
0x180017e1b  nop     dword ptr [rax+rax+00h]
0x180017e20  mov     edx, dword ptr [rsp+480h+bmi.bmiColors.rgbBlue]
0x180017e24  mov     r8d, 0FF0000h
0x180017e2a  mov     ecx, [rsp+480h+var_414]
0x180017e2e  mov     eax, [rsp+480h+var_410]
0x180017e32  cmp     edx, r8d
0x180017e35  jnz     short loc_180017E9A
0x180017e37  cmp     ecx, 0FF00h
0x180017e3d  jnz     short loc_180017E60
0x180017e3f  cmp     eax, 0FFh
0x180017e44  jnz     short loc_180017E60
0x180017e46  movzx   eax, [rsp+480h+bmi.bmiHeader.biBitCount]
0x180017e4b  cmp     ax, 18h
0x180017e4f  jz      loc_180017F63
0x180017e55  cmp     ax, 20h ; ' '
0x180017e59  jnz     short loc_180017E60
0x180017e5b  mov     ebx, 22009h
0x180017e60  mov     rcx, rdi; ho
0x180017e63  call    cs:__imp_DeleteObject
0x180017e6a  nop     dword ptr [rax+rax+00h]
0x180017e6f  mov     eax, ebx
0x180017e71  mov     rcx, [rbp+380h+var_10]
0x180017e78  xor     rcx, rsp; StackCookie
0x180017e7b  call    __security_check_cookie
0x180017e80  lea     r11, [rsp+480h+var_s0]
0x180017e88  mov     rbx, [r11+18h]
0x180017e8c  mov     rsi, [r11+20h]
0x180017e90  mov     rdi, [r11+28h]
0x180017e94  mov     rsp, r11
0x180017e97  pop     rbp
0x180017e98  retn
0x180017e9a  cmp     edx, 0FFh
0x180017ea0  jz      short loc_180017EFE
0x180017ea2  cmp     edx, 7C00h
0x180017ea8  jz      short loc_180017F29
0x180017eaa  cmp     edx, 0F800h
0x180017eb0  jnz     short loc_180017E60
0x180017eb2  cmp     ecx, 7E0h
0x180017eb8  jnz     short loc_180017E60
0x180017eba  cmp     eax, 1Fh
0x180017ebd  jnz     short loc_180017E60
0x180017ebf  cmp     [rsp+480h+bmi.bmiHeader.biBitCount], 10h
0x180017ec5  mov     eax, 21006h
0x180017eca  cmovz   ebx, eax
0x180017ecd  jmp     short loc_180017E60
0x180017ecf  mov     ecx, eax
0x180017ed1  sub     ecx, 1
0x180017ed4  jz      short loc_180017EF4
0x180017ed6  sub     ecx, 3
0x180017ed9  jz      short loc_180017EEA
0x180017edb  cmp     ecx, 4
0x180017ede  jnz     short loc_180017E60
0x180017ee0  mov     ebx, 30803h
0x180017ee5  jmp     loc_180017E60
0x180017eea  mov     ebx, 30402h
0x180017eef  jmp     loc_180017E60
0x180017ef4  mov     ebx, 30101h
0x180017ef9  jmp     loc_180017E60
0x180017efe  cmp     ecx, 0FF00h
0x180017f04  jnz     loc_180017E60
0x180017f0a  cmp     eax, r8d
0x180017f0d  jnz     loc_180017E60
0x180017f13  cmp     [rsp+480h+bmi.bmiHeader.biBitCount], 18h
0x180017f19  jnz     loc_180017E60
0x180017f1f  mov     ebx, 21810h
0x180017f24  jmp     loc_180017E60
0x180017f29  cmp     ecx, 3E0h
0x180017f2f  jnz     loc_180017E60
0x180017f35  cmp     eax, 1Fh
0x180017f38  jnz     loc_180017E60
0x180017f3e  cmp     [rsp+480h+bmi.bmiHeader.biBitCount], 10h
0x180017f44  jnz     loc_180017E60
0x180017f4a  mov     ebx, 21005h
0x180017f4f  jmp     loc_180017E60
0x180017f54  cmp     [rsp+480h+bmi.bmiHeader.biCompression], ebx
0x180017f58  jnz     loc_180017E60
0x180017f5e  jmp     loc_180017E4B
0x180017f63  mov     ebx, 21808h
0x180017f68  jmp     loc_180017E60
```
