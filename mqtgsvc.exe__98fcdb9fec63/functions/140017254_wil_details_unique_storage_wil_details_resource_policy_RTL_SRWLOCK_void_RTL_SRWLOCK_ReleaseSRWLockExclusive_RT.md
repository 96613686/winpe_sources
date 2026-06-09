# wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)

- ea: `0x140017254`
- end: `0x14001726c`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `24`
- prototype: `void __fastcall(RTL_SRWLOCK **)`
- caller_count: `12`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400163f0`
- `0x140016460`
- `0x1400171d8`
- `0x140017bc4`
- `0x14001944c`
- `0x140019638`
- `0x140019964`
- `0x140019a0c`
- `0x140019b7c`
- `0x14001aabc`
- `0x14001ab90`
- `0x14001b03c`

## callees

- `0x140017254`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x140017260`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140017260`

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
0x140017254  sub     rsp, 28h
0x140017258  mov     rcx, [rcx]; SRWLock
0x14001725b  test    rcx, rcx
0x14001725e  jz      short loc_140017267
0x140017260  call    cs:__imp_ReleaseSRWLockExclusive
0x140017266  nop
0x140017267  add     rsp, 28h
0x14001726b  retn
```
