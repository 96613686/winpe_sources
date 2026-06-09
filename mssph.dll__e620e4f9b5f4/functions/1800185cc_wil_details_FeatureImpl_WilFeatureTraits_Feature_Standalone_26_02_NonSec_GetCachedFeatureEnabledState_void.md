# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1800185cc`
- end: `0x180018705`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b454`

## callees

- `0x18000d118`
- `0x180012908`
- `0x180015b28`
- `0x1800185cc`
- `0x18001929c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001868a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001868a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_1800367E8);
      v16 = &stru_1800367E8;
      if ( !v5
        || v5 != dword_1800367FC
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_26_02_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180036820, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor, 0xFFFFFFFB);
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
0x1800185cc  mov     [rsp+arg_10], rbx
0x1800185d1  mov     [rsp+arg_18], rbp
0x1800185d6  mov     [rsp+arg_0], rcx
0x1800185db  push    rsi
0x1800185dc  push    rdi
0x1800185dd  push    r14
0x1800185df  sub     rsp, 30h
0x1800185e3  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x1800185ea  mov     rdi, rdx
0x1800185ed  mov     qword ptr [rdx], 0
0x1800185f4  mov     eax, [rsi]
0x1800185f6  mov     [rdx], eax
0x1800185f8  and     eax, 6
0x1800185fb  cmp     al, 6
0x1800185fd  jz      loc_1800186EF
0x180018603  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180018608  lea     r8, [rsp+48h+arg_0]
0x18001860d  mov     dword ptr [rsp+48h+arg_0], 0
0x180018615  lea     rdx, [rsp+48h+arg_8]
0x18001861a  mov     ebp, eax
0x18001861c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCurrentFeatureEnabledState(int *)
0x180018621  mov     eax, [rdi]
0x180018623  mov     rbx, [rsp+48h+arg_8]
0x180018628  cmp     dword ptr [rsp+48h+arg_0], 0
0x18001862d  mov     edx, eax
0x18001862f  mov     [rdi], eax
0x180018631  mov     ecx, eax
0x180018633  jz      short loc_18001864E
0x180018635  test    dl, 2
0x180018638  jnz     short loc_18001864E
0x18001863a  and     ecx, 0FFFFF63Eh
0x180018640  mov     eax, ebx
0x180018642  and     eax, 9C1h
0x180018647  or      ecx, eax
0x180018649  or      ecx, 2
0x18001864c  mov     [rdi], ecx
0x18001864e  mov     r8d, edx
0x180018651  and     r8d, 4
0x180018655  jnz     short loc_180018669
0x180018657  btr     ecx, 0Ah
0x18001865b  mov     eax, ebx
0x18001865d  and     eax, 400h
0x180018662  or      ecx, eax
0x180018664  or      ecx, 4
0x180018667  mov     [rdi], ecx
0x180018669  mov     eax, edx
0x18001866b  lock cmpxchg [rsi], ecx
0x18001866f  jnz     short loc_180018628
0x180018671  test    r8d, r8d
0x180018674  jnz     short loc_1800186DA
0x180018676  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001867c  test    eax, eax
0x18001867e  jz      short loc_1800186DA
0x180018680  lea     r14, stru_1800367E8
0x180018687  mov     rcx, r14; SRWLock
0x18001868a  call    cs:__imp_AcquireSRWLockExclusive
0x180018690  mov     eax, cs:dword_1800367FC
0x180018696  mov     [rsp+48h+arg_8], r14
0x18001869b  test    ebp, ebp
0x18001869d  jz      short loc_1800186CC
0x18001869f  cmp     ebp, eax
0x1800186a1  jnz     short loc_1800186CC
0x1800186a3  mov     r8d, 10h; unsigned __int64
0x1800186a9  mov     [rsp+48h+var_28], 3
0x1800186b2  lea     rdx, [rsp+48h+var_28]; void *
0x1800186b7  mov     [rsp+48h+var_20], rsi
0x1800186bc  lea     rcx, qword_180036820; this
0x1800186c3  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800186c8  test    al, al
0x1800186ca  jnz     short loc_1800186D0
0x1800186cc  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800186d0  lea     rcx, [rsp+48h+arg_8]
0x1800186d5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800186da  mov     eax, [rdi]
0x1800186dc  test    al, 2
0x1800186de  jnz     short loc_1800186EF
0x1800186e0  and     eax, 0FFFFF63Eh
0x1800186e5  and     ebx, 9C1h
0x1800186eb  or      eax, ebx
0x1800186ed  mov     [rdi], eax
0x1800186ef  mov     rbx, [rsp+48h+arg_10]
0x1800186f4  mov     rax, rdi
0x1800186f7  mov     rbp, [rsp+48h+arg_18]
0x1800186fc  add     rsp, 30h
0x180018700  pop     r14
0x180018702  pop     rdi
0x180018703  pop     rsi
0x180018704  retn
```
