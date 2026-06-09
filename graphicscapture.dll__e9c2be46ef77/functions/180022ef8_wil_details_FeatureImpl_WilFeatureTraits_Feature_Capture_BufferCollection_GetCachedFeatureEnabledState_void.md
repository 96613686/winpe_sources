# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_BufferCollection>::GetCachedFeatureEnabledState(void)

- ea: `0x180022ef8`
- end: `0x180023031`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_BufferCollection@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800235f4`
- `0x1800240d0`

## callees

- `0x180007c28`
- `0x180008684`
- `0x18000c930`
- `0x180022ef8`
- `0x1800232bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022fb6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022fb6`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_BufferCollection>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Capture_BufferCollection__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Capture_BufferCollection__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_BufferCollection>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Capture_BufferCollection__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180035B78);
      v16 = &stru_180035B78;
      if ( !v5
        || v5 != dword_180035B8C
        || (v14[0] = 3,
            v14[1] = Feature_Capture_BufferCollection__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180035BB0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Capture_BufferCollection__descriptor, 0xFFFFFFFB);
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
0x180022ef8  mov     [rsp+arg_10], rbx
0x180022efd  mov     [rsp+arg_18], rbp
0x180022f02  mov     [rsp+arg_0], rcx
0x180022f07  push    rsi
0x180022f08  push    rdi
0x180022f09  push    r14
0x180022f0b  sub     rsp, 30h
0x180022f0f  mov     rsi, cs:Feature_Capture_BufferCollection__descriptor
0x180022f16  mov     rdi, rdx
0x180022f19  mov     qword ptr [rdx], 0
0x180022f20  mov     eax, [rsi]
0x180022f22  mov     [rdx], eax
0x180022f24  and     eax, 6
0x180022f27  cmp     al, 6
0x180022f29  jz      loc_18002301B
0x180022f2f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180022f34  lea     r8, [rsp+48h+arg_0]
0x180022f39  mov     dword ptr [rsp+48h+arg_0], 0
0x180022f41  lea     rdx, [rsp+48h+arg_8]
0x180022f46  mov     ebp, eax
0x180022f48  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_BufferCollection@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_BufferCollection>::GetCurrentFeatureEnabledState(int *)
0x180022f4d  mov     eax, [rdi]
0x180022f4f  mov     rbx, [rsp+48h+arg_8]
0x180022f54  cmp     dword ptr [rsp+48h+arg_0], 0
0x180022f59  mov     edx, eax
0x180022f5b  mov     [rdi], eax
0x180022f5d  mov     ecx, eax
0x180022f5f  jz      short loc_180022F7A
0x180022f61  test    dl, 2
0x180022f64  jnz     short loc_180022F7A
0x180022f66  and     ecx, 0FFFFF63Eh
0x180022f6c  mov     eax, ebx
0x180022f6e  and     eax, 9C1h
0x180022f73  or      ecx, eax
0x180022f75  or      ecx, 2
0x180022f78  mov     [rdi], ecx
0x180022f7a  mov     r8d, edx
0x180022f7d  and     r8d, 4
0x180022f81  jnz     short loc_180022F95
0x180022f83  btr     ecx, 0Ah
0x180022f87  mov     eax, ebx
0x180022f89  and     eax, 400h
0x180022f8e  or      ecx, eax
0x180022f90  or      ecx, 4
0x180022f93  mov     [rdi], ecx
0x180022f95  mov     eax, edx
0x180022f97  lock cmpxchg [rsi], ecx
0x180022f9b  jnz     short loc_180022F54
0x180022f9d  test    r8d, r8d
0x180022fa0  jnz     short loc_180023006
0x180022fa2  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180022fa8  test    eax, eax
0x180022faa  jz      short loc_180023006
0x180022fac  lea     r14, stru_180035B78
0x180022fb3  mov     rcx, r14; SRWLock
0x180022fb6  call    cs:__imp_AcquireSRWLockExclusive
0x180022fbc  mov     eax, cs:dword_180035B8C
0x180022fc2  mov     [rsp+48h+arg_8], r14
0x180022fc7  test    ebp, ebp
0x180022fc9  jz      short loc_180022FF8
0x180022fcb  cmp     ebp, eax
0x180022fcd  jnz     short loc_180022FF8
0x180022fcf  mov     r8d, 10h; unsigned __int64
0x180022fd5  mov     [rsp+48h+var_28], 3
0x180022fde  lea     rdx, [rsp+48h+var_28]; void *
0x180022fe3  mov     [rsp+48h+var_20], rsi
0x180022fe8  lea     rcx, qword_180035BB0; this
0x180022fef  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180022ff4  test    al, al
0x180022ff6  jnz     short loc_180022FFC
0x180022ff8  lock and dword ptr [rsi], 0FFFFFFFBh
0x180022ffc  lea     rcx, [rsp+48h+arg_8]
0x180023001  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180023006  mov     eax, [rdi]
0x180023008  test    al, 2
0x18002300a  jnz     short loc_18002301B
0x18002300c  and     eax, 0FFFFF63Eh
0x180023011  and     ebx, 9C1h
0x180023017  or      eax, ebx
0x180023019  mov     [rdi], eax
0x18002301b  mov     rbx, [rsp+48h+arg_10]
0x180023020  mov     rax, rdi
0x180023023  mov     rbp, [rsp+48h+arg_18]
0x180023028  add     rsp, 30h
0x18002302c  pop     r14
0x18002302e  pop     rdi
0x18002302f  pop     rsi
0x180023030  retn
```
