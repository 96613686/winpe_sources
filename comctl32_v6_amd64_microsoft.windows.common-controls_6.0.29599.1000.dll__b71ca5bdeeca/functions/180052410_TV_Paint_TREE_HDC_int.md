# TV_Paint(_TREE *,HDC__ *,int)

- ea: `0x180052410`
- end: `0x1800526eb`
- name: `?TV_Paint@@YAXPEAU_TREE@@PEAUHDC__@@H@Z`
- size: `731`
- prototype: `void __fastcall(struct _TREE *, HDC hdcTarget, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001d900`

## callees

- `0x18001cf08`
- `0x180021614`
- `0x180050e0c`
- `0x1800511bc`
- `0x180052410`
- `0x1800526f4`
- `0x180052760`
- `0x180114520`
- `0x180114ebc`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800525cc`
- `GDI32!DeleteObject` at `0x1800525cc`
- `GDI32!SelectObject` at `0x1800524fa`
- `GDI32!SelectObject` at `0x1800525c3`
- `GDI32!SelectObject` at `0x1800524fa`
- `GDI32!SelectObject` at `0x1800525c3`
- `GDI32!DeleteDC` at `0x1800525d5`
- `GDI32!DeleteDC` at `0x180052669`
- `GDI32!DeleteDC` at `0x1800525d5`
- `GDI32!DeleteDC` at `0x180052669`
- `GDI32!CreateCompatibleDC` at `0x1800524c3`
- `GDI32!CreateCompatibleDC` at `0x1800524c3`
- `GDI32!CreateCompatibleBitmap` at `0x1800524e2`
- `GDI32!CreateCompatibleBitmap` at `0x1800524e2`
- `GDI32!GetClipBox` at `0x1800526e0`
- `GDI32!GetClipBox` at `0x1800526e0`
- `GDI32!BitBlt` at `0x1800525b6`
- `GDI32!BitBlt` at `0x1800525b6`
- `GDI32!OffsetWindowOrgEx` at `0x180052511`
- `GDI32!OffsetWindowOrgEx` at `0x180052682`
- `GDI32!OffsetWindowOrgEx` at `0x180052511`
- `GDI32!OffsetWindowOrgEx` at `0x180052682`
- `USER32!FillRect` at `0x180052533`
- `USER32!FillRect` at `0x1800526a1`
- `USER32!FillRect` at `0x180052533`
- `USER32!FillRect` at `0x1800526a1`
- `USER32!EndPaint` at `0x1800525fa`
- `USER32!EndPaint` at `0x1800525fa`
- `USER32!GetUpdateRect` at `0x180052639`
- `USER32!GetUpdateRect` at `0x180052639`
- `UxTheme!BufferedPaintSetAlpha` at `0x1800526cb`
- `UxTheme!BufferedPaintSetAlpha` at `0x1800526cb`

## pseudocode

```c
void __fastcall TV_Paint(struct _TREE *a1, HDC hdcTarget)
{
  int v4; // r15d
  int v5; // r14d
  HDC v6; // rax
  HDC v7; // rsi
  HDC hdcSrc; // rdi
  HBITMAP v9; // r12
  HDC v10; // r13
  HBITMAP CompatibleBitmap; // rax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rdi
  CCompositedDraw *v15; // rbx
  __int64 v16; // rcx
  void *v17; // rcx
  int cy; // [rsp+20h] [rbp-89h]
  HGDIOBJ h; // [rsp+50h] [rbp-59h]
  PAINTSTRUCT Paint; // [rsp+60h] [rbp-49h] BYREF
  struct tagRECT Rect; // [rsp+B0h] [rbp+7h] BYREF

  Rect = 0;
  if ( hdcTarget || GetUpdateRect(*(HWND *)a1, &Rect, 0) )
  {
    memset_0(&Paint, 0, sizeof(Paint));
    v4 = 0;
    v5 = 1;
    if ( hdcTarget )
    {
      v4 = 1;
      GetClipBox(hdcTarget, &Paint.rcPaint);
    }
    v6 = CCompositedDraw::BeginCompositedPaint(*((CCompositedDraw **)a1 + 73), *(HWND *)a1, hdcTarget, &Paint, 0);
    v7 = v6;
    if ( v6 )
    {
      hdcSrc = 0;
      v9 = 0;
      h = 0;
      v10 = v6;
      if ( *(_DWORD *)(*((_QWORD *)a1 + 73) + 24LL) )
      {
        OffsetWindowOrgEx(0, Paint.rcPaint.left, Paint.rcPaint.top, 0);
        TV_GetBackgroundBrush(a1, v7);
        FillRect(v7, &Paint.rcPaint, *((HBRUSH *)a1 + 28));
        v16 = *((_QWORD *)a1 + 73);
        if ( !*(_DWORD *)(v16 + 28) )
        {
          v17 = *(void **)(v16 + 40);
          if ( v17 )
            BufferedPaintSetAlpha(v17, &Paint.rcPaint, 0xFFu);
        }
      }
      else if ( (*((_BYTE *)a1 + 500) & 4) != 0 )
      {
        hdcSrc = CreateCompatibleDC(v6);
        if ( hdcSrc )
        {
          CompatibleBitmap = CreateCompatibleBitmap(
                               v10,
                               Paint.rcPaint.right - Paint.rcPaint.left,
                               Paint.rcPaint.bottom - Paint.rcPaint.top);
          v9 = CompatibleBitmap;
          if ( CompatibleBitmap )
          {
            h = SelectObject(hdcSrc, CompatibleBitmap);
            OffsetWindowOrgEx(hdcSrc, Paint.rcPaint.left, Paint.rcPaint.top, 0);
            v10 = hdcSrc;
            TV_GetBackgroundBrush(a1, hdcSrc);
            FillRect(hdcSrc, &Paint.rcPaint, *((HBRUSH *)a1 + 28));
            v4 = 0;
          }
          else
          {
            DeleteDC(hdcSrc);
            hdcSrc = 0;
          }
        }
      }
      v12 = *((_QWORD *)a1 + 71);
      if ( v12 )
      {
        v13 = *((_DWORD *)a1 + 16);
        if ( (v13 & 0x400000) != 0 )
        {
          *((_DWORD *)a1 + 16) = v13 & 0xFF7FFFFF;
          if ( (unsigned int)CAnimationEngine::UpdateAnimateData(v12, 0) == 1 )
            *((_DWORD *)a1 + 16) |= 0x800000u;
        }
      }
      if ( !v4 && !Paint.fErase )
        v5 = 0;
      TV_DrawTree(a1, v10, v5, &Paint.rcPaint, cy);
      TV_PostDrawTrackAnimation(a1);
      if ( hdcSrc )
      {
        BitBlt(
          v7,
          Paint.rcPaint.left,
          Paint.rcPaint.top,
          Paint.rcPaint.right - Paint.rcPaint.left,
          Paint.rcPaint.bottom - Paint.rcPaint.top,
          hdcSrc,
          Paint.rcPaint.left,
          Paint.rcPaint.top,
          0xCC0020u);
        SelectObject(hdcSrc, h);
        DeleteObject(v9);
        DeleteDC(hdcSrc);
      }
    }
    v14 = *((_QWORD *)a1 + 73);
    v15 = *(CCompositedDraw **)a1;
    CCompositedDraw::EndDoubleBuffer((CCompositedDraw *)v14);
    if ( *(_DWORD *)(v14 + 32) )
      EndPaint((HWND)v15, &Paint);
    *(_QWORD *)(v14 + 16) = 0;
    *(_DWORD *)(v14 + 32) = 0;
  }
}

```

## disassembly

```asm
0x180052410  mov     [rsp-8+arg_10], rbx
0x180052415  push    rbp
0x180052416  push    rsi
0x180052417  push    rdi
0x180052418  push    r12
0x18005241a  push    r13
0x18005241c  push    r14
0x18005241e  push    r15
0x180052420  lea     rbp, [rsp-27h]
0x180052425  sub     rsp, 0D0h
0x18005242c  mov     rax, cs:__security_cookie
0x180052433  xor     rax, rsp
0x180052436  mov     [rbp+57h+var_40], rax
0x18005243a  xor     r13d, r13d
0x18005243d  xorps   xmm0, xmm0
0x180052440  mov     rdi, rdx
0x180052443  mov     rbx, rcx
0x180052446  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18005244a  test    rdx, rdx
0x18005244d  jz      loc_18005262F
0x180052453  xor     edx, edx; Val
0x180052455  lea     rcx, [rbp+57h+Paint]; void *
0x180052459  lea     r8d, [rdx+48h]; Size
0x18005245d  call    memset_0
0x180052462  mov     r15d, r13d
0x180052465  mov     r14d, 1
0x18005246b  test    rdi, rdi
0x18005246e  jnz     loc_1800526D6
0x180052474  mov     rdx, [rbx]; hWnd
0x180052477  lea     r9, [rbp+57h+Paint]; lpPaint
0x18005247b  mov     rcx, [rbx+248h]; this
0x180052482  mov     r8, rdi; hdcTarget
0x180052485  mov     [rsp+100h+cy], r13d; int
0x18005248a  call    ?BeginCompositedPaint@CCompositedDraw@@QEAAPEAUHDC__@@PEAUHWND__@@PEAU2@PEAUtagPAINTSTRUCT@@H@Z; CCompositedDraw::BeginCompositedPaint(HWND__ *,HDC__ *,tagPAINTSTRUCT *,int)
0x18005248f  mov     rsi, rax
0x180052492  test    rax, rax
0x180052495  jz      loc_1800525DB
0x18005249b  mov     rcx, [rbx+248h]
0x1800524a2  xor     edi, edi
0x1800524a4  mov     r12, r13
0x1800524a7  mov     [rbp+57h+h], r13
0x1800524ab  mov     r13, rax
0x1800524ae  cmp     [rcx+18h], edi
0x1800524b1  jnz     loc_180052676
0x1800524b7  test    byte ptr [rbx+1F4h], 4
0x1800524be  jz      short loc_18005253C
0x1800524c0  mov     rcx, rax; hdc
0x1800524c3  call    cs:__imp_CreateCompatibleDC
0x1800524c9  mov     rdi, rax
0x1800524cc  test    rax, rax
0x1800524cf  jz      short loc_18005253C
0x1800524d1  mov     r8d, [rbp+57h+Paint.rcPaint.bottom]
0x1800524d5  mov     rcx, r13; hdc
0x1800524d8  mov     edx, [rbp+57h+Paint.rcPaint.right]
0x1800524db  sub     r8d, [rbp+57h+Paint.rcPaint.top]; cy
0x1800524df  sub     edx, [rbp+57h+Paint.rcPaint.left]; cx
0x1800524e2  call    cs:__imp_CreateCompatibleBitmap
0x1800524e8  mov     r12, rax
0x1800524eb  mov     rcx, rdi; hdc
0x1800524ee  test    rax, rax
0x1800524f1  jz      loc_180052669
0x1800524f7  mov     rdx, rax; h
0x1800524fa  call    cs:__imp_SelectObject
0x180052500  mov     r8d, [rbp+57h+Paint.rcPaint.top]; y
0x180052504  xor     r9d, r9d; lppt
0x180052507  mov     edx, [rbp+57h+Paint.rcPaint.left]; x
0x18005250a  mov     rcx, rdi; hdc
0x18005250d  mov     [rbp+57h+h], rax
0x180052511  call    cs:__imp_OffsetWindowOrgEx
0x180052517  mov     rdx, rdi; HDC
0x18005251a  mov     rcx, rbx; struct _TREE *
0x18005251d  mov     r13, rdi
0x180052520  call    ?TV_GetBackgroundBrush@@YAXPEAU_TREE@@PEAUHDC__@@@Z; TV_GetBackgroundBrush(_TREE *,HDC__ *)
0x180052525  mov     r8, [rbx+0E0h]; hbr
0x18005252c  lea     rdx, [rbp+57h+Paint.rcPaint]; lprc
0x180052530  mov     rcx, rdi; hDC
0x180052533  call    cs:__imp_FillRect
0x180052539  xor     r15d, r15d
0x18005253c  mov     rcx, [rbx+238h]
0x180052543  test    rcx, rcx
0x180052546  jz      short loc_180052555
0x180052548  mov     eax, [rbx+40h]
0x18005254b  bt      eax, 16h
0x18005254f  jb      loc_180052648
0x180052555  test    r15d, r15d
0x180052558  jnz     short loc_180052563
0x18005255a  cmp     [rbp+57h+Paint.fErase], r15d
0x18005255e  jnz     short loc_180052563
0x180052560  xor     r14d, r14d
0x180052563  lea     r9, [rbp+57h+Paint.rcPaint]; struct tagRECT *
0x180052567  mov     r8d, r14d; int
0x18005256a  mov     rdx, r13; HDC
0x18005256d  mov     rcx, rbx; struct _TREE *
0x180052570  call    ?TV_DrawTree@@YAXPEAU_TREE@@PEAUHDC__@@HPEBUtagRECT@@H@Z; TV_DrawTree(_TREE *,HDC__ *,int,tagRECT const *,int)
0x180052575  mov     rcx, rbx; struct _TREE *
0x180052578  call    ?TV_PostDrawTrackAnimation@@YAXPEAU_TREE@@@Z; TV_PostDrawTrackAnimation(_TREE *)
0x18005257d  xor     r13d, r13d
0x180052580  test    rdi, rdi
0x180052583  jz      short loc_1800525DB
0x180052585  mov     r8d, [rbp+57h+Paint.rcPaint.top]; y
0x180052589  mov     rcx, rsi; hdc
0x18005258c  mov     edx, [rbp+57h+Paint.rcPaint.left]; x
0x18005258f  mov     eax, [rbp+57h+Paint.rcPaint.bottom]
0x180052592  mov     r9d, [rbp+57h+Paint.rcPaint.right]
0x180052596  sub     eax, r8d
0x180052599  mov     [rsp+100h+rop], 0CC0020h; rop
0x1800525a1  sub     r9d, edx; cx
0x1800525a4  mov     [rsp+100h+y1], r8d; y1
0x1800525a9  mov     [rsp+100h+x1], edx; x1
0x1800525ad  mov     [rsp+100h+hdcSrc], rdi; hdcSrc
0x1800525b2  mov     [rsp+100h+cy], eax; cy
0x1800525b6  call    cs:__imp_BitBlt
0x1800525bc  mov     rdx, [rbp+57h+h]; h
0x1800525c0  mov     rcx, rdi; hdc
0x1800525c3  call    cs:__imp_SelectObject
0x1800525c9  mov     rcx, r12; ho
0x1800525cc  call    cs:__imp_DeleteObject
0x1800525d2  mov     rcx, rdi; hdc
0x1800525d5  call    cs:__imp_DeleteDC
0x1800525db  mov     rdi, [rbx+248h]
0x1800525e2  mov     rbx, [rbx]
0x1800525e5  mov     rcx, rdi; this
0x1800525e8  call    ?EndDoubleBuffer@CCompositedDraw@@QEAAXXZ; CCompositedDraw::EndDoubleBuffer(void)
0x1800525ed  cmp     [rdi+20h], r13d
0x1800525f1  jz      short loc_180052600
0x1800525f3  lea     rdx, [rbp+57h+Paint]; lpPaint
0x1800525f7  mov     rcx, rbx; hWnd
0x1800525fa  call    cs:__imp_EndPaint
0x180052600  mov     [rdi+10h], r13
0x180052604  mov     [rdi+20h], r13d
0x180052608  mov     rcx, [rbp+57h+var_40]
0x18005260c  xor     rcx, rsp; StackCookie
0x18005260f  call    __security_check_cookie
0x180052614  mov     rbx, [rsp+100h+arg_10]
0x18005261c  add     rsp, 0D0h
0x180052623  pop     r15
0x180052625  pop     r14
0x180052627  pop     r13
0x180052629  pop     r12
0x18005262b  pop     rdi
0x18005262c  pop     rsi
0x18005262d  pop     rbp
0x18005262e  retn
0x18005262f  mov     rcx, [rcx]; hWnd
0x180052632  lea     rdx, [rbp+57h+Rect]; lpRect
0x180052636  xor     r8d, r8d; bErase
0x180052639  call    cs:__imp_GetUpdateRect
0x18005263f  test    eax, eax
0x180052641  jz      short loc_180052608
0x180052643  jmp     loc_180052453
0x180052648  btr     eax, 17h
0x18005264c  xor     edx, edx
0x18005264e  mov     [rbx+40h], eax
0x180052651  call    ?UpdateAnimateData@CAnimationEngine@@QEAA?AW4AnimationUpdateResults@@PEAVCAnimationData@@@Z; CAnimationEngine::UpdateAnimateData(CAnimationData *)
0x180052656  cmp     eax, r14d
0x180052659  jnz     loc_180052555
0x18005265f  bts     dword ptr [rbx+40h], 17h
0x180052664  jmp     loc_180052555
0x180052669  call    cs:__imp_DeleteDC
0x18005266f  xor     edi, edi
0x180052671  jmp     loc_18005253C
0x180052676  mov     r8d, [rbp+57h+Paint.rcPaint.top]; y
0x18005267a  xor     r9d, r9d; lppt
0x18005267d  mov     edx, [rbp+57h+Paint.rcPaint.left]; x
0x180052680  xor     ecx, ecx; hdc
0x180052682  call    cs:__imp_OffsetWindowOrgEx
0x180052688  mov     rdx, rsi; HDC
0x18005268b  mov     rcx, rbx; struct _TREE *
0x18005268e  call    ?TV_GetBackgroundBrush@@YAXPEAU_TREE@@PEAUHDC__@@@Z; TV_GetBackgroundBrush(_TREE *,HDC__ *)
0x180052693  mov     r8, [rbx+0E0h]; hbr
0x18005269a  lea     rdx, [rbp+57h+Paint.rcPaint]; lprc
0x18005269e  mov     rcx, rsi; hDC
0x1800526a1  call    cs:__imp_FillRect
0x1800526a7  mov     rcx, [rbx+248h]
0x1800526ae  cmp     [rcx+1Ch], edi
0x1800526b1  jnz     loc_18005253C
0x1800526b7  mov     rcx, [rcx+28h]; hBufferedPaint
0x1800526bb  test    rcx, rcx
0x1800526be  jz      loc_18005253C
0x1800526c4  mov     r8b, 0FFh; alpha
0x1800526c7  lea     rdx, [rbp+57h+Paint.rcPaint]; prc
0x1800526cb  call    cs:__imp_BufferedPaintSetAlpha
0x1800526d1  jmp     loc_18005253C
0x1800526d6  lea     rdx, [rbp+57h+Paint.rcPaint]; lprect
0x1800526da  mov     rcx, rdi; hdc
0x1800526dd  mov     r15d, r14d
0x1800526e0  call    cs:__imp_GetClipBox
0x1800526e6  jmp     loc_180052474
```
