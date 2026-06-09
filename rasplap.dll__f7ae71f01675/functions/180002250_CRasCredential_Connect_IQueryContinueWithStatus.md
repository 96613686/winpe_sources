# CRasCredential::Connect(IQueryContinueWithStatus *)

- ea: `0x180002250`
- end: `0x1800028b2`
- name: `?Connect@CRasCredential@@UEAAJPEAUIQueryContinueWithStatus@@@Z`
- size: `1634`
- prototype: `__int64 __fastcall(CRasCredential *__hidden this, struct IQueryContinueWithStatus *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180002250`
- `0x1800028b8`
- `0x1800056d4`
- `0x180005b90`
- `0x1800086d4`
- `0x18000c010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800022b3`
- `KERNEL32!EnterCriticalSection` at `0x18000239f`
- `KERNEL32!EnterCriticalSection` at `0x1800023fb`
- `KERNEL32!EnterCriticalSection` at `0x18000263d`
- `KERNEL32!EnterCriticalSection` at `0x180002691`
- `KERNEL32!EnterCriticalSection` at `0x1800022b3`
- `KERNEL32!EnterCriticalSection` at `0x18000239f`
- `KERNEL32!EnterCriticalSection` at `0x1800023fb`
- `KERNEL32!EnterCriticalSection` at `0x18000263d`
- `KERNEL32!EnterCriticalSection` at `0x180002691`
- `KERNEL32!LeaveCriticalSection` at `0x1800022e8`
- `KERNEL32!LeaveCriticalSection` at `0x1800022f6`
- `KERNEL32!LeaveCriticalSection` at `0x1800023d5`
- `KERNEL32!LeaveCriticalSection` at `0x18000265a`
- `KERNEL32!LeaveCriticalSection` at `0x1800026a8`
- `KERNEL32!LeaveCriticalSection` at `0x18000284b`
- `KERNEL32!LeaveCriticalSection` at `0x1800022e8`
- `KERNEL32!LeaveCriticalSection` at `0x1800022f6`
- `KERNEL32!LeaveCriticalSection` at `0x1800023d5`
- `KERNEL32!LeaveCriticalSection` at `0x18000265a`
- `KERNEL32!LeaveCriticalSection` at `0x1800026a8`
- `KERNEL32!LeaveCriticalSection` at `0x18000284b`
- `KERNEL32!LocalAlloc` at `0x1800023e5`
- `KERNEL32!LocalAlloc` at `0x1800023e5`
- `KERNEL32!Sleep` at `0x18000266a`
- `KERNEL32!Sleep` at `0x18000266a`
- `KERNEL32!GetLastError` at `0x180002601`
- `KERNEL32!GetLastError` at `0x180002601`
- `KERNEL32!CloseHandle` at `0x180002889`
- `KERNEL32!CloseHandle` at `0x180002889`
- `KERNEL32!CreateThread` at `0x1800025f3`
- `KERNEL32!CreateThread` at `0x1800025f3`
- `KERNEL32!LocalFree` at `0x18000287b`
- `KERNEL32!LocalFree` at `0x18000287b`
- `rtutils!TracePrintfExA` at `0x180002286`
- `rtutils!TracePrintfExA` at `0x1800022df`
- `rtutils!TracePrintfExA` at `0x180002332`
- `rtutils!TracePrintfExA` at `0x1800023c5`
- `rtutils!TracePrintfExA` at `0x180002454`
- `rtutils!TracePrintfExA` at `0x1800024cf`
- `rtutils!TracePrintfExA` at `0x1800025ce`
- `rtutils!TracePrintfExA` at `0x180002630`
- `rtutils!TracePrintfExA` at `0x1800026d3`
- `rtutils!TracePrintfExA` at `0x180002810`
- `rtutils!TracePrintfExA` at `0x18000286a`
- `rtutils!TracePrintfExA` at `0x180002286`
- `rtutils!TracePrintfExA` at `0x1800022df`
- `rtutils!TracePrintfExA` at `0x180002332`
- `rtutils!TracePrintfExA` at `0x1800023c5`
- `rtutils!TracePrintfExA` at `0x180002454`
- `rtutils!TracePrintfExA` at `0x1800024cf`
- `rtutils!TracePrintfExA` at `0x1800025ce`
- `rtutils!TracePrintfExA` at `0x180002630`
- `rtutils!TracePrintfExA` at `0x1800026d3`
- `rtutils!TracePrintfExA` at `0x180002810`
- `rtutils!TracePrintfExA` at `0x18000286a`

## string_xrefs

- `0x180002329`: `CRasCredential::Connect:Skip Raslogon as it is already connected`
- `0x180002624`: `CRasCredential::Connect:Failed to CreateThread: hr = %#x`

## pseudocode

```c
__int64 __fastcall CRasCredential::Connect(CRasCredential *this, struct IQueryContinueWithStatus *a2)
{
  int *v4; // r14
  signed int v5; // ebx
  int v6; // eax
  char *v7; // rax
  unsigned int *v8; // rbp
  int v9; // eax
  char *v10; // rdi
  __int64 v11; // rcx
  HANDLE Thread; // rdi
  __int64 v13; // rcx
  int v14; // eax
  signed int LastError; // eax
  int v16; // r9d
  __int64 v17; // r11

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "CRasCredential::Connect called for [%S]", (const wchar_t *)this + 10);
  v4 = (int *)((char *)this + 2132);
  *((_DWORD *)this + 533) = 0;
  ((void (__fastcall *)(struct IQueryContinueWithStatus *))a2->lpVtbl->AddRef)(a2);
  EnterCriticalSection(&g_ConnectStatusLock);
  if ( !g_fCanConnect )
  {
    *v4 = 3052;
    v5 = 0;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "CRasCredential::Connect:ConnectingStatus: IDS_RAS_OTHER_CONNECT_INPROGRESS");
    goto LABEL_6;
  }
  LeaveCriticalSection(&g_ConnectStatusLock);
  v5 = ((__int64 (__fastcall *)(struct IQueryContinueWithStatus *))a2->lpVtbl->QueryContinue)(a2);
  if ( v5 < 0 )
    goto LABEL_72;
  if ( *((_DWORD *)this + 135) )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "CRasCredential::Connect:Skip Raslogon as it is already connected");
    *((_DWORD *)this + 541) = 1;
    goto LABEL_72;
  }
  *((_DWORD *)this + 541) = 0;
  *(_OWORD *)((char *)this + 2140) = 0;
  *(_QWORD *)((char *)this + 2156) = 0;
  v6 = *((_DWORD *)this + 534);
  if ( *((_DWORD *)this + 138) == 1 )
  {
    if ( v6 )
    {
LABEL_14:
      if ( *((_WORD *)this + 808) )
        goto LABEL_15;
      v9 = 3055;
      goto LABEL_24;
    }
  }
  else if ( !v6 )
  {
    goto LABEL_14;
  }
  if ( *((_WORD *)this + 278) )
  {
LABEL_15:
    *v4 = 600;
    EnterCriticalSection(&g_ConnectStatusLock);
    g_connectStatus = 600;
    g_fCanConnect = 0;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "CRasCredential::Connect:ConnectingStatus: RAS_PLAP_CONNECTING");
    LeaveCriticalSection(&g_ConnectStatusLock);
    v7 = (char *)LocalAlloc(0x40u, 0x858u);
    v8 = (unsigned int *)v7;
    if ( !v7 )
    {
      v5 = -2147024882;
      EnterCriticalSection(&g_ConnectStatusLock);
      g_connectStatus = 14;
      g_fCanConnect = 1;
LABEL_6:
      LeaveCriticalSection(&g_ConnectStatusLock);
      goto LABEL_72;
    }
    v10 = v7 + 2096;
    *((_DWORD *)v7 + 527) = *((_DWORD *)this + 137);
    *((_DWORD *)v7 + 526) = *((_DWORD *)this + 138);
    *((_DWORD *)v7 + 522) = 0;
    *((_QWORD *)v7 + 262) = 0;
    StringCchCopyW((STRSAFE_LPWSTR)v7, 0x101u, (STRSAFE_LPCWSTR)this + 10);
    if ( v8[526] == 1 )
    {
      GetIdentityFromSmartcard(v11, v8, v8[527], (char *)v8 + 514);
    }
    else
    {
      if ( v8[526] != 2 )
      {
        Thread = 0;
        if ( g_dwTraceId != -1 )
          TracePrintfExA(
            g_dwTraceId,
            0xCu,
            "CRasCredential::Connect: Auth type expected to be either username/password or smartcard. Returning E_INVALIDARG.");
        v5 = -2147024809;
LABEL_70:
        LocalFree(v8);
        if ( Thread )
          CloseHandle(Thread);
        goto LABEL_72;
      }
      StringCchCopyW((STRSAFE_LPWSTR)v8 + 257, 0x101u, (STRSAFE_LPCWSTR)this + 278);
      StringCchCopyW((STRSAFE_LPWSTR)v8 + 771, 0x10u, (STRSAFE_LPCWSTR)this + 792);
      EncodePasswordW((char *)this + 1070);
      StringCchCopyW((STRSAFE_LPWSTR)v8 + 514, 0x101u, (STRSAFE_LPCWSTR)this + 535);
      EncodePasswordW((char *)this + 1070);
      EncodePasswordW(v8 + 257);
      v10 = (char *)(v8 + 524);
    }
    EncodePasswordW((char *)this + 1616);
    StringCchCopyW((STRSAFE_LPWSTR)v8 + 787, 0x101u, (STRSAFE_LPCWSTR)this + 808);
    EncodePasswordW((char *)this + 1616);
    EncodePasswordW((char *)v8 + 1574);
    v13 = *((_QWORD *)this + 1);
    if ( v13 )
    {
      v14 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v13 + 96LL))(v13, v10);
      if ( v14 < 0 && g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "ICredentialProviderCredentialEvents::OnCreatingWindow:Failed: hr = %#x", v14);
    }
    Thread = CreateThread(0, 0, RasConnect, v8, 0, 0);
    if ( Thread )
    {
      while ( 1 )
      {
        Sleep(0x64u);
        v5 = ((__int64 (__fastcall *)(struct IQueryContinueWithStatus *))a2->lpVtbl->QueryContinue)(a2);
        if ( v5 < 0 )
          break;
        EnterCriticalSection(&g_ConnectStatusLock);
        if ( g_fCanConnect )
        {
          v16 = g_connectStatus;
          *v4 = g_connectStatus;
          if ( g_dwTraceId != -1 )
            TracePrintfExA(g_dwTraceId, 0xCu, "CRasCredential::Connect: ConnectingStatus: %d", v16);
          if ( !*v4 )
          {
            *((_DWORD *)this + 135) = 1;
            if ( v8[522] )
            {
              if ( v8[526] == 1 )
              {
                if ( *((_DWORD *)this + 534) )
                {
                  EncodePasswordW(v8 + 257);
                  StringCchCopyW((STRSAFE_LPWSTR)this + 808, 0x101u, (STRSAFE_LPCWSTR)v8 + 514);
                  EncodePasswordW(v8 + 257);
                  EncodePasswordW((char *)this + 1616);
                  if ( g_dwTraceId != -1 )
                    TracePrintfExA(g_dwTraceId, 0xCu, "Using RAS credentials [smartcard] to do local logon.");
                }
                else if ( g_dwTraceId != -1 )
                {
                  TracePrintfExA(
                    g_dwTraceId,
                    0xCu,
                    "Using smartcard PIN for RAS connection and using username/password for local logon.");
                }
              }
              else if ( v8[526] == 2 )
              {
                if ( *((_DWORD *)this + 534) )
                {
                  StringCchCopyW((STRSAFE_LPWSTR)this + 278, 0x101u, (STRSAFE_LPCWSTR)v8 + 257);
                  StringCchCopyW((STRSAFE_LPWSTR)this + 792, 0x10u, (STRSAFE_LPCWSTR)v8 + 771);
                  EncodePasswordW(v8 + 257);
                  StringCchCopyW((STRSAFE_LPWSTR)this + 535, 0x101u, (STRSAFE_LPCWSTR)v8 + 514);
                  EncodePasswordW(v17);
                  EncodePasswordW(v8 + 257);
                  if ( g_dwTraceId != -1 )
                    TracePrintfExA(g_dwTraceId, 0xCu, "Using RAS credentials [username/password] to do local logon.");
                }
                else if ( g_dwTraceId != -1 )
                {
                  TracePrintfExA(
                    g_dwTraceId,
                    0xCu,
                    "Using username/password for RAS connection and using smartcard PIN for local logon.");
                }
              }
            }
            *(_OWORD *)((char *)this + 2140) = *((_OWORD *)v8 + 132);
            *(_QWORD *)((char *)this + 2156) = *((_QWORD *)v8 + 266);
          }
          v5 = *v4;
          if ( *v4 > 0 )
            v5 = (unsigned __int16)v5 | 0x80070000;
          LeaveCriticalSection(&g_ConnectStatusLock);
          goto LABEL_69;
        }
        LeaveCriticalSection(&g_ConnectStatusLock);
      }
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "CRasCredential::Connect: Timeout happened. Hence exiting");
LABEL_69:
      CRasCredential::_UpdateConnectStatus(this);
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "CRasCredential::Connect:Failed to CreateThread: hr = %#x", v5);
      EnterCriticalSection(&g_ConnectStatusLock);
      g_connectStatus = (unsigned __int16)v5;
      g_fCanConnect = 1;
      LeaveCriticalSection(&g_ConnectStatusLock);
    }
    goto LABEL_70;
  }
  v9 = 3051;
LABEL_24:
  *v4 = v9;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "CRasCredential::Connect:_IsAuthDataValidForConnection() Failed");
  v5 = -2147024205;
LABEL_72:
  ((void (__fastcall *)(struct IQueryContinueWithStatus *))a2->lpVtbl->Release)(a2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180002250  push    rbx
0x180002252  push    rbp
0x180002253  push    rsi
0x180002254  push    rdi
0x180002255  push    r12
0x180002257  push    r13
0x180002259  push    r14
0x18000225b  push    r15
0x18000225d  sub     rsp, 38h
0x180002261  mov     rsi, rcx
0x180002264  or      edi, 0FFFFFFFFh
0x180002267  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000226d  mov     r12, rdx
0x180002270  mov     ebp, 0Ch
0x180002275  cmp     ecx, edi
0x180002277  jz      short loc_18000228C
0x180002279  lea     r9, [rsi+14h]
0x18000227d  mov     edx, ebp; dwFlags
0x18000227f  lea     r8, aCrascredential_1; "CRasCredential::Connect called for [%S]"
0x180002286  call    cs:__imp_TracePrintfExA
0x18000228c  lea     r14, [rsi+854h]
0x180002293  xor     r13d, r13d
0x180002296  mov     [r14], r13d
0x180002299  mov     rcx, r12
0x18000229c  mov     rax, [r12]
0x1800022a0  mov     rax, [rax+8]
0x1800022a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022a9  lea     r15, g_ConnectStatusLock
0x1800022b0  mov     rcx, r15; lpCriticalSection
0x1800022b3  call    cs:__imp_EnterCriticalSection
0x1800022b9  cmp     cs:g_fCanConnect, r13d
0x1800022c0  jnz     short loc_1800022F3
0x1800022c2  mov     dword ptr [r14], 0BECh
0x1800022c9  mov     ebx, r13d
0x1800022cc  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800022d2  cmp     ecx, edi
0x1800022d4  jz      short loc_1800022E5
0x1800022d6  lea     r8, aCrascredential_9; "CRasCredential::Connect:ConnectingStatu"...
0x1800022dd  mov     edx, ebp; dwFlags
0x1800022df  call    cs:__imp_TracePrintfExA
0x1800022e5  mov     rcx, r15; lpCriticalSection
0x1800022e8  call    cs:__imp_LeaveCriticalSection
0x1800022ee  jmp     loc_18000288F
0x1800022f3  mov     rcx, r15; lpCriticalSection
0x1800022f6  call    cs:__imp_LeaveCriticalSection
0x1800022fc  mov     rax, [r12]
0x180002300  mov     rcx, r12
0x180002303  mov     rax, [rax+18h]
0x180002307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000230c  mov     ebx, eax
0x18000230e  test    eax, eax
0x180002310  js      loc_18000288F
0x180002316  cmp     [rsi+21Ch], r13d
0x18000231d  jz      short loc_180002347
0x18000231f  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180002325  cmp     ecx, edi
0x180002327  jz      short loc_180002338
0x180002329  lea     r8, aCrascredential_6; "CRasCredential::Connect:Skip Raslogon a"...
0x180002330  mov     edx, ebp; dwFlags
0x180002332  call    cs:__imp_TracePrintfExA
0x180002338  mov     dword ptr [rsi+874h], 1
0x180002342  jmp     loc_18000288F
0x180002347  xor     eax, eax
0x180002349  mov     [rsi+874h], r13d
0x180002350  xorps   xmm0, xmm0
0x180002353  mov     r15d, 1
0x180002359  movups  xmmword ptr [rsi+85Ch], xmm0
0x180002360  mov     [rsi+86Ch], rax
0x180002367  mov     eax, [rsi+858h]
0x18000236d  cmp     [rsi+228h], r15d
0x180002374  jnz     loc_18000242F
0x18000237a  test    eax, eax
0x18000237c  jz      loc_18000241A
0x180002382  cmp     [rsi+650h], r13w
0x18000238a  jz      loc_180002439
0x180002390  mov     ebx, 258h
0x180002395  lea     rcx, g_ConnectStatusLock; lpCriticalSection
0x18000239c  mov     [r14], ebx
0x18000239f  call    cs:__imp_EnterCriticalSection
0x1800023a5  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800023ab  mov     cs:g_connectStatus, ebx
0x1800023b1  mov     cs:g_fCanConnect, r13d
0x1800023b8  cmp     ecx, edi
0x1800023ba  jz      short loc_1800023CB
0x1800023bc  lea     r8, aCrascredential_19; "CRasCredential::Connect:ConnectingStatu"...
0x1800023c3  mov     edx, ebp; dwFlags
0x1800023c5  call    cs:__imp_TracePrintfExA
0x1800023cb  lea     rdi, g_ConnectStatusLock
0x1800023d2  mov     rcx, rdi; lpCriticalSection
0x1800023d5  call    cs:__imp_LeaveCriticalSection
0x1800023db  mov     edx, 858h; uBytes
0x1800023e0  mov     ecx, 40h ; '@'; uFlags
0x1800023e5  call    cs:__imp_LocalAlloc
0x1800023eb  mov     rbp, rax
0x1800023ee  test    rax, rax
0x1800023f1  jnz     short loc_180002464
0x1800023f3  mov     rcx, rdi; lpCriticalSection
0x1800023f6  mov     ebx, 8007000Eh
0x1800023fb  call    cs:__imp_EnterCriticalSection
0x180002401  mov     rcx, rdi
0x180002404  mov     cs:g_connectStatus, 0Eh
0x18000240e  mov     cs:g_fCanConnect, r15d
0x180002415  jmp     loc_1800022E8
0x18000241a  cmp     [rsi+22Ch], r13w
0x180002422  jnz     loc_180002390
0x180002428  mov     eax, 0BEBh
0x18000242d  jmp     short loc_18000243E
0x18000242f  test    eax, eax
0x180002431  jz      loc_180002382
0x180002437  jmp     short loc_18000241A
0x180002439  mov     eax, 0BEFh
0x18000243e  mov     [r14], eax
0x180002441  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180002447  cmp     ecx, edi
0x180002449  jz      short loc_18000245A
0x18000244b  lea     r8, aCrascredential_24; "CRasCredential::Connect:_IsAuthDataVali"...
0x180002452  mov     edx, ebp; dwFlags
0x180002454  call    cs:__imp_TracePrintfExA
0x18000245a  mov     ebx, 800702B3h
0x18000245f  jmp     loc_18000288F
0x180002464  lea     r8, [rsi+14h]; pszSrc
0x180002468  mov     ebx, 101h
0x18000246d  mov     eax, [r8+210h]
0x180002474  lea     rdi, [rbp+830h]
0x18000247b  mov     [rbp+83Ch], eax
0x180002481  mov     edx, ebx; cchDest
0x180002483  mov     eax, [rsi+228h]
0x180002489  mov     rcx, rbp; pszDest
0x18000248c  mov     [rbp+838h], eax
0x180002492  mov     [rbp+828h], r13d
0x180002499  mov     [rdi], r13
0x18000249c  call    StringCchCopyW
0x1800024a1  mov     eax, [rbp+838h]
0x1800024a7  sub     eax, r15d
0x1800024aa  jz      loc_18000254C
0x1800024b0  cmp     eax, r15d
0x1800024b3  jz      short loc_1800024DF
0x1800024b5  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800024bb  mov     rdi, r13
0x1800024be  cmp     ecx, 0FFFFFFFFh
0x1800024c1  jz      short loc_1800024D5
0x1800024c3  lea     r8, aCrascredential_11; "CRasCredential::Connect: Auth type expe"...
0x1800024ca  mov     edx, 0Ch; dwFlags
0x1800024cf  call    cs:__imp_TracePrintfExA
0x1800024d5  mov     ebx, 80070057h
0x1800024da  jmp     loc_180002878
0x1800024df  lea     r8, [rsi+22Ch]; pszSrc
0x1800024e6  mov     rdx, rbx; cchDest
0x1800024e9  lea     rcx, [rbp+202h]; pszDest
0x1800024f0  call    StringCchCopyW
0x1800024f5  lea     r8, [rsi+630h]; pszSrc
0x1800024fc  mov     edx, 10h; cchDest
0x180002501  lea     rcx, [rbp+606h]; pszDest
0x180002508  call    StringCchCopyW
0x18000250d  lea     rdi, [rsi+42Eh]
0x180002514  mov     rcx, rdi
0x180002517  call    EncodePasswordW
0x18000251c  lea     rbx, [rbp+404h]
0x180002523  mov     r8, rdi; pszSrc
0x180002526  mov     rcx, rbx; pszDest
0x180002529  mov     edx, 101h; cchDest
0x18000252e  call    StringCchCopyW
0x180002533  mov     rcx, rdi
0x180002536  call    EncodePasswordW
0x18000253b  mov     rcx, rbx
0x18000253e  call    EncodePasswordW
0x180002543  lea     rdi, [rbp+830h]
0x18000254a  jmp     short loc_180002562
0x18000254c  mov     r8d, [rbp+83Ch]
0x180002553  lea     r9, [rbp+202h]
0x18000255a  mov     rdx, rbp
0x18000255d  call    GetIdentityFromSmartcard
0x180002562  lea     r13, [rsi+650h]
0x180002569  mov     rcx, r13
0x18000256c  call    EncodePasswordW
0x180002571  lea     rbx, [rbp+626h]
0x180002578  mov     r8, r13; pszSrc
0x18000257b  mov     rcx, rbx; pszDest
0x18000257e  mov     edx, 101h; cchDest
0x180002583  call    StringCchCopyW
0x180002588  mov     rcx, r13
0x18000258b  call    EncodePasswordW
0x180002590  mov     rcx, rbx
0x180002593  call    EncodePasswordW
0x180002598  mov     rcx, [rsi+8]
0x18000259c  test    rcx, rcx
0x18000259f  jz      short loc_1800025D4
0x1800025a1  mov     rax, [rcx]
0x1800025a4  mov     rdx, rdi
0x1800025a7  mov     rax, [rax+60h]
0x1800025ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025b0  test    eax, eax
0x1800025b2  jns     short loc_1800025D4
0x1800025b4  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800025ba  cmp     ecx, 0FFFFFFFFh
0x1800025bd  jz      short loc_1800025D4
0x1800025bf  mov     r9d, eax
0x1800025c2  lea     r8, aIcredentialpro; "ICredentialProviderCredentialEvents::On"...
0x1800025c9  mov     edx, 0Ch; dwFlags
0x1800025ce  call    cs:__imp_TracePrintfExA
0x1800025d4  mov     [rsp+78h+lpThreadId], 0; lpThreadId
0x1800025dd  lea     r8, RasConnect; lpStartAddress
0x1800025e4  mov     r9, rbp; lpParameter
0x1800025e7  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x1800025ef  xor     edx, edx; dwStackSize
0x1800025f1  xor     ecx, ecx; lpThreadAttributes
0x1800025f3  call    cs:__imp_CreateThread
0x1800025f9  mov     rdi, rax
0x1800025fc  test    rax, rax
0x1800025ff  jnz     short loc_180002665
0x180002601  call    cs:__imp_GetLastError
0x180002607  mov     ebx, eax
0x180002609  test    eax, eax
0x18000260b  jle     short loc_180002616
0x18000260d  movzx   ebx, ax
0x180002610  or      ebx, 80070000h
0x180002616  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000261c  cmp     ecx, 0FFFFFFFFh
0x18000261f  jz      short loc_180002636
0x180002621  mov     r9d, ebx
0x180002624  lea     r8, aCrascredential_18; "CRasCredential::Connect:Failed to Creat"...
0x18000262b  mov     edx, 0Ch; dwFlags
0x180002630  call    cs:__imp_TracePrintfExA
0x180002636  lea     rcx, g_ConnectStatusLock; lpCriticalSection
0x18000263d  call    cs:__imp_EnterCriticalSection
0x180002643  movzx   eax, bx
0x180002646  lea     rcx, g_ConnectStatusLock; lpCriticalSection
0x18000264d  mov     cs:g_connectStatus, eax
0x180002653  mov     cs:g_fCanConnect, r15d
0x18000265a  call    cs:__imp_LeaveCriticalSection
0x180002660  jmp     loc_180002878
0x180002665  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18000266a  call    cs:__imp_Sleep
0x180002670  mov     rax, [r12]
0x180002674  mov     rcx, r12
0x180002677  mov     rax, [rax+18h]
0x18000267b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002680  mov     ebx, eax
0x180002682  test    eax, eax
0x180002684  js      loc_180002853
0x18000268a  lea     rcx, g_ConnectStatusLock; lpCriticalSection
0x180002691  call    cs:__imp_EnterCriticalSection
0x180002697  xor     ebx, ebx
0x180002699  cmp     cs:g_fCanConnect, ebx
0x18000269f  jnz     short loc_1800026B0
0x1800026a1  lea     rcx, g_ConnectStatusLock; lpCriticalSection
0x1800026a8  call    cs:__imp_LeaveCriticalSection
0x1800026ae  jmp     short loc_180002665
0x1800026b0  mov     r9d, cs:g_connectStatus
0x1800026b7  or      edx, 0FFFFFFFFh
0x1800026ba  mov     [r14], r9d
0x1800026bd  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800026c3  cmp     ecx, edx
0x1800026c5  jz      short loc_1800026DC
0x1800026c7  lea     r8, aCrascredential_5; "CRasCredential::Connect: ConnectingStat"...
0x1800026ce  mov     edx, 0Ch; dwFlags
0x1800026d3  call    cs:__imp_TracePrintfExA
0x1800026d9  or      edx, 0FFFFFFFFh
0x1800026dc  cmp     [r14], ebx
0x1800026df  jnz     loc_180002834
0x1800026e5  mov     [rsi+21Ch], r15d
0x1800026ec  cmp     [rbp+828h], ebx
0x1800026f2  jz      loc_180002816
0x1800026f8  mov     ecx, [rbp+838h]
0x1800026fe  sub     ecx, r15d
0x180002701  jz      loc_1800027AF
0x180002707  cmp     ecx, r15d
0x18000270a  jnz     loc_180002816
0x180002710  cmp     [rsi+858h], ebx
0x180002716  jz      loc_18000279C
0x18000271c  mov     r15d, 101h
0x180002722  lea     r8, [rbp+202h]; pszSrc
0x180002729  mov     edx, r15d; cchDest
0x18000272c  lea     rcx, [rsi+22Ch]; pszDest
0x180002733  call    StringCchCopyW
0x180002738  lea     r8, [rbp+606h]; pszSrc
0x18000273f  mov     edx, 10h; cchDest
0x180002744  lea     rcx, [rsi+630h]; pszDest
0x18000274b  call    StringCchCopyW
0x180002750  lea     rbx, [rbp+404h]
0x180002757  mov     rcx, rbx
0x18000275a  call    EncodePasswordW
0x18000275f  lea     r11, [rsi+42Eh]
0x180002766  mov     r8, rbx; pszSrc
0x180002769  mov     rcx, r11; pszDest
0x18000276c  mov     edx, r15d; cchDest
0x18000276f  call    StringCchCopyW
0x180002774  mov     rcx, r11
0x180002777  call    EncodePasswordW
0x18000277c  mov     rcx, rbx
0x18000277f  call    EncodePasswordW
0x180002784  mov     ecx, cs:g_dwTraceId
0x18000278a  cmp     ecx, 0FFFFFFFFh
0x18000278d  jz      loc_180002816
0x180002793  lea     r8, aUsingRasCreden_0; "Using RAS credentials [username/passwor"...
0x18000279a  jmp     short loc_18000280B
0x18000279c  mov     ecx, cs:g_dwTraceId
0x1800027a2  cmp     ecx, edx
0x1800027a4  jz      short loc_180002816
0x1800027a6  lea     r8, aUsingUsernameP; "Using username/password for RAS connect"...
  ... truncated ...
```
