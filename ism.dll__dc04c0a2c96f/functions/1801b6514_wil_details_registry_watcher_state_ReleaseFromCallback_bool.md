# wil::details::registry_watcher_state::ReleaseFromCallback(bool)

- ea: `0x1801b6514`
- end: `0x1801b65b7`
- name: `?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z`
- size: `163`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1801b6ed0`

## callees

- `0x180055b40`
- `0x1800cb270`
- `0x1801b6514`
- `0x1801b6f88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801b6533`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801b6533`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1801b6597`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1801b6597`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1801b6560`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1801b6560`

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
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v7);
}

```

## disassembly

```asm
0x1801b6514  mov     [rsp+arg_8], rbx
0x1801b6519  mov     [rsp+arg_10], rsi
0x1801b651e  push    rdi
0x1801b651f  sub     rsp, 20h
0x1801b6523  lea     rbx, [rcx+98h]
0x1801b652a  mov     rdi, rcx
0x1801b652d  mov     rcx, rbx; SRWLock
0x1801b6530  mov     sil, dl
0x1801b6533  call    cs:__imp_AcquireSRWLockExclusive
0x1801b6539  or      eax, 0FFFFFFFFh
0x1801b653c  mov     [rsp+28h+arg_0], rbx
0x1801b6541  lock xadd [rdi+94h], eax
0x1801b6549  cmp     eax, 1
0x1801b654c  jnz     short loc_1801B6581
0x1801b654e  mov     rcx, [rdi+88h]; pwa
0x1801b6555  mov     qword ptr [rdi+88h], 0
0x1801b6560  call    cs:__imp_CloseThreadpoolWait
0x1801b6566  xor     edx, edx
0x1801b6568  lea     rcx, [rsp+28h+arg_0]
0x1801b656d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x1801b6572  test    rdi, rdi
0x1801b6575  jz      short loc_1801B659D
0x1801b6577  mov     rcx, rdi; this
0x1801b657a  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x1801b657f  jmp     short loc_1801B659D
0x1801b6581  test    sil, sil
0x1801b6584  jz      short loc_1801B659D
0x1801b6586  mov     rdx, [rdi+80h]; h
0x1801b658d  xor     r8d, r8d; pftTimeout
0x1801b6590  mov     rcx, [rdi+88h]; pwa
0x1801b6597  call    cs:__imp_SetThreadpoolWait
0x1801b659d  lea     rcx, [rsp+28h+arg_0]
0x1801b65a2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1801b65a7  mov     rbx, [rsp+28h+arg_8]
0x1801b65ac  mov     rsi, [rsp+28h+arg_10]
0x1801b65b1  add     rsp, 20h
0x1801b65b5  pop     rdi
0x1801b65b6  retn
```
