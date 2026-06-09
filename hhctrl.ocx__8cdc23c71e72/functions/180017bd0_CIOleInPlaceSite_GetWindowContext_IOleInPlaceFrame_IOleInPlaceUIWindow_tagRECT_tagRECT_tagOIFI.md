# CIOleInPlaceSite::GetWindowContext(IOleInPlaceFrame * *,IOleInPlaceUIWindow * *,tagRECT *,tagRECT *,tagOIFI *)

- ea: `0x180017bd0`
- end: `0x180017c97`
- name: `?GetWindowContext@CIOleInPlaceSite@@UEAAJPEAPEAUIOleInPlaceFrame@@PEAPEAUIOleInPlaceUIWindow@@PEAUtagRECT@@2PEAUtagOIFI@@@Z`
- size: `199`
- prototype: `int(CIOleInPlaceSite *__hidden this, struct IOleInPlaceFrame **, struct IOleInPlaceUIWindow **, struct tagRECT *, struct tagRECT *, struct tagOIFI *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180075c90`
- `0x180078010`

## import_xrefs

- `USER32!CopyRect` at `0x180017c4f`
- `USER32!CopyRect` at `0x180017c5d`
- `USER32!CopyRect` at `0x180017c4f`
- `USER32!CopyRect` at `0x180017c5d`
- `USER32!GetClientRect` at `0x180017c41`
- `USER32!GetClientRect` at `0x180017c41`

## pseudocode

```c
__int64 __fastcall CIOleInPlaceSite::GetWindowContext(
        CIOleInPlaceSite *this,
        struct IOleInPlaceFrame **a2,
        struct IOleInPlaceUIWindow **a3,
        struct tagRECT *a4,
        struct tagRECT *lprcDst,
        struct tagOIFI *a6)
{
  __int64 v6; // rax
  __int64 result; // rax
  struct tagRECT Rect; // [rsp+20h] [rbp-58h] BYREF

  v6 = *((_QWORD *)this + 2);
  Rect = 0;
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v6 + 72) + 8LL))(*(_QWORD *)(v6 + 72));
  *a2 = *(struct IOleInPlaceFrame **)(*((_QWORD *)this + 2) + 72LL);
  *a3 = 0;
  GetClientRect(*(HWND *)(*((_QWORD *)this + 2) + 32LL), &Rect);
  CopyRect(a4, &Rect);
  CopyRect(lprcDst, &Rect);
  a6->fMDIApp = 0;
  result = 0;
  a6->hwndFrame = *(HWND *)(*((_QWORD *)this + 2) + 32LL);
  a6->haccel = 0;
  a6->cAccelEntries = 0;
  return result;
}

```

## disassembly

```asm
0x180017bd0  push    rbx
0x180017bd2  push    rbp
0x180017bd3  push    rsi
0x180017bd4  push    rdi
0x180017bd5  push    r14
0x180017bd7  push    r15
0x180017bd9  sub     rsp, 48h
0x180017bdd  mov     rax, cs:__security_cookie
0x180017be4  xor     rax, rsp
0x180017be7  mov     [rsp+78h+var_48], rax
0x180017bec  mov     rax, [rcx+10h]
0x180017bf0  xorps   xmm0, xmm0
0x180017bf3  mov     rsi, [rsp+78h+lprcDst]
0x180017bfb  mov     r15, rcx
0x180017bfe  mov     r14, [rsp+78h+arg_28]
0x180017c06  mov     rbp, r9
0x180017c09  movups  xmmword ptr [rsp+78h+Rect.left], xmm0
0x180017c0e  mov     rcx, [rax+48h]
0x180017c12  mov     rdi, r8
0x180017c15  mov     rbx, rdx
0x180017c18  mov     rax, [rcx]
0x180017c1b  mov     rax, [rax+8]
0x180017c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c24  mov     rax, [r15+10h]
0x180017c28  mov     rdx, [rax+48h]
0x180017c2c  mov     [rbx], rdx
0x180017c2f  xor     ebx, ebx
0x180017c31  mov     [rdi], rbx
0x180017c34  lea     rdx, [rsp+78h+Rect]; lpRect
0x180017c39  mov     rcx, [r15+10h]
0x180017c3d  mov     rcx, [rcx+20h]; hWnd
0x180017c41  call    cs:__imp_GetClientRect
0x180017c47  lea     rdx, [rsp+78h+Rect]; lprcSrc
0x180017c4c  mov     rcx, rbp; lprcDst
0x180017c4f  call    cs:__imp_CopyRect
0x180017c55  lea     rdx, [rsp+78h+Rect]; lprcSrc
0x180017c5a  mov     rcx, rsi; lprcDst
0x180017c5d  call    cs:__imp_CopyRect
0x180017c63  mov     [r14+4], ebx
0x180017c67  mov     rax, [r15+10h]
0x180017c6b  mov     rcx, [rax+20h]
0x180017c6f  xor     eax, eax
0x180017c71  mov     [r14+8], rcx
0x180017c75  mov     [r14+10h], rbx
0x180017c79  mov     [r14+18h], ebx
0x180017c7d  mov     rcx, [rsp+78h+var_48]
0x180017c82  xor     rcx, rsp; StackCookie
0x180017c85  call    __security_check_cookie
0x180017c8a  add     rsp, 48h
0x180017c8e  pop     r15
0x180017c90  pop     r14
0x180017c92  pop     rdi
0x180017c93  pop     rsi
0x180017c94  pop     rbp
0x180017c95  pop     rbx
0x180017c96  retn
```
