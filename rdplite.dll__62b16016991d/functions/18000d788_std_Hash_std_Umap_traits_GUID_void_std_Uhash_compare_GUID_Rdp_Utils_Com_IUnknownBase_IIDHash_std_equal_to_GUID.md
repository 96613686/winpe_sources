# std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::insert(std::initializer_list<std::pair<_GUID const,void *>>)

- ea: `0x18000d788`
- end: `0x18000d7cc`
- name: `?insert@?$_Hash@V?$_Umap_traits@U_GUID@@PEAXV?$_Uhash_compare@U_GUID@@UIIDHash@IUnknownBase@Com@Utils@Rdp@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAX@std@@@3@$0A@@std@@@std@@QEAAXV?$initializer_list@U?$pair@$$CBU_GUID@@PEAX@std@@@2@@Z`
- size: `68`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a00c`
- `0x18000a3f4`
- `0x18000a4d8`
- `0x18000f39c`
- `0x18000f908`
- `0x18001339c`
- `0x180016a90`
- `0x1800182b4`
- `0x18001c6d4`
- `0x18001c914`
- `0x1800200d8`
- `0x1800231d4`

## callees

- `0x180009e04`
- `0x18000d788`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::insert(
        __int64 a1,
        __int64 *a2)
{
  __int64 v2; // rdi
  __int64 i; // rbx
  __int64 result; // rax
  _BYTE v6[24]; // [rsp+20h] [rbp-18h] BYREF

  v2 = a2[1];
  for ( i = *a2; i != v2; i += 24 )
    result = std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::emplace<std::pair<_GUID const,void *> const &>(
               a1,
               v6,
               i);
  return result;
}

```

## disassembly

```asm
0x18000d788  mov     [rsp+arg_0], rbx
0x18000d78d  mov     [rsp+arg_8], rsi
0x18000d792  push    rdi
0x18000d793  sub     rsp, 30h
0x18000d797  mov     rdi, [rdx+8]
0x18000d79b  mov     rsi, rcx
0x18000d79e  mov     rbx, [rdx]
0x18000d7a1  jmp     short loc_18000D7B7
0x18000d7a3  mov     r8, rbx
0x18000d7a6  lea     rdx, [rsp+38h+var_18]
0x18000d7ab  mov     rcx, rsi
0x18000d7ae  call    ??$emplace@AEBU?$pair@$$CBU_GUID@@PEAX@std@@@?$_Hash@V?$_Umap_traits@U_GUID@@PEAXV?$_Uhash_compare@U_GUID@@UIIDHash@IUnknownBase@Com@Utils@Rdp@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAX@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@PEAX@std@@@std@@@std@@@std@@_N@1@AEBU?$pair@$$CBU_GUID@@PEAX@1@@Z; std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::emplace<std::pair<_GUID const,void *> const &>(std::pair<_GUID const,void *> const &)
0x18000d7b3  add     rbx, 18h
0x18000d7b7  cmp     rbx, rdi
0x18000d7ba  jnz     short loc_18000D7A3
0x18000d7bc  mov     rbx, [rsp+38h+arg_0]
0x18000d7c1  mov     rsi, [rsp+38h+arg_8]
0x18000d7c6  add     rsp, 30h
0x18000d7ca  pop     rdi
0x18000d7cb  retn
```
