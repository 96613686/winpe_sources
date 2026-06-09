# CreateToolbarEx

- ea: `0x180023ee0`
- end: `0x180024053`
- name: `CreateToolbarEx`
- size: `371`
- prototype: `HWND __stdcall(HWND hwnd, DWORD ws, UINT wID, int nBitmaps, HINSTANCE hBMInst, UINT_PTR wBMID, LPCTBBUTTON lpButtons, int iNumButtons, int dxButton, int dyButton, int dxBitmap, int dyBitmap, UINT uStructSize)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180023e70`

## callees

- `0x180023ee0`

## import_xrefs

- `USER32!SendMessageW` at `0x180023f6d`
- `USER32!SendMessageW` at `0x180023fa2`
- `USER32!SendMessageW` at `0x180023fdc`
- `USER32!SendMessageW` at `0x18002401e`
- `USER32!SendMessageW` at `0x18002403c`
- `USER32!SendMessageW` at `0x180023f6d`
- `USER32!SendMessageW` at `0x180023fa2`
- `USER32!SendMessageW` at `0x180023fdc`
- `USER32!SendMessageW` at `0x18002401e`
- `USER32!SendMessageW` at `0x18002403c`
- `USER32!DestroyWindow` at `0x180023fea`
- `USER32!DestroyWindow` at `0x180023fea`
- `USER32!CreateWindowExW` at `0x180023f40`
- `USER32!CreateWindowExW` at `0x180023f40`

## pseudocode

```c
HWND __stdcall CreateToolbarEx(
        HWND hwnd,
        DWORD ws,
        UINT wID,
        int nBitmaps,
        HINSTANCE hBMInst,
        UINT_PTR wBMID,
        LPCTBBUTTON lpButtons,
        int iNumButtons,
        int dxButton,
        int dyButton,
        int dxBitmap,
        int dyBitmap,
        UINT uStructSize)
{
  WPARAM v13; // rdi
  HWND Window; // rax
  HWND v15; // rbx
  LPARAM lParam[3]; // [rsp+60h] [rbp-18h] BYREF

  v13 = nBitmaps;
  Window = CreateWindowExW(0, L"ToolbarWindow32", 0, ws | 0x40000000, 0, 0, 100, 30, hwnd, (HMENU)(int)wID, g_hinst, 0);
  v15 = Window;
  if ( Window )
  {
    *(_OWORD *)lParam = 0;
    SendMessageW(Window, 0x41Eu, uStructSize, 0);
    if ( dxBitmap
      && dyBitmap
      && !SendMessageW(
            v15,
            0x420u,
            0,
            (unsigned __int16)dxBitmap | ((unsigned __int64)(unsigned __int16)dyBitmap << 16))
      || dxButton
      && dyButton
      && !SendMessageW(
            v15,
            0x420u,
            0,
            (unsigned __int16)dxButton | ((unsigned __int64)(unsigned __int16)dyButton << 16)) )
    {
      DestroyWindow(v15);
      return 0;
    }
    else
    {
      lParam[0] = (LPARAM)hBMInst;
      lParam[1] = wBMID;
      SendMessageW(v15, 0x413u, v13, (LPARAM)lParam);
      SendMessageW(v15, 0x444u, iNumButtons, (LPARAM)lpButtons);
    }
  }
  return v15;
}

```

## disassembly

```asm
0x180023ee0  mov     r11, rsp
0x180023ee3  mov     [r11+8], rbx
0x180023ee7  push    rdi
0x180023ee8  sub     rsp, 70h
0x180023eec  mov     rax, cs:g_hinst
0x180023ef3  bts     edx, 1Eh
0x180023ef7  mov     qword ptr [r11-20h], 0
0x180023eff  mov     [r11-28h], rax
0x180023f03  movsxd  r10, r8d
0x180023f06  xor     r8d, r8d; lpWindowName
0x180023f09  mov     [r11-30h], r10
0x180023f0d  mov     [r11-38h], rcx
0x180023f11  xor     ecx, ecx; dwExStyle
0x180023f13  mov     [rsp+78h+nHeight], 1Eh; nHeight
0x180023f1b  movsxd  rdi, r9d
0x180023f1e  mov     r9d, edx; dwStyle
0x180023f21  mov     [rsp+78h+nWidth], 64h ; 'd'; nWidth
0x180023f29  lea     rdx, c_szToolbarClass; "ToolbarWindow32"
0x180023f30  mov     [rsp+78h+Y], 0; Y
0x180023f38  mov     [rsp+78h+X], 0; X
0x180023f40  call    cs:__imp_CreateWindowExW
0x180023f46  mov     rbx, rax
0x180023f49  test    rax, rax
0x180023f4c  jz      loc_180024042
0x180023f52  mov     r8d, [rsp+78h+uStructSize]; wParam
0x180023f5a  xorps   xmm0, xmm0
0x180023f5d  xor     r9d, r9d; lParam
0x180023f60  mov     edx, 41Eh; Msg
0x180023f65  mov     rcx, rax; hWnd
0x180023f68  movups  xmmword ptr [rsp+78h+lParam], xmm0
0x180023f6d  call    cs:__imp_SendMessageW
0x180023f73  mov     ecx, [rsp+78h+dxBitmap]
0x180023f7a  test    ecx, ecx
0x180023f7c  jz      short loc_180023FAD
0x180023f7e  mov     eax, [rsp+78h+dyBitmap]
0x180023f85  test    eax, eax
0x180023f87  jz      short loc_180023FAD
0x180023f89  movzx   r9d, ax
0x180023f8d  xor     r8d, r8d; wParam
0x180023f90  movzx   eax, cx
0x180023f93  mov     edx, 420h; Msg
0x180023f98  shl     r9, 10h
0x180023f9c  mov     rcx, rbx; hWnd
0x180023f9f  or      r9, rax; lParam
0x180023fa2  call    cs:__imp_SendMessageW
0x180023fa8  test    rax, rax
0x180023fab  jz      short loc_180023FE7
0x180023fad  mov     eax, [rsp+78h+dxButton]
0x180023fb4  test    eax, eax
0x180023fb6  jz      short loc_180023FF4
0x180023fb8  mov     ecx, [rsp+78h+dyButton]
0x180023fbf  test    ecx, ecx
0x180023fc1  jz      short loc_180023FF4
0x180023fc3  movzx   r9d, cx
0x180023fc7  xor     r8d, r8d; wParam
0x180023fca  shl     r9, 10h
0x180023fce  mov     edx, 420h; Msg
0x180023fd3  movzx   eax, ax
0x180023fd6  mov     rcx, rbx; hWnd
0x180023fd9  or      r9, rax; lParam
0x180023fdc  call    cs:__imp_SendMessageW
0x180023fe2  test    rax, rax
0x180023fe5  jnz     short loc_180023FF4
0x180023fe7  mov     rcx, rbx; hWnd
0x180023fea  call    cs:__imp_DestroyWindow
0x180023ff0  xor     ebx, ebx
0x180023ff2  jmp     short loc_180024042
0x180023ff4  mov     rax, [rsp+78h+hBMInst]
0x180023ffc  lea     r9, [rsp+78h+lParam]; lParam
0x180024001  mov     [rsp+78h+lParam], rax
0x180024006  mov     r8, rdi; wParam
0x180024009  mov     rax, [rsp+78h+wBMID]
0x180024011  mov     edx, 413h; Msg
0x180024016  mov     rcx, rbx; hWnd
0x180024019  mov     [rsp+78h+lParam+8], rax
0x18002401e  call    cs:__imp_SendMessageW
0x180024024  movsxd  r8, [rsp+78h+iNumButtons]; wParam
0x18002402c  mov     edx, 444h; Msg
0x180024031  mov     r9, [rsp+78h+lpButtons]; lParam
0x180024039  mov     rcx, rbx; hWnd
0x18002403c  call    cs:__imp_SendMessageW
0x180024042  mov     rax, rbx
0x180024045  mov     rbx, [rsp+78h+arg_0]
0x18002404d  add     rsp, 70h
0x180024051  pop     rdi
0x180024052  retn
```
