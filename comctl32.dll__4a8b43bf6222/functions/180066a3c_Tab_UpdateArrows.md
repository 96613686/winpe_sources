# Tab_UpdateArrows

- ea: `0x180066a3c`
- end: `0x180066c7f`
- name: `Tab_UpdateArrows`
- size: `579`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180064000`
- `0x180064e70`
- `0x1800654bc`
- `0x180066950`
- `0x180066d40`

## callees

- `0x1800115f0`
- `0x18002d220`
- `0x180062d80`
- `0x180064820`
- `0x180065328`
- `0x180066a3c`
- `0x180066c88`

## import_xrefs

- `USER32!SetWindowPos` at `0x180066c5e`
- `USER32!SetWindowPos` at `0x180066c5e`
- `USER32!SendMessageW` at `0x180066c74`
- `USER32!SendMessageW` at `0x180066c74`
- `USER32!ShowWindow` at `0x180066b26`
- `USER32!ShowWindow` at `0x180066b26`
- `USER32!IsWindowVisible` at `0x180066c2a`
- `USER32!IsWindowVisible` at `0x180066c2a`
- `USER32!InvalidateRect` at `0x180066b35`
- `USER32!InvalidateRect` at `0x180066b5b`
- `USER32!InvalidateRect` at `0x180066b8d`
- `USER32!InvalidateRect` at `0x180066b35`
- `USER32!InvalidateRect` at `0x180066b5b`
- `USER32!InvalidateRect` at `0x180066b8d`
- `USER32!IsRectEmpty` at `0x180066a79`
- `USER32!IsRectEmpty` at `0x180066a79`

## pseudocode

```c
int __fastcall Tab_UpdateArrows(__int64 a1, int a2)
{
  HWND UpDownControl; // rax
  bool v5; // zf
  LONG right; // edx
  int v7; // r14d
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // r10
  int v11; // edi
  _DWORD *v12; // r11
  int nUpper; // edi
  HWND v14; // rcx
  LONG v15; // ecx
  RECT rc; // [rsp+60h] [rbp+7h] BYREF

  rc = 0;
  Tab_GetClientRect(a1, &rc);
  LODWORD(UpDownControl) = IsRectEmpty(&rc);
  if ( (_DWORD)UpDownControl )
    return (int)UpDownControl;
  v5 = (*(_DWORD *)(a1 + 16) & 0x200) == 0;
  LODWORD(UpDownControl) = rc.right;
  *(_DWORD *)(a1 + 116) = rc.right;
  if ( !v5 )
    goto LABEL_14;
  LODWORD(UpDownControl) = CalcPaintMetrics(a1, 0);
  right = rc.right;
  if ( *(_DWORD *)(a1 + 104) < rc.right )
    goto LABEL_14;
  v7 = *(_DWORD *)(a1 + 120);
  v8 = 0;
  v9 = rc.right - 2 * v7;
  *(_DWORD *)(a1 + 116) = v9;
  if ( right - 2 * v7 < *(_DWORD *)(a1 + 104) )
  {
    v10 = *(_QWORD *)(a1 + 64);
    v11 = 0;
    if ( v10 )
    {
      do
      {
        if ( v8 < 0 )
          break;
        if ( v8 >= *(_DWORD *)v10 )
          break;
        v12 = *(_DWORD **)(*(_QWORD *)(v10 + 8) + 8LL * v8);
        if ( !v12 )
          break;
        ++v8;
        v11 += v12[2] - *v12;
      }
      while ( v9 + v11 < *(_DWORD *)(a1 + 104) );
    }
  }
  UpDownControl = *(HWND *)(a1 + 64);
  nUpper = *(_DWORD *)UpDownControl - 1;
  if ( v8 < *(_DWORD *)UpDownControl )
    nUpper = v8;
  if ( nUpper <= 0 )
  {
    *(_DWORD *)(a1 + 116) = right;
LABEL_14:
    v14 = *(HWND *)(a1 + 56);
    if ( v14 )
    {
      ShowWindow(v14, 0);
      LODWORD(UpDownControl) = InvalidateRect(*(HWND *)a1, 0, 1);
    }
    if ( *(int *)(a1 + 124) > 0 )
    {
      Tab_OnHScroll(a1, 0, 4);
      LODWORD(UpDownControl) = InvalidateRect(*(HWND *)a1, 0, 1);
    }
    return (int)UpDownControl;
  }
  if ( !*(_QWORD *)(a1 + 56) )
  {
    InvalidateRect(*(HWND *)a1, 0, 1);
    UpDownControl = CreateUpDownControl(
                      (*(_DWORD *)(a1 + 16) & 0x80u) != 0 ? 1073741825 : 1073741888,
                      0,
                      0,
                      0,
                      0,
                      *(HWND *)a1,
                      1,
                      g_hinst,
                      0,
                      nUpper,
                      0,
                      *(_DWORD *)(a1 + 124));
    *(_QWORD *)(a1 + 56) = UpDownControl;
    if ( !UpDownControl )
      return (int)UpDownControl;
    right = rc.right;
  }
  v15 = *(_DWORD *)(a1 + 112);
  rc.left = right - 2 * v7;
  rc.bottom = v15;
  rc.top = v15 - v7;
  Tab_VDFlipRect(a1, &rc);
  if ( a2 || !IsWindowVisible(*(HWND *)(a1 + 56)) )
    SetWindowPos(*(HWND *)(a1 + 56), 0, rc.left, rc.top, rc.right - rc.left, rc.bottom - rc.top, 0x54u);
  LODWORD(UpDownControl) = SendMessageW(*(HWND *)(a1 + 56), 0x465u, 0, (unsigned __int16)nUpper);
  return (int)UpDownControl;
}

```

## disassembly

```asm
0x180066a3c  push    rbp
0x180066a3e  push    rbx
0x180066a3f  push    rsi
0x180066a40  push    rdi
0x180066a41  push    r14
0x180066a43  push    r15
0x180066a45  lea     rbp, [rsp-2Fh]
0x180066a4a  sub     rsp, 88h
0x180066a51  mov     rax, cs:__security_cookie
0x180066a58  xor     rax, rsp
0x180066a5b  mov     [rbp+57h+var_40], rax
0x180066a5f  mov     r15d, edx
0x180066a62  xorps   xmm0, xmm0
0x180066a65  lea     rdx, [rbp+57h+rc]
0x180066a69  mov     rbx, rcx
0x180066a6c  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x180066a70  call    Tab_GetClientRect
0x180066a75  lea     rcx, [rbp+57h+rc]; lprc
0x180066a79  call    cs:__imp_IsRectEmpty
0x180066a7f  test    eax, eax
0x180066a81  jnz     loc_180066B61
0x180066a87  test    dword ptr [rbx+10h], 200h
0x180066a8e  mov     eax, [rbp+57h+rc.right]
0x180066a91  mov     [rbx+74h], eax
0x180066a94  jnz     loc_180066B1B
0x180066a9a  xor     edx, edx
0x180066a9c  mov     rcx, rbx
0x180066a9f  call    CalcPaintMetrics
0x180066aa4  mov     edx, [rbp+57h+rc.right]
0x180066aa7  cmp     [rbx+68h], edx
0x180066aaa  jl      short loc_180066B1B
0x180066aac  mov     r14d, [rbx+78h]
0x180066ab0  mov     r9d, edx
0x180066ab3  mov     eax, edx
0x180066ab5  xor     r8d, r8d
0x180066ab8  lea     esi, [r14+r14]
0x180066abc  sub     r9d, esi
0x180066abf  sub     eax, esi
0x180066ac1  mov     [rbx+74h], r9d
0x180066ac5  cmp     eax, [rbx+68h]
0x180066ac8  jge     short loc_180066B04
0x180066aca  mov     r10, [rbx+40h]
0x180066ace  xor     edi, edi
0x180066ad0  test    r10, r10
0x180066ad3  jz      short loc_180066B04
0x180066ad5  test    r8d, r8d
0x180066ad8  js      short loc_180066B04
0x180066ada  cmp     r8d, [r10]
0x180066add  jge     short loc_180066B04
0x180066adf  mov     rax, [r10+8]
0x180066ae3  movsxd  rcx, r8d
0x180066ae6  mov     r11, [rax+rcx*8]
0x180066aea  test    r11, r11
0x180066aed  jz      short loc_180066B04
0x180066aef  mov     eax, [r11+8]
0x180066af3  inc     r8d
0x180066af6  sub     eax, [r11]
0x180066af9  add     edi, eax
0x180066afb  lea     eax, [r9+rdi]
0x180066aff  cmp     eax, [rbx+68h]
0x180066b02  jl      short loc_180066AD5
0x180066b04  mov     rax, [rbx+40h]
0x180066b08  mov     ecx, [rax]
0x180066b0a  cmp     r8d, ecx
0x180066b0d  lea     edi, [rcx-1]
0x180066b10  cmovl   edi, r8d
0x180066b14  test    edi, edi
0x180066b16  jg      short loc_180066B7D
0x180066b18  mov     [rbx+74h], edx
0x180066b1b  mov     rcx, [rbx+38h]; hWnd
0x180066b1f  test    rcx, rcx
0x180066b22  jz      short loc_180066B3B
0x180066b24  xor     edx, edx; nCmdShow
0x180066b26  call    cs:__imp_ShowWindow
0x180066b2c  mov     rcx, [rbx]; hWnd
0x180066b2f  xor     edx, edx; lpRect
0x180066b31  lea     r8d, [rdx+1]; bErase
0x180066b35  call    cs:__imp_InvalidateRect
0x180066b3b  cmp     dword ptr [rbx+7Ch], 0
0x180066b3f  jle     short loc_180066B61
0x180066b41  xor     r9d, r9d
0x180066b44  xor     edx, edx
0x180066b46  mov     rcx, rbx
0x180066b49  lea     r8d, [r9+4]
0x180066b4d  call    Tab_OnHScroll
0x180066b52  mov     rcx, [rbx]; hWnd
0x180066b55  xor     edx, edx; lpRect
0x180066b57  lea     r8d, [rdx+1]; bErase
0x180066b5b  call    cs:__imp_InvalidateRect
0x180066b61  mov     rcx, [rbp+57h+var_40]
0x180066b65  xor     rcx, rsp; StackCookie
0x180066b68  call    __security_check_cookie
0x180066b6d  add     rsp, 88h
0x180066b74  pop     r15
0x180066b76  pop     r14
0x180066b78  pop     rdi
0x180066b79  pop     rsi
0x180066b7a  pop     rbx
0x180066b7b  pop     rbp
0x180066b7c  retn
0x180066b7d  cmp     qword ptr [rbx+38h], 0
0x180066b82  jnz     short loc_180066C02
0x180066b84  mov     rcx, [rbx]; hWnd
0x180066b87  xor     edx, edx; lpRect
0x180066b89  lea     r8d, [rdx+1]; bErase
0x180066b8d  call    cs:__imp_InvalidateRect
0x180066b93  mov     eax, [rbx+10h]
0x180066b96  and     al, 80h
0x180066b98  neg     al
0x180066b9a  mov     eax, [rbx+7Ch]
0x180066b9d  mov     [rsp+0B0h+nPos], eax; nPos
0x180066ba1  sbb     ecx, ecx
0x180066ba3  mov     rax, cs:g_hinst
0x180066baa  and     ecx, 0FFFFFFC1h
0x180066bad  mov     [rsp+0B0h+nLower], 0; nLower
0x180066bb5  add     ecx, 40000040h; dwStyle
0x180066bbb  mov     [rsp+0B0h+nUpper], edi; nUpper
0x180066bbf  xor     r9d, r9d; cx
0x180066bc2  mov     [rsp+0B0h+hBuddy], 0; hBuddy
0x180066bcb  xor     r8d, r8d; y
0x180066bce  mov     [rsp+0B0h+hInst], rax; hInst
0x180066bd3  xor     edx, edx; x
0x180066bd5  mov     rax, [rbx]
0x180066bd8  mov     [rsp+0B0h+nID], 1; nID
0x180066be0  mov     [rsp+0B0h+hParent], rax; hParent
0x180066be5  mov     [rsp+0B0h+cy], 0; cy
0x180066bed  call    CreateUpDownControl
0x180066bf2  mov     [rbx+38h], rax
0x180066bf6  test    rax, rax
0x180066bf9  jz      loc_180066B61
0x180066bff  mov     edx, [rbp+57h+rc.right]
0x180066c02  mov     ecx, [rbx+70h]
0x180066c05  sub     edx, esi
0x180066c07  mov     eax, ecx
0x180066c09  mov     [rbp+57h+rc.left], edx
0x180066c0c  sub     eax, r14d
0x180066c0f  mov     [rbp+57h+rc.bottom], ecx
0x180066c12  lea     rdx, [rbp+57h+rc]
0x180066c16  mov     [rbp+57h+rc.top], eax
0x180066c19  mov     rcx, rbx
0x180066c1c  call    Tab_VDFlipRect
0x180066c21  test    r15d, r15d
0x180066c24  jnz     short loc_180066C34
0x180066c26  mov     rcx, [rbx+38h]; hWnd
0x180066c2a  call    cs:__imp_IsWindowVisible
0x180066c30  test    eax, eax
0x180066c32  jnz     short loc_180066C64
0x180066c34  mov     ecx, [rbp+57h+rc.bottom]
0x180066c37  xor     edx, edx; hWndInsertAfter
0x180066c39  mov     r9d, [rbp+57h+rc.top]; Y
0x180066c3d  sub     ecx, r9d
0x180066c40  mov     eax, [rbp+57h+rc.right]
0x180066c43  mov     r8d, [rbp+57h+rc.left]; X
0x180066c47  sub     eax, r8d
0x180066c4a  mov     [rsp+0B0h+nID], 54h ; 'T'; uFlags
0x180066c52  mov     dword ptr [rsp+0B0h+hParent], ecx; cy
0x180066c56  mov     rcx, [rbx+38h]; hWnd
0x180066c5a  mov     [rsp+0B0h+cy], eax; cx
0x180066c5e  call    cs:__imp_SetWindowPos
0x180066c64  mov     rcx, [rbx+38h]; hWnd
0x180066c68  xor     r8d, r8d; wParam
0x180066c6b  movzx   r9d, di; lParam
0x180066c6f  mov     edx, 465h; Msg
0x180066c74  call    cs:__imp_SendMessageW
0x180066c7a  jmp     loc_180066B61
```
