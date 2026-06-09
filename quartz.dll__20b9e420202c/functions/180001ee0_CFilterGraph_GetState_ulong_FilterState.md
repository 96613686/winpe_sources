# CFilterGraph::GetState(ulong,_FilterState *)

- ea: `0x180001ee0`
- end: `0x1800026fb`
- name: `?GetState@CFilterGraph@@UEAAJKPEAW4_FilterState@@@Z`
- size: `2075`
- prototype: `__int64 __fastcall(CFilterGraph *__hidden this, unsigned int, enum _FilterState *)`
- caller_count: `3`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001750`
- `0x1800229e8`
- `0x18002a6f8`

## callees

- `0x180001ee0`
- `0x180003808`
- `0x180005358`
- `0x180013200`
- `0x18001d3b0`
- `0x1800301c8`
- `0x1800388a0`
- `0x180065328`
- `0x1800653a0`
- `0x18006d2b0`
- `0x18006d2ec`
- `0x18006d358`
- `0x18006d51c`
- `0x180141ca4`
- `0x18015e010`

## import_xrefs

- `KERNEL32!Sleep` at `0x1800024c8`
- `KERNEL32!Sleep` at `0x1800024c8`
- `KERNEL32!GetCurrentThread` at `0x180002122`
- `KERNEL32!GetCurrentThread` at `0x180002146`
- `KERNEL32!GetCurrentThread` at `0x1800021b8`
- `KERNEL32!GetCurrentThread` at `0x180002122`
- `KERNEL32!GetCurrentThread` at `0x180002146`
- `KERNEL32!GetCurrentThread` at `0x1800021b8`
- `KERNEL32!GetThreadPriority` at `0x180002131`
- `KERNEL32!GetThreadPriority` at `0x180002131`
- `KERNEL32!GetTickCount` at `0x1800020fe`
- `KERNEL32!GetTickCount` at `0x1800020fe`
- `KERNEL32!SetThreadPriority` at `0x18000215a`
- `KERNEL32!SetThreadPriority` at `0x1800021cb`
- `KERNEL32!SetThreadPriority` at `0x18000215a`
- `KERNEL32!SetThreadPriority` at `0x1800021cb`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180001fe8`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180002183`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180001fe8`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180002183`
- `KERNEL32!GetCurrentThreadId` at `0x180001f85`
- `KERNEL32!GetCurrentThreadId` at `0x18000225e`
- `KERNEL32!GetCurrentThreadId` at `0x180001f85`
- `KERNEL32!GetCurrentThreadId` at `0x18000225e`
- `KERNEL32!ReleaseMutex` at `0x180002431`
- `KERNEL32!ReleaseMutex` at `0x1800026b2`
- `KERNEL32!ReleaseMutex` at `0x180002431`
- `KERNEL32!ReleaseMutex` at `0x1800026b2`
- `USER32!GetQueueStatus` at `0x1800021dc`
- `USER32!GetQueueStatus` at `0x1800021dc`
- `USER32!DispatchMessageW` at `0x1800020a5`
- `USER32!DispatchMessageW` at `0x1800020a5`
- `USER32!PeekMessageW` at `0x180002091`
- `USER32!PeekMessageW` at `0x1800020c6`
- `USER32!PeekMessageW` at `0x1800020ea`
- `USER32!PeekMessageW` at `0x180002247`
- `USER32!PeekMessageW` at `0x180002091`
- `USER32!PeekMessageW` at `0x1800020c6`
- `USER32!PeekMessageW` at `0x1800020ea`
- `USER32!PeekMessageW` at `0x180002247`
- `USER32!MsgWaitForMultipleObjects` at `0x180002041`
- `USER32!MsgWaitForMultipleObjects` at `0x180002041`
- `USER32!RegisterWindowMessageW` at `0x180002206`
- `USER32!RegisterWindowMessageW` at `0x180002206`
- `USER32!PostThreadMessageW` at `0x180002275`
- `USER32!PostThreadMessageW` at `0x180002275`
- `WINMM!timeGetTime` at `0x180002456`
- `WINMM!timeGetTime` at `0x1800024d4`
- `WINMM!timeGetTime` at `0x180002456`
- `WINMM!timeGetTime` at `0x1800024d4`

## pseudocode

```c
__int64 __fastcall CFilterGraph::GetState(CFilterGraph *this, __int64 a2, enum _FilterState *a3)
{
  enum _FilterState *v3; // r15
  CFilterGraph *v4; // rsi
  char *v6; // r13
  char *v7; // r12
  int v8; // ebx
  int v9; // edx
  int v10; // ecx
  DWORD CurrentThreadId; // edi
  UINT v12; // r12d
  HWND v13; // r14
  void *v14; // rax
  DWORD v15; // ebx
  int v16; // r15d
  unsigned int v17; // edi
  DWORD v18; // eax
  DWORD v19; // esi
  DWORD v20; // r13d
  DWORD v21; // eax
  DWORD TickCount; // eax
  unsigned int v23; // edx
  unsigned int v24; // eax
  unsigned int v25; // ecx
  HANDLE CurrentThread; // rax
  HANDLE v27; // rax
  bool v28; // zf
  HANDLE v29; // rax
  UINT v30; // r14d
  BOOL v31; // eax
  DWORD v32; // eax
  int v33; // eax
  CFilterGraph *v34; // rcx
  int v35; // ebx
  int v36; // edi
  __int64 **v37; // rbx
  struct IUnknown *v38; // r14
  __int64 *v39; // rax
  int v40; // edx
  int v41; // ecx
  char v42; // al
  void *v43; // rcx
  struct IUnknown *v44; // r14
  DWORD Time; // edi
  DWORD v46; // eax
  DWORD v47; // eax
  __int64 *v48; // rax
  int v49; // edx
  int v50; // ecx
  char v51; // al
  __int64 *v52; // rax
  int v53; // edx
  int v54; // ecx
  char v55; // al
  __int64 *v56; // rax
  int v57; // edx
  int v58; // ecx
  char v59; // r14
  int v60; // edx
  int v61; // ecx
  void *v62; // rcx
  int v63; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v64; // [rsp+44h] [rbp-BCh]
  int v65; // [rsp+48h] [rbp-B8h]
  char *v66; // [rsp+50h] [rbp-B0h] BYREF
  int nPriority; // [rsp+58h] [rbp-A8h]
  struct IUnknown *v68; // [rsp+60h] [rbp-A0h]
  int v69; // [rsp+68h] [rbp-98h]
  int v70; // [rsp+6Ch] [rbp-94h]
  char *v71; // [rsp+78h] [rbp-88h]
  struct tagMSG Msg; // [rsp+80h] [rbp-80h] BYREF
  HANDLE Handles[2]; // [rsp+B0h] [rbp-50h] BYREF
  CFilterGraph *v74; // [rsp+C0h] [rbp-40h]
  enum _FilterState *v75; // [rsp+C8h] [rbp-38h]
  struct tagMSG v76; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v77[112]; // [rsp+100h] [rbp+0h] BYREF

  v75 = a3;
  v64 = a2;
  v3 = a3;
  v74 = this;
  v4 = this;
  v65 = 0;
  if ( !a3 )
    return 2147500035LL;
  v6 = (char *)this - 152;
  v71 = (char *)this - 152;
  if ( (Microsoft_Windows_DirectShow_CoreEnableBits & 0x10) != 0 )
    McTemplateU0pq_EventWriteTransfer(this, a2, (char *)this - 152, (unsigned int)a2);
  else
    v71 = (char *)this - 152;
  v7 = (char *)v4 + 104;
LABEL_7:
  v63 = 0;
  v8 = 1;
  CurrentThreadId = GetCurrentThreadId();
  LODWORD(v66) = CurrentThreadId;
  if ( CurrentThreadId == *((_DWORD *)v4 + 28) )
    goto LABEL_40;
  v12 = *((_DWORD *)v4 + 32);
  if ( CurrentThreadId == *((_DWORD *)v4 + 33) )
    v13 = (HWND)*((_QWORD *)v4 + 15);
  else
    v13 = 0;
  v14 = (void *)*((_QWORD *)v4 + 13);
  v69 = 0;
  nPriority = 0;
  Handles[1] = 0;
  Handles[0] = v14;
  v70 = -1;
  v15 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
  if ( v15 )
  {
    v16 = v69;
    v17 = v70;
    v18 = 64;
    v19 = v69;
    if ( v13 )
      v18 = 72;
    LODWORD(v68) = v18;
    do
    {
      v20 = v17;
      if ( v17 > 0xA )
        v20 = 10;
      v21 = MsgWaitForMultipleObjects(1u, Handles, 0, v20, v18);
      v15 = v21;
      if ( v21 != 1 && (v21 != 258 || v20 == v17) )
        break;
      memset(&Msg, 0, sizeof(Msg));
      if ( v13 && PeekMessageW(&Msg, v13, v12, v12, 1u) )
      {
        do
          DispatchMessageW(&Msg);
        while ( PeekMessageW(&Msg, v13, v12, v12, 1u) );
      }
      PeekMessageW(&Msg, 0, 0, 0, 0);
      if ( v17 - 1 <= 0xFFFFFFFD )
      {
        TickCount = GetTickCount();
        v23 = TickCount - v19;
        v19 = TickCount;
        v24 = v17;
        v25 = v17 - v23;
        v17 = 0;
        if ( v23 <= v24 )
          v17 = v25;
      }
      if ( !v16 )
      {
        CurrentThread = GetCurrentThread();
        nPriority = GetThreadPriority(CurrentThread);
        if ( (unsigned int)nPriority < 2 )
        {
          v27 = GetCurrentThread();
          SetThreadPriority(v27, 2);
        }
        v16 = 1;
      }
      v15 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
      v18 = (unsigned int)v68;
    }
    while ( v15 );
    v4 = v74;
    v28 = v16 == 0;
    v3 = v75;
    v6 = v71;
    CurrentThreadId = (unsigned int)v66;
    if ( !v28 )
    {
      v29 = GetCurrentThread();
      SetThreadPriority(v29, nPriority);
      if ( (GetQueueStatus(8u) & 0x80000) != 0 )
      {
        v30 = wMsgFilterMax;
        if ( wMsgFilterMax || (wMsgFilterMax = RegisterWindowMessageW(L"AMUnblock"), (v30 = wMsgFilterMax) != 0) )
        {
          memset(&v76, 0, sizeof(v76));
          do
          {
            v31 = PeekMessageW(&v76, HWND_MESSAGE|0x2LL, v30, v30, 1u);
            v30 = wMsgFilterMax;
          }
          while ( v31 );
        }
        v32 = GetCurrentThreadId();
        PostThreadMessageW(v32, v30, 0, 0);
      }
    }
  }
  v7 = (char *)v4 + 104;
  if ( !v15 )
  {
    v8 = 1;
    *((_DWORD *)v4 + 28) = CurrentThreadId;
LABEL_40:
    ++*((_DWORD *)v4 + 29);
    goto LABEL_41;
  }
  v8 = 0;
LABEL_41:
  if ( !v8 )
    v7 = 0;
  v33 = *((_DWORD *)v6 + 100);
  v66 = v7;
  if ( *((_DWORD *)v6 + 101) == v33 )
    goto LABEL_47;
  v6[641] = 1;
  Msg.lParam = 10;
  *(_QWORD *)&Msg.time = 0;
  memset(&Msg, 0, 20);
  *(_QWORD *)&Msg.pt.y = v6;
  v35 = CFilterGraph::MergeRootNodes(
          (CFilterGraph *)v6,
          (struct CFilterGraph::CFilGenList *)&Msg,
          (struct CFilterGraph::CFilGenList *)(v6 + 296));
  if ( v35 >= 0 )
  {
    CFilterGraph::ClearRanks(v34, (struct CFilterGraph::CFilGenList *)(v6 + 296));
    v35 = CFilterGraph::NumberNodes(
            (CFilterGraph *)v6,
            (struct CFilterGraph::CFilGenList *)(v6 + 296),
            (struct CFilterGraph::CFilGenList *)&Msg);
    if ( v35 >= 0 )
    {
      CFilterGraph::SortList((CFilterGraph *)v6, (struct CFilterGraph::CFilGenList *)(v6 + 296));
      *((_DWORD *)v6 + 100) = *((_DWORD *)v6 + 101);
      v6[641] = 0;
      CBaseList::~CBaseList((CBaseList *)&Msg);
LABEL_47:
      v36 = 0;
      *v3 = *((enum _FilterState *)v4 + 4);
      v37 = (__int64 **)*((_QWORD *)v4 + 19);
      v68 = 0;
      while ( 1 )
      {
        if ( !v37 )
        {
          if ( v7 )
          {
            v28 = (*((_DWORD *)v7 + 3))-- == 1;
            if ( v28 )
            {
              v43 = *(void **)v7;
              *((_DWORD *)v7 + 2) = 0;
              ReleaseMutex(v43);
            }
          }
          v44 = v68;
          if ( !v68 )
          {
            if ( (Microsoft_Windows_DirectShow_CoreEnableBits & 0x10) != 0 )
              McTemplateU0pqpzd_EventWriteTransfer(v10, v9, (_DWORD)v6, *v3, 0, 0, v36);
            return (unsigned int)v36;
          }
          if ( !v64 )
          {
            if ( (Microsoft_Windows_DirectShow_CoreEnableBits & 0x10) != 0 )
            {
              v56 = (__int64 *)CDisp::CDisp((CDisp *)v77, v68);
              McTemplateU0pqpzd_EventWriteTransfer(v58, v57, (_DWORD)v6, *v3, (char)v44, *v56, 55);
              v59 = 8;
            }
            else
            {
              v59 = v65;
            }
            if ( (v59 & 8) != 0 )
              CDispBasic::~CDispBasic((CDispBasic *)v77);
            return 262711;
          }
          v7 = (char *)v4 + 104;
          Time = timeGetTime();
          CMsgMutex::Lock((CFilterGraph *)((char *)v4 + 104), 0, 0xFFFFFFFF);
          *v3 = *((enum _FilterState *)v4 + 4);
          v35 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, int *))v44->lpVtbl[2].AddRef)(v44, 10, &v63);
          CMsgMutex::Unlock((CFilterGraph *)((char *)v4 + 104));
          if ( v35 < 0 || v35 == 262760 )
            return (unsigned int)v35;
          if ( v63 != *v3 )
          {
            if ( v63 != 1 )
              return 2147500037LL;
            Sleep(0xAu);
          }
          v46 = timeGetTime();
          if ( v64 != -1 )
          {
            v47 = v46 - Time;
            if ( v64 <= v47 )
              v64 = 0;
            else
              v64 -= v47;
          }
          goto LABEL_7;
        }
        v38 = (struct IUnknown *)*v37[2];
        v36 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, int *))v38->lpVtbl[2].AddRef)(v38, 0, &v63);
        if ( v36 < 0 )
        {
          if ( (Microsoft_Windows_DirectShow_CoreEnableBits & 0x10) != 0 )
          {
            v52 = (__int64 *)CDisp::CDisp((CDisp *)v77, v38);
            McTemplateU0pqpzd_EventWriteTransfer(v54, v53, (_DWORD)v6, *((_DWORD *)v4 + 4), (char)v38, *v52, v36);
            v55 = 1;
          }
          else
          {
            v55 = v65;
          }
          if ( (v55 & 1) != 0 )
            goto LABEL_87;
LABEL_88:
          CAutoMsgMutex::~CAutoMsgMutex((CAutoMsgMutex *)&v66);
          return (unsigned int)v36;
        }
        if ( v63 == *v3 )
        {
          if ( !v36 )
            goto LABEL_58;
          if ( v36 != 262711 )
          {
            if ( (Microsoft_Windows_DirectShow_CoreEnableBits & 0x10) != 0 )
            {
              v48 = (__int64 *)CDisp::CDisp((CDisp *)v77, v38);
              McTemplateU0pqpzd_EventWriteTransfer(v50, v49, (_DWORD)v6, *((_DWORD *)v4 + 4), (char)v38, *v48, v36);
              v51 = 4;
            }
            else
            {
              v51 = v65;
            }
            if ( (v51 & 4) == 0 )
              goto LABEL_88;
LABEL_87:
            CDispBasic::~CDispBasic((CDispBasic *)v77);
            goto LABEL_88;
          }
        }
        else if ( v63 != 1 )
        {
          if ( (Microsoft_Windows_DirectShow_CoreEnableBits & 0x10) != 0 )
          {
            v39 = (__int64 *)CDisp::CDisp((CDisp *)v77, v38);
            McTemplateU0pqpzd_EventWriteTransfer(v41, v40, (_DWORD)v6, v63, (char)v38, *v39, 5);
            v42 = 2;
          }
          else
          {
            v42 = v65;
          }
          if ( (v42 & 2) != 0 )
            CDispBasic::~CDispBasic((CDispBasic *)v77);
          CAutoMsgMutex::~CAutoMsgMutex((CAutoMsgMutex *)&v66);
          return 2147500037LL;
        }
        v68 = v38;
LABEL_58:
        v37 = (__int64 **)*v37;
      }
    }
  }
  v6[641] = 0;
  CBaseList::~CBaseList((CBaseList *)&Msg);
  if ( (Microsoft_Windows_DirectShow_CoreEnableBits & 0x10) != 0 )
    McTemplateU0pqpzd_EventWriteTransfer(v61, v60, (_DWORD)v6, *((_DWORD *)v4 + 4), 0, 0, v35);
  if ( v7 )
  {
    v28 = (*((_DWORD *)v7 + 3))-- == 1;
    if ( v28 )
    {
      v62 = *(void **)v7;
      *((_DWORD *)v7 + 2) = 0;
      ReleaseMutex(v62);
    }
  }
  return (unsigned int)v35;
}

```

## disassembly

```asm
0x180001ee0  push    rbp
0x180001ee2  push    rsi
0x180001ee3  push    r14
0x180001ee5  push    r15
0x180001ee7  lea     rbp, [rsp-98h]
0x180001eef  sub     rsp, 198h
0x180001ef6  mov     rax, cs:__security_cookie
0x180001efd  xor     rax, rsp
0x180001f00  mov     [rbp+0B0h+var_40], rax
0x180001f04  xor     r14d, r14d
0x180001f07  mov     [rbp+0B0h+var_E8], r8
0x180001f0b  mov     [rsp+1B0h+var_16C], edx
0x180001f0f  mov     r15, r8
0x180001f12  mov     [rbp+0B0h+var_F0], rcx
0x180001f16  mov     rsi, rcx
0x180001f19  mov     [rsp+1B0h+var_168], r14d
0x180001f1e  test    r8, r8
0x180001f21  jnz     short loc_180001F2D
0x180001f23  mov     eax, 80004003h
0x180001f28  jmp     loc_1800026E0
0x180001f2d  test    cs:Microsoft_Windows_DirectShow_CoreEnableBits, 10h
0x180001f34  mov     [rsp+1B0h+arg_18], rbx
0x180001f3c  mov     [rsp+1B0h+var_20], rdi
0x180001f44  mov     [rsp+1B0h+var_28], r12
0x180001f4c  mov     [rsp+1B0h+var_30], r13
0x180001f54  lea     r13, [rcx-98h]
0x180001f5b  mov     [rsp+1B0h+var_138], r13
0x180001f60  jz      short loc_180001F6F
0x180001f62  mov     r9d, edx
0x180001f65  mov     r8, r13
0x180001f68  call    McTemplateU0pq_EventWriteTransfer
0x180001f6d  jmp     short loc_180001F74
0x180001f6f  mov     [rsp+1B0h+var_138], r13
0x180001f74  lea     r12, [rsi+68h]
0x180001f78  mov     [rsp+1B0h+var_170], 0
0x180001f80  mov     ebx, 1
0x180001f85  call    cs:__imp_GetCurrentThreadId
0x180001f8c  nop     dword ptr [rax+rax+00h]
0x180001f91  mov     edi, eax
0x180001f93  mov     dword ptr [rsp+1B0h+var_160], eax
0x180001f97  mov     eax, [rsi+70h]
0x180001f9a  cmp     edi, eax
0x180001f9c  jz      loc_180002295
0x180001fa2  mov     r12d, [rsi+80h]
0x180001fa9  xor     ecx, ecx
0x180001fab  cmp     edi, [rsi+84h]
0x180001fb1  jnz     short loc_180001FB9
0x180001fb3  mov     r14, [rsi+78h]
0x180001fb7  jmp     short loc_180001FBC
0x180001fb9  mov     r14, rcx
0x180001fbc  mov     rax, [rsi+68h]
0x180001fc0  lea     rdx, [rbp+0B0h+Handles]; lpHandles
0x180001fc4  mov     [rsp+1B0h+var_148], ecx
0x180001fc8  xor     r9d, r9d; dwMilliseconds
0x180001fcb  mov     [rsp+1B0h+nPriority], ecx
0x180001fcf  xor     r8d, r8d; bWaitAll
0x180001fd2  mov     [rbp+0B0h+var_F8], rcx
0x180001fd6  mov     [rsp+1B0h+bAlertable], ecx; bAlertable
0x180001fda  mov     ecx, ebx; nCount
0x180001fdc  mov     [rbp+0B0h+Handles], rax
0x180001fe0  mov     [rsp+1B0h+var_144], 0FFFFFFFFh
0x180001fe8  call    cs:__imp_WaitForMultipleObjectsEx
0x180001fef  nop     dword ptr [rax+rax+00h]
0x180001ff4  mov     ebx, eax
0x180001ff6  cmp     eax, 1
0x180001ff9  jb      loc_180002281
0x180001fff  mov     r15d, [rsp+1B0h+var_148]
0x180002004  test    r14, r14
0x180002007  mov     edi, [rsp+1B0h+var_144]
0x18000200b  mov     eax, 40h ; '@'
0x180002010  mov     ecx, 48h ; 'H'
0x180002015  mov     esi, r15d
0x180002018  cmovnz  eax, ecx
0x18000201b  mov     dword ptr [rsp+1B0h+var_150], eax
0x18000201f  mov     ecx, 0Ah
0x180002024  mov     [rsp+1B0h+bAlertable], eax; dwWakeMask
0x180002028  cmp     edi, 0Ah
0x18000202b  lea     rdx, [rbp+0B0h+Handles]; pHandles
0x18000202f  mov     r13d, edi
0x180002032  cmova   r13d, ecx
0x180002036  xor     r8d, r8d; fWaitAll
0x180002039  mov     r9d, r13d; dwMilliseconds
0x18000203c  mov     ecx, 1; nCount
0x180002041  call    cs:__imp_MsgWaitForMultipleObjects
0x180002048  nop     dword ptr [rax+rax+00h]
0x18000204d  mov     ebx, eax
0x18000204f  cmp     eax, 1
0x180002052  jz      short loc_180002068
0x180002054  cmp     eax, 102h
0x180002059  jnz     loc_18000219E
0x18000205f  cmp     r13d, edi
0x180002062  jz      loc_18000219E
0x180002068  xorps   xmm0, xmm0
0x18000206b  movups  xmmword ptr [rbp+0B0h+Msg.hwnd], xmm0
0x18000206f  movups  xmmword ptr [rbp+0B0h+Msg.wParam], xmm0
0x180002073  movups  xmmword ptr [rbp+0B0h+Msg.time], xmm0
0x180002077  test    r14, r14
0x18000207a  jz      short loc_1800020D6
0x18000207c  mov     r9d, r12d; wMsgFilterMax
0x18000207f  mov     [rsp+1B0h+bAlertable], 1; wRemoveMsg
0x180002087  mov     r8d, r12d; wMsgFilterMin
0x18000208a  lea     rcx, [rbp+0B0h+Msg]; lpMsg
0x18000208e  mov     rdx, r14; hWnd
0x180002091  call    cs:__imp_PeekMessageW
0x180002098  nop     dword ptr [rax+rax+00h]
0x18000209d  test    eax, eax
0x18000209f  jz      short loc_1800020D6
0x1800020a1  lea     rcx, [rbp+0B0h+Msg]; lpMsg
0x1800020a5  call    cs:__imp_DispatchMessageW
0x1800020ac  nop     dword ptr [rax+rax+00h]
0x1800020b1  mov     r9d, r12d; wMsgFilterMax
0x1800020b4  mov     [rsp+1B0h+bAlertable], 1; wRemoveMsg
0x1800020bc  mov     r8d, r12d; wMsgFilterMin
0x1800020bf  lea     rcx, [rbp+0B0h+Msg]; lpMsg
0x1800020c3  mov     rdx, r14; hWnd
0x1800020c6  call    cs:__imp_PeekMessageW
0x1800020cd  nop     dword ptr [rax+rax+00h]
0x1800020d2  test    eax, eax
0x1800020d4  jnz     short loc_1800020A1
0x1800020d6  xor     r9d, r9d; wMsgFilterMax
0x1800020d9  mov     [rsp+1B0h+bAlertable], 0; wRemoveMsg
0x1800020e1  xor     r8d, r8d; wMsgFilterMin
0x1800020e4  lea     rcx, [rbp+0B0h+Msg]; lpMsg
0x1800020e8  xor     edx, edx; hWnd
0x1800020ea  call    cs:__imp_PeekMessageW
0x1800020f1  nop     dword ptr [rax+rax+00h]
0x1800020f6  lea     eax, [rdi-1]
0x1800020f9  cmp     eax, 0FFFFFFFDh
0x1800020fc  ja      short loc_18000211D
0x1800020fe  call    cs:__imp_GetTickCount
0x180002105  nop     dword ptr [rax+rax+00h]
0x18000210a  mov     ecx, edi
0x18000210c  mov     edx, eax
0x18000210e  sub     edx, esi
0x180002110  mov     esi, eax
0x180002112  mov     eax, edi
0x180002114  sub     ecx, edx
0x180002116  xor     edi, edi
0x180002118  cmp     edx, eax
0x18000211a  cmovbe  edi, ecx
0x18000211d  test    r15d, r15d
0x180002120  jnz     short loc_18000216C
0x180002122  call    cs:__imp_GetCurrentThread
0x180002129  nop     dword ptr [rax+rax+00h]
0x18000212e  mov     rcx, rax; hThread
0x180002131  call    cs:__imp_GetThreadPriority
0x180002138  nop     dword ptr [rax+rax+00h]
0x18000213d  mov     [rsp+1B0h+nPriority], eax
0x180002141  cmp     eax, 2
0x180002144  jnb     short loc_180002166
0x180002146  call    cs:__imp_GetCurrentThread
0x18000214d  nop     dword ptr [rax+rax+00h]
0x180002152  mov     rcx, rax; hThread
0x180002155  mov     edx, 2; nPriority
0x18000215a  call    cs:__imp_SetThreadPriority
0x180002161  nop     dword ptr [rax+rax+00h]
0x180002166  mov     r15d, 1
0x18000216c  xor     r9d, r9d; dwMilliseconds
0x18000216f  mov     [rsp+1B0h+bAlertable], 0; bAlertable
0x180002177  xor     r8d, r8d; bWaitAll
0x18000217a  lea     rdx, [rbp+0B0h+Handles]; lpHandles
0x18000217e  mov     ecx, 1; nCount
0x180002183  call    cs:__imp_WaitForMultipleObjectsEx
0x18000218a  nop     dword ptr [rax+rax+00h]
0x18000218f  mov     ebx, eax
0x180002191  cmp     eax, 1
0x180002194  mov     eax, dword ptr [rsp+1B0h+var_150]
0x180002198  jnb     loc_18000201F
0x18000219e  mov     rsi, [rbp+0B0h+var_F0]
0x1800021a2  test    r15d, r15d
0x1800021a5  mov     r15, [rbp+0B0h+var_E8]
0x1800021a9  mov     r13, [rsp+1B0h+var_138]
0x1800021ae  mov     edi, dword ptr [rsp+1B0h+var_160]
0x1800021b2  jz      loc_180002281
0x1800021b8  call    cs:__imp_GetCurrentThread
0x1800021bf  nop     dword ptr [rax+rax+00h]
0x1800021c4  mov     edx, [rsp+1B0h+nPriority]; nPriority
0x1800021c8  mov     rcx, rax; hThread
0x1800021cb  call    cs:__imp_SetThreadPriority
0x1800021d2  nop     dword ptr [rax+rax+00h]
0x1800021d7  mov     ecx, 8; flags
0x1800021dc  call    cs:__imp_GetQueueStatus
0x1800021e3  nop     dword ptr [rax+rax+00h]
0x1800021e8  shr     eax, 10h
0x1800021eb  test    al, 8
0x1800021ed  jz      loc_180002281
0x1800021f3  mov     r14d, cs:wMsgFilterMax
0x1800021fa  test    r14d, r14d
0x1800021fd  jnz     short loc_18000221F
0x1800021ff  lea     rcx, String; "AMUnblock"
0x180002206  call    cs:__imp_RegisterWindowMessageW
0x18000220d  nop     dword ptr [rax+rax+00h]
0x180002212  mov     cs:wMsgFilterMax, eax
0x180002218  mov     r14d, eax
0x18000221b  test    eax, eax
0x18000221d  jz      short loc_18000225E
0x18000221f  xorps   xmm0, xmm0
0x180002222  movups  xmmword ptr [rbp+0B0h+var_E0.hwnd], xmm0
0x180002226  movups  xmmword ptr [rbp+0B0h+var_E0.wParam], xmm0
0x18000222a  movups  xmmword ptr [rbp+0B0h+var_E0.time], xmm0
0x18000222e  mov     r9d, r14d; wMsgFilterMax
0x180002231  mov     [rsp+1B0h+bAlertable], 1; wRemoveMsg
0x180002239  mov     r8d, r14d; wMsgFilterMin
0x18000223c  lea     rcx, [rbp+0B0h+var_E0]; lpMsg
0x180002240  mov     rdx, 0FFFFFFFFFFFFFFFFh; hWnd
0x180002247  call    cs:__imp_PeekMessageW
0x18000224e  nop     dword ptr [rax+rax+00h]
0x180002253  mov     r14d, cs:wMsgFilterMax
0x18000225a  test    eax, eax
0x18000225c  jnz     short loc_18000222E
0x18000225e  call    cs:__imp_GetCurrentThreadId
0x180002265  nop     dword ptr [rax+rax+00h]
0x18000226a  xor     r9d, r9d; lParam
0x18000226d  xor     r8d, r8d; wParam
0x180002270  mov     ecx, eax; idThread
0x180002272  mov     edx, r14d; Msg
0x180002275  call    cs:__imp_PostThreadMessageW
0x18000227c  nop     dword ptr [rax+rax+00h]
0x180002281  lea     r12, [rsi+68h]
0x180002285  test    ebx, ebx
0x180002287  jnz     loc_1800023F3
0x18000228d  mov     ebx, 1
0x180002292  mov     [rsi+70h], edi
0x180002295  inc     dword ptr [rsi+74h]
0x180002298  xor     eax, eax
0x18000229a  test    ebx, ebx
0x18000229c  cmovz   r12, rax
0x1800022a0  mov     eax, [r13+190h]
0x1800022a7  mov     [rsp+1B0h+var_160], r12
0x1800022ac  cmp     [r13+194h], eax
0x1800022b3  jz      loc_180002358
0x1800022b9  xorps   xmm0, xmm0
0x1800022bc  mov     byte ptr [r13+281h], 1
0x1800022c4  lea     r8, [r13+128h]; struct CFilterGraph::CFilGenList *
0x1800022cb  mov     dword ptr [rbp+0B0h+Msg.wParam], 0
0x1800022d2  lea     rdx, [rbp+0B0h+Msg]; struct CFilterGraph::CFilGenList *
0x1800022d6  mov     [rbp+0B0h+Msg.lParam], 0Ah
0x1800022de  mov     rcx, r13; this
0x1800022e1  mov     qword ptr [rbp+0B0h+Msg.time], 0
0x1800022e9  movdqu  xmmword ptr [rbp+0B0h+Msg.hwnd], xmm0
0x1800022ee  mov     qword ptr [rbp+0B0h+Msg.pt.y], r13
0x1800022f2  call    ?MergeRootNodes@CFilterGraph@@AEAAJAEAVCFilGenList@1@0@Z; CFilterGraph::MergeRootNodes(CFilterGraph::CFilGenList &,CFilterGraph::CFilGenList &)
0x1800022f7  mov     ebx, eax
0x1800022f9  test    eax, eax
0x1800022fb  js      loc_18000265C
0x180002301  lea     rdx, [r13+128h]; struct CFilterGraph::CFilGenList *
0x180002308  call    ?ClearRanks@CFilterGraph@@AEAAXAEAVCFilGenList@1@@Z; CFilterGraph::ClearRanks(CFilterGraph::CFilGenList &)
0x18000230d  lea     rdx, [r13+128h]; struct CFilterGraph::CFilGenList *
0x180002314  mov     rcx, r13; this
0x180002317  lea     r8, [rbp+0B0h+Msg]; struct CFilterGraph::CFilGenList *
0x18000231b  call    ?NumberNodes@CFilterGraph@@AEAAJAEAVCFilGenList@1@0@Z; CFilterGraph::NumberNodes(CFilterGraph::CFilGenList &,CFilterGraph::CFilGenList &)
0x180002320  mov     ebx, eax
0x180002322  test    eax, eax
0x180002324  js      loc_18000265C
0x18000232a  lea     rdx, [r13+128h]; struct CFilterGraph::CFilGenList *
0x180002331  mov     rcx, r13; this
0x180002334  call    ?SortList@CFilterGraph@@AEAAXAEAVCFilGenList@1@@Z; CFilterGraph::SortList(CFilterGraph::CFilGenList &)
0x180002339  mov     eax, [r13+194h]
0x180002340  lea     rcx, [rbp+0B0h+Msg]; this
0x180002344  mov     [r13+190h], eax
0x18000234b  mov     byte ptr [r13+281h], 0
0x180002353  call    ??1CBaseList@@QEAA@XZ; CBaseList::~CBaseList(void)
0x180002358  mov     eax, [rsi+10h]
0x18000235b  xor     edi, edi
0x18000235d  xor     r14d, r14d
0x180002360  mov     [r15], eax
0x180002363  mov     rbx, [rsi+98h]
0x18000236a  mov     [rsp+1B0h+var_150], r14
0x18000236f  nop
0x180002370  test    rbx, rbx
0x180002373  jz      loc_180002417
0x180002379  mov     rax, [rbx+10h]
0x18000237d  lea     r8, [rsp+1B0h+var_170]
0x180002382  xor     edx, edx
0x180002384  mov     r14, [rax]
0x180002387  mov     rcx, r14
0x18000238a  mov     rax, [r14]
0x18000238d  mov     rax, [rax+38h]
0x180002391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002396  mov     edi, eax
0x180002398  test    eax, eax
0x18000239a  js      loc_180002578
0x1800023a0  mov     eax, [rsp+1B0h+var_170]
0x1800023a4  cmp     eax, [r15]
0x1800023a7  jz      short loc_1800023FA
0x1800023a9  cmp     eax, 1
0x1800023ac  jz      short loc_18000240A
0x1800023ae  test    cs:Microsoft_Windows_DirectShow_CoreEnableBits, 10h
0x1800023b5  jz      loc_180002510
0x1800023bb  mov     rdx, r14; struct IUnknown *
0x1800023be  lea     rcx, [rbp+0B0h+var_B0]; this
0x1800023c2  call    ??0CDisp@@QEAA@PEAUIUnknown@@@Z; CDisp::CDisp(IUnknown *)
0x1800023c7  mov     r9d, [rsp+1B0h+var_170]
0x1800023cc  mov     r8, r13
0x1800023cf  mov     [rsp+1B0h+var_180], 80004005h
0x1800023d7  mov     rax, [rax]
0x1800023da  mov     [rsp+1B0h+var_188], rax
0x1800023df  mov     qword ptr [rsp+1B0h+bAlertable], r14
0x1800023e4  call    McTemplateU0pqpzd_EventWriteTransfer
0x1800023e9  mov     eax, 2
  ... truncated ...
```
