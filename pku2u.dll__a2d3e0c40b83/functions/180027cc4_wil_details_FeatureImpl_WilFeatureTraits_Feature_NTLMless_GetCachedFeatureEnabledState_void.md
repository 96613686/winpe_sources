# wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless>::GetCachedFeatureEnabledState(void)

- ea: `0x180027cc4`
- end: `0x180027dfd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_NTLMless@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800299e0`
- `0x18002ad74`

## callees

- `0x18001f7b4`
- `0x1800279d4`
- `0x180027cc4`
- `0x180027f44`
- `0x18002ae1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027d82`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027d82`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_NTLMless__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_NTLMless__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_NTLMless__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800548E4
        || (v14[0] = 3,
            v14[1] = Feature_NTLMless__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180054908, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_NTLMless__descriptor, 0xFFFFFFFB);
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
0x180027cc4  mov     [rsp+arg_10], rbx
0x180027cc9  mov     [rsp+arg_18], rbp
0x180027cce  mov     [rsp+arg_0], rcx
0x180027cd3  push    rsi
0x180027cd4  push    rdi
0x180027cd5  push    r14
0x180027cd7  sub     rsp, 30h
0x180027cdb  mov     rsi, cs:Feature_NTLMless__descriptor
0x180027ce2  mov     rdi, rdx
0x180027ce5  mov     qword ptr [rdx], 0
0x180027cec  mov     eax, [rsi]
0x180027cee  mov     [rdx], eax
0x180027cf0  and     eax, 6
0x180027cf3  cmp     al, 6
0x180027cf5  jz      loc_180027DE7
0x180027cfb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180027d00  lea     r8, [rsp+48h+arg_0]
0x180027d05  mov     dword ptr [rsp+48h+arg_0], 0
0x180027d0d  lea     rdx, [rsp+48h+arg_8]
0x180027d12  mov     ebp, eax
0x180027d14  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_NTLMless@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless>::GetCurrentFeatureEnabledState(int *)
0x180027d19  mov     eax, [rdi]
0x180027d1b  mov     rbx, [rsp+48h+arg_8]
0x180027d20  cmp     dword ptr [rsp+48h+arg_0], 0
0x180027d25  mov     edx, eax
0x180027d27  mov     [rdi], eax
0x180027d29  mov     ecx, eax
0x180027d2b  jz      short loc_180027D46
0x180027d2d  test    dl, 2
0x180027d30  jnz     short loc_180027D46
0x180027d32  and     ecx, 0FFFFF63Eh
0x180027d38  mov     eax, ebx
0x180027d3a  and     eax, 9C1h
0x180027d3f  or      ecx, eax
0x180027d41  or      ecx, 2
0x180027d44  mov     [rdi], ecx
0x180027d46  mov     r8d, edx
0x180027d49  and     r8d, 4
0x180027d4d  jnz     short loc_180027D61
0x180027d4f  btr     ecx, 0Ah
0x180027d53  mov     eax, ebx
0x180027d55  and     eax, 400h
0x180027d5a  or      ecx, eax
0x180027d5c  or      ecx, 4
0x180027d5f  mov     [rdi], ecx
0x180027d61  mov     eax, edx
0x180027d63  lock cmpxchg [rsi], ecx
0x180027d67  jnz     short loc_180027D20
0x180027d69  test    r8d, r8d
0x180027d6c  jnz     short loc_180027DD2
0x180027d6e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180027d74  test    eax, eax
0x180027d76  jz      short loc_180027DD2
0x180027d78  lea     r14, SRWLock
0x180027d7f  mov     rcx, r14; SRWLock
0x180027d82  call    cs:__imp_AcquireSRWLockExclusive
0x180027d88  mov     eax, cs:dword_1800548E4
0x180027d8e  mov     [rsp+48h+arg_8], r14
0x180027d93  test    ebp, ebp
0x180027d95  jz      short loc_180027DC4
0x180027d97  cmp     ebp, eax
0x180027d99  jnz     short loc_180027DC4
0x180027d9b  mov     r8d, 10h; unsigned __int64
0x180027da1  mov     [rsp+48h+var_28], 3
0x180027daa  lea     rdx, [rsp+48h+var_28]; void *
0x180027daf  mov     [rsp+48h+var_20], rsi
0x180027db4  lea     rcx, qword_180054908; this
0x180027dbb  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180027dc0  test    al, al
0x180027dc2  jnz     short loc_180027DC8
0x180027dc4  lock and dword ptr [rsi], 0FFFFFFFBh
0x180027dc8  lea     rcx, [rsp+48h+arg_8]
0x180027dcd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180027dd2  mov     eax, [rdi]
0x180027dd4  test    al, 2
0x180027dd6  jnz     short loc_180027DE7
0x180027dd8  and     eax, 0FFFFF63Eh
0x180027ddd  and     ebx, 9C1h
0x180027de3  or      eax, ebx
0x180027de5  mov     [rdi], eax
0x180027de7  mov     rbx, [rsp+48h+arg_10]
0x180027dec  mov     rax, rdi
0x180027def  mov     rbp, [rsp+48h+arg_18]
0x180027df4  add     rsp, 30h
0x180027df8  pop     r14
0x180027dfa  pop     rdi
0x180027dfb  pop     rsi
0x180027dfc  retn
```
