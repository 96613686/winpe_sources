# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180008db8`
- end: `0x180008e42`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800067c0`

## callees

- `0x180003fd8`
- `0x180008db8`
- `0x180009e8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008ddc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008ddc`

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
0x180008db8  push    rbx
0x180008dba  push    rbp
0x180008dbb  push    rsi
0x180008dbc  push    rdi
0x180008dbd  push    r14
0x180008dbf  sub     rsp, 40h
0x180008dc3  mov     eax, [rcx]
0x180008dc5  mov     ebp, r9d
0x180008dc8  mov     esi, r8d
0x180008dcb  mov     rdi, rdx
0x180008dce  mov     r14, rcx
0x180008dd1  test    eax, eax
0x180008dd3  jz      short loc_180008E37
0x180008dd5  lea     rbx, [rcx+8]
0x180008dd9  mov     rcx, rbx; SRWLock
0x180008ddc  call    cs:__imp_AcquireSRWLockExclusive
0x180008de2  mov     eax, [r14+1Ch]
0x180008de6  mov     [rsp+68h+var_48], rbx
0x180008deb  test    ebp, ebp
0x180008ded  jz      short loc_180008E1C
0x180008def  cmp     ebp, eax
0x180008df1  jnz     short loc_180008E1C
0x180008df3  lea     rcx, [r14+40h]; this
0x180008df7  mov     [rsp+68h+var_3C], 0
0x180008dff  mov     r8d, 10h; unsigned __int64
0x180008e05  mov     [rsp+68h+var_40], esi
0x180008e09  lea     rdx, [rsp+68h+var_40]; void *
0x180008e0e  mov     [rsp+68h+var_38], rdi
0x180008e13  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180008e18  test    al, al
0x180008e1a  jnz     short loc_180008E2D
0x180008e1c  neg     esi
0x180008e1e  sbb     eax, eax
0x180008e20  and     eax, 83Ah
0x180008e25  add     eax, 0FFFFF7C1h
0x180008e2a  lock and [rdi], eax
0x180008e2d  lea     rcx, [rsp+68h+var_48]
0x180008e32  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180008e37  add     rsp, 40h
0x180008e3b  pop     r14
0x180008e3d  pop     rdi
0x180008e3e  pop     rsi
0x180008e3f  pop     rbp
0x180008e40  pop     rbx
0x180008e41  retn
```
