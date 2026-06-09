# CMmStream::CreateTempFileMapping(ulong)

- ea: `0x1800123c4`
- end: `0x18001247f`
- name: `?CreateTempFileMapping@CMmStream@@QEAAXK@Z`
- size: `187`
- prototype: `void __fastcall(CMmStream *this, DWORD dwMaximumSizeLow)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x1800121b4`

## callees

- `0x18000fab0`
- `0x1800123c4`
- `0x18001f458`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800123e7`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800123e7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001240c`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001240c`

## string_xrefs

- `0x180012421`: `[HTML] File mapping of temporary file failed\n`
- `0x180012450`: `[HTML] Mapping view of temporary file failed\n`

## pseudocode

```c
void __fastcall CMmStream::CreateTempFileMapping(CMmStream *this, DWORD dwMaximumSizeLow)
{
  HANDLE FileMappingW; // rax
  const wchar_t *v4; // r9
  LPVOID v5; // rax
  const wchar_t *v6; // r9
  const char *v7; // r9
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, dwMaximumSizeLow, 0);
  *((_QWORD *)this + 3) = FileMappingW;
  if ( !FileMappingW )
  {
    SearchIndexerDebug::Error(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
      (const wchar_t *)0x242,
      (unsigned int)L"[HTML] File mapping of temporary file failed\n",
      v4);
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x243,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
      v7);
  }
  v5 = MapViewOfFile(FileMappingW, 2u, 0, 0, 0);
  *((_QWORD *)this + 4) = v5;
  if ( !v5 )
  {
    SearchIndexerDebug::Error(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
      (const wchar_t *)0x249,
      (unsigned int)L"[HTML] Mapping view of temporary file failed\n",
      v6);
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x24A,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
      v8);
  }
}

```

## disassembly

```asm
0x1800123c4  push    rbx
0x1800123c6  sub     rsp, 30h
0x1800123ca  xor     r9d, r9d; dwMaximumSizeHigh
0x1800123cd  mov     [rsp+38h+lpName], 0; lpName
0x1800123d6  mov     rbx, rcx
0x1800123d9  mov     [rsp+38h+dwMaximumSizeLow], edx; dwMaximumSizeLow
0x1800123dd  xor     edx, edx; lpFileMappingAttributes
0x1800123df  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800123e3  lea     r8d, [r9+4]; flProtect
0x1800123e7  call    cs:__imp_CreateFileMappingW
0x1800123ed  mov     [rbx+18h], rax
0x1800123f1  test    rax, rax
0x1800123f4  jz      short loc_180012421
0x1800123f6  xor     r9d, r9d; dwFileOffsetLow
0x1800123f9  mov     qword ptr [rsp+38h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x180012402  xor     r8d, r8d; dwFileOffsetHigh
0x180012405  mov     rcx, rax; hFileMappingObject
0x180012408  lea     edx, [r9+2]; dwDesiredAccess
0x18001240c  call    cs:__imp_MapViewOfFile
0x180012412  mov     [rbx+20h], rax
0x180012416  test    rax, rax
0x180012419  jz      short loc_180012450
0x18001241b  add     rsp, 30h
0x18001241f  pop     rbx
0x180012420  retn
0x180012421  lea     r8, aHtmlFileMappin; "[HTML] File mapping of temporary file f"...
0x180012428  mov     edx, 242h; wchar_t *
0x18001242d  lea     rcx, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180012434  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x180012439  mov     rcx, [rsp+38h]; this
0x18001243e  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180012445  mov     edx, 243h; void *
0x18001244a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180012450  lea     r8, aHtmlMappingVie; "[HTML] Mapping view of temporary file f"...
0x180012457  mov     edx, 249h; wchar_t *
0x18001245c  lea     rcx, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180012463  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x180012468  mov     rcx, [rsp+38h]; this
0x18001246d  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180012474  mov     edx, 24Ah; void *
0x180012479  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
