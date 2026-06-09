# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x140016b1c`
- end: `0x140016bd3`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `183`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000d7c0`
- `0x14001003c`
- `0x140013bd0`
- `0x140013c00`

## callees

- `0x14000a6ac`
- `0x140013f04`
- `0x140016b1c`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140016b32`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140016b32`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140016b70`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140016b70`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140016ba1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140016ba1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140016b62`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140016b62`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::OnSignaled(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)
{
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rbx
  void (__fastcall *v6)(__int64); // rbp
  __int64 v7; // r15
  char *v8; // rdx
  LPCRITICAL_SECTION v9; // [rsp+60h] [rbp+8h] BYREF

  AcquireSRWLockShared(SRWLock);
  v9 = (LPCRITICAL_SECTION)SRWLock;
  v4 = (*(_QWORD *)&lpCriticalSection[1].LockCount - (unsigned __int64)lpCriticalSection[1].DebugInfo) >> 4;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  v5 = 0;
  while ( v5 < v4 )
  {
    v6 = 0;
    v7 = 0;
    EnterCriticalSection(lpCriticalSection);
    v9 = lpCriticalSection;
    AcquireSRWLockExclusive(SRWLock);
    while ( v5 < v4 )
    {
      v8 = (char *)lpCriticalSection[1].DebugInfo + 16 * v5++;
      if ( *(_QWORD *)v8 )
      {
        v6 = *(void (__fastcall **)(__int64))v8;
        v7 = *((_QWORD *)v8 + 1);
        break;
      }
    }
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    if ( v6 )
      v6(v7);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v9);
  }
}

```

## disassembly

```asm
0x140016b1c  push    rbx
0x140016b1e  push    rbp
0x140016b1f  push    rsi
0x140016b20  push    rdi
0x140016b21  push    r14
0x140016b23  push    r15
0x140016b25  sub     rsp, 28h
0x140016b29  mov     rsi, rdx
0x140016b2c  mov     r14, rcx
0x140016b2f  mov     rcx, rdx; SRWLock
0x140016b32  call    cs:__imp_AcquireSRWLockShared
0x140016b38  mov     [rsp+58h+arg_0], rsi
0x140016b3d  mov     rdi, [r14+30h]
0x140016b41  sub     rdi, [r14+28h]
0x140016b45  shr     rdi, 4
0x140016b49  lea     rcx, [rsp+58h+arg_0]
0x140016b4e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140016b53  xor     ebx, ebx
0x140016b55  test    rdi, rdi
0x140016b58  jz      short loc_140016BC6
0x140016b5a  xor     ebp, ebp
0x140016b5c  xor     r15d, r15d
0x140016b5f  mov     rcx, r14; lpCriticalSection
0x140016b62  call    cs:__imp_EnterCriticalSection
0x140016b68  mov     [rsp+58h+arg_0], r14
0x140016b6d  mov     rcx, rsi; SRWLock
0x140016b70  call    cs:__imp_AcquireSRWLockExclusive
0x140016b76  cmp     rbx, rdi
0x140016b79  jnb     short loc_140016B99
0x140016b7b  lea     rcx, [rbx+1]
0x140016b7f  shl     rbx, 4
0x140016b83  mov     rdx, [r14+28h]
0x140016b87  add     rdx, rbx
0x140016b8a  mov     rbx, rcx
0x140016b8d  cmp     [rdx], rbp
0x140016b90  jz      short loc_140016B76
0x140016b92  mov     rbp, [rdx]
0x140016b95  mov     r15, [rdx+8]
0x140016b99  test    rsi, rsi
0x140016b9c  jz      short loc_140016BA7
0x140016b9e  mov     rcx, rsi; SRWLock
0x140016ba1  call    cs:__imp_ReleaseSRWLockExclusive
0x140016ba7  test    rbp, rbp
0x140016baa  jz      short loc_140016BB7
0x140016bac  mov     rcx, r15
0x140016baf  mov     rax, rbp
0x140016bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016bb7  lea     rcx, [rsp+58h+arg_0]
0x140016bbc  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140016bc1  cmp     rbx, rdi
0x140016bc4  jb      short loc_140016B5A
0x140016bc6  add     rsp, 28h
0x140016bca  pop     r15
0x140016bcc  pop     r14
0x140016bce  pop     rdi
0x140016bcf  pop     rsi
0x140016bd0  pop     rbp
0x140016bd1  pop     rbx
0x140016bd2  retn
```
