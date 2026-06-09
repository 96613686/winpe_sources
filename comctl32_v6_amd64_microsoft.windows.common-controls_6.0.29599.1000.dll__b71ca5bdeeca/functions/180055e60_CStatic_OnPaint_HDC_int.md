# CStatic::OnPaint(HDC__ *,int)

- ea: `0x180055e60`
- end: `0x1800565eb`
- name: `?OnPaint@CStatic@@AEAAXPEAUHDC__@@H@Z`
- size: `1931`
- prototype: `void __fastcall(LPARAM lData, HDC hdc, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180055550`
- `0x180055c80`

## callees

- `0x180055e60`
- `0x18006a640`
- `0x1800ad3b0`
- `0x1800d3e70`
- `0x180114520`
- `0x180114ebc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056515`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800565a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056515`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800565a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800565b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800565b1`
- `GDI32!IntersectClipRect` at `0x180055eef`
- `GDI32!IntersectClipRect` at `0x180055eef`
- `GDI32!SetTextAlign` at `0x180056356`
- `GDI32!SetTextAlign` at `0x1800565e0`
- `GDI32!SetTextAlign` at `0x180056356`
- `GDI32!SetTextAlign` at `0x1800565e0`
- `GDI32!SetBkColor` at `0x1800563a0`
- `GDI32!SetBkColor` at `0x1800563a0`
- `GDI32!GetObjectW` at `0x1800561f8`
- `GDI32!GetObjectW` at `0x1800561f8`
- `GDI32!SetBkMode` at `0x180055f5e`
- `GDI32!SetBkMode` at `0x180055f5e`
- `GDI32!SetTextColor` at `0x180056367`
- `GDI32!SetTextColor` at `0x180056367`
- `GDI32!GetTextAlign` at `0x180056344`
- `GDI32!GetTextAlign` at `0x180056344`
- `GDI32!SelectObject` at `0x180055f1a`
- `GDI32!SelectObject` at `0x180056110`
- `GDI32!SelectObject` at `0x18005622d`
- `GDI32!SelectObject` at `0x1800562af`
- `GDI32!SelectObject` at `0x180055f1a`
- `GDI32!SelectObject` at `0x180056110`
- `GDI32!SelectObject` at `0x18005622d`
- `GDI32!SelectObject` at `0x1800562af`
- `GDI32!DeleteDC` at `0x18005629e`
- `GDI32!DeleteDC` at `0x18005629e`
- `GDI32!CreateCompatibleDC` at `0x180056214`
- `GDI32!CreateCompatibleDC` at `0x180056214`
- `GDI32!TextOutW` at `0x18005659d`
- `GDI32!TextOutW` at `0x18005659d`
- `GDI32!GdiAlphaBlend` at `0x1800564ec`
- `GDI32!GdiAlphaBlend` at `0x1800564ec`
- `GDI32!SetLayoutWidth` at `0x180056336`
- `GDI32!SetLayoutWidth` at `0x1800563d1`
- `GDI32!SetLayoutWidth` at `0x180056336`
- `GDI32!SetLayoutWidth` at `0x1800563d1`
- `GDI32!GdiTransparentBlt` at `0x180056290`
- `GDI32!GdiTransparentBlt` at `0x180056290`
- `GDI32!PlayEnhMetaFile` at `0x18005646c`
- `GDI32!PlayEnhMetaFile` at `0x18005646c`
- `USER32!FillRect` at `0x180056084`
- `USER32!FillRect` at `0x180056439`
- `USER32!FillRect` at `0x180056084`
- `USER32!FillRect` at `0x180056439`
- `USER32!GetSysColorBrush` at `0x1800560c1`
- `USER32!GetSysColorBrush` at `0x1800563be`
- `USER32!GetSysColorBrush` at `0x1800560c1`
- `USER32!GetSysColorBrush` at `0x1800563be`
- `USER32!IsWindowVisible` at `0x180056005`
- `USER32!IsWindowVisible` at `0x180056005`
- `USER32!IsWindowEnabled` at `0x1800560a2`
- `USER32!IsWindowEnabled` at `0x1800560a2`
- `USER32!GetParent` at `0x180055f6a`
- `USER32!GetParent` at `0x180055f8a`
- `USER32!GetParent` at `0x180055f6a`
- `USER32!GetParent` at `0x180055f8a`
- `USER32!GetWindowTextW` at `0x18005654a`
- `USER32!GetWindowTextW` at `0x18005654a`
- `USER32!SendMessageW` at `0x180055f7e`
- `USER32!SendMessageW` at `0x180056064`
- `USER32!SendMessageW` at `0x180055f7e`
- `USER32!SendMessageW` at `0x180056064`
- `USER32!GetDlgCtrlID` at `0x180055ff2`
- `USER32!GetDlgCtrlID` at `0x180055ff2`
- `USER32!GetSysColor` at `0x180056252`
- `USER32!GetSysColor` at `0x180056252`
- `USER32!GetClientRect` at `0x180055ed0`
- `USER32!GetClientRect` at `0x180055ed0`
- `USER32!DrawIconEx` at `0x18005631f`
- `USER32!DrawIconEx` at `0x18005631f`
- `USER32!DrawEdge` at `0x180056176`
- `USER32!DrawEdge` at `0x180056176`
- `USER32!GetWindowTextLengthW` at `0x180056092`
- `USER32!GetWindowTextLengthW` at `0x18005650d`
- `USER32!GetWindowTextLengthW` at `0x180056092`
- `USER32!GetWindowTextLengthW` at `0x18005650d`
- `USER32!DrawStateW` at `0x1800560fb`
- `USER32!DrawStateW` at `0x1800560fb`
- `USER32!DrawFrame` at `0x1800565cf`
- `USER32!DrawFrame` at `0x1800565cf`
- `UxTheme!GetThemeColor` at `0x180055f48`
- `UxTheme!GetThemeColor` at `0x18005638c`
- `UxTheme!GetThemeColor` at `0x180055f48`
- `UxTheme!GetThemeColor` at `0x18005638c`

## pseudocode

```c
void __fastcall CStatic::OnPaint(LPARAM lData, HDC hdc, int a3)
{
  int v6; // r15d
  int v7; // r12d
  HWND v8; // rcx
  unsigned __int8 v9; // di
  void *v10; // rdx
  void *v11; // rcx
  LPARAM v12; // rbx
  HWND Parent; // rax
  HBRUSH v14; // r13
  HWND v15; // rbx
  HWND v16; // rcx
  int DlgCtrlID; // eax
  HWND v18; // rcx
  BOOL v19; // eax
  int v20; // ecx
  __int64 v21; // rax
  UINT uFlags; // r15d
  int cy; // edi
  int v24; // ebx
  HBRUSH SysColorBrush; // rax
  __int64 v26; // r9
  void *v27; // rcx
  HDC CompatibleDC; // rax
  HDC v29; // r15
  HGDIOBJ v30; // r12
  int v31; // edi
  int v32; // ebx
  DWORD crTransparent; // eax
  unsigned int v34; // ebx
  int v35; // r15d
  LONG left; // r10d
  int v37; // ecx
  LONG top; // r11d
  int v39; // r8d
  void *v40; // rcx
  int v41; // ecx
  HBRUSH v42; // r8
  __int64 v43; // rcx
  HENHMETAFILE v44; // rdx
  int WindowTextLengthW; // edi
  HANDLE ProcessHeap; // rax
  WCHAR *v47; // rax
  WCHAR *v48; // rbx
  HANDLE v49; // rax
  UINT align; // [rsp+60h] [rbp-49h]
  int v51; // [rsp+64h] [rbp-45h]
  HGDIOBJ h; // [rsp+68h] [rbp-41h]
  LPARAM lParam[2]; // [rsp+70h] [rbp-39h] BYREF
  __int128 v54; // [rsp+80h] [rbp-29h]
  HDC v55; // [rsp+90h] [rbp-19h]
  struct tagRECT v56; // [rsp+98h] [rbp-11h]
  __int64 v57; // [rsp+A8h] [rbp-1h]
  struct tagRECT Rect; // [rsp+B0h] [rbp+7h] BYREF
  COLORREF pColor; // [rsp+C0h] [rbp+17h] BYREF

  align = 0;
  v6 = *(_DWORD *)(*(_QWORD *)(lData + 48) + 8LL);
  v51 = v6 & 0x2000;
  if ( (v6 & 0x2000) != 0 )
  {
    align = GetTextAlign(hdc);
    SetTextAlign(hdc, align | 0x100);
  }
  v7 = *(_DWORD *)(*(_QWORD *)(lData + 48) + 12LL);
  v8 = *(HWND *)lData;
  v9 = v7 & 0x1F;
  Rect = 0;
  GetClientRect(v8, &Rect);
  if ( a3 )
    IntersectClipRect(hdc, Rect.left, Rect.top, Rect.right, Rect.bottom);
  if ( (byte_1801F06A8[v9] & 8) != 0 && (v10 = *(void **)(lData + 8)) != 0 )
    h = SelectObject(hdc, v10);
  else
    h = 0;
  v11 = *(void **)(lData + 40);
  if ( v11 )
  {
    pColor = 0;
    if ( GetThemeColor(v11, 0, 0, 3803, &pColor) >= 0 )
    {
      SetTextColor(hdc, pColor);
      v40 = *(void **)(lData + 40);
      LODWORD(lParam[0]) = 0;
      if ( GetThemeColor(v40, 0, 0, 3802, (COLORREF *)lParam) >= 0 )
        SetBkColor(hdc, lParam[0]);
    }
  }
  SetBkMode(hdc, 2);
  v12 = *(_QWORD *)lData;
  Parent = GetParent(*(HWND *)lData);
  v14 = (HBRUSH)SendMessageW(Parent, 0x138u, (WPARAM)hdc, v12);
  v15 = GetParent(*(HWND *)lData);
  if ( (byte_1801F06A8[v9] & 4) != 0 && (*(_BYTE *)(lData + 32) & 2) == 0 )
    FillRect(hdc, &Rect, v14);
  if ( v9 <= 8u )
  {
    if ( v9 != 8 )
    {
      if ( !v9 || v9 == 1 || v9 == 2 )
      {
LABEL_21:
        if ( GetWindowTextLengthW(*(HWND *)lData) )
        {
          uFlags = 0;
          if ( !IsWindowEnabled(*(HWND *)lData) && (*(_BYTE *)(lData + 32) & 8) == 0 )
            uFlags = 32;
          cy = Rect.bottom - Rect.top;
          v24 = Rect.right - Rect.left;
          SysColorBrush = GetSysColorBrush(8);
          DrawStateW(hdc, SysColorBrush, CStatic::s_DrawStateCB, lData, 1u, Rect.left, Rect.top, v24, cy, uFlags);
        }
        goto LABEL_24;
      }
      if ( v9 == 3 )
      {
        if ( *(_QWORD *)(lData + 16) )
        {
          v34 = 0;
          v35 = v6 & 0x400000;
          if ( v35 )
            v34 = SetLayoutWidth(hdc, 0xFFFFFFFFLL, 0);
          if ( (v7 & 0x200) != 0 )
          {
            v43 = *(_QWORD *)(lData + 16);
            lParam[0] = 0;
            GetIconSize(v43, lParam);
            v37 = lParam[0];
            v39 = HIDWORD(lParam[0]);
            left = (Rect.right - LODWORD(lParam[0])) / 2;
            Rect.left = left;
            Rect.right = LODWORD(lParam[0]) + left;
            top = (Rect.bottom - HIDWORD(lParam[0])) / 2;
            Rect.top = top;
            Rect.bottom = HIDWORD(lParam[0]) + top;
          }
          else
          {
            left = Rect.left;
            v37 = Rect.right - Rect.left;
            top = Rect.top;
            v39 = Rect.bottom - Rect.top;
          }
          DrawIconEx(hdc, left, top, *(HICON *)(lData + 16), v37, v39, *(_DWORD *)(lData + 28), v14, 3u);
          if ( v35 )
            SetLayoutWidth(hdc, 0xFFFFFFFFLL, v34);
          goto LABEL_24;
        }
        v42 = v14;
      }
      else
      {
        switch ( v9 )
        {
          case 4u:
            v41 = 21;
            break;
          case 5u:
            v41 = 16;
            break;
          case 6u:
            v41 = 20;
            break;
          case 7u:
            v26 = 168;
            goto LABEL_85;
          default:
            goto LABEL_24;
        }
        v42 = GetSysColorBrush(v41);
      }
      FillRect(hdc, &Rect, v42);
      goto LABEL_24;
    }
    v26 = 128;
LABEL_85:
    DrawFrame(hdc, &Rect, 1, v26);
    goto LABEL_24;
  }
  if ( v9 == 9 )
  {
    v26 = 160;
    goto LABEL_85;
  }
  if ( v9 != 11 )
  {
    if ( v9 != 12 )
    {
      switch ( v9 )
      {
        case 0xDu:
          memset_0(lParam, 0, 0x40u);
          v16 = *(HWND *)lData;
          LODWORD(lParam[0]) = 5;
          DlgCtrlID = GetDlgCtrlID(v16);
          v18 = *(HWND *)lData;
          HIDWORD(lParam[0]) = DlgCtrlID;
          HIDWORD(lParam[1]) = 1;
          v19 = IsWindowVisible(v18);
          v55 = hdc;
          *((_QWORD *)&v54 + 1) = *(_QWORD *)lData;
          v20 = v19 ? 4 : 0;
          v56 = Rect;
          v21 = *(_QWORD *)(lData + 48);
          LODWORD(v54) = v20;
          v57 = 0;
          if ( (*(_DWORD *)(v21 + 8) & 0x40000000) != 0 )
            LODWORD(v54) = v20 | 0x100;
          SendMessageW(v15, 0x2Bu, HIDWORD(lParam[0]), (LPARAM)lParam);
          break;
        case 0xEu:
          v27 = *(void **)(lData + 16);
          if ( v27 )
          {
            *(_OWORD *)lParam = 0;
            v54 = 0;
            if ( GetObjectW(v27, 32, lParam) )
            {
              if ( (v7 & 0x200) != 0 )
              {
                Rect.left = (Rect.right - HIDWORD(lParam[0])) >> 1;
                Rect.right = Rect.left + HIDWORD(lParam[0]);
                Rect.top = (Rect.bottom - LODWORD(lParam[1])) >> 1;
                Rect.bottom = Rect.top + LODWORD(lParam[1]);
              }
              CompatibleDC = CreateCompatibleDC(hdc);
              v29 = CompatibleDC;
              if ( CompatibleDC )
              {
                v30 = SelectObject(CompatibleDC, *(HGDIOBJ *)(lData + 16));
                if ( (*(_BYTE *)(lData + 32) & 4) != 0 )
                {
                  pColor = 33488896;
                  GdiAlphaBlend(
                    hdc,
                    Rect.left,
                    Rect.top,
                    Rect.right - Rect.left,
                    Rect.bottom - Rect.top,
                    v29,
                    0,
                    0,
                    SHIDWORD(lParam[0]),
                    lParam[1],
                    (BLENDFUNCTION)33488896);
                }
                else
                {
                  v31 = Rect.bottom - Rect.top;
                  v32 = Rect.right - Rect.left;
                  crTransparent = GetSysColor(15);
                  GdiTransparentBlt(
                    hdc,
                    Rect.left,
                    Rect.top,
                    v32,
                    v31,
                    v29,
                    0,
                    0,
                    SHIDWORD(lParam[0]),
                    lParam[1],
                    crTransparent);
                }
                if ( v30 )
                  SelectObject(v29, v30);
                DeleteDC(v29);
              }
            }
          }
          break;
        case 0xFu:
          v44 = *(HENHMETAFILE *)(lData + 16);
          if ( v44 )
          {
            *(struct tagRECT *)lParam = Rect;
            PlayEnhMetaFile(hdc, v44, (const RECT *)lParam);
          }
          break;
        case 0x12u:
          DrawEdge(hdc, &Rect, 6u, 0xFu);
          break;
      }
      goto LABEL_24;
    }
    goto LABEL_21;
  }
  WindowTextLengthW = GetWindowTextLengthW(*(HWND *)lData);
  ProcessHeap = GetProcessHeap();
  v47 = (WCHAR *)CCHeapAllocArraySize(ProcessHeap, 8, 2, (unsigned int)(WindowTextLengthW + 1));
  v48 = v47;
  if ( v47 )
  {
    if ( WindowTextLengthW <= 0 )
      *v47 = 0;
    else
      WindowTextLengthW = GetWindowTextW(*(HWND *)lData, v47, WindowTextLengthW + 1);
    if ( (v7 & 0x80u) == 0 )
      TextOutW(hdc, Rect.left, Rect.top, v48, WindowTextLengthW);
    else
      SHExtTextOutW(hdc, Rect.left, Rect.top, 6);
    v49 = GetProcessHeap();
    HeapFree(v49, 0, v48);
  }
LABEL_24:
  if ( h )
    SelectObject(hdc, h);
  if ( v51 )
    SetTextAlign(hdc, align);
}

```

## disassembly

```asm
0x180055e60  mov     [rsp-8+arg_10], rbx
0x180055e65  push    rbp
0x180055e66  push    rsi
0x180055e67  push    rdi
0x180055e68  push    r12
0x180055e6a  push    r13
0x180055e6c  push    r14
0x180055e6e  push    r15
0x180055e70  lea     rbp, [rsp-27h]
0x180055e75  sub     rsp, 0D0h
0x180055e7c  mov     rax, cs:__security_cookie
0x180055e83  xor     rax, rsp
0x180055e86  mov     [rbp+57h+var_38], rax
0x180055e8a  mov     rax, [rcx+30h]
0x180055e8e  mov     ebx, r8d
0x180055e91  mov     rsi, rdx
0x180055e94  mov     [rbp+57h+align], 0
0x180055e9b  mov     r14, rcx
0x180055e9e  mov     r15d, [rax+8]
0x180055ea2  mov     eax, r15d
0x180055ea5  and     eax, 2000h
0x180055eaa  mov     [rbp+57h+var_9C], eax
0x180055ead  jnz     loc_180056341
0x180055eb3  mov     rcx, [r14+30h]
0x180055eb7  lea     rdx, [rbp+57h+Rect]; lpRect
0x180055ebb  xorps   xmm0, xmm0
0x180055ebe  mov     r12d, [rcx+0Ch]
0x180055ec2  mov     dil, r12b
0x180055ec5  mov     rcx, [r14]; hWnd
0x180055ec8  and     dil, 1Fh
0x180055ecc  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x180055ed0  call    cs:__imp_GetClientRect
0x180055ed6  test    ebx, ebx
0x180055ed8  jz      short loc_180055EF5
0x180055eda  mov     eax, [rbp+57h+Rect.bottom]
0x180055edd  mov     rcx, rsi; hdc
0x180055ee0  mov     r9d, [rbp+57h+Rect.right]; right
0x180055ee4  mov     r8d, [rbp+57h+Rect.top]; top
0x180055ee8  mov     edx, [rbp+57h+Rect.left]; left
0x180055eeb  mov     [rsp+100h+bottom], eax; bottom
0x180055eef  call    cs:__imp_IntersectClipRect
0x180055ef5  movzx   eax, dil
0x180055ef9  lea     rcx, byte_1801F06A8
0x180055f00  test    byte ptr [rax+rcx], 8
0x180055f04  jz      loc_180056147
0x180055f0a  mov     rdx, [r14+8]; h
0x180055f0e  test    rdx, rdx
0x180055f11  jz      loc_180056147
0x180055f17  mov     rcx, rsi; hdc
0x180055f1a  call    cs:__imp_SelectObject
0x180055f20  mov     [rbp+57h+h], rax
0x180055f24  mov     rcx, [r14+28h]; hTheme
0x180055f28  test    rcx, rcx
0x180055f2b  jz      short loc_180055F56
0x180055f2d  lea     rax, [rbp+57h+pColor]
0x180055f31  mov     [rbp+57h+pColor], 0
0x180055f38  mov     r9d, 0EDBh; iPropId
0x180055f3e  mov     qword ptr [rsp+100h+bottom], rax; pColor
0x180055f43  xor     r8d, r8d; iStateId
0x180055f46  xor     edx, edx; iPartId
0x180055f48  call    cs:__imp_GetThemeColor
0x180055f4e  test    eax, eax
0x180055f50  jns     loc_180056361
0x180055f56  mov     edx, 2; mode
0x180055f5b  mov     rcx, rsi; hdc
0x180055f5e  call    cs:__imp_SetBkMode
0x180055f64  mov     rbx, [r14]
0x180055f67  mov     rcx, rbx; hWnd
0x180055f6a  call    cs:__imp_GetParent
0x180055f70  mov     r9, rbx; lParam
0x180055f73  mov     r8, rsi; wParam
0x180055f76  mov     rcx, rax; hWnd
0x180055f79  mov     edx, 138h; Msg
0x180055f7e  call    cs:__imp_SendMessageW
0x180055f84  mov     rcx, [r14]; hWnd
0x180055f87  mov     r13, rax
0x180055f8a  call    cs:__imp_GetParent
0x180055f90  movzx   ecx, dil
0x180055f94  mov     rbx, rax
0x180055f97  lea     rax, byte_1801F06A8
0x180055f9e  test    byte ptr [rcx+rax], 4
0x180055fa2  jnz     loc_18005606F
0x180055fa8  movzx   ecx, dil
0x180055fac  cmp     ecx, 8
0x180055faf  jbe     loc_18005617E
0x180055fb5  sub     ecx, 9
0x180055fb8  jz      loc_1800565BC
0x180055fbe  sub     ecx, 2
0x180055fc1  jz      loc_18005650A
0x180055fc7  sub     ecx, 1
0x180055fca  jz      loc_18005608F
0x180055fd0  sub     ecx, 1
0x180055fd3  jnz     loc_180056154
0x180055fd9  lea     r8d, [rcx+40h]; Size
0x180055fdd  xor     edx, edx; Val
0x180055fdf  lea     rcx, [rbp+57h+lParam]; void *
0x180055fe3  call    memset_0
0x180055fe8  mov     rcx, [r14]; hWnd
0x180055feb  mov     dword ptr [rbp+57h+lParam], 5
0x180055ff2  call    cs:__imp_GetDlgCtrlID
0x180055ff8  mov     rcx, [r14]; hWnd
0x180055ffb  mov     dword ptr [rbp+57h+lParam+4], eax
0x180055ffe  mov     dword ptr [rbp+57h+lParam+0Ch], 1
0x180056005  call    cs:__imp_IsWindowVisible
0x18005600b  neg     eax
0x18005600d  mov     [rbp+57h+var_70], rsi
0x180056011  mov     rax, [r14]
0x180056014  mov     qword ptr [rbp+57h+var_80+8], rax
0x180056018  sbb     ecx, ecx
0x18005601a  mov     eax, [rbp+57h+Rect.left]
0x18005601d  and     ecx, 4
0x180056020  mov     [rbp+57h+var_68], eax
0x180056023  mov     eax, [rbp+57h+Rect.top]
0x180056026  mov     [rbp+57h+var_64], eax
0x180056029  mov     eax, [rbp+57h+Rect.right]
0x18005602c  mov     [rbp+57h+var_60], eax
0x18005602f  mov     eax, [rbp+57h+Rect.bottom]
0x180056032  mov     [rbp+57h+var_5C], eax
0x180056035  mov     rax, [r14+30h]
0x180056039  mov     dword ptr [rbp+57h+var_80], ecx
0x18005603c  mov     [rbp+57h+var_58], 0
0x180056044  test    dword ptr [rax+8], 40000000h
0x18005604b  jz      short loc_180056054
0x18005604d  bts     ecx, 8
0x180056051  mov     dword ptr [rbp+57h+var_80], ecx
0x180056054  mov     r8d, dword ptr [rbp+57h+lParam+4]; wParam
0x180056058  lea     r9, [rbp+57h+lParam]; lParam
0x18005605c  mov     edx, 2Bh ; '+'; Msg
0x180056061  mov     rcx, rbx; hWnd
0x180056064  call    cs:__imp_SendMessageW
0x18005606a  jmp     loc_180056101
0x18005606f  test    byte ptr [r14+20h], 2
0x180056074  jnz     loc_180055FA8
0x18005607a  mov     r8, r13; hbr
0x18005607d  lea     rdx, [rbp+57h+Rect]; lprc
0x180056081  mov     rcx, rsi; hDC
0x180056084  call    cs:__imp_FillRect
0x18005608a  jmp     loc_180055FA8
0x18005608f  mov     rcx, [r14]; hWnd
0x180056092  call    cs:__imp_GetWindowTextLengthW
0x180056098  test    eax, eax
0x18005609a  jz      short loc_180056101
0x18005609c  mov     rcx, [r14]; hWnd
0x18005609f  xor     r15d, r15d
0x1800560a2  call    cs:__imp_IsWindowEnabled
0x1800560a8  test    eax, eax
0x1800560aa  jz      loc_1800564F7
0x1800560b0  mov     edi, [rbp+57h+Rect.bottom]
0x1800560b3  mov     ecx, 8; nIndex
0x1800560b8  mov     ebx, [rbp+57h+Rect.right]
0x1800560bb  sub     edi, [rbp+57h+Rect.top]
0x1800560be  sub     ebx, [rbp+57h+Rect.left]
0x1800560c1  call    cs:__imp_GetSysColorBrush
0x1800560c7  mov     [rsp+100h+uFlags], r15d; uFlags
0x1800560cc  lea     r8, ?s_DrawStateCB@CStatic@@CAHPEAUHDC__@@_J_KHH@Z; qfnCallBack
0x1800560d3  mov     [rsp+100h+cy], edi; cy
0x1800560d7  mov     rdx, rax; hbrFore
0x1800560da  mov     eax, [rbp+57h+Rect.top]
0x1800560dd  mov     r9, r14; lData
0x1800560e0  mov     [rsp+100h+yoriginSrc], ebx; cx
0x1800560e4  mov     rcx, rsi; hdc
0x1800560e7  mov     [rsp+100h+y], eax; y
0x1800560eb  mov     eax, [rbp+57h+Rect.left]
0x1800560ee  mov     [rsp+100h+x], eax; x
0x1800560f2  mov     qword ptr [rsp+100h+bottom], 1; wData
0x1800560fb  call    cs:__imp_DrawStateW
0x180056101  mov     rax, [rbp+57h+h]
0x180056105  test    rax, rax
0x180056108  jz      short loc_180056116
0x18005610a  mov     rdx, rax; h
0x18005610d  mov     rcx, rsi; hdc
0x180056110  call    cs:__imp_SelectObject
0x180056116  cmp     [rbp+57h+var_9C], 0
0x18005611a  jnz     loc_1800565DA
0x180056120  mov     rcx, [rbp+57h+var_38]
0x180056124  xor     rcx, rsp; StackCookie
0x180056127  call    __security_check_cookie
0x18005612c  mov     rbx, [rsp+100h+arg_10]
0x180056134  add     rsp, 0D0h
0x18005613b  pop     r15
0x18005613d  pop     r14
0x18005613f  pop     r13
0x180056141  pop     r12
0x180056143  pop     rdi
0x180056144  pop     rsi
0x180056145  pop     rbp
0x180056146  retn
0x180056147  mov     [rbp+57h+h], 0
0x18005614f  jmp     loc_180055F24
0x180056154  sub     ecx, 1
0x180056157  jz      short loc_1800561D7
0x180056159  sub     ecx, 1
0x18005615c  jz      loc_18005644F
0x180056162  cmp     ecx, 3
0x180056165  jnz     short loc_180056101
0x180056167  lea     r9d, [rcx+0Ch]; grfFlags
0x18005616b  lea     r8d, [rcx+3]; edge
0x18005616f  mov     rcx, rsi; hdc
0x180056172  lea     rdx, [rbp+57h+Rect]; qrc
0x180056176  call    cs:__imp_DrawEdge
0x18005617c  jmp     short loc_180056101
0x18005617e  jz      loc_180056444
0x180056184  test    dil, dil
0x180056187  jz      loc_18005608F
0x18005618d  sub     ecx, 1
0x180056190  jz      loc_18005608F
0x180056196  sub     ecx, 1
0x180056199  jz      loc_18005608F
0x18005619f  sub     ecx, 1
0x1800561a2  jz      loc_1800562B7
0x1800561a8  sub     ecx, 1
0x1800561ab  jz      loc_1800563B9
0x1800561b1  sub     ecx, 1
0x1800561b4  jz      loc_1800563B2
0x1800561ba  sub     ecx, 1
0x1800561bd  jz      loc_1800563AB
0x1800561c3  cmp     ecx, 1
0x1800561c6  jnz     loc_180056101
0x1800561cc  mov     r9d, 0A8h
0x1800561d2  jmp     loc_1800565C2
0x1800561d7  mov     rcx, [r14+10h]; h
0x1800561db  test    rcx, rcx
0x1800561de  jz      loc_180056101
0x1800561e4  xorps   xmm0, xmm0
0x1800561e7  lea     r8, [rbp+57h+lParam]; pv
0x1800561eb  mov     edx, 20h ; ' '; c
0x1800561f0  movups  xmmword ptr [rbp+57h+lParam], xmm0
0x1800561f4  movups  [rbp+57h+var_80], xmm0
0x1800561f8  call    cs:__imp_GetObjectW
0x1800561fe  test    eax, eax
0x180056200  jz      loc_180056101
0x180056206  bt      r12d, 9
0x18005620b  jb      loc_180056477
0x180056211  mov     rcx, rsi; hdc
0x180056214  call    cs:__imp_CreateCompatibleDC
0x18005621a  mov     r15, rax
0x18005621d  test    rax, rax
0x180056220  jz      loc_180056101
0x180056226  mov     rdx, [r14+10h]; h
0x18005622a  mov     rcx, rax; hdc
0x18005622d  call    cs:__imp_SelectObject
0x180056233  test    byte ptr [r14+20h], 4
0x180056238  mov     r12, rax
0x18005623b  jnz     loc_1800564A0
0x180056241  mov     edi, [rbp+57h+Rect.bottom]
0x180056244  mov     ecx, 0Fh; nIndex
0x180056249  mov     ebx, [rbp+57h+Rect.right]
0x18005624c  sub     edi, [rbp+57h+Rect.top]
0x18005624f  sub     ebx, [rbp+57h+Rect.left]
0x180056252  call    cs:__imp_GetSysColor
0x180056258  mov     r8d, [rbp+57h+Rect.top]; yoriginDest
0x18005625c  mov     r9d, ebx; wDest
0x18005625f  mov     edx, [rbp+57h+Rect.left]; xoriginDest
0x180056262  mov     rcx, rsi; hdcDest
0x180056265  mov     [rsp+100h+crTransparent], eax; crTransparent
0x180056269  mov     eax, dword ptr [rbp+57h+lParam+8]
0x18005626c  mov     [rsp+100h+uFlags], eax; hSrc
0x180056270  mov     eax, dword ptr [rbp+57h+lParam+4]
0x180056273  mov     [rsp+100h+cy], eax; wSrc
0x180056277  mov     [rsp+100h+yoriginSrc], 0; yoriginSrc
0x18005627f  mov     [rsp+100h+y], 0; xoriginSrc
0x180056287  mov     qword ptr [rsp+100h+x], r15; hdcSrc
0x18005628c  mov     [rsp+100h+bottom], edi; hDest
0x180056290  call    cs:__imp_GdiTransparentBlt
0x180056296  test    r12, r12
0x180056299  jnz     short loc_1800562A9
0x18005629b  mov     rcx, r15; hdc
0x18005629e  call    cs:__imp_DeleteDC
0x1800562a4  jmp     loc_180056101
0x1800562a9  mov     rdx, r12; h
0x1800562ac  mov     rcx, r15; hdc
0x1800562af  call    cs:__imp_SelectObject
0x1800562b5  jmp     short loc_18005629B
0x1800562b7  cmp     qword ptr [r14+10h], 0
0x1800562bc  jz      loc_18005642F
0x1800562c2  xor     ebx, ebx
0x1800562c4  or      edi, 0FFFFFFFFh
0x1800562c7  and     r15d, 400000h
0x1800562ce  jnz     loc_1800563C9
0x1800562d4  bt      r12d, 9
0x1800562d9  jb      loc_1800563DE
0x1800562df  mov     ecx, [rbp+57h+Rect.right]
0x1800562e2  mov     r10d, [rbp+57h+Rect.left]
0x1800562e6  sub     ecx, r10d
0x1800562e9  mov     r8d, [rbp+57h+Rect.bottom]
0x1800562ed  mov     r11d, [rbp+57h+Rect.top]
0x1800562f1  sub     r8d, r11d
0x1800562f4  mov     eax, [r14+1Ch]
0x1800562f8  mov     edx, r10d; xLeft
0x1800562fb  mov     r9, [r14+10h]; hIcon
0x1800562ff  mov     [rsp+100h+cy], 3; diFlags
0x180056307  mov     qword ptr [rsp+100h+yoriginSrc], r13; hbrFlickerFreeDraw
0x18005630c  mov     [rsp+100h+y], eax; istepIfAniCur
0x180056310  mov     [rsp+100h+x], r8d; cyWidth
0x180056315  mov     r8d, r11d; yTop
0x180056318  mov     [rsp+100h+bottom], ecx; cxWidth
0x18005631c  mov     rcx, rsi; hdc
0x18005631f  call    cs:__imp_DrawIconEx
0x180056325  test    r15d, r15d
0x180056328  jz      loc_180056101
  ... truncated ...
```
