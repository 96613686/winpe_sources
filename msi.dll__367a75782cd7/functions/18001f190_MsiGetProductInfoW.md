# MsiGetProductInfoW

- ea: `0x18001f190`
- end: `0x18001f6f1`
- name: `MsiGetProductInfoW`
- size: `1377`
- prototype: `UINT __stdcall(LPCWSTR szProduct, LPCWSTR szAttribute, LPWSTR lpValueBuf, LPDWORD pcchValueBuf)`
- caller_count: `8`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001db00`
- `0x180031ff0`
- `0x180090f70`
- `0x180098b50`
- `0x18011ff14`
- `0x18013ae34`
- `0x18018b330`
- `0x18019e210`

## callees

- `0x18001d960`
- `0x18001f190`
- `0x180021030`
- `0x180025a18`
- `0x18004cf08`
- `0x1800a9d48`
- `0x180157094`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x18001f5b5`
- `ADVAPI32!SetThreadToken` at `0x18001f5d6`
- `ADVAPI32!SetThreadToken` at `0x18001f5f9`
- `ADVAPI32!SetThreadToken` at `0x18001f692`
- `ADVAPI32!SetThreadToken` at `0x18001f5b5`
- `ADVAPI32!SetThreadToken` at `0x18001f5d6`
- `ADVAPI32!SetThreadToken` at `0x18001f5f9`
- `ADVAPI32!SetThreadToken` at `0x18001f692`
- `ADVAPI32!OpenThreadToken` at `0x18001f45d`
- `ADVAPI32!OpenThreadToken` at `0x18001f4dc`
- `ADVAPI32!OpenThreadToken` at `0x18001f45d`
- `ADVAPI32!OpenThreadToken` at `0x18001f4dc`
- `ADVAPI32!OpenProcessToken` at `0x18001f48c`
- `ADVAPI32!OpenProcessToken` at `0x18001f507`
- `ADVAPI32!OpenProcessToken` at `0x18001f48c`
- `ADVAPI32!OpenProcessToken` at `0x18001f507`
- `KERNEL32!CloseHandle` at `0x18001f57f`
- `KERNEL32!CloseHandle` at `0x18001f5a2`
- `KERNEL32!CloseHandle` at `0x18001f5c9`
- `KERNEL32!CloseHandle` at `0x18001f5ea`
- `KERNEL32!CloseHandle` at `0x18001f57f`
- `KERNEL32!CloseHandle` at `0x18001f5a2`
- `KERNEL32!CloseHandle` at `0x18001f5c9`
- `KERNEL32!CloseHandle` at `0x18001f5ea`
- `KERNEL32!LeaveCriticalSection` at `0x18001f214`
- `KERNEL32!LeaveCriticalSection` at `0x18001f3f1`
- `KERNEL32!LeaveCriticalSection` at `0x18001f562`
- `KERNEL32!LeaveCriticalSection` at `0x18001f214`
- `KERNEL32!LeaveCriticalSection` at `0x18001f3f1`
- `KERNEL32!LeaveCriticalSection` at `0x18001f562`
- `KERNEL32!GetLastError` at `0x18001f22f`
- `KERNEL32!GetLastError` at `0x18001f22f`
- `KERNEL32!EnterCriticalSection` at `0x18001f1f8`
- `KERNEL32!EnterCriticalSection` at `0x18001f3e2`
- `KERNEL32!EnterCriticalSection` at `0x18001f1f8`
- `KERNEL32!EnterCriticalSection` at `0x18001f3e2`
- `KERNEL32!GetCurrentThread` at `0x18001f446`
- `KERNEL32!GetCurrentThread` at `0x18001f4c5`
- `KERNEL32!GetCurrentThread` at `0x18001f446`
- `KERNEL32!GetCurrentThread` at `0x18001f4c5`
- `KERNEL32!GetCurrentProcess` at `0x18001f479`
- `KERNEL32!GetCurrentProcess` at `0x18001f4f4`
- `KERNEL32!GetCurrentProcess` at `0x18001f479`
- `KERNEL32!GetCurrentProcess` at `0x18001f4f4`
- `KERNEL32!lstrlenW` at `0x18001f286`
- `KERNEL32!lstrlenW` at `0x18001f286`
- `KERNEL32!GlobalFree` at `0x18001f2b1`
- `KERNEL32!GlobalFree` at `0x18001f2d0`
- `KERNEL32!GlobalFree` at `0x18001f38a`
- `KERNEL32!GlobalFree` at `0x18001f432`
- `KERNEL32!GlobalFree` at `0x18001f2b1`
- `KERNEL32!GlobalFree` at `0x18001f2d0`
- `KERNEL32!GlobalFree` at `0x18001f38a`
- `KERNEL32!GlobalFree` at `0x18001f432`
- `KERNEL32!TlsSetValue` at `0x18001f242`
- `KERNEL32!TlsSetValue` at `0x18001f406`
- `KERNEL32!TlsSetValue` at `0x18001f242`
- `KERNEL32!TlsSetValue` at `0x18001f406`
- `KERNEL32!TlsGetValue` at `0x18001f21c`
- `KERNEL32!TlsGetValue` at `0x18001f21c`
- `KERNEL32!TlsAlloc` at `0x18001f544`
- `KERNEL32!TlsAlloc` at `0x18001f544`

## string_xrefs

- `0x18001f317`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`

## pseudocode

```c
UINT __stdcall MsiGetProductInfoW(LPCWSTR szProduct, LPCWSTR szAttribute, LPWSTR lpValueBuf, LPDWORD pcchValueBuf)
{
  int v4; // eax
  void *v9; // r12
  char v10; // r13
  DWORD v11; // ebx
  int v12; // ecx
  __int64 v13; // rax
  unsigned int v15; // r10d
  __int64 *v16; // r8
  _WORD *v17; // r9
  unsigned int v18; // edx
  __int64 v19; // rax
  UINT Info; // edi
  int v21; // eax
  DWORD v22; // ebx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  HANDLE v25; // rax
  HANDLE v26; // rax
  BOOL v27; // ebx
  BOOL v28; // ebx
  int v29; // [rsp+38h] [rbp-C8h]
  void *TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  LPVOID Value; // [rsp+70h] [rbp-90h] BYREF
  char v33; // [rsp+78h] [rbp-88h]
  HGLOBAL hMem; // [rsp+80h] [rbp-80h]
  int v35; // [rsp+88h] [rbp-78h]
  _BYTE v36[80]; // [rsp+90h] [rbp-70h] BYREF
  HGLOBAL v37; // [rsp+E0h] [rbp-20h]
  int v38; // [rsp+E8h] [rbp-18h]
  _BYTE v39[80]; // [rsp+F0h] [rbp-10h] BYREF

  v4 = dword_180306D40;
  Value = 0;
  v33 = 0;
  v9 = 0;
  v10 = 0;
  if ( dword_180306D40 == -1 )
  {
    TokenHandle = (void *)-1LL;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
    {
      if ( !SetThreadToken(0, 0) )
        ExitProcessIfNotClient();
    }
    else
    {
      TokenHandle = (void *)-1LL;
    }
    hObject = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &hObject) )
    {
      v27 = IsLocalSystemToken(hObject);
      CloseHandle(hObject);
      dword_180306D40 = v27;
    }
    else if ( g_dmDiagnosticMode )
    {
      DebugString(
        9,
        0,
        0,
        L"Could not determine if the process is running as local system or not.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    if ( TokenHandle != (void *)-1LL )
    {
      if ( !SetThreadToken(0, TokenHandle) )
        ExitProcessIfNotClient();
      CloseHandle(TokenHandle);
    }
    v4 = dword_180306D40;
  }
  if ( g_scServerContext != 2 && v4 == 1 )
  {
    EnterCriticalSection(&g_csImpersonationLock);
    v11 = g_dwImpersonationSlot;
    if ( g_dwImpersonationSlot == -1
      && (g_dwImpersonationSlot = TlsAlloc(), v11 = g_dwImpersonationSlot, g_dwImpersonationSlot == -1) )
    {
      LeaveCriticalSection(&g_csImpersonationLock);
    }
    else
    {
      LeaveCriticalSection(&g_csImpersonationLock);
      Value = TlsGetValue(v11);
      v9 = Value;
      if ( Value || !GetLastError() )
      {
        TlsSetValue(v11, (LPVOID)0xFFFFFFFF80000000LL);
        v10 = 1;
        v33 = 1;
      }
    }
  }
  v38 = 33;
  v37 = v39;
  if ( !szProduct || !szAttribute || lpValueBuf && !pcchValueBuf )
    goto LABEL_20;
  v35 = 39;
  hMem = v36;
  if ( lstrlenW(szProduct) != 38 )
  {
    if ( !DecomposeDescriptor(szProduct, 1, (unsigned __int16 *)hMem, 0, 0, 0, 0, 0) )
    {
LABEL_15:
      if ( v35 > 39 )
        GlobalFree(hMem);
      hMem = v36;
      v35 = 39;
      if ( v38 > 33 )
        GlobalFree(v37);
      v38 = 33;
      v37 = v39;
LABEL_20:
      CForbidTokenChangesDuringCall::~CForbidTokenChangesDuringCall(&Value);
      return 87;
    }
    szProduct = (LPCWSTR)hMem;
  }
  v12 = 0;
  while ( v12 < 38 )
  {
    v13 = v12++;
    if ( !szProduct[v13] )
      goto LABEL_15;
  }
  if ( *szProduct != 123 || szProduct[37] != 125 )
    goto LABEL_15;
  v15 = v38;
  v16 = qword_18026F6C0;
  v17 = v37;
  v18 = 0;
  while ( v16 < (__int64 *)L"Software\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData" )
  {
    if ( v18 >= v15 )
      goto LABEL_15;
    v19 = *(unsigned __int8 *)v16;
    v16 = (__int64 *)((char *)v16 + 1);
    *v17++ = szProduct[v19];
    ++v18;
  }
  if ( v18 >= v15 )
    goto LABEL_15;
  LOBYTE(v29) = 0;
  *v17 = 0;
  Info = GetInfo(v37, 0, 3, 1, szAttribute, lpValueBuf, pcchValueBuf, v29, -1);
  if ( v35 > 39 )
    GlobalFree(hMem);
  hMem = v36;
  v35 = 39;
  if ( v38 > 33 )
    GlobalFree(v37);
  v38 = 33;
  v37 = v39;
  v21 = dword_180306D40;
  if ( dword_180306D40 == -1 )
  {
    TokenHandle = (void *)-1LL;
    v25 = GetCurrentThread();
    if ( OpenThreadToken(v25, 4u, 1, &TokenHandle) )
    {
      if ( !SetThreadToken(0, 0) )
        ExitProcessIfNotClient();
    }
    else
    {
      TokenHandle = (void *)-1LL;
    }
    hObject = 0;
    v26 = GetCurrentProcess();
    if ( OpenProcessToken(v26, 8u, &hObject) )
    {
      v28 = IsLocalSystemToken(hObject);
      CloseHandle(hObject);
      dword_180306D40 = v28;
    }
    else if ( g_dmDiagnosticMode )
    {
      DebugString(
        9,
        0,
        0,
        L"Could not determine if the process is running as local system or not.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    if ( TokenHandle != (void *)-1LL )
    {
      if ( !SetThreadToken(0, TokenHandle) )
        ExitProcessIfNotClient();
      CloseHandle(TokenHandle);
    }
    v21 = dword_180306D40;
  }
  if ( v21 == 1 && g_scServerContext != 2 )
  {
    EnterCriticalSection(&g_csImpersonationLock);
    v22 = g_dwImpersonationSlot;
    LeaveCriticalSection(&g_csImpersonationLock);
    if ( v22 != -1 )
    {
      if ( v10 )
        TlsSetValue(v22, v9);
    }
  }
  return Info;
}

```

## disassembly

```asm
0x18001f190  push    rbp
0x18001f192  push    rbx
0x18001f193  push    rsi
0x18001f194  push    rdi
0x18001f195  push    r12
0x18001f197  push    r13
0x18001f199  push    r14
0x18001f19b  push    r15
0x18001f19d  lea     rbp, [rsp-58h]
0x18001f1a2  sub     rsp, 158h
0x18001f1a9  mov     rax, cs:__security_cookie
0x18001f1b0  xor     rax, rsp
0x18001f1b3  mov     [rbp+90h+var_50], rax
0x18001f1b7  mov     eax, cs:dword_180306D40
0x18001f1bd  xor     ebx, ebx
0x18001f1bf  mov     [rsp+190h+var_120], rbx
0x18001f1c4  mov     r15, r9
0x18001f1c7  mov     [rsp+190h+var_118], bl
0x18001f1cb  mov     r14, r8
0x18001f1ce  mov     rsi, rdx
0x18001f1d1  mov     rdi, rcx
0x18001f1d4  mov     r12d, ebx
0x18001f1d7  mov     r13b, bl
0x18001f1da  cmp     eax, 0FFFFFFFFh
0x18001f1dd  jz      loc_18001F43D
0x18001f1e3  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18001f1ea  jz      short loc_18001F250
0x18001f1ec  cmp     eax, 1
0x18001f1ef  jnz     short loc_18001F250
0x18001f1f1  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001f1f8  call    cs:__imp_EnterCriticalSection
0x18001f1fe  mov     ebx, cs:?g_dwImpersonationSlot@@3KA; ulong g_dwImpersonationSlot
0x18001f204  cmp     ebx, 0FFFFFFFFh
0x18001f207  jz      loc_18001F544
0x18001f20d  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001f214  call    cs:__imp_LeaveCriticalSection
0x18001f21a  mov     ecx, ebx; dwTlsIndex
0x18001f21c  call    cs:__imp_TlsGetValue
0x18001f222  mov     [rsp+190h+var_120], rax
0x18001f227  mov     r12, rax
0x18001f22a  test    rax, rax
0x18001f22d  jnz     short loc_18001F239
0x18001f22f  call    cs:__imp_GetLastError
0x18001f235  test    eax, eax
0x18001f237  jnz     short loc_18001F250
0x18001f239  mov     rdx, 0FFFFFFFF80000000h; lpTlsValue
0x18001f240  mov     ecx, ebx; dwTlsIndex
0x18001f242  call    cs:__imp_TlsSetValue
0x18001f248  mov     r13b, 1
0x18001f24b  mov     [rsp+190h+var_118], r13b
0x18001f250  xor     ebx, ebx
0x18001f252  mov     [rbp+90h+var_A8], 21h ; '!'
0x18001f259  lea     rax, [rbp+90h+var_A0]
0x18001f25d  mov     [rbp+90h+var_B0], rax
0x18001f261  test    rdi, rdi
0x18001f264  jz      short loc_18001F2E5
0x18001f266  test    rsi, rsi
0x18001f269  jz      short loc_18001F2E5
0x18001f26b  test    r14, r14
0x18001f26e  jnz     loc_18001F536
0x18001f274  lea     rax, [rbp+90h+var_100]
0x18001f278  mov     [rbp+90h+var_108], 27h ; '''
0x18001f27f  mov     rcx, rdi; lpString
0x18001f282  mov     [rbp+90h+hMem], rax
0x18001f286  call    cs:__imp_lstrlenW
0x18001f28c  cmp     eax, 26h ; '&'
0x18001f28f  jnz     loc_18001F658
0x18001f295  mov     ecx, ebx
0x18001f297  cmp     ecx, 26h ; '&'
0x18001f29a  jge     short loc_18001F2F9
0x18001f29c  movsxd  rax, ecx
0x18001f29f  inc     ecx
0x18001f2a1  cmp     [rdi+rax*2], bx
0x18001f2a5  jnz     short loc_18001F297
0x18001f2a7  cmp     [rbp+90h+var_108], 27h ; '''
0x18001f2ab  jle     short loc_18001F2B7
0x18001f2ad  mov     rcx, [rbp+90h+hMem]; hMem
0x18001f2b1  call    cs:__imp_GlobalFree
0x18001f2b7  cmp     [rbp+90h+var_A8], 21h ; '!'
0x18001f2bb  lea     rax, [rbp+90h+var_100]
0x18001f2bf  mov     [rbp+90h+hMem], rax
0x18001f2c3  mov     [rbp+90h+var_108], 27h ; '''
0x18001f2ca  jle     short loc_18001F2D6
0x18001f2cc  mov     rcx, [rbp+90h+var_B0]; hMem
0x18001f2d0  call    cs:__imp_GlobalFree
0x18001f2d6  lea     rax, [rbp+90h+var_A0]
0x18001f2da  mov     [rbp+90h+var_A8], 21h ; '!'
0x18001f2e1  mov     [rbp+90h+var_B0], rax
0x18001f2e5  lea     rcx, [rsp+190h+var_120]; this
0x18001f2ea  call    ??1CForbidTokenChangesDuringCall@@QEAA@XZ; CForbidTokenChangesDuringCall::~CForbidTokenChangesDuringCall(void)
0x18001f2ef  mov     eax, 57h ; 'W'
0x18001f2f4  jmp     loc_18001F40E
0x18001f2f9  cmp     word ptr [rdi], 7Bh ; '{'
0x18001f2fd  jnz     short loc_18001F2A7
0x18001f2ff  cmp     word ptr [rdi+4Ah], 7Dh ; '}'
0x18001f304  jnz     short loc_18001F2A7
0x18001f306  mov     r10d, [rbp+90h+var_A8]
0x18001f30a  lea     r8, qword_18026F6C0
0x18001f311  mov     r9, [rbp+90h+var_B0]
0x18001f315  mov     edx, ebx
0x18001f317  lea     rax, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001f31e  cmp     r8, rax
0x18001f321  jnb     short loc_18001F343
0x18001f323  cmp     edx, r10d
0x18001f326  jnb     loc_18001F2A7
0x18001f32c  movzx   eax, byte ptr [r8]
0x18001f330  inc     r8
0x18001f333  movzx   ecx, word ptr [rdi+rax*2]
0x18001f337  mov     [r9], cx
0x18001f33b  add     r9, 2
0x18001f33f  inc     edx
0x18001f341  jmp     short loc_18001F317
0x18001f343  cmp     edx, r10d
0x18001f346  jnb     loc_18001F2A7
0x18001f34c  mov     dword ptr [rsp+190h+var_150], 0FFFFFFFFh
0x18001f354  xor     edx, edx
0x18001f356  mov     byte ptr [rsp+190h+var_158], bl
0x18001f35a  mov     [r9], bx
0x18001f35e  mov     rcx, [rbp+90h+var_B0]
0x18001f362  mov     [rsp+190h+var_160], r15
0x18001f367  lea     r9d, [rdx+1]
0x18001f36b  lea     r8d, [rdx+3]
0x18001f36f  mov     [rsp+190h+var_168], r14
0x18001f374  mov     [rsp+190h+var_170], rsi
0x18001f379  call    ?GetInfo@@YAIPEBG0W4iaaAppAssignment@@W4ptPropertyType@@0PEAGPEAK_NW4tagINSTALLSTATE@@@Z; GetInfo(ushort const *,ushort const *,iaaAppAssignment,ptPropertyType,ushort const *,ushort *,ulong *,bool,tagINSTALLSTATE)
0x18001f37e  cmp     [rbp+90h+var_108], 27h ; '''
0x18001f382  mov     edi, eax
0x18001f384  jle     short loc_18001F390
0x18001f386  mov     rcx, [rbp+90h+hMem]; hMem
0x18001f38a  call    cs:__imp_GlobalFree
0x18001f390  cmp     [rbp+90h+var_A8], 21h ; '!'
0x18001f394  lea     rax, [rbp+90h+var_100]
0x18001f398  mov     [rbp+90h+hMem], rax
0x18001f39c  mov     [rbp+90h+var_108], 27h ; '''
0x18001f3a3  jg      loc_18001F42E
0x18001f3a9  lea     rax, [rbp+90h+var_A0]
0x18001f3ad  mov     [rbp+90h+var_A8], 21h ; '!'
0x18001f3b4  mov     [rbp+90h+var_B0], rax
0x18001f3b8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001f3bc  mov     eax, cs:dword_180306D40
0x18001f3c2  cmp     eax, esi
0x18001f3c4  jz      loc_18001F4C0
0x18001f3ca  cmp     eax, 1
0x18001f3cd  jnz     short loc_18001F40C
0x18001f3cf  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18001f3d6  jz      short loc_18001F40C
0x18001f3d8  lea     rsi, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csImpersonationLock
0x18001f3df  mov     rcx, rsi; lpCriticalSection
0x18001f3e2  call    cs:__imp_EnterCriticalSection
0x18001f3e8  mov     ebx, cs:?g_dwImpersonationSlot@@3KA; ulong g_dwImpersonationSlot
0x18001f3ee  mov     rcx, rsi; lpCriticalSection
0x18001f3f1  call    cs:__imp_LeaveCriticalSection
0x18001f3f7  cmp     ebx, 0FFFFFFFFh
0x18001f3fa  jz      short loc_18001F40C
0x18001f3fc  test    r13b, r13b
0x18001f3ff  jz      short loc_18001F40C
0x18001f401  mov     rdx, r12; lpTlsValue
0x18001f404  mov     ecx, ebx; dwTlsIndex
0x18001f406  call    cs:__imp_TlsSetValue
0x18001f40c  mov     eax, edi
0x18001f40e  mov     rcx, [rbp+90h+var_50]
0x18001f412  xor     rcx, rsp; StackCookie
0x18001f415  call    __security_check_cookie
0x18001f41a  add     rsp, 158h
0x18001f421  pop     r15
0x18001f423  pop     r14
0x18001f425  pop     r13
0x18001f427  pop     r12
0x18001f429  pop     rdi
0x18001f42a  pop     rsi
0x18001f42b  pop     rbx
0x18001f42c  pop     rbp
0x18001f42d  retn
0x18001f42e  mov     rcx, [rbp+90h+var_B0]; hMem
0x18001f432  call    cs:__imp_GlobalFree
0x18001f438  jmp     loc_18001F3A9
0x18001f43d  mov     [rsp+190h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18001f446  call    cs:__imp_GetCurrentThread
0x18001f44c  mov     edx, 4; DesiredAccess
0x18001f451  lea     r9, [rsp+190h+TokenHandle]; TokenHandle
0x18001f456  mov     rcx, rax; ThreadHandle
0x18001f459  lea     r8d, [rdx-3]; OpenAsSelf
0x18001f45d  call    cs:__imp_OpenThreadToken
0x18001f463  test    eax, eax
0x18001f465  jnz     loc_18001F5F5
0x18001f46b  mov     [rsp+190h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18001f474  mov     [rsp+190h+hObject], rbx
0x18001f479  call    cs:__imp_GetCurrentProcess
0x18001f47f  lea     r8, [rsp+190h+hObject]; TokenHandle
0x18001f484  mov     edx, 8; DesiredAccess
0x18001f489  mov     rcx, rax; ProcessHandle
0x18001f48c  call    cs:__imp_OpenProcessToken
0x18001f492  test    eax, eax
0x18001f494  jnz     loc_18001F56D
0x18001f49a  cmp     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x18001f4a0  jnz     loc_18001F611
0x18001f4a6  mov     rdx, [rsp+190h+TokenHandle]; Token
0x18001f4ab  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18001f4af  jnz     loc_18001F5B3
0x18001f4b5  mov     eax, cs:dword_180306D40
0x18001f4bb  jmp     loc_18001F1E3
0x18001f4c0  mov     [rsp+190h+TokenHandle], rsi
0x18001f4c5  call    cs:__imp_GetCurrentThread
0x18001f4cb  mov     edx, 4; DesiredAccess
0x18001f4d0  lea     r9, [rsp+190h+TokenHandle]; TokenHandle
0x18001f4d5  mov     rcx, rax; ThreadHandle
0x18001f4d8  lea     r8d, [rdx-3]; OpenAsSelf
0x18001f4dc  call    cs:__imp_OpenThreadToken
0x18001f4e2  test    eax, eax
0x18001f4e4  jnz     loc_18001F68E
0x18001f4ea  mov     [rsp+190h+TokenHandle], rsi
0x18001f4ef  mov     [rsp+190h+hObject], rbx
0x18001f4f4  call    cs:__imp_GetCurrentProcess
0x18001f4fa  lea     r8, [rsp+190h+hObject]; TokenHandle
0x18001f4ff  mov     edx, 8; DesiredAccess
0x18001f504  mov     rcx, rax; ProcessHandle
0x18001f507  call    cs:__imp_OpenProcessToken
0x18001f50d  test    eax, eax
0x18001f50f  jnz     short loc_18001F590
0x18001f511  cmp     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x18001f517  jnz     loc_18001F6AA
0x18001f51d  mov     rdx, [rsp+190h+TokenHandle]; Token
0x18001f522  cmp     rdx, rsi
0x18001f525  jnz     loc_18001F5D4
0x18001f52b  mov     eax, cs:dword_180306D40
0x18001f531  jmp     loc_18001F3CA
0x18001f536  test    r15, r15
0x18001f539  jnz     loc_18001F274
0x18001f53f  jmp     loc_18001F2E5
0x18001f544  call    cs:__imp_TlsAlloc
0x18001f54a  mov     cs:?g_dwImpersonationSlot@@3KA, eax; ulong g_dwImpersonationSlot
0x18001f550  mov     ebx, eax
0x18001f552  cmp     eax, 0FFFFFFFFh
0x18001f555  jnz     loc_18001F20D
0x18001f55b  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001f562  call    cs:__imp_LeaveCriticalSection
0x18001f568  jmp     loc_18001F250
0x18001f56d  mov     rcx, [rsp+190h+hObject]; void *
0x18001f572  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x18001f577  mov     rcx, [rsp+190h+hObject]; hObject
0x18001f57c  movzx   ebx, al
0x18001f57f  call    cs:__imp_CloseHandle
0x18001f585  mov     cs:dword_180306D40, ebx
0x18001f58b  jmp     loc_18001F4A6
0x18001f590  mov     rcx, [rsp+190h+hObject]; void *
0x18001f595  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x18001f59a  mov     rcx, [rsp+190h+hObject]; hObject
0x18001f59f  movzx   ebx, al
0x18001f5a2  call    cs:__imp_CloseHandle
0x18001f5a8  mov     cs:dword_180306D40, ebx
0x18001f5ae  jmp     loc_18001F51D
0x18001f5b3  xor     ecx, ecx; Thread
0x18001f5b5  call    cs:__imp_SetThreadToken
0x18001f5bb  test    eax, eax
0x18001f5bd  jnz     short loc_18001F5C4
0x18001f5bf  call    ExitProcessIfNotClient
0x18001f5c4  mov     rcx, [rsp+190h+TokenHandle]; hObject
0x18001f5c9  call    cs:__imp_CloseHandle
0x18001f5cf  jmp     loc_18001F4B5
0x18001f5d4  xor     ecx, ecx; Thread
0x18001f5d6  call    cs:__imp_SetThreadToken
0x18001f5dc  test    eax, eax
0x18001f5de  jnz     short loc_18001F5E5
0x18001f5e0  call    ExitProcessIfNotClient
0x18001f5e5  mov     rcx, [rsp+190h+TokenHandle]; hObject
0x18001f5ea  call    cs:__imp_CloseHandle
0x18001f5f0  jmp     loc_18001F52B
0x18001f5f5  xor     edx, edx; Token
0x18001f5f7  xor     ecx, ecx; Thread
0x18001f5f9  call    cs:__imp_SetThreadToken
0x18001f5ff  test    eax, eax
0x18001f601  jnz     loc_18001F474
0x18001f607  call    ExitProcessIfNotClient
0x18001f60c  jmp     loc_18001F474
0x18001f611  mov     [rsp+190h+var_138], rbx; void *
0x18001f616  lea     rax, aNull; "(NULL)"
0x18001f61d  mov     [rsp+190h+var_140], ebx; unsigned int
0x18001f621  lea     r9, aCouldNotDeterm_1; "Could not determine if the process is r"...
0x18001f628  mov     [rsp+190h+var_148], rax; unsigned __int16 *
0x18001f62d  xor     edx, edx; unsigned __int16
0x18001f62f  mov     [rsp+190h+var_150], rax; unsigned __int16 *
0x18001f634  xor     r8d, r8d; int
0x18001f637  mov     [rsp+190h+var_158], rax; unsigned __int16 *
0x18001f63c  mov     [rsp+190h+var_160], rax; unsigned __int16 *
0x18001f641  mov     [rsp+190h+var_168], rax; unsigned __int16 *
0x18001f646  lea     ecx, [rdx+9]; int
0x18001f649  mov     [rsp+190h+var_170], rax; unsigned __int16 *
0x18001f64e  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18001f653  jmp     loc_18001F4A6
0x18001f658  mov     r8, [rbp+90h+hMem]; unsigned __int16 *
0x18001f65c  xor     r9d, r9d; unsigned __int16 *
0x18001f65f  mov     [rsp+190h+var_158], rbx; bool *
0x18001f664  mov     dl, 1; bool
0x18001f666  mov     [rsp+190h+var_160], rbx; unsigned int *
0x18001f66b  mov     rcx, rdi; unsigned __int16 *
0x18001f66e  mov     [rsp+190h+var_168], rbx; unsigned int *
0x18001f673  mov     [rsp+190h+var_170], rbx; unsigned __int16 *
0x18001f678  call    ?DecomposeDescriptor@@YAHPEBG_NPEAG22PEAK3PEA_N@Z; DecomposeDescriptor(ushort const *,bool,ushort *,ushort *,ushort *,ulong *,ulong *,bool *)
0x18001f67d  test    eax, eax
0x18001f67f  jz      loc_18001F2A7
  ... truncated ...
```
