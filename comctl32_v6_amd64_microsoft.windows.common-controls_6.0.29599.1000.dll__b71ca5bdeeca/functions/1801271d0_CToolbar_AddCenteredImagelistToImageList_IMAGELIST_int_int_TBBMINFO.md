# CToolbar::_AddCenteredImagelistToImageList(_IMAGELIST *,int,int,TBBMINFO *)

- ea: `0x1801271d0`
- end: `0x18012740a`
- name: `?_AddCenteredImagelistToImageList@CToolbar@@AEAAHPEAU_IMAGELIST@@HHPEAUTBBMINFO@@@Z`
- size: `570`
- prototype: `int(CToolbar *__hidden this, struct _IMAGELIST *, int, int, struct TBBMINFO *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180045cd4`

## callees

- `0x18003bbd0`
- `0x1800b16b0`
- `0x1800bfc30`
- `0x1800bfd50`
- `0x180114520`
- `0x1801271d0`

## import_xrefs

- `GDI32!DeleteObject` at `0x1801273b8`
- `GDI32!DeleteObject` at `0x1801273b8`
- `GDI32!SelectObject` at `0x1801272f9`
- `GDI32!SelectObject` at `0x180127381`
- `GDI32!SelectObject` at `0x1801272f9`
- `GDI32!SelectObject` at `0x180127381`
- `GDI32!DeleteDC` at `0x1801273cf`
- `GDI32!DeleteDC` at `0x1801273cf`
- `GDI32!CreateCompatibleDC` at `0x180127232`
- `GDI32!CreateCompatibleDC` at `0x180127232`
- `GDI32!GetStockObject` at `0x18012731e`
- `GDI32!GetStockObject` at `0x18012731e`
- `GDI32!CreateDIBSection` at `0x1801272ca`
- `GDI32!CreateDIBSection` at `0x1801272ca`
- `USER32!FillRect` at `0x18012732e`
- `USER32!FillRect` at `0x18012732e`
- `USER32!GetDC` at `0x180127219`
- `USER32!GetDC` at `0x180127219`
- `USER32!ReleaseDC` at `0x1801273da`
- `USER32!ReleaseDC` at `0x1801273da`

## pseudocode

```c
__int64 __fastcall CToolbar::_AddCenteredImagelistToImageList(
        CToolbar *this,
        struct _IMAGELIST *a2,
        int a3,
        int a4,
        HINSTANCE *a5)
{
  CToolbar *v5; // rbx
  unsigned int v7; // r12d
  HDC DC; // rax
  HDC v9; // rsi
  HDC CompatibleDC; // r15
  struct _IMAGELIST *ImageW; // r13
  LONG v12; // eax
  HBITMAP v13; // rsi
  int v14; // eax
  HGDIOBJ v15; // rax
  void *v16; // rdi
  HBRUSH StockObject; // rax
  BOOL v18; // eax
  unsigned int v19; // ebx
  int i; // [rsp+40h] [rbp-61h]
  HDC v26; // [rsp+60h] [rbp-41h]
  void *ppvBits; // [rsp+68h] [rbp-39h] BYREF
  RECT h; // [rsp+70h] [rbp-31h] BYREF
  BITMAPINFO pbmi; // [rsp+80h] [rbp-21h] BYREF

  v5 = this;
  v7 = 0;
  DC = GetDC(0);
  v26 = DC;
  v9 = DC;
  if ( DC )
  {
    CompatibleDC = CreateCompatibleDC(DC);
    if ( CompatibleDC )
    {
      ImageW = ImageList_LoadImageW(a5[1], (LPCWSTR)*((unsigned __int16 *)a5 + 8), a3, 1, 0xFFFFFFFF, 0, 0x2040u);
      if ( ImageW )
      {
        v12 = *((_DWORD *)v5 + 59);
        memset(&pbmi.bmiHeader.biWidth, 0, 40);
        pbmi.bmiHeader.biWidth = v12;
        pbmi.bmiHeader.biHeight = *((_DWORD *)v5 + 60);
        ppvBits = 0;
        pbmi.bmiHeader.biSize = 40;
        *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
        *(_QWORD *)&h.left = CreateDIBSection(v9, &pbmi, 0, &ppvBits, 0, 0);
        if ( *(_QWORD *)&h.left )
        {
          v13 = *(HBITMAP *)&h.left;
          v7 = 1;
          v14 = 0;
          i = 0;
          do
          {
            if ( v14 >= *(_DWORD *)a5 )
              break;
            v15 = SelectObject(CompatibleDC, v13);
            *(_QWORD *)&h.left = 0;
            v16 = v15;
            h.right = *((_DWORD *)v5 + 59);
            h.bottom = *((_DWORD *)v5 + 60);
            StockObject = (HBRUSH)GetStockObject(0);
            FillRect(CompatibleDC, &h, StockObject);
            v18 = ImageList_Draw(
                    ImageW,
                    i,
                    CompatibleDC,
                    (*((_DWORD *)v5 + 59) - a3) / 2,
                    (*((_DWORD *)v5 + 60) - a4) / 2,
                    1u);
            v19 = 0;
            if ( v18 )
              v19 = v7;
            SelectObject(CompatibleDC, v16);
            v7 = 0;
            if ( ImageList_Add(a2, v13, 0) != -1 )
              v7 = v19;
            v5 = this;
            v14 = ++i;
          }
          while ( v7 );
          DeleteObject(v13);
          v9 = v26;
        }
        ImageList_DestroyPrivate(ImageW, 0);
      }
      DeleteDC(CompatibleDC);
    }
    ReleaseDC(0, v9);
  }
  return v7;
}

```

## disassembly

```asm
0x1801271d0  mov     [rsp-8+arg_18], rbx
0x1801271d5  push    rbp
0x1801271d6  push    rsi
0x1801271d7  push    rdi
0x1801271d8  push    r12
0x1801271da  push    r13
0x1801271dc  push    r14
0x1801271de  push    r15
0x1801271e0  lea     rbp, [rsp-1Fh]
0x1801271e5  sub     rsp, 0C0h
0x1801271ec  mov     rax, cs:__security_cookie
0x1801271f3  xor     rax, rsp
0x1801271f6  mov     [rbp+4Fh+var_40], rax
0x1801271fa  mov     r14, [rbp+4Fh+arg_20]
0x1801271fe  mov     rbx, rcx
0x180127201  mov     [rbp+4Fh+var_98], rcx
0x180127205  mov     edi, r8d
0x180127208  xor     ecx, ecx; hWnd
0x18012720a  mov     [rbp+4Fh+var_AC], r9d
0x18012720e  mov     [rbp+4Fh+var_A8], r8d
0x180127212  xor     r12d, r12d
0x180127215  mov     [rbp+4Fh+himl], rdx
0x180127219  call    cs:__imp_GetDC
0x18012721f  mov     [rbp+4Fh+var_90], rax
0x180127223  mov     rsi, rax
0x180127226  test    rax, rax
0x180127229  jz      loc_1801273E0
0x18012722f  mov     rcx, rax; hdc
0x180127232  call    cs:__imp_CreateCompatibleDC
0x180127238  mov     r15, rax
0x18012723b  test    rax, rax
0x18012723e  jz      loc_1801273D5
0x180127244  movzx   edx, word ptr [r14+10h]; lpbmp
0x180127249  lea     r9d, [r12+1]; cGrow
0x18012724e  mov     rcx, [r14+8]; hi
0x180127252  mov     r8d, edi; cx
0x180127255  mov     [rsp+0F0h+uFlags], 2040h; uFlags
0x18012725d  mov     [rsp+0F0h+uType], r12d; uType
0x180127262  mov     [rsp+0F0h+crMask], 0FFFFFFFFh; crMask
0x18012726a  call    ImageList_LoadImageW
0x18012726f  xor     edi, edi
0x180127271  mov     r13, rax
0x180127274  test    rax, rax
0x180127277  jz      loc_1801273CC
0x18012727d  xor     eax, eax
0x18012727f  mov     [rsp+0F0h+uType], edi; offset
0x180127283  xorps   xmm0, xmm0
0x180127286  mov     qword ptr [rbp+4Fh+pbmi.bmiHeader.biClrImportant], rax
0x18012728a  mov     eax, [rbx+0ECh]
0x180127290  lea     r9, [rbp+4Fh+ppvBits]; ppvBits
0x180127294  movups  xmmword ptr [rbp+4Fh+pbmi.bmiHeader.biWidth], xmm0
0x180127298  mov     [rbp+4Fh+pbmi.bmiHeader.biWidth], eax
0x18012729b  lea     rdx, [rbp+4Fh+pbmi]; pbmi
0x18012729f  mov     eax, [rbx+0F0h]
0x1801272a5  xor     r8d, r8d; usage
0x1801272a8  mov     rcx, rsi; hdc
0x1801272ab  mov     [rbp+4Fh+pbmi.bmiHeader.biHeight], eax
0x1801272ae  mov     [rbp+4Fh+ppvBits], rdi
0x1801272b2  movups  xmmword ptr [rbp+4Fh+pbmi.bmiHeader.biSizeImage], xmm0
0x1801272b6  mov     [rbp+4Fh+pbmi.bmiHeader.biSize], 28h ; '('
0x1801272bd  mov     qword ptr [rbp+4Fh+pbmi.bmiHeader.biPlanes], 200001h
0x1801272c5  mov     qword ptr [rsp+0F0h+crMask], rdi; hSection
0x1801272ca  call    cs:__imp_CreateDIBSection
0x1801272d0  mov     [rbp+4Fh+h], rax
0x1801272d4  test    rax, rax
0x1801272d7  jz      loc_1801273C2
0x1801272dd  mov     rsi, [rbp+4Fh+h]
0x1801272e1  lea     r12d, [rdi+1]
0x1801272e5  mov     eax, edi
0x1801272e7  mov     [rbp+4Fh+i], eax
0x1801272ea  cmp     eax, [r14]
0x1801272ed  jge     loc_1801273B5
0x1801272f3  mov     rdx, rsi; h
0x1801272f6  mov     rcx, r15; hdc
0x1801272f9  call    cs:__imp_SelectObject
0x1801272ff  xor     ecx, ecx; i
0x180127301  mov     [rbp+4Fh+h], 0
0x180127309  mov     rdi, rax
0x18012730c  mov     eax, [rbx+0ECh]
0x180127312  mov     [rbp+4Fh+var_78], eax
0x180127315  mov     eax, [rbx+0F0h]
0x18012731b  mov     [rbp+4Fh+var_74], eax
0x18012731e  call    cs:__imp_GetStockObject
0x180127324  lea     rdx, [rbp+4Fh+h]; lprc
0x180127328  mov     rcx, r15; hDC
0x18012732b  mov     r8, rax; hbr
0x18012732e  call    cs:__imp_FillRect
0x180127334  mov     eax, [rbx+0F0h]
0x18012733a  mov     r8d, 2
0x180127340  sub     eax, [rbp+4Fh+var_AC]
0x180127343  cdq
0x180127344  mov     [rsp+0F0h+uType], 1; fStyle
0x18012734c  idiv    r8d
0x18012734f  mov     ecx, eax
0x180127351  mov     eax, [rbx+0ECh]
0x180127357  sub     eax, [rbp+4Fh+var_A8]
0x18012735a  cdq
0x18012735b  mov     [rsp+0F0h+crMask], ecx; y
0x18012735f  idiv    r8d
0x180127362  mov     edx, [rbp+4Fh+i]; i
0x180127365  mov     r8, r15; hdcDst
0x180127368  mov     r9d, eax; x
0x18012736b  mov     rcx, r13; himl
0x18012736e  call    ImageList_Draw
0x180127373  xor     ebx, ebx
0x180127375  mov     rdx, rdi; h
0x180127378  test    eax, eax
0x18012737a  mov     rcx, r15; hdc
0x18012737d  cmovnz  ebx, r12d
0x180127381  call    cs:__imp_SelectObject
0x180127387  mov     rcx, [rbp+4Fh+himl]; himl
0x18012738b  xor     r8d, r8d; hbmMask
0x18012738e  mov     rdx, rsi; hbmImage
0x180127391  call    ImageList_Add
0x180127396  xor     r12d, r12d
0x180127399  cmp     eax, 0FFFFFFFFh
0x18012739c  mov     eax, [rbp+4Fh+i]
0x18012739f  cmovnz  r12d, ebx
0x1801273a3  mov     rbx, [rbp+4Fh+var_98]
0x1801273a7  inc     eax
0x1801273a9  mov     [rbp+4Fh+i], eax
0x1801273ac  test    r12d, r12d
0x1801273af  jnz     loc_1801272EA
0x1801273b5  mov     rcx, rsi; ho
0x1801273b8  call    cs:__imp_DeleteObject
0x1801273be  mov     rsi, [rbp+4Fh+var_90]
0x1801273c2  xor     edx, edx
0x1801273c4  mov     rcx, r13
0x1801273c7  call    ImageList_DestroyPrivate
0x1801273cc  mov     rcx, r15; hdc
0x1801273cf  call    cs:__imp_DeleteDC
0x1801273d5  mov     rdx, rsi; hDC
0x1801273d8  xor     ecx, ecx; hWnd
0x1801273da  call    cs:__imp_ReleaseDC
0x1801273e0  mov     eax, r12d
0x1801273e3  mov     rcx, [rbp+4Fh+var_40]
0x1801273e7  xor     rcx, rsp; StackCookie
0x1801273ea  call    __security_check_cookie
0x1801273ef  mov     rbx, [rsp+0F0h+arg_18]
0x1801273f7  add     rsp, 0C0h
0x1801273fe  pop     r15
0x180127400  pop     r14
0x180127402  pop     r13
0x180127404  pop     r12
0x180127406  pop     rdi
0x180127407  pop     rsi
0x180127408  pop     rbp
0x180127409  retn
```
