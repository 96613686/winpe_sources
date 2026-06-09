# CenterDlg

- ea: `0x18001450c`
- end: `0x180014635`
- name: `CenterDlg`
- size: `297`
- prototype: `BOOL __fastcall(HWND hWnd)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180003230`
- `0x180003570`
- `0x180003e10`
- `0x180005c00`
- `0x18000af80`
- `0x18000b9c0`
- `0x1800147c0`

## callees

- `0x18001450c`
- `0x180014ae0`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x18001455b`
- `USER32!GetSystemMetrics` at `0x180014567`
- `USER32!GetSystemMetrics` at `0x1800145c5`
- `USER32!GetSystemMetrics` at `0x1800145e3`
- `USER32!GetSystemMetrics` at `0x18001455b`
- `USER32!GetSystemMetrics` at `0x180014567`
- `USER32!GetSystemMetrics` at `0x1800145c5`
- `USER32!GetSystemMetrics` at `0x1800145e3`
- `USER32!MoveWindow` at `0x18001460a`
- `USER32!MoveWindow` at `0x18001460a`
- `USER32!GetWindowRect` at `0x180014579`
- `USER32!GetWindowRect` at `0x180014586`
- `USER32!GetWindowRect` at `0x180014579`
- `USER32!GetWindowRect` at `0x180014586`
- `USER32!GetParent` at `0x180014544`
- `USER32!GetParent` at `0x180014544`

## pseudocode

```c
BOOL __fastcall CenterDlg(HWND hWnd)
{
  HWND Parent; // rax
  int v3; // r14d
  int nHeight; // r15d
  int v5; // edi
  int v6; // ebx
  int v7; // ecx
  int v8; // edx
  struct tagRECT Rect; // [rsp+30h] [rbp-30h] BYREF
  struct tagRECT v11; // [rsp+40h] [rbp-20h] BYREF

  Rect = 0;
  v11 = 0;
  Parent = GetParent(hWnd);
  if ( Parent )
  {
    GetWindowRect(Parent, &Rect);
  }
  else
  {
    *(_QWORD *)&Rect.left = 0;
    Rect.right = GetSystemMetrics(0);
    Rect.bottom = GetSystemMetrics(1);
  }
  GetWindowRect(hWnd, &v11);
  v3 = v11.right - v11.left;
  nHeight = v11.bottom - v11.top;
  v5 = ((Rect.left + Rect.right) >> 1) - ((v11.right - v11.left) >> 1);
  v6 = ((Rect.top + Rect.bottom) >> 1) - ((v11.bottom - v11.top) >> 1);
  if ( v5 > 0 )
  {
    v7 = v5 + v3 - GetSystemMetrics(0);
    if ( v7 > 0 )
      v5 -= v7;
  }
  else
  {
    v5 = 1;
  }
  if ( v6 > 0 )
  {
    v8 = v6 + nHeight - GetSystemMetrics(1);
    if ( v8 > 0 )
      v6 -= v8;
  }
  else
  {
    v6 = 1;
  }
  return MoveWindow(hWnd, v5, v6, v3, nHeight, 1);
}

```

## disassembly

```asm
0x18001450c  mov     [rsp-28h+arg_8], rbx
0x180014511  mov     [rsp-28h+arg_10], rsi
0x180014516  push    rbp
0x180014517  push    rdi
0x180014518  push    r12
0x18001451a  push    r14
0x18001451c  push    r15
0x18001451e  mov     rbp, rsp
0x180014521  sub     rsp, 60h
0x180014525  mov     rax, cs:__security_cookie
0x18001452c  xor     rax, rsp
0x18001452f  mov     [rbp+var_10], rax
0x180014533  xorps   xmm0, xmm0
0x180014536  xorps   xmm1, xmm1
0x180014539  movups  xmmword ptr [rbp+Rect.left], xmm0
0x18001453d  mov     rsi, rcx
0x180014540  movups  xmmword ptr [rbp+var_20.left], xmm1
0x180014544  call    cs:__imp_GetParent
0x18001454a  mov     r12d, 1
0x180014550  test    rax, rax
0x180014553  jnz     short loc_180014572
0x180014555  xor     ecx, ecx; nIndex
0x180014557  mov     qword ptr [rbp+Rect.left], rax
0x18001455b  call    cs:__imp_GetSystemMetrics
0x180014561  mov     ecx, r12d; nIndex
0x180014564  mov     [rbp+Rect.right], eax
0x180014567  call    cs:__imp_GetSystemMetrics
0x18001456d  mov     [rbp+Rect.bottom], eax
0x180014570  jmp     short loc_18001457F
0x180014572  lea     rdx, [rbp+Rect]; lpRect
0x180014576  mov     rcx, rax; hWnd
0x180014579  call    cs:__imp_GetWindowRect
0x18001457f  lea     rdx, [rbp+var_20]; lpRect
0x180014583  mov     rcx, rsi; hWnd
0x180014586  call    cs:__imp_GetWindowRect
0x18001458c  mov     r14d, [rbp+var_20.right]
0x180014590  sub     r14d, [rbp+var_20.left]
0x180014594  mov     edi, [rbp+Rect.right]
0x180014597  mov     eax, r14d
0x18001459a  add     edi, [rbp+Rect.left]
0x18001459d  mov     r15d, [rbp+var_20.bottom]
0x1800145a1  sub     r15d, [rbp+var_20.top]
0x1800145a5  mov     ebx, [rbp+Rect.bottom]
0x1800145a8  add     ebx, [rbp+Rect.top]
0x1800145ab  sar     eax, 1
0x1800145ad  sar     edi, 1
0x1800145af  sub     edi, eax
0x1800145b1  sar     ebx, 1
0x1800145b3  mov     eax, r15d
0x1800145b6  sar     eax, 1
0x1800145b8  sub     ebx, eax
0x1800145ba  test    edi, edi
0x1800145bc  jg      short loc_1800145C3
0x1800145be  mov     edi, r12d
0x1800145c1  jmp     short loc_1800145D7
0x1800145c3  xor     ecx, ecx; nIndex
0x1800145c5  call    cs:__imp_GetSystemMetrics
0x1800145cb  lea     ecx, [rdi+r14]
0x1800145cf  sub     ecx, eax
0x1800145d1  test    ecx, ecx
0x1800145d3  jle     short loc_1800145D7
0x1800145d5  sub     edi, ecx
0x1800145d7  test    ebx, ebx
0x1800145d9  jg      short loc_1800145E0
0x1800145db  mov     ebx, r12d
0x1800145de  jmp     short loc_1800145F5
0x1800145e0  mov     ecx, r12d; nIndex
0x1800145e3  call    cs:__imp_GetSystemMetrics
0x1800145e9  lea     edx, [rbx+r15]
0x1800145ed  sub     edx, eax
0x1800145ef  test    edx, edx
0x1800145f1  jle     short loc_1800145F5
0x1800145f3  sub     ebx, edx
0x1800145f5  mov     [rsp+60h+bRepaint], r12d; bRepaint
0x1800145fa  mov     r9d, r14d; nWidth
0x1800145fd  mov     r8d, ebx; Y
0x180014600  mov     [rsp+60h+nHeight], r15d; nHeight
0x180014605  mov     edx, edi; X
0x180014607  mov     rcx, rsi; hWnd
0x18001460a  call    cs:__imp_MoveWindow
0x180014610  mov     rcx, [rbp+var_10]
0x180014614  xor     rcx, rsp; StackCookie
0x180014617  call    __security_check_cookie
0x18001461c  lea     r11, [rsp+60h+var_s0]
0x180014621  mov     rbx, [r11+38h]
0x180014625  mov     rsi, [r11+40h]
0x180014629  mov     rsp, r11
0x18001462c  pop     r15
0x18001462e  pop     r14
0x180014630  pop     r12
0x180014632  pop     rdi
0x180014633  pop     rbp
0x180014634  retn
```
