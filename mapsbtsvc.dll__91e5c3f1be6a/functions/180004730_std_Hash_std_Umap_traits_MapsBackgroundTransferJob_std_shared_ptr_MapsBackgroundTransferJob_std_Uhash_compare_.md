# std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Clear_guard::~_Clear_guard(void)

- ea: `0x180004730`
- end: `0x1800047a7`
- name: `??1_Clear_guard@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ`
- size: `119`
- prototype: `unsigned __int64 __fastcall(_QWORD *)`
- caller_count: `11`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005070`
- `0x1800051b0`
- `0x180005354`
- `0x1800056d0`
- `0x180005820`
- `0x180005e8c`
- `0x180013d12`
- `0x180013d5a`
- `0x180013d90`
- `0x180013db4`
- `0x180013dea`

## callees

- `0x180003dbc`
- `0x180004024`
- `0x180004730`
- `0x18000617c`

## pseudocode

```c
unsigned __int64 __fastcall std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Clear_guard::~_Clear_guard(
        _QWORD *a1)
{
  _QWORD *v1; // rbx
  _QWORD *v2; // rdx
  unsigned __int64 result; // rax
  unsigned __int64 *v4; // rdx
  unsigned __int64 *v5; // rcx
  unsigned __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v1 = (_QWORD *)*a1;
  if ( *a1 && v1[2] )
  {
    v2 = (_QWORD *)v1[1];
    if ( v1[7] >> 3 <= v1[2] )
    {
      std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *>>>(
        a1,
        v2);
      *(_QWORD *)v1[1] = v1[1];
      *(_QWORD *)(v1[1] + 8LL) = v1[1];
      v1[2] = 0;
      v4 = (unsigned __int64 *)v1[4];
      v5 = (unsigned __int64 *)v1[3];
      v6 = v1[1];
      return std::fill<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>>>(
               v5,
               v4,
               &v6);
    }
    else
    {
      return std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Unchecked_erase(
               *a1,
               *v2,
               v1[1]);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004730  push    rbx
0x180004732  sub     rsp, 20h
0x180004736  mov     rbx, [rcx]
0x180004739  test    rbx, rbx
0x18000473c  jz      short loc_1800047A1
0x18000473e  cmp     qword ptr [rbx+10h], 0
0x180004743  jz      short loc_1800047A1
0x180004745  mov     rax, [rbx+38h]
0x180004749  mov     rdx, [rbx+8]
0x18000474d  shr     rax, 3
0x180004751  cmp     rax, [rbx+10h]
0x180004755  jbe     short loc_18000476A
0x180004757  mov     r8, rdx
0x18000475a  mov     rcx, rbx
0x18000475d  mov     rdx, [rdx]
0x180004760  add     rsp, 20h
0x180004764  pop     rbx
0x180004765  jmp     ?_Unchecked_erase@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@PEAX@2@PEAU32@QEAU32@@Z; std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Unchecked_erase(std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *> *,std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *> * const)
0x18000476a  call    ??$_Free_non_head@V?$allocator@U?$_List_node@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *>>>(std::allocator<std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *>> &,std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *> *)
0x18000476f  mov     rax, [rbx+8]
0x180004773  lea     r8, [rsp+28h+arg_0]
0x180004778  mov     [rax], rax
0x18000477b  mov     rax, [rbx+8]
0x18000477f  mov     [rax+8], rax
0x180004783  mov     qword ptr [rbx+10h], 0
0x18000478b  mov     rax, [rbx+8]
0x18000478f  mov     rdx, [rbx+20h]
0x180004793  mov     rcx, [rbx+18h]
0x180004797  mov     [rsp+28h+arg_0], rax
0x18000479c  call    ??$fill@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@std@@@std@@@std@@V12@@std@@YAXQEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@std@@@std@@@0@0AEBV10@@Z; std::fill<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>> * const,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>> * const,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>> const &)
0x1800047a1  add     rsp, 20h
0x1800047a5  pop     rbx
0x1800047a6  retn
```
