# CMemoryMappedInputStream::InternalInitNoCodePage(void)

- ea: `0x18000d6fc`
- end: `0x18000d7e3`
- name: `?InternalInitNoCodePage@CMemoryMappedInputStream@@AEAAXXZ`
- size: `231`
- prototype: `void __fastcall(CMemoryMappedInputStream *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000dd68`
- `0x180013610`

## callees

- `0x18000d2f0`
- `0x18000d6fc`
- `0x18000e4e8`
- `0x18000fab0`
- `0x180013500`
- `0x180025010`

## string_xrefs

- `0x18000d7ae`: `[HTML] Throwing FILTER_E_ACCESS in CMemoryMappedInputStream::InternalInitNoCodePage because _mmStream.Ok() is false`

## pseudocode

```c
void __fastcall CMemoryMappedInputStream::InternalInitNoCodePage(CMemoryMappedInputStream *this)
{
  char *v1; // rdi
  __int64 v2; // rax
  const wchar_t *v4; // r9
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = 0;
  *((_WORD *)this + 12) = 0;
  v1 = (char *)this + 32;
  v2 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 5) = 0;
  if ( !(*(unsigned int (__fastcall **)(char *))(v2 + 8))((char *)this + 32) )
  {
    v1 = (char *)this + 88;
    if ( !(*(unsigned int (__fastcall **)(char *))(*((_QWORD *)this + 11) + 8LL))((char *)this + 88) )
    {
      SearchIndexerDebug::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\inpstrm.cxx",
        (const wchar_t *)0x3BD,
        (unsigned int)L"[HTML] Throwing FILTER_E_ACCESS in CMemoryMappedInputStream::InternalInitNoCodePage because _mmStr"
                       "eam.Ok() is false",
        v4);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3BE,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\inpstrm.cxx",
        (const char *)0x80041703LL,
        v5);
    }
  }
  CMmStreamConsecBuf::Rewind((CMemoryMappedInputStream *)((char *)this + 192));
  *((_QWORD *)this + 27) = v1;
  *((_QWORD *)this + 28) = 0;
  *((_DWORD *)this + 50) = 0;
  if ( !(*(unsigned int (__fastcall **)(char *))(*(_QWORD *)v1 + 32LL))(v1) )
    CMmStreamConsecBuf::Map((CMemoryMappedInputStream *)((char *)this + 192));
}

```

## disassembly

```asm
0x18000d6fc  mov     [rsp+arg_0], rbx
0x18000d701  mov     [rsp+arg_8], rsi
0x18000d706  push    rdi; int
0x18000d707  sub     rsp, 20h
0x18000d70b  xor     eax, eax
0x18000d70d  mov     qword ptr [rcx], 0
0x18000d714  mov     [rcx+18h], ax
0x18000d718  lea     rdi, [rcx+20h]
0x18000d71c  mov     rax, [rdi]
0x18000d71f  mov     rbx, rcx
0x18000d722  mov     qword ptr [rcx+8], 0
0x18000d72a  mov     dword ptr [rcx+14h], 0
0x18000d731  mov     rcx, rdi
0x18000d734  mov     rax, [rax+8]
0x18000d738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d73d  test    eax, eax
0x18000d73f  jnz     short loc_18000D758
0x18000d741  lea     rdi, [rbx+58h]
0x18000d745  mov     rax, [rdi]
0x18000d748  mov     rcx, rdi
0x18000d74b  mov     rax, [rax+8]
0x18000d74f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d754  test    eax, eax
0x18000d756  jz      short loc_18000D7AE
0x18000d758  lea     rsi, [rbx+0C0h]
0x18000d75f  mov     rcx, rsi; this
0x18000d762  call    ?Rewind@CMmStreamConsecBuf@@QEAAXXZ; CMmStreamConsecBuf::Rewind(void)
0x18000d767  mov     [rbx+0D8h], rdi
0x18000d76e  mov     rcx, rdi
0x18000d771  mov     qword ptr [rbx+0E0h], 0
0x18000d77c  mov     dword ptr [rbx+0C8h], 0
0x18000d786  mov     rax, [rdi]
0x18000d789  mov     rax, [rax+20h]
0x18000d78d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d792  test    eax, eax
0x18000d794  jnz     short loc_18000D79E
0x18000d796  mov     rcx, rsi; this
0x18000d799  call    ?Map@CMmStreamConsecBuf@@QEAAXK@Z; CMmStreamConsecBuf::Map(ulong)
0x18000d79e  mov     rbx, [rsp+28h+arg_0]
0x18000d7a3  mov     rsi, [rsp+28h+arg_8]
0x18000d7a8  add     rsp, 20h
0x18000d7ac  pop     rdi
0x18000d7ad  retn
0x18000d7ae  lea     r8, aHtmlThrowingFi_0; "[HTML] Throwing FILTER_E_ACCESS in CMem"...
0x18000d7b5  mov     edx, 3BDh; wchar_t *
0x18000d7ba  lea     rcx, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000d7c1  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x18000d7c6  mov     rcx, [rsp+28h]; this
0x18000d7cb  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000d7d2  mov     r9d, 80041703h; char *
0x18000d7d8  mov     edx, 3BEh; void *
0x18000d7dd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
