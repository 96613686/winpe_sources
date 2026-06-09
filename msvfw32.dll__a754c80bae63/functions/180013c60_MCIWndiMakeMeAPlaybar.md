# MCIWndiMakeMeAPlaybar

- ea: `0x180013c60`
- end: `0x180013e3f`
- name: `MCIWndiMakeMeAPlaybar`
- size: `479`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012da8`
- `0x18001306c`

## callees

- `0x1800014b0`
- `0x180013c60`
- `0x180015124`

## import_xrefs

- `COMCTL32!CreateToolbarEx` at `0x180013d8e`
- `COMCTL32!CreateToolbarEx` at `0x180013d8e`
- `USER32!SetWindowLongPtrW` at `0x180013e12`
- `USER32!SetWindowLongPtrW` at `0x180013e12`
- `USER32!GetWindowLongPtrW` at `0x180013da4`
- `USER32!GetWindowLongPtrW` at `0x180013df5`
- `USER32!GetWindowLongPtrW` at `0x180013da4`
- `USER32!GetWindowLongPtrW` at `0x180013df5`
- `USER32!CreateWindowExW` at `0x180013de0`
- `USER32!CreateWindowExW` at `0x180013de0`

## pseudocode

```c
void __fastcall MCIWndiMakeMeAPlaybar(__int64 a1)
{
  HWND v2; // rcx
  HWND v3; // rax
  HWND v4; // rbx
  HWND v5; // rcx
  HINSTANCE WindowLongPtrW; // rax
  HWND Window; // rax
  LRESULT (__stdcall *v8)(HWND, UINT, WPARAM, LPARAM); // rax
  HWND v9; // rcx
  TBBUTTON Buttons; // [rsp+70h] [rbp-90h] BYREF
  int v11; // [rsp+90h] [rbp-70h]
  int v12; // [rsp+94h] [rbp-6Ch]
  __int16 v13; // [rsp+98h] [rbp-68h]
  __int64 v14; // [rsp+A8h] [rbp-58h]
  int v15; // [rsp+B0h] [rbp-50h]
  int v16; // [rsp+B4h] [rbp-4Ch]
  __int16 v17; // [rsp+B8h] [rbp-48h]
  __int64 v18; // [rsp+C8h] [rbp-38h]
  int v19; // [rsp+D0h] [rbp-30h]
  int v20; // [rsp+D4h] [rbp-2Ch]
  __int16 v21; // [rsp+D8h] [rbp-28h]
  __int64 v22; // [rsp+E8h] [rbp-18h]
  int v23; // [rsp+F0h] [rbp-10h]
  int v24; // [rsp+F4h] [rbp-Ch]
  __int16 v25; // [rsp+F8h] [rbp-8h]
  __int64 v26; // [rsp+108h] [rbp+8h]
  int v27; // [rsp+110h] [rbp+10h]
  int v28; // [rsp+114h] [rbp+14h]
  __int16 v29; // [rsp+118h] [rbp+18h]
  __int64 v30; // [rsp+128h] [rbp+28h]
  int v31; // [rsp+130h] [rbp+30h]
  int v32; // [rsp+134h] [rbp+34h]
  __int16 v33; // [rsp+138h] [rbp+38h]
  __int64 v34; // [rsp+148h] [rbp+48h]
  int v35; // [rsp+150h] [rbp+50h]
  int v36; // [rsp+154h] [rbp+54h]
  __int16 v37; // [rsp+158h] [rbp+58h]
  __int64 v38; // [rsp+168h] [rbp+68h]

  if ( (*(_BYTE *)(a1 + 32) & 2) == 0 )
  {
    Buttons.iBitmap = 2;
    v19 = 4;
    v33 = 4;
    v35 = 4;
    Buttons.idCommand = -1;
    Buttons.iString = -1;
    v14 = -1;
    v15 = 2;
    v18 = -1;
    v22 = -1;
    v26 = -1;
    v27 = 2;
    v28 = -1;
    v30 = -1;
    v34 = -1;
    v38 = -1;
    v2 = *(HWND *)a1;
    *(_WORD *)&Buttons.fsState = 256;
    v11 = 0;
    v12 = 2054;
    v13 = 12;
    v16 = 2056;
    v17 = 12;
    v20 = 2063;
    v21 = 12;
    v23 = 5;
    v24 = 108;
    v25 = 12;
    v29 = 256;
    v31 = 3;
    v32 = 107;
    v36 = 109;
    v37 = 256;
    v3 = CreateToolbarEx(v2, 0x4600010Cu, 0x2EBu, 8, ghInst, 0x3BFu, &Buttons, 8, 13, 13, 13, 13, 0x20u);
    v4 = *(HWND *)a1;
    v5 = *(HWND *)a1;
    *(_QWORD *)(a1 + 192) = v3;
    WindowLongPtrW = (HINSTANCE)GetWindowLongPtrW(v5, -6);
    Window = CreateWindowExW(0, L"msctls_trackbar32", 0, 0x56000000u, 0, 0, 0, 0, v4, 0, WindowLongPtrW, 0);
    *(_QWORD *)(a1 + 200) = Window;
    v8 = (LRESULT (__stdcall *)(HWND, UINT, WPARAM, LPARAM))GetWindowLongPtrW(Window, -4);
    v9 = *(HWND *)(a1 + 200);
    fnTrackbarWndProc = v8;
    SetWindowLongPtrW(v9, -4, (LONG_PTR)SubClassedTrackbarWndProc);
    *(_QWORD *)(a1 + 208) = 0;
    MCIWndiValidateMedia(a1);
  }
}

```

## disassembly

```asm
0x180013c60  push    rbp
0x180013c62  push    rbx
0x180013c63  push    rsi
0x180013c64  push    rdi
0x180013c65  lea     rbp, [rsp-88h]
0x180013c6d  sub     rsp, 188h
0x180013c74  mov     rax, cs:__security_cookie
0x180013c7b  xor     rax, rsp
0x180013c7e  mov     [rbp+0A0h+var_30], rax
0x180013c82  mov     edx, 2
0x180013c87  mov     rdi, rcx
0x180013c8a  test    [rcx+20h], dl
0x180013c8d  jnz     loc_180013E27
0x180013c93  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180013c97  mov     [rsp+1A0h+uStructSize], 20h ; ' '; uStructSize
0x180013c9f  lea     eax, [rdx+2]
0x180013ca2  mov     [rsp+1A0h+Buttons.iBitmap], edx
0x180013ca6  mov     [rbp+0A0h+var_D0], eax
0x180013ca9  lea     r9d, [rdx+6]; nBitmaps
0x180013cad  mov     [rbp+0A0h+var_68], ax
0x180013cb1  xor     esi, esi
0x180013cb3  mov     [rbp+0A0h+var_50], eax
0x180013cb6  mov     r8d, 2EBh; wID
0x180013cbc  lea     eax, [rdx+0Bh]
0x180013cbf  mov     [rsp+1A0h+Buttons.idCommand], ecx
0x180013cc3  mov     [rsp+1A0h+dyBitmap], eax; dyBitmap
0x180013cc7  mov     [rsp+1A0h+dxBitmap], eax; dxBitmap
0x180013ccb  mov     [rsp+1A0h+dyButton], eax; dyButton
0x180013ccf  mov     [rsp+1A0h+dxButton], eax; dxButton
0x180013cd3  lea     rax, [rsp+1A0h+Buttons]
0x180013cd8  mov     [rsp+1A0h+iNumButtons], r9d; iNumButtons
0x180013cdd  mov     [rsp+1A0h+lpButtons], rax; lpButtons
0x180013ce2  mov     rax, cs:ghInst
0x180013ce9  mov     [rbp+0A0h+Buttons.iString], rcx
0x180013ced  mov     [rbp+0A0h+var_F8], rcx
0x180013cf1  mov     [rbp+0A0h+var_F0], edx
0x180013cf4  mov     [rbp+0A0h+var_D8], rcx
0x180013cf8  mov     [rbp+0A0h+var_B8], rcx
0x180013cfc  mov     [rbp+0A0h+var_98], rcx
0x180013d00  mov     [rbp+0A0h+var_90], edx
0x180013d03  mov     edx, 4600010Ch; ws
0x180013d08  mov     [rbp+0A0h+var_8C], ecx
0x180013d0b  mov     [rbp+0A0h+var_78], rcx
0x180013d0f  mov     [rbp+0A0h+var_58], rcx
0x180013d13  mov     [rbp+0A0h+var_38], rcx
0x180013d17  mov     rcx, [rdi]; hwnd
0x180013d1a  mov     [rsp+1A0h+wBMID], 3BFh; wBMID
0x180013d23  mov     [rsp+1A0h+hBMInst], rax; hBMInst
0x180013d28  mov     word ptr [rsp+1A0h+Buttons.fsState], 100h
0x180013d2f  mov     [rbp+0A0h+var_110], esi
0x180013d32  mov     [rbp+0A0h+var_10C], 806h
0x180013d39  mov     [rbp+0A0h+var_108], 0Ch
0x180013d3f  mov     [rbp+0A0h+var_EC], 808h
0x180013d46  mov     [rbp+0A0h+var_E8], 0Ch
0x180013d4c  mov     [rbp+0A0h+var_CC], 80Fh
0x180013d53  mov     [rbp+0A0h+var_C8], 0Ch
0x180013d59  mov     [rbp+0A0h+var_B0], 5
0x180013d60  mov     [rbp+0A0h+var_AC], 6Ch ; 'l'
0x180013d67  mov     [rbp+0A0h+var_A8], 0Ch
0x180013d6d  mov     [rbp+0A0h+var_88], 100h
0x180013d73  mov     [rbp+0A0h+var_70], 3
0x180013d7a  mov     [rbp+0A0h+var_6C], 6Bh ; 'k'
0x180013d81  mov     [rbp+0A0h+var_4C], 6Dh ; 'm'
0x180013d88  mov     [rbp+0A0h+var_48], 100h
0x180013d8e  call    cs:__imp_CreateToolbarEx
0x180013d94  mov     rbx, [rdi]
0x180013d97  lea     edx, [rsi-6]; nIndex
0x180013d9a  mov     rcx, rbx; hWnd
0x180013d9d  mov     [rdi+0C0h], rax
0x180013da4  call    cs:__imp_GetWindowLongPtrW
0x180013daa  mov     qword ptr [rsp+1A0h+dyBitmap], rsi; lpParam
0x180013daf  lea     rdx, ClassName; "msctls_trackbar32"
0x180013db6  mov     qword ptr [rsp+1A0h+dxBitmap], rax; hInstance
0x180013dbb  mov     r9d, 56000000h; dwStyle
0x180013dc1  mov     qword ptr [rsp+1A0h+dyButton], rsi; hMenu
0x180013dc6  xor     r8d, r8d; lpWindowName
0x180013dc9  mov     qword ptr [rsp+1A0h+dxButton], rbx; hWndParent
0x180013dce  xor     ecx, ecx; dwExStyle
0x180013dd0  mov     [rsp+1A0h+iNumButtons], esi; nHeight
0x180013dd4  mov     dword ptr [rsp+1A0h+lpButtons], esi; nWidth
0x180013dd8  mov     dword ptr [rsp+1A0h+wBMID], esi; Y
0x180013ddc  mov     dword ptr [rsp+1A0h+hBMInst], esi; X
0x180013de0  call    cs:__imp_CreateWindowExW
0x180013de6  lea     ebx, [rsi-4]
0x180013de9  mov     [rdi+0C8h], rax
0x180013df0  mov     edx, ebx; nIndex
0x180013df2  mov     rcx, rax; hWnd
0x180013df5  call    cs:__imp_GetWindowLongPtrW
0x180013dfb  mov     rcx, [rdi+0C8h]; hWnd
0x180013e02  lea     r8, SubClassedTrackbarWndProc; dwNewLong
0x180013e09  mov     edx, ebx; nIndex
0x180013e0b  mov     cs:fnTrackbarWndProc, rax
0x180013e12  call    cs:__imp_SetWindowLongPtrW
0x180013e18  mov     [rdi+0D0h], rsi
0x180013e1f  mov     rcx, rdi
0x180013e22  call    MCIWndiValidateMedia
0x180013e27  mov     rcx, [rbp+0A0h+var_30]
0x180013e2b  xor     rcx, rsp; StackCookie
0x180013e2e  call    __security_check_cookie
0x180013e33  add     rsp, 188h
0x180013e3a  pop     rdi
0x180013e3b  pop     rsi
0x180013e3c  pop     rbx
0x180013e3d  pop     rbp
0x180013e3e  retn
```
