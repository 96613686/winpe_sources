# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18001a280`
- end: `0x18001a301`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `129`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180018854`

## callees

- `0x180008c94`
- `0x18000ee40`
- `0x18001a280`
- `0x18001ac44`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        __int64 a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  _DWORD v8[2]; // [rsp+20h] [rbp-38h] BYREF
  volatile signed __int32 *v9; // [rsp+28h] [rbp-30h]
  RTL_SRWLOCK *v10; // [rsp+60h] [rbp+8h] BYREF

  if ( *(_DWORD *)a1 )
  {
    wil::srwlock::lock_exclusive((RTL_SRWLOCK *)(a1 + 8), &v10);
    if ( !a4
      || a4 != *(_DWORD *)(a1 + 28)
      || (v8[1] = 0,
          v8[0] = a3,
          v9 = a2,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(a1 + 64), v8, 0x10u)) )
    {
      _InterlockedAnd(a2, a3 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x18001a280  push    rbx
0x18001a282  push    rbp
0x18001a283  push    rsi
0x18001a284  push    rdi
0x18001a285  sub     rsp, 38h
0x18001a289  mov     eax, [rcx]
0x18001a28b  mov     ebp, r9d
0x18001a28e  mov     ebx, r8d
0x18001a291  mov     rdi, rdx
0x18001a294  mov     rsi, rcx
0x18001a297  test    eax, eax
0x18001a299  jz      short loc_18001A2F8
0x18001a29b  add     rcx, 8
0x18001a29f  lea     rdx, [rsp+58h+arg_0]
0x18001a2a4  call    ?lock_exclusive@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_exclusive(void)
0x18001a2a9  mov     eax, [rsi+1Ch]
0x18001a2ac  test    ebp, ebp
0x18001a2ae  jz      short loc_18001A2DD
0x18001a2b0  cmp     ebp, eax
0x18001a2b2  jnz     short loc_18001A2DD
0x18001a2b4  lea     rcx, [rsi+40h]; this
0x18001a2b8  mov     [rsp+58h+var_34], 0
0x18001a2c0  mov     r8d, 10h; unsigned __int64
0x18001a2c6  mov     [rsp+58h+var_38], ebx
0x18001a2ca  lea     rdx, [rsp+58h+var_38]; void *
0x18001a2cf  mov     [rsp+58h+var_30], rdi
0x18001a2d4  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001a2d9  test    al, al
0x18001a2db  jnz     short loc_18001A2EE
0x18001a2dd  neg     ebx
0x18001a2df  sbb     eax, eax
0x18001a2e1  and     eax, 83Ah
0x18001a2e6  add     eax, 0FFFFF7C1h
0x18001a2eb  lock and [rdi], eax
0x18001a2ee  lea     rcx, [rsp+58h+arg_0]
0x18001a2f3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001a2f8  add     rsp, 38h
0x18001a2fc  pop     rdi
0x18001a2fd  pop     rsi
0x18001a2fe  pop     rbp
0x18001a2ff  pop     rbx
0x18001a300  retn
```
