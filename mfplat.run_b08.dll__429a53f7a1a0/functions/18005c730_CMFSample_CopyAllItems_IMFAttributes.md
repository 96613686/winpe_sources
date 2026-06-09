# CMFSample::CopyAllItems(IMFAttributes *)

- ea: `0x18005c730`
- end: `0x18005c839`
- name: `?CopyAllItems@CMFSample@@UEAAJPEAUIMFAttributes@@@Z`
- size: `265`
- prototype: `__int64 __fastcall(CMFSample *__hidden this, struct IMFAttributes *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18005c730`
- `0x18013a180`
- `0x18013a1f0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005c77e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005c77e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005c7fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005c7fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005c806`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005c806`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c766`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c7d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c766`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c7d8`

## pseudocode

```c
__int64 __fastcall CMFSample::CopyAllItems(CMFSample *this, struct IMFAttributes *a2)
{
  unsigned int *p_m_cUsedEntries; // rsi
  unsigned int *p_m_dwRecursionCount; // rdi
  int v6; // r14d
  __int64 i; // r15
  DWORD CurrentThreadId; // eax
  __int64 m_OwningThreadId; // rcx

  p_m_cUsedEntries = &this->m_cUsedEntries;
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 8) != 0 )
    McTemplateU0pqp_EventWriteTransfer((_DWORD)this, (_DWORD)a2, (_DWORD)this, *p_m_cUsedEntries, (char)a2);
  p_m_dwRecursionCount = &this->m_Lock.m_dwRecursionCount;
  if ( this->m_Lock.m_OwningThreadId == GetCurrentThreadId() )
    ++*p_m_dwRecursionCount;
  else
    AcquireSRWLockShared(&this->m_Lock.m_SRWLock);
  v6 = a2->DeleteAllItems(a2);
  if ( v6 >= 0 )
  {
    for ( i = 0; (unsigned int)i < *p_m_cUsedEntries; i = (unsigned int)(i + 1) )
    {
      v6 = a2->SetItem(a2, (const _GUID *)&this->m_pEntries[i], &this->m_pEntries[i].m_Value);
      if ( v6 < 0 )
        break;
    }
  }
  CurrentThreadId = GetCurrentThreadId();
  m_OwningThreadId = this->m_Lock.m_OwningThreadId;
  if ( (_DWORD)m_OwningThreadId == CurrentThreadId )
  {
    if ( *p_m_dwRecursionCount )
    {
      --*p_m_dwRecursionCount;
    }
    else
    {
      this->m_Lock.m_OwningThreadId = 0;
      ReleaseSRWLockExclusive(&this->m_Lock.m_SRWLock);
    }
  }
  else
  {
    ReleaseSRWLockShared(&this->m_Lock.m_SRWLock);
  }
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 8) != 0 )
    McTemplateU0pq_EventWriteTransfer(m_OwningThreadId, &Attributes_CopyAllItems_Stop, this, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005c730  push    rbx
0x18005c732  push    rbp
0x18005c733  push    rsi
0x18005c734  push    rdi
0x18005c735  push    r12
0x18005c737  push    r14
0x18005c739  push    r15
0x18005c73b  sub     rsp, 30h
0x18005c73f  test    byte ptr cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 8
0x18005c746  lea     rsi, [rcx+24h]
0x18005c74a  mov     r12, rdx
0x18005c74d  mov     rbp, rcx
0x18005c750  jz      short loc_18005C762
0x18005c752  mov     r9d, [rsi]
0x18005c755  mov     r8, rcx
0x18005c758  mov     [rsp+68h+var_48], rdx
0x18005c75d  call    McTemplateU0pqp_EventWriteTransfer
0x18005c762  lea     rbx, [rbp+8]
0x18005c766  call    cs:__imp_GetCurrentThreadId
0x18005c76c  mov     ecx, [rbx+8]
0x18005c76f  lea     rdi, [rbx+0Ch]
0x18005c773  cmp     ecx, eax
0x18005c775  jnz     short loc_18005C77B
0x18005c777  inc     dword ptr [rdi]
0x18005c779  jmp     short loc_18005C784
0x18005c77b  mov     rcx, rbx; SRWLock
0x18005c77e  call    cs:__imp_AcquireSRWLockShared
0x18005c784  mov     rax, [r12]
0x18005c788  mov     rcx, r12
0x18005c78b  mov     rax, [rax+0A0h]
0x18005c792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c797  mov     r14d, eax
0x18005c79a  test    eax, eax
0x18005c79c  js      short loc_18005C7D8
0x18005c79e  xor     r15d, r15d
0x18005c7a1  cmp     [rsi], r15d
0x18005c7a4  jbe     short loc_18005C7D8
0x18005c7a6  mov     rax, [rbp+18h]
0x18005c7aa  lea     rcx, [r15+r15*4]
0x18005c7ae  lea     rdx, [rax+rcx*8]
0x18005c7b2  mov     rax, [r12]
0x18005c7b6  lea     r8, [rdx+10h]
0x18005c7ba  mov     rcx, r12
0x18005c7bd  mov     rax, [rax+90h]
0x18005c7c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c7c9  mov     r14d, eax
0x18005c7cc  test    eax, eax
0x18005c7ce  js      short loc_18005C7D8
0x18005c7d0  inc     r15d
0x18005c7d3  cmp     r15d, [rsi]
0x18005c7d6  jb      short loc_18005C7A6
0x18005c7d8  call    cs:__imp_GetCurrentThreadId
0x18005c7de  mov     ecx, [rbx+8]
0x18005c7e1  cmp     ecx, eax
0x18005c7e3  jnz     short loc_18005C803
0x18005c7e5  mov     eax, [rdi]
0x18005c7e7  test    eax, eax
0x18005c7e9  jz      short loc_18005C7F1
0x18005c7eb  dec     eax
0x18005c7ed  mov     [rdi], eax
0x18005c7ef  jmp     short loc_18005C80C
0x18005c7f1  mov     rcx, rbx; SRWLock
0x18005c7f4  mov     dword ptr [rbx+8], 0
0x18005c7fb  call    cs:__imp_ReleaseSRWLockExclusive
0x18005c801  jmp     short loc_18005C80C
0x18005c803  mov     rcx, rbx; SRWLock
0x18005c806  call    cs:__imp_ReleaseSRWLockShared
0x18005c80c  test    byte ptr cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 8
0x18005c813  jz      short loc_18005C827
0x18005c815  mov     r9d, r14d
0x18005c818  lea     rdx, Attributes_CopyAllItems_Stop
0x18005c81f  mov     r8, rbp
0x18005c822  call    McTemplateU0pq_EventWriteTransfer
0x18005c827  mov     eax, r14d
0x18005c82a  add     rsp, 30h
0x18005c82e  pop     r15
0x18005c830  pop     r14
0x18005c832  pop     r12
0x18005c834  pop     rdi
0x18005c835  pop     rsi
0x18005c836  pop     rbp
0x18005c837  pop     rbx
0x18005c838  retn
```
