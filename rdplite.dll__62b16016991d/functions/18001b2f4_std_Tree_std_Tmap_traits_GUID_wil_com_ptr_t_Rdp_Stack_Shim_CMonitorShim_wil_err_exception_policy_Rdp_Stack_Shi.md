# std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>,Rdp::Stack::Shim::CAdapterShim::MonitorIdComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>,0>>::find(_GUID const &)

- ea: `0x18001b2f4`
- end: `0x18001b343`
- name: `?find@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@UMonitorIdComparer@CAdapterShim@Shim@Stack@Rdp@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z`
- size: `79`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018f90`
- `0x1800192c4`
- `0x180019894`
- `0x18001aac8`

## callees

- `0x1800180e8`
- `0x18001819c`
- `0x18001b2f4`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>,Rdp::Stack::Shim::CAdapterShim::MonitorIdComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>,0>>::find(
        __int64 *a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 v6; // r8
  __int64 v7; // rbx
  __int64 v8; // rcx
  _QWORD *result; // rax
  _BYTE v10[16]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v11; // [rsp+30h] [rbp-18h]

  std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>,Rdp::Stack::Shim::CAdapterShim::MonitorIdComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>,0>>::_Find_lower_bound<_GUID>(
    a1,
    v10);
  v6 = a3;
  v7 = v11;
  if ( !(unsigned __int8)std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>,Rdp::Stack::Shim::CAdapterShim::MonitorIdComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>,0>>::_Lower_bound_duplicate<_GUID>(
                           v8,
                           v11,
                           v6) )
    v7 = *a1;
  result = a2;
  *a2 = v7;
  return result;
}

```

## disassembly

```asm
0x18001b2f4  mov     [rsp+arg_0], rbx
0x18001b2f9  mov     [rsp+arg_8], rsi
0x18001b2fe  push    rdi
0x18001b2ff  sub     rsp, 40h
0x18001b303  mov     rdi, rdx
0x18001b306  mov     rbx, r8
0x18001b309  lea     rdx, [rsp+48h+var_28]
0x18001b30e  mov     rsi, rcx
0x18001b311  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@UMonitorIdComparer@CAdapterShim@Shim@Stack@Rdp@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>,Rdp::Stack::Shim::CAdapterShim::MonitorIdComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x18001b316  mov     r8, rbx
0x18001b319  mov     rbx, [rsp+48h+var_18]
0x18001b31e  mov     rdx, rbx
0x18001b321  call    ??$_Lower_bound_duplicate@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@UMonitorIdComparer@CAdapterShim@Shim@Stack@Rdp@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>,Rdp::Stack::Shim::CAdapterShim::MonitorIdComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>,0>>::_Lower_bound_duplicate<_GUID>(std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *> * const,_GUID const &)
0x18001b326  test    al, al
0x18001b328  jnz     short loc_18001B32D
0x18001b32a  mov     rbx, [rsi]
0x18001b32d  mov     rsi, [rsp+48h+arg_8]
0x18001b332  mov     rax, rdi
0x18001b335  mov     [rdi], rbx
0x18001b338  mov     rbx, [rsp+48h+arg_0]
0x18001b33d  add     rsp, 40h
0x18001b341  pop     rdi
0x18001b342  retn
```
