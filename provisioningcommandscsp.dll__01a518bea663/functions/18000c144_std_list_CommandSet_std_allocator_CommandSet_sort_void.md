# std::list<CommandSet,std::allocator<CommandSet>>::sort(void)

- ea: `0x18000c144`
- end: `0x18000c3ff`
- name: `?sort@?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAAXXZ`
- size: `699`
- prototype: `void __fastcall(__int64 ***)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b7dc`

## callees

- `0x180001bb8`
- `0x180002220`
- `0x180006a00`
- `0x18000ba18`
- `0x18000bd6c`
- `0x18000c144`
- `0x18000c600`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000c367`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000c367`

## pseudocode

```c
void __fastcall std::list<CommandSet>::sort(__int64 ***a1)
{
  __int64 **v2; // rdi
  __int64 **v3; // r15
  unsigned __int64 v4; // rbx
  __int64 **v5; // rcx
  __int64 *v6; // rdx
  __int64 v7; // r8
  __int64 *v8; // r9
  __int64 v9; // rcx
  unsigned __int64 i; // r14
  __int64 v11; // rax
  __int64 ***v12; // r12
  __int64 ***v13; // rcx
  __int64 **v14; // rax
  __int64 **v15; // rax
  unsigned __int64 j; // rdi
  __int64 ***v17; // rcx
  unsigned __int64 v18; // rdx
  __int64 **v19; // r8
  __int64 *v20; // r10
  __int64 **v21; // r11
  __int64 *v22; // rbx
  __int64 v23; // rcx
  __int64 **v24; // [rsp+30h] [rbp-D0h] BYREF
  __int64 **v25; // [rsp+38h] [rbp-C8h]
  _BYTE v26[416]; // [rsp+40h] [rbp-C0h] BYREF

  if ( (unsigned __int64)a1[1] >= 2 )
  {
    v2 = 0;
    v25 = 0;
    v3 = (__int64 **)std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0((__int64)a1, 0, 0);
    v24 = v3;
    `eh vector constructor iterator'(
      v26,
      0x10u,
      0x1Au,
      (void (*)(void *))std::list<CommandSet>::list<CommandSet>,
      (void (*)(void *))std::list<CommandSet>::~list<CommandSet>);
    v4 = 0;
    while ( 1 )
    {
      v5 = a1[1];
      if ( !v5 )
        break;
      v6 = **a1;
      v7 = *v6;
      v8 = *v3;
      if ( &v24 != a1 )
      {
        if ( v2 == (__int64 **)0x38E38E38E38E38DLL )
          goto LABEL_24;
        v2 = (__int64 **)((char *)v2 + 1);
        v25 = v2;
        a1[1] = (__int64 **)((char *)v5 - 1);
      }
      *(_QWORD *)v6[1] = v7;
      **(_QWORD **)(v7 + 8) = v8;
      *(_QWORD *)v8[1] = v6;
      v9 = v8[1];
      v8[1] = *(_QWORD *)(v7 + 8);
      *(_QWORD *)(v7 + 8) = v6[1];
      v6[1] = v9;
      for ( i = 0; i < v4; ++i )
      {
        v11 = 16 * i;
        if ( !*(_QWORD *)&v26[16 * i + 8] )
          break;
        v12 = (__int64 ***)&v26[v11];
        std::list<CommandSet>::merge((__int64 ***)&v26[v11], &v24);
        if ( v12 == &v24 )
        {
          v2 = v25;
          v3 = v24;
        }
        else
        {
          v3 = *v12;
          *v12 = v24;
          v24 = v3;
          v2 = v12[1];
          v12[1] = v25;
          v25 = v2;
        }
      }
      v13 = (__int64 ***)&v26[16 * i];
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
          v14 = *v13;
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
      std::list<CommandSet>::merge((__int64 ***)&v26[16 * j], (__int64 ***)&v26[16 * j - 16]);
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
        a1[1] = (__int64 **)((char *)v19 + v18);
        v17[1] = 0;
        *(_QWORD *)v22[1] = v21;
        *v21[1] = (__int64)v20;
        *(_QWORD *)v20[1] = v22;
        v23 = v20[1];
        v20[1] = (__int64)v21[1];
        v21[1] = (__int64 *)v22[1];
        v22[1] = v23;
      }
    }
    `eh vector destructor iterator'(v26, 0x10u, 26, (void (*)(void *))std::list<CommandSet>::~list<CommandSet>);
    std::list<CommandSet>::~list<CommandSet>(&v24);
  }
}

```

## disassembly

```asm
0x18000c144  push    rbp
0x18000c146  push    rbx
0x18000c147  push    rsi
0x18000c148  push    rdi
0x18000c149  push    r12
0x18000c14b  push    r13
0x18000c14d  push    r14
0x18000c14f  push    r15
0x18000c151  lea     rbp, [rsp-0F8h]
0x18000c159  sub     rsp, 1F8h
0x18000c160  mov     rax, cs:__security_cookie
0x18000c167  xor     rax, rsp
0x18000c16a  mov     [rbp+130h+var_50], rax
0x18000c171  mov     rsi, rcx
0x18000c174  cmp     qword ptr [rcx+8], 2
0x18000c179  jb      loc_18000C3DC
0x18000c17f  xor     edi, edi
0x18000c181  mov     [rsp+230h+var_1F8], rdi
0x18000c186  xor     r8d, r8d
0x18000c189  xor     edx, edx
0x18000c18b  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *)
0x18000c190  mov     r15, rax
0x18000c193  mov     [rsp+230h+var_200], rax
0x18000c198  lea     r14, ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; std::list<CommandSet>::~list<CommandSet>(void)
0x18000c19f  mov     [rsp+230h+var_210], r14; void (*)(void *)
0x18000c1a4  lea     r9, ??0?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x18000c1ab  lea     edx, [rdi+10h]; unsigned __int64
0x18000c1ae  lea     r8d, [rdi+1Ah]; unsigned __int64
0x18000c1b2  lea     rcx, [rsp+230h+var_1F0]; void *
0x18000c1b7  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18000c1bc  nop
0x18000c1bd  xor     ebx, ebx
0x18000c1bf  mov     r13, 38E38E38E38E38Dh
0x18000c1c9  mov     rcx, [rsi+8]
0x18000c1cd  test    rcx, rcx
0x18000c1d0  jz      loc_18000C314
0x18000c1d6  mov     rax, [rsi]
0x18000c1d9  mov     rdx, [rax]
0x18000c1dc  mov     r8, [rdx]
0x18000c1df  mov     r9, [r15]
0x18000c1e2  lea     rax, [rsp+230h+var_200]
0x18000c1e7  cmp     rax, rsi
0x18000c1ea  jz      short loc_18000C20C
0x18000c1ec  mov     rax, r13
0x18000c1ef  sub     rax, rdi
0x18000c1f2  cmp     rax, 1
0x18000c1f6  jb      loc_18000C360
0x18000c1fc  inc     rdi
0x18000c1ff  mov     [rsp+230h+var_1F8], rdi
0x18000c204  lea     rax, [rcx-1]
0x18000c208  mov     [rsi+8], rax
0x18000c20c  mov     rax, [rdx+8]
0x18000c210  mov     [rax], r8
0x18000c213  mov     rax, [r8+8]
0x18000c217  mov     [rax], r9
0x18000c21a  mov     rax, [r9+8]
0x18000c21e  mov     [rax], rdx
0x18000c221  mov     rcx, [r9+8]
0x18000c225  mov     rax, [r8+8]
0x18000c229  mov     [r9+8], rax
0x18000c22d  mov     rax, [rdx+8]
0x18000c231  mov     [r8+8], rax
0x18000c235  mov     [rdx+8], rcx
0x18000c239  xor     r14d, r14d
0x18000c23c  test    rbx, rbx
0x18000c23f  jz      short loc_18000C2A9
0x18000c241  mov     rax, r14
0x18000c244  shl     rax, 4
0x18000c248  cmp     [rsp+rax+230h+var_1E8], 0
0x18000c24e  jz      short loc_18000C2A9
0x18000c250  lea     r12, [rsp+230h+var_1F0]
0x18000c255  add     r12, rax
0x18000c258  lea     rdx, [rsp+230h+var_200]
0x18000c25d  mov     rcx, r12
0x18000c260  call    ?merge@?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAAXAEAV12@@Z; std::list<CommandSet>::merge(std::list<CommandSet> &)
0x18000c265  lea     rax, [rsp+230h+var_200]
0x18000c26a  cmp     r12, rax
0x18000c26d  jz      short loc_18000C297
0x18000c26f  mov     r15, [r12]
0x18000c273  mov     rax, [rsp+230h+var_200]
0x18000c278  mov     [r12], rax
0x18000c27c  mov     [rsp+230h+var_200], r15
0x18000c281  mov     rdi, [r12+8]
0x18000c286  mov     rax, [rsp+230h+var_1F8]
0x18000c28b  mov     [r12+8], rax
0x18000c290  mov     [rsp+230h+var_1F8], rdi
0x18000c295  jmp     short loc_18000C2A1
0x18000c297  mov     rdi, [rsp+230h+var_1F8]
0x18000c29c  mov     r15, [rsp+230h+var_200]
0x18000c2a1  inc     r14
0x18000c2a4  cmp     r14, rbx
0x18000c2a7  jb      short loc_18000C241
0x18000c2a9  mov     rax, r14
0x18000c2ac  shl     rax, 4
0x18000c2b0  lea     rcx, [rsp+230h+var_1F0]
0x18000c2b5  add     rcx, rax
0x18000c2b8  cmp     r14, 19h
0x18000c2bc  jnz     short loc_18000C2DB
0x18000c2be  add     rcx, 0FFFFFFFFFFFFFFF0h
0x18000c2c2  lea     rdx, [rsp+230h+var_200]
0x18000c2c7  call    ?merge@?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAAXAEAV12@@Z; std::list<CommandSet>::merge(std::list<CommandSet> &)
0x18000c2cc  mov     rdi, [rsp+230h+var_1F8]
0x18000c2d1  mov     r15, [rsp+230h+var_200]
0x18000c2d6  jmp     loc_18000C1C9
0x18000c2db  lea     rax, [rsp+230h+var_200]
0x18000c2e0  cmp     rcx, rax
0x18000c2e3  jz      short loc_18000C303
0x18000c2e5  mov     rax, [rcx]
0x18000c2e8  mov     [rcx], r15
0x18000c2eb  mov     r15, rax
0x18000c2ee  mov     [rsp+230h+var_200], rax
0x18000c2f3  mov     rax, [rcx+8]
0x18000c2f7  mov     [rcx+8], rdi
0x18000c2fb  mov     rdi, rax
0x18000c2fe  mov     [rsp+230h+var_1F8], rax
0x18000c303  cmp     r14, rbx
0x18000c306  jnz     loc_18000C1C9
0x18000c30c  inc     rbx
0x18000c30f  jmp     loc_18000C1C9
0x18000c314  mov     edi, 1
0x18000c319  cmp     rbx, rdi
0x18000c31c  jbe     short loc_18000C33E
0x18000c31e  mov     rax, rdi
0x18000c321  shl     rax, 4
0x18000c325  lea     rcx, [rsp+230h+var_1F0]
0x18000c32a  add     rcx, rax
0x18000c32d  lea     rdx, [rcx-10h]
0x18000c331  call    ?merge@?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAAXAEAV12@@Z; std::list<CommandSet>::merge(std::list<CommandSet> &)
0x18000c336  inc     rdi
0x18000c339  cmp     rdi, rbx
0x18000c33c  jb      short loc_18000C31E
0x18000c33e  add     rbx, rbx
0x18000c341  lea     rcx, [rsp+rbx*8+230h+var_200]
0x18000c346  cmp     rsi, rcx
0x18000c349  jz      short loc_18000C3B7
0x18000c34b  mov     rdx, [rcx+8]
0x18000c34f  test    rdx, rdx
0x18000c352  jz      short loc_18000C3B7
0x18000c354  mov     r8, [rsi+8]
0x18000c358  sub     r13, r8
0x18000c35b  cmp     r13, rdx
0x18000c35e  jnb     short loc_18000C36E
0x18000c360  lea     rcx, aListTTooLong; "list<T> too long"
0x18000c367  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000c36e  mov     rax, [rsi]
0x18000c371  mov     r10, [rax]
0x18000c374  mov     r11, [rcx]
0x18000c377  mov     rbx, [r11]
0x18000c37a  lea     rax, [rdx+r8]
0x18000c37e  mov     [rsi+8], rax
0x18000c382  mov     qword ptr [rcx+8], 0
0x18000c38a  mov     rax, [rbx+8]
0x18000c38e  mov     [rax], r11
0x18000c391  mov     rax, [r11+8]
0x18000c395  mov     [rax], r10
0x18000c398  mov     rax, [r10+8]
0x18000c39c  mov     [rax], rbx
0x18000c39f  mov     rcx, [r10+8]
0x18000c3a3  mov     rax, [r11+8]
0x18000c3a7  mov     [r10+8], rax
0x18000c3ab  mov     rax, [rbx+8]
0x18000c3af  mov     [r11+8], rax
0x18000c3b3  mov     [rbx+8], rcx
0x18000c3b7  lea     r9, ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x18000c3be  mov     edx, 10h; unsigned __int64
0x18000c3c3  lea     r8d, [rdx+0Ah]; unsigned __int64
0x18000c3c7  lea     rcx, [rsp+230h+var_1F0]; void *
0x18000c3cc  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000c3d1  nop
0x18000c3d2  lea     rcx, [rsp+230h+var_200]; void *
0x18000c3d7  call    ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; std::list<CommandSet>::~list<CommandSet>(void)
0x18000c3dc  mov     rcx, [rbp+130h+var_50]
0x18000c3e3  xor     rcx, rsp; StackCookie
0x18000c3e6  call    __security_check_cookie
0x18000c3eb  add     rsp, 1F8h
0x18000c3f2  pop     r15
0x18000c3f4  pop     r14
0x18000c3f6  pop     r13
0x18000c3f8  pop     r12
0x18000c3fa  pop     rdi
0x18000c3fb  pop     rsi
0x18000c3fc  pop     rbx
0x18000c3fd  pop     rbp
0x18000c3fe  retn
```
