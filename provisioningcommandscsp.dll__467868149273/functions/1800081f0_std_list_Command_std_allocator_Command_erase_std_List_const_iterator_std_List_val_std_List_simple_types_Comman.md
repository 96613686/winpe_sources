# std::list<Command,std::allocator<Command>>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>,std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>)

- ea: `0x1800081f0`
- end: `0x1800082b2`
- name: `?erase@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@2@0@Z`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006ab4`

## callees

- `0x1800081f0`
- `0x18000a554`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008242`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008289`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008242`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008289`

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
0x1800081f0  push    rbx
0x1800081f2  push    rbp
0x1800081f3  push    rsi
0x1800081f4  push    rdi
0x1800081f5  push    r14
0x1800081f7  push    r15
0x1800081f9  sub     rsp, 28h
0x1800081fd  mov     rax, [rcx]
0x180008200  mov     rdi, r9
0x180008203  mov     rbx, r8
0x180008206  mov     r14, rdx
0x180008209  mov     rsi, rcx
0x18000820c  mov     r15, [rax]
0x18000820f  cmp     r8, r15
0x180008212  jnz     short loc_18000825E
0x180008214  cmp     r9, rax
0x180008217  jnz     short loc_18000825E
0x180008219  mov     [rax], rax
0x18000821c  mov     rax, [rcx]
0x18000821f  mov     [rax+8], rax
0x180008223  mov     rax, [rcx]
0x180008226  mov     qword ptr [rcx+8], 0
0x18000822e  cmp     r15, rax
0x180008231  jz      short loc_180008259
0x180008233  mov     rbx, [r15]
0x180008236  lea     rcx, [r15+10h]; this
0x18000823a  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x18000823f  mov     rcx, r15
0x180008242  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008249  nop     dword ptr [rax+rax+00h]
0x18000824e  mov     rax, [rsi]
0x180008251  mov     r15, rbx
0x180008254  cmp     rbx, rax
0x180008257  jnz     short loc_180008233
0x180008259  mov     [r14], rax
0x18000825c  jmp     short loc_1800082A1
0x18000825e  cmp     rbx, rdi
0x180008261  jz      short loc_18000829E
0x180008263  mov     rbp, [rbx]
0x180008266  cmp     rbx, [rsi]
0x180008269  jz      short loc_180008299
0x18000826b  mov     rax, [rbx+8]
0x18000826f  mov     [rax], rbp
0x180008272  mov     rcx, [rbx]
0x180008275  mov     rax, [rbx+8]
0x180008279  mov     [rcx+8], rax
0x18000827d  lea     rcx, [rbx+10h]; this
0x180008281  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x180008286  mov     rcx, rbx
0x180008289  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008290  nop     dword ptr [rax+rax+00h]
0x180008295  dec     qword ptr [rsi+8]
0x180008299  mov     rbx, rbp
0x18000829c  jmp     short loc_18000825E
0x18000829e  mov     [r14], rdi
0x1800082a1  mov     rax, r14
0x1800082a4  add     rsp, 28h
0x1800082a8  pop     r15
0x1800082aa  pop     r14
0x1800082ac  pop     rdi
0x1800082ad  pop     rsi
0x1800082ae  pop     rbp
0x1800082af  pop     rbx
0x1800082b0  retn
```
