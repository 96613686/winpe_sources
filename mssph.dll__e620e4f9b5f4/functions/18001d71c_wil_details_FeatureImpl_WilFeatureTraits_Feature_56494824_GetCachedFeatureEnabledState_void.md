# wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::GetCachedFeatureEnabledState(void)

- ea: `0x18001d71c`
- end: `0x18001d855`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001dfa8`
- `0x18001e25c`

## callees

- `0x18000d118`
- `0x180012908`
- `0x180015b28`
- `0x18001d71c`
- `0x18001db7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d7da`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d7da`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_56494824__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_56494824__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_56494824__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_1800367E8);
      v16 = &stru_1800367E8;
      if ( !v5
        || v5 != dword_1800367FC
        || (v14[0] = 3,
            v14[1] = Feature_56494824__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180036820, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_56494824__descriptor, 0xFFFFFFFB);
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
0x18001d71c  mov     [rsp+arg_10], rbx
0x18001d721  mov     [rsp+arg_18], rbp
0x18001d726  mov     [rsp+arg_0], rcx
0x18001d72b  push    rsi
0x18001d72c  push    rdi
0x18001d72d  push    r14
0x18001d72f  sub     rsp, 30h
0x18001d733  mov     rsi, cs:Feature_56494824__descriptor
0x18001d73a  mov     rdi, rdx
0x18001d73d  mov     qword ptr [rdx], 0
0x18001d744  mov     eax, [rsi]
0x18001d746  mov     [rdx], eax
0x18001d748  and     eax, 6
0x18001d74b  cmp     al, 6
0x18001d74d  jz      loc_18001D83F
0x18001d753  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001d758  lea     r8, [rsp+48h+arg_0]
0x18001d75d  mov     dword ptr [rsp+48h+arg_0], 0
0x18001d765  lea     rdx, [rsp+48h+arg_8]
0x18001d76a  mov     ebp, eax
0x18001d76c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::GetCurrentFeatureEnabledState(int *)
0x18001d771  mov     eax, [rdi]
0x18001d773  mov     rbx, [rsp+48h+arg_8]
0x18001d778  cmp     dword ptr [rsp+48h+arg_0], 0
0x18001d77d  mov     edx, eax
0x18001d77f  mov     [rdi], eax
0x18001d781  mov     ecx, eax
0x18001d783  jz      short loc_18001D79E
0x18001d785  test    dl, 2
0x18001d788  jnz     short loc_18001D79E
0x18001d78a  and     ecx, 0FFFFF63Eh
0x18001d790  mov     eax, ebx
0x18001d792  and     eax, 9C1h
0x18001d797  or      ecx, eax
0x18001d799  or      ecx, 2
0x18001d79c  mov     [rdi], ecx
0x18001d79e  mov     r8d, edx
0x18001d7a1  and     r8d, 4
0x18001d7a5  jnz     short loc_18001D7B9
0x18001d7a7  btr     ecx, 0Ah
0x18001d7ab  mov     eax, ebx
0x18001d7ad  and     eax, 400h
0x18001d7b2  or      ecx, eax
0x18001d7b4  or      ecx, 4
0x18001d7b7  mov     [rdi], ecx
0x18001d7b9  mov     eax, edx
0x18001d7bb  lock cmpxchg [rsi], ecx
0x18001d7bf  jnz     short loc_18001D778
0x18001d7c1  test    r8d, r8d
0x18001d7c4  jnz     short loc_18001D82A
0x18001d7c6  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001d7cc  test    eax, eax
0x18001d7ce  jz      short loc_18001D82A
0x18001d7d0  lea     r14, stru_1800367E8
0x18001d7d7  mov     rcx, r14; SRWLock
0x18001d7da  call    cs:__imp_AcquireSRWLockExclusive
0x18001d7e0  mov     eax, cs:dword_1800367FC
0x18001d7e6  mov     [rsp+48h+arg_8], r14
0x18001d7eb  test    ebp, ebp
0x18001d7ed  jz      short loc_18001D81C
0x18001d7ef  cmp     ebp, eax
0x18001d7f1  jnz     short loc_18001D81C
0x18001d7f3  mov     r8d, 10h; unsigned __int64
0x18001d7f9  mov     [rsp+48h+var_28], 3
0x18001d802  lea     rdx, [rsp+48h+var_28]; void *
0x18001d807  mov     [rsp+48h+var_20], rsi
0x18001d80c  lea     rcx, qword_180036820; this
0x18001d813  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001d818  test    al, al
0x18001d81a  jnz     short loc_18001D820
0x18001d81c  lock and dword ptr [rsi], 0FFFFFFFBh
0x18001d820  lea     rcx, [rsp+48h+arg_8]
0x18001d825  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001d82a  mov     eax, [rdi]
0x18001d82c  test    al, 2
0x18001d82e  jnz     short loc_18001D83F
0x18001d830  and     eax, 0FFFFF63Eh
0x18001d835  and     ebx, 9C1h
0x18001d83b  or      eax, ebx
0x18001d83d  mov     [rdi], eax
0x18001d83f  mov     rbx, [rsp+48h+arg_10]
0x18001d844  mov     rax, rdi
0x18001d847  mov     rbp, [rsp+48h+arg_18]
0x18001d84c  add     rsp, 30h
0x18001d850  pop     r14
0x18001d852  pop     rdi
0x18001d853  pop     rsi
0x18001d854  retn
```
