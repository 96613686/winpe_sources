# WSPAsyncSelect

- ea: `0x180002240`
- end: `0x180002649`
- name: `WSPAsyncSelect`
- size: `1033`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001e60`
- `0x180002240`
- `0x180002650`
- `0x1800028b8`
- `0x1800052a0`
- `0x180008190`
- `0x180008250`
- `0x18000c130`
- `0x18000fe60`
- `0x1800214f8`
- `0x180022f20`
- `0x180038118`
- `0x1800382b8`
- `0x18003ac78`
- `0x18003aec4`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000228e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000228e`
- `ntdll!NtSetIoCompletion` at `0x1800023dc`
- `ntdll!NtSetIoCompletion` at `0x1800023dc`
- `ntdll!RtlFreeHeap` at `0x180002493`
- `ntdll!RtlFreeHeap` at `0x1800025f4`
- `ntdll!RtlFreeHeap` at `0x180002493`
- `ntdll!RtlFreeHeap` at `0x1800025f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800023aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000247b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800025c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800023aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000247b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800025c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002347`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002347`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x1800022bc`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x1800022bc`

## pseudocode

```c
__int64 __fastcall WSPAsyncSelect(void *a1, HWND a2, int a3, int a4, unsigned int *a5)
{
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rbx
  __int64 v14; // rdx
  _DWORD *HeapRoutine; // rsi
  __int64 v16; // r8
  int v17; // eax
  struct _RTL_CRITICAL_SECTION *v18; // rcx
  NTSTATUS v19; // eax
  unsigned int v20; // edi
  unsigned int v22; // eax
  char v23[8]; // [rsp+40h] [rbp-38h] BYREF
  LPVOID v24[6]; // [rsp+48h] [rbp-30h] BYREF

  v24[0] = 0;
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_sqqqq(
      (_DWORD)a1,
      17,
      (unsigned int)WPP_6558a8cfbcde30925840af8972a4178a_Traceguids,
      (unsigned int)"WSPAsyncSelect",
      (char)a1,
      (char)a2,
      a3,
      a4);
  if ( SockProcessTerminating || !SockWspStartupCount || (v24[0] = TlsGetValue(MSAFD_SockTlsSlot)) == 0 )
  {
    v22 = SockEnterApiSlow(v24);
    if ( v22 )
    {
      *a5 = v22;
      return 0xFFFFFFFFLL;
    }
  }
  if ( (unsigned int)IsIsWindowPresent() && !IsWindow(a2) )
  {
    v20 = 10022;
    goto LABEL_33;
  }
  if ( (a4 & 0xFFFFFC00) != 0 )
  {
    v20 = 10022;
    goto LABEL_33;
  }
  if ( !(unsigned int)SockCheckAndInitAsyncSelectHelper() )
  {
    v20 = 10055;
    goto LABEL_33;
  }
  v10 = SockFindAndReferenceSocket(a1);
  v13 = v10;
  if ( !v10 )
  {
    v20 = 10038;
    goto LABEL_33;
  }
  if ( (*(_BYTE *)(v10 + 69) & 0x20) != 0 )
  {
    v20 = 10038;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10, 0xFFFFFFFF) == 1 )
      SockDestroySocket(v10, v11, v12);
    goto LABEL_33;
  }
  HeapRoutine = (_DWORD *)SockAllocateHeapRoutine(SockPrivateHeap, 0, 64);
  if ( !HeapRoutine )
  {
    v20 = 10055;
    goto LABEL_21;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 224));
  if ( (*(_BYTE *)(v13 + 68) & 0x40) != 0 )
  {
    if ( *(_DWORD *)(v13 + 216) )
    {
      v20 = SockEventSelectHelper(v13, 0, 0);
      if ( v20 )
        goto LABEL_46;
    }
LABEL_15:
    *(_QWORD *)(v13 + 104) = a2;
    *(_DWORD *)(v13 + 116) = a3;
    *(_DWORD *)(v13 + 120) = a4;
    *(_DWORD *)(v13 + 124) = 0;
    if ( !SockIsSocketConnected(v13) && (*(_BYTE *)(v13 + 80) & 1) == 0 )
      *(_DWORD *)(v13 + 124) |= 2u;
    v17 = *(_DWORD *)(v13 + 124);
    v18 = (struct _RTL_CRITICAL_SECTION *)(v13 + 224);
    ++*(_DWORD *)(v13 + 112);
    if ( (~v17 & *(_DWORD *)(v13 + 120)) != 0 )
    {
      *(_QWORD *)HeapRoutine = v13;
      HeapRoutine[2] = *(_DWORD *)(v13 + 112);
      LeaveCriticalSection(v18);
      if ( !SockCheckAndReferenceAsyncThread() )
      {
        v20 = 10055;
        goto LABEL_49;
      }
      v19 = NtSetIoCompletion(SockAsyncQueuePort, SockProcessQueuedAsyncSelect, HeapRoutine, 0, 0);
      if ( v19 < 0 )
      {
        _InterlockedDecrement(&SockAsyncThreadReferenceCount);
        v20 = NtStatusToSocketError((unsigned int)v19);
        goto LABEL_49;
      }
      _InterlockedIncrement((volatile signed __int32 *)v13);
    }
    else
    {
      LeaveCriticalSection(v18);
      RtlFreeHeap(SockPrivateHeap, 0, HeapRoutine);
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_qll(v9, 20, v16, v13, *(_DWORD *)(v13 + 120), *(_DWORD *)(v13 + 124));
    }
    v20 = 0;
    goto LABEL_21;
  }
  v23[0] = 1;
  v20 = SockSetInformation(v13, 2, v23, 0);
  if ( !v20 )
  {
    *(_BYTE *)(v13 + 68) |= 0x40u;
    goto LABEL_15;
  }
LABEL_46:
  LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 224));
LABEL_49:
  RtlFreeHeap(SockPrivateHeap, 0, HeapRoutine);
LABEL_21:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13, 0xFFFFFFFF) == 1 )
    SockDestroySocket(v13, v14, v16);
  if ( !v20 )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_q(1025, 18, WPP_6558a8cfbcde30925840af8972a4178a_Traceguids, v13);
    return 0;
  }
LABEL_33:
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_l(v9, 19, WPP_6558a8cfbcde30925840af8972a4178a_Traceguids, v20);
  *a5 = v20;
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180002240  push    rbx
0x180002242  push    rbp
0x180002243  push    r12
0x180002245  push    r13
0x180002247  push    r14
0x180002249  sub     rsp, 50h
0x18000224d  xor     r13d, r13d
0x180002250  movsxd  rbp, r9d
0x180002253  mov     [rsp+78h+var_30], r13
0x180002258  mov     r14, rdx
0x18000225b  mov     r12d, r8d
0x18000225e  mov     rbx, rcx
0x180002261  test    byte ptr cs:xmmword_180063D60, 2
0x180002268  jnz     loc_180002532
0x18000226e  cmp     cs:SockProcessTerminating, r13b
0x180002275  jnz     loc_18000244C
0x18000227b  cmp     cs:SockWspStartupCount, r13d
0x180002282  jbe     loc_18000244C
0x180002288  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x18000228e  call    cs:__imp_TlsGetValue
0x180002295  nop     dword ptr [rax+rax+00h]
0x18000229a  mov     [rsp+78h+var_30], rax
0x18000229f  test    rax, rax
0x1800022a2  jz      loc_18000244C
0x1800022a8  mov     [rsp+78h+arg_8], rdi
0x1800022b0  call    IsIsWindowPresent
0x1800022b5  test    eax, eax
0x1800022b7  jz      short loc_1800022D0
0x1800022b9  mov     rcx, r14; hWnd
0x1800022bc  call    cs:__imp_IsWindow
0x1800022c3  nop     dword ptr [rax+rax+00h]
0x1800022c8  test    eax, eax
0x1800022ca  jz      loc_180002563
0x1800022d0  test    ebp, 0FFFFFC00h
0x1800022d6  jnz     loc_18000256D
0x1800022dc  call    SockCheckAndInitAsyncSelectHelper
0x1800022e1  test    eax, eax
0x1800022e3  jz      loc_180002577
0x1800022e9  mov     dl, 1
0x1800022eb  mov     rcx, rbx
0x1800022ee  call    SockFindAndReferenceSocket
0x1800022f3  mov     rbx, rax
0x1800022f6  test    rax, rax
0x1800022f9  jz      loc_1800024CC
0x1800022ff  test    byte ptr [rax+45h], 20h
0x180002303  jnz     loc_180002581
0x180002309  mov     rcx, cs:SockPrivateHeap
0x180002310  xor     edx, edx
0x180002312  mov     rax, cs:SockAllocateHeapRoutine
0x180002319  mov     r8d, 40h ; '@'
0x18000231f  mov     [rsp+78h+arg_0], rsi
0x180002327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000232c  mov     rsi, rax
0x18000232f  test    rax, rax
0x180002332  jz      loc_180002445
0x180002338  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x18000233f  mov     [rsp+78h+arg_10], r15
0x180002347  call    cs:__imp_EnterCriticalSection
0x18000234e  nop     dword ptr [rax+rax+00h]
0x180002353  test    byte ptr [rbx+44h], 40h
0x180002357  jz      loc_180002505
0x18000235d  cmp     [rbx+0D8h], r13d
0x180002364  jnz     loc_1800025A5
0x18000236a  mov     rcx, rbx
0x18000236d  mov     [rbx+68h], r14
0x180002371  mov     [rbx+74h], r12d
0x180002375  mov     [rbx+78h], ebp
0x180002378  mov     [rbx+7Ch], r13d
0x18000237c  call    SockIsSocketConnected
0x180002381  test    al, al
0x180002383  jz      loc_1800024F2
0x180002389  mov     eax, [rbx+7Ch]
0x18000238c  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x180002393  inc     dword ptr [rbx+70h]
0x180002396  not     eax
0x180002398  test    [rbx+78h], eax
0x18000239b  jz      loc_18000247B
0x1800023a1  mov     [rsi], rbx
0x1800023a4  mov     eax, [rbx+70h]
0x1800023a7  mov     [rsi+8], eax
0x1800023aa  call    cs:__imp_LeaveCriticalSection
0x1800023b1  nop     dword ptr [rax+rax+00h]
0x1800023b6  call    SockCheckAndReferenceAsyncThread
0x1800023bb  test    al, al
0x1800023bd  jz      loc_1800025D1
0x1800023c3  mov     rcx, cs:SockAsyncQueuePort; IoCompletionPortHandle
0x1800023ca  lea     rdx, SockProcessQueuedAsyncSelect; CompletionKey
0x1800023d1  xor     r9d, r9d; CompletionStatus
0x1800023d4  mov     qword ptr [rsp+78h+CompletionInformation], r13; CompletionInformation
0x1800023d9  mov     r8, rsi; CompletionContext
0x1800023dc  call    cs:__imp_NtSetIoCompletion
0x1800023e3  nop     dword ptr [rax+rax+00h]
0x1800023e8  test    eax, eax
0x1800023ea  js      loc_1800025D8
0x1800023f0  lock inc dword ptr [rbx]
0x1800023f3  mov     edi, r13d
0x1800023f6  mov     r15, [rsp+78h+arg_10]
0x1800023fe  mov     eax, 0FFFFFFFFh
0x180002403  lock xadd [rbx], eax
0x180002407  mov     rsi, [rsp+78h+arg_0]
0x18000240f  cmp     eax, 1
0x180002412  jz      loc_180002605
0x180002418  test    edi, edi
0x18000241a  jnz     loc_1800024D1
0x180002420  test    byte ptr cs:xmmword_180063D60, 2
0x180002427  jnz     loc_18000262B
0x18000242d  xor     eax, eax
0x18000242f  mov     rdi, [rsp+78h+arg_8]
0x180002437  add     rsp, 50h
0x18000243b  pop     r14
0x18000243d  pop     r13
0x18000243f  pop     r12
0x180002441  pop     rbp
0x180002442  pop     rbx
0x180002443  retn
0x180002445  mov     edi, 2747h
0x18000244a  jmp     short loc_1800023FE
0x18000244c  lea     rcx, [rsp+78h+var_30]
0x180002451  call    SockEnterApiSlow
0x180002456  test    eax, eax
0x180002458  jz      loc_1800022A8
0x18000245e  mov     rcx, [rsp+78h+arg_20]
0x180002466  mov     [rcx], eax
0x180002468  mov     eax, 0FFFFFFFFh
0x18000246d  add     rsp, 50h
0x180002471  pop     r14
0x180002473  pop     r13
0x180002475  pop     r12
0x180002477  pop     rbp
0x180002478  pop     rbx
0x180002479  retn
0x18000247b  call    cs:__imp_LeaveCriticalSection
0x180002482  nop     dword ptr [rax+rax+00h]
0x180002487  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18000248e  mov     r8, rsi; P
0x180002491  xor     edx, edx; Flags
0x180002493  call    cs:__imp_RtlFreeHeap
0x18000249a  nop     dword ptr [rax+rax+00h]
0x18000249f  test    byte ptr cs:xmmword_180063D60, 2
0x1800024a6  jz      loc_1800023F3
0x1800024ac  mov     eax, [rbx+7Ch]
0x1800024af  mov     edx, 14h
0x1800024b4  mov     dword ptr [rsp+78h+var_50], eax
0x1800024b8  mov     r9, rbx
0x1800024bb  mov     eax, [rbx+78h]
0x1800024be  mov     [rsp+78h+CompletionInformation], eax
0x1800024c2  call    WPP_SF_qll
0x1800024c7  jmp     loc_1800023F3
0x1800024cc  mov     edi, 2736h
0x1800024d1  test    byte ptr cs:xmmword_180063D60, 2
0x1800024d8  jnz     loc_180002612
0x1800024de  mov     rax, [rsp+78h+arg_20]
0x1800024e6  mov     [rax], edi
0x1800024e8  mov     eax, 0FFFFFFFFh
0x1800024ed  jmp     loc_18000242F
0x1800024f2  test    byte ptr [rbx+50h], 1
0x1800024f6  jnz     loc_180002389
0x1800024fc  or      dword ptr [rbx+7Ch], 2
0x180002500  jmp     loc_180002389
0x180002505  xor     r9d, r9d
0x180002508  mov     [rsp+78h+var_38], 1
0x18000250d  lea     r8, [rsp+78h+var_38]
0x180002512  mov     edx, 2
0x180002517  mov     rcx, rbx
0x18000251a  call    SockSetInformation
0x18000251f  mov     edi, eax
0x180002521  test    eax, eax
0x180002523  jnz     loc_1800025BC
0x180002529  or      byte ptr [rbx+44h], 40h
0x18000252d  jmp     loc_18000236A
0x180002532  mov     [rsp+78h+var_40], rbp
0x180002537  lea     r9, aWspasyncselect; "WSPAsyncSelect"
0x18000253e  mov     [rsp+78h+var_48], r12
0x180002543  lea     r8, WPP_6558a8cfbcde30925840af8972a4178a_Traceguids
0x18000254a  mov     [rsp+78h+var_50], r14
0x18000254f  mov     edx, 11h
0x180002554  mov     qword ptr [rsp+78h+CompletionInformation], rbx
0x180002559  call    WPP_SF_sqqqq
0x18000255e  jmp     loc_18000226E
0x180002563  mov     edi, 2726h
0x180002568  jmp     loc_1800024D1
0x18000256d  mov     edi, 2726h
0x180002572  jmp     loc_1800024D1
0x180002577  mov     edi, 2747h
0x18000257c  jmp     loc_1800024D1
0x180002581  mov     edi, 2736h
0x180002586  mov     eax, 0FFFFFFFFh
0x18000258b  lock xadd [rbx], eax
0x18000258f  cmp     eax, 1
0x180002592  jnz     loc_1800024D1
0x180002598  mov     rcx, rbx
0x18000259b  call    SockDestroySocket
0x1800025a0  jmp     loc_1800024D1
0x1800025a5  xor     r8d, r8d
0x1800025a8  xor     edx, edx
0x1800025aa  mov     rcx, rbx
0x1800025ad  call    SockEventSelectHelper
0x1800025b2  mov     edi, eax
0x1800025b4  test    eax, eax
0x1800025b6  jz      loc_18000236A
0x1800025bc  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x1800025c3  call    cs:__imp_LeaveCriticalSection
0x1800025ca  nop     dword ptr [rax+rax+00h]
0x1800025cf  jmp     short loc_1800025E8
0x1800025d1  mov     edi, 2747h
0x1800025d6  jmp     short loc_1800025E8
0x1800025d8  lock dec cs:SockAsyncThreadReferenceCount
0x1800025df  mov     ecx, eax
0x1800025e1  call    NtStatusToSocketError
0x1800025e6  mov     edi, eax
0x1800025e8  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x1800025ef  mov     r8, rsi; P
0x1800025f2  xor     edx, edx; Flags
0x1800025f4  call    cs:__imp_RtlFreeHeap
0x1800025fb  nop     dword ptr [rax+rax+00h]
0x180002600  jmp     loc_1800023F6
0x180002605  mov     rcx, rbx
0x180002608  call    SockDestroySocket
0x18000260d  jmp     loc_180002418
0x180002612  mov     edx, 13h
0x180002617  lea     r8, WPP_6558a8cfbcde30925840af8972a4178a_Traceguids
0x18000261e  mov     r9d, edi
0x180002621  call    WPP_SF_l
0x180002626  jmp     loc_1800024DE
0x18000262b  mov     edx, 12h
0x180002630  lea     r8, WPP_6558a8cfbcde30925840af8972a4178a_Traceguids
0x180002637  mov     ecx, 401h
0x18000263c  mov     r9, rbx
0x18000263f  call    WPP_SF_q
0x180002644  jmp     loc_18000242D
```
