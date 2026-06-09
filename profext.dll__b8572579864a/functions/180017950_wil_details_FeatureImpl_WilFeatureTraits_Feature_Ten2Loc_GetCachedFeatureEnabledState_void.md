# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x180017950`
- end: `0x180017a90`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a4d4`
- `0x18001ba60`

## callees

- `0x180013750`
- `0x180016c90`
- `0x180017950`
- `0x180018418`
- `0x18001c040`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017a0e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017a0e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Ten2Loc__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800316D4
        || (v14[0] = 3,
            v14[1] = Feature_Ten2Loc__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180031708, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Ten2Loc__descriptor, 0xFFFFFFFB);
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
0x180017950  mov     [rsp+arg_10], rbx
0x180017955  mov     [rsp+arg_18], rbp
0x18001795a  mov     [rsp+arg_0], rcx
0x18001795f  push    rsi
0x180017960  push    rdi
0x180017961  push    r14
0x180017963  sub     rsp, 30h
0x180017967  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x18001796e  mov     rdi, rdx
0x180017971  mov     qword ptr [rdx], 0
0x180017978  mov     eax, [rsi]
0x18001797a  mov     [rdx], eax
0x18001797c  and     eax, 6
0x18001797f  cmp     al, 6
0x180017981  jz      loc_180017A79
0x180017987  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001798c  lea     r8, [rsp+48h+arg_0]
0x180017991  mov     dword ptr [rsp+48h+arg_0], 0
0x180017999  lea     rdx, [rsp+48h+arg_8]
0x18001799e  mov     ebp, eax
0x1800179a0  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x1800179a5  mov     eax, [rdi]
0x1800179a7  mov     rbx, [rsp+48h+arg_8]
0x1800179ac  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800179b1  mov     edx, eax
0x1800179b3  mov     [rdi], eax
0x1800179b5  mov     ecx, eax
0x1800179b7  jz      short loc_1800179D2
0x1800179b9  test    dl, 2
0x1800179bc  jnz     short loc_1800179D2
0x1800179be  and     ecx, 0FFFFF63Eh
0x1800179c4  mov     eax, ebx
0x1800179c6  and     eax, 9C1h
0x1800179cb  or      ecx, eax
0x1800179cd  or      ecx, 2
0x1800179d0  mov     [rdi], ecx
0x1800179d2  mov     r8d, edx
0x1800179d5  and     r8d, 4
0x1800179d9  jnz     short loc_1800179ED
0x1800179db  btr     ecx, 0Ah
0x1800179df  mov     eax, ebx
0x1800179e1  and     eax, 400h
0x1800179e6  or      ecx, eax
0x1800179e8  or      ecx, 4
0x1800179eb  mov     [rdi], ecx
0x1800179ed  mov     eax, edx
0x1800179ef  lock cmpxchg [rsi], ecx
0x1800179f3  jnz     short loc_1800179AC
0x1800179f5  test    r8d, r8d
0x1800179f8  jnz     short loc_180017A64
0x1800179fa  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180017a00  test    eax, eax
0x180017a02  jz      short loc_180017A64
0x180017a04  lea     r14, SRWLock
0x180017a0b  mov     rcx, r14; SRWLock
0x180017a0e  call    cs:__imp_AcquireSRWLockExclusive
0x180017a15  nop     dword ptr [rax+rax+00h]
0x180017a1a  mov     eax, cs:dword_1800316D4
0x180017a20  mov     [rsp+48h+arg_8], r14
0x180017a25  test    ebp, ebp
0x180017a27  jz      short loc_180017A56
0x180017a29  cmp     ebp, eax
0x180017a2b  jnz     short loc_180017A56
0x180017a2d  mov     r8d, 10h; unsigned __int64
0x180017a33  mov     [rsp+48h+var_28], 3
0x180017a3c  lea     rdx, [rsp+48h+var_28]; void *
0x180017a41  mov     [rsp+48h+var_20], rsi
0x180017a46  lea     rcx, qword_180031708; this
0x180017a4d  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180017a52  test    al, al
0x180017a54  jnz     short loc_180017A5A
0x180017a56  lock and dword ptr [rsi], 0FFFFFFFBh
0x180017a5a  lea     rcx, [rsp+48h+arg_8]
0x180017a5f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180017a64  mov     eax, [rdi]
0x180017a66  test    al, 2
0x180017a68  jnz     short loc_180017A79
0x180017a6a  and     eax, 0FFFFF63Eh
0x180017a6f  and     ebx, 9C1h
0x180017a75  or      eax, ebx
0x180017a77  mov     [rdi], eax
0x180017a79  mov     rbx, [rsp+48h+arg_10]
0x180017a7e  mov     rax, rdi
0x180017a81  mov     rbp, [rsp+48h+arg_18]
0x180017a86  add     rsp, 30h
0x180017a8a  pop     r14
0x180017a8c  pop     rdi
0x180017a8d  pop     rsi
0x180017a8e  retn
```
