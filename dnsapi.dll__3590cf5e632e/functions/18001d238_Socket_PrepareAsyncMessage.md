# Socket_PrepareAsyncMessage

- ea: `0x18001d238`
- end: `0x18001d8f1`
- name: `Socket_PrepareAsyncMessage`
- size: `1721`
- prototype: `__int64 __usercall@<rax>(PVOID pv@<rcx>, HANDLE fl@<rdx>, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001cc18`

## callees

- `0x18001d238`
- `0x18002144c`
- `0x18008b5f0`
- `0x1800cc388`
- `0x1800cd924`
- `0x1800dc9e0`
- `0x1800de650`
- `0x1800dfa80`
- `0x1800e1ed0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d670`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d69a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d670`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d69a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d2b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d2b4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d387`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d387`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001d43d`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001d5d2`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001d43d`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001d5d2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d3e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d51f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d3e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d51f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18001d5b4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18001d5b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d8a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d8a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d56a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d56a`

## pseudocode

```c
__int64 __fastcall Socket_PrepareAsyncMessage(
        _QWORD *pv,
        HANDLE fl,
        unsigned int a3,
        __int64 a4,
        int a5,
        _QWORD *a6,
        _DWORD *a7)
{
  _QWORD *v7; // rax
  __int64 v10; // rbx
  __int64 v11; // rbp
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  struct _TP_TIMER *v16; // r12
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v18; // r12
  DWORD LastError; // edi
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rcx
  HANDLE ProcessHeap; // rax
  _QWORD *v25; // rax
  int v26; // ecx
  __int64 v27; // rdi
  PVOID v28; // r8
  void (__stdcall *v29)(PTP_CALLBACK_INSTANCE, PVOID, PVOID, ULONG, ULONG_PTR, PTP_IO); // rdx
  struct _TP_IO *ThreadpoolIo; // rax
  struct _TP_IO *v31; // rbp
  __int64 v32; // rdx
  __int64 v33; // [rsp+58h] [rbp-60h]
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp-58h] BYREF
  struct _FILETIME v35; // [rsp+68h] [rbp-50h] BYREF

  v7 = a6;
  v10 = pv[11];
  v11 = a3;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
  {
    WPP_SF_qPdldqq((_DWORD)pv, (_DWORD)fl, a3, (_DWORD)pv, (char)fl, a3, 1, a5, (__int64)a6, (__int64)a7);
    v7 = a6;
  }
  if ( a7 )
    *a7 = 1;
  if ( v7 )
    *v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 528));
  *(_DWORD *)(v10 + 524) = 0;
  _InterlockedAdd((volatile signed __int32 *)pv, 1u);
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_qD(1035, 10, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, pv, *(_DWORD *)pv);
  if ( *(_DWORD *)(v10 + 580) )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_(1035, 136, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids);
    LastError = 1223;
    goto LABEL_40;
  }
  if ( (*(_DWORD *)(v10 + 520) & 0x200) != 0 || *((_DWORD *)pv + 108) )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_(1035, 137, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids);
    LastError = *((_DWORD *)pv + 49);
    goto LABEL_38;
  }
  if ( !(_DWORD)v11 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_(1035, 138, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids);
    LastError = 87;
    goto LABEL_40;
  }
  v12 = 352;
  if ( a5 != 2 )
    v12 = 320;
  v33 = v12;
  v13 = 472;
  if ( a5 != 2 )
    v13 = 488;
  v14 = *(_QWORD *)(v13 + v10);
  v15 = 464;
  if ( a5 != 2 )
    v15 = 480;
  *(_QWORD *)(v10 + 496) = *(_QWORD *)(v15 + v10);
  *(_QWORD *)(v10 + 504) = v14;
  v16 = *(struct _TP_TIMER **)(v10 + 512);
  if ( v16 )
  {
    LastError = 0;
    v35 = 0;
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_qD(1035, 19, WPP_0ee542721a7b375122a881c30985be4a_Traceguids, v16, v11);
    v35 = (struct _FILETIME)(-10000 * v11);
    SetThreadpoolTimer(v16, &v35, 0, (unsigned int)v11 / 0xA);
  }
  else
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_qD(1035, 20, WPP_0ee542721a7b375122a881c30985be4a_Traceguids, pv, v11);
    ThreadpoolTimer = CreateThreadpoolTimer(Recv_TimerCallback, pv, 0);
    v18 = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      LastError = 0;
      pftDueTime = 0;
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_qD(1035, 19, WPP_0ee542721a7b375122a881c30985be4a_Traceguids, ThreadpoolTimer, v11);
      pftDueTime = (struct _FILETIME)(-10000 * v11);
      SetThreadpoolTimer(v18, &pftDueTime, 0, (unsigned int)v11 / 0xA);
      *(_QWORD *)(v10 + 512) = v18;
    }
    else
    {
      LastError = GetLastError();
    }
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_qD(1035, 21, WPP_0ee542721a7b375122a881c30985be4a_Traceguids, *(_QWORD *)(v10 + 512), LastError);
    if ( LastError )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
        return LastError;
      v32 = 139;
      goto LABEL_62;
    }
  }
  v20 = *(_QWORD *)(v10 + 496);
  if ( v20 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_qqdd(v20, 142, (unsigned int)WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids, v10, v20);
    if ( *(_DWORD *)(v10 + 572) )
    {
      if ( a7 )
        *a7 = 0;
      goto LABEL_35;
    }
    StartThreadpoolIo(*(PTP_IO *)(v10 + 496));
LABEL_34:
    AddRefSendBlob(pv);
    *(_DWORD *)(v10 + 524) |= 0x10u;
LABEL_35:
    v21 = *(_QWORD *)(v10 + 496);
    v22 = *(_QWORD *)(v10 + 504);
    if ( a5 == 2 )
    {
      *(_QWORD *)(v10 + 464) = v21;
      *(_QWORD *)(v10 + 472) = v22;
    }
    else
    {
      *(_QWORD *)(v10 + 480) = v21;
      *(_QWORD *)(v10 + 488) = v22;
    }
    *a6 = v10 + v33;
LABEL_38:
    if ( !LastError )
      *(_DWORD *)(v10 + 520) |= 0x80u;
    goto LABEL_40;
  }
  LastError = 8;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_qD(1035, 140, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids, v10, *(unsigned __int8 *)(v10 + 658));
  if ( *(_BYTE *)(v10 + 658) )
  {
    ProcessHeap = g_hProcessHeap;
    if ( !g_hProcessHeap )
    {
      ProcessHeap = GetProcessHeap();
      g_hProcessHeap = ProcessHeap;
    }
    v25 = HeapAlloc(ProcessHeap, 8u, 8u);
    *(_QWORD *)(v10 + 504) = v25;
    if ( !v25 )
      goto LABEL_40;
    *v25 = pv;
    v27 = *(_QWORD *)(v10 + 504);
    *(_QWORD *)(v10 + 496) = 0;
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_qql(v26, 16, (unsigned int)WPP_0ee542721a7b375122a881c30985be4a_Traceguids, (_DWORD)fl, v27);
    v28 = (PVOID)v27;
    v29 = Recv_CacheIoCompletionCb;
  }
  else
  {
    *(_QWORD *)(v10 + 496) = 0;
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_qql(v20, 16, (unsigned int)WPP_0ee542721a7b375122a881c30985be4a_Traceguids, (_DWORD)fl, (__int64)pv);
    v28 = pv;
    v29 = (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PVOID, ULONG, ULONG_PTR, PTP_IO))Recv_IoCompletionCallback;
  }
  ThreadpoolIo = CreateThreadpoolIo(fl, v29, v28, 0);
  v31 = ThreadpoolIo;
  if ( ThreadpoolIo )
  {
    LastError = 0;
    StartThreadpoolIo(ThreadpoolIo);
    *(_QWORD *)(v10 + 496) = v31;
  }
  else
  {
    LastError = GetLastError();
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_qD(1035, 17, WPP_0ee542721a7b375122a881c30985be4a_Traceguids, *(_QWORD *)(v10 + 496), LastError);
  if ( !LastError )
    goto LABEL_34;
  if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
    return LastError;
  v32 = 141;
LABEL_62:
  WPP_SF_d(1035, v32, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids, LastError);
LABEL_40:
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 143, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x18001d238  mov     [rsp+arg_18], rbx
0x18001d23d  push    rbp
0x18001d23e  push    rsi
0x18001d23f  push    rdi
0x18001d240  push    r12
0x18001d242  push    r13
0x18001d244  push    r14
0x18001d246  push    r15
0x18001d248  sub     rsp, 80h
0x18001d24f  mov     rax, cs:__security_cookie
0x18001d256  xor     rax, rsp
0x18001d259  mov     [rsp+0B8h+var_48], rax
0x18001d25e  mov     rax, [rsp+0B8h+arg_28]
0x18001d266  mov     r13, rdx
0x18001d269  mov     r15, [rsp+0B8h+arg_30]
0x18001d271  mov     rsi, rcx
0x18001d274  mov     rbx, [rcx+58h]
0x18001d278  mov     [rsp+0B8h+var_68], rax
0x18001d27d  mov     ebp, r8d
0x18001d280  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18001d287  mov     r14d, 1
0x18001d28d  mov     edi, [rsp+0B8h+arg_20]
0x18001d294  jnz     loc_18001D6C5
0x18001d29a  xor     r12d, r12d
0x18001d29d  test    r15, r15
0x18001d2a0  jz      short loc_18001D2A5
0x18001d2a2  mov     [r15], r14d
0x18001d2a5  test    rax, rax
0x18001d2a8  jz      short loc_18001D2AD
0x18001d2aa  mov     [rax], r12
0x18001d2ad  lea     rcx, [rbx+210h]; lpCriticalSection
0x18001d2b4  call    cs:__imp_EnterCriticalSection
0x18001d2bb  nop     dword ptr [rax+rax+00h]
0x18001d2c0  mov     [rbx+20Ch], r12d
0x18001d2c7  lock add [rsi], r14d
0x18001d2cb  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18001d2d2  mov     r8d, 40Bh
0x18001d2d8  jnz     loc_18001D78D
0x18001d2de  lea     rax, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x18001d2e5  cmp     [rbx+244h], r12d
0x18001d2ec  jnz     loc_18001D625
0x18001d2f2  test    dword ptr [rbx+208h], 200h
0x18001d2fc  jnz     loc_18001D6AD
0x18001d302  cmp     [rsi+1B0h], r12d
0x18001d309  jnz     loc_18001D6AD
0x18001d30f  test    ebp, ebp
0x18001d311  jz      loc_18001D6F3
0x18001d317  cmp     edi, 2
0x18001d31a  mov     eax, 160h
0x18001d31f  lea     ecx, [rax-20h]
0x18001d322  cmovnz  eax, ecx
0x18001d325  mov     [rsp+0B8h+var_60], rax
0x18001d32a  mov     eax, 1D8h
0x18001d32f  lea     ecx, [rax+10h]
0x18001d332  cmovnz  eax, ecx
0x18001d335  mov     rcx, [rax+rbx]
0x18001d339  mov     eax, 1D0h
0x18001d33e  lea     edx, [rax+10h]
0x18001d341  cmovnz  eax, edx
0x18001d344  mov     rax, [rax+rbx]
0x18001d348  mov     [rbx+1F0h], rax
0x18001d34f  mov     [rbx+1F8h], rcx
0x18001d356  mov     r12, [rbx+200h]
0x18001d35d  test    r12, r12
0x18001d360  jnz     loc_18001D4D6
0x18001d366  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18001d36d  lea     r14, WPP_0ee542721a7b375122a881c30985be4a_Traceguids
0x18001d374  jnz     loc_18001D83B
0x18001d37a  xor     r8d, r8d; pcbe
0x18001d37d  lea     rcx, Recv_TimerCallback; pfnti
0x18001d384  mov     rdx, rsi; pv
0x18001d387  call    cs:__imp_CreateThreadpoolTimer
0x18001d38e  nop     dword ptr [rax+rax+00h]
0x18001d393  mov     r12, rax
0x18001d396  test    rax, rax
0x18001d399  jz      loc_18001D670
0x18001d39f  xor     edi, edi
0x18001d3a1  mov     qword ptr [rsp+0B8h+pftDueTime.dwLowDateTime], rdi
0x18001d3a6  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18001d3ad  jnz     loc_18001D7D7
0x18001d3b3  imul    rax, rbp, 0FFFFFFFFFFFFD8F0h
0x18001d3ba  xor     r8d, r8d; msPeriod
0x18001d3bd  mov     rcx, rax
0x18001d3c0  mov     [rsp+0B8h+pftDueTime.dwLowDateTime], eax
0x18001d3c4  shr     rcx, 20h
0x18001d3c8  mov     eax, 0CCCCCCCDh
0x18001d3cd  mul     ebp
0x18001d3cf  mov     [rsp+0B8h+pftDueTime.dwHighDateTime], ecx
0x18001d3d3  mov     rcx, r12; pti
0x18001d3d6  shr     edx, 3
0x18001d3d9  mov     r9d, edx; msWindowLength
0x18001d3dc  lea     rdx, [rsp+0B8h+pftDueTime]; pftDueTime
0x18001d3e1  call    cs:__imp_SetThreadpoolTimer
0x18001d3e8  nop     dword ptr [rax+rax+00h]
0x18001d3ed  mov     [rbx+200h], r12
0x18001d3f4  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18001d3fb  jnz     loc_18001D857
0x18001d401  xor     r12d, r12d
0x18001d404  test    edi, edi
0x18001d406  jnz     loc_18001D683
0x18001d40c  mov     rcx, [rbx+1F0h]
0x18001d413  test    rcx, rcx
0x18001d416  jz      loc_18001D533
0x18001d41c  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18001d423  jnz     loc_18001D75D
0x18001d429  cmp     [rbx+23Ch], r12d
0x18001d430  jnz     loc_18001D63C
0x18001d436  mov     rcx, [rbx+1F0h]; pio
0x18001d43d  call    cs:__imp_StartThreadpoolIo
0x18001d444  nop     dword ptr [rax+rax+00h]
0x18001d449  mov     rcx, rsi
0x18001d44c  call    AddRefSendBlob
0x18001d451  or      dword ptr [rbx+20Ch], 10h
0x18001d458  mov     rdx, [rsp+0B8h+var_60]
0x18001d45d  mov     rax, [rbx+1F0h]
0x18001d464  add     rdx, rbx
0x18001d467  cmp     [rsp+0B8h+arg_20], 2
0x18001d46f  mov     rcx, [rbx+1F8h]
0x18001d476  jz      loc_18001D728
0x18001d47c  mov     [rbx+1E0h], rax
0x18001d483  mov     [rbx+1E8h], rcx
0x18001d48a  mov     rax, [rsp+0B8h+var_68]
0x18001d48f  mov     [rax], rdx
0x18001d492  test    edi, edi
0x18001d494  jnz     short loc_18001D49E
0x18001d496  bts     dword ptr [rbx+208h], 7
0x18001d49e  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18001d4a5  jnz     loc_18001D70A
0x18001d4ab  mov     eax, edi
0x18001d4ad  mov     rcx, [rsp+0B8h+var_48]
0x18001d4b2  xor     rcx, rsp; StackCookie
0x18001d4b5  call    __security_check_cookie
0x18001d4ba  mov     rbx, [rsp+0B8h+arg_18]
0x18001d4c2  add     rsp, 80h
0x18001d4c9  pop     r15
0x18001d4cb  pop     r14
0x18001d4cd  pop     r13
0x18001d4cf  pop     r12
0x18001d4d1  pop     rdi
0x18001d4d2  pop     rsi
0x18001d4d3  pop     rbp
0x18001d4d4  retn
0x18001d4d6  xor     edi, edi
0x18001d4d8  mov     qword ptr [rsp+0B8h+var_50.dwLowDateTime], rdi
0x18001d4dd  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18001d4e4  lea     r14, WPP_0ee542721a7b375122a881c30985be4a_Traceguids
0x18001d4eb  jnz     loc_18001D7F5
0x18001d4f1  imul    rax, rbp, 0FFFFFFFFFFFFD8F0h
0x18001d4f8  xor     r8d, r8d; msPeriod
0x18001d4fb  mov     rcx, rax
0x18001d4fe  mov     [rsp+0B8h+var_50.dwLowDateTime], eax
0x18001d502  shr     rcx, 20h
0x18001d506  mov     eax, 0CCCCCCCDh
0x18001d50b  mul     ebp
0x18001d50d  mov     [rsp+0B8h+var_50.dwHighDateTime], ecx
0x18001d511  mov     rcx, r12; pti
0x18001d514  shr     edx, 3
0x18001d517  mov     r9d, edx; msWindowLength
0x18001d51a  lea     rdx, [rsp+0B8h+var_50]; pftDueTime
0x18001d51f  call    cs:__imp_SetThreadpoolTimer
0x18001d526  nop     dword ptr [rax+rax+00h]
0x18001d52b  xor     r12d, r12d
0x18001d52e  jmp     loc_18001D40C
0x18001d533  mov     edi, 8
0x18001d538  test    byte ptr cs:xmmword_1801119E0+1, dil
0x18001d53f  jnz     loc_18001D879
0x18001d545  cmp     [rbx+292h], r12b
0x18001d54c  jz      loc_18001D64D
0x18001d552  mov     rax, cs:g_hProcessHeap
0x18001d559  test    rax, rax
0x18001d55c  jz      loc_18001D8A2
0x18001d562  mov     r8, rdi; dwBytes
0x18001d565  mov     edx, edi; dwFlags
0x18001d567  mov     rcx, rax; hHeap
0x18001d56a  call    cs:__imp_HeapAlloc
0x18001d571  nop     dword ptr [rax+rax+00h]
0x18001d576  mov     [rbx+1F8h], rax
0x18001d57d  test    rax, rax
0x18001d580  jz      loc_18001D49E
0x18001d586  mov     [rax], rsi
0x18001d589  mov     rdi, [rbx+1F8h]
0x18001d590  mov     [rbx+1F0h], r12
0x18001d597  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18001d59e  jnz     loc_18001D73B
0x18001d5a4  mov     r8, rdi; pv
0x18001d5a7  lea     rdx, Recv_CacheIoCompletionCb; pfnio
0x18001d5ae  xor     r9d, r9d; pcbe
0x18001d5b1  mov     rcx, r13; fl
0x18001d5b4  call    cs:__imp_CreateThreadpoolIo
0x18001d5bb  nop     dword ptr [rax+rax+00h]
0x18001d5c0  mov     rbp, rax
0x18001d5c3  test    rax, rax
0x18001d5c6  jz      loc_18001D69A
0x18001d5cc  mov     rcx, rax; pio
0x18001d5cf  mov     edi, r12d
0x18001d5d2  call    cs:__imp_StartThreadpoolIo
0x18001d5d9  nop     dword ptr [rax+rax+00h]
0x18001d5de  mov     [rbx+1F0h], rbp
0x18001d5e5  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18001d5ec  jnz     loc_18001D8BA
0x18001d5f2  test    edi, edi
0x18001d5f4  jz      loc_18001D449
0x18001d5fa  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18001d601  jz      loc_18001D4AB
0x18001d607  mov     edx, 8Dh
0x18001d60c  mov     ecx, 40Bh
0x18001d611  lea     r8, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x18001d618  mov     r9d, edi
0x18001d61b  call    WPP_SF_d
0x18001d620  jmp     loc_18001D49E
0x18001d625  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18001d62c  jnz     loc_18001D811
0x18001d632  mov     edi, 4C7h
0x18001d637  jmp     loc_18001D49E
0x18001d63c  test    r15, r15
0x18001d63f  jz      loc_18001D458
0x18001d645  mov     [r15], r12d
0x18001d648  jmp     loc_18001D458
0x18001d64d  mov     [rbx+1F0h], r12
0x18001d654  test    byte ptr cs:xmmword_1801119E0+1, dil
0x18001d65b  jnz     loc_18001D7B5
0x18001d661  mov     r8, rsi
0x18001d664  lea     rdx, Recv_IoCompletionCallback
0x18001d66b  jmp     loc_18001D5AE
0x18001d670  call    cs:__imp_GetLastError
0x18001d677  nop     dword ptr [rax+rax+00h]
0x18001d67c  mov     edi, eax
0x18001d67e  jmp     loc_18001D3F4
0x18001d683  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18001d68a  jz      loc_18001D4AB
0x18001d690  mov     edx, 8Bh
0x18001d695  jmp     loc_18001D60C
0x18001d69a  call    cs:__imp_GetLastError
0x18001d6a1  nop     dword ptr [rax+rax+00h]
0x18001d6a6  mov     edi, eax
0x18001d6a8  jmp     loc_18001D5E5
0x18001d6ad  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18001d6b4  jnz     loc_18001D8DC
0x18001d6ba  mov     edi, [rsi+0C4h]
0x18001d6c0  jmp     loc_18001D492
0x18001d6c5  mov     [rsp+0B8h+var_70], r15
0x18001d6ca  mov     r9, rsi
0x18001d6cd  mov     [rsp+0B8h+var_78], rax
0x18001d6d2  mov     [rsp+0B8h+var_80], edi
0x18001d6d6  mov     [rsp+0B8h+var_88], r14d
0x18001d6db  mov     [rsp+0B8h+var_90], ebp
0x18001d6df  mov     [rsp+0B8h+var_98], r13
0x18001d6e4  call    WPP_SF_qPdldqq
0x18001d6e9  mov     rax, [rsp+0B8h+var_68]
0x18001d6ee  jmp     loc_18001D29A
0x18001d6f3  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18001d6fa  jnz     loc_18001D826
0x18001d700  mov     edi, 57h ; 'W'
0x18001d705  jmp     loc_18001D49E
0x18001d70a  mov     edx, 8Fh
0x18001d70f  lea     r8, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x18001d716  mov     ecx, 40Bh
0x18001d71b  mov     r9d, edi
0x18001d71e  call    WPP_SF_d
0x18001d723  jmp     loc_18001D4AB
0x18001d728  mov     [rbx+1D0h], rax
0x18001d72f  mov     [rbx+1D8h], rcx
0x18001d736  jmp     loc_18001D48A
0x18001d73b  mov     edx, 10h
0x18001d740  mov     [rsp+0B8h+var_90], 1
0x18001d748  mov     r9, r13
0x18001d74b  mov     [rsp+0B8h+var_98], rdi
0x18001d750  mov     r8, r14
0x18001d753  call    WPP_SF_qql
0x18001d758  jmp     loc_18001D5A4
0x18001d75d  mov     eax, [rbx+23Ch]
0x18001d763  lea     r8, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x18001d76a  mov     [rsp+0B8h+var_88], 1
0x18001d772  mov     edx, 8Eh
0x18001d777  mov     [rsp+0B8h+var_90], eax
0x18001d77b  mov     r9, rbx
0x18001d77e  mov     [rsp+0B8h+var_98], rcx
0x18001d783  call    WPP_SF_qqdd
0x18001d788  jmp     loc_18001D429
0x18001d78d  mov     eax, [rsi]
0x18001d78f  mov     ecx, r8d
0x18001d792  lea     r8, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids
0x18001d799  mov     dword ptr [rsp+0B8h+var_98], eax
0x18001d79d  mov     edx, 0Ah
0x18001d7a2  mov     r9, rsi
0x18001d7a5  call    WPP_SF_qD
0x18001d7aa  mov     r8d, 40Bh
0x18001d7b0  jmp     loc_18001D2DE
0x18001d7b5  mov     edx, 10h
0x18001d7ba  mov     [rsp+0B8h+var_90], 1
0x18001d7c2  mov     r9, r13
0x18001d7c5  mov     [rsp+0B8h+var_98], rsi
0x18001d7ca  mov     r8, r14
0x18001d7cd  call    WPP_SF_qql
0x18001d7d2  jmp     loc_18001D661
0x18001d7d7  mov     edx, 13h
0x18001d7dc  mov     dword ptr [rsp+0B8h+var_98], ebp
0x18001d7e0  mov     ecx, 40Bh
0x18001d7e5  mov     r9, r12
0x18001d7e8  mov     r8, r14
  ... truncated ...
```
