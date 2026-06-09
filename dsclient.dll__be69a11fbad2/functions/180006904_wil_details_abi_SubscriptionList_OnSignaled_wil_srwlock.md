# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180006904`
- end: `0x1800069ca`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `198`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180003cd0`
- `0x180003d00`
- `0x180005598`

## callees

- `0x1800048d8`
- `0x1800048f8`
- `0x180004918`
- `0x180006904`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000694d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000694d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000691d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000691d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000695b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000695b`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::OnSignaled(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)
{
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rbx
  void (__fastcall *v6)(__int64); // rbp
  __int64 v7; // r15
  unsigned __int64 v8; // rax
  WORD *v9; // rcx
  RTL_SRWLOCK *v10; // [rsp+50h] [rbp+8h] BYREF
  LPCRITICAL_SECTION v11; // [rsp+58h] [rbp+10h] BYREF

  AcquireSRWLockShared(SRWLock);
  v4 = (*(_QWORD *)&lpCriticalSection[1].LockCount - (unsigned __int64)lpCriticalSection[1].DebugInfo) >> 4;
  v10 = SRWLock;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  v5 = 0;
  while ( v5 < v4 )
  {
    v6 = 0;
    v7 = 0;
    EnterCriticalSection(lpCriticalSection);
    v11 = lpCriticalSection;
    AcquireSRWLockExclusive(SRWLock);
    v10 = SRWLock;
    if ( v5 < v4 )
    {
      while ( 1 )
      {
        v8 = v5 + 1;
        v9 = &lpCriticalSection[1].DebugInfo->Type + 8 * v5++;
        if ( *(_QWORD *)v9 )
          break;
        if ( v8 >= v4 )
          goto LABEL_7;
      }
      v6 = *(void (__fastcall **)(__int64))v9;
      v7 = *((_QWORD *)v9 + 1);
    }
LABEL_7:
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
    if ( v6 )
      v6(v7);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x180006904  mov     [rsp+arg_10], rbx
0x180006909  push    rbp
0x18000690a  push    rsi
0x18000690b  push    rdi
0x18000690c  push    r14
0x18000690e  push    r15
0x180006910  sub     rsp, 20h
0x180006914  mov     rsi, rcx
0x180006917  mov     r14, rdx
0x18000691a  mov     rcx, rdx; SRWLock
0x18000691d  call    cs:__imp_AcquireSRWLockShared
0x180006923  mov     rdi, [rsi+30h]
0x180006927  lea     rcx, [rsp+48h+arg_0]
0x18000692c  sub     rdi, [rsi+28h]
0x180006930  shr     rdi, 4
0x180006934  mov     [rsp+48h+arg_0], r14
0x180006939  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000693e  xor     ebx, ebx
0x180006940  test    rdi, rdi
0x180006943  jz      short loc_1800069B9
0x180006945  mov     rcx, rsi; lpCriticalSection
0x180006948  xor     ebp, ebp
0x18000694a  xor     r15d, r15d
0x18000694d  call    cs:__imp_EnterCriticalSection
0x180006953  mov     rcx, r14; SRWLock
0x180006956  mov     [rsp+48h+arg_8], rsi
0x18000695b  call    cs:__imp_AcquireSRWLockExclusive
0x180006961  mov     [rsp+48h+arg_0], r14
0x180006966  cmp     rbx, rdi
0x180006969  jnb     short loc_180006990
0x18000696b  mov     rdx, [rsi+28h]
0x18000696f  lea     rax, [rbx+1]
0x180006973  add     rbx, rbx
0x180006976  lea     rcx, [rdx+rbx*8]
0x18000697a  mov     rbx, rax
0x18000697d  cmp     [rcx], rbp
0x180006980  jnz     short loc_180006989
0x180006982  cmp     rax, rdi
0x180006985  jb      short loc_18000696F
0x180006987  jmp     short loc_180006990
0x180006989  mov     rbp, [rcx]
0x18000698c  mov     r15, [rcx+8]
0x180006990  lea     rcx, [rsp+48h+arg_0]
0x180006995  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000699a  test    rbp, rbp
0x18000699d  jz      short loc_1800069AA
0x18000699f  mov     rcx, r15
0x1800069a2  mov     rax, rbp
0x1800069a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069aa  lea     rcx, [rsp+48h+arg_8]
0x1800069af  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800069b4  cmp     rbx, rdi
0x1800069b7  jb      short loc_180006945
0x1800069b9  mov     rbx, [rsp+48h+arg_10]
0x1800069be  add     rsp, 20h
0x1800069c2  pop     r15
0x1800069c4  pop     r14
0x1800069c6  pop     rdi
0x1800069c7  pop     rsi
0x1800069c8  pop     rbp
0x1800069c9  retn
```
