# CMemoryMappedInputStream::Init(wchar_t const *)

- ea: `0x18000f98c`
- end: `0x18000faaa`
- name: `?Init@CMemoryMappedInputStream@@QEAAXPEB_W@Z`
- size: `286`
- prototype: `void __fastcall(CMemoryMappedInputStream *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000dd68`

## callees

- `0x18000d2f0`
- `0x18000e4e8`
- `0x18000f98c`
- `0x18000fab0`
- `0x1800100ec`
- `0x180013500`
- `0x180025010`

## string_xrefs

- `0x18000fa75`: `[HTML] Throwing FILTER_E_ACCESS in CMemoryMappedInputStream::Init\n`

## pseudocode

```c
void __fastcall CMemoryMappedInputStream::Init(CMemoryMappedInputStream *this, const wchar_t *a2)
{
  CMmStream *v2; // rbx
  __int64 v3; // rax
  CMmStreamConsecBuf *v4; // rdi
  const wchar_t *v7; // r9
  int v8; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_QWORD *)this = 0;
  *((_WORD *)this + 12) = 0;
  v2 = (CMemoryMappedInputStream *)((char *)this + 32);
  v3 = *((_QWORD *)this + 4);
  v4 = (CMemoryMappedInputStream *)((char *)this + 192);
  *((_DWORD *)this + 2) = 0;
  *((_DWORD *)this + 3) = 1;
  *((_DWORD *)this + 5) = 0;
  if ( (*(unsigned int (__fastcall **)(char *))(v3 + 8))((char *)this + 32) )
  {
    CMmStreamConsecBuf::Rewind(v4);
    (*(void (__fastcall **)(CMmStream *))(*(_QWORD *)v2 + 16LL))(v2);
  }
  if ( (*(unsigned int (__fastcall **)(char *))(*((_QWORD *)this + 11) + 8LL))((char *)this + 88) )
  {
    CMmStreamConsecBuf::Rewind(v4);
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 11) + 16LL))((char *)this + 88);
  }
  CMmStream::Open(v2, a2);
  if ( !(*(unsigned int (__fastcall **)(CMmStream *))(*(_QWORD *)v2 + 8LL))(v2) )
  {
    SearchIndexerDebug::Error(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\inpstrm.cxx",
      (const wchar_t *)0x122,
      (unsigned int)L"[HTML] Throwing FILTER_E_ACCESS in CMemoryMappedInputStream::Init\n",
      v7);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x123,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\inpstrm.cxx",
      (const char *)0x80041703LL,
      v8);
  }
  *((_QWORD *)v4 + 3) = v2;
  *((_QWORD *)v4 + 4) = 0;
  *((_DWORD *)v4 + 2) = 0;
  if ( !(*(unsigned int (__fastcall **)(CMmStream *))(*(_QWORD *)v2 + 32LL))(v2) )
    CMmStreamConsecBuf::Map(v4);
}

```

## disassembly

```asm
0x18000f98c  push    rbx
0x18000f98e  push    rbp
0x18000f98f  push    rsi
0x18000f990  push    rdi
0x18000f991  sub     rsp, 38h
0x18000f995  xor     eax, eax
0x18000f997  mov     qword ptr [rcx], 0
0x18000f99e  mov     [rcx+18h], ax
0x18000f9a2  lea     rbx, [rcx+20h]
0x18000f9a6  mov     rax, [rbx]
0x18000f9a9  lea     rdi, [rcx+0C0h]
0x18000f9b0  mov     rsi, rcx
0x18000f9b3  mov     dword ptr [rcx+8], 0
0x18000f9ba  mov     dword ptr [rcx+0Ch], 1
0x18000f9c1  mov     rbp, rdx
0x18000f9c4  mov     dword ptr [rcx+14h], 0
0x18000f9cb  mov     rcx, rbx
0x18000f9ce  mov     rax, [rax+8]
0x18000f9d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9d7  test    eax, eax
0x18000f9d9  jz      short loc_18000F9F2
0x18000f9db  mov     rcx, rdi; this
0x18000f9de  call    ?Rewind@CMmStreamConsecBuf@@QEAAXXZ; CMmStreamConsecBuf::Rewind(void)
0x18000f9e3  mov     rax, [rbx]
0x18000f9e6  mov     rcx, rbx
0x18000f9e9  mov     rax, [rax+10h]
0x18000f9ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9f2  mov     rax, [rsi+58h]
0x18000f9f6  lea     rcx, [rsi+58h]
0x18000f9fa  mov     rax, [rax+8]
0x18000f9fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa03  test    eax, eax
0x18000fa05  jz      short loc_18000FA20
0x18000fa07  mov     rcx, rdi; this
0x18000fa0a  call    ?Rewind@CMmStreamConsecBuf@@QEAAXXZ; CMmStreamConsecBuf::Rewind(void)
0x18000fa0f  mov     rax, [rsi+58h]
0x18000fa13  lea     rcx, [rsi+58h]
0x18000fa17  mov     rax, [rax+10h]
0x18000fa1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa20  mov     rdx, rbp; wchar_t *
0x18000fa23  mov     rcx, rbx; this
0x18000fa26  call    ?Open@CMmStream@@QEAAXPEB_WKKKK@Z; CMmStream::Open(wchar_t const *,ulong,ulong,ulong,ulong)
0x18000fa2b  mov     rax, [rbx]
0x18000fa2e  mov     rcx, rbx
0x18000fa31  mov     rax, [rax+8]
0x18000fa35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa3a  test    eax, eax
0x18000fa3c  jz      short loc_18000FA75
0x18000fa3e  mov     [rdi+18h], rbx
0x18000fa42  mov     rcx, rbx
0x18000fa45  mov     qword ptr [rdi+20h], 0
0x18000fa4d  mov     dword ptr [rdi+8], 0
0x18000fa54  mov     rax, [rbx]
0x18000fa57  mov     rax, [rax+20h]
0x18000fa5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa60  test    eax, eax
0x18000fa62  jnz     short loc_18000FA6C
0x18000fa64  mov     rcx, rdi; this
0x18000fa67  call    ?Map@CMmStreamConsecBuf@@QEAAXK@Z; CMmStreamConsecBuf::Map(ulong)
0x18000fa6c  add     rsp, 38h
0x18000fa70  pop     rdi
0x18000fa71  pop     rsi
0x18000fa72  pop     rbp
0x18000fa73  pop     rbx
0x18000fa74  retn
0x18000fa75  lea     r8, aHtmlThrowingFi_1; "[HTML] Throwing FILTER_E_ACCESS in CMem"...
0x18000fa7c  mov     edx, 122h; wchar_t *
0x18000fa81  lea     rcx, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000fa88  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x18000fa8d  mov     rcx, [rsp+58h]; this
0x18000fa92  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000fa99  mov     r9d, 80041703h; char *
0x18000fa9f  mov     edx, 123h; void *
0x18000faa4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
