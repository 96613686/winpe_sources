# CGhostWindow::FrostBitmap(void)

- ea: `0x180006538`
- end: `0x18000677d`
- name: `?FrostBitmap@CGhostWindow@@IEAAHXZ`
- size: `581`
- prototype: `__int64 __fastcall(CGhostWindow *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005910`
- `0x180006bb8`
- `0x180007280`
- `0x18000a080`

## callees

- `0x180001190`
- `0x180006538`
- `0x18000a0b4`

## import_xrefs

- `USER32!UpdateWindow` at `0x180006755`
- `USER32!UpdateWindow` at `0x180006755`
- `USER32!InvalidateRect` at `0x18000674b`
- `USER32!InvalidateRect` at `0x18000674b`
- `GDI32!SelectObject` at `0x180006646`
- `GDI32!SelectObject` at `0x18000669f`
- `GDI32!SelectObject` at `0x1800066f7`
- `GDI32!SelectObject` at `0x18000670c`
- `GDI32!SelectObject` at `0x180006646`
- `GDI32!SelectObject` at `0x18000669f`
- `GDI32!SelectObject` at `0x1800066f7`
- `GDI32!SelectObject` at `0x18000670c`
- `GDI32!CreateCompatibleDC` at `0x18000660a`
- `GDI32!CreateCompatibleDC` at `0x180006687`
- `GDI32!CreateCompatibleDC` at `0x18000660a`
- `GDI32!CreateCompatibleDC` at `0x180006687`
- `GDI32!GdiAlphaBlend` at `0x1800066e5`
- `GDI32!GdiAlphaBlend` at `0x1800066e5`
- `GDI32!GetStockObject` at `0x180006667`
- `GDI32!GetStockObject` at `0x180006667`
- `GDI32!DeleteDC` at `0x180006700`
- `GDI32!DeleteDC` at `0x180006738`
- `GDI32!DeleteDC` at `0x180006700`
- `GDI32!DeleteDC` at `0x180006738`
- `GDI32!DeleteObject` at `0x18000671d`
- `GDI32!DeleteObject` at `0x18000672f`
- `GDI32!DeleteObject` at `0x18000671d`
- `GDI32!DeleteObject` at `0x18000672f`
- `ext-ms-win-ntuser-gui-l1-1-0!FillRect` at `0x180006677`
- `ext-ms-win-ntuser-gui-l1-1-0!FillRect` at `0x180006677`
- `ext-ms-win-ntuser-window-l1-1-2!SetTimer` at `0x1800065ac`
- `ext-ms-win-ntuser-window-l1-1-2!SetTimer` at `0x1800065ac`
- `dwmapi!DwmUpdateThumbnailProperties` at `0x1800065eb`
- `dwmapi!DwmUpdateThumbnailProperties` at `0x1800065eb`

## pseudocode

```c
__int64 __fastcall CGhostWindow::FrostBitmap(CGhostWindow *this)
{
  unsigned int v2; // esi
  UINT_PTR v3; // rax
  void *v4; // rcx
  HDC CompatibleDC; // r14
  void *AlphaBitmap; // rax
  void *v7; // r15
  HGDIOBJ v8; // r13
  HBRUSH StockObject; // rax
  HDC v10; // rax
  HDC hdcSrc; // r12
  HGDIOBJ v12; // rbx
  RECT rc; // [rsp+68h] [rbp-31h] BYREF
  DWM_THUMBNAIL_PROPERTIES ptnProperties; // [rsp+78h] [rbp-21h] BYREF

  v2 = 0;
  if ( !*((_DWORD *)this + 53) && !*((_DWORD *)this + 51) && !*((_DWORD *)this + 52) )
  {
    *((_DWORD *)this + 53) = 1;
    if ( *((_QWORD *)this + 18) )
    {
      v3 = SetTimer(*((HWND *)this + 6), 0x64u, 0x14u, 0);
      *((_QWORD *)this + 20) = v3;
      if ( v3
        || (v4 = (void *)*((_QWORD *)this + 18),
            memset(&ptnProperties.rcDestination.bottom, 0, 29),
            ptnProperties.opacity = 100,
            *(_OWORD *)&ptnProperties.dwFlags = 0,
            ptnProperties.dwFlags = 4,
            DwmUpdateThumbnailProperties(v4, &ptnProperties) >= 0) )
      {
        v2 = 1;
LABEL_19:
        InvalidateRect(*((HWND *)this + 6), 0, 0);
        UpdateWindow(*((HWND *)this + 6));
      }
    }
    else if ( *((_QWORD *)this + 17) )
    {
      CompatibleDC = CreateCompatibleDC(0);
      if ( CompatibleDC )
      {
        AlphaBitmap = (void *)CreateAlphaBitmap(*((unsigned int *)this + 43), *((unsigned int *)this + 44));
        v7 = AlphaBitmap;
        if ( AlphaBitmap )
        {
          rc = 0;
          *(_QWORD *)&rc.left = 0;
          v8 = SelectObject(CompatibleDC, AlphaBitmap);
          rc.right = *((_DWORD *)this + 43);
          rc.bottom = *((_DWORD *)this + 44);
          StockObject = (HBRUSH)GetStockObject(0);
          if ( FillRect(CompatibleDC, &rc, StockObject) )
          {
            v10 = CreateCompatibleDC(0);
            hdcSrc = v10;
            if ( v10 )
            {
              v12 = SelectObject(v10, *((HGDIOBJ *)this + 17));
              LOBYTE(v2) = GdiAlphaBlend(
                             CompatibleDC,
                             0,
                             0,
                             *((_DWORD *)this + 43),
                             *((_DWORD *)this + 44),
                             hdcSrc,
                             0,
                             0,
                             *((_DWORD *)this + 43),
                             *((_DWORD *)this + 44),
                             (BLENDFUNCTION)6553600);
              SelectObject(hdcSrc, v12);
              DeleteDC(hdcSrc);
            }
          }
          SelectObject(CompatibleDC, v8);
          if ( v2 )
          {
            DeleteObject(*((HGDIOBJ *)this + 17));
            *((_QWORD *)this + 17) = v7;
          }
          else
          {
            DeleteObject(v7);
          }
        }
        DeleteDC(CompatibleDC);
        if ( v2 )
          goto LABEL_19;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180006538  push    rbp
0x18000653a  push    rbx
0x18000653b  push    rsi
0x18000653c  push    rdi
0x18000653d  push    r12
0x18000653f  push    r13
0x180006541  push    r14
0x180006543  push    r15
0x180006545  lea     rbp, [rsp-1Fh]
0x18000654a  sub     rsp, 0B8h
0x180006551  mov     rax, cs:__security_cookie
0x180006558  xor     rax, rsp
0x18000655b  mov     [rbp+57h+var_48], rax
0x18000655f  xor     ebx, ebx
0x180006561  mov     rdi, rcx
0x180006564  mov     esi, ebx
0x180006566  cmp     [rcx+0D4h], ebx
0x18000656c  jnz     loc_18000675B
0x180006572  cmp     [rcx+0CCh], ebx
0x180006578  jnz     loc_18000675B
0x18000657e  cmp     [rcx+0D0h], ebx
0x180006584  jnz     loc_18000675B
0x18000658a  lea     r14d, [rbx+1]
0x18000658e  mov     [rcx+0D4h], r14d
0x180006595  cmp     [rcx+90h], rbx
0x18000659c  jz      short loc_1800065FB
0x18000659e  mov     rcx, [rcx+30h]; hWnd
0x1800065a2  lea     edx, [rbx+64h]; nIDEvent
0x1800065a5  xor     r9d, r9d; lpTimerFunc
0x1800065a8  lea     r8d, [rbx+14h]; uElapse
0x1800065ac  call    cs:__imp_SetTimer
0x1800065b2  mov     [rdi+0A0h], rax
0x1800065b9  test    rax, rax
0x1800065bc  jz      short loc_1800065C6
0x1800065be  mov     esi, r14d
0x1800065c1  jmp     loc_180006742
0x1800065c6  mov     rcx, [rdi+90h]; hThumbnailId
0x1800065cd  lea     rdx, [rbp+57h+ptnProperties]; ptnProperties
0x1800065d1  xorps   xmm0, xmm0
0x1800065d4  movups  xmmword ptr [rbp+57h+ptnProperties.rcDestination.bottom], xmm0
0x1800065d8  movups  xmmword ptr [rbp+57h+ptnProperties.rcSource.right+1], xmm0
0x1800065dc  mov     [rbp+57h+ptnProperties.opacity], 64h ; 'd'
0x1800065e0  movups  xmmword ptr [rbp+57h+ptnProperties.dwFlags], xmm0
0x1800065e4  mov     [rbp+57h+ptnProperties.dwFlags], 4
0x1800065eb  call    cs:__imp_DwmUpdateThumbnailProperties
0x1800065f1  test    eax, eax
0x1800065f3  js      loc_18000675B
0x1800065f9  jmp     short loc_1800065BE
0x1800065fb  cmp     [rcx+88h], rbx
0x180006602  jz      loc_18000675B
0x180006608  xor     ecx, ecx; hdc
0x18000660a  call    cs:__imp_CreateCompatibleDC
0x180006610  mov     r14, rax
0x180006613  test    rax, rax
0x180006616  jz      loc_18000675B
0x18000661c  mov     edx, [rdi+0B0h]
0x180006622  mov     ecx, [rdi+0ACh]
0x180006628  call    CreateAlphaBitmap
0x18000662d  mov     r15, rax
0x180006630  test    rax, rax
0x180006633  jz      loc_180006735
0x180006639  xorps   xmm0, xmm0
0x18000663c  mov     rdx, rax; h
0x18000663f  mov     rcx, r14; hdc
0x180006642  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x180006646  call    cs:__imp_SelectObject
0x18000664c  xor     ecx, ecx; i
0x18000664e  mov     qword ptr [rbp+57h+rc.left], rbx
0x180006652  mov     r13, rax
0x180006655  mov     eax, [rdi+0ACh]
0x18000665b  mov     [rbp+57h+rc.right], eax
0x18000665e  mov     eax, [rdi+0B0h]
0x180006664  mov     [rbp+57h+rc.bottom], eax
0x180006667  call    cs:__imp_GetStockObject
0x18000666d  lea     rdx, [rbp+57h+rc]; lprc
0x180006671  mov     rcx, r14; hDC
0x180006674  mov     r8, rax; hbr
0x180006677  call    cs:__imp_FillRect
0x18000667d  test    eax, eax
0x18000667f  jz      loc_180006706
0x180006685  xor     ecx, ecx; hdc
0x180006687  call    cs:__imp_CreateCompatibleDC
0x18000668d  mov     r12, rax
0x180006690  test    rax, rax
0x180006693  jz      short loc_180006706
0x180006695  mov     rdx, [rdi+88h]; h
0x18000669c  mov     rcx, rax; hdc
0x18000669f  call    cs:__imp_SelectObject
0x1800066a5  mov     ecx, [rdi+0B0h]
0x1800066ab  xor     r8d, r8d; yoriginDest
0x1800066ae  mov     r9d, [rdi+0ACh]; wDest
0x1800066b5  mov     rbx, rax
0x1800066b8  mov     dword ptr [rbp+57h+var_90.BlendOp], 640000h
0x1800066bf  xor     edx, edx; xoriginDest
0x1800066c1  mov     eax, dword ptr [rbp+57h+var_90.BlendOp]
0x1800066c4  mov     dword ptr [rsp+0F0h+ftn.BlendOp], eax; ftn
0x1800066c8  mov     [rsp+0F0h+hSrc], ecx; hSrc
0x1800066cc  mov     [rsp+0F0h+wSrc], r9d; wSrc
0x1800066d1  mov     [rsp+0F0h+yoriginSrc], esi; yoriginSrc
0x1800066d5  mov     [rsp+0F0h+xoriginSrc], esi; xoriginSrc
0x1800066d9  mov     [rsp+0F0h+hdcSrc], r12; hdcSrc
0x1800066de  mov     [rsp+0F0h+hDest], ecx; hDest
0x1800066e2  mov     rcx, r14; hdcDest
0x1800066e5  call    cs:__imp_GdiAlphaBlend
0x1800066eb  mov     rdx, rbx; h
0x1800066ee  mov     rcx, r12; hdc
0x1800066f1  test    eax, eax
0x1800066f3  setnz   sil
0x1800066f7  call    cs:__imp_SelectObject
0x1800066fd  mov     rcx, r12; hdc
0x180006700  call    cs:__imp_DeleteDC
0x180006706  mov     rdx, r13; h
0x180006709  mov     rcx, r14; hdc
0x18000670c  call    cs:__imp_SelectObject
0x180006712  test    esi, esi
0x180006714  jz      short loc_18000672C
0x180006716  mov     rcx, [rdi+88h]; ho
0x18000671d  call    cs:__imp_DeleteObject
0x180006723  mov     [rdi+88h], r15
0x18000672a  jmp     short loc_180006735
0x18000672c  mov     rcx, r15; ho
0x18000672f  call    cs:__imp_DeleteObject
0x180006735  mov     rcx, r14; hdc
0x180006738  call    cs:__imp_DeleteDC
0x18000673e  test    esi, esi
0x180006740  jz      short loc_18000675B
0x180006742  mov     rcx, [rdi+30h]; hWnd
0x180006746  xor     r8d, r8d; bErase
0x180006749  xor     edx, edx; lpRect
0x18000674b  call    cs:__imp_InvalidateRect
0x180006751  mov     rcx, [rdi+30h]; hWnd
0x180006755  call    cs:__imp_UpdateWindow
0x18000675b  mov     eax, esi
0x18000675d  mov     rcx, [rbp+57h+var_48]
0x180006761  xor     rcx, rsp; StackCookie
0x180006764  call    __security_check_cookie
0x180006769  add     rsp, 0B8h
0x180006770  pop     r15
0x180006772  pop     r14
0x180006774  pop     r13
0x180006776  pop     r12
0x180006778  pop     rdi
0x180006779  pop     rsi
0x18000677a  pop     rbx
0x18000677b  pop     rbp
0x18000677c  retn
```
