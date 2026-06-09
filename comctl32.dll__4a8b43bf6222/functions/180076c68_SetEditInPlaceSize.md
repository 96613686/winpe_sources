# SetEditInPlaceSize

- ea: `0x180076c68`
- end: `0x180076f48`
- name: `SetEditInPlaceSize`
- size: `736`
- prototype: `__int64 __fastcall(HWND hWnd, LPRECT lprcDst, HGDIOBJ h)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18006b160`
- `0x180076674`

## callees

- `0x1800115f0`
- `0x180076c68`

## import_xrefs

- `GDI32!SelectObject` at `0x180076d42`
- `GDI32!SelectObject` at `0x180076d42`
- `USER32!GetClientRect` at `0x180076e39`
- `USER32!GetClientRect` at `0x180076e39`
- `USER32!GetWindowLongW` at `0x180076e7a`
- `USER32!GetWindowLongW` at `0x180076e8a`
- `USER32!GetWindowLongW` at `0x180076e7a`
- `USER32!GetWindowLongW` at `0x180076e8a`
- `USER32!GetParent` at `0x180076cb9`
- `USER32!GetParent` at `0x180076cb9`
- `USER32!SetWindowPos` at `0x180076ef2`
- `USER32!SetWindowPos` at `0x180076ef2`
- `USER32!GetDC` at `0x180076d33`
- `USER32!GetDC` at `0x180076d33`
- `USER32!ReleaseDC` at `0x180076e2b`
- `USER32!ReleaseDC` at `0x180076e2b`
- `USER32!SendMessageW` at `0x180076e64`
- `USER32!SendMessageW` at `0x180076e64`
- `USER32!CopyRect` at `0x180076f00`
- `USER32!CopyRect` at `0x180076f00`
- `USER32!DrawTextW` at `0x180076d9f`
- `USER32!DrawTextW` at `0x180076d9f`
- `USER32!InvalidateRect` at `0x180076f0f`
- `USER32!InvalidateRect` at `0x180076f0f`
- `USER32!InflateRect` at `0x180076eb6`
- `USER32!InflateRect` at `0x180076eb6`
- `USER32!IntersectRect` at `0x180076e4e`
- `USER32!IntersectRect` at `0x180076e4e`
- `USER32!GetWindowTextW` at `0x180076cd2`
- `USER32!GetWindowTextW` at `0x180076cd2`
- `USER32!OffsetRect` at `0x180076dfe`
- `USER32!OffsetRect` at `0x180076dfe`
- `USER32!AdjustWindowRectEx` at `0x180076e9d`
- `USER32!AdjustWindowRectEx` at `0x180076e9d`
- `USER32!HideCaret` at `0x180076ebf`
- `USER32!HideCaret` at `0x180076ebf`
- `USER32!ShowCaret` at `0x180076f18`
- `USER32!ShowCaret` at `0x180076f18`

## pseudocode

```c
BOOL __fastcall SetEditInPlaceSize(HWND hWnd, LPRECT lprcDst, HGDIOBJ h, char a4)
{
  __int64 v8; // rbx
  HWND Parent; // r13
  int WindowTextW; // r14d
  __int64 v11; // rcx
  const wchar_t *v12; // rdx
  WCHAR *v13; // rax
  WCHAR *v14; // rcx
  HDC DC; // rbx
  int v16; // esi
  UINT format; // eax
  LONG right; // ecx
  LONG top; // r8d
  LONG left; // ecx
  LONG v21; // edx
  LONG WindowLongW; // ebx
  LONG v23; // eax
  struct tagRECT rc; // [rsp+40h] [rbp-C0h] BYREF
  LPARAM lParam[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct tagRECT Rect; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR String[264]; // [rsp+70h] [rbp-90h] BYREF

  rc = 0;
  Rect = 0;
  *(_OWORD *)lParam = 0;
  v8 = 261;
  Parent = GetParent(hWnd);
  WindowTextW = GetWindowTextW(hWnd, String, 261);
  if ( !String[0] )
  {
    v11 = 2147483646;
    v12 = L" ";
    v13 = String;
    do
    {
      if ( !v11 )
        break;
      if ( !*v12 )
        break;
      *v13++ = *v12++;
      --v11;
      --v8;
    }
    while ( v8 );
    v14 = v13 - 1;
    WindowTextW = 1;
    if ( v8 )
      v14 = v13;
    *v14 = 0;
  }
  DC = GetDC(Parent);
  SelectObject(DC, h);
  rc.bottom = 0;
  *(_QWORD *)&rc.left = 0;
  rc.right = g_cxIconSpacing - 2 * g_cxLabelMargin;
  v16 = a4 & 1;
  if ( v16 )
  {
    format = 11281;
    if ( g_uiACP == 949 )
      format = 535569;
  }
  else
  {
    format = 11297;
  }
  DrawTextW(DC, String, WindowTextW, &rc, format);
  right = rc.right;
  top = lprcDst->top;
  if ( rc.right < g_cxIconSpacing / 4 )
    right = g_cxIconSpacing / 4;
  rc.right = right;
  if ( v16 )
  {
    left = lprcDst->left + (rc.left + lprcDst->right - lprcDst->left - right) / 2;
  }
  else
  {
    left = lprcDst->left;
    top += (rc.top + lprcDst->bottom - top - rc.bottom) / 2;
  }
  OffsetRect(&rc, left, top);
  if ( v16 )
    v21 = rc.right;
  else
    v21 = rc.right + 4 * g_cxLabelMargin;
  rc.right = g_cyEdge + v21;
  ReleaseDC(Parent, DC);
  GetClientRect(Parent, &Rect);
  IntersectRect(&rc, &rc, &Rect);
  SendMessageW(hWnd, 0xB2u, 0, (LPARAM)lParam);
  HIDWORD(lParam[0]) = -HIDWORD(lParam[0]);
  LODWORD(lParam[0]) = -LODWORD(lParam[0]);
  WindowLongW = GetWindowLongW(hWnd, -20);
  v23 = GetWindowLongW(hWnd, -16);
  AdjustWindowRectEx((LPRECT)lParam, v23, 0, WindowLongW);
  InflateRect(&rc, -LODWORD(lParam[0]), -HIDWORD(lParam[0]));
  HideCaret(hWnd);
  SetWindowPos(hWnd, 0, rc.left, rc.top, rc.right - rc.left, rc.bottom - rc.top, 0x114u);
  CopyRect(lprcDst, &rc);
  InvalidateRect(hWnd, 0, 1);
  return ShowCaret(hWnd);
}

```

## disassembly

```asm
0x180076c68  mov     [rsp-8+arg_18], rbx
0x180076c6d  push    rbp
0x180076c6e  push    rsi
0x180076c6f  push    rdi
0x180076c70  push    r12
0x180076c72  push    r13
0x180076c74  push    r14
0x180076c76  push    r15
0x180076c78  lea     rbp, [rsp-190h]
0x180076c80  sub     rsp, 290h
0x180076c87  mov     rax, cs:__security_cookie
0x180076c8e  xor     rax, rsp
0x180076c91  mov     [rbp+1C0h+var_40], rax
0x180076c98  xorps   xmm0, xmm0
0x180076c9b  xorps   xmm1, xmm1
0x180076c9e  movups  xmmword ptr [rsp+2C0h+rc.left], xmm0
0x180076ca3  mov     esi, r9d
0x180076ca6  mov     r12, r8
0x180076ca9  movups  xmmword ptr [rsp+2C0h+Rect.left], xmm1
0x180076cae  mov     rdi, rdx
0x180076cb1  mov     r15, rcx
0x180076cb4  movups  xmmword ptr [rsp+2C0h+lParam], xmm0
0x180076cb9  call    cs:__imp_GetParent
0x180076cbf  mov     ebx, 105h
0x180076cc4  lea     rdx, [rsp+2C0h+String]; lpString
0x180076cc9  mov     r8d, ebx; nMaxCount
0x180076ccc  mov     rcx, r15; hWnd
0x180076ccf  mov     r13, rax
0x180076cd2  call    cs:__imp_GetWindowTextW
0x180076cd8  xor     r9d, r9d
0x180076cdb  mov     r14d, eax
0x180076cde  cmp     [rsp+2C0h+String], r9w
0x180076ce4  jnz     short loc_180076D30
0x180076ce6  mov     ecx, 7FFFFFFEh
0x180076ceb  lea     rdx, c_szSpace; " "
0x180076cf2  lea     rax, [rsp+2C0h+String]
0x180076cf7  test    rcx, rcx
0x180076cfa  jz      short loc_180076D1B
0x180076cfc  movzx   r8d, word ptr [rdx]
0x180076d00  test    r8w, r8w
0x180076d04  jz      short loc_180076D1B
0x180076d06  mov     [rax], r8w
0x180076d0a  add     rdx, 2
0x180076d0e  add     rax, 2
0x180076d12  dec     rcx
0x180076d15  sub     rbx, 1
0x180076d19  jnz     short loc_180076CF7
0x180076d1b  test    rbx, rbx
0x180076d1e  lea     rcx, [rax-2]
0x180076d22  mov     r14d, 1
0x180076d28  cmovnz  rcx, rax
0x180076d2c  mov     [rcx], r9w
0x180076d30  mov     rcx, r13; hWnd
0x180076d33  call    cs:__imp_GetDC
0x180076d39  mov     rcx, rax; hdc
0x180076d3c  mov     rdx, r12; h
0x180076d3f  mov     rbx, rax
0x180076d42  call    cs:__imp_SelectObject
0x180076d48  mov     ecx, cs:g_cxLabelMargin
0x180076d4e  xor     r12d, r12d
0x180076d51  mov     edx, cs:g_cxIconSpacing
0x180076d57  add     ecx, ecx
0x180076d59  sub     edx, ecx
0x180076d5b  mov     [rsp+2C0h+rc.bottom], r12d
0x180076d60  mov     qword ptr [rsp+2C0h+rc.left], r12
0x180076d65  mov     [rsp+2C0h+rc.right], edx
0x180076d69  and     esi, 1
0x180076d6c  jz      short loc_180076D86
0x180076d6e  cmp     cs:g_uiACP, 3B5h
0x180076d78  mov     eax, 2C11h
0x180076d7d  jnz     short loc_180076D8B
0x180076d7f  mov     eax, 82C11h
0x180076d84  jmp     short loc_180076D8B
0x180076d86  mov     eax, 2C21h
0x180076d8b  lea     r9, [rsp+2C0h+rc]; lprc
0x180076d90  mov     [rsp+2C0h+format], eax; format
0x180076d94  mov     r8d, r14d; cchText
0x180076d97  lea     rdx, [rsp+2C0h+String]; lpchText
0x180076d9c  mov     rcx, rbx; hdc
0x180076d9f  call    cs:__imp_DrawTextW
0x180076da5  mov     ecx, [rsp+2C0h+rc.right]
0x180076da9  mov     eax, cs:g_cxIconSpacing
0x180076daf  mov     r8d, [rdi+4]
0x180076db3  cdq
0x180076db4  and     edx, 3
0x180076db7  add     eax, edx
0x180076db9  sar     eax, 2
0x180076dbc  cmp     ecx, eax
0x180076dbe  cmovl   ecx, eax
0x180076dc1  mov     [rsp+2C0h+rc.right], ecx
0x180076dc5  test    esi, esi
0x180076dc7  jz      short loc_180076DDF
0x180076dc9  mov     eax, [rdi+8]
0x180076dcc  sub     eax, [rdi]
0x180076dce  sub     eax, ecx
0x180076dd0  add     eax, [rsp+2C0h+rc.left]
0x180076dd4  cdq
0x180076dd5  sub     eax, edx
0x180076dd7  sar     eax, 1
0x180076dd9  mov     ecx, eax
0x180076ddb  add     ecx, [rdi]
0x180076ddd  jmp     short loc_180076DF7
0x180076ddf  mov     eax, [rdi+0Ch]
0x180076de2  mov     ecx, [rdi]
0x180076de4  sub     eax, r8d
0x180076de7  sub     eax, [rsp+2C0h+rc.bottom]
0x180076deb  add     eax, [rsp+2C0h+rc.top]
0x180076def  cdq
0x180076df0  sub     eax, edx
0x180076df2  sar     eax, 1
0x180076df4  add     r8d, eax; dy
0x180076df7  mov     edx, ecx; dx
0x180076df9  lea     rcx, [rsp+2C0h+rc]; lprc
0x180076dfe  call    cs:__imp_OffsetRect
0x180076e04  test    esi, esi
0x180076e06  jnz     short loc_180076E17
0x180076e08  mov     ecx, [rsp+2C0h+rc.right]
0x180076e0c  mov     eax, cs:g_cxLabelMargin
0x180076e12  lea     edx, [rcx+rax*4]
0x180076e15  jmp     short loc_180076E1B
0x180076e17  mov     edx, [rsp+2C0h+rc.right]
0x180076e1b  add     edx, cs:g_cyEdge
0x180076e21  mov     rcx, r13; hWnd
0x180076e24  mov     [rsp+2C0h+rc.right], edx
0x180076e28  mov     rdx, rbx; hDC
0x180076e2b  call    cs:__imp_ReleaseDC
0x180076e31  lea     rdx, [rsp+2C0h+Rect]; lpRect
0x180076e36  mov     rcx, r13; hWnd
0x180076e39  call    cs:__imp_GetClientRect
0x180076e3f  lea     r8, [rsp+2C0h+Rect]; lprcSrc2
0x180076e44  lea     rdx, [rsp+2C0h+rc]; lprcSrc1
0x180076e49  lea     rcx, [rsp+2C0h+rc]; lprcDst
0x180076e4e  call    cs:__imp_IntersectRect
0x180076e54  lea     r9, [rsp+2C0h+lParam]; lParam
0x180076e59  xor     r8d, r8d; wParam
0x180076e5c  mov     edx, 0B2h; Msg
0x180076e61  mov     rcx, r15; hWnd
0x180076e64  call    cs:__imp_SendMessageW
0x180076e6a  neg     dword ptr [rsp+2C0h+lParam+4]
0x180076e6e  mov     edx, 0FFFFFFECh; nIndex
0x180076e73  neg     dword ptr [rsp+2C0h+lParam]
0x180076e77  mov     rcx, r15; hWnd
0x180076e7a  call    cs:__imp_GetWindowLongW
0x180076e80  mov     edx, 0FFFFFFF0h; nIndex
0x180076e85  mov     rcx, r15; hWnd
0x180076e88  mov     ebx, eax
0x180076e8a  call    cs:__imp_GetWindowLongW
0x180076e90  mov     r9d, ebx; dwExStyle
0x180076e93  lea     rcx, [rsp+2C0h+lParam]; lpRect
0x180076e98  mov     edx, eax; dwStyle
0x180076e9a  xor     r8d, r8d; bMenu
0x180076e9d  call    cs:__imp_AdjustWindowRectEx
0x180076ea3  mov     r8d, dword ptr [rsp+2C0h+lParam+4]
0x180076ea8  lea     rcx, [rsp+2C0h+rc]; lprc
0x180076ead  mov     edx, dword ptr [rsp+2C0h+lParam]
0x180076eb1  neg     r8d; dy
0x180076eb4  neg     edx; dx
0x180076eb6  call    cs:__imp_InflateRect
0x180076ebc  mov     rcx, r15; hWnd
0x180076ebf  call    cs:__imp_HideCaret
0x180076ec5  mov     edx, [rsp+2C0h+rc.bottom]
0x180076ec9  mov     rcx, r15; hWnd
0x180076ecc  mov     r9d, [rsp+2C0h+rc.top]; Y
0x180076ed1  sub     edx, r9d
0x180076ed4  mov     eax, [rsp+2C0h+rc.right]
0x180076ed8  mov     r8d, [rsp+2C0h+rc.left]; X
0x180076edd  sub     eax, r8d
0x180076ee0  mov     [rsp+2C0h+uFlags], 114h; uFlags
0x180076ee8  mov     [rsp+2C0h+cy], edx; cy
0x180076eec  xor     edx, edx; hWndInsertAfter
0x180076eee  mov     [rsp+2C0h+format], eax; cx
0x180076ef2  call    cs:__imp_SetWindowPos
0x180076ef8  lea     rdx, [rsp+2C0h+rc]; lprcSrc
0x180076efd  mov     rcx, rdi; lprcDst
0x180076f00  call    cs:__imp_CopyRect
0x180076f06  xor     edx, edx; lpRect
0x180076f08  mov     rcx, r15; hWnd
0x180076f0b  lea     r8d, [rdx+1]; bErase
0x180076f0f  call    cs:__imp_InvalidateRect
0x180076f15  mov     rcx, r15; hWnd
0x180076f18  call    cs:__imp_ShowCaret
0x180076f1e  mov     rcx, [rbp+1C0h+var_40]
0x180076f25  xor     rcx, rsp; StackCookie
0x180076f28  call    __security_check_cookie
0x180076f2d  mov     rbx, [rsp+2C0h+arg_18]
0x180076f35  add     rsp, 290h
0x180076f3c  pop     r15
0x180076f3e  pop     r14
0x180076f40  pop     r13
0x180076f42  pop     r12
0x180076f44  pop     rdi
0x180076f45  pop     rsi
0x180076f46  pop     rbp
0x180076f47  retn
```
