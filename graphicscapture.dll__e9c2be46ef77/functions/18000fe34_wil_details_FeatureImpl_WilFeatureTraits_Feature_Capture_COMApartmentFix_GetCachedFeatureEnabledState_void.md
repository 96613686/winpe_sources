# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_COMApartmentFix>::GetCachedFeatureEnabledState(void)

- ea: `0x18000fe34`
- end: `0x18000ff6d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_COMApartmentFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011900`
- `0x180012340`

## callees

- `0x180007c28`
- `0x180008684`
- `0x18000c930`
- `0x18000fe34`
- `0x1800105b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fef2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fef2`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_COMApartmentFix>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Capture_COMApartmentFix__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Capture_COMApartmentFix__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_COMApartmentFix>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Capture_COMApartmentFix__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180035B78);
      v16 = &stru_180035B78;
      if ( !v5
        || v5 != dword_180035B8C
        || (v14[0] = 3,
            v14[1] = Feature_Capture_COMApartmentFix__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180035BB0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Capture_COMApartmentFix__descriptor, 0xFFFFFFFB);
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
0x18000fe34  mov     [rsp+arg_10], rbx
0x18000fe39  mov     [rsp+arg_18], rbp
0x18000fe3e  mov     [rsp+arg_0], rcx
0x18000fe43  push    rsi
0x18000fe44  push    rdi
0x18000fe45  push    r14
0x18000fe47  sub     rsp, 30h
0x18000fe4b  mov     rsi, cs:Feature_Capture_COMApartmentFix__descriptor
0x18000fe52  mov     rdi, rdx
0x18000fe55  mov     qword ptr [rdx], 0
0x18000fe5c  mov     eax, [rsi]
0x18000fe5e  mov     [rdx], eax
0x18000fe60  and     eax, 6
0x18000fe63  cmp     al, 6
0x18000fe65  jz      loc_18000FF57
0x18000fe6b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000fe70  lea     r8, [rsp+48h+arg_0]
0x18000fe75  mov     dword ptr [rsp+48h+arg_0], 0
0x18000fe7d  lea     rdx, [rsp+48h+arg_8]
0x18000fe82  mov     ebp, eax
0x18000fe84  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_COMApartmentFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_COMApartmentFix>::GetCurrentFeatureEnabledState(int *)
0x18000fe89  mov     eax, [rdi]
0x18000fe8b  mov     rbx, [rsp+48h+arg_8]
0x18000fe90  cmp     dword ptr [rsp+48h+arg_0], 0
0x18000fe95  mov     edx, eax
0x18000fe97  mov     [rdi], eax
0x18000fe99  mov     ecx, eax
0x18000fe9b  jz      short loc_18000FEB6
0x18000fe9d  test    dl, 2
0x18000fea0  jnz     short loc_18000FEB6
0x18000fea2  and     ecx, 0FFFFF63Eh
0x18000fea8  mov     eax, ebx
0x18000feaa  and     eax, 9C1h
0x18000feaf  or      ecx, eax
0x18000feb1  or      ecx, 2
0x18000feb4  mov     [rdi], ecx
0x18000feb6  mov     r8d, edx
0x18000feb9  and     r8d, 4
0x18000febd  jnz     short loc_18000FED1
0x18000febf  btr     ecx, 0Ah
0x18000fec3  mov     eax, ebx
0x18000fec5  and     eax, 400h
0x18000feca  or      ecx, eax
0x18000fecc  or      ecx, 4
0x18000fecf  mov     [rdi], ecx
0x18000fed1  mov     eax, edx
0x18000fed3  lock cmpxchg [rsi], ecx
0x18000fed7  jnz     short loc_18000FE90
0x18000fed9  test    r8d, r8d
0x18000fedc  jnz     short loc_18000FF42
0x18000fede  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000fee4  test    eax, eax
0x18000fee6  jz      short loc_18000FF42
0x18000fee8  lea     r14, stru_180035B78
0x18000feef  mov     rcx, r14; SRWLock
0x18000fef2  call    cs:__imp_AcquireSRWLockExclusive
0x18000fef8  mov     eax, cs:dword_180035B8C
0x18000fefe  mov     [rsp+48h+arg_8], r14
0x18000ff03  test    ebp, ebp
0x18000ff05  jz      short loc_18000FF34
0x18000ff07  cmp     ebp, eax
0x18000ff09  jnz     short loc_18000FF34
0x18000ff0b  mov     r8d, 10h; unsigned __int64
0x18000ff11  mov     [rsp+48h+var_28], 3
0x18000ff1a  lea     rdx, [rsp+48h+var_28]; void *
0x18000ff1f  mov     [rsp+48h+var_20], rsi
0x18000ff24  lea     rcx, qword_180035BB0; this
0x18000ff2b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000ff30  test    al, al
0x18000ff32  jnz     short loc_18000FF38
0x18000ff34  lock and dword ptr [rsi], 0FFFFFFFBh
0x18000ff38  lea     rcx, [rsp+48h+arg_8]
0x18000ff3d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000ff42  mov     eax, [rdi]
0x18000ff44  test    al, 2
0x18000ff46  jnz     short loc_18000FF57
0x18000ff48  and     eax, 0FFFFF63Eh
0x18000ff4d  and     ebx, 9C1h
0x18000ff53  or      eax, ebx
0x18000ff55  mov     [rdi], eax
0x18000ff57  mov     rbx, [rsp+48h+arg_10]
0x18000ff5c  mov     rax, rdi
0x18000ff5f  mov     rbp, [rsp+48h+arg_18]
0x18000ff64  add     rsp, 30h
0x18000ff68  pop     r14
0x18000ff6a  pop     rdi
0x18000ff6b  pop     rsi
0x18000ff6c  retn
```
