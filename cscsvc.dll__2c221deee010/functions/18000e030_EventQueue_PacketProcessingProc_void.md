# EventQueue_PacketProcessingProc(void *)

- ea: `0x18000e030`
- end: `0x18000e514`
- name: `?EventQueue_PacketProcessingProc@@YAKPEAX@Z`
- size: `1252`
- prototype: `unsigned int __fastcall(EVENT_THREAD_CONTROL_BLOCK *this)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x18000c3f0`
- `0x18000ce7c`
- `0x18000ceb0`
- `0x18000d760`
- `0x18000e030`
- `0x1800258f0`
- `0x18002ec80`
- `0x18002ed50`
- `0x180036394`
- `0x18003c460`
- `0x18003c560`
- `0x18003e928`
- `0x18004e4b4`
- `0x18004e5f0`
- `0x18004fd00`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e047`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e047`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e07f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e088`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e25e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e2f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e3b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e431`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e460`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e07f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e088`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e25e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e2f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e3b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e431`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e460`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e0ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e17b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e306`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e3e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e457`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e486`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e48f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e0ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e17b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e306`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e3e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e457`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e486`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e48f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000e0ba`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000e0cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000e0ba`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000e0cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000e3ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000e3ed`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000e4a9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000e4a9`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18000e4a3`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18000e4a3`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18000e067`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18000e067`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000e054`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000e054`

## pseudocode

```c
__int64 __fastcall EventQueue_PacketProcessingProc(EVENT_THREAD_CONTROL_BLOCK *this)
{
  char *v2; // r15
  char *v3; // rsi
  DWORD TickCount; // ebx
  DWORD v5; // eax
  unsigned int v6; // ecx
  char *v7; // rbp
  EVENT_QUEUE_PACKET *v8; // r14
  EVENT_QUEUE_PACKET *v9; // r12
  __int64 i; // rbp
  __int64 v11; // rcx
  unsigned int v12; // eax
  __int64 v13; // r10
  __int64 (__fastcall *v14)(__int64); // r13
  int v15; // r14d
  int v16; // r12d
  unsigned int j; // r15d
  int v18; // eax
  int v19; // ebp
  unsigned int v20; // eax
  __int64 v21; // r10
  __int64 v22; // rcx
  __int64 k; // rbp
  __int64 v24; // rcx
  char *v25; // rax
  _QWORD *v26; // rcx
  EVENT_QUEUE_PACKET *v27; // rax
  _QWORD *v28; // rcx
  __int64 v29; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // [rsp+28h] [rbp-50h]

  *((_DWORD *)this + 4) = GetCurrentThreadId();
  if ( CoInitializeEx(0, 0) >= 0 )
  {
    if ( CoEnableCallCancellation(0) >= 0 )
    {
      EnterCriticalSection(&g_csEventDispatcherLock);
      EnterCriticalSection(&g_csEventDispatcherLock);
      if ( ++dword_1800B8280 > (unsigned int)dword_1800B8284 )
        dword_1800B8284 = dword_1800B8280;
      LeaveCriticalSection(&g_csEventDispatcherLock);
      v2 = (char *)this + 32;
      v3 = (char *)*((_QWORD *)this + 4);
      TickCount = GetTickCount();
      while ( 1 )
      {
        if ( v3 == v2 )
        {
          v28 = (_QWORD *)*((_QWORD *)this + 1);
          if ( *(_QWORD *)this )
            *(_QWORD *)(*(_QWORD *)this + 8LL) = v28;
          if ( v28 )
            *v28 = *(_QWORD *)this;
          *((_QWORD *)this + 1) = 0;
          *(_QWORD *)this = 0;
          EVENT_THREAD_CONTROL_BLOCK::Destroy(this);
          CLinkPool<EVENT_THREAD_CONTROL_BLOCK>::_ReturnEntryToFreeList(v29, this);
          EnterCriticalSection(&g_csEventDispatcherLock);
          if ( --dword_1800B8288 > dword_1800B828C )
            dword_1800B828C = dword_1800B8288;
          LeaveCriticalSection(&g_csEventDispatcherLock);
          goto LABEL_65;
        }
        v5 = GetTickCount();
        v6 = v5 - TickCount - 1;
        if ( v5 >= TickCount )
          v6 = v5 - TickCount;
        if ( v6 >= g_dwDispatchThreadQuantumMs )
          break;
        v7 = v3;
        v8 = (EVENT_QUEUE_PACKET *)v3;
        v9 = (EVENT_QUEUE_PACKET *)v3;
        if ( *((_QWORD *)v3 + 4) )
        {
          for ( i = 0; i != 4; ++i )
          {
            v11 = *(_QWORD *)&v3[8 * i + 56];
            if ( v11 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
          }
          _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)v3 + 11) + 8LL));
          if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v12 = (unsigned int)EventName((enum tagOFFLINEFILES_EVENTS)*((_DWORD *)v3 + 5));
            LODWORD(v33) = *((_DWORD *)this + 6);
            WPP_SF_SdD(
              *(_QWORD *)(v13 + 16),
              16,
              (unsigned int)WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids,
              v12,
              *((_DWORD *)this + 5),
              v33);
          }
          v14 = (__int64 (__fastcall *)(__int64))*((_QWORD *)v3 + 4);
          LeaveCriticalSection(&g_csEventDispatcherLock);
          v15 = 0;
          v16 = 0;
          for ( j = 0; ; ++j )
          {
            v18 = v14((__int64)(v3 + 40));
            v19 = v18;
            if ( v18 >= 0 )
              break;
            if ( v18 == -2147417848 )
            {
              v15 = 1;
              break;
            }
            if ( (((unsigned __int16)v18 - 1722) & 0xFFFFFFFA) != 0 || (unsigned __int16)v18 == 1723 )
            {
              if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  14,
                  WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids,
                  (unsigned int)v18);
              }
              break;
            }
            if ( j >= g_dwDispatchMaxEventRetries )
            {
              if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids);
              }
              v15 = 1;
              v16 = 1;
            }
            if ( v16 )
              break;
          }
          EnterCriticalSection(&g_csEventDispatcherLock);
          if ( v19 < 0
            && WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v20 = (unsigned int)EventName((enum tagOFFLINEFILES_EVENTS)*((_DWORD *)v3 + 5));
            WPP_SF_SddD(
              *(_QWORD *)(v21 + 16),
              17,
              *((_DWORD *)this + 5),
              v20,
              *((_DWORD *)this + 5),
              *((_DWORD *)this + 6),
              v19);
          }
          v22 = *((_QWORD *)v3 + 11);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v22 + 8), 0xFFFFFFFF) == 1 && v22 )
            (**(void (__fastcall ***)(__int64, __int64))v22)(v22, 1);
          for ( k = 0; k != 4; ++k )
          {
            v24 = *(_QWORD *)&v3[8 * k + 56];
            if ( v24 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
          }
          EnterCriticalSection(&g_csEventDispatcherLock);
          ++dword_1800B827C;
          LeaveCriticalSection(&g_csEventDispatcherLock);
          if ( v15 )
          {
            if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                18,
                WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids,
                *((unsigned int *)this + 6),
                *((_DWORD *)this + 5));
            }
            EventDispatcher_UnregisterConnection(*((_DWORD *)v3 + 6));
          }
          v9 = (EVENT_QUEUE_PACKET *)v3;
          v2 = (char *)this + 32;
          v7 = v3;
          v8 = (EVENT_QUEUE_PACKET *)v3;
        }
        v25 = *(char **)v3;
        v26 = (_QWORD *)*((_QWORD *)v8 + 1);
        v3 = v25;
        if ( v25 )
          *((_QWORD *)v25 + 1) = v26;
        if ( v26 )
          *v26 = *(_QWORD *)v7;
        *((_QWORD *)v8 + 1) = 0;
        *(_QWORD *)v8 = 0;
        EVENT_QUEUE_PACKET::Destroy(v8);
        *((_QWORD *)v8 + 1) = 0;
        *(_QWORD *)v8 = 0;
        v27 = g_EventPacketPool;
        *(_QWORD *)v7 = g_EventPacketPool;
        *((_QWORD *)v8 + 1) = &g_EventPacketPool;
        g_EventPacketPool = v9;
        *((_QWORD *)v27 + 1) = v8;
        EnterCriticalSection(&g_csEventDispatcherLock);
        if ( --dword_1800B8270 > dword_1800B8274 )
          dword_1800B8274 = dword_1800B8270;
        LeaveCriticalSection(&g_csEventDispatcherLock);
        --*((_DWORD *)this + 12);
        GetSystemTime((LPSYSTEMTIME)this + 6);
      }
      *((_DWORD *)this + 4) = 0;
      if ( (int)EventQueue_QueueWorkItem(this) < 0 )
      {
        CLinkPool<EVENT_QUEUE_PACKET>::_UnlinkEntry(v31, this);
        *((_QWORD *)this + 1) = 0;
        *(_QWORD *)this = 0;
        EVENT_THREAD_CONTROL_BLOCK::Destroy(this);
        CLinkPool<EVENT_THREAD_CONTROL_BLOCK>::_ReturnEntryToFreeList(v32, this);
        PerfCounter_AdjustCounter(&dword_1800B8288, &dword_1800B828C, -1);
      }
LABEL_65:
      EnterCriticalSection(&g_csEventDispatcherLock);
      if ( --dword_1800B8280 > (unsigned int)dword_1800B8284 )
        dword_1800B8284 = dword_1800B8280;
      LeaveCriticalSection(&g_csEventDispatcherLock);
      LeaveCriticalSection(&g_csEventDispatcherLock);
      CInvSemaphore::Decrement((CInvSemaphore *)&g_invsemThreadControlBlocks);
      CoDisableCallCancellation(0);
    }
    CoUninitialize();
  }
  return 0;
}

```

## disassembly

```asm
0x18000e030  mov     [rsp+arg_18], rbx
0x18000e035  push    rbp
0x18000e036  push    rsi
0x18000e037  push    rdi
0x18000e038  push    r12
0x18000e03a  push    r13
0x18000e03c  push    r14
0x18000e03e  push    r15
0x18000e040  sub     rsp, 40h
0x18000e044  mov     rdi, rcx
0x18000e047  call    cs:__imp_GetCurrentThreadId
0x18000e04d  xor     edx, edx; dwCoInit
0x18000e04f  xor     ecx, ecx; pvReserved
0x18000e051  mov     [rdi+10h], eax
0x18000e054  call    cs:__imp_CoInitializeEx
0x18000e05a  xor     r13d, r13d
0x18000e05d  test    eax, eax
0x18000e05f  js      loc_18000E4AF
0x18000e065  xor     ecx, ecx; pReserved
0x18000e067  call    cs:__imp_CoEnableCallCancellation
0x18000e06d  test    eax, eax
0x18000e06f  js      loc_18000E4A9
0x18000e075  lea     rbp, ?g_csEventDispatcherLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csEventDispatcherLock
0x18000e07c  mov     rcx, rbp; lpCriticalSection
0x18000e07f  call    cs:__imp_EnterCriticalSection
0x18000e085  mov     rcx, rbp; lpCriticalSection
0x18000e088  call    cs:__imp_EnterCriticalSection
0x18000e08e  mov     eax, cs:dword_1800B8280
0x18000e094  inc     eax
0x18000e096  cmp     eax, cs:dword_1800B8284
0x18000e09c  mov     cs:dword_1800B8280, eax
0x18000e0a2  jbe     short loc_18000E0AA
0x18000e0a4  mov     cs:dword_1800B8284, eax
0x18000e0aa  mov     rcx, rbp; lpCriticalSection
0x18000e0ad  call    cs:__imp_LeaveCriticalSection
0x18000e0b3  lea     r15, [rdi+20h]
0x18000e0b7  mov     rsi, [r15]
0x18000e0ba  call    cs:__imp_GetTickCount
0x18000e0c0  mov     ebx, eax
0x18000e0c2  or      r14d, 0FFFFFFFFh
0x18000e0c6  jmp     loc_18000E3F3
0x18000e0cb  call    cs:__imp_GetTickCount
0x18000e0d1  mov     edx, eax
0x18000e0d3  sub     edx, ebx
0x18000e0d5  cmp     eax, ebx
0x18000e0d7  lea     ecx, [rdx-1]
0x18000e0da  cmovnb  ecx, edx
0x18000e0dd  cmp     ecx, cs:?g_dwDispatchThreadQuantumMs@@3KA; ulong g_dwDispatchThreadQuantumMs
0x18000e0e3  jnb     loc_18000E4C9
0x18000e0e9  mov     rbp, rsi
0x18000e0ec  mov     r14, rsi
0x18000e0ef  mov     r12, rsi
0x18000e0f2  cmp     [rsi+20h], r13
0x18000e0f6  jz      loc_18000E356
0x18000e0fc  mov     rbp, r13
0x18000e0ff  mov     rcx, [rsi+rbp*8+38h]
0x18000e104  test    rcx, rcx
0x18000e107  jz      short loc_18000E115
0x18000e109  mov     rax, [rcx]
0x18000e10c  mov     rax, [rax+8]
0x18000e110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e115  inc     rbp
0x18000e118  cmp     rbp, 4
0x18000e11c  jnz     short loc_18000E0FF
0x18000e11e  mov     rax, [rsi+58h]
0x18000e122  lock inc dword ptr [rax+8]
0x18000e126  mov     r10, cs:WPP_GLOBAL_Control
0x18000e12d  lea     rax, WPP_GLOBAL_Control
0x18000e134  cmp     r10, rax
0x18000e137  jz      short loc_18000E170
0x18000e139  test    byte ptr [r10+1Ch], 10h
0x18000e13e  jz      short loc_18000E170
0x18000e140  mov     ecx, [rsi+14h]; enum tagOFFLINEFILES_EVENTS
0x18000e143  call    ?EventName@@YAPEBGW4tagOFFLINEFILES_EVENTS@@@Z; EventName(tagOFFLINEFILES_EVENTS)
0x18000e148  mov     r8d, [rdi+18h]
0x18000e14c  lea     edx, [rbp+0Ch]
0x18000e14f  mov     rcx, [r10+10h]
0x18000e153  mov     r9, rax
0x18000e156  mov     dword ptr [rsp+78h+var_50], r8d
0x18000e15b  mov     r8d, [rdi+14h]
0x18000e15f  mov     [rsp+78h+var_58], r8d
0x18000e164  lea     r8, WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids
0x18000e16b  call    WPP_SF_SdD
0x18000e170  mov     r13, [rsi+20h]
0x18000e174  lea     rcx, ?g_csEventDispatcherLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000e17b  call    cs:__imp_LeaveCriticalSection
0x18000e181  xor     r14d, r14d
0x18000e184  xor     r12d, r12d
0x18000e187  xor     r15d, r15d
0x18000e18a  lea     rax, [rsi+28h]
0x18000e18e  mov     rcx, rax
0x18000e191  mov     rax, r13
0x18000e194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e199  mov     ebp, eax
0x18000e19b  test    eax, eax
0x18000e19d  jns     loc_18000E24D
0x18000e1a3  cmp     eax, 80010108h
0x18000e1a8  jz      loc_18000E247
0x18000e1ae  movzx   edx, bp
0x18000e1b1  lea     ecx, [rdx-6BAh]
0x18000e1b7  test    ecx, 0FFFFFFFAh
0x18000e1bd  jnz     short loc_18000E214
0x18000e1bf  cmp     edx, 6BBh
0x18000e1c5  jz      short loc_18000E214
0x18000e1c7  cmp     r15d, cs:?g_dwDispatchMaxEventRetries@@3KA; ulong g_dwDispatchMaxEventRetries
0x18000e1ce  jb      short loc_18000E207
0x18000e1d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1d7  lea     rax, WPP_GLOBAL_Control
0x18000e1de  cmp     rcx, rax
0x18000e1e1  jz      short loc_18000E1FE
0x18000e1e3  test    byte ptr [rcx+1Ch], 10h
0x18000e1e7  jz      short loc_18000E1FE
0x18000e1e9  mov     rcx, [rcx+10h]
0x18000e1ed  lea     r8, WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids
0x18000e1f4  mov     edx, 0Dh
0x18000e1f9  call    WPP_SF_
0x18000e1fe  mov     r14d, 1
0x18000e204  mov     r12d, r14d
0x18000e207  test    r12d, r12d
0x18000e20a  jnz     short loc_18000E24D
0x18000e20c  inc     r15d
0x18000e20f  jmp     loc_18000E18A
0x18000e214  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e21b  lea     r12, WPP_GLOBAL_Control
0x18000e222  cmp     rcx, r12
0x18000e225  jz      short loc_18000E254
0x18000e227  test    byte ptr [rcx+1Ch], 10h
0x18000e22b  jz      short loc_18000E254
0x18000e22d  mov     rcx, [rcx+10h]
0x18000e231  lea     r8, WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids
0x18000e238  mov     edx, 0Eh
0x18000e23d  mov     r9d, ebp
0x18000e240  call    WPP_SF_d
0x18000e245  jmp     short loc_18000E254
0x18000e247  mov     r14d, 1
0x18000e24d  lea     r12, WPP_GLOBAL_Control
0x18000e254  lea     r15, ?g_csEventDispatcherLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csEventDispatcherLock
0x18000e25b  mov     rcx, r15; lpCriticalSection
0x18000e25e  call    cs:__imp_EnterCriticalSection
0x18000e264  xor     r13d, r13d
0x18000e267  test    ebp, ebp
0x18000e269  jns     short loc_18000E2AC
0x18000e26b  mov     r10, cs:WPP_GLOBAL_Control
0x18000e272  cmp     r10, r12
0x18000e275  jz      short loc_18000E2AC
0x18000e277  test    byte ptr [r10+1Ch], 2
0x18000e27c  jz      short loc_18000E2AC
0x18000e27e  mov     ecx, [rsi+14h]; enum tagOFFLINEFILES_EVENTS
0x18000e281  call    ?EventName@@YAPEBGW4tagOFFLINEFILES_EVENTS@@@Z; EventName(tagOFFLINEFILES_EVENTS)
0x18000e286  mov     r8d, [rdi+18h]
0x18000e28a  lea     edx, [r13+11h]
0x18000e28e  mov     rcx, [r10+10h]
0x18000e292  mov     r9, rax
0x18000e295  mov     [rsp+78h+var_48], ebp
0x18000e299  mov     dword ptr [rsp+78h+var_50], r8d
0x18000e29e  mov     r8d, [rdi+14h]
0x18000e2a2  mov     [rsp+78h+var_58], r8d
0x18000e2a7  call    WPP_SF_SddD
0x18000e2ac  mov     rcx, [rsi+58h]
0x18000e2b0  or      eax, 0FFFFFFFFh
0x18000e2b3  lock xadd [rcx+8], eax
0x18000e2b8  cmp     eax, 1
0x18000e2bb  jnz     short loc_18000E2D2
0x18000e2bd  test    rcx, rcx
0x18000e2c0  jz      short loc_18000E2D2
0x18000e2c2  mov     rax, [rcx]
0x18000e2c5  mov     edx, 1
0x18000e2ca  mov     rax, [rax]
0x18000e2cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2d2  mov     rbp, r13
0x18000e2d5  mov     rcx, [rsi+rbp*8+38h]
0x18000e2da  test    rcx, rcx
0x18000e2dd  jz      short loc_18000E2EB
0x18000e2df  mov     rax, [rcx]
0x18000e2e2  mov     rax, [rax+10h]
0x18000e2e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2eb  inc     rbp
0x18000e2ee  cmp     rbp, 4
0x18000e2f2  jnz     short loc_18000E2D5
0x18000e2f4  mov     rcx, r15; lpCriticalSection
0x18000e2f7  call    cs:__imp_EnterCriticalSection
0x18000e2fd  inc     cs:dword_1800B827C
0x18000e303  mov     rcx, r15; lpCriticalSection
0x18000e306  call    cs:__imp_LeaveCriticalSection
0x18000e30c  test    r14d, r14d
0x18000e30f  jz      short loc_18000E349
0x18000e311  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e318  cmp     rcx, r12
0x18000e31b  jz      short loc_18000E341
0x18000e31d  test    byte ptr [rcx+1Ch], 10h
0x18000e321  jz      short loc_18000E341
0x18000e323  mov     eax, [rdi+14h]
0x18000e326  lea     edx, [rbp+0Eh]
0x18000e329  mov     r9d, [rdi+18h]
0x18000e32d  lea     r8, WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids
0x18000e334  mov     rcx, [rcx+10h]
0x18000e338  mov     [rsp+78h+var_58], eax
0x18000e33c  call    WPP_SF_dd
0x18000e341  mov     ecx, [rsi+18h]; unsigned int
0x18000e344  call    ?EventDispatcher_UnregisterConnection@@YAJK@Z; EventDispatcher_UnregisterConnection(ulong)
0x18000e349  mov     r12, rsi
0x18000e34c  lea     r15, [rdi+20h]
0x18000e350  mov     rbp, rsi
0x18000e353  mov     r14, rsi
0x18000e356  mov     rax, [rsi]
0x18000e359  mov     rcx, [r14+8]
0x18000e35d  mov     rsi, rax
0x18000e360  test    rax, rax
0x18000e363  jz      short loc_18000E369
0x18000e365  mov     [rax+8], rcx
0x18000e369  test    rcx, rcx
0x18000e36c  jz      short loc_18000E375
0x18000e36e  mov     rax, [rbp+0]
0x18000e372  mov     [rcx], rax
0x18000e375  mov     rcx, r14; this
0x18000e378  mov     [r14+8], r13
0x18000e37c  mov     [r14], r13
0x18000e37f  call    ?Destroy@EVENT_QUEUE_PACKET@@QEAAXXZ; EVENT_QUEUE_PACKET::Destroy(void)
0x18000e384  mov     [r14+8], r13
0x18000e388  lea     rcx, ?g_EventPacketPool@@3V?$CLinkPool@UEVENT_QUEUE_PACKET@@@@A; CLinkPool<EVENT_QUEUE_PACKET> g_EventPacketPool
0x18000e38f  mov     [r14], r13
0x18000e392  mov     rax, cs:?g_EventPacketPool@@3V?$CLinkPool@UEVENT_QUEUE_PACKET@@@@A; CLinkPool<EVENT_QUEUE_PACKET> g_EventPacketPool
0x18000e399  mov     [rbp+0], rax
0x18000e39d  lea     rbp, ?g_csEventDispatcherLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csEventDispatcherLock
0x18000e3a4  mov     [r14+8], rcx
0x18000e3a8  mov     rcx, rbp; lpCriticalSection
0x18000e3ab  mov     cs:?g_EventPacketPool@@3V?$CLinkPool@UEVENT_QUEUE_PACKET@@@@A, r12; CLinkPool<EVENT_QUEUE_PACKET> g_EventPacketPool
0x18000e3b2  mov     [rax+8], r14
0x18000e3b6  call    cs:__imp_EnterCriticalSection
0x18000e3bc  mov     eax, cs:dword_1800B8270
0x18000e3c2  or      r14d, 0FFFFFFFFh
0x18000e3c6  add     eax, r14d
0x18000e3c9  cmp     eax, cs:dword_1800B8274
0x18000e3cf  mov     cs:dword_1800B8270, eax
0x18000e3d5  jbe     short loc_18000E3DD
0x18000e3d7  mov     cs:dword_1800B8274, eax
0x18000e3dd  mov     rcx, rbp; lpCriticalSection
0x18000e3e0  call    cs:__imp_LeaveCriticalSection
0x18000e3e6  dec     dword ptr [rdi+30h]
0x18000e3e9  lea     rcx, [rdi+60h]; lpSystemTime
0x18000e3ed  call    cs:__imp_GetSystemTime
0x18000e3f3  cmp     rsi, r15
0x18000e3f6  jnz     loc_18000E0CB
0x18000e3fc  mov     rax, [rdi]
0x18000e3ff  mov     rcx, [rdi+8]
0x18000e403  test    rax, rax
0x18000e406  jz      short loc_18000E40C
0x18000e408  mov     [rax+8], rcx
0x18000e40c  test    rcx, rcx
0x18000e40f  jz      short loc_18000E417
0x18000e411  mov     rax, [rdi]
0x18000e414  mov     [rcx], rax
0x18000e417  mov     rcx, rdi; this
0x18000e41a  mov     [rdi+8], r13
0x18000e41e  mov     [rdi], r13
0x18000e421  call    ?Destroy@EVENT_THREAD_CONTROL_BLOCK@@QEAAXXZ; EVENT_THREAD_CONTROL_BLOCK::Destroy(void)
0x18000e426  mov     rdx, rdi
0x18000e429  call    ?_ReturnEntryToFreeList@?$CLinkPool@UEVENT_THREAD_CONTROL_BLOCK@@@@AEAAXPEAUEVENT_THREAD_CONTROL_BLOCK@@@Z; CLinkPool<EVENT_THREAD_CONTROL_BLOCK>::_ReturnEntryToFreeList(EVENT_THREAD_CONTROL_BLOCK *)
0x18000e42e  mov     rcx, rbp; lpCriticalSection
0x18000e431  call    cs:__imp_EnterCriticalSection
0x18000e437  mov     eax, cs:dword_1800B8288
0x18000e43d  add     eax, r14d
0x18000e440  cmp     eax, cs:dword_1800B828C
0x18000e446  mov     cs:dword_1800B8288, eax
0x18000e44c  jbe     short loc_18000E454
0x18000e44e  mov     cs:dword_1800B828C, eax
0x18000e454  mov     rcx, rbp; lpCriticalSection
0x18000e457  call    cs:__imp_LeaveCriticalSection
0x18000e45d  mov     rcx, rbp; lpCriticalSection
0x18000e460  call    cs:__imp_EnterCriticalSection
0x18000e466  mov     eax, cs:dword_1800B8280
0x18000e46c  add     eax, r14d
0x18000e46f  cmp     eax, cs:dword_1800B8284
0x18000e475  mov     cs:dword_1800B8280, eax
0x18000e47b  jbe     short loc_18000E483
0x18000e47d  mov     cs:dword_1800B8284, eax
0x18000e483  mov     rcx, rbp; lpCriticalSection
0x18000e486  call    cs:__imp_LeaveCriticalSection
0x18000e48c  mov     rcx, rbp; lpCriticalSection
0x18000e48f  call    cs:__imp_LeaveCriticalSection
0x18000e495  lea     rcx, ?g_invsemThreadControlBlocks@@3VCInvSemaphore@@A; this
0x18000e49c  call    ?Decrement@CInvSemaphore@@QEAAXXZ; CInvSemaphore::Decrement(void)
0x18000e4a1  xor     ecx, ecx; pReserved
0x18000e4a3  call    cs:__imp_CoDisableCallCancellation
0x18000e4a9  call    cs:__imp_CoUninitialize
0x18000e4af  mov     rbx, [rsp+78h+arg_18]
0x18000e4b7  xor     eax, eax
0x18000e4b9  add     rsp, 40h
0x18000e4bd  pop     r15
0x18000e4bf  pop     r14
0x18000e4c1  pop     r13
0x18000e4c3  pop     r12
0x18000e4c5  pop     rdi
0x18000e4c6  pop     rsi
0x18000e4c7  pop     rbp
0x18000e4c8  retn
0x18000e4c9  mov     rcx, rdi; struct EVENT_THREAD_CONTROL_BLOCK *
0x18000e4cc  mov     [rdi+10h], r13d
0x18000e4d0  call    ?EventQueue_QueueWorkItem@@YAJPEAUEVENT_THREAD_CONTROL_BLOCK@@@Z; EventQueue_QueueWorkItem(EVENT_THREAD_CONTROL_BLOCK *)
0x18000e4d5  test    eax, eax
  ... truncated ...
```
