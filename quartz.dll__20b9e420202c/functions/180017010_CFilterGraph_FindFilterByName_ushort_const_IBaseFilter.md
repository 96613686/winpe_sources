# CFilterGraph::FindFilterByName(ushort const *,IBaseFilter * *)

- ea: `0x180017010`
- end: `0x180017484`
- name: `?FindFilterByName@CFilterGraph@@UEAAJPEBGPEAPEAUIBaseFilter@@@Z`
- size: `1140`
- prototype: `int(CFilterGraph *__hidden this, const unsigned __int16 *, struct IBaseFilter **)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800072a0`

## callees

- `0x180017010`
- `0x18015e010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180017217`
- `KERNEL32!GetCurrentThread` at `0x18001723e`
- `KERNEL32!GetCurrentThread` at `0x1800172c4`
- `KERNEL32!GetCurrentThread` at `0x180017217`
- `KERNEL32!GetCurrentThread` at `0x18001723e`
- `KERNEL32!GetCurrentThread` at `0x1800172c4`
- `KERNEL32!GetThreadPriority` at `0x180017226`
- `KERNEL32!GetThreadPriority` at `0x180017226`
- `KERNEL32!GetTickCount` at `0x1800171f3`
- `KERNEL32!GetTickCount` at `0x1800171f3`
- `KERNEL32!SetThreadPriority` at `0x180017252`
- `KERNEL32!SetThreadPriority` at `0x1800172da`
- `KERNEL32!SetThreadPriority` at `0x180017252`
- `KERNEL32!SetThreadPriority` at `0x1800172da`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1800170d9`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18001727b`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1800170d9`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18001727b`
- `KERNEL32!lstrcmpW` at `0x1800173df`
- `KERNEL32!lstrcmpW` at `0x1800173df`
- `KERNEL32!GetCurrentThreadId` at `0x18001705c`
- `KERNEL32!GetCurrentThreadId` at `0x18001736d`
- `KERNEL32!GetCurrentThreadId` at `0x18001705c`
- `KERNEL32!GetCurrentThreadId` at `0x18001736d`
- `KERNEL32!ReleaseMutex` at `0x180017421`
- `KERNEL32!ReleaseMutex` at `0x18001746a`
- `KERNEL32!ReleaseMutex` at `0x180017421`
- `KERNEL32!ReleaseMutex` at `0x18001746a`
- `USER32!GetQueueStatus` at `0x1800172eb`
- `USER32!GetQueueStatus` at `0x1800172eb`
- `USER32!DispatchMessageW` at `0x18001719c`
- `USER32!DispatchMessageW` at `0x18001719c`
- `USER32!PeekMessageW` at `0x180017187`
- `USER32!PeekMessageW` at `0x1800171ba`
- `USER32!PeekMessageW` at `0x1800171df`
- `USER32!PeekMessageW` at `0x180017356`
- `USER32!PeekMessageW` at `0x180017187`
- `USER32!PeekMessageW` at `0x1800171ba`
- `USER32!PeekMessageW` at `0x1800171df`
- `USER32!PeekMessageW` at `0x180017356`
- `USER32!MsgWaitForMultipleObjects` at `0x180017136`
- `USER32!MsgWaitForMultipleObjects` at `0x180017136`
- `USER32!RegisterWindowMessageW` at `0x180017315`
- `USER32!RegisterWindowMessageW` at `0x180017315`
- `USER32!PostThreadMessageW` at `0x180017384`
- `USER32!PostThreadMessageW` at `0x180017384`

## pseudocode

```c
__int64 __fastcall CFilterGraph::FindFilterByName(
        CFilterGraph *this,
        const unsigned __int16 *a2,
        struct IBaseFilter **a3)
{
  struct IBaseFilter **v3; // r12
  const WCHAR *v4; // rbp
  CFilterGraph *v5; // rbx
  char *v6; // rsi
  DWORD CurrentThreadId; // eax
  DWORD v8; // r14d
  int v9; // edi
  UINT v10; // r13d
  DWORD v11; // r15d
  HWND v12; // rsi
  int v13; // r12d
  unsigned int v14; // ebp
  DWORD v15; // r14d
  DWORD v16; // ebx
  DWORD v17; // eax
  DWORD v18; // eax
  DWORD TickCount; // eax
  unsigned int v20; // edx
  unsigned int v21; // eax
  unsigned int v22; // ecx
  HANDLE CurrentThread; // rax
  HANDLE v24; // rax
  bool v25; // zf
  HANDLE v26; // rax
  UINT v27; // r13d
  BOOL v28; // eax
  DWORD v29; // eax
  __int64 v30; // rax
  __int64 v31; // rbx
  __int64 v32; // rdi
  struct IBaseFilter *v33; // rcx
  HANDLE v34; // rcx
  HANDLE v36; // rcx
  DWORD v37; // [rsp+30h] [rbp-A8h]
  DWORD v38; // [rsp+3Ch] [rbp-9Ch]
  HWND hWnd; // [rsp+40h] [rbp-98h]
  HANDLE Handles[2]; // [rsp+48h] [rbp-90h] BYREF
  struct tagMSG Msg; // [rsp+58h] [rbp-80h] BYREF
  unsigned int nPriority; // [rsp+F8h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = this;
  if ( !a2 || !a3 )
    return 2147500035LL;
  v6 = (char *)this + 256;
  CurrentThreadId = GetCurrentThreadId();
  v38 = CurrentThreadId;
  v8 = CurrentThreadId;
  v9 = 1;
  if ( CurrentThreadId != *((_DWORD *)v6 + 2) )
  {
    v10 = *((_DWORD *)v6 + 6);
    if ( CurrentThreadId == *((_DWORD *)v6 + 7) )
      hWnd = (HWND)*((_QWORD *)v6 + 2);
    else
      hWnd = 0;
    Handles[0] = *(HANDLE *)v6;
    nPriority = 0;
    Handles[1] = 0;
    v11 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
    if ( v11 )
    {
      v12 = hWnd;
      v13 = 0;
      v14 = -1;
      v15 = 64;
      if ( hWnd )
        v15 = 72;
      v16 = 0;
      do
      {
        v17 = v14;
        if ( v14 > 0xA )
          v17 = 10;
        v37 = v17;
        v18 = MsgWaitForMultipleObjects(1u, Handles, 0, v17, v15);
        v11 = v18;
        if ( v18 != 1 && (v18 != 258 || v37 == v14) )
          break;
        memset(&Msg, 0, sizeof(Msg));
        if ( v12 && PeekMessageW(&Msg, v12, v10, v10, 1u) )
        {
          do
            DispatchMessageW(&Msg);
          while ( PeekMessageW(&Msg, v12, v10, v10, 1u) );
        }
        PeekMessageW(&Msg, 0, 0, 0, 0);
        if ( v14 - 1 <= 0xFFFFFFFD )
        {
          TickCount = GetTickCount();
          v20 = TickCount - v16;
          v16 = TickCount;
          v21 = v14;
          v22 = v14 - v20;
          v14 = 0;
          if ( v20 <= v21 )
            v14 = v22;
        }
        if ( !v13 )
        {
          CurrentThread = GetCurrentThread();
          nPriority = GetThreadPriority(CurrentThread);
          if ( nPriority < 2 )
          {
            v24 = GetCurrentThread();
            SetThreadPriority(v24, 2);
          }
          v12 = hWnd;
          v13 = 1;
        }
        v11 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
      }
      while ( v11 );
      v5 = this;
      v25 = v13 == 0;
      v4 = a2;
      v8 = v38;
      v3 = a3;
      v6 = (char *)this + 256;
      if ( !v25 )
      {
        v26 = GetCurrentThread();
        SetThreadPriority(v26, nPriority);
        if ( (GetQueueStatus(8u) & 0x80000) != 0 )
        {
          v27 = wMsgFilterMax;
          if ( wMsgFilterMax || (wMsgFilterMax = RegisterWindowMessageW(L"AMUnblock"), (v27 = wMsgFilterMax) != 0) )
          {
            memset(&Msg, 0, sizeof(Msg));
            do
            {
              v28 = PeekMessageW(&Msg, HWND_MESSAGE|0x2LL, v27, v27, 1u);
              v27 = wMsgFilterMax;
            }
            while ( v28 );
          }
          v29 = GetCurrentThreadId();
          PostThreadMessageW(v29, v27, 0, 0);
        }
      }
    }
    if ( v11 )
    {
      v9 = 0;
      goto LABEL_37;
    }
    *((_DWORD *)v5 + 66) = v8;
  }
  ++*((_DWORD *)v5 + 67);
LABEL_37:
  v30 = *((_QWORD *)v5 + 37);
  if ( !v9 )
    v6 = 0;
  while ( v30 )
  {
    v31 = *(_QWORD *)(v30 + 16);
    v32 = *(_QWORD *)(v30 + 8);
    if ( v31 && !lstrcmpW(*(LPCWSTR *)(v31 + 8), v4) )
    {
      v33 = *(struct IBaseFilter **)v31;
      *v3 = *(struct IBaseFilter **)v31;
      ((void (__fastcall *)(struct IBaseFilter *))v33->lpVtbl->AddRef)(v33);
      if ( v6 )
      {
        v25 = (*((_DWORD *)v6 + 3))-- == 1;
        if ( v25 )
        {
          v34 = *(HANDLE *)v6;
          *((_DWORD *)v6 + 2) = 0;
          ReleaseMutex(v34);
        }
      }
      return 0;
    }
    v30 = v32;
  }
  *v3 = 0;
  if ( v6 )
  {
    v25 = (*((_DWORD *)v6 + 3))-- == 1;
    if ( v25 )
    {
      v36 = *(HANDLE *)v6;
      *((_DWORD *)v6 + 2) = 0;
      ReleaseMutex(v36);
    }
  }
  return 2147746326LL;
}

```

## disassembly

```asm
0x180017010  mov     rax, rsp
0x180017013  mov     [rax+18h], r8
0x180017017  mov     [rax+10h], rdx
0x18001701b  mov     [rax+8], rcx
0x18001701f  push    rbx
0x180017020  push    rbp
0x180017021  push    r12
0x180017023  sub     rsp, 0C0h
0x18001702a  mov     r12, r8
0x18001702d  mov     rbp, rdx
0x180017030  mov     rbx, rcx
0x180017033  test    rdx, rdx
0x180017036  jz      loc_18001747D
0x18001703c  test    r8, r8
0x18001703f  jz      loc_18001747D
0x180017045  mov     [rax-20h], rsi
0x180017049  lea     rsi, [rcx+100h]
0x180017050  mov     [rax-28h], rdi
0x180017054  mov     [rax-38h], r14
0x180017058  mov     [rax-40h], r15
0x18001705c  call    cs:__imp_GetCurrentThreadId
0x180017063  nop     dword ptr [rax+rax+00h]
0x180017068  mov     r8d, [rsi+8]
0x18001706c  xor     r15d, r15d
0x18001706f  mov     [rsp+0D8h+var_9C], eax
0x180017073  mov     r14d, eax
0x180017076  mov     edi, 1
0x18001707b  cmp     eax, r8d
0x18001707e  jz      loc_1800173A7
0x180017084  mov     [rsp+0D8h+var_30], r13
0x18001708c  mov     r13d, [rsi+18h]
0x180017090  cmp     eax, [rsi+1Ch]
0x180017093  jnz     short loc_1800170A0
0x180017095  mov     rax, [rsi+10h]
0x180017099  mov     [rsp+0D8h+hWnd], rax
0x18001709e  jmp     short loc_1800170A5
0x1800170a0  mov     [rsp+0D8h+hWnd], r15
0x1800170a5  mov     rax, [rsi]
0x1800170a8  lea     rdx, [rsp+0D8h+Handles]; lpHandles
0x1800170ad  xor     r9d, r9d; dwMilliseconds
0x1800170b0  mov     [rsp+0D8h+Handles], rax
0x1800170b5  xor     r8d, r8d; bWaitAll
0x1800170b8  mov     [rsp+0D8h+var_A0], 0FFFFFFFFh
0x1800170c0  mov     ecx, edi; nCount
0x1800170c2  mov     [rsp+0D8h+var_A4], r15d
0x1800170c7  mov     [rsp+0D8h+nPriority], r15d
0x1800170cf  mov     [rsp+0D8h+var_88], r15
0x1800170d4  mov     [rsp+0D8h+bAlertable], r15d; bAlertable
0x1800170d9  call    cs:__imp_WaitForMultipleObjectsEx
0x1800170e0  nop     dword ptr [rax+rax+00h]
0x1800170e5  mov     r15d, eax
0x1800170e8  cmp     eax, edi
0x1800170ea  jb      loc_180017390
0x1800170f0  mov     rsi, [rsp+0D8h+hWnd]
0x1800170f5  mov     eax, 48h ; 'H'
0x1800170fa  mov     r12d, [rsp+0D8h+var_A4]
0x1800170ff  test    rsi, rsi
0x180017102  mov     ebp, [rsp+0D8h+var_A0]
0x180017106  mov     r14d, 40h ; '@'
0x18001710c  cmovnz  r14d, eax
0x180017110  mov     ecx, 0Ah
0x180017115  mov     ebx, r12d
0x180017118  mov     eax, ebp
0x18001711a  mov     [rsp+0D8h+bAlertable], r14d; dwWakeMask
0x18001711f  cmp     ebp, 0Ah
0x180017122  lea     rdx, [rsp+0D8h+Handles]; pHandles
0x180017127  cmova   eax, ecx
0x18001712a  xor     r8d, r8d; fWaitAll
0x18001712d  mov     r9d, eax; dwMilliseconds
0x180017130  mov     [rsp+0D8h+var_A8], eax
0x180017134  mov     ecx, edi; nCount
0x180017136  call    cs:__imp_MsgWaitForMultipleObjects
0x18001713d  nop     dword ptr [rax+rax+00h]
0x180017142  mov     r15d, eax
0x180017145  cmp     eax, edi
0x180017147  jz      short loc_18001715E
0x180017149  cmp     eax, 102h
0x18001714e  jnz     loc_180017297
0x180017154  cmp     [rsp+0D8h+var_A8], ebp
0x180017158  jz      loc_180017297
0x18001715e  xorps   xmm0, xmm0
0x180017161  movups  xmmword ptr [rsp+0D8h+Msg.hwnd], xmm0
0x180017166  movups  xmmword ptr [rsp+0D8h+Msg.wParam], xmm0
0x18001716b  movups  xmmword ptr [rsp+0D8h+Msg.time], xmm0
0x180017170  test    rsi, rsi
0x180017173  jz      short loc_1800171CA
0x180017175  mov     r9d, r13d; wMsgFilterMax
0x180017178  mov     [rsp+0D8h+bAlertable], edi; wRemoveMsg
0x18001717c  mov     r8d, r13d; wMsgFilterMin
0x18001717f  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x180017184  mov     rdx, rsi; hWnd
0x180017187  call    cs:__imp_PeekMessageW
0x18001718e  nop     dword ptr [rax+rax+00h]
0x180017193  test    eax, eax
0x180017195  jz      short loc_1800171CA
0x180017197  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x18001719c  call    cs:__imp_DispatchMessageW
0x1800171a3  nop     dword ptr [rax+rax+00h]
0x1800171a8  mov     r9d, r13d; wMsgFilterMax
0x1800171ab  mov     [rsp+0D8h+bAlertable], edi; wRemoveMsg
0x1800171af  mov     r8d, r13d; wMsgFilterMin
0x1800171b2  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x1800171b7  mov     rdx, rsi; hWnd
0x1800171ba  call    cs:__imp_PeekMessageW
0x1800171c1  nop     dword ptr [rax+rax+00h]
0x1800171c6  test    eax, eax
0x1800171c8  jnz     short loc_180017197
0x1800171ca  xor     r9d, r9d; wMsgFilterMax
0x1800171cd  mov     [rsp+0D8h+bAlertable], 0; wRemoveMsg
0x1800171d5  xor     r8d, r8d; wMsgFilterMin
0x1800171d8  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x1800171dd  xor     edx, edx; hWnd
0x1800171df  call    cs:__imp_PeekMessageW
0x1800171e6  nop     dword ptr [rax+rax+00h]
0x1800171eb  lea     eax, [rbp-1]
0x1800171ee  cmp     eax, 0FFFFFFFDh
0x1800171f1  ja      short loc_180017212
0x1800171f3  call    cs:__imp_GetTickCount
0x1800171fa  nop     dword ptr [rax+rax+00h]
0x1800171ff  mov     ecx, ebp
0x180017201  mov     edx, eax
0x180017203  sub     edx, ebx
0x180017205  mov     ebx, eax
0x180017207  mov     eax, ebp
0x180017209  sub     ecx, edx
0x18001720b  xor     ebp, ebp
0x18001720d  cmp     edx, eax
0x18001720f  cmovbe  ebp, ecx
0x180017212  test    r12d, r12d
0x180017215  jnz     short loc_180017266
0x180017217  call    cs:__imp_GetCurrentThread
0x18001721e  nop     dword ptr [rax+rax+00h]
0x180017223  mov     rcx, rax; hThread
0x180017226  call    cs:__imp_GetThreadPriority
0x18001722d  nop     dword ptr [rax+rax+00h]
0x180017232  mov     [rsp+0D8h+nPriority], eax
0x180017239  cmp     eax, 2
0x18001723c  jnb     short loc_18001725E
0x18001723e  call    cs:__imp_GetCurrentThread
0x180017245  nop     dword ptr [rax+rax+00h]
0x18001724a  mov     rcx, rax; hThread
0x18001724d  mov     edx, 2; nPriority
0x180017252  call    cs:__imp_SetThreadPriority
0x180017259  nop     dword ptr [rax+rax+00h]
0x18001725e  mov     rsi, [rsp+0D8h+hWnd]
0x180017263  mov     r12d, edi
0x180017266  xor     r9d, r9d; dwMilliseconds
0x180017269  mov     [rsp+0D8h+bAlertable], 0; bAlertable
0x180017271  xor     r8d, r8d; bWaitAll
0x180017274  lea     rdx, [rsp+0D8h+Handles]; lpHandles
0x180017279  mov     ecx, edi; nCount
0x18001727b  call    cs:__imp_WaitForMultipleObjectsEx
0x180017282  nop     dword ptr [rax+rax+00h]
0x180017287  mov     r15d, eax
0x18001728a  mov     ecx, 0Ah
0x18001728f  cmp     eax, edi
0x180017291  jnb     loc_180017118
0x180017297  mov     rbx, [rsp+0D8h+arg_0]
0x18001729f  test    r12d, r12d
0x1800172a2  mov     rbp, [rsp+0D8h+arg_8]
0x1800172aa  mov     r14d, [rsp+0D8h+var_9C]
0x1800172af  mov     r12, [rsp+0D8h+arg_10]
0x1800172b7  lea     rsi, [rbx+100h]
0x1800172be  jz      loc_180017390
0x1800172c4  call    cs:__imp_GetCurrentThread
0x1800172cb  nop     dword ptr [rax+rax+00h]
0x1800172d0  mov     edx, [rsp+0D8h+nPriority]; nPriority
0x1800172d7  mov     rcx, rax; hThread
0x1800172da  call    cs:__imp_SetThreadPriority
0x1800172e1  nop     dword ptr [rax+rax+00h]
0x1800172e6  mov     ecx, 8; flags
0x1800172eb  call    cs:__imp_GetQueueStatus
0x1800172f2  nop     dword ptr [rax+rax+00h]
0x1800172f7  shr     eax, 10h
0x1800172fa  test    al, 8
0x1800172fc  jz      loc_180017390
0x180017302  mov     r13d, cs:wMsgFilterMax
0x180017309  test    r13d, r13d
0x18001730c  jnz     short loc_18001732E
0x18001730e  lea     rcx, String; "AMUnblock"
0x180017315  call    cs:__imp_RegisterWindowMessageW
0x18001731c  nop     dword ptr [rax+rax+00h]
0x180017321  mov     cs:wMsgFilterMax, eax
0x180017327  mov     r13d, eax
0x18001732a  test    eax, eax
0x18001732c  jz      short loc_18001736D
0x18001732e  xorps   xmm0, xmm0
0x180017331  movups  xmmword ptr [rsp+0D8h+Msg.hwnd], xmm0
0x180017336  movups  xmmword ptr [rsp+0D8h+Msg.wParam], xmm0
0x18001733b  movups  xmmword ptr [rsp+0D8h+Msg.time], xmm0
0x180017340  mov     r9d, r13d; wMsgFilterMax
0x180017343  mov     [rsp+0D8h+bAlertable], edi; wRemoveMsg
0x180017347  mov     r8d, r13d; wMsgFilterMin
0x18001734a  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x18001734f  mov     rdx, 0FFFFFFFFFFFFFFFFh; hWnd
0x180017356  call    cs:__imp_PeekMessageW
0x18001735d  nop     dword ptr [rax+rax+00h]
0x180017362  mov     r13d, cs:wMsgFilterMax
0x180017369  test    eax, eax
0x18001736b  jnz     short loc_180017340
0x18001736d  call    cs:__imp_GetCurrentThreadId
0x180017374  nop     dword ptr [rax+rax+00h]
0x180017379  xor     r9d, r9d; lParam
0x18001737c  xor     r8d, r8d; wParam
0x18001737f  mov     ecx, eax; idThread
0x180017381  mov     edx, r13d; Msg
0x180017384  call    cs:__imp_PostThreadMessageW
0x18001738b  nop     dword ptr [rax+rax+00h]
0x180017390  mov     r13, [rsp+0D8h+var_30]
0x180017398  test    r15d, r15d
0x18001739b  jnz     short loc_1800173F4
0x18001739d  mov     [rbx+108h], r14d
0x1800173a4  xor     r15d, r15d
0x1800173a7  inc     dword ptr [rbx+10Ch]
0x1800173ad  mov     rax, [rbx+128h]
0x1800173b4  test    edi, edi
0x1800173b6  mov     r14, [rsp+0D8h+var_38]
0x1800173be  cmovz   rsi, r15
0x1800173c2  test    rax, rax
0x1800173c5  jz      loc_180017454
0x1800173cb  mov     rbx, [rax+10h]
0x1800173cf  mov     rdi, [rax+8]
0x1800173d3  test    rbx, rbx
0x1800173d6  jz      short loc_1800173EF
0x1800173d8  mov     rcx, [rbx+8]; lpString1
0x1800173dc  mov     rdx, rbp; lpString2
0x1800173df  call    cs:__imp_lstrcmpW
0x1800173e6  nop     dword ptr [rax+rax+00h]
0x1800173eb  test    eax, eax
0x1800173ed  jz      short loc_1800173FC
0x1800173ef  mov     rax, rdi
0x1800173f2  jmp     short loc_1800173C2
0x1800173f4  xor     r15d, r15d
0x1800173f7  mov     edi, r15d
0x1800173fa  jmp     short loc_1800173AD
0x1800173fc  mov     rcx, [rbx]
0x1800173ff  mov     [r12], rcx
0x180017403  mov     rax, [rcx]
0x180017406  mov     rax, [rax+8]
0x18001740a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001740f  test    rsi, rsi
0x180017412  jz      short loc_18001742D
0x180017414  add     dword ptr [rsi+0Ch], 0FFFFFFFFh
0x180017418  jnz     short loc_18001742D
0x18001741a  mov     rcx, [rsi]; hMutex
0x18001741d  mov     [rsi+8], r15d
0x180017421  call    cs:__imp_ReleaseMutex
0x180017428  nop     dword ptr [rax+rax+00h]
0x18001742d  xor     eax, eax
0x18001742f  mov     rdi, [rsp+0D8h+var_28]
0x180017437  mov     rsi, [rsp+0D8h+var_20]
0x18001743f  mov     r15, [rsp+0D8h+var_40]
0x180017447  add     rsp, 0C0h
0x18001744e  pop     r12
0x180017450  pop     rbp
0x180017451  pop     rbx
0x180017452  retn
0x180017454  mov     [r12], r15
0x180017458  test    rsi, rsi
0x18001745b  jz      short loc_180017476
0x18001745d  add     dword ptr [rsi+0Ch], 0FFFFFFFFh
0x180017461  jnz     short loc_180017476
0x180017463  mov     rcx, [rsi]; hMutex
0x180017466  mov     [rsi+8], r15d
0x18001746a  call    cs:__imp_ReleaseMutex
0x180017471  nop     dword ptr [rax+rax+00h]
0x180017476  mov     eax, 80040216h
0x18001747b  jmp     short loc_18001742F
0x18001747d  mov     eax, 80004003h
0x180017482  jmp     short loc_180017447
```
