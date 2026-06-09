# LoadListTitles

- ea: `0x18000d3b4`
- end: `0x18000d4f8`
- name: `LoadListTitles`
- size: `324`
- prototype: `__int64 __fastcall(HWND hWnd, UINT uID)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a3b0`
- `0x18000b9c0`
- `0x18000d208`

## callees

- `0x18000d3b4`
- `0x180014ae0`

## import_xrefs

- `USER32!GetWindowLongPtrW` at `0x18000d417`
- `USER32!GetWindowLongPtrW` at `0x18000d417`
- `USER32!SendMessageW` at `0x18000d4db`
- `USER32!SendMessageW` at `0x18000d4db`
- `USER32!SetWindowLongPtrW` at `0x18000d42f`
- `USER32!SetWindowLongPtrW` at `0x18000d42f`
- `USER32!LoadStringW` at `0x18000d449`
- `USER32!LoadStringW` at `0x18000d449`

## pseudocode

```c
__int64 __fastcall LoadListTitles(HWND hWnd, UINT uID)
{
  WCHAR *v2; // r14
  WCHAR *v3; // rdi
  int v6; // esi
  LONG_PTR WindowLongPtrW; // rax
  LPARAM lParam[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v10; // [rsp+30h] [rbp-D0h]
  __int128 v11; // [rsp+40h] [rbp-C0h]
  __int64 v12; // [rsp+50h] [rbp-B0h]
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF

  v2 = Buffer;
  v3 = Buffer;
  v6 = 0;
  WindowLongPtrW = GetWindowLongPtrW(hWnd, -16);
  SetWindowLongPtrW(hWnd, -16, WindowLongPtrW & 0xFFFFFFFFFFFFFFE4uLL | 0x19);
  LoadStringW(g_hResDLL, uID, Buffer, 260);
  lParam[1] = 0;
  lParam[0] = 15;
  v10 = 0;
  v12 = 0;
  v11 = 0;
  while ( 1 )
  {
    if ( !*v2 )
      return 0;
    while ( *v3 && *v3 != 124 )
      ++v3;
    *v3 = 0;
    LODWORD(lParam[1]) = 100;
    HIDWORD(v10) = v6;
    *(_QWORD *)&v10 = v2;
    if ( (unsigned int)SendMessageW(hWnd, 0x1061u, v6, (LPARAM)lParam) == -1 )
      break;
    ++v6;
    v2 = ++v3;
  }
  return 1;
}

```

## disassembly

```asm
0x18000d3b4  mov     [rsp-8+arg_10], rbx
0x18000d3b9  mov     [rsp-8+arg_18], rsi
0x18000d3be  push    rbp
0x18000d3bf  push    rdi
0x18000d3c0  push    r13
0x18000d3c2  push    r14
0x18000d3c4  push    r15
0x18000d3c6  lea     rbp, [rsp-180h]
0x18000d3ce  sub     rsp, 280h
0x18000d3d5  mov     rax, cs:__security_cookie
0x18000d3dc  xor     rax, rsp
0x18000d3df  mov     [rbp+1A0h+var_30], rax
0x18000d3e6  xorps   xmm0, xmm0
0x18000d3e9  lea     r14, [rsp+2A0h+Buffer]
0x18000d3ee  xor     eax, eax
0x18000d3f0  lea     rdi, [rsp+2A0h+Buffer]
0x18000d3f5  mov     ebx, edx
0x18000d3f7  mov     [rsp+2A0h+var_250], rax
0x18000d3fc  xor     r13d, r13d
0x18000d3ff  mov     r15, rcx
0x18000d402  movups  xmmword ptr [rsp+2A0h+lParam], xmm0
0x18000d407  lea     edx, [rax-10h]; nIndex
0x18000d40a  mov     esi, r13d
0x18000d40d  movups  [rsp+2A0h+var_270], xmm0
0x18000d412  movups  [rsp+2A0h+var_260], xmm0
0x18000d417  call    cs:__imp_GetWindowLongPtrW
0x18000d41d  lea     edx, [r13-10h]; nIndex
0x18000d421  mov     rcx, r15; hWnd
0x18000d424  and     rax, 0FFFFFFFFFFFFFFFDh
0x18000d428  or      rax, 19h
0x18000d42c  mov     r8, rax; dwNewLong
0x18000d42f  call    cs:__imp_SetWindowLongPtrW
0x18000d435  mov     rcx, cs:g_hResDLL; hInstance
0x18000d43c  lea     r8, [rsp+2A0h+Buffer]; lpBuffer
0x18000d441  mov     r9d, 104h; cchBufferMax
0x18000d447  mov     edx, ebx; uID
0x18000d449  call    cs:__imp_LoadStringW
0x18000d44f  xorps   xmm0, xmm0
0x18000d452  xor     eax, eax
0x18000d454  movups  xmmword ptr [rsp+2A0h+lParam], xmm0
0x18000d459  mov     [rsp+2A0h+lParam], 0Fh
0x18000d462  movups  [rsp+2A0h+var_270], xmm0
0x18000d467  mov     [rsp+2A0h+var_250], rax
0x18000d46c  movups  [rsp+2A0h+var_260], xmm0
0x18000d471  cmp     [r14], r13w
0x18000d475  jnz     short loc_18000D4AE
0x18000d477  xor     eax, eax
0x18000d479  mov     rcx, [rbp+1A0h+var_30]
0x18000d480  xor     rcx, rsp; StackCookie
0x18000d483  call    __security_check_cookie
0x18000d488  lea     r11, [rsp+2A0h+var_20]
0x18000d490  mov     rbx, [r11+40h]
0x18000d494  mov     rsi, [r11+48h]
0x18000d498  mov     rsp, r11
0x18000d49b  pop     r15
0x18000d49d  pop     r14
0x18000d49f  pop     r13
0x18000d4a1  pop     rdi
0x18000d4a2  pop     rbp
0x18000d4a3  retn
0x18000d4a4  cmp     ax, 7Ch ; '|'
0x18000d4a8  jz      short loc_18000D4B6
0x18000d4aa  add     rdi, 2
0x18000d4ae  movzx   eax, word ptr [rdi]
0x18000d4b1  test    ax, ax
0x18000d4b4  jnz     short loc_18000D4A4
0x18000d4b6  movsxd  r8, esi; wParam
0x18000d4b9  lea     r9, [rsp+2A0h+lParam]; lParam
0x18000d4be  mov     edx, 1061h; Msg
0x18000d4c3  mov     [rdi], r13w
0x18000d4c7  mov     rcx, r15; hWnd
0x18000d4ca  mov     dword ptr [rsp+2A0h+lParam+8], 64h ; 'd'
0x18000d4d2  mov     dword ptr [rsp+2A0h+var_270+0Ch], esi
0x18000d4d6  mov     qword ptr [rsp+2A0h+var_270], r14
0x18000d4db  call    cs:__imp_SendMessageW
0x18000d4e1  cmp     eax, 0FFFFFFFFh
0x18000d4e4  jz      short loc_18000D4F1
0x18000d4e6  inc     esi
0x18000d4e8  add     rdi, 2
0x18000d4ec  mov     r14, rdi
0x18000d4ef  jmp     short loc_18000D471
0x18000d4f1  mov     eax, 1
0x18000d4f6  jmp     short loc_18000D479
```
