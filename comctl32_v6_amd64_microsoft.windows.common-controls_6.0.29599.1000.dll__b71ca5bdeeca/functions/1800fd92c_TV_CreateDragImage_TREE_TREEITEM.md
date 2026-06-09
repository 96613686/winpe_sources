# TV_CreateDragImage(_TREE *,_TREEITEM *)

- ea: `0x1800fd92c`
- end: `0x1800fdc18`
- name: `?TV_CreateDragImage@@YAPEAU_IMAGELIST@@PEAU_TREE@@PEAU_TREEITEM@@@Z`
- size: `748`
- prototype: `struct _IMAGELIST *__fastcall(struct _TREE *, struct _TREEITEM *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18001d900`

## callees

- `0x180012230`
- `0x18001aaf0`
- `0x18001c9b0`
- `0x18001fc20`
- `0x180027a2c`
- `0x1800286c0`
- `0x1800bfd50`
- `0x1800fd92c`
- `0x180114ebc`
- `0x18011f01c`
- `0x18012a628`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800fdbdb`
- `GDI32!DeleteObject` at `0x1800fdbe9`
- `GDI32!DeleteObject` at `0x1800fdbf7`
- `GDI32!DeleteObject` at `0x1800fdbdb`
- `GDI32!DeleteObject` at `0x1800fdbe9`
- `GDI32!DeleteObject` at `0x1800fdbf7`
- `GDI32!SetBkMode` at `0x1800fda37`
- `GDI32!SetBkMode` at `0x1800fda37`
- `GDI32!PatBlt` at `0x1800fda69`
- `GDI32!PatBlt` at `0x1800fdacf`
- `GDI32!PatBlt` at `0x1800fda69`
- `GDI32!PatBlt` at `0x1800fdacf`
- `GDI32!SelectObject` at `0x1800fda29`
- `GDI32!SelectObject` at `0x1800fda43`
- `GDI32!SelectObject` at `0x1800fdab1`
- `GDI32!SelectObject` at `0x1800fdb11`
- `GDI32!SelectObject` at `0x1800fdb21`
- `GDI32!SelectObject` at `0x1800fda29`
- `GDI32!SelectObject` at `0x1800fda43`
- `GDI32!SelectObject` at `0x1800fdab1`
- `GDI32!SelectObject` at `0x1800fdb11`
- `GDI32!SelectObject` at `0x1800fdb21`
- `GDI32!CreateCompatibleDC` at `0x1800fd9a7`
- `GDI32!CreateCompatibleDC` at `0x1800fd9a7`
- `GDI32!SetLayout` at `0x1800fda14`
- `GDI32!SetLayout` at `0x1800fda14`
- `GDI32!CreateBitmap` at `0x1800fd9e9`
- `GDI32!CreateBitmap` at `0x1800fd9e9`

## pseudocode

```c
struct _IMAGELIST *__fastcall TV_CreateDragImage(struct _TREE *a1, struct _TREEITEM *a2)
{
  struct _IMAGELIST *v4; // r15
  unsigned __int16 ItemWidth; // ax
  int v6; // r12d
  int v7; // r13d
  int v8; // r14d
  HDC CompatibleDC; // rbx
  int v10; // r12d
  HBITMAP Bitmap; // rbp
  HBITMAP ColorBitmap; // r14
  int v13; // r15d
  void *v14; // rdx
  struct _IMAGELIST *v15; // rax
  int v16; // eax
  struct tagTVITEMEXW v18; // [rsp+40h] [rbp-98h] BYREF
  int h; // [rsp+E0h] [rbp+8h]
  HGDIOBJ ha; // [rsp+E0h] [rbp+8h]

  memset_0(&v18, 0, sizeof(v18));
  if ( !*((_QWORD *)a1 + 22) )
    return 0;
  if ( !a2 )
  {
    a2 = (struct _TREEITEM *)*((_QWORD *)a1 + 20);
    if ( !a2 )
      return 0;
  }
  h = *((_DWORD *)a1 + 8);
  v4 = 0;
  ItemWidth = TV_GetItemWidth(a1, a2);
  v6 = *((__int16 *)a1 + 174);
  v7 = *((__int16 *)a1 + 179);
  v8 = ItemWidth;
  CompatibleDC = CreateCompatibleDC(0);
  if ( CompatibleDC )
  {
    v10 = v8 + v6;
    Bitmap = 0;
    ColorBitmap = (HBITMAP)CreateColorBitmap(v10, v7);
    if ( ColorBitmap )
    {
      Bitmap = CreateBitmap(v10, v7, 1u, 1u, 0);
      if ( Bitmap )
      {
        v13 = h & 0x400000;
        if ( (h & 0x400000) != 0 )
          SetLayout(CompatibleDC, 1u);
        v14 = (void *)*((_QWORD *)a1 + 29);
        if ( v14 )
          SelectObject(CompatibleDC, v14);
        SetBkMode(CompatibleDC, 1);
        ha = SelectObject(CompatibleDC, ColorBitmap);
        PatBlt(CompatibleDC, 0, 0, v10, v7, 0x42u);
        TV_DrawItem(a1, a2, CompatibleDC, 0, 0, ((*((_DWORD *)a1 + 125) & 8) << 6) | 7);
        if ( v13 )
          MirrorBitmapInDC(CompatibleDC, ColorBitmap);
        SelectObject(CompatibleDC, Bitmap);
        PatBlt(CompatibleDC, 0, 0, v10, v7, 0xFF0062u);
        TV_DrawItem(a1, a2, CompatibleDC, 0, 0, 7u);
        if ( v13 )
          MirrorBitmapInDC(CompatibleDC, Bitmap);
        SelectObject(CompatibleDC, ha);
        SelectObject(CompatibleDC, g_hfontSystem);
        v15 = ImageList_Create(v10, v7, 1u, 1, 0);
        v4 = v15;
        if ( v15 )
        {
          ImageList_SetBkColor(v15, 0xFFFFFFFF);
          ImageList_Add(v4, ColorBitmap, Bitmap);
          TV_GetItem(a1, a2, 2u, &v18);
          v16 = *((__int16 *)a1 + 179) - *((__int16 *)a1 + 175);
          ImageList_CopyDitherImage(
            (int)v4,
            v16 % 2,
            0,
            v16 / 2,
            *((HIMAGELIST *)a1 + 22),
            v18.iImage,
            (*((_DWORD *)a1 + 8) >> 15) & 0x80 | *((_WORD *)a2 + 26) & 0xF00);
        }
      }
    }
    DeleteObject(CompatibleDC);
    if ( ColorBitmap )
      DeleteObject(ColorBitmap);
    if ( Bitmap )
      DeleteObject(Bitmap);
  }
  return v4;
}

```

## disassembly

```asm
0x1800fd92c  push    rbx
0x1800fd92e  push    rbp
0x1800fd92f  push    rsi
0x1800fd930  push    rdi
0x1800fd931  push    r12
0x1800fd933  push    r13
0x1800fd935  push    r14
0x1800fd937  push    r15
0x1800fd939  sub     rsp, 98h
0x1800fd940  mov     rsi, rdx
0x1800fd943  mov     rdi, rcx
0x1800fd946  xor     edx, edx; Val
0x1800fd948  lea     rcx, [rsp+0D8h+var_98]; void *
0x1800fd94d  lea     r8d, [rdx+50h]; Size
0x1800fd951  call    memset_0
0x1800fd956  cmp     qword ptr [rdi+0B0h], 0
0x1800fd95e  jz      loc_1800FDC02
0x1800fd964  test    rsi, rsi
0x1800fd967  jnz     short loc_1800FD979
0x1800fd969  mov     rsi, [rdi+0A0h]
0x1800fd970  test    rsi, rsi
0x1800fd973  jz      loc_1800FDC02
0x1800fd979  mov     eax, [rdi+20h]
0x1800fd97c  mov     rdx, rsi; struct _TREEITEM *
0x1800fd97f  mov     rcx, rdi; struct _TREE *
0x1800fd982  mov     dword ptr [rsp+0D8h+h], eax
0x1800fd989  xor     r15d, r15d
0x1800fd98c  call    ?TV_GetItemWidth@@YAGPEAU_TREE@@PEAU_TREEITEM@@@Z; TV_GetItemWidth(_TREE *,_TREEITEM *)
0x1800fd991  movsx   r12d, word ptr [rdi+15Ch]
0x1800fd999  xor     ecx, ecx; hdc
0x1800fd99b  movsx   r13d, word ptr [rdi+166h]
0x1800fd9a3  movzx   r14d, ax
0x1800fd9a7  call    cs:__imp_CreateCompatibleDC
0x1800fd9ad  mov     rbx, rax
0x1800fd9b0  test    rax, rax
0x1800fd9b3  jz      loc_1800FDBFD
0x1800fd9b9  add     r12d, r14d
0x1800fd9bc  mov     edx, r13d; cy
0x1800fd9bf  mov     ecx, r12d; cx
0x1800fd9c2  xor     ebp, ebp
0x1800fd9c4  call    CreateColorBitmap
0x1800fd9c9  mov     r14, rax
0x1800fd9cc  test    rax, rax
0x1800fd9cf  jz      loc_1800FDBD8
0x1800fd9d5  lea     eax, [rbp+1]
0x1800fd9d8  mov     [rsp+0D8h+lpBits], rbp; lpBits
0x1800fd9dd  mov     r9d, eax; nBitCount
0x1800fd9e0  mov     r8d, eax; nPlanes
0x1800fd9e3  mov     edx, r13d; nHeight
0x1800fd9e6  mov     ecx, r12d; nWidth
0x1800fd9e9  call    cs:__imp_CreateBitmap
0x1800fd9ef  mov     rbp, rax
0x1800fd9f2  test    rax, rax
0x1800fd9f5  jz      loc_1800FDBD8
0x1800fd9fb  mov     r15d, dword ptr [rsp+0D8h+h]
0x1800fda03  and     r15d, 400000h
0x1800fda0a  jz      short loc_1800FDA1A
0x1800fda0c  mov     edx, 1; l
0x1800fda11  mov     rcx, rbx; hdc
0x1800fda14  call    cs:__imp_SetLayout
0x1800fda1a  mov     rdx, [rdi+0E8h]; h
0x1800fda21  test    rdx, rdx
0x1800fda24  jz      short loc_1800FDA2F
0x1800fda26  mov     rcx, rbx; hdc
0x1800fda29  call    cs:__imp_SelectObject
0x1800fda2f  mov     edx, 1; mode
0x1800fda34  mov     rcx, rbx; hdc
0x1800fda37  call    cs:__imp_SetBkMode
0x1800fda3d  mov     rdx, r14; h
0x1800fda40  mov     rcx, rbx; hdc
0x1800fda43  call    cs:__imp_SelectObject
0x1800fda49  mov     r9d, r12d; w
0x1800fda4c  mov     [rsp+0D8h+rop], 42h ; 'B'; rop
0x1800fda54  xor     r8d, r8d; y
0x1800fda57  mov     [rsp+0D8h+h], rax
0x1800fda5f  xor     edx, edx; x
0x1800fda61  mov     dword ptr [rsp+0D8h+lpBits], r13d; h
0x1800fda66  mov     rcx, rbx; hdc
0x1800fda69  call    cs:__imp_PatBlt
0x1800fda6f  mov     eax, [rdi+1F4h]
0x1800fda75  xor     r9d, r9d; int
0x1800fda78  and     eax, 8
0x1800fda7b  mov     r8, rbx; HDC
0x1800fda7e  shl     eax, 6
0x1800fda81  mov     rdx, rsi; struct _TREEITEM *
0x1800fda84  or      eax, 7
0x1800fda87  mov     rcx, rdi; struct _TREE *
0x1800fda8a  mov     [rsp+0D8h+rop], eax; unsigned int
0x1800fda8e  mov     dword ptr [rsp+0D8h+lpBits], 0; int
0x1800fda96  call    ?TV_DrawItem@@YAXPEAU_TREE@@PEAU_TREEITEM@@PEAUHDC__@@HHI@Z; TV_DrawItem(_TREE *,_TREEITEM *,HDC__ *,int,int,uint)
0x1800fda9b  test    r15d, r15d
0x1800fda9e  jz      short loc_1800FDAAB
0x1800fdaa0  mov     rdx, r14; h
0x1800fdaa3  mov     rcx, rbx; hdc
0x1800fdaa6  call    MirrorBitmapInDC
0x1800fdaab  mov     rdx, rbp; h
0x1800fdaae  mov     rcx, rbx; hdc
0x1800fdab1  call    cs:__imp_SelectObject
0x1800fdab7  mov     r9d, r12d; w
0x1800fdaba  mov     [rsp+0D8h+rop], 0FF0062h; rop
0x1800fdac2  xor     r8d, r8d; y
0x1800fdac5  mov     dword ptr [rsp+0D8h+lpBits], r13d; h
0x1800fdaca  xor     edx, edx; x
0x1800fdacc  mov     rcx, rbx; hdc
0x1800fdacf  call    cs:__imp_PatBlt
0x1800fdad5  xor     r9d, r9d; int
0x1800fdad8  mov     [rsp+0D8h+rop], 7; unsigned int
0x1800fdae0  mov     r8, rbx; HDC
0x1800fdae3  mov     dword ptr [rsp+0D8h+lpBits], 0; int
0x1800fdaeb  mov     rdx, rsi; struct _TREEITEM *
0x1800fdaee  mov     rcx, rdi; struct _TREE *
0x1800fdaf1  call    ?TV_DrawItem@@YAXPEAU_TREE@@PEAU_TREEITEM@@PEAUHDC__@@HHI@Z; TV_DrawItem(_TREE *,_TREEITEM *,HDC__ *,int,int,uint)
0x1800fdaf6  test    r15d, r15d
0x1800fdaf9  jz      short loc_1800FDB06
0x1800fdafb  mov     rdx, rbp; h
0x1800fdafe  mov     rcx, rbx; hdc
0x1800fdb01  call    MirrorBitmapInDC
0x1800fdb06  mov     rdx, [rsp+0D8h+h]; h
0x1800fdb0e  mov     rcx, rbx; hdc
0x1800fdb11  call    cs:__imp_SelectObject
0x1800fdb17  mov     rdx, cs:g_hfontSystem; h
0x1800fdb1e  mov     rcx, rbx; hdc
0x1800fdb21  call    cs:__imp_SelectObject
0x1800fdb27  mov     eax, 1
0x1800fdb2c  mov     dword ptr [rsp+0D8h+lpBits], 0; cGrow
0x1800fdb34  mov     r9d, eax; cInitial
0x1800fdb37  mov     r8d, eax; flags
0x1800fdb3a  mov     edx, r13d; cy
0x1800fdb3d  mov     ecx, r12d; cx
0x1800fdb40  call    ImageList_Create
0x1800fdb45  mov     r15, rax
0x1800fdb48  test    rax, rax
0x1800fdb4b  jz      loc_1800FDBD8
0x1800fdb51  or      edx, 0FFFFFFFFh; clrBk
0x1800fdb54  mov     rcx, rax; himl
0x1800fdb57  call    ImageList_SetBkColor
0x1800fdb5c  mov     r8, rbp; hbmMask
0x1800fdb5f  mov     rdx, r14; hbmImage
0x1800fdb62  mov     rcx, r15; himl
0x1800fdb65  call    ImageList_Add
0x1800fdb6a  mov     r12d, 2
0x1800fdb70  lea     r9, [rsp+0D8h+var_98]; struct tagTVITEMEXW *
0x1800fdb75  mov     r8d, r12d; unsigned int
0x1800fdb78  mov     rdx, rsi; struct _TREEITEM *
0x1800fdb7b  mov     rcx, rdi; struct _TREE *
0x1800fdb7e  call    ?TV_GetItem@@YAXPEAU_TREE@@PEAU_TREEITEM@@IPEAUtagTVITEMEXW@@@Z; TV_GetItem(_TREE *,_TREEITEM *,uint,tagTVITEMEXW *)
0x1800fdb83  mov     eax, [rdi+20h]
0x1800fdb86  movsx   ecx, word ptr [rdi+15Eh]
0x1800fdb8d  movzx   r8d, word ptr [rsi+34h]
0x1800fdb92  shr     eax, 0Fh
0x1800fdb95  and     r8d, 0F00h
0x1800fdb9c  and     eax, 80h
0x1800fdba1  or      r8d, eax
0x1800fdba4  movsx   eax, word ptr [rdi+166h]
0x1800fdbab  sub     eax, ecx
0x1800fdbad  mov     [rsp+0D8h+var_A8], r8d; int
0x1800fdbb2  cdq; int
0x1800fdbb3  xor     r8d, r8d; int
0x1800fdbb6  idiv    r12d
0x1800fdbb9  mov     rcx, r15; int
0x1800fdbbc  mov     r9d, eax; int
0x1800fdbbf  mov     eax, [rsp+0D8h+var_98.iImage]
0x1800fdbc3  mov     [rsp+0D8h+rop], eax; int
0x1800fdbc7  mov     rax, [rdi+0B0h]
0x1800fdbce  mov     [rsp+0D8h+lpBits], rax; himl
0x1800fdbd3  call    ImageList_CopyDitherImage
0x1800fdbd8  mov     rcx, rbx; ho
0x1800fdbdb  call    cs:__imp_DeleteObject
0x1800fdbe1  test    r14, r14
0x1800fdbe4  jz      short loc_1800FDBEF
0x1800fdbe6  mov     rcx, r14; ho
0x1800fdbe9  call    cs:__imp_DeleteObject
0x1800fdbef  test    rbp, rbp
0x1800fdbf2  jz      short loc_1800FDBFD
0x1800fdbf4  mov     rcx, rbp; ho
0x1800fdbf7  call    cs:__imp_DeleteObject
0x1800fdbfd  mov     rax, r15
0x1800fdc00  jmp     short loc_1800FDC04
0x1800fdc02  xor     eax, eax
0x1800fdc04  add     rsp, 98h
0x1800fdc0b  pop     r15
0x1800fdc0d  pop     r14
0x1800fdc0f  pop     r13
0x1800fdc11  pop     r12
0x1800fdc13  pop     rdi
0x1800fdc14  pop     rsi
0x1800fdc15  pop     rbp
0x1800fdc16  pop     rbx
0x1800fdc17  retn
```
