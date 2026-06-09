# _indexer::result::details::result_from_caught_exception_1__::_1_::catch$7

- ea: `0x180016583`
- end: `0x1800165fd`
- name: `_indexer::result::details::result_from_caught_exception_1__::_1_::catch$7`
- size: `122`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180013ad8`
- `0x180018010`

## string_xrefs

- `0x1800165b9`: `std::bad_optional_access`

## pseudocode

```c
__int64 __fastcall indexer::result::details::result_from_caught_exception_1__::_1_::catch_7(__int64 a1, __int64 a2)
{
  const char *v3; // rax
  const char *v4; // r9
  const char *v6; // [rsp+20h] [rbp-38h]
  wil::details *v7; // [rsp+30h] [rbp-28h]

  *(_DWORD *)(a2 + 296) = -2147019873;
  v3 = (const char *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 128) + 8LL))(*(_QWORD *)(a2 + 128));
  LODWORD(v7) = -2147019873;
  indexer::result::details::log_error_code_exception(
    *(indexer::result::details **)(a2 + 272),
    (void *)*(unsigned int *)(a2 + 280),
    *(_QWORD *)(a2 + 288),
    v4,
    v6,
    *(const char **)(a2 + 264),
    v7,
    (__int64)"std::bad_optional_access",
    v3);
  return 0;
}

```

## disassembly

```asm
0x180016583  mov     [rsp+arg_8], rdx
0x180016588  push    rbp
0x180016589  sub     rsp, 50h
0x18001658d  mov     rbp, rdx
0x180016590  mov     dword ptr [rbp+128h], 8007139Fh
0x18001659a  mov     rcx, [rbp+80h]
0x1800165a1  mov     rax, [rcx]
0x1800165a4  mov     rax, [rax+8]
0x1800165a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165ad  mov     rcx, [rbp+108h]
0x1800165b4  mov     [rsp+58h+var_18], rax; char *
0x1800165b9  lea     rax, aStdBadOptional; "std::bad_optional_access"
0x1800165c0  mov     [rsp+58h+var_20], rax; __int64
0x1800165c5  mov     dword ptr [rsp+58h+var_28], 8007139Fh; wil::details *
0x1800165cd  mov     [rsp+58h+var_30], rcx; char *
0x1800165d2  mov     r8, [rbp+120h]; unsigned int
0x1800165d9  mov     edx, [rbp+118h]; void *
0x1800165df  mov     rcx, [rbp+110h]; this
0x1800165e6  call    ?log_error_code_exception@details@result@indexer@@YAXPEAXIPEBD110J11@Z; indexer::result::details::log_error_code_exception(void *,uint,char const *,char const *,char const *,void *,long,char const *,char const *)
0x1800165eb  nop
0x1800165ec  mov     rax, 0
0x1800165f6  add     rsp, 50h
0x1800165fa  pop     rbp
0x1800165fb  retn
```
