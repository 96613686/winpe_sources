# std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::emplace<std::pair<_GUID const,void *> const &>(std::pair<_GUID const,void *> const &)

- ea: `0x180009e04`
- end: `0x180009f5d`
- name: `??$emplace@AEBU?$pair@$$CBU_GUID@@PEAX@std@@@?$_Hash@V?$_Umap_traits@U_GUID@@PEAXV?$_Uhash_compare@U_GUID@@UIIDHash@IUnknownBase@Com@Utils@Rdp@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAX@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@PEAX@std@@@std@@@std@@@std@@_N@1@AEBU?$pair@$$CBU_GUID@@PEAX@1@@Z`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000d788`

## callees

- `0x180003714`
- `0x180008be0`
- `0x180009cc8`
- `0x180009e04`
- `0x18000a61c`
- `0x18000d304`
- `0x18000d3a8`
- `0x18000d538`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::emplace<std::pair<_GUID const,void *> const &>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rbp
  _OWORD *v7; // r14
  __int64 v8; // rdx
  float v9; // xmm0_4
  __int64 v10; // rcx
  float v11; // xmm1_4
  __int64 v12; // rax
  __int64 v13; // rax
  _QWORD v15[2]; // [rsp+20h] [rbp-58h] BYREF
  _OWORD v16[4]; // [rsp+30h] [rbp-48h] BYREF

  v6 = *(_QWORD *)(a3 + 8);
  std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::_Find_last<_GUID>(
    a1,
    v16,
    a3,
    v6);
  if ( *((_QWORD *)&v16[0] + 1) )
  {
    *(_QWORD *)a2 = *((_QWORD *)&v16[0] + 1);
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( *(_QWORD *)(a1 + 16) == 0x666666666666666LL )
      std::_Xlength_error("unordered_map/set too long");
    v15[0] = a1 + 8;
    v7 = operator new(0x28u);
    v15[1] = v7;
    v7[1] = *(_OWORD *)a3;
    *((_QWORD *)v7 + 4) = *(_QWORD *)(a3 + 16);
    v8 = *(_QWORD *)(a1 + 16) + 1LL;
    if ( v8 < 0 )
      v9 = (float)(v8 & 1 | (unsigned int)((unsigned __int64)v8 >> 1))
         + (float)(v8 & 1 | (unsigned int)((unsigned __int64)v8 >> 1));
    else
      v9 = (float)(int)v8;
    v10 = *(_QWORD *)(a1 + 56);
    if ( v10 < 0 )
    {
      v12 = *(_QWORD *)(a1 + 56) & 1LL | ((unsigned __int64)v10 >> 1);
      v11 = (float)(int)v12 + (float)(int)v12;
    }
    else
    {
      v11 = (float)(int)v10;
    }
    if ( (float)(v9 / v11) > *(float *)a1 )
    {
      v13 = std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::_Desired_grow_bucket_count(a1);
      std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::_Forced_rehash(
        a1,
        v13);
      v16[0] = *(_OWORD *)std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::_Find_last<_GUID>(
                            a1,
                            v16,
                            v7 + 1,
                            v6);
    }
    *(_QWORD *)a2 = std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::_Insert_new_node_before(
                      a1,
                      v6,
                      *(_QWORD *)&v16[0],
                      v7,
                      v15[0],
                      0);
    *(_BYTE *)(a2 + 8) = 1;
    std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<_GUID const,void *>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<_GUID const,void *>,void *>>>(v15);
  }
  return a2;
}

```

## disassembly

```asm
0x180009e04  push    rbx
0x180009e06  push    rbp
0x180009e07  push    rsi
0x180009e08  push    rdi
0x180009e09  push    r14
0x180009e0b  push    r15
0x180009e0d  sub     rsp, 48h
0x180009e11  mov     rsi, r8
0x180009e14  mov     rdi, rdx
0x180009e17  mov     rbx, rcx
0x180009e1a  mov     rbp, [r8+8]
0x180009e1e  mov     r9, rbp
0x180009e21  lea     rdx, [rsp+78h+var_48]
0x180009e26  call    ??$_Find_last@U_GUID@@@?$_Hash@V?$_Umap_traits@U_GUID@@PEAXV?$_Uhash_compare@U_GUID@@UIIDHash@IUnknownBase@Com@Utils@Rdp@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAX@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBU_GUID@@PEAX@std@@PEAX@std@@@1@AEBU_GUID@@_K@Z; std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::_Find_last<_GUID>(_GUID const &,unsigned __int64)
0x180009e2b  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x180009e30  test    rdx, rdx
0x180009e33  jz      short loc_180009E41
0x180009e35  mov     [rdi], rdx
0x180009e38  mov     byte ptr [rdi+8], 0
0x180009e3c  jmp     loc_180009F4D
0x180009e41  mov     rax, 666666666666666h
0x180009e4b  cmp     [rbx+10h], rax
0x180009e4f  jnz     short loc_180009E5E
0x180009e51  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180009e58  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180009e5e  lea     rax, [rbx+8]
0x180009e62  mov     [rsp+78h+var_58], rax
0x180009e67  mov     [rsp+78h+var_50], 0
0x180009e70  mov     ecx, 28h ; '('; Size
0x180009e75  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009e7a  mov     r14, rax
0x180009e7d  mov     [rsp+78h+var_50], rax
0x180009e82  movups  xmm0, xmmword ptr [rsi]
0x180009e85  movups  xmmword ptr [rax+10h], xmm0
0x180009e89  movsd   xmm1, qword ptr [rsi+10h]
0x180009e8e  movsd   qword ptr [rax+20h], xmm1
0x180009e93  mov     rdx, [rbx+10h]
0x180009e97  add     rdx, 1
0x180009e9b  xorps   xmm0, xmm0
0x180009e9e  js      short loc_180009EA7
0x180009ea0  cvtsi2ss xmm0, rdx
0x180009ea5  jmp     short loc_180009EBF
0x180009ea7  mov     rcx, rdx
0x180009eaa  shr     rcx, 1
0x180009ead  mov     rax, rdx
0x180009eb0  and     eax, 1
0x180009eb3  or      rcx, rax
0x180009eb6  cvtsi2ss xmm0, rcx
0x180009ebb  addss   xmm0, xmm0
0x180009ebf  mov     rcx, [rbx+38h]
0x180009ec3  xorps   xmm1, xmm1
0x180009ec6  test    rcx, rcx
0x180009ec9  js      short loc_180009ED2
0x180009ecb  cvtsi2ss xmm1, rcx
0x180009ed0  jmp     short loc_180009EE7
0x180009ed2  mov     rax, rcx
0x180009ed5  shr     rax, 1
0x180009ed8  and     ecx, 1
0x180009edb  or      rax, rcx
0x180009ede  cvtsi2ss xmm1, rax
0x180009ee3  addss   xmm1, xmm1
0x180009ee7  divss   xmm0, xmm1
0x180009eeb  comiss  xmm0, dword ptr [rbx]
0x180009eee  jbe     short loc_180009F20
0x180009ef0  mov     rcx, rbx
0x180009ef3  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@U_GUID@@PEAXV?$_Uhash_compare@U_GUID@@UIIDHash@IUnknownBase@Com@Utils@Rdp@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAX@std@@@3@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x180009ef8  mov     rdx, rax
0x180009efb  mov     rcx, rbx
0x180009efe  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@U_GUID@@PEAXV?$_Uhash_compare@U_GUID@@UIIDHash@IUnknownBase@Com@Utils@Rdp@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAX@std@@@3@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::_Forced_rehash(unsigned __int64)
0x180009f03  mov     r9, rbp
0x180009f06  lea     r8, [r14+10h]
0x180009f0a  lea     rdx, [rsp+78h+var_48]
0x180009f0f  mov     rcx, rbx
0x180009f12  call    ??$_Find_last@U_GUID@@@?$_Hash@V?$_Umap_traits@U_GUID@@PEAXV?$_Uhash_compare@U_GUID@@UIIDHash@IUnknownBase@Com@Utils@Rdp@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAX@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBU_GUID@@PEAX@std@@PEAX@std@@@1@AEBU_GUID@@_K@Z; std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::_Find_last<_GUID>(_GUID const &,unsigned __int64)
0x180009f17  movups  xmm0, xmmword ptr [rax]
0x180009f1a  movdqu  [rsp+78h+var_48], xmm0
0x180009f20  mov     [rsp+78h+var_50], 0
0x180009f29  mov     r9, r14
0x180009f2c  mov     r8, qword ptr [rsp+78h+var_48]
0x180009f31  mov     rdx, rbp
0x180009f34  mov     rcx, rbx
0x180009f37  call    ?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@U_GUID@@PEAXV?$_Uhash_compare@U_GUID@@UIIDHash@IUnknownBase@Com@Utils@Rdp@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAX@std@@@3@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@$$CBU_GUID@@PEAX@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<_GUID const,void *>,void *> * const,std::_List_node<std::pair<_GUID const,void *>,void *> * const)
0x180009f3c  mov     [rdi], rax
0x180009f3f  mov     byte ptr [rdi+8], 1
0x180009f43  lea     rcx, [rsp+78h+var_58]
0x180009f48  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@U?$pair@$$CBU_GUID@@PEAX@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<_GUID const,void *>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<_GUID const,void *>,void *>>>(void)
0x180009f4d  mov     rax, rdi
0x180009f50  add     rsp, 48h
0x180009f54  pop     r15
0x180009f56  pop     r14
0x180009f58  pop     rdi
0x180009f59  pop     rsi
0x180009f5a  pop     rbp
0x180009f5b  pop     rbx
0x180009f5c  retn
```
