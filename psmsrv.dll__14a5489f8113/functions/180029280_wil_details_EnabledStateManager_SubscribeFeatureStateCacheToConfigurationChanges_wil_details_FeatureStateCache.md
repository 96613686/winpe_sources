# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180029280`
- end: `0x180029319`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `153`
- prototype: `void __fastcall(__int64, volatile signed __int32 *, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180029320`

## callees

- `0x18001ae8c`
- `0x180029280`
- `0x180029dec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800292ab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800292ab`

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
      || (v10[1] = 0,
          v10[0] = a3,
          v11 = a2,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(a1 + 64), v10, 0x10u)) )
    {
      _InterlockedAnd(a2, a3 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  }
}

```

## disassembly

```asm
0x180029280  mov     [rsp+arg_8], rbx
0x180029285  mov     [rsp+arg_10], rbp
0x18002928a  push    rsi
0x18002928b  push    rdi
0x18002928c  push    r14
0x18002928e  sub     rsp, 30h
0x180029292  mov     eax, [rcx]
0x180029294  mov     ebp, r9d
0x180029297  mov     edi, r8d
0x18002929a  mov     rsi, rdx
0x18002929d  mov     r14, rcx
0x1800292a0  test    eax, eax
0x1800292a2  jz      short loc_180029306
0x1800292a4  lea     rbx, [rcx+8]
0x1800292a8  mov     rcx, rbx; SRWLock
0x1800292ab  call    cs:__imp_AcquireSRWLockExclusive
0x1800292b1  mov     eax, [r14+1Ch]
0x1800292b5  mov     [rsp+48h+arg_0], rbx
0x1800292ba  test    ebp, ebp
0x1800292bc  jz      short loc_1800292EB
0x1800292be  cmp     ebp, eax
0x1800292c0  jnz     short loc_1800292EB
0x1800292c2  lea     rcx, [r14+40h]; this
0x1800292c6  mov     [rsp+48h+var_24], 0
0x1800292ce  mov     r8d, 10h; unsigned __int64
0x1800292d4  mov     [rsp+48h+var_28], edi
0x1800292d8  lea     rdx, [rsp+48h+var_28]; void *
0x1800292dd  mov     [rsp+48h+var_20], rsi
0x1800292e2  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800292e7  test    al, al
0x1800292e9  jnz     short loc_1800292FC
0x1800292eb  neg     edi
0x1800292ed  sbb     eax, eax
0x1800292ef  and     eax, 83Ah
0x1800292f4  add     eax, 0FFFFF7C1h
0x1800292f9  lock and [rsi], eax
0x1800292fc  lea     rcx, [rsp+48h+arg_0]
0x180029301  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180029306  mov     rbx, [rsp+48h+arg_8]
0x18002930b  mov     rbp, [rsp+48h+arg_10]
0x180029310  add     rsp, 30h
0x180029314  pop     r14
0x180029316  pop     rdi
0x180029317  pop     rsi
0x180029318  retn
```
