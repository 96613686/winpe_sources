# InitializeConfig

- ea: `0x180076828`
- end: `0x180076aa7`
- name: `InitializeConfig`
- size: `639`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180060308`
- `0x180066fd0`

## callees

- `0x18002eb64`
- `0x180032b10`
- `0x180073e20`
- `0x180076828`
- `0x18007a8b4`
- `0x18007bbd4`
- `0x1800a3f14`
- `0x1800a4380`
- `0x1800a9f04`
- `0x1800aa100`

## import_xrefs

- `ntoskrnl!PsGetCurrentServerSilo` at `0x18007689e`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180076a3f`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x18007689e`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180076a3f`
- `ntoskrnl!PsCreateSiloContext` at `0x1800768c6`
- `ntoskrnl!PsCreateSiloContext` at `0x1800768c6`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x180076a53`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x180076a53`
- `ntoskrnl!PsDereferenceSiloContext` at `0x180076a88`
- `ntoskrnl!PsDereferenceSiloContext` at `0x180076a88`
- `ntoskrnl!ExInitializeResourceLite` at `0x18007692b`
- `ntoskrnl!ExInitializeResourceLite` at `0x1800769b5`
- `ntoskrnl!ExInitializeResourceLite` at `0x1800769f9`
- `ntoskrnl!ExInitializeResourceLite` at `0x18007692b`
- `ntoskrnl!ExInitializeResourceLite` at `0x1800769b5`
- `ntoskrnl!ExInitializeResourceLite` at `0x1800769f9`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x180076859`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x180076859`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1800769c3`
- `ntoskrnl!RtlNtStatusToDosError` at `0x180076a07`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1800769c3`
- `ntoskrnl!RtlNtStatusToDosError` at `0x180076a07`

## pseudocode

```c
__int64 InitializeConfig()
{
  char TrustedEnvironment; // al
  char v1; // al
  __int64 CurrentServerSilo; // rax
  NTSTATUS v3; // edi
  char *v4; // rcx
  struct _ERESOURCE *v5; // rcx
  NTSTATUS Publisher; // eax
  NTSTATUS inserted; // eax
  char v8; // al
  char *v9; // rbx
  NTSTATUS v10; // eax
  char *v11; // rbx
  NTSTATUS v12; // eax
  char v13; // al
  PVOID v14; // rbx
  unsigned int v15; // edi
  __int64 v16; // rax
  PVOID v17; // rcx
  char v18; // al
  PVOID StartContext; // [rsp+40h] [rbp+10h] BYREF

  TrustedEnvironment = g_TrustedEnvironment;
  StartContext = 0;
  if ( !g_TrustedEnvironment )
    TrustedEnvironment = GetTrustedEnvironment();
  if ( (TrustedEnvironment & 2) != 0 )
  {
    v4 = (char *)&pGlobalConfigContext;
    StartContext = &pGlobalConfigContext;
  }
  else
  {
    if ( !(unsigned __int8)PsIsCurrentThreadInServerSilo() )
    {
      TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_1800D1588);
      v1 = g_TrustedEnvironment;
      if ( !g_TrustedEnvironment )
        v1 = GetTrustedEnvironment();
      if ( (v1 & 1) != 0 )
        InitializeProcessImageNameKM();
      TlgRegisterAggregateProviderEx(&dword_1800D15C0);
    }
    CurrentServerSilo = PsGetCurrentServerSilo();
    v3 = PsCreateSiloContext(CurrentServerSilo, 432, 512, CngSiloContextCleanup, &StartContext);
    if ( v3 < 0 )
      goto LABEL_28;
    v4 = (char *)StartContext;
  }
  v5 = (struct _ERESOURCE *)(v4 + 272);
  *(_QWORD *)&v5[1].ActiveCount = 0;
  v5[1].SystemResourcesList.Flink = 0;
  v5[1].SystemResourcesList.Blink = 0;
  LODWORD(v5[1].OwnerTable) = 0;
  v5[1].SharedWaiters = 0;
  LODWORD(v5[1].ExclusiveWaiters) = 0;
  v3 = ExInitializeResourceLite(v5);
  if ( v3 < 0 )
  {
LABEL_28:
    v17 = StartContext;
    if ( StartContext )
    {
      v18 = g_TrustedEnvironment;
      if ( !g_TrustedEnvironment )
      {
        v18 = GetTrustedEnvironment();
        v17 = StartContext;
      }
      if ( (v18 & 2) != 0 )
        CngSiloContextCleanup(v17);
      else
        PsDereferenceSiloContext();
    }
    return (unsigned int)v3;
  }
  *(_DWORD *)StartContext |= 1u;
  Publisher = CcnCreatePublisher((char *)StartContext + 264);
  if ( Publisher )
    goto LABEL_15;
  *(_DWORD *)StartContext |= 2u;
  v8 = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    v8 = GetTrustedEnvironment();
  if ( (v8 & 2) == 0 )
  {
    v3 = RegKeyNotificationsInitialize(StartContext);
    if ( v3 )
      goto LABEL_28;
    *(_DWORD *)StartContext |= 4u;
  }
  v9 = (char *)StartContext;
  memset((char *)StartContext + 8, 0, 0x80u);
  v10 = ExInitializeResourceLite((PERESOURCE)(v9 + 8));
  Publisher = RtlNtStatusToDosError(v10);
  if ( Publisher
    || (*(_DWORD *)StartContext |= 8u,
        v11 = (char *)StartContext,
        memset((char *)StartContext + 136, 0, 0x80u),
        v12 = ExInitializeResourceLite((PERESOURCE)(v11 + 136)),
        (Publisher = RtlNtStatusToDosError(v12)) != 0) )
  {
LABEL_15:
    inserted = WinErrorToNtStatus(Publisher);
LABEL_27:
    v3 = inserted;
    goto LABEL_28;
  }
  *(_DWORD *)StartContext |= 0x10u;
  v13 = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    v13 = GetTrustedEnvironment();
  if ( (v13 & 2) == 0 )
  {
    v14 = StartContext;
    v15 = g_SiloSlot;
    v16 = PsGetCurrentServerSilo();
    inserted = PsInsertPermanentSiloContext(v16, v15, v14);
    goto LABEL_27;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180076828  mov     [rsp-8+arg_8], rbx
0x18007682d  mov     [rsp-8+arg_10], rdi
0x180076832  push    rbp
0x180076833  mov     rbp, rsp
0x180076836  sub     rsp, 30h
0x18007683a  mov     eax, cs:g_TrustedEnvironment
0x180076840  mov     [rbp+StartContext], 0
0x180076848  test    eax, eax
0x18007684a  jnz     short loc_180076851
0x18007684c  call    GetTrustedEnvironment
0x180076851  test    al, 2
0x180076853  jnz     loc_1800768E2
0x180076859  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x180076860  nop     dword ptr [rax+rax+00h]
0x180076865  test    al, al
0x180076867  jnz     short loc_18007689E
0x180076869  xor     r8d, r8d
0x18007686c  lea     rcx, dword_1800D1588; CallbackContext
0x180076873  xor     edx, edx
0x180076875  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x18007687a  mov     eax, cs:g_TrustedEnvironment
0x180076880  test    eax, eax
0x180076882  jnz     short loc_180076889
0x180076884  call    GetTrustedEnvironment
0x180076889  test    al, 1
0x18007688b  jz      short loc_180076892
0x18007688d  call    InitializeProcessImageNameKM
0x180076892  lea     rcx, dword_1800D15C0; CallbackContext
0x180076899  call    TlgRegisterAggregateProviderEx
0x18007689e  call    cs:__imp_PsGetCurrentServerSilo
0x1800768a5  nop     dword ptr [rax+rax+00h]
0x1800768aa  mov     edx, 1B0h
0x1800768af  lea     r9, ?CngSiloContextCleanup@@YAXPEAX@Z; CngSiloContextCleanup(void *)
0x1800768b6  mov     rcx, rax
0x1800768b9  lea     rax, [rbp+StartContext]
0x1800768bd  mov     [rsp+30h+var_10], rax
0x1800768c2  lea     r8d, [rdx+50h]
0x1800768c6  call    cs:__imp_PsCreateSiloContext
0x1800768cd  nop     dword ptr [rax+rax+00h]
0x1800768d2  mov     edi, eax
0x1800768d4  test    eax, eax
0x1800768d6  js      loc_180076A61
0x1800768dc  mov     rcx, [rbp+StartContext]
0x1800768e0  jmp     short loc_1800768ED
0x1800768e2  lea     rcx, ?pGlobalConfigContext@@3U_CNG_CONFIG_CONTEXT@@A; _CNG_CONFIG_CONTEXT pGlobalConfigContext
0x1800768e9  mov     [rbp+StartContext], rcx
0x1800768ed  add     rcx, 110h; Resource
0x1800768f4  mov     qword ptr [rcx+80h], 0
0x1800768ff  mov     qword ptr [rcx+68h], 0
0x180076907  mov     qword ptr [rcx+70h], 0
0x18007690f  mov     dword ptr [rcx+78h], 0
0x180076916  mov     qword ptr [rcx+88h], 0
0x180076921  mov     dword ptr [rcx+90h], 0
0x18007692b  call    cs:__imp_ExInitializeResourceLite
0x180076932  nop     dword ptr [rax+rax+00h]
0x180076937  mov     edi, eax
0x180076939  test    eax, eax
0x18007693b  js      loc_180076A61
0x180076941  mov     rcx, [rbp+StartContext]
0x180076945  or      dword ptr [rcx], 1
0x180076948  mov     rcx, [rbp+StartContext]
0x18007694c  add     rcx, 108h
0x180076953  call    CcnCreatePublisher
0x180076958  test    eax, eax
0x18007695a  jz      short loc_180076968
0x18007695c  mov     ecx, eax; Status
0x18007695e  call    WinErrorToNtStatus
0x180076963  jmp     loc_180076A5F
0x180076968  mov     rax, [rbp+StartContext]
0x18007696c  or      dword ptr [rax], 2
0x18007696f  mov     eax, cs:g_TrustedEnvironment
0x180076975  test    eax, eax
0x180076977  jnz     short loc_18007697E
0x180076979  call    GetTrustedEnvironment
0x18007697e  test    al, 2
0x180076980  jnz     short loc_18007699C
0x180076982  mov     rcx, [rbp+StartContext]; StartContext
0x180076986  call    RegKeyNotificationsInitialize
0x18007698b  mov     edi, eax
0x18007698d  test    eax, eax
0x18007698f  jnz     loc_180076A61
0x180076995  mov     rax, [rbp+StartContext]
0x180076999  or      dword ptr [rax], 4
0x18007699c  mov     rbx, [rbp+StartContext]
0x1800769a0  xor     edx, edx; Val
0x1800769a2  mov     r8d, 80h; Size
0x1800769a8  lea     rcx, [rbx+8]; void *
0x1800769ac  call    memset
0x1800769b1  lea     rcx, [rbx+8]; Resource
0x1800769b5  call    cs:__imp_ExInitializeResourceLite
0x1800769bc  nop     dword ptr [rax+rax+00h]
0x1800769c1  mov     ecx, eax; Status
0x1800769c3  call    cs:__imp_RtlNtStatusToDosError
0x1800769ca  nop     dword ptr [rax+rax+00h]
0x1800769cf  test    eax, eax
0x1800769d1  jnz     short loc_18007695C
0x1800769d3  mov     rax, [rbp+StartContext]
0x1800769d7  xor     edx, edx; Val
0x1800769d9  mov     r8d, 80h; Size
0x1800769df  or      dword ptr [rax], 8
0x1800769e2  mov     rbx, [rbp+StartContext]
0x1800769e6  lea     rcx, [rbx+88h]; void *
0x1800769ed  call    memset
0x1800769f2  lea     rcx, [rbx+88h]; Resource
0x1800769f9  call    cs:__imp_ExInitializeResourceLite
0x180076a00  nop     dword ptr [rax+rax+00h]
0x180076a05  mov     ecx, eax; Status
0x180076a07  call    cs:__imp_RtlNtStatusToDosError
0x180076a0e  nop     dword ptr [rax+rax+00h]
0x180076a13  test    eax, eax
0x180076a15  jnz     loc_18007695C
0x180076a1b  mov     rax, [rbp+StartContext]
0x180076a1f  or      dword ptr [rax], 10h
0x180076a22  mov     eax, cs:g_TrustedEnvironment
0x180076a28  test    eax, eax
0x180076a2a  jnz     short loc_180076A31
0x180076a2c  call    GetTrustedEnvironment
0x180076a31  test    al, 2
0x180076a33  jnz     short loc_180076A94
0x180076a35  mov     rbx, [rbp+StartContext]
0x180076a39  mov     edi, cs:g_SiloSlot
0x180076a3f  call    cs:__imp_PsGetCurrentServerSilo
0x180076a46  nop     dword ptr [rax+rax+00h]
0x180076a4b  mov     r8, rbx
0x180076a4e  mov     edx, edi
0x180076a50  mov     rcx, rax
0x180076a53  call    cs:__imp_PsInsertPermanentSiloContext
0x180076a5a  nop     dword ptr [rax+rax+00h]
0x180076a5f  mov     edi, eax
0x180076a61  mov     rcx, [rbp+StartContext]
0x180076a65  test    rcx, rcx
0x180076a68  jz      short loc_180076A94
0x180076a6a  mov     eax, cs:g_TrustedEnvironment
0x180076a70  test    eax, eax
0x180076a72  jnz     short loc_180076A7D
0x180076a74  call    GetTrustedEnvironment
0x180076a79  mov     rcx, [rbp+StartContext]; void *
0x180076a7d  test    al, 2
0x180076a7f  jz      short loc_180076A88
0x180076a81  call    ?CngSiloContextCleanup@@YAXPEAX@Z; CngSiloContextCleanup(void *)
0x180076a86  jmp     short loc_180076A94
0x180076a88  call    cs:__imp_PsDereferenceSiloContext
0x180076a8f  nop     dword ptr [rax+rax+00h]
0x180076a94  mov     rbx, [rsp+30h+arg_8]
0x180076a99  mov     eax, edi
0x180076a9b  mov     rdi, [rsp+30h+arg_10]
0x180076aa0  add     rsp, 30h
0x180076aa4  pop     rbp
0x180076aa5  retn
```
