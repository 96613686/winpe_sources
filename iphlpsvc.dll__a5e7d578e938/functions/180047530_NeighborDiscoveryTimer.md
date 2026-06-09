# NeighborDiscoveryTimer

- ea: `0x180047530`
- end: `0x180047af2`
- name: `NeighborDiscoveryTimer`
- size: `1474`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004c64`
- `0x18000d7c0`
- `0x180012dcc`
- `0x180013580`
- `0x180030d34`
- `0x180047530`
- `0x180047af8`
- `0x180049958`
- `0x18004b5f0`
- `0x18004c188`
- `0x1800616b4`
- `0x180064358`
- `0x180064638`
- `0x18006534c`
- `0x180066650`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringW` at `0x180047923`
- `ntdll!RtlIpv6AddressToStringW` at `0x180047923`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800475f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800478ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800475f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800478ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047649`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047a01`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047649`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047a01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047720`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047806`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047a8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047720`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047806`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047a8d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800476ff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800476ff`

## string_xrefs

- `0x1800475b5`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180047776`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180047887`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x1800479cc`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180047a3e`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180047a68`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180047a9e`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`

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
          BroadcastBufferOnInterface((__int64)Context, v7, 0, *(_DWORD *)(v7 + 96), 0, 0);
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
0x180047530  mov     rax, rsp
0x180047533  push    rbp
0x180047534  push    rbx
0x180047535  push    rsi
0x180047536  push    rdi
0x180047537  push    r12
0x180047539  push    r13
0x18004753b  push    r14
0x18004753d  push    r15
0x18004753f  lea     rbp, [rax-48h]
0x180047543  sub     rsp, 108h
0x18004754a  movaps  xmmword ptr [rax-58h], xmm6
0x18004754e  mov     rax, cs:__security_cookie
0x180047555  xor     rax, rsp
0x180047558  mov     [rbp+40h+var_60], rax
0x18004755c  mov     rdi, rdx
0x18004755f  lea     rcx, [rsp+140h+S]; void *
0x180047564  xor     edx, edx; Val
0x180047566  mov     r8d, 82h; Size
0x18004756c  call    memset_0
0x180047571  mov     rcx, cs:g_IpTlsInterfaceListLock
0x180047578  xorps   xmm0, xmm0
0x18004757b  movups  [rsp+140h+var_118+8], xmm0
0x180047580  call    IpTlsAcquireLock
0x180047585  mov     rcx, [rdi+120h]
0x18004758c  mov     esi, 80A0h
0x180047591  mov     rax, [rcx+498h]
0x180047598  test    rax, rax
0x18004759b  jnz     short loc_1800475D5
0x18004759d  mov     ecx, esi; dwBytes
0x18004759f  call    MALLOC
0x1800475a4  mov     rbx, rax
0x1800475a7  test    rax, rax
0x1800475aa  jnz     short loc_1800475F1
0x1800475ac  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x1800475b3  jz      short loc_1800475F1
0x1800475b5  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800475bc  mov     dword ptr [rsp+140h+var_120], 13CAh
0x1800475c4  xor     r8d, r8d
0x1800475c7  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x1800475ce  call    McTemplateU0psq_EventWriteTransfer
0x1800475d3  jmp     short loc_1800475F1
0x1800475d5  lea     rbx, [rax-30h]
0x1800475d9  mov     rax, [rax]
0x1800475dc  mov     [rcx+498h], rax
0x1800475e3  mov     rax, [rdi+120h]
0x1800475ea  lock dec dword ptr [rax+4A4h]
0x1800475f1  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x1800475f8  call    cs:__imp_ReleaseMutex
0x1800475ff  nop     dword ptr [rax+rax+00h]
0x180047604  lea     r14, SendBufferCleanup
0x18004760b  test    rbx, rbx
0x18004760e  jz      short loc_18004762B
0x180047610  mov     r8, rsi; Size
0x180047613  xor     edx, edx; Val
0x180047615  mov     rcx, rbx; void *
0x180047618  call    memset_0
0x18004761d  mov     dword ptr [rbx+50h], 1
0x180047624  mov     [rbx+88h], r14
0x18004762b  lea     rax, [rsp+140h+var_118+8]
0x180047630  mov     [rsp+140h+var_108], rax
0x180047635  lea     r15, [rdi+0F0h]
0x18004763c  lea     rax, [rsp+140h+var_118+8]
0x180047641  mov     rcx, r15; lpCriticalSection
0x180047644  mov     qword ptr [rsp+140h+var_118+8], rax
0x180047649  call    cs:__imp_EnterCriticalSection
0x180047650  nop     dword ptr [rax+rax+00h]
0x180047655  mov     ecx, [rdi+170h]
0x18004765b  mov     eax, ecx
0x18004765d  and     al, 25h
0x18004765f  cmp     al, 1
0x180047661  jnz     loc_180047A8A
0x180047667  lea     rax, [rdi+8]
0x18004766b  xor     esi, esi
0x18004766d  mov     rdx, [rax]
0x180047670  cmp     rdx, rax
0x180047673  jnz     short loc_18004767A
0x180047675  xorps   xmm6, xmm6
0x180047678  jmp     short loc_18004767E
0x18004767a  movups  xmm6, xmmword ptr [rdx-18h]
0x18004767e  lea     rax, [rdi+138h]
0x180047685  or      ecx, 4
0x180047688  mov     r14, [rax]
0x18004768b  lea     r12, aDereferenceIpt; "(Dereference IPTLS Buffer(%p)%S:%d"
0x180047692  mov     [rdi+170h], ecx
0x180047698  mov     r13d, 20000000h
0x18004769e  cmp     r14, rax
0x1800476a1  jz      short loc_1800476EB
0x1800476a3  cmp     qword ptr [r14+20h], 0
0x1800476a8  lea     r15, [r14-18h]
0x1800476ac  mov     rax, [r14]
0x1800476af  mov     [rsp+140h+var_100], rax
0x1800476b4  jnz     loc_1800477AA
0x1800476ba  mov     rdx, r15
0x1800476bd  mov     rcx, rdi
0x1800476c0  call    IpTlsServerRemoveNDEntry
0x1800476c5  mov     rcx, r15
0x1800476c8  call    FREE
0x1800476cd  lea     r15, [rdi+0F0h]
0x1800476d4  mov     r14, [rsp+140h+var_100]
0x1800476d9  lea     rax, [rdi+138h]
0x1800476e0  cmp     r14, rax
0x1800476e3  jnz     short loc_1800476A3
0x1800476e5  mov     ecx, [rdi+170h]
0x1800476eb  cmp     [rax], rax
0x1800476ee  jnz     short loc_180047714
0x1800476f0  mov     rcx, [rdi+130h]; pti
0x1800476f7  xor     r9d, r9d; msWindowLength
0x1800476fa  xor     r8d, r8d; msPeriod
0x1800476fd  xor     edx, edx; pftDueTime
0x1800476ff  call    cs:__imp_SetThreadpoolTimer
0x180047706  nop     dword ptr [rax+rax+00h]
0x18004770b  mov     ecx, [rdi+170h]
0x180047711  and     ecx, 0FFFFFFFEh
0x180047714  and     ecx, 0FFFFFFFBh
0x180047717  mov     [rdi+170h], ecx
0x18004771d  mov     rcx, r15; lpCriticalSection
0x180047720  call    cs:__imp_LeaveCriticalSection
0x180047727  nop     dword ptr [rax+rax+00h]
0x18004772c  mov     rax, qword ptr [rsp+140h+var_118+8]
0x180047731  lea     rcx, [rsp+140h+var_118+8]
0x180047736  cmp     rax, rcx
0x180047739  jz      loc_180047A19
0x18004773f  lea     rcx, [rsp+140h+var_118+8]
0x180047744  cmp     [rax+8], rcx
0x180047748  jnz     loc_180047A12
0x18004774e  mov     rcx, [rax]
0x180047751  cmp     [rcx+8], rax
0x180047755  jnz     loc_180047A12
0x18004775b  mov     qword ptr [rsp+140h+var_118+8], rcx
0x180047760  lea     rdx, [rsp+140h+var_118+8]
0x180047765  lea     r14, [rax-18h]
0x180047769  mov     [rcx+8], rdx
0x18004776d  mov     r8, [r14+38h]
0x180047771  test    r8, r8
0x180047774  jz      short loc_1800477A0
0x180047776  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18004777d  mov     dword ptr [rsp+140h+var_120], 14CBh
0x180047785  mov     rdx, r12
0x180047788  mov     ecx, r13d
0x18004778b  call    EventWrite0
0x180047790  mov     rcx, [r14+38h]
0x180047794  call    IpTlsDereferenceBufferEx
0x180047799  inc     cs:g_IpTlsGlobalStatsNDDrops
0x1800477a0  mov     rcx, r14
0x1800477a3  call    FREE
0x1800477a8  jmp     short loc_18004772C
0x1800477aa  cmp     byte ptr [r15+48h], 0
0x1800477af  jnz     short loc_1800477FF
0x1800477b1  mov     rdx, r15
0x1800477b4  mov     rcx, rdi
0x1800477b7  call    IpTlsServerRemoveNDEntry
0x1800477bc  mov     rax, [rsp+140h+var_108]
0x1800477c1  lea     rcx, [rsp+140h+var_118+8]
0x1800477c6  cmp     [rax], rcx
0x1800477c9  jnz     loc_180047A12
0x1800477cf  mov     [r14+8], rax
0x1800477d3  lea     rcx, [rsp+140h+var_118+8]
0x1800477d8  mov     [r14], rcx
0x1800477db  mov     [rax], r14
0x1800477de  mov     [rsp+140h+var_108], r14
0x1800477e3  cmp     byte ptr [r15+49h], 0
0x1800477e8  jz      loc_1800476CD
0x1800477ee  lea     rdx, [r15+28h]
0x1800477f2  mov     rcx, rdi
0x1800477f5  call    IpTlsRemoveConflictEntries
0x1800477fa  jmp     loc_1800476CD
0x1800477ff  lea     rcx, [rdi+0F0h]; lpCriticalSection
0x180047806  call    cs:__imp_LeaveCriticalSection
0x18004780d  nop     dword ptr [rax+rax+00h]
0x180047812  cmp     byte ptr [r15+49h], 0
0x180047817  jnz     short loc_180047844
0x180047819  test    rbx, rbx
0x18004781c  jz      loc_180047993
0x180047822  mov     ecx, [rbx+60h]
0x180047825  lea     rax, [rcx+40h]
0x180047829  cmp     rax, 8000h
0x18004782f  ja      loc_180047993
0x180047835  lea     eax, [rcx+40h]
0x180047838  mov     [rbx+60h], eax
0x18004783b  lea     r14, [rcx+rbx]
0x18004783f  jmp     loc_180047911
0x180047844  test    rsi, rsi
0x180047847  jnz     loc_180047904
0x18004784d  mov     rcx, cs:g_IpTlsInterfaceListLock
0x180047854  call    IpTlsAcquireLock
0x180047859  mov     rcx, [rdi+120h]
0x180047860  mov     rax, [rcx+498h]
0x180047867  test    rax, rax
0x18004786a  jnz     short loc_1800478A7
0x18004786c  mov     ecx, 80A0h; dwBytes
0x180047871  call    MALLOC
0x180047876  mov     rsi, rax
0x180047879  test    rax, rax
0x18004787c  jnz     short loc_1800478C3
0x18004787e  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x180047885  jz      short loc_1800478C3
0x180047887  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18004788e  mov     dword ptr [rsp+140h+var_120], 1453h
0x180047896  xor     r8d, r8d
0x180047899  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x1800478a0  call    McTemplateU0psq_EventWriteTransfer
0x1800478a5  jmp     short loc_1800478C3
0x1800478a7  lea     rsi, [rax-30h]
0x1800478ab  mov     rax, [rax]
0x1800478ae  mov     [rcx+498h], rax
0x1800478b5  mov     rax, [rdi+120h]
0x1800478bc  lock dec dword ptr [rax+4A4h]
0x1800478c3  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x1800478ca  call    cs:__imp_ReleaseMutex
0x1800478d1  nop     dword ptr [rax+rax+00h]
0x1800478d6  test    rsi, rsi
0x1800478d9  jz      loc_180047993
0x1800478df  xor     edx, edx; Val
0x1800478e1  mov     r8d, 80A0h; Size
0x1800478e7  mov     rcx, rsi; void *
0x1800478ea  call    memset_0
0x1800478ef  lea     rax, SendBufferCleanup
0x1800478f6  mov     dword ptr [rsi+50h], 1
0x1800478fd  mov     [rsi+88h], rax
0x180047904  mov     ecx, [rsi+60h]
0x180047907  lea     eax, [rcx+40h]
0x18004790a  mov     [rsi+60h], eax
0x18004790d  lea     r14, [rsi+rcx]
0x180047911  add     r14, 98h
0x180047918  jz      short loc_180047993
0x18004791a  lea     rcx, [r15+28h]; Addr
0x18004791e  lea     rdx, [rsp+140h+S]; S
0x180047923  call    cs:__imp_RtlIpv6AddressToStringW
0x18004792a  nop     dword ptr [rax+rax+00h]
0x18004792f  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180047936  jz      short loc_180047954
0x180047938  mov     r8, [rdi+120h]
0x18004793f  lea     r9, [rsp+140h+S]
0x180047944  add     r8, 38h ; '8'
0x180047948  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_NEIGHBOR_DISCOVERY
0x18004794f  call    McTemplateU0zz_EventWriteTransfer
0x180047954  mov     dword ptr [r14+4], 0FF3A1800h
0x18004795c  mov     rcx, r14
0x18004795f  mov     dword ptr [r14], 60h ; '`'
0x180047966  movdqu  xmmword ptr [r14+8], xmm6
0x18004796c  movups  xmm0, xmmword ptr [r15+28h]
0x180047971  movdqu  xmmword ptr [r14+18h], xmm0
0x180047977  movups  xmm1, xmmword ptr [r15+28h]
0x18004797c  mov     word ptr [r14+28h], 87h
0x180047983  movdqu  xmmword ptr [r14+30h], xmm1
0x180047989  call    ComputeIcmpv6Checksum
0x18004798e  mov     [r14+2Ah], ax
0x180047993  cmp     byte ptr [r15+49h], 0
0x180047998  jz      short loc_1800479F3
0x18004799a  test    rsi, rsi
0x18004799d  jz      short loc_1800479F3
0x18004799f  mov     r8d, [rsi+60h]
0x1800479a3  mov     rdx, rsi
0x1800479a6  sub     r8d, 40h ; '@'
0x1800479aa  mov     rcx, rdi
0x1800479ad  call    IpTlsLimitedBroadcastPacket
0x1800479b2  test    al, al
0x1800479b4  jnz     short loc_1800479BF
0x1800479b6  add     dword ptr [rsi+60h], 0FFFFFFC0h
0x1800479ba  mov     byte ptr [r15+48h], 1
0x1800479bf  mov     eax, [rsi+60h]
0x1800479c2  add     eax, 40h ; '@'
0x1800479c5  cmp     eax, 8000h
0x1800479ca  jbe     short loc_1800479F3
0x1800479cc  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800479d3  mov     dword ptr [rsp+140h+var_120], 14A2h
0x1800479db  mov     r8, rsi
0x1800479de  mov     rdx, r12
0x1800479e1  mov     ecx, r13d
0x1800479e4  call    EventWrite0
0x1800479e9  mov     rcx, rsi
0x1800479ec  call    IpTlsDereferenceBufferEx
0x1800479f1  xor     esi, esi
0x1800479f3  dec     byte ptr [r15+48h]
0x1800479f7  lea     r15, [rdi+0F0h]
0x1800479fe  mov     rcx, r15; lpCriticalSection
0x180047a01  call    cs:__imp_EnterCriticalSection
0x180047a08  nop     dword ptr [rax+rax+00h]
0x180047a0d  jmp     loc_1800476D4
0x180047a12  mov     ecx, 3
0x180047a17  int     29h; Win8: RtlFailFast(ecx)
0x180047a19  test    rbx, rbx
0x180047a1c  jz      short loc_180047A63
0x180047a1e  mov     r9d, [rbx+60h]
0x180047a22  xor     r8d, r8d
0x180047a25  mov     byte ptr [rsp+140h+var_118], 0
0x180047a2a  mov     rdx, rbx
0x180047a2d  mov     rcx, rdi
0x180047a30  mov     [rsp+140h+var_120], 0
0x180047a39  call    BroadcastBufferOnInterface
0x180047a3e  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180047a45  mov     dword ptr [rsp+140h+var_120], 14DBh
0x180047a4d  mov     r8, rbx
0x180047a50  mov     rdx, r12
0x180047a53  mov     ecx, r13d
0x180047a56  call    EventWrite0
0x180047a5b  mov     rcx, rbx
0x180047a5e  call    IpTlsDereferenceBufferEx
0x180047a63  test    rsi, rsi
  ... truncated ...
```
