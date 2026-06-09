# TV_OnSetFont

- ea: `0x18006a770`
- end: `0x18006a94b`
- name: `TV_OnSetFont`
- size: `475`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18006bbb0`
- `0x18007f054`

## callees

- `0x1800115f0`
- `0x180018ab8`
- `0x180068308`
- `0x18006a770`
- `0x18006b33c`
- `0x18006b754`
- `0x18007cf94`
- `0x18007d454`
- `0x18007d538`
- `0x18007e574`
- `0x18008ea60`

## import_xrefs

- `GDI32!GetTextExtentPointW` at `0x18006a846`
- `GDI32!GetTextExtentPointW` at `0x18006a846`
- `GDI32!SelectObject` at `0x18006a820`
- `GDI32!SelectObject` at `0x18006a86d`
- `GDI32!SelectObject` at `0x18006a820`
- `GDI32!SelectObject` at `0x18006a86d`
- `GDI32!DeleteObject` at `0x18006a7c1`
- `GDI32!DeleteObject` at `0x18006a7c1`
- `GDI32!CreateFontIndirectW` at `0x18006a7fc`
- `GDI32!CreateFontIndirectW` at `0x18006a7fc`
- `USER32!GetDC` at `0x18006a80c`
- `USER32!GetDC` at `0x18006a80c`
- `USER32!ReleaseDC` at `0x18006a879`
- `USER32!ReleaseDC` at `0x18006a879`
- `USER32!SystemParametersInfoW` at `0x18006a7f1`
- `USER32!SystemParametersInfoW` at `0x18006a7f1`
- `USER32!SendMessageW` at `0x18006a91d`
- `USER32!SendMessageW` at `0x18006a91d`

## pseudocode

```c
LRESULT __fastcall TV_OnSetFont(__int64 a1, HFONT a2)
{
  bool v2; // zf
  void *v5; // rcx
  HFONT v6; // rax
  HDC DC; // rax
  HDC v8; // rsi
  HGDIOBJ v9; // rbp
  LRESULT result; // rax
  HWND v11; // rcx
  WCHAR String; // [rsp+20h] [rbp-98h] BYREF
  struct tagSIZE sz; // [rsp+28h] [rbp-90h] BYREF
  LOGFONTW pvParam; // [rsp+30h] [rbp-88h] BYREF

  v2 = (*(_BYTE *)(a1 + 56) & 0x40) == 0;
  String = 74;
  sz = 0;
  if ( !v2 )
  {
    v5 = *(void **)(a1 + 200);
    if ( v5 )
    {
      DeleteObject(v5);
      *(_DWORD *)(a1 + 56) &= ~0x40u;
    }
  }
  if ( !a2 )
  {
    memset(&pvParam, 0, sizeof(pvParam));
    SystemParametersInfoW(0x1Fu, 0x5Cu, &pvParam, 0);
    v6 = CreateFontIndirectW(&pvParam);
    *(_DWORD *)(a1 + 56) |= 0x40u;
    a2 = v6;
  }
  DC = GetDC(*(HWND *)a1);
  v8 = DC;
  if ( a2 )
    v9 = SelectObject(DC, a2);
  else
    v9 = 0;
  sz.cy = 0;
  GetTextExtentPointW(v8, &String, 1, &sz);
  *(_WORD *)(a1 + 300) = LOWORD(sz.cy) + 2 * g_cyBorder;
  if ( v9 )
    SelectObject(v8, v9);
  ReleaseDC(*(HWND *)a1, v8);
  *(_QWORD *)(a1 + 200) = a2;
  if ( *(_QWORD *)(a1 + 216) )
    TV_CreateBoldFont(a1);
  *(_DWORD *)(a1 + 28) = GetCodePageForFont(a2);
  TV_DeleteHotFonts(a1);
  if ( !*(_WORD *)(a1 + 308) )
  {
    if ( !*(_WORD *)(a1 + 302) )
      *(_WORD *)(a1 + 302) = *(_WORD *)(a1 + 300);
    TV_SetIndent(a1, 19);
  }
  TV_RecomputeItemWidths(a1);
  *(_WORD *)(a1 + 314) = TV_RecomputeMaxWidth(a1);
  TV_CalcScrollBars(a1);
  result = TV_SetItemHeight(a1);
  v11 = *(HWND *)(a1 + 360);
  if ( v11 )
    return SendMessageW(v11, 0x30u, *(_QWORD *)(a1 + 200), 1);
  return result;
}

```

## disassembly

```asm
0x18006a770  mov     [rsp+arg_10], rbx
0x18006a775  mov     [rsp+arg_18], rbp
0x18006a77a  push    rsi
0x18006a77b  push    rdi
0x18006a77c  push    r14
0x18006a77e  sub     rsp, 0A0h
0x18006a785  mov     rax, cs:__security_cookie
0x18006a78c  xor     rax, rsp
0x18006a78f  mov     [rsp+0B8h+var_28], rax
0x18006a797  xor     r14d, r14d
0x18006a79a  mov     eax, 4Ah ; 'J'
0x18006a79f  test    byte ptr [rcx+38h], 40h
0x18006a7a3  mov     rdi, rdx
0x18006a7a6  mov     rbx, rcx
0x18006a7a9  mov     [rsp+0B8h+String], ax
0x18006a7ae  mov     qword ptr [rsp+0B8h+sz.cx], r14
0x18006a7b3  jz      short loc_18006A7CB
0x18006a7b5  mov     rcx, [rcx+0C8h]; ho
0x18006a7bc  test    rcx, rcx
0x18006a7bf  jz      short loc_18006A7CB
0x18006a7c1  call    cs:__imp_DeleteObject
0x18006a7c7  and     dword ptr [rbx+38h], 0FFFFFFBFh
0x18006a7cb  test    rdi, rdi
0x18006a7ce  jnz     short loc_18006A809
0x18006a7d0  mov     edi, 5Ch ; '\'
0x18006a7d5  lea     rcx, [rsp+0B8h+pvParam]; void *
0x18006a7da  mov     r8d, edi; Size
0x18006a7dd  xor     edx, edx; Val
0x18006a7df  call    memset
0x18006a7e4  xor     r9d, r9d; fWinIni
0x18006a7e7  lea     r8, [rsp+0B8h+pvParam]; pvParam
0x18006a7ec  mov     edx, edi; uiParam
0x18006a7ee  lea     ecx, [rdi-3Dh]; uiAction
0x18006a7f1  call    cs:__imp_SystemParametersInfoW
0x18006a7f7  lea     rcx, [rsp+0B8h+pvParam]; lplf
0x18006a7fc  call    cs:__imp_CreateFontIndirectW
0x18006a802  or      dword ptr [rbx+38h], 40h
0x18006a806  mov     rdi, rax
0x18006a809  mov     rcx, [rbx]; hWnd
0x18006a80c  call    cs:__imp_GetDC
0x18006a812  mov     rsi, rax
0x18006a815  test    rdi, rdi
0x18006a818  jz      short loc_18006A82B
0x18006a81a  mov     rdx, rdi; h
0x18006a81d  mov     rcx, rax; hdc
0x18006a820  call    cs:__imp_SelectObject
0x18006a826  mov     rbp, rax
0x18006a829  jmp     short loc_18006A82E
0x18006a82b  mov     rbp, r14
0x18006a82e  lea     r9, [rsp+0B8h+sz]; lpsz
0x18006a833  mov     [rsp+0B8h+sz.cy], r14d
0x18006a838  mov     r8d, 1; c
0x18006a83e  lea     rdx, [rsp+0B8h+String]; lpString
0x18006a843  mov     rcx, rsi; hdc
0x18006a846  call    cs:__imp_GetTextExtentPointW
0x18006a84c  movzx   eax, word ptr cs:g_cyBorder
0x18006a853  add     ax, ax
0x18006a856  add     ax, word ptr [rsp+0B8h+sz.cy]
0x18006a85b  mov     [rbx+12Ch], ax
0x18006a862  test    rbp, rbp
0x18006a865  jz      short loc_18006A873
0x18006a867  mov     rdx, rbp; h
0x18006a86a  mov     rcx, rsi; hdc
0x18006a86d  call    cs:__imp_SelectObject
0x18006a873  mov     rcx, [rbx]; hWnd
0x18006a876  mov     rdx, rsi; hDC
0x18006a879  call    cs:__imp_ReleaseDC
0x18006a87f  mov     [rbx+0C8h], rdi
0x18006a886  cmp     [rbx+0D8h], r14
0x18006a88d  jz      short loc_18006A897
0x18006a88f  mov     rcx, rbx
0x18006a892  call    TV_CreateBoldFont
0x18006a897  mov     rcx, rdi; h
0x18006a89a  call    GetCodePageForFont
0x18006a89f  mov     rcx, rbx
0x18006a8a2  mov     [rbx+1Ch], eax
0x18006a8a5  call    TV_DeleteHotFonts
0x18006a8aa  cmp     [rbx+134h], r14w
0x18006a8b2  jnz     short loc_18006A8D9
0x18006a8b4  cmp     [rbx+12Eh], r14w
0x18006a8bc  jnz     short loc_18006A8CC
0x18006a8be  movzx   eax, word ptr [rbx+12Ch]
0x18006a8c5  mov     [rbx+12Eh], ax
0x18006a8cc  mov     edx, 13h
0x18006a8d1  mov     rcx, rbx
0x18006a8d4  call    TV_SetIndent
0x18006a8d9  mov     rcx, rbx
0x18006a8dc  call    TV_RecomputeItemWidths
0x18006a8e1  mov     rcx, rbx
0x18006a8e4  call    TV_RecomputeMaxWidth
0x18006a8e9  mov     rcx, rbx
0x18006a8ec  mov     [rbx+13Ah], ax
0x18006a8f3  call    TV_CalcScrollBars
0x18006a8f8  mov     rcx, rbx
0x18006a8fb  call    TV_SetItemHeight
0x18006a900  mov     rcx, [rbx+168h]; hWnd
0x18006a907  test    rcx, rcx
0x18006a90a  jz      short loc_18006A923
0x18006a90c  mov     r8, [rbx+0C8h]; wParam
0x18006a913  mov     r9d, 1; lParam
0x18006a919  lea     edx, [r9+2Fh]; Msg
0x18006a91d  call    cs:__imp_SendMessageW
0x18006a923  mov     rcx, [rsp+0B8h+var_28]
0x18006a92b  xor     rcx, rsp; StackCookie
0x18006a92e  call    __security_check_cookie
0x18006a933  lea     r11, [rsp+0B8h+var_18]
0x18006a93b  mov     rbx, [r11+30h]
0x18006a93f  mov     rbp, [r11+38h]
0x18006a943  mov     rsp, r11
0x18006a946  pop     r14
0x18006a948  pop     rdi
0x18006a949  pop     rsi
0x18006a94a  retn
```
