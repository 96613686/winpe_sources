# PutDCStateInMetafile

- ea: `0x180027dbc`
- end: `0x180028162`
- name: `PutDCStateInMetafile`
- size: `934`
- prototype: `__int64 __fastcall(HDC hdc)`
- caller_count: `1`
- callee_count: `29`
- tags: ``

## callers

- `0x180052060`

## callees

- `0x180006a28`
- `0x180018720`
- `0x180018860`
- `0x180018940`
- `0x180018a20`
- `0x180018c30`
- `0x180018df0`
- `0x180018f00`
- `0x180018fe0`
- `0x1800190c0`
- `0x180019310`
- `0x18001e920`
- `0x1800209d0`
- `0x180021e50`
- `0x180022b20`
- `0x180027350`
- `0x180027dbc`
- `0x180028170`
- `0x180028dd0`
- `0x18002ada0`
- `0x18005cba8`
- `0x18005dfc0`
- `0x18006bcb0`
- `0x180070200`
- `0x18008c060`
- `0x18008db50`
- `0x1800902a0`
- `0x180090360`
- `0x180090420`

## import_xrefs

- `GDI32!MoveToEx` at `0x1800280a7`
- `GDI32!MoveToEx` at `0x1800280a7`
- `GDI32!SelectObject` at `0x180027e06`
- `GDI32!SelectObject` at `0x180027e2e`
- `GDI32!SelectObject` at `0x180027e5e`
- `GDI32!SelectObject` at `0x180027e06`
- `GDI32!SelectObject` at `0x180027e2e`
- `GDI32!SelectObject` at `0x180027e5e`
- `GDI32!SetBkMode` at `0x180027eca`
- `GDI32!SetBkMode` at `0x180027eca`
- `GDI32!SetPolyFillMode` at `0x180027ef0`
- `GDI32!SetPolyFillMode` at `0x180027ef0`
- `GDI32!SetStretchBltMode` at `0x180027f35`
- `GDI32!SetStretchBltMode` at `0x180027f35`
- `GDI32!SetTextAlign` at `0x180027f5a`
- `GDI32!SetTextAlign` at `0x180027f5a`
- `GDI32!SetTextColor` at `0x180027ea4`
- `GDI32!SetTextColor` at `0x180027ea4`
- `GDI32!SetICMMode` at `0x1800280de`
- `GDI32!SetICMMode` at `0x1800280f6`
- `GDI32!SetICMMode` at `0x180028107`
- `GDI32!SetICMMode` at `0x1800280de`
- `GDI32!SetICMMode` at `0x1800280f6`
- `GDI32!SetICMMode` at `0x180028107`
- `GDI32!pldcGet` at `0x180027dd2`
- `GDI32!pldcGet` at `0x180027dd2`
- `win32u!NtGdiAnyLinkedFonts` at `0x180028133`
- `win32u!NtGdiAnyLinkedFonts` at `0x180028133`

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
0x180027dbc  push    rbp
0x180027dbe  push    rbx
0x180027dbf  push    rdi
0x180027dc0  mov     rbp, rsp
0x180027dc3  sub     rsp, 30h
0x180027dc7  mov     rdi, rcx
0x180027dca  mov     qword ptr [rbp+pt.x], 0
0x180027dd2  call    cs:__imp_pldcGet
0x180027dd9  nop     dword ptr [rax+rax+00h]
0x180027dde  mov     rbx, rax
0x180027de1  test    rax, rax
0x180027de4  jz      loc_180028157
0x180027dea  mov     edx, 300000h
0x180027def  mov     rcx, rdi
0x180027df2  call    GetDCObject
0x180027df7  test    rax, rax
0x180027dfa  jz      loc_180028157
0x180027e00  mov     rdx, rax; h
0x180027e03  mov     rcx, rdi; hdc
0x180027e06  call    cs:__imp_SelectObject
0x180027e0d  nop     dword ptr [rax+rax+00h]
0x180027e12  mov     edx, 100000h
0x180027e17  mov     rcx, rdi
0x180027e1a  call    GetDCObject
0x180027e1f  test    rax, rax
0x180027e22  jz      loc_180028157
0x180027e28  mov     rdx, rax; h
0x180027e2b  mov     rcx, rdi; hdc
0x180027e2e  call    cs:__imp_SelectObject
0x180027e35  nop     dword ptr [rax+rax+00h]
0x180027e3a  mov     edx, 0A0000h
0x180027e3f  mov     qword ptr [rbx+78h], 0
0x180027e47  mov     rcx, rdi
0x180027e4a  call    GetDCObject
0x180027e4f  test    rax, rax
0x180027e52  jz      loc_180028157
0x180027e58  mov     rdx, rax; h
0x180027e5b  mov     rcx, rdi; hdc
0x180027e5e  call    cs:__imp_SelectObject
0x180027e65  nop     dword ptr [rax+rax+00h]
0x180027e6a  mov     rcx, rdi; hdc
0x180027e6d  call    GetBkColor
0x180027e72  cmp     eax, 0FFFFFFh
0x180027e77  jz      short loc_180027E8B
0x180027e79  mov     rcx, rdi; hdc
0x180027e7c  call    GetBkColor
0x180027e81  mov     edx, eax; color
0x180027e83  mov     rcx, rdi; hdc
0x180027e86  call    SetBkColor
0x180027e8b  mov     rcx, rdi; hdc
0x180027e8e  call    GetTextColor
0x180027e93  test    eax, eax
0x180027e95  jz      short loc_180027EB0
0x180027e97  mov     rcx, rdi; hdc
0x180027e9a  call    GetTextColor
0x180027e9f  mov     edx, eax; color
0x180027ea1  mov     rcx, rdi; hdc
0x180027ea4  call    cs:__imp_SetTextColor
0x180027eab  nop     dword ptr [rax+rax+00h]
0x180027eb0  mov     rcx, rdi; hdc
0x180027eb3  call    GetBkMode
0x180027eb8  cmp     eax, 2
0x180027ebb  jz      short loc_180027ED6
0x180027ebd  mov     rcx, rdi; hdc
0x180027ec0  call    GetBkMode
0x180027ec5  mov     edx, eax; mode
0x180027ec7  mov     rcx, rdi; hdc
0x180027eca  call    cs:__imp_SetBkMode
0x180027ed1  nop     dword ptr [rax+rax+00h]
0x180027ed6  mov     rcx, rdi; hdc
0x180027ed9  call    GetPolyFillMode
0x180027ede  cmp     eax, 1
0x180027ee1  jz      short loc_180027EFC
0x180027ee3  mov     rcx, rdi; hdc
0x180027ee6  call    GetPolyFillMode
0x180027eeb  mov     edx, eax; mode
0x180027eed  mov     rcx, rdi; hdc
0x180027ef0  call    cs:__imp_SetPolyFillMode
0x180027ef7  nop     dword ptr [rax+rax+00h]
0x180027efc  mov     rcx, rdi; hdc
0x180027eff  call    GetROP2
0x180027f04  cmp     eax, 0Dh
0x180027f07  jz      short loc_180027F1B
0x180027f09  mov     rcx, rdi; hdc
0x180027f0c  call    GetROP2
0x180027f11  mov     edx, eax; rop2
0x180027f13  mov     rcx, rdi; hdc
0x180027f16  call    SetROP2
0x180027f1b  mov     rcx, rdi; hdc
0x180027f1e  call    GetStretchBltMode
0x180027f23  cmp     eax, 1
0x180027f26  jz      short loc_180027F41
0x180027f28  mov     rcx, rdi; hdc
0x180027f2b  call    GetStretchBltMode
0x180027f30  mov     edx, eax; mode
0x180027f32  mov     rcx, rdi; hdc
0x180027f35  call    cs:__imp_SetStretchBltMode
0x180027f3c  nop     dword ptr [rax+rax+00h]
0x180027f41  mov     rcx, rdi; hdc
0x180027f44  call    GetTextAlign
0x180027f49  test    eax, eax
0x180027f4b  jz      short loc_180027F66
0x180027f4d  mov     rcx, rdi; hdc
0x180027f50  call    GetTextAlign
0x180027f55  mov     edx, eax; align
0x180027f57  mov     rcx, rdi; hdc
0x180027f5a  call    cs:__imp_SetTextAlign
0x180027f61  nop     dword ptr [rax+rax+00h]
0x180027f66  xor     r8d, r8d
0x180027f69  mov     rcx, rdi
0x180027f6c  lea     edx, [r8+2]
0x180027f70  call    GetDCDWord
0x180027f75  test    eax, eax
0x180027f77  jnz     short loc_180027F8B
0x180027f79  xor     r8d, r8d
0x180027f7c  lea     edx, [rax+3]
0x180027f7f  mov     rcx, rdi
0x180027f82  call    GetDCDWord
0x180027f87  test    eax, eax
0x180027f89  jz      short loc_180027FB8
0x180027f8b  xor     r8d, r8d
0x180027f8e  mov     rcx, rdi
0x180027f91  lea     edx, [r8+3]
0x180027f95  call    GetDCDWord
0x180027f9a  xor     r8d, r8d
0x180027f9d  mov     rcx, rdi
0x180027fa0  mov     ebx, eax
0x180027fa2  lea     edx, [r8+2]
0x180027fa6  call    GetDCDWord
0x180027fab  mov     r8d, ebx; count
0x180027fae  mov     edx, eax; extra
0x180027fb0  mov     rcx, rdi; hdc
0x180027fb3  call    SetTextJustification
0x180027fb8  mov     rcx, rdi; hdc
0x180027fbb  call    GetMapMode
0x180027fc0  cmp     eax, 1
0x180027fc3  jz      loc_18002808A
0x180027fc9  mov     rcx, rdi; hdc
0x180027fcc  call    GetMapMode
0x180027fd1  lea     rdx, [rbp+size]; lpsize
0x180027fd5  mov     qword ptr [rbp+point.x], 0
0x180027fdd  mov     rcx, rdi; hdc
0x180027fe0  mov     qword ptr [rbp+var_8.x], 0
0x180027fe8  mov     ebx, eax
0x180027fea  mov     qword ptr [rbp+arg_10.cx], 0
0x180027ff2  mov     qword ptr [rbp+size.cx], 0
0x180027ffa  call    GetViewportExtEx
0x180027fff  lea     rdx, [rbp+arg_10]; lpsize
0x180028003  mov     rcx, rdi; hdc
0x180028006  call    GetWindowExtEx
0x18002800b  lea     rdx, [rbp+point]; lppoint
0x18002800f  mov     rcx, rdi; hdc
0x180028012  call    GetWindowOrgEx
0x180028017  lea     rdx, [rbp+var_8]; lppoint
0x18002801b  mov     rcx, rdi; hdc
0x18002801e  call    GetViewportOrgEx
0x180028023  mov     edx, 1; iMode
0x180028028  mov     rcx, rdi; hdc
0x18002802b  call    SetMapMode
0x180028030  mov     edx, ebx; iMode
0x180028032  mov     rcx, rdi; hdc
0x180028035  call    SetMapMode
0x18002803a  lea     eax, [rbx-7]
0x18002803d  cmp     eax, 1
0x180028040  ja      short loc_180028066
0x180028042  mov     r8d, [rbp+arg_10.cy]; y
0x180028046  xor     r9d, r9d; lpsz
0x180028049  mov     edx, [rbp+arg_10.cx]; x
0x18002804c  mov     rcx, rdi; hdc
0x18002804f  call    SetWindowExtEx
0x180028054  mov     r8d, [rbp+size.cy]; y
0x180028058  xor     r9d, r9d; lpsz
0x18002805b  mov     edx, [rbp+size.cx]; x
0x18002805e  mov     rcx, rdi; hdc
0x180028061  call    SetViewportExtEx
0x180028066  mov     r8d, [rbp+point.y]; y
0x18002806a  xor     r9d, r9d; lppt
0x18002806d  mov     edx, [rbp+point.x]; x
0x180028070  mov     rcx, rdi; hdc
0x180028073  call    SetWindowOrgEx
0x180028078  mov     r8d, [rbp+var_8.y]; y
0x18002807c  xor     r9d, r9d; lppt
0x18002807f  mov     edx, [rbp+var_8.x]; x
0x180028082  mov     rcx, rdi; hdc
0x180028085  call    SetViewportOrgEx
0x18002808a  lea     rdx, [rbp+pt]; lppt
0x18002808e  mov     rcx, rdi; hdc
0x180028091  call    GetCurrentPositionEx
0x180028096  test    eax, eax
0x180028098  jz      short loc_1800280B3
0x18002809a  mov     r8d, [rbp+pt.y]; y
0x18002809e  xor     r9d, r9d; lppt
0x1800280a1  mov     edx, [rbp+pt.x]; x
0x1800280a4  mov     rcx, rdi; hdc
0x1800280a7  call    cs:__imp_MoveToEx
0x1800280ae  nop     dword ptr [rax+rax+00h]
0x1800280b3  lea     rdx, [rbp+pt]; lppt
0x1800280b7  mov     rcx, rdi; hdc
0x1800280ba  call    GetBrushOrgEx
0x1800280bf  test    eax, eax
0x1800280c1  jz      short loc_1800280D6
0x1800280c3  mov     r8d, [rbp+pt.y]; y
0x1800280c7  lea     r9, [rbp+pt]; lppt
0x1800280cb  mov     edx, [rbp+pt.x]; x
0x1800280ce  mov     rcx, rdi; hdc
0x1800280d1  call    SetBrushOrgEx
0x1800280d6  mov     edx, 3; mode
0x1800280db  mov     rcx, rdi; hdc
0x1800280de  call    cs:__imp_SetICMMode
0x1800280e5  nop     dword ptr [rax+rax+00h]
0x1800280ea  test    eax, eax
0x1800280ec  jz      short loc_180028113
0x1800280ee  mov     edx, 3; mode
0x1800280f3  mov     rcx, rdi; hdc
0x1800280f6  call    cs:__imp_SetICMMode
0x1800280fd  nop     dword ptr [rax+rax+00h]
0x180028102  mov     edx, eax; mode
0x180028104  mov     rcx, rdi; hdc
0x180028107  call    cs:__imp_SetICMMode
0x18002810e  nop     dword ptr [rax+rax+00h]
0x180028113  mov     rcx, rdi; hdc
0x180028116  call    GetColorSpace
0x18002811b  test    rax, rax
0x18002811e  jz      short loc_180028133
0x180028120  mov     rcx, rdi; hdc
0x180028123  call    GetColorSpace
0x180028128  mov     rdx, rax; hcs
0x18002812b  mov     rcx, rdi; hdc
0x18002812e  call    SetColorSpace
0x180028133  call    cs:__imp_NtGdiAnyLinkedFonts
0x18002813a  nop     dword ptr [rax+rax+00h]
0x18002813f  test    eax, eax
0x180028141  jnz     short loc_180028150
0x180028143  xor     r8d, r8d
0x180028146  xor     edx, edx
0x180028148  mov     rcx, rdi
0x18002814b  call    MF_SetLinkedUFIs
0x180028150  mov     eax, 1
0x180028155  jmp     short loc_180028159
0x180028157  xor     eax, eax
0x180028159  add     rsp, 30h
0x18002815d  pop     rdi
0x18002815e  pop     rbx
0x18002815f  pop     rbp
0x180028160  retn
```
