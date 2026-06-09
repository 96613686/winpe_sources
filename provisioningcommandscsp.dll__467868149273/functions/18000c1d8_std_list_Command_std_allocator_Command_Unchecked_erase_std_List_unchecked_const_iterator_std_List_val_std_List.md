# std::list<Command,std::allocator<Command>>::_Unchecked_erase(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<Command>>,std::_Iterator_base0>)

- ea: `0x18000c1d8`
- end: `0x18000c22a`
- name: `?_Unchecked_erase@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000da3e`

## callees

- `0x18000a554`
- `0x18000c1d8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c20e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c20e`

## pseudocode

```c
void __fastcall std::list<Command>::_Unchecked_erase(void **a1, void *a2)
{
  if ( a2 != *a1 )
  {
    **((_QWORD **)a2 + 1) = *(_QWORD *)a2;
    *(_QWORD *)(*(_QWORD *)a2 + 8LL) = *((_QWORD *)a2 + 1);
    Command::~Command((void **)a2 + 2);
    operator delete(a2);
    a1[1] = (char *)a1[1] - 1;
  }
}

```

## disassembly

```asm
0x18000c1d8  mov     [rsp+arg_0], rbx
0x18000c1dd  push    rdi
0x18000c1de  sub     rsp, 20h
0x18000c1e2  mov     rbx, rdx
0x18000c1e5  mov     rdi, rcx
0x18000c1e8  cmp     rdx, [rcx]
0x18000c1eb  jz      short loc_18000C21E
0x18000c1ed  mov     rdx, [rdx+8]
0x18000c1f1  lea     rcx, [rbx+10h]; this
0x18000c1f5  mov     rax, [rbx]
0x18000c1f8  mov     [rdx], rax
0x18000c1fb  mov     rdx, [rbx]
0x18000c1fe  mov     rax, [rbx+8]
0x18000c202  mov     [rdx+8], rax
0x18000c206  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x18000c20b  mov     rcx, rbx
0x18000c20e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c215  nop     dword ptr [rax+rax+00h]
0x18000c21a  dec     qword ptr [rdi+8]
0x18000c21e  mov     rbx, [rsp+28h+arg_0]
0x18000c223  add     rsp, 20h
0x18000c227  pop     rdi
0x18000c228  retn
```
