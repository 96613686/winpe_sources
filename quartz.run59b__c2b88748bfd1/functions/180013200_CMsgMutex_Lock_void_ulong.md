# CMsgMutex::Lock(void *,ulong)

- ea: `0x180013200`
- end: `0x1800135aa`
- name: `?Lock@CMsgMutex@@QEAAHPEAXK@Z`
- size: `938`
- prototype: `__int64 __fastcall(CMsgMutex *__hidden this, void *, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180001ee0`
- `0x18006dc20`
- `0x18006dfe0`
- `0x18006e060`

## callees

- `0x180013200`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x1800133c8`
- `KERNEL32!GetCurrentThread` at `0x1800133ec`
- `KERNEL32!GetCurrentThread` at `0x1800134d5`
- `KERNEL32!GetCurrentThread` at `0x1800133c8`
- `KERNEL32!GetCurrentThread` at `0x1800133ec`
- `KERNEL32!GetCurrentThread` at `0x1800134d5`
- `KERNEL32!GetThreadPriority` at `0x1800133d7`
- `KERNEL32!GetThreadPriority` at `0x1800133d7`
- `KERNEL32!GetTickCount` at `0x180013431`
- `KERNEL32!GetTickCount` at `0x1800134b1`
- `KERNEL32!GetTickCount` at `0x180013431`
- `KERNEL32!GetTickCount` at `0x1800134b1`
- `KERNEL32!SetThreadPriority` at `0x180013400`
- `KERNEL32!SetThreadPriority` at `0x1800134e8`
- `KERNEL32!SetThreadPriority` at `0x180013400`
- `KERNEL32!SetThreadPriority` at `0x1800134e8`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1800132c5`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1800132c5`
- `KERNEL32!GetCurrentThreadId` at `0x180013219`
- `KERNEL32!GetCurrentThreadId` at `0x18001357b`
- `KERNEL32!GetCurrentThreadId` at `0x180013219`
- `KERNEL32!GetCurrentThreadId` at `0x18001357b`
- `USER32!GetQueueStatus` at `0x1800134f9`
- `USER32!GetQueueStatus` at `0x1800134f9`
- `USER32!DispatchMessageW` at `0x18001347a`
- `USER32!DispatchMessageW` at `0x18001347a`
- `USER32!PeekMessageW` at `0x1800133a2`
- `USER32!PeekMessageW` at `0x180013461`
- `USER32!PeekMessageW` at `0x18001349c`
- `USER32!PeekMessageW` at `0x180013565`
- `USER32!PeekMessageW` at `0x1800133a2`
- `USER32!PeekMessageW` at `0x180013461`
- `USER32!PeekMessageW` at `0x18001349c`
- `USER32!PeekMessageW` at `0x180013565`
- `USER32!MsgWaitForMultipleObjects` at `0x18001335b`
- `USER32!MsgWaitForMultipleObjects` at `0x18001335b`
- `USER32!RegisterWindowMessageW` at `0x180013521`
- `USER32!RegisterWindowMessageW` at `0x180013521`
- `USER32!PostThreadMessageW` at `0x180013591`
- `USER32!PostThreadMessageW` at `0x180013591`

## pseudocode

```c
__int64 __fastcall CMsgMutex::Lock(CMsgMutex *this, void *a2, unsigned int a3)
{
  CMsgMutex *v5; // rbx
  DWORD CurrentThreadId; // eax
  UINT v8; // r13d
  HWND v9; // r15
  int v10; // r12d
  DWORD v11; // edi
  DWORD v12; // r14d
  DWORD v13; // esi
  DWORD v14; // ebx
  DWORD v15; // eax
  DWORD v16; // eax
  HANDLE CurrentThread; // rax
  HANDLE v18; // rax
  DWORD v19; // eax
  unsigned int v20; // edx
  unsigned int v21; // eax
  unsigned int v22; // ecx
  HANDLE v23; // rax
  UINT v24; // ebp
  BOOL v25; // eax
  DWORD v26; // eax
  unsigned int nPriority; // [rsp+30h] [rbp-88h]
  DWORD v28; // [rsp+34h] [rbp-84h]
  HANDLE Handles[2]; // [rsp+38h] [rbp-80h] BYREF
  struct tagMSG Msg; // [rsp+48h] [rbp-70h] BYREF
  DWORD TickCount; // [rsp+D8h] [rbp+20h]

  v5 = this;
  CurrentThreadId = GetCurrentThreadId();
  v28 = CurrentThreadId;
  if ( CurrentThreadId == *((_DWORD *)v5 + 2) )
    goto LABEL_2;
  v8 = *((_DWORD *)v5 + 6);
  if ( CurrentThreadId == *((_DWORD *)v5 + 7) )
    v9 = (HWND)*((_QWORD *)v5 + 2);
  else
    v9 = 0;
  v10 = 0;
  Handles[0] = *(HANDLE *)v5;
  TickCount = 0;
  nPriority = 0;
  Handles[1] = a2;
  if ( a3 - 1 <= 0xFFFFFFFD )
    TickCount = GetTickCount();
  v11 = TickCount;
  v12 = (a2 != 0) + 1;
  while ( 1 )
  {
    v13 = WaitForMultipleObjectsEx(v12, Handles, 0, 0, 0);
    if ( v13 < v12 )
      break;
    v14 = a3;
    if ( a3 > 0xA )
      v14 = 10;
    v15 = 64;
    if ( v9 )
      v15 = 72;
    v16 = MsgWaitForMultipleObjects(v12, Handles, 0, v14, v15);
    v13 = v16;
    if ( v16 != v12 && (v16 != 258 || v14 == a3) )
      break;
    memset(&Msg, 0, sizeof(Msg));
    if ( v9 && PeekMessageW(&Msg, v9, v8, v8, 1u) )
    {
      do
        DispatchMessageW(&Msg);
      while ( PeekMessageW(&Msg, v9, v8, v8, 1u) );
    }
    PeekMessageW(&Msg, 0, 0, 0, 0);
    if ( a3 - 1 <= 0xFFFFFFFD )
    {
      v19 = GetTickCount();
      v20 = v19 - v11;
      v11 = v19;
      v21 = a3;
      v22 = a3 - v20;
      a3 = 0;
      if ( v20 <= v21 )
        a3 = v22;
    }
    if ( !v10 )
    {
      CurrentThread = GetCurrentThread();
      nPriority = GetThreadPriority(CurrentThread);
      if ( nPriority < 2 )
      {
        v18 = GetCurrentThread();
        SetThreadPriority(v18, 2);
      }
      v10 = 1;
    }
  }
  v5 = this;
  if ( v10 )
  {
    v23 = GetCurrentThread();
    SetThreadPriority(v23, nPriority);
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
      v26 = GetCurrentThreadId();
      PostThreadMessageW(v26, v24, 0, 0);
    }
  }
  if ( !v13 )
  {
    *((_DWORD *)this + 2) = v28;
LABEL_2:
    ++*((_DWORD *)v5 + 3);
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180013200  mov     [rsp+arg_0], rcx
0x180013205  push    rbx
0x180013206  push    rbp
0x180013207  push    rsi
0x180013208  push    rdi
0x180013209  sub     rsp, 98h
0x180013210  mov     ebp, r8d
0x180013213  mov     rsi, rdx
0x180013216  mov     rbx, rcx
0x180013219  call    cs:__imp_GetCurrentThreadId
0x180013220  nop     dword ptr [rax+rax+00h]
0x180013225  mov     ecx, [rbx+8]
0x180013228  mov     [rsp+0B8h+var_84], eax
0x18001322c  cmp     eax, ecx
0x18001322e  jnz     short loc_180013245
0x180013230  inc     dword ptr [rbx+0Ch]
0x180013233  mov     eax, 1
0x180013238  add     rsp, 98h
0x18001323f  pop     rdi
0x180013240  pop     rsi
0x180013241  pop     rbp
0x180013242  pop     rbx
0x180013243  retn
0x180013245  mov     [rsp+0B8h+arg_8], r12
0x18001324d  xor     ecx, ecx
0x18001324f  mov     [rsp+0B8h+var_28], r13
0x180013257  mov     r13d, [rbx+18h]
0x18001325b  mov     [rsp+0B8h+var_30], r14
0x180013263  mov     [rsp+0B8h+var_38], r15
0x18001326b  cmp     eax, [rbx+1Ch]
0x18001326e  jnz     loc_180013324
0x180013274  mov     r15, [rbx+10h]
0x180013278  mov     rax, [rbx]
0x18001327b  mov     r12d, ecx
0x18001327e  mov     [rsp+0B8h+Handles], rax
0x180013283  lea     eax, [rbp-1]
0x180013286  mov     [rsp+0B8h+arg_18], ecx
0x18001328d  mov     [rsp+0B8h+nPriority], ecx
0x180013291  mov     [rsp+0B8h+var_78], rsi
0x180013296  cmp     eax, 0FFFFFFFDh
0x180013299  jbe     loc_180013431
0x18001329f  mov     edi, [rsp+0B8h+arg_18]
0x1800132a6  test    rsi, rsi
0x1800132a9  mov     r14d, ecx
0x1800132ac  setnz   r14b
0x1800132b0  inc     r14d
0x1800132b3  mov     [rsp+0B8h+bAlertable], ecx; bAlertable
0x1800132b7  lea     rdx, [rsp+0B8h+Handles]; lpHandles
0x1800132bc  mov     ecx, r14d; nCount
0x1800132bf  xor     r9d, r9d; dwMilliseconds
0x1800132c2  xor     r8d, r8d; bWaitAll
0x1800132c5  call    cs:__imp_WaitForMultipleObjectsEx
0x1800132cc  nop     dword ptr [rax+rax+00h]
0x1800132d1  mov     esi, eax
0x1800132d3  cmp     eax, r14d
0x1800132d6  jnb     short loc_18001332C
0x1800132d8  mov     r15, [rsp+0B8h+var_38]
0x1800132e0  test    r12d, r12d
0x1800132e3  mov     r12, [rsp+0B8h+arg_8]
0x1800132eb  mov     r14, [rsp+0B8h+var_30]
0x1800132f3  mov     r13, [rsp+0B8h+var_28]
0x1800132fb  mov     rbx, [rsp+0B8h+arg_0]
0x180013303  mov     edi, [rsp+0B8h+var_84]
0x180013307  jnz     loc_1800134D5
0x18001330d  test    esi, esi
0x18001330f  jz      loc_1800135A2
0x180013315  xor     eax, eax
0x180013317  add     rsp, 98h
0x18001331e  pop     rdi
0x18001331f  pop     rsi
0x180013320  pop     rbp
0x180013321  pop     rbx
0x180013322  retn
0x180013324  mov     r15, rcx
0x180013327  jmp     loc_180013278
0x18001332c  mov     eax, 0Ah
0x180013331  lea     rdx, [rsp+0B8h+Handles]; pHandles
0x180013336  mov     ecx, 48h ; 'H'
0x18001333b  cmp     ebp, 0Ah
0x18001333e  mov     ebx, ebp
0x180013340  cmova   ebx, eax
0x180013343  mov     eax, 40h ; '@'
0x180013348  test    r15, r15
0x18001334b  mov     r9d, ebx; dwMilliseconds
0x18001334e  cmovnz  eax, ecx
0x180013351  xor     r8d, r8d; fWaitAll
0x180013354  mov     ecx, r14d; nCount
0x180013357  mov     [rsp+0B8h+bAlertable], eax; dwWakeMask
0x18001335b  call    cs:__imp_MsgWaitForMultipleObjects
0x180013362  nop     dword ptr [rax+rax+00h]
0x180013367  mov     esi, eax
0x180013369  cmp     eax, r14d
0x18001336c  jnz     loc_180013419
0x180013372  xorps   xmm0, xmm0
0x180013375  movups  xmmword ptr [rsp+0B8h+Msg.hwnd], xmm0
0x18001337a  movups  xmmword ptr [rsp+0B8h+Msg.wParam], xmm0
0x18001337f  movups  xmmword ptr [rsp+0B8h+Msg.time], xmm0
0x180013384  test    r15, r15
0x180013387  jnz     loc_18001344B
0x18001338d  xor     r9d, r9d; wMsgFilterMax
0x180013390  mov     [rsp+0B8h+bAlertable], 0; wRemoveMsg
0x180013398  xor     r8d, r8d; wMsgFilterMin
0x18001339b  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x1800133a0  xor     edx, edx; hWnd
0x1800133a2  call    cs:__imp_PeekMessageW
0x1800133a9  nop     dword ptr [rax+rax+00h]
0x1800133ae  lea     eax, [rbp-1]
0x1800133b1  cmp     eax, 0FFFFFFFDh
0x1800133b4  jbe     loc_1800134B1
0x1800133ba  mov     ecx, 0
0x1800133bf  test    r12d, r12d
0x1800133c2  jnz     loc_1800132B3
0x1800133c8  call    cs:__imp_GetCurrentThread
0x1800133cf  nop     dword ptr [rax+rax+00h]
0x1800133d4  mov     rcx, rax; hThread
0x1800133d7  call    cs:__imp_GetThreadPriority
0x1800133de  nop     dword ptr [rax+rax+00h]
0x1800133e3  mov     [rsp+0B8h+nPriority], eax
0x1800133e7  cmp     eax, 2
0x1800133ea  jnb     short loc_18001340C
0x1800133ec  call    cs:__imp_GetCurrentThread
0x1800133f3  nop     dword ptr [rax+rax+00h]
0x1800133f8  mov     rcx, rax; hThread
0x1800133fb  mov     edx, 2; nPriority
0x180013400  call    cs:__imp_SetThreadPriority
0x180013407  nop     dword ptr [rax+rax+00h]
0x18001340c  xor     ecx, ecx
0x18001340e  mov     r12d, 1
0x180013414  jmp     loc_1800132B3
0x180013419  cmp     eax, 102h
0x18001341e  jnz     loc_1800132D8
0x180013424  cmp     ebx, ebp
0x180013426  jz      loc_1800132D8
0x18001342c  jmp     loc_180013372
0x180013431  call    cs:__imp_GetTickCount
0x180013438  nop     dword ptr [rax+rax+00h]
0x18001343d  mov     [rsp+0B8h+arg_18], eax
0x180013444  xor     ecx, ecx
0x180013446  jmp     loc_18001329F
0x18001344b  mov     r9d, r13d; wMsgFilterMax
0x18001344e  mov     [rsp+0B8h+bAlertable], 1; wRemoveMsg
0x180013456  mov     r8d, r13d; wMsgFilterMin
0x180013459  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x18001345e  mov     rdx, r15; hWnd
0x180013461  call    cs:__imp_PeekMessageW
0x180013468  nop     dword ptr [rax+rax+00h]
0x18001346d  test    eax, eax
0x18001346f  jz      loc_18001338D
0x180013475  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x18001347a  call    cs:__imp_DispatchMessageW
0x180013481  nop     dword ptr [rax+rax+00h]
0x180013486  mov     r9d, r13d; wMsgFilterMax
0x180013489  mov     [rsp+0B8h+bAlertable], 1; wRemoveMsg
0x180013491  mov     r8d, r13d; wMsgFilterMin
0x180013494  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x180013499  mov     rdx, r15; hWnd
0x18001349c  call    cs:__imp_PeekMessageW
0x1800134a3  nop     dword ptr [rax+rax+00h]
0x1800134a8  test    eax, eax
0x1800134aa  jnz     short loc_180013475
0x1800134ac  jmp     loc_18001338D
0x1800134b1  call    cs:__imp_GetTickCount
0x1800134b8  nop     dword ptr [rax+rax+00h]
0x1800134bd  mov     ecx, ebp
0x1800134bf  mov     edx, eax
0x1800134c1  sub     edx, edi
0x1800134c3  mov     edi, eax
0x1800134c5  mov     eax, ebp
0x1800134c7  sub     ecx, edx
0x1800134c9  xor     ebp, ebp
0x1800134cb  cmp     edx, eax
0x1800134cd  cmovbe  ebp, ecx
0x1800134d0  jmp     loc_1800133BA
0x1800134d5  call    cs:__imp_GetCurrentThread
0x1800134dc  nop     dword ptr [rax+rax+00h]
0x1800134e1  mov     edx, [rsp+0B8h+nPriority]; nPriority
0x1800134e5  mov     rcx, rax; hThread
0x1800134e8  call    cs:__imp_SetThreadPriority
0x1800134ef  nop     dword ptr [rax+rax+00h]
0x1800134f4  mov     ecx, 8; flags
0x1800134f9  call    cs:__imp_GetQueueStatus
0x180013500  nop     dword ptr [rax+rax+00h]
0x180013505  shr     eax, 10h
0x180013508  test    al, 8
0x18001350a  jz      loc_18001330D
0x180013510  mov     ebp, cs:wMsgFilterMax
0x180013516  test    ebp, ebp
0x180013518  jnz     short loc_180013539
0x18001351a  lea     rcx, String; "AMUnblock"
0x180013521  call    cs:__imp_RegisterWindowMessageW
0x180013528  nop     dword ptr [rax+rax+00h]
0x18001352d  mov     cs:wMsgFilterMax, eax
0x180013533  mov     ebp, eax
0x180013535  test    eax, eax
0x180013537  jz      short loc_18001357B
0x180013539  xorps   xmm0, xmm0
0x18001353c  movups  xmmword ptr [rsp+0B8h+Msg.hwnd], xmm0
0x180013541  movups  xmmword ptr [rsp+0B8h+Msg.wParam], xmm0
0x180013546  movups  xmmword ptr [rsp+0B8h+Msg.time], xmm0
0x18001354b  mov     r9d, ebp; wMsgFilterMax
0x18001354e  mov     [rsp+0B8h+bAlertable], 1; wRemoveMsg
0x180013556  mov     r8d, ebp; wMsgFilterMin
0x180013559  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x18001355e  mov     rdx, 0FFFFFFFFFFFFFFFFh; hWnd
0x180013565  call    cs:__imp_PeekMessageW
0x18001356c  nop     dword ptr [rax+rax+00h]
0x180013571  mov     ebp, cs:wMsgFilterMax
0x180013577  test    eax, eax
0x180013579  jnz     short loc_18001354B
0x18001357b  call    cs:__imp_GetCurrentThreadId
0x180013582  nop     dword ptr [rax+rax+00h]
0x180013587  xor     r9d, r9d; lParam
0x18001358a  xor     r8d, r8d; wParam
0x18001358d  mov     ecx, eax; idThread
0x18001358f  mov     edx, ebp; Msg
0x180013591  call    cs:__imp_PostThreadMessageW
0x180013598  nop     dword ptr [rax+rax+00h]
0x18001359d  jmp     loc_18001330D
0x1800135a2  mov     [rbx+8], edi
0x1800135a5  jmp     loc_180013230
```
