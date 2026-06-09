# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Replace<ushort>(unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)

- ea: `0x18000d694`
- end: `0x18000d81d`
- name: `??$_Replace@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_K_KQEBG0@Z`
- size: `393`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int64, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000eaf4`

## callees

- `0x18000c338`
- `0x18000d578`
- `0x18000d694`
- `0x18000fd10`
- `0x180010774`
- `0x180010780`

## pseudocode

```c
__int64 __fastcall std::wstring::_Replace<unsigned short>(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        __int64 a4,
        unsigned __int64 a5)
{
  int v7; // r8d
  int v8; // r9d
  __int64 v9; // r13
  __int64 v10; // rax
  size_t v11; // r8
  char *v13; // rdi
  unsigned __int64 v14; // r12
  __int64 v15; // rax
  __int64 v16; // rdx
  const wchar_t *v17; // r9
  __int64 v18; // rdi
  char *v19; // [rsp+A8h] [rbp+20h]

  std::_String_val<std::_Simple_types<unsigned short>>::_Check_offset();
  v9 = *(_QWORD *)(a1 + 16);
  if ( v9 - 1 < a3 )
    a3 = v9 - 1;
  if ( a3 == a5 )
  {
    v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    memmove_0((void *)(v10 + 2), L"74727632", v11);
    return a1;
  }
  if ( a5 < a3 )
  {
    v13 = (char *)(std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1) + 2);
    memmove_0(v13, L"74727632", 2 * a5);
    memmove_0(&v13[2 * a5], &v13[2 * a3], 2 * (v9 - 1 - a3) + 2);
    *(_QWORD *)(a1 + 16) = a5 + v9 - a3;
    return a1;
  }
  v14 = a5 - a3;
  if ( a5 - a3 <= *(_QWORD *)(a1 + 24) - v9 )
  {
    *(_QWORD *)(a1 + 16) = v14 + v9;
    v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    v19 = (char *)(v15 + 2);
    v17 = (const wchar_t *)(v15 + 2 + 2 * a3);
    if ( (unsigned __int64)&a74727632[a5] <= v15 + 2 || (unsigned __int64)L"74727632" > v15 + 2 * v9 )
    {
      v18 = a5;
    }
    else if ( v17 > L"74727632" )
    {
      v18 = v17 - L"74727632";
    }
    else
    {
      v18 = 0;
    }
    memmove_0((void *)&v17[v14], v17, 2 * v16 + 2);
    memmove_0(v19, L"74727632", 2 * v18);
    memcpy_0(&v19[2 * v18], &a74727632[v14 + v18], 2 * (a5 - v18));
    return a1;
  }
  return std::wstring::_Reallocate_grow_by<_lambda_622fe101509e1fd0c758e599152cbb8b_,unsigned __int64,unsigned __int64,unsigned short const *,unsigned __int64>(
           a1,
           (int)a5 - (int)a3,
           v7,
           v8,
           a3);
}

```

## disassembly

```asm
0x18000d694  mov     [rsp+arg_18], r9
0x18000d699  push    rbx
0x18000d69a  push    rbp
0x18000d69b  push    rsi
0x18000d69c  push    rdi
0x18000d69d  push    r12
0x18000d69f  push    r13
0x18000d6a1  push    r14
0x18000d6a3  push    r15
0x18000d6a5  sub     rsp, 48h
0x18000d6a9  mov     rsi, r8
0x18000d6ac  mov     rbp, rcx
0x18000d6af  call    ?_Check_offset@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAX_K@Z; std::_String_val<std::_Simple_types<ushort>>::_Check_offset(unsigned __int64)
0x18000d6b4  mov     r13, [rbp+10h]
0x18000d6b8  mov     rcx, rbp
0x18000d6bb  mov     r14, [rsp+88h+arg_20]
0x18000d6c3  lea     rdx, [r13-1]
0x18000d6c7  cmp     rdx, rsi
0x18000d6ca  cmovb   rsi, rdx
0x18000d6ce  cmp     rsi, r14
0x18000d6d1  jnz     short loc_18000D6F4
0x18000d6d3  lea     r8, [r14+r14]
0x18000d6d7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000d6dc  lea     rdx, a74727632; "74727632"
0x18000d6e3  lea     rcx, [rax+2]; void *
0x18000d6e7  call    memmove_0
0x18000d6ec  mov     rax, rbp
0x18000d6ef  jmp     loc_18000D80C
0x18000d6f4  sub     rdx, rsi
0x18000d6f7  mov     [rsp+88h+arg_18], rdx
0x18000d6ff  cmp     r14, rsi
0x18000d702  jnb     short loc_18000D74C
0x18000d704  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000d709  lea     rbx, [r14+r14]
0x18000d70d  mov     r8, rbx; Size
0x18000d710  lea     rdx, a74727632; "74727632"
0x18000d717  lea     rdi, [rax+2]
0x18000d71b  mov     rcx, rdi; void *
0x18000d71e  call    memmove_0
0x18000d723  mov     r8, [rsp+88h+arg_18]
0x18000d72b  lea     rdx, [rdi+rsi*2]; Src
0x18000d72f  lea     rcx, [rdi+rbx]; void *
0x18000d733  lea     r8, ds:2[r8*2]; Size
0x18000d73b  call    memmove_0
0x18000d740  sub     r13, rsi
0x18000d743  add     r13, r14
0x18000d746  mov     [rbp+10h], r13
0x18000d74a  jmp     short loc_18000D6EC
0x18000d74c  mov     rax, [rbp+18h]
0x18000d750  mov     r12, r14
0x18000d753  sub     r12, rsi
0x18000d756  sub     rax, r13
0x18000d759  cmp     r12, rax
0x18000d75c  ja      loc_18000D7FA
0x18000d762  lea     rax, [r12+r13]
0x18000d766  mov     [rbp+10h], rax
0x18000d76a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000d76f  lea     r15, a74727632; "74727632"
0x18000d776  lea     rcx, [r15+r14*2]
0x18000d77a  lea     r8, [rax+2]
0x18000d77e  mov     [rsp+88h+arg_18], r8
0x18000d786  lea     r9, [r8+rsi*2]
0x18000d78a  cmp     rcx, r8
0x18000d78d  jbe     short loc_18000D7AC
0x18000d78f  lea     rax, [rax+r13*2]
0x18000d793  cmp     r15, rax
0x18000d796  ja      short loc_18000D7AC
0x18000d798  cmp     r9, r15
0x18000d79b  ja      short loc_18000D7A1
0x18000d79d  xor     edi, edi
0x18000d79f  jmp     short loc_18000D7AF
0x18000d7a1  mov     rdi, r9
0x18000d7a4  sub     rdi, r15
0x18000d7a7  sar     rdi, 1
0x18000d7aa  jmp     short loc_18000D7AF
0x18000d7ac  mov     rdi, r14
0x18000d7af  lea     r8, ds:2[rdx*2]; Size
0x18000d7b7  mov     rdx, r9; Src
0x18000d7ba  lea     rcx, [r9+r12*2]; void *
0x18000d7be  call    memmove_0
0x18000d7c3  mov     rsi, [rsp+88h+arg_18]
0x18000d7cb  lea     rbx, [rdi+rdi]
0x18000d7cf  mov     r8, rbx; Size
0x18000d7d2  mov     rcx, rsi; void *
0x18000d7d5  mov     rdx, r15; Src
0x18000d7d8  call    memmove_0
0x18000d7dd  sub     r14, rdi
0x18000d7e0  lea     rax, [r12+rdi]
0x18000d7e4  lea     rdx, [r15+rax*2]; Src
0x18000d7e8  lea     rcx, [rbx+rsi]; void *
0x18000d7ec  lea     r8, [r14+r14]; Size
0x18000d7f0  call    memcpy_0
0x18000d7f5  jmp     loc_18000D6EC
0x18000d7fa  mov     [rsp+88h+var_58], r14
0x18000d7ff  mov     rdx, r12
0x18000d802  mov     [rsp+88h+var_68], rsi
0x18000d807  call    ??$_Reallocate_grow_by@V_lambda_622fe101509e1fd0c758e599152cbb8b_@@_K_KPEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_622fe101509e1fd0c758e599152cbb8b_@@_K2PEBG2@Z; std::wstring::_Reallocate_grow_by<_lambda_622fe101509e1fd0c758e599152cbb8b_,unsigned __int64,unsigned __int64,ushort const *,unsigned __int64>(unsigned __int64,_lambda_622fe101509e1fd0c758e599152cbb8b_,unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x18000d80c  add     rsp, 48h
0x18000d810  pop     r15
0x18000d812  pop     r14
0x18000d814  pop     r13
0x18000d816  pop     r12
0x18000d818  pop     rdi
0x18000d819  pop     rsi
0x18000d81a  pop     rbp
0x18000d81b  pop     rbx
0x18000d81c  retn
```
