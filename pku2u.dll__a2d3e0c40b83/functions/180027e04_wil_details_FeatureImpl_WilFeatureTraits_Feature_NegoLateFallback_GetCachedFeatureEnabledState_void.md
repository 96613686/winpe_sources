# wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::GetCachedFeatureEnabledState(void)

- ea: `0x180027e04`
- end: `0x180027f3d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_NegoLateFallback@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029a68`
- `0x18002adb0`

## callees

- `0x18001f7b4`
- `0x1800279d4`
- `0x180027e04`
- `0x180027fe8`
- `0x18002ae1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027ec2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027ec2`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::GetCachedFeatureEnabledState(
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
  _QWORD v14[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details *v15; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v16; // [rsp+58h] [rbp+10h] BYREF

  v15 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_NegoLateFallback__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_NegoLateFallback__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::GetCurrentFeatureEnabledState(
      v6,
      &v16,
      &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_NegoLateFallback__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800548E4
        || (v14[0] = 3,
            v14[1] = Feature_NegoLateFallback__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180054908, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_NegoLateFallback__descriptor, 0xFFFFFFFB);
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
0x180027e04  mov     [rsp+arg_10], rbx
0x180027e09  mov     [rsp+arg_18], rbp
0x180027e0e  mov     [rsp+arg_0], rcx
0x180027e13  push    rsi
0x180027e14  push    rdi
0x180027e15  push    r14
0x180027e17  sub     rsp, 30h
0x180027e1b  mov     rsi, cs:Feature_NegoLateFallback__descriptor
0x180027e22  mov     rdi, rdx
0x180027e25  mov     qword ptr [rdx], 0
0x180027e2c  mov     eax, [rsi]
0x180027e2e  mov     [rdx], eax
0x180027e30  and     eax, 6
0x180027e33  cmp     al, 6
0x180027e35  jz      loc_180027F27
0x180027e3b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180027e40  lea     r8, [rsp+48h+arg_0]
0x180027e45  mov     dword ptr [rsp+48h+arg_0], 0
0x180027e4d  lea     rdx, [rsp+48h+arg_8]
0x180027e52  mov     ebp, eax
0x180027e54  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_NegoLateFallback@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::GetCurrentFeatureEnabledState(int *)
0x180027e59  mov     eax, [rdi]
0x180027e5b  mov     rbx, [rsp+48h+arg_8]
0x180027e60  cmp     dword ptr [rsp+48h+arg_0], 0
0x180027e65  mov     edx, eax
0x180027e67  mov     [rdi], eax
0x180027e69  mov     ecx, eax
0x180027e6b  jz      short loc_180027E86
0x180027e6d  test    dl, 2
0x180027e70  jnz     short loc_180027E86
0x180027e72  and     ecx, 0FFFFF63Eh
0x180027e78  mov     eax, ebx
0x180027e7a  and     eax, 9C1h
0x180027e7f  or      ecx, eax
0x180027e81  or      ecx, 2
0x180027e84  mov     [rdi], ecx
0x180027e86  mov     r8d, edx
0x180027e89  and     r8d, 4
0x180027e8d  jnz     short loc_180027EA1
0x180027e8f  btr     ecx, 0Ah
0x180027e93  mov     eax, ebx
0x180027e95  and     eax, 400h
0x180027e9a  or      ecx, eax
0x180027e9c  or      ecx, 4
0x180027e9f  mov     [rdi], ecx
0x180027ea1  mov     eax, edx
0x180027ea3  lock cmpxchg [rsi], ecx
0x180027ea7  jnz     short loc_180027E60
0x180027ea9  test    r8d, r8d
0x180027eac  jnz     short loc_180027F12
0x180027eae  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180027eb4  test    eax, eax
0x180027eb6  jz      short loc_180027F12
0x180027eb8  lea     r14, SRWLock
0x180027ebf  mov     rcx, r14; SRWLock
0x180027ec2  call    cs:__imp_AcquireSRWLockExclusive
0x180027ec8  mov     eax, cs:dword_1800548E4
0x180027ece  mov     [rsp+48h+arg_8], r14
0x180027ed3  test    ebp, ebp
0x180027ed5  jz      short loc_180027F04
0x180027ed7  cmp     ebp, eax
0x180027ed9  jnz     short loc_180027F04
0x180027edb  mov     r8d, 10h; unsigned __int64
0x180027ee1  mov     [rsp+48h+var_28], 3
0x180027eea  lea     rdx, [rsp+48h+var_28]; void *
0x180027eef  mov     [rsp+48h+var_20], rsi
0x180027ef4  lea     rcx, qword_180054908; this
0x180027efb  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180027f00  test    al, al
0x180027f02  jnz     short loc_180027F08
0x180027f04  lock and dword ptr [rsi], 0FFFFFFFBh
0x180027f08  lea     rcx, [rsp+48h+arg_8]
0x180027f0d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180027f12  mov     eax, [rdi]
0x180027f14  test    al, 2
0x180027f16  jnz     short loc_180027F27
0x180027f18  and     eax, 0FFFFF63Eh
0x180027f1d  and     ebx, 9C1h
0x180027f23  or      eax, ebx
0x180027f25  mov     [rdi], eax
0x180027f27  mov     rbx, [rsp+48h+arg_10]
0x180027f2c  mov     rax, rdi
0x180027f2f  mov     rbp, [rsp+48h+arg_18]
0x180027f34  add     rsp, 30h
0x180027f38  pop     r14
0x180027f3a  pop     rdi
0x180027f3b  pop     rsi
0x180027f3c  retn
```
