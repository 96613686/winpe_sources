# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180014db0`
- end: `0x180014e49`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `153`
- prototype: `void __fastcall(__int64, volatile signed __int32 *, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000bb18`
- `0x180013924`

## callees

- `0x18000ab44`
- `0x18000c824`
- `0x180014db0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014ddb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014ddb`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        __int64 a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  RTL_SRWLOCK *v8; // rbx
  int v9; // eax
  _DWORD v10[2]; // [rsp+20h] [rbp-28h] BYREF
  volatile signed __int32 *v11; // [rsp+28h] [rbp-20h]
  RTL_SRWLOCK *v12; // [rsp+50h] [rbp+8h] BYREF

  if ( *(_DWORD *)a1 )
  {
    v8 = (RTL_SRWLOCK *)(a1 + 8);
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
    v9 = *(_DWORD *)(a1 + 28);
    v12 = v8;
    if ( !a4
      || a4 != v9
      || (v10[1] = 0, v10[0] = a3, v11 = a2, !wil::details_abi::heap_buffer::push_back((void **)(a1 + 64), v10, 0x10u)) )
    {
      _InterlockedAnd(a2, a3 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  }
}

```

## disassembly

```asm
0x180014db0  mov     [rsp+arg_8], rbx
0x180014db5  mov     [rsp+arg_10], rbp
0x180014dba  push    rsi
0x180014dbb  push    rdi
0x180014dbc  push    r14
0x180014dbe  sub     rsp, 30h
0x180014dc2  mov     eax, [rcx]
0x180014dc4  mov     ebp, r9d
0x180014dc7  mov     edi, r8d
0x180014dca  mov     rsi, rdx
0x180014dcd  mov     r14, rcx
0x180014dd0  test    eax, eax
0x180014dd2  jz      short loc_180014E36
0x180014dd4  lea     rbx, [rcx+8]
0x180014dd8  mov     rcx, rbx; SRWLock
0x180014ddb  call    cs:__imp_AcquireSRWLockExclusive
0x180014de1  mov     eax, [r14+1Ch]
0x180014de5  mov     [rsp+48h+arg_0], rbx
0x180014dea  test    ebp, ebp
0x180014dec  jz      short loc_180014E1B
0x180014dee  cmp     ebp, eax
0x180014df0  jnz     short loc_180014E1B
0x180014df2  lea     rcx, [r14+40h]; this
0x180014df6  mov     [rsp+48h+var_24], 0
0x180014dfe  mov     r8d, 10h; unsigned __int64
0x180014e04  mov     [rsp+48h+var_28], edi
0x180014e08  lea     rdx, [rsp+48h+var_28]; void *
0x180014e0d  mov     [rsp+48h+var_20], rsi
0x180014e12  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180014e17  test    al, al
0x180014e19  jnz     short loc_180014E2C
0x180014e1b  neg     edi
0x180014e1d  sbb     eax, eax
0x180014e1f  and     eax, 83Ah
0x180014e24  add     eax, 0FFFFF7C1h
0x180014e29  lock and [rsi], eax
0x180014e2c  lea     rcx, [rsp+48h+arg_0]
0x180014e31  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014e36  mov     rbx, [rsp+48h+arg_8]
0x180014e3b  mov     rbp, [rsp+48h+arg_10]
0x180014e40  add     rsp, 30h
0x180014e44  pop     r14
0x180014e46  pop     rdi
0x180014e47  pop     rsi
0x180014e48  retn
```
