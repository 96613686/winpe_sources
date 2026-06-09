# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x1800135e8`
- end: `0x180013721`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001500c`
- `0x180015a20`

## callees

- `0x18000f11c`
- `0x180012c54`
- `0x1800135e8`
- `0x18001406c`
- `0x180015b2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800136a6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800136a6`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Ten2Loc__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800226CC
        || (v14[0] = 3,
            v14[1] = Feature_Ten2Loc__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800226F0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Ten2Loc__descriptor, 0xFFFFFFFB);
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
0x1800135e8  mov     [rsp+arg_10], rbx
0x1800135ed  mov     [rsp+arg_18], rbp
0x1800135f2  mov     [rsp+arg_0], rcx
0x1800135f7  push    rsi
0x1800135f8  push    rdi
0x1800135f9  push    r14
0x1800135fb  sub     rsp, 30h
0x1800135ff  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x180013606  mov     rdi, rdx
0x180013609  mov     qword ptr [rdx], 0
0x180013610  mov     eax, [rsi]
0x180013612  mov     [rdx], eax
0x180013614  and     eax, 6
0x180013617  cmp     al, 6
0x180013619  jz      loc_18001370B
0x18001361f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013624  lea     r8, [rsp+48h+arg_0]
0x180013629  mov     dword ptr [rsp+48h+arg_0], 0
0x180013631  lea     rdx, [rsp+48h+arg_8]
0x180013636  mov     ebp, eax
0x180013638  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x18001363d  mov     eax, [rdi]
0x18001363f  mov     rbx, [rsp+48h+arg_8]
0x180013644  cmp     dword ptr [rsp+48h+arg_0], 0
0x180013649  mov     edx, eax
0x18001364b  mov     [rdi], eax
0x18001364d  mov     ecx, eax
0x18001364f  jz      short loc_18001366A
0x180013651  test    dl, 2
0x180013654  jnz     short loc_18001366A
0x180013656  and     ecx, 0FFFFF63Eh
0x18001365c  mov     eax, ebx
0x18001365e  and     eax, 9C1h
0x180013663  or      ecx, eax
0x180013665  or      ecx, 2
0x180013668  mov     [rdi], ecx
0x18001366a  mov     r8d, edx
0x18001366d  and     r8d, 4
0x180013671  jnz     short loc_180013685
0x180013673  btr     ecx, 0Ah
0x180013677  mov     eax, ebx
0x180013679  and     eax, 400h
0x18001367e  or      ecx, eax
0x180013680  or      ecx, 4
0x180013683  mov     [rdi], ecx
0x180013685  mov     eax, edx
0x180013687  lock cmpxchg [rsi], ecx
0x18001368b  jnz     short loc_180013644
0x18001368d  test    r8d, r8d
0x180013690  jnz     short loc_1800136F6
0x180013692  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180013698  test    eax, eax
0x18001369a  jz      short loc_1800136F6
0x18001369c  lea     r14, SRWLock
0x1800136a3  mov     rcx, r14; SRWLock
0x1800136a6  call    cs:__imp_AcquireSRWLockExclusive
0x1800136ac  mov     eax, cs:dword_1800226CC
0x1800136b2  mov     [rsp+48h+arg_8], r14
0x1800136b7  test    ebp, ebp
0x1800136b9  jz      short loc_1800136E8
0x1800136bb  cmp     ebp, eax
0x1800136bd  jnz     short loc_1800136E8
0x1800136bf  mov     r8d, 10h; unsigned __int64
0x1800136c5  mov     [rsp+48h+var_28], 3
0x1800136ce  lea     rdx, [rsp+48h+var_28]; void *
0x1800136d3  mov     [rsp+48h+var_20], rsi
0x1800136d8  lea     rcx, qword_1800226F0; this
0x1800136df  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800136e4  test    al, al
0x1800136e6  jnz     short loc_1800136EC
0x1800136e8  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800136ec  lea     rcx, [rsp+48h+arg_8]
0x1800136f1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800136f6  mov     eax, [rdi]
0x1800136f8  test    al, 2
0x1800136fa  jnz     short loc_18001370B
0x1800136fc  and     eax, 0FFFFF63Eh
0x180013701  and     ebx, 9C1h
0x180013707  or      eax, ebx
0x180013709  mov     [rdi], eax
0x18001370b  mov     rbx, [rsp+48h+arg_10]
0x180013710  mov     rax, rdi
0x180013713  mov     rbp, [rsp+48h+arg_18]
0x180013718  add     rsp, 30h
0x18001371c  pop     r14
0x18001371e  pop     rdi
0x18001371f  pop     rsi
0x180013720  retn
```
