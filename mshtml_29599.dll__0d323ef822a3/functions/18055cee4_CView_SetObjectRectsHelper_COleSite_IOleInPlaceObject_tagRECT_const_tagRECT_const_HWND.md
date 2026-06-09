# CView::SetObjectRectsHelper(COleSite *,IOleInPlaceObject *,tagRECT const *,tagRECT const *,HWND__ *)

- ea: `0x18055cee4`
- end: `0x18055d147`
- name: `?SetObjectRectsHelper@CView@@IEAAXPEAVCOleSite@@PEAUIOleInPlaceObject@@PEBUtagRECT@@2PEAUHWND__@@@Z`
- size: `611`
- prototype: `void __fastcall(CView *__hidden this, struct COleSite *, struct IOleInPlaceObject *, const struct tagRECT *, const struct tagRECT *, HWND hWnd)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18055cd54`
- `0x1806e3aa0`

## callees

- `0x180085fb4`
- `0x18055cee4`
- `0x18055d150`
- `0x1805c5a30`
- `0x180e2074c`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `GDI32!EqualRgn` at `0x18055d0e0`
- `GDI32!EqualRgn` at `0x18055d0e0`
- `GDI32!DeleteObject` at `0x18055d133`
- `GDI32!DeleteObject` at `0x18055d13c`
- `GDI32!DeleteObject` at `0x18055d133`
- `GDI32!DeleteObject` at `0x18055d13c`
- `GDI32!CreateRectRgnIndirect` at `0x18055cfcb`
- `GDI32!CreateRectRgnIndirect` at `0x18055d0ac`
- `GDI32!CreateRectRgnIndirect` at `0x18055cfcb`
- `GDI32!CreateRectRgnIndirect` at `0x18055d0ac`
- `GDI32!OffsetRgn` at `0x18055d080`
- `GDI32!OffsetRgn` at `0x18055d100`
- `GDI32!OffsetRgn` at `0x18055d080`
- `GDI32!OffsetRgn` at `0x18055d100`
- `GDI32!GetRgnBox` at `0x18055d0d4`
- `GDI32!GetRgnBox` at `0x18055d0d4`
- `USER32!GetWindowRgn` at `0x18055cfdf`
- `USER32!GetWindowRgn` at `0x18055d0c7`
- `USER32!GetWindowRgn` at `0x18055cfdf`
- `USER32!GetWindowRgn` at `0x18055d0c7`
- `USER32!SetWindowRgn` at `0x18055d10f`
- `USER32!SetWindowRgn` at `0x18055d10f`

## pseudocode

```c
void __fastcall CView::SetObjectRectsHelper(
        CView *this,
        struct COleSite *a2,
        const struct tagRECT *a3,
        const struct tagRECT *a4,
        const struct tagRECT *a5,
        HWND hWnd)
{
  HRGN v6; // rdi
  HRGN RectRgnIndirect; // rax
  int v12; // r12d
  int v13; // r13d
  int v14; // r14d
  __int64 v15; // r15
  __int64 v16; // rdx
  HRGN v17; // rcx
  int v18; // r8d
  HRGN v19; // rax
  HRGN v20; // rbx
  int v21; // [rsp+20h] [rbp-58h]
  __int128 v22; // [rsp+28h] [rbp-50h] BYREF
  __int128 v23; // [rsp+38h] [rbp-40h] BYREF
  struct tagRECT rc; // [rsp+48h] [rbp-30h] BYREF
  const struct tagRECT *v25; // [rsp+58h] [rbp-20h]
  __int64 v26; // [rsp+60h] [rbp-18h]

  v6 = 0;
  v22 = 0;
  v23 = 0;
  if ( hWnd )
  {
    RectRgnIndirect = CreateRectRgnIndirect(&g_Zero);
    v6 = RectRgnIndirect;
    if ( RectRgnIndirect )
      GetWindowRgn(hWnd, RectRgnIndirect);
    CView::GetHWNDRect(this, hWnd, (struct CRect *)&v22);
  }
  v26 = *((_QWORD *)this + 91);
  *(_QWORD *)&rc.left = this;
  *((_QWORD *)this + 91) = &rc;
  *(_QWORD *)&rc.right = 0;
  v25 = a3;
  COleSite::SetOleSiteRects(a2, a4, a3);
  if ( a3 )
    (*(void (__fastcall **)(const struct tagRECT *, const struct tagRECT *, const struct tagRECT *))(*(_QWORD *)&a3->left + 56LL))(
      a3,
      a4,
      a5);
  if ( *(_QWORD *)&rc.left )
    *(_QWORD *)(*(_QWORD *)&rc.left + 728LL) = v26;
  if ( !hWnd || (CView::GetHWNDRect(this, hWnd, (struct CRect *)&v23), !(unsigned __int8)CRect::operator!=(&v22, &v23)) )
  {
LABEL_7:
    if ( v6 )
      goto LABEL_28;
    return;
  }
  v12 = v22 - v23;
  v13 = DWORD1(v22) - DWORD1(v23);
  v14 = *((_DWORD *)this + 175) - 1;
  v21 = 0;
  if ( v14 < 0 )
    goto LABEL_21;
  v15 = v14;
  do
  {
    v16 = *((_QWORD *)this + 88);
    if ( hWnd != *(HWND *)(v16 + 40 * v15) )
      goto LABEL_18;
    v17 = *(HRGN *)(v16 + 40 * v15 + 8);
    v18 = 1;
    v21 = 1;
    if ( v17 )
    {
      OffsetRgn(v17, v12, v13);
LABEL_18:
      v18 = v21;
      goto LABEL_19;
    }
    *(_DWORD *)(v16 + 40 * v15 + 16) += v12;
    *(_DWORD *)(v16 + 40 * v15 + 20) += v13;
    *(_DWORD *)(v16 + 40 * v15 + 24) += v12;
    *(_DWORD *)(v16 + 40 * v15 + 28) += v13;
LABEL_19:
    --v15;
    --v14;
  }
  while ( v14 >= 0 );
  if ( v18 )
    goto LABEL_7;
LABEL_21:
  if ( v6 )
  {
    v19 = CreateRectRgnIndirect(&g_Zero);
    v20 = v19;
    if ( v19 )
    {
      rc = 0;
      GetWindowRgn(hWnd, v19);
      GetRgnBox(v20, &rc);
      if ( !EqualRgn(v6, v20) || CRect::IsRectEmpty((CRect *)&rc) )
      {
        DeleteObject(v20);
      }
      else
      {
        OffsetRgn(v20, v12, v13);
        SetWindowRgn(hWnd, v20, 0);
      }
    }
LABEL_28:
    DeleteObject(v6);
  }
}

```

## disassembly

```asm
0x18055cee4  mov     rax, rsp
0x18055cee7  mov     [rax+20h], r9
0x18055ceeb  mov     [rax+18h], r8
0x18055ceef  mov     [rax+10h], rdx
0x18055cef3  mov     [rax+8], rcx
0x18055cef7  push    rbp
0x18055cef8  push    rbx
0x18055cef9  push    rsi
0x18055cefa  push    rdi
0x18055cefb  push    r12
0x18055cefd  push    r13
0x18055ceff  push    r14
0x18055cf01  push    r15
0x18055cf03  mov     rbp, rsp
0x18055cf06  sub     rsp, 78h
0x18055cf0a  mov     rax, cs:__security_cookie
0x18055cf11  xor     rax, rsp
0x18055cf14  mov     [rbp+var_10], rax
0x18055cf18  mov     rsi, [rbp+hWnd]
0x18055cf1c  xor     edi, edi
0x18055cf1e  mov     rbx, [rbp+arg_0]
0x18055cf22  xorps   xmm0, xmm0
0x18055cf25  mov     r12, [rbp+arg_8]
0x18055cf29  xorps   xmm1, xmm1
0x18055cf2c  mov     r14, [rbp+arg_10]
0x18055cf30  mov     r15, [rbp+arg_18]
0x18055cf34  mov     r13, [rbp+arg_20]
0x18055cf38  movups  [rbp+var_50], xmm0
0x18055cf3c  movups  [rbp+var_40], xmm1
0x18055cf40  test    rsi, rsi
0x18055cf43  jnz     short loc_18055CFC4
0x18055cf45  mov     rax, [rbx+2D8h]
0x18055cf4c  mov     rdx, r15; struct tagRECT *
0x18055cf4f  mov     [rbp+var_18], rax
0x18055cf53  mov     rcx, r12; this
0x18055cf56  lea     rax, [rbp+rc]
0x18055cf5a  mov     qword ptr [rbp+rc.left], rbx
0x18055cf5e  mov     [rbx+2D8h], rax
0x18055cf65  mov     qword ptr [rbp+rc.right], 0
0x18055cf6d  mov     [rbp+var_20], r14
0x18055cf71  call    ?SetOleSiteRects@COleSite@@QEAAXPEBUtagRECT@@0@Z; COleSite::SetOleSiteRects(tagRECT const *,tagRECT const *)
0x18055cf76  test    r14, r14
0x18055cf79  jz      short loc_18055CF90
0x18055cf7b  mov     rax, [r14]
0x18055cf7e  mov     r8, r13
0x18055cf81  mov     rdx, r15
0x18055cf84  mov     rcx, r14
0x18055cf87  mov     rax, [rax+38h]
0x18055cf8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18055cf90  mov     rcx, qword ptr [rbp+rc.left]
0x18055cf94  test    rcx, rcx
0x18055cf97  jnz     short loc_18055CFF9
0x18055cf99  test    rsi, rsi
0x18055cf9c  jnz     short loc_18055D006
0x18055cf9e  test    rdi, rdi
0x18055cfa1  jnz     loc_18055D139
0x18055cfa7  mov     rcx, [rbp+var_10]
0x18055cfab  xor     rcx, rsp; StackCookie
0x18055cfae  call    __security_check_cookie
0x18055cfb3  add     rsp, 78h
0x18055cfb7  pop     r15
0x18055cfb9  pop     r14
0x18055cfbb  pop     r13
0x18055cfbd  pop     r12
0x18055cfbf  pop     rdi
0x18055cfc0  pop     rsi
0x18055cfc1  pop     rbx
0x18055cfc2  pop     rbp
0x18055cfc3  retn
0x18055cfc4  lea     rcx, ?g_Zero@@3TZERO_STRUCTS@@B; lprect
0x18055cfcb  call    cs:__imp_CreateRectRgnIndirect
0x18055cfd1  mov     rdi, rax
0x18055cfd4  test    rax, rax
0x18055cfd7  jz      short loc_18055CFE5
0x18055cfd9  mov     rdx, rax; hRgn
0x18055cfdc  mov     rcx, rsi; hWnd
0x18055cfdf  call    cs:__imp_GetWindowRgn
0x18055cfe5  lea     r8, [rbp+var_50]; struct CRect *
0x18055cfe9  mov     rdx, rsi; HWND
0x18055cfec  mov     rcx, rbx; this
0x18055cfef  call    ?GetHWNDRect@CView@@QEBAXPEAUHWND__@@PEAVCRect@@@Z; CView::GetHWNDRect(HWND__ *,CRect *)
0x18055cff4  jmp     loc_18055CF45
0x18055cff9  mov     rax, [rbp+var_18]
0x18055cffd  mov     [rcx+2D8h], rax
0x18055d004  jmp     short loc_18055CF99
0x18055d006  lea     r8, [rbp+var_40]; struct CRect *
0x18055d00a  mov     rdx, rsi; HWND
0x18055d00d  mov     rcx, rbx; this
0x18055d010  call    ?GetHWNDRect@CView@@QEBAXPEAUHWND__@@PEAVCRect@@@Z; CView::GetHWNDRect(HWND__ *,CRect *)
0x18055d015  lea     rdx, [rbp+var_40]
0x18055d019  lea     rcx, [rbp+var_50]
0x18055d01d  call    ??9CRect@@QEBA_NAEBUtagRECT@@@Z; CRect::operator!=(tagRECT const &)
0x18055d022  test    al, al
0x18055d024  jz      loc_18055CF9E
0x18055d02a  mov     r12d, dword ptr [rbp+var_50]
0x18055d02e  xor     r8d, r8d
0x18055d031  mov     r13d, dword ptr [rbp+var_50+4]
0x18055d035  sub     r12d, dword ptr [rbp+var_40]
0x18055d039  sub     r13d, dword ptr [rbp+var_40+4]
0x18055d03d  mov     r14d, [rbx+2BCh]
0x18055d044  sub     r14d, 1
0x18055d048  mov     [rbp+var_58], r8d
0x18055d04c  js      short loc_18055D09C
0x18055d04e  movsxd  r15, r14d
0x18055d051  mov     rdx, [rbx+2C0h]
0x18055d058  lea     rax, [r15+r15*4]
0x18055d05c  cmp     rsi, [rdx+rax*8]
0x18055d060  jnz     short loc_18055D086
0x18055d062  mov     rcx, [rdx+rax*8+8]; hrgn
0x18055d067  mov     r8d, 1
0x18055d06d  mov     [rbp+var_58], r8d
0x18055d071  test    rcx, rcx
0x18055d074  jz      loc_18055D117
0x18055d07a  mov     r8d, r13d; y
0x18055d07d  mov     edx, r12d; x
0x18055d080  call    cs:__imp_OffsetRgn
0x18055d086  mov     r8d, [rbp+var_58]
0x18055d08a  dec     r15
0x18055d08d  sub     r14d, 1
0x18055d091  jns     short loc_18055D051
0x18055d093  test    r8d, r8d
0x18055d096  jnz     loc_18055CF9E
0x18055d09c  test    rdi, rdi
0x18055d09f  jz      loc_18055CFA7
0x18055d0a5  lea     rcx, ?g_Zero@@3TZERO_STRUCTS@@B; lprect
0x18055d0ac  call    cs:__imp_CreateRectRgnIndirect
0x18055d0b2  mov     rbx, rax
0x18055d0b5  test    rax, rax
0x18055d0b8  jz      short loc_18055D139
0x18055d0ba  xorps   xmm0, xmm0
0x18055d0bd  mov     rdx, rax; hRgn
0x18055d0c0  mov     rcx, rsi; hWnd
0x18055d0c3  movups  xmmword ptr [rbp+rc.left], xmm0
0x18055d0c7  call    cs:__imp_GetWindowRgn
0x18055d0cd  lea     rdx, [rbp+rc]; lprc
0x18055d0d1  mov     rcx, rbx; hrgn
0x18055d0d4  call    cs:__imp_GetRgnBox
0x18055d0da  mov     rdx, rbx; hrgn2
0x18055d0dd  mov     rcx, rdi; hrgn1
0x18055d0e0  call    cs:__imp_EqualRgn
0x18055d0e6  test    eax, eax
0x18055d0e8  jz      short loc_18055D130
0x18055d0ea  lea     rcx, [rbp+rc]; this
0x18055d0ee  call    ?IsRectEmpty@CRect@@QEBA_NXZ; CRect::IsRectEmpty(void)
0x18055d0f3  test    al, al
0x18055d0f5  jnz     short loc_18055D130
0x18055d0f7  mov     r8d, r13d; y
0x18055d0fa  mov     edx, r12d; x
0x18055d0fd  mov     rcx, rbx; hrgn
0x18055d100  call    cs:__imp_OffsetRgn
0x18055d106  xor     r8d, r8d; bRedraw
0x18055d109  mov     rdx, rbx; hRgn
0x18055d10c  mov     rcx, rsi; hWnd
0x18055d10f  call    cs:__imp_SetWindowRgn
0x18055d115  jmp     short loc_18055D139
0x18055d117  add     [rdx+rax*8+10h], r12d
0x18055d11c  add     [rdx+rax*8+14h], r13d
0x18055d121  add     [rdx+rax*8+18h], r12d
0x18055d126  add     [rdx+rax*8+1Ch], r13d
0x18055d12b  jmp     loc_18055D08A
0x18055d130  mov     rcx, rbx; ho
0x18055d133  call    cs:__imp_DeleteObject
0x18055d139  mov     rcx, rdi; ho
0x18055d13c  call    cs:__imp_DeleteObject
0x18055d142  jmp     loc_18055CFA7
```
