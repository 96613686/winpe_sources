# std::list<Command,std::allocator<Command>>::sort(void)

- ea: `0x18000be80`
- end: `0x18000c13b`
- name: `?sort@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXXZ`
- size: `699`
- prototype: `void __fastcall(void ***)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000b660`

## callees

- `0x180001bb8`
- `0x180002220`
- `0x180007698`
- `0x180009fa0`
- `0x18000bb60`
- `0x18000be80`
- `0x18000c600`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000c0a3`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000c0a3`

## pseudocode

```c
void __fastcall std::list<Command>::sort(void ***a1)
{
  __int64 **v2; // rdi
  void **v3; // r15
  unsigned __int64 v4; // rbx
  void **v5; // rcx
  __int64 *v6; // rdx
  __int64 v7; // r8
  _QWORD **v8; // r9
  _QWORD *v9; // rcx
  unsigned __int64 i; // r14
  __int64 v11; // rax
  void ***v12; // r12
  __int64 ***v13; // rcx
  void **v14; // rax
  __int64 **v15; // rax
  unsigned __int64 j; // rdi
  void ***v17; // rcx
  unsigned __int64 v18; // rdx
  void **v19; // r8
  _QWORD **v20; // r10
  void **v21; // r11
  _QWORD **v22; // rbx
  _QWORD *v23; // rcx
  void **v24; // [rsp+30h] [rbp-D0h] BYREF
  void **v25; // [rsp+38h] [rbp-C8h]
  _BYTE v26[416]; // [rsp+40h] [rbp-C0h] BYREF

  if ( (unsigned __int64)a1[1] >= 2 )
  {
    v2 = 0;
    v25 = 0;
    v3 = (void **)std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0((__int64)a1, 0, 0);
    v24 = v3;
    `eh vector constructor iterator'(
      v26,
      0x10u,
      0x1Au,
      (void (*)(void *))std::list<Command>::list<Command>,
      (void (*)(void *))std::list<Command>::~list<Command>);
    v4 = 0;
    while ( 1 )
    {
      v5 = a1[1];
      if ( !v5 )
        break;
      v6 = (__int64 *)**a1;
      v7 = *v6;
      v8 = (_QWORD **)*v3;
      if ( &v24 != a1 )
      {
        if ( v2 == (__int64 **)0x1FFFFFFFFFFFFFELL )
          goto LABEL_24;
        v2 = (__int64 **)((char *)v2 + 1);
        v25 = (void **)v2;
        a1[1] = (void **)((char *)v5 - 1);
      }
      *(_QWORD *)v6[1] = v7;
      **(_QWORD **)(v7 + 8) = v8;
      *v8[1] = v6;
      v9 = v8[1];
      v8[1] = *(_QWORD **)(v7 + 8);
      *(_QWORD *)(v7 + 8) = v6[1];
      v6[1] = (__int64)v9;
      for ( i = 0; i < v4; ++i )
      {
        v11 = 16 * i;
        if ( !*(_QWORD *)&v26[16 * i + 8] )
          break;
        v12 = (void ***)&v26[v11];
        std::list<Command>::merge((__int64 ***)&v26[v11], (__int64 ***)&v24);
        if ( v12 == &v24 )
        {
          v2 = (__int64 **)v25;
          v3 = v24;
        }
        else
        {
          v3 = *v12;
          *v12 = v24;
          v24 = v3;
          v2 = (__int64 **)v12[1];
          v12[1] = v25;
          v25 = (void **)v2;
        }
      }
      v13 = (__int64 ***)&v26[16 * i];
      if ( i == 25 )
      {
        std::list<Command>::merge(v13 - 2, (__int64 ***)&v24);
        v2 = (__int64 **)v25;
        v3 = v24;
      }
      else
      {
        if ( v13 != (__int64 ***)&v24 )
        {
          v14 = (void **)*v13;
          *v13 = (__int64 **)v3;
          v3 = v14;
          v24 = v14;
          v15 = v13[1];
          v13[1] = v2;
          v2 = v15;
          v25 = (void **)v15;
        }
        if ( i == v4 )
          ++v4;
      }
    }
    for ( j = 1; j < v4; ++j )
      std::list<Command>::merge((__int64 ***)&v26[16 * j], (__int64 ***)&v26[16 * j - 16]);
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
        v20 = (_QWORD **)**a1;
        v21 = *v17;
        v22 = (_QWORD **)**v17;
        a1[1] = (void **)((char *)v19 + v18);
        v17[1] = 0;
        *v22[1] = v21;
        *(_QWORD *)v21[1] = v20;
        *v20[1] = v22;
        v23 = v20[1];
        v20[1] = v21[1];
        v21[1] = v22[1];
        v22[1] = v23;
      }
    }
    `eh vector destructor iterator'(v26, 0x10u, 26, (void (*)(void *))std::list<Command>::~list<Command>);
    std::list<Command>::~list<Command>(&v24);
  }
}

```

## disassembly

```asm
0x18000be80  push    rbp
0x18000be82  push    rbx
0x18000be83  push    rsi
0x18000be84  push    rdi
0x18000be85  push    r12
0x18000be87  push    r13
0x18000be89  push    r14
0x18000be8b  push    r15
0x18000be8d  lea     rbp, [rsp-0F8h]
0x18000be95  sub     rsp, 1F8h
0x18000be9c  mov     rax, cs:__security_cookie
0x18000bea3  xor     rax, rsp
0x18000bea6  mov     [rbp+130h+var_50], rax
0x18000bead  mov     rsi, rcx
0x18000beb0  cmp     qword ptr [rcx+8], 2
0x18000beb5  jb      loc_18000C118
0x18000bebb  xor     edi, edi
0x18000bebd  mov     [rsp+230h+var_1F8], rdi
0x18000bec2  xor     r8d, r8d
0x18000bec5  xor     edx, edx
0x18000bec7  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommand@@V?$allocator@UCommand@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *)
0x18000becc  mov     r15, rax
0x18000becf  mov     [rsp+230h+var_200], rax
0x18000bed4  lea     r14, ??1?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ; std::list<Command>::~list<Command>(void)
0x18000bedb  mov     [rsp+230h+var_210], r14; void (*)(void *)
0x18000bee0  lea     r9, ??0?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x18000bee7  lea     edx, [rdi+10h]; unsigned __int64
0x18000beea  lea     r8d, [rdi+1Ah]; unsigned __int64
0x18000beee  lea     rcx, [rsp+230h+var_1F0]; void *
0x18000bef3  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18000bef8  nop
0x18000bef9  xor     ebx, ebx
0x18000befb  mov     r13, 1FFFFFFFFFFFFFEh
0x18000bf05  mov     rcx, [rsi+8]
0x18000bf09  test    rcx, rcx
0x18000bf0c  jz      loc_18000C050
0x18000bf12  mov     rax, [rsi]
0x18000bf15  mov     rdx, [rax]
0x18000bf18  mov     r8, [rdx]
0x18000bf1b  mov     r9, [r15]
0x18000bf1e  lea     rax, [rsp+230h+var_200]
0x18000bf23  cmp     rax, rsi
0x18000bf26  jz      short loc_18000BF48
0x18000bf28  mov     rax, r13
0x18000bf2b  sub     rax, rdi
0x18000bf2e  cmp     rax, 1
0x18000bf32  jb      loc_18000C09C
0x18000bf38  inc     rdi
0x18000bf3b  mov     [rsp+230h+var_1F8], rdi
0x18000bf40  lea     rax, [rcx-1]
0x18000bf44  mov     [rsi+8], rax
0x18000bf48  mov     rax, [rdx+8]
0x18000bf4c  mov     [rax], r8
0x18000bf4f  mov     rax, [r8+8]
0x18000bf53  mov     [rax], r9
0x18000bf56  mov     rax, [r9+8]
0x18000bf5a  mov     [rax], rdx
0x18000bf5d  mov     rcx, [r9+8]
0x18000bf61  mov     rax, [r8+8]
0x18000bf65  mov     [r9+8], rax
0x18000bf69  mov     rax, [rdx+8]
0x18000bf6d  mov     [r8+8], rax
0x18000bf71  mov     [rdx+8], rcx
0x18000bf75  xor     r14d, r14d
0x18000bf78  test    rbx, rbx
0x18000bf7b  jz      short loc_18000BFE5
0x18000bf7d  mov     rax, r14
0x18000bf80  shl     rax, 4
0x18000bf84  cmp     [rsp+rax+230h+var_1E8], 0
0x18000bf8a  jz      short loc_18000BFE5
0x18000bf8c  lea     r12, [rsp+230h+var_1F0]
0x18000bf91  add     r12, rax
0x18000bf94  lea     rdx, [rsp+230h+var_200]
0x18000bf99  mov     rcx, r12
0x18000bf9c  call    ?merge@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXAEAV12@@Z; std::list<Command>::merge(std::list<Command> &)
0x18000bfa1  lea     rax, [rsp+230h+var_200]
0x18000bfa6  cmp     r12, rax
0x18000bfa9  jz      short loc_18000BFD3
0x18000bfab  mov     r15, [r12]
0x18000bfaf  mov     rax, [rsp+230h+var_200]
0x18000bfb4  mov     [r12], rax
0x18000bfb8  mov     [rsp+230h+var_200], r15
0x18000bfbd  mov     rdi, [r12+8]
0x18000bfc2  mov     rax, [rsp+230h+var_1F8]
0x18000bfc7  mov     [r12+8], rax
0x18000bfcc  mov     [rsp+230h+var_1F8], rdi
0x18000bfd1  jmp     short loc_18000BFDD
0x18000bfd3  mov     rdi, [rsp+230h+var_1F8]
0x18000bfd8  mov     r15, [rsp+230h+var_200]
0x18000bfdd  inc     r14
0x18000bfe0  cmp     r14, rbx
0x18000bfe3  jb      short loc_18000BF7D
0x18000bfe5  mov     rax, r14
0x18000bfe8  shl     rax, 4
0x18000bfec  lea     rcx, [rsp+230h+var_1F0]
0x18000bff1  add     rcx, rax
0x18000bff4  cmp     r14, 19h
0x18000bff8  jnz     short loc_18000C017
0x18000bffa  add     rcx, 0FFFFFFFFFFFFFFF0h
0x18000bffe  lea     rdx, [rsp+230h+var_200]
0x18000c003  call    ?merge@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXAEAV12@@Z; std::list<Command>::merge(std::list<Command> &)
0x18000c008  mov     rdi, [rsp+230h+var_1F8]
0x18000c00d  mov     r15, [rsp+230h+var_200]
0x18000c012  jmp     loc_18000BF05
0x18000c017  lea     rax, [rsp+230h+var_200]
0x18000c01c  cmp     rcx, rax
0x18000c01f  jz      short loc_18000C03F
0x18000c021  mov     rax, [rcx]
0x18000c024  mov     [rcx], r15
0x18000c027  mov     r15, rax
0x18000c02a  mov     [rsp+230h+var_200], rax
0x18000c02f  mov     rax, [rcx+8]
0x18000c033  mov     [rcx+8], rdi
0x18000c037  mov     rdi, rax
0x18000c03a  mov     [rsp+230h+var_1F8], rax
0x18000c03f  cmp     r14, rbx
0x18000c042  jnz     loc_18000BF05
0x18000c048  inc     rbx
0x18000c04b  jmp     loc_18000BF05
0x18000c050  mov     edi, 1
0x18000c055  cmp     rbx, rdi
0x18000c058  jbe     short loc_18000C07A
0x18000c05a  mov     rax, rdi
0x18000c05d  shl     rax, 4
0x18000c061  lea     rcx, [rsp+230h+var_1F0]
0x18000c066  add     rcx, rax
0x18000c069  lea     rdx, [rcx-10h]
0x18000c06d  call    ?merge@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXAEAV12@@Z; std::list<Command>::merge(std::list<Command> &)
0x18000c072  inc     rdi
0x18000c075  cmp     rdi, rbx
0x18000c078  jb      short loc_18000C05A
0x18000c07a  add     rbx, rbx
0x18000c07d  lea     rcx, [rsp+rbx*8+230h+var_200]
0x18000c082  cmp     rsi, rcx
0x18000c085  jz      short loc_18000C0F3
0x18000c087  mov     rdx, [rcx+8]
0x18000c08b  test    rdx, rdx
0x18000c08e  jz      short loc_18000C0F3
0x18000c090  mov     r8, [rsi+8]
0x18000c094  sub     r13, r8
0x18000c097  cmp     r13, rdx
0x18000c09a  jnb     short loc_18000C0AA
0x18000c09c  lea     rcx, aListTTooLong; "list<T> too long"
0x18000c0a3  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000c0aa  mov     rax, [rsi]
0x18000c0ad  mov     r10, [rax]
0x18000c0b0  mov     r11, [rcx]
0x18000c0b3  mov     rbx, [r11]
0x18000c0b6  lea     rax, [rdx+r8]
0x18000c0ba  mov     [rsi+8], rax
0x18000c0be  mov     qword ptr [rcx+8], 0
0x18000c0c6  mov     rax, [rbx+8]
0x18000c0ca  mov     [rax], r11
0x18000c0cd  mov     rax, [r11+8]
0x18000c0d1  mov     [rax], r10
0x18000c0d4  mov     rax, [r10+8]
0x18000c0d8  mov     [rax], rbx
0x18000c0db  mov     rcx, [r10+8]
0x18000c0df  mov     rax, [r11+8]
0x18000c0e3  mov     [r10+8], rax
0x18000c0e7  mov     rax, [rbx+8]
0x18000c0eb  mov     [r11+8], rax
0x18000c0ef  mov     [rbx+8], rcx
0x18000c0f3  lea     r9, ??1?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x18000c0fa  mov     edx, 10h; unsigned __int64
0x18000c0ff  lea     r8d, [rdx+0Ah]; unsigned __int64
0x18000c103  lea     rcx, [rsp+230h+var_1F0]; void *
0x18000c108  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000c10d  nop
0x18000c10e  lea     rcx, [rsp+230h+var_200]; void *
0x18000c113  call    ??1?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ; std::list<Command>::~list<Command>(void)
0x18000c118  mov     rcx, [rbp+130h+var_50]
0x18000c11f  xor     rcx, rsp; StackCookie
0x18000c122  call    __security_check_cookie
0x18000c127  add     rsp, 1F8h
0x18000c12e  pop     r15
0x18000c130  pop     r14
0x18000c132  pop     r13
0x18000c134  pop     r12
0x18000c136  pop     rdi
0x18000c137  pop     rsi
0x18000c138  pop     rbx
0x18000c139  pop     rbp
0x18000c13a  retn
```
