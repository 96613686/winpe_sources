# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18001ccf4`
- end: `0x18001cd8d`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180019a68`
- `0x180019c70`

## callees

- `0x18000ac00`
- `0x18001ccf4`
- `0x18001d570`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001cd1f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001cd1f`

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
0x18001ccf4  mov     [rsp+arg_8], rbx
0x18001ccf9  mov     [rsp+arg_10], rbp
0x18001ccfe  push    rsi
0x18001ccff  push    rdi
0x18001cd00  push    r14
0x18001cd02  sub     rsp, 30h
0x18001cd06  mov     eax, [rcx]
0x18001cd08  mov     ebp, r9d
0x18001cd0b  mov     edi, r8d
0x18001cd0e  mov     rsi, rdx
0x18001cd11  mov     r14, rcx
0x18001cd14  test    eax, eax
0x18001cd16  jz      short loc_18001CD7A
0x18001cd18  lea     rbx, [rcx+8]
0x18001cd1c  mov     rcx, rbx; SRWLock
0x18001cd1f  call    cs:__imp_AcquireSRWLockExclusive
0x18001cd25  mov     eax, [r14+1Ch]
0x18001cd29  mov     [rsp+48h+arg_0], rbx
0x18001cd2e  test    ebp, ebp
0x18001cd30  jz      short loc_18001CD5F
0x18001cd32  cmp     ebp, eax
0x18001cd34  jnz     short loc_18001CD5F
0x18001cd36  lea     rcx, [r14+40h]; this
0x18001cd3a  mov     [rsp+48h+var_24], 0
0x18001cd42  mov     r8d, 10h; unsigned __int64
0x18001cd48  mov     [rsp+48h+var_28], edi
0x18001cd4c  lea     rdx, [rsp+48h+var_28]; void *
0x18001cd51  mov     [rsp+48h+var_20], rsi
0x18001cd56  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001cd5b  test    al, al
0x18001cd5d  jnz     short loc_18001CD70
0x18001cd5f  neg     edi
0x18001cd61  sbb     eax, eax
0x18001cd63  and     eax, 83Ah
0x18001cd68  add     eax, 0FFFFF7C1h
0x18001cd6d  lock and [rsi], eax
0x18001cd70  lea     rcx, [rsp+48h+arg_0]
0x18001cd75  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001cd7a  mov     rbx, [rsp+48h+arg_8]
0x18001cd7f  mov     rbp, [rsp+48h+arg_10]
0x18001cd84  add     rsp, 30h
0x18001cd88  pop     r14
0x18001cd8a  pop     rdi
0x18001cd8b  pop     rsi
0x18001cd8c  retn
```
