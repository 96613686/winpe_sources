# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18003d6a0`
- end: `0x18003d733`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `147`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001c9b4`
- `0x18003b49c`
- `0x180040760`
- `0x180040848`
- `0x180059998`
- `0x180059afc`

## callees

- `0x18003af20`
- `0x18003d6a0`
- `0x18003dc50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d6cb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d6cb`

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
  unsigned __int64 v10; // r8
  unsigned int Ptr_high; // eax
  _DWORD Source[2]; // [rsp+20h] [rbp-28h] BYREF
  volatile signed __int32 *v13; // [rsp+28h] [rbp-20h]
  unsigned int *v14; // [rsp+50h] [rbp+8h] BYREF

  result = LODWORD(a1->Ptr);
  if ( (_DWORD)result )
  {
    v9 = (unsigned int *)&a1[1];
    AcquireSRWLockExclusive(a1 + 1);
    Ptr_high = HIDWORD(a1[3].Ptr);
    v14 = v9;
    if ( !a4
      || a4 != Ptr_high
      || (Source[1] = 0,
          Source[0] = a3,
          v13 = a2,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&a1[8], Source, v10)) )
    {
      _InterlockedAnd(a2, a3 != 0 ? -5 : -2111);
    }
    return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
  }
  return result;
}

```

## disassembly

```asm
0x18003d6a0  mov     [rsp+arg_8], rbx
0x18003d6a5  mov     [rsp+arg_10], rbp
0x18003d6aa  push    rsi
0x18003d6ab  push    rdi
0x18003d6ac  push    r14
0x18003d6ae  sub     rsp, 30h
0x18003d6b2  mov     eax, [rcx]
0x18003d6b4  mov     ebp, r9d
0x18003d6b7  mov     edi, r8d
0x18003d6ba  mov     rsi, rdx
0x18003d6bd  mov     r14, rcx
0x18003d6c0  test    eax, eax
0x18003d6c2  jz      short loc_18003D720
0x18003d6c4  lea     rbx, [rcx+8]
0x18003d6c8  mov     rcx, rbx; SRWLock
0x18003d6cb  call    cs:__imp_AcquireSRWLockExclusive
0x18003d6d1  mov     eax, [r14+1Ch]
0x18003d6d5  mov     [rsp+48h+arg_0], rbx
0x18003d6da  test    ebp, ebp
0x18003d6dc  jz      short loc_18003D705
0x18003d6de  cmp     ebp, eax
0x18003d6e0  jnz     short loc_18003D705
0x18003d6e2  lea     rcx, [r14+40h]; this
0x18003d6e6  mov     [rsp+48h+var_24], 0
0x18003d6ee  lea     rdx, [rsp+48h+Source]; Source
0x18003d6f3  mov     [rsp+48h+Source], edi
0x18003d6f7  mov     [rsp+48h+var_20], rsi
0x18003d6fc  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003d701  test    al, al
0x18003d703  jnz     short loc_18003D716
0x18003d705  neg     edi
0x18003d707  sbb     eax, eax
0x18003d709  and     eax, 83Ah
0x18003d70e  add     eax, 0FFFFF7C1h
0x18003d713  lock and [rsi], eax
0x18003d716  lea     rcx, [rsp+48h+arg_0]
0x18003d71b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003d720  mov     rbx, [rsp+48h+arg_8]
0x18003d725  mov     rbp, [rsp+48h+arg_10]
0x18003d72a  add     rsp, 30h
0x18003d72e  pop     r14
0x18003d730  pop     rdi
0x18003d731  pop     rsi
0x18003d732  retn
```
