# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetCachedFeatureEnabledState(void)

- ea: `0x14001e934`
- end: `0x14001ea6d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140020230`
- `0x1400211d0`

## callees

- `0x1400050dc`
- `0x140006020`
- `0x14000c520`
- `0x14001e934`
- `0x14001ea74`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14001e9f2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001e9f2`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Narrator_AddUpdates__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Narrator_AddUpdates__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Narrator_AddUpdates__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_140036C30);
      v16 = &stru_140036C30;
      if ( !v5
        || v5 != dword_140036C44
        || (v14[0] = 1,
            v14[1] = Feature_Narrator_AddUpdates__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_140036C68, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Narrator_AddUpdates__descriptor, 0xFFFFFFFB);
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
0x14001e934  mov     [rsp+arg_10], rbx
0x14001e939  mov     [rsp+arg_18], rbp
0x14001e93e  mov     [rsp+arg_0], rcx
0x14001e943  push    rsi
0x14001e944  push    rdi
0x14001e945  push    r14
0x14001e947  sub     rsp, 30h
0x14001e94b  mov     rsi, cs:Feature_Narrator_AddUpdates__descriptor
0x14001e952  mov     rdi, rdx
0x14001e955  mov     qword ptr [rdx], 0
0x14001e95c  mov     eax, [rsi]
0x14001e95e  mov     [rdx], eax
0x14001e960  and     eax, 6
0x14001e963  cmp     al, 6
0x14001e965  jz      loc_14001EA57
0x14001e96b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14001e970  lea     r8, [rsp+48h+arg_0]
0x14001e975  mov     dword ptr [rsp+48h+arg_0], 0
0x14001e97d  lea     rdx, [rsp+48h+arg_8]
0x14001e982  mov     ebp, eax
0x14001e984  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetCurrentFeatureEnabledState(int *)
0x14001e989  mov     eax, [rdi]
0x14001e98b  mov     rbx, [rsp+48h+arg_8]
0x14001e990  cmp     dword ptr [rsp+48h+arg_0], 0
0x14001e995  mov     edx, eax
0x14001e997  mov     [rdi], eax
0x14001e999  mov     ecx, eax
0x14001e99b  jz      short loc_14001E9B6
0x14001e99d  test    dl, 2
0x14001e9a0  jnz     short loc_14001E9B6
0x14001e9a2  and     ecx, 0FFFFF63Eh
0x14001e9a8  mov     eax, ebx
0x14001e9aa  and     eax, 9C1h
0x14001e9af  or      ecx, eax
0x14001e9b1  or      ecx, 2
0x14001e9b4  mov     [rdi], ecx
0x14001e9b6  mov     r8d, edx
0x14001e9b9  and     r8d, 4
0x14001e9bd  jnz     short loc_14001E9D1
0x14001e9bf  btr     ecx, 0Ah
0x14001e9c3  mov     eax, ebx
0x14001e9c5  and     eax, 400h
0x14001e9ca  or      ecx, eax
0x14001e9cc  or      ecx, 4
0x14001e9cf  mov     [rdi], ecx
0x14001e9d1  mov     eax, edx
0x14001e9d3  lock cmpxchg [rsi], ecx
0x14001e9d7  jnz     short loc_14001E990
0x14001e9d9  test    r8d, r8d
0x14001e9dc  jnz     short loc_14001EA42
0x14001e9de  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14001e9e4  test    eax, eax
0x14001e9e6  jz      short loc_14001EA42
0x14001e9e8  lea     r14, stru_140036C30
0x14001e9ef  mov     rcx, r14; SRWLock
0x14001e9f2  call    cs:__imp_AcquireSRWLockExclusive
0x14001e9f8  mov     eax, cs:dword_140036C44
0x14001e9fe  mov     [rsp+48h+arg_8], r14
0x14001ea03  test    ebp, ebp
0x14001ea05  jz      short loc_14001EA34
0x14001ea07  cmp     ebp, eax
0x14001ea09  jnz     short loc_14001EA34
0x14001ea0b  mov     r8d, 10h; unsigned __int64
0x14001ea11  mov     [rsp+48h+var_28], 1
0x14001ea1a  lea     rdx, [rsp+48h+var_28]; void *
0x14001ea1f  mov     [rsp+48h+var_20], rsi
0x14001ea24  lea     rcx, qword_140036C68; this
0x14001ea2b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14001ea30  test    al, al
0x14001ea32  jnz     short loc_14001EA38
0x14001ea34  lock and dword ptr [rsi], 0FFFFFFFBh
0x14001ea38  lea     rcx, [rsp+48h+arg_8]
0x14001ea3d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14001ea42  mov     eax, [rdi]
0x14001ea44  test    al, 2
0x14001ea46  jnz     short loc_14001EA57
0x14001ea48  and     eax, 0FFFFF63Eh
0x14001ea4d  and     ebx, 9C1h
0x14001ea53  or      eax, ebx
0x14001ea55  mov     [rdi], eax
0x14001ea57  mov     rbx, [rsp+48h+arg_10]
0x14001ea5c  mov     rax, rdi
0x14001ea5f  mov     rbp, [rsp+48h+arg_18]
0x14001ea64  add     rsp, 30h
0x14001ea68  pop     r14
0x14001ea6a  pop     rdi
0x14001ea6b  pop     rsi
0x14001ea6c  retn
```
