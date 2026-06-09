# WaitDispatchingMessages(void *,ulong,HWND__ *,uint,void *)

- ea: `0x180013ea0`
- end: `0x18001419d`
- name: `?WaitDispatchingMessages@@YAKPEAXKPEAUHWND__@@I0@Z`
- size: `765`
- prototype: `unsigned int(void *, unsigned int, HWND, unsigned int, void *)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800712d0`
- `0x1800c0ae0`
- `0x180149d50`

## callees

- `0x180013ea0`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180013fc7`
- `KERNEL32!GetCurrentThread` at `0x180013fea`
- `KERNEL32!GetCurrentThread` at `0x1800140d1`
- `KERNEL32!GetCurrentThread` at `0x180013fc7`
- `KERNEL32!GetCurrentThread` at `0x180013fea`
- `KERNEL32!GetCurrentThread` at `0x1800140d1`
- `KERNEL32!GetThreadPriority` at `0x180013fd6`
- `KERNEL32!GetThreadPriority` at `0x180013fd6`
- `KERNEL32!GetTickCount` at `0x180014031`
- `KERNEL32!GetTickCount` at `0x1800140ab`
- `KERNEL32!GetTickCount` at `0x180014031`
- `KERNEL32!GetTickCount` at `0x1800140ab`
- `KERNEL32!SetThreadPriority` at `0x180013ffe`
- `KERNEL32!SetThreadPriority` at `0x1800140e3`
- `KERNEL32!SetThreadPriority` at `0x180013ffe`
- `KERNEL32!SetThreadPriority` at `0x1800140e3`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180013efe`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180013efe`
- `KERNEL32!GetCurrentThreadId` at `0x180014176`
- `KERNEL32!GetCurrentThreadId` at `0x180014176`
- `USER32!GetQueueStatus` at `0x1800140f4`
- `USER32!GetQueueStatus` at `0x1800140f4`
- `USER32!DispatchMessageW` at `0x180014074`
- `USER32!DispatchMessageW` at `0x180014074`
- `USER32!PeekMessageW` at `0x180013fa7`
- `USER32!PeekMessageW` at `0x18001405b`
- `USER32!PeekMessageW` at `0x180014096`
- `USER32!PeekMessageW` at `0x180014160`
- `USER32!PeekMessageW` at `0x180013fa7`
- `USER32!PeekMessageW` at `0x18001405b`
- `USER32!PeekMessageW` at `0x180014096`
- `USER32!PeekMessageW` at `0x180014160`
- `USER32!MsgWaitForMultipleObjects` at `0x180013f61`
- `USER32!MsgWaitForMultipleObjects` at `0x180013f61`
- `USER32!RegisterWindowMessageW` at `0x18001411c`
- `USER32!RegisterWindowMessageW` at `0x18001411c`
- `USER32!PostThreadMessageW` at `0x18001418c`
- `USER32!PostThreadMessageW` at `0x18001418c`

## pseudocode

```c
__int64 __fastcall WaitDispatchingMessages(void *a1, unsigned int a2, HWND a3, UINT a4, void *a5)
{
  int v5; // esi
  DWORD TickCount; // r12d
  unsigned int ThreadPriority; // r13d
  unsigned int v10; // ebp
  DWORD v11; // ebx
  DWORD v12; // edi
  DWORD v14; // ecx
  DWORD v15; // eax
  DWORD v16; // eax
  HANDLE CurrentThread; // rax
  HANDLE v18; // rax
  DWORD v19; // eax
  DWORD v20; // edx
  unsigned int v21; // eax
  unsigned int v22; // ecx
  HANDLE v23; // rax
  UINT v24; // ebx
  BOOL v25; // eax
  DWORD CurrentThreadId; // eax
  HANDLE Handles[2]; // [rsp+30h] [rbp-88h] BYREF
  struct tagMSG Msg; // [rsp+40h] [rbp-78h] BYREF
  DWORD v29; // [rsp+C8h] [rbp+10h]

  v5 = 0;
  Handles[0] = a1;
  TickCount = 0;
  Handles[1] = a5;
  ThreadPriority = 0;
  v10 = a2;
  if ( a2 - 1 <= 0xFFFFFFFD )
    TickCount = GetTickCount();
  v11 = (a5 != 0) + 1;
  while ( 1 )
  {
    v12 = WaitForMultipleObjectsEx(v11, Handles, 0, 0, 0);
    if ( v12 < v11 )
      break;
    v14 = v10;
    if ( v10 > 0xA )
      v14 = 10;
    v15 = 64;
    v29 = v14;
    if ( a3 )
      v15 = 72;
    v16 = MsgWaitForMultipleObjects(v11, Handles, 0, v14, v15);
    v12 = v16;
    if ( v16 != v11 && (v16 != 258 || v29 == v10) )
      break;
    memset(&Msg, 0, sizeof(Msg));
    if ( a3 && PeekMessageW(&Msg, a3, a4, a4, 1u) )
    {
      do
        DispatchMessageW(&Msg);
      while ( PeekMessageW(&Msg, a3, a4, a4, 1u) );
    }
    PeekMessageW(&Msg, 0, 0, 0, 0);
    if ( v10 - 1 <= 0xFFFFFFFD )
    {
      v19 = GetTickCount();
      v20 = v19 - TickCount;
      TickCount = v19;
      v21 = v10;
      v22 = v10 - v20;
      v10 = 0;
      if ( v20 <= v21 )
        v10 = v22;
    }
    if ( !v5 )
    {
      CurrentThread = GetCurrentThread();
      ThreadPriority = GetThreadPriority(CurrentThread);
      if ( ThreadPriority < 2 )
      {
        v18 = GetCurrentThread();
        SetThreadPriority(v18, 2);
      }
      v5 = 1;
    }
  }
  if ( v5 )
  {
    v23 = GetCurrentThread();
    SetThreadPriority(v23, ThreadPriority);
    if ( (GetQueueStatus(8u) & 0x80000) != 0 )
    {
      v24 = wMsgFilterMax;
      if ( wMsgFilterMax || (wMsgFilterMax = RegisterWindowMessageW(L"AMUnblock"), (v24 = wMsgFilterMax) != 0) )
      {
        memset(&Msg, 0, sizeof(Msg));
        do
        {
          v25 = PeekMessageW(&Msg, HWND_MESSAGE|0x2LL, v24, v24, 1u);
          v24 = wMsgFilterMax;
        }
        while ( v25 );
      }
      CurrentThreadId = GetCurrentThreadId();
      PostThreadMessageW(CurrentThreadId, v24, 0, 0);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x180013ea0  push    rbx
0x180013ea2  push    rbp
0x180013ea3  push    rsi
0x180013ea4  push    rdi
0x180013ea5  push    r12
0x180013ea7  push    r13
0x180013ea9  push    r14
0x180013eab  push    r15
0x180013ead  sub     rsp, 78h
0x180013eb1  mov     rdi, [rsp+0B8h+arg_20]
0x180013eb9  lea     eax, [rdx-1]
0x180013ebc  xor     esi, esi
0x180013ebe  mov     [rsp+0B8h+Handles], rcx
0x180013ec3  xor     r12d, r12d
0x180013ec6  mov     [rsp+0B8h+var_80], rdi
0x180013ecb  xor     r13d, r13d
0x180013ece  mov     r15d, r9d
0x180013ed1  mov     r14, r8
0x180013ed4  mov     ebp, edx
0x180013ed6  cmp     eax, 0FFFFFFFDh
0x180013ed9  jbe     loc_180014031
0x180013edf  xor     ebx, ebx
0x180013ee1  test    rdi, rdi
0x180013ee4  setnz   bl
0x180013ee7  inc     ebx
0x180013ee9  xor     r9d, r9d; dwMilliseconds
0x180013eec  mov     [rsp+0B8h+bAlertable], 0; bAlertable
0x180013ef4  xor     r8d, r8d; bWaitAll
0x180013ef7  lea     rdx, [rsp+0B8h+Handles]; lpHandles
0x180013efc  mov     ecx, ebx; nCount
0x180013efe  call    cs:__imp_WaitForMultipleObjectsEx
0x180013f05  nop     dword ptr [rax+rax+00h]
0x180013f0a  mov     edi, eax
0x180013f0c  cmp     eax, ebx
0x180013f0e  jnb     short loc_180013F2C
0x180013f10  test    esi, esi
0x180013f12  jnz     loc_1800140D1
0x180013f18  mov     eax, edi
0x180013f1a  add     rsp, 78h
0x180013f1e  pop     r15
0x180013f20  pop     r14
0x180013f22  pop     r13
0x180013f24  pop     r12
0x180013f26  pop     rdi
0x180013f27  pop     rsi
0x180013f28  pop     rbp
0x180013f29  pop     rbx
0x180013f2a  retn
0x180013f2c  mov     eax, 0Ah
0x180013f31  cmp     ebp, 0Ah
0x180013f34  mov     ecx, ebp
0x180013f36  mov     edx, 48h ; 'H'
0x180013f3b  cmova   ecx, eax
0x180013f3e  mov     eax, 40h ; '@'
0x180013f43  mov     [rsp+0B8h+arg_8], ecx
0x180013f4a  mov     r9d, ecx; dwMilliseconds
0x180013f4d  test    r14, r14
0x180013f50  mov     ecx, ebx; nCount
0x180013f52  cmovnz  eax, edx
0x180013f55  xor     r8d, r8d; fWaitAll
0x180013f58  lea     rdx, [rsp+0B8h+Handles]; pHandles
0x180013f5d  mov     [rsp+0B8h+bAlertable], eax; dwWakeMask
0x180013f61  call    cs:__imp_MsgWaitForMultipleObjects
0x180013f68  nop     dword ptr [rax+rax+00h]
0x180013f6d  mov     edi, eax
0x180013f6f  cmp     eax, ebx
0x180013f71  jnz     loc_180014014
0x180013f77  xorps   xmm0, xmm0
0x180013f7a  movups  xmmword ptr [rsp+0B8h+Msg.hwnd], xmm0
0x180013f7f  movups  xmmword ptr [rsp+0B8h+Msg.wParam], xmm0
0x180013f84  movups  xmmword ptr [rsp+0B8h+Msg.time], xmm0
0x180013f89  test    r14, r14
0x180013f8c  jnz     loc_180014045
0x180013f92  xor     r9d, r9d; wMsgFilterMax
0x180013f95  mov     [rsp+0B8h+bAlertable], 0; wRemoveMsg
0x180013f9d  xor     r8d, r8d; wMsgFilterMin
0x180013fa0  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x180013fa5  xor     edx, edx; hWnd
0x180013fa7  call    cs:__imp_PeekMessageW
0x180013fae  nop     dword ptr [rax+rax+00h]
0x180013fb3  lea     eax, [rbp-1]
0x180013fb6  cmp     eax, 0FFFFFFFDh
0x180013fb9  jbe     loc_1800140AB
0x180013fbf  test    esi, esi
0x180013fc1  jnz     loc_180013EE9
0x180013fc7  call    cs:__imp_GetCurrentThread
0x180013fce  nop     dword ptr [rax+rax+00h]
0x180013fd3  mov     rcx, rax; hThread
0x180013fd6  call    cs:__imp_GetThreadPriority
0x180013fdd  nop     dword ptr [rax+rax+00h]
0x180013fe2  mov     r13d, eax
0x180013fe5  cmp     eax, 2
0x180013fe8  jnb     short loc_18001400A
0x180013fea  call    cs:__imp_GetCurrentThread
0x180013ff1  nop     dword ptr [rax+rax+00h]
0x180013ff6  mov     rcx, rax; hThread
0x180013ff9  mov     edx, 2; nPriority
0x180013ffe  call    cs:__imp_SetThreadPriority
0x180014005  nop     dword ptr [rax+rax+00h]
0x18001400a  mov     esi, 1
0x18001400f  jmp     loc_180013EE9
0x180014014  cmp     eax, 102h
0x180014019  jnz     loc_180013F10
0x18001401f  cmp     [rsp+0B8h+arg_8], ebp
0x180014026  jz      loc_180013F10
0x18001402c  jmp     loc_180013F77
0x180014031  call    cs:__imp_GetTickCount
0x180014038  nop     dword ptr [rax+rax+00h]
0x18001403d  mov     r12d, eax
0x180014040  jmp     loc_180013EDF
0x180014045  mov     r9d, r15d; wMsgFilterMax
0x180014048  mov     [rsp+0B8h+bAlertable], 1; wRemoveMsg
0x180014050  mov     r8d, r15d; wMsgFilterMin
0x180014053  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x180014058  mov     rdx, r14; hWnd
0x18001405b  call    cs:__imp_PeekMessageW
0x180014062  nop     dword ptr [rax+rax+00h]
0x180014067  test    eax, eax
0x180014069  jz      loc_180013F92
0x18001406f  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x180014074  call    cs:__imp_DispatchMessageW
0x18001407b  nop     dword ptr [rax+rax+00h]
0x180014080  mov     r9d, r15d; wMsgFilterMax
0x180014083  mov     [rsp+0B8h+bAlertable], 1; wRemoveMsg
0x18001408b  mov     r8d, r15d; wMsgFilterMin
0x18001408e  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x180014093  mov     rdx, r14; hWnd
0x180014096  call    cs:__imp_PeekMessageW
0x18001409d  nop     dword ptr [rax+rax+00h]
0x1800140a2  test    eax, eax
0x1800140a4  jnz     short loc_18001406F
0x1800140a6  jmp     loc_180013F92
0x1800140ab  call    cs:__imp_GetTickCount
0x1800140b2  nop     dword ptr [rax+rax+00h]
0x1800140b7  mov     ecx, ebp
0x1800140b9  mov     edx, eax
0x1800140bb  sub     edx, r12d
0x1800140be  mov     r12d, eax
0x1800140c1  mov     eax, ebp
0x1800140c3  sub     ecx, edx
0x1800140c5  xor     ebp, ebp
0x1800140c7  cmp     edx, eax
0x1800140c9  cmovbe  ebp, ecx
0x1800140cc  jmp     loc_180013FBF
0x1800140d1  call    cs:__imp_GetCurrentThread
0x1800140d8  nop     dword ptr [rax+rax+00h]
0x1800140dd  mov     rcx, rax; hThread
0x1800140e0  mov     edx, r13d; nPriority
0x1800140e3  call    cs:__imp_SetThreadPriority
0x1800140ea  nop     dword ptr [rax+rax+00h]
0x1800140ef  mov     ecx, 8; flags
0x1800140f4  call    cs:__imp_GetQueueStatus
0x1800140fb  nop     dword ptr [rax+rax+00h]
0x180014100  shr     eax, 10h
0x180014103  test    al, 8
0x180014105  jz      loc_180013F18
0x18001410b  mov     ebx, cs:wMsgFilterMax
0x180014111  test    ebx, ebx
0x180014113  jnz     short loc_180014134
0x180014115  lea     rcx, String; "AMUnblock"
0x18001411c  call    cs:__imp_RegisterWindowMessageW
0x180014123  nop     dword ptr [rax+rax+00h]
0x180014128  mov     cs:wMsgFilterMax, eax
0x18001412e  mov     ebx, eax
0x180014130  test    eax, eax
0x180014132  jz      short loc_180014176
0x180014134  xorps   xmm0, xmm0
0x180014137  movups  xmmword ptr [rsp+0B8h+Msg.hwnd], xmm0
0x18001413c  movups  xmmword ptr [rsp+0B8h+Msg.wParam], xmm0
0x180014141  movups  xmmword ptr [rsp+0B8h+Msg.time], xmm0
0x180014146  mov     r9d, ebx; wMsgFilterMax
0x180014149  mov     [rsp+0B8h+bAlertable], 1; wRemoveMsg
0x180014151  mov     r8d, ebx; wMsgFilterMin
0x180014154  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x180014159  mov     rdx, 0FFFFFFFFFFFFFFFFh; hWnd
0x180014160  call    cs:__imp_PeekMessageW
0x180014167  nop     dword ptr [rax+rax+00h]
0x18001416c  mov     ebx, cs:wMsgFilterMax
0x180014172  test    eax, eax
0x180014174  jnz     short loc_180014146
0x180014176  call    cs:__imp_GetCurrentThreadId
0x18001417d  nop     dword ptr [rax+rax+00h]
0x180014182  xor     r9d, r9d; lParam
0x180014185  xor     r8d, r8d; wParam
0x180014188  mov     ecx, eax; idThread
0x18001418a  mov     edx, ebx; Msg
0x18001418c  call    cs:__imp_PostThreadMessageW
0x180014193  nop     dword ptr [rax+rax+00h]
0x180014198  jmp     loc_180013F18
```
