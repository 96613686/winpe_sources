# RecoverySetSupplementalCredential

- ea: `0x1800385fc`
- end: `0x18003886b`
- name: `RecoverySetSupplementalCredential`
- size: `623`
- prototype: `__int64 __fastcall(__int64, const BYTE *, DWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180036dc0`

## callees

- `0x180007f10`
- `0x18000a5d0`
- `0x180013bec`
- `0x18001c9c0`
- `0x18001d810`
- `0x180036a6c`
- `0x180036a94`
- `0x1800376a0`
- `0x1800385fc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180038740`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180038740`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800387b3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800387b3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800387eb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800387eb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180038727`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180038727`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180038816`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180038816`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180038708`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180038708`

## string_xrefs

- `0x1800386f7`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`

## pseudocode

```c
__int64 __fastcall RecoverySetSupplementalCredential(__int64 a1, const BYTE *a2, DWORD a3)
{
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // rcx
  HANDLE CurrentThread; // rax
  DWORD v10; // eax
  int v12; // [rsp+50h] [rbp-B0h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  __int64 v17; // [rsp+78h] [rbp-88h] BYREF
  const WCHAR *v18; // [rsp+80h] [rbp-80h] BYREF
  void **p_TokenHandle; // [rsp+88h] [rbp-78h] BYREF
  HKEY *p_hKey; // [rsp+90h] [rbp-70h] BYREF
  HKEY *p_phkResult; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v22[4]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR SubKey[264]; // [rsp+C0h] [rbp-40h] BYREF

  v12 = 0;
  v18 = L"C80ED86A-0D28-40dc-B379-BB594E14EA1B";
  v17 = -2147483646;
  v22[0] = &v12;
  phkResult = 0;
  v22[1] = &v17;
  hKey = 0;
  v22[2] = &v18;
  p_phkResult = &phkResult;
  p_hKey = &hKey;
  p_TokenHandle = &TokenHandle;
  dwDisposition = 0;
  TokenHandle = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 25, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids);
  if ( !(unsigned int)GetTextualSid(a1, SubKey, 261) )
  {
    v6 = 8;
    v7 = 1579;
    v8 = 8;
LABEL_6:
    DebugTraceError(v8, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", v7);
    goto LABEL_17;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
    TokenHandle = 0;
  RevertToSelf();
  v10 = OpenSupplementalCredentialStore(0x20006u, &hKey);
  v6 = v10;
  if ( v10 )
  {
    v7 = 1602;
LABEL_11:
    v8 = v10;
    goto LABEL_6;
  }
  v12 = 1;
  v10 = RegCreateKeyExW(hKey, SubKey, 0, (LPWSTR)&Class, 0, 0x20006u, 0, &phkResult, &dwDisposition);
  v6 = v10;
  if ( v10 )
  {
    v7 = 1623;
    goto LABEL_11;
  }
  v10 = RegSetValueExW(phkResult, &Class, 0, 3u, a2, a3);
  v6 = v10;
  if ( v10 )
  {
    v7 = 1636;
    goto LABEL_11;
  }
  v6 = 0;
LABEL_17:
  if ( TokenHandle )
    SetThreadToken(0, TokenHandle);
  ScopedCloseHandle::~ScopedCloseHandle((ScopedCloseHandle *)&p_TokenHandle);
  ScopedRegClose::~ScopedRegClose((ScopedRegClose *)&p_hKey);
  ScopedRegClose::~ScopedRegClose((ScopedRegClose *)&p_phkResult);
  ScopedRegUnload::~ScopedRegUnload((ScopedRegUnload *)v22);
  return v6;
}

```

## disassembly

```asm
0x1800385fc  mov     [rsp-8+arg_18], rbx
0x180038601  push    rbp
0x180038602  push    rsi
0x180038603  push    rdi
0x180038604  lea     rbp, [rsp-1E0h]
0x18003860c  sub     rsp, 2E0h
0x180038613  mov     rax, cs:__security_cookie
0x18003861a  xor     rax, rsp
0x18003861d  mov     [rbp+1F0h+var_20], rax
0x180038624  lea     rax, aC80ed86a0d2840; "C80ED86A-0D28-40dc-B379-BB594E14EA1B"
0x18003862b  mov     [rsp+2F0h+var_2A0], 0
0x180038633  mov     [rbp+1F0h+var_270], rax
0x180038637  mov     esi, r8d
0x18003863a  lea     rax, [rsp+2F0h+var_2A0]
0x18003863f  mov     [rsp+2F0h+var_278], 0FFFFFFFF80000002h
0x180038648  mov     [rbp+1F0h+var_250], rax
0x18003864c  mov     rdi, rdx
0x18003864f  lea     rax, [rsp+2F0h+var_278]
0x180038654  mov     [rsp+2F0h+var_280], 0
0x18003865d  mov     [rbp+1F0h+var_248], rax
0x180038661  mov     rbx, rcx
0x180038664  lea     rax, [rbp+1F0h+var_270]
0x180038668  mov     [rsp+2F0h+hKey], 0
0x180038671  mov     [rbp+1F0h+var_240], rax
0x180038675  lea     rax, [rsp+2F0h+var_280]
0x18003867a  mov     [rbp+1F0h+var_258], rax
0x18003867e  lea     rax, [rsp+2F0h+hKey]
0x180038683  mov     [rbp+1F0h+var_260], rax
0x180038687  lea     rax, [rsp+2F0h+TokenHandle]
0x18003868c  mov     [rbp+1F0h+var_268], rax
0x180038690  mov     [rsp+2F0h+dwDisposition], 0
0x180038698  mov     [rsp+2F0h+TokenHandle], 0
0x1800386a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800386a8  lea     rax, WPP_GLOBAL_Control
0x1800386af  cmp     rcx, rax
0x1800386b2  jz      short loc_1800386CF
0x1800386b4  test    byte ptr [rcx+1Ch], 4
0x1800386b8  jz      short loc_1800386CF
0x1800386ba  mov     rcx, [rcx+10h]
0x1800386be  lea     r8, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids
0x1800386c5  mov     edx, 19h
0x1800386ca  call    WPP_SF_
0x1800386cf  mov     r8d, 105h
0x1800386d5  lea     rdx, [rbp+1F0h+SubKey]
0x1800386d9  mov     rcx, rbx
0x1800386dc  call    GetTextualSid
0x1800386e1  test    eax, eax
0x1800386e3  jnz     short loc_180038708
0x1800386e5  lea     ebx, [rax+8]
0x1800386e8  mov     r9d, 62Bh
0x1800386ee  mov     ecx, ebx
0x1800386f0  lea     rdx, aDwerror; "dwError"
0x1800386f7  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800386fe  call    DebugTraceError
0x180038703  jmp     loc_18003880A
0x180038708  call    cs:__imp_GetCurrentThread
0x18003870f  nop     dword ptr [rax+rax+00h]
0x180038714  lea     r9, [rsp+2F0h+TokenHandle]; TokenHandle
0x180038719  mov     edx, 2000Ch; DesiredAccess
0x18003871e  mov     rcx, rax; ThreadHandle
0x180038721  mov     r8d, 1; OpenAsSelf
0x180038727  call    cs:__imp_OpenThreadToken
0x18003872e  nop     dword ptr [rax+rax+00h]
0x180038733  test    eax, eax
0x180038735  jnz     short loc_180038740
0x180038737  mov     [rsp+2F0h+TokenHandle], 0
0x180038740  call    cs:__imp_RevertToSelf
0x180038747  nop     dword ptr [rax+rax+00h]
0x18003874c  lea     rdx, [rsp+2F0h+hKey]; phkResult
0x180038751  mov     ecx, 20006h; samDesired
0x180038756  call    ?OpenSupplementalCredentialStore@@YAKKPEAPEAUHKEY__@@@Z; OpenSupplementalCredentialStore(ulong,HKEY__ * *)
0x18003875b  mov     ebx, eax
0x18003875d  test    eax, eax
0x18003875f  jz      short loc_18003876B
0x180038761  mov     r9d, 642h
0x180038767  mov     ecx, eax
0x180038769  jmp     short loc_1800386F0
0x18003876b  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180038770  lea     rax, [rsp+2F0h+dwDisposition]
0x180038775  mov     [rsp+2F0h+lpdwDisposition], rax; lpdwDisposition
0x18003877a  lea     r9, Class; lpClass
0x180038781  lea     rax, [rsp+2F0h+var_280]
0x180038786  mov     [rsp+2F0h+var_2A0], 1
0x18003878e  mov     [rsp+2F0h+phkResult], rax; phkResult
0x180038793  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x180038797  mov     [rsp+2F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800387a0  xor     r8d, r8d; Reserved
0x1800387a3  mov     [rsp+2F0h+samDesired], 20006h; samDesired
0x1800387ab  mov     [rsp+2F0h+dwOptions], 0; dwOptions
0x1800387b3  call    cs:__imp_RegCreateKeyExW
0x1800387ba  nop     dword ptr [rax+rax+00h]
0x1800387bf  mov     ebx, eax
0x1800387c1  test    eax, eax
0x1800387c3  jz      short loc_1800387CD
0x1800387c5  mov     r9d, 657h
0x1800387cb  jmp     short loc_180038767
0x1800387cd  mov     rcx, [rsp+2F0h+var_280]; hKey
0x1800387d2  lea     rdx, Class; lpValueName
0x1800387d9  mov     [rsp+2F0h+samDesired], esi; cbData
0x1800387dd  mov     r9d, 3; dwType
0x1800387e3  xor     r8d, r8d; Reserved
0x1800387e6  mov     qword ptr [rsp+2F0h+dwOptions], rdi; lpData
0x1800387eb  call    cs:__imp_RegSetValueExW
0x1800387f2  nop     dword ptr [rax+rax+00h]
0x1800387f7  mov     ebx, eax
0x1800387f9  test    eax, eax
0x1800387fb  jz      short loc_180038808
0x1800387fd  mov     r9d, 664h
0x180038803  jmp     loc_180038767
0x180038808  xor     ebx, ebx
0x18003880a  mov     rdx, [rsp+2F0h+TokenHandle]; Token
0x18003880f  test    rdx, rdx
0x180038812  jz      short loc_180038822
0x180038814  xor     ecx, ecx; Thread
0x180038816  call    cs:__imp_SetThreadToken
0x18003881d  nop     dword ptr [rax+rax+00h]
0x180038822  lea     rcx, [rbp+1F0h+var_268]; this
0x180038826  call    ??1ScopedCloseHandle@@QEAA@XZ; ScopedCloseHandle::~ScopedCloseHandle(void)
0x18003882b  lea     rcx, [rbp+1F0h+var_260]; this
0x18003882f  call    ??1ScopedRegClose@@QEAA@XZ; ScopedRegClose::~ScopedRegClose(void)
0x180038834  lea     rcx, [rbp+1F0h+var_258]; this
0x180038838  call    ??1ScopedRegClose@@QEAA@XZ; ScopedRegClose::~ScopedRegClose(void)
0x18003883d  lea     rcx, [rbp+1F0h+var_250]; this
0x180038841  call    ??1ScopedRegUnload@@QEAA@XZ; ScopedRegUnload::~ScopedRegUnload(void)
0x180038846  mov     eax, ebx
0x180038848  mov     rcx, [rbp+1F0h+var_20]
0x18003884f  xor     rcx, rsp; StackCookie
0x180038852  call    __security_check_cookie
0x180038857  mov     rbx, [rsp+2F0h+arg_18]
0x18003885f  add     rsp, 2E0h
0x180038866  pop     rdi
0x180038867  pop     rsi
0x180038868  pop     rbp
0x180038869  retn
```
