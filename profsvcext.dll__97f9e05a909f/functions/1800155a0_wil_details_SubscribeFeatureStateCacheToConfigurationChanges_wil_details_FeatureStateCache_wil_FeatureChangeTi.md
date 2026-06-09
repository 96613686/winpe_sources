# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1800155a0`
- end: `0x18001562e`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `142`
- prototype: `void __fastcall(volatile signed __int32 *, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800135d4`
- `0x180013b80`

## callees

- `0x180011514`
- `0x1800155a0`
- `0x1800173ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800155c5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800155c5`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  _DWORD v6[2]; // [rsp+20h] [rbp-38h] BYREF
  volatile signed __int32 *v7; // [rsp+28h] [rbp-30h]
  RTL_SRWLOCK *v8; // [rsp+78h] [rbp+20h] BYREF

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    v8 = &SRWLock;
    if ( !a3
      || a3 != dword_18002DA34
      || (v6[1] = 0,
          v6[0] = a2,
          v7 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002DA58, v6, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  }
}

```

## disassembly

```asm
0x1800155a0  push    rbx
0x1800155a2  push    rbp
0x1800155a3  push    rsi
0x1800155a4  push    rdi
0x1800155a5  sub     rsp, 38h
0x1800155a9  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800155af  mov     esi, r8d
0x1800155b2  mov     ebx, edx
0x1800155b4  mov     rdi, rcx
0x1800155b7  test    eax, eax
0x1800155b9  jz      short loc_180015625
0x1800155bb  lea     rbp, SRWLock
0x1800155c2  mov     rcx, rbp; SRWLock
0x1800155c5  call    cs:__imp_AcquireSRWLockExclusive
0x1800155cb  mov     eax, cs:dword_18002DA34
0x1800155d1  mov     [rsp+58h+arg_18], rbp
0x1800155d6  test    esi, esi
0x1800155d8  jz      short loc_18001560A
0x1800155da  cmp     esi, eax
0x1800155dc  jnz     short loc_18001560A
0x1800155de  mov     r8d, 10h; unsigned __int64
0x1800155e4  mov     [rsp+58h+var_34], 0
0x1800155ec  lea     rdx, [rsp+58h+var_38]; void *
0x1800155f1  mov     [rsp+58h+var_38], ebx
0x1800155f5  lea     rcx, qword_18002DA58; this
0x1800155fc  mov     [rsp+58h+var_30], rdi
0x180015601  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180015606  test    al, al
0x180015608  jnz     short loc_18001561B
0x18001560a  neg     ebx
0x18001560c  sbb     eax, eax
0x18001560e  and     eax, 83Ah
0x180015613  add     eax, 0FFFFF7C1h
0x180015618  lock and [rdi], eax
0x18001561b  lea     rcx, [rsp+58h+arg_18]
0x180015620  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180015625  add     rsp, 38h
0x180015629  pop     rdi
0x18001562a  pop     rsi
0x18001562b  pop     rbp
0x18001562c  pop     rbx
0x18001562d  retn
```
