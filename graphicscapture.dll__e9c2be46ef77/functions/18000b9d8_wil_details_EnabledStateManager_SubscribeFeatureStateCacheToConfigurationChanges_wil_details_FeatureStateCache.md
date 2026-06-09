# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000b9d8`
- end: `0x18000ba71`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000957c`

## callees

- `0x180007c28`
- `0x18000b9d8`
- `0x18000c930`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ba03`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ba03`

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
0x18000b9d8  mov     [rsp+arg_8], rbx
0x18000b9dd  mov     [rsp+arg_10], rbp
0x18000b9e2  push    rsi
0x18000b9e3  push    rdi
0x18000b9e4  push    r14
0x18000b9e6  sub     rsp, 30h
0x18000b9ea  mov     eax, [rcx]
0x18000b9ec  mov     ebp, r9d
0x18000b9ef  mov     edi, r8d
0x18000b9f2  mov     rsi, rdx
0x18000b9f5  mov     r14, rcx
0x18000b9f8  test    eax, eax
0x18000b9fa  jz      short loc_18000BA5E
0x18000b9fc  lea     rbx, [rcx+8]
0x18000ba00  mov     rcx, rbx; SRWLock
0x18000ba03  call    cs:__imp_AcquireSRWLockExclusive
0x18000ba09  mov     eax, [r14+1Ch]
0x18000ba0d  mov     [rsp+48h+arg_0], rbx
0x18000ba12  test    ebp, ebp
0x18000ba14  jz      short loc_18000BA43
0x18000ba16  cmp     ebp, eax
0x18000ba18  jnz     short loc_18000BA43
0x18000ba1a  lea     rcx, [r14+40h]; this
0x18000ba1e  mov     [rsp+48h+var_24], 0
0x18000ba26  mov     r8d, 10h; unsigned __int64
0x18000ba2c  mov     [rsp+48h+var_28], edi
0x18000ba30  lea     rdx, [rsp+48h+var_28]; void *
0x18000ba35  mov     [rsp+48h+var_20], rsi
0x18000ba3a  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000ba3f  test    al, al
0x18000ba41  jnz     short loc_18000BA54
0x18000ba43  neg     edi
0x18000ba45  sbb     eax, eax
0x18000ba47  and     eax, 83Ah
0x18000ba4c  add     eax, 0FFFFF7C1h
0x18000ba51  lock and [rsi], eax
0x18000ba54  lea     rcx, [rsp+48h+arg_0]
0x18000ba59  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000ba5e  mov     rbx, [rsp+48h+arg_8]
0x18000ba63  mov     rbp, [rsp+48h+arg_10]
0x18000ba68  add     rsp, 30h
0x18000ba6c  pop     r14
0x18000ba6e  pop     rdi
0x18000ba6f  pop     rsi
0x18000ba70  retn
```
