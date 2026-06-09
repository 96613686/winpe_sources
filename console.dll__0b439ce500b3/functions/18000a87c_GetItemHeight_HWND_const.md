# GetItemHeight(HWND__ * const)

- ea: `0x18000a87c`
- end: `0x18000a9c7`
- name: `?GetItemHeight@@YAIQEAUHWND__@@@Z`
- size: `331`
- prototype: `unsigned int __fastcall(HWND hWnd)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009264`
- `0x180009980`

## callees

- `0x1800015b0`
- `0x18000a87c`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000a919`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000a919`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18000a933`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18000a978`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18000a933`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18000a978`
- `ext-ms-win-gdi-dc-l1-2-0!GetObjectW` at `0x18000a8ee`
- `ext-ms-win-gdi-dc-l1-2-0!GetObjectW` at `0x18000a8ee`
- `ext-ms-win-gdi-font-l1-1-0!GetTextMetricsW` at `0x18000a961`
- `ext-ms-win-gdi-font-l1-1-0!GetTextMetricsW` at `0x18000a961`
- `ext-ms-win-ntuser-draw-l1-1-1!LoadBitmapW` at `0x18000a8cc`
- `ext-ms-win-ntuser-draw-l1-1-1!LoadBitmapW` at `0x18000a8cc`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18000a8a9`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18000a8a9`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x18000a98a`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x18000a98a`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x18000a8fd`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x18000a8fd`

## pseudocode

```c
__int64 __fastcall GetItemHeight(HWND hWnd)
{
  HDC DC; // rdi
  void *v3; // rax
  HGDIOBJ v4; // rbx
  __int64 result; // rax
  tagTEXTMETRICW tm; // [rsp+20h] [rbp-58h] BYREF

  if ( hbmTT )
  {
    DeleteObject(hbmTT);
    hbmTT = 0;
  }
  hbmTT = LoadBitmapW(ghInstance, (LPCWSTR)0x3E8);
  GetObjectW(hbmTT, 32, &bmTT);
  DC = GetDC(hWnd);
  v3 = (void *)SendMessageW(hWnd, 0x31u, 0, 0);
  v4 = v3;
  if ( v3 )
    v4 = SelectObject(DC, v3);
  memset(&tm, 0, sizeof(tm));
  GetTextMetricsW(DC, &tm);
  if ( v4 )
    SelectObject(DC, v4);
  ReleaseDC(hWnd, DC);
  result = (unsigned int)tm.tmHeight;
  if ( tm.tmHeight < dword_1800237A8 )
    return (unsigned int)dword_1800237A8;
  return result;
}

```

## disassembly

```asm
0x18000a87c  mov     [rsp+arg_8], rbx
0x18000a881  mov     [rsp+arg_10], rsi
0x18000a886  push    rdi
0x18000a887  sub     rsp, 70h
0x18000a88b  mov     rax, cs:__security_cookie
0x18000a892  xor     rax, rsp
0x18000a895  mov     [rsp+78h+var_18], rax
0x18000a89a  mov     rsi, rcx
0x18000a89d  mov     rcx, cs:?hbmTT@@3PEAUHBITMAP__@@EA; ho
0x18000a8a4  test    rcx, rcx
0x18000a8a7  jz      short loc_18000A8C0
0x18000a8a9  call    cs:__imp_DeleteObject
0x18000a8b0  nop     dword ptr [rax+rax+00h]
0x18000a8b5  mov     cs:?hbmTT@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * hbmTT
0x18000a8c0  mov     rcx, cs:?ghInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18000a8c7  mov     edx, 3E8h; lpBitmapName
0x18000a8cc  call    cs:__imp_LoadBitmapW
0x18000a8d3  nop     dword ptr [rax+rax+00h]
0x18000a8d8  lea     r8, ?bmTT@@3UtagBITMAP@@A; pv
0x18000a8df  mov     edx, 20h ; ' '; c
0x18000a8e4  mov     rcx, rax; h
0x18000a8e7  mov     cs:?hbmTT@@3PEAUHBITMAP__@@EA, rax; HBITMAP__ * hbmTT
0x18000a8ee  call    cs:__imp_GetObjectW
0x18000a8f5  nop     dword ptr [rax+rax+00h]
0x18000a8fa  mov     rcx, rsi; hWnd
0x18000a8fd  call    cs:__imp_GetDC
0x18000a904  nop     dword ptr [rax+rax+00h]
0x18000a909  xor     r9d, r9d; lParam
0x18000a90c  xor     r8d, r8d; wParam
0x18000a90f  mov     rcx, rsi; hWnd
0x18000a912  mov     rdi, rax
0x18000a915  lea     edx, [r9+31h]; Msg
0x18000a919  call    cs:__imp_SendMessageW
0x18000a920  nop     dword ptr [rax+rax+00h]
0x18000a925  mov     rbx, rax
0x18000a928  test    rax, rax
0x18000a92b  jz      short loc_18000A942
0x18000a92d  mov     rdx, rax; h
0x18000a930  mov     rcx, rdi; hdc
0x18000a933  call    cs:__imp_SelectObject
0x18000a93a  nop     dword ptr [rax+rax+00h]
0x18000a93f  mov     rbx, rax
0x18000a942  xorps   xmm0, xmm0
0x18000a945  lea     rdx, [rsp+78h+tm]; lptm
0x18000a94a  movups  xmmword ptr [rsp+78h+tm.tmOverhang], xmm0
0x18000a94f  mov     rcx, rdi; hdc
0x18000a952  movups  xmmword ptr [rsp+78h+tm.tmFirstChar], xmm0
0x18000a957  movups  xmmword ptr [rsp+78h+tm.tmHeight], xmm0
0x18000a95c  movups  xmmword ptr [rsp+78h+tm.tmExternalLeading], xmm0
0x18000a961  call    cs:__imp_GetTextMetricsW
0x18000a968  nop     dword ptr [rax+rax+00h]
0x18000a96d  test    rbx, rbx
0x18000a970  jz      short loc_18000A984
0x18000a972  mov     rdx, rbx; h
0x18000a975  mov     rcx, rdi; hdc
0x18000a978  call    cs:__imp_SelectObject
0x18000a97f  nop     dword ptr [rax+rax+00h]
0x18000a984  mov     rdx, rdi; hDC
0x18000a987  mov     rcx, rsi; hWnd
0x18000a98a  call    cs:__imp_ReleaseDC
0x18000a991  nop     dword ptr [rax+rax+00h]
0x18000a996  mov     eax, [rsp+78h+tm.tmHeight]
0x18000a99a  cmp     eax, cs:dword_1800237A8
0x18000a9a0  cmovl   eax, cs:dword_1800237A8
0x18000a9a7  mov     rcx, [rsp+78h+var_18]
0x18000a9ac  xor     rcx, rsp; StackCookie
0x18000a9af  call    __security_check_cookie
0x18000a9b4  lea     r11, [rsp+78h+var_8]
0x18000a9b9  mov     rbx, [r11+18h]
0x18000a9bd  mov     rsi, [r11+20h]
0x18000a9c1  mov     rsp, r11
0x18000a9c4  pop     rdi
0x18000a9c5  retn
```
