# Microsoft::Windows::MDM::OmadmClient::NetworkHandler::CreateUserAgent(Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState &,ushort * *,ushort *,ulong,ulong *)

- ea: `0x140032d10`
- end: `0x1400330fc`
- name: `?CreateUserAgent@NetworkHandler@OmadmClient@MDM@Windows@Microsoft@@UEAAJAEAVSyncmlSessionState@2345@PEAPEAGPEAGKPEAK@Z`
- size: `1004`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::NetworkHandler *__hidden this, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *, unsigned __int16 **, unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140003450`
- `0x14000b0f4`
- `0x14000d71c`
- `0x14000d778`
- `0x14000e610`
- `0x140013404`
- `0x140032d10`
- `0x140069010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsupr_s` at `0x140032f06`
- `api-ms-win-crt-private-l1-1-0!_o__wcsupr_s` at `0x140032f06`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140032e66`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140032e66`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140032e83`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140032e83`
- `DMCmnUtils!BigStrcat` at `0x140032e41`
- `DMCmnUtils!BigStrcat` at `0x140032f8f`
- `DMCmnUtils!BigStrcat` at `0x140032e41`
- `DMCmnUtils!BigStrcat` at `0x140032f8f`
- `DMCmnUtils!InvStrCmpW` at `0x140032e28`
- `DMCmnUtils!InvStrCmpW` at `0x140032e28`

## string_xrefs

- `0x140032d68`: `CreateUserAgent`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::NetworkHandler::CreateUserAgent(
        Microsoft::Windows::MDM::OmadmClient::NetworkHandler *this,
        struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *a2,
        unsigned __int16 **a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned int *a6)
{
  __int64 v9; // r8
  char v10; // al
  int v11; // esi
  const unsigned __int16 *v12; // rcx
  __int64 v13; // rcx
  unsigned __int16 *v14; // rbx
  wchar_t *v15; // rsi
  wchar_t *v16; // r15
  wchar_t *v17; // rsi
  __int64 v18; // rdx
  wchar_t *v19; // rax
  unsigned int v20; // ecx
  unsigned int v21; // ebx
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // r9
  const unsigned __int16 *v25; // r8
  int v27; // [rsp+20h] [rbp-D8h]
  unsigned int v28; // [rsp+40h] [rbp-B8h] BYREF
  wchar_t *v29; // [rsp+48h] [rbp-B0h] BYREF
  _QWORD v30[3]; // [rsp+50h] [rbp-A8h] BYREF
  int v31; // [rsp+68h] [rbp-90h]
  unsigned int *v32; // [rsp+70h] [rbp-88h]
  unsigned __int16 *v33; // [rsp+78h] [rbp-80h]
  Microsoft::Windows::MDM::OmadmClient::NetworkHandler *v34; // [rsp+80h] [rbp-78h]
  unsigned int *v35; // [rsp+88h] [rbp-70h]
  struct _EVENT_DATA_DESCRIPTOR v36; // [rsp+90h] [rbp-68h] BYREF
  wchar_t **v37; // [rsp+A0h] [rbp-58h]
  __int64 v38; // [rsp+A8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v34 = this;
  v35 = a6;
  v28 = 0;
  v30[0] = 0;
  v30[1] = "CreateUserAgent";
  v30[2] = COmaDmLogger::GetLogger();
  v31 = 2;
  v32 = &v28;
  v10 = Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits;
  v11 = 4;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    LODWORD(v29) = 61;
    v37 = &v29;
    v38 = 4;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)OmaDmClientFunctionEntryPointEvent,
      v9,
      2u,
      &v36);
    v10 = Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits;
  }
  v36.Ptr = (ULONGLONG)&v28;
  LOBYTE(v36.Size) = 1;
  v12 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
  if ( !v12 )
  {
    LODWORD(v30[0]) = 18030;
LABEL_37:
    HIDWORD(v30[0]) = -2147418113;
    if ( (v10 & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v12, OmaDmClientFunctionReturnValueEvent, 61, v28);
    Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v30);
    return 2147549183LL;
  }
  if ( !*((_QWORD *)a2 + 203) )
  {
    LODWORD(v30[0]) = 18004;
    goto LABEL_37;
  }
  v33 = 0;
  if ( InvStrCmpW(v12, L"sprint") )
  {
    v14 = BigStrcat(1u, L"MSFT OMA DM Client/1.2.0.1");
    *a4 = 0;
    goto LABEL_25;
  }
  v15 = wcsrchr(*((const wchar_t **)a2 + 203), 0x3Au);
  v29 = wcsstr(*((const wchar_t **)a2 + 203), L"ESN:");
  v16 = (wchar_t *)*((_QWORD *)a2 + 203);
  if ( v15 )
    v17 = v15 + 1;
  else
    v17 = (wchar_t *)*((_QWORD *)a2 + 203);
  if ( !v17 )
  {
    v21 = -2147024809;
    v20 = -2147024809;
LABEL_32:
    v28 = v20;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x175,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\networkhandler.cpp",
      (const char *)0x80070057LL,
      v27);
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
    {
      v24 = v28;
      goto LABEL_34;
    }
LABEL_35:
    Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v30);
    return v21;
  }
  v18 = 0x7FFFFFFF;
  v19 = v17;
  do
  {
    if ( !*v19 )
      break;
    ++v19;
    --v18;
  }
  while ( v18 );
  v20 = v18 == 0 ? 0x80070057 : 0;
  if ( !v18 )
  {
    v21 = -2147024809;
    goto LABEL_32;
  }
  v28 = v18 == 0 ? 0x80070057 : 0;
  v22 = _o__wcsupr_s(v17, ((0x7FFFFFFF - v18) & -(__int64)(v18 != 0)) + 1);
  v21 = v22;
  if ( v22 )
  {
    if ( v22 > 0 )
      v21 = (unsigned __int16)v22 | 0x80070000;
    v28 = v21;
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) == 0 )
      goto LABEL_35;
    v24 = v21;
    goto LABEL_34;
  }
  v25 = L" ESN/";
  if ( v16 != v29 )
    v25 = L" MEID/";
  v14 = BigStrcat(7u, *((_QWORD *)a2 + 205), L"/", *((_QWORD *)a2 + 206), v25, v17, L" MSFT/", *((_QWORD *)a2 + 207));
  v33 = v14;
  (*(void (__fastcall **)(Microsoft::Windows::MDM::OmadmClient::NetworkHandler *, unsigned __int16 *, _QWORD))(*(_QWORD *)v34 + 16LL))(
    v34,
    a4,
    a5);
  v11 = 3;
LABEL_25:
  *v35 = v11;
  if ( !v14 )
  {
    v21 = -2147024882;
    v28 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19B,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\networkhandler.cpp",
      (const char *)0x8007000ELL,
      v27);
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
    {
      v24 = v28;
LABEL_34:
      McTemplateU0qq_EventWriteTransfer(v23, OmaDmClientFunctionReturnValueEvent, 61, v24);
      goto LABEL_35;
    }
    goto LABEL_35;
  }
  v28 = 0;
  *a3 = v14;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
    McTemplateU0qq_EventWriteTransfer(v13, OmaDmClientFunctionReturnValueEvent, 61, v28);
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v30);
  return 0;
}

```

## disassembly

```asm
0x140032d10  push    rbx
0x140032d12  push    rsi
0x140032d13  push    rdi
0x140032d14  push    r12
0x140032d16  push    r13
0x140032d18  push    r14
0x140032d1a  push    r15
0x140032d1c  sub     rsp, 0C0h
0x140032d23  mov     rax, cs:__security_cookie
0x140032d2a  xor     rax, rsp
0x140032d2d  mov     [rsp+0F8h+var_48], rax
0x140032d35  mov     r12, r9
0x140032d38  mov     r13, r8
0x140032d3b  mov     r14, rdx
0x140032d3e  mov     [rsp+0F8h+var_78], rcx
0x140032d46  mov     rax, [rsp+0F8h+arg_28]
0x140032d4e  mov     [rsp+0F8h+var_70], rax
0x140032d56  xor     r15d, r15d
0x140032d59  mov     [rsp+0F8h+var_B8], r15d
0x140032d5e  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x140032d63  mov     [rsp+0F8h+var_A8], r15
0x140032d68  lea     rcx, aCreateuseragen; "CreateUserAgent"
0x140032d6f  mov     [rsp+0F8h+var_A0], rcx
0x140032d74  mov     [rsp+0F8h+var_98], rax
0x140032d79  mov     [rsp+0F8h+var_90], 2
0x140032d81  lea     rax, [rsp+0F8h+var_B8]
0x140032d86  mov     [rsp+0F8h+var_88], rax
0x140032d8b  mov     eax, cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits
0x140032d91  lea     esi, [r15+4]
0x140032d95  test    al, 8
0x140032d97  jz      short loc_140032DE0
0x140032d99  mov     dword ptr [rsp+0F8h+var_B0], 3Dh ; '='
0x140032da1  lea     rax, [rsp+0F8h+var_B0]
0x140032da6  mov     [rsp+0F8h+var_58], rax
0x140032dae  mov     [rsp+0F8h+var_50], rsi
0x140032db6  lea     rax, [rsp+0F8h+var_68]
0x140032dbe  mov     qword ptr [rsp+0F8h+var_D8], rax; int
0x140032dc3  lea     r9d, [r15+2]
0x140032dc7  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x140032dce  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x140032dd5  call    McGenEventWrite_EventWriteTransfer
0x140032dda  mov     eax, cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits
0x140032de0  lea     rdi, [rsp+0F8h+var_B8]
0x140032de5  mov     qword ptr [rsp+0F8h+var_68], rdi
0x140032ded  mov     ebx, 1
0x140032df2  mov     [rsp+0F8h+var_60], bl
0x140032df9  mov     rcx, [r14+48h]
0x140032dfd  test    rcx, rcx
0x140032e00  jnz     short loc_140032E0F
0x140032e02  mov     dword ptr [rsp+0F8h+var_A8], 466Eh
0x140032e0a  jmp     loc_1400330A5
0x140032e0f  cmp     [r14+658h], r15
0x140032e16  jz      loc_14003309D
0x140032e1c  mov     [rsp+0F8h+var_80], r15
0x140032e21  lea     rdx, aSprint; "sprint"
0x140032e28  call    cs:__imp_?InvStrCmpW@@YAHPEBG0@Z; InvStrCmpW(ushort const *,ushort const *)
0x140032e2f  nop     dword ptr [rax+rax+00h]
0x140032e34  test    eax, eax
0x140032e36  jz      short loc_140032E5A
0x140032e38  lea     rdx, ?gc_szUserAgentName@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "MSFT OMA DM Client/1.2.0.1"
0x140032e3f  mov     ecx, ebx
0x140032e41  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x140032e48  nop     dword ptr [rax+rax+00h]
0x140032e4d  mov     rbx, rax
0x140032e50  mov     [r12], r15w
0x140032e55  jmp     loc_140032FCA
0x140032e5a  mov     edx, 3Ah ; ':'; Ch
0x140032e5f  mov     rcx, [r14+658h]; Str
0x140032e66  call    cs:__imp_wcsrchr
0x140032e6d  nop     dword ptr [rax+rax+00h]
0x140032e72  mov     rsi, rax
0x140032e75  lea     rdx, ?gc_szEsnPrefix@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "ESN:"
0x140032e7c  mov     rcx, [r14+658h]; Str
0x140032e83  call    cs:__imp_wcsstr
0x140032e8a  nop     dword ptr [rax+rax+00h]
0x140032e8f  mov     [rsp+0F8h+var_B0], rax
0x140032e94  mov     r15, [r14+658h]
0x140032e9b  xor     r10d, r10d
0x140032e9e  test    rsi, rsi
0x140032ea1  jz      short loc_140032EA9
0x140032ea3  add     rsi, 2
0x140032ea7  jmp     short loc_140032EAC
0x140032ea9  mov     rsi, r15
0x140032eac  test    rsi, rsi
0x140032eaf  jz      loc_140033046
0x140032eb5  mov     r8d, 7FFFFFFFh
0x140032ebb  mov     edx, r8d
0x140032ebe  mov     rax, rsi
0x140032ec1  cmp     [rax], r10w
0x140032ec5  jz      short loc_140032ED0
0x140032ec7  add     rax, 2
0x140032ecb  sub     rdx, rbx
0x140032ece  jnz     short loc_140032EC1
0x140032ed0  mov     rax, rdx
0x140032ed3  neg     rax
0x140032ed6  sbb     ecx, ecx
0x140032ed8  not     ecx
0x140032eda  and     ecx, 80070057h
0x140032ee0  mov     rax, rdx
0x140032ee3  sub     r8, rdx
0x140032ee6  neg     rax
0x140032ee9  sbb     r9, r9
0x140032eec  and     r9, r8
0x140032eef  test    rdx, rdx
0x140032ef2  jnz     short loc_140032EFB
0x140032ef4  mov     ebx, ecx
0x140032ef6  jmp     loc_14003304D
0x140032efb  mov     [rsp+0F8h+var_B8], ecx
0x140032eff  lea     rdx, [r9+1]
0x140032f03  mov     rcx, rsi
0x140032f06  call    cs:__imp__o__wcsupr_s
0x140032f0d  nop     dword ptr [rax+rax+00h]
0x140032f12  mov     ebx, eax
0x140032f14  test    eax, eax
0x140032f16  jz      short loc_140032F3C
0x140032f18  jle     short loc_140032F23
0x140032f1a  movzx   ebx, ax
0x140032f1d  or      ebx, 80070000h
0x140032f23  mov     [rsp+0F8h+var_B8], ebx
0x140032f27  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x140032f2e  jz      loc_14003308F
0x140032f34  mov     r9d, ebx
0x140032f37  jmp     loc_14003307C
0x140032f3c  mov     rax, [r14+678h]
0x140032f43  lea     rcx, ?gc_szMeidToken@OmadmClient@MDM@Windows@Microsoft@@3QBGB; " MEID/"
0x140032f4a  lea     r8, ?gc_szEsnToken@OmadmClient@MDM@Windows@Microsoft@@3QBGB; " ESN/"
0x140032f51  cmp     r15, [rsp+0F8h+var_B0]
0x140032f56  cmovnz  r8, rcx
0x140032f5a  mov     [rsp+0F8h+var_C0], rax
0x140032f5f  lea     rax, ?gc_szMsftToken@OmadmClient@MDM@Windows@Microsoft@@3QBGB; " MSFT/"
0x140032f66  mov     [rsp+0F8h+var_C8], rax
0x140032f6b  mov     [rsp+0F8h+var_D0], rsi
0x140032f70  mov     qword ptr [rsp+0F8h+var_D8], r8; int
0x140032f75  mov     r9, [r14+670h]
0x140032f7c  lea     r8, asc_14006D22C; "/"
0x140032f83  mov     rdx, [r14+668h]
0x140032f8a  mov     ecx, 7
0x140032f8f  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x140032f96  nop     dword ptr [rax+rax+00h]
0x140032f9b  mov     rbx, rax
0x140032f9e  mov     [rsp+0F8h+var_80], rax
0x140032fa3  mov     rcx, [rsp+0F8h+var_78]
0x140032fab  mov     rax, [rcx]
0x140032fae  mov     r8d, [rsp+0F8h+arg_20]
0x140032fb6  mov     rdx, r12
0x140032fb9  mov     rax, [rax+10h]
0x140032fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032fc2  mov     esi, 3
0x140032fc7  xor     r15d, r15d
0x140032fca  mov     rax, [rsp+0F8h+var_70]
0x140032fd2  mov     [rax], esi
0x140032fd4  test    rbx, rbx
0x140032fd7  jz      short loc_140033012
0x140032fd9  mov     [rsp+0F8h+var_B8], r15d
0x140032fde  mov     [r13+0], rbx
0x140032fe2  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x140032fe9  jz      short loc_140033001
0x140032feb  mov     r9d, [rdi]
0x140032fee  mov     r8d, 3Dh ; '='
0x140032ff4  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x140032ffb  call    McTemplateU0qq_EventWriteTransfer
0x140033000  nop
0x140033001  lea     rcx, [rsp+0F8h+var_A8]; this
0x140033006  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14003300b  xor     eax, eax
0x14003300d  jmp     loc_1400330D8
0x140033012  mov     ebx, 8007000Eh
0x140033017  mov     [rsp+0F8h+var_B8], ebx
0x14003301b  mov     rcx, [rsp+0F8h]; this
0x140033023  mov     r9d, ebx; char *
0x140033026  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14003302d  mov     edx, 19Bh; void *
0x140033032  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140033037  nop
0x140033038  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x14003303f  jz      short loc_14003308F
0x140033041  mov     r9d, [rdi]
0x140033044  jmp     short loc_14003307C
0x140033046  mov     ebx, 80070057h
0x14003304b  mov     ecx, ebx
0x14003304d  mov     [rsp+0F8h+var_B8], ecx
0x140033051  mov     rcx, [rsp+0F8h]; this
0x140033059  mov     r9d, ebx; char *
0x14003305c  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140033063  mov     edx, 175h; void *
0x140033068  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003306d  nop
0x14003306e  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x140033075  jz      short loc_14003308F
0x140033077  mov     r9d, [rsp+0F8h+var_B8]
0x14003307c  mov     r8d, 3Dh ; '='
0x140033082  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x140033089  call    McTemplateU0qq_EventWriteTransfer
0x14003308e  nop
0x14003308f  lea     rcx, [rsp+0F8h+var_A8]; this
0x140033094  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x140033099  mov     eax, ebx
0x14003309b  jmp     short loc_1400330D8
0x14003309d  mov     dword ptr [rsp+0F8h+var_A8], 4654h
0x1400330a5  mov     dword ptr [rsp+0F8h+var_A8+4], 8000FFFFh
0x1400330ad  test    al, 8
0x1400330af  jz      short loc_1400330C9
0x1400330b1  mov     r9d, [rsp+0F8h+var_B8]
0x1400330b6  mov     r8d, 3Dh ; '='
0x1400330bc  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x1400330c3  call    McTemplateU0qq_EventWriteTransfer
0x1400330c8  nop
0x1400330c9  lea     rcx, [rsp+0F8h+var_A8]; this
0x1400330ce  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x1400330d3  mov     eax, 8000FFFFh
0x1400330d8  mov     rcx, [rsp+0F8h+var_48]
0x1400330e0  xor     rcx, rsp; StackCookie
0x1400330e3  call    __security_check_cookie
0x1400330e8  add     rsp, 0C0h
0x1400330ef  pop     r15
0x1400330f1  pop     r14
0x1400330f3  pop     r13
0x1400330f5  pop     r12
0x1400330f7  pop     rdi
0x1400330f8  pop     rsi
0x1400330f9  pop     rbx
0x1400330fa  retn
```
