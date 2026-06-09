# wil::details::registry_watcher_state::ReleaseFromCallback(bool)

- ea: `0x1800f82f4`
- end: `0x1800f83b3`
- name: `?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z`
- size: `191`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x1800f8610`

## callees

- `0x18005f560`
- `0x1800efd64`
- `0x1800f82f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f8350`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f839d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f8350`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f839d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f8312`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f8312`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f8358`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f8358`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f8345`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f8345`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800f838f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800f838f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800f833a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800f833a`

## pseudocode

```c
void __fastcall wil::details::registry_watcher_state::ReleaseFromCallback(
        wil::details::registry_watcher_state *this,
        char a2)
{
  RTL_SRWLOCK *v2; // rsi
  struct _TP_WAIT *v5; // rcx
  DWORD LastError; // ebx

  v2 = (RTL_SRWLOCK *)((char *)this + 152);
  AcquireSRWLockExclusive((PSRWLOCK)this + 19);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 37, 0xFFFFFFFF) == 1 )
  {
    v5 = (struct _TP_WAIT *)*((_QWORD *)this + 17);
    *((_QWORD *)this + 17) = 0;
    CloseThreadpoolWait(v5);
    if ( v2 )
    {
      LastError = GetLastError();
      ReleaseSRWLockExclusive(v2);
      SetLastError(LastError);
    }
    if ( this )
    {
      wil::details::registry_watcher_state::~registry_watcher_state(this);
      operator delete(this, (const struct std::nothrow_t *)0xA0);
    }
  }
  else
  {
    if ( a2 )
      SetThreadpoolWait(*((PTP_WAIT *)this + 17), *((HANDLE *)this + 16), 0);
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
  }
}

```

## disassembly

```asm
0x1800f82f4  mov     [rsp+arg_0], rbx
0x1800f82f9  mov     [rsp+arg_8], rsi
0x1800f82fe  push    rdi
0x1800f82ff  sub     rsp, 20h
0x1800f8303  lea     rsi, [rcx+98h]
0x1800f830a  mov     rdi, rcx
0x1800f830d  mov     rcx, rsi; SRWLock
0x1800f8310  mov     bl, dl
0x1800f8312  call    cs:__imp_AcquireSRWLockExclusive
0x1800f8318  or      eax, 0FFFFFFFFh
0x1800f831b  lock xadd [rdi+94h], eax
0x1800f8323  cmp     eax, 1
0x1800f8326  jnz     short loc_1800F837A
0x1800f8328  mov     rcx, [rdi+88h]; pwa
0x1800f832f  mov     qword ptr [rdi+88h], 0
0x1800f833a  call    cs:__imp_CloseThreadpoolWait
0x1800f8340  test    rsi, rsi
0x1800f8343  jz      short loc_1800F835E
0x1800f8345  call    cs:__imp_GetLastError
0x1800f834b  mov     rcx, rsi; SRWLock
0x1800f834e  mov     ebx, eax
0x1800f8350  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f8356  mov     ecx, ebx; dwErrCode
0x1800f8358  call    cs:__imp_SetLastError
0x1800f835e  test    rdi, rdi
0x1800f8361  jz      short loc_1800F83A3
0x1800f8363  mov     rcx, rdi; this
0x1800f8366  call    ??1registry_watcher_state@details@wil@@QEAA@XZ; wil::details::registry_watcher_state::~registry_watcher_state(void)
0x1800f836b  mov     edx, 0A0h; struct std::nothrow_t *
0x1800f8370  mov     rcx, rdi; void *
0x1800f8373  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f8378  jmp     short loc_1800F83A3
0x1800f837a  test    bl, bl
0x1800f837c  jz      short loc_1800F8395
0x1800f837e  mov     rdx, [rdi+80h]; h
0x1800f8385  xor     r8d, r8d; pftTimeout
0x1800f8388  mov     rcx, [rdi+88h]; pwa
0x1800f838f  call    cs:__imp_SetThreadpoolWait
0x1800f8395  test    rsi, rsi
0x1800f8398  jz      short loc_1800F83A3
0x1800f839a  mov     rcx, rsi; SRWLock
0x1800f839d  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f83a3  mov     rbx, [rsp+28h+arg_0]
0x1800f83a8  mov     rsi, [rsp+28h+arg_8]
0x1800f83ad  add     rsp, 20h
0x1800f83b1  pop     rdi
0x1800f83b2  retn
```
