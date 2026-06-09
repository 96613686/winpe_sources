# CUIFSchemeOfc10::DrawFrameCtrlBitmap(HDC__ *,tagRECT const *,HBITMAP__ *,HBITMAP__ *,ulong)

- ea: `0x1800dc740`
- end: `0x1800dcb58`
- name: `?DrawFrameCtrlBitmap@CUIFSchemeOfc10@@UEAAXPEAUHDC__@@PEBUtagRECT@@PEAUHBITMAP__@@2K@Z`
- size: `1048`
- prototype: `void(CUIFSchemeOfc10 *__hidden this, HDC, const struct tagRECT *, HBITMAP, HBITMAP, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800d9a94`
- `0x1800da020`
- `0x1800dc740`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `USER32!SetRect` at `0x1800dc877`
- `USER32!SetRect` at `0x1800dc877`
- `GDI32!DeleteObject` at `0x1800dca80`
- `GDI32!DeleteObject` at `0x1800dcb2e`
- `GDI32!DeleteObject` at `0x1800dca80`
- `GDI32!DeleteObject` at `0x1800dcb2e`
- `GDI32!CreateCompatibleDC` at `0x1800dc8ae`
- `GDI32!CreateCompatibleDC` at `0x1800dc8dd`
- `GDI32!CreateCompatibleDC` at `0x1800dc9ad`
- `GDI32!CreateCompatibleDC` at `0x1800dc8ae`
- `GDI32!CreateCompatibleDC` at `0x1800dc8dd`
- `GDI32!CreateCompatibleDC` at `0x1800dc9ad`
- `GDI32!DeleteDC` at `0x1800dca89`
- `GDI32!DeleteDC` at `0x1800dcac8`
- `GDI32!DeleteDC` at `0x1800dcadd`
- `GDI32!DeleteDC` at `0x1800dca89`
- `GDI32!DeleteDC` at `0x1800dcac8`
- `GDI32!DeleteDC` at `0x1800dcadd`
- `GDI32!SelectObject` at `0x1800dc8d1`
- `GDI32!SelectObject` at `0x1800dc90a`
- `GDI32!SelectObject` at `0x1800dc959`
- `GDI32!SelectObject` at `0x1800dc994`
- `GDI32!SelectObject` at `0x1800dc9a2`
- `GDI32!SelectObject` at `0x1800dc9d8`
- `GDI32!SelectObject` at `0x1800dca77`
- `GDI32!SelectObject` at `0x1800dcad4`
- `GDI32!SelectObject` at `0x1800dc8d1`
- `GDI32!SelectObject` at `0x1800dc90a`
- `GDI32!SelectObject` at `0x1800dc959`
- `GDI32!SelectObject` at `0x1800dc994`
- `GDI32!SelectObject` at `0x1800dc9a2`
- `GDI32!SelectObject` at `0x1800dc9d8`
- `GDI32!SelectObject` at `0x1800dca77`
- `GDI32!SelectObject` at `0x1800dcad4`
- `GDI32!CreateBitmap` at `0x1800dc9c9`
- `GDI32!CreateBitmap` at `0x1800dc9c9`
- `GDI32!SetBkColor` at `0x1800dc9e6`
- `GDI32!SetBkColor` at `0x1800dca2a`
- `GDI32!SetBkColor` at `0x1800dc9e6`
- `GDI32!SetBkColor` at `0x1800dca2a`
- `GDI32!SetTextColor` at `0x1800dca35`
- `GDI32!SetTextColor` at `0x1800dca35`
- `GDI32!BitBlt` at `0x1800dc93c`
- `GDI32!BitBlt` at `0x1800dc988`
- `GDI32!BitBlt` at `0x1800dca1c`
- `GDI32!BitBlt` at `0x1800dca6b`
- `GDI32!BitBlt` at `0x1800dcabf`
- `GDI32!BitBlt` at `0x1800dc93c`
- `GDI32!BitBlt` at `0x1800dc988`
- `GDI32!BitBlt` at `0x1800dca1c`
- `GDI32!BitBlt` at `0x1800dca6b`
- `GDI32!BitBlt` at `0x1800dcabf`
- `GDI32!CreateCompatibleBitmap` at `0x1800dc8c0`
- `GDI32!CreateCompatibleBitmap` at `0x1800dc8c0`

## pseudocode

```c
void __fastcall CUIFSchemeOfc10::DrawFrameCtrlBitmap(
        CUIFSchemeOfc10 *this,
        HDC a2,
        const struct tagRECT *a3,
        HBITMAP a4,
        HBITMAP a5,
        unsigned int a6)
{
  HDC v7; // rbp
  HBRUSH v9; // rbx
  HBRUSH v10; // rax
  HBITMAP DisabledBitmap; // rbx
  int v12; // esi
  int v13; // r13d
  unsigned int v14; // ebx
  HDC CompatibleDC; // r15
  HGDIOBJ v16; // r14
  HDC hdcSrc; // rbp
  void *v18; // rax
  HGDIOBJ v19; // rbx
  HDC v20; // rsi
  HBITMAP Bitmap; // rdi
  HGDIOBJ v22; // rbx
  unsigned __int64 yBottom; // [rsp+20h] [rbp-B8h]
  unsigned __int64 yBottoma; // [rsp+20h] [rbp-B8h]
  int nHeight; // [rsp+50h] [rbp-88h]
  unsigned int v26; // [rsp+54h] [rbp-84h]
  HBITMAP CompatibleBitmap; // [rsp+70h] [rbp-68h]
  struct tagRECT rc; // [rsp+78h] [rbp-60h] BYREF

  v7 = a2;
  if ( a5 )
  {
    v26 = (*(__int64 (__fastcall **)(CUIFSchemeOfc10 *, _QWORD))(*(_QWORD *)this + 224LL))(this, a6);
    if ( (a6 & 0x20) != 0 )
    {
      v9 = (HBRUSH)(*(__int64 (__fastcall **)(CUIFSchemeOfc10 *, __int64))(*(_QWORD *)this + 16LL))(this, 12);
      v10 = (HBRUSH)(*(__int64 (__fastcall **)(CUIFSchemeOfc10 *, _QWORD))(*(_QWORD *)this + 16LL))(this, v26);
      DisabledBitmap = CreateDisabledBitmap(a3, a5, v10, v9, 0);
    }
    else
    {
      v12 = a3->bottom - a3->top;
      v13 = a3->right - a3->left;
      nHeight = v12;
      rc = 0;
      SetRect(&rc, 0, 0, v13, v12);
      if ( (a6 & 0x11) == 0x11 || (a6 & 2) != 0 )
      {
        v14 = 8;
      }
      else if ( (a6 & 1) != 0 )
      {
        v14 = 5;
      }
      else
      {
        v14 = (a6 & 0x10) != 0 ? 5 : 10;
      }
      CompatibleDC = CreateCompatibleDC(v7);
      CompatibleBitmap = CreateCompatibleBitmap(v7, v13, v12);
      v16 = SelectObject(CompatibleDC, CompatibleBitmap);
      hdcSrc = CreateCompatibleDC(v7);
      (*(void (__fastcall **)(CUIFSchemeOfc10 *, HDC, struct tagRECT *, _QWORD))(*(_QWORD *)this + 64LL))(
        this,
        CompatibleDC,
        &rc,
        v26);
      SelectObject(hdcSrc, a5);
      BitBlt(CompatibleDC, 0, 0, v13, v12, hdcSrc, 0, 0, 0x8800C6u);
      v18 = (void *)(*(__int64 (__fastcall **)(CUIFSchemeOfc10 *, _QWORD))(*(_QWORD *)this + 16LL))(this, v14);
      v19 = SelectObject(CompatibleDC, v18);
      BitBlt(CompatibleDC, 0, 0, v13, v12, hdcSrc, 0, 0, 0xBA0B09u);
      SelectObject(CompatibleDC, v19);
      SelectObject(hdcSrc, a4);
      v20 = CreateCompatibleDC(a2);
      Bitmap = CreateBitmap(v13, nHeight, 1u, 1u, 0);
      v22 = SelectObject(v20, Bitmap);
      SetBkColor(hdcSrc, 0);
      BitBlt(v20, 0, 0, v13, nHeight, hdcSrc, 0, 0, 0xCC0020u);
      SetBkColor(CompatibleDC, 0xFFFFFFu);
      SetTextColor(CompatibleDC, 0);
      BitBlt(CompatibleDC, 0, 0, v13, nHeight, v20, 0, 0, 0x8800C6u);
      SelectObject(v20, v22);
      DeleteObject(Bitmap);
      DeleteDC(v20);
      BitBlt(CompatibleDC, 0, 0, v13, nHeight, hdcSrc, 0, 0, 0x660046u);
      DeleteDC(hdcSrc);
      SelectObject(CompatibleDC, v16);
      DeleteDC(CompatibleDC);
      v7 = a2;
      DisabledBitmap = CompatibleBitmap;
    }
    CUIDrawState(
      v7,
      0,
      (int (*)(HDC, __int64, unsigned __int64, int, int))(unsigned int)a3->left,
      (__int64)DisabledBitmap,
      yBottoma,
      a3->left,
      a3->top,
      a3->right - a3->left,
      a3->bottom - a3->top,
      4u);
    DeleteObject(DisabledBitmap);
  }
  else
  {
    CUIDrawState(
      a2,
      0,
      (int (*)(HDC, __int64, unsigned __int64, int, int))(unsigned int)a3->top,
      (__int64)a4,
      yBottom,
      a3->left,
      a3->top,
      a3->right - a3->left,
      a3->bottom - a3->top,
      (a6 & 0x20) != 0 ? 164 : 4);
  }
}

```

## disassembly

```asm
0x1800dc740  push    rbx
0x1800dc742  push    rbp
0x1800dc743  push    rsi
0x1800dc744  push    rdi
0x1800dc745  push    r12
0x1800dc747  push    r13
0x1800dc749  push    r14
0x1800dc74b  push    r15
0x1800dc74d  sub     rsp, 98h
0x1800dc754  mov     rax, cs:__security_cookie
0x1800dc75b  xor     rax, rsp
0x1800dc75e  mov     [rsp+0D8h+var_50], rax
0x1800dc766  mov     r14, [rsp+0D8h+arg_20]
0x1800dc76e  mov     r12, r8
0x1800dc771  mov     ebx, [rsp+0D8h+arg_28]
0x1800dc778  mov     rbp, rdx
0x1800dc77b  mov     esi, ebx
0x1800dc77d  mov     [rsp+0D8h+var_70], r9
0x1800dc782  and     esi, 20h
0x1800dc785  mov     [rsp+0D8h+hdc], rdx
0x1800dc78a  mov     [rsp+0D8h+h], r14
0x1800dc78f  mov     rdi, rcx
0x1800dc792  test    r14, r14
0x1800dc795  jnz     short loc_1800DC7E1
0x1800dc797  mov     ecx, [r12+0Ch]
0x1800dc79c  neg     esi
0x1800dc79e  mov     r8d, [r8+4]; int (*)(HDC, __int64, unsigned __int64, int, int)
0x1800dc7a2  mov     r10d, [r12]
0x1800dc7a6  sbb     edx, edx
0x1800dc7a8  mov     eax, [r12+8]
0x1800dc7ad  and     edx, 0A0h
0x1800dc7b3  add     edx, 4
0x1800dc7b6  sub     ecx, r8d
0x1800dc7b9  mov     [rsp+0D8h+var_90], edx; unsigned int
0x1800dc7bd  sub     eax, r10d
0x1800dc7c0  mov     [rsp+0D8h+rop], ecx; int
0x1800dc7c4  xor     edx, edx; hbrFore
0x1800dc7c6  mov     [rsp+0D8h+y1], eax; int
0x1800dc7ca  mov     rcx, rbp; hdc
0x1800dc7cd  mov     [rsp+0D8h+x1], r8d; int
0x1800dc7d2  mov     dword ptr [rsp+0D8h+hdcSrc], r10d; int
0x1800dc7d7  call    ?CUIDrawState@@YAHPEAUHDC__@@PEAUHBRUSH__@@P6AH0_J_KHH@Z23HHHHI@Z; CUIDrawState(HDC__ *,HBRUSH__ *,int (*)(HDC__ *,__int64,unsigned __int64,int,int),__int64,unsigned __int64,int,int,int,int,uint)
0x1800dc7dc  jmp     loc_1800DCB34
0x1800dc7e1  mov     rax, [rcx]
0x1800dc7e4  mov     edx, ebx
0x1800dc7e6  mov     rax, [rax+0E0h]
0x1800dc7ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc7f2  mov     [rsp+0D8h+var_84], eax
0x1800dc7f6  mov     r15d, eax
0x1800dc7f9  test    esi, esi
0x1800dc7fb  jz      short loc_1800DC847
0x1800dc7fd  mov     rdx, [rdi]
0x1800dc800  mov     rcx, rdi
0x1800dc803  mov     rax, [rdx+10h]
0x1800dc807  mov     edx, 0Ch
0x1800dc80c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc811  mov     r8, [rdi]
0x1800dc814  mov     rbx, rax
0x1800dc817  mov     edx, r15d
0x1800dc81a  mov     rcx, rdi
0x1800dc81d  mov     rax, [r8+10h]
0x1800dc821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc826  mov     r9, rbx; HBRUSH
0x1800dc829  mov     [rsp+0D8h+yBottom], 0; int
0x1800dc831  mov     r8, rax; HBRUSH
0x1800dc834  mov     rdx, r14; HBITMAP
0x1800dc837  mov     rcx, r12; struct tagRECT *
0x1800dc83a  call    ?CreateDisabledBitmap@@YAPEAUHBITMAP__@@PEBUtagRECT@@PEAU1@PEAUHBRUSH__@@2H@Z; CreateDisabledBitmap(tagRECT const *,HBITMAP__ *,HBRUSH__ *,HBRUSH__ *,int)
0x1800dc83f  mov     rbx, rax
0x1800dc842  jmp     loc_1800DCAED
0x1800dc847  mov     r13d, [r12+8]
0x1800dc84c  lea     rcx, [rsp+0D8h+rc]; lprc
0x1800dc851  mov     esi, [r12+0Ch]
0x1800dc856  xorps   xmm0, xmm0
0x1800dc859  sub     esi, [r12+4]
0x1800dc85e  xor     r8d, r8d; yTop
0x1800dc861  sub     r13d, [r12]
0x1800dc865  xor     edx, edx; xLeft
0x1800dc867  mov     r9d, r13d; xRight
0x1800dc86a  mov     [rsp+0D8h+nHeight], esi
0x1800dc86e  movups  xmmword ptr [rsp+0D8h+rc.left], xmm0
0x1800dc873  mov     [rsp+0D8h+yBottom], esi; yBottom
0x1800dc877  call    cs:__imp_SetRect
0x1800dc87d  mov     eax, ebx
0x1800dc87f  and     eax, 11h
0x1800dc882  cmp     al, 11h
0x1800dc884  jz      short loc_1800DC88B
0x1800dc886  test    bl, 2
0x1800dc889  jz      short loc_1800DC892
0x1800dc88b  mov     ebx, 8
0x1800dc890  jmp     short loc_1800DC8AB
0x1800dc892  test    bl, 1
0x1800dc895  jz      short loc_1800DC89E
0x1800dc897  mov     ebx, 5
0x1800dc89c  jmp     short loc_1800DC8AB
0x1800dc89e  and     bl, 10h
0x1800dc8a1  neg     bl
0x1800dc8a3  sbb     ebx, ebx
0x1800dc8a5  and     ebx, 0FFFFFFFBh
0x1800dc8a8  add     ebx, 0Ah
0x1800dc8ab  mov     rcx, rbp; hdc
0x1800dc8ae  call    cs:__imp_CreateCompatibleDC
0x1800dc8b4  mov     r8d, esi; cy
0x1800dc8b7  mov     edx, r13d; cx
0x1800dc8ba  mov     rcx, rbp; hdc
0x1800dc8bd  mov     r15, rax
0x1800dc8c0  call    cs:__imp_CreateCompatibleBitmap
0x1800dc8c6  mov     rdx, rax; h
0x1800dc8c9  mov     [rsp+0D8h+var_68], rax
0x1800dc8ce  mov     rcx, r15; hdc
0x1800dc8d1  call    cs:__imp_SelectObject
0x1800dc8d7  mov     rcx, rbp; hdc
0x1800dc8da  mov     r14, rax
0x1800dc8dd  call    cs:__imp_CreateCompatibleDC
0x1800dc8e3  mov     rcx, [rdi]
0x1800dc8e6  lea     r8, [rsp+0D8h+rc]
0x1800dc8eb  mov     r9d, [rsp+0D8h+var_84]
0x1800dc8f0  mov     rbp, rax
0x1800dc8f3  mov     rdx, r15
0x1800dc8f6  mov     rax, [rcx+40h]
0x1800dc8fa  mov     rcx, rdi
0x1800dc8fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc902  mov     rdx, [rsp+0D8h+h]; h
0x1800dc907  mov     rcx, rbp; hdc
0x1800dc90a  call    cs:__imp_SelectObject
0x1800dc910  mov     [rsp+0D8h+rop], 8800C6h; rop
0x1800dc918  mov     r9d, r13d; cx
0x1800dc91b  mov     [rsp+0D8h+y1], 0; y1
0x1800dc923  xor     r8d, r8d; y
0x1800dc926  mov     [rsp+0D8h+x1], 0; x1
0x1800dc92e  xor     edx, edx; x
0x1800dc930  mov     [rsp+0D8h+hdcSrc], rbp; hdcSrc
0x1800dc935  mov     rcx, r15; hdc
0x1800dc938  mov     [rsp+0D8h+yBottom], esi; cy
0x1800dc93c  call    cs:__imp_BitBlt
0x1800dc942  mov     rax, [rdi]
0x1800dc945  mov     edx, ebx
0x1800dc947  mov     rcx, rdi
0x1800dc94a  mov     rax, [rax+10h]
0x1800dc94e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc953  mov     rdx, rax; h
0x1800dc956  mov     rcx, r15; hdc
0x1800dc959  call    cs:__imp_SelectObject
0x1800dc95f  mov     [rsp+0D8h+rop], 0BA0B09h; rop
0x1800dc967  xor     edi, edi
0x1800dc969  mov     [rsp+0D8h+y1], edi; y1
0x1800dc96d  mov     r9d, r13d; cx
0x1800dc970  mov     [rsp+0D8h+x1], edi; x1
0x1800dc974  xor     r8d, r8d; y
0x1800dc977  mov     [rsp+0D8h+hdcSrc], rbp; hdcSrc
0x1800dc97c  xor     edx, edx; x
0x1800dc97e  mov     rcx, r15; hdc
0x1800dc981  mov     [rsp+0D8h+yBottom], esi; cy
0x1800dc985  mov     rbx, rax
0x1800dc988  call    cs:__imp_BitBlt
0x1800dc98e  mov     rdx, rbx; h
0x1800dc991  mov     rcx, r15; hdc
0x1800dc994  call    cs:__imp_SelectObject
0x1800dc99a  mov     rdx, [rsp+0D8h+var_70]; h
0x1800dc99f  mov     rcx, rbp; hdc
0x1800dc9a2  call    cs:__imp_SelectObject
0x1800dc9a8  mov     rcx, [rsp+0D8h+hdc]; hdc
0x1800dc9ad  call    cs:__imp_CreateCompatibleDC
0x1800dc9b3  mov     edx, [rsp+0D8h+nHeight]; nHeight
0x1800dc9b7  lea     r8d, [rdi+1]; nPlanes
0x1800dc9bb  mov     r9d, r8d; nBitCount
0x1800dc9be  mov     qword ptr [rsp+0D8h+yBottom], rdi; lpBits
0x1800dc9c3  mov     ecx, r13d; nWidth
0x1800dc9c6  mov     rsi, rax
0x1800dc9c9  call    cs:__imp_CreateBitmap
0x1800dc9cf  mov     rdx, rax; h
0x1800dc9d2  mov     rcx, rsi; hdc
0x1800dc9d5  mov     rdi, rax
0x1800dc9d8  call    cs:__imp_SelectObject
0x1800dc9de  xor     edx, edx; color
0x1800dc9e0  mov     rcx, rbp; hdc
0x1800dc9e3  mov     rbx, rax
0x1800dc9e6  call    cs:__imp_SetBkColor
0x1800dc9ec  mov     [rsp+0D8h+rop], 0CC0020h; rop
0x1800dc9f4  mov     [rsp+0D8h+y1], 0; y1
0x1800dc9fc  mov     [rsp+0D8h+x1], 0; x1
0x1800dca04  mov     eax, [rsp+0D8h+nHeight]
0x1800dca08  mov     r9d, r13d; cx
0x1800dca0b  mov     [rsp+0D8h+hdcSrc], rbp; hdcSrc
0x1800dca10  xor     r8d, r8d; y
0x1800dca13  xor     edx, edx; x
0x1800dca15  mov     [rsp+0D8h+yBottom], eax; cy
0x1800dca19  mov     rcx, rsi; hdc
0x1800dca1c  call    cs:__imp_BitBlt
0x1800dca22  mov     edx, 0FFFFFFh; color
0x1800dca27  mov     rcx, r15; hdc
0x1800dca2a  call    cs:__imp_SetBkColor
0x1800dca30  xor     edx, edx; color
0x1800dca32  mov     rcx, r15; hdc
0x1800dca35  call    cs:__imp_SetTextColor
0x1800dca3b  mov     eax, [rsp+0D8h+nHeight]
0x1800dca3f  mov     r9d, r13d; cx
0x1800dca42  mov     [rsp+0D8h+rop], 8800C6h; rop
0x1800dca4a  xor     r8d, r8d; y
0x1800dca4d  mov     [rsp+0D8h+y1], 0; y1
0x1800dca55  xor     edx, edx; x
0x1800dca57  mov     [rsp+0D8h+x1], 0; x1
0x1800dca5f  mov     rcx, r15; hdc
0x1800dca62  mov     [rsp+0D8h+hdcSrc], rsi; hdcSrc
0x1800dca67  mov     [rsp+0D8h+yBottom], eax; cy
0x1800dca6b  call    cs:__imp_BitBlt
0x1800dca71  mov     rdx, rbx; h
0x1800dca74  mov     rcx, rsi; hdc
0x1800dca77  call    cs:__imp_SelectObject
0x1800dca7d  mov     rcx, rdi; ho
0x1800dca80  call    cs:__imp_DeleteObject
0x1800dca86  mov     rcx, rsi; hdc
0x1800dca89  call    cs:__imp_DeleteDC
0x1800dca8f  mov     eax, [rsp+0D8h+nHeight]
0x1800dca93  mov     r9d, r13d; cx
0x1800dca96  mov     [rsp+0D8h+rop], 660046h; rop
0x1800dca9e  xor     r8d, r8d; y
0x1800dcaa1  mov     [rsp+0D8h+y1], 0; y1
0x1800dcaa9  xor     edx, edx; x
0x1800dcaab  mov     [rsp+0D8h+x1], 0; x1
0x1800dcab3  mov     rcx, r15; hdc
0x1800dcab6  mov     [rsp+0D8h+hdcSrc], rbp; hdcSrc
0x1800dcabb  mov     [rsp+0D8h+yBottom], eax; unsigned __int64
0x1800dcabf  call    cs:__imp_BitBlt
0x1800dcac5  mov     rcx, rbp; hdc
0x1800dcac8  call    cs:__imp_DeleteDC
0x1800dcace  mov     rdx, r14; h
0x1800dcad1  mov     rcx, r15; hdc
0x1800dcad4  call    cs:__imp_SelectObject
0x1800dcada  mov     rcx, r15; hdc
0x1800dcadd  call    cs:__imp_DeleteDC
0x1800dcae3  mov     rbp, [rsp+0D8h+hdc]
0x1800dcae8  mov     rbx, [rsp+0D8h+var_68]
0x1800dcaed  mov     edx, [r12+4]
0x1800dcaf2  mov     r9, rbx; __int64
0x1800dcaf5  mov     ecx, [r12+0Ch]
0x1800dcafa  mov     r8d, [r12]; int (*)(HDC, __int64, unsigned __int64, int, int)
0x1800dcafe  sub     ecx, edx
0x1800dcb00  mov     eax, [r12+8]
0x1800dcb05  mov     [rsp+0D8h+var_90], 4; unsigned int
0x1800dcb0d  sub     eax, r8d
0x1800dcb10  mov     [rsp+0D8h+rop], ecx; int
0x1800dcb14  mov     rcx, rbp; hdc
0x1800dcb17  mov     [rsp+0D8h+y1], eax; int
0x1800dcb1b  mov     [rsp+0D8h+x1], edx; int
0x1800dcb1f  xor     edx, edx; hbrFore
0x1800dcb21  mov     dword ptr [rsp+0D8h+hdcSrc], r8d; int
0x1800dcb26  call    ?CUIDrawState@@YAHPEAUHDC__@@PEAUHBRUSH__@@P6AH0_J_KHH@Z23HHHHI@Z; CUIDrawState(HDC__ *,HBRUSH__ *,int (*)(HDC__ *,__int64,unsigned __int64,int,int),__int64,unsigned __int64,int,int,int,int,uint)
0x1800dcb2b  mov     rcx, rbx; ho
0x1800dcb2e  call    cs:__imp_DeleteObject
0x1800dcb34  mov     rcx, [rsp+0D8h+var_50]
0x1800dcb3c  xor     rcx, rsp; StackCookie
0x1800dcb3f  call    __security_check_cookie
0x1800dcb44  add     rsp, 98h
0x1800dcb4b  pop     r15
0x1800dcb4d  pop     r14
0x1800dcb4f  pop     r13
0x1800dcb51  pop     r12
0x1800dcb53  pop     rdi
0x1800dcb54  pop     rsi
0x1800dcb55  pop     rbp
0x1800dcb56  pop     rbx
0x1800dcb57  retn
```
