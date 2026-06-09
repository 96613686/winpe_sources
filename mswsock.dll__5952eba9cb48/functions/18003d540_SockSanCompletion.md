# SockSanCompletion

- ea: `0x18003d540`
- end: `0x18003dae2`
- name: `SockSanCompletion`
- size: `1442`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x180017810`
- `0x180018ea0`

## callees

- `0x180008250`
- `0x18000d000`
- `0x180014e38`
- `0x1800248fc`
- `0x180024f14`
- `0x180037195`
- `0x180038118`
- `0x18003ae8c`
- `0x18003aefc`
- `0x18003d540`
- `0x18003dae8`
- `0x180041b44`
- `0x180042128`
- `0x180047cb0`
- `0x180049b2c`
- `0x18004bfb8`
- `0x1800514d0`
- `0x18005284c`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003d574`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003d574`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d7fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d90b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003da94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d7fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d90b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003da94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d68b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d7e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d8c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d68b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d7e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d8c8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003d859`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003d859`
- `WS2_32!WahReferenceContextByHandle` at `0x18003d6c1`
- `WS2_32!WahReferenceContextByHandle` at `0x18003d6c1`

## pseudocode

```c
void __fastcall SockSanCompletion(__int64 *a1, _DWORD *a2)
{
  char v3; // r13
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdi
  __int64 *v8; // r14
  __int64 v9; // rbp
  __int64 v10; // r9
  void *v11; // rsi
  int v12; // r15d
  __int64 **v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // r12d
  __int64 **v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 HeapRoutine; // rax
  unsigned int v20; // eax
  __int64 v21; // rdx
  int v22; // [rsp+A0h] [rbp+8h] BYREF
  __int64 v23; // [rsp+A8h] [rbp+10h] BYREF
  unsigned int v24; // [rsp+B0h] [rbp+18h] BYREF

  v3 = 0;
  LODWORD(v23) = 0;
  v24 = 0;
  v22 = 0;
  TlsGetValue(MSAFD_SockTlsSlot);
  v7 = a1[1];
  v8 = a1 - 2;
  v9 = *a1;
  if ( (BYTE2(xmmword_180063D60) & 4) != 0 )
    WPP_SF_q(1042, 29, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, a1[1]);
  v10 = (unsigned int)*a2;
  if ( !(_DWORD)v10 || (_DWORD)v10 == 261 )
  {
    v11 = (void *)WahReferenceContextByHandle(SockContextTable, a1[2]);
    if ( !v11 )
    {
      v11 = SockImportHandle((HANDLE)a1[2], &v22, 0);
      if ( v11 || v22 == 1 && (v11 = (void *)SockSanHandleImportFailure(a1[2], (__int64 *)v9)) != 0 )
      {
        if ( SBYTE2(xmmword_180063D60) < 0 )
          WPP_SF_qq(1047, 30, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v11, *((_QWORD *)v11 + 1));
        CloseSanHandle(v9);
        v3 = 1;
      }
    }
    *a2 = 0;
    v10 = 0;
    if ( v11 && v7 )
    {
      if ( *((_QWORD *)v11 + 33) )
      {
        if ( !(unsigned __int8)CleanupTPSock(v11, v7, v6, 0) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 676), 0xFFFFFFFF) == 1 )
            SockSanDeleteHalfAcceptedSocket((char *)v7);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 676), 0xFFFFFFFF) == 1 )
            SockSanDeleteHalfAcceptedSocket((char *)v7);
          v7 = 0;
          v12 = -1073741823;
          goto LABEL_17;
        }
        v7 = *((_QWORD *)v11 + 33);
      }
      else
      {
        *((_QWORD *)v11 + 33) = v7;
        _InterlockedIncrement((volatile signed __int32 *)v11);
        _InterlockedIncrement((volatile signed __int32 *)v11);
        *(_QWORD *)v7 = v11;
        *(_QWORD *)(v7 + 8) = v11;
      }
      if ( (*((_BYTE *)v11 + 72) & 1) != 0 )
        *(_DWORD *)(v7 + 32) = 1;
      if ( v3 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 48));
        *(_BYTE *)(v7 + 209) = 1;
        LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 48));
      }
      *((_BYTE *)v11 + 69) |= 8u;
      _InterlockedIncrement(*(volatile signed __int32 **)(v7 + 8));
      _InterlockedIncrement(*(volatile signed __int32 **)(v7 + 8));
      if ( (BYTE2(xmmword_180063D60) & 4) != 0 )
        WPP_SF_q(1042, 32, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, *((_QWORD *)v11 + 1));
      PostAllReceives((PVOID)v7);
      while ( *(_DWORD *)(v7 + 36) && !*(_DWORD *)(v7 + 136) )
        Sleep(0);
      SendControlMessage((PVOID)v7, 0, 0);
      memcpy_0(*((void **)v11 + 22), (char *)v8 + 86, *((unsigned __int16 *)v8 + 42) + 2LL);
      memcpy_0(
        *((void **)v11 + 21),
        (char *)v8 + *((unsigned __int16 *)v8 + 42) + 90,
        *(unsigned __int16 *)((char *)v8 + *((unsigned __int16 *)v8 + 42) + 88) + 2LL);
      v15 = *((_DWORD *)a1 + 6);
      EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 48));
      v16 = (__int64 **)(v9 + 680);
      v8[3] = 0;
      v17 = *(_QWORD *)(v9 + 680);
      if ( *(_QWORD *)(v17 + 8) != v9 + 680 )
LABEL_26:
        __fastfail(3u);
      *v8 = v17;
      v8[1] = (__int64)v16;
      *(_QWORD *)(v17 + 8) = v8;
      *v16 = v8;
      --*(_DWORD *)(v9 + 676);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 48));
      v8 = 0;
      if ( v15 )
      {
        HeapRoutine = SockAllocateHeapRoutine(SockPrivateHeap, 0, v15);
        *(_QWORD *)(v7 + 632) = HeapRoutine;
        if ( HeapRoutine )
        {
          *(_DWORD *)(v7 + 624) = v15;
          *(_QWORD *)(v7 + 664) = HeapRoutine;
          LODWORD(v23) = 0;
          _InterlockedIncrement(*(volatile signed __int32 **)(v7 + 8));
          v20 = HandleApplicationRecv(
                  (char *)v7,
                  (_DWORD *)(v7 + 624),
                  1u,
                  &v24,
                  &v23,
                  (_QWORD *)(v7 + 640),
                  AcceptExRecvCompletionRoutine,
                  ConnectThreadHandle,
                  1u,
                  0,
                  0);
          if ( !v20 || v20 == 997 )
          {
            v12 = 0;
LABEL_17:
            if ( *((_QWORD *)v11 + 33)
              && *((_DWORD *)v11 + 6) == 4
              && (*(_BYTE *)(*((_QWORD *)v11 + 33) + 800LL) & 0x40) == 0 )
            {
              SockSanCloseSocket(v11);
            }
            if ( !_InterlockedDecrement((volatile signed __int32 *)v11) )
              SockDestroySocket((__int64)v11, v5, v6);
            goto LABEL_23;
          }
          if ( (xmmword_180063D60 & 2) != 0 )
            WPP_SF_d(1025, 33, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v20);
        }
      }
      if ( (BYTE2(xmmword_180063D60) & 4) != 0 )
        WPP_SF_qq(1042, 34, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, *(_QWORD *)(*(_QWORD *)v7 + 8LL), v7);
      v12 = AfdCompleteAccept(
              v18,
              *(_QWORD *)(*(_QWORD *)v7 + 8LL),
              *(_QWORD *)(v7 + 216) + 24LL,
              *(_QWORD *)(v7 + 632),
              *(_DWORD *)(v7 + 624));
      if ( v12 )
      {
        v21 = (unsigned int)_InterlockedDecrement(*(volatile signed __int32 **)(v7 + 8));
        if ( !(_DWORD)v21 )
          SockDestroySocket(*(_QWORD *)(v7 + 8), v21, v6);
        AbortSanConnection(v7);
      }
      goto LABEL_17;
    }
  }
  else
  {
    v11 = 0;
  }
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_d(1025, 31, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v10);
  if ( *a2 == -1073741816 )
    CloseSanHandle(v9);
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 676), 0xFFFFFFFF) == 1 )
      SockSanDeleteHalfAcceptedSocket((char *)v7);
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v7 + 676)) )
      SockSanDeleteHalfAcceptedSocket((char *)v7);
    v7 = 0;
  }
  v12 = -1073741823;
  if ( v11 )
    goto LABEL_17;
LABEL_23:
  if ( v7 )
  {
    if ( v8 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 48));
      v13 = (__int64 **)(v9 + 680);
      v8[3] = 0;
      v14 = *(_QWORD *)(v9 + 680);
      if ( *(_QWORD *)(v14 + 8) != v9 + 680 )
        goto LABEL_26;
      *v8 = v14;
      v8[1] = (__int64)v13;
      *(_QWORD *)(v14 + 8) = v8;
      *v13 = v8;
      --*(_DWORD *)(v9 + 676);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 48));
    }
    if ( _InterlockedExchangeAdd(*(volatile signed __int32 **)(v9 + 8), 0xFFFFFFFF) == 1 )
      SockDestroySocket(*(_QWORD *)(v9 + 8), v5, v6);
  }
  if ( v3 )
  {
    if ( v12 )
      SockCloseSocket((__int64)v11);
  }
}

```

## disassembly

```asm
0x18003d540  mov     rax, rsp
0x18003d543  mov     [rax+20h], rbx
0x18003d547  push    rbp
0x18003d548  push    rsi
0x18003d549  push    rdi
0x18003d54a  push    r12
0x18003d54c  push    r13
0x18003d54e  push    r14
0x18003d550  push    r15
0x18003d552  sub     rsp, 60h
0x18003d556  xor     r12d, r12d
0x18003d559  mov     r15, rcx
0x18003d55c  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x18003d562  mov     r13b, r12b
0x18003d565  mov     [rax+10h], r12d
0x18003d569  mov     rbx, rdx
0x18003d56c  mov     [rax+18h], r12d
0x18003d570  mov     [rax+8], r12d
0x18003d574  call    cs:__imp_TlsGetValue
0x18003d57b  nop     dword ptr [rax+rax+00h]
0x18003d580  mov     rdi, [r15+8]
0x18003d584  lea     r14, [r15-10h]
0x18003d588  mov     rbp, [r15]
0x18003d58b  test    byte ptr cs:xmmword_180063D60+2, 4
0x18003d592  jz      short loc_18003D5AD
0x18003d594  lea     edx, [r12+1Dh]
0x18003d599  mov     ecx, 412h
0x18003d59e  mov     r9, rdi
0x18003d5a1  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18003d5a8  call    WPP_SF_q
0x18003d5ad  mov     r9d, [rbx]
0x18003d5b0  test    r9d, r9d
0x18003d5b3  jz      loc_18003D6B6
0x18003d5b9  cmp     r9d, 105h
0x18003d5c0  jz      loc_18003D6B6
0x18003d5c6  mov     rsi, r12
0x18003d5c9  test    byte ptr cs:xmmword_180063D60, 2
0x18003d5d0  jz      short loc_18003D5E8
0x18003d5d2  mov     edx, 1Fh
0x18003d5d7  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18003d5de  mov     ecx, 401h
0x18003d5e3  call    WPP_SF_d
0x18003d5e8  cmp     dword ptr [rbx], 0C0000008h
0x18003d5ee  jnz     short loc_18003D5F8
0x18003d5f0  mov     rcx, rbp
0x18003d5f3  call    CloseSanHandle
0x18003d5f8  or      ebx, 0FFFFFFFFh
0x18003d5fb  test    rdi, rdi
0x18003d5fe  jz      short loc_18003D62F
0x18003d600  mov     eax, ebx
0x18003d602  lock xadd [rdi+2A4h], eax
0x18003d60a  add     eax, ebx
0x18003d60c  jnz     short loc_18003D616
0x18003d60e  mov     rcx, rdi; P
0x18003d611  call    SockSanDeleteHalfAcceptedSocket
0x18003d616  mov     eax, ebx
0x18003d618  lock xadd [rdi+2A4h], eax
0x18003d620  add     eax, ebx
0x18003d622  jnz     short loc_18003D62C
0x18003d624  mov     rcx, rdi; P
0x18003d627  call    SockSanDeleteHalfAcceptedSocket
0x18003d62c  mov     rdi, r12
0x18003d62f  mov     r15d, 0C0000001h
0x18003d635  test    rsi, rsi
0x18003d638  jz      short loc_18003D675
0x18003d63a  cmp     [rsi+108h], r12
0x18003d641  jz      short loc_18003D663
0x18003d643  mov     eax, [rsi+18h]
0x18003d646  cmp     eax, 4
0x18003d649  jnz     short loc_18003D663
0x18003d64b  mov     rax, [rsi+108h]
0x18003d652  test    byte ptr [rax+320h], 40h
0x18003d659  jnz     short loc_18003D663
0x18003d65b  mov     rcx, rsi
0x18003d65e  call    SockSanCloseSocket
0x18003d663  mov     eax, ebx
0x18003d665  lock xadd [rsi], eax
0x18003d669  add     eax, ebx
0x18003d66b  jnz     short loc_18003D675
0x18003d66d  mov     rcx, rsi
0x18003d670  call    SockDestroySocket
0x18003d675  test    rdi, rdi
0x18003d678  jz      loc_18003DAB7
0x18003d67e  test    r14, r14
0x18003d681  jz      loc_18003DAA0
0x18003d687  lea     rcx, [rbp+30h]; lpCriticalSection
0x18003d68b  call    cs:__imp_EnterCriticalSection
0x18003d692  nop     dword ptr [rax+rax+00h]
0x18003d697  lea     rax, [rbp+2A8h]
0x18003d69e  mov     [r14+18h], r12
0x18003d6a2  mov     rcx, [rax]
0x18003d6a5  cmp     [rcx+8], rax
0x18003d6a9  jz      loc_18003DA7C
0x18003d6af  mov     ecx, 3
0x18003d6b4  int     29h; Win8: RtlFailFast(ecx)
0x18003d6b6  mov     rdx, [r15+10h]
0x18003d6ba  mov     rcx, cs:SockContextTable
0x18003d6c1  call    cs:__imp_WahReferenceContextByHandle
0x18003d6c8  nop     dword ptr [rax+rax+00h]
0x18003d6cd  mov     rsi, rax
0x18003d6d0  test    rax, rax
0x18003d6d3  jnz     short loc_18003D745
0x18003d6d5  mov     rcx, [r15+10h]; FileHandle
0x18003d6d9  lea     rdx, [rsp+98h+arg_0]
0x18003d6e1  xor     r8d, r8d
0x18003d6e4  call    SockImportHandle
0x18003d6e9  mov     rsi, rax
0x18003d6ec  test    rax, rax
0x18003d6ef  jnz     short loc_18003D70F
0x18003d6f1  cmp     [rsp+98h+arg_0], 1
0x18003d6f9  jnz     short loc_18003D745
0x18003d6fb  mov     rcx, [r15+10h]
0x18003d6ff  mov     rdx, rbp
0x18003d702  call    SockSanHandleImportFailure
0x18003d707  mov     rsi, rax
0x18003d70a  test    rax, rax
0x18003d70d  jz      short loc_18003D745
0x18003d70f  cmp     byte ptr cs:xmmword_180063D60+2, r12b
0x18003d716  jge     short loc_18003D73A
0x18003d718  mov     rax, [rsi+8]
0x18003d71c  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18003d723  mov     edx, 1Eh
0x18003d728  mov     [rsp+98h+var_78], rax
0x18003d72d  mov     ecx, 417h
0x18003d732  mov     r9, rsi
0x18003d735  call    WPP_SF_qq
0x18003d73a  mov     rcx, rbp
0x18003d73d  call    CloseSanHandle
0x18003d742  mov     r13b, 1
0x18003d745  mov     [rbx], r12d
0x18003d748  mov     r9d, r12d
0x18003d74b  test    rsi, rsi
0x18003d74e  jz      loc_18003D5C9
0x18003d754  test    rdi, rdi
0x18003d757  jz      loc_18003D5C9
0x18003d75d  cmp     [rsi+108h], r12
0x18003d764  jz      short loc_18003D7BB
0x18003d766  mov     rdx, rdi
0x18003d769  mov     rcx, rsi
0x18003d76c  call    CleanupTPSock
0x18003d771  test    al, al
0x18003d773  jz      short loc_18003D77E
0x18003d775  mov     rdi, [rsi+108h]
0x18003d77c  jmp     short loc_18003D7CF
0x18003d77e  or      ebx, 0FFFFFFFFh
0x18003d781  mov     eax, ebx
0x18003d783  lock xadd [rdi+2A4h], eax
0x18003d78b  add     eax, ebx
0x18003d78d  jnz     short loc_18003D797
0x18003d78f  mov     rcx, rdi; P
0x18003d792  call    SockSanDeleteHalfAcceptedSocket
0x18003d797  mov     eax, ebx
0x18003d799  lock xadd [rdi+2A4h], eax
0x18003d7a1  add     eax, ebx
0x18003d7a3  jnz     short loc_18003D7AD
0x18003d7a5  mov     rcx, rdi; P
0x18003d7a8  call    SockSanDeleteHalfAcceptedSocket
0x18003d7ad  mov     rdi, r12
0x18003d7b0  mov     r15d, 0C0000001h
0x18003d7b6  jmp     loc_18003D63A
0x18003d7bb  mov     [rsi+108h], rdi
0x18003d7c2  lock inc dword ptr [rsi]
0x18003d7c5  lock inc dword ptr [rsi]
0x18003d7c8  mov     [rdi], rsi
0x18003d7cb  mov     [rdi+8], rsi
0x18003d7cf  test    byte ptr [rsi+48h], 1
0x18003d7d3  jz      short loc_18003D7DC
0x18003d7d5  mov     dword ptr [rdi+20h], 1
0x18003d7dc  test    r13b, r13b
0x18003d7df  jz      short loc_18003D808
0x18003d7e1  lea     rcx, [rdi+30h]; lpCriticalSection
0x18003d7e5  call    cs:__imp_EnterCriticalSection
0x18003d7ec  nop     dword ptr [rax+rax+00h]
0x18003d7f1  lea     rcx, [rdi+30h]; lpCriticalSection
0x18003d7f5  mov     byte ptr [rdi+0D1h], 1
0x18003d7fc  call    cs:__imp_LeaveCriticalSection
0x18003d803  nop     dword ptr [rax+rax+00h]
0x18003d808  or      byte ptr [rsi+45h], 8
0x18003d80c  mov     rax, [rdi+8]
0x18003d810  lock inc dword ptr [rax]
0x18003d813  mov     rax, [rdi+8]
0x18003d817  lock inc dword ptr [rax]
0x18003d81a  test    byte ptr cs:xmmword_180063D60+2, 4
0x18003d821  jz      short loc_18003D83D
0x18003d823  mov     r9, [rsi+8]
0x18003d827  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18003d82e  mov     edx, 20h ; ' '
0x18003d833  mov     ecx, 412h
0x18003d838  call    WPP_SF_q
0x18003d83d  lea     rdx, [rdi+0E0h]
0x18003d844  mov     rcx, rdi
0x18003d847  call    PostAllReceives
0x18003d84c  jmp     short loc_18003D865
0x18003d84e  cmp     [rdi+88h], r12d
0x18003d855  jnz     short loc_18003D86B
0x18003d857  xor     ecx, ecx; dwMilliseconds
0x18003d859  call    cs:__imp_Sleep
0x18003d860  nop     dword ptr [rax+rax+00h]
0x18003d865  cmp     [rdi+24h], r12d
0x18003d869  jnz     short loc_18003D84E
0x18003d86b  mov     [rsp+98h+var_70], r12
0x18003d870  xor     r9d, r9d
0x18003d873  xor     r8d, r8d
0x18003d876  mov     [rsp+98h+var_78], r12
0x18003d87b  mov     dl, 1
0x18003d87d  mov     rcx, rdi
0x18003d880  call    SendControlMessage
0x18003d885  movzx   r8d, word ptr [r14+54h]
0x18003d88a  lea     rdx, [r14+56h]; Src
0x18003d88e  mov     rcx, [rsi+0B0h]; void *
0x18003d895  add     r8, 2; Size
0x18003d899  call    memcpy_0
0x18003d89e  movzx   eax, word ptr [r14+54h]
0x18003d8a3  mov     rcx, [rsi+0A8h]; void *
0x18003d8aa  movzx   r8d, word ptr [rax+r14+58h]
0x18003d8b0  lea     rdx, [rax+5Ah]
0x18003d8b4  add     r8, 2; Size
0x18003d8b8  add     rdx, r14; Src
0x18003d8bb  call    memcpy_0
0x18003d8c0  mov     r12d, [r15+18h]
0x18003d8c4  lea     rcx, [rbp+30h]; lpCriticalSection
0x18003d8c8  call    cs:__imp_EnterCriticalSection
0x18003d8cf  nop     dword ptr [rax+rax+00h]
0x18003d8d4  lea     rax, [rbp+2A8h]
0x18003d8db  mov     qword ptr [r14+18h], 0
0x18003d8e3  mov     rdx, [rax]
0x18003d8e6  cmp     [rdx+8], rax
0x18003d8ea  jnz     loc_18003D6AF
0x18003d8f0  mov     [r14], rdx
0x18003d8f3  lea     rcx, [rbp+30h]; lpCriticalSection
0x18003d8f7  mov     [r14+8], rax
0x18003d8fb  or      ebx, 0FFFFFFFFh
0x18003d8fe  mov     [rdx+8], r14
0x18003d902  mov     [rax], r14
0x18003d905  add     [rbp+2A4h], ebx
0x18003d90b  call    cs:__imp_LeaveCriticalSection
0x18003d912  nop     dword ptr [rax+rax+00h]
0x18003d917  xor     r14d, r14d
0x18003d91a  test    r12d, r12d
0x18003d91d  jz      loc_18003D9F7
0x18003d923  mov     rcx, cs:SockPrivateHeap
0x18003d92a  lea     r15, [rdi+270h]
0x18003d931  mov     rax, cs:SockAllocateHeapRoutine
0x18003d938  mov     r8d, r12d
0x18003d93b  xor     edx, edx
0x18003d93d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d942  mov     [r15+8], rax
0x18003d946  test    rax, rax
0x18003d949  jz      loc_18003D9F7
0x18003d94f  mov     [r15], r12d
0x18003d952  xor     r12d, r12d
0x18003d955  mov     [rdi+298h], rax
0x18003d95c  mov     dword ptr [rsp+98h+arg_8], r12d
0x18003d964  mov     rax, [rdi+8]
0x18003d968  lock inc dword ptr [rax]
0x18003d96b  mov     rax, cs:ConnectThreadHandle
0x18003d972  lea     rcx, [rdi+280h]
0x18003d979  mov     [rsp+98h+var_48], r12d; int
0x18003d97e  lea     r9, [rsp+98h+arg_10]
0x18003d986  mov     [rsp+98h+var_50], r12; __int64
0x18003d98b  lea     r8d, [rbx+2]
0x18003d98f  mov     [rsp+98h+var_58], 1; char
0x18003d994  mov     rdx, r15
0x18003d997  mov     [rsp+98h+var_60], rax; __int64
0x18003d99c  lea     rax, AcceptExRecvCompletionRoutine
0x18003d9a3  mov     [rsp+98h+var_68], rax; __int64
0x18003d9a8  lea     rax, [rsp+98h+arg_8]
0x18003d9b0  mov     [rsp+98h+var_70], rcx; __int64
0x18003d9b5  mov     rcx, rdi; CompletionContext
0x18003d9b8  mov     [rsp+98h+var_78], rax; __int64
0x18003d9bd  call    HandleApplicationRecv
0x18003d9c2  test    eax, eax
0x18003d9c4  jz      short loc_18003D9EF
0x18003d9c6  cmp     eax, 3E5h
0x18003d9cb  jz      short loc_18003D9EF
0x18003d9cd  test    byte ptr cs:xmmword_180063D60, 2
0x18003d9d4  jz      short loc_18003D9FA
0x18003d9d6  lea     edx, [rbx+22h]
0x18003d9d9  mov     ecx, 401h
0x18003d9de  mov     r9d, eax
0x18003d9e1  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18003d9e8  call    WPP_SF_d
0x18003d9ed  jmp     short loc_18003D9FA
0x18003d9ef  mov     r15d, r12d
0x18003d9f2  jmp     loc_18003D63A
0x18003d9f7  xor     r12d, r12d
0x18003d9fa  test    byte ptr cs:xmmword_180063D60+2, 4
0x18003da01  jz      short loc_18003DA25
0x18003da03  mov     r9, [rdi]
0x18003da06  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18003da0d  mov     edx, 22h ; '"'
0x18003da12  mov     [rsp+98h+var_78], rdi
0x18003da17  mov     ecx, 412h
0x18003da1c  mov     r9, [r9+8]
0x18003da20  call    WPP_SF_qq
0x18003da25  mov     rdx, [rdi]
0x18003da28  mov     r8, [rdi+0D8h]
0x18003da2f  mov     eax, [rdi+270h]
0x18003da35  add     r8, 18h
0x18003da39  mov     r9, [rdi+278h]
  ... truncated ...
```
