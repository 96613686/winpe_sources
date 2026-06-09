# std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::_Unchecked_erase(std::_List_node<long,void *> *,std::_List_node<long,void *> * const)

- ea: `0x1800136bc`
- end: `0x180013826`
- name: `?_Unchecked_erase@?$_Hash@V?$_Uset_traits@JV?$_Uhash_compare@JU?$hash@J@std@@U?$equal_to@J@2@@std@@V?$allocator@J@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@JPEAX@2@PEAU32@QEAU32@@Z`
- size: `362`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180012208`

## callees

- `0x180002c8c`
- `0x1800136bc`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::_Unchecked_erase(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rdi
  __int64 v8; // r12
  __int64 v9; // r15
  _QWORD *v10; // r14
  unsigned __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r15
  void *v14; // rcx
  _QWORD *v15; // rbx
  _QWORD *v17; // rax
  __int64 v18; // rcx
  unsigned __int64 i; // rdx
  __int64 v20; // rax
  void *v21; // rcx
  _QWORD *v22; // rbx
  _QWORD *v23; // [rsp+68h] [rbp+10h]
  _QWORD *v24; // [rsp+70h] [rbp+18h]
  _QWORD *v25; // [rsp+70h] [rbp+18h]
  _QWORD *v26; // [rsp+78h] [rbp+20h]

  if ( a2 != a3 )
  {
    v6 = (_QWORD *)a1[1];
    v7 = a2;
    v8 = a1[3];
    v9 = 0xCBF29CE484222325uLL;
    v10 = (_QWORD *)a2[1];
    v11 = 0;
    v23 = v6;
    do
    {
      v12 = *((unsigned __int8 *)a2 + v11 + 16);
      ++v11;
      v9 = 0x100000001B3LL * (v12 ^ v9);
    }
    while ( v11 < 4 );
    v13 = 2 * (a1[6] & v9);
    v24 = *(_QWORD **)(v8 + 8 * v13);
    v26 = *(_QWORD **)(v8 + 8 * v13 + 8);
    while ( 1 )
    {
      v14 = v7;
      v15 = v7;
      v7 = (_QWORD *)*v7;
      operator delete(v14);
      --a1[2];
      if ( v15 == v26 )
        break;
      if ( v7 == a3 )
      {
        if ( v24 == a2 )
LABEL_8:
          *(_QWORD *)(v8 + 8 * v13) = v7;
        goto LABEL_9;
      }
    }
    if ( v24 == a2 )
    {
      *(_QWORD *)(v8 + 8 * v13) = v23;
      v17 = v23;
    }
    else
    {
      v17 = v10;
    }
    *(_QWORD *)(v8 + 8 * v13 + 8) = v17;
    while ( v7 != a3 )
    {
      v18 = 0xCBF29CE484222325uLL;
      for ( i = 0; i < 4; ++i )
      {
        v20 = *((unsigned __int8 *)v7 + i + 16);
        v18 = 0x100000001B3LL * (v20 ^ v18);
      }
      v13 = 2 * (v18 & a1[6]);
      v25 = *(_QWORD **)(v8 + 16 * (v18 & a1[6]) + 8);
      while ( 1 )
      {
        v21 = v7;
        v22 = v7;
        v7 = (_QWORD *)*v7;
        operator delete(v21);
        --a1[2];
        if ( v22 == v25 )
          break;
        if ( v7 == a3 )
          goto LABEL_8;
      }
      *(_QWORD *)(v8 + 8 * v13) = v23;
      *(_QWORD *)(v8 + 8 * v13 + 8) = v23;
    }
LABEL_9:
    *v10 = v7;
    v7[1] = v10;
  }
  return a3;
}

```

## disassembly

```asm
0x1800136bc  mov     [rsp+arg_0], rbx
0x1800136c1  push    rbp
0x1800136c2  push    rsi
0x1800136c3  push    rdi
0x1800136c4  push    r12
0x1800136c6  push    r13
0x1800136c8  push    r14
0x1800136ca  push    r15
0x1800136cc  sub     rsp, 20h
0x1800136d0  mov     rsi, r8
0x1800136d3  mov     rbp, rdx
0x1800136d6  mov     r13, rcx
0x1800136d9  cmp     rdx, r8
0x1800136dc  jz      loc_180013770
0x1800136e2  mov     rax, [rcx+8]
0x1800136e6  mov     rdi, rdx
0x1800136e9  mov     r12, [rcx+18h]
0x1800136ed  mov     r15, 0CBF29CE484222325h
0x1800136f7  mov     r14, [rdx+8]
0x1800136fb  xor     ecx, ecx
0x1800136fd  mov     [rsp+58h+arg_8], rax
0x180013702  mov     rdx, 100000001B3h
0x18001370c  movzx   eax, byte ptr [rcx+rbp+10h]
0x180013711  inc     rcx
0x180013714  xor     r15, rax
0x180013717  imul    r15, rdx
0x18001371b  cmp     rcx, 4
0x18001371f  jb      short loc_18001370C
0x180013721  and     r15, [r13+30h]
0x180013725  add     r15, r15
0x180013728  mov     rax, [r12+r15*8]
0x18001372c  mov     [rsp+58h+arg_10], rax
0x180013731  mov     rax, [r12+r15*8+8]
0x180013736  mov     [rsp+58h+arg_18], rax
0x18001373b  mov     rcx, rdi; void *
0x18001373e  mov     rbx, rdi
0x180013741  mov     rdi, [rdi]
0x180013744  mov     edx, 18h; unsigned __int64
0x180013749  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001374e  dec     qword ptr [r13+10h]
0x180013752  cmp     rbx, [rsp+58h+arg_18]
0x180013757  jz      short loc_180013788
0x180013759  cmp     rdi, rsi
0x18001375c  jnz     short loc_18001373B
0x18001375e  cmp     [rsp+58h+arg_10], rbp
0x180013763  jnz     short loc_180013769
0x180013765  mov     [r12+r15*8], rdi
0x180013769  mov     [r14], rdi
0x18001376c  mov     [rdi+8], r14
0x180013770  mov     rbx, [rsp+58h+arg_0]
0x180013775  mov     rax, rsi
0x180013778  add     rsp, 20h
0x18001377c  pop     r15
0x18001377e  pop     r14
0x180013780  pop     r13
0x180013782  pop     r12
0x180013784  pop     rdi
0x180013785  pop     rsi
0x180013786  pop     rbp
0x180013787  retn
0x180013788  cmp     [rsp+58h+arg_10], rbp
0x18001378d  jnz     short loc_18001379D
0x18001378f  mov     rbp, [rsp+58h+arg_8]
0x180013794  mov     [r12+r15*8], rbp
0x180013798  mov     rax, rbp
0x18001379b  jmp     short loc_1800137A0
0x18001379d  mov     rax, r14
0x1800137a0  mov     [r12+r15*8+8], rax
0x1800137a5  jmp     short loc_18001381C
0x1800137a7  mov     rcx, 0CBF29CE484222325h
0x1800137b1  xor     edx, edx
0x1800137b3  mov     rbp, 100000001B3h
0x1800137bd  movzx   eax, byte ptr [rdi+rdx+10h]
0x1800137c2  inc     rdx
0x1800137c5  xor     rcx, rax
0x1800137c8  imul    rcx, rbp
0x1800137cc  cmp     rdx, 4
0x1800137d0  jb      short loc_1800137BD
0x1800137d2  mov     r15, [r13+30h]
0x1800137d6  mov     rbp, [rsp+58h+arg_8]
0x1800137db  and     r15, rcx
0x1800137de  add     r15, r15
0x1800137e1  mov     rax, [r12+r15*8+8]
0x1800137e6  mov     [rsp+58h+arg_10], rax
0x1800137eb  mov     rcx, rdi; void *
0x1800137ee  mov     rbx, rdi
0x1800137f1  mov     rdi, [rdi]
0x1800137f4  mov     edx, 18h; unsigned __int64
0x1800137f9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800137fe  dec     qword ptr [r13+10h]
0x180013802  cmp     rbx, [rsp+58h+arg_10]
0x180013807  jz      short loc_180013813
0x180013809  cmp     rdi, rsi
0x18001380c  jnz     short loc_1800137EB
0x18001380e  jmp     loc_180013765
0x180013813  mov     [r12+r15*8], rbp
0x180013817  mov     [r12+r15*8+8], rbp
0x18001381c  cmp     rdi, rsi
0x18001381f  jnz     short loc_1800137A7
0x180013821  jmp     loc_180013769
```
