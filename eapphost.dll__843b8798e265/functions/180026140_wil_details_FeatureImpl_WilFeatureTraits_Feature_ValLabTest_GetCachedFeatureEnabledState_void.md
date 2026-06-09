# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180026140`
- end: `0x180026280`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029b3c`

## callees

- `0x18000ac08`
- `0x18000b8e0`
- `0x18000dba4`
- `0x180026140`
- `0x180026354`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800261fe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800261fe`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_18004E660);
      v16 = &stru_18004E660;
      if ( !v5
        || v5 != dword_18004E674
        || (v14[0] = 3,
            v14[1] = Feature_ValLabTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18004E6A8, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ValLabTest__descriptor, 0xFFFFFFFB);
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
0x180026140  mov     [rsp+arg_10], rbx
0x180026145  mov     [rsp+arg_18], rbp
0x18002614a  mov     [rsp+arg_0], rcx
0x18002614f  push    rsi
0x180026150  push    rdi
0x180026151  push    r14
0x180026153  sub     rsp, 30h
0x180026157  mov     rsi, cs:Feature_ValLabTest__descriptor
0x18002615e  mov     rdi, rdx
0x180026161  mov     qword ptr [rdx], 0
0x180026168  mov     eax, [rsi]
0x18002616a  mov     [rdx], eax
0x18002616c  and     eax, 6
0x18002616f  cmp     al, 6
0x180026171  jz      loc_180026269
0x180026177  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002617c  lea     r8, [rsp+48h+arg_0]
0x180026181  mov     dword ptr [rsp+48h+arg_0], 0
0x180026189  lea     rdx, [rsp+48h+arg_8]
0x18002618e  mov     ebp, eax
0x180026190  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)
0x180026195  mov     eax, [rdi]
0x180026197  mov     rbx, [rsp+48h+arg_8]
0x18002619c  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800261a1  mov     edx, eax
0x1800261a3  mov     [rdi], eax
0x1800261a5  mov     ecx, eax
0x1800261a7  jz      short loc_1800261C2
0x1800261a9  test    dl, 2
0x1800261ac  jnz     short loc_1800261C2
0x1800261ae  and     ecx, 0FFFFF63Eh
0x1800261b4  mov     eax, ebx
0x1800261b6  and     eax, 9C1h
0x1800261bb  or      ecx, eax
0x1800261bd  or      ecx, 2
0x1800261c0  mov     [rdi], ecx
0x1800261c2  mov     r8d, edx
0x1800261c5  and     r8d, 4
0x1800261c9  jnz     short loc_1800261DD
0x1800261cb  btr     ecx, 0Ah
0x1800261cf  mov     eax, ebx
0x1800261d1  and     eax, 400h
0x1800261d6  or      ecx, eax
0x1800261d8  or      ecx, 4
0x1800261db  mov     [rdi], ecx
0x1800261dd  mov     eax, edx
0x1800261df  lock cmpxchg [rsi], ecx
0x1800261e3  jnz     short loc_18002619C
0x1800261e5  test    r8d, r8d
0x1800261e8  jnz     short loc_180026254
0x1800261ea  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800261f0  test    eax, eax
0x1800261f2  jz      short loc_180026254
0x1800261f4  lea     r14, stru_18004E660
0x1800261fb  mov     rcx, r14; SRWLock
0x1800261fe  call    cs:__imp_AcquireSRWLockExclusive
0x180026205  nop     dword ptr [rax+rax+00h]
0x18002620a  mov     eax, cs:dword_18004E674
0x180026210  mov     [rsp+48h+arg_8], r14
0x180026215  test    ebp, ebp
0x180026217  jz      short loc_180026246
0x180026219  cmp     ebp, eax
0x18002621b  jnz     short loc_180026246
0x18002621d  mov     r8d, 10h; unsigned __int64
0x180026223  mov     [rsp+48h+var_28], 3
0x18002622c  lea     rdx, [rsp+48h+var_28]; void *
0x180026231  mov     [rsp+48h+var_20], rsi
0x180026236  lea     rcx, qword_18004E6A8; this
0x18002623d  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180026242  test    al, al
0x180026244  jnz     short loc_18002624A
0x180026246  lock and dword ptr [rsi], 0FFFFFFFBh
0x18002624a  lea     rcx, [rsp+48h+arg_8]
0x18002624f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180026254  mov     eax, [rdi]
0x180026256  test    al, 2
0x180026258  jnz     short loc_180026269
0x18002625a  and     eax, 0FFFFF63Eh
0x18002625f  and     ebx, 9C1h
0x180026265  or      eax, ebx
0x180026267  mov     [rdi], eax
0x180026269  mov     rbx, [rsp+48h+arg_10]
0x18002626e  mov     rax, rdi
0x180026271  mov     rbp, [rsp+48h+arg_18]
0x180026276  add     rsp, 30h
0x18002627a  pop     r14
0x18002627c  pop     rdi
0x18002627d  pop     rsi
0x18002627e  retn
```
