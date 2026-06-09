# make_unique_pku2u<_PAC_TOKEN_SECURITY_ATTRIBUTE [0]>(unsigned __int64)

- ea: `0x180038914`
- end: `0x180038997`
- name: `??$make_unique_pku2u@$$BY0A@U_PAC_TOKEN_SECURITY_ATTRIBUTE@@@@YA?AV?$unique_ptr@$$BY0A@U_PAC_TOKEN_SECURITY_ATTRIBUTE@@U?$function_deleter@P6AXPEAX@Z$1?Pku2uFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003a688`

## callees

- `0x180018870`
- `0x18002ad2c`
- `0x180038914`

## string_xrefs

- `0x180038935`: `onecore\ds\security\protocols\pku2u\utils.hxx`

## pseudocode

```c
char **__fastcall make_unique_pku2u<_PAC_TOKEN_SECURITY_ATTRIBUTE [0]>(
        char **a1,
        unsigned __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // rdi
  char *v6; // rax
  char *v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( a2 > 0x666666666666666LL )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\utils.hxx",
      a4);
  v5 = 40 * a2;
  v6 = (char *)basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, 40 * a2);
  *a1 = v6;
  if ( v6 )
  {
    v7 = &v6[v5];
    while ( v6 != v7 )
    {
      *(_OWORD *)v6 = 0;
      *((_OWORD *)v6 + 1) = 0;
      *((_QWORD *)v6 + 4) = 0;
      v6 += 40;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180038914  mov     [rsp+arg_0], rbx
0x180038919  push    rdi
0x18003891a  sub     rsp, 30h
0x18003891e  mov     rax, 666666666666666h
0x180038928  mov     rbx, rcx
0x18003892b  cmp     rdx, rax
0x18003892e  jbe     short loc_180038947
0x180038930  mov     rcx, [rsp+38h]; this
0x180038935  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\protocols\\pku2u"...
0x18003893c  mov     edx, 67h ; 'g'; void *
0x180038941  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180038947  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x18003894e  lea     rax, [rdx+rdx*4]
0x180038952  lea     rdi, ds:0[rax*8]
0x18003895a  mov     rdx, rdi; unsigned __int64
0x18003895d  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x180038962  mov     [rbx], rax
0x180038965  test    rax, rax
0x180038968  jz      short loc_180038989
0x18003896a  lea     rcx, [rdi+rax]
0x18003896e  jmp     short loc_180038984
0x180038970  xorps   xmm0, xmm0
0x180038973  xor     edx, edx
0x180038975  movups  xmmword ptr [rax], xmm0
0x180038978  movups  xmmword ptr [rax+10h], xmm0
0x18003897c  mov     [rax+20h], rdx
0x180038980  add     rax, 28h ; '('
0x180038984  cmp     rax, rcx
0x180038987  jnz     short loc_180038970
0x180038989  mov     rax, rbx
0x18003898c  mov     rbx, [rsp+38h+arg_0]
0x180038991  add     rsp, 30h
0x180038995  pop     rdi
0x180038996  retn
```
