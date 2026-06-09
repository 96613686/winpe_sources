# CExpInterDlg::OnDialogResize(uint,unsigned __int64,__int64,int &)

- ea: `0x14001c02c`
- end: `0x14001c332`
- name: `?OnDialogResize@CExpInterDlg@@QEAA_JI_K_JAEAH@Z`
- size: `774`
- prototype: `__int64(CExpInterDlg *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14001b9c4`
- `0x14001db80`

## callees

- `0x14001c02c`
- `0x14004ad80`

## import_xrefs

- `USER32!SendMessageW` at `0x14001c2da`
- `USER32!SendMessageW` at `0x14001c2da`
- `USER32!GetDlgItem` at `0x14001c14f`
- `USER32!GetDlgItem` at `0x14001c1cf`
- `USER32!GetDlgItem` at `0x14001c242`
- `USER32!GetDlgItem` at `0x14001c14f`
- `USER32!GetDlgItem` at `0x14001c1cf`
- `USER32!GetDlgItem` at `0x14001c242`
- `USER32!InvalidateRect` at `0x14001c2b2`
- `USER32!InvalidateRect` at `0x14001c2ef`
- `USER32!InvalidateRect` at `0x14001c2b2`
- `USER32!InvalidateRect` at `0x14001c2ef`
- `USER32!MapDialogRect` at `0x14001c0c9`
- `USER32!MapDialogRect` at `0x14001c0e7`
- `USER32!MapDialogRect` at `0x14001c173`
- `USER32!MapDialogRect` at `0x14001c1f3`
- `USER32!MapDialogRect` at `0x14001c266`
- `USER32!MapDialogRect` at `0x14001c0c9`
- `USER32!MapDialogRect` at `0x14001c0e7`
- `USER32!MapDialogRect` at `0x14001c173`
- `USER32!MapDialogRect` at `0x14001c1f3`
- `USER32!MapDialogRect` at `0x14001c266`
- `USER32!UpdateWindow` at `0x14001c2c1`
- `USER32!UpdateWindow` at `0x14001c2ff`
- `USER32!UpdateWindow` at `0x14001c2c1`
- `USER32!UpdateWindow` at `0x14001c2ff`
- `USER32!MoveWindow` at `0x14001c128`
- `USER32!MoveWindow` at `0x14001c1ba`
- `USER32!MoveWindow` at `0x14001c22d`
- `USER32!MoveWindow` at `0x14001c29e`
- `USER32!MoveWindow` at `0x14001c128`
- `USER32!MoveWindow` at `0x14001c1ba`
- `USER32!MoveWindow` at `0x14001c22d`
- `USER32!MoveWindow` at `0x14001c29e`
- `USER32!GetClientRect` at `0x14001c069`
- `USER32!GetClientRect` at `0x14001c084`
- `USER32!GetClientRect` at `0x14001c09b`
- `USER32!GetClientRect` at `0x14001c069`
- `USER32!GetClientRect` at `0x14001c084`
- `USER32!GetClientRect` at `0x14001c09b`

## pseudocode

```c
__int64 __fastcall CExpInterDlg::OnDialogResize(CExpInterDlg *this, __int64 a2, WPARAM a3, LPARAM a4)
{
  HWND v5; // rcx
  LONG right; // ebx
  LONG bottom; // r14d
  LONG v10; // esi
  bool v11; // zf
  LONG v12; // r15d
  HWND v13; // rcx
  int v14; // eax
  LONG left; // edx
  HWND v16; // rcx
  LONG top; // ecx
  HWND DlgItem; // rax
  HWND v19; // rcx
  HWND v20; // rbx
  LONG v21; // r9d
  HWND v22; // rax
  HWND v23; // rcx
  HWND v24; // rbx
  LONG v25; // r9d
  HWND v26; // rax
  HWND v27; // rcx
  HWND v28; // rbx
  struct tagRECT Rect; // [rsp+30h] [rbp-20h] BYREF

  v5 = (HWND)*((_QWORD *)this + 1);
  Rect = 0;
  GetClientRect(v5, &Rect);
  right = Rect.right;
  bottom = Rect.bottom;
  GetClientRect(*((HWND *)this + 10), &Rect);
  v10 = Rect.bottom;
  GetClientRect(*((HWND *)this + 11), &Rect);
  v11 = *((_DWORD *)this + 36) == 1;
  v12 = Rect.bottom;
  v13 = (HWND)*((_QWORD *)this + 1);
  Rect = (struct tagRECT)_mm_load_si128((const __m128i *)&_xmm);
  if ( v11 )
  {
    MapDialogRect(v13, &Rect);
    v14 = *((_DWORD *)this + 44);
    left = v14 + Rect.left;
    Rect.left += v14;
    right -= v14;
  }
  else
  {
    MapDialogRect(v13, &Rect);
    left = Rect.left;
  }
  Rect.bottom = bottom - Rect.bottom - v12 - v10;
  v16 = (HWND)*((_QWORD *)this + 13);
  Rect.right = right - Rect.right;
  Rect.top += v10;
  MoveWindow(v16, left, Rect.top, Rect.right, Rect.bottom, 1);
  top = Rect.top;
  *((_DWORD *)this + 45) = Rect.top;
  *((_DWORD *)this + 47) = Rect.bottom + top;
  DlgItem = GetDlgItem(*((HWND *)this + 1), 1035);
  v19 = (HWND)*((_QWORD *)this + 1);
  v20 = DlgItem;
  Rect = (struct tagRECT)_mm_load_si128((const __m128i *)&_xmm);
  MapDialogRect(v19, &Rect);
  v21 = *((_DWORD *)this + 44) - Rect.right;
  Rect.top += v10;
  Rect.right = v21;
  Rect.bottom = bottom - Rect.bottom - v12 - v10;
  MoveWindow(v20, Rect.left, Rect.top, v21, Rect.bottom, 1);
  v22 = GetDlgItem(*((HWND *)this + 1), 1036);
  v23 = (HWND)*((_QWORD *)this + 1);
  v24 = v22;
  Rect = (struct tagRECT)_mm_load_si128((const __m128i *)&_xmm);
  MapDialogRect(v23, &Rect);
  v25 = *((_DWORD *)this + 44) - Rect.right;
  Rect.top = bottom - Rect.top - v12;
  Rect.right = v25;
  MoveWindow(v24, Rect.left, Rect.top, v25, Rect.bottom, 1);
  v26 = GetDlgItem(*((HWND *)this + 1), 1037);
  v27 = (HWND)*((_QWORD *)this + 1);
  v28 = v26;
  Rect = (struct tagRECT)_mm_load_si128((const __m128i *)&_xmm);
  MapDialogRect(v27, &Rect);
  Rect.left = *((_DWORD *)this + 44) - Rect.left;
  Rect.top = bottom - Rect.top - v12;
  MoveWindow(v28, Rect.left, Rect.top, Rect.right, Rect.bottom, 1);
  InvalidateRect(v28, 0, 1);
  UpdateWindow(v28);
  SendMessageW(*((HWND *)this + 11), 5u, a3, a4);
  InvalidateRect(*((HWND *)this + 1), 0, 1);
  UpdateWindow(*((HWND *)this + 1));
  return 0;
}

```

## disassembly

```asm
0x14001c02c  mov     [rsp-38h+arg_8], rbx
0x14001c031  push    rbp
0x14001c032  push    rsi
0x14001c033  push    rdi
0x14001c034  push    r12
0x14001c036  push    r13
0x14001c038  push    r14
0x14001c03a  push    r15
0x14001c03c  mov     rbp, rsp
0x14001c03f  sub     rsp, 50h
0x14001c043  mov     rax, cs:__security_cookie
0x14001c04a  xor     rax, rsp
0x14001c04d  mov     [rbp+var_10], rax
0x14001c051  mov     rdi, rcx
0x14001c054  lea     rdx, [rbp+Rect]; lpRect
0x14001c058  mov     rcx, [rcx+8]; hWnd
0x14001c05c  xorps   xmm0, xmm0
0x14001c05f  movups  xmmword ptr [rbp+Rect.left], xmm0
0x14001c063  mov     r13, r9
0x14001c066  mov     r12, r8
0x14001c069  call    cs:__imp_GetClientRect
0x14001c070  nop     dword ptr [rax+rax+00h]
0x14001c075  mov     rcx, [rdi+50h]; hWnd
0x14001c079  lea     rdx, [rbp+Rect]; lpRect
0x14001c07d  mov     ebx, [rbp+Rect.right]
0x14001c080  mov     r14d, [rbp+Rect.bottom]
0x14001c084  call    cs:__imp_GetClientRect
0x14001c08b  nop     dword ptr [rax+rax+00h]
0x14001c090  mov     rcx, [rdi+58h]; hWnd
0x14001c094  lea     rdx, [rbp+Rect]; lpRect
0x14001c098  mov     esi, [rbp+Rect.bottom]
0x14001c09b  call    cs:__imp_GetClientRect
0x14001c0a2  nop     dword ptr [rax+rax+00h]
0x14001c0a7  cmp     dword ptr [rdi+90h], 1
0x14001c0ae  lea     rdx, [rbp+Rect]; lpRect
0x14001c0b2  movdqa  xmm0, cs:__xmm@00000008000000080000000400000004
0x14001c0ba  mov     r15d, [rbp+Rect.bottom]
0x14001c0be  mov     rcx, [rdi+8]; hDlg
0x14001c0c2  movdqu  xmmword ptr [rbp+Rect.left], xmm0
0x14001c0c7  jnz     short loc_14001C0E7
0x14001c0c9  call    cs:__imp_MapDialogRect
0x14001c0d0  nop     dword ptr [rax+rax+00h]
0x14001c0d5  mov     edx, [rbp+Rect.left]
0x14001c0d8  mov     eax, [rdi+0B0h]
0x14001c0de  add     edx, eax
0x14001c0e0  mov     [rbp+Rect.left], edx
0x14001c0e3  sub     ebx, eax
0x14001c0e5  jmp     short loc_14001C0F6
0x14001c0e7  call    cs:__imp_MapDialogRect
0x14001c0ee  nop     dword ptr [rax+rax+00h]
0x14001c0f3  mov     edx, [rbp+Rect.left]; X
0x14001c0f6  mov     r8d, [rbp+Rect.top]
0x14001c0fa  mov     ecx, r14d
0x14001c0fd  sub     ecx, [rbp+Rect.bottom]
0x14001c100  add     r8d, esi; Y
0x14001c103  sub     ebx, [rbp+Rect.right]
0x14001c106  sub     ecx, r15d
0x14001c109  sub     ecx, esi
0x14001c10b  mov     [rsp+50h+bRepaint], 1; bRepaint
0x14001c113  mov     [rbp+Rect.bottom], ecx
0x14001c116  mov     r9d, ebx; nWidth
0x14001c119  mov     [rsp+50h+nHeight], ecx; nHeight
0x14001c11d  mov     rcx, [rdi+68h]; hWnd
0x14001c121  mov     [rbp+Rect.right], ebx
0x14001c124  mov     [rbp+Rect.top], r8d
0x14001c128  call    cs:__imp_MoveWindow
0x14001c12f  nop     dword ptr [rax+rax+00h]
0x14001c134  mov     ecx, [rbp+Rect.top]
0x14001c137  mov     edx, 40Bh; nIDDlgItem
0x14001c13c  mov     [rdi+0B4h], ecx
0x14001c142  add     ecx, [rbp+Rect.bottom]
0x14001c145  mov     [rdi+0BCh], ecx
0x14001c14b  mov     rcx, [rdi+8]; hDlg
0x14001c14f  call    cs:__imp_GetDlgItem
0x14001c156  nop     dword ptr [rax+rax+00h]
0x14001c15b  movdqa  xmm0, cs:__xmm@0000004c000000040000000400000004
0x14001c163  lea     rdx, [rbp+Rect]; lpRect
0x14001c167  mov     rcx, [rdi+8]; hDlg
0x14001c16b  mov     rbx, rax
0x14001c16e  movdqu  xmmword ptr [rbp+Rect.left], xmm0
0x14001c173  call    cs:__imp_MapDialogRect
0x14001c17a  nop     dword ptr [rax+rax+00h]
0x14001c17f  mov     r8d, [rbp+Rect.top]
0x14001c183  mov     eax, r14d
0x14001c186  sub     eax, [rbp+Rect.bottom]
0x14001c189  add     r8d, esi; Y
0x14001c18c  mov     r9d, [rdi+0B0h]
0x14001c193  sub     eax, r15d
0x14001c196  sub     r9d, [rbp+Rect.right]; nWidth
0x14001c19a  sub     eax, esi
0x14001c19c  mov     edx, [rbp+Rect.left]; X
0x14001c19f  mov     esi, 1
0x14001c1a4  mov     [rsp+50h+bRepaint], esi; bRepaint
0x14001c1a8  mov     rcx, rbx; hWnd
0x14001c1ab  mov     [rsp+50h+nHeight], eax; nHeight
0x14001c1af  mov     [rbp+Rect.top], r8d
0x14001c1b3  mov     [rbp+Rect.right], r9d
0x14001c1b7  mov     [rbp+Rect.bottom], eax
0x14001c1ba  call    cs:__imp_MoveWindow
0x14001c1c1  nop     dword ptr [rax+rax+00h]
0x14001c1c6  mov     rcx, [rdi+8]; hDlg
0x14001c1ca  mov     edx, 40Ch; nIDDlgItem
0x14001c1cf  call    cs:__imp_GetDlgItem
0x14001c1d6  nop     dword ptr [rax+rax+00h]
0x14001c1db  movdqa  xmm0, cs:__xmm@00000030000000040000004400000004
0x14001c1e3  lea     rdx, [rbp+Rect]; lpRect
0x14001c1e7  mov     rcx, [rdi+8]; hDlg
0x14001c1eb  mov     rbx, rax
0x14001c1ee  movdqu  xmmword ptr [rbp+Rect.left], xmm0
0x14001c1f3  call    cs:__imp_MapDialogRect
0x14001c1fa  nop     dword ptr [rax+rax+00h]
0x14001c1ff  mov     r9d, [rdi+0B0h]
0x14001c206  mov     r8d, r14d
0x14001c209  sub     r8d, [rbp+Rect.top]
0x14001c20d  mov     rcx, rbx; hWnd
0x14001c210  sub     r9d, [rbp+Rect.right]; nWidth
0x14001c214  sub     r8d, r15d; Y
0x14001c217  mov     eax, [rbp+Rect.bottom]
0x14001c21a  mov     edx, [rbp+Rect.left]; X
0x14001c21d  mov     [rsp+50h+bRepaint], esi; bRepaint
0x14001c221  mov     [rbp+Rect.top], r8d
0x14001c225  mov     [rbp+Rect.right], r9d
0x14001c229  mov     [rsp+50h+nHeight], eax; nHeight
0x14001c22d  call    cs:__imp_MoveWindow
0x14001c234  nop     dword ptr [rax+rax+00h]
0x14001c239  mov     rcx, [rdi+8]; hDlg
0x14001c23d  mov     edx, 40Dh; nIDDlgItem
0x14001c242  call    cs:__imp_GetDlgItem
0x14001c249  nop     dword ptr [rax+rax+00h]
0x14001c24e  movdqa  xmm0, cs:__xmm@0000000c000000360000001000000036
0x14001c256  lea     rdx, [rbp+Rect]; lpRect
0x14001c25a  mov     rcx, [rdi+8]; hDlg
0x14001c25e  mov     rbx, rax
0x14001c261  movdqu  xmmword ptr [rbp+Rect.left], xmm0
0x14001c266  call    cs:__imp_MapDialogRect
0x14001c26d  nop     dword ptr [rax+rax+00h]
0x14001c272  mov     edx, [rdi+0B0h]
0x14001c278  sub     edx, [rbp+Rect.left]; X
0x14001c27b  sub     r14d, [rbp+Rect.top]
0x14001c27f  mov     [rbp+Rect.left], edx
0x14001c282  sub     r14d, r15d
0x14001c285  mov     eax, [rbp+Rect.bottom]
0x14001c288  mov     r8d, r14d; Y
0x14001c28b  mov     r9d, [rbp+Rect.right]; nWidth
0x14001c28f  mov     rcx, rbx; hWnd
0x14001c292  mov     [rsp+50h+bRepaint], esi; bRepaint
0x14001c296  mov     [rsp+50h+nHeight], eax; nHeight
0x14001c29a  mov     [rbp+Rect.top], r14d
0x14001c29e  call    cs:__imp_MoveWindow
0x14001c2a5  nop     dword ptr [rax+rax+00h]
0x14001c2aa  mov     r8d, esi; bErase
0x14001c2ad  xor     edx, edx; lpRect
0x14001c2af  mov     rcx, rbx; hWnd
0x14001c2b2  call    cs:__imp_InvalidateRect
0x14001c2b9  nop     dword ptr [rax+rax+00h]
0x14001c2be  mov     rcx, rbx; hWnd
0x14001c2c1  call    cs:__imp_UpdateWindow
0x14001c2c8  nop     dword ptr [rax+rax+00h]
0x14001c2cd  mov     rcx, [rdi+58h]; hWnd
0x14001c2d1  lea     edx, [rsi+4]; Msg
0x14001c2d4  mov     r9, r13; lParam
0x14001c2d7  mov     r8, r12; wParam
0x14001c2da  call    cs:__imp_SendMessageW
0x14001c2e1  nop     dword ptr [rax+rax+00h]
0x14001c2e6  mov     rcx, [rdi+8]; hWnd
0x14001c2ea  mov     r8d, esi; bErase
0x14001c2ed  xor     edx, edx; lpRect
0x14001c2ef  call    cs:__imp_InvalidateRect
0x14001c2f6  nop     dword ptr [rax+rax+00h]
0x14001c2fb  mov     rcx, [rdi+8]; hWnd
0x14001c2ff  call    cs:__imp_UpdateWindow
0x14001c306  nop     dword ptr [rax+rax+00h]
0x14001c30b  xor     eax, eax
0x14001c30d  mov     rcx, [rbp+var_10]
0x14001c311  xor     rcx, rsp; StackCookie
0x14001c314  call    __security_check_cookie
0x14001c319  mov     rbx, [rsp+50h+arg_8]
0x14001c321  add     rsp, 50h
0x14001c325  pop     r15
0x14001c327  pop     r14
0x14001c329  pop     r13
0x14001c32b  pop     r12
0x14001c32d  pop     rdi
0x14001c32e  pop     rsi
0x14001c32f  pop     rbp
0x14001c330  retn
```
