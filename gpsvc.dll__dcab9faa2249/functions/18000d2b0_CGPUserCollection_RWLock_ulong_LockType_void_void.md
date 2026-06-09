# CGPUserCollection::RWLock(ulong,LockType,void * *,void *)

- ea: `0x18000d2b0`
- end: `0x18000de29`
- name: `?RWLock@CGPUserCollection@@QEAAKKW4LockType@@PEAPEAXPEAX@Z`
- size: `2937`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `12`
- tags: ``

## callers

- `0x180009d2c`
- `0x18000c398`
- `0x18000c6a0`
- `0x18000cc30`
- `0x18000e5f0`
- `0x18000fa40`
- `0x180010760`
- `0x180044f08`
- `0x180045010`
- `0x180090284`

## callees

- `0x18000a4b0`
- `0x18000a504`
- `0x18000a52c`
- `0x18000d2b0`
- `0x18000de30`
- `0x180039148`
- `0x18004dc00`
- `0x180075ec0`
- `0x1800b2738`
- `0x1800b4188`
- `0x1800b4258`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d345`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d44c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d52e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d345`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d44c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d52e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000da71`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000da71`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d738`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d8ec`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d738`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d8ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d3cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d475`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d5a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d3cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d475`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d5a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d64e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d683`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d64e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d683`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d356`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d401`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d53f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d5c3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d89d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d356`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d401`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d53f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d5c3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d89d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d3dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d643`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d3dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d643`

## string_xrefs

- `0x18000d6b7`: `CGPUserCollection::RWLock Lock Called to acquire READ Lock`
- `0x18000d6e7`: `CGPUserCollection::RWLock Lock Called to acquire READ Lock`
- `0x18000d509`: `CGPUserCollection::RWLock Lock Called to acquire WRITER Lock`
- `0x18000d70a`: `CGPUserCollection::RWLock Lock Called to acquire WRITER Lock`
- `0x18000dc14`: `CGPUserCollection::RWLock Failed to create user collection context`
- `0x18000dc44`: `CGPUserCollection::RWLock Failed to create user collection context`
- `0x18000dc5c`: `CGPUserCollection::Adding reader to Reader list`
- `0x18000dc8c`: `CGPUserCollection::Adding reader to Reader list`
- `0x18000dcc4`: `CGPUserCollection::RWLock Failed to add reader in to reader list`
- `0x18000dd77`: `CGPUserCollection::RWLock Failed to add reader in to reader list`
- `0x18000dcfb`: `Number of readers in the list = %d`
- `0x18000dd45`: `Number of readers in the list = %d`
- `0x18000d7b4`: `Reader has to wait for lock. ReaderID : %d.`
- `0x18000d7f7`: `Reader has to wait for lock. ReaderID : %d.`
- `0x18000d83b`: `Writer Lock got immediately.`
- `0x18000d86d`: `Writer Lock got immediately.`
- `0x18000d96b`: `Writer has to wait for lock. WriterID : %d.`
- `0x18000d996`: `Writer has to wait for lock. WriterID : %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CGPUserCollection::RWLock(__int64 a1, int a2, int a3, _QWORD *a4, void *a5)
{
  _QWORD *v5; // rax
  HANDLE *v8; // r14
  void *v9; // r13
  int *v10; // rdi
  struct _RTL_CRITICAL_SECTION *v11; // rax
  CRWLock *v12; // rcx
  HANDLE *v13; // rsi
  struct _RWLOCK_CONTEXT *v14; // rbx
  int v15; // ecx
  __int64 v16; // rax
  int v17; // eax
  DWORD LastError; // esi
  _QWORD *v19; // rax
  struct _RTL_CRITICAL_SECTION *v20; // rbx
  CRWLock *v22; // rcx
  HLOCAL v23; // rsi
  int v24; // eax
  HANDLE EventW; // rax
  HANDLE v26; // rcx
  int v27; // eax
  _DWORD *v28; // rbx
  HLOCAL v29; // rax
  HANDLE *v30; // rdi
  HANDLE v31; // rax
  HANDLE v32; // rcx
  BOOL v33; // ebx
  DWORD v34; // eax
  DWORD v35; // eax
  __int64 v36; // rax
  __int64 v37; // r8
  __int64 v38; // rax
  __int64 v39; // r8
  _DWORD *v40; // [rsp+30h] [rbp-50h] BYREF
  struct _RWLOCK_CONTEXT *v41; // [rsp+38h] [rbp-48h] BYREF
  struct _RWLOCK_CONTEXT *v42; // [rsp+40h] [rbp-40h] BYREF
  _DWORD *v43; // [rsp+48h] [rbp-38h] BYREF
  HANDLE *v44; // [rsp+50h] [rbp-30h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+58h] [rbp-28h]
  struct _RTL_CRITICAL_SECTION *v46; // [rsp+60h] [rbp-20h]
  CRWLock *v47; // [rsp+68h] [rbp-18h]
  HANDLE Handles[2]; // [rsp+70h] [rbp-10h] BYREF
  HANDLE hSourceHandle; // [rsp+C0h] [rbp+40h] BYREF
  int v50; // [rsp+C8h] [rbp+48h]
  _QWORD *v51; // [rsp+D8h] [rbp+58h]

  v51 = a4;
  v50 = a2;
  v5 = a4;
  v8 = 0;
  v42 = 0;
  *(_OWORD *)Handles = 0;
  if ( a3 )
  {
    v50 = 0;
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_3;
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGPUserCollection::RWLock Lock Called to acquire WRITER Lock");
LABEL_68:
      v5 = v51;
      goto LABEL_3;
    }
    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGPUserCollection::RWLock Lock Called to acquire WRITER Lock");
      goto LABEL_68;
    }
  }
  else
  {
    v50 = 1;
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_3;
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGPUserCollection::RWLock Lock Called to acquire READ Lock");
      goto LABEL_68;
    }
    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGPUserCollection::RWLock Lock Called to acquire READ Lock");
      goto LABEL_68;
    }
  }
LABEL_3:
  if ( *(_QWORD *)(a1 + 48) && v5 )
  {
    v9 = 0;
    *v5 = 0;
    v10 = (int *)(a1 + 56);
    v47 = (CRWLock *)(a1 + 56);
    v11 = *(struct _RTL_CRITICAL_SECTION **)(a1 + 128);
    lpCriticalSection = v11;
    if ( !a3 )
    {
      v46 = v11;
      if ( v11 )
        EnterCriticalSection(v11);
      v13 = (HANDLE *)LocalAlloc(0x40u, 0x18u);
      v44 = v13;
      v14 = (struct _RWLOCK_CONTEXT *)v13;
      v41 = (struct _RWLOCK_CONTEXT *)v13;
      if ( v13 )
      {
        v15 = ++*(_DWORD *)(a1 + 60);
        v16 = *(_QWORD *)(a1 + 80);
        if ( (!v16 || !*(_QWORD *)(v16 + 8)) && *(_DWORD *)(a1 + 68) != 2 )
        {
          v17 = *v10;
          if ( !*v10 )
            *(_DWORD *)(a1 + 68) = 1;
          *v10 = v17 + 1;
          *(_DWORD *)v13 = v15;
          v13[1] = 0;
LABEL_15:
          *((_DWORD *)v13 + 4) = 0;
          v14 = 0;
          v8 = v13;
          v42 = (struct _RWLOCK_CONTEXT *)v13;
          LastError = 0;
          goto LABEL_16;
        }
        hSourceHandle = 0;
        v40 = LocalAlloc(0x40u, 0x18u);
        if ( v40 )
        {
          EventW = CreateEventW(0, 0, 0, 0);
          XHandle::operator=(&hSourceHandle, EventW);
          v26 = hSourceHandle;
          if ( hSourceHandle )
          {
            v27 = *(_DWORD *)(a1 + 60);
            v28 = v40;
            *v40 = v27;
            *((_QWORD *)v28 + 1) = v26;
            *(_DWORD *)v13 = v27;
            LastError = DuplicateEventHandle(v26, v13 + 1);
            if ( !LastError )
            {
              v43 = v28;
              LastError = STLWrap_List<_RWLOCK_CONTEXT *>::push_back(a1 + 72, &v43);
              if ( !LastError )
              {
                hSourceHandle = 0;
                v40 = 0;
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( g_lpDebugMsg )
                  {
                    g_lpDebugMsg(4u, L"Reader has to wait for lock. ReaderID : %d.", *(unsigned int *)(a1 + 60));
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(4u, L"Reader has to wait for lock. ReaderID : %d.", *(unsigned int *)(a1 + 60));
                  }
                }
                XHandle::~XHandle(&hSourceHandle);
                XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v40);
                v13 = v44;
                goto LABEL_15;
              }
            }
            XHandle::~XHandle(&hSourceHandle);
            XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v40);
          }
          else
          {
            LastError = GetLastError();
            XHandle::~XHandle(&hSourceHandle);
            XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v40);
            if ( !LastError )
            {
LABEL_16:
              if ( lpCriticalSection )
                LeaveCriticalSection(lpCriticalSection);
              goto LABEL_18;
            }
          }
        }
        else
        {
          LastError = 14;
        }
      }
      else
      {
        LastError = 14;
      }
      CRWLock::FreeLockContext(v12, &v41);
      v14 = v41;
      goto LABEL_16;
    }
    v46 = v11;
    if ( v11 )
      EnterCriticalSection(v11);
    v23 = LocalAlloc(0x40u, 0x18u);
    v43 = v23;
    v14 = (struct _RWLOCK_CONTEXT *)v23;
    v41 = (struct _RWLOCK_CONTEXT *)v23;
    if ( v23 )
    {
      v24 = ++*(_DWORD *)(a1 + 64);
      if ( !*(_DWORD *)(a1 + 68) )
      {
        *(_DWORD *)(a1 + 68) = 2;
        *(_DWORD *)v23 = v24;
        *((_QWORD *)v23 + 1) = 0;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"Writer Lock got immediately.");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"Writer Lock got immediately.");
          }
        }
LABEL_41:
        *((_DWORD *)v23 + 4) = 1;
        v14 = 0;
        v8 = (HANDLE *)v23;
        v42 = (struct _RWLOCK_CONTEXT *)v23;
        LastError = 0;
        goto LABEL_42;
      }
      v40 = 0;
      hSourceHandle = 0;
      v29 = LocalAlloc(0x40u, 0x18u);
      XPtrLF<_RWLOCK_CONTEXT>::operator=(&v40, v29);
      v30 = (HANDLE *)v40;
      if ( v40 )
      {
        v31 = CreateEventW(0, 0, 0, 0);
        XHandle::operator=(&hSourceHandle, v31);
        v32 = hSourceHandle;
        if ( !hSourceHandle )
        {
          LastError = GetLastError();
          XHandle::~XHandle(&hSourceHandle);
          XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v40);
          if ( !LastError )
            goto LABEL_42;
          goto LABEL_57;
        }
        *(_DWORD *)v30 = *(_DWORD *)(a1 + 64);
        v30[1] = v32;
        *(_DWORD *)v23 = *(_DWORD *)v30;
        LastError = DuplicateEventHandle(v32, (LPHANDLE)v23 + 1);
        if ( !LastError )
        {
          v44 = v30;
          LastError = STLWrap_List<_RWLOCK_CONTEXT *>::push_back(a1 + 80, &v44);
          if ( !LastError )
          {
            hSourceHandle = 0;
            v40 = 0;
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(4u, L"Writer has to wait for lock. WriterID : %d.", *(unsigned int *)(a1 + 64));
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(4u, L"Writer has to wait for lock. WriterID : %d.", *(unsigned int *)(a1 + 64));
              }
            }
            XHandle::~XHandle(&hSourceHandle);
            XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v40);
            v23 = v43;
            goto LABEL_41;
          }
        }
      }
      else
      {
        LastError = 14;
      }
      XHandle::~XHandle(&hSourceHandle);
      XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v40);
    }
    else
    {
      LastError = 14;
    }
LABEL_57:
    CRWLock::FreeLockContext(v22, &v41);
    v14 = v41;
LABEL_42:
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
LABEL_18:
    if ( v14 )
      LocalFree(v14);
    if ( LastError )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"CGPUserCollection::RWLock Failed to acquire lock!");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"CGPUserCollection::RWLock Failed to acquire lock!");
        }
      }
      goto LABEL_52;
    }
    if ( !v8[1] )
      goto LABEL_22;
    v33 = a5 != 0;
    Handles[0] = v8[1];
    Handles[1] = a5;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CGPUserCollection::RWLock Entering WaitForMultipleObjectsEx with timeout %d", 0xFFFFFFFFLL);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(
          4u,
          L"CGPUserCollection::RWLock Entering WaitForMultipleObjectsEx with timeout %d",
          0xFFFFFFFFLL);
      }
    }
    v34 = WaitForMultipleObjectsEx(v33 + 1, Handles, 0, 0xFFFFFFFF, 0);
    LastError = v34;
    if ( v34 )
    {
      v35 = v34 - 1;
      if ( !v35 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"Quit event signalled.");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"Quit event signalled.");
          }
        }
        LastError = 1223;
        goto LABEL_128;
      }
      if ( v35 == 257 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"Wait Timed out");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"Wait Timed out");
          }
        }
        LastError = 1460;
        goto LABEL_128;
      }
      if ( LastError )
      {
LABEL_128:
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"WaitForMultipleObjects failed with 0x%x", LastError);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"WaitForMultipleObjects failed with 0x%x", LastError);
          }
        }
LABEL_52:
        if ( v8 )
          CRWLock::CancelLock(v47, &v42);
        if ( v9 )
          LocalFree(v9);
        return LastError;
      }
    }
    else if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"Got the lock");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"Got the lock");
      }
    }
LABEL_22:
    v19 = LocalAlloc(0x40u, 0x10u);
    v9 = v19;
    if ( v19 )
    {
      *v19 = v8;
      *((_DWORD *)v19 + 2) = 0;
      *((_DWORD *)v19 + 3) = a3;
      LastError = 0;
      if ( !v50 )
      {
LABEL_28:
        *v51 = v9;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"CGPUserCollection::RWLock Lock taken successfully with status 0x%x ", LastError);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"CGPUserCollection::RWLock Lock taken successfully with status 0x%x ", LastError);
          }
        }
        return LastError;
      }
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"CGPUserCollection::Adding reader to Reader list");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"CGPUserCollection::Adding reader to Reader list");
        }
      }
      hSourceHandle = v9;
      v20 = *(struct _RTL_CRITICAL_SECTION **)(a1 + 40);
      if ( v20 )
      {
        v46 = *(struct _RTL_CRITICAL_SECTION **)(a1 + 40);
        EnterCriticalSection(v20);
        LastError = STLWrap_List<_USER_COLLECTION_CONTEXT *>::push_front(a1 + 136, &hSourceHandle);
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            v36 = *(_QWORD *)(a1 + 136);
            if ( v36 )
              v37 = *(unsigned int *)(v36 + 8);
            else
              v37 = 0;
            g_lpDebugMsg(4u, L"Number of readers in the list = %d", v37);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            v38 = *(_QWORD *)(a1 + 136);
            if ( v38 )
              v39 = *(unsigned int *)(v38 + 8);
            else
              v39 = 0;
            RedirectDebugMsg(4u, L"Number of readers in the list = %d", v39);
          }
        }
        LeaveCriticalSection(v20);
        if ( !LastError )
          goto LABEL_28;
      }
      else
      {
        LastError = 14;
      }
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"CGPUserCollection::RWLock Failed to add reader in to reader list");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"CGPUserCollection::RWLock Failed to add reader in to reader list");
        }
      }
    }
    else
    {
      v9 = 0;
      LastError = 14;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"CGPUserCollection::RWLock Failed to create user collection context");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"CGPUserCollection::RWLock Failed to create user collection context");
        }
      }
    }
    goto LABEL_52;
  }
  LastError = 87;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"CGPUserCollection::RWLock Error occured while validating parameters");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"CGPUserCollection::RWLock Error occured while validating parameters");
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18000d2b0  mov     [rsp-38h+arg_10], rbx
0x18000d2b5  mov     [rsp-38h+arg_18], r9
0x18000d2ba  mov     [rsp-38h+arg_8], edx
0x18000d2be  push    rbp
0x18000d2bf  push    rsi
0x18000d2c0  push    rdi
0x18000d2c1  push    r12
0x18000d2c3  push    r13
0x18000d2c5  push    r14
0x18000d2c7  push    r15
0x18000d2c9  mov     rbp, rsp
0x18000d2cc  sub     rsp, 80h
0x18000d2d3  mov     rax, r9
0x18000d2d6  mov     r12d, r8d
0x18000d2d9  mov     r15, rcx
0x18000d2dc  xor     r14d, r14d
0x18000d2df  mov     [rbp+var_40], r14
0x18000d2e3  xorps   xmm0, xmm0
0x18000d2e6  movups  xmmword ptr [rbp+Handles], xmm0
0x18000d2ea  test    r8d, r8d
0x18000d2ed  jnz     loc_18000D4E8
0x18000d2f3  mov     [rbp+arg_8], 1
0x18000d2fa  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18000d301  jnz     loc_18000D6AB
0x18000d307  cmp     [r15+30h], r14
0x18000d30b  jz      loc_18000D4B4
0x18000d311  test    rax, rax
0x18000d314  jz      loc_18000D4B4
0x18000d31a  xor     r13d, r13d
0x18000d31d  mov     [rax], r13
0x18000d320  lea     rdi, [r15+38h]
0x18000d324  mov     [rbp+var_18], rdi
0x18000d328  mov     rax, [rdi+48h]
0x18000d32c  mov     [rbp+lpCriticalSection], rax
0x18000d330  test    r12d, r12d
0x18000d333  jnz     loc_18000D522
0x18000d339  mov     [rbp+var_20], rax
0x18000d33d  test    rax, rax
0x18000d340  jz      short loc_18000D34C
0x18000d342  mov     rcx, rax; lpCriticalSection
0x18000d345  call    cs:__imp_EnterCriticalSection
0x18000d34b  nop
0x18000d34c  mov     edx, 18h; uBytes
0x18000d351  mov     ecx, 40h ; '@'; uFlags
0x18000d356  call    cs:__imp_LocalAlloc
0x18000d35c  mov     rsi, rax
0x18000d35f  mov     [rbp+var_30], rax
0x18000d363  mov     rbx, rax
0x18000d366  mov     [rbp+var_48], rax
0x18000d36a  test    rax, rax
0x18000d36d  jz      loc_18000D724
0x18000d373  inc     dword ptr [rdi+4]
0x18000d376  mov     ecx, [rdi+4]
0x18000d379  mov     rax, [rdi+18h]
0x18000d37d  test    rax, rax
0x18000d380  jz      short loc_18000D38D
0x18000d382  cmp     qword ptr [rax+8], 0
0x18000d387  jnz     loc_18000D5B1
0x18000d38d  cmp     dword ptr [rdi+0Ch], 2
0x18000d391  jz      loc_18000D5B1
0x18000d397  mov     eax, [rdi]
0x18000d399  test    eax, eax
0x18000d39b  jnz     short loc_18000D3A4
0x18000d39d  mov     dword ptr [rdi+0Ch], 1
0x18000d3a4  inc     eax
0x18000d3a6  mov     [rdi], eax
0x18000d3a8  mov     [rsi], ecx
0x18000d3aa  mov     qword ptr [rsi+8], 0
0x18000d3b2  mov     dword ptr [rsi+10h], 0
0x18000d3b9  xor     ebx, ebx
0x18000d3bb  mov     r14, rsi
0x18000d3be  mov     [rbp+var_40], rsi
0x18000d3c2  xor     esi, esi
0x18000d3c4  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18000d3c8  test    rcx, rcx
0x18000d3cb  jz      short loc_18000D3D4
0x18000d3cd  call    cs:__imp_LeaveCriticalSection
0x18000d3d3  nop
0x18000d3d4  test    rbx, rbx
0x18000d3d7  jz      short loc_18000D3E2
0x18000d3d9  mov     rcx, rbx; hMem
0x18000d3dc  call    cs:__imp_LocalFree
0x18000d3e2  test    esi, esi
0x18000d3e4  jnz     loc_18000D5ED
0x18000d3ea  mov     rcx, [r14+8]
0x18000d3ee  test    rcx, rcx
0x18000d3f1  jnz     loc_18000D9EC
0x18000d3f7  mov     edx, 10h; uBytes
0x18000d3fc  mov     ecx, 40h ; '@'; uFlags
0x18000d401  call    cs:__imp_LocalAlloc
0x18000d407  mov     r13, rax
0x18000d40a  test    rax, rax
0x18000d40d  jz      loc_18000D619
0x18000d413  mov     [rax], r14
0x18000d416  mov     dword ptr [rax+8], 0
0x18000d41d  mov     [rax+0Ch], r12d
0x18000d421  xor     esi, esi
0x18000d423  cmp     [rbp+arg_8], esi
0x18000d426  jz      short loc_18000D483
0x18000d428  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x18000d42e  jnz     loc_18000DC50
0x18000d434  mov     [rbp+hSourceHandle], r13
0x18000d438  mov     rbx, [r15+28h]
0x18000d43c  test    rbx, rbx
0x18000d43f  jz      loc_18000DCA2
0x18000d445  mov     [rbp+var_20], rbx
0x18000d449  mov     rcx, rbx; lpCriticalSection
0x18000d44c  call    cs:__imp_EnterCriticalSection
0x18000d452  nop
0x18000d453  lea     rdx, [rbp+hSourceHandle]
0x18000d457  lea     rcx, [r15+88h]
0x18000d45e  call    ?push_front@?$STLWrap_List@PEAU_USER_COLLECTION_CONTEXT@@@@QEAAKAEBQEAU_USER_COLLECTION_CONTEXT@@@Z; STLWrap_List<_USER_COLLECTION_CONTEXT *>::push_front(_USER_COLLECTION_CONTEXT * const &)
0x18000d463  mov     esi, eax
0x18000d465  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18000d46c  jnz     loc_18000DCDA
0x18000d472  mov     rcx, rbx; lpCriticalSection
0x18000d475  call    cs:__imp_LeaveCriticalSection
0x18000d47b  test    esi, esi
0x18000d47d  jnz     loc_18000DCA7
0x18000d483  mov     rax, [rbp+arg_18]
0x18000d487  mov     [rax], r13
0x18000d48a  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18000d491  jnz     loc_18000DD9F
0x18000d497  mov     eax, esi
0x18000d499  mov     rbx, [rsp+80h+arg_10]
0x18000d4a1  add     rsp, 80h
0x18000d4a8  pop     r15
0x18000d4aa  pop     r14
0x18000d4ac  pop     r13
0x18000d4ae  pop     r12
0x18000d4b0  pop     rdi
0x18000d4b1  pop     rsi
0x18000d4b2  pop     rbp
0x18000d4b3  retn
0x18000d4b4  mov     esi, 57h ; 'W'
0x18000d4b9  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18000d4c0  jz      short loc_18000D497
0x18000d4c2  mov     r8, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000d4c9  test    r8, r8
0x18000d4cc  jz      loc_18000DDF9
0x18000d4d2  lea     rdx, aCgpusercollect_13; "CGPUserCollection::RWLock Error occured"...
0x18000d4d9  mov     ecx, 2
0x18000d4de  mov     rax, r8
0x18000d4e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4e6  jmp     short loc_18000D497
0x18000d4e8  mov     [rbp+arg_8], r14d
0x18000d4ec  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18000d4f3  jz      loc_18000D307
0x18000d4f9  mov     r8, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000d500  test    r8, r8
0x18000d503  jz      loc_18000D6F0
0x18000d509  lea     rdx, aCgpusercollect_6; "CGPUserCollection::RWLock Lock Called t"...
0x18000d510  mov     ecx, 4
0x18000d515  mov     rax, r8
0x18000d518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d51d  jmp     loc_18000D71B
0x18000d522  mov     [rbp+var_20], rax
0x18000d526  test    rax, rax
0x18000d529  jz      short loc_18000D535
0x18000d52b  mov     rcx, rax; lpCriticalSection
0x18000d52e  call    cs:__imp_EnterCriticalSection
0x18000d534  nop
0x18000d535  mov     edx, 18h; uBytes
0x18000d53a  mov     ecx, 40h ; '@'; uFlags
0x18000d53f  call    cs:__imp_LocalAlloc
0x18000d545  mov     rsi, rax
0x18000d548  mov     [rbp+var_38], rax
0x18000d54c  mov     rbx, rax
0x18000d54f  mov     [rbp+var_48], rax
0x18000d553  test    rax, rax
0x18000d556  jz      loc_18000D825
0x18000d55c  inc     dword ptr [rdi+8]
0x18000d55f  mov     eax, [rdi+8]
0x18000d562  cmp     dword ptr [rdi+0Ch], 0
0x18000d566  jnz     loc_18000D883
0x18000d56c  mov     dword ptr [rdi+0Ch], 2
0x18000d573  mov     [rbx], eax
0x18000d575  mov     qword ptr [rbx+8], 0
0x18000d57d  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18000d584  jnz     loc_18000D82F
0x18000d58a  mov     dword ptr [rsi+10h], 1
0x18000d591  xor     ebx, ebx
0x18000d593  mov     r14, rsi
0x18000d596  mov     [rbp+var_40], rsi
0x18000d59a  xor     esi, esi
0x18000d59c  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18000d5a0  test    rcx, rcx
0x18000d5a3  jz      short loc_18000D5AC
0x18000d5a5  call    cs:__imp_LeaveCriticalSection
0x18000d5ab  nop
0x18000d5ac  jmp     loc_18000D3D4
0x18000d5b1  mov     [rbp+hSourceHandle], 0
0x18000d5b9  mov     edx, 18h; uBytes
0x18000d5be  mov     ecx, 40h ; '@'; uFlags
0x18000d5c3  call    cs:__imp_LocalAlloc
0x18000d5c9  mov     [rbp+var_50], rax
0x18000d5cd  test    rax, rax
0x18000d5d0  jnz     loc_18000D72E
0x18000d5d6  mov     esi, 0Eh
0x18000d5db  lea     rdx, [rbp+var_48]; struct _RWLOCK_CONTEXT **
0x18000d5df  call    ?FreeLockContext@CRWLock@@AEAAXPEAPEAU_RWLOCK_CONTEXT@@@Z; CRWLock::FreeLockContext(_RWLOCK_CONTEXT * *)
0x18000d5e4  mov     rbx, [rbp+var_48]
0x18000d5e8  jmp     loc_18000D3C4
0x18000d5ed  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18000d5f4  jz      short loc_18000D62E
0x18000d5f6  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000d5fd  test    rax, rax
0x18000d600  jz      loc_18000D9C4
0x18000d606  lea     rdx, aCgpusercollect_11; "CGPUserCollection::RWLock Failed to acq"...
0x18000d60d  mov     ecx, 2
0x18000d612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d617  jmp     short loc_18000D62E
0x18000d619  xor     r13d, r13d
0x18000d61c  mov     esi, 0Eh
0x18000d621  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18000d628  jnz     loc_18000DC08
0x18000d62e  test    r14, r14
0x18000d631  jnz     loc_18000DD8D
0x18000d637  test    r13, r13
0x18000d63a  jz      loc_18000D497
0x18000d640  mov     rcx, r13; hMem
0x18000d643  call    cs:__imp_LocalFree
0x18000d649  jmp     loc_18000D497
0x18000d64e  call    cs:__imp_GetLastError
0x18000d654  mov     esi, eax
0x18000d656  lea     rcx, [rbp+hSourceHandle]; this
0x18000d65a  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x18000d65f  nop
0x18000d660  lea     rcx, [rbp+var_50]
0x18000d664  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18000d669  test    esi, esi
0x18000d66b  jz      loc_18000D59C
0x18000d671  lea     rdx, [rbp+var_48]; struct _RWLOCK_CONTEXT **
0x18000d675  call    ?FreeLockContext@CRWLock@@AEAAXPEAPEAU_RWLOCK_CONTEXT@@@Z; CRWLock::FreeLockContext(_RWLOCK_CONTEXT * *)
0x18000d67a  mov     rbx, [rbp+var_48]
0x18000d67e  jmp     loc_18000D59C
0x18000d683  call    cs:__imp_GetLastError
0x18000d689  mov     esi, eax
0x18000d68b  lea     rcx, [rbp+hSourceHandle]; this
0x18000d68f  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x18000d694  nop
0x18000d695  lea     rcx, [rbp+var_50]
0x18000d699  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18000d69e  test    esi, esi
0x18000d6a0  jz      loc_18000D3C4
0x18000d6a6  jmp     loc_18000D5DB
0x18000d6ab  mov     r8, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000d6b2  test    r8, r8
0x18000d6b5  jz      short loc_18000D6CD
0x18000d6b7  lea     rdx, aCgpusercollect_1; "CGPUserCollection::RWLock Lock Called t"...
0x18000d6be  mov     ecx, 4
0x18000d6c3  mov     rax, r8
0x18000d6c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6cb  jmp     short loc_18000D71B
0x18000d6cd  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18000d6d4  jz      loc_18000D307
0x18000d6da  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18000d6e1  jz      loc_18000D307
0x18000d6e7  lea     rdx, aCgpusercollect_1; "CGPUserCollection::RWLock Lock Called t"...
0x18000d6ee  jmp     short loc_18000D711
0x18000d6f0  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18000d6f7  jz      loc_18000D307
0x18000d6fd  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18000d704  jz      loc_18000D307
0x18000d70a  lea     rdx, aCgpusercollect_6; "CGPUserCollection::RWLock Lock Called t"...
0x18000d711  mov     ecx, 4; unsigned int
0x18000d716  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18000d71b  mov     rax, [rbp+arg_18]
0x18000d71f  jmp     loc_18000D307
0x18000d724  mov     esi, 0Eh
0x18000d729  jmp     loc_18000D5DB
0x18000d72e  xor     r9d, r9d; lpName
0x18000d731  xor     r8d, r8d; bInitialState
0x18000d734  xor     edx, edx; bManualReset
0x18000d736  xor     ecx, ecx; lpEventAttributes
0x18000d738  call    cs:__imp_CreateEventW
0x18000d73e  mov     rdx, rax
0x18000d741  lea     rcx, [rbp+hSourceHandle]
0x18000d745  call    ??4XHandle@@QEAAXPEAX@Z; XHandle::operator=(void *)
0x18000d74a  mov     rcx, [rbp+hSourceHandle]; hSourceHandle
0x18000d74e  test    rcx, rcx
0x18000d751  jz      loc_18000D683
0x18000d757  mov     eax, [rdi+4]
0x18000d75a  mov     rbx, [rbp+var_50]
0x18000d75e  mov     [rbx], eax
0x18000d760  mov     [rbx+8], rcx
0x18000d764  mov     [rsi], eax
0x18000d766  lea     rdx, [rsi+8]; lpTargetHandle
0x18000d76a  call    ?DuplicateEventHandle@@YAKPEAXPEAPEAX@Z; DuplicateEventHandle(void *,void * *)
0x18000d76f  mov     esi, eax
0x18000d771  test    eax, eax
0x18000d773  jnz     short loc_18000D7C7
0x18000d775  mov     [rbp+var_38], rbx
0x18000d779  lea     rcx, [rdi+10h]
0x18000d77d  lea     rdx, [rbp+var_38]
0x18000d781  call    ?push_back@?$STLWrap_List@PEAU_RWLOCK_CONTEXT@@@@QEAAKAEBQEAU_RWLOCK_CONTEXT@@@Z; STLWrap_List<_RWLOCK_CONTEXT *>::push_back(_RWLOCK_CONTEXT * const &)
0x18000d786  mov     esi, eax
0x18000d788  test    eax, eax
0x18000d78a  jnz     short loc_18000D7C7
0x18000d78c  mov     [rbp+hSourceHandle], 0
  ... truncated ...
```
