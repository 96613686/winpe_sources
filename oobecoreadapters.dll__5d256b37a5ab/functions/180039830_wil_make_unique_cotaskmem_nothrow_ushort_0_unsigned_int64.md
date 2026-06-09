# wil::make_unique_cotaskmem_nothrow<ushort [0]>(unsigned __int64)

- ea: `0x180039830`
- end: `0x18003989a`
- name: `??$make_unique_cotaskmem_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003a984`

## callees

- `0x1800194d8`
- `0x180039830`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003986a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003986a`

## string_xrefs

- `0x180039851`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_cotaskmem_nothrow<unsigned short [0]>(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // rdi
  _WORD *v6; // rax
  _WORD *v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 > 0x7FFFFFFFFFFFFFFFLL )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1802,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v5 = a2;
  v6 = CoTaskMemAlloc(2 * a2);
  *a1 = v6;
  if ( v6 )
  {
    v7 = &v6[v5];
    while ( v6 != v7 )
      *v6++ = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180039830  mov     [rsp+arg_0], rbx
0x180039835  push    rdi
0x180039836  sub     rsp, 20h
0x18003983a  mov     rax, 7FFFFFFFFFFFFFFFh
0x180039844  mov     rbx, rcx
0x180039847  cmp     rdx, rax
0x18003984a  jbe     short loc_180039863
0x18003984c  mov     rcx, [rsp+28h]; this
0x180039851  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180039858  mov     edx, 1802h; void *
0x18003985d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180039863  lea     rdi, [rdx+rdx]
0x180039867  mov     rcx, rdi; cb
0x18003986a  call    cs:__imp_CoTaskMemAlloc
0x180039870  mov     [rbx], rax
0x180039873  test    rax, rax
0x180039876  jz      short loc_18003988C
0x180039878  lea     rcx, [rdi+rax]
0x18003987c  jmp     short loc_180039887
0x18003987e  xor     edx, edx
0x180039880  mov     [rax], dx
0x180039883  add     rax, 2
0x180039887  cmp     rax, rcx
0x18003988a  jnz     short loc_18003987E
0x18003988c  mov     rax, rbx
0x18003988f  mov     rbx, [rsp+28h+arg_0]
0x180039894  add     rsp, 20h
0x180039898  pop     rdi
0x180039899  retn
```
