# CMemoryMappedInputStream::Init(IStream *)

- ea: `0x18000e344`
- end: `0x18000e474`
- name: `?Init@CMemoryMappedInputStream@@QEAAXPEAUIStream@@@Z`
- size: `304`
- prototype: `void __fastcall(CMemoryMappedInputStream *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000dd68`

## callees

- `0x18000d2f0`
- `0x18000e344`
- `0x18000e47c`
- `0x18000e4e8`
- `0x18000fab0`
- `0x180013500`
- `0x180025010`

## string_xrefs

- `0x18000e407`: `[HTML] Throwing FILTER_E_ACCESS in CMemoryMappedInputStream::Init (stream)\n`

## pseudocode

```c
void __fastcall CMemoryMappedInputStream::Init(CMemoryMappedInputStream *this, struct IStream *a2)
{
  char *v2; // rsi
  __int64 v3; // rax
  CMmStreamConsecBuf *v4; // rdi
  CMmIStream *v7; // rbx
  const wchar_t *v8; // r9
  unsigned int v9; // edx
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_QWORD *)this = 0;
  *((_WORD *)this + 12) = 0;
  v2 = (char *)this + 32;
  v3 = *((_QWORD *)this + 4);
  v4 = (CMemoryMappedInputStream *)((char *)this + 192);
  *((_DWORD *)this + 2) = 0;
  *((_DWORD *)this + 3) = 1;
  *((_DWORD *)this + 5) = 0;
  if ( (*(unsigned int (__fastcall **)(char *))(v3 + 8))((char *)this + 32) )
  {
    CMmStreamConsecBuf::Rewind(v4);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
  }
  v7 = (CMemoryMappedInputStream *)((char *)this + 88);
  if ( (*(unsigned int (__fastcall **)(CMmIStream *))(*(_QWORD *)v7 + 8LL))(v7) )
  {
    CMmStreamConsecBuf::Rewind(v4);
    (*(void (__fastcall **)(CMmIStream *))(*(_QWORD *)v7 + 16LL))(v7);
  }
  CMmIStream::Open(v7, a2);
  if ( !(*(unsigned int (__fastcall **)(CMmIStream *))(*(_QWORD *)v7 + 8LL))(v7) )
  {
    SearchIndexerDebug::Error(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\inpstrm.cxx",
      (const wchar_t *)0x157,
      (unsigned int)L"[HTML] Throwing FILTER_E_ACCESS in CMemoryMappedInputStream::Init (stream)\n",
      v8);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x158,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\inpstrm.cxx",
      (const char *)0x80041703LL,
      v10);
  }
  *((_QWORD *)v4 + 3) = v7;
  *((_QWORD *)v4 + 4) = 0;
  *((_DWORD *)v4 + 2) = 0;
  if ( !(*(unsigned int (__fastcall **)(CMmIStream *))(*(_QWORD *)v7 + 32LL))(v7) )
    CMmStreamConsecBuf::Map(v4, v9);
}

```

## disassembly

```asm
0x18000e344  push    rbx
0x18000e346  push    rbp
0x18000e347  push    rsi
0x18000e348  push    rdi
0x18000e349  sub     rsp, 28h
0x18000e34d  xor     eax, eax
0x18000e34f  mov     qword ptr [rcx], 0
0x18000e356  mov     [rcx+18h], ax
0x18000e35a  lea     rsi, [rcx+20h]
0x18000e35e  mov     rax, [rsi]
0x18000e361  lea     rdi, [rcx+0C0h]
0x18000e368  mov     rbx, rcx
0x18000e36b  mov     dword ptr [rcx+8], 0
0x18000e372  mov     dword ptr [rcx+0Ch], 1
0x18000e379  mov     rbp, rdx
0x18000e37c  mov     dword ptr [rcx+14h], 0
0x18000e383  mov     rcx, rsi
0x18000e386  mov     rax, [rax+8]
0x18000e38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e38f  test    eax, eax
0x18000e391  jnz     loc_18000E43C
0x18000e397  add     rbx, 58h ; 'X'
0x18000e39b  mov     rcx, rbx
0x18000e39e  mov     rax, [rbx]
0x18000e3a1  mov     rax, [rax+8]
0x18000e3a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3aa  test    eax, eax
0x18000e3ac  jnz     loc_18000E458
0x18000e3b2  mov     rdx, rbp; struct IStream *
0x18000e3b5  mov     rcx, rbx; this
0x18000e3b8  call    ?Open@CMmIStream@@QEAAXPEAUIStream@@@Z; CMmIStream::Open(IStream *)
0x18000e3bd  mov     rax, [rbx]
0x18000e3c0  mov     rcx, rbx
0x18000e3c3  mov     rax, [rax+8]
0x18000e3c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3cc  test    eax, eax
0x18000e3ce  jz      short loc_18000E407
0x18000e3d0  mov     [rdi+18h], rbx
0x18000e3d4  mov     rcx, rbx
0x18000e3d7  mov     qword ptr [rdi+20h], 0
0x18000e3df  mov     dword ptr [rdi+8], 0
0x18000e3e6  mov     rax, [rbx]
0x18000e3e9  mov     rax, [rax+20h]
0x18000e3ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3f2  test    eax, eax
0x18000e3f4  jnz     short loc_18000E3FE
0x18000e3f6  mov     rcx, rdi; this
0x18000e3f9  call    ?Map@CMmStreamConsecBuf@@QEAAXK@Z; CMmStreamConsecBuf::Map(ulong)
0x18000e3fe  add     rsp, 28h
0x18000e402  pop     rdi
0x18000e403  pop     rsi
0x18000e404  pop     rbp
0x18000e405  pop     rbx
0x18000e406  retn
0x18000e407  lea     r8, aHtmlThrowingFi_2; "[HTML] Throwing FILTER_E_ACCESS in CMem"...
0x18000e40e  mov     edx, 157h; wchar_t *
0x18000e413  lea     rcx, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000e41a  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x18000e41f  mov     rcx, [rsp+48h]; this
0x18000e424  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000e42b  mov     r9d, 80041703h; char *
0x18000e431  mov     edx, 158h; void *
0x18000e436  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e43c  mov     rcx, rdi; this
0x18000e43f  call    ?Rewind@CMmStreamConsecBuf@@QEAAXXZ; CMmStreamConsecBuf::Rewind(void)
0x18000e444  mov     rax, [rsi]
0x18000e447  mov     rcx, rsi
0x18000e44a  mov     rax, [rax+10h]
0x18000e44e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e453  jmp     loc_18000E397
0x18000e458  mov     rcx, rdi; this
0x18000e45b  call    ?Rewind@CMmStreamConsecBuf@@QEAAXXZ; CMmStreamConsecBuf::Rewind(void)
0x18000e460  mov     rax, [rbx]
0x18000e463  mov     rcx, rbx
0x18000e466  mov     rax, [rax+10h]
0x18000e46a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e46f  jmp     loc_18000E3B2
```
