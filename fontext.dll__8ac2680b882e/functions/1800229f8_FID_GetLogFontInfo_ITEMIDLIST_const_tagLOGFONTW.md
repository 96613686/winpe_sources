# FID_GetLogFontInfo(_ITEMIDLIST const *,tagLOGFONTW *)

- ea: `0x1800229f8`
- end: `0x180022c07`
- name: `?FID_GetLogFontInfo@@YAJPEFBU_ITEMIDLIST@@PEAUtagLOGFONTW@@@Z`
- size: `527`
- prototype: `__int64 __fastcall(const struct _ITEMIDLIST *, struct tagLOGFONTW *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800247a0`
- `0x180027140`

## callees

- `0x180006624`
- `0x18001a494`
- `0x1800226f8`
- `0x1800229f8`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022bc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022bc0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022b5d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022b5d`
- `GDI32!EnumFontFamiliesExW` at `0x180022af4`
- `GDI32!EnumFontFamiliesExW` at `0x180022af4`
- `GDI32!AddFontResourceExW` at `0x180022a5c`
- `GDI32!AddFontResourceExW` at `0x180022a5c`
- `GDI32!GetFontResourceInfoW` at `0x180022b31`
- `GDI32!GetFontResourceInfoW` at `0x180022b7d`
- `GDI32!GetFontResourceInfoW` at `0x180022b31`
- `GDI32!GetFontResourceInfoW` at `0x180022b7d`
- `GDI32!RemoveFontResourceExW` at `0x180022bdb`
- `GDI32!RemoveFontResourceExW` at `0x180022bdb`
- `USER32!ReleaseDC` at `0x180022aff`
- `USER32!ReleaseDC` at `0x180022aff`
- `USER32!GetDC` at `0x180022a87`
- `USER32!GetDC` at `0x180022a87`

## pseudocode

```c
__int64 __fastcall FID_GetLogFontInfo(const struct _ITEMIDLIST *a1, struct tagLOGFONTW *a2)
{
  unsigned __int16 *v4; // rax
  __int64 v5; // rsi
  HDC DC; // rbx
  _OWORD *v7; // rax
  _OWORD *v8; // rbx
  __int128 v9; // xmm1
  int v11; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v12; // [rsp+34h] [rbp-CCh] BYREF
  int v13; // [rsp+38h] [rbp-C8h] BYREF
  LPARAM lParam[4]; // [rsp+40h] [rbp-C0h] BYREF
  tagLOGFONTW Logfont; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR name[520]; // [rsp+C0h] [rbp-40h] BYREF

  v11 = -2147467259;
  memset_0(name, 0, sizeof(name));
  FID_FontResourceFileName(a1, name, 0x208u);
  if ( AddFontResourceExW(name, 0x10u, 0) )
  {
    v4 = CItemIDFactory<FID,156830041>::_IsValid(&a1->mkid.cb);
    v5 = (unsigned __int64)(v4 + 7) & -(__int64)(v4 != 0);
    if ( v5 )
    {
      DC = GetDC(0);
      if ( DC )
      {
        lParam[0] = v5;
        lParam[1] = (LPARAM)a2;
        lParam[2] = (LPARAM)&v11;
        memset_0(&Logfont, 0, sizeof(Logfont));
        Logfont.lfCharSet = 1;
        if ( StringCchCopyW(Logfont.lfFaceName, 0x20u, (const unsigned __int16 *)(v5 + 1888)) >= 0 )
          EnumFontFamiliesExW(
            DC,
            &Logfont,
            lambda_efaee31caf20594d93e3d4844f2d70f6_::_lambda_invoker_cdecl_,
            (LPARAM)lParam,
            0);
        ReleaseDC(0, DC);
      }
    }
    if ( v11 < 0 )
    {
      v12 = 1;
      v13 = 4;
      if ( (unsigned int)GetFontResourceInfoW(name, &v13, &v12, 0) )
      {
        if ( v12 <= 0x2C8590B )
        {
          v13 = 92 * v12;
          v7 = LocalAlloc(0x40u, 92 * v12);
          v8 = v7;
          if ( v7 )
          {
            if ( (unsigned int)GetFontResourceInfoW(name, &v13, v7, 2) )
            {
              *(_OWORD *)&a2->lfHeight = *v8;
              *(_OWORD *)&a2->lfWeight = v8[1];
              *(_OWORD *)&a2->lfFaceName[2] = v8[2];
              *(_OWORD *)&a2->lfFaceName[10] = v8[3];
              *(_OWORD *)&a2->lfFaceName[18] = v8[4];
              v9 = *(_OWORD *)((char *)v8 + 76);
              v11 = 0;
              *(_OWORD *)&a2->lfFaceName[24] = v9;
            }
            LocalFree(v8);
          }
          else
          {
            v11 = -2147024882;
          }
        }
      }
    }
    RemoveFontResourceExW(name, 0x10u, 0);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800229f8  mov     [rsp-8+arg_10], rbx
0x1800229fd  push    rbp
0x1800229fe  push    rsi
0x1800229ff  push    rdi
0x180022a00  lea     rbp, [rsp-3E0h]
0x180022a08  sub     rsp, 4E0h
0x180022a0f  mov     rax, cs:__security_cookie
0x180022a16  xor     rax, rsp
0x180022a19  mov     [rbp+3F0h+var_20], rax
0x180022a20  mov     rdi, rdx
0x180022a23  mov     [rsp+4F0h+var_4C0], 80004005h
0x180022a2b  mov     rbx, rcx
0x180022a2e  xor     edx, edx; Val
0x180022a30  lea     rcx, [rbp+3F0h+name]; void *
0x180022a34  mov     r8d, 410h; Size
0x180022a3a  call    memset_0
0x180022a3f  mov     r8d, 208h; unsigned int
0x180022a45  lea     rdx, [rbp+3F0h+name]; unsigned __int16 *
0x180022a49  mov     rcx, rbx; struct _ITEMIDLIST *
0x180022a4c  call    ?FID_FontResourceFileName@@YAXPEFBU_ITEMIDLIST@@PEAGI@Z; FID_FontResourceFileName(_ITEMIDLIST const *,ushort *,uint)
0x180022a51  xor     r8d, r8d; res
0x180022a54  lea     rcx, [rbp+3F0h+name]; name
0x180022a58  lea     edx, [r8+10h]; fl
0x180022a5c  call    cs:__imp_AddFontResourceExW
0x180022a62  test    eax, eax
0x180022a64  jz      loc_180022BE1
0x180022a6a  mov     rcx, rbx
0x180022a6d  call    ?_IsValid@?$CItemIDFactory@UFID@@$0JFJAJFJ@@@CAPEFBUCHILDITEMID@1@PEFBU_ITEMIDLIST@@@Z; CItemIDFactory<FID,156830041>::_IsValid(_ITEMIDLIST const *)
0x180022a72  lea     rcx, [rax+0Eh]
0x180022a76  neg     rax
0x180022a79  sbb     rsi, rsi
0x180022a7c  and     rsi, rcx
0x180022a7f  jz      loc_180022B05
0x180022a85  xor     ecx, ecx; hWnd
0x180022a87  call    cs:__imp_GetDC
0x180022a8d  mov     rbx, rax
0x180022a90  test    rax, rax
0x180022a93  jz      short loc_180022B05
0x180022a95  xor     edx, edx; Val
0x180022a97  mov     [rsp+4F0h+lParam], rsi
0x180022a9c  lea     rax, [rsp+4F0h+var_4C0]
0x180022aa1  mov     [rsp+4F0h+var_4A8], rdi
0x180022aa6  lea     rcx, [rsp+4F0h+Logfont]; void *
0x180022aab  mov     [rsp+4F0h+var_4A0], rax
0x180022ab0  lea     r8d, [rdx+5Ch]; Size
0x180022ab4  call    memset_0
0x180022ab9  lea     r8, [rsi+760h]; unsigned __int16 *
0x180022ac0  mov     [rsp+4F0h+Logfont.lfCharSet], 1
0x180022ac5  mov     edx, 20h ; ' '; unsigned __int64
0x180022aca  lea     rcx, [rsp+4F0h+Logfont.lfFaceName]; unsigned __int16 *
0x180022acf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180022ad4  test    eax, eax
0x180022ad6  js      short loc_180022AFA
0x180022ad8  lea     r9, [rsp+4F0h+lParam]; lParam
0x180022add  mov     [rsp+4F0h+dwFlags], 0; dwFlags
0x180022ae5  lea     r8, _lambda_efaee31caf20594d93e3d4844f2d70f6____lambda_invoker_cdecl_; lpProc
0x180022aec  mov     rcx, rbx; hdc
0x180022aef  lea     rdx, [rsp+4F0h+Logfont]; lpLogfont
0x180022af4  call    cs:__imp_EnumFontFamiliesExW
0x180022afa  mov     rdx, rbx; hDC
0x180022afd  xor     ecx, ecx; hWnd
0x180022aff  call    cs:__imp_ReleaseDC
0x180022b05  cmp     [rsp+4F0h+var_4C0], 0
0x180022b0a  jge     loc_180022BD0
0x180022b10  xor     r9d, r9d
0x180022b13  mov     [rsp+4F0h+var_4BC], 1
0x180022b1b  lea     r8, [rsp+4F0h+var_4BC]
0x180022b20  mov     [rsp+4F0h+var_4B8], 4
0x180022b28  lea     rdx, [rsp+4F0h+var_4B8]
0x180022b2d  lea     rcx, [rbp+3F0h+name]
0x180022b31  call    cs:__imp_GetFontResourceInfoW
0x180022b37  test    eax, eax
0x180022b39  jz      loc_180022BD0
0x180022b3f  cmp     [rsp+4F0h+var_4BC], 2C8590Bh
0x180022b47  ja      loc_180022BD0
0x180022b4d  imul    eax, [rsp+4F0h+var_4BC], 5Ch ; '\'
0x180022b52  mov     ecx, 40h ; '@'; uFlags
0x180022b57  mov     edx, eax; uBytes
0x180022b59  mov     [rsp+4F0h+var_4B8], eax
0x180022b5d  call    cs:__imp_LocalAlloc
0x180022b63  mov     rbx, rax
0x180022b66  test    rax, rax
0x180022b69  jz      short loc_180022BC8
0x180022b6b  mov     r9d, 2
0x180022b71  lea     rdx, [rsp+4F0h+var_4B8]
0x180022b76  mov     r8, rax
0x180022b79  lea     rcx, [rbp+3F0h+name]
0x180022b7d  call    cs:__imp_GetFontResourceInfoW
0x180022b83  test    eax, eax
0x180022b85  jz      short loc_180022BBD
0x180022b87  movups  xmm0, xmmword ptr [rbx]
0x180022b8a  movaps  xmmword ptr [rdi], xmm0
0x180022b8d  movups  xmm1, xmmword ptr [rbx+10h]
0x180022b91  movaps  xmmword ptr [rdi+10h], xmm1
0x180022b95  movups  xmm0, xmmword ptr [rbx+20h]
0x180022b99  movaps  xmmword ptr [rdi+20h], xmm0
0x180022b9d  movups  xmm1, xmmword ptr [rbx+30h]
0x180022ba1  movaps  xmmword ptr [rdi+30h], xmm1
0x180022ba5  movups  xmm0, xmmword ptr [rbx+40h]
0x180022ba9  movaps  xmmword ptr [rdi+40h], xmm0
0x180022bad  movups  xmm1, xmmword ptr [rbx+4Ch]
0x180022bb1  mov     [rsp+4F0h+var_4C0], 0
0x180022bb9  movups  xmmword ptr [rdi+4Ch], xmm1
0x180022bbd  mov     rcx, rbx; hMem
0x180022bc0  call    cs:__imp_LocalFree
0x180022bc6  jmp     short loc_180022BD0
0x180022bc8  mov     [rsp+4F0h+var_4C0], 8007000Eh
0x180022bd0  xor     r8d, r8d; pdv
0x180022bd3  lea     rcx, [rbp+3F0h+name]; name
0x180022bd7  lea     edx, [r8+10h]; fl
0x180022bdb  call    cs:__imp_RemoveFontResourceExW
0x180022be1  mov     eax, [rsp+4F0h+var_4C0]
0x180022be5  mov     rcx, [rbp+3F0h+var_20]
0x180022bec  xor     rcx, rsp; StackCookie
0x180022bef  call    __security_check_cookie
0x180022bf4  mov     rbx, [rsp+4F0h+arg_10]
0x180022bfc  add     rsp, 4E0h
0x180022c03  pop     rdi
0x180022c04  pop     rsi
0x180022c05  pop     rbp
0x180022c06  retn
```
