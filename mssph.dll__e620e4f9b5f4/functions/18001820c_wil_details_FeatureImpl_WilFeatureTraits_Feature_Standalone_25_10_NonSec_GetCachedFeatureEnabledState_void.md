# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18001820c`
- end: `0x180018345`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b2c8`

## callees

- `0x18000d118`
- `0x180012908`
- `0x180015b28`
- `0x18001820c`
- `0x180019128`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800182ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800182ca`

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
      AcquireSRWLockExclusive(&stru_1800367E8);
      v16 = &stru_1800367E8;
      if ( !v5
        || v5 != dword_1800367FC
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_25_10_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180036820, v14, 0x10u)) )
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
0x18001820c  mov     [rsp+arg_10], rbx
0x180018211  mov     [rsp+arg_18], rbp
0x180018216  mov     [rsp+arg_0], rcx
0x18001821b  push    rsi
0x18001821c  push    rdi
0x18001821d  push    r14
0x18001821f  sub     rsp, 30h
0x180018223  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18001822a  mov     rdi, rdx
0x18001822d  mov     qword ptr [rdx], 0
0x180018234  mov     eax, [rsi]
0x180018236  mov     [rdx], eax
0x180018238  and     eax, 6
0x18001823b  cmp     al, 6
0x18001823d  jz      loc_18001832F
0x180018243  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180018248  lea     r8, [rsp+48h+arg_0]
0x18001824d  mov     dword ptr [rsp+48h+arg_0], 0
0x180018255  lea     rdx, [rsp+48h+arg_8]
0x18001825a  mov     ebp, eax
0x18001825c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(int *)
0x180018261  mov     eax, [rdi]
0x180018263  mov     rbx, [rsp+48h+arg_8]
0x180018268  cmp     dword ptr [rsp+48h+arg_0], 0
0x18001826d  mov     edx, eax
0x18001826f  mov     [rdi], eax
0x180018271  mov     ecx, eax
0x180018273  jz      short loc_18001828E
0x180018275  test    dl, 2
0x180018278  jnz     short loc_18001828E
0x18001827a  and     ecx, 0FFFFF63Eh
0x180018280  mov     eax, ebx
0x180018282  and     eax, 9C1h
0x180018287  or      ecx, eax
0x180018289  or      ecx, 2
0x18001828c  mov     [rdi], ecx
0x18001828e  mov     r8d, edx
0x180018291  and     r8d, 4
0x180018295  jnz     short loc_1800182A9
0x180018297  btr     ecx, 0Ah
0x18001829b  mov     eax, ebx
0x18001829d  and     eax, 400h
0x1800182a2  or      ecx, eax
0x1800182a4  or      ecx, 4
0x1800182a7  mov     [rdi], ecx
0x1800182a9  mov     eax, edx
0x1800182ab  lock cmpxchg [rsi], ecx
0x1800182af  jnz     short loc_180018268
0x1800182b1  test    r8d, r8d
0x1800182b4  jnz     short loc_18001831A
0x1800182b6  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800182bc  test    eax, eax
0x1800182be  jz      short loc_18001831A
0x1800182c0  lea     r14, stru_1800367E8
0x1800182c7  mov     rcx, r14; SRWLock
0x1800182ca  call    cs:__imp_AcquireSRWLockExclusive
0x1800182d0  mov     eax, cs:dword_1800367FC
0x1800182d6  mov     [rsp+48h+arg_8], r14
0x1800182db  test    ebp, ebp
0x1800182dd  jz      short loc_18001830C
0x1800182df  cmp     ebp, eax
0x1800182e1  jnz     short loc_18001830C
0x1800182e3  mov     r8d, 10h; unsigned __int64
0x1800182e9  mov     [rsp+48h+var_28], 3
0x1800182f2  lea     rdx, [rsp+48h+var_28]; void *
0x1800182f7  mov     [rsp+48h+var_20], rsi
0x1800182fc  lea     rcx, qword_180036820; this
0x180018303  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180018308  test    al, al
0x18001830a  jnz     short loc_180018310
0x18001830c  lock and dword ptr [rsi], 0FFFFFFFBh
0x180018310  lea     rcx, [rsp+48h+arg_8]
0x180018315  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001831a  mov     eax, [rdi]
0x18001831c  test    al, 2
0x18001831e  jnz     short loc_18001832F
0x180018320  and     eax, 0FFFFF63Eh
0x180018325  and     ebx, 9C1h
0x18001832b  or      eax, ebx
0x18001832d  mov     [rdi], eax
0x18001832f  mov     rbx, [rsp+48h+arg_10]
0x180018334  mov     rax, rdi
0x180018337  mov     rbp, [rsp+48h+arg_18]
0x18001833c  add     rsp, 30h
0x180018340  pop     r14
0x180018342  pop     rdi
0x180018343  pop     rsi
0x180018344  retn
```
