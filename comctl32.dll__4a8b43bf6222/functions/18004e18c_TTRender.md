# TTRender

- ea: `0x18004e18c`
- end: `0x18004e677`
- name: `TTRender`
- size: `1259`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18004f220`

## callees

- `0x1800115f0`
- `0x180037080`
- `0x18004d014`
- `0x18004e18c`
- `0x18004e680`
- `0x18008ea60`

## import_xrefs

- `GDI32!SelectObject` at `0x18004e22c`
- `GDI32!SelectObject` at `0x18004e22c`
- `GDI32!DeleteObject` at `0x18004e3e2`
- `GDI32!DeleteObject` at `0x18004e522`
- `GDI32!DeleteObject` at `0x18004e52e`
- `GDI32!DeleteObject` at `0x18004e5e5`
- `GDI32!DeleteObject` at `0x18004e5ee`
- `GDI32!DeleteObject` at `0x18004e3e2`
- `GDI32!DeleteObject` at `0x18004e522`
- `GDI32!DeleteObject` at `0x18004e52e`
- `GDI32!DeleteObject` at `0x18004e5e5`
- `GDI32!DeleteObject` at `0x18004e5ee`
- `GDI32!CreateRectRgn` at `0x18004e4e3`
- `GDI32!CreateRectRgn` at `0x18004e59f`
- `GDI32!CreateRectRgn` at `0x18004e4e3`
- `GDI32!CreateRectRgn` at `0x18004e59f`
- `GDI32!ExtTextOutW` at `0x18004e584`
- `GDI32!ExtTextOutW` at `0x18004e584`
- `GDI32!SetBkMode` at `0x18004e3ed`
- `GDI32!SetBkMode` at `0x18004e3ed`
- `GDI32!SetBkColor` at `0x18004e3bb`
- `GDI32!SetBkColor` at `0x18004e3bb`
- `GDI32!SetTextColor` at `0x18004e248`
- `GDI32!SetTextColor` at `0x18004e248`
- `GDI32!GetNearestColor` at `0x18004e399`
- `GDI32!GetNearestColor` at `0x18004e399`
- `GDI32!CreateSolidBrush` at `0x18004e3c6`
- `GDI32!CreateSolidBrush` at `0x18004e507`
- `GDI32!CreateSolidBrush` at `0x18004e5c3`
- `GDI32!CreateSolidBrush` at `0x18004e3c6`
- `GDI32!CreateSolidBrush` at `0x18004e507`
- `GDI32!CreateSolidBrush` at `0x18004e5c3`
- `GDI32!FillRgn` at `0x18004e519`
- `GDI32!FillRgn` at `0x18004e519`
- `GDI32!FrameRgn` at `0x18004e5dc`
- `GDI32!FrameRgn` at `0x18004e5dc`
- `KERNEL32!lstrlenW` at `0x18004e444`
- `KERNEL32!lstrlenW` at `0x18004e558`
- `KERNEL32!lstrlenW` at `0x18004e444`
- `KERNEL32!lstrlenW` at `0x18004e558`
- `USER32!GetClientRect` at `0x18004e239`
- `USER32!GetClientRect` at `0x18004e239`
- `USER32!DrawTextW` at `0x18004e45e`
- `USER32!DrawTextW` at `0x18004e45e`
- `USER32!FillRect` at `0x18004e3d9`
- `USER32!FillRect` at `0x18004e3d9`
- `USER32!InflateRect` at `0x18004e2ce`
- `USER32!InflateRect` at `0x18004e41a`
- `USER32!InflateRect` at `0x18004e4af`
- `USER32!InflateRect` at `0x18004e66c`
- `USER32!InflateRect` at `0x18004e2ce`
- `USER32!InflateRect` at `0x18004e41a`
- `USER32!InflateRect` at `0x18004e4af`
- `USER32!InflateRect` at `0x18004e66c`
- `USER32!OffsetRect` at `0x18004e2ea`
- `USER32!OffsetRect` at `0x18004e4ce`
- `USER32!OffsetRect` at `0x18004e2ea`
- `USER32!OffsetRect` at `0x18004e4ce`
- `USER32!GetWindowRgn` at `0x18004e4f7`
- `USER32!GetWindowRgn` at `0x18004e5b3`
- `USER32!GetWindowRgn` at `0x18004e4f7`
- `USER32!GetWindowRgn` at `0x18004e5b3`

## pseudocode

```c
__int64 __fastcall TTRender(__int64 a1, HDC a2)
{
  int v2; // r13d
  __int64 v4; // rdx
  unsigned int v6; // esi
  __int64 ToolText; // rax
  __int64 v8; // rbx
  const WCHAR *lpString; // r14
  int v10; // r12d
  int v11; // ecx
  int v12; // eax
  bool v13; // zf
  int v14; // ecx
  int v15; // edx
  __int64 v16; // rcx
  int v17; // eax
  int v18; // ebx
  int v19; // eax
  COLORREF NearestColor; // eax
  COLORREF v21; // ecx
  UINT v22; // r12d
  HBRUSH SolidBrush; // rbx
  int v24; // eax
  int v25; // r13d
  int v26; // ebx
  int v27; // r8d
  HRGN RectRgn; // rax
  HRGN v29; // r12
  HBRUSH v30; // rbx
  UINT c; // eax
  HRGN v32; // rax
  HRGN v33; // r14
  HBRUSH v34; // rbx
  __int64 v35; // rcx
  UINT options; // [rsp+40h] [rbp-79h]
  int v38; // [rsp+44h] [rbp-75h]
  int v39; // [rsp+48h] [rbp-71h]
  char v40; // [rsp+50h] [rbp-69h]
  _QWORD format[12]; // [rsp+60h] [rbp-59h] BYREF
  struct tagRECT Rect; // [rsp+C0h] [rbp+7h] BYREF

  v2 = 0;
  v4 = *(_QWORD *)(a1 + 80);
  v6 = 0;
  Rect = 0;
  if ( v4 )
  {
    ToolText = GetToolText();
    v8 = *(_QWORD *)(a1 + 80);
    lpString = (const WCHAR *)(ToolText & -(__int64)(v8 != 0));
    if ( lpString )
    {
      if ( *lpString )
      {
        memset(format, 0, 0x58u);
        if ( (*(_BYTE *)(v8 + 4) & 4) != 0 || (v10 = 0, (*(_DWORD *)(a1 + 32) & 0x2000) != 0) )
          v10 = 128;
        SelectObject(a2, *(HGDIOBJ *)(a1 + 96));
        GetClientRect(*(HWND *)a1, &Rect);
        SetTextColor(a2, *(_DWORD *)(a1 + 200));
        v6 = 1;
        format[0] = *(_QWORD *)a1;
        format[1] = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 16LL);
        v11 = *(_DWORD *)(a1 + 208);
        LODWORD(format[2]) = -12;
        format[4] = a2;
        LODWORD(format[6]) = Rect.right - *(_DWORD *)(a1 + 216) - 2 * g_cxBorder;
        HIDWORD(format[5]) = Rect.top + g_cyBorder + *(_DWORD *)(a1 + 212);
        v12 = Rect.bottom - *(_DWORD *)(a1 + 220) - g_cyBorder;
        v13 = (*(_BYTE *)(a1 + 16) & 0x40) == 0;
        LODWORD(format[3]) = 1;
        LODWORD(format[5]) = Rect.left + 2 * g_cxBorder + v11;
        HIDWORD(format[6]) = v12;
        if ( !v13 )
        {
          InflateRect((LPRECT)&format[5], -10, -8);
          if ( (*(_BYTE *)(a1 + 192) & 4) == 0 )
            OffsetRect((LPRECT)&format[5], 0, *(_DWORD *)(a1 + 224));
        }
        v14 = 32;
        if ( *(_DWORD *)(a1 + 204) != -1 )
          v14 = 592;
        v15 = v14 | 0x800;
        if ( (*(_BYTE *)(a1 + 16) & 2) == 0 )
          v15 = v14;
        v16 = *(_QWORD *)(a1 + 80);
        v17 = *(_DWORD *)(v16 + 4);
        if ( (v17 & 4) != 0 || (*(_DWORD *)(a1 + 32) & 0x2000) != 0 )
          v15 |= 0x20000u;
        v18 = v15 | 2;
        if ( (v17 & 0x800) == 0 )
          v18 = v15;
        LODWORD(format[10]) = v18;
        v38 = v18;
        v19 = SendNotifyEx(*(_QWORD *)(v16 + 8), -1, 0, format, (*(_DWORD *)(v16 + 4) >> 6) & 1);
        v40 = v19;
        if ( *(__int64 *)(a1 + 40) < 5 || v19 != 4 )
        {
          if ( LODWORD(format[10]) != v18 || (v18 & 0x20022) != 0x20 || *(_DWORD *)(a1 + 160) )
            v2 = 1;
          NearestColor = GetNearestColor(a2, *(_DWORD *)(a1 + 196));
          v21 = *(_DWORD *)(a1 + 196);
          if ( v21 != NearestColor || v2 )
          {
            SolidBrush = CreateSolidBrush(v21);
            FillRect(a2, &Rect, SolidBrush);
            DeleteObject(SolidBrush);
            SetBkMode(a2, 1);
            if ( v2 )
            {
              ++HIDWORD(format[6]);
              ++LODWORD(format[6]);
              if ( *(_DWORD *)(a1 + 160) && (*(_BYTE *)(a1 + 16) & 0x40) == 0 )
                InflateRect((LPRECT)&format[5], -10, -8);
              if ( !(unsigned int)TTRenderTitledTip(a1, a2, 0, &format[5], v38) )
              {
                v24 = lstrlenW(lpString);
                DrawTextW(a2, lpString, v24, (LPRECT)&format[5], format[10]);
              }
              goto LABEL_45;
            }
            v22 = v10 | 4;
            options = v22;
          }
          else
          {
            v22 = v10 | 2;
            options = v22;
            SetBkColor(a2, v21);
          }
          v25 = g_cyBorder + *(_DWORD *)(a1 + 212);
          v26 = *(_DWORD *)(a1 + 208) + 2 * g_cxBorder;
          if ( (*(_BYTE *)(a1 + 16) & 0x40) != 0 )
          {
            v26 += 10;
            v25 += 8;
            v39 = v26;
            InflateRect(&Rect, -10, -8);
            if ( (*(_BYTE *)(a1 + 192) & 4) == 0 )
            {
              v27 = *(_DWORD *)(a1 + 224);
              v25 += v27;
              OffsetRect(&Rect, 0, v27);
            }
            RectRgn = CreateRectRgn(1, 1, 2, 2);
            v29 = RectRgn;
            if ( RectRgn )
            {
              if ( GetWindowRgn(*(HWND *)a1, RectRgn) )
              {
                v30 = CreateSolidBrush(*(_DWORD *)(a1 + 196));
                FillRgn(a2, v29, v30);
                DeleteObject(v30);
                v26 = v39;
              }
              DeleteObject(v29);
            }
            v22 = options;
          }
          else if ( *(_DWORD *)(a1 + 160) )
          {
            InflateRect(&Rect, -10, -8);
          }
          if ( !(unsigned int)TTRenderTitledTip(a1, a2, 0, &Rect, v38) )
          {
            c = lstrlenW(lpString);
            ExtTextOutW(a2, v26, v25, v22, &Rect, lpString, c, 0);
          }
LABEL_45:
          if ( (*(_BYTE *)(a1 + 16) & 0x40) != 0 )
          {
            v32 = CreateRectRgn(1, 1, 2, 2);
            v33 = v32;
            if ( v32 )
            {
              if ( GetWindowRgn(*(HWND *)a1, v32) )
              {
                v34 = CreateSolidBrush(*(_DWORD *)(a1 + 200));
                FrameRgn(a2, v33, v34, 1, 1);
                DeleteObject(v34);
              }
              DeleteObject(v33);
            }
          }
          if ( (v40 & 0x14) == 0x10 )
          {
            v35 = *(_QWORD *)(a1 + 80);
            ++LODWORD(format[3]);
            SendNotifyEx(*(_QWORD *)(v35 + 8), -1, 0, format, (*(_DWORD *)(v35 + 4) >> 6) & 1);
          }
        }
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18004e18c  mov     [rsp-8+arg_10], rbx
0x18004e191  push    rbp
0x18004e192  push    rsi
0x18004e193  push    rdi
0x18004e194  push    r12
0x18004e196  push    r13
0x18004e198  push    r14
0x18004e19a  push    r15
0x18004e19c  lea     rbp, [rsp-27h]
0x18004e1a1  sub     rsp, 0E0h
0x18004e1a8  mov     rax, cs:__security_cookie
0x18004e1af  xor     rax, rsp
0x18004e1b2  mov     [rbp+57h+var_40], rax
0x18004e1b6  xor     r13d, r13d
0x18004e1b9  mov     r15, rdx
0x18004e1bc  mov     rdx, [rcx+50h]
0x18004e1c0  xorps   xmm0, xmm0
0x18004e1c3  mov     rdi, rcx
0x18004e1c6  mov     esi, r13d
0x18004e1c9  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18004e1cd  test    rdx, rdx
0x18004e1d0  jz      loc_18004E629
0x18004e1d6  call    GetToolText
0x18004e1db  mov     rbx, [rdi+50h]
0x18004e1df  mov     rcx, rax
0x18004e1e2  mov     rax, rbx
0x18004e1e5  neg     rax
0x18004e1e8  sbb     r14, r14
0x18004e1eb  and     r14, rcx
0x18004e1ee  jz      loc_18004E629
0x18004e1f4  cmp     [r14], r13w
0x18004e1f8  jz      loc_18004E629
0x18004e1fe  xor     edx, edx; Val
0x18004e200  lea     r8d, [r13+58h]; Size
0x18004e204  lea     rcx, [rbp+57h+var_B0]; void *
0x18004e208  call    memset
0x18004e20d  test    byte ptr [rbx+4], 4
0x18004e211  jnz     short loc_18004E21F
0x18004e213  test    dword ptr [rdi+20h], 2000h
0x18004e21a  mov     r12d, r13d
0x18004e21d  jz      short loc_18004E225
0x18004e21f  mov     r12d, 80h
0x18004e225  mov     rdx, [rdi+60h]; h
0x18004e229  mov     rcx, r15; hdc
0x18004e22c  call    cs:__imp_SelectObject
0x18004e232  mov     rcx, [rdi]; hWnd
0x18004e235  lea     rdx, [rbp+57h+Rect]; lpRect
0x18004e239  call    cs:__imp_GetClientRect
0x18004e23f  mov     edx, [rdi+0C8h]; color
0x18004e245  mov     rcx, r15; hdc
0x18004e248  call    cs:__imp_SetTextColor
0x18004e24e  mov     rax, [rdi]
0x18004e251  mov     esi, 1
0x18004e256  mov     [rbp+57h+var_B0], rax
0x18004e25a  mov     rax, [rdi+50h]
0x18004e25e  mov     rcx, [rax+10h]
0x18004e262  mov     eax, cs:g_cxBorder
0x18004e268  mov     [rbp+57h+var_A8], rcx
0x18004e26c  mov     ecx, [rdi+0D0h]
0x18004e272  mov     [rbp+57h+var_A0], 0FFFFFFF4h
0x18004e279  lea     edx, [rax+rax]
0x18004e27c  mov     [rbp+57h+var_90], r15
0x18004e280  mov     eax, [rbp+57h+Rect.right]
0x18004e283  add     ecx, edx
0x18004e285  sub     eax, [rdi+0D8h]
0x18004e28b  add     ecx, [rbp+57h+Rect.left]
0x18004e28e  sub     eax, edx
0x18004e290  mov     [rbp+57h+rc.right], eax
0x18004e293  mov     eax, [rdi+0D4h]
0x18004e299  add     eax, cs:g_cyBorder
0x18004e29f  add     eax, [rbp+57h+Rect.top]
0x18004e2a2  mov     [rbp+57h+rc.top], eax
0x18004e2a5  mov     eax, [rbp+57h+Rect.bottom]
0x18004e2a8  sub     eax, [rdi+0DCh]
0x18004e2ae  sub     eax, cs:g_cyBorder
0x18004e2b4  test    byte ptr [rdi+10h], 40h
0x18004e2b8  mov     [rbp+57h+var_98], esi
0x18004e2bb  mov     [rbp+57h+rc.left], ecx
0x18004e2be  mov     [rbp+57h+rc.bottom], eax
0x18004e2c1  jz      short loc_18004E2F0
0x18004e2c3  lea     edx, [rsi-0Bh]; dx
0x18004e2c6  lea     r8d, [rsi-9]; dy
0x18004e2ca  lea     rcx, [rbp+57h+rc]; lprc
0x18004e2ce  call    cs:__imp_InflateRect
0x18004e2d4  test    byte ptr [rdi+0C0h], 4
0x18004e2db  jnz     short loc_18004E2F0
0x18004e2dd  mov     r8d, [rdi+0E0h]; dy
0x18004e2e4  lea     rcx, [rbp+57h+rc]; lprc
0x18004e2e8  xor     edx, edx; dx
0x18004e2ea  call    cs:__imp_OffsetRect
0x18004e2f0  cmp     dword ptr [rdi+0CCh], 0FFFFFFFFh
0x18004e2f7  mov     ecx, 20h ; ' '
0x18004e2fc  mov     eax, 250h
0x18004e301  mov     r8d, 800h
0x18004e307  cmovnz  ecx, eax
0x18004e30a  mov     edx, ecx
0x18004e30c  or      edx, r8d
0x18004e30f  test    byte ptr [rdi+10h], 2
0x18004e313  cmovz   edx, ecx
0x18004e316  mov     rcx, [rdi+50h]
0x18004e31a  mov     eax, [rcx+4]
0x18004e31d  test    al, 4
0x18004e31f  jnz     short loc_18004E32A
0x18004e321  test    dword ptr [rdi+20h], 2000h
0x18004e328  jz      short loc_18004E32E
0x18004e32a  bts     edx, 11h
0x18004e32e  mov     ebx, edx
0x18004e330  lea     r9, [rbp+57h+var_B0]
0x18004e334  or      ebx, 2
0x18004e337  test    r8d, eax
0x18004e33a  cmovz   ebx, edx
0x18004e33d  xor     r8d, r8d
0x18004e340  mov     [rbp+57h+var_60], ebx
0x18004e343  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004e347  mov     eax, [rcx+4]
0x18004e34a  mov     rcx, [rcx+8]
0x18004e34e  shr     eax, 6
0x18004e351  and     eax, esi
0x18004e353  mov     [rbp+57h+var_CC], ebx
0x18004e356  mov     [rsp+110h+format], eax
0x18004e35a  call    SendNotifyEx
0x18004e35f  cmp     qword ptr [rdi+28h], 5
0x18004e364  mov     qword ptr [rbp+57h+var_C0], rax
0x18004e368  jl      short loc_18004E373
0x18004e36a  cmp     eax, 4
0x18004e36d  jz      loc_18004E629
0x18004e373  cmp     [rbp+57h+var_60], ebx
0x18004e376  jnz     short loc_18004E38D
0x18004e378  mov     eax, ebx
0x18004e37a  and     eax, 20022h
0x18004e37f  cmp     eax, 20h ; ' '
0x18004e382  jnz     short loc_18004E38D
0x18004e384  cmp     [rdi+0A0h], r13d
0x18004e38b  jz      short loc_18004E390
0x18004e38d  mov     r13d, esi
0x18004e390  mov     edx, [rdi+0C4h]; color
0x18004e396  mov     rcx, r15; hdc
0x18004e399  call    cs:__imp_GetNearestColor
0x18004e39f  mov     ecx, [rdi+0C4h]; color
0x18004e3a5  cmp     ecx, eax
0x18004e3a7  jnz     short loc_18004E3C6
0x18004e3a9  test    r13d, r13d
0x18004e3ac  jnz     short loc_18004E3C6
0x18004e3ae  or      r12d, 2
0x18004e3b2  mov     edx, ecx; color
0x18004e3b4  mov     rcx, r15; hdc
0x18004e3b7  mov     [rbp+57h+options], r12d
0x18004e3bb  call    cs:__imp_SetBkColor
0x18004e3c1  jmp     loc_18004E471
0x18004e3c6  call    cs:__imp_CreateSolidBrush
0x18004e3cc  lea     rdx, [rbp+57h+Rect]; lprc
0x18004e3d0  mov     rcx, r15; hDC
0x18004e3d3  mov     r8, rax; hbr
0x18004e3d6  mov     rbx, rax
0x18004e3d9  call    cs:__imp_FillRect
0x18004e3df  mov     rcx, rbx; ho
0x18004e3e2  call    cs:__imp_DeleteObject
0x18004e3e8  mov     edx, esi; mode
0x18004e3ea  mov     rcx, r15; hdc
0x18004e3ed  call    cs:__imp_SetBkMode
0x18004e3f3  test    r13d, r13d
0x18004e3f6  jz      short loc_18004E469
0x18004e3f8  add     [rbp+57h+rc.bottom], esi
0x18004e3fb  add     [rbp+57h+rc.right], esi
0x18004e3fe  cmp     dword ptr [rdi+0A0h], 0
0x18004e405  jbe     short loc_18004E420
0x18004e407  test    byte ptr [rdi+10h], 40h
0x18004e40b  jnz     short loc_18004E420
0x18004e40d  mov     edx, 0FFFFFFF6h; dx
0x18004e412  lea     rcx, [rbp+57h+rc]; lprc
0x18004e416  lea     r8d, [rdx+2]; dy
0x18004e41a  call    cs:__imp_InflateRect
0x18004e420  mov     eax, [rbp+57h+var_CC]
0x18004e423  lea     r9, [rbp+57h+rc]
0x18004e427  xor     r8d, r8d
0x18004e42a  mov     [rsp+110h+format], eax
0x18004e42e  mov     rdx, r15
0x18004e431  mov     rcx, rdi
0x18004e434  call    TTRenderTitledTip
0x18004e439  test    eax, eax
0x18004e43b  jnz     loc_18004E58A
0x18004e441  mov     rcx, r14; lpString
0x18004e444  call    cs:__imp_lstrlenW
0x18004e44a  lea     r9, [rbp+57h+rc]; lprc
0x18004e44e  mov     rdx, r14; lpchText
0x18004e451  mov     r8d, eax; cchText
0x18004e454  mov     rcx, r15; hdc
0x18004e457  mov     eax, [rbp+57h+var_60]
0x18004e45a  mov     [rsp+110h+format], eax; format
0x18004e45e  call    cs:__imp_DrawTextW
0x18004e464  jmp     loc_18004E58A
0x18004e469  or      r12d, 4
0x18004e46d  mov     [rbp+57h+options], r12d
0x18004e471  mov     ecx, [rdi+0D0h]
0x18004e477  mov     eax, cs:g_cxBorder
0x18004e47d  mov     r13d, [rdi+0D4h]
0x18004e484  add     r13d, cs:g_cyBorder
0x18004e48b  test    byte ptr [rdi+10h], 40h
0x18004e48f  lea     ebx, [rcx+rax*2]
0x18004e492  jz      loc_18004E652
0x18004e498  mov     edx, 0FFFFFFF6h; dx
0x18004e49d  lea     rcx, [rbp+57h+Rect]; lprc
0x18004e4a1  add     ebx, 0Ah
0x18004e4a4  add     r13d, 8
0x18004e4a8  mov     [rbp+57h+var_C8], ebx
0x18004e4ab  lea     r8d, [rdx+2]; dy
0x18004e4af  call    cs:__imp_InflateRect
0x18004e4b5  test    byte ptr [rdi+0C0h], 4
0x18004e4bc  jnz     short loc_18004E4D4
0x18004e4be  mov     r8d, [rdi+0E0h]; dy
0x18004e4c5  lea     rcx, [rbp+57h+Rect]; lprc
0x18004e4c9  add     r13d, r8d
0x18004e4cc  xor     edx, edx; dx
0x18004e4ce  call    cs:__imp_OffsetRect
0x18004e4d4  mov     eax, 2
0x18004e4d9  mov     edx, esi; y1
0x18004e4db  mov     r9d, eax; y2
0x18004e4de  mov     r8d, eax; x2
0x18004e4e1  mov     ecx, esi; x1
0x18004e4e3  call    cs:__imp_CreateRectRgn
0x18004e4e9  mov     r12, rax
0x18004e4ec  test    rax, rax
0x18004e4ef  jz      short loc_18004E534
0x18004e4f1  mov     rcx, [rdi]; hWnd
0x18004e4f4  mov     rdx, rax; hRgn
0x18004e4f7  call    cs:__imp_GetWindowRgn
0x18004e4fd  test    eax, eax
0x18004e4ff  jz      short loc_18004E52B
0x18004e501  mov     ecx, [rdi+0C4h]; color
0x18004e507  call    cs:__imp_CreateSolidBrush
0x18004e50d  mov     rdx, r12; hrgn
0x18004e510  mov     rcx, r15; hdc
0x18004e513  mov     r8, rax; hbr
0x18004e516  mov     rbx, rax
0x18004e519  call    cs:__imp_FillRgn
0x18004e51f  mov     rcx, rbx; ho
0x18004e522  call    cs:__imp_DeleteObject
0x18004e528  mov     ebx, [rbp+57h+var_C8]
0x18004e52b  mov     rcx, r12; ho
0x18004e52e  call    cs:__imp_DeleteObject
0x18004e534  mov     r12d, [rbp+57h+options]
0x18004e538  mov     eax, [rbp+57h+var_CC]
0x18004e53b  lea     r9, [rbp+57h+Rect]
0x18004e53f  xor     r8d, r8d
0x18004e542  mov     [rsp+110h+format], eax
0x18004e546  mov     rdx, r15
0x18004e549  mov     rcx, rdi
0x18004e54c  call    TTRenderTitledTip
0x18004e551  test    eax, eax
0x18004e553  jnz     short loc_18004E58A
0x18004e555  mov     rcx, r14; lpString
0x18004e558  call    cs:__imp_lstrlenW
0x18004e55e  mov     [rsp+110h+lpDx], 0; lpDx
0x18004e567  mov     r9d, r12d; options
0x18004e56a  mov     [rsp+110h+c], eax; c
0x18004e56e  mov     r8d, r13d; y
0x18004e571  lea     rax, [rbp+57h+Rect]
0x18004e575  mov     [rsp+110h+lpString], r14; lpString
0x18004e57a  mov     edx, ebx; x
0x18004e57c  mov     qword ptr [rsp+110h+format], rax; lprect
0x18004e581  mov     rcx, r15; hdc
0x18004e584  call    cs:__imp_ExtTextOutW
0x18004e58a  test    byte ptr [rdi+10h], 40h
0x18004e58e  jz      short loc_18004E5F4
0x18004e590  mov     eax, 2
0x18004e595  mov     edx, esi; y1
0x18004e597  mov     r9d, eax; y2
0x18004e59a  mov     r8d, eax; x2
0x18004e59d  mov     ecx, esi; x1
0x18004e59f  call    cs:__imp_CreateRectRgn
0x18004e5a5  mov     r14, rax
0x18004e5a8  test    rax, rax
0x18004e5ab  jz      short loc_18004E5F4
0x18004e5ad  mov     rcx, [rdi]; hWnd
0x18004e5b0  mov     rdx, rax; hRgn
0x18004e5b3  call    cs:__imp_GetWindowRgn
0x18004e5b9  test    eax, eax
0x18004e5bb  jz      short loc_18004E5EB
0x18004e5bd  mov     ecx, [rdi+0C8h]; color
0x18004e5c3  call    cs:__imp_CreateSolidBrush
0x18004e5c9  mov     r9d, esi; w
0x18004e5cc  mov     [rsp+110h+format], esi; h
0x18004e5d0  mov     r8, rax; hbr
0x18004e5d3  mov     rdx, r14; hrgn
0x18004e5d6  mov     rcx, r15; hdc
0x18004e5d9  mov     rbx, rax
0x18004e5dc  call    cs:__imp_FrameRgn
0x18004e5e2  mov     rcx, rbx; ho
0x18004e5e5  call    cs:__imp_DeleteObject
0x18004e5eb  mov     rcx, r14; ho
0x18004e5ee  call    cs:__imp_DeleteObject
0x18004e5f4  mov     rax, qword ptr [rbp+57h+var_C0]
0x18004e5f8  and     al, 14h
0x18004e5fa  cmp     al, 10h
0x18004e5fc  jnz     short loc_18004E629
0x18004e5fe  mov     rcx, [rdi+50h]
0x18004e602  lea     r9, [rbp+57h+var_B0]
0x18004e606  add     [rbp+57h+var_98], esi
0x18004e609  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004e60d  mov     r8d, [rcx+4]
  ... truncated ...
```
