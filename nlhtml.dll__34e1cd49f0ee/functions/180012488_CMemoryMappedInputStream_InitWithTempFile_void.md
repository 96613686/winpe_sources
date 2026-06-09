# CMemoryMappedInputStream::InitWithTempFile(void)

- ea: `0x180012488`
- end: `0x18001257e`
- name: `?InitWithTempFile@CMemoryMappedInputStream@@QEAAXXZ`
- size: `246`
- prototype: `void __fastcall(CMemoryMappedInputStream *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800121b4`

## callees

- `0x18000d2f0`
- `0x18000e4e8`
- `0x18000fab0`
- `0x180012488`
- `0x180012584`
- `0x180013500`
- `0x180025010`

## string_xrefs

- `0x18001253f`: `[HTML] Throwing FILTER_E_ACCESS in CMemoryMappedInputStream::InitWithTempFile\n`

## pseudocode

```c
void __fastcall CMemoryMappedInputStream::InitWithTempFile(CMemoryMappedInputStream *this)
{
  CMmStream *v1; // rdi
  __int64 v2; // rax
  const wchar_t *v4; // r9
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = 0;
  *((_WORD *)this + 12) = 0;
  v1 = (CMemoryMappedInputStream *)((char *)this + 32);
  v2 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 932;
  *((_DWORD *)this + 7) = 1;
  if ( !(*(unsigned int (__fastcall **)(char *))(v2 + 8))((char *)this + 32)
    && !(*(unsigned int (__fastcall **)(char *))(*((_QWORD *)this + 11) + 8LL))((char *)this + 88) )
  {
    SearchIndexerDebug::Error(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\inpstrm.cxx",
      (const wchar_t *)0x196,
      (unsigned int)L"[HTML] Throwing FILTER_E_ACCESS in CMemoryMappedInputStream::InitWithTempFile\n",
      v4);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x197,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\inpstrm.cxx",
      (const char *)0x80041703LL,
      v5);
  }
  CMmStreamConsecBuf::Rewind((CMemoryMappedInputStream *)((char *)this + 192));
  CMmStream::InitWithTempFile(v1);
  *((_QWORD *)this + 27) = v1;
  *((_QWORD *)this + 28) = 0;
  *((_DWORD *)this + 50) = 0;
  if ( !(*(unsigned int (__fastcall **)(CMmStream *))(*(_QWORD *)v1 + 32LL))(v1) )
    CMmStreamConsecBuf::Map((CMemoryMappedInputStream *)((char *)this + 192));
}

```

## disassembly

```asm
0x180012488  mov     [rsp+arg_0], rbx
0x18001248d  mov     [rsp+arg_8], rsi
0x180012492  push    rdi; int
0x180012493  sub     rsp, 20h
0x180012497  xor     eax, eax
0x180012499  mov     qword ptr [rcx], 0
0x1800124a0  mov     [rcx+18h], ax
0x1800124a4  lea     rdi, [rcx+20h]
0x1800124a8  mov     rax, [rdi]
0x1800124ab  mov     rbx, rcx
0x1800124ae  mov     qword ptr [rcx+8], 0
0x1800124b6  mov     qword ptr [rcx+10h], 3A4h
0x1800124be  mov     dword ptr [rcx+1Ch], 1
0x1800124c5  mov     rcx, rdi
0x1800124c8  mov     rax, [rax+8]
0x1800124cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124d1  test    eax, eax
0x1800124d3  jz      short loc_18001252B
0x1800124d5  lea     rsi, [rbx+0C0h]
0x1800124dc  mov     rcx, rsi; this
0x1800124df  call    ?Rewind@CMmStreamConsecBuf@@QEAAXXZ; CMmStreamConsecBuf::Rewind(void)
0x1800124e4  mov     rcx, rdi; this
0x1800124e7  call    ?InitWithTempFile@CMmStream@@QEAAXXZ; CMmStream::InitWithTempFile(void)
0x1800124ec  mov     [rbx+0D8h], rdi
0x1800124f3  mov     rcx, rdi
0x1800124f6  mov     qword ptr [rbx+0E0h], 0
0x180012501  mov     dword ptr [rbx+0C8h], 0
0x18001250b  mov     rax, [rdi]
0x18001250e  mov     rax, [rax+20h]
0x180012512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012517  test    eax, eax
0x180012519  jz      short loc_180012574
0x18001251b  mov     rbx, [rsp+28h+arg_0]
0x180012520  mov     rsi, [rsp+28h+arg_8]
0x180012525  add     rsp, 20h
0x180012529  pop     rdi
0x18001252a  retn
0x18001252b  lea     rcx, [rbx+58h]
0x18001252f  mov     rax, [rcx]
0x180012532  mov     rax, [rax+8]
0x180012536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001253b  test    eax, eax
0x18001253d  jnz     short loc_1800124D5
0x18001253f  lea     r8, aHtmlThrowingFi; "[HTML] Throwing FILTER_E_ACCESS in CMem"...
0x180012546  mov     edx, 196h; wchar_t *
0x18001254b  lea     rcx, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180012552  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x180012557  mov     rcx, [rsp+28h]; this
0x18001255c  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180012563  mov     r9d, 80041703h; char *
0x180012569  mov     edx, 197h; void *
0x18001256e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012574  mov     rcx, rsi; this
0x180012577  call    ?Map@CMmStreamConsecBuf@@QEAAXK@Z; CMmStreamConsecBuf::Map(ulong)
0x18001257c  jmp     short loc_18001251B
```
