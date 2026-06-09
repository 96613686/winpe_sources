# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x18003b6c0`
- end: `0x18003b7f3`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `307`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003cf54`
- `0x18003db64`

## callees

- `0x18003af20`
- `0x18003b30c`
- `0x18003b6c0`
- `0x18003bb20`
- `0x18003dc50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b77e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b77e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  int v12; // r8d
  unsigned __int64 v13; // r8
  _QWORD Source[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details *v16; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v17; // [rsp+58h] [rbp+10h] BYREF

  v16 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v16) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
      v6,
      &v17,
      &v16);
    v7 = *(_DWORD *)a2;
    v8 = (__int16)v17;
    do
    {
      v9 = (_DWORD)v16 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      v12 = v7 & 4;
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxAccOptimization__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v17 = &SRWLock;
      if ( !v5
        || v5 != dword_18009D90C
        || (Source[0] = 3,
            Source[1] = Feature_UxAccOptimization__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18009D930, Source, v13)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_UxAccOptimization__descriptor, 0xFFFFFFFB);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v17);
    }
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18003b6c0  mov     [rsp+arg_10], rbx
0x18003b6c5  mov     [rsp+arg_18], rbp
0x18003b6ca  mov     [rsp+arg_0], rcx
0x18003b6cf  push    rsi
0x18003b6d0  push    rdi
0x18003b6d1  push    r14
0x18003b6d3  sub     rsp, 30h
0x18003b6d7  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x18003b6de  mov     rdi, rdx
0x18003b6e1  mov     qword ptr [rdx], 0
0x18003b6e8  mov     eax, [rsi]
0x18003b6ea  mov     [rdx], eax
0x18003b6ec  and     eax, 6
0x18003b6ef  cmp     al, 6
0x18003b6f1  jz      loc_18003B7DD
0x18003b6f7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18003b6fc  lea     r8, [rsp+48h+arg_0]
0x18003b701  mov     dword ptr [rsp+48h+arg_0], 0
0x18003b709  lea     rdx, [rsp+48h+arg_8]
0x18003b70e  mov     ebp, eax
0x18003b710  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x18003b715  mov     eax, [rdi]
0x18003b717  mov     rbx, [rsp+48h+arg_8]
0x18003b71c  cmp     dword ptr [rsp+48h+arg_0], 0
0x18003b721  mov     edx, eax
0x18003b723  mov     [rdi], eax
0x18003b725  mov     ecx, eax
0x18003b727  jz      short loc_18003B742
0x18003b729  test    dl, 2
0x18003b72c  jnz     short loc_18003B742
0x18003b72e  and     ecx, 0FFFFF63Eh
0x18003b734  mov     eax, ebx
0x18003b736  and     eax, 9C1h
0x18003b73b  or      ecx, eax
0x18003b73d  or      ecx, 2
0x18003b740  mov     [rdi], ecx
0x18003b742  mov     r8d, edx
0x18003b745  and     r8d, 4
0x18003b749  jnz     short loc_18003B75D
0x18003b74b  btr     ecx, 0Ah
0x18003b74f  mov     eax, ebx
0x18003b751  and     eax, 400h
0x18003b756  or      ecx, eax
0x18003b758  or      ecx, 4
0x18003b75b  mov     [rdi], ecx
0x18003b75d  mov     eax, edx
0x18003b75f  lock cmpxchg [rsi], ecx
0x18003b763  jnz     short loc_18003B71C
0x18003b765  test    r8d, r8d
0x18003b768  jnz     short loc_18003B7C8
0x18003b76a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18003b770  test    eax, eax
0x18003b772  jz      short loc_18003B7C8
0x18003b774  lea     r14, SRWLock
0x18003b77b  mov     rcx, r14; SRWLock
0x18003b77e  call    cs:__imp_AcquireSRWLockExclusive
0x18003b784  mov     eax, cs:dword_18009D90C
0x18003b78a  mov     [rsp+48h+arg_8], r14
0x18003b78f  test    ebp, ebp
0x18003b791  jz      short loc_18003B7BA
0x18003b793  cmp     ebp, eax
0x18003b795  jnz     short loc_18003B7BA
0x18003b797  lea     rdx, [rsp+48h+Source]; Source
0x18003b79c  mov     [rsp+48h+Source], 3
0x18003b7a5  lea     rcx, qword_18009D930; this
0x18003b7ac  mov     [rsp+48h+var_20], rsi
0x18003b7b1  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003b7b6  test    al, al
0x18003b7b8  jnz     short loc_18003B7BE
0x18003b7ba  lock and dword ptr [rsi], 0FFFFFFFBh
0x18003b7be  lea     rcx, [rsp+48h+arg_8]
0x18003b7c3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003b7c8  mov     eax, [rdi]
0x18003b7ca  test    al, 2
0x18003b7cc  jnz     short loc_18003B7DD
0x18003b7ce  and     eax, 0FFFFF63Eh
0x18003b7d3  and     ebx, 9C1h
0x18003b7d9  or      eax, ebx
0x18003b7db  mov     [rdi], eax
0x18003b7dd  mov     rbx, [rsp+48h+arg_10]
0x18003b7e2  mov     rax, rdi
0x18003b7e5  mov     rbp, [rsp+48h+arg_18]
0x18003b7ea  add     rsp, 30h
0x18003b7ee  pop     r14
0x18003b7f0  pop     rdi
0x18003b7f1  pop     rsi
0x18003b7f2  retn
```
