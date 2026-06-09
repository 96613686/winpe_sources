# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180007914`
- end: `0x1800079ad`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005030`

## callees

- `0x180003338`
- `0x180007914`
- `0x180008d20`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000793f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000793f`

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
0x180007914  mov     [rsp+arg_8], rbx
0x180007919  mov     [rsp+arg_10], rbp
0x18000791e  push    rsi
0x18000791f  push    rdi
0x180007920  push    r14
0x180007922  sub     rsp, 30h
0x180007926  mov     eax, [rcx]
0x180007928  mov     ebp, r9d
0x18000792b  mov     edi, r8d
0x18000792e  mov     rsi, rdx
0x180007931  mov     r14, rcx
0x180007934  test    eax, eax
0x180007936  jz      short loc_18000799A
0x180007938  lea     rbx, [rcx+8]
0x18000793c  mov     rcx, rbx; SRWLock
0x18000793f  call    cs:__imp_AcquireSRWLockExclusive
0x180007945  mov     eax, [r14+1Ch]
0x180007949  mov     [rsp+48h+arg_0], rbx
0x18000794e  test    ebp, ebp
0x180007950  jz      short loc_18000797F
0x180007952  cmp     ebp, eax
0x180007954  jnz     short loc_18000797F
0x180007956  lea     rcx, [r14+40h]; this
0x18000795a  mov     [rsp+48h+var_24], 0
0x180007962  mov     r8d, 10h; unsigned __int64
0x180007968  mov     [rsp+48h+var_28], edi
0x18000796c  lea     rdx, [rsp+48h+var_28]; void *
0x180007971  mov     [rsp+48h+var_20], rsi
0x180007976  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000797b  test    al, al
0x18000797d  jnz     short loc_180007990
0x18000797f  neg     edi
0x180007981  sbb     eax, eax
0x180007983  and     eax, 83Ah
0x180007988  add     eax, 0FFFFF7C1h
0x18000798d  lock and [rsi], eax
0x180007990  lea     rcx, [rsp+48h+arg_0]
0x180007995  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000799a  mov     rbx, [rsp+48h+arg_8]
0x18000799f  mov     rbp, [rsp+48h+arg_10]
0x1800079a4  add     rsp, 30h
0x1800079a8  pop     r14
0x1800079aa  pop     rdi
0x1800079ab  pop     rsi
0x1800079ac  retn
```
