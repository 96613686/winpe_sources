# std::_Parser<ushort const *,ushort,std::regex_traits<ushort>>::_Disjunction(void)

- ea: `0x18002de68`
- end: `0x18002dff0`
- name: `?_Disjunction@?$_Parser@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ`
- size: `392`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x18002dcd4`
- `0x180030638`

## callees

- `0x180002fd4`
- `0x18002c708`
- `0x18002ced4`
- `0x18002de68`
- `0x18002ebe0`
- `0x18002fc54`
- `0x180030434`

## pseudocode

```c
__int64 __fastcall std::_Parser<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Disjunction(
        __int64 a1)
{
  __int64 v1; // rbp
  __int64 v3; // r13
  _DWORD *v4; // rsi
  __int64 result; // rax
  __int64 v6; // rax
  __int64 v7; // r15
  _WORD *v8; // rdx
  _WORD *v9; // rcx
  int v10; // r8d
  __int64 v11; // rax
  __int64 v12; // rdi
  __int64 v13; // r14
  __int64 v14; // rax
  _QWORD *v15; // rax

  v1 = a1 + 64;
  v3 = *(_QWORD *)(a1 + 72);
  v4 = (_DWORD *)(a1 + 124);
  result = ((__int64 (*)(void))std::_Parser<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Alternative)();
  if ( !(_BYTE)result )
  {
    if ( *v4 != 124 )
      return result;
    v6 = std::_Builder<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_New_node(v1, 8);
    std::_Builder<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_End_group(v1, v6);
  }
  result = std::_Builder<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Begin_if(v1, v3);
  v7 = result;
  while ( *v4 == 124 )
  {
    v8 = *(_WORD **)a1;
    if ( *(_QWORD *)a1 != *(_QWORD *)(a1 + 16) )
    {
      if ( *v8 != 92
        || (v9 = v8 + 1, v8 + 1 == *(_WORD **)(a1 + 16))
        || ((v10 = *(_DWORD *)(a1 + 128), (v10 & 8) != 0) || (unsigned __int16)(*v9 - 40) > 1u)
        && ((v10 & 0x10) != 0 || ((*v9 - 123) & 0xFFFD) != 0) )
      {
        v9 = *(_WORD **)a1;
      }
      *(_QWORD *)a1 = v9 + 1;
    }
    std::_Parser<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Trans(a1);
    if ( !(unsigned __int8)std::_Parser<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Alternative(a1) )
    {
      v11 = std::_Builder<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_New_node(v1, 8);
      std::_Builder<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_End_group(v1, v11);
    }
    v12 = *(_QWORD *)(v3 + 16);
    v13 = *(_QWORD *)(v7 + 16);
    *(_QWORD *)(v7 + 16) = 0;
    v14 = *(_QWORD *)(a1 + 72);
    *(_QWORD *)(a1 + 72) = v7;
    *(_QWORD *)(v7 + 16) = 0;
    *(_QWORD *)(v14 + 16) = v7;
    while ( *(_QWORD *)(v12 + 40) )
      v12 = *(_QWORD *)(v12 + 40);
    v15 = operator new(0x30u);
    if ( v15 )
    {
      v15[1] = 16;
      *v15 = &std::_Node_if::`vftable';
      v15[2] = 0;
      v15[3] = 0;
      v15[4] = v7;
      v15[5] = 0;
    }
    *(_QWORD *)(v12 + 40) = v15;
    v15[2] = v13;
    result = *(_QWORD *)(v12 + 40);
    *(_QWORD *)(v13 + 24) = result;
  }
  return result;
}

```

## disassembly

```asm
0x18002de68  mov     [rsp+arg_8], rbx
0x18002de6d  mov     [rsp+arg_10], rbp
0x18002de72  push    rsi
0x18002de73  push    rdi
0x18002de74  push    r13
0x18002de76  push    r14
0x18002de78  push    r15
0x18002de7a  sub     rsp, 20h
0x18002de7e  lea     rbp, [rcx+40h]
0x18002de82  mov     rbx, rcx
0x18002de85  mov     r13, [rbp+8]
0x18002de89  lea     rsi, [rcx+7Ch]
0x18002de8d  call    ?_Alternative@?$_Parser@PEBGGV?$regex_traits@G@std@@@std@@AEAA_NXZ; std::_Parser<ushort const *,ushort,std::regex_traits<ushort>>::_Alternative(void)
0x18002de92  test    al, al
0x18002de94  jnz     short loc_18002DEB7
0x18002de96  cmp     dword ptr [rsi], 7Ch ; '|'
0x18002de99  jnz     loc_18002DFD8
0x18002de9f  mov     edx, 8
0x18002dea4  mov     rcx, rbp
0x18002dea7  call    ?_New_node@?$_Builder@PEBGGV?$regex_traits@G@std@@@std@@AEAAPEAV_Node_base@2@W4_Node_type@2@@Z; std::_Builder<ushort const *,ushort,std::regex_traits<ushort>>::_New_node(std::_Node_type)
0x18002deac  mov     rdx, rax
0x18002deaf  mov     rcx, rbp
0x18002deb2  call    ?_End_group@?$_Builder@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEAV_Node_base@2@@Z; std::_Builder<ushort const *,ushort,std::regex_traits<ushort>>::_End_group(std::_Node_base *)
0x18002deb7  mov     rdx, r13
0x18002deba  mov     rcx, rbp
0x18002debd  call    ?_Begin_if@?$_Builder@PEBGGV?$regex_traits@G@std@@@std@@QEAAPEAV_Node_base@2@PEAV32@@Z; std::_Builder<ushort const *,ushort,std::regex_traits<ushort>>::_Begin_if(std::_Node_base *)
0x18002dec2  mov     r15, rax
0x18002dec5  jmp     loc_18002DFCF
0x18002deca  mov     rdx, [rbx]
0x18002decd  cmp     rdx, [rbx+10h]
0x18002ded1  jz      short loc_18002DF20
0x18002ded3  cmp     word ptr [rdx], 5Ch ; '\'
0x18002ded7  jnz     short loc_18002DF16
0x18002ded9  lea     rcx, [rdx+2]
0x18002dedd  cmp     rcx, [rbx+10h]
0x18002dee1  jz      short loc_18002DF16
0x18002dee3  mov     r8d, [rbx+80h]
0x18002deea  test    r8b, 8
0x18002deee  jnz     short loc_18002DEFD
0x18002def0  movzx   eax, word ptr [rcx]
0x18002def3  sub     ax, 28h ; '('
0x18002def7  cmp     ax, 1
0x18002defb  jbe     short loc_18002DF19
0x18002defd  test    r8b, 10h
0x18002df01  jnz     short loc_18002DF16
0x18002df03  movzx   eax, word ptr [rcx]
0x18002df06  mov     r8d, 0FFFDh
0x18002df0c  sub     ax, 7Bh ; '{'
0x18002df10  test    r8w, ax
0x18002df14  jz      short loc_18002DF19
0x18002df16  mov     rcx, rdx
0x18002df19  lea     rax, [rcx+2]
0x18002df1d  mov     [rbx], rax
0x18002df20  mov     rcx, rbx
0x18002df23  call    ?_Trans@?$_Parser@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser<ushort const *,ushort,std::regex_traits<ushort>>::_Trans(void)
0x18002df28  mov     rcx, rbx
0x18002df2b  call    ?_Alternative@?$_Parser@PEBGGV?$regex_traits@G@std@@@std@@AEAA_NXZ; std::_Parser<ushort const *,ushort,std::regex_traits<ushort>>::_Alternative(void)
0x18002df30  test    al, al
0x18002df32  jnz     short loc_18002DF4C
0x18002df34  mov     edx, 8
0x18002df39  mov     rcx, rbp
0x18002df3c  call    ?_New_node@?$_Builder@PEBGGV?$regex_traits@G@std@@@std@@AEAAPEAV_Node_base@2@W4_Node_type@2@@Z; std::_Builder<ushort const *,ushort,std::regex_traits<ushort>>::_New_node(std::_Node_type)
0x18002df41  mov     rdx, rax
0x18002df44  mov     rcx, rbp
0x18002df47  call    ?_End_group@?$_Builder@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEAV_Node_base@2@@Z; std::_Builder<ushort const *,ushort,std::regex_traits<ushort>>::_End_group(std::_Node_base *)
0x18002df4c  mov     rdi, [r13+10h]
0x18002df50  mov     r14, [r15+10h]
0x18002df54  mov     qword ptr [r15+10h], 0
0x18002df5c  mov     rax, [rbx+48h]
0x18002df60  mov     [rbx+48h], r15
0x18002df64  mov     qword ptr [r15+10h], 0
0x18002df6c  mov     [rax+10h], r15
0x18002df70  jmp     short loc_18002DF76
0x18002df72  mov     rdi, [rdi+28h]
0x18002df76  cmp     qword ptr [rdi+28h], 0
0x18002df7b  jnz     short loc_18002DF72
0x18002df7d  mov     ecx, 30h ; '0'; Size
0x18002df82  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002df87  mov     [rsp+48h+arg_0], rax
0x18002df8c  test    rax, rax
0x18002df8f  jz      short loc_18002DFBF
0x18002df91  lea     rcx, ??_7_Node_if@std@@6B@; const std::_Node_if::`vftable'
0x18002df98  mov     qword ptr [rax+8], 10h
0x18002dfa0  mov     [rax], rcx
0x18002dfa3  mov     qword ptr [rax+10h], 0
0x18002dfab  mov     qword ptr [rax+18h], 0
0x18002dfb3  mov     [rax+20h], r15
0x18002dfb7  mov     qword ptr [rax+28h], 0
0x18002dfbf  mov     [rdi+28h], rax
0x18002dfc3  mov     [rax+10h], r14
0x18002dfc7  mov     rax, [rdi+28h]
0x18002dfcb  mov     [r14+18h], rax
0x18002dfcf  cmp     dword ptr [rsi], 7Ch ; '|'
0x18002dfd2  jz      loc_18002DECA
0x18002dfd8  mov     rbx, [rsp+48h+arg_8]
0x18002dfdd  mov     rbp, [rsp+48h+arg_10]
0x18002dfe2  add     rsp, 20h
0x18002dfe6  pop     r15
0x18002dfe8  pop     r14
0x18002dfea  pop     r13
0x18002dfec  pop     rdi
0x18002dfed  pop     rsi
0x18002dfee  retn
```
