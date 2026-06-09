# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::replace(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x180001b2c`
- end: `0x180001c9e`
- name: `?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0PEBG0@Z`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180010948`

## callees

- `0x180001b2c`
- `0x180002044`
- `0x1800022f0`
- `0x180002630`
- `0x18000265c`
- `0x180002890`
- `0x180002b00`
- `0x180002b2c`
- `0x180007830`

## pseudocode

```c
_QWORD *__fastcall std::wstring::replace(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        _BYTE *a4,
        unsigned __int64 a5)
{
  _QWORD *v9; // rax
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rbp
  _QWORD *v13; // rcx
  _QWORD *v14; // rdx
  unsigned __int64 v15; // r12
  _QWORD *v16; // rcx
  _QWORD *v17; // rdx
  _QWORD *v18; // rax

  if ( (unsigned __int8)std::wstring::_Inside(a1, a4) )
  {
    if ( a1[3] < 8u )
      v9 = a1;
    else
      v9 = (_QWORD *)*a1;
    return std::wstring::replace(a1, a2, a3, a1, (a4 - (_BYTE *)v9) >> 1, a5);
  }
  else
  {
    v11 = a1[2];
    if ( v11 < a2 )
      std::_Xout_of_range("invalid string position");
    if ( v11 - a2 < a3 )
      a3 = v11 - a2;
    if ( ~a5 <= v11 - a3 )
      std::_Xlength_error("string too long");
    v12 = v11 - a2 - a3;
    if ( a5 < a3 )
    {
      if ( a1[3] < 8u )
      {
        v13 = a1;
        v14 = a1;
      }
      else
      {
        v13 = (_QWORD *)*a1;
        v14 = (_QWORD *)*a1;
      }
      std::char_traits<unsigned short>::move((char *)v13 + 2 * a2 + 2 * a5, (char *)v14 + 2 * a2 + 2 * a3, v12);
    }
    if ( a5 || a3 )
    {
      v15 = a5 + a1[2] - a3;
      if ( (unsigned __int8)std::wstring::_Grow(a1, v15, 0) )
      {
        if ( a3 < a5 )
        {
          if ( a1[3] < 8u )
          {
            v16 = a1;
            v17 = a1;
          }
          else
          {
            v16 = (_QWORD *)*a1;
            v17 = (_QWORD *)*a1;
          }
          std::char_traits<unsigned short>::move((char *)v16 + 2 * a2 + 2 * a5, (char *)v17 + 2 * a2 + 2 * a3, v12);
        }
        if ( a1[3] < 8u )
          v18 = a1;
        else
          v18 = (_QWORD *)*a1;
        std::char_traits<unsigned short>::copy((char *)v18 + 2 * a2, a4, a5);
        std::wstring::_Eos(a1, v15);
      }
    }
    return a1;
  }
}

```

## disassembly

```asm
0x180001b2c  push    rbx
0x180001b2e  push    rbp
0x180001b2f  push    rsi
0x180001b30  push    rdi
0x180001b31  push    r12
0x180001b33  push    r14
0x180001b35  push    r15
0x180001b37  sub     rsp, 30h
0x180001b3b  mov     r14, rdx
0x180001b3e  mov     r15, r9
0x180001b41  mov     rdx, r9
0x180001b44  mov     rdi, r8
0x180001b47  mov     rbx, rcx
0x180001b4a  call    ?_Inside@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_NPEBG@Z; std::wstring::_Inside(ushort const *)
0x180001b4f  test    al, al
0x180001b51  jz      short loc_180001B90
0x180001b53  cmp     qword ptr [rbx+18h], 8
0x180001b58  jb      short loc_180001B5F
0x180001b5a  mov     rax, [rbx]
0x180001b5d  jmp     short loc_180001B62
0x180001b5f  mov     rax, rbx
0x180001b62  sub     r15, rax
0x180001b65  mov     r9, rbx
0x180001b68  mov     rax, [rsp+68h+arg_20]
0x180001b70  mov     r8, rdi
0x180001b73  sar     r15, 1
0x180001b76  mov     rdx, r14
0x180001b79  mov     [rsp+68h+var_40], rax
0x180001b7e  mov     rcx, rbx
0x180001b81  mov     [rsp+68h+var_48], r15
0x180001b86  call    ?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0AEBV12@00@Z; std::wstring::replace(unsigned __int64,unsigned __int64,std::wstring const &,unsigned __int64,unsigned __int64)
0x180001b8b  jmp     loc_180001C8F
0x180001b90  mov     rcx, [rbx+10h]
0x180001b94  cmp     rcx, r14
0x180001b97  jnb     short loc_180001BA6
0x180001b99  lea     rcx, aInvalidStringP; "invalid string position"
0x180001ba0  call    ?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180001ba6  mov     rsi, [rsp+68h+arg_20]
0x180001bae  mov     rbp, rcx
0x180001bb1  sub     rbp, r14
0x180001bb4  mov     rax, rsi
0x180001bb7  cmp     rbp, rdi
0x180001bba  not     rax
0x180001bbd  cmovb   rdi, rbp
0x180001bc1  sub     rcx, rdi
0x180001bc4  cmp     rax, rcx
0x180001bc7  ja      short loc_180001BD6
0x180001bc9  lea     rcx, aStringTooLong; "string too long"
0x180001bd0  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180001bd6  sub     rbp, rdi
0x180001bd9  cmp     rsi, rdi
0x180001bdc  jnb     short loc_180001C0B
0x180001bde  cmp     qword ptr [rbx+18h], 8
0x180001be3  jb      short loc_180001BED
0x180001be5  mov     rcx, [rbx]
0x180001be8  mov     rdx, rcx
0x180001beb  jmp     short loc_180001BF3
0x180001bed  mov     rcx, rbx
0x180001bf0  mov     rdx, rbx
0x180001bf3  lea     rax, [r14+rdi]
0x180001bf7  mov     r8, rbp
0x180001bfa  lea     rdx, [rdx+rax*2]
0x180001bfe  lea     rax, [r14+rsi]
0x180001c02  lea     rcx, [rcx+rax*2]
0x180001c06  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x180001c0b  test    rsi, rsi
0x180001c0e  jnz     short loc_180001C15
0x180001c10  test    rdi, rdi
0x180001c13  jz      short loc_180001C8C
0x180001c15  mov     r12, [rbx+10h]
0x180001c19  xor     r8d, r8d
0x180001c1c  sub     r12, rdi
0x180001c1f  mov     rcx, rbx
0x180001c22  add     r12, rsi
0x180001c25  mov     rdx, r12
0x180001c28  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x180001c2d  test    al, al
0x180001c2f  jz      short loc_180001C8C
0x180001c31  cmp     rdi, rsi
0x180001c34  jnb     short loc_180001C63
0x180001c36  cmp     qword ptr [rbx+18h], 8
0x180001c3b  jb      short loc_180001C45
0x180001c3d  mov     rcx, [rbx]
0x180001c40  mov     rdx, rcx
0x180001c43  jmp     short loc_180001C4B
0x180001c45  mov     rcx, rbx
0x180001c48  mov     rdx, rbx
0x180001c4b  lea     rax, [r14+rdi]
0x180001c4f  mov     r8, rbp
0x180001c52  lea     rdx, [rdx+rax*2]
0x180001c56  lea     rax, [r14+rsi]
0x180001c5a  lea     rcx, [rcx+rax*2]
0x180001c5e  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x180001c63  cmp     qword ptr [rbx+18h], 8
0x180001c68  jb      short loc_180001C6F
0x180001c6a  mov     rax, [rbx]
0x180001c6d  jmp     short loc_180001C72
0x180001c6f  mov     rax, rbx
0x180001c72  lea     rcx, [rax+r14*2]
0x180001c76  mov     r8, rsi
0x180001c79  mov     rdx, r15
0x180001c7c  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x180001c81  mov     rdx, r12
0x180001c84  mov     rcx, rbx
0x180001c87  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x180001c8c  mov     rax, rbx
0x180001c8f  add     rsp, 30h
0x180001c93  pop     r15
0x180001c95  pop     r14
0x180001c97  pop     r12
0x180001c99  pop     rdi
0x180001c9a  pop     rsi
0x180001c9b  pop     rbp
0x180001c9c  pop     rbx
0x180001c9d  retn
```
