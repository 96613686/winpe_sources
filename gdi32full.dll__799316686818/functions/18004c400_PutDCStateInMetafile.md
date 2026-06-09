# PutDCStateInMetafile

- ea: `0x18004c400`
- end: `0x18004c751`
- name: `PutDCStateInMetafile`
- size: `849`
- prototype: `__int64 __fastcall(HDC hdc)`
- caller_count: `1`
- callee_count: `29`
- tags: ``

## callers

- `0x18004c018`

## callees

- `0x18000d6c0`
- `0x180010000`
- `0x180010140`
- `0x180010210`
- `0x1800102f0`
- `0x1800104e0`
- `0x180010690`
- `0x180010790`
- `0x180010870`
- `0x180010950`
- `0x180010b70`
- `0x180014240`
- `0x180015970`
- `0x180016900`
- `0x18001dc40`
- `0x1800200f0`
- `0x180021fa0`
- `0x18004c400`
- `0x18004c760`
- `0x18004c840`
- `0x180057d58`
- `0x180059f00`
- `0x180067540`
- `0x18006b8c0`
- `0x180086c80`
- `0x180088630`
- `0x18008ab70`
- `0x18008ac30`
- `0x18008acf0`

## import_xrefs

- `GDI32!MoveToEx` at `0x18004c6b5`
- `GDI32!MoveToEx` at `0x18004c6b5`
- `GDI32!SelectObject` at `0x18004c444`
- `GDI32!SelectObject` at `0x18004c466`
- `GDI32!SelectObject` at `0x18004c490`
- `GDI32!SelectObject` at `0x18004c444`
- `GDI32!SelectObject` at `0x18004c466`
- `GDI32!SelectObject` at `0x18004c490`
- `GDI32!SetBkMode` at `0x18004c4f0`
- `GDI32!SetBkMode` at `0x18004c4f0`
- `GDI32!SetPolyFillMode` at `0x18004c510`
- `GDI32!SetPolyFillMode` at `0x18004c510`
- `GDI32!SetStretchBltMode` at `0x18004c54f`
- `GDI32!SetStretchBltMode` at `0x18004c54f`
- `GDI32!SetTextAlign` at `0x18004c56e`
- `GDI32!SetTextAlign` at `0x18004c56e`
- `GDI32!SetTextColor` at `0x18004c4d0`
- `GDI32!SetTextColor` at `0x18004c4d0`
- `GDI32!SetICMMode` at `0x18004c6e6`
- `GDI32!SetICMMode` at `0x18004c6f8`
- `GDI32!SetICMMode` at `0x18004c703`
- `GDI32!SetICMMode` at `0x18004c6e6`
- `GDI32!SetICMMode` at `0x18004c6f8`
- `GDI32!SetICMMode` at `0x18004c703`
- `GDI32!pldcGet` at `0x18004c416`
- `GDI32!pldcGet` at `0x18004c416`
- `win32u!NtGdiAnyLinkedFonts` at `0x18004c729`
- `win32u!NtGdiAnyLinkedFonts` at `0x18004c729`

## pseudocode

```c
__int64 __fastcall PutDCStateInMetafile(HDC hdc)
{
  __int64 v2; // rbx
  void *DCObject; // rax
  void *v4; // rax
  void *v5; // rax
  COLORREF BkColor; // eax
  COLORREF TextColor; // eax
  int BkMode; // eax
  int PolyFillMode; // eax
  int ROP2; // eax
  int StretchBltMode; // eax
  UINT TextAlign; // eax
  int DCDWord; // ebx
  int v14; // eax
  int MapMode; // ebx
  int v16; // eax
  HCOLORSPACE ColorSpace; // rax
  struct tagPOINT point; // [rsp+20h] [rbp-10h] BYREF
  struct tagPOINT v20; // [rsp+28h] [rbp-8h] BYREF
  struct tagPOINT pt; // [rsp+58h] [rbp+28h] BYREF
  struct tagSIZE v22; // [rsp+60h] [rbp+30h] BYREF
  struct tagSIZE size; // [rsp+68h] [rbp+38h] BYREF

  pt = 0;
  v2 = pldcGet(hdc);
  if ( !v2 )
    return 0;
  DCObject = (void *)GetDCObject(hdc, 3145728);
  if ( !DCObject )
    return 0;
  SelectObject(hdc, DCObject);
  v4 = (void *)GetDCObject(hdc, 0x100000);
  if ( !v4 )
    return 0;
  SelectObject(hdc, v4);
  *(_QWORD *)(v2 + 120) = 0;
  v5 = (void *)GetDCObject(hdc, 655360);
  if ( !v5 )
    return 0;
  SelectObject(hdc, v5);
  if ( GetBkColor(hdc) != 0xFFFFFF )
  {
    BkColor = GetBkColor(hdc);
    SetBkColor(hdc, BkColor);
  }
  if ( GetTextColor(hdc) )
  {
    TextColor = GetTextColor(hdc);
    SetTextColor(hdc, TextColor);
  }
  if ( GetBkMode(hdc) != 2 )
  {
    BkMode = GetBkMode(hdc);
    SetBkMode(hdc, BkMode);
  }
  if ( GetPolyFillMode(hdc) != 1 )
  {
    PolyFillMode = GetPolyFillMode(hdc);
    SetPolyFillMode(hdc, PolyFillMode);
  }
  if ( GetROP2(hdc) != 13 )
  {
    ROP2 = GetROP2(hdc);
    SetROP2(hdc, ROP2);
  }
  if ( GetStretchBltMode(hdc) != 1 )
  {
    StretchBltMode = GetStretchBltMode(hdc);
    SetStretchBltMode(hdc, StretchBltMode);
  }
  if ( GetTextAlign(hdc) )
  {
    TextAlign = GetTextAlign(hdc);
    SetTextAlign(hdc, TextAlign);
  }
  if ( (unsigned int)GetDCDWord(hdc, 2) || (unsigned int)GetDCDWord(hdc, 3) )
  {
    DCDWord = GetDCDWord(hdc, 3);
    v14 = GetDCDWord(hdc, 2);
    SetTextJustification(hdc, v14, DCDWord);
  }
  if ( GetMapMode(hdc) != 1 )
  {
    point = 0;
    v20 = 0;
    MapMode = GetMapMode(hdc);
    v22 = 0;
    size = 0;
    GetViewportExtEx(hdc, &size);
    GetWindowExtEx(hdc, &v22);
    GetWindowOrgEx(hdc, &point);
    GetViewportOrgEx(hdc, &v20);
    SetMapMode(hdc, 1);
    SetMapMode(hdc, MapMode);
    if ( (unsigned int)(MapMode - 7) <= 1 )
    {
      SetWindowExtEx(hdc, v22.cx, v22.cy, 0);
      SetViewportExtEx(hdc, size.cx, size.cy, 0);
    }
    SetWindowOrgEx(hdc, point.x, point.y, 0);
    SetViewportOrgEx(hdc, v20.x, v20.y, 0);
  }
  if ( GetCurrentPositionEx(hdc, &pt) )
    MoveToEx(hdc, pt.x, pt.y, 0);
  if ( GetBrushOrgEx(hdc, &pt) )
    SetBrushOrgEx(hdc, pt.x, pt.y, &pt);
  if ( SetICMMode(hdc, 3) )
  {
    v16 = SetICMMode(hdc, 3);
    SetICMMode(hdc, v16);
  }
  if ( GetColorSpace(hdc) )
  {
    ColorSpace = GetColorSpace(hdc);
    SetColorSpace(hdc, ColorSpace);
  }
  if ( !(unsigned int)NtGdiAnyLinkedFonts() )
    MF_SetLinkedUFIs(hdc, 0, 0);
  return 1;
}

```

## disassembly

```asm
0x18004c400  push    rbp
0x18004c402  push    rbx
0x18004c403  push    rdi
0x18004c404  mov     rbp, rsp
0x18004c407  sub     rsp, 30h
0x18004c40b  mov     rdi, rcx
0x18004c40e  mov     qword ptr [rbp+pt.x], 0
0x18004c416  call    cs:__imp_pldcGet
0x18004c41c  mov     rbx, rax
0x18004c41f  test    rax, rax
0x18004c422  jz      loc_18004C747
0x18004c428  mov     edx, 300000h
0x18004c42d  mov     rcx, rdi
0x18004c430  call    GetDCObject
0x18004c435  test    rax, rax
0x18004c438  jz      loc_18004C747
0x18004c43e  mov     rdx, rax; h
0x18004c441  mov     rcx, rdi; hdc
0x18004c444  call    cs:__imp_SelectObject
0x18004c44a  mov     edx, 100000h
0x18004c44f  mov     rcx, rdi
0x18004c452  call    GetDCObject
0x18004c457  test    rax, rax
0x18004c45a  jz      loc_18004C747
0x18004c460  mov     rdx, rax; h
0x18004c463  mov     rcx, rdi; hdc
0x18004c466  call    cs:__imp_SelectObject
0x18004c46c  mov     edx, 0A0000h
0x18004c471  mov     qword ptr [rbx+78h], 0
0x18004c479  mov     rcx, rdi
0x18004c47c  call    GetDCObject
0x18004c481  test    rax, rax
0x18004c484  jz      loc_18004C747
0x18004c48a  mov     rdx, rax; h
0x18004c48d  mov     rcx, rdi; hdc
0x18004c490  call    cs:__imp_SelectObject
0x18004c496  mov     rcx, rdi; hdc
0x18004c499  call    GetBkColor
0x18004c49e  cmp     eax, 0FFFFFFh
0x18004c4a3  jz      short loc_18004C4B7
0x18004c4a5  mov     rcx, rdi; hdc
0x18004c4a8  call    GetBkColor
0x18004c4ad  mov     edx, eax; color
0x18004c4af  mov     rcx, rdi; hdc
0x18004c4b2  call    SetBkColor
0x18004c4b7  mov     rcx, rdi; hdc
0x18004c4ba  call    GetTextColor
0x18004c4bf  test    eax, eax
0x18004c4c1  jz      short loc_18004C4D6
0x18004c4c3  mov     rcx, rdi; hdc
0x18004c4c6  call    GetTextColor
0x18004c4cb  mov     edx, eax; color
0x18004c4cd  mov     rcx, rdi; hdc
0x18004c4d0  call    cs:__imp_SetTextColor
0x18004c4d6  mov     rcx, rdi; hdc
0x18004c4d9  call    GetBkMode
0x18004c4de  cmp     eax, 2
0x18004c4e1  jz      short loc_18004C4F6
0x18004c4e3  mov     rcx, rdi; hdc
0x18004c4e6  call    GetBkMode
0x18004c4eb  mov     edx, eax; mode
0x18004c4ed  mov     rcx, rdi; hdc
0x18004c4f0  call    cs:__imp_SetBkMode
0x18004c4f6  mov     rcx, rdi; hdc
0x18004c4f9  call    GetPolyFillMode
0x18004c4fe  cmp     eax, 1
0x18004c501  jz      short loc_18004C516
0x18004c503  mov     rcx, rdi; hdc
0x18004c506  call    GetPolyFillMode
0x18004c50b  mov     edx, eax; mode
0x18004c50d  mov     rcx, rdi; hdc
0x18004c510  call    cs:__imp_SetPolyFillMode
0x18004c516  mov     rcx, rdi; hdc
0x18004c519  call    GetROP2
0x18004c51e  cmp     eax, 0Dh
0x18004c521  jz      short loc_18004C535
0x18004c523  mov     rcx, rdi; hdc
0x18004c526  call    GetROP2
0x18004c52b  mov     edx, eax; rop2
0x18004c52d  mov     rcx, rdi; hdc
0x18004c530  call    SetROP2
0x18004c535  mov     rcx, rdi; hdc
0x18004c538  call    GetStretchBltMode
0x18004c53d  cmp     eax, 1
0x18004c540  jz      short loc_18004C555
0x18004c542  mov     rcx, rdi; hdc
0x18004c545  call    GetStretchBltMode
0x18004c54a  mov     edx, eax; mode
0x18004c54c  mov     rcx, rdi; hdc
0x18004c54f  call    cs:__imp_SetStretchBltMode
0x18004c555  mov     rcx, rdi; hdc
0x18004c558  call    GetTextAlign
0x18004c55d  test    eax, eax
0x18004c55f  jz      short loc_18004C574
0x18004c561  mov     rcx, rdi; hdc
0x18004c564  call    GetTextAlign
0x18004c569  mov     edx, eax; align
0x18004c56b  mov     rcx, rdi; hdc
0x18004c56e  call    cs:__imp_SetTextAlign
0x18004c574  xor     r8d, r8d
0x18004c577  mov     rcx, rdi
0x18004c57a  lea     edx, [r8+2]
0x18004c57e  call    GetDCDWord
0x18004c583  test    eax, eax
0x18004c585  jnz     short loc_18004C599
0x18004c587  xor     r8d, r8d
0x18004c58a  lea     edx, [rax+3]
0x18004c58d  mov     rcx, rdi
0x18004c590  call    GetDCDWord
0x18004c595  test    eax, eax
0x18004c597  jz      short loc_18004C5C6
0x18004c599  xor     r8d, r8d
0x18004c59c  mov     rcx, rdi
0x18004c59f  lea     edx, [r8+3]
0x18004c5a3  call    GetDCDWord
0x18004c5a8  xor     r8d, r8d
0x18004c5ab  mov     rcx, rdi
0x18004c5ae  mov     ebx, eax
0x18004c5b0  lea     edx, [r8+2]
0x18004c5b4  call    GetDCDWord
0x18004c5b9  mov     r8d, ebx; count
0x18004c5bc  mov     edx, eax; extra
0x18004c5be  mov     rcx, rdi; hdc
0x18004c5c1  call    SetTextJustification
0x18004c5c6  mov     rcx, rdi; hdc
0x18004c5c9  call    GetMapMode
0x18004c5ce  cmp     eax, 1
0x18004c5d1  jz      loc_18004C698
0x18004c5d7  mov     rcx, rdi; hdc
0x18004c5da  call    GetMapMode
0x18004c5df  lea     rdx, [rbp+size]; lpsize
0x18004c5e3  mov     qword ptr [rbp+point.x], 0
0x18004c5eb  mov     rcx, rdi; hdc
0x18004c5ee  mov     qword ptr [rbp+var_8.x], 0
0x18004c5f6  mov     ebx, eax
0x18004c5f8  mov     qword ptr [rbp+arg_10.cx], 0
0x18004c600  mov     qword ptr [rbp+size.cx], 0
0x18004c608  call    GetViewportExtEx
0x18004c60d  lea     rdx, [rbp+arg_10]; lpsize
0x18004c611  mov     rcx, rdi; hdc
0x18004c614  call    GetWindowExtEx
0x18004c619  lea     rdx, [rbp+point]; lppoint
0x18004c61d  mov     rcx, rdi; hdc
0x18004c620  call    GetWindowOrgEx
0x18004c625  lea     rdx, [rbp+var_8]; lppoint
0x18004c629  mov     rcx, rdi; hdc
0x18004c62c  call    GetViewportOrgEx
0x18004c631  mov     edx, 1; iMode
0x18004c636  mov     rcx, rdi; hdc
0x18004c639  call    SetMapMode
0x18004c63e  mov     edx, ebx; iMode
0x18004c640  mov     rcx, rdi; hdc
0x18004c643  call    SetMapMode
0x18004c648  lea     eax, [rbx-7]
0x18004c64b  cmp     eax, 1
0x18004c64e  ja      short loc_18004C674
0x18004c650  mov     r8d, [rbp+arg_10.cy]; y
0x18004c654  xor     r9d, r9d; lpsz
0x18004c657  mov     edx, [rbp+arg_10.cx]; x
0x18004c65a  mov     rcx, rdi; hdc
0x18004c65d  call    SetWindowExtEx
0x18004c662  mov     r8d, [rbp+size.cy]; y
0x18004c666  xor     r9d, r9d; lpsz
0x18004c669  mov     edx, [rbp+size.cx]; x
0x18004c66c  mov     rcx, rdi; hdc
0x18004c66f  call    SetViewportExtEx
0x18004c674  mov     r8d, [rbp+point.y]; y
0x18004c678  xor     r9d, r9d; lppt
0x18004c67b  mov     edx, [rbp+point.x]; x
0x18004c67e  mov     rcx, rdi; hdc
0x18004c681  call    SetWindowOrgEx
0x18004c686  mov     r8d, [rbp+var_8.y]; y
0x18004c68a  xor     r9d, r9d; lppt
0x18004c68d  mov     edx, [rbp+var_8.x]; x
0x18004c690  mov     rcx, rdi; hdc
0x18004c693  call    SetViewportOrgEx
0x18004c698  lea     rdx, [rbp+pt]; lppt
0x18004c69c  mov     rcx, rdi; hdc
0x18004c69f  call    GetCurrentPositionEx
0x18004c6a4  test    eax, eax
0x18004c6a6  jz      short loc_18004C6BB
0x18004c6a8  mov     r8d, [rbp+pt.y]; y
0x18004c6ac  xor     r9d, r9d; lppt
0x18004c6af  mov     edx, [rbp+pt.x]; x
0x18004c6b2  mov     rcx, rdi; hdc
0x18004c6b5  call    cs:__imp_MoveToEx
0x18004c6bb  lea     rdx, [rbp+pt]; lppt
0x18004c6bf  mov     rcx, rdi; hdc
0x18004c6c2  call    GetBrushOrgEx
0x18004c6c7  test    eax, eax
0x18004c6c9  jz      short loc_18004C6DE
0x18004c6cb  mov     r8d, [rbp+pt.y]; y
0x18004c6cf  lea     r9, [rbp+pt]; lppt
0x18004c6d3  mov     edx, [rbp+pt.x]; x
0x18004c6d6  mov     rcx, rdi; hdc
0x18004c6d9  call    SetBrushOrgEx
0x18004c6de  mov     edx, 3; mode
0x18004c6e3  mov     rcx, rdi; hdc
0x18004c6e6  call    cs:__imp_SetICMMode
0x18004c6ec  test    eax, eax
0x18004c6ee  jz      short loc_18004C709
0x18004c6f0  mov     edx, 3; mode
0x18004c6f5  mov     rcx, rdi; hdc
0x18004c6f8  call    cs:__imp_SetICMMode
0x18004c6fe  mov     edx, eax; mode
0x18004c700  mov     rcx, rdi; hdc
0x18004c703  call    cs:__imp_SetICMMode
0x18004c709  mov     rcx, rdi; hdc
0x18004c70c  call    GetColorSpace
0x18004c711  test    rax, rax
0x18004c714  jz      short loc_18004C729
0x18004c716  mov     rcx, rdi; hdc
0x18004c719  call    GetColorSpace
0x18004c71e  mov     rdx, rax; hcs
0x18004c721  mov     rcx, rdi; hdc
0x18004c724  call    SetColorSpace
0x18004c729  call    cs:__imp_NtGdiAnyLinkedFonts
0x18004c72f  test    eax, eax
0x18004c731  jnz     short loc_18004C740
0x18004c733  xor     r8d, r8d
0x18004c736  xor     edx, edx
0x18004c738  mov     rcx, rdi
0x18004c73b  call    MF_SetLinkedUFIs
0x18004c740  mov     eax, 1
0x18004c745  jmp     short loc_18004C749
0x18004c747  xor     eax, eax
0x18004c749  add     rsp, 30h
0x18004c74d  pop     rdi
0x18004c74e  pop     rbx
0x18004c74f  pop     rbp
0x18004c750  retn
```
