# wil::details::registry_watcher_state::ReleaseFromCallback(bool)

- ea: `0x1800214dc`
- end: `0x180021588`
- name: `?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z`
- size: `172`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800257b0`

## callees

- `0x180016398`
- `0x1800214dc`
- `0x18003ad34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800214fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800214fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021572`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021572`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180021564`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180021564`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180021528`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180021528`

## pseudocode

```c
void __fastcall wil::details::registry_watcher_state::ReleaseFromCallback(
        wil::details::registry_watcher_state *this,
        char a2)
{
  RTL_SRWLOCK *v2; // rbx
  struct _TP_WAIT *v5; // rcx
  unsigned int v6; // edx
  PSRWLOCK SRWLock; // [rsp+30h] [rbp+8h] BYREF

  v2 = (RTL_SRWLOCK *)((char *)this + 152);
  AcquireSRWLockExclusive((PSRWLOCK)this + 19);
  SRWLock = v2;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 37, 0xFFFFFFFF) == 1 )
  {
    v5 = (struct _TP_WAIT *)*((_QWORD *)this + 17);
    *((_QWORD *)this + 17) = 0;
    CloseThreadpoolWait(v5);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
      &SRWLock,
      0);
    if ( this )
      wil::details::registry_watcher_state::`scalar deleting destructor'(this, v6);
    v2 = SRWLock;
  }
  else if ( a2 )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 17), *((HANDLE *)this + 16), 0);
  }
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
}

```

## disassembly

```asm
0x1800214dc  mov     [rsp+arg_8], rbx
0x1800214e1  mov     [rsp+arg_10], rsi
0x1800214e6  push    rdi
0x1800214e7  sub     rsp, 20h
0x1800214eb  lea     rbx, [rcx+98h]
0x1800214f2  mov     rdi, rcx
0x1800214f5  mov     rcx, rbx; SRWLock
0x1800214f8  mov     sil, dl
0x1800214fb  call    cs:__imp_AcquireSRWLockExclusive
0x180021501  or      eax, 0FFFFFFFFh
0x180021504  mov     [rsp+28h+SRWLock], rbx
0x180021509  lock xadd [rdi+94h], eax
0x180021511  cmp     eax, 1
0x180021514  jnz     short loc_18002154E
0x180021516  mov     rcx, [rdi+88h]; pwa
0x18002151d  mov     qword ptr [rdi+88h], 0
0x180021528  call    cs:__imp_CloseThreadpoolWait
0x18002152e  xor     edx, edx
0x180021530  lea     rcx, [rsp+28h+SRWLock]
0x180021535  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x18002153a  test    rdi, rdi
0x18002153d  jz      short loc_180021547
0x18002153f  mov     rcx, rdi; this
0x180021542  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x180021547  mov     rbx, [rsp+28h+SRWLock]
0x18002154c  jmp     short loc_18002156A
0x18002154e  test    sil, sil
0x180021551  jz      short loc_18002156A
0x180021553  mov     rdx, [rdi+80h]; h
0x18002155a  xor     r8d, r8d; pftTimeout
0x18002155d  mov     rcx, [rdi+88h]; pwa
0x180021564  call    cs:__imp_SetThreadpoolWait
0x18002156a  test    rbx, rbx
0x18002156d  jz      short loc_180021578
0x18002156f  mov     rcx, rbx; SRWLock
0x180021572  call    cs:__imp_ReleaseSRWLockExclusive
0x180021578  mov     rbx, [rsp+28h+arg_8]
0x18002157d  mov     rsi, [rsp+28h+arg_10]
0x180021582  add     rsp, 20h
0x180021586  pop     rdi
0x180021587  retn
```
