# GetHeaderPadding

- ea: `0x180019128`
- end: `0x1800191f0`
- name: `GetHeaderPadding`
- size: `200`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001af68`

## callees

- `0x180019128`
- `0x180030ea0`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x1800191c8`
- `USER32!GetSystemMetrics` at `0x1800191c8`
- `USER32!GetClientRect` at `0x18001917a`
- `USER32!GetClientRect` at `0x18001917a`
- `UxTheme!GetThemeBackgroundContentRect` at `0x1800191a0`
- `UxTheme!GetThemeBackgroundContentRect` at `0x1800191a0`
- `UxTheme!OpenThemeData` at `0x180019164`
- `UxTheme!OpenThemeData` at `0x180019164`
- `UxTheme!CloseThemeData` at `0x1800191bd`
- `UxTheme!CloseThemeData` at `0x1800191bd`

## pseudocode

```c
int __fastcall GetHeaderPadding(HWND hWnd, int *a2, _DWORD *a3)
{
  int v6; // ebx
  HTHEME v7; // rdi
  int result; // eax
  struct tagRECT Rect; // [rsp+30h] [rbp-58h] BYREF
  struct tagRECT pContentRect; // [rsp+40h] [rbp-48h] BYREF

  Rect = 0;
  pContentRect = 0;
  v6 = 0;
  v7 = OpenThemeData(hWnd, L"Header");
  if ( v7 )
  {
    GetClientRect(hWnd, &Rect);
    if ( GetThemeBackgroundContentRect(v7, 0, 1, 1, &Rect, &pContentRect) >= 0 )
      v6 = Rect.right + pContentRect.left - pContentRect.right - Rect.left;
    CloseThemeData(v7);
  }
  result = GetSystemMetrics(45);
  *a2 = v6;
  *a3 = 6 * result;
  return result;
}

```

## disassembly

```asm
0x180019128  push    rbx
0x18001912a  push    rbp
0x18001912b  push    rsi
0x18001912c  push    rdi
0x18001912d  push    r14
0x18001912f  sub     rsp, 60h
0x180019133  mov     rax, cs:__security_cookie
0x18001913a  xor     rax, rsp
0x18001913d  mov     [rsp+88h+var_38], rax
0x180019142  mov     rsi, rdx
0x180019145  xorps   xmm0, xmm0
0x180019148  xorps   xmm1, xmm1
0x18001914b  lea     rdx, aHeader; "Header"
0x180019152  movups  xmmword ptr [rsp+88h+Rect.left], xmm0
0x180019157  mov     r14, r8
0x18001915a  mov     rbp, rcx
0x18001915d  movups  xmmword ptr [rsp+88h+var_48.left], xmm1
0x180019162  xor     ebx, ebx
0x180019164  call    cs:__imp_OpenThemeData
0x18001916a  mov     rdi, rax
0x18001916d  test    rax, rax
0x180019170  jz      short loc_1800191C3
0x180019172  lea     rdx, [rsp+88h+Rect]; lpRect
0x180019177  mov     rcx, rbp; hWnd
0x18001917a  call    cs:__imp_GetClientRect
0x180019180  lea     rax, [rsp+88h+var_48]
0x180019185  xor     edx, edx; hdc
0x180019187  mov     [rsp+88h+pContentRect], rax; pContentRect
0x18001918c  lea     r8d, [rbx+1]; iPartId
0x180019190  lea     rax, [rsp+88h+Rect]
0x180019195  mov     r9d, r8d; iStateId
0x180019198  mov     rcx, rdi; hTheme
0x18001919b  mov     [rsp+88h+pBoundingRect], rax; pBoundingRect
0x1800191a0  call    cs:__imp_GetThemeBackgroundContentRect
0x1800191a6  test    eax, eax
0x1800191a8  js      short loc_1800191BA
0x1800191aa  mov     ebx, [rsp+88h+var_48.left]
0x1800191ae  sub     ebx, [rsp+88h+var_48.right]
0x1800191b2  sub     ebx, [rsp+88h+Rect.left]
0x1800191b6  add     ebx, [rsp+88h+Rect.right]
0x1800191ba  mov     rcx, rdi; hTheme
0x1800191bd  call    cs:__imp_CloseThemeData
0x1800191c3  mov     ecx, 2Dh ; '-'; nIndex
0x1800191c8  call    cs:__imp_GetSystemMetrics
0x1800191ce  mov     [rsi], ebx
0x1800191d0  lea     ecx, [rax+rax*2]
0x1800191d3  add     ecx, ecx
0x1800191d5  mov     [r14], ecx
0x1800191d8  mov     rcx, [rsp+88h+var_38]
0x1800191dd  xor     rcx, rsp; StackCookie
0x1800191e0  call    __security_check_cookie
0x1800191e5  add     rsp, 60h
0x1800191e9  pop     r14
0x1800191eb  pop     rdi
0x1800191ec  pop     rsi
0x1800191ed  pop     rbp
0x1800191ee  pop     rbx
0x1800191ef  retn
```
