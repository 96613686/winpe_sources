# CenterDialog(HWND__ *)

- ea: `0x100518ac4`
- end: `0x100518bf3`
- name: `?CenterDialog@@YAXPEAUHWND__@@@Z`
- size: `303`
- prototype: `void __fastcall(HWND hWnd)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x100518c00`
- `0x1005190b0`
- `0x10051baa0`
- `0x10051f6c0`

## callees

- `0x100518ac4`
- `0x100548210`

## import_xrefs

- `USER32!GetParent` at `0x100518aee`
- `USER32!GetParent` at `0x100518aee`
- `USER32!GetWindowRect` at `0x100518b16`
- `USER32!GetWindowRect` at `0x100518b44`
- `USER32!GetWindowRect` at `0x100518b16`
- `USER32!GetWindowRect` at `0x100518b44`
- `USER32!GetSystemMetrics` at `0x100518b28`
- `USER32!GetSystemMetrics` at `0x100518b34`
- `USER32!GetSystemMetrics` at `0x100518b83`
- `USER32!GetSystemMetrics` at `0x100518ba1`
- `USER32!GetSystemMetrics` at `0x100518b28`
- `USER32!GetSystemMetrics` at `0x100518b34`
- `USER32!GetSystemMetrics` at `0x100518b83`
- `USER32!GetSystemMetrics` at `0x100518ba1`
- `USER32!IsWindowVisible` at `0x100518b05`
- `USER32!IsWindowVisible` at `0x100518b05`
- `USER32!MoveWindow` at `0x100518bc8`
- `USER32!MoveWindow` at `0x100518bc8`

## pseudocode

```c
void __fastcall CenterDialog(HWND hWnd)
{
  HWND Parent; // rax
  HWND v3; // rbx
  int v4; // r15d
  int nHeight; // r14d
  int v6; // edi
  int v7; // ebx
  int v8; // ecx
  int v9; // edx
  tagRECT Rect; // [rsp+30h] [rbp-30h] BYREF
  struct tagRECT v11; // [rsp+40h] [rbp-20h] BYREF

  Parent = GetParent(hWnd);
  v3 = Parent;
  if ( Parent && IsWindowVisible(Parent) )
  {
    GetWindowRect(v3, &Rect);
  }
  else
  {
    Rect.top = 0;
    Rect.left = 0;
    Rect.right = GetSystemMetrics(0);
    Rect.bottom = GetSystemMetrics(1);
  }
  GetWindowRect(hWnd, &v11);
  v4 = v11.right - v11.left;
  nHeight = v11.bottom - v11.top;
  v6 = ((Rect.left + Rect.right) >> 1) - ((v11.right - v11.left) >> 1);
  v7 = ((Rect.top + Rect.bottom) >> 1) - ((v11.bottom - v11.top) >> 1);
  if ( v6 > 0 )
  {
    v8 = v6 + v4 - GetSystemMetrics(0);
    if ( v8 > 0 )
      v6 -= v8;
  }
  else
  {
    v6 = 1;
  }
  if ( v7 > 0 )
  {
    v9 = v7 + nHeight - GetSystemMetrics(1);
    if ( v9 > 0 )
      v7 -= v9;
  }
  else
  {
    v7 = 1;
  }
  MoveWindow(hWnd, v6, v7, v4, nHeight, 1);
}

```

## disassembly

```asm
0x100518ac4  mov     [rsp-28h+arg_8], rbx
0x100518ac9  mov     [rsp-28h+arg_10], rsi
0x100518ace  push    rbp
0x100518acf  push    rdi
0x100518ad0  push    r12
0x100518ad2  push    r14
0x100518ad4  push    r15
0x100518ad6  mov     rbp, rsp
0x100518ad9  sub     rsp, 60h
0x100518add  mov     rax, cs:__security_cookie
0x100518ae4  xor     rax, rsp
0x100518ae7  mov     [rbp+var_10], rax
0x100518aeb  mov     rsi, rcx
0x100518aee  call    cs:__imp_GetParent
0x100518af4  mov     rbx, rax
0x100518af7  mov     r12d, 1
0x100518afd  test    rax, rax
0x100518b00  jz      short loc_100518B1E
0x100518b02  mov     rcx, rax; hWnd
0x100518b05  call    cs:__imp_IsWindowVisible
0x100518b0b  test    eax, eax
0x100518b0d  jz      short loc_100518B1E
0x100518b0f  lea     rdx, [rbp+Rect]; lpRect
0x100518b13  mov     rcx, rbx; hWnd
0x100518b16  call    cs:__imp_GetWindowRect
0x100518b1c  jmp     short loc_100518B3D
0x100518b1e  and     [rbp+Rect.top], 0
0x100518b22  xor     ecx, ecx; nIndex
0x100518b24  and     [rbp+Rect.left], 0
0x100518b28  call    cs:__imp_GetSystemMetrics
0x100518b2e  mov     ecx, r12d; nIndex
0x100518b31  mov     [rbp+Rect.right], eax
0x100518b34  call    cs:__imp_GetSystemMetrics
0x100518b3a  mov     [rbp+Rect.bottom], eax
0x100518b3d  lea     rdx, [rbp+var_20]; lpRect
0x100518b41  mov     rcx, rsi; hWnd
0x100518b44  call    cs:__imp_GetWindowRect
0x100518b4a  mov     r15d, [rbp+var_20.right]
0x100518b4e  sub     r15d, [rbp+var_20.left]
0x100518b52  mov     edi, [rbp+Rect.right]
0x100518b55  mov     eax, r15d
0x100518b58  add     edi, [rbp+Rect.left]
0x100518b5b  mov     r14d, [rbp+var_20.bottom]
0x100518b5f  sub     r14d, [rbp+var_20.top]
0x100518b63  mov     ebx, [rbp+Rect.bottom]
0x100518b66  add     ebx, [rbp+Rect.top]
0x100518b69  sar     eax, 1
0x100518b6b  sar     edi, 1
0x100518b6d  sub     edi, eax
0x100518b6f  sar     ebx, 1
0x100518b71  mov     eax, r14d
0x100518b74  sar     eax, 1
0x100518b76  sub     ebx, eax
0x100518b78  test    edi, edi
0x100518b7a  jg      short loc_100518B81
0x100518b7c  mov     edi, r12d
0x100518b7f  jmp     short loc_100518B95
0x100518b81  xor     ecx, ecx; nIndex
0x100518b83  call    cs:__imp_GetSystemMetrics
0x100518b89  lea     ecx, [rdi+r15]
0x100518b8d  sub     ecx, eax
0x100518b8f  test    ecx, ecx
0x100518b91  jle     short loc_100518B95
0x100518b93  sub     edi, ecx
0x100518b95  test    ebx, ebx
0x100518b97  jg      short loc_100518B9E
0x100518b99  mov     ebx, r12d
0x100518b9c  jmp     short loc_100518BB3
0x100518b9e  mov     ecx, r12d; nIndex
0x100518ba1  call    cs:__imp_GetSystemMetrics
0x100518ba7  lea     edx, [rbx+r14]
0x100518bab  sub     edx, eax
0x100518bad  test    edx, edx
0x100518baf  jle     short loc_100518BB3
0x100518bb1  sub     ebx, edx
0x100518bb3  mov     [rsp+60h+bRepaint], r12d; bRepaint
0x100518bb8  mov     r9d, r15d; nWidth
0x100518bbb  mov     r8d, ebx; Y
0x100518bbe  mov     [rsp+60h+nHeight], r14d; nHeight
0x100518bc3  mov     edx, edi; X
0x100518bc5  mov     rcx, rsi; hWnd
0x100518bc8  call    cs:__imp_MoveWindow
0x100518bce  mov     rcx, [rbp+var_10]
0x100518bd2  xor     rcx, rsp; StackCookie
0x100518bd5  call    __security_check_cookie
0x100518bda  lea     r11, [rsp+60h+var_s0]
0x100518bdf  mov     rbx, [r11+38h]
0x100518be3  mov     rsi, [r11+40h]
0x100518be7  mov     rsp, r11
0x100518bea  pop     r15
0x100518bec  pop     r14
0x100518bee  pop     r12
0x100518bf0  pop     rdi
0x100518bf1  pop     rbp
0x100518bf2  retn
```
