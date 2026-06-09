# TV_CreateToolTips

- ea: `0x18007e430`
- end: `0x18007e56b`
- name: `TV_CreateToolTips`
- size: `315`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18006a9c4`
- `0x18007f054`

## callees

- `0x1800115f0`
- `0x18007e430`

## import_xrefs

- `USER32!SendMessageW` at `0x18007e509`
- `USER32!SendMessageW` at `0x18007e527`
- `USER32!SendMessageW` at `0x18007e545`
- `USER32!SendMessageW` at `0x18007e509`
- `USER32!SendMessageW` at `0x18007e527`
- `USER32!SendMessageW` at `0x18007e545`
- `USER32!CreateWindowExW` at `0x18007e4a0`
- `USER32!CreateWindowExW` at `0x18007e4a0`

## pseudocode

```c
HWND __fastcall TV_CreateToolTips(__int64 a1)
{
  HWND result; // rax
  LPARAM lParam; // [rsp+60h] [rbp-58h] BYREF
  HWND v4; // [rsp+68h] [rbp-50h]
  HWND v5; // [rsp+70h] [rbp-48h]
  __int64 v6; // [rsp+78h] [rbp-40h]
  __int128 v7; // [rsp+80h] [rbp-38h]
  __m128i si128; // [rsp+90h] [rbp-28h]

  result = CreateWindowExW(
             (*(_DWORD *)(a1 + 16) & 0x40u) << 7,
             L"tooltips_class32",
             0,
             0x80000002,
             0x80000000,
             0x80000000,
             0x80000000,
             0x80000000,
             *(HWND *)a1,
             0,
             g_hinst,
             0);
  *(_QWORD *)(a1 + 360) = result;
  if ( result )
  {
    v4 = *(HWND *)a1;
    v7 = 0;
    v5 = v4;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v6 = 0;
    lParam = 0x10100000040LL;
    SendMessageW(result, 0x432u, 0, (LPARAM)&lParam);
    SendMessageW(*(HWND *)(a1 + 360), 0x30u, *(_QWORD *)(a1 + 200), 1);
    return (HWND)SendMessageW(*(HWND *)(a1 + 360), 0x403u, 3u, 500);
  }
  else
  {
    *(_DWORD *)(a1 + 16) |= 0x80u;
  }
  return result;
}

```

## disassembly

```asm
0x18007e430  mov     r11, rsp
0x18007e433  push    rbx
0x18007e434  sub     rsp, 0B0h
0x18007e43b  mov     rax, cs:__security_cookie
0x18007e442  xor     rax, rsp
0x18007e445  mov     [rsp+0B8h+var_18], rax
0x18007e44d  mov     rax, cs:g_hinst
0x18007e454  lea     rdx, c_szSToolTipsClass; "tooltips_class32"
0x18007e45b  mov     qword ptr [r11-60h], 0
0x18007e463  mov     rbx, rcx
0x18007e466  mov     ecx, [rcx+10h]
0x18007e469  mov     r9d, 80000002h; dwStyle
0x18007e46f  mov     [r11-68h], rax
0x18007e473  and     ecx, 40h
0x18007e476  mov     qword ptr [r11-70h], 0
0x18007e47e  xor     r8d, r8d; lpWindowName
0x18007e481  mov     rax, [rbx]
0x18007e484  mov     [r11-78h], rax
0x18007e488  mov     eax, 80000000h
0x18007e48d  mov     [rsp+0B8h+nHeight], eax; nHeight
0x18007e491  mov     [rsp+0B8h+nWidth], eax; nWidth
0x18007e495  mov     [rsp+0B8h+Y], eax; Y
0x18007e499  shl     ecx, 7; dwExStyle
0x18007e49c  mov     [rsp+0B8h+X], eax; X
0x18007e4a0  call    cs:__imp_CreateWindowExW
0x18007e4a6  mov     [rbx+168h], rax
0x18007e4ad  test    rax, rax
0x18007e4b0  jz      loc_18007E54D
0x18007e4b6  mov     rcx, [rbx]
0x18007e4b9  lea     r9, [rsp+0B8h+lParam]; lParam
0x18007e4be  xorps   xmm0, xmm0
0x18007e4c1  mov     [rsp+0B8h+var_50], rcx
0x18007e4c6  movdqa  [rsp+0B8h+var_38], xmm0
0x18007e4cf  xor     r8d, r8d; wParam
0x18007e4d2  movdqa  xmm0, cs:__xmm@0000000000000000ffffffffffffffff
0x18007e4da  mov     edx, 432h; Msg
0x18007e4df  mov     [rsp+0B8h+var_48], rcx
0x18007e4e4  mov     rcx, rax; hWnd
0x18007e4e7  movdqa  [rsp+0B8h+var_28], xmm0
0x18007e4f0  mov     [rsp+0B8h+var_40], 0
0x18007e4f9  mov     dword ptr [rsp+0B8h+lParam], 40h ; '@'
0x18007e501  mov     dword ptr [rsp+0B8h+lParam+4], 101h
0x18007e509  call    cs:__imp_SendMessageW
0x18007e50f  mov     r8, [rbx+0C8h]; wParam
0x18007e516  mov     r9d, 1; lParam
0x18007e51c  mov     rcx, [rbx+168h]; hWnd
0x18007e523  lea     edx, [r9+2Fh]; Msg
0x18007e527  call    cs:__imp_SendMessageW
0x18007e52d  mov     rcx, [rbx+168h]; hWnd
0x18007e534  mov     edx, 403h; Msg
0x18007e539  mov     r9d, 1F4h; lParam
0x18007e53f  mov     r8d, 3; wParam
0x18007e545  call    cs:__imp_SendMessageW
0x18007e54b  jmp     short loc_18007E552
0x18007e54d  bts     dword ptr [rbx+10h], 7
0x18007e552  mov     rcx, [rsp+0B8h+var_18]
0x18007e55a  xor     rcx, rsp; StackCookie
0x18007e55d  call    __security_check_cookie
0x18007e562  add     rsp, 0B0h
0x18007e569  pop     rbx
0x18007e56a  retn
```
