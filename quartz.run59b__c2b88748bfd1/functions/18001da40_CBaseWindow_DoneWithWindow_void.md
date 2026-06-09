# CBaseWindow::DoneWithWindow(void)

- ea: `0x18001da40`
- end: `0x18001de0a`
- name: `?DoneWithWindow@CBaseWindow@@UEAAJXZ`
- size: `970`
- prototype: `__int64 __fastcall(CBaseWindow *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18009c6b4`
- `0x1800aae00`
- `0x1800ab304`
- `0x1800d5d28`
- `0x1800d6050`

## callees

- `0x18001da40`
- `0x180025158`
- `0x18015e010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18001dc5d`
- `KERNEL32!GetCurrentThread` at `0x18001dc80`
- `KERNEL32!GetCurrentThread` at `0x18001dcdf`
- `KERNEL32!GetCurrentThread` at `0x18001dc5d`
- `KERNEL32!GetCurrentThread` at `0x18001dc80`
- `KERNEL32!GetCurrentThread` at `0x18001dcdf`
- `KERNEL32!GetThreadPriority` at `0x18001dc6c`
- `KERNEL32!GetThreadPriority` at `0x18001dc6c`
- `KERNEL32!GetTickCount` at `0x18001dc36`
- `KERNEL32!GetTickCount` at `0x18001dc36`
- `KERNEL32!SetThreadPriority` at `0x18001dc93`
- `KERNEL32!SetThreadPriority` at `0x18001dcf1`
- `KERNEL32!SetThreadPriority` at `0x18001dc93`
- `KERNEL32!SetThreadPriority` at `0x18001dcf1`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18001dba1`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18001dcb8`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18001dba1`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18001dcb8`
- `KERNEL32!CreateEventW` at `0x18001db33`
- `KERNEL32!CreateEventW` at `0x18001db33`
- `KERNEL32!GetCurrentThreadId` at `0x18001da8e`
- `KERNEL32!GetCurrentThreadId` at `0x18001dd7d`
- `KERNEL32!GetCurrentThreadId` at `0x18001da8e`
- `KERNEL32!GetCurrentThreadId` at `0x18001dd7d`
- `KERNEL32!CloseHandle` at `0x18001dda7`
- `KERNEL32!CloseHandle` at `0x18001dda7`
- `GDI32!DeleteDC` at `0x18001dddb`
- `GDI32!DeleteDC` at `0x18001dddb`
- `USER32!GetQueueStatus` at `0x18001dd02`
- `USER32!GetQueueStatus` at `0x18001dd02`
- `USER32!PeekMessageW` at `0x18001dc22`
- `USER32!PeekMessageW` at `0x18001dd67`
- `USER32!PeekMessageW` at `0x18001dc22`
- `USER32!PeekMessageW` at `0x18001dd67`
- `USER32!MsgWaitForMultipleObjects` at `0x18001dbda`
- `USER32!MsgWaitForMultipleObjects` at `0x18001dbda`
- `USER32!RegisterWindowMessageW` at `0x18001dd2a`
- `USER32!RegisterWindowMessageW` at `0x18001dd2a`
- `USER32!SetWindowLongW` at `0x18001dac5`
- `USER32!SetWindowLongW` at `0x18001dac5`
- `USER32!PostThreadMessageW` at `0x18001dd93`
- `USER32!PostThreadMessageW` at `0x18001dd93`
- `USER32!DestroyWindow` at `0x18001dae3`
- `USER32!DestroyWindow` at `0x18001dae3`
- `USER32!PostMessageW` at `0x18001db6e`
- `USER32!PostMessageW` at `0x18001db6e`
- `USER32!GetWindowThreadProcessId` at `0x18001da80`
- `USER32!GetWindowThreadProcessId` at `0x18001da80`
- `USER32!SendMessageW` at `0x18001ddc2`
- `USER32!SendMessageW` at `0x18001ddc2`
- `USER32!IsWindow` at `0x18001da63`
- `USER32!IsWindow` at `0x18001db08`
- `USER32!IsWindow` at `0x18001da63`
- `USER32!IsWindow` at `0x18001db08`

## pseudocode

```c
__int64 __fastcall CBaseWindow::DoneWithWindow(HWND *this)
{
  HWND *v1; // rdi
  DWORD WindowThreadProcessId; // ebx
  HWND v3; // rbx
  HANDLE EventW; // rax
  void *v5; // rbx
  unsigned int v7; // esi
  int v8; // r14d
  DWORD v9; // r13d
  unsigned int ThreadPriority; // r12d
  DWORD v11; // r15d
  DWORD v12; // eax
  DWORD TickCount; // eax
  unsigned int v14; // edx
  unsigned int v15; // ecx
  bool v16; // cc
  HANDLE CurrentThread; // rax
  HANDLE v18; // rax
  HANDLE v19; // rax
  UINT v20; // esi
  BOOL v21; // eax
  DWORD CurrentThreadId; // eax
  HDC v23; // rcx
  HANDLE Handles[2]; // [rsp+30h] [rbp-40h] BYREF
  struct tagMSG Msg; // [rsp+40h] [rbp-30h] BYREF
  HANDLE v27; // [rsp+B8h] [rbp+48h] BYREF

  v1 = this;
  if ( IsWindow(this[2])
    && (WindowThreadProcessId = GetWindowThreadProcessId(v1[2], 0), WindowThreadProcessId == GetCurrentThreadId()) )
  {
    v3 = v1[2];
    if ( v3 )
    {
      (*((void (__fastcall **)(HWND *))*v1 + 3))(v1);
      SetWindowLongW(v3, -16, *((_DWORD *)v1 + 15));
      (*((void (__fastcall **)(HWND *))*v1 + 8))(v1);
      DestroyWindow(v3);
      v1[6] = 0;
      v1[7] = 0;
      v1[8] = 0;
      *((_DWORD *)v1 + 18) = 0;
    }
  }
  else
  {
    if ( IsWindow(v1[2]) )
    {
      if ( *((_BYTE *)v1 + 148) )
      {
        EventW = CreateEventW(0, 0, 0, 0);
        v27 = EventW;
        v5 = EventW;
        if ( !EventW )
        {
          CAMEvent::~CAMEvent((CAMEvent *)&v27);
          return 2147942414LL;
        }
        PostMessageW(v1[2], ::Msg, (WPARAM)EventW, 0);
        Handles[0] = v5;
        Handles[1] = 0;
        v7 = -1;
        v8 = 0;
        v9 = 0;
        ThreadPriority = 0;
        if ( WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0) )
        {
          do
          {
            v11 = v7;
            if ( v7 > 0xA )
              v11 = 10;
            v12 = MsgWaitForMultipleObjects(1u, Handles, 0, v11, 0x40u);
            if ( v12 != 1 && (v12 != 258 || v11 == v7) )
              break;
            memset(&Msg, 0, sizeof(Msg));
            PeekMessageW(&Msg, 0, 0, 0, 0);
            if ( v7 - 1 <= 0xFFFFFFFD )
            {
              TickCount = GetTickCount();
              v14 = TickCount - v9;
              v9 = TickCount;
              v15 = v7 - v14;
              v16 = v14 <= v7;
              v7 = 0;
              if ( v16 )
                v7 = v15;
            }
            if ( !v8 )
            {
              CurrentThread = GetCurrentThread();
              ThreadPriority = GetThreadPriority(CurrentThread);
              if ( ThreadPriority < 2 )
              {
                v18 = GetCurrentThread();
                SetThreadPriority(v18, 2);
              }
              v8 = 1;
            }
          }
          while ( WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0) );
          v1 = this;
          if ( v8 )
          {
            v19 = GetCurrentThread();
            SetThreadPriority(v19, ThreadPriority);
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
              CurrentThreadId = GetCurrentThreadId();
              PostThreadMessageW(CurrentThreadId, v20, 0, 0);
            }
          }
        }
        if ( v5 )
          CloseHandle(v5);
      }
      else
      {
        SendMessageW(v1[2], ::Msg, 0, 0);
      }
    }
    v23 = (HDC)v1[10];
    v1[3] = 0;
    if ( v23 )
    {
      DeleteDC(v23);
      v1[10] = 0;
    }
    v1[2] = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18001da40  mov     [rsp-38h+arg_10], rbx
0x18001da45  mov     [rsp-38h+arg_0], rcx
0x18001da4a  push    rbp
0x18001da4b  push    rsi
0x18001da4c  push    rdi
0x18001da4d  push    r12
0x18001da4f  push    r13
0x18001da51  push    r14
0x18001da53  push    r15
0x18001da55  mov     rbp, rsp
0x18001da58  sub     rsp, 70h
0x18001da5c  mov     rdi, rcx
0x18001da5f  mov     rcx, [rcx+10h]; hWnd
0x18001da63  call    cs:__imp_IsWindow
0x18001da6a  nop     dword ptr [rax+rax+00h]
0x18001da6f  xor     r15d, r15d
0x18001da72  test    eax, eax
0x18001da74  jz      loc_18001DB04
0x18001da7a  mov     rcx, [rdi+10h]; hWnd
0x18001da7e  xor     edx, edx; lpdwProcessId
0x18001da80  call    cs:__imp_GetWindowThreadProcessId
0x18001da87  nop     dword ptr [rax+rax+00h]
0x18001da8c  mov     ebx, eax
0x18001da8e  call    cs:__imp_GetCurrentThreadId
0x18001da95  nop     dword ptr [rax+rax+00h]
0x18001da9a  cmp     ebx, eax
0x18001da9c  jnz     short loc_18001DB04
0x18001da9e  mov     rbx, [rdi+10h]
0x18001daa2  test    rbx, rbx
0x18001daa5  jz      loc_18001DDEF
0x18001daab  mov     rax, [rdi]
0x18001daae  mov     rcx, rdi
0x18001dab1  mov     rax, [rax+18h]
0x18001dab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001daba  mov     r8d, [rdi+3Ch]; dwNewLong
0x18001dabe  lea     edx, [r15-10h]; nIndex
0x18001dac2  mov     rcx, rbx; hWnd
0x18001dac5  call    cs:__imp_SetWindowLongW
0x18001dacc  nop     dword ptr [rax+rax+00h]
0x18001dad1  mov     rax, [rdi]
0x18001dad4  mov     rcx, rdi
0x18001dad7  mov     rax, [rax+40h]
0x18001dadb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dae0  mov     rcx, rbx; hWnd
0x18001dae3  call    cs:__imp_DestroyWindow
0x18001daea  nop     dword ptr [rax+rax+00h]
0x18001daef  mov     [rdi+30h], r15
0x18001daf3  mov     [rdi+38h], r15
0x18001daf7  mov     [rdi+40h], r15
0x18001dafb  mov     [rdi+48h], r15d
0x18001daff  jmp     loc_18001DDEF
0x18001db04  mov     rcx, [rdi+10h]; hWnd
0x18001db08  call    cs:__imp_IsWindow
0x18001db0f  nop     dword ptr [rax+rax+00h]
0x18001db14  test    eax, eax
0x18001db16  jz      loc_18001DDCE
0x18001db1c  xor     r9d, r9d; lParam
0x18001db1f  cmp     [rdi+94h], r15b
0x18001db26  jz      loc_18001DDB5
0x18001db2c  xor     r8d, r8d; bInitialState
0x18001db2f  xor     edx, edx; bManualReset
0x18001db31  xor     ecx, ecx; lpEventAttributes
0x18001db33  call    cs:__imp_CreateEventW
0x18001db3a  nop     dword ptr [rax+rax+00h]
0x18001db3f  mov     [rbp+arg_8], rax
0x18001db43  mov     rbx, rax
0x18001db46  test    rax, rax
0x18001db49  jnz     short loc_18001DB5E
0x18001db4b  lea     rcx, [rbp+arg_8]; this
0x18001db4f  call    ??1CAMEvent@@QEAA@XZ; CAMEvent::~CAMEvent(void)
0x18001db54  mov     eax, 8007000Eh
0x18001db59  jmp     loc_18001DDF1
0x18001db5e  mov     edx, cs:Msg; Msg
0x18001db64  xor     r9d, r9d; lParam
0x18001db67  mov     rcx, [rdi+10h]; hWnd
0x18001db6b  mov     r8, rbx; wParam
0x18001db6e  call    cs:__imp_PostMessageW
0x18001db75  nop     dword ptr [rax+rax+00h]
0x18001db7a  xor     r9d, r9d; dwMilliseconds
0x18001db7d  mov     [rbp+Handles], rbx
0x18001db81  xor     r8d, r8d; bWaitAll
0x18001db84  mov     [rbp+var_38], r15
0x18001db88  lea     rdx, [rbp+Handles]; lpHandles
0x18001db8c  mov     [rsp+70h+bAlertable], r15d; bAlertable
0x18001db91  or      esi, 0FFFFFFFFh
0x18001db94  mov     r14d, r15d
0x18001db97  lea     ecx, [r9+1]; nCount
0x18001db9b  mov     r13d, r15d
0x18001db9e  mov     r12d, r15d
0x18001dba1  call    cs:__imp_WaitForMultipleObjectsEx
0x18001dba8  nop     dword ptr [rax+rax+00h]
0x18001dbad  cmp     eax, 1
0x18001dbb0  jb      loc_18001DD9F
0x18001dbb6  mov     edi, 0Ah
0x18001dbbb  cmp     esi, edi
0x18001dbbd  mov     [rsp+70h+bAlertable], 40h ; '@'; dwWakeMask
0x18001dbc5  mov     r15d, esi
0x18001dbc8  lea     rdx, [rbp+Handles]; pHandles
0x18001dbcc  cmova   r15d, edi
0x18001dbd0  xor     r8d, r8d; fWaitAll
0x18001dbd3  mov     r9d, r15d; dwMilliseconds
0x18001dbd6  lea     ecx, [r8+1]; nCount
0x18001dbda  call    cs:__imp_MsgWaitForMultipleObjects
0x18001dbe1  nop     dword ptr [rax+rax+00h]
0x18001dbe6  cmp     eax, 1
0x18001dbe9  jz      short loc_18001DBFF
0x18001dbeb  cmp     eax, 102h
0x18001dbf0  jnz     loc_18001DCCF
0x18001dbf6  cmp     r15d, esi
0x18001dbf9  jz      loc_18001DCCF
0x18001dbff  xorps   xmm0, xmm0
0x18001dc02  lea     rcx, [rbp+Msg]; lpMsg
0x18001dc06  xor     r15d, r15d
0x18001dc09  xor     r9d, r9d; wMsgFilterMax
0x18001dc0c  xor     r8d, r8d; wMsgFilterMin
0x18001dc0f  mov     [rsp+70h+bAlertable], r15d; wRemoveMsg
0x18001dc14  xor     edx, edx; hWnd
0x18001dc16  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x18001dc1a  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x18001dc1e  movups  xmmword ptr [rbp+Msg.time], xmm0
0x18001dc22  call    cs:__imp_PeekMessageW
0x18001dc29  nop     dword ptr [rax+rax+00h]
0x18001dc2e  lea     eax, [rsi-1]
0x18001dc31  cmp     eax, 0FFFFFFFDh
0x18001dc34  ja      short loc_18001DC58
0x18001dc36  call    cs:__imp_GetTickCount
0x18001dc3d  nop     dword ptr [rax+rax+00h]
0x18001dc42  mov     ecx, esi
0x18001dc44  mov     edx, eax
0x18001dc46  sub     edx, r13d
0x18001dc49  mov     r13d, eax
0x18001dc4c  mov     eax, esi
0x18001dc4e  sub     ecx, edx
0x18001dc50  cmp     edx, eax
0x18001dc52  mov     esi, r15d
0x18001dc55  cmovbe  esi, ecx
0x18001dc58  test    r14d, r14d
0x18001dc5b  jnz     short loc_18001DCA5
0x18001dc5d  call    cs:__imp_GetCurrentThread
0x18001dc64  nop     dword ptr [rax+rax+00h]
0x18001dc69  mov     rcx, rax; hThread
0x18001dc6c  call    cs:__imp_GetThreadPriority
0x18001dc73  nop     dword ptr [rax+rax+00h]
0x18001dc78  mov     r12d, eax
0x18001dc7b  cmp     eax, 2
0x18001dc7e  jnb     short loc_18001DC9F
0x18001dc80  call    cs:__imp_GetCurrentThread
0x18001dc87  nop     dword ptr [rax+rax+00h]
0x18001dc8c  mov     rcx, rax; hThread
0x18001dc8f  lea     edx, [r14+2]; nPriority
0x18001dc93  call    cs:__imp_SetThreadPriority
0x18001dc9a  nop     dword ptr [rax+rax+00h]
0x18001dc9f  mov     r14d, 1
0x18001dca5  xor     r9d, r9d; dwMilliseconds
0x18001dca8  mov     [rsp+70h+bAlertable], r15d; bAlertable
0x18001dcad  xor     r8d, r8d; bWaitAll
0x18001dcb0  lea     rdx, [rbp+Handles]; lpHandles
0x18001dcb4  lea     ecx, [r9+1]; nCount
0x18001dcb8  call    cs:__imp_WaitForMultipleObjectsEx
0x18001dcbf  nop     dword ptr [rax+rax+00h]
0x18001dcc4  cmp     eax, 1
0x18001dcc7  jnb     loc_18001DBBB
0x18001dccd  jmp     short loc_18001DCD2
0x18001dccf  xor     r15d, r15d
0x18001dcd2  mov     rdi, [rbp+arg_0]
0x18001dcd6  test    r14d, r14d
0x18001dcd9  jz      loc_18001DD9F
0x18001dcdf  call    cs:__imp_GetCurrentThread
0x18001dce6  nop     dword ptr [rax+rax+00h]
0x18001dceb  mov     rcx, rax; hThread
0x18001dcee  mov     edx, r12d; nPriority
0x18001dcf1  call    cs:__imp_SetThreadPriority
0x18001dcf8  nop     dword ptr [rax+rax+00h]
0x18001dcfd  mov     ecx, 8; flags
0x18001dd02  call    cs:__imp_GetQueueStatus
0x18001dd09  nop     dword ptr [rax+rax+00h]
0x18001dd0e  shr     eax, 10h
0x18001dd11  test    al, 8
0x18001dd13  jz      loc_18001DD9F
0x18001dd19  mov     esi, cs:wMsgFilterMax
0x18001dd1f  test    esi, esi
0x18001dd21  jnz     short loc_18001DD42
0x18001dd23  lea     rcx, String; "AMUnblock"
0x18001dd2a  call    cs:__imp_RegisterWindowMessageW
0x18001dd31  nop     dword ptr [rax+rax+00h]
0x18001dd36  mov     cs:wMsgFilterMax, eax
0x18001dd3c  mov     esi, eax
0x18001dd3e  test    eax, eax
0x18001dd40  jz      short loc_18001DD7D
0x18001dd42  xorps   xmm0, xmm0
0x18001dd45  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x18001dd49  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x18001dd4d  movups  xmmword ptr [rbp+Msg.time], xmm0
0x18001dd51  mov     r9d, esi; wMsgFilterMax
0x18001dd54  mov     [rsp+70h+bAlertable], 1; wRemoveMsg
0x18001dd5c  mov     r8d, esi; wMsgFilterMin
0x18001dd5f  lea     rcx, [rbp+Msg]; lpMsg
0x18001dd63  or      rdx, 0FFFFFFFFFFFFFFFFh; hWnd
0x18001dd67  call    cs:__imp_PeekMessageW
0x18001dd6e  nop     dword ptr [rax+rax+00h]
0x18001dd73  mov     esi, cs:wMsgFilterMax
0x18001dd79  test    eax, eax
0x18001dd7b  jnz     short loc_18001DD51
0x18001dd7d  call    cs:__imp_GetCurrentThreadId
0x18001dd84  nop     dword ptr [rax+rax+00h]
0x18001dd89  xor     r9d, r9d; lParam
0x18001dd8c  xor     r8d, r8d; wParam
0x18001dd8f  mov     ecx, eax; idThread
0x18001dd91  mov     edx, esi; Msg
0x18001dd93  call    cs:__imp_PostThreadMessageW
0x18001dd9a  nop     dword ptr [rax+rax+00h]
0x18001dd9f  test    rbx, rbx
0x18001dda2  jz      short loc_18001DDCE
0x18001dda4  mov     rcx, rbx; hObject
0x18001dda7  call    cs:__imp_CloseHandle
0x18001ddae  nop     dword ptr [rax+rax+00h]
0x18001ddb3  jmp     short loc_18001DDCE
0x18001ddb5  mov     edx, cs:Msg; Msg
0x18001ddbb  xor     r8d, r8d; wParam
0x18001ddbe  mov     rcx, [rdi+10h]; hWnd
0x18001ddc2  call    cs:__imp_SendMessageW
0x18001ddc9  nop     dword ptr [rax+rax+00h]
0x18001ddce  mov     rcx, [rdi+50h]; hdc
0x18001ddd2  mov     [rdi+18h], r15
0x18001ddd6  test    rcx, rcx
0x18001ddd9  jz      short loc_18001DDEB
0x18001dddb  call    cs:__imp_DeleteDC
0x18001dde2  nop     dword ptr [rax+rax+00h]
0x18001dde7  mov     [rdi+50h], r15
0x18001ddeb  mov     [rdi+10h], r15
0x18001ddef  xor     eax, eax
0x18001ddf1  mov     rbx, [rsp+70h+arg_10]
0x18001ddf9  add     rsp, 70h
0x18001ddfd  pop     r15
0x18001ddff  pop     r14
0x18001de01  pop     r13
0x18001de03  pop     r12
0x18001de05  pop     rdi
0x18001de06  pop     rsi
0x18001de07  pop     rbp
0x18001de08  retn
```
