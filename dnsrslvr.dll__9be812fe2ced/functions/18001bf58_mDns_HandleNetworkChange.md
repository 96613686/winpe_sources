# mDns_HandleNetworkChange

- ea: `0x18001bf58`
- end: `0x18001c3a7`
- name: `mDns_HandleNetworkChange`
- size: `1103`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, service_task`

## callers

- `0x18002d5b0`
- `0x180052250`

## callees

- `0x180018118`
- `0x18001bc60`
- `0x18001bf58`
- `0x18001c3b0`
- `0x18001c4bc`
- `0x18001cd24`
- `0x18001dd0c`
- `0x18002ec28`
- `0x1800311d8`
- `0x1800340bc`
- `0x18003e1d4`
- `0x180046a70`
- `0x180046ec0`
- `0x18004b858`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `DNSAPI!NetInfo_CreatePerNetworkNetinfo` at `0x18001c1b5`
- `DNSAPI!NetInfo_CreatePerNetworkNetinfo` at `0x18001c1b5`
- `DNSAPI!NetInfo_Free` at `0x18001c354`
- `DNSAPI!NetInfo_Free` at `0x18001c362`
- `DNSAPI!NetInfo_Free` at `0x18001c354`
- `DNSAPI!NetInfo_Free` at `0x18001c362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0d3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001c0c1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001c0c1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001c33d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001c33d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001c068`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001c068`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c032`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c101`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c262`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c2d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c34a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c032`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c101`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c262`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c2d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c34a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bfb6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bfe1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c151`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c2aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bfb6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bfe1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c151`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c2aa`

## pseudocode

```c
__int64 __fastcall mDns_HandleNetworkChange(unsigned int a1)
{
  QueryTable *p_OwningThread; // rcx
  char v2; // al
  char *v3; // rax
  struct _RTL_CRITICAL_SECTION *v4; // rax
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  DWORD LastError; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  struct _RTL_CRITICAL_SECTION *v9; // rcx
  QueryTable *v10; // rcx
  char v11; // al
  unsigned int v12; // eax
  __int64 v13; // rdx
  struct _DnsNetInfo *v14; // rdx
  char v15; // al
  __int64 v17; // [rsp+20h] [rbp-28h] BYREF
  __int64 v18; // [rsp+28h] [rbp-20h] BYREF

  v17 = 0;
  v18 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 11, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids, a1);
  EnterCriticalSection(&g_mDnsNetworkChangeLock);
  MDnsProbeAnnounceTask::Abort();
  mDns_DestroyNetworkConfig();
  v2 = g_InitPhase;
  if ( (g_InitPhase & 1) == 0 )
  {
    EnterCriticalSection(&g_csMdnsTree);
    v3 = (char *)operator new(0x58u);
    if ( !v3 )
    {
      g_MDnsTree = 0;
      v7 = 14;
      v9 = &g_csMdnsTree;
LABEL_16:
      LeaveCriticalSection(v9);
      goto LABEL_56;
    }
    *(_QWORD *)v3 = 0;
    *(_QWORD *)(v3 + 76) = 0;
    *((_QWORD *)v3 + 1) = 0;
    *((_QWORD *)v3 + 2) = 0;
    *((_QWORD *)v3 + 3) = 0;
    *((_QWORD *)v3 + 4) = 0;
    *((_QWORD *)v3 + 5) = 0;
    *((_QWORD *)v3 + 6) = 0;
    *((_DWORD *)v3 + 21) = 0;
    *((_DWORD *)v3 + 14) = 0;
    *(_OWORD *)(v3 + 60) = 0;
    g_MDnsTree = (MDnsTree *)v3;
    LeaveCriticalSection(&g_csMdnsTree);
    v2 = g_InitPhase | 1;
    g_InitPhase |= 1u;
  }
  if ( (v2 & 2) == 0 )
  {
    v4 = (struct _RTL_CRITICAL_SECTION *)operator new(0x50u);
    v5 = v4;
    if ( !v4 )
    {
      g_QueryTable = 0;
      v7 = 14;
      goto LABEL_56;
    }
    InitializeCriticalSection(v4 + 1);
    *(_QWORD *)&v5->LockCount = v5;
    p_OwningThread = (QueryTable *)&v5->OwningThread;
    v5->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v5;
    v5->LockSemaphore = &v5->OwningThread;
    v5->OwningThread = &v5->OwningThread;
    v5->SpinCount = 0;
    g_InitPhase |= 2u;
    g_QueryTable = (QueryTable *)v5;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_(1035, 12, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids);
    v2 = g_InitPhase;
  }
  if ( (v2 & 4) == 0 )
  {
    g_mdnsResponderStop = CreateEventW(0, 1, 0, 0);
    if ( !g_mdnsResponderStop )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_56;
      v8 = 13;
LABEL_55:
      WPP_SF_d(1035, v8, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids, LastError);
      goto LABEL_56;
    }
    g_InitPhase |= 4u;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 14, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids);
  QueryTable::ClearCache(p_OwningThread, 0);
  QueryTable::Reset(v10);
  EnterCriticalSection(&g_MdnsNetInfoLock);
  v11 = g_InitPhase;
  if ( (g_InitPhase & 0x10) != 0 )
  {
    v14 = g_pMdnsNetInfo;
  }
  else
  {
    if ( g_fVelocityNetinfoCleanup )
    {
      v12 = GrabNetworkInfo(0, &v17, 0);
      v7 = v12;
      if ( v12 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        {
          v13 = 15;
LABEL_49:
          WPP_SF_d(1035, v13, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids, v12);
          goto LABEL_50;
        }
        goto LABEL_50;
      }
    }
    else
    {
      v12 = GrabNetworkInfoOld(0, 1, &v17, 0);
      v7 = v12;
      if ( v12 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        {
          v13 = 16;
          goto LABEL_49;
        }
        goto LABEL_50;
      }
    }
    v12 = NetInfo_CreatePerNetworkNetinfo(v17, &v18);
    v7 = v12;
    if ( v12 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      {
        v13 = 17;
        goto LABEL_49;
      }
LABEL_50:
      v9 = &g_MdnsNetInfoLock;
      goto LABEL_16;
    }
    *(_DWORD *)(v18 + 48) = *(_DWORD *)(v17 + 48);
    v14 = (struct _DnsNetInfo *)v17;
    g_pMdnsPerNetworkInfo = (struct _DnsNetInfo *)v18;
    v11 = g_InitPhase | 0x10;
    g_pMdnsNetInfo = (struct _DnsNetInfo *)v17;
    g_InitPhase |= 0x10u;
    v17 = 0;
    v18 = 0;
  }
  if ( (v11 & 0x20) == 0 )
  {
    v12 = Mcast_Build(&g_pMdnsInfo, v14, 1);
    v7 = v12;
    if ( v12 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      {
        v13 = 18;
        goto LABEL_49;
      }
      goto LABEL_50;
    }
    g_InitPhase |= 0x20u;
  }
  LeaveCriticalSection(&g_MdnsNetInfoLock);
  LastError = InitGlobalInterfaceTable();
  v7 = LastError;
  if ( LastError )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_56;
    v8 = 19;
    goto LABEL_55;
  }
  v15 = g_InitPhase;
  if ( (g_InitPhase & 8) == 0 )
  {
    LastError = mDns_CreateResponderThread();
    v7 = LastError;
    if ( LastError )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_56;
      v8 = 20;
      goto LABEL_55;
    }
    v15 = g_InitPhase | 8;
    g_InitPhase |= 8u;
  }
  if ( (v15 & 1) != 0 )
  {
    EnterCriticalSection(&g_csMdnsTree);
    if ( g_MDnsTree && (*((_QWORD *)g_MDnsTree + 5) || *((_QWORD *)g_MDnsTree + 2)) )
      MDnsTree::ReassignNetworkIndices(g_MDnsTree);
    LeaveCriticalSection(&g_csMdnsTree);
    MDnsProbeAnnounceTask::Start();
  }
LABEL_56:
  if ( g_hMDnsInitDoneEvent )
    SetEvent(g_hMDnsInitDoneEvent);
  LeaveCriticalSection(&g_mDnsNetworkChangeLock);
  NetInfo_Free(v17);
  v17 = 0;
  NetInfo_Free(v18);
  v18 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 21, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18001bf58  push    rbp
0x18001bf5a  push    rbx
0x18001bf5b  push    rsi
0x18001bf5c  push    rdi
0x18001bf5d  push    r12
0x18001bf5f  push    r13
0x18001bf61  push    r14
0x18001bf63  push    r15
0x18001bf65  mov     rbp, rsp
0x18001bf68  sub     rsp, 48h
0x18001bf6c  mov     rax, cs:__security_cookie
0x18001bf73  xor     rax, rsp
0x18001bf76  mov     [rbp+var_18], rax
0x18001bf7a  xor     edi, edi
0x18001bf7c  mov     r9d, ecx
0x18001bf7f  mov     [rbp+var_28], rdi
0x18001bf83  mov     [rbp+var_20], rdi
0x18001bf87  mov     si, 8
0x18001bf8b  lea     r15, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids
0x18001bf92  test    byte ptr cs:xmmword_1800AB5A0+1, sil
0x18001bf99  mov     r14d, 40Bh
0x18001bf9f  jz      short loc_18001BFAF
0x18001bfa1  lea     edx, [rdi+0Bh]
0x18001bfa4  mov     ecx, r14d
0x18001bfa7  mov     r8, r15
0x18001bfaa  call    WPP_SF_d
0x18001bfaf  lea     rcx, ?g_mDnsNetworkChangeLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001bfb6  call    cs:__imp_EnterCriticalSection
0x18001bfbc  call    ?Abort@MDnsProbeAnnounceTask@@SAXXZ; MDnsProbeAnnounceTask::Abort(void)
0x18001bfc1  call    mDns_DestroyNetworkConfig
0x18001bfc6  mov     al, byte ptr cs:?g_InitPhase@@3TMDNS_INIT_PHASE@@A; MDNS_INIT_PHASE g_InitPhase
0x18001bfcc  lea     r13, ?g_csMdnsTree@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csMdnsTree
0x18001bfd3  mov     r12d, 1
0x18001bfd9  test    r12b, al
0x18001bfdc  jnz     short loc_18001C04A
0x18001bfde  mov     rcx, r13; lpCriticalSection
0x18001bfe1  call    cs:__imp_EnterCriticalSection
0x18001bfe7  lea     ecx, [r12+57h]; Size
0x18001bfec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bff1  test    rax, rax
0x18001bff4  jz      loc_18001C0F2
0x18001bffa  xor     ecx, ecx
0x18001bffc  mov     [rax], rdi
0x18001bfff  mov     [rax+4Ch], rcx
0x18001c003  xorps   xmm0, xmm0
0x18001c006  mov     [rax+8], rdi
0x18001c00a  mov     rcx, r13; lpCriticalSection
0x18001c00d  mov     [rax+10h], rdi
0x18001c011  mov     [rax+18h], rdi
0x18001c015  mov     [rax+20h], rdi
0x18001c019  mov     [rax+28h], rdi
0x18001c01d  mov     [rax+30h], rdi
0x18001c021  mov     [rax+54h], edi
0x18001c024  mov     [rax+38h], edi
0x18001c027  movups  xmmword ptr [rax+3Ch], xmm0
0x18001c02b  mov     cs:?g_MDnsTree@@3PEAVMDnsTree@@EA, rax; MDnsTree * g_MDnsTree
0x18001c032  call    cs:__imp_LeaveCriticalSection
0x18001c038  movzx   eax, cs:?g_InitPhase@@3TMDNS_INIT_PHASE@@A; MDNS_INIT_PHASE g_InitPhase
0x18001c03f  or      ax, r12w
0x18001c043  mov     cs:?g_InitPhase@@3TMDNS_INIT_PHASE@@A, ax; MDNS_INIT_PHASE g_InitPhase
0x18001c04a  test    al, 2
0x18001c04c  jnz     short loc_18001C0B2
0x18001c04e  mov     ecx, 50h ; 'P'; Size
0x18001c053  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c058  mov     rbx, rax
0x18001c05b  test    rax, rax
0x18001c05e  jz      loc_18001C10C
0x18001c064  lea     rcx, [rax+28h]; lpCriticalSection
0x18001c068  call    cs:__imp_InitializeCriticalSection
0x18001c06e  mov     [rbx+8], rbx
0x18001c072  lea     rcx, [rbx+10h]
0x18001c076  mov     [rbx], rbx
0x18001c079  mov     [rcx+8], rcx
0x18001c07d  mov     [rcx], rcx
0x18001c080  mov     [rbx+20h], rdi
0x18001c084  or      cs:?g_InitPhase@@3TMDNS_INIT_PHASE@@A, 2; MDNS_INIT_PHASE g_InitPhase
0x18001c08c  mov     cs:?g_QueryTable@@3PEAVQueryTable@@EA, rbx; QueryTable * g_QueryTable
0x18001c093  test    byte ptr cs:xmmword_1800AB5A0+1, sil
0x18001c09a  jz      short loc_18001C0AC
0x18001c09c  mov     edx, 0Ch
0x18001c0a1  mov     ecx, r14d
0x18001c0a4  mov     r8, r15
0x18001c0a7  call    WPP_SF_
0x18001c0ac  mov     al, byte ptr cs:?g_InitPhase@@3TMDNS_INIT_PHASE@@A; MDNS_INIT_PHASE g_InitPhase
0x18001c0b2  test    al, 4
0x18001c0b4  jnz     short loc_18001C125
0x18001c0b6  xor     r9d, r9d; lpName
0x18001c0b9  xor     r8d, r8d; bInitialState
0x18001c0bc  mov     edx, r12d; bManualReset
0x18001c0bf  xor     ecx, ecx; lpEventAttributes
0x18001c0c1  call    cs:__imp_CreateEventW
0x18001c0c7  mov     cs:?g_mdnsResponderStop@@3PEAXEA, rax; void * g_mdnsResponderStop
0x18001c0ce  test    rax, rax
0x18001c0d1  jnz     short loc_18001C11D
0x18001c0d3  call    cs:__imp_GetLastError
0x18001c0d9  mov     ebx, eax
0x18001c0db  test    byte ptr cs:xmmword_1800AB5A0+1, sil
0x18001c0e2  jz      loc_18001C331
0x18001c0e8  mov     edx, 0Dh
0x18001c0ed  jmp     loc_18001C323
0x18001c0f2  mov     cs:?g_MDnsTree@@3PEAVMDnsTree@@EA, rdi; MDnsTree * g_MDnsTree
0x18001c0f9  mov     ebx, 0Eh
0x18001c0fe  mov     rcx, r13; lpCriticalSection
0x18001c101  call    cs:__imp_LeaveCriticalSection
0x18001c107  jmp     loc_18001C331
0x18001c10c  mov     cs:?g_QueryTable@@3PEAVQueryTable@@EA, rdi; QueryTable * g_QueryTable
0x18001c113  mov     ebx, 0Eh
0x18001c118  jmp     loc_18001C331
0x18001c11d  or      cs:?g_InitPhase@@3TMDNS_INIT_PHASE@@A, 4; MDNS_INIT_PHASE g_InitPhase
0x18001c125  test    byte ptr cs:xmmword_1800AB5A0+1, sil
0x18001c12c  jz      short loc_18001C13E
0x18001c12e  mov     edx, 0Eh
0x18001c133  mov     ecx, r14d
0x18001c136  mov     r8, r15
0x18001c139  call    WPP_SF_
0x18001c13e  xor     edx, edx; int
0x18001c140  call    ?ClearCache@QueryTable@@QEAAXH@Z; QueryTable::ClearCache(int)
0x18001c145  call    ?Reset@QueryTable@@QEAAXXZ; QueryTable::Reset(void)
0x18001c14a  lea     rcx, ?g_MdnsNetInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001c151  call    cs:__imp_EnterCriticalSection
0x18001c157  mov     al, byte ptr cs:?g_InitPhase@@3TMDNS_INIT_PHASE@@A; MDNS_INIT_PHASE g_InitPhase
0x18001c15d  test    al, 10h
0x18001c15f  jnz     loc_18001C22F
0x18001c165  xor     ecx, ecx
0x18001c167  cmp     cs:g_fVelocityNetinfoCleanup, edi
0x18001c16d  jz      short loc_18001C198
0x18001c16f  xor     r8d, r8d
0x18001c172  lea     rdx, [rbp+var_28]
0x18001c176  call    GrabNetworkInfo
0x18001c17b  mov     ebx, eax
0x18001c17d  test    eax, eax
0x18001c17f  jz      short loc_18001C1AD
0x18001c181  test    byte ptr cs:xmmword_1800AB5A0+1, sil
0x18001c188  jz      loc_18001C2F9
0x18001c18e  mov     edx, 0Fh
0x18001c193  jmp     loc_18001C2EB
0x18001c198  xor     r9d, r9d
0x18001c19b  lea     r8, [rbp+var_28]
0x18001c19f  mov     edx, r12d
0x18001c1a2  call    GrabNetworkInfoOld
0x18001c1a7  mov     ebx, eax
0x18001c1a9  test    eax, eax
0x18001c1ab  jnz     short loc_18001C218
0x18001c1ad  mov     rcx, [rbp+var_28]
0x18001c1b1  lea     rdx, [rbp+var_20]
0x18001c1b5  call    cs:__imp_NetInfo_CreatePerNetworkNetinfo
0x18001c1bb  mov     ebx, eax
0x18001c1bd  test    eax, eax
0x18001c1bf  jnz     short loc_18001C201
0x18001c1c1  mov     rax, [rbp+var_28]
0x18001c1c5  mov     ecx, [rax+30h]
0x18001c1c8  mov     rax, [rbp+var_20]
0x18001c1cc  mov     [rax+30h], ecx
0x18001c1cf  mov     rax, [rbp+var_20]
0x18001c1d3  mov     rdx, [rbp+var_28]
0x18001c1d7  mov     cs:?g_pMdnsPerNetworkInfo@@3PEAU_DnsNetInfo@@EA, rax; _DnsNetInfo * g_pMdnsPerNetworkInfo
0x18001c1de  movzx   eax, cs:?g_InitPhase@@3TMDNS_INIT_PHASE@@A; MDNS_INIT_PHASE g_InitPhase
0x18001c1e5  or      ax, 10h
0x18001c1e9  mov     cs:?g_pMdnsNetInfo@@3PEAU_DnsNetInfo@@EA, rdx; _DnsNetInfo * g_pMdnsNetInfo
0x18001c1f0  mov     cs:?g_InitPhase@@3TMDNS_INIT_PHASE@@A, ax; MDNS_INIT_PHASE g_InitPhase
0x18001c1f7  mov     [rbp+var_28], rdi
0x18001c1fb  mov     [rbp+var_20], rdi
0x18001c1ff  jmp     short loc_18001C236
0x18001c201  test    byte ptr cs:xmmword_1800AB5A0+1, sil
0x18001c208  jz      loc_18001C2F9
0x18001c20e  mov     edx, 11h
0x18001c213  jmp     loc_18001C2EB
0x18001c218  test    byte ptr cs:xmmword_1800AB5A0+1, sil
0x18001c21f  jz      loc_18001C2F9
0x18001c225  mov     edx, 10h
0x18001c22a  jmp     loc_18001C2EB
0x18001c22f  mov     rdx, cs:?g_pMdnsNetInfo@@3PEAU_DnsNetInfo@@EA; _DnsNetInfo * g_pMdnsNetInfo
0x18001c236  test    al, 20h
0x18001c238  jnz     short loc_18001C25B
0x18001c23a  mov     r8d, r12d
0x18001c23d  lea     rcx, ?g_pMdnsInfo@@3PEAU_McastInfo@@EA; _McastInfo * g_pMdnsInfo
0x18001c244  call    Mcast_Build
0x18001c249  mov     ebx, eax
0x18001c24b  test    eax, eax
0x18001c24d  jnz     loc_18001C2DD
0x18001c253  or      cs:?g_InitPhase@@3TMDNS_INIT_PHASE@@A, 20h; MDNS_INIT_PHASE g_InitPhase
0x18001c25b  lea     rcx, ?g_MdnsNetInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001c262  call    cs:__imp_LeaveCriticalSection
0x18001c268  call    ?InitGlobalInterfaceTable@@YAKXZ; InitGlobalInterfaceTable(void)
0x18001c26d  mov     ebx, eax
0x18001c26f  test    eax, eax
0x18001c271  jnz     loc_18001C315
0x18001c277  mov     al, byte ptr cs:?g_InitPhase@@3TMDNS_INIT_PHASE@@A; MDNS_INIT_PHASE g_InitPhase
0x18001c27d  test    sil, al
0x18001c280  jnz     short loc_18001C29E
0x18001c282  call    mDns_CreateResponderThread
0x18001c287  mov     ebx, eax
0x18001c289  test    eax, eax
0x18001c28b  jnz     short loc_18001C305
0x18001c28d  movzx   eax, cs:?g_InitPhase@@3TMDNS_INIT_PHASE@@A; MDNS_INIT_PHASE g_InitPhase
0x18001c294  or      ax, si
0x18001c297  mov     cs:?g_InitPhase@@3TMDNS_INIT_PHASE@@A, ax; MDNS_INIT_PHASE g_InitPhase
0x18001c29e  test    r12b, al
0x18001c2a1  jz      loc_18001C331
0x18001c2a7  mov     rcx, r13; lpCriticalSection
0x18001c2aa  call    cs:__imp_EnterCriticalSection
0x18001c2b0  mov     rcx, cs:?g_MDnsTree@@3PEAVMDnsTree@@EA; this
0x18001c2b7  test    rcx, rcx
0x18001c2ba  jz      short loc_18001C2CD
0x18001c2bc  cmp     [rcx+28h], rdi
0x18001c2c0  jnz     short loc_18001C2C8
0x18001c2c2  cmp     [rcx+10h], rdi
0x18001c2c6  jz      short loc_18001C2CD
0x18001c2c8  call    ?ReassignNetworkIndices@MDnsTree@@QEAAXXZ; MDnsTree::ReassignNetworkIndices(void)
0x18001c2cd  mov     rcx, r13; lpCriticalSection
0x18001c2d0  call    cs:__imp_LeaveCriticalSection
0x18001c2d6  call    ?Start@MDnsProbeAnnounceTask@@SAXXZ; MDnsProbeAnnounceTask::Start(void)
0x18001c2db  jmp     short loc_18001C331
0x18001c2dd  test    byte ptr cs:xmmword_1800AB5A0+1, sil
0x18001c2e4  jz      short loc_18001C2F9
0x18001c2e6  mov     edx, 12h
0x18001c2eb  mov     r9d, eax
0x18001c2ee  mov     r8, r15
0x18001c2f1  mov     ecx, r14d
0x18001c2f4  call    WPP_SF_d
0x18001c2f9  lea     rcx, ?g_MdnsNetInfoLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_MdnsNetInfoLock
0x18001c300  jmp     loc_18001C101
0x18001c305  test    byte ptr cs:xmmword_1800AB5A0+1, sil
0x18001c30c  jz      short loc_18001C331
0x18001c30e  mov     edx, 14h
0x18001c313  jmp     short loc_18001C323
0x18001c315  test    byte ptr cs:xmmword_1800AB5A0+1, sil
0x18001c31c  jz      short loc_18001C331
0x18001c31e  mov     edx, 13h
0x18001c323  mov     r9d, eax
0x18001c326  mov     r8, r15
0x18001c329  mov     ecx, r14d
0x18001c32c  call    WPP_SF_d
0x18001c331  mov     rcx, cs:?g_hMDnsInitDoneEvent@@3PEAXEA; hEvent
0x18001c338  test    rcx, rcx
0x18001c33b  jz      short loc_18001C343
0x18001c33d  call    cs:__imp_SetEvent
0x18001c343  lea     rcx, ?g_mDnsNetworkChangeLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001c34a  call    cs:__imp_LeaveCriticalSection
0x18001c350  mov     rcx, [rbp+var_28]
0x18001c354  call    cs:__imp_NetInfo_Free
0x18001c35a  mov     rcx, [rbp+var_20]
0x18001c35e  mov     [rbp+var_28], rdi
0x18001c362  call    cs:__imp_NetInfo_Free
0x18001c368  mov     [rbp+var_20], rdi
0x18001c36c  test    byte ptr cs:xmmword_1800AB5A0+1, sil
0x18001c373  jz      short loc_18001C388
0x18001c375  mov     edx, 15h
0x18001c37a  mov     ecx, r14d
0x18001c37d  mov     r9d, ebx
0x18001c380  mov     r8, r15
0x18001c383  call    WPP_SF_d
0x18001c388  mov     eax, ebx
0x18001c38a  mov     rcx, [rbp+var_18]
0x18001c38e  xor     rcx, rsp; StackCookie
0x18001c391  call    __security_check_cookie
0x18001c396  add     rsp, 48h
0x18001c39a  pop     r15
0x18001c39c  pop     r14
0x18001c39e  pop     r13
0x18001c3a0  pop     r12
0x18001c3a2  pop     rdi
0x18001c3a3  pop     rsi
0x18001c3a4  pop     rbx
0x18001c3a5  pop     rbp
0x18001c3a6  retn
```
