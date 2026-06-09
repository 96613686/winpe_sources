# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Eaphost_TVS_Fixes>::GetCachedFeatureEnabledState(void)

- ea: `0x180025ff8`
- end: `0x180026138`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Eaphost_TVS_Fixes@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029aac`
- `0x18002beec`

## callees

- `0x18000ac08`
- `0x18000b8e0`
- `0x18000dba4`
- `0x180025ff8`
- `0x180026288`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800260b6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800260b6`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Eaphost_TVS_Fixes>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Eaphost_TVS_Fixes__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Eaphost_TVS_Fixes__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Eaphost_TVS_Fixes>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Eaphost_TVS_Fixes__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_18004E660);
      v16 = &stru_18004E660;
      if ( !v5
        || v5 != dword_18004E674
        || (v14[0] = 3,
            v14[1] = Feature_Eaphost_TVS_Fixes__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18004E6A8, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Eaphost_TVS_Fixes__descriptor, 0xFFFFFFFB);
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
0x180025ff8  mov     [rsp+arg_10], rbx
0x180025ffd  mov     [rsp+arg_18], rbp
0x180026002  mov     [rsp+arg_0], rcx
0x180026007  push    rsi
0x180026008  push    rdi
0x180026009  push    r14
0x18002600b  sub     rsp, 30h
0x18002600f  mov     rsi, cs:Feature_Eaphost_TVS_Fixes__descriptor
0x180026016  mov     rdi, rdx
0x180026019  mov     qword ptr [rdx], 0
0x180026020  mov     eax, [rsi]
0x180026022  mov     [rdx], eax
0x180026024  and     eax, 6
0x180026027  cmp     al, 6
0x180026029  jz      loc_180026121
0x18002602f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180026034  lea     r8, [rsp+48h+arg_0]
0x180026039  mov     dword ptr [rsp+48h+arg_0], 0
0x180026041  lea     rdx, [rsp+48h+arg_8]
0x180026046  mov     ebp, eax
0x180026048  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Eaphost_TVS_Fixes@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Eaphost_TVS_Fixes>::GetCurrentFeatureEnabledState(int *)
0x18002604d  mov     eax, [rdi]
0x18002604f  mov     rbx, [rsp+48h+arg_8]
0x180026054  cmp     dword ptr [rsp+48h+arg_0], 0
0x180026059  mov     edx, eax
0x18002605b  mov     [rdi], eax
0x18002605d  mov     ecx, eax
0x18002605f  jz      short loc_18002607A
0x180026061  test    dl, 2
0x180026064  jnz     short loc_18002607A
0x180026066  and     ecx, 0FFFFF63Eh
0x18002606c  mov     eax, ebx
0x18002606e  and     eax, 9C1h
0x180026073  or      ecx, eax
0x180026075  or      ecx, 2
0x180026078  mov     [rdi], ecx
0x18002607a  mov     r8d, edx
0x18002607d  and     r8d, 4
0x180026081  jnz     short loc_180026095
0x180026083  btr     ecx, 0Ah
0x180026087  mov     eax, ebx
0x180026089  and     eax, 400h
0x18002608e  or      ecx, eax
0x180026090  or      ecx, 4
0x180026093  mov     [rdi], ecx
0x180026095  mov     eax, edx
0x180026097  lock cmpxchg [rsi], ecx
0x18002609b  jnz     short loc_180026054
0x18002609d  test    r8d, r8d
0x1800260a0  jnz     short loc_18002610C
0x1800260a2  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800260a8  test    eax, eax
0x1800260aa  jz      short loc_18002610C
0x1800260ac  lea     r14, stru_18004E660
0x1800260b3  mov     rcx, r14; SRWLock
0x1800260b6  call    cs:__imp_AcquireSRWLockExclusive
0x1800260bd  nop     dword ptr [rax+rax+00h]
0x1800260c2  mov     eax, cs:dword_18004E674
0x1800260c8  mov     [rsp+48h+arg_8], r14
0x1800260cd  test    ebp, ebp
0x1800260cf  jz      short loc_1800260FE
0x1800260d1  cmp     ebp, eax
0x1800260d3  jnz     short loc_1800260FE
0x1800260d5  mov     r8d, 10h; unsigned __int64
0x1800260db  mov     [rsp+48h+var_28], 3
0x1800260e4  lea     rdx, [rsp+48h+var_28]; void *
0x1800260e9  mov     [rsp+48h+var_20], rsi
0x1800260ee  lea     rcx, qword_18004E6A8; this
0x1800260f5  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800260fa  test    al, al
0x1800260fc  jnz     short loc_180026102
0x1800260fe  lock and dword ptr [rsi], 0FFFFFFFBh
0x180026102  lea     rcx, [rsp+48h+arg_8]
0x180026107  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002610c  mov     eax, [rdi]
0x18002610e  test    al, 2
0x180026110  jnz     short loc_180026121
0x180026112  and     eax, 0FFFFF63Eh
0x180026117  and     ebx, 9C1h
0x18002611d  or      eax, ebx
0x18002611f  mov     [rdi], eax
0x180026121  mov     rbx, [rsp+48h+arg_10]
0x180026126  mov     rax, rdi
0x180026129  mov     rbp, [rsp+48h+arg_18]
0x18002612e  add     rsp, 30h
0x180026132  pop     r14
0x180026134  pop     rdi
0x180026135  pop     rsi
0x180026136  retn
```
