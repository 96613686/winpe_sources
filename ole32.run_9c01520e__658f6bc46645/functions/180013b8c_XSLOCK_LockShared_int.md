# XSLOCK::LockShared(int)

- ea: `0x180013b8c`
- end: `0x180013d62`
- name: `?LockShared@XSLOCK@@QEAAHH@Z`
- size: `470`
- prototype: `int __fastcall(XSLOCK *this, int fWait)`
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800125c8`
- `0x1800126bc`
- `0x180013414`
- `0x180014e30`
- `0x18001519c`
- `0x180016dc4`

## callees

- `0x180013b8c`
- `0x180035b08`
- `0x1800c631c`
- `0x1800c6804`
- `0x1800c6950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013bee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013ce6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013bee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013ce6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013ba7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013ba7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180013cf8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180013cf8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013bc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013c8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013bc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013c8a`

## pseudocode

```c
__int64 __fastcall XSLOCK::LockShared(XSLOCK *this, int fWait)
{
  unsigned int v3; // ebx
  DWORD v4; // eax
  DWORD v5; // ebp
  int v6; // edx
  XSLOCK::OWNERENTRY *v7; // rdi
  int v8; // r8d
  SEMAPHORE *p_m_semaphoreSharedWaiters; // r15
  XSLOCK::OWNERENTRY *v10; // rax
  DWORD CurrentThreadId; // eax
  unsigned __int64 v12; // rdi
  int v13; // edx
  int v14; // r8d
  XSLOCK::OWNERENTRY *ThreadOrFree; // r14
  XSLOCK::OWNERENTRY *v17; // rax

  EnterCriticalSection(&this->m_lock.critSec);
  v3 = 0;
  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInXSLOCK>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_FixNonAtomicAccessInXSLOCK>::GetImpl'::`2'::impl) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v12 = CurrentThreadId;
    if ( !this->m_cOwner )
    {
      this->m_ownerThreads[1].dwThreadId.m_h = CurrentThreadId;
      goto LABEL_4;
    }
    if ( this->m_isOwnedExclusive )
    {
      if ( this->m_ownerThreads[0].dwThreadId.m_h == CurrentThreadId )
        goto LABEL_8;
      ThreadOrFree = XSLOCK::FindThreadOrFree(this, 0);
    }
    else
    {
      v17 = XSLOCK::FindThreadOrFree(this, (OPAQUE_HANDLE<1>)CurrentThreadId);
      ThreadOrFree = v17;
      if ( !v17 )
        goto LABEL_5;
      if ( v17->dwThreadId.m_h == v12 )
      {
        v3 = 1;
        ++v17->ownerCount;
        goto LABEL_5;
      }
      if ( !this->m_cExclusiveWaiters )
      {
        v3 = 1;
        v17->dwThreadId.m_h = v12;
        v17->ownerCount = 1;
        goto LABEL_19;
      }
    }
    p_m_semaphoreSharedWaiters = &this->m_semaphoreSharedWaiters;
    if ( !this->m_semaphoreSharedWaiters.m_hSem )
      SEMAPHORE::Initialize(&this->m_semaphoreSharedWaiters, v13, v14);
    v3 = 1;
    ThreadOrFree->dwThreadId.m_h = v12;
    ThreadOrFree->ownerCount = 1;
    goto LABEL_28;
  }
  v4 = GetCurrentThreadId();
  v5 = v4;
  if ( this->m_cOwner )
  {
    if ( this->m_isOwnedExclusive )
    {
      if ( this->m_ownerThreads[0].threadId._Storage._Value == v4 )
      {
LABEL_8:
        v3 = 1;
        ++this->m_ownerThreads[0].ownerCount;
        goto LABEL_5;
      }
      if ( this->m_isOwnedExclusive )
      {
        v7 = XSLOCK::FindThreadOrFree(this, 0);
LABEL_11:
        p_m_semaphoreSharedWaiters = &this->m_semaphoreSharedWaiters;
        if ( !this->m_semaphoreSharedWaiters.m_hSem )
          SEMAPHORE::Initialize(&this->m_semaphoreSharedWaiters, v6, v8);
        v3 = 1;
        v7->threadId._Storage._Value = v5;
        v7->ownerCount = 1;
LABEL_28:
        ++this->m_cSharedWaiters;
        LeaveCriticalSection(&this->m_lock.critSec);
        WaitForSingleObject(p_m_semaphoreSharedWaiters->m_hSem, 0xFFFFFFFF);
        return v3;
      }
    }
    v10 = XSLOCK::FindThreadOrFree(this, v4);
    v7 = v10;
    if ( !v10 )
      goto LABEL_5;
    if ( v10->threadId._Storage._Value == v5 )
    {
      v3 = 1;
      ++v10->ownerCount;
      goto LABEL_5;
    }
    if ( this->m_cExclusiveWaiters )
      goto LABEL_11;
    v3 = 1;
    v10->threadId._Storage._Value = v5;
    v10->ownerCount = 1;
LABEL_19:
    ++this->m_cOwner;
    goto LABEL_5;
  }
  this->m_ownerThreads[1].threadId._Storage._Value = v4;
LABEL_4:
  v3 = 1;
  this->m_ownerThreads[1].ownerCount = 1;
  this->m_cOwner = 1;
LABEL_5:
  LeaveCriticalSection(&this->m_lock.critSec);
  return v3;
}

```

## disassembly

```asm
0x180013b8c  mov     [rsp+arg_0], rbx
0x180013b91  mov     [rsp+arg_8], rbp
0x180013b96  mov     [rsp+arg_10], rsi
0x180013b9b  push    rdi
0x180013b9c  push    r14
0x180013b9e  push    r15
0x180013ba0  sub     rsp, 20h
0x180013ba4  mov     rsi, this
0x180013ba7  call    cs:__imp_EnterCriticalSection
0x180013bae  nop     dword ptr [rax+rax+00h]
0x180013bb3  lea     this, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixNonAtomicAccessInXSLOCK@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInXSLOCK@@@details@3@XZ@4V453@A; __annotation("WILSTG:|57632796|Feature_FixNonAtomicAccessInXSLOCK|EnabledByDefault")
0x180013bba  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInXSLOCK@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInXSLOCK>::__private_IsEnabled(void)
0x180013bbf  xor     ebx, ebx
0x180013bc1  test    al, al
0x180013bc3  jz      loc_180013C8A
0x180013bc9  call    cs:__imp_GetCurrentThreadId
0x180013bd0  nop     dword ptr [rax+rax+00h]
0x180013bd5  mov     ebp, eax
0x180013bd7  cmp     [rsi+30h], ebx
0x180013bda  jnz     short loc_180013BFF
0x180013bdc  nop
0x180013bdd  mov     [rsi+50h], eax
0x180013be0  mov     ebx, 1
0x180013be5  mov     [rsi+54h], ebx
0x180013be8  mov     [rsi+30h], ebx
0x180013beb  mov     this, rsi; lpCriticalSection
0x180013bee  call    cs:__imp_LeaveCriticalSection
0x180013bf5  nop     dword ptr [rax+rax+00h]
0x180013bfa  jmp     loc_180013D04
0x180013bff  cmp     [rsi+78h], ebx
0x180013c02  jz      short loc_180013C4A
0x180013c04  mov     eax, [rsi+40h]
0x180013c07  nop
0x180013c08  cmp     eax, ebp
0x180013c0a  jnz     short loc_180013C16
0x180013c0c  mov     ebx, 1
0x180013c11  add     [rsi+44h], ebx
0x180013c14  jmp     short loc_180013BEB
0x180013c16  cmp     [rsi+78h], ebx
0x180013c19  jz      short loc_180013C4A
0x180013c1b  xor     edx, edx; dwThreadId
0x180013c1d  mov     this, rsi; this
0x180013c20  call    ?FindThreadOrFree@XSLOCK@@AEAAPEAUOWNERENTRY@1@K@Z; XSLOCK::FindThreadOrFree(ulong)
0x180013c25  mov     rdi, rax
0x180013c28  lea     r15, [rsi+68h]
0x180013c2c  cmp     [r15], rbx
0x180013c2f  jnz     short loc_180013C39
0x180013c31  mov     this, r15; this
0x180013c34  call    ?Initialize@SEMAPHORE@@QEAAXJJ@Z; SEMAPHORE::Initialize(long,long)
0x180013c39  nop
0x180013c3a  mov     ebx, 1
0x180013c3f  mov     [rdi+8], ebp
0x180013c42  mov     [rdi+0Ch], ebx
0x180013c45  jmp     loc_180013CE0
0x180013c4a  mov     edx, ebp; dwThreadId
0x180013c4c  mov     this, rsi; this
0x180013c4f  call    ?FindThreadOrFree@XSLOCK@@AEAAPEAUOWNERENTRY@1@K@Z; XSLOCK::FindThreadOrFree(ulong)
0x180013c54  mov     rdi, rax
0x180013c57  test    rax, rax
0x180013c5a  jz      short loc_180013BEB
0x180013c5c  mov     eax, [rax+8]
0x180013c5f  nop
0x180013c60  cmp     eax, ebp
0x180013c62  jnz     short loc_180013C71
0x180013c64  mov     ebx, 1
0x180013c69  add     [rdi+0Ch], ebx
0x180013c6c  jmp     loc_180013BEB
0x180013c71  cmp     [rsi+70h], ebx
0x180013c74  ja      short loc_180013C28
0x180013c76  nop
0x180013c77  mov     ebx, 1
0x180013c7c  mov     [rdi+8], ebp
0x180013c7f  mov     [rdi+0Ch], ebx
0x180013c82  add     [rsi+30h], ebx
0x180013c85  jmp     loc_180013BEB
0x180013c8a  call    cs:__imp_GetCurrentThreadId
0x180013c91  nop     dword ptr [rax+rax+00h]
0x180013c96  mov     edi, eax
0x180013c98  cmp     [rsi+30h], ebx
0x180013c9b  jnz     short loc_180013CA6
0x180013c9d  mov     [rsi+48h], rdi
0x180013ca1  jmp     loc_180013BE0
0x180013ca6  cmp     [rsi+78h], ebx
0x180013ca9  jz      short loc_180013D20
0x180013cab  cmp     [rsi+38h], rdi
0x180013caf  jz      loc_180013C0C
0x180013cb5  mov     rdx, rbx; dwThreadId
0x180013cb8  mov     this, rsi; this
0x180013cbb  call    ?FindThreadOrFree@XSLOCK@@AEAAPEAUOWNERENTRY@1@V?$OPAQUE_HANDLE@$00@@@Z; XSLOCK::FindThreadOrFree(OPAQUE_HANDLE<1>)
0x180013cc0  mov     r14, rax
0x180013cc3  lea     r15, [rsi+68h]
0x180013cc7  cmp     [r15], rbx
0x180013cca  jnz     short loc_180013CD4
0x180013ccc  mov     this, r15; this
0x180013ccf  call    ?Initialize@SEMAPHORE@@QEAAXJJ@Z; SEMAPHORE::Initialize(long,long)
0x180013cd4  mov     ebx, 1
0x180013cd9  mov     [r14], rdi
0x180013cdc  mov     [r14+0Ch], ebx
0x180013ce0  add     [rsi+74h], ebx
0x180013ce3  mov     this, rsi; lpCriticalSection
0x180013ce6  call    cs:__imp_LeaveCriticalSection
0x180013ced  nop     dword ptr [rax+rax+00h]
0x180013cf2  mov     this, [r15]; hHandle
0x180013cf5  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180013cf8  call    cs:__imp_WaitForSingleObject
0x180013cff  nop     dword ptr [rax+rax+00h]
0x180013d04  mov     rbp, [rsp+38h+arg_8]
0x180013d09  mov     eax, ebx
0x180013d0b  mov     rbx, [rsp+38h+arg_0]
0x180013d10  mov     rsi, [rsp+38h+arg_10]
0x180013d15  add     rsp, 20h
0x180013d19  pop     r15
0x180013d1b  pop     r14
0x180013d1d  pop     rdi
0x180013d1e  retn
0x180013d20  mov     rdx, rdi; dwThreadId
0x180013d23  mov     this, rsi; this
0x180013d26  call    ?FindThreadOrFree@XSLOCK@@AEAAPEAUOWNERENTRY@1@V?$OPAQUE_HANDLE@$00@@@Z; XSLOCK::FindThreadOrFree(OPAQUE_HANDLE<1>)
0x180013d2b  mov     r14, rax
0x180013d2e  test    rax, rax
0x180013d31  jz      loc_180013BEB
0x180013d37  cmp     [rax], rdi
0x180013d3a  jnz     short loc_180013D49
0x180013d3c  mov     ebx, 1
0x180013d41  add     [rax+0Ch], ebx
0x180013d44  jmp     loc_180013BEB
0x180013d49  cmp     [rsi+70h], ebx
0x180013d4c  ja      loc_180013CC3
0x180013d52  mov     ebx, 1
0x180013d57  mov     [rax], rdi
0x180013d5a  mov     [rax+0Ch], ebx
0x180013d5d  jmp     loc_180013C82
```
