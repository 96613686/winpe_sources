# Ext3MFThumbnailProvider::DoPreview(void)

- ea: `0x180003f40`
- end: `0x180003fff`
- name: `?DoPreview@Ext3MFThumbnailProvider@@UEAAJXZ`
- size: `191`
- prototype: `__int64 __fastcall(Ext3MFThumbnailProvider *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180003d38`
- `0x180003e64`
- `0x180003f40`
- `0x180009c98`
- `0x18000b010`

## import_xrefs

- `GDI32!DeleteObject` at `0x180003fd0`
- `GDI32!DeleteObject` at `0x180003fd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Ext3MFThumbnailProvider::DoPreview(Ext3MFThumbnailProvider *this)
{
  Ext3MFThumbnailProvider *v1; // rsi
  __int64 *v2; // rdi
  HBITMAP v3; // rbx
  Ext3MFThumbnailProvider *v4; // rcx
  __int64 v5; // rcx
  unsigned int PreviewWindow; // edi
  WTS_ALPHATYPE v8; // [rsp+40h] [rbp+8h] BYREF
  struct IStream *v9; // [rsp+48h] [rbp+10h] BYREF
  HBITMAP v10; // [rsp+50h] [rbp+18h] BYREF

  v1 = (Ext3MFThumbnailProvider *)((char *)this - 16);
  if ( *((_QWORD *)this + 9) )
    return 2147500037LL;
  v2 = (__int64 *)((char *)this + 40);
  if ( !*((_QWORD *)this + 5) )
    return 2147500037LL;
  v3 = 0;
  v10 = 0;
  v9 = 0;
  if ( (int)Print3MFUtils::ExtractModel((_QWORD *)this + 5, (__int64)&v9) >= 0 && v9 )
  {
    Ext3MFThumbnailProvider::Create32bppHBITMAP(v4, v9, &v10, &v8);
    v3 = v10;
  }
  v5 = *v2;
  if ( *v2 )
  {
    *v2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  PreviewWindow = Ext3MFThumbnailProvider::CreatePreviewWindow(v1, (LPARAM)v3);
  if ( v3 )
    DeleteObject(v3);
  if ( v9 )
    ((void (__fastcall *)(struct IStream *))v9->lpVtbl->Release)(v9);
  return PreviewWindow;
}

```

## disassembly

```asm
0x180003f40  push    rbx
0x180003f42  push    rsi
0x180003f43  push    rdi
0x180003f44  sub     rsp, 20h
0x180003f48  lea     rsi, [rcx-10h]
0x180003f4c  cmp     qword ptr [rsi+58h], 0
0x180003f51  jnz     loc_180003FF2
0x180003f57  lea     rdi, [rcx+28h]
0x180003f5b  cmp     qword ptr [rdi], 0
0x180003f5f  jz      loc_180003FF2
0x180003f65  xor     ebx, ebx
0x180003f67  mov     [rsp+38h+arg_10], rbx
0x180003f6c  mov     [rsp+38h+arg_8], rbx
0x180003f71  lea     rdx, [rsp+38h+arg_8]
0x180003f76  mov     rcx, rdi
0x180003f79  call    ?ExtractModel@Print3MFUtils@@YAJAEAV?$CComPtr@UIStream@@@ATL@@0@Z; Print3MFUtils::ExtractModel(ATL::CComPtr<IStream> &,ATL::CComPtr<IStream> &)
0x180003f7e  test    eax, eax
0x180003f80  js      short loc_180003FA0
0x180003f82  mov     rdx, [rsp+38h+arg_8]; struct IStream *
0x180003f87  test    rdx, rdx
0x180003f8a  jz      short loc_180003FA0
0x180003f8c  lea     r9, [rsp+38h+arg_0]; enum WTS_ALPHATYPE *
0x180003f91  lea     r8, [rsp+38h+arg_10]; HBITMAP *
0x180003f96  call    ?Create32bppHBITMAP@Ext3MFThumbnailProvider@@AEAAJPEAUIStream@@PEAPEAUHBITMAP__@@PEAW4WTS_ALPHATYPE@@@Z; Ext3MFThumbnailProvider::Create32bppHBITMAP(IStream *,HBITMAP__ * *,WTS_ALPHATYPE *)
0x180003f9b  mov     rbx, [rsp+38h+arg_10]
0x180003fa0  mov     rcx, [rdi]
0x180003fa3  test    rcx, rcx
0x180003fa6  jz      short loc_180003FBB
0x180003fa8  mov     qword ptr [rdi], 0
0x180003faf  mov     rax, [rcx]
0x180003fb2  mov     rax, [rax+10h]
0x180003fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fbb  mov     rdx, rbx; HBITMAP
0x180003fbe  mov     rcx, rsi; this
0x180003fc1  call    ?CreatePreviewWindow@Ext3MFThumbnailProvider@@AEAAJPEAUHBITMAP__@@@Z; Ext3MFThumbnailProvider::CreatePreviewWindow(HBITMAP__ *)
0x180003fc6  mov     edi, eax
0x180003fc8  test    rbx, rbx
0x180003fcb  jz      short loc_180003FD7
0x180003fcd  mov     rcx, rbx; ho
0x180003fd0  call    cs:__imp_DeleteObject
0x180003fd6  nop
0x180003fd7  mov     rcx, [rsp+38h+arg_8]
0x180003fdc  test    rcx, rcx
0x180003fdf  jz      short loc_180003FEE
0x180003fe1  mov     rax, [rcx]
0x180003fe4  mov     rax, [rax+10h]
0x180003fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fed  nop
0x180003fee  mov     eax, edi
0x180003ff0  jmp     short loc_180003FF7
0x180003ff2  mov     eax, 80004005h
0x180003ff7  add     rsp, 20h
0x180003ffb  pop     rdi
0x180003ffc  pop     rsi
0x180003ffd  pop     rbx
0x180003ffe  retn
```
