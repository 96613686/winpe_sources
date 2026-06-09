# std::list<Command,std::allocator<Command>>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>,std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>)

- ea: `0x180007e48`
- end: `0x180007efd`
- name: `?erase@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@2@0@Z`
- size: `181`
- prototype: `void ***__fastcall(void ****, void ***, void **, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800067a0`

## callees

- `0x180007e48`
- `0x18000a050`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007e9a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007edb`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007e9a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007edb`

## pseudocode

```c
void ***__fastcall std::list<Command>::erase(void ****a1, void ***a2, void **a3, void **a4)
{
  void **v4; // rax
  void ***v6; // rbx
  void **v9; // r15
  void **v10; // rax
  void **v11; // rbx
  void **v12; // rbp

  v4 = (void **)*a1;
  v6 = (void ***)a3;
  v9 = **a1;
  if ( a3 == v9 && a4 == v4 )
  {
    *v4 = v4;
    (*a1)[1] = (void **)*a1;
    v10 = (void **)*a1;
    a1[1] = 0;
    if ( v9 != v10 )
    {
      do
      {
        v11 = (void **)*v9;
        Command::~Command(v9 + 2);
        operator delete(v9);
        v10 = (void **)*a1;
        v9 = v11;
      }
      while ( v11 != (void **)*a1 );
    }
    *a2 = v10;
  }
  else
  {
    while ( v6 != (void ***)a4 )
    {
      v12 = *v6;
      if ( v6 != *a1 )
      {
        *v6[1] = v12;
        (*v6)[1] = v6[1];
        Command::~Command((void **)v6 + 2);
        operator delete(v6);
        a1[1] = (void ***)((char *)a1[1] - 1);
      }
      v6 = (void ***)v12;
    }
    *a2 = a4;
  }
  return a2;
}

```

## disassembly

```asm
0x180007e48  push    rbx
0x180007e4a  push    rbp
0x180007e4b  push    rsi
0x180007e4c  push    rdi
0x180007e4d  push    r14
0x180007e4f  push    r15
0x180007e51  sub     rsp, 28h
0x180007e55  mov     rax, [rcx]
0x180007e58  mov     rdi, r9
0x180007e5b  mov     rbx, r8
0x180007e5e  mov     r14, rdx
0x180007e61  mov     rsi, rcx
0x180007e64  mov     r15, [rax]
0x180007e67  cmp     r8, r15
0x180007e6a  jnz     short loc_180007EB0
0x180007e6c  cmp     r9, rax
0x180007e6f  jnz     short loc_180007EB0
0x180007e71  mov     [rax], rax
0x180007e74  mov     rax, [rcx]
0x180007e77  mov     [rax+8], rax
0x180007e7b  mov     rax, [rcx]
0x180007e7e  mov     qword ptr [rcx+8], 0
0x180007e86  cmp     r15, rax
0x180007e89  jz      short loc_180007EAB
0x180007e8b  mov     rbx, [r15]
0x180007e8e  lea     rcx, [r15+10h]; this
0x180007e92  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x180007e97  mov     rcx, r15
0x180007e9a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007ea0  mov     rax, [rsi]
0x180007ea3  mov     r15, rbx
0x180007ea6  cmp     rbx, rax
0x180007ea9  jnz     short loc_180007E8B
0x180007eab  mov     [r14], rax
0x180007eae  jmp     short loc_180007EED
0x180007eb0  cmp     rbx, rdi
0x180007eb3  jz      short loc_180007EEA
0x180007eb5  mov     rbp, [rbx]
0x180007eb8  cmp     rbx, [rsi]
0x180007ebb  jz      short loc_180007EE5
0x180007ebd  mov     rax, [rbx+8]
0x180007ec1  mov     [rax], rbp
0x180007ec4  mov     rcx, [rbx]
0x180007ec7  mov     rax, [rbx+8]
0x180007ecb  mov     [rcx+8], rax
0x180007ecf  lea     rcx, [rbx+10h]; this
0x180007ed3  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x180007ed8  mov     rcx, rbx
0x180007edb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007ee1  dec     qword ptr [rsi+8]
0x180007ee5  mov     rbx, rbp
0x180007ee8  jmp     short loc_180007EB0
0x180007eea  mov     [r14], rdi
0x180007eed  mov     rax, r14
0x180007ef0  add     rsp, 28h
0x180007ef4  pop     r15
0x180007ef6  pop     r14
0x180007ef8  pop     rdi
0x180007ef9  pop     rsi
0x180007efa  pop     rbp
0x180007efb  pop     rbx
0x180007efc  retn
```
