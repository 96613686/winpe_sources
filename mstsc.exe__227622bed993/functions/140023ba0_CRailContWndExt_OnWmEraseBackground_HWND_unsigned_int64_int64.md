# CRailContWndExt::OnWmEraseBackground(HWND__ *,unsigned __int64,__int64)

- ea: `0x140023ba0`
- end: `0x140023d15`
- name: `?OnWmEraseBackground@CRailContWndExt@@UEAA_JPEAUHWND__@@_K_J@Z`
- size: `373`
- prototype: `__int64(CRailContWndExt *__hidden this, HWND, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x140023ba0`
- `0x14004bcfc`
- `0x1400a4ab4`
- `0x140111220`

## import_xrefs

- `USER32!GetClientRect` at `0x140023c6b`
- `USER32!GetClientRect` at `0x140023c6b`
- `GDI32!PatBlt` at `0x140023c9a`
- `GDI32!PatBlt` at `0x140023c9a`
- `GDI32!SelectObject` at `0x140023c77`
- `GDI32!SelectObject` at `0x140023c77`
- `GDI32!CreateSolidBrush` at `0x140023c55`
- `GDI32!CreateSolidBrush` at `0x140023c55`
- `GDI32!RealizePalette` at `0x140023bf9`
- `GDI32!RealizePalette` at `0x140023bf9`
- `GDI32!SelectPalette` at `0x140023bed`
- `GDI32!SelectPalette` at `0x140023c32`
- `GDI32!SelectPalette` at `0x140023bed`
- `GDI32!SelectPalette` at `0x140023c32`
- `GDI32!DeleteObject` at `0x140023ca3`
- `GDI32!DeleteObject` at `0x140023ca3`

## pseudocode

```c
__int64 __fastcall CRailContWndExt::OnWmEraseBackground(CRailContWndExt *this, HWND a2, HDC a3)
{
  __int64 v5; // rdx
  HPALETTE v7; // rdx
  HPALETTE v8; // rsi
  CBrandingBar *v9; // rcx
  CProgressBand *v10; // rcx
  HBRUSH SolidBrush; // rbx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  struct tagRECT Rect; // [rsp+30h] [rbp-38h] BYREF

  v5 = *((_QWORD *)this + 2);
  if ( v5 && *((_QWORD *)this + 3) )
  {
    v7 = *(HPALETTE *)(v5 + 24);
    v8 = 0;
    if ( v7 )
    {
      v8 = SelectPalette(a3, v7, 0);
      RealizePalette(a3);
    }
    v9 = (CBrandingBar *)*((_QWORD *)this + 2);
    if ( v9 )
      CBrandingBar::OnWmPaint(v9, a3);
    v10 = (CProgressBand *)*((_QWORD *)this + 3);
    if ( v10 )
      CProgressBand::OnEraseParentBackground(v10, a3);
    if ( v8 )
      SelectPalette(a3, v8, 1);
    if ( (*((_DWORD *)this + 517) & 0x100) != 0 )
    {
      Rect = 0;
      SolidBrush = CreateSolidBrush(0xFFFFFFu);
      if ( SolidBrush )
      {
        GetClientRect(a2, &Rect);
        SelectObject(a3, SolidBrush);
        PatBlt(a3, 0, 0, Rect.right, Rect.bottom, 0xF00021u);
        DeleteObject(SolidBrush);
        return 1;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          65,
          &WPP_054707ce312e306d358833de4c0f150b_Traceguids,
          CurrentThreadActivityIdPrefix);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140023ba0  mov     [rsp+arg_18], rbx
0x140023ba5  push    rbp
0x140023ba6  push    rsi
0x140023ba7  push    rdi
0x140023ba8  sub     rsp, 50h
0x140023bac  mov     rax, cs:__security_cookie
0x140023bb3  xor     rax, rsp
0x140023bb6  mov     [rsp+68h+var_28], rax
0x140023bbb  mov     rbp, rdx
0x140023bbe  mov     rdi, r8
0x140023bc1  mov     rdx, [rcx+10h]
0x140023bc5  mov     rbx, rcx
0x140023bc8  test    rdx, rdx
0x140023bcb  jz      loc_140023CF6
0x140023bd1  cmp     qword ptr [rcx+18h], 0
0x140023bd6  jz      loc_140023CF6
0x140023bdc  mov     rdx, [rdx+18h]; hPal
0x140023be0  xor     esi, esi
0x140023be2  test    rdx, rdx
0x140023be5  jz      short loc_140023BFF
0x140023be7  xor     r8d, r8d; bForceBkgd
0x140023bea  mov     rcx, rdi; hdc
0x140023bed  call    cs:__imp_SelectPalette
0x140023bf3  mov     rcx, rdi; hdc
0x140023bf6  mov     rsi, rax
0x140023bf9  call    cs:__imp_RealizePalette
0x140023bff  mov     rcx, [rbx+10h]; this
0x140023c03  test    rcx, rcx
0x140023c06  jz      short loc_140023C10
0x140023c08  mov     rdx, rdi; HDC
0x140023c0b  call    ?OnWmPaint@CBrandingBar@@QEAAXPEAUHDC__@@@Z; CBrandingBar::OnWmPaint(HDC__ *)
0x140023c10  mov     rcx, [rbx+18h]; this
0x140023c14  test    rcx, rcx
0x140023c17  jz      short loc_140023C21
0x140023c19  mov     rdx, rdi; HDC
0x140023c1c  call    ?OnEraseParentBackground@CProgressBand@@QEAAHPEAUHDC__@@@Z; CProgressBand::OnEraseParentBackground(HDC__ *)
0x140023c21  test    rsi, rsi
0x140023c24  jz      short loc_140023C38
0x140023c26  mov     r8d, 1; bForceBkgd
0x140023c2c  mov     rdx, rsi; hPal
0x140023c2f  mov     rcx, rdi; hdc
0x140023c32  call    cs:__imp_SelectPalette
0x140023c38  test    dword ptr [rbx+814h], 100h
0x140023c42  jz      loc_140023CF6
0x140023c48  xorps   xmm0, xmm0
0x140023c4b  mov     ecx, 0FFFFFFh; color
0x140023c50  movups  xmmword ptr [rsp+68h+Rect.left], xmm0
0x140023c55  call    cs:__imp_CreateSolidBrush
0x140023c5b  mov     rbx, rax
0x140023c5e  test    rax, rax
0x140023c61  jz      short loc_140023CB0
0x140023c63  lea     rdx, [rsp+68h+Rect]; lpRect
0x140023c68  mov     rcx, rbp; hWnd
0x140023c6b  call    cs:__imp_GetClientRect
0x140023c71  mov     rdx, rbx; h
0x140023c74  mov     rcx, rdi; hdc
0x140023c77  call    cs:__imp_SelectObject
0x140023c7d  mov     edx, [rsp+68h+Rect.bottom]
0x140023c81  xor     r8d, r8d; y
0x140023c84  mov     r9d, [rsp+68h+Rect.right]; w
0x140023c89  mov     rcx, rdi; hdc
0x140023c8c  mov     [rsp+68h+rop], 0F00021h; rop
0x140023c94  mov     [rsp+68h+h], edx; h
0x140023c98  xor     edx, edx; x
0x140023c9a  call    cs:__imp_PatBlt
0x140023ca0  mov     rcx, rbx; ho
0x140023ca3  call    cs:__imp_DeleteObject
0x140023ca9  mov     eax, 1
0x140023cae  jmp     short loc_140023CF8
0x140023cb0  mov     rax, cs:WPP_GLOBAL_Control
0x140023cb7  lea     rcx, WPP_GLOBAL_Control
0x140023cbe  cmp     rax, rcx
0x140023cc1  jz      short loc_140023CF6
0x140023cc3  test    dword ptr [rax+1Ch], 1000h
0x140023cca  jz      short loc_140023CF6
0x140023ccc  cmp     byte ptr [rax+19h], 2
0x140023cd0  jb      short loc_140023CF6
0x140023cd2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140023cd7  mov     rcx, cs:WPP_GLOBAL_Control
0x140023cde  lea     r8, WPP_054707ce312e306d358833de4c0f150b_Traceguids
0x140023ce5  mov     edx, 41h ; 'A'
0x140023cea  mov     r9d, eax
0x140023ced  mov     rcx, [rcx+10h]
0x140023cf1  call    WPP_SF_d
0x140023cf6  xor     eax, eax
0x140023cf8  mov     rcx, [rsp+68h+var_28]
0x140023cfd  xor     rcx, rsp; StackCookie
0x140023d00  call    __security_check_cookie
0x140023d05  mov     rbx, [rsp+68h+arg_18]
0x140023d0d  add     rsp, 50h
0x140023d11  pop     rdi
0x140023d12  pop     rsi
0x140023d13  pop     rbp
0x140023d14  retn
```
