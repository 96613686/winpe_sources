# wil::details::registry_watcher_state::ReleaseFromCallback(bool)

- ea: `0x18009f0b8`
- end: `0x18009f15b`
- name: `?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z`
- size: `163`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800a1b90`

## callees

- `0x18004cbbc`
- `0x18009cb1c`
- `0x18009f0b8`
- `0x1800a3600`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009f0d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009f0d7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18009f13b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18009f13b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18009f104`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18009f104`

## pseudocode

```c
void __fastcall wil::details::registry_watcher_state::ReleaseFromCallback(
        wil::details::registry_watcher_state *this,
        char a2)
{
  char *v2; // rbx
  struct _TP_WAIT *v5; // rcx
  unsigned int v6; // edx
  char *v7; // [rsp+30h] [rbp+8h] BYREF

  v2 = (char *)this + 152;
  AcquireSRWLockExclusive((PSRWLOCK)this + 19);
  v7 = v2;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 37, 0xFFFFFFFF) == 1 )
  {
    v5 = (struct _TP_WAIT *)*((_QWORD *)this + 17);
    *((_QWORD *)this + 17) = 0;
    CloseThreadpoolWait(v5);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
      &v7,
      0);
    if ( this )
      wil::details::registry_watcher_state::`scalar deleting destructor'(this, v6);
  }
  else if ( a2 )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 17), *((HANDLE *)this + 16), 0);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v7);
}

```

## disassembly

```asm
0x18009f0b8  mov     [rsp+arg_8], rbx
0x18009f0bd  mov     [rsp+arg_10], rsi
0x18009f0c2  push    rdi
0x18009f0c3  sub     rsp, 20h
0x18009f0c7  lea     rbx, [rcx+98h]
0x18009f0ce  mov     rdi, rcx
0x18009f0d1  mov     rcx, rbx; SRWLock
0x18009f0d4  mov     sil, dl
0x18009f0d7  call    cs:__imp_AcquireSRWLockExclusive
0x18009f0dd  or      eax, 0FFFFFFFFh
0x18009f0e0  mov     [rsp+28h+arg_0], rbx
0x18009f0e5  lock xadd [rdi+94h], eax
0x18009f0ed  cmp     eax, 1
0x18009f0f0  jnz     short loc_18009F125
0x18009f0f2  mov     rcx, [rdi+88h]; pwa
0x18009f0f9  mov     qword ptr [rdi+88h], 0
0x18009f104  call    cs:__imp_CloseThreadpoolWait
0x18009f10a  xor     edx, edx
0x18009f10c  lea     rcx, [rsp+28h+arg_0]
0x18009f111  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x18009f116  test    rdi, rdi
0x18009f119  jz      short loc_18009F141
0x18009f11b  mov     rcx, rdi; this
0x18009f11e  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x18009f123  jmp     short loc_18009F141
0x18009f125  test    sil, sil
0x18009f128  jz      short loc_18009F141
0x18009f12a  mov     rdx, [rdi+80h]; h
0x18009f131  xor     r8d, r8d; pftTimeout
0x18009f134  mov     rcx, [rdi+88h]; pwa
0x18009f13b  call    cs:__imp_SetThreadpoolWait
0x18009f141  lea     rcx, [rsp+28h+arg_0]
0x18009f146  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18009f14b  mov     rbx, [rsp+28h+arg_8]
0x18009f150  mov     rsi, [rsp+28h+arg_10]
0x18009f155  add     rsp, 20h
0x18009f159  pop     rdi
0x18009f15a  retn
```
