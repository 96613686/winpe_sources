# DusmCore::RemoveConnection(DusmConnection const &)

- ea: `0x18001f9e0`
- end: `0x18001faa0`
- name: `?RemoveConnection@DusmCore@@SAXAEBVDusmConnection@@@Z`
- size: `192`
- prototype: `void __fastcall(const struct DusmConnection *)`
- caller_count: `8`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180032988`
- `0x180036280`
- `0x180036be8`
- `0x1800391a0`
- `0x180039240`
- `0x180039a3c`
- `0x180039cd8`
- `0x18003c8b0`

## callees

- `0x18000f094`
- `0x18000f684`
- `0x18001e1e0`
- `0x18001e6f4`
- `0x18001f7a8`
- `0x18001f9e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f9ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f9ff`

## pseudocode

```c
void __fastcall DusmCore::RemoveConnection(const struct DusmConnection *a1)
{
  LPCRITICAL_SECTION v1; // rbx
  LPCRITICAL_SECTION v3; // rsi
  __int64 v4; // rbx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdx
  __int64 v6; // r14
  __int64 v7; // rdi
  __int64 v8; // rbp
  LPCRITICAL_SECTION v9; // [rsp+40h] [rbp+8h] BYREF
  char v10; // [rsp+48h] [rbp+10h] BYREF

  v1 = DusmCore::s_pInstance;
  EnterCriticalSection(DusmCore::s_pInstance);
  v3 = DusmCore::s_pInstance;
  v9 = v1;
  v4 = *(_QWORD *)&DusmCore::s_pInstance[1].LockCount;
  DebugInfo = DusmCore::s_pInstance[1].DebugInfo;
  v6 = (v4 - (__int64)DebugInfo) >> 4;
  v7 = *(_QWORD *)std::remove_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_std::shared_ptr_DusmConnection_________DusmCore::RemoveConnection_::_2_::_lambda_1___(
                    &v10,
                    DebugInfo,
                    v4,
                    a1);
  if ( v7 != v4 )
  {
    v8 = *(_QWORD *)&v3[1].LockCount;
    while ( v4 != v8 )
    {
      std::shared_ptr<DusmDataPlanTraits>::operator=(v7, v4);
      v7 += 16;
      v4 += 16;
    }
    std::_Destroy_range<std::allocator<std::shared_ptr<DusmConnection>>>(v7, *(_QWORD *)&v3[1].LockCount);
    *(_QWORD *)&v3[1].LockCount = v7;
  }
  if ( v6 != (__int64)(*(_QWORD *)&DusmCore::s_pInstance[1].LockCount
                     - (unsigned __int64)DusmCore::s_pInstance[1].DebugInfo) >> 4 )
    DusmCore::PublishGlobalWnfState((DusmCore *)DusmCore::s_pInstance);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v9);
}

```

## disassembly

```asm
0x18001f9e0  mov     [rsp+arg_10], rbx
0x18001f9e5  mov     [rsp+arg_18], rbp
0x18001f9ea  push    rsi
0x18001f9eb  push    rdi
0x18001f9ec  push    r14
0x18001f9ee  sub     rsp, 20h
0x18001f9f2  mov     rbx, cs:?s_pInstance@DusmCore@@0PEAV1@EA; DusmCore * DusmCore::s_pInstance
0x18001f9f9  mov     rdi, rcx
0x18001f9fc  mov     rcx, rbx; lpCriticalSection
0x18001f9ff  call    cs:__imp_EnterCriticalSection
0x18001fa05  mov     rsi, cs:?s_pInstance@DusmCore@@0PEAV1@EA; DusmCore * DusmCore::s_pInstance
0x18001fa0c  lea     rcx, [rsp+38h+arg_8]
0x18001fa11  mov     [rsp+38h+arg_0], rbx
0x18001fa16  mov     r9, rdi
0x18001fa19  mov     rbx, [rsi+30h]
0x18001fa1d  mov     rdx, [rsi+28h]
0x18001fa21  mov     r14, rbx
0x18001fa24  sub     r14, rdx
0x18001fa27  mov     r8, rbx
0x18001fa2a  sar     r14, 4
0x18001fa2e  call    std__remove_if_std___Vector_iterator_std___Vector_val_std___Simple_types_std__shared_ptr_DusmConnection_________DusmCore__RemoveConnection____2____lambda_1___
0x18001fa33  mov     rdi, [rax]
0x18001fa36  cmp     rdi, rbx
0x18001fa39  jz      short loc_18001FA66
0x18001fa3b  mov     rbp, [rsi+30h]
0x18001fa3f  jmp     short loc_18001FA51
0x18001fa41  mov     rdx, rbx
0x18001fa44  call    ??4?$shared_ptr@VDusmDataPlanTraits@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<DusmDataPlanTraits>::operator=(std::shared_ptr<DusmDataPlanTraits> &&)
0x18001fa49  add     rdi, 10h
0x18001fa4d  add     rbx, 10h
0x18001fa51  mov     rcx, rdi
0x18001fa54  cmp     rbx, rbp
0x18001fa57  jnz     short loc_18001FA41
0x18001fa59  mov     rdx, [rsi+30h]
0x18001fa5d  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VDusmConnection@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VDusmConnection@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VDusmConnection@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<DusmConnection>>>(std::shared_ptr<DusmConnection> *,std::shared_ptr<DusmConnection> * const,std::allocator<std::shared_ptr<DusmConnection>> &)
0x18001fa62  mov     [rsi+30h], rdi
0x18001fa66  mov     rcx, cs:?s_pInstance@DusmCore@@0PEAV1@EA; this
0x18001fa6d  mov     rax, [rcx+30h]
0x18001fa71  sub     rax, [rcx+28h]
0x18001fa75  sar     rax, 4
0x18001fa79  cmp     r14, rax
0x18001fa7c  jz      short loc_18001FA83
0x18001fa7e  call    ?PublishGlobalWnfState@DusmCore@@AEAAXXZ; DusmCore::PublishGlobalWnfState(void)
0x18001fa83  lea     rcx, [rsp+38h+arg_0]
0x18001fa88  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001fa8d  mov     rbx, [rsp+38h+arg_10]
0x18001fa92  mov     rbp, [rsp+38h+arg_18]
0x18001fa97  add     rsp, 20h
0x18001fa9b  pop     r14
0x18001fa9d  pop     rdi
0x18001fa9e  pop     rsi
0x18001fa9f  retn
```
