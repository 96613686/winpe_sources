# std::list<CommandSet,std::allocator<CommandSet>>::sort(void)

- ea: `0x140009ecc`
- end: `0x14000a187`
- name: `?sort@?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAAXXZ`
- size: `699`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400090ec`

## callees

- `0x140002228`
- `0x1400022f0`
- `0x140003560`
- `0x140009328`
- `0x140009af4`
- `0x140009ecc`
- `0x14000a370`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000a0ef`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000a0ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall std::list<CommandSet>::sort(__int64 **a1)
{
  __int64 v2; // rdi
  _QWORD *v3; // r15
  unsigned __int64 v4; // rbx
  __int64 *v5; // rcx
  __int64 *v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rcx
  unsigned __int64 i; // r14
  __int64 v11; // rax
  _QWORD *v12; // r12
  _QWORD *v13; // rcx
  _QWORD *v14; // rax
  __int64 v15; // rax
  unsigned __int64 j; // rdi
  __int64 **v17; // rcx
  unsigned __int64 v18; // rdx
  __int64 *v19; // r8
  __int64 v20; // r10
  __int64 *v21; // r11
  __int64 v22; // rbx
  __int64 v23; // rcx
  _QWORD *v24; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h]
  _BYTE v26[416]; // [rsp+40h] [rbp-C0h] BYREF

  if ( (unsigned __int64)a1[1] >= 2 )
  {
    v2 = 0;
    v25 = 0;
    v3 = (_QWORD *)std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(a1, 0, 0);
    v24 = v3;
    `eh vector constructor iterator'(
      v26,
      0x10u,
      0x1Au,
      std::list<CommandSet>::list<CommandSet>,
      std::list<CommandSet>::~list<CommandSet>);
    v4 = 0;
    while ( 1 )
    {
      v5 = a1[1];
      if ( !v5 )
        break;
      v6 = (__int64 *)**a1;
      v7 = *v6;
      v8 = *v3;
      if ( &v24 != a1 )
      {
        if ( v2 == 0x38E38E38E38E38DLL )
          goto LABEL_24;
        v25 = ++v2;
        a1[1] = (__int64 *)((char *)v5 - 1);
      }
      *(_QWORD *)v6[1] = v7;
      **(_QWORD **)(v7 + 8) = v8;
      **(_QWORD **)(v8 + 8) = v6;
      v9 = *(_QWORD *)(v8 + 8);
      *(_QWORD *)(v8 + 8) = *(_QWORD *)(v7 + 8);
      *(_QWORD *)(v7 + 8) = v6[1];
      v6[1] = v9;
      for ( i = 0; i < v4; ++i )
      {
        v11 = 16 * i;
        if ( !*(_QWORD *)&v26[16 * i + 8] )
          break;
        v12 = &v26[v11];
        std::list<CommandSet>::merge(&v26[v11], &v24);
        if ( v12 == &v24 )
        {
          v2 = v25;
          v3 = v24;
        }
        else
        {
          v3 = (_QWORD *)*v12;
          *v12 = v24;
          v24 = v3;
          v2 = v12[1];
          v12[1] = v25;
          v25 = v2;
        }
      }
      v13 = &v26[16 * i];
      if ( i == 25 )
      {
        std::list<CommandSet>::merge(v13 - 2, &v24);
        v2 = v25;
        v3 = v24;
      }
      else
      {
        if ( v13 != &v24 )
        {
          v14 = (_QWORD *)*v13;
          *v13 = v3;
          v3 = v14;
          v24 = v14;
          v15 = v13[1];
          v13[1] = v2;
          v2 = v15;
          v25 = v15;
        }
        if ( i == v4 )
          ++v4;
      }
    }
    for ( j = 1; j < v4; ++j )
      std::list<CommandSet>::merge(&v26[16 * j], &v26[16 * j - 16]);
    v17 = &(&v24)[2 * v4];
    if ( a1 != v17 )
    {
      v18 = (unsigned __int64)v17[1];
      if ( v18 )
      {
        v19 = a1[1];
        if ( 0x38E38E38E38E38DLL - (__int64)v19 < v18 )
LABEL_24:
          std::_Xlength_error("list<T> too long");
        v20 = **a1;
        v21 = *v17;
        v22 = **v17;
        a1[1] = (__int64 *)((char *)v19 + v18);
        v17[1] = 0;
        **(_QWORD **)(v22 + 8) = v21;
        *(_QWORD *)v21[1] = v20;
        **(_QWORD **)(v20 + 8) = v22;
        v23 = *(_QWORD *)(v20 + 8);
        *(_QWORD *)(v20 + 8) = v21[1];
        v21[1] = *(_QWORD *)(v22 + 8);
        *(_QWORD *)(v22 + 8) = v23;
      }
    }
    `eh vector destructor iterator'(v26, 0x10u, 0x1Au, std::list<CommandSet>::~list<CommandSet>);
    std::list<CommandSet>::~list<CommandSet>(&v24);
  }
}

```

## disassembly

```asm
0x140009ecc  push    rbp
0x140009ece  push    rbx
0x140009ecf  push    rsi
0x140009ed0  push    rdi
0x140009ed1  push    r12
0x140009ed3  push    r13
0x140009ed5  push    r14
0x140009ed7  push    r15
0x140009ed9  lea     rbp, [rsp-0F8h]
0x140009ee1  sub     rsp, 1F8h
0x140009ee8  mov     rax, cs:__security_cookie
0x140009eef  xor     rax, rsp
0x140009ef2  mov     [rbp+130h+var_50], rax
0x140009ef9  mov     rsi, rcx
0x140009efc  cmp     qword ptr [rcx+8], 2
0x140009f01  jb      loc_14000A164
0x140009f07  xor     edi, edi
0x140009f09  mov     [rsp+230h+var_1F8], rdi
0x140009f0e  xor     r8d, r8d
0x140009f11  xor     edx, edx
0x140009f13  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *)
0x140009f18  mov     r15, rax
0x140009f1b  mov     [rsp+230h+var_200], rax
0x140009f20  lea     r14, ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; std::list<CommandSet>::~list<CommandSet>(void)
0x140009f27  mov     [rsp+230h+var_210], r14; void (*)(void *)
0x140009f2c  lea     r9, ??0?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x140009f33  lea     edx, [rdi+10h]; unsigned __int64
0x140009f36  lea     r8d, [rdi+1Ah]; unsigned __int64
0x140009f3a  lea     rcx, [rsp+230h+var_1F0]; void *
0x140009f3f  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x140009f44  nop
0x140009f45  xor     ebx, ebx
0x140009f47  mov     r13, 38E38E38E38E38Dh
0x140009f51  mov     rcx, [rsi+8]
0x140009f55  test    rcx, rcx
0x140009f58  jz      loc_14000A09C
0x140009f5e  mov     rax, [rsi]
0x140009f61  mov     rdx, [rax]
0x140009f64  mov     r8, [rdx]
0x140009f67  mov     r9, [r15]
0x140009f6a  lea     rax, [rsp+230h+var_200]
0x140009f6f  cmp     rax, rsi
0x140009f72  jz      short loc_140009F94
0x140009f74  mov     rax, r13
0x140009f77  sub     rax, rdi
0x140009f7a  cmp     rax, 1
0x140009f7e  jb      loc_14000A0E8
0x140009f84  inc     rdi
0x140009f87  mov     [rsp+230h+var_1F8], rdi
0x140009f8c  lea     rax, [rcx-1]
0x140009f90  mov     [rsi+8], rax
0x140009f94  mov     rax, [rdx+8]
0x140009f98  mov     [rax], r8
0x140009f9b  mov     rax, [r8+8]
0x140009f9f  mov     [rax], r9
0x140009fa2  mov     rax, [r9+8]
0x140009fa6  mov     [rax], rdx
0x140009fa9  mov     rcx, [r9+8]
0x140009fad  mov     rax, [r8+8]
0x140009fb1  mov     [r9+8], rax
0x140009fb5  mov     rax, [rdx+8]
0x140009fb9  mov     [r8+8], rax
0x140009fbd  mov     [rdx+8], rcx
0x140009fc1  xor     r14d, r14d
0x140009fc4  test    rbx, rbx
0x140009fc7  jz      short loc_14000A031
0x140009fc9  mov     rax, r14
0x140009fcc  shl     rax, 4
0x140009fd0  cmp     [rsp+rax+230h+var_1E8], 0
0x140009fd6  jz      short loc_14000A031
0x140009fd8  lea     r12, [rsp+230h+var_1F0]
0x140009fdd  add     r12, rax
0x140009fe0  lea     rdx, [rsp+230h+var_200]
0x140009fe5  mov     rcx, r12
0x140009fe8  call    ?merge@?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAAXAEAV12@@Z; std::list<CommandSet>::merge(std::list<CommandSet> &)
0x140009fed  lea     rax, [rsp+230h+var_200]
0x140009ff2  cmp     r12, rax
0x140009ff5  jz      short loc_14000A01F
0x140009ff7  mov     r15, [r12]
0x140009ffb  mov     rax, [rsp+230h+var_200]
0x14000a000  mov     [r12], rax
0x14000a004  mov     [rsp+230h+var_200], r15
0x14000a009  mov     rdi, [r12+8]
0x14000a00e  mov     rax, [rsp+230h+var_1F8]
0x14000a013  mov     [r12+8], rax
0x14000a018  mov     [rsp+230h+var_1F8], rdi
0x14000a01d  jmp     short loc_14000A029
0x14000a01f  mov     rdi, [rsp+230h+var_1F8]
0x14000a024  mov     r15, [rsp+230h+var_200]
0x14000a029  inc     r14
0x14000a02c  cmp     r14, rbx
0x14000a02f  jb      short loc_140009FC9
0x14000a031  mov     rax, r14
0x14000a034  shl     rax, 4
0x14000a038  lea     rcx, [rsp+230h+var_1F0]
0x14000a03d  add     rcx, rax
0x14000a040  cmp     r14, 19h
0x14000a044  jnz     short loc_14000A063
0x14000a046  add     rcx, 0FFFFFFFFFFFFFFF0h
0x14000a04a  lea     rdx, [rsp+230h+var_200]
0x14000a04f  call    ?merge@?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAAXAEAV12@@Z; std::list<CommandSet>::merge(std::list<CommandSet> &)
0x14000a054  mov     rdi, [rsp+230h+var_1F8]
0x14000a059  mov     r15, [rsp+230h+var_200]
0x14000a05e  jmp     loc_140009F51
0x14000a063  lea     rax, [rsp+230h+var_200]
0x14000a068  cmp     rcx, rax
0x14000a06b  jz      short loc_14000A08B
0x14000a06d  mov     rax, [rcx]
0x14000a070  mov     [rcx], r15
0x14000a073  mov     r15, rax
0x14000a076  mov     [rsp+230h+var_200], rax
0x14000a07b  mov     rax, [rcx+8]
0x14000a07f  mov     [rcx+8], rdi
0x14000a083  mov     rdi, rax
0x14000a086  mov     [rsp+230h+var_1F8], rax
0x14000a08b  cmp     r14, rbx
0x14000a08e  jnz     loc_140009F51
0x14000a094  inc     rbx
0x14000a097  jmp     loc_140009F51
0x14000a09c  mov     edi, 1
0x14000a0a1  cmp     rbx, rdi
0x14000a0a4  jbe     short loc_14000A0C6
0x14000a0a6  mov     rax, rdi
0x14000a0a9  shl     rax, 4
0x14000a0ad  lea     rcx, [rsp+230h+var_1F0]
0x14000a0b2  add     rcx, rax
0x14000a0b5  lea     rdx, [rcx-10h]
0x14000a0b9  call    ?merge@?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAAXAEAV12@@Z; std::list<CommandSet>::merge(std::list<CommandSet> &)
0x14000a0be  inc     rdi
0x14000a0c1  cmp     rdi, rbx
0x14000a0c4  jb      short loc_14000A0A6
0x14000a0c6  add     rbx, rbx
0x14000a0c9  lea     rcx, [rsp+rbx*8+230h+var_200]
0x14000a0ce  cmp     rsi, rcx
0x14000a0d1  jz      short loc_14000A13F
0x14000a0d3  mov     rdx, [rcx+8]
0x14000a0d7  test    rdx, rdx
0x14000a0da  jz      short loc_14000A13F
0x14000a0dc  mov     r8, [rsi+8]
0x14000a0e0  sub     r13, r8
0x14000a0e3  cmp     r13, rdx
0x14000a0e6  jnb     short loc_14000A0F6
0x14000a0e8  lea     rcx, aListTTooLong; "list<T> too long"
0x14000a0ef  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x14000a0f6  mov     rax, [rsi]
0x14000a0f9  mov     r10, [rax]
0x14000a0fc  mov     r11, [rcx]
0x14000a0ff  mov     rbx, [r11]
0x14000a102  lea     rax, [rdx+r8]
0x14000a106  mov     [rsi+8], rax
0x14000a10a  mov     qword ptr [rcx+8], 0
0x14000a112  mov     rax, [rbx+8]
0x14000a116  mov     [rax], r11
0x14000a119  mov     rax, [r11+8]
0x14000a11d  mov     [rax], r10
0x14000a120  mov     rax, [r10+8]
0x14000a124  mov     [rax], rbx
0x14000a127  mov     rcx, [r10+8]
0x14000a12b  mov     rax, [r11+8]
0x14000a12f  mov     [r10+8], rax
0x14000a133  mov     rax, [rbx+8]
0x14000a137  mov     [r11+8], rax
0x14000a13b  mov     [rbx+8], rcx
0x14000a13f  lea     r9, ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x14000a146  mov     edx, 10h; unsigned __int64
0x14000a14b  lea     r8d, [rdx+0Ah]; unsigned __int64
0x14000a14f  lea     rcx, [rsp+230h+var_1F0]; void *
0x14000a154  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14000a159  nop
0x14000a15a  lea     rcx, [rsp+230h+var_200]; void *
0x14000a15f  call    ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; std::list<CommandSet>::~list<CommandSet>(void)
0x14000a164  mov     rcx, [rbp+130h+var_50]
0x14000a16b  xor     rcx, rsp; StackCookie
0x14000a16e  call    __security_check_cookie
0x14000a173  add     rsp, 1F8h
0x14000a17a  pop     r15
0x14000a17c  pop     r14
0x14000a17e  pop     r13
0x14000a180  pop     r12
0x14000a182  pop     rdi
0x14000a183  pop     rsi
0x14000a184  pop     rbx
0x14000a185  pop     rbp
0x14000a186  retn
```
