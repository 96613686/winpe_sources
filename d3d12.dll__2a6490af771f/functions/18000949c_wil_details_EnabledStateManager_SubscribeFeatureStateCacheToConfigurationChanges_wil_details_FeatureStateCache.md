# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000949c`
- end: `0x180009535`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180007c14`
- `0x18000ecf0`

## callees

- `0x1800045a8`
- `0x18000949c`
- `0x18000a1e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800094c7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800094c7`

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
0x18000949c  mov     [rsp+arg_8], rbx
0x1800094a1  mov     [rsp+arg_10], rbp
0x1800094a6  push    rsi
0x1800094a7  push    rdi
0x1800094a8  push    r14
0x1800094aa  sub     rsp, 30h
0x1800094ae  mov     eax, [rcx]
0x1800094b0  mov     ebp, r9d
0x1800094b3  mov     edi, r8d
0x1800094b6  mov     rsi, rdx
0x1800094b9  mov     r14, rcx
0x1800094bc  test    eax, eax
0x1800094be  jz      short loc_180009522
0x1800094c0  lea     rbx, [rcx+8]
0x1800094c4  mov     rcx, rbx; SRWLock
0x1800094c7  call    cs:__imp_AcquireSRWLockExclusive
0x1800094cd  mov     eax, [r14+1Ch]
0x1800094d1  mov     [rsp+48h+arg_0], rbx
0x1800094d6  test    ebp, ebp
0x1800094d8  jz      short loc_180009507
0x1800094da  cmp     ebp, eax
0x1800094dc  jnz     short loc_180009507
0x1800094de  lea     rcx, [r14+40h]; this
0x1800094e2  mov     [rsp+48h+var_24], 0
0x1800094ea  mov     r8d, 10h; unsigned __int64
0x1800094f0  mov     [rsp+48h+var_28], edi
0x1800094f4  lea     rdx, [rsp+48h+var_28]; void *
0x1800094f9  mov     [rsp+48h+var_20], rsi
0x1800094fe  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180009503  test    al, al
0x180009505  jnz     short loc_180009518
0x180009507  neg     edi
0x180009509  sbb     eax, eax
0x18000950b  and     eax, 83Ah
0x180009510  add     eax, 0FFFFF7C1h
0x180009515  lock and [rsi], eax
0x180009518  lea     rcx, [rsp+48h+arg_0]
0x18000951d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180009522  mov     rbx, [rsp+48h+arg_8]
0x180009527  mov     rbp, [rsp+48h+arg_10]
0x18000952c  add     rsp, 30h
0x180009530  pop     r14
0x180009532  pop     rdi
0x180009533  pop     rsi
0x180009534  retn
```
