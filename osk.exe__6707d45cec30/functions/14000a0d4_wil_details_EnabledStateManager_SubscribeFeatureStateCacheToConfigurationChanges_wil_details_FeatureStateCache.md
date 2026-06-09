# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x14000a0d4`
- end: `0x14000a16d`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140007098`
- `0x14002265c`

## callees

- `0x1400050dc`
- `0x14000a0d4`
- `0x14000c520`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a0ff`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a0ff`

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
0x14000a0d4  mov     [rsp+arg_8], rbx
0x14000a0d9  mov     [rsp+arg_10], rbp
0x14000a0de  push    rsi
0x14000a0df  push    rdi
0x14000a0e0  push    r14
0x14000a0e2  sub     rsp, 30h
0x14000a0e6  mov     eax, [rcx]
0x14000a0e8  mov     ebp, r9d
0x14000a0eb  mov     edi, r8d
0x14000a0ee  mov     rsi, rdx
0x14000a0f1  mov     r14, rcx
0x14000a0f4  test    eax, eax
0x14000a0f6  jz      short loc_14000A15A
0x14000a0f8  lea     rbx, [rcx+8]
0x14000a0fc  mov     rcx, rbx; SRWLock
0x14000a0ff  call    cs:__imp_AcquireSRWLockExclusive
0x14000a105  mov     eax, [r14+1Ch]
0x14000a109  mov     [rsp+48h+arg_0], rbx
0x14000a10e  test    ebp, ebp
0x14000a110  jz      short loc_14000A13F
0x14000a112  cmp     ebp, eax
0x14000a114  jnz     short loc_14000A13F
0x14000a116  lea     rcx, [r14+40h]; this
0x14000a11a  mov     [rsp+48h+var_24], 0
0x14000a122  mov     r8d, 10h; unsigned __int64
0x14000a128  mov     [rsp+48h+var_28], edi
0x14000a12c  lea     rdx, [rsp+48h+var_28]; void *
0x14000a131  mov     [rsp+48h+var_20], rsi
0x14000a136  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000a13b  test    al, al
0x14000a13d  jnz     short loc_14000A150
0x14000a13f  neg     edi
0x14000a141  sbb     eax, eax
0x14000a143  and     eax, 83Ah
0x14000a148  add     eax, 0FFFFF7C1h
0x14000a14d  lock and [rsi], eax
0x14000a150  lea     rcx, [rsp+48h+arg_0]
0x14000a155  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000a15a  mov     rbx, [rsp+48h+arg_8]
0x14000a15f  mov     rbp, [rsp+48h+arg_10]
0x14000a164  add     rsp, 30h
0x14000a168  pop     r14
0x14000a16a  pop     rdi
0x14000a16b  pop     rsi
0x14000a16c  retn
```
