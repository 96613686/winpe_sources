# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Find_last<ushort const *>(ushort const * const &,unsigned __int64)

- ea: `0x18001825c`
- end: `0x1800182e5`
- name: `??$_Find_last@PEBG@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@PEBGPEAX@std@@@1@AEBQEBG_K@Z`
- size: `137`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _QWORD *, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018328`
- `0x18001a5d0`

## callees

- `0x18001825c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800182a0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800182c1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800182a0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800182c1`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Find_last<unsigned short const *>(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4)
{
  __int64 v5; // rsi
  _QWORD *v6; // rdx
  _QWORD *v8; // rdi
  _QWORD *v9; // rsi
  int v10; // eax

  v5 = a1[3];
  v6 = (_QWORD *)a1[1];
  v8 = *(_QWORD **)(v5 + 16 * (a4 & a1[6]) + 8);
  if ( v8 == v6 )
  {
    *a2 = v6;
  }
  else
  {
    v9 = *(_QWORD **)(v5 + 16 * (a4 & a1[6]));
    while ( (int)_o__wcsicmp(*a3, v8[2]) < 0 )
    {
      if ( v8 == v9 )
      {
        *a2 = v8;
        goto LABEL_3;
      }
      v8 = (_QWORD *)v8[1];
    }
    v10 = _o__wcsicmp(v8[2], *a3);
    *a2 = *v8;
    if ( v10 >= 0 )
    {
      a2[1] = v8;
      return a2;
    }
  }
LABEL_3:
  a2[1] = 0;
  return a2;
}

```

## disassembly

```asm
0x18001825c  push    rbx
0x18001825e  push    rsi
0x18001825f  push    rdi
0x180018260  push    r14
0x180018262  sub     rsp, 28h
0x180018266  mov     rax, [rcx+30h]
0x18001826a  mov     rbx, rdx
0x18001826d  mov     rsi, [rcx+18h]
0x180018271  and     rax, r9
0x180018274  mov     rdx, [rcx+8]
0x180018278  add     rax, rax
0x18001827b  mov     r14, r8
0x18001827e  mov     rdi, [rsi+rax*8+8]
0x180018283  cmp     rdi, rdx
0x180018286  jnz     short loc_180018295
0x180018288  mov     [rbx], rdx
0x18001828b  mov     qword ptr [rbx+8], 0
0x180018293  jmp     short loc_1800182D8
0x180018295  mov     rsi, [rsi+rax*8]
0x180018299  mov     rdx, [rdi+10h]
0x18001829d  mov     rcx, [r14]
0x1800182a0  call    cs:__imp__o__wcsicmp
0x1800182a6  test    eax, eax
0x1800182a8  jns     short loc_1800182BA
0x1800182aa  cmp     rdi, rsi
0x1800182ad  jz      short loc_1800182B5
0x1800182af  mov     rdi, [rdi+8]
0x1800182b3  jmp     short loc_180018299
0x1800182b5  mov     [rbx], rdi
0x1800182b8  jmp     short loc_18001828B
0x1800182ba  mov     rdx, [r14]
0x1800182bd  mov     rcx, [rdi+10h]
0x1800182c1  call    cs:__imp__o__wcsicmp
0x1800182c7  mov     rcx, [rdi]
0x1800182ca  shr     eax, 1Fh
0x1800182cd  mov     [rbx], rcx
0x1800182d0  test    al, al
0x1800182d2  jnz     short loc_18001828B
0x1800182d4  mov     [rbx+8], rdi
0x1800182d8  mov     rax, rbx
0x1800182db  add     rsp, 28h
0x1800182df  pop     r14
0x1800182e1  pop     rdi
0x1800182e2  pop     rsi
0x1800182e3  pop     rbx
0x1800182e4  retn
```
