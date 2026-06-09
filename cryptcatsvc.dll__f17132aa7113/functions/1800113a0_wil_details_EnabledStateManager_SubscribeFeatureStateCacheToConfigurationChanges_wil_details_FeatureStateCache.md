# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1800113a0`
- end: `0x18001142a`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000f37c`

## callees

- `0x18000b5ec`
- `0x1800113a0`
- `0x18001201c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800113c4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800113c4`

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
  unsigned int *v11; // [rsp+20h] [rbp-48h] BYREF
  _DWORD v12[2]; // [rsp+28h] [rbp-40h] BYREF
  volatile signed __int32 *v13; // [rsp+30h] [rbp-38h]

  result = LODWORD(a1->Ptr);
  if ( (_DWORD)result )
  {
    v9 = (unsigned int *)&a1[1];
    AcquireSRWLockExclusive(a1 + 1);
    Ptr_high = HIDWORD(a1[3].Ptr);
    v11 = v9;
    if ( !a4
      || a4 != Ptr_high
      || (v12[1] = 0,
          v12[0] = a3,
          v13 = a2,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&a1[8], v12, 0x10u)) )
    {
      _InterlockedAnd(a2, a3 != 0 ? -5 : -2111);
    }
    return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
  return result;
}

```

## disassembly

```asm
0x1800113a0  push    rbx
0x1800113a2  push    rbp
0x1800113a3  push    rsi
0x1800113a4  push    rdi
0x1800113a5  push    r14
0x1800113a7  sub     rsp, 40h
0x1800113ab  mov     eax, [rcx]
0x1800113ad  mov     ebp, r9d
0x1800113b0  mov     esi, r8d
0x1800113b3  mov     rdi, rdx
0x1800113b6  mov     r14, rcx
0x1800113b9  test    eax, eax
0x1800113bb  jz      short loc_18001141F
0x1800113bd  lea     rbx, [rcx+8]
0x1800113c1  mov     rcx, rbx; SRWLock
0x1800113c4  call    cs:__imp_AcquireSRWLockExclusive
0x1800113ca  mov     eax, [r14+1Ch]
0x1800113ce  mov     [rsp+68h+var_48], rbx
0x1800113d3  test    ebp, ebp
0x1800113d5  jz      short loc_180011404
0x1800113d7  cmp     ebp, eax
0x1800113d9  jnz     short loc_180011404
0x1800113db  lea     rcx, [r14+40h]; this
0x1800113df  mov     [rsp+68h+var_3C], 0
0x1800113e7  mov     r8d, 10h; unsigned __int64
0x1800113ed  mov     [rsp+68h+var_40], esi
0x1800113f1  lea     rdx, [rsp+68h+var_40]; void *
0x1800113f6  mov     [rsp+68h+var_38], rdi
0x1800113fb  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180011400  test    al, al
0x180011402  jnz     short loc_180011415
0x180011404  neg     esi
0x180011406  sbb     eax, eax
0x180011408  and     eax, 83Ah
0x18001140d  add     eax, 0FFFFF7C1h
0x180011412  lock and [rdi], eax
0x180011415  lea     rcx, [rsp+68h+var_48]
0x18001141a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001141f  add     rsp, 40h
0x180011423  pop     r14
0x180011425  pop     rdi
0x180011426  pop     rsi
0x180011427  pop     rbp
0x180011428  pop     rbx
0x180011429  retn
```
