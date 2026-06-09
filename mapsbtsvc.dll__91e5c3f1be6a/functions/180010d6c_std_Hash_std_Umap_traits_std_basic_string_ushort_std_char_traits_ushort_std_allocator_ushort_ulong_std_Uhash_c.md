# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ulong>>,0>>::clear(void)

- ea: `0x180010d6c`
- end: `0x180010ddb`
- name: `?clear@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAAXXZ`
- size: `111`
- prototype: `unsigned __int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b6a4`
- `0x18000dd10`

## callees

- `0x180004024`
- `0x180009fb8`
- `0x180010994`
- `0x180010d6c`

## pseudocode

```c
unsigned __int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::clear(
        _QWORD *a1)
{
  __int64 *v2; // rdx
  unsigned __int64 result; // rax
  unsigned __int64 *v4; // rdx
  unsigned __int64 *v5; // rcx
  unsigned __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  if ( a1[2] )
  {
    v2 = (__int64 *)a1[1];
    if ( a1[7] >> 3 <= a1[2] )
    {
      std::_List_node<std::pair<std::wstring const,unsigned long>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<std::wstring const,unsigned long>,void *>>>(
        a1,
        v2);
      *(_QWORD *)a1[1] = a1[1];
      *(_QWORD *)(a1[1] + 8LL) = a1[1];
      a1[2] = 0;
      v4 = (unsigned __int64 *)a1[4];
      v5 = (unsigned __int64 *)a1[3];
      v6 = a1[1];
      return std::fill<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>>>(
               v5,
               v4,
               &v6);
    }
    else
    {
      return std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Unchecked_erase(
               a1,
               *v2,
               a1[1]);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180010d6c  push    rbx
0x180010d6e  sub     rsp, 20h
0x180010d72  cmp     qword ptr [rcx+10h], 0
0x180010d77  mov     rbx, rcx
0x180010d7a  jz      short loc_180010DD5
0x180010d7c  mov     rax, [rcx+38h]
0x180010d80  mov     rdx, [rcx+8]
0x180010d84  shr     rax, 3
0x180010d88  cmp     rax, [rcx+10h]
0x180010d8c  jbe     short loc_180010D9E
0x180010d8e  mov     r8, rdx
0x180010d91  mov     rdx, [rdx]
0x180010d94  add     rsp, 20h
0x180010d98  pop     rbx
0x180010d99  jmp     ?_Unchecked_erase@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@2@PEAU32@QEAU32@@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Unchecked_erase(std::_List_node<std::pair<std::wstring const,ulong>,void *> *,std::_List_node<std::pair<std::wstring const,ulong>,void *> * const)
0x180010d9e  call    ??$_Free_non_head@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<std::wstring const,ulong>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<std::wstring const,ulong>,void *>>>(std::allocator<std::_List_node<std::pair<std::wstring const,ulong>,void *>> &,std::_List_node<std::pair<std::wstring const,ulong>,void *> *)
0x180010da3  mov     rax, [rbx+8]
0x180010da7  lea     r8, [rsp+28h+arg_0]
0x180010dac  mov     [rax], rax
0x180010daf  mov     rax, [rbx+8]
0x180010db3  mov     [rax+8], rax
0x180010db7  mov     qword ptr [rbx+10h], 0
0x180010dbf  mov     rax, [rbx+8]
0x180010dc3  mov     rdx, [rbx+20h]
0x180010dc7  mov     rcx, [rbx+18h]
0x180010dcb  mov     [rsp+28h+arg_0], rax
0x180010dd0  call    ??$fill@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@std@@@std@@@std@@V12@@std@@YAXQEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@std@@@std@@@0@0AEBV10@@Z; std::fill<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>> * const,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>> * const,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>> const &)
0x180010dd5  add     rsp, 20h
0x180010dd9  pop     rbx
0x180010dda  retn
```
