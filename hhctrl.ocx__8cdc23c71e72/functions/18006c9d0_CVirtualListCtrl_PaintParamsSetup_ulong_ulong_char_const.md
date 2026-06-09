# CVirtualListCtrl::PaintParamsSetup(ulong,ulong,char const *)

- ea: `0x18006c9d0`
- end: `0x18006cae7`
- name: `?PaintParamsSetup@CVirtualListCtrl@@QEAAXKKPEBD@Z`
- size: `279`
- prototype: `void(CVirtualListCtrl *__hidden this, unsigned int, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18003b090`

## callees

- `0x18002cab4`
- `0x180037594`
- `0x180066f30`
- `0x18006c9d0`
- `0x180075c90`

## import_xrefs

- `USER32!GetWindowDC` at `0x18006ca10`
- `USER32!GetWindowDC` at `0x18006ca10`
- `USER32!ReleaseDC` at `0x18006ca4e`
- `USER32!ReleaseDC` at `0x18006ca4e`
- `GDI32!GetObjectA` at `0x18006cab3`
- `GDI32!GetObjectA` at `0x18006cab3`
- `GDI32!GetNearestColor` at `0x18006ca27`
- `GDI32!GetNearestColor` at `0x18006ca35`
- `GDI32!GetNearestColor` at `0x18006ca27`
- `GDI32!GetNearestColor` at `0x18006ca35`
- `GDI32!CreateSolidBrush` at `0x18006ca5c`
- `GDI32!CreateSolidBrush` at `0x18006ca5c`

## pseudocode

```c
void __fastcall CVirtualListCtrl::PaintParamsSetup(CVirtualListCtrl *this, COLORREF a2, COLORREF a3, const char *a4)
{
  HDC WindowDC; // rbp
  COLORREF NearestColor; // ebx
  COLORREF v10; // ecx
  struct CHtmlHelpControl *v11; // r9
  void *v12; // rcx
  _OWORD pv[2]; // [rsp+20h] [rbp-178h] BYREF
  char v14[272]; // [rsp+40h] [rbp-158h] BYREF

  if ( a2 != -1 && a3 != -1 )
  {
    WindowDC = GetWindowDC(*((HWND *)this + 5));
    if ( (unsigned int)GetHighContrastFlag()
      || (NearestColor = GetNearestColor(WindowDC, a3), GetNearestColor(WindowDC, a2) == NearestColor) )
    {
      *((_DWORD *)this + 24) = -1;
      *((_DWORD *)this + 25) = -1;
    }
    ReleaseDC(*((HWND *)this + 5), WindowDC);
  }
  v10 = *((_DWORD *)this + 25);
  if ( v10 != -1 )
    *((_QWORD *)this + 9) = CreateSolidBrush(v10);
  if ( a4 && (unsigned int)ConvertToCacheFile(a4, v14, 0x104u) )
  {
    if ( (unsigned int)LoadGif(v14, (HBITMAP *)this + 10, (HPALETTE *)this + 8, v11) )
    {
      v12 = (void *)*((_QWORD *)this + 10);
      memset(pv, 0, sizeof(pv));
      GetObjectA(v12, 32, pv);
      *((_QWORD *)this + 11) = *(_QWORD *)((char *)pv + 4);
    }
  }
}

```

## disassembly

```asm
0x18006c9d0  push    rbx
0x18006c9d2  push    rbp
0x18006c9d3  push    rsi
0x18006c9d4  push    rdi
0x18006c9d5  push    r14
0x18006c9d7  push    r15
0x18006c9d9  sub     rsp, 168h
0x18006c9e0  mov     rax, cs:__security_cookie
0x18006c9e7  xor     rax, rsp
0x18006c9ea  mov     [rsp+198h+var_48], rax
0x18006c9f2  or      r15d, 0FFFFFFFFh
0x18006c9f6  mov     rsi, r9
0x18006c9f9  mov     ebx, r8d
0x18006c9fc  mov     r14d, edx
0x18006c9ff  mov     rdi, rcx
0x18006ca02  cmp     edx, r15d
0x18006ca05  jz      short loc_18006CA54
0x18006ca07  cmp     ebx, r15d
0x18006ca0a  jz      short loc_18006CA54
0x18006ca0c  mov     rcx, [rcx+28h]; hWnd
0x18006ca10  call    cs:__imp_GetWindowDC
0x18006ca16  mov     rbp, rax
0x18006ca19  call    ?GetHighContrastFlag@@YAHXZ; GetHighContrastFlag(void)
0x18006ca1e  test    eax, eax
0x18006ca20  jnz     short loc_18006CA3F
0x18006ca22  mov     edx, ebx; color
0x18006ca24  mov     rcx, rbp; hdc
0x18006ca27  call    cs:__imp_GetNearestColor
0x18006ca2d  mov     edx, r14d; color
0x18006ca30  mov     rcx, rbp; hdc
0x18006ca33  mov     ebx, eax
0x18006ca35  call    cs:__imp_GetNearestColor
0x18006ca3b  cmp     eax, ebx
0x18006ca3d  jnz     short loc_18006CA47
0x18006ca3f  mov     [rdi+60h], r15d
0x18006ca43  mov     [rdi+64h], r15d
0x18006ca47  mov     rcx, [rdi+28h]; hWnd
0x18006ca4b  mov     rdx, rbp; hDC
0x18006ca4e  call    cs:__imp_ReleaseDC
0x18006ca54  mov     ecx, [rdi+64h]; color
0x18006ca57  cmp     ecx, r15d
0x18006ca5a  jz      short loc_18006CA66
0x18006ca5c  call    cs:__imp_CreateSolidBrush
0x18006ca62  mov     [rdi+48h], rax
0x18006ca66  test    rsi, rsi
0x18006ca69  jz      short loc_18006CAC7
0x18006ca6b  mov     r8d, 104h; unsigned __int64
0x18006ca71  lea     rdx, [rsp+198h+var_158]; char *
0x18006ca76  mov     rcx, rsi; char *
0x18006ca79  call    ?ConvertToCacheFile@@YAHPEBDPEAD_K@Z; ConvertToCacheFile(char const *,char *,unsigned __int64)
0x18006ca7e  test    eax, eax
0x18006ca80  jz      short loc_18006CAC7
0x18006ca82  lea     r8, [rdi+40h]; HPALETTE *
0x18006ca86  lea     rdx, [rdi+50h]; HBITMAP *
0x18006ca8a  lea     rcx, [rsp+198h+var_158]; char *
0x18006ca8f  call    ?LoadGif@@YAHPEBDPEAPEAUHBITMAP__@@PEAPEAUHPALETTE__@@PEAVCHtmlHelpControl@@@Z; LoadGif(char const *,HBITMAP__ * *,HPALETTE__ * *,CHtmlHelpControl *)
0x18006ca94  test    eax, eax
0x18006ca96  jz      short loc_18006CAC7
0x18006ca98  mov     rcx, [rdi+50h]; h
0x18006ca9c  lea     r8, [rsp+198h+pv]; pv
0x18006caa1  xorps   xmm0, xmm0
0x18006caa4  mov     edx, 20h ; ' '; c
0x18006caa9  movups  [rsp+198h+pv], xmm0
0x18006caae  movups  [rsp+198h+var_168], xmm0
0x18006cab3  call    cs:__imp_GetObjectA
0x18006cab9  mov     eax, dword ptr [rsp+198h+pv+4]
0x18006cabd  mov     [rdi+58h], eax
0x18006cac0  mov     eax, dword ptr [rsp+198h+pv+8]
0x18006cac4  mov     [rdi+5Ch], eax
0x18006cac7  mov     rcx, [rsp+198h+var_48]
0x18006cacf  xor     rcx, rsp; StackCookie
0x18006cad2  call    __security_check_cookie
0x18006cad7  add     rsp, 168h
0x18006cade  pop     r15
0x18006cae0  pop     r14
0x18006cae2  pop     rdi
0x18006cae3  pop     rsi
0x18006cae4  pop     rbp
0x18006cae5  pop     rbx
0x18006cae6  retn
```
