# CPersistBrowserFrame::_EnsureWindowIsCompletelyOnScreen(tagRECT *)

- ea: `0x1802370fc`
- end: `0x1802372e8`
- name: `?_EnsureWindowIsCompletelyOnScreen@CPersistBrowserFrame@@CAXPEAUtagRECT@@@Z`
- size: `492`
- prototype: `void __fastcall(LPRECT lprc)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180229ed4`
- `0x18023bc88`

## callees

- `0x1802294b0`
- `0x1802370fc`
- `0x18054e310`

## import_xrefs

- `GDI32!CombineRgn` at `0x180237212`
- `GDI32!CombineRgn` at `0x180237212`
- `GDI32!SetRectRgn` at `0x1802371fc`
- `GDI32!SetRectRgn` at `0x1802371fc`
- `GDI32!EqualRgn` at `0x18023721e`
- `GDI32!EqualRgn` at `0x18023721e`
- `GDI32!CreateRectRgn` at `0x180237199`
- `GDI32!CreateRectRgn` at `0x1802371ad`
- `GDI32!CreateRectRgn` at `0x1802371c4`
- `GDI32!CreateRectRgn` at `0x180237199`
- `GDI32!CreateRectRgn` at `0x1802371ad`
- `GDI32!CreateRectRgn` at `0x1802371c4`
- `USER32!GetMonitorInfoW` at `0x18023714c`
- `USER32!GetMonitorInfoW` at `0x18023714c`
- `USER32!MonitorFromRect` at `0x180237127`
- `USER32!MonitorFromRect` at `0x180237127`
- `USER32!OffsetRect` at `0x180237189`
- `USER32!OffsetRect` at `0x18023727a`
- `USER32!OffsetRect` at `0x1802372ab`
- `USER32!OffsetRect` at `0x180237189`
- `USER32!OffsetRect` at `0x18023727a`
- `USER32!OffsetRect` at `0x1802372ab`
- `USER32!IntersectRect` at `0x18023728b`
- `USER32!IntersectRect` at `0x18023728b`
- `USER32!EqualRect` at `0x180237162`
- `USER32!EqualRect` at `0x180237162`
- `USER32!CopyRect` at `0x180237298`
- `USER32!CopyRect` at `0x180237298`
- `USER32!EnumDisplayMonitors` at `0x1802371e0`
- `USER32!EnumDisplayMonitors` at `0x1802371e0`

## pseudocode

```c
void __fastcall CPersistBrowserFrame::_EnsureWindowIsCompletelyOnScreen(LPRECT lprc)
{
  HMONITOR v2; // rax
  int v3; // esi
  int v4; // r14d
  HRGN v5; // rdi
  HRGN v6; // rbx
  int v7; // ecx
  int v8; // r9d
  bool v9; // cc
  int v10; // ecx
  int v11; // edx
  LPARAM dwData; // [rsp+30h] [rbp-39h] BYREF
  HRGN v13; // [rsp+38h] [rbp-31h] BYREF
  HRGN RectRgn; // [rsp+40h] [rbp-29h] BYREF
  struct tagMONITORINFO mi; // [rsp+48h] [rbp-21h] BYREF
  struct tagRECT rcDst; // [rsp+70h] [rbp+7h] BYREF

  v2 = MonitorFromRect(lprc, 2u);
  memset(&mi, 0, sizeof(mi));
  mi.cbSize = 40;
  if ( GetMonitorInfoW(v2, &mi) )
  {
    if ( EqualRect(&mi.rcMonitor, &mi.rcWork) )
    {
      v3 = 0;
      v4 = 0;
    }
    else
    {
      v3 = mi.rcWork.left - mi.rcMonitor.left;
      v4 = mi.rcWork.top - mi.rcMonitor.top;
    }
    OffsetRect(lprc, v3, v4);
    dwData = (LPARAM)CreateRectRgn(0, 0, 0, 0);
    RectRgn = CreateRectRgn(0, 0, 0, 0);
    v5 = RectRgn;
    v13 = CreateRectRgn(0, 0, 0, 0);
    v6 = v13;
    EnumDisplayMonitors(0, 0, CPersistBrowserFrame::_GetDesktopRegionEnumProc, (LPARAM)&dwData);
    SetRectRgn(v6, lprc->left, lprc->top, lprc->right, lprc->bottom);
    CombineRgn(v5, (HRGN)dwData, v6, 1);
    if ( !EqualRgn(v5, v6) )
    {
      v7 = mi.rcWork.top - lprc->top;
      if ( lprc->top >= mi.rcWork.top )
        v7 = 0;
      v8 = mi.rcWork.bottom - lprc->bottom;
      v9 = lprc->bottom <= mi.rcWork.bottom;
      rcDst = 0;
      if ( v9 )
        v8 = v7;
      v10 = mi.rcWork.left - lprc->left;
      if ( lprc->left >= mi.rcWork.left )
        v10 = 0;
      v11 = mi.rcWork.right - lprc->right;
      if ( lprc->right <= mi.rcWork.right )
        v11 = v10;
      OffsetRect(lprc, v11, v8);
      IntersectRect(&rcDst, lprc, &mi.rcWork);
      CopyRect(lprc, &rcDst);
    }
    OffsetRect(lprc, -v3, -v4);
    CRegion::~CRegion((CRegion *)&v13);
    CRegion::~CRegion((CRegion *)&RectRgn);
    CRegion::~CRegion((CRegion *)&dwData);
  }
}

```

## disassembly

```asm
0x1802370fc  push    rbp
0x1802370fe  push    rbx
0x1802370ff  push    rsi
0x180237100  push    rdi
0x180237101  push    r14
0x180237103  push    r15
0x180237105  lea     rbp, [rsp-2Fh]
0x18023710a  sub     rsp, 98h
0x180237111  mov     rax, cs:__security_cookie
0x180237118  xor     rax, rsp
0x18023711b  mov     [rbp+57h+var_40], rax
0x18023711f  mov     edx, 2; dwFlags
0x180237124  mov     r15, rcx
0x180237127  call    cs:__imp_MonitorFromRect
0x18023712d  xor     ecx, ecx
0x18023712f  lea     rdx, [rbp+57h+mi]; lpmi
0x180237133  xorps   xmm0, xmm0
0x180237136  mov     qword ptr [rbp+57h+mi.rcWork.bottom], rcx
0x18023713a  movups  xmmword ptr [rbp+57h+mi.cbSize], xmm0
0x18023713e  mov     rcx, rax; hMonitor
0x180237141  mov     [rbp+57h+mi.cbSize], 28h ; '('
0x180237148  movups  xmmword ptr [rbp+57h+mi.rcMonitor.bottom], xmm0
0x18023714c  call    cs:__imp_GetMonitorInfoW
0x180237152  test    eax, eax
0x180237154  jz      loc_1802372CC
0x18023715a  lea     rdx, [rbp+57h+mi.rcWork]; lprc2
0x18023715e  lea     rcx, [rbp+57h+mi.rcMonitor]; lprc1
0x180237162  call    cs:__imp_EqualRect
0x180237168  test    eax, eax
0x18023716a  jnz     short loc_18023717C
0x18023716c  mov     esi, [rbp+57h+mi.rcWork.left]
0x18023716f  sub     esi, [rbp+57h+mi.rcMonitor.left]
0x180237172  mov     r14d, [rbp+57h+mi.rcWork.top]
0x180237176  sub     r14d, [rbp+57h+mi.rcMonitor.top]
0x18023717a  jmp     short loc_180237181
0x18023717c  xor     esi, esi
0x18023717e  xor     r14d, r14d
0x180237181  mov     r8d, r14d; dy
0x180237184  mov     edx, esi; dx
0x180237186  mov     rcx, r15; lprc
0x180237189  call    cs:__imp_OffsetRect
0x18023718f  xor     r9d, r9d; y2
0x180237192  xor     r8d, r8d; x2
0x180237195  xor     edx, edx; y1
0x180237197  xor     ecx, ecx; x1
0x180237199  call    cs:__imp_CreateRectRgn
0x18023719f  xor     r9d, r9d; y2
0x1802371a2  xor     r8d, r8d; x2
0x1802371a5  xor     edx, edx; y1
0x1802371a7  mov     [rbp+57h+dwData], rax
0x1802371ab  xor     ecx, ecx; x1
0x1802371ad  call    cs:__imp_CreateRectRgn
0x1802371b3  xor     r9d, r9d; y2
0x1802371b6  xor     r8d, r8d; x2
0x1802371b9  xor     edx, edx; y1
0x1802371bb  mov     [rbp+57h+var_80], rax
0x1802371bf  xor     ecx, ecx; x1
0x1802371c1  mov     rdi, rax
0x1802371c4  call    cs:__imp_CreateRectRgn
0x1802371ca  lea     r9, [rbp+57h+dwData]; dwData
0x1802371ce  xor     edx, edx; lprcClip
0x1802371d0  lea     r8, ?_GetDesktopRegionEnumProc@CPersistBrowserFrame@@CAHPEAUHMONITOR__@@PEAUHDC__@@PEAUtagRECT@@_J@Z; lpfnEnum
0x1802371d7  mov     [rbp+57h+var_88], rax
0x1802371db  xor     ecx, ecx; hdc
0x1802371dd  mov     rbx, rax
0x1802371e0  call    cs:__imp_EnumDisplayMonitors
0x1802371e6  mov     eax, [r15+0Ch]
0x1802371ea  mov     rcx, rbx; hrgn
0x1802371ed  mov     r9d, [r15+8]; right
0x1802371f1  mov     r8d, [r15+4]; top
0x1802371f5  mov     edx, [r15]; left
0x1802371f8  mov     [rsp+0C0h+bottom], eax; bottom
0x1802371fc  call    cs:__imp_SetRectRgn
0x180237202  mov     rdx, [rbp+57h+dwData]; hrgnSrc1
0x180237206  mov     r9d, 1; iMode
0x18023720c  mov     r8, rbx; hrgnSrc2
0x18023720f  mov     rcx, rdi; hrgnDst
0x180237212  call    cs:__imp_CombineRgn
0x180237218  mov     rdx, rbx; hrgn2
0x18023721b  mov     rcx, rdi; hrgn1
0x18023721e  call    cs:__imp_EqualRgn
0x180237224  test    eax, eax
0x180237226  jnz     short loc_18023729E
0x180237228  mov     edx, [rbp+57h+mi.rcWork.top]
0x18023722b  xorps   xmm0, xmm0
0x18023722e  mov     r8d, [rbp+57h+mi.rcWork.bottom]
0x180237232  mov     ecx, edx
0x180237234  sub     ecx, [r15+4]
0x180237238  mov     r9d, r8d
0x18023723b  cmp     [r15+4], edx
0x18023723f  mov     r10d, [rbp+57h+mi.rcWork.left]
0x180237243  mov     r11d, [rbp+57h+mi.rcWork.right]
0x180237247  cmovge  ecx, eax
0x18023724a  sub     r9d, [r15+0Ch]
0x18023724e  mov     edx, r11d
0x180237251  cmp     [r15+0Ch], r8d
0x180237255  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x180237259  cmovle  r9d, ecx
0x18023725d  mov     ecx, r10d
0x180237260  sub     ecx, [r15]
0x180237263  mov     r8d, r9d; dy
0x180237266  cmp     [r15], r10d
0x180237269  cmovge  ecx, eax
0x18023726c  sub     edx, [r15+8]
0x180237270  cmp     [r15+8], r11d
0x180237274  cmovle  edx, ecx; dx
0x180237277  mov     rcx, r15; lprc
0x18023727a  call    cs:__imp_OffsetRect
0x180237280  lea     r8, [rbp+57h+mi.rcWork]; lprcSrc2
0x180237284  mov     rdx, r15; lprcSrc1
0x180237287  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x18023728b  call    cs:__imp_IntersectRect
0x180237291  lea     rdx, [rbp+57h+rcDst]; lprcSrc
0x180237295  mov     rcx, r15; lprcDst
0x180237298  call    cs:__imp_CopyRect
0x18023729e  neg     r14d
0x1802372a1  neg     esi
0x1802372a3  mov     r8d, r14d; dy
0x1802372a6  mov     edx, esi; dx
0x1802372a8  mov     rcx, r15; lprc
0x1802372ab  call    cs:__imp_OffsetRect
0x1802372b1  lea     rcx, [rbp+57h+var_88]; this
0x1802372b5  call    ??1CRegion@@QEAA@XZ; CRegion::~CRegion(void)
0x1802372ba  lea     rcx, [rbp+57h+var_80]; this
0x1802372be  call    ??1CRegion@@QEAA@XZ; CRegion::~CRegion(void)
0x1802372c3  lea     rcx, [rbp+57h+dwData]; this
0x1802372c7  call    ??1CRegion@@QEAA@XZ; CRegion::~CRegion(void)
0x1802372cc  mov     rcx, [rbp+57h+var_40]
0x1802372d0  xor     rcx, rsp; StackCookie
0x1802372d3  call    __security_check_cookie
0x1802372d8  add     rsp, 98h
0x1802372df  pop     r15
0x1802372e1  pop     r14
0x1802372e3  pop     rdi
0x1802372e4  pop     rsi
0x1802372e5  pop     rbx
0x1802372e6  pop     rbp
0x1802372e7  retn
```
