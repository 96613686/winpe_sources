# CHintWnd::OnEraseBackground(HDC__ *)

- ea: `0x180155994`
- end: `0x180155b74`
- name: `?OnEraseBackground@CHintWnd@@IEAAXPEAUHDC__@@@Z`
- size: `480`
- prototype: `void(CHintWnd *__hidden this, HDC)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1801563b0`

## callees

- `0x180039c98`
- `0x180039ce4`
- `0x180155994`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180155a8f`
- `KERNEL32!GetLastError` at `0x180155b22`
- `KERNEL32!GetLastError` at `0x180155a8f`
- `KERNEL32!GetLastError` at `0x180155b22`
- `GDI32!DeleteObject` at `0x180155a4d`
- `GDI32!DeleteObject` at `0x180155aed`
- `GDI32!DeleteObject` at `0x180155a4d`
- `GDI32!DeleteObject` at `0x180155aed`
- `GDI32!DeleteDC` at `0x180155afb`
- `GDI32!DeleteDC` at `0x180155afb`
- `GDI32!SelectObject` at `0x180155a20`
- `GDI32!SelectObject` at `0x180155ae4`
- `GDI32!SelectObject` at `0x180155a20`
- `GDI32!SelectObject` at `0x180155ae4`
- `GDI32!CreateCompatibleDC` at `0x1801559ff`
- `GDI32!CreateCompatibleDC` at `0x1801559ff`
- `GDI32!BitBlt` at `0x180155a85`
- `GDI32!BitBlt` at `0x180155a85`
- `GDI32!CreateCompatibleBitmap` at `0x1801559f3`
- `GDI32!CreateCompatibleBitmap` at `0x1801559f3`
- `GDI32!CreateSolidBrush` at `0x180155a2b`
- `GDI32!CreateSolidBrush` at `0x180155a2b`
- `USER32!FillRect` at `0x180155a44`
- `USER32!FillRect` at `0x180155a44`
- `USER32!GetClientRect` at `0x1801559d9`
- `USER32!GetClientRect` at `0x1801559d9`
- `USER32!GetSysColor` at `0x1801559c8`
- `USER32!GetSysColor` at `0x1801559c8`

## pseudocode

```c
void __fastcall CHintWnd::OnEraseBackground(HWND *this, HDC a2)
{
  COLORREF SysColor; // edi
  HBITMAP CompatibleBitmap; // rsi
  HDC CompatibleDC; // rax
  HDC hdcSrc; // rbx
  HGDIOBJ v8; // r14
  HBRUSH SolidBrush; // rax
  HBRUSH v10; // rdi
  DWORD LastError; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  DWORD v13; // ebx
  unsigned int v14; // eax
  struct tagRECT Rect; // [rsp+50h] [rbp-38h] BYREF

  Rect = 0;
  SysColor = GetSysColor(24);
  if ( GetClientRect(this[6], &Rect) )
  {
    CompatibleBitmap = CreateCompatibleBitmap(a2, Rect.right, Rect.bottom);
    CompatibleDC = CreateCompatibleDC(a2);
    hdcSrc = CompatibleDC;
    if ( CompatibleBitmap )
    {
      if ( CompatibleDC )
      {
        v8 = SelectObject(CompatibleDC, CompatibleBitmap);
        SolidBrush = CreateSolidBrush(SysColor);
        v10 = SolidBrush;
        if ( SolidBrush )
        {
          FillRect(hdcSrc, &Rect, SolidBrush);
          DeleteObject(v10);
        }
        if ( !BitBlt(a2, 0, 0, Rect.right, Rect.bottom, hdcSrc, 0, 0, 0xCC0020u) )
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              25,
              WPP_5202f0024a5f32f57ee7148868e1e98d_Traceguids,
              CurrentThreadActivityIdPrefix,
              LastError);
          }
        }
        SelectObject(hdcSrc, v8);
      }
      DeleteObject(CompatibleBitmap);
    }
    if ( hdcSrc )
      DeleteDC(hdcSrc);
  }
  else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
         && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = GetLastError();
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_5202f0024a5f32f57ee7148868e1e98d_Traceguids, v14, v13);
  }
}

```

## disassembly

```asm
0x180155994  mov     [rsp+arg_10], rbx
0x180155999  mov     [rsp+arg_18], rbp
0x18015599e  push    rsi
0x18015599f  push    rdi
0x1801559a0  push    r14
0x1801559a2  sub     rsp, 70h
0x1801559a6  mov     rax, cs:__security_cookie
0x1801559ad  xor     rax, rsp
0x1801559b0  mov     [rsp+88h+var_28], rax
0x1801559b5  mov     rbx, rcx
0x1801559b8  xorps   xmm0, xmm0
0x1801559bb  mov     ecx, 18h; nIndex
0x1801559c0  mov     rbp, rdx
0x1801559c3  movups  xmmword ptr [rsp+88h+Rect.left], xmm0
0x1801559c8  call    cs:__imp_GetSysColor
0x1801559ce  mov     rcx, [rbx+30h]; hWnd
0x1801559d2  lea     rdx, [rsp+88h+Rect]; lpRect
0x1801559d7  mov     edi, eax
0x1801559d9  call    cs:__imp_GetClientRect
0x1801559df  test    eax, eax
0x1801559e1  jz      loc_180155B03
0x1801559e7  mov     r8d, [rsp+88h+Rect.bottom]; cy
0x1801559ec  mov     rcx, rbp; hdc
0x1801559ef  mov     edx, [rsp+88h+Rect.right]; cx
0x1801559f3  call    cs:__imp_CreateCompatibleBitmap
0x1801559f9  mov     rcx, rbp; hdc
0x1801559fc  mov     rsi, rax
0x1801559ff  call    cs:__imp_CreateCompatibleDC
0x180155a05  mov     rbx, rax
0x180155a08  test    rsi, rsi
0x180155a0b  jz      loc_180155AF3
0x180155a11  test    rax, rax
0x180155a14  jz      loc_180155AEA
0x180155a1a  mov     rdx, rsi; h
0x180155a1d  mov     rcx, rax; hdc
0x180155a20  call    cs:__imp_SelectObject
0x180155a26  mov     ecx, edi; color
0x180155a28  mov     r14, rax
0x180155a2b  call    cs:__imp_CreateSolidBrush
0x180155a31  mov     rdi, rax
0x180155a34  test    rax, rax
0x180155a37  jz      short loc_180155A53
0x180155a39  mov     r8, rax; hbr
0x180155a3c  lea     rdx, [rsp+88h+Rect]; lprc
0x180155a41  mov     rcx, rbx; hDC
0x180155a44  call    cs:__imp_FillRect
0x180155a4a  mov     rcx, rdi; ho
0x180155a4d  call    cs:__imp_DeleteObject
0x180155a53  mov     eax, [rsp+88h+Rect.bottom]
0x180155a57  xor     r8d, r8d; y
0x180155a5a  mov     r9d, [rsp+88h+Rect.right]; cx
0x180155a5f  xor     edx, edx; x
0x180155a61  mov     [rsp+88h+rop], 0CC0020h; rop
0x180155a69  mov     rcx, rbp; hdc
0x180155a6c  mov     [rsp+88h+y1], 0; y1
0x180155a74  mov     [rsp+88h+x1], 0; x1
0x180155a7c  mov     [rsp+88h+hdcSrc], rbx; hdcSrc
0x180155a81  mov     [rsp+88h+cy], eax; cy
0x180155a85  call    cs:__imp_BitBlt
0x180155a8b  test    eax, eax
0x180155a8d  jnz     short loc_180155ADE
0x180155a8f  call    cs:__imp_GetLastError
0x180155a95  mov     edi, eax
0x180155a97  mov     rdx, cs:WPP_GLOBAL_Control
0x180155a9e  lea     rcx, WPP_GLOBAL_Control
0x180155aa5  cmp     rdx, rcx
0x180155aa8  jz      short loc_180155ADE
0x180155aaa  test    byte ptr [rdx+1Ch], 8
0x180155aae  jz      short loc_180155ADE
0x180155ab0  cmp     byte ptr [rdx+19h], 2
0x180155ab4  jb      short loc_180155ADE
0x180155ab6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180155abb  mov     rcx, cs:WPP_GLOBAL_Control
0x180155ac2  lea     r8, WPP_5202f0024a5f32f57ee7148868e1e98d_Traceguids
0x180155ac9  mov     edx, 19h
0x180155ace  mov     [rsp+88h+cy], edi
0x180155ad2  mov     r9d, eax
0x180155ad5  mov     rcx, [rcx+10h]
0x180155ad9  call    WPP_SF_Dd
0x180155ade  mov     rdx, r14; h
0x180155ae1  mov     rcx, rbx; hdc
0x180155ae4  call    cs:__imp_SelectObject
0x180155aea  mov     rcx, rsi; ho
0x180155aed  call    cs:__imp_DeleteObject
0x180155af3  test    rbx, rbx
0x180155af6  jz      short loc_180155B52
0x180155af8  mov     rcx, rbx; hdc
0x180155afb  call    cs:__imp_DeleteDC
0x180155b01  jmp     short loc_180155B52
0x180155b03  mov     rax, cs:WPP_GLOBAL_Control
0x180155b0a  lea     rcx, WPP_GLOBAL_Control
0x180155b11  cmp     rax, rcx
0x180155b14  jz      short loc_180155B52
0x180155b16  test    byte ptr [rax+1Ch], 1
0x180155b1a  jz      short loc_180155B52
0x180155b1c  cmp     byte ptr [rax+19h], 2
0x180155b20  jb      short loc_180155B52
0x180155b22  call    cs:__imp_GetLastError
0x180155b28  mov     ebx, eax
0x180155b2a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180155b2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180155b36  lea     r8, WPP_5202f0024a5f32f57ee7148868e1e98d_Traceguids
0x180155b3d  mov     edx, 1Ah
0x180155b42  mov     [rsp+88h+cy], ebx
0x180155b46  mov     r9d, eax
0x180155b49  mov     rcx, [rcx+10h]
0x180155b4d  call    WPP_SF_Dd
0x180155b52  mov     rcx, [rsp+88h+var_28]
0x180155b57  xor     rcx, rsp; StackCookie
0x180155b5a  call    __security_check_cookie
0x180155b5f  lea     r11, [rsp+88h+var_18]
0x180155b64  mov     rbx, [r11+30h]
0x180155b68  mov     rbp, [r11+38h]
0x180155b6c  mov     rsp, r11
0x180155b6f  pop     r14
0x180155b71  pop     rdi
0x180155b72  pop     rsi
0x180155b73  retn
```
