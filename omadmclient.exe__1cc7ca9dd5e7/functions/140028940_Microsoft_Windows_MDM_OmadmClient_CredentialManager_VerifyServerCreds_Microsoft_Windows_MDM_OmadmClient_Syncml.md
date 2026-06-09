# Microsoft::Windows::MDM::OmadmClient::CredentialManager::VerifyServerCreds(Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState &,int *)

- ea: `0x140028940`
- end: `0x140029099`
- name: `?VerifyServerCreds@CredentialManager@OmadmClient@MDM@Windows@Microsoft@@IEAAJAEAVSyncmlSessionState@2345@PEAH@Z`
- size: `1881`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::CredentialManager *__hidden this, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1400285f0`

## callees

- `0x140003450`
- `0x14000b0f4`
- `0x14000d71c`
- `0x14000d778`
- `0x14000e610`
- `0x140011678`
- `0x140013404`
- `0x140026628`
- `0x140026eac`
- `0x140028940`
- `0x1400552f8`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028e83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028f1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028e83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028f1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140028ea2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140028f3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140028ea2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140028f3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140028da3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140028e65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140028e94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140028f2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140028f7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140028ff2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140028da3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140028e65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140028e94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140028f2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140028f7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140028ff2`
- `DMCmnUtils!CopyString` at `0x140028b7f`
- `DMCmnUtils!CopyString` at `0x140028b7f`
- `DMCmnUtils!InvStrCmpW` at `0x140028bd7`
- `DMCmnUtils!InvStrCmpW` at `0x140028dd5`
- `DMCmnUtils!InvStrCmpW` at `0x140028e07`
- `DMCmnUtils!InvStrCmpW` at `0x140028faa`
- `DMCmnUtils!InvStrCmpW` at `0x140028bd7`
- `DMCmnUtils!InvStrCmpW` at `0x140028dd5`
- `DMCmnUtils!InvStrCmpW` at `0x140028e07`
- `DMCmnUtils!InvStrCmpW` at `0x140028faa`
- `omadmapi!__imp_OmaDmIsNodeValuePresent` at `0x140028c29`
- `omadmapi!__imp_OmaDmIsNodeValuePresent` at `0x140028c29`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140028a4f`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140028af9`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140028b3c`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140028c54`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140028a4f`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140028af9`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140028b3c`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140028c54`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::CredentialManager::VerifyServerCreds(
        Microsoft::Windows::MDM::OmadmClient::CredentialManager *this,
        struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *a2,
        int *a3)
{
  unsigned __int16 *v6; // r14
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rcx
  int ValueFromStruct; // eax
  Microsoft::Windows::MDM::OmadmClient::CredentialManager *Ptr; // rcx
  __int64 v13; // r8
  unsigned int v14; // ebx
  bool v15; // zf
  __int64 v16; // r9
  const unsigned __int16 **v17; // rsi
  int v18; // eax
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  char v22; // al
  bool v23; // zf
  const BYTE **v24; // r9
  int v25; // eax
  __int64 v26; // r8
  void *v27; // rsi
  DWORD LastError; // ebx
  void *v29; // rsi
  DWORD v30; // ebx
  __int64 v31; // rcx
  __int64 *v32; // rdx
  unsigned __int16 *v34; // [rsp+20h] [rbp-108h]
  unsigned __int16 *v35; // [rsp+20h] [rbp-108h]
  unsigned int v36; // [rsp+50h] [rbp-D8h] BYREF
  int v37; // [rsp+58h] [rbp-D0h] BYREF
  Microsoft::Windows::MDM::OmadmClient::CredentialManager *v38; // [rsp+60h] [rbp-C8h] BYREF
  BYTE **v39; // [rsp+68h] [rbp-C0h] BYREF
  _QWORD v40[3]; // [rsp+70h] [rbp-B8h] BYREF
  int v41; // [rsp+88h] [rbp-A0h]
  unsigned int *v42; // [rsp+90h] [rbp-98h]
  const unsigned __int16 **v43; // [rsp+98h] [rbp-90h] BYREF
  _QWORD v44[2]; // [rsp+A0h] [rbp-88h] BYREF
  char v45; // [rsp+B0h] [rbp-78h]
  struct _EVENT_DATA_DESCRIPTOR hMem; // [rsp+B8h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+C8h] [rbp-60h] BYREF
  int *v48; // [rsp+D8h] [rbp-50h]
  __int64 v49; // [rsp+E0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v6 = 0;
  v36 = 0;
  v40[0] = 0;
  v40[1] = "VerifyServerCreds";
  v40[2] = COmaDmLogger::GetLogger();
  v10 = 2;
  v41 = 2;
  v42 = &v36;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    v37 = 24;
    v48 = &v37;
    v49 = 4;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)OmaDmClientFunctionEntryPointEvent,
      v8,
      2u,
      &v47);
  }
  v44[1] = &v36;
  v45 = 1;
  if ( (*((_BYTE *)a2 + 1908) & 4) == 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v10, v7, v8, v9, v34);
  *a3 = 0;
  v38 = 0;
  v39 = 0;
  ValueFromStruct = OmaDmGetValueFromStruct(19, (char *)a2 + 48, *((unsigned int *)a2 + 157), &v39, &v38);
  v14 = ValueFromStruct;
  v36 = ValueFromStruct;
  if ( ValueFromStruct < 0 )
  {
    LODWORD(v40[0]) = 6026;
LABEL_7:
    HIDWORD(v40[0]) = ValueFromStruct;
    v15 = (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) == 0;
    goto LABEL_8;
  }
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 1) != 0 )
  {
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)VerifyServerCredsPrimaryNonce,
      v13,
      1u,
      &hMem);
    (*(void (__fastcall **)(_QWORD, BYTE *, _QWORD))(**((_QWORD **)this + 1) + 24LL))(
      *((_QWORD *)this + 1),
      *v39,
      *(unsigned int *)v38);
  }
  v44[0] = 0;
  ValueFromStruct = OmaDmGetValueFromStruct(18, (char *)a2 + 48, *((unsigned int *)a2 + 157), v44, 0);
  v14 = ValueFromStruct;
  v36 = ValueFromStruct;
  if ( ValueFromStruct < 0 )
  {
    LODWORD(v40[0]) = 6027;
    goto LABEL_7;
  }
  v43 = 0;
  ValueFromStruct = OmaDmGetValueFromStruct(2, (char *)a2 + 48, 0xFFFFFFFFLL, &v43, 0);
  v14 = ValueFromStruct;
  v36 = ValueFromStruct;
  if ( ValueFromStruct < 0 )
  {
    LODWORD(v40[0]) = 6028;
    goto LABEL_7;
  }
  v17 = (const unsigned __int16 **)((char *)a2 + 584);
  if ( !*((_QWORD *)a2 + 73) )
  {
    *v17 = 0;
    v18 = CopyString(*v43, 0xFFFFFFFF, (unsigned __int16 **)a2 + 73);
    v14 = v18;
    v36 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3D8,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\credentialmanager.cpp",
        (const char *)(unsigned int)v18,
        (int)v35);
      goto LABEL_19;
    }
  }
  if ( !InvStrCmpW(*v17, *v43) )
    v6 = (unsigned __int16 *)*v17;
  if ( (*((_BYTE *)a2 + 1908) & 3) != 3 || !*((_QWORD *)a2 + 71) && *((_DWORD *)a2 + 158) != 2 || !v6 )
  {
LABEL_67:
    if ( *a3 )
    {
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 1) != 0 )
      {
        v32 = SuccessfulServerAuthenticationEvent;
LABEL_72:
        McGenEventWrite_EventWriteTransfer(
          (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)v32,
          v19,
          1u,
          &v47);
      }
    }
    else if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 2) != 0 )
    {
      v32 = FailedToAuthenticateServerEvent;
      goto LABEL_72;
    }
    v14 = v36;
    v23 = (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) == 0;
LABEL_74:
    if ( !v23 )
    {
      v16 = v14;
      goto LABEL_76;
    }
    goto LABEL_77;
  }
  if ( (unsigned int)OmaDmIsNodeValuePresent(37, (char *)a2 + 48) )
  {
    v14 = OmaDmGetValueFromStruct(37, (char *)a2 + 48, 0xFFFFFFFFLL, &v39, &v38);
    v36 = v14;
    v22 = Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits;
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 1) != 0 )
    {
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)VerifyServerCredsSecondaryNonce,
        v21,
        1u,
        &v47);
      (*(void (__fastcall **)(_QWORD, BYTE *, _QWORD))(**((_QWORD **)this + 1) + 24LL))(
        *((_QWORD *)this + 1),
        *v39,
        *(unsigned int *)v38);
      v14 = v36;
      v22 = Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits;
    }
    if ( (v14 & 0x80000000) != 0 )
    {
      LODWORD(v40[0]) = 6029;
      HIDWORD(v40[0]) = v14;
      v23 = (v22 & 8) == 0;
      goto LABEL_74;
    }
    v24 = (const BYTE **)v39;
    if ( !*v39 || (Ptr = v38, !*(_DWORD *)v38) )
    {
      v40[0] = 0x8000FFFF00003AB2uLL;
      if ( (v22 & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(Ptr, OmaDmClientFunctionReturnValueEvent, 24, v14);
      v14 = -2147418113;
      goto LABEL_77;
    }
  }
  else
  {
    Ptr = v38;
    v24 = (const BYTE **)v39;
  }
  hMem.Ptr = 0;
  if ( *((_DWORD *)a2 + 158) != 2 )
  {
    hMem.Ptr = 0;
    v25 = Microsoft::Windows::MDM::OmadmClient::CredentialManager::CalcMd5CredHash(
            Ptr,
            v6,
            *(const unsigned __int16 **)v44[0],
            *v24,
            *(_DWORD *)Ptr,
            (unsigned __int16 **)&hMem);
    v14 = v25;
    v16 = (unsigned int)v25;
    v36 = v25;
    if ( v25 < 0 )
    {
      LODWORD(v40[0]) = 15009;
      HIDWORD(v40[0]) = v25;
      Ptr = (Microsoft::Windows::MDM::OmadmClient::CredentialManager *)hMem.Ptr;
      if ( hMem.Ptr )
      {
        LocalFree((HLOCAL)hMem.Ptr);
        v16 = v36;
      }
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        goto LABEL_76;
      goto LABEL_77;
    }
    if ( InvStrCmpW((const unsigned __int16 *)hMem.Ptr, *((const unsigned __int16 **)a2 + 71)) )
      goto LABEL_65;
    goto LABEL_62;
  }
  if ( !*((_QWORD *)a2 + 247) )
    MicrosoftTelemetryAssertTriggeredNoArgs(Ptr, v20, v21, v24, v35);
  if ( !InvStrCmpW(v6, *((const unsigned __int16 **)a2 + 236)) )
  {
    v27 = (void *)hMem.Ptr;
    if ( hMem.Ptr )
    {
      LastError = GetLastError();
      LocalFree(v27);
      SetLastError(LastError);
    }
    hMem.Ptr = 0;
    ValueFromStruct = Microsoft::Windows::MDM::OmadmClient::CredentialManager::CalcHmacCredHashWorker(
                        this,
                        0,
                        *((unsigned __int8 **)a2 + 247),
                        *((_DWORD *)a2 + 496),
                        v6,
                        *(unsigned __int16 **)v44[0],
                        *v39,
                        *(_DWORD *)v38,
                        (unsigned __int16 **)&hMem);
    v36 = ValueFromStruct;
    v29 = (void *)*((_QWORD *)a2 + 247);
    if ( v29 )
    {
      v30 = GetLastError();
      LocalFree(v29);
      SetLastError(v30);
      ValueFromStruct = v36;
    }
    *((_QWORD *)a2 + 247) = 0;
    *((_DWORD *)a2 + 496) = 0;
    v14 = ValueFromStruct;
    if ( ValueFromStruct < 0 )
    {
      LODWORD(v40[0]) = 15007;
      HIDWORD(v40[0]) = ValueFromStruct;
      Ptr = (Microsoft::Windows::MDM::OmadmClient::CredentialManager *)hMem.Ptr;
      if ( hMem.Ptr )
      {
        LocalFree((HLOCAL)hMem.Ptr);
        ValueFromStruct = v36;
      }
      v15 = (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) == 0;
LABEL_8:
      if ( !v15 )
      {
        v16 = (unsigned int)ValueFromStruct;
LABEL_76:
        McTemplateU0qq_EventWriteTransfer(Ptr, OmaDmClientFunctionReturnValueEvent, 24, v16);
        goto LABEL_77;
      }
      goto LABEL_77;
    }
    if ( InvStrCmpW((const unsigned __int16 *)hMem.Ptr, *((const unsigned __int16 **)a2 + 237)) )
    {
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 1) != 0 )
        McTemplateU0zz_EventWriteTransfer(v31, VerifyServerCredsFailMatchHmacCreds, *((_QWORD *)a2 + 237), hMem.Ptr);
      goto LABEL_65;
    }
LABEL_62:
    *a3 = 1;
LABEL_65:
    Ptr = (Microsoft::Windows::MDM::OmadmClient::CredentialManager *)hMem.Ptr;
    if ( hMem.Ptr )
      LocalFree((HLOCAL)hMem.Ptr);
    goto LABEL_67;
  }
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)VerifyServerCredsFailMatchHmacServerUsername,
      v26,
      1u,
      &v47);
  v40[0] = 0x82AC000500003AB3uLL;
  v14 = -2102657019;
  Ptr = (Microsoft::Windows::MDM::OmadmClient::CredentialManager *)hMem.Ptr;
  if ( hMem.Ptr )
    LocalFree((HLOCAL)hMem.Ptr);
LABEL_19:
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    v16 = v36;
    goto LABEL_76;
  }
LABEL_77:
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v40);
  return v14;
}

```

## disassembly

```asm
0x140028940  push    rbx
0x140028942  push    rsi
0x140028943  push    rdi
0x140028944  push    r12
0x140028946  push    r13
0x140028948  push    r14
0x14002894a  push    r15
0x14002894c  sub     rsp, 0F0h
0x140028953  mov     rax, cs:__security_cookie
0x14002895a  xor     rax, rsp
0x14002895d  mov     [rsp+128h+var_40], rax
0x140028965  mov     r12, r8
0x140028968  mov     rdi, rdx
0x14002896b  mov     r13, rcx
0x14002896e  xor     r14d, r14d
0x140028971  mov     [rsp+128h+var_D8], r14d
0x140028976  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14002897b  mov     [rsp+128h+var_B8], r14
0x140028980  lea     rcx, aVerifyservercr; "VerifyServerCreds"
0x140028987  mov     [rsp+128h+var_B0], rcx
0x14002898c  mov     [rsp+128h+var_A8], rax
0x140028994  lea     ecx, [r14+2]
0x140028998  mov     [rsp+128h+var_A0], ecx
0x14002899f  lea     rax, [rsp+128h+var_D8]
0x1400289a4  mov     [rsp+128h+var_98], rax
0x1400289ac  mov     sil, 8
0x1400289af  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, sil
0x1400289b6  jz      short loc_1400289FC
0x1400289b8  mov     [rsp+128h+var_D0], 18h
0x1400289c0  lea     rax, [rsp+128h+var_D0]
0x1400289c5  mov     [rsp+128h+var_50], rax
0x1400289cd  mov     [rsp+128h+var_48], 4
0x1400289d9  lea     rax, [rsp+128h+var_60]
0x1400289e1  mov     [rsp+128h+var_108], rax
0x1400289e6  mov     r9d, ecx
0x1400289e9  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x1400289f0  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x1400289f7  call    McGenEventWrite_EventWriteTransfer
0x1400289fc  lea     rax, [rsp+128h+var_D8]
0x140028a01  mov     [rsp+128h+var_80], rax
0x140028a09  mov     [rsp+128h+var_78], 1
0x140028a11  test    byte ptr [rdi+774h], 4
0x140028a18  jnz     short loc_140028A1F
0x140028a1a  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "syncmlSessionState.m_grfServerCredProps & gc_ServerCredPropProvided")
0x140028a1f  mov     [r12], r14d
0x140028a23  mov     [rsp+128h+var_C8], r14
0x140028a28  mov     [rsp+128h+var_C0], r14
0x140028a2d  lea     r15, [rdi+30h]
0x140028a31  lea     rax, [rsp+128h+var_C8]
0x140028a36  mov     [rsp+128h+var_108], rax
0x140028a3b  lea     r9, [rsp+128h+var_C0]
0x140028a40  mov     r8d, [rdi+274h]
0x140028a47  mov     rdx, r15
0x140028a4a  mov     ecx, 13h
0x140028a4f  call    cs:__imp_OmaDmGetValueFromStruct
0x140028a56  nop     dword ptr [rax+rax+00h]
0x140028a5b  mov     ebx, eax
0x140028a5d  mov     [rsp+128h+var_D8], eax
0x140028a61  test    eax, eax
0x140028a63  jns     short loc_140028A86
0x140028a65  mov     dword ptr [rsp+128h+var_B8], 178Ah
0x140028a6d  mov     dword ptr [rsp+128h+var_B8+4], eax
0x140028a71  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, sil
0x140028a78  jz      loc_140029069
0x140028a7e  mov     r9d, eax
0x140028a81  jmp     loc_140029056
0x140028a86  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 1
0x140028a8d  jz      short loc_140028AD5
0x140028a8f  lea     rax, [rsp+128h+hMem]
0x140028a97  mov     [rsp+128h+var_108], rax
0x140028a9c  mov     r9d, 1
0x140028aa2  lea     rdx, VerifyServerCredsPrimaryNonce
0x140028aa9  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x140028ab0  call    McGenEventWrite_EventWriteTransfer
0x140028ab5  mov     rcx, [r13+8]
0x140028ab9  mov     rax, [rcx]
0x140028abc  mov     r8, [rsp+128h+var_C8]
0x140028ac1  mov     r8d, [r8]
0x140028ac4  mov     rdx, [rsp+128h+var_C0]
0x140028ac9  mov     rdx, [rdx]
0x140028acc  mov     rax, [rax+18h]
0x140028ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028ad5  mov     [rsp+128h+var_88], r14
0x140028add  mov     [rsp+128h+var_108], r14
0x140028ae2  lea     r9, [rsp+128h+var_88]
0x140028aea  mov     r8d, [rdi+274h]
0x140028af1  mov     rdx, r15
0x140028af4  mov     ecx, 12h
0x140028af9  call    cs:__imp_OmaDmGetValueFromStruct
0x140028b00  nop     dword ptr [rax+rax+00h]
0x140028b05  mov     ebx, eax
0x140028b07  mov     [rsp+128h+var_D8], eax
0x140028b0b  test    eax, eax
0x140028b0d  jns     short loc_140028B1C
0x140028b0f  mov     dword ptr [rsp+128h+var_B8], 178Bh
0x140028b17  jmp     loc_140028A6D
0x140028b1c  mov     [rsp+128h+var_90], r14
0x140028b24  mov     [rsp+128h+var_108], r14; int
0x140028b29  lea     r9, [rsp+128h+var_90]
0x140028b31  or      r8d, 0FFFFFFFFh
0x140028b35  mov     rdx, r15
0x140028b38  lea     ecx, [r8+3]
0x140028b3c  call    cs:__imp_OmaDmGetValueFromStruct
0x140028b43  nop     dword ptr [rax+rax+00h]
0x140028b48  mov     ebx, eax
0x140028b4a  mov     [rsp+128h+var_D8], eax
0x140028b4e  test    eax, eax
0x140028b50  jns     short loc_140028B5F
0x140028b52  mov     dword ptr [rsp+128h+var_B8], 178Ch
0x140028b5a  jmp     loc_140028A6D
0x140028b5f  lea     rsi, [rdi+248h]
0x140028b66  cmp     [rsi], r14
0x140028b69  jnz     short loc_140028BC9
0x140028b6b  mov     [rsi], r14
0x140028b6e  mov     r8, rsi
0x140028b71  or      edx, 0FFFFFFFFh
0x140028b74  mov     rcx, [rsp+128h+var_90]
0x140028b7c  mov     rcx, [rcx]
0x140028b7f  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x140028b86  nop     dword ptr [rax+rax+00h]
0x140028b8b  mov     ebx, eax
0x140028b8d  mov     [rsp+128h+var_D8], eax
0x140028b91  test    eax, eax
0x140028b93  jns     short loc_140028BC9
0x140028b95  mov     rcx, [rsp+128h]; this
0x140028b9d  mov     r9d, eax; char *
0x140028ba0  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140028ba7  mov     edx, 3D8h; void *
0x140028bac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140028bb1  nop
0x140028bb2  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x140028bb9  jz      loc_140029069
0x140028bbf  mov     r9d, [rsp+128h+var_D8]
0x140028bc4  jmp     loc_140029056
0x140028bc9  mov     rdx, [rsp+128h+var_90]
0x140028bd1  mov     rdx, [rdx]
0x140028bd4  mov     rcx, [rsi]
0x140028bd7  call    cs:__imp_?InvStrCmpW@@YAHPEBG0@Z; InvStrCmpW(ushort const *,ushort const *)
0x140028bde  nop     dword ptr [rax+rax+00h]
0x140028be3  test    eax, eax
0x140028be5  jnz     short loc_140028BEA
0x140028be7  mov     r14, [rsi]
0x140028bea  mov     eax, [rdi+774h]
0x140028bf0  and     eax, 3
0x140028bf3  cmp     al, 3
0x140028bf5  jnz     loc_140028FFE
0x140028bfb  cmp     qword ptr [rdi+238h], 0
0x140028c03  jnz     short loc_140028C12
0x140028c05  cmp     dword ptr [rdi+278h], 2
0x140028c0c  jnz     loc_140028FFE
0x140028c12  test    r14, r14
0x140028c15  jz      loc_140028FFE
0x140028c1b  or      esi, 0FFFFFFFFh
0x140028c1e  mov     r8d, esi
0x140028c21  mov     rdx, r15
0x140028c24  lea     ebx, [rsi+26h]
0x140028c27  mov     ecx, ebx
0x140028c29  call    cs:__imp_OmaDmIsNodeValuePresent
0x140028c30  nop     dword ptr [rax+rax+00h]
0x140028c35  test    eax, eax
0x140028c37  jz      loc_140028D1F
0x140028c3d  lea     rax, [rsp+128h+var_C8]
0x140028c42  mov     [rsp+128h+var_108], rax
0x140028c47  lea     r9, [rsp+128h+var_C0]
0x140028c4c  mov     r8d, esi
0x140028c4f  mov     rdx, r15
0x140028c52  mov     ecx, ebx
0x140028c54  call    cs:__imp_OmaDmGetValueFromStruct
0x140028c5b  nop     dword ptr [rax+rax+00h]
0x140028c60  mov     ebx, eax
0x140028c62  mov     [rsp+128h+var_D8], eax
0x140028c66  mov     eax, cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits
0x140028c6c  lea     r15d, [rsi+2]
0x140028c70  test    r15b, al
0x140028c73  jz      short loc_140028CC2
0x140028c75  lea     rax, [rsp+128h+var_60]
0x140028c7d  mov     [rsp+128h+var_108], rax
0x140028c82  mov     r9d, r15d
0x140028c85  lea     rdx, VerifyServerCredsSecondaryNonce
0x140028c8c  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x140028c93  call    McGenEventWrite_EventWriteTransfer
0x140028c98  mov     rcx, [r13+8]
0x140028c9c  mov     rax, [rcx]
0x140028c9f  mov     r8, [rsp+128h+var_C8]
0x140028ca4  mov     r8d, [r8]
0x140028ca7  mov     rdx, [rsp+128h+var_C0]
0x140028cac  mov     rdx, [rdx]
0x140028caf  mov     rax, [rax+18h]
0x140028cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028cb8  mov     ebx, [rsp+128h+var_D8]
0x140028cbc  mov     eax, cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits
0x140028cc2  test    ebx, ebx
0x140028cc4  jns     short loc_140028CD9
0x140028cc6  mov     dword ptr [rsp+128h+var_B8], 178Dh
0x140028cce  mov     dword ptr [rsp+128h+var_B8+4], ebx
0x140028cd2  test    al, 8
0x140028cd4  jmp     loc_140029051
0x140028cd9  mov     r9, [rsp+128h+var_C0]
0x140028cde  cmp     qword ptr [r9], 0
0x140028ce2  jz      short loc_140028CEE
0x140028ce4  mov     rcx, [rsp+128h+var_C8]
0x140028ce9  cmp     dword ptr [rcx], 0
0x140028cec  jnz     short loc_140028D2F
0x140028cee  mov     dword ptr [rsp+128h+var_B8], 3AB2h
0x140028cf6  mov     edi, 8000FFFFh
0x140028cfb  mov     dword ptr [rsp+128h+var_B8+4], edi
0x140028cff  test    al, 8
0x140028d01  jz      short loc_140028D18
0x140028d03  mov     r9d, ebx
0x140028d06  mov     r8d, 18h
0x140028d0c  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x140028d13  call    McTemplateU0qq_EventWriteTransfer
0x140028d18  mov     ebx, edi
0x140028d1a  jmp     loc_140029069
0x140028d1f  mov     rcx, [rsp+128h+var_C8]; this
0x140028d24  mov     r9, [rsp+128h+var_C0]
0x140028d29  mov     r15d, 1
0x140028d2f  mov     qword ptr [rsp+128h+hMem], 0
0x140028d3b  cmp     dword ptr [rdi+278h], 2
0x140028d42  jz      loc_140028DEE
0x140028d48  mov     qword ptr [rsp+128h+hMem], 0
0x140028d54  lea     rax, [rsp+128h+hMem]
0x140028d5c  mov     [rsp+128h+var_100], rax; unsigned __int16 **
0x140028d61  mov     eax, [rcx]
0x140028d63  mov     dword ptr [rsp+128h+var_108], eax; unsigned int
0x140028d67  mov     r9, [r9]; unsigned __int8 *
0x140028d6a  mov     r8, [rsp+128h+var_88]
0x140028d72  mov     r8, [r8]; unsigned __int16 *
0x140028d75  mov     rdx, r14; unsigned __int16 *
0x140028d78  call    ?CalcMd5CredHash@CredentialManager@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEBG0QEBEKPEAPEAG@Z; Microsoft::Windows::MDM::OmadmClient::CredentialManager::CalcMd5CredHash(ushort const *,ushort const *,uchar const * const,ulong,ushort * *)
0x140028d7d  mov     ebx, eax
0x140028d7f  mov     r9d, eax
0x140028d82  mov     [rsp+128h+var_D8], eax
0x140028d86  test    eax, eax
0x140028d88  jns     short loc_140028DC6
0x140028d8a  mov     dword ptr [rsp+128h+var_B8], 3AA1h
0x140028d92  mov     dword ptr [rsp+128h+var_B8+4], eax
0x140028d96  mov     rcx, qword ptr [rsp+128h+hMem]; hMem
0x140028d9e  test    rcx, rcx
0x140028da1  jz      short loc_140028DB4
0x140028da3  call    cs:__imp_LocalFree
0x140028daa  nop     dword ptr [rax+rax+00h]
0x140028daf  mov     r9d, [rsp+128h+var_D8]
0x140028db4  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x140028dbb  jz      loc_140029069
0x140028dc1  jmp     loc_140029056
0x140028dc6  mov     rdx, [rdi+238h]
0x140028dcd  mov     rcx, qword ptr [rsp+128h+hMem]
0x140028dd5  call    cs:__imp_?InvStrCmpW@@YAHPEBG0@Z; InvStrCmpW(ushort const *,ushort const *)
0x140028ddc  nop     dword ptr [rax+rax+00h]
0x140028de1  test    eax, eax
0x140028de3  jnz     loc_140028FE5
0x140028de9  jmp     loc_140028FBA
0x140028dee  cmp     qword ptr [rdi+7B8h], 0
0x140028df6  jnz     short loc_140028DFD
0x140028df8  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "nullptr != syncmlSessionState.m_pbMessageFromServer")
0x140028dfd  mov     rdx, [rdi+760h]
0x140028e04  mov     rcx, r14
0x140028e07  call    cs:__imp_?InvStrCmpW@@YAHPEBG0@Z; InvStrCmpW(ushort const *,ushort const *)
0x140028e0e  nop     dword ptr [rax+rax+00h]
0x140028e13  test    eax, eax
0x140028e15  jz      short loc_140028E76
0x140028e17  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, r15b
0x140028e1e  jz      short loc_140028E43
0x140028e20  lea     rax, [rsp+128h+var_60]
0x140028e28  mov     [rsp+128h+var_108], rax
0x140028e2d  mov     r9d, r15d
0x140028e30  lea     rdx, VerifyServerCredsFailMatchHmacServerUsername
0x140028e37  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x140028e3e  call    McGenEventWrite_EventWriteTransfer
0x140028e43  mov     dword ptr [rsp+128h+var_B8], 3AB3h
0x140028e4b  mov     ebx, 82AC0005h
0x140028e50  mov     dword ptr [rsp+128h+var_B8+4], ebx
0x140028e54  mov     rcx, qword ptr [rsp+128h+hMem]; hMem
0x140028e5c  test    rcx, rcx
0x140028e5f  jz      loc_140028BB2
0x140028e65  call    cs:__imp_LocalFree
0x140028e6c  nop     dword ptr [rax+rax+00h]
0x140028e71  jmp     loc_140028BB2
0x140028e76  mov     rsi, qword ptr [rsp+128h+hMem]
0x140028e7e  test    rsi, rsi
0x140028e81  jz      short loc_140028EAE
0x140028e83  call    cs:__imp_GetLastError
0x140028e8a  nop     dword ptr [rax+rax+00h]
0x140028e8f  mov     ebx, eax
0x140028e91  mov     rcx, rsi; hMem
0x140028e94  call    cs:__imp_LocalFree
0x140028e9b  nop     dword ptr [rax+rax+00h]
0x140028ea0  mov     ecx, ebx; dwErrCode
0x140028ea2  call    cs:__imp_SetLastError
0x140028ea9  nop     dword ptr [rax+rax+00h]
0x140028eae  mov     qword ptr [rsp+128h+hMem], 0
0x140028eba  lea     rax, [rsp+128h+hMem]
0x140028ec2  mov     [rsp+128h+var_E8], rax; unsigned __int16 **
0x140028ec7  mov     rax, [rsp+128h+var_C8]
0x140028ecc  mov     edx, [rax]
0x140028ece  mov     [rsp+128h+var_F0], edx; unsigned int
0x140028ed2  mov     rax, [rsp+128h+var_C0]
0x140028ed7  mov     rdx, [rax]
0x140028eda  mov     [rsp+128h+var_F8], rdx; unsigned __int8 *
  ... truncated ...
```
