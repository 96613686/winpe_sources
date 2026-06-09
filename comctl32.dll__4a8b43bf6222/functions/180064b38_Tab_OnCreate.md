# Tab_OnCreate

- ea: `0x180064b38`
- end: `0x180064d7f`
- name: `Tab_OnCreate`
- size: `583`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180066d40`

## callees

- `0x1800115f0`
- `0x18002eab0`
- `0x180064b38`
- `0x18008691c`
- `0x180090020`

## import_xrefs

- `GDI32!GetDeviceCaps` at `0x180064c43`
- `GDI32!GetDeviceCaps` at `0x180064c43`
- `USER32!GetDC` at `0x180064c32`
- `USER32!GetDC` at `0x180064c32`
- `USER32!ReleaseDC` at `0x180064c54`
- `USER32!ReleaseDC` at `0x180064c54`
- `USER32!SendMessageW` at `0x180064d26`
- `USER32!SendMessageW` at `0x180064d26`
- `USER32!SetWindowLongW` at `0x180064bbe`
- `USER32!SetWindowLongW` at `0x180064bbe`
- `USER32!CreateWindowExW` at `0x180064d04`
- `USER32!CreateWindowExW` at `0x180064d04`

## pseudocode

```c
HDPA __fastcall Tab_OnCreate(_QWORD *a1)
{
  HDPA result; // rax
  unsigned int v3; // r8d
  int v4; // eax
  int v5; // ecx
  int v6; // eax
  HDC DC; // rbx
  HWND Window; // rax
  __int64 (__fastcall *v9)(_QWORD, _QWORD); // rax
  LPARAM lParam; // [rsp+60h] [rbp-58h] BYREF
  HWND hWndParent; // [rsp+68h] [rbp-50h]
  HWND v12; // [rsp+70h] [rbp-48h]
  __int64 v13; // [rsp+78h] [rbp-40h]
  __int128 v14; // [rsp+80h] [rbp-38h]
  __int64 v15; // [rsp+90h] [rbp-28h]
  __int64 v16; // [rsp+98h] [rbp-20h]

  result = DPA_CreateEx(4, 0);
  a1[8] = result;
  if ( result )
  {
    v3 = *((_DWORD *)a1 + 4);
    if ( (v3 & 0x400) == 0 )
    {
      v3 &= 0xFFFFFFCF;
      *((_DWORD *)a1 + 4) = v3;
    }
    if ( (v3 & 0x80u) != 0 )
    {
      v3 |= 0x200u;
      *((_DWORD *)a1 + 4) = v3;
    }
    if ( (v3 & 1) != 0 )
    {
      v3 = v3 & 0xFFFFFCFF | 0x200;
      *((_DWORD *)a1 + 4) = v3;
    }
    if ( (v3 & 8) != 0 )
      *((_DWORD *)a1 + 20) |= 1u;
    SetWindowLongW((HWND)*a1, -16, v3 | 0x4000000);
    *((_DWORD *)a1 + 18) = 16;
    *((_DWORD *)a1 + 19) = 8;
    *((_DWORD *)a1 + 28) = 0x7FFFFFFF;
    *((_DWORD *)a1 + 26) = 0x7FFFFFFF;
    v4 = g_cxEdge;
    *((_DWORD *)a1 + 24) = -1;
    *((_DWORD *)a1 + 54) = -1;
    *((_DWORD *)a1 + 31) = 0;
    v5 = 3 * v4;
    a1[7] = 0;
    v6 = g_cyEdge;
    *((_DWORD *)a1 + 33) = v5;
    *((_DWORD *)a1 + 37) = -1;
    *((_DWORD *)a1 + 25) = -1;
    *((_DWORD *)a1 + 38) = -1;
    *((_DWORD *)a1 + 34) = 3 * v6 / 2;
    DC = GetDC(0);
    *((_DWORD *)a1 + 35) = GetDeviceCaps(DC, 88);
    ReleaseDC(0, DC);
    InitDitherBrush();
    if ( (a1[2] & 0x4000) != 0 )
    {
      hWndParent = (HWND)*a1;
      v12 = hWndParent;
      v13 = 0;
      v14 = 0;
      v16 = 0;
      lParam = 0x100000040LL;
      v15 = 0;
      Window = CreateWindowExW(
                 0,
                 L"tooltips_class32",
                 &WindowName,
                 0x80000000,
                 0x80000000,
                 0x80000000,
                 0x80000000,
                 0x80000000,
                 hWndParent,
                 0,
                 g_hinst,
                 0);
      a1[22] = Window;
      if ( Window )
        SendMessageW(Window, 0x432u, 0, (LPARAM)&lParam);
      else
        *((_DWORD *)a1 + 4) &= ~0x4000u;
    }
    if ( g_fDBCSInputEnabled )
    {
      v9 = g_pfnImmAssociateContext;
      if ( g_pfnImmAssociateContext )
        v9 = (__int64 (__fastcall *)(_QWORD, _QWORD))g_pfnImmAssociateContext(*a1, 0);
      a1[23] = v9;
    }
    return (HDPA)1;
  }
  return result;
}

```

## disassembly

```asm
0x180064b38  mov     [rsp+arg_8], rbx
0x180064b3d  push    rdi
0x180064b3e  sub     rsp, 0B0h
0x180064b45  mov     rax, cs:__security_cookie
0x180064b4c  xor     rax, rsp
0x180064b4f  mov     [rsp+0B8h+var_18], rax
0x180064b57  xor     edx, edx; hheap
0x180064b59  mov     rdi, rcx
0x180064b5c  lea     ecx, [rdx+4]; cpGrow
0x180064b5f  call    DPA_CreateEx
0x180064b64  mov     [rdi+40h], rax
0x180064b68  test    rax, rax
0x180064b6b  jz      loc_180064D5E
0x180064b71  mov     r8d, [rdi+10h]
0x180064b75  bt      r8d, 0Ah
0x180064b7a  jb      short loc_180064B84
0x180064b7c  and     r8d, 0FFFFFFCFh
0x180064b80  mov     [rdi+10h], r8d
0x180064b84  mov     eax, 200h
0x180064b89  test    r8b, r8b
0x180064b8c  jns     short loc_180064B95
0x180064b8e  or      r8d, eax
0x180064b91  mov     [rdi+10h], r8d
0x180064b95  test    r8b, 1
0x180064b99  jz      short loc_180064BA7
0x180064b9b  btr     r8d, 8
0x180064ba0  or      r8d, eax
0x180064ba3  mov     [rdi+10h], r8d
0x180064ba7  test    r8b, 8
0x180064bab  jz      short loc_180064BB1
0x180064bad  or      dword ptr [rdi+50h], 1
0x180064bb1  mov     rcx, [rdi]; hWnd
0x180064bb4  bts     r8d, 1Ah; dwNewLong
0x180064bb9  mov     edx, 0FFFFFFF0h; nIndex
0x180064bbe  call    cs:__imp_SetWindowLongW
0x180064bc4  or      r8d, 0FFFFFFFFh
0x180064bc8  mov     dword ptr [rdi+48h], 10h
0x180064bcf  mov     eax, 7FFFFFFFh
0x180064bd4  mov     dword ptr [rdi+4Ch], 8
0x180064bdb  mov     [rdi+70h], eax
0x180064bde  mov     [rdi+68h], eax
0x180064be1  mov     eax, cs:g_cxEdge
0x180064be7  mov     [rdi+60h], r8d
0x180064beb  mov     [rdi+0D8h], r8d
0x180064bf2  mov     dword ptr [rdi+7Ch], 0
0x180064bf9  lea     ecx, [rax+rax*2]
0x180064bfc  mov     qword ptr [rdi+38h], 0
0x180064c04  mov     eax, cs:g_cyEdge
0x180064c0a  mov     [rdi+84h], ecx
0x180064c10  xor     ecx, ecx; hWnd
0x180064c12  mov     [rdi+94h], r8d
0x180064c19  mov     [rdi+64h], r8d
0x180064c1d  lea     eax, [rax+rax*2]
0x180064c20  mov     [rdi+98h], r8d
0x180064c27  cdq
0x180064c28  sub     eax, edx
0x180064c2a  sar     eax, 1
0x180064c2c  mov     [rdi+88h], eax
0x180064c32  call    cs:__imp_GetDC
0x180064c38  mov     rcx, rax; hdc
0x180064c3b  mov     edx, 58h ; 'X'; index
0x180064c40  mov     rbx, rax
0x180064c43  call    cs:__imp_GetDeviceCaps
0x180064c49  mov     rdx, rbx; hDC
0x180064c4c  xor     ecx, ecx; hWnd
0x180064c4e  mov     [rdi+8Ch], eax
0x180064c54  call    cs:__imp_ReleaseDC
0x180064c5a  call    InitDitherBrush
0x180064c5f  test    dword ptr [rdi+10h], 4000h
0x180064c66  jz      loc_180064D33
0x180064c6c  mov     rcx, [rdi]
0x180064c6f  lea     r8, WindowName; lpWindowName
0x180064c76  mov     rax, cs:g_hinst
0x180064c7d  lea     rdx, c_szSToolTipsClass; "tooltips_class32"
0x180064c84  mov     [rsp+0B8h+lpParam], 0; lpParam
0x180064c8d  xorps   xmm0, xmm0
0x180064c90  mov     [rsp+0B8h+hInstance], rax; hInstance
0x180064c95  mov     r9d, 80000000h; dwStyle
0x180064c9b  mov     [rsp+0B8h+hMenu], 0; hMenu
0x180064ca4  mov     eax, 80000000h
0x180064ca9  mov     [rsp+0B8h+hWndParent], rcx; hWndParent
0x180064cae  mov     [rsp+0B8h+nHeight], eax; nHeight
0x180064cb2  mov     [rsp+0B8h+nWidth], eax; nWidth
0x180064cb6  mov     [rsp+0B8h+var_50], rcx
0x180064cbb  mov     [rsp+0B8h+var_48], rcx
0x180064cc0  xor     ecx, ecx; dwExStyle
0x180064cc2  mov     [rsp+0B8h+Y], eax; Y
0x180064cc6  mov     [rsp+0B8h+X], eax; X
0x180064cca  mov     [rsp+0B8h+var_40], 0
0x180064cd3  movdqa  [rsp+0B8h+var_38], xmm0
0x180064cdc  mov     [rsp+0B8h+var_20], 0
0x180064ce8  mov     dword ptr [rsp+0B8h+lParam], 40h ; '@'
0x180064cf0  mov     dword ptr [rsp+0B8h+lParam+4], 1
0x180064cf8  mov     [rsp+0B8h+var_28], 0
0x180064d04  call    cs:__imp_CreateWindowExW
0x180064d0a  mov     [rdi+0B0h], rax
0x180064d11  test    rax, rax
0x180064d14  jz      short loc_180064D2E
0x180064d16  lea     r9, [rsp+0B8h+lParam]; lParam
0x180064d1b  xor     r8d, r8d; wParam
0x180064d1e  mov     edx, 432h; Msg
0x180064d23  mov     rcx, rax; hWnd
0x180064d26  call    cs:__imp_SendMessageW
0x180064d2c  jmp     short loc_180064D33
0x180064d2e  btr     dword ptr [rdi+10h], 0Eh
0x180064d33  cmp     cs:g_fDBCSInputEnabled, 0
0x180064d3a  jz      short loc_180064D59
0x180064d3c  mov     rax, cs:g_pfnImmAssociateContext
0x180064d43  test    rax, rax
0x180064d46  jz      short loc_180064D52
0x180064d48  mov     rcx, [rdi]
0x180064d4b  xor     edx, edx
0x180064d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064d52  mov     [rdi+0B8h], rax
0x180064d59  mov     eax, 1
0x180064d5e  mov     rcx, [rsp+0B8h+var_18]
0x180064d66  xor     rcx, rsp; StackCookie
0x180064d69  call    __security_check_cookie
0x180064d6e  mov     rbx, [rsp+0B8h+arg_8]
0x180064d76  add     rsp, 0B0h
0x180064d7d  pop     rdi
0x180064d7e  retn
```
