# GetUpdateRectEnumProc

- ea: `0x180025c70`
- end: `0x180025d15`
- name: `GetUpdateRectEnumProc`
- size: `165`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x1800115f0`
- `0x180025c70`

## import_xrefs

- `USER32!MapWindowPoints` at `0x180025ccf`
- `USER32!MapWindowPoints` at `0x180025ccf`
- `USER32!UnionRect` at `0x180025ce9`
- `USER32!UnionRect` at `0x180025ce9`
- `USER32!IsWindowVisible` at `0x180025c8f`
- `USER32!IsWindowVisible` at `0x180025c8f`
- `USER32!GetUpdateRect` at `0x180025cac`
- `USER32!GetUpdateRect` at `0x180025cac`

## pseudocode

```c
__int64 __fastcall GetUpdateRectEnumProc(HWND a1, __int64 a2)
{
  HWND v4; // rdx
  struct tagRECT Rect; // [rsp+20h] [rbp-38h] BYREF
  struct tagRECT rcDst; // [rsp+30h] [rbp-28h] BYREF

  if ( IsWindowVisible(a1) )
  {
    Rect = 0;
    if ( GetUpdateRect(a1, &Rect, 0) )
    {
      v4 = *(HWND *)a2;
      rcDst = 0;
      MapWindowPoints(a1, v4, (LPPOINT)&Rect, 2u);
      UnionRect(&rcDst, &Rect, (const RECT *)(a2 + 300));
      *(struct tagRECT *)(a2 + 300) = rcDst;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180025c70  mov     [rsp+arg_10], rbx
0x180025c75  push    rdi
0x180025c76  sub     rsp, 50h
0x180025c7a  mov     rax, cs:__security_cookie
0x180025c81  xor     rax, rsp
0x180025c84  mov     [rsp+58h+var_18], rax
0x180025c89  mov     rdi, rdx
0x180025c8c  mov     rbx, rcx
0x180025c8f  call    cs:__imp_IsWindowVisible
0x180025c95  test    eax, eax
0x180025c97  jz      short loc_180025CF8
0x180025c99  xorps   xmm0, xmm0
0x180025c9c  lea     rdx, [rsp+58h+Rect]; lpRect
0x180025ca1  xor     r8d, r8d; bErase
0x180025ca4  mov     rcx, rbx; hWnd
0x180025ca7  movups  xmmword ptr [rsp+58h+Rect.left], xmm0
0x180025cac  call    cs:__imp_GetUpdateRect
0x180025cb2  test    eax, eax
0x180025cb4  jz      short loc_180025CF8
0x180025cb6  mov     rdx, [rdi]; hWndTo
0x180025cb9  lea     r8, [rsp+58h+Rect]; lpPoints
0x180025cbe  xorps   xmm0, xmm0
0x180025cc1  mov     r9d, 2; cPoints
0x180025cc7  mov     rcx, rbx; hWndFrom
0x180025cca  movups  xmmword ptr [rsp+58h+rcDst.left], xmm0
0x180025ccf  call    cs:__imp_MapWindowPoints
0x180025cd5  lea     rbx, [rdi+12Ch]
0x180025cdc  mov     r8, rbx; lprcSrc2
0x180025cdf  lea     rdx, [rsp+58h+Rect]; lprcSrc1
0x180025ce4  lea     rcx, [rsp+58h+rcDst]; lprcDst
0x180025ce9  call    cs:__imp_UnionRect
0x180025cef  movups  xmm0, xmmword ptr [rsp+58h+rcDst.left]
0x180025cf4  movdqu  xmmword ptr [rbx], xmm0
0x180025cf8  mov     eax, 1
0x180025cfd  mov     rcx, [rsp+58h+var_18]
0x180025d02  xor     rcx, rsp; StackCookie
0x180025d05  call    __security_check_cookie
0x180025d0a  mov     rbx, [rsp+58h+arg_10]
0x180025d0f  add     rsp, 50h
0x180025d13  pop     rdi
0x180025d14  retn
```
