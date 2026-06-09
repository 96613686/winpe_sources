# CFGControl::CImplMediaControl::Stop(void)

- ea: `0x180005390`
- end: `0x180005b43`
- name: `?Stop@CImplMediaControl@CFGControl@@UEAAJXZ`
- size: `1971`
- prototype: `__int64 __fastcall(CFGControl::CImplMediaControl *__hidden this)`
- caller_count: `6`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002a428`
- `0x180070f78`
- `0x180071070`
- `0x1800752b0`
- `0x1800763b8`
- `0x18007685c`

## callees

- `0x1800032f0`
- `0x180004454`
- `0x180005358`
- `0x180005390`
- `0x180005b50`
- `0x180013810`
- `0x18001d3b0`
- `0x18001f5c0`
- `0x180027efc`
- `0x18002cd84`
- `0x18005d570`
- `0x180060a3c`
- `0x18015e010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18000552e`
- `KERNEL32!GetCurrentThread` at `0x180005551`
- `KERNEL32!GetCurrentThread` at `0x1800055b0`
- `KERNEL32!GetCurrentThread` at `0x180005806`
- `KERNEL32!GetCurrentThread` at `0x180005829`
- `KERNEL32!GetCurrentThread` at `0x180005898`
- `KERNEL32!GetCurrentThread` at `0x18000552e`
- `KERNEL32!GetCurrentThread` at `0x180005551`
- `KERNEL32!GetCurrentThread` at `0x1800055b0`
- `KERNEL32!GetCurrentThread` at `0x180005806`
- `KERNEL32!GetCurrentThread` at `0x180005829`
- `KERNEL32!GetCurrentThread` at `0x180005898`
- `KERNEL32!GetThreadPriority` at `0x18000553d`
- `KERNEL32!GetThreadPriority` at `0x180005815`
- `KERNEL32!GetThreadPriority` at `0x18000553d`
- `KERNEL32!GetThreadPriority` at `0x180005815`
- `KERNEL32!GetTickCount` at `0x18000550b`
- `KERNEL32!GetTickCount` at `0x1800057dd`
- `KERNEL32!GetTickCount` at `0x18000550b`
- `KERNEL32!GetTickCount` at `0x1800057dd`
- `KERNEL32!SetThreadPriority` at `0x180005564`
- `KERNEL32!SetThreadPriority` at `0x1800055c2`
- `KERNEL32!SetThreadPriority` at `0x18000583c`
- `KERNEL32!SetThreadPriority` at `0x1800058aa`
- `KERNEL32!SetThreadPriority` at `0x180005564`
- `KERNEL32!SetThreadPriority` at `0x1800055c2`
- `KERNEL32!SetThreadPriority` at `0x18000583c`
- `KERNEL32!SetThreadPriority` at `0x1800058aa`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180005425`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000558c`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1800056f3`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180005864`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180005425`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000558c`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1800056f3`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180005864`
- `KERNEL32!GetCurrentThreadId` at `0x1800053bc`
- `KERNEL32!GetCurrentThreadId` at `0x18000564e`
- `KERNEL32!GetCurrentThreadId` at `0x180005695`
- `KERNEL32!GetCurrentThreadId` at `0x180005936`
- `KERNEL32!GetCurrentThreadId` at `0x1800053bc`
- `KERNEL32!GetCurrentThreadId` at `0x18000564e`
- `KERNEL32!GetCurrentThreadId` at `0x180005695`
- `KERNEL32!GetCurrentThreadId` at `0x180005936`
- `USER32!GetQueueStatus` at `0x1800055d3`
- `USER32!GetQueueStatus` at `0x1800058bb`
- `USER32!GetQueueStatus` at `0x1800055d3`
- `USER32!GetQueueStatus` at `0x1800058bb`
- `USER32!DispatchMessageW` at `0x1800054b2`
- `USER32!DispatchMessageW` at `0x180005784`
- `USER32!DispatchMessageW` at `0x1800054b2`
- `USER32!DispatchMessageW` at `0x180005784`
- `USER32!PeekMessageW` at `0x1800054d3`
- `USER32!PeekMessageW` at `0x1800054f7`
- `USER32!PeekMessageW` at `0x180005638`
- `USER32!PeekMessageW` at `0x1800057a5`
- `USER32!PeekMessageW` at `0x1800057c9`
- `USER32!PeekMessageW` at `0x180005920`
- `USER32!PeekMessageW` at `0x1800054d3`
- `USER32!PeekMessageW` at `0x1800054f7`
- `USER32!PeekMessageW` at `0x180005638`
- `USER32!PeekMessageW` at `0x1800057a5`
- `USER32!PeekMessageW` at `0x1800057c9`
- `USER32!PeekMessageW` at `0x180005920`
- `USER32!MsgWaitForMultipleObjects` at `0x18000546f`
- `USER32!MsgWaitForMultipleObjects` at `0x180005740`
- `USER32!MsgWaitForMultipleObjects` at `0x18000546f`
- `USER32!MsgWaitForMultipleObjects` at `0x180005740`
- `USER32!RegisterWindowMessageW` at `0x1800055fb`
- `USER32!RegisterWindowMessageW` at `0x1800058e3`
- `USER32!RegisterWindowMessageW` at `0x1800055fb`
- `USER32!RegisterWindowMessageW` at `0x1800058e3`
- `USER32!PostThreadMessageW` at `0x180005664`
- `USER32!PostThreadMessageW` at `0x18000594c`
- `USER32!PostThreadMessageW` at `0x180005664`
- `USER32!PostThreadMessageW` at `0x18000594c`
- `USER32!KillTimer` at `0x180005a52`
- `USER32!KillTimer` at `0x180005a52`

## pseudocode

```c
__int64 __fastcall CFGControl::CImplMediaControl::Stop(CFGControl::CImplMediaControl *this)
{
  CFGControl::CImplMediaControl *v1; // r13
  void **v2; // r15
  DWORD CurrentThreadId; // eax
  int v4; // edx
  unsigned int v5; // ebx
  DWORD v6; // esi
  HWND v7; // r14
  void *v8; // rax
  DWORD v9; // edi
  int v10; // r13d
  DWORD v11; // esi
  DWORD v12; // eax
  DWORD TickCount; // eax
  HANDLE CurrentThread; // rax
  HANDLE v15; // rax
  bool v16; // zf
  HANDLE v17; // rax
  UINT v18; // ebx
  BOOL v19; // eax
  DWORD v20; // eax
  __int64 *v21; // rax
  __int64 v22; // rdi
  CMsgMutex *v23; // rsi
  DWORD v24; // eax
  CFilterGraph *v25; // rcx
  DWORD v26; // ebx
  HWND v27; // r12
  DWORD v28; // r14d
  int v29; // r13d
  DWORD v30; // r15d
  unsigned int v31; // esi
  DWORD v32; // ebx
  DWORD v33; // eax
  DWORD v34; // eax
  HANDLE v35; // rax
  HANDLE v36; // rax
  HANDLE v37; // rax
  UINT v38; // ebx
  BOOL v39; // eax
  DWORD v40; // eax
  struct IUnknown *v41; // rdx
  _QWORD *v42; // rbx
  __int64 v43; // rbx
  int v44; // eax
  __int64 v45; // rcx
  int v46; // eax
  int v47; // ebx
  unsigned int nPriority; // [rsp+30h] [rbp-59h]
  UINT nPrioritya; // [rsp+30h] [rbp-59h]
  UINT wMsgFilterMin; // [rsp+38h] [rbp-51h]
  void **v52; // [rsp+40h] [rbp-49h]
  MSG Msg; // [rsp+48h] [rbp-41h] BYREF
  HANDLE Handles[2]; // [rsp+78h] [rbp-11h] BYREF
  HANDLE pHandles[2]; // [rsp+88h] [rbp-1h] BYREF
  __int64 v56; // [rsp+98h] [rbp+Fh]
  CFGControl::CImplMediaControl *v57; // [rsp+F0h] [rbp+67h] BYREF
  DWORD v58; // [rsp+F8h] [rbp+6Fh]
  unsigned int v59; // [rsp+100h] [rbp+77h]
  int ThreadPriority; // [rsp+108h] [rbp+7Fh]

  v57 = this;
  v1 = this;
  v2 = *(void ***)(*((_QWORD *)this + 5) + 16LL);
  v52 = v2;
  CurrentThreadId = GetCurrentThreadId();
  v4 = *((_DWORD *)v2 + 2);
  v5 = -1;
  v58 = CurrentThreadId;
  v6 = CurrentThreadId;
  v59 = -1;
  if ( CurrentThreadId == v4 )
    goto LABEL_36;
  wMsgFilterMin = *((_DWORD *)v2 + 6);
  if ( CurrentThreadId == *((_DWORD *)v2 + 7) )
    v7 = (HWND)v2[2];
  else
    v7 = 0;
  v8 = *v2;
  nPriority = 0;
  Handles[1] = 0;
  ThreadPriority = 0;
  Handles[0] = v8;
  v9 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
  if ( v9 )
  {
    v10 = 0;
    do
    {
      v11 = v5;
      if ( v5 > 0xA )
        v11 = 10;
      v12 = MsgWaitForMultipleObjects(1u, Handles, 0, v11, v7 != 0 ? 72 : 64);
      v9 = v12;
      if ( v12 != 1 && (v12 != 258 || v11 == v5) )
        break;
      memset(&Msg, 0, sizeof(Msg));
      if ( v7 )
      {
        while ( PeekMessageW(&Msg, v7, wMsgFilterMin, wMsgFilterMin, 1u) )
          DispatchMessageW(&Msg);
      }
      PeekMessageW(&Msg, 0, 0, 0, 0);
      if ( v5 - 1 <= 0xFFFFFFFD )
      {
        TickCount = GetTickCount();
        if ( TickCount - ThreadPriority <= v5 )
          v5 -= TickCount - ThreadPriority;
        else
          v5 = 0;
        ThreadPriority = TickCount;
      }
      if ( !v10 )
      {
        CurrentThread = GetCurrentThread();
        nPriority = GetThreadPriority(CurrentThread);
        if ( nPriority < 2 )
        {
          v15 = GetCurrentThread();
          SetThreadPriority(v15, 2);
        }
        v10 = 1;
      }
      v9 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
    }
    while ( v9 );
    v16 = v10 == 0;
    v1 = v57;
    if ( !v16 )
    {
      v17 = GetCurrentThread();
      SetThreadPriority(v17, nPriority);
      if ( (GetQueueStatus(8u) & 0x80000) != 0 )
      {
        v18 = wMsgFilterMax;
        if ( wMsgFilterMax || (wMsgFilterMax = RegisterWindowMessageW(L"AMUnblock"), (v18 = wMsgFilterMax) != 0) )
        {
          memset(&Msg, 0, sizeof(Msg));
          do
          {
            v19 = PeekMessageW(&Msg, HWND_MESSAGE|0x2LL, v18, v18, 1u);
            v18 = wMsgFilterMax;
          }
          while ( v19 );
        }
        v20 = GetCurrentThreadId();
        PostThreadMessageW(v20, v18, 0, 0);
      }
    }
    v6 = v58;
  }
  if ( !v9 )
  {
    *((_DWORD *)v2 + 2) = v6;
LABEL_36:
    ++*((_DWORD *)v2 + 3);
    goto LABEL_37;
  }
  v2 = 0;
  v52 = 0;
LABEL_37:
  v21 = (__int64 *)*((_QWORD *)v1 + 5);
  Handles[0] = v2;
  v22 = *v21;
  v56 = v22;
  v23 = (CMsgMutex *)(v22 + 256);
  v24 = GetCurrentThreadId();
  v25 = (CFilterGraph *)*(unsigned int *)(v22 + 264);
  v26 = v24;
  v58 = v24;
  if ( v24 == (_DWORD)v25 )
  {
LABEL_73:
    ++*(_DWORD *)(v22 + 268);
    goto LABEL_74;
  }
  nPrioritya = *(_DWORD *)(v22 + 280);
  if ( v24 == *(_DWORD *)(v22 + 284) )
    v27 = *(HWND *)(v22 + 272);
  else
    v27 = 0;
  pHandles[0] = *(HANDLE *)v23;
  ThreadPriority = 0;
  pHandles[1] = 0;
  v28 = WaitForMultipleObjectsEx(1u, pHandles, 0, 0, 0);
  if ( v28 )
  {
    v29 = 0;
    v30 = 0;
    do
    {
      v31 = v59;
      v32 = v59;
      if ( v59 > 0xA )
        v32 = 10;
      v33 = MsgWaitForMultipleObjects(1u, pHandles, 0, v32, v27 != 0 ? 72 : 64);
      v28 = v33;
      if ( v33 != 1 && (v33 != 258 || v32 == v31) )
        break;
      memset(&Msg, 0, sizeof(Msg));
      if ( v27 )
      {
        while ( PeekMessageW(&Msg, v27, nPrioritya, nPrioritya, 1u) )
          DispatchMessageW(&Msg);
      }
      PeekMessageW(&Msg, 0, 0, 0, 0);
      if ( v31 - 1 <= 0xFFFFFFFD )
      {
        v34 = GetTickCount();
        if ( v34 - v30 <= v31 )
          v59 = v31 - (v34 - v30);
        else
          v59 = 0;
        v30 = v34;
      }
      if ( !v29 )
      {
        v35 = GetCurrentThread();
        ThreadPriority = GetThreadPriority(v35);
        if ( (unsigned int)ThreadPriority < 2 )
        {
          v36 = GetCurrentThread();
          SetThreadPriority(v36, 2);
        }
        v29 = 1;
      }
      v28 = WaitForMultipleObjectsEx(1u, pHandles, 0, 0, 0);
    }
    while ( v28 );
    v22 = v56;
    v16 = v29 == 0;
    v2 = v52;
    v1 = v57;
    v23 = (CMsgMutex *)(v56 + 256);
    if ( !v16 )
    {
      v37 = GetCurrentThread();
      SetThreadPriority(v37, ThreadPriority);
      if ( (GetQueueStatus(8u) & 0x80000) != 0 )
      {
        v38 = wMsgFilterMax;
        if ( wMsgFilterMax || (wMsgFilterMax = RegisterWindowMessageW(L"AMUnblock"), (v38 = wMsgFilterMax) != 0) )
        {
          memset(&Msg, 0, sizeof(Msg));
          do
          {
            v39 = PeekMessageW(&Msg, HWND_MESSAGE|0x2LL, v38, v38, 1u);
            v38 = wMsgFilterMax;
          }
          while ( v39 );
        }
        v40 = GetCurrentThreadId();
        PostThreadMessageW(v40, v38, 0, 0);
      }
    }
    v26 = v58;
  }
  if ( !v28 )
  {
    *(_DWORD *)(v22 + 264) = v26;
    goto LABEL_73;
  }
  v23 = 0;
LABEL_74:
  v57 = v23;
  v41 = *(struct IUnknown **)(v22 + 648);
  if ( v41 )
  {
    CFilterGraph::CallThroughFrameStepPropertySet(v25, v41, 2u, 0);
    CImplMediaEvent::CEventStore::ClearEvents((CImplMediaEvent::CEventStore *)(*(_QWORD *)(v22 + 248) + 808LL), 36);
    ++*(_DWORD *)(*(_QWORD *)(v22 + 248) + 168LL);
    ATL::AtlComPtrAssign((struct IUnknown **)(v22 + 648), 0);
    v42 = (_QWORD *)(v22 + 656);
    if ( *(_DWORD *)(v22 + 664) == 1 && *v42 )
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v42 + 32LL))(*v42, 2147500036LL);
    *(_DWORD *)(v22 + 664) = 0;
    ATL::AtlComPtrAssign((struct IUnknown **)(v22 + 656), 0);
    CAutoMsgMutex::~CAutoMsgMutex((CAutoMsgMutex *)&v57);
  }
  else if ( v23 )
  {
    CMsgMutex::Unlock(v23);
  }
  v43 = *((_QWORD *)v1 + 5);
  v44 = *(_DWORD *)(v43 + 176);
  if ( v44 == 1025 )
    goto LABEL_93;
  if ( v44 )
  {
    KillTimer(*(HWND *)(v43 + 504), 1u);
    *(_DWORD *)(v43 + 176) = 0;
  }
  *(_DWORD *)(v43 + 136) = 0;
  ++*(_DWORD *)(v43 + 164);
  *(_DWORD *)(*((_QWORD *)v1 + 5) + 172LL) = 0;
  v45 = **((_QWORD **)v1 + 5);
  v46 = *(_DWORD *)(v45 + 168);
  if ( v46 != 2 )
  {
    if ( v46 )
      goto LABEL_88;
LABEL_93:
    CAutoMsgMutex::~CAutoMsgMutex((CAutoMsgMutex *)Handles);
    return 0;
  }
  CFilterGraph::Pause((CFilterGraph *)(v45 + 152));
LABEL_88:
  CFGControl::CImplMediaSeeking::ClearSegments((CFGControl::CImplMediaSeeking *)(*((_QWORD *)v1 + 5) + 968LL));
  CFGControl::CImplMediaSeeking::GetCurrentPosition(
    (CFGControl::CImplMediaSeeking *)(*((_QWORD *)v1 + 5) + 968LL),
    (__int64 *)(*((_QWORD *)v1 + 5) + 1056LL));
  v47 = CFilterGraph::Stop((CFilterGraph *)(**((_QWORD **)v1 + 5) + 152LL));
  CFGControl::CImplMediaSeeking::AfterStop((CFGControl::CImplMediaSeeking *)(*((_QWORD *)v1 + 5) + 968LL));
  if ( v47 >= 0 )
    CImplMediaEvent::Notify((CImplMediaEvent *)(*((_QWORD *)v1 + 5) + 792LL), 50, 0, 0);
  if ( v2 )
    CMsgMutex::Unlock((CMsgMutex *)v2);
  return (unsigned int)v47;
}

```

## disassembly

```asm
0x180005390  mov     [rsp-8+arg_0], rcx
0x180005395  push    rbp
0x180005396  push    rbx
0x180005397  push    rsi
0x180005398  push    rdi
0x180005399  push    r12
0x18000539b  push    r13
0x18000539d  push    r14
0x18000539f  push    r15
0x1800053a1  lea     rbp, [rsp-1Fh]
0x1800053a6  sub     rsp, 0A8h
0x1800053ad  mov     rax, [rcx+28h]
0x1800053b1  mov     r13, rcx
0x1800053b4  mov     r15, [rax+10h]
0x1800053b8  mov     [rbp+57h+var_A0], r15
0x1800053bc  call    cs:__imp_GetCurrentThreadId
0x1800053c3  nop     dword ptr [rax+rax+00h]
0x1800053c8  mov     edx, [r15+8]
0x1800053cc  or      ebx, 0FFFFFFFFh
0x1800053cf  mov     [rbp+57h+arg_8], eax
0x1800053d2  mov     esi, eax
0x1800053d4  mov     [rbp+57h+arg_10], ebx
0x1800053d7  cmp     eax, edx
0x1800053d9  jz      loc_18000567B
0x1800053df  mov     eax, [r15+18h]
0x1800053e3  mov     [rbp+57h+wMsgFilterMin], eax
0x1800053e6  cmp     esi, [r15+1Ch]
0x1800053ea  jnz     short loc_1800053F2
0x1800053ec  mov     r14, [r15+10h]
0x1800053f0  jmp     short loc_1800053F5
0x1800053f2  xor     r14d, r14d
0x1800053f5  mov     rax, [r15]
0x1800053f8  xor     edx, edx
0x1800053fa  xor     r9d, r9d; dwMilliseconds
0x1800053fd  mov     [rbp+57h+nPriority], edx
0x180005400  mov     [rbp+57h+var_60], rdx
0x180005404  xor     r8d, r8d; bWaitAll
0x180005407  mov     [rsp+0E0h+bAlertable], edx; bAlertable
0x18000540b  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18000540f  mov     [rbp+57h+var_AC], 0
0x180005416  lea     ecx, [r9+1]; nCount
0x18000541a  mov     [rbp+57h+arg_18], 0
0x180005421  mov     [rbp+57h+Handles], rax
0x180005425  call    cs:__imp_WaitForMultipleObjectsEx
0x18000542c  nop     dword ptr [rax+rax+00h]
0x180005431  mov     edi, eax
0x180005433  cmp     eax, 1
0x180005436  jb      loc_180005673
0x18000543c  mov     r13d, [rbp+57h+var_AC]
0x180005440  mov     rax, r14
0x180005443  neg     rax
0x180005446  sbb     r12d, r12d
0x180005449  and     r12d, 8
0x18000544d  add     r12d, 40h ; '@'
0x180005451  mov     eax, 0Ah
0x180005456  mov     [rsp+0E0h+bAlertable], r12d; dwWakeMask
0x18000545b  cmp     ebx, eax
0x18000545d  lea     rdx, [rbp+57h+Handles]; pHandles
0x180005461  mov     esi, ebx
0x180005463  cmova   esi, eax
0x180005466  xor     r8d, r8d; fWaitAll
0x180005469  mov     r9d, esi; dwMilliseconds
0x18000546c  lea     ecx, [rax-9]; nCount
0x18000546f  call    cs:__imp_MsgWaitForMultipleObjects
0x180005476  nop     dword ptr [rax+rax+00h]
0x18000547b  mov     edi, eax
0x18000547d  cmp     eax, 1
0x180005480  jz      short loc_180005495
0x180005482  cmp     eax, 102h
0x180005487  jnz     loc_1800055A3
0x18000548d  cmp     esi, ebx
0x18000548f  jz      loc_1800055A3
0x180005495  xorps   xmm0, xmm0
0x180005498  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x18000549c  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x1800054a0  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x1800054a4  test    r14, r14
0x1800054a7  jz      short loc_1800054E3
0x1800054a9  mov     edi, [rbp+57h+wMsgFilterMin]
0x1800054ac  jmp     short loc_1800054BE
0x1800054ae  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800054b2  call    cs:__imp_DispatchMessageW
0x1800054b9  nop     dword ptr [rax+rax+00h]
0x1800054be  mov     r9d, edi; wMsgFilterMax
0x1800054c1  mov     [rsp+0E0h+bAlertable], 1; wRemoveMsg
0x1800054c9  mov     r8d, edi; wMsgFilterMin
0x1800054cc  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800054d0  mov     rdx, r14; hWnd
0x1800054d3  call    cs:__imp_PeekMessageW
0x1800054da  nop     dword ptr [rax+rax+00h]
0x1800054df  test    eax, eax
0x1800054e1  jnz     short loc_1800054AE
0x1800054e3  xor     r9d, r9d; wMsgFilterMax
0x1800054e6  mov     [rsp+0E0h+bAlertable], 0; wRemoveMsg
0x1800054ee  xor     r8d, r8d; wMsgFilterMin
0x1800054f1  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800054f5  xor     edx, edx; hWnd
0x1800054f7  call    cs:__imp_PeekMessageW
0x1800054fe  nop     dword ptr [rax+rax+00h]
0x180005503  lea     eax, [rbx-1]
0x180005506  cmp     eax, 0FFFFFFFDh
0x180005509  ja      short loc_180005529
0x18000550b  call    cs:__imp_GetTickCount
0x180005512  nop     dword ptr [rax+rax+00h]
0x180005517  mov     ecx, eax
0x180005519  sub     ecx, [rbp+57h+arg_18]
0x18000551c  cmp     ecx, ebx
0x18000551e  jbe     short loc_180005524
0x180005520  xor     ebx, ebx
0x180005522  jmp     short loc_180005526
0x180005524  sub     ebx, ecx
0x180005526  mov     [rbp+57h+arg_18], eax
0x180005529  test    r13d, r13d
0x18000552c  jnz     short loc_180005576
0x18000552e  call    cs:__imp_GetCurrentThread
0x180005535  nop     dword ptr [rax+rax+00h]
0x18000553a  mov     rcx, rax; hThread
0x18000553d  call    cs:__imp_GetThreadPriority
0x180005544  nop     dword ptr [rax+rax+00h]
0x180005549  mov     [rbp+57h+nPriority], eax
0x18000554c  cmp     eax, 2
0x18000554f  jnb     short loc_180005570
0x180005551  call    cs:__imp_GetCurrentThread
0x180005558  nop     dword ptr [rax+rax+00h]
0x18000555d  mov     rcx, rax; hThread
0x180005560  lea     edx, [r13+2]; nPriority
0x180005564  call    cs:__imp_SetThreadPriority
0x18000556b  nop     dword ptr [rax+rax+00h]
0x180005570  mov     r13d, 1
0x180005576  xor     r9d, r9d; dwMilliseconds
0x180005579  mov     [rsp+0E0h+bAlertable], 0; bAlertable
0x180005581  xor     r8d, r8d; bWaitAll
0x180005584  lea     rdx, [rbp+57h+Handles]; lpHandles
0x180005588  lea     ecx, [r9+1]; nCount
0x18000558c  call    cs:__imp_WaitForMultipleObjectsEx
0x180005593  nop     dword ptr [rax+rax+00h]
0x180005598  mov     edi, eax
0x18000559a  cmp     eax, 1
0x18000559d  jnb     loc_180005451
0x1800055a3  test    r13d, r13d
0x1800055a6  mov     r13, [rbp+57h+arg_0]
0x1800055aa  jz      loc_180005670
0x1800055b0  call    cs:__imp_GetCurrentThread
0x1800055b7  nop     dword ptr [rax+rax+00h]
0x1800055bc  mov     edx, [rbp+57h+nPriority]; nPriority
0x1800055bf  mov     rcx, rax; hThread
0x1800055c2  call    cs:__imp_SetThreadPriority
0x1800055c9  nop     dword ptr [rax+rax+00h]
0x1800055ce  mov     ecx, 8; flags
0x1800055d3  call    cs:__imp_GetQueueStatus
0x1800055da  nop     dword ptr [rax+rax+00h]
0x1800055df  shr     eax, 10h
0x1800055e2  test    al, 8
0x1800055e4  jz      loc_180005670
0x1800055ea  mov     ebx, cs:wMsgFilterMax
0x1800055f0  test    ebx, ebx
0x1800055f2  jnz     short loc_180005613
0x1800055f4  lea     rcx, String; "AMUnblock"
0x1800055fb  call    cs:__imp_RegisterWindowMessageW
0x180005602  nop     dword ptr [rax+rax+00h]
0x180005607  mov     cs:wMsgFilterMax, eax
0x18000560d  mov     ebx, eax
0x18000560f  test    eax, eax
0x180005611  jz      short loc_18000564E
0x180005613  xorps   xmm0, xmm0
0x180005616  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x18000561a  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x18000561e  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x180005622  mov     r9d, ebx; wMsgFilterMax
0x180005625  mov     [rsp+0E0h+bAlertable], 1; wRemoveMsg
0x18000562d  mov     r8d, ebx; wMsgFilterMin
0x180005630  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180005634  or      rdx, 0FFFFFFFFFFFFFFFFh; hWnd
0x180005638  call    cs:__imp_PeekMessageW
0x18000563f  nop     dword ptr [rax+rax+00h]
0x180005644  mov     ebx, cs:wMsgFilterMax
0x18000564a  test    eax, eax
0x18000564c  jnz     short loc_180005622
0x18000564e  call    cs:__imp_GetCurrentThreadId
0x180005655  nop     dword ptr [rax+rax+00h]
0x18000565a  xor     r9d, r9d; lParam
0x18000565d  xor     r8d, r8d; wParam
0x180005660  mov     ecx, eax; idThread
0x180005662  mov     edx, ebx; Msg
0x180005664  call    cs:__imp_PostThreadMessageW
0x18000566b  nop     dword ptr [rax+rax+00h]
0x180005670  mov     esi, [rbp+57h+arg_8]
0x180005673  test    edi, edi
0x180005675  jnz     short loc_1800056C2
0x180005677  mov     [r15+8], esi
0x18000567b  inc     dword ptr [r15+0Ch]
0x18000567f  mov     rax, [r13+28h]
0x180005683  mov     [rbp+57h+Handles], r15
0x180005687  mov     rdi, [rax]
0x18000568a  mov     [rbp+57h+var_48], rdi
0x18000568e  lea     rsi, [rdi+100h]
0x180005695  call    cs:__imp_GetCurrentThreadId
0x18000569c  nop     dword ptr [rax+rax+00h]
0x1800056a1  mov     ecx, [rsi+8]
0x1800056a4  mov     ebx, eax
0x1800056a6  mov     [rbp+57h+arg_8], eax
0x1800056a9  cmp     eax, ecx
0x1800056ab  jz      loc_18000596A
0x1800056b1  mov     eax, [rsi+18h]
0x1800056b4  mov     [rbp+57h+nPriority], eax
0x1800056b7  cmp     ebx, [rsi+1Ch]
0x1800056ba  jnz     short loc_1800056CB
0x1800056bc  mov     r12, [rsi+10h]
0x1800056c0  jmp     short loc_1800056CE
0x1800056c2  xor     r15d, r15d
0x1800056c5  mov     [rbp+57h+var_A0], r15
0x1800056c9  jmp     short loc_18000567F
0x1800056cb  xor     r12d, r12d
0x1800056ce  mov     rax, [rsi]
0x1800056d1  lea     rdx, [rbp+57h+pHandles]; lpHandles
0x1800056d5  xor     ecx, ecx
0x1800056d7  mov     [rbp+57h+pHandles], rax
0x1800056db  xor     r9d, r9d; dwMilliseconds
0x1800056de  mov     [rbp+57h+wMsgFilterMin], ecx
0x1800056e1  mov     [rbp+57h+arg_18], ecx
0x1800056e4  xor     r8d, r8d; bWaitAll
0x1800056e7  mov     [rbp+57h+var_50], rcx
0x1800056eb  mov     [rsp+0E0h+bAlertable], ecx; bAlertable
0x1800056ef  lea     ecx, [r9+1]; nCount
0x1800056f3  call    cs:__imp_WaitForMultipleObjectsEx
0x1800056fa  nop     dword ptr [rax+rax+00h]
0x1800056ff  mov     r14d, eax
0x180005702  cmp     eax, 1
0x180005705  jb      loc_18000595B
0x18000570b  mov     r13d, [rbp+57h+wMsgFilterMin]
0x18000570f  mov     rax, r12
0x180005712  neg     rax
0x180005715  mov     r15d, r13d
0x180005718  sbb     edi, edi
0x18000571a  and     edi, 8
0x18000571d  add     edi, 40h ; '@'
0x180005720  mov     esi, [rbp+57h+arg_10]
0x180005723  lea     rdx, [rbp+57h+pHandles]; pHandles
0x180005727  mov     eax, 0Ah
0x18000572c  mov     [rsp+0E0h+bAlertable], edi; dwWakeMask
0x180005730  cmp     esi, eax
0x180005732  mov     ebx, esi
0x180005734  cmova   ebx, eax
0x180005737  xor     r8d, r8d; fWaitAll
0x18000573a  mov     r9d, ebx; dwMilliseconds
0x18000573d  lea     ecx, [rax-9]; nCount
0x180005740  call    cs:__imp_MsgWaitForMultipleObjects
0x180005747  nop     dword ptr [rax+rax+00h]
0x18000574c  mov     r14d, eax
0x18000574f  cmp     eax, 1
0x180005752  jz      short loc_180005767
0x180005754  cmp     eax, 102h
0x180005759  jnz     loc_18000587C
0x18000575f  cmp     ebx, esi
0x180005761  jz      loc_18000587C
0x180005767  xorps   xmm0, xmm0
0x18000576a  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x18000576e  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x180005772  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x180005776  test    r12, r12
0x180005779  jz      short loc_1800057B5
0x18000577b  mov     ebx, [rbp+57h+nPriority]
0x18000577e  jmp     short loc_180005790
0x180005780  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180005784  call    cs:__imp_DispatchMessageW
0x18000578b  nop     dword ptr [rax+rax+00h]
0x180005790  mov     r9d, ebx; wMsgFilterMax
0x180005793  mov     [rsp+0E0h+bAlertable], 1; wRemoveMsg
0x18000579b  mov     r8d, ebx; wMsgFilterMin
0x18000579e  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800057a2  mov     rdx, r12; hWnd
0x1800057a5  call    cs:__imp_PeekMessageW
0x1800057ac  nop     dword ptr [rax+rax+00h]
0x1800057b1  test    eax, eax
0x1800057b3  jnz     short loc_180005780
0x1800057b5  xor     r9d, r9d; wMsgFilterMax
0x1800057b8  mov     [rsp+0E0h+bAlertable], 0; wRemoveMsg
0x1800057c0  xor     r8d, r8d; wMsgFilterMin
0x1800057c3  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800057c7  xor     edx, edx; hWnd
0x1800057c9  call    cs:__imp_PeekMessageW
0x1800057d0  nop     dword ptr [rax+rax+00h]
0x1800057d5  lea     eax, [rsi-1]
0x1800057d8  cmp     eax, 0FFFFFFFDh
0x1800057db  ja      short loc_180005801
0x1800057dd  call    cs:__imp_GetTickCount
0x1800057e4  nop     dword ptr [rax+rax+00h]
0x1800057e9  mov     ecx, eax
0x1800057eb  sub     ecx, r15d
0x1800057ee  cmp     ecx, esi
0x1800057f0  jbe     short loc_1800057F9
0x1800057f2  xor     ebx, ebx
0x1800057f4  mov     [rbp+57h+arg_10], ebx
0x1800057f7  jmp     short loc_1800057FE
0x1800057f9  sub     esi, ecx
0x1800057fb  mov     [rbp+57h+arg_10], esi
0x1800057fe  mov     r15d, eax
0x180005801  test    r13d, r13d
0x180005804  jnz     short loc_18000584E
0x180005806  call    cs:__imp_GetCurrentThread
  ... truncated ...
```
