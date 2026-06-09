# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180018d1c`
- end: `0x180018e5b`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001b230`

## callees

- `0x180013750`
- `0x180016c90`
- `0x180018d1c`
- `0x18001c040`
- `0x18001c640`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018dcb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018dcb`

## pseudocode

```c
bool __fastcall wil::details::IsFeatureConfigured(
        wil::details *a1,
        unsigned int a2,
        unsigned __int8 a3,
        int a4,
        _DWORD *a5)
{
  int v5; // esi
  __int64 *v7; // rbx
  unsigned int v10; // eax
  unsigned int v11; // edi
  int v12; // eax
  int v13; // edx
  bool v14; // si
  char v15; // al
  RTL_SRWLOCK *v16; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v17[6]; // [rsp+28h] [rbp-30h] BYREF
  int v18; // [rsp+78h] [rbp+20h] BYREF

  v5 = a3;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (*(_DWORD *)v7 & 2) != 0 )
  {
    *a5 = 1;
    return (unsigned int)wil_RtlStagingConfig_QueryFeatureState((__int64)a1, a2, a3, 0) != 0;
  }
  else
  {
    v10 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v18 = 0;
    v11 = v10;
    *a5 = 1;
    v12 = wil_RtlStagingConfig_QueryFeatureState((__int64)a1, a2, v5, &v18);
    v13 = v18;
    v14 = v12 != 0;
    v15 = _InterlockedExchange((volatile __int32 *)v7, (v18 != 0) + 6);
    if ( !v13 && (v15 & 4) == 0 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v11
        || v11 != dword_1800316D4
        || (v17[0] = 0,
            v17[1] = v7,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180031708, v17, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)v7, 0xFFFFF7C1);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
    }
    return v14;
  }
}

```

## disassembly

```asm
0x180018d1c  mov     [rsp+arg_0], rbx
0x180018d21  mov     [rsp+arg_8], rbp
0x180018d26  push    rsi
0x180018d27  push    rdi
0x180018d28  push    r14
0x180018d2a  sub     rsp, 40h
0x180018d2e  test    r9d, r9d
0x180018d31  movzx   esi, r8b
0x180018d35  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180018d3c  mov     ebp, edx
0x180018d3e  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180018d45  mov     r14, rcx
0x180018d48  cmovnz  rbx, rax
0x180018d4c  mov     r9d, [rbx]
0x180018d4f  mov     eax, r9d
0x180018d52  and     al, 3
0x180018d54  cmp     al, 2
0x180018d56  jnz     short loc_180018D5F
0x180018d58  xor     al, al
0x180018d5a  jmp     loc_180018E47
0x180018d5f  test    r9b, 2
0x180018d63  jnz     loc_180018E29
0x180018d69  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180018d6e  mov     rcx, [rsp+58h+arg_20]
0x180018d76  lea     r9, [rsp+58h+arg_18]
0x180018d7b  mov     r8d, esi
0x180018d7e  mov     [rsp+58h+arg_18], 0
0x180018d86  mov     edx, ebp
0x180018d88  mov     edi, eax
0x180018d8a  mov     dword ptr [rcx], 1
0x180018d90  mov     rcx, r14
0x180018d93  call    wil_RtlStagingConfig_QueryFeatureState
0x180018d98  mov     edx, [rsp+58h+arg_18]
0x180018d9c  test    eax, eax
0x180018d9e  mov     ecx, edx
0x180018da0  setnz   sil
0x180018da4  neg     ecx
0x180018da6  sbb     eax, eax
0x180018da8  neg     eax
0x180018daa  add     eax, 6
0x180018dad  xchg    eax, [rbx]
0x180018daf  test    edx, edx
0x180018db1  jnz     short loc_180018E24
0x180018db3  test    al, 4
0x180018db5  jnz     short loc_180018E24
0x180018db7  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180018dbd  test    eax, eax
0x180018dbf  jz      short loc_180018E24
0x180018dc1  lea     rbp, SRWLock
0x180018dc8  mov     rcx, rbp; SRWLock
0x180018dcb  call    cs:__imp_AcquireSRWLockExclusive
0x180018dd2  nop     dword ptr [rax+rax+00h]
0x180018dd7  mov     eax, cs:dword_1800316D4
0x180018ddd  mov     [rsp+58h+var_38], rbp
0x180018de2  test    edi, edi
0x180018de4  jz      short loc_180018E13
0x180018de6  cmp     edi, eax
0x180018de8  jnz     short loc_180018E13
0x180018dea  mov     r8d, 10h; unsigned __int64
0x180018df0  mov     [rsp+58h+var_30], 0
0x180018df9  lea     rdx, [rsp+58h+var_30]; void *
0x180018dfe  mov     [rsp+58h+var_28], rbx
0x180018e03  lea     rcx, qword_180031708; this
0x180018e0a  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180018e0f  test    al, al
0x180018e11  jnz     short loc_180018E1A
0x180018e13  lock and dword ptr [rbx], 0FFFFF7C1h
0x180018e1a  lea     rcx, [rsp+58h+var_38]
0x180018e1f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180018e24  mov     al, sil
0x180018e27  jmp     short loc_180018E47
0x180018e29  mov     rax, [rsp+58h+arg_20]
0x180018e31  mov     r8d, esi
0x180018e34  xor     r9d, r9d
0x180018e37  mov     dword ptr [rax], 1
0x180018e3d  call    wil_RtlStagingConfig_QueryFeatureState
0x180018e42  test    eax, eax
0x180018e44  setnz   al
0x180018e47  mov     rbx, [rsp+58h+arg_0]
0x180018e4c  mov     rbp, [rsp+58h+arg_8]
0x180018e51  add     rsp, 40h
0x180018e55  pop     r14
0x180018e57  pop     rdi
0x180018e58  pop     rsi
0x180018e59  retn
```
