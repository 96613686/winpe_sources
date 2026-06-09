# DWMInputRouter::GetTargetListFromHitTestResult(InputType,HitTestResult const &,Microsoft::WRL::ComPtr<IDCompInputTarget> &)

- ea: `0x180017c60`
- end: `0x180017e43`
- name: `?GetTargetListFromHitTestResult@DWMInputRouter@@AEAA?AV?$vector@V?$ComPtr@UIInputTarget@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIInputTarget@@@WRL@Microsoft@@@std@@@std@@W4InputType@@AEBUHitTestResult@@AEAV?$ComPtr@UIDCompInputTarget@@@WRL@Microsoft@@@Z`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800179e0`

## callees

- `0x18000c5bc`
- `0x180017050`
- `0x18001707c`
- `0x180017c60`
- `0x180017e4c`
- `0x180018190`
- `0x18001875c`
- `0x18008941c`
- `0x1801ce010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017e3c`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017e3c`
- `win32u!NtQueryCompositionInputSinkLuid` at `0x180017ca2`
- `win32u!NtQueryCompositionInputSinkLuid` at `0x180017ca2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall DWMInputRouter::GetTargetListFromHitTestResult(
        DWMInputRouter *a1,
        __int64 *a2,
        int a3,
        __int64 a4,
        _QWORD *a5)
{
  __int64 v5; // rbx
  __int64 v7; // rcx
  int v8; // r8d
  DWMInputRouter *v9; // r10
  __int64 v10; // rax
  __int64 *v11; // rsi
  __int64 *v12; // r12
  struct IInputTarget **TargetFromInputSite; // rax
  struct IInputTarget **v14; // r13
  __int64 v15; // rcx
  __int64 v16; // r14
  __int64 v17; // rbx
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  __int64 v20; // rbp
  __int64 size_of; // rax
  __int64 v22; // rax
  __int64 v23; // r10
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rcx
  __int64 v27; // r9
  __int64 v28; // r10
  struct IInputTarget *v29; // rcx
  __int64 v31; // [rsp+48h] [rbp-60h] BYREF
  struct IInputTarget *v32; // [rsp+50h] [rbp-58h] BYREF

  v5 = a4;
  v31 = 0;
  v7 = *(_QWORD *)(a4 + 8);
  if ( v7 )
    NtQueryCompositionInputSinkLuid(v7, &v31);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,ForegroundManager::TargetingInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,ForegroundManager::TargetingInfo>>>>>>(a2);
  v10 = *(_QWORD *)(v5 + 104);
  v11 = *(__int64 **)(v10 - 24);
  v12 = *(__int64 **)(v10 - 16);
  if ( v11 != v12 )
  {
    while ( 1 )
    {
      TargetFromInputSite = DWMInputRouter::GetTargetFromInputSite(v9, &v32, v11, v8, (HWND *)v5, (__int64)&v31, a5);
      v14 = TargetFromInputSite;
      v15 = a2[2];
      v16 = a2[1];
      if ( v16 == v15 )
      {
        v17 = (v16 - *a2) >> 3;
        if ( v17 == 0x1FFFFFFFFFFFFFFFLL )
          std::_Xlength_error("vector too long");
        v18 = (v15 - *a2) >> 3;
        v19 = v18 >> 1;
        v20 = 0x1FFFFFFFFFFFFFFFLL;
        if ( v18 <= 0x1FFFFFFFFFFFFFFFLL - (v18 >> 1) )
        {
          v20 = v19 + v18;
          if ( v19 + v18 < v17 + 1 )
            v20 = v17 + 1;
        }
        size_of = std::_Get_size_of_n<8>(v20);
        v22 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
        Microsoft::WRL::ComPtr<InputSite>::ComPtr<InputSite>(v22 + 8 * v17, v14);
        v24 = a2[1];
        v25 = v23;
        v26 = *a2;
        if ( v16 != v24 )
        {
          std::_Uninitialized_move<Microsoft::WRL::ComPtr<IActivationListenerInputObjectProxy> *,std::allocator<Microsoft::WRL::ComPtr<IActivationListenerInputObjectProxy>>>(
            v26,
            v16,
            v23);
          v25 = v27 + 8;
          v24 = a2[1];
          v26 = v16;
        }
        std::_Uninitialized_move<Microsoft::WRL::ComPtr<IActivationListenerInputObjectProxy> *,std::allocator<Microsoft::WRL::ComPtr<IActivationListenerInputObjectProxy>>>(
          v26,
          v24,
          v25);
        std::vector<Microsoft::WRL::ComPtr<IMPCInputProviderBase>>::_Change_array(a2, v28, v17 + 1, v20);
      }
      else
      {
        Microsoft::WRL::ComPtr<InputSite>::ComPtr<InputSite>(a2[1], TargetFromInputSite);
        a2[1] += 8;
      }
      v29 = v32;
      if ( v32 )
      {
        v32 = 0;
        (*(void (__fastcall **)(struct IInputTarget *))(*(_QWORD *)v29 + 16LL))(v29);
      }
      if ( ++v11 == v12 )
        break;
      v5 = a4;
      v8 = a3;
      v9 = a1;
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180017c60  mov     rax, rsp
0x180017c63  mov     [rax+20h], r9
0x180017c67  mov     [rax+18h], r8d
0x180017c6b  mov     [rax+10h], rdx
0x180017c6f  mov     [rax+8], rcx
0x180017c73  push    rbx
0x180017c74  push    rbp
0x180017c75  push    rsi
0x180017c76  push    rdi
0x180017c77  push    r12
0x180017c79  push    r13
0x180017c7b  push    r14
0x180017c7d  push    r15
0x180017c7f  sub     rsp, 68h
0x180017c83  mov     rbx, r9
0x180017c86  mov     rdi, rdx
0x180017c89  mov     r10, rcx
0x180017c8c  xor     ebp, ebp
0x180017c8e  mov     [rax-68h], ebp
0x180017c91  mov     [rax-60h], rbp
0x180017c95  mov     rcx, [r9+8]
0x180017c99  test    rcx, rcx
0x180017c9c  jz      short loc_180017CB8
0x180017c9e  lea     rdx, [rax-60h]
0x180017ca2  call    cs:__imp_NtQueryCompositionInputSinkLuid
0x180017ca8  mov     r8d, [rsp+0A8h+arg_10]
0x180017cb0  mov     r10, [rsp+0A8h+arg_0]
0x180017cb8  mov     rcx, rdi
0x180017cbb  call    ??$?0AEBV?$allocator@U?$pair@$$CBIUTargetingInfo@ForegroundManager@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIUTargetingInfo@ForegroundManager@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBIUTargetingInfo@ForegroundManager@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,ForegroundManager::TargetingInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,ForegroundManager::TargetingInfo>>>>>>(std::allocator<std::pair<uint const,ForegroundManager::TargetingInfo>> const &)
0x180017cc0  mov     [rsp+0A8h+var_68], 1
0x180017cc8  mov     rax, [rbx+68h]
0x180017ccc  mov     rsi, [rax-18h]
0x180017cd0  mov     r12, [rax-10h]
0x180017cd4  cmp     rsi, r12
0x180017cd7  jz      loc_180017E0F
0x180017cdd  mov     r15, 1FFFFFFFFFFFFFFFh
0x180017ce7  mov     rax, [rsp+0A8h+arg_20]
0x180017cef  mov     [rsp+0A8h+var_78], rax; __int64
0x180017cf4  lea     rax, [rsp+0A8h+var_60]
0x180017cf9  mov     [rsp+0A8h+var_80], rax; __int64
0x180017cfe  mov     [rsp+0A8h+var_88], rbx; __int64
0x180017d03  mov     r9d, r8d
0x180017d06  mov     r8, rsi
0x180017d09  lea     rdx, [rsp+0A8h+var_58]; struct IInputTarget **
0x180017d0e  mov     rcx, r10; this
0x180017d11  call    ?GetTargetFromInputSite@DWMInputRouter@@AEAA?AV?$ComPtr@UIInputTarget@@@WRL@Microsoft@@AEBV?$ComPtr@VInputSite@@@34@W4InputType@@AEBUHitTestResult@@AEBU_LUID@@AEAV?$ComPtr@UIDCompInputTarget@@@34@@Z; DWMInputRouter::GetTargetFromInputSite(Microsoft::WRL::ComPtr<InputSite> const &,InputType,HitTestResult const &,_LUID const &,Microsoft::WRL::ComPtr<IDCompInputTarget> &)
0x180017d16  mov     r13, rax
0x180017d19  mov     rcx, [rdi+10h]
0x180017d1d  mov     r14, [rdi+8]
0x180017d21  cmp     r14, rcx
0x180017d24  jnz     loc_180017E23
0x180017d2a  mov     rax, [rdi]
0x180017d2d  mov     rbx, r14
0x180017d30  sub     rbx, rax
0x180017d33  sar     rbx, 3
0x180017d37  cmp     rbx, r15
0x180017d3a  jz      loc_180017E35
0x180017d40  lea     r15, [rbx+1]
0x180017d44  sub     rcx, rax
0x180017d47  sar     rcx, 3
0x180017d4b  mov     rdx, rcx
0x180017d4e  shr     rdx, 1
0x180017d51  mov     rbp, 1FFFFFFFFFFFFFFFh
0x180017d5b  mov     rax, rbp
0x180017d5e  sub     rax, rdx
0x180017d61  cmp     rcx, rax
0x180017d64  ja      short loc_180017D71
0x180017d66  lea     rbp, [rdx+rcx]
0x180017d6a  cmp     rbp, r15
0x180017d6d  cmovb   rbp, r15
0x180017d71  mov     rcx, rbp
0x180017d74  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x180017d79  mov     rcx, rax
0x180017d7c  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180017d81  mov     r10, rax
0x180017d84  lea     r9, [rax+rbx*8]
0x180017d88  mov     rdx, r13
0x180017d8b  mov     rcx, r9
0x180017d8e  call    ??0?$ComPtr@VInputSite@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<InputSite>::ComPtr<InputSite>(Microsoft::WRL::ComPtr<InputSite> &&)
0x180017d93  mov     rdx, [rdi+8]
0x180017d97  mov     r8, r10
0x180017d9a  mov     rcx, [rdi]
0x180017d9d  cmp     r14, rdx
0x180017da0  jz      short loc_180017DB5
0x180017da2  mov     rdx, r14
0x180017da5  call    ??$_Uninitialized_move@PEAV?$ComPtr@UIActivationListenerInputObjectProxy@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIActivationListenerInputObjectProxy@@@WRL@Microsoft@@@std@@@std@@YAPEAV?$ComPtr@UIActivationListenerInputObjectProxy@@@WRL@Microsoft@@QEAV123@0PEAV123@AEAV?$allocator@V?$ComPtr@UIActivationListenerInputObjectProxy@@@WRL@Microsoft@@@0@@Z; std::_Uninitialized_move<Microsoft::WRL::ComPtr<IActivationListenerInputObjectProxy> *,std::allocator<Microsoft::WRL::ComPtr<IActivationListenerInputObjectProxy>>>(Microsoft::WRL::ComPtr<IActivationListenerInputObjectProxy> * const,Microsoft::WRL::ComPtr<IActivationListenerInputObjectProxy> * const,Microsoft::WRL::ComPtr<IActivationListenerInputObjectProxy> *,std::allocator<Microsoft::WRL::ComPtr<IActivationListenerInputObjectProxy>> &)
0x180017daa  lea     r8, [r9+8]
0x180017dae  mov     rdx, [rdi+8]
0x180017db2  mov     rcx, r14
0x180017db5  call    ??$_Uninitialized_move@PEAV?$ComPtr@UIActivationListenerInputObjectProxy@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIActivationListenerInputObjectProxy@@@WRL@Microsoft@@@std@@@std@@YAPEAV?$ComPtr@UIActivationListenerInputObjectProxy@@@WRL@Microsoft@@QEAV123@0PEAV123@AEAV?$allocator@V?$ComPtr@UIActivationListenerInputObjectProxy@@@WRL@Microsoft@@@0@@Z; std::_Uninitialized_move<Microsoft::WRL::ComPtr<IActivationListenerInputObjectProxy> *,std::allocator<Microsoft::WRL::ComPtr<IActivationListenerInputObjectProxy>>>(Microsoft::WRL::ComPtr<IActivationListenerInputObjectProxy> * const,Microsoft::WRL::ComPtr<IActivationListenerInputObjectProxy> * const,Microsoft::WRL::ComPtr<IActivationListenerInputObjectProxy> *,std::allocator<Microsoft::WRL::ComPtr<IActivationListenerInputObjectProxy>> &)
0x180017dba  mov     r9, rbp
0x180017dbd  mov     r8, r15
0x180017dc0  mov     rdx, r10
0x180017dc3  mov     rcx, rdi
0x180017dc6  call    ?_Change_array@?$vector@V?$ComPtr@UIMPCInputProviderBase@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMPCInputProviderBase@@@WRL@Microsoft@@@std@@@std@@AEAAXQEAV?$ComPtr@UIMPCInputProviderBase@@@WRL@Microsoft@@_K1@Z; std::vector<Microsoft::WRL::ComPtr<IMPCInputProviderBase>>::_Change_array(Microsoft::WRL::ComPtr<IMPCInputProviderBase> * const,unsigned __int64,unsigned __int64)
0x180017dcb  xor     ebp, ebp
0x180017dcd  mov     rcx, [rsp+0A8h+var_58]
0x180017dd2  test    rcx, rcx
0x180017dd5  jz      short loc_180017DE9
0x180017dd7  mov     [rsp+0A8h+var_58], rbp
0x180017ddc  mov     rax, [rcx]
0x180017ddf  mov     rax, [rax+10h]
0x180017de3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017de8  nop
0x180017de9  add     rsi, 8
0x180017ded  cmp     rsi, r12
0x180017df0  jz      short loc_180017E0F
0x180017df2  mov     rbx, [rsp+0A8h+arg_18]
0x180017dfa  mov     r8d, [rsp+0A8h+arg_10]
0x180017e02  mov     r10, [rsp+0A8h+arg_0]
0x180017e0a  jmp     loc_180017CDD
0x180017e0f  mov     rax, rdi
0x180017e12  add     rsp, 68h
0x180017e16  pop     r15
0x180017e18  pop     r14
0x180017e1a  pop     r13
0x180017e1c  pop     r12
0x180017e1e  pop     rdi
0x180017e1f  pop     rsi
0x180017e20  pop     rbp
0x180017e21  pop     rbx
0x180017e22  retn
0x180017e23  mov     rdx, r13
0x180017e26  mov     rcx, r14
0x180017e29  call    ??0?$ComPtr@VInputSite@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<InputSite>::ComPtr<InputSite>(Microsoft::WRL::ComPtr<InputSite> &&)
0x180017e2e  add     qword ptr [rdi+8], 8
0x180017e33  jmp     short loc_180017DCD
0x180017e35  lea     rcx, aVectorTooLong; "vector too long"
0x180017e3c  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
