# CUIFWindow::PaintObject(HDC__ *,tagRECT const *)

- ea: `0x1800719e0`
- end: `0x180071c0a`
- name: `?PaintObject@CUIFWindow@@UEAAXPEAUHDC__@@PEBUtagRECT@@@Z`
- size: `554`
- prototype: `void __fastcall(CUIFWindow *__hidden this, HDC hDC, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800719e0`
- `0x180071c10`
- `0x180071cd8`
- `0x180093454`
- `0x1800e3360`
- `0x180104958`
- `0x18010a010`

## import_xrefs

- `USER32!ReleaseDC` at `0x180071bf3`
- `USER32!ReleaseDC` at `0x180071bf3`
- `USER32!GetDC` at `0x180071a09`
- `USER32!GetDC` at `0x180071a09`
- `GDI32!DeleteObject` at `0x180071bb3`
- `GDI32!DeleteObject` at `0x180071bc1`
- `GDI32!DeleteObject` at `0x180071bb3`
- `GDI32!DeleteObject` at `0x180071bc1`
- `GDI32!CreateCompatibleDC` at `0x180071a24`
- `GDI32!CreateCompatibleDC` at `0x180071a24`
- `GDI32!DeleteDC` at `0x180071bde`
- `GDI32!DeleteDC` at `0x180071bde`
- `GDI32!SelectObject` at `0x180071a5e`
- `GDI32!SelectObject` at `0x180071b68`
- `GDI32!SelectObject` at `0x180071baa`
- `GDI32!SelectObject` at `0x180071a5e`
- `GDI32!SelectObject` at `0x180071b68`
- `GDI32!SelectObject` at `0x180071baa`
- `GDI32!SetViewportOrgEx` at `0x180071a78`
- `GDI32!SetViewportOrgEx` at `0x180071a78`
- `GDI32!BitBlt` at `0x180071b9e`
- `GDI32!BitBlt` at `0x180071b9e`
- `GDI32!CreateCompatibleBitmap` at `0x180071a46`
- `GDI32!CreateCompatibleBitmap` at `0x180071a46`

## pseudocode

```c
void __fastcall CUIFWindow::PaintObject(HWND *this, HDC hDC, const struct tagRECT *a3)
{
  int v3; // r12d
  HDC DC; // rbp
  HDC hdcSrc; // rsi
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v9; // r15
  HGDIOBJ v10; // r13
  HWND v11; // rdx
  HWND v12; // rcx
  int v13; // r9d
  HBITMAP v14; // r14
  __int64 i; // rcx
  unsigned int v16; // [rsp+50h] [rbp-68h] BYREF
  __int64 v17; // [rsp+58h] [rbp-60h]
  _BYTE v18[8]; // [rsp+60h] [rbp-58h] BYREF
  __int64 v19; // [rsp+68h] [rbp-50h]

  v3 = 0;
  DC = hDC;
  if ( !hDC )
  {
    DC = GetDC(this[21]);
    v3 = 1;
  }
  if ( !a3 )
    a3 = (const struct tagRECT *)(this + 11);
  hdcSrc = CreateCompatibleDC(DC);
  if ( hdcSrc )
  {
    CompatibleBitmap = CreateCompatibleBitmap(DC, a3->right - a3->left, a3->bottom - a3->top);
    v9 = CompatibleBitmap;
    if ( CompatibleBitmap )
    {
      v10 = SelectObject(hdcSrc, CompatibleBitmap);
      SetViewportOrgEx(hdcSrc, -a3->left, -a3->top, 0);
      if ( !this[3] && (int)CUIFTheme::InternalOpenThemeData((CUIFTheme *)this, v11) < 0
        || ((*((_BYTE *)this + 84) & 1) == 0
         || (*((int (__fastcall **)(HWND *, HWND, HDC, char *))*this + 1))(this, this[21], hdcSrc, (char *)this + 88) < 0)
        && (*(__int64 (__fastcall **)(HWND *, HDC, _QWORD, char *, _QWORD))*this)(
             this,
             hdcSrc,
             *((unsigned int *)this + 5),
             (char *)this + 88,
             0) < 0 )
      {
        v12 = this[6];
        if ( v12 )
          (*(void (__fastcall **)(HWND, HDC, const struct tagRECT *, __int64))(*(_QWORD *)v12 + 64LL))(
            v12,
            hdcSrc,
            a3,
            22);
      }
      v17 = 0;
      v19 = 0;
      CBitmapBits::SaveBits((CBitmapBits *)&v16, hdcSrc, v9);
      CUIFObject::PaintObject((CUIFObject *)this, hdcSrc, a3);
      v14 = 0;
      if ( v17 )
      {
        for ( i = 0; (unsigned int)i < v16; i = (unsigned int)(i + 1) )
        {
          if ( *(_BYTE *)(v17 + 4 * i + 3) )
          {
            v14 = CAlphaRestore::Restore((CAlphaRestore *)&v16, hdcSrc, v9, v13);
            break;
          }
        }
      }
      SelectObject(hdcSrc, v14);
      BitBlt(DC, a3->left, a3->top, a3->right - a3->left, a3->bottom - a3->top, hdcSrc, a3->left, a3->top, 0xCC0020u);
      SelectObject(hdcSrc, v10);
      DeleteObject(v9);
      if ( v14 )
        DeleteObject(v14);
      CBitmapBits::~CBitmapBits((CBitmapBits *)v18);
      CBitmapBits::~CBitmapBits((CBitmapBits *)&v16);
    }
    DeleteDC(hdcSrc);
    if ( v3 )
      ReleaseDC(this[21], DC);
  }
}

```

## disassembly

```asm
0x1800719e0  push    rbx
0x1800719e2  push    rbp
0x1800719e3  push    rsi
0x1800719e4  push    rdi
0x1800719e5  push    r12
0x1800719e7  push    r13
0x1800719e9  push    r14
0x1800719eb  push    r15
0x1800719ed  sub     rsp, 78h
0x1800719f1  xor     r12d, r12d
0x1800719f4  mov     rdi, r8
0x1800719f7  mov     rbp, rdx
0x1800719fa  mov     rbx, rcx
0x1800719fd  test    rdx, rdx
0x180071a00  jnz     short loc_180071A18
0x180071a02  mov     rcx, [rcx+0A8h]; hWnd
0x180071a09  call    cs:__imp_GetDC
0x180071a0f  mov     rbp, rax
0x180071a12  mov     r12d, 1
0x180071a18  test    rdi, rdi
0x180071a1b  jnz     short loc_180071A21
0x180071a1d  lea     rdi, [rbx+58h]
0x180071a21  mov     rcx, rbp; hdc
0x180071a24  call    cs:__imp_CreateCompatibleDC
0x180071a2a  mov     rsi, rax
0x180071a2d  test    rax, rax
0x180071a30  jz      loc_180071BF9
0x180071a36  mov     r8d, [rdi+0Ch]
0x180071a3a  mov     rcx, rbp; hdc
0x180071a3d  mov     edx, [rdi+8]
0x180071a40  sub     r8d, [rdi+4]; cy
0x180071a44  sub     edx, [rdi]; cx
0x180071a46  call    cs:__imp_CreateCompatibleBitmap
0x180071a4c  mov     r15, rax
0x180071a4f  test    rax, rax
0x180071a52  jz      loc_180071BDB
0x180071a58  mov     rdx, rax; h
0x180071a5b  mov     rcx, rsi; hdc
0x180071a5e  call    cs:__imp_SelectObject
0x180071a64  mov     r8d, [rdi+4]
0x180071a68  xor     r9d, r9d; lppt
0x180071a6b  mov     edx, [rdi]
0x180071a6d  neg     r8d; y
0x180071a70  neg     edx; x
0x180071a72  mov     rcx, rsi; hdc
0x180071a75  mov     r13, rax
0x180071a78  call    cs:__imp_SetViewportOrgEx
0x180071a7e  cmp     qword ptr [rbx+18h], 0
0x180071a83  jnz     short loc_180071A91
0x180071a85  mov     rcx, rbx; this
0x180071a88  call    ?InternalOpenThemeData@CUIFTheme@@QEAAJPEAUHWND__@@@Z; CUIFTheme::InternalOpenThemeData(HWND__ *)
0x180071a8d  test    eax, eax
0x180071a8f  js      short loc_180071ADE
0x180071a91  test    byte ptr [rbx+54h], 1
0x180071a95  jz      short loc_180071AB8
0x180071a97  mov     rax, [rbx]
0x180071a9a  lea     r9, [rbx+58h]
0x180071a9e  mov     rdx, [rbx+0A8h]
0x180071aa5  mov     r8, rsi
0x180071aa8  mov     rcx, rbx
0x180071aab  mov     rax, [rax+8]
0x180071aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071ab4  test    eax, eax
0x180071ab6  jns     short loc_180071AFF
0x180071ab8  mov     rax, [rbx]
0x180071abb  lea     r9, [rbx+58h]
0x180071abf  mov     r8d, [rbx+14h]
0x180071ac3  mov     rdx, rsi
0x180071ac6  mov     rcx, rbx
0x180071ac9  mov     qword ptr [rsp+0B8h+cy], 0
0x180071ad2  mov     rax, [rax]
0x180071ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071ada  test    eax, eax
0x180071adc  jns     short loc_180071AFF
0x180071ade  mov     rcx, [rbx+30h]
0x180071ae2  test    rcx, rcx
0x180071ae5  jz      short loc_180071AFF
0x180071ae7  mov     rax, [rcx]
0x180071aea  mov     r9d, 16h
0x180071af0  mov     r8, rdi
0x180071af3  mov     rdx, rsi
0x180071af6  mov     rax, [rax+40h]
0x180071afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071aff  mov     r8, r15; HBITMAP
0x180071b02  mov     [rsp+0B8h+var_60], 0
0x180071b0b  mov     rdx, rsi; HDC
0x180071b0e  mov     [rsp+0B8h+var_50], 0
0x180071b17  lea     rcx, [rsp+0B8h+var_68]; this
0x180071b1c  call    ?SaveBits@CBitmapBits@@QEAAHPEAUHDC__@@PEAUHBITMAP__@@@Z; CBitmapBits::SaveBits(HDC__ *,HBITMAP__ *)
0x180071b21  mov     r8, rdi; struct tagRECT *
0x180071b24  mov     rdx, rsi; HDC
0x180071b27  mov     rcx, rbx; this
0x180071b2a  call    ?PaintObject@CUIFObject@@UEAAXPEAUHDC__@@PEBUtagRECT@@@Z; CUIFObject::PaintObject(HDC__ *,tagRECT const *)
0x180071b2f  mov     rdx, [rsp+0B8h+var_60]
0x180071b34  xor     r14d, r14d
0x180071b37  test    rdx, rdx
0x180071b3a  jz      short loc_180071B62
0x180071b3c  xor     ecx, ecx
0x180071b3e  cmp     ecx, [rsp+0B8h+var_68]
0x180071b42  jnb     short loc_180071B62
0x180071b44  cmp     [rdx+rcx*4+3], r14b
0x180071b49  jnz     short loc_180071B4F
0x180071b4b  inc     ecx
0x180071b4d  jmp     short loc_180071B3E
0x180071b4f  mov     r8, r15; HBITMAP
0x180071b52  lea     rcx, [rsp+0B8h+var_68]; this
0x180071b57  mov     rdx, rsi; HDC
0x180071b5a  call    ?Restore@CAlphaRestore@@QEAAPEAUHBITMAP__@@PEAUHDC__@@PEAU2@H@Z; CAlphaRestore::Restore(HDC__ *,HBITMAP__ *,int)
0x180071b5f  mov     r14, rax
0x180071b62  mov     rdx, r14; h
0x180071b65  mov     rcx, rsi; hdc
0x180071b68  call    cs:__imp_SelectObject
0x180071b6e  mov     r8d, [rdi+4]; y
0x180071b72  mov     ecx, [rdi+0Ch]
0x180071b75  mov     edx, [rdi]; x
0x180071b77  sub     ecx, r8d
0x180071b7a  mov     r9d, [rdi+8]
0x180071b7e  mov     [rsp+0B8h+rop], 0CC0020h; rop
0x180071b86  sub     r9d, edx; cx
0x180071b89  mov     [rsp+0B8h+y1], r8d; y1
0x180071b8e  mov     [rsp+0B8h+x1], edx; x1
0x180071b92  mov     [rsp+0B8h+hdcSrc], rsi; hdcSrc
0x180071b97  mov     [rsp+0B8h+cy], ecx; cy
0x180071b9b  mov     rcx, rbp; hdc
0x180071b9e  call    cs:__imp_BitBlt
0x180071ba4  mov     rdx, r13; h
0x180071ba7  mov     rcx, rsi; hdc
0x180071baa  call    cs:__imp_SelectObject
0x180071bb0  mov     rcx, r15; ho
0x180071bb3  call    cs:__imp_DeleteObject
0x180071bb9  test    r14, r14
0x180071bbc  jz      short loc_180071BC7
0x180071bbe  mov     rcx, r14; ho
0x180071bc1  call    cs:__imp_DeleteObject
0x180071bc7  lea     rcx, [rsp+0B8h+var_58]; this
0x180071bcc  call    ??1CBitmapBits@@QEAA@XZ; CBitmapBits::~CBitmapBits(void)
0x180071bd1  lea     rcx, [rsp+0B8h+var_68]; this
0x180071bd6  call    ??1CBitmapBits@@QEAA@XZ; CBitmapBits::~CBitmapBits(void)
0x180071bdb  mov     rcx, rsi; hdc
0x180071bde  call    cs:__imp_DeleteDC
0x180071be4  test    r12d, r12d
0x180071be7  jz      short loc_180071BF9
0x180071be9  mov     rcx, [rbx+0A8h]; hWnd
0x180071bf0  mov     rdx, rbp; hDC
0x180071bf3  call    cs:__imp_ReleaseDC
0x180071bf9  add     rsp, 78h
0x180071bfd  pop     r15
0x180071bff  pop     r14
0x180071c01  pop     r13
0x180071c03  pop     r12
0x180071c05  pop     rdi
0x180071c06  pop     rsi
0x180071c07  pop     rbp
0x180071c08  pop     rbx
0x180071c09  retn
```
