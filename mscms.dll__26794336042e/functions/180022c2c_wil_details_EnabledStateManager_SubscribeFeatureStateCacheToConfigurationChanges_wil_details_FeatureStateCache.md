# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180022c2c`
- end: `0x180022cc5`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `153`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000f690`
- `0x18000f7a0`
- `0x180022f3c`
- `0x1800403b8`
- `0x1800404a0`
- `0x180040588`
- `0x180048624`
- `0x180048710`
- `0x1800487f8`
- `0x180048a98`

## callees

- `0x1800198f8`
- `0x18001c798`
- `0x180022c2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022c57`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022c57`

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
0x180022c2c  mov     [rsp+arg_8], rbx
0x180022c31  mov     [rsp+arg_10], rbp
0x180022c36  push    rsi
0x180022c37  push    rdi
0x180022c38  push    r14
0x180022c3a  sub     rsp, 30h
0x180022c3e  mov     eax, [rcx]
0x180022c40  mov     ebp, r9d
0x180022c43  mov     edi, r8d
0x180022c46  mov     rsi, rdx
0x180022c49  mov     r14, rcx
0x180022c4c  test    eax, eax
0x180022c4e  jz      short loc_180022CB2
0x180022c50  lea     rbx, [rcx+8]
0x180022c54  mov     rcx, rbx; SRWLock
0x180022c57  call    cs:__imp_AcquireSRWLockExclusive
0x180022c5d  mov     eax, [r14+1Ch]
0x180022c61  mov     [rsp+48h+arg_0], rbx
0x180022c66  test    ebp, ebp
0x180022c68  jz      short loc_180022C97
0x180022c6a  cmp     ebp, eax
0x180022c6c  jnz     short loc_180022C97
0x180022c6e  lea     rcx, [r14+40h]; this
0x180022c72  mov     [rsp+48h+var_24], 0
0x180022c7a  mov     r8d, 10h; unsigned __int64
0x180022c80  mov     [rsp+48h+var_28], edi
0x180022c84  lea     rdx, [rsp+48h+var_28]; void *
0x180022c89  mov     [rsp+48h+var_20], rsi
0x180022c8e  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180022c93  test    al, al
0x180022c95  jnz     short loc_180022CA8
0x180022c97  neg     edi
0x180022c99  sbb     eax, eax
0x180022c9b  and     eax, 83Ah
0x180022ca0  add     eax, 0FFFFF7C1h
0x180022ca5  lock and [rsi], eax
0x180022ca8  lea     rcx, [rsp+48h+arg_0]
0x180022cad  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180022cb2  mov     rbx, [rsp+48h+arg_8]
0x180022cb7  mov     rbp, [rsp+48h+arg_10]
0x180022cbc  add     rsp, 30h
0x180022cc0  pop     r14
0x180022cc2  pop     rdi
0x180022cc3  pop     rsi
0x180022cc4  retn
```
