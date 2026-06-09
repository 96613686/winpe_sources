# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Unchecked_erase(std::_List_node<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,void *> *,std::_List_node<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,void *> * const)

- ea: `0x18001382c`
- end: `0x1800139fd`
- name: `?_Unchecked_erase@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `465`
- prototype: `char *__fastcall(_QWORD *, char *, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800122c4`

## callees

- `0x180002c8c`
- `0x18000dcb0`
- `0x18001382c`

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
      std::wstring::~wstring(v17 + 2);
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
        std::wstring::~wstring(v27 + 2);
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
0x18001382c  mov     [rsp+arg_0], rcx
0x180013831  push    rbx
0x180013832  push    rbp
0x180013833  push    rsi
0x180013834  push    rdi
0x180013835  push    r12
0x180013837  push    r13
0x180013839  push    r14
0x18001383b  push    r15
0x18001383d  sub     rsp, 28h
0x180013841  mov     rbp, r8
0x180013844  mov     r15, rdx
0x180013847  mov     r9, rcx
0x18001384a  cmp     rdx, r8
0x18001384d  jz      loc_1800139CD
0x180013853  mov     rax, [rcx+8]
0x180013857  mov     rsi, rdx
0x18001385a  mov     r12, [rcx+18h]
0x18001385e  lea     rcx, [rdx+10h]
0x180013862  cmp     qword ptr [rcx+18h], 7
0x180013867  mov     r14, [rdx+8]
0x18001386b  mov     r10, [rcx+10h]
0x18001386f  mov     [rsp+68h+arg_10], rax
0x180013877  jbe     short loc_18001387C
0x180013879  mov     rcx, [rcx]
0x18001387c  xor     edx, edx
0x18001387e  mov     r8, 0CBF29CE484222325h
0x180013888  mov     r11, 100000001B3h
0x180013892  add     r10, r10
0x180013895  jz      short loc_1800138AA
0x180013897  movzx   eax, byte ptr [rcx+rdx]
0x18001389b  inc     rdx
0x18001389e  xor     r8, rax
0x1800138a1  imul    r8, r11
0x1800138a5  cmp     rdx, r10
0x1800138a8  jb      short loc_180013897
0x1800138aa  mov     r13, [r9+30h]
0x1800138ae  and     r13, r8
0x1800138b1  add     r13, r13
0x1800138b4  mov     rax, [r12+r13*8]
0x1800138b8  mov     [rsp+68h+arg_8], rax
0x1800138bd  mov     rax, [r12+r13*8+8]
0x1800138c2  mov     [rsp+68h+arg_18], rax
0x1800138ca  mov     rbx, rsi
0x1800138cd  mov     rdi, rsi
0x1800138d0  mov     rsi, [rsi]
0x1800138d3  lea     rcx, [rbx+10h]; void *
0x1800138d7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800138dc  mov     edx, 30h ; '0'; unsigned __int64
0x1800138e1  mov     rcx, rbx; void *
0x1800138e4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800138e9  mov     r9, [rsp+68h+arg_0]
0x1800138ee  dec     qword ptr [r9+10h]
0x1800138f2  cmp     rbx, [rsp+68h+arg_18]
0x1800138fa  jz      short loc_180013915
0x1800138fc  cmp     rsi, rbp
0x1800138ff  jnz     short loc_1800138CA
0x180013901  cmp     [rsp+68h+arg_8], r15
0x180013906  jnz     loc_1800139C6
0x18001390c  mov     [r12+r13*8], rsi
0x180013910  jmp     loc_1800139C6
0x180013915  cmp     [rsp+68h+arg_8], r15
0x18001391a  jnz     short loc_18001392D
0x18001391c  mov     rdx, [rsp+68h+arg_10]
0x180013924  mov     [r12+r13*8], rdx
0x180013928  mov     rax, rdx
0x18001392b  jmp     short loc_180013930
0x18001392d  mov     rax, r14
0x180013930  mov     [r12+r13*8+8], rax
0x180013935  jmp     loc_1800139F2
0x18001393a  lea     rcx, [rsi+10h]
0x18001393e  cmp     qword ptr [rcx+18h], 7
0x180013943  mov     r10, [rcx+10h]
0x180013947  jbe     short loc_18001394C
0x180013949  mov     rcx, [rcx]
0x18001394c  xor     r8d, r8d
0x18001394f  mov     rdx, 0CBF29CE484222325h
0x180013959  add     r10, r10
0x18001395c  jz      short loc_180013981
0x18001395e  mov     r9, 100000001B3h
0x180013968  movzx   eax, byte ptr [rcx+r8]
0x18001396d  inc     r8
0x180013970  xor     rdx, rax
0x180013973  imul    rdx, r9
0x180013977  cmp     r8, r10
0x18001397a  jb      short loc_180013968
0x18001397c  mov     r9, [rsp+68h+arg_0]
0x180013981  mov     r15, [r9+30h]
0x180013985  and     r15, rdx
0x180013988  add     r15, r15
0x18001398b  mov     r13, [r12+r15*8+8]
0x180013990  mov     rbx, rsi
0x180013993  mov     rdi, rsi
0x180013996  mov     rsi, [rsi]
0x180013999  lea     rcx, [rbx+10h]; void *
0x18001399d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800139a2  mov     edx, 30h ; '0'; unsigned __int64
0x1800139a7  mov     rcx, rbx; void *
0x1800139aa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800139af  mov     r9, [rsp+68h+arg_0]
0x1800139b4  dec     qword ptr [r9+10h]
0x1800139b8  cmp     rbx, r13
0x1800139bb  jz      short loc_1800139E1
0x1800139bd  cmp     rsi, rbp
0x1800139c0  jnz     short loc_180013990
0x1800139c2  mov     [r12+r15*8], rsi
0x1800139c6  mov     [r14], rsi
0x1800139c9  mov     [rsi+8], r14
0x1800139cd  mov     rax, rbp
0x1800139d0  add     rsp, 28h
0x1800139d4  pop     r15
0x1800139d6  pop     r14
0x1800139d8  pop     r13
0x1800139da  pop     r12
0x1800139dc  pop     rdi
0x1800139dd  pop     rsi
0x1800139de  pop     rbp
0x1800139df  pop     rbx
0x1800139e0  retn
0x1800139e1  mov     rax, [rsp+68h+arg_10]
0x1800139e9  mov     [r12+r15*8], rax
0x1800139ed  mov     [r12+r15*8+8], rax
0x1800139f2  cmp     rsi, rbp
0x1800139f5  jnz     loc_18001393A
0x1800139fb  jmp     short loc_1800139C6
```
