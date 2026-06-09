# CMmStream::InitWithTempFile(void)

- ea: `0x180012584`
- end: `0x180012691`
- name: `?InitWithTempFile@CMmStream@@QEAAXXZ`
- size: `269`
- prototype: `void __fastcall(CMmStream *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180012488`

## callees

- `0x18000fab0`
- `0x180012584`
- `0x18001f458`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012635`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012596`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800125e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012596`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800125e1`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001262b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001262b`

## string_xrefs

- `0x18001263b`: `[HTML] UnmapViewOfFile _pTempFileBuf returned %d\n`

## pseudocode

```c
void __fastcall CMmStream::InitWithTempFile(CMmStream *this)
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
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    if ( !CloseHandle(v2) )
    {
      SearchIndexerDebug::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
        (const wchar_t *)0xE9,
        (unsigned int)L"[HTML] Closing file mapping _hMap failed\n",
        v3);
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xEA,
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
        (const wchar_t *)0xF4,
        (unsigned int)L"[HTML] Closing _hFile handle failed\n",
        v6);
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xF5,
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
        (const wchar_t *)0xFE,
        (unsigned int)L"[HTML] UnmapViewOfFile _pTempFileBuf returned %d\n",
        (const wchar_t *)LastError);
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xFF,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
        v10);
    }
    *((_QWORD *)this + 4) = 0;
  }
  *((_QWORD *)this + 2) = *((_QWORD *)this + 3);
  *((_DWORD *)this + 11) = *((_DWORD *)this + 10);
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x180012584  push    rbx
0x180012586  sub     rsp, 20h
0x18001258a  mov     rbx, rcx
0x18001258d  mov     rcx, [rcx+10h]; hObject
0x180012591  test    rcx, rcx
0x180012594  jz      short loc_1800125D7
0x180012596  call    cs:__imp_CloseHandle
0x18001259c  test    eax, eax
0x18001259e  jnz     short loc_1800125CF
0x1800125a0  lea     r8, aHtmlClosingFil; "[HTML] Closing file mapping _hMap faile"...
0x1800125a7  mov     edx, 0E9h; wchar_t *
0x1800125ac  lea     rcx, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x1800125b3  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800125b8  mov     rcx, [rsp+28h]; this
0x1800125bd  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\fil"...
0x1800125c4  mov     edx, 0EAh; void *
0x1800125c9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800125cf  mov     qword ptr [rbx+10h], 0
0x1800125d7  mov     rcx, [rbx+8]; hObject
0x1800125db  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800125df  jz      short loc_180012622
0x1800125e1  call    cs:__imp_CloseHandle
0x1800125e7  test    eax, eax
0x1800125e9  jnz     short loc_18001261A
0x1800125eb  lea     r8, aHtmlClosingHfi; "[HTML] Closing _hFile handle failed\n"
0x1800125f2  mov     edx, 0F4h; wchar_t *
0x1800125f7  lea     rcx, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x1800125fe  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x180012603  mov     rcx, [rsp+28h]; this
0x180012608  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18001260f  mov     edx, 0F5h; void *
0x180012614  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001261a  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x180012622  mov     rcx, [rbx+20h]; lpBaseAddress
0x180012626  test    rcx, rcx
0x180012629  jz      short loc_180012675
0x18001262b  call    cs:__imp_UnmapViewOfFile
0x180012631  test    eax, eax
0x180012633  jnz     short loc_18001266D
0x180012635  call    cs:__imp_GetLastError
0x18001263b  lea     r8, aHtmlUnmapviewo_1; "[HTML] UnmapViewOfFile _pTempFileBuf re"...
0x180012642  mov     edx, 0FEh; wchar_t *
0x180012647  mov     r9d, eax; wchar_t *
0x18001264a  lea     rcx, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180012651  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x180012656  mov     rcx, [rsp+28h]; this
0x18001265b  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180012662  mov     edx, 0FFh; void *
0x180012667  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001266d  mov     qword ptr [rbx+20h], 0
0x180012675  mov     rax, [rbx+18h]
0x180012679  mov     [rbx+10h], rax
0x18001267d  mov     eax, [rbx+28h]
0x180012680  mov     [rbx+2Ch], eax
0x180012683  mov     qword ptr [rbx+18h], 0
0x18001268b  add     rsp, 20h
0x18001268f  pop     rbx
0x180012690  retn
```
