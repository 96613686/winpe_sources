# CFilterGraph::CancelStepInternal(FRAME_SKIP_NOTIFY)

- ea: `0x18001d598`
- end: `0x18001d9b1`
- name: `?CancelStepInternal@CFilterGraph@@QEAAJW4FRAME_SKIP_NOTIFY@@@Z`
- size: `1049`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002a3d0`
- `0x180030320`
- `0x180064d74`
- `0x180070660`
- `0x180070eec`
- `0x180071720`

## callees

- `0x18001d3b0`
- `0x18001d598`
- `0x180027efc`
- `0x18005d570`
- `0x180060a3c`
- `0x18015e010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18001d744`
- `KERNEL32!GetCurrentThread` at `0x18001d767`
- `KERNEL32!GetCurrentThread` at `0x18001d7d0`
- `KERNEL32!GetCurrentThread` at `0x18001d744`
- `KERNEL32!GetCurrentThread` at `0x18001d767`
- `KERNEL32!GetCurrentThread` at `0x18001d7d0`
- `KERNEL32!GetThreadPriority` at `0x18001d753`
- `KERNEL32!GetThreadPriority` at `0x18001d753`
- `KERNEL32!GetTickCount` at `0x18001d71b`
- `KERNEL32!GetTickCount` at `0x18001d71b`
- `KERNEL32!SetThreadPriority` at `0x18001d779`
- `KERNEL32!SetThreadPriority` at `0x18001d7e2`
- `KERNEL32!SetThreadPriority` at `0x18001d779`
- `KERNEL32!SetThreadPriority` at `0x18001d7e2`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18001d62d`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18001d7a0`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18001d62d`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18001d7a0`
- `KERNEL32!GetCurrentThreadId` at `0x18001d5c6`
- `KERNEL32!GetCurrentThreadId` at `0x18001d86e`
- `KERNEL32!GetCurrentThreadId` at `0x18001d5c6`
- `KERNEL32!GetCurrentThreadId` at `0x18001d86e`
- `KERNEL32!ReleaseMutex` at `0x18001d98e`
- `KERNEL32!ReleaseMutex` at `0x18001d98e`
- `USER32!GetQueueStatus` at `0x18001d7f3`
- `USER32!GetQueueStatus` at `0x18001d7f3`
- `USER32!DispatchMessageW` at `0x18001d6c1`
- `USER32!DispatchMessageW` at `0x18001d6c1`
- `USER32!PeekMessageW` at `0x18001d6e2`
- `USER32!PeekMessageW` at `0x18001d706`
- `USER32!PeekMessageW` at `0x18001d858`
- `USER32!PeekMessageW` at `0x18001d6e2`
- `USER32!PeekMessageW` at `0x18001d706`
- `USER32!PeekMessageW` at `0x18001d858`
- `USER32!MsgWaitForMultipleObjects` at `0x18001d67b`
- `USER32!MsgWaitForMultipleObjects` at `0x18001d67b`
- `USER32!RegisterWindowMessageW` at `0x18001d81b`
- `USER32!RegisterWindowMessageW` at `0x18001d81b`
- `USER32!PostThreadMessageW` at `0x18001d884`
- `USER32!PostThreadMessageW` at `0x18001d884`

## pseudocode

```c
__int64 __fastcall CFilterGraph::CancelStepInternal(CFilterGraph *a1, int a2)
{
  int v2; // r12d
  __int64 v3; // rsi
  CFilterGraph *v4; // rbx
  DWORD CurrentThreadId; // eax
  int v6; // r8d
  DWORD v7; // r15d
  HWND v8; // rdi
  void *v9; // rax
  unsigned int v10; // r13d
  DWORD v11; // r14d
  int v12; // esi
  DWORD v13; // r15d
  DWORD v14; // eax
  DWORD TickCount; // eax
  unsigned int v16; // edx
  unsigned int v17; // ecx
  unsigned int v18; // eax
  HANDLE CurrentThread; // rax
  HANDLE v20; // rax
  bool v21; // zf
  HANDLE v22; // rax
  UINT v23; // edi
  BOOL v24; // eax
  DWORD v25; // eax
  int v26; // eax
  int v27; // eax
  struct IUnknown *v28; // rdx
  CFilterGraph *v29; // rcx
  unsigned int v30; // esi
  __int64 v31; // rcx
  unsigned int nPriority; // [rsp+30h] [rbp-39h]
  UINT wMsgFilterMin; // [rsp+38h] [rbp-31h]
  HANDLE Handles[2]; // [rsp+40h] [rbp-29h] BYREF
  MSG Msg; // [rsp+50h] [rbp-19h] BYREF
  CFilterGraph *v37; // [rsp+D0h] [rbp+67h] BYREF
  int v38; // [rsp+D8h] [rbp+6Fh]
  DWORD v39; // [rsp+E0h] [rbp+77h]
  DWORD v40; // [rsp+E8h] [rbp+7Fh]

  v38 = a2;
  v37 = a1;
  v2 = a2;
  v3 = (__int64)a1 + 256;
  v4 = a1;
  CurrentThreadId = GetCurrentThreadId();
  v6 = *(_DWORD *)(v3 + 8);
  v7 = CurrentThreadId;
  v39 = CurrentThreadId;
  if ( CurrentThreadId == v6 )
    goto LABEL_34;
  wMsgFilterMin = *(_DWORD *)(v3 + 24);
  if ( CurrentThreadId == *(_DWORD *)(v3 + 28) )
    v8 = *(HWND *)(v3 + 16);
  else
    v8 = 0;
  v9 = *(void **)v3;
  nPriority = 0;
  Handles[1] = 0;
  v10 = -1;
  v40 = 0;
  Handles[0] = v9;
  v11 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
  if ( v11 )
  {
    v12 = 0;
    do
    {
      v13 = v10;
      if ( v10 > 0xA )
        v13 = 10;
      v14 = MsgWaitForMultipleObjects(1u, Handles, 0, v13, v8 != 0 ? 72 : 64);
      v11 = v14;
      if ( v14 != 1 && (v14 != 258 || v13 == v10) )
        break;
      memset(&Msg, 0, sizeof(Msg));
      if ( v8 )
      {
        while ( PeekMessageW(&Msg, v8, wMsgFilterMin, wMsgFilterMin, 1u) )
          DispatchMessageW(&Msg);
      }
      PeekMessageW(&Msg, 0, 0, 0, 0);
      if ( v10 - 1 <= 0xFFFFFFFD )
      {
        TickCount = GetTickCount();
        v16 = TickCount - v40;
        v17 = v10 - (TickCount - v40);
        v40 = TickCount;
        v18 = v10;
        v10 = 0;
        if ( v16 <= v18 )
          v10 = v17;
      }
      if ( !v12 )
      {
        CurrentThread = GetCurrentThread();
        nPriority = GetThreadPriority(CurrentThread);
        if ( nPriority < 2 )
        {
          v20 = GetCurrentThread();
          SetThreadPriority(v20, 2);
        }
        v12 = 1;
      }
      v11 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
    }
    while ( v11 );
    v4 = v37;
    v21 = v12 == 0;
    v3 = (__int64)v37 + 256;
    if ( !v21 )
    {
      v22 = GetCurrentThread();
      SetThreadPriority(v22, nPriority);
      if ( (GetQueueStatus(8u) & 0x80000) != 0 )
      {
        v23 = wMsgFilterMax;
        if ( wMsgFilterMax || (wMsgFilterMax = RegisterWindowMessageW(L"AMUnblock"), (v23 = wMsgFilterMax) != 0) )
        {
          memset(&Msg, 0, sizeof(Msg));
          do
          {
            v24 = PeekMessageW(&Msg, HWND_MESSAGE|0x2LL, v23, v23, 1u);
            v23 = wMsgFilterMax;
          }
          while ( v24 );
        }
        v25 = GetCurrentThreadId();
        PostThreadMessageW(v25, v23, 0, 0);
      }
    }
    v7 = v39;
    v2 = v38;
  }
  if ( !v11 )
  {
    *((_DWORD *)v4 + 66) = v7;
LABEL_34:
    ++*((_DWORD *)v4 + 67);
    v26 = 1;
    goto LABEL_35;
  }
  v26 = 0;
LABEL_35:
  v27 = -v26;
  v28 = (struct IUnknown *)*((_QWORD *)v4 + 81);
  v29 = (CFilterGraph *)(v3 & -(__int64)(v27 != 0));
  v37 = v29;
  if ( v28 )
  {
    v30 = CFilterGraph::CallThroughFrameStepPropertySet(v29, v28, 2u, 0);
    CImplMediaEvent::CEventStore::ClearEvents((CImplMediaEvent::CEventStore *)(*((_QWORD *)v4 + 31) + 808LL), 36);
    ++*(_DWORD *)(*((_QWORD *)v4 + 31) + 168LL);
    ATL::AtlComPtrAssign((struct IUnknown **)v4 + 81, 0);
    if ( v2 != 1 && *((_DWORD *)v4 + 166) == 1 )
    {
      v31 = *((_QWORD *)v4 + 82);
      if ( v31 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 32LL))(v31, 2147500036LL);
    }
    *((_DWORD *)v4 + 166) = 0;
    ATL::AtlComPtrAssign((struct IUnknown **)v4 + 82, 0);
    CAutoMsgMutex::~CAutoMsgMutex((CAutoMsgMutex *)&v37);
    return v30;
  }
  else
  {
    if ( v29 )
    {
      v21 = (*(_DWORD *)((v3 & -(__int64)(v27 != 0)) + 0xC))-- == 1;
      if ( v21 )
      {
        *(_DWORD *)((v3 & -(__int64)(v27 != 0)) + 8) = 0;
        ReleaseMutex(*(HANDLE *)v29);
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18001d598  mov     [rsp-8+arg_8], edx
0x18001d59c  mov     [rsp-8+arg_0], rcx
0x18001d5a1  push    rbp
0x18001d5a2  push    rbx
0x18001d5a3  push    rsi
0x18001d5a4  push    rdi
0x18001d5a5  push    r12
0x18001d5a7  push    r13
0x18001d5a9  push    r14
0x18001d5ab  push    r15
0x18001d5ad  lea     rbp, [rsp-1Fh]
0x18001d5b2  sub     rsp, 88h
0x18001d5b9  mov     r12d, edx
0x18001d5bc  lea     rsi, [rcx+100h]
0x18001d5c3  mov     rbx, rcx
0x18001d5c6  call    cs:__imp_GetCurrentThreadId
0x18001d5cd  nop     dword ptr [rax+rax+00h]
0x18001d5d2  mov     r8d, [rsi+8]
0x18001d5d6  mov     r15d, eax
0x18001d5d9  mov     [rbp+57h+arg_10], eax
0x18001d5dc  cmp     eax, r8d
0x18001d5df  jz      loc_18001D8A8
0x18001d5e5  mov     eax, [rsi+18h]
0x18001d5e8  mov     [rbp+57h+wMsgFilterMin], eax
0x18001d5eb  cmp     r15d, [rsi+1Ch]
0x18001d5ef  jnz     short loc_18001D5F7
0x18001d5f1  mov     rdi, [rsi+10h]
0x18001d5f5  jmp     short loc_18001D5F9
0x18001d5f7  xor     edi, edi
0x18001d5f9  mov     rax, [rsi]
0x18001d5fc  xor     edx, edx
0x18001d5fe  xor     r9d, r9d; dwMilliseconds
0x18001d601  mov     [rbp+57h+nPriority], edx
0x18001d604  mov     [rbp+57h+var_78], rdx
0x18001d608  xor     r8d, r8d; bWaitAll
0x18001d60b  mov     [rsp+0C0h+bAlertable], edx; bAlertable
0x18001d60f  or      r13d, 0FFFFFFFFh
0x18001d613  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18001d617  mov     [rbp+57h+var_8C], 0
0x18001d61e  lea     ecx, [r9+1]; nCount
0x18001d622  mov     [rbp+57h+arg_18], 0
0x18001d629  mov     [rbp+57h+Handles], rax
0x18001d62d  call    cs:__imp_WaitForMultipleObjectsEx
0x18001d634  nop     dword ptr [rax+rax+00h]
0x18001d639  mov     r14d, eax
0x18001d63c  cmp     eax, 1
0x18001d63f  jb      loc_18001D898
0x18001d645  mov     esi, [rbp+57h+var_8C]
0x18001d648  mov     rax, rdi
0x18001d64b  neg     rax
0x18001d64e  mov     eax, 0Ah
0x18001d653  sbb     r12d, r12d
0x18001d656  and     r12d, 8
0x18001d65a  add     r12d, 40h ; '@'
0x18001d65e  cmp     r13d, eax
0x18001d661  mov     [rsp+0C0h+bAlertable], r12d; dwWakeMask
0x18001d666  mov     r15d, r13d
0x18001d669  lea     rdx, [rbp+57h+Handles]; pHandles
0x18001d66d  cmova   r15d, eax
0x18001d671  xor     r8d, r8d; fWaitAll
0x18001d674  mov     r9d, r15d; dwMilliseconds
0x18001d677  lea     ecx, [r8+1]; nCount
0x18001d67b  call    cs:__imp_MsgWaitForMultipleObjects
0x18001d682  nop     dword ptr [rax+rax+00h]
0x18001d687  mov     r14d, eax
0x18001d68a  cmp     eax, 1
0x18001d68d  jz      short loc_18001D6A3
0x18001d68f  cmp     eax, 102h
0x18001d694  jnz     loc_18001D7BD
0x18001d69a  cmp     r15d, r13d
0x18001d69d  jz      loc_18001D7BD
0x18001d6a3  xorps   xmm0, xmm0
0x18001d6a6  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x18001d6aa  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x18001d6ae  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x18001d6b2  test    rdi, rdi
0x18001d6b5  jz      short loc_18001D6F2
0x18001d6b7  mov     r14d, [rbp+57h+wMsgFilterMin]
0x18001d6bb  jmp     short loc_18001D6CD
0x18001d6bd  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18001d6c1  call    cs:__imp_DispatchMessageW
0x18001d6c8  nop     dword ptr [rax+rax+00h]
0x18001d6cd  mov     r9d, r14d; wMsgFilterMax
0x18001d6d0  mov     [rsp+0C0h+bAlertable], 1; wRemoveMsg
0x18001d6d8  mov     r8d, r14d; wMsgFilterMin
0x18001d6db  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18001d6df  mov     rdx, rdi; hWnd
0x18001d6e2  call    cs:__imp_PeekMessageW
0x18001d6e9  nop     dword ptr [rax+rax+00h]
0x18001d6ee  test    eax, eax
0x18001d6f0  jnz     short loc_18001D6BD
0x18001d6f2  xor     r9d, r9d; wMsgFilterMax
0x18001d6f5  mov     [rsp+0C0h+bAlertable], 0; wRemoveMsg
0x18001d6fd  xor     r8d, r8d; wMsgFilterMin
0x18001d700  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18001d704  xor     edx, edx; hWnd
0x18001d706  call    cs:__imp_PeekMessageW
0x18001d70d  nop     dword ptr [rax+rax+00h]
0x18001d712  lea     eax, [r13-1]
0x18001d716  cmp     eax, 0FFFFFFFDh
0x18001d719  ja      short loc_18001D740
0x18001d71b  call    cs:__imp_GetTickCount
0x18001d722  nop     dword ptr [rax+rax+00h]
0x18001d727  mov     ecx, r13d
0x18001d72a  mov     edx, eax
0x18001d72c  sub     edx, [rbp+57h+arg_18]
0x18001d72f  sub     ecx, edx
0x18001d731  mov     [rbp+57h+arg_18], eax
0x18001d734  mov     eax, r13d
0x18001d737  xor     r13d, r13d
0x18001d73a  cmp     edx, eax
0x18001d73c  cmovbe  r13d, ecx
0x18001d740  test    esi, esi
0x18001d742  jnz     short loc_18001D78A
0x18001d744  call    cs:__imp_GetCurrentThread
0x18001d74b  nop     dword ptr [rax+rax+00h]
0x18001d750  mov     rcx, rax; hThread
0x18001d753  call    cs:__imp_GetThreadPriority
0x18001d75a  nop     dword ptr [rax+rax+00h]
0x18001d75f  mov     [rbp+57h+nPriority], eax
0x18001d762  cmp     eax, 2
0x18001d765  jnb     short loc_18001D785
0x18001d767  call    cs:__imp_GetCurrentThread
0x18001d76e  nop     dword ptr [rax+rax+00h]
0x18001d773  mov     rcx, rax; hThread
0x18001d776  lea     edx, [rsi+2]; nPriority
0x18001d779  call    cs:__imp_SetThreadPriority
0x18001d780  nop     dword ptr [rax+rax+00h]
0x18001d785  mov     esi, 1
0x18001d78a  xor     r9d, r9d; dwMilliseconds
0x18001d78d  mov     [rsp+0C0h+bAlertable], 0; bAlertable
0x18001d795  xor     r8d, r8d; bWaitAll
0x18001d798  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18001d79c  lea     ecx, [r9+1]; nCount
0x18001d7a0  call    cs:__imp_WaitForMultipleObjectsEx
0x18001d7a7  nop     dword ptr [rax+rax+00h]
0x18001d7ac  mov     r14d, eax
0x18001d7af  cmp     eax, 1
0x18001d7b2  mov     eax, 0Ah
0x18001d7b7  jnb     loc_18001D65E
0x18001d7bd  mov     rbx, [rbp+57h+arg_0]
0x18001d7c1  test    esi, esi
0x18001d7c3  lea     rsi, [rbx+100h]
0x18001d7ca  jz      loc_18001D890
0x18001d7d0  call    cs:__imp_GetCurrentThread
0x18001d7d7  nop     dword ptr [rax+rax+00h]
0x18001d7dc  mov     edx, [rbp+57h+nPriority]; nPriority
0x18001d7df  mov     rcx, rax; hThread
0x18001d7e2  call    cs:__imp_SetThreadPriority
0x18001d7e9  nop     dword ptr [rax+rax+00h]
0x18001d7ee  mov     ecx, 8; flags
0x18001d7f3  call    cs:__imp_GetQueueStatus
0x18001d7fa  nop     dword ptr [rax+rax+00h]
0x18001d7ff  shr     eax, 10h
0x18001d802  test    al, 8
0x18001d804  jz      loc_18001D890
0x18001d80a  mov     edi, cs:wMsgFilterMax
0x18001d810  test    edi, edi
0x18001d812  jnz     short loc_18001D833
0x18001d814  lea     rcx, String; "AMUnblock"
0x18001d81b  call    cs:__imp_RegisterWindowMessageW
0x18001d822  nop     dword ptr [rax+rax+00h]
0x18001d827  mov     cs:wMsgFilterMax, eax
0x18001d82d  mov     edi, eax
0x18001d82f  test    eax, eax
0x18001d831  jz      short loc_18001D86E
0x18001d833  xorps   xmm0, xmm0
0x18001d836  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x18001d83a  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x18001d83e  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x18001d842  mov     r9d, edi; wMsgFilterMax
0x18001d845  mov     [rsp+0C0h+bAlertable], 1; wRemoveMsg
0x18001d84d  mov     r8d, edi; wMsgFilterMin
0x18001d850  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18001d854  or      rdx, 0FFFFFFFFFFFFFFFFh; hWnd
0x18001d858  call    cs:__imp_PeekMessageW
0x18001d85f  nop     dword ptr [rax+rax+00h]
0x18001d864  mov     edi, cs:wMsgFilterMax
0x18001d86a  test    eax, eax
0x18001d86c  jnz     short loc_18001D842
0x18001d86e  call    cs:__imp_GetCurrentThreadId
0x18001d875  nop     dword ptr [rax+rax+00h]
0x18001d87a  xor     r9d, r9d; lParam
0x18001d87d  xor     r8d, r8d; wParam
0x18001d880  mov     ecx, eax; idThread
0x18001d882  mov     edx, edi; Msg
0x18001d884  call    cs:__imp_PostThreadMessageW
0x18001d88b  nop     dword ptr [rax+rax+00h]
0x18001d890  mov     r15d, [rbp+57h+arg_10]
0x18001d894  mov     r12d, [rbp+57h+arg_8]
0x18001d898  test    r14d, r14d
0x18001d89b  jnz     loc_18001D972
0x18001d8a1  mov     [rbx+108h], r15d
0x18001d8a8  inc     dword ptr [rbx+10Ch]
0x18001d8ae  mov     eax, 1
0x18001d8b3  neg     eax
0x18001d8b5  lea     rdi, [rbx+288h]
0x18001d8bc  mov     rdx, [rdi]; struct IUnknown *
0x18001d8bf  sbb     rcx, rcx
0x18001d8c2  and     rcx, rsi; this
0x18001d8c5  mov     [rbp+57h+arg_0], rcx
0x18001d8c9  test    rdx, rdx
0x18001d8cc  jz      loc_18001D979
0x18001d8d2  xor     r9d, r9d; unsigned int
0x18001d8d5  lea     r8d, [r9+2]; unsigned int
0x18001d8d9  call    ?CallThroughFrameStepPropertySet@CFilterGraph@@AEAAJPEAUIUnknown@@KK@Z; CFilterGraph::CallThroughFrameStepPropertySet(IUnknown *,ulong,ulong)
0x18001d8de  mov     rcx, [rbx+0F8h]
0x18001d8e5  mov     edx, 24h ; '$'; int
0x18001d8ea  add     rcx, 328h; this
0x18001d8f1  mov     esi, eax
0x18001d8f3  call    ?ClearEvents@CEventStore@CImplMediaEvent@@QEAAXJ@Z; CImplMediaEvent::CEventStore::ClearEvents(long)
0x18001d8f8  mov     rdx, [rbx+0F8h]
0x18001d8ff  mov     rcx, rdi; struct IUnknown **
0x18001d902  mov     r8d, [rdx+0A8h]
0x18001d909  mov     rdx, [rbx+0F8h]
0x18001d910  inc     r8d
0x18001d913  mov     [rdx+0A8h], r8d
0x18001d91a  xor     edx, edx; struct IUnknown *
0x18001d91c  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001d921  cmp     r12d, 1
0x18001d925  jz      short loc_18001D94D
0x18001d927  cmp     dword ptr [rbx+298h], 1
0x18001d92e  jnz     short loc_18001D94D
0x18001d930  mov     rcx, [rbx+290h]
0x18001d937  test    rcx, rcx
0x18001d93a  jz      short loc_18001D94D
0x18001d93c  mov     rax, [rcx]
0x18001d93f  mov     edx, 80004004h
0x18001d944  mov     rax, [rax+20h]
0x18001d948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d94d  lea     rcx, [rbx+290h]; struct IUnknown **
0x18001d954  mov     dword ptr [rbx+298h], 0
0x18001d95e  xor     edx, edx; struct IUnknown *
0x18001d960  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001d965  lea     rcx, [rbp+57h+arg_0]; this
0x18001d969  call    ??1CAutoMsgMutex@@QEAA@XZ; CAutoMsgMutex::~CAutoMsgMutex(void)
0x18001d96e  mov     eax, esi
0x18001d970  jmp     short loc_18001D99C
0x18001d972  xor     eax, eax
0x18001d974  jmp     loc_18001D8B3
0x18001d979  test    rcx, rcx
0x18001d97c  jz      short loc_18001D99A
0x18001d97e  add     dword ptr [rcx+0Ch], 0FFFFFFFFh
0x18001d982  jnz     short loc_18001D99A
0x18001d984  mov     dword ptr [rcx+8], 0
0x18001d98b  mov     rcx, [rcx]; hMutex
0x18001d98e  call    cs:__imp_ReleaseMutex
0x18001d995  nop     dword ptr [rax+rax+00h]
0x18001d99a  xor     eax, eax
0x18001d99c  add     rsp, 88h
0x18001d9a3  pop     r15
0x18001d9a5  pop     r14
0x18001d9a7  pop     r13
0x18001d9a9  pop     r12
0x18001d9ab  pop     rdi
0x18001d9ac  pop     rsi
0x18001d9ad  pop     rbx
0x18001d9ae  pop     rbp
0x18001d9af  retn
```
