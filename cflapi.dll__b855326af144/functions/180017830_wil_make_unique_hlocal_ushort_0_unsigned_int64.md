# wil::make_unique_hlocal<ushort [0]>(unsigned __int64)

- ea: `0x180017830`
- end: `0x1800178c7`
- name: `??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001332c`

## callees

- `0x18000fbdc`
- `0x18000fc00`
- `0x180017830`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017867`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017867`

## string_xrefs

- `0x1800178b5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall wil::make_unique_hlocal<unsigned short [0]>(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // rdi
  _WORD *v6; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  _WORD *v9; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( a2 > 0x7FFFFFFFFFFFFFFFLL )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x12CE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v5 = a2;
  v6 = LocalAlloc(0, 2 * a2);
  *a1 = v6;
  if ( v6 )
  {
    v9 = &v6[v5];
    while ( v6 != v9 )
      *v6++ = 0;
  }
  if ( !*a1 )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0x1321, v7, v8);
  return a1;
}

```

## disassembly

```asm
0x180017830  mov     [rsp+arg_8], rbx
0x180017835  mov     [rsp+arg_0], rcx
0x18001783a  push    rdi
0x18001783b  sub     rsp, 30h
0x18001783f  mov     rbx, rcx
0x180017842  mov     [rsp+38h+var_18], 0
0x18001784a  mov     rcx, [rsp+38h]; this
0x18001784f  mov     rax, 7FFFFFFFFFFFFFFFh
0x180017859  cmp     rdx, rax
0x18001785c  ja      short loc_1800178B5
0x18001785e  lea     rdi, [rdx+rdx]
0x180017862  mov     rdx, rdi; uBytes
0x180017865  xor     ecx, ecx; uFlags
0x180017867  call    cs:__imp_LocalAlloc
0x18001786d  mov     [rbx], rax
0x180017870  test    rax, rax
0x180017873  jz      short loc_180017889
0x180017875  lea     rcx, [rdi+rax]
0x180017879  jmp     short loc_180017884
0x18001787b  xor     edx, edx
0x18001787d  mov     [rax], dx
0x180017880  add     rax, 2
0x180017884  cmp     rax, rcx
0x180017887  jnz     short loc_18001787B
0x180017889  mov     [rsp+38h+var_18], 1
0x180017891  mov     rcx, [rsp+38h]; this
0x180017896  cmp     qword ptr [rbx], 0
0x18001789a  jz      short loc_1800178AA
0x18001789c  mov     rax, rbx
0x18001789f  mov     rbx, [rsp+38h+arg_8]
0x1800178a4  add     rsp, 30h
0x1800178a8  pop     rdi
0x1800178a9  retn
0x1800178aa  mov     edx, 1321h; void *
0x1800178af  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800178b5  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800178bc  mov     edx, 12CEh; void *
0x1800178c1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
