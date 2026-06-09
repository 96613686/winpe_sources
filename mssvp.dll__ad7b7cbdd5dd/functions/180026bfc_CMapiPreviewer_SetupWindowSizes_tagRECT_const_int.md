# CMapiPreviewer::SetupWindowSizes(tagRECT const *,int)

- ea: `0x180026bfc`
- end: `0x180026f1b`
- name: `?SetupWindowSizes@CMapiPreviewer@@AEAAJPEBUtagRECT@@H@Z`
- size: `799`
- prototype: `int(CMapiPreviewer *__hidden this, const struct tagRECT *, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180023020`
- `0x180026980`
- `0x180026ac0`

## callees

- `0x180006270`
- `0x180026bfc`
- `0x18003d010`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x180026d2a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x180026d7b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x180026e0c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x180026eee`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x180026d2a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x180026d7b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x180026e0c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x180026eee`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180026d43`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180026d9f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180026d43`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180026d9f`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180026e3d`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180026e7c`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180026e3d`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180026e7c`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x180026c9d`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x180026c9d`
- `USER32!InvalidateRect` at `0x180026e52`
- `USER32!InvalidateRect` at `0x180026e91`
- `USER32!InvalidateRect` at `0x180026e52`
- `USER32!InvalidateRect` at `0x180026e91`

## pseudocode

```c
__int64 __fastcall CMapiPreviewer::SetupWindowSizes(CMapiPreviewer *this, const struct tagRECT *a2, int a3)
{
  BOOL v3; // ebx
  int v5; // r13d
  int *v6; // rsi
  int v7; // r12d
  __int64 v8; // rbp
  int v9; // r15d
  __int64 v10; // r14
  __int64 v11; // rbx
  HWND v12; // rcx
  int yBottom; // eax
  int v14; // r9d
  __int64 v15; // rcx
  unsigned int v16; // ebx
  HWND v17; // rcx
  struct tagRECT rc; // [rsp+40h] [rbp-58h] BYREF

  v3 = 0;
  if ( !a3 && *((_DWORD *)this + 32) == a2->left && *((_DWORD *)this + 34) == a2->right )
    v3 = *((_DWORD *)this + 33) == a2->top;
  v5 = *((_DWORD *)this + 35);
  v6 = (int *)((char *)this + 144);
  v7 = *((_DWORD *)this + 34);
  *((struct tagRECT *)this + 8) = *a2;
  if ( v3 )
  {
    *((_DWORD *)this + 39) = a2->bottom;
  }
  else
  {
    *(struct tagRECT *)v6 = *a2;
    *v6 += 8;
    if ( *((_DWORD *)this + 38) < *v6 )
      *((_DWORD *)this + 38) = *v6;
  }
  if ( a3 || !IsRectEmpty(a2) && !v3 )
  {
    v8 = 0;
    *((_DWORD *)this + 68) = 1;
    if ( *((_DWORD *)this + 298) )
    {
      do
      {
        v9 = *((_DWORD *)this + 32) + 8;
        v10 = 56LL * (unsigned int)v8;
        if ( *(_QWORD *)((char *)this + v10 + 320) )
          v9 += *((_DWORD *)this + 299);
        v11 = 56 * (v8 + 6);
        SetWindowPos(
          *(HWND *)((char *)this + v10 + 296),
          0,
          v9,
          *(_DWORD *)((char *)this + v11),
          *((_DWORD *)this + 34) - v9,
          2 * *(_DWORD *)((char *)this + v10 + 344),
          0x1Cu);
        SendMessageW(*(HWND *)((char *)this + v10 + 296), 0x441u, 0, 0);
        SetWindowPos(
          *(HWND *)((char *)this + v10 + 296),
          0,
          v9,
          *(_DWORD *)((char *)this + v11),
          *((_DWORD *)this + 34) - v9,
          *(_DWORD *)((char *)this + v10 + 340),
          0x14u);
        if ( *(_DWORD *)((char *)this + v10 + 348) )
          SendMessageW(*(HWND *)((char *)this + v10 + 296), 0x460u, 1u, 1);
        v8 = (unsigned int)(v8 + 1);
      }
      while ( (unsigned int)v8 < *((_DWORD *)this + 298) );
      v6 = (int *)((char *)this + 144);
    }
    *((_DWORD *)this + 68) = 0;
  }
  v12 = (HWND)*((_QWORD *)this + 21);
  if ( v12 )
  {
    SetWindowPos(
      v12,
      0,
      *((_DWORD *)this + 32),
      *((_DWORD *)this + 33),
      *((_DWORD *)this + 34) - *((_DWORD *)this + 32),
      *((_DWORD *)this + 35) - *((_DWORD *)this + 33),
      0x14u);
    yBottom = *((_DWORD *)this + 35);
    rc = 0;
    if ( yBottom > v5 )
    {
      SetRect(&rc, *((_DWORD *)this + 32), v5, 8, yBottom);
      InvalidateRect(*((HWND *)this + 21), &rc, 1);
    }
    v14 = *((_DWORD *)this + 34);
    if ( v14 > v7 )
    {
      SetRect(&rc, v7, 0, v14, *((_DWORD *)this + 37) - 1);
      InvalidateRect(*((HWND *)this + 21), &rc, 1);
    }
  }
  v15 = *((_QWORD *)this + 13);
  if ( v15 )
  {
    return (*(unsigned int (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 32LL))(v15, v6);
  }
  else
  {
    v17 = (HWND)*((_QWORD *)this + 22);
    v16 = 0;
    if ( v17 )
      SetWindowPos(
        v17,
        0,
        *v6,
        *((_DWORD *)this + 37),
        *((_DWORD *)this + 38) - *v6,
        *((_DWORD *)this + 39) - *((_DWORD *)this + 37),
        0x14u);
  }
  return v16;
}

```

## disassembly

```asm
0x180026bfc  mov     [rsp+arg_10], rbx
0x180026c01  push    rbp
0x180026c02  push    rsi
0x180026c03  push    rdi
0x180026c04  push    r12
0x180026c06  push    r13
0x180026c08  push    r14
0x180026c0a  push    r15
0x180026c0c  sub     rsp, 60h
0x180026c10  mov     rax, cs:__security_cookie
0x180026c17  xor     rax, rsp
0x180026c1a  mov     [rsp+98h+var_48], rax
0x180026c1f  xor     ebx, ebx
0x180026c21  mov     rdi, rcx
0x180026c24  lea     r14d, [rbx+1]
0x180026c28  test    r8d, r8d
0x180026c2b  jnz     short loc_180026C4F
0x180026c2d  mov     eax, [rdx]
0x180026c2f  cmp     [rcx+80h], eax
0x180026c35  jnz     short loc_180026C4F
0x180026c37  mov     eax, [rdx+8]
0x180026c3a  cmp     [rcx+88h], eax
0x180026c40  jnz     short loc_180026C4F
0x180026c42  mov     eax, [rdx+4]
0x180026c45  cmp     [rcx+84h], eax
0x180026c4b  cmovz   ebx, r14d
0x180026c4f  mov     r13d, [rcx+8Ch]
0x180026c56  lea     rsi, [rcx+90h]
0x180026c5d  mov     r12d, [rcx+88h]
0x180026c64  movups  xmm0, xmmword ptr [rdx]
0x180026c67  movdqu  xmmword ptr [rcx+80h], xmm0
0x180026c6f  test    ebx, ebx
0x180026c71  jz      short loc_180026C7B
0x180026c73  mov     eax, [rdx+0Ch]
0x180026c76  mov     [rsi+0Ch], eax
0x180026c79  jmp     short loc_180026C95
0x180026c7b  movups  xmm0, xmmword ptr [rdx]
0x180026c7e  movdqu  xmmword ptr [rsi], xmm0
0x180026c82  add     dword ptr [rsi], 8
0x180026c85  mov     eax, [rsi]
0x180026c87  cmp     [rcx+98h], eax
0x180026c8d  jge     short loc_180026C95
0x180026c8f  mov     [rcx+98h], eax
0x180026c95  test    r8d, r8d
0x180026c98  jnz     short loc_180026CB3
0x180026c9a  mov     rcx, rdx; lprc
0x180026c9d  call    cs:__imp_IsRectEmpty
0x180026ca3  test    eax, eax
0x180026ca5  jnz     loc_180026DCA
0x180026cab  test    ebx, ebx
0x180026cad  jnz     loc_180026DCA
0x180026cb3  xor     ebp, ebp
0x180026cb5  mov     [rdi+110h], r14d
0x180026cbc  cmp     [rdi+4A8h], ebp
0x180026cc2  jbe     loc_180026DC0
0x180026cc8  mov     rsi, r14
0x180026ccb  mov     r15d, [rdi+80h]
0x180026cd2  mov     ecx, ebp
0x180026cd4  add     r15d, 8
0x180026cd8  imul    r14, rcx, 38h ; '8'
0x180026cdc  cmp     qword ptr [r14+rdi+140h], 0
0x180026ce5  jz      short loc_180026CEE
0x180026ce7  add     r15d, [rdi+4ACh]
0x180026cee  mov     ecx, [r14+rdi+158h]
0x180026cf6  lea     rax, [rbp+6]
0x180026cfa  imul    rbx, rax, 38h ; '8'
0x180026cfe  mov     eax, [rdi+88h]
0x180026d04  add     ecx, ecx
0x180026d06  mov     [rsp+98h+uFlags], 1Ch; uFlags
0x180026d0e  sub     eax, r15d
0x180026d11  mov     [rsp+98h+cy], ecx; cy
0x180026d15  mov     r8d, r15d; X
0x180026d18  mov     rcx, [r14+rdi+128h]; hWnd
0x180026d20  xor     edx, edx; hWndInsertAfter
0x180026d22  mov     r9d, [rbx+rdi]; Y
0x180026d26  mov     [rsp+98h+yBottom], eax; cx
0x180026d2a  call    cs:__imp_SetWindowPos
0x180026d30  mov     rcx, [r14+rdi+128h]; hWnd
0x180026d38  xor     r9d, r9d; lParam
0x180026d3b  xor     r8d, r8d; wParam
0x180026d3e  mov     edx, 441h; Msg
0x180026d43  call    cs:__imp_SendMessageW
0x180026d49  mov     ecx, [rdi+88h]
0x180026d4f  mov     r8d, r15d; X
0x180026d52  mov     eax, [r14+rdi+154h]
0x180026d5a  sub     ecx, r15d
0x180026d5d  mov     r9d, [rbx+rdi]; Y
0x180026d61  xor     edx, edx; hWndInsertAfter
0x180026d63  mov     [rsp+98h+uFlags], 14h; uFlags
0x180026d6b  mov     [rsp+98h+cy], eax; cy
0x180026d6f  mov     [rsp+98h+yBottom], ecx; cx
0x180026d73  mov     rcx, [r14+rdi+128h]; hWnd
0x180026d7b  call    cs:__imp_SetWindowPos
0x180026d81  cmp     dword ptr [r14+rdi+15Ch], 0
0x180026d8a  jz      short loc_180026DA5
0x180026d8c  mov     rcx, [r14+rdi+128h]; hWnd
0x180026d94  mov     r9, rsi; lParam
0x180026d97  mov     r8, rsi; wParam
0x180026d9a  mov     edx, 460h; Msg
0x180026d9f  call    cs:__imp_SendMessageW
0x180026da5  add     ebp, esi
0x180026da7  cmp     ebp, [rdi+4A8h]
0x180026dad  jb      loc_180026CCB
0x180026db3  lea     rsi, [rdi+90h]
0x180026dba  mov     r14d, 1
0x180026dc0  mov     dword ptr [rdi+110h], 0
0x180026dca  mov     rcx, [rdi+0A8h]; hWnd
0x180026dd1  test    rcx, rcx
0x180026dd4  jz      loc_180026E97
0x180026dda  mov     edx, [rdi+8Ch]
0x180026de0  mov     r9d, [rdi+84h]; Y
0x180026de7  sub     edx, r9d
0x180026dea  mov     eax, [rdi+88h]
0x180026df0  mov     r8d, [rdi+80h]; X
0x180026df7  sub     eax, r8d
0x180026dfa  mov     [rsp+98h+uFlags], 14h; uFlags
0x180026e02  mov     [rsp+98h+cy], edx; cy
0x180026e06  xor     edx, edx; hWndInsertAfter
0x180026e08  mov     [rsp+98h+yBottom], eax; cx
0x180026e0c  call    cs:__imp_SetWindowPos
0x180026e12  mov     eax, [rdi+8Ch]
0x180026e18  xorps   xmm0, xmm0
0x180026e1b  movups  xmmword ptr [rsp+98h+rc.left], xmm0
0x180026e20  cmp     eax, r13d
0x180026e23  jle     short loc_180026E58
0x180026e25  mov     edx, [rdi+80h]; xLeft
0x180026e2b  lea     rcx, [rsp+98h+rc]; lprc
0x180026e30  mov     r9d, 8; xRight
0x180026e36  mov     [rsp+98h+yBottom], eax; yBottom
0x180026e3a  mov     r8d, r13d; yTop
0x180026e3d  call    cs:__imp_SetRect
0x180026e43  mov     rcx, [rdi+0A8h]; hWnd
0x180026e4a  lea     rdx, [rsp+98h+rc]; lpRect
0x180026e4f  mov     r8d, r14d; bErase
0x180026e52  call    cs:__imp_InvalidateRect
0x180026e58  mov     r9d, [rdi+88h]; xRight
0x180026e5f  cmp     r9d, r12d
0x180026e62  jle     short loc_180026E97
0x180026e64  mov     eax, [rdi+94h]
0x180026e6a  lea     rcx, [rsp+98h+rc]; lprc
0x180026e6f  sub     eax, r14d
0x180026e72  xor     r8d, r8d; yTop
0x180026e75  mov     edx, r12d; xLeft
0x180026e78  mov     [rsp+98h+yBottom], eax; yBottom
0x180026e7c  call    cs:__imp_SetRect
0x180026e82  mov     rcx, [rdi+0A8h]; hWnd
0x180026e89  lea     rdx, [rsp+98h+rc]; lpRect
0x180026e8e  mov     r8d, r14d; bErase
0x180026e91  call    cs:__imp_InvalidateRect
0x180026e97  mov     rcx, [rdi+68h]
0x180026e9b  test    rcx, rcx
0x180026e9e  jz      short loc_180026EB3
0x180026ea0  mov     rax, [rcx]
0x180026ea3  mov     rdx, rsi
0x180026ea6  mov     rax, [rax+20h]
0x180026eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026eaf  mov     ebx, eax
0x180026eb1  jmp     short loc_180026EF4
0x180026eb3  mov     rcx, [rdi+0B0h]; hWnd
0x180026eba  xor     ebx, ebx
0x180026ebc  test    rcx, rcx
0x180026ebf  jz      short loc_180026EF4
0x180026ec1  mov     edx, [rdi+9Ch]
0x180026ec7  mov     r9d, [rdi+94h]; Y
0x180026ece  sub     edx, r9d
0x180026ed1  mov     eax, [rdi+98h]
0x180026ed7  sub     eax, [rsi]
0x180026ed9  mov     r8d, [rsi]; X
0x180026edc  mov     [rsp+98h+uFlags], 14h; uFlags
0x180026ee4  mov     [rsp+98h+cy], edx; cy
0x180026ee8  xor     edx, edx; hWndInsertAfter
0x180026eea  mov     [rsp+98h+yBottom], eax; cx
0x180026eee  call    cs:__imp_SetWindowPos
0x180026ef4  mov     eax, ebx
0x180026ef6  mov     rcx, [rsp+98h+var_48]
0x180026efb  xor     rcx, rsp; StackCookie
0x180026efe  call    __security_check_cookie
0x180026f03  mov     rbx, [rsp+98h+arg_10]
0x180026f0b  add     rsp, 60h
0x180026f0f  pop     r15
0x180026f11  pop     r14
0x180026f13  pop     r13
0x180026f15  pop     r12
0x180026f17  pop     rdi
0x180026f18  pop     rsi
0x180026f19  pop     rbp
0x180026f1a  retn
```
