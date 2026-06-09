# CFGControl::UpdateLists(void)

- ea: `0x18000cb50`
- end: `0x18000d163`
- name: `?UpdateLists@CFGControl@@QEAAJXZ`
- size: `1555`
- prototype: `__int64 __fastcall(CFGControl *__hidden this)`
- caller_count: `16`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180003868`
- `0x180005260`
- `0x18000be98`
- `0x18000c040`
- `0x18000c530`
- `0x18000c640`
- `0x18000c680`
- `0x180028678`
- `0x18002a620`
- `0x18002b730`
- `0x18002d948`
- `0x18006fda0`
- `0x18006fdd8`
- `0x180075964`
- `0x180077790`
- `0x180077be0`

## callees

- `0x18000cb50`
- `0x18001a050`
- `0x18001d3b0`
- `0x1800240d0`
- `0x18002a1d8`
- `0x18002d668`
- `0x18006fd34`
- `0x1800702f0`
- `0x180071ffc`
- `0x18015e010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18000cd1a`
- `KERNEL32!GetCurrentThread` at `0x18000cd3d`
- `KERNEL32!GetCurrentThread` at `0x18000cdae`
- `KERNEL32!GetCurrentThread` at `0x18000cd1a`
- `KERNEL32!GetCurrentThread` at `0x18000cd3d`
- `KERNEL32!GetCurrentThread` at `0x18000cdae`
- `KERNEL32!GetThreadPriority` at `0x18000cd29`
- `KERNEL32!GetThreadPriority` at `0x18000cd29`
- `KERNEL32!GetTickCount` at `0x18000ccf6`
- `KERNEL32!GetTickCount` at `0x18000ccf6`
- `KERNEL32!SetThreadPriority` at `0x18000cd51`
- `KERNEL32!SetThreadPriority` at `0x18000cdc0`
- `KERNEL32!SetThreadPriority` at `0x18000cd51`
- `KERNEL32!SetThreadPriority` at `0x18000cdc0`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000cbe8`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000cd7a`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000cbe8`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000cd7a`
- `KERNEL32!GetCurrentThreadId` at `0x18000cb72`
- `KERNEL32!GetCurrentThreadId` at `0x18000ce53`
- `KERNEL32!GetCurrentThreadId` at `0x18000cb72`
- `KERNEL32!GetCurrentThreadId` at `0x18000ce53`
- `KERNEL32!ReleaseMutex` at `0x18000d146`
- `KERNEL32!ReleaseMutex` at `0x18000d146`
- `USER32!GetQueueStatus` at `0x18000cdd1`
- `USER32!GetQueueStatus` at `0x18000cdd1`
- `USER32!DispatchMessageW` at `0x18000cc9d`
- `USER32!DispatchMessageW` at `0x18000cc9d`
- `USER32!PeekMessageW` at `0x18000cc89`
- `USER32!PeekMessageW` at `0x18000ccbe`
- `USER32!PeekMessageW` at `0x18000cce2`
- `USER32!PeekMessageW` at `0x18000ce3c`
- `USER32!PeekMessageW` at `0x18000cc89`
- `USER32!PeekMessageW` at `0x18000ccbe`
- `USER32!PeekMessageW` at `0x18000cce2`
- `USER32!PeekMessageW` at `0x18000ce3c`
- `USER32!MsgWaitForMultipleObjects` at `0x18000cc39`
- `USER32!MsgWaitForMultipleObjects` at `0x18000cc39`
- `USER32!RegisterWindowMessageW` at `0x18000cdfb`
- `USER32!RegisterWindowMessageW` at `0x18000cdfb`
- `USER32!PostThreadMessageW` at `0x18000ce6a`
- `USER32!PostThreadMessageW` at `0x18000ce6a`

## pseudocode

```c
__int64 __fastcall CFGControl::UpdateLists(void **this)
{
  CFGControl *v1; // rbx
  CFGControl *v2; // rdi
  DWORD CurrentThreadId; // eax
  int v4; // edx
  DWORD v5; // esi
  UINT v6; // r12d
  HWND v7; // r15
  int v8; // r13d
  DWORD v9; // r14d
  unsigned int v10; // edi
  DWORD v11; // eax
  DWORD v12; // esi
  DWORD v13; // ebx
  DWORD v14; // eax
  DWORD TickCount; // eax
  unsigned int v16; // edx
  unsigned int v17; // eax
  unsigned int v18; // ecx
  HANDLE CurrentThread; // rax
  HANDLE v20; // rax
  HANDLE v21; // rax
  UINT v22; // r15d
  BOOL v23; // eax
  DWORD v24; // eax
  int v25; // ecx
  bool v26; // zf
  int v27; // ecx
  int v28; // eax
  CFilterGraph *v29; // rcx
  int v30; // esi
  struct IMediaSeeking *v32; // r14
  int FilterMiscFlags; // eax
  CFGControl *v34; // rcx
  int v35; // esi
  struct IMediaSeekingVtbl *lpVtbl; // rax
  __int64 v37; // rcx
  __int64 v38; // rax
  struct IVideoWindow *v39; // rdx
  void *v40; // rcx
  __int64 v41; // [rsp+30h] [rbp-49h] BYREF
  struct IVideoWindow *v42; // [rsp+38h] [rbp-41h] BYREF
  void *v43; // [rsp+40h] [rbp-39h] BYREF
  HANDLE Handles[2]; // [rsp+48h] [rbp-31h] BYREF
  struct tagMSG Msg; // [rsp+58h] [rbp-21h] BYREF
  void **v46; // [rsp+E0h] [rbp+67h] BYREF
  int nPriority; // [rsp+E8h] [rbp+6Fh] BYREF
  unsigned int v48; // [rsp+F0h] [rbp+77h] BYREF
  struct IUnknown *i; // [rsp+F8h] [rbp+7Fh] BYREF

  v46 = this;
  v2 = (CFGControl *)this;
  v43 = this[2];
  v1 = (CFGControl *)v43;
  CurrentThreadId = GetCurrentThreadId();
  v4 = *((_DWORD *)v43 + 2);
  LODWORD(v41) = CurrentThreadId;
  v5 = CurrentThreadId;
  if ( CurrentThreadId != v4 )
  {
    v6 = *((_DWORD *)v43 + 6);
    if ( CurrentThreadId == *((_DWORD *)v43 + 7) )
      v7 = (HWND)*((_QWORD *)v43 + 2);
    else
      v7 = 0;
    Handles[0] = *(HANDLE *)v43;
    v48 = -1;
    nPriority = 0;
    v8 = 0;
    Handles[1] = 0;
    v9 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
    if ( v9 )
    {
      v10 = v48;
      v11 = 64;
      v12 = 0;
      if ( v7 )
        v11 = 72;
      LODWORD(v42) = v11;
      do
      {
        v13 = v10;
        if ( v10 > 0xA )
          v13 = 10;
        v14 = MsgWaitForMultipleObjects(1u, Handles, 0, v13, v11);
        v9 = v14;
        if ( v14 != 1 && (v14 != 258 || v13 == v10) )
          break;
        memset(&Msg, 0, sizeof(Msg));
        if ( v7 && PeekMessageW(&Msg, v7, v6, v6, 1u) )
        {
          do
            DispatchMessageW(&Msg);
          while ( PeekMessageW(&Msg, v7, v6, v6, 1u) );
        }
        PeekMessageW(&Msg, 0, 0, 0, 0);
        if ( v10 - 1 <= 0xFFFFFFFD )
        {
          TickCount = GetTickCount();
          v16 = TickCount - v12;
          v12 = TickCount;
          v17 = v10;
          v18 = v10 - v16;
          v10 = 0;
          if ( v16 <= v17 )
            v10 = v18;
        }
        if ( !v8 )
        {
          CurrentThread = GetCurrentThread();
          nPriority = GetThreadPriority(CurrentThread);
          if ( (unsigned int)nPriority < 2 )
          {
            v20 = GetCurrentThread();
            SetThreadPriority(v20, 2);
          }
          v8 = 1;
        }
        v9 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
        v11 = (unsigned int)v42;
      }
      while ( v9 );
      v1 = (CFGControl *)v43;
      v2 = (CFGControl *)v46;
      v5 = v41;
      if ( v8 )
      {
        v21 = GetCurrentThread();
        SetThreadPriority(v21, nPriority);
        if ( (GetQueueStatus(8u) & 0x80000) != 0 )
        {
          v22 = wMsgFilterMax;
          if ( wMsgFilterMax || (wMsgFilterMax = RegisterWindowMessageW(L"AMUnblock"), (v22 = wMsgFilterMax) != 0) )
          {
            memset(&Msg, 0, sizeof(Msg));
            do
            {
              v23 = PeekMessageW(&Msg, HWND_MESSAGE|0x2LL, v22, v22, 1u);
              v22 = wMsgFilterMax;
            }
            while ( v23 );
          }
          v24 = GetCurrentThreadId();
          PostThreadMessageW(v24, v22, 0, 0);
        }
      }
    }
    if ( v9 )
    {
      v25 = 0;
      goto LABEL_35;
    }
    *((_DWORD *)v1 + 2) = v5;
  }
  ++*((_DWORD *)v1 + 3);
  v25 = 1;
LABEL_35:
  if ( !v25 )
    v1 = 0;
  v26 = *((_DWORD *)v2 + 54) == 0;
  v46 = (void **)v1;
  if ( !v26 )
  {
    CAutoMsgMutex::~CAutoMsgMutex((CAutoMsgMutex *)&v46);
    return 0;
  }
  v27 = *(_DWORD *)(*(_QWORD *)v2 + 404LL);
  v28 = *((_DWORD *)v2 + 7);
  *((_DWORD *)v2 + 7) = v27;
  if ( v27 == v28 )
    goto LABEL_78;
  nPriority = 0;
  *((_DWORD *)v2 + 266) = 0;
  CFGControl::EmptyLists(v2);
  v29 = *(CFilterGraph **)v2;
  Handles[0] = 0;
  v30 = CFilterGraph::EnumFilters(v29, (struct IEnumFilters **)Handles);
  if ( v30 < 0 )
  {
    CAutoMsgMutex::~CAutoMsgMutex((CAutoMsgMutex *)&v46);
    return (unsigned int)v30;
  }
  for ( i = 0;
        !(*(unsigned int (__fastcall **)(HANDLE, __int64, struct IUnknown **, _QWORD))(*(_QWORD *)Handles[0] + 24LL))(
           Handles[0],
           1,
           &i,
           0);
        ((void (__fastcall *)(struct IUnknown *))i->lpVtbl->Release)(i) )
  {
    v32 = CMediaSeekingProxy::CreateIMediaSeeking((struct IBaseFilter *)i, &nPriority);
    v48 = 0;
    FilterMiscFlags = GetFilterMiscFlags(i, &v48);
    v35 = nPriority;
    if ( FilterMiscFlags >= 0 )
    {
      if ( (v48 & 1) != 0 )
        goto LABEL_50;
      goto LABEL_51;
    }
    if ( nPriority >= 0 )
    {
      if ( !CFGControl::IsRenderer(v34, (struct IBaseFilter *)i) )
LABEL_50:
        ++*((_DWORD *)v2 + 6);
LABEL_51:
      if ( v35 >= 0 )
      {
        CBaseList::AddTailI((CFGControl *)((char *)v2 + 288), v32);
        lpVtbl = v32->lpVtbl;
        LODWORD(v46) = 0;
        if ( ((int (__fastcall *)(struct IMediaSeeking *, void ***))lpVtbl->GetCapabilities)(v32, &v46) < 0 )
        {
          *((_DWORD *)v2 + 266) &= ~0x80u;
        }
        else if ( *((_DWORD *)v2 + 76) == 1 )
        {
          *((_DWORD *)v2 + 266) = (_DWORD)v46;
        }
        else
        {
          *((_DWORD *)v2 + 266) &= (unsigned int)v46;
        }
      }
    }
    v41 = 0;
    if ( !*((_QWORD *)v2 + 34) )
    {
      ((void (__fastcall *)(struct IUnknown *, GUID *, __int64 *))i->lpVtbl->QueryInterface)(i, &IID_IBasicVideo, &v41);
      if ( !*((_QWORD *)v2 + 35) )
        *((_QWORD *)v2 + 35) = v41;
    }
    v42 = 0;
    if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IVideoWindow **))i->lpVtbl->QueryInterface)(
           i,
           &IID_IVideoWindow,
           &v42) >= 0 )
      CBaseList::AddTailI((CFGControl *)((char *)v2 + 368), v42);
    if ( *((_QWORD *)v2 + 34) )
      goto LABEL_68;
    if ( !v41 )
      goto LABEL_70;
    if ( !v42 )
    {
LABEL_68:
      if ( v41 && v41 != *((_QWORD *)v2 + 35) )
        (*(void (**)(void))(*(_QWORD *)v41 + 16LL))();
    }
    else
    {
      CFGControl::SetFirstVW(v2, v42);
      v37 = *((_QWORD *)v2 + 35);
      if ( v37 != v41 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        *((_QWORD *)v2 + 35) = v41;
      }
    }
LABEL_70:
    v43 = 0;
    nPriority = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, void **))i->lpVtbl->QueryInterface)(
                  i,
                  &IID_IBasicAudio,
                  &v43);
    if ( nPriority >= 0 )
      CBaseList::AddTailI((CFGControl *)((char *)v2 + 328), v43);
  }
  (*(void (__fastcall **)(HANDLE))(*(_QWORD *)Handles[0] + 16LL))(Handles[0]);
  if ( !*((_QWORD *)v2 + 34) )
  {
    v38 = *((_QWORD *)v2 + 46);
    if ( v38 )
      v39 = *(struct IVideoWindow **)(v38 + 16);
    else
      v39 = 0;
    CFGControl::SetFirstVW(v2, v39);
  }
LABEL_78:
  if ( v1 )
  {
    v26 = (*((_DWORD *)v1 + 3))-- == 1;
    if ( v26 )
    {
      v40 = *(void **)v1;
      *((_DWORD *)v1 + 2) = 0;
      ReleaseMutex(v40);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000cb50  mov     [rsp-8+arg_0], rcx
0x18000cb55  push    rbp
0x18000cb56  push    rbx
0x18000cb57  push    rsi
0x18000cb58  push    rdi
0x18000cb59  push    r14
0x18000cb5b  lea     rbp, [rsp-37h]
0x18000cb60  sub     rsp, 0B0h
0x18000cb67  mov     rbx, [rcx+10h]
0x18000cb6b  mov     rdi, rcx
0x18000cb6e  mov     [rbp+57h+var_90], rbx
0x18000cb72  call    cs:__imp_GetCurrentThreadId
0x18000cb79  nop     dword ptr [rax+rax+00h]
0x18000cb7e  mov     edx, [rbx+8]
0x18000cb81  xor     r14d, r14d
0x18000cb84  mov     dword ptr [rbp+57h+var_A0], eax
0x18000cb87  mov     esi, eax
0x18000cb89  cmp     eax, edx
0x18000cb8b  jz      loc_18000CE99
0x18000cb91  mov     [rsp+0D0h+var_28], r12
0x18000cb99  mov     r12d, [rbx+18h]
0x18000cb9d  mov     [rsp+0D0h+var_30], r13
0x18000cba5  mov     [rsp+0D0h+var_38], r15
0x18000cbad  cmp     eax, [rbx+1Ch]
0x18000cbb0  jnz     short loc_18000CBB8
0x18000cbb2  mov     r15, [rbx+10h]
0x18000cbb6  jmp     short loc_18000CBBB
0x18000cbb8  mov     r15, r14
0x18000cbbb  mov     rax, [rbx]
0x18000cbbe  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18000cbc2  xor     r9d, r9d; dwMilliseconds
0x18000cbc5  mov     [rbp+57h+Handles], rax
0x18000cbc9  xor     r8d, r8d; bWaitAll
0x18000cbcc  mov     [rbp+57h+arg_10], 0FFFFFFFFh
0x18000cbd3  mov     ecx, 1; nCount
0x18000cbd8  mov     [rbp+57h+nPriority], r14d
0x18000cbdc  mov     r13d, r14d
0x18000cbdf  mov     [rbp+57h+var_80], r14
0x18000cbe3  mov     [rsp+0D0h+bAlertable], r14d; bAlertable
0x18000cbe8  call    cs:__imp_WaitForMultipleObjectsEx
0x18000cbef  nop     dword ptr [rax+rax+00h]
0x18000cbf4  mov     r14d, eax
0x18000cbf7  cmp     eax, 1
0x18000cbfa  jb      loc_18000CE76
0x18000cc00  mov     edi, [rbp+57h+arg_10]
0x18000cc03  mov     ecx, 48h ; 'H'
0x18000cc08  test    r15, r15
0x18000cc0b  mov     eax, 40h ; '@'
0x18000cc10  mov     esi, r13d
0x18000cc13  cmovnz  eax, ecx
0x18000cc16  mov     ecx, 0Ah
0x18000cc1b  mov     dword ptr [rbp+57h+var_98], eax
0x18000cc1e  cmp     edi, 0Ah
0x18000cc21  mov     [rsp+0D0h+bAlertable], eax; dwWakeMask
0x18000cc25  mov     ebx, edi
0x18000cc27  lea     rdx, [rbp+57h+Handles]; pHandles
0x18000cc2b  cmova   ebx, ecx
0x18000cc2e  xor     r8d, r8d; fWaitAll
0x18000cc31  mov     r9d, ebx; dwMilliseconds
0x18000cc34  mov     ecx, 1; nCount
0x18000cc39  call    cs:__imp_MsgWaitForMultipleObjects
0x18000cc40  nop     dword ptr [rax+rax+00h]
0x18000cc45  mov     r14d, eax
0x18000cc48  cmp     eax, 1
0x18000cc4b  jz      short loc_18000CC60
0x18000cc4d  cmp     eax, 102h
0x18000cc52  jnz     loc_18000CD9A
0x18000cc58  cmp     ebx, edi
0x18000cc5a  jz      loc_18000CD9A
0x18000cc60  xorps   xmm0, xmm0
0x18000cc63  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x18000cc67  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x18000cc6b  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x18000cc6f  test    r15, r15
0x18000cc72  jz      short loc_18000CCCE
0x18000cc74  mov     r9d, r12d; wMsgFilterMax
0x18000cc77  mov     [rsp+0D0h+bAlertable], 1; wRemoveMsg
0x18000cc7f  mov     r8d, r12d; wMsgFilterMin
0x18000cc82  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18000cc86  mov     rdx, r15; hWnd
0x18000cc89  call    cs:__imp_PeekMessageW
0x18000cc90  nop     dword ptr [rax+rax+00h]
0x18000cc95  test    eax, eax
0x18000cc97  jz      short loc_18000CCCE
0x18000cc99  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18000cc9d  call    cs:__imp_DispatchMessageW
0x18000cca4  nop     dword ptr [rax+rax+00h]
0x18000cca9  mov     r9d, r12d; wMsgFilterMax
0x18000ccac  mov     [rsp+0D0h+bAlertable], 1; wRemoveMsg
0x18000ccb4  mov     r8d, r12d; wMsgFilterMin
0x18000ccb7  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18000ccbb  mov     rdx, r15; hWnd
0x18000ccbe  call    cs:__imp_PeekMessageW
0x18000ccc5  nop     dword ptr [rax+rax+00h]
0x18000ccca  test    eax, eax
0x18000cccc  jnz     short loc_18000CC99
0x18000ccce  xor     r9d, r9d; wMsgFilterMax
0x18000ccd1  mov     [rsp+0D0h+bAlertable], 0; wRemoveMsg
0x18000ccd9  xor     r8d, r8d; wMsgFilterMin
0x18000ccdc  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18000cce0  xor     edx, edx; hWnd
0x18000cce2  call    cs:__imp_PeekMessageW
0x18000cce9  nop     dword ptr [rax+rax+00h]
0x18000ccee  lea     eax, [rdi-1]
0x18000ccf1  cmp     eax, 0FFFFFFFDh
0x18000ccf4  ja      short loc_18000CD15
0x18000ccf6  call    cs:__imp_GetTickCount
0x18000ccfd  nop     dword ptr [rax+rax+00h]
0x18000cd02  mov     ecx, edi
0x18000cd04  mov     edx, eax
0x18000cd06  sub     edx, esi
0x18000cd08  mov     esi, eax
0x18000cd0a  mov     eax, edi
0x18000cd0c  sub     ecx, edx
0x18000cd0e  xor     edi, edi
0x18000cd10  cmp     edx, eax
0x18000cd12  cmovbe  edi, ecx
0x18000cd15  test    r13d, r13d
0x18000cd18  jnz     short loc_18000CD63
0x18000cd1a  call    cs:__imp_GetCurrentThread
0x18000cd21  nop     dword ptr [rax+rax+00h]
0x18000cd26  mov     rcx, rax; hThread
0x18000cd29  call    cs:__imp_GetThreadPriority
0x18000cd30  nop     dword ptr [rax+rax+00h]
0x18000cd35  mov     [rbp+57h+nPriority], eax
0x18000cd38  cmp     eax, 2
0x18000cd3b  jnb     short loc_18000CD5D
0x18000cd3d  call    cs:__imp_GetCurrentThread
0x18000cd44  nop     dword ptr [rax+rax+00h]
0x18000cd49  mov     rcx, rax; hThread
0x18000cd4c  mov     edx, 2; nPriority
0x18000cd51  call    cs:__imp_SetThreadPriority
0x18000cd58  nop     dword ptr [rax+rax+00h]
0x18000cd5d  mov     r13d, 1
0x18000cd63  xor     r9d, r9d; dwMilliseconds
0x18000cd66  mov     [rsp+0D0h+bAlertable], 0; bAlertable
0x18000cd6e  xor     r8d, r8d; bWaitAll
0x18000cd71  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18000cd75  mov     ecx, 1; nCount
0x18000cd7a  call    cs:__imp_WaitForMultipleObjectsEx
0x18000cd81  nop     dword ptr [rax+rax+00h]
0x18000cd86  mov     r14d, eax
0x18000cd89  cmp     eax, 1
0x18000cd8c  mov     eax, dword ptr [rbp+57h+var_98]
0x18000cd8f  mov     ecx, 0Ah
0x18000cd94  jnb     loc_18000CC1E
0x18000cd9a  mov     rbx, [rbp+57h+var_90]
0x18000cd9e  mov     rdi, [rbp+57h+arg_0]
0x18000cda2  mov     esi, dword ptr [rbp+57h+var_A0]
0x18000cda5  test    r13d, r13d
0x18000cda8  jz      loc_18000CE76
0x18000cdae  call    cs:__imp_GetCurrentThread
0x18000cdb5  nop     dword ptr [rax+rax+00h]
0x18000cdba  mov     edx, [rbp+57h+nPriority]; nPriority
0x18000cdbd  mov     rcx, rax; hThread
0x18000cdc0  call    cs:__imp_SetThreadPriority
0x18000cdc7  nop     dword ptr [rax+rax+00h]
0x18000cdcc  mov     ecx, 8; flags
0x18000cdd1  call    cs:__imp_GetQueueStatus
0x18000cdd8  nop     dword ptr [rax+rax+00h]
0x18000cddd  shr     eax, 10h
0x18000cde0  test    al, 8
0x18000cde2  jz      loc_18000CE76
0x18000cde8  mov     r15d, cs:wMsgFilterMax
0x18000cdef  test    r15d, r15d
0x18000cdf2  jnz     short loc_18000CE14
0x18000cdf4  lea     rcx, String; "AMUnblock"
0x18000cdfb  call    cs:__imp_RegisterWindowMessageW
0x18000ce02  nop     dword ptr [rax+rax+00h]
0x18000ce07  mov     cs:wMsgFilterMax, eax
0x18000ce0d  mov     r15d, eax
0x18000ce10  test    eax, eax
0x18000ce12  jz      short loc_18000CE53
0x18000ce14  xorps   xmm0, xmm0
0x18000ce17  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x18000ce1b  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x18000ce1f  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x18000ce23  mov     r9d, r15d; wMsgFilterMax
0x18000ce26  mov     [rsp+0D0h+bAlertable], 1; wRemoveMsg
0x18000ce2e  mov     r8d, r15d; wMsgFilterMin
0x18000ce31  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18000ce35  mov     rdx, 0FFFFFFFFFFFFFFFFh; hWnd
0x18000ce3c  call    cs:__imp_PeekMessageW
0x18000ce43  nop     dword ptr [rax+rax+00h]
0x18000ce48  mov     r15d, cs:wMsgFilterMax
0x18000ce4f  test    eax, eax
0x18000ce51  jnz     short loc_18000CE23
0x18000ce53  call    cs:__imp_GetCurrentThreadId
0x18000ce5a  nop     dword ptr [rax+rax+00h]
0x18000ce5f  xor     r9d, r9d; lParam
0x18000ce62  xor     r8d, r8d; wParam
0x18000ce65  mov     ecx, eax; idThread
0x18000ce67  mov     edx, r15d; Msg
0x18000ce6a  call    cs:__imp_PostThreadMessageW
0x18000ce71  nop     dword ptr [rax+rax+00h]
0x18000ce76  mov     r15, [rsp+0D0h+var_38]
0x18000ce7e  mov     r13, [rsp+0D0h+var_30]
0x18000ce86  mov     r12, [rsp+0D0h+var_28]
0x18000ce8e  test    r14d, r14d
0x18000ce91  jnz     short loc_18000CEC2
0x18000ce93  mov     [rbx+8], esi
0x18000ce96  xor     r14d, r14d
0x18000ce99  inc     dword ptr [rbx+0Ch]
0x18000ce9c  mov     ecx, 1
0x18000cea1  test    ecx, ecx
0x18000cea3  cmovz   rbx, r14
0x18000cea7  cmp     dword ptr [rdi+0D8h], 0
0x18000ceae  mov     [rbp+57h+arg_0], rbx
0x18000ceb2  jz      short loc_18000CECA
0x18000ceb4  lea     rcx, [rbp+57h+arg_0]; this
0x18000ceb8  call    ??1CAutoMsgMutex@@QEAA@XZ; CAutoMsgMutex::~CAutoMsgMutex(void)
0x18000cebd  jmp     loc_18000D152
0x18000cec2  xor     r14d, r14d
0x18000cec5  mov     ecx, r14d
0x18000cec8  jmp     short loc_18000CEA1
0x18000ceca  mov     rax, [rdi]
0x18000cecd  mov     ecx, [rax+194h]
0x18000ced3  mov     eax, [rdi+1Ch]
0x18000ced6  mov     [rdi+1Ch], ecx
0x18000ced9  cmp     ecx, eax
0x18000cedb  jz      loc_18000D134
0x18000cee1  mov     rcx, rdi; this
0x18000cee4  mov     [rbp+57h+nPriority], r14d
0x18000cee8  mov     [rdi+428h], r14d
0x18000ceef  call    ?EmptyLists@CFGControl@@IEAAXXZ; CFGControl::EmptyLists(void)
0x18000cef4  mov     rcx, [rdi]; this
0x18000cef7  lea     rdx, [rbp+57h+Handles]; struct IEnumFilters **
0x18000cefb  mov     [rbp+57h+Handles], r14
0x18000ceff  call    ?EnumFilters@CFilterGraph@@UEAAJPEAPEAUIEnumFilters@@@Z; CFilterGraph::EnumFilters(IEnumFilters * *)
0x18000cf04  mov     esi, eax
0x18000cf06  test    eax, eax
0x18000cf08  jns     short loc_18000CF1A
0x18000cf0a  lea     rcx, [rbp+57h+arg_0]; this
0x18000cf0e  call    ??1CAutoMsgMutex@@QEAA@XZ; CAutoMsgMutex::~CAutoMsgMutex(void)
0x18000cf13  mov     eax, esi
0x18000cf15  jmp     loc_18000D154
0x18000cf1a  mov     [rbp+57h+arg_18], r14
0x18000cf1e  mov     rcx, [rbp+57h+Handles]
0x18000cf22  lea     r8, [rbp+57h+arg_18]
0x18000cf26  xor     r9d, r9d
0x18000cf29  mov     edx, 1
0x18000cf2e  mov     rax, [rcx]
0x18000cf31  mov     rax, [rax+18h]
0x18000cf35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf3a  test    eax, eax
0x18000cf3c  jnz     loc_18000D0FD
0x18000cf42  mov     rcx, [rbp+57h+arg_18]; struct IBaseFilter *
0x18000cf46  lea     rdx, [rbp+57h+nPriority]; int *
0x18000cf4a  call    ?CreateIMediaSeeking@CMediaSeekingProxy@@SAPEAUIMediaSeeking@@PEAUIBaseFilter@@PEAJ@Z; CMediaSeekingProxy::CreateIMediaSeeking(IBaseFilter *,long *)
0x18000cf4f  mov     rcx, [rbp+57h+arg_18]; struct IUnknown *
0x18000cf53  lea     rdx, [rbp+57h+arg_10]; unsigned int *
0x18000cf57  mov     r14, rax
0x18000cf5a  mov     [rbp+57h+arg_10], 0
0x18000cf61  call    ?GetFilterMiscFlags@@YAJPEAUIUnknown@@PEAK@Z; GetFilterMiscFlags(IUnknown *,ulong *)
0x18000cf66  mov     esi, [rbp+57h+nPriority]
0x18000cf69  test    eax, eax
0x18000cf6b  js      short loc_18000CF75
0x18000cf6d  test    byte ptr [rbp+57h+arg_10], 1
0x18000cf71  jnz     short loc_18000CF86
0x18000cf73  jmp     short loc_18000CF89
0x18000cf75  test    esi, esi
0x18000cf77  js      short loc_18000CFE0
0x18000cf79  mov     rdx, [rbp+57h+arg_18]; struct IBaseFilter *
0x18000cf7d  call    ?IsRenderer@CFGControl@@IEAAJPEAUIBaseFilter@@@Z; CFGControl::IsRenderer(IBaseFilter *)
0x18000cf82  test    eax, eax
0x18000cf84  jnz     short loc_18000CF89
0x18000cf86  inc     dword ptr [rdi+18h]
0x18000cf89  test    esi, esi
0x18000cf8b  js      short loc_18000CFE0
0x18000cf8d  lea     rcx, [rdi+120h]; this
0x18000cf94  mov     rdx, r14; void *
0x18000cf97  call    ?AddTailI@CBaseList@@IEAAPEAU__POSITION@@PEAX@Z; CBaseList::AddTailI(void *)
0x18000cf9c  mov     rax, [r14]
0x18000cf9f  lea     rdx, [rbp+57h+arg_0]
0x18000cfa3  mov     rcx, r14
0x18000cfa6  mov     dword ptr [rbp+57h+arg_0], 0
0x18000cfad  mov     rax, [rax+18h]
0x18000cfb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfb6  test    eax, eax
0x18000cfb8  js      short loc_18000CFD6
0x18000cfba  cmp     dword ptr [rdi+130h], 1
0x18000cfc1  mov     eax, dword ptr [rbp+57h+arg_0]
0x18000cfc4  jnz     short loc_18000CFCE
0x18000cfc6  mov     [rdi+428h], eax
0x18000cfcc  jmp     short loc_18000CFE0
0x18000cfce  and     [rdi+428h], eax
0x18000cfd4  jmp     short loc_18000CFE0
0x18000cfd6  and     dword ptr [rdi+428h], 0FFFFFF7Fh
0x18000cfe0  xor     r14d, r14d
0x18000cfe3  mov     [rbp+57h+var_A0], r14
0x18000cfe7  cmp     [rdi+110h], r14
0x18000cfee  jnz     short loc_18000D01E
0x18000cff0  mov     rcx, [rbp+57h+arg_18]
0x18000cff4  lea     r8, [rbp+57h+var_A0]
0x18000cff8  lea     rdx, IID_IBasicVideo
0x18000cfff  mov     rax, [rcx]
0x18000d002  mov     rax, [rax]
0x18000d005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d00a  cmp     [rdi+118h], r14
0x18000d011  jnz     short loc_18000D01E
  ... truncated ...
```
