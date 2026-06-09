# wil::details::FeatureImpl<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::GetCachedFeatureEnabledState(void)

- ea: `0x140010730`
- end: `0x14001086d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_OSK_SecureOnLockScreen@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012db0`

## callees

- `0x1400050dc`
- `0x140006020`
- `0x14000c520`
- `0x140010730`
- `0x140010874`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1400107f4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400107f4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // r14d
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  int v12; // r8d
  _QWORD v14[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details *v15; // [rsp+60h] [rbp+30h] BYREF
  RTL_SRWLOCK *v16; // [rsp+68h] [rbp+38h] BYREF

  v15 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_OSK_SecureOnLockScreen__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_OSK_SecureOnLockScreen__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::GetCurrentFeatureEnabledState(
      v6,
      &v16,
      &v15);
    if ( !v5 )
      LODWORD(v15) = 0;
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_OSK_SecureOnLockScreen__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_140036C30);
      v16 = &stru_140036C30;
      if ( !v5
        || v5 != dword_140036C44
        || (v14[0] = 0,
            v14[1] = Feature_OSK_SecureOnLockScreen__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_140036C68, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_OSK_SecureOnLockScreen__descriptor, 0xFFFFF7C1);
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
0x140010730  mov     [rsp-28h+arg_10], rbx
0x140010735  mov     [rsp-28h+arg_0], rcx
0x14001073a  push    rbp
0x14001073b  push    rsi
0x14001073c  push    rdi
0x14001073d  push    r14
0x14001073f  push    r15
0x140010741  mov     rbp, rsp
0x140010744  sub     rsp, 30h
0x140010748  mov     rsi, cs:Feature_OSK_SecureOnLockScreen__descriptor
0x14001074f  mov     rdi, rdx
0x140010752  mov     qword ptr [rdx], 0
0x140010759  mov     eax, [rsi]
0x14001075b  mov     [rdx], eax
0x14001075d  and     eax, 6
0x140010760  cmp     al, 6
0x140010762  jz      loc_140010859
0x140010768  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14001076d  lea     r8, [rbp+arg_0]
0x140010771  mov     dword ptr [rbp+arg_0], 0
0x140010778  lea     rdx, [rbp+arg_8]
0x14001077c  mov     r14d, eax
0x14001077f  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_OSK_SecureOnLockScreen@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::GetCurrentFeatureEnabledState(int *)
0x140010784  test    r14d, r14d
0x140010787  jnz     short loc_14001078D
0x140010789  mov     dword ptr [rbp+arg_0], r14d
0x14001078d  mov     eax, [rdi]
0x14001078f  mov     rbx, [rbp+arg_8]
0x140010793  cmp     dword ptr [rbp+arg_0], 0
0x140010797  mov     edx, eax
0x140010799  mov     [rdi], eax
0x14001079b  mov     ecx, eax
0x14001079d  jz      short loc_1400107B8
0x14001079f  test    dl, 2
0x1400107a2  jnz     short loc_1400107B8
0x1400107a4  and     ecx, 0FFFFF63Eh
0x1400107aa  mov     eax, ebx
0x1400107ac  and     eax, 9C1h
0x1400107b1  or      ecx, eax
0x1400107b3  or      ecx, 2
0x1400107b6  mov     [rdi], ecx
0x1400107b8  mov     r8d, edx
0x1400107bb  and     r8d, 4
0x1400107bf  jnz     short loc_1400107D3
0x1400107c1  btr     ecx, 0Ah
0x1400107c5  mov     eax, ebx
0x1400107c7  and     eax, 400h
0x1400107cc  or      ecx, eax
0x1400107ce  or      ecx, 4
0x1400107d1  mov     [rdi], ecx
0x1400107d3  mov     eax, edx
0x1400107d5  lock cmpxchg [rsi], ecx
0x1400107d9  jnz     short loc_140010793
0x1400107db  test    r8d, r8d
0x1400107de  jnz     short loc_140010844
0x1400107e0  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1400107e6  test    eax, eax
0x1400107e8  jz      short loc_140010844
0x1400107ea  lea     r15, stru_140036C30
0x1400107f1  mov     rcx, r15; SRWLock
0x1400107f4  call    cs:__imp_AcquireSRWLockExclusive
0x1400107fa  mov     eax, cs:dword_140036C44
0x140010800  mov     [rbp+arg_8], r15
0x140010804  test    r14d, r14d
0x140010807  jz      short loc_140010834
0x140010809  cmp     r14d, eax
0x14001080c  jnz     short loc_140010834
0x14001080e  mov     r8d, 10h; unsigned __int64
0x140010814  mov     [rbp+var_10], 0
0x14001081c  lea     rdx, [rbp+var_10]; void *
0x140010820  mov     [rbp+var_8], rsi
0x140010824  lea     rcx, qword_140036C68; this
0x14001082b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140010830  test    al, al
0x140010832  jnz     short loc_14001083B
0x140010834  lock and dword ptr [rsi], 0FFFFF7C1h
0x14001083b  lea     rcx, [rbp+arg_8]
0x14001083f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140010844  mov     eax, [rdi]
0x140010846  test    al, 2
0x140010848  jnz     short loc_140010859
0x14001084a  and     eax, 0FFFFF63Eh
0x14001084f  and     ebx, 9C1h
0x140010855  or      eax, ebx
0x140010857  mov     [rdi], eax
0x140010859  mov     rbx, [rsp+30h+arg_10]
0x14001085e  mov     rax, rdi
0x140010861  add     rsp, 30h
0x140010865  pop     r15
0x140010867  pop     r14
0x140010869  pop     rdi
0x14001086a  pop     rsi
0x14001086b  pop     rbp
0x14001086c  retn
```
