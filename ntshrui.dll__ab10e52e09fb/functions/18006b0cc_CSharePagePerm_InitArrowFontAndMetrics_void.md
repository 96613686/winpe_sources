# CSharePagePerm::_InitArrowFontAndMetrics(void)

- ea: `0x18006b0cc`
- end: `0x18006b273`
- name: `?_InitArrowFontAndMetrics@CSharePagePerm@@AEAAXXZ`
- size: `423`
- prototype: `void __fastcall(CSharePagePerm *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006b27c`

## callees

- `0x18001a570`
- `0x1800254e0`
- `0x18006b0cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006b1f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006b1f1`
- `GDI32!CreateFontW` at `0x18006b1e1`
- `GDI32!CreateFontW` at `0x18006b1e1`
- `GDI32!SelectObject` at `0x18006b216`
- `GDI32!SelectObject` at `0x18006b216`
- `GDI32!GetTextMetricsW` at `0x18006b12c`
- `GDI32!GetTextMetricsW` at `0x18006b12c`
- `USER32!DrawTextW` at `0x18006b235`
- `USER32!DrawTextW` at `0x18006b235`
- `USER32!GetSystemMetrics` at `0x18006b140`
- `USER32!GetSystemMetrics` at `0x18006b140`
- `USER32!GetDC` at `0x18006b100`
- `USER32!GetDC` at `0x18006b100`
- `USER32!ReleaseDC` at `0x18006b255`
- `USER32!ReleaseDC` at `0x18006b255`

## pseudocode

```c
void __fastcall CSharePagePerm::_InitArrowFontAndMetrics(CSharePagePerm *this)
{
  HDC DC; // rax
  HDC v3; // rsi
  __int16 SystemMetrics; // ax
  HMODULE v5; // rcx
  WCHAR *v6; // rbx
  void *v7; // rdx
  int cWeight; // [rsp+20h] [rbp-79h]
  WCHAR chText; // [rsp+70h] [rbp-29h] BYREF
  LPCWSTR pszFaceName[2]; // [rsp+78h] [rbp-21h] BYREF
  struct tagTEXTMETRICW tm; // [rsp+88h] [rbp-11h] BYREF

  *((_QWORD *)this + 38) = 0;
  DC = GetDC(*((HWND *)this + 31));
  v3 = DC;
  if ( DC )
  {
    memset(&tm, 0, sizeof(tm));
    GetTextMetricsW(DC, &tm);
    *((_DWORD *)this + 76) = tm.tmMaxCharWidth;
    SystemMetrics = GetSystemMetrics(6);
    v5 = g_hInstance;
    pszFaceName[0] = 0;
    *((_DWORD *)this + 77) = ((LOWORD(tm.tmHeight) + LOWORD(tm.tmExternalLeading) + SystemMetrics) & 0xFFFE) - 1;
    TResourceStringAllocCopyEx<unsigned short *>(v5, cWeight, pszFaceName);
    v6 = (WCHAR *)pszFaceName[0];
    *((_QWORD *)this + 36) = CreateFontW(*((_DWORD *)this + 77), 0, 0, 0, 400, 0, 0, 0, 2u, 0, 0, 0, 0, pszFaceName[0]);
    CoTaskMemFree(v6);
    v7 = (void *)*((_QWORD *)this + 36);
    if ( v7 )
    {
      chText = 54;
      *(_OWORD *)pszFaceName = 0;
      SelectObject(v3, v7);
      if ( DrawTextW(v3, &chText, 1, (LPRECT)pszFaceName, 0x424u) )
        *((_DWORD *)this + 76) = LODWORD(pszFaceName[1]) - LODWORD(pszFaceName[0]);
    }
    ReleaseDC(*((HWND *)this + 31), v3);
  }
}

```

## disassembly

```asm
0x18006b0cc  push    rbp
0x18006b0ce  push    rbx
0x18006b0cf  push    rsi
0x18006b0d0  push    rdi
0x18006b0d1  lea     rbp, [rsp-3Fh]
0x18006b0d6  sub     rsp, 0D8h
0x18006b0dd  mov     rax, cs:__security_cookie
0x18006b0e4  xor     rax, rsp
0x18006b0e7  mov     [rbp+57h+var_28], rax
0x18006b0eb  mov     rdi, rcx
0x18006b0ee  mov     qword ptr [rcx+130h], 0
0x18006b0f9  mov     rcx, [rcx+0F8h]; hWnd
0x18006b100  call    cs:__imp_GetDC
0x18006b106  mov     rsi, rax
0x18006b109  test    rax, rax
0x18006b10c  jz      loc_18006B25B
0x18006b112  xorps   xmm0, xmm0
0x18006b115  lea     rdx, [rbp+57h+tm]; lptm
0x18006b119  movups  xmmword ptr [rbp+57h+tm.tmOverhang], xmm0
0x18006b11d  mov     rcx, rax; hdc
0x18006b120  movups  xmmword ptr [rbp+57h+tm.tmFirstChar], xmm0
0x18006b124  movups  xmmword ptr [rbp+57h+tm.tmHeight], xmm0
0x18006b128  movups  xmmword ptr [rbp+57h+tm.tmExternalLeading], xmm0
0x18006b12c  call    cs:__imp_GetTextMetricsW
0x18006b132  mov     ecx, [rbp+57h+tm.tmMaxCharWidth]
0x18006b135  mov     [rdi+130h], ecx
0x18006b13b  mov     ecx, 6; nIndex
0x18006b140  call    cs:__imp_GetSystemMetrics
0x18006b146  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x18006b14d  lea     r9, _ResourceStringAllocCopyExCoAlloc
0x18006b154  add     eax, [rbp+57h+tm.tmExternalLeading]
0x18006b157  mov     edx, 0CFBh
0x18006b15c  add     eax, [rbp+57h+tm.tmHeight]
0x18006b15f  and     eax, 0FFFEh
0x18006b164  mov     [rbp+57h+var_78], 0
0x18006b16c  dec     eax
0x18006b16e  mov     [rdi+134h], eax
0x18006b174  lea     rax, [rbp+57h+var_78]
0x18006b178  mov     qword ptr [rsp+0F0h+bItalic], rax; void *
0x18006b17d  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x18006b182  mov     rbx, [rbp+57h+var_78]
0x18006b186  xor     r9d, r9d; cOrientation
0x18006b189  mov     ecx, [rdi+134h]; cHeight
0x18006b18f  xor     r8d, r8d; cEscapement
0x18006b192  mov     [rsp+0F0h+pszFaceName], rbx; pszFaceName
0x18006b197  xor     edx, edx; cWidth
0x18006b199  mov     [rsp+0F0h+iPitchAndFamily], 0; iPitchAndFamily
0x18006b1a1  mov     [rsp+0F0h+iQuality], 0; iQuality
0x18006b1a9  mov     [rsp+0F0h+iClipPrecision], 0; iClipPrecision
0x18006b1b1  mov     [rsp+0F0h+iOutPrecision], 0; iOutPrecision
0x18006b1b9  mov     [rsp+0F0h+iCharSet], 2; iCharSet
0x18006b1c1  mov     [rsp+0F0h+bStrikeOut], 0; bStrikeOut
0x18006b1c9  mov     [rsp+0F0h+bUnderline], 0; bUnderline
0x18006b1d1  mov     [rsp+0F0h+bItalic], 0; bItalic
0x18006b1d9  mov     [rsp+0F0h+cWeight], 190h; cWeight
0x18006b1e1  call    cs:__imp_CreateFontW
0x18006b1e7  mov     rcx, rbx; pv
0x18006b1ea  mov     [rdi+120h], rax
0x18006b1f1  call    cs:__imp_CoTaskMemFree
0x18006b1f7  mov     rdx, [rdi+120h]; h
0x18006b1fe  test    rdx, rdx
0x18006b201  jz      short loc_18006B24B
0x18006b203  xorps   xmm0, xmm0
0x18006b206  mov     eax, 36h ; '6'
0x18006b20b  mov     rcx, rsi; hdc
0x18006b20e  mov     [rbp+57h+chText], ax
0x18006b212  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x18006b216  call    cs:__imp_SelectObject
0x18006b21c  lea     r9, [rbp+57h+var_78]; lprc
0x18006b220  mov     [rsp+0F0h+cWeight], 424h; format
0x18006b228  mov     r8d, 1; cchText
0x18006b22e  lea     rdx, [rbp+57h+chText]; lpchText
0x18006b232  mov     rcx, rsi; hdc
0x18006b235  call    cs:__imp_DrawTextW
0x18006b23b  test    eax, eax
0x18006b23d  jz      short loc_18006B24B
0x18006b23f  mov     eax, dword ptr [rbp+57h+var_78+8]
0x18006b242  sub     eax, dword ptr [rbp+57h+var_78]
0x18006b245  mov     [rdi+130h], eax
0x18006b24b  mov     rcx, [rdi+0F8h]; hWnd
0x18006b252  mov     rdx, rsi; hDC
0x18006b255  call    cs:__imp_ReleaseDC
0x18006b25b  mov     rcx, [rbp+57h+var_28]
0x18006b25f  xor     rcx, rsp; StackCookie
0x18006b262  call    __security_check_cookie
0x18006b267  add     rsp, 0D8h
0x18006b26e  pop     rdi
0x18006b26f  pop     rsi
0x18006b270  pop     rbx
0x18006b271  pop     rbp
0x18006b272  retn
```
