# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180015be8`
- end: `0x180015c82`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `154`
- prototype: `void __fastcall(__int64, volatile signed __int32 *, int, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180012f98`
- `0x180013a00`
- `0x180015c90`

## callees

- `0x18000acac`
- `0x180015be8`
- `0x1800168ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015c13`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015c13`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        __int64 a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  RTL_SRWLOCK *v8; // rbx
  _DWORD v9[2]; // [rsp+20h] [rbp-28h] BYREF
  volatile signed __int32 *v10; // [rsp+28h] [rbp-20h]
  RTL_SRWLOCK *v11; // [rsp+50h] [rbp+8h] BYREF

  if ( *(_DWORD *)a1 )
  {
    v8 = (RTL_SRWLOCK *)(a1 + 8);
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
    v11 = v8;
    if ( !a4
      || a4 != *(_DWORD *)(a1 + 28)
      || (v9[1] = 0, v9[0] = a3, v10 = a2, !wil::details_abi::heap_buffer::push_back((void **)(a1 + 64), v9, 0x10u)) )
    {
      _InterlockedAnd(a2, a3 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x180015be8  mov     [rsp+arg_8], rbx
0x180015bed  mov     [rsp+arg_10], rbp
0x180015bf2  push    rsi
0x180015bf3  push    rdi
0x180015bf4  push    r14
0x180015bf6  sub     rsp, 30h
0x180015bfa  mov     ebp, r9d
0x180015bfd  mov     edi, r8d
0x180015c00  mov     rsi, rdx
0x180015c03  mov     r14, rcx
0x180015c06  mov     eax, [rcx]
0x180015c08  test    eax, eax
0x180015c0a  jz      short loc_180015C6F
0x180015c0c  lea     rbx, [rcx+8]
0x180015c10  mov     rcx, rbx; SRWLock
0x180015c13  call    cs:__imp_AcquireSRWLockExclusive
0x180015c19  mov     [rsp+48h+arg_0], rbx
0x180015c1e  mov     eax, [r14+1Ch]
0x180015c22  test    ebp, ebp
0x180015c24  jz      short loc_180015C53
0x180015c26  cmp     ebp, eax
0x180015c28  jnz     short loc_180015C53
0x180015c2a  mov     [rsp+48h+var_24], 0
0x180015c32  mov     [rsp+48h+var_28], edi
0x180015c36  mov     [rsp+48h+var_20], rsi
0x180015c3b  lea     rcx, [r14+40h]; this
0x180015c3f  mov     r8d, 10h; unsigned __int64
0x180015c45  lea     rdx, [rsp+48h+var_28]; void *
0x180015c4a  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180015c4f  test    al, al
0x180015c51  jnz     short loc_180015C64
0x180015c53  neg     edi
0x180015c55  sbb     eax, eax
0x180015c57  and     eax, 83Ah
0x180015c5c  add     eax, 0FFFFF7C1h
0x180015c61  lock and [rsi], eax
0x180015c64  lea     rcx, [rsp+48h+arg_0]
0x180015c69  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180015c6e  nop
0x180015c6f  mov     rbx, [rsp+48h+arg_8]
0x180015c74  mov     rbp, [rsp+48h+arg_10]
0x180015c79  add     rsp, 30h
0x180015c7d  pop     r14
0x180015c7f  pop     rdi
0x180015c80  pop     rsi
0x180015c81  retn
```
