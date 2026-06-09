# CMFCDynamicLayout::GetItemRect(AFX_DYNAMIC_LAYOUT_ITEM &)

- ea: `0x180018a28`
- end: `0x180018aa5`
- name: `?GetItemRect@CMFCDynamicLayout@@IEBA?AVCRect@@AEAUAFX_DYNAMIC_LAYOUT_ITEM@@@Z`
- size: `125`
- prototype: `struct CRect __high(struct AFX_DYNAMIC_LAYOUT_ITEM *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018c44`

## callees

- `0x180018a28`
- `0x18001b550`

## import_xrefs

- `MFC42u!__imp_?ScreenToClient@CWnd@@QEBAXPEAUtagRECT@@@Z` at `0x180018a7b`
- `MFC42u!__imp_?ScreenToClient@CWnd@@QEBAXPEAUtagRECT@@@Z` at `0x180018a7b`
- `USER32!CopyRect` at `0x180018a5c`
- `USER32!CopyRect` at `0x180018a5c`
- `USER32!GetWindowRect` at `0x180018a6c`
- `USER32!GetWindowRect` at `0x180018a6c`

## pseudocode

```c
struct tagRECT *__fastcall CMFCDynamicLayout::GetItemRect(__int64 a1, struct tagRECT *a2, HWND *a3)
{
  bool v3; // zf
  struct tagRECT Rect; // [rsp+20h] [rbp-28h] BYREF

  v3 = *(_QWORD *)(a1 + 8) == 0;
  Rect = 0;
  if ( v3 )
  {
    CopyRect(a2, 0);
  }
  else
  {
    GetWindowRect(*a3, &Rect);
    CWnd::ScreenToClient(*(CWnd **)(a1 + 8), &Rect);
    *a2 = Rect;
  }
  return a2;
}

```

## disassembly

```asm
0x180018a28  mov     [rsp+arg_18], rbx
0x180018a2d  push    rdi
0x180018a2e  sub     rsp, 40h
0x180018a32  mov     rax, cs:__security_cookie
0x180018a39  xor     rax, rsp
0x180018a3c  mov     [rsp+48h+var_18], rax
0x180018a41  cmp     qword ptr [rcx+8], 0
0x180018a46  xorps   xmm0, xmm0
0x180018a49  movdqu  xmmword ptr [rsp+48h+Rect.left], xmm0
0x180018a4f  mov     rbx, rdx
0x180018a52  mov     rdi, rcx
0x180018a55  jnz     short loc_180018A64
0x180018a57  xor     edx, edx; lprcSrc
0x180018a59  mov     rcx, rbx; lprcDst
0x180018a5c  call    cs:__imp_CopyRect
0x180018a62  jmp     short loc_180018A8A
0x180018a64  mov     rcx, [r8]; hWnd
0x180018a67  lea     rdx, [rsp+48h+Rect]; lpRect
0x180018a6c  call    cs:__imp_GetWindowRect
0x180018a72  mov     rcx, [rdi+8]
0x180018a76  lea     rdx, [rsp+48h+Rect]
0x180018a7b  call    cs:__imp_?ScreenToClient@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ScreenToClient(tagRECT *)
0x180018a81  movups  xmm0, xmmword ptr [rsp+48h+Rect.left]
0x180018a86  movdqu  xmmword ptr [rbx], xmm0
0x180018a8a  mov     rax, rbx
0x180018a8d  mov     rcx, [rsp+48h+var_18]
0x180018a92  xor     rcx, rsp; StackCookie
0x180018a95  call    __security_check_cookie
0x180018a9a  mov     rbx, [rsp+48h+arg_18]
0x180018a9f  add     rsp, 40h
0x180018aa3  pop     rdi
0x180018aa4  retn
```
