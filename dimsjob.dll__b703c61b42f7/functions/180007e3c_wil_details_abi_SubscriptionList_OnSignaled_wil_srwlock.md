# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180007e3c`
- end: `0x180007efb`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `191`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180004f20`
- `0x180004f50`
- `0x1800063b4`

## callees

- `0x180003620`
- `0x180005a3c`
- `0x180005a5c`
- `0x180007e3c`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007e93`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007e93`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007e55`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007e55`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007e85`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007e85`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::OnSignaled(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)
{
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rbx
  void (__fastcall *v6)(__int64); // rsi
  __int64 v7; // r15
  char *v8; // rdx
  RTL_SRWLOCK *v9; // [rsp+50h] [rbp+8h] BYREF
  LPCRITICAL_SECTION v10; // [rsp+58h] [rbp+10h] BYREF

  AcquireSRWLockShared(SRWLock);
  v9 = SRWLock;
  v4 = (*(_QWORD *)&lpCriticalSection[1].LockCount - (unsigned __int64)lpCriticalSection[1].DebugInfo) >> 4;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  v5 = 0;
  while ( v5 < v4 )
  {
    v6 = 0;
    v7 = 0;
    EnterCriticalSection(lpCriticalSection);
    v10 = lpCriticalSection;
    AcquireSRWLockExclusive(SRWLock);
    v9 = SRWLock;
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
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
    if ( v6 )
      v6(v7);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x180007e3c  mov     [rsp+arg_10], rbx
0x180007e41  push    rbp
0x180007e42  push    rsi
0x180007e43  push    rdi
0x180007e44  push    r14
0x180007e46  push    r15
0x180007e48  sub     rsp, 20h
0x180007e4c  mov     r14, rdx
0x180007e4f  mov     rbp, rcx
0x180007e52  mov     rcx, rdx; SRWLock
0x180007e55  call    cs:__imp_AcquireSRWLockShared
0x180007e5b  mov     [rsp+48h+arg_0], r14
0x180007e60  mov     rdi, [rbp+30h]
0x180007e64  sub     rdi, [rbp+28h]
0x180007e68  shr     rdi, 4
0x180007e6c  lea     rcx, [rsp+48h+arg_0]
0x180007e71  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180007e76  xor     ebx, ebx
0x180007e78  test    rdi, rdi
0x180007e7b  jz      short loc_180007EEA
0x180007e7d  xor     esi, esi
0x180007e7f  xor     r15d, r15d
0x180007e82  mov     rcx, rbp; lpCriticalSection
0x180007e85  call    cs:__imp_EnterCriticalSection
0x180007e8b  mov     [rsp+48h+arg_8], rbp
0x180007e90  mov     rcx, r14; SRWLock
0x180007e93  call    cs:__imp_AcquireSRWLockExclusive
0x180007e99  mov     [rsp+48h+arg_0], r14
0x180007e9e  cmp     rbx, rdi
0x180007ea1  jnb     short loc_180007EC1
0x180007ea3  lea     rcx, [rbx+1]
0x180007ea7  shl     rbx, 4
0x180007eab  mov     rdx, [rbp+28h]
0x180007eaf  add     rdx, rbx
0x180007eb2  mov     rbx, rcx
0x180007eb5  cmp     [rdx], rsi
0x180007eb8  jz      short loc_180007E9E
0x180007eba  mov     rsi, [rdx]
0x180007ebd  mov     r15, [rdx+8]
0x180007ec1  lea     rcx, [rsp+48h+arg_0]
0x180007ec6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180007ecb  test    rsi, rsi
0x180007ece  jz      short loc_180007EDB
0x180007ed0  mov     rcx, r15
0x180007ed3  mov     rax, rsi
0x180007ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007edb  lea     rcx, [rsp+48h+arg_8]
0x180007ee0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180007ee5  cmp     rbx, rdi
0x180007ee8  jb      short loc_180007E7D
0x180007eea  mov     rbx, [rsp+48h+arg_10]
0x180007eef  add     rsp, 20h
0x180007ef3  pop     r15
0x180007ef5  pop     r14
0x180007ef7  pop     rdi
0x180007ef8  pop     rsi
0x180007ef9  pop     rbp
0x180007efa  retn
```
