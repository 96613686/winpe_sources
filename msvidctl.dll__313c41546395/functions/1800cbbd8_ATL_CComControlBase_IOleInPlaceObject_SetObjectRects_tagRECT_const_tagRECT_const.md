# ATL::CComControlBase::IOleInPlaceObject_SetObjectRects(tagRECT const *,tagRECT const *)

- ea: `0x1800cbbd8`
- end: `0x1800cbcd1`
- name: `?IOleInPlaceObject_SetObjectRects@CComControlBase@ATL@@QEAAJPEBUtagRECT@@0@Z`
- size: `249`
- prototype: `int(ATL::CComControlBase *__hidden this, const struct tagRECT *, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800d1f50`

## callees

- `0x180004640`
- `0x1800cbbd8`

## import_xrefs

- `USER32!OffsetRect` at `0x1800cbc58`
- `USER32!OffsetRect` at `0x1800cbc58`
- `USER32!SetWindowRgn` at `0x1800cbc7c`
- `USER32!SetWindowRgn` at `0x1800cbc7c`
- `USER32!SetWindowPos` at `0x1800cbcad`
- `USER32!SetWindowPos` at `0x1800cbcad`
- `USER32!EqualRect` at `0x1800cbc3e`
- `USER32!EqualRect` at `0x1800cbc3e`
- `USER32!IntersectRect` at `0x1800cbc2c`
- `USER32!IntersectRect` at `0x1800cbc2c`
- `GDI32!CreateRectRgnIndirect` at `0x1800cbc63`
- `GDI32!CreateRectRgnIndirect` at `0x1800cbc63`

## pseudocode

```c
__int64 __fastcall ATL::CComControlBase::IOleInPlaceObject_SetObjectRects(
        ATL::CComControlBase *this,
        const struct tagRECT *a2,
        const struct tagRECT *a3)
{
  _QWORD *v5; // rax
  HRGN v6; // rsi
  struct tagRECT rcDst; // [rsp+40h] [rbp-38h] BYREF

  if ( !a2 || !a3 )
    return 2147500035LL;
  v5 = (_QWORD *)*((_QWORD *)this + 11);
  *(struct tagRECT *)((char *)this + 72) = *a2;
  if ( *v5 )
  {
    rcDst = 0;
    v6 = 0;
    if ( IntersectRect(&rcDst, a2, a3) )
    {
      if ( !EqualRect(&rcDst, a2) )
      {
        OffsetRect(&rcDst, -a2->left, -a2->top);
        v6 = CreateRectRgnIndirect(&rcDst);
      }
    }
    SetWindowRgn(**((HWND **)this + 11), v6, 1);
    SetWindowPos(**((HWND **)this + 11), 0, a2->left, a2->top, a2->right - a2->left, a2->bottom - a2->top, 0x14u);
  }
  return 0;
}

```

## disassembly

```asm
0x1800cbbd8  push    rbx
0x1800cbbda  push    rsi
0x1800cbbdb  push    rdi
0x1800cbbdc  sub     rsp, 60h
0x1800cbbe0  mov     rax, cs:__security_cookie
0x1800cbbe7  xor     rax, rsp
0x1800cbbea  mov     [rsp+78h+var_28], rax
0x1800cbbef  mov     rbx, rdx
0x1800cbbf2  mov     rdi, rcx
0x1800cbbf5  test    rdx, rdx
0x1800cbbf8  jz      loc_1800CBCB7
0x1800cbbfe  test    r8, r8
0x1800cbc01  jz      loc_1800CBCB7
0x1800cbc07  movups  xmm0, xmmword ptr [rdx]
0x1800cbc0a  mov     rax, [rcx+58h]
0x1800cbc0e  movdqu  xmmword ptr [rcx+48h], xmm0
0x1800cbc13  cmp     qword ptr [rax], 0
0x1800cbc17  jz      loc_1800CBCB3
0x1800cbc1d  xorps   xmm0, xmm0
0x1800cbc20  lea     rcx, [rsp+78h+rcDst]; lprcDst
0x1800cbc25  movups  xmmword ptr [rsp+78h+rcDst.left], xmm0
0x1800cbc2a  xor     esi, esi
0x1800cbc2c  call    cs:__imp_IntersectRect
0x1800cbc32  test    eax, eax
0x1800cbc34  jz      short loc_1800CBC6C
0x1800cbc36  mov     rdx, rbx; lprc2
0x1800cbc39  lea     rcx, [rsp+78h+rcDst]; lprc1
0x1800cbc3e  call    cs:__imp_EqualRect
0x1800cbc44  test    eax, eax
0x1800cbc46  jnz     short loc_1800CBC6C
0x1800cbc48  mov     r8d, [rbx+4]
0x1800cbc4c  lea     rcx, [rsp+78h+rcDst]; lprc
0x1800cbc51  mov     edx, [rbx]
0x1800cbc53  neg     r8d; dy
0x1800cbc56  neg     edx; dx
0x1800cbc58  call    cs:__imp_OffsetRect
0x1800cbc5e  lea     rcx, [rsp+78h+rcDst]; lprect
0x1800cbc63  call    cs:__imp_CreateRectRgnIndirect
0x1800cbc69  mov     rsi, rax
0x1800cbc6c  mov     rcx, [rdi+58h]
0x1800cbc70  mov     r8d, 1; bRedraw
0x1800cbc76  mov     rdx, rsi; hRgn
0x1800cbc79  mov     rcx, [rcx]; hWnd
0x1800cbc7c  call    cs:__imp_SetWindowRgn
0x1800cbc82  mov     edx, [rbx+0Ch]
0x1800cbc85  mov     rcx, [rdi+58h]
0x1800cbc89  mov     r9d, [rbx+4]; Y
0x1800cbc8d  sub     edx, r9d
0x1800cbc90  mov     eax, [rbx+8]
0x1800cbc93  sub     eax, [rbx]
0x1800cbc95  mov     rcx, [rcx]; hWnd
0x1800cbc98  mov     r8d, [rbx]; X
0x1800cbc9b  mov     [rsp+78h+uFlags], 14h; uFlags
0x1800cbca3  mov     [rsp+78h+cy], edx; cy
0x1800cbca7  xor     edx, edx; hWndInsertAfter
0x1800cbca9  mov     [rsp+78h+var_58], eax; cx
0x1800cbcad  call    cs:__imp_SetWindowPos
0x1800cbcb3  xor     eax, eax
0x1800cbcb5  jmp     short loc_1800CBCBC
0x1800cbcb7  mov     eax, 80004003h
0x1800cbcbc  mov     rcx, [rsp+78h+var_28]
0x1800cbcc1  xor     rcx, rsp; StackCookie
0x1800cbcc4  call    __security_check_cookie
0x1800cbcc9  add     rsp, 60h
0x1800cbccd  pop     rdi
0x1800cbcce  pop     rsi
0x1800cbccf  pop     rbx
0x1800cbcd0  retn
```
