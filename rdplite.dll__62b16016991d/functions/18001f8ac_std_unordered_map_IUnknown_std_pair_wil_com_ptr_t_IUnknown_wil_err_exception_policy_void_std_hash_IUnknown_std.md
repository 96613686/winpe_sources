# std::unordered_map<IUnknown *,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>,std::hash<IUnknown *>,std::equal_to<IUnknown *>,std::allocator<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>>::_Insert_or_assign<IUnknown *,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>(IUnknown * &&,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *> &&)

- ea: `0x18001f8ac`
- end: `0x18001fa51`
- name: `??$_Insert_or_assign@PEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@?$unordered_map@PEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@U?$hash@PEAUIUnknown@@@3@U?$equal_to@PEAUIUnknown@@@3@V?$allocator@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@3@@std@@AEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAPEAUIUnknown@@$$QEAU?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@1@@Z`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020cec`

## callees

- `0x180003714`
- `0x180008be0`
- `0x18000d304`
- `0x18000d538`
- `0x18001c408`
- `0x18001effc`
- `0x18001f8ac`
- `0x180020a30`
- `0x180022b20`
- `0x18002a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::unordered_map<IUnknown *,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>::_Insert_or_assign<IUnknown *,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>(
        unsigned __int64 a1,
        __int64 a2,
        const unsigned __int8 *a3,
        __int64 *a4)
{
  unsigned __int64 appended; // rbp
  __int64 v9; // rdx
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rcx
  _QWORD *v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rdx
  float v16; // xmm0_4
  __int64 v17; // rcx
  float v18; // xmm1_4
  __int64 v19; // rax
  __int64 v20; // rax
  _QWORD v22[2]; // [rsp+20h] [rbp-58h] BYREF
  _OWORD v23[4]; // [rsp+30h] [rbp-48h] BYREF

  appended = std::_Fnv1a_append_bytes(a1, a3, (unsigned __int64)a3);
  std::_Hash<std::_Umap_traits<IUnknown *,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>,std::_Uhash_compare<IUnknown *,std::hash<IUnknown *>,std::equal_to<IUnknown *>>,std::allocator<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>,0>>::_Find_last<IUnknown *>(
    a1,
    v23,
    v9,
    appended);
  v10 = *((_QWORD *)&v23[0] + 1);
  if ( *((_QWORD *)&v23[0] + 1) )
  {
    v11 = *a4;
    *a4 = 0;
    v12 = *(_QWORD *)(v10 + 24);
    *(_QWORD *)(v10 + 24) = v11;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    *(_QWORD *)(v10 + 32) = a4[1];
    *(_QWORD *)a2 = v10;
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( *(_QWORD *)(a1 + 16) == 0x666666666666666LL )
      std::_Xlength_error("unordered_map/set too long");
    v22[0] = a1 + 8;
    v13 = operator new(0x28u);
    v22[1] = v13;
    v13[2] = *(_QWORD *)a3;
    v14 = *a4;
    *a4 = 0;
    v13[3] = v14;
    v13[4] = a4[1];
    v15 = *(_QWORD *)(a1 + 16) + 1LL;
    if ( v15 < 0 )
      v16 = (float)(v15 & 1 | (unsigned int)((unsigned __int64)v15 >> 1))
          + (float)(v15 & 1 | (unsigned int)((unsigned __int64)v15 >> 1));
    else
      v16 = (float)(int)v15;
    v17 = *(_QWORD *)(a1 + 56);
    if ( v17 < 0 )
    {
      v19 = *(_QWORD *)(a1 + 56) & 1LL | ((unsigned __int64)v17 >> 1);
      v18 = (float)(int)v19 + (float)(int)v19;
    }
    else
    {
      v18 = (float)(int)v17;
    }
    if ( (float)(v16 / v18) > *(float *)a1 )
    {
      v20 = std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::_Desired_grow_bucket_count(a1);
      std::_Hash<std::_Umap_traits<IUnknown *,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>,std::_Uhash_compare<IUnknown *,std::hash<IUnknown *>,std::equal_to<IUnknown *>>,std::allocator<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>,0>>::_Forced_rehash(
        a1,
        v20);
      v23[0] = *(_OWORD *)std::_Hash<std::_Umap_traits<IUnknown *,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>,std::_Uhash_compare<IUnknown *,std::hash<IUnknown *>,std::equal_to<IUnknown *>>,std::allocator<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>,0>>::_Find_last<IUnknown *>(
                            a1,
                            v23,
                            v13 + 2,
                            appended);
    }
    *(_QWORD *)a2 = std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::_Insert_new_node_before(
                      a1,
                      appended,
                      *(_QWORD *)&v23[0],
                      v13,
                      v22[0],
                      0);
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>,void *>>>(v22);
  }
  return a2;
}

```

## disassembly

```asm
0x18001f8ac  push    rbx
0x18001f8ae  push    rbp
0x18001f8af  push    rsi
0x18001f8b0  push    rdi
0x18001f8b1  push    r12
0x18001f8b3  push    r14
0x18001f8b5  push    r15
0x18001f8b7  sub     rsp, 40h
0x18001f8bb  mov     r14, r9
0x18001f8be  mov     r15, r8
0x18001f8c1  mov     rsi, rdx
0x18001f8c4  mov     rdi, rcx
0x18001f8c7  mov     rdx, r8; unsigned __int8 *
0x18001f8ca  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18001f8cf  mov     rbp, rax
0x18001f8d2  mov     r9, rax
0x18001f8d5  mov     r8, rdx
0x18001f8d8  lea     rdx, [rsp+78h+var_48]
0x18001f8dd  mov     rcx, rdi
0x18001f8e0  call    ??$_Find_last@PEAUIUnknown@@@?$_Hash@V?$_Umap_traits@PEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@V?$_Uhash_compare@PEAUIUnknown@@U?$hash@PEAUIUnknown@@@std@@U?$equal_to@PEAUIUnknown@@@3@@3@V?$allocator@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@PEAX@std@@@1@AEBQEAUIUnknown@@_K@Z; std::_Hash<std::_Umap_traits<IUnknown *,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>,std::_Uhash_compare<IUnknown *,std::hash<IUnknown *>,std::equal_to<IUnknown *>>,std::allocator<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>,0>>::_Find_last<IUnknown *>(IUnknown * const &,unsigned __int64)
0x18001f8e5  mov     rbx, qword ptr [rsp+78h+var_48+8]
0x18001f8ea  test    rbx, rbx
0x18001f8ed  jz      short loc_18001F927
0x18001f8ef  mov     rax, [r14]
0x18001f8f2  mov     qword ptr [r14], 0
0x18001f8f9  mov     rcx, [rbx+18h]
0x18001f8fd  mov     [rbx+18h], rax
0x18001f901  test    rcx, rcx
0x18001f904  jz      short loc_18001F913
0x18001f906  mov     rax, [rcx]
0x18001f909  mov     rax, [rax+10h]
0x18001f90d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f912  nop
0x18001f913  mov     rax, [r14+8]
0x18001f917  mov     [rbx+20h], rax
0x18001f91b  mov     [rsi], rbx
0x18001f91e  mov     byte ptr [rsi+8], 0
0x18001f922  jmp     loc_18001FA3F
0x18001f927  mov     rax, 666666666666666h
0x18001f931  cmp     [rdi+10h], rax
0x18001f935  jnz     short loc_18001F944
0x18001f937  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18001f93e  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001f944  lea     rax, [rdi+8]
0x18001f948  mov     [rsp+78h+var_58], rax
0x18001f94d  mov     [rsp+78h+var_50], 0
0x18001f956  mov     ecx, 28h ; '('; Size
0x18001f95b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f960  mov     rbx, rax
0x18001f963  mov     [rsp+78h+var_50], rax
0x18001f968  mov     rcx, [r15]
0x18001f96b  mov     [rax+10h], rcx
0x18001f96f  mov     rcx, [r14]
0x18001f972  mov     qword ptr [r14], 0
0x18001f979  mov     [rax+18h], rcx
0x18001f97d  mov     rcx, [r14+8]
0x18001f981  mov     [rax+20h], rcx
0x18001f985  mov     rdx, [rdi+10h]
0x18001f989  add     rdx, 1
0x18001f98d  xorps   xmm0, xmm0
0x18001f990  js      short loc_18001F999
0x18001f992  cvtsi2ss xmm0, rdx
0x18001f997  jmp     short loc_18001F9B1
0x18001f999  mov     rcx, rdx
0x18001f99c  shr     rcx, 1
0x18001f99f  mov     rax, rdx
0x18001f9a2  and     eax, 1
0x18001f9a5  or      rcx, rax
0x18001f9a8  cvtsi2ss xmm0, rcx
0x18001f9ad  addss   xmm0, xmm0
0x18001f9b1  mov     rcx, [rdi+38h]
0x18001f9b5  xorps   xmm1, xmm1
0x18001f9b8  test    rcx, rcx
0x18001f9bb  js      short loc_18001F9C4
0x18001f9bd  cvtsi2ss xmm1, rcx
0x18001f9c2  jmp     short loc_18001F9D9
0x18001f9c4  mov     rax, rcx
0x18001f9c7  shr     rax, 1
0x18001f9ca  and     ecx, 1
0x18001f9cd  or      rax, rcx
0x18001f9d0  cvtsi2ss xmm1, rax
0x18001f9d5  addss   xmm1, xmm1
0x18001f9d9  divss   xmm0, xmm1
0x18001f9dd  comiss  xmm0, dword ptr [rdi]
0x18001f9e0  jbe     short loc_18001FA12
0x18001f9e2  mov     rcx, rdi
0x18001f9e5  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@U_GUID@@PEAXV?$_Uhash_compare@U_GUID@@UIIDHash@IUnknownBase@Com@Utils@Rdp@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAX@std@@@3@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x18001f9ea  mov     rdx, rax
0x18001f9ed  mov     rcx, rdi
0x18001f9f0  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@PEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@V?$_Uhash_compare@PEAUIUnknown@@U?$hash@PEAUIUnknown@@@std@@U?$equal_to@PEAUIUnknown@@@3@@3@V?$allocator@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@3@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<IUnknown *,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>,std::_Uhash_compare<IUnknown *,std::hash<IUnknown *>,std::equal_to<IUnknown *>>,std::allocator<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>,0>>::_Forced_rehash(unsigned __int64)
0x18001f9f5  mov     r9, rbp
0x18001f9f8  lea     r8, [rbx+10h]
0x18001f9fc  lea     rdx, [rsp+78h+var_48]
0x18001fa01  mov     rcx, rdi
0x18001fa04  call    ??$_Find_last@PEAUIUnknown@@@?$_Hash@V?$_Umap_traits@PEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@V?$_Uhash_compare@PEAUIUnknown@@U?$hash@PEAUIUnknown@@@std@@U?$equal_to@PEAUIUnknown@@@3@@3@V?$allocator@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@PEAX@std@@@1@AEBQEAUIUnknown@@_K@Z; std::_Hash<std::_Umap_traits<IUnknown *,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>,std::_Uhash_compare<IUnknown *,std::hash<IUnknown *>,std::equal_to<IUnknown *>>,std::allocator<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>,0>>::_Find_last<IUnknown *>(IUnknown * const &,unsigned __int64)
0x18001fa09  movups  xmm0, xmmword ptr [rax]
0x18001fa0c  movdqu  [rsp+78h+var_48], xmm0
0x18001fa12  mov     [rsp+78h+var_50], 0
0x18001fa1b  mov     r9, rbx
0x18001fa1e  mov     r8, qword ptr [rsp+78h+var_48]
0x18001fa23  mov     rdx, rbp
0x18001fa26  mov     rcx, rdi
0x18001fa29  call    ?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@U_GUID@@PEAXV?$_Uhash_compare@U_GUID@@UIIDHash@IUnknownBase@Com@Utils@Rdp@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAX@std@@@3@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@$$CBU_GUID@@PEAX@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<_GUID const,void *>,void *> * const,std::_List_node<std::pair<_GUID const,void *>,void *> * const)
0x18001fa2e  mov     [rsi], rax
0x18001fa31  mov     byte ptr [rsi+8], 1
0x18001fa35  lea     rcx, [rsp+78h+var_58]
0x18001fa3a  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>,void *>>>(void)
0x18001fa3f  mov     rax, rsi
0x18001fa42  add     rsp, 40h
0x18001fa46  pop     r15
0x18001fa48  pop     r14
0x18001fa4a  pop     r12
0x18001fa4c  pop     rdi
0x18001fa4d  pop     rsi
0x18001fa4e  pop     rbp
0x18001fa4f  pop     rbx
0x18001fa50  retn
```
