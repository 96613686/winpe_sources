# std::list<CommandSet,std::allocator<CommandSet>>::sort(void)

- ea: `0x18000c744`
- end: `0x18000ca06`
- name: `?sort@?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAAXXZ`
- size: `706`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000be6c`

## callees

- `0x180001bc8`
- `0x180002230`
- `0x180006d20`
- `0x18000c0d0`
- `0x18000c360`
- `0x18000c744`
- `0x18000ccc0`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000c967`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000c967`

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
0x18000c744  push    rbp
0x18000c746  push    rbx
0x18000c747  push    rsi
0x18000c748  push    rdi
0x18000c749  push    r12
0x18000c74b  push    r13
0x18000c74d  push    r14
0x18000c74f  push    r15
0x18000c751  lea     rbp, [rsp-0F8h]
0x18000c759  sub     rsp, 1F8h
0x18000c760  mov     rax, cs:__security_cookie
0x18000c767  xor     rax, rsp
0x18000c76a  mov     [rbp+130h+var_50], rax
0x18000c771  mov     rsi, rcx
0x18000c774  cmp     qword ptr [rcx+8], 2
0x18000c779  jb      loc_18000C9E2
0x18000c77f  xor     edi, edi
0x18000c781  mov     [rsp+230h+var_1F8], rdi
0x18000c786  xor     r8d, r8d
0x18000c789  xor     edx, edx
0x18000c78b  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *)
0x18000c790  mov     r15, rax
0x18000c793  mov     [rsp+230h+var_200], rax
0x18000c798  lea     r14, ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; std::list<CommandSet>::~list<CommandSet>(void)
0x18000c79f  mov     [rsp+230h+var_210], r14; void (*)(void *)
0x18000c7a4  lea     r9, ??0?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x18000c7ab  lea     edx, [rdi+10h]; unsigned __int64
0x18000c7ae  lea     r8d, [rdi+1Ah]; unsigned __int64
0x18000c7b2  lea     rcx, [rsp+230h+var_1F0]; void *
0x18000c7b7  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18000c7bc  nop
0x18000c7bd  xor     ebx, ebx
0x18000c7bf  mov     r13, 38E38E38E38E38Dh
0x18000c7c9  mov     rcx, [rsi+8]
0x18000c7cd  test    rcx, rcx
0x18000c7d0  jz      loc_18000C914
0x18000c7d6  mov     rax, [rsi]
0x18000c7d9  mov     rdx, [rax]
0x18000c7dc  mov     r8, [rdx]
0x18000c7df  mov     r9, [r15]
0x18000c7e2  lea     rax, [rsp+230h+var_200]
0x18000c7e7  cmp     rax, rsi
0x18000c7ea  jz      short loc_18000C80C
0x18000c7ec  mov     rax, r13
0x18000c7ef  sub     rax, rdi
0x18000c7f2  cmp     rax, 1
0x18000c7f6  jb      loc_18000C960
0x18000c7fc  inc     rdi
0x18000c7ff  mov     [rsp+230h+var_1F8], rdi
0x18000c804  lea     rax, [rcx-1]
0x18000c808  mov     [rsi+8], rax
0x18000c80c  mov     rax, [rdx+8]
0x18000c810  mov     [rax], r8
0x18000c813  mov     rax, [r8+8]
0x18000c817  mov     [rax], r9
0x18000c81a  mov     rax, [r9+8]
0x18000c81e  mov     [rax], rdx
0x18000c821  mov     rcx, [r9+8]
0x18000c825  mov     rax, [r8+8]
0x18000c829  mov     [r9+8], rax
0x18000c82d  mov     rax, [rdx+8]
0x18000c831  mov     [r8+8], rax
0x18000c835  mov     [rdx+8], rcx
0x18000c839  xor     r14d, r14d
0x18000c83c  test    rbx, rbx
0x18000c83f  jz      short loc_18000C8A9
0x18000c841  mov     rax, r14
0x18000c844  shl     rax, 4
0x18000c848  cmp     [rsp+rax+230h+var_1E8], 0
0x18000c84e  jz      short loc_18000C8A9
0x18000c850  lea     r12, [rsp+230h+var_1F0]
0x18000c855  add     r12, rax
0x18000c858  lea     rdx, [rsp+230h+var_200]
0x18000c85d  mov     rcx, r12
0x18000c860  call    ?merge@?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAAXAEAV12@@Z; std::list<CommandSet>::merge(std::list<CommandSet> &)
0x18000c865  lea     rax, [rsp+230h+var_200]
0x18000c86a  cmp     r12, rax
0x18000c86d  jz      short loc_18000C897
0x18000c86f  mov     r15, [r12]
0x18000c873  mov     rax, [rsp+230h+var_200]
0x18000c878  mov     [r12], rax
0x18000c87c  mov     [rsp+230h+var_200], r15
0x18000c881  mov     rdi, [r12+8]
0x18000c886  mov     rax, [rsp+230h+var_1F8]
0x18000c88b  mov     [r12+8], rax
0x18000c890  mov     [rsp+230h+var_1F8], rdi
0x18000c895  jmp     short loc_18000C8A1
0x18000c897  mov     rdi, [rsp+230h+var_1F8]
0x18000c89c  mov     r15, [rsp+230h+var_200]
0x18000c8a1  inc     r14
0x18000c8a4  cmp     r14, rbx
0x18000c8a7  jb      short loc_18000C841
0x18000c8a9  mov     rax, r14
0x18000c8ac  shl     rax, 4
0x18000c8b0  lea     rcx, [rsp+230h+var_1F0]
0x18000c8b5  add     rcx, rax
0x18000c8b8  cmp     r14, 19h
0x18000c8bc  jnz     short loc_18000C8DB
0x18000c8be  add     rcx, 0FFFFFFFFFFFFFFF0h
0x18000c8c2  lea     rdx, [rsp+230h+var_200]
0x18000c8c7  call    ?merge@?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAAXAEAV12@@Z; std::list<CommandSet>::merge(std::list<CommandSet> &)
0x18000c8cc  mov     rdi, [rsp+230h+var_1F8]
0x18000c8d1  mov     r15, [rsp+230h+var_200]
0x18000c8d6  jmp     loc_18000C7C9
0x18000c8db  lea     rax, [rsp+230h+var_200]
0x18000c8e0  cmp     rcx, rax
0x18000c8e3  jz      short loc_18000C903
0x18000c8e5  mov     rax, [rcx]
0x18000c8e8  mov     [rcx], r15
0x18000c8eb  mov     r15, rax
0x18000c8ee  mov     [rsp+230h+var_200], rax
0x18000c8f3  mov     rax, [rcx+8]
0x18000c8f7  mov     [rcx+8], rdi
0x18000c8fb  mov     rdi, rax
0x18000c8fe  mov     [rsp+230h+var_1F8], rax
0x18000c903  cmp     r14, rbx
0x18000c906  jnz     loc_18000C7C9
0x18000c90c  inc     rbx
0x18000c90f  jmp     loc_18000C7C9
0x18000c914  mov     edi, 1
0x18000c919  cmp     rbx, rdi
0x18000c91c  jbe     short loc_18000C93E
0x18000c91e  mov     rax, rdi
0x18000c921  shl     rax, 4
0x18000c925  lea     rcx, [rsp+230h+var_1F0]
0x18000c92a  add     rcx, rax
0x18000c92d  lea     rdx, [rcx-10h]
0x18000c931  call    ?merge@?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAAXAEAV12@@Z; std::list<CommandSet>::merge(std::list<CommandSet> &)
0x18000c936  inc     rdi
0x18000c939  cmp     rdi, rbx
0x18000c93c  jb      short loc_18000C91E
0x18000c93e  add     rbx, rbx
0x18000c941  lea     rcx, [rsp+rbx*8+230h+var_200]
0x18000c946  cmp     rsi, rcx
0x18000c949  jz      short loc_18000C9BD
0x18000c94b  mov     rdx, [rcx+8]
0x18000c94f  test    rdx, rdx
0x18000c952  jz      short loc_18000C9BD
0x18000c954  mov     r8, [rsi+8]
0x18000c958  sub     r13, r8
0x18000c95b  cmp     r13, rdx
0x18000c95e  jnb     short loc_18000C974
0x18000c960  lea     rcx, aListTTooLong; "list<T> too long"
0x18000c967  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000c974  mov     rax, [rsi]
0x18000c977  mov     r10, [rax]
0x18000c97a  mov     r11, [rcx]
0x18000c97d  mov     rbx, [r11]
0x18000c980  lea     rax, [rdx+r8]
0x18000c984  mov     [rsi+8], rax
0x18000c988  mov     qword ptr [rcx+8], 0
0x18000c990  mov     rax, [rbx+8]
0x18000c994  mov     [rax], r11
0x18000c997  mov     rax, [r11+8]
0x18000c99b  mov     [rax], r10
0x18000c99e  mov     rax, [r10+8]
0x18000c9a2  mov     [rax], rbx
0x18000c9a5  mov     rcx, [r10+8]
0x18000c9a9  mov     rax, [r11+8]
0x18000c9ad  mov     [r10+8], rax
0x18000c9b1  mov     rax, [rbx+8]
0x18000c9b5  mov     [r11+8], rax
0x18000c9b9  mov     [rbx+8], rcx
0x18000c9bd  lea     r9, ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x18000c9c4  mov     edx, 10h; unsigned __int64
0x18000c9c9  lea     r8d, [rdx+0Ah]; unsigned __int64
0x18000c9cd  lea     rcx, [rsp+230h+var_1F0]; void *
0x18000c9d2  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000c9d7  nop
0x18000c9d8  lea     rcx, [rsp+230h+var_200]; void *
0x18000c9dd  call    ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; std::list<CommandSet>::~list<CommandSet>(void)
0x18000c9e2  mov     rcx, [rbp+130h+var_50]
0x18000c9e9  xor     rcx, rsp; StackCookie
0x18000c9ec  call    __security_check_cookie
0x18000c9f1  add     rsp, 1F8h
0x18000c9f8  pop     r15
0x18000c9fa  pop     r14
0x18000c9fc  pop     r13
0x18000c9fe  pop     r12
0x18000ca00  pop     rdi
0x18000ca01  pop     rsi
0x18000ca02  pop     rbx
0x18000ca03  pop     rbp
0x18000ca04  retn
```
