# ListView_OnCreateDragImage

- ea: `0x18005506c`
- end: `0x180055452`
- name: `ListView_OnCreateDragImage`
- size: `998`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005c0a0`

## callees

- `0x1800115f0`
- `0x18001968c`
- `0x1800526a8`
- `0x180052cf8`
- `0x18005506c`
- `0x180055de0`
- `0x180058588`
- `0x18005bcc0`
- `0x1800852a0`
- `0x180085390`
- `0x180085530`
- `0x180085704`
- `0x180086550`
- `0x18008ea60`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x1800551c8`
- `GDI32!CreateCompatibleDC` at `0x1800551c8`
- `GDI32!SelectObject` at `0x180055239`
- `GDI32!SelectObject` at `0x180055277`
- `GDI32!SelectObject` at `0x1800552cd`
- `GDI32!SelectObject` at `0x180055314`
- `GDI32!SelectObject` at `0x180055324`
- `GDI32!SelectObject` at `0x180055239`
- `GDI32!SelectObject` at `0x180055277`
- `GDI32!SelectObject` at `0x1800552cd`
- `GDI32!SelectObject` at `0x180055314`
- `GDI32!SelectObject` at `0x180055324`
- `GDI32!DeleteObject` at `0x180055402`
- `GDI32!DeleteObject` at `0x180055410`
- `GDI32!DeleteObject` at `0x18005541e`
- `GDI32!DeleteObject` at `0x180055402`
- `GDI32!DeleteObject` at `0x180055410`
- `GDI32!DeleteObject` at `0x18005541e`
- `GDI32!SetLayout` at `0x18005522c`
- `GDI32!SetLayout` at `0x18005522c`
- `GDI32!SetBkMode` at `0x180055247`
- `GDI32!SetBkMode` at `0x180055247`
- `GDI32!PatBlt` at `0x18005529f`
- `GDI32!PatBlt` at `0x1800552eb`
- `GDI32!PatBlt` at `0x18005529f`
- `GDI32!PatBlt` at `0x1800552eb`
- `GDI32!CreateBitmap` at `0x180055208`
- `GDI32!CreateBitmap` at `0x180055208`
- `USER32!InflateRect` at `0x18005518e`
- `USER32!InflateRect` at `0x18005518e`
- `USER32!UpdateWindow` at `0x180055122`
- `USER32!UpdateWindow` at `0x180055122`

## pseudocode

```c
struct _IMAGELIST *__fastcall ListView_OnCreateDragImage(__int64 a1, int a2, LONG *a3)
{
  __int64 v3; // r13
  struct _IMAGELIST *v6; // r15
  LONG left; // edx
  int v8; // esi
  int v9; // r12d
  int v10; // eax
  HDC CompatibleDC; // rdi
  HBITMAP Bitmap; // r14
  HBITMAP ColorBitmap; // r12
  struct _IMAGELIST *v14; // rsi
  struct _IMAGELIST *v15; // rax
  int v16; // edx
  int v18; // [rsp+40h] [rbp-C0h]
  int v19; // [rsp+40h] [rbp-C0h]
  unsigned int nHeight; // [rsp+44h] [rbp-BCh]
  unsigned int v21; // [rsp+48h] [rbp-B8h]
  __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  HGDIOBJ h; // [rsp+58h] [rbp-A8h]
  __int128 v24; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v25; // [rsp+70h] [rbp-90h]
  int v26[4]; // [rsp+80h] [rbp-80h]
  __int64 v27; // [rsp+90h] [rbp-70h]
  _QWORD v28[18]; // [rsp+A0h] [rbp-60h] BYREF
  struct tagRECT v29; // [rsp+130h] [rbp+30h] BYREF
  struct tagRECT rc; // [rsp+140h] [rbp+40h] BYREF
  struct tagRECT rcDst; // [rsp+150h] [rbp+50h] BYREF
  int v32[4]; // [rsp+160h] [rbp+60h] BYREF

  v3 = a2;
  v27 = 0;
  v22 = 0;
  rcDst = 0;
  rc = 0;
  *(_OWORD *)v32 = 0;
  v24 = 0;
  v25 = 0;
  *(_OWORD *)v26 = 0;
  memset(v28, 0, sizeof(v28));
  v29 = 0;
  if ( !a3 || (int)v3 < 0 || (int)v3 >= *(_DWORD *)(a1 + 512) )
    return 0;
  v6 = 0;
  v18 = *(_DWORD *)(a1 + 32);
  if ( *(_DWORD *)(a1 + 532) == (_DWORD)v3 )
  {
    ListView_OnSetHotItem(a1);
    UpdateWindow(*(HWND *)a1);
  }
  ListView_GetRects(a1, v3, (int)&rc, (int)v32, &rcDst, &v29);
  if ( (*(_BYTE *)(a1 + 16) & 3) == 0 )
  {
    ListView_UnfoldRects(a1, (unsigned int)v3, &rc, v32, &rcDst, &v29);
    InflateRect(&rc, -g_cxIconMargin, -g_cyIconMargin);
  }
  left = v29.left;
  v8 = v29.right - v29.left;
  LODWORD(v22) = rcDst.left - v29.left;
  v9 = v29.bottom - rc.top;
  v10 = rcDst.top - rc.top;
  a3[1] = rc.top;
  HIDWORD(v22) = v10;
  v21 = v8;
  nHeight = v9;
  *a3 = left;
  CompatibleDC = CreateCompatibleDC(0);
  if ( CompatibleDC )
  {
    Bitmap = 0;
    ColorBitmap = (HBITMAP)CreateColorBitmap(v8, v9);
    if ( ColorBitmap )
    {
      Bitmap = CreateBitmap(v8, nHeight, 1u, 1u, 0);
      if ( Bitmap )
      {
        v19 = v18 & 0x400000;
        if ( v19 )
          SetLayout(CompatibleDC, 1u);
        SelectObject(CompatibleDC, *(HGDIOBJ *)(a1 + 88));
        SetBkMode(CompatibleDC, 1);
        v28[0] = a1;
        v28[1] = &v22;
        v28[13] = v3;
        v28[4] = 0;
        v28[10] = CompatibleDC;
        v28[2] = 0;
        LODWORD(v28[3]) = 135;
        h = SelectObject(CompatibleDC, ColorBitmap);
        PatBlt(CompatibleDC, 0, 0, v8, nHeight, 0x42u);
        ListView_DrawItem(v28);
        if ( v19 )
          MirrorBitmapInDC(CompatibleDC, ColorBitmap);
        LODWORD(v28[3]) = 135;
        SelectObject(CompatibleDC, Bitmap);
        PatBlt(CompatibleDC, 0, 0, v8, nHeight, 0xFF0062u);
        ListView_DrawItem(v28);
        if ( v19 )
          MirrorBitmapInDC(CompatibleDC, Bitmap);
        SelectObject(CompatibleDC, h);
        SelectObject(CompatibleDC, g_hfontSystem);
        if ( (*(_BYTE *)(a1 + 16) & 3) != 0 )
        {
          if ( (*(_BYTE *)(a1 + 16) & 3) != 0 )
          {
            v14 = *(struct _IMAGELIST **)(a1 + 232);
          }
          else if ( ((*(_BYTE *)(a1 + 16) & 3) != 0) == 2 )
          {
            v14 = *(struct _IMAGELIST **)(a1 + 480);
          }
          else
          {
            v14 = 0;
          }
        }
        else
        {
          v14 = *(struct _IMAGELIST **)(a1 + 272);
        }
        v15 = (struct _IMAGELIST *)ImageList_Clone(v14, v21, nHeight);
        v6 = v15;
        if ( v15 )
        {
          ImageList_SetBkColor(v15, 0xFFFFFFFF);
          ImageList_Add(v6, ColorBitmap, Bitmap);
          if ( v14 )
          {
            *(_QWORD *)((char *)&v24 + 4) = (unsigned int)v3;
            LODWORD(v25) = 3840;
            LODWORD(v24) = 10;
            ListView_OnGetItem(a1, &v24);
            ImageList_CopyDitherImage(
              (int)v6,
              v16,
              rc.left - v29.left,
              0,
              v14,
              v26[1],
              WORD6(v24) & 0xF00 | (*(_DWORD *)(a1 + 32) >> 15) & 0x80);
          }
        }
      }
    }
    DeleteObject(CompatibleDC);
    if ( ColorBitmap )
      DeleteObject(ColorBitmap);
    if ( Bitmap )
      DeleteObject(Bitmap);
  }
  return v6;
}

```

## disassembly

```asm
0x18005506c  mov     [rsp-8+arg_18], rbx
0x180055071  push    rbp
0x180055072  push    rsi
0x180055073  push    rdi
0x180055074  push    r12
0x180055076  push    r13
0x180055078  push    r14
0x18005507a  push    r15
0x18005507c  lea     rbp, [rsp-80h]
0x180055081  sub     rsp, 180h
0x180055088  mov     rax, cs:__security_cookie
0x18005508f  xor     rax, rsp
0x180055092  mov     [rbp+0B0h+var_40], rax
0x180055096  xorps   xmm1, xmm1
0x180055099  movsxd  r13, edx
0x18005509c  xorps   xmm0, xmm0
0x18005509f  xor     eax, eax
0x1800550a1  mov     rdi, r8
0x1800550a4  mov     [rbp+0B0h+var_120], rax
0x1800550a8  mov     rbx, rcx
0x1800550ab  mov     [rsp+1B0h+var_160], rax
0x1800550b0  xor     edx, edx; Val
0x1800550b2  lea     rcx, [rbp+0B0h+var_110]; void *
0x1800550b6  mov     r8d, 90h; Size
0x1800550bc  movups  xmmword ptr [rbp+0B0h+rcDst.left], xmm0
0x1800550c0  movups  xmmword ptr [rbp+0B0h+rc.left], xmm1
0x1800550c4  movups  xmmword ptr [rbp+0B0h+var_50], xmm0
0x1800550c8  movups  [rsp+1B0h+var_150], xmm1
0x1800550cd  movups  [rsp+1B0h+var_140], xmm1
0x1800550d2  movups  xmmword ptr [rbp+0B0h+var_130], xmm1
0x1800550d6  call    memset
0x1800550db  xorps   xmm0, xmm0
0x1800550de  movups  xmmword ptr [rbp+0B0h+var_80.left], xmm0
0x1800550e2  test    rdi, rdi
0x1800550e5  jz      loc_180055429
0x1800550eb  test    r13d, r13d
0x1800550ee  js      loc_180055429
0x1800550f4  cmp     r13d, [rbx+200h]
0x1800550fb  jge     loc_180055429
0x180055101  mov     eax, [rbx+20h]
0x180055104  xor     r15d, r15d
0x180055107  mov     [rsp+1B0h+var_170], eax
0x18005510b  cmp     [rbx+214h], r13d
0x180055112  jnz     short loc_180055128
0x180055114  or      edx, 0FFFFFFFFh
0x180055117  mov     rcx, rbx; int
0x18005511a  call    ListView_OnSetHotItem
0x18005511f  mov     rcx, [rbx]; hWnd
0x180055122  call    cs:__imp_UpdateWindow
0x180055128  lea     rax, [rbp+0B0h+var_80]
0x18005512c  mov     edx, r13d; int
0x18005512f  mov     qword ptr [rsp+1B0h+rop], rax; LPRECT
0x180055134  lea     r9, [rbp+0B0h+var_50]; int
0x180055138  lea     rax, [rbp+0B0h+rcDst]
0x18005513c  mov     rcx, rbx; int
0x18005513f  lea     r8, [rbp+0B0h+rc]; int
0x180055143  mov     [rsp+1B0h+lpBits], rax; lprcDst
0x180055148  call    ListView_GetRects
0x18005514d  test    byte ptr [rbx+10h], 3
0x180055151  jnz     short loc_180055194
0x180055153  lea     rax, [rbp+0B0h+var_80]
0x180055157  mov     edx, r13d
0x18005515a  mov     qword ptr [rsp+1B0h+rop], rax
0x18005515f  lea     r9, [rbp+0B0h+var_50]
0x180055163  lea     rax, [rbp+0B0h+rcDst]
0x180055167  mov     rcx, rbx
0x18005516a  lea     r8, [rbp+0B0h+rc]
0x18005516e  mov     [rsp+1B0h+lpBits], rax
0x180055173  call    ListView_UnfoldRects
0x180055178  mov     r8d, cs:g_cyIconMargin
0x18005517f  lea     rcx, [rbp+0B0h+rc]; lprc
0x180055183  mov     edx, cs:g_cxIconMargin
0x180055189  neg     r8d; dy
0x18005518c  neg     edx; dx
0x18005518e  call    cs:__imp_InflateRect
0x180055194  mov     ecx, [rbp+0B0h+rc.top]
0x180055197  mov     edx, [rbp+0B0h+var_80.left]
0x18005519a  mov     eax, [rbp+0B0h+rcDst.left]
0x18005519d  mov     esi, [rbp+0B0h+var_80.right]
0x1800551a0  sub     eax, edx
0x1800551a2  mov     r12d, [rbp+0B0h+var_80.bottom]
0x1800551a6  sub     esi, edx
0x1800551a8  mov     dword ptr [rsp+1B0h+var_160], eax
0x1800551ac  sub     r12d, ecx
0x1800551af  mov     eax, [rbp+0B0h+rcDst.top]
0x1800551b2  sub     eax, ecx
0x1800551b4  mov     [rdi+4], ecx
0x1800551b7  xor     ecx, ecx; hdc
0x1800551b9  mov     dword ptr [rsp+1B0h+var_160+4], eax
0x1800551bd  mov     [rsp+1B0h+var_168], esi
0x1800551c1  mov     [rsp+1B0h+nHeight], r12d
0x1800551c6  mov     [rdi], edx
0x1800551c8  call    cs:__imp_CreateCompatibleDC
0x1800551ce  mov     rdi, rax
0x1800551d1  test    rax, rax
0x1800551d4  jz      loc_180055424
0x1800551da  mov     edx, r12d; cy
0x1800551dd  mov     ecx, esi; cx
0x1800551df  xor     r14d, r14d
0x1800551e2  call    CreateColorBitmap
0x1800551e7  mov     r12, rax
0x1800551ea  test    rax, rax
0x1800551ed  jz      loc_1800553FF
0x1800551f3  mov     edx, [rsp+1B0h+nHeight]; nHeight
0x1800551f7  lea     eax, [r14+1]
0x1800551fb  mov     r9d, eax; nBitCount
0x1800551fe  mov     [rsp+1B0h+lpBits], r14; lpBits
0x180055203  mov     r8d, eax; nPlanes
0x180055206  mov     ecx, esi; nWidth
0x180055208  call    cs:__imp_CreateBitmap
0x18005520e  mov     r14, rax
0x180055211  test    rax, rax
0x180055214  jz      loc_1800553FF
0x18005521a  and     [rsp+1B0h+var_170], 400000h
0x180055222  jz      short loc_180055232
0x180055224  mov     edx, 1; l
0x180055229  mov     rcx, rdi; hdc
0x18005522c  call    cs:__imp_SetLayout
0x180055232  mov     rdx, [rbx+58h]; h
0x180055236  mov     rcx, rdi; hdc
0x180055239  call    cs:__imp_SelectObject
0x18005523f  mov     edx, 1; mode
0x180055244  mov     rcx, rdi; hdc
0x180055247  call    cs:__imp_SetBkMode
0x18005524d  lea     rax, [rsp+1B0h+var_160]
0x180055252  mov     [rbp+0B0h+var_110], rbx
0x180055256  mov     rdx, r12; h
0x180055259  mov     [rbp+0B0h+var_108], rax
0x18005525d  mov     rcx, rdi; hdc
0x180055260  mov     [rbp+0B0h+var_A8], r13
0x180055264  mov     [rbp+0B0h+var_F0], r15
0x180055268  mov     [rbp+0B0h+var_C0], rdi
0x18005526c  mov     [rbp+0B0h+var_100], r15
0x180055270  mov     [rbp+0B0h+var_F8], 87h
0x180055277  call    cs:__imp_SelectObject
0x18005527d  mov     r15d, [rsp+1B0h+nHeight]
0x180055282  mov     r9d, esi; w
0x180055285  xor     r8d, r8d; y
0x180055288  mov     [rsp+1B0h+rop], 42h ; 'B'; rop
0x180055290  xor     edx, edx; x
0x180055292  mov     [rsp+1B0h+h], rax
0x180055297  mov     rcx, rdi; hdc
0x18005529a  mov     dword ptr [rsp+1B0h+lpBits], r15d; h
0x18005529f  call    cs:__imp_PatBlt
0x1800552a5  lea     rcx, [rbp+0B0h+var_110]
0x1800552a9  call    ListView_DrawItem
0x1800552ae  cmp     [rsp+1B0h+var_170], 0
0x1800552b3  jz      short loc_1800552C0
0x1800552b5  mov     rdx, r12; h
0x1800552b8  mov     rcx, rdi; hdc
0x1800552bb  call    MirrorBitmapInDC
0x1800552c0  mov     rdx, r14; h
0x1800552c3  mov     [rbp+0B0h+var_F8], 87h
0x1800552ca  mov     rcx, rdi; hdc
0x1800552cd  call    cs:__imp_SelectObject
0x1800552d3  mov     r9d, esi; w
0x1800552d6  mov     [rsp+1B0h+rop], 0FF0062h; rop
0x1800552de  xor     r8d, r8d; y
0x1800552e1  mov     dword ptr [rsp+1B0h+lpBits], r15d; h
0x1800552e6  xor     edx, edx; x
0x1800552e8  mov     rcx, rdi; hdc
0x1800552eb  call    cs:__imp_PatBlt
0x1800552f1  lea     rcx, [rbp+0B0h+var_110]
0x1800552f5  call    ListView_DrawItem
0x1800552fa  cmp     [rsp+1B0h+var_170], 0
0x1800552ff  jz      short loc_18005530C
0x180055301  mov     rdx, r14; h
0x180055304  mov     rcx, rdi; hdc
0x180055307  call    MirrorBitmapInDC
0x18005530c  mov     rdx, [rsp+1B0h+h]; h
0x180055311  mov     rcx, rdi; hdc
0x180055314  call    cs:__imp_SelectObject
0x18005531a  mov     rdx, cs:g_hfontSystem; h
0x180055321  mov     rcx, rdi; hdc
0x180055324  call    cs:__imp_SelectObject
0x18005532a  test    byte ptr [rbx+10h], 3
0x18005532e  mov     ecx, 0
0x180055333  setnz   cl
0x180055336  test    ecx, ecx
0x180055338  jz      short loc_18005535A
0x18005533a  sub     ecx, 1
0x18005533d  jz      short loc_180055351
0x18005533f  cmp     ecx, 1
0x180055342  jz      short loc_180055348
0x180055344  xor     esi, esi
0x180055346  jmp     short loc_180055361
0x180055348  mov     rsi, [rbx+1E0h]
0x18005534f  jmp     short loc_180055361
0x180055351  mov     rsi, [rbx+0E8h]
0x180055358  jmp     short loc_180055361
0x18005535a  mov     rsi, [rbx+110h]
0x180055361  mov     edx, [rsp+1B0h+var_168]
0x180055365  mov     r8d, r15d
0x180055368  mov     rcx, rsi
0x18005536b  call    ImageList_Clone
0x180055370  mov     r15, rax
0x180055373  test    rax, rax
0x180055376  jz      loc_1800553FF
0x18005537c  or      edx, 0FFFFFFFFh; clrBk
0x18005537f  mov     rcx, rax; himl
0x180055382  call    ImageList_SetBkColor
0x180055387  mov     r8, r14; hbmMask
0x18005538a  mov     rdx, r12; hbmImage
0x18005538d  mov     rcx, r15; himl
0x180055390  call    ImageList_Add
0x180055395  test    rsi, rsi
0x180055398  jz      short loc_1800553FF
0x18005539a  mov     dword ptr [rsp+1B0h+var_150+4], r13d
0x18005539f  lea     rdx, [rsp+1B0h+var_150]
0x1800553a4  mov     r13d, 0F00h
0x1800553aa  mov     dword ptr [rsp+1B0h+var_150+8], 0
0x1800553b2  mov     rcx, rbx
0x1800553b5  mov     dword ptr [rsp+1B0h+var_140], r13d
0x1800553ba  mov     dword ptr [rsp+1B0h+var_150], 0Ah
0x1800553c2  call    ListView_OnGetItem
0x1800553c7  mov     ecx, [rbx+20h]
0x1800553ca  xor     r9d, r9d; int
0x1800553cd  mov     eax, dword ptr [rsp+1B0h+var_150+0Ch]
0x1800553d1  mov     r8d, [rbp+0B0h+rc.left]
0x1800553d5  and     eax, r13d
0x1800553d8  sub     r8d, [rbp+0B0h+var_80.left]; int
0x1800553dc  shr     ecx, 0Fh
0x1800553df  and     ecx, 80h
0x1800553e5  or      ecx, eax
0x1800553e7  mov     eax, [rbp+0B0h+var_130+4]
0x1800553ea  mov     [rsp+1B0h+var_180], ecx; int
0x1800553ee  mov     rcx, r15; int
0x1800553f1  mov     [rsp+1B0h+rop], eax; int
0x1800553f5  mov     [rsp+1B0h+lpBits], rsi; struct _IMAGELIST *
0x1800553fa  call    ImageList_CopyDitherImage
0x1800553ff  mov     rcx, rdi; ho
0x180055402  call    cs:__imp_DeleteObject
0x180055408  test    r12, r12
0x18005540b  jz      short loc_180055416
0x18005540d  mov     rcx, r12; ho
0x180055410  call    cs:__imp_DeleteObject
0x180055416  test    r14, r14
0x180055419  jz      short loc_180055424
0x18005541b  mov     rcx, r14; ho
0x18005541e  call    cs:__imp_DeleteObject
0x180055424  mov     rax, r15
0x180055427  jmp     short loc_18005542B
0x180055429  xor     eax, eax
0x18005542b  mov     rcx, [rbp+0B0h+var_40]
0x18005542f  xor     rcx, rsp; StackCookie
0x180055432  call    __security_check_cookie
0x180055437  mov     rbx, [rsp+1B0h+arg_18]
0x18005543f  add     rsp, 180h
0x180055446  pop     r15
0x180055448  pop     r14
0x18005544a  pop     r13
0x18005544c  pop     r12
0x18005544e  pop     rdi
0x18005544f  pop     rsi
0x180055450  pop     rbp
0x180055451  retn
```
