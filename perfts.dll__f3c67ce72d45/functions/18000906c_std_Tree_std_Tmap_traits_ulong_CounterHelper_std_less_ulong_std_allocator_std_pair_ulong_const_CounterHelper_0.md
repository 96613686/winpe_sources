# std::_Tree<std::_Tmap_traits<ulong,CounterHelper *,std::less<ulong>,std::allocator<std::pair<ulong const,CounterHelper *>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CounterHelper *>>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CounterHelper *>>>>)

- ea: `0x18000906c`
- end: `0x180009153`
- name: `?erase@?$_Tree@V?$_Tmap_traits@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAVCounterHelper@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAVCounterHelper@@@std@@@std@@@std@@@2@0@Z`
- size: `231`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800095e8`
- `0x18000a260`
- `0x18000a2a0`
- `0x18000a2e0`

## callees

- `0x180008f38`
- `0x18000906c`
- `0x18000915c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800090af`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800090af`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 **__fastcall std::_Tree<std::_Tmap_traits<unsigned long,CounterHelper *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CounterHelper *>>,0>>::erase(
        __int64 ***a1,
        __int64 **a2,
        __int64 *a3,
        __int64 *a4)
{
  __int64 *v5; // rbx
  __int64 **v8; // rax
  __int64 *v9; // rbx
  __int64 *j; // rdi
  __int64 *v11; // r8
  __int64 *i; // rax
  __int64 *v13; // rcx
  char v15; // [rsp+50h] [rbp+8h] BYREF

  v5 = a3;
  v8 = *a1;
  if ( a3 != **a1 || a4 != (__int64 *)v8 )
  {
    while ( 1 )
    {
      if ( v5 == a4 )
      {
        *a2 = v5;
        return a2;
      }
      v11 = v5;
      if ( !*((_BYTE *)v5 + 25) )
      {
        i = (__int64 *)v5[2];
        if ( *((_BYTE *)i + 25) )
        {
          for ( i = (__int64 *)v5[1]; !*((_BYTE *)i + 25) && v5 == (__int64 *)i[2]; i = (__int64 *)i[1] )
            v5 = i;
LABEL_16:
          v5 = i;
          goto LABEL_17;
        }
        v13 = (__int64 *)*i;
        if ( *(_BYTE *)(*i + 25) )
          goto LABEL_16;
        do
        {
          v5 = v13;
          v13 = (__int64 *)*v13;
        }
        while ( !*((_BYTE *)v13 + 25) );
      }
LABEL_17:
      std::_Tree<std::_Tmap_traits<unsigned long,CounterHelper *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CounterHelper *>>,0>>::erase(
        a1,
        &v15,
        v11);
    }
  }
  v9 = v8[1];
  for ( j = v9; !*((_BYTE *)j + 25); v9 = j )
  {
    std::_Tree<std::_Tmap_traits<unsigned long,CounterHelper *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CounterHelper *>>,0>>::_Erase(
      a1,
      j[2]);
    j = (__int64 *)*j;
    operator delete(v9);
  }
  (*a1)[1] = (__int64 *)*a1;
  **a1 = (__int64 *)*a1;
  (*a1)[2] = (__int64 *)*a1;
  a1[1] = 0;
  *a2 = **a1;
  return a2;
}

```

## disassembly

```asm
0x18000906c  push    rbx
0x18000906e  push    rdi
0x18000906f  push    r14
0x180009071  push    r15
0x180009073  sub     rsp, 28h
0x180009077  mov     rdi, r9
0x18000907a  mov     rbx, r8
0x18000907d  mov     r15, rdx
0x180009080  mov     r14, rcx
0x180009083  mov     rax, [rcx]
0x180009086  cmp     r8, [rax]
0x180009089  jnz     short loc_1800090E5
0x18000908b  cmp     r9, rax
0x18000908e  jnz     short loc_1800090E5
0x180009090  mov     rbx, [rax+8]
0x180009094  mov     rdi, rbx
0x180009097  cmp     byte ptr [rbx+19h], 0
0x18000909b  jnz     short loc_1800090BE
0x18000909d  mov     rdx, [rdi+10h]
0x1800090a1  mov     rcx, r14
0x1800090a4  call    ?_Erase@?$_Tree@V?$_Tmap_traits@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBKPEAVCounterHelper@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ulong,CounterHelper *,std::less<ulong>,std::allocator<std::pair<ulong const,CounterHelper *>>,0>>::_Erase(std::_Tree_node<std::pair<ulong const,CounterHelper *>,void *> *)
0x1800090a9  mov     rdi, [rdi]
0x1800090ac  mov     rcx, rbx
0x1800090af  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800090b5  mov     rbx, rdi
0x1800090b8  cmp     byte ptr [rdi+19h], 0
0x1800090bc  jz      short loc_18000909D
0x1800090be  mov     rax, [r14]
0x1800090c1  mov     [rax+8], rax
0x1800090c5  mov     rax, [r14]
0x1800090c8  mov     [rax], rax
0x1800090cb  mov     rax, [r14]
0x1800090ce  mov     [rax+10h], rax
0x1800090d2  mov     qword ptr [r14+8], 0
0x1800090da  mov     rax, [r14]
0x1800090dd  mov     rcx, [rax]
0x1800090e0  mov     [r15], rcx
0x1800090e3  jmp     short loc_180009145
0x1800090e5  cmp     rbx, rdi
0x1800090e8  jz      short loc_180009142
0x1800090ea  mov     r8, rbx
0x1800090ed  cmp     byte ptr [rbx+19h], 0
0x1800090f1  jnz     short loc_180009133
0x1800090f3  mov     rax, [rbx+10h]
0x1800090f7  cmp     byte ptr [rax+19h], 0
0x1800090fb  jnz     short loc_180009117
0x1800090fd  mov     rcx, [rax]
0x180009100  cmp     byte ptr [rcx+19h], 0
0x180009104  jnz     short loc_180009130
0x180009106  mov     rbx, rcx
0x180009109  mov     rax, [rcx]
0x18000910c  mov     rcx, rax
0x18000910f  cmp     byte ptr [rax+19h], 0
0x180009113  jz      short loc_180009106
0x180009115  jmp     short loc_180009133
0x180009117  mov     rax, [rbx+8]
0x18000911b  jmp     short loc_18000912A
0x18000911d  cmp     rbx, [rax+10h]
0x180009121  jnz     short loc_180009130
0x180009123  mov     rbx, rax
0x180009126  mov     rax, [rax+8]
0x18000912a  cmp     byte ptr [rax+19h], 0
0x18000912e  jz      short loc_18000911D
0x180009130  mov     rbx, rax
0x180009133  lea     rdx, [rsp+48h+arg_0]
0x180009138  mov     rcx, r14
0x18000913b  call    ?erase@?$_Tree@V?$_Tmap_traits@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAVCounterHelper@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAVCounterHelper@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<ulong,CounterHelper *,std::less<ulong>,std::allocator<std::pair<ulong const,CounterHelper *>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CounterHelper *>>>>)
0x180009140  jmp     short loc_1800090E5
0x180009142  mov     [r15], rbx
0x180009145  mov     rax, r15
0x180009148  add     rsp, 28h
0x18000914c  pop     r15
0x18000914e  pop     r14
0x180009150  pop     rdi
0x180009151  pop     rbx
0x180009152  retn
```
