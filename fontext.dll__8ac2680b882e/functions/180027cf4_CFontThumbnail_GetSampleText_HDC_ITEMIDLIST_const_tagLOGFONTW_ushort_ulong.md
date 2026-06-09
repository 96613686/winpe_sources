# CFontThumbnail::_GetSampleText(HDC__ *,_ITEMIDLIST const *,tagLOGFONTW *,ushort *,ulong)

- ea: `0x180027cf4`
- end: `0x180027e51`
- name: `?_GetSampleText@CFontThumbnail@@AEAAXPEAUHDC__@@PEFBU_ITEMIDLIST@@PEAUtagLOGFONTW@@PEAGK@Z`
- size: `349`
- prototype: `void __fastcall(CFontThumbnail *__hidden this, HDC hdc, const struct _ITEMIDLIST *, LOGFONTW *lplf, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180027140`

## callees

- `0x180006624`
- `0x180027810`
- `0x180027cf4`
- `0x1800283a8`
- `0x180031070`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180027da5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180027dd6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180027da5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180027dd6`
- `GDI32!DeleteObject` at `0x180027e2d`
- `GDI32!DeleteObject` at `0x180027e2d`
- `GDI32!CreateFontIndirectW` at `0x180027d2f`
- `GDI32!CreateFontIndirectW` at `0x180027d2f`
- `GDI32!SelectObject` at `0x180027d47`
- `GDI32!SelectObject` at `0x180027e24`
- `GDI32!SelectObject` at `0x180027d47`
- `GDI32!SelectObject` at `0x180027e24`

## pseudocode

```c
void __fastcall CFontThumbnail::_GetSampleText(
        CFontThumbnail *this,
        HDC hdc,
        const struct _ITEMIDLIST *a3,
        LOGFONTW *lplf,
        unsigned __int16 *a5)
{
  HFONT FontIndirectW; // rax
  HFONT v9; // r15
  HGDIOBJ v10; // r12
  UINT SampleResourceId; // eax
  UINT v12; // edi
  WCHAR *v13; // r8
  WCHAR Buffer[8]; // [rsp+20h] [rbp-88h] BYREF
  __int128 v15; // [rsp+30h] [rbp-78h]
  __int128 v16; // [rsp+40h] [rbp-68h]

  *a5 = 0;
  FontIndirectW = CreateFontIndirectW(lplf);
  v9 = FontIndirectW;
  if ( FontIndirectW )
  {
    v10 = SelectObject(hdc, FontIndirectW);
    SampleResourceId = CFontThumbnail::_GetSampleResourceId(this, hdc, a3);
    v12 = SampleResourceId;
    if ( SampleResourceId != -1 )
    {
      *(_OWORD *)Buffer = 0;
      v15 = 0;
      v16 = 0;
      if ( SampleResourceId == 130 )
      {
        if ( !::Buffer && !LoadStringW(g_hInstance, 0x82u, &::Buffer, 24) )
          StringCchCopyW(&::Buffer, 0x18u, L"ABC");
        v13 = &::Buffer;
      }
      else
      {
        if ( LoadStringW(g_hInstance, SampleResourceId, Buffer, 24) )
        {
          if ( v12 - 150 <= 1 )
            CFontThumbnail::_SetGlyphSample(this, Buffer);
        }
        else
        {
          StringCchCopyW(Buffer, 0x18u, L"ABC");
        }
        v13 = Buffer;
      }
      StringCchCopyW(a5, 0x18u, v13);
    }
    SelectObject(hdc, v10);
    DeleteObject(v9);
  }
}

```

## disassembly

```asm
0x180027cf4  push    rbx
0x180027cf6  push    rbp
0x180027cf7  push    rsi
0x180027cf8  push    rdi
0x180027cf9  push    r12
0x180027cfb  push    r13
0x180027cfd  push    r14
0x180027cff  push    r15
0x180027d01  sub     rsp, 68h
0x180027d05  mov     rax, cs:__security_cookie
0x180027d0c  xor     rax, rsp
0x180027d0f  mov     [rsp+0A8h+var_58], rax
0x180027d14  mov     rsi, [rsp+0A8h+arg_20]
0x180027d1c  mov     r14, rcx
0x180027d1f  xor     r13d, r13d
0x180027d22  mov     rcx, r9; lplf
0x180027d25  mov     rbx, r8
0x180027d28  mov     rbp, rdx
0x180027d2b  mov     [rsi], r13w
0x180027d2f  call    cs:__imp_CreateFontIndirectW
0x180027d35  mov     r15, rax
0x180027d38  test    rax, rax
0x180027d3b  jz      loc_180027E33
0x180027d41  mov     rdx, rax; h
0x180027d44  mov     rcx, rbp; hdc
0x180027d47  call    cs:__imp_SelectObject
0x180027d4d  mov     r8, rbx; struct _ITEMIDLIST *
0x180027d50  mov     rdx, rbp; hdc
0x180027d53  mov     rcx, r14; this
0x180027d56  mov     r12, rax
0x180027d59  call    ?_GetSampleResourceId@CFontThumbnail@@AEAAHPEAUHDC__@@PEFBU_ITEMIDLIST@@@Z; CFontThumbnail::_GetSampleResourceId(HDC__ *,_ITEMIDLIST const *)
0x180027d5e  mov     edi, eax
0x180027d60  cmp     eax, 0FFFFFFFFh
0x180027d63  jz      loc_180027E1E
0x180027d69  xorps   xmm0, xmm0
0x180027d6c  mov     edx, 82h; uID
0x180027d71  movups  xmmword ptr [rsp+0A8h+Buffer], xmm0
0x180027d76  movups  [rsp+0A8h+var_78], xmm0
0x180027d7b  lea     ebx, [rdx-6Ah]
0x180027d7e  movups  [rsp+0A8h+var_68], xmm0
0x180027d83  cmp     eax, edx
0x180027d85  jnz     short loc_180027DC5
0x180027d87  cmp     cs:Buffer, r13w
0x180027d8f  lea     rdi, Buffer
0x180027d96  jnz     short loc_180027DC0
0x180027d98  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180027d9f  mov     r9d, ebx; cchBufferMax
0x180027da2  mov     r8, rdi; lpBuffer
0x180027da5  call    cs:__imp_LoadStringW
0x180027dab  test    eax, eax
0x180027dad  jnz     short loc_180027DC0
0x180027daf  lea     r8, c_szThumbnailSampleDefault; "ABC"
0x180027db6  mov     edx, ebx; unsigned __int64
0x180027db8  mov     rcx, rdi; unsigned __int16 *
0x180027dbb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027dc0  mov     r8, rdi
0x180027dc3  jmp     short loc_180027E13
0x180027dc5  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180027dcc  lea     r8, [rsp+0A8h+Buffer]; lpBuffer
0x180027dd1  mov     r9d, ebx; cchBufferMax
0x180027dd4  mov     edx, edi; uID
0x180027dd6  call    cs:__imp_LoadStringW
0x180027ddc  test    eax, eax
0x180027dde  jnz     short loc_180027DF6
0x180027de0  lea     r8, c_szThumbnailSampleDefault; "ABC"
0x180027de7  mov     rdx, rbx; unsigned __int64
0x180027dea  lea     rcx, [rsp+0A8h+Buffer]; unsigned __int16 *
0x180027def  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027df4  jmp     short loc_180027E0E
0x180027df6  lea     eax, [rdi-96h]
0x180027dfc  cmp     eax, 1
0x180027dff  ja      short loc_180027E0E
0x180027e01  lea     rdx, [rsp+0A8h+Buffer]; unsigned __int16 *
0x180027e06  mov     rcx, r14; this
0x180027e09  call    ?_SetGlyphSample@CFontThumbnail@@AEAAXPEAG@Z; CFontThumbnail::_SetGlyphSample(ushort *)
0x180027e0e  lea     r8, [rsp+0A8h+Buffer]; unsigned __int16 *
0x180027e13  mov     rdx, rbx; unsigned __int64
0x180027e16  mov     rcx, rsi; unsigned __int16 *
0x180027e19  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027e1e  mov     rdx, r12; h
0x180027e21  mov     rcx, rbp; hdc
0x180027e24  call    cs:__imp_SelectObject
0x180027e2a  mov     rcx, r15; ho
0x180027e2d  call    cs:__imp_DeleteObject
0x180027e33  mov     rcx, [rsp+0A8h+var_58]
0x180027e38  xor     rcx, rsp; StackCookie
0x180027e3b  call    __security_check_cookie
0x180027e40  add     rsp, 68h
0x180027e44  pop     r15
0x180027e46  pop     r14
0x180027e48  pop     r13
0x180027e4a  pop     r12
0x180027e4c  pop     rdi
0x180027e4d  pop     rsi
0x180027e4e  pop     rbp
0x180027e4f  pop     rbx
0x180027e50  retn
```
