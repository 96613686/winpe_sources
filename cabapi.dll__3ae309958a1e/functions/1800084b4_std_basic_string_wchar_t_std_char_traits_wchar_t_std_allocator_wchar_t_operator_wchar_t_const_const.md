# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::operator+=(wchar_t const * const)

- ea: `0x1800084b4`
- end: `0x18000852c`
- name: `??Y?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z`
- size: `120`
- prototype: `_QWORD *__fastcall(_QWORD *Src, _WORD *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180008fd8`
- `0x18000b84c`
- `0x18000c8e0`
- `0x18000e228`
- `0x18000e458`

## callees

- `0x180007e88`
- `0x1800084b4`
- `0x180013e04`

## pseudocode

```c
_QWORD *__fastcall std::wstring::operator+=(_QWORD *Src, _WORD *a2)
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
    return (_QWORD *)____Reallocate_grow_by_V_lambda_1___1_____Append__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W_K___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Append__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_K_Z(
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
0x1800084b4  push    rbx
0x1800084b6  push    rbp
0x1800084b7  push    rsi
0x1800084b8  push    rdi
0x1800084b9  sub     rsp, 38h
0x1800084bd  mov     r9, rdx
0x1800084c0  mov     rbx, rcx
0x1800084c3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800084c7  xor     ebp, ebp
0x1800084c9  inc     rdx
0x1800084cc  cmp     [r9+rdx*2], bp
0x1800084d1  jnz     short loc_1800084C9
0x1800084d3  mov     rcx, [rcx+10h]
0x1800084d7  mov     rax, [rbx+18h]
0x1800084db  sub     rax, rcx
0x1800084de  cmp     rdx, rax
0x1800084e1  ja      short loc_180008510
0x1800084e3  cmp     qword ptr [rbx+18h], 7
0x1800084e8  lea     rsi, [rcx+rdx]
0x1800084ec  mov     [rbx+10h], rsi
0x1800084f0  jbe     short loc_1800084F7
0x1800084f2  mov     rdi, [rbx]
0x1800084f5  jmp     short loc_1800084FA
0x1800084f7  mov     rdi, rbx
0x1800084fa  lea     r8, [rdx+rdx]; Size
0x1800084fe  mov     rdx, r9; Src
0x180008501  lea     rcx, [rdi+rcx*2]; void *
0x180008505  call    memmove_0
0x18000850a  mov     [rdi+rsi*2], bp
0x18000850e  jmp     short loc_180008520
0x180008510  mov     rcx, rbx; Src
0x180008513  mov     [rsp+58h+var_38], rdx; __int64
0x180008518  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@QEB_W_K@Z@PEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@_W@01@AEAAAEAV01@QEB_W0@Z@PEB_W_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *,unsigned __int64>(unsigned __int64,`std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *,unsigned __int64)
0x18000851d  mov     rbx, rax
0x180008520  mov     rax, rbx
0x180008523  add     rsp, 38h
0x180008527  pop     rdi
0x180008528  pop     rsi
0x180008529  pop     rbp
0x18000852a  pop     rbx
0x18000852b  retn
```
