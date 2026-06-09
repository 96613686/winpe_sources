# CHtmlIFilter::InternalConvertToSJISUsingMLang(ulong,IMultiLanguage2 *)

- ea: `0x1800121b4`
- end: `0x1800123bc`
- name: `?InternalConvertToSJISUsingMLang@CHtmlIFilter@@AEAAXKPEAUIMultiLanguage2@@@Z`
- size: `520`
- prototype: `void __fastcall(CHtmlIFilter *__hidden this, unsigned int, struct IMultiLanguage2 *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000dd68`

## callees

- `0x18000d2f0`
- `0x18000fab0`
- `0x1800121b4`
- `0x1800123c4`
- `0x180012488`
- `0x180013500`
- `0x18001f458`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012381`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800122c4`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800122c4`

## string_xrefs

- `0x180012387`: `[HTML] UnmapViewOfFile of _pTempFileBuf returned %d\n`

## pseudocode

```c
void __fastcall CHtmlIFilter::InternalConvertToSJISUsingMLang(
        CHtmlIFilter *this,
        unsigned int a2,
        struct IMultiLanguage2 *a3)
{
  char *v3; // rsi
  CMmStream *v5; // r15
  unsigned int v8; // eax
  HRESULT (__stdcall *ConvertString)(IMultiLanguage2 *, DWORD *, DWORD, DWORD, BYTE *, UINT *, BYTE *, UINT *); // rax
  const wchar_t *v10; // r9
  DWORD LastError; // eax
  const char *v12; // r9
  int v13[2]; // [rsp+20h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  unsigned int v15; // [rsp+90h] [rbp+8h]
  int v16; // [rsp+A8h] [rbp+20h] BYREF

  v3 = (char *)this + 712;
  v5 = (CHtmlIFilter *)((char *)this + 744);
  if ( (*(unsigned int (__fastcall **)(char *))(*((_QWORD *)this + 93) + 8LL))((char *)this + 744) )
    v8 = *((_DWORD *)v3 + 19);
  else
    v8 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)v3 + 11) + 48LL))(v3 + 88);
  v15 = v8;
  if ( *((_QWORD *)this + 113) )
    (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 116) + 88LL))(
      *((_QWORD *)this + 116),
      (char *)this + 904);
  (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 116) + 72LL))(
    *((_QWORD *)this + 116),
    (char *)this + 904);
  CMmStream::CreateTempFileMapping(v5, v15);
  *(_QWORD *)v13 = *((_QWORD *)this + 113);
  ConvertString = a3->lpVtbl->ConvertString;
  v16 = 0;
  if ( ((unsigned int (__fastcall *)(struct IMultiLanguage2 *, int *, _QWORD, __int64))ConvertString)(a3, &v16, a2, 932) )
  {
    SearchIndexerDebug::Error(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\htmlfilt.cxx",
      (const wchar_t *)0x50F,
      (unsigned int)L"[HTML] Conversion to S-JIS returned failed\n",
      v10);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x510,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\htmlfilt.cxx",
      (const char *)0x80004005LL,
      v13[0]);
  }
  *((_DWORD *)this + 196) = v15;
  CMmStreamConsecBuf::Rewind((CHtmlIFilter *)((char *)this + 904));
  if ( !UnmapViewOfFile(*((LPCVOID *)this + 97)) )
  {
    LastError = GetLastError();
    SearchIndexerDebug::Error(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
      (const wchar_t *)0x25E,
      (unsigned int)L"[HTML] UnmapViewOfFile of _pTempFileBuf returned %d\n",
      (const wchar_t *)LastError);
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x25F,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\mmstrm.cxx",
      v12);
  }
  *((_QWORD *)this + 97) = 0;
  *(_OWORD *)((char *)this + 616) = 0;
  *(_OWORD *)((char *)this + 632) = 0;
  *((_QWORD *)this + 81) = 0;
  *((_WORD *)this + 328) = 0;
  *((_DWORD *)this + 175) = 0;
  *((_QWORD *)this + 88) = (char *)this + 658;
  CMemoryMappedInputStream::InitWithTempFile((CMemoryMappedInputStream *)v3);
}

```

## disassembly

```asm
0x1800121b4  push    rbx
0x1800121b6  push    rbp
0x1800121b7  push    rsi
0x1800121b8  push    rdi
0x1800121b9  push    r12
0x1800121bb  push    r14
0x1800121bd  push    r15
0x1800121bf  sub     rsp, 50h
0x1800121c3  lea     rsi, [rcx+2C8h]
0x1800121ca  mov     rbx, rcx
0x1800121cd  lea     r15, [rsi+20h]
0x1800121d1  mov     rbp, r8
0x1800121d4  mov     rax, [r15]
0x1800121d7  mov     rcx, r15
0x1800121da  mov     r12d, edx
0x1800121dd  mov     rax, [rax+8]
0x1800121e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121e6  test    eax, eax
0x1800121e8  jnz     loc_180012329
0x1800121ee  lea     rcx, [rsi+58h]
0x1800121f2  mov     rax, [rcx]
0x1800121f5  mov     rax, [rax+30h]
0x1800121f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121fe  lea     rdi, [rbx+388h]
0x180012205  mov     [rsp+88h+arg_0], eax
0x18001220c  cmp     qword ptr [rdi], 0
0x180012210  jnz     loc_180012331
0x180012216  mov     rcx, [rdi+18h]
0x18001221a  mov     rdx, rdi
0x18001221d  mov     rax, [rcx]
0x180012220  mov     rax, [rax+48h]
0x180012224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012229  mov     edx, [rsp+88h+arg_0]; unsigned int
0x180012230  mov     rcx, r15; this
0x180012233  call    ?CreateTempFileMapping@CMmStream@@QEAAXK@Z; CMmStream::CreateTempFileMapping(ulong)
0x180012238  mov     eax, [rsp+88h+arg_0]
0x18001223f  lea     rcx, [rsp+88h+arg_10]
0x180012247  mov     [rsp+88h+var_50], rcx
0x18001224c  lea     rdx, [rsp+88h+arg_18]
0x180012254  mov     rcx, [rbx+308h]
0x18001225b  mov     r9d, 3A4h
0x180012261  mov     [rsp+88h+var_58], rcx
0x180012266  mov     r8d, r12d
0x180012269  mov     [rsp+88h+arg_10], eax
0x180012270  lea     rcx, [rsp+88h+arg_0]
0x180012278  mov     rax, [rbp+0]
0x18001227c  mov     [rsp+88h+var_60], rcx
0x180012281  mov     rcx, [rdi]
0x180012284  mov     qword ptr [rsp+88h+var_68], rcx; int
0x180012289  mov     rcx, rbp
0x18001228c  mov     rax, [rax+48h]
0x180012290  mov     [rsp+88h+arg_18], 0
0x18001229b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122a0  test    eax, eax
0x1800122a2  jnz     loc_180012349
0x1800122a8  mov     eax, [rsp+88h+arg_10]
0x1800122af  mov     rcx, rdi; this
0x1800122b2  mov     [rbx+310h], eax
0x1800122b8  call    ?Rewind@CMmStreamConsecBuf@@QEAAXXZ; CMmStreamConsecBuf::Rewind(void)
0x1800122bd  mov     rcx, [rbx+308h]; lpBaseAddress
0x1800122c4  call    cs:__imp_UnmapViewOfFile
0x1800122ca  test    eax, eax
0x1800122cc  jz      loc_180012381
0x1800122d2  mov     qword ptr [rbx+308h], 0
0x1800122dd  xor     eax, eax
0x1800122df  xorps   xmm0, xmm0
0x1800122e2  mov     rcx, rsi; this
0x1800122e5  movups  xmmword ptr [rbx+268h], xmm0
0x1800122ec  movups  xmmword ptr [rbx+278h], xmm0
0x1800122f3  mov     [rbx+288h], rax
0x1800122fa  mov     [rbx+290h], ax
0x180012301  mov     [rbx+2BCh], eax
0x180012307  lea     rax, [rbx+292h]
0x18001230e  mov     [rbx+2C0h], rax
0x180012315  call    ?InitWithTempFile@CMemoryMappedInputStream@@QEAAXXZ; CMemoryMappedInputStream::InitWithTempFile(void)
0x18001231a  add     rsp, 50h
0x18001231e  pop     r15
0x180012320  pop     r14
0x180012322  pop     r12
0x180012324  pop     rdi
0x180012325  pop     rsi
0x180012326  pop     rbp
0x180012327  pop     rbx
0x180012328  retn
0x180012329  mov     eax, [rsi+4Ch]
0x18001232c  jmp     loc_1800121FE
0x180012331  mov     rcx, [rdi+18h]
0x180012335  mov     rdx, rdi
0x180012338  mov     rax, [rcx]
0x18001233b  mov     rax, [rax+58h]
0x18001233f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012344  jmp     loc_180012216
0x180012349  lea     r8, aHtmlConversion; "[HTML] Conversion to S-JIS returned fai"...
0x180012350  mov     edx, 50Fh; wchar_t *
0x180012355  lea     rcx, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18001235c  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x180012361  mov     rcx, [rsp+88h]; this
0x180012369  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180012370  mov     r9d, 80004005h; char *
0x180012376  mov     edx, 510h; void *
0x18001237b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012381  call    cs:__imp_GetLastError
0x180012387  lea     r8, aHtmlUnmapviewo_0; "[HTML] UnmapViewOfFile of _pTempFileBuf"...
0x18001238e  mov     edx, 25Eh; wchar_t *
0x180012393  mov     r9d, eax; wchar_t *
0x180012396  lea     rcx, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18001239d  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800123a2  mov     rcx, [rsp+88h]; this
0x1800123aa  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\fil"...
0x1800123b1  mov     edx, 25Fh; void *
0x1800123b6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
