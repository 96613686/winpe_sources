# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Unchecked_erase(std::_List_node<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,void *> *,std::_List_node<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,void *> * const)

- ea: `0x140033424`
- end: `0x1400335f5`
- name: `?_Unchecked_erase@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `465`
- prototype: `char *__fastcall(_QWORD *, char *, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400335fc`

## callees

- `0x140003244`
- `0x140013df8`
- `0x140033424`

## pseudocode

```c
char *__fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Unchecked_erase(
        _QWORD *a1,
        char *a2,
        char *a3)
{
  char **v6; // rax
  char *v7; // rsi
  __int64 v8; // r12
  _QWORD *v9; // rcx
  char **v10; // r14
  __int64 v11; // r10
  unsigned __int64 v12; // rdx
  __int64 v13; // r8
  unsigned __int64 v14; // r10
  __int64 v15; // rax
  __int64 v16; // r13
  char **v17; // rbx
  _QWORD *v18; // r9
  char **v19; // rax
  _QWORD *v20; // rcx
  unsigned __int64 v21; // r8
  __int64 v22; // rdx
  unsigned __int64 v23; // r10
  __int64 v24; // rax
  __int64 v25; // r15
  char **v26; // r13
  char **v27; // rbx
  char *v30; // [rsp+78h] [rbp+10h]
  char **v31; // [rsp+80h] [rbp+18h]
  char **v32; // [rsp+88h] [rbp+20h]

  if ( a2 != a3 )
  {
    v6 = (char **)a1[1];
    v7 = a2;
    v8 = a1[3];
    v9 = a2 + 16;
    v10 = (char **)*((_QWORD *)a2 + 1);
    v11 = *((_QWORD *)a2 + 4);
    v31 = v6;
    if ( *((_QWORD *)a2 + 5) > 7u )
      v9 = (_QWORD *)*v9;
    v12 = 0;
    v13 = 0xCBF29CE484222325uLL;
    v14 = 2 * v11;
    if ( v14 )
    {
      do
      {
        v15 = *((unsigned __int8 *)v9 + v12++);
        v13 = 0x100000001B3LL * (v15 ^ v13);
      }
      while ( v12 < v14 );
    }
    v16 = 2 * (v13 & a1[6]);
    v30 = *(char **)(v8 + 16 * (v13 & a1[6]));
    v32 = *(char ***)(v8 + 16 * (v13 & a1[6]) + 8);
    while ( 1 )
    {
      v17 = (char **)v7;
      v7 = *(char **)v7;
      std::wstring::_Tidy_deallocate(v17 + 2);
      operator delete(v17);
      v18 = a1;
      --a1[2];
      if ( v17 == v32 )
        break;
      if ( v7 == a3 )
      {
        if ( v30 == a2 )
          *(_QWORD *)(v8 + 8 * v16) = v7;
        goto LABEL_24;
      }
    }
    if ( v30 == a2 )
    {
      *(_QWORD *)(v8 + 8 * v16) = v31;
      v19 = v31;
    }
    else
    {
      v19 = v10;
    }
    *(_QWORD *)(v8 + 8 * v16 + 8) = v19;
    while ( v7 != a3 )
    {
      v20 = v7 + 16;
      if ( *((_QWORD *)v7 + 5) > 7u )
        v20 = (_QWORD *)*v20;
      v21 = 0;
      v22 = 0xCBF29CE484222325uLL;
      v23 = 2LL * *((_QWORD *)v7 + 4);
      if ( v23 )
      {
        do
        {
          v24 = *((unsigned __int8 *)v20 + v21++);
          v22 = 0x100000001B3LL * (v24 ^ v22);
        }
        while ( v21 < v23 );
        v18 = a1;
      }
      v25 = 2 * (v22 & v18[6]);
      v26 = *(char ***)(v8 + 16 * (v22 & v18[6]) + 8);
      while ( 1 )
      {
        v27 = (char **)v7;
        v7 = *(char **)v7;
        std::wstring::_Tidy_deallocate(v27 + 2);
        operator delete(v27);
        v18 = a1;
        --a1[2];
        if ( v27 == v26 )
          break;
        if ( v7 == a3 )
        {
          *(_QWORD *)(v8 + 8 * v25) = v7;
          goto LABEL_24;
        }
      }
      *(_QWORD *)(v8 + 8 * v25) = v31;
      *(_QWORD *)(v8 + 8 * v25 + 8) = v31;
    }
LABEL_24:
    *v10 = v7;
    *((_QWORD *)v7 + 1) = v10;
  }
  return a3;
}

```

## disassembly

```asm
0x140033424  mov     [rsp+arg_0], rcx
0x140033429  push    rbx
0x14003342a  push    rbp
0x14003342b  push    rsi
0x14003342c  push    rdi
0x14003342d  push    r12
0x14003342f  push    r13
0x140033431  push    r14
0x140033433  push    r15
0x140033435  sub     rsp, 28h
0x140033439  mov     rbp, r8
0x14003343c  mov     r15, rdx
0x14003343f  mov     r9, rcx
0x140033442  cmp     rdx, r8
0x140033445  jz      loc_1400335C5
0x14003344b  mov     rax, [rcx+8]
0x14003344f  mov     rsi, rdx
0x140033452  mov     r12, [rcx+18h]
0x140033456  lea     rcx, [rdx+10h]
0x14003345a  cmp     qword ptr [rcx+18h], 7
0x14003345f  mov     r14, [rdx+8]
0x140033463  mov     r10, [rcx+10h]
0x140033467  mov     [rsp+68h+arg_10], rax
0x14003346f  jbe     short loc_140033474
0x140033471  mov     rcx, [rcx]
0x140033474  xor     edx, edx
0x140033476  mov     r8, 0CBF29CE484222325h
0x140033480  mov     r11, 100000001B3h
0x14003348a  add     r10, r10
0x14003348d  jz      short loc_1400334A2
0x14003348f  movzx   eax, byte ptr [rcx+rdx]
0x140033493  inc     rdx
0x140033496  xor     r8, rax
0x140033499  imul    r8, r11
0x14003349d  cmp     rdx, r10
0x1400334a0  jb      short loc_14003348F
0x1400334a2  mov     r13, [r9+30h]
0x1400334a6  and     r13, r8
0x1400334a9  add     r13, r13
0x1400334ac  mov     rax, [r12+r13*8]
0x1400334b0  mov     [rsp+68h+arg_8], rax
0x1400334b5  mov     rax, [r12+r13*8+8]
0x1400334ba  mov     [rsp+68h+arg_18], rax
0x1400334c2  mov     rbx, rsi
0x1400334c5  mov     rdi, rsi
0x1400334c8  mov     rsi, [rsi]
0x1400334cb  lea     rcx, [rbx+10h]
0x1400334cf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400334d4  mov     edx, 30h ; '0'
0x1400334d9  mov     rcx, rbx; Block
0x1400334dc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400334e1  mov     r9, [rsp+68h+arg_0]
0x1400334e6  dec     qword ptr [r9+10h]
0x1400334ea  cmp     rbx, [rsp+68h+arg_18]
0x1400334f2  jz      short loc_14003350D
0x1400334f4  cmp     rsi, rbp
0x1400334f7  jnz     short loc_1400334C2
0x1400334f9  cmp     [rsp+68h+arg_8], r15
0x1400334fe  jnz     loc_1400335BE
0x140033504  mov     [r12+r13*8], rsi
0x140033508  jmp     loc_1400335BE
0x14003350d  cmp     [rsp+68h+arg_8], r15
0x140033512  jnz     short loc_140033525
0x140033514  mov     rdx, [rsp+68h+arg_10]
0x14003351c  mov     [r12+r13*8], rdx
0x140033520  mov     rax, rdx
0x140033523  jmp     short loc_140033528
0x140033525  mov     rax, r14
0x140033528  mov     [r12+r13*8+8], rax
0x14003352d  jmp     loc_1400335EA
0x140033532  lea     rcx, [rsi+10h]
0x140033536  cmp     qword ptr [rcx+18h], 7
0x14003353b  mov     r10, [rcx+10h]
0x14003353f  jbe     short loc_140033544
0x140033541  mov     rcx, [rcx]
0x140033544  xor     r8d, r8d
0x140033547  mov     rdx, 0CBF29CE484222325h
0x140033551  add     r10, r10
0x140033554  jz      short loc_140033579
0x140033556  mov     r9, 100000001B3h
0x140033560  movzx   eax, byte ptr [rcx+r8]
0x140033565  inc     r8
0x140033568  xor     rdx, rax
0x14003356b  imul    rdx, r9
0x14003356f  cmp     r8, r10
0x140033572  jb      short loc_140033560
0x140033574  mov     r9, [rsp+68h+arg_0]
0x140033579  mov     r15, [r9+30h]
0x14003357d  and     r15, rdx
0x140033580  add     r15, r15
0x140033583  mov     r13, [r12+r15*8+8]
0x140033588  mov     rbx, rsi
0x14003358b  mov     rdi, rsi
0x14003358e  mov     rsi, [rsi]
0x140033591  lea     rcx, [rbx+10h]
0x140033595  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003359a  mov     edx, 30h ; '0'
0x14003359f  mov     rcx, rbx; Block
0x1400335a2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400335a7  mov     r9, [rsp+68h+arg_0]
0x1400335ac  dec     qword ptr [r9+10h]
0x1400335b0  cmp     rbx, r13
0x1400335b3  jz      short loc_1400335D9
0x1400335b5  cmp     rsi, rbp
0x1400335b8  jnz     short loc_140033588
0x1400335ba  mov     [r12+r15*8], rsi
0x1400335be  mov     [r14], rsi
0x1400335c1  mov     [rsi+8], r14
0x1400335c5  mov     rax, rbp
0x1400335c8  add     rsp, 28h
0x1400335cc  pop     r15
0x1400335ce  pop     r14
0x1400335d0  pop     r13
0x1400335d2  pop     r12
0x1400335d4  pop     rdi
0x1400335d5  pop     rsi
0x1400335d6  pop     rbp
0x1400335d7  pop     rbx
0x1400335d8  retn
0x1400335d9  mov     rax, [rsp+68h+arg_10]
0x1400335e1  mov     [r12+r15*8], rax
0x1400335e5  mov     [r12+r15*8+8], rax
0x1400335ea  cmp     rsi, rbp
0x1400335ed  jnz     loc_140033532
0x1400335f3  jmp     short loc_1400335BE
```
