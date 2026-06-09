# AccountPolicyCriticalSection::UnLock(void *)

- ea: `0x180007350`
- end: `0x180007b2f`
- name: `?UnLock@AccountPolicyCriticalSection@@QEAAKPEAX@Z`
- size: `2015`
- prototype: `unsigned int(AccountPolicyCriticalSection *__hidden this, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180006f70`

## callees

- `0x180007350`
- `0x180007b38`
- `0x180008244`
- `0x18000a4b0`
- `0x18005ce24`
- `0x180075ec0`
- `0x18007d304`
- `0x1800b4188`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000738d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800073fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000747c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000754a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000738d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800073fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000747c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000754a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800077b9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007a3e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800077b9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007a3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800073d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007411`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800074e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800075b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007606`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800073d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007411`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800074e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800075b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007606`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007833`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000794c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007833`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000794c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ab8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007828`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007aad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007828`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007aad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800074d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800075a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800074d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800075a3`

## string_xrefs

- `0x180007435`: `The reader was already unlocked by writer before.`
- `0x1800078ca`: `The reader was already unlocked by writer before.`
- `0x18000766b`: `The writer is cancelling lock in UnLock - %s.`
- `0x180007699`: `The writer is cancelling lock in UnLock - %s.`
- `0x1800078f9`: `The writer is cancelling lock in UnLock - %s.`
- `0x180007924`: `The writer is cancelling lock in UnLock - %s.`
- `0x18000777b`: `Signalling first writer with ID [%d]`
- `0x1800077a4`: `Signalling first writer with ID [%d]`
- `0x180007a00`: `Signalling first writer with ID [%d]`
- `0x180007a29`: `Signalling first writer with ID [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AccountPolicyCriticalSection::UnLock(AccountPolicyCriticalSection *this, void *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  __int64 v5; // r8
  _QWORD *j; // rcx
  void *v7; // rbp
  __int64 v8; // r8
  DWORD LastError; // ebx
  __int64 v10; // r14
  struct _RTL_CRITICAL_SECTION *v11; // rbp
  unsigned int v12; // r12d
  bool v13; // zf
  _QWORD *v14; // rax
  __int64 v15; // rax
  void *v16; // rcx
  __int64 v18; // r14
  struct _RTL_CRITICAL_SECTION *v19; // rbp
  unsigned int v20; // r12d
  _QWORD *v21; // rax
  __int64 v22; // rax
  void *v23; // rcx
  _QWORD *i; // rcx
  void *v25; // rbp
  struct _RWLOCK_CONTEXT *v26; // r13
  CRWLock *v27; // rcx
  struct _RWLOCK_CONTEXT *v28; // r13
  CRWLock *v29; // rcx
  struct _RWLOCK_CONTEXT *v30; // [rsp+78h] [rbp+10h] BYREF
  struct _RTL_CRITICAL_SECTION *v31; // [rsp+80h] [rbp+18h]

  if ( (*((_BYTE *)a2 + 12) & 2) == 0 )
  {
    if ( !*((_DWORD *)a2 + 7) )
    {
      v4 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 9);
      if ( !v4 )
        goto LABEL_14;
      EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 9));
      v8 = *((_QWORD *)this + 12);
      if ( v8 )
      {
        for ( i = **(_QWORD ***)v8; i != *(_QWORD **)v8; i = (_QWORD *)*i )
        {
          v25 = (void *)i[2];
          if ( v25 == a2 )
          {
            *(_QWORD *)i[1] = *i;
            *(_QWORD *)(*i + 8LL) = i[1];
            --*(_QWORD *)(v8 + 8);
            operator delete(i);
            LeaveCriticalSection(v4);
            if ( v25 )
              goto LABEL_36;
            goto LABEL_14;
          }
        }
      }
LABEL_13:
      LeaveCriticalSection(v4);
LABEL_14:
      LastError = 0;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"The reader was already unlocked by writer before.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"The reader was already unlocked by writer before.");
        }
      }
      goto LABEL_34;
    }
    if ( *((_DWORD *)a2 + 6) )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"The writer is cancelling lock in UnLock - %s.", *((_QWORD *)this + 13));
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"The writer is cancelling lock in UnLock - %s.", *((_QWORD *)this + 13));
        }
      }
      LastError = CRWLock::CancelLock(*((CRWLock **)this + 2), (struct _RWLOCK_CONTEXT **)a2 + 2);
      if ( LastError )
      {
        LastError = GetLastError();
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"CancelLock failed with 0x%x for %s", LastError, *((_QWORD *)this + 13));
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"CancelLock failed with 0x%x for %s", LastError, *((_QWORD *)this + 13));
          }
        }
        goto LABEL_34;
      }
    }
    else
    {
LABEL_36:
      v18 = *((_QWORD *)this + 2);
      LastError = 0;
      if ( *(_DWORD *)(*((_QWORD *)a2 + 2) + 16LL) )
      {
        v20 = CRWLock::WriterUnLock(*((CRWLock **)this + 2), (struct _RWLOCK_CONTEXT **)a2 + 2);
      }
      else
      {
        v19 = *(struct _RTL_CRITICAL_SECTION **)(v18 + 72);
        v31 = v19;
        if ( v19 )
          EnterCriticalSection(v19);
        v20 = 0;
        v13 = (*(_DWORD *)v18)-- == 1;
        if ( v13 )
        {
          v21 = *(_QWORD **)(v18 + 24);
          if ( v21 && v21[1] )
          {
            v30 = *(struct _RWLOCK_CONTEXT **)(*(_QWORD *)*v21 + 16LL);
            v28 = v30;
            STLWrap_List<_NOTIFY_CALLER_INFO *>::pop_front(v18 + 24);
            if ( v28 )
            {
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(4u, L"Signalling first writer with ID [%d]", *(unsigned int *)v28);
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(4u, L"Signalling first writer with ID [%d]", *(unsigned int *)v28);
                }
              }
              SetEvent(*((HANDLE *)v28 + 1));
              CRWLock::FreeLockContext(v29, &v30);
              *(_DWORD *)(v18 + 12) = 2;
            }
            else
            {
              v20 = 1359;
            }
          }
          else
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(4u, L"Setting lock state as notLocked");
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(4u, L"Setting lock state as notLocked");
              }
            }
            *(_DWORD *)(v18 + 12) = 0;
          }
        }
        v22 = *((_QWORD *)a2 + 2);
        if ( v22 )
        {
          v23 = *(void **)(v22 + 8);
          if ( v23 )
            CloseHandle(v23);
          *(_QWORD *)(*((_QWORD *)a2 + 2) + 8LL) = 0;
          LocalFree(*((HLOCAL *)a2 + 2));
          *((_QWORD *)a2 + 2) = 0;
        }
        if ( v19 )
          LeaveCriticalSection(v19);
      }
      if ( v20 )
      {
        LastError = GetLastError();
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"UnLock failed with 0x%x for %s", LastError, *((_QWORD *)this + 13));
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"UnLock failed with 0x%x for %s", LastError, *((_QWORD *)this + 13));
          }
        }
        goto LABEL_34;
      }
    }
    _InterlockedDecrement((volatile signed __int32 *)this + 6);
    goto LABEL_34;
  }
  if ( !*((_DWORD *)a2 + 7) )
  {
    v4 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 21);
    if ( !v4 )
      goto LABEL_14;
    EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 21));
    v5 = *((_QWORD *)this + 24);
    if ( v5 )
    {
      for ( j = **(_QWORD ***)v5; j != *(_QWORD **)v5; j = (_QWORD *)*j )
      {
        v7 = (void *)j[2];
        if ( v7 == a2 )
        {
          *(_QWORD *)j[1] = *j;
          *(_QWORD *)(*j + 8LL) = j[1];
          --*(_QWORD *)(v5 + 8);
          operator delete(j);
          LeaveCriticalSection(v4);
          if ( v7 )
            goto LABEL_18;
          goto LABEL_14;
        }
      }
    }
    goto LABEL_13;
  }
  if ( *((_DWORD *)a2 + 6) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"The writer is cancelling lock in UnLock - %s.", *((_QWORD *)this + 25));
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"The writer is cancelling lock in UnLock - %s.", *((_QWORD *)this + 25));
      }
    }
    LastError = CRWLock::CancelLock(*((CRWLock **)this + 14), (struct _RWLOCK_CONTEXT **)a2 + 2);
    if ( !LastError )
      goto LABEL_33;
    LastError = GetLastError();
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"CancelLock failed with 0x%x for %s", LastError, *((_QWORD *)this + 25));
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"CancelLock failed with 0x%x for %s", LastError, *((_QWORD *)this + 25));
      }
    }
  }
  else
  {
LABEL_18:
    v10 = *((_QWORD *)this + 14);
    LastError = 0;
    if ( *(_DWORD *)(*((_QWORD *)a2 + 2) + 16LL) )
    {
      v12 = CRWLock::WriterUnLock(*((CRWLock **)this + 14), (struct _RWLOCK_CONTEXT **)a2 + 2);
    }
    else
    {
      v11 = *(struct _RTL_CRITICAL_SECTION **)(v10 + 72);
      v31 = v11;
      if ( v11 )
        EnterCriticalSection(v11);
      v12 = 0;
      v13 = (*(_DWORD *)v10)-- == 1;
      if ( v13 )
      {
        v14 = *(_QWORD **)(v10 + 24);
        if ( v14 && v14[1] )
        {
          v30 = *(struct _RWLOCK_CONTEXT **)(*(_QWORD *)*v14 + 16LL);
          v26 = v30;
          STLWrap_List<_NOTIFY_CALLER_INFO *>::pop_front(v10 + 24);
          if ( v26 )
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(4u, L"Signalling first writer with ID [%d]", *(unsigned int *)v26);
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(4u, L"Signalling first writer with ID [%d]", *(unsigned int *)v26);
              }
            }
            SetEvent(*((HANDLE *)v26 + 1));
            CRWLock::FreeLockContext(v27, &v30);
            *(_DWORD *)(v10 + 12) = 2;
          }
          else
          {
            v12 = 1359;
          }
        }
        else
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(4u, L"Setting lock state as notLocked");
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(4u, L"Setting lock state as notLocked");
            }
          }
          *(_DWORD *)(v10 + 12) = 0;
        }
      }
      v15 = *((_QWORD *)a2 + 2);
      if ( v15 )
      {
        v16 = *(void **)(v15 + 8);
        if ( v16 )
          CloseHandle(v16);
        *(_QWORD *)(*((_QWORD *)a2 + 2) + 8LL) = 0;
        LocalFree(*((HLOCAL *)a2 + 2));
        *((_QWORD *)a2 + 2) = 0;
      }
      if ( v11 )
        LeaveCriticalSection(v11);
    }
    if ( !v12 )
    {
LABEL_33:
      _InterlockedDecrement((volatile signed __int32 *)this + 30);
      goto LABEL_34;
    }
    LastError = GetLastError();
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"UnLock failed with 0x%x for %s", LastError, *((_QWORD *)this + 25));
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"UnLock failed with 0x%x for %s", LastError, *((_QWORD *)this + 25));
      }
    }
  }
LABEL_34:
  CPolicyCriticalSection::DeletePolicySectionContext(a2);
  return LastError;
}

```

## disassembly

```asm
0x180007350  mov     [rsp+arg_0], rbx
0x180007355  push    rbp
0x180007356  push    rsi
0x180007357  push    rdi
0x180007358  push    r12
0x18000735a  push    r13
0x18000735c  push    r14
0x18000735e  push    r15
0x180007360  sub     rsp, 30h
0x180007364  mov     rdi, rdx
0x180007367  mov     rsi, rcx
0x18000736a  test    byte ptr [rdx+0Ch], 2
0x18000736e  jz      short loc_1800073E5
0x180007370  cmp     dword ptr [rdx+1Ch], 0
0x180007374  jnz     loc_18000744B
0x18000737a  mov     rbx, [rcx+0A8h]
0x180007381  test    rbx, rbx
0x180007384  jz      loc_180007417
0x18000738a  mov     rcx, rbx; lpCriticalSection
0x18000738d  call    cs:__imp_EnterCriticalSection
0x180007393  mov     r8, [rsi+0C0h]
0x18000739a  test    r8, r8
0x18000739d  jz      short loc_18000740E
0x18000739f  mov     rax, [r8]
0x1800073a2  mov     rcx, [rax]; Block
0x1800073a5  cmp     rcx, rax
0x1800073a8  jz      short loc_18000740E
0x1800073aa  mov     rbp, [rcx+10h]
0x1800073ae  cmp     rbp, rdi
0x1800073b1  jnz     loc_180007642
0x1800073b7  mov     rdx, [rcx+8]
0x1800073bb  mov     rax, [rcx]
0x1800073be  mov     [rdx], rax
0x1800073c1  mov     rdx, [rcx]
0x1800073c4  mov     rax, [rcx+8]
0x1800073c8  mov     [rdx+8], rax
0x1800073cc  dec     qword ptr [r8+8]
0x1800073d0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800073d5  mov     rcx, rbx; lpCriticalSection
0x1800073d8  call    cs:__imp_LeaveCriticalSection
0x1800073de  test    rbp, rbp
0x1800073e1  jnz     short loc_180007455
0x1800073e3  jmp     short loc_180007417
0x1800073e5  cmp     dword ptr [rdx+1Ch], 0
0x1800073e9  jnz     loc_180007519
0x1800073ef  mov     rbx, [rcx+48h]
0x1800073f3  test    rbx, rbx
0x1800073f6  jz      short loc_180007417
0x1800073f8  mov     rcx, rbx; lpCriticalSection
0x1800073fb  call    cs:__imp_EnterCriticalSection
0x180007401  mov     r8, [rsi+60h]
0x180007405  test    r8, r8
0x180007408  jnz     loc_1800075CD
0x18000740e  mov     rcx, rbx; lpCriticalSection
0x180007411  call    cs:__imp_LeaveCriticalSection
0x180007417  xor     ebx, ebx
0x180007419  cmp     cs:?g_dwDebugLevel@@3KA, ebx; ulong g_dwDebugLevel
0x18000741f  jz      loc_1800074FA
0x180007425  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000742c  test    rax, rax
0x18000742f  jz      loc_1800078B0
0x180007435  lea     rdx, aTheReaderWasAl; "The reader was already unlocked by writ"...
0x18000743c  mov     ecx, 2
0x180007441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007446  jmp     loc_1800074FA
0x18000744b  cmp     dword ptr [rdx+18h], 0
0x18000744f  jnz     loc_18000764F
0x180007455  mov     r14, [rsi+70h]
0x180007459  mov     rax, [rdi+10h]
0x18000745d  xor     ebx, ebx
0x18000745f  cmp     [rax+10h], ebx
0x180007462  jnz     loc_18000761A
0x180007468  mov     rbp, [r14+48h]
0x18000746c  mov     [rsp+68h+arg_10], rbp
0x180007474  test    rbp, rbp
0x180007477  jz      short loc_180007483
0x180007479  mov     rcx, rbp; lpCriticalSection
0x18000747c  call    cs:__imp_EnterCriticalSection
0x180007482  nop
0x180007483  mov     r12d, ebx
0x180007486  add     dword ptr [r14], 0FFFFFFFFh
0x18000748a  jnz     short loc_1800074B3
0x18000748c  lea     rcx, [r14+18h]
0x180007490  mov     rax, [rcx]
0x180007493  test    rax, rax
0x180007496  jz      short loc_1800074A2
0x180007498  cmp     [rax+8], r12
0x18000749c  jnz     loc_18000773E
0x1800074a2  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800074a9  jnz     loc_1800077D6
0x1800074af  mov     [r14+0Ch], ebx
0x1800074b3  mov     rax, [rdi+10h]
0x1800074b7  test    rax, rax
0x1800074ba  jz      short loc_1800074DF
0x1800074bc  mov     rcx, [rax+8]; hObject
0x1800074c0  test    rcx, rcx
0x1800074c3  jnz     loc_180007828
0x1800074c9  mov     rax, [rdi+10h]
0x1800074cd  mov     [rax+8], rbx
0x1800074d1  mov     rcx, [rdi+10h]; hMem
0x1800074d5  call    cs:__imp_LocalFree
0x1800074db  mov     [rdi+10h], rbx
0x1800074df  test    rbp, rbp
0x1800074e2  jz      short loc_1800074ED
0x1800074e4  mov     rcx, rbp; lpCriticalSection
0x1800074e7  call    cs:__imp_LeaveCriticalSection
0x1800074ed  test    r12d, r12d
0x1800074f0  jnz     loc_180007833
0x1800074f6  lock dec dword ptr [rsi+78h]
0x1800074fa  mov     rcx, rdi; hMem
0x1800074fd  call    ?DeletePolicySectionContext@CPolicyCriticalSection@@CAXPEAU_POLICY_SECTION_CONTEXT@@@Z; CPolicyCriticalSection::DeletePolicySectionContext(_POLICY_SECTION_CONTEXT *)
0x180007502  mov     eax, ebx
0x180007504  mov     rbx, [rsp+68h+arg_0]
0x180007509  add     rsp, 30h
0x18000750d  pop     r15
0x18000750f  pop     r14
0x180007511  pop     r13
0x180007513  pop     r12
0x180007515  pop     rdi
0x180007516  pop     rsi
0x180007517  pop     rbp
0x180007518  retn
0x180007519  cmp     dword ptr [rdx+18h], 0
0x18000751d  jnz     loc_1800078E0
0x180007523  mov     r14, [rsi+10h]
0x180007527  mov     rax, [rdi+10h]
0x18000752b  xor     ebx, ebx
0x18000752d  cmp     [rax+10h], ebx
0x180007530  jnz     loc_18000762E
0x180007536  mov     rbp, [r14+48h]
0x18000753a  mov     [rsp+68h+arg_10], rbp
0x180007542  test    rbp, rbp
0x180007545  jz      short loc_180007551
0x180007547  mov     rcx, rbp; lpCriticalSection
0x18000754a  call    cs:__imp_EnterCriticalSection
0x180007550  nop
0x180007551  mov     r12d, ebx
0x180007554  add     dword ptr [r14], 0FFFFFFFFh
0x180007558  jnz     short loc_180007581
0x18000755a  lea     rcx, [r14+18h]
0x18000755e  mov     rax, [rcx]
0x180007561  test    rax, rax
0x180007564  jz      short loc_180007570
0x180007566  cmp     [rax+8], r12
0x18000756a  jnz     loc_1800079C3
0x180007570  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180007577  jnz     loc_180007A5B
0x18000757d  mov     [r14+0Ch], ebx
0x180007581  mov     rax, [rdi+10h]
0x180007585  test    rax, rax
0x180007588  jz      short loc_1800075AD
0x18000758a  mov     rcx, [rax+8]; hObject
0x18000758e  test    rcx, rcx
0x180007591  jnz     loc_180007AAD
0x180007597  mov     rax, [rdi+10h]
0x18000759b  mov     [rax+8], rbx
0x18000759f  mov     rcx, [rdi+10h]; hMem
0x1800075a3  call    cs:__imp_LocalFree
0x1800075a9  mov     [rdi+10h], rbx
0x1800075ad  test    rbp, rbp
0x1800075b0  jz      short loc_1800075BB
0x1800075b2  mov     rcx, rbp; lpCriticalSection
0x1800075b5  call    cs:__imp_LeaveCriticalSection
0x1800075bb  test    r12d, r12d
0x1800075be  jnz     loc_180007AB8
0x1800075c4  lock dec dword ptr [rsi+18h]
0x1800075c8  jmp     loc_1800074FA
0x1800075cd  mov     rax, [r8]
0x1800075d0  mov     rcx, [rax]; Block
0x1800075d3  cmp     rcx, rax
0x1800075d6  jz      loc_18000740E
0x1800075dc  mov     rbp, [rcx+10h]
0x1800075e0  cmp     rbp, rdi
0x1800075e3  jnz     short loc_18000764A
0x1800075e5  mov     rdx, [rcx+8]
0x1800075e9  mov     rax, [rcx]
0x1800075ec  mov     [rdx], rax
0x1800075ef  mov     rdx, [rcx]
0x1800075f2  mov     rax, [rcx+8]
0x1800075f6  mov     [rdx+8], rax
0x1800075fa  dec     qword ptr [r8+8]
0x1800075fe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007603  mov     rcx, rbx; lpCriticalSection
0x180007606  call    cs:__imp_LeaveCriticalSection
0x18000760c  test    rbp, rbp
0x18000760f  jnz     loc_180007523
0x180007615  jmp     loc_180007417
0x18000761a  lea     rdx, [rdi+10h]; struct _RWLOCK_CONTEXT **
0x18000761e  mov     rcx, r14; this
0x180007621  call    ?WriterUnLock@CRWLock@@AEAAKPEAPEAU_RWLOCK_CONTEXT@@@Z; CRWLock::WriterUnLock(_RWLOCK_CONTEXT * *)
0x180007626  mov     r12d, eax
0x180007629  jmp     loc_1800074ED
0x18000762e  lea     rdx, [rdi+10h]; struct _RWLOCK_CONTEXT **
0x180007632  mov     rcx, r14; this
0x180007635  call    ?WriterUnLock@CRWLock@@AEAAKPEAPEAU_RWLOCK_CONTEXT@@@Z; CRWLock::WriterUnLock(_RWLOCK_CONTEXT * *)
0x18000763a  mov     r12d, eax
0x18000763d  jmp     loc_1800075BB
0x180007642  mov     rcx, [rcx]
0x180007645  jmp     loc_1800073A5
0x18000764a  mov     rcx, [rcx]
0x18000764d  jmp     short loc_1800075D3
0x18000764f  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180007656  jz      short loc_1800076AA
0x180007658  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000765f  test    rax, rax
0x180007662  jz      short loc_18000767E
0x180007664  mov     r8, [rcx+0C8h]
0x18000766b  lea     rdx, aTheWriterIsCan; "The writer is cancelling lock in UnLock"...
0x180007672  mov     ecx, 4
0x180007677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000767c  jmp     short loc_1800076AA
0x18000767e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180007686  jz      short loc_1800076AA
0x180007688  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180007690  jz      short loc_1800076AA
0x180007692  mov     r8, [rcx+0C8h]
0x180007699  lea     rdx, aTheWriterIsCan; "The writer is cancelling lock in UnLock"...
0x1800076a0  mov     ecx, 4; unsigned int
0x1800076a5  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800076aa  lea     rdx, [rdi+10h]; struct _RWLOCK_CONTEXT **
0x1800076ae  mov     rcx, [rsi+70h]; this
0x1800076b2  call    ?CancelLock@CRWLock@@QEAAKPEAPEAU_RWLOCK_CONTEXT@@@Z; CRWLock::CancelLock(_RWLOCK_CONTEXT * *)
0x1800076b7  mov     ebx, eax
0x1800076b9  test    eax, eax
0x1800076bb  jz      loc_1800074F6
0x1800076c1  call    cs:__imp_GetLastError
0x1800076c7  mov     ebx, eax
0x1800076c9  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x1800076d0  jz      loc_1800074FA
0x1800076d6  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800076dd  test    rax, rax
0x1800076e0  jz      short loc_180007702
0x1800076e2  mov     r9, [rsi+0C8h]
0x1800076e9  mov     r8d, ebx
0x1800076ec  lea     rdx, aCancellockFail; "CancelLock failed with 0x%x for %s"
0x1800076f3  mov     ecx, 2
0x1800076f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076fd  jmp     loc_1800074FA
0x180007702  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18000770a  jz      loc_1800074FA
0x180007710  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180007718  jz      loc_1800074FA
0x18000771e  mov     r9, [rsi+0C8h]
0x180007725  mov     r8d, ebx
0x180007728  lea     rdx, aCancellockFail; "CancelLock failed with 0x%x for %s"
0x18000772f  mov     ecx, 2; unsigned int
0x180007734  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180007739  jmp     loc_1800074FA
0x18000773e  mov     rax, [rax]
0x180007741  mov     rdx, [rax]
0x180007744  mov     r13, [rdx+10h]
0x180007748  mov     [rsp+68h+arg_8], r13
0x18000774d  call    ?pop_front@?$STLWrap_List@PEAU_NOTIFY_CALLER_INFO@@@@QEAAXXZ; STLWrap_List<_NOTIFY_CALLER_INFO *>::pop_front(void)
0x180007752  test    r13, r13
0x180007755  jnz     short loc_180007762
0x180007757  mov     r12d, 54Fh
0x18000775d  jmp     loc_1800074B3
0x180007762  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180007769  jz      short loc_1800077B5
0x18000776b  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180007772  test    rax, rax
0x180007775  jz      short loc_18000778E
0x180007777  mov     r8d, [r13+0]
0x18000777b  lea     rdx, aSignallingFirs; "Signalling first writer with ID [%d]"
0x180007782  mov     ecx, 4
0x180007787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000778c  jmp     short loc_1800077B5
0x18000778e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180007795  jz      short loc_1800077B5
0x180007797  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18000779e  jz      short loc_1800077B5
0x1800077a0  mov     r8d, [r13+0]
0x1800077a4  lea     rdx, aSignallingFirs; "Signalling first writer with ID [%d]"
0x1800077ab  mov     ecx, 4; unsigned int
0x1800077b0  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800077b5  mov     rcx, [r13+8]; hEvent
0x1800077b9  call    cs:__imp_SetEvent
0x1800077bf  lea     rdx, [rsp+68h+arg_8]; struct _RWLOCK_CONTEXT **
0x1800077c4  call    ?FreeLockContext@CRWLock@@AEAAXPEAPEAU_RWLOCK_CONTEXT@@@Z; CRWLock::FreeLockContext(_RWLOCK_CONTEXT * *)
0x1800077c9  mov     dword ptr [r14+0Ch], 2
0x1800077d1  jmp     loc_1800074B3
0x1800077d6  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800077dd  test    rax, rax
0x1800077e0  jz      short loc_1800077F8
0x1800077e2  lea     rdx, aSettingLockSta; "Setting lock state as notLocked"
0x1800077e9  mov     ecx, 4
0x1800077ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077f3  jmp     loc_1800074AF
0x1800077f8  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800077ff  jz      loc_1800074AF
0x180007805  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18000780c  jz      loc_1800074AF
0x180007812  lea     rdx, aSettingLockSta; "Setting lock state as notLocked"
0x180007819  mov     ecx, 4; unsigned int
0x18000781e  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180007823  jmp     loc_1800074AF
0x180007828  call    cs:__imp_CloseHandle
0x18000782e  jmp     loc_1800074C9
0x180007833  call    cs:__imp_GetLastError
0x180007839  mov     ebx, eax
  ... truncated ...
```
