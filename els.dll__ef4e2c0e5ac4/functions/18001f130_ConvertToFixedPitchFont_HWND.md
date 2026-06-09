# ConvertToFixedPitchFont(HWND__ *)

- ea: `0x18001f130`
- end: `0x18001f1ea`
- name: `?ConvertToFixedPitchFont@@YAHPEAUHWND__@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b2d0`

## callees

- `0x18001f130`
- `0x180022292`
- `0x1800222d0`

## import_xrefs

- `USER32!SendMessageW` at `0x18001f16b`
- `USER32!SendMessageW` at `0x18001f1c2`
- `USER32!SendMessageW` at `0x18001f16b`
- `USER32!SendMessageW` at `0x18001f1c2`
- `GDI32!GetObjectW` at `0x18001f17e`
- `GDI32!GetObjectW` at `0x18001f17e`
- `GDI32!CreateFontIndirectW` at `0x18001f1a7`
- `GDI32!CreateFontIndirectW` at `0x18001f1a7`

## pseudocode

```c
__int64 __fastcall ConvertToFixedPitchFont(HWND hWnd)
{
  void *v2; // rax
  HFONT v3; // rax
  LOGFONTW pv; // [rsp+20h] [rbp-78h] BYREF

  memset_0(&pv, 0, sizeof(pv));
  v2 = (void *)SendMessageW(hWnd, 0x31u, 0, 0);
  if ( !GetObjectW(v2, 92, &pv) )
    return 0;
  pv.lfQuality = 2;
  pv.lfPitchAndFamily = pv.lfPitchAndFamily & 0xFC | 1;
  pv.lfFaceName[0] = 0;
  v3 = CreateFontIndirectW(&pv);
  if ( !v3 )
    return 0;
  SendMessageW(hWnd, 0x30u, (WPARAM)v3, 1);
  return 1;
}

```

## disassembly

```asm
0x18001f130  push    rbx
0x18001f132  sub     rsp, 90h
0x18001f139  mov     rax, cs:__security_cookie
0x18001f140  xor     rax, rsp
0x18001f143  mov     [rsp+98h+var_18], rax
0x18001f14b  xor     edx, edx; Val
0x18001f14d  mov     rbx, rcx
0x18001f150  lea     rcx, [rsp+98h+pv]; void *
0x18001f155  lea     r8d, [rdx+5Ch]; Size
0x18001f159  call    memset_0
0x18001f15e  xor     r9d, r9d; lParam
0x18001f161  xor     r8d, r8d; wParam
0x18001f164  mov     rcx, rbx; hWnd
0x18001f167  lea     edx, [r9+31h]; Msg
0x18001f16b  call    cs:__imp_SendMessageW
0x18001f171  lea     r8, [rsp+98h+pv]; pv
0x18001f176  mov     edx, 5Ch ; '\'; c
0x18001f17b  mov     rcx, rax; h
0x18001f17e  call    cs:__imp_GetObjectW
0x18001f184  test    eax, eax
0x18001f186  jz      short loc_18001F1CF
0x18001f188  mov     dl, [rsp+98h+var_5D]
0x18001f18c  lea     rcx, [rsp+98h+pv]; lplf
0x18001f191  and     dl, 0FDh
0x18001f194  mov     [rsp+98h+var_5E], 2
0x18001f199  or      dl, 1
0x18001f19c  mov     [rsp+98h+var_5D], dl
0x18001f1a0  xor     edx, edx
0x18001f1a2  mov     [rsp+98h+var_5C], dx
0x18001f1a7  call    cs:__imp_CreateFontIndirectW
0x18001f1ad  test    rax, rax
0x18001f1b0  jz      short loc_18001F1CF
0x18001f1b2  mov     r9d, 1; lParam
0x18001f1b8  mov     r8, rax; wParam
0x18001f1bb  mov     rcx, rbx; hWnd
0x18001f1be  lea     edx, [r9+2Fh]; Msg
0x18001f1c2  call    cs:__imp_SendMessageW
0x18001f1c8  mov     eax, 1
0x18001f1cd  jmp     short loc_18001F1D1
0x18001f1cf  xor     eax, eax
0x18001f1d1  mov     rcx, [rsp+98h+var_18]
0x18001f1d9  xor     rcx, rsp; StackCookie
0x18001f1dc  call    __security_check_cookie
0x18001f1e1  add     rsp, 90h
0x18001f1e8  pop     rbx
0x18001f1e9  retn
```
