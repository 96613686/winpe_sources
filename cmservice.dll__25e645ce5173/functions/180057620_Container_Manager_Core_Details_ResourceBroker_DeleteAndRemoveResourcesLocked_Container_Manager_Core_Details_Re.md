# Container::Manager::Core::Details::ResourceBroker::DeleteAndRemoveResourcesLocked(Container::Manager::Core::Details::ResourceDeletionContext,Csl::SrwLock::ReleaseOnScopeExit<0> &,bool)

- ea: `0x180057620`
- end: `0x1800578f7`
- name: `?DeleteAndRemoveResourcesLocked@ResourceBroker@Details@Core@Manager@Container@@AEAAXUResourceDeletionContext@2345@AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@_N@Z`
- size: `727`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180057c8c`
- `0x1800603fc`

## callees

- `0x180004fc4`
- `0x18000a10c`
- `0x18004e000`
- `0x18004e0e8`
- `0x18004fe0c`
- `0x180057620`
- `0x180057900`
- `0x180060fc0`
- `0x180061534`
- `0x180066180`
- `0x1800666e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800577ae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180057875`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800577ae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180057875`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057743`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800577de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800577fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005784b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800578a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800578c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057743`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800577de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800577fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005784b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800578a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800578c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800577ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057881`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800577ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057881`

## string_xrefs

- `0x1800578e5`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`

## pseudocode

```c
void __fastcall Container::Manager::Core::Details::ResourceBroker::DeleteAndRemoveResourcesLocked(
        __int64 a1,
        _QWORD *a2,
        char *a3,
        const char *a4)
{
  const struct Container::Manager::Core::Details::Resource **v4; // rbx
  __int64 *v5; // r15
  const struct Container::Manager::Core::Details::Resource **v6; // rdi
  __int64 *v7; // rbp
  bool v8; // r12
  char *v12; // rbp
  __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  char v16; // al
  _QWORD *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // r9
  __int64 v20; // rcx
  Container::Manager::Core::Details::ResourceBroker *v21; // rcx
  const struct Container::Manager::Core::Details::Resource **v22; // rbx
  const struct Container::Manager::Core::Details::Resource **v23; // rdi
  __int64 v24; // rbx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rcx
  char v30; // [rsp+20h] [rbp-78h] BYREF
  char v31; // [rsp+28h] [rbp-70h] BYREF
  _QWORD v32[13]; // [rsp+30h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v4 = (const struct Container::Manager::Core::Details::Resource **)*a2;
  v5 = a2 + 6;
  v6 = (const struct Container::Manager::Core::Details::Resource **)a2[1];
  v7 = a2 + 6;
  v8 = (char)a4;
  while ( v4 != v6 )
  {
    *((_BYTE *)*v4 + 256) = 1;
    v12 = (char *)*((_QWORD *)*v4 + 31);
    *((_QWORD *)*v4 + 31) = 0;
    if ( v12 )
    {
      wistd::unique_ptr<Csl::ListEntry<Container::Manager::Core::Details::Resource *>,wistd::default_delete<Csl::ListEntry<Container::Manager::Core::Details::Resource *>>>::reset(
        v12 + 24,
        0);
      operator delete(v12, (const struct std::nothrow_t *)0x20);
    }
    v7 = a2 + 6;
    v13 = a2[8];
    if ( a2[7] != v13 )
      goto LABEL_11;
    v14 = 0xAAAAAAAAAAAAAAABuLL * ((v13 - *v7) >> 3);
    v15 = 7 * (v14 >> 2) + 8;
    if ( v15 > 0x555555555555555LL )
      v15 = 0x555555555555555LL;
    if ( v14 < v15
      && (unsigned __int8)utl::vector<utl::vector<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>,utl::allocator<utl::vector<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>>>::_SetCapacity(a2 + 6) )
    {
LABEL_11:
      v17 = (_QWORD *)a2[7];
      *v17 = -1;
      v17[1] = -1;
      v17[2] = -1;
      a2[7] += 24LL;
      v16 = 0;
    }
    else
    {
      v16 = 1;
    }
    if ( v16 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x175F,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        a4);
    Container::Manager::Core::Details::Resource::RemoveAllOutgoingNeighbors(*v4++, a2[7] - 24LL);
  }
  v18 = *(_QWORD *)a3;
  if ( *(_QWORD *)a3 )
  {
    *(_DWORD *)(v18 + 8) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v18);
    *(_QWORD *)a3 = 0;
  }
  else
  {
    v5 = v7;
  }
  v19 = *v5;
  v20 = v5[1] - *v5;
  v5[1] = *v5;
  utl::_RangeDestroyApc<utl::allocator<utl::vector<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>>>(
    v20,
    v19,
    v20 / 24);
  v22 = (const struct Container::Manager::Core::Details::Resource **)*a2;
  v23 = (const struct Container::Manager::Core::Details::Resource **)a2[1];
  while ( v22 != v23 )
    Container::Manager::Core::Details::ResourceBroker::DeleteResource(v21, *v22++, v8);
  v24 = a1 + 16;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 16));
  *(_DWORD *)(a1 + 24) = GetCurrentThreadId();
  if ( a3 == &v30 )
  {
    if ( a1 != -16 )
    {
      *(_DWORD *)(a1 + 24) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 16));
    }
  }
  else
  {
    v25 = *(_QWORD *)a3;
    if ( *(_QWORD *)a3 )
    {
      *(_DWORD *)(v25 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v25);
    }
    *(_QWORD *)a3 = v24;
  }
  v32[0] = *a2;
  v32[1] = a2[1];
  v32[2] = a2[2];
  *a2 = -1;
  a2[1] = -1;
  a2[2] = -1;
  Container::Manager::Core::Details::ResourceBroker::RemoveResourcesLocked(a1, v32, a2 + 3);
  v26 = *(_QWORD *)a3;
  if ( *(_QWORD *)a3 )
  {
    *(_DWORD *)(v26 + 8) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v26);
    *(_QWORD *)a3 = 0;
  }
  v27 = a2[3];
  v28 = a2[4] - v27;
  a2[4] = v27;
  utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>>(
    v26,
    v27,
    v28 >> 3);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 16));
  *(_DWORD *)(a1 + 24) = GetCurrentThreadId();
  if ( a3 == &v31 )
  {
    if ( a1 != -16 )
    {
      *(_DWORD *)(a1 + 24) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 16));
    }
  }
  else
  {
    v29 = *(_QWORD *)a3;
    if ( *(_QWORD *)a3 )
    {
      *(_DWORD *)(v29 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v29);
    }
    *(_QWORD *)a3 = v24;
  }
  Container::Manager::Core::Details::ResourceDeletionContext::~ResourceDeletionContext((Container::Manager::Core::Details::ResourceDeletionContext *)a2);
}

```

## disassembly

```asm
0x180057620  push    rbx
0x180057622  push    rbp
0x180057623  push    rsi
0x180057624  push    rdi
0x180057625  push    r12
0x180057627  push    r13
0x180057629  push    r14
0x18005762b  push    r15
0x18005762d  sub     rsp, 58h
0x180057631  mov     rbx, [rdx]
0x180057634  lea     r15, [rdx+30h]
0x180057638  mov     rdi, [rdx+8]
0x18005763c  mov     rbp, r15
0x18005763f  mov     r12b, r9b
0x180057642  mov     r14, r8
0x180057645  mov     rsi, rdx
0x180057648  mov     r13, rcx
0x18005764b  mov     r8, 555555555555555h
0x180057655  cmp     rbx, rdi
0x180057658  jz      loc_180057736
0x18005765e  mov     rax, [rbx]
0x180057661  mov     byte ptr [rax+100h], 1
0x180057668  mov     rax, [rbx]
0x18005766b  mov     rbp, [rax+0F8h]
0x180057672  mov     qword ptr [rax+0F8h], 0
0x18005767d  test    rbp, rbp
0x180057680  jz      short loc_1800576A4
0x180057682  lea     rcx, [rbp+18h]
0x180057686  xor     edx, edx
0x180057688  call    ?reset@?$unique_ptr@V?$ListEntry@PEAVResource@Details@Core@Manager@Container@@@Csl@@U?$default_delete@V?$ListEntry@PEAVResource@Details@Core@Manager@Container@@@Csl@@@wistd@@@wistd@@QEAAXPEAV?$ListEntry@PEAVResource@Details@Core@Manager@Container@@@Csl@@@Z; wistd::unique_ptr<Csl::ListEntry<Container::Manager::Core::Details::Resource *>,wistd::default_delete<Csl::ListEntry<Container::Manager::Core::Details::Resource *>>>::reset(Csl::ListEntry<Container::Manager::Core::Details::Resource *> *)
0x18005768d  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x180057692  mov     rcx, rbp; void *
0x180057695  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005769a  mov     r8, 555555555555555h
0x1800576a4  lea     rbp, [rsi+30h]
0x1800576a8  mov     rcx, [rbp+10h]
0x1800576ac  cmp     [rbp+8], rcx
0x1800576b0  jnz     short loc_1800576F3
0x1800576b2  sub     rcx, [rbp+0]
0x1800576b6  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800576c0  sar     rcx, 3
0x1800576c4  imul    rcx, rax
0x1800576c8  mov     rax, rcx
0x1800576cb  shr     rax, 2
0x1800576cf  imul    rdx, rax, 7
0x1800576d3  add     rdx, 8
0x1800576d7  cmp     rdx, r8
0x1800576da  cmova   rdx, r8
0x1800576de  cmp     rcx, rdx
0x1800576e1  jnb     short loc_1800576EF
0x1800576e3  mov     rcx, rbp
0x1800576e6  call    ?_SetCapacity@?$vector@V?$vector@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@V?$allocator@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@V?$allocator@V?$vector@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@V?$allocator@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::vector<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>,utl::allocator<utl::vector<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>>>::_SetCapacity(unsigned __int64)
0x1800576eb  test    al, al
0x1800576ed  jnz     short loc_1800576F3
0x1800576ef  mov     al, 1
0x1800576f1  jmp     short loc_18005770D
0x1800576f3  mov     rax, [rbp+8]
0x1800576f7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800576fb  mov     [rax], rcx
0x1800576fe  mov     [rax+8], rcx
0x180057702  mov     [rax+10h], rcx
0x180057706  add     qword ptr [rbp+8], 18h
0x18005770b  xor     al, al
0x18005770d  mov     rcx, [rsp+98h]; this
0x180057715  test    al, al
0x180057717  jnz     loc_1800578E5
0x18005771d  mov     rdx, [rsi+38h]
0x180057721  mov     rcx, [rbx]
0x180057724  sub     rdx, 18h
0x180057728  call    ?RemoveAllOutgoingNeighbors@Resource@Details@Core@Manager@Container@@AEAAXAEAV?$vector@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@V?$allocator@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@@Z; Container::Manager::Core::Details::Resource::RemoveAllOutgoingNeighbors(utl::vector<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>> &)
0x18005772d  add     rbx, 8
0x180057731  jmp     loc_18005764B
0x180057736  mov     rcx, [r14]; SRWLock
0x180057739  test    rcx, rcx
0x18005773c  jz      short loc_180057754
0x18005773e  xor     ebp, ebp
0x180057740  mov     [rcx+8], ebp
0x180057743  call    cs:__imp_ReleaseSRWLockExclusive
0x18005774a  nop     dword ptr [rax+rax+00h]
0x18005774f  mov     [r14], rbp
0x180057752  jmp     short loc_180057759
0x180057754  mov     r15, rbp
0x180057757  xor     ebp, ebp
0x180057759  mov     r9, [r15]
0x18005775c  mov     rax, 2AAAAAAAAAAAAAABh
0x180057766  mov     rcx, [r15+8]
0x18005776a  sub     rcx, r9
0x18005776d  mov     [r15+8], r9
0x180057771  imul    rcx
0x180057774  sar     rdx, 2
0x180057778  mov     r8, rdx
0x18005777b  shr     r8, 3Fh
0x18005777f  add     r8, rdx
0x180057782  mov     rdx, r9
0x180057785  call    ??$_RangeDestroyApc@V?$allocator@V?$vector@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@V?$allocator@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$vector@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@V?$allocator@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@@0@PEAV?$vector@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@V?$allocator@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::vector<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>>>(utl::allocator<utl::vector<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>> &,utl::vector<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>> *,unsigned __int64)
0x18005778a  mov     rbx, [rsi]
0x18005778d  mov     rdi, [rsi+8]
0x180057791  cmp     rbx, rdi
0x180057794  jz      short loc_1800577A7
0x180057796  mov     rdx, [rbx]; struct Container::Manager::Core::Details::Resource *
0x180057799  mov     r8b, r12b; bool
0x18005779c  call    ?DeleteResource@ResourceBroker@Details@Core@Manager@Container@@AEAAXPEBVResource@2345@_N@Z; Container::Manager::Core::Details::ResourceBroker::DeleteResource(Container::Manager::Core::Details::Resource const *,bool)
0x1800577a1  add     rbx, 8
0x1800577a5  jmp     short loc_180057791
0x1800577a7  lea     rbx, [r13+10h]
0x1800577ab  mov     rcx, rbx; SRWLock
0x1800577ae  call    cs:__imp_AcquireSRWLockExclusive
0x1800577b5  nop     dword ptr [rax+rax+00h]
0x1800577ba  call    cs:__imp_GetCurrentThreadId
0x1800577c1  nop     dword ptr [rax+rax+00h]
0x1800577c6  mov     [rbx+8], eax
0x1800577c9  lea     rax, [rsp+98h+var_78]
0x1800577ce  cmp     r14, rax
0x1800577d1  jz      short loc_1800577EF
0x1800577d3  mov     rcx, [r14]; SRWLock
0x1800577d6  test    rcx, rcx
0x1800577d9  jz      short loc_1800577EA
0x1800577db  mov     [rcx+8], ebp
0x1800577de  call    cs:__imp_ReleaseSRWLockExclusive
0x1800577e5  nop     dword ptr [rax+rax+00h]
0x1800577ea  mov     [r14], rbx
0x1800577ed  jmp     short loc_180057806
0x1800577ef  test    rbx, rbx
0x1800577f2  jz      short loc_180057806
0x1800577f4  mov     rcx, rbx; SRWLock
0x1800577f7  mov     [rbx+8], ebp
0x1800577fa  call    cs:__imp_ReleaseSRWLockExclusive
0x180057801  nop     dword ptr [rax+rax+00h]
0x180057806  mov     rax, [rsi]
0x180057809  lea     r8, [rsi+18h]
0x18005780d  mov     [rsp+98h+var_68], rax
0x180057812  lea     rdx, [rsp+98h+var_68]
0x180057817  mov     rax, [rsi+8]
0x18005781b  mov     rcx, r13
0x18005781e  mov     [rsp+98h+var_60], rax
0x180057823  mov     rax, [rsi+10h]
0x180057827  mov     [rsp+98h+var_58], rax
0x18005782c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180057830  mov     [rsi], rax
0x180057833  mov     [rsi+8], rax
0x180057837  mov     [rsi+10h], rax
0x18005783b  call    ?RemoveResourcesLocked@ResourceBroker@Details@Core@Manager@Container@@AEAAXV?$vector@PEAVResource@Details@Core@Manager@Container@@V?$allocator@PEAVResource@Details@Core@Manager@Container@@@utl@@@utl@@AEAV?$vector@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@V?$allocator@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@7@@Z; Container::Manager::Core::Details::ResourceBroker::RemoveResourcesLocked(utl::vector<Container::Manager::Core::Details::Resource *,utl::allocator<Container::Manager::Core::Details::Resource *>>,utl::vector<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>> &)
0x180057840  mov     rcx, [r14]; SRWLock
0x180057843  test    rcx, rcx
0x180057846  jz      short loc_18005785A
0x180057848  mov     [rcx+8], ebp
0x18005784b  call    cs:__imp_ReleaseSRWLockExclusive
0x180057852  nop     dword ptr [rax+rax+00h]
0x180057857  mov     [r14], rbp
0x18005785a  mov     rdx, [rsi+18h]
0x18005785e  mov     r8, [rsi+20h]
0x180057862  sub     r8, rdx
0x180057865  mov     [rsi+20h], rdx
0x180057869  sar     r8, 3
0x18005786d  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@@0@PEAV?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@_K@Z; utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>>(utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>> &,wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>> *,unsigned __int64)
0x180057872  mov     rcx, rbx; SRWLock
0x180057875  call    cs:__imp_AcquireSRWLockExclusive
0x18005787c  nop     dword ptr [rax+rax+00h]
0x180057881  call    cs:__imp_GetCurrentThreadId
0x180057888  nop     dword ptr [rax+rax+00h]
0x18005788d  mov     [rbx+8], eax
0x180057890  lea     rax, [rsp+98h+var_70]
0x180057895  cmp     r14, rax
0x180057898  jz      short loc_1800578B6
0x18005789a  mov     rcx, [r14]; SRWLock
0x18005789d  test    rcx, rcx
0x1800578a0  jz      short loc_1800578B1
0x1800578a2  mov     [rcx+8], ebp
0x1800578a5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800578ac  nop     dword ptr [rax+rax+00h]
0x1800578b1  mov     [r14], rbx
0x1800578b4  jmp     short loc_1800578CD
0x1800578b6  test    rbx, rbx
0x1800578b9  jz      short loc_1800578CD
0x1800578bb  mov     rcx, rbx; SRWLock
0x1800578be  mov     [rbx+8], ebp
0x1800578c1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800578c8  nop     dword ptr [rax+rax+00h]
0x1800578cd  mov     rcx, rsi; this
0x1800578d0  add     rsp, 58h
0x1800578d4  pop     r15
0x1800578d6  pop     r14
0x1800578d8  pop     r13
0x1800578da  pop     r12
0x1800578dc  pop     rdi
0x1800578dd  pop     rsi
0x1800578de  pop     rbp
0x1800578df  pop     rbx
0x1800578e0  jmp     ??1ResourceDeletionContext@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ResourceDeletionContext::~ResourceDeletionContext(void)
0x1800578e5  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800578ec  mov     edx, 175Fh; void *
0x1800578f1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
