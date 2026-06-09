# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180012fa8`
- end: `0x1800130e1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001442c`

## callees

- `0x18000f11c`
- `0x180012c54`
- `0x180012fa8`
- `0x180013e28`
- `0x180015b2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013066`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013066`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800226CC
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_25_10_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800226F0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, 0xFFFFFFFB);
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
0x180012fa8  mov     [rsp+arg_10], rbx
0x180012fad  mov     [rsp+arg_18], rbp
0x180012fb2  mov     [rsp+arg_0], rcx
0x180012fb7  push    rsi
0x180012fb8  push    rdi
0x180012fb9  push    r14
0x180012fbb  sub     rsp, 30h
0x180012fbf  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x180012fc6  mov     rdi, rdx
0x180012fc9  mov     qword ptr [rdx], 0
0x180012fd0  mov     eax, [rsi]
0x180012fd2  mov     [rdx], eax
0x180012fd4  and     eax, 6
0x180012fd7  cmp     al, 6
0x180012fd9  jz      loc_1800130CB
0x180012fdf  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012fe4  lea     r8, [rsp+48h+arg_0]
0x180012fe9  mov     dword ptr [rsp+48h+arg_0], 0
0x180012ff1  lea     rdx, [rsp+48h+arg_8]
0x180012ff6  mov     ebp, eax
0x180012ff8  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(int *)
0x180012ffd  mov     eax, [rdi]
0x180012fff  mov     rbx, [rsp+48h+arg_8]
0x180013004  cmp     dword ptr [rsp+48h+arg_0], 0
0x180013009  mov     edx, eax
0x18001300b  mov     [rdi], eax
0x18001300d  mov     ecx, eax
0x18001300f  jz      short loc_18001302A
0x180013011  test    dl, 2
0x180013014  jnz     short loc_18001302A
0x180013016  and     ecx, 0FFFFF63Eh
0x18001301c  mov     eax, ebx
0x18001301e  and     eax, 9C1h
0x180013023  or      ecx, eax
0x180013025  or      ecx, 2
0x180013028  mov     [rdi], ecx
0x18001302a  mov     r8d, edx
0x18001302d  and     r8d, 4
0x180013031  jnz     short loc_180013045
0x180013033  btr     ecx, 0Ah
0x180013037  mov     eax, ebx
0x180013039  and     eax, 400h
0x18001303e  or      ecx, eax
0x180013040  or      ecx, 4
0x180013043  mov     [rdi], ecx
0x180013045  mov     eax, edx
0x180013047  lock cmpxchg [rsi], ecx
0x18001304b  jnz     short loc_180013004
0x18001304d  test    r8d, r8d
0x180013050  jnz     short loc_1800130B6
0x180013052  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180013058  test    eax, eax
0x18001305a  jz      short loc_1800130B6
0x18001305c  lea     r14, SRWLock
0x180013063  mov     rcx, r14; SRWLock
0x180013066  call    cs:__imp_AcquireSRWLockExclusive
0x18001306c  mov     eax, cs:dword_1800226CC
0x180013072  mov     [rsp+48h+arg_8], r14
0x180013077  test    ebp, ebp
0x180013079  jz      short loc_1800130A8
0x18001307b  cmp     ebp, eax
0x18001307d  jnz     short loc_1800130A8
0x18001307f  mov     r8d, 10h; unsigned __int64
0x180013085  mov     [rsp+48h+var_28], 3
0x18001308e  lea     rdx, [rsp+48h+var_28]; void *
0x180013093  mov     [rsp+48h+var_20], rsi
0x180013098  lea     rcx, qword_1800226F0; this
0x18001309f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800130a4  test    al, al
0x1800130a6  jnz     short loc_1800130AC
0x1800130a8  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800130ac  lea     rcx, [rsp+48h+arg_8]
0x1800130b1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800130b6  mov     eax, [rdi]
0x1800130b8  test    al, 2
0x1800130ba  jnz     short loc_1800130CB
0x1800130bc  and     eax, 0FFFFF63Eh
0x1800130c1  and     ebx, 9C1h
0x1800130c7  or      eax, ebx
0x1800130c9  mov     [rdi], eax
0x1800130cb  mov     rbx, [rsp+48h+arg_10]
0x1800130d0  mov     rax, rdi
0x1800130d3  mov     rbp, [rsp+48h+arg_18]
0x1800130d8  add     rsp, 30h
0x1800130dc  pop     r14
0x1800130de  pop     rdi
0x1800130df  pop     rsi
0x1800130e0  retn
```
