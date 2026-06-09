# ListView_OnSetFont

- ea: `0x180058390`
- end: `0x18005857f`
- name: `ListView_OnSetFont`
- size: `495`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180054c90`
- `0x18005a094`
- `0x18005c0a0`

## callees

- `0x1800115f0`
- `0x180018004`
- `0x180018ab8`
- `0x180053e2c`
- `0x180058390`
- `0x18005bde8`
- `0x18008ea60`

## import_xrefs

- `GDI32!GetTextExtentPointW` at `0x180058453`
- `GDI32!GetTextExtentPointW` at `0x18005848b`
- `GDI32!GetTextExtentPointW` at `0x180058453`
- `GDI32!GetTextExtentPointW` at `0x18005848b`
- `GDI32!SelectObject` at `0x180058435`
- `GDI32!SelectObject` at `0x1800584a1`
- `GDI32!SelectObject` at `0x180058435`
- `GDI32!SelectObject` at `0x1800584a1`
- `GDI32!DeleteObject` at `0x1800583f0`
- `GDI32!DeleteObject` at `0x18005851b`
- `GDI32!DeleteObject` at `0x1800583f0`
- `GDI32!DeleteObject` at `0x18005851b`
- `GDI32!CreateFontIndirectW` at `0x180058418`
- `GDI32!CreateFontIndirectW` at `0x180058418`
- `USER32!GetDC` at `0x180058426`
- `USER32!GetDC` at `0x180058426`
- `USER32!ReleaseDC` at `0x1800584ac`
- `USER32!ReleaseDC` at `0x1800584ac`
- `USER32!SystemParametersInfoW` at `0x18005840d`
- `USER32!SystemParametersInfoW` at `0x18005840d`
- `USER32!SendMessageW` at `0x1800584e3`
- `USER32!SendMessageW` at `0x1800584fe`
- `USER32!SendMessageW` at `0x1800584e3`
- `USER32!SendMessageW` at `0x1800584fe`
- `USER32!RedrawWindow` at `0x180058551`
- `USER32!RedrawWindow` at `0x180058551`

## pseudocode

```c
int __fastcall ListView_OnSetFont(__int64 a1, HFONT a2, int a3)
{
  void *v6; // rcx
  HFONT v7; // rax
  HDC DC; // rdi
  HGDIOBJ v9; // rbx
  HWND v10; // rcx
  HWND v11; // rcx
  void *v12; // rcx
  int result; // eax
  struct tagSIZE sz; // [rsp+20h] [rbp-98h] BYREF
  LOGFONTW pvParam; // [rsp+30h] [rbp-88h] BYREF

  sz = 0;
  memset(&pvParam, 0, sizeof(pvParam));
  if ( (*(_DWORD *)(a1 + 72) & 0x100) != 0 )
  {
    v6 = *(void **)(a1 + 88);
    if ( v6 )
    {
      DeleteObject(v6);
      *(_DWORD *)(a1 + 72) &= ~0x100u;
    }
  }
  if ( !a2 )
  {
    SystemParametersInfoW(0x1Fu, 0x5Cu, &pvParam, 0);
    v7 = CreateFontIndirectW(&pvParam);
    *(_DWORD *)(a1 + 72) |= 0x100u;
    a2 = v7;
  }
  DC = GetDC(0);
  v9 = SelectObject(DC, a2);
  GetTextExtentPointW(DC, L"0", 1, &sz);
  *(_DWORD *)(a1 + 128) = sz.cy;
  *(_DWORD *)(a1 + 132) = sz.cx;
  sz = 0;
  GetTextExtentPointW(DC, L"...", 3, &sz);
  *(_DWORD *)(a1 + 136) = sz.cx;
  SelectObject(DC, v9);
  ReleaseDC(0, DC);
  *(_QWORD *)(a1 + 88) = a2;
  *(_DWORD *)(a1 + 28) = GetCodePageForFont(a2);
  ListView_InvalidateCachedLabelSizes(a1);
  v10 = *(HWND *)(a1 + 208);
  if ( v10 )
    SendMessageW(v10, 0x30u, *(_QWORD *)(a1 + 88), 0);
  v11 = *(HWND *)(a1 + 440);
  if ( v11 )
  {
    SendMessageW(v11, 0x30u, *(_QWORD *)(a1 + 88), 0);
    ListView_UpdateScrollBars(a1);
  }
  v12 = *(void **)(a1 + 536);
  if ( v12 )
  {
    DeleteObject(v12);
    *(_QWORD *)(a1 + 536) = 0;
  }
  result = CCGetHotFont(*(HANDLE *)(a1 + 88));
  *(_DWORD *)(a1 + 320) = -1;
  if ( a3 )
    return RedrawWindow(*(HWND *)a1, 0, 0, 5u);
  return result;
}

```

## disassembly

```asm
0x180058390  mov     [rsp+arg_10], rbx
0x180058395  mov     [rsp+arg_18], rbp
0x18005839a  push    rsi
0x18005839b  push    rdi
0x18005839c  push    r14
0x18005839e  sub     rsp, 0A0h
0x1800583a5  mov     rax, cs:__security_cookie
0x1800583ac  xor     rax, rsp
0x1800583af  mov     [rsp+0B8h+var_28], rax
0x1800583b7  mov     r14d, r8d
0x1800583ba  mov     qword ptr [rsp+0B8h+sz.cx], 0
0x1800583c3  mov     rbp, rdx
0x1800583c6  mov     rsi, rcx
0x1800583c9  mov     ebx, 5Ch ; '\'
0x1800583ce  lea     rcx, [rsp+0B8h+pvParam]; void *
0x1800583d3  mov     r8d, ebx; Size
0x1800583d6  xor     edx, edx; Val
0x1800583d8  call    memset
0x1800583dd  mov     edi, 100h
0x1800583e2  test    [rsi+48h], edi
0x1800583e5  jz      short loc_1800583FB
0x1800583e7  mov     rcx, [rsi+58h]; ho
0x1800583eb  test    rcx, rcx
0x1800583ee  jz      short loc_1800583FB
0x1800583f0  call    cs:__imp_DeleteObject
0x1800583f6  btr     dword ptr [rsi+48h], 8
0x1800583fb  test    rbp, rbp
0x1800583fe  jnz     short loc_180058424
0x180058400  xor     r9d, r9d; fWinIni
0x180058403  lea     r8, [rsp+0B8h+pvParam]; pvParam
0x180058408  mov     edx, ebx; uiParam
0x18005840a  lea     ecx, [rbp+1Fh]; uiAction
0x18005840d  call    cs:__imp_SystemParametersInfoW
0x180058413  lea     rcx, [rsp+0B8h+pvParam]; lplf
0x180058418  call    cs:__imp_CreateFontIndirectW
0x18005841e  or      [rsi+48h], edi
0x180058421  mov     rbp, rax
0x180058424  xor     ecx, ecx; hWnd
0x180058426  call    cs:__imp_GetDC
0x18005842c  mov     rcx, rax; hdc
0x18005842f  mov     rdx, rbp; h
0x180058432  mov     rdi, rax
0x180058435  call    cs:__imp_SelectObject
0x18005843b  lea     r9, [rsp+0B8h+sz]; lpsz
0x180058440  mov     r8d, 1; c
0x180058446  lea     rdx, a0_0; "0"
0x18005844d  mov     rcx, rdi; hdc
0x180058450  mov     rbx, rax
0x180058453  call    cs:__imp_GetTextExtentPointW
0x180058459  mov     ecx, [rsp+0B8h+sz.cy]
0x18005845d  lea     r9, [rsp+0B8h+sz]; lpsz
0x180058462  mov     [rsi+80h], ecx
0x180058468  lea     rdx, c_szEllipses; "..."
0x18005846f  mov     ecx, [rsp+0B8h+sz.cx]
0x180058473  mov     r8d, 3; c
0x180058479  mov     [rsi+84h], ecx
0x18005847f  mov     rcx, rdi; hdc
0x180058482  mov     qword ptr [rsp+0B8h+sz.cx], 0
0x18005848b  call    cs:__imp_GetTextExtentPointW
0x180058491  mov     eax, [rsp+0B8h+sz.cx]
0x180058495  mov     rdx, rbx; h
0x180058498  mov     rcx, rdi; hdc
0x18005849b  mov     [rsi+88h], eax
0x1800584a1  call    cs:__imp_SelectObject
0x1800584a7  mov     rdx, rdi; hDC
0x1800584aa  xor     ecx, ecx; hWnd
0x1800584ac  call    cs:__imp_ReleaseDC
0x1800584b2  mov     rcx, rbp; h
0x1800584b5  mov     [rsi+58h], rbp
0x1800584b9  call    GetCodePageForFont
0x1800584be  mov     rcx, rsi
0x1800584c1  mov     [rsi+1Ch], eax
0x1800584c4  call    ListView_InvalidateCachedLabelSizes
0x1800584c9  mov     rcx, [rsi+0D0h]; hWnd
0x1800584d0  mov     ebx, 30h ; '0'
0x1800584d5  test    rcx, rcx
0x1800584d8  jz      short loc_1800584E9
0x1800584da  mov     r8, [rsi+58h]; wParam
0x1800584de  xor     r9d, r9d; lParam
0x1800584e1  mov     edx, ebx; Msg
0x1800584e3  call    cs:__imp_SendMessageW
0x1800584e9  mov     rcx, [rsi+1B8h]; hWnd
0x1800584f0  test    rcx, rcx
0x1800584f3  jz      short loc_18005850C
0x1800584f5  mov     r8, [rsi+58h]; wParam
0x1800584f9  xor     r9d, r9d; lParam
0x1800584fc  mov     edx, ebx; Msg
0x1800584fe  call    cs:__imp_SendMessageW
0x180058504  mov     rcx, rsi
0x180058507  call    ListView_UpdateScrollBars
0x18005850c  lea     rbx, [rsi+218h]
0x180058513  mov     rcx, [rbx]; ho
0x180058516  test    rcx, rcx
0x180058519  jz      short loc_180058528
0x18005851b  call    cs:__imp_DeleteObject
0x180058521  mov     qword ptr [rbx], 0
0x180058528  mov     rcx, [rsi+58h]; h
0x18005852c  mov     rdx, rbx
0x18005852f  call    CCGetHotFont
0x180058534  mov     dword ptr [rsi+140h], 0FFFFFFFFh
0x18005853e  test    r14d, r14d
0x180058541  jz      short loc_180058557
0x180058543  mov     rcx, [rsi]; hWnd
0x180058546  mov     r9d, 5; flags
0x18005854c  xor     r8d, r8d; hrgnUpdate
0x18005854f  xor     edx, edx; lprcUpdate
0x180058551  call    cs:__imp_RedrawWindow
0x180058557  mov     rcx, [rsp+0B8h+var_28]
0x18005855f  xor     rcx, rsp; StackCookie
0x180058562  call    __security_check_cookie
0x180058567  lea     r11, [rsp+0B8h+var_18]
0x18005856f  mov     rbx, [r11+30h]
0x180058573  mov     rbp, [r11+38h]
0x180058577  mov     rsp, r11
0x18005857a  pop     r14
0x18005857c  pop     rdi
0x18005857d  pop     rsi
0x18005857e  retn
```
