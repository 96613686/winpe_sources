# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1800130e8`
- end: `0x180013221`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001415c`

## callees

- `0x18000f11c`
- `0x180012c54`
- `0x1800130e8`
- `0x180013e9c`
- `0x180015b2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800131a6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800131a6`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800226CC
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_25_11_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800226F0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, 0xFFFFFFFB);
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
0x1800130e8  mov     [rsp+arg_10], rbx
0x1800130ed  mov     [rsp+arg_18], rbp
0x1800130f2  mov     [rsp+arg_0], rcx
0x1800130f7  push    rsi
0x1800130f8  push    rdi
0x1800130f9  push    r14
0x1800130fb  sub     rsp, 30h
0x1800130ff  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x180013106  mov     rdi, rdx
0x180013109  mov     qword ptr [rdx], 0
0x180013110  mov     eax, [rsi]
0x180013112  mov     [rdx], eax
0x180013114  and     eax, 6
0x180013117  cmp     al, 6
0x180013119  jz      loc_18001320B
0x18001311f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013124  lea     r8, [rsp+48h+arg_0]
0x180013129  mov     dword ptr [rsp+48h+arg_0], 0
0x180013131  lea     rdx, [rsp+48h+arg_8]
0x180013136  mov     ebp, eax
0x180013138  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(int *)
0x18001313d  mov     eax, [rdi]
0x18001313f  mov     rbx, [rsp+48h+arg_8]
0x180013144  cmp     dword ptr [rsp+48h+arg_0], 0
0x180013149  mov     edx, eax
0x18001314b  mov     [rdi], eax
0x18001314d  mov     ecx, eax
0x18001314f  jz      short loc_18001316A
0x180013151  test    dl, 2
0x180013154  jnz     short loc_18001316A
0x180013156  and     ecx, 0FFFFF63Eh
0x18001315c  mov     eax, ebx
0x18001315e  and     eax, 9C1h
0x180013163  or      ecx, eax
0x180013165  or      ecx, 2
0x180013168  mov     [rdi], ecx
0x18001316a  mov     r8d, edx
0x18001316d  and     r8d, 4
0x180013171  jnz     short loc_180013185
0x180013173  btr     ecx, 0Ah
0x180013177  mov     eax, ebx
0x180013179  and     eax, 400h
0x18001317e  or      ecx, eax
0x180013180  or      ecx, 4
0x180013183  mov     [rdi], ecx
0x180013185  mov     eax, edx
0x180013187  lock cmpxchg [rsi], ecx
0x18001318b  jnz     short loc_180013144
0x18001318d  test    r8d, r8d
0x180013190  jnz     short loc_1800131F6
0x180013192  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180013198  test    eax, eax
0x18001319a  jz      short loc_1800131F6
0x18001319c  lea     r14, SRWLock
0x1800131a3  mov     rcx, r14; SRWLock
0x1800131a6  call    cs:__imp_AcquireSRWLockExclusive
0x1800131ac  mov     eax, cs:dword_1800226CC
0x1800131b2  mov     [rsp+48h+arg_8], r14
0x1800131b7  test    ebp, ebp
0x1800131b9  jz      short loc_1800131E8
0x1800131bb  cmp     ebp, eax
0x1800131bd  jnz     short loc_1800131E8
0x1800131bf  mov     r8d, 10h; unsigned __int64
0x1800131c5  mov     [rsp+48h+var_28], 3
0x1800131ce  lea     rdx, [rsp+48h+var_28]; void *
0x1800131d3  mov     [rsp+48h+var_20], rsi
0x1800131d8  lea     rcx, qword_1800226F0; this
0x1800131df  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800131e4  test    al, al
0x1800131e6  jnz     short loc_1800131EC
0x1800131e8  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800131ec  lea     rcx, [rsp+48h+arg_8]
0x1800131f1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800131f6  mov     eax, [rdi]
0x1800131f8  test    al, 2
0x1800131fa  jnz     short loc_18001320B
0x1800131fc  and     eax, 0FFFFF63Eh
0x180013201  and     ebx, 9C1h
0x180013207  or      eax, ebx
0x180013209  mov     [rdi], eax
0x18001320b  mov     rbx, [rsp+48h+arg_10]
0x180013210  mov     rax, rdi
0x180013213  mov     rbp, [rsp+48h+arg_18]
0x180013218  add     rsp, 30h
0x18001321c  pop     r14
0x18001321e  pop     rdi
0x18001321f  pop     rsi
0x180013220  retn
```
