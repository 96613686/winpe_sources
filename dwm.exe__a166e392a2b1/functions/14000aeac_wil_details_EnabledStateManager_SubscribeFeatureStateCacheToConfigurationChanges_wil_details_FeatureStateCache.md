# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x14000aeac`
- end: `0x14000af45`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000921c`
- `0x14000cf54`

## callees

- `0x140004dcc`
- `0x14000aeac`
- `0x14000ba8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000aed7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000aed7`

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
0x14000aeac  mov     [rsp+arg_8], rbx
0x14000aeb1  mov     [rsp+arg_10], rbp
0x14000aeb6  push    rsi
0x14000aeb7  push    rdi
0x14000aeb8  push    r14
0x14000aeba  sub     rsp, 30h
0x14000aebe  mov     eax, [rcx]
0x14000aec0  mov     ebp, r9d
0x14000aec3  mov     edi, r8d
0x14000aec6  mov     rsi, rdx
0x14000aec9  mov     r14, rcx
0x14000aecc  test    eax, eax
0x14000aece  jz      short loc_14000AF32
0x14000aed0  lea     rbx, [rcx+8]
0x14000aed4  mov     rcx, rbx; SRWLock
0x14000aed7  call    cs:__imp_AcquireSRWLockExclusive
0x14000aedd  mov     eax, [r14+1Ch]
0x14000aee1  mov     [rsp+48h+arg_0], rbx
0x14000aee6  test    ebp, ebp
0x14000aee8  jz      short loc_14000AF17
0x14000aeea  cmp     ebp, eax
0x14000aeec  jnz     short loc_14000AF17
0x14000aeee  lea     rcx, [r14+40h]; this
0x14000aef2  mov     [rsp+48h+var_24], 0
0x14000aefa  mov     r8d, 10h; unsigned __int64
0x14000af00  mov     [rsp+48h+var_28], edi
0x14000af04  lea     rdx, [rsp+48h+var_28]; void *
0x14000af09  mov     [rsp+48h+var_20], rsi
0x14000af0e  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000af13  test    al, al
0x14000af15  jnz     short loc_14000AF28
0x14000af17  neg     edi
0x14000af19  sbb     eax, eax
0x14000af1b  and     eax, 83Ah
0x14000af20  add     eax, 0FFFFF7C1h
0x14000af25  lock and [rsi], eax
0x14000af28  lea     rcx, [rsp+48h+arg_0]
0x14000af2d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000af32  mov     rbx, [rsp+48h+arg_8]
0x14000af37  mov     rbp, [rsp+48h+arg_10]
0x14000af3c  add     rsp, 30h
0x14000af40  pop     r14
0x14000af42  pop     rdi
0x14000af43  pop     rsi
0x14000af44  retn
```
