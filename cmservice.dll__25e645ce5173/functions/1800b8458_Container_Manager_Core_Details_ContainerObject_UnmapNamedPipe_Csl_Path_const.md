# Container::Manager::Core::Details::ContainerObject::UnmapNamedPipe(Csl::Path const &)

- ea: `0x1800b8458`
- end: `0x1800b86ec`
- name: `?UnmapNamedPipe@ContainerObject@Details@Core@Manager@Container@@AEAAJAEBVPath@Csl@@@Z`
- size: `660`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::ContainerObject *__hidden this, const struct Path *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001ec50`

## callees

- `0x180004fc4`
- `0x18000da88`
- `0x180016774`
- `0x18009b018`
- `0x1800ac950`
- `0x1800b8458`
- `0x1800ba5ac`
- `0x180125268`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b8497`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b85d1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b8497`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b85d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b85ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b861a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b865b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b86ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b85ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b861a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b865b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b86ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b84a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b85dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b84a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b85dd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b84f3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b8552`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b84f3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b8552`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::ContainerObject::UnmapNamedPipe(
        Container::Manager::Core::Details::ContainerObject *this,
        LPCWCH *a2)
{
  RTL_SRWLOCK *v3; // rbx
  DWORD CurrentThreadId; // eax
  LPCWCH *v6; // rdi
  LPCWCH *v7; // rsi
  LPCWCH *v8; // r14
  __int64 v9; // rax
  unsigned int v10; // edi
  __int64 v11; // rdx
  RTL_SRWLOCK *v12; // rcx
  int v13; // esi
  BOOL bIgnoreCase; // [rsp+20h] [rbp-30h]
  void *v16[2]; // [rsp+30h] [rbp-20h] BYREF
  _WORD v17[8]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  PSRWLOCK SRWLock; // [rsp+80h] [rbp+30h] BYREF

  v16[0] = v17;
  v3 = (RTL_SRWLOCK *)((char *)this + 456);
  v16[1] = v17;
  v17[0] = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this + 57);
  CurrentThreadId = GetCurrentThreadId();
  v6 = (LPCWCH *)((char *)this + 648);
  SRWLock = v3;
  LODWORD(v3[1].Ptr) = CurrentThreadId;
  if ( *((Container::Manager::Core::Details::ContainerObject **)this + 83) == (Container::Manager::Core::Details::ContainerObject *)((char *)this + 648) )
    goto LABEL_20;
  v7 = (LPCWCH *)*v6;
  v8 = (LPCWCH *)((char *)this + 648);
  do
  {
    if ( CompareStringOrdinal(v7[3], v7[4] - v7[3], *a2, a2[1] - *a2, 1) == 1 )
    {
      v9 = 2;
    }
    else
    {
      v8 = v7;
      v9 = 1;
    }
    v7 = (LPCWCH *)v7[v9];
  }
  while ( v7 != (LPCWCH *)&utl::_TreeSentinel );
  if ( v8 == v6 || CompareStringOrdinal(*a2, a2[1] - *a2, v8[3], v8[4] - v8[3], 1) == 1 )
  {
LABEL_20:
    v10 = -2147023728;
    v11 = 3297;
    goto LABEL_21;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v16,
                           v8[7],
                           v8[8] - v8[7]) )
  {
    v10 = -2147024882;
    v11 = 3301;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)v10,
      bIgnoreCase);
    LODWORD(v3[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v3);
    if ( v16[0] != v17 )
      operator delete(v16[0], (const struct std::nothrow_t *)&std::nothrow);
    return v10;
  }
  Container::Manager::Core::Details::ContainerObject::AcquireAndWaitForContainerInfrastructureWakeReference(
    this,
    &SRWLock);
  v12 = SRWLock;
  if ( SRWLock )
  {
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v12);
  }
  v13 = Container::Manager::Hcs::ComputeSystem::UnmapNamedPipe(
          *((Container::Manager::Hcs::ComputeSystem **)this + 157),
          (const struct Path *)a2,
          (const struct Path *)v16);
  AcquireSRWLockExclusive(v3);
  LODWORD(v3[1].Ptr) = GetCurrentThreadId();
  Container::Manager::Core::Details::ContainerObject::ReleaseContainerInfrastructureWakeReference(this);
  if ( v13 >= 0 )
  {
    utl::_Tree<Csl::Path,utl::pair<Csl::Path const,Csl::Path>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,Csl::Path>>,0>::erase((char *)this + 648);
    LODWORD(v3[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v3);
    if ( v16[0] != v17 )
      operator delete(v16[0], (const struct std::nothrow_t *)&std::nothrow);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCF6,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)(unsigned int)v13,
      bIgnoreCase);
    LODWORD(v3[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v3);
    if ( v16[0] != v17 )
      operator delete(v16[0], (const struct std::nothrow_t *)&std::nothrow);
    return (unsigned int)v13;
  }
}

```

## disassembly

```asm
0x1800b8458  mov     [rsp-28h+arg_8], rbx
0x1800b845d  mov     [rsp-28h+arg_10], rsi
0x1800b8462  push    rbp
0x1800b8463  push    rdi
0x1800b8464  push    r12
0x1800b8466  push    r14
0x1800b8468  push    r15
0x1800b846a  mov     rbp, rsp
0x1800b846d  sub     rsp, 50h
0x1800b8471  lea     rax, [rbp+var_10]
0x1800b8475  mov     r15, rcx
0x1800b8478  mov     [rbp+var_20], rax
0x1800b847c  lea     rbx, [rcx+1C8h]
0x1800b8483  lea     rax, [rbp+var_10]
0x1800b8487  mov     rcx, rbx; SRWLock
0x1800b848a  mov     [rbp+var_18], rax
0x1800b848e  mov     r12, rdx
0x1800b8491  xor     eax, eax
0x1800b8493  mov     [rbp+var_10], ax
0x1800b8497  call    cs:__imp_AcquireSRWLockExclusive
0x1800b849e  nop     dword ptr [rax+rax+00h]
0x1800b84a3  call    cs:__imp_GetCurrentThreadId
0x1800b84aa  nop     dword ptr [rax+rax+00h]
0x1800b84af  lea     rdi, [r15+288h]
0x1800b84b6  mov     [rbp+SRWLock], rbx
0x1800b84ba  mov     [rbx+8], eax
0x1800b84bd  cmp     [rdi+10h], rdi
0x1800b84c1  jz      loc_1800B8684
0x1800b84c7  mov     rsi, [rdi]
0x1800b84ca  mov     r14, rdi
0x1800b84cd  mov     rcx, [rsi+18h]; lpString1
0x1800b84d1  mov     r9, [r12+8]
0x1800b84d6  mov     rdx, [rsi+20h]
0x1800b84da  sub     r9, [r12]
0x1800b84de  sub     rdx, rcx
0x1800b84e1  mov     r8, [r12]; lpString2
0x1800b84e5  sar     r9, 1; cchCount2
0x1800b84e8  sar     rdx, 1; cchCount1
0x1800b84eb  mov     [rsp+50h+bIgnoreCase], 1; bIgnoreCase
0x1800b84f3  call    cs:__imp_CompareStringOrdinal
0x1800b84fa  nop     dword ptr [rax+rax+00h]
0x1800b84ff  cmp     eax, 1
0x1800b8502  jnz     short loc_1800B850B
0x1800b8504  mov     eax, 10h
0x1800b8509  jmp     short loc_1800B8513
0x1800b850b  mov     r14, rsi
0x1800b850e  mov     eax, 8
0x1800b8513  mov     rsi, [rax+rsi]
0x1800b8517  lea     rax, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x1800b851e  cmp     rsi, rax
0x1800b8521  jnz     short loc_1800B84CD
0x1800b8523  cmp     r14, rdi
0x1800b8526  jz      loc_1800B8684
0x1800b852c  mov     r8, [r14+18h]; lpString2
0x1800b8530  mov     r9, [r14+20h]
0x1800b8534  mov     rdx, [r12+8]
0x1800b8539  sub     r9, r8
0x1800b853c  sub     rdx, [r12]
0x1800b8540  mov     rcx, [r12]; lpString1
0x1800b8544  sar     r9, 1; cchCount2
0x1800b8547  sar     rdx, 1; cchCount1
0x1800b854a  mov     [rsp+50h+bIgnoreCase], 1; int
0x1800b8552  call    cs:__imp_CompareStringOrdinal
0x1800b8559  nop     dword ptr [rax+rax+00h]
0x1800b855e  cmp     eax, 1
0x1800b8561  jz      loc_1800B8684
0x1800b8567  mov     rdx, [r14+38h]
0x1800b856b  lea     rcx, [rbp+var_20]
0x1800b856f  mov     r8, [r14+40h]
0x1800b8573  sub     r8, rdx
0x1800b8576  sar     r8, 1
0x1800b8579  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800b857e  test    al, al
0x1800b8580  jnz     short loc_1800B8591
0x1800b8582  mov     edi, 8007000Eh
0x1800b8587  mov     edx, 0CE5h
0x1800b858c  jmp     loc_1800B868E
0x1800b8591  lea     rdx, [rbp+SRWLock]
0x1800b8595  mov     rcx, r15
0x1800b8598  call    ?AcquireAndWaitForContainerInfrastructureWakeReference@ContainerObject@Details@Core@Manager@Container@@AEAAXAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::AcquireAndWaitForContainerInfrastructureWakeReference(Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800b859d  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800b85a1  test    rcx, rcx
0x1800b85a4  jz      short loc_1800B85B9
0x1800b85a6  mov     dword ptr [rcx+8], 0
0x1800b85ad  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b85b4  nop     dword ptr [rax+rax+00h]
0x1800b85b9  mov     rcx, [r15+4E8h]; this
0x1800b85c0  lea     r8, [rbp+var_20]; struct Path *
0x1800b85c4  mov     rdx, r12; struct Path *
0x1800b85c7  call    ?UnmapNamedPipe@ComputeSystem@Hcs@Manager@Container@@QEAAJAEBVPath@Csl@@0@Z; Container::Manager::Hcs::ComputeSystem::UnmapNamedPipe(Csl::Path const &,Csl::Path const &)
0x1800b85cc  mov     rcx, rbx; SRWLock
0x1800b85cf  mov     esi, eax
0x1800b85d1  call    cs:__imp_AcquireSRWLockExclusive
0x1800b85d8  nop     dword ptr [rax+rax+00h]
0x1800b85dd  call    cs:__imp_GetCurrentThreadId
0x1800b85e4  nop     dword ptr [rax+rax+00h]
0x1800b85e9  mov     rcx, r15; this
0x1800b85ec  mov     [rbx+8], eax
0x1800b85ef  call    ?ReleaseContainerInfrastructureWakeReference@ContainerObject@Details@Core@Manager@Container@@AEAAXXZ; Container::Manager::Core::Details::ContainerObject::ReleaseContainerInfrastructureWakeReference(void)
0x1800b85f4  test    esi, esi
0x1800b85f6  jns     short loc_1800B8646
0x1800b85f8  mov     rcx, [rbp+28h]; this
0x1800b85fc  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800b8603  mov     r9d, esi; char *
0x1800b8606  mov     edx, 0CF6h; void *
0x1800b860b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b8610  mov     rcx, rbx; SRWLock
0x1800b8613  mov     dword ptr [rbx+8], 0
0x1800b861a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b8621  nop     dword ptr [rax+rax+00h]
0x1800b8626  mov     rcx, [rbp+var_20]; void *
0x1800b862a  lea     rax, [rbp+var_10]
0x1800b862e  cmp     rcx, rax
0x1800b8631  jz      short loc_1800B863F
0x1800b8633  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b863a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b863f  mov     eax, esi
0x1800b8641  jmp     loc_1800B86D2
0x1800b8646  mov     rdx, r12
0x1800b8649  mov     rcx, rdi; void *
0x1800b864c  call    ?erase@?$_Tree@VPath@Csl@@U?$pair@$$CBVPath@Csl@@V12@@utl@@U?$less@VPath@Csl@@@4@V?$allocator@U?$pair@$$CBVPath@Csl@@V12@@utl@@@4@$0A@@utl@@QEAA_KAEBVPath@Csl@@@Z; utl::_Tree<Csl::Path,utl::pair<Csl::Path const,Csl::Path>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,Csl::Path>>,0>::erase(Csl::Path const &)
0x1800b8651  mov     rcx, rbx; SRWLock
0x1800b8654  mov     dword ptr [rbx+8], 0
0x1800b865b  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b8662  nop     dword ptr [rax+rax+00h]
0x1800b8667  mov     rcx, [rbp+var_20]; void *
0x1800b866b  lea     rax, [rbp+var_10]
0x1800b866f  cmp     rcx, rax
0x1800b8672  jz      short loc_1800B8680
0x1800b8674  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b867b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b8680  xor     eax, eax
0x1800b8682  jmp     short loc_1800B86D2
0x1800b8684  mov     edi, 80070490h
0x1800b8689  mov     edx, 0CE1h; void *
0x1800b868e  mov     rcx, [rbp+28h]; this
0x1800b8692  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800b8699  mov     r9d, edi; char *
0x1800b869c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b86a1  mov     rcx, rbx; SRWLock
0x1800b86a4  mov     dword ptr [rbx+8], 0
0x1800b86ab  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b86b2  nop     dword ptr [rax+rax+00h]
0x1800b86b7  mov     rcx, [rbp+var_20]; void *
0x1800b86bb  lea     rdx, [rbp+var_10]
0x1800b86bf  cmp     rcx, rdx
0x1800b86c2  jz      short loc_1800B86D0
0x1800b86c4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b86cb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b86d0  mov     eax, edi
0x1800b86d2  lea     r11, [rsp+50h+var_s0]
0x1800b86d7  mov     rbx, [r11+38h]
0x1800b86db  mov     rsi, [r11+40h]
0x1800b86df  mov     rsp, r11
0x1800b86e2  pop     r15
0x1800b86e4  pop     r14
0x1800b86e6  pop     r12
0x1800b86e8  pop     rdi
0x1800b86e9  pop     rbp
0x1800b86ea  retn
```
