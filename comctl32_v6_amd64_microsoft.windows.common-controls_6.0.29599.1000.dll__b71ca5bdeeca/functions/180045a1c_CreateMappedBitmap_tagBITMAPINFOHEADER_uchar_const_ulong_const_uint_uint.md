# _CreateMappedBitmap(tagBITMAPINFOHEADER *,uchar const *,ulong const *,uint,uint)

- ea: `0x180045a1c`
- end: `0x180045c35`
- name: `?_CreateMappedBitmap@@YAPEAUHBITMAP__@@PEAUtagBITMAPINFOHEADER@@PEBEPEBKII@Z`
- size: `537`
- prototype: `HBITMAP __usercall@<rax>(BITMAPINFO *lpbmi@<rcx>, const unsigned __int8 *@<rdx>, const unsigned int *@<r8>, unsigned int@<r9d>, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180045fa0`

## callees

- `0x180045a1c`
- `0x180114520`
- `0x1801d0c54`

## import_xrefs

- `GDI32!DeleteObject` at `0x180045bfd`
- `GDI32!DeleteObject` at `0x180045bfd`
- `GDI32!SelectObject` at `0x180045b03`
- `GDI32!SelectObject` at `0x180045bf4`
- `GDI32!SelectObject` at `0x180045b03`
- `GDI32!SelectObject` at `0x180045bf4`
- `GDI32!CreateCompatibleDC` at `0x180045a70`
- `GDI32!CreateCompatibleDC` at `0x180045a70`
- `GDI32!CreateCompatibleBitmap` at `0x180045aeb`
- `GDI32!CreateCompatibleBitmap` at `0x180045aeb`
- `GDI32!BitBlt` at `0x180045be8`
- `GDI32!BitBlt` at `0x180045be8`
- `GDI32!CreateDIBSection` at `0x180045ac6`
- `GDI32!CreateDIBSection` at `0x180045ac6`
- `GDI32!StretchDIBits` at `0x180045b4a`
- `GDI32!StretchDIBits` at `0x180045bbc`
- `GDI32!StretchDIBits` at `0x180045b4a`
- `GDI32!StretchDIBits` at `0x180045bbc`
- `USER32!GetDC` at `0x180045a5b`
- `USER32!GetDC` at `0x180045a5b`
- `USER32!ReleaseDC` at `0x180045c08`
- `USER32!ReleaseDC` at `0x180045c08`

## pseudocode

```c
HBITMAP __fastcall _CreateMappedBitmap(
        BITMAPINFO *lpbmi,
        const unsigned __int8 *a2,
        const unsigned int *a3,
        unsigned int a4,
        char a5)
{
  HBITMAP CompatibleBitmap; // rbp
  HDC DC; // rax
  HDC v8; // r15
  HDC CompatibleDC; // rdi
  LONG SrcWidth; // esi
  LONG SrcHeight; // r12d
  DWORD biCompression; // r13d
  int v13; // edx
  HGDIOBJ v14; // r13
  void *ppvBits; // [rsp+88h] [rbp-60h] BYREF

  CompatibleBitmap = 0;
  DC = GetDC(0);
  v8 = DC;
  if ( DC )
  {
    CompatibleDC = CreateCompatibleDC(DC);
    if ( CompatibleDC )
    {
      SrcWidth = lpbmi->bmiHeader.biWidth;
      SrcHeight = lpbmi->bmiHeader.biHeight;
      if ( (a5 & 4) != 0 )
      {
        biCompression = lpbmi->bmiHeader.biCompression;
        ppvBits = 0;
        if ( biCompression != 3 )
          lpbmi->bmiHeader.biCompression = 0;
        CompatibleBitmap = CreateDIBSection(v8, lpbmi, 0, &ppvBits, 0, 0);
        lpbmi->bmiHeader.biCompression = biCompression;
      }
      if ( CompatibleBitmap )
        goto LABEL_11;
      v13 = 2 * SrcWidth;
      if ( (a5 & 2) == 0 )
        v13 = SrcWidth;
      CompatibleBitmap = CreateCompatibleBitmap(v8, v13, SrcHeight);
      if ( CompatibleBitmap )
      {
LABEL_11:
        v14 = SelectObject(CompatibleDC, CompatibleBitmap);
        StretchDIBits(CompatibleDC, 0, 0, SrcWidth, SrcHeight, 0, 0, SrcWidth, SrcHeight, a2, lpbmi, 0, 0xCC0020u);
        if ( (a5 & 2) != 0 )
        {
          if ( a4 )
            memmove_0((char *)lpbmi + lpbmi->bmiHeader.biSize, a3, 4LL * a4);
          StretchDIBits(
            CompatibleDC,
            SrcWidth,
            0,
            SrcWidth,
            SrcHeight,
            0,
            0,
            SrcWidth,
            SrcHeight,
            a2,
            lpbmi,
            0,
            0xCC0020u);
          BitBlt(CompatibleDC, 0, 0, SrcWidth, SrcHeight, CompatibleDC, SrcWidth, 0, 0x220326u);
        }
        SelectObject(CompatibleDC, v14);
      }
      DeleteObject(CompatibleDC);
    }
    ReleaseDC(0, v8);
  }
  return CompatibleBitmap;
}

```

## disassembly

```asm
0x180045a1c  push    rbx
0x180045a1e  push    rbp
0x180045a1f  push    rsi
0x180045a20  push    rdi
0x180045a21  push    r12
0x180045a23  push    r13
0x180045a25  push    r14
0x180045a27  push    r15
0x180045a29  sub     rsp, 0A8h
0x180045a30  mov     rax, cs:__security_cookie
0x180045a37  xor     rax, rsp
0x180045a3a  mov     [rsp+0E8h+var_58], rax
0x180045a42  mov     rbx, rcx
0x180045a45  mov     [rsp+0E8h+var_78], r9d
0x180045a4a  xor     ecx, ecx; hWnd
0x180045a4c  mov     [rsp+0E8h+Src], r8
0x180045a54  mov     [rsp+0E8h+var_70], rdx
0x180045a59  xor     ebp, ebp
0x180045a5b  call    cs:__imp_GetDC
0x180045a61  mov     r15, rax
0x180045a64  test    rax, rax
0x180045a67  jz      loc_180045C0E
0x180045a6d  mov     rcx, rax; hdc
0x180045a70  call    cs:__imp_CreateCompatibleDC
0x180045a76  mov     rdi, rax
0x180045a79  test    rax, rax
0x180045a7c  jz      loc_180045C03
0x180045a82  mov     r14d, [rsp+0E8h+arg_20]
0x180045a8a  mov     esi, [rbx+4]
0x180045a8d  mov     r12d, [rbx+8]
0x180045a91  test    r14b, 4
0x180045a95  jz      short loc_180045AD3
0x180045a97  mov     r13d, [rbx+10h]
0x180045a9b  mov     [rsp+0E8h+ppvBits], rbp
0x180045aa3  cmp     r13d, 3
0x180045aa7  jz      short loc_180045AAC
0x180045aa9  mov     [rbx+10h], ebp
0x180045aac  mov     [rsp+0E8h+offset], ebp; offset
0x180045ab0  lea     r9, [rsp+0E8h+ppvBits]; ppvBits
0x180045ab8  xor     r8d, r8d; usage
0x180045abb  mov     [rsp+0E8h+hSection], rbp; hSection
0x180045ac0  mov     rdx, rbx; pbmi
0x180045ac3  mov     rcx, r15; hdc
0x180045ac6  call    cs:__imp_CreateDIBSection
0x180045acc  mov     rbp, rax
0x180045acf  mov     [rbx+10h], r13d
0x180045ad3  and     r14d, 2
0x180045ad7  test    rbp, rbp
0x180045ada  jnz     short loc_180045AFD
0x180045adc  lea     edx, [rsi+rsi]
0x180045adf  test    r14d, r14d
0x180045ae2  mov     r8d, r12d; cy
0x180045ae5  mov     rcx, r15; hdc
0x180045ae8  cmovz   edx, esi; cx
0x180045aeb  call    cs:__imp_CreateCompatibleBitmap
0x180045af1  mov     rbp, rax
0x180045af4  test    rax, rax
0x180045af7  jz      loc_180045BFA
0x180045afd  mov     rdx, rbp; h
0x180045b00  mov     rcx, rdi; hdc
0x180045b03  call    cs:__imp_SelectObject
0x180045b09  mov     [rsp+0E8h+rop], 0CC0020h; rop
0x180045b11  xor     ecx, ecx
0x180045b13  mov     [rsp+0E8h+iUsage], ecx; iUsage
0x180045b17  mov     r13, rax
0x180045b1a  mov     rax, [rsp+0E8h+var_70]
0x180045b1f  mov     r9d, esi; DestWidth
0x180045b22  mov     [rsp+0E8h+lpbmi], rbx; lpbmi
0x180045b27  xor     r8d, r8d; yDest
0x180045b2a  mov     [rsp+0E8h+lpBits], rax; lpBits
0x180045b2f  xor     edx, edx; xDest
0x180045b31  mov     [rsp+0E8h+SrcHeight], r12d; SrcHeight
0x180045b36  mov     [rsp+0E8h+SrcWidth], esi; SrcWidth
0x180045b3a  mov     [rsp+0E8h+ySrc], ecx; ySrc
0x180045b3e  mov     [rsp+0E8h+offset], ecx; xSrc
0x180045b42  mov     rcx, rdi; hdc
0x180045b45  mov     dword ptr [rsp+0E8h+hSection], r12d; DestHeight
0x180045b4a  call    cs:__imp_StretchDIBits
0x180045b50  test    r14d, r14d
0x180045b53  jz      loc_180045BEE
0x180045b59  mov     eax, [rsp+0E8h+var_78]
0x180045b5d  xor     r14d, r14d
0x180045b60  test    eax, eax
0x180045b62  jz      short loc_180045B7D
0x180045b64  mov     ecx, [rbx]
0x180045b66  mov     r8d, eax
0x180045b69  mov     rdx, [rsp+0E8h+Src]; Src
0x180045b71  add     rcx, rbx; void *
0x180045b74  shl     r8, 2; Size
0x180045b78  call    memmove_0
0x180045b7d  mov     rax, [rsp+0E8h+var_70]
0x180045b82  mov     r9d, esi; DestWidth
0x180045b85  mov     [rsp+0E8h+rop], 0CC0020h; rop
0x180045b8d  xor     r8d, r8d; yDest
0x180045b90  mov     [rsp+0E8h+iUsage], r14d; iUsage
0x180045b95  mov     edx, esi; xDest
0x180045b97  mov     [rsp+0E8h+lpbmi], rbx; lpbmi
0x180045b9c  mov     rcx, rdi; hdc
0x180045b9f  mov     [rsp+0E8h+lpBits], rax; lpBits
0x180045ba4  mov     [rsp+0E8h+SrcHeight], r12d; SrcHeight
0x180045ba9  mov     [rsp+0E8h+SrcWidth], esi; SrcWidth
0x180045bad  mov     [rsp+0E8h+ySrc], r14d; ySrc
0x180045bb2  mov     [rsp+0E8h+offset], r14d; xSrc
0x180045bb7  mov     dword ptr [rsp+0E8h+hSection], r12d; DestHeight
0x180045bbc  call    cs:__imp_StretchDIBits
0x180045bc2  mov     [rsp+0E8h+SrcHeight], 220326h; rop
0x180045bca  mov     r9d, esi; cx
0x180045bcd  mov     [rsp+0E8h+SrcWidth], r14d; y1
0x180045bd2  xor     r8d, r8d; y
0x180045bd5  mov     [rsp+0E8h+ySrc], esi; x1
0x180045bd9  xor     edx, edx; x
0x180045bdb  mov     qword ptr [rsp+0E8h+offset], rdi; hdcSrc
0x180045be0  mov     rcx, rdi; hdc
0x180045be3  mov     dword ptr [rsp+0E8h+hSection], r12d; cy
0x180045be8  call    cs:__imp_BitBlt
0x180045bee  mov     rdx, r13; h
0x180045bf1  mov     rcx, rdi; hdc
0x180045bf4  call    cs:__imp_SelectObject
0x180045bfa  mov     rcx, rdi; ho
0x180045bfd  call    cs:__imp_DeleteObject
0x180045c03  mov     rdx, r15; hDC
0x180045c06  xor     ecx, ecx; hWnd
0x180045c08  call    cs:__imp_ReleaseDC
0x180045c0e  mov     rax, rbp
0x180045c11  mov     rcx, [rsp+0E8h+var_58]
0x180045c19  xor     rcx, rsp; StackCookie
0x180045c1c  call    __security_check_cookie
0x180045c21  add     rsp, 0A8h
0x180045c28  pop     r15
0x180045c2a  pop     r14
0x180045c2c  pop     r13
0x180045c2e  pop     r12
0x180045c30  pop     rdi
0x180045c31  pop     rsi
0x180045c32  pop     rbp
0x180045c33  pop     rbx
0x180045c34  retn
```
