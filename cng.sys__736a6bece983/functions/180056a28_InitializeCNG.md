# InitializeCNG

- ea: `0x180056a28`
- end: `0x180056bee`
- name: `InitializeCNG`
- size: `454`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005d7b8`

## callees

- `0x18000743c`
- `0x180021af4`
- `0x180056a28`
- `0x180056d04`
- `0x1800682b0`
- `0x18006a5dc`
- `0x18006d088`
- `0x1800748e8`
- `0x1800824b4`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x180056b0a`
- `ntoskrnl!ExInitializeResourceLite` at `0x180056b0a`
- `ntoskrnl!KeBugCheck` at `0x180056bc6`
- `ntoskrnl!KeBugCheck` at `0x180056bc6`
- `HAL!KeQueryPerformanceCounter` at `0x180056b53`
- `HAL!KeQueryPerformanceCounter` at `0x180056b7e`
- `HAL!KeQueryPerformanceCounter` at `0x180056b53`
- `HAL!KeQueryPerformanceCounter` at `0x180056b7e`

## string_xrefs

- `0x180056a8d`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180056ab1`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\init.c`
- `0x180056bac`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\init.c`

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
  if ( _InterlockedCompareExchange(&dword_1800CC420, 1, 0) )
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
0x180056a28  mov     [rsp+arg_8], rbx
0x180056a2d  mov     [rsp+arg_10], rbp
0x180056a32  push    rdi
0x180056a33  sub     rsp, 20h
0x180056a37  mov     ebp, 1
0x180056a3c  xor     eax, eax
0x180056a3e  mov     qword ptr [rsp+28h+PerformanceFrequency], rbp
0x180056a43  lock cmpxchg cs:dword_1800CC420, ebp
0x180056a4b  jnz     loc_180056BD9
0x180056a51  mov     eax, cs:g_TrustedEnvironment
0x180056a57  test    eax, eax
0x180056a59  jnz     short loc_180056A60
0x180056a5b  call    GetTrustedEnvironment
0x180056a60  test    al, 2
0x180056a62  jnz     loc_180056B2C
0x180056a68  cmp     cs:g_fLoaderInitialized, 0
0x180056a6f  jnz     short loc_180056AC8
0x180056a71  mov     cs:g_pLoadedProviderList, 0
0x180056a7c  call    _InitializeLoaderLock
0x180056a81  mov     ebx, eax
0x180056a83  test    eax, eax
0x180056a85  jns     short loc_180056AC2
0x180056a87  mov     r9d, 7ACh
0x180056a8d  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180056a94  lea     rdx, aSresult; "sResult"
0x180056a9b  mov     ecx, eax
0x180056a9d  call    DebugTraceError
0x180056aa2  mov     r9d, 59h ; 'Y'
0x180056aa8  mov     ecx, ebx
0x180056aaa  lea     rdx, aNtstatus; "ntStatus"
0x180056ab1  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180056ab8  call    DebugTraceError
0x180056abd  jmp     loc_180056BDB
0x180056ac2  mov     cs:g_fLoaderInitialized, ebp
0x180056ac8  call    InitializeConfig
0x180056acd  mov     ebx, eax
0x180056acf  test    eax, eax
0x180056ad1  jns     short loc_180056ADD
0x180056ad3  mov     r9d, 61h ; 'a'
0x180056ad9  mov     ecx, eax
0x180056adb  jmp     short loc_180056AAA
0x180056add  call    InitializeSystemPreferredCache
0x180056ae2  mov     ebx, eax
0x180056ae4  test    eax, eax
0x180056ae6  jns     short loc_180056AF0
0x180056ae8  mov     r9d, 69h ; 'i'
0x180056aee  jmp     short loc_180056AD9
0x180056af0  call    TlsInitializeDefaultAlgorithms
0x180056af5  mov     ebx, eax
0x180056af7  test    eax, eax
0x180056af9  jns     short loc_180056B03
0x180056afb  mov     r9d, 71h ; 'q'
0x180056b01  jmp     short loc_180056AD9
0x180056b03  lea     rcx, Resource; Resource
0x180056b0a  call    cs:__imp_ExInitializeResourceLite
0x180056b11  nop     dword ptr [rax+rax+00h]
0x180056b16  lea     r8, ETW_LOG_CNG_PROVIDER_Context
0x180056b1d  mov     r9, r8
0x180056b20  lea     rcx, ETW_LOG_CNG_PROVIDER
0x180056b27  call    McGenEventRegister_EtwRegister
0x180056b2c  cmp     cs:g_fSelftest, 0
0x180056b33  jz      loc_180056BD3
0x180056b39  mov     eax, cs:g_TrustedEnvironment
0x180056b3f  xor     ebx, ebx
0x180056b41  test    eax, eax
0x180056b43  jnz     short loc_180056B4A
0x180056b45  call    GetTrustedEnvironment
0x180056b4a  test    al, 2
0x180056b4c  jnz     short loc_180056B62
0x180056b4e  lea     rcx, [rsp+28h+PerformanceFrequency]; PerformanceFrequency
0x180056b53  call    cs:__imp_KeQueryPerformanceCounter
0x180056b5a  nop     dword ptr [rax+rax+00h]
0x180056b5f  mov     rbx, rax
0x180056b62  call    AlgorithmCheck
0x180056b67  mov     edi, eax
0x180056b69  mov     eax, cs:g_TrustedEnvironment
0x180056b6f  test    eax, eax
0x180056b71  jnz     short loc_180056B78
0x180056b73  call    GetTrustedEnvironment
0x180056b78  test    al, 2
0x180056b7a  jnz     short loc_180056BA2
0x180056b7c  xor     ecx, ecx; PerformanceFrequency
0x180056b7e  call    cs:__imp_KeQueryPerformanceCounter
0x180056b85  nop     dword ptr [rax+rax+00h]
0x180056b8a  sub     rax, rbx
0x180056b8d  xor     edx, edx
0x180056b8f  imul    rax, 0F4240h
0x180056b96  div     qword ptr [rsp+28h+PerformanceFrequency]
0x180056b9b  mov     cs:g_selftestDuration, rax
0x180056ba2  test    edi, edi
0x180056ba4  jns     short loc_180056BD3
0x180056ba6  mov     r9d, 9Ah
0x180056bac  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180056bb3  lea     rdx, aNtstatus; "ntStatus"
0x180056bba  mov     ecx, edi
0x180056bbc  call    DebugTraceError
0x180056bc1  mov     ecx, 123h; BugCheckCode
0x180056bc6  call    cs:__imp_KeBugCheck
0x180056bd3  mov     cs:g_fLoadCNGDone, ebp
0x180056bd9  xor     ebx, ebx
0x180056bdb  mov     rbp, [rsp+28h+arg_10]
0x180056be0  mov     eax, ebx
0x180056be2  mov     rbx, [rsp+28h+arg_8]
0x180056be7  add     rsp, 20h
0x180056beb  pop     rdi
0x180056bec  retn
```
