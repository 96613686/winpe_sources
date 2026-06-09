# CenterDialog

- ea: `0x1800b4850`
- end: `0x1800b49aa`
- name: `CenterDialog`
- size: `346`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800b49b0`
- `0x1800b7cb0`

## callees

- `0x180003d80`
- `0x1800b4850`

## import_xrefs

- `USER32!MoveWindow` at `0x1800b497b`
- `USER32!MoveWindow` at `0x1800b497b`
- `USER32!IsWindowVisible` at `0x1800b488a`
- `USER32!IsWindowVisible` at `0x1800b488a`
- `USER32!GetParent` at `0x1800b4879`
- `USER32!GetParent` at `0x1800b4879`
- `USER32!GetWindowRect` at `0x1800b489c`
- `USER32!GetWindowRect` at `0x1800b48ce`
- `USER32!GetWindowRect` at `0x1800b489c`
- `USER32!GetWindowRect` at `0x1800b48ce`
- `USER32!GetSystemMetrics` at `0x1800b48ad`
- `USER32!GetSystemMetrics` at `0x1800b48bc`
- `USER32!GetSystemMetrics` at `0x1800b4931`
- `USER32!GetSystemMetrics` at `0x1800b4953`
- `USER32!GetSystemMetrics` at `0x1800b48ad`
- `USER32!GetSystemMetrics` at `0x1800b48bc`
- `USER32!GetSystemMetrics` at `0x1800b4931`
- `USER32!GetSystemMetrics` at `0x1800b4953`

## pseudocode

```c
BOOL __fastcall CenterDialog(HWND hWnd)
{
  HWND Parent; // rax
  HWND v3; // rbx
  BOOL result; // eax
  int nHeight; // ebp
  int v6; // r14d
  int v7; // edi
  int v8; // ebx
  int v9; // ecx
  int v10; // edx
  tagRECT Rect; // [rsp+30h] [rbp-48h] BYREF
  struct tagRECT v12; // [rsp+40h] [rbp-38h] BYREF

  Rect = 0;
  v12 = 0;
  Parent = GetParent(hWnd);
  v3 = Parent;
  if ( Parent && IsWindowVisible(Parent) )
  {
    result = GetWindowRect(v3, &Rect);
    if ( !result )
      return result;
  }
  else
  {
    Rect.right = GetSystemMetrics(0);
    Rect.bottom = GetSystemMetrics(1);
  }
  result = GetWindowRect(hWnd, &v12);
  if ( result )
  {
    nHeight = v12.bottom - v12.top;
    v6 = v12.right - v12.left;
    v7 = ((Rect.left + Rect.right) >> 1) - ((v12.right - v12.left) >> 1);
    v8 = ((Rect.top + Rect.bottom) >> 1) - ((v12.bottom - v12.top) >> 1);
    if ( v7 > 0 )
    {
      v9 = v7 + v6 - GetSystemMetrics(0);
      if ( v9 > 0 )
        v7 -= v9;
    }
    else
    {
      v7 = 1;
    }
    if ( v8 > 0 )
    {
      v10 = v8 + nHeight - GetSystemMetrics(1);
      if ( v10 > 0 )
        v8 -= v10;
    }
    else
    {
      v8 = 1;
    }
    return MoveWindow(hWnd, v7, v8, v6, nHeight, 1);
  }
  return result;
}

```

## disassembly

```asm
0x1800b4850  push    rbx
0x1800b4852  push    rsi
0x1800b4853  sub     rsp, 68h
0x1800b4857  mov     rax, cs:__security_cookie
0x1800b485e  xor     rax, rsp
0x1800b4861  mov     [rsp+78h+var_28], rax
0x1800b4866  xorps   xmm0, xmm0
0x1800b4869  xorps   xmm1, xmm1
0x1800b486c  movups  xmmword ptr [rsp+78h+Rect.left], xmm0
0x1800b4871  mov     rsi, rcx
0x1800b4874  movups  xmmword ptr [rsp+78h+var_38.left], xmm1
0x1800b4879  call    cs:__imp_GetParent
0x1800b487f  mov     rbx, rax
0x1800b4882  test    rax, rax
0x1800b4885  jz      short loc_1800B48AB
0x1800b4887  mov     rcx, rax; hWnd
0x1800b488a  call    cs:__imp_IsWindowVisible
0x1800b4890  test    eax, eax
0x1800b4892  jz      short loc_1800B48AB
0x1800b4894  lea     rdx, [rsp+78h+Rect]; lpRect
0x1800b4899  mov     rcx, rbx; hWnd
0x1800b489c  call    cs:__imp_GetWindowRect
0x1800b48a2  test    eax, eax
0x1800b48a4  jnz     short loc_1800B48C6
0x1800b48a6  jmp     loc_1800B4996
0x1800b48ab  xor     ecx, ecx; nIndex
0x1800b48ad  call    cs:__imp_GetSystemMetrics
0x1800b48b3  mov     ecx, 1; nIndex
0x1800b48b8  mov     [rsp+78h+Rect.right], eax
0x1800b48bc  call    cs:__imp_GetSystemMetrics
0x1800b48c2  mov     [rsp+78h+Rect.bottom], eax
0x1800b48c6  lea     rdx, [rsp+78h+var_38]; lpRect
0x1800b48cb  mov     rcx, rsi; hWnd
0x1800b48ce  call    cs:__imp_GetWindowRect
0x1800b48d4  test    eax, eax
0x1800b48d6  jz      loc_1800B4996
0x1800b48dc  mov     ebx, [rsp+78h+Rect.bottom]
0x1800b48e0  add     ebx, [rsp+78h+Rect.top]
0x1800b48e4  mov     [rsp+78h+arg_8], rbp
0x1800b48ec  mov     ebp, [rsp+78h+var_38.bottom]
0x1800b48f0  sub     ebp, [rsp+78h+var_38.top]
0x1800b48f4  mov     [rsp+78h+arg_10], rdi
0x1800b48fc  mov     edi, [rsp+78h+Rect.right]
0x1800b4900  add     edi, [rsp+78h+Rect.left]
0x1800b4904  mov     [rsp+78h+var_18], r14
0x1800b4909  mov     r14d, [rsp+78h+var_38.right]
0x1800b490e  sub     r14d, [rsp+78h+var_38.left]
0x1800b4913  sar     edi, 1
0x1800b4915  mov     eax, r14d
0x1800b4918  sar     eax, 1
0x1800b491a  sub     edi, eax
0x1800b491c  sar     ebx, 1
0x1800b491e  mov     eax, ebp
0x1800b4920  sar     eax, 1
0x1800b4922  sub     ebx, eax
0x1800b4924  test    edi, edi
0x1800b4926  jg      short loc_1800B492F
0x1800b4928  mov     edi, 1
0x1800b492d  jmp     short loc_1800B4943
0x1800b492f  xor     ecx, ecx; nIndex
0x1800b4931  call    cs:__imp_GetSystemMetrics
0x1800b4937  lea     ecx, [rdi+r14]
0x1800b493b  sub     ecx, eax
0x1800b493d  test    ecx, ecx
0x1800b493f  jle     short loc_1800B4943
0x1800b4941  sub     edi, ecx
0x1800b4943  test    ebx, ebx
0x1800b4945  jg      short loc_1800B494E
0x1800b4947  mov     ebx, 1
0x1800b494c  jmp     short loc_1800B4964
0x1800b494e  mov     ecx, 1; nIndex
0x1800b4953  call    cs:__imp_GetSystemMetrics
0x1800b4959  lea     edx, [rbx+rbp]
0x1800b495c  sub     edx, eax
0x1800b495e  test    edx, edx
0x1800b4960  jle     short loc_1800B4964
0x1800b4962  sub     ebx, edx
0x1800b4964  mov     [rsp+78h+bRepaint], 1; bRepaint
0x1800b496c  mov     r9d, r14d; nWidth
0x1800b496f  mov     r8d, ebx; Y
0x1800b4972  mov     [rsp+78h+nHeight], ebp; nHeight
0x1800b4976  mov     edx, edi; X
0x1800b4978  mov     rcx, rsi; hWnd
0x1800b497b  call    cs:__imp_MoveWindow
0x1800b4981  mov     r14, [rsp+78h+var_18]
0x1800b4986  mov     rdi, [rsp+78h+arg_10]
0x1800b498e  mov     rbp, [rsp+78h+arg_8]
0x1800b4996  mov     rcx, [rsp+78h+var_28]
0x1800b499b  xor     rcx, rsp; StackCookie
0x1800b499e  call    __security_check_cookie
0x1800b49a3  add     rsp, 68h
0x1800b49a7  pop     rsi
0x1800b49a8  pop     rbx
0x1800b49a9  retn
```
