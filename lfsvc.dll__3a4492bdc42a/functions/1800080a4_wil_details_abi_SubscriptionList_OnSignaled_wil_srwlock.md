# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x1800080a4`
- end: `0x180008163`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `191`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180004dd0`
- `0x180004e00`
- `0x180006ad8`

## callees

- `0x18000336c`
- `0x180005f80`
- `0x180005fa0`
- `0x1800080a4`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800080ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800080ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800080bd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800080bd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800080fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800080fb`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::OnSignaled(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)
{
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rbx
  void (__fastcall *v6)(__int64); // rsi
  __int64 v7; // r15
  char *v8; // rdx
  RTL_SRWLOCK *v9; // [rsp+20h] [rbp-38h] BYREF
  LPCRITICAL_SECTION v10[6]; // [rsp+28h] [rbp-30h] BYREF

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
    v10[0] = lpCriticalSection;
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
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v10);
  }
}

```

## disassembly

```asm
0x1800080a4  mov     [rsp+arg_10], rbx
0x1800080a9  push    rbp
0x1800080aa  push    rsi
0x1800080ab  push    rdi
0x1800080ac  push    r14
0x1800080ae  push    r15
0x1800080b0  sub     rsp, 30h
0x1800080b4  mov     r14, rdx
0x1800080b7  mov     rbp, rcx
0x1800080ba  mov     rcx, rdx; SRWLock
0x1800080bd  call    cs:__imp_AcquireSRWLockShared
0x1800080c3  mov     [rsp+58h+var_38], r14
0x1800080c8  mov     rdi, [rbp+30h]
0x1800080cc  sub     rdi, [rbp+28h]
0x1800080d0  shr     rdi, 4
0x1800080d4  lea     rcx, [rsp+58h+var_38]
0x1800080d9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800080de  xor     ebx, ebx
0x1800080e0  test    rdi, rdi
0x1800080e3  jz      short loc_180008152
0x1800080e5  xor     esi, esi
0x1800080e7  xor     r15d, r15d
0x1800080ea  mov     rcx, rbp; lpCriticalSection
0x1800080ed  call    cs:__imp_EnterCriticalSection
0x1800080f3  mov     [rsp+58h+var_30], rbp
0x1800080f8  mov     rcx, r14; SRWLock
0x1800080fb  call    cs:__imp_AcquireSRWLockExclusive
0x180008101  mov     [rsp+58h+var_38], r14
0x180008106  cmp     rbx, rdi
0x180008109  jnb     short loc_180008129
0x18000810b  lea     rcx, [rbx+1]
0x18000810f  shl     rbx, 4
0x180008113  mov     rdx, [rbp+28h]
0x180008117  add     rdx, rbx
0x18000811a  mov     rbx, rcx
0x18000811d  cmp     [rdx], rsi
0x180008120  jz      short loc_180008106
0x180008122  mov     rsi, [rdx]
0x180008125  mov     r15, [rdx+8]
0x180008129  lea     rcx, [rsp+58h+var_38]
0x18000812e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180008133  test    rsi, rsi
0x180008136  jz      short loc_180008143
0x180008138  mov     rcx, r15
0x18000813b  mov     rax, rsi
0x18000813e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008143  lea     rcx, [rsp+58h+var_30]
0x180008148  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000814d  cmp     rbx, rdi
0x180008150  jb      short loc_1800080E5
0x180008152  mov     rbx, [rsp+58h+arg_10]
0x180008157  add     rsp, 30h
0x18000815b  pop     r15
0x18000815d  pop     r14
0x18000815f  pop     rdi
0x180008160  pop     rsi
0x180008161  pop     rbp
0x180008162  retn
```
