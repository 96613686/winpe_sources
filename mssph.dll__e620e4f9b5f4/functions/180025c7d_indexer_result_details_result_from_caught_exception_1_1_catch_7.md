# _indexer::result::details::result_from_caught_exception_1__::_1_::catch$7

- ea: `0x180025c7d`
- end: `0x180025cf7`
- name: `_indexer::result::details::result_from_caught_exception_1__::_1_::catch$7`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001c55c`
- `0x180027010`

## string_xrefs

- `0x180025cb3`: `std::bad_optional_access`

## pseudocode

```c
__int64 __fastcall indexer::result::details::result_from_caught_exception_1__::_1_::catch_7(__int64 a1, __int64 a2)
{
  const char *v3; // rax
  const char *v4; // r9
  const char *v6; // [rsp+20h] [rbp-38h]
  wil::details *v7; // [rsp+30h] [rbp-28h]
  const char *v8; // [rsp+48h] [rbp-10h]

  *(_DWORD *)(a2 + 312) = -2147019873;
  v3 = (const char *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 128) + 8LL))(*(_QWORD *)(a2 + 128));
  LODWORD(v7) = -2147019873;
  indexer::result::details::log_error_code_exception(
    *(indexer::result::details **)(a2 + 288),
    (void *)*(unsigned int *)(a2 + 296),
    *(_QWORD *)(a2 + 304),
    v4,
    v6,
    *(const char **)(a2 + 280),
    v7,
    (__int64)"std::bad_optional_access",
    v3,
    v8);
  return 0;
}

```

## disassembly

```asm
0x180025c7d  mov     [rsp+arg_8], rdx
0x180025c82  push    rbp
0x180025c83  sub     rsp, 50h
0x180025c87  mov     rbp, rdx
0x180025c8a  mov     dword ptr [rbp+138h], 8007139Fh
0x180025c94  mov     rcx, [rbp+80h]
0x180025c9b  mov     rax, [rcx]
0x180025c9e  mov     rax, [rax+8]
0x180025ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ca7  mov     rcx, [rbp+118h]
0x180025cae  mov     [rsp+58h+var_18], rax; char *
0x180025cb3  lea     rax, aStdBadOptional; "std::bad_optional_access"
0x180025cba  mov     [rsp+58h+var_20], rax; __int64
0x180025cbf  mov     dword ptr [rsp+58h+var_28], 8007139Fh; wil::details *
0x180025cc7  mov     [rsp+58h+var_30], rcx; char *
0x180025ccc  mov     r8, [rbp+130h]; unsigned int
0x180025cd3  mov     edx, [rbp+128h]; void *
0x180025cd9  mov     rcx, [rbp+120h]; this
0x180025ce0  call    ?log_error_code_exception@details@result@indexer@@YAXPEAXIPEBD110J11@Z; indexer::result::details::log_error_code_exception(void *,uint,char const *,char const *,char const *,void *,long,char const *,char const *)
0x180025ce5  nop
0x180025ce6  mov     rax, 0
0x180025cf0  add     rsp, 50h
0x180025cf4  pop     rbp
0x180025cf5  retn
```
