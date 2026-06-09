# CNovSetDlg::OnDialogResize(uint,unsigned __int64,__int64,int &)

- ea: `0x14002d2d0`
- end: `0x14002d3ee`
- name: `?OnDialogResize@CNovSetDlg@@QEAA_JI_K_JAEAH@Z`
- size: `286`
- prototype: `__int64 __fastcall(CNovSetDlg *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140023d70`

## callees

- `0x14002d2d0`
- `0x14004ad80`

## import_xrefs

- `USER32!SetScrollInfo` at `0x14002d38a`
- `USER32!SetScrollInfo` at `0x14002d38a`
- `USER32!ShowScrollBar` at `0x14002d342`
- `USER32!ShowScrollBar` at `0x14002d39b`
- `USER32!ShowScrollBar` at `0x14002d342`
- `USER32!ShowScrollBar` at `0x14002d39b`
- `USER32!InvalidateRect` at `0x14002d3b1`
- `USER32!InvalidateRect` at `0x14002d3b1`
- `USER32!UpdateWindow` at `0x14002d3c1`
- `USER32!UpdateWindow` at `0x14002d3c1`
- `USER32!GetClientRect` at `0x14002d307`
- `USER32!GetClientRect` at `0x14002d307`

## pseudocode

```c
__int64 __fastcall CNovSetDlg::OnDialogResize(HWND *this, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v5; // ebx
  HWND v6; // rcx
  HWND v7; // rcx
  SCROLLINFO v9; // [rsp+20h] [rbp-40h] BYREF
  struct tagRECT Rect; // [rsp+40h] [rbp-20h] BYREF

  Rect = 0;
  if ( a4 )
  {
    v5 = WORD1(a4);
  }
  else
  {
    GetClientRect(this[1], &Rect);
    v5 = Rect.bottom - Rect.top;
  }
  v6 = this[1];
  if ( v5 >= dword_140064230 )
  {
    ShowScrollBar(v6, 1, 0);
  }
  else
  {
    memset(&v9, 0, sizeof(v9));
    ShowScrollBar(v6, 1, 1);
    v7 = this[1];
    v9.cbSize = 28;
    *(_QWORD *)&v9.fMask = 3;
    v9.nMax = 700 / dword_140064234;
    v9.nPage = v5 / dword_140064234;
    SetScrollInfo(v7, 1, &v9, 1);
  }
  InvalidateRect(this[1], 0, 1);
  UpdateWindow(this[1]);
  return 0;
}

```

## disassembly

```asm
0x14002d2d0  mov     [rsp-8+arg_8], rbx
0x14002d2d5  mov     [rsp-8+arg_10], rdi
0x14002d2da  push    rbp
0x14002d2db  mov     rbp, rsp
0x14002d2de  sub     rsp, 60h
0x14002d2e2  mov     rax, cs:__security_cookie
0x14002d2e9  xor     rax, rsp
0x14002d2ec  mov     [rbp+var_10], rax
0x14002d2f0  xorps   xmm0, xmm0
0x14002d2f3  mov     rdi, rcx
0x14002d2f6  movups  xmmword ptr [rbp+Rect.left], xmm0
0x14002d2fa  test    r9, r9
0x14002d2fd  jnz     short loc_14002D31B
0x14002d2ff  mov     rcx, [rcx+8]; hWnd
0x14002d303  lea     rdx, [rbp+Rect]; lpRect
0x14002d307  call    cs:__imp_GetClientRect
0x14002d30e  nop     dword ptr [rax+rax+00h]
0x14002d313  mov     ebx, [rbp+Rect.bottom]
0x14002d316  sub     ebx, [rbp+Rect.top]
0x14002d319  jmp     short loc_14002D323
0x14002d31b  shr     r9, 10h
0x14002d31f  movzx   ebx, r9w
0x14002d323  cmp     ebx, cs:dword_140064230
0x14002d329  mov     edx, 1; wBar
0x14002d32e  mov     rcx, [rdi+8]; hWnd
0x14002d332  jnb     short loc_14002D398
0x14002d334  xorps   xmm0, xmm0
0x14002d337  mov     r8d, edx; bShow
0x14002d33a  movups  xmmword ptr [rbp+var_40.cbSize], xmm0
0x14002d33e  movups  xmmword ptr [rbp+var_40.nMax], xmm0
0x14002d342  call    cs:__imp_ShowScrollBar
0x14002d349  nop     dword ptr [rax+rax+00h]
0x14002d34e  mov     rcx, [rdi+8]; hwnd
0x14002d352  lea     r8, [rbp+var_40]; lpsi
0x14002d356  mov     eax, 2BCh
0x14002d35b  mov     [rbp+var_40.cbSize], 1Ch
0x14002d362  cdq
0x14002d363  mov     qword ptr [rbp+var_40.fMask], 3
0x14002d36b  idiv    cs:dword_140064234
0x14002d371  xor     edx, edx
0x14002d373  mov     r9d, 1; redraw
0x14002d379  mov     [rbp+var_40.nMax], eax
0x14002d37c  mov     eax, ebx
0x14002d37e  div     cs:dword_140064234
0x14002d384  mov     edx, r9d; nBar
0x14002d387  mov     [rbp+var_40.nPage], eax
0x14002d38a  call    cs:__imp_SetScrollInfo
0x14002d391  nop     dword ptr [rax+rax+00h]
0x14002d396  jmp     short loc_14002D3A7
0x14002d398  xor     r8d, r8d; bShow
0x14002d39b  call    cs:__imp_ShowScrollBar
0x14002d3a2  nop     dword ptr [rax+rax+00h]
0x14002d3a7  mov     rcx, [rdi+8]; hWnd
0x14002d3ab  xor     edx, edx; lpRect
0x14002d3ad  lea     r8d, [rdx+1]; bErase
0x14002d3b1  call    cs:__imp_InvalidateRect
0x14002d3b8  nop     dword ptr [rax+rax+00h]
0x14002d3bd  mov     rcx, [rdi+8]; hWnd
0x14002d3c1  call    cs:__imp_UpdateWindow
0x14002d3c8  nop     dword ptr [rax+rax+00h]
0x14002d3cd  xor     eax, eax
0x14002d3cf  mov     rcx, [rbp+var_10]
0x14002d3d3  xor     rcx, rsp; StackCookie
0x14002d3d6  call    __security_check_cookie
0x14002d3db  lea     r11, [rsp+60h+var_s0]
0x14002d3e0  mov     rbx, [r11+18h]
0x14002d3e4  mov     rdi, [r11+20h]
0x14002d3e8  mov     rsp, r11
0x14002d3eb  pop     rbp
0x14002d3ec  retn
```
