# ReaderMode_WndProc

- ea: `0x18011d4b0`
- end: `0x18011d931`
- name: `ReaderMode_WndProc`
- size: `1153`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180114520`
- `0x18011d254`
- `0x18011d4b0`
- `0x1801d1010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18011d5f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18011d6f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18011d5f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18011d6f3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18011d709`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18011d709`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18011d600`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18011d600`
- `GDI32!DeleteObject` at `0x18011d5ec`
- `GDI32!DeleteObject` at `0x18011d6da`
- `GDI32!DeleteObject` at `0x18011d6e3`
- `GDI32!DeleteObject` at `0x18011d5ec`
- `GDI32!DeleteObject` at `0x18011d6da`
- `GDI32!DeleteObject` at `0x18011d6e3`
- `GDI32!GetObjectW` at `0x18011d7c0`
- `GDI32!GetObjectW` at `0x18011d7c0`
- `GDI32!SelectObject` at `0x18011d627`
- `GDI32!SelectObject` at `0x18011d64d`
- `GDI32!SelectObject` at `0x18011d667`
- `GDI32!SelectObject` at `0x18011d6c5`
- `GDI32!SelectObject` at `0x18011d6d1`
- `GDI32!SelectObject` at `0x18011d627`
- `GDI32!SelectObject` at `0x18011d64d`
- `GDI32!SelectObject` at `0x18011d667`
- `GDI32!SelectObject` at `0x18011d6c5`
- `GDI32!SelectObject` at `0x18011d6d1`
- `GDI32!CreateCompatibleDC` at `0x18011d60e`
- `GDI32!CreateCompatibleDC` at `0x18011d60e`
- `GDI32!CreatePen` at `0x18011d635`
- `GDI32!CreatePen` at `0x18011d635`
- `GDI32!BitBlt` at `0x18011d6a0`
- `GDI32!BitBlt` at `0x18011d6a0`
- `GDI32!CreateEllipticRgn` at `0x18011d82b`
- `GDI32!CreateEllipticRgn` at `0x18011d82b`
- `GDI32!GetStockObject` at `0x18011d65b`
- `GDI32!GetStockObject` at `0x18011d65b`
- `GDI32!Ellipse` at `0x18011d6b9`
- `GDI32!Ellipse` at `0x18011d6b9`
- `USER32!SetWindowRgn` at `0x18011d83f`
- `USER32!SetWindowRgn` at `0x18011d83f`
- `USER32!LoadBitmapW` at `0x18011d7a1`
- `USER32!LoadBitmapW` at `0x18011d7a1`
- `USER32!SetWindowPos` at `0x18011d861`
- `USER32!SetWindowPos` at `0x18011d861`
- `USER32!SetTimer` at `0x18011d886`
- `USER32!SetTimer` at `0x18011d886`
- `USER32!SetFocus` at `0x18011d873`
- `USER32!SetFocus` at `0x18011d873`
- `USER32!SetCapture` at `0x18011d86a`
- `USER32!SetCapture` at `0x18011d86a`
- `USER32!SetWindowLongW` at `0x18011d782`
- `USER32!SetWindowLongW` at `0x18011d796`
- `USER32!SetWindowLongW` at `0x18011d782`
- `USER32!SetWindowLongW` at `0x18011d796`
- `USER32!KillTimer` at `0x18011d5c6`
- `USER32!KillTimer` at `0x18011d5c6`
- `USER32!ReleaseCapture` at `0x18011d90b`
- `USER32!ReleaseCapture` at `0x18011d90b`
- `USER32!GetCursorPos` at `0x18011d806`
- `USER32!GetCursorPos` at `0x18011d806`
- `USER32!DefWindowProcW` at `0x18011d8d2`
- `USER32!DefWindowProcW` at `0x18011d8d2`
- `USER32!DestroyWindow` at `0x18011d5b5`
- `USER32!DestroyWindow` at `0x18011d5b5`
- `USER32!SetWindowLongPtrW` at `0x18011d736`
- `USER32!SetWindowLongPtrW` at `0x18011d736`
- `USER32!GetWindowLongPtrW` at `0x18011d4f9`
- `USER32!GetWindowLongPtrW` at `0x18011d4f9`
- `USER32!GetClientRect` at `0x18011d8f3`
- `USER32!GetClientRect` at `0x18011d8f3`
- `USER32!PtInRect` at `0x18011d901`
- `USER32!PtInRect` at `0x18011d901`

## pseudocode

```c
LRESULT __fastcall ReaderMode_WndProc(HWND hWnd, UINT Msg, HDC wParam, _OWORD **lParam)
{
  LONG_PTR WindowLongPtrW; // rsi
  void *v9; // rcx
  HANDLE v10; // rax
  HDC CompatibleDC; // rax
  HDC hdcSrc; // r14
  HPEN Pen; // rax
  HPEN v14; // r12
  HGDIOBJ v15; // rdi
  HGDIOBJ StockObject; // rax
  HGDIOBJ v17; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v20; // rax
  _QWORD *v21; // rdi
  _OWORD *v22; // rcx
  __int64 v23; // rsi
  HBITMAP BitmapW; // rax
  int v25; // edi
  int v26; // esi
  HRGN EllipticRgn; // rax
  struct tagPOINT Point; // [rsp+50h] [rbp-19h] BYREF
  struct tagRECT pv[2]; // [rsp+58h] [rbp-11h] BYREF
  struct tagRECT Rect; // [rsp+78h] [rbp+Fh] BYREF

  Point = 0;
  Rect = 0;
  memset(pv, 0, sizeof(pv));
  WindowLongPtrW = GetWindowLongPtrW(hWnd, 0);
  if ( !WindowLongPtrW && Msg != 1 )
    return DefWindowProcW(hWnd, Msg, (WPARAM)wParam, (LPARAM)lParam);
  if ( Msg > 0x204 )
  {
    if ( Msg != 517 && Msg != 519 )
    {
      switch ( Msg )
      {
        case 0x208u:
          Point.x = (__int16)lParam;
          Point.y = SWORD1(lParam);
          GetClientRect(hWnd, &Rect);
          if ( PtInRect(&Rect, Point) )
            return 0;
          break;
        case 0x20Au:
        case 0x20Bu:
        case 0x20Cu:
        case 0x20Eu:
          break;
        case 0x215u:
          goto LABEL_16;
        default:
          return DefWindowProcW(hWnd, Msg, (WPARAM)wParam, (LPARAM)lParam);
      }
    }
LABEL_49:
    ReleaseCapture();
    return 0;
  }
  if ( Msg == 516 )
    goto LABEL_49;
  if ( Msg == 1 )
  {
    ProcessHeap = GetProcessHeap();
    v20 = HeapAlloc(ProcessHeap, 8u, 0x50u);
    v21 = v20;
    if ( !v20 )
      return -1;
    v22 = *lParam;
    *(_OWORD *)v20 = **lParam;
    v20[2] = *((_QWORD *)v22 + 2);
    SetWindowLongPtrW(hWnd, 0, (LONG_PTR)v20);
    if ( !v21[1] )
      return -1;
    if ( (*((_BYTE *)v21 + 4) & 3) == 3 )
    {
      v23 = 32661;
    }
    else if ( (*((_BYTE *)v21 + 4) & 1) != 0 )
    {
      v23 = 32559;
    }
    else
    {
      if ( (*((_BYTE *)v21 + 4) & 2) == 0 )
        return -1;
      v23 = 32660;
    }
    SetWindowLongW(hWnd, -20, 128);
    SetWindowLongW(hWnd, -16, -2080374784);
    BitmapW = LoadBitmapW(0, (LPCWSTR)v23);
    v21[8] = BitmapW;
    if ( BitmapW
      && GetObjectW(BitmapW, 32, pv)
      && ((unsigned int (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))v21[1])(v21[2], 1, 0, 0) )
    {
      v21[9] = *(_QWORD *)&pv[0].top;
      v25 = pv[0].top + 1;
      v26 = pv[0].right + 1;
      GetCursorPos(&Point);
      Point.x += v25 / -2;
      Point.y += v26 / -2;
      EllipticRgn = CreateEllipticRgn(0, 0, v25, v26);
      if ( EllipticRgn )
        SetWindowRgn(hWnd, EllipticRgn, 0);
      SetWindowPos(hWnd, HWND_MESSAGE|0x2LL, Point.x, Point.y, v25, v26, 0x50u);
      SetCapture(hWnd);
      SetFocus(hWnd);
      SetTimer(hWnd, 1u, 0xAu, 0);
      return 0;
    }
    return -1;
  }
  if ( Msg != 20 )
  {
    if ( Msg == 130 )
    {
      KillTimer(hWnd, 1u);
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(WindowLongPtrW + 8))(*(_QWORD *)(WindowLongPtrW + 16), 3, 0);
      v9 = *(void **)(WindowLongPtrW + 64);
      if ( v9 )
        DeleteObject(v9);
      v10 = GetProcessHeap();
      HeapFree(v10, 0, (LPVOID)WindowLongPtrW);
      return 0;
    }
    if ( Msg == 256 )
      goto LABEL_49;
    if ( Msg != 275 )
    {
      if ( Msg != 512 )
      {
        if ( Msg - 513 >= 2 )
          return DefWindowProcW(hWnd, Msg, (WPARAM)wParam, (LPARAM)lParam);
        goto LABEL_49;
      }
      ReaderMode_MouseMove(hWnd);
      return 0;
    }
    if ( !*(_QWORD *)(WindowLongPtrW + 48)
      || (*(unsigned int (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(WindowLongPtrW + 8))(
           *(_QWORD *)(WindowLongPtrW + 16),
           2,
           *(unsigned int *)(WindowLongPtrW + 48),
           *(unsigned int *)(WindowLongPtrW + 52)) )
    {
      return 0;
    }
LABEL_16:
    DestroyWindow(hWnd);
    return 0;
  }
  CompatibleDC = CreateCompatibleDC(wParam);
  hdcSrc = CompatibleDC;
  if ( !CompatibleDC )
    return 0;
  SelectObject(CompatibleDC, *(HGDIOBJ *)(WindowLongPtrW + 64));
  Pen = CreatePen(0, 1, 0);
  v14 = Pen;
  if ( Pen )
  {
    v15 = SelectObject(wParam, Pen);
    StockObject = GetStockObject(5);
    v17 = SelectObject(wParam, StockObject);
    BitBlt(wParam, 0, 0, *(_DWORD *)(WindowLongPtrW + 72), *(_DWORD *)(WindowLongPtrW + 76), hdcSrc, 0, 0, 0xCC0020u);
    Ellipse(wParam, 0, 0, *(_DWORD *)(WindowLongPtrW + 72), *(_DWORD *)(WindowLongPtrW + 76));
    SelectObject(wParam, v15);
    SelectObject(wParam, v17);
    DeleteObject(v14);
  }
  DeleteObject(hdcSrc);
  return 1;
}

```

## disassembly

```asm
0x18011d4b0  push    rbp
0x18011d4b2  push    rbx
0x18011d4b3  push    rsi
0x18011d4b4  push    rdi
0x18011d4b5  push    r12
0x18011d4b7  push    r14
0x18011d4b9  push    r15
0x18011d4bb  lea     rbp, [rsp-27h]
0x18011d4c0  sub     rsp, 90h
0x18011d4c7  mov     rax, cs:__security_cookie
0x18011d4ce  xor     rax, rsp
0x18011d4d1  mov     [rbp+57h+var_38], rax
0x18011d4d5  xorps   xmm0, xmm0
0x18011d4d8  mov     qword ptr [rbp+57h+Point.x], 0
0x18011d4e0  mov     edi, edx
0x18011d4e2  mov     r14, r9
0x18011d4e5  xor     edx, edx; nIndex
0x18011d4e7  mov     r15, r8
0x18011d4ea  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18011d4ee  mov     rbx, rcx
0x18011d4f1  movups  [rbp+57h+pv], xmm0
0x18011d4f5  movups  [rbp+57h+var_58], xmm0
0x18011d4f9  call    cs:__imp_GetWindowLongPtrW
0x18011d4ff  mov     rsi, rax
0x18011d502  mov     r12d, 1
0x18011d508  test    rax, rax
0x18011d50b  jnz     short loc_18011D516
0x18011d50d  cmp     edi, r12d
0x18011d510  jnz     loc_18011D8C7
0x18011d516  mov     eax, 204h
0x18011d51b  cmp     edi, eax
0x18011d51d  ja      loc_18011D897
0x18011d523  jz      loc_18011D90B
0x18011d529  mov     eax, edi
0x18011d52b  sub     eax, r12d
0x18011d52e  jz      loc_18011D6F3
0x18011d534  sub     eax, 13h
0x18011d537  jz      loc_18011D60B
0x18011d53d  sub     eax, 6Eh ; 'n'
0x18011d540  jz      short loc_18011D5C0
0x18011d542  sub     eax, 7Eh ; '~'
0x18011d545  jz      loc_18011D90B
0x18011d54b  sub     eax, 13h
0x18011d54e  jz      short loc_18011D581
0x18011d550  sub     eax, 0EDh
0x18011d555  jz      short loc_18011D56E
0x18011d557  sub     eax, r12d
0x18011d55a  jz      loc_18011D90B
0x18011d560  cmp     eax, r12d
0x18011d563  jz      loc_18011D90B
0x18011d569  jmp     loc_18011D8C7
0x18011d56e  mov     r8, r14
0x18011d571  mov     rdx, rsi
0x18011d574  mov     rcx, rbx; hWnd
0x18011d577  call    ReaderMode_MouseMove
0x18011d57c  jmp     loc_18011D911
0x18011d581  mov     r8d, [rsi+30h]
0x18011d585  test    r8d, r8d
0x18011d588  jnz     short loc_18011D594
0x18011d58a  cmp     [rsi+34h], r8d
0x18011d58e  jz      loc_18011D911
0x18011d594  mov     r9d, [rsi+34h]
0x18011d598  mov     edx, 2
0x18011d59d  mov     rcx, [rsi+10h]
0x18011d5a1  mov     rax, [rsi+8]
0x18011d5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011d5aa  test    eax, eax
0x18011d5ac  jnz     loc_18011D911
0x18011d5b2  mov     rcx, rbx; hWnd
0x18011d5b5  call    cs:__imp_DestroyWindow
0x18011d5bb  jmp     loc_18011D911
0x18011d5c0  mov     rdx, r12; uIDEvent
0x18011d5c3  mov     rcx, rbx; hWnd
0x18011d5c6  call    cs:__imp_KillTimer
0x18011d5cc  mov     rcx, [rsi+10h]
0x18011d5d0  xor     r9d, r9d
0x18011d5d3  mov     rax, [rsi+8]
0x18011d5d7  xor     r8d, r8d
0x18011d5da  lea     edx, [r9+3]
0x18011d5de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011d5e3  mov     rcx, [rsi+40h]; ho
0x18011d5e7  test    rcx, rcx
0x18011d5ea  jz      short loc_18011D5F2
0x18011d5ec  call    cs:__imp_DeleteObject
0x18011d5f2  call    cs:__imp_GetProcessHeap
0x18011d5f8  mov     r8, rsi; lpMem
0x18011d5fb  xor     edx, edx; dwFlags
0x18011d5fd  mov     rcx, rax; hHeap
0x18011d600  call    cs:__imp_HeapFree
0x18011d606  jmp     loc_18011D911
0x18011d60b  mov     rcx, r15; hdc
0x18011d60e  call    cs:__imp_CreateCompatibleDC
0x18011d614  mov     r14, rax
0x18011d617  test    rax, rax
0x18011d61a  jz      loc_18011D911
0x18011d620  mov     rdx, [rsi+40h]; h
0x18011d624  mov     rcx, rax; hdc
0x18011d627  call    cs:__imp_SelectObject
0x18011d62d  xor     r8d, r8d; color
0x18011d630  mov     edx, r12d; cWidth
0x18011d633  xor     ecx, ecx; iStyle
0x18011d635  call    cs:__imp_CreatePen
0x18011d63b  mov     r12, rax
0x18011d63e  test    rax, rax
0x18011d641  jz      loc_18011D6E0
0x18011d647  mov     rdx, rax; h
0x18011d64a  mov     rcx, r15; hdc
0x18011d64d  call    cs:__imp_SelectObject
0x18011d653  mov     ecx, 5; i
0x18011d658  mov     rdi, rax
0x18011d65b  call    cs:__imp_GetStockObject
0x18011d661  mov     rdx, rax; h
0x18011d664  mov     rcx, r15; hdc
0x18011d667  call    cs:__imp_SelectObject
0x18011d66d  mov     ecx, [rsi+4Ch]
0x18011d670  xor     r8d, r8d; y
0x18011d673  mov     r9d, [rsi+48h]; cx
0x18011d677  xor     edx, edx; x
0x18011d679  mov     [rsp+0C0h+rop], 0CC0020h; rop
0x18011d681  mov     rbx, rax
0x18011d684  mov     [rsp+0C0h+y1], 0; y1
0x18011d68c  mov     [rsp+0C0h+x1], 0; x1
0x18011d694  mov     [rsp+0C0h+hdcSrc], r14; hdcSrc
0x18011d699  mov     [rsp+0C0h+cy], ecx; cy
0x18011d69d  mov     rcx, r15; hdc
0x18011d6a0  call    cs:__imp_BitBlt
0x18011d6a6  mov     edx, [rsi+4Ch]
0x18011d6a9  xor     r8d, r8d; top
0x18011d6ac  mov     r9d, [rsi+48h]; right
0x18011d6b0  mov     rcx, r15; hdc
0x18011d6b3  mov     [rsp+0C0h+cy], edx; bottom
0x18011d6b7  xor     edx, edx; left
0x18011d6b9  call    cs:__imp_Ellipse
0x18011d6bf  mov     rdx, rdi; h
0x18011d6c2  mov     rcx, r15; hdc
0x18011d6c5  call    cs:__imp_SelectObject
0x18011d6cb  mov     rdx, rbx; h
0x18011d6ce  mov     rcx, r15; hdc
0x18011d6d1  call    cs:__imp_SelectObject
0x18011d6d7  mov     rcx, r12; ho
0x18011d6da  call    cs:__imp_DeleteObject
0x18011d6e0  mov     rcx, r14; ho
0x18011d6e3  call    cs:__imp_DeleteObject
0x18011d6e9  mov     eax, 1
0x18011d6ee  jmp     loc_18011D913
0x18011d6f3  call    cs:__imp_GetProcessHeap
0x18011d6f9  mov     r15d, 50h ; 'P'
0x18011d6ff  mov     rcx, rax; hHeap
0x18011d702  mov     r8d, r15d; dwBytes
0x18011d705  lea     edx, [r15-48h]; dwFlags
0x18011d709  call    cs:__imp_HeapAlloc
0x18011d70f  mov     rdi, rax
0x18011d712  test    rax, rax
0x18011d715  jz      loc_18011D891
0x18011d71b  mov     rcx, [r14]
0x18011d71e  mov     r8, rax; dwNewLong
0x18011d721  xor     edx, edx; nIndex
0x18011d723  movups  xmm0, xmmword ptr [rcx]
0x18011d726  movups  xmmword ptr [rax], xmm0
0x18011d729  movsd   xmm1, qword ptr [rcx+10h]
0x18011d72e  mov     rcx, rbx; hWnd
0x18011d731  movsd   qword ptr [rax+10h], xmm1
0x18011d736  call    cs:__imp_SetWindowLongPtrW
0x18011d73c  cmp     qword ptr [rdi+8], 0
0x18011d741  jz      loc_18011D891
0x18011d747  mov     eax, [rdi+4]
0x18011d74a  and     eax, 3
0x18011d74d  cmp     al, 3
0x18011d74f  jnz     short loc_18011D758
0x18011d751  mov     esi, 7F95h
0x18011d756  jmp     short loc_18011D774
0x18011d758  test    [rdi+4], r12b
0x18011d75c  jz      short loc_18011D765
0x18011d75e  mov     esi, 7F2Fh
0x18011d763  jmp     short loc_18011D774
0x18011d765  test    byte ptr [rdi+4], 2
0x18011d769  jz      loc_18011D891
0x18011d76f  mov     esi, 7F94h
0x18011d774  mov     edx, 0FFFFFFECh; nIndex
0x18011d779  mov     r8d, 80h; dwNewLong
0x18011d77f  mov     rcx, rbx; hWnd
0x18011d782  call    cs:__imp_SetWindowLongW
0x18011d788  mov     edx, 0FFFFFFF0h; nIndex
0x18011d78d  mov     r8d, 84000000h; dwNewLong
0x18011d793  mov     rcx, rbx; hWnd
0x18011d796  call    cs:__imp_SetWindowLongW
0x18011d79c  mov     rdx, rsi; lpBitmapName
0x18011d79f  xor     ecx, ecx; hInstance
0x18011d7a1  call    cs:__imp_LoadBitmapW
0x18011d7a7  mov     [rdi+40h], rax
0x18011d7ab  test    rax, rax
0x18011d7ae  jz      loc_18011D891
0x18011d7b4  lea     r8, [rbp+57h+pv]; pv
0x18011d7b8  mov     edx, 20h ; ' '; c
0x18011d7bd  mov     rcx, rax; h
0x18011d7c0  call    cs:__imp_GetObjectW
0x18011d7c6  test    eax, eax
0x18011d7c8  jz      loc_18011D891
0x18011d7ce  mov     rcx, [rdi+10h]
0x18011d7d2  xor     r9d, r9d
0x18011d7d5  mov     rax, [rdi+8]
0x18011d7d9  xor     r8d, r8d
0x18011d7dc  mov     edx, r12d
0x18011d7df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011d7e4  test    eax, eax
0x18011d7e6  jz      loc_18011D891
0x18011d7ec  mov     eax, dword ptr [rbp+57h+pv+4]
0x18011d7ef  lea     rcx, [rbp+57h+Point]; lpPoint
0x18011d7f3  mov     [rdi+48h], eax
0x18011d7f6  mov     eax, dword ptr [rbp+57h+pv+8]
0x18011d7f9  mov     [rdi+4Ch], eax
0x18011d7fc  mov     edi, dword ptr [rbp+57h+pv+4]
0x18011d7ff  mov     esi, dword ptr [rbp+57h+pv+8]
0x18011d802  inc     edi
0x18011d804  inc     esi
0x18011d806  call    cs:__imp_GetCursorPos
0x18011d80c  mov     ecx, 0FFFFFFFEh
0x18011d811  mov     eax, edi
0x18011d813  cdq
0x18011d814  mov     r9d, esi; y2
0x18011d817  idiv    ecx
0x18011d819  mov     r8d, edi; x2
0x18011d81c  add     [rbp+57h+Point.x], eax
0x18011d81f  mov     eax, esi
0x18011d821  cdq
0x18011d822  idiv    ecx
0x18011d824  xor     edx, edx; y1
0x18011d826  xor     ecx, ecx; x1
0x18011d828  add     [rbp+57h+Point.y], eax
0x18011d82b  call    cs:__imp_CreateEllipticRgn
0x18011d831  test    rax, rax
0x18011d834  jz      short loc_18011D845
0x18011d836  xor     r8d, r8d; bRedraw
0x18011d839  mov     rdx, rax; hRgn
0x18011d83c  mov     rcx, rbx; hWnd
0x18011d83f  call    cs:__imp_SetWindowRgn
0x18011d845  mov     r9d, [rbp+57h+Point.y]; Y
0x18011d849  or      rdx, 0FFFFFFFFFFFFFFFFh; hWndInsertAfter
0x18011d84d  mov     r8d, [rbp+57h+Point.x]; X
0x18011d851  mov     rcx, rbx; hWnd
0x18011d854  mov     [rsp+0C0h+x1], r15d; uFlags
0x18011d859  mov     dword ptr [rsp+0C0h+hdcSrc], esi; cy
0x18011d85d  mov     [rsp+0C0h+cy], edi; cx
0x18011d861  call    cs:__imp_SetWindowPos
0x18011d867  mov     rcx, rbx; hWnd
0x18011d86a  call    cs:__imp_SetCapture
0x18011d870  mov     rcx, rbx; hWnd
0x18011d873  call    cs:__imp_SetFocus
0x18011d879  xor     r9d, r9d; lpTimerFunc
0x18011d87c  mov     rdx, r12; nIDEvent
0x18011d87f  mov     rcx, rbx; hWnd
0x18011d882  lea     r8d, [r9+0Ah]; uElapse
0x18011d886  call    cs:__imp_SetTimer
0x18011d88c  jmp     loc_18011D911
0x18011d891  or      rax, 0FFFFFFFFFFFFFFFFh
0x18011d895  jmp     short loc_18011D913
0x18011d897  mov     eax, edi
0x18011d899  sub     eax, 205h
0x18011d89e  jz      short loc_18011D90B
0x18011d8a0  sub     eax, 2
0x18011d8a3  jz      short loc_18011D90B
0x18011d8a5  sub     eax, r12d
0x18011d8a8  jz      short loc_18011D8DA
0x18011d8aa  sub     eax, 2
0x18011d8ad  jz      short loc_18011D90B
0x18011d8af  sub     eax, r12d
0x18011d8b2  jz      short loc_18011D90B
0x18011d8b4  sub     eax, r12d
0x18011d8b7  jz      short loc_18011D90B
0x18011d8b9  sub     eax, 2
0x18011d8bc  jz      short loc_18011D90B
0x18011d8be  cmp     eax, 7
0x18011d8c1  jz      loc_18011D5B2
0x18011d8c7  mov     r9, r14; lParam
0x18011d8ca  mov     r8, r15; wParam
0x18011d8cd  mov     edx, edi; Msg
0x18011d8cf  mov     rcx, rbx; hWnd
0x18011d8d2  call    cs:__imp_DefWindowProcW
0x18011d8d8  jmp     short loc_18011D913
0x18011d8da  movsx   eax, r14w
0x18011d8de  lea     rdx, [rbp+57h+Rect]; lpRect
0x18011d8e2  mov     [rbp+57h+Point.x], eax
0x18011d8e5  mov     rcx, rbx; hWnd
0x18011d8e8  shr     r14, 10h
0x18011d8ec  movsx   eax, r14w
0x18011d8f0  mov     [rbp+57h+Point.y], eax
0x18011d8f3  call    cs:__imp_GetClientRect
0x18011d8f9  mov     rdx, qword ptr [rbp+57h+Point.x]; pt
0x18011d8fd  lea     rcx, [rbp+57h+Rect]; lprc
0x18011d901  call    cs:__imp_PtInRect
0x18011d907  test    eax, eax
0x18011d909  jnz     short loc_18011D911
0x18011d90b  call    cs:__imp_ReleaseCapture
0x18011d911  xor     eax, eax
0x18011d913  mov     rcx, [rbp+57h+var_38]
0x18011d917  xor     rcx, rsp; StackCookie
0x18011d91a  call    __security_check_cookie
0x18011d91f  add     rsp, 90h
0x18011d926  pop     r15
0x18011d928  pop     r14
  ... truncated ...
```
