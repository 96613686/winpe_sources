# CBackingStoreWin32::_GetViewBounds(tagRECT &)

- ea: `0x180060c30`
- end: `0x180060cfa`
- name: `?_GetViewBounds@CBackingStoreWin32@@MEAAJAEAUtagRECT@@@Z`
- size: `202`
- prototype: `int(CBackingStoreWin32 *__hidden this, struct tagRECT *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180060c30`
- `0x180106a60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060ce6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060ce6`
- `USER32!SendMessageW` at `0x180060c8d`
- `USER32!SendMessageW` at `0x180060c8d`
- `USER32!IntersectRect` at `0x180060cad`
- `USER32!IntersectRect` at `0x180060cad`
- `USER32!MapWindowPoints` at `0x180060cc2`
- `USER32!MapWindowPoints` at `0x180060cc2`
- `USER32!GetClientRect` at `0x180060c5f`
- `USER32!GetClientRect` at `0x180060c5f`
- `USER32!SetRectEmpty` at `0x180060c52`
- `USER32!SetRectEmpty` at `0x180060c76`
- `USER32!SetRectEmpty` at `0x180060c52`
- `USER32!SetRectEmpty` at `0x180060c76`
- `USER32!IsRectEmpty` at `0x180060c98`
- `USER32!IsRectEmpty` at `0x180060c98`

## pseudocode

```c
int __fastcall CBackingStoreWin32::_GetViewBounds(HWND *this, struct tagRECT *a2)
{
  int result; // eax
  struct tagRECT rc; // [rsp+20h] [rbp-28h] BYREF

  SetRectEmpty(a2);
  if ( GetClientRect(this[1], a2) )
  {
    rc = 0;
    SetRectEmpty(&rc);
    SendMessageW(this[1], 0xB2u, 0, (LPARAM)&rc);
    if ( !IsRectEmpty(&rc) )
      IntersectRect(a2, &rc, a2);
    if ( MapWindowPoints(this[1], 0, (LPPOINT)a2, 2u) )
      return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180060c30  mov     [rsp+arg_10], rbx
0x180060c35  push    rdi
0x180060c36  sub     rsp, 40h
0x180060c3a  mov     rax, cs:__security_cookie
0x180060c41  xor     rax, rsp
0x180060c44  mov     [rsp+48h+var_18], rax
0x180060c49  mov     rdi, rcx
0x180060c4c  mov     rbx, rdx
0x180060c4f  mov     rcx, rdx; lprc
0x180060c52  call    cs:__imp_SetRectEmpty
0x180060c58  mov     rcx, [rdi+8]; hWnd
0x180060c5c  mov     rdx, rbx; lpRect
0x180060c5f  call    cs:__imp_GetClientRect
0x180060c65  test    eax, eax
0x180060c67  jz      short loc_180060CE6
0x180060c69  xorps   xmm0, xmm0
0x180060c6c  lea     rcx, [rsp+48h+rc]; lprc
0x180060c71  movups  xmmword ptr [rsp+48h+rc.left], xmm0
0x180060c76  call    cs:__imp_SetRectEmpty
0x180060c7c  mov     rcx, [rdi+8]; hWnd
0x180060c80  lea     r9, [rsp+48h+rc]; lParam
0x180060c85  xor     r8d, r8d; wParam
0x180060c88  mov     edx, 0B2h; Msg
0x180060c8d  call    cs:__imp_SendMessageW
0x180060c93  lea     rcx, [rsp+48h+rc]; lprc
0x180060c98  call    cs:__imp_IsRectEmpty
0x180060c9e  test    eax, eax
0x180060ca0  jnz     short loc_180060CB3
0x180060ca2  mov     r8, rbx; lprcSrc2
0x180060ca5  lea     rdx, [rsp+48h+rc]; lprcSrc1
0x180060caa  mov     rcx, rbx; lprcDst
0x180060cad  call    cs:__imp_IntersectRect
0x180060cb3  mov     rcx, [rdi+8]; hWndFrom
0x180060cb7  mov     r9d, 2; cPoints
0x180060cbd  mov     r8, rbx; lpPoints
0x180060cc0  xor     edx, edx; hWndTo
0x180060cc2  call    cs:__imp_MapWindowPoints
0x180060cc8  test    eax, eax
0x180060cca  jz      short loc_180060CE6
0x180060ccc  xor     eax, eax
0x180060cce  mov     rcx, [rsp+48h+var_18]
0x180060cd3  xor     rcx, rsp; StackCookie
0x180060cd6  call    __security_check_cookie
0x180060cdb  mov     rbx, [rsp+48h+arg_10]
0x180060ce0  add     rsp, 40h
0x180060ce4  pop     rdi
0x180060ce5  retn
0x180060ce6  call    cs:__imp_GetLastError
0x180060cec  test    eax, eax
0x180060cee  jle     short loc_180060CCE
0x180060cf0  movzx   eax, ax
0x180060cf3  or      eax, 80070000h
0x180060cf8  jmp     short loc_180060CCE
```
