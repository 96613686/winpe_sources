# anchor

- ea: `0x18002de9c`
- end: `0x18002e0a6`
- name: `anchor`
- size: `522`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18002d670`
- `0x18002e4b4`

## callees

- `0x1800115f0`
- `0x18002de9c`
- `0x18002e3b4`

## import_xrefs

- `USER32!GetWindowLongW` at `0x18002df0a`
- `USER32!GetWindowLongW` at `0x18002df39`
- `USER32!GetWindowLongW` at `0x18002df81`
- `USER32!GetWindowLongW` at `0x18002dfc0`
- `USER32!GetWindowLongW` at `0x18002df0a`
- `USER32!GetWindowLongW` at `0x18002df39`
- `USER32!GetWindowLongW` at `0x18002df81`
- `USER32!GetWindowLongW` at `0x18002dfc0`
- `USER32!SetWindowPos` at `0x18002e07b`
- `USER32!SetWindowPos` at `0x18002e07b`
- `USER32!ScreenToClient` at `0x18002dfdc`
- `USER32!ScreenToClient` at `0x18002dfdc`
- `USER32!SetWindowLongW` at `0x18002df71`
- `USER32!SetWindowLongW` at `0x18002df93`
- `USER32!SetWindowLongW` at `0x18002df71`
- `USER32!SetWindowLongW` at `0x18002df93`
- `USER32!MoveWindow` at `0x18002e040`
- `USER32!MoveWindow` at `0x18002e040`
- `USER32!GetWindowRect` at `0x18002df22`
- `USER32!GetWindowRect` at `0x18002dfa5`
- `USER32!GetWindowRect` at `0x18002df22`
- `USER32!GetWindowRect` at `0x18002dfa5`

## pseudocode

```c
BOOL __fastcall anchor(__int64 a1)
{
  int v2; // r14d
  HWND v3; // rcx
  int v4; // r15d
  int v5; // r12d
  int v6; // ecx
  LONG v7; // r8d
  LONG WindowLongW; // eax
  int nHeight; // esi
  int v10; // ebx
  LONG v11; // eax
  HWND v12; // rcx
  bool v13; // cf
  LONG left; // eax
  LONG v15; // edx
  int v16; // r9d
  int v17; // ebx
  LONG v18; // eax
  struct tagRECT Rect; // [rsp+40h] [rbp-20h] BYREF

  *(_DWORD *)(a1 + 64) &= ~8u;
  Rect = 0;
  v2 = 0;
  isgoodbuddy();
  v3 = *(HWND *)(a1 + 56);
  v4 = *(_DWORD *)(a1 + 16) & 0x800000;
  if ( v3 && (*(_BYTE *)(a1 + 16) & 0xC) != 0 )
  {
    v5 = 1;
    if ( *(_DWORD *)(a1 + 84) == 1 || (GetWindowLongW(v3, -20) & 0x200) != 0 )
      *(_DWORD *)(a1 + 64) |= 0x10u;
    GetWindowRect(*(HWND *)(a1 + 56), &Rect);
    if ( *(_DWORD *)(a1 + 84) == 1 || (GetWindowLongW(*(HWND *)(a1 + 56), -16) & 0x800000) != 0 )
    {
      v6 = *(_DWORD *)(a1 + 64);
      *(_DWORD *)(a1 + 16) &= ~0x800000u;
      v7 = *(_DWORD *)(a1 + 16);
      *(_DWORD *)(a1 + 64) = v6 | 8;
      v2 = g_cxBorder * (((v6 & 0x10) != 0) + 1);
      SetWindowLongW(*(HWND *)a1, -16, v7);
      WindowLongW = GetWindowLongW(*(HWND *)a1, -20);
      SetWindowLongW(*(HWND *)a1, -20, WindowLongW & 0xFFFFFDFF);
    }
  }
  else
  {
    v5 = 0;
    GetWindowRect(*(HWND *)a1, &Rect);
  }
  nHeight = Rect.bottom - Rect.top;
  v10 = Rect.right - Rect.left;
  v11 = GetWindowLongW(*(HWND *)(a1 + 8), -20);
  v12 = *(HWND *)(a1 + 8);
  v13 = (v11 & 0x400000) != 0;
  left = Rect.left;
  if ( v13 )
    left = Rect.right;
  Rect.left = left;
  ScreenToClient(v12, (LPPOINT)&Rect);
  v15 = Rect.left;
  v16 = v10 + Rect.left;
  Rect.right = v10 + Rect.left;
  if ( v5 )
  {
    v17 = g_cxVScroll - g_cxBorder;
    if ( g_cxVScroll - g_cxBorder > nHeight )
      v17 = nHeight;
    v10 = v2 + v17;
    if ( (*(_BYTE *)(a1 + 16) & 8) != 0 )
    {
      v15 = v10 - v2 + Rect.left;
      Rect.right = v10 + Rect.left;
    }
    else
    {
      v18 = v16 - v10;
      v16 = v2 + v16 - v10;
      Rect.left = v18;
    }
    MoveWindow(*(HWND *)(a1 + 56), v15, Rect.top, v16 - v15, nHeight, 1);
    v15 = Rect.left;
  }
  else if ( (*(_BYTE *)(a1 + 16) & 0x40) == 0 )
  {
    v10 = g_cxVScroll + (v4 != 0 ? 2 : 0);
  }
  return SetWindowPos(*(HWND *)a1, 0, v15, Rect.top, v10, nHeight, 0x34u);
}

```

## disassembly

```asm
0x18002de9c  mov     [rsp-28h+arg_8], rbx
0x18002dea1  mov     [rsp-28h+arg_10], rsi
0x18002dea6  push    rbp
0x18002dea7  push    rdi
0x18002dea8  push    r12
0x18002deaa  push    r14
0x18002deac  push    r15
0x18002deae  mov     rbp, rsp
0x18002deb1  sub     rsp, 60h
0x18002deb5  mov     rax, cs:__security_cookie
0x18002debc  xor     rax, rsp
0x18002debf  mov     [rbp+var_10], rax
0x18002dec3  and     dword ptr [rcx+40h], 0FFFFFFF7h
0x18002dec7  xorps   xmm0, xmm0
0x18002deca  movups  xmmword ptr [rbp+Rect.left], xmm0
0x18002dece  mov     rdi, rcx
0x18002ded1  xor     r14d, r14d
0x18002ded4  call    isgoodbuddy
0x18002ded9  mov     r15d, [rdi+10h]
0x18002dedd  mov     ebx, 800000h
0x18002dee2  mov     rcx, [rdi+38h]; hWnd
0x18002dee6  and     r15d, ebx
0x18002dee9  test    rcx, rcx
0x18002deec  jz      loc_18002DF9B
0x18002def2  test    byte ptr [rdi+10h], 0Ch
0x18002def6  jz      loc_18002DF9B
0x18002defc  lea     r12d, [r14+1]
0x18002df00  cmp     [rdi+54h], r12d
0x18002df04  jz      short loc_18002DF16
0x18002df06  lea     edx, [r14-14h]; nIndex
0x18002df0a  call    cs:__imp_GetWindowLongW
0x18002df10  bt      eax, 9
0x18002df14  jnb     short loc_18002DF1A
0x18002df16  or      dword ptr [rdi+40h], 10h
0x18002df1a  mov     rcx, [rdi+38h]; hWnd
0x18002df1e  lea     rdx, [rbp+Rect]; lpRect
0x18002df22  call    cs:__imp_GetWindowRect
0x18002df28  mov     esi, 0FFFFFFF0h
0x18002df2d  cmp     [rdi+54h], r12d
0x18002df31  jz      short loc_18002DF43
0x18002df33  mov     rcx, [rdi+38h]; hWnd
0x18002df37  mov     edx, esi; nIndex
0x18002df39  call    cs:__imp_GetWindowLongW
0x18002df3f  test    ebx, eax
0x18002df41  jz      short loc_18002DFAB
0x18002df43  mov     ecx, [rdi+40h]
0x18002df46  mov     edx, esi; nIndex
0x18002df48  mov     eax, ecx
0x18002df4a  and     al, 10h
0x18002df4c  neg     al
0x18002df4e  sbb     r14d, r14d
0x18002df51  btr     dword ptr [rdi+10h], 17h
0x18002df56  mov     r8d, [rdi+10h]; dwNewLong
0x18002df5a  or      ecx, 8
0x18002df5d  neg     r14d
0x18002df60  mov     [rdi+40h], ecx
0x18002df63  mov     rcx, [rdi]; hWnd
0x18002df66  inc     r14d
0x18002df69  imul    r14d, cs:g_cxBorder
0x18002df71  call    cs:__imp_SetWindowLongW
0x18002df77  mov     rcx, [rdi]; hWnd
0x18002df7a  mov     ebx, 0FFFFFFECh
0x18002df7f  mov     edx, ebx; nIndex
0x18002df81  call    cs:__imp_GetWindowLongW
0x18002df87  mov     rcx, [rdi]; hWnd
0x18002df8a  mov     edx, ebx; nIndex
0x18002df8c  btr     eax, 9
0x18002df90  mov     r8d, eax; dwNewLong
0x18002df93  call    cs:__imp_SetWindowLongW
0x18002df99  jmp     short loc_18002DFAB
0x18002df9b  mov     rcx, [rdi]; hWnd
0x18002df9e  lea     rdx, [rbp+Rect]; lpRect
0x18002dfa2  xor     r12d, r12d
0x18002dfa5  call    cs:__imp_GetWindowRect
0x18002dfab  mov     esi, [rbp+Rect.bottom]
0x18002dfae  mov     edx, 0FFFFFFECh; nIndex
0x18002dfb3  mov     ebx, [rbp+Rect.right]
0x18002dfb6  mov     rcx, [rdi+8]; hWnd
0x18002dfba  sub     esi, [rbp+Rect.top]
0x18002dfbd  sub     ebx, [rbp+Rect.left]
0x18002dfc0  call    cs:__imp_GetWindowLongW
0x18002dfc6  mov     rcx, [rdi+8]; hWnd
0x18002dfca  lea     rdx, [rbp+Rect]; lpPoint
0x18002dfce  bt      eax, 16h
0x18002dfd2  mov     eax, [rbp+Rect.left]
0x18002dfd5  cmovb   eax, [rbp+Rect.right]
0x18002dfd9  mov     [rbp+Rect.left], eax
0x18002dfdc  call    cs:__imp_ScreenToClient
0x18002dfe2  mov     edx, [rbp+Rect.left]; X
0x18002dfe5  lea     r9d, [rbx+rdx]
0x18002dfe9  mov     [rbp+Rect.right], r9d
0x18002dfed  test    r12d, r12d
0x18002dff0  jz      short loc_18002E04B
0x18002dff2  mov     ebx, cs:g_cxVScroll
0x18002dff8  sub     ebx, cs:g_cxBorder
0x18002dffe  cmp     ebx, esi
0x18002e000  cmovg   ebx, esi
0x18002e003  add     ebx, r14d
0x18002e006  test    byte ptr [rdi+10h], 8
0x18002e00a  jz      short loc_18002E01D
0x18002e00c  mov     ecx, edx
0x18002e00e  mov     eax, ebx
0x18002e010  sub     eax, r14d
0x18002e013  add     edx, eax
0x18002e015  lea     eax, [rbx+rcx]
0x18002e018  mov     [rbp+Rect.right], eax
0x18002e01b  jmp     short loc_18002E029
0x18002e01d  sub     r9d, ebx
0x18002e020  mov     eax, r9d
0x18002e023  add     r9d, r14d
0x18002e026  mov     [rbp+Rect.left], eax
0x18002e029  mov     r8d, [rbp+Rect.top]; Y
0x18002e02d  sub     r9d, edx; nWidth
0x18002e030  mov     rcx, [rdi+38h]; hWnd
0x18002e034  mov     [rsp+60h+bRepaint], 1; bRepaint
0x18002e03c  mov     [rsp+60h+nHeight], esi; nHeight
0x18002e040  call    cs:__imp_MoveWindow
0x18002e046  mov     edx, [rbp+Rect.left]
0x18002e049  jmp     short loc_18002E05F
0x18002e04b  test    byte ptr [rdi+10h], 40h
0x18002e04f  jnz     short loc_18002E05F
0x18002e051  neg     r15d
0x18002e054  sbb     ebx, ebx
0x18002e056  and     ebx, 2
0x18002e059  add     ebx, cs:g_cxVScroll
0x18002e05f  mov     r9d, [rbp+Rect.top]; Y
0x18002e063  mov     r8d, edx; X
0x18002e066  mov     rcx, [rdi]; hWnd
0x18002e069  xor     edx, edx; hWndInsertAfter
0x18002e06b  mov     [rsp+60h+uFlags], 34h ; '4'; uFlags
0x18002e073  mov     [rsp+60h+bRepaint], esi; cy
0x18002e077  mov     [rsp+60h+nHeight], ebx; cx
0x18002e07b  call    cs:__imp_SetWindowPos
0x18002e081  mov     rcx, [rbp+var_10]
0x18002e085  xor     rcx, rsp; StackCookie
0x18002e088  call    __security_check_cookie
0x18002e08d  lea     r11, [rsp+60h+var_s0]
0x18002e092  mov     rbx, [r11+38h]
0x18002e096  mov     rsi, [r11+40h]
0x18002e09a  mov     rsp, r11
0x18002e09d  pop     r15
0x18002e09f  pop     r14
0x18002e0a1  pop     r12
0x18002e0a3  pop     rdi
0x18002e0a4  pop     rbp
0x18002e0a5  retn
```
