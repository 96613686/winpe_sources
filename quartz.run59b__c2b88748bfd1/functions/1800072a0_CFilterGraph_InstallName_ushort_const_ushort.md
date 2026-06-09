# CFilterGraph::InstallName(ushort const *,ushort * &)

- ea: `0x1800072a0`
- end: `0x1800078a7`
- name: `?InstallName@CFilterGraph@@AEAAJPEBGAEAPEAG@Z`
- size: `1543`
- prototype: `__int64 __fastcall(CFilterGraph *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180006cc0`

## callees

- `0x180004924`
- `0x1800072a0`
- `0x1800078b0`
- `0x180017010`
- `0x1800384a4`
- `0x1800388a0`
- `0x18015bb98`
- `0x18015e010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x1800074c1`
- `KERNEL32!GetCurrentThread` at `0x1800074e5`
- `KERNEL32!GetCurrentThread` at `0x180007560`
- `KERNEL32!GetCurrentThread` at `0x1800074c1`
- `KERNEL32!GetCurrentThread` at `0x1800074e5`
- `KERNEL32!GetCurrentThread` at `0x180007560`
- `KERNEL32!GetThreadPriority` at `0x1800074d0`
- `KERNEL32!GetThreadPriority` at `0x1800074d0`
- `KERNEL32!GetTickCount` at `0x180007499`
- `KERNEL32!GetTickCount` at `0x180007499`
- `KERNEL32!SetThreadPriority` at `0x1800074f9`
- `KERNEL32!SetThreadPriority` at `0x180007573`
- `KERNEL32!SetThreadPriority` at `0x1800074f9`
- `KERNEL32!SetThreadPriority` at `0x180007573`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000737b`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180007522`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000737b`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180007522`
- `KERNEL32!lstrcmpW` at `0x180007672`
- `KERNEL32!lstrcmpW` at `0x180007672`
- `KERNEL32!GetCurrentThreadId` at `0x180007309`
- `KERNEL32!GetCurrentThreadId` at `0x180007604`
- `KERNEL32!GetCurrentThreadId` at `0x180007309`
- `KERNEL32!GetCurrentThreadId` at `0x180007604`
- `KERNEL32!ReleaseMutex` at `0x1800076b2`
- `KERNEL32!ReleaseMutex` at `0x180007717`
- `KERNEL32!ReleaseMutex` at `0x1800076b2`
- `KERNEL32!ReleaseMutex` at `0x180007717`
- `KERNEL32!lstrlenW` at `0x1800076c6`
- `KERNEL32!lstrlenW` at `0x180007728`
- `KERNEL32!lstrlenW` at `0x1800077cc`
- `KERNEL32!lstrlenW` at `0x1800076c6`
- `KERNEL32!lstrlenW` at `0x180007728`
- `KERNEL32!lstrlenW` at `0x1800077cc`
- `USER32!GetQueueStatus` at `0x180007584`
- `USER32!GetQueueStatus` at `0x180007584`
- `USER32!DispatchMessageW` at `0x180007441`
- `USER32!DispatchMessageW` at `0x180007441`
- `USER32!PeekMessageW` at `0x18000742c`
- `USER32!PeekMessageW` at `0x18000745f`
- `USER32!PeekMessageW` at `0x180007484`
- `USER32!PeekMessageW` at `0x1800075ed`
- `USER32!PeekMessageW` at `0x18000742c`
- `USER32!PeekMessageW` at `0x18000745f`
- `USER32!PeekMessageW` at `0x180007484`
- `USER32!PeekMessageW` at `0x1800075ed`
- `USER32!MsgWaitForMultipleObjects` at `0x1800073dc`
- `USER32!MsgWaitForMultipleObjects` at `0x1800073dc`
- `USER32!RegisterWindowMessageW` at `0x1800075ae`
- `USER32!RegisterWindowMessageW` at `0x1800075ae`
- `USER32!PostThreadMessageW` at `0x18000761b`
- `USER32!PostThreadMessageW` at `0x18000761b`

## pseudocode

```c
__int64 __fastcall CFilterGraph::InstallName(CFilterGraph *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  unsigned __int16 **v3; // r15
  unsigned __int16 *v4; // r14
  CFilterGraph *v5; // r13
  char *v6; // rsi
  DWORD CurrentThreadId; // eax
  int v8; // ebx
  DWORD v9; // edi
  UINT v10; // r12d
  void *v11; // rax
  DWORD v12; // r15d
  HWND v13; // rdi
  DWORD v14; // eax
  int v15; // r14d
  unsigned int v16; // r13d
  DWORD v17; // esi
  DWORD v18; // ecx
  DWORD v19; // eax
  DWORD TickCount; // eax
  unsigned int v21; // edx
  unsigned int v22; // eax
  unsigned int v23; // ecx
  HANDLE CurrentThread; // rax
  HANDLE v25; // rax
  bool v26; // zf
  HANDLE v27; // rax
  UINT v28; // r12d
  BOOL v29; // eax
  DWORD v30; // eax
  __int64 i; // rax
  LPCWSTR *v32; // rbx
  __int64 v33; // rdi
  LPCWSTR v34; // rdi
  void *v35; // rcx
  int v36; // ebx
  int v37; // esi
  unsigned int v38; // eax
  void *v39; // rcx
  int v40; // edi
  unsigned __int16 *v41; // rax
  __int64 result; // rax
  int v43; // ecx
  unsigned int v44; // ecx
  unsigned int v45; // esi
  const unsigned __int16 *v46; // rdi
  __int64 v47; // r8
  __int64 v48; // rax
  unsigned __int64 v49; // rcx
  size_t v50; // r8
  int v51; // ecx
  DWORD v52; // [rsp+30h] [rbp-D0h]
  DWORD v53; // [rsp+34h] [rbp-CCh]
  HWND hWnd; // [rsp+38h] [rbp-C8h] BYREF
  int nPriority; // [rsp+40h] [rbp-C0h]
  int v56; // [rsp+44h] [rbp-BCh]
  int v57; // [rsp+48h] [rbp-B8h]
  DWORD v58; // [rsp+4Ch] [rbp-B4h]
  unsigned __int16 **v59; // [rsp+50h] [rbp-B0h]
  HANDLE Handles[2]; // [rsp+58h] [rbp-A8h] BYREF
  CFilterGraph *v61; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v62; // [rsp+70h] [rbp-90h]
  struct tagMSG Msg; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v64[128]; // [rsp+B0h] [rbp-50h] BYREF

  v59 = a3;
  v3 = a3;
  v62 = a2;
  v4 = a2;
  v61 = this;
  v5 = this;
  *a3 = 0;
  if ( a2 && *a2 )
  {
    v6 = (char *)this + 256;
    CurrentThreadId = GetCurrentThreadId();
    v8 = 1;
    v53 = CurrentThreadId;
    v9 = CurrentThreadId;
    if ( CurrentThreadId != *((_DWORD *)v6 + 2) )
    {
      v10 = *((_DWORD *)v6 + 6);
      if ( CurrentThreadId == *((_DWORD *)v6 + 7) )
        hWnd = (HWND)*((_QWORD *)v6 + 2);
      else
        hWnd = 0;
      v11 = *(void **)v6;
      v56 = 0;
      nPriority = 0;
      Handles[1] = 0;
      Handles[0] = v11;
      v57 = -1;
      v12 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
      if ( v12 )
      {
        v13 = hWnd;
        v14 = 64;
        v15 = v56;
        v16 = v57;
        if ( hWnd )
          v14 = 72;
        v58 = v14;
        v17 = v56;
        do
        {
          v18 = v16;
          if ( v16 > 0xA )
            v18 = 10;
          v52 = v18;
          v19 = MsgWaitForMultipleObjects(1u, Handles, 0, v18, v14);
          v12 = v19;
          if ( v19 != 1 && (v19 != 258 || v52 == v16) )
            break;
          memset(&Msg, 0, sizeof(Msg));
          if ( v13 && PeekMessageW(&Msg, v13, v10, v10, 1u) )
          {
            do
              DispatchMessageW(&Msg);
            while ( PeekMessageW(&Msg, v13, v10, v10, 1u) );
          }
          PeekMessageW(&Msg, 0, 0, 0, 0);
          if ( v16 - 1 <= 0xFFFFFFFD )
          {
            TickCount = GetTickCount();
            v21 = TickCount - v17;
            v17 = TickCount;
            v22 = v16;
            v23 = v16 - v21;
            v16 = 0;
            if ( v21 <= v22 )
              v16 = v23;
          }
          if ( !v15 )
          {
            CurrentThread = GetCurrentThread();
            nPriority = GetThreadPriority(CurrentThread);
            if ( (unsigned int)nPriority < 2 )
            {
              v25 = GetCurrentThread();
              SetThreadPriority(v25, 2);
            }
            v13 = hWnd;
            v15 = 1;
          }
          v12 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
          v14 = v58;
        }
        while ( v12 );
        v5 = v61;
        v26 = v15 == 0;
        v4 = (unsigned __int16 *)v62;
        v9 = v53;
        v6 = (char *)v61 + 256;
        if ( !v26 )
        {
          v27 = GetCurrentThread();
          SetThreadPriority(v27, nPriority);
          if ( (GetQueueStatus(8u) & 0x80000) != 0 )
          {
            v28 = wMsgFilterMax;
            if ( wMsgFilterMax || (wMsgFilterMax = RegisterWindowMessageW(L"AMUnblock"), (v28 = wMsgFilterMax) != 0) )
            {
              memset(&Msg, 0, sizeof(Msg));
              do
              {
                v29 = PeekMessageW(&Msg, HWND_MESSAGE|0x2LL, v28, v28, 1u);
                v28 = wMsgFilterMax;
              }
              while ( v29 );
            }
            v30 = GetCurrentThreadId();
            PostThreadMessageW(v30, v28, 0, 0);
          }
        }
      }
      v26 = v12 == 0;
      v3 = v59;
      if ( !v26 )
      {
        v8 = 0;
LABEL_37:
        if ( !v8 )
          v6 = 0;
        for ( i = *((_QWORD *)v5 + 37); i; i = v33 )
        {
          v32 = *(LPCWSTR **)(i + 16);
          v33 = *(_QWORD *)(i + 8);
          if ( v32 && !lstrcmpW(v32[1], v4) )
          {
            v34 = *v32;
            (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)*v32 + 8LL))(*v32);
            if ( v6 )
            {
              v26 = (*((_DWORD *)v6 + 3))-- == 1;
              if ( v26 )
              {
                v35 = *(void **)v6;
                *((_DWORD *)v6 + 2) = 0;
                ReleaseMutex(v35);
              }
            }
            v36 = 2;
            v37 = 128;
            v38 = lstrlenW(v4) + 1;
            if ( v38 < 0x80 )
              v37 = v38;
            StringCchCopyW(v64, v37, v4);
            v4 = v64;
            (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)v34 + 16LL))(v34);
            goto LABEL_58;
          }
        }
        if ( v6 )
        {
          v26 = (*((_DWORD *)v6 + 3))-- == 1;
          if ( v26 )
          {
            v39 = *(void **)v6;
            *((_DWORD *)v6 + 2) = 0;
            ReleaseMutex(v39);
          }
        }
        v36 = 0;
        goto LABEL_55;
      }
      *((_DWORD *)v5 + 66) = v9;
    }
    ++*((_DWORD *)v5 + 67);
    goto LABEL_37;
  }
  v36 = 1;
  v4 = v64;
  v37 = 1;
  v64[0] = 0;
LABEL_58:
  v43 = *((_DWORD *)v5 + 120);
  v26 = v43 == -1;
  v44 = v43 + 1;
  *((_DWORD *)v5 + 120) = v44;
  if ( !v26 )
  {
    v45 = v37 - 1;
    v46 = L"%04u";
    if ( v36 != 1 )
      v46 = L" %04u";
    do
    {
      StringCchPrintfW((wchar_t *)&Msg, 0x14u, v46, v44);
      v47 = (unsigned int)(lstrlenW((LPCWSTR)&Msg) + 1);
      v48 = v45;
      v49 = 128 - v47;
      v50 = 2 * v47;
      if ( v45 >= v49 )
        v48 = (unsigned int)v49;
      memcpy_0(&v64[v48], &Msg, v50);
      hWnd = 0;
      if ( CFilterGraph::FindFilterByName(v5, v64, (struct IBaseFilter **)&hWnd) < 0 )
        break;
      (*(void (__fastcall **)(HWND))(*(_QWORD *)hWnd + 16LL))(hWnd);
      v51 = *((_DWORD *)v5 + 120);
      v26 = v51 == -1;
      v44 = v51 + 1;
      *((_DWORD *)v5 + 120) = v44;
    }
    while ( !v26 );
    v3 = v59;
  }
  if ( !*((_DWORD *)v5 + 120) )
    return 2147746349LL;
LABEL_55:
  v40 = lstrlenW(v4) + 1;
  v41 = (unsigned __int16 *)operator new[](saturated_mul(v40, 2u));
  *v3 = v41;
  if ( !v41 )
    return 2147942414LL;
  memcpy_0(v41, v4, 2 * v40);
  result = 262701;
  if ( v36 != 2 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1800072a0  mov     [rsp-8+arg_18], rbx
0x1800072a5  push    rbp
0x1800072a6  push    rsi
0x1800072a7  push    rdi
0x1800072a8  push    r12
0x1800072aa  push    r13
0x1800072ac  push    r14
0x1800072ae  push    r15
0x1800072b0  lea     rbp, [rsp-0C0h]
0x1800072b8  sub     rsp, 1C0h
0x1800072bf  mov     rax, cs:__security_cookie
0x1800072c6  xor     rax, rsp
0x1800072c9  mov     [rbp+0F0h+var_40], rax
0x1800072d0  mov     [rsp+1F0h+var_1A0], r8
0x1800072d5  mov     r15, r8
0x1800072d8  mov     [rsp+1F0h+var_180], rdx
0x1800072dd  mov     r14, rdx
0x1800072e0  mov     [rsp+1F0h+var_188], rcx
0x1800072e5  mov     r13, rcx
0x1800072e8  mov     qword ptr [r8], 0
0x1800072ef  test    rdx, rdx
0x1800072f2  jz      loc_180007767
0x1800072f8  cmp     word ptr [rdx], 0
0x1800072fc  jz      loc_180007767
0x180007302  lea     rsi, [rcx+100h]
0x180007309  call    cs:__imp_GetCurrentThreadId
0x180007310  nop     dword ptr [rax+rax+00h]
0x180007315  mov     ecx, [rsi+8]
0x180007318  mov     ebx, 1
0x18000731d  mov     [rsp+1F0h+var_1BC], eax
0x180007321  mov     edi, eax
0x180007323  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18000732a  cmp     eax, ecx
0x18000732c  jz      loc_18000763F
0x180007332  mov     r12d, [rsi+18h]
0x180007336  xor     ecx, ecx
0x180007338  cmp     eax, [rsi+1Ch]
0x18000733b  jnz     short loc_180007348
0x18000733d  mov     rax, [rsi+10h]
0x180007341  mov     [rsp+1F0h+hWnd], rax
0x180007346  jmp     short loc_18000734D
0x180007348  mov     [rsp+1F0h+hWnd], rcx
0x18000734d  mov     rax, [rsi]
0x180007350  lea     rdx, [rsp+1F0h+Handles]; lpHandles
0x180007355  mov     [rsp+1F0h+var_1AC], ecx
0x180007359  xor     r9d, r9d; dwMilliseconds
0x18000735c  mov     [rsp+1F0h+nPriority], ecx
0x180007360  xor     r8d, r8d; bWaitAll
0x180007363  mov     [rsp+1F0h+var_190], rcx
0x180007368  mov     [rsp+1F0h+bAlertable], ecx; bAlertable
0x18000736c  mov     ecx, ebx; nCount
0x18000736e  mov     [rsp+1F0h+Handles], rax
0x180007373  mov     [rsp+1F0h+var_1A8], 0FFFFFFFFh
0x18000737b  call    cs:__imp_WaitForMultipleObjectsEx
0x180007382  nop     dword ptr [rax+rax+00h]
0x180007387  mov     r15d, eax
0x18000738a  cmp     eax, ebx
0x18000738c  jb      loc_180007627
0x180007392  mov     rdi, [rsp+1F0h+hWnd]
0x180007397  mov     eax, 40h ; '@'
0x18000739c  mov     r14d, [rsp+1F0h+var_1AC]
0x1800073a1  test    rdi, rdi
0x1800073a4  mov     r13d, [rsp+1F0h+var_1A8]
0x1800073a9  mov     ecx, 48h ; 'H'
0x1800073ae  cmovnz  eax, ecx
0x1800073b1  mov     edx, 0Ah
0x1800073b6  mov     [rsp+1F0h+var_1A4], eax
0x1800073ba  mov     esi, r14d
0x1800073bd  mov     ecx, r13d
0x1800073c0  mov     [rsp+1F0h+bAlertable], eax; dwWakeMask
0x1800073c4  cmp     r13d, 0Ah
0x1800073c8  cmova   ecx, edx
0x1800073cb  xor     r8d, r8d; fWaitAll
0x1800073ce  mov     [rsp+1F0h+var_1C0], ecx
0x1800073d2  lea     rdx, [rsp+1F0h+Handles]; pHandles
0x1800073d7  mov     r9d, ecx; dwMilliseconds
0x1800073da  mov     ecx, ebx; nCount
0x1800073dc  call    cs:__imp_MsgWaitForMultipleObjects
0x1800073e3  nop     dword ptr [rax+rax+00h]
0x1800073e8  mov     r15d, eax
0x1800073eb  cmp     eax, ebx
0x1800073ed  jz      short loc_180007405
0x1800073ef  cmp     eax, 102h
0x1800073f4  jnz     loc_180007542
0x1800073fa  cmp     [rsp+1F0h+var_1C0], r13d
0x1800073ff  jz      loc_180007542
0x180007405  xorps   xmm0, xmm0
0x180007408  movups  xmmword ptr [rsp+1F0h+Msg.hwnd], xmm0
0x18000740d  movups  xmmword ptr [rbp+0F0h+Msg.wParam], xmm0
0x180007411  movups  xmmword ptr [rbp+0F0h+Msg.time], xmm0
0x180007415  test    rdi, rdi
0x180007418  jz      short loc_18000746F
0x18000741a  mov     r9d, r12d; wMsgFilterMax
0x18000741d  mov     [rsp+1F0h+bAlertable], ebx; wRemoveMsg
0x180007421  mov     r8d, r12d; wMsgFilterMin
0x180007424  lea     rcx, [rsp+1F0h+Msg]; lpMsg
0x180007429  mov     rdx, rdi; hWnd
0x18000742c  call    cs:__imp_PeekMessageW
0x180007433  nop     dword ptr [rax+rax+00h]
0x180007438  test    eax, eax
0x18000743a  jz      short loc_18000746F
0x18000743c  lea     rcx, [rsp+1F0h+Msg]; lpMsg
0x180007441  call    cs:__imp_DispatchMessageW
0x180007448  nop     dword ptr [rax+rax+00h]
0x18000744d  mov     r9d, r12d; wMsgFilterMax
0x180007450  mov     [rsp+1F0h+bAlertable], ebx; wRemoveMsg
0x180007454  mov     r8d, r12d; wMsgFilterMin
0x180007457  lea     rcx, [rsp+1F0h+Msg]; lpMsg
0x18000745c  mov     rdx, rdi; hWnd
0x18000745f  call    cs:__imp_PeekMessageW
0x180007466  nop     dword ptr [rax+rax+00h]
0x18000746b  test    eax, eax
0x18000746d  jnz     short loc_18000743C
0x18000746f  xor     r9d, r9d; wMsgFilterMax
0x180007472  mov     [rsp+1F0h+bAlertable], 0; wRemoveMsg
0x18000747a  xor     r8d, r8d; wMsgFilterMin
0x18000747d  lea     rcx, [rsp+1F0h+Msg]; lpMsg
0x180007482  xor     edx, edx; hWnd
0x180007484  call    cs:__imp_PeekMessageW
0x18000748b  nop     dword ptr [rax+rax+00h]
0x180007490  lea     eax, [r13-1]
0x180007494  cmp     eax, 0FFFFFFFDh
0x180007497  ja      short loc_1800074BC
0x180007499  call    cs:__imp_GetTickCount
0x1800074a0  nop     dword ptr [rax+rax+00h]
0x1800074a5  mov     ecx, r13d
0x1800074a8  mov     edx, eax
0x1800074aa  sub     edx, esi
0x1800074ac  mov     esi, eax
0x1800074ae  mov     eax, r13d
0x1800074b1  sub     ecx, edx
0x1800074b3  xor     r13d, r13d
0x1800074b6  cmp     edx, eax
0x1800074b8  cmovbe  r13d, ecx
0x1800074bc  test    r14d, r14d
0x1800074bf  jnz     short loc_18000750D
0x1800074c1  call    cs:__imp_GetCurrentThread
0x1800074c8  nop     dword ptr [rax+rax+00h]
0x1800074cd  mov     rcx, rax; hThread
0x1800074d0  call    cs:__imp_GetThreadPriority
0x1800074d7  nop     dword ptr [rax+rax+00h]
0x1800074dc  mov     [rsp+1F0h+nPriority], eax
0x1800074e0  cmp     eax, 2
0x1800074e3  jnb     short loc_180007505
0x1800074e5  call    cs:__imp_GetCurrentThread
0x1800074ec  nop     dword ptr [rax+rax+00h]
0x1800074f1  mov     rcx, rax; hThread
0x1800074f4  mov     edx, 2; nPriority
0x1800074f9  call    cs:__imp_SetThreadPriority
0x180007500  nop     dword ptr [rax+rax+00h]
0x180007505  mov     rdi, [rsp+1F0h+hWnd]
0x18000750a  mov     r14d, ebx
0x18000750d  xor     r9d, r9d; dwMilliseconds
0x180007510  mov     [rsp+1F0h+bAlertable], 0; bAlertable
0x180007518  xor     r8d, r8d; bWaitAll
0x18000751b  lea     rdx, [rsp+1F0h+Handles]; lpHandles
0x180007520  mov     ecx, ebx; nCount
0x180007522  call    cs:__imp_WaitForMultipleObjectsEx
0x180007529  nop     dword ptr [rax+rax+00h]
0x18000752e  mov     r15d, eax
0x180007531  cmp     eax, ebx
0x180007533  mov     eax, [rsp+1F0h+var_1A4]
0x180007537  mov     edx, 0Ah
0x18000753c  jnb     loc_1800073BD
0x180007542  mov     r13, [rsp+1F0h+var_188]
0x180007547  test    r14d, r14d
0x18000754a  mov     r14, [rsp+1F0h+var_180]
0x18000754f  mov     edi, [rsp+1F0h+var_1BC]
0x180007553  lea     rsi, [r13+100h]
0x18000755a  jz      loc_180007627
0x180007560  call    cs:__imp_GetCurrentThread
0x180007567  nop     dword ptr [rax+rax+00h]
0x18000756c  mov     edx, [rsp+1F0h+nPriority]; nPriority
0x180007570  mov     rcx, rax; hThread
0x180007573  call    cs:__imp_SetThreadPriority
0x18000757a  nop     dword ptr [rax+rax+00h]
0x18000757f  mov     ecx, 8; flags
0x180007584  call    cs:__imp_GetQueueStatus
0x18000758b  nop     dword ptr [rax+rax+00h]
0x180007590  shr     eax, 10h
0x180007593  test    al, 8
0x180007595  jz      loc_180007627
0x18000759b  mov     r12d, cs:wMsgFilterMax
0x1800075a2  test    r12d, r12d
0x1800075a5  jnz     short loc_1800075C7
0x1800075a7  lea     rcx, String; "AMUnblock"
0x1800075ae  call    cs:__imp_RegisterWindowMessageW
0x1800075b5  nop     dword ptr [rax+rax+00h]
0x1800075ba  mov     cs:wMsgFilterMax, eax
0x1800075c0  mov     r12d, eax
0x1800075c3  test    eax, eax
0x1800075c5  jz      short loc_180007604
0x1800075c7  xorps   xmm0, xmm0
0x1800075ca  movups  xmmword ptr [rsp+1F0h+Msg.hwnd], xmm0
0x1800075cf  movups  xmmword ptr [rbp+0F0h+Msg.wParam], xmm0
0x1800075d3  movups  xmmword ptr [rbp+0F0h+Msg.time], xmm0
0x1800075d7  mov     r9d, r12d; wMsgFilterMax
0x1800075da  mov     [rsp+1F0h+bAlertable], ebx; wRemoveMsg
0x1800075de  mov     r8d, r12d; wMsgFilterMin
0x1800075e1  lea     rcx, [rsp+1F0h+Msg]; lpMsg
0x1800075e6  mov     rdx, 0FFFFFFFFFFFFFFFFh; hWnd
0x1800075ed  call    cs:__imp_PeekMessageW
0x1800075f4  nop     dword ptr [rax+rax+00h]
0x1800075f9  mov     r12d, cs:wMsgFilterMax
0x180007600  test    eax, eax
0x180007602  jnz     short loc_1800075D7
0x180007604  call    cs:__imp_GetCurrentThreadId
0x18000760b  nop     dword ptr [rax+rax+00h]
0x180007610  xor     r9d, r9d; lParam
0x180007613  xor     r8d, r8d; wParam
0x180007616  mov     ecx, eax; idThread
0x180007618  mov     edx, r12d; Msg
0x18000761b  call    cs:__imp_PostThreadMessageW
0x180007622  nop     dword ptr [rax+rax+00h]
0x180007627  test    r15d, r15d
0x18000762a  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180007631  mov     r15, [rsp+1F0h+var_1A0]
0x180007636  jnz     short loc_180007687
0x180007638  mov     [r13+108h], edi
0x18000763f  inc     dword ptr [r13+10Ch]
0x180007646  xor     eax, eax
0x180007648  test    ebx, ebx
0x18000764a  cmovz   rsi, rax
0x18000764e  mov     rax, [r13+128h]
0x180007655  test    rax, rax
0x180007658  jz      loc_180007702
0x18000765e  mov     rbx, [rax+10h]
0x180007662  mov     rdi, [rax+8]
0x180007666  test    rbx, rbx
0x180007669  jz      short loc_180007682
0x18000766b  mov     rcx, [rbx+8]; lpString1
0x18000766f  mov     rdx, r14; lpString2
0x180007672  call    cs:__imp_lstrcmpW
0x180007679  nop     dword ptr [rax+rax+00h]
0x18000767e  test    eax, eax
0x180007680  jz      short loc_18000768B
0x180007682  mov     rax, rdi
0x180007685  jmp     short loc_180007655
0x180007687  xor     ebx, ebx
0x180007689  jmp     short loc_180007646
0x18000768b  mov     rdi, [rbx]
0x18000768e  mov     rcx, rdi
0x180007691  mov     rax, [rdi]
0x180007694  mov     rax, [rax+8]
0x180007698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000769d  test    rsi, rsi
0x1800076a0  jz      short loc_1800076BE
0x1800076a2  add     dword ptr [rsi+0Ch], 0FFFFFFFFh
0x1800076a6  jnz     short loc_1800076BE
0x1800076a8  mov     rcx, [rsi]; hMutex
0x1800076ab  mov     dword ptr [rsi+8], 0
0x1800076b2  call    cs:__imp_ReleaseMutex
0x1800076b9  nop     dword ptr [rax+rax+00h]
0x1800076be  mov     rcx, r14; lpString
0x1800076c1  mov     ebx, 2
0x1800076c6  call    cs:__imp_lstrlenW
0x1800076cd  nop     dword ptr [rax+rax+00h]
0x1800076d2  mov     esi, 80h
0x1800076d7  lea     rcx, [rbp+0F0h+var_140]; unsigned __int16 *
0x1800076db  inc     eax
0x1800076dd  mov     r8, r14; unsigned __int16 *
0x1800076e0  cmp     eax, esi
0x1800076e2  cmovb   esi, eax
0x1800076e5  movsxd  rdx, esi; unsigned __int64
0x1800076e8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800076ed  mov     rax, [rdi]
0x1800076f0  lea     r14, [rbp+0F0h+var_140]
0x1800076f4  mov     rcx, rdi
0x1800076f7  mov     rax, [rax+10h]
0x1800076fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007700  jmp     short loc_18000777F
0x180007702  test    rsi, rsi
0x180007705  jz      short loc_180007723
0x180007707  add     dword ptr [rsi+0Ch], 0FFFFFFFFh
0x18000770b  jnz     short loc_180007723
0x18000770d  mov     rcx, [rsi]; hMutex
0x180007710  mov     dword ptr [rsi+8], 0
0x180007717  call    cs:__imp_ReleaseMutex
0x18000771e  nop     dword ptr [rax+rax+00h]
0x180007723  xor     ebx, ebx
0x180007725  mov     rcx, r14; lpString
0x180007728  call    cs:__imp_lstrlenW
0x18000772f  nop     dword ptr [rax+rax+00h]
0x180007734  lea     edi, [rax+1]
0x180007737  mov     eax, 2
0x18000773c  movsxd  rcx, edi
0x18000773f  mul     rcx
0x180007742  cmovb   rax, r12
0x180007746  mov     rcx, rax; unsigned __int64
0x180007749  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000774e  mov     [r15], rax
0x180007751  mov     rcx, rax; void *
0x180007754  test    rax, rax
0x180007757  jnz     loc_180007861
0x18000775d  mov     eax, 8007000Eh
0x180007762  jmp     loc_18000787C
0x180007767  mov     ebx, 1
0x18000776c  lea     r14, [rbp+0F0h+var_140]
0x180007770  xor     eax, eax
0x180007772  mov     esi, ebx
  ... truncated ...
```
