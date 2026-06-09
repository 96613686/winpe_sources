# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::operator+=(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18000b2c0`
- end: `0x18000b345`
- name: `??Y?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z`
- size: `133`
- prototype: `_QWORD *__fastcall(_QWORD *Src, _QWORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b84c`
- `0x18000c8e0`
- `0x18000e228`
- `0x18000e458`

## callees

- `0x180007e88`
- `0x18000b2c0`
- `0x180013e04`

## pseudocode

```c
_QWORD *__fastcall std::wstring::operator+=(_QWORD *Src, _QWORD *a2)
{
  unsigned __int64 v3; // rcx
  __int64 v4; // r9
  bool v5; // cc
  __int64 v6; // rsi
  _QWORD *v7; // rdi

  v3 = a2[2];
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  v4 = Src[2];
  if ( v3 > Src[3] - v4 )
    return (_QWORD *)____Reallocate_grow_by_V_lambda_1___1_____Append__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W_K___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Append__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_K_Z(
                       Src,
                       v3);
  v5 = Src[3] <= 7u;
  v6 = v4 + v3;
  Src[2] = v4 + v3;
  if ( v5 )
    v7 = Src;
  else
    v7 = (_QWORD *)*Src;
  memmove_0((char *)v7 + 2 * v4, a2, 2 * v3);
  *((_WORD *)v7 + v6) = 0;
  return Src;
}

```

## disassembly

```asm
0x18000b2c0  mov     [rsp+arg_0], rbx
0x18000b2c5  mov     [rsp+arg_8], rsi
0x18000b2ca  push    rdi
0x18000b2cb  sub     rsp, 30h
0x18000b2cf  cmp     qword ptr [rdx+18h], 7
0x18000b2d4  mov     rbx, rcx
0x18000b2d7  mov     rcx, [rdx+10h]
0x18000b2db  jbe     short loc_18000B2E0
0x18000b2dd  mov     rdx, [rdx]; Src
0x18000b2e0  mov     r9, [rbx+10h]
0x18000b2e4  mov     rax, [rbx+18h]
0x18000b2e8  sub     rax, r9
0x18000b2eb  cmp     rcx, rax
0x18000b2ee  ja      short loc_18000B31C
0x18000b2f0  cmp     qword ptr [rbx+18h], 7
0x18000b2f5  lea     rsi, [r9+rcx]
0x18000b2f9  mov     [rbx+10h], rsi
0x18000b2fd  jbe     short loc_18000B304
0x18000b2ff  mov     rdi, [rbx]
0x18000b302  jmp     short loc_18000B307
0x18000b304  mov     rdi, rbx
0x18000b307  lea     r8, [rcx+rcx]; Size
0x18000b30b  lea     rcx, [rdi+r9*2]; void *
0x18000b30f  call    memmove_0
0x18000b314  xor     eax, eax
0x18000b316  mov     [rdi+rsi*2], ax
0x18000b31a  jmp     short loc_18000B332
0x18000b31c  mov     r9, rdx
0x18000b31f  mov     [rsp+38h+var_18], rcx; __int64
0x18000b324  mov     rdx, rcx
0x18000b327  mov     rcx, rbx; Src
0x18000b32a  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@QEB_W_K@Z@PEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@_W@01@AEAAAEAV01@QEB_W0@Z@PEB_W_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *,unsigned __int64>(unsigned __int64,`std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *,unsigned __int64)
0x18000b32f  mov     rbx, rax
0x18000b332  mov     rsi, [rsp+38h+arg_8]
0x18000b337  mov     rax, rbx
0x18000b33a  mov     rbx, [rsp+38h+arg_0]
0x18000b33f  add     rsp, 30h
0x18000b343  pop     rdi
0x18000b344  retn
```
