# TL_OnCreate

- ea: `0x18004a994`
- end: `0x18004aaf7`
- name: `TL_OnCreate`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004c060`

## callees

- `0x18004a994`
- `0x18004d110`

## import_xrefs

- `USER32!CreateWindowExW` at `0x18004aaa4`
- `USER32!CreateWindowExW` at `0x18004aaa4`
- `USER32!GetClientRect` at `0x18004aa5c`
- `USER32!GetClientRect` at `0x18004aa5c`
- `USER32!SendMessageW` at `0x18004aac3`
- `USER32!SendMessageW` at `0x18004aac3`

## pseudocode

```c
HWND __fastcall TL_OnCreate(__int64 a1, __int64 a2)
{
  HWND v4; // rcx
  DWORD v5; // edi
  DWORD v6; // ebx
  HWND result; // rax
  HWND v8; // rbx
  struct tagRECT Rect; // [rsp+60h] [rbp-38h] BYREF

  *(_QWORD *)(a1 + 272) = 0;
  *(_QWORD *)(a1 + 240) = 0;
  *(_QWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 248) = 0;
  *(_QWORD *)(a1 + 232) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_DWORD *)(a1 + 8) = *(_DWORD *)(a2 + 16);
  *(_QWORD *)(a1 + 24) = *(_QWORD *)(a2 + 24);
  *(_DWORD *)(a1 + 88) = -1;
  *(_DWORD *)(a1 + 92) = -1;
  *(_QWORD *)(a1 + 192) = L"ROOT";
  *(_QWORD *)(a1 + 64) = a1 + 56;
  *(_QWORD *)(a1 + 56) = a1 + 56;
  *(_QWORD *)(a1 + 80) = a1 + 72;
  *(_QWORD *)(a1 + 72) = a1 + 72;
  *(_QWORD *)(a1 + 212) = 1;
  *(_QWORD *)(a1 + 32) = 0;
  *(_DWORD *)(a1 + 96) = 0;
  v4 = *(HWND *)a1;
  v5 = *(_DWORD *)(a2 + 48) & 0xBFFF03CA | 0x40000405;
  v6 = *(_DWORD *)(a2 + 72) & 0xFFFDFCFF;
  Rect = 0;
  GetClientRect(v4, &Rect);
  result = CreateWindowExW(
             v6,
             L"SysListView32",
             0,
             v5,
             0,
             0,
             Rect.right,
             Rect.bottom,
             *(HWND *)a1,
             0,
             *(HINSTANCE *)(a2 + 8),
             0);
  v8 = result;
  if ( result )
  {
    SendMessageW(result, 0x1001u, 0, 0xFFFFFFFFLL);
    result = (HWND)1;
    *(_QWORD *)(a1 + 16) = v8;
  }
  return result;
}

```

## disassembly

```asm
0x18004a994  mov     [rsp+arg_10], rbx
0x18004a999  mov     [rsp+arg_18], rbp
0x18004a99e  push    rsi
0x18004a99f  push    rdi
0x18004a9a0  push    r14
0x18004a9a2  sub     rsp, 80h
0x18004a9a9  mov     rax, cs:__security_cookie
0x18004a9b0  xor     rax, rsp
0x18004a9b3  mov     [rsp+98h+var_28], rax
0x18004a9b8  xor     ebp, ebp
0x18004a9ba  mov     rsi, rdx
0x18004a9bd  mov     [rcx+110h], rbp
0x18004a9c4  mov     r14, rcx
0x18004a9c7  mov     [rcx+0F0h], rbp
0x18004a9ce  xorps   xmm0, xmm0
0x18004a9d1  mov     [rcx+108h], rbp
0x18004a9d8  mov     [rcx+0F8h], rbp
0x18004a9df  mov     [rcx+0E8h], rbp
0x18004a9e6  mov     [rcx+10h], rbp
0x18004a9ea  mov     eax, [rdx+10h]
0x18004a9ed  mov     [rcx+8], eax
0x18004a9f0  mov     rax, [rdx+18h]
0x18004a9f4  mov     [rcx+18h], rax
0x18004a9f8  or      eax, 0FFFFFFFFh
0x18004a9fb  mov     [rcx+58h], eax
0x18004a9fe  mov     [rcx+5Ch], eax
0x18004aa01  lea     rax, aRoot; "ROOT"
0x18004aa08  mov     [rcx+0C0h], rax
0x18004aa0f  lea     rax, [rcx+38h]
0x18004aa13  mov     [rcx+40h], rax
0x18004aa17  mov     [rax], rax
0x18004aa1a  lea     rax, [rcx+48h]
0x18004aa1e  mov     [rcx+50h], rax
0x18004aa22  mov     [rax], rax
0x18004aa25  mov     qword ptr [rcx+0D4h], 1
0x18004aa30  mov     [rcx+20h], rbp
0x18004aa34  mov     [rcx+60h], ebp
0x18004aa37  mov     edi, [rdx+30h]
0x18004aa3a  mov     ebx, [rdx+48h]
0x18004aa3d  and     edi, 0FFFF07CFh
0x18004aa43  mov     rcx, [rcx]; hWnd
0x18004aa46  lea     rdx, [rsp+98h+Rect]; lpRect
0x18004aa4b  or      edi, 40000405h
0x18004aa51  and     ebx, 0FFFDFCFFh
0x18004aa57  movups  xmmword ptr [rsp+98h+Rect.left], xmm0
0x18004aa5c  call    cs:__imp_GetClientRect
0x18004aa62  mov     rax, [rsi+8]
0x18004aa66  lea     rdx, aSyslistview32; "SysListView32"
0x18004aa6d  mov     [rsp+98h+lpParam], rbp; lpParam
0x18004aa72  mov     r9d, edi; dwStyle
0x18004aa75  mov     [rsp+98h+hInstance], rax; hInstance
0x18004aa7a  xor     r8d, r8d; lpWindowName
0x18004aa7d  mov     rax, [r14]
0x18004aa80  mov     ecx, ebx; dwExStyle
0x18004aa82  mov     [rsp+98h+hMenu], rbp; hMenu
0x18004aa87  mov     [rsp+98h+hWndParent], rax; hWndParent
0x18004aa8c  mov     eax, [rsp+98h+Rect.bottom]
0x18004aa90  mov     [rsp+98h+nHeight], eax; nHeight
0x18004aa94  mov     eax, [rsp+98h+Rect.right]
0x18004aa98  mov     [rsp+98h+nWidth], eax; nWidth
0x18004aa9c  mov     [rsp+98h+Y], ebp; Y
0x18004aaa0  mov     [rsp+98h+X], ebp; X
0x18004aaa4  call    cs:__imp_CreateWindowExW
0x18004aaaa  mov     rbx, rax
0x18004aaad  test    rax, rax
0x18004aab0  jz      short loc_18004AAD2
0x18004aab2  mov     r9d, 0FFFFFFFFh; lParam
0x18004aab8  xor     r8d, r8d; wParam
0x18004aabb  mov     edx, 1001h; Msg
0x18004aac0  mov     rcx, rbx; hWnd
0x18004aac3  call    cs:__imp_SendMessageW
0x18004aac9  mov     eax, 1
0x18004aace  mov     [r14+10h], rbx
0x18004aad2  mov     rcx, [rsp+98h+var_28]
0x18004aad7  xor     rcx, rsp; StackCookie
0x18004aada  call    __security_check_cookie
0x18004aadf  lea     r11, [rsp+98h+var_18]
0x18004aae7  mov     rbx, [r11+30h]
0x18004aaeb  mov     rbp, [r11+38h]
0x18004aaef  mov     rsp, r11
0x18004aaf2  pop     r14
0x18004aaf4  pop     rdi
0x18004aaf5  pop     rsi
0x18004aaf6  retn
```
