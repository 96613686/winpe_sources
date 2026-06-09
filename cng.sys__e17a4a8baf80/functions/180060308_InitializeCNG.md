# InitializeCNG

- ea: `0x180060308`
- end: `0x1800604ce`
- name: `InitializeCNG`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180067098`

## callees

- `0x18001155c`
- `0x18002eb64`
- `0x180060308`
- `0x1800605e4`
- `0x180071a50`
- `0x180073d7c`
- `0x180076828`
- `0x18007e088`
- `0x18008b6b4`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x1800603ea`
- `ntoskrnl!ExInitializeResourceLite` at `0x1800603ea`
- `ntoskrnl!KeBugCheck` at `0x1800604a6`
- `ntoskrnl!KeBugCheck` at `0x1800604a6`
- `HAL!KeQueryPerformanceCounter` at `0x180060433`
- `HAL!KeQueryPerformanceCounter` at `0x18006045e`
- `HAL!KeQueryPerformanceCounter` at `0x180060433`
- `HAL!KeQueryPerformanceCounter` at `0x18006045e`

## string_xrefs

- `0x18006036d`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180060391`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\init.c`
- `0x18006048c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\init.c`

## pseudocode

```c
__int64 InitializeCNG()
{
  char TrustedEnvironment; // al
  int v1; // eax
  unsigned int v2; // ebx
  __int64 v3; // r9
  __int64 v4; // rcx
  int v5; // eax
  __int64 v6; // rdx
  char v7; // al
  LARGE_INTEGER v8; // rbx
  int v9; // edi
  char v10; // al
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+30h] [rbp+8h] BYREF

  PerformanceFrequency.QuadPart = 1;
  if ( _InterlockedCompareExchange(&dword_1800D2420, 1, 0) )
    return 0;
  TrustedEnvironment = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    TrustedEnvironment = GetTrustedEnvironment();
  if ( (TrustedEnvironment & 2) != 0 )
  {
LABEL_18:
    if ( g_fSelftest )
    {
      v7 = g_TrustedEnvironment;
      v8.QuadPart = 0;
      if ( !g_TrustedEnvironment )
        v7 = GetTrustedEnvironment();
      if ( (v7 & 2) == 0 )
        v8 = KeQueryPerformanceCounter(&PerformanceFrequency);
      v9 = AlgorithmCheck();
      v10 = g_TrustedEnvironment;
      if ( !g_TrustedEnvironment )
        v10 = GetTrustedEnvironment();
      if ( (v10 & 2) == 0 )
        g_selftestDuration = (unsigned __int64)(1000000 * (*(_QWORD *)&KeQueryPerformanceCounter(0) - v8.QuadPart))
                           / PerformanceFrequency.QuadPart;
      if ( v9 < 0 )
      {
        DebugTraceError(
          (unsigned int)v9,
          "ntStatus",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\init.c",
          154);
        KeBugCheck(0x123u);
      }
    }
    g_fLoadCNGDone = 1;
    return 0;
  }
  if ( g_fLoaderInitialized )
  {
LABEL_10:
    v5 = InitializeConfig();
    v2 = v5;
    if ( v5 < 0 )
    {
      v3 = 97;
LABEL_12:
      v4 = (unsigned int)v5;
      goto LABEL_8;
    }
    v5 = InitializeSystemPreferredCache();
    v2 = v5;
    if ( v5 < 0 )
    {
      v3 = 105;
      goto LABEL_12;
    }
    v5 = TlsInitializeDefaultAlgorithms();
    v2 = v5;
    if ( v5 < 0 )
    {
      v3 = 113;
      goto LABEL_12;
    }
    ExInitializeResourceLite(&Resource);
    McGenEventRegister_EtwRegister(ETW_LOG_CNG_PROVIDER, v6, ETW_LOG_CNG_PROVIDER_Context, ETW_LOG_CNG_PROVIDER_Context);
    goto LABEL_18;
  }
  g_pLoadedProviderList = 0;
  v1 = InitializeLoaderLock();
  v2 = v1;
  if ( v1 >= 0 )
  {
    g_fLoaderInitialized = 1;
    goto LABEL_10;
  }
  DebugTraceError((unsigned int)v1, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", 1964);
  v3 = 89;
  v4 = v2;
LABEL_8:
  DebugTraceError(v4, "ntStatus", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\init.c", v3);
  return v2;
}

```

## disassembly

```asm
0x180060308  mov     [rsp+arg_8], rbx
0x18006030d  mov     [rsp+arg_10], rbp
0x180060312  push    rdi
0x180060313  sub     rsp, 20h
0x180060317  mov     ebp, 1
0x18006031c  xor     eax, eax
0x18006031e  mov     qword ptr [rsp+28h+PerformanceFrequency], rbp
0x180060323  lock cmpxchg cs:dword_1800D2420, ebp
0x18006032b  jnz     loc_1800604B9
0x180060331  mov     eax, cs:g_TrustedEnvironment
0x180060337  test    eax, eax
0x180060339  jnz     short loc_180060340
0x18006033b  call    GetTrustedEnvironment
0x180060340  test    al, 2
0x180060342  jnz     loc_18006040C
0x180060348  cmp     cs:g_fLoaderInitialized, 0
0x18006034f  jnz     short loc_1800603A8
0x180060351  mov     cs:g_pLoadedProviderList, 0
0x18006035c  call    _InitializeLoaderLock
0x180060361  mov     ebx, eax
0x180060363  test    eax, eax
0x180060365  jns     short loc_1800603A2
0x180060367  mov     r9d, 7ACh
0x18006036d  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180060374  lea     rdx, aSresult; "sResult"
0x18006037b  mov     ecx, eax
0x18006037d  call    DebugTraceError
0x180060382  mov     r9d, 59h ; 'Y'
0x180060388  mov     ecx, ebx
0x18006038a  lea     rdx, aNtstatus; "ntStatus"
0x180060391  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180060398  call    DebugTraceError
0x18006039d  jmp     loc_1800604BB
0x1800603a2  mov     cs:g_fLoaderInitialized, ebp
0x1800603a8  call    InitializeConfig
0x1800603ad  mov     ebx, eax
0x1800603af  test    eax, eax
0x1800603b1  jns     short loc_1800603BD
0x1800603b3  mov     r9d, 61h ; 'a'
0x1800603b9  mov     ecx, eax
0x1800603bb  jmp     short loc_18006038A
0x1800603bd  call    InitializeSystemPreferredCache
0x1800603c2  mov     ebx, eax
0x1800603c4  test    eax, eax
0x1800603c6  jns     short loc_1800603D0
0x1800603c8  mov     r9d, 69h ; 'i'
0x1800603ce  jmp     short loc_1800603B9
0x1800603d0  call    TlsInitializeDefaultAlgorithms
0x1800603d5  mov     ebx, eax
0x1800603d7  test    eax, eax
0x1800603d9  jns     short loc_1800603E3
0x1800603db  mov     r9d, 71h ; 'q'
0x1800603e1  jmp     short loc_1800603B9
0x1800603e3  lea     rcx, Resource; Resource
0x1800603ea  call    cs:__imp_ExInitializeResourceLite
0x1800603f1  nop     dword ptr [rax+rax+00h]
0x1800603f6  lea     r8, ETW_LOG_CNG_PROVIDER_Context
0x1800603fd  mov     r9, r8
0x180060400  lea     rcx, ETW_LOG_CNG_PROVIDER
0x180060407  call    McGenEventRegister_EtwRegister
0x18006040c  cmp     cs:g_fSelftest, 0
0x180060413  jz      loc_1800604B3
0x180060419  mov     eax, cs:g_TrustedEnvironment
0x18006041f  xor     ebx, ebx
0x180060421  test    eax, eax
0x180060423  jnz     short loc_18006042A
0x180060425  call    GetTrustedEnvironment
0x18006042a  test    al, 2
0x18006042c  jnz     short loc_180060442
0x18006042e  lea     rcx, [rsp+28h+PerformanceFrequency]; PerformanceFrequency
0x180060433  call    cs:__imp_KeQueryPerformanceCounter
0x18006043a  nop     dword ptr [rax+rax+00h]
0x18006043f  mov     rbx, rax
0x180060442  call    AlgorithmCheck
0x180060447  mov     edi, eax
0x180060449  mov     eax, cs:g_TrustedEnvironment
0x18006044f  test    eax, eax
0x180060451  jnz     short loc_180060458
0x180060453  call    GetTrustedEnvironment
0x180060458  test    al, 2
0x18006045a  jnz     short loc_180060482
0x18006045c  xor     ecx, ecx; PerformanceFrequency
0x18006045e  call    cs:__imp_KeQueryPerformanceCounter
0x180060465  nop     dword ptr [rax+rax+00h]
0x18006046a  sub     rax, rbx
0x18006046d  xor     edx, edx
0x18006046f  imul    rax, 0F4240h
0x180060476  div     qword ptr [rsp+28h+PerformanceFrequency]
0x18006047b  mov     cs:g_selftestDuration, rax
0x180060482  test    edi, edi
0x180060484  jns     short loc_1800604B3
0x180060486  mov     r9d, 9Ah
0x18006048c  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180060493  lea     rdx, aNtstatus; "ntStatus"
0x18006049a  mov     ecx, edi
0x18006049c  call    DebugTraceError
0x1800604a1  mov     ecx, 123h; BugCheckCode
0x1800604a6  call    cs:__imp_KeBugCheck
0x1800604b3  mov     cs:g_fLoadCNGDone, ebp
0x1800604b9  xor     ebx, ebx
0x1800604bb  mov     rbp, [rsp+28h+arg_10]
0x1800604c0  mov     eax, ebx
0x1800604c2  mov     rbx, [rsp+28h+arg_8]
0x1800604c7  add     rsp, 20h
0x1800604cb  pop     rdi
0x1800604cc  retn
```
