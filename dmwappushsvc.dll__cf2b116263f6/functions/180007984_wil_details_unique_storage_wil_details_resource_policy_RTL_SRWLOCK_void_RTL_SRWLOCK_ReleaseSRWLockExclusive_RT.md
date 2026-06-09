# wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)

- ea: `0x180007984`
- end: `0x18000799b`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(RTL_SRWLOCK **)`
- caller_count: `18`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180006880`
- `0x180006910`
- `0x1800083e4`
- `0x1800084d0`
- `0x180009aa0`
- `0x180009b68`
- `0x180009bf4`
- `0x180009cec`
- `0x180009dd8`
- `0x180009ec4`
- `0x18000a45c`
- `0x18000a504`
- `0x18000a5cc`
- `0x18000a76c`
- `0x18000b604`
- `0x18000b698`
- `0x18000b768`
- `0x18000bd1c`

## callees

- `0x180007984`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007990`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007990`

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
0x180007984  sub     rsp, 28h
0x180007988  mov     rcx, [rcx]; SRWLock
0x18000798b  test    rcx, rcx
0x18000798e  jz      short loc_180007996
0x180007990  call    cs:__imp_ReleaseSRWLockExclusive
0x180007996  add     rsp, 28h
0x18000799a  retn
```
