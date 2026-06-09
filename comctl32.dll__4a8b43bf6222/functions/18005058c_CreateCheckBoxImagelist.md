# CreateCheckBoxImagelist

- ea: `0x18005058c`
- end: `0x1800507c5`
- name: `CreateCheckBoxImagelist`
- size: `569`
- prototype: `__int64 __fastcall(HIMAGELIST himl)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180053d94`
- `0x1800696b8`

## callees

- `0x1800115f0`
- `0x180035c50`
- `0x180042570`
- `0x18005058c`
- `0x1800852a0`
- `0x180085430`
- `0x1800857d0`
- `0x180085e30`
- `0x180085eb0`
- `0x1800864d0`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x1800505ef`
- `GDI32!CreateCompatibleDC` at `0x1800505ef`
- `GDI32!SelectObject` at `0x18005067f`
- `GDI32!SelectObject` at `0x18005074a`
- `GDI32!SelectObject` at `0x18005067f`
- `GDI32!SelectObject` at `0x18005074a`
- `GDI32!DeleteObject` at `0x18005079b`
- `GDI32!DeleteObject` at `0x18005079b`
- `GDI32!DeleteDC` at `0x180050792`
- `GDI32!DeleteDC` at `0x180050792`
- `USER32!GetDC` at `0x1800505c7`
- `USER32!GetDC` at `0x1800505c7`
- `USER32!ReleaseDC` at `0x1800505fd`
- `USER32!ReleaseDC` at `0x1800505fd`
- `USER32!InflateRect` at `0x1800506cb`
- `USER32!InflateRect` at `0x1800506cb`
- `USER32!DrawFrameControl` at `0x180050702`
- `USER32!DrawFrameControl` at `0x18005073d`
- `USER32!DrawFrameControl` at `0x180050702`
- `USER32!DrawFrameControl` at `0x18005073d`
- `USER32!OffsetRect` at `0x1800506e6`
- `USER32!OffsetRect` at `0x180050712`
- `USER32!OffsetRect` at `0x180050727`
- `USER32!OffsetRect` at `0x1800506e6`
- `USER32!OffsetRect` at `0x180050712`
- `USER32!OffsetRect` at `0x180050727`

## pseudocode

```c
struct _IMAGELIST *__fastcall CreateCheckBoxImagelist(HIMAGELIST himl, int a2, __int64 a3, int a4)
{
  HDC DC; // rax
  HDC v8; // rsi
  int v9; // ebx
  HDC CompatibleDC; // rdi
  int v11; // ecx
  int v12; // edx
  struct _IMAGELIST *v13; // rsi
  HBITMAP ColorBitmap; // r14
  COLORREF v15; // r13d
  HGDIOBJ v16; // rax
  int v18; // [rsp+30h] [rbp-38h] BYREF
  int cy; // [rsp+34h] [rbp-34h] BYREF
  HGDIOBJ h; // [rsp+38h] [rbp-30h] BYREF
  struct tagRECT rc; // [rsp+40h] [rbp-28h] BYREF

  v18 = 0;
  cy = 0;
  DC = GetDC(0);
  v8 = DC;
  rc = 0;
  v9 = (a2 != 0) + 2;
  if ( !DC )
    return 0;
  CompatibleDC = CreateCompatibleDC(DC);
  ReleaseDC(0, v8);
  if ( !CompatibleDC )
    return 0;
  if ( himl && ImageList_GetIconSize(himl, &v18, &cy) )
  {
    v11 = v18;
    v12 = cy;
  }
  else
  {
    v11 = g_cxSmIcon;
    v12 = g_cySmIcon;
    v18 = g_cxSmIcon;
    cy = g_cySmIcon;
  }
  v13 = ImageList_Create(v11, v12, 1u, 0, (unsigned int)(a2 != 0) + 2);
  ColorBitmap = (HBITMAP)CreateColorBitmap(v18 * v9, cy);
  v15 = 16711935;
  if ( g_clrWindow == 16711935 )
    v15 = 16711680;
  v16 = SelectObject(CompatibleDC, ColorBitmap);
  rc.bottom = cy;
  h = v16;
  *(_QWORD *)&rc.left = 0;
  rc.right = v18 * v9;
  FillRectClr(CompatibleDC, &rc, v15);
  rc.right = v18;
  InflateRect(&rc, -g_cxEdge, -g_cyEdge);
  ++rc.right;
  ++rc.bottom;
  if ( a2 )
    OffsetRect(&rc, v18, 0);
  DrawFrameControl(CompatibleDC, &rc, 4u, 0x4000u);
  OffsetRect(&rc, v18, 0);
  if ( a4 )
    OffsetRect(&rc, -1, 0);
  DrawFrameControl(CompatibleDC, &rc, 4u, 0x4400u);
  SelectObject(CompatibleDC, h);
  ImageList_AddMasked(v13, ColorBitmap, v15);
  if ( a4 )
  {
    h = ImageList_GetIcon(v13, (unsigned int)(a2 != 0) + 1, 0);
    MirrorIcon((HICON *)&h, 0);
    ImageList_ReplaceIcon(v13, (a2 != 0) + 1, (HICON)h);
  }
  DeleteDC(CompatibleDC);
  DeleteObject(ColorBitmap);
  return v13;
}

```

## disassembly

```asm
0x18005058c  push    rbp
0x18005058e  push    rbx
0x18005058f  push    rsi
0x180050590  push    rdi
0x180050591  push    r12
0x180050593  push    r13
0x180050595  push    r14
0x180050597  push    r15
0x180050599  mov     rbp, rsp
0x18005059c  sub     rsp, 68h
0x1800505a0  mov     rax, cs:__security_cookie
0x1800505a7  xor     rax, rsp
0x1800505aa  mov     [rbp+var_18], rax
0x1800505ae  mov     r14, rcx
0x1800505b1  mov     [rbp+var_38], 0
0x1800505b8  xor     ecx, ecx; hWnd
0x1800505ba  mov     [rbp+cy], 0
0x1800505c1  mov     r15d, r9d
0x1800505c4  mov     r12d, edx
0x1800505c7  call    cs:__imp_GetDC
0x1800505cd  mov     ecx, r12d
0x1800505d0  xorps   xmm0, xmm0
0x1800505d3  neg     ecx
0x1800505d5  mov     rsi, rax
0x1800505d8  movups  xmmword ptr [rbp+rc.left], xmm0
0x1800505dc  sbb     ebx, ebx
0x1800505de  neg     ebx
0x1800505e0  add     ebx, 2
0x1800505e3  test    rax, rax
0x1800505e6  jz      loc_1800507A6
0x1800505ec  mov     rcx, rax; hdc
0x1800505ef  call    cs:__imp_CreateCompatibleDC
0x1800505f5  mov     rdx, rsi; hDC
0x1800505f8  xor     ecx, ecx; hWnd
0x1800505fa  mov     rdi, rax
0x1800505fd  call    cs:__imp_ReleaseDC
0x180050603  test    rdi, rdi
0x180050606  jz      loc_1800507A6
0x18005060c  test    r14, r14
0x18005060f  jz      short loc_18005062D
0x180050611  lea     r8, [rbp+cy]; cy
0x180050615  mov     rcx, r14; himl
0x180050618  lea     rdx, [rbp+var_38]; cx
0x18005061c  call    ImageList_GetIconSize
0x180050621  test    eax, eax
0x180050623  jz      short loc_18005062D
0x180050625  mov     ecx, [rbp+var_38]
0x180050628  mov     edx, [rbp+cy]
0x18005062b  jmp     short loc_18005063F
0x18005062d  mov     ecx, cs:g_cxSmIcon; cx
0x180050633  mov     edx, cs:g_cySmIcon; cy
0x180050639  mov     [rbp+var_38], ecx
0x18005063c  mov     [rbp+cy], edx
0x18005063f  xor     r9d, r9d; cInitial
0x180050642  mov     [rsp+68h+cGrow], ebx; cGrow
0x180050646  lea     r8d, [r9+1]; flags
0x18005064a  call    ImageList_Create
0x18005064f  mov     edx, [rbp+cy]; cy
0x180050652  mov     ecx, ebx
0x180050654  imul    ecx, [rbp+var_38]; cx
0x180050658  mov     rsi, rax
0x18005065b  call    CreateColorBitmap
0x180050660  mov     r14, rax
0x180050663  mov     r13d, 0FF00FFh
0x180050669  cmp     cs:g_clrWindow, r13d
0x180050670  mov     eax, 0FF0000h
0x180050675  mov     rdx, r14; h
0x180050678  mov     rcx, rdi; hdc
0x18005067b  cmovz   r13d, eax
0x18005067f  call    cs:__imp_SelectObject
0x180050685  mov     ecx, [rbp+cy]
0x180050688  lea     rdx, [rbp+rc]; lprect
0x18005068c  mov     [rbp+rc.bottom], ecx
0x18005068f  mov     r8d, r13d; color
0x180050692  mov     ecx, ebx
0x180050694  mov     [rbp+h], rax
0x180050698  imul    ecx, [rbp+var_38]
0x18005069c  mov     qword ptr [rbp+rc.left], 0
0x1800506a4  mov     [rbp+rc.right], ecx
0x1800506a7  mov     rcx, rdi; hdc
0x1800506aa  call    FillRectClr
0x1800506af  mov     ecx, [rbp+var_38]
0x1800506b2  mov     r8d, cs:g_cyEdge
0x1800506b9  mov     edx, cs:g_cxEdge
0x1800506bf  neg     r8d; dy
0x1800506c2  mov     [rbp+rc.right], ecx
0x1800506c5  neg     edx; dx
0x1800506c7  lea     rcx, [rbp+rc]; lprc
0x1800506cb  call    cs:__imp_InflateRect
0x1800506d1  inc     [rbp+rc.right]
0x1800506d4  inc     [rbp+rc.bottom]
0x1800506d7  test    r12d, r12d
0x1800506da  jz      short loc_1800506EC
0x1800506dc  mov     edx, [rbp+var_38]; dx
0x1800506df  lea     rcx, [rbp+rc]; lprc
0x1800506e3  xor     r8d, r8d; dy
0x1800506e6  call    cs:__imp_OffsetRect
0x1800506ec  mov     r12d, 4
0x1800506f2  lea     rdx, [rbp+rc]; LPRECT
0x1800506f6  mov     r8d, r12d; UINT
0x1800506f9  mov     r9d, 4000h; UINT
0x1800506ff  mov     rcx, rdi; HDC
0x180050702  call    cs:__imp_DrawFrameControl
0x180050708  mov     edx, [rbp+var_38]; dx
0x18005070b  lea     rcx, [rbp+rc]; lprc
0x18005070f  xor     r8d, r8d; dy
0x180050712  call    cs:__imp_OffsetRect
0x180050718  test    r15d, r15d
0x18005071b  jz      short loc_18005072D
0x18005071d  xor     r8d, r8d; dy
0x180050720  lea     rcx, [rbp+rc]; lprc
0x180050724  or      edx, 0FFFFFFFFh; dx
0x180050727  call    cs:__imp_OffsetRect
0x18005072d  mov     r9d, 4400h; UINT
0x180050733  lea     rdx, [rbp+rc]; LPRECT
0x180050737  mov     r8d, r12d; UINT
0x18005073a  mov     rcx, rdi; HDC
0x18005073d  call    cs:__imp_DrawFrameControl
0x180050743  mov     rdx, [rbp+h]; h
0x180050747  mov     rcx, rdi; hdc
0x18005074a  call    cs:__imp_SelectObject
0x180050750  mov     r8d, r13d; crMask
0x180050753  mov     rdx, r14; hbmImage
0x180050756  mov     rcx, rsi; himl
0x180050759  call    ImageList_AddMasked
0x18005075e  test    r15d, r15d
0x180050761  jz      short loc_18005078F
0x180050763  xor     r8d, r8d; flags
0x180050766  lea     edx, [rbx-1]; i
0x180050769  mov     rcx, rsi; himl
0x18005076c  call    ImageList_GetIcon
0x180050771  xor     edx, edx
0x180050773  mov     [rbp+h], rax
0x180050777  lea     rcx, [rbp+h]
0x18005077b  call    MirrorIcon
0x180050780  mov     r8, [rbp+h]; hicon
0x180050784  lea     edx, [rbx-1]; i
0x180050787  mov     rcx, rsi; himl
0x18005078a  call    ImageList_ReplaceIcon
0x18005078f  mov     rcx, rdi; hdc
0x180050792  call    cs:__imp_DeleteDC
0x180050798  mov     rcx, r14; ho
0x18005079b  call    cs:__imp_DeleteObject
0x1800507a1  mov     rax, rsi
0x1800507a4  jmp     short loc_1800507A8
0x1800507a6  xor     eax, eax
0x1800507a8  mov     rcx, [rbp+var_18]
0x1800507ac  xor     rcx, rsp; StackCookie
0x1800507af  call    __security_check_cookie
0x1800507b4  add     rsp, 68h
0x1800507b8  pop     r15
0x1800507ba  pop     r14
0x1800507bc  pop     r13
0x1800507be  pop     r12
0x1800507c0  pop     rdi
0x1800507c1  pop     rsi
0x1800507c2  pop     rbx
0x1800507c3  pop     rbp
0x1800507c4  retn
```
