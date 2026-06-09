# wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)

- ea: `0x180003fd8`
- end: `0x180003fef`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `26`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800030d0`
- `0x180005484`
- `0x180005538`
- `0x1800055d4`
- `0x18000726c`
- `0x180007334`
- `0x1800073c0`
- `0x180007414`
- `0x1800074fc`
- `0x180007608`
- `0x180007694`
- `0x180007a24`
- `0x180007c4c`
- `0x180008db8`
- `0x180008e48`
- `0x18000930c`
- `0x1800094f0`
- `0x18000b454`
- `0x18000b5b0`
- `0x18000b70c`
- `0x18000fefc`
- `0x180010704`
- `0x180010790`
- `0x1800114fc`
- `0x180011d2c`
- `0x180011d9c`

## callees

- `0x180003fd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003fe4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003fe4`

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
0x180003fd8  sub     rsp, 28h
0x180003fdc  mov     rcx, [rcx]; SRWLock
0x180003fdf  test    rcx, rcx
0x180003fe2  jz      short loc_180003FEA
0x180003fe4  call    cs:__imp_ReleaseSRWLockExclusive
0x180003fea  add     rsp, 28h
0x180003fee  retn
```
