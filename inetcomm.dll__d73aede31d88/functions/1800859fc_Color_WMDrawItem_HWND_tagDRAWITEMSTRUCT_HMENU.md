# Color_WMDrawItem(HWND__ *,tagDRAWITEMSTRUCT *,HMENU__ *)

- ea: `0x1800859fc`
- end: `0x180085cc2`
- name: `?Color_WMDrawItem@@YAXPEAUHWND__@@PEAUtagDRAWITEMSTRUCT@@PEAUHMENU__@@@Z`
- size: `710`
- prototype: `void __fastcall(HWND, struct tagDRAWITEMSTRUCT *, HMENU)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180087fa0`

## callees

- `0x1800859fc`
- `0x1800866d0`
- `0x18008838c`
- `0x1800cc9ba`
- `0x1800cca00`

## import_xrefs

- `GDI32!SelectObject` at `0x180085b2b`
- `GDI32!SelectObject` at `0x180085b88`
- `GDI32!SelectObject` at `0x180085bb3`
- `GDI32!SelectObject` at `0x180085bfa`
- `GDI32!SelectObject` at `0x180085c6e`
- `GDI32!SelectObject` at `0x180085b2b`
- `GDI32!SelectObject` at `0x180085b88`
- `GDI32!SelectObject` at `0x180085bb3`
- `GDI32!SelectObject` at `0x180085bfa`
- `GDI32!SelectObject` at `0x180085c6e`
- `GDI32!DeleteObject` at `0x180085bbc`
- `GDI32!DeleteObject` at `0x180085c77`
- `GDI32!DeleteObject` at `0x180085bbc`
- `GDI32!DeleteObject` at `0x180085c77`
- `GDI32!SetBkColor` at `0x180085a5e`
- `GDI32!SetBkColor` at `0x180085a7c`
- `GDI32!SetBkColor` at `0x180085c91`
- `GDI32!SetBkColor` at `0x180085a5e`
- `GDI32!SetBkColor` at `0x180085a7c`
- `GDI32!SetBkColor` at `0x180085c91`
- `GDI32!SetTextColor` at `0x180085a96`
- `GDI32!SetTextColor` at `0x180085c84`
- `GDI32!SetTextColor` at `0x180085a96`
- `GDI32!SetTextColor` at `0x180085c84`
- `GDI32!CreateSolidBrush` at `0x180085b76`
- `GDI32!CreateSolidBrush` at `0x180085be4`
- `GDI32!CreateSolidBrush` at `0x180085b76`
- `GDI32!CreateSolidBrush` at `0x180085be4`
- `GDI32!ExtTextOutW` at `0x180085b63`
- `GDI32!ExtTextOutW` at `0x180085b63`
- `GDI32!Rectangle` at `0x180085ba6`
- `GDI32!Rectangle` at `0x180085ba6`
- `GDI32!Ellipse` at `0x180085c61`
- `GDI32!Ellipse` at `0x180085c61`
- `USER32!GetSystemMetrics` at `0x180085aa4`
- `USER32!GetSystemMetrics` at `0x180085ab3`
- `USER32!GetSystemMetrics` at `0x180085ac0`
- `USER32!GetSystemMetrics` at `0x180085c08`
- `USER32!GetSystemMetrics` at `0x180085c38`
- `USER32!GetSystemMetrics` at `0x180085aa4`
- `USER32!GetSystemMetrics` at `0x180085ab3`
- `USER32!GetSystemMetrics` at `0x180085ac0`
- `USER32!GetSystemMetrics` at `0x180085c08`
- `USER32!GetSystemMetrics` at `0x180085c38`
- `USER32!GetSysColor` at `0x180085a52`
- `USER32!GetSysColor` at `0x180085a70`
- `USER32!GetSysColor` at `0x180085a8a`
- `USER32!GetSysColor` at `0x180085bdc`
- `USER32!GetSysColor` at `0x180085a52`
- `USER32!GetSysColor` at `0x180085a70`
- `USER32!GetSysColor` at `0x180085a8a`
- `USER32!GetSysColor` at `0x180085bdc`
- `USER32!GetMenuStringW` at `0x180085b0e`
- `USER32!GetMenuStringW` at `0x180085b0e`

## pseudocode

```c
void __fastcall Color_WMDrawItem(HWND a1, struct tagDRAWITEMSTRUCT *a2, HMENU a3)
{
  UINT itemID; // edi
  COLORREF SysColor; // eax
  COLORREF v6; // eax
  int v7; // ecx
  COLORREF v8; // eax
  COLORREF v9; // r15d
  COLORREF v10; // eax
  COLORREF v11; // r12d
  unsigned __int16 v12; // bx
  unsigned __int16 v13; // ax
  int v14; // r14d
  int v15; // esi
  UINT c; // ebx
  HFONT MenuFont; // rax
  COLORREF ColorFromIndex; // eax
  HBRUSH SolidBrush; // rax
  HGDIOBJ v20; // rbx
  HGDIOBJ v21; // rax
  int v22; // ecx
  COLORREF v23; // eax
  HBRUSH v24; // rax
  HGDIOBJ v25; // rsi
  int v26; // edi
  int v27; // ebx
  int v28; // eax
  HGDIOBJ v29; // rax
  int top; // [rsp+40h] [rbp-278h]
  unsigned __int16 SystemMetrics; // [rsp+44h] [rbp-274h]
  int left; // [rsp+48h] [rbp-270h]
  WCHAR String[264]; // [rsp+60h] [rbp-258h] BYREF

  memset_0(String, 0, 0x208u);
  itemID = a2->itemID;
  if ( (a2->itemState & 1) != 0 )
  {
    SysColor = GetSysColor(13);
    v6 = SetBkColor(a2->hDC, SysColor);
    v7 = 14;
  }
  else
  {
    v8 = GetSysColor(4);
    v6 = SetBkColor(a2->hDC, v8);
    v7 = 7;
  }
  v9 = v6;
  v10 = GetSysColor(v7);
  v11 = SetTextColor(a2->hDC, v10);
  SystemMetrics = GetSystemMetrics(5);
  v12 = GetSystemMetrics(71);
  v13 = GetSystemMetrics(6);
  v14 = a2->rcItem.bottom - v13;
  top = v13 + a2->rcItem.top;
  left = a2->rcItem.left + v12;
  v15 = left + 2 * (v14 - top);
  c = GetMenuStringW(a3, itemID, String, 260, 0);
  if ( c )
  {
    MenuFont = hFontGetMenuFont(a1);
    SelectObject(a2->hDC, MenuFont);
    ExtTextOutW(a2->hDC, v15 + 2 * SystemMetrics, a2->rcItem.top, 2u, &a2->rcItem, String, c, 0);
  }
  ColorFromIndex = GetColorFromIndex(itemID - 174);
  SolidBrush = CreateSolidBrush(ColorFromIndex);
  if ( SolidBrush )
  {
    v20 = SelectObject(a2->hDC, SolidBrush);
    Rectangle(a2->hDC, left, top, v15, v14);
    v21 = SelectObject(a2->hDC, v20);
    DeleteObject(v21);
  }
  if ( (a2->itemState & 8) != 0 )
  {
    v22 = 14;
    if ( (a2->itemState & 1) == 0 )
      v22 = 7;
    v23 = GetSysColor(v22);
    v24 = CreateSolidBrush(v23);
    if ( v24 )
    {
      v25 = SelectObject(a2->hDC, v24);
      v26 = (unsigned __int16)(LOWORD(a2->rcItem.left) + GetSystemMetrics(71) / 2);
      v27 = (unsigned __int16)(top + (v14 - top) / 2);
      v28 = GetSystemMetrics(71);
      Ellipse(
        a2->hDC,
        v26 - (unsigned __int16)(v28 / 4),
        v27 - (unsigned __int16)(v28 / 4),
        v26 + (unsigned __int16)(v28 / 4),
        (unsigned __int16)(v28 / 4) + v27);
      v29 = SelectObject(a2->hDC, v25);
      DeleteObject(v29);
    }
  }
  SetTextColor(a2->hDC, v11);
  SetBkColor(a2->hDC, v9);
}

```

## disassembly

```asm
0x1800859fc  mov     [rsp+arg_18], rbx
0x180085a01  push    rbp
0x180085a02  push    rsi
0x180085a03  push    rdi
0x180085a04  push    r12
0x180085a06  push    r13
0x180085a08  push    r14
0x180085a0a  push    r15
0x180085a0c  sub     rsp, 280h
0x180085a13  mov     rax, cs:__security_cookie
0x180085a1a  xor     rax, rsp
0x180085a1d  mov     [rsp+2B8h+var_48], rax
0x180085a25  mov     [rsp+2B8h+hMenu], r8
0x180085a2a  mov     rbp, rdx
0x180085a2d  mov     [rsp+2B8h+hWnd], rcx
0x180085a32  xor     edx, edx; Val
0x180085a34  mov     r8d, 208h; Size
0x180085a3a  lea     rcx, [rsp+2B8h+String]; void *
0x180085a3f  call    memset_0
0x180085a44  test    byte ptr [rbp+10h], 1
0x180085a48  mov     edi, [rbp+8]
0x180085a4b  jz      short loc_180085A6B
0x180085a4d  mov     ecx, 0Dh; nIndex
0x180085a52  call    cs:__imp_GetSysColor
0x180085a58  mov     rcx, [rbp+20h]; hdc
0x180085a5c  mov     edx, eax; color
0x180085a5e  call    cs:__imp_SetBkColor
0x180085a64  mov     ecx, 0Eh
0x180085a69  jmp     short loc_180085A87
0x180085a6b  mov     ecx, 4; nIndex
0x180085a70  call    cs:__imp_GetSysColor
0x180085a76  mov     rcx, [rbp+20h]; hdc
0x180085a7a  mov     edx, eax; color
0x180085a7c  call    cs:__imp_SetBkColor
0x180085a82  mov     ecx, 7; nIndex
0x180085a87  mov     r15d, eax
0x180085a8a  call    cs:__imp_GetSysColor
0x180085a90  mov     rcx, [rbp+20h]; hdc
0x180085a94  mov     edx, eax; color
0x180085a96  call    cs:__imp_SetTextColor
0x180085a9c  mov     ecx, 5; nIndex
0x180085aa1  mov     r12d, eax
0x180085aa4  call    cs:__imp_GetSystemMetrics
0x180085aaa  mov     ecx, 47h ; 'G'; nIndex
0x180085aaf  mov     [rsp+2B8h+var_274], eax
0x180085ab3  call    cs:__imp_GetSystemMetrics
0x180085ab9  mov     ecx, 6; nIndex
0x180085abe  mov     ebx, eax
0x180085ac0  call    cs:__imp_GetSystemMetrics
0x180085ac6  mov     r14d, [rbp+34h]
0x180085aca  lea     r13, [rbp+28h]
0x180085ace  mov     r8d, [r13+4]
0x180085ad2  mov     r9d, 104h; cchMax
0x180085ad8  movzx   edx, ax
0x180085adb  add     r8d, edx
0x180085ade  movzx   ecx, bx
0x180085ae1  add     ecx, [r13+0]
0x180085ae5  sub     r14d, edx
0x180085ae8  mov     eax, r14d
0x180085aeb  mov     [rsp+2B8h+top], r8d
0x180085af0  sub     eax, r8d
0x180085af3  mov     [rsp+2B8h+left], ecx
0x180085af7  lea     r8, [rsp+2B8h+String]; lpString
0x180085afc  mov     [rsp+2B8h+flags], 0; flags
0x180085b04  mov     edx, edi; uIDItem
0x180085b06  lea     esi, [rcx+rax*2]
0x180085b09  mov     rcx, [rsp+2B8h+hMenu]; hMenu
0x180085b0e  call    cs:__imp_GetMenuStringW
0x180085b14  mov     ebx, eax
0x180085b16  test    eax, eax
0x180085b18  jz      short loc_180085B69
0x180085b1a  mov     rcx, [rsp+2B8h+hWnd]; hWnd
0x180085b1f  call    ?hFontGetMenuFont@@YAPEAUHFONT__@@PEAUHWND__@@@Z; hFontGetMenuFont(HWND__ *)
0x180085b24  mov     rcx, [rbp+20h]; hdc
0x180085b28  mov     rdx, rax; h
0x180085b2b  call    cs:__imp_SelectObject
0x180085b31  movzx   ecx, word ptr [rsp+2B8h+var_274]
0x180085b36  lea     rax, [rsp+2B8h+String]
0x180085b3b  mov     r8d, [rbp+2Ch]; y
0x180085b3f  mov     r9d, 2; options
0x180085b45  mov     [rsp+2B8h+lpDx], 0; lpDx
0x180085b4e  mov     [rsp+2B8h+c], ebx; c
0x180085b52  lea     edx, [rsi+rcx*2]; x
0x180085b55  mov     [rsp+2B8h+lpString], rax; lpString
0x180085b5a  mov     rcx, [rbp+20h]; hdc
0x180085b5e  mov     qword ptr [rsp+2B8h+flags], r13; lprect
0x180085b63  call    cs:__imp_ExtTextOutW
0x180085b69  lea     ecx, [rdi-0AEh]
0x180085b6f  call    GetColorFromIndex
0x180085b74  mov     ecx, eax; color
0x180085b76  call    cs:__imp_CreateSolidBrush
0x180085b7c  test    rax, rax
0x180085b7f  jz      short loc_180085BC2
0x180085b81  mov     rcx, [rbp+20h]; hdc
0x180085b85  mov     rdx, rax; h
0x180085b88  call    cs:__imp_SelectObject
0x180085b8e  mov     r8d, [rsp+2B8h+top]; top
0x180085b93  mov     r9d, esi; right
0x180085b96  mov     edx, [rsp+2B8h+left]; left
0x180085b9a  mov     rbx, rax
0x180085b9d  mov     rcx, [rbp+20h]; hdc
0x180085ba1  mov     [rsp+2B8h+flags], r14d; bottom
0x180085ba6  call    cs:__imp_Rectangle
0x180085bac  mov     rcx, [rbp+20h]; hdc
0x180085bb0  mov     rdx, rbx; h
0x180085bb3  call    cs:__imp_SelectObject
0x180085bb9  mov     rcx, rax; ho
0x180085bbc  call    cs:__imp_DeleteObject
0x180085bc2  test    byte ptr [rbp+10h], 8
0x180085bc6  jz      loc_180085C7D
0x180085bcc  test    byte ptr [rbp+10h], 1
0x180085bd0  mov     ecx, 0Eh
0x180085bd5  jnz     short loc_180085BDC
0x180085bd7  mov     ecx, 7; nIndex
0x180085bdc  call    cs:__imp_GetSysColor
0x180085be2  mov     ecx, eax; color
0x180085be4  call    cs:__imp_CreateSolidBrush
0x180085bea  test    rax, rax
0x180085bed  jz      loc_180085C7D
0x180085bf3  mov     rcx, [rbp+20h]; hdc
0x180085bf7  mov     rdx, rax; h
0x180085bfa  call    cs:__imp_SelectObject
0x180085c00  mov     ecx, 47h ; 'G'; nIndex
0x180085c05  mov     rsi, rax
0x180085c08  call    cs:__imp_GetSystemMetrics
0x180085c0e  mov     ecx, [rsp+2B8h+top]
0x180085c12  mov     r8d, 2
0x180085c18  cdq
0x180085c19  sub     r14d, ecx
0x180085c1c  idiv    r8d
0x180085c1f  add     ax, [r13+0]
0x180085c24  movzx   edi, ax
0x180085c27  mov     eax, r14d
0x180085c2a  cdq
0x180085c2b  idiv    r8d
0x180085c2e  add     ax, cx
0x180085c31  lea     ecx, [r8+45h]; nIndex
0x180085c35  movzx   ebx, ax
0x180085c38  call    cs:__imp_GetSystemMetrics
0x180085c3e  cdq
0x180085c3f  mov     ecx, 4
0x180085c44  idiv    ecx
0x180085c46  movzx   ecx, ax
0x180085c49  lea     eax, [rcx+rbx]
0x180085c4c  sub     ebx, ecx
0x180085c4e  lea     r9d, [rdi+rcx]; right
0x180085c52  mov     [rsp+2B8h+flags], eax; bottom
0x180085c56  sub     edi, ecx
0x180085c58  mov     r8d, ebx; top
0x180085c5b  mov     rcx, [rbp+20h]; hdc
0x180085c5f  mov     edx, edi; left
0x180085c61  call    cs:__imp_Ellipse
0x180085c67  mov     rcx, [rbp+20h]; hdc
0x180085c6b  mov     rdx, rsi; h
0x180085c6e  call    cs:__imp_SelectObject
0x180085c74  mov     rcx, rax; ho
0x180085c77  call    cs:__imp_DeleteObject
0x180085c7d  mov     rcx, [rbp+20h]; hdc
0x180085c81  mov     edx, r12d; color
0x180085c84  call    cs:__imp_SetTextColor
0x180085c8a  mov     rcx, [rbp+20h]; hdc
0x180085c8e  mov     edx, r15d; color
0x180085c91  call    cs:__imp_SetBkColor
0x180085c97  mov     rcx, [rsp+2B8h+var_48]
0x180085c9f  xor     rcx, rsp; StackCookie
0x180085ca2  call    __security_check_cookie
0x180085ca7  mov     rbx, [rsp+2B8h+arg_18]
0x180085caf  add     rsp, 280h
0x180085cb6  pop     r15
0x180085cb8  pop     r14
0x180085cba  pop     r13
0x180085cbc  pop     r12
0x180085cbe  pop     rdi
0x180085cbf  pop     rsi
0x180085cc0  pop     rbp
0x180085cc1  retn
```
