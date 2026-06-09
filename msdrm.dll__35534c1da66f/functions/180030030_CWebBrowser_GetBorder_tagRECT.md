# CWebBrowser::GetBorder(tagRECT *)

- ea: `0x180030030`
- end: `0x180030082`
- name: `?GetBorder@CWebBrowser@@UEAAJPEAUtagRECT@@@Z`
- size: `82`
- prototype: `int(CWebBrowser *__hidden this, struct tagRECT *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18005bdc0`

## import_xrefs

- `USER32!CopyRect` at `0x180030067`
- `USER32!CopyRect` at `0x180030067`
- `USER32!GetClientRect` at `0x180030059`
- `USER32!GetClientRect` at `0x180030059`

## pseudocode

```c
__int64 __fastcall CWebBrowser::GetBorder(CWebBrowser *this, struct tagRECT *a2)
{
  HWND v2; // rcx
  struct tagRECT Rect; // [rsp+20h] [rbp-28h] BYREF

  v2 = (HWND)*((_QWORD *)this + 5);
  Rect = 0;
  GetClientRect(v2, &Rect);
  CopyRect(a2, &Rect);
  return 0;
}

```

## disassembly

```asm
0x180030030  push    rbx
0x180030032  sub     rsp, 40h
0x180030036  mov     rax, cs:__security_cookie
0x18003003d  xor     rax, rsp
0x180030040  mov     [rsp+48h+var_18], rax
0x180030045  mov     rcx, [rcx+28h]; hWnd
0x180030049  mov     rbx, rdx
0x18003004c  xorps   xmm0, xmm0
0x18003004f  lea     rdx, [rsp+48h+Rect]; lpRect
0x180030054  movups  xmmword ptr [rsp+48h+Rect.left], xmm0
0x180030059  call    cs:__imp_GetClientRect
0x18003005f  lea     rdx, [rsp+48h+Rect]; lprcSrc
0x180030064  mov     rcx, rbx; lprcDst
0x180030067  call    cs:__imp_CopyRect
0x18003006d  xor     eax, eax
0x18003006f  mov     rcx, [rsp+48h+var_18]
0x180030074  xor     rcx, rsp; StackCookie
0x180030077  call    __security_check_cookie
0x18003007c  add     rsp, 40h
0x180030080  pop     rbx
0x180030081  retn
```
