# NewFont

- ea: `0x180021dc4`
- end: `0x180021f09`
- name: `NewFont`
- size: `325`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180021c80`
- `0x180022bb0`

## callees

- `0x1800115f0`
- `0x180017b38`
- `0x180018ab8`
- `0x180021dc4`

## import_xrefs

- `GDI32!SelectObject` at `0x180021e7f`
- `GDI32!SelectObject` at `0x180021ea1`
- `GDI32!SelectObject` at `0x180021e7f`
- `GDI32!SelectObject` at `0x180021ea1`
- `GDI32!DeleteObject` at `0x180021e21`
- `GDI32!DeleteObject` at `0x180021e21`
- `GDI32!GetTextMetricsW` at `0x180021e90`
- `GDI32!GetTextMetricsW` at `0x180021e90`
- `USER32!GetDC` at `0x180021df6`
- `USER32!GetDC` at `0x180021df6`
- `USER32!ReleaseDC` at `0x180021eca`
- `USER32!ReleaseDC` at `0x180021eca`
- `USER32!SendMessageW` at `0x180021ee2`
- `USER32!SendMessageW` at `0x180021ee2`

## pseudocode

```c
int __fastcall NewFont(__int64 a1, HFONT a2, int a3)
{
  void *v3; // r14
  int v5; // esi
  HDC DC; // rbp
  HGDIOBJ v9; // rsi
  LONG tmInternalLeading; // ecx
  int v11; // edx
  int result; // eax
  struct tagTEXTMETRICW tm; // [rsp+20h] [rbp-78h] BYREF

  v3 = *(void **)(a1 + 64);
  v5 = *(_DWORD *)(a1 + 72);
  DC = GetDC(*(HWND *)a1);
  if ( a2 )
  {
    *(_QWORD *)(a1 + 64) = a2;
    *(_DWORD *)(a1 + 72) = 0;
    *(_DWORD *)(a1 + 104) = GetCodePageForFont(a2);
    if ( v5 )
      DeleteObject(v3);
  }
  else if ( v5 )
  {
    a2 = *(HFONT *)(a1 + 64);
  }
  else
  {
    a2 = CCCreateStatusFont();
    if ( !a2 )
      a2 = (HFONT)g_hfontSystem;
    *(_QWORD *)(a1 + 64) = a2;
    *(_DWORD *)(a1 + 72) = a2 != 0;
  }
  if ( a2 != (HFONT)-1LL )
  {
    v9 = 0;
    memset(&tm, 0, sizeof(tm));
    if ( a2 )
      v9 = SelectObject(DC, a2);
    GetTextMetricsW(DC, &tm);
    if ( v9 )
      SelectObject(DC, v9);
    tmInternalLeading = tm.tmInternalLeading;
    v11 = tm.tmInternalLeading + tm.tmHeight;
    *(_DWORD *)(a1 + 76) = tm.tmInternalLeading + tm.tmHeight;
    if ( !tmInternalLeading )
      *(_DWORD *)(a1 + 76) = v11 + 2 * g_cyBorder;
  }
  result = ReleaseDC(*(HWND *)a1, DC);
  if ( a3 )
    return SendMessageW(*(HWND *)a1, 5u, 0, 0);
  return result;
}

```

## disassembly

```asm
0x180021dc4  mov     [rsp+arg_10], rbx
0x180021dc9  push    rbp
0x180021dca  push    rsi
0x180021dcb  push    rdi
0x180021dcc  push    r14
0x180021dce  push    r15
0x180021dd0  sub     rsp, 70h
0x180021dd4  mov     rax, cs:__security_cookie
0x180021ddb  xor     rax, rsp
0x180021dde  mov     [rsp+98h+var_38], rax
0x180021de3  mov     r14, [rcx+40h]
0x180021de7  mov     rdi, rcx
0x180021dea  mov     esi, [rcx+48h]
0x180021ded  mov     r15d, r8d
0x180021df0  mov     rcx, [rcx]; hWnd
0x180021df3  mov     rbx, rdx
0x180021df6  call    cs:__imp_GetDC
0x180021dfc  mov     rbp, rax
0x180021dff  test    rbx, rbx
0x180021e02  jz      short loc_180021E29
0x180021e04  mov     rcx, rbx; h
0x180021e07  mov     [rdi+40h], rbx
0x180021e0b  mov     dword ptr [rdi+48h], 0
0x180021e12  call    GetCodePageForFont
0x180021e17  mov     [rdi+68h], eax
0x180021e1a  test    esi, esi
0x180021e1c  jz      short loc_180021E55
0x180021e1e  mov     rcx, r14; ho
0x180021e21  call    cs:__imp_DeleteObject
0x180021e27  jmp     short loc_180021E55
0x180021e29  test    esi, esi
0x180021e2b  jz      short loc_180021E33
0x180021e2d  mov     rbx, [rdi+40h]
0x180021e31  jmp     short loc_180021E55
0x180021e33  call    CCCreateStatusFont
0x180021e38  test    rax, rax
0x180021e3b  mov     rbx, rax
0x180021e3e  cmovz   rbx, cs:g_hfontSystem
0x180021e46  xor     eax, eax
0x180021e48  test    rbx, rbx
0x180021e4b  mov     [rdi+40h], rbx
0x180021e4f  setnz   al
0x180021e52  mov     [rdi+48h], eax
0x180021e55  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180021e59  jz      short loc_180021EC4
0x180021e5b  xorps   xmm0, xmm0
0x180021e5e  xor     esi, esi
0x180021e60  movups  xmmword ptr [rsp+98h+tm.tmOverhang], xmm0
0x180021e65  movups  xmmword ptr [rsp+98h+tm.tmFirstChar], xmm0
0x180021e6a  movups  xmmword ptr [rsp+98h+tm.tmHeight], xmm0
0x180021e6f  movups  xmmword ptr [rsp+98h+tm.tmExternalLeading], xmm0
0x180021e74  test    rbx, rbx
0x180021e77  jz      short loc_180021E88
0x180021e79  mov     rdx, rbx; h
0x180021e7c  mov     rcx, rbp; hdc
0x180021e7f  call    cs:__imp_SelectObject
0x180021e85  mov     rsi, rax
0x180021e88  lea     rdx, [rsp+98h+tm]; lptm
0x180021e8d  mov     rcx, rbp; hdc
0x180021e90  call    cs:__imp_GetTextMetricsW
0x180021e96  test    rsi, rsi
0x180021e99  jz      short loc_180021EA7
0x180021e9b  mov     rdx, rsi; h
0x180021e9e  mov     rcx, rbp; hdc
0x180021ea1  call    cs:__imp_SelectObject
0x180021ea7  mov     ecx, [rsp+98h+tm.tmInternalLeading]
0x180021eab  mov     edx, [rsp+98h+tm.tmHeight]
0x180021eaf  add     edx, ecx
0x180021eb1  mov     [rdi+4Ch], edx
0x180021eb4  test    ecx, ecx
0x180021eb6  jnz     short loc_180021EC4
0x180021eb8  mov     eax, cs:g_cyBorder
0x180021ebe  lea     ecx, [rdx+rax*2]
0x180021ec1  mov     [rdi+4Ch], ecx
0x180021ec4  mov     rcx, [rdi]; hWnd
0x180021ec7  mov     rdx, rbp; hDC
0x180021eca  call    cs:__imp_ReleaseDC
0x180021ed0  test    r15d, r15d
0x180021ed3  jz      short loc_180021EE8
0x180021ed5  mov     rcx, [rdi]; hWnd
0x180021ed8  xor     r9d, r9d; lParam
0x180021edb  xor     r8d, r8d; wParam
0x180021ede  lea     edx, [r9+5]; Msg
0x180021ee2  call    cs:__imp_SendMessageW
0x180021ee8  mov     rcx, [rsp+98h+var_38]
0x180021eed  xor     rcx, rsp; StackCookie
0x180021ef0  call    __security_check_cookie
0x180021ef5  mov     rbx, [rsp+98h+arg_10]
0x180021efd  add     rsp, 70h
0x180021f01  pop     r15
0x180021f03  pop     r14
0x180021f05  pop     rdi
0x180021f06  pop     rsi
0x180021f07  pop     rbp
0x180021f08  retn
```
