# RecoveryRetrieveSupplementalCredential

- ea: `0x1800382f4`
- end: `0x1800385f3`
- name: `RecoveryRetrieveSupplementalCredential`
- size: `767`
- prototype: `__int64 __fastcall(__int64, BYTE **, DWORD *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180036ac8`
- `0x180037ba8`

## callees

- `0x180007f10`
- `0x18000a5d0`
- `0x180013bec`
- `0x18001c9c0`
- `0x18001d810`
- `0x180036a6c`
- `0x180036a94`
- `0x1800376a0`
- `0x1800382f4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003843a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003843a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800384c6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038535`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800384c6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038535`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038489`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038489`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180038425`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180038425`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003858c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003858c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180038406`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180038406`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800385a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800385a0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800384f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800384f3`

## string_xrefs

- `0x1800383ee`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`

## pseudocode

```c
__int64 __fastcall RecoveryRetrieveSupplementalCredential(__int64 a1, BYTE **a2, DWORD *a3)
{
  BYTE *v3; // rdi
  __int64 v7; // r9
  __int64 v8; // rcx
  unsigned int v9; // ebx
  HANDLE CurrentThread; // rax
  DWORD v11; // eax
  DWORD v12; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  int v16; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v20; // [rsp+58h] [rbp-A8h] BYREF
  const WCHAR *v21; // [rsp+60h] [rbp-A0h] BYREF
  void **p_TokenHandle; // [rsp+68h] [rbp-98h] BYREF
  HKEY *p_hKey; // [rsp+70h] [rbp-90h] BYREF
  HKEY *p_phkResult; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v25[4]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SubKey[264]; // [rsp+A0h] [rbp-60h] BYREF

  v16 = 0;
  v21 = L"C80ED86A-0D28-40dc-B379-BB594E14EA1B";
  v3 = 0;
  v20 = -2147483646;
  v25[0] = &v16;
  phkResult = 0;
  v25[1] = &v20;
  hKey = 0;
  v25[2] = &v21;
  Type = 0;
  p_phkResult = &phkResult;
  p_hKey = &hKey;
  p_TokenHandle = &TokenHandle;
  cbData = 0;
  TokenHandle = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 26, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids);
  if ( !(unsigned int)GetTextualSid(a1, SubKey, 261) )
  {
    v7 = 1692;
LABEL_6:
    v8 = 8;
    v9 = 8;
LABEL_7:
    DebugTraceError(v8, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", v7);
    goto LABEL_26;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
    TokenHandle = 0;
  RevertToSelf();
  v11 = OpenSupplementalCredentialStore(0x20019u, &hKey);
  v9 = v11;
  if ( v11 )
  {
    v7 = 1715;
LABEL_12:
    v8 = v11;
    goto LABEL_7;
  }
  v16 = 1;
  v11 = RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &phkResult);
  v9 = v11;
  if ( v11 )
  {
    v7 = 1732;
    goto LABEL_12;
  }
  v11 = RegQueryValueExW(phkResult, &Class, 0, &Type, 0, &cbData);
  v9 = v11;
  if ( v11 && v11 != 234 )
  {
    v7 = 1748;
    goto LABEL_12;
  }
  v3 = (BYTE *)LocalAlloc(0x40u, cbData);
  if ( !v3 )
  {
    v7 = 1757;
    goto LABEL_6;
  }
  v11 = RegQueryValueExW(phkResult, &Class, 0, &Type, v3, &cbData);
  v9 = v11;
  if ( v11 && v11 != 234 )
  {
    v7 = 1772;
    goto LABEL_12;
  }
  if ( Type != 3 )
  {
    v9 = 13;
    v7 = 1780;
    v8 = 13;
    goto LABEL_7;
  }
  v12 = cbData;
  *a2 = v3;
  v3 = 0;
  v9 = 0;
  *a3 = v12;
LABEL_26:
  if ( TokenHandle )
    SetThreadToken(0, TokenHandle);
  if ( v3 )
    LocalFree(v3);
  ScopedCloseHandle::~ScopedCloseHandle((ScopedCloseHandle *)&p_TokenHandle);
  ScopedRegClose::~ScopedRegClose((ScopedRegClose *)&p_hKey);
  ScopedRegClose::~ScopedRegClose((ScopedRegClose *)&p_phkResult);
  ScopedRegUnload::~ScopedRegUnload((ScopedRegUnload *)v25);
  return v9;
}

```

## disassembly

```asm
0x1800382f4  push    rbp
0x1800382f6  push    rbx
0x1800382f7  push    rsi
0x1800382f8  push    rdi
0x1800382f9  push    r14
0x1800382fb  lea     rbp, [rsp-1C0h]
0x180038303  sub     rsp, 2C0h
0x18003830a  mov     rax, cs:__security_cookie
0x180038311  xor     rax, rsp
0x180038314  mov     [rbp+1E0h+var_30], rax
0x18003831b  lea     rax, aC80ed86a0d2840; "C80ED86A-0D28-40dc-B379-BB594E14EA1B"
0x180038322  mov     [rsp+2E0h+var_2A8], 0
0x18003832a  mov     [rsp+2E0h+var_280], rax
0x18003832f  xor     edi, edi
0x180038331  lea     rax, [rsp+2E0h+var_2A8]
0x180038336  mov     [rsp+2E0h+var_288], 0FFFFFFFF80000002h
0x18003833f  mov     [rbp+1E0h+var_260], rax
0x180038343  mov     r14, r8
0x180038346  lea     rax, [rsp+2E0h+var_288]
0x18003834b  mov     [rsp+2E0h+var_2A0], 0
0x180038354  mov     [rbp+1E0h+var_258], rax
0x180038358  mov     rsi, rdx
0x18003835b  lea     rax, [rsp+2E0h+var_280]
0x180038360  mov     [rsp+2E0h+hKey], 0
0x180038369  mov     [rbp+1E0h+var_250], rax
0x18003836d  mov     rbx, rcx
0x180038370  lea     rax, [rsp+2E0h+var_2A0]
0x180038375  mov     [rsp+2E0h+Type], 0
0x18003837d  mov     [rsp+2E0h+var_268], rax
0x180038382  lea     rax, [rsp+2E0h+hKey]
0x180038387  mov     [rsp+2E0h+var_270], rax
0x18003838c  lea     rax, [rsp+2E0h+TokenHandle]
0x180038391  mov     [rsp+2E0h+var_278], rax
0x180038396  mov     [rsp+2E0h+cbData], edi
0x18003839a  mov     [rsp+2E0h+TokenHandle], rdi
0x18003839f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800383a6  lea     rax, WPP_GLOBAL_Control
0x1800383ad  cmp     rcx, rax
0x1800383b0  jz      short loc_1800383CB
0x1800383b2  test    byte ptr [rcx+1Ch], 4
0x1800383b6  jz      short loc_1800383CB
0x1800383b8  mov     rcx, [rcx+10h]
0x1800383bc  lea     edx, [rdi+1Ah]
0x1800383bf  lea     r8, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids
0x1800383c6  call    WPP_SF_
0x1800383cb  mov     r8d, 105h
0x1800383d1  lea     rdx, [rbp+1E0h+SubKey]
0x1800383d5  mov     rcx, rbx
0x1800383d8  call    GetTextualSid
0x1800383dd  test    eax, eax
0x1800383df  jnz     short loc_180038406
0x1800383e1  mov     r9d, 69Ch
0x1800383e7  mov     ecx, 8
0x1800383ec  mov     ebx, ecx
0x1800383ee  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800383f5  lea     rdx, aDwerror; "dwError"
0x1800383fc  call    DebugTraceError
0x180038401  jmp     loc_180038580
0x180038406  call    cs:__imp_GetCurrentThread
0x18003840d  nop     dword ptr [rax+rax+00h]
0x180038412  lea     r9, [rsp+2E0h+TokenHandle]; TokenHandle
0x180038417  mov     edx, 2000Ch; DesiredAccess
0x18003841c  mov     rcx, rax; ThreadHandle
0x18003841f  mov     r8d, 1; OpenAsSelf
0x180038425  call    cs:__imp_OpenThreadToken
0x18003842c  nop     dword ptr [rax+rax+00h]
0x180038431  test    eax, eax
0x180038433  jnz     short loc_18003843A
0x180038435  mov     [rsp+2E0h+TokenHandle], rdi
0x18003843a  call    cs:__imp_RevertToSelf
0x180038441  nop     dword ptr [rax+rax+00h]
0x180038446  lea     rdx, [rsp+2E0h+hKey]; phkResult
0x18003844b  mov     ecx, 20019h; samDesired
0x180038450  call    ?OpenSupplementalCredentialStore@@YAKKPEAPEAUHKEY__@@@Z; OpenSupplementalCredentialStore(ulong,HKEY__ * *)
0x180038455  mov     ebx, eax
0x180038457  test    eax, eax
0x180038459  jz      short loc_180038465
0x18003845b  mov     r9d, 6B3h
0x180038461  mov     ecx, eax
0x180038463  jmp     short loc_1800383EE
0x180038465  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18003846a  lea     rax, [rsp+2E0h+var_2A0]
0x18003846f  mov     r9d, 20019h; samDesired
0x180038475  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18003847a  xor     r8d, r8d; ulOptions
0x18003847d  mov     [rsp+2E0h+var_2A8], 1
0x180038485  lea     rdx, [rbp+1E0h+SubKey]; lpSubKey
0x180038489  call    cs:__imp_RegOpenKeyExW
0x180038490  nop     dword ptr [rax+rax+00h]
0x180038495  mov     ebx, eax
0x180038497  test    eax, eax
0x180038499  jz      short loc_1800384A3
0x18003849b  mov     r9d, 6C4h
0x1800384a1  jmp     short loc_180038461
0x1800384a3  mov     rcx, [rsp+2E0h+var_2A0]; hKey
0x1800384a8  lea     rax, [rsp+2E0h+cbData]
0x1800384ad  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x1800384b2  lea     r9, [rsp+2E0h+Type]; lpType
0x1800384b7  xor     r8d, r8d; lpReserved
0x1800384ba  mov     [rsp+2E0h+phkResult], rdi; lpData
0x1800384bf  lea     rdx, Class; lpValueName
0x1800384c6  call    cs:__imp_RegQueryValueExW
0x1800384cd  nop     dword ptr [rax+rax+00h]
0x1800384d2  mov     ebx, eax
0x1800384d4  test    eax, eax
0x1800384d6  jz      short loc_1800384EA
0x1800384d8  cmp     eax, 0EAh
0x1800384dd  jz      short loc_1800384EA
0x1800384df  mov     r9d, 6D4h
0x1800384e5  jmp     loc_180038461
0x1800384ea  mov     edx, [rsp+2E0h+cbData]; uBytes
0x1800384ee  mov     ecx, 40h ; '@'; uFlags
0x1800384f3  call    cs:__imp_LocalAlloc
0x1800384fa  nop     dword ptr [rax+rax+00h]
0x1800384ff  mov     rdi, rax
0x180038502  test    rax, rax
0x180038505  jnz     short loc_180038512
0x180038507  mov     r9d, 6DDh
0x18003850d  jmp     loc_1800383E7
0x180038512  mov     rcx, [rsp+2E0h+var_2A0]; hKey
0x180038517  lea     rax, [rsp+2E0h+cbData]
0x18003851c  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x180038521  lea     r9, [rsp+2E0h+Type]; lpType
0x180038526  xor     r8d, r8d; lpReserved
0x180038529  mov     [rsp+2E0h+phkResult], rdi; lpData
0x18003852e  lea     rdx, Class; lpValueName
0x180038535  call    cs:__imp_RegQueryValueExW
0x18003853c  nop     dword ptr [rax+rax+00h]
0x180038541  mov     ebx, eax
0x180038543  test    eax, eax
0x180038545  jz      short loc_180038559
0x180038547  cmp     eax, 0EAh
0x18003854c  jz      short loc_180038559
0x18003854e  mov     r9d, 6ECh
0x180038554  jmp     loc_180038461
0x180038559  cmp     [rsp+2E0h+Type], 3
0x18003855e  jz      short loc_180038572
0x180038560  mov     ebx, 0Dh
0x180038565  mov     r9d, 6F4h
0x18003856b  mov     ecx, ebx
0x18003856d  jmp     loc_1800383EE
0x180038572  mov     eax, [rsp+2E0h+cbData]
0x180038576  mov     [rsi], rdi
0x180038579  xor     edi, edi
0x18003857b  xor     ebx, ebx
0x18003857d  mov     [r14], eax
0x180038580  mov     rdx, [rsp+2E0h+TokenHandle]; Token
0x180038585  test    rdx, rdx
0x180038588  jz      short loc_180038598
0x18003858a  xor     ecx, ecx; Thread
0x18003858c  call    cs:__imp_SetThreadToken
0x180038593  nop     dword ptr [rax+rax+00h]
0x180038598  test    rdi, rdi
0x18003859b  jz      short loc_1800385AC
0x18003859d  mov     rcx, rdi; hMem
0x1800385a0  call    cs:__imp_LocalFree
0x1800385a7  nop     dword ptr [rax+rax+00h]
0x1800385ac  lea     rcx, [rsp+2E0h+var_278]; this
0x1800385b1  call    ??1ScopedCloseHandle@@QEAA@XZ; ScopedCloseHandle::~ScopedCloseHandle(void)
0x1800385b6  lea     rcx, [rsp+2E0h+var_270]; this
0x1800385bb  call    ??1ScopedRegClose@@QEAA@XZ; ScopedRegClose::~ScopedRegClose(void)
0x1800385c0  lea     rcx, [rsp+2E0h+var_268]; this
0x1800385c5  call    ??1ScopedRegClose@@QEAA@XZ; ScopedRegClose::~ScopedRegClose(void)
0x1800385ca  lea     rcx, [rbp+1E0h+var_260]; this
0x1800385ce  call    ??1ScopedRegUnload@@QEAA@XZ; ScopedRegUnload::~ScopedRegUnload(void)
0x1800385d3  mov     eax, ebx
0x1800385d5  mov     rcx, [rbp+1E0h+var_30]
0x1800385dc  xor     rcx, rsp; StackCookie
0x1800385df  call    __security_check_cookie
0x1800385e4  add     rsp, 2C0h
0x1800385eb  pop     r14
0x1800385ed  pop     rdi
0x1800385ee  pop     rsi
0x1800385ef  pop     rbx
0x1800385f0  pop     rbp
0x1800385f1  retn
```
