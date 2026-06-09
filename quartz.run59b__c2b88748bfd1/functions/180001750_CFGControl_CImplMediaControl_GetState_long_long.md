# CFGControl::CImplMediaControl::GetState(long,long *)

- ea: `0x180001750`
- end: `0x180001ba0`
- name: `?GetState@CImplMediaControl@CFGControl@@UEAAJJPEAJ@Z`
- size: `1104`
- prototype: `int(CFGControl::CImplMediaControl *__hidden this, int, int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18006fe30`
- `0x1800753ec`
- `0x180075594`
- `0x180075660`

## callees

- `0x180001750`
- `0x180001ba0`
- `0x180001ee0`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180001977`
- `KERNEL32!GetCurrentThread` at `0x18000199e`
- `KERNEL32!GetCurrentThread` at `0x180001a20`
- `KERNEL32!GetCurrentThread` at `0x180001977`
- `KERNEL32!GetCurrentThread` at `0x18000199e`
- `KERNEL32!GetCurrentThread` at `0x180001a20`
- `KERNEL32!GetThreadPriority` at `0x180001986`
- `KERNEL32!GetThreadPriority` at `0x180001986`
- `KERNEL32!GetTickCount` at `0x180001952`
- `KERNEL32!GetTickCount` at `0x180001952`
- `KERNEL32!SetThreadPriority` at `0x1800019b2`
- `KERNEL32!SetThreadPriority` at `0x180001a36`
- `KERNEL32!SetThreadPriority` at `0x1800019b2`
- `KERNEL32!SetThreadPriority` at `0x180001a36`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180001839`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1800019d9`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180001839`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1800019d9`
- `KERNEL32!GetCurrentThreadId` at `0x1800017bb`
- `KERNEL32!GetCurrentThreadId` at `0x180001acd`
- `KERNEL32!GetCurrentThreadId` at `0x1800017bb`
- `KERNEL32!GetCurrentThreadId` at `0x180001acd`
- `KERNEL32!ReleaseMutex` at `0x180001b27`
- `KERNEL32!ReleaseMutex` at `0x180001b27`
- `USER32!GetQueueStatus` at `0x180001a47`
- `USER32!GetQueueStatus` at `0x180001a47`
- `USER32!DispatchMessageW` at `0x1800018f7`
- `USER32!DispatchMessageW` at `0x1800018f7`
- `USER32!PeekMessageW` at `0x1800018e2`
- `USER32!PeekMessageW` at `0x180001919`
- `USER32!PeekMessageW` at `0x18000193e`
- `USER32!PeekMessageW` at `0x180001ab6`
- `USER32!PeekMessageW` at `0x1800018e2`
- `USER32!PeekMessageW` at `0x180001919`
- `USER32!PeekMessageW` at `0x18000193e`
- `USER32!PeekMessageW` at `0x180001ab6`
- `USER32!MsgWaitForMultipleObjects` at `0x18000188e`
- `USER32!MsgWaitForMultipleObjects` at `0x18000188e`
- `USER32!RegisterWindowMessageW` at `0x180001a71`
- `USER32!RegisterWindowMessageW` at `0x180001a71`
- `USER32!PostThreadMessageW` at `0x180001ae4`
- `USER32!PostThreadMessageW` at `0x180001ae4`

## pseudocode

```c
__int64 __fastcall CFGControl::CImplMediaControl::GetState(
        CFGControl::CImplMediaControl *this,
        unsigned int a2,
        int *a3)
{
  int *v3; // rbx
  unsigned int v4; // ebp
  CFGControl::CImplMediaControl *v5; // rdi
  __int64 result; // rax
  __int64 v7; // rsi
  __int64 v8; // rsi
  DWORD CurrentThreadId; // eax
  DWORD v10; // r14d
  UINT v11; // r13d
  HWND v12; // r12
  void *v13; // rax
  DWORD v14; // r15d
  int v15; // r14d
  unsigned int v16; // esi
  DWORD v17; // edi
  DWORD v18; // ebx
  DWORD v19; // ebp
  DWORD v20; // eax
  DWORD TickCount; // eax
  unsigned int v22; // edx
  unsigned int v23; // ecx
  bool v24; // cc
  HANDLE CurrentThread; // rax
  HANDLE v26; // rax
  bool v27; // zf
  HANDLE v28; // rax
  UINT v29; // r12d
  BOOL v30; // eax
  DWORD v31; // eax
  void *v32; // rcx
  enum _FilterState LieState; // eax
  __int64 v34; // rcx
  enum _FilterState v35; // esi
  DWORD v36; // [rsp+3Ch] [rbp-9Ch]
  HANDLE Handles[2]; // [rsp+40h] [rbp-98h] BYREF
  __int64 v38; // [rsp+50h] [rbp-88h]
  tagMSG Msg; // [rsp+58h] [rbp-80h] BYREF
  int *v42; // [rsp+F0h] [rbp+18h] BYREF
  int nPriority; // [rsp+F8h] [rbp+20h]

  v42 = a3;
  v3 = a3;
  v4 = a2;
  v5 = this;
  if ( !a3 )
    return 2147500035LL;
  v7 = *((_QWORD *)this + 5);
  if ( a2 == 0x80000000 )
  {
    *a3 = *(_DWORD *)(v7 + 136);
    return 0;
  }
  v8 = *(_QWORD *)(v7 + 16);
  v38 = v8;
  CurrentThreadId = GetCurrentThreadId();
  v36 = CurrentThreadId;
  v10 = CurrentThreadId;
  if ( CurrentThreadId != *(_DWORD *)(v8 + 8) )
  {
    v11 = *(_DWORD *)(v8 + 24);
    if ( CurrentThreadId == *(_DWORD *)(v8 + 28) )
      v12 = *(HWND *)(v8 + 16);
    else
      v12 = 0;
    v13 = *(void **)v8;
    nPriority = 0;
    Handles[1] = 0;
    Handles[0] = v13;
    v14 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
    if ( v14 )
    {
      v15 = 0;
      v16 = -1;
      v17 = 64;
      v18 = 0;
      if ( v12 )
        v17 = 72;
      do
      {
        v19 = v16;
        if ( v16 > 0xA )
          v19 = 10;
        v20 = MsgWaitForMultipleObjects(1u, Handles, 0, v19, v17);
        v14 = v20;
        if ( v20 != 1 && (v20 != 258 || v19 == v16) )
          break;
        memset(&Msg, 0, sizeof(Msg));
        if ( v12 && PeekMessageW(&Msg, v12, v11, v11, 1u) )
        {
          do
            DispatchMessageW(&Msg);
          while ( PeekMessageW(&Msg, v12, v11, v11, 1u) );
        }
        PeekMessageW(&Msg, 0, 0, 0, 0);
        if ( v16 - 1 <= 0xFFFFFFFD )
        {
          TickCount = GetTickCount();
          v22 = TickCount - v18;
          v18 = TickCount;
          v23 = v16 - v22;
          v24 = v22 <= v16;
          v16 = 0;
          if ( v24 )
            v16 = v23;
        }
        if ( !v15 )
        {
          CurrentThread = GetCurrentThread();
          nPriority = GetThreadPriority(CurrentThread);
          if ( (unsigned int)nPriority < 2 )
          {
            v26 = GetCurrentThread();
            SetThreadPriority(v26, 2);
          }
          v15 = 1;
        }
        v14 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
      }
      while ( v14 );
      v3 = v42;
      v27 = v15 == 0;
      v10 = v36;
      v5 = this;
      v8 = v38;
      v4 = a2;
      if ( !v27 )
      {
        v28 = GetCurrentThread();
        SetThreadPriority(v28, nPriority);
        if ( (GetQueueStatus(8u) & 0x80000) != 0 )
        {
          v29 = wMsgFilterMax;
          if ( wMsgFilterMax || (wMsgFilterMax = RegisterWindowMessageW(L"AMUnblock"), (v29 = wMsgFilterMax) != 0) )
          {
            memset(&Msg, 0, sizeof(Msg));
            do
            {
              v30 = PeekMessageW(&Msg, HWND_MESSAGE|0x2LL, v29, v29, 1u);
              v29 = wMsgFilterMax;
            }
            while ( v30 );
          }
          v31 = GetCurrentThreadId();
          PostThreadMessageW(v31, v29, 0, 0);
        }
      }
    }
    if ( v14 )
      goto LABEL_40;
    *(_DWORD *)(v8 + 8) = v10;
  }
  ++*(_DWORD *)(v8 + 12);
  if ( v8 )
  {
    v27 = (*(_DWORD *)(v8 + 12))-- == 1;
    if ( v27 )
    {
      v32 = *(void **)v8;
      *(_DWORD *)(v8 + 8) = 0;
      ReleaseMutex(v32);
    }
  }
LABEL_40:
  LieState = CFGControl::GetLieState(*((CFGControl **)v5 + 5));
  v34 = *((_QWORD *)v5 + 5);
  LODWORD(v42) = 0;
  v35 = LieState;
  result = CFilterGraph::GetState((CFilterGraph *)(*(_QWORD *)v34 + 152LL), v4, (enum _FilterState *)&v42);
  if ( (int)result >= 0 && v35 != (_DWORD)v42 )
    result = 262711;
  *v3 = v35;
  return result;
}

```

## disassembly

```asm
0x180001750  mov     [rsp+arg_10], r8
0x180001755  mov     [rsp+arg_8], edx
0x180001759  mov     [rsp+arg_0], rcx
0x18000175e  push    rbx
0x18000175f  push    rbp
0x180001760  push    rdi
0x180001761  sub     rsp, 0C0h
0x180001768  mov     rbx, r8
0x18000176b  mov     ebp, edx
0x18000176d  mov     rdi, rcx
0x180001770  test    r8, r8
0x180001773  jnz     short loc_180001786
0x180001775  mov     eax, 80004003h
0x18000177a  add     rsp, 0C0h
0x180001781  pop     rdi
0x180001782  pop     rbp
0x180001783  pop     rbx
0x180001784  retn
0x180001786  mov     [rsp+0D8h+var_20], rsi
0x18000178e  mov     rsi, [rcx+28h]
0x180001792  cmp     edx, 80000000h
0x180001798  jnz     short loc_1800017AA
0x18000179a  mov     eax, [rsi+88h]
0x1800017a0  mov     [r8], eax
0x1800017a3  xor     eax, eax
0x1800017a5  jmp     loc_180001B83
0x1800017aa  mov     rsi, [rsi+10h]
0x1800017ae  mov     [rsp+0D8h+var_88], rsi
0x1800017b3  mov     [rsp+0D8h+var_38], r14
0x1800017bb  call    cs:__imp_GetCurrentThreadId
0x1800017c2  nop     dword ptr [rax+rax+00h]
0x1800017c7  mov     ecx, [rsi+8]
0x1800017ca  xor     edx, edx
0x1800017cc  mov     [rsp+0D8h+var_9C], eax
0x1800017d0  mov     r14d, eax
0x1800017d3  cmp     eax, ecx
0x1800017d5  jz      loc_180001B13
0x1800017db  mov     [rsp+0D8h+var_30], r13
0x1800017e3  mov     r13d, [rsi+18h]
0x1800017e7  mov     [rsp+0D8h+var_40], r15
0x1800017ef  mov     [rsp+0D8h+var_28], r12
0x1800017f7  cmp     eax, [rsi+1Ch]
0x1800017fa  jnz     short loc_180001802
0x1800017fc  mov     r12, [rsi+10h]
0x180001800  jmp     short loc_180001805
0x180001802  mov     r12, rdx
0x180001805  mov     rax, [rsi]
0x180001808  xor     r9d, r9d; dwMilliseconds
0x18000180b  mov     [rsp+0D8h+var_A8], edx
0x18000180f  xor     r8d, r8d; bWaitAll
0x180001812  mov     [rsp+0D8h+nPriority], edx
0x180001819  mov     ecx, 1; nCount
0x18000181e  mov     [rsp+0D8h+var_90], rdx
0x180001823  mov     [rsp+0D8h+bAlertable], edx; bAlertable
0x180001827  lea     rdx, [rsp+0D8h+Handles]; lpHandles
0x18000182c  mov     [rsp+0D8h+Handles], rax
0x180001831  mov     [rsp+0D8h+var_A4], 0FFFFFFFFh
0x180001839  call    cs:__imp_WaitForMultipleObjectsEx
0x180001840  nop     dword ptr [rax+rax+00h]
0x180001845  mov     r15d, eax
0x180001848  cmp     eax, 1
0x18000184b  jb      loc_180001AF0
0x180001851  mov     r14d, [rsp+0D8h+var_A8]
0x180001856  mov     eax, 48h ; 'H'
0x18000185b  mov     esi, [rsp+0D8h+var_A4]
0x18000185f  test    r12, r12
0x180001862  mov     edi, 40h ; '@'
0x180001867  mov     ebx, r14d
0x18000186a  cmovnz  edi, eax
0x18000186d  mov     eax, 0Ah
0x180001872  cmp     esi, 0Ah
0x180001875  mov     [rsp+0D8h+bAlertable], edi; dwWakeMask
0x180001879  mov     ebp, esi
0x18000187b  lea     rdx, [rsp+0D8h+Handles]; pHandles
0x180001880  cmova   ebp, eax
0x180001883  mov     ecx, 1; nCount
0x180001888  mov     r9d, ebp; dwMilliseconds
0x18000188b  xor     r8d, r8d; fWaitAll
0x18000188e  call    cs:__imp_MsgWaitForMultipleObjects
0x180001895  nop     dword ptr [rax+rax+00h]
0x18000189a  mov     r15d, eax
0x18000189d  cmp     eax, 1
0x1800018a0  jz      short loc_1800018B5
0x1800018a2  cmp     eax, 102h
0x1800018a7  jnz     loc_1800019F6
0x1800018ad  cmp     ebp, esi
0x1800018af  jz      loc_1800019F6
0x1800018b5  xorps   xmm0, xmm0
0x1800018b8  movups  xmmword ptr [rsp+0D8h+Msg.hwnd], xmm0
0x1800018bd  movups  xmmword ptr [rsp+0D8h+Msg.wParam], xmm0
0x1800018c2  movups  xmmword ptr [rsp+0D8h+Msg.time], xmm0
0x1800018c7  test    r12, r12
0x1800018ca  jz      short loc_180001929
0x1800018cc  mov     r9d, r13d; wMsgFilterMax
0x1800018cf  mov     [rsp+0D8h+bAlertable], 1; wRemoveMsg
0x1800018d7  mov     r8d, r13d; wMsgFilterMin
0x1800018da  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x1800018df  mov     rdx, r12; hWnd
0x1800018e2  call    cs:__imp_PeekMessageW
0x1800018e9  nop     dword ptr [rax+rax+00h]
0x1800018ee  test    eax, eax
0x1800018f0  jz      short loc_180001929
0x1800018f2  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x1800018f7  call    cs:__imp_DispatchMessageW
0x1800018fe  nop     dword ptr [rax+rax+00h]
0x180001903  mov     r9d, r13d; wMsgFilterMax
0x180001906  mov     [rsp+0D8h+bAlertable], 1; wRemoveMsg
0x18000190e  mov     r8d, r13d; wMsgFilterMin
0x180001911  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x180001916  mov     rdx, r12; hWnd
0x180001919  call    cs:__imp_PeekMessageW
0x180001920  nop     dword ptr [rax+rax+00h]
0x180001925  test    eax, eax
0x180001927  jnz     short loc_1800018F2
0x180001929  xor     r15d, r15d
0x18000192c  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x180001931  xor     r9d, r9d; wMsgFilterMax
0x180001934  mov     [rsp+0D8h+bAlertable], r15d; wRemoveMsg
0x180001939  xor     r8d, r8d; wMsgFilterMin
0x18000193c  xor     edx, edx; hWnd
0x18000193e  call    cs:__imp_PeekMessageW
0x180001945  nop     dword ptr [rax+rax+00h]
0x18000194a  lea     eax, [rsi-1]
0x18000194d  cmp     eax, 0FFFFFFFDh
0x180001950  ja      short loc_180001972
0x180001952  call    cs:__imp_GetTickCount
0x180001959  nop     dword ptr [rax+rax+00h]
0x18000195e  mov     ecx, esi
0x180001960  mov     edx, eax
0x180001962  sub     edx, ebx
0x180001964  mov     ebx, eax
0x180001966  mov     eax, esi
0x180001968  sub     ecx, edx
0x18000196a  cmp     edx, eax
0x18000196c  mov     esi, r15d
0x18000196f  cmovbe  esi, ecx
0x180001972  test    r14d, r14d
0x180001975  jnz     short loc_1800019C4
0x180001977  call    cs:__imp_GetCurrentThread
0x18000197e  nop     dword ptr [rax+rax+00h]
0x180001983  mov     rcx, rax; hThread
0x180001986  call    cs:__imp_GetThreadPriority
0x18000198d  nop     dword ptr [rax+rax+00h]
0x180001992  mov     [rsp+0D8h+nPriority], eax
0x180001999  cmp     eax, 2
0x18000199c  jnb     short loc_1800019BE
0x18000199e  call    cs:__imp_GetCurrentThread
0x1800019a5  nop     dword ptr [rax+rax+00h]
0x1800019aa  mov     rcx, rax; hThread
0x1800019ad  mov     edx, 2; nPriority
0x1800019b2  call    cs:__imp_SetThreadPriority
0x1800019b9  nop     dword ptr [rax+rax+00h]
0x1800019be  mov     r14d, 1
0x1800019c4  xor     r9d, r9d; dwMilliseconds
0x1800019c7  mov     [rsp+0D8h+bAlertable], r15d; bAlertable
0x1800019cc  xor     r8d, r8d; bWaitAll
0x1800019cf  lea     rdx, [rsp+0D8h+Handles]; lpHandles
0x1800019d4  mov     ecx, 1; nCount
0x1800019d9  call    cs:__imp_WaitForMultipleObjectsEx
0x1800019e0  nop     dword ptr [rax+rax+00h]
0x1800019e5  mov     r15d, eax
0x1800019e8  cmp     eax, 1
0x1800019eb  mov     eax, 0Ah
0x1800019f0  jnb     loc_180001872
0x1800019f6  mov     rbx, [rsp+0D8h+arg_10]
0x1800019fe  test    r14d, r14d
0x180001a01  mov     r14d, [rsp+0D8h+var_9C]
0x180001a06  mov     rdi, [rsp+0D8h+arg_0]
0x180001a0e  mov     rsi, [rsp+0D8h+var_88]
0x180001a13  mov     ebp, [rsp+0D8h+arg_8]
0x180001a1a  jz      loc_180001AF0
0x180001a20  call    cs:__imp_GetCurrentThread
0x180001a27  nop     dword ptr [rax+rax+00h]
0x180001a2c  mov     edx, [rsp+0D8h+nPriority]; nPriority
0x180001a33  mov     rcx, rax; hThread
0x180001a36  call    cs:__imp_SetThreadPriority
0x180001a3d  nop     dword ptr [rax+rax+00h]
0x180001a42  mov     ecx, 8; flags
0x180001a47  call    cs:__imp_GetQueueStatus
0x180001a4e  nop     dword ptr [rax+rax+00h]
0x180001a53  shr     eax, 10h
0x180001a56  test    al, 8
0x180001a58  jz      loc_180001AF0
0x180001a5e  mov     r12d, cs:wMsgFilterMax
0x180001a65  test    r12d, r12d
0x180001a68  jnz     short loc_180001A8A
0x180001a6a  lea     rcx, String; "AMUnblock"
0x180001a71  call    cs:__imp_RegisterWindowMessageW
0x180001a78  nop     dword ptr [rax+rax+00h]
0x180001a7d  mov     cs:wMsgFilterMax, eax
0x180001a83  mov     r12d, eax
0x180001a86  test    eax, eax
0x180001a88  jz      short loc_180001ACD
0x180001a8a  xorps   xmm0, xmm0
0x180001a8d  movups  xmmword ptr [rsp+0D8h+Msg.hwnd], xmm0
0x180001a92  movups  xmmword ptr [rsp+0D8h+Msg.wParam], xmm0
0x180001a97  movups  xmmword ptr [rsp+0D8h+Msg.time], xmm0
0x180001a9c  mov     r9d, r12d; wMsgFilterMax
0x180001a9f  mov     [rsp+0D8h+bAlertable], 1; wRemoveMsg
0x180001aa7  mov     r8d, r12d; wMsgFilterMin
0x180001aaa  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x180001aaf  mov     rdx, 0FFFFFFFFFFFFFFFFh; hWnd
0x180001ab6  call    cs:__imp_PeekMessageW
0x180001abd  nop     dword ptr [rax+rax+00h]
0x180001ac2  mov     r12d, cs:wMsgFilterMax
0x180001ac9  test    eax, eax
0x180001acb  jnz     short loc_180001A9C
0x180001acd  call    cs:__imp_GetCurrentThreadId
0x180001ad4  nop     dword ptr [rax+rax+00h]
0x180001ad9  xor     r9d, r9d; lParam
0x180001adc  xor     r8d, r8d; wParam
0x180001adf  mov     ecx, eax; idThread
0x180001ae1  mov     edx, r12d; Msg
0x180001ae4  call    cs:__imp_PostThreadMessageW
0x180001aeb  nop     dword ptr [rax+rax+00h]
0x180001af0  mov     r13, [rsp+0D8h+var_30]
0x180001af8  test    r15d, r15d
0x180001afb  mov     r15, [rsp+0D8h+var_40]
0x180001b03  mov     r12, [rsp+0D8h+var_28]
0x180001b0b  jnz     short loc_180001B33
0x180001b0d  mov     [rsi+8], r14d
0x180001b11  xor     edx, edx
0x180001b13  inc     dword ptr [rsi+0Ch]
0x180001b16  test    rsi, rsi
0x180001b19  jz      short loc_180001B33
0x180001b1b  add     dword ptr [rsi+0Ch], 0FFFFFFFFh
0x180001b1f  jnz     short loc_180001B33
0x180001b21  mov     rcx, [rsi]; hMutex
0x180001b24  mov     [rsi+8], edx
0x180001b27  call    cs:__imp_ReleaseMutex
0x180001b2e  nop     dword ptr [rax+rax+00h]
0x180001b33  mov     rcx, [rdi+28h]; this
0x180001b37  call    ?GetLieState@CFGControl@@QEAA?AW4_FilterState@@XZ; CFGControl::GetLieState(void)
0x180001b3c  mov     rcx, [rdi+28h]
0x180001b40  lea     r8, [rsp+0D8h+arg_10]; enum _FilterState *
0x180001b48  mov     edx, ebp; unsigned int
0x180001b4a  mov     dword ptr [rsp+0D8h+arg_10], 0
0x180001b55  mov     esi, eax
0x180001b57  mov     rcx, [rcx]
0x180001b5a  add     rcx, 98h; this
0x180001b61  call    ?GetState@CFilterGraph@@UEAAJKPEAW4_FilterState@@@Z; CFilterGraph::GetState(ulong,_FilterState *)
0x180001b66  mov     r14, [rsp+0D8h+var_38]
0x180001b6e  test    eax, eax
0x180001b70  js      short loc_180001B81
0x180001b72  cmp     esi, dword ptr [rsp+0D8h+arg_10]
0x180001b79  mov     ecx, 40237h
0x180001b7e  cmovnz  eax, ecx
0x180001b81  mov     [rbx], esi
0x180001b83  mov     rsi, [rsp+0D8h+var_20]
0x180001b8b  add     rsp, 0C0h
0x180001b92  pop     rdi
0x180001b93  pop     rbp
0x180001b94  pop     rbx
0x180001b95  retn
```
