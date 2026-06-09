# CView::SetObjectRectsHelper(COleSite *,IOleInPlaceObject *,tagRECT const *,tagRECT const *,HWND__ *)

- ea: `0x18055a570`
- end: `0x18055a81e`
- name: `?SetObjectRectsHelper@CView@@IEAAXPEAVCOleSite@@PEAUIOleInPlaceObject@@PEBUtagRECT@@2PEAUHWND__@@@Z`
- size: `686`
- prototype: `void __fastcall(CView *this, struct COleSite *, const struct tagRECT *, const struct tagRECT *, const struct tagRECT *, HWND hWnd)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18055a3e0`
- `0x1806e8094`

## callees

- `0x1800c7de4`
- `0x18055a570`
- `0x18055a824`
- `0x1805afb98`
- `0x180e44e8c`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `GDI32!EqualRgn` at `0x18055a799`
- `GDI32!EqualRgn` at `0x18055a799`
- `GDI32!DeleteObject` at `0x18055a7fe`
- `GDI32!DeleteObject` at `0x18055a80d`
- `GDI32!DeleteObject` at `0x18055a7fe`
- `GDI32!DeleteObject` at `0x18055a80d`
- `GDI32!CreateRectRgnIndirect` at `0x18055a65c`
- `GDI32!CreateRectRgnIndirect` at `0x18055a74f`
- `GDI32!CreateRectRgnIndirect` at `0x18055a65c`
- `GDI32!CreateRectRgnIndirect` at `0x18055a74f`
- `GDI32!OffsetRgn` at `0x18055a71d`
- `GDI32!OffsetRgn` at `0x18055a7bf`
- `GDI32!OffsetRgn` at `0x18055a71d`
- `GDI32!OffsetRgn` at `0x18055a7bf`
- `GDI32!GetRgnBox` at `0x18055a787`
- `GDI32!GetRgnBox` at `0x18055a787`
- `USER32!GetWindowRgn` at `0x18055a676`
- `USER32!GetWindowRgn` at `0x18055a774`
- `USER32!GetWindowRgn` at `0x18055a676`
- `USER32!GetWindowRgn` at `0x18055a774`
- `USER32!SetWindowRgn` at `0x18055a7d4`
- `USER32!SetWindowRgn` at `0x18055a7d4`

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
  if ( !hWnd || (CView::GetHWNDRect(this, hWnd, (struct CRect *)&v23), !CRect::operator!=(&v22, &v23)) )
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
0x18055a570  mov     rax, rsp
0x18055a573  mov     [rax+20h], r9
0x18055a577  mov     [rax+18h], r8
0x18055a57b  mov     [rax+10h], rdx
0x18055a57f  mov     [rax+8], rcx
0x18055a583  push    rbp
0x18055a584  push    rbx
0x18055a585  push    rsi
0x18055a586  push    rdi
0x18055a587  push    r12
0x18055a589  push    r13
0x18055a58b  push    r14
0x18055a58d  push    r15
0x18055a58f  mov     rbp, rsp
0x18055a592  sub     rsp, 78h
0x18055a596  mov     rax, cs:__security_cookie
0x18055a59d  xor     rax, rsp
0x18055a5a0  mov     [rbp+var_10], rax
0x18055a5a4  mov     rsi, [rbp+hWnd]
0x18055a5a8  xor     edi, edi
0x18055a5aa  mov     rbx, [rbp+arg_0]
0x18055a5ae  xorps   xmm0, xmm0
0x18055a5b1  mov     r12, [rbp+arg_8]
0x18055a5b5  xorps   xmm1, xmm1
0x18055a5b8  mov     r14, [rbp+arg_10]
0x18055a5bc  mov     r15, [rbp+arg_18]
0x18055a5c0  mov     r13, [rbp+arg_20]
0x18055a5c4  movups  [rbp+var_50], xmm0
0x18055a5c8  movups  [rbp+var_40], xmm1
0x18055a5cc  test    rsi, rsi
0x18055a5cf  jnz     loc_18055A655
0x18055a5d5  mov     rax, [rbx+2D8h]
0x18055a5dc  mov     rdx, r15; struct tagRECT *
0x18055a5df  mov     [rbp+var_18], rax
0x18055a5e3  mov     rcx, r12; this
0x18055a5e6  lea     rax, [rbp+rc]
0x18055a5ea  mov     qword ptr [rbp+rc.left], rbx
0x18055a5ee  mov     [rbx+2D8h], rax
0x18055a5f5  mov     qword ptr [rbp+rc.right], 0
0x18055a5fd  mov     [rbp+var_20], r14
0x18055a601  call    ?SetOleSiteRects@COleSite@@QEAAXPEBUtagRECT@@0@Z; COleSite::SetOleSiteRects(tagRECT const *,tagRECT const *)
0x18055a606  test    r14, r14
0x18055a609  jz      short loc_18055A620
0x18055a60b  mov     rax, [r14]
0x18055a60e  mov     r8, r13
0x18055a611  mov     rdx, r15
0x18055a614  mov     rcx, r14
0x18055a617  mov     rax, [rax+38h]
0x18055a61b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18055a620  mov     rcx, qword ptr [rbp+rc.left]
0x18055a624  test    rcx, rcx
0x18055a627  jnz     short loc_18055A696
0x18055a629  test    rsi, rsi
0x18055a62c  jnz     short loc_18055A6A3
0x18055a62e  test    rdi, rdi
0x18055a631  jnz     loc_18055A80A
0x18055a637  mov     rcx, [rbp+var_10]
0x18055a63b  xor     rcx, rsp; StackCookie
0x18055a63e  call    __security_check_cookie
0x18055a643  add     rsp, 78h
0x18055a647  pop     r15
0x18055a649  pop     r14
0x18055a64b  pop     r13
0x18055a64d  pop     r12
0x18055a64f  pop     rdi
0x18055a650  pop     rsi
0x18055a651  pop     rbx
0x18055a652  pop     rbp
0x18055a653  retn
0x18055a655  lea     rcx, ?g_Zero@@3TZERO_STRUCTS@@B; lprect
0x18055a65c  call    cs:__imp_CreateRectRgnIndirect
0x18055a663  nop     dword ptr [rax+rax+00h]
0x18055a668  mov     rdi, rax
0x18055a66b  test    rax, rax
0x18055a66e  jz      short loc_18055A682
0x18055a670  mov     rdx, rax; hRgn
0x18055a673  mov     rcx, rsi; hWnd
0x18055a676  call    cs:__imp_GetWindowRgn
0x18055a67d  nop     dword ptr [rax+rax+00h]
0x18055a682  lea     r8, [rbp+var_50]; struct CRect *
0x18055a686  mov     rdx, rsi; HWND
0x18055a689  mov     rcx, rbx; this
0x18055a68c  call    ?GetHWNDRect@CView@@QEBAXPEAUHWND__@@PEAVCRect@@@Z; CView::GetHWNDRect(HWND__ *,CRect *)
0x18055a691  jmp     loc_18055A5D5
0x18055a696  mov     rax, [rbp+var_18]
0x18055a69a  mov     [rcx+2D8h], rax
0x18055a6a1  jmp     short loc_18055A629
0x18055a6a3  lea     r8, [rbp+var_40]; struct CRect *
0x18055a6a7  mov     rdx, rsi; HWND
0x18055a6aa  mov     rcx, rbx; this
0x18055a6ad  call    ?GetHWNDRect@CView@@QEBAXPEAUHWND__@@PEAVCRect@@@Z; CView::GetHWNDRect(HWND__ *,CRect *)
0x18055a6b2  lea     rdx, [rbp+var_40]
0x18055a6b6  lea     rcx, [rbp+var_50]
0x18055a6ba  call    ??9CRect@@QEBA_NAEBUtagRECT@@@Z; CRect::operator!=(tagRECT const &)
0x18055a6bf  test    al, al
0x18055a6c1  jz      loc_18055A62E
0x18055a6c7  mov     r12d, dword ptr [rbp+var_50]
0x18055a6cb  xor     r8d, r8d
0x18055a6ce  mov     r13d, dword ptr [rbp+var_50+4]
0x18055a6d2  sub     r12d, dword ptr [rbp+var_40]
0x18055a6d6  sub     r13d, dword ptr [rbp+var_40+4]
0x18055a6da  mov     r14d, [rbx+2BCh]
0x18055a6e1  sub     r14d, 1
0x18055a6e5  mov     [rbp+var_58], r8d
0x18055a6e9  js      short loc_18055A73F
0x18055a6eb  movsxd  r15, r14d
0x18055a6ee  mov     rdx, [rbx+2C0h]
0x18055a6f5  lea     rax, [r15+r15*4]
0x18055a6f9  cmp     rsi, [rdx+rax*8]
0x18055a6fd  jnz     short loc_18055A729
0x18055a6ff  mov     rcx, [rdx+rax*8+8]; hrgn
0x18055a704  mov     r8d, 1
0x18055a70a  mov     [rbp+var_58], r8d
0x18055a70e  test    rcx, rcx
0x18055a711  jz      loc_18055A7E2
0x18055a717  mov     r8d, r13d; y
0x18055a71a  mov     edx, r12d; x
0x18055a71d  call    cs:__imp_OffsetRgn
0x18055a724  nop     dword ptr [rax+rax+00h]
0x18055a729  mov     r8d, [rbp+var_58]
0x18055a72d  dec     r15
0x18055a730  sub     r14d, 1
0x18055a734  jns     short loc_18055A6EE
0x18055a736  test    r8d, r8d
0x18055a739  jnz     loc_18055A62E
0x18055a73f  test    rdi, rdi
0x18055a742  jz      loc_18055A637
0x18055a748  lea     rcx, ?g_Zero@@3TZERO_STRUCTS@@B; lprect
0x18055a74f  call    cs:__imp_CreateRectRgnIndirect
0x18055a756  nop     dword ptr [rax+rax+00h]
0x18055a75b  mov     rbx, rax
0x18055a75e  test    rax, rax
0x18055a761  jz      loc_18055A80A
0x18055a767  xorps   xmm0, xmm0
0x18055a76a  mov     rdx, rax; hRgn
0x18055a76d  mov     rcx, rsi; hWnd
0x18055a770  movups  xmmword ptr [rbp+rc.left], xmm0
0x18055a774  call    cs:__imp_GetWindowRgn
0x18055a77b  nop     dword ptr [rax+rax+00h]
0x18055a780  lea     rdx, [rbp+rc]; lprc
0x18055a784  mov     rcx, rbx; hrgn
0x18055a787  call    cs:__imp_GetRgnBox
0x18055a78e  nop     dword ptr [rax+rax+00h]
0x18055a793  mov     rdx, rbx; hrgn2
0x18055a796  mov     rcx, rdi; hrgn1
0x18055a799  call    cs:__imp_EqualRgn
0x18055a7a0  nop     dword ptr [rax+rax+00h]
0x18055a7a5  test    eax, eax
0x18055a7a7  jz      short loc_18055A7FB
0x18055a7a9  lea     rcx, [rbp+rc]; this
0x18055a7ad  call    ?IsRectEmpty@CRect@@QEBA_NXZ; CRect::IsRectEmpty(void)
0x18055a7b2  test    al, al
0x18055a7b4  jnz     short loc_18055A7FB
0x18055a7b6  mov     r8d, r13d; y
0x18055a7b9  mov     edx, r12d; x
0x18055a7bc  mov     rcx, rbx; hrgn
0x18055a7bf  call    cs:__imp_OffsetRgn
0x18055a7c6  nop     dword ptr [rax+rax+00h]
0x18055a7cb  xor     r8d, r8d; bRedraw
0x18055a7ce  mov     rdx, rbx; hRgn
0x18055a7d1  mov     rcx, rsi; hWnd
0x18055a7d4  call    cs:__imp_SetWindowRgn
0x18055a7db  nop     dword ptr [rax+rax+00h]
0x18055a7e0  jmp     short loc_18055A80A
0x18055a7e2  add     [rdx+rax*8+10h], r12d
0x18055a7e7  add     [rdx+rax*8+14h], r13d
0x18055a7ec  add     [rdx+rax*8+18h], r12d
0x18055a7f1  add     [rdx+rax*8+1Ch], r13d
0x18055a7f6  jmp     loc_18055A72D
0x18055a7fb  mov     rcx, rbx; ho
0x18055a7fe  call    cs:__imp_DeleteObject
0x18055a805  nop     dword ptr [rax+rax+00h]
0x18055a80a  mov     rcx, rdi; ho
0x18055a80d  call    cs:__imp_DeleteObject
0x18055a814  nop     dword ptr [rax+rax+00h]
0x18055a819  jmp     loc_18055A637
```
