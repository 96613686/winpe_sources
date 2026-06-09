# InitializeConfig

- ea: `0x18006c688`
- end: `0x18006c907`
- name: `InitializeConfig`
- size: `639`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180056138`
- `0x18005ce00`

## callees

- `0x180024a34`
- `0x1800289e0`
- `0x180069c80`
- `0x18006c688`
- `0x180070714`
- `0x180071a34`
- `0x18009d414`
- `0x18009dd40`
- `0x1800a3164`
- `0x1800a3360`

## import_xrefs

- `ntoskrnl!PsGetCurrentServerSilo` at `0x18006c6fe`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x18006c89f`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x18006c6fe`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x18006c89f`
- `ntoskrnl!PsCreateSiloContext` at `0x18006c726`
- `ntoskrnl!PsCreateSiloContext` at `0x18006c726`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x18006c8b3`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x18006c8b3`
- `ntoskrnl!PsDereferenceSiloContext` at `0x18006c8e8`
- `ntoskrnl!PsDereferenceSiloContext` at `0x18006c8e8`
- `ntoskrnl!ExInitializeResourceLite` at `0x18006c78b`
- `ntoskrnl!ExInitializeResourceLite` at `0x18006c815`
- `ntoskrnl!ExInitializeResourceLite` at `0x18006c859`
- `ntoskrnl!ExInitializeResourceLite` at `0x18006c78b`
- `ntoskrnl!ExInitializeResourceLite` at `0x18006c815`
- `ntoskrnl!ExInitializeResourceLite` at `0x18006c859`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x18006c6b9`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x18006c6b9`
- `ntoskrnl!RtlNtStatusToDosError` at `0x18006c823`
- `ntoskrnl!RtlNtStatusToDosError` at `0x18006c867`
- `ntoskrnl!RtlNtStatusToDosError` at `0x18006c823`
- `ntoskrnl!RtlNtStatusToDosError` at `0x18006c867`

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
      TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_1800C9588);
      v1 = g_TrustedEnvironment;
      if ( !g_TrustedEnvironment )
        v1 = GetTrustedEnvironment();
      if ( (v1 & 1) != 0 )
        InitializeProcessImageNameKM();
      TlgRegisterAggregateProviderEx(&dword_1800C95C0);
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
0x18006c688  mov     [rsp-8+arg_8], rbx
0x18006c68d  mov     [rsp-8+arg_10], rdi
0x18006c692  push    rbp
0x18006c693  mov     rbp, rsp
0x18006c696  sub     rsp, 30h
0x18006c69a  mov     eax, cs:g_TrustedEnvironment
0x18006c6a0  mov     [rbp+StartContext], 0
0x18006c6a8  test    eax, eax
0x18006c6aa  jnz     short loc_18006C6B1
0x18006c6ac  call    GetTrustedEnvironment
0x18006c6b1  test    al, 2
0x18006c6b3  jnz     loc_18006C742
0x18006c6b9  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x18006c6c0  nop     dword ptr [rax+rax+00h]
0x18006c6c5  test    al, al
0x18006c6c7  jnz     short loc_18006C6FE
0x18006c6c9  xor     r8d, r8d
0x18006c6cc  lea     rcx, dword_1800C9588; CallbackContext
0x18006c6d3  xor     edx, edx
0x18006c6d5  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x18006c6da  mov     eax, cs:g_TrustedEnvironment
0x18006c6e0  test    eax, eax
0x18006c6e2  jnz     short loc_18006C6E9
0x18006c6e4  call    GetTrustedEnvironment
0x18006c6e9  test    al, 1
0x18006c6eb  jz      short loc_18006C6F2
0x18006c6ed  call    InitializeProcessImageNameKM
0x18006c6f2  lea     rcx, dword_1800C95C0; CallbackContext
0x18006c6f9  call    TlgRegisterAggregateProviderEx
0x18006c6fe  call    cs:__imp_PsGetCurrentServerSilo
0x18006c705  nop     dword ptr [rax+rax+00h]
0x18006c70a  mov     edx, 1B0h
0x18006c70f  lea     r9, ?CngSiloContextCleanup@@YAXPEAX@Z; CngSiloContextCleanup(void *)
0x18006c716  mov     rcx, rax
0x18006c719  lea     rax, [rbp+StartContext]
0x18006c71d  mov     [rsp+30h+var_10], rax
0x18006c722  lea     r8d, [rdx+50h]
0x18006c726  call    cs:__imp_PsCreateSiloContext
0x18006c72d  nop     dword ptr [rax+rax+00h]
0x18006c732  mov     edi, eax
0x18006c734  test    eax, eax
0x18006c736  js      loc_18006C8C1
0x18006c73c  mov     rcx, [rbp+StartContext]
0x18006c740  jmp     short loc_18006C74D
0x18006c742  lea     rcx, ?pGlobalConfigContext@@3U_CNG_CONFIG_CONTEXT@@A; _CNG_CONFIG_CONTEXT pGlobalConfigContext
0x18006c749  mov     [rbp+StartContext], rcx
0x18006c74d  add     rcx, 110h; Resource
0x18006c754  mov     qword ptr [rcx+80h], 0
0x18006c75f  mov     qword ptr [rcx+68h], 0
0x18006c767  mov     qword ptr [rcx+70h], 0
0x18006c76f  mov     dword ptr [rcx+78h], 0
0x18006c776  mov     qword ptr [rcx+88h], 0
0x18006c781  mov     dword ptr [rcx+90h], 0
0x18006c78b  call    cs:__imp_ExInitializeResourceLite
0x18006c792  nop     dword ptr [rax+rax+00h]
0x18006c797  mov     edi, eax
0x18006c799  test    eax, eax
0x18006c79b  js      loc_18006C8C1
0x18006c7a1  mov     rcx, [rbp+StartContext]
0x18006c7a5  or      dword ptr [rcx], 1
0x18006c7a8  mov     rcx, [rbp+StartContext]
0x18006c7ac  add     rcx, 108h
0x18006c7b3  call    CcnCreatePublisher
0x18006c7b8  test    eax, eax
0x18006c7ba  jz      short loc_18006C7C8
0x18006c7bc  mov     ecx, eax; Status
0x18006c7be  call    WinErrorToNtStatus
0x18006c7c3  jmp     loc_18006C8BF
0x18006c7c8  mov     rax, [rbp+StartContext]
0x18006c7cc  or      dword ptr [rax], 2
0x18006c7cf  mov     eax, cs:g_TrustedEnvironment
0x18006c7d5  test    eax, eax
0x18006c7d7  jnz     short loc_18006C7DE
0x18006c7d9  call    GetTrustedEnvironment
0x18006c7de  test    al, 2
0x18006c7e0  jnz     short loc_18006C7FC
0x18006c7e2  mov     rcx, [rbp+StartContext]; StartContext
0x18006c7e6  call    RegKeyNotificationsInitialize
0x18006c7eb  mov     edi, eax
0x18006c7ed  test    eax, eax
0x18006c7ef  jnz     loc_18006C8C1
0x18006c7f5  mov     rax, [rbp+StartContext]
0x18006c7f9  or      dword ptr [rax], 4
0x18006c7fc  mov     rbx, [rbp+StartContext]
0x18006c800  xor     edx, edx; Val
0x18006c802  mov     r8d, 80h; Size
0x18006c808  lea     rcx, [rbx+8]; void *
0x18006c80c  call    memset
0x18006c811  lea     rcx, [rbx+8]; Resource
0x18006c815  call    cs:__imp_ExInitializeResourceLite
0x18006c81c  nop     dword ptr [rax+rax+00h]
0x18006c821  mov     ecx, eax; Status
0x18006c823  call    cs:__imp_RtlNtStatusToDosError
0x18006c82a  nop     dword ptr [rax+rax+00h]
0x18006c82f  test    eax, eax
0x18006c831  jnz     short loc_18006C7BC
0x18006c833  mov     rax, [rbp+StartContext]
0x18006c837  xor     edx, edx; Val
0x18006c839  mov     r8d, 80h; Size
0x18006c83f  or      dword ptr [rax], 8
0x18006c842  mov     rbx, [rbp+StartContext]
0x18006c846  lea     rcx, [rbx+88h]; void *
0x18006c84d  call    memset
0x18006c852  lea     rcx, [rbx+88h]; Resource
0x18006c859  call    cs:__imp_ExInitializeResourceLite
0x18006c860  nop     dword ptr [rax+rax+00h]
0x18006c865  mov     ecx, eax; Status
0x18006c867  call    cs:__imp_RtlNtStatusToDosError
0x18006c86e  nop     dword ptr [rax+rax+00h]
0x18006c873  test    eax, eax
0x18006c875  jnz     loc_18006C7BC
0x18006c87b  mov     rax, [rbp+StartContext]
0x18006c87f  or      dword ptr [rax], 10h
0x18006c882  mov     eax, cs:g_TrustedEnvironment
0x18006c888  test    eax, eax
0x18006c88a  jnz     short loc_18006C891
0x18006c88c  call    GetTrustedEnvironment
0x18006c891  test    al, 2
0x18006c893  jnz     short loc_18006C8F4
0x18006c895  mov     rbx, [rbp+StartContext]
0x18006c899  mov     edi, cs:g_SiloSlot
0x18006c89f  call    cs:__imp_PsGetCurrentServerSilo
0x18006c8a6  nop     dword ptr [rax+rax+00h]
0x18006c8ab  mov     r8, rbx
0x18006c8ae  mov     edx, edi
0x18006c8b0  mov     rcx, rax
0x18006c8b3  call    cs:__imp_PsInsertPermanentSiloContext
0x18006c8ba  nop     dword ptr [rax+rax+00h]
0x18006c8bf  mov     edi, eax
0x18006c8c1  mov     rcx, [rbp+StartContext]
0x18006c8c5  test    rcx, rcx
0x18006c8c8  jz      short loc_18006C8F4
0x18006c8ca  mov     eax, cs:g_TrustedEnvironment
0x18006c8d0  test    eax, eax
0x18006c8d2  jnz     short loc_18006C8DD
0x18006c8d4  call    GetTrustedEnvironment
0x18006c8d9  mov     rcx, [rbp+StartContext]; void *
0x18006c8dd  test    al, 2
0x18006c8df  jz      short loc_18006C8E8
0x18006c8e1  call    ?CngSiloContextCleanup@@YAXPEAX@Z; CngSiloContextCleanup(void *)
0x18006c8e6  jmp     short loc_18006C8F4
0x18006c8e8  call    cs:__imp_PsDereferenceSiloContext
0x18006c8ef  nop     dword ptr [rax+rax+00h]
0x18006c8f4  mov     rbx, [rsp+30h+arg_8]
0x18006c8f9  mov     eax, edi
0x18006c8fb  mov     rdi, [rsp+30h+arg_10]
0x18006c900  add     rsp, 30h
0x18006c904  pop     rbp
0x18006c905  retn
```
