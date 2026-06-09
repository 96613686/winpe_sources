# sub_1801FFBE8

- ea: `0x1801ffbe8`
- end: `0x1801ffe2f`
- name: `sub_1801FFBE8`
- size: `583`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x1801fd030`

## callees

- `0x1800d0ce8`
- `0x18013bad0`
- `0x18013c916`
- `0x1801fab54`
- `0x1801faba0`
- `0x1801fc570`
- `0x1801fd0d4`
- `0x1801fd354`
- `0x1801fea58`
- `0x1801fed50`
- `0x1801ff9b8`
- `0x1801ffbe8`
- `0x18027a010`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!DefWindowProcW` at `0x1801ffdc9`
- `ext-ms-win-ntuser-window-l1-1-0!DefWindowProcW` at `0x1801ffdc9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongW` at `0x1801ffcac`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongW` at `0x1801ffcba`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongW` at `0x1801ffcac`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongW` at `0x1801ffcba`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x1801ffc97`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x1801ffc97`
- `ext-ms-win-ntuser-draw-l1-1-0!GetUpdateRect` at `0x1801ffce8`
- `ext-ms-win-ntuser-draw-l1-1-0!GetUpdateRect` at `0x1801ffce8`

## pseudocode

```c
LRESULT __fastcall sub_1801FFBE8(__int64 a1, HWND a2, UINT a3, WPARAM a4, LPARAM lParam)
{
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rax
  LONG WindowLongW; // ebx
  __int64 v14; // rbx
  __int64 v15; // r8
  int v17; // [rsp+50h] [rbp-A8h] BYREF
  unsigned int v18; // [rsp+54h] [rbp-A4h] BYREF
  struct tagRECT Rect; // [rsp+58h] [rbp-A0h] BYREF
  _BYTE v20[80]; // [rsp+70h] [rbp-88h] BYREF

  v9 = (unsigned __int8)sub_1801FD0D4(a1, a3, a4);
  v12 = *(_QWORD *)(a1 + 120);
  if ( v12 && a3 == *(_DWORD *)(v12 + 64) )
  {
    LOBYTE(v10) = *(_BYTE *)(a1 + 112);
    LOBYTE(v11) = 1;
    sub_1801FED50(a1, a1 + 56, v10, v11);
    return 0;
  }
  if ( a3 > 0x21 )
  {
    if ( a3 == 256 || a3 == 513 || a3 == 516 || a3 == 519 )
    {
      sub_1800D0CE8(0, 0, 0, 0, 0, 0, 0, 0, 0, 0);
      return 0;
    }
    if ( a3 != 587 )
      goto LABEL_22;
    return 3;
  }
  switch ( a3 )
  {
    case 0x21u:
      return 3;
    case 1u:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
      sub_1801FD354(a1);
      return 0;
    case 2u:
      sub_1801FABA0(a1);
      return 0;
    case 0xFu:
      Rect = 0;
      if ( GetUpdateRect(a2, &Rect, 0) )
      {
        memset(v20, 0, 0x48u);
        v18 = 0;
        v17 = 0;
        v14 = ((__int64 (__fastcall *)(HWND, _BYTE *))qword_1802DD8E8)(a2, v20);
        sub_1801FC570(a1, &v18, &v17);
        sub_1801FEA58(a1, v14, v15, v18, v17);
        ((void (__fastcall *)(HWND, _BYTE *))qword_1802DED50)(a2, v20);
      }
      return 0;
    case 0x15u:
    case 0x1Au:
      sub_1801FAB54(a1);
      if ( *(_BYTE *)(a1 + 100) )
      {
        WindowLongW = GetWindowLongW(a2, -20);
        SetWindowLongW(a2, -20, WindowLongW & 0xFFF7FFFF);
        SetWindowLongW(a2, -20, WindowLongW);
        sub_1801FF9B8(a1, 0, 0xFFu);
      }
      return 0;
  }
LABEL_22:
  if ( (_BYTE)v9 )
    return v9 ^ 1;
  else
    return DefWindowProcW(a2, a3, a4, lParam);
}

```

## disassembly

```asm
0x1801ffbe8  push    rbx
0x1801ffbea  push    rbp
0x1801ffbeb  push    rsi
0x1801ffbec  push    rdi
0x1801ffbed  sub     rsp, 0D8h
0x1801ffbf4  mov     rax, cs:__security_cookie
0x1801ffbfb  xor     rax, rsp
0x1801ffbfe  mov     [rsp+0F8h+var_38], rax
0x1801ffc06  mov     ebx, r8d
0x1801ffc09  mov     rsi, rdx
0x1801ffc0c  mov     edx, ebx
0x1801ffc0e  mov     r8, r9
0x1801ffc11  mov     rbp, r9
0x1801ffc14  mov     rdi, rcx
0x1801ffc17  call    sub_1801FD0D4
0x1801ffc1c  movzx   ecx, al
0x1801ffc1f  mov     rax, [rdi+78h]
0x1801ffc23  test    rax, rax
0x1801ffc26  jz      short loc_1801FFC45
0x1801ffc28  cmp     ebx, [rax+40h]
0x1801ffc2b  jnz     short loc_1801FFC45
0x1801ffc2d  mov     r8b, [rdi+70h]
0x1801ffc31  lea     rdx, [rdi+38h]
0x1801ffc35  mov     r9b, 1
0x1801ffc38  mov     rcx, rdi
0x1801ffc3b  call    sub_1801FED50
0x1801ffc40  jmp     loc_1801FFE11
0x1801ffc45  cmp     ebx, 21h ; '!'
0x1801ffc48  ja      loc_1801FFD96
0x1801ffc4e  jz      loc_1801FFDDA
0x1801ffc54  mov     eax, ebx
0x1801ffc56  sub     eax, 1
0x1801ffc59  jz      loc_1801FFD7D
0x1801ffc5f  sub     eax, 1
0x1801ffc62  jz      loc_1801FFD70
0x1801ffc68  sub     eax, 0Dh
0x1801ffc6b  jz      short loc_1801FFCD5
0x1801ffc6d  sub     eax, 6
0x1801ffc70  jz      short loc_1801FFC7B
0x1801ffc72  cmp     eax, 5
0x1801ffc75  jnz     loc_1801FFDB5
0x1801ffc7b  mov     rcx, rdi
0x1801ffc7e  call    sub_1801FAB54
0x1801ffc83  cmp     byte ptr [rdi+64h], 0
0x1801ffc87  jz      loc_1801FFE11
0x1801ffc8d  mov     ebp, 0FFFFFFECh
0x1801ffc92  mov     rcx, rsi; hWnd
0x1801ffc95  mov     edx, ebp; nIndex
0x1801ffc97  call    cs:GetWindowLongW
0x1801ffc9d  mov     edx, ebp; nIndex
0x1801ffc9f  mov     rcx, rsi; hWnd
0x1801ffca2  mov     r8d, eax
0x1801ffca5  mov     ebx, eax
0x1801ffca7  btr     r8d, 13h; dwNewLong
0x1801ffcac  call    cs:SetWindowLongW
0x1801ffcb2  mov     r8d, ebx; dwNewLong
0x1801ffcb5  mov     edx, ebp; nIndex
0x1801ffcb7  mov     rcx, rsi; hWnd
0x1801ffcba  call    cs:SetWindowLongW
0x1801ffcc0  xor     edx, edx
0x1801ffcc2  mov     r8d, 0FFh
0x1801ffcc8  mov     rcx, rdi
0x1801ffccb  call    sub_1801FF9B8
0x1801ffcd0  jmp     loc_1801FFE11
0x1801ffcd5  xorps   xmm0, xmm0
0x1801ffcd8  lea     rdx, [rsp+0F8h+Rect]; lpRect
0x1801ffcdd  xor     r8d, r8d; bErase
0x1801ffce0  mov     rcx, rsi; hWnd
0x1801ffce3  movups  xmmword ptr [rsp+0F8h+Rect.left], xmm0
0x1801ffce8  call    cs:GetUpdateRect
0x1801ffcee  test    eax, eax
0x1801ffcf0  jz      loc_1801FFE11
0x1801ffcf6  xor     edx, edx; Val
0x1801ffcf8  lea     rcx, [rsp+0F8h+var_88]; void *
0x1801ffcfd  lea     r8d, [rdx+48h]; Size
0x1801ffd01  call    memset
0x1801ffd06  mov     rax, cs:qword_1802DD8E8
0x1801ffd0d  lea     rdx, [rsp+0F8h+var_88]
0x1801ffd12  mov     rcx, rsi
0x1801ffd15  call    j__guard_dispatch_icall
0x1801ffd1a  lea     r8, [rsp+0F8h+var_A8]
0x1801ffd1f  mov     [rsp+0F8h+var_A4], 0
0x1801ffd27  lea     rdx, [rsp+0F8h+var_A4]
0x1801ffd2c  mov     [rsp+0F8h+var_A8], 0
0x1801ffd34  mov     rcx, rdi
0x1801ffd37  mov     rbx, rax
0x1801ffd3a  call    sub_1801FC570
0x1801ffd3f  mov     ecx, [rsp+0F8h+var_A8]
0x1801ffd43  mov     rdx, rbx
0x1801ffd46  mov     r9d, [rsp+0F8h+var_A4]
0x1801ffd4b  mov     [rsp+0F8h+var_D8], ecx
0x1801ffd4f  mov     rcx, rdi
0x1801ffd52  call    sub_1801FEA58
0x1801ffd57  mov     rax, cs:qword_1802DED50
0x1801ffd5e  lea     rdx, [rsp+0F8h+var_88]
0x1801ffd63  mov     rcx, rsi
0x1801ffd66  call    j__guard_dispatch_icall
0x1801ffd6b  jmp     loc_1801FFE11
0x1801ffd70  mov     rcx, rdi
0x1801ffd73  call    sub_1801FABA0
0x1801ffd78  jmp     loc_1801FFE11
0x1801ffd7d  mov     rax, [rdi]
0x1801ffd80  mov     rcx, rdi
0x1801ffd83  mov     rax, [rax+8]
0x1801ffd87  call    j__guard_dispatch_icall
0x1801ffd8c  mov     rcx, rdi
0x1801ffd8f  call    sub_1801FD354
0x1801ffd94  jmp     short loc_1801FFE11
0x1801ffd96  mov     eax, ebx
0x1801ffd98  sub     eax, 100h
0x1801ffd9d  jz      short loc_1801FFDE1
0x1801ffd9f  sub     eax, 101h
0x1801ffda4  jz      short loc_1801FFDE1
0x1801ffda6  sub     eax, 3
0x1801ffda9  jz      short loc_1801FFDE1
0x1801ffdab  sub     eax, 3
0x1801ffdae  jz      short loc_1801FFDE1
0x1801ffdb0  cmp     eax, 44h ; 'D'
0x1801ffdb3  jz      short loc_1801FFDDA
0x1801ffdb5  test    cl, cl
0x1801ffdb7  jnz     short loc_1801FFDD1
0x1801ffdb9  mov     r9, [rsp+0F8h+lParam]; lParam
0x1801ffdc1  mov     r8, rbp; wParam
0x1801ffdc4  mov     edx, ebx; Msg
0x1801ffdc6  mov     rcx, rsi; hWnd
0x1801ffdc9  call    cs:DefWindowProcW
0x1801ffdcf  jmp     short loc_1801FFE13
0x1801ffdd1  mov     rax, rcx
0x1801ffdd4  xor     rax, 1
0x1801ffdd8  jmp     short loc_1801FFE13
0x1801ffdda  mov     eax, 3
0x1801ffddf  jmp     short loc_1801FFE13
0x1801ffde1  mov     [rsp+0F8h+var_B0], 0
0x1801ffde9  xor     r9d, r9d
0x1801ffdec  mov     [rsp+0F8h+var_B8], 0
0x1801ffdf1  xor     r8d, r8d
0x1801ffdf4  mov     [rsp+0F8h+var_C0], 0
0x1801ffdf9  xor     edx, edx
0x1801ffdfb  mov     [rsp+0F8h+var_C8], 0
0x1801ffe00  xor     ecx, ecx
0x1801ffe02  mov     [rsp+0F8h+var_D0], 0
0x1801ffe07  mov     byte ptr [rsp+0F8h+var_D8], 0
0x1801ffe0c  call    sub_1800D0CE8
0x1801ffe11  xor     eax, eax
0x1801ffe13  mov     rcx, [rsp+0F8h+var_38]
0x1801ffe1b  xor     rcx, rsp; StackCookie
0x1801ffe1e  call    __security_check_cookie
0x1801ffe23  add     rsp, 0D8h
0x1801ffe2a  pop     rdi
0x1801ffe2b  pop     rsi
0x1801ffe2c  pop     rbp
0x1801ffe2d  pop     rbx
0x1801ffe2e  retn
```
