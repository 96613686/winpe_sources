# CFGControl::GetLieState(void)

- ea: `0x180001ba0`
- end: `0x180001ed7`
- name: `?GetLieState@CFGControl@@QEAA?AW4_FilterState@@XZ`
- size: `823`
- prototype: `enum _FilterState __fastcall(CFGControl *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180001750`
- `0x18006ff74`
- `0x1800752b0`
- `0x18007685c`

## callees

- `0x180001ba0`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180001d3f`
- `KERNEL32!GetCurrentThread` at `0x180001d62`
- `KERNEL32!GetCurrentThread` at `0x180001dbe`
- `KERNEL32!GetCurrentThread` at `0x180001d3f`
- `KERNEL32!GetCurrentThread` at `0x180001d62`
- `KERNEL32!GetCurrentThread` at `0x180001dbe`
- `KERNEL32!GetThreadPriority` at `0x180001d4e`
- `KERNEL32!GetThreadPriority` at `0x180001d4e`
- `KERNEL32!GetTickCount` at `0x180001d16`
- `KERNEL32!GetTickCount` at `0x180001d16`
- `KERNEL32!SetThreadPriority` at `0x180001d74`
- `KERNEL32!SetThreadPriority` at `0x180001dd0`
- `KERNEL32!SetThreadPriority` at `0x180001d74`
- `KERNEL32!SetThreadPriority` at `0x180001dd0`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180001c30`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180001d96`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180001c30`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180001d96`
- `KERNEL32!GetCurrentThreadId` at `0x180001bc8`
- `KERNEL32!GetCurrentThreadId` at `0x180001e58`
- `KERNEL32!GetCurrentThreadId` at `0x180001bc8`
- `KERNEL32!GetCurrentThreadId` at `0x180001e58`
- `KERNEL32!ReleaseMutex` at `0x180001eb0`
- `KERNEL32!ReleaseMutex` at `0x180001eb0`
- `USER32!GetQueueStatus` at `0x180001de1`
- `USER32!GetQueueStatus` at `0x180001de1`
- `USER32!DispatchMessageW` at `0x180001cc0`
- `USER32!DispatchMessageW` at `0x180001cc0`
- `USER32!PeekMessageW` at `0x180001cdd`
- `USER32!PeekMessageW` at `0x180001d01`
- `USER32!PeekMessageW` at `0x180001e42`
- `USER32!PeekMessageW` at `0x180001cdd`
- `USER32!PeekMessageW` at `0x180001d01`
- `USER32!PeekMessageW` at `0x180001e42`
- `USER32!MsgWaitForMultipleObjects` at `0x180001c7b`
- `USER32!MsgWaitForMultipleObjects` at `0x180001c7b`
- `USER32!RegisterWindowMessageW` at `0x180001e09`
- `USER32!RegisterWindowMessageW` at `0x180001e09`
- `USER32!PostThreadMessageW` at `0x180001e6e`
- `USER32!PostThreadMessageW` at `0x180001e6e`

## pseudocode

```c
__int64 __fastcall CFGControl::GetLieState(CFGControl *this)
{
  __int64 v1; // rsi
  CFGControl *v2; // r12
  int v3; // edi
  DWORD v4; // r15d
  HWND v5; // rbx
  void *v6; // rax
  unsigned int v7; // r13d
  DWORD v8; // r14d
  int v9; // esi
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
  unsigned int v23; // ebx
  int v24; // edi
  UINT wMsgFilterMin; // [rsp+34h] [rbp-35h]
  __int64 v27; // [rsp+38h] [rbp-31h]
  HANDLE Handles[2]; // [rsp+40h] [rbp-29h] BYREF
  MSG Msg; // [rsp+50h] [rbp-19h] BYREF
  DWORD CurrentThreadId; // [rsp+D8h] [rbp+6Fh]
  DWORD v32; // [rsp+E0h] [rbp+77h]
  unsigned int nPriority; // [rsp+E8h] [rbp+7Fh]

  v1 = *((_QWORD *)this + 2);
  v2 = this;
  v27 = v1;
  v3 = 1;
  CurrentThreadId = GetCurrentThreadId();
  v4 = CurrentThreadId;
  if ( CurrentThreadId != *(_DWORD *)(v1 + 8) )
  {
    wMsgFilterMin = *(_DWORD *)(v1 + 24);
    if ( CurrentThreadId == *(_DWORD *)(v1 + 28) )
      v5 = *(HWND *)(v1 + 16);
    else
      v5 = 0;
    v6 = *(void **)v1;
    nPriority = 0;
    Handles[1] = 0;
    v7 = -1;
    v32 = 0;
    Handles[0] = v6;
    v8 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
    if ( v8 )
    {
      v9 = 0;
      do
      {
        v10 = v7;
        if ( v7 > 0xA )
          v10 = 10;
        v11 = MsgWaitForMultipleObjects(1u, Handles, 0, v10, v5 != 0 ? 72 : 64);
        v8 = v11;
        if ( v11 != 1 && (v11 != 258 || v10 == v7) )
          break;
        memset(&Msg, 0, sizeof(Msg));
        if ( v5 )
        {
          while ( PeekMessageW(&Msg, v5, wMsgFilterMin, wMsgFilterMin, 1u) )
            DispatchMessageW(&Msg);
        }
        PeekMessageW(&Msg, 0, 0, 0, 0);
        if ( v7 - 1 <= 0xFFFFFFFD )
        {
          TickCount = GetTickCount();
          v13 = TickCount - v32;
          v14 = v7 - (TickCount - v32);
          v32 = TickCount;
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
      v1 = v27;
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
      v4 = CurrentThreadId;
      v2 = this;
    }
    if ( v8 )
    {
      v3 = 0;
      goto LABEL_35;
    }
    *(_DWORD *)(v1 + 8) = v4;
  }
  ++*(_DWORD *)(v1 + 12);
LABEL_35:
  v23 = *((_DWORD *)v2 + 34);
  v24 = -v3;
  if ( (v1 & -(__int64)(v24 != 0)) != 0 )
  {
    v18 = (*(_DWORD *)((v1 & -(__int64)(v24 != 0)) + 0xC))-- == 1;
    if ( v18 )
    {
      *(_DWORD *)((v1 & -(__int64)(v24 != 0)) + 8) = 0;
      ReleaseMutex(*(HANDLE *)(v1 & -(__int64)(v24 != 0)));
    }
  }
  return v23;
}

```

## disassembly

```asm
0x180001ba0  mov     [rsp-8+arg_0], rcx
0x180001ba5  push    rbp
0x180001ba6  push    rbx
0x180001ba7  push    rsi
0x180001ba8  push    rdi
0x180001ba9  push    r12
0x180001bab  push    r13
0x180001bad  push    r14
0x180001baf  push    r15
0x180001bb1  lea     rbp, [rsp-1Fh]
0x180001bb6  sub     rsp, 88h
0x180001bbd  mov     rsi, [rcx+10h]
0x180001bc1  mov     r12, rcx
0x180001bc4  mov     [rbp+57h+var_88], rsi
0x180001bc8  call    cs:__imp_GetCurrentThreadId
0x180001bcf  nop     dword ptr [rax+rax+00h]
0x180001bd4  mov     edx, [rsi+8]
0x180001bd7  mov     edi, 1
0x180001bdc  mov     [rbp+57h+arg_8], eax
0x180001bdf  mov     r15d, eax
0x180001be2  cmp     eax, edx
0x180001be4  jz      loc_180001E8B
0x180001bea  mov     eax, [rsi+18h]
0x180001bed  mov     [rbp+57h+wMsgFilterMin], eax
0x180001bf0  cmp     r15d, [rsi+1Ch]
0x180001bf4  jnz     short loc_180001BFC
0x180001bf6  mov     rbx, [rsi+10h]
0x180001bfa  jmp     short loc_180001BFE
0x180001bfc  xor     ebx, ebx
0x180001bfe  mov     rax, [rsi]
0x180001c01  xor     edx, edx
0x180001c03  mov     [rbp+57h+nPriority], edx
0x180001c06  xor     r9d, r9d; dwMilliseconds
0x180001c09  mov     [rbp+57h+var_78], rdx
0x180001c0d  xor     r8d, r8d; bWaitAll
0x180001c10  mov     [rsp+0C0h+bAlertable], edx; bAlertable
0x180001c14  mov     ecx, edi; nCount
0x180001c16  lea     rdx, [rbp+57h+Handles]; lpHandles
0x180001c1a  mov     [rbp+57h+var_90], 0
0x180001c21  or      r13d, 0FFFFFFFFh
0x180001c25  mov     [rbp+57h+arg_10], 0
0x180001c2c  mov     [rbp+57h+Handles], rax
0x180001c30  call    cs:__imp_WaitForMultipleObjectsEx
0x180001c37  nop     dword ptr [rax+rax+00h]
0x180001c3c  mov     r14d, eax
0x180001c3f  cmp     eax, edi
0x180001c41  jb      loc_180001E82
0x180001c47  mov     esi, [rbp+57h+var_90]
0x180001c4a  mov     rax, rbx
0x180001c4d  neg     rax
0x180001c50  mov     eax, 0Ah
0x180001c55  sbb     r12d, r12d
0x180001c58  and     r12d, 8
0x180001c5c  add     r12d, 40h ; '@'
0x180001c60  cmp     r13d, eax
0x180001c63  mov     [rsp+0C0h+bAlertable], r12d; dwWakeMask
0x180001c68  mov     r15d, r13d
0x180001c6b  lea     rdx, [rbp+57h+Handles]; pHandles
0x180001c6f  cmova   r15d, eax
0x180001c73  mov     ecx, edi; nCount
0x180001c75  mov     r9d, r15d; dwMilliseconds
0x180001c78  xor     r8d, r8d; fWaitAll
0x180001c7b  call    cs:__imp_MsgWaitForMultipleObjects
0x180001c82  nop     dword ptr [rax+rax+00h]
0x180001c87  mov     r14d, eax
0x180001c8a  cmp     eax, edi
0x180001c8c  jz      short loc_180001CA2
0x180001c8e  cmp     eax, 102h
0x180001c93  jnz     loc_180001DB2
0x180001c99  cmp     r15d, r13d
0x180001c9c  jz      loc_180001DB2
0x180001ca2  xorps   xmm0, xmm0
0x180001ca5  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x180001ca9  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x180001cad  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x180001cb1  test    rbx, rbx
0x180001cb4  jz      short loc_180001CED
0x180001cb6  mov     r14d, [rbp+57h+wMsgFilterMin]
0x180001cba  jmp     short loc_180001CCC
0x180001cbc  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180001cc0  call    cs:__imp_DispatchMessageW
0x180001cc7  nop     dword ptr [rax+rax+00h]
0x180001ccc  mov     r9d, r14d; wMsgFilterMax
0x180001ccf  mov     [rsp+0C0h+bAlertable], edi; wRemoveMsg
0x180001cd3  mov     r8d, r14d; wMsgFilterMin
0x180001cd6  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180001cda  mov     rdx, rbx; hWnd
0x180001cdd  call    cs:__imp_PeekMessageW
0x180001ce4  nop     dword ptr [rax+rax+00h]
0x180001ce9  test    eax, eax
0x180001ceb  jnz     short loc_180001CBC
0x180001ced  xor     r9d, r9d; wMsgFilterMax
0x180001cf0  mov     [rsp+0C0h+bAlertable], 0; wRemoveMsg
0x180001cf8  xor     r8d, r8d; wMsgFilterMin
0x180001cfb  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180001cff  xor     edx, edx; hWnd
0x180001d01  call    cs:__imp_PeekMessageW
0x180001d08  nop     dword ptr [rax+rax+00h]
0x180001d0d  lea     eax, [r13-1]
0x180001d11  cmp     eax, 0FFFFFFFDh
0x180001d14  ja      short loc_180001D3B
0x180001d16  call    cs:__imp_GetTickCount
0x180001d1d  nop     dword ptr [rax+rax+00h]
0x180001d22  mov     ecx, r13d
0x180001d25  mov     edx, eax
0x180001d27  sub     edx, [rbp+57h+arg_10]
0x180001d2a  sub     ecx, edx
0x180001d2c  mov     [rbp+57h+arg_10], eax
0x180001d2f  mov     eax, r13d
0x180001d32  xor     r13d, r13d
0x180001d35  cmp     edx, eax
0x180001d37  cmovbe  r13d, ecx
0x180001d3b  test    esi, esi
0x180001d3d  jnz     short loc_180001D82
0x180001d3f  call    cs:__imp_GetCurrentThread
0x180001d46  nop     dword ptr [rax+rax+00h]
0x180001d4b  mov     rcx, rax; hThread
0x180001d4e  call    cs:__imp_GetThreadPriority
0x180001d55  nop     dword ptr [rax+rax+00h]
0x180001d5a  mov     [rbp+57h+nPriority], eax
0x180001d5d  cmp     eax, 2
0x180001d60  jnb     short loc_180001D80
0x180001d62  call    cs:__imp_GetCurrentThread
0x180001d69  nop     dword ptr [rax+rax+00h]
0x180001d6e  mov     rcx, rax; hThread
0x180001d71  lea     edx, [rsi+2]; nPriority
0x180001d74  call    cs:__imp_SetThreadPriority
0x180001d7b  nop     dword ptr [rax+rax+00h]
0x180001d80  mov     esi, edi
0x180001d82  xor     r9d, r9d; dwMilliseconds
0x180001d85  mov     [rsp+0C0h+bAlertable], 0; bAlertable
0x180001d8d  xor     r8d, r8d; bWaitAll
0x180001d90  lea     rdx, [rbp+57h+Handles]; lpHandles
0x180001d94  mov     ecx, edi; nCount
0x180001d96  call    cs:__imp_WaitForMultipleObjectsEx
0x180001d9d  nop     dword ptr [rax+rax+00h]
0x180001da2  mov     r14d, eax
0x180001da5  cmp     eax, edi
0x180001da7  mov     eax, 0Ah
0x180001dac  jnb     loc_180001C60
0x180001db2  test    esi, esi
0x180001db4  mov     rsi, [rbp+57h+var_88]
0x180001db8  jz      loc_180001E7A
0x180001dbe  call    cs:__imp_GetCurrentThread
0x180001dc5  nop     dword ptr [rax+rax+00h]
0x180001dca  mov     edx, [rbp+57h+nPriority]; nPriority
0x180001dcd  mov     rcx, rax; hThread
0x180001dd0  call    cs:__imp_SetThreadPriority
0x180001dd7  nop     dword ptr [rax+rax+00h]
0x180001ddc  mov     ecx, 8; flags
0x180001de1  call    cs:__imp_GetQueueStatus
0x180001de8  nop     dword ptr [rax+rax+00h]
0x180001ded  shr     eax, 10h
0x180001df0  test    al, 8
0x180001df2  jz      loc_180001E7A
0x180001df8  mov     ebx, cs:wMsgFilterMax
0x180001dfe  test    ebx, ebx
0x180001e00  jnz     short loc_180001E21
0x180001e02  lea     rcx, String; "AMUnblock"
0x180001e09  call    cs:__imp_RegisterWindowMessageW
0x180001e10  nop     dword ptr [rax+rax+00h]
0x180001e15  mov     cs:wMsgFilterMax, eax
0x180001e1b  mov     ebx, eax
0x180001e1d  test    eax, eax
0x180001e1f  jz      short loc_180001E58
0x180001e21  xorps   xmm0, xmm0
0x180001e24  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x180001e28  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x180001e2c  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x180001e30  mov     r9d, ebx; wMsgFilterMax
0x180001e33  mov     [rsp+0C0h+bAlertable], edi; wRemoveMsg
0x180001e37  mov     r8d, ebx; wMsgFilterMin
0x180001e3a  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180001e3e  or      rdx, 0FFFFFFFFFFFFFFFFh; hWnd
0x180001e42  call    cs:__imp_PeekMessageW
0x180001e49  nop     dword ptr [rax+rax+00h]
0x180001e4e  mov     ebx, cs:wMsgFilterMax
0x180001e54  test    eax, eax
0x180001e56  jnz     short loc_180001E30
0x180001e58  call    cs:__imp_GetCurrentThreadId
0x180001e5f  nop     dword ptr [rax+rax+00h]
0x180001e64  xor     r9d, r9d; lParam
0x180001e67  xor     r8d, r8d; wParam
0x180001e6a  mov     ecx, eax; idThread
0x180001e6c  mov     edx, ebx; Msg
0x180001e6e  call    cs:__imp_PostThreadMessageW
0x180001e75  nop     dword ptr [rax+rax+00h]
0x180001e7a  mov     r15d, [rbp+57h+arg_8]
0x180001e7e  mov     r12, [rbp+57h+arg_0]
0x180001e82  test    r14d, r14d
0x180001e85  jnz     short loc_180001ED3
0x180001e87  mov     [rsi+8], r15d
0x180001e8b  add     [rsi+0Ch], edi
0x180001e8e  mov     ebx, [r12+88h]
0x180001e96  neg     edi
0x180001e98  sbb     rcx, rcx
0x180001e9b  and     rcx, rsi
0x180001e9e  jz      short loc_180001EBC
0x180001ea0  add     dword ptr [rcx+0Ch], 0FFFFFFFFh
0x180001ea4  jnz     short loc_180001EBC
0x180001ea6  mov     dword ptr [rcx+8], 0
0x180001ead  mov     rcx, [rcx]; hMutex
0x180001eb0  call    cs:__imp_ReleaseMutex
0x180001eb7  nop     dword ptr [rax+rax+00h]
0x180001ebc  mov     eax, ebx
0x180001ebe  add     rsp, 88h
0x180001ec5  pop     r15
0x180001ec7  pop     r14
0x180001ec9  pop     r13
0x180001ecb  pop     r12
0x180001ecd  pop     rdi
0x180001ece  pop     rsi
0x180001ecf  pop     rbx
0x180001ed0  pop     rbp
0x180001ed1  retn
0x180001ed3  xor     edi, edi
0x180001ed5  jmp     short loc_180001E8E
```
