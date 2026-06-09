# FontPreviewWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18000a5f0`
- end: `0x18000a873`
- name: `?FontPreviewWndProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `643`
- prototype: `__int64 __fastcall(HWND, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800015b0`
- `0x180002088`
- `0x18000a5f0`
- `0x180010470`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x18000a689`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x18000a689`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DefWindowProcW` at `0x18000a653`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DefWindowProcW` at `0x18000a653`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClientRect` at `0x18000a744`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClientRect` at `0x18000a744`
- `api-ms-win-ntuser-rectangle-l1-1-0!InflateRect` at `0x18000a7db`
- `api-ms-win-ntuser-rectangle-l1-1-0!InflateRect` at `0x18000a7db`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18000a769`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18000a790`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18000a815`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18000a837`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18000a769`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18000a790`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18000a815`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18000a837`
- `ext-ms-win-gdi-draw-l1-1-1!PatBlt` at `0x18000a7c3`
- `ext-ms-win-gdi-draw-l1-1-1!PatBlt` at `0x18000a7c3`
- `ext-ms-win-gdi-draw-l1-1-1!SetBkColor` at `0x18000a731`
- `ext-ms-win-gdi-draw-l1-1-1!SetBkColor` at `0x18000a731`
- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x18000a77a`
- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x18000a77a`
- `ext-ms-win-gdi-font-l1-1-1!SetTextColor` at `0x18000a71f`
- `ext-ms-win-gdi-font-l1-1-1!SetTextColor` at `0x18000a71f`
- `ext-ms-win-ntuser-draw-l1-1-0!BeginPaint` at `0x18000a675`
- `ext-ms-win-ntuser-draw-l1-1-0!BeginPaint` at `0x18000a675`
- `ext-ms-win-ntuser-draw-l1-1-0!EndPaint` at `0x18000a84a`
- `ext-ms-win-ntuser-draw-l1-1-0!EndPaint` at `0x18000a84a`
- `ext-ms-win-ntuser-misc-l1-1-0!DrawTextW` at `0x18000a802`
- `ext-ms-win-ntuser-misc-l1-1-0!DrawTextW` at `0x18000a802`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18000a824`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18000a824`
- `ext-ms-win-gdi-internal-desktop-l1-1-0!GetNearestColor` at `0x18000a6b2`
- `ext-ms-win-gdi-internal-desktop-l1-1-0!GetNearestColor` at `0x18000a6e3`
- `ext-ms-win-gdi-internal-desktop-l1-1-0!GetNearestColor` at `0x18000a70b`
- `ext-ms-win-gdi-internal-desktop-l1-1-0!GetNearestColor` at `0x18000a6b2`
- `ext-ms-win-gdi-internal-desktop-l1-1-0!GetNearestColor` at `0x18000a6e3`
- `ext-ms-win-gdi-internal-desktop-l1-1-0!GetNearestColor` at `0x18000a70b`

## string_xrefs

- `0x18000a7fb`: `C:\WINDOWS> dir                       \nSYSTEM       <DIR>     10-01-99   5:00a\nSYSTEM32     <DIR>     10-01-99   5:00a\nREADME   TXT     26926 10-01-99   5:00a\nWINDOWS  BMP     46080 10-01-99   5:00a\nNOTEPAD  EXE    337232 10-01-99   5:00a\nCLOCK    AVI     39594 10-01-99   5:00p\nWIN      INI      7005 10-01-99   5:00a\n`

## pseudocode

```c
LRESULT __fastcall FontPreviewWndProc(HWND a1, UINT Msg, WPARAM wParam, LPARAM lParam)
{
  COLORREF NearestColor; // edi
  COLORREF v10; // edx
  COLORREF v11; // ebx
  HGDIOBJ v12; // rsi
  HBRUSH SolidBrush; // rdi
  HGDIOBJ v14; // rbx
  tagPAINTSTRUCT Paint; // [rsp+30h] [rbp-39h] BYREF
  struct tagRECT Rect; // [rsp+80h] [rbp+17h] BYREF

  memset_0(&Paint, 0, sizeof(Paint));
  Rect = 0;
  if ( Msg == 15 )
  {
    BeginPaint(a1, &Paint);
    if ( GetWindowLongW(a1, -12) == 422 )
    {
      NearestColor = GetNearestColor(Paint.hdc, *((_DWORD *)gpStateInfo + (*((_BYTE *)gpStateInfo + 102) & 0xF) + 28));
      v10 = *((_DWORD *)gpStateInfo + ((*((_WORD *)gpStateInfo + 51) >> 4) & 0xF) + 28);
    }
    else
    {
      NearestColor = GetNearestColor(Paint.hdc, *((_DWORD *)gpStateInfo + (*((_BYTE *)gpStateInfo + 100) & 0xF) + 28));
      v10 = *((_DWORD *)gpStateInfo + ((*((_WORD *)gpStateInfo + 50) >> 4) & 0xF) + 28);
    }
    v11 = GetNearestColor(Paint.hdc, v10);
    SetTextColor(Paint.hdc, NearestColor);
    SetBkColor(Paint.hdc, v11);
    GetClientRect(a1, &Rect);
    v12 = SelectObject(Paint.hdc, *((HGDIOBJ *)FontInfo + 5 * g_currentFontIndex));
    SolidBrush = CreateSolidBrush(v11);
    v14 = SelectObject(Paint.hdc, SolidBrush);
    PatBlt(Paint.hdc, Rect.left, Rect.top, Rect.right - Rect.left, Rect.bottom - Rect.top, 0xF00021u);
    InflateRect(&Rect, -2, -2);
    DrawTextW(
      Paint.hdc,
      L"C:\\WINDOWS> dir                       \n"
       "SYSTEM       <DIR>     10-01-99   5:00a\n"
       "SYSTEM32     <DIR>     10-01-99   5:00a\n"
       "README   TXT     26926 10-01-99   5:00a\n"
       "WINDOWS  BMP     46080 10-01-99   5:00a\n"
       "NOTEPAD  EXE    337232 10-01-99   5:00a\n"
       "CLOCK    AVI     39594 10-01-99   5:00p\n"
       "WIN      INI      7005 10-01-99   5:00a\n",
      -1,
      &Rect,
      0);
    SelectObject(Paint.hdc, v14);
    DeleteObject(SolidBrush);
    SelectObject(Paint.hdc, v12);
    EndPaint(a1, &Paint);
  }
  else if ( Msg != 20 )
  {
    if ( Msg != 736 )
      return DefWindowProcW(a1, Msg, wParam, lParam);
    RecreateFontHandles(a1);
  }
  return 0;
}

```

## disassembly

```asm
0x18000a5f0  push    rbp
0x18000a5f2  push    rbx
0x18000a5f3  push    rsi
0x18000a5f4  push    rdi
0x18000a5f5  push    r14
0x18000a5f7  lea     rbp, [rsp-37h]
0x18000a5fc  sub     rsp, 0A0h
0x18000a603  mov     rax, cs:__security_cookie
0x18000a60a  xor     rax, rsp
0x18000a60d  mov     [rbp+57h+var_30], rax
0x18000a611  mov     ebx, edx
0x18000a613  mov     rdi, r8
0x18000a616  xor     edx, edx; Val
0x18000a618  mov     r14, rcx
0x18000a61b  lea     rcx, [rbp+57h+Paint]; void *
0x18000a61f  mov     rsi, r9
0x18000a622  lea     r8d, [rdx+48h]; Size
0x18000a626  call    memset_0
0x18000a62b  xorps   xmm0, xmm0
0x18000a62e  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18000a632  cmp     ebx, 0Fh
0x18000a635  jz      short loc_18000A66E
0x18000a637  cmp     ebx, 14h
0x18000a63a  jz      loc_18000A856
0x18000a640  mov     rcx, r14; HWND
0x18000a643  cmp     ebx, 2E0h
0x18000a649  jz      short loc_18000A664
0x18000a64b  mov     r9, rsi; lParam
0x18000a64e  mov     r8, rdi; wParam
0x18000a651  mov     edx, ebx; Msg
0x18000a653  call    cs:__imp_DefWindowProcW
0x18000a65a  nop     dword ptr [rax+rax+00h]
0x18000a65f  jmp     loc_18000A858
0x18000a664  call    ?RecreateFontHandles@@YAXQEAUHWND__@@@Z; RecreateFontHandles(HWND__ * const)
0x18000a669  jmp     loc_18000A856
0x18000a66e  lea     rdx, [rbp+57h+Paint]; lpPaint
0x18000a672  mov     rcx, r14; hWnd
0x18000a675  call    cs:__imp_BeginPaint
0x18000a67c  nop     dword ptr [rax+rax+00h]
0x18000a681  mov     edx, 0FFFFFFF4h; nIndex
0x18000a686  mov     rcx, r14; hWnd
0x18000a689  call    cs:__imp_GetWindowLongW
0x18000a690  nop     dword ptr [rax+rax+00h]
0x18000a695  mov     rcx, [rbp+57h+Paint.hdc]; hdc
0x18000a699  cmp     eax, 1A6h
0x18000a69e  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000a6a5  jnz     short loc_18000A6D8
0x18000a6a7  movzx   edx, byte ptr [rax+66h]
0x18000a6ab  and     edx, 0Fh
0x18000a6ae  mov     edx, [rax+rdx*4+70h]; color
0x18000a6b2  call    cs:__imp_GetNearestColor
0x18000a6b9  nop     dword ptr [rax+rax+00h]
0x18000a6be  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000a6c5  mov     edi, eax
0x18000a6c7  movzx   edx, word ptr [rcx+66h]
0x18000a6cb  shr     dx, 4
0x18000a6cf  and     edx, 0Fh
0x18000a6d2  mov     edx, [rcx+rdx*4+70h]
0x18000a6d6  jmp     short loc_18000A707
0x18000a6d8  movzx   edx, byte ptr [rax+64h]
0x18000a6dc  and     edx, 0Fh
0x18000a6df  mov     edx, [rax+rdx*4+70h]; color
0x18000a6e3  call    cs:__imp_GetNearestColor
0x18000a6ea  nop     dword ptr [rax+rax+00h]
0x18000a6ef  mov     edi, eax
0x18000a6f1  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000a6f8  movzx   edx, word ptr [rax+64h]
0x18000a6fc  shr     dx, 4
0x18000a700  and     edx, 0Fh
0x18000a703  mov     edx, [rax+rdx*4+70h]; color
0x18000a707  mov     rcx, [rbp+57h+Paint.hdc]; hdc
0x18000a70b  call    cs:__imp_GetNearestColor
0x18000a712  nop     dword ptr [rax+rax+00h]
0x18000a717  mov     rcx, [rbp+57h+Paint.hdc]; hdc
0x18000a71b  mov     edx, edi; color
0x18000a71d  mov     ebx, eax
0x18000a71f  call    cs:__imp_SetTextColor
0x18000a726  nop     dword ptr [rax+rax+00h]
0x18000a72b  mov     rcx, [rbp+57h+Paint.hdc]; hdc
0x18000a72f  mov     edx, ebx; color
0x18000a731  call    cs:__imp_SetBkColor
0x18000a738  nop     dword ptr [rax+rax+00h]
0x18000a73d  lea     rdx, [rbp+57h+Rect]; lpRect
0x18000a741  mov     rcx, r14; hWnd
0x18000a744  call    cs:__imp_GetClientRect
0x18000a74b  nop     dword ptr [rax+rax+00h]
0x18000a750  mov     eax, cs:?g_currentFontIndex@@3KA; ulong g_currentFontIndex
0x18000a756  mov     rdx, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x18000a75d  lea     rcx, [rax+rax*4]
0x18000a761  mov     rdx, [rdx+rcx*8]; h
0x18000a765  mov     rcx, [rbp+57h+Paint.hdc]; hdc
0x18000a769  call    cs:__imp_SelectObject
0x18000a770  nop     dword ptr [rax+rax+00h]
0x18000a775  mov     ecx, ebx; color
0x18000a777  mov     rsi, rax
0x18000a77a  call    cs:__imp_CreateSolidBrush
0x18000a781  nop     dword ptr [rax+rax+00h]
0x18000a786  mov     rcx, [rbp+57h+Paint.hdc]; hdc
0x18000a78a  mov     rdx, rax; h
0x18000a78d  mov     rdi, rax
0x18000a790  call    cs:__imp_SelectObject
0x18000a797  nop     dword ptr [rax+rax+00h]
0x18000a79c  mov     ecx, [rbp+57h+Rect.bottom]
0x18000a79f  mov     rbx, rax
0x18000a7a2  mov     r8d, [rbp+57h+Rect.top]; y
0x18000a7a6  sub     ecx, r8d
0x18000a7a9  mov     r9d, [rbp+57h+Rect.right]
0x18000a7ad  mov     edx, [rbp+57h+Rect.left]; x
0x18000a7b0  sub     r9d, edx; w
0x18000a7b3  mov     [rsp+0C0h+rop], 0F00021h; rop
0x18000a7bb  mov     [rsp+0C0h+h], ecx; h
0x18000a7bf  mov     rcx, [rbp+57h+Paint.hdc]; hdc
0x18000a7c3  call    cs:__imp_PatBlt
0x18000a7ca  nop     dword ptr [rax+rax+00h]
0x18000a7cf  mov     edx, 0FFFFFFFEh; dx
0x18000a7d4  lea     rcx, [rbp+57h+Rect]; lprc
0x18000a7d8  mov     r8d, edx; dy
0x18000a7db  call    cs:__imp_InflateRect
0x18000a7e2  nop     dword ptr [rax+rax+00h]
0x18000a7e7  mov     rcx, [rbp+57h+Paint.hdc]; hdc
0x18000a7eb  lea     r9, [rbp+57h+Rect]; lprc
0x18000a7ef  or      r8d, 0FFFFFFFFh; cchText
0x18000a7f3  mov     [rsp+0C0h+h], 0; format
0x18000a7fb  lea     rdx, ?g_szPreviewText@@3QB_WB; "C:\\WINDOWS> dir                       "...
0x18000a802  call    cs:__imp_DrawTextW
0x18000a809  nop     dword ptr [rax+rax+00h]
0x18000a80e  mov     rcx, [rbp+57h+Paint.hdc]; hdc
0x18000a812  mov     rdx, rbx; h
0x18000a815  call    cs:__imp_SelectObject
0x18000a81c  nop     dword ptr [rax+rax+00h]
0x18000a821  mov     rcx, rdi; ho
0x18000a824  call    cs:__imp_DeleteObject
0x18000a82b  nop     dword ptr [rax+rax+00h]
0x18000a830  mov     rcx, [rbp+57h+Paint.hdc]; hdc
0x18000a834  mov     rdx, rsi; h
0x18000a837  call    cs:__imp_SelectObject
0x18000a83e  nop     dword ptr [rax+rax+00h]
0x18000a843  lea     rdx, [rbp+57h+Paint]; lpPaint
0x18000a847  mov     rcx, r14; hWnd
0x18000a84a  call    cs:__imp_EndPaint
0x18000a851  nop     dword ptr [rax+rax+00h]
0x18000a856  xor     eax, eax
0x18000a858  mov     rcx, [rbp+57h+var_30]
0x18000a85c  xor     rcx, rsp; StackCookie
0x18000a85f  call    __security_check_cookie
0x18000a864  add     rsp, 0A0h
0x18000a86b  pop     r14
0x18000a86d  pop     rdi
0x18000a86e  pop     rsi
0x18000a86f  pop     rbx
0x18000a870  pop     rbp
0x18000a871  retn
```
