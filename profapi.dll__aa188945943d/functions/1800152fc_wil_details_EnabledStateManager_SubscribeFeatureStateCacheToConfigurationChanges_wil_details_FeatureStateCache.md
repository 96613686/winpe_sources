# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1800152fc`
- end: `0x180015395`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `153`
- prototype: `void __fastcall(__int64, volatile signed __int32 *, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000e0b0`
- `0x180012ec0`

## callees

- `0x18000f11c`
- `0x1800152fc`
- `0x180015b2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015327`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015327`

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
0x1800152fc  mov     [rsp+arg_8], rbx
0x180015301  mov     [rsp+arg_10], rbp
0x180015306  push    rsi
0x180015307  push    rdi
0x180015308  push    r14
0x18001530a  sub     rsp, 30h
0x18001530e  mov     eax, [rcx]
0x180015310  mov     ebp, r9d
0x180015313  mov     edi, r8d
0x180015316  mov     rsi, rdx
0x180015319  mov     r14, rcx
0x18001531c  test    eax, eax
0x18001531e  jz      short loc_180015382
0x180015320  lea     rbx, [rcx+8]
0x180015324  mov     rcx, rbx; SRWLock
0x180015327  call    cs:__imp_AcquireSRWLockExclusive
0x18001532d  mov     eax, [r14+1Ch]
0x180015331  mov     [rsp+48h+arg_0], rbx
0x180015336  test    ebp, ebp
0x180015338  jz      short loc_180015367
0x18001533a  cmp     ebp, eax
0x18001533c  jnz     short loc_180015367
0x18001533e  lea     rcx, [r14+40h]; this
0x180015342  mov     [rsp+48h+var_24], 0
0x18001534a  mov     r8d, 10h; unsigned __int64
0x180015350  mov     [rsp+48h+var_28], edi
0x180015354  lea     rdx, [rsp+48h+var_28]; void *
0x180015359  mov     [rsp+48h+var_20], rsi
0x18001535e  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180015363  test    al, al
0x180015365  jnz     short loc_180015378
0x180015367  neg     edi
0x180015369  sbb     eax, eax
0x18001536b  and     eax, 83Ah
0x180015370  add     eax, 0FFFFF7C1h
0x180015375  lock and [rsi], eax
0x180015378  lea     rcx, [rsp+48h+arg_0]
0x18001537d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180015382  mov     rbx, [rsp+48h+arg_8]
0x180015387  mov     rbp, [rsp+48h+arg_10]
0x18001538c  add     rsp, 30h
0x180015390  pop     r14
0x180015392  pop     rdi
0x180015393  pop     rsi
0x180015394  retn
```
