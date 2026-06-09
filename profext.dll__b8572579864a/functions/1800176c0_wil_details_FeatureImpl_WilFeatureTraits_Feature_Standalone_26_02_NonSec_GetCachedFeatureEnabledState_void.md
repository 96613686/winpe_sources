# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1800176c0`
- end: `0x180017800`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018418`

## callees

- `0x180013750`
- `0x180016c90`
- `0x1800176c0`
- `0x180018328`
- `0x18001c040`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001777e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001777e`

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
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800316D4
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_26_02_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180031708, v14, 0x10u)) )
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
0x1800176c0  mov     [rsp+arg_10], rbx
0x1800176c5  mov     [rsp+arg_18], rbp
0x1800176ca  mov     [rsp+arg_0], rcx
0x1800176cf  push    rsi
0x1800176d0  push    rdi
0x1800176d1  push    r14
0x1800176d3  sub     rsp, 30h
0x1800176d7  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x1800176de  mov     rdi, rdx
0x1800176e1  mov     qword ptr [rdx], 0
0x1800176e8  mov     eax, [rsi]
0x1800176ea  mov     [rdx], eax
0x1800176ec  and     eax, 6
0x1800176ef  cmp     al, 6
0x1800176f1  jz      loc_1800177E9
0x1800176f7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800176fc  lea     r8, [rsp+48h+arg_0]
0x180017701  mov     dword ptr [rsp+48h+arg_0], 0
0x180017709  lea     rdx, [rsp+48h+arg_8]
0x18001770e  mov     ebp, eax
0x180017710  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCurrentFeatureEnabledState(int *)
0x180017715  mov     eax, [rdi]
0x180017717  mov     rbx, [rsp+48h+arg_8]
0x18001771c  cmp     dword ptr [rsp+48h+arg_0], 0
0x180017721  mov     edx, eax
0x180017723  mov     [rdi], eax
0x180017725  mov     ecx, eax
0x180017727  jz      short loc_180017742
0x180017729  test    dl, 2
0x18001772c  jnz     short loc_180017742
0x18001772e  and     ecx, 0FFFFF63Eh
0x180017734  mov     eax, ebx
0x180017736  and     eax, 9C1h
0x18001773b  or      ecx, eax
0x18001773d  or      ecx, 2
0x180017740  mov     [rdi], ecx
0x180017742  mov     r8d, edx
0x180017745  and     r8d, 4
0x180017749  jnz     short loc_18001775D
0x18001774b  btr     ecx, 0Ah
0x18001774f  mov     eax, ebx
0x180017751  and     eax, 400h
0x180017756  or      ecx, eax
0x180017758  or      ecx, 4
0x18001775b  mov     [rdi], ecx
0x18001775d  mov     eax, edx
0x18001775f  lock cmpxchg [rsi], ecx
0x180017763  jnz     short loc_18001771C
0x180017765  test    r8d, r8d
0x180017768  jnz     short loc_1800177D4
0x18001776a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180017770  test    eax, eax
0x180017772  jz      short loc_1800177D4
0x180017774  lea     r14, SRWLock
0x18001777b  mov     rcx, r14; SRWLock
0x18001777e  call    cs:__imp_AcquireSRWLockExclusive
0x180017785  nop     dword ptr [rax+rax+00h]
0x18001778a  mov     eax, cs:dword_1800316D4
0x180017790  mov     [rsp+48h+arg_8], r14
0x180017795  test    ebp, ebp
0x180017797  jz      short loc_1800177C6
0x180017799  cmp     ebp, eax
0x18001779b  jnz     short loc_1800177C6
0x18001779d  mov     r8d, 10h; unsigned __int64
0x1800177a3  mov     [rsp+48h+var_28], 3
0x1800177ac  lea     rdx, [rsp+48h+var_28]; void *
0x1800177b1  mov     [rsp+48h+var_20], rsi
0x1800177b6  lea     rcx, qword_180031708; this
0x1800177bd  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800177c2  test    al, al
0x1800177c4  jnz     short loc_1800177CA
0x1800177c6  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800177ca  lea     rcx, [rsp+48h+arg_8]
0x1800177cf  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800177d4  mov     eax, [rdi]
0x1800177d6  test    al, 2
0x1800177d8  jnz     short loc_1800177E9
0x1800177da  and     eax, 0FFFFF63Eh
0x1800177df  and     ebx, 9C1h
0x1800177e5  or      eax, ebx
0x1800177e7  mov     [rdi], eax
0x1800177e9  mov     rbx, [rsp+48h+arg_10]
0x1800177ee  mov     rax, rdi
0x1800177f1  mov     rbp, [rsp+48h+arg_18]
0x1800177f6  add     rsp, 30h
0x1800177fa  pop     r14
0x1800177fc  pop     rdi
0x1800177fd  pop     rsi
0x1800177fe  retn
```
