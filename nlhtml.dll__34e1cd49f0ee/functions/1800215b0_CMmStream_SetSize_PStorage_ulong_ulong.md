# CMmStream::SetSize(PStorage &,ulong,ulong)

- ea: `0x1800215b0`
- end: `0x1800216f8`
- name: `?SetSize@CMmStream@@UEAAXAEAVPStorage@@KK@Z`
- size: `328`
- prototype: `void(CMmStream *__hidden this, struct PStorage *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x18000fab0`
- `0x18001f458`
- `0x1800215b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021619`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021623`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021619`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021623`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021669`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800215ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800215ce`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800216bd`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800216bd`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002160e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002160e`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18002165f`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18002165f`

## string_xrefs

- `0x180021629`: `[HTML] CMmStream::Close -- SetFilePointer returned %d\n`

## pseudocode

```c
void __fastcall CMmStream::SetSize(CMmStream *this, struct PStorage *a2, DWORD a3, LONG a4)
{
  void *v6; // rcx
  DWORD LastError; // eax
  const char *v8; // r9
  DWORD v9; // eax
  const char *v10; // r9
  HANDLE FileMappingW; // rax
  const char *v12; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LONG DistanceToMoveHigh; // [rsp+68h] [rbp+20h] BYREF

  DistanceToMoveHigh = a4;
  v6 = (void *)*((_QWORD *)this + 2);
  if ( v6 )
  {
    CloseHandle(v6);
    a4 = DistanceToMoveHigh;
  }
  if ( __SPAIR64__(a4, a3) < *(_QWORD *)((char *)this + 44) )
  {
    if ( SetFilePointer(*((HANDLE *)this + 1), a3, &DistanceToMoveHigh, 0) == -1 && GetLastError() )
    {
      LastError = GetLastError();
      SearchIndexerDebug::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
        (const wchar_t *)0x162,
        (unsigned int)L"[HTML] CMmStream::Close -- SetFilePointer returned %d\n",
        (const wchar_t *)LastError);
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x163,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
        v8);
    }
    if ( !SetEndOfFile(*((HANDLE *)this + 1)) )
    {
      v9 = GetLastError();
      SearchIndexerDebug::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
        (const wchar_t *)0x168,
        (unsigned int)L"[HTML] CMmStream::Close -- SetEndOfFile returned %d\n",
        (const wchar_t *)v9);
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x169,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
        v10);
    }
    a4 = DistanceToMoveHigh;
  }
  FileMappingW = CreateFileMappingW(*((HANDLE *)this + 1), 0, 4u, a4, a3, 0);
  *((_QWORD *)this + 2) = FileMappingW;
  if ( !FileMappingW )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x176,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
      v12);
  *((_DWORD *)this + 12) = DistanceToMoveHigh;
  *((_DWORD *)this + 11) = a3;
}

```

## disassembly

```asm
0x1800215b0  mov     [rsp+arg_8], rbx
0x1800215b5  mov     [rsp+DistanceToMoveHigh], r9d
0x1800215ba  push    rdi
0x1800215bb  sub     rsp, 40h
0x1800215bf  mov     rbx, rcx
0x1800215c2  mov     edi, r8d
0x1800215c5  mov     rcx, [rcx+10h]; hObject
0x1800215c9  test    rcx, rcx
0x1800215cc  jz      short loc_1800215D9
0x1800215ce  call    cs:__imp_CloseHandle
0x1800215d4  mov     r9d, [rsp+48h+DistanceToMoveHigh]
0x1800215d9  mov     eax, [rbx+2Ch]
0x1800215dc  mov     dword ptr [rsp+48h+arg_0], eax
0x1800215e0  mov     eax, [rbx+30h]
0x1800215e3  mov     dword ptr [rsp+48h+arg_0+4], eax
0x1800215e7  mov     rax, [rsp+48h+arg_0]
0x1800215ec  mov     dword ptr [rsp+48h+var_18], edi
0x1800215f0  mov     dword ptr [rsp+48h+var_18+4], r9d
0x1800215f5  cmp     [rsp+48h+var_18], rax
0x1800215fa  jge     loc_1800216A6
0x180021600  mov     rcx, [rbx+8]; hFile
0x180021604  lea     r8, [rsp+48h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x180021609  xor     r9d, r9d; dwMoveMethod
0x18002160c  mov     edx, edi; lDistanceToMove
0x18002160e  call    cs:__imp_SetFilePointer
0x180021614  cmp     eax, 0FFFFFFFFh
0x180021617  jnz     short loc_18002165B
0x180021619  call    cs:__imp_GetLastError
0x18002161f  test    eax, eax
0x180021621  jz      short loc_18002165B
0x180021623  call    cs:__imp_GetLastError
0x180021629  lea     r8, aHtmlCmmstreamC_0; "[HTML] CMmStream::Close -- SetFilePoint"...
0x180021630  mov     edx, 162h; wchar_t *
0x180021635  mov     r9d, eax; wchar_t *
0x180021638  lea     rcx, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18002163f  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x180021644  mov     rcx, [rsp+48h]; this
0x180021649  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180021650  mov     edx, 163h; void *
0x180021655  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002165b  mov     rcx, [rbx+8]; hFile
0x18002165f  call    cs:__imp_SetEndOfFile
0x180021665  test    eax, eax
0x180021667  jnz     short loc_1800216A1
0x180021669  call    cs:__imp_GetLastError
0x18002166f  lea     r8, aHtmlCmmstreamC; "[HTML] CMmStream::Close -- SetEndOfFile"...
0x180021676  mov     edx, 168h; wchar_t *
0x18002167b  mov     r9d, eax; wchar_t *
0x18002167e  lea     rcx, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180021685  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x18002168a  mov     rcx, [rsp+48h]; this
0x18002168f  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180021696  mov     edx, 169h; void *
0x18002169b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800216a1  mov     r9d, [rsp+48h+DistanceToMoveHigh]; dwMaximumSizeHigh
0x1800216a6  mov     rcx, [rbx+8]; hFile
0x1800216aa  xor     edx, edx; lpFileMappingAttributes
0x1800216ac  mov     [rsp+48h+lpName], 0; lpName
0x1800216b5  mov     [rsp+48h+dwMaximumSizeLow], edi; dwMaximumSizeLow
0x1800216b9  lea     r8d, [rdx+4]; flProtect
0x1800216bd  call    cs:__imp_CreateFileMappingW
0x1800216c3  mov     [rbx+10h], rax
0x1800216c7  test    rax, rax
0x1800216ca  jnz     short loc_1800216E3
0x1800216cc  mov     rcx, [rsp+48h]; this
0x1800216d1  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\fil"...
0x1800216d8  mov     edx, 176h; void *
0x1800216dd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800216e3  mov     eax, [rsp+48h+DistanceToMoveHigh]
0x1800216e7  mov     [rbx+30h], eax
0x1800216ea  mov     [rbx+2Ch], edi
0x1800216ed  mov     rbx, [rsp+48h+arg_8]
0x1800216f2  add     rsp, 40h
0x1800216f6  pop     rdi
0x1800216f7  retn
```
