# CertPropInitializeSession

- ea: `0x180002690`
- end: `0x180002a8d`
- name: `CertPropInitializeSession`
- size: `1021`
- prototype: `__int64 __fastcall(__int64 SessionId, LPVOID **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800061c0`

## callees

- `0x1800010c4`
- `0x1800013d0`
- `0x1800023b8`
- `0x180002690`
- `0x180004600`
- `0x180018bb4`
- `0x180018d78`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18000290a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18000290a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180002949`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180002949`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000275e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000275e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002960`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002960`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002a10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002a10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002706`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002706`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180002979`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180002979`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180002872`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180002872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002845`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002845`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000285f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000285f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000283b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000283b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002a1b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002a1b`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x1800027ae`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x1800027ae`
- `WTSAPI32!WTSQueryUserToken` at `0x1800027f6`
- `WTSAPI32!WTSQueryUserToken` at `0x1800027f6`
- `WTSAPI32!WTSFreeMemory` at `0x180002a2b`
- `WTSAPI32!WTSFreeMemory` at `0x180002a2b`

## pseudocode

```c
__int64 __fastcall CertPropInitializeSession(__int64 SessionId, LPVOID **a2)
{
  DWORD v3; // r15d
  int v4; // esi
  int v5; // r9d
  LPVOID *v6; // rdi
  DWORD LastError; // ebx
  _DWORD *v8; // rax
  LPVOID *v9; // rax
  HANDLE *v10; // r15
  __int64 v11; // rdx
  __int64 v12; // rcx
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  HANDLE EventW; // rax
  DWORD v15; // eax
  LPWSTR v16; // rcx
  LPWSTR ppBuffer[7]; // [rsp+30h] [rbp-38h] BYREF
  DWORD pBytesReturned; // [rsp+80h] [rbp+18h] BYREF
  void *phToken; // [rsp+88h] [rbp+20h] BYREF

  v3 = SessionId;
  v4 = 0;
  ppBuffer[0] = 0;
  pBytesReturned = 0;
  WppTraceIndent(SessionId, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
      v5,
      v3);
  }
  EnterCriticalSection(&g_csSessionList);
  if ( !g_fShutdownInProgress )
  {
    v8 = g_pSessionList;
    if ( g_pSessionList )
    {
      do
      {
        if ( v3 == v8[2] )
          break;
        v8 = *(_DWORD **)v8;
      }
      while ( v8 );
      if ( v8 )
      {
        LastError = 183;
        goto LABEL_40;
      }
    }
    LastError = 8;
    v9 = (LPVOID *)HeapAlloc(g_hHeap, 8u, 0x270u);
    v6 = v9;
    ppBuffer[1] = (LPWSTR)v9;
    if ( !v9 )
      goto LABEL_38;
    *v9 = g_pSessionList;
    g_pSessionList = v9;
    *((_DWORD *)v9 + 2) = v3;
    *((_DWORD *)v9 + 154) = 0;
    if ( WTSQuerySessionInformationW(0, v3, WTSIsRemoteSession, ppBuffer, &pBytesReturned)
      && ppBuffer[0]
      && pBytesReturned == 1 )
    {
      *((_DWORD *)v6 + 154) = *(_BYTE *)ppBuffer[0] != 0;
    }
    if ( a2 )
      *a2 = v6;
    phToken = 0;
    if ( WTSQueryUserToken(v3, &phToken) )
    {
      v10 = v6 + 52;
      if ( DuplicateTokenEx(phToken, 0xEu, 0, SecurityImpersonation, TokenImpersonation, v6 + 52) )
        LastError = 0;
      else
        LastError = GetLastError();
    }
    else
    {
      LastError = GetLastError();
      v10 = v6 + 52;
    }
    if ( phToken )
      CloseHandle(phToken);
    if ( LastError )
    {
LABEL_37:
      if ( LastError == 183 )
        goto LABEL_40;
      goto LABEL_38;
    }
    if ( !SetThreadToken(0, *v10) )
      goto LABEL_34;
    v4 = 1;
    LODWORD(phToken) = 1;
    if ( g_fEnableRootCertProp == 1 )
    {
      *((_DWORD *)v6 + 142) = 1;
      *((_DWORD *)v6 + 143) = g_RootsCleanupOption;
    }
    LastError = RootInfoGetLuidAndSID(v12, v11, *v10, v6 + 74, v6 + 75);
    if ( LastError )
    {
LABEL_36:
      if ( !LastError )
        goto LABEL_40;
      goto LABEL_37;
    }
    *((_DWORD *)v6 + 141) = 1;
    *((_DWORD *)v6 + 106) = 3;
    v6[54] = 0;
    v6[55] = 0;
    v6[56] = 0;
    v6[57] = 0;
    v6[58] = 0;
    v6[59] = 0;
    *((_DWORD *)v6 + 120) = 0;
    *((_DWORD *)v6 + 121) = 1;
    *((_DWORD *)v6 + 122) = 72;
    *((_DWORD *)v6 + 124) = 1;
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    v6[63] = ThreadpoolCleanupGroup;
    if ( !ThreadpoolCleanupGroup )
      goto LABEL_34;
    v6[55] = ThreadpoolCleanupGroup;
    v6[56] = 0;
    v6[57] = (LPVOID)g_hInst;
    v6[76] = CreateThreadpoolWork(
               CertPropAssociateSmartCardUserWithCertificateCallback,
               v6,
               (PTP_CALLBACK_ENVIRON)(v6 + 53));
    EventW = CreateEventW(0, 1, 0, 0);
    v6[64] = EventW;
    if ( EventW )
    {
      InitializeCriticalSection((LPCRITICAL_SECTION)v6 + 13);
      *((_DWORD *)v6 + 140) = 1;
      *((_DWORD *)v6 + 8) = 1;
      *((_DWORD *)v6 + 7) = g_fEnableRootCertProp;
      *((_DWORD *)v6 + 11) = 1;
      *((_DWORD *)v6 + 10) = 1;
      *((_DWORD *)v6 + 9) = 1;
      *((_DWORD *)v6 + 12) = 2;
      *((_DWORD *)v6 + 13) = 1;
      *((_DWORD *)v6 + 6) = 1;
      v6[7] = g_hHeap;
      *((_DWORD *)v6 + 16) = 2;
      v15 = ReaderMonitorInitialize();
    }
    else
    {
LABEL_34:
      v15 = GetLastError();
    }
    LastError = v15;
    goto LABEL_36;
  }
  v6 = 0;
  LastError = 1115;
LABEL_38:
  if ( v6 )
  {
    g_pSessionList = *v6;
    CertPropFreeListNode(v6);
  }
LABEL_40:
  LeaveCriticalSection(&g_csSessionList);
  if ( v4 == 1 )
    RevertToSelf();
  v16 = ppBuffer[0];
  if ( ppBuffer[0] )
    WTSFreeMemory(ppBuffer[0]);
  WppTraceIndent(v16, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
      WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180002690  mov     rax, rsp
0x180002693  mov     [rax+8], rbx
0x180002697  mov     [rax+10h], rsi
0x18000269b  push    rdi
0x18000269c  push    r12
0x18000269e  push    r13
0x1800026a0  push    r14
0x1800026a2  push    r15
0x1800026a4  sub     rsp, 40h
0x1800026a8  mov     r12, rdx
0x1800026ab  mov     r15d, ecx
0x1800026ae  xor     r13d, r13d
0x1800026b1  mov     esi, r13d
0x1800026b4  mov     [rax-38h], r13
0x1800026b8  mov     [rax+18h], r13d
0x1800026bc  mov     edx, 2
0x1800026c1  call    WppTraceIndent
0x1800026c6  lea     r14, WPP_GLOBAL_Control
0x1800026cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026d4  cmp     rcx, r14
0x1800026d7  jz      short loc_1800026FF
0x1800026d9  test    byte ptr [rcx+1Ch], 1
0x1800026dd  jz      short loc_1800026FF
0x1800026df  cmp     byte ptr [rcx+19h], 4
0x1800026e3  jb      short loc_1800026FF
0x1800026e5  mov     edx, 27h ; '''
0x1800026ea  mov     dword ptr [rsp+68h+pBytesReturned], r15d
0x1800026ef  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x1800026f6  mov     rcx, [rcx+10h]
0x1800026fa  call    WPP_SF_sd
0x1800026ff  lea     rcx, g_csSessionList; lpCriticalSection
0x180002706  call    cs:__imp_EnterCriticalSection
0x18000270c  cmp     cs:g_fShutdownInProgress, esi
0x180002712  jz      short loc_180002721
0x180002714  mov     rdi, r13
0x180002717  mov     ebx, 45Bh
0x18000271c  jmp     loc_1800029F2
0x180002721  mov     rax, cs:g_pSessionList
0x180002728  test    rax, rax
0x18000272b  jz      short loc_18000274A
0x18000272d  cmp     r15d, [rax+8]
0x180002731  jz      short loc_18000273B
0x180002733  mov     rax, [rax]
0x180002736  test    rax, rax
0x180002739  jnz     short loc_18000272D
0x18000273b  test    rax, rax
0x18000273e  jz      short loc_18000274A
0x180002740  mov     ebx, 0B7h
0x180002745  jmp     loc_180002A09
0x18000274a  mov     ebx, 8
0x18000274f  mov     r8d, 270h; dwBytes
0x180002755  mov     edx, ebx; dwFlags
0x180002757  mov     rcx, cs:g_hHeap; hHeap
0x18000275e  call    cs:__imp_HeapAlloc
0x180002764  mov     rdi, rax
0x180002767  mov     [rsp+68h+var_30], rax
0x18000276c  test    rax, rax
0x18000276f  jz      loc_1800029F2
0x180002775  mov     rax, cs:g_pSessionList
0x18000277c  mov     [rdi], rax
0x18000277f  mov     cs:g_pSessionList, rdi
0x180002786  mov     [rdi+8], r15d
0x18000278a  mov     [rdi+268h], r13d
0x180002791  lea     rax, [rsp+68h+arg_10]
0x180002799  mov     [rsp+68h+pBytesReturned], rax; pBytesReturned
0x18000279e  lea     r9, [rsp+68h+ppBuffer]; ppBuffer
0x1800027a3  mov     r8d, 1Dh; WTSInfoClass
0x1800027a9  mov     edx, r15d; SessionId
0x1800027ac  xor     ecx, ecx; hServer
0x1800027ae  call    cs:__imp_WTSQuerySessionInformationW
0x1800027b4  test    eax, eax
0x1800027b6  jz      short loc_1800027DA
0x1800027b8  mov     rcx, [rsp+68h+ppBuffer]
0x1800027bd  test    rcx, rcx
0x1800027c0  jz      short loc_1800027DA
0x1800027c2  cmp     [rsp+68h+arg_10], 1
0x1800027ca  jnz     short loc_1800027DA
0x1800027cc  mov     eax, r13d
0x1800027cf  cmp     [rcx], al
0x1800027d1  setnz   al
0x1800027d4  mov     [rdi+268h], eax
0x1800027da  test    r12, r12
0x1800027dd  jz      short loc_1800027E3
0x1800027df  mov     [r12], rdi
0x1800027e3  mov     [rsp+68h+phToken], r13
0x1800027eb  lea     rdx, [rsp+68h+phToken]; phToken
0x1800027f3  mov     ecx, r15d; SessionId
0x1800027f6  call    cs:__imp_WTSQueryUserToken
0x1800027fc  test    eax, eax
0x1800027fe  jnz     short loc_180002811
0x180002800  call    cs:__imp_GetLastError
0x180002806  mov     ebx, eax
0x180002808  lea     r15, [rdi+1A0h]
0x18000280f  jmp     short loc_180002852
0x180002811  lea     r15, [rdi+1A0h]
0x180002818  mov     [rsp+68h+phNewToken], r15; phNewToken
0x18000281d  mov     dword ptr [rsp+68h+pBytesReturned], 2; TokenType
0x180002825  mov     r9d, 2; ImpersonationLevel
0x18000282b  xor     r8d, r8d; lpTokenAttributes
0x18000282e  mov     edx, 0Eh; dwDesiredAccess
0x180002833  mov     rcx, [rsp+68h+phToken]; hExistingToken
0x18000283b  call    cs:__imp_DuplicateTokenEx
0x180002841  test    eax, eax
0x180002843  jnz     short loc_18000284F
0x180002845  call    cs:__imp_GetLastError
0x18000284b  mov     ebx, eax
0x18000284d  jmp     short loc_180002852
0x18000284f  mov     ebx, r13d
0x180002852  mov     rcx, [rsp+68h+phToken]; hObject
0x18000285a  test    rcx, rcx
0x18000285d  jz      short loc_180002865
0x18000285f  call    cs:__imp_CloseHandle
0x180002865  test    ebx, ebx
0x180002867  jnz     loc_1800029EA
0x18000286d  mov     rdx, [r15]; Token
0x180002870  xor     ecx, ecx; Thread
0x180002872  call    cs:__imp_SetThreadToken
0x180002878  test    eax, eax
0x18000287a  jz      loc_1800029DE
0x180002880  mov     esi, 1
0x180002885  mov     dword ptr [rsp+68h+phToken], esi
0x18000288c  cmp     cs:g_fEnableRootCertProp, esi
0x180002892  jnz     short loc_1800028A6
0x180002894  mov     [rdi+238h], esi
0x18000289a  mov     eax, cs:g_RootsCleanupOption
0x1800028a0  mov     [rdi+23Ch], eax
0x1800028a6  lea     rax, [rdi+258h]
0x1800028ad  lea     r9, [rdi+250h]
0x1800028b4  mov     [rsp+68h+pBytesReturned], rax
0x1800028b9  mov     r8, [r15]
0x1800028bc  call    RootInfoGetLuidAndSID
0x1800028c1  mov     ebx, eax
0x1800028c3  test    eax, eax
0x1800028c5  jnz     loc_1800029E6
0x1800028cb  mov     [rdi+234h], esi
0x1800028d1  lea     rbx, [rdi+1A8h]
0x1800028d8  mov     dword ptr [rbx], 3
0x1800028de  mov     [rbx+8], r13
0x1800028e2  mov     [rbx+10h], r13
0x1800028e6  mov     [rbx+18h], r13
0x1800028ea  mov     [rbx+20h], r13
0x1800028ee  mov     [rbx+28h], r13
0x1800028f2  mov     [rbx+30h], r13
0x1800028f6  mov     [rbx+38h], r13d
0x1800028fa  mov     [rbx+3Ch], esi
0x1800028fd  mov     dword ptr [rbx+40h], 48h ; 'H'
0x180002904  mov     [rdi+1F0h], esi
0x18000290a  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180002910  mov     [rdi+1F8h], rax
0x180002917  test    rax, rax
0x18000291a  jz      loc_1800029DE
0x180002920  mov     [rdi+1B8h], rax
0x180002927  mov     [rdi+1C0h], r13
0x18000292e  mov     rax, cs:g_hInst
0x180002935  mov     [rdi+1C8h], rax
0x18000293c  mov     r8, rbx; pcbe
0x18000293f  mov     rdx, rdi; pv
0x180002942  lea     rcx, CertPropAssociateSmartCardUserWithCertificateCallback; pfnwk
0x180002949  call    cs:__imp_CreateThreadpoolWork
0x18000294f  mov     [rdi+260h], rax
0x180002956  xor     r9d, r9d; lpName
0x180002959  xor     r8d, r8d; bInitialState
0x18000295c  mov     edx, esi; bManualReset
0x18000295e  xor     ecx, ecx; lpEventAttributes
0x180002960  call    cs:__imp_CreateEventW
0x180002966  mov     [rdi+200h], rax
0x18000296d  test    rax, rax
0x180002970  jz      short loc_1800029DE
0x180002972  lea     rcx, [rdi+208h]; lpCriticalSection
0x180002979  call    cs:__imp_InitializeCriticalSection
0x18000297f  nop
0x180002980  mov     [rdi+230h], esi
0x180002986  mov     [rdi+20h], esi
0x180002989  mov     eax, cs:g_fEnableRootCertProp
0x18000298f  mov     [rdi+1Ch], eax
0x180002992  mov     [rdi+2Ch], esi
0x180002995  mov     [rdi+28h], esi
0x180002998  mov     [rdi+24h], esi
0x18000299b  mov     dword ptr [rdi+30h], 2
0x1800029a2  mov     [rdi+34h], esi
0x1800029a5  lea     rcx, [rdi+18h]
0x1800029a9  mov     [rcx], esi
0x1800029ab  mov     rax, cs:g_hHeap
0x1800029b2  mov     [rdi+38h], rax
0x1800029b6  mov     dword ptr [rdi+40h], 2
0x1800029bd  call    ReaderMonitorInitialize
0x1800029c2  jmp     short loc_1800029E4
0x1800029c4  mov     ebx, 8
0x1800029c9  lea     r14, WPP_GLOBAL_Control
0x1800029d0  mov     rdi, [rsp+68h+var_30]
0x1800029d5  mov     esi, dword ptr [rsp+68h+phToken]
0x1800029dc  jmp     short loc_1800029E6
0x1800029de  call    cs:__imp_GetLastError
0x1800029e4  mov     ebx, eax
0x1800029e6  test    ebx, ebx
0x1800029e8  jz      short loc_180002A09
0x1800029ea  cmp     ebx, 0B7h
0x1800029f0  jz      short loc_180002A09
0x1800029f2  test    rdi, rdi
0x1800029f5  jz      short loc_180002A09
0x1800029f7  mov     rax, [rdi]
0x1800029fa  mov     cs:g_pSessionList, rax
0x180002a01  mov     rcx, rdi; lpMem
0x180002a04  call    CertPropFreeListNode
0x180002a09  lea     rcx, g_csSessionList; lpCriticalSection
0x180002a10  call    cs:__imp_LeaveCriticalSection
0x180002a16  cmp     esi, 1
0x180002a19  jnz     short loc_180002A21
0x180002a1b  call    cs:__imp_RevertToSelf
0x180002a21  mov     rcx, [rsp+68h+ppBuffer]; pMemory
0x180002a26  test    rcx, rcx
0x180002a29  jz      short loc_180002A31
0x180002a2b  call    cs:__imp_WTSFreeMemory
0x180002a31  mov     edx, 2
0x180002a36  call    WppTraceIndent
0x180002a3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a42  cmp     rcx, r14
0x180002a45  jz      short loc_180002A73
0x180002a47  test    byte ptr [rcx+1Ch], 1
0x180002a4b  jz      short loc_180002A73
0x180002a4d  cmp     byte ptr [rcx+19h], 4
0x180002a51  jb      short loc_180002A73
0x180002a53  mov     edx, 28h ; '('
0x180002a58  mov     dword ptr [rsp+68h+pBytesReturned], ebx
0x180002a5c  mov     r9, cs:WPP_pszIndent
0x180002a63  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x180002a6a  mov     rcx, [rcx+10h]
0x180002a6e  call    WPP_SF_sD
0x180002a73  mov     eax, ebx
0x180002a75  mov     rbx, [rsp+68h+arg_0]
0x180002a7a  mov     rsi, [rsp+68h+arg_8]
0x180002a7f  add     rsp, 40h
0x180002a83  pop     r15
0x180002a85  pop     r14
0x180002a87  pop     r13
0x180002a89  pop     r12
0x180002a8b  pop     rdi
0x180002a8c  retn
```
