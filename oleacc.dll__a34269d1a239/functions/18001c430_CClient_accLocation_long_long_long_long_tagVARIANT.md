# CClient::accLocation(long *,long *,long *,long *,tagVARIANT)

- ea: `0x18001c430`
- end: `0x18001c506`
- name: `?accLocation@CClient@@UEAAJPEAJ000UtagVARIANT@@@Z`
- size: `214`
- prototype: `__int64 __fastcall(CClient *__hidden this, int *, int *, int *, int *, struct tagVARIANT *)`
- caller_count: `14`
- callee_count: `3`
- tags: ``

## callers

- `0x180005050`
- `0x18001ae40`
- `0x18001be00`
- `0x180026d10`
- `0x180028ba0`
- `0x18002a160`
- `0x18002c7d0`
- `0x18002fcc0`
- `0x180039650`
- `0x18003db10`
- `0x18003f5e0`
- `0x180041750`
- `0x180043f80`
- `0x180044c30`

## callees

- `0x18001c430`
- `0x18001e4c0`
- `0x180049010`

## import_xrefs

- `USER32!SetRectEmpty` at `0x18001c4a0`
- `USER32!SetRectEmpty` at `0x18001c4a0`
- `USER32!MapWindowPoints` at `0x18001c4c5`
- `USER32!MapWindowPoints` at `0x18001c4c5`
- `USER32!GetClientRect` at `0x18001c4ae`
- `USER32!GetClientRect` at `0x18001c4ae`

## pseudocode

```c
__int64 __fastcall CClient::accLocation(HWND *this, int *a2, int *a3, int *a4, int *a5, struct tagVARIANT *a6)
{
  HWND v11; // rbx
  LONG top; // edx
  int v13; // eax
  struct tagRECT rc; // [rsp+20h] [rbp-58h] BYREF

  rc = 0;
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  if ( !(*((unsigned int (__fastcall **)(HWND *, struct tagVARIANT *))*this + 30))(this, a6) )
    return 2147942487LL;
  v11 = this[10];
  SetRectEmpty(&rc);
  GetClientRect(v11, &rc);
  MapWindowPoints(this[10], 0, (LPPOINT)&rc, 2u);
  top = rc.top;
  v13 = rc.right - rc.left;
  *a2 = rc.left;
  *a3 = top;
  *a4 = v13;
  *a5 = rc.bottom - top;
  return 0;
}

```

## disassembly

```asm
0x18001c430  push    rbx
0x18001c432  push    rbp
0x18001c433  push    rsi
0x18001c434  push    rdi
0x18001c435  push    r14
0x18001c437  push    r15
0x18001c439  sub     rsp, 48h
0x18001c43d  mov     rax, cs:__security_cookie
0x18001c444  xor     rax, rsp
0x18001c447  mov     [rsp+78h+var_48], rax
0x18001c44c  mov     rbp, [rsp+78h+arg_20]
0x18001c454  xor     ebx, ebx
0x18001c456  mov     rsi, rdx
0x18001c459  xorps   xmm0, xmm0
0x18001c45c  mov     rdx, [rsp+78h+arg_28]
0x18001c464  mov     r15, r9
0x18001c467  mov     r14, r8
0x18001c46a  mov     rdi, rcx
0x18001c46d  movups  xmmword ptr [rsp+78h+rc.left], xmm0
0x18001c472  mov     [rsi], ebx
0x18001c474  mov     [r8], ebx
0x18001c477  mov     [r9], ebx
0x18001c47a  mov     [rbp+0], ebx
0x18001c47d  mov     rax, [rcx]
0x18001c480  mov     rax, [rax+0F0h]
0x18001c487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c48c  test    eax, eax
0x18001c48e  jnz     short loc_18001C497
0x18001c490  mov     eax, 80070057h
0x18001c495  jmp     short loc_18001C4EC
0x18001c497  mov     rbx, [rdi+50h]
0x18001c49b  lea     rcx, [rsp+78h+rc]; lprc
0x18001c4a0  call    cs:__imp_SetRectEmpty
0x18001c4a6  lea     rdx, [rsp+78h+rc]; lpRect
0x18001c4ab  mov     rcx, rbx; hWnd
0x18001c4ae  call    cs:__imp_GetClientRect
0x18001c4b4  mov     rcx, [rdi+50h]; hWndFrom
0x18001c4b8  lea     r8, [rsp+78h+rc]; lpPoints
0x18001c4bd  mov     r9d, 2; cPoints
0x18001c4c3  xor     edx, edx; hWndTo
0x18001c4c5  call    cs:__imp_MapWindowPoints
0x18001c4cb  mov     ecx, [rsp+78h+rc.left]
0x18001c4cf  mov     edx, [rsp+78h+rc.top]
0x18001c4d3  mov     eax, [rsp+78h+rc.right]
0x18001c4d7  sub     eax, ecx
0x18001c4d9  mov     [rsi], ecx
0x18001c4db  mov     [r14], edx
0x18001c4de  mov     [r15], eax
0x18001c4e1  mov     eax, [rsp+78h+rc.bottom]
0x18001c4e5  sub     eax, edx
0x18001c4e7  mov     [rbp+0], eax
0x18001c4ea  xor     eax, eax
0x18001c4ec  mov     rcx, [rsp+78h+var_48]
0x18001c4f1  xor     rcx, rsp; StackCookie
0x18001c4f4  call    __security_check_cookie
0x18001c4f9  add     rsp, 48h
0x18001c4fd  pop     r15
0x18001c4ff  pop     r14
0x18001c501  pop     rdi
0x18001c502  pop     rsi
0x18001c503  pop     rbp
0x18001c504  pop     rbx
0x18001c505  retn
```
