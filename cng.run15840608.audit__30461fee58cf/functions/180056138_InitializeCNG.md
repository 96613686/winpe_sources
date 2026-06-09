# InitializeCNG

- ea: `0x180056138`
- end: `0x1800562fe`
- name: `InitializeCNG`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005cec8`

## callees

- `0x18000743c`
- `0x180024a34`
- `0x180056138`
- `0x180056414`
- `0x1800678b0`
- `0x180069bdc`
- `0x18006c688`
- `0x180073ee8`
- `0x1800814c4`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x18005621a`
- `ntoskrnl!ExInitializeResourceLite` at `0x18005621a`
- `ntoskrnl!KeBugCheck` at `0x1800562d6`
- `ntoskrnl!KeBugCheck` at `0x1800562d6`
- `HAL!KeQueryPerformanceCounter` at `0x180056263`
- `HAL!KeQueryPerformanceCounter` at `0x18005628e`
- `HAL!KeQueryPerformanceCounter` at `0x180056263`
- `HAL!KeQueryPerformanceCounter` at `0x18005628e`

## string_xrefs

- `0x18005619d`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x1800561c1`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\init.c`
- `0x1800562bc`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\init.c`

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
  if ( _InterlockedCompareExchange(&dword_1800CA3E0, 1, 0) )
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
0x180056138  mov     [rsp+arg_8], rbx
0x18005613d  mov     [rsp+arg_10], rbp
0x180056142  push    rdi
0x180056143  sub     rsp, 20h
0x180056147  mov     ebp, 1
0x18005614c  xor     eax, eax
0x18005614e  mov     qword ptr [rsp+28h+PerformanceFrequency], rbp
0x180056153  lock cmpxchg cs:dword_1800CA3E0, ebp
0x18005615b  jnz     loc_1800562E9
0x180056161  mov     eax, cs:g_TrustedEnvironment
0x180056167  test    eax, eax
0x180056169  jnz     short loc_180056170
0x18005616b  call    GetTrustedEnvironment
0x180056170  test    al, 2
0x180056172  jnz     loc_18005623C
0x180056178  cmp     cs:g_fLoaderInitialized, 0
0x18005617f  jnz     short loc_1800561D8
0x180056181  mov     cs:g_pLoadedProviderList, 0
0x18005618c  call    _InitializeLoaderLock
0x180056191  mov     ebx, eax
0x180056193  test    eax, eax
0x180056195  jns     short loc_1800561D2
0x180056197  mov     r9d, 7ACh
0x18005619d  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800561a4  lea     rdx, aSresult; "sResult"
0x1800561ab  mov     ecx, eax
0x1800561ad  call    DebugTraceError
0x1800561b2  mov     r9d, 59h ; 'Y'
0x1800561b8  mov     ecx, ebx
0x1800561ba  lea     rdx, aNtstatus; "ntStatus"
0x1800561c1  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800561c8  call    DebugTraceError
0x1800561cd  jmp     loc_1800562EB
0x1800561d2  mov     cs:g_fLoaderInitialized, ebp
0x1800561d8  call    InitializeConfig
0x1800561dd  mov     ebx, eax
0x1800561df  test    eax, eax
0x1800561e1  jns     short loc_1800561ED
0x1800561e3  mov     r9d, 61h ; 'a'
0x1800561e9  mov     ecx, eax
0x1800561eb  jmp     short loc_1800561BA
0x1800561ed  call    InitializeSystemPreferredCache
0x1800561f2  mov     ebx, eax
0x1800561f4  test    eax, eax
0x1800561f6  jns     short loc_180056200
0x1800561f8  mov     r9d, 69h ; 'i'
0x1800561fe  jmp     short loc_1800561E9
0x180056200  call    TlsInitializeDefaultAlgorithms
0x180056205  mov     ebx, eax
0x180056207  test    eax, eax
0x180056209  jns     short loc_180056213
0x18005620b  mov     r9d, 71h ; 'q'
0x180056211  jmp     short loc_1800561E9
0x180056213  lea     rcx, Resource; Resource
0x18005621a  call    cs:__imp_ExInitializeResourceLite
0x180056221  nop     dword ptr [rax+rax+00h]
0x180056226  lea     r8, ETW_LOG_CNG_PROVIDER_Context
0x18005622d  mov     r9, r8
0x180056230  lea     rcx, ETW_LOG_CNG_PROVIDER
0x180056237  call    McGenEventRegister_EtwRegister
0x18005623c  cmp     cs:g_fSelftest, 0
0x180056243  jz      loc_1800562E3
0x180056249  mov     eax, cs:g_TrustedEnvironment
0x18005624f  xor     ebx, ebx
0x180056251  test    eax, eax
0x180056253  jnz     short loc_18005625A
0x180056255  call    GetTrustedEnvironment
0x18005625a  test    al, 2
0x18005625c  jnz     short loc_180056272
0x18005625e  lea     rcx, [rsp+28h+PerformanceFrequency]; PerformanceFrequency
0x180056263  call    cs:__imp_KeQueryPerformanceCounter
0x18005626a  nop     dword ptr [rax+rax+00h]
0x18005626f  mov     rbx, rax
0x180056272  call    AlgorithmCheck
0x180056277  mov     edi, eax
0x180056279  mov     eax, cs:g_TrustedEnvironment
0x18005627f  test    eax, eax
0x180056281  jnz     short loc_180056288
0x180056283  call    GetTrustedEnvironment
0x180056288  test    al, 2
0x18005628a  jnz     short loc_1800562B2
0x18005628c  xor     ecx, ecx; PerformanceFrequency
0x18005628e  call    cs:__imp_KeQueryPerformanceCounter
0x180056295  nop     dword ptr [rax+rax+00h]
0x18005629a  sub     rax, rbx
0x18005629d  xor     edx, edx
0x18005629f  imul    rax, 0F4240h
0x1800562a6  div     qword ptr [rsp+28h+PerformanceFrequency]
0x1800562ab  mov     cs:g_selftestDuration, rax
0x1800562b2  test    edi, edi
0x1800562b4  jns     short loc_1800562E3
0x1800562b6  mov     r9d, 9Ah
0x1800562bc  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800562c3  lea     rdx, aNtstatus; "ntStatus"
0x1800562ca  mov     ecx, edi
0x1800562cc  call    DebugTraceError
0x1800562d1  mov     ecx, 123h; BugCheckCode
0x1800562d6  call    cs:__imp_KeBugCheck
0x1800562e3  mov     cs:g_fLoadCNGDone, ebp
0x1800562e9  xor     ebx, ebx
0x1800562eb  mov     rbp, [rsp+28h+arg_10]
0x1800562f0  mov     eax, ebx
0x1800562f2  mov     rbx, [rsp+28h+arg_8]
0x1800562f7  add     rsp, 20h
0x1800562fb  pop     rdi
0x1800562fc  retn
```
