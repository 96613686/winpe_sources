# InitNfsRedir

- ea: `0x14002d428`
- end: `0x14002dda3`
- name: `InitNfsRedir`
- size: `2427`
- prototype: `__int64 __fastcall(PVOID StartContext)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14002246c`

## callees

- `0x1400159cc`
- `0x1400159fc`
- `0x140016138`
- `0x140016380`
- `0x140018310`
- `0x14001db18`
- `0x140022054`
- `0x14002d428`
- `0x14002dec4`
- `0x14002e5a8`
- `0x14002e7fc`
- `0x14002e8e4`
- `0x14002eb18`
- `0x14002efe0`
- `0x140038550`
- `0x140039328`
- `0x1400393f8`
- `0x140039a60`
- `0x140039b40`
- `0x140039b90`
- `0x14003aba0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14002dcd6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14002dcd6`
- `ntoskrnl!ExInitializeResourceLite` at `0x14002d524`
- `ntoskrnl!ExInitializeResourceLite` at `0x14002d524`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002dd22`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002dd22`
- `ntoskrnl!RtlInitAnsiString` at `0x14002d79f`
- `ntoskrnl!RtlInitAnsiString` at `0x14002d7e5`
- `ntoskrnl!RtlInitAnsiString` at `0x14002d79f`
- `ntoskrnl!RtlInitAnsiString` at `0x14002d7e5`
- `ntoskrnl!KeInitializeEvent` at `0x14002d5f5`
- `ntoskrnl!KeInitializeEvent` at `0x14002d60e`
- `ntoskrnl!KeInitializeEvent` at `0x14002d5f5`
- `ntoskrnl!KeInitializeEvent` at `0x14002d60e`
- `ntoskrnl!NtClose` at `0x14002d775`
- `ntoskrnl!NtClose` at `0x14002d775`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14002d671`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14002d671`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14002d53d`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14002d53d`
- `ntoskrnl!RtlInitializeSid` at `0x14002d639`
- `ntoskrnl!RtlInitializeSid` at `0x14002d639`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002d64e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002d64e`
- `ntoskrnl!NtOpenProcessToken` at `0x14002d728`
- `ntoskrnl!NtOpenProcessToken` at `0x14002d728`
- `ntoskrnl!NtAdjustPrivilegesToken` at `0x14002d755`
- `ntoskrnl!NtAdjustPrivilegesToken` at `0x14002d755`
- `ntoskrnl!LsaRegisterLogonProcess` at `0x14002d7bd`
- `ntoskrnl!LsaRegisterLogonProcess` at `0x14002d7bd`
- `ntoskrnl!LsaLookupAuthenticationPackage` at `0x14002d7ff`
- `ntoskrnl!LsaLookupAuthenticationPackage` at `0x14002d7ff`
- `ntoskrnl!PsCreateSystemThread` at `0x14002d991`
- `ntoskrnl!PsCreateSystemThread` at `0x14002d991`
- `ntoskrnl!KeInitializeMutex` at `0x14002d5b2`
- `ntoskrnl!KeInitializeMutex` at `0x14002d5c7`
- `ntoskrnl!KeInitializeMutex` at `0x14002d5dc`
- `ntoskrnl!KeInitializeMutex` at `0x14002d5b2`
- `ntoskrnl!KeInitializeMutex` at `0x14002d5c7`
- `ntoskrnl!KeInitializeMutex` at `0x14002d5dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002dcf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002dd0a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002dd37`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002dcf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002dd0a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002dd37`
- `ntoskrnl!ExAllocatePool2` at `0x14002d4d1`
- `ntoskrnl!ExAllocatePool2` at `0x14002d556`
- `ntoskrnl!ExAllocatePool2` at `0x14002d4d1`
- `ntoskrnl!ExAllocatePool2` at `0x14002d556`
- `rpcxdr!OncRpcEndpointOpen` at `0x14002da86`
- `rpcxdr!OncRpcEndpointOpen` at `0x14002db09`
- `rpcxdr!OncRpcEndpointOpen` at `0x14002da86`
- `rpcxdr!OncRpcEndpointOpen` at `0x14002db09`
- `rpcxdr!OncRpcEndpointClose` at `0x14002dc2b`
- `rpcxdr!OncRpcEndpointClose` at `0x14002dc73`
- `rpcxdr!OncRpcEndpointClose` at `0x14002dc2b`
- `rpcxdr!OncRpcEndpointClose` at `0x14002dc73`

## pseudocode

```c
__int64 __fastcall InitNfsRedir(char *StartContext)
{
  char v2; // r14
  struct _ERESOURCE *Pool2; // rax
  PDEVICE_OBJECT v4; // rcx
  __int64 v5; // rdx
  int Registry; // edi
  ULONG v7; // eax
  __int64 v8; // rax
  void *v9; // rcx
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // ebx
  int v13; // eax
  char v14; // r15
  __int64 v15; // r8
  int v16; // r9d
  __int64 v17; // r8
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  void *v20; // rcx
  void *v21; // rcx
  struct _ERESOURCE *v22; // rcx
  __int64 v24; // [rsp+40h] [rbp-49h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-41h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+50h] [rbp-39h] BYREF
  _BYTE NewState[24]; // [rsp+58h] [rbp-31h] BYREF
  int v28; // [rsp+70h] [rbp-19h]
  __int64 v29; // [rsp+78h] [rbp-11h] BYREF
  int v30; // [rsp+80h] [rbp-9h]
  int v31; // [rsp+84h] [rbp-5h]
  char v32[16]; // [rsp+88h] [rbp-1h] BYREF

  v2 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  LODWORD(v24) = 0;
  v29 = 0;
  v30 = 0;
  v31 = 3;
  strcpy(v32, "InitNfsRedir");
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids);
  Pool2 = (struct _ERESOURCE *)ExAllocatePool2(66, 104, 1666344526);
  *((_QWORD *)StartContext + 183) = Pool2;
  if ( !Pool2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_9;
    v5 = 11;
LABEL_8:
    WPP_SF_(v4->AttachedDevice, v5, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids);
LABEL_9:
    Registry = -1073741670;
    goto LABEL_88;
  }
  Registry = ExInitializeResourceLite(Pool2);
  if ( Registry >= 0 )
  {
    v7 = RtlLengthRequiredSid(1u);
    v8 = ExAllocatePool2(258, v7, 1800562254);
    *((_QWORD *)StartContext + 248) = v8;
    if ( !v8 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_9;
      v5 = 12;
      goto LABEL_8;
    }
    Registry = NfsInitialiseServiceSecDesc((struct _ACL **)StartContext + 249, StartContext + 2040);
    if ( Registry >= 0 )
    {
      KeInitializeMutex((PRKMUTEX)(StartContext + 2208), 0);
      KeInitializeMutex((PRKMUTEX)(StartContext + 2096), 0);
      KeInitializeMutex((PRKMUTEX)(StartContext + 2152), 0);
      KeInitializeEvent((PRKEVENT)(StartContext + 2264), SynchronizationEvent, 0);
      KeInitializeEvent((PRKEVENT)(StartContext + 2288), SynchronizationEvent, 0);
      v9 = (void *)*((_QWORD *)StartContext + 248);
      *((_DWORD *)StartContext + 583) = -2;
      *((_DWORD *)StartContext + 584) = -2;
      RtlInitializeSid(v9, &IdentifierAuthority, 1u);
      *RtlSubAuthoritySid(*((PSID *)StartContext + 248), 0) = 18;
      Registry = RtlConvertSidToUnicodeString((PUNICODE_STRING)StartContext + 130, *((PSID *)StartContext + 248), 1u);
      if ( Registry < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_88;
        v11 = 14;
        goto LABEL_20;
      }
      Registry = NfsUpCallCreateRequestQueue(StartContext + 2016);
      if ( Registry < 0 )
        goto LABEL_88;
      Registry = NfsUpCallInitializeRequestQueue(*((_QWORD *)StartContext + 252));
      if ( Registry < 0 )
        goto LABEL_88;
      *((_DWORD *)StartContext + 350) = 0x200000;
      *((_QWORD *)StartContext + 176) = StartContext + 1316;
      v12 = 32;
      StartContext[1316] = 0;
      TokenHandle = (void *)-1LL;
      *(_DWORD *)NewState = 1;
      *(_QWORD *)&NewState[4] = 7;
      *(_DWORD *)&NewState[12] = 2;
      Registry = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x20u, &TokenHandle);
      if ( Registry < 0 )
        goto LABEL_88;
      Registry = NtAdjustPrivilegesToken(TokenHandle, 0, (PTOKEN_PRIVILEGES)NewState, 0, 0, 0);
      if ( Registry == 262 )
        Registry = -1073741790;
      NtClose(TokenHandle);
      if ( Registry < 0 )
        goto LABEL_88;
      LODWORD(TokenHandle) = 0;
      *(_OWORD *)NewState = 0;
      RtlInitAnsiString((PANSI_STRING)NewState, "ClientForNFS");
      Registry = LsaRegisterLogonProcess(
                   (PLSA_STRING)NewState,
                   (PHANDLE)StartContext + 253,
                   (PLSA_OPERATIONAL_MODE)&TokenHandle);
      if ( Registry < 0 )
        goto LABEL_88;
      *(_OWORD *)NewState = 0;
      RtlInitAnsiString((PANSI_STRING)NewState, "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0");
      Registry = LsaLookupAuthenticationPackage(*((_QWORD *)StartContext + 253), NewState, StartContext + 2032);
      if ( Registry < 0 )
        goto LABEL_88;
      MdaReadRegistrySettings(StartContext);
      NfsRdrpReadStartupRegistrySettings(StartContext);
      NfsRdrpInitAutomountDfsMaps(StartContext);
      if ( (int)NfsReadRegistry(
                  &stru_140041080,
                  L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default",
                  (__int64)&v24,
                  4) >= 0 )
      {
        v12 = v24;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_SD(WPP_GLOBAL_Control->AttachedDevice);
        LODWORD(v24) = 32;
      }
      Registry = NuiInit(v12);
      if ( Registry < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_88;
        v11 = 16;
LABEL_20:
        WPP_SF_d(v10->AttachedDevice, v11, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids);
        goto LABEL_88;
      }
      Registry = NfsReadRegistry(
                   &stru_140041080,
                   L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Auth",
                   (__int64)&v24,
                   4);
      if ( Registry < 0 )
      {
        v13 = v24;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids);
        v13 = v24;
        if ( (_DWORD)v24 )
        {
          if ( (_DWORD)v24 == 5 )
            goto LABEL_48;
          v13 = 0;
          LODWORD(v24) = 0;
        }
      }
      if ( v13 != 5 )
      {
        Registry = PsCreateSystemThread(
                     (PHANDLE)StartContext + 179,
                     0x1FFFFFu,
                     0,
                     0,
                     0,
                     MdaUserCacheThread,
                     StartContext);
        if ( Registry < 0 )
        {
          v2 = 1;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_sD(
              WPP_GLOBAL_Control->AttachedDevice,
              18,
              (unsigned int)WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids,
              (unsigned int)v32,
              Registry);
          }
          goto LABEL_88;
        }
        goto LABEL_54;
      }
LABEL_48:
      MapReadMappingServerFromRegistry(StartContext);
      if ( Registry < 0 )
      {
        v2 = 1;
        goto LABEL_88;
      }
LABEL_54:
      Registry = NfsRdrCryptoInit((BCRYPT_ALG_HANDLE *)StartContext + 169);
      if ( Registry >= 0 )
      {
        v14 = 1;
      }
      else
      {
        v14 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_sD(
            WPP_GLOBAL_Control->AttachedDevice,
            19,
            (unsigned int)WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids,
            (unsigned int)v32,
            Registry);
      }
      v2 = 1;
      if ( Registry < 0 )
        goto LABEL_76;
      v15 = *((_DWORD *)StartContext + 579) >> 10;
      *(_QWORD *)&NewState[16] = 0;
      LOBYTE(v15) = v15 & 1;
      v28 = 0;
      *(_QWORD *)NewState = 2;
      *(_QWORD *)&NewState[8] = 0;
      v16 = OncRpcEndpointOpen(&v29, NewState, v15, 17, 0, 0, StartContext + 1440);
      if ( v16 == -1073700845 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids);
      }
      else if ( v16 < 0 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_83;
        v19 = 21;
        goto LABEL_82;
      }
      v17 = *((_DWORD *)StartContext + 579) >> 10;
      LOBYTE(v17) = (*((_DWORD *)StartContext + 579) & 0x400) != 0;
      *(_QWORD *)NewState = 23;
      v28 = 0;
      *(_OWORD *)&NewState[8] = 0;
      Registry = OncRpcEndpointOpen(&v29, NewState, v17, 17, 0, 0, StartContext + 1448);
      if ( Registry == -1073700845 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids);
        Registry = 0;
        goto LABEL_69;
      }
      if ( Registry >= 0 )
      {
LABEL_69:
        if ( *((_QWORD *)StartContext + 180) || *((_QWORD *)StartContext + 181) )
          goto LABEL_108;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids);
        Registry = -1073700845;
        goto LABEL_75;
      }
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      {
LABEL_83:
        Registry = -1073741670;
LABEL_75:
        v2 = 1;
LABEL_76:
        if ( v14 )
          NfsRdrCryptoTeardown(StartContext + 1352);
        goto LABEL_88;
      }
      v19 = 23;
LABEL_82:
      WPP_SF_d(v18->AttachedDevice, v19, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids);
      goto LABEL_83;
    }
  }
LABEL_88:
  if ( *((_QWORD *)StartContext + 181)
    && (int)OncRpcEndpointClose() < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids);
  }
  if ( *((_QWORD *)StartContext + 180)
    && (int)OncRpcEndpointClose() < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids);
  }
  NfsUpCallShutdownRequestQueue(*((_QWORD *)StartContext + 252));
  NfsUpCallDestroyRequestQueue(StartContext + 2016);
  if ( *((_QWORD *)StartContext + 261) )
    RtlFreeUnicodeString((PUNICODE_STRING)StartContext + 130);
  v20 = (void *)*((_QWORD *)StartContext + 248);
  if ( v20 )
    ExFreePoolWithTag(v20, 0);
  v21 = (void *)*((_QWORD *)StartContext + 249);
  if ( v21 )
    ExFreePoolWithTag(v21, 0);
  v22 = (struct _ERESOURCE *)*((_QWORD *)StartContext + 183);
  if ( v22 )
  {
    ExDeleteResourceLite(v22);
    ExFreePoolWithTag(*((PVOID *)StartContext + 183), 0);
  }
  if ( v2 )
    NuiFinish();
LABEL_108:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids, v32);
  return (unsigned int)Registry;
}

```

## disassembly

```asm
0x14002d428  push    rbp
0x14002d42a  push    rbx
0x14002d42b  push    rsi
0x14002d42c  push    rdi
0x14002d42d  push    r12
0x14002d42f  push    r13
0x14002d431  push    r14
0x14002d433  push    r15
0x14002d435  lea     rbp, [rsp-1Fh]
0x14002d43a  sub     rsp, 0A8h
0x14002d441  mov     rax, cs:__security_cookie
0x14002d448  xor     rax, rsp
0x14002d44b  mov     [rbp+57h+var_48], rax
0x14002d44f  mov     eax, dword ptr cs:aInitnfsredir+8; "edir"
0x14002d455  xor     r12d, r12d
0x14002d458  movsd   xmm0, qword ptr cs:aInitnfsredir; "InitNfsRedir"
0x14002d460  mov     rsi, rcx
0x14002d463  mov     dword ptr [rbp+57h+var_58+8], eax
0x14002d466  mov     r14b, r12b
0x14002d469  mov     al, byte ptr cs:aInitnfsredir+0Ch; ""
0x14002d46f  mov     [rbp+57h+var_58+0Ch], al
0x14002d472  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r12d
0x14002d476  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x14002d47c  mov     dword ptr [rbp+57h+var_A0], r12d
0x14002d480  mov     [rbp+57h+var_68], r12
0x14002d484  mov     [rbp+57h+var_60], r12d
0x14002d488  mov     [rbp+57h+var_5C], 3
0x14002d48f  movsd   qword ptr [rbp+57h+var_58], xmm0
0x14002d494  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d49b  lea     rbx, WPP_GLOBAL_Control
0x14002d4a2  cmp     rcx, rbx
0x14002d4a5  jz      short loc_14002D4C3
0x14002d4a7  mov     eax, [rcx+2Ch]
0x14002d4aa  test    al, 8
0x14002d4ac  jz      short loc_14002D4C3
0x14002d4ae  mov     rcx, [rcx+18h]
0x14002d4b2  lea     edx, [r12+0Ah]
0x14002d4b7  lea     r8, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids
0x14002d4be  call    WPP_SF_
0x14002d4c3  mov     edx, 68h ; 'h'
0x14002d4c8  mov     r8d, 6352664Eh
0x14002d4ce  lea     ecx, [rdx-26h]
0x14002d4d1  call    cs:__imp_ExAllocatePool2
0x14002d4d8  nop     dword ptr [rax+rax+00h]
0x14002d4dd  mov     [rsi+5B8h], rax
0x14002d4e4  mov     r13d, 1
0x14002d4ea  test    rax, rax
0x14002d4ed  jnz     short loc_14002D521
0x14002d4ef  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d4f6  cmp     rcx, rbx
0x14002d4f9  jz      short loc_14002D517
0x14002d4fb  mov     eax, [rcx+2Ch]
0x14002d4fe  test    r13b, al
0x14002d501  jz      short loc_14002D517
0x14002d503  lea     edx, [r13+0Ah]
0x14002d507  mov     rcx, [rcx+18h]
0x14002d50b  lea     r8, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids
0x14002d512  call    WPP_SF_
0x14002d517  mov     edi, 0C000009Ah
0x14002d51c  jmp     loc_14002DC1F
0x14002d521  mov     rcx, rax; Resource
0x14002d524  call    cs:__imp_ExInitializeResourceLite
0x14002d52b  nop     dword ptr [rax+rax+00h]
0x14002d530  mov     edi, eax
0x14002d532  test    eax, eax
0x14002d534  js      loc_14002DC1F
0x14002d53a  mov     ecx, r13d; SubAuthorityCount
0x14002d53d  call    cs:__imp_RtlLengthRequiredSid
0x14002d544  nop     dword ptr [rax+rax+00h]
0x14002d549  mov     edx, eax
0x14002d54b  mov     ecx, 102h
0x14002d550  mov     r8d, 6B52664Eh
0x14002d556  call    cs:__imp_ExAllocatePool2
0x14002d55d  nop     dword ptr [rax+rax+00h]
0x14002d562  mov     [rsi+7C0h], rax
0x14002d569  test    rax, rax
0x14002d56c  jnz     short loc_14002D58C
0x14002d56e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d575  cmp     rcx, rbx
0x14002d578  jz      short loc_14002D517
0x14002d57a  mov     eax, [rcx+2Ch]
0x14002d57d  test    r13b, al
0x14002d580  jz      short loc_14002D517
0x14002d582  mov     edx, 0Ch
0x14002d587  jmp     loc_14002D507
0x14002d58c  lea     rdx, [rsi+7F8h]
0x14002d593  lea     rcx, [rsi+7C8h]
0x14002d59a  call    NfsInitialiseServiceSecDesc
0x14002d59f  mov     edi, eax
0x14002d5a1  test    eax, eax
0x14002d5a3  js      loc_14002DC1F
0x14002d5a9  lea     rcx, [rsi+8A0h]; Mutex
0x14002d5b0  xor     edx, edx; Level
0x14002d5b2  call    cs:__imp_KeInitializeMutex
0x14002d5b9  nop     dword ptr [rax+rax+00h]
0x14002d5be  lea     rcx, [rsi+830h]; Mutex
0x14002d5c5  xor     edx, edx; Level
0x14002d5c7  call    cs:__imp_KeInitializeMutex
0x14002d5ce  nop     dword ptr [rax+rax+00h]
0x14002d5d3  lea     rcx, [rsi+868h]; Mutex
0x14002d5da  xor     edx, edx; Level
0x14002d5dc  call    cs:__imp_KeInitializeMutex
0x14002d5e3  nop     dword ptr [rax+rax+00h]
0x14002d5e8  lea     rcx, [rsi+8D8h]; Event
0x14002d5ef  xor     r8d, r8d; State
0x14002d5f2  mov     edx, r13d; Type
0x14002d5f5  call    cs:__imp_KeInitializeEvent
0x14002d5fc  nop     dword ptr [rax+rax+00h]
0x14002d601  lea     rcx, [rsi+8F0h]; Event
0x14002d608  xor     r8d, r8d; State
0x14002d60b  mov     edx, r13d; Type
0x14002d60e  call    cs:__imp_KeInitializeEvent
0x14002d615  nop     dword ptr [rax+rax+00h]
0x14002d61a  mov     rcx, [rsi+7C0h]; Sid
0x14002d621  lea     rdx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x14002d625  mov     eax, 0FFFFFFFEh
0x14002d62a  mov     r8b, r13b; SubAuthorityCount
0x14002d62d  mov     [rsi+91Ch], eax
0x14002d633  mov     [rsi+920h], eax
0x14002d639  call    cs:__imp_RtlInitializeSid
0x14002d640  nop     dword ptr [rax+rax+00h]
0x14002d645  mov     rcx, [rsi+7C0h]; Sid
0x14002d64c  xor     edx, edx; SubAuthority
0x14002d64e  call    cs:__imp_RtlSubAuthoritySid
0x14002d655  nop     dword ptr [rax+rax+00h]
0x14002d65a  lea     rcx, [rsi+820h]; UnicodeString
0x14002d661  mov     r8b, r13b; AllocateDestinationString
0x14002d664  mov     dword ptr [rax], 12h
0x14002d66a  mov     rdx, [rsi+7C0h]; Sid
0x14002d671  call    cs:__imp_RtlConvertSidToUnicodeString
0x14002d678  nop     dword ptr [rax+rax+00h]
0x14002d67d  mov     edi, eax
0x14002d67f  test    eax, eax
0x14002d681  jns     short loc_14002D6BC
0x14002d683  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d68a  cmp     rcx, rbx
0x14002d68d  jz      loc_14002DC1F
0x14002d693  mov     eax, [rcx+2Ch]
0x14002d696  test    r13b, al
0x14002d699  jz      loc_14002DC1F
0x14002d69f  mov     edx, 0Eh
0x14002d6a4  mov     rcx, [rcx+18h]
0x14002d6a8  lea     r8, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids
0x14002d6af  mov     r9d, edi
0x14002d6b2  call    WPP_SF_d
0x14002d6b7  jmp     loc_14002DC1F
0x14002d6bc  lea     rbx, [rsi+7E0h]
0x14002d6c3  mov     rcx, rbx
0x14002d6c6  call    NfsUpCallCreateRequestQueue
0x14002d6cb  mov     edi, eax
0x14002d6cd  test    eax, eax
0x14002d6cf  js      loc_14002DC18
0x14002d6d5  mov     rcx, [rbx]
0x14002d6d8  call    NfsUpCallInitializeRequestQueue
0x14002d6dd  mov     edi, eax
0x14002d6df  test    eax, eax
0x14002d6e1  js      loc_14002DC18
0x14002d6e7  lea     rax, [rsi+524h]
0x14002d6ee  mov     dword ptr [rsi+578h], 200000h
0x14002d6f8  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14002d6fc  mov     [rsi+580h], rax
0x14002d703  mov     ebx, 20h ; ' '
0x14002d708  mov     [rax], r12b
0x14002d70b  mov     edx, ebx; DesiredAccess
0x14002d70d  mov     [rbp+57h+TokenHandle], rcx
0x14002d711  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x14002d715  mov     dword ptr [rbp+57h+NewState], r13d
0x14002d719  mov     qword ptr [rbp+57h+NewState+4], 7
0x14002d721  mov     dword ptr [rbp+57h+NewState+0Ch], 2
0x14002d728  call    cs:__imp_NtOpenProcessToken
0x14002d72f  nop     dword ptr [rax+rax+00h]
0x14002d734  mov     edi, eax
0x14002d736  test    eax, eax
0x14002d738  js      loc_14002DC18
0x14002d73e  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x14002d742  lea     r8, [rbp+57h+NewState]; NewState
0x14002d746  mov     [rsp+0E0h+ReturnLength], r12; ReturnLength
0x14002d74b  xor     r9d, r9d; BufferLength
0x14002d74e  xor     edx, edx; DisableAllPrivileges
0x14002d750  mov     [rsp+0E0h+PreviousState], r12; PreviousState
0x14002d755  call    cs:__imp_NtAdjustPrivilegesToken
0x14002d75c  nop     dword ptr [rax+rax+00h]
0x14002d761  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x14002d765  mov     edi, eax
0x14002d767  mov     eax, 0C0000022h
0x14002d76c  cmp     edi, 106h
0x14002d772  cmovz   edi, eax
0x14002d775  call    cs:__imp_NtClose
0x14002d77c  nop     dword ptr [rax+rax+00h]
0x14002d781  test    edi, edi
0x14002d783  js      loc_14002DC18
0x14002d789  xorps   xmm0, xmm0
0x14002d78c  mov     dword ptr [rbp+57h+TokenHandle], r12d
0x14002d790  lea     rdx, aClientfornfs; "ClientForNFS"
0x14002d797  lea     rcx, [rbp+57h+NewState]; DestinationString
0x14002d79b  movups  xmmword ptr [rbp+57h+NewState], xmm0
0x14002d79f  call    cs:__imp_RtlInitAnsiString
0x14002d7a6  nop     dword ptr [rax+rax+00h]
0x14002d7ab  lea     r15, [rsi+7E8h]
0x14002d7b2  mov     rdx, r15; LsaHandle
0x14002d7b5  lea     r8, [rbp+57h+TokenHandle]; SecurityMode
0x14002d7b9  lea     rcx, [rbp+57h+NewState]; LogonProcessName
0x14002d7bd  call    cs:__imp_LsaRegisterLogonProcess
0x14002d7c4  nop     dword ptr [rax+rax+00h]
0x14002d7c9  mov     edi, eax
0x14002d7cb  test    eax, eax
0x14002d7cd  js      loc_14002DC18
0x14002d7d3  xorps   xmm0, xmm0
0x14002d7d6  lea     rdx, aMicrosoftAuthe; "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0"
0x14002d7dd  lea     rcx, [rbp+57h+NewState]; DestinationString
0x14002d7e1  movups  xmmword ptr [rbp+57h+NewState], xmm0
0x14002d7e5  call    cs:__imp_RtlInitAnsiString
0x14002d7ec  nop     dword ptr [rax+rax+00h]
0x14002d7f1  mov     rcx, [r15]
0x14002d7f4  lea     r8, [rsi+7F0h]
0x14002d7fb  lea     rdx, [rbp+57h+NewState]
0x14002d7ff  call    cs:__imp_LsaLookupAuthenticationPackage
0x14002d806  nop     dword ptr [rax+rax+00h]
0x14002d80b  mov     edi, eax
0x14002d80d  test    eax, eax
0x14002d80f  js      loc_14002DC18
0x14002d815  mov     rcx, rsi
0x14002d818  call    MdaReadRegistrySettings
0x14002d81d  mov     rcx, rsi
0x14002d820  call    NfsRdrpReadStartupRegistrySettings
0x14002d825  mov     rcx, rsi
0x14002d828  call    NfsRdrpInitAutomountDfsMaps
0x14002d82d  lea     r15d, [rbx-1Ch]
0x14002d831  lea     rax, [rbp+57h+var_A0]
0x14002d835  mov     dword ptr [rsp+0E0h+ReturnLength], r15d; int
0x14002d83a  mov     r9d, r15d
0x14002d83d  mov     [rsp+0E0h+PreviousState], rax; __int64
0x14002d842  lea     r8, aMaxnfsuser; "MaxNfsUser"
0x14002d849  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x14002d850  lea     rcx, stru_140041080; SourceString
0x14002d857  call    NfsReadRegistry
0x14002d85c  test    eax, eax
0x14002d85e  jns     short loc_14002D88D
0x14002d860  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d867  lea     rdx, WPP_GLOBAL_Control
0x14002d86e  cmp     rcx, rdx
0x14002d871  jz      short loc_14002D888
0x14002d873  mov     edx, [rcx+2Ch]
0x14002d876  test    dl, 2
0x14002d879  jz      short loc_14002D888
0x14002d87b  mov     rcx, [rcx+18h]
0x14002d87f  mov     dword ptr [rsp+0E0h+PreviousState], eax
0x14002d883  call    WPP_SF_SD
0x14002d888  mov     dword ptr [rbp+57h+var_A0], ebx
0x14002d88b  jmp     short loc_14002D890
0x14002d88d  mov     ebx, dword ptr [rbp+57h+var_A0]
0x14002d890  mov     ecx, ebx
0x14002d892  call    NuiInit
0x14002d897  mov     edi, eax
0x14002d899  test    eax, eax
0x14002d89b  jns     short loc_14002D8CA
0x14002d89d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d8a4  lea     rbx, WPP_GLOBAL_Control
0x14002d8ab  cmp     rcx, rbx
0x14002d8ae  jz      loc_14002DC1F
0x14002d8b4  mov     eax, [rcx+2Ch]
0x14002d8b7  test    r13b, al
0x14002d8ba  jz      loc_14002DC1F
0x14002d8c0  mov     edx, 10h
0x14002d8c5  jmp     loc_14002D6A4
0x14002d8ca  lea     rax, [rbp+57h+var_A0]
0x14002d8ce  mov     dword ptr [rsp+0E0h+ReturnLength], r15d; int
0x14002d8d3  mov     r9d, r15d
0x14002d8d6  mov     [rsp+0E0h+PreviousState], rax; __int64
0x14002d8db  lea     r8, aAuthtype; "AuthType"
0x14002d8e2  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x14002d8e9  lea     rcx, stru_140041080; SourceString
0x14002d8f0  call    NfsReadRegistry
0x14002d8f5  mov     edi, eax
0x14002d8f7  test    eax, eax
0x14002d8f9  js      short loc_14002D942
0x14002d8fb  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d902  lea     rbx, WPP_GLOBAL_Control
0x14002d909  cmp     rcx, rbx
0x14002d90c  jz      short loc_14002D92E
0x14002d90e  mov     eax, [rcx+2Ch]
0x14002d911  test    al, 2
0x14002d913  jz      short loc_14002D92E
0x14002d915  mov     r9d, dword ptr [rbp+57h+var_A0]
0x14002d919  lea     r8, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids
0x14002d920  mov     rcx, [rcx+18h]
0x14002d924  mov     edx, 11h
0x14002d929  call    WPP_SF_d
0x14002d92e  mov     eax, dword ptr [rbp+57h+var_A0]
0x14002d931  test    eax, eax
0x14002d933  jz      short loc_14002D94C
0x14002d935  cmp     eax, 5
0x14002d938  jz      short loc_14002D951
0x14002d93a  mov     eax, r12d
0x14002d93d  mov     dword ptr [rbp+57h+var_A0], eax
0x14002d940  jmp     short loc_14002D94C
0x14002d942  mov     eax, dword ptr [rbp+57h+var_A0]
0x14002d945  lea     rbx, WPP_GLOBAL_Control
0x14002d94c  cmp     eax, 5
0x14002d94f  jnz     short loc_14002D969
  ... truncated ...
```
