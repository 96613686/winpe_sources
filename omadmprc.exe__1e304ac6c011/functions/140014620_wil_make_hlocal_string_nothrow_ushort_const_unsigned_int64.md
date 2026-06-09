# wil::make_hlocal_string_nothrow(ushort const *,unsigned __int64)

- ea: `0x140014620`
- end: `0x1400146c0`
- name: `?make_hlocal_string_nothrow@wil@@YA@PEBG_K@Z`
- size: `160`
- prototype: `_QWORD(wil *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400128d4`
- `0x140013350`

## callees

- `0x140009e3c`
- `0x140014620`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140014684`
- `msvcrt!memcpy_s` at `0x140014684`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140014663`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140014663`

## string_xrefs

- `0x1400146ae`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
wil *__fastcall wil::make_hlocal_string_nothrow(wil *this, const unsigned __int16 *a2, __int64 a3, const char *a4)
{
  __int64 v6; // rcx
  const unsigned __int16 *v7; // rax
  rsize_t v8; // r14
  char *v9; // rax
  char *v10; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v6 = 0x7FFFFFFF;
  v7 = a2;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v6;
  }
  while ( v6 );
  v8 = 2 * (v7 - a2);
  v9 = (char *)LocalAlloc(0, v8 + 2);
  v10 = v9;
  if ( v9 )
  {
    memcpy_s(v9, v8 + 2, a2, v8);
    *(_WORD *)&v10[v8] = 0;
  }
  *(_QWORD *)this = v10;
  return this;
}

```

## disassembly

```asm
0x140014620  push    rbx
0x140014622  push    rbp
0x140014623  push    rsi
0x140014624  push    rdi
0x140014625  push    r14
0x140014627  push    r15
0x140014629  sub     rsp, 28h
0x14001462d  xor     r15d, r15d
0x140014630  mov     rbx, rdx
0x140014633  mov     rsi, rcx
0x140014636  test    rdx, rdx
0x140014639  jz      short loc_1400146A9
0x14001463b  mov     ecx, 7FFFFFFFh
0x140014640  mov     rax, rdx
0x140014643  cmp     [rax], r15w
0x140014647  jz      short loc_140014653
0x140014649  add     rax, 2
0x14001464d  sub     rcx, 1
0x140014651  jnz     short loc_140014643
0x140014653  sub     rax, rbx
0x140014656  xor     ecx, ecx; uFlags
0x140014658  sar     rax, 1
0x14001465b  lea     r14, [rax+rax]
0x14001465f  lea     rdx, [r14+2]; uBytes
0x140014663  call    cs:__imp_LocalAlloc
0x14001466a  nop     dword ptr [rax+rax+00h]
0x14001466f  mov     rdi, rax
0x140014672  test    rax, rax
0x140014675  jz      short loc_140014695
0x140014677  mov     r9, r14; SourceSize
0x14001467a  lea     rdx, [r14+2]; DestinationSize
0x14001467e  mov     r8, rbx; Source
0x140014681  mov     rcx, rax; Destination
0x140014684  call    cs:__imp_memcpy_s
0x14001468b  nop     dword ptr [rax+rax+00h]
0x140014690  mov     [r14+rdi], r15w
0x140014695  mov     [rsi], rdi
0x140014698  mov     rax, rsi
0x14001469b  add     rsp, 28h
0x14001469f  pop     r15
0x1400146a1  pop     r14
0x1400146a3  pop     rdi
0x1400146a4  pop     rsi
0x1400146a5  pop     rbp
0x1400146a6  pop     rbx
0x1400146a7  retn
0x1400146a9  mov     rcx, [rsp+58h]; this
0x1400146ae  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400146b5  mov     edx, 0F89h; void *
0x1400146ba  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
