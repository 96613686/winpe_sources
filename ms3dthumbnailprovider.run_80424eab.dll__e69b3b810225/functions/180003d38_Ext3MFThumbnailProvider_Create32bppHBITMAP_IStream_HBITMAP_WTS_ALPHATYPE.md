# Ext3MFThumbnailProvider::Create32bppHBITMAP(IStream *,HBITMAP__ * *,WTS_ALPHATYPE *)

- ea: `0x180003d38`
- end: `0x180003e5c`
- name: `?Create32bppHBITMAP@Ext3MFThumbnailProvider@@AEAAJPEAUIStream@@PEAPEAUHBITMAP__@@PEAW4WTS_ALPHATYPE@@@Z`
- size: `292`
- prototype: `__int64 __fastcall(Ext3MFThumbnailProvider *this, struct IStream *, HBITMAP *, enum WTS_ALPHATYPE *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003f40`
- `0x180004020`

## callees

- `0x180003b0c`
- `0x180003d38`
- `0x18000b010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180003d86`
- `ole32!CoCreateInstance` at `0x180003d86`

## pseudocode

```c
__int64 __fastcall Ext3MFThumbnailProvider::Create32bppHBITMAP(
        Ext3MFThumbnailProvider *this,
        struct IStream *a2,
        HBITMAP *a3,
        enum WTS_ALPHATYPE *a4)
{
  HRESULT Instance; // ebx
  Ext3MFThumbnailProvider *v8; // rcx
  __int64 v10; // [rsp+30h] [rbp-10h] BYREF
  struct IWICImagingFactory *v11; // [rsp+60h] [rbp+20h] BYREF
  struct IWICBitmapSource *v12; // [rsp+70h] [rbp+30h] BYREF

  *a3 = 0;
  v11 = 0;
  Instance = CoCreateInstance(
               &CLSID_WICImagingFactory2,
               0,
               1u,
               &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
               (LPVOID *)&v11);
  if ( Instance >= 0 )
  {
    v10 = 0;
    Instance = ((__int64 (__fastcall *)(struct IWICImagingFactory *, struct IStream *, GUID *, _QWORD, __int64 *))v11->lpVtbl->CreateDecoderFromStream)(
                 v11,
                 a2,
                 &GUID_VendorMicrosoft,
                 0,
                 &v10);
    if ( Instance >= 0 )
    {
      v12 = 0;
      Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IWICBitmapSource **))(*(_QWORD *)v10 + 104LL))(
                   v10,
                   0,
                   &v12);
      if ( Instance >= 0 )
      {
        Instance = Ext3MFThumbnailProvider::ConvertBitmapSourceTo32bppHBITMAP(v8, v12, v11, a3);
        if ( Instance >= 0 )
          *a4 = WTSAT_ARGB;
        ((void (__fastcall *)(struct IWICBitmapSource *))v12->lpVtbl->Release)(v12);
      }
    }
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  if ( v11 )
    ((void (__fastcall *)(struct IWICImagingFactory *))v11->lpVtbl->Release)(v11);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180003d38  mov     r11, rsp
0x180003d3b  mov     [r11+10h], rbx
0x180003d3f  mov     [r11+20h], rsi
0x180003d43  mov     [r11+8], rcx
0x180003d47  push    rbp
0x180003d48  push    rdi
0x180003d49  push    r14
0x180003d4b  mov     rbp, rsp
0x180003d4e  sub     rsp, 40h
0x180003d52  mov     rdi, r9
0x180003d55  mov     rsi, r8
0x180003d58  mov     r14, rdx
0x180003d5b  mov     qword ptr [r8], 0
0x180003d62  mov     [rbp+arg_0], 0
0x180003d6a  lea     rax, [rbp+arg_0]
0x180003d6e  mov     [r11-38h], rax
0x180003d72  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180003d79  xor     edx, edx; pUnkOuter
0x180003d7b  lea     r8d, [rdx+1]; dwClsContext
0x180003d7f  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180003d86  call    cs:__imp_CoCreateInstance
0x180003d8c  mov     ebx, eax
0x180003d8e  test    eax, eax
0x180003d90  js      loc_180003E31
0x180003d96  mov     [rbp+var_10], 0
0x180003d9e  mov     rcx, [rbp+arg_0]
0x180003da2  mov     rax, [rcx]
0x180003da5  lea     rdx, [rbp+var_10]
0x180003da9  mov     [rsp+40h+var_20], rdx
0x180003dae  xor     r9d, r9d
0x180003db1  lea     r8, GUID_VendorMicrosoft
0x180003db8  mov     rdx, r14
0x180003dbb  mov     rax, [rax+20h]
0x180003dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dc4  mov     ebx, eax
0x180003dc6  test    eax, eax
0x180003dc8  js      short loc_180003E1B
0x180003dca  mov     [rbp+arg_10], 0
0x180003dd2  mov     rcx, [rbp+var_10]
0x180003dd6  mov     rax, [rcx]
0x180003dd9  lea     r8, [rbp+arg_10]
0x180003ddd  xor     edx, edx
0x180003ddf  mov     rax, [rax+68h]
0x180003de3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003de8  mov     ebx, eax
0x180003dea  test    eax, eax
0x180003dec  js      short loc_180003E1B
0x180003dee  mov     r9, rsi; HBITMAP *
0x180003df1  mov     r8, [rbp+arg_0]; struct IWICImagingFactory *
0x180003df5  mov     rdx, [rbp+arg_10]; struct IWICBitmapSource *
0x180003df9  call    ?ConvertBitmapSourceTo32bppHBITMAP@Ext3MFThumbnailProvider@@AEAAJPEAUIWICBitmapSource@@PEAUIWICImagingFactory@@PEAPEAUHBITMAP__@@@Z; Ext3MFThumbnailProvider::ConvertBitmapSourceTo32bppHBITMAP(IWICBitmapSource *,IWICImagingFactory *,HBITMAP__ * *)
0x180003dfe  mov     ebx, eax
0x180003e00  test    eax, eax
0x180003e02  js      short loc_180003E0A
0x180003e04  mov     dword ptr [rdi], 2
0x180003e0a  mov     rcx, [rbp+arg_10]
0x180003e0e  mov     rax, [rcx]
0x180003e11  mov     rax, [rax+10h]
0x180003e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e1a  nop
0x180003e1b  mov     rcx, [rbp+var_10]
0x180003e1f  test    rcx, rcx
0x180003e22  jz      short loc_180003E31
0x180003e24  mov     rax, [rcx]
0x180003e27  mov     rax, [rax+10h]
0x180003e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e30  nop
0x180003e31  mov     rcx, [rbp+arg_0]
0x180003e35  test    rcx, rcx
0x180003e38  jz      short loc_180003E47
0x180003e3a  mov     rax, [rcx]
0x180003e3d  mov     rax, [rax+10h]
0x180003e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e46  nop
0x180003e47  mov     eax, ebx
0x180003e49  mov     rbx, [rsp+40h+arg_8]
0x180003e4e  mov     rsi, [rsp+40h+arg_18]
0x180003e53  add     rsp, 40h
0x180003e57  pop     r14
0x180003e59  pop     rdi
0x180003e5a  pop     rbp
0x180003e5b  retn
```
