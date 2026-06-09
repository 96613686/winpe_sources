# std::list<Command,std::allocator<Command>>::sort(void)

- ea: `0x140009c08`
- end: `0x140009ec3`
- name: `?sort@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXXZ`
- size: `699`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140008f54`

## callees

- `0x140002228`
- `0x1400022f0`
- `0x140007c70`
- `0x140007d20`
- `0x1400098e8`
- `0x140009c08`
- `0x14000a370`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140009e2b`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140009e2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall std::list<Command>::sort(__int64 **a1)
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
    v3 = (_QWORD *)std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0(a1, 0, 0);
    v24 = v3;
    `eh vector constructor iterator'(
      v26,
      0x10u,
      0x1Au,
      std::list<Command>::list<Command>,
      std::list<Command>::~list<Command>);
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
        if ( v2 == 0x1FFFFFFFFFFFFFELL )
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
        std::list<Command>::merge(&v26[v11], &v24);
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
        std::list<Command>::merge(v13 - 2, &v24);
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
      std::list<Command>::merge(&v26[16 * j], &v26[16 * j - 16]);
    v17 = &(&v24)[2 * v4];
    if ( a1 != v17 )
    {
      v18 = (unsigned __int64)v17[1];
      if ( v18 )
      {
        v19 = a1[1];
        if ( 0x1FFFFFFFFFFFFFELL - (__int64)v19 < v18 )
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
    `eh vector destructor iterator'(v26, 0x10u, 0x1Au, std::list<Command>::~list<Command>);
    std::list<Command>::~list<Command>(&v24);
  }
}

```

## disassembly

```asm
0x140009c08  push    rbp
0x140009c0a  push    rbx
0x140009c0b  push    rsi
0x140009c0c  push    rdi
0x140009c0d  push    r12
0x140009c0f  push    r13
0x140009c11  push    r14
0x140009c13  push    r15
0x140009c15  lea     rbp, [rsp-0F8h]
0x140009c1d  sub     rsp, 1F8h
0x140009c24  mov     rax, cs:__security_cookie
0x140009c2b  xor     rax, rsp
0x140009c2e  mov     [rbp+130h+var_50], rax
0x140009c35  mov     rsi, rcx
0x140009c38  cmp     qword ptr [rcx+8], 2
0x140009c3d  jb      loc_140009EA0
0x140009c43  xor     edi, edi
0x140009c45  mov     [rsp+230h+var_1F8], rdi
0x140009c4a  xor     r8d, r8d
0x140009c4d  xor     edx, edx
0x140009c4f  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommand@@V?$allocator@UCommand@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *)
0x140009c54  mov     r15, rax
0x140009c57  mov     [rsp+230h+var_200], rax
0x140009c5c  lea     r14, ??1?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ; std::list<Command>::~list<Command>(void)
0x140009c63  mov     [rsp+230h+var_210], r14; void (*)(void *)
0x140009c68  lea     r9, ??0?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x140009c6f  lea     edx, [rdi+10h]; unsigned __int64
0x140009c72  lea     r8d, [rdi+1Ah]; unsigned __int64
0x140009c76  lea     rcx, [rsp+230h+var_1F0]; void *
0x140009c7b  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x140009c80  nop
0x140009c81  xor     ebx, ebx
0x140009c83  mov     r13, 1FFFFFFFFFFFFFEh
0x140009c8d  mov     rcx, [rsi+8]
0x140009c91  test    rcx, rcx
0x140009c94  jz      loc_140009DD8
0x140009c9a  mov     rax, [rsi]
0x140009c9d  mov     rdx, [rax]
0x140009ca0  mov     r8, [rdx]
0x140009ca3  mov     r9, [r15]
0x140009ca6  lea     rax, [rsp+230h+var_200]
0x140009cab  cmp     rax, rsi
0x140009cae  jz      short loc_140009CD0
0x140009cb0  mov     rax, r13
0x140009cb3  sub     rax, rdi
0x140009cb6  cmp     rax, 1
0x140009cba  jb      loc_140009E24
0x140009cc0  inc     rdi
0x140009cc3  mov     [rsp+230h+var_1F8], rdi
0x140009cc8  lea     rax, [rcx-1]
0x140009ccc  mov     [rsi+8], rax
0x140009cd0  mov     rax, [rdx+8]
0x140009cd4  mov     [rax], r8
0x140009cd7  mov     rax, [r8+8]
0x140009cdb  mov     [rax], r9
0x140009cde  mov     rax, [r9+8]
0x140009ce2  mov     [rax], rdx
0x140009ce5  mov     rcx, [r9+8]
0x140009ce9  mov     rax, [r8+8]
0x140009ced  mov     [r9+8], rax
0x140009cf1  mov     rax, [rdx+8]
0x140009cf5  mov     [r8+8], rax
0x140009cf9  mov     [rdx+8], rcx
0x140009cfd  xor     r14d, r14d
0x140009d00  test    rbx, rbx
0x140009d03  jz      short loc_140009D6D
0x140009d05  mov     rax, r14
0x140009d08  shl     rax, 4
0x140009d0c  cmp     [rsp+rax+230h+var_1E8], 0
0x140009d12  jz      short loc_140009D6D
0x140009d14  lea     r12, [rsp+230h+var_1F0]
0x140009d19  add     r12, rax
0x140009d1c  lea     rdx, [rsp+230h+var_200]
0x140009d21  mov     rcx, r12
0x140009d24  call    ?merge@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXAEAV12@@Z; std::list<Command>::merge(std::list<Command> &)
0x140009d29  lea     rax, [rsp+230h+var_200]
0x140009d2e  cmp     r12, rax
0x140009d31  jz      short loc_140009D5B
0x140009d33  mov     r15, [r12]
0x140009d37  mov     rax, [rsp+230h+var_200]
0x140009d3c  mov     [r12], rax
0x140009d40  mov     [rsp+230h+var_200], r15
0x140009d45  mov     rdi, [r12+8]
0x140009d4a  mov     rax, [rsp+230h+var_1F8]
0x140009d4f  mov     [r12+8], rax
0x140009d54  mov     [rsp+230h+var_1F8], rdi
0x140009d59  jmp     short loc_140009D65
0x140009d5b  mov     rdi, [rsp+230h+var_1F8]
0x140009d60  mov     r15, [rsp+230h+var_200]
0x140009d65  inc     r14
0x140009d68  cmp     r14, rbx
0x140009d6b  jb      short loc_140009D05
0x140009d6d  mov     rax, r14
0x140009d70  shl     rax, 4
0x140009d74  lea     rcx, [rsp+230h+var_1F0]
0x140009d79  add     rcx, rax
0x140009d7c  cmp     r14, 19h
0x140009d80  jnz     short loc_140009D9F
0x140009d82  add     rcx, 0FFFFFFFFFFFFFFF0h
0x140009d86  lea     rdx, [rsp+230h+var_200]
0x140009d8b  call    ?merge@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXAEAV12@@Z; std::list<Command>::merge(std::list<Command> &)
0x140009d90  mov     rdi, [rsp+230h+var_1F8]
0x140009d95  mov     r15, [rsp+230h+var_200]
0x140009d9a  jmp     loc_140009C8D
0x140009d9f  lea     rax, [rsp+230h+var_200]
0x140009da4  cmp     rcx, rax
0x140009da7  jz      short loc_140009DC7
0x140009da9  mov     rax, [rcx]
0x140009dac  mov     [rcx], r15
0x140009daf  mov     r15, rax
0x140009db2  mov     [rsp+230h+var_200], rax
0x140009db7  mov     rax, [rcx+8]
0x140009dbb  mov     [rcx+8], rdi
0x140009dbf  mov     rdi, rax
0x140009dc2  mov     [rsp+230h+var_1F8], rax
0x140009dc7  cmp     r14, rbx
0x140009dca  jnz     loc_140009C8D
0x140009dd0  inc     rbx
0x140009dd3  jmp     loc_140009C8D
0x140009dd8  mov     edi, 1
0x140009ddd  cmp     rbx, rdi
0x140009de0  jbe     short loc_140009E02
0x140009de2  mov     rax, rdi
0x140009de5  shl     rax, 4
0x140009de9  lea     rcx, [rsp+230h+var_1F0]
0x140009dee  add     rcx, rax
0x140009df1  lea     rdx, [rcx-10h]
0x140009df5  call    ?merge@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXAEAV12@@Z; std::list<Command>::merge(std::list<Command> &)
0x140009dfa  inc     rdi
0x140009dfd  cmp     rdi, rbx
0x140009e00  jb      short loc_140009DE2
0x140009e02  add     rbx, rbx
0x140009e05  lea     rcx, [rsp+rbx*8+230h+var_200]
0x140009e0a  cmp     rsi, rcx
0x140009e0d  jz      short loc_140009E7B
0x140009e0f  mov     rdx, [rcx+8]
0x140009e13  test    rdx, rdx
0x140009e16  jz      short loc_140009E7B
0x140009e18  mov     r8, [rsi+8]
0x140009e1c  sub     r13, r8
0x140009e1f  cmp     r13, rdx
0x140009e22  jnb     short loc_140009E32
0x140009e24  lea     rcx, aListTTooLong; "list<T> too long"
0x140009e2b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x140009e32  mov     rax, [rsi]
0x140009e35  mov     r10, [rax]
0x140009e38  mov     r11, [rcx]
0x140009e3b  mov     rbx, [r11]
0x140009e3e  lea     rax, [rdx+r8]
0x140009e42  mov     [rsi+8], rax
0x140009e46  mov     qword ptr [rcx+8], 0
0x140009e4e  mov     rax, [rbx+8]
0x140009e52  mov     [rax], r11
0x140009e55  mov     rax, [r11+8]
0x140009e59  mov     [rax], r10
0x140009e5c  mov     rax, [r10+8]
0x140009e60  mov     [rax], rbx
0x140009e63  mov     rcx, [r10+8]
0x140009e67  mov     rax, [r11+8]
0x140009e6b  mov     [r10+8], rax
0x140009e6f  mov     rax, [rbx+8]
0x140009e73  mov     [r11+8], rax
0x140009e77  mov     [rbx+8], rcx
0x140009e7b  lea     r9, ??1?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x140009e82  mov     edx, 10h; unsigned __int64
0x140009e87  lea     r8d, [rdx+0Ah]; unsigned __int64
0x140009e8b  lea     rcx, [rsp+230h+var_1F0]; void *
0x140009e90  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x140009e95  nop
0x140009e96  lea     rcx, [rsp+230h+var_200]; void *
0x140009e9b  call    ??1?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ; std::list<Command>::~list<Command>(void)
0x140009ea0  mov     rcx, [rbp+130h+var_50]
0x140009ea7  xor     rcx, rsp; StackCookie
0x140009eaa  call    __security_check_cookie
0x140009eaf  add     rsp, 1F8h
0x140009eb6  pop     r15
0x140009eb8  pop     r14
0x140009eba  pop     r13
0x140009ebc  pop     r12
0x140009ebe  pop     rdi
0x140009ebf  pop     rsi
0x140009ec0  pop     rbx
0x140009ec1  pop     rbp
0x140009ec2  retn
```
