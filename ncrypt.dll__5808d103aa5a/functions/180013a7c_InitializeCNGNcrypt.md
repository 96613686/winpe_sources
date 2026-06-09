# InitializeCNGNcrypt

- ea: `0x180013a7c`
- end: `0x180013bc7`
- name: `InitializeCNGNcrypt`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013880`

## callees

- `0x18000d02c`
- `0x18000e120`
- `0x180013a7c`
- `0x180013d38`
- `0x180013ef0`
- `0x180013f38`
- `0x180013ffc`
- `0x180018e18`
- `0x180018e90`
- `0x180019060`
- `0x180019548`

## import_xrefs

- `ntdll!RtlInitializeCriticalSection` at `0x180013b3d`
- `ntdll!RtlInitializeCriticalSection` at `0x180013b3d`
- `ntdll!RtlDllShutdownInProgress` at `0x180013b8c`
- `ntdll!RtlDllShutdownInProgress` at `0x180013b8c`
- `NTASN1!__imp_RtlAsn1GetModuleHandle` at `0x180013a89`
- `NTASN1!__imp_RtlAsn1GetModuleHandle` at `0x180013a89`

## string_xrefs

- `0x180013ac5`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\init.c`
- `0x180013bab`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\init.c`

## pseudocode

```c
__int64 InitializeCNGNcrypt()
{
  int v0; // edx
  unsigned int v1; // ebx
  NTSTATUS v2; // eax
  __int64 v3; // r9
  char TrustedEnvironment; // al

  ASN1_NCRYPT_MODULE_HANDLE = RtlAsn1GetModuleHandle(L"{DCD07F46-25B9-4844-BFA5-C7D582C66524}");
  if ( !ASN1_NCRYPT_MODULE_HANDLE )
  {
    v1 = -2146893783;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v0,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\init.c",
        (unsigned int)"Status",
        41,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\init.c",
        163);
    goto LABEL_23;
  }
  v2 = MSCryptInitializeMemoryLists();
  v1 = v2;
  if ( v2 )
  {
    v3 = 173;
LABEL_22:
    DebugTraceError((unsigned int)v2, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\init.c", v3);
LABEL_23:
    UninitializeCNGNcrypt();
    return v1;
  }
  dword_18002AB28 |= 1u;
  v2 = InitializeLoader();
  v1 = v2;
  if ( v2 )
  {
    v3 = 181;
    goto LABEL_22;
  }
  dword_18002AB28 |= 2u;
  if ( !dword_18002AF1C )
  {
    v2 = RtlInitializeCriticalSection(&g_csKeyProtectorLock);
    v1 = v2;
    if ( v2 < 0 )
    {
      v3 = 189;
      goto LABEL_22;
    }
    dword_18002AF1C = 1;
  }
  dword_18002AB28 |= 4u;
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&qword_18002A108);
  if ( (unsigned int)Feature_KG_Ncrypt_Telemetry__private_IsEnabledDeviceUsageNoInline() )
  {
    TrustedEnvironment = g_TrustedEnvironment;
    if ( !g_TrustedEnvironment )
      TrustedEnvironment = GetTrustedEnvironment();
    if ( (TrustedEnvironment & 1) != 0 )
      InitializeProcessImageNameUM();
    if ( !RtlDllShutdownInProgress() )
      TlgRegisterAggregateProviderEx();
  }
  return 0;
}

```

## disassembly

```asm
0x180013a7c  push    rbx
0x180013a7e  sub     rsp, 40h
0x180013a82  lea     rcx, aDcd07f4625b948; "{DCD07F46-25B9-4844-BFA5-C7D582C66524}"
0x180013a89  call    cs:__imp_RtlAsn1GetModuleHandle
0x180013a8f  mov     cs:ASN1_NCRYPT_MODULE_HANDLE, rax
0x180013a96  test    rax, rax
0x180013a99  jnz     short loc_180013AF2
0x180013a9b  mov     ebx, 80090029h
0x180013aa0  mov     rcx, cs:WPP_GLOBAL_Control
0x180013aa7  lea     rax, WPP_GLOBAL_Control
0x180013aae  cmp     rcx, rax
0x180013ab1  jz      loc_180013BC0
0x180013ab7  test    byte ptr [rcx+1Ch], 1
0x180013abb  jz      loc_180013BC0
0x180013ac1  mov     rcx, [rcx+10h]
0x180013ac5  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013acc  mov     [rsp+48h+var_18], 0A3h
0x180013ad4  lea     r9, aStatus; "Status"
0x180013adb  mov     [rsp+48h+var_20], r8
0x180013ae0  mov     [rsp+48h+var_28], 80090029h
0x180013ae8  call    WPP_SF_sDsd
0x180013aed  jmp     loc_180013BC0
0x180013af2  call    MSCryptInitializeMemoryLists
0x180013af7  mov     ebx, eax
0x180013af9  test    eax, eax
0x180013afb  jz      short loc_180013B08
0x180013afd  mov     r9d, 0ADh
0x180013b03  jmp     loc_180013BAB
0x180013b08  or      cs:dword_18002AB28, 1
0x180013b0f  call    InitializeLoader
0x180013b14  mov     ebx, eax
0x180013b16  test    eax, eax
0x180013b18  jz      short loc_180013B25
0x180013b1a  mov     r9d, 0B5h
0x180013b20  jmp     loc_180013BAB
0x180013b25  or      cs:dword_18002AB28, 2
0x180013b2c  mov     eax, cs:dword_18002AF1C
0x180013b32  test    eax, eax
0x180013b34  jnz     short loc_180013B53
0x180013b36  lea     rcx, g_csKeyProtectorLock; CriticalSection
0x180013b3d  call    cs:__imp_RtlInitializeCriticalSection
0x180013b43  mov     ebx, eax
0x180013b45  test    eax, eax
0x180013b47  js      short loc_180013BA5
0x180013b49  mov     cs:dword_18002AF1C, 1
0x180013b53  or      cs:dword_18002AB28, 4
0x180013b5a  lea     rcx, qword_18002A108; CallbackContext
0x180013b61  xor     r8d, r8d
0x180013b64  xor     edx, edx
0x180013b66  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180013b6b  call    Feature_KG_Ncrypt_Telemetry__private_IsEnabledDeviceUsageNoInline
0x180013b70  test    eax, eax
0x180013b72  jz      short loc_180013B9B
0x180013b74  mov     eax, cs:g_TrustedEnvironment
0x180013b7a  test    eax, eax
0x180013b7c  jnz     short loc_180013B83
0x180013b7e  call    GetTrustedEnvironment
0x180013b83  test    al, 1
0x180013b85  jz      short loc_180013B8C
0x180013b87  call    InitializeProcessImageNameUM
0x180013b8c  call    cs:__imp_RtlDllShutdownInProgress
0x180013b92  test    al, al
0x180013b94  jnz     short loc_180013B9B
0x180013b96  call    TlgRegisterAggregateProviderEx
0x180013b9b  xor     ebx, ebx
0x180013b9d  mov     eax, ebx
0x180013b9f  add     rsp, 40h
0x180013ba3  pop     rbx
0x180013ba4  retn
0x180013ba5  mov     r9d, 0BDh
0x180013bab  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013bb2  mov     ecx, eax
0x180013bb4  lea     rdx, aStatus; "Status"
0x180013bbb  call    DebugTraceError
0x180013bc0  call    UninitializeCNGNcrypt
0x180013bc5  jmp     short loc_180013B9D
```
