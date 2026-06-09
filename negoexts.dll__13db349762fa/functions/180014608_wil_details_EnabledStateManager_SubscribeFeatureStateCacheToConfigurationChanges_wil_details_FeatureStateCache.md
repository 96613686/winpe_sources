# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180014608`
- end: `0x1800146a1`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180012370`
- `0x180019d00`

## callees

- `0x18000df10`
- `0x180014608`
- `0x18001527c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014633`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014633`

## pseudocode

```c
__int64 __fastcall wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        RTL_SRWLOCK *a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  __int64 result; // rax
  unsigned int *v9; // rbx
  unsigned int Ptr_high; // eax
  _DWORD v11[2]; // [rsp+20h] [rbp-28h] BYREF
  volatile signed __int32 *v12; // [rsp+28h] [rbp-20h]
  unsigned int *v13; // [rsp+50h] [rbp+8h] BYREF

  result = LODWORD(a1->Ptr);
  if ( (_DWORD)result )
  {
    v9 = (unsigned int *)&a1[1];
    AcquireSRWLockExclusive(a1 + 1);
    Ptr_high = HIDWORD(a1[3].Ptr);
    v13 = v9;
    if ( !a4
      || a4 != Ptr_high
      || (v11[1] = 0,
          v11[0] = a3,
          v12 = a2,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&a1[8], v11, 0x10u)) )
    {
      _InterlockedAnd(a2, a3 != 0 ? -5 : -2111);
    }
    return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  }
  return result;
}

```

## disassembly

```asm
0x180014608  mov     [rsp+arg_8], rbx
0x18001460d  mov     [rsp+arg_10], rbp
0x180014612  push    rsi
0x180014613  push    rdi
0x180014614  push    r14
0x180014616  sub     rsp, 30h
0x18001461a  mov     eax, [rcx]
0x18001461c  mov     ebp, r9d
0x18001461f  mov     edi, r8d
0x180014622  mov     rsi, rdx
0x180014625  mov     r14, rcx
0x180014628  test    eax, eax
0x18001462a  jz      short loc_18001468E
0x18001462c  lea     rbx, [rcx+8]
0x180014630  mov     rcx, rbx; SRWLock
0x180014633  call    cs:__imp_AcquireSRWLockExclusive
0x180014639  mov     eax, [r14+1Ch]
0x18001463d  mov     [rsp+48h+arg_0], rbx
0x180014642  test    ebp, ebp
0x180014644  jz      short loc_180014673
0x180014646  cmp     ebp, eax
0x180014648  jnz     short loc_180014673
0x18001464a  lea     rcx, [r14+40h]; this
0x18001464e  mov     [rsp+48h+var_24], 0
0x180014656  mov     r8d, 10h; unsigned __int64
0x18001465c  mov     [rsp+48h+var_28], edi
0x180014660  lea     rdx, [rsp+48h+var_28]; void *
0x180014665  mov     [rsp+48h+var_20], rsi
0x18001466a  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001466f  test    al, al
0x180014671  jnz     short loc_180014684
0x180014673  neg     edi
0x180014675  sbb     eax, eax
0x180014677  and     eax, 83Ah
0x18001467c  add     eax, 0FFFFF7C1h
0x180014681  lock and [rsi], eax
0x180014684  lea     rcx, [rsp+48h+arg_0]
0x180014689  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001468e  mov     rbx, [rsp+48h+arg_8]
0x180014693  mov     rbp, [rsp+48h+arg_10]
0x180014698  add     rsp, 30h
0x18001469c  pop     r14
0x18001469e  pop     rdi
0x18001469f  pop     rsi
0x1800146a0  retn
```
