# GetCurrentUserSID(CAPITempBufferRef<uchar> &)

- ea: `0x1800252a8`
- end: `0x18002554e`
- name: `?GetCurrentUserSID@@YAKAEAV?$CAPITempBufferRef@E@@@Z`
- size: `678`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800227d0`
- `0x1800250d4`
- `0x18006bd18`
- `0x180145e58`
- `0x18015cd14`
- `0x18020614c`

## callees

- `0x180024f9c`
- `0x1800252a8`
- `0x180025a18`
- `0x1800b7800`
- `0x180146568`
- `0x18015238c`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!CopySid` at `0x180025431`
- `ADVAPI32!CopySid` at `0x180025431`
- `ADVAPI32!GetTokenInformation` at `0x180025417`
- `ADVAPI32!GetTokenInformation` at `0x180025417`
- `ADVAPI32!OpenThreadToken` at `0x1800253b2`
- `ADVAPI32!OpenThreadToken` at `0x1800253b2`
- `ADVAPI32!OpenProcessToken` at `0x1800253dd`
- `ADVAPI32!OpenProcessToken` at `0x1800253dd`
- `KERNEL32!CloseHandle` at `0x18002544a`
- `KERNEL32!CloseHandle` at `0x18002544a`
- `KERNEL32!LeaveCriticalSection` at `0x18002534a`
- `KERNEL32!LeaveCriticalSection` at `0x18002534a`
- `KERNEL32!GetLastError` at `0x1800253bc`
- `KERNEL32!GetLastError` at `0x18002549b`
- `KERNEL32!GetLastError` at `0x1800254e5`
- `KERNEL32!GetLastError` at `0x180025541`
- `KERNEL32!GetLastError` at `0x1800253bc`
- `KERNEL32!GetLastError` at `0x18002549b`
- `KERNEL32!GetLastError` at `0x1800254e5`
- `KERNEL32!GetLastError` at `0x180025541`
- `KERNEL32!EnterCriticalSection` at `0x180025326`
- `KERNEL32!EnterCriticalSection` at `0x180025326`
- `KERNEL32!GlobalAlloc` at `0x1800254b6`
- `KERNEL32!GlobalAlloc` at `0x1800254b6`
- `KERNEL32!GetCurrentThread` at `0x18002539e`
- `KERNEL32!GetCurrentThread` at `0x18002539e`
- `KERNEL32!GetCurrentProcess` at `0x1800253cd`
- `KERNEL32!GetCurrentProcess` at `0x1800253cd`
- `KERNEL32!GlobalFree` at `0x1800254c7`
- `KERNEL32!GlobalFree` at `0x1800254c7`
- `KERNEL32!TlsGetValue` at `0x180025337`
- `KERNEL32!TlsGetValue` at `0x180025337`

## string_xrefs

- `0x180025508`: `GetTokenInformation failed with error %d`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSID(__int64 a1)
{
  __int64 v1; // rbx
  HGLOBAL v3; // rsi
  int v4; // eax
  bool v5; // dl
  int v6; // ecx
  unsigned int v7; // ebx
  struct IUnknownVtbl *lpVtbl; // rax
  bool v9; // si
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  HGLOBAL v13; // rbx
  bool *v15; // rdx
  DWORD v16; // eax
  void *TokenHandle; // [rsp+60h] [rbp-49h] BYREF
  DWORD ReturnLength; // [rsp+68h] [rbp-41h] BYREF
  PSID TokenInformation[12]; // [rsp+70h] [rbp-39h] BYREF

  v1 = a1 + 16;
  if ( *(int *)(a1 + 12) < 72 )
    v3 = GlobalAlloc(0, 0x48u);
  else
    v3 = (HGLOBAL)(a1 + 16);
  if ( v3 )
  {
    if ( *(_QWORD *)a1 != v1 )
      GlobalFree(*(HGLOBAL *)a1);
    *(_QWORD *)a1 = v3;
    *(_DWORD *)(a1 + 8) = 72;
    TokenHandle = 0;
    v4 = RunningAsLocalSystem();
    if ( v4 == -1 )
      return 5;
    v6 = g_scServerContext;
    v7 = 0;
    if ( g_scServerContext == 2 || v4 == 1 )
    {
      EnterCriticalSection(&g_csImpersonationLock);
      if ( g_dwImpersonationSlot != -1 )
        v7 = (unsigned int)TlsGetValue(g_dwImpersonationSlot) >> 29;
      LeaveCriticalSection(&g_csImpersonationLock);
      v6 = g_scServerContext;
    }
    if ( v6 == 2 && v7 == 1 )
    {
      CCoImpersonate::CCoImpersonate((CCoImpersonate *)&ReturnLength, v5);
      LastError = OpenUserToken(&TokenHandle, v15);
      CCoImpersonate::~CCoImpersonate((CCoImpersonate *)&ReturnLength);
      v9 = LastError == 0;
LABEL_16:
      if ( !LastError )
      {
LABEL_26:
        v13 = *(HGLOBAL *)a1;
        ReturnLength = 0;
        if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
        {
          if ( CopySid(0x48u, v13, TokenInformation[0]) )
            LastError = 0;
          else
            LastError = GetLastError();
        }
        else
        {
          v16 = GetLastError();
          LastError = v16;
          if ( g_dmDiagnosticMode )
            DebugString(
              9,
              0,
              0,
              L"GetTokenInformation failed with error %d",
              (const unsigned __int16 *)v16,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
        }
        if ( v9 )
          CloseHandle(TokenHandle);
      }
      return LastError;
    }
    lpVtbl = (struct IUnknownVtbl *)Token;
    v9 = 0;
    if ( !Token && v6 == 2 )
    {
      if ( !CMsiTransaction::m_pMsiTransaction )
      {
        TokenHandle = 0;
        goto LABEL_20;
      }
      lpVtbl = CMsiTransaction::m_pMsiTransaction[5].lpVtbl;
    }
    LastError = 0;
    TokenHandle = lpVtbl;
    if ( lpVtbl )
      goto LABEL_16;
LABEL_20:
    LastError = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      if ( LastError == 1008 )
      {
        LastError = 0;
        CurrentProcess = GetCurrentProcess();
        if ( !OpenProcessToken(CurrentProcess, 0xCu, &TokenHandle) )
          LastError = GetLastError();
      }
    }
    if ( LastError )
      return LastError;
    v9 = 1;
    goto LABEL_26;
  }
  return 14;
}

```

## disassembly

```asm
0x1800252a8  push    rbp
0x1800252aa  push    rbx
0x1800252ab  push    rsi
0x1800252ac  push    rdi
0x1800252ad  lea     rbp, [rsp-3Fh]
0x1800252b2  sub     rsp, 0E8h
0x1800252b9  mov     rax, cs:__security_cookie
0x1800252c0  xor     rax, rsp
0x1800252c3  mov     [rbp+57h+var_30], rax
0x1800252c7  cmp     dword ptr [rcx+0Ch], 48h ; 'H'
0x1800252cb  lea     rbx, [rcx+10h]
0x1800252cf  mov     rdi, rcx
0x1800252d2  jl      loc_1800254AF
0x1800252d8  mov     rsi, rbx
0x1800252db  test    rsi, rsi
0x1800252de  jz      loc_1800254A8
0x1800252e4  cmp     [rdi], rbx
0x1800252e7  jnz     loc_1800254C4
0x1800252ed  mov     [rdi], rsi
0x1800252f0  mov     dword ptr [rdi+8], 48h ; 'H'
0x1800252f7  mov     [rbp+57h+TokenHandle], 0
0x1800252ff  call    ?RunningAsLocalSystem@@YA?AW4TRI@@XZ; RunningAsLocalSystem(void)
0x180025304  cmp     eax, 0FFFFFFFFh
0x180025307  jz      loc_1800254D2
0x18002530d  mov     ecx, cs:?g_scServerContext@@3W4scEnum@@A; scEnum g_scServerContext
0x180025313  xor     ebx, ebx
0x180025315  cmp     ecx, 2
0x180025318  jz      short loc_18002531F
0x18002531a  cmp     eax, 1
0x18002531d  jnz     short loc_180025356
0x18002531f  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180025326  call    cs:__imp_EnterCriticalSection
0x18002532c  mov     ecx, cs:?g_dwImpersonationSlot@@3KA; dwTlsIndex
0x180025332  cmp     ecx, 0FFFFFFFFh
0x180025335  jz      short loc_180025343
0x180025337  call    cs:__imp_TlsGetValue
0x18002533d  mov     rbx, rax
0x180025340  shr     ebx, 1Dh
0x180025343  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002534a  call    cs:__imp_LeaveCriticalSection
0x180025350  mov     ecx, cs:?g_scServerContext@@3W4scEnum@@A; scEnum g_scServerContext
0x180025356  cmp     ecx, 2
0x180025359  jz      loc_18002546A
0x18002535f  mov     rax, cs:Token
0x180025366  xor     sil, sil
0x180025369  test    rax, rax
0x18002536c  jnz     short loc_180025373
0x18002536e  cmp     ecx, 2
0x180025371  jz      short loc_180025388
0x180025373  xor     ebx, ebx
0x180025375  mov     [rbp+57h+TokenHandle], rax
0x180025379  test    rax, rax
0x18002537c  jz      short loc_18002539C
0x18002537e  test    ebx, ebx
0x180025380  jnz     loc_180025450
0x180025386  jmp     short loc_1800253F2
0x180025388  mov     rax, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x18002538f  test    rax, rax
0x180025392  jnz     loc_1800254DC
0x180025398  mov     [rbp+57h+TokenHandle], rax
0x18002539c  xor     ebx, ebx
0x18002539e  call    cs:__imp_GetCurrentThread
0x1800253a4  mov     rcx, rax; ThreadHandle
0x1800253a7  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800253ab  lea     edx, [rbx+0Ch]; DesiredAccess
0x1800253ae  lea     r8d, [rbx+1]; OpenAsSelf
0x1800253b2  call    cs:__imp_OpenThreadToken
0x1800253b8  test    eax, eax
0x1800253ba  jnz     short loc_1800253EB
0x1800253bc  call    cs:__imp_GetLastError
0x1800253c2  mov     ebx, eax
0x1800253c4  cmp     eax, 3F0h
0x1800253c9  jnz     short loc_1800253EB
0x1800253cb  xor     ebx, ebx
0x1800253cd  call    cs:__imp_GetCurrentProcess
0x1800253d3  mov     rcx, rax; ProcessHandle
0x1800253d6  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1800253da  lea     edx, [rbx+0Ch]; DesiredAccess
0x1800253dd  call    cs:__imp_OpenProcessToken
0x1800253e3  test    eax, eax
0x1800253e5  jz      loc_18002549B
0x1800253eb  test    ebx, ebx
0x1800253ed  jnz     short loc_180025450
0x1800253ef  mov     sil, 1
0x1800253f2  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800253f6  lea     rax, [rbp+57h+var_98]
0x1800253fa  mov     rbx, [rdi]
0x1800253fd  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180025401  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180025407  mov     [rbp+57h+var_98], 0
0x18002540e  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x180025413  lea     edx, [r9-57h]; TokenInformationClass
0x180025417  call    cs:__imp_GetTokenInformation
0x18002541d  test    eax, eax
0x18002541f  jz      loc_1800254E5
0x180025425  mov     r8, [rbp+57h+TokenInformation]; pSourceSid
0x180025429  mov     rdx, rbx; pDestinationSid
0x18002542c  mov     ecx, 48h ; 'H'; nDestinationSidLength
0x180025431  call    cs:__imp_CopySid
0x180025437  test    eax, eax
0x180025439  jz      loc_180025541
0x18002543f  xor     ebx, ebx
0x180025441  test    sil, sil
0x180025444  jz      short loc_180025450
0x180025446  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18002544a  call    cs:__imp_CloseHandle
0x180025450  mov     eax, ebx
0x180025452  mov     rcx, [rbp+57h+var_30]
0x180025456  xor     rcx, rsp; StackCookie
0x180025459  call    __security_check_cookie
0x18002545e  add     rsp, 0E8h
0x180025465  pop     rdi
0x180025466  pop     rsi
0x180025467  pop     rbx
0x180025468  pop     rbp
0x180025469  retn
0x18002546a  cmp     ebx, 1
0x18002546d  jnz     loc_18002535F
0x180025473  lea     rcx, [rbp+57h+var_98]; this
0x180025477  call    ??0CCoImpersonate@@QEAA@_N@Z; CCoImpersonate::CCoImpersonate(bool)
0x18002547c  lea     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180025480  call    ?OpenUserToken@@YAKAEAPEAXPEA_N@Z; OpenUserToken(void * &,bool *)
0x180025485  lea     rcx, [rbp+57h+var_98]; this
0x180025489  mov     ebx, eax
0x18002548b  call    ??1CCoImpersonate@@QEAA@XZ; CCoImpersonate::~CCoImpersonate(void)
0x180025490  test    ebx, ebx
0x180025492  setz    sil
0x180025496  jmp     loc_18002537E
0x18002549b  call    cs:__imp_GetLastError
0x1800254a1  mov     ebx, eax
0x1800254a3  jmp     loc_1800253EB
0x1800254a8  mov     eax, 0Eh
0x1800254ad  jmp     short loc_180025452
0x1800254af  mov     edx, 48h ; 'H'; dwBytes
0x1800254b4  xor     ecx, ecx; uFlags
0x1800254b6  call    cs:__imp_GlobalAlloc
0x1800254bc  mov     rsi, rax
0x1800254bf  jmp     loc_1800252DB
0x1800254c4  mov     rcx, [rdi]; hMem
0x1800254c7  call    cs:__imp_GlobalFree
0x1800254cd  jmp     loc_1800252ED
0x1800254d2  mov     ebx, 5
0x1800254d7  jmp     loc_180025450
0x1800254dc  mov     rax, [rax+28h]
0x1800254e0  jmp     loc_180025373
0x1800254e5  call    cs:__imp_GetLastError
0x1800254eb  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x1800254f2  mov     ebx, eax
0x1800254f4  jz      loc_180025441
0x1800254fa  lea     rcx, aNull; "(NULL)"
0x180025501  xor     edx, edx; unsigned __int16
0x180025503  mov     [rsp+100h+var_A8], rdx; void *
0x180025508  lea     r9, aGettokeninform; "GetTokenInformation failed with error %"...
0x18002550f  mov     [rsp+100h+var_B0], edx; unsigned int
0x180025513  xor     r8d, r8d; int
0x180025516  mov     [rsp+100h+var_B8], rcx; unsigned __int16 *
0x18002551b  mov     [rsp+100h+var_C0], rcx; unsigned __int16 *
0x180025520  mov     [rsp+100h+var_C8], rcx; unsigned __int16 *
0x180025525  mov     [rsp+100h+var_D0], rcx; unsigned __int16 *
0x18002552a  mov     [rsp+100h+var_D8], rcx; unsigned __int16 *
0x18002552f  lea     ecx, [rdx+9]; int
0x180025532  mov     [rsp+100h+ReturnLength], rbx; unsigned __int16 *
0x180025537  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18002553c  jmp     loc_180025441
0x180025541  call    cs:__imp_GetLastError
0x180025547  mov     ebx, eax
0x180025549  jmp     loc_180025441
```
