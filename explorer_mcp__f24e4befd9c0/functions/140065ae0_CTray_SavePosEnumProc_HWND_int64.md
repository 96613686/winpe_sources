# CTray::SavePosEnumProc(HWND__ *,__int64)

- ea: `0x140065ae0`
- end: `0x140065d51`
- name: `?SavePosEnumProc@CTray@@KAHPEAUHWND__@@_J@Z`
- size: `625`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140021280`
- `0x140065ae0`
- `0x14010e160`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-rtcore-ntuser-private-l1-1-0!GetWindowBand` at `0x140065b0f`
- `api-ms-win-rtcore-ntuser-private-l1-1-0!GetWindowBand` at `0x140065b0f`
- `api-ms-win-ntuser-rectangle-l1-1-0!IntersectRect` at `0x140065c95`
- `api-ms-win-ntuser-rectangle-l1-1-0!IntersectRect` at `0x140065c95`
- `GDI32!CreateRectRgn` at `0x140065c2f`
- `GDI32!CreateRectRgn` at `0x140065c2f`
- `GDI32!SetRectRgn` at `0x140065cb6`
- `GDI32!SetRectRgn` at `0x140065cb6`
- `GDI32!OffsetRgn` at `0x140065c7b`
- `GDI32!OffsetRgn` at `0x140065c7b`
- `GDI32!DeleteObject` at `0x140065d23`
- `GDI32!DeleteObject` at `0x140065d23`
- `GDI32!CombineRgn` at `0x140065cd2`
- `GDI32!CombineRgn` at `0x140065d14`
- `GDI32!CombineRgn` at `0x140065cd2`
- `GDI32!CombineRgn` at `0x140065d14`
- `ext-ms-win-ntuser-draw-l1-1-2!GetWindowRgn` at `0x140065c60`
- `ext-ms-win-ntuser-draw-l1-1-2!GetWindowRgn` at `0x140065c60`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindowVisible` at `0x140065b2d`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindowVisible` at `0x140065b2d`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowRect` at `0x140065c4a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowRect` at `0x140065c4a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowLongW` at `0x140065cf2`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowLongW` at `0x140065cf2`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-1!GetWindowPlacement` at `0x140065b9d`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-1!GetWindowPlacement` at `0x140065b9d`

## pseudocode

```c
__int64 __fastcall CTray::SavePosEnumProc(HWND a1, __int64 a2)
{
  void (__fastcall *v5)(__int64, __int64, __int128 *); // rax
  __int64 v6; // rbx
  HRGN RectRgn; // rsi
  int v8; // [rsp+30h] [rbp-19h] BYREF
  __int128 v9; // [rsp+38h] [rbp-11h] BYREF
  __int128 wndpl_4; // [rsp+48h] [rbp-1h]
  __int128 wndpl_20; // [rsp+58h] [rbp+Fh]
  __int64 wndpl_36; // [rsp+68h] [rbp+1Fh]
  struct tagRECT Rect; // [rsp+70h] [rbp+27h] BYREF

  v8 = 0;
  if ( (unsigned int)GetWindowBand(a1, &v8)
    && ((unsigned int)(v8 - 1) <= 1 || v8 == 16)
    && IsWindowVisible(a1)
    && (!*(_QWORD *)(a2 + 16) || v8 == 1)
    && a1 != *(HWND *)a2
    && a1 != v_hwndDesktop )
  {
    v9 = 0;
    HIDWORD(v9) = 44;
    wndpl_4 = 0;
    wndpl_36 = 0;
    wndpl_20 = 0;
    GetWindowPlacement(a1, (WINDOWPLACEMENT *)((char *)&v9 + 12));
    if ( DWORD1(wndpl_4) != 2 )
    {
      if ( *(_QWORD *)(a2 + 16) && v8 == 1 )
      {
        *(_QWORD *)&v9 = a1;
        Rect = 0;
        RectRgn = CreateRectRgn(0, 0, 0, 0);
        if ( RectRgn )
        {
          if ( GetWindowRect(a1, &Rect) )
          {
            if ( (unsigned int)GetWindowRgn(a1, RectRgn) <= 1 )
            {
              IntersectRect(&Rect, &Rect, *(const RECT **)(a2 + 24));
              SetRectRgn(RectRgn, Rect.left, Rect.top, Rect.right, Rect.bottom);
            }
            else
            {
              OffsetRgn(RectRgn, Rect.left, Rect.top);
            }
          }
          if ( CombineRgn(RectRgn, RectRgn, *(HRGN *)(a2 + 16), 4) != 1 )
          {
            DWORD2(v9) = 1;
            if ( (GetWindowLongW(a1, -20) & 0x80000) == 0 )
              CombineRgn(*(HRGN *)(a2 + 16), *(HRGN *)(a2 + 16), RectRgn, 2);
          }
          DeleteObject(RectRgn);
        }
      }
      else
      {
        *(_QWORD *)&v9 = a1;
        DWORD2(v9) = 1;
      }
      v5 = (void (__fastcall *)(__int64, __int64, __int128 *))qword_14024EA98;
      v6 = *(_QWORD *)(a2 + 8);
      if ( qword_14024EA98 == -1 )
      {
        GetProcFromComCtl32(&qword_14024EA98, 324);
        v5 = (void (__fastcall *)(__int64, __int64, __int128 *))qword_14024EA98;
      }
      if ( v5 )
        v5(v6, 0x7FFFFFFF, &v9);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140065ae0  push    rbp
0x140065ae2  push    rbx
0x140065ae3  push    rdi
0x140065ae4  lea     rbp, [rsp-47h]
0x140065ae9  sub     rsp, 90h
0x140065af0  mov     rax, cs:__security_cookie
0x140065af7  xor     rax, rsp
0x140065afa  mov     [rbp+57h+var_20], rax
0x140065afe  mov     rdi, rdx
0x140065b01  mov     [rbp+57h+var_70], 0
0x140065b08  lea     rdx, [rbp+57h+var_70]
0x140065b0c  mov     rbx, rcx
0x140065b0f  call    cs:__imp_GetWindowBand
0x140065b16  nop     dword ptr [rax+rax+00h]
0x140065b1b  test    eax, eax
0x140065b1d  jz      short loc_140065B3D
0x140065b1f  mov     ecx, [rbp+57h+var_70]
0x140065b22  lea     eax, [rcx-1]
0x140065b25  cmp     eax, 1
0x140065b28  ja      short loc_140065B5A
0x140065b2a  mov     rcx, rbx; hWnd
0x140065b2d  call    cs:__imp_IsWindowVisible
0x140065b34  nop     dword ptr [rax+rax+00h]
0x140065b39  test    eax, eax
0x140065b3b  jnz     short loc_140065B61
0x140065b3d  mov     eax, 1
0x140065b42  mov     rcx, [rbp+57h+var_20]
0x140065b46  xor     rcx, rsp; StackCookie
0x140065b49  call    __security_check_cookie
0x140065b4e  add     rsp, 90h
0x140065b55  pop     rdi
0x140065b56  pop     rbx
0x140065b57  pop     rbp
0x140065b58  retn
0x140065b5a  cmp     ecx, 10h
0x140065b5d  jnz     short loc_140065B3D
0x140065b5f  jmp     short loc_140065B2A
0x140065b61  cmp     qword ptr [rdi+10h], 0
0x140065b66  jnz     loc_140065C05
0x140065b6c  cmp     rbx, [rdi]
0x140065b6f  jz      short loc_140065B3D
0x140065b71  cmp     rbx, cs:?v_hwndDesktop@@3PEAUHWND__@@EA; HWND__ * v_hwndDesktop
0x140065b78  jz      short loc_140065B3D
0x140065b7a  xorps   xmm0, xmm0
0x140065b7d  lea     rdx, [rbp+57h+wndpl]; lpwndpl
0x140065b81  xor     eax, eax
0x140065b83  mov     rcx, rbx; hWnd
0x140065b86  movups  xmmword ptr [rbp-11h], xmm0
0x140065b8a  mov     [rbp+57h+wndpl.length], 2Ch ; ','
0x140065b91  movups  xmmword ptr [rbp+57h+wndpl.flags], xmm0
0x140065b95  mov     qword ptr [rbp+57h+wndpl.rcNormalPosition.right], rax
0x140065b99  movups  xmmword ptr [rbp+57h+wndpl.ptMaxPosition.x], xmm0
0x140065b9d  call    cs:__imp_GetWindowPlacement
0x140065ba4  nop     dword ptr [rax+rax+00h]
0x140065ba9  cmp     [rbp+57h+wndpl.showCmd], 2
0x140065bad  jz      short loc_140065B3D
0x140065baf  cmp     qword ptr [rdi+10h], 0
0x140065bb4  mov     [rsp+0A0h+arg_10], rsi
0x140065bbc  jnz     short loc_140065C14
0x140065bbe  mov     [rbp+57h+var_68], rbx
0x140065bc2  mov     [rbp+57h+var_60], 1
0x140065bc9  mov     rax, cs:qword_14024EA98
0x140065bd0  mov     rbx, [rdi+8]
0x140065bd4  mov     rsi, [rsp+0A0h+arg_10]
0x140065bdc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140065be0  jz      loc_140065D34
0x140065be6  test    rax, rax
0x140065be9  jz      loc_140065B3D
0x140065bef  lea     r8, [rbp+57h+var_68]
0x140065bf3  mov     edx, 7FFFFFFFh
0x140065bf8  mov     rcx, rbx
0x140065bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140065c00  jmp     loc_140065B3D
0x140065c05  cmp     [rbp+57h+var_70], 1
0x140065c09  jz      loc_140065B6C
0x140065c0f  jmp     loc_140065B3D
0x140065c14  cmp     [rbp+57h+var_70], 1
0x140065c18  jnz     short loc_140065BBE
0x140065c1a  xorps   xmm0, xmm0
0x140065c1d  mov     [rbp+57h+var_68], rbx
0x140065c21  xor     r9d, r9d; y2
0x140065c24  xor     r8d, r8d; x2
0x140065c27  xor     edx, edx; y1
0x140065c29  xor     ecx, ecx; x1
0x140065c2b  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x140065c2f  call    cs:__imp_CreateRectRgn
0x140065c36  nop     dword ptr [rax+rax+00h]
0x140065c3b  mov     rsi, rax
0x140065c3e  test    rax, rax
0x140065c41  jz      short loc_140065BC9
0x140065c43  lea     rdx, [rbp+57h+Rect]; lpRect
0x140065c47  mov     rcx, rbx; hWnd
0x140065c4a  call    cs:__imp_GetWindowRect
0x140065c51  nop     dword ptr [rax+rax+00h]
0x140065c56  test    eax, eax
0x140065c58  jz      short loc_140065CC2
0x140065c5a  mov     rdx, rsi; hRgn
0x140065c5d  mov     rcx, rbx; hWnd
0x140065c60  call    cs:__imp_GetWindowRgn
0x140065c67  nop     dword ptr [rax+rax+00h]
0x140065c6c  cmp     eax, 1
0x140065c6f  jbe     short loc_140065C89
0x140065c71  mov     r8d, [rbp+57h+Rect.top]; y
0x140065c75  mov     rcx, rsi; hrgn
0x140065c78  mov     edx, [rbp+57h+Rect.left]; x
0x140065c7b  call    cs:__imp_OffsetRgn
0x140065c82  nop     dword ptr [rax+rax+00h]
0x140065c87  jmp     short loc_140065CC2
0x140065c89  mov     r8, [rdi+18h]; lprcSrc2
0x140065c8d  lea     rdx, [rbp+57h+Rect]; lprcSrc1
0x140065c91  lea     rcx, [rbp+57h+Rect]; lprcDst
0x140065c95  call    cs:__imp_IntersectRect
0x140065c9c  nop     dword ptr [rax+rax+00h]
0x140065ca1  mov     eax, [rbp+57h+Rect.bottom]
0x140065ca4  mov     rcx, rsi; hrgn
0x140065ca7  mov     r9d, [rbp+57h+Rect.right]; right
0x140065cab  mov     r8d, [rbp+57h+Rect.top]; top
0x140065caf  mov     edx, [rbp+57h+Rect.left]; left
0x140065cb2  mov     [rsp+0A0h+bottom], eax; bottom
0x140065cb6  call    cs:__imp_SetRectRgn
0x140065cbd  nop     dword ptr [rax+rax+00h]
0x140065cc2  mov     r8, [rdi+10h]; hrgnSrc2
0x140065cc6  mov     r9d, 4; iMode
0x140065ccc  mov     rdx, rsi; hrgnSrc1
0x140065ccf  mov     rcx, rsi; hrgnDst
0x140065cd2  call    cs:__imp_CombineRgn
0x140065cd9  nop     dword ptr [rax+rax+00h]
0x140065cde  cmp     eax, 1
0x140065ce1  jz      short loc_140065D20
0x140065ce3  mov     edx, 0FFFFFFECh; nIndex
0x140065ce8  mov     [rbp+57h+var_60], 1
0x140065cef  mov     rcx, rbx; hWnd
0x140065cf2  call    cs:__imp_GetWindowLongW
0x140065cf9  nop     dword ptr [rax+rax+00h]
0x140065cfe  bt      eax, 13h
0x140065d02  jb      short loc_140065D20
0x140065d04  mov     rcx, [rdi+10h]; hrgnDst
0x140065d08  mov     r9d, 2; iMode
0x140065d0e  mov     rdx, rcx; hrgnSrc1
0x140065d11  mov     r8, rsi; hrgnSrc2
0x140065d14  call    cs:__imp_CombineRgn
0x140065d1b  nop     dword ptr [rax+rax+00h]
0x140065d20  mov     rcx, rsi; ho
0x140065d23  call    cs:__imp_DeleteObject
0x140065d2a  nop     dword ptr [rax+rax+00h]
0x140065d2f  jmp     loc_140065BC9
0x140065d34  mov     edx, 144h
0x140065d39  lea     rcx, qword_14024EA98
0x140065d40  call    _GetProcFromComCtl32
0x140065d45  mov     rax, cs:qword_14024EA98
0x140065d4c  jmp     loc_140065BE6
```
