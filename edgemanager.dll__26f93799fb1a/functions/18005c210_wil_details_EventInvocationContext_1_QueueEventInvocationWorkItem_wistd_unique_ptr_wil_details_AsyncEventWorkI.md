# wil::details::EventInvocationContext<1>::QueueEventInvocationWorkItem(wistd::unique_ptr<wil::details::AsyncEventWorkItemBase,wistd::default_delete<wil::details::AsyncEventWorkItemBase>> &&)

- ea: `0x18005c210`
- end: `0x18005c280`
- name: `?QueueEventInvocationWorkItem@?$EventInvocationContext@$00@details@wil@@UEAAX$$QEAV?$unique_ptr@UAsyncEventWorkItemBase@details@wil@@U?$default_delete@UAsyncEventWorkItemBase@details@wil@@@wistd@@@wistd@@@Z`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1800212d4`
- `0x18005b6a4`
- `0x18005c210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005c22c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005c22c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18005c25c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18005c25c`

## pseudocode

```c
__int64 __fastcall wil::details::EventInvocationContext<1>::QueueEventInvocationWorkItem(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v5; // rcx
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  v2 = a1 + 88;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 88));
  v5 = *(_QWORD *)(a1 + 104);
  v7 = v2;
  wistd::unique_ptr<wil::details::AsyncEventWorkItemBase,wistd::default_delete<wil::details::AsyncEventWorkItemBase>>::operator=(
    v5,
    a2);
  *(_QWORD *)(a1 + 104) = **(_QWORD **)(a1 + 104) + 8LL;
  if ( !*(_BYTE *)(a1 + 64) )
  {
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 80));
    *(_BYTE *)(a1 + 64) = 1;
  }
  return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v7);
}

```

## disassembly

```asm
0x18005c210  mov     [rsp+arg_8], rbx
0x18005c215  mov     [rsp+arg_10], rsi
0x18005c21a  push    rdi
0x18005c21b  sub     rsp, 20h
0x18005c21f  lea     rbx, [rcx+58h]
0x18005c223  mov     rsi, rcx
0x18005c226  mov     rcx, rbx; SRWLock
0x18005c229  mov     rdi, rdx
0x18005c22c  call    cs:__imp_AcquireSRWLockExclusive
0x18005c232  mov     rcx, [rsi+68h]
0x18005c236  mov     rdx, rdi
0x18005c239  mov     [rsp+28h+arg_0], rbx
0x18005c23e  call    ??4?$unique_ptr@UAsyncEventWorkItemBase@details@wil@@U?$default_delete@UAsyncEventWorkItemBase@details@wil@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<wil::details::AsyncEventWorkItemBase,wistd::default_delete<wil::details::AsyncEventWorkItemBase>>::operator=(wistd::unique_ptr<wil::details::AsyncEventWorkItemBase,wistd::default_delete<wil::details::AsyncEventWorkItemBase>> &&)
0x18005c243  mov     rax, [rsi+68h]
0x18005c247  mov     rdx, [rax]
0x18005c24a  add     rdx, 8
0x18005c24e  mov     [rsi+68h], rdx
0x18005c252  cmp     byte ptr [rsi+40h], 0
0x18005c256  jnz     short loc_18005C266
0x18005c258  mov     rcx, [rsi+50h]; pwk
0x18005c25c  call    cs:__imp_SubmitThreadpoolWork
0x18005c262  mov     byte ptr [rsi+40h], 1
0x18005c266  lea     rcx, [rsp+28h+arg_0]
0x18005c26b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005c270  mov     rbx, [rsp+28h+arg_8]
0x18005c275  mov     rsi, [rsp+28h+arg_10]
0x18005c27a  add     rsp, 20h
0x18005c27e  pop     rdi
0x18005c27f  retn
```
