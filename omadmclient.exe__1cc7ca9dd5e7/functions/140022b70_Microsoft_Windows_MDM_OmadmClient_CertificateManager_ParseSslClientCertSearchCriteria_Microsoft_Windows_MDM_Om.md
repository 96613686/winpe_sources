# Microsoft::Windows::MDM::OmadmClient::CertificateManager::ParseSslClientCertSearchCriteria(Microsoft::Windows::MDM::OmadmClient::SslClientCertInfo *,tagOMADMACCTINFO &,ulong)

- ea: `0x140022b70`
- end: `0x140022fa5`
- name: `?ParseSslClientCertSearchCriteria@CertificateManager@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEAUSslClientCertInfo@2345@AEAUtagOMADMACCTINFO@@K@Z`
- size: `1077`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::CertificateManager *__hidden this, struct Microsoft::Windows::MDM::OmadmClient::SslClientCertInfo *, struct tagOMADMACCTINFO *, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140021a20`
- `0x1400223f0`

## callees

- `0x140003450`
- `0x14000b0f4`
- `0x14000d71c`
- `0x14000d778`
- `0x14000e610`
- `0x140013404`
- `0x140022b70`
- `0x140022fac`
- `0x1400233e8`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140022d53`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140022d53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140022d84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140022e07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140022e7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140022ec8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140022d84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140022e07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140022e7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140022ec8`
- `DMCmnUtils!BigStrcat` at `0x140022cbb`
- `DMCmnUtils!BigStrcat` at `0x140022cbb`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140022c3f`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140022c3f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::CertificateManager::ParseSslClientCertSearchCriteria(
        Microsoft::Windows::MDM::OmadmClient::CertificateManager *this,
        struct Microsoft::Windows::MDM::OmadmClient::SslClientCertInfo *a2,
        struct tagOMADMACCTINFO *a3,
        unsigned int a4)
{
  __int64 v8; // r8
  unsigned int ValueFromStruct; // eax
  __int64 v10; // rdx
  Microsoft::Windows::MDM::OmadmClient::CertificateManager *v11; // rcx
  __int64 v12; // r8
  unsigned int v13; // edi
  __int64 v14; // r9
  struct IConfigManager2URI *v15; // rcx
  unsigned __int16 *v16; // rbx
  struct IConfigManager2URI *v17; // rcx
  HRESULT Instance; // eax
  struct IConfigManager2URI *v19; // rcx
  int v20; // eax
  struct IConfigManager2URI *v21; // rcx
  int v22; // eax
  struct IConfigManager2URI *v23; // rcx
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  struct IConfigManager2URI *v27; // rcx
  struct IConfigManager2URI *v28; // rcx
  int ppv; // [rsp+20h] [rbp-59h]
  int ppva; // [rsp+20h] [rbp-59h]
  unsigned int v32; // [rsp+30h] [rbp-49h] BYREF
  struct IConfigManager2URI *v33; // [rsp+38h] [rbp-41h] BYREF
  unsigned __int16 *v34; // [rsp+40h] [rbp-39h] BYREF
  _QWORD *v35; // [rsp+48h] [rbp-31h] BYREF
  _QWORD v36[3]; // [rsp+50h] [rbp-29h] BYREF
  int v37; // [rsp+68h] [rbp-11h]
  unsigned int *v38; // [rsp+70h] [rbp-9h]
  struct _EVENT_DATA_DESCRIPTOR v39; // [rsp+78h] [rbp-1h] BYREF
  unsigned __int16 **v40; // [rsp+88h] [rbp+Fh]
  __int64 v41; // [rsp+90h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v32 = 0;
  v36[0] = 0;
  v36[1] = "ParseSslClientCertSearchCriteria";
  v36[2] = COmaDmLogger::GetLogger();
  v37 = 2;
  v38 = &v32;
  v33 = 0;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    LODWORD(v34) = 51;
    v40 = &v34;
    v41 = 4;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)OmaDmClientFunctionEntryPointEvent,
      v8,
      2u,
      &v39);
  }
  v39.Ptr = (ULONGLONG)&v32;
  *(_QWORD *)&v39.Size = &v33;
  LOBYTE(v40) = 1;
  v35 = 0;
  ValueFromStruct = OmaDmGetValueFromStruct(23, a3, 0xFFFFFFFFLL, &v35, 0);
  v13 = ValueFromStruct;
  v14 = ValueFromStruct;
  v32 = ValueFromStruct;
  if ( (ValueFromStruct & 0x80000000) != 0 )
  {
    LODWORD(v36[0]) = 6031;
    HIDWORD(v36[0]) = ValueFromStruct;
    v15 = v33;
    if ( v33 )
    {
      (*(void (__fastcall **)(struct IConfigManager2URI *, __int64, __int64, _QWORD))(*(_QWORD *)v33 + 16LL))(
        v33,
        v10,
        v12,
        ValueFromStruct);
      v33 = 0;
      v14 = v32;
    }
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v15, OmaDmClientFunctionReturnValueEvent, 51, v14);
    goto LABEL_46;
  }
  if ( *v35 )
  {
    v16 = BigStrcat(2u, L".?", *v35, ValueFromStruct);
    v34 = v16;
    if ( !v16 )
    {
      v13 = -2147024882;
      v32 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5AE,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\certificatemanager.cpp",
        (const char *)0x8007000ELL,
        ppv);
      v17 = v33;
      if ( v33 )
      {
        (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v33 + 16LL))(v33);
        v33 = 0;
      }
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v17, OmaDmClientFunctionReturnValueEvent, 51, v32);
      goto LABEL_46;
    }
    v32 = 0;
    Instance = CoCreateInstance(
                 &GUID_50a41ef1_6bfa_4b7e_973e_798ea0bebad4,
                 0,
                 1u,
                 &GUID_e34e5896_40b2_45c4_a9c0_8a9601c3b0a6,
                 (LPVOID *)&v33);
    v13 = Instance;
    v32 = Instance;
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5B6,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\certificatemanager.cpp",
        (const char *)(unsigned int)Instance,
        ppva);
      LocalFree(v16);
      v19 = v33;
      if ( v33 )
      {
        (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v33 + 16LL))(v33);
        v33 = 0;
      }
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v19, OmaDmClientFunctionReturnValueEvent, 51, v32);
      goto LABEL_46;
    }
    v20 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, unsigned __int16 *))(*(_QWORD *)v33 + 40LL))(v33, v16);
    v13 = v20;
    v32 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5B9,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\certificatemanager.cpp",
        (const char *)(unsigned int)v20,
        ppva);
      LocalFree(v16);
      v21 = v33;
      if ( v33 )
      {
        (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v33 + 16LL))(v33);
        v33 = 0;
      }
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v21, OmaDmClientFunctionReturnValueEvent, 51, v32);
      goto LABEL_46;
    }
    v22 = Microsoft::Windows::MDM::OmadmClient::CertificateManager::ParseSslClientCertSubjectCriteria(this, v33, a2, a4);
    v13 = v22;
    v32 = v22;
    if ( v22 < 0 )
    {
      LODWORD(v36[0]) = 12039;
      HIDWORD(v36[0]) = v22;
      LocalFree(v16);
      v23 = v33;
      if ( v33 )
      {
        (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v33 + 16LL))(v33);
        v33 = 0;
      }
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v23, OmaDmClientFunctionReturnValueEvent, 51, v32);
      goto LABEL_46;
    }
    LocalFree(v16);
    v14 = v32;
  }
  if ( *((_QWORD *)a2 + 6) == *((_QWORD *)a2 + 5)
    && (v24 = Microsoft::Windows::MDM::OmadmClient::CertificateManager::ParseSslClientCertStoresCriteria(v11, v33, a2),
        v13 = v24,
        v14 = (unsigned int)v24,
        v32 = v24,
        v24 < 0) )
  {
    LODWORD(v36[0]) = 12038;
    HIDWORD(v36[0]) = v24;
    v27 = v33;
    if ( v33 )
    {
      (*(void (__fastcall **)(struct IConfigManager2URI *, __int64, __int64, _QWORD))(*(_QWORD *)v33 + 16LL))(
        v33,
        v25,
        v26,
        (unsigned int)v24);
      v33 = 0;
      v14 = v32;
    }
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v27, OmaDmClientFunctionReturnValueEvent, 51, v14);
  }
  else
  {
    v13 = v14;
    v28 = v33;
    if ( v33 )
    {
      (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v33 + 16LL))(v33);
      v33 = 0;
      v14 = v32;
    }
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v28, OmaDmClientFunctionReturnValueEvent, 51, v14);
  }
LABEL_46:
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v36);
  return v13;
}

```

## disassembly

```asm
0x140022b70  push    rbp
0x140022b72  push    rbx
0x140022b73  push    rsi
0x140022b74  push    rdi
0x140022b75  push    r12
0x140022b77  push    r14
0x140022b79  push    r15
0x140022b7b  lea     rbp, [rsp-27h]
0x140022b80  sub     rsp, 0A0h
0x140022b87  mov     rax, cs:__security_cookie
0x140022b8e  xor     rax, rsp
0x140022b91  mov     [rbp+57h+var_38], rax
0x140022b95  mov     r15d, r9d
0x140022b98  mov     rbx, r8
0x140022b9b  mov     rsi, rdx
0x140022b9e  mov     r14, rcx
0x140022ba1  xor     r12d, r12d
0x140022ba4  mov     [rbp+57h+var_A0], r12d
0x140022ba8  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x140022bad  mov     [rbp+57h+var_80], r12
0x140022bb1  lea     rcx, aParsesslclient; "ParseSslClientCertSearchCriteria"
0x140022bb8  mov     [rbp+57h+var_78], rcx
0x140022bbc  mov     [rbp+57h+var_70], rax
0x140022bc0  lea     ecx, [r12+2]
0x140022bc5  mov     [rbp+57h+var_68], ecx
0x140022bc8  lea     rax, [rbp+57h+var_A0]
0x140022bcc  mov     [rbp+57h+var_60], rax
0x140022bd0  mov     [rbp+57h+var_98], r12
0x140022bd4  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x140022bdb  jz      short loc_140022C13
0x140022bdd  mov     dword ptr [rbp+57h+var_90], 33h ; '3'
0x140022be4  lea     rax, [rbp+57h+var_90]
0x140022be8  mov     [rbp+57h+var_48], rax
0x140022bec  mov     [rbp+57h+var_40], 4
0x140022bf4  lea     rax, [rbp+57h+var_58]
0x140022bf8  mov     qword ptr [rsp+0D0h+ppv], rax
0x140022bfd  mov     r9d, ecx
0x140022c00  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x140022c07  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x140022c0e  call    McGenEventWrite_EventWriteTransfer
0x140022c13  lea     rax, [rbp+57h+var_A0]
0x140022c17  mov     [rbp+57h+var_58], rax
0x140022c1b  lea     rax, [rbp+57h+var_98]
0x140022c1f  mov     [rbp+57h+var_50], rax
0x140022c23  mov     byte ptr [rbp+57h+var_48], 1
0x140022c27  mov     [rbp+57h+var_88], r12
0x140022c2b  mov     qword ptr [rsp+0D0h+ppv], r12; int
0x140022c30  lea     r9, [rbp+57h+var_88]
0x140022c34  or      r8d, 0FFFFFFFFh
0x140022c38  mov     rdx, rbx
0x140022c3b  lea     ecx, [r8+18h]
0x140022c3f  call    cs:__imp_OmaDmGetValueFromStruct
0x140022c46  nop     dword ptr [rax+rax+00h]
0x140022c4b  mov     edi, eax
0x140022c4d  mov     r9d, eax
0x140022c50  mov     [rbp+57h+var_A0], eax
0x140022c53  test    eax, eax
0x140022c55  jns     short loc_140022C9F
0x140022c57  mov     dword ptr [rbp+57h+var_80], 178Fh
0x140022c5e  mov     dword ptr [rbp+57h+var_80+4], eax
0x140022c61  mov     rcx, [rbp+57h+var_98]
0x140022c65  test    rcx, rcx
0x140022c68  jz      short loc_140022C7E
0x140022c6a  mov     rax, [rcx]
0x140022c6d  mov     rax, [rax+10h]
0x140022c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022c76  mov     [rbp+57h+var_98], r12
0x140022c7a  mov     r9d, [rbp+57h+var_A0]
0x140022c7e  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x140022c85  jz      short loc_140022C9A
0x140022c87  mov     r8d, 33h ; '3'
0x140022c8d  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x140022c94  call    McTemplateU0qq_EventWriteTransfer
0x140022c99  nop
0x140022c9a  jmp     loc_140022F7B
0x140022c9f  mov     rax, [rbp+57h+var_88]
0x140022ca3  mov     r8, [rax]
0x140022ca6  test    r8, r8
0x140022ca9  jz      loc_140022ED8
0x140022caf  lea     rdx, asc_140071AEC; ".?"
0x140022cb6  mov     ecx, 2
0x140022cbb  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x140022cc2  nop     dword ptr [rax+rax+00h]
0x140022cc7  mov     rbx, rax
0x140022cca  mov     [rbp+57h+var_90], rax
0x140022cce  test    rax, rax
0x140022cd1  jnz     short loc_140022D32
0x140022cd3  mov     edi, 8007000Eh
0x140022cd8  mov     [rbp+57h+var_A0], edi
0x140022cdb  mov     rcx, [rbp+5Fh]; this
0x140022cdf  mov     r9d, edi; char *
0x140022ce2  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140022ce9  mov     edx, 5AEh; void *
0x140022cee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140022cf3  nop
0x140022cf4  mov     rcx, [rbp+57h+var_98]
0x140022cf8  test    rcx, rcx
0x140022cfb  jz      short loc_140022D0D
0x140022cfd  mov     rax, [rcx]
0x140022d00  mov     rax, [rax+10h]
0x140022d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022d09  mov     [rbp+57h+var_98], r12
0x140022d0d  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x140022d14  jz      short loc_140022D2D
0x140022d16  mov     r9d, [rbp+57h+var_A0]
0x140022d1a  mov     r8d, 33h ; '3'
0x140022d20  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x140022d27  call    McTemplateU0qq_EventWriteTransfer
0x140022d2c  nop
0x140022d2d  jmp     loc_140022F7B
0x140022d32  mov     [rbp+57h+var_A0], r12d
0x140022d36  lea     rax, [rbp+57h+var_98]
0x140022d3a  mov     qword ptr [rsp+0D0h+ppv], rax; int
0x140022d3f  lea     r9, _GUID_e34e5896_40b2_45c4_a9c0_8a9601c3b0a6; riid
0x140022d46  xor     edx, edx; pUnkOuter
0x140022d48  lea     r8d, [rdx+1]; dwClsContext
0x140022d4c  lea     rcx, _GUID_50a41ef1_6bfa_4b7e_973e_798ea0bebad4; rclsid
0x140022d53  call    cs:__imp_CoCreateInstance
0x140022d5a  nop     dword ptr [rax+rax+00h]
0x140022d5f  mov     edi, eax
0x140022d61  mov     [rbp+57h+var_A0], eax
0x140022d64  test    eax, eax
0x140022d66  jns     short loc_140022DCF
0x140022d68  mov     rcx, [rbp+5Fh]; this
0x140022d6c  mov     r9d, eax; char *
0x140022d6f  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140022d76  mov     edx, 5B6h; void *
0x140022d7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140022d80  nop
0x140022d81  mov     rcx, rbx; hMem
0x140022d84  call    cs:__imp_LocalFree
0x140022d8b  nop     dword ptr [rax+rax+00h]
0x140022d90  nop
0x140022d91  mov     rcx, [rbp+57h+var_98]
0x140022d95  test    rcx, rcx
0x140022d98  jz      short loc_140022DAA
0x140022d9a  mov     rax, [rcx]
0x140022d9d  mov     rax, [rax+10h]
0x140022da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022da6  mov     [rbp+57h+var_98], r12
0x140022daa  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x140022db1  jz      short loc_140022DCA
0x140022db3  mov     r9d, [rbp+57h+var_A0]
0x140022db7  mov     r8d, 33h ; '3'
0x140022dbd  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x140022dc4  call    McTemplateU0qq_EventWriteTransfer
0x140022dc9  nop
0x140022dca  jmp     loc_140022F7B
0x140022dcf  mov     rcx, [rbp+57h+var_98]
0x140022dd3  mov     rax, [rcx]
0x140022dd6  mov     rdx, rbx
0x140022dd9  mov     rax, [rax+28h]
0x140022ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022de2  mov     edi, eax
0x140022de4  mov     [rbp+57h+var_A0], eax
0x140022de7  test    eax, eax
0x140022de9  jns     short loc_140022E52
0x140022deb  mov     rcx, [rbp+5Fh]; this
0x140022def  mov     r9d, eax; char *
0x140022df2  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140022df9  mov     edx, 5B9h; void *
0x140022dfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140022e03  nop
0x140022e04  mov     rcx, rbx; hMem
0x140022e07  call    cs:__imp_LocalFree
0x140022e0e  nop     dword ptr [rax+rax+00h]
0x140022e13  nop
0x140022e14  mov     rcx, [rbp+57h+var_98]
0x140022e18  test    rcx, rcx
0x140022e1b  jz      short loc_140022E2D
0x140022e1d  mov     rax, [rcx]
0x140022e20  mov     rax, [rax+10h]
0x140022e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022e29  mov     [rbp+57h+var_98], r12
0x140022e2d  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x140022e34  jz      short loc_140022E4D
0x140022e36  mov     r9d, [rbp+57h+var_A0]
0x140022e3a  mov     r8d, 33h ; '3'
0x140022e40  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x140022e47  call    McTemplateU0qq_EventWriteTransfer
0x140022e4c  nop
0x140022e4d  jmp     loc_140022F7B
0x140022e52  mov     r9d, r15d; unsigned int
0x140022e55  mov     r8, rsi; struct Microsoft::Windows::MDM::OmadmClient::SslClientCertInfo *
0x140022e58  mov     rdx, [rbp+57h+var_98]; struct IConfigManager2URI *
0x140022e5c  mov     rcx, r14; this
0x140022e5f  call    ?ParseSslClientCertSubjectCriteria@CertificateManager@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEAUIConfigManager2URI@@PEAUSslClientCertInfo@2345@K@Z; Microsoft::Windows::MDM::OmadmClient::CertificateManager::ParseSslClientCertSubjectCriteria(IConfigManager2URI *,Microsoft::Windows::MDM::OmadmClient::SslClientCertInfo *,ulong)
0x140022e64  mov     edi, eax
0x140022e66  mov     [rbp+57h+var_A0], eax
0x140022e69  test    eax, eax
0x140022e6b  jns     short loc_140022EC5
0x140022e6d  mov     dword ptr [rbp+57h+var_80], 2F07h
0x140022e74  mov     dword ptr [rbp+57h+var_80+4], eax
0x140022e77  mov     rcx, rbx; hMem
0x140022e7a  call    cs:__imp_LocalFree
0x140022e81  nop     dword ptr [rax+rax+00h]
0x140022e86  nop
0x140022e87  mov     rcx, [rbp+57h+var_98]
0x140022e8b  test    rcx, rcx
0x140022e8e  jz      short loc_140022EA0
0x140022e90  mov     rax, [rcx]
0x140022e93  mov     rax, [rax+10h]
0x140022e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022e9c  mov     [rbp+57h+var_98], r12
0x140022ea0  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x140022ea7  jz      short loc_140022EC0
0x140022ea9  mov     r9d, [rbp+57h+var_A0]
0x140022ead  mov     r8d, 33h ; '3'
0x140022eb3  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x140022eba  call    McTemplateU0qq_EventWriteTransfer
0x140022ebf  nop
0x140022ec0  jmp     loc_140022F7B
0x140022ec5  mov     rcx, rbx; hMem
0x140022ec8  call    cs:__imp_LocalFree
0x140022ecf  nop     dword ptr [rax+rax+00h]
0x140022ed4  mov     r9d, [rbp+57h+var_A0]
0x140022ed8  mov     rax, [rsi+30h]
0x140022edc  cmp     rax, [rsi+28h]
0x140022ee0  jnz     short loc_140022F3F
0x140022ee2  mov     r8, rsi; struct Microsoft::Windows::MDM::OmadmClient::SslClientCertInfo *
0x140022ee5  mov     rdx, [rbp+57h+var_98]; struct IConfigManager2URI *
0x140022ee9  call    ?ParseSslClientCertStoresCriteria@CertificateManager@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEAUIConfigManager2URI@@PEAUSslClientCertInfo@2345@@Z; Microsoft::Windows::MDM::OmadmClient::CertificateManager::ParseSslClientCertStoresCriteria(IConfigManager2URI *,Microsoft::Windows::MDM::OmadmClient::SslClientCertInfo *)
0x140022eee  mov     edi, eax
0x140022ef0  mov     r9d, eax
0x140022ef3  mov     [rbp+57h+var_A0], eax
0x140022ef6  test    eax, eax
0x140022ef8  jns     short loc_140022F3F
0x140022efa  mov     dword ptr [rbp+57h+var_80], 2F06h
0x140022f01  mov     dword ptr [rbp+57h+var_80+4], eax
0x140022f04  mov     rcx, [rbp+57h+var_98]
0x140022f08  test    rcx, rcx
0x140022f0b  jz      short loc_140022F21
0x140022f0d  mov     rax, [rcx]
0x140022f10  mov     rax, [rax+10h]
0x140022f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022f19  mov     [rbp+57h+var_98], r12
0x140022f1d  mov     r9d, [rbp+57h+var_A0]
0x140022f21  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x140022f28  jz      short loc_140022F3D
0x140022f2a  mov     r8d, 33h ; '3'
0x140022f30  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x140022f37  call    McTemplateU0qq_EventWriteTransfer
0x140022f3c  nop
0x140022f3d  jmp     short loc_140022F7B
0x140022f3f  mov     edi, r9d
0x140022f42  mov     rcx, [rbp+57h+var_98]
0x140022f46  test    rcx, rcx
0x140022f49  jz      short loc_140022F5F
0x140022f4b  mov     rax, [rcx]
0x140022f4e  mov     rax, [rax+10h]
0x140022f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022f57  mov     [rbp+57h+var_98], r12
0x140022f5b  mov     r9d, [rbp+57h+var_A0]
0x140022f5f  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x140022f66  jz      short loc_140022F7B
0x140022f68  mov     r8d, 33h ; '3'
0x140022f6e  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x140022f75  call    McTemplateU0qq_EventWriteTransfer
0x140022f7a  nop
0x140022f7b  lea     rcx, [rbp+57h+var_80]; this
0x140022f7f  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x140022f84  mov     eax, edi
0x140022f86  mov     rcx, [rbp+57h+var_38]
0x140022f8a  xor     rcx, rsp; StackCookie
0x140022f8d  call    __security_check_cookie
0x140022f92  add     rsp, 0A0h
0x140022f99  pop     r15
0x140022f9b  pop     r14
0x140022f9d  pop     r12
0x140022f9f  pop     rdi
0x140022fa0  pop     rsi
0x140022fa1  pop     rbx
0x140022fa2  pop     rbp
0x140022fa3  retn
```
