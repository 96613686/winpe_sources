# InitializeConfig

- ea: `0x18006d088`
- end: `0x18006d307`
- name: `InitializeConfig`
- size: `639`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180056a28`
- `0x18005d6f0`

## callees

- `0x180021af4`
- `0x180025aa0`
- `0x18006a680`
- `0x18006d088`
- `0x180071114`
- `0x180072434`
- `0x18009f2e0`
- `0x18009fa80`
- `0x1800a4f94`
- `0x1800a5190`

## import_xrefs

- `ntoskrnl!PsGetCurrentServerSilo` at `0x18006d0fe`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x18006d29f`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x18006d0fe`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x18006d29f`
- `ntoskrnl!PsCreateSiloContext` at `0x18006d126`
- `ntoskrnl!PsCreateSiloContext` at `0x18006d126`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x18006d2b3`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x18006d2b3`
- `ntoskrnl!PsDereferenceSiloContext` at `0x18006d2e8`
- `ntoskrnl!PsDereferenceSiloContext` at `0x18006d2e8`
- `ntoskrnl!ExInitializeResourceLite` at `0x18006d18b`
- `ntoskrnl!ExInitializeResourceLite` at `0x18006d215`
- `ntoskrnl!ExInitializeResourceLite` at `0x18006d259`
- `ntoskrnl!ExInitializeResourceLite` at `0x18006d18b`
- `ntoskrnl!ExInitializeResourceLite` at `0x18006d215`
- `ntoskrnl!ExInitializeResourceLite` at `0x18006d259`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x18006d0b9`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x18006d0b9`
- `ntoskrnl!RtlNtStatusToDosError` at `0x18006d223`
- `ntoskrnl!RtlNtStatusToDosError` at `0x18006d267`
- `ntoskrnl!RtlNtStatusToDosError` at `0x18006d223`
- `ntoskrnl!RtlNtStatusToDosError` at `0x18006d267`

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
      TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_1800CB588);
      v1 = g_TrustedEnvironment;
      if ( !g_TrustedEnvironment )
        v1 = GetTrustedEnvironment();
      if ( (v1 & 1) != 0 )
        InitializeProcessImageNameKM();
      TlgRegisterAggregateProviderEx(&dword_1800CB5C0);
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
0x18006d088  mov     [rsp-8+arg_8], rbx
0x18006d08d  mov     [rsp-8+arg_10], rdi
0x18006d092  push    rbp
0x18006d093  mov     rbp, rsp
0x18006d096  sub     rsp, 30h
0x18006d09a  mov     eax, cs:g_TrustedEnvironment
0x18006d0a0  mov     [rbp+StartContext], 0
0x18006d0a8  test    eax, eax
0x18006d0aa  jnz     short loc_18006D0B1
0x18006d0ac  call    GetTrustedEnvironment
0x18006d0b1  test    al, 2
0x18006d0b3  jnz     loc_18006D142
0x18006d0b9  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x18006d0c0  nop     dword ptr [rax+rax+00h]
0x18006d0c5  test    al, al
0x18006d0c7  jnz     short loc_18006D0FE
0x18006d0c9  xor     r8d, r8d
0x18006d0cc  lea     rcx, dword_1800CB588; CallbackContext
0x18006d0d3  xor     edx, edx
0x18006d0d5  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x18006d0da  mov     eax, cs:g_TrustedEnvironment
0x18006d0e0  test    eax, eax
0x18006d0e2  jnz     short loc_18006D0E9
0x18006d0e4  call    GetTrustedEnvironment
0x18006d0e9  test    al, 1
0x18006d0eb  jz      short loc_18006D0F2
0x18006d0ed  call    InitializeProcessImageNameKM
0x18006d0f2  lea     rcx, dword_1800CB5C0; CallbackContext
0x18006d0f9  call    TlgRegisterAggregateProviderEx
0x18006d0fe  call    cs:__imp_PsGetCurrentServerSilo
0x18006d105  nop     dword ptr [rax+rax+00h]
0x18006d10a  mov     edx, 1B0h
0x18006d10f  lea     r9, ?CngSiloContextCleanup@@YAXPEAX@Z; CngSiloContextCleanup(void *)
0x18006d116  mov     rcx, rax
0x18006d119  lea     rax, [rbp+StartContext]
0x18006d11d  mov     [rsp+30h+var_10], rax
0x18006d122  lea     r8d, [rdx+50h]
0x18006d126  call    cs:__imp_PsCreateSiloContext
0x18006d12d  nop     dword ptr [rax+rax+00h]
0x18006d132  mov     edi, eax
0x18006d134  test    eax, eax
0x18006d136  js      loc_18006D2C1
0x18006d13c  mov     rcx, [rbp+StartContext]
0x18006d140  jmp     short loc_18006D14D
0x18006d142  lea     rcx, ?pGlobalConfigContext@@3U_CNG_CONFIG_CONTEXT@@A; _CNG_CONFIG_CONTEXT pGlobalConfigContext
0x18006d149  mov     [rbp+StartContext], rcx
0x18006d14d  add     rcx, 110h; Resource
0x18006d154  mov     qword ptr [rcx+80h], 0
0x18006d15f  mov     qword ptr [rcx+68h], 0
0x18006d167  mov     qword ptr [rcx+70h], 0
0x18006d16f  mov     dword ptr [rcx+78h], 0
0x18006d176  mov     qword ptr [rcx+88h], 0
0x18006d181  mov     dword ptr [rcx+90h], 0
0x18006d18b  call    cs:__imp_ExInitializeResourceLite
0x18006d192  nop     dword ptr [rax+rax+00h]
0x18006d197  mov     edi, eax
0x18006d199  test    eax, eax
0x18006d19b  js      loc_18006D2C1
0x18006d1a1  mov     rcx, [rbp+StartContext]
0x18006d1a5  or      dword ptr [rcx], 1
0x18006d1a8  mov     rcx, [rbp+StartContext]
0x18006d1ac  add     rcx, 108h
0x18006d1b3  call    CcnCreatePublisher
0x18006d1b8  test    eax, eax
0x18006d1ba  jz      short loc_18006D1C8
0x18006d1bc  mov     ecx, eax; Status
0x18006d1be  call    WinErrorToNtStatus
0x18006d1c3  jmp     loc_18006D2BF
0x18006d1c8  mov     rax, [rbp+StartContext]
0x18006d1cc  or      dword ptr [rax], 2
0x18006d1cf  mov     eax, cs:g_TrustedEnvironment
0x18006d1d5  test    eax, eax
0x18006d1d7  jnz     short loc_18006D1DE
0x18006d1d9  call    GetTrustedEnvironment
0x18006d1de  test    al, 2
0x18006d1e0  jnz     short loc_18006D1FC
0x18006d1e2  mov     rcx, [rbp+StartContext]; StartContext
0x18006d1e6  call    RegKeyNotificationsInitialize
0x18006d1eb  mov     edi, eax
0x18006d1ed  test    eax, eax
0x18006d1ef  jnz     loc_18006D2C1
0x18006d1f5  mov     rax, [rbp+StartContext]
0x18006d1f9  or      dword ptr [rax], 4
0x18006d1fc  mov     rbx, [rbp+StartContext]
0x18006d200  xor     edx, edx; Val
0x18006d202  mov     r8d, 80h; Size
0x18006d208  lea     rcx, [rbx+8]; void *
0x18006d20c  call    memset
0x18006d211  lea     rcx, [rbx+8]; Resource
0x18006d215  call    cs:__imp_ExInitializeResourceLite
0x18006d21c  nop     dword ptr [rax+rax+00h]
0x18006d221  mov     ecx, eax; Status
0x18006d223  call    cs:__imp_RtlNtStatusToDosError
0x18006d22a  nop     dword ptr [rax+rax+00h]
0x18006d22f  test    eax, eax
0x18006d231  jnz     short loc_18006D1BC
0x18006d233  mov     rax, [rbp+StartContext]
0x18006d237  xor     edx, edx; Val
0x18006d239  mov     r8d, 80h; Size
0x18006d23f  or      dword ptr [rax], 8
0x18006d242  mov     rbx, [rbp+StartContext]
0x18006d246  lea     rcx, [rbx+88h]; void *
0x18006d24d  call    memset
0x18006d252  lea     rcx, [rbx+88h]; Resource
0x18006d259  call    cs:__imp_ExInitializeResourceLite
0x18006d260  nop     dword ptr [rax+rax+00h]
0x18006d265  mov     ecx, eax; Status
0x18006d267  call    cs:__imp_RtlNtStatusToDosError
0x18006d26e  nop     dword ptr [rax+rax+00h]
0x18006d273  test    eax, eax
0x18006d275  jnz     loc_18006D1BC
0x18006d27b  mov     rax, [rbp+StartContext]
0x18006d27f  or      dword ptr [rax], 10h
0x18006d282  mov     eax, cs:g_TrustedEnvironment
0x18006d288  test    eax, eax
0x18006d28a  jnz     short loc_18006D291
0x18006d28c  call    GetTrustedEnvironment
0x18006d291  test    al, 2
0x18006d293  jnz     short loc_18006D2F4
0x18006d295  mov     rbx, [rbp+StartContext]
0x18006d299  mov     edi, cs:g_SiloSlot
0x18006d29f  call    cs:__imp_PsGetCurrentServerSilo
0x18006d2a6  nop     dword ptr [rax+rax+00h]
0x18006d2ab  mov     r8, rbx
0x18006d2ae  mov     edx, edi
0x18006d2b0  mov     rcx, rax
0x18006d2b3  call    cs:__imp_PsInsertPermanentSiloContext
0x18006d2ba  nop     dword ptr [rax+rax+00h]
0x18006d2bf  mov     edi, eax
0x18006d2c1  mov     rcx, [rbp+StartContext]
0x18006d2c5  test    rcx, rcx
0x18006d2c8  jz      short loc_18006D2F4
0x18006d2ca  mov     eax, cs:g_TrustedEnvironment
0x18006d2d0  test    eax, eax
0x18006d2d2  jnz     short loc_18006D2DD
0x18006d2d4  call    GetTrustedEnvironment
0x18006d2d9  mov     rcx, [rbp+StartContext]; void *
0x18006d2dd  test    al, 2
0x18006d2df  jz      short loc_18006D2E8
0x18006d2e1  call    ?CngSiloContextCleanup@@YAXPEAX@Z; CngSiloContextCleanup(void *)
0x18006d2e6  jmp     short loc_18006D2F4
0x18006d2e8  call    cs:__imp_PsDereferenceSiloContext
0x18006d2ef  nop     dword ptr [rax+rax+00h]
0x18006d2f4  mov     rbx, [rsp+30h+arg_8]
0x18006d2f9  mov     eax, edi
0x18006d2fb  mov     rdi, [rsp+30h+arg_10]
0x18006d300  add     rsp, 30h
0x18006d304  pop     rbp
0x18006d305  retn
```
