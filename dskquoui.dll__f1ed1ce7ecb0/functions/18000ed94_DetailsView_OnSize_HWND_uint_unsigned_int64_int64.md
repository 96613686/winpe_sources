# DetailsView::OnSize(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18000ed94`
- end: `0x18000ef30`
- name: `?OnSize@DetailsView@@AEAA_JPEAUHWND__@@I_K_J@Z`
- size: `412`
- prototype: `__int64(DetailsView *__hidden this, HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dc40`
- `0x18000dd24`
- `0x180010960`

## callees

- `0x180001510`
- `0x18000ed94`

## import_xrefs

- `USER32!GetClientRect` at `0x18000edd5`
- `USER32!GetClientRect` at `0x18000ee19`
- `USER32!GetClientRect` at `0x18000eedc`
- `USER32!GetClientRect` at `0x18000edd5`
- `USER32!GetClientRect` at `0x18000ee19`
- `USER32!GetClientRect` at `0x18000eedc`
- `USER32!MoveWindow` at `0x18000ef08`
- `USER32!MoveWindow` at `0x18000ef08`
- `USER32!SetWindowPos` at `0x18000eeaa`
- `USER32!SetWindowPos` at `0x18000eeaa`
- `USER32!SendMessageW` at `0x18000ee0b`
- `USER32!SendMessageW` at `0x18000ee3a`
- `USER32!SendMessageW` at `0x18000ee5d`
- `USER32!SendMessageW` at `0x18000eece`
- `USER32!SendMessageW` at `0x18000ee0b`
- `USER32!SendMessageW` at `0x18000ee3a`
- `USER32!SendMessageW` at `0x18000ee5d`
- `USER32!SendMessageW` at `0x18000eece`
- `USER32!GetWindowRect` at `0x18000ee75`
- `USER32!GetWindowRect` at `0x18000ee75`

## pseudocode

```c
__int64 __fastcall DetailsView::OnSize(DetailsView *this, HWND a2, UINT a3, WPARAM a4, LPARAM lParam)
{
  LONG left; // r13d
  LONG top; // r14d
  LONG right; // esi
  LONG bottom; // edi
  HWND v12; // rcx
  int v13; // eax
  HWND v14; // rcx
  HWND v15; // rcx
  HWND v16; // rcx
  LPARAM v18[2]; // [rsp+40h] [rbp-41h] BYREF
  struct tagRECT Rect; // [rsp+50h] [rbp-31h] BYREF
  struct tagRECT v20; // [rsp+60h] [rbp-21h] BYREF
  struct tagRECT v21; // [rsp+70h] [rbp-11h] BYREF

  Rect = 0;
  GetClientRect(a2, &Rect);
  left = Rect.left;
  top = Rect.top;
  right = Rect.right;
  bottom = Rect.bottom;
  if ( (*((_BYTE *)this + 588) & 1) != 0 )
  {
    v12 = (HWND)*((_QWORD *)this + 15);
    v20 = 0;
    SendMessageW(v12, a3, a4, lParam);
    GetClientRect(*((HWND *)this + 15), &v20);
    top += v20.bottom - v20.top + 1;
    v13 = SendMessageW(*((HWND *)this + 15), 0x418u, 0, 0);
    if ( v13 > 0 )
    {
      v14 = (HWND)*((_QWORD *)this + 15);
      *(_OWORD *)v18 = 0;
      SendMessageW(v14, 0x41Du, v13 - 1, (LPARAM)v18);
      v15 = (HWND)*((_QWORD *)this + 16);
      v21 = 0;
      GetWindowRect(v15, &v21);
      SetWindowPos(*((HWND *)this + 16), 0, LODWORD(v18[1]) + 1, HIDWORD(v18[0]) + 1, 0, 0, 0x1Du);
    }
  }
  if ( (*((_BYTE *)this + 588) & 2) != 0 )
  {
    v16 = (HWND)*((_QWORD *)this + 14);
    *(_OWORD *)v18 = 0;
    SendMessageW(v16, a3, a4, lParam);
    GetClientRect(*((HWND *)this + 14), (LPRECT)v18);
    bottom += HIDWORD(v18[0]) - HIDWORD(v18[1]);
  }
  MoveWindow(*((HWND *)this + 13), 0, top, right - left, bottom - top, 1);
  return 0;
}

```

## disassembly

```asm
0x18000ed94  push    rbp
0x18000ed96  push    rbx
0x18000ed97  push    rsi
0x18000ed98  push    rdi
0x18000ed99  push    r12
0x18000ed9b  push    r13
0x18000ed9d  push    r14
0x18000ed9f  push    r15
0x18000eda1  lea     rbp, [rsp-17h]
0x18000eda6  sub     rsp, 98h
0x18000edad  mov     rax, cs:__security_cookie
0x18000edb4  xor     rax, rsp
0x18000edb7  mov     [rbp+4Fh+var_50], rax
0x18000edbb  mov     rax, rdx
0x18000edbe  mov     rbx, rcx
0x18000edc1  xorps   xmm0, xmm0
0x18000edc4  lea     rdx, [rbp+4Fh+Rect]; lpRect
0x18000edc8  mov     rcx, rax; hWnd
0x18000edcb  mov     r12, r9
0x18000edce  mov     r15d, r8d
0x18000edd1  movups  xmmword ptr [rbp+4Fh+Rect.left], xmm0
0x18000edd5  call    cs:__imp_GetClientRect
0x18000eddb  test    byte ptr [rbx+24Ch], 1
0x18000ede2  mov     r13d, [rbp+4Fh+Rect.left]
0x18000ede6  mov     r14d, [rbp+4Fh+Rect.top]
0x18000edea  mov     esi, [rbp+4Fh+Rect.right]
0x18000eded  mov     edi, [rbp+4Fh+Rect.bottom]
0x18000edf0  jz      loc_18000EEB0
0x18000edf6  mov     r9, [rbp+4Fh+lParam]; lParam
0x18000edfa  xorps   xmm0, xmm0
0x18000edfd  mov     rcx, [rbx+78h]; hWnd
0x18000ee01  mov     r8, r12; wParam
0x18000ee04  mov     edx, r15d; Msg
0x18000ee07  movups  xmmword ptr [rbp+4Fh+var_70.left], xmm0
0x18000ee0b  call    cs:__imp_SendMessageW
0x18000ee11  mov     rcx, [rbx+78h]; hWnd
0x18000ee15  lea     rdx, [rbp+4Fh+var_70]; lpRect
0x18000ee19  call    cs:__imp_GetClientRect
0x18000ee1f  mov     eax, [rbp+4Fh+var_70.bottom]
0x18000ee22  inc     r14d
0x18000ee25  sub     eax, [rbp+4Fh+var_70.top]
0x18000ee28  xor     r9d, r9d; lParam
0x18000ee2b  mov     rcx, [rbx+78h]; hWnd
0x18000ee2f  xor     r8d, r8d; wParam
0x18000ee32  mov     edx, 418h; Msg
0x18000ee37  add     r14d, eax
0x18000ee3a  call    cs:__imp_SendMessageW
0x18000ee40  test    eax, eax
0x18000ee42  jle     short loc_18000EEB0
0x18000ee44  mov     rcx, [rbx+78h]; hWnd
0x18000ee48  lea     r9, [rbp+4Fh+var_90]; lParam
0x18000ee4c  dec     eax
0x18000ee4e  xorps   xmm0, xmm0
0x18000ee51  movsxd  r8, eax; wParam
0x18000ee54  mov     edx, 41Dh; Msg
0x18000ee59  movups  xmmword ptr [rbp+4Fh+var_90], xmm0
0x18000ee5d  call    cs:__imp_SendMessageW
0x18000ee63  mov     rcx, [rbx+80h]; hWnd
0x18000ee6a  lea     rdx, [rbp+4Fh+var_60]; lpRect
0x18000ee6e  xorps   xmm0, xmm0
0x18000ee71  movups  xmmword ptr [rbp+4Fh+var_60.left], xmm0
0x18000ee75  call    cs:__imp_GetWindowRect
0x18000ee7b  mov     r9d, dword ptr [rbp+4Fh+var_90+4]
0x18000ee7f  xor     edx, edx; hWndInsertAfter
0x18000ee81  mov     r8d, dword ptr [rbp+4Fh+var_90+8]
0x18000ee85  inc     r9d; Y
0x18000ee88  mov     rcx, [rbx+80h]; hWnd
0x18000ee8f  inc     r8d; X
0x18000ee92  mov     [rsp+0D0h+uFlags], 1Dh; uFlags
0x18000ee9a  mov     [rsp+0D0h+cy], 0; cy
0x18000eea2  mov     [rsp+0D0h+nHeight], 0; cx
0x18000eeaa  call    cs:__imp_SetWindowPos
0x18000eeb0  test    byte ptr [rbx+24Ch], 2
0x18000eeb7  jz      short loc_18000EEEA
0x18000eeb9  mov     r9, [rbp+4Fh+lParam]; lParam
0x18000eebd  xorps   xmm0, xmm0
0x18000eec0  mov     rcx, [rbx+70h]; hWnd
0x18000eec4  mov     r8, r12; wParam
0x18000eec7  mov     edx, r15d; Msg
0x18000eeca  movups  xmmword ptr [rbp+4Fh+var_90], xmm0
0x18000eece  call    cs:__imp_SendMessageW
0x18000eed4  mov     rcx, [rbx+70h]; hWnd
0x18000eed8  lea     rdx, [rbp+4Fh+var_90]; lpRect
0x18000eedc  call    cs:__imp_GetClientRect
0x18000eee2  mov     eax, dword ptr [rbp+4Fh+var_90+4]
0x18000eee5  sub     eax, dword ptr [rbp+4Fh+var_90+0Ch]
0x18000eee8  add     edi, eax
0x18000eeea  mov     rcx, [rbx+68h]; hWnd
0x18000eeee  sub     esi, r13d
0x18000eef1  sub     edi, r14d
0x18000eef4  mov     [rsp+0D0h+cy], 1; bRepaint
0x18000eefc  mov     r9d, esi; nWidth
0x18000eeff  mov     [rsp+0D0h+nHeight], edi; nHeight
0x18000ef03  mov     r8d, r14d; Y
0x18000ef06  xor     edx, edx; X
0x18000ef08  call    cs:__imp_MoveWindow
0x18000ef0e  xor     eax, eax
0x18000ef10  mov     rcx, [rbp+4Fh+var_50]
0x18000ef14  xor     rcx, rsp; StackCookie
0x18000ef17  call    __security_check_cookie
0x18000ef1c  add     rsp, 98h
0x18000ef23  pop     r15
0x18000ef25  pop     r14
0x18000ef27  pop     r13
0x18000ef29  pop     r12
0x18000ef2b  pop     rdi
0x18000ef2c  pop     rsi
0x18000ef2d  pop     rbx
0x18000ef2e  pop     rbp
0x18000ef2f  retn
```
