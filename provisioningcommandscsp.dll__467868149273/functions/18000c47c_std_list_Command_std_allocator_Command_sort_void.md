# std::list<Command,std::allocator<Command>>::sort(void)

- ea: `0x18000c47c`
- end: `0x18000c73e`
- name: `?sort@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXXZ`
- size: `706`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000bce8`

## callees

- `0x180001bc8`
- `0x180002230`
- `0x180007a08`
- `0x18000a490`
- `0x18000c230`
- `0x18000c47c`
- `0x18000ccc0`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000c69f`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000c69f`

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
0x18000c47c  push    rbp
0x18000c47e  push    rbx
0x18000c47f  push    rsi
0x18000c480  push    rdi
0x18000c481  push    r12
0x18000c483  push    r13
0x18000c485  push    r14
0x18000c487  push    r15
0x18000c489  lea     rbp, [rsp-0F8h]
0x18000c491  sub     rsp, 1F8h
0x18000c498  mov     rax, cs:__security_cookie
0x18000c49f  xor     rax, rsp
0x18000c4a2  mov     [rbp+130h+var_50], rax
0x18000c4a9  mov     rsi, rcx
0x18000c4ac  cmp     qword ptr [rcx+8], 2
0x18000c4b1  jb      loc_18000C71A
0x18000c4b7  xor     edi, edi
0x18000c4b9  mov     [rsp+230h+var_1F8], rdi
0x18000c4be  xor     r8d, r8d
0x18000c4c1  xor     edx, edx
0x18000c4c3  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommand@@V?$allocator@UCommand@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *)
0x18000c4c8  mov     r15, rax
0x18000c4cb  mov     [rsp+230h+var_200], rax
0x18000c4d0  lea     r14, ??1?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ; std::list<Command>::~list<Command>(void)
0x18000c4d7  mov     [rsp+230h+var_210], r14; void (*)(void *)
0x18000c4dc  lea     r9, ??0?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x18000c4e3  lea     edx, [rdi+10h]; unsigned __int64
0x18000c4e6  lea     r8d, [rdi+1Ah]; unsigned __int64
0x18000c4ea  lea     rcx, [rsp+230h+var_1F0]; void *
0x18000c4ef  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18000c4f4  nop
0x18000c4f5  xor     ebx, ebx
0x18000c4f7  mov     r13, 1FFFFFFFFFFFFFEh
0x18000c501  mov     rcx, [rsi+8]
0x18000c505  test    rcx, rcx
0x18000c508  jz      loc_18000C64C
0x18000c50e  mov     rax, [rsi]
0x18000c511  mov     rdx, [rax]
0x18000c514  mov     r8, [rdx]
0x18000c517  mov     r9, [r15]
0x18000c51a  lea     rax, [rsp+230h+var_200]
0x18000c51f  cmp     rax, rsi
0x18000c522  jz      short loc_18000C544
0x18000c524  mov     rax, r13
0x18000c527  sub     rax, rdi
0x18000c52a  cmp     rax, 1
0x18000c52e  jb      loc_18000C698
0x18000c534  inc     rdi
0x18000c537  mov     [rsp+230h+var_1F8], rdi
0x18000c53c  lea     rax, [rcx-1]
0x18000c540  mov     [rsi+8], rax
0x18000c544  mov     rax, [rdx+8]
0x18000c548  mov     [rax], r8
0x18000c54b  mov     rax, [r8+8]
0x18000c54f  mov     [rax], r9
0x18000c552  mov     rax, [r9+8]
0x18000c556  mov     [rax], rdx
0x18000c559  mov     rcx, [r9+8]
0x18000c55d  mov     rax, [r8+8]
0x18000c561  mov     [r9+8], rax
0x18000c565  mov     rax, [rdx+8]
0x18000c569  mov     [r8+8], rax
0x18000c56d  mov     [rdx+8], rcx
0x18000c571  xor     r14d, r14d
0x18000c574  test    rbx, rbx
0x18000c577  jz      short loc_18000C5E1
0x18000c579  mov     rax, r14
0x18000c57c  shl     rax, 4
0x18000c580  cmp     [rsp+rax+230h+var_1E8], 0
0x18000c586  jz      short loc_18000C5E1
0x18000c588  lea     r12, [rsp+230h+var_1F0]
0x18000c58d  add     r12, rax
0x18000c590  lea     rdx, [rsp+230h+var_200]
0x18000c595  mov     rcx, r12
0x18000c598  call    ?merge@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXAEAV12@@Z; std::list<Command>::merge(std::list<Command> &)
0x18000c59d  lea     rax, [rsp+230h+var_200]
0x18000c5a2  cmp     r12, rax
0x18000c5a5  jz      short loc_18000C5CF
0x18000c5a7  mov     r15, [r12]
0x18000c5ab  mov     rax, [rsp+230h+var_200]
0x18000c5b0  mov     [r12], rax
0x18000c5b4  mov     [rsp+230h+var_200], r15
0x18000c5b9  mov     rdi, [r12+8]
0x18000c5be  mov     rax, [rsp+230h+var_1F8]
0x18000c5c3  mov     [r12+8], rax
0x18000c5c8  mov     [rsp+230h+var_1F8], rdi
0x18000c5cd  jmp     short loc_18000C5D9
0x18000c5cf  mov     rdi, [rsp+230h+var_1F8]
0x18000c5d4  mov     r15, [rsp+230h+var_200]
0x18000c5d9  inc     r14
0x18000c5dc  cmp     r14, rbx
0x18000c5df  jb      short loc_18000C579
0x18000c5e1  mov     rax, r14
0x18000c5e4  shl     rax, 4
0x18000c5e8  lea     rcx, [rsp+230h+var_1F0]
0x18000c5ed  add     rcx, rax
0x18000c5f0  cmp     r14, 19h
0x18000c5f4  jnz     short loc_18000C613
0x18000c5f6  add     rcx, 0FFFFFFFFFFFFFFF0h
0x18000c5fa  lea     rdx, [rsp+230h+var_200]
0x18000c5ff  call    ?merge@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXAEAV12@@Z; std::list<Command>::merge(std::list<Command> &)
0x18000c604  mov     rdi, [rsp+230h+var_1F8]
0x18000c609  mov     r15, [rsp+230h+var_200]
0x18000c60e  jmp     loc_18000C501
0x18000c613  lea     rax, [rsp+230h+var_200]
0x18000c618  cmp     rcx, rax
0x18000c61b  jz      short loc_18000C63B
0x18000c61d  mov     rax, [rcx]
0x18000c620  mov     [rcx], r15
0x18000c623  mov     r15, rax
0x18000c626  mov     [rsp+230h+var_200], rax
0x18000c62b  mov     rax, [rcx+8]
0x18000c62f  mov     [rcx+8], rdi
0x18000c633  mov     rdi, rax
0x18000c636  mov     [rsp+230h+var_1F8], rax
0x18000c63b  cmp     r14, rbx
0x18000c63e  jnz     loc_18000C501
0x18000c644  inc     rbx
0x18000c647  jmp     loc_18000C501
0x18000c64c  mov     edi, 1
0x18000c651  cmp     rbx, rdi
0x18000c654  jbe     short loc_18000C676
0x18000c656  mov     rax, rdi
0x18000c659  shl     rax, 4
0x18000c65d  lea     rcx, [rsp+230h+var_1F0]
0x18000c662  add     rcx, rax
0x18000c665  lea     rdx, [rcx-10h]
0x18000c669  call    ?merge@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXAEAV12@@Z; std::list<Command>::merge(std::list<Command> &)
0x18000c66e  inc     rdi
0x18000c671  cmp     rdi, rbx
0x18000c674  jb      short loc_18000C656
0x18000c676  add     rbx, rbx
0x18000c679  lea     rcx, [rsp+rbx*8+230h+var_200]
0x18000c67e  cmp     rsi, rcx
0x18000c681  jz      short loc_18000C6F5
0x18000c683  mov     rdx, [rcx+8]
0x18000c687  test    rdx, rdx
0x18000c68a  jz      short loc_18000C6F5
0x18000c68c  mov     r8, [rsi+8]
0x18000c690  sub     r13, r8
0x18000c693  cmp     r13, rdx
0x18000c696  jnb     short loc_18000C6AC
0x18000c698  lea     rcx, aListTTooLong; "list<T> too long"
0x18000c69f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000c6ac  mov     rax, [rsi]
0x18000c6af  mov     r10, [rax]
0x18000c6b2  mov     r11, [rcx]
0x18000c6b5  mov     rbx, [r11]
0x18000c6b8  lea     rax, [rdx+r8]
0x18000c6bc  mov     [rsi+8], rax
0x18000c6c0  mov     qword ptr [rcx+8], 0
0x18000c6c8  mov     rax, [rbx+8]
0x18000c6cc  mov     [rax], r11
0x18000c6cf  mov     rax, [r11+8]
0x18000c6d3  mov     [rax], r10
0x18000c6d6  mov     rax, [r10+8]
0x18000c6da  mov     [rax], rbx
0x18000c6dd  mov     rcx, [r10+8]
0x18000c6e1  mov     rax, [r11+8]
0x18000c6e5  mov     [r10+8], rax
0x18000c6e9  mov     rax, [rbx+8]
0x18000c6ed  mov     [r11+8], rax
0x18000c6f1  mov     [rbx+8], rcx
0x18000c6f5  lea     r9, ??1?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x18000c6fc  mov     edx, 10h; unsigned __int64
0x18000c701  lea     r8d, [rdx+0Ah]; unsigned __int64
0x18000c705  lea     rcx, [rsp+230h+var_1F0]; void *
0x18000c70a  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000c70f  nop
0x18000c710  lea     rcx, [rsp+230h+var_200]; void *
0x18000c715  call    ??1?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ; std::list<Command>::~list<Command>(void)
0x18000c71a  mov     rcx, [rbp+130h+var_50]
0x18000c721  xor     rcx, rsp; StackCookie
0x18000c724  call    __security_check_cookie
0x18000c729  add     rsp, 1F8h
0x18000c730  pop     r15
0x18000c732  pop     r14
0x18000c734  pop     r13
0x18000c736  pop     r12
0x18000c738  pop     rdi
0x18000c739  pop     rsi
0x18000c73a  pop     rbx
0x18000c73b  pop     rbp
0x18000c73c  retn
```
