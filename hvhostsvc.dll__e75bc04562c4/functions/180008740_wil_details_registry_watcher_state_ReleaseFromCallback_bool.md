# wil::details::registry_watcher_state::ReleaseFromCallback(bool)

- ea: `0x180008740`
- end: `0x1800087ec`
- name: `?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z`
- size: `172`
- prototype: `void __fastcall(wil::details::registry_watcher_state *this, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180008a50`

## callees

- `0x180008464`
- `0x180008740`
- `0x180008e1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000875f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000875f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800087d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800087d6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800087c8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800087c8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000878c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000878c`

## pseudocode

```c
void __fastcall wil::details::registry_watcher_state::ReleaseFromCallback(
        wil::details::registry_watcher_state *this,
        char a2)
{
  RTL_SRWLOCK *v2; // rbx
  struct _TP_WAIT *v5; // rcx
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
      wil::details::registry_watcher_state::`scalar deleting destructor'(this);
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
0x180008740  mov     [rsp+arg_8], rbx
0x180008745  mov     [rsp+arg_10], rsi
0x18000874a  push    rdi
0x18000874b  sub     rsp, 20h
0x18000874f  lea     rbx, [rcx+98h]
0x180008756  mov     rdi, rcx
0x180008759  mov     rcx, rbx; SRWLock
0x18000875c  mov     sil, dl
0x18000875f  call    cs:__imp_AcquireSRWLockExclusive
0x180008765  or      eax, 0FFFFFFFFh
0x180008768  mov     [rsp+28h+SRWLock], rbx
0x18000876d  lock xadd [rdi+94h], eax
0x180008775  cmp     eax, 1
0x180008778  jnz     short loc_1800087B2
0x18000877a  mov     rcx, [rdi+88h]; pwa
0x180008781  mov     qword ptr [rdi+88h], 0
0x18000878c  call    cs:__imp_CloseThreadpoolWait
0x180008792  xor     edx, edx
0x180008794  lea     rcx, [rsp+28h+SRWLock]
0x180008799  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x18000879e  test    rdi, rdi
0x1800087a1  jz      short loc_1800087AB
0x1800087a3  mov     rcx, rdi; this
0x1800087a6  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x1800087ab  mov     rbx, [rsp+28h+SRWLock]
0x1800087b0  jmp     short loc_1800087CE
0x1800087b2  test    sil, sil
0x1800087b5  jz      short loc_1800087CE
0x1800087b7  mov     rdx, [rdi+80h]; h
0x1800087be  xor     r8d, r8d; pftTimeout
0x1800087c1  mov     rcx, [rdi+88h]; pwa
0x1800087c8  call    cs:__imp_SetThreadpoolWait
0x1800087ce  test    rbx, rbx
0x1800087d1  jz      short loc_1800087DC
0x1800087d3  mov     rcx, rbx; SRWLock
0x1800087d6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800087dc  mov     rbx, [rsp+28h+arg_8]
0x1800087e1  mov     rsi, [rsp+28h+arg_10]
0x1800087e6  add     rsp, 20h
0x1800087ea  pop     rdi
0x1800087eb  retn
```
