# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180017660`
- end: `0x1800176f5`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `149`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180010200`
- `0x1800102f4`
- `0x1800103e8`
- `0x1800104dc`
- `0x1800105d0`
- `0x1800106c4`
- `0x1800107b8`
- `0x1800108ac`
- `0x1800118ec`

## callees

- `0x18000851c`
- `0x180017660`
- `0x180018e04`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180017688`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180017688`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  RTL_SRWLOCK *v6; // [rsp+20h] [rbp-38h] BYREF
  _DWORD v7[2]; // [rsp+28h] [rbp-30h] BYREF
  volatile signed __int32 *v8; // [rsp+30h] [rbp-28h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    v6 = &SRWLock;
    if ( !a3
      || a3 != dword_180044A9C
      || (v7[1] = 0,
          v7[0] = a2,
          v8 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180044AC0, v7, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v6);
  }
}

```

## disassembly

```asm
0x180017660  mov     [rsp+arg_10], rbx
0x180017665  push    rbp
0x180017666  push    rsi
0x180017667  push    rdi
0x180017668  sub     rsp, 40h
0x18001766c  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180017672  mov     esi, r8d
0x180017675  mov     edi, edx
0x180017677  mov     rbx, rcx
0x18001767a  test    eax, eax
0x18001767c  jz      short loc_1800176E8
0x18001767e  lea     rbp, SRWLock
0x180017685  mov     rcx, rbp; SRWLock
0x180017688  call    cs:__imp_AcquireSRWLockExclusive
0x18001768e  mov     eax, cs:dword_180044A9C
0x180017694  mov     [rsp+58h+var_38], rbp
0x180017699  test    esi, esi
0x18001769b  jz      short loc_1800176CD
0x18001769d  cmp     esi, eax
0x18001769f  jnz     short loc_1800176CD
0x1800176a1  mov     r8d, 10h; unsigned __int64
0x1800176a7  mov     [rsp+58h+var_2C], 0
0x1800176af  lea     rdx, [rsp+58h+var_30]; void *
0x1800176b4  mov     [rsp+58h+var_30], edi
0x1800176b8  lea     rcx, qword_180044AC0; this
0x1800176bf  mov     [rsp+58h+var_28], rbx
0x1800176c4  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800176c9  test    al, al
0x1800176cb  jnz     short loc_1800176DE
0x1800176cd  neg     edi
0x1800176cf  sbb     eax, eax
0x1800176d1  and     eax, 83Ah
0x1800176d6  add     eax, 0FFFFF7C1h
0x1800176db  lock and [rbx], eax
0x1800176de  lea     rcx, [rsp+58h+var_38]
0x1800176e3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800176e8  mov     rbx, [rsp+58h+arg_10]
0x1800176ed  add     rsp, 40h
0x1800176f1  pop     rdi
0x1800176f2  pop     rsi
0x1800176f3  pop     rbp
0x1800176f4  retn
```
