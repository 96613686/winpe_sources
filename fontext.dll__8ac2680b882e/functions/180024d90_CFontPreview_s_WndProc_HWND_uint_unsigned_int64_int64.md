# CFontPreview::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180024d90`
- end: `0x180025199`
- name: `?s_WndProc@CFontPreview@@CA_JPEAUHWND__@@I_K_J@Z`
- size: `1033`
- prototype: `__int64 __fastcall(HWND, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800247a0`
- `0x180024aac`
- `0x180024d90`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x180024fde`
- `GDI32!CreateCompatibleDC` at `0x1800250d4`
- `GDI32!CreateCompatibleDC` at `0x180024fde`
- `GDI32!CreateCompatibleDC` at `0x1800250d4`
- `GDI32!DeleteDC` at `0x180025031`
- `GDI32!DeleteDC` at `0x180025107`
- `GDI32!DeleteDC` at `0x180025031`
- `GDI32!DeleteDC` at `0x180025107`
- `USER32!DefWindowProcW` at `0x180025170`
- `USER32!DefWindowProcW` at `0x180025170`
- `USER32!InvalidateRect` at `0x180024f16`
- `USER32!InvalidateRect` at `0x180024f16`
- `USER32!ScrollWindowEx` at `0x180024f09`
- `USER32!ScrollWindowEx` at `0x180024f09`
- `USER32!SetRect` at `0x180025001`
- `USER32!SetRect` at `0x180025001`
- `USER32!SetScrollInfo` at `0x18002509b`
- `USER32!SetScrollInfo` at `0x18002514f`
- `USER32!SetScrollInfo` at `0x18002509b`
- `USER32!SetScrollInfo` at `0x18002514f`
- `USER32!GetClientRect` at `0x1800250b4`
- `USER32!GetClientRect` at `0x1800250b4`
- `USER32!EndPaint` at `0x180024f97`
- `USER32!EndPaint` at `0x180024f97`
- `USER32!BeginPaint` at `0x180024f6e`
- `USER32!BeginPaint` at `0x180024f6e`
- `USER32!SetWindowLongPtrW` at `0x180024dd9`
- `USER32!SetWindowLongPtrW` at `0x180024dd9`
- `USER32!GetWindowLongPtrW` at `0x180024dee`
- `USER32!GetWindowLongPtrW` at `0x180024dee`

## pseudocode

```c
LRESULT __fastcall CFontPreview::s_WndProc(HWND a1, UINT Msg, WPARAM wParam, LONG_PTR *lParam)
{
  CFontPreview *WindowLongPtrW; // rdi
  int v10; // r8d
  int v11; // edx
  int v12; // ecx
  int v13; // edx
  int v14; // eax
  int v15; // r15d
  int v16; // r8d
  int v17; // eax
  const SCROLLINFO *p_rc; // r8
  HWND v19; // rdx
  UINT v20; // r15d
  HDC v21; // rbx
  HWND v22; // rdx
  int v23; // edx
  int v24; // ecx
  HDC CompatibleDC; // rax
  HDC v26; // rbx
  HWND v27; // rdx
  tagPAINTSTRUCT Paint; // [rsp+40h] [rbp-79h] BYREF
  struct tagRECT rc; // [rsp+90h] [rbp-29h] BYREF
  int v31; // [rsp+A0h] [rbp-19h]
  int v32; // [rsp+A4h] [rbp-15h]
  int v33; // [rsp+A8h] [rbp-11h]
  SCROLLINFO v34; // [rsp+B0h] [rbp-9h] BYREF

  if ( Msg != 129 )
  {
    WindowLongPtrW = (CFontPreview *)GetWindowLongPtrW(a1, -21);
    if ( WindowLongPtrW )
    {
      switch ( Msg )
      {
        case 1u:
          rc = 0;
          GetClientRect(a1, &rc);
          *((_DWORD *)WindowLongPtrW + 624) = rc.right - rc.left;
          *((_DWORD *)WindowLongPtrW + 625) = rc.bottom - rc.top;
          CompatibleDC = CreateCompatibleDC(0);
          *((_DWORD *)WindowLongPtrW + 622) = 0;
          v26 = CompatibleDC;
          *((_DWORD *)WindowLongPtrW + 626) = CFontPreview::RenderPreview(WindowLongPtrW, v27, CompatibleDC, 0, &rc);
          DeleteDC(v26);
          v34.nMax = *((_DWORD *)WindowLongPtrW + 626);
          v34.nPage = *((_DWORD *)WindowLongPtrW + 625);
          v34.nPos = *((_DWORD *)WindowLongPtrW + 622);
          v34.nTrackPos = 0;
          v34.cbSize = 28;
          *(_QWORD *)&v34.fMask = 31;
          SetScrollInfo(a1, 1, &v34, 1);
          CFontPreview::ShowOrHideVScroll(WindowLongPtrW, a1);
          return 0;
        case 5u:
          v20 = WORD1(lParam);
          if ( __PAIR64__(WORD1(lParam), (unsigned __int16)lParam) == *((_QWORD *)WindowLongPtrW + 312) )
            return 0;
          *((_DWORD *)WindowLongPtrW + 624) = (unsigned __int16)lParam;
          rc = 0;
          *((_DWORD *)WindowLongPtrW + 625) = WORD1(lParam);
          v21 = CreateCompatibleDC(0);
          SetRect(&rc, 0, 0, *((_DWORD *)WindowLongPtrW + 624), *((_DWORD *)WindowLongPtrW + 625));
          *((_DWORD *)WindowLongPtrW + 622) = 0;
          *((_DWORD *)WindowLongPtrW + 626) = CFontPreview::RenderPreview(WindowLongPtrW, v22, v21, 0, &rc);
          DeleteDC(v21);
          CFontPreview::ShowOrHideVScroll(WindowLongPtrW, a1);
          v23 = *((_DWORD *)WindowLongPtrW + 625);
          v24 = *((_DWORD *)WindowLongPtrW + 626);
          if ( v24 > v23 && *((_DWORD *)WindowLongPtrW + 622) > v24 - v23 )
            *((_DWORD *)WindowLongPtrW + 622) = v24 - v23;
          p_rc = &v34;
          v34.nPos = *((_DWORD *)WindowLongPtrW + 622);
          v34.nTrackPos = 0;
          v34.cbSize = 28;
          *(_QWORD *)&v34.fMask = 31;
          v34.nMax = v24;
          v34.nPage = v20;
LABEL_46:
          SetScrollInfo(a1, 1, p_rc, 1);
          return 0;
        case 0xFu:
          memset_0(&Paint, 0, sizeof(Paint));
          BeginPaint(a1, &Paint);
          CFontPreview::RenderPreview(WindowLongPtrW, v19, Paint.hdc, *((_DWORD *)WindowLongPtrW + 622), &Paint.rcPaint);
          EndPaint(a1, &Paint);
          return 0;
        case 0x14u:
          return 1;
        case 0x115u:
          v10 = *((_DWORD *)WindowLongPtrW + 622);
          v11 = v10;
          if ( (_WORD)wParam )
          {
            switch ( (unsigned __int16)wParam )
            {
              case 1u:
                v11 = *((_DWORD *)WindowLongPtrW + 623) + v10;
                break;
              case 2u:
                v11 = v10 - *((_DWORD *)WindowLongPtrW + 625);
                break;
              case 3u:
                v11 = *((_DWORD *)WindowLongPtrW + 625) + v10;
                break;
              case 4u:
              case 5u:
                if ( WORD1(wParam) != v10 )
                  v11 = WORD1(wParam);
                break;
              case 6u:
                v11 = 0;
                break;
              case 7u:
                v11 = *((_DWORD *)WindowLongPtrW + 626);
                break;
            }
          }
          else
          {
            v11 = v10 - *((_DWORD *)WindowLongPtrW + 623);
          }
          v12 = 0;
          if ( v11 >= 0 )
            v12 = v11;
          v13 = *((_DWORD *)WindowLongPtrW + 625);
          v14 = *((_DWORD *)WindowLongPtrW + 626) - v13;
          if ( v12 <= v14 )
            v14 = v12;
          v15 = 0;
          if ( v14 >= 0 )
            v15 = v14;
          if ( v10 == v15 )
            return 0;
          v16 = v10 - v15;
          v17 = -v16;
          if ( v16 > 0 )
            v17 = v16;
          if ( v17 >= v13 )
            InvalidateRect(a1, 0, 1);
          else
            ScrollWindowEx(a1, 0, v16, 0, 0, 0, 0, 6u);
          p_rc = (const SCROLLINFO *)&rc;
          rc.bottom = *((_DWORD *)WindowLongPtrW + 626);
          v31 = *((_DWORD *)WindowLongPtrW + 625);
          *((_DWORD *)WindowLongPtrW + 622) = v15;
          v33 = 0;
          rc.left = 28;
          *(_QWORD *)&rc.top = 31;
          v32 = v15;
          goto LABEL_46;
      }
    }
    return DefWindowProcW(a1, Msg, wParam, (LPARAM)lParam);
  }
  if ( !lParam )
    return 0;
  SetWindowLongPtrW(a1, -21, *lParam);
  return 1;
}

```

## disassembly

```asm
0x180024d90  push    rbp
0x180024d92  push    rbx
0x180024d93  push    rdi
0x180024d94  push    r12
0x180024d96  push    r14
0x180024d98  push    r15
0x180024d9a  lea     rbp, [rsp-2Fh]
0x180024d9f  sub     rsp, 0E8h
0x180024da6  mov     rax, cs:__security_cookie
0x180024dad  xor     rax, rsp
0x180024db0  mov     [rbp+57h+var_40], rax
0x180024db4  mov     rbx, r9
0x180024db7  mov     r15, r8
0x180024dba  mov     r12d, edx
0x180024dbd  mov     r14, rcx
0x180024dc0  cmp     edx, 81h
0x180024dc6  jnz     short loc_180024DE9
0x180024dc8  test    rbx, rbx
0x180024dcb  jz      loc_180025160
0x180024dd1  mov     r8, [r9]; dwNewLong
0x180024dd4  mov     edx, 0FFFFFFEBh; nIndex
0x180024dd9  call    cs:__imp_SetWindowLongPtrW
0x180024ddf  mov     ebx, 1
0x180024de4  jmp     loc_180025179
0x180024de9  mov     edx, 0FFFFFFEBh; nIndex
0x180024dee  call    cs:__imp_GetWindowLongPtrW
0x180024df4  mov     rdi, rax
0x180024df7  test    rax, rax
0x180024dfa  jz      loc_180025164
0x180024e00  mov     eax, r12d
0x180024e03  sub     eax, 1
0x180024e06  jz      loc_1800250A6
0x180024e0c  sub     eax, 4
0x180024e0f  jz      loc_180024FA2
0x180024e15  sub     eax, 0Ah
0x180024e18  jz      loc_180024F58
0x180024e1e  sub     eax, 5
0x180024e21  jz      short loc_180024DDF
0x180024e23  cmp     eax, 101h
0x180024e28  jnz     loc_180025164
0x180024e2e  mov     r8d, [rdi+9B8h]
0x180024e35  mov     edx, r8d
0x180024e38  movzx   ecx, r15w
0x180024e3c  test    ecx, ecx
0x180024e3e  jz      short loc_180024E97
0x180024e40  sub     ecx, 1
0x180024e43  jz      short loc_180024E8F
0x180024e45  sub     ecx, 1
0x180024e48  jz      short loc_180024E87
0x180024e4a  sub     ecx, 1
0x180024e4d  jz      short loc_180024E7F
0x180024e4f  sub     ecx, 1
0x180024e52  jz      short loc_180024E6F
0x180024e54  sub     ecx, 1
0x180024e57  jz      short loc_180024E6F
0x180024e59  sub     ecx, 1
0x180024e5c  jz      short loc_180024E6B
0x180024e5e  cmp     ecx, 1
0x180024e61  jnz     short loc_180024E9D
0x180024e63  mov     edx, [rdi+9C8h]
0x180024e69  jmp     short loc_180024E9D
0x180024e6b  xor     edx, edx
0x180024e6d  jmp     short loc_180024E9D
0x180024e6f  shr     r15, 10h
0x180024e73  movzx   eax, r15w
0x180024e77  cmp     eax, edx
0x180024e79  jz      short loc_180024E9D
0x180024e7b  mov     edx, eax
0x180024e7d  jmp     short loc_180024E9D
0x180024e7f  add     edx, [rdi+9C4h]
0x180024e85  jmp     short loc_180024E9D
0x180024e87  sub     edx, [rdi+9C4h]
0x180024e8d  jmp     short loc_180024E9D
0x180024e8f  add     edx, [rdi+9BCh]
0x180024e95  jmp     short loc_180024E9D
0x180024e97  sub     edx, [rdi+9BCh]
0x180024e9d  mov     eax, [rdi+9C8h]
0x180024ea3  xor     ecx, ecx
0x180024ea5  test    edx, edx
0x180024ea7  cmovns  ecx, edx
0x180024eaa  mov     edx, [rdi+9C4h]
0x180024eb0  sub     eax, edx
0x180024eb2  cmp     ecx, eax
0x180024eb4  cmovle  eax, ecx
0x180024eb7  xor     r15d, r15d
0x180024eba  test    eax, eax
0x180024ebc  cmovns  r15d, eax
0x180024ec0  cmp     r8d, r15d
0x180024ec3  jz      loc_180025160
0x180024ec9  sub     r8d, r15d; dy
0x180024ecc  mov     ebx, 1
0x180024ed1  mov     eax, r8d
0x180024ed4  mov     rcx, r14; hWnd
0x180024ed7  neg     eax
0x180024ed9  cmovs   eax, r8d
0x180024edd  cmp     eax, edx
0x180024edf  jge     short loc_180024F11
0x180024ee1  mov     [rsp+110h+flags], 6; flags
0x180024ee9  xor     r9d, r9d; prcScroll
0x180024eec  mov     [rsp+110h+prcUpdate], 0; prcUpdate
0x180024ef5  xor     edx, edx; dx
0x180024ef7  mov     [rsp+110h+hrgnUpdate], 0; hrgnUpdate
0x180024f00  mov     [rsp+110h+prcClip], 0; prcClip
0x180024f09  call    cs:__imp_ScrollWindowEx
0x180024f0f  jmp     short loc_180024F1C
0x180024f11  mov     r8d, ebx; bErase
0x180024f14  xor     edx, edx; lpRect
0x180024f16  call    cs:__imp_InvalidateRect
0x180024f1c  mov     eax, [rdi+9C8h]
0x180024f22  lea     r8, [rbp+57h+rc]
0x180024f26  mov     [rbp+57h+rc.bottom], eax
0x180024f29  mov     eax, [rdi+9C4h]
0x180024f2f  mov     [rbp+57h+var_70], eax
0x180024f32  mov     [rdi+9B8h], r15d
0x180024f39  mov     [rbp+57h+var_68], 0
0x180024f40  mov     [rbp+57h+rc.left], 1Ch
0x180024f47  mov     qword ptr [rbp+57h+rc.top], 1Fh
0x180024f4f  mov     [rbp+57h+var_6C], r15d
0x180024f53  jmp     loc_180025093
0x180024f58  xor     edx, edx; Val
0x180024f5a  lea     rcx, [rbp+57h+Paint]; void *
0x180024f5e  lea     r8d, [rdx+48h]; Size
0x180024f62  call    memset_0
0x180024f67  lea     rdx, [rbp+57h+Paint]; lpPaint
0x180024f6b  mov     rcx, r14; hWnd
0x180024f6e  call    cs:__imp_BeginPaint
0x180024f74  mov     r9d, [rdi+9B8h]; int
0x180024f7b  lea     rax, [rbp+57h+Paint.rcPaint]
0x180024f7f  mov     r8, [rbp+57h+Paint.hdc]; HDC
0x180024f83  mov     rcx, rdi; this
0x180024f86  mov     [rsp+110h+prcClip], rax; struct tagRECT *
0x180024f8b  call    ?RenderPreview@CFontPreview@@AEAAHPEAUHWND__@@PEAUHDC__@@HPEAUtagRECT@@@Z; CFontPreview::RenderPreview(HWND__ *,HDC__ *,int,tagRECT *)
0x180024f90  lea     rdx, [rbp+57h+Paint]; lpPaint
0x180024f94  mov     rcx, r14; hWnd
0x180024f97  call    cs:__imp_EndPaint
0x180024f9d  jmp     loc_180025160
0x180024fa2  mov     rax, rbx
0x180024fa5  shr     rax, 10h
0x180024fa9  movzx   r15d, ax
0x180024fad  cmp     r15d, [rdi+9C4h]
0x180024fb4  jnz     short loc_180024FC5
0x180024fb6  movzx   eax, bx
0x180024fb9  cmp     eax, [rdi+9C0h]
0x180024fbf  jz      loc_180025160
0x180024fc5  movzx   eax, bx
0x180024fc8  xorps   xmm0, xmm0
0x180024fcb  xor     ecx, ecx; hdc
0x180024fcd  mov     [rdi+9C0h], eax
0x180024fd3  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x180024fd7  mov     [rdi+9C4h], r15d
0x180024fde  call    cs:__imp_CreateCompatibleDC
0x180024fe4  mov     ecx, [rdi+9C4h]
0x180024fea  xor     r8d, r8d; yTop
0x180024fed  mov     r9d, [rdi+9C0h]; xRight
0x180024ff4  xor     edx, edx; xLeft
0x180024ff6  mov     dword ptr [rsp+110h+prcClip], ecx; yBottom
0x180024ffa  mov     rbx, rax
0x180024ffd  lea     rcx, [rbp+57h+rc]; lprc
0x180025001  call    cs:__imp_SetRect
0x180025007  lea     rax, [rbp+57h+rc]
0x18002500b  mov     dword ptr [rdi+9B8h], 0
0x180025015  xor     r9d, r9d; int
0x180025018  mov     [rsp+110h+prcClip], rax; struct tagRECT *
0x18002501d  mov     r8, rbx; HDC
0x180025020  mov     rcx, rdi; this
0x180025023  call    ?RenderPreview@CFontPreview@@AEAAHPEAUHWND__@@PEAUHDC__@@HPEAUtagRECT@@@Z; CFontPreview::RenderPreview(HWND__ *,HDC__ *,int,tagRECT *)
0x180025028  mov     rcx, rbx; hdc
0x18002502b  mov     [rdi+9C8h], eax
0x180025031  call    cs:__imp_DeleteDC
0x180025037  mov     rdx, r14; HWND
0x18002503a  mov     rcx, rdi; this
0x18002503d  call    ?ShowOrHideVScroll@CFontPreview@@AEAAXPEAUHWND__@@@Z; CFontPreview::ShowOrHideVScroll(HWND__ *)
0x180025042  mov     edx, [rdi+9C4h]
0x180025048  mov     ecx, [rdi+9C8h]
0x18002504e  cmp     ecx, edx
0x180025050  jle     short loc_180025064
0x180025052  mov     eax, ecx
0x180025054  sub     eax, edx
0x180025056  cmp     [rdi+9B8h], eax
0x18002505c  jle     short loc_180025064
0x18002505e  mov     [rdi+9B8h], eax
0x180025064  mov     eax, [rdi+9B8h]
0x18002506a  lea     r8, [rbp+57h+var_60]; lpsi
0x18002506e  mov     [rbp+57h+var_60.nPos], eax
0x180025071  mov     ebx, 1
0x180025076  mov     [rbp+57h+var_60.nTrackPos], 0
0x18002507d  mov     [rbp+57h+var_60.cbSize], 1Ch
0x180025084  mov     qword ptr [rbp+57h+var_60.fMask], 1Fh
0x18002508c  mov     [rbp+57h+var_60.nMax], ecx
0x18002508f  mov     [rbp+57h+var_60.nPage], r15d
0x180025093  mov     r9d, ebx; redraw
0x180025096  mov     edx, ebx; nBar
0x180025098  mov     rcx, r14; hwnd
0x18002509b  call    cs:__imp_SetScrollInfo
0x1800250a1  jmp     loc_180025160
0x1800250a6  xorps   xmm0, xmm0
0x1800250a9  lea     rdx, [rbp+57h+rc]; lpRect
0x1800250ad  mov     rcx, r14; hWnd
0x1800250b0  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x1800250b4  call    cs:__imp_GetClientRect
0x1800250ba  mov     eax, [rbp+57h+rc.right]
0x1800250bd  xor     ecx, ecx; hdc
0x1800250bf  sub     eax, [rbp+57h+rc.left]
0x1800250c2  mov     [rdi+9C0h], eax
0x1800250c8  mov     eax, [rbp+57h+rc.bottom]
0x1800250cb  sub     eax, [rbp+57h+rc.top]
0x1800250ce  mov     [rdi+9C4h], eax
0x1800250d4  call    cs:__imp_CreateCompatibleDC
0x1800250da  xor     r9d, r9d; int
0x1800250dd  mov     dword ptr [rdi+9B8h], 0
0x1800250e7  mov     rbx, rax
0x1800250ea  mov     rcx, rdi; this
0x1800250ed  lea     rax, [rbp+57h+rc]
0x1800250f1  mov     r8, rbx; HDC
0x1800250f4  mov     [rsp+110h+prcClip], rax; struct tagRECT *
0x1800250f9  call    ?RenderPreview@CFontPreview@@AEAAHPEAUHWND__@@PEAUHDC__@@HPEAUtagRECT@@@Z; CFontPreview::RenderPreview(HWND__ *,HDC__ *,int,tagRECT *)
0x1800250fe  mov     rcx, rbx; hdc
0x180025101  mov     [rdi+9C8h], eax
0x180025107  call    cs:__imp_DeleteDC
0x18002510d  mov     eax, [rdi+9C8h]
0x180025113  lea     r8, [rbp+57h+var_60]; lpsi
0x180025117  mov     [rbp+57h+var_60.nMax], eax
0x18002511a  mov     ebx, 1
0x18002511f  mov     eax, [rdi+9C4h]
0x180025125  mov     r9d, ebx; redraw
0x180025128  mov     [rbp+57h+var_60.nPage], eax
0x18002512b  mov     edx, ebx; nBar
0x18002512d  mov     eax, [rdi+9B8h]
0x180025133  mov     rcx, r14; hwnd
0x180025136  mov     [rbp+57h+var_60.nPos], eax
0x180025139  mov     [rbp+57h+var_60.nTrackPos], 0
0x180025140  mov     [rbp+57h+var_60.cbSize], 1Ch
0x180025147  mov     qword ptr [rbp+57h+var_60.fMask], 1Fh
0x18002514f  call    cs:__imp_SetScrollInfo
0x180025155  mov     rdx, r14; HWND
0x180025158  mov     rcx, rdi; this
0x18002515b  call    ?ShowOrHideVScroll@CFontPreview@@AEAAXPEAUHWND__@@@Z; CFontPreview::ShowOrHideVScroll(HWND__ *)
0x180025160  xor     ebx, ebx
0x180025162  jmp     short loc_180025179
0x180025164  mov     r9, rbx; lParam
0x180025167  mov     r8, r15; wParam
0x18002516a  mov     edx, r12d; Msg
0x18002516d  mov     rcx, r14; hWnd
0x180025170  call    cs:__imp_DefWindowProcW
0x180025176  mov     rbx, rax
0x180025179  mov     rax, rbx
0x18002517c  mov     rcx, [rbp+57h+var_40]
0x180025180  xor     rcx, rsp; StackCookie
0x180025183  call    __security_check_cookie
0x180025188  add     rsp, 0E8h
0x18002518f  pop     r15
0x180025191  pop     r14
0x180025193  pop     r12
0x180025195  pop     rdi
0x180025196  pop     rbx
0x180025197  pop     rbp
0x180025198  retn
```
