# CInfoPanel::RenderBorder(HDC__ *,tagRECT const *)

- ea: `0x18050bd08`
- end: `0x18050be9f`
- name: `?RenderBorder@CInfoPanel@@AEAAXPEAUHDC__@@PEBUtagRECT@@@Z`
- size: `407`
- prototype: `void(CInfoPanel *__hidden this, HDC, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18050b840`

## callees

- `0x18050bd08`

## import_xrefs

- `GDI32!DeleteObject` at `0x18050bddf`
- `GDI32!DeleteObject` at `0x18050be8e`
- `GDI32!DeleteObject` at `0x18050bddf`
- `GDI32!DeleteObject` at `0x18050be8e`
- `GDI32!SelectObject` at `0x18050bd57`
- `GDI32!SelectObject` at `0x18050be00`
- `GDI32!SelectObject` at `0x18050bd57`
- `GDI32!SelectObject` at `0x18050be00`
- `GDI32!MoveToEx` at `0x18050bd68`
- `GDI32!MoveToEx` at `0x18050bd92`
- `GDI32!MoveToEx` at `0x18050bdbe`
- `GDI32!MoveToEx` at `0x18050be12`
- `GDI32!MoveToEx` at `0x18050be3c`
- `GDI32!MoveToEx` at `0x18050be6d`
- `GDI32!MoveToEx` at `0x18050bd68`
- `GDI32!MoveToEx` at `0x18050bd92`
- `GDI32!MoveToEx` at `0x18050bdbe`
- `GDI32!MoveToEx` at `0x18050be12`
- `GDI32!MoveToEx` at `0x18050be3c`
- `GDI32!MoveToEx` at `0x18050be6d`
- `GDI32!LineTo` at `0x18050bd77`
- `GDI32!LineTo` at `0x18050bda5`
- `GDI32!LineTo` at `0x18050bdd1`
- `GDI32!LineTo` at `0x18050be25`
- `GDI32!LineTo` at `0x18050be53`
- `GDI32!LineTo` at `0x18050be80`
- `GDI32!LineTo` at `0x18050bd77`
- `GDI32!LineTo` at `0x18050bda5`
- `GDI32!LineTo` at `0x18050bdd1`
- `GDI32!LineTo` at `0x18050be25`
- `GDI32!LineTo` at `0x18050be53`
- `GDI32!LineTo` at `0x18050be80`
- `GDI32!CreatePen` at `0x18050bd43`
- `GDI32!CreatePen` at `0x18050bdec`
- `GDI32!CreatePen` at `0x18050bd43`
- `GDI32!CreatePen` at `0x18050bdec`
- `USER32!GetSysColor` at `0x18050bd34`
- `USER32!GetSysColor` at `0x18050bd34`

## pseudocode

```c
void __fastcall CInfoPanel::RenderBorder(CInfoPanel *this, HDC a2, const struct tagRECT *a3)
{
  COLORREF SysColor; // esi
  COLORREF v6; // r8d
  HPEN Pen; // rax
  HPEN v8; // rdi
  HPEN v9; // rax
  HPEN v10; // rdi

  if ( *((_DWORD *)this + 731) )
  {
    SysColor = GetSysColor(19);
    v6 = SysColor;
  }
  else
  {
    SysColor = 13146741;
    v6 = 5066061;
  }
  Pen = CreatePen(0, 0, v6);
  v8 = Pen;
  if ( Pen )
    SelectObject(a2, Pen);
  MoveToEx(a2, 0, 0, 0);
  LineTo(a2, 0, a3->bottom);
  MoveToEx(a2, 0, a3->bottom - 1, 0);
  LineTo(a2, a3->right, a3->bottom - 1);
  MoveToEx(a2, a3->right - 1, a3->bottom - 1, 0);
  LineTo(a2, a3->right - 1, -1);
  if ( v8 )
    DeleteObject(v8);
  v9 = CreatePen(0, 0, SysColor);
  v10 = v9;
  if ( v9 )
    SelectObject(a2, v9);
  MoveToEx(a2, 1, 0, 0);
  LineTo(a2, 1, a3->bottom - 1);
  MoveToEx(a2, 1, a3->bottom - 2, 0);
  LineTo(a2, a3->right - 1, a3->bottom - 2);
  MoveToEx(a2, a3->right - 2, a3->bottom - 2, 0);
  LineTo(a2, a3->right - 2, -1);
  if ( v10 )
    DeleteObject(v10);
}

```

## disassembly

```asm
0x18050bd08  push    rbx
0x18050bd0a  push    rbp
0x18050bd0b  push    rsi
0x18050bd0c  push    rdi
0x18050bd0d  push    r14
0x18050bd0f  sub     rsp, 20h
0x18050bd13  cmp     dword ptr [rcx+0B6Ch], 0
0x18050bd1a  mov     rbp, r8
0x18050bd1d  mov     rbx, rdx
0x18050bd20  jnz     short loc_18050BD2F
0x18050bd22  mov     esi, 0C89A75h
0x18050bd27  mov     r8d, 4D4D4Dh
0x18050bd2d  jmp     short loc_18050BD3F
0x18050bd2f  mov     ecx, 13h; nIndex
0x18050bd34  call    cs:__imp_GetSysColor
0x18050bd3a  mov     esi, eax
0x18050bd3c  mov     r8d, eax; color
0x18050bd3f  xor     edx, edx; cWidth
0x18050bd41  xor     ecx, ecx; iStyle
0x18050bd43  call    cs:__imp_CreatePen
0x18050bd49  mov     rdi, rax
0x18050bd4c  test    rax, rax
0x18050bd4f  jz      short loc_18050BD5D
0x18050bd51  mov     rdx, rax; h
0x18050bd54  mov     rcx, rbx; hdc
0x18050bd57  call    cs:__imp_SelectObject
0x18050bd5d  xor     r9d, r9d; lppt
0x18050bd60  xor     r8d, r8d; y
0x18050bd63  xor     edx, edx; x
0x18050bd65  mov     rcx, rbx; hdc
0x18050bd68  call    cs:__imp_MoveToEx
0x18050bd6e  mov     r8d, [rbp+0Ch]; y
0x18050bd72  xor     edx, edx; x
0x18050bd74  mov     rcx, rbx; hdc
0x18050bd77  call    cs:__imp_LineTo
0x18050bd7d  mov     r8d, [rbp+0Ch]
0x18050bd81  mov     r14d, 1
0x18050bd87  sub     r8d, r14d; y
0x18050bd8a  xor     r9d, r9d; lppt
0x18050bd8d  xor     edx, edx; x
0x18050bd8f  mov     rcx, rbx; hdc
0x18050bd92  call    cs:__imp_MoveToEx
0x18050bd98  mov     r8d, [rbp+0Ch]
0x18050bd9c  mov     rcx, rbx; hdc
0x18050bd9f  mov     edx, [rbp+8]; x
0x18050bda2  sub     r8d, r14d; y
0x18050bda5  call    cs:__imp_LineTo
0x18050bdab  mov     r8d, [rbp+0Ch]
0x18050bdaf  xor     r9d, r9d; lppt
0x18050bdb2  mov     edx, [rbp+8]
0x18050bdb5  sub     r8d, r14d; y
0x18050bdb8  sub     edx, r14d; x
0x18050bdbb  mov     rcx, rbx; hdc
0x18050bdbe  call    cs:__imp_MoveToEx
0x18050bdc4  mov     edx, [rbp+8]
0x18050bdc7  or      r8d, 0FFFFFFFFh; y
0x18050bdcb  sub     edx, r14d; x
0x18050bdce  mov     rcx, rbx; hdc
0x18050bdd1  call    cs:__imp_LineTo
0x18050bdd7  test    rdi, rdi
0x18050bdda  jz      short loc_18050BDE5
0x18050bddc  mov     rcx, rdi; ho
0x18050bddf  call    cs:__imp_DeleteObject
0x18050bde5  mov     r8d, esi; color
0x18050bde8  xor     edx, edx; cWidth
0x18050bdea  xor     ecx, ecx; iStyle
0x18050bdec  call    cs:__imp_CreatePen
0x18050bdf2  mov     rdi, rax
0x18050bdf5  test    rax, rax
0x18050bdf8  jz      short loc_18050BE06
0x18050bdfa  mov     rdx, rax; h
0x18050bdfd  mov     rcx, rbx; hdc
0x18050be00  call    cs:__imp_SelectObject
0x18050be06  xor     r9d, r9d; lppt
0x18050be09  xor     r8d, r8d; y
0x18050be0c  mov     edx, r14d; x
0x18050be0f  mov     rcx, rbx; hdc
0x18050be12  call    cs:__imp_MoveToEx
0x18050be18  mov     r8d, [rbp+0Ch]
0x18050be1c  mov     edx, r14d; x
0x18050be1f  sub     r8d, r14d; y
0x18050be22  mov     rcx, rbx; hdc
0x18050be25  call    cs:__imp_LineTo
0x18050be2b  mov     r8d, [rbp+0Ch]
0x18050be2f  xor     r9d, r9d; lppt
0x18050be32  sub     r8d, 2; y
0x18050be36  mov     edx, r14d; x
0x18050be39  mov     rcx, rbx; hdc
0x18050be3c  call    cs:__imp_MoveToEx
0x18050be42  mov     r8d, [rbp+0Ch]
0x18050be46  mov     rcx, rbx; hdc
0x18050be49  mov     edx, [rbp+8]
0x18050be4c  sub     r8d, 2; y
0x18050be50  sub     edx, r14d; x
0x18050be53  call    cs:__imp_LineTo
0x18050be59  mov     r8d, [rbp+0Ch]
0x18050be5d  xor     r9d, r9d; lppt
0x18050be60  mov     edx, [rbp+8]
0x18050be63  sub     r8d, 2; y
0x18050be67  sub     edx, 2; x
0x18050be6a  mov     rcx, rbx; hdc
0x18050be6d  call    cs:__imp_MoveToEx
0x18050be73  mov     edx, [rbp+8]
0x18050be76  or      r8d, 0FFFFFFFFh; y
0x18050be7a  sub     edx, 2; x
0x18050be7d  mov     rcx, rbx; hdc
0x18050be80  call    cs:__imp_LineTo
0x18050be86  test    rdi, rdi
0x18050be89  jz      short loc_18050BE94
0x18050be8b  mov     rcx, rdi; ho
0x18050be8e  call    cs:__imp_DeleteObject
0x18050be94  add     rsp, 20h
0x18050be98  pop     r14
0x18050be9a  pop     rdi
0x18050be9b  pop     rsi
0x18050be9c  pop     rbp
0x18050be9d  pop     rbx
0x18050be9e  retn
```
