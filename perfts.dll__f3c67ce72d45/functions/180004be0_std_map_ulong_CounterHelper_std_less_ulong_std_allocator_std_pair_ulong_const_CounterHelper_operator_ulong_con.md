# std::map<ulong,CounterHelper *,std::less<ulong>,std::allocator<std::pair<ulong const,CounterHelper *>>>::operator[](ulong const &)

- ea: `0x180004be0`
- end: `0x180004c6e`
- name: `??A?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@QEAAAEAPEAVCounterHelper@@AEBK@Z`
- size: `142`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800058b8`
- `0x180006214`
- `0x180007668`
- `0x180008074`

## callees

- `0x1800041ec`
- `0x1800044a4`
- `0x180004be0`

## pseudocode

```c
__int64 *__fastcall std::map<unsigned long,CounterHelper *>::operator[](__int64 **a1, int *a2)
{
  __int64 *v2; // rbx
  int v3; // edi
  __int64 *v4; // r8
  __int64 *v5; // rax
  __int64 v6; // rax
  int v8; // [rsp+30h] [rbp-18h] BYREF
  __int64 v9; // [rsp+38h] [rbp-10h]
  __int64 *v10; // [rsp+50h] [rbp+8h] BYREF

  v2 = *a1;
  v3 = (int)a1;
  v4 = (__int64 *)(*a1)[1];
  if ( *((_BYTE *)v4 + 25) )
    goto LABEL_8;
  do
  {
    if ( *((_DWORD *)v4 + 8) >= (unsigned int)*a2 )
    {
      v2 = v4;
      v4 = (__int64 *)*v4;
    }
    else
    {
      v4 = (__int64 *)v4[2];
    }
    v5 = v2;
  }
  while ( !*((_BYTE *)v4 + 25) );
  if ( v2 == *a1 || (unsigned int)*a2 < *((_DWORD *)v2 + 8) )
  {
LABEL_8:
    v8 = *a2;
    v9 = 0;
    v6 = std::_Tree_buy<std::pair<unsigned long const,CounterHelper *>>::_Buynode<std::pair<unsigned long,CounterHelper *>>(
           a1,
           &v8);
    std::_Tree<std::_Tmap_traits<unsigned long,CounterHelper *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CounterHelper *>>,0>>::_Insert_hint<std::pair<unsigned long const,CounterHelper *> &,std::_Tree_node<std::pair<unsigned long const,CounterHelper *>,void *> *>(
      v3,
      (unsigned int)&v10,
      (_DWORD)v2,
      v6 + 32,
      v6);
    v5 = v10;
  }
  return v5 + 5;
}

```

## disassembly

```asm
0x180004be0  mov     [rsp+arg_8], rbx
0x180004be5  push    rdi
0x180004be6  sub     rsp, 40h
0x180004bea  mov     rbx, [rcx]
0x180004bed  xor     r10d, r10d
0x180004bf0  mov     rdi, rcx
0x180004bf3  mov     r8, [rbx+8]
0x180004bf7  cmp     [r8+19h], r10b
0x180004bfb  jnz     short loc_180004C29
0x180004bfd  mov     ecx, [rdx]
0x180004bff  mov     r9, rbx
0x180004c02  cmp     [r8+20h], ecx
0x180004c06  jnb     short loc_180004C0E
0x180004c08  mov     r8, [r8+10h]
0x180004c0c  jmp     short loc_180004C14
0x180004c0e  mov     rbx, r8
0x180004c11  mov     r8, [r8]
0x180004c14  mov     rax, rbx
0x180004c17  cmp     [r8+19h], r10b
0x180004c1b  jz      short loc_180004C02
0x180004c1d  cmp     rax, r9
0x180004c20  jz      short loc_180004C29
0x180004c22  mov     ecx, [rbx+20h]
0x180004c25  cmp     [rdx], ecx
0x180004c27  jnb     short loc_180004C5F
0x180004c29  mov     eax, [rdx]
0x180004c2b  mov     rcx, rdi
0x180004c2e  lea     rdx, [rsp+48h+var_18]
0x180004c33  mov     [rsp+48h+var_18], eax
0x180004c37  mov     [rsp+48h+var_10], r10
0x180004c3c  call    ??$_Buynode@U?$pair@KPEAVCounterHelper@@@std@@@?$_Tree_buy@U?$pair@$$CBKPEAVCounterHelper@@@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKPEAVCounterHelper@@@std@@PEAX@1@$$QEAU?$pair@KPEAVCounterHelper@@@1@@Z; std::_Tree_buy<std::pair<ulong const,CounterHelper *>>::_Buynode<std::pair<ulong,CounterHelper *>>(std::pair<ulong,CounterHelper *> &&)
0x180004c41  mov     r8, rbx
0x180004c44  mov     [rsp+48h+var_28], rax
0x180004c49  lea     rdx, [rsp+48h+arg_0]
0x180004c4e  mov     rcx, rdi
0x180004c51  lea     r9, [rax+20h]
0x180004c55  call    ??$_Insert_hint@AEAU?$pair@$$CBKPEAVCounterHelper@@@std@@PEAU?$_Tree_node@U?$pair@$$CBKPEAVCounterHelper@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAVCounterHelper@@@std@@@std@@@std@@@1@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAVCounterHelper@@@std@@@std@@@std@@@1@AEAU?$pair@$$CBKPEAVCounterHelper@@@1@PEAU?$_Tree_node@U?$pair@$$CBKPEAVCounterHelper@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<ulong,CounterHelper *,std::less<ulong>,std::allocator<std::pair<ulong const,CounterHelper *>>,0>>::_Insert_hint<std::pair<ulong const,CounterHelper *> &,std::_Tree_node<std::pair<ulong const,CounterHelper *>,void *> *>(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CounterHelper *>>>>,std::pair<ulong const,CounterHelper *> &,std::_Tree_node<std::pair<ulong const,CounterHelper *>,void *> *)
0x180004c5a  mov     rax, [rsp+48h+arg_0]
0x180004c5f  mov     rbx, [rsp+48h+arg_8]
0x180004c64  add     rax, 28h ; '('
0x180004c68  add     rsp, 40h
0x180004c6c  pop     rdi
0x180004c6d  retn
```
