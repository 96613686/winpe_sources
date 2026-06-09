# CFilterGraph::Stop(void)

- ea: `0x1800032f0`
- end: `0x1800037ff`
- name: `?Stop@CFilterGraph@@UEAAJXZ`
- size: `1295`
- prototype: `__int64 __fastcall(CFilterGraph *__hidden this)`
- caller_count: `8`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002710`
- `0x180005390`
- `0x18001f5c0`
- `0x1800229e8`
- `0x18006f65c`
- `0x180070eec`
- `0x180071554`
- `0x180071a3c`

## callees

- `0x1800032f0`
- `0x180005358`
- `0x180007a2c`
- `0x18001fbcc`
- `0x18002af88`
- `0x18002c054`
- `0x1800301c8`
- `0x1800388a0`
- `0x180065048`
- `0x18006a060`
- `0x180141ca4`
- `0x18015e010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x1800034cb`
- `KERNEL32!GetCurrentThread` at `0x1800034ef`
- `KERNEL32!GetCurrentThread` at `0x180003555`
- `KERNEL32!GetCurrentThread` at `0x1800034cb`
- `KERNEL32!GetCurrentThread` at `0x1800034ef`
- `KERNEL32!GetCurrentThread` at `0x180003555`
- `KERNEL32!GetThreadPriority` at `0x1800034da`
- `KERNEL32!GetThreadPriority` at `0x1800034da`
- `KERNEL32!GetTickCount` at `0x1800034a0`
- `KERNEL32!GetTickCount` at `0x1800034a0`
- `KERNEL32!SetThreadPriority` at `0x180003501`
- `KERNEL32!SetThreadPriority` at `0x180003568`
- `KERNEL32!SetThreadPriority` at `0x180003501`
- `KERNEL32!SetThreadPriority` at `0x180003568`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1800033aa`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180003529`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1800033aa`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180003529`
- `KERNEL32!GetCurrentThreadId` at `0x180003342`
- `KERNEL32!GetCurrentThreadId` at `0x1800035f7`
- `KERNEL32!GetCurrentThreadId` at `0x180003342`
- `KERNEL32!GetCurrentThreadId` at `0x1800035f7`
- `KERNEL32!ReleaseMutex` at `0x180003680`
- `KERNEL32!ReleaseMutex` at `0x180003680`
- `USER32!GetQueueStatus` at `0x180003579`
- `USER32!GetQueueStatus` at `0x180003579`
- `USER32!DispatchMessageW` at `0x180003444`
- `USER32!DispatchMessageW` at `0x180003444`
- `USER32!PeekMessageW` at `0x180003466`
- `USER32!PeekMessageW` at `0x18000348b`
- `USER32!PeekMessageW` at `0x1800035e1`
- `USER32!PeekMessageW` at `0x180003466`
- `USER32!PeekMessageW` at `0x18000348b`
- `USER32!PeekMessageW` at `0x1800035e1`
- `USER32!MsgWaitForMultipleObjects` at `0x1800033fa`
- `USER32!MsgWaitForMultipleObjects` at `0x1800033fa`
- `USER32!RegisterWindowMessageW` at `0x1800035a1`
- `USER32!RegisterWindowMessageW` at `0x1800035a1`
- `USER32!PostThreadMessageW` at `0x18000360d`
- `USER32!PostThreadMessageW` at `0x18000360d`

## pseudocode

```c
__int64 __fastcall CFilterGraph::Stop(CFilterGraph *this)
{
  HANDLE *v2; // rdi
  DWORD CurrentThreadId; // eax
  int v4; // ecx
  DWORD v5; // r15d
  HWND v6; // rbx
  unsigned int v7; // r13d
  DWORD v8; // r14d
  int v9; // edi
  DWORD v10; // r15d
  DWORD v11; // eax
  DWORD TickCount; // eax
  unsigned int v13; // edx
  unsigned int v14; // ecx
  unsigned int v15; // eax
  HANDLE CurrentThread; // rax
  HANDLE v17; // rax
  bool v18; // zf
  HANDLE v19; // rax
  UINT v20; // ebx
  BOOL v21; // eax
  DWORD v22; // eax
  int v23; // eax
  CMsgMutex *v24; // r14
  void *v25; // rcx
  CDistributorManager *v27; // rcx
  int v28; // eax
  int v29; // ebx
  struct IUnknown *v30; // r12
  CReconnectList *v31; // rax
  __int64 v32; // r15
  struct IUnknown *v33; // rdi
  int v34; // eax
  char v35; // di
  __int64 v36; // rcx
  DWORD v37; // [rsp+30h] [rbp-D0h]
  DWORD v38; // [rsp+34h] [rbp-CCh]
  unsigned int nPriority; // [rsp+38h] [rbp-C8h]
  UINT wMsgFilterMin; // [rsp+40h] [rbp-C0h]
  HANDLE Handles[3]; // [rsp+48h] [rbp-B8h] BYREF
  MSG Msg; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v43[112]; // [rsp+90h] [rbp-70h] BYREF

  if ( (Microsoft_Windows_DirectShow_CoreEnableBits & 0x10) != 0 )
    McTemplateU0p_EventWriteTransfer(this, StopStartEvent, (char *)this - 152);
  v2 = (HANDLE *)((char *)this + 104);
  CurrentThreadId = GetCurrentThreadId();
  v4 = *((_DWORD *)this + 28);
  v5 = CurrentThreadId;
  v37 = CurrentThreadId;
  if ( CurrentThreadId == v4 )
    goto LABEL_36;
  wMsgFilterMin = *((_DWORD *)this + 32);
  if ( CurrentThreadId == *((_DWORD *)this + 33) )
    v6 = (HWND)*((_QWORD *)this + 15);
  else
    v6 = 0;
  v38 = 0;
  v7 = -1;
  nPriority = 0;
  Handles[0] = *v2;
  Handles[1] = 0;
  v8 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
  if ( v8 )
  {
    v9 = 0;
    do
    {
      v10 = v7;
      if ( v7 > 0xA )
        v10 = 10;
      v11 = MsgWaitForMultipleObjects(1u, Handles, 0, v10, v6 != 0 ? 72 : 64);
      v8 = v11;
      if ( v11 != 1 && (v11 != 258 || v10 == v7) )
        break;
      memset(&Msg, 0, sizeof(Msg));
      if ( v6 )
      {
        while ( PeekMessageW(&Msg, v6, wMsgFilterMin, wMsgFilterMin, 1u) )
          DispatchMessageW(&Msg);
      }
      PeekMessageW(&Msg, 0, 0, 0, 0);
      if ( v7 - 1 <= 0xFFFFFFFD )
      {
        TickCount = GetTickCount();
        v13 = TickCount - v38;
        v14 = v7 - (TickCount - v38);
        v38 = TickCount;
        v15 = v7;
        v7 = 0;
        if ( v13 <= v15 )
          v7 = v14;
      }
      if ( !v9 )
      {
        CurrentThread = GetCurrentThread();
        nPriority = GetThreadPriority(CurrentThread);
        if ( nPriority < 2 )
        {
          v17 = GetCurrentThread();
          SetThreadPriority(v17, 2);
        }
        v9 = 1;
      }
      v8 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
    }
    while ( v8 );
    v18 = v9 == 0;
    v2 = (HANDLE *)((char *)this + 104);
    if ( !v18 )
    {
      v19 = GetCurrentThread();
      SetThreadPriority(v19, nPriority);
      if ( (GetQueueStatus(8u) & 0x80000) != 0 )
      {
        v20 = wMsgFilterMax;
        if ( wMsgFilterMax || (wMsgFilterMax = RegisterWindowMessageW(L"AMUnblock"), (v20 = wMsgFilterMax) != 0) )
        {
          memset(&Msg, 0, sizeof(Msg));
          do
          {
            v21 = PeekMessageW(&Msg, HWND_MESSAGE|0x2LL, v20, v20, 1u);
            v20 = wMsgFilterMax;
          }
          while ( v21 );
        }
        v22 = GetCurrentThreadId();
        PostThreadMessageW(v22, v20, 0, 0);
      }
    }
    v5 = v37;
  }
  if ( !v8 )
  {
    *((_DWORD *)this + 28) = v5;
LABEL_36:
    ++*((_DWORD *)this + 29);
    v23 = 1;
    goto LABEL_37;
  }
  v23 = 0;
LABEL_37:
  v24 = (CMsgMutex *)((unsigned __int64)v2 & -(__int64)(v23 != 0));
  if ( *((_DWORD *)this + 4) )
  {
    CFGControl::Stop(*((CFGControl **)this + 12));
    v27 = (CDistributorManager *)*((_QWORD *)this + 49);
    if ( v27 )
      CDistributorManager::Stop(v27);
    v28 = CFilterGraph::UpstreamOrder((CFilterGraph *)((char *)this - 152));
    v29 = 0;
    v30 = 0;
    if ( (unsigned int)(v28 + 2147467263) > 1 )
      v29 = v28;
    v31 = (CFilterGraph *)((char *)this + 232);
    ++*((_DWORD *)this + 58);
    v32 = *((_QWORD *)this + 18);
    if ( v32 )
    {
      do
      {
        v33 = **(struct IUnknown ***)(v32 + 16);
        v34 = ((__int64 (__fastcall *)(struct IUnknown *))v33->lpVtbl[1].AddRef)(v33);
        if ( v34 >= 0 )
          v33 = v30;
        v30 = v33;
        if ( (!v29 || v34 < 0 && v29 >= 0) && (unsigned int)(v34 + 2147467263) > 1
          || (unsigned int)(v29 + 2147467263) <= 1 )
        {
          v29 = v34;
        }
        v32 = *(_QWORD *)(v32 + 8);
      }
      while ( v32 );
      v31 = (CFilterGraph *)((char *)this + 232);
    }
    *((_QWORD *)this + 34) = 0;
    *((_QWORD *)this + 33) = 0;
    *(_WORD *)((char *)this + 585) = 0;
    *((_QWORD *)this + 74) = 0;
    *((_QWORD *)this + 75) = 0;
    *((_DWORD *)this + 4) = 0;
    CReconnectList::Passive(v31);
    if ( (Microsoft_Windows_DirectShow_CoreEnableBits & 0x10) != 0 )
    {
      if ( v30 )
      {
        v35 = 1;
        v36 = *(_QWORD *)CDisp::CDisp((CDisp *)v43, v30);
      }
      else
      {
        v36 = 0;
        v35 = 0;
      }
      McTemplateU0ppzd_EventWriteTransfer(v36, (unsigned int)StopStopEvent, (_DWORD)this - 152, (_DWORD)v30, v36, v29);
    }
    else
    {
      v35 = 0;
    }
    if ( (v35 & 1) != 0 )
      CDispBasic::~CDispBasic((CDispBasic *)v43);
    if ( v24 )
      CMsgMutex::Unlock(v24);
    return (unsigned int)v29;
  }
  else
  {
    if ( (Microsoft_Windows_DirectShow_CoreEnableBits & 0x10) != 0 )
      McTemplateU0ppzd_EventWriteTransfer(v4, (unsigned int)StopStopEvent, (_DWORD)this - 152, 0, 0, 0);
    if ( v24 )
    {
      v18 = (*((_DWORD *)v24 + 3))-- == 1;
      if ( v18 )
      {
        v25 = *(void **)v24;
        *((_DWORD *)v24 + 2) = 0;
        ReleaseMutex(v25);
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800032f0  push    rbp
0x1800032f2  push    rbx
0x1800032f3  push    rsi
0x1800032f4  push    rdi
0x1800032f5  push    r12
0x1800032f7  push    r13
0x1800032f9  push    r14
0x1800032fb  push    r15
0x1800032fd  lea     rbp, [rsp-18h]
0x180003302  sub     rsp, 118h
0x180003309  mov     rax, cs:__security_cookie
0x180003310  xor     rax, rsp
0x180003313  mov     [rbp+50h+var_50], rax
0x180003317  xor     r12d, r12d
0x18000331a  mov     rsi, rcx
0x18000331d  test    cs:Microsoft_Windows_DirectShow_CoreEnableBits, 10h
0x180003324  mov     [rsp+150h+var_114], r12d
0x180003329  jz      short loc_18000333E
0x18000332b  lea     r8, [rcx-98h]
0x180003332  lea     rdx, StopStartEvent
0x180003339  call    McTemplateU0p_EventWriteTransfer
0x18000333e  lea     rdi, [rsi+68h]
0x180003342  call    cs:__imp_GetCurrentThreadId
0x180003349  nop     dword ptr [rax+rax+00h]
0x18000334e  mov     ecx, [rdi+8]
0x180003351  mov     r15d, eax
0x180003354  mov     [rsp+150h+var_120], eax
0x180003358  cmp     eax, ecx
0x18000335a  jz      loc_180003627
0x180003360  mov     eax, [rdi+18h]
0x180003363  mov     [rsp+150h+wMsgFilterMin], eax
0x180003367  cmp     r15d, [rdi+1Ch]
0x18000336b  jnz     short loc_180003373
0x18000336d  mov     rbx, [rdi+10h]
0x180003371  jmp     short loc_180003376
0x180003373  mov     rbx, r12
0x180003376  mov     rax, [rdi]
0x180003379  lea     rdx, [rsp+150h+Handles]; lpHandles
0x18000337e  xor     r9d, r9d; dwMilliseconds
0x180003381  mov     [rsp+150h+var_10C], r12d
0x180003386  xor     r8d, r8d; bWaitAll
0x180003389  mov     [rsp+150h+var_11C], r12d
0x18000338e  or      r13d, 0FFFFFFFFh
0x180003392  mov     [rsp+150h+nPriority], r12d
0x180003397  mov     [rsp+150h+Handles], rax
0x18000339c  lea     ecx, [r9+1]; nCount
0x1800033a0  mov     [rsp+150h+var_100], r12
0x1800033a5  mov     [rsp+150h+bAlertable], r12d; bAlertable
0x1800033aa  call    cs:__imp_WaitForMultipleObjectsEx
0x1800033b1  nop     dword ptr [rax+rax+00h]
0x1800033b6  mov     r14d, eax
0x1800033b9  cmp     eax, 1
0x1800033bc  jb      loc_18000361E
0x1800033c2  mov     edi, [rsp+150h+var_10C]
0x1800033c6  mov     rax, rbx
0x1800033c9  neg     rax
0x1800033cc  mov     eax, 0Ah
0x1800033d1  sbb     r12d, r12d
0x1800033d4  and     r12d, 8
0x1800033d8  add     r12d, 40h ; '@'
0x1800033dc  cmp     r13d, eax
0x1800033df  mov     [rsp+150h+bAlertable], r12d; dwWakeMask
0x1800033e4  mov     r15d, r13d
0x1800033e7  lea     rdx, [rsp+150h+Handles]; pHandles
0x1800033ec  cmova   r15d, eax
0x1800033f0  xor     r8d, r8d; fWaitAll
0x1800033f3  mov     r9d, r15d; dwMilliseconds
0x1800033f6  lea     ecx, [r8+1]; nCount
0x1800033fa  call    cs:__imp_MsgWaitForMultipleObjects
0x180003401  nop     dword ptr [rax+rax+00h]
0x180003406  mov     r14d, eax
0x180003409  cmp     eax, 1
0x18000340c  jz      short loc_180003422
0x18000340e  cmp     eax, 102h
0x180003413  jnz     loc_180003546
0x180003419  cmp     r15d, r13d
0x18000341c  jz      loc_180003546
0x180003422  xorps   xmm0, xmm0
0x180003425  movups  xmmword ptr [rsp+150h+Msg.hwnd], xmm0
0x18000342a  movups  xmmword ptr [rsp+150h+Msg.wParam], xmm0
0x18000342f  movups  xmmword ptr [rbp+50h+Msg.time], xmm0
0x180003433  test    rbx, rbx
0x180003436  jz      short loc_180003476
0x180003438  mov     r14d, [rsp+150h+wMsgFilterMin]
0x18000343d  jmp     short loc_180003450
0x18000343f  lea     rcx, [rsp+150h+Msg]; lpMsg
0x180003444  call    cs:__imp_DispatchMessageW
0x18000344b  nop     dword ptr [rax+rax+00h]
0x180003450  mov     r9d, r14d; wMsgFilterMax
0x180003453  mov     [rsp+150h+bAlertable], 1; wRemoveMsg
0x18000345b  mov     r8d, r14d; wMsgFilterMin
0x18000345e  lea     rcx, [rsp+150h+Msg]; lpMsg
0x180003463  mov     rdx, rbx; hWnd
0x180003466  call    cs:__imp_PeekMessageW
0x18000346d  nop     dword ptr [rax+rax+00h]
0x180003472  test    eax, eax
0x180003474  jnz     short loc_18000343F
0x180003476  xor     r9d, r9d; wMsgFilterMax
0x180003479  mov     [rsp+150h+bAlertable], 0; wRemoveMsg
0x180003481  xor     r8d, r8d; wMsgFilterMin
0x180003484  lea     rcx, [rsp+150h+Msg]; lpMsg
0x180003489  xor     edx, edx; hWnd
0x18000348b  call    cs:__imp_PeekMessageW
0x180003492  nop     dword ptr [rax+rax+00h]
0x180003497  lea     eax, [r13-1]
0x18000349b  cmp     eax, 0FFFFFFFDh
0x18000349e  ja      short loc_1800034C7
0x1800034a0  call    cs:__imp_GetTickCount
0x1800034a7  nop     dword ptr [rax+rax+00h]
0x1800034ac  mov     ecx, r13d
0x1800034af  mov     edx, eax
0x1800034b1  sub     edx, [rsp+150h+var_11C]
0x1800034b5  sub     ecx, edx
0x1800034b7  mov     [rsp+150h+var_11C], eax
0x1800034bb  mov     eax, r13d
0x1800034be  xor     r13d, r13d
0x1800034c1  cmp     edx, eax
0x1800034c3  cmovbe  r13d, ecx
0x1800034c7  test    edi, edi
0x1800034c9  jnz     short loc_180003512
0x1800034cb  call    cs:__imp_GetCurrentThread
0x1800034d2  nop     dword ptr [rax+rax+00h]
0x1800034d7  mov     rcx, rax; hThread
0x1800034da  call    cs:__imp_GetThreadPriority
0x1800034e1  nop     dword ptr [rax+rax+00h]
0x1800034e6  mov     [rsp+150h+nPriority], eax
0x1800034ea  cmp     eax, 2
0x1800034ed  jnb     short loc_18000350D
0x1800034ef  call    cs:__imp_GetCurrentThread
0x1800034f6  nop     dword ptr [rax+rax+00h]
0x1800034fb  mov     rcx, rax; hThread
0x1800034fe  lea     edx, [rdi+2]; nPriority
0x180003501  call    cs:__imp_SetThreadPriority
0x180003508  nop     dword ptr [rax+rax+00h]
0x18000350d  mov     edi, 1
0x180003512  xor     r9d, r9d; dwMilliseconds
0x180003515  mov     [rsp+150h+bAlertable], 0; bAlertable
0x18000351d  xor     r8d, r8d; bWaitAll
0x180003520  lea     rdx, [rsp+150h+Handles]; lpHandles
0x180003525  lea     ecx, [r9+1]; nCount
0x180003529  call    cs:__imp_WaitForMultipleObjectsEx
0x180003530  nop     dword ptr [rax+rax+00h]
0x180003535  mov     r14d, eax
0x180003538  cmp     eax, 1
0x18000353b  mov     eax, 0Ah
0x180003540  jnb     loc_1800033DC
0x180003546  xor     r12d, r12d
0x180003549  test    edi, edi
0x18000354b  lea     rdi, [rsi+68h]
0x18000354f  jz      loc_180003619
0x180003555  call    cs:__imp_GetCurrentThread
0x18000355c  nop     dword ptr [rax+rax+00h]
0x180003561  mov     edx, [rsp+150h+nPriority]; nPriority
0x180003565  mov     rcx, rax; hThread
0x180003568  call    cs:__imp_SetThreadPriority
0x18000356f  nop     dword ptr [rax+rax+00h]
0x180003574  lea     ecx, [r12+8]; flags
0x180003579  call    cs:__imp_GetQueueStatus
0x180003580  nop     dword ptr [rax+rax+00h]
0x180003585  shr     eax, 10h
0x180003588  test    al, 8
0x18000358a  jz      loc_180003619
0x180003590  mov     ebx, cs:wMsgFilterMax
0x180003596  test    ebx, ebx
0x180003598  jnz     short loc_1800035B9
0x18000359a  lea     rcx, String; "AMUnblock"
0x1800035a1  call    cs:__imp_RegisterWindowMessageW
0x1800035a8  nop     dword ptr [rax+rax+00h]
0x1800035ad  mov     cs:wMsgFilterMax, eax
0x1800035b3  mov     ebx, eax
0x1800035b5  test    eax, eax
0x1800035b7  jz      short loc_1800035F7
0x1800035b9  xorps   xmm0, xmm0
0x1800035bc  movups  xmmword ptr [rsp+150h+Msg.hwnd], xmm0
0x1800035c1  movups  xmmword ptr [rsp+150h+Msg.wParam], xmm0
0x1800035c6  movups  xmmword ptr [rbp+50h+Msg.time], xmm0
0x1800035ca  mov     r9d, ebx; wMsgFilterMax
0x1800035cd  mov     [rsp+150h+bAlertable], 1; wRemoveMsg
0x1800035d5  mov     r8d, ebx; wMsgFilterMin
0x1800035d8  lea     rcx, [rsp+150h+Msg]; lpMsg
0x1800035dd  or      rdx, 0FFFFFFFFFFFFFFFFh; hWnd
0x1800035e1  call    cs:__imp_PeekMessageW
0x1800035e8  nop     dword ptr [rax+rax+00h]
0x1800035ed  mov     ebx, cs:wMsgFilterMax
0x1800035f3  test    eax, eax
0x1800035f5  jnz     short loc_1800035CA
0x1800035f7  call    cs:__imp_GetCurrentThreadId
0x1800035fe  nop     dword ptr [rax+rax+00h]
0x180003603  xor     r9d, r9d; lParam
0x180003606  xor     r8d, r8d; wParam
0x180003609  mov     ecx, eax; idThread
0x18000360b  mov     edx, ebx; Msg
0x18000360d  call    cs:__imp_PostThreadMessageW
0x180003614  nop     dword ptr [rax+rax+00h]
0x180003619  mov     r15d, [rsp+150h+var_120]
0x18000361e  test    r14d, r14d
0x180003621  jnz     short loc_180003693
0x180003623  mov     [rsi+70h], r15d
0x180003627  inc     dword ptr [rsi+74h]
0x18000362a  mov     eax, 1
0x18000362f  neg     eax
0x180003631  lea     r13, [rsi-98h]
0x180003638  sbb     r14, r14
0x18000363b  and     r14, rdi
0x18000363e  xor     edi, edi
0x180003640  cmp     [r13+0A8h], edi
0x180003647  jnz     short loc_180003698
0x180003649  test    cs:Microsoft_Windows_DirectShow_CoreEnableBits, 10h
0x180003650  jz      short loc_18000366D
0x180003652  mov     [rsp+150h+var_128], edi
0x180003656  lea     rdx, StopStopEvent
0x18000365d  xor     r9d, r9d
0x180003660  mov     qword ptr [rsp+150h+bAlertable], rdi
0x180003665  mov     r8, r13
0x180003668  call    McTemplateU0ppzd_EventWriteTransfer
0x18000366d  test    r14, r14
0x180003670  jz      short loc_18000368C
0x180003672  add     dword ptr [r14+0Ch], 0FFFFFFFFh
0x180003677  jnz     short loc_18000368C
0x180003679  mov     rcx, [r14]; hMutex
0x18000367c  mov     [r14+8], edi
0x180003680  call    cs:__imp_ReleaseMutex
0x180003687  nop     dword ptr [rax+rax+00h]
0x18000368c  xor     eax, eax
0x18000368e  jmp     loc_1800037DE
0x180003693  mov     eax, r12d
0x180003696  jmp     short loc_18000362F
0x180003698  mov     rcx, [rsi+60h]; this
0x18000369c  call    ?Stop@CFGControl@@QEAAJXZ; CFGControl::Stop(void)
0x1800036a1  mov     rcx, [rsi+188h]; this
0x1800036a8  test    rcx, rcx
0x1800036ab  jz      short loc_1800036B2
0x1800036ad  call    ?Stop@CDistributorManager@@QEAAJXZ; CDistributorManager::Stop(void)
0x1800036b2  mov     rcx, r13; this
0x1800036b5  call    ?UpstreamOrder@CFilterGraph@@AEAAJXZ; CFilterGraph::UpstreamOrder(void)
0x1800036ba  mov     ebx, edi
0x1800036bc  mov     r12, rdi
0x1800036bf  lea     ecx, [rax+7FFFBFFFh]
0x1800036c5  cmp     ecx, 1
0x1800036c8  cmova   ebx, eax
0x1800036cb  lea     rax, [rsi+0E8h]
0x1800036d2  inc     dword ptr [rax]
0x1800036d4  mov     r15, [rsi+90h]
0x1800036db  test    r15, r15
0x1800036de  jz      short loc_180003744
0x1800036e0  mov     rax, [r15+10h]
0x1800036e4  mov     rdi, [rax]
0x1800036e7  mov     rcx, rdi
0x1800036ea  mov     rax, [rdi]
0x1800036ed  mov     rax, [rax+20h]
0x1800036f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036f6  test    eax, eax
0x1800036f8  mov     ecx, eax
0x1800036fa  cmovns  rdi, r12
0x1800036fe  mov     r12, rdi
0x180003701  xor     edi, edi
0x180003703  test    ebx, ebx
0x180003705  jz      short loc_18000370F
0x180003707  test    eax, eax
0x180003709  jns     short loc_180003719
0x18000370b  test    ebx, ebx
0x18000370d  js      short loc_180003719
0x18000370f  add     eax, 7FFFBFFFh
0x180003714  cmp     eax, 1
0x180003717  ja      short loc_180003724
0x180003719  lea     eax, [rbx+7FFFBFFFh]
0x18000371f  cmp     eax, 1
0x180003722  ja      short loc_180003726
0x180003724  mov     ebx, ecx
0x180003726  test    r15, r15
0x180003729  jnz     short loc_180003734
0x18000372b  mov     r15, [rsi+90h]
0x180003732  jmp     short loc_180003738
0x180003734  mov     r15, [r15+8]
0x180003738  test    r15, r15
0x18000373b  jnz     short loc_1800036E0
0x18000373d  lea     rax, [rsi+0E8h]
0x180003744  mov     [rsi+110h], rdi
0x18000374b  mov     rcx, rax; this
0x18000374e  mov     [rsi+108h], rdi
0x180003755  mov     word ptr [rsi+249h], 0
0x18000375e  mov     [rsi+250h], rdi
0x180003765  mov     [rsi+258h], rdi
0x18000376c  mov     [rsi+10h], edi
0x18000376f  call    ?Passive@CReconnectList@@QEAAXXZ; CReconnectList::Passive(void)
0x180003774  test    cs:Microsoft_Windows_DirectShow_CoreEnableBits, 10h
0x18000377b  jz      short loc_1800037BC
0x18000377d  test    r12, r12
0x180003780  jz      short loc_180003798
0x180003782  mov     rdx, r12; struct IUnknown *
0x180003785  lea     rcx, [rbp+50h+var_C0]; this
0x180003789  call    ??0CDisp@@QEAA@PEAUIUnknown@@@Z; CDisp::CDisp(IUnknown *)
0x18000378e  mov     edi, 1
0x180003793  mov     rcx, [rax]
0x180003796  jmp     short loc_18000379F
0x180003798  mov     rcx, rdi
0x18000379b  mov     edi, [rsp+150h+var_114]
0x18000379f  mov     [rsp+150h+var_128], ebx
0x1800037a3  lea     rdx, StopStopEvent
0x1800037aa  mov     r9, r12
  ... truncated ...
```
