# CScopeChangeNotification::QueueEvent(ulong)

- ea: `0x1801e4910`
- end: `0x1801e4ac2`
- name: `?QueueEvent@CScopeChangeNotification@@AEAAXK@Z`
- size: `434`
- prototype: `void __fastcall(CScopeChangeNotification *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b08b0`

## callees

- `0x18008a124`
- `0x1800bdd18`
- `0x1800f3878`
- `0x180109184`
- `0x18010b360`
- `0x1801e4354`
- `0x1801e4910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801e4967`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801e4967`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1801e4957`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1801e4957`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1801e4948`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1801e4a96`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1801e4948`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1801e4a96`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x1801e4932`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x1801e4932`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801e4975`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801e4975`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CScopeChangeNotification::QueueEvent(CScopeChangeNotification *this, int a2)
{
  ULONGLONG TickCount64; // rax
  ULONGLONG v5; // rcx
  __int64 v6; // rbx
  __int64 *v7; // r15
  ULONGLONG v8; // r13
  unsigned int v9; // esi
  __int64 v10; // rax
  __int64 v11; // rdx
  signed __int64 v12; // rax
  unsigned __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rax
  _BYTE v18[72]; // [rsp+20h] [rbp-48h] BYREF
  unsigned int v19; // [rsp+70h] [rbp+8h] BYREF
  int v20; // [rsp+78h] [rbp+10h] BYREF
  char *v21; // [rsp+80h] [rbp+18h] BYREF

  v20 = a2;
  if ( IsThreadpoolTimerSet(*((PTP_TIMER *)this + 15)) )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 15), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 15), 1);
  }
  AcquireSRWLockExclusive((PSRWLOCK)this + 16);
  v21 = (char *)this + 128;
  TickCount64 = GetTickCount64();
  v6 = *((_QWORD *)this + 26);
  v7 = (__int64 *)((char *)this + 208);
  v8 = TickCount64;
LABEL_4:
  v6 = *(_QWORD *)v6;
  while ( v6 != *v7 )
  {
    v9 = *(_DWORD *)(v6 + 16);
    v19 = v9;
    if ( v9 == a2 )
      goto LABEL_4;
    v10 = std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>::operator()<unsigned long>(
            v5,
            &v19);
    v11 = *(_QWORD *)(std::_Hash<std::_Umap_traits<unsigned long,unsigned __int64,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,unsigned __int64>>,0>>::_Find_last<unsigned long>(
                        (char *)this + 136,
                        v18,
                        &v19,
                        v10)
                    + 8);
    if ( !v11 )
      v11 = *((_QWORD *)this + 18);
    v12 = 0;
    if ( v11 != *((_QWORD *)this + 18) )
      v12 = _InterlockedCompareExchange64((volatile signed __int64 *)(v11 + 24), 0, 0);
    v13 = -*(__int64 *)&CScopeChangeNotification::s_debounceTimeout;
    if ( *(__int64 *)&CScopeChangeNotification::s_debounceTimeout > 0 )
      v13 = (unsigned __int64)CScopeChangeNotification::s_debounceTimeout;
    v5 = v8 - v12;
    if ( v8 - v12 <= v13 )
      goto LABEL_4;
    v14 = std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>::operator()<unsigned long>(
            v5,
            v6 + 16);
    v15 = 2 * (*((_QWORD *)this + 31) & v14);
    v16 = *((_QWORD *)this + 28);
    if ( *(_QWORD *)(v16 + 16 * (*((_QWORD *)this + 31) & v14) + 8) == v6 )
    {
      if ( *(_QWORD *)(v16 + 16 * (*((_QWORD *)this + 31) & v14)) == v6 )
      {
        v17 = *v7;
        *(_QWORD *)(v16 + 8 * v15) = *v7;
      }
      else
      {
        v17 = *(_QWORD *)(v6 + 8);
      }
      *(_QWORD *)(v16 + 8 * v15 + 8) = v17;
    }
    else if ( *(_QWORD *)(v16 + 16 * (*((_QWORD *)this + 31) & v14)) == v6 )
    {
      *(_QWORD *)(v16 + 16 * (*((_QWORD *)this + 31) & v14)) = *(_QWORD *)v6;
    }
    v6 = std::list<unsigned long>::_Unchecked_erase((char *)this + 208, v6);
    CScopeChangeNotification::FireEvent(this, v9);
  }
  std::_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>::emplace<unsigned long const &>(
    (char *)this + 200,
    v18,
    &v20);
  SetThreadpoolTimer(*((PTP_TIMER *)this + 15), &CScopeChangeNotification::s_debounceTimeout, 0, 0);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v21);
}

```

## disassembly

```asm
0x1801e4910  mov     [rsp+arg_18], rbx
0x1801e4915  mov     [rsp+arg_8], edx
0x1801e4919  push    rbp
0x1801e491a  push    rsi
0x1801e491b  push    rdi
0x1801e491c  push    r12
0x1801e491e  push    r13
0x1801e4920  push    r14
0x1801e4922  push    r15
0x1801e4924  sub     rsp, 30h
0x1801e4928  mov     r12d, edx
0x1801e492b  mov     rdi, rcx
0x1801e492e  mov     rcx, [rcx+78h]; pti
0x1801e4932  call    cs:__imp_IsThreadpoolTimerSet
0x1801e4938  test    eax, eax
0x1801e493a  jz      short loc_1801E495D
0x1801e493c  xor     r9d, r9d; msWindowLength
0x1801e493f  xor     r8d, r8d; msPeriod
0x1801e4942  xor     edx, edx; pftDueTime
0x1801e4944  mov     rcx, [rdi+78h]; pti
0x1801e4948  call    cs:__imp_SetThreadpoolTimer
0x1801e494e  mov     edx, 1; fCancelPendingCallbacks
0x1801e4953  mov     rcx, [rdi+78h]; pti
0x1801e4957  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1801e495d  lea     rbx, [rdi+80h]
0x1801e4964  mov     rcx, rbx; SRWLock
0x1801e4967  call    cs:__imp_AcquireSRWLockExclusive
0x1801e496d  mov     [rsp+68h+arg_10], rbx
0x1801e4975  call    cs:__imp_GetTickCount64
0x1801e497b  mov     rbx, [rdi+0D0h]
0x1801e4982  lea     r15, [rdi+0D0h]
0x1801e4989  mov     r13, rax
0x1801e498c  mov     rbx, [rbx]
0x1801e498f  cmp     rbx, [r15]
0x1801e4992  jz      loc_1801E4A6F
0x1801e4998  mov     esi, [rbx+10h]
0x1801e499b  mov     [rsp+68h+arg_0], esi
0x1801e499f  cmp     esi, r12d
0x1801e49a2  jz      short loc_1801E498C
0x1801e49a4  lea     rbp, [rdi+88h]
0x1801e49ab  lea     rdx, [rsp+68h+arg_0]
0x1801e49b0  call    ??$?RK@?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@QEBA_KAEBK@Z; std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>::operator()<ulong>(ulong const &)
0x1801e49b5  mov     r9, rax
0x1801e49b8  lea     r8, [rsp+68h+arg_0]
0x1801e49bd  lea     rdx, [rsp+68h+var_48]
0x1801e49c2  mov     rcx, rbp
0x1801e49c5  call    ??$_Find_last@K@?$_Hash@V?$_Umap_traits@K_KV?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBK_K@std@@PEAX@std@@@1@AEBK_K@Z; std::_Hash<std::_Umap_traits<ulong,unsigned __int64,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,unsigned __int64>>,0>>::_Find_last<ulong>(ulong const &,unsigned __int64)
0x1801e49ca  mov     rdx, [rax+8]
0x1801e49ce  test    rdx, rdx
0x1801e49d1  jnz     short loc_1801E49D7
0x1801e49d3  mov     rdx, [rbp+8]
0x1801e49d7  xor     eax, eax
0x1801e49d9  cmp     rdx, [rdi+90h]
0x1801e49e0  jz      short loc_1801E49EA
0x1801e49e2  xor     ecx, ecx
0x1801e49e4  lock cmpxchg [rdx+18h], rcx
0x1801e49ea  mov     r8, qword ptr cs:?s_debounceTimeout@CScopeChangeNotification@@0_JA.dwLowDateTime; __int64 CScopeChangeNotification::s_debounceTimeout ...
0x1801e49f1  neg     r8
0x1801e49f4  cmovs   r8, qword ptr cs:?s_debounceTimeout@CScopeChangeNotification@@0_JA.dwLowDateTime; __int64 CScopeChangeNotification::s_debounceTimeout ...
0x1801e49fc  mov     rcx, r13
0x1801e49ff  sub     rcx, rax
0x1801e4a02  cmp     rcx, r8
0x1801e4a05  jbe     short loc_1801E498C
0x1801e4a07  lea     rdx, [rbx+10h]
0x1801e4a0b  call    ??$?RK@?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@QEBA_KAEBK@Z; std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>::operator()<ulong>(ulong const &)
0x1801e4a10  mov     rdx, rax
0x1801e4a13  and     rdx, [rdi+0F8h]
0x1801e4a1a  add     rdx, rdx
0x1801e4a1d  mov     rcx, [rdi+0E0h]
0x1801e4a24  cmp     [rcx+rdx*8+8], rbx
0x1801e4a29  jnz     short loc_1801E4A45
0x1801e4a2b  cmp     [rcx+rdx*8], rbx
0x1801e4a2f  jnz     short loc_1801E4A3A
0x1801e4a31  mov     rax, [r15]
0x1801e4a34  mov     [rcx+rdx*8], rax
0x1801e4a38  jmp     short loc_1801E4A3E
0x1801e4a3a  mov     rax, [rbx+8]
0x1801e4a3e  mov     [rcx+rdx*8+8], rax
0x1801e4a43  jmp     short loc_1801E4A52
0x1801e4a45  cmp     [rcx+rdx*8], rbx
0x1801e4a49  jnz     short loc_1801E4A52
0x1801e4a4b  mov     rax, [rbx]
0x1801e4a4e  mov     [rcx+rdx*8], rax
0x1801e4a52  mov     rdx, rbx
0x1801e4a55  mov     rcx, r15
0x1801e4a58  call    ?_Unchecked_erase@?$list@KV?$allocator@K@std@@@std@@AEAAPEAU?$_List_node@KPEAX@2@QEAU32@@Z; std::list<ulong>::_Unchecked_erase(std::_List_node<ulong,void *> * const)
0x1801e4a5d  mov     rbx, rax
0x1801e4a60  mov     edx, esi; unsigned int
0x1801e4a62  mov     rcx, rdi; this
0x1801e4a65  call    ?FireEvent@CScopeChangeNotification@@AEAAXK@Z; CScopeChangeNotification::FireEvent(ulong)
0x1801e4a6a  jmp     loc_1801E498F
0x1801e4a6f  lea     r8, [rsp+68h+arg_8]
0x1801e4a74  lea     rdx, [rsp+68h+var_48]
0x1801e4a79  lea     rcx, [rdi+0C8h]
0x1801e4a80  call    ??$emplace@AEBK@?$_Hash@V?$_Uset_traits@KV?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@@std@@_N@1@AEBK@Z; std::_Hash<std::_Uset_traits<ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<ulong>,0>>::emplace<ulong const &>(ulong const &)
0x1801e4a85  xor     r9d, r9d; msWindowLength
0x1801e4a88  xor     r8d, r8d; msPeriod
0x1801e4a8b  lea     rdx, ?s_debounceTimeout@CScopeChangeNotification@@0_JA; pftDueTime
0x1801e4a92  mov     rcx, [rdi+78h]; pti
0x1801e4a96  call    cs:__imp_SetThreadpoolTimer
0x1801e4a9c  nop
0x1801e4a9d  lea     rcx, [rsp+68h+arg_10]
0x1801e4aa5  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1801e4aaa  mov     rbx, [rsp+68h+arg_18]
0x1801e4ab2  add     rsp, 30h
0x1801e4ab6  pop     r15
0x1801e4ab8  pop     r14
0x1801e4aba  pop     r13
0x1801e4abc  pop     r12
0x1801e4abe  pop     rdi
0x1801e4abf  pop     rsi
0x1801e4ac0  pop     rbp
0x1801e4ac1  retn
```
