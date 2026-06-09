# std::list<Command,std::allocator<Command>>::_Unchecked_erase(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<Command>>,std::_Iterator_base0>)

- ea: `0x18000bb0c`
- end: `0x18000bb57`
- name: `?_Unchecked_erase@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `75`
- prototype: `void __fastcall(void **, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d372`

## callees

- `0x18000a050`
- `0x18000bb0c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000bb42`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bb42`

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
0x18000bb0c  mov     [rsp+arg_0], rbx
0x18000bb11  push    rdi
0x18000bb12  sub     rsp, 20h
0x18000bb16  mov     rbx, rdx
0x18000bb19  mov     rdi, rcx
0x18000bb1c  cmp     rdx, [rcx]
0x18000bb1f  jz      short loc_18000BB4C
0x18000bb21  mov     rdx, [rdx+8]
0x18000bb25  lea     rcx, [rbx+10h]; this
0x18000bb29  mov     rax, [rbx]
0x18000bb2c  mov     [rdx], rax
0x18000bb2f  mov     rdx, [rbx]
0x18000bb32  mov     rax, [rbx+8]
0x18000bb36  mov     [rdx+8], rax
0x18000bb3a  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x18000bb3f  mov     rcx, rbx
0x18000bb42  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000bb48  dec     qword ptr [rdi+8]
0x18000bb4c  mov     rbx, [rsp+28h+arg_0]
0x18000bb51  add     rsp, 20h
0x18000bb55  pop     rdi
0x18000bb56  retn
```
