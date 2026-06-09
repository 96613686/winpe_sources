# std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::~_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>(void)

- ea: `0x18000a640`
- end: `0x18000a696`
- name: `??1?$_Hash@V?$_Umap_traits@U_GUID@@PEAXV?$_Uhash_compare@U_GUID@@UIIDHash@IUnknownBase@Com@Utils@Rdp@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAX@std@@@3@$0A@@std@@@std@@QEAA@XZ`
- size: `86`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `17`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a60c`
- `0x18000a7bc`
- `0x18000a8c4`
- `0x18000aac0`
- `0x18000ab00`
- `0x18000abc0`
- `0x18000fd10`
- `0x18000ff14`
- `0x1800135bc`
- `0x180017290`
- `0x18001888c`
- `0x180018a40`
- `0x18001cc8c`
- `0x18001ccec`
- `0x18002097c`
- `0x180020c30`
- `0x180028944`

## callees

- `0x1800049b8`
- `0x180009d30`
- `0x18000a640`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::~_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>(
        _QWORD *a1)
{
  __int64 v2; // rcx

  v2 = a1[3];
  if ( v2 )
  {
    std::_Deallocate<16>(v2, (a1[5] - v2) & 0xFFFFFFFFFFFFFFF8uLL);
    a1[3] = 0;
    a1[4] = 0;
    a1[5] = 0;
  }
  std::_List_node<std::pair<_GUID const,void *>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<_GUID const,void *>,void *>>>(
    v2,
    a1[1]);
  return std::_Deallocate<16>(a1[1], 40);
}

```

## disassembly

```asm
0x18000a640  push    rbx
0x18000a642  sub     rsp, 20h
0x18000a646  mov     rbx, rcx
0x18000a649  mov     rcx, [rcx+18h]
0x18000a64d  test    rcx, rcx
0x18000a650  jz      short loc_18000A67A
0x18000a652  mov     rdx, [rbx+28h]
0x18000a656  sub     rdx, rcx
0x18000a659  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000a65d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000a662  mov     qword ptr [rbx+18h], 0
0x18000a66a  mov     qword ptr [rbx+20h], 0
0x18000a672  mov     qword ptr [rbx+28h], 0
0x18000a67a  mov     rdx, [rbx+8]
0x18000a67e  call    ??$_Free_non_head@V?$allocator@U?$_List_node@U?$pair@$$CBU_GUID@@PEAX@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBU_GUID@@PEAX@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBU_GUID@@PEAX@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<_GUID const,void *>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<_GUID const,void *>,void *>>>(std::allocator<std::_List_node<std::pair<_GUID const,void *>,void *>> &,std::_List_node<std::pair<_GUID const,void *>,void *> *)
0x18000a683  mov     rcx, [rbx+8]
0x18000a687  mov     edx, 28h ; '('
0x18000a68c  add     rsp, 20h
0x18000a690  pop     rbx
0x18000a691  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
