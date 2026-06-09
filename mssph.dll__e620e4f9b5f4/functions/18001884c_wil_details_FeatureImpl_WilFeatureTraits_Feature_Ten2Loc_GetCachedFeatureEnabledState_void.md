# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x18001884c`
- end: `0x180018985`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b55c`
- `0x18001c178`

## callees

- `0x18000d118`
- `0x180012908`
- `0x180015b28`
- `0x18001884c`
- `0x180019394`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001890a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001890a`

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
      AcquireSRWLockExclusive(&stru_1800367E8);
      v16 = &stru_1800367E8;
      if ( !v5
        || v5 != dword_1800367FC
        || (v14[0] = 3,
            v14[1] = Feature_Ten2Loc__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180036820, v14, 0x10u)) )
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
0x18001884c  mov     [rsp+arg_10], rbx
0x180018851  mov     [rsp+arg_18], rbp
0x180018856  mov     [rsp+arg_0], rcx
0x18001885b  push    rsi
0x18001885c  push    rdi
0x18001885d  push    r14
0x18001885f  sub     rsp, 30h
0x180018863  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x18001886a  mov     rdi, rdx
0x18001886d  mov     qword ptr [rdx], 0
0x180018874  mov     eax, [rsi]
0x180018876  mov     [rdx], eax
0x180018878  and     eax, 6
0x18001887b  cmp     al, 6
0x18001887d  jz      loc_18001896F
0x180018883  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180018888  lea     r8, [rsp+48h+arg_0]
0x18001888d  mov     dword ptr [rsp+48h+arg_0], 0
0x180018895  lea     rdx, [rsp+48h+arg_8]
0x18001889a  mov     ebp, eax
0x18001889c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x1800188a1  mov     eax, [rdi]
0x1800188a3  mov     rbx, [rsp+48h+arg_8]
0x1800188a8  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800188ad  mov     edx, eax
0x1800188af  mov     [rdi], eax
0x1800188b1  mov     ecx, eax
0x1800188b3  jz      short loc_1800188CE
0x1800188b5  test    dl, 2
0x1800188b8  jnz     short loc_1800188CE
0x1800188ba  and     ecx, 0FFFFF63Eh
0x1800188c0  mov     eax, ebx
0x1800188c2  and     eax, 9C1h
0x1800188c7  or      ecx, eax
0x1800188c9  or      ecx, 2
0x1800188cc  mov     [rdi], ecx
0x1800188ce  mov     r8d, edx
0x1800188d1  and     r8d, 4
0x1800188d5  jnz     short loc_1800188E9
0x1800188d7  btr     ecx, 0Ah
0x1800188db  mov     eax, ebx
0x1800188dd  and     eax, 400h
0x1800188e2  or      ecx, eax
0x1800188e4  or      ecx, 4
0x1800188e7  mov     [rdi], ecx
0x1800188e9  mov     eax, edx
0x1800188eb  lock cmpxchg [rsi], ecx
0x1800188ef  jnz     short loc_1800188A8
0x1800188f1  test    r8d, r8d
0x1800188f4  jnz     short loc_18001895A
0x1800188f6  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800188fc  test    eax, eax
0x1800188fe  jz      short loc_18001895A
0x180018900  lea     r14, stru_1800367E8
0x180018907  mov     rcx, r14; SRWLock
0x18001890a  call    cs:__imp_AcquireSRWLockExclusive
0x180018910  mov     eax, cs:dword_1800367FC
0x180018916  mov     [rsp+48h+arg_8], r14
0x18001891b  test    ebp, ebp
0x18001891d  jz      short loc_18001894C
0x18001891f  cmp     ebp, eax
0x180018921  jnz     short loc_18001894C
0x180018923  mov     r8d, 10h; unsigned __int64
0x180018929  mov     [rsp+48h+var_28], 3
0x180018932  lea     rdx, [rsp+48h+var_28]; void *
0x180018937  mov     [rsp+48h+var_20], rsi
0x18001893c  lea     rcx, qword_180036820; this
0x180018943  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180018948  test    al, al
0x18001894a  jnz     short loc_180018950
0x18001894c  lock and dword ptr [rsi], 0FFFFFFFBh
0x180018950  lea     rcx, [rsp+48h+arg_8]
0x180018955  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001895a  mov     eax, [rdi]
0x18001895c  test    al, 2
0x18001895e  jnz     short loc_18001896F
0x180018960  and     eax, 0FFFFF63Eh
0x180018965  and     ebx, 9C1h
0x18001896b  or      eax, ebx
0x18001896d  mov     [rdi], eax
0x18001896f  mov     rbx, [rsp+48h+arg_10]
0x180018974  mov     rax, rdi
0x180018977  mov     rbp, [rsp+48h+arg_18]
0x18001897c  add     rsp, 30h
0x180018980  pop     r14
0x180018982  pop     rdi
0x180018983  pop     rsi
0x180018984  retn
```
