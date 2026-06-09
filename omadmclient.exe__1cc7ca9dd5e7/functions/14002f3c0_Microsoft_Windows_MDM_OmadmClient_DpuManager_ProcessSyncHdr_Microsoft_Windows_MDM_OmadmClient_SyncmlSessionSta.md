# Microsoft::Windows::MDM::OmadmClient::DpuManager::ProcessSyncHdr(Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState &,ushort *)

- ea: `0x14002f3c0`
- end: `0x14002fc9a`
- name: `?ProcessSyncHdr@DpuManager@OmadmClient@MDM@Windows@Microsoft@@UEAAJAEAVSyncmlSessionState@2345@PEAG@Z`
- size: `2266`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::DpuManager *__hidden this, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *, BYTE *pInit)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140003450`
- `0x14000b0f4`
- `0x14000d71c`
- `0x14000d778`
- `0x14000e610`
- `0x140013404`
- `0x14002ae20`
- `0x14002b144`
- `0x14002f3c0`
- `0x14002fcec`
- `0x14002ff9c`
- `0x1400552f8`
- `0x140069010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x14002f57e`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x14002f57e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002fb36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002fb36`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002fb55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002fb55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002fb47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002fb47`
- `XmlLite!CreateXmlReader` at `0x14002f4cd`
- `XmlLite!CreateXmlReader` at `0x14002f4cd`
- `DMCmnUtils!CopyString` at `0x14002fb71`
- `DMCmnUtils!CopyString` at `0x14002fb71`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x14002f5bf`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x14002f5bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::DpuManager::ProcessSyncHdr(
        Microsoft::Windows::MDM::OmadmClient::DpuManager *this,
        const unsigned __int16 **a2,
        BYTE *pInit)
{
  __int64 v6; // r8
  char v7; // al
  unsigned int *v8; // rcx
  int v9; // ebx
  __int64 v10; // r9
  HRESULT v11; // eax
  int v12; // eax
  unsigned __int64 v13; // rcx
  IStream *v14; // rax
  IStream *v15; // rdi
  int v16; // eax
  int started; // eax
  __int64 v18; // r8
  int v19; // eax
  int v20; // eax
  int v21; // eax
  void (__fastcall *v22)(IStream *); // rax
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  void **v28; // r14
  __int64 v29; // rax
  int v30; // eax
  void *v31; // r15
  DWORD LastError; // ebx
  int v33; // eax
  int *v35; // [rsp+20h] [rbp-E8h]
  unsigned int v36; // [rsp+30h] [rbp-D8h] BYREF
  void *ppvObject; // [rsp+38h] [rbp-D0h] BYREF
  unsigned int v38; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v39; // [rsp+48h] [rbp-C0h] BYREF
  int v40; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v41[3]; // [rsp+58h] [rbp-B0h] BYREF
  int v42; // [rsp+70h] [rbp-98h]
  unsigned int *v43; // [rsp+78h] [rbp-90h]
  unsigned __int16 *v44; // [rsp+80h] [rbp-88h] BYREF
  unsigned __int16 *v45; // [rsp+88h] [rbp-80h] BYREF
  _QWORD v46[2]; // [rsp+90h] [rbp-78h] BYREF
  char v47; // [rsp+A0h] [rbp-68h]
  int v48[4]; // [rsp+A8h] [rbp-60h] BYREF
  unsigned int *v49; // [rsp+B8h] [rbp-50h]
  __int64 v50; // [rsp+C0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v36 = 0;
  v41[0] = 0;
  v41[1] = "ProcessSyncHdr";
  v41[2] = COmaDmLogger::GetLogger();
  v42 = 2;
  v43 = &v36;
  v7 = Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    v39 = 26;
    v49 = &v39;
    v50 = 4;
    v35 = v48;
    McGenEventWrite_EventWriteTransfer(WP_OMADM_CLIENT_PROVIDER_Context, OmaDmClientFunctionEntryPointEvent, v6, 2);
    v7 = Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits;
  }
  v8 = &v36;
  v46[1] = &v36;
  v47 = 1;
  if ( !pInit )
  {
    v9 = -805306128;
    v36 = -805306128;
    if ( (v7 & 8) != 0 )
    {
      v10 = 3489661168LL;
      goto LABEL_99;
    }
    goto LABEL_100;
  }
  ppvObject = 0;
  v11 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v9 = v11;
  v36 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\dpumanager.cpp",
      (const char *)(unsigned int)v11,
      (int)v35);
    v8 = (unsigned int *)ppvObject;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    goto LABEL_97;
  }
  v12 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
  v9 = v12;
  v36 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBA,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\dpumanager.cpp",
      (const char *)(unsigned int)v12,
      (int)v35);
    v8 = (unsigned int *)ppvObject;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    goto LABEL_97;
  }
  while ( (unsigned int)_o_iswspace(*(unsigned __int16 *)pInit) )
    pInit += 2;
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)&pInit[2 * v13] );
  v45 = 0;
  if ( !is_mul_ok(v13, 2u) )
  {
    v9 = -2147024362;
    v36 = -2147024362;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\dpumanager.cpp",
      (const char *)0x80070216LL,
      (int)v35);
    v8 = (unsigned int *)ppvObject;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
LABEL_97:
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      goto LABEL_98;
    goto LABEL_100;
  }
  v36 = 0;
  v14 = SHCreateMemStream(pInit, 2 * (int)v13);
  v15 = v14;
  v46[0] = v14;
  if ( !v14 )
  {
    v9 = -2147024882;
    v36 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCA,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\dpumanager.cpp",
      (const char *)0x8007000ELL,
      (int)v35);
    v8 = (unsigned int *)ppvObject;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    goto LABEL_97;
  }
  v36 = 0;
  v16 = (*(__int64 (__fastcall **)(void *, IStream *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, v14);
  v9 = v16;
  v36 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\dpumanager.cpp",
      (const char *)(unsigned int)v16,
      (int)v35);
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v15 + 16LL))(v15);
    v8 = (unsigned int *)ppvObject;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    goto LABEL_97;
  }
  v40 = 0;
  while ( 1 )
  {
    started = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v40);
    v36 = started;
    if ( started )
      break;
    v39 = 0;
    v38 = 0;
    v45 = 0;
    v44 = 0;
    switch ( v40 )
    {
      case 1:
        v21 = (*(__int64 (__fastcall **)(void *, unsigned __int16 **, unsigned int *))(*(_QWORD *)ppvObject + 112LL))(
                ppvObject,
                &v44,
                &v38);
        v9 = v21;
        v36 = v21;
        if ( v21 < 0 )
        {
          LODWORD(v41[0]) = 21032;
          HIDWORD(v41[0]) = v21;
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)v15 + 16LL))(v15);
          v8 = (unsigned int *)ppvObject;
          if ( ppvObject )
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
          goto LABEL_97;
        }
        started = Microsoft::Windows::MDM::OmadmClient::DpuManager::StartElement(
                    this,
                    (struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *)a2,
                    v44,
                    v38);
        v9 = started;
        v36 = started;
        if ( started < 0 )
        {
          LODWORD(v41[0]) = 21092;
          HIDWORD(v41[0]) = started;
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)v15 + 16LL))(v15);
          v8 = (unsigned int *)ppvObject;
          if ( ppvObject )
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
          goto LABEL_97;
        }
        goto LABEL_44;
      case 3:
        v20 = (*(__int64 (__fastcall **)(void *, unsigned __int16 **, unsigned int *))(*(_QWORD *)ppvObject + 128LL))(
                ppvObject,
                &v45,
                &v39);
        v9 = v20;
        v36 = v20;
        if ( v20 < 0 )
        {
          LODWORD(v41[0]) = 21033;
          HIDWORD(v41[0]) = v20;
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)v15 + 16LL))(v15);
          v8 = (unsigned int *)ppvObject;
          if ( ppvObject )
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
          goto LABEL_97;
        }
        started = Microsoft::Windows::MDM::OmadmClient::DpuManager::Characters(
                    this,
                    (struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *)a2,
                    v45,
                    v39);
        v9 = started;
        v36 = started;
        if ( started < 0 )
        {
          LODWORD(v41[0]) = 21096;
          HIDWORD(v41[0]) = started;
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)v15 + 16LL))(v15);
          v8 = (unsigned int *)ppvObject;
          if ( ppvObject )
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
          goto LABEL_97;
        }
        goto LABEL_44;
      case 15:
        v19 = (*(__int64 (__fastcall **)(void *, unsigned __int16 **, unsigned int *))(*(_QWORD *)ppvObject + 112LL))(
                ppvObject,
                &v44,
                &v38);
        v9 = v19;
        v36 = v19;
        if ( v19 < 0 )
        {
          LODWORD(v41[0]) = 21031;
          HIDWORD(v41[0]) = v19;
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)v15 + 16LL))(v15);
          v8 = (unsigned int *)ppvObject;
          if ( ppvObject )
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
          goto LABEL_97;
        }
        started = Microsoft::Windows::MDM::OmadmClient::DpuManager::EndElement(
                    this,
                    (struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *)a2,
                    v44,
                    v38);
        v9 = started;
        v36 = started;
        if ( started < 0 )
        {
          LODWORD(v41[0]) = 21018;
          HIDWORD(v41[0]) = started;
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)v15 + 16LL))(v15);
          v8 = (unsigned int *)ppvObject;
          if ( ppvObject )
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
          goto LABEL_97;
        }
LABEL_44:
        if ( v9 == 1 && *((_DWORD *)a2 + 508) )
          goto LABEL_60;
        break;
    }
  }
  v9 = started;
LABEL_60:
  if ( !*((_DWORD *)a2 + 508) )
  {
    if ( v9 >= 0 )
    {
      started = -2102788095;
      v36 = -2102788095;
    }
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 2) != 0 )
    {
      LODWORD(v46[0]) = started;
      v49 = (unsigned int *)v46;
      v50 = 4;
      McGenEventWrite_EventWriteTransfer(WP_OMADM_CLIENT_PROVIDER_Context, FailedSyncHdrParsingEvent, v18, 2);
      started = v36;
    }
    v9 = started;
    v22 = *(void (__fastcall **)(IStream *))(*(_QWORD *)v15 + 16LL);
    if ( v9 >= 0 )
    {
      v22(v15);
      v8 = (unsigned int *)ppvObject;
      if ( ppvObject )
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    }
    else
    {
      LODWORD(v41[0]) = 30001;
      HIDWORD(v41[0]) = v9;
      v22(v15);
      v8 = (unsigned int *)ppvObject;
      if ( ppvObject )
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    }
    goto LABEL_97;
  }
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 1) != 0 )
  {
    v35 = v48;
    McGenEventWrite_EventWriteTransfer(WP_OMADM_CLIENT_PROVIDER_Context, SuccesfulSyncHdrParsingEvent, v18, 1);
  }
  v36 = 0;
  v23 = Microsoft::Windows::MDM::OmadmClient::DpuManager::VerifySyncHdrData(
          this,
          (struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *)a2);
  v9 = v23;
  v36 = v23;
  if ( v23 < 0 )
  {
    LODWORD(v41[0]) = 21098;
    HIDWORD(v41[0]) = v23;
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v15 + 16LL))(v15);
    v8 = (unsigned int *)ppvObject;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    goto LABEL_97;
  }
  if ( !a2[242] )
    goto LABEL_92;
  v28 = (void **)(a2 + 177);
  if ( !a2[177] )
    MicrosoftTelemetryAssertTriggeredNoArgs(v25, v24, v26, v27, v35);
  v29 = (*(__int64 (__fastcall **)(struct Microsoft::Windows::MDM::OmadmClient::IAbstractFactory *))(*(_QWORD *)Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory + 112LL))(Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory);
  v30 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 **, const unsigned __int16 *))(*(_QWORD *)v29 + 8LL))(
          v29,
          a2,
          a2[242]);
  v9 = v30;
  v36 = v30;
  if ( v30 < 0 )
  {
    LODWORD(v41[0]) = 21064;
    HIDWORD(v41[0]) = v30;
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v15 + 16LL))(v15);
    v8 = (unsigned int *)ppvObject;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    goto LABEL_97;
  }
  v31 = *v28;
  if ( *v28 )
  {
    LastError = GetLastError();
    LocalFree(v31);
    SetLastError(LastError);
  }
  *v28 = 0;
  v33 = CopyString(a2[222], 0xFFFFFFFF, (unsigned __int16 **)a2 + 177);
  v9 = v33;
  v36 = v33;
  if ( v33 >= 0 )
  {
LABEL_92:
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v15 + 16LL))(v15);
    v8 = (unsigned int *)ppvObject;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    goto LABEL_97;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x127,
    (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\dpumanager.cpp",
    (const char *)(unsigned int)v33,
    (int)v35);
  (*(void (__fastcall **)(IStream *))(*(_QWORD *)v15 + 16LL))(v15);
  v8 = (unsigned int *)ppvObject;
  if ( ppvObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) == 0 )
    goto LABEL_100;
LABEL_98:
  v10 = v36;
LABEL_99:
  McTemplateU0qq_EventWriteTransfer(v8, OmaDmClientFunctionReturnValueEvent, 26, v10);
LABEL_100:
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v41);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14002f3c0  push    rbx
0x14002f3c2  push    rsi
0x14002f3c3  push    rdi
0x14002f3c4  push    r12
0x14002f3c6  push    r13
0x14002f3c8  push    r14
0x14002f3ca  push    r15
0x14002f3cc  sub     rsp, 0D0h
0x14002f3d3  mov     rax, cs:__security_cookie
0x14002f3da  xor     rax, rsp
0x14002f3dd  mov     [rsp+108h+var_40], rax
0x14002f3e5  mov     rdi, r8
0x14002f3e8  mov     rsi, rdx
0x14002f3eb  mov     r14, rcx
0x14002f3ee  xor     r12d, r12d
0x14002f3f1  mov     [rsp+108h+var_D8], r12d
0x14002f3f6  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14002f3fb  mov     [rsp+108h+var_B0], r12
0x14002f400  lea     rcx, aProcesssynchdr; "ProcessSyncHdr"
0x14002f407  mov     [rsp+108h+var_A8], rcx
0x14002f40c  mov     [rsp+108h+var_A0], rax
0x14002f411  mov     [rsp+108h+var_98], 2
0x14002f419  lea     rax, [rsp+108h+var_D8]
0x14002f41e  mov     [rsp+108h+var_90], rax
0x14002f423  mov     eax, cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits
0x14002f429  lea     r15d, [r12+1Ah]
0x14002f42e  mov     r13b, 8
0x14002f431  test    r13b, al
0x14002f434  jz      short loc_14002F47F
0x14002f436  mov     [rsp+108h+var_C0], r15d
0x14002f43b  lea     rax, [rsp+108h+var_C0]
0x14002f440  mov     [rsp+108h+var_50], rax
0x14002f448  mov     [rsp+108h+var_48], 4
0x14002f454  lea     rax, [rsp+108h+var_60]
0x14002f45c  mov     qword ptr [rsp+108h+var_E8], rax; int
0x14002f461  lea     r9d, [r12+2]
0x14002f466  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x14002f46d  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x14002f474  call    McGenEventWrite_EventWriteTransfer
0x14002f479  mov     eax, cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits
0x14002f47f  lea     rcx, [rsp+108h+var_D8]
0x14002f484  mov     [rsp+108h+var_70], rcx
0x14002f48c  mov     [rsp+108h+var_68], 1
0x14002f494  test    rdi, rdi
0x14002f497  jnz     short loc_14002F4B9
0x14002f499  mov     ebx, 0D00000F0h
0x14002f49e  mov     [rsp+108h+var_D8], ebx
0x14002f4a2  test    r13b, al
0x14002f4a5  jz      loc_14002FC6A
0x14002f4ab  mov     r9d, 0D00000F0h
0x14002f4b1  mov     r8d, r15d
0x14002f4b4  jmp     loc_14002FC5D
0x14002f4b9  mov     [rsp+108h+ppvObject], r12
0x14002f4be  xor     r8d, r8d; pMalloc
0x14002f4c1  lea     rdx, [rsp+108h+ppvObject]; ppvObject
0x14002f4c6  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x14002f4cd  call    cs:__imp_CreateXmlReader
0x14002f4d4  nop     dword ptr [rax+rax+00h]
0x14002f4d9  mov     ebx, eax
0x14002f4db  mov     [rsp+108h+var_D8], eax
0x14002f4df  test    eax, eax
0x14002f4e1  jns     short loc_14002F51C
0x14002f4e3  mov     rcx, [rsp+108h]; this
0x14002f4eb  mov     r9d, eax; char *
0x14002f4ee  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14002f4f5  mov     edx, 0B6h; void *
0x14002f4fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002f4ff  nop
0x14002f500  mov     rcx, [rsp+108h+ppvObject]
0x14002f505  test    rcx, rcx
0x14002f508  jz      short loc_14002F517
0x14002f50a  mov     rax, [rcx]
0x14002f50d  mov     rax, [rax+10h]
0x14002f511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f516  nop
0x14002f517  jmp     loc_14002FC4C
0x14002f51c  mov     rcx, [rsp+108h+ppvObject]
0x14002f521  mov     rax, [rcx]
0x14002f524  xor     r8d, r8d
0x14002f527  lea     edx, [r8+4]
0x14002f52b  mov     rax, [rax+28h]
0x14002f52f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f534  mov     ebx, eax
0x14002f536  mov     [rsp+108h+var_D8], eax
0x14002f53a  test    eax, eax
0x14002f53c  jns     short loc_14002F57B
0x14002f53e  mov     rcx, [rsp+108h]; this
0x14002f546  mov     r9d, eax; char *
0x14002f549  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14002f550  mov     edx, 0BAh; void *
0x14002f555  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002f55a  nop
0x14002f55b  mov     rcx, [rsp+108h+ppvObject]
0x14002f560  test    rcx, rcx
0x14002f563  jz      short loc_14002F572
0x14002f565  mov     rax, [rcx]
0x14002f568  mov     rax, [rax+10h]
0x14002f56c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f571  nop
0x14002f572  jmp     loc_14002FC4C
0x14002f577  add     rdi, 2
0x14002f57b  movzx   ecx, word ptr [rdi]
0x14002f57e  call    cs:__imp__o_iswspace
0x14002f585  nop     dword ptr [rax+rax+00h]
0x14002f58a  test    eax, eax
0x14002f58c  jnz     short loc_14002F577
0x14002f58e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14002f592  inc     rcx
0x14002f595  cmp     [rdi+rcx*2], r12w
0x14002f59a  jnz     short loc_14002F592
0x14002f59c  mov     [rsp+108h+var_80], r12
0x14002f5a4  mov     eax, 2
0x14002f5a9  mul     rcx
0x14002f5ac  test    rdx, rdx
0x14002f5af  jnz     loc_14002FC0F
0x14002f5b5  mov     [rsp+108h+var_D8], r12d
0x14002f5ba  mov     edx, eax; cbInit
0x14002f5bc  mov     rcx, rdi; pInit
0x14002f5bf  call    cs:__imp_SHCreateMemStream
0x14002f5c6  nop     dword ptr [rax+rax+00h]
0x14002f5cb  mov     rdi, rax
0x14002f5ce  mov     [rsp+108h+var_78], rax
0x14002f5d6  test    rax, rax
0x14002f5d9  jnz     short loc_14002F61D
0x14002f5db  mov     ebx, 8007000Eh
0x14002f5e0  mov     [rsp+108h+var_D8], ebx
0x14002f5e4  mov     rcx, [rsp+108h]; this
0x14002f5ec  mov     r9d, ebx; char *
0x14002f5ef  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14002f5f6  mov     edx, 0CAh; void *
0x14002f5fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002f600  nop
0x14002f601  mov     rcx, [rsp+108h+ppvObject]
0x14002f606  test    rcx, rcx
0x14002f609  jz      short loc_14002F618
0x14002f60b  mov     rax, [rcx]
0x14002f60e  mov     rax, [rax+10h]
0x14002f612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f617  nop
0x14002f618  jmp     loc_14002FC4C
0x14002f61d  mov     [rsp+108h+var_D8], r12d
0x14002f622  mov     rcx, [rsp+108h+ppvObject]
0x14002f627  mov     rax, [rcx]
0x14002f62a  mov     rdx, rdi
0x14002f62d  mov     rax, [rax+18h]
0x14002f631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f636  mov     ebx, eax
0x14002f638  mov     [rsp+108h+var_D8], eax
0x14002f63c  test    eax, eax
0x14002f63e  jns     short loc_14002F689
0x14002f640  mov     rcx, [rsp+108h]; this
0x14002f648  mov     r9d, eax; char *
0x14002f64b  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14002f652  mov     edx, 0CDh; void *
0x14002f657  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002f65c  nop
0x14002f65d  mov     rax, [rdi]
0x14002f660  mov     rcx, rdi
0x14002f663  mov     rax, [rax+10h]
0x14002f667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f66c  nop
0x14002f66d  mov     rcx, [rsp+108h+ppvObject]
0x14002f672  test    rcx, rcx
0x14002f675  jz      short loc_14002F684
0x14002f677  mov     rax, [rcx]
0x14002f67a  mov     rax, [rax+10h]
0x14002f67e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f683  nop
0x14002f684  jmp     loc_14002FC4C
0x14002f689  mov     [rsp+108h+var_B8], r12d
0x14002f68e  mov     rcx, [rsp+108h+ppvObject]
0x14002f693  mov     rax, [rcx]
0x14002f696  lea     rdx, [rsp+108h+var_B8]
0x14002f69b  mov     rax, [rax+30h]
0x14002f69f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f6a4  mov     [rsp+108h+var_D8], eax
0x14002f6a8  test    eax, eax
0x14002f6aa  jnz     loc_14002F949
0x14002f6b0  mov     [rsp+108h+var_C0], r12d
0x14002f6b5  mov     [rsp+108h+var_C8], r12d
0x14002f6ba  mov     [rsp+108h+var_80], r12
0x14002f6c2  mov     [rsp+108h+var_88], r12
0x14002f6ca  mov     ecx, [rsp+108h+var_B8]
0x14002f6ce  sub     ecx, 1
0x14002f6d1  jz      loc_14002F7FC
0x14002f6d7  sub     ecx, 2
0x14002f6da  jz      loc_14002F76F
0x14002f6e0  cmp     ecx, 0Ch
0x14002f6e3  jnz     short loc_14002F68E
0x14002f6e5  mov     rcx, [rsp+108h+ppvObject]
0x14002f6ea  mov     rax, [rcx]
0x14002f6ed  lea     r8, [rsp+108h+var_C8]
0x14002f6f2  lea     rdx, [rsp+108h+var_88]
0x14002f6fa  mov     rax, [rax+70h]
0x14002f6fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f703  mov     ebx, eax
0x14002f705  mov     [rsp+108h+var_D8], eax
0x14002f709  test    eax, eax
0x14002f70b  js      loc_14002F869
0x14002f711  mov     r9d, [rsp+108h+var_C8]; unsigned int
0x14002f716  mov     r8, [rsp+108h+var_88]; unsigned __int16 *
0x14002f71e  mov     rdx, rsi; struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *
0x14002f721  mov     rcx, r14; this
0x14002f724  call    ?EndElement@DpuManager@OmadmClient@MDM@Windows@Microsoft@@AEAAJAEAVSyncmlSessionState@2345@PEBGI@Z; Microsoft::Windows::MDM::OmadmClient::DpuManager::EndElement(Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState &,ushort const *,uint)
0x14002f729  mov     ebx, eax
0x14002f72b  mov     [rsp+108h+var_D8], eax
0x14002f72f  test    eax, eax
0x14002f731  jns     loc_14002F84E
0x14002f737  mov     dword ptr [rsp+108h+var_B0], 521Ah
0x14002f73f  mov     dword ptr [rsp+108h+var_B0+4], eax
0x14002f743  mov     rax, [rdi]
0x14002f746  mov     rcx, rdi
0x14002f749  mov     rax, [rax+10h]
0x14002f74d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f752  nop
0x14002f753  mov     rcx, [rsp+108h+ppvObject]
0x14002f758  test    rcx, rcx
0x14002f75b  jz      short loc_14002F76A
0x14002f75d  mov     rax, [rcx]
0x14002f760  mov     rax, [rax+10h]
0x14002f764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f769  nop
0x14002f76a  jmp     loc_14002FC4C
0x14002f76f  mov     rcx, [rsp+108h+ppvObject]
0x14002f774  mov     rax, [rcx]
0x14002f777  lea     r8, [rsp+108h+var_C0]
0x14002f77c  lea     rdx, [rsp+108h+var_80]
0x14002f784  mov     rax, [rax+80h]
0x14002f78b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f790  mov     ebx, eax
0x14002f792  mov     [rsp+108h+var_D8], eax
0x14002f796  test    eax, eax
0x14002f798  js      loc_14002F8A1
0x14002f79e  mov     r9d, [rsp+108h+var_C0]; unsigned int
0x14002f7a3  mov     r8, [rsp+108h+var_80]; unsigned __int16 *
0x14002f7ab  mov     rdx, rsi; struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *
0x14002f7ae  mov     rcx, r14; this
0x14002f7b1  call    ?Characters@DpuManager@OmadmClient@MDM@Windows@Microsoft@@AEAAJAEAVSyncmlSessionState@2345@PEBGI@Z; Microsoft::Windows::MDM::OmadmClient::DpuManager::Characters(Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState &,ushort const *,uint)
0x14002f7b6  mov     ebx, eax
0x14002f7b8  mov     [rsp+108h+var_D8], eax
0x14002f7bc  test    eax, eax
0x14002f7be  jns     loc_14002F84E
0x14002f7c4  mov     dword ptr [rsp+108h+var_B0], 5268h
0x14002f7cc  mov     dword ptr [rsp+108h+var_B0+4], eax
0x14002f7d0  mov     rax, [rdi]
0x14002f7d3  mov     rcx, rdi
0x14002f7d6  mov     rax, [rax+10h]
0x14002f7da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f7df  nop
0x14002f7e0  mov     rcx, [rsp+108h+ppvObject]
0x14002f7e5  test    rcx, rcx
0x14002f7e8  jz      short loc_14002F7F7
0x14002f7ea  mov     rax, [rcx]
0x14002f7ed  mov     rax, [rax+10h]
0x14002f7f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f7f6  nop
0x14002f7f7  jmp     loc_14002FC4C
0x14002f7fc  mov     rcx, [rsp+108h+ppvObject]
0x14002f801  mov     rax, [rcx]
0x14002f804  lea     r8, [rsp+108h+var_C8]
0x14002f809  lea     rdx, [rsp+108h+var_88]
0x14002f811  mov     rax, [rax+70h]
0x14002f815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f81a  mov     ebx, eax
0x14002f81c  mov     [rsp+108h+var_D8], eax
0x14002f820  test    eax, eax
0x14002f822  js      loc_14002F911
0x14002f828  mov     r9d, [rsp+108h+var_C8]; unsigned int
0x14002f82d  mov     r8, [rsp+108h+var_88]; unsigned __int16 *
0x14002f835  mov     rdx, rsi; struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *
0x14002f838  mov     rcx, r14; this
0x14002f83b  call    ?StartElement@DpuManager@OmadmClient@MDM@Windows@Microsoft@@AEAAJAEAVSyncmlSessionState@2345@PEBGI@Z; Microsoft::Windows::MDM::OmadmClient::DpuManager::StartElement(Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState &,ushort const *,uint)
0x14002f840  mov     ebx, eax
0x14002f842  mov     [rsp+108h+var_D8], eax
0x14002f846  test    eax, eax
0x14002f848  js      loc_14002F8D9
0x14002f84e  cmp     ebx, 1
0x14002f851  jnz     loc_14002F68E
0x14002f857  cmp     [rsi+7F0h], r12d
0x14002f85e  jz      loc_14002F68E
0x14002f864  jmp     loc_14002F94B
0x14002f869  mov     dword ptr [rsp+108h+var_B0], 5227h
0x14002f871  mov     dword ptr [rsp+108h+var_B0+4], eax
0x14002f875  mov     rax, [rdi]
0x14002f878  mov     rcx, rdi
0x14002f87b  mov     rax, [rax+10h]
0x14002f87f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f884  nop
0x14002f885  mov     rcx, [rsp+108h+ppvObject]
0x14002f88a  test    rcx, rcx
0x14002f88d  jz      short loc_14002F89C
0x14002f88f  mov     rax, [rcx]
0x14002f892  mov     rax, [rax+10h]
0x14002f896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f89b  nop
0x14002f89c  jmp     loc_14002FC4C
0x14002f8a1  mov     dword ptr [rsp+108h+var_B0], 5229h
0x14002f8a9  mov     dword ptr [rsp+108h+var_B0+4], eax
0x14002f8ad  mov     rax, [rdi]
0x14002f8b0  mov     rcx, rdi
  ... truncated ...
```
