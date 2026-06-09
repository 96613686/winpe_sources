# DirectUI::LoadDDBitmap(ushort const *,HINSTANCE__ *,int,int)

- ea: `0x180459514`
- end: `0x1804597b9`
- name: `?LoadDDBitmap@DirectUI@@YAPEAUHBITMAP__@@PEBGPEAUHINSTANCE__@@HH@Z`
- size: `677`
- prototype: `HBITMAP __fastcall(LPCWSTR name, HINSTANCE hInst, HINSTANCE cx, int cy, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180450914`

## callees

- `0x180459514`
- `0x18054e286`
- `0x18054e310`

## import_xrefs

- `GDI32!GetBrushOrgEx` at `0x1804596c4`
- `GDI32!GetBrushOrgEx` at `0x1804596c4`
- `GDI32!SetStretchBltMode` at `0x1804596d2`
- `GDI32!SetStretchBltMode` at `0x1804596d2`
- `GDI32!CreateHalftonePalette` at `0x180459686`
- `GDI32!CreateHalftonePalette` at `0x180459686`
- `GDI32!StretchBlt` at `0x18045972e`
- `GDI32!StretchBlt` at `0x18045972e`
- `GDI32!SetBrushOrgEx` at `0x1804596e7`
- `GDI32!SetBrushOrgEx` at `0x1804596e7`
- `GDI32!DeleteObject` at `0x180459749`
- `GDI32!DeleteObject` at `0x180459781`
- `GDI32!DeleteObject` at `0x180459749`
- `GDI32!DeleteObject` at `0x180459781`
- `GDI32!SelectObject` at `0x18045962d`
- `GDI32!SelectObject` at `0x18045967a`
- `GDI32!SelectObject` at `0x18045975a`
- `GDI32!SelectObject` at `0x18045976f`
- `GDI32!SelectObject` at `0x18045962d`
- `GDI32!SelectObject` at `0x18045967a`
- `GDI32!SelectObject` at `0x18045975a`
- `GDI32!SelectObject` at `0x18045976f`
- `GDI32!GetObjectW` at `0x180459604`
- `GDI32!GetObjectW` at `0x180459604`
- `GDI32!GetDeviceCaps` at `0x180459565`
- `GDI32!GetDeviceCaps` at `0x180459565`
- `GDI32!DeleteDC` at `0x180459763`
- `GDI32!DeleteDC` at `0x180459778`
- `GDI32!DeleteDC` at `0x180459763`
- `GDI32!DeleteDC` at `0x180459778`
- `GDI32!CreateCompatibleDC` at `0x180459615`
- `GDI32!CreateCompatibleDC` at `0x18045963e`
- `GDI32!CreateCompatibleDC` at `0x180459615`
- `GDI32!CreateCompatibleDC` at `0x18045963e`
- `GDI32!CreateCompatibleBitmap` at `0x180459662`
- `GDI32!CreateCompatibleBitmap` at `0x180459662`
- `GDI32!SelectPalette` at `0x1804596a1`
- `GDI32!SelectPalette` at `0x180459740`
- `GDI32!SelectPalette` at `0x1804596a1`
- `GDI32!SelectPalette` at `0x180459740`
- `GDI32!RealizePalette` at `0x1804596ad`
- `GDI32!RealizePalette` at `0x1804596ad`
- `USER32!ReleaseDC` at `0x18045978c`
- `USER32!ReleaseDC` at `0x18045978c`
- `USER32!GetDC` at `0x180459554`
- `USER32!GetDC` at `0x180459554`
- `USER32!LoadImageW` at `0x1804595a1`
- `USER32!LoadImageW` at `0x1804595d5`
- `USER32!LoadImageW` at `0x1804595a1`
- `USER32!LoadImageW` at `0x1804595d5`

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
0x180459514  push    rbx
0x180459516  push    rbp
0x180459517  push    rsi
0x180459518  push    rdi
0x180459519  push    r12
0x18045951b  push    r13
0x18045951d  push    r14
0x18045951f  push    r15
0x180459521  sub     rsp, 0F8h
0x180459528  mov     rax, cs:__security_cookie
0x18045952f  xor     rax, rsp
0x180459532  mov     [rsp+138h+var_58], rax
0x18045953a  mov     r15d, r9d
0x18045953d  mov     ebp, r8d
0x180459540  mov     rbx, rdx
0x180459543  mov     rdi, rcx
0x180459546  test    rcx, rcx
0x180459549  jnz     short loc_180459552
0x18045954b  xor     eax, eax
0x18045954d  jmp     loc_180459795
0x180459552  xor     ecx, ecx; hWnd
0x180459554  call    cs:__imp_GetDC
0x18045955a  mov     rcx, rax; hdc
0x18045955d  mov     edx, 26h ; '&'; index
0x180459562  mov     rsi, rax
0x180459565  call    cs:__imp_GetDeviceCaps
0x18045956b  mov     rdx, rdi; name
0x18045956e  bt      eax, 8
0x180459572  jb      short loc_1804595AF
0x180459574  mov     r9d, 2
0x18045957a  mov     r8, rbx
0x18045957d  neg     r8
0x180459580  mov     rcx, rbx; hInst
0x180459583  sbb     r10d, r10d
0x180459586  not     r10d
0x180459589  and     r10d, 10h
0x18045958d  cmp     ebp, 1
0x180459590  mov     [rsp+138h+fuLoad], r10d; fuLoad
0x180459595  mov     [rsp+138h+cy], r15d; cy
0x18045959a  cmovnz  r9d, ebp; cx
0x18045959e  xor     r8d, r8d; type
0x1804595a1  call    cs:__imp_LoadImageW
0x1804595a7  mov     r14, rax
0x1804595aa  jmp     loc_180459787
0x1804595af  xor     r14d, r14d
0x1804595b2  mov     rax, rbx
0x1804595b5  neg     rax
0x1804595b8  mov     r9d, ebp; cx
0x1804595bb  sbb     ecx, ecx
0x1804595bd  xor     r8d, r8d; type
0x1804595c0  and     ecx, 0FFFFFFF0h
0x1804595c3  add     ecx, 2010h
0x1804595c9  mov     [rsp+138h+fuLoad], ecx; fuLoad
0x1804595cd  mov     rcx, rbx; hInst
0x1804595d0  mov     [rsp+138h+cy], r15d; cy
0x1804595d5  call    cs:__imp_LoadImageW
0x1804595db  mov     r15, rax
0x1804595de  test    rax, rax
0x1804595e1  jz      loc_180459787
0x1804595e7  lea     ebx, [r14+68h]
0x1804595eb  xor     edx, edx; Val
0x1804595ed  mov     r8d, ebx; Size
0x1804595f0  lea     rcx, [rsp+138h+pv]; void *
0x1804595f5  call    memset_0
0x1804595fa  lea     r8, [rsp+138h+pv]; pv
0x1804595ff  mov     edx, ebx; c
0x180459601  mov     rcx, r15; h
0x180459604  call    cs:__imp_GetObjectW
0x18045960a  cmp     eax, ebx
0x18045960c  jnz     loc_18045977E
0x180459612  mov     rcx, rsi; hdc
0x180459615  call    cs:__imp_CreateCompatibleDC
0x18045961b  mov     rbp, rax
0x18045961e  test    rax, rax
0x180459621  jz      loc_18045977E
0x180459627  mov     rdx, r15; h
0x18045962a  mov     rcx, rax; hdc
0x18045962d  call    cs:__imp_SelectObject
0x180459633  mov     rcx, rsi; hdc
0x180459636  mov     [rsp+138h+var_D0], rax
0x18045963b  mov     rbx, rax
0x18045963e  call    cs:__imp_CreateCompatibleDC
0x180459644  mov     rdi, rax
0x180459647  test    rax, rax
0x18045964a  jz      loc_180459769
0x180459650  mov     r8d, [rsp+138h+hDest]; cy
0x180459658  mov     rcx, rsi; hdc
0x18045965b  mov     edx, [rsp+138h+wDest]; cx
0x180459662  call    cs:__imp_CreateCompatibleBitmap
0x180459668  mov     r14, rax
0x18045966b  test    rax, rax
0x18045966e  jz      loc_180459760
0x180459674  mov     rdx, rax; h
0x180459677  mov     rcx, rdi; hdc
0x18045967a  call    cs:__imp_SelectObject
0x180459680  mov     rcx, rdi; hdc
0x180459683  mov     r13, rax
0x180459686  call    cs:__imp_CreateHalftonePalette
0x18045968c  mov     r12, rax
0x18045968f  test    rax, rax
0x180459692  jz      loc_180459754
0x180459698  xor     r8d, r8d; bForceBkgd
0x18045969b  mov     rdx, rax; hPal
0x18045969e  mov     rcx, rdi; hdc
0x1804596a1  call    cs:__imp_SelectPalette
0x1804596a7  mov     rcx, rdi; hdc
0x1804596aa  mov     rbx, rax
0x1804596ad  call    cs:__imp_RealizePalette
0x1804596b3  lea     rdx, [rsp+138h+pt]; lppt
0x1804596b8  mov     qword ptr [rsp+138h+pt.x], 0
0x1804596c1  mov     rcx, rdi; hdc
0x1804596c4  call    cs:__imp_GetBrushOrgEx
0x1804596ca  mov     edx, 4; mode
0x1804596cf  mov     rcx, rdi; hdc
0x1804596d2  call    cs:__imp_SetStretchBltMode
0x1804596d8  mov     r8d, [rsp+138h+pt.y]; y
0x1804596dd  xor     r9d, r9d; lppt
0x1804596e0  mov     edx, [rsp+138h+pt.x]; x
0x1804596e4  mov     rcx, rdi; hdc
0x1804596e7  call    cs:__imp_SetBrushOrgEx
0x1804596ed  mov     eax, [rsp+138h+hDest]
0x1804596f4  xor     r8d, r8d; yDest
0x1804596f7  mov     r9d, [rsp+138h+wDest]; wDest
0x1804596ff  xor     edx, edx; xDest
0x180459701  mov     [rsp+138h+rop], 0CC0020h; rop
0x180459709  mov     rcx, rdi; hdcDest
0x18045970c  mov     [rsp+138h+hSrc], eax; hSrc
0x180459710  mov     [rsp+138h+wSrc], r9d; wSrc
0x180459715  mov     [rsp+138h+ySrc], 0; ySrc
0x18045971d  mov     [rsp+138h+xSrc], 0; xSrc
0x180459725  mov     qword ptr [rsp+138h+fuLoad], rbp; hdcSrc
0x18045972a  mov     [rsp+138h+cy], eax; hDest
0x18045972e  call    cs:__imp_StretchBlt
0x180459734  mov     r8d, 1; bForceBkgd
0x18045973a  mov     rdx, rbx; hPal
0x18045973d  mov     rcx, rdi; hdc
0x180459740  call    cs:__imp_SelectPalette
0x180459746  mov     rcx, r12; ho
0x180459749  call    cs:__imp_DeleteObject
0x18045974f  mov     rbx, [rsp+138h+var_D0]
0x180459754  mov     rdx, r13; h
0x180459757  mov     rcx, rdi; hdc
0x18045975a  call    cs:__imp_SelectObject
0x180459760  mov     rcx, rdi; hdc
0x180459763  call    cs:__imp_DeleteDC
0x180459769  mov     rdx, rbx; h
0x18045976c  mov     rcx, rbp; hdc
0x18045976f  call    cs:__imp_SelectObject
0x180459775  mov     rcx, rbp; hdc
0x180459778  call    cs:__imp_DeleteDC
0x18045977e  mov     rcx, r15; ho
0x180459781  call    cs:__imp_DeleteObject
0x180459787  mov     rdx, rsi; hDC
0x18045978a  xor     ecx, ecx; hWnd
0x18045978c  call    cs:__imp_ReleaseDC
0x180459792  mov     rax, r14
0x180459795  mov     rcx, [rsp+138h+var_58]
0x18045979d  xor     rcx, rsp; StackCookie
0x1804597a0  call    __security_check_cookie
0x1804597a5  add     rsp, 0F8h
0x1804597ac  pop     r15
0x1804597ae  pop     r14
0x1804597b0  pop     r13
0x1804597b2  pop     r12
0x1804597b4  pop     rdi
0x1804597b5  pop     rsi
0x1804597b6  pop     rbp
0x1804597b7  pop     rbx
0x1804597b8  retn
```
