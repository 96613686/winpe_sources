# std::unordered_map<void *,wil::com_ptr_t<ID3D11Fence,wil::err_exception_policy>,std::hash<void *>,std::equal_to<void *>,std::allocator<std::pair<void * const,wil::com_ptr_t<ID3D11Fence,wil::err_exception_policy>>>>::_Insert_or_assign<void * const &,wil::com_ptr_t<ID3D11Fence,wil::err_exception_policy> &>(void * const &,wil::com_ptr_t<ID3D11Fence,wil::err_exception_policy> &)

- ea: `0x18001f55c`
- end: `0x18001f6fd`
- name: `??$_Insert_or_assign@AEBQEAXAEAV?$com_ptr_t@UID3D11Fence@@Uerr_exception_policy@wil@@@wil@@@?$unordered_map@PEAXV?$com_ptr_t@UID3D11Fence@@Uerr_exception_policy@wil@@@wil@@U?$hash@PEAX@std@@U?$equal_to@PEAX@4@V?$allocator@U?$pair@QEAXV?$com_ptr_t@UID3D11Fence@@Uerr_exception_policy@wil@@@wil@@@std@@@4@@std@@AEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAXV?$com_ptr_t@UID3D11Fence@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@std@@_N@1@AEBQEAXAEAV?$com_ptr_t@UID3D11Fence@@Uerr_exception_policy@wil@@@wil@@@Z`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ff30`

## callees

- `0x180003714`
- `0x180008be0`
- `0x18000a0e4`
- `0x18000d304`
- `0x18000d538`
- `0x18001c408`
- `0x18001cb94`
- `0x18001effc`
- `0x18001f55c`
- `0x180022c98`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall std::unordered_map<void *,wil::com_ptr_t<ID3D11Fence,wil::err_exception_policy>>::_Insert_or_assign<void * const &,wil::com_ptr_t<ID3D11Fence,wil::err_exception_policy> &>(
        unsigned __int64 a1,
        __int64 a2,
        const unsigned __int8 *a3,
        __int64 *a4)
{
  unsigned __int64 appended; // rbp
  __int64 v9; // rdx
  __int64 v10; // rsi
  __int64 v11; // rcx
  __int64 v12; // rdi
  _QWORD *v13; // rsi
  __int64 v14; // rdx
  float v15; // xmm0_4
  __int64 v16; // rcx
  float v17; // xmm1_4
  __int64 v18; // rax
  __int64 v19; // rax
  _QWORD v21[2]; // [rsp+20h] [rbp-58h] BYREF
  _OWORD v22[4]; // [rsp+30h] [rbp-48h] BYREF

  appended = std::_Fnv1a_append_bytes(a1, a3, (unsigned __int64)a3);
  std::_Hash<std::_Umap_traits<IUnknown *,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>,std::_Uhash_compare<IUnknown *,std::hash<IUnknown *>,std::equal_to<IUnknown *>>,std::allocator<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>,0>>::_Find_last<IUnknown *>(
    a1,
    v22,
    v9,
    appended);
  v10 = *((_QWORD *)&v22[0] + 1);
  if ( *((_QWORD *)&v22[0] + 1) )
  {
    v11 = *a4;
    v12 = *(_QWORD *)(*((_QWORD *)&v22[0] + 1) + 24LL);
    *(_QWORD *)(*((_QWORD *)&v22[0] + 1) + 24LL) = *a4;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    *(_QWORD *)a2 = v10;
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( *(_QWORD *)(a1 + 16) == 0x7FFFFFFFFFFFFFFLL )
      std::_Xlength_error("unordered_map/set too long");
    v21[0] = a1 + 8;
    v13 = operator new(0x20u);
    v21[1] = v13;
    v13[2] = *(_QWORD *)a3;
    wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
      v13 + 3,
      *a4);
    v14 = *(_QWORD *)(a1 + 16) + 1LL;
    if ( v14 < 0 )
      v15 = (float)(v14 & 1 | (unsigned int)((unsigned __int64)v14 >> 1))
          + (float)(v14 & 1 | (unsigned int)((unsigned __int64)v14 >> 1));
    else
      v15 = (float)(int)v14;
    v16 = *(_QWORD *)(a1 + 56);
    if ( v16 < 0 )
    {
      v18 = *(_QWORD *)(a1 + 56) & 1LL | ((unsigned __int64)v16 >> 1);
      v17 = (float)(int)v18 + (float)(int)v18;
    }
    else
    {
      v17 = (float)(int)v16;
    }
    if ( (float)(v15 / v17) > *(float *)a1 )
    {
      v19 = std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::_Desired_grow_bucket_count(a1);
      std::_Hash<std::_Umap_traits<void *,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>>>,0>>::_Forced_rehash(
        a1,
        v19);
      v22[0] = *(_OWORD *)std::_Hash<std::_Umap_traits<IUnknown *,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>,std::_Uhash_compare<IUnknown *,std::hash<IUnknown *>,std::equal_to<IUnknown *>>,std::allocator<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>,0>>::_Find_last<IUnknown *>(
                            a1,
                            v22,
                            v13 + 2,
                            appended);
    }
    *(_QWORD *)a2 = std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::_Insert_new_node_before(
                      a1,
                      appended,
                      *(_QWORD *)&v22[0],
                      v13,
                      v21[0],
                      0);
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned __int64 const,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned __int64 const,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>>,void *>>>(v21);
  }
  return a2;
}

```

## disassembly

```asm
0x18001f55c  push    rbx
0x18001f55e  push    rbp
0x18001f55f  push    rsi
0x18001f560  push    rdi
0x18001f561  push    r12
0x18001f563  push    r14
0x18001f565  push    r15
0x18001f567  sub     rsp, 40h
0x18001f56b  mov     r14, r9
0x18001f56e  mov     r15, r8
0x18001f571  mov     rbx, rdx
0x18001f574  mov     rdi, rcx
0x18001f577  mov     rdx, r8; unsigned __int8 *
0x18001f57a  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18001f57f  mov     rbp, rax
0x18001f582  mov     r9, rax
0x18001f585  mov     r8, rdx
0x18001f588  lea     rdx, [rsp+78h+var_48]
0x18001f58d  mov     rcx, rdi
0x18001f590  call    ??$_Find_last@PEAUIUnknown@@@?$_Hash@V?$_Umap_traits@PEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@V?$_Uhash_compare@PEAUIUnknown@@U?$hash@PEAUIUnknown@@@std@@U?$equal_to@PEAUIUnknown@@@3@@3@V?$allocator@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@PEAX@std@@@1@AEBQEAUIUnknown@@_K@Z; std::_Hash<std::_Umap_traits<IUnknown *,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>,std::_Uhash_compare<IUnknown *,std::hash<IUnknown *>,std::equal_to<IUnknown *>>,std::allocator<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>,0>>::_Find_last<IUnknown *>(IUnknown * const &,unsigned __int64)
0x18001f595  mov     rsi, qword ptr [rsp+78h+var_48+8]
0x18001f59a  test    rsi, rsi
0x18001f59d  jz      short loc_18001F5DC
0x18001f59f  mov     rcx, [r14]
0x18001f5a2  mov     rdi, [rsi+18h]
0x18001f5a6  mov     [rsi+18h], rcx
0x18001f5aa  test    rcx, rcx
0x18001f5ad  jz      short loc_18001F5BB
0x18001f5af  mov     rax, [rcx]
0x18001f5b2  mov     rax, [rax+8]
0x18001f5b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5bb  test    rdi, rdi
0x18001f5be  jz      short loc_18001F5D0
0x18001f5c0  mov     rax, [rdi]
0x18001f5c3  mov     rcx, rdi
0x18001f5c6  mov     rax, [rax+10h]
0x18001f5ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5cf  nop
0x18001f5d0  mov     [rbx], rsi
0x18001f5d3  mov     byte ptr [rbx+8], 0
0x18001f5d7  jmp     loc_18001F6EB
0x18001f5dc  mov     rax, 7FFFFFFFFFFFFFFh
0x18001f5e6  cmp     [rdi+10h], rax
0x18001f5ea  jnz     short loc_18001F5F9
0x18001f5ec  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18001f5f3  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001f5f9  lea     rax, [rdi+8]
0x18001f5fd  mov     [rsp+78h+var_58], rax
0x18001f602  mov     [rsp+78h+var_50], 0
0x18001f60b  mov     ecx, 20h ; ' '; Size
0x18001f610  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f615  mov     rsi, rax
0x18001f618  mov     [rsp+78h+var_50], rax
0x18001f61d  mov     rcx, [r15]
0x18001f620  mov     [rax+10h], rcx
0x18001f624  lea     rcx, [rax+18h]
0x18001f628  mov     rdx, [r14]
0x18001f62b  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x18001f630  nop
0x18001f631  mov     rdx, [rdi+10h]
0x18001f635  add     rdx, 1
0x18001f639  xorps   xmm0, xmm0
0x18001f63c  js      short loc_18001F645
0x18001f63e  cvtsi2ss xmm0, rdx
0x18001f643  jmp     short loc_18001F65D
0x18001f645  mov     rcx, rdx
0x18001f648  shr     rcx, 1
0x18001f64b  mov     rax, rdx
0x18001f64e  and     eax, 1
0x18001f651  or      rcx, rax
0x18001f654  cvtsi2ss xmm0, rcx
0x18001f659  addss   xmm0, xmm0
0x18001f65d  mov     rcx, [rdi+38h]
0x18001f661  xorps   xmm1, xmm1
0x18001f664  test    rcx, rcx
0x18001f667  js      short loc_18001F670
0x18001f669  cvtsi2ss xmm1, rcx
0x18001f66e  jmp     short loc_18001F685
0x18001f670  mov     rax, rcx
0x18001f673  shr     rax, 1
0x18001f676  and     ecx, 1
0x18001f679  or      rax, rcx
0x18001f67c  cvtsi2ss xmm1, rax
0x18001f681  addss   xmm1, xmm1
0x18001f685  divss   xmm0, xmm1
0x18001f689  comiss  xmm0, dword ptr [rdi]
0x18001f68c  jbe     short loc_18001F6BE
0x18001f68e  mov     rcx, rdi
0x18001f691  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@U_GUID@@PEAXV?$_Uhash_compare@U_GUID@@UIIDHash@IUnknownBase@Com@Utils@Rdp@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAX@std@@@3@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x18001f696  mov     rdx, rax
0x18001f699  mov     rcx, rdi
0x18001f69c  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@PEAXV?$com_ptr_t@UID3D11Texture2D@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@std@@V?$allocator@U?$pair@QEAXV?$com_ptr_t@UID3D11Texture2D@@Uerr_exception_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<void *,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>>>,0>>::_Forced_rehash(unsigned __int64)
0x18001f6a1  mov     r9, rbp
0x18001f6a4  lea     r8, [rsi+10h]
0x18001f6a8  lea     rdx, [rsp+78h+var_48]
0x18001f6ad  mov     rcx, rdi
0x18001f6b0  call    ??$_Find_last@PEAUIUnknown@@@?$_Hash@V?$_Umap_traits@PEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@V?$_Uhash_compare@PEAUIUnknown@@U?$hash@PEAUIUnknown@@@std@@U?$equal_to@PEAUIUnknown@@@3@@3@V?$allocator@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@PEAX@std@@@1@AEBQEAUIUnknown@@_K@Z; std::_Hash<std::_Umap_traits<IUnknown *,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>,std::_Uhash_compare<IUnknown *,std::hash<IUnknown *>,std::equal_to<IUnknown *>>,std::allocator<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>,0>>::_Find_last<IUnknown *>(IUnknown * const &,unsigned __int64)
0x18001f6b5  movups  xmm0, xmmword ptr [rax]
0x18001f6b8  movdqu  [rsp+78h+var_48], xmm0
0x18001f6be  mov     [rsp+78h+var_50], 0
0x18001f6c7  mov     r9, rsi
0x18001f6ca  mov     r8, qword ptr [rsp+78h+var_48]
0x18001f6cf  mov     rdx, rbp
0x18001f6d2  mov     rcx, rdi
0x18001f6d5  call    ?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@U_GUID@@PEAXV?$_Uhash_compare@U_GUID@@UIIDHash@IUnknownBase@Com@Utils@Rdp@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAX@std@@@3@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@$$CBU_GUID@@PEAX@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<_GUID const,void *>,void *> * const,std::_List_node<std::pair<_GUID const,void *>,void *> * const)
0x18001f6da  mov     [rbx], rax
0x18001f6dd  mov     byte ptr [rbx+8], 1
0x18001f6e1  lea     rcx, [rsp+78h+var_58]
0x18001f6e6  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CB_KV?$com_ptr_t@VCFrameProcessorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned __int64 const,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned __int64 const,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>>,void *>>>(void)
0x18001f6eb  mov     rax, rbx
0x18001f6ee  add     rsp, 40h
0x18001f6f2  pop     r15
0x18001f6f4  pop     r14
0x18001f6f6  pop     r12
0x18001f6f8  pop     rdi
0x18001f6f9  pop     rsi
0x18001f6fa  pop     rbp
0x18001f6fb  pop     rbx
0x18001f6fc  retn
```
