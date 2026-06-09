# CFGControl::CImplMediaSeeking::GetCurrentMediaTime(__int64 *)

- ea: `0x18000b2c0`
- end: `0x18000bc26`
- name: `?GetCurrentMediaTime@CImplMediaSeeking@CFGControl@@QEAAJPEA_J@Z`
- size: `2406`
- prototype: `__int64 __fastcall(CFGControl::CImplMediaSeeking *__hidden this, __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180077c20`
- `0x180078610`

## callees

- `0x18000b2c0`
- `0x18000c640`
- `0x1800135b0`
- `0x18001d3b0`
- `0x180077830`
- `0x180077f4c`
- `0x18015e010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18000b48e`
- `KERNEL32!GetCurrentThread` at `0x18000b4b1`
- `KERNEL32!GetCurrentThread` at `0x18000b517`
- `KERNEL32!GetCurrentThread` at `0x18000b80e`
- `KERNEL32!GetCurrentThread` at `0x18000b831`
- `KERNEL32!GetCurrentThread` at `0x18000b8a5`
- `KERNEL32!GetCurrentThread` at `0x18000b48e`
- `KERNEL32!GetCurrentThread` at `0x18000b4b1`
- `KERNEL32!GetCurrentThread` at `0x18000b517`
- `KERNEL32!GetCurrentThread` at `0x18000b80e`
- `KERNEL32!GetCurrentThread` at `0x18000b831`
- `KERNEL32!GetCurrentThread` at `0x18000b8a5`
- `KERNEL32!GetThreadPriority` at `0x18000b49d`
- `KERNEL32!GetThreadPriority` at `0x18000b81d`
- `KERNEL32!GetThreadPriority` at `0x18000b49d`
- `KERNEL32!GetThreadPriority` at `0x18000b81d`
- `KERNEL32!GetTickCount` at `0x18000b466`
- `KERNEL32!GetTickCount` at `0x18000b7ea`
- `KERNEL32!GetTickCount` at `0x18000b466`
- `KERNEL32!GetTickCount` at `0x18000b7ea`
- `KERNEL32!SetThreadPriority` at `0x18000b4c5`
- `KERNEL32!SetThreadPriority` at `0x18000b529`
- `KERNEL32!SetThreadPriority` at `0x18000b845`
- `KERNEL32!SetThreadPriority` at `0x18000b8b7`
- `KERNEL32!SetThreadPriority` at `0x18000b4c5`
- `KERNEL32!SetThreadPriority` at `0x18000b529`
- `KERNEL32!SetThreadPriority` at `0x18000b845`
- `KERNEL32!SetThreadPriority` at `0x18000b8b7`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000b358`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000b4e5`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000b6dc`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000b869`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000b358`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000b4e5`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000b6dc`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000b869`
- `KERNEL32!LeaveCriticalSection` at `0x18000b63c`
- `KERNEL32!LeaveCriticalSection` at `0x18000b63c`
- `KERNEL32!EnterCriticalSection` at `0x18000b627`
- `KERNEL32!EnterCriticalSection` at `0x18000b627`
- `KERNEL32!GetCurrentThreadId` at `0x18000b2f4`
- `KERNEL32!GetCurrentThreadId` at `0x18000b5b9`
- `KERNEL32!GetCurrentThreadId` at `0x18000b67a`
- `KERNEL32!GetCurrentThreadId` at `0x18000b947`
- `KERNEL32!GetCurrentThreadId` at `0x18000b2f4`
- `KERNEL32!GetCurrentThreadId` at `0x18000b5b9`
- `KERNEL32!GetCurrentThreadId` at `0x18000b67a`
- `KERNEL32!GetCurrentThreadId` at `0x18000b947`
- `KERNEL32!ReleaseMutex` at `0x18000ba12`
- `KERNEL32!ReleaseMutex` at `0x18000bab2`
- `KERNEL32!ReleaseMutex` at `0x18000bb86`
- `KERNEL32!ReleaseMutex` at `0x18000ba12`
- `KERNEL32!ReleaseMutex` at `0x18000bab2`
- `KERNEL32!ReleaseMutex` at `0x18000bb86`
- `USER32!GetQueueStatus` at `0x18000b53a`
- `USER32!GetQueueStatus` at `0x18000b8c8`
- `USER32!GetQueueStatus` at `0x18000b53a`
- `USER32!GetQueueStatus` at `0x18000b8c8`
- `USER32!DispatchMessageW` at `0x18000b411`
- `USER32!DispatchMessageW` at `0x18000b794`
- `USER32!DispatchMessageW` at `0x18000b411`
- `USER32!DispatchMessageW` at `0x18000b794`
- `USER32!PeekMessageW` at `0x18000b3fd`
- `USER32!PeekMessageW` at `0x18000b42f`
- `USER32!PeekMessageW` at `0x18000b451`
- `USER32!PeekMessageW` at `0x18000b5a2`
- `USER32!PeekMessageW` at `0x18000b780`
- `USER32!PeekMessageW` at `0x18000b7b2`
- `USER32!PeekMessageW` at `0x18000b7d6`
- `USER32!PeekMessageW` at `0x18000b92e`
- `USER32!PeekMessageW` at `0x18000b3fd`
- `USER32!PeekMessageW` at `0x18000b42f`
- `USER32!PeekMessageW` at `0x18000b451`
- `USER32!PeekMessageW` at `0x18000b5a2`
- `USER32!PeekMessageW` at `0x18000b780`
- `USER32!PeekMessageW` at `0x18000b7b2`
- `USER32!PeekMessageW` at `0x18000b7d6`
- `USER32!PeekMessageW` at `0x18000b92e`
- `USER32!MsgWaitForMultipleObjects` at `0x18000b3ad`
- `USER32!MsgWaitForMultipleObjects` at `0x18000b730`
- `USER32!MsgWaitForMultipleObjects` at `0x18000b3ad`
- `USER32!MsgWaitForMultipleObjects` at `0x18000b730`
- `USER32!RegisterWindowMessageW` at `0x18000b564`
- `USER32!RegisterWindowMessageW` at `0x18000b8f0`
- `USER32!RegisterWindowMessageW` at `0x18000b564`
- `USER32!RegisterWindowMessageW` at `0x18000b8f0`
- `USER32!PostThreadMessageW` at `0x18000b5d0`
- `USER32!PostThreadMessageW` at `0x18000b95e`
- `USER32!PostThreadMessageW` at `0x18000b5d0`
- `USER32!PostThreadMessageW` at `0x18000b95e`

## pseudocode

```c
__int64 __fastcall CFGControl::CImplMediaSeeking::GetCurrentMediaTime(struct __POSITION **this, __int64 *a2)
{
  __int64 *v2; // r13
  CFGControl::CImplMediaSeeking *v3; // r14
  void **v4; // rsi
  DWORD CurrentThreadId; // eax
  int v6; // r8d
  DWORD v7; // ebx
  int v8; // r12d
  HWND v9; // r15
  DWORD v10; // edi
  int v11; // r13d
  unsigned int v12; // r14d
  DWORD v13; // eax
  int v14; // ebx
  DWORD v15; // esi
  DWORD v16; // eax
  DWORD TickCount; // eax
  unsigned int v18; // edx
  unsigned int v19; // ecx
  bool v20; // cc
  HANDLE CurrentThread; // rax
  HANDLE v22; // rax
  bool v23; // zf
  HANDLE v24; // rax
  UINT v25; // r15d
  BOOL v26; // eax
  DWORD v27; // eax
  int v28; // ecx
  __int64 v29; // rbx
  int v30; // r15d
  __int64 v31; // rcx
  struct _RTL_CRITICAL_SECTION *v32; // rdi
  int v33; // ebx
  _QWORD *v34; // rdi
  __int64 v35; // rbx
  DWORD v36; // eax
  int v37; // ecx
  DWORD v38; // r15d
  struct __POSITION *v39; // rax
  DWORD v40; // eax
  HWND v41; // r15
  DWORD v42; // eax
  int v43; // r14d
  unsigned int v44; // edi
  int v45; // ebx
  DWORD v46; // esi
  DWORD v47; // eax
  DWORD v48; // eax
  DWORD v49; // edx
  unsigned int v50; // eax
  unsigned int v51; // ecx
  HANDLE v52; // rax
  HANDLE v53; // rax
  HANDLE v54; // rax
  UINT v55; // eax
  DWORD v56; // eax
  __int64 v57; // rax
  __int64 v58; // rcx
  int v59; // edx
  __int64 v60; // rcx
  __int64 v61; // rax
  struct __POSITION *v62; // rcx
  __int64 v63; // rcx
  void *v64; // rcx
  __int64 v66; // rcx
  int ListSeeking; // ebx
  struct __POSITION *v68; // rcx
  void *NextI; // rax
  int v70; // eax
  struct __POSITION *v71; // rcx
  __int64 v72; // rdx
  __int64 v73; // [rsp+30h] [rbp-79h] BYREF
  int v74; // [rsp+38h] [rbp-71h]
  UINT wMsgFilterMin; // [rsp+3Ch] [rbp-6Dh]
  DWORD v76; // [rsp+40h] [rbp-69h]
  int v77; // [rsp+44h] [rbp-65h]
  HWND hWnd; // [rsp+48h] [rbp-61h]
  __int64 v79; // [rsp+50h] [rbp-59h] BYREF
  void **v80; // [rsp+58h] [rbp-51h]
  struct tagMSG Msg; // [rsp+60h] [rbp-49h] BYREF
  HANDLE Handles[2]; // [rsp+90h] [rbp-19h] BYREF
  HANDLE pHandles[2]; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v84; // [rsp+B0h] [rbp+7h]
  _QWORD *v85; // [rsp+B8h] [rbp+Fh]
  struct __POSITION **v86; // [rsp+110h] [rbp+67h] BYREF
  __int64 *v87; // [rsp+118h] [rbp+6Fh]
  int nPriority; // [rsp+120h] [rbp+77h]
  int ThreadPriority; // [rsp+128h] [rbp+7Fh]

  v87 = a2;
  v86 = this;
  v2 = a2;
  v3 = (CFGControl::CImplMediaSeeking *)this;
  v80 = (void **)*((_QWORD *)this[4] + 2);
  v4 = v80;
  CurrentThreadId = GetCurrentThreadId();
  v6 = *((_DWORD *)v80 + 2);
  v77 = CurrentThreadId;
  v7 = CurrentThreadId;
  v8 = 1;
  if ( CurrentThreadId == v6 )
    goto LABEL_34;
  wMsgFilterMin = *((_DWORD *)v80 + 6);
  if ( CurrentThreadId == *((_DWORD *)v80 + 7) )
    v9 = (HWND)v80[2];
  else
    v9 = 0;
  Handles[0] = *v80;
  v74 = -1;
  ThreadPriority = 0;
  nPriority = 0;
  Handles[1] = 0;
  v10 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
  if ( v10 )
  {
    v11 = ThreadPriority;
    v12 = v74;
    v13 = 64;
    v14 = ThreadPriority;
    if ( v9 )
      v13 = 72;
    v76 = v13;
    do
    {
      v15 = v12;
      if ( v12 > 0xA )
        v15 = 10;
      v16 = MsgWaitForMultipleObjects(1u, Handles, 0, v15, v13);
      v10 = v16;
      if ( v16 != 1 && (v16 != 258 || v15 == v12) )
        break;
      memset(&Msg, 0, sizeof(Msg));
      if ( v9 && PeekMessageW(&Msg, v9, wMsgFilterMin, wMsgFilterMin, 1u) )
      {
        do
          DispatchMessageW(&Msg);
        while ( PeekMessageW(&Msg, v9, wMsgFilterMin, wMsgFilterMin, 1u) );
      }
      PeekMessageW(&Msg, 0, 0, 0, 0);
      if ( v12 - 1 <= 0xFFFFFFFD )
      {
        TickCount = GetTickCount();
        v18 = TickCount - v14;
        v14 = TickCount;
        v19 = v12 - v18;
        v20 = v18 <= v12;
        v12 = 0;
        if ( v20 )
          v12 = v19;
      }
      if ( !v11 )
      {
        CurrentThread = GetCurrentThread();
        nPriority = GetThreadPriority(CurrentThread);
        if ( (unsigned int)nPriority < 2 )
        {
          v22 = GetCurrentThread();
          SetThreadPriority(v22, 2);
        }
        v11 = 1;
      }
      v10 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
      v13 = v76;
    }
    while ( v10 );
    v4 = v80;
    v23 = v11 == 0;
    v2 = v87;
    v3 = (CFGControl::CImplMediaSeeking *)v86;
    v7 = v77;
    if ( !v23 )
    {
      v24 = GetCurrentThread();
      SetThreadPriority(v24, nPriority);
      if ( (GetQueueStatus(8u) & 0x80000) != 0 )
      {
        v25 = wMsgFilterMax;
        if ( wMsgFilterMax || (wMsgFilterMax = RegisterWindowMessageW(L"AMUnblock"), (v25 = wMsgFilterMax) != 0) )
        {
          memset(&Msg, 0, sizeof(Msg));
          do
          {
            v26 = PeekMessageW(&Msg, HWND_MESSAGE|0x2LL, v25, v25, 1u);
            v25 = wMsgFilterMax;
          }
          while ( v26 );
        }
        v27 = GetCurrentThreadId();
        PostThreadMessageW(v27, v25, 0, 0);
      }
    }
  }
  if ( !v10 )
  {
    *((_DWORD *)v4 + 2) = v7;
LABEL_34:
    ++*((_DWORD *)v4 + 3);
    v28 = 1;
    goto LABEL_35;
  }
  v28 = 0;
LABEL_35:
  v29 = *((_QWORD *)v3 + 4);
  v73 = 0;
  v30 = 0;
  if ( !v28 )
    v4 = 0;
  v80 = v4;
  v23 = *(_QWORD *)(v29 + 192) == 0;
  Handles[0] = v4;
  if ( v23 )
  {
    v31 = *((_QWORD *)v3 + 9);
    goto LABEL_105;
  }
  v32 = (struct _RTL_CRITICAL_SECTION *)(v29 + 888);
  EnterCriticalSection((LPCRITICAL_SECTION)(v29 + 888));
  v33 = *(_DWORD *)(v29 + 132);
  LeaveCriticalSection(v32);
  if ( !v33 )
  {
    v31 = 0;
    if ( *((_QWORD *)v3 + 10) != 0x7FFFFFFFFFFFFFFFLL )
      v31 = *((_QWORD *)v3 + 10);
    goto LABEL_105;
  }
  v34 = (_QWORD *)*((_QWORD *)v3 + 4);
  v85 = v34;
  v84 = v34[2];
  v35 = v84;
  v36 = GetCurrentThreadId();
  v37 = *(_DWORD *)(v35 + 8);
  v38 = v36;
  v74 = v36;
  if ( v36 == v37 )
    goto LABEL_79;
  wMsgFilterMin = *(_DWORD *)(v35 + 24);
  if ( v36 == *(_DWORD *)(v35 + 28) )
    hWnd = *(HWND *)(v35 + 16);
  else
    hWnd = 0;
  v39 = *(struct __POSITION **)v35;
  nPriority = 0;
  ThreadPriority = 0;
  pHandles[1] = 0;
  pHandles[0] = v39;
  v77 = -1;
  v40 = WaitForMultipleObjectsEx(1u, pHandles, 0, 0, 0);
  if ( v40 )
  {
    v41 = hWnd;
    v42 = 64;
    v43 = nPriority;
    v44 = v77;
    if ( hWnd )
      v42 = 72;
    v45 = nPriority;
    LODWORD(hWnd) = v42;
    do
    {
      v46 = v44;
      if ( v44 > 0xA )
        v46 = 10;
      v47 = MsgWaitForMultipleObjects(1u, pHandles, 0, v46, v42);
      nPriority = v47;
      if ( v47 != 1 && (v47 != 258 || v46 == v44) )
        break;
      memset(&Msg, 0, sizeof(Msg));
      if ( v41 && PeekMessageW(&Msg, v41, wMsgFilterMin, wMsgFilterMin, 1u) )
      {
        do
          DispatchMessageW(&Msg);
        while ( PeekMessageW(&Msg, v41, wMsgFilterMin, wMsgFilterMin, 1u) );
      }
      PeekMessageW(&Msg, 0, 0, 0, 0);
      if ( v44 - 1 <= 0xFFFFFFFD )
      {
        v48 = GetTickCount();
        v49 = v48 - v45;
        v45 = v48;
        v50 = v44;
        v51 = v44 - v49;
        v44 = 0;
        if ( v49 <= v50 )
          v44 = v51;
      }
      if ( !v43 )
      {
        v52 = GetCurrentThread();
        ThreadPriority = GetThreadPriority(v52);
        if ( (unsigned int)ThreadPriority < 2 )
        {
          v53 = GetCurrentThread();
          SetThreadPriority(v53, 2);
        }
        v43 = 1;
      }
      nPriority = WaitForMultipleObjectsEx(1u, pHandles, 0, 0, 0);
      v42 = (unsigned int)hWnd;
    }
    while ( nPriority );
    v4 = v80;
    v23 = v43 == 0;
    v3 = (CFGControl::CImplMediaSeeking *)v86;
    v35 = v84;
    v34 = v85;
    v38 = v74;
    v2 = v87;
    if ( !v23 )
    {
      v54 = GetCurrentThread();
      SetThreadPriority(v54, ThreadPriority);
      if ( (GetQueueStatus(8u) & 0x80000) != 0 )
      {
        v55 = wMsgFilterMax;
        if ( wMsgFilterMax
          || (v55 = RegisterWindowMessageW(L"AMUnblock"), LODWORD(v86) = v55, (wMsgFilterMax = v55) != 0) )
        {
          memset(&Msg, 0, sizeof(Msg));
          do
          {
            v23 = !PeekMessageW(&Msg, HWND_MESSAGE|0x2LL, v55, v55, 1u);
            v55 = wMsgFilterMax;
          }
          while ( !v23 );
          LODWORD(v86) = wMsgFilterMax;
        }
        v56 = GetCurrentThreadId();
        PostThreadMessageW(v56, (UINT)v86, 0, 0);
      }
    }
    v40 = nPriority;
  }
  if ( !v40 )
  {
    *(_DWORD *)(v35 + 8) = v38;
LABEL_79:
    ++*(_DWORD *)(v35 + 12);
    goto LABEL_80;
  }
  v8 = 0;
LABEL_80:
  v57 = *v34;
  v58 = 0;
  if ( !v8 )
    v35 = 0;
  v79 = 0;
  v86 = (struct __POSITION **)v35;
  v59 = *(_DWORD *)(v57 + 168);
  if ( v59 )
  {
    v60 = v34[26];
    if ( !v60 )
    {
      CAutoMsgMutex::~CAutoMsgMutex((CAutoMsgMutex *)&v86);
LABEL_94:
      v63 = *((_QWORD *)v3 + 7);
      if ( v63 )
      {
        v30 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v63 + 96LL))(v63, &v73);
        if ( v30 >= 0 )
          v30 = CFGControl::CImplMediaSeeking::ConvertTimeFormat(v3, &v73, &TIME_FORMAT_MEDIA_TIME, v73, 0);
      }
      else
      {
        v66 = *((_QWORD *)v3 + 4);
        v86 = 0;
        ListSeeking = CFGControl::GetListSeeking(v66, &v86);
        if ( ListSeeking < 0 )
        {
          CAutoMsgMutex::~CAutoMsgMutex((CAutoMsgMutex *)Handles);
          return (unsigned int)ListSeeking;
        }
        v68 = *v86;
        v86 = (struct __POSITION **)v68;
        if ( v68 )
        {
          while ( 1 )
          {
            NextI = CBaseList::GetNextI(v68, (struct __POSITION **)&v86);
            v70 = (*(__int64 (__fastcall **)(void *, __int64 *))(*(_QWORD *)NextI + 96LL))(NextI, &v73);
            v30 = v70;
            if ( !v70 )
              break;
            if ( !v86 )
            {
              if ( v70 < 0 )
                break;
              goto LABEL_116;
            }
          }
        }
        else
        {
LABEL_116:
          v30 = -2147467262;
        }
      }
      v31 = v73;
      goto LABEL_98;
    }
    if ( v59 == 1 )
    {
      v61 = v34[24];
      if ( v61 )
        v58 = v34[25] - v61;
      else
        v58 = 0;
    }
    else
    {
      if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v60 + 24LL))(v60, &v79) < 0 )
      {
        if ( v35 )
        {
          v23 = (*(_DWORD *)(v35 + 12))-- == 1;
          if ( v23 )
          {
            v62 = *(struct __POSITION **)v35;
            *(_DWORD *)(v35 + 8) = 0;
            ReleaseMutex(v62);
          }
        }
        goto LABEL_94;
      }
      v58 = v79 - v34[24];
    }
    v79 = v58;
    if ( v58 < 0 )
    {
      v58 = 0;
      v79 = 0;
    }
  }
  v73 = v58;
  if ( v35 )
  {
    v23 = (*(_DWORD *)(v35 + 12))-- == 1;
    if ( v23 )
    {
      v71 = *(struct __POSITION **)v35;
      *(_DWORD *)(v35 + 8) = 0;
      ReleaseMutex(v71);
    }
    v58 = v73;
  }
  v30 = 0;
  if ( *((_QWORD *)v3 + 16) )
  {
    CFGControl::CImplMediaSeeking::KillDeadSegments(v3, v58);
    v72 = *((_QWORD *)v3 + 16);
    v31 = *(_QWORD *)(v72 + 16) + (unsigned int)(int)((double)((int)v73 - *(_DWORD *)v72) * *(double *)(v72 + 32) + 0.5);
    v73 = v31;
    if ( v31 > *(_QWORD *)(v72 + 24) )
    {
      v31 = *(_QWORD *)(v72 + 24);
      v73 = v31;
    }
  }
  else
  {
    v31 = (unsigned int)(int)((double)(int)v58 * *((double *)v3 + 8) + 0.5);
    v73 = v31;
  }
LABEL_98:
  if ( !*((_BYTE *)v3 + 104) )
  {
    if ( v30 >= 0 )
    {
      v31 += *((_QWORD *)v3 + 9);
      v73 = v31;
    }
    if ( v31 > *((_QWORD *)v3 + 10) )
    {
      v31 = *((_QWORD *)v3 + 10);
      v73 = v31;
    }
  }
  if ( v31 >= 0 )
    goto LABEL_106;
  v31 = 0;
LABEL_105:
  v73 = v31;
LABEL_106:
  *v2 = v31;
  if ( v4 )
  {
    v23 = (*((_DWORD *)v4 + 3))-- == 1;
    if ( v23 )
    {
      v64 = *v4;
      *((_DWORD *)v4 + 2) = 0;
      ReleaseMutex(v64);
    }
  }
  return (unsigned int)v30;
}

```

## disassembly

```asm
0x18000b2c0  mov     [rsp-8+arg_8], rdx
0x18000b2c5  mov     [rsp-8+arg_0], rcx
0x18000b2ca  push    rbp
0x18000b2cb  push    rbx
0x18000b2cc  push    rsi
0x18000b2cd  push    rdi
0x18000b2ce  push    r12
0x18000b2d0  push    r13
0x18000b2d2  push    r14
0x18000b2d4  push    r15
0x18000b2d6  lea     rbp, [rsp-1Fh]
0x18000b2db  sub     rsp, 0C8h
0x18000b2e2  mov     rax, [rcx+20h]
0x18000b2e6  mov     r13, rdx
0x18000b2e9  mov     r14, rcx
0x18000b2ec  mov     rsi, [rax+10h]
0x18000b2f0  mov     [rbp+57h+var_A8], rsi
0x18000b2f4  call    cs:__imp_GetCurrentThreadId
0x18000b2fb  nop     dword ptr [rax+rax+00h]
0x18000b300  mov     r8d, [rsi+8]
0x18000b304  xor     r9d, r9d; dwMilliseconds
0x18000b307  mov     [rbp+57h+var_BC], eax
0x18000b30a  mov     ebx, eax
0x18000b30c  mov     r12d, 1
0x18000b312  cmp     eax, r8d
0x18000b315  jz      loc_18000B5E6
0x18000b31b  mov     eax, [rsi+18h]
0x18000b31e  mov     [rbp+57h+wMsgFilterMin], eax
0x18000b321  cmp     ebx, [rsi+1Ch]
0x18000b324  jnz     short loc_18000B32C
0x18000b326  mov     r15, [rsi+10h]
0x18000b32a  jmp     short loc_18000B32F
0x18000b32c  mov     r15, r9
0x18000b32f  mov     rax, [rsi]
0x18000b332  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18000b336  xor     r8d, r8d; bWaitAll
0x18000b339  mov     [rbp+57h+Handles], rax
0x18000b33d  mov     ecx, r12d; nCount
0x18000b340  mov     [rbp+57h+var_C8], 0FFFFFFFFh
0x18000b347  mov     [rbp+57h+arg_18], r9d
0x18000b34b  mov     [rbp+57h+nPriority], r9d
0x18000b34f  mov     [rbp+57h+var_68], r9
0x18000b353  mov     [rsp+100h+bAlertable], r9d; bAlertable
0x18000b358  call    cs:__imp_WaitForMultipleObjectsEx
0x18000b35f  nop     dword ptr [rax+rax+00h]
0x18000b364  mov     edi, eax
0x18000b366  cmp     eax, r12d
0x18000b369  jb      loc_18000B5DC
0x18000b36f  mov     r13d, [rbp+57h+arg_18]
0x18000b373  test    r15, r15
0x18000b376  mov     r14d, [rbp+57h+var_C8]
0x18000b37a  mov     eax, 40h ; '@'
0x18000b37f  mov     ecx, 48h ; 'H'
0x18000b384  mov     ebx, r13d
0x18000b387  cmovnz  eax, ecx
0x18000b38a  mov     [rbp+57h+var_C0], eax
0x18000b38d  mov     ecx, 0Ah
0x18000b392  mov     [rsp+100h+bAlertable], eax; dwWakeMask
0x18000b396  cmp     r14d, 0Ah
0x18000b39a  lea     rdx, [rbp+57h+Handles]; pHandles
0x18000b39e  mov     esi, r14d
0x18000b3a1  cmova   esi, ecx
0x18000b3a4  xor     r8d, r8d; fWaitAll
0x18000b3a7  mov     r9d, esi; dwMilliseconds
0x18000b3aa  mov     ecx, r12d; nCount
0x18000b3ad  call    cs:__imp_MsgWaitForMultipleObjects
0x18000b3b4  nop     dword ptr [rax+rax+00h]
0x18000b3b9  mov     edi, eax
0x18000b3bb  cmp     eax, r12d
0x18000b3be  jz      short loc_18000B3D4
0x18000b3c0  cmp     eax, 102h
0x18000b3c5  jnz     loc_18000B4FF
0x18000b3cb  cmp     esi, r14d
0x18000b3ce  jz      loc_18000B4FF
0x18000b3d4  xorps   xmm0, xmm0
0x18000b3d7  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x18000b3db  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x18000b3df  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x18000b3e3  test    r15, r15
0x18000b3e6  jz      short loc_18000B43F
0x18000b3e8  mov     edi, [rbp+57h+wMsgFilterMin]
0x18000b3eb  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18000b3ef  mov     r9d, edi; wMsgFilterMax
0x18000b3f2  mov     [rsp+100h+bAlertable], r12d; wRemoveMsg
0x18000b3f7  mov     r8d, edi; wMsgFilterMin
0x18000b3fa  mov     rdx, r15; hWnd
0x18000b3fd  call    cs:__imp_PeekMessageW
0x18000b404  nop     dword ptr [rax+rax+00h]
0x18000b409  test    eax, eax
0x18000b40b  jz      short loc_18000B43F
0x18000b40d  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18000b411  call    cs:__imp_DispatchMessageW
0x18000b418  nop     dword ptr [rax+rax+00h]
0x18000b41d  mov     r9d, edi; wMsgFilterMax
0x18000b420  mov     [rsp+100h+bAlertable], r12d; wRemoveMsg
0x18000b425  mov     r8d, edi; wMsgFilterMin
0x18000b428  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18000b42c  mov     rdx, r15; hWnd
0x18000b42f  call    cs:__imp_PeekMessageW
0x18000b436  nop     dword ptr [rax+rax+00h]
0x18000b43b  test    eax, eax
0x18000b43d  jnz     short loc_18000B40D
0x18000b43f  xor     edi, edi
0x18000b441  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18000b445  xor     r9d, r9d; wMsgFilterMax
0x18000b448  mov     [rsp+100h+bAlertable], edi; wRemoveMsg
0x18000b44c  xor     r8d, r8d; wMsgFilterMin
0x18000b44f  xor     edx, edx; hWnd
0x18000b451  call    cs:__imp_PeekMessageW
0x18000b458  nop     dword ptr [rax+rax+00h]
0x18000b45d  lea     eax, [r14-1]
0x18000b461  cmp     eax, 0FFFFFFFDh
0x18000b464  ja      short loc_18000B489
0x18000b466  call    cs:__imp_GetTickCount
0x18000b46d  nop     dword ptr [rax+rax+00h]
0x18000b472  mov     ecx, r14d
0x18000b475  mov     edx, eax
0x18000b477  sub     edx, ebx
0x18000b479  mov     ebx, eax
0x18000b47b  mov     eax, r14d
0x18000b47e  sub     ecx, edx
0x18000b480  cmp     edx, eax
0x18000b482  mov     r14d, edi
0x18000b485  cmovbe  r14d, ecx
0x18000b489  test    r13d, r13d
0x18000b48c  jnz     short loc_18000B4D4
0x18000b48e  call    cs:__imp_GetCurrentThread
0x18000b495  nop     dword ptr [rax+rax+00h]
0x18000b49a  mov     rcx, rax; hThread
0x18000b49d  call    cs:__imp_GetThreadPriority
0x18000b4a4  nop     dword ptr [rax+rax+00h]
0x18000b4a9  mov     [rbp+57h+nPriority], eax
0x18000b4ac  cmp     eax, 2
0x18000b4af  jnb     short loc_18000B4D1
0x18000b4b1  call    cs:__imp_GetCurrentThread
0x18000b4b8  nop     dword ptr [rax+rax+00h]
0x18000b4bd  mov     rcx, rax; hThread
0x18000b4c0  mov     edx, 2; nPriority
0x18000b4c5  call    cs:__imp_SetThreadPriority
0x18000b4cc  nop     dword ptr [rax+rax+00h]
0x18000b4d1  mov     r13d, r12d
0x18000b4d4  xor     r9d, r9d; dwMilliseconds
0x18000b4d7  mov     [rsp+100h+bAlertable], edi; bAlertable
0x18000b4db  xor     r8d, r8d; bWaitAll
0x18000b4de  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18000b4e2  mov     ecx, r12d; nCount
0x18000b4e5  call    cs:__imp_WaitForMultipleObjectsEx
0x18000b4ec  nop     dword ptr [rax+rax+00h]
0x18000b4f1  mov     edi, eax
0x18000b4f3  cmp     eax, r12d
0x18000b4f6  mov     eax, [rbp+57h+var_C0]
0x18000b4f9  jnb     loc_18000B38D
0x18000b4ff  mov     rsi, [rbp+57h+var_A8]
0x18000b503  test    r13d, r13d
0x18000b506  mov     r13, [rbp+57h+arg_8]
0x18000b50a  mov     r14, [rbp+57h+arg_0]
0x18000b50e  mov     ebx, [rbp+57h+var_BC]
0x18000b511  jz      loc_18000B5DC
0x18000b517  call    cs:__imp_GetCurrentThread
0x18000b51e  nop     dword ptr [rax+rax+00h]
0x18000b523  mov     edx, [rbp+57h+nPriority]; nPriority
0x18000b526  mov     rcx, rax; hThread
0x18000b529  call    cs:__imp_SetThreadPriority
0x18000b530  nop     dword ptr [rax+rax+00h]
0x18000b535  mov     ecx, 8; flags
0x18000b53a  call    cs:__imp_GetQueueStatus
0x18000b541  nop     dword ptr [rax+rax+00h]
0x18000b546  shr     eax, 10h
0x18000b549  test    al, 8
0x18000b54b  jz      loc_18000B5DC
0x18000b551  mov     r15d, cs:wMsgFilterMax
0x18000b558  test    r15d, r15d
0x18000b55b  jnz     short loc_18000B57D
0x18000b55d  lea     rcx, String; "AMUnblock"
0x18000b564  call    cs:__imp_RegisterWindowMessageW
0x18000b56b  nop     dword ptr [rax+rax+00h]
0x18000b570  mov     cs:wMsgFilterMax, eax
0x18000b576  mov     r15d, eax
0x18000b579  test    eax, eax
0x18000b57b  jz      short loc_18000B5B9
0x18000b57d  xorps   xmm0, xmm0
0x18000b580  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x18000b584  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x18000b588  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x18000b58c  mov     r9d, r15d; wMsgFilterMax
0x18000b58f  mov     [rsp+100h+bAlertable], r12d; wRemoveMsg
0x18000b594  mov     r8d, r15d; wMsgFilterMin
0x18000b597  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18000b59b  mov     rdx, 0FFFFFFFFFFFFFFFFh; hWnd
0x18000b5a2  call    cs:__imp_PeekMessageW
0x18000b5a9  nop     dword ptr [rax+rax+00h]
0x18000b5ae  mov     r15d, cs:wMsgFilterMax
0x18000b5b5  test    eax, eax
0x18000b5b7  jnz     short loc_18000B58C
0x18000b5b9  call    cs:__imp_GetCurrentThreadId
0x18000b5c0  nop     dword ptr [rax+rax+00h]
0x18000b5c5  xor     r9d, r9d; lParam
0x18000b5c8  xor     r8d, r8d; wParam
0x18000b5cb  mov     ecx, eax; idThread
0x18000b5cd  mov     edx, r15d; Msg
0x18000b5d0  call    cs:__imp_PostThreadMessageW
0x18000b5d7  nop     dword ptr [rax+rax+00h]
0x18000b5dc  xor     r9d, r9d
0x18000b5df  test    edi, edi
0x18000b5e1  jnz     short loc_18000B618
0x18000b5e3  mov     [rsi+8], ebx
0x18000b5e6  inc     dword ptr [rsi+0Ch]
0x18000b5e9  mov     ecx, r12d
0x18000b5ec  mov     rbx, [r14+20h]
0x18000b5f0  test    ecx, ecx
0x18000b5f2  mov     [rbp+57h+var_D0], r9
0x18000b5f6  mov     r15d, r9d
0x18000b5f9  cmovz   rsi, r9
0x18000b5fd  mov     [rbp+57h+var_A8], rsi
0x18000b601  cmp     qword ptr [rbx+0C0h], 0
0x18000b609  mov     [rbp+57h+Handles], rsi
0x18000b60d  jnz     short loc_18000B61D
0x18000b60f  mov     rcx, [r14+48h]
0x18000b613  jmp     loc_18000BA98
0x18000b618  mov     ecx, r9d
0x18000b61b  jmp     short loc_18000B5EC
0x18000b61d  lea     rdi, [rbx+378h]
0x18000b624  mov     rcx, rdi; lpCriticalSection
0x18000b627  call    cs:__imp_EnterCriticalSection
0x18000b62e  nop     dword ptr [rax+rax+00h]
0x18000b633  mov     ebx, [rbx+84h]
0x18000b639  mov     rcx, rdi; lpCriticalSection
0x18000b63c  call    cs:__imp_LeaveCriticalSection
0x18000b643  nop     dword ptr [rax+rax+00h]
0x18000b648  test    ebx, ebx
0x18000b64a  jnz     short loc_18000B66A
0x18000b64c  xor     r9d, r9d
0x18000b64f  mov     rdx, 7FFFFFFFFFFFFFFFh
0x18000b659  cmp     [r14+50h], rdx
0x18000b65d  mov     ecx, r9d
0x18000b660  cmovnz  rcx, [r14+50h]
0x18000b665  jmp     loc_18000BA98
0x18000b66a  mov     rdi, [r14+20h]
0x18000b66e  mov     [rbp+57h+var_48], rdi
0x18000b672  mov     rbx, [rdi+10h]
0x18000b676  mov     [rbp+57h+var_50], rbx
0x18000b67a  call    cs:__imp_GetCurrentThreadId
0x18000b681  nop     dword ptr [rax+rax+00h]
0x18000b686  mov     ecx, [rbx+8]
0x18000b689  mov     r15d, eax
0x18000b68c  mov     [rbp+57h+var_C8], eax
0x18000b68f  cmp     eax, ecx
0x18000b691  jz      loc_18000B975
0x18000b697  mov     eax, [rbx+18h]
0x18000b69a  xor     ecx, ecx
0x18000b69c  mov     [rbp+57h+wMsgFilterMin], eax
0x18000b69f  cmp     r15d, [rbx+1Ch]
0x18000b6a3  jnz     short loc_18000B6AF
0x18000b6a5  mov     rax, [rbx+10h]
0x18000b6a9  mov     [rbp+57h+hWnd], rax
0x18000b6ad  jmp     short loc_18000B6B3
0x18000b6af  mov     [rbp+57h+hWnd], rcx
0x18000b6b3  mov     rax, [rbx]
0x18000b6b6  lea     rdx, [rbp+57h+pHandles]; lpHandles
0x18000b6ba  mov     [rbp+57h+nPriority], ecx
0x18000b6bd  xor     r9d, r9d; dwMilliseconds
0x18000b6c0  mov     [rbp+57h+arg_18], ecx
0x18000b6c3  xor     r8d, r8d; bWaitAll
0x18000b6c6  mov     [rbp+57h+var_58], rcx
0x18000b6ca  mov     [rsp+100h+bAlertable], ecx; bAlertable
0x18000b6ce  mov     ecx, r12d; nCount
0x18000b6d1  mov     [rbp+57h+pHandles], rax
0x18000b6d5  mov     [rbp+57h+var_BC], 0FFFFFFFFh
0x18000b6dc  call    cs:__imp_WaitForMultipleObjectsEx
0x18000b6e3  nop     dword ptr [rax+rax+00h]
0x18000b6e8  cmp     eax, r12d
0x18000b6eb  jb      loc_18000B96D
0x18000b6f1  mov     r15, [rbp+57h+hWnd]
0x18000b6f5  mov     eax, 40h ; '@'
0x18000b6fa  mov     r14d, [rbp+57h+nPriority]
0x18000b6fe  test    r15, r15
0x18000b701  mov     edi, [rbp+57h+var_BC]
0x18000b704  mov     ecx, 48h ; 'H'
0x18000b709  cmovnz  eax, ecx
0x18000b70c  mov     ebx, r14d
0x18000b70f  mov     dword ptr [rbp+57h+hWnd], eax
0x18000b712  mov     ecx, 0Ah
0x18000b717  mov     [rsp+100h+bAlertable], eax; dwWakeMask
0x18000b71b  cmp     edi, 0Ah
0x18000b71e  lea     rdx, [rbp+57h+pHandles]; pHandles
0x18000b722  mov     esi, edi
0x18000b724  cmova   esi, ecx
0x18000b727  xor     r8d, r8d; fWaitAll
0x18000b72a  mov     r9d, esi; dwMilliseconds
0x18000b72d  mov     ecx, r12d; nCount
0x18000b730  call    cs:__imp_MsgWaitForMultipleObjects
0x18000b737  nop     dword ptr [rax+rax+00h]
0x18000b73c  mov     [rbp+57h+nPriority], eax
0x18000b73f  cmp     eax, r12d
0x18000b742  jz      short loc_18000B757
0x18000b744  cmp     eax, 102h
0x18000b749  jnz     loc_18000B884
0x18000b74f  cmp     esi, edi
0x18000b751  jz      loc_18000B884
0x18000b757  xorps   xmm0, xmm0
  ... truncated ...
```
