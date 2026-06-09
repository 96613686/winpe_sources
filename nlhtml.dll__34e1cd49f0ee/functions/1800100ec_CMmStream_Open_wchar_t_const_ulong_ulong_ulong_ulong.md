# CMmStream::Open(wchar_t const *,ulong,ulong,ulong,ulong)

- ea: `0x1800100ec`
- end: `0x18001027f`
- name: `?Open@CMmStream@@QEAAXPEB_WKKKK@Z`
- size: `403`
- prototype: `void __fastcall(CMmStream *this, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x18000f98c`

## callees

- `0x18000fab0`
- `0x1800100ec`
- `0x180010288`
- `0x18001f458`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001014b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010181`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001024e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001014b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010181`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001024e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180010201`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180010201`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180010173`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180010173`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001012e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001012e`

## string_xrefs

- `0x180010254`: `[HTML] Open failed on MM Stream; GetLastError()=0x%x\n`
- `0x18001019d`: `[HTML] Open stream %ws failed\n`

## pseudocode

```c
void __fastcall CMmStream::Open(CMmStream *this, const wchar_t *a2)
{
  DWORD *v4; // rdi
  DWORD FileSize; // eax
  const char *v6; // r9
  DWORD dwMaximumSizeLow; // ecx
  HANDLE FileMappingW; // rax
  const wchar_t *v9; // r9
  const char *v10; // r9
  DWORD LastError; // eax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *((_DWORD *)this + 13) = 0;
  *((_QWORD *)this + 1) = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( !(*(unsigned int (__fastcall **)(CMmStream *))(*(_QWORD *)this + 8LL))(this) )
    GetLastError();
  if ( (*(unsigned int (__fastcall **)(CMmStream *))(*(_QWORD *)this + 8LL))(this) )
  {
    v4 = (DWORD *)((char *)this + 48);
    FileSize = GetFileSize(*((HANDLE *)this + 1), (LPDWORD)this + 12);
    *((_DWORD *)this + 11) = FileSize;
    if ( FileSize == -1 && GetLastError() )
    {
      (*(void (__fastcall **)(CMmStream *))(*(_QWORD *)this + 16LL))(this);
      SearchIndexerDebug::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
        (const wchar_t *)0xA2,
        (unsigned int)L"[HTML] Open stream %ws failed\n",
        a2);
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xA3,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
        v6);
    }
    dwMaximumSizeLow = *((_DWORD *)this + 11);
    if ( dwMaximumSizeLow || *v4 )
    {
      FileMappingW = CreateFileMappingW(
                       *((HANDLE *)this + 1),
                       0,
                       *((_DWORD *)this + 13) != 0 ? 4 : 2,
                       *v4,
                       dwMaximumSizeLow,
                       0);
      *((_QWORD *)this + 2) = FileMappingW;
      if ( !FileMappingW )
      {
        (*(void (__fastcall **)(CMmStream *))(*(_QWORD *)this + 16LL))(this);
        SearchIndexerDebug::Error(
          (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
          (const wchar_t *)0xCB,
          (unsigned int)L"[HTML] File mapping failed\n",
          v9);
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xCC,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
          v10);
      }
    }
  }
  else
  {
    LastError = GetLastError();
    SearchIndexerDebug::Information(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
      (const wchar_t *)0xD2,
      (unsigned int)L"[HTML] Open failed on MM Stream; GetLastError()=0x%x\n",
      (const wchar_t *)LastError);
  }
}

```

## disassembly

```asm
0x1800100ec  mov     rax, rsp
0x1800100ef  mov     [rax+8], rbx
0x1800100f3  mov     [rax+10h], rsi
0x1800100f7  push    rdi
0x1800100f8  sub     rsp, 40h
0x1800100fc  mov     rsi, rdx
0x1800100ff  mov     qword ptr [rax-18h], 0
0x180010107  xor     r9d, r9d; lpSecurityAttributes
0x18001010a  mov     dword ptr [rcx+34h], 0
0x180010111  mov     rbx, rcx
0x180010114  mov     dword ptr [rax-20h], 80h
0x18001011b  mov     edx, 80000000h; dwDesiredAccess
0x180010120  mov     dword ptr [rax-28h], 3
0x180010127  mov     rcx, rsi; lpFileName
0x18001012a  lea     r8d, [r9+1]; dwShareMode
0x18001012e  call    cs:__imp_CreateFileW
0x180010134  mov     [rbx+8], rax
0x180010138  mov     rcx, rbx
0x18001013b  mov     rax, [rbx]
0x18001013e  mov     rax, [rax+8]
0x180010142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010147  test    eax, eax
0x180010149  jnz     short loc_180010151
0x18001014b  call    cs:__imp_GetLastError
0x180010151  mov     rax, [rbx]
0x180010154  mov     rcx, rbx
0x180010157  mov     rax, [rax+8]
0x18001015b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010160  test    eax, eax
0x180010162  jz      loc_18001024E
0x180010168  mov     rcx, [rbx+8]; hFile
0x18001016c  lea     rdi, [rbx+30h]
0x180010170  mov     rdx, rdi; lpFileSizeHigh
0x180010173  call    cs:__imp_GetFileSize
0x180010179  mov     [rbx+2Ch], eax
0x18001017c  cmp     eax, 0FFFFFFFFh
0x18001017f  jnz     short loc_1800101CC
0x180010181  call    cs:__imp_GetLastError
0x180010187  test    eax, eax
0x180010189  jz      short loc_1800101CC
0x18001018b  mov     rax, [rbx]
0x18001018e  mov     rcx, rbx
0x180010191  mov     rax, [rax+10h]
0x180010195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001019a  mov     r9, rsi; wchar_t *
0x18001019d  lea     r8, aHtmlOpenStream; "[HTML] Open stream %ws failed\n"
0x1800101a4  mov     edx, 0A2h; wchar_t *
0x1800101a9  lea     rcx, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x1800101b0  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800101b5  mov     rcx, [rsp+48h]; this
0x1800101ba  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\fil"...
0x1800101c1  mov     edx, 0A3h; void *
0x1800101c6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800101cc  mov     ecx, [rbx+2Ch]
0x1800101cf  test    ecx, ecx
0x1800101d1  jnz     short loc_1800101DB
0x1800101d3  cmp     [rdi], ecx
0x1800101d5  jz      loc_18001026F
0x1800101db  mov     eax, [rbx+34h]
0x1800101de  mov     r9d, [rdi]; dwMaximumSizeHigh
0x1800101e1  neg     eax
0x1800101e3  mov     [rsp+48h+lpName], 0; lpName
0x1800101ec  sbb     r8d, r8d
0x1800101ef  mov     [rsp+48h+dwMaximumSizeLow], ecx; dwMaximumSizeLow
0x1800101f3  mov     rcx, [rbx+8]; hFile
0x1800101f7  and     r8d, 2
0x1800101fb  add     r8d, 2; flProtect
0x1800101ff  xor     edx, edx; lpFileMappingAttributes
0x180010201  call    cs:__imp_CreateFileMappingW
0x180010207  mov     [rbx+10h], rax
0x18001020b  test    rax, rax
0x18001020e  jnz     short loc_18001026F
0x180010210  mov     rax, [rbx]
0x180010213  mov     rcx, rbx
0x180010216  mov     rax, [rax+10h]
0x18001021a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001021f  lea     r8, aHtmlFileMappin_0; "[HTML] File mapping failed\n"
0x180010226  mov     edx, 0CBh; wchar_t *
0x18001022b  lea     rcx, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180010232  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x180010237  mov     rcx, [rsp+48h]; this
0x18001023c  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180010243  mov     edx, 0CCh; void *
0x180010248  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001024e  call    cs:__imp_GetLastError
0x180010254  lea     r8, aHtmlOpenFailed; "[HTML] Open failed on MM Stream; GetLas"...
0x18001025b  mov     edx, 0D2h; wchar_t *
0x180010260  mov     r9d, eax; wchar_t *
0x180010263  lea     rcx, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18001026a  call    ?Information@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Information(wchar_t const *,uint,wchar_t const *,...)
0x18001026f  mov     rbx, [rsp+48h+arg_0]
0x180010274  mov     rsi, [rsp+48h+arg_8]
0x180010279  add     rsp, 40h
0x18001027d  pop     rdi
0x18001027e  retn
```
