# CLVDrawState::SetLabelFont(HFONT__ *)

- ea: `0x180077b9c`
- end: `0x180077ce6`
- name: `?SetLabelFont@CLVDrawState@@QEAAXPEAUHFONT__@@@Z`
- size: `330`
- prototype: `void __fastcall(CLVDrawState *__hidden this, HFONT)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180075db0`
- `0x18007664c`
- `0x180077618`

## callees

- `0x18004c6f0`
- `0x180077b9c`
- `0x180077cec`
- `0x180114520`

## import_xrefs

- `GDI32!DeleteObject` at `0x180077cc5`
- `GDI32!DeleteObject` at `0x180077cd4`
- `GDI32!DeleteObject` at `0x180077cc5`
- `GDI32!DeleteObject` at `0x180077cd4`
- `GDI32!GetTextMetricsW` at `0x180077c43`
- `GDI32!GetTextMetricsW` at `0x180077c43`
- `GDI32!SelectObject` at `0x180077c1b`
- `GDI32!SelectObject` at `0x180077c88`
- `GDI32!SelectObject` at `0x180077c1b`
- `GDI32!SelectObject` at `0x180077c88`
- `GDI32!GetTextExtentPointW` at `0x180077c75`
- `GDI32!GetTextExtentPointW` at `0x180077c75`
- `USER32!GetDC` at `0x180077c02`
- `USER32!GetDC` at `0x180077c02`
- `USER32!ReleaseDC` at `0x180077c93`
- `USER32!ReleaseDC` at `0x180077c93`

## pseudocode

```c
void __fastcall CLVDrawState::SetLabelFont(CLVDrawState *this, HFONT a2)
{
  void *v4; // rcx
  HDC DC; // rax
  HDC v6; // rsi
  HGDIOBJ v7; // rbx
  void *v8; // rcx
  struct tagSIZE sz; // [rsp+20h] [rbp-58h] BYREF
  struct tagTEXTMETRICW tm; // [rsp+28h] [rbp-50h] BYREF

  if ( *((_BYTE *)this + 36) )
  {
    v8 = (void *)*((_QWORD *)this + 5);
    if ( v8 )
    {
      DeleteObject(v8);
      *((_BYTE *)this + 36) = 0;
    }
  }
  *((_QWORD *)this + 5) = a2;
  if ( !a2 )
  {
    *((_QWORD *)this + 5) = DPISCALEINFO::CreateIconTitleFont(*((DPISCALEINFO **)this + 10));
    *((_BYTE *)this + 36) = 1;
  }
  v4 = (void *)*((_QWORD *)this + 6);
  if ( v4 )
  {
    DeleteObject(v4);
    *((_QWORD *)this + 6) = 0;
  }
  DPISCALEINFO::EnsureHotFont((DPISCALEINFO *)v4, *((HFONT *)this + 5), (HFONT *)this + 6);
  DC = GetDC(0);
  v6 = DC;
  if ( DC )
  {
    v7 = SelectObject(DC, *((HGDIOBJ *)this + 5));
    memset(&tm, 0, sizeof(tm));
    GetTextMetricsW(v6, &tm);
    *((_DWORD *)this + 5) = tm.tmHeight;
    *((_DWORD *)this + 4) = tm.tmAveCharWidth;
    sz = 0;
    GetTextExtentPointW(v6, L"...", 3, &sz);
    *((_DWORD *)this + 8) = sz.cx;
    SelectObject(v6, v7);
    ReleaseDC(0, v6);
  }
}

```

## disassembly

```asm
0x180077b9c  mov     [rsp+arg_8], rbx
0x180077ba1  mov     [rsp+arg_10], rsi
0x180077ba6  push    rdi
0x180077ba7  sub     rsp, 70h
0x180077bab  mov     rax, cs:__security_cookie
0x180077bb2  xor     rax, rsp
0x180077bb5  mov     [rsp+78h+var_10], rax
0x180077bba  cmp     byte ptr [rcx+24h], 0
0x180077bbe  mov     rbx, rdx
0x180077bc1  mov     rdi, rcx
0x180077bc4  jnz     loc_180077CB8
0x180077bca  mov     [rdi+28h], rbx
0x180077bce  test    rbx, rbx
0x180077bd1  jnz     short loc_180077BE4
0x180077bd3  mov     rcx, [rdi+50h]; this
0x180077bd7  call    ?CreateIconTitleFont@DPISCALEINFO@@QEBAPEAUHFONT__@@XZ; DPISCALEINFO::CreateIconTitleFont(void)
0x180077bdc  mov     [rdi+28h], rax
0x180077be0  mov     byte ptr [rdi+24h], 1
0x180077be4  lea     rbx, [rdi+30h]
0x180077be8  mov     rcx, [rbx]; this
0x180077beb  test    rcx, rcx
0x180077bee  jnz     loc_180077CD4
0x180077bf4  mov     rdx, [rdi+28h]; HFONT
0x180077bf8  mov     r8, rbx; HFONT *
0x180077bfb  call    ?EnsureHotFont@DPISCALEINFO@@QEBAPEAUHFONT__@@PEAU2@PEAPEAU2@@Z; DPISCALEINFO::EnsureHotFont(HFONT__ *,HFONT__ * *)
0x180077c00  xor     ecx, ecx; hWnd
0x180077c02  call    cs:__imp_GetDC
0x180077c08  mov     rsi, rax
0x180077c0b  test    rax, rax
0x180077c0e  jz      loc_180077C99
0x180077c14  mov     rdx, [rdi+28h]; h
0x180077c18  mov     rcx, rax; hdc
0x180077c1b  call    cs:__imp_SelectObject
0x180077c21  xorps   xmm0, xmm0
0x180077c24  lea     rdx, [rsp+78h+tm]; lptm
0x180077c29  movups  xmmword ptr [rsp+78h+tm.tmOverhang], xmm0
0x180077c2e  mov     rcx, rsi; hdc
0x180077c31  mov     rbx, rax
0x180077c34  movups  xmmword ptr [rsp+78h+tm.tmFirstChar], xmm0
0x180077c39  movups  xmmword ptr [rsp+78h+tm.tmHeight], xmm0
0x180077c3e  movups  xmmword ptr [rsp+78h+tm.tmExternalLeading], xmm0
0x180077c43  call    cs:__imp_GetTextMetricsW
0x180077c49  mov     ecx, [rsp+78h+tm.tmHeight]
0x180077c4d  lea     r9, [rsp+78h+sz]; lpsz
0x180077c52  mov     [rdi+14h], ecx
0x180077c55  lea     rdx, c_szEllipses; "..."
0x180077c5c  mov     ecx, [rsp+78h+tm.tmAveCharWidth]
0x180077c60  mov     r8d, 3; c
0x180077c66  mov     [rdi+10h], ecx
0x180077c69  mov     rcx, rsi; hdc
0x180077c6c  mov     qword ptr [rsp+78h+sz.cx], 0
0x180077c75  call    cs:__imp_GetTextExtentPointW
0x180077c7b  mov     eax, [rsp+78h+sz.cx]
0x180077c7f  mov     rdx, rbx; h
0x180077c82  mov     rcx, rsi; hdc
0x180077c85  mov     [rdi+20h], eax
0x180077c88  call    cs:__imp_SelectObject
0x180077c8e  mov     rdx, rsi; hDC
0x180077c91  xor     ecx, ecx; hWnd
0x180077c93  call    cs:__imp_ReleaseDC
0x180077c99  mov     rcx, [rsp+78h+var_10]
0x180077c9e  xor     rcx, rsp; StackCookie
0x180077ca1  call    __security_check_cookie
0x180077ca6  lea     r11, [rsp+78h+var_8]
0x180077cab  mov     rbx, [r11+18h]
0x180077caf  mov     rsi, [r11+20h]
0x180077cb3  mov     rsp, r11
0x180077cb6  pop     rdi
0x180077cb7  retn
0x180077cb8  mov     rcx, [rcx+28h]; ho
0x180077cbc  test    rcx, rcx
0x180077cbf  jz      loc_180077BCA
0x180077cc5  call    cs:__imp_DeleteObject
0x180077ccb  mov     byte ptr [rdi+24h], 0
0x180077ccf  jmp     loc_180077BCA
0x180077cd4  call    cs:__imp_DeleteObject
0x180077cda  mov     qword ptr [rbx], 0
0x180077ce1  jmp     loc_180077BF4
```
