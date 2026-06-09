# wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)

- ea: `0x140006e08`
- end: `0x140006e1f`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(RTL_SRWLOCK **)`
- caller_count: `23`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140006ab0`
- `0x140006b40`
- `0x14000747c`
- `0x140007530`
- `0x1400075cc`
- `0x140007644`
- `0x140007efc`
- `0x140007fc8`
- `0x140008054`
- `0x1400084cc`
- `0x140008584`
- `0x140008670`
- `0x140008a80`
- `0x140008b28`
- `0x140008c6c`
- `0x1400096d0`
- `0x140009764`
- `0x1400097fc`
- `0x1400099dc`
- `0x14000f94c`
- `0x14000fce0`
- `0x140010030`
- `0x140016020`

## callees

- `0x140006e08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006e14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006e14`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(
        RTL_SRWLOCK **a1)
{
  RTL_SRWLOCK *v1; // rcx

  v1 = *a1;
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
}

```

## disassembly

```asm
0x140006e08  sub     rsp, 28h
0x140006e0c  mov     rcx, [rcx]; SRWLock
0x140006e0f  test    rcx, rcx
0x140006e12  jz      short loc_140006E1A
0x140006e14  call    cs:__imp_ReleaseSRWLockExclusive
0x140006e1a  add     rsp, 28h
0x140006e1e  retn
```
