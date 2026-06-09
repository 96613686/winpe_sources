# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52435335>::GetCachedFeatureEnabledState(void)

- ea: `0x180023178`
- end: `0x1800232b5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID52435335@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023708`

## callees

- `0x180007c28`
- `0x180008684`
- `0x18000c930`
- `0x180023178`
- `0x180023458`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002323c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002323c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52435335>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ID52435335__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ID52435335__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52435335>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ID52435335__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180035B78);
      v16 = &stru_180035B78;
      if ( !v5
        || v5 != dword_180035B8C
        || (v14[0] = 0,
            v14[1] = Feature_ID52435335__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180035BB0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ID52435335__descriptor, 0xFFFFF7C1);
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
0x180023178  mov     [rsp-28h+arg_10], rbx
0x18002317d  mov     [rsp-28h+arg_0], rcx
0x180023182  push    rbp
0x180023183  push    rsi
0x180023184  push    rdi
0x180023185  push    r14
0x180023187  push    r15
0x180023189  mov     rbp, rsp
0x18002318c  sub     rsp, 30h
0x180023190  mov     rsi, cs:Feature_ID52435335__descriptor
0x180023197  mov     rdi, rdx
0x18002319a  mov     qword ptr [rdx], 0
0x1800231a1  mov     eax, [rsi]
0x1800231a3  mov     [rdx], eax
0x1800231a5  and     eax, 6
0x1800231a8  cmp     al, 6
0x1800231aa  jz      loc_1800232A1
0x1800231b0  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800231b5  lea     r8, [rbp+arg_0]
0x1800231b9  mov     dword ptr [rbp+arg_0], 0
0x1800231c0  lea     rdx, [rbp+arg_8]
0x1800231c4  mov     r14d, eax
0x1800231c7  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID52435335@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52435335>::GetCurrentFeatureEnabledState(int *)
0x1800231cc  test    r14d, r14d
0x1800231cf  jnz     short loc_1800231D5
0x1800231d1  mov     dword ptr [rbp+arg_0], r14d
0x1800231d5  mov     eax, [rdi]
0x1800231d7  mov     rbx, [rbp+arg_8]
0x1800231db  cmp     dword ptr [rbp+arg_0], 0
0x1800231df  mov     edx, eax
0x1800231e1  mov     [rdi], eax
0x1800231e3  mov     ecx, eax
0x1800231e5  jz      short loc_180023200
0x1800231e7  test    dl, 2
0x1800231ea  jnz     short loc_180023200
0x1800231ec  and     ecx, 0FFFFF63Eh
0x1800231f2  mov     eax, ebx
0x1800231f4  and     eax, 9C1h
0x1800231f9  or      ecx, eax
0x1800231fb  or      ecx, 2
0x1800231fe  mov     [rdi], ecx
0x180023200  mov     r8d, edx
0x180023203  and     r8d, 4
0x180023207  jnz     short loc_18002321B
0x180023209  btr     ecx, 0Ah
0x18002320d  mov     eax, ebx
0x18002320f  and     eax, 400h
0x180023214  or      ecx, eax
0x180023216  or      ecx, 4
0x180023219  mov     [rdi], ecx
0x18002321b  mov     eax, edx
0x18002321d  lock cmpxchg [rsi], ecx
0x180023221  jnz     short loc_1800231DB
0x180023223  test    r8d, r8d
0x180023226  jnz     short loc_18002328C
0x180023228  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002322e  test    eax, eax
0x180023230  jz      short loc_18002328C
0x180023232  lea     r15, stru_180035B78
0x180023239  mov     rcx, r15; SRWLock
0x18002323c  call    cs:__imp_AcquireSRWLockExclusive
0x180023242  mov     eax, cs:dword_180035B8C
0x180023248  mov     [rbp+arg_8], r15
0x18002324c  test    r14d, r14d
0x18002324f  jz      short loc_18002327C
0x180023251  cmp     r14d, eax
0x180023254  jnz     short loc_18002327C
0x180023256  mov     r8d, 10h; unsigned __int64
0x18002325c  mov     [rbp+var_10], 0
0x180023264  lea     rdx, [rbp+var_10]; void *
0x180023268  mov     [rbp+var_8], rsi
0x18002326c  lea     rcx, qword_180035BB0; this
0x180023273  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180023278  test    al, al
0x18002327a  jnz     short loc_180023283
0x18002327c  lock and dword ptr [rsi], 0FFFFF7C1h
0x180023283  lea     rcx, [rbp+arg_8]
0x180023287  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002328c  mov     eax, [rdi]
0x18002328e  test    al, 2
0x180023290  jnz     short loc_1800232A1
0x180023292  and     eax, 0FFFFF63Eh
0x180023297  and     ebx, 9C1h
0x18002329d  or      eax, ebx
0x18002329f  mov     [rdi], eax
0x1800232a1  mov     rbx, [rsp+30h+arg_10]
0x1800232a6  mov     rax, rdi
0x1800232a9  add     rsp, 30h
0x1800232ad  pop     r15
0x1800232af  pop     r14
0x1800232b1  pop     rdi
0x1800232b2  pop     rsi
0x1800232b3  pop     rbp
0x1800232b4  retn
```
