# CFGControl::CImplMediaSeeking::IsFormatSupported(_GUID const *)

- ea: `0x18000c680`
- end: `0x18000cb3f`
- name: `?IsFormatSupported@CImplMediaSeeking@CFGControl@@UEAAJPEBU_GUID@@@Z`
- size: `1215`
- prototype: `__int64 __fastcall(CFGControl::CImplMediaSeeking *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x18000c680`
- `0x18000cb50`
- `0x18015e010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18000c8ce`
- `KERNEL32!GetCurrentThread` at `0x18000cac1`
- `KERNEL32!GetCurrentThread` at `0x18000cae8`
- `KERNEL32!GetCurrentThread` at `0x18000c8ce`
- `KERNEL32!GetCurrentThread` at `0x18000cac1`
- `KERNEL32!GetCurrentThread` at `0x18000cae8`
- `KERNEL32!GetThreadPriority` at `0x18000cad0`
- `KERNEL32!GetThreadPriority` at `0x18000cad0`
- `KERNEL32!GetTickCount` at `0x18000ca9d`
- `KERNEL32!GetTickCount` at `0x18000ca9d`
- `KERNEL32!SetThreadPriority` at `0x18000c8e4`
- `KERNEL32!SetThreadPriority` at `0x18000cafc`
- `KERNEL32!SetThreadPriority` at `0x18000c8e4`
- `KERNEL32!SetThreadPriority` at `0x18000cafc`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000c77f`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000ca08`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000c77f`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000ca08`
- `KERNEL32!GetCurrentThreadId` at `0x18000c6af`
- `KERNEL32!GetCurrentThreadId` at `0x18000c97b`
- `KERNEL32!GetCurrentThreadId` at `0x18000c6af`
- `KERNEL32!GetCurrentThreadId` at `0x18000c97b`
- `KERNEL32!ReleaseMutex` at `0x18000c835`
- `KERNEL32!ReleaseMutex` at `0x18000c835`
- `USER32!GetQueueStatus` at `0x18000c8f5`
- `USER32!GetQueueStatus` at `0x18000c8f5`
- `USER32!DispatchMessageW` at `0x18000ca66`
- `USER32!DispatchMessageW` at `0x18000ca66`
- `USER32!PeekMessageW` at `0x18000c964`
- `USER32!PeekMessageW` at `0x18000c9cf`
- `USER32!PeekMessageW` at `0x18000ca4d`
- `USER32!PeekMessageW` at `0x18000ca88`
- `USER32!PeekMessageW` at `0x18000c964`
- `USER32!PeekMessageW` at `0x18000c9cf`
- `USER32!PeekMessageW` at `0x18000ca4d`
- `USER32!PeekMessageW` at `0x18000ca88`
- `USER32!MsgWaitForMultipleObjects` at `0x18000c889`
- `USER32!MsgWaitForMultipleObjects` at `0x18000c889`
- `USER32!RegisterWindowMessageW` at `0x18000c91f`
- `USER32!RegisterWindowMessageW` at `0x18000c91f`
- `USER32!PostThreadMessageW` at `0x18000c992`
- `USER32!PostThreadMessageW` at `0x18000c992`

## pseudocode

```c
__int64 __fastcall CFGControl::CImplMediaSeeking::IsFormatSupported(
        CFGControl::CImplMediaSeeking *this,
        const struct _GUID *a2)
{
  const struct _GUID *v2; // rbp
  CFGControl::CImplMediaSeeking *v3; // rdi
  __int64 v4; // rbx
  DWORD CurrentThreadId; // eax
  DWORD v6; // esi
  int v7; // ecx
  __int64 v8; // rdi
  int updated; // esi
  UINT v11; // r12d
  HWND v12; // r15
  int v13; // r13d
  DWORD v14; // r14d
  __int64 v15; // rcx
  __int64 v16; // rdi
  HANDLE v18; // rcx
  unsigned int v19; // ebp
  DWORD v20; // ebx
  DWORD v21; // edi
  DWORD v22; // esi
  DWORD v23; // eax
  HANDLE v24; // rax
  UINT v25; // r15d
  BOOL v26; // eax
  DWORD v27; // eax
  DWORD TickCount; // eax
  unsigned int v29; // edx
  unsigned int v30; // eax
  unsigned int v31; // ecx
  HANDLE CurrentThread; // rax
  HANDLE v33; // rax
  DWORD v34; // [rsp+34h] [rbp-94h]
  __int64 v35; // [rsp+38h] [rbp-90h]
  HANDLE Handles[2]; // [rsp+40h] [rbp-88h] BYREF
  struct tagMSG Msg; // [rsp+50h] [rbp-78h] BYREF
  unsigned int nPriority; // [rsp+E0h] [rbp+18h]

  v2 = a2;
  v3 = this;
  v4 = *(_QWORD *)(*((_QWORD *)this + 4) + 16LL);
  v35 = v4;
  CurrentThreadId = GetCurrentThreadId();
  v6 = CurrentThreadId;
  v34 = CurrentThreadId;
  if ( CurrentThreadId == *(_DWORD *)(v4 + 8) )
    goto LABEL_2;
  v11 = *(_DWORD *)(v4 + 24);
  if ( CurrentThreadId == *(_DWORD *)(v4 + 28) )
    v12 = *(HWND *)(v4 + 16);
  else
    v12 = 0;
  v13 = 0;
  Handles[0] = *(HANDLE *)v4;
  nPriority = 0;
  Handles[1] = 0;
  v14 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
  if ( v14 )
  {
    v19 = -1;
    v20 = 64;
    v21 = 0;
    if ( v12 )
      v20 = 72;
    do
    {
      v22 = v19;
      if ( v19 > 0xA )
        v22 = 10;
      v23 = MsgWaitForMultipleObjects(1u, Handles, 0, v22, v20);
      v14 = v23;
      if ( v23 != 1 && (v23 != 258 || v22 == v19) )
        break;
      memset(&Msg, 0, sizeof(Msg));
      if ( v12 && PeekMessageW(&Msg, v12, v11, v11, 1u) )
      {
        do
          DispatchMessageW(&Msg);
        while ( PeekMessageW(&Msg, v12, v11, v11, 1u) );
      }
      PeekMessageW(&Msg, 0, 0, 0, 0);
      if ( v19 - 1 <= 0xFFFFFFFD )
      {
        TickCount = GetTickCount();
        v29 = TickCount - v21;
        v21 = TickCount;
        v30 = v19;
        v31 = v19 - v29;
        v19 = 0;
        if ( v29 <= v30 )
          v19 = v31;
      }
      if ( !v13 )
      {
        CurrentThread = GetCurrentThread();
        nPriority = GetThreadPriority(CurrentThread);
        if ( nPriority < 2 )
        {
          v33 = GetCurrentThread();
          SetThreadPriority(v33, 2);
        }
        v13 = 1;
      }
      v14 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
    }
    while ( v14 );
    v4 = v35;
    v3 = this;
    v6 = v34;
    v2 = a2;
    if ( v13 )
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
  if ( !v14 )
  {
    *(_DWORD *)(v4 + 8) = v6;
LABEL_2:
    ++*(_DWORD *)(v4 + 12);
    v7 = 1;
    goto LABEL_3;
  }
  v7 = 0;
LABEL_3:
  v8 = *((_QWORD *)v3 + 4);
  if ( !v7 )
    v4 = 0;
  updated = CFGControl::UpdateLists((void **)v8);
  if ( updated >= 0 )
  {
    if ( *(int *)(v8 + 304) < 1 )
    {
      updated = -2147467263;
    }
    else
    {
      v15 = *(_QWORD *)(v8 + 288);
      updated = 1;
      if ( v15 )
      {
        while ( updated )
        {
          if ( !v15 )
          {
            updated = (*(__int64 (__fastcall **)(_QWORD, const struct _GUID *))(MEMORY[0] + 40LL))(0, v2);
            break;
          }
          v16 = *(_QWORD *)(v15 + 8);
          updated = (*(__int64 (__fastcall **)(_QWORD, const struct _GUID *))(**(_QWORD **)(v15 + 16) + 40LL))(
                      *(_QWORD *)(v15 + 16),
                      v2);
          v15 = v16;
          if ( !v16 )
            break;
        }
      }
    }
  }
  if ( v4 )
  {
    if ( (*(_DWORD *)(v4 + 12))-- == 1 )
    {
      v18 = *(HANDLE *)v4;
      *(_DWORD *)(v4 + 8) = 0;
      ReleaseMutex(v18);
    }
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000c680  mov     rax, rsp
0x18000c683  mov     [rax+10h], rdx
0x18000c687  mov     [rax+8], rcx
0x18000c68b  push    rbx
0x18000c68c  push    rsi
0x18000c68d  sub     rsp, 0B8h
0x18000c694  mov     rbx, [rcx+20h]
0x18000c698  mov     [rax-18h], rbp
0x18000c69c  mov     rbp, rdx
0x18000c69f  mov     [rax-20h], rdi
0x18000c6a3  mov     rdi, rcx
0x18000c6a6  mov     rbx, [rbx+10h]
0x18000c6aa  mov     [rsp+0C8h+var_90], rbx
0x18000c6af  call    cs:__imp_GetCurrentThreadId
0x18000c6b6  nop     dword ptr [rax+rax+00h]
0x18000c6bb  mov     r8d, [rbx+8]
0x18000c6bf  mov     esi, eax
0x18000c6c1  mov     [rsp+0C8h+var_94], eax
0x18000c6c5  cmp     eax, r8d
0x18000c6c8  jnz     short loc_18000C716
0x18000c6ca  inc     dword ptr [rbx+0Ch]
0x18000c6cd  mov     ecx, 1
0x18000c6d2  mov     rdi, [rdi+20h]
0x18000c6d6  xor     eax, eax
0x18000c6d8  test    ecx, ecx
0x18000c6da  mov     rcx, rdi; this
0x18000c6dd  cmovz   rbx, rax
0x18000c6e1  call    ?UpdateLists@CFGControl@@QEAAJXZ; CFGControl::UpdateLists(void)
0x18000c6e6  mov     esi, eax
0x18000c6e8  test    eax, eax
0x18000c6ea  jns     loc_18000C7C7
0x18000c6f0  mov     rdi, [rsp+0C8h+var_20]
0x18000c6f8  mov     rbp, [rsp+0C8h+var_18]
0x18000c700  test    rbx, rbx
0x18000c703  jnz     loc_18000C821
0x18000c709  mov     eax, esi
0x18000c70b  add     rsp, 0B8h
0x18000c712  pop     rsi
0x18000c713  pop     rbx
0x18000c714  retn
0x18000c716  mov     [rsp+0C8h+var_28], r12
0x18000c71e  mov     r12d, [rbx+18h]
0x18000c722  mov     [rsp+0C8h+var_30], r13
0x18000c72a  mov     [rsp+0C8h+var_38], r14
0x18000c732  mov     [rsp+0C8h+var_40], r15
0x18000c73a  cmp     eax, [rbx+1Ch]
0x18000c73d  jnz     loc_18000C846
0x18000c743  mov     r15, [rbx+10h]
0x18000c747  mov     rax, [rbx]
0x18000c74a  lea     rdx, [rsp+0C8h+Handles]; lpHandles
0x18000c74f  xor     r13d, r13d
0x18000c752  mov     [rsp+0C8h+Handles], rax
0x18000c757  xor     r9d, r9d; dwMilliseconds
0x18000c75a  mov     [rsp+0C8h+nPriority], r13d
0x18000c762  xor     r8d, r8d; bWaitAll
0x18000c765  mov     [rsp+0C8h+var_80], r13
0x18000c76a  mov     ecx, 1; nCount
0x18000c76f  mov     [rsp+0C8h+bAlertable], r13d; bAlertable
0x18000c774  mov     [rsp+0C8h+arg_18], 0FFFFFFFFh
0x18000c77f  call    cs:__imp_WaitForMultipleObjectsEx
0x18000c786  nop     dword ptr [rax+rax+00h]
0x18000c78b  mov     r14d, eax
0x18000c78e  cmp     eax, 1
0x18000c791  jnb     loc_18000C84E
0x18000c797  mov     r15, [rsp+0C8h+var_40]
0x18000c79f  test    r14d, r14d
0x18000c7a2  mov     r14, [rsp+0C8h+var_38]
0x18000c7aa  mov     r13, [rsp+0C8h+var_30]
0x18000c7b2  mov     r12, [rsp+0C8h+var_28]
0x18000c7ba  jz      loc_18000CB13
0x18000c7c0  xor     ecx, ecx
0x18000c7c2  jmp     loc_18000C6D2
0x18000c7c7  cmp     dword ptr [rdi+130h], 1
0x18000c7ce  jl      loc_18000CB1B
0x18000c7d4  mov     rcx, [rdi+120h]
0x18000c7db  mov     esi, 1
0x18000c7e0  test    rcx, rcx
0x18000c7e3  jz      loc_18000C6F0
0x18000c7e9  test    esi, esi
0x18000c7eb  jz      loc_18000C6F0
0x18000c7f1  mov     rdx, rbp
0x18000c7f4  test    rcx, rcx
0x18000c7f7  jz      loc_18000CB25
0x18000c7fd  mov     rdi, [rcx+8]
0x18000c801  mov     rcx, [rcx+10h]
0x18000c805  mov     rax, [rcx]
0x18000c808  mov     rax, [rax+28h]
0x18000c80c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c811  mov     esi, eax
0x18000c813  mov     rcx, rdi
0x18000c816  test    rdi, rdi
0x18000c819  jz      loc_18000C6F0
0x18000c81f  jmp     short loc_18000C7E9
0x18000c821  add     dword ptr [rbx+0Ch], 0FFFFFFFFh
0x18000c825  jnz     loc_18000C709
0x18000c82b  mov     rcx, [rbx]; hMutex
0x18000c82e  mov     dword ptr [rbx+8], 0
0x18000c835  call    cs:__imp_ReleaseMutex
0x18000c83c  nop     dword ptr [rax+rax+00h]
0x18000c841  jmp     loc_18000C709
0x18000c846  xor     r15d, r15d
0x18000c849  jmp     loc_18000C747
0x18000c84e  mov     ebp, [rsp+0C8h+arg_18]
0x18000c855  mov     eax, 48h ; 'H'
0x18000c85a  test    r15, r15
0x18000c85d  mov     ebx, 40h ; '@'
0x18000c862  mov     edi, r13d
0x18000c865  cmovnz  ebx, eax
0x18000c868  mov     eax, 0Ah
0x18000c86d  cmp     ebp, 0Ah
0x18000c870  mov     [rsp+0C8h+bAlertable], ebx; dwWakeMask
0x18000c874  mov     esi, ebp
0x18000c876  lea     rdx, [rsp+0C8h+Handles]; pHandles
0x18000c87b  cmova   esi, eax
0x18000c87e  mov     ecx, 1; nCount
0x18000c883  mov     r9d, esi; dwMilliseconds
0x18000c886  xor     r8d, r8d; fWaitAll
0x18000c889  call    cs:__imp_MsgWaitForMultipleObjects
0x18000c890  nop     dword ptr [rax+rax+00h]
0x18000c895  mov     r14d, eax
0x18000c898  cmp     eax, 1
0x18000c89b  jz      loc_18000C9A3
0x18000c8a1  cmp     eax, 102h
0x18000c8a6  jz      loc_18000CA2A
0x18000c8ac  mov     rbx, [rsp+0C8h+var_90]
0x18000c8b1  mov     rdi, [rsp+0C8h+arg_0]
0x18000c8b9  mov     esi, [rsp+0C8h+var_94]
0x18000c8bd  mov     rbp, [rsp+0C8h+arg_8]
0x18000c8c5  test    r13d, r13d
0x18000c8c8  jz      loc_18000C797
0x18000c8ce  call    cs:__imp_GetCurrentThread
0x18000c8d5  nop     dword ptr [rax+rax+00h]
0x18000c8da  mov     edx, [rsp+0C8h+nPriority]; nPriority
0x18000c8e1  mov     rcx, rax; hThread
0x18000c8e4  call    cs:__imp_SetThreadPriority
0x18000c8eb  nop     dword ptr [rax+rax+00h]
0x18000c8f0  mov     ecx, 8; flags
0x18000c8f5  call    cs:__imp_GetQueueStatus
0x18000c8fc  nop     dword ptr [rax+rax+00h]
0x18000c901  shr     eax, 10h
0x18000c904  test    al, 8
0x18000c906  jz      loc_18000C797
0x18000c90c  mov     r15d, cs:wMsgFilterMax
0x18000c913  test    r15d, r15d
0x18000c916  jnz     short loc_18000C938
0x18000c918  lea     rcx, String; "AMUnblock"
0x18000c91f  call    cs:__imp_RegisterWindowMessageW
0x18000c926  nop     dword ptr [rax+rax+00h]
0x18000c92b  mov     cs:wMsgFilterMax, eax
0x18000c931  mov     r15d, eax
0x18000c934  test    eax, eax
0x18000c936  jz      short loc_18000C97B
0x18000c938  xorps   xmm0, xmm0
0x18000c93b  movups  xmmword ptr [rsp+0C8h+Msg.hwnd], xmm0
0x18000c940  movups  xmmword ptr [rsp+0C8h+Msg.wParam], xmm0
0x18000c945  movups  xmmword ptr [rsp+0C8h+Msg.time], xmm0
0x18000c94a  mov     r9d, r15d; wMsgFilterMax
0x18000c94d  mov     [rsp+0C8h+bAlertable], 1; wRemoveMsg
0x18000c955  mov     r8d, r15d; wMsgFilterMin
0x18000c958  lea     rcx, [rsp+0C8h+Msg]; lpMsg
0x18000c95d  mov     rdx, 0FFFFFFFFFFFFFFFFh; hWnd
0x18000c964  call    cs:__imp_PeekMessageW
0x18000c96b  nop     dword ptr [rax+rax+00h]
0x18000c970  mov     r15d, cs:wMsgFilterMax
0x18000c977  test    eax, eax
0x18000c979  jnz     short loc_18000C94A
0x18000c97b  call    cs:__imp_GetCurrentThreadId
0x18000c982  nop     dword ptr [rax+rax+00h]
0x18000c987  xor     r9d, r9d; lParam
0x18000c98a  xor     r8d, r8d; wParam
0x18000c98d  mov     ecx, eax; idThread
0x18000c98f  mov     edx, r15d; Msg
0x18000c992  call    cs:__imp_PostThreadMessageW
0x18000c999  nop     dword ptr [rax+rax+00h]
0x18000c99e  jmp     loc_18000C797
0x18000c9a3  xorps   xmm0, xmm0
0x18000c9a6  movups  xmmword ptr [rsp+0C8h+Msg.hwnd], xmm0
0x18000c9ab  movups  xmmword ptr [rsp+0C8h+Msg.wParam], xmm0
0x18000c9b0  movups  xmmword ptr [rsp+0C8h+Msg.time], xmm0
0x18000c9b5  test    r15, r15
0x18000c9b8  jnz     short loc_18000CA37
0x18000c9ba  xor     r9d, r9d; wMsgFilterMax
0x18000c9bd  mov     [rsp+0C8h+bAlertable], 0; wRemoveMsg
0x18000c9c5  xor     r8d, r8d; wMsgFilterMin
0x18000c9c8  lea     rcx, [rsp+0C8h+Msg]; lpMsg
0x18000c9cd  xor     edx, edx; hWnd
0x18000c9cf  call    cs:__imp_PeekMessageW
0x18000c9d6  nop     dword ptr [rax+rax+00h]
0x18000c9db  lea     eax, [rbp-1]
0x18000c9de  cmp     eax, 0FFFFFFFDh
0x18000c9e1  jbe     loc_18000CA9D
0x18000c9e7  test    r13d, r13d
0x18000c9ea  jz      loc_18000CAC1
0x18000c9f0  xor     r9d, r9d; dwMilliseconds
0x18000c9f3  mov     [rsp+0C8h+bAlertable], 0; bAlertable
0x18000c9fb  xor     r8d, r8d; bWaitAll
0x18000c9fe  lea     rdx, [rsp+0C8h+Handles]; lpHandles
0x18000ca03  mov     ecx, 1; nCount
0x18000ca08  call    cs:__imp_WaitForMultipleObjectsEx
0x18000ca0f  nop     dword ptr [rax+rax+00h]
0x18000ca14  mov     r14d, eax
0x18000ca17  cmp     eax, 1
0x18000ca1a  mov     eax, 0Ah
0x18000ca1f  jnb     loc_18000C86D
0x18000ca25  jmp     loc_18000C8AC
0x18000ca2a  cmp     esi, ebp
0x18000ca2c  jz      loc_18000C8AC
0x18000ca32  jmp     loc_18000C9A3
0x18000ca37  mov     r9d, r12d; wMsgFilterMax
0x18000ca3a  mov     [rsp+0C8h+bAlertable], 1; wRemoveMsg
0x18000ca42  mov     r8d, r12d; wMsgFilterMin
0x18000ca45  lea     rcx, [rsp+0C8h+Msg]; lpMsg
0x18000ca4a  mov     rdx, r15; hWnd
0x18000ca4d  call    cs:__imp_PeekMessageW
0x18000ca54  nop     dword ptr [rax+rax+00h]
0x18000ca59  test    eax, eax
0x18000ca5b  jz      loc_18000C9BA
0x18000ca61  lea     rcx, [rsp+0C8h+Msg]; lpMsg
0x18000ca66  call    cs:__imp_DispatchMessageW
0x18000ca6d  nop     dword ptr [rax+rax+00h]
0x18000ca72  mov     r9d, r12d; wMsgFilterMax
0x18000ca75  mov     [rsp+0C8h+bAlertable], 1; wRemoveMsg
0x18000ca7d  mov     r8d, r12d; wMsgFilterMin
0x18000ca80  lea     rcx, [rsp+0C8h+Msg]; lpMsg
0x18000ca85  mov     rdx, r15; hWnd
0x18000ca88  call    cs:__imp_PeekMessageW
0x18000ca8f  nop     dword ptr [rax+rax+00h]
0x18000ca94  test    eax, eax
0x18000ca96  jnz     short loc_18000CA61
0x18000ca98  jmp     loc_18000C9BA
0x18000ca9d  call    cs:__imp_GetTickCount
0x18000caa4  nop     dword ptr [rax+rax+00h]
0x18000caa9  mov     ecx, ebp
0x18000caab  mov     edx, eax
0x18000caad  sub     edx, edi
0x18000caaf  mov     edi, eax
0x18000cab1  mov     eax, ebp
0x18000cab3  sub     ecx, edx
0x18000cab5  xor     ebp, ebp
0x18000cab7  cmp     edx, eax
0x18000cab9  cmovbe  ebp, ecx
0x18000cabc  jmp     loc_18000C9E7
0x18000cac1  call    cs:__imp_GetCurrentThread
0x18000cac8  nop     dword ptr [rax+rax+00h]
0x18000cacd  mov     rcx, rax; hThread
0x18000cad0  call    cs:__imp_GetThreadPriority
0x18000cad7  nop     dword ptr [rax+rax+00h]
0x18000cadc  mov     [rsp+0C8h+nPriority], eax
0x18000cae3  cmp     eax, 2
0x18000cae6  jnb     short loc_18000CB08
0x18000cae8  call    cs:__imp_GetCurrentThread
0x18000caef  nop     dword ptr [rax+rax+00h]
0x18000caf4  mov     rcx, rax; hThread
0x18000caf7  mov     edx, 2; nPriority
0x18000cafc  call    cs:__imp_SetThreadPriority
0x18000cb03  nop     dword ptr [rax+rax+00h]
0x18000cb08  mov     r13d, 1
0x18000cb0e  jmp     loc_18000C9F0
0x18000cb13  mov     [rbx+8], esi
0x18000cb16  jmp     loc_18000C6CA
0x18000cb1b  mov     esi, 80004001h
0x18000cb20  jmp     loc_18000C6F0
0x18000cb25  mov     rax, ds:0
0x18000cb2d  xor     ecx, ecx
0x18000cb2f  mov     rax, [rax+28h]
0x18000cb33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb38  mov     esi, eax
0x18000cb3a  jmp     loc_18000C6F0
```
