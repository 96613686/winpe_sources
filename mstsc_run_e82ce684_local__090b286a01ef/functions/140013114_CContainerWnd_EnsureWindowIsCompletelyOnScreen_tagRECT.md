# CContainerWnd::EnsureWindowIsCompletelyOnScreen(tagRECT *)

- ea: `0x140013114`
- end: `0x1400132f5`
- name: `?EnsureWindowIsCompletelyOnScreen@CContainerWnd@@AEAAXPEAUtagRECT@@@Z`
- size: `481`
- prototype: `void(CContainerWnd *__hidden this, struct tagRECT *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400123e4`
- `0x140013d38`

## callees

- `0x140013114`
- `0x14001e610`
- `0x14001e6d4`
- `0x14001e85c`
- `0x140113390`

## import_xrefs

- `USER32!EqualRect` at `0x1400131ba`
- `USER32!EqualRect` at `0x1400131ba`
- `USER32!CopyRect` at `0x1400132a4`
- `USER32!CopyRect` at `0x1400132a4`
- `USER32!IntersectRect` at `0x140013297`
- `USER32!IntersectRect` at `0x140013297`
- `USER32!OffsetRect` at `0x1400131e1`
- `USER32!OffsetRect` at `0x140013286`
- `USER32!OffsetRect` at `0x1400132b7`
- `USER32!OffsetRect` at `0x1400131e1`
- `USER32!OffsetRect` at `0x140013286`
- `USER32!OffsetRect` at `0x1400132b7`
- `GDI32!EqualRgn` at `0x140013231`
- `GDI32!EqualRgn` at `0x140013231`
- `GDI32!CombineRgn` at `0x140013225`
- `GDI32!CombineRgn` at `0x140013225`
- `GDI32!SetRectRgn` at `0x14001320f`
- `GDI32!SetRectRgn` at `0x14001320f`
- `GDI32!DeleteObject` at `0x1400132c0`
- `GDI32!DeleteObject` at `0x1400132c9`
- `GDI32!DeleteObject` at `0x1400132d3`
- `GDI32!DeleteObject` at `0x1400132c0`
- `GDI32!DeleteObject` at `0x1400132c9`
- `GDI32!DeleteObject` at `0x1400132d3`
- `GDI32!CreateRectRgn` at `0x140013182`
- `GDI32!CreateRectRgn` at `0x140013196`
- `GDI32!CreateRectRgn` at `0x1400131a9`
- `GDI32!CreateRectRgn` at `0x140013182`
- `GDI32!CreateRectRgn` at `0x140013196`
- `GDI32!CreateRectRgn` at `0x1400131a9`

## pseudocode

```c
void __fastcall CContainerWnd::EnsureWindowIsCompletelyOnScreen(CContainerWnd *this, struct tagRECT *a2)
{
  HMONITOR v3; // rax
  HRGN v4; // rdi
  HRGN v5; // rbx
  int v6; // esi
  int v7; // r14d
  HDC v8; // rcx
  int v9; // ecx
  int v10; // r9d
  int v11; // ecx
  int v12; // edx
  LPARAM RectRgn; // [rsp+30h] [rbp-29h] BYREF
  tagMONITORINFO v14; // [rsp+38h] [rbp-21h] BYREF
  struct tagRECT rcDst; // [rsp+60h] [rbp+7h] BYREF

  memset(&v14, 0, sizeof(v14));
  v3 = xMonitorFromRect(a2, 2u);
  v14.cbSize = 40;
  if ( xGetMonitorInfo(v3, &v14) )
  {
    rcDst = 0;
    RectRgn = (LPARAM)CreateRectRgn(0, 0, 0, 0);
    v4 = CreateRectRgn(0, 0, 0, 0);
    v5 = CreateRectRgn(0, 0, 0, 0);
    if ( EqualRect(&v14.rcMonitor, &v14.rcWork) )
    {
      v7 = 0;
      v6 = 0;
    }
    else
    {
      v6 = v14.rcWork.left - v14.rcMonitor.left;
      v7 = v14.rcWork.top - v14.rcMonitor.top;
    }
    OffsetRect(a2, v6, v7);
    xEnumDisplayMonitors(v8, 0, GetDesktopRegionEnumProc, (LPARAM)&RectRgn);
    SetRectRgn(v5, a2->left, a2->top, a2->right, a2->bottom);
    CombineRgn(v4, (HRGN)RectRgn, v5, 1);
    if ( !EqualRgn(v4, v5) )
    {
      v9 = v14.rcWork.top - a2->top;
      if ( a2->top >= v14.rcWork.top )
        v9 = 0;
      v10 = v14.rcWork.bottom - a2->bottom;
      if ( a2->bottom <= v14.rcWork.bottom )
        v10 = v9;
      v11 = v14.rcWork.left - a2->left;
      if ( a2->left >= v14.rcWork.left )
        v11 = 0;
      v12 = v14.rcWork.right - a2->right;
      if ( a2->right <= v14.rcWork.right )
        v12 = v11;
      OffsetRect(a2, v12, v10);
      IntersectRect(&rcDst, a2, &v14.rcWork);
      CopyRect(a2, &rcDst);
    }
    OffsetRect(a2, -v6, -v7);
    DeleteObject(v5);
    DeleteObject(v4);
    DeleteObject((HGDIOBJ)RectRgn);
  }
}

```

## disassembly

```asm
0x140013114  push    rbp
0x140013116  push    rbx
0x140013117  push    rsi
0x140013118  push    rdi
0x140013119  push    r14
0x14001311b  push    r15
0x14001311d  lea     rbp, [rsp-2Fh]
0x140013122  sub     rsp, 88h
0x140013129  mov     rax, cs:__security_cookie
0x140013130  xor     rax, rsp
0x140013133  mov     [rbp+57h+var_40], rax
0x140013137  xor     eax, eax
0x140013139  mov     r15, rdx
0x14001313c  xorps   xmm0, xmm0
0x14001313f  mov     qword ptr [rbp+57h+var_78.rcWork.bottom], rax
0x140013143  mov     rcx, r15; LPCRECT
0x140013146  movups  xmmword ptr [rbp+57h+var_78.cbSize], xmm0
0x14001314a  lea     edx, [rax+2]; DWORD
0x14001314d  movups  xmmword ptr [rbp+57h+var_78.rcMonitor.bottom], xmm0
0x140013151  call    xMonitorFromRect
0x140013156  lea     rdx, [rbp+57h+var_78]; LPMONITORINFO
0x14001315a  mov     [rbp+57h+var_78.cbSize], 28h ; '('
0x140013161  mov     rcx, rax; HMONITOR
0x140013164  call    xGetMonitorInfo
0x140013169  test    eax, eax
0x14001316b  jz      loc_1400132D9
0x140013171  xorps   xmm0, xmm0
0x140013174  xor     r9d, r9d; y2
0x140013177  xor     r8d, r8d; x2
0x14001317a  xor     edx, edx; y1
0x14001317c  xor     ecx, ecx; x1
0x14001317e  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x140013182  call    cs:__imp_CreateRectRgn
0x140013188  xor     r9d, r9d; y2
0x14001318b  xor     r8d, r8d; x2
0x14001318e  xor     edx, edx; y1
0x140013190  mov     [rbp+57h+var_80], rax
0x140013194  xor     ecx, ecx; x1
0x140013196  call    cs:__imp_CreateRectRgn
0x14001319c  xor     r9d, r9d; y2
0x14001319f  xor     r8d, r8d; x2
0x1400131a2  xor     edx, edx; y1
0x1400131a4  xor     ecx, ecx; x1
0x1400131a6  mov     rdi, rax
0x1400131a9  call    cs:__imp_CreateRectRgn
0x1400131af  lea     rdx, [rbp+57h+var_78.rcWork]; lprc2
0x1400131b3  mov     rbx, rax
0x1400131b6  lea     rcx, [rbp+57h+var_78.rcMonitor]; lprc1
0x1400131ba  call    cs:__imp_EqualRect
0x1400131c0  test    eax, eax
0x1400131c2  jnz     short loc_1400131D4
0x1400131c4  mov     esi, [rbp+57h+var_78.rcWork.left]
0x1400131c7  sub     esi, [rbp+57h+var_78.rcMonitor.left]
0x1400131ca  mov     r14d, [rbp+57h+var_78.rcWork.top]
0x1400131ce  sub     r14d, [rbp+57h+var_78.rcMonitor.top]
0x1400131d2  jmp     short loc_1400131D9
0x1400131d4  xor     r14d, r14d
0x1400131d7  xor     esi, esi
0x1400131d9  mov     r8d, r14d; dy
0x1400131dc  mov     edx, esi; dx
0x1400131de  mov     rcx, r15; lprc
0x1400131e1  call    cs:__imp_OffsetRect
0x1400131e7  lea     r9, [rbp+57h+var_80]; LPARAM
0x1400131eb  xor     edx, edx; LPCRECT
0x1400131ed  lea     r8, ?GetDesktopRegionEnumProc@@YAHPEAUHMONITOR__@@PEAUHDC__@@PEAUtagRECT@@_J@Z; MONITORENUMPROC
0x1400131f4  call    xEnumDisplayMonitors
0x1400131f9  mov     eax, [r15+0Ch]
0x1400131fd  mov     rcx, rbx; hrgn
0x140013200  mov     r9d, [r15+8]; right
0x140013204  mov     r8d, [r15+4]; top
0x140013208  mov     edx, [r15]; left
0x14001320b  mov     [rsp+0B0h+bottom], eax; bottom
0x14001320f  call    cs:__imp_SetRectRgn
0x140013215  mov     rdx, [rbp+57h+var_80]; hrgnSrc1
0x140013219  mov     r9d, 1; iMode
0x14001321f  mov     r8, rbx; hrgnSrc2
0x140013222  mov     rcx, rdi; hrgnDst
0x140013225  call    cs:__imp_CombineRgn
0x14001322b  mov     rdx, rbx; hrgn2
0x14001322e  mov     rcx, rdi; hrgn1
0x140013231  call    cs:__imp_EqualRgn
0x140013237  test    eax, eax
0x140013239  jnz     short loc_1400132AA
0x14001323b  mov     edx, [rbp+57h+var_78.rcWork.top]
0x14001323e  mov     ecx, edx
0x140013240  sub     ecx, [r15+4]
0x140013244  cmp     [r15+4], edx
0x140013248  mov     r8d, [rbp+57h+var_78.rcWork.bottom]
0x14001324c  mov     r9d, r8d
0x14001324f  mov     r10d, [rbp+57h+var_78.rcWork.left]
0x140013253  cmovge  ecx, eax
0x140013256  sub     r9d, [r15+0Ch]
0x14001325a  cmp     [r15+0Ch], r8d
0x14001325e  mov     r11d, [rbp+57h+var_78.rcWork.right]
0x140013262  mov     edx, r11d
0x140013265  cmovle  r9d, ecx
0x140013269  mov     ecx, r10d
0x14001326c  sub     ecx, [r15]
0x14001326f  mov     r8d, r9d; dy
0x140013272  cmp     [r15], r10d
0x140013275  cmovge  ecx, eax
0x140013278  sub     edx, [r15+8]
0x14001327c  cmp     [r15+8], r11d
0x140013280  cmovle  edx, ecx; dx
0x140013283  mov     rcx, r15; lprc
0x140013286  call    cs:__imp_OffsetRect
0x14001328c  lea     r8, [rbp+57h+var_78.rcWork]; lprcSrc2
0x140013290  mov     rdx, r15; lprcSrc1
0x140013293  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x140013297  call    cs:__imp_IntersectRect
0x14001329d  lea     rdx, [rbp+57h+rcDst]; lprcSrc
0x1400132a1  mov     rcx, r15; lprcDst
0x1400132a4  call    cs:__imp_CopyRect
0x1400132aa  neg     r14d
0x1400132ad  neg     esi
0x1400132af  mov     r8d, r14d; dy
0x1400132b2  mov     edx, esi; dx
0x1400132b4  mov     rcx, r15; lprc
0x1400132b7  call    cs:__imp_OffsetRect
0x1400132bd  mov     rcx, rbx; ho
0x1400132c0  call    cs:__imp_DeleteObject
0x1400132c6  mov     rcx, rdi; ho
0x1400132c9  call    cs:__imp_DeleteObject
0x1400132cf  mov     rcx, [rbp+57h+var_80]; ho
0x1400132d3  call    cs:__imp_DeleteObject
0x1400132d9  mov     rcx, [rbp+57h+var_40]
0x1400132dd  xor     rcx, rsp; StackCookie
0x1400132e0  call    __security_check_cookie
0x1400132e5  add     rsp, 88h
0x1400132ec  pop     r15
0x1400132ee  pop     r14
0x1400132f0  pop     rdi
0x1400132f1  pop     rsi
0x1400132f2  pop     rbx
0x1400132f3  pop     rbp
0x1400132f4  retn
```
