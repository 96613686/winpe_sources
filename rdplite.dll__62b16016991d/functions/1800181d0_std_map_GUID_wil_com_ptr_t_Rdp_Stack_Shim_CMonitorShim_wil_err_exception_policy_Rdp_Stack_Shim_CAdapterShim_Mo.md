# std::map<_GUID,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>,Rdp::Stack::Shim::CAdapterShim::MonitorIdComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Try_emplace<_GUID const &,>(_GUID const &)

- ea: `0x1800181d0`
- end: `0x1800182ae`
- name: `??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@UMonitorIdComparer@CAdapterShim@Shim@Stack@Rdp@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z`
- size: `222`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018afc`

## callees

- `0x180003714`
- `0x180008be0`
- `0x1800180e8`
- `0x18001819c`
- `0x1800181d0`
- `0x180018764`
- `0x18001b0fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::map<_GUID,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>,Rdp::Stack::Shim::CAdapterShim::MonitorIdComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Try_emplace<_GUID const &,>(
        __int64 *a1,
        __int64 a2,
        _OWORD *a3)
{
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rbx
  _OWORD *v9; // rdi
  __int128 v11; // [rsp+20h] [rbp-58h] BYREF
  __int128 v12; // [rsp+30h] [rbp-48h] BYREF
  __int64 v13; // [rsp+40h] [rbp-38h]

  std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>,Rdp::Stack::Shim::CAdapterShim::MonitorIdComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>,0>>::_Find_lower_bound<_GUID>(
    a1,
    &v12);
  v6 = v13;
  if ( (unsigned __int8)std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>,Rdp::Stack::Shim::CAdapterShim::MonitorIdComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>,0>>::_Lower_bound_duplicate<_GUID>(
                          v7,
                          v13,
                          a3) )
  {
    *(_QWORD *)a2 = v6;
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( a1[1] == 0x492492492492492LL )
      std::_Xlength_error("map/set too long");
    v8 = *a1;
    v11 = (unsigned __int64)a1;
    v9 = operator new(0x38u);
    v9[2] = *a3;
    *((_QWORD *)v9 + 6) = 0;
    *(_QWORD *)v9 = v8;
    *((_QWORD *)v9 + 1) = v8;
    *((_QWORD *)v9 + 2) = v8;
    *((_WORD *)v9 + 12) = 0;
    *((_QWORD *)&v11 + 1) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *>>>(&v11);
    v11 = v12;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Insert_node(
                      a1,
                      &v11,
                      v9);
    *(_BYTE *)(a2 + 8) = 1;
  }
  return a2;
}

```

## disassembly

```asm
0x1800181d0  push    rbx
0x1800181d2  push    rbp
0x1800181d3  push    rsi
0x1800181d4  push    rdi
0x1800181d5  push    r14
0x1800181d7  sub     rsp, 50h
0x1800181db  mov     rbp, r8
0x1800181de  mov     rsi, rdx
0x1800181e1  mov     r14, rcx
0x1800181e4  lea     rdx, [rsp+78h+var_48]
0x1800181e9  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@UMonitorIdComparer@CAdapterShim@Shim@Stack@Rdp@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>,Rdp::Stack::Shim::CAdapterShim::MonitorIdComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x1800181ee  mov     r8, rbp
0x1800181f1  mov     rbx, [rsp+78h+var_38]
0x1800181f6  mov     rdx, rbx
0x1800181f9  call    ??$_Lower_bound_duplicate@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@UMonitorIdComparer@CAdapterShim@Shim@Stack@Rdp@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>,Rdp::Stack::Shim::CAdapterShim::MonitorIdComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>,0>>::_Lower_bound_duplicate<_GUID>(std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *> * const,_GUID const &)
0x1800181fe  test    al, al
0x180018200  jz      short loc_18001820E
0x180018202  mov     [rsi], rbx
0x180018205  mov     byte ptr [rsi+8], 0
0x180018209  jmp     loc_1800182A0
0x18001820e  mov     rax, 492492492492492h
0x180018218  cmp     [r14+8], rax
0x18001821c  jnz     short loc_18001822B
0x18001821e  lea     rcx, aMapSetTooLong; "map/set too long"
0x180018225  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001822b  mov     rbx, [r14]
0x18001822e  mov     qword ptr [rsp+78h+var_58], r14
0x180018233  mov     qword ptr [rsp+78h+var_58+8], 0
0x18001823c  mov     ecx, 38h ; '8'; Size
0x180018241  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018246  mov     rdi, rax
0x180018249  movups  xmm0, xmmword ptr [rbp+0]
0x18001824d  movdqu  xmmword ptr [rax+20h], xmm0
0x180018252  mov     qword ptr [rax+30h], 0
0x18001825a  mov     [rax], rbx
0x18001825d  mov     [rax+8], rbx
0x180018261  mov     [rax+10h], rbx
0x180018265  mov     word ptr [rax+18h], 0
0x18001826b  mov     qword ptr [rsp+78h+var_58+8], 0
0x180018274  lea     rcx, [rsp+78h+var_58]
0x180018279  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *>>>(void)
0x18001827e  movups  xmm0, [rsp+78h+var_48]
0x180018283  movdqu  [rsp+78h+var_58], xmm0
0x180018289  mov     r8, rdi
0x18001828c  lea     rdx, [rsp+78h+var_58]
0x180018291  mov     rcx, r14
0x180018294  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *> *>,std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *> * const)
0x180018299  mov     [rsi], rax
0x18001829c  mov     byte ptr [rsi+8], 1
0x1800182a0  mov     rax, rsi
0x1800182a3  add     rsp, 50h
0x1800182a7  pop     r14
0x1800182a9  pop     rdi
0x1800182aa  pop     rsi
0x1800182ab  pop     rbp
0x1800182ac  pop     rbx
0x1800182ad  retn
```
