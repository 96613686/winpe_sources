# XSLOCK::LockExclusive(void)

- ea: `0x180014cf4`
- end: `0x180014e27`
- name: `?LockExclusive@XSLOCK@@QEAAXXZ`
- size: `307`
- prototype: `void __fastcall(XSLOCK *this)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180013304`
- `0x180014cc8`
- `0x180014e30`
- `0x180016dc4`

## callees

- `0x180014cf4`
- `0x180039df8`
- `0x180044fd0`
- `0x1800c6950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014d64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014da2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014dc2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014e0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014d64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014da2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014dc2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014e0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014d09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014d09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014d25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014d72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014d25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014d72`

## pseudocode

```c
void __fastcall XSLOCK::LockExclusive(XSLOCK *this)
{
  DWORD CurrentThreadId; // eax
  int v3; // edx
  int v4; // r8d
  unsigned int v5; // ebx
  EVENT *p_m_eventExclusiveWaiters; // rsi
  DWORD v7; // eax
  unsigned __int64 v8; // rbx
  unsigned int v9; // edx
  unsigned int v10; // edx

  while ( 1 )
  {
    EnterCriticalSection(&this->m_lock.critSec);
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInXSLOCK>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_FixNonAtomicAccessInXSLOCK>::GetImpl'::`2'::impl) )
      break;
    CurrentThreadId = GetCurrentThreadId();
    v5 = CurrentThreadId;
    if ( !this->m_cOwner )
    {
      this->m_isOwnedExclusive = 1;
      this->m_ownerThreads[0].threadId._Storage._Value = CurrentThreadId;
      goto LABEL_16;
    }
    if ( this->m_isOwnedExclusive && this->m_ownerThreads[0].threadId._Storage._Value == CurrentThreadId )
      goto LABEL_14;
    p_m_eventExclusiveWaiters = &this->m_eventExclusiveWaiters;
    if ( this->m_eventExclusiveWaiters.m_hEvent )
    {
      ++this->m_cExclusiveWaiters;
      LeaveCriticalSection(&this->m_lock.critSec);
      EVENT::Wait(&this->m_eventExclusiveWaiters, v10);
      this->m_ownerThreads[0].threadId._Storage._Value = v5;
      return;
    }
LABEL_6:
    EVENT::Initialize(p_m_eventExclusiveWaiters, v3, v4);
    LeaveCriticalSection(&this->m_lock.critSec);
  }
  v7 = GetCurrentThreadId();
  v8 = v7;
  if ( this->m_cOwner )
  {
    if ( this->m_isOwnedExclusive && this->m_ownerThreads[0].dwThreadId.m_h == v7 )
    {
LABEL_14:
      ++this->m_ownerThreads[0].ownerCount;
      goto LABEL_17;
    }
    p_m_eventExclusiveWaiters = &this->m_eventExclusiveWaiters;
    if ( this->m_eventExclusiveWaiters.m_hEvent )
    {
      ++this->m_cExclusiveWaiters;
      LeaveCriticalSection(&this->m_lock.critSec);
      EVENT::Wait(&this->m_eventExclusiveWaiters, v9);
      this->m_ownerThreads[0].dwThreadId.m_h = v8;
      return;
    }
    goto LABEL_6;
  }
  this->m_isOwnedExclusive = 1;
  this->m_ownerThreads[0].dwThreadId.m_h = v7;
LABEL_16:
  this->m_cOwner = 1;
  this->m_ownerThreads[0].ownerCount = 1;
LABEL_17:
  LeaveCriticalSection(&this->m_lock.critSec);
}

```

## disassembly

```asm
0x180014cf4  mov     [rsp+arg_0], rbx
0x180014cf9  mov     [rsp+arg_8], rsi
0x180014cfe  push    rdi
0x180014cff  sub     rsp, 20h
0x180014d03  mov     rdi, this
0x180014d06  mov     this, rdi; lpCriticalSection
0x180014d09  call    cs:__imp_EnterCriticalSection
0x180014d10  nop     dword ptr [rax+rax+00h]
0x180014d15  lea     this, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixNonAtomicAccessInXSLOCK@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInXSLOCK@@@details@3@XZ@4V453@A; __annotation("WILSTG:|57632796|Feature_FixNonAtomicAccessInXSLOCK|EnabledByDefault")
0x180014d1c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInXSLOCK@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInXSLOCK>::__private_IsEnabled(void)
0x180014d21  test    al, al
0x180014d23  jz      short loc_180014D72
0x180014d25  call    cs:__imp_GetCurrentThreadId
0x180014d2c  nop     dword ptr [rax+rax+00h]
0x180014d31  cmp     dword ptr [rdi+30h], 0
0x180014d35  mov     ebx, eax
0x180014d37  jz      loc_180014DDC
0x180014d3d  cmp     dword ptr [rdi+78h], 0
0x180014d41  jz      short loc_180014D4F
0x180014d43  mov     ecx, [rdi+40h]
0x180014d46  nop
0x180014d47  cmp     ecx, eax
0x180014d49  jz      loc_180014DE9
0x180014d4f  lea     rsi, [rdi+60h]
0x180014d53  cmp     qword ptr [rsi], 0
0x180014d57  jnz     short loc_180014DBC
0x180014d59  mov     this, rsi; this
0x180014d5c  call    ?Initialize@EVENT@@QEAAXHH@Z; EVENT::Initialize(int,int)
0x180014d61  mov     this, rdi; lpCriticalSection
0x180014d64  call    cs:__imp_LeaveCriticalSection
0x180014d6b  nop     dword ptr [rax+rax+00h]
0x180014d70  jmp     short loc_180014D06
0x180014d72  call    cs:__imp_GetCurrentThreadId
0x180014d79  nop     dword ptr [rax+rax+00h]
0x180014d7e  cmp     dword ptr [rdi+30h], 0
0x180014d82  mov     ebx, eax
0x180014d84  jz      short loc_180014DEE
0x180014d86  cmp     dword ptr [rdi+78h], 0
0x180014d8a  jz      short loc_180014D92
0x180014d8c  cmp     [rdi+38h], rbx
0x180014d90  jz      short loc_180014DE9
0x180014d92  lea     rsi, [rdi+60h]
0x180014d96  cmp     qword ptr [rsi], 0
0x180014d9a  jz      short loc_180014D59
0x180014d9c  inc     dword ptr [rdi+70h]
0x180014d9f  mov     this, rdi; lpCriticalSection
0x180014da2  call    cs:__imp_LeaveCriticalSection
0x180014da9  nop     dword ptr [rax+rax+00h]
0x180014dae  mov     this, rsi; this
0x180014db1  call    ?Wait@EVENT@@QEAAJK@Z; EVENT::Wait(ulong)
0x180014db6  mov     [rdi+38h], rbx
0x180014dba  jmp     short loc_180014E16
0x180014dbc  inc     dword ptr [rdi+70h]
0x180014dbf  mov     this, rdi; lpCriticalSection
0x180014dc2  call    cs:__imp_LeaveCriticalSection
0x180014dc9  nop     dword ptr [rax+rax+00h]
0x180014dce  mov     this, rsi; this
0x180014dd1  call    ?Wait@EVENT@@QEAAJK@Z; EVENT::Wait(ulong)
0x180014dd6  nop
0x180014dd7  mov     [rdi+40h], ebx
0x180014dda  jmp     short loc_180014E16
0x180014ddc  mov     dword ptr [rdi+78h], 1
0x180014de3  nop
0x180014de4  mov     [rdi+40h], ebx
0x180014de7  jmp     short loc_180014DF9
0x180014de9  inc     dword ptr [rdi+44h]
0x180014dec  jmp     short loc_180014E07
0x180014dee  mov     dword ptr [rdi+78h], 1
0x180014df5  mov     [rdi+38h], rbx
0x180014df9  mov     dword ptr [rdi+30h], 1
0x180014e00  mov     dword ptr [rdi+44h], 1
0x180014e07  mov     this, rdi; lpCriticalSection
0x180014e0a  call    cs:__imp_LeaveCriticalSection
0x180014e11  nop     dword ptr [rax+rax+00h]
0x180014e16  mov     rbx, [rsp+28h+arg_0]
0x180014e1b  mov     rsi, [rsp+28h+arg_8]
0x180014e20  add     rsp, 20h
0x180014e24  pop     rdi
0x180014e25  retn
```
