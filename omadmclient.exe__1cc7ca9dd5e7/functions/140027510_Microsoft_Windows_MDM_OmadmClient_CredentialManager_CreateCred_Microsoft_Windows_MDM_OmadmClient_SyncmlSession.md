# Microsoft::Windows::MDM::OmadmClient::CredentialManager::CreateCred(Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState &,ushort const *,ushort * *,ushort * *)

- ea: `0x140027510`
- end: `0x140027ac6`
- name: `?CreateCred@CredentialManager@OmadmClient@MDM@Windows@Microsoft@@UEAAJAEAVSyncmlSessionState@2345@PEBGPEAPEAG2@Z`
- size: `1462`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::CredentialManager *__hidden this, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140003450`
- `0x14000b0f4`
- `0x14000d71c`
- `0x14000d778`
- `0x14000e610`
- `0x140013404`
- `0x1400134a4`
- `0x14001391c`
- `0x140027510`
- `0x1400552f8`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027888`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027900`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027a19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027888`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027900`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027a19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140027684`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400278a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140027684`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400278a7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400278ec`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140027a09`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400278ec`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140027a09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140027676`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140027753`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140027899`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140027960`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140027a46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140027676`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140027753`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140027899`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140027960`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140027a46`
- `coredpus!__imp_GetAuthTypeName` at `0x14002798a`
- `coredpus!__imp_GetAuthTypeName` at `0x14002798a`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140027825`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140027825`

## string_xrefs

- `0x1400279fd`: `<Cred><Meta><Format xmlns="syncml:metinf">b64</Format><Type xmlns="syncml:metinf">%1</Type></Meta><Data>%2</Data></Cred>`
- `0x140027561`: `CreateCred`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::CredentialManager::CreateCred(
        Microsoft::Windows::MDM::OmadmClient::CredentialManager *this,
        struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5)
{
  const unsigned __int16 *v6; // rbx
  struct COmaDmLogger *Logger; // rax
  __int64 v10; // r8
  char v11; // al
  unsigned __int64 v12; // rcx
  unsigned int v13; // ebx
  __int64 v14; // r9
  va_list *v15; // rsi
  void *v16; // r14
  DWORD LastError; // ebx
  int v18; // ecx
  int v19; // ecx
  struct COmaDmLogger *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  struct COmaDmLogger *v25; // rax
  int ValueFromStruct; // eax
  HLOCAL v27; // r14
  DWORD v28; // ebx
  signed int v29; // eax
  int v30; // eax
  va_list AuthTypeName; // rcx
  va_list v32; // rax
  signed int v33; // eax
  unsigned __int16 *v34; // rax
  unsigned __int16 *v35; // rax
  LPWSTR lpBuffer; // [rsp+20h] [rbp-E8h]
  char *v38; // [rsp+40h] [rbp-C8h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-C0h] BYREF
  WCHAR Buffer[4]; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v41[3]; // [rsp+58h] [rbp-B0h] BYREF
  int v42; // [rsp+70h] [rbp-98h]
  char **v43; // [rsp+78h] [rbp-90h]
  int v44; // [rsp+80h] [rbp-88h] BYREF
  va_list Arguments[2]; // [rsp+88h] [rbp-80h] BYREF
  va_list *v46; // [rsp+98h] [rbp-70h] BYREF
  const unsigned __int16 *v47; // [rsp+A0h] [rbp-68h]
  struct _EVENT_DATA_DESCRIPTOR v48; // [rsp+A8h] [rbp-60h] BYREF
  int *v49; // [rsp+B8h] [rbp-50h]
  __int64 v50; // [rsp+C0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v6 = a3;
  v47 = a3;
  LODWORD(v38) = 0;
  Logger = COmaDmLogger::GetLogger();
  Microsoft::Windows::TelemetryLogger::LogFunctionEntryMeasure(Logger, 2, "CreateCred", 0);
  v41[0] = 0;
  v41[1] = "CreateCred";
  v41[2] = COmaDmLogger::GetLogger();
  v42 = 2;
  v43 = &v38;
  v11 = Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    v44 = 65;
    v49 = &v44;
    v50 = 4;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)OmaDmClientFunctionEntryPointEvent,
      v10,
      2u,
      &v48);
    v11 = Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits;
  }
  v12 = (unsigned __int64)&v38;
  v48.Ptr = (ULONGLONG)&v38;
  LOBYTE(v48.Size) = 1;
  if ( !a4 )
  {
    v13 = -805306127;
    LODWORD(v38) = -805306127;
    if ( (v11 & 8) != 0 )
    {
      v14 = 3489661169LL;
LABEL_59:
      McTemplateU0qq_EventWriteTransfer(v12, OmaDmClientFunctionReturnValueEvent, 65, v14);
      goto LABEL_60;
    }
    goto LABEL_60;
  }
  if ( a5 )
  {
    *a4 = 0;
    *a5 = 0;
    v15 = (va_list *)((char *)a2 + 576);
    v16 = (void *)*((_QWORD *)a2 + 72);
    if ( v16 )
    {
      LastError = GetLastError();
      LocalFree(v16);
      SetLastError(LastError);
      v6 = v47;
    }
    *v15 = 0;
    v46 = 0;
    hMem = 0;
    *(_OWORD *)Arguments = 0;
    v18 = *((_DWORD *)a2 + 158);
    if ( v18 )
    {
      v19 = v18 - 1;
      if ( v19 )
      {
        v12 = (unsigned int)(v19 - 1);
        if ( (_DWORD)v12 )
        {
          if ( (_DWORD)v12 != 2 )
          {
            v20 = COmaDmLogger::GetLogger();
            Microsoft::Windows::TelemetryLogger::LogMeasure(v20, 1, 15003, 0);
            MicrosoftTelemetryAssertTriggeredNoArgs(v22, v21, v23, v24, lpBuffer);
            goto LABEL_16;
          }
          v25 = COmaDmLogger::GetLogger();
          Microsoft::Windows::TelemetryLogger::LogMeasure(v25, 1, 15031, 0);
          v14 = (unsigned int)v38;
          v13 = (unsigned int)v38;
LABEL_19:
          v12 = (unsigned __int64)hMem;
          if ( hMem )
          {
            LocalFree(hMem);
            v14 = (unsigned int)v38;
          }
          if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
            goto LABEL_59;
          goto LABEL_60;
        }
        if ( !v6 )
        {
          v13 = -805306128;
          LODWORD(v38) = -805306128;
          if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
          {
            v14 = 3489661168LL;
            goto LABEL_59;
          }
          goto LABEL_60;
        }
        ValueFromStruct = (*(__int64 (__fastcall **)(Microsoft::Windows::MDM::OmadmClient::CredentialManager *, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *, const unsigned __int16 *, _QWORD, _DWORD, char *))(*(_QWORD *)this + 32LL))(
                            this,
                            a2,
                            v6,
                            0,
                            0,
                            (char *)a2 + 576);
        v13 = ValueFromStruct;
        v14 = (unsigned int)ValueFromStruct;
        LODWORD(v38) = ValueFromStruct;
        if ( ValueFromStruct < 0 )
        {
          LODWORD(v41[0]) = 15016;
LABEL_28:
          HIDWORD(v41[0]) = ValueFromStruct;
          goto LABEL_19;
        }
      }
      else
      {
        ValueFromStruct = (*(__int64 (__fastcall **)(Microsoft::Windows::MDM::OmadmClient::CredentialManager *, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *, char *))(*(_QWORD *)this + 24LL))(
                            this,
                            a2,
                            (char *)a2 + 576);
        v13 = ValueFromStruct;
        v14 = (unsigned int)ValueFromStruct;
        LODWORD(v38) = ValueFromStruct;
        if ( ValueFromStruct < 0 )
        {
          LODWORD(v41[0]) = 15017;
          goto LABEL_28;
        }
      }
      ValueFromStruct = OmaDmGetValueFromStruct(17, (char *)a2 + 48, *((unsigned int *)a2 + 156), &v46, 0);
      v13 = ValueFromStruct;
      v14 = (unsigned int)ValueFromStruct;
      LODWORD(v38) = ValueFromStruct;
      if ( ValueFromStruct < 0 )
      {
        LODWORD(v41[0]) = 6017;
        goto LABEL_28;
      }
      if ( !*v46 )
      {
        v41[0] = 0x8000FFFF00001774uLL;
        v13 = -2147418113;
        goto LABEL_19;
      }
      Arguments[0] = *v46;
      Arguments[1] = 0;
      v27 = hMem;
      if ( hMem )
      {
        v28 = GetLastError();
        LocalFree(v27);
        SetLastError(v28);
      }
      hMem = 0;
      if ( !FormatMessageW(0x2500u, L"<LocName>%1</LocName>", 0, 0, (LPWSTR)&hMem, 0x100u, Arguments) )
      {
        v29 = GetLastError();
        v13 = v29;
        if ( v29 > 0 )
          v13 = (unsigned __int16)v29 | 0x80070000;
        v14 = v13;
        LODWORD(v38) = v13;
        goto LABEL_19;
      }
    }
    else
    {
      v30 = (*(__int64 (__fastcall **)(Microsoft::Windows::MDM::OmadmClient::CredentialManager *, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *, char *))(*(_QWORD *)this + 16LL))(
              this,
              a2,
              (char *)a2 + 576);
      v13 = v30;
      LODWORD(v38) = v30;
      if ( v30 < 0 )
      {
        LODWORD(v41[0]) = 15004;
        HIDWORD(v41[0]) = v30;
        goto LABEL_43;
      }
    }
LABEL_16:
    v13 = (unsigned int)v38;
    if ( (int)v38 >= 0 )
    {
      AuthTypeName = (va_list)GetAuthTypeName(*((unsigned int *)a2 + 158));
      if ( AuthTypeName )
      {
        v32 = *v15;
        if ( *v15 )
        {
          Arguments[0] = AuthTypeName;
          Arguments[1] = v32;
          *(_QWORD *)Buffer = 0;
          if ( FormatMessageW(
                 0x2500u,
                 L"<Cred><Meta><Format xmlns=\"syncml:metinf\">b64</Format><Type xmlns=\"syncml:metinf\">%1</Type></Meta><"
                  "Data>%2</Data></Cred>",
                 0,
                 0,
                 Buffer,
                 0x100u,
                 Arguments) )
          {
            v34 = *(unsigned __int16 **)Buffer;
            *(_QWORD *)Buffer = 0;
            *a5 = v34;
            v35 = (unsigned __int16 *)hMem;
            hMem = 0;
            *a4 = v35;
            v13 = (unsigned int)v38;
            if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
            {
              v14 = (unsigned int)v38;
              goto LABEL_59;
            }
            goto LABEL_60;
          }
          v33 = GetLastError();
          v13 = v33;
          if ( v33 > 0 )
            v13 = (unsigned __int16)v33 | 0x80070000;
          LODWORD(v38) = v13;
          if ( *(_QWORD *)Buffer )
            LocalFree(*(HLOCAL *)Buffer);
          goto LABEL_43;
        }
        LODWORD(v41[0]) = 15010;
      }
      else
      {
        LODWORD(v41[0]) = 15013;
      }
      v13 = -2147418113;
      HIDWORD(v41[0]) = -2147418113;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x83,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\credentialmanager.cpp",
        (const char *)(unsigned int)v38,
        (int)lpBuffer);
    }
LABEL_43:
    v12 = (unsigned __int64)hMem;
    if ( hMem )
      LocalFree(hMem);
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
    {
      v14 = (unsigned int)v38;
      goto LABEL_59;
    }
    goto LABEL_60;
  }
  v13 = -805306126;
  LODWORD(v38) = -805306126;
  if ( (v11 & 8) != 0 )
  {
    v14 = 3489661170LL;
    goto LABEL_59;
  }
LABEL_60:
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v41);
  return v13;
}

```

## disassembly

```asm
0x140027510  push    rbx
0x140027512  push    rsi
0x140027513  push    rdi
0x140027514  push    r12
0x140027516  push    r13
0x140027518  push    r14
0x14002751a  push    r15
0x14002751c  sub     rsp, 0D0h
0x140027523  mov     rax, cs:__security_cookie
0x14002752a  xor     rax, rsp
0x14002752d  mov     [rsp+108h+var_40], rax
0x140027535  mov     r13, r9
0x140027538  mov     rbx, r8
0x14002753b  mov     [rsp+108h+var_68], rbx
0x140027543  mov     rdi, rdx
0x140027546  mov     r15, rcx
0x140027549  mov     r12, [rsp+108h+arg_20]
0x140027551  xor     r14d, r14d
0x140027554  mov     dword ptr [rsp+108h+var_C8], r14d
0x140027559  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14002755e  xor     r9d, r9d
0x140027561  lea     rsi, aCreatecred; "CreateCred"
0x140027568  mov     r8, rsi
0x14002756b  lea     edx, [r14+2]
0x14002756f  mov     rcx, rax
0x140027572  call    ?LogFunctionEntryMeasure@TelemetryLogger@Windows@Microsoft@@QEAAXW4TracingLevel@23@PEBDPEBGZZ; Microsoft::Windows::TelemetryLogger::LogFunctionEntryMeasure(Microsoft::Windows::TracingLevel,char const *,ushort const *,...)
0x140027577  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14002757c  mov     [rsp+108h+var_B0], r14
0x140027581  mov     [rsp+108h+var_A8], rsi
0x140027586  mov     [rsp+108h+var_A0], rax
0x14002758b  lea     ecx, [r14+2]
0x14002758f  mov     [rsp+108h+var_98], ecx
0x140027593  lea     rax, [rsp+108h+var_C8]
0x140027598  mov     [rsp+108h+var_90], rax
0x14002759d  mov     eax, cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits
0x1400275a3  test    al, 8
0x1400275a5  jz      short loc_1400275F7
0x1400275a7  mov     [rsp+108h+var_88], 41h ; 'A'
0x1400275b2  lea     rax, [rsp+108h+var_88]
0x1400275ba  mov     [rsp+108h+var_50], rax
0x1400275c2  mov     [rsp+108h+var_48], 4
0x1400275ce  lea     rax, [rsp+108h+var_60]
0x1400275d6  mov     [rsp+108h+lpBuffer], rax; int
0x1400275db  mov     r9d, ecx
0x1400275de  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x1400275e5  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x1400275ec  call    McGenEventWrite_EventWriteTransfer
0x1400275f1  mov     eax, cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits
0x1400275f7  lea     rcx, [rsp+108h+var_C8]
0x1400275fc  mov     qword ptr [rsp+108h+var_60], rcx
0x140027604  mov     [rsp+108h+var_58], 1
0x14002760c  test    r13, r13
0x14002760f  jnz     short loc_14002762D
0x140027611  mov     ebx, 0D00000F1h
0x140027616  mov     dword ptr [rsp+108h+var_C8], ebx
0x14002761a  test    al, 8
0x14002761c  jz      loc_140027A96
0x140027622  mov     r9d, 0D00000F1h
0x140027628  jmp     loc_140027A83
0x14002762d  test    r12, r12
0x140027630  jnz     short loc_14002764E
0x140027632  mov     ebx, 0D00000F2h
0x140027637  mov     dword ptr [rsp+108h+var_C8], ebx
0x14002763b  test    al, 8
0x14002763d  jz      loc_140027A96
0x140027643  mov     r9d, 0D00000F2h
0x140027649  jmp     loc_140027A83
0x14002764e  mov     [r13+0], r14
0x140027652  mov     [r12], r14
0x140027656  lea     rsi, [rdi+240h]
0x14002765d  mov     r14, [rsi]
0x140027660  test    r14, r14
0x140027663  jz      short loc_140027698
0x140027665  call    cs:__imp_GetLastError
0x14002766c  nop     dword ptr [rax+rax+00h]
0x140027671  mov     ebx, eax
0x140027673  mov     rcx, r14; hMem
0x140027676  call    cs:__imp_LocalFree
0x14002767d  nop     dword ptr [rax+rax+00h]
0x140027682  mov     ecx, ebx; dwErrCode
0x140027684  call    cs:__imp_SetLastError
0x14002768b  nop     dword ptr [rax+rax+00h]
0x140027690  mov     rbx, [rsp+108h+var_68]
0x140027698  xor     r14d, r14d
0x14002769b  mov     [rsi], r14
0x14002769e  mov     [rsp+108h+var_70], r14
0x1400276a6  mov     [rsp+108h+hMem], r14
0x1400276ab  xorps   xmm0, xmm0
0x1400276ae  movups  xmmword ptr [rsp+108h+var_80], xmm0
0x1400276b6  mov     ecx, [rdi+278h]
0x1400276bc  test    ecx, ecx
0x1400276be  jz      loc_140027927
0x1400276c4  sub     ecx, 1
0x1400276c7  jz      loc_1400277DC
0x1400276cd  sub     ecx, 1
0x1400276d0  jz      loc_140027776
0x1400276d6  cmp     ecx, 2
0x1400276d9  jz      short loc_140027727
0x1400276db  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x1400276e0  xor     r9d, r9d
0x1400276e3  lea     edx, [r14+1]
0x1400276e7  mov     r8d, 3A9Bh
0x1400276ed  mov     rcx, rax
0x1400276f0  call    ?LogMeasure@TelemetryLogger@Windows@Microsoft@@QEAAXW4TracingLevel@23@KPEBGZZ; Microsoft::Windows::TelemetryLogger::LogMeasure(Microsoft::Windows::TracingLevel,ulong,ushort const *,...)
0x1400276f5  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "0")
0x1400276fa  mov     ebx, dword ptr [rsp+108h+var_C8]
0x1400276fe  test    ebx, ebx
0x140027700  jns     loc_140027984
0x140027706  mov     rcx, [rsp+108h]; this
0x14002770e  mov     r9d, ebx; char *
0x140027711  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140027718  mov     edx, 83h; void *
0x14002771d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140027722  jmp     loc_140027956
0x140027727  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14002772c  xor     r9d, r9d
0x14002772f  lea     edx, [r9+1]
0x140027733  mov     r8d, 3AB7h
0x140027739  mov     rcx, rax
0x14002773c  call    ?LogMeasure@TelemetryLogger@Windows@Microsoft@@QEAAXW4TracingLevel@23@KPEBGZZ; Microsoft::Windows::TelemetryLogger::LogMeasure(Microsoft::Windows::TracingLevel,ulong,ushort const *,...)
0x140027741  mov     r9d, dword ptr [rsp+108h+var_C8]
0x140027746  mov     ebx, r9d
0x140027749  mov     rcx, [rsp+108h+hMem]; hMem
0x14002774e  test    rcx, rcx
0x140027751  jz      short loc_140027764
0x140027753  call    cs:__imp_LocalFree
0x14002775a  nop     dword ptr [rax+rax+00h]
0x14002775f  mov     r9d, dword ptr [rsp+108h+var_C8]
0x140027764  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x14002776b  jz      loc_140027A96
0x140027771  jmp     loc_140027A83
0x140027776  test    rbx, rbx
0x140027779  jnz     short loc_14002779C
0x14002777b  mov     ebx, 0D00000F0h
0x140027780  mov     dword ptr [rsp+108h+var_C8], ebx
0x140027784  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x14002778b  jz      loc_140027A96
0x140027791  mov     r9d, 0D00000F0h
0x140027797  jmp     loc_140027A83
0x14002779c  mov     rax, [r15]
0x14002779f  mov     qword ptr [rsp+108h+nSize], rsi
0x1400277a4  mov     dword ptr [rsp+108h+lpBuffer], r14d
0x1400277a9  xor     r9d, r9d
0x1400277ac  mov     r8, rbx
0x1400277af  mov     rdx, rdi
0x1400277b2  mov     rcx, r15
0x1400277b5  mov     rax, [rax+20h]
0x1400277b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400277be  mov     ebx, eax
0x1400277c0  mov     r9d, eax
0x1400277c3  mov     dword ptr [rsp+108h+var_C8], eax
0x1400277c7  test    eax, eax
0x1400277c9  jns     short loc_140027808
0x1400277cb  mov     dword ptr [rsp+108h+var_B0], 3AA8h
0x1400277d3  mov     dword ptr [rsp+108h+var_B0+4], eax
0x1400277d7  jmp     loc_140027749
0x1400277dc  mov     rax, [r15]
0x1400277df  mov     r8, rsi
0x1400277e2  mov     rdx, rdi
0x1400277e5  mov     rcx, r15
0x1400277e8  mov     rax, [rax+18h]
0x1400277ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400277f1  mov     ebx, eax
0x1400277f3  mov     r9d, eax
0x1400277f6  mov     dword ptr [rsp+108h+var_C8], eax
0x1400277fa  test    eax, eax
0x1400277fc  jns     short loc_140027808
0x1400277fe  mov     dword ptr [rsp+108h+var_B0], 3AA9h
0x140027806  jmp     short loc_1400277D3
0x140027808  lea     rdx, [rdi+30h]
0x14002780c  mov     [rsp+108h+lpBuffer], r14
0x140027811  lea     r9, [rsp+108h+var_70]
0x140027819  mov     r8d, [rdi+270h]
0x140027820  mov     ecx, 11h
0x140027825  call    cs:__imp_OmaDmGetValueFromStruct
0x14002782c  nop     dword ptr [rax+rax+00h]
0x140027831  mov     ebx, eax
0x140027833  mov     r9d, eax
0x140027836  mov     dword ptr [rsp+108h+var_C8], eax
0x14002783a  test    eax, eax
0x14002783c  jns     short loc_140027848
0x14002783e  mov     dword ptr [rsp+108h+var_B0], 1781h
0x140027846  jmp     short loc_1400277D3
0x140027848  mov     rax, [rsp+108h+var_70]
0x140027850  mov     rcx, [rax]
0x140027853  test    rcx, rcx
0x140027856  jnz     short loc_14002786E
0x140027858  mov     dword ptr [rsp+108h+var_B0], 1774h
0x140027860  mov     ebx, 8000FFFFh
0x140027865  mov     dword ptr [rsp+108h+var_B0+4], ebx
0x140027869  jmp     loc_140027749
0x14002786e  mov     [rsp+108h+var_80], rcx
0x140027876  mov     [rsp+108h+var_80+8], r14
0x14002787e  mov     r14, [rsp+108h+hMem]
0x140027883  test    r14, r14
0x140027886  jz      short loc_1400278B3
0x140027888  call    cs:__imp_GetLastError
0x14002788f  nop     dword ptr [rax+rax+00h]
0x140027894  mov     ebx, eax
0x140027896  mov     rcx, r14; hMem
0x140027899  call    cs:__imp_LocalFree
0x1400278a0  nop     dword ptr [rax+rax+00h]
0x1400278a5  mov     ecx, ebx; dwErrCode
0x1400278a7  call    cs:__imp_SetLastError
0x1400278ae  nop     dword ptr [rax+rax+00h]
0x1400278b3  xor     r14d, r14d
0x1400278b6  mov     [rsp+108h+hMem], r14
0x1400278bb  lea     rax, [rsp+108h+var_80]
0x1400278c3  mov     [rsp+108h+Arguments], rax; Arguments
0x1400278c8  mov     [rsp+108h+nSize], 100h; nSize
0x1400278d0  lea     rax, [rsp+108h+hMem]
0x1400278d5  mov     [rsp+108h+lpBuffer], rax; lpBuffer
0x1400278da  xor     r9d, r9d; dwLanguageId
0x1400278dd  xor     r8d, r8d; dwMessageId
0x1400278e0  lea     rdx, ?gc_szLocNameXmlTemplate@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "<LocName>%1</LocName>"
0x1400278e7  mov     ecx, 2500h; dwFlags
0x1400278ec  call    cs:__imp_FormatMessageW
0x1400278f3  nop     dword ptr [rax+rax+00h]
0x1400278f8  test    eax, eax
0x1400278fa  jnz     loc_1400276FA
0x140027900  call    cs:__imp_GetLastError
0x140027907  nop     dword ptr [rax+rax+00h]
0x14002790c  mov     ebx, eax
0x14002790e  test    eax, eax
0x140027910  jle     short loc_14002791B
0x140027912  movzx   ebx, ax
0x140027915  or      ebx, 80070000h
0x14002791b  mov     r9d, ebx
0x14002791e  mov     dword ptr [rsp+108h+var_C8], ebx
0x140027922  jmp     loc_140027749
0x140027927  mov     rax, [r15]
0x14002792a  mov     r8, rsi
0x14002792d  mov     rdx, rdi
0x140027930  mov     rcx, r15
0x140027933  mov     rax, [rax+10h]
0x140027937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002793c  mov     ebx, eax
0x14002793e  mov     dword ptr [rsp+108h+var_C8], eax
0x140027942  test    eax, eax
0x140027944  jns     loc_1400276FA
0x14002794a  mov     dword ptr [rsp+108h+var_B0], 3A9Ch
0x140027952  mov     dword ptr [rsp+108h+var_B0+4], eax
0x140027956  mov     rcx, [rsp+108h+hMem]; hMem
0x14002795b  test    rcx, rcx
0x14002795e  jz      short loc_14002796D
0x140027960  call    cs:__imp_LocalFree
0x140027967  nop     dword ptr [rax+rax+00h]
0x14002796c  nop
0x14002796d  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x140027974  jz      loc_140027A96
0x14002797a  mov     r9d, dword ptr [rsp+108h+var_C8]
0x14002797f  jmp     loc_140027A83
0x140027984  mov     ecx, [rdi+278h]
0x14002798a  call    cs:__imp_GetAuthTypeName
0x140027991  nop     dword ptr [rax+rax+00h]
0x140027996  mov     rcx, rax
0x140027999  test    rax, rax
0x14002799c  jnz     short loc_1400279B1
0x14002799e  mov     dword ptr [rsp+108h+var_B0], 3AA5h
0x1400279a6  mov     ebx, 8000FFFFh
0x1400279ab  mov     dword ptr [rsp+108h+var_B0+4], ebx
0x1400279af  jmp     short loc_140027956
0x1400279b1  mov     rax, [rsi]
0x1400279b4  test    rax, rax
0x1400279b7  jnz     short loc_1400279C3
0x1400279b9  mov     dword ptr [rsp+108h+var_B0], 3AA2h
0x1400279c1  jmp     short loc_1400279A6
0x1400279c3  mov     [rsp+108h+var_80], rcx
0x1400279cb  mov     [rsp+108h+var_80+8], rax
0x1400279d3  mov     qword ptr [rsp+108h+Buffer], r14
0x1400279d8  lea     rax, [rsp+108h+var_80]
0x1400279e0  mov     [rsp+108h+Arguments], rax; Arguments
0x1400279e5  mov     [rsp+108h+nSize], 100h; nSize
0x1400279ed  lea     rax, [rsp+108h+Buffer]
0x1400279f2  mov     [rsp+108h+lpBuffer], rax; lpBuffer
0x1400279f7  xor     r9d, r9d; dwLanguageId
0x1400279fa  xor     r8d, r8d; dwMessageId
0x1400279fd  lea     rdx, ?gc_szCredXmlTemplate@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "<Cred><Meta><Format xmlns=\"syncml:meti"...
0x140027a04  mov     ecx, 2500h; dwFlags
0x140027a09  call    cs:__imp_FormatMessageW
0x140027a10  nop     dword ptr [rax+rax+00h]
0x140027a15  test    eax, eax
0x140027a17  jnz     short loc_140027A57
0x140027a19  call    cs:__imp_GetLastError
0x140027a20  nop     dword ptr [rax+rax+00h]
0x140027a25  mov     ebx, eax
0x140027a27  test    eax, eax
0x140027a29  jle     short loc_140027A34
0x140027a2b  movzx   ebx, ax
0x140027a2e  or      ebx, 80070000h
0x140027a34  mov     dword ptr [rsp+108h+var_C8], ebx
0x140027a38  mov     rcx, qword ptr [rsp+108h+Buffer]; hMem
0x140027a3d  test    rcx, rcx
0x140027a40  jz      loc_140027956
0x140027a46  call    cs:__imp_LocalFree
0x140027a4d  nop     dword ptr [rax+rax+00h]
0x140027a52  jmp     loc_140027956
0x140027a57  mov     rax, qword ptr [rsp+108h+Buffer]
0x140027a5c  mov     qword ptr [rsp+108h+Buffer], r14
0x140027a61  mov     [r12], rax
  ... truncated ...
```
