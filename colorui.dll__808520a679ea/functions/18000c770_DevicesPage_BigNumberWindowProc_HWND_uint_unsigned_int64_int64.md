# DevicesPage::BigNumberWindowProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18000c770`
- end: `0x18000ca34`
- name: `?BigNumberWindowProc@DevicesPage@@CA_JPEAUHWND__@@I_K_J@Z`
- size: `708`
- prototype: `LRESULT __fastcall(HWND hWnd, UINT Msg, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000c770`
- `0x18000cc44`
- `0x1800184ce`
- `0x180018500`

## import_xrefs

- `USER32!ReleaseDC` at `0x18000c9ef`
- `USER32!ReleaseDC` at `0x18000c9ef`
- `USER32!GetClientRect` at `0x18000c807`
- `USER32!GetClientRect` at `0x18000c958`
- `USER32!GetClientRect` at `0x18000c807`
- `USER32!GetClientRect` at `0x18000c958`
- `USER32!SetWindowRgn` at `0x18000c9e3`
- `USER32!SetWindowRgn` at `0x18000c9e3`
- `USER32!GetDC` at `0x18000c96e`
- `USER32!GetDC` at `0x18000c96e`
- `USER32!DestroyWindow` at `0x18000c7df`
- `USER32!DestroyWindow` at `0x18000c7df`
- `USER32!BeginPaint` at `0x18000c82e`
- `USER32!BeginPaint` at `0x18000c82e`
- `USER32!EndPaint` at `0x18000c92f`
- `USER32!EndPaint` at `0x18000c92f`
- `USER32!GetWindowTextW` at `0x18000c7f9`
- `USER32!GetWindowTextW` at `0x18000c94a`
- `USER32!GetWindowTextW` at `0x18000c7f9`
- `USER32!GetWindowTextW` at `0x18000c94a`
- `USER32!DefWindowProcW` at `0x18000ca0e`
- `USER32!DefWindowProcW` at `0x18000ca0e`
- `GDI32!DeleteObject` at `0x18000c921`
- `GDI32!DeleteObject` at `0x18000c9f8`
- `GDI32!DeleteObject` at `0x18000c921`
- `GDI32!DeleteObject` at `0x18000c9f8`
- `GDI32!CreatePen` at `0x18000c8ec`
- `GDI32!CreatePen` at `0x18000c8ec`
- `GDI32!SetBkMode` at `0x18000c884`
- `GDI32!SetBkMode` at `0x18000c994`
- `GDI32!SetBkMode` at `0x18000c884`
- `GDI32!SetBkMode` at `0x18000c994`
- `GDI32!EndPath` at `0x18000c8b8`
- `GDI32!EndPath` at `0x18000c9c8`
- `GDI32!EndPath` at `0x18000c8b8`
- `GDI32!EndPath` at `0x18000c9c8`
- `GDI32!SetTextColor` at `0x18000c86e`
- `GDI32!SetTextColor` at `0x18000c86e`
- `GDI32!TextOutW` at `0x18000c8af`
- `GDI32!TextOutW` at `0x18000c8dc`
- `GDI32!TextOutW` at `0x18000c9bf`
- `GDI32!TextOutW` at `0x18000c8af`
- `GDI32!TextOutW` at `0x18000c8dc`
- `GDI32!TextOutW` at `0x18000c9bf`
- `GDI32!StrokePath` at `0x18000c90c`
- `GDI32!StrokePath` at `0x18000c90c`
- `GDI32!PathToRegion` at `0x18000c9d1`
- `GDI32!PathToRegion` at `0x18000c9d1`
- `GDI32!BeginPath` at `0x18000c877`
- `GDI32!BeginPath` at `0x18000c986`
- `GDI32!BeginPath` at `0x18000c877`
- `GDI32!BeginPath` at `0x18000c986`
- `GDI32!SelectObject` at `0x18000c860`
- `GDI32!SelectObject` at `0x18000c900`
- `GDI32!SelectObject` at `0x18000c918`
- `GDI32!SelectObject` at `0x18000c97d`
- `GDI32!SelectObject` at `0x18000c860`
- `GDI32!SelectObject` at `0x18000c900`
- `GDI32!SelectObject` at `0x18000c918`
- `GDI32!SelectObject` at `0x18000c97d`
- `GDI32!PatBlt` at `0x18000c854`
- `GDI32!PatBlt` at `0x18000c854`

## pseudocode

```c
LRESULT __fastcall DevicesPage::BigNumberWindowProc(HWND hWnd, UINT Msg, WPARAM a3, LPARAM a4)
{
  HFONT v7; // r13
  HDC v8; // rsi
  __int64 v9; // rbx
  __int64 v10; // rax
  HPEN Pen; // rax
  HPEN v12; // r12
  HGDIOBJ v13; // rbx
  HFONT v14; // rcx
  HFONT BigFont; // r12
  HDC DC; // rsi
  __int64 v17; // rbx
  HRGN v18; // rax
  struct tagRECT Rect; // [rsp+40h] [rbp-C0h] BYREF
  tagPAINTSTRUCT Paint; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR String[80]; // [rsp+A0h] [rbp-60h] BYREF

  Rect = 0;
  memset_0(&Paint, 0, sizeof(Paint));
  switch ( Msg )
  {
    case 5u:
      GetWindowTextW(hWnd, String, 80);
      GetClientRect(hWnd, &Rect);
      BigFont = DevicesPage::GetBigFont(&Rect);
      DC = GetDC(hWnd);
      SelectObject(DC, BigFont);
      BeginPath(DC);
      SetBkMode(DC, 1);
      v17 = -1;
      do
        ++v17;
      while ( String[v17] );
      TextOutW(DC, 0, 0, String, v17);
      EndPath(DC);
      v18 = PathToRegion(DC);
      SetWindowRgn(hWnd, v18, 1);
      ReleaseDC(hWnd, DC);
      v14 = BigFont;
      goto LABEL_16;
    case 0xFu:
      GetWindowTextW(hWnd, String, 80);
      GetClientRect(hWnd, &Rect);
      v7 = DevicesPage::GetBigFont(&Rect);
      if ( !v7 )
        return DefWindowProcW(hWnd, Msg, a3, a4);
      v8 = BeginPaint(hWnd, &Paint);
      PatBlt(v8, 0, 0, Rect.right, Rect.bottom, 0x80000042);
      SelectObject(v8, v7);
      SetTextColor(v8, 0xFFFFFFu);
      BeginPath(v8);
      SetBkMode(v8, 1);
      v9 = -1;
      v10 = -1;
      do
        ++v10;
      while ( String[v10] );
      TextOutW(v8, 0, 0, String, v10);
      EndPath(v8);
      do
        ++v9;
      while ( String[v9] );
      TextOutW(v8, 0, 0, String, v9);
      Pen = CreatePen(6, 4, 0);
      v12 = Pen;
      if ( Pen )
      {
        v13 = SelectObject(v8, Pen);
        StrokePath(v8);
        SelectObject(v8, v13);
        DeleteObject(v12);
      }
      EndPaint(hWnd, &Paint);
      v14 = v7;
LABEL_16:
      DeleteObject(v14);
      return DefWindowProcW(hWnd, Msg, a3, a4);
    case 0x113u:
      DestroyWindow(hWnd);
      return 0;
  }
  return DefWindowProcW(hWnd, Msg, a3, a4);
}

```

## disassembly

```asm
0x18000c770  push    rbp
0x18000c772  push    rbx
0x18000c773  push    rsi
0x18000c774  push    rdi
0x18000c775  push    r12
0x18000c777  push    r13
0x18000c779  push    r14
0x18000c77b  push    r15
0x18000c77d  lea     rbp, [rsp-58h]
0x18000c782  sub     rsp, 158h
0x18000c789  mov     rax, cs:__security_cookie
0x18000c790  xor     rax, rsp
0x18000c793  mov     [rbp+90h+var_50], rax
0x18000c797  mov     r15d, edx
0x18000c79a  mov     [rsp+190h+wParam], r8
0x18000c79f  xor     edx, edx; Val
0x18000c7a1  mov     [rsp+190h+lParam], r9
0x18000c7a6  mov     rdi, rcx
0x18000c7a9  xorps   xmm0, xmm0
0x18000c7ac  lea     rcx, [rsp+190h+Paint]; void *
0x18000c7b1  movups  xmmword ptr [rsp+190h+Rect.left], xmm0
0x18000c7b6  lea     r8d, [rdx+48h]; Size
0x18000c7ba  call    memset_0
0x18000c7bf  cmp     r15d, 5
0x18000c7c3  jz      loc_18000C93D
0x18000c7c9  cmp     r15d, 0Fh
0x18000c7cd  jz      short loc_18000C7EC
0x18000c7cf  cmp     r15d, 113h
0x18000c7d6  jnz     loc_18000C9FE
0x18000c7dc  mov     rcx, rdi; hWnd
0x18000c7df  call    cs:__imp_DestroyWindow
0x18000c7e5  xor     eax, eax
0x18000c7e7  jmp     loc_18000CA14
0x18000c7ec  mov     r8d, 50h ; 'P'; nMaxCount
0x18000c7f2  lea     rdx, [rbp+90h+String]; lpString
0x18000c7f6  mov     rcx, rdi; hWnd
0x18000c7f9  call    cs:__imp_GetWindowTextW
0x18000c7ff  lea     rdx, [rsp+190h+Rect]; lpRect
0x18000c804  mov     rcx, rdi; hWnd
0x18000c807  call    cs:__imp_GetClientRect
0x18000c80d  lea     rcx, [rsp+190h+Rect]; struct tagRECT *
0x18000c812  call    ?GetBigFont@DevicesPage@@CAPEAUHFONT__@@PEBUtagRECT@@@Z; DevicesPage::GetBigFont(tagRECT const *)
0x18000c817  xor     r14d, r14d
0x18000c81a  mov     r13, rax
0x18000c81d  test    rax, rax
0x18000c820  jz      loc_18000C9FE
0x18000c826  lea     rdx, [rsp+190h+Paint]; lpPaint
0x18000c82b  mov     rcx, rdi; hWnd
0x18000c82e  call    cs:__imp_BeginPaint
0x18000c834  mov     ecx, [rsp+190h+Rect.bottom]
0x18000c838  xor     r8d, r8d; y
0x18000c83b  mov     r9d, [rsp+190h+Rect.right]; w
0x18000c840  xor     edx, edx; x
0x18000c842  mov     [rsp+190h+rop], 80000042h; rop
0x18000c84a  mov     rsi, rax
0x18000c84d  mov     [rsp+190h+h], ecx; h
0x18000c851  mov     rcx, rax; hdc
0x18000c854  call    cs:__imp_PatBlt
0x18000c85a  mov     rdx, r13; h
0x18000c85d  mov     rcx, rsi; hdc
0x18000c860  call    cs:__imp_SelectObject
0x18000c866  mov     edx, 0FFFFFFh; color
0x18000c86b  mov     rcx, rsi; hdc
0x18000c86e  call    cs:__imp_SetTextColor
0x18000c874  mov     rcx, rsi; hdc
0x18000c877  call    cs:__imp_BeginPath
0x18000c87d  lea     edx, [r14+1]; mode
0x18000c881  mov     rcx, rsi; hdc
0x18000c884  call    cs:__imp_SetBkMode
0x18000c88a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000c88e  lea     rcx, [rbp+90h+String]
0x18000c892  mov     rax, rbx
0x18000c895  inc     rax
0x18000c898  cmp     [rcx+rax*2], r14w
0x18000c89d  jnz     short loc_18000C895
0x18000c89f  lea     r9, [rbp+90h+String]; lpString
0x18000c8a3  mov     [rsp+190h+h], eax; c
0x18000c8a7  xor     r8d, r8d; y
0x18000c8aa  xor     edx, edx; x
0x18000c8ac  mov     rcx, rsi; hdc
0x18000c8af  call    cs:__imp_TextOutW
0x18000c8b5  mov     rcx, rsi; hdc
0x18000c8b8  call    cs:__imp_EndPath
0x18000c8be  lea     rax, [rbp+90h+String]
0x18000c8c2  inc     rbx
0x18000c8c5  cmp     [rax+rbx*2], r14w
0x18000c8ca  jnz     short loc_18000C8C2
0x18000c8cc  lea     r9, [rbp+90h+String]; lpString
0x18000c8d0  mov     [rsp+190h+h], ebx; c
0x18000c8d4  xor     r8d, r8d; y
0x18000c8d7  xor     edx, edx; x
0x18000c8d9  mov     rcx, rsi; hdc
0x18000c8dc  call    cs:__imp_TextOutW
0x18000c8e2  xor     r8d, r8d; color
0x18000c8e5  lea     edx, [r8+4]; cWidth
0x18000c8e9  lea     ecx, [rdx+2]; iStyle
0x18000c8ec  call    cs:__imp_CreatePen
0x18000c8f2  mov     r12, rax
0x18000c8f5  test    rax, rax
0x18000c8f8  jz      short loc_18000C927
0x18000c8fa  mov     rdx, rax; h
0x18000c8fd  mov     rcx, rsi; hdc
0x18000c900  call    cs:__imp_SelectObject
0x18000c906  mov     rcx, rsi; hdc
0x18000c909  mov     rbx, rax
0x18000c90c  call    cs:__imp_StrokePath
0x18000c912  mov     rdx, rbx; h
0x18000c915  mov     rcx, rsi; hdc
0x18000c918  call    cs:__imp_SelectObject
0x18000c91e  mov     rcx, r12; ho
0x18000c921  call    cs:__imp_DeleteObject
0x18000c927  lea     rdx, [rsp+190h+Paint]; lpPaint
0x18000c92c  mov     rcx, rdi; hWnd
0x18000c92f  call    cs:__imp_EndPaint
0x18000c935  mov     rcx, r13
0x18000c938  jmp     loc_18000C9F8
0x18000c93d  mov     r8d, 50h ; 'P'; nMaxCount
0x18000c943  lea     rdx, [rbp+90h+String]; lpString
0x18000c947  mov     rcx, rdi; hWnd
0x18000c94a  call    cs:__imp_GetWindowTextW
0x18000c950  lea     rdx, [rsp+190h+Rect]; lpRect
0x18000c955  mov     rcx, rdi; hWnd
0x18000c958  call    cs:__imp_GetClientRect
0x18000c95e  lea     rcx, [rsp+190h+Rect]; struct tagRECT *
0x18000c963  call    ?GetBigFont@DevicesPage@@CAPEAUHFONT__@@PEBUtagRECT@@@Z; DevicesPage::GetBigFont(tagRECT const *)
0x18000c968  mov     rcx, rdi; hWnd
0x18000c96b  mov     r12, rax
0x18000c96e  call    cs:__imp_GetDC
0x18000c974  mov     rcx, rax; hdc
0x18000c977  mov     rdx, r12; h
0x18000c97a  mov     rsi, rax
0x18000c97d  call    cs:__imp_SelectObject
0x18000c983  mov     rcx, rsi; hdc
0x18000c986  call    cs:__imp_BeginPath
0x18000c98c  mov     edx, 1; mode
0x18000c991  mov     rcx, rsi; hdc
0x18000c994  call    cs:__imp_SetBkMode
0x18000c99a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000c99e  lea     rax, [rbp+90h+String]
0x18000c9a2  xor     r14d, r14d
0x18000c9a5  inc     rbx
0x18000c9a8  cmp     [rax+rbx*2], r14w
0x18000c9ad  jnz     short loc_18000C9A5
0x18000c9af  lea     r9, [rbp+90h+String]; lpString
0x18000c9b3  mov     [rsp+190h+h], ebx; c
0x18000c9b7  xor     r8d, r8d; y
0x18000c9ba  xor     edx, edx; x
0x18000c9bc  mov     rcx, rsi; hdc
0x18000c9bf  call    cs:__imp_TextOutW
0x18000c9c5  mov     rcx, rsi; hdc
0x18000c9c8  call    cs:__imp_EndPath
0x18000c9ce  mov     rcx, rsi; hdc
0x18000c9d1  call    cs:__imp_PathToRegion
0x18000c9d7  mov     r8d, 1; bRedraw
0x18000c9dd  mov     rcx, rdi; hWnd
0x18000c9e0  mov     rdx, rax; hRgn
0x18000c9e3  call    cs:__imp_SetWindowRgn
0x18000c9e9  mov     rdx, rsi; hDC
0x18000c9ec  mov     rcx, rdi; hWnd
0x18000c9ef  call    cs:__imp_ReleaseDC
0x18000c9f5  mov     rcx, r12; ho
0x18000c9f8  call    cs:__imp_DeleteObject
0x18000c9fe  mov     r9, [rsp+190h+lParam]; lParam
0x18000ca03  mov     edx, r15d; Msg
0x18000ca06  mov     r8, [rsp+190h+wParam]; wParam
0x18000ca0b  mov     rcx, rdi; hWnd
0x18000ca0e  call    cs:__imp_DefWindowProcW
0x18000ca14  mov     rcx, [rbp+90h+var_50]
0x18000ca18  xor     rcx, rsp; StackCookie
0x18000ca1b  call    __security_check_cookie
0x18000ca20  add     rsp, 158h
0x18000ca27  pop     r15
0x18000ca29  pop     r14
0x18000ca2b  pop     r13
0x18000ca2d  pop     r12
0x18000ca2f  pop     rdi
0x18000ca30  pop     rsi
0x18000ca31  pop     rbx
0x18000ca32  pop     rbp
0x18000ca33  retn
```
