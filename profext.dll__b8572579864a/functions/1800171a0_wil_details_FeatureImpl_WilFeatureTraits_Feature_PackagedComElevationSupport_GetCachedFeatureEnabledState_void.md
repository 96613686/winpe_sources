# wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetCachedFeatureEnabledState(void)

- ea: `0x1800171a0`
- end: `0x1800172e0`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a4a4`
- `0x18001ba34`

## callees

- `0x180013750`
- `0x180016c90`
- `0x1800171a0`
- `0x180018100`
- `0x18001c040`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001725e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001725e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_PackagedComElevationSupport__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_PackagedComElevationSupport__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_PackagedComElevationSupport__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800316D4
        || (v14[0] = 3,
            v14[1] = Feature_PackagedComElevationSupport__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180031708, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_PackagedComElevationSupport__descriptor, 0xFFFFFFFB);
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
0x1800171a0  mov     [rsp+arg_10], rbx
0x1800171a5  mov     [rsp+arg_18], rbp
0x1800171aa  mov     [rsp+arg_0], rcx
0x1800171af  push    rsi
0x1800171b0  push    rdi
0x1800171b1  push    r14
0x1800171b3  sub     rsp, 30h
0x1800171b7  mov     rsi, cs:Feature_PackagedComElevationSupport__descriptor
0x1800171be  mov     rdi, rdx
0x1800171c1  mov     qword ptr [rdx], 0
0x1800171c8  mov     eax, [rsi]
0x1800171ca  mov     [rdx], eax
0x1800171cc  and     eax, 6
0x1800171cf  cmp     al, 6
0x1800171d1  jz      loc_1800172C9
0x1800171d7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800171dc  lea     r8, [rsp+48h+arg_0]
0x1800171e1  mov     dword ptr [rsp+48h+arg_0], 0
0x1800171e9  lea     rdx, [rsp+48h+arg_8]
0x1800171ee  mov     ebp, eax
0x1800171f0  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetCurrentFeatureEnabledState(int *)
0x1800171f5  mov     eax, [rdi]
0x1800171f7  mov     rbx, [rsp+48h+arg_8]
0x1800171fc  cmp     dword ptr [rsp+48h+arg_0], 0
0x180017201  mov     edx, eax
0x180017203  mov     [rdi], eax
0x180017205  mov     ecx, eax
0x180017207  jz      short loc_180017222
0x180017209  test    dl, 2
0x18001720c  jnz     short loc_180017222
0x18001720e  and     ecx, 0FFFFF63Eh
0x180017214  mov     eax, ebx
0x180017216  and     eax, 9C1h
0x18001721b  or      ecx, eax
0x18001721d  or      ecx, 2
0x180017220  mov     [rdi], ecx
0x180017222  mov     r8d, edx
0x180017225  and     r8d, 4
0x180017229  jnz     short loc_18001723D
0x18001722b  btr     ecx, 0Ah
0x18001722f  mov     eax, ebx
0x180017231  and     eax, 400h
0x180017236  or      ecx, eax
0x180017238  or      ecx, 4
0x18001723b  mov     [rdi], ecx
0x18001723d  mov     eax, edx
0x18001723f  lock cmpxchg [rsi], ecx
0x180017243  jnz     short loc_1800171FC
0x180017245  test    r8d, r8d
0x180017248  jnz     short loc_1800172B4
0x18001724a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180017250  test    eax, eax
0x180017252  jz      short loc_1800172B4
0x180017254  lea     r14, SRWLock
0x18001725b  mov     rcx, r14; SRWLock
0x18001725e  call    cs:__imp_AcquireSRWLockExclusive
0x180017265  nop     dword ptr [rax+rax+00h]
0x18001726a  mov     eax, cs:dword_1800316D4
0x180017270  mov     [rsp+48h+arg_8], r14
0x180017275  test    ebp, ebp
0x180017277  jz      short loc_1800172A6
0x180017279  cmp     ebp, eax
0x18001727b  jnz     short loc_1800172A6
0x18001727d  mov     r8d, 10h; unsigned __int64
0x180017283  mov     [rsp+48h+var_28], 3
0x18001728c  lea     rdx, [rsp+48h+var_28]; void *
0x180017291  mov     [rsp+48h+var_20], rsi
0x180017296  lea     rcx, qword_180031708; this
0x18001729d  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800172a2  test    al, al
0x1800172a4  jnz     short loc_1800172AA
0x1800172a6  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800172aa  lea     rcx, [rsp+48h+arg_8]
0x1800172af  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800172b4  mov     eax, [rdi]
0x1800172b6  test    al, 2
0x1800172b8  jnz     short loc_1800172C9
0x1800172ba  and     eax, 0FFFFF63Eh
0x1800172bf  and     ebx, 9C1h
0x1800172c5  or      eax, ebx
0x1800172c7  mov     [rdi], eax
0x1800172c9  mov     rbx, [rsp+48h+arg_10]
0x1800172ce  mov     rax, rdi
0x1800172d1  mov     rbp, [rsp+48h+arg_18]
0x1800172d6  add     rsp, 30h
0x1800172da  pop     r14
0x1800172dc  pop     rdi
0x1800172dd  pop     rsi
0x1800172de  retn
```
