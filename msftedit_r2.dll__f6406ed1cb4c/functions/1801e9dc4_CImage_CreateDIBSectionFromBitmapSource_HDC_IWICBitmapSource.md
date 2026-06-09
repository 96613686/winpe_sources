# CImage::CreateDIBSectionFromBitmapSource(HDC__ *,IWICBitmapSource *)

- ea: `0x1801e9dc4`
- end: `0x1801e9fbe`
- name: `?CreateDIBSectionFromBitmapSource@CImage@@AEAAJPEAUHDC__@@PEAUIWICBitmapSource@@@Z`
- size: `506`
- prototype: `__int64 __fastcall(CImage *this, HDC, struct IWICBitmapSource *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1801e9924`

## callees

- `0x18013ce80`
- `0x18013dcc2`
- `0x1801e9dc4`
- `0x18027f010`

## import_xrefs

- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x1801e9f9a`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x1801e9f9a`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801e9edc`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801e9edc`

## pseudocode

```c
__int64 __fastcall CImage::CreateDIBSectionFromBitmapSource(CImage *this, HDC a2, struct IWICBitmapSource *a3)
{
  struct IWICBitmapSourceVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetPixelFormat)(IWICBitmapSource *, WICPixelFormatGUID *); // rax
  signed int v8; // ebx
  unsigned __int64 v9; // rax
  __int64 v10; // r8
  unsigned __int64 v11; // rcx
  __int64 v12; // r9
  void *v13; // rcx
  HBITMAP v15; // rax
  unsigned int v16; // [rsp+30h] [rbp-29h] BYREF
  unsigned int v17; // [rsp+34h] [rbp-25h] BYREF
  void *ppvBits; // [rsp+38h] [rbp-21h] BYREF
  __int128 Buf1; // [rsp+40h] [rbp-19h] BYREF
  BITMAPINFO pbmi; // [rsp+50h] [rbp-9h] BYREF

  lpVtbl = a3->lpVtbl;
  v16 = 0;
  v17 = 0;
  ppvBits = 0;
  GetPixelFormat = lpVtbl->GetPixelFormat;
  Buf1 = 0;
  v8 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, __int128 *))GetPixelFormat)(a3, &Buf1);
  if ( v8 < 0 )
    goto LABEL_14;
  if ( *((_BYTE *)this + 211) )
  {
    if ( memcmp_0(&Buf1, &GUID_WICPixelFormat32bppPBGRA, 0x10u) )
      v8 = -2147467259;
    if ( v8 < 0 )
      goto LABEL_14;
  }
  else if ( memcmp_0(&Buf1, &GUID_WICPixelFormat32bppBGR, 0x10u) )
  {
LABEL_20:
    v8 = -2147467259;
    goto LABEL_14;
  }
  v8 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, unsigned int *, unsigned int *))a3->lpVtbl->GetSize)(
         a3,
         &v16,
         &v17);
  if ( v8 < 0 )
  {
LABEL_14:
    v13 = (void *)*((_QWORD *)this + 16);
    if ( v13 )
    {
      DeleteObject(v13);
      *((_QWORD *)this + 16) = 0;
    }
    return (unsigned int)v8;
  }
  pbmi.bmiHeader.biWidth = v16;
  pbmi.bmiHeader.biHeight = -v17;
  memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
  pbmi.bmiHeader.biSize = 40;
  *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
  v15 = CreateDIBSection(a2, &pbmi, 0, &ppvBits, 0, 0);
  *((_QWORD *)this + 16) = v15;
  if ( !v15 )
    goto LABEL_20;
  v9 = 4LL * v16;
  v10 = 4 * v16;
  if ( v9 > 0xFFFFFFFF )
    v10 = 0xFFFFFFFFLL;
  v8 = v9 > 0xFFFFFFFF ? 0x80070216 : 0;
  if ( v9 > 0xFFFFFFFF )
    goto LABEL_14;
  v11 = v17 * (unsigned __int64)(unsigned int)v10;
  v12 = v17 * (unsigned int)v10;
  if ( v11 > 0xFFFFFFFF )
    v12 = 0xFFFFFFFFLL;
  v8 = v11 > 0xFFFFFFFF ? 0x80070216 : 0;
  if ( v11 > 0xFFFFFFFF )
    goto LABEL_14;
  v8 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, _QWORD, __int64, __int64, void *))a3->lpVtbl->CopyPixels)(
         a3,
         0,
         v10,
         v12,
         ppvBits);
  if ( v8 < 0 )
    goto LABEL_14;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1801e9dc4  mov     [rsp-8+arg_18], rbx
0x1801e9dc9  push    rbp
0x1801e9dca  push    rsi
0x1801e9dcb  push    rdi
0x1801e9dcc  push    r12
0x1801e9dce  push    r14
0x1801e9dd0  lea     rbp, [rsp-37h]
0x1801e9dd5  sub     rsp, 90h
0x1801e9ddc  mov     rax, cs:__security_cookie
0x1801e9de3  xor     rax, rsp
0x1801e9de6  mov     [rbp+57h+var_30], rax
0x1801e9dea  mov     rax, [r8]
0x1801e9ded  mov     r14, rdx
0x1801e9df0  mov     rdi, rcx
0x1801e9df3  mov     [rbp+57h+var_80], 0
0x1801e9dfa  xorps   xmm0, xmm0
0x1801e9dfd  mov     [rbp+57h+var_7C], 0
0x1801e9e04  lea     rdx, [rbp+57h+Buf1]
0x1801e9e08  mov     [rbp+57h+ppvBits], 0
0x1801e9e10  mov     rax, [rax+20h]
0x1801e9e14  mov     rcx, r8
0x1801e9e17  mov     rsi, r8
0x1801e9e1a  movups  [rbp+57h+Buf1], xmm0
0x1801e9e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9e23  mov     ebx, eax
0x1801e9e25  test    eax, eax
0x1801e9e27  js      short loc_1801E9E60
0x1801e9e29  cmp     byte ptr [rdi+0D3h], 0
0x1801e9e30  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1801e9e34  mov     r12d, 80004005h
0x1801e9e3a  mov     r8d, 10h; Size
0x1801e9e40  jz      loc_1801E9F19
0x1801e9e46  lea     rdx, GUID_WICPixelFormat32bppPBGRA; Buf2
0x1801e9e4d  call    memcmp_0
0x1801e9e52  test    eax, eax
0x1801e9e54  cmovnz  ebx, r12d
0x1801e9e58  test    ebx, ebx
0x1801e9e5a  jns     loc_1801E9F2D
0x1801e9e60  test    ebx, ebx
0x1801e9e62  js      short loc_1801E9ED0
0x1801e9e64  mov     eax, [rbp+57h+var_80]
0x1801e9e67  mov     edx, 0FFFFFFFFh
0x1801e9e6c  shl     rax, 2
0x1801e9e70  mov     r8d, eax
0x1801e9e73  cmp     rax, rdx
0x1801e9e76  jbe     short loc_1801E9E7B
0x1801e9e78  mov     r8d, edx
0x1801e9e7b  cmp     rdx, rax
0x1801e9e7e  mov     r10d, 80070216h
0x1801e9e84  sbb     ebx, ebx
0x1801e9e86  and     ebx, r10d
0x1801e9e89  cmp     rax, rdx
0x1801e9e8c  ja      short loc_1801E9ED0
0x1801e9e8e  mov     eax, [rbp+57h+var_7C]
0x1801e9e91  mov     ecx, r8d
0x1801e9e94  imul    rcx, rax
0x1801e9e98  mov     r9d, ecx
0x1801e9e9b  cmp     rcx, rdx
0x1801e9e9e  jbe     short loc_1801E9EA3
0x1801e9ea0  mov     r9d, edx
0x1801e9ea3  cmp     rdx, rcx
0x1801e9ea6  sbb     ebx, ebx
0x1801e9ea8  and     ebx, r10d
0x1801e9eab  cmp     rcx, rdx
0x1801e9eae  ja      short loc_1801E9ED0
0x1801e9eb0  mov     rdx, [rbp+57h+ppvBits]
0x1801e9eb4  mov     rcx, rsi
0x1801e9eb7  mov     rax, [rsi]
0x1801e9eba  mov     [rsp+0B0h+hSection], rdx
0x1801e9ebf  xor     edx, edx
0x1801e9ec1  mov     rax, [rax+38h]
0x1801e9ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9eca  mov     ebx, eax
0x1801e9ecc  test    eax, eax
0x1801e9ece  jns     short loc_1801E9EF3
0x1801e9ed0  mov     rcx, [rdi+80h]; ho
0x1801e9ed7  test    rcx, rcx
0x1801e9eda  jz      short loc_1801E9EF3
0x1801e9edc  call    cs:__imp_DeleteObject
0x1801e9ee3  nop     dword ptr [rax+rax+00h]
0x1801e9ee8  mov     qword ptr [rdi+80h], 0
0x1801e9ef3  mov     eax, ebx
0x1801e9ef5  mov     rcx, [rbp+57h+var_30]
0x1801e9ef9  xor     rcx, rsp; StackCookie
0x1801e9efc  call    __security_check_cookie
0x1801e9f01  mov     rbx, [rsp+0B0h+arg_18]
0x1801e9f09  add     rsp, 90h
0x1801e9f10  pop     r14
0x1801e9f12  pop     r12
0x1801e9f14  pop     rdi
0x1801e9f15  pop     rsi
0x1801e9f16  pop     rbp
0x1801e9f17  retn
0x1801e9f19  lea     rdx, GUID_WICPixelFormat32bppBGR; Buf2
0x1801e9f20  call    memcmp_0
0x1801e9f25  test    eax, eax
0x1801e9f27  jnz     loc_1801E9FB6
0x1801e9f2d  mov     rax, [rsi]
0x1801e9f30  lea     r8, [rbp+57h+var_7C]
0x1801e9f34  lea     rdx, [rbp+57h+var_80]
0x1801e9f38  mov     rcx, rsi
0x1801e9f3b  mov     rax, [rax+18h]
0x1801e9f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9f44  mov     ebx, eax
0x1801e9f46  test    eax, eax
0x1801e9f48  js      loc_1801E9E60
0x1801e9f4e  mov     eax, [rbp+57h+var_80]
0x1801e9f51  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x1801e9f55  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x1801e9f58  lea     rdx, [rbp+57h+pbmi]; pbmi
0x1801e9f5c  mov     eax, [rbp+57h+var_7C]
0x1801e9f5f  xorps   xmm0, xmm0
0x1801e9f62  neg     eax
0x1801e9f64  mov     [rsp+0B0h+offset], 0; offset
0x1801e9f6c  xor     r8d, r8d; usage
0x1801e9f6f  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x1801e9f72  mov     rcx, r14; hdc
0x1801e9f75  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], 0
0x1801e9f7d  movdqu  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x1801e9f82  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x1801e9f89  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x1801e9f91  mov     [rsp+0B0h+hSection], 0; hSection
0x1801e9f9a  call    cs:__imp_CreateDIBSection
0x1801e9fa1  nop     dword ptr [rax+rax+00h]
0x1801e9fa6  mov     [rdi+80h], rax
0x1801e9fad  test    rax, rax
0x1801e9fb0  jnz     loc_1801E9E64
0x1801e9fb6  mov     ebx, r12d
0x1801e9fb9  jmp     loc_1801E9ED0
```
