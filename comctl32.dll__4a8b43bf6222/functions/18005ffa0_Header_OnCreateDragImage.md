# Header_OnCreateDragImage

- ea: `0x18005ffa0`
- end: `0x1800602ce`
- name: `Header_OnCreateDragImage`
- size: `814`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180061d14`
- `0x180061f10`

## callees

- `0x1800115f0`
- `0x18001968c`
- `0x18005ec54`
- `0x18005fc74`
- `0x18005ffa0`
- `0x180060990`
- `0x1800852a0`
- `0x180085390`
- `0x180085430`
- `0x180085704`
- `0x1800857d0`
- `0x180085890`
- `0x180086550`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x18006000f`
- `GDI32!CreateCompatibleDC` at `0x18006000f`
- `GDI32!SelectObject` at `0x180060089`
- `GDI32!SelectObject` at `0x180060103`
- `GDI32!SelectObject` at `0x180060147`
- `GDI32!SelectObject` at `0x180060174`
- `GDI32!SelectObject` at `0x1800601b9`
- `GDI32!SelectObject` at `0x180060219`
- `GDI32!SelectObject` at `0x18006026b`
- `GDI32!SelectObject` at `0x18006027c`
- `GDI32!SelectObject` at `0x180060089`
- `GDI32!SelectObject` at `0x180060103`
- `GDI32!SelectObject` at `0x180060147`
- `GDI32!SelectObject` at `0x180060174`
- `GDI32!SelectObject` at `0x1800601b9`
- `GDI32!SelectObject` at `0x180060219`
- `GDI32!SelectObject` at `0x18006026b`
- `GDI32!SelectObject` at `0x18006027c`
- `GDI32!DeleteObject` at `0x180060285`
- `GDI32!DeleteObject` at `0x180060293`
- `GDI32!DeleteObject` at `0x1800602a1`
- `GDI32!DeleteObject` at `0x180060285`
- `GDI32!DeleteObject` at `0x180060293`
- `GDI32!DeleteObject` at `0x1800602a1`
- `GDI32!SetLayout` at `0x180060077`
- `GDI32!SetLayout` at `0x180060077`
- `GDI32!SetBkColor` at `0x1800600f7`
- `GDI32!SetBkColor` at `0x1800601ad`
- `GDI32!SetBkColor` at `0x1800600f7`
- `GDI32!SetBkColor` at `0x1800601ad`
- `GDI32!SetTextColor` at `0x1800600e8`
- `GDI32!SetTextColor` at `0x18006019e`
- `GDI32!SetTextColor` at `0x1800600e8`
- `GDI32!SetTextColor` at `0x18006019e`
- `GDI32!PatBlt` at `0x180060168`
- `GDI32!PatBlt` at `0x180060168`
- `GDI32!CreateBitmap` at `0x18006004e`
- `GDI32!CreateBitmap` at `0x18006004e`
- `USER32!DrawEdge` at `0x1800601f9`
- `USER32!DrawEdge` at `0x1800601f9`
- `USER32!OffsetRect` at `0x180060007`
- `USER32!OffsetRect` at `0x180060007`

## pseudocode

```c
struct _IMAGELIST *__fastcall Header_OnCreateDragImage(__int64 a1, unsigned int a2)
{
  int v2; // r12d
  struct _IMAGELIST *v4; // r15
  HDC CompatibleDC; // rbx
  HBITMAP Bitmap; // rdi
  HBITMAP ColorBitmap; // rsi
  HGDIOBJ v8; // r14
  void *v9; // rdx
  HGDIOBJ v10; // r12
  HGDIOBJ v11; // r12
  struct _IMAGELIST *v12; // r13
  int v13; // edx
  unsigned int v15; // [rsp+40h] [rbp-30h]
  int v17; // [rsp+48h] [rbp-28h]
  struct _IMAGELIST *himl; // [rsp+50h] [rbp-20h]
  struct tagRECT rc; // [rsp+58h] [rbp-18h] BYREF

  v2 = *(_DWORD *)(a1 + 32);
  rc = 0;
  v4 = 0;
  v15 = Header_ItemOrderToIndex();
  if ( (unsigned int)Header_OnGetItemRect(a1, v15, &rc) )
  {
    OffsetRect(&rc, -rc.left, -rc.top);
    CompatibleDC = CreateCompatibleDC(0);
    if ( CompatibleDC )
    {
      Bitmap = 0;
      ColorBitmap = (HBITMAP)CreateColorBitmap(rc.right, rc.bottom);
      if ( ColorBitmap )
      {
        Bitmap = CreateBitmap(rc.right, rc.bottom, 1u, 1u, 0);
        if ( Bitmap )
        {
          v8 = 0;
          v17 = v2 & 0x400000;
          if ( (v2 & 0x400000) != 0 )
            SetLayout(CompatibleDC, 1u);
          v9 = *(void **)(a1 + 72);
          if ( v9 )
            v8 = SelectObject(CompatibleDC, v9);
          himl = ImageList_Create(rc.right, rc.bottom, 1u, 1, 0);
          if ( himl )
          {
            v10 = 0;
            v4 = ImageList_Create(rc.right, rc.bottom, 1u, 1, 0);
            if ( v4 )
            {
              SetTextColor(CompatibleDC, g_clrBtnText);
              SetBkColor(CompatibleDC, g_clrBtnShadow);
              v11 = SelectObject(CompatibleDC, ColorBitmap);
              Header_DrawItem(a1, CompatibleDC, a2, v15, &rc, 2);
              if ( v17 )
                MirrorBitmapInDC(CompatibleDC, ColorBitmap);
              SelectObject(CompatibleDC, Bitmap);
              PatBlt(CompatibleDC, 0, 0, rc.right, rc.bottom, 0x42u);
              SelectObject(CompatibleDC, v11);
              ImageList_SetBkColor(himl, 0xFFFFFFFF);
              ImageList_Add(himl, ColorBitmap, Bitmap);
              SetTextColor(CompatibleDC, g_clrBtnText);
              SetBkColor(CompatibleDC, g_clrBtnShadow);
              v10 = SelectObject(CompatibleDC, ColorBitmap);
              Header_DrawItem(a1, CompatibleDC, a2, v15, &rc, 3);
              DrawEdge(CompatibleDC, &rc, 9u, 0x400Fu);
              if ( v17 )
                MirrorBitmapInDC(CompatibleDC, ColorBitmap);
              SelectObject(CompatibleDC, v10);
              ImageList_AddMasked(v4, ColorBitmap, g_clrBtnShadow);
              v12 = himl;
              ImageList_CopyDitherImage((int)v4, v13, 0, 0, himl, 0, 0);
            }
            else
            {
              v12 = himl;
            }
            ImageList_Destroy(v12);
            if ( v10 )
              SelectObject(CompatibleDC, v10);
          }
          if ( v8 )
            SelectObject(CompatibleDC, v8);
        }
      }
      DeleteObject(CompatibleDC);
      if ( ColorBitmap )
        DeleteObject(ColorBitmap);
      if ( Bitmap )
        DeleteObject(Bitmap);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18005ffa0  mov     [rsp-38h+arg_10], rbx
0x18005ffa5  push    rbp
0x18005ffa6  push    rsi
0x18005ffa7  push    rdi
0x18005ffa8  push    r12
0x18005ffaa  push    r13
0x18005ffac  push    r14
0x18005ffae  push    r15
0x18005ffb0  mov     rbp, rsp
0x18005ffb3  sub     rsp, 70h
0x18005ffb7  mov     rax, cs:__security_cookie
0x18005ffbe  xor     rax, rsp
0x18005ffc1  mov     [rbp+var_8], rax
0x18005ffc5  mov     r12d, [rcx+20h]
0x18005ffc9  xorps   xmm0, xmm0
0x18005ffcc  movups  xmmword ptr [rbp+rc.left], xmm0
0x18005ffd0  mov     [rbp+var_2C], edx
0x18005ffd3  mov     r13, rcx
0x18005ffd6  xor     r15d, r15d
0x18005ffd9  call    Header_ItemOrderToIndex
0x18005ffde  lea     r8, [rbp+rc]
0x18005ffe2  mov     [rbp+var_30], eax
0x18005ffe5  mov     edx, eax
0x18005ffe7  mov     rcx, r13
0x18005ffea  call    Header_OnGetItemRect
0x18005ffef  test    eax, eax
0x18005fff1  jz      loc_1800602A7
0x18005fff7  mov     r8d, [rbp+rc.top]
0x18005fffb  lea     rcx, [rbp+rc]; lprc
0x18005ffff  mov     edx, [rbp+rc.left]
0x180060002  neg     r8d; dy
0x180060005  neg     edx; dx
0x180060007  call    cs:__imp_OffsetRect
0x18006000d  xor     ecx, ecx; hdc
0x18006000f  call    cs:__imp_CreateCompatibleDC
0x180060015  mov     rbx, rax
0x180060018  test    rax, rax
0x18006001b  jz      loc_1800602A7
0x180060021  mov     edx, [rbp+rc.bottom]; cy
0x180060024  xor     edi, edi
0x180060026  mov     ecx, [rbp+rc.right]; cx
0x180060029  call    CreateColorBitmap
0x18006002e  mov     rsi, rax
0x180060031  test    rax, rax
0x180060034  jz      loc_180060282
0x18006003a  mov     edx, [rbp+rc.bottom]; nHeight
0x18006003d  lea     eax, [rdi+1]
0x180060040  mov     ecx, [rbp+rc.right]; nWidth
0x180060043  mov     r9d, eax; nBitCount
0x180060046  mov     r8d, eax; nPlanes
0x180060049  mov     [rsp+70h+lpBits], rdi; lpBits
0x18006004e  call    cs:__imp_CreateBitmap
0x180060054  mov     rdi, rax
0x180060057  test    rax, rax
0x18006005a  jz      loc_180060282
0x180060060  xor     r14d, r14d
0x180060063  and     r12d, 400000h
0x18006006a  mov     [rbp+var_28], r12d
0x18006006e  jz      short loc_18006007D
0x180060070  lea     edx, [r15+1]; l
0x180060074  mov     rcx, rbx; hdc
0x180060077  call    cs:__imp_SetLayout
0x18006007d  mov     rdx, [r13+48h]; h
0x180060081  test    rdx, rdx
0x180060084  jz      short loc_180060092
0x180060086  mov     rcx, rbx; hdc
0x180060089  call    cs:__imp_SelectObject
0x18006008f  mov     r14, rax
0x180060092  mov     edx, [rbp+rc.bottom]; cy
0x180060095  mov     r9d, 1; cInitial
0x18006009b  mov     ecx, [rbp+rc.right]; cx
0x18006009e  mov     r8d, r9d; flags
0x1800600a1  mov     dword ptr [rsp+70h+lpBits], r15d; cGrow
0x1800600a6  call    ImageList_Create
0x1800600ab  mov     [rbp+himl], rax
0x1800600af  test    rax, rax
0x1800600b2  jz      loc_180060271
0x1800600b8  mov     edx, [rbp+rc.bottom]; cy
0x1800600bb  xor     r12d, r12d
0x1800600be  mov     ecx, [rbp+rc.right]; cx
0x1800600c1  mov     dword ptr [rsp+70h+lpBits], r12d; cGrow
0x1800600c6  lea     r8d, [r12+1]; flags
0x1800600cb  mov     r9d, r8d; cInitial
0x1800600ce  call    ImageList_Create
0x1800600d3  mov     r15, rax
0x1800600d6  test    rax, rax
0x1800600d9  jz      loc_180060254
0x1800600df  mov     edx, cs:g_clrBtnText; color
0x1800600e5  mov     rcx, rbx; hdc
0x1800600e8  call    cs:__imp_SetTextColor
0x1800600ee  mov     edx, cs:g_clrBtnShadow; color
0x1800600f4  mov     rcx, rbx; hdc
0x1800600f7  call    cs:__imp_SetBkColor
0x1800600fd  mov     rdx, rsi; h
0x180060100  mov     rcx, rbx; hdc
0x180060103  call    cs:__imp_SelectObject
0x180060109  mov     r9d, [rbp+var_30]
0x18006010d  mov     rdx, rbx
0x180060110  mov     r8d, [rbp+var_2C]
0x180060114  mov     r12, rax
0x180060117  lea     rax, [rbp+rc]
0x18006011b  mov     [rsp+70h+rop], 2
0x180060123  mov     rcx, r13
0x180060126  mov     [rsp+70h+lpBits], rax
0x18006012b  call    Header_DrawItem
0x180060130  cmp     [rbp+var_28], 0
0x180060134  jz      short loc_180060141
0x180060136  mov     rdx, rsi; h
0x180060139  mov     rcx, rbx; hdc
0x18006013c  call    MirrorBitmapInDC
0x180060141  mov     rdx, rdi; h
0x180060144  mov     rcx, rbx; hdc
0x180060147  call    cs:__imp_SelectObject
0x18006014d  mov     eax, [rbp+rc.bottom]
0x180060150  xor     r8d, r8d; y
0x180060153  mov     r9d, [rbp+rc.right]; w
0x180060157  xor     edx, edx; x
0x180060159  mov     rcx, rbx; hdc
0x18006015c  mov     [rsp+70h+rop], 42h ; 'B'; rop
0x180060164  mov     dword ptr [rsp+70h+lpBits], eax; h
0x180060168  call    cs:__imp_PatBlt
0x18006016e  mov     rdx, r12; h
0x180060171  mov     rcx, rbx; hdc
0x180060174  call    cs:__imp_SelectObject
0x18006017a  mov     rcx, [rbp+himl]; himl
0x18006017e  or      edx, 0FFFFFFFFh; clrBk
0x180060181  call    ImageList_SetBkColor
0x180060186  mov     rcx, [rbp+himl]; himl
0x18006018a  mov     r8, rdi; hbmMask
0x18006018d  mov     rdx, rsi; hbmImage
0x180060190  call    ImageList_Add
0x180060195  mov     edx, cs:g_clrBtnText; color
0x18006019b  mov     rcx, rbx; hdc
0x18006019e  call    cs:__imp_SetTextColor
0x1800601a4  mov     edx, cs:g_clrBtnShadow; color
0x1800601aa  mov     rcx, rbx; hdc
0x1800601ad  call    cs:__imp_SetBkColor
0x1800601b3  mov     rdx, rsi; h
0x1800601b6  mov     rcx, rbx; hdc
0x1800601b9  call    cs:__imp_SelectObject
0x1800601bf  mov     r9d, [rbp+var_30]
0x1800601c3  mov     rdx, rbx
0x1800601c6  mov     r8d, [rbp+var_2C]
0x1800601ca  mov     r12, rax
0x1800601cd  lea     rax, [rbp+rc]
0x1800601d1  mov     [rsp+70h+rop], 3
0x1800601d9  mov     rcx, r13
0x1800601dc  mov     [rsp+70h+lpBits], rax
0x1800601e1  call    Header_DrawItem
0x1800601e6  mov     r9d, 400Fh; grfFlags
0x1800601ec  lea     rdx, [rbp+rc]; qrc
0x1800601f0  mov     r8d, 9; edge
0x1800601f6  mov     rcx, rbx; hdc
0x1800601f9  call    cs:__imp_DrawEdge
0x1800601ff  xor     r13d, r13d
0x180060202  cmp     [rbp+var_28], r13d
0x180060206  jz      short loc_180060213
0x180060208  mov     rdx, rsi; h
0x18006020b  mov     rcx, rbx; hdc
0x18006020e  call    MirrorBitmapInDC
0x180060213  mov     rdx, r12; h
0x180060216  mov     rcx, rbx; hdc
0x180060219  call    cs:__imp_SelectObject
0x18006021f  mov     r8d, cs:g_clrBtnShadow; crMask
0x180060226  mov     rdx, rsi; hbmImage
0x180060229  mov     rcx, r15; himl
0x18006022c  call    ImageList_AddMasked
0x180060231  mov     [rsp+70h+var_40], r13d; int
0x180060236  xor     r9d, r9d; int
0x180060239  mov     [rsp+70h+rop], r13d; int
0x18006023e  xor     r8d, r8d; int
0x180060241  mov     r13, [rbp+himl]
0x180060245  mov     rcx, r15; int
0x180060248  mov     [rsp+70h+lpBits], r13; struct _IMAGELIST *
0x18006024d  call    ImageList_CopyDitherImage
0x180060252  jmp     short loc_180060258
0x180060254  mov     r13, [rbp+himl]
0x180060258  mov     rcx, r13; himl
0x18006025b  call    ImageList_Destroy
0x180060260  test    r12, r12
0x180060263  jz      short loc_180060271
0x180060265  mov     rdx, r12; h
0x180060268  mov     rcx, rbx; hdc
0x18006026b  call    cs:__imp_SelectObject
0x180060271  test    r14, r14
0x180060274  jz      short loc_180060282
0x180060276  mov     rdx, r14; h
0x180060279  mov     rcx, rbx; hdc
0x18006027c  call    cs:__imp_SelectObject
0x180060282  mov     rcx, rbx; ho
0x180060285  call    cs:__imp_DeleteObject
0x18006028b  test    rsi, rsi
0x18006028e  jz      short loc_180060299
0x180060290  mov     rcx, rsi; ho
0x180060293  call    cs:__imp_DeleteObject
0x180060299  test    rdi, rdi
0x18006029c  jz      short loc_1800602A7
0x18006029e  mov     rcx, rdi; ho
0x1800602a1  call    cs:__imp_DeleteObject
0x1800602a7  mov     rax, r15
0x1800602aa  mov     rcx, [rbp+var_8]
0x1800602ae  xor     rcx, rsp; StackCookie
0x1800602b1  call    __security_check_cookie
0x1800602b6  mov     rbx, [rsp+70h+arg_10]
0x1800602be  add     rsp, 70h
0x1800602c2  pop     r15
0x1800602c4  pop     r14
0x1800602c6  pop     r13
0x1800602c8  pop     r12
0x1800602ca  pop     rdi
0x1800602cb  pop     rsi
0x1800602cc  pop     rbp
0x1800602cd  retn
```
