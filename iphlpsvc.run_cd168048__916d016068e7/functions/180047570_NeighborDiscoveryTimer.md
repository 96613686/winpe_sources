# NeighborDiscoveryTimer

- ea: `0x180047570`
- end: `0x180047b32`
- name: `NeighborDiscoveryTimer`
- size: `1474`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004c54`
- `0x18000d7b0`
- `0x180012dbc`
- `0x180013570`
- `0x180030d24`
- `0x180047570`
- `0x180047b38`
- `0x180049998`
- `0x18004b630`
- `0x18004c1c8`
- `0x180061694`
- `0x180064338`
- `0x180064618`
- `0x18006532c`
- `0x180066630`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringW` at `0x180047963`
- `ntdll!RtlIpv6AddressToStringW` at `0x180047963`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180047638`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18004790a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180047638`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18004790a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047689`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047a41`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047689`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047a41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047760`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047846`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047acd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047760`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047846`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047acd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004773f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004773f`

## string_xrefs

- `0x1800475f5`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x1800477b6`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x1800478c7`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180047a0c`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180047a7e`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180047aa8`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180047ade`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`

## pseudocode

```c
void __fastcall NeighborDiscoveryTimer(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_TIMER Timer)
{
  __int64 v4; // rcx
  _QWORD *v5; // rax
  int v6; // ecx
  __int64 v7; // rbx
  struct _RTL_CRITICAL_SECTION *v8; // r15
  __int64 v9; // rsi
  char *v10; // rdx
  __int128 v11; // xmm6
  _QWORD *v12; // rax
  unsigned int v13; // ecx
  void **v14; // r14
  bool v15; // zf
  void **v16; // r15
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // r14
  __int64 v20; // r8
  void ***v21; // rax
  __int64 v22; // rcx
  __int64 v23; // r14
  __int64 v24; // rcx
  _QWORD *v25; // rax
  int v26; // ecx
  __int64 v27; // rcx
  __int64 v28; // r14
  __int64 v29; // rcx
  __int128 v30; // xmm1
  __int64 v31; // rcx
  __int64 v32; // [rsp+28h] [rbp-E0h]
  __int64 v33; // [rsp+28h] [rbp-E0h]
  __int128 v34; // [rsp+38h] [rbp-D0h] BYREF
  void **v35; // [rsp+48h] [rbp-C0h]
  WCHAR S[72]; // [rsp+58h] [rbp-B0h] BYREF

  memset_0(S, 0, 0x82u);
  v34 = 0;
  IpTlsAcquireLock(g_IpTlsInterfaceListLock);
  v4 = *((_QWORD *)Context + 36);
  v5 = *(_QWORD **)(v4 + 1176);
  if ( v5 )
  {
    v7 = (__int64)(v5 - 6);
    *(_QWORD *)(v4 + 1176) = *v5;
    _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)Context + 36) + 1188LL));
  }
  else
  {
    v7 = MALLOC(0x80A0u);
    if ( !v7 && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x1000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v6,
        (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE,
        0,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
        202);
  }
  ReleaseMutex(g_IpTlsInterfaceListLock);
  if ( v7 )
  {
    memset_0((void *)v7, 0, 0x80A0u);
    *(_DWORD *)(v7 + 80) = 1;
    *(_QWORD *)(v7 + 136) = SendBufferCleanup;
  }
  *((_QWORD *)&v34 + 1) = &v34;
  v8 = (struct _RTL_CRITICAL_SECTION *)(Context + 240);
  *(_QWORD *)&v34 = &v34;
  EnterCriticalSection((LPCRITICAL_SECTION)Context + 6);
  if ( (*((_DWORD *)Context + 92) & 0x25) == 1 )
  {
    v9 = 0;
    v10 = (char *)*((_QWORD *)Context + 1);
    if ( v10 == Context + 8 )
      v11 = 0;
    else
      v11 = *(_OWORD *)(v10 - 24);
    v12 = Context + 312;
    v13 = *((_DWORD *)Context + 92) | 4;
    v14 = (void **)*((_QWORD *)Context + 39);
    *((_DWORD *)Context + 92) = v13;
    if ( v14 == (void **)(Context + 312) )
      goto LABEL_18;
    while ( 1 )
    {
      v15 = v14[4] == 0;
      v16 = v14 - 3;
      v35 = (void **)*v14;
      if ( v15 )
      {
        IpTlsServerRemoveNDEntry(Context, v14 - 3);
        FREE(v14 - 3);
      }
      else
      {
        if ( *((_BYTE *)v16 + 72) )
        {
          LeaveCriticalSection((LPCRITICAL_SECTION)Context + 6);
          if ( !*((_BYTE *)v16 + 73) )
          {
            if ( v7 )
            {
              v22 = *(unsigned int *)(v7 + 96);
              if ( (unsigned __int64)(v22 + 64) <= 0x8000 )
              {
                *(_DWORD *)(v7 + 96) = v22 + 64;
                v23 = v22 + v7;
LABEL_44:
                v28 = v23 + 152;
                if ( v28 )
                {
                  RtlIpv6AddressToStringW((const struct in6_addr *)(v16 + 5), S);
                  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
                    McTemplateU0zz_EventWriteTransfer(
                      v29,
                      EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_NEIGHBOR_DISCOVERY,
                      *((_QWORD *)Context + 36) + 56LL,
                      S);
                  *(_DWORD *)(v28 + 4) = -12969984;
                  *(_DWORD *)v28 = 96;
                  *(_OWORD *)(v28 + 8) = v11;
                  *(_OWORD *)(v28 + 24) = *(_OWORD *)(v16 + 5);
                  v30 = *(_OWORD *)(v16 + 5);
                  *(_WORD *)(v28 + 40) = 135;
                  *(_OWORD *)(v28 + 48) = v30;
                  *(_WORD *)(v28 + 42) = ComputeIcmpv6Checksum(v28);
                }
              }
            }
LABEL_48:
            if ( *((_BYTE *)v16 + 73) && v9 )
            {
              if ( !(unsigned __int8)IpTlsLimitedBroadcastPacket(Context, v9, (unsigned int)(*(_DWORD *)(v9 + 96) - 64)) )
              {
                *(_DWORD *)(v9 + 96) -= 64;
                *((_BYTE *)v16 + 72) = 1;
              }
              if ( (unsigned int)(*(_DWORD *)(v9 + 96) + 64) > 0x8000 )
              {
                LODWORD(v32) = 5282;
                EventWrite0(
                  0x20000000,
                  L"(Dereference IPTLS Buffer(%p)%S:%d",
                  v9,
                  "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
                  v32);
                IpTlsDereferenceBufferEx(v9);
                v9 = 0;
              }
            }
            --*((_BYTE *)v16 + 72);
            v8 = (struct _RTL_CRITICAL_SECTION *)(Context + 240);
            EnterCriticalSection((LPCRITICAL_SECTION)Context + 6);
            goto LABEL_16;
          }
          if ( !v9 )
          {
            IpTlsAcquireLock(g_IpTlsInterfaceListLock);
            v24 = *((_QWORD *)Context + 36);
            v25 = *(_QWORD **)(v24 + 1176);
            if ( v25 )
            {
              v9 = (__int64)(v25 - 6);
              *(_QWORD *)(v24 + 1176) = *v25;
              _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)Context + 36) + 1188LL));
            }
            else
            {
              v9 = MALLOC(0x80A0u);
              if ( !v9 && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x1000) != 0 )
                McTemplateU0psq_EventWriteTransfer(
                  v26,
                  (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE,
                  0,
                  (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
                  83);
            }
            ReleaseMutex(g_IpTlsInterfaceListLock);
            if ( !v9 )
              goto LABEL_48;
            memset_0((void *)v9, 0, 0x80A0u);
            *(_DWORD *)(v9 + 80) = 1;
            *(_QWORD *)(v9 + 136) = SendBufferCleanup;
          }
          v27 = *(unsigned int *)(v9 + 96);
          *(_DWORD *)(v9 + 96) = v27 + 64;
          v23 = v9 + v27;
          goto LABEL_44;
        }
        IpTlsServerRemoveNDEntry(Context, v14 - 3);
        v21 = (void ***)*((_QWORD *)&v34 + 1);
        if ( **((__int128 ***)&v34 + 1) != &v34 )
LABEL_55:
          __fastfail(3u);
        v14[1] = (void *)*((_QWORD *)&v34 + 1);
        *v14 = &v34;
        *v21 = v14;
        *((_QWORD *)&v34 + 1) = v14;
        if ( *((_BYTE *)v16 + 73) )
          IpTlsRemoveConflictEntries(Context, v16 + 5);
      }
      v8 = (struct _RTL_CRITICAL_SECTION *)(Context + 240);
LABEL_16:
      v14 = v35;
      v12 = Context + 312;
      if ( v35 == (void **)(Context + 312) )
      {
        v13 = *((_DWORD *)Context + 92);
LABEL_18:
        if ( (_QWORD *)*v12 == v12 )
        {
          SetThreadpoolTimer(*((PTP_TIMER *)Context + 38), 0, 0, 0);
          v13 = *((_DWORD *)Context + 92) & 0xFFFFFFFE;
        }
        *((_DWORD *)Context + 92) = v13 & 0xFFFFFFFB;
        LeaveCriticalSection(v8);
        while ( 1 )
        {
          v17 = v34;
          if ( (__int128 *)v34 == &v34 )
            break;
          if ( *(__int128 **)(v34 + 8) != &v34 )
            goto LABEL_55;
          v18 = *(_QWORD *)v34;
          if ( *(_QWORD *)(*(_QWORD *)v34 + 8LL) != (_QWORD)v34 )
            goto LABEL_55;
          *(_QWORD *)&v34 = *(_QWORD *)v34;
          v19 = v17 - 24;
          *(_QWORD *)(v18 + 8) = &v34;
          v20 = *(_QWORD *)(v17 - 24 + 56);
          if ( v20 )
          {
            LODWORD(v32) = 5323;
            EventWrite0(
              0x20000000,
              L"(Dereference IPTLS Buffer(%p)%S:%d",
              v20,
              "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
              v32);
            IpTlsDereferenceBufferEx(*(_QWORD *)(v19 + 56));
            ++g_IpTlsGlobalStatsNDDrops;
          }
          FREE(v19);
        }
        if ( v7 )
        {
          BroadcastBufferOnInterface((_DWORD)Context, v7, 0, *(_DWORD *)(v7 + 96), 0, 0);
          LODWORD(v33) = 5339;
          EventWrite0(
            0x20000000,
            L"(Dereference IPTLS Buffer(%p)%S:%d",
            v7,
            "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
            v33);
          IpTlsDereferenceBufferEx(v7);
        }
        if ( v9 )
        {
          LODWORD(v32) = 5344;
          EventWrite0(
            0x20000000,
            L"(Dereference IPTLS Buffer(%p)%S:%d",
            v9,
            "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
            v32);
          v31 = v9;
          goto LABEL_62;
        }
        return;
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)Context + 6);
  if ( v7 )
  {
    LODWORD(v32) = 5099;
    EventWrite0(
      0x20000000,
      L"(Dereference IPTLS Buffer(%p)%S:%d",
      v7,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
      v32);
    v31 = v7;
LABEL_62:
    IpTlsDereferenceBufferEx(v31);
  }
}

```

## disassembly

```asm
0x180047570  mov     rax, rsp
0x180047573  push    rbp
0x180047574  push    rbx
0x180047575  push    rsi
0x180047576  push    rdi
0x180047577  push    r12
0x180047579  push    r13
0x18004757b  push    r14
0x18004757d  push    r15
0x18004757f  lea     rbp, [rax-48h]
0x180047583  sub     rsp, 108h
0x18004758a  movaps  xmmword ptr [rax-58h], xmm6
0x18004758e  mov     rax, cs:__security_cookie
0x180047595  xor     rax, rsp
0x180047598  mov     [rbp+40h+var_60], rax
0x18004759c  mov     rdi, rdx
0x18004759f  lea     rcx, [rsp+140h+S]; void *
0x1800475a4  xor     edx, edx; Val
0x1800475a6  mov     r8d, 82h; Size
0x1800475ac  call    memset_0
0x1800475b1  mov     rcx, cs:g_IpTlsInterfaceListLock
0x1800475b8  xorps   xmm0, xmm0
0x1800475bb  movups  [rsp+140h+var_118+8], xmm0
0x1800475c0  call    IpTlsAcquireLock
0x1800475c5  mov     rcx, [rdi+120h]
0x1800475cc  mov     esi, 80A0h
0x1800475d1  mov     rax, [rcx+498h]
0x1800475d8  test    rax, rax
0x1800475db  jnz     short loc_180047615
0x1800475dd  mov     ecx, esi; dwBytes
0x1800475df  call    MALLOC
0x1800475e4  mov     rbx, rax
0x1800475e7  test    rax, rax
0x1800475ea  jnz     short loc_180047631
0x1800475ec  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x1800475f3  jz      short loc_180047631
0x1800475f5  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800475fc  mov     dword ptr [rsp+140h+var_120], 13CAh
0x180047604  xor     r8d, r8d
0x180047607  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x18004760e  call    McTemplateU0psq_EventWriteTransfer
0x180047613  jmp     short loc_180047631
0x180047615  lea     rbx, [rax-30h]
0x180047619  mov     rax, [rax]
0x18004761c  mov     [rcx+498h], rax
0x180047623  mov     rax, [rdi+120h]
0x18004762a  lock dec dword ptr [rax+4A4h]
0x180047631  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x180047638  call    cs:__imp_ReleaseMutex
0x18004763f  nop     dword ptr [rax+rax+00h]
0x180047644  lea     r14, SendBufferCleanup
0x18004764b  test    rbx, rbx
0x18004764e  jz      short loc_18004766B
0x180047650  mov     r8, rsi; Size
0x180047653  xor     edx, edx; Val
0x180047655  mov     rcx, rbx; void *
0x180047658  call    memset_0
0x18004765d  mov     dword ptr [rbx+50h], 1
0x180047664  mov     [rbx+88h], r14
0x18004766b  lea     rax, [rsp+140h+var_118+8]
0x180047670  mov     [rsp+140h+var_108], rax
0x180047675  lea     r15, [rdi+0F0h]
0x18004767c  lea     rax, [rsp+140h+var_118+8]
0x180047681  mov     rcx, r15; lpCriticalSection
0x180047684  mov     qword ptr [rsp+140h+var_118+8], rax
0x180047689  call    cs:__imp_EnterCriticalSection
0x180047690  nop     dword ptr [rax+rax+00h]
0x180047695  mov     ecx, [rdi+170h]
0x18004769b  mov     eax, ecx
0x18004769d  and     al, 25h
0x18004769f  cmp     al, 1
0x1800476a1  jnz     loc_180047ACA
0x1800476a7  lea     rax, [rdi+8]
0x1800476ab  xor     esi, esi
0x1800476ad  mov     rdx, [rax]
0x1800476b0  cmp     rdx, rax
0x1800476b3  jnz     short loc_1800476BA
0x1800476b5  xorps   xmm6, xmm6
0x1800476b8  jmp     short loc_1800476BE
0x1800476ba  movups  xmm6, xmmword ptr [rdx-18h]
0x1800476be  lea     rax, [rdi+138h]
0x1800476c5  or      ecx, 4
0x1800476c8  mov     r14, [rax]
0x1800476cb  lea     r12, aDereferenceIpt; "(Dereference IPTLS Buffer(%p)%S:%d"
0x1800476d2  mov     [rdi+170h], ecx
0x1800476d8  mov     r13d, 20000000h
0x1800476de  cmp     r14, rax
0x1800476e1  jz      short loc_18004772B
0x1800476e3  cmp     qword ptr [r14+20h], 0
0x1800476e8  lea     r15, [r14-18h]
0x1800476ec  mov     rax, [r14]
0x1800476ef  mov     [rsp+140h+var_100], rax
0x1800476f4  jnz     loc_1800477EA
0x1800476fa  mov     rdx, r15
0x1800476fd  mov     rcx, rdi
0x180047700  call    IpTlsServerRemoveNDEntry
0x180047705  mov     rcx, r15
0x180047708  call    FREE
0x18004770d  lea     r15, [rdi+0F0h]
0x180047714  mov     r14, [rsp+140h+var_100]
0x180047719  lea     rax, [rdi+138h]
0x180047720  cmp     r14, rax
0x180047723  jnz     short loc_1800476E3
0x180047725  mov     ecx, [rdi+170h]
0x18004772b  cmp     [rax], rax
0x18004772e  jnz     short loc_180047754
0x180047730  mov     rcx, [rdi+130h]; pti
0x180047737  xor     r9d, r9d; msWindowLength
0x18004773a  xor     r8d, r8d; msPeriod
0x18004773d  xor     edx, edx; pftDueTime
0x18004773f  call    cs:__imp_SetThreadpoolTimer
0x180047746  nop     dword ptr [rax+rax+00h]
0x18004774b  mov     ecx, [rdi+170h]
0x180047751  and     ecx, 0FFFFFFFEh
0x180047754  and     ecx, 0FFFFFFFBh
0x180047757  mov     [rdi+170h], ecx
0x18004775d  mov     rcx, r15; lpCriticalSection
0x180047760  call    cs:__imp_LeaveCriticalSection
0x180047767  nop     dword ptr [rax+rax+00h]
0x18004776c  mov     rax, qword ptr [rsp+140h+var_118+8]
0x180047771  lea     rcx, [rsp+140h+var_118+8]
0x180047776  cmp     rax, rcx
0x180047779  jz      loc_180047A59
0x18004777f  lea     rcx, [rsp+140h+var_118+8]
0x180047784  cmp     [rax+8], rcx
0x180047788  jnz     loc_180047A52
0x18004778e  mov     rcx, [rax]
0x180047791  cmp     [rcx+8], rax
0x180047795  jnz     loc_180047A52
0x18004779b  mov     qword ptr [rsp+140h+var_118+8], rcx
0x1800477a0  lea     rdx, [rsp+140h+var_118+8]
0x1800477a5  lea     r14, [rax-18h]
0x1800477a9  mov     [rcx+8], rdx
0x1800477ad  mov     r8, [r14+38h]
0x1800477b1  test    r8, r8
0x1800477b4  jz      short loc_1800477E0
0x1800477b6  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800477bd  mov     dword ptr [rsp+140h+var_120], 14CBh
0x1800477c5  mov     rdx, r12
0x1800477c8  mov     ecx, r13d
0x1800477cb  call    EventWrite0
0x1800477d0  mov     rcx, [r14+38h]
0x1800477d4  call    IpTlsDereferenceBufferEx
0x1800477d9  inc     cs:g_IpTlsGlobalStatsNDDrops
0x1800477e0  mov     rcx, r14
0x1800477e3  call    FREE
0x1800477e8  jmp     short loc_18004776C
0x1800477ea  cmp     byte ptr [r15+48h], 0
0x1800477ef  jnz     short loc_18004783F
0x1800477f1  mov     rdx, r15
0x1800477f4  mov     rcx, rdi
0x1800477f7  call    IpTlsServerRemoveNDEntry
0x1800477fc  mov     rax, [rsp+140h+var_108]
0x180047801  lea     rcx, [rsp+140h+var_118+8]
0x180047806  cmp     [rax], rcx
0x180047809  jnz     loc_180047A52
0x18004780f  mov     [r14+8], rax
0x180047813  lea     rcx, [rsp+140h+var_118+8]
0x180047818  mov     [r14], rcx
0x18004781b  mov     [rax], r14
0x18004781e  mov     [rsp+140h+var_108], r14
0x180047823  cmp     byte ptr [r15+49h], 0
0x180047828  jz      loc_18004770D
0x18004782e  lea     rdx, [r15+28h]
0x180047832  mov     rcx, rdi
0x180047835  call    IpTlsRemoveConflictEntries
0x18004783a  jmp     loc_18004770D
0x18004783f  lea     rcx, [rdi+0F0h]; lpCriticalSection
0x180047846  call    cs:__imp_LeaveCriticalSection
0x18004784d  nop     dword ptr [rax+rax+00h]
0x180047852  cmp     byte ptr [r15+49h], 0
0x180047857  jnz     short loc_180047884
0x180047859  test    rbx, rbx
0x18004785c  jz      loc_1800479D3
0x180047862  mov     ecx, [rbx+60h]
0x180047865  lea     rax, [rcx+40h]
0x180047869  cmp     rax, 8000h
0x18004786f  ja      loc_1800479D3
0x180047875  lea     eax, [rcx+40h]
0x180047878  mov     [rbx+60h], eax
0x18004787b  lea     r14, [rcx+rbx]
0x18004787f  jmp     loc_180047951
0x180047884  test    rsi, rsi
0x180047887  jnz     loc_180047944
0x18004788d  mov     rcx, cs:g_IpTlsInterfaceListLock
0x180047894  call    IpTlsAcquireLock
0x180047899  mov     rcx, [rdi+120h]
0x1800478a0  mov     rax, [rcx+498h]
0x1800478a7  test    rax, rax
0x1800478aa  jnz     short loc_1800478E7
0x1800478ac  mov     ecx, 80A0h; dwBytes
0x1800478b1  call    MALLOC
0x1800478b6  mov     rsi, rax
0x1800478b9  test    rax, rax
0x1800478bc  jnz     short loc_180047903
0x1800478be  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x1800478c5  jz      short loc_180047903
0x1800478c7  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800478ce  mov     dword ptr [rsp+140h+var_120], 1453h
0x1800478d6  xor     r8d, r8d
0x1800478d9  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x1800478e0  call    McTemplateU0psq_EventWriteTransfer
0x1800478e5  jmp     short loc_180047903
0x1800478e7  lea     rsi, [rax-30h]
0x1800478eb  mov     rax, [rax]
0x1800478ee  mov     [rcx+498h], rax
0x1800478f5  mov     rax, [rdi+120h]
0x1800478fc  lock dec dword ptr [rax+4A4h]
0x180047903  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x18004790a  call    cs:__imp_ReleaseMutex
0x180047911  nop     dword ptr [rax+rax+00h]
0x180047916  test    rsi, rsi
0x180047919  jz      loc_1800479D3
0x18004791f  xor     edx, edx; Val
0x180047921  mov     r8d, 80A0h; Size
0x180047927  mov     rcx, rsi; void *
0x18004792a  call    memset_0
0x18004792f  lea     rax, SendBufferCleanup
0x180047936  mov     dword ptr [rsi+50h], 1
0x18004793d  mov     [rsi+88h], rax
0x180047944  mov     ecx, [rsi+60h]
0x180047947  lea     eax, [rcx+40h]
0x18004794a  mov     [rsi+60h], eax
0x18004794d  lea     r14, [rsi+rcx]
0x180047951  add     r14, 98h
0x180047958  jz      short loc_1800479D3
0x18004795a  lea     rcx, [r15+28h]; Addr
0x18004795e  lea     rdx, [rsp+140h+S]; S
0x180047963  call    cs:__imp_RtlIpv6AddressToStringW
0x18004796a  nop     dword ptr [rax+rax+00h]
0x18004796f  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180047976  jz      short loc_180047994
0x180047978  mov     r8, [rdi+120h]
0x18004797f  lea     r9, [rsp+140h+S]
0x180047984  add     r8, 38h ; '8'
0x180047988  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_NEIGHBOR_DISCOVERY
0x18004798f  call    McTemplateU0zz_EventWriteTransfer
0x180047994  mov     dword ptr [r14+4], 0FF3A1800h
0x18004799c  mov     rcx, r14
0x18004799f  mov     dword ptr [r14], 60h ; '`'
0x1800479a6  movdqu  xmmword ptr [r14+8], xmm6
0x1800479ac  movups  xmm0, xmmword ptr [r15+28h]
0x1800479b1  movdqu  xmmword ptr [r14+18h], xmm0
0x1800479b7  movups  xmm1, xmmword ptr [r15+28h]
0x1800479bc  mov     word ptr [r14+28h], 87h
0x1800479c3  movdqu  xmmword ptr [r14+30h], xmm1
0x1800479c9  call    ComputeIcmpv6Checksum
0x1800479ce  mov     [r14+2Ah], ax
0x1800479d3  cmp     byte ptr [r15+49h], 0
0x1800479d8  jz      short loc_180047A33
0x1800479da  test    rsi, rsi
0x1800479dd  jz      short loc_180047A33
0x1800479df  mov     r8d, [rsi+60h]
0x1800479e3  mov     rdx, rsi
0x1800479e6  sub     r8d, 40h ; '@'
0x1800479ea  mov     rcx, rdi
0x1800479ed  call    IpTlsLimitedBroadcastPacket
0x1800479f2  test    al, al
0x1800479f4  jnz     short loc_1800479FF
0x1800479f6  add     dword ptr [rsi+60h], 0FFFFFFC0h
0x1800479fa  mov     byte ptr [r15+48h], 1
0x1800479ff  mov     eax, [rsi+60h]
0x180047a02  add     eax, 40h ; '@'
0x180047a05  cmp     eax, 8000h
0x180047a0a  jbe     short loc_180047A33
0x180047a0c  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180047a13  mov     dword ptr [rsp+140h+var_120], 14A2h
0x180047a1b  mov     r8, rsi
0x180047a1e  mov     rdx, r12
0x180047a21  mov     ecx, r13d
0x180047a24  call    EventWrite0
0x180047a29  mov     rcx, rsi
0x180047a2c  call    IpTlsDereferenceBufferEx
0x180047a31  xor     esi, esi
0x180047a33  dec     byte ptr [r15+48h]
0x180047a37  lea     r15, [rdi+0F0h]
0x180047a3e  mov     rcx, r15; lpCriticalSection
0x180047a41  call    cs:__imp_EnterCriticalSection
0x180047a48  nop     dword ptr [rax+rax+00h]
0x180047a4d  jmp     loc_180047714
0x180047a52  mov     ecx, 3
0x180047a57  int     29h; Win8: RtlFailFast(ecx)
0x180047a59  test    rbx, rbx
0x180047a5c  jz      short loc_180047AA3
0x180047a5e  mov     r9d, [rbx+60h]
0x180047a62  xor     r8d, r8d
0x180047a65  mov     byte ptr [rsp+140h+var_118], 0
0x180047a6a  mov     rdx, rbx
0x180047a6d  mov     rcx, rdi
0x180047a70  mov     [rsp+140h+var_120], 0
0x180047a79  call    BroadcastBufferOnInterface
0x180047a7e  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180047a85  mov     dword ptr [rsp+140h+var_120], 14DBh
0x180047a8d  mov     r8, rbx
0x180047a90  mov     rdx, r12
0x180047a93  mov     ecx, r13d
0x180047a96  call    EventWrite0
0x180047a9b  mov     rcx, rbx
0x180047a9e  call    IpTlsDereferenceBufferEx
0x180047aa3  test    rsi, rsi
  ... truncated ...
```
