# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18001011c`
- end: `0x1800101b5`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `153`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000f24c`
- `0x1800118f0`
- `0x1800119d8`
- `0x180011b3c`
- `0x180011c24`

## callees

- `0x18000cad8`
- `0x18001011c`
- `0x180010a6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010147`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010147`

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
0x18001011c  mov     [rsp+arg_8], rbx
0x180010121  mov     [rsp+arg_10], rbp
0x180010126  push    rsi
0x180010127  push    rdi
0x180010128  push    r14
0x18001012a  sub     rsp, 30h
0x18001012e  mov     eax, [rcx]
0x180010130  mov     ebp, r9d
0x180010133  mov     edi, r8d
0x180010136  mov     rsi, rdx
0x180010139  mov     r14, rcx
0x18001013c  test    eax, eax
0x18001013e  jz      short loc_1800101A2
0x180010140  lea     rbx, [rcx+8]
0x180010144  mov     rcx, rbx; SRWLock
0x180010147  call    cs:__imp_AcquireSRWLockExclusive
0x18001014d  mov     eax, [r14+1Ch]
0x180010151  mov     [rsp+48h+arg_0], rbx
0x180010156  test    ebp, ebp
0x180010158  jz      short loc_180010187
0x18001015a  cmp     ebp, eax
0x18001015c  jnz     short loc_180010187
0x18001015e  lea     rcx, [r14+40h]; this
0x180010162  mov     [rsp+48h+var_24], 0
0x18001016a  mov     r8d, 10h; unsigned __int64
0x180010170  mov     [rsp+48h+var_28], edi
0x180010174  lea     rdx, [rsp+48h+var_28]; void *
0x180010179  mov     [rsp+48h+var_20], rsi
0x18001017e  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180010183  test    al, al
0x180010185  jnz     short loc_180010198
0x180010187  neg     edi
0x180010189  sbb     eax, eax
0x18001018b  and     eax, 83Ah
0x180010190  add     eax, 0FFFFF7C1h
0x180010195  lock and [rsi], eax
0x180010198  lea     rcx, [rsp+48h+arg_0]
0x18001019d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800101a2  mov     rbx, [rsp+48h+arg_8]
0x1800101a7  mov     rbp, [rsp+48h+arg_10]
0x1800101ac  add     rsp, 30h
0x1800101b0  pop     r14
0x1800101b2  pop     rdi
0x1800101b3  pop     rsi
0x1800101b4  retn
```
