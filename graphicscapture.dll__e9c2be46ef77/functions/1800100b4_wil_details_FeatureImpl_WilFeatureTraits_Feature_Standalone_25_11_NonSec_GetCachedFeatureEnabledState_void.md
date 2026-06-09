# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1800100b4`
- end: `0x1800101ed`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011a10`

## callees

- `0x180007c28`
- `0x180008684`
- `0x18000c930`
- `0x1800100b4`
- `0x1800106fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010172`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010172`

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
      AcquireSRWLockExclusive(&stru_180035B78);
      v16 = &stru_180035B78;
      if ( !v5
        || v5 != dword_180035B8C
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_25_11_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180035BB0, v14, 0x10u)) )
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
0x1800100b4  mov     [rsp+arg_10], rbx
0x1800100b9  mov     [rsp+arg_18], rbp
0x1800100be  mov     [rsp+arg_0], rcx
0x1800100c3  push    rsi
0x1800100c4  push    rdi
0x1800100c5  push    r14
0x1800100c7  sub     rsp, 30h
0x1800100cb  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x1800100d2  mov     rdi, rdx
0x1800100d5  mov     qword ptr [rdx], 0
0x1800100dc  mov     eax, [rsi]
0x1800100de  mov     [rdx], eax
0x1800100e0  and     eax, 6
0x1800100e3  cmp     al, 6
0x1800100e5  jz      loc_1800101D7
0x1800100eb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800100f0  lea     r8, [rsp+48h+arg_0]
0x1800100f5  mov     dword ptr [rsp+48h+arg_0], 0
0x1800100fd  lea     rdx, [rsp+48h+arg_8]
0x180010102  mov     ebp, eax
0x180010104  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(int *)
0x180010109  mov     eax, [rdi]
0x18001010b  mov     rbx, [rsp+48h+arg_8]
0x180010110  cmp     dword ptr [rsp+48h+arg_0], 0
0x180010115  mov     edx, eax
0x180010117  mov     [rdi], eax
0x180010119  mov     ecx, eax
0x18001011b  jz      short loc_180010136
0x18001011d  test    dl, 2
0x180010120  jnz     short loc_180010136
0x180010122  and     ecx, 0FFFFF63Eh
0x180010128  mov     eax, ebx
0x18001012a  and     eax, 9C1h
0x18001012f  or      ecx, eax
0x180010131  or      ecx, 2
0x180010134  mov     [rdi], ecx
0x180010136  mov     r8d, edx
0x180010139  and     r8d, 4
0x18001013d  jnz     short loc_180010151
0x18001013f  btr     ecx, 0Ah
0x180010143  mov     eax, ebx
0x180010145  and     eax, 400h
0x18001014a  or      ecx, eax
0x18001014c  or      ecx, 4
0x18001014f  mov     [rdi], ecx
0x180010151  mov     eax, edx
0x180010153  lock cmpxchg [rsi], ecx
0x180010157  jnz     short loc_180010110
0x180010159  test    r8d, r8d
0x18001015c  jnz     short loc_1800101C2
0x18001015e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180010164  test    eax, eax
0x180010166  jz      short loc_1800101C2
0x180010168  lea     r14, stru_180035B78
0x18001016f  mov     rcx, r14; SRWLock
0x180010172  call    cs:__imp_AcquireSRWLockExclusive
0x180010178  mov     eax, cs:dword_180035B8C
0x18001017e  mov     [rsp+48h+arg_8], r14
0x180010183  test    ebp, ebp
0x180010185  jz      short loc_1800101B4
0x180010187  cmp     ebp, eax
0x180010189  jnz     short loc_1800101B4
0x18001018b  mov     r8d, 10h; unsigned __int64
0x180010191  mov     [rsp+48h+var_28], 3
0x18001019a  lea     rdx, [rsp+48h+var_28]; void *
0x18001019f  mov     [rsp+48h+var_20], rsi
0x1800101a4  lea     rcx, qword_180035BB0; this
0x1800101ab  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800101b0  test    al, al
0x1800101b2  jnz     short loc_1800101B8
0x1800101b4  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800101b8  lea     rcx, [rsp+48h+arg_8]
0x1800101bd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800101c2  mov     eax, [rdi]
0x1800101c4  test    al, 2
0x1800101c6  jnz     short loc_1800101D7
0x1800101c8  and     eax, 0FFFFF63Eh
0x1800101cd  and     ebx, 9C1h
0x1800101d3  or      eax, ebx
0x1800101d5  mov     [rdi], eax
0x1800101d7  mov     rbx, [rsp+48h+arg_10]
0x1800101dc  mov     rax, rdi
0x1800101df  mov     rbp, [rsp+48h+arg_18]
0x1800101e4  add     rsp, 30h
0x1800101e8  pop     r14
0x1800101ea  pop     rdi
0x1800101eb  pop     rsi
0x1800101ec  retn
```
