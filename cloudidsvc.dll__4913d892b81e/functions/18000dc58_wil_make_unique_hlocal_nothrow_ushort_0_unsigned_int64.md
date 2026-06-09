# wil::make_unique_hlocal_nothrow<ushort [0]>(unsigned __int64)

- ea: `0x18000dc58`
- end: `0x18000dcb8`
- name: `??$make_unique_hlocal_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z`
- size: `96`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dc08`

## callees

- `0x18000dc58`
- `0x18000fd34`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000dc88`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000dc88`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_hlocal_nothrow<unsigned short [0]>(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned int a3,
        const char *a4)
{
  __int64 v5; // rdi
  _WORD *v6; // rax
  _WORD *v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 > 0x7FFFFFFFFFFFFFFFLL )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, (void *)a2, a3, a4);
  v5 = a2;
  v6 = LocalAlloc(0, 2 * a2);
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
0x18000dc58  mov     [rsp+arg_0], rbx
0x18000dc5d  push    rdi
0x18000dc5e  sub     rsp, 20h
0x18000dc62  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000dc6c  mov     rbx, rcx
0x18000dc6f  cmp     rdx, rax
0x18000dc72  jbe     short loc_18000DC7F
0x18000dc74  mov     rcx, [rsp+28h]; this
0x18000dc79  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000dc7f  lea     rdi, [rdx+rdx]
0x18000dc83  xor     ecx, ecx; uFlags
0x18000dc85  mov     rdx, rdi; uBytes
0x18000dc88  call    cs:__imp_LocalAlloc
0x18000dc8e  mov     [rbx], rax
0x18000dc91  test    rax, rax
0x18000dc94  jz      short loc_18000DCAA
0x18000dc96  lea     rcx, [rdi+rax]
0x18000dc9a  jmp     short loc_18000DCA5
0x18000dc9c  xor     edx, edx
0x18000dc9e  mov     [rax], dx
0x18000dca1  add     rax, 2
0x18000dca5  cmp     rax, rcx
0x18000dca8  jnz     short loc_18000DC9C
0x18000dcaa  mov     rax, rbx
0x18000dcad  mov     rbx, [rsp+28h+arg_0]
0x18000dcb2  add     rsp, 20h
0x18000dcb6  pop     rdi
0x18000dcb7  retn
```
