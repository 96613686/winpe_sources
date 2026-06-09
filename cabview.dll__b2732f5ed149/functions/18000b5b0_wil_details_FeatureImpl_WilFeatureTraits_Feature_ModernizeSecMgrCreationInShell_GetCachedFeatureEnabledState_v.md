# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetCachedFeatureEnabledState(void)

- ea: `0x18000b5b0`
- end: `0x18000b704`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `340`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c934`
- `0x18000d084`

## callees

- `0x180002620`
- `0x180003fd8`
- `0x180005510`
- `0x180009e8c`
- `0x18000b5b0`
- `0x18000b930`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b678`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b678`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  bool v8; // zf
  signed __int32 v9; // edx
  unsigned int v10; // ecx
  int v11; // r8d
  RTL_SRWLOCK *v13; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v14[2]; // [rsp+28h] [rbp-40h] BYREF
  int v15; // [rsp+38h] [rbp-30h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_ModernizeSecMgrCreationInShell__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ModernizeSecMgrCreationInShell__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v15 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetCurrentFeatureEnabledState(
      v5,
      &v13,
      &v15);
    v6 = *(_DWORD *)a2;
    v7 = (__int16)v13;
    do
    {
      v8 = v15 == 0;
      v9 = v6;
      *(_DWORD *)a2 = v6;
      v10 = v6;
      if ( !v8 && (v6 & 2) == 0 )
      {
        v10 = v7 & 0x9C1 | v6 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v10;
      }
      v11 = v6 & 4;
      if ( (v6 & 4) == 0 )
      {
        v10 = v7 & 0x400 | v10 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v10;
      }
      v6 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_ModernizeSecMgrCreationInShell__descriptor,
             v10,
             v6);
    }
    while ( v9 != v6 );
    if ( !v11 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_18001A190);
      v13 = &stru_18001A190;
      if ( !v4
        || v4 != dword_18001A1A4
        || (v14[0] = 3,
            v14[1] = Feature_ModernizeSecMgrCreationInShell__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18001A1C8, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ModernizeSecMgrCreationInShell__descriptor, 0xFFFFFFFB);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
    }
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000b5b0  mov     [rsp+arg_0], rbx
0x18000b5b5  mov     [rsp+arg_10], rbp
0x18000b5ba  push    rsi
0x18000b5bb  push    rdi
0x18000b5bc  push    r14
0x18000b5be  sub     rsp, 50h
0x18000b5c2  mov     rax, cs:__security_cookie
0x18000b5c9  xor     rax, rsp
0x18000b5cc  mov     [rsp+68h+var_28], rax
0x18000b5d1  mov     rsi, cs:Feature_ModernizeSecMgrCreationInShell__descriptor
0x18000b5d8  mov     rdi, rdx
0x18000b5db  mov     qword ptr [rdx], 0
0x18000b5e2  mov     eax, [rsi]
0x18000b5e4  mov     [rdx], eax
0x18000b5e6  and     eax, 6
0x18000b5e9  cmp     al, 6
0x18000b5eb  jz      loc_18000B6DF
0x18000b5f1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000b5f6  lea     r8, [rsp+68h+var_30]
0x18000b5fb  mov     [rsp+68h+var_30], 0
0x18000b603  lea     rdx, [rsp+68h+var_48]
0x18000b608  mov     ebp, eax
0x18000b60a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetCurrentFeatureEnabledState(int *)
0x18000b60f  mov     eax, [rdi]
0x18000b611  mov     rbx, [rsp+68h+var_48]
0x18000b616  cmp     [rsp+68h+var_30], 0
0x18000b61b  mov     edx, eax
0x18000b61d  mov     [rdi], eax
0x18000b61f  mov     ecx, eax
0x18000b621  jz      short loc_18000B63C
0x18000b623  test    dl, 2
0x18000b626  jnz     short loc_18000B63C
0x18000b628  and     ecx, 0FFFFF63Eh
0x18000b62e  mov     eax, ebx
0x18000b630  and     eax, 9C1h
0x18000b635  or      ecx, eax
0x18000b637  or      ecx, 2
0x18000b63a  mov     [rdi], ecx
0x18000b63c  mov     r8d, edx
0x18000b63f  and     r8d, 4
0x18000b643  jnz     short loc_18000B657
0x18000b645  btr     ecx, 0Ah
0x18000b649  mov     eax, ebx
0x18000b64b  and     eax, 400h
0x18000b650  or      ecx, eax
0x18000b652  or      ecx, 4
0x18000b655  mov     [rdi], ecx
0x18000b657  mov     eax, edx
0x18000b659  lock cmpxchg [rsi], ecx
0x18000b65d  jnz     short loc_18000B616
0x18000b65f  test    r8d, r8d
0x18000b662  jnz     short loc_18000B6C8
0x18000b664  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000b66a  test    eax, eax
0x18000b66c  jz      short loc_18000B6C8
0x18000b66e  lea     r14, stru_18001A190
0x18000b675  mov     rcx, r14; SRWLock
0x18000b678  call    cs:__imp_AcquireSRWLockExclusive
0x18000b67e  mov     eax, cs:dword_18001A1A4
0x18000b684  mov     [rsp+68h+var_48], r14
0x18000b689  test    ebp, ebp
0x18000b68b  jz      short loc_18000B6BA
0x18000b68d  cmp     ebp, eax
0x18000b68f  jnz     short loc_18000B6BA
0x18000b691  mov     r8d, 10h; unsigned __int64
0x18000b697  mov     [rsp+68h+var_40], 3
0x18000b6a0  lea     rdx, [rsp+68h+var_40]; void *
0x18000b6a5  mov     [rsp+68h+var_38], rsi
0x18000b6aa  lea     rcx, qword_18001A1C8; this
0x18000b6b1  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000b6b6  test    al, al
0x18000b6b8  jnz     short loc_18000B6BE
0x18000b6ba  lock and dword ptr [rsi], 0FFFFFFFBh
0x18000b6be  lea     rcx, [rsp+68h+var_48]
0x18000b6c3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000b6c8  mov     ecx, [rdi]
0x18000b6ca  test    cl, 2
0x18000b6cd  jnz     short loc_18000B6DF
0x18000b6cf  and     ecx, 0FFFFF63Eh
0x18000b6d5  and     ebx, 9C1h
0x18000b6db  or      ecx, ebx
0x18000b6dd  mov     [rdi], ecx
0x18000b6df  mov     rax, rdi
0x18000b6e2  mov     rcx, [rsp+68h+var_28]
0x18000b6e7  xor     rcx, rsp; StackCookie
0x18000b6ea  call    __security_check_cookie
0x18000b6ef  lea     r11, [rsp+68h+var_18]
0x18000b6f4  mov     rbx, [r11+20h]
0x18000b6f8  mov     rbp, [r11+30h]
0x18000b6fc  mov     rsp, r11
0x18000b6ff  pop     r14
0x18000b701  pop     rdi
0x18000b702  pop     rsi
0x18000b703  retn
```
