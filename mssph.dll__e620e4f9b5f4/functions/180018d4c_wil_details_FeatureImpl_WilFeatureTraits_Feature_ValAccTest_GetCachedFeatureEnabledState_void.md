# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180018d4c`
- end: `0x180018e85`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b77c`
- `0x18001c268`

## callees

- `0x18000d118`
- `0x180012908`
- `0x180015b28`
- `0x180018d4c`
- `0x180019744`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018e0a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018e0a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_1800367E8);
      v16 = &stru_1800367E8;
      if ( !v5
        || v5 != dword_1800367FC
        || (v14[0] = 3,
            v14[1] = Feature_ValAccTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180036820, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ValAccTest__descriptor, 0xFFFFFFFB);
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
0x180018d4c  mov     [rsp+arg_10], rbx
0x180018d51  mov     [rsp+arg_18], rbp
0x180018d56  mov     [rsp+arg_0], rcx
0x180018d5b  push    rsi
0x180018d5c  push    rdi
0x180018d5d  push    r14
0x180018d5f  sub     rsp, 30h
0x180018d63  mov     rsi, cs:Feature_ValAccTest__descriptor
0x180018d6a  mov     rdi, rdx
0x180018d6d  mov     qword ptr [rdx], 0
0x180018d74  mov     eax, [rsi]
0x180018d76  mov     [rdx], eax
0x180018d78  and     eax, 6
0x180018d7b  cmp     al, 6
0x180018d7d  jz      loc_180018E6F
0x180018d83  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180018d88  lea     r8, [rsp+48h+arg_0]
0x180018d8d  mov     dword ptr [rsp+48h+arg_0], 0
0x180018d95  lea     rdx, [rsp+48h+arg_8]
0x180018d9a  mov     ebp, eax
0x180018d9c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x180018da1  mov     eax, [rdi]
0x180018da3  mov     rbx, [rsp+48h+arg_8]
0x180018da8  cmp     dword ptr [rsp+48h+arg_0], 0
0x180018dad  mov     edx, eax
0x180018daf  mov     [rdi], eax
0x180018db1  mov     ecx, eax
0x180018db3  jz      short loc_180018DCE
0x180018db5  test    dl, 2
0x180018db8  jnz     short loc_180018DCE
0x180018dba  and     ecx, 0FFFFF63Eh
0x180018dc0  mov     eax, ebx
0x180018dc2  and     eax, 9C1h
0x180018dc7  or      ecx, eax
0x180018dc9  or      ecx, 2
0x180018dcc  mov     [rdi], ecx
0x180018dce  mov     r8d, edx
0x180018dd1  and     r8d, 4
0x180018dd5  jnz     short loc_180018DE9
0x180018dd7  btr     ecx, 0Ah
0x180018ddb  mov     eax, ebx
0x180018ddd  and     eax, 400h
0x180018de2  or      ecx, eax
0x180018de4  or      ecx, 4
0x180018de7  mov     [rdi], ecx
0x180018de9  mov     eax, edx
0x180018deb  lock cmpxchg [rsi], ecx
0x180018def  jnz     short loc_180018DA8
0x180018df1  test    r8d, r8d
0x180018df4  jnz     short loc_180018E5A
0x180018df6  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180018dfc  test    eax, eax
0x180018dfe  jz      short loc_180018E5A
0x180018e00  lea     r14, stru_1800367E8
0x180018e07  mov     rcx, r14; SRWLock
0x180018e0a  call    cs:__imp_AcquireSRWLockExclusive
0x180018e10  mov     eax, cs:dword_1800367FC
0x180018e16  mov     [rsp+48h+arg_8], r14
0x180018e1b  test    ebp, ebp
0x180018e1d  jz      short loc_180018E4C
0x180018e1f  cmp     ebp, eax
0x180018e21  jnz     short loc_180018E4C
0x180018e23  mov     r8d, 10h; unsigned __int64
0x180018e29  mov     [rsp+48h+var_28], 3
0x180018e32  lea     rdx, [rsp+48h+var_28]; void *
0x180018e37  mov     [rsp+48h+var_20], rsi
0x180018e3c  lea     rcx, qword_180036820; this
0x180018e43  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180018e48  test    al, al
0x180018e4a  jnz     short loc_180018E50
0x180018e4c  lock and dword ptr [rsi], 0FFFFFFFBh
0x180018e50  lea     rcx, [rsp+48h+arg_8]
0x180018e55  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180018e5a  mov     eax, [rdi]
0x180018e5c  test    al, 2
0x180018e5e  jnz     short loc_180018E6F
0x180018e60  and     eax, 0FFFFF63Eh
0x180018e65  and     ebx, 9C1h
0x180018e6b  or      eax, ebx
0x180018e6d  mov     [rdi], eax
0x180018e6f  mov     rbx, [rsp+48h+arg_10]
0x180018e74  mov     rax, rdi
0x180018e77  mov     rbp, [rsp+48h+arg_18]
0x180018e7c  add     rsp, 30h
0x180018e80  pop     r14
0x180018e82  pop     rdi
0x180018e83  pop     rsi
0x180018e84  retn
```
