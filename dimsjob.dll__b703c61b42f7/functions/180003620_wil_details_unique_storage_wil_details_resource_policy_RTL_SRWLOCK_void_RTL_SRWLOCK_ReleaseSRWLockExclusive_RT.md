# wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)

- ea: `0x180003620`
- end: `0x180003637`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(RTL_SRWLOCK **)`
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800033fc`
- `0x1800034f4`
- `0x180004f80`
- `0x180004ff0`
- `0x180006164`
- `0x180007e3c`
- `0x180008224`
- `0x180008370`
- `0x180009048`
- `0x180009118`
- `0x180009518`

## callees

- `0x180003620`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000362c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000362c`

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
0x180003620  sub     rsp, 28h
0x180003624  mov     rcx, [rcx]; SRWLock
0x180003627  test    rcx, rcx
0x18000362a  jz      short loc_180003632
0x18000362c  call    cs:__imp_ReleaseSRWLockExclusive
0x180003632  add     rsp, 28h
0x180003636  retn
```
