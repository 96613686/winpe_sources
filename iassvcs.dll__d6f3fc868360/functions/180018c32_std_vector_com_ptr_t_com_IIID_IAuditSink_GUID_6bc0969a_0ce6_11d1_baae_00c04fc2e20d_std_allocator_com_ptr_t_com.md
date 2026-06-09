# _std::vector__com_ptr_t__com_IIID_IAuditSink_&_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d____std::allocator__com_ptr_t__com_IIID_IAuditSink_&_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d_______::_Reallocate_::_1_::catch$1

- ea: `0x180018c32`
- end: `0x180018c52`
- name: `_std::vector__com_ptr_t__com_IIID_IAuditSink_&_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d____std::allocator__com_ptr_t__com_IIID_IAuditSink_&_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d_______::_Reallocate_::_1_::catch$1`
- size: `32`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001e0e`
- `0x180012c14`

## pseudocode

```c
void __fastcall __noreturn std::vector__com_ptr_t__com_IIID_IAuditSink___GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d____std::allocator__com_ptr_t__com_IIID_IAuditSink___GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d_______::_Reallocate_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  std::_Tree_buy<std::pair<std::wstring const,_RadiusClientEntry *>>::_Freenode0(a1, *(void **)(a2 + 104));
  throw;
}

```

## disassembly

```asm
0x180018c32  mov     [rsp+arg_8], rdx
0x180018c37  push    rbp
0x180018c38  sub     rsp, 30h
0x180018c3c  mov     rbp, rdx
0x180018c3f  mov     rdx, [rbp+68h]
0x180018c43  call    ?_Freenode0@?$_Tree_buy@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_RadiusClientEntry@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_RadiusClientEntry@@@std@@@2@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_RadiusClientEntry@@@std@@PEAX@2@@Z; std::_Tree_buy<std::pair<std::wstring const,_RadiusClientEntry *>>::_Freenode0(std::_Tree_node<std::pair<std::wstring const,_RadiusClientEntry *>,void *> *)
0x180018c48  xor     edx, edx; pThrowInfo
0x180018c4a  xor     ecx, ecx; pExceptionObject
0x180018c4c  call    _CxxThrowException_0
```
