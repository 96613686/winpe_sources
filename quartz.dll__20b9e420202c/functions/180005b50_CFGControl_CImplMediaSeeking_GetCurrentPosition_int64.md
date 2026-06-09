# CFGControl::CImplMediaSeeking::GetCurrentPosition(__int64 *)

- ea: `0x180005b50`
- end: `0x180006639`
- name: `?GetCurrentPosition@CImplMediaSeeking@CFGControl@@UEAAJPEA_J@Z`
- size: `2793`
- prototype: `__int64 __fastcall(CFGControl::CImplMediaSeeking *__hidden this, __int64 *)`
- caller_count: `3`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180005390`
- `0x1800229e8`
- `0x18006f65c`

## callees

- `0x180005358`
- `0x180005b50`
- `0x18000c640`
- `0x1800135b0`
- `0x18001d3b0`
- `0x180077830`
- `0x180077f4c`
- `0x18015e010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x1800060c2`
- `KERNEL32!GetCurrentThread` at `0x1800062c2`
- `KERNEL32!GetCurrentThread` at `0x1800062e5`
- `KERNEL32!GetCurrentThread` at `0x1800063aa`
- `KERNEL32!GetCurrentThread` at `0x1800063cd`
- `KERNEL32!GetCurrentThread` at `0x1800063f5`
- `KERNEL32!GetCurrentThread` at `0x1800060c2`
- `KERNEL32!GetCurrentThread` at `0x1800062c2`
- `KERNEL32!GetCurrentThread` at `0x1800062e5`
- `KERNEL32!GetCurrentThread` at `0x1800063aa`
- `KERNEL32!GetCurrentThread` at `0x1800063cd`
- `KERNEL32!GetCurrentThread` at `0x1800063f5`
- `KERNEL32!GetThreadPriority` at `0x1800062d1`
- `KERNEL32!GetThreadPriority` at `0x1800063b9`
- `KERNEL32!GetThreadPriority` at `0x1800062d1`
- `KERNEL32!GetThreadPriority` at `0x1800063b9`
- `KERNEL32!GetTickCount` at `0x180006298`
- `KERNEL32!GetTickCount` at `0x180006384`
- `KERNEL32!GetTickCount` at `0x180006298`
- `KERNEL32!GetTickCount` at `0x180006384`
- `KERNEL32!SetThreadPriority` at `0x1800060d4`
- `KERNEL32!SetThreadPriority` at `0x1800062f9`
- `KERNEL32!SetThreadPriority` at `0x1800063e1`
- `KERNEL32!SetThreadPriority` at `0x180006407`
- `KERNEL32!SetThreadPriority` at `0x1800060d4`
- `KERNEL32!SetThreadPriority` at `0x1800062f9`
- `KERNEL32!SetThreadPriority` at `0x1800063e1`
- `KERNEL32!SetThreadPriority` at `0x180006407`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180005d75`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180005dde`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180005ff5`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1800061e8`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180005d75`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180005dde`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180005ff5`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1800061e8`
- `KERNEL32!LeaveCriticalSection` at `0x180005c36`
- `KERNEL32!LeaveCriticalSection` at `0x180005c36`
- `KERNEL32!EnterCriticalSection` at `0x180005c21`
- `KERNEL32!EnterCriticalSection` at `0x180005c21`
- `KERNEL32!GetCurrentThreadId` at `0x180005bbb`
- `KERNEL32!GetCurrentThreadId` at `0x180005c5a`
- `KERNEL32!GetCurrentThreadId` at `0x180006164`
- `KERNEL32!GetCurrentThreadId` at `0x180006497`
- `KERNEL32!GetCurrentThreadId` at `0x180005bbb`
- `KERNEL32!GetCurrentThreadId` at `0x180005c5a`
- `KERNEL32!GetCurrentThreadId` at `0x180006164`
- `KERNEL32!GetCurrentThreadId` at `0x180006497`
- `KERNEL32!ReleaseMutex` at `0x180005e28`
- `KERNEL32!ReleaseMutex` at `0x180005ebb`
- `KERNEL32!ReleaseMutex` at `0x180005e28`
- `KERNEL32!ReleaseMutex` at `0x180005ebb`
- `USER32!GetQueueStatus` at `0x1800060e5`
- `USER32!GetQueueStatus` at `0x180006418`
- `USER32!GetQueueStatus` at `0x1800060e5`
- `USER32!GetQueueStatus` at `0x180006418`
- `USER32!DispatchMessageW` at `0x180006265`
- `USER32!DispatchMessageW` at `0x180006351`
- `USER32!DispatchMessageW` at `0x180006265`
- `USER32!DispatchMessageW` at `0x180006351`
- `USER32!PeekMessageW` at `0x180005fc3`
- `USER32!PeekMessageW` at `0x18000614d`
- `USER32!PeekMessageW` at `0x1800061b6`
- `USER32!PeekMessageW` at `0x18000624d`
- `USER32!PeekMessageW` at `0x180006283`
- `USER32!PeekMessageW` at `0x180006339`
- `USER32!PeekMessageW` at `0x18000636f`
- `USER32!PeekMessageW` at `0x18000647e`
- `USER32!PeekMessageW` at `0x180005fc3`
- `USER32!PeekMessageW` at `0x18000614d`
- `USER32!PeekMessageW` at `0x1800061b6`
- `USER32!PeekMessageW` at `0x18000624d`
- `USER32!PeekMessageW` at `0x180006283`
- `USER32!PeekMessageW` at `0x180006339`
- `USER32!PeekMessageW` at `0x18000636f`
- `USER32!PeekMessageW` at `0x18000647e`
- `USER32!MsgWaitForMultipleObjects` at `0x180005f82`
- `USER32!MsgWaitForMultipleObjects` at `0x180006053`
- `USER32!MsgWaitForMultipleObjects` at `0x180005f82`
- `USER32!MsgWaitForMultipleObjects` at `0x180006053`
- `USER32!RegisterWindowMessageW` at `0x18000610f`
- `USER32!RegisterWindowMessageW` at `0x180006440`
- `USER32!RegisterWindowMessageW` at `0x18000610f`
- `USER32!RegisterWindowMessageW` at `0x180006440`
- `USER32!PostThreadMessageW` at `0x18000617b`
- `USER32!PostThreadMessageW` at `0x1800064ae`
- `USER32!PostThreadMessageW` at `0x18000617b`
- `USER32!PostThreadMessageW` at `0x1800064ae`

## pseudocode

```c
__int64 __fastcall CFGControl::CImplMediaSeeking::GetCurrentPosition(
        CFGControl::CImplMediaSeeking *this,
        struct __POSITION *a2)
{
  __int64 *v2; // r14
  CFGControl::CImplMediaSeeking *v3; // rsi
  _DWORD *v5; // r15
  DWORD CurrentThreadId; // eax
  int v7; // ecx
  DWORD v8; // ebx
  int v9; // r13d
  int v10; // ecx
  __int64 v11; // rbx
  int ListSeeking; // r12d
  bool v13; // zf
  struct _RTL_CRITICAL_SECTION *v14; // rdi
  int v15; // ebx
  _QWORD *v16; // rdi
  __int64 v17; // rbx
  DWORD v18; // eax
  int v19; // ecx
  DWORD v20; // r12d
  __int64 v21; // rax
  __int64 v22; // rcx
  int v23; // edx
  __int64 v24; // rcx
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rbx
  HWND v28; // r12
  DWORD v29; // edi
  struct __POSITION *v30; // rax
  DWORD v31; // eax
  struct __POSITION *v32; // rcx
  __int64 v33; // rcx
  HANDLE v34; // rcx
  int v35; // ebx
  unsigned int v36; // r15d
  DWORD v37; // eax
  int v38; // r14d
  DWORD v39; // esi
  DWORD v40; // eax
  HWND v41; // rdi
  DWORD v42; // eax
  int v43; // r14d
  unsigned int v44; // esi
  int v45; // r12d
  DWORD v46; // ebx
  DWORD v47; // eax
  HANDLE v48; // rax
  UINT v49; // r12d
  BOOL v50; // eax
  DWORD v51; // eax
  DWORD v52; // eax
  bool v53; // cf
  DWORD TickCount; // eax
  unsigned int v55; // edx
  unsigned int v56; // ecx
  bool v57; // cc
  HANDLE CurrentThread; // rax
  HANDLE v59; // rax
  DWORD v60; // eax
  unsigned int v61; // edx
  unsigned int v62; // ecx
  HANDLE v63; // rax
  HANDLE v64; // rax
  HANDLE v65; // rax
  UINT v66; // eax
  DWORD v67; // eax
  __int64 v68; // rax
  __int64 v69; // rcx
  struct __POSITION *v70; // rcx
  void *NextI; // rax
  int v72; // eax
  __int64 v73; // rdx
  __int64 v74; // [rsp+30h] [rbp-89h] BYREF
  int v75; // [rsp+38h] [rbp-81h]
  DWORD v76; // [rsp+3Ch] [rbp-7Dh]
  UINT wMsgFilterMin; // [rsp+40h] [rbp-79h]
  DWORD v78; // [rsp+44h] [rbp-75h]
  int v79; // [rsp+48h] [rbp-71h]
  __int64 v80; // [rsp+50h] [rbp-69h] BYREF
  HWND hWnd; // [rsp+58h] [rbp-61h]
  _DWORD *v82; // [rsp+60h] [rbp-59h]
  struct tagMSG Msg; // [rsp+68h] [rbp-51h] BYREF
  HANDLE Handles[2]; // [rsp+98h] [rbp-21h] BYREF
  HANDLE pHandles[2]; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v86; // [rsp+B8h] [rbp-1h]
  _QWORD *v87; // [rsp+C0h] [rbp+7h]
  struct __POSITION **v89; // [rsp+128h] [rbp+6Fh] BYREF
  int nPriority; // [rsp+130h] [rbp+77h]
  int ThreadPriority; // [rsp+138h] [rbp+7Fh]

  v89 = (struct __POSITION **)a2;
  v2 = (__int64 *)a2;
  v3 = this;
  if ( !a2 )
    return 2147500035LL;
  v5 = *(_DWORD **)(*((_QWORD *)this + 4) + 16LL);
  v82 = v5;
  CurrentThreadId = GetCurrentThreadId();
  v7 = v5[2];
  v79 = CurrentThreadId;
  v8 = CurrentThreadId;
  v9 = 1;
  if ( CurrentThreadId == v7 )
    goto LABEL_4;
  wMsgFilterMin = v5[6];
  if ( CurrentThreadId == v5[7] )
    v28 = (HWND)*((_QWORD *)v5 + 2);
  else
    v28 = 0;
  Handles[0] = *(HANDLE *)v5;
  v75 = -1;
  ThreadPriority = 0;
  nPriority = 0;
  Handles[1] = 0;
  v29 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
  if ( v29 )
  {
    v35 = ThreadPriority;
    v36 = v75;
    v37 = 64;
    v38 = ThreadPriority;
    if ( v28 )
      v37 = 72;
    v78 = v37;
    do
    {
      v39 = v36;
      if ( v36 > 0xA )
        v39 = 10;
      v40 = MsgWaitForMultipleObjects(1u, Handles, 0, v39, v37);
      v29 = v40;
      if ( v40 != 1 && (v40 != 258 || v39 == v36) )
        break;
      memset(&Msg, 0, sizeof(Msg));
      if ( v28 && PeekMessageW(&Msg, v28, wMsgFilterMin, wMsgFilterMin, 1u) )
      {
        do
          DispatchMessageW(&Msg);
        while ( PeekMessageW(&Msg, v28, wMsgFilterMin, wMsgFilterMin, 1u) );
      }
      PeekMessageW(&Msg, 0, 0, 0, 0);
      if ( v36 - 1 <= 0xFFFFFFFD )
      {
        TickCount = GetTickCount();
        v55 = TickCount - v38;
        v38 = TickCount;
        v56 = v36 - v55;
        v57 = v55 <= v36;
        v36 = 0;
        if ( v57 )
          v36 = v56;
      }
      if ( !v35 )
      {
        CurrentThread = GetCurrentThread();
        nPriority = GetThreadPriority(CurrentThread);
        if ( (unsigned int)nPriority < 2 )
        {
          v59 = GetCurrentThread();
          SetThreadPriority(v59, 2);
        }
        v35 = 1;
      }
      v29 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
      v37 = v78;
    }
    while ( v29 );
    v3 = this;
    v13 = v35 == 0;
    v8 = v79;
    v2 = (__int64 *)v89;
    v5 = v82;
    if ( !v13 )
    {
      v48 = GetCurrentThread();
      SetThreadPriority(v48, nPriority);
      if ( (GetQueueStatus(8u) & 0x80000) != 0 )
      {
        v49 = wMsgFilterMax;
        if ( wMsgFilterMax || (wMsgFilterMax = RegisterWindowMessageW(L"AMUnblock"), (v49 = wMsgFilterMax) != 0) )
        {
          memset(&Msg, 0, sizeof(Msg));
          do
          {
            v50 = PeekMessageW(&Msg, HWND_MESSAGE|0x2LL, v49, v49, 1u);
            v49 = wMsgFilterMax;
          }
          while ( v50 );
        }
        v51 = GetCurrentThreadId();
        PostThreadMessageW(v51, v49, 0, 0);
      }
    }
  }
  if ( !v29 )
  {
    v5[2] = v8;
LABEL_4:
    ++v5[3];
    v10 = 1;
    goto LABEL_5;
  }
  v10 = 0;
LABEL_5:
  v11 = *((_QWORD *)v3 + 4);
  v74 = 0;
  ListSeeking = 0;
  if ( !v10 )
    v5 = 0;
  v13 = *(_QWORD *)(v11 + 192) == 0;
  v82 = v5;
  Handles[0] = v5;
  if ( v13 )
  {
    v27 = *((_QWORD *)v3 + 9);
    goto LABEL_37;
  }
  v14 = (struct _RTL_CRITICAL_SECTION *)(v11 + 888);
  EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 888));
  v15 = *(_DWORD *)(v11 + 132);
  LeaveCriticalSection(v14);
  if ( !v15 )
  {
    v27 = 0;
    if ( *((_QWORD *)v3 + 10) != 0x7FFFFFFFFFFFFFFFLL )
      v27 = *((_QWORD *)v3 + 10);
    goto LABEL_37;
  }
  v16 = (_QWORD *)*((_QWORD *)v3 + 4);
  v87 = v16;
  v86 = v16[2];
  v17 = v86;
  v18 = GetCurrentThreadId();
  v19 = *(_DWORD *)(v17 + 8);
  v20 = v18;
  v75 = v18;
  if ( v18 == v19 )
    goto LABEL_10;
  wMsgFilterMin = *(_DWORD *)(v17 + 24);
  if ( v18 == *(_DWORD *)(v17 + 28) )
    hWnd = *(HWND *)(v17 + 16);
  else
    hWnd = 0;
  v30 = *(struct __POSITION **)v17;
  nPriority = 0;
  ThreadPriority = 0;
  pHandles[1] = 0;
  pHandles[0] = v30;
  v79 = -1;
  v31 = WaitForMultipleObjectsEx(1u, pHandles, 0, 0, 0);
  if ( v31 )
  {
    v41 = hWnd;
    v42 = 64;
    v43 = nPriority;
    v44 = v79;
    if ( hWnd )
      v42 = 72;
    v45 = nPriority;
    v76 = v42;
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
        v60 = GetTickCount();
        v61 = v60 - v45;
        v45 = v60;
        v62 = v44 - v61;
        v57 = v61 <= v44;
        v44 = 0;
        if ( v57 )
          v44 = v62;
      }
      if ( !v43 )
      {
        v63 = GetCurrentThread();
        ThreadPriority = GetThreadPriority(v63);
        if ( (unsigned int)ThreadPriority < 2 )
        {
          v64 = GetCurrentThread();
          SetThreadPriority(v64, 2);
        }
        v43 = 1;
      }
      v52 = WaitForMultipleObjectsEx(1u, pHandles, 0, 0, 0);
      v41 = hWnd;
      v53 = v52 == 0;
      nPriority = v52;
      v42 = v76;
    }
    while ( !v53 );
    v17 = v86;
    v13 = v43 == 0;
    v2 = (__int64 *)v89;
    v3 = this;
    v5 = v82;
    v16 = v87;
    v20 = v75;
    if ( !v13 )
    {
      v65 = GetCurrentThread();
      SetThreadPriority(v65, ThreadPriority);
      if ( (GetQueueStatus(8u) & 0x80000) != 0 )
      {
        v66 = wMsgFilterMax;
        if ( wMsgFilterMax
          || (v66 = RegisterWindowMessageW(L"AMUnblock"), LODWORD(v89) = v66, (wMsgFilterMax = v66) != 0) )
        {
          memset(&Msg, 0, sizeof(Msg));
          do
          {
            v13 = !PeekMessageW(&Msg, HWND_MESSAGE|0x2LL, v66, v66, 1u);
            v66 = wMsgFilterMax;
          }
          while ( !v13 );
          LODWORD(v89) = wMsgFilterMax;
        }
        v67 = GetCurrentThreadId();
        PostThreadMessageW(v67, (UINT)v89, 0, 0);
      }
    }
    v31 = nPriority;
  }
  if ( !v31 )
  {
    *(_DWORD *)(v17 + 8) = v20;
LABEL_10:
    ++*(_DWORD *)(v17 + 12);
    goto LABEL_11;
  }
  v9 = 0;
LABEL_11:
  v21 = *v16;
  v22 = 0;
  if ( !v9 )
    v17 = 0;
  v80 = 0;
  v89 = (struct __POSITION **)v17;
  v23 = *(_DWORD *)(v21 + 168);
  if ( !v23 )
    goto LABEL_48;
  v24 = v16[26];
  if ( !v24 )
  {
    CAutoMsgMutex::~CAutoMsgMutex((CAutoMsgMutex *)&v89);
    goto LABEL_18;
  }
  if ( v23 == 1 )
  {
    v68 = v16[24];
    if ( v68 )
      v22 = v16[25] - v68;
    else
      v22 = 0;
LABEL_46:
    v80 = v22;
    if ( v22 < 0 )
    {
      v22 = 0;
      v80 = 0;
    }
LABEL_48:
    v74 = v22;
    if ( v17 )
    {
      CMsgMutex::Unlock((CMsgMutex *)v17);
      v22 = v74;
    }
    ListSeeking = 0;
    if ( *((_QWORD *)v3 + 16) )
    {
      CFGControl::CImplMediaSeeking::KillDeadSegments(v3, v22);
      v73 = *((_QWORD *)v3 + 16);
      v27 = (unsigned int)(int)((double)((int)v74 - *(_DWORD *)v73) * *(double *)(v73 + 32) + 0.5)
          + *(_QWORD *)(v73 + 16);
      v74 = v27;
      if ( v27 > *(_QWORD *)(v73 + 24) )
      {
        v27 = *(_QWORD *)(v73 + 24);
        v74 = v27;
      }
    }
    else
    {
      v27 = (unsigned int)(int)((double)(int)v22 * *((double *)v3 + 8) + 0.5);
      v74 = v27;
    }
    goto LABEL_52;
  }
  if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 24LL))(v24, &v80) >= 0 )
  {
    v22 = v80 - v16[24];
    goto LABEL_46;
  }
  if ( v17 )
  {
    v13 = (*(_DWORD *)(v17 + 12))-- == 1;
    if ( v13 )
    {
      v32 = *(struct __POSITION **)v17;
      *(_DWORD *)(v17 + 8) = 0;
      ReleaseMutex(v32);
    }
  }
LABEL_18:
  v25 = *((_QWORD *)v3 + 7);
  if ( v25 )
  {
    ListSeeking = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 96LL))(v25, &v74);
    if ( ListSeeking >= 0 )
    {
      v26 = CFGControl::CImplMediaSeeking::ConvertTimeFormat(v3, &v74, &TIME_FORMAT_MEDIA_TIME, v74, 0);
      v27 = v74;
      ListSeeking = v26;
LABEL_52:
      if ( !*((_BYTE *)v3 + 104) )
      {
        if ( ListSeeking >= 0 )
        {
          v27 += *((_QWORD *)v3 + 9);
          v74 = v27;
        }
        if ( v27 > *((_QWORD *)v3 + 10) )
        {
          v27 = *((_QWORD *)v3 + 10);
          v74 = v27;
        }
      }
      if ( v27 >= 0 )
        goto LABEL_38;
      v27 = 0;
LABEL_37:
      v74 = v27;
LABEL_38:
      if ( v5 )
      {
        v13 = v5[3]-- == 1;
        if ( v13 )
        {
          v34 = *(HANDLE *)v5;
          v5[2] = 0;
          ReleaseMutex(v34);
        }
      }
      if ( ListSeeking >= 0 )
      {
        v33 = *((_QWORD *)v3 + 7);
        if ( v33 )
        {
          if ( v27 == *((_QWORD *)v3 + 10) )
            (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 88LL))(v33, v2);
          else
            return (unsigned int)CFGControl::CImplMediaSeeking::ConvertTimeFormat(
                                   v3,
                                   v2,
                                   0,
                                   v27,
                                   &TIME_FORMAT_MEDIA_TIME);
        }
        else
        {
          *v2 = v27;
        }
      }
      return (unsigned int)ListSeeking;
    }
LABEL_131:
    v27 = v74;
    goto LABEL_52;
  }
  v69 = *((_QWORD *)v3 + 4);
  v89 = 0;
  ListSeeking = CFGControl::GetListSeeking(v69, &v89);
  if ( ListSeeking >= 0 )
  {
    v70 = *v89;
    v89 = (struct __POSITION **)v70;
    if ( v70 )
    {
      while ( 1 )
      {
        NextI = CBaseList::GetNextI(v70, (struct __POSITION **)&v89);
        v72 = (*(__int64 (__fastcall **)(void *, __int64 *))(*(_QWORD *)NextI + 96LL))(NextI, &v74);
        ListSeeking = v72;
        if ( !v72 )
          break;
        if ( !v89 )
        {
          if ( v72 < 0 )
            goto LABEL_131;
          goto LABEL_130;
        }
      }
    }
    else
    {
LABEL_130:
      ListSeeking = -2147467262;
    }
    goto LABEL_131;
  }
  CAutoMsgMutex::~CAutoMsgMutex((CAutoMsgMutex *)Handles);
  return (unsigned int)ListSeeking;
}

```

## disassembly

```asm
0x180005b50  mov     [rsp-8+arg_8], rdx
0x180005b55  mov     [rsp-8+arg_0], rcx
0x180005b5a  push    rbp
0x180005b5b  push    rsi
0x180005b5c  push    r14
0x180005b5e  lea     rbp, [rsp-47h]
0x180005b63  sub     rsp, 100h
0x180005b6a  mov     r14, rdx
0x180005b6d  mov     rsi, rcx
0x180005b70  test    rdx, rdx
0x180005b73  jnz     short loc_180005B87
0x180005b75  mov     eax, 80004003h
0x180005b7a  add     rsp, 100h
0x180005b81  pop     r14
0x180005b83  pop     rsi
0x180005b84  pop     rbp
0x180005b85  retn
0x180005b87  mov     rax, [rcx+20h]
0x180005b8b  mov     [rsp+110h+var_18], rbx
0x180005b93  mov     [rsp+110h+var_20], rdi
0x180005b9b  mov     [rsp+110h+var_28], r12
0x180005ba3  mov     [rsp+110h+var_30], r13
0x180005bab  mov     [rsp+110h+var_38], r15
0x180005bb3  mov     r15, [rax+10h]
0x180005bb7  mov     [rbp+57h+var_B0], r15
0x180005bbb  call    cs:__imp_GetCurrentThreadId
0x180005bc2  nop     dword ptr [rax+rax+00h]
0x180005bc7  mov     ecx, [r15+8]
0x180005bcb  xor     r8d, r8d; bWaitAll
0x180005bce  mov     [rbp+57h+var_C8], eax
0x180005bd1  mov     ebx, eax
0x180005bd3  mov     r13d, 1
0x180005bd9  cmp     eax, ecx
0x180005bdb  jnz     loc_180005D36
0x180005be1  inc     dword ptr [r15+0Ch]
0x180005be5  mov     ecx, r13d
0x180005be8  mov     rbx, [rsi+20h]
0x180005bec  lea     rdi, TIME_FORMAT_MEDIA_TIME
0x180005bf3  test    ecx, ecx
0x180005bf5  mov     [rsp+110h+var_E0], r8
0x180005bfa  mov     r12d, r8d
0x180005bfd  cmovz   r15, r8
0x180005c01  cmp     qword ptr [rbx+0C0h], 0
0x180005c09  mov     [rbp+57h+var_B0], r15
0x180005c0d  mov     [rbp+57h+Handles], r15
0x180005c11  jz      loc_180006221
0x180005c17  lea     rdi, [rbx+378h]
0x180005c1e  mov     rcx, rdi; lpCriticalSection
0x180005c21  call    cs:__imp_EnterCriticalSection
0x180005c28  nop     dword ptr [rax+rax+00h]
0x180005c2d  mov     ebx, [rbx+84h]
0x180005c33  mov     rcx, rdi; lpCriticalSection
0x180005c36  call    cs:__imp_LeaveCriticalSection
0x180005c3d  nop     dword ptr [rax+rax+00h]
0x180005c42  test    ebx, ebx
0x180005c44  jz      loc_180005E39
0x180005c4a  mov     rdi, [rsi+20h]
0x180005c4e  mov     [rbp+57h+var_50], rdi
0x180005c52  mov     rbx, [rdi+10h]
0x180005c56  mov     [rbp+57h+var_58], rbx
0x180005c5a  call    cs:__imp_GetCurrentThreadId
0x180005c61  nop     dword ptr [rax+rax+00h]
0x180005c66  mov     ecx, [rbx+8]
0x180005c69  mov     r12d, eax
0x180005c6c  mov     [rsp+110h+var_D8], eax
0x180005c70  cmp     eax, ecx
0x180005c72  jnz     loc_180005D9F
0x180005c78  inc     dword ptr [rbx+0Ch]
0x180005c7b  xor     r8d, r8d
0x180005c7e  mov     rax, [rdi]
0x180005c81  test    r13d, r13d
0x180005c84  mov     rcx, r8
0x180005c87  cmovz   rbx, r8
0x180005c8b  mov     [rbp+57h+var_C0], rcx
0x180005c8f  mov     [rbp+57h+arg_8], rbx
0x180005c93  mov     edx, [rax+0A8h]
0x180005c99  test    edx, edx
0x180005c9b  jz      loc_180005EE7
0x180005ca1  mov     rcx, [rdi+0D0h]
0x180005ca8  test    rcx, rcx
0x180005cab  jz      loc_1800064C8
0x180005cb1  cmp     edx, 1
0x180005cb4  jz      loc_1800064D6
0x180005cba  mov     rax, [rcx]
0x180005cbd  lea     rdx, [rbp+57h+var_C0]
0x180005cc1  mov     rax, [rax+18h]
0x180005cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cca  test    eax, eax
0x180005ccc  jns     loc_180005EC9
0x180005cd2  test    rbx, rbx
0x180005cd5  jnz     loc_180005E14
0x180005cdb  mov     rcx, [rsi+38h]
0x180005cdf  test    rcx, rcx
0x180005ce2  jz      loc_1800064F9
0x180005ce8  mov     rax, [rcx]
0x180005ceb  lea     rdx, [rsp+110h+var_E0]
0x180005cf0  mov     rax, [rax+60h]
0x180005cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cf9  mov     r12d, eax
0x180005cfc  test    eax, eax
0x180005cfe  js      loc_18000656B
0x180005d04  mov     r9, [rsp+110h+var_E0]; __int64
0x180005d09  lea     rdi, TIME_FORMAT_MEDIA_TIME
0x180005d10  mov     r8, rdi; struct _GUID *
0x180005d13  mov     qword ptr [rsp+110h+bAlertable], 0; struct _GUID *
0x180005d1c  lea     rdx, [rsp+110h+var_E0]; __int64 *
0x180005d21  mov     rcx, rsi; this
0x180005d24  call    ?ConvertTimeFormat@CImplMediaSeeking@CFGControl@@UEAAJPEA_JPEBU_GUID@@_J1@Z; CFGControl::CImplMediaSeeking::ConvertTimeFormat(__int64 *,_GUID const *,__int64,_GUID const *)
0x180005d29  mov     rbx, [rsp+110h+var_E0]
0x180005d2e  mov     r12d, eax
0x180005d31  jmp     loc_180006577
0x180005d36  mov     eax, [r15+18h]
0x180005d3a  mov     [rbp+57h+wMsgFilterMin], eax
0x180005d3d  cmp     ebx, [r15+1Ch]
0x180005d41  jnz     loc_180005E06
0x180005d47  mov     r12, [r15+10h]
0x180005d4b  mov     rax, [r15]
0x180005d4e  lea     rdx, [rbp+57h+Handles]; lpHandles
0x180005d52  xor     r9d, r9d; dwMilliseconds
0x180005d55  mov     [rbp+57h+Handles], rax
0x180005d59  mov     ecx, r13d; nCount
0x180005d5c  mov     [rsp+110h+var_D8], 0FFFFFFFFh
0x180005d64  mov     [rbp+57h+arg_18], r8d
0x180005d68  mov     [rbp+57h+nPriority], r8d
0x180005d6c  mov     [rbp+57h+var_70], r8
0x180005d70  mov     [rsp+110h+bAlertable], r8d; bAlertable
0x180005d75  call    cs:__imp_WaitForMultipleObjectsEx
0x180005d7c  nop     dword ptr [rax+rax+00h]
0x180005d81  mov     edi, eax
0x180005d83  cmp     eax, r13d
0x180005d86  jnb     loc_180005F44
0x180005d8c  xor     r8d, r8d
0x180005d8f  test    edi, edi
0x180005d91  jz      loc_18000630D
0x180005d97  mov     ecx, r8d
0x180005d9a  jmp     loc_180005BE8
0x180005d9f  mov     eax, [rbx+18h]
0x180005da2  xor     ecx, ecx
0x180005da4  mov     [rbp+57h+wMsgFilterMin], eax
0x180005da7  cmp     r12d, [rbx+1Ch]
0x180005dab  jnz     short loc_180005E0E
0x180005dad  mov     rax, [rbx+10h]
0x180005db1  mov     [rbp+57h+hWnd], rax
0x180005db5  mov     rax, [rbx]
0x180005db8  lea     rdx, [rbp+57h+pHandles]; lpHandles
0x180005dbc  mov     [rbp+57h+nPriority], ecx
0x180005dbf  xor     r9d, r9d; dwMilliseconds
0x180005dc2  mov     [rbp+57h+arg_18], ecx
0x180005dc5  xor     r8d, r8d; bWaitAll
0x180005dc8  mov     [rbp+57h+var_60], rcx
0x180005dcc  mov     [rsp+110h+bAlertable], ecx; bAlertable
0x180005dd0  mov     ecx, r13d; nCount
0x180005dd3  mov     [rbp+57h+pHandles], rax
0x180005dd7  mov     [rbp+57h+var_C8], 0FFFFFFFFh
0x180005dde  call    cs:__imp_WaitForMultipleObjectsEx
0x180005de5  nop     dword ptr [rax+rax+00h]
0x180005dea  cmp     eax, r13d
0x180005ded  jnb     loc_180006014
0x180005df3  test    eax, eax
0x180005df5  jz      loc_1800064BF
0x180005dfb  xor     r8d, r8d
0x180005dfe  mov     r13d, r8d
0x180005e01  jmp     loc_180005C7E
0x180005e06  mov     r12, r8
0x180005e09  jmp     loc_180005D4B
0x180005e0e  mov     [rbp+57h+hWnd], rcx
0x180005e12  jmp     short loc_180005DB5
0x180005e14  add     dword ptr [rbx+0Ch], 0FFFFFFFFh
0x180005e18  jnz     loc_180005CDB
0x180005e1e  mov     rcx, [rbx]; hMutex
0x180005e21  mov     dword ptr [rbx+8], 0
0x180005e28  call    cs:__imp_ReleaseMutex
0x180005e2f  nop     dword ptr [rax+rax+00h]
0x180005e34  jmp     loc_180005CDB
0x180005e39  xor     r8d, r8d
0x180005e3c  lea     rdi, TIME_FORMAT_MEDIA_TIME
0x180005e43  mov     rcx, 7FFFFFFFFFFFFFFFh
0x180005e4d  mov     ebx, r8d
0x180005e50  cmp     [rsi+50h], rcx
0x180005e54  cmovnz  rbx, [rsi+50h]
0x180005e59  jmp     short loc_180005E5E
0x180005e5b  mov     rbx, r8
0x180005e5e  mov     [rsp+110h+var_E0], rbx
0x180005e63  test    r15, r15
0x180005e66  jnz     short loc_180005EAD
0x180005e68  test    r12d, r12d
0x180005e6b  js      short loc_180005E7D
0x180005e6d  mov     rcx, [rsi+38h]
0x180005e71  test    rcx, rcx
0x180005e74  jnz     loc_180006604
0x180005e7a  mov     [r14], rbx
0x180005e7d  mov     r15, [rsp+110h+var_38]
0x180005e85  mov     eax, r12d
0x180005e88  mov     r12, [rsp+110h+var_28]
0x180005e90  mov     r13, [rsp+110h+var_30]
0x180005e98  mov     rdi, [rsp+110h+var_20]
0x180005ea0  mov     rbx, [rsp+110h+var_18]
0x180005ea8  jmp     loc_180005B7A
0x180005ead  add     dword ptr [r15+0Ch], 0FFFFFFFFh
0x180005eb2  jnz     short loc_180005E68
0x180005eb4  mov     rcx, [r15]; hMutex
0x180005eb7  mov     [r15+8], r8d
0x180005ebb  call    cs:__imp_ReleaseMutex
0x180005ec2  nop     dword ptr [rax+rax+00h]
0x180005ec7  jmp     short loc_180005E68
0x180005ec9  mov     rcx, [rbp+57h+var_C0]
0x180005ecd  sub     rcx, [rdi+0C0h]
0x180005ed4  xor     r8d, r8d
0x180005ed7  mov     [rbp+57h+var_C0], rcx
0x180005edb  test    rcx, rcx
0x180005ede  jns     short loc_180005EE7
0x180005ee0  mov     rcx, r8
0x180005ee3  mov     [rbp+57h+var_C0], rcx
0x180005ee7  mov     [rsp+110h+var_E0], rcx
0x180005eec  test    rbx, rbx
0x180005eef  jnz     loc_18000620C
0x180005ef5  cmp     qword ptr [rsi+80h], 0
0x180005efd  mov     r12d, r8d
0x180005f00  jnz     loc_18000657F
0x180005f06  xorps   xmm0, xmm0
0x180005f09  lea     rdi, TIME_FORMAT_MEDIA_TIME
0x180005f10  cvtsi2sd xmm0, rcx
0x180005f15  mulsd   xmm0, qword ptr [rsi+40h]
0x180005f1a  addsd   xmm0, cs:__real@3fe0000000000000
0x180005f22  cvttsd2si rbx, xmm0
0x180005f27  mov     [rsp+110h+var_E0], rbx
0x180005f2c  cmp     byte ptr [rsi+68h], 0
0x180005f30  jz      loc_1800065DC
0x180005f36  test    rbx, rbx
0x180005f39  jns     loc_180005E63
0x180005f3f  jmp     loc_180005E5B
0x180005f44  mov     ebx, [rbp+57h+arg_18]
0x180005f47  test    r12, r12
0x180005f4a  mov     r15d, [rsp+110h+var_D8]
0x180005f4f  mov     eax, 40h ; '@'
0x180005f54  mov     ecx, 48h ; 'H'
0x180005f59  mov     r14d, ebx
0x180005f5c  cmovnz  eax, ecx
0x180005f5f  mov     [rbp+57h+var_CC], eax
0x180005f62  mov     ecx, 0Ah
0x180005f67  mov     [rsp+110h+bAlertable], eax; dwWakeMask
0x180005f6b  cmp     r15d, 0Ah
0x180005f6f  lea     rdx, [rbp+57h+Handles]; pHandles
0x180005f73  mov     esi, r15d
0x180005f76  cmova   esi, ecx
0x180005f79  xor     r8d, r8d; fWaitAll
0x180005f7c  mov     r9d, esi; dwMilliseconds
0x180005f7f  mov     ecx, r13d; nCount
0x180005f82  call    cs:__imp_MsgWaitForMultipleObjects
0x180005f89  nop     dword ptr [rax+rax+00h]
0x180005f8e  mov     edi, eax
0x180005f90  cmp     eax, r13d
0x180005f93  jnz     loc_1800060A0
0x180005f99  xorps   xmm0, xmm0
0x180005f9c  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x180005fa0  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x180005fa4  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x180005fa8  test    r12, r12
0x180005fab  jnz     loc_180006238
0x180005fb1  xor     edi, edi
0x180005fb3  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180005fb7  xor     r9d, r9d; wMsgFilterMax
0x180005fba  mov     [rsp+110h+bAlertable], edi; wRemoveMsg
0x180005fbe  xor     r8d, r8d; wMsgFilterMin
0x180005fc1  xor     edx, edx; hWnd
0x180005fc3  call    cs:__imp_PeekMessageW
0x180005fca  nop     dword ptr [rax+rax+00h]
0x180005fcf  lea     eax, [r15-1]
0x180005fd3  cmp     eax, 0FFFFFFFDh
0x180005fd6  jbe     loc_180006298
0x180005fdc  test    ebx, ebx
0x180005fde  jz      loc_1800062C2
0x180005fe4  xor     r9d, r9d; dwMilliseconds
0x180005fe7  mov     [rsp+110h+bAlertable], edi; bAlertable
0x180005feb  xor     r8d, r8d; bWaitAll
0x180005fee  lea     rdx, [rbp+57h+Handles]; lpHandles
0x180005ff2  mov     ecx, r13d; nCount
0x180005ff5  call    cs:__imp_WaitForMultipleObjectsEx
0x180005ffc  nop     dword ptr [rax+rax+00h]
0x180006001  mov     edi, eax
0x180006003  cmp     eax, r13d
0x180006006  mov     eax, [rbp+57h+var_CC]
0x180006009  jnb     loc_180005F62
0x18000600f  jmp     loc_1800060AB
0x180006014  mov     rdi, [rbp+57h+hWnd]
0x180006018  mov     eax, 40h ; '@'
0x18000601d  mov     r14d, [rbp+57h+nPriority]
0x180006021  test    rdi, rdi
0x180006024  mov     esi, [rbp+57h+var_C8]
0x180006027  mov     ecx, 48h ; 'H'
0x18000602c  cmovnz  eax, ecx
0x18000602f  mov     r12d, r14d
0x180006032  mov     [rbp+57h+var_D4], eax
0x180006035  mov     ecx, 0Ah
0x18000603a  mov     [rsp+110h+bAlertable], eax; dwWakeMask
0x18000603e  cmp     esi, 0Ah
0x180006041  lea     rdx, [rbp+57h+pHandles]; pHandles
0x180006045  mov     ebx, esi
0x180006047  cmova   ebx, ecx
0x18000604a  xor     r8d, r8d; fWaitAll
  ... truncated ...
```
