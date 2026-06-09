# wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)

- ea: `0x140004dcc`
- end: `0x140004de3`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `17`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400041e4`
- `0x140006a50`
- `0x140006aa0`
- `0x140007ff8`
- `0x1400080ac`
- `0x140008148`
- `0x1400099ec`
- `0x140009ab4`
- `0x140009c24`
- `0x140009f54`
- `0x14000a14c`
- `0x14000aeac`
- `0x14000b210`
- `0x14000b410`
- `0x14000ced4`
- `0x14000d0d0`
- `0x14000d124`

## callees

- `0x140004dcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004dd8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004dd8`

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
0x140004dcc  sub     rsp, 28h
0x140004dd0  mov     rcx, [rcx]; SRWLock
0x140004dd3  test    rcx, rcx
0x140004dd6  jz      short loc_140004DDE
0x140004dd8  call    cs:__imp_ReleaseSRWLockExclusive
0x140004dde  add     rsp, 28h
0x140004de2  retn
```
