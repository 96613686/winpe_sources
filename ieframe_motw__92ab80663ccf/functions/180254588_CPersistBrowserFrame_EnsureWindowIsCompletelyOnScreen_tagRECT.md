# CPersistBrowserFrame::_EnsureWindowIsCompletelyOnScreen(tagRECT *)

- ea: `0x180254588`
- end: `0x1802547d3`
- name: `?_EnsureWindowIsCompletelyOnScreen@CPersistBrowserFrame@@CAXPEAUtagRECT@@@Z`
- size: `587`
- prototype: `void __fastcall(LPRECT lprc)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1802468c4`
- `0x18025967c`

## callees

- `0x180245e54`
- `0x180254588`
- `0x180591f80`

## import_xrefs

- `GDI32!CombineRgn` at `0x1802546d4`
- `GDI32!CombineRgn` at `0x1802546d4`
- `GDI32!SetRectRgn` at `0x1802546b8`
- `GDI32!SetRectRgn` at `0x1802546b8`
- `GDI32!EqualRgn` at `0x1802546e6`
- `GDI32!EqualRgn` at `0x1802546e6`
- `GDI32!CreateRectRgn` at `0x18025463d`
- `GDI32!CreateRectRgn` at `0x180254657`
- `GDI32!CreateRectRgn` at `0x180254674`
- `GDI32!CreateRectRgn` at `0x18025463d`
- `GDI32!CreateRectRgn` at `0x180254657`
- `GDI32!CreateRectRgn` at `0x180254674`
- `USER32!GetMonitorInfoW` at `0x1802545de`
- `USER32!GetMonitorInfoW` at `0x1802545de`
- `USER32!MonitorFromRect` at `0x1802545b3`
- `USER32!MonitorFromRect` at `0x1802545b3`
- `USER32!OffsetRect` at `0x180254627`
- `USER32!OffsetRect` at `0x18025474c`
- `USER32!OffsetRect` at `0x18025478f`
- `USER32!OffsetRect` at `0x180254627`
- `USER32!OffsetRect` at `0x18025474c`
- `USER32!OffsetRect` at `0x18025478f`
- `USER32!IntersectRect` at `0x180254763`
- `USER32!IntersectRect` at `0x180254763`
- `USER32!EqualRect` at `0x1802545fa`
- `USER32!EqualRect` at `0x1802545fa`
- `USER32!CopyRect` at `0x180254776`
- `USER32!CopyRect` at `0x180254776`
- `USER32!EnumDisplayMonitors` at `0x180254696`
- `USER32!EnumDisplayMonitors` at `0x180254696`

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
0x180254588  push    rbp
0x18025458a  push    rbx
0x18025458b  push    rsi
0x18025458c  push    rdi
0x18025458d  push    r14
0x18025458f  push    r15
0x180254591  lea     rbp, [rsp-2Fh]
0x180254596  sub     rsp, 98h
0x18025459d  mov     rax, cs:__security_cookie
0x1802545a4  xor     rax, rsp
0x1802545a7  mov     [rbp+57h+var_40], rax
0x1802545ab  mov     edx, 2; dwFlags
0x1802545b0  mov     r15, rcx
0x1802545b3  call    cs:__imp_MonitorFromRect
0x1802545ba  nop     dword ptr [rax+rax+00h]
0x1802545bf  xor     ecx, ecx
0x1802545c1  lea     rdx, [rbp+57h+mi]; lpmi
0x1802545c5  xorps   xmm0, xmm0
0x1802545c8  mov     qword ptr [rbp+57h+mi.rcWork.bottom], rcx
0x1802545cc  movups  xmmword ptr [rbp+57h+mi.cbSize], xmm0
0x1802545d0  mov     rcx, rax; hMonitor
0x1802545d3  mov     [rbp+57h+mi.cbSize], 28h ; '('
0x1802545da  movups  xmmword ptr [rbp+57h+mi.rcMonitor.bottom], xmm0
0x1802545de  call    cs:__imp_GetMonitorInfoW
0x1802545e5  nop     dword ptr [rax+rax+00h]
0x1802545ea  test    eax, eax
0x1802545ec  jz      loc_1802547B6
0x1802545f2  lea     rdx, [rbp+57h+mi.rcWork]; lprc2
0x1802545f6  lea     rcx, [rbp+57h+mi.rcMonitor]; lprc1
0x1802545fa  call    cs:__imp_EqualRect
0x180254601  nop     dword ptr [rax+rax+00h]
0x180254606  test    eax, eax
0x180254608  jnz     short loc_18025461A
0x18025460a  mov     esi, [rbp+57h+mi.rcWork.left]
0x18025460d  sub     esi, [rbp+57h+mi.rcMonitor.left]
0x180254610  mov     r14d, [rbp+57h+mi.rcWork.top]
0x180254614  sub     r14d, [rbp+57h+mi.rcMonitor.top]
0x180254618  jmp     short loc_18025461F
0x18025461a  xor     esi, esi
0x18025461c  xor     r14d, r14d
0x18025461f  mov     r8d, r14d; dy
0x180254622  mov     edx, esi; dx
0x180254624  mov     rcx, r15; lprc
0x180254627  call    cs:__imp_OffsetRect
0x18025462e  nop     dword ptr [rax+rax+00h]
0x180254633  xor     r9d, r9d; y2
0x180254636  xor     r8d, r8d; x2
0x180254639  xor     edx, edx; y1
0x18025463b  xor     ecx, ecx; x1
0x18025463d  call    cs:__imp_CreateRectRgn
0x180254644  nop     dword ptr [rax+rax+00h]
0x180254649  xor     r9d, r9d; y2
0x18025464c  xor     r8d, r8d; x2
0x18025464f  xor     edx, edx; y1
0x180254651  mov     [rbp+57h+dwData], rax
0x180254655  xor     ecx, ecx; x1
0x180254657  call    cs:__imp_CreateRectRgn
0x18025465e  nop     dword ptr [rax+rax+00h]
0x180254663  xor     r9d, r9d; y2
0x180254666  xor     r8d, r8d; x2
0x180254669  xor     edx, edx; y1
0x18025466b  mov     [rbp+57h+var_80], rax
0x18025466f  xor     ecx, ecx; x1
0x180254671  mov     rdi, rax
0x180254674  call    cs:__imp_CreateRectRgn
0x18025467b  nop     dword ptr [rax+rax+00h]
0x180254680  lea     r9, [rbp+57h+dwData]; dwData
0x180254684  xor     edx, edx; lprcClip
0x180254686  lea     r8, ?_GetDesktopRegionEnumProc@CPersistBrowserFrame@@CAHPEAUHMONITOR__@@PEAUHDC__@@PEAUtagRECT@@_J@Z; lpfnEnum
0x18025468d  mov     [rbp+57h+var_88], rax
0x180254691  xor     ecx, ecx; hdc
0x180254693  mov     rbx, rax
0x180254696  call    cs:__imp_EnumDisplayMonitors
0x18025469d  nop     dword ptr [rax+rax+00h]
0x1802546a2  mov     eax, [r15+0Ch]
0x1802546a6  mov     rcx, rbx; hrgn
0x1802546a9  mov     r9d, [r15+8]; right
0x1802546ad  mov     r8d, [r15+4]; top
0x1802546b1  mov     edx, [r15]; left
0x1802546b4  mov     [rsp+0C0h+bottom], eax; bottom
0x1802546b8  call    cs:__imp_SetRectRgn
0x1802546bf  nop     dword ptr [rax+rax+00h]
0x1802546c4  mov     rdx, [rbp+57h+dwData]; hrgnSrc1
0x1802546c8  mov     r9d, 1; iMode
0x1802546ce  mov     r8, rbx; hrgnSrc2
0x1802546d1  mov     rcx, rdi; hrgnDst
0x1802546d4  call    cs:__imp_CombineRgn
0x1802546db  nop     dword ptr [rax+rax+00h]
0x1802546e0  mov     rdx, rbx; hrgn2
0x1802546e3  mov     rcx, rdi; hrgn1
0x1802546e6  call    cs:__imp_EqualRgn
0x1802546ed  nop     dword ptr [rax+rax+00h]
0x1802546f2  test    eax, eax
0x1802546f4  jnz     loc_180254782
0x1802546fa  mov     edx, [rbp+57h+mi.rcWork.top]
0x1802546fd  xorps   xmm0, xmm0
0x180254700  mov     r8d, [rbp+57h+mi.rcWork.bottom]
0x180254704  mov     ecx, edx
0x180254706  sub     ecx, [r15+4]
0x18025470a  mov     r9d, r8d
0x18025470d  cmp     [r15+4], edx
0x180254711  mov     r10d, [rbp+57h+mi.rcWork.left]
0x180254715  mov     r11d, [rbp+57h+mi.rcWork.right]
0x180254719  cmovge  ecx, eax
0x18025471c  sub     r9d, [r15+0Ch]
0x180254720  mov     edx, r11d
0x180254723  cmp     [r15+0Ch], r8d
0x180254727  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x18025472b  cmovle  r9d, ecx
0x18025472f  mov     ecx, r10d
0x180254732  sub     ecx, [r15]
0x180254735  mov     r8d, r9d; dy
0x180254738  cmp     [r15], r10d
0x18025473b  cmovge  ecx, eax
0x18025473e  sub     edx, [r15+8]
0x180254742  cmp     [r15+8], r11d
0x180254746  cmovle  edx, ecx; dx
0x180254749  mov     rcx, r15; lprc
0x18025474c  call    cs:__imp_OffsetRect
0x180254753  nop     dword ptr [rax+rax+00h]
0x180254758  lea     r8, [rbp+57h+mi.rcWork]; lprcSrc2
0x18025475c  mov     rdx, r15; lprcSrc1
0x18025475f  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x180254763  call    cs:__imp_IntersectRect
0x18025476a  nop     dword ptr [rax+rax+00h]
0x18025476f  lea     rdx, [rbp+57h+rcDst]; lprcSrc
0x180254773  mov     rcx, r15; lprcDst
0x180254776  call    cs:__imp_CopyRect
0x18025477d  nop     dword ptr [rax+rax+00h]
0x180254782  neg     r14d
0x180254785  neg     esi
0x180254787  mov     r8d, r14d; dy
0x18025478a  mov     edx, esi; dx
0x18025478c  mov     rcx, r15; lprc
0x18025478f  call    cs:__imp_OffsetRect
0x180254796  nop     dword ptr [rax+rax+00h]
0x18025479b  lea     rcx, [rbp+57h+var_88]; this
0x18025479f  call    ??1CRegion@@QEAA@XZ; CRegion::~CRegion(void)
0x1802547a4  lea     rcx, [rbp+57h+var_80]; this
0x1802547a8  call    ??1CRegion@@QEAA@XZ; CRegion::~CRegion(void)
0x1802547ad  lea     rcx, [rbp+57h+dwData]; this
0x1802547b1  call    ??1CRegion@@QEAA@XZ; CRegion::~CRegion(void)
0x1802547b6  mov     rcx, [rbp+57h+var_40]
0x1802547ba  xor     rcx, rsp; StackCookie
0x1802547bd  call    __security_check_cookie
0x1802547c2  add     rsp, 98h
0x1802547c9  pop     r15
0x1802547cb  pop     r14
0x1802547cd  pop     rdi
0x1802547ce  pop     rsi
0x1802547cf  pop     rbx
0x1802547d0  pop     rbp
0x1802547d1  retn
```
