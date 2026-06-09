# SetDIBits

- ea: `0x18001f0a0`
- end: `0x18001f267`
- name: `SetDIBits`
- size: `455`
- prototype: `int __stdcall(HDC hdc, HBITMAP hbm, UINT start, UINT cLines, const void *lpBits, const BITMAPINFO *lpbmi, UINT ColorUse)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180059230`
- `0x1800785d4`
- `0x18008e84c`

## callees

- `0x18000d6c0`
- `0x18001f0a0`
- `0x18001f270`
- `0x18001f310`
- `0x18001fe20`

## import_xrefs

- `GDI32!DeleteDC` at `0x18001f23b`
- `GDI32!DeleteDC` at `0x18001f23b`
- `GDI32!RestoreDC` at `0x18001f1e5`
- `GDI32!RestoreDC` at `0x18001f1e5`
- `GDI32!SaveDC` at `0x18001f20b`
- `GDI32!SaveDC` at `0x18001f20b`
- `GDI32!SelectObject` at `0x18001f13e`
- `GDI32!SelectObject` at `0x18001f1d5`
- `GDI32!SelectObject` at `0x18001f13e`
- `GDI32!SelectObject` at `0x18001f1d5`
- `GDI32!GdiSetLastError` at `0x18001f248`
- `GDI32!GdiSetLastError` at `0x18001f248`
- `win32u!NtGdiGetDCforBitmap` at `0x18001f10f`
- `win32u!NtGdiGetDCforBitmap` at `0x18001f10f`

## pseudocode

```c
int __stdcall SetDIBits(
        HDC hdc,
        HBITMAP hbm,
        UINT start,
        UINT cLines,
        const void *lpBits,
        const BITMAPINFO *lpbmi,
        UINT ColorUse)
{
  int v9; // ebp
  HDC DCforBitmap; // rax
  HDC CompatibleDC; // rbx
  bool v12; // zf
  int v13; // r14d
  HGDIOBJ v14; // r12
  HPALETTE v15; // rsi
  LONG h; // ecx
  LONG biWidth_low; // r9d
  HPALETTE DCObject; // rax

  if ( !lpBits || (BYTE2(hbm) & 0x1F) != 5 )
    return 0;
  v9 = 1;
  if ( lpbmi && lpbmi->bmiHeader.biSize >= 0x28 && lpbmi->bmiHeader.biCompression - 4 <= 1 )
  {
    GdiSetLastError(87);
    return 0;
  }
  DCforBitmap = (HDC)NtGdiGetDCforBitmap(hbm);
  CompatibleDC = DCforBitmap;
  if ( DCforBitmap )
  {
    v9 = 0;
    v12 = SaveDC(DCforBitmap) == 0;
  }
  else
  {
    CompatibleDC = CreateCompatibleDC(hdc);
    v12 = CompatibleDC == 0;
  }
  if ( v12 )
    return 0;
  v13 = 0;
  v14 = SelectObject(CompatibleDC, hbm);
  if ( v14 )
  {
    v15 = 0;
    if ( hdc )
    {
      DCObject = (HPALETTE)GetDCObject(hdc, 0x80000);
      v15 = SelectPalette(CompatibleDC, DCObject, 0);
    }
    if ( lpbmi->bmiHeader.biSize < 0x28 )
    {
      biWidth_low = LOWORD(lpbmi->bmiHeader.biWidth);
      h = HIWORD(lpbmi->bmiHeader.biWidth);
    }
    else
    {
      h = lpbmi->bmiHeader.biHeight;
      biWidth_low = lpbmi->bmiHeader.biWidth;
      if ( h < 0 )
        h = -h;
    }
    v13 = SetDIBitsToDevice(CompatibleDC, 0, 0, biWidth_low, h, 0, 0, start, cLines, lpBits, lpbmi, ColorUse);
    if ( hdc )
      SelectPalette(CompatibleDC, v15, 0);
    SelectObject(CompatibleDC, v14);
  }
  if ( v9 )
    DeleteDC(CompatibleDC);
  else
    RestoreDC(CompatibleDC, -1);
  return v13;
}

```

## disassembly

```asm
0x18001f0a0  mov     [rsp+arg_0], rbx
0x18001f0a5  mov     [rsp+arg_18], r9d
0x18001f0aa  mov     [rsp+arg_10], r8d
0x18001f0af  push    rbp
0x18001f0b0  push    rsi
0x18001f0b1  push    rdi
0x18001f0b2  push    r12
0x18001f0b4  push    r13
0x18001f0b6  push    r14
0x18001f0b8  push    r15
0x18001f0ba  sub     rsp, 60h
0x18001f0be  mov     r13, [rsp+98h+lpBits]
0x18001f0c6  mov     rsi, rdx
0x18001f0c9  mov     r15, rcx
0x18001f0cc  test    r13, r13
0x18001f0cf  jz      loc_18001F24E
0x18001f0d5  mov     rax, rdx
0x18001f0d8  shr     rax, 10h
0x18001f0dc  and     eax, 1Fh
0x18001f0df  cmp     al, 5
0x18001f0e1  jnz     loc_18001F24E
0x18001f0e7  mov     rdi, [rsp+98h+lpbmi]
0x18001f0ef  mov     ebp, 1
0x18001f0f4  test    rdi, rdi
0x18001f0f7  jz      short loc_18001F10C
0x18001f0f9  cmp     dword ptr [rdi], 28h ; '('
0x18001f0fc  jb      short loc_18001F10C
0x18001f0fe  mov     eax, [rdi+10h]
0x18001f101  sub     eax, 4
0x18001f104  cmp     eax, ebp
0x18001f106  jbe     loc_18001F243
0x18001f10c  mov     rcx, rsi
0x18001f10f  call    cs:__imp_NtGdiGetDCforBitmap
0x18001f115  mov     rbx, rax
0x18001f118  test    rax, rax
0x18001f11b  jnz     loc_18001F206
0x18001f121  mov     rcx, r15; hdc
0x18001f124  call    CreateCompatibleDC
0x18001f129  mov     rbx, rax
0x18001f12c  test    rax, rax
0x18001f12f  jz      loc_18001F24E
0x18001f135  mov     rdx, rsi; h
0x18001f138  mov     rcx, rbx; hdc
0x18001f13b  xor     r14d, r14d
0x18001f13e  call    cs:__imp_SelectObject
0x18001f144  mov     r12, rax
0x18001f147  test    rax, rax
0x18001f14a  jz      loc_18001F1DB
0x18001f150  xor     esi, esi
0x18001f152  test    r15, r15
0x18001f155  jnz     loc_18001F218
0x18001f15b  cmp     dword ptr [rdi], 28h ; '('
0x18001f15e  jb      loc_18001F252
0x18001f164  mov     ecx, [rdi+8]
0x18001f167  mov     r9d, [rdi+4]; w
0x18001f16b  test    ecx, ecx
0x18001f16d  js      loc_18001F260
0x18001f173  mov     eax, [rsp+98h+ColorUse]
0x18001f17a  xor     r8d, r8d; yDest
0x18001f17d  mov     [rsp+98h+var_40], eax; ColorUse
0x18001f181  xor     edx, edx; xDest
0x18001f183  mov     eax, [rsp+98h+arg_18]
0x18001f18a  mov     [rsp+98h+var_48], rdi; lpbmi
0x18001f18f  mov     [rsp+98h+lpvBits], r13; lpvBits
0x18001f194  mov     [rsp+98h+cLines], eax; cLines
0x18001f198  mov     eax, [rsp+98h+arg_10]
0x18001f19f  mov     [rsp+98h+StartScan], eax; StartScan
0x18001f1a3  mov     [rsp+98h+ySrc], r14d; ySrc
0x18001f1a8  mov     [rsp+98h+xSrc], r14d; xSrc
0x18001f1ad  mov     [rsp+98h+h], ecx; h
0x18001f1b1  mov     rcx, rbx; hdc
0x18001f1b4  call    SetDIBitsToDevice
0x18001f1b9  mov     r14d, eax
0x18001f1bc  test    r15, r15
0x18001f1bf  jz      short loc_18001F1CF
0x18001f1c1  xor     r8d, r8d; bForceBkgd
0x18001f1c4  mov     rdx, rsi; hPal
0x18001f1c7  mov     rcx, rbx; hdc
0x18001f1ca  call    SelectPalette
0x18001f1cf  mov     rdx, r12; h
0x18001f1d2  mov     rcx, rbx; hdc
0x18001f1d5  call    cs:__imp_SelectObject
0x18001f1db  mov     rcx, rbx; hdc
0x18001f1de  test    ebp, ebp
0x18001f1e0  jnz     short loc_18001F23B
0x18001f1e2  or      edx, 0FFFFFFFFh; nSavedDC
0x18001f1e5  call    cs:__imp_RestoreDC
0x18001f1eb  mov     eax, r14d
0x18001f1ee  mov     rbx, [rsp+98h+arg_0]
0x18001f1f6  add     rsp, 60h
0x18001f1fa  pop     r15
0x18001f1fc  pop     r14
0x18001f1fe  pop     r13
0x18001f200  pop     r12
0x18001f202  pop     rdi
0x18001f203  pop     rsi
0x18001f204  pop     rbp
0x18001f205  retn
0x18001f206  mov     rcx, rax; hdc
0x18001f209  xor     ebp, ebp
0x18001f20b  call    cs:__imp_SaveDC
0x18001f211  test    eax, eax
0x18001f213  jmp     loc_18001F12F
0x18001f218  mov     edx, 80000h
0x18001f21d  mov     rcx, r15
0x18001f220  call    GetDCObject
0x18001f225  xor     r8d, r8d; bForceBkgd
0x18001f228  mov     rdx, rax; hPal
0x18001f22b  mov     rcx, rbx; hdc
0x18001f22e  call    SelectPalette
0x18001f233  mov     rsi, rax
0x18001f236  jmp     loc_18001F15B
0x18001f23b  call    cs:__imp_DeleteDC
0x18001f241  jmp     short loc_18001F1EB
0x18001f243  mov     ecx, 57h ; 'W'
0x18001f248  call    cs:__imp_GdiSetLastError
0x18001f24e  xor     eax, eax
0x18001f250  jmp     short loc_18001F1EE
0x18001f252  movzx   r9d, word ptr [rdi+4]
0x18001f257  movzx   ecx, word ptr [rdi+6]
0x18001f25b  jmp     loc_18001F173
0x18001f260  neg     ecx
0x18001f262  jmp     loc_18001F173
```
