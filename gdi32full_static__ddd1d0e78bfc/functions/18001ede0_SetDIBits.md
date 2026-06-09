# SetDIBits

- ea: `0x18001ede0`
- end: `0x18001efd2`
- name: `SetDIBits`
- size: `498`
- prototype: `int __stdcall(HDC hdc, HBITMAP hbm, UINT start, UINT cLines, const void *lpBits, const BITMAPINFO *lpbmi, UINT ColorUse)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18005a5b4`
- `0x18007d0ac`
- `0x180094210`

## callees

- `0x180006a28`
- `0x18001ede0`
- `0x18001efe0`
- `0x18001f090`
- `0x1800200a0`

## import_xrefs

- `GDI32!DeleteDC` at `0x18001ef9a`
- `GDI32!DeleteDC` at `0x18001ef9a`
- `GDI32!RestoreDC` at `0x18001ef37`
- `GDI32!RestoreDC` at `0x18001ef37`
- `GDI32!SaveDC` at `0x18001ef64`
- `GDI32!SaveDC` at `0x18001ef64`
- `GDI32!SelectObject` at `0x18001ee84`
- `GDI32!SelectObject` at `0x18001ef21`
- `GDI32!SelectObject` at `0x18001ee84`
- `GDI32!SelectObject` at `0x18001ef21`
- `GDI32!GdiSetLastError` at `0x18001efad`
- `GDI32!GdiSetLastError` at `0x18001efad`
- `win32u!NtGdiGetDCforBitmap` at `0x18001ee4f`
- `win32u!NtGdiGetDCforBitmap` at `0x18001ee4f`

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
0x18001ede0  mov     [rsp+arg_0], rbx
0x18001ede5  mov     [rsp+arg_18], r9d
0x18001edea  mov     [rsp+arg_10], r8d
0x18001edef  push    rbp
0x18001edf0  push    rsi
0x18001edf1  push    rdi
0x18001edf2  push    r12
0x18001edf4  push    r13
0x18001edf6  push    r14
0x18001edf8  push    r15
0x18001edfa  sub     rsp, 60h
0x18001edfe  mov     r13, [rsp+98h+lpBits]
0x18001ee06  mov     rsi, rdx
0x18001ee09  mov     r15, rcx
0x18001ee0c  test    r13, r13
0x18001ee0f  jz      loc_18001EFB9
0x18001ee15  mov     rax, rdx
0x18001ee18  shr     rax, 10h
0x18001ee1c  and     eax, 1Fh
0x18001ee1f  cmp     al, 5
0x18001ee21  jnz     loc_18001EFB9
0x18001ee27  mov     rdi, [rsp+98h+lpbmi]
0x18001ee2f  mov     ebp, 1
0x18001ee34  test    rdi, rdi
0x18001ee37  jz      short loc_18001EE4C
0x18001ee39  cmp     dword ptr [rdi], 28h ; '('
0x18001ee3c  jb      short loc_18001EE4C
0x18001ee3e  mov     eax, [rdi+10h]
0x18001ee41  sub     eax, 4
0x18001ee44  cmp     eax, ebp
0x18001ee46  jbe     loc_18001EFA8
0x18001ee4c  mov     rcx, rsi
0x18001ee4f  call    cs:__imp_NtGdiGetDCforBitmap
0x18001ee56  nop     dword ptr [rax+rax+00h]
0x18001ee5b  mov     rbx, rax
0x18001ee5e  test    rax, rax
0x18001ee61  jnz     loc_18001EF5F
0x18001ee67  mov     rcx, r15; hdc
0x18001ee6a  call    CreateCompatibleDC
0x18001ee6f  mov     rbx, rax
0x18001ee72  test    rax, rax
0x18001ee75  jz      loc_18001EFB9
0x18001ee7b  mov     rdx, rsi; h
0x18001ee7e  mov     rcx, rbx; hdc
0x18001ee81  xor     r14d, r14d
0x18001ee84  call    cs:__imp_SelectObject
0x18001ee8b  nop     dword ptr [rax+rax+00h]
0x18001ee90  mov     r12, rax
0x18001ee93  test    rax, rax
0x18001ee96  jz      loc_18001EF2D
0x18001ee9c  xor     esi, esi
0x18001ee9e  test    r15, r15
0x18001eea1  jnz     loc_18001EF77
0x18001eea7  cmp     dword ptr [rdi], 28h ; '('
0x18001eeaa  jb      loc_18001EFBD
0x18001eeb0  mov     ecx, [rdi+8]
0x18001eeb3  mov     r9d, [rdi+4]; w
0x18001eeb7  test    ecx, ecx
0x18001eeb9  js      loc_18001EFCB
0x18001eebf  mov     eax, [rsp+98h+ColorUse]
0x18001eec6  xor     r8d, r8d; yDest
0x18001eec9  mov     [rsp+98h+var_40], eax; ColorUse
0x18001eecd  xor     edx, edx; xDest
0x18001eecf  mov     eax, [rsp+98h+arg_18]
0x18001eed6  mov     [rsp+98h+var_48], rdi; lpbmi
0x18001eedb  mov     [rsp+98h+lpvBits], r13; lpvBits
0x18001eee0  mov     [rsp+98h+cLines], eax; cLines
0x18001eee4  mov     eax, [rsp+98h+arg_10]
0x18001eeeb  mov     [rsp+98h+StartScan], eax; StartScan
0x18001eeef  mov     [rsp+98h+ySrc], r14d; ySrc
0x18001eef4  mov     [rsp+98h+xSrc], r14d; xSrc
0x18001eef9  mov     [rsp+98h+h], ecx; h
0x18001eefd  mov     rcx, rbx; hdc
0x18001ef00  call    SetDIBitsToDevice
0x18001ef05  mov     r14d, eax
0x18001ef08  test    r15, r15
0x18001ef0b  jz      short loc_18001EF1B
0x18001ef0d  xor     r8d, r8d; bForceBkgd
0x18001ef10  mov     rdx, rsi; hPal
0x18001ef13  mov     rcx, rbx; hdc
0x18001ef16  call    SelectPalette
0x18001ef1b  mov     rdx, r12; h
0x18001ef1e  mov     rcx, rbx; hdc
0x18001ef21  call    cs:__imp_SelectObject
0x18001ef28  nop     dword ptr [rax+rax+00h]
0x18001ef2d  mov     rcx, rbx; hdc
0x18001ef30  test    ebp, ebp
0x18001ef32  jnz     short loc_18001EF9A
0x18001ef34  or      edx, 0FFFFFFFFh; nSavedDC
0x18001ef37  call    cs:__imp_RestoreDC
0x18001ef3e  nop     dword ptr [rax+rax+00h]
0x18001ef43  mov     eax, r14d
0x18001ef46  mov     rbx, [rsp+98h+arg_0]
0x18001ef4e  add     rsp, 60h
0x18001ef52  pop     r15
0x18001ef54  pop     r14
0x18001ef56  pop     r13
0x18001ef58  pop     r12
0x18001ef5a  pop     rdi
0x18001ef5b  pop     rsi
0x18001ef5c  pop     rbp
0x18001ef5d  retn
0x18001ef5f  mov     rcx, rax; hdc
0x18001ef62  xor     ebp, ebp
0x18001ef64  call    cs:__imp_SaveDC
0x18001ef6b  nop     dword ptr [rax+rax+00h]
0x18001ef70  test    eax, eax
0x18001ef72  jmp     loc_18001EE75
0x18001ef77  mov     edx, 80000h
0x18001ef7c  mov     rcx, r15
0x18001ef7f  call    GetDCObject
0x18001ef84  xor     r8d, r8d; bForceBkgd
0x18001ef87  mov     rdx, rax; hPal
0x18001ef8a  mov     rcx, rbx; hdc
0x18001ef8d  call    SelectPalette
0x18001ef92  mov     rsi, rax
0x18001ef95  jmp     loc_18001EEA7
0x18001ef9a  call    cs:__imp_DeleteDC
0x18001efa1  nop     dword ptr [rax+rax+00h]
0x18001efa6  jmp     short loc_18001EF43
0x18001efa8  mov     ecx, 57h ; 'W'
0x18001efad  call    cs:__imp_GdiSetLastError
0x18001efb4  nop     dword ptr [rax+rax+00h]
0x18001efb9  xor     eax, eax
0x18001efbb  jmp     short loc_18001EF46
0x18001efbd  movzx   r9d, word ptr [rdi+4]
0x18001efc2  movzx   ecx, word ptr [rdi+6]
0x18001efc6  jmp     loc_18001EEBF
0x18001efcb  neg     ecx
0x18001efcd  jmp     loc_18001EEBF
```
