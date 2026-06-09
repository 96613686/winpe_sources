# CMmStream::Close(void)

- ea: `0x1800213e0`
- end: `0x180021521`
- name: `?Close@CMmStream@@UEAAXXZ`
- size: `321`
- prototype: `void __fastcall(CMmStream *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000fab0`
- `0x18001f458`
- `0x1800213e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021491`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021491`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800213f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002143d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800214da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800213f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002143d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800214da`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180021487`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180021487`

## string_xrefs

- `0x180021497`: `[HTML] UnmapViewOfFile _pTempFileBuf returned %d\n`
- `0x1800214e4`: `[HTML] Closing _hTempFileMap handle failed\n`

## pseudocode

```c
void __fastcall CMmStream::Close(CMmStream *this)
{
  void *v2; // rcx
  const wchar_t *v3; // r9
  const char *v4; // r9
  void *v5; // rcx
  const wchar_t *v6; // r9
  const char *v7; // r9
  const void *v8; // rcx
  DWORD LastError; // eax
  const char *v10; // r9
  void *v11; // rcx
  const wchar_t *v12; // r9
  const char *v13; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    if ( !CloseHandle(v2) )
    {
      SearchIndexerDebug::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
        (const wchar_t *)0x11E,
        (unsigned int)L"[HTML] Closing file mapping _hMap failed\n",
        v3);
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x11F,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
        v4);
    }
    *((_QWORD *)this + 2) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 1);
  if ( v5 != (void *)-1LL )
  {
    if ( !CloseHandle(v5) )
    {
      SearchIndexerDebug::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
        (const wchar_t *)0x129,
        (unsigned int)L"[HTML] Closing _hFile handle failed\n",
        v6);
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x12A,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
        v7);
    }
    *((_QWORD *)this + 1) = -1;
  }
  v8 = (const void *)*((_QWORD *)this + 4);
  if ( v8 )
  {
    if ( !UnmapViewOfFile(v8) )
    {
      LastError = GetLastError();
      SearchIndexerDebug::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
        (const wchar_t *)0x133,
        (unsigned int)L"[HTML] UnmapViewOfFile _pTempFileBuf returned %d\n",
        (const wchar_t *)LastError);
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x134,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
        v10);
    }
    *((_QWORD *)this + 4) = 0;
  }
  v11 = (void *)*((_QWORD *)this + 3);
  if ( v11 )
  {
    if ( !CloseHandle(v11) )
    {
      SearchIndexerDebug::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
        (const wchar_t *)0x13E,
        (unsigned int)L"[HTML] Closing _hTempFileMap handle failed\n",
        v12);
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x13F,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
        v13);
    }
    *((_QWORD *)this + 3) = -1;
  }
}

```

## disassembly

```asm
0x1800213e0  push    rbx
0x1800213e2  sub     rsp, 20h
0x1800213e6  mov     rbx, rcx
0x1800213e9  mov     rcx, [rcx+10h]; hObject
0x1800213ed  test    rcx, rcx
0x1800213f0  jz      short loc_180021433
0x1800213f2  call    cs:__imp_CloseHandle
0x1800213f8  test    eax, eax
0x1800213fa  jnz     short loc_18002142B
0x1800213fc  lea     r8, aHtmlClosingFil; "[HTML] Closing file mapping _hMap faile"...
0x180021403  mov     edx, 11Eh; wchar_t *
0x180021408  lea     rcx, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18002140f  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x180021414  mov     rcx, [rsp+28h]; this
0x180021419  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180021420  mov     edx, 11Fh; void *
0x180021425  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002142b  mov     qword ptr [rbx+10h], 0
0x180021433  mov     rcx, [rbx+8]; hObject
0x180021437  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002143b  jz      short loc_18002147E
0x18002143d  call    cs:__imp_CloseHandle
0x180021443  test    eax, eax
0x180021445  jnz     short loc_180021476
0x180021447  lea     r8, aHtmlClosingHfi; "[HTML] Closing _hFile handle failed\n"
0x18002144e  mov     edx, 129h; wchar_t *
0x180021453  lea     rcx, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18002145a  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x18002145f  mov     rcx, [rsp+28h]; this
0x180021464  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18002146b  mov     edx, 12Ah; void *
0x180021470  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180021476  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x18002147e  mov     rcx, [rbx+20h]; lpBaseAddress
0x180021482  test    rcx, rcx
0x180021485  jz      short loc_1800214D1
0x180021487  call    cs:__imp_UnmapViewOfFile
0x18002148d  test    eax, eax
0x18002148f  jnz     short loc_1800214C9
0x180021491  call    cs:__imp_GetLastError
0x180021497  lea     r8, aHtmlUnmapviewo_1; "[HTML] UnmapViewOfFile _pTempFileBuf re"...
0x18002149e  mov     edx, 133h; wchar_t *
0x1800214a3  mov     r9d, eax; wchar_t *
0x1800214a6  lea     rcx, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x1800214ad  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800214b2  mov     rcx, [rsp+28h]; this
0x1800214b7  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\fil"...
0x1800214be  mov     edx, 134h; void *
0x1800214c3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800214c9  mov     qword ptr [rbx+20h], 0
0x1800214d1  mov     rcx, [rbx+18h]; hObject
0x1800214d5  test    rcx, rcx
0x1800214d8  jz      short loc_18002151B
0x1800214da  call    cs:__imp_CloseHandle
0x1800214e0  test    eax, eax
0x1800214e2  jnz     short loc_180021513
0x1800214e4  lea     r8, aHtmlClosingHte; "[HTML] Closing _hTempFileMap handle fai"...
0x1800214eb  mov     edx, 13Eh; wchar_t *
0x1800214f0  lea     rcx, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x1800214f7  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800214fc  mov     rcx, [rsp+28h]; this
0x180021501  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180021508  mov     edx, 13Fh; void *
0x18002150d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180021513  mov     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x18002151b  add     rsp, 20h
0x18002151f  pop     rbx
0x180021520  retn
```
