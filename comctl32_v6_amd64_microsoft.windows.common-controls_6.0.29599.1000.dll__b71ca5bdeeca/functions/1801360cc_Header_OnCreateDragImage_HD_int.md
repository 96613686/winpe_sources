# Header_OnCreateDragImage(HD *,int)

- ea: `0x1801360cc`
- end: `0x18013642d`
- name: `?Header_OnCreateDragImage@@YAPEAU_IMAGELIST@@PEAUHD@@H@Z`
- size: `865`
- prototype: `struct _IMAGELIST *__fastcall(struct HD *, int)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800089d0`
- `0x1801372b0`

## callees

- `0x180009d38`
- `0x180009d9c`
- `0x180012230`
- `0x180027a2c`
- `0x1800286c0`
- `0x18003bbd0`
- `0x18008d2d0`
- `0x1800bfd50`
- `0x1800bfe10`
- `0x180114520`
- `0x18011f01c`
- `0x18012a628`
- `0x1801360cc`

## import_xrefs

- `GDI32!DeleteObject` at `0x1801363e4`
- `GDI32!DeleteObject` at `0x1801363f2`
- `GDI32!DeleteObject` at `0x180136400`
- `GDI32!DeleteObject` at `0x1801363e4`
- `GDI32!DeleteObject` at `0x1801363f2`
- `GDI32!DeleteObject` at `0x180136400`
- `GDI32!SetBkColor` at `0x18013622f`
- `GDI32!SetBkColor` at `0x1801362fb`
- `GDI32!SetBkColor` at `0x18013622f`
- `GDI32!SetBkColor` at `0x1801362fb`
- `GDI32!SetTextColor` at `0x180136219`
- `GDI32!SetTextColor` at `0x1801362e5`
- `GDI32!SetTextColor` at `0x180136219`
- `GDI32!SetTextColor` at `0x1801362e5`
- `GDI32!PatBlt` at `0x1801362a8`
- `GDI32!PatBlt` at `0x1801362a8`
- `GDI32!SelectObject` at `0x1801361b3`
- `GDI32!SelectObject` at `0x18013623b`
- `GDI32!SelectObject` at `0x180136287`
- `GDI32!SelectObject` at `0x1801362b4`
- `GDI32!SelectObject` at `0x180136307`
- `GDI32!SelectObject` at `0x18013636f`
- `GDI32!SelectObject` at `0x1801363ca`
- `GDI32!SelectObject` at `0x1801363db`
- `GDI32!SelectObject` at `0x1801361b3`
- `GDI32!SelectObject` at `0x18013623b`
- `GDI32!SelectObject` at `0x180136287`
- `GDI32!SelectObject` at `0x1801362b4`
- `GDI32!SelectObject` at `0x180136307`
- `GDI32!SelectObject` at `0x18013636f`
- `GDI32!SelectObject` at `0x1801363ca`
- `GDI32!SelectObject` at `0x1801363db`
- `GDI32!CreateCompatibleDC` at `0x18013613b`
- `GDI32!CreateCompatibleDC` at `0x18013613b`
- `GDI32!SetLayout` at `0x1801361a1`
- `GDI32!SetLayout` at `0x1801361a1`
- `GDI32!CreateBitmap` at `0x18013617a`
- `GDI32!CreateBitmap` at `0x18013617a`
- `USER32!OffsetRect` at `0x180136133`
- `USER32!OffsetRect` at `0x180136133`
- `USER32!GetSysColor` at `0x18013620e`
- `USER32!GetSysColor` at `0x180136224`
- `USER32!GetSysColor` at `0x1801362da`
- `USER32!GetSysColor` at `0x1801362f0`
- `USER32!GetSysColor` at `0x18013637a`
- `USER32!GetSysColor` at `0x18013620e`
- `USER32!GetSysColor` at `0x180136224`
- `USER32!GetSysColor` at `0x1801362da`
- `USER32!GetSysColor` at `0x1801362f0`
- `USER32!GetSysColor` at `0x18013637a`
- `USER32!DrawEdge` at `0x18013634f`
- `USER32!DrawEdge` at `0x18013634f`

## pseudocode

```c
struct _IMAGELIST *__fastcall Header_OnCreateDragImage(struct HD *a1, int a2)
{
  int v2; // r12d
  struct _IMAGELIST *v4; // r15
  HDC CompatibleDC; // rbx
  HBITMAP Bitmap; // rdi
  HBITMAP ColorBitmap; // r14
  HGDIOBJ v8; // rsi
  void *v9; // rdx
  HGDIOBJ v10; // r12
  COLORREF SysColor; // eax
  COLORREF v12; // eax
  HGDIOBJ v13; // r12
  COLORREF v14; // eax
  COLORREF v15; // eax
  COLORREF v16; // eax
  struct _IMAGELIST *v17; // r13
  int v18; // edx
  int v20; // [rsp+40h] [rbp-30h]
  int v22; // [rsp+48h] [rbp-28h]
  struct _IMAGELIST *himl; // [rsp+50h] [rbp-20h]
  struct tagRECT rc; // [rsp+58h] [rbp-18h] BYREF

  v2 = *((_DWORD *)a1 + 8);
  rc = 0;
  v4 = 0;
  v20 = Header_ItemOrderToIndex(a1, a2);
  if ( Header_OnGetItemRect(a1, v20, &rc) )
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
          v22 = v2 & 0x400000;
          if ( (v2 & 0x400000) != 0 )
            SetLayout(CompatibleDC, 1u);
          v9 = (void *)*((_QWORD *)a1 + 11);
          if ( v9 )
            v8 = SelectObject(CompatibleDC, v9);
          himl = ImageList_Create(rc.right, rc.bottom, 1u, 1, 0);
          if ( himl )
          {
            v10 = 0;
            v4 = ImageList_Create(rc.right, rc.bottom, 1u, 1, 0);
            if ( v4 )
            {
              SysColor = GetSysColor(18);
              SetTextColor(CompatibleDC, SysColor);
              v12 = GetSysColor(16);
              SetBkColor(CompatibleDC, v12);
              v13 = SelectObject(CompatibleDC, ColorBitmap);
              Header_DrawItem(a1, CompatibleDC, a2, v20, &rc, 2, 0);
              if ( v22 )
                MirrorBitmapInDC(CompatibleDC, ColorBitmap);
              SelectObject(CompatibleDC, Bitmap);
              PatBlt(CompatibleDC, 0, 0, rc.right, rc.bottom, 0x42u);
              SelectObject(CompatibleDC, v13);
              ImageList_SetBkColor(himl, 0xFFFFFFFF);
              ImageList_Add(himl, ColorBitmap, Bitmap);
              v14 = GetSysColor(18);
              SetTextColor(CompatibleDC, v14);
              v15 = GetSysColor(16);
              SetBkColor(CompatibleDC, v15);
              v10 = SelectObject(CompatibleDC, ColorBitmap);
              Header_DrawItem(a1, CompatibleDC, a2, v20, &rc, 3, 0);
              DrawEdge(CompatibleDC, &rc, 9u, 0x400Fu);
              if ( v22 )
                MirrorBitmapInDC(CompatibleDC, ColorBitmap);
              SelectObject(CompatibleDC, v10);
              v16 = GetSysColor(16);
              ImageList_AddMasked(v4, ColorBitmap, v16);
              v17 = himl;
              ImageList_CopyDitherImage((int)v4, v18, 0, 0, himl, 0, 0);
            }
            else
            {
              v17 = himl;
            }
            ImageList_DestroyPrivate(v17, 0);
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
0x1801360cc  mov     [rsp-38h+arg_10], rbx
0x1801360d1  push    rbp
0x1801360d2  push    rsi
0x1801360d3  push    rdi
0x1801360d4  push    r12
0x1801360d6  push    r13
0x1801360d8  push    r14
0x1801360da  push    r15
0x1801360dc  mov     rbp, rsp
0x1801360df  sub     rsp, 70h
0x1801360e3  mov     rax, cs:__security_cookie
0x1801360ea  xor     rax, rsp
0x1801360ed  mov     [rbp+var_8], rax
0x1801360f1  mov     r12d, [rcx+20h]
0x1801360f5  xorps   xmm0, xmm0
0x1801360f8  movups  xmmword ptr [rbp+rc.left], xmm0
0x1801360fc  mov     [rbp+var_2C], edx
0x1801360ff  mov     r13, rcx
0x180136102  xor     r15d, r15d
0x180136105  call    ?Header_ItemOrderToIndex@@YAHPEAUHD@@H@Z; Header_ItemOrderToIndex(HD *,int)
0x18013610a  lea     r8, [rbp+rc]; struct tagRECT *
0x18013610e  mov     [rbp+var_30], eax
0x180136111  mov     edx, eax; int
0x180136113  mov     rcx, r13; struct HD *
0x180136116  call    ?Header_OnGetItemRect@@YAHPEAUHD@@HPEAUtagRECT@@@Z; Header_OnGetItemRect(HD *,int,tagRECT *)
0x18013611b  test    eax, eax
0x18013611d  jz      loc_180136406
0x180136123  mov     r8d, [rbp+rc.top]
0x180136127  lea     rcx, [rbp+rc]; lprc
0x18013612b  mov     edx, [rbp+rc.left]
0x18013612e  neg     r8d; dy
0x180136131  neg     edx; dx
0x180136133  call    cs:__imp_OffsetRect
0x180136139  xor     ecx, ecx; hdc
0x18013613b  call    cs:__imp_CreateCompatibleDC
0x180136141  mov     rbx, rax
0x180136144  test    rax, rax
0x180136147  jz      loc_180136406
0x18013614d  mov     edx, [rbp+rc.bottom]; cy
0x180136150  xor     edi, edi
0x180136152  mov     ecx, [rbp+rc.right]; cx
0x180136155  call    CreateColorBitmap
0x18013615a  mov     r14, rax
0x18013615d  test    rax, rax
0x180136160  jz      loc_1801363E1
0x180136166  mov     edx, [rbp+rc.bottom]; nHeight
0x180136169  lea     eax, [rdi+1]
0x18013616c  mov     ecx, [rbp+rc.right]; nWidth
0x18013616f  mov     r9d, eax; nBitCount
0x180136172  mov     r8d, eax; nPlanes
0x180136175  mov     [rsp+70h+lpBits], rdi; lpBits
0x18013617a  call    cs:__imp_CreateBitmap
0x180136180  mov     rdi, rax
0x180136183  test    rax, rax
0x180136186  jz      loc_1801363E1
0x18013618c  xor     esi, esi
0x18013618e  and     r12d, 400000h
0x180136195  mov     [rbp+var_28], r12d
0x180136199  jz      short loc_1801361A7
0x18013619b  lea     edx, [rsi+1]; l
0x18013619e  mov     rcx, rbx; hdc
0x1801361a1  call    cs:__imp_SetLayout
0x1801361a7  mov     rdx, [r13+58h]; h
0x1801361ab  test    rdx, rdx
0x1801361ae  jz      short loc_1801361BC
0x1801361b0  mov     rcx, rbx; hdc
0x1801361b3  call    cs:__imp_SelectObject
0x1801361b9  mov     rsi, rax
0x1801361bc  mov     edx, [rbp+rc.bottom]; cy
0x1801361bf  mov     r9d, 1; cInitial
0x1801361c5  mov     ecx, [rbp+rc.right]; cx
0x1801361c8  mov     r8d, r9d; flags
0x1801361cb  mov     dword ptr [rsp+70h+lpBits], r15d; cGrow
0x1801361d0  call    ImageList_Create
0x1801361d5  mov     [rbp+himl], rax
0x1801361d9  test    rax, rax
0x1801361dc  jz      loc_1801363D0
0x1801361e2  mov     edx, [rbp+rc.bottom]; cy
0x1801361e5  xor     r12d, r12d
0x1801361e8  mov     ecx, [rbp+rc.right]; cx
0x1801361eb  mov     dword ptr [rsp+70h+lpBits], r12d; cGrow
0x1801361f0  lea     r8d, [r12+1]; flags
0x1801361f5  mov     r9d, r8d; cInitial
0x1801361f8  call    ImageList_Create
0x1801361fd  mov     r15, rax
0x180136200  test    rax, rax
0x180136203  jz      loc_1801363B1
0x180136209  lea     ecx, [r12+12h]; nIndex
0x18013620e  call    cs:__imp_GetSysColor
0x180136214  mov     edx, eax; color
0x180136216  mov     rcx, rbx; hdc
0x180136219  call    cs:__imp_SetTextColor
0x18013621f  lea     ecx, [r12+10h]; nIndex
0x180136224  call    cs:__imp_GetSysColor
0x18013622a  mov     edx, eax; color
0x18013622c  mov     rcx, rbx; hdc
0x18013622f  call    cs:__imp_SetBkColor
0x180136235  mov     rdx, r14; h
0x180136238  mov     rcx, rbx; hdc
0x18013623b  call    cs:__imp_SelectObject
0x180136241  mov     r9d, [rbp+var_30]; int
0x180136245  mov     rdx, rbx; hdc
0x180136248  mov     r8d, [rbp+var_2C]; int
0x18013624c  mov     r12, rax
0x18013624f  lea     rax, [rbp+rc]
0x180136253  mov     [rsp+70h+var_40], 0; int
0x18013625b  mov     [rsp+70h+rop], 2; char
0x180136263  mov     rcx, r13; struct HD *
0x180136266  mov     [rsp+70h+lpBits], rax; lprect
0x18013626b  call    ?Header_DrawItem@@YAXPEAUHD@@PEAUHDC__@@HHPEBUtagRECT@@IH@Z; Header_DrawItem(HD *,HDC__ *,int,int,tagRECT const *,uint,int)
0x180136270  cmp     [rbp+var_28], 0
0x180136274  jz      short loc_180136281
0x180136276  mov     rdx, r14; h
0x180136279  mov     rcx, rbx; hdc
0x18013627c  call    MirrorBitmapInDC
0x180136281  mov     rdx, rdi; h
0x180136284  mov     rcx, rbx; hdc
0x180136287  call    cs:__imp_SelectObject
0x18013628d  mov     eax, [rbp+rc.bottom]
0x180136290  xor     r8d, r8d; y
0x180136293  mov     r9d, [rbp+rc.right]; w
0x180136297  xor     edx, edx; x
0x180136299  mov     rcx, rbx; hdc
0x18013629c  mov     [rsp+70h+rop], 42h ; 'B'; rop
0x1801362a4  mov     dword ptr [rsp+70h+lpBits], eax; h
0x1801362a8  call    cs:__imp_PatBlt
0x1801362ae  mov     rdx, r12; h
0x1801362b1  mov     rcx, rbx; hdc
0x1801362b4  call    cs:__imp_SelectObject
0x1801362ba  mov     rcx, [rbp+himl]; himl
0x1801362be  or      edx, 0FFFFFFFFh; clrBk
0x1801362c1  call    ImageList_SetBkColor
0x1801362c6  mov     rcx, [rbp+himl]; himl
0x1801362ca  mov     r8, rdi; hbmMask
0x1801362cd  mov     rdx, r14; hbmImage
0x1801362d0  call    ImageList_Add
0x1801362d5  mov     ecx, 12h; nIndex
0x1801362da  call    cs:__imp_GetSysColor
0x1801362e0  mov     edx, eax; color
0x1801362e2  mov     rcx, rbx; hdc
0x1801362e5  call    cs:__imp_SetTextColor
0x1801362eb  mov     ecx, 10h; nIndex
0x1801362f0  call    cs:__imp_GetSysColor
0x1801362f6  mov     edx, eax; color
0x1801362f8  mov     rcx, rbx; hdc
0x1801362fb  call    cs:__imp_SetBkColor
0x180136301  mov     rdx, r14; h
0x180136304  mov     rcx, rbx; hdc
0x180136307  call    cs:__imp_SelectObject
0x18013630d  mov     r9d, [rbp+var_30]; int
0x180136311  mov     rdx, rbx; hdc
0x180136314  mov     r8d, [rbp+var_2C]; int
0x180136318  mov     r12, rax
0x18013631b  lea     rax, [rbp+rc]
0x18013631f  mov     [rsp+70h+var_40], 0; int
0x180136327  mov     [rsp+70h+rop], 3; char
0x18013632f  mov     rcx, r13; struct HD *
0x180136332  mov     [rsp+70h+lpBits], rax; lprect
0x180136337  call    ?Header_DrawItem@@YAXPEAUHD@@PEAUHDC__@@HHPEBUtagRECT@@IH@Z; Header_DrawItem(HD *,HDC__ *,int,int,tagRECT const *,uint,int)
0x18013633c  mov     r9d, 400Fh; grfFlags
0x180136342  lea     rdx, [rbp+rc]; qrc
0x180136346  mov     r8d, 9; edge
0x18013634c  mov     rcx, rbx; hdc
0x18013634f  call    cs:__imp_DrawEdge
0x180136355  xor     r13d, r13d
0x180136358  cmp     [rbp+var_28], r13d
0x18013635c  jz      short loc_180136369
0x18013635e  mov     rdx, r14; h
0x180136361  mov     rcx, rbx; hdc
0x180136364  call    MirrorBitmapInDC
0x180136369  mov     rdx, r12; h
0x18013636c  mov     rcx, rbx; hdc
0x18013636f  call    cs:__imp_SelectObject
0x180136375  mov     ecx, 10h; nIndex
0x18013637a  call    cs:__imp_GetSysColor
0x180136380  mov     rdx, r14; hbmImage
0x180136383  mov     rcx, r15; himl
0x180136386  mov     r8d, eax; crMask
0x180136389  call    ImageList_AddMasked
0x18013638e  mov     [rsp+70h+var_40], r13d; int
0x180136393  xor     r9d, r9d; int
0x180136396  mov     [rsp+70h+rop], r13d; int
0x18013639b  xor     r8d, r8d; int
0x18013639e  mov     r13, [rbp+himl]
0x1801363a2  mov     rcx, r15; int
0x1801363a5  mov     [rsp+70h+lpBits], r13; himl
0x1801363aa  call    ImageList_CopyDitherImage
0x1801363af  jmp     short loc_1801363B5
0x1801363b1  mov     r13, [rbp+himl]
0x1801363b5  xor     edx, edx
0x1801363b7  mov     rcx, r13
0x1801363ba  call    ImageList_DestroyPrivate
0x1801363bf  test    r12, r12
0x1801363c2  jz      short loc_1801363D0
0x1801363c4  mov     rdx, r12; h
0x1801363c7  mov     rcx, rbx; hdc
0x1801363ca  call    cs:__imp_SelectObject
0x1801363d0  test    rsi, rsi
0x1801363d3  jz      short loc_1801363E1
0x1801363d5  mov     rdx, rsi; h
0x1801363d8  mov     rcx, rbx; hdc
0x1801363db  call    cs:__imp_SelectObject
0x1801363e1  mov     rcx, rbx; ho
0x1801363e4  call    cs:__imp_DeleteObject
0x1801363ea  test    r14, r14
0x1801363ed  jz      short loc_1801363F8
0x1801363ef  mov     rcx, r14; ho
0x1801363f2  call    cs:__imp_DeleteObject
0x1801363f8  test    rdi, rdi
0x1801363fb  jz      short loc_180136406
0x1801363fd  mov     rcx, rdi; ho
0x180136400  call    cs:__imp_DeleteObject
0x180136406  mov     rax, r15
0x180136409  mov     rcx, [rbp+var_8]
0x18013640d  xor     rcx, rsp; StackCookie
0x180136410  call    __security_check_cookie
0x180136415  mov     rbx, [rsp+70h+arg_10]
0x18013641d  add     rsp, 70h
0x180136421  pop     r15
0x180136423  pop     r14
0x180136425  pop     r13
0x180136427  pop     r12
0x180136429  pop     rdi
0x18013642a  pop     rsi
0x18013642b  pop     rbp
0x18013642c  retn
```
