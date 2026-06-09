# std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Disjunction(void)

- ea: `0x180021640`
- end: `0x18002175c`
- name: `?_Disjunction@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ`
- size: `284`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x1800152a8`
- `0x180021764`
- `0x180021dd4`
- `0x18002394c`

## callees

- `0x1800037dc`
- `0x1800203d8`
- `0x180020828`
- `0x180021640`
- `0x1800223f8`
- `0x18002344c`
- `0x18002349c`

## pseudocode

```c
__int64 __fastcall std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Disjunction(
        __int64 a1)
{
  __int64 v1; // r13
  _DWORD *v2; // rdi
  __int64 result; // rax
  __int64 v5; // rbp
  __int64 v6; // rax
  __int64 v7; // r14
  __int64 v8; // rax
  __int64 v9; // rsi
  __int64 v10; // r15
  __int64 v11; // rax
  _QWORD *v12; // rax

  v1 = *(_QWORD *)(a1 + 64);
  v2 = (_DWORD *)(a1 + 112);
  result = ((__int64 (*)(void))std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Alternative)();
  if ( (_BYTE)result )
  {
    v5 = a1 + 56;
  }
  else
  {
    if ( *v2 != 124 )
      return result;
    v5 = a1 + 56;
    v6 = std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_New_node(a1 + 56, 8);
    result = std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_End_group(
               a1 + 56,
               v6);
  }
  if ( *v2 == 124 )
  {
    v7 = std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Begin_if(v5, v1);
    do
    {
      std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Next(a1);
      if ( !(unsigned __int8)std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Alternative(a1) )
      {
        v8 = std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_New_node(
               a1 + 56,
               8);
        std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_End_group(a1 + 56, v8);
      }
      v9 = *(_QWORD *)(v1 + 16);
      v10 = *(_QWORD *)(v7 + 16);
      *(_QWORD *)(v7 + 16) = 0;
      v11 = *(_QWORD *)(v5 + 8);
      *(_QWORD *)(v5 + 8) = v7;
      *(_QWORD *)(v7 + 16) = 0;
      *(_QWORD *)(v11 + 16) = v7;
      while ( *(_QWORD *)(v9 + 40) )
        v9 = *(_QWORD *)(v9 + 40);
      v12 = operator new(0x30u);
      v12[1] = 16;
      v12[3] = 0;
      *v12 = &std::_Node_if::`vftable';
      v12[4] = v7;
      v12[5] = 0;
      *(_QWORD *)(v9 + 40) = v12;
      v12[2] = v10;
      result = *(_QWORD *)(v9 + 40);
      *(_QWORD *)(v10 + 24) = result;
    }
    while ( *v2 == 124 );
  }
  return result;
}

```

## disassembly

```asm
0x180021640  push    rbx
0x180021642  push    rbp
0x180021643  push    rsi
0x180021644  push    rdi
0x180021645  push    r13
0x180021647  push    r14
0x180021649  push    r15
0x18002164b  sub     rsp, 20h
0x18002164f  mov     r13, [rcx+40h]
0x180021653  lea     rdi, [rcx+70h]
0x180021657  mov     rbx, rcx
0x18002165a  call    ?_Alternative@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAA_NXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Alternative(void)
0x18002165f  test    al, al
0x180021661  jnz     short loc_18002168A
0x180021663  cmp     dword ptr [rdi], 7Ch ; '|'
0x180021666  jnz     loc_18002174D
0x18002166c  lea     rbp, [rbx+38h]
0x180021670  mov     edx, 8
0x180021675  mov     rcx, rbp
0x180021678  call    ?_New_node@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@AEAAPEAV_Node_base@2@W4_Node_type@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_New_node(std::_Node_type)
0x18002167d  mov     rdx, rax
0x180021680  mov     rcx, rbp
0x180021683  call    ?_End_group@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEAV_Node_base@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_End_group(std::_Node_base *)
0x180021688  jmp     short loc_18002168E
0x18002168a  lea     rbp, [rbx+38h]
0x18002168e  cmp     dword ptr [rdi], 7Ch ; '|'
0x180021691  jnz     loc_18002174D
0x180021697  mov     rdx, r13
0x18002169a  mov     rcx, rbp
0x18002169d  call    ?_Begin_if@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAPEAV_Node_base@2@PEAV32@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_Begin_if(std::_Node_base *)
0x1800216a2  mov     r14, rax
0x1800216a5  mov     rcx, rbx
0x1800216a8  call    ?_Next@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Next(void)
0x1800216ad  mov     rcx, rbx
0x1800216b0  call    ?_Alternative@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAA_NXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Alternative(void)
0x1800216b5  test    al, al
0x1800216b7  jnz     short loc_1800216D3
0x1800216b9  lea     rcx, [rbx+38h]
0x1800216bd  mov     edx, 8
0x1800216c2  call    ?_New_node@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@AEAAPEAV_Node_base@2@W4_Node_type@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_New_node(std::_Node_type)
0x1800216c7  lea     rcx, [rbx+38h]
0x1800216cb  mov     rdx, rax
0x1800216ce  call    ?_End_group@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEAV_Node_base@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_End_group(std::_Node_base *)
0x1800216d3  mov     rsi, [r13+10h]
0x1800216d7  mov     r15, [r14+10h]
0x1800216db  mov     qword ptr [r14+10h], 0
0x1800216e3  mov     rax, [rbp+8]
0x1800216e7  mov     [rbp+8], r14
0x1800216eb  mov     qword ptr [r14+10h], 0
0x1800216f3  mov     [rax+10h], r14
0x1800216f7  jmp     short loc_1800216FD
0x1800216f9  mov     rsi, [rsi+28h]
0x1800216fd  cmp     qword ptr [rsi+28h], 0
0x180021702  jnz     short loc_1800216F9
0x180021704  mov     ecx, 30h ; '0'; Size
0x180021709  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002170e  lea     rcx, ??_7_Node_if@std@@6B@; const std::_Node_if::`vftable'
0x180021715  mov     qword ptr [rax+8], 10h
0x18002171d  mov     qword ptr [rax+18h], 0
0x180021725  mov     [rax], rcx
0x180021728  mov     [rax+20h], r14
0x18002172c  mov     qword ptr [rax+28h], 0
0x180021734  mov     [rsi+28h], rax
0x180021738  mov     [rax+10h], r15
0x18002173c  mov     rax, [rsi+28h]
0x180021740  mov     [r15+18h], rax
0x180021744  cmp     dword ptr [rdi], 7Ch ; '|'
0x180021747  jz      loc_1800216A5
0x18002174d  add     rsp, 20h
0x180021751  pop     r15
0x180021753  pop     r14
0x180021755  pop     r13
0x180021757  pop     rdi
0x180021758  pop     rsi
0x180021759  pop     rbp
0x18002175a  pop     rbx
0x18002175b  retn
```
