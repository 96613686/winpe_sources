# wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)

- ea: `0x18000f11c`
- end: `0x18000f133`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(RTL_SRWLOCK **)`
- caller_count: `26`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000d1cc`
- `0x18000ef04`
- `0x18000eff0`
- `0x180012580`
- `0x1800125f0`
- `0x180012b90`
- `0x180012c7c`
- `0x180012fa8`
- `0x1800130e8`
- `0x180013228`
- `0x180013368`
- `0x1800134a8`
- `0x1800135e8`
- `0x180013728`
- `0x180013868`
- `0x1800139a8`
- `0x180013ae8`
- `0x180013c28`
- `0x1800147c0`
- `0x180014888`
- `0x180014bc0`
- `0x180014cec`
- `0x1800152fc`
- `0x18001539c`
- `0x180015520`
- `0x1800156b0`

## callees

- `0x18000f11c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f128`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f128`

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
0x18000f11c  sub     rsp, 28h
0x18000f120  mov     rcx, [rcx]; SRWLock
0x18000f123  test    rcx, rcx
0x18000f126  jz      short loc_18000F12E
0x18000f128  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f12e  add     rsp, 28h
0x18000f132  retn
```
