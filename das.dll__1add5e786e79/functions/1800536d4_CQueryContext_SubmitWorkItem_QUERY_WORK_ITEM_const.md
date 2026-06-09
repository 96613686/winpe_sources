# CQueryContext::SubmitWorkItem(_QUERY_WORK_ITEM const &)

- ea: `0x1800536d4`
- end: `0x180053793`
- name: `?SubmitWorkItem@CQueryContext@@IEAAJAEBU_QUERY_WORK_ITEM@@@Z`
- size: `191`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, const struct _QUERY_WORK_ITEM *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180026e30`
- `0x1800272ec`
- `0x1800529dc`

## callees

- `0x180024e58`
- `0x18002db04`
- `0x1800536d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053760`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053760`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180053750`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180053750`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800536f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800536f3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180053774`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180053774`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CQueryContext::SubmitWorkItem(PSRWLOCK SRWLock, const struct _QUERY_WORK_ITEM *a2)
{
  PSRWLOCK v4; // rbx
  _OWORD *Ptr; // rdx
  const char *v6; // r9
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  PSRWLOCK v9; // [rsp+30h] [rbp+8h] BYREF

  v4 = SRWLock + 72;
  EnterCriticalSection((LPCRITICAL_SECTION)&SRWLock[72]);
  try
  {
    v9 = v4;
    Ptr = SRWLock[78].Ptr;
    if ( Ptr == SRWLock[79].Ptr )
    {
      std::vector<_QUERY_WORK_ITEM>::_Emplace_reallocate<_QUERY_WORK_ITEM const &>(&SRWLock[77], Ptr, a2);
    }
    else
    {
      *Ptr = *(_OWORD *)a2;
      Ptr[1] = *((_OWORD *)a2 + 1);
      Ptr[2] = *((_OWORD *)a2 + 2);
      Ptr[3] = *((_OWORD *)a2 + 3);
      SRWLock[78].Ptr = (char *)SRWLock[78].Ptr + 64;
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v9);
    if ( *((_DWORD *)a2 + 4) == 1 )
    {
      AcquireSRWLockExclusive(SRWLock);
      LODWORD(SRWLock[1].Ptr) = 1;
      ReleaseSRWLockExclusive(SRWLock);
    }
    _InterlockedIncrement((volatile signed __int32 *)&SRWLock[56].Ptr + 1);
    SubmitThreadpoolWork((PTP_WORK)SRWLock[71].Ptr);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x9F8,
                           (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\querycontext.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x1800536d4  mov     [rsp+arg_8], rbx
0x1800536d9  mov     [rsp+arg_10], rsi
0x1800536de  push    rdi
0x1800536df  sub     rsp, 20h
0x1800536e3  mov     rsi, rdx
0x1800536e6  mov     rdi, rcx
0x1800536e9  lea     rbx, [rcx+240h]
0x1800536f0  mov     rcx, rbx; lpCriticalSection
0x1800536f3  call    cs:__imp_EnterCriticalSection
0x1800536f9  mov     [rsp+28h+arg_0], rbx
0x1800536fe  lea     rcx, [rdi+268h]
0x180053705  mov     rdx, [rcx+8]
0x180053709  cmp     rdx, [rcx+10h]
0x18005370d  jz      short loc_180053734
0x18005370f  movaps  xmm0, xmmword ptr [rsi]
0x180053712  movaps  xmmword ptr [rdx], xmm0
0x180053715  movaps  xmm1, xmmword ptr [rsi+10h]
0x180053719  movaps  xmmword ptr [rdx+10h], xmm1
0x18005371d  movaps  xmm0, xmmword ptr [rsi+20h]
0x180053721  movaps  xmmword ptr [rdx+20h], xmm0
0x180053725  movaps  xmm1, xmmword ptr [rsi+30h]
0x180053729  movaps  xmmword ptr [rdx+30h], xmm1
0x18005372d  add     qword ptr [rcx+8], 40h ; '@'
0x180053732  jmp     short loc_18005373D
0x180053734  mov     r8, rsi
0x180053737  call    ??$_Emplace_reallocate@AEBU_QUERY_WORK_ITEM@@@?$vector@U_QUERY_WORK_ITEM@@V?$allocator@U_QUERY_WORK_ITEM@@@std@@@std@@AEAAPEAU_QUERY_WORK_ITEM@@QEAU2@AEBU2@@Z; std::vector<_QUERY_WORK_ITEM>::_Emplace_reallocate<_QUERY_WORK_ITEM const &>(_QUERY_WORK_ITEM * const,_QUERY_WORK_ITEM const &)
0x18005373c  nop
0x18005373d  lea     rcx, [rsp+28h+arg_0]
0x180053742  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180053747  cmp     dword ptr [rsi+10h], 1
0x18005374b  jnz     short loc_180053766
0x18005374d  mov     rcx, rdi; SRWLock
0x180053750  call    cs:__imp_AcquireSRWLockExclusive
0x180053756  mov     dword ptr [rdi+8], 1
0x18005375d  mov     rcx, rdi; SRWLock
0x180053760  call    cs:__imp_ReleaseSRWLockExclusive
0x180053766  lock inc dword ptr [rdi+1C4h]
0x18005376d  mov     rcx, [rdi+238h]; pwk
0x180053774  call    cs:__imp_SubmitThreadpoolWork
0x18005377a  xor     eax, eax
0x18005377c  jmp     short loc_180053782
0x18005377e  mov     eax, dword ptr [rsp+28h+arg_0]
0x180053782  mov     rbx, [rsp+28h+arg_8]
0x180053787  mov     rsi, [rsp+28h+arg_10]
0x18005378c  add     rsp, 20h
0x180053790  pop     rdi
0x180053791  retn
```
