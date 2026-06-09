# std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,1>>::_Copy_nodes<0>(std::_Tree_node<ulong,void *> *,std::_Tree_node<ulong,void *> *)

- ea: `0x18000f428`
- end: `0x18000f4c3`
- name: `??$_Copy_nodes@$0A@@?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$00@std@@@std@@IEAAPEAU?$_Tree_node@KPEAX@1@PEAU21@0@Z`
- size: `155`
- prototype: `_DWORD *__fastcall(__int64 *, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f428`
- `0x18000fcfc`

## callees

- `0x180002a80`
- `0x18000f428`

## pseudocode

```c
_DWORD *__fastcall std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,1>>::_Copy_nodes<0>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rbp
  _DWORD *v7; // rbx

  v6 = *a1;
  if ( *(_BYTE *)(a2 + 25) )
    return (_DWORD *)*a1;
  v7 = operator new(0x20u);
  v7[7] = *(_DWORD *)(a2 + 28);
  *(_QWORD *)v7 = v6;
  *((_QWORD *)v7 + 2) = v6;
  *((_WORD *)v7 + 12) = 0;
  *((_QWORD *)v7 + 1) = a3;
  *((_BYTE *)v7 + 24) = *(_BYTE *)(a2 + 24);
  *(_QWORD *)v7 = std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,1>>::_Copy_nodes<0>(
                    a1,
                    *(_QWORD *)a2,
                    v7);
  *((_QWORD *)v7 + 2) = std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,1>>::_Copy_nodes<0>(
                          a1,
                          *(_QWORD *)(a2 + 16),
                          v7);
  return v7;
}

```

## disassembly

```asm
0x18000f428  push    rbx
0x18000f42a  push    rbp
0x18000f42b  push    rsi
0x18000f42c  push    rdi
0x18000f42d  push    r14
0x18000f42f  sub     rsp, 40h
0x18000f433  mov     r14, r8
0x18000f436  mov     rsi, rdx
0x18000f439  mov     rdi, rcx
0x18000f43c  mov     rbp, [rcx]
0x18000f43f  cmp     byte ptr [rdx+19h], 0
0x18000f443  jnz     short loc_18000F4B2
0x18000f445  mov     [rsp+68h+var_48], rcx
0x18000f44a  mov     [rsp+68h+var_40], 0
0x18000f453  mov     ecx, 20h ; ' '; Size
0x18000f458  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f45d  mov     rbx, rax
0x18000f460  mov     eax, [rsi+1Ch]
0x18000f463  mov     [rbx+1Ch], eax
0x18000f466  mov     [rbx], rbp
0x18000f469  mov     [rbx+10h], rbp
0x18000f46d  mov     word ptr [rbx+18h], 0
0x18000f473  mov     [rbx+8], r14
0x18000f477  mov     al, [rsi+18h]
0x18000f47a  mov     [rbx+18h], al
0x18000f47d  mov     [rsp+68h+var_48], rdi
0x18000f482  mov     [rsp+68h+var_40], rdi
0x18000f487  mov     [rsp+68h+var_38], rbx
0x18000f48c  mov     r8, rbx
0x18000f48f  mov     rdx, [rsi]
0x18000f492  mov     rcx, rdi
0x18000f495  call    ??$_Copy_nodes@$0A@@?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$00@std@@@std@@IEAAPEAU?$_Tree_node@KPEAX@1@PEAU21@0@Z; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,1>>::_Copy_nodes<0>(std::_Tree_node<ulong,void *> *,std::_Tree_node<ulong,void *> *)
0x18000f49a  mov     [rbx], rax
0x18000f49d  mov     r8, rbx
0x18000f4a0  mov     rdx, [rsi+10h]
0x18000f4a4  mov     rcx, rdi
0x18000f4a7  call    ??$_Copy_nodes@$0A@@?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$00@std@@@std@@IEAAPEAU?$_Tree_node@KPEAX@1@PEAU21@0@Z; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,1>>::_Copy_nodes<0>(std::_Tree_node<ulong,void *> *,std::_Tree_node<ulong,void *> *)
0x18000f4ac  mov     [rbx+10h], rax
0x18000f4b0  jmp     short loc_18000F4B5
0x18000f4b2  mov     rbx, rbp
0x18000f4b5  mov     rax, rbx
0x18000f4b8  add     rsp, 40h
0x18000f4bc  pop     r14
0x18000f4be  pop     rdi
0x18000f4bf  pop     rsi
0x18000f4c0  pop     rbp
0x18000f4c1  pop     rbx
0x18000f4c2  retn
```
