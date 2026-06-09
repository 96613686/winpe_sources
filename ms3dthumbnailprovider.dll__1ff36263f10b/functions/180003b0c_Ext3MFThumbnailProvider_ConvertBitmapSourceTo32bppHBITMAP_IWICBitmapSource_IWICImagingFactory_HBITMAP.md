# Ext3MFThumbnailProvider::ConvertBitmapSourceTo32bppHBITMAP(IWICBitmapSource *,IWICImagingFactory *,HBITMAP__ * *)

- ea: `0x180003b0c`
- end: `0x180003d32`
- name: `?ConvertBitmapSourceTo32bppHBITMAP@Ext3MFThumbnailProvider@@AEAAJPEAUIWICBitmapSource@@PEAUIWICImagingFactory@@PEAPEAUHBITMAP__@@@Z`
- size: `550`
- prototype: `__int64 __fastcall(Ext3MFThumbnailProvider *__hidden this, struct IWICBitmapSource *, struct IWICImagingFactory *, HBITMAP *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003d38`

## callees

- `0x180001ef0`
- `0x180003b0c`
- `0x18000a2c4`
- `0x18000b010`

## import_xrefs

- `GDI32!DeleteObject` at `0x180003cf9`
- `GDI32!DeleteObject` at `0x180003cf9`
- `GDI32!CreateDIBSection` at `0x180003c99`
- `GDI32!CreateDIBSection` at `0x180003c99`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Ext3MFThumbnailProvider::ConvertBitmapSourceTo32bppHBITMAP(
        Ext3MFThumbnailProvider *this,
        struct IWICBitmapSource *a2,
        struct IWICImagingFactory *a3,
        HBITMAP *a4)
{
  int v7; // ebx
  HBITMAP v8; // rdi
  __int64 v10; // [rsp+40h] [rbp-49h] BYREF
  LONG v11; // [rsp+48h] [rbp-41h] BYREF
  __int64 v12; // [rsp+50h] [rbp-39h] BYREF
  void *ppvBits; // [rsp+58h] [rbp-31h] BYREF
  __int64 v14; // [rsp+60h] [rbp-29h] BYREF
  LONG v15; // [rsp+68h] [rbp-21h]
  int v16; // [rsp+6Ch] [rbp-1Dh]
  BITMAPINFO pbmi; // [rsp+70h] [rbp-19h] BYREF
  __int128 Buf1; // [rsp+A0h] [rbp+17h] BYREF

  *a4 = 0;
  v12 = 0;
  Buf1 = 0;
  if ( ((int (__fastcall *)(struct IWICBitmapSource *, __int128 *))a2->lpVtbl->GetPixelFormat)(a2, &Buf1) < 0
    || !memcmp_0(&Buf1, &GUID_WICPixelFormat32bppBGRA, 0x10u) )
  {
    v7 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           &GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94,
           &v12);
  }
  else
  {
    v10 = 0;
    v7 = ((__int64 (__fastcall *)(struct IWICImagingFactory *, __int64 *))a3->lpVtbl->CreateFormatConverter)(a3, &v10);
    if ( v7 < 0 )
      goto LABEL_15;
    v7 = (*(__int64 (__fastcall **)(__int64, struct IWICBitmapSource *, GUID *, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v10 + 64LL))(
           v10,
           a2,
           &GUID_WICPixelFormat32bppBGRA,
           0,
           0,
           0,
           0);
    if ( v7 >= 0 )
      v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v10)(
             v10,
             &GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94,
             &v12);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  if ( v7 >= 0 )
  {
    v11 = 0;
    LODWORD(v10) = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, LONG *, __int64 *))(*(_QWORD *)v12 + 24LL))(v12, &v11, &v10);
    if ( v7 >= 0 )
    {
      pbmi.bmiHeader.biSize = 40;
      memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
      pbmi.bmiHeader.biWidth = v11;
      pbmi.bmiHeader.biHeight = -(int)v10;
      *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
      ppvBits = 0;
      v8 = CreateDIBSection(0, &pbmi, 0, &ppvBits, 0, 0);
      if ( v8 )
      {
        v14 = 0;
        v15 = v11;
        v16 = v10;
        v7 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD, _QWORD, void *))(*(_QWORD *)v12 + 56LL))(
               v12,
               &v14,
               (unsigned int)(4 * v11),
               (unsigned int)(4 * v11 * v10),
               ppvBits);
        if ( v7 < 0 )
          DeleteObject(v8);
        else
          *a4 = v8;
      }
      else
      {
        v7 = -2147024882;
      }
    }
  }
LABEL_15:
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180003b0c  push    rbp
0x180003b0e  push    rbx
0x180003b0f  push    rsi
0x180003b10  push    rdi
0x180003b11  push    r14
0x180003b13  lea     rbp, [rsp-37h]
0x180003b18  sub     rsp, 0C0h
0x180003b1f  mov     rax, cs:__security_cookie
0x180003b26  xor     rax, rsp
0x180003b29  mov     [rbp+57h+var_30], rax
0x180003b2d  mov     rsi, r9
0x180003b30  mov     rbx, r8
0x180003b33  mov     rdi, rdx
0x180003b36  xor     r14d, r14d
0x180003b39  mov     [r9], r14
0x180003b3c  mov     [rbp+57h+var_90], r14
0x180003b40  xorps   xmm0, xmm0
0x180003b43  movups  [rbp+57h+Buf1], xmm0
0x180003b47  mov     rax, [rdx]
0x180003b4a  lea     rdx, [rbp+57h+Buf1]
0x180003b4e  mov     rcx, rdi
0x180003b51  mov     rax, [rax+20h]
0x180003b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b5a  test    eax, eax
0x180003b5c  js      loc_180003C03
0x180003b62  lea     r8d, [r14+10h]; Size
0x180003b66  lea     rdx, GUID_WICPixelFormat32bppBGRA; Buf2
0x180003b6d  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180003b71  call    memcmp_0
0x180003b76  test    eax, eax
0x180003b78  jz      loc_180003C03
0x180003b7e  mov     [rbp+57h+var_A0], r14
0x180003b82  mov     rax, [rbx]
0x180003b85  lea     rdx, [rbp+57h+var_A0]
0x180003b89  mov     rcx, rbx
0x180003b8c  mov     rax, [rax+50h]
0x180003b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b95  mov     ebx, eax
0x180003b97  test    eax, eax
0x180003b99  js      loc_180003D00
0x180003b9f  mov     rcx, [rbp+57h+var_A0]
0x180003ba3  mov     rax, [rcx]
0x180003ba6  mov     [rsp+0E0h+var_B0], r14d
0x180003bab  xorps   xmm0, xmm0
0x180003bae  movsd   qword ptr [rsp+0E0h+offset], xmm0
0x180003bb4  mov     [rsp+0E0h+hSection], r14
0x180003bb9  xor     r9d, r9d
0x180003bbc  lea     r8, GUID_WICPixelFormat32bppBGRA
0x180003bc3  mov     rdx, rdi
0x180003bc6  mov     rax, [rax+40h]
0x180003bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bcf  mov     ebx, eax
0x180003bd1  test    eax, eax
0x180003bd3  js      short loc_180003BF1
0x180003bd5  mov     rcx, [rbp+57h+var_A0]
0x180003bd9  mov     rax, [rcx]
0x180003bdc  lea     r8, [rbp+57h+var_90]
0x180003be0  lea     rdx, _GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94
0x180003be7  mov     rax, [rax]
0x180003bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bef  mov     ebx, eax
0x180003bf1  mov     rcx, [rbp+57h+var_A0]
0x180003bf5  mov     rax, [rcx]
0x180003bf8  mov     rax, [rax+10h]
0x180003bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c01  jmp     short loc_180003C1E
0x180003c03  mov     rax, [rdi]
0x180003c06  lea     r8, [rbp+57h+var_90]
0x180003c0a  lea     rdx, _GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94
0x180003c11  mov     rcx, rdi
0x180003c14  mov     rax, [rax]
0x180003c17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c1c  mov     ebx, eax
0x180003c1e  test    ebx, ebx
0x180003c20  js      loc_180003D00
0x180003c26  mov     [rbp+57h+var_98], r14d
0x180003c2a  mov     dword ptr [rbp+57h+var_A0], r14d
0x180003c2e  mov     rcx, [rbp+57h+var_90]
0x180003c32  mov     rax, [rcx]
0x180003c35  lea     r8, [rbp+57h+var_A0]
0x180003c39  lea     rdx, [rbp+57h+var_98]
0x180003c3d  mov     rax, [rax+18h]
0x180003c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c46  mov     ebx, eax
0x180003c48  test    eax, eax
0x180003c4a  js      loc_180003D00
0x180003c50  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x180003c57  xorps   xmm0, xmm0
0x180003c5a  xor     eax, eax
0x180003c5c  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biWidth], xmm0
0x180003c60  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x180003c64  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], rax
0x180003c68  mov     eax, [rbp+57h+var_98]
0x180003c6b  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x180003c6e  mov     eax, dword ptr [rbp+57h+var_A0]
0x180003c71  neg     eax
0x180003c73  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x180003c76  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x180003c7e  mov     [rbp+57h+ppvBits], r14
0x180003c82  mov     [rsp+0E0h+offset], r14d; offset
0x180003c87  mov     [rsp+0E0h+hSection], r14; hSection
0x180003c8c  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x180003c90  xor     r8d, r8d; usage
0x180003c93  lea     rdx, [rbp+57h+pbmi]; pbmi
0x180003c97  xor     ecx, ecx; hdc
0x180003c99  call    cs:__imp_CreateDIBSection
0x180003c9f  mov     rdi, rax
0x180003ca2  test    rax, rax
0x180003ca5  jnz     short loc_180003CAE
0x180003ca7  mov     ebx, 8007000Eh
0x180003cac  jmp     short loc_180003D00
0x180003cae  mov     [rbp+57h+var_80], r14
0x180003cb2  mov     r8d, [rbp+57h+var_98]
0x180003cb6  mov     [rbp+57h+var_78], r8d
0x180003cba  mov     r9d, dword ptr [rbp+57h+var_A0]
0x180003cbe  mov     [rbp+57h+var_74], r9d
0x180003cc2  mov     rcx, [rbp+57h+var_90]
0x180003cc6  mov     rdx, [rbp+57h+ppvBits]
0x180003cca  mov     rax, [rcx]
0x180003ccd  imul    r9d, r8d
0x180003cd1  shl     r9d, 2
0x180003cd5  shl     r8d, 2
0x180003cd9  mov     [rsp+0E0h+hSection], rdx
0x180003cde  lea     rdx, [rbp+57h+var_80]
0x180003ce2  mov     rax, [rax+38h]
0x180003ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ceb  mov     ebx, eax
0x180003ced  test    eax, eax
0x180003cef  js      short loc_180003CF6
0x180003cf1  mov     [rsi], rdi
0x180003cf4  jmp     short loc_180003D00
0x180003cf6  mov     rcx, rdi; ho
0x180003cf9  call    cs:__imp_DeleteObject
0x180003cff  nop
0x180003d00  mov     rcx, [rbp+57h+var_90]
0x180003d04  test    rcx, rcx
0x180003d07  jz      short loc_180003D16
0x180003d09  mov     rax, [rcx]
0x180003d0c  mov     rax, [rax+10h]
0x180003d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d15  nop
0x180003d16  mov     eax, ebx
0x180003d18  mov     rcx, [rbp+57h+var_30]
0x180003d1c  xor     rcx, rsp; StackCookie
0x180003d1f  call    __security_check_cookie
0x180003d24  add     rsp, 0C0h
0x180003d2b  pop     r14
0x180003d2d  pop     rdi
0x180003d2e  pop     rsi
0x180003d2f  pop     rbx
0x180003d30  pop     rbp
0x180003d31  retn
```
