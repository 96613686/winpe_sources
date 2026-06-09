# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::append(ushort const * const)

- ea: `0x18000977c`
- end: `0x1800097f4`
- name: `?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z`
- size: `120`
- prototype: `_QWORD *__fastcall(_QWORD *Src, _WORD *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180008940`
- `0x18000ac08`
- `0x18000e284`
- `0x18000eae0`
- `0x180010170`

## callees

- `0x1800035f2`
- `0x180007c94`
- `0x18000977c`

## pseudocode

```c
_QWORD *__fastcall std::wstring::append(_QWORD *Src, _WORD *a2)
{
  _QWORD *v3; // rbx
  unsigned __int64 v4; // rdx
  __int64 v5; // rcx
  bool v6; // cc
  __int64 v7; // rsi
  _QWORD *v8; // rdi

  v3 = Src;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  v5 = Src[2];
  if ( v4 > v3[3] - v5 )
    return (_QWORD *)std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
                       v3,
                       v4);
  v6 = v3[3] <= 7u;
  v7 = v5 + v4;
  v3[2] = v5 + v4;
  if ( v6 )
    v8 = v3;
  else
    v8 = (_QWORD *)*v3;
  memmove_0((char *)v8 + 2 * v5, a2, 2 * v4);
  *((_WORD *)v8 + v7) = 0;
  return v3;
}

```

## disassembly

```asm
0x18000977c  push    rbx
0x18000977e  push    rbp
0x18000977f  push    rsi
0x180009780  push    rdi
0x180009781  sub     rsp, 38h
0x180009785  mov     r9, rdx
0x180009788  mov     rbx, rcx
0x18000978b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000978f  xor     ebp, ebp
0x180009791  inc     rdx
0x180009794  cmp     [r9+rdx*2], bp
0x180009799  jnz     short loc_180009791
0x18000979b  mov     rcx, [rcx+10h]
0x18000979f  mov     rax, [rbx+18h]
0x1800097a3  sub     rax, rcx
0x1800097a6  cmp     rdx, rax
0x1800097a9  ja      short loc_1800097D8
0x1800097ab  cmp     qword ptr [rbx+18h], 7
0x1800097b0  lea     rsi, [rcx+rdx]
0x1800097b4  mov     [rbx+10h], rsi
0x1800097b8  jbe     short loc_1800097BF
0x1800097ba  mov     rdi, [rbx]
0x1800097bd  jmp     short loc_1800097C2
0x1800097bf  mov     rdi, rbx
0x1800097c2  lea     r8, [rdx+rdx]; Size
0x1800097c6  mov     rdx, r9; Src
0x1800097c9  lea     rcx, [rdi+rcx*2]; void *
0x1800097cd  call    memmove_0
0x1800097d2  mov     [rdi+rsi*2], bp
0x1800097d6  jmp     short loc_1800097E8
0x1800097d8  mov     rcx, rbx; Src
0x1800097db  mov     [rsp+58h+var_38], rdx; __int64
0x1800097e0  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x1800097e5  mov     rbx, rax
0x1800097e8  mov     rax, rbx
0x1800097eb  add     rsp, 38h
0x1800097ef  pop     rdi
0x1800097f0  pop     rsi
0x1800097f1  pop     rbp
0x1800097f2  pop     rbx
0x1800097f3  retn
```
