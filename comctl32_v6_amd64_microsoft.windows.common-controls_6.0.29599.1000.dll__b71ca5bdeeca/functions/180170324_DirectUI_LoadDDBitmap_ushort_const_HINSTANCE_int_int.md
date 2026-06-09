# DirectUI::LoadDDBitmap(ushort const *,HINSTANCE__ *,int,int)

- ea: `0x180170324`
- end: `0x1801705c9`
- name: `?LoadDDBitmap@DirectUI@@YAPEAUHBITMAP__@@PEBGPEAUHINSTANCE__@@HH@Z`
- size: `677`
- prototype: `HBITMAP __fastcall(LPCWSTR name, HINSTANCE hInst, HINSTANCE cx, int cy, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1801649dc`

## callees

- `0x180114520`
- `0x180114ebc`
- `0x180170324`

## import_xrefs

- `GDI32!DeleteObject` at `0x180170559`
- `GDI32!DeleteObject` at `0x180170591`
- `GDI32!DeleteObject` at `0x180170559`
- `GDI32!DeleteObject` at `0x180170591`
- `GDI32!GetObjectW` at `0x180170414`
- `GDI32!GetObjectW` at `0x180170414`
- `GDI32!SelectObject` at `0x18017043d`
- `GDI32!SelectObject` at `0x18017048a`
- `GDI32!SelectObject` at `0x18017056a`
- `GDI32!SelectObject` at `0x18017057f`
- `GDI32!SelectObject` at `0x18017043d`
- `GDI32!SelectObject` at `0x18017048a`
- `GDI32!SelectObject` at `0x18017056a`
- `GDI32!SelectObject` at `0x18017057f`
- `GDI32!DeleteDC` at `0x180170573`
- `GDI32!DeleteDC` at `0x180170588`
- `GDI32!DeleteDC` at `0x180170573`
- `GDI32!DeleteDC` at `0x180170588`
- `GDI32!CreateCompatibleDC` at `0x180170425`
- `GDI32!CreateCompatibleDC` at `0x18017044e`
- `GDI32!CreateCompatibleDC` at `0x180170425`
- `GDI32!CreateCompatibleDC` at `0x18017044e`
- `GDI32!CreateCompatibleBitmap` at `0x180170472`
- `GDI32!CreateCompatibleBitmap` at `0x180170472`
- `GDI32!GetDeviceCaps` at `0x180170375`
- `GDI32!GetDeviceCaps` at `0x180170375`
- `GDI32!CreateHalftonePalette` at `0x180170496`
- `GDI32!CreateHalftonePalette` at `0x180170496`
- `GDI32!SelectPalette` at `0x1801704b1`
- `GDI32!SelectPalette` at `0x180170550`
- `GDI32!SelectPalette` at `0x1801704b1`
- `GDI32!SelectPalette` at `0x180170550`
- `GDI32!RealizePalette` at `0x1801704bd`
- `GDI32!RealizePalette` at `0x1801704bd`
- `GDI32!StretchBlt` at `0x18017053e`
- `GDI32!StretchBlt` at `0x18017053e`
- `GDI32!SetBrushOrgEx` at `0x1801704f7`
- `GDI32!SetBrushOrgEx` at `0x1801704f7`
- `GDI32!SetStretchBltMode` at `0x1801704e2`
- `GDI32!SetStretchBltMode` at `0x1801704e2`
- `GDI32!GetBrushOrgEx` at `0x1801704d4`
- `GDI32!GetBrushOrgEx` at `0x1801704d4`
- `USER32!LoadImageW` at `0x1801703b1`
- `USER32!LoadImageW` at `0x1801703e5`
- `USER32!LoadImageW` at `0x1801703b1`
- `USER32!LoadImageW` at `0x1801703e5`
- `USER32!GetDC` at `0x180170364`
- `USER32!GetDC` at `0x180170364`
- `USER32!ReleaseDC` at `0x18017059c`
- `USER32!ReleaseDC` at `0x18017059c`

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
0x180170324  push    rbx
0x180170326  push    rbp
0x180170327  push    rsi
0x180170328  push    rdi
0x180170329  push    r12
0x18017032b  push    r13
0x18017032d  push    r14
0x18017032f  push    r15
0x180170331  sub     rsp, 0F8h
0x180170338  mov     rax, cs:__security_cookie
0x18017033f  xor     rax, rsp
0x180170342  mov     [rsp+138h+var_58], rax
0x18017034a  mov     r15d, r9d
0x18017034d  mov     ebp, r8d
0x180170350  mov     rbx, rdx
0x180170353  mov     rdi, rcx
0x180170356  test    rcx, rcx
0x180170359  jnz     short loc_180170362
0x18017035b  xor     eax, eax
0x18017035d  jmp     loc_1801705A5
0x180170362  xor     ecx, ecx; hWnd
0x180170364  call    cs:__imp_GetDC
0x18017036a  mov     rcx, rax; hdc
0x18017036d  mov     edx, 26h ; '&'; index
0x180170372  mov     rsi, rax
0x180170375  call    cs:__imp_GetDeviceCaps
0x18017037b  mov     rdx, rdi; name
0x18017037e  bt      eax, 8
0x180170382  jb      short loc_1801703BF
0x180170384  mov     r9d, 2
0x18017038a  mov     r8, rbx
0x18017038d  neg     r8
0x180170390  mov     rcx, rbx; hInst
0x180170393  sbb     r10d, r10d
0x180170396  not     r10d
0x180170399  and     r10d, 10h
0x18017039d  cmp     ebp, 1
0x1801703a0  mov     [rsp+138h+fuLoad], r10d; fuLoad
0x1801703a5  mov     [rsp+138h+cy], r15d; cy
0x1801703aa  cmovnz  r9d, ebp; cx
0x1801703ae  xor     r8d, r8d; type
0x1801703b1  call    cs:__imp_LoadImageW
0x1801703b7  mov     r14, rax
0x1801703ba  jmp     loc_180170597
0x1801703bf  xor     r14d, r14d
0x1801703c2  mov     rax, rbx
0x1801703c5  neg     rax
0x1801703c8  mov     r9d, ebp; cx
0x1801703cb  sbb     ecx, ecx
0x1801703cd  xor     r8d, r8d; type
0x1801703d0  and     ecx, 0FFFFFFF0h
0x1801703d3  add     ecx, 2010h
0x1801703d9  mov     [rsp+138h+fuLoad], ecx; fuLoad
0x1801703dd  mov     rcx, rbx; hInst
0x1801703e0  mov     [rsp+138h+cy], r15d; cy
0x1801703e5  call    cs:__imp_LoadImageW
0x1801703eb  mov     r15, rax
0x1801703ee  test    rax, rax
0x1801703f1  jz      loc_180170597
0x1801703f7  lea     ebx, [r14+68h]
0x1801703fb  xor     edx, edx; Val
0x1801703fd  mov     r8d, ebx; Size
0x180170400  lea     rcx, [rsp+138h+pv]; void *
0x180170405  call    memset_0
0x18017040a  lea     r8, [rsp+138h+pv]; pv
0x18017040f  mov     edx, ebx; c
0x180170411  mov     rcx, r15; h
0x180170414  call    cs:__imp_GetObjectW
0x18017041a  cmp     eax, ebx
0x18017041c  jnz     loc_18017058E
0x180170422  mov     rcx, rsi; hdc
0x180170425  call    cs:__imp_CreateCompatibleDC
0x18017042b  mov     rbp, rax
0x18017042e  test    rax, rax
0x180170431  jz      loc_18017058E
0x180170437  mov     rdx, r15; h
0x18017043a  mov     rcx, rax; hdc
0x18017043d  call    cs:__imp_SelectObject
0x180170443  mov     rcx, rsi; hdc
0x180170446  mov     [rsp+138h+var_D0], rax
0x18017044b  mov     rbx, rax
0x18017044e  call    cs:__imp_CreateCompatibleDC
0x180170454  mov     rdi, rax
0x180170457  test    rax, rax
0x18017045a  jz      loc_180170579
0x180170460  mov     r8d, [rsp+138h+hDest]; cy
0x180170468  mov     rcx, rsi; hdc
0x18017046b  mov     edx, [rsp+138h+wDest]; cx
0x180170472  call    cs:__imp_CreateCompatibleBitmap
0x180170478  mov     r14, rax
0x18017047b  test    rax, rax
0x18017047e  jz      loc_180170570
0x180170484  mov     rdx, rax; h
0x180170487  mov     rcx, rdi; hdc
0x18017048a  call    cs:__imp_SelectObject
0x180170490  mov     rcx, rdi; hdc
0x180170493  mov     r13, rax
0x180170496  call    cs:__imp_CreateHalftonePalette
0x18017049c  mov     r12, rax
0x18017049f  test    rax, rax
0x1801704a2  jz      loc_180170564
0x1801704a8  xor     r8d, r8d; bForceBkgd
0x1801704ab  mov     rdx, rax; hPal
0x1801704ae  mov     rcx, rdi; hdc
0x1801704b1  call    cs:__imp_SelectPalette
0x1801704b7  mov     rcx, rdi; hdc
0x1801704ba  mov     rbx, rax
0x1801704bd  call    cs:__imp_RealizePalette
0x1801704c3  lea     rdx, [rsp+138h+pt]; lppt
0x1801704c8  mov     qword ptr [rsp+138h+pt.x], 0
0x1801704d1  mov     rcx, rdi; hdc
0x1801704d4  call    cs:__imp_GetBrushOrgEx
0x1801704da  mov     edx, 4; mode
0x1801704df  mov     rcx, rdi; hdc
0x1801704e2  call    cs:__imp_SetStretchBltMode
0x1801704e8  mov     r8d, [rsp+138h+pt.y]; y
0x1801704ed  xor     r9d, r9d; lppt
0x1801704f0  mov     edx, [rsp+138h+pt.x]; x
0x1801704f4  mov     rcx, rdi; hdc
0x1801704f7  call    cs:__imp_SetBrushOrgEx
0x1801704fd  mov     eax, [rsp+138h+hDest]
0x180170504  xor     r8d, r8d; yDest
0x180170507  mov     r9d, [rsp+138h+wDest]; wDest
0x18017050f  xor     edx, edx; xDest
0x180170511  mov     [rsp+138h+rop], 0CC0020h; rop
0x180170519  mov     rcx, rdi; hdcDest
0x18017051c  mov     [rsp+138h+hSrc], eax; hSrc
0x180170520  mov     [rsp+138h+wSrc], r9d; wSrc
0x180170525  mov     [rsp+138h+ySrc], 0; ySrc
0x18017052d  mov     [rsp+138h+xSrc], 0; xSrc
0x180170535  mov     qword ptr [rsp+138h+fuLoad], rbp; hdcSrc
0x18017053a  mov     [rsp+138h+cy], eax; hDest
0x18017053e  call    cs:__imp_StretchBlt
0x180170544  mov     r8d, 1; bForceBkgd
0x18017054a  mov     rdx, rbx; hPal
0x18017054d  mov     rcx, rdi; hdc
0x180170550  call    cs:__imp_SelectPalette
0x180170556  mov     rcx, r12; ho
0x180170559  call    cs:__imp_DeleteObject
0x18017055f  mov     rbx, [rsp+138h+var_D0]
0x180170564  mov     rdx, r13; h
0x180170567  mov     rcx, rdi; hdc
0x18017056a  call    cs:__imp_SelectObject
0x180170570  mov     rcx, rdi; hdc
0x180170573  call    cs:__imp_DeleteDC
0x180170579  mov     rdx, rbx; h
0x18017057c  mov     rcx, rbp; hdc
0x18017057f  call    cs:__imp_SelectObject
0x180170585  mov     rcx, rbp; hdc
0x180170588  call    cs:__imp_DeleteDC
0x18017058e  mov     rcx, r15; ho
0x180170591  call    cs:__imp_DeleteObject
0x180170597  mov     rdx, rsi; hDC
0x18017059a  xor     ecx, ecx; hWnd
0x18017059c  call    cs:__imp_ReleaseDC
0x1801705a2  mov     rax, r14
0x1801705a5  mov     rcx, [rsp+138h+var_58]
0x1801705ad  xor     rcx, rsp; StackCookie
0x1801705b0  call    __security_check_cookie
0x1801705b5  add     rsp, 0F8h
0x1801705bc  pop     r15
0x1801705be  pop     r14
0x1801705c0  pop     r13
0x1801705c2  pop     r12
0x1801705c4  pop     rdi
0x1801705c5  pop     rsi
0x1801705c6  pop     rbp
0x1801705c7  pop     rbx
0x1801705c8  retn
```
