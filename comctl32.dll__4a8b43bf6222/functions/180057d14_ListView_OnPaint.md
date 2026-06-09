# ListView_OnPaint

- ea: `0x180057d14`
- end: `0x180057f46`
- name: `ListView_OnPaint`
- size: `562`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005c0a0`

## callees

- `0x1800115f0`
- `0x180057d14`
- `0x18005a9e4`
- `0x18005bde8`
- `0x180075c34`
- `0x18007ab40`
- `0x18008ea60`

## import_xrefs

- `GDI32!DeleteObject` at `0x180057e29`
- `GDI32!DeleteObject` at `0x180057e29`
- `GDI32!CreateRectRgn` at `0x180057ddc`
- `GDI32!CreateRectRgn` at `0x180057ddc`
- `GDI32!SetBrushOrgEx` at `0x180057e67`
- `GDI32!SetBrushOrgEx` at `0x180057ef3`
- `GDI32!SetBrushOrgEx` at `0x180057e67`
- `GDI32!SetBrushOrgEx` at `0x180057ef3`
- `GDI32!CombineRgn` at `0x180057e20`
- `GDI32!CombineRgn` at `0x180057e20`
- `USER32!SetRect` at `0x180057e88`
- `USER32!SetRect` at `0x180057e88`
- `USER32!BeginPaint` at `0x180057eb6`
- `USER32!BeginPaint` at `0x180057eb6`
- `USER32!EndPaint` at `0x180057f1b`
- `USER32!EndPaint` at `0x180057f1b`
- `USER32!UpdateWindow` at `0x180057d7f`
- `USER32!UpdateWindow` at `0x180057d7f`
- `USER32!GetUpdateRect` at `0x180057d95`
- `USER32!GetUpdateRect` at `0x180057d95`
- `USER32!GetUpdateRgn` at `0x180057df3`
- `USER32!GetUpdateRgn` at `0x180057df3`

## pseudocode

```c
int __fastcall ListView_OnPaint(__int64 a1, HDC hdc)
{
  bool v4; // zf
  HWND v5; // rcx
  int result; // eax
  int v7; // eax
  __int64 v8; // r8
  HRGN RectRgn; // rax
  HRGN v10; // rdi
  HRGN v11; // rcx
  int v12; // edx
  HDC v13; // rax
  HDC v14; // rdi
  int v15; // edx
  struct tagRECT Rect; // [rsp+30h] [rbp-78h] BYREF
  struct tagPAINTSTRUCT Paint; // [rsp+40h] [rbp-68h] BYREF

  memset(&Paint, 0, sizeof(Paint));
  v4 = *(_DWORD *)(a1 + 304) == 0x7FFFFFFF;
  Rect = 0;
  if ( v4 )
    ListView_Recompute(a1);
  if ( (*(_DWORD *)(a1 + 16) & 3) == 1 )
  {
    v5 = *(HWND *)(a1 + 440);
    if ( v5 )
      UpdateWindow(v5);
  }
  if ( hdc || (result = GetUpdateRect(*(HWND *)a1, &Rect, 0)) != 0 )
  {
    v7 = *(_DWORD *)(a1 + 72);
    if ( (v7 & 2) == 0 )
    {
      v8 = (unsigned int)(*(_DWORD *)(a1 + 512) - 1);
      *(_DWORD *)(a1 + 72) = v7 | 2;
      ListView_MaybeResizeListColumns(a1, 0, v8);
      ListView_UpdateScrollBars(a1);
    }
    if ( (*(_BYTE *)(a1 + 72) & 0x10) == 0 )
    {
      RectRgn = CreateRectRgn(0, 0, 0, 0);
      v10 = RectRgn;
      if ( RectRgn )
      {
        GetUpdateRgn(*(HWND *)a1, RectRgn, 0);
        v11 = *(HRGN *)(a1 + 200);
        if ( v11 )
        {
          if ( v11 != (HRGN)1 )
            CombineRgn(v11, *(HRGN *)(a1 + 200), v10, 2);
          DeleteObject(v10);
        }
        else
        {
          *(_QWORD *)(a1 + 200) = v10;
        }
      }
    }
    if ( hdc )
    {
      if ( (*(_DWORD *)(a1 + 16) & 1) != 0 )
      {
        if ( (*(_DWORD *)(a1 + 16) & 3) == 3 )
          v12 = *(_DWORD *)(a1 + 248);
        else
          v12 = *(_DWORD *)(a1 + 456);
      }
      else
      {
        v12 = *(_DWORD *)(a1 + 296);
      }
      SetBrushOrgEx(hdc, -v12, 0, 0);
      SetRect(&Paint.rcPaint, 0, 0, *(_DWORD *)(a1 + 164), *(_DWORD *)(a1 + 168));
      result = *(_DWORD *)(a1 + 72) & 0x12;
      if ( (*(_BYTE *)(a1 + 72) & 0x12) == 0x12 )
        return ListView_Redraw(a1, hdc);
    }
    else
    {
      v13 = BeginPaint(*(HWND *)a1, &Paint);
      v14 = v13;
      if ( (*(_DWORD *)(a1 + 16) & 1) != 0 )
      {
        if ( (*(_DWORD *)(a1 + 16) & 3) == 3 )
          v15 = *(_DWORD *)(a1 + 248);
        else
          v15 = *(_DWORD *)(a1 + 456);
      }
      else
      {
        v15 = *(_DWORD *)(a1 + 296);
      }
      SetBrushOrgEx(v13, -v15, 0, 0);
      if ( (*(_BYTE *)(a1 + 72) & 0x12) == 0x12 )
        ListView_Redraw(a1, v14);
      return EndPaint(*(HWND *)a1, &Paint);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180057d14  mov     [rsp+arg_10], rbx
0x180057d19  mov     [rsp+arg_18], rsi
0x180057d1e  push    rdi
0x180057d1f  sub     rsp, 0A0h
0x180057d26  mov     rax, cs:__security_cookie
0x180057d2d  xor     rax, rsp
0x180057d30  mov     [rsp+0A8h+var_18], rax
0x180057d38  mov     rsi, rdx
0x180057d3b  mov     rbx, rcx
0x180057d3e  xor     edx, edx; Val
0x180057d40  lea     rcx, [rsp+0A8h+Paint]; void *
0x180057d45  lea     r8d, [rdx+48h]; Size
0x180057d49  call    memset
0x180057d4e  cmp     dword ptr [rbx+130h], 7FFFFFFFh
0x180057d58  xorps   xmm0, xmm0
0x180057d5b  movups  xmmword ptr [rsp+0A8h+Rect.left], xmm0
0x180057d60  jnz     short loc_180057D6A
0x180057d62  mov     rcx, rbx; int
0x180057d65  call    ListView_Recompute
0x180057d6a  mov     eax, [rbx+10h]
0x180057d6d  and     al, 3
0x180057d6f  cmp     al, 1
0x180057d71  jnz     short loc_180057D85
0x180057d73  mov     rcx, [rbx+1B8h]; hWnd
0x180057d7a  test    rcx, rcx
0x180057d7d  jz      short loc_180057D85
0x180057d7f  call    cs:__imp_UpdateWindow
0x180057d85  test    rsi, rsi
0x180057d88  jnz     short loc_180057DA3
0x180057d8a  mov     rcx, [rbx]; hWnd
0x180057d8d  lea     rdx, [rsp+0A8h+Rect]; lpRect
0x180057d92  xor     r8d, r8d; bErase
0x180057d95  call    cs:__imp_GetUpdateRect
0x180057d9b  test    eax, eax
0x180057d9d  jz      loc_180057F21
0x180057da3  mov     eax, [rbx+48h]
0x180057da6  test    al, 2
0x180057da8  jnz     short loc_180057DCC
0x180057daa  mov     r8d, [rbx+200h]
0x180057db1  or      eax, 2
0x180057db4  dec     r8d
0x180057db7  mov     [rbx+48h], eax
0x180057dba  xor     edx, edx
0x180057dbc  mov     rcx, rbx
0x180057dbf  call    ListView_MaybeResizeListColumns
0x180057dc4  mov     rcx, rbx
0x180057dc7  call    ListView_UpdateScrollBars
0x180057dcc  test    byte ptr [rbx+48h], 10h
0x180057dd0  jnz     short loc_180057E2F
0x180057dd2  xor     r9d, r9d; y2
0x180057dd5  xor     r8d, r8d; x2
0x180057dd8  xor     edx, edx; y1
0x180057dda  xor     ecx, ecx; x1
0x180057ddc  call    cs:__imp_CreateRectRgn
0x180057de2  mov     rdi, rax
0x180057de5  test    rax, rax
0x180057de8  jz      short loc_180057E2F
0x180057dea  mov     rcx, [rbx]; hWnd
0x180057ded  xor     r8d, r8d; bErase
0x180057df0  mov     rdx, rax; hRgn
0x180057df3  call    cs:__imp_GetUpdateRgn
0x180057df9  mov     rcx, [rbx+0C8h]; hrgnDst
0x180057e00  test    rcx, rcx
0x180057e03  jnz     short loc_180057E0E
0x180057e05  mov     [rbx+0C8h], rdi
0x180057e0c  jmp     short loc_180057E2F
0x180057e0e  cmp     rcx, 1
0x180057e12  jz      short loc_180057E26
0x180057e14  mov     r9d, 2; iMode
0x180057e1a  mov     r8, rdi; hrgnSrc2
0x180057e1d  mov     rdx, rcx; hrgnSrc1
0x180057e20  call    cs:__imp_CombineRgn
0x180057e26  mov     rcx, rdi; ho
0x180057e29  call    cs:__imp_DeleteObject
0x180057e2f  test    rsi, rsi
0x180057e32  jz      short loc_180057EAE
0x180057e34  mov     eax, [rbx+10h]
0x180057e37  and     eax, 3
0x180057e3a  test    eax, 0FFFFFFFDh
0x180057e3f  jz      short loc_180057E56
0x180057e41  cmp     eax, 3
0x180057e44  jnz     short loc_180057E4E
0x180057e46  mov     edx, [rbx+0F8h]
0x180057e4c  jmp     short loc_180057E5C
0x180057e4e  mov     edx, [rbx+1C8h]
0x180057e54  jmp     short loc_180057E5C
0x180057e56  mov     edx, [rbx+128h]
0x180057e5c  neg     edx; x
0x180057e5e  xor     r9d, r9d; lppt
0x180057e61  xor     r8d, r8d; y
0x180057e64  mov     rcx, rsi; hdc
0x180057e67  call    cs:__imp_SetBrushOrgEx
0x180057e6d  mov     eax, [rbx+0A8h]
0x180057e73  lea     rcx, [rsp+0A8h+Paint.rcPaint]; lprc
0x180057e78  mov     r9d, [rbx+0A4h]; xRight
0x180057e7f  xor     r8d, r8d; yTop
0x180057e82  xor     edx, edx; xLeft
0x180057e84  mov     [rsp+0A8h+yBottom], eax; yBottom
0x180057e88  call    cs:__imp_SetRect
0x180057e8e  mov     eax, [rbx+48h]
0x180057e91  and     eax, 12h
0x180057e94  cmp     al, 12h
0x180057e96  jnz     loc_180057F21
0x180057e9c  lea     r8, [rsp+0A8h+Paint.rcPaint]
0x180057ea1  mov     rdx, rsi; hdc
0x180057ea4  mov     rcx, rbx; int
0x180057ea7  call    ListView_Redraw
0x180057eac  jmp     short loc_180057F21
0x180057eae  mov     rcx, [rbx]; hWnd
0x180057eb1  lea     rdx, [rsp+0A8h+Paint]; lpPaint
0x180057eb6  call    cs:__imp_BeginPaint
0x180057ebc  mov     ecx, [rbx+10h]
0x180057ebf  mov     rdi, rax
0x180057ec2  and     ecx, 3
0x180057ec5  test    ecx, 0FFFFFFFDh
0x180057ecb  jz      short loc_180057EE2
0x180057ecd  cmp     ecx, 3
0x180057ed0  jnz     short loc_180057EDA
0x180057ed2  mov     edx, [rbx+0F8h]
0x180057ed8  jmp     short loc_180057EE8
0x180057eda  mov     edx, [rbx+1C8h]
0x180057ee0  jmp     short loc_180057EE8
0x180057ee2  mov     edx, [rbx+128h]
0x180057ee8  neg     edx; x
0x180057eea  xor     r9d, r9d; lppt
0x180057eed  xor     r8d, r8d; y
0x180057ef0  mov     rcx, rdi; hdc
0x180057ef3  call    cs:__imp_SetBrushOrgEx
0x180057ef9  mov     eax, [rbx+48h]
0x180057efc  and     eax, 12h
0x180057eff  cmp     al, 12h
0x180057f01  jnz     short loc_180057F13
0x180057f03  lea     r8, [rsp+0A8h+Paint.rcPaint]
0x180057f08  mov     rdx, rdi; hdc
0x180057f0b  mov     rcx, rbx; int
0x180057f0e  call    ListView_Redraw
0x180057f13  mov     rcx, [rbx]; hWnd
0x180057f16  lea     rdx, [rsp+0A8h+Paint]; lpPaint
0x180057f1b  call    cs:__imp_EndPaint
0x180057f21  mov     rcx, [rsp+0A8h+var_18]
0x180057f29  xor     rcx, rsp; StackCookie
0x180057f2c  call    __security_check_cookie
0x180057f31  lea     r11, [rsp+0A8h+var_8]
0x180057f39  mov     rbx, [r11+20h]
0x180057f3d  mov     rsi, [r11+28h]
0x180057f41  mov     rsp, r11
0x180057f44  pop     rdi
0x180057f45  retn
```
