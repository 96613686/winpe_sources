# Tracer::TraceEnergyDetails(unsigned __int64)

- ea: `0x18002c414`
- end: `0x18002c5f4`
- name: `?TraceEnergyDetails@Tracer@@AEAAK_K@Z`
- size: `480`
- prototype: `unsigned int __fastcall(Tracer *__hidden this, REGHANDLE RegHandle)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002bc28`

## callees

- `0x1800178d8`
- `0x18002c3c4`
- `0x18002c414`
- `0x18002c5fc`
- `0x18003b274`
- `0x18003b6fc`
- `0x18003bb60`
- `0x18004ca90`
- `0x18008dcec`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18002c488`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18002c56e`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18002c488`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18002c56e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Tracer::TraceEnergyDetails(Tracer *this, REGHANDLE RegHandle)
{
  ULONG v4; // esi
  __int128 *v5; // rdi
  _QWORD *v6; // rbx
  __int64 i; // rbx
  int v8; // eax
  __int64 v9; // rcx
  __int64 j; // rax
  int v12; // [rsp+20h] [rbp-60h] BYREF
  __int128 v13; // [rsp+28h] [rbp-58h] BYREF
  unsigned int v14; // [rsp+38h] [rbp-48h] BYREF
  void *v15[2]; // [rsp+40h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-30h] BYREF
  int *v17; // [rsp+60h] [rbp-20h]
  __int64 v18; // [rsp+68h] [rbp-18h]

  v14 = 0;
  v13 = 0;
  std::_Tree<std::_Tmap_traits<_GUID const,ProviderInfo,std::less<_GUID const>,std::allocator<std::pair<_GUID const,ProviderInfo>>,0>>::_Alloc_sentinel_and_proxy(&v13);
  v12 = 0;
  v14 = Tracer::NtklEnableFlags(this);
  UserData.Ptr = (ULONGLONG)&v14;
  *(_QWORD *)&UserData.Size = 4;
  v4 = EventWrite(RegHandle, &ENERGY_EVT_NTKL_RUNDOWN, 1u, &UserData);
  if ( !v4 )
  {
    v5 = (__int128 *)Tracer::RequiredProviders(this, v15);
    if ( &v13 != v5 )
    {
      v6 = (_QWORD *)v13;
      std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,ProviderInfo>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<_GUID const,ProviderInfo>,void *>>>(
        &v13,
        &v13,
        *(_QWORD *)(v13 + 8));
      v6[1] = v6;
      *v6 = v6;
      v6[2] = v6;
      *((_QWORD *)&v13 + 1) = 0;
      std::_Tree<std::_Tmap_traits<_GUID const,ProviderInfo,std::less<_GUID const>,std::allocator<std::pair<_GUID const,ProviderInfo>>,0>>::_Copy<0>(
        &v13,
        v5);
    }
    std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,ProviderInfo>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<_GUID const,ProviderInfo>,void *>>>(
      v15,
      v15,
      *((_QWORD *)v15[0] + 1));
    std::_Deallocate<16>(v15[0], 0x40u);
    for ( i = *(_QWORD *)v13; i != (_QWORD)v13; i = j )
    {
      v12 = 0;
      v8 = 0;
      if ( *(_BYTE *)(i + 48) )
      {
        v12 = 1;
        v8 = 1;
      }
      if ( *(_BYTE *)(i + 49) )
        v12 = v8 | 2;
      UserData.Ptr = i + 32;
      *(_QWORD *)&UserData.Size = 16;
      v17 = &v12;
      v18 = 4;
      v4 = EventWrite(RegHandle, &ENERGY_EVT_PROVIDER_RUNDOWN, 2u, &UserData);
      if ( v4 )
        break;
      v9 = *(_QWORD *)(i + 16);
      if ( *(_BYTE *)(v9 + 25) )
      {
        for ( j = *(_QWORD *)(i + 8); !*(_BYTE *)(j + 25) && i == *(_QWORD *)(j + 16); j = *(_QWORD *)(j + 8) )
          i = j;
      }
      else
      {
        j = std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,UsbDevice>>>::_Min(v9);
      }
    }
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,ProviderInfo>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<_GUID const,ProviderInfo>,void *>>>(
    &v13,
    &v13,
    *(_QWORD *)(v13 + 8));
  std::_Deallocate<16>((void *)v13, 0x40u);
  return v4;
}

```

## disassembly

```asm
0x18002c414  mov     [rsp-28h+arg_10], rbx
0x18002c419  push    rbp
0x18002c41a  push    rsi
0x18002c41b  push    rdi
0x18002c41c  push    r14
0x18002c41e  push    r15
0x18002c420  mov     rbp, rsp
0x18002c423  sub     rsp, 80h
0x18002c42a  mov     rax, cs:__security_cookie
0x18002c431  xor     rax, rsp
0x18002c434  mov     [rbp+var_10], rax
0x18002c438  mov     r14, rdx
0x18002c43b  mov     rbx, rcx
0x18002c43e  xor     r15d, r15d
0x18002c441  mov     [rbp+var_48], r15d
0x18002c445  xorps   xmm0, xmm0
0x18002c448  movdqu  [rbp+var_58], xmm0
0x18002c44d  lea     rcx, [rbp+var_58]
0x18002c451  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@$$CBU_GUID@@VProviderInfo@@U?$less@$$CBU_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@VProviderInfo@@@std@@@4@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<_GUID const,ProviderInfo,std::less<_GUID const>,std::allocator<std::pair<_GUID const,ProviderInfo>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18002c456  nop
0x18002c457  mov     [rbp+var_60], r15d
0x18002c45b  mov     rcx, rbx; this
0x18002c45e  call    ?NtklEnableFlags@Tracer@@AEAAKXZ; Tracer::NtklEnableFlags(void)
0x18002c463  mov     [rbp+var_48], eax
0x18002c466  lea     rax, [rbp+var_48]
0x18002c46a  mov     [rbp+UserData.Ptr], rax
0x18002c46e  mov     qword ptr [rbp+UserData.Size], 4
0x18002c476  lea     r9, [rbp+UserData]; UserData
0x18002c47a  lea     r8d, [r15+1]; UserDataCount
0x18002c47e  lea     rdx, ENERGY_EVT_NTKL_RUNDOWN; EventDescriptor
0x18002c485  mov     rcx, r14; RegHandle
0x18002c488  call    cs:__imp_EventWrite
0x18002c48e  mov     esi, eax
0x18002c490  test    eax, eax
0x18002c492  jnz     loc_18002C5AC
0x18002c498  lea     rdx, [rbp+var_40]
0x18002c49c  mov     rcx, rbx
0x18002c49f  call    ?RequiredProviders@Tracer@@AEAA?BV?$map@$$CBU_GUID@@VProviderInfo@@U?$less@$$CBU_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@VProviderInfo@@@std@@@4@@std@@XZ; Tracer::RequiredProviders(void)
0x18002c4a4  mov     rdi, rax
0x18002c4a7  lea     rax, [rbp+var_58]
0x18002c4ab  cmp     rax, rdi
0x18002c4ae  jz      short loc_18002C4E1
0x18002c4b0  mov     rbx, qword ptr [rbp+var_58]
0x18002c4b4  mov     r8, [rbx+8]
0x18002c4b8  lea     rdx, [rbp+var_58]
0x18002c4bc  lea     rcx, [rbp+var_58]
0x18002c4c0  call    ??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@VProviderInfo@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@VProviderInfo@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@VProviderInfo@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@VProviderInfo@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,ProviderInfo>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<_GUID const,ProviderInfo>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,ProviderInfo>,void *>> &,std::_Tree_node<std::pair<_GUID const,ProviderInfo>,void *> *)
0x18002c4c5  mov     [rbx+8], rbx
0x18002c4c9  mov     [rbx], rbx
0x18002c4cc  mov     [rbx+10h], rbx
0x18002c4d0  mov     qword ptr [rbp+var_58+8], r15
0x18002c4d4  mov     rdx, rdi
0x18002c4d7  lea     rcx, [rbp+var_58]
0x18002c4db  call    ??$_Copy@$0A@@?$_Tree@V?$_Tmap_traits@$$CBU_GUID@@VProviderInfo@@U?$less@$$CBU_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@VProviderInfo@@@std@@@4@$0A@@std@@@std@@IEAAXAEBV01@@Z; std::_Tree<std::_Tmap_traits<_GUID const,ProviderInfo,std::less<_GUID const>,std::allocator<std::pair<_GUID const,ProviderInfo>>,0>>::_Copy<0>(std::_Tree<std::_Tmap_traits<_GUID const,ProviderInfo,std::less<_GUID const>,std::allocator<std::pair<_GUID const,ProviderInfo>>,0>> const &)
0x18002c4e0  nop
0x18002c4e1  mov     r8, [rbp+var_40]
0x18002c4e5  mov     r8, [r8+8]
0x18002c4e9  lea     rdx, [rbp+var_40]
0x18002c4ed  lea     rcx, [rbp+var_40]
0x18002c4f1  call    ??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@VProviderInfo@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@VProviderInfo@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@VProviderInfo@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@VProviderInfo@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,ProviderInfo>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<_GUID const,ProviderInfo>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,ProviderInfo>,void *>> &,std::_Tree_node<std::pair<_GUID const,ProviderInfo>,void *> *)
0x18002c4f6  mov     edx, 40h ; '@'
0x18002c4fb  mov     rcx, [rbp+var_40]
0x18002c4ff  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002c504  mov     rbx, qword ptr [rbp+var_58]
0x18002c508  mov     rbx, [rbx]
0x18002c50b  cmp     rbx, qword ptr [rbp+var_58]
0x18002c50f  jz      loc_18002C5AC
0x18002c515  mov     [rbp+var_60], r15d
0x18002c519  mov     eax, r15d
0x18002c51c  cmp     [rbx+30h], r15b
0x18002c520  jz      short loc_18002C52E
0x18002c522  mov     [rbp+var_60], 1
0x18002c529  mov     eax, 1
0x18002c52e  cmp     [rbx+31h], r15b
0x18002c532  jz      short loc_18002C53A
0x18002c534  or      eax, 2
0x18002c537  mov     [rbp+var_60], eax
0x18002c53a  lea     rax, [rbx+20h]
0x18002c53e  mov     [rbp+UserData.Ptr], rax
0x18002c542  mov     qword ptr [rbp+UserData.Size], 10h
0x18002c54a  lea     rax, [rbp+var_60]
0x18002c54e  mov     [rbp+var_20], rax
0x18002c552  mov     [rbp+var_18], 4
0x18002c55a  lea     r9, [rbp+UserData]; UserData
0x18002c55e  mov     r8d, 2; UserDataCount
0x18002c564  lea     rdx, ENERGY_EVT_PROVIDER_RUNDOWN; EventDescriptor
0x18002c56b  mov     rcx, r14; RegHandle
0x18002c56e  call    cs:__imp_EventWrite
0x18002c574  mov     esi, eax
0x18002c576  test    eax, eax
0x18002c578  jnz     short loc_18002C5AC
0x18002c57a  mov     rcx, [rbx+10h]
0x18002c57e  cmp     [rcx+19h], r15b
0x18002c582  jz      short loc_18002C59F
0x18002c584  mov     rax, [rbx+8]
0x18002c588  jmp     short loc_18002C597
0x18002c58a  cmp     rbx, [rax+10h]
0x18002c58e  jnz     short loc_18002C5A4
0x18002c590  mov     rbx, rax
0x18002c593  mov     rax, [rax+8]
0x18002c597  cmp     [rax+19h], r15b
0x18002c59b  jz      short loc_18002C58A
0x18002c59d  jmp     short loc_18002C5A4
0x18002c59f  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXVUsbDevice@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@QEAXVUsbDevice@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,UsbDevice>>>::_Min(std::_Tree_node<std::pair<void * const,UsbDevice>,void *> *)
0x18002c5a4  mov     rbx, rax
0x18002c5a7  jmp     loc_18002C50B
0x18002c5ac  mov     r8, qword ptr [rbp+var_58]
0x18002c5b0  mov     r8, [r8+8]
0x18002c5b4  lea     rdx, [rbp+var_58]
0x18002c5b8  lea     rcx, [rbp+var_58]
0x18002c5bc  call    ??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@VProviderInfo@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@VProviderInfo@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@VProviderInfo@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@VProviderInfo@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,ProviderInfo>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<_GUID const,ProviderInfo>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,ProviderInfo>,void *>> &,std::_Tree_node<std::pair<_GUID const,ProviderInfo>,void *> *)
0x18002c5c1  mov     edx, 40h ; '@'
0x18002c5c6  mov     rcx, qword ptr [rbp+var_58]
0x18002c5ca  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002c5cf  mov     eax, esi
0x18002c5d1  mov     rcx, [rbp+var_10]
0x18002c5d5  xor     rcx, rsp; StackCookie
0x18002c5d8  call    __security_check_cookie
0x18002c5dd  mov     rbx, [rsp+80h+arg_10]
0x18002c5e5  add     rsp, 80h
0x18002c5ec  pop     r15
0x18002c5ee  pop     r14
0x18002c5f0  pop     rdi
0x18002c5f1  pop     rsi
0x18002c5f2  pop     rbp
0x18002c5f3  retn
```
