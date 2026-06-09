# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OSK_LockscreenCheck>::GetCachedFeatureEnabledState(void)

- ea: `0x14001b294`
- end: `0x14001b3d1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OSK_LockscreenCheck@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14001b498`

## callees

- `0x1400050dc`
- `0x140006020`
- `0x14000c520`
- `0x14001b294`
- `0x14001b3d8`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14001b358`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001b358`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OSK_LockscreenCheck>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // r14d
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  int v12; // r8d
  _QWORD v14[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details *v15; // [rsp+60h] [rbp+30h] BYREF
  RTL_SRWLOCK *v16; // [rsp+68h] [rbp+38h] BYREF

  v15 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Servicing_OSK_LockscreenCheck__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_OSK_LockscreenCheck__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OSK_LockscreenCheck>::GetCurrentFeatureEnabledState(
      v6,
      &v16,
      &v15);
    if ( !v5 )
      LODWORD(v15) = 0;
    v7 = *(_DWORD *)a2;
    v8 = (__int16)v16;
    do
    {
      v9 = (_DWORD)v15 == 0;
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
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_Servicing_OSK_LockscreenCheck__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_140036C30);
      v16 = &stru_140036C30;
      if ( !v5
        || v5 != dword_140036C44
        || (v14[0] = 0,
            v14[1] = Feature_Servicing_OSK_LockscreenCheck__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_140036C68, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Servicing_OSK_LockscreenCheck__descriptor, 0xFFFFF7C1);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
    }
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x14001b294  mov     [rsp-28h+arg_10], rbx
0x14001b299  mov     [rsp-28h+arg_0], rcx
0x14001b29e  push    rbp
0x14001b29f  push    rsi
0x14001b2a0  push    rdi
0x14001b2a1  push    r14
0x14001b2a3  push    r15
0x14001b2a5  mov     rbp, rsp
0x14001b2a8  sub     rsp, 30h
0x14001b2ac  mov     rsi, cs:Feature_Servicing_OSK_LockscreenCheck__descriptor
0x14001b2b3  mov     rdi, rdx
0x14001b2b6  mov     qword ptr [rdx], 0
0x14001b2bd  mov     eax, [rsi]
0x14001b2bf  mov     [rdx], eax
0x14001b2c1  and     eax, 6
0x14001b2c4  cmp     al, 6
0x14001b2c6  jz      loc_14001B3BD
0x14001b2cc  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14001b2d1  lea     r8, [rbp+arg_0]
0x14001b2d5  mov     dword ptr [rbp+arg_0], 0
0x14001b2dc  lea     rdx, [rbp+arg_8]
0x14001b2e0  mov     r14d, eax
0x14001b2e3  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OSK_LockscreenCheck@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OSK_LockscreenCheck>::GetCurrentFeatureEnabledState(int *)
0x14001b2e8  test    r14d, r14d
0x14001b2eb  jnz     short loc_14001B2F1
0x14001b2ed  mov     dword ptr [rbp+arg_0], r14d
0x14001b2f1  mov     eax, [rdi]
0x14001b2f3  mov     rbx, [rbp+arg_8]
0x14001b2f7  cmp     dword ptr [rbp+arg_0], 0
0x14001b2fb  mov     edx, eax
0x14001b2fd  mov     [rdi], eax
0x14001b2ff  mov     ecx, eax
0x14001b301  jz      short loc_14001B31C
0x14001b303  test    dl, 2
0x14001b306  jnz     short loc_14001B31C
0x14001b308  and     ecx, 0FFFFF63Eh
0x14001b30e  mov     eax, ebx
0x14001b310  and     eax, 9C1h
0x14001b315  or      ecx, eax
0x14001b317  or      ecx, 2
0x14001b31a  mov     [rdi], ecx
0x14001b31c  mov     r8d, edx
0x14001b31f  and     r8d, 4
0x14001b323  jnz     short loc_14001B337
0x14001b325  btr     ecx, 0Ah
0x14001b329  mov     eax, ebx
0x14001b32b  and     eax, 400h
0x14001b330  or      ecx, eax
0x14001b332  or      ecx, 4
0x14001b335  mov     [rdi], ecx
0x14001b337  mov     eax, edx
0x14001b339  lock cmpxchg [rsi], ecx
0x14001b33d  jnz     short loc_14001B2F7
0x14001b33f  test    r8d, r8d
0x14001b342  jnz     short loc_14001B3A8
0x14001b344  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14001b34a  test    eax, eax
0x14001b34c  jz      short loc_14001B3A8
0x14001b34e  lea     r15, stru_140036C30
0x14001b355  mov     rcx, r15; SRWLock
0x14001b358  call    cs:__imp_AcquireSRWLockExclusive
0x14001b35e  mov     eax, cs:dword_140036C44
0x14001b364  mov     [rbp+arg_8], r15
0x14001b368  test    r14d, r14d
0x14001b36b  jz      short loc_14001B398
0x14001b36d  cmp     r14d, eax
0x14001b370  jnz     short loc_14001B398
0x14001b372  mov     r8d, 10h; unsigned __int64
0x14001b378  mov     [rbp+var_10], 0
0x14001b380  lea     rdx, [rbp+var_10]; void *
0x14001b384  mov     [rbp+var_8], rsi
0x14001b388  lea     rcx, qword_140036C68; this
0x14001b38f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14001b394  test    al, al
0x14001b396  jnz     short loc_14001B39F
0x14001b398  lock and dword ptr [rsi], 0FFFFF7C1h
0x14001b39f  lea     rcx, [rbp+arg_8]
0x14001b3a3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14001b3a8  mov     eax, [rdi]
0x14001b3aa  test    al, 2
0x14001b3ac  jnz     short loc_14001B3BD
0x14001b3ae  and     eax, 0FFFFF63Eh
0x14001b3b3  and     ebx, 9C1h
0x14001b3b9  or      eax, ebx
0x14001b3bb  mov     [rdi], eax
0x14001b3bd  mov     rbx, [rsp+30h+arg_10]
0x14001b3c2  mov     rax, rdi
0x14001b3c5  add     rsp, 30h
0x14001b3c9  pop     r15
0x14001b3cb  pop     r14
0x14001b3cd  pop     rdi
0x14001b3ce  pop     rsi
0x14001b3cf  pop     rbp
0x14001b3d0  retn
```
