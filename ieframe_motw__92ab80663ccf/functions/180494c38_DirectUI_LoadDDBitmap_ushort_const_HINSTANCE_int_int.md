# DirectUI::LoadDDBitmap(ushort const *,HINSTANCE__ *,int,int)

- ea: `0x180494c38`
- end: `0x180494f74`
- name: `?LoadDDBitmap@DirectUI@@YAPEAUHBITMAP__@@PEBGPEAUHINSTANCE__@@HH@Z`
- size: `828`
- prototype: `HBITMAP __fastcall(LPCWSTR name, HINSTANCE hInst, HINSTANCE cx, int cy, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18048be0c`

## callees

- `0x180494c38`
- `0x180591ef6`
- `0x180591f80`

## import_xrefs

- `GDI32!GetBrushOrgEx` at `0x180494e36`
- `GDI32!GetBrushOrgEx` at `0x180494e36`
- `GDI32!SetStretchBltMode` at `0x180494e4a`
- `GDI32!SetStretchBltMode` at `0x180494e4a`
- `GDI32!CreateHalftonePalette` at `0x180494de6`
- `GDI32!CreateHalftonePalette` at `0x180494de6`
- `GDI32!StretchBlt` at `0x180494eb2`
- `GDI32!StretchBlt` at `0x180494eb2`
- `GDI32!SetBrushOrgEx` at `0x180494e65`
- `GDI32!SetBrushOrgEx` at `0x180494e65`
- `GDI32!DeleteObject` at `0x180494ed9`
- `GDI32!DeleteObject` at `0x180494f2f`
- `GDI32!DeleteObject` at `0x180494ed9`
- `GDI32!DeleteObject` at `0x180494f2f`
- `GDI32!SelectObject` at `0x180494d75`
- `GDI32!SelectObject` at `0x180494dd4`
- `GDI32!SelectObject` at `0x180494ef0`
- `GDI32!SelectObject` at `0x180494f11`
- `GDI32!SelectObject` at `0x180494d75`
- `GDI32!SelectObject` at `0x180494dd4`
- `GDI32!SelectObject` at `0x180494ef0`
- `GDI32!SelectObject` at `0x180494f11`
- `GDI32!GetObjectW` at `0x180494d40`
- `GDI32!GetObjectW` at `0x180494d40`
- `GDI32!GetDeviceCaps` at `0x180494c8f`
- `GDI32!GetDeviceCaps` at `0x180494c8f`
- `GDI32!DeleteDC` at `0x180494eff`
- `GDI32!DeleteDC` at `0x180494f20`
- `GDI32!DeleteDC` at `0x180494eff`
- `GDI32!DeleteDC` at `0x180494f20`
- `GDI32!CreateCompatibleDC` at `0x180494d57`
- `GDI32!CreateCompatibleDC` at `0x180494d8c`
- `GDI32!CreateCompatibleDC` at `0x180494d57`
- `GDI32!CreateCompatibleDC` at `0x180494d8c`
- `GDI32!CreateCompatibleBitmap` at `0x180494db6`
- `GDI32!CreateCompatibleBitmap` at `0x180494db6`
- `GDI32!SelectPalette` at `0x180494e07`
- `GDI32!SelectPalette` at `0x180494eca`
- `GDI32!SelectPalette` at `0x180494e07`
- `GDI32!SelectPalette` at `0x180494eca`
- `GDI32!RealizePalette` at `0x180494e19`
- `GDI32!RealizePalette` at `0x180494e19`
- `USER32!ReleaseDC` at `0x180494f40`
- `USER32!ReleaseDC` at `0x180494f40`
- `USER32!GetDC` at `0x180494c78`
- `USER32!GetDC` at `0x180494c78`
- `USER32!LoadImageW` at `0x180494cd1`
- `USER32!LoadImageW` at `0x180494d0b`
- `USER32!LoadImageW` at `0x180494cd1`
- `USER32!LoadImageW` at `0x180494d0b`

## pseudocode

```c
HANDLE __fastcall DirectUI::LoadDDBitmap(LPCWSTR name, HINSTANCE hInst, HINSTANCE cx, int cy)
{
  int v5; // ebp
  HDC DC; // rsi
  int v10; // r9d
  HANDLE v11; // r14
  HANDLE ImageW; // r15
  HDC CompatibleDC; // rax
  HDC v14; // rbp
  void *v15; // rbx
  HDC v16; // rdi
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v18; // r13
  HPALETTE HalftonePalette; // rax
  HPALETTE v20; // r12
  HPALETTE v21; // rbx
  struct tagPOINT pt; // [rsp+60h] [rbp-D8h] BYREF
  HGDIOBJ v23; // [rsp+68h] [rbp-D0h]
  _BYTE pv[36]; // [rsp+70h] [rbp-C8h] BYREF
  int wDest; // [rsp+94h] [rbp-A4h]
  int hDest; // [rsp+98h] [rbp-A0h]

  v5 = (int)cx;
  if ( !name )
    return 0;
  DC = GetDC(0);
  if ( (GetDeviceCaps(DC, 38) & 0x100) != 0 )
  {
    v11 = 0;
    ImageW = LoadImageW(hInst, name, 0, v5, cy, hInst != 0 ? 0x2000 : 8208);
    if ( ImageW )
    {
      memset_0(pv, 0, 0x68u);
      if ( GetObjectW(ImageW, 104, pv) == 104 )
      {
        CompatibleDC = CreateCompatibleDC(DC);
        v14 = CompatibleDC;
        if ( CompatibleDC )
        {
          v23 = SelectObject(CompatibleDC, ImageW);
          v15 = v23;
          v16 = CreateCompatibleDC(DC);
          if ( v16 )
          {
            CompatibleBitmap = CreateCompatibleBitmap(DC, wDest, hDest);
            v11 = CompatibleBitmap;
            if ( CompatibleBitmap )
            {
              v18 = SelectObject(v16, CompatibleBitmap);
              HalftonePalette = CreateHalftonePalette(v16);
              v20 = HalftonePalette;
              if ( HalftonePalette )
              {
                v21 = SelectPalette(v16, HalftonePalette, 0);
                RealizePalette(v16);
                pt = 0;
                GetBrushOrgEx(v16, &pt);
                SetStretchBltMode(v16, 4);
                SetBrushOrgEx(v16, pt.x, pt.y, 0);
                StretchBlt(v16, 0, 0, wDest, hDest, v14, 0, 0, wDest, hDest, 0xCC0020u);
                SelectPalette(v16, v21, 1);
                DeleteObject(v20);
                v15 = v23;
              }
              SelectObject(v16, v18);
            }
            DeleteDC(v16);
          }
          SelectObject(v14, v15);
          DeleteDC(v14);
        }
      }
      DeleteObject(ImageW);
    }
  }
  else
  {
    v10 = 2;
    if ( v5 != 1 )
      v10 = v5;
    v11 = LoadImageW(hInst, name, 0, v10, cy, hInst == 0 ? 0x10 : 0);
  }
  ReleaseDC(0, DC);
  return v11;
}

```

## disassembly

```asm
0x180494c38  push    rbx
0x180494c3a  push    rbp
0x180494c3b  push    rsi
0x180494c3c  push    rdi
0x180494c3d  push    r12
0x180494c3f  push    r13
0x180494c41  push    r14
0x180494c43  push    r15
0x180494c45  sub     rsp, 0F8h
0x180494c4c  mov     rax, cs:__security_cookie
0x180494c53  xor     rax, rsp
0x180494c56  mov     [rsp+138h+var_58], rax
0x180494c5e  mov     r15d, r9d
0x180494c61  mov     ebp, r8d
0x180494c64  mov     rbx, rdx
0x180494c67  mov     rdi, rcx
0x180494c6a  test    rcx, rcx
0x180494c6d  jnz     short loc_180494C76
0x180494c6f  xor     eax, eax
0x180494c71  jmp     loc_180494F4F
0x180494c76  xor     ecx, ecx; hWnd
0x180494c78  call    cs:__imp_GetDC
0x180494c7f  nop     dword ptr [rax+rax+00h]
0x180494c84  mov     rcx, rax; hdc
0x180494c87  mov     edx, 26h ; '&'; index
0x180494c8c  mov     rsi, rax
0x180494c8f  call    cs:__imp_GetDeviceCaps
0x180494c96  nop     dword ptr [rax+rax+00h]
0x180494c9b  mov     rdx, rdi; name
0x180494c9e  bt      eax, 8
0x180494ca2  jb      short loc_180494CE5
0x180494ca4  mov     r9d, 2
0x180494caa  mov     r8, rbx
0x180494cad  neg     r8
0x180494cb0  mov     rcx, rbx; hInst
0x180494cb3  sbb     r10d, r10d
0x180494cb6  not     r10d
0x180494cb9  and     r10d, 10h
0x180494cbd  cmp     ebp, 1
0x180494cc0  mov     [rsp+138h+fuLoad], r10d; fuLoad
0x180494cc5  mov     [rsp+138h+cy], r15d; cy
0x180494cca  cmovnz  r9d, ebp; cx
0x180494cce  xor     r8d, r8d; type
0x180494cd1  call    cs:__imp_LoadImageW
0x180494cd8  nop     dword ptr [rax+rax+00h]
0x180494cdd  mov     r14, rax
0x180494ce0  jmp     loc_180494F3B
0x180494ce5  xor     r14d, r14d
0x180494ce8  mov     rax, rbx
0x180494ceb  neg     rax
0x180494cee  mov     r9d, ebp; cx
0x180494cf1  sbb     ecx, ecx
0x180494cf3  xor     r8d, r8d; type
0x180494cf6  and     ecx, 0FFFFFFF0h
0x180494cf9  add     ecx, 2010h
0x180494cff  mov     [rsp+138h+fuLoad], ecx; fuLoad
0x180494d03  mov     rcx, rbx; hInst
0x180494d06  mov     [rsp+138h+cy], r15d; cy
0x180494d0b  call    cs:__imp_LoadImageW
0x180494d12  nop     dword ptr [rax+rax+00h]
0x180494d17  mov     r15, rax
0x180494d1a  test    rax, rax
0x180494d1d  jz      loc_180494F3B
0x180494d23  lea     ebx, [r14+68h]
0x180494d27  xor     edx, edx; Val
0x180494d29  mov     r8d, ebx; Size
0x180494d2c  lea     rcx, [rsp+138h+pv]; void *
0x180494d31  call    memset_0
0x180494d36  lea     r8, [rsp+138h+pv]; pv
0x180494d3b  mov     edx, ebx; c
0x180494d3d  mov     rcx, r15; h
0x180494d40  call    cs:__imp_GetObjectW
0x180494d47  nop     dword ptr [rax+rax+00h]
0x180494d4c  cmp     eax, ebx
0x180494d4e  jnz     loc_180494F2C
0x180494d54  mov     rcx, rsi; hdc
0x180494d57  call    cs:__imp_CreateCompatibleDC
0x180494d5e  nop     dword ptr [rax+rax+00h]
0x180494d63  mov     rbp, rax
0x180494d66  test    rax, rax
0x180494d69  jz      loc_180494F2C
0x180494d6f  mov     rdx, r15; h
0x180494d72  mov     rcx, rax; hdc
0x180494d75  call    cs:__imp_SelectObject
0x180494d7c  nop     dword ptr [rax+rax+00h]
0x180494d81  mov     rcx, rsi; hdc
0x180494d84  mov     [rsp+138h+var_D0], rax
0x180494d89  mov     rbx, rax
0x180494d8c  call    cs:__imp_CreateCompatibleDC
0x180494d93  nop     dword ptr [rax+rax+00h]
0x180494d98  mov     rdi, rax
0x180494d9b  test    rax, rax
0x180494d9e  jz      loc_180494F0B
0x180494da4  mov     r8d, [rsp+138h+hDest]; cy
0x180494dac  mov     rcx, rsi; hdc
0x180494daf  mov     edx, [rsp+138h+wDest]; cx
0x180494db6  call    cs:__imp_CreateCompatibleBitmap
0x180494dbd  nop     dword ptr [rax+rax+00h]
0x180494dc2  mov     r14, rax
0x180494dc5  test    rax, rax
0x180494dc8  jz      loc_180494EFC
0x180494dce  mov     rdx, rax; h
0x180494dd1  mov     rcx, rdi; hdc
0x180494dd4  call    cs:__imp_SelectObject
0x180494ddb  nop     dword ptr [rax+rax+00h]
0x180494de0  mov     rcx, rdi; hdc
0x180494de3  mov     r13, rax
0x180494de6  call    cs:__imp_CreateHalftonePalette
0x180494ded  nop     dword ptr [rax+rax+00h]
0x180494df2  mov     r12, rax
0x180494df5  test    rax, rax
0x180494df8  jz      loc_180494EEA
0x180494dfe  xor     r8d, r8d; bForceBkgd
0x180494e01  mov     rdx, rax; hPal
0x180494e04  mov     rcx, rdi; hdc
0x180494e07  call    cs:__imp_SelectPalette
0x180494e0e  nop     dword ptr [rax+rax+00h]
0x180494e13  mov     rcx, rdi; hdc
0x180494e16  mov     rbx, rax
0x180494e19  call    cs:__imp_RealizePalette
0x180494e20  nop     dword ptr [rax+rax+00h]
0x180494e25  lea     rdx, [rsp+138h+pt]; lppt
0x180494e2a  mov     qword ptr [rsp+138h+pt.x], 0
0x180494e33  mov     rcx, rdi; hdc
0x180494e36  call    cs:__imp_GetBrushOrgEx
0x180494e3d  nop     dword ptr [rax+rax+00h]
0x180494e42  mov     edx, 4; mode
0x180494e47  mov     rcx, rdi; hdc
0x180494e4a  call    cs:__imp_SetStretchBltMode
0x180494e51  nop     dword ptr [rax+rax+00h]
0x180494e56  mov     r8d, [rsp+138h+pt.y]; y
0x180494e5b  xor     r9d, r9d; lppt
0x180494e5e  mov     edx, [rsp+138h+pt.x]; x
0x180494e62  mov     rcx, rdi; hdc
0x180494e65  call    cs:__imp_SetBrushOrgEx
0x180494e6c  nop     dword ptr [rax+rax+00h]
0x180494e71  mov     eax, [rsp+138h+hDest]
0x180494e78  xor     r8d, r8d; yDest
0x180494e7b  mov     r9d, [rsp+138h+wDest]; wDest
0x180494e83  xor     edx, edx; xDest
0x180494e85  mov     [rsp+138h+rop], 0CC0020h; rop
0x180494e8d  mov     rcx, rdi; hdcDest
0x180494e90  mov     [rsp+138h+hSrc], eax; hSrc
0x180494e94  mov     [rsp+138h+wSrc], r9d; wSrc
0x180494e99  mov     [rsp+138h+ySrc], 0; ySrc
0x180494ea1  mov     [rsp+138h+xSrc], 0; xSrc
0x180494ea9  mov     qword ptr [rsp+138h+fuLoad], rbp; hdcSrc
0x180494eae  mov     [rsp+138h+cy], eax; hDest
0x180494eb2  call    cs:__imp_StretchBlt
0x180494eb9  nop     dword ptr [rax+rax+00h]
0x180494ebe  mov     r8d, 1; bForceBkgd
0x180494ec4  mov     rdx, rbx; hPal
0x180494ec7  mov     rcx, rdi; hdc
0x180494eca  call    cs:__imp_SelectPalette
0x180494ed1  nop     dword ptr [rax+rax+00h]
0x180494ed6  mov     rcx, r12; ho
0x180494ed9  call    cs:__imp_DeleteObject
0x180494ee0  nop     dword ptr [rax+rax+00h]
0x180494ee5  mov     rbx, [rsp+138h+var_D0]
0x180494eea  mov     rdx, r13; h
0x180494eed  mov     rcx, rdi; hdc
0x180494ef0  call    cs:__imp_SelectObject
0x180494ef7  nop     dword ptr [rax+rax+00h]
0x180494efc  mov     rcx, rdi; hdc
0x180494eff  call    cs:__imp_DeleteDC
0x180494f06  nop     dword ptr [rax+rax+00h]
0x180494f0b  mov     rdx, rbx; h
0x180494f0e  mov     rcx, rbp; hdc
0x180494f11  call    cs:__imp_SelectObject
0x180494f18  nop     dword ptr [rax+rax+00h]
0x180494f1d  mov     rcx, rbp; hdc
0x180494f20  call    cs:__imp_DeleteDC
0x180494f27  nop     dword ptr [rax+rax+00h]
0x180494f2c  mov     rcx, r15; ho
0x180494f2f  call    cs:__imp_DeleteObject
0x180494f36  nop     dword ptr [rax+rax+00h]
0x180494f3b  mov     rdx, rsi; hDC
0x180494f3e  xor     ecx, ecx; hWnd
0x180494f40  call    cs:__imp_ReleaseDC
0x180494f47  nop     dword ptr [rax+rax+00h]
0x180494f4c  mov     rax, r14
0x180494f4f  mov     rcx, [rsp+138h+var_58]
0x180494f57  xor     rcx, rsp; StackCookie
0x180494f5a  call    __security_check_cookie
0x180494f5f  add     rsp, 0F8h
0x180494f66  pop     r15
0x180494f68  pop     r14
0x180494f6a  pop     r13
0x180494f6c  pop     r12
0x180494f6e  pop     rdi
0x180494f6f  pop     rsi
0x180494f70  pop     rbp
0x180494f71  pop     rbx
0x180494f72  retn
```
