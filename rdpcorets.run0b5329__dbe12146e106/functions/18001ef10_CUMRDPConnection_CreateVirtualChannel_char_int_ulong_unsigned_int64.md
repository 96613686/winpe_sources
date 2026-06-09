# CUMRDPConnection::CreateVirtualChannel(char *,int,ulong,unsigned __int64 *)

- ea: `0x18001ef10`
- end: `0x18001f51f`
- name: `?CreateVirtualChannel@CUMRDPConnection@@UEAAJPEADHKPEA_K@Z`
- size: `1551`
- prototype: `__int64 __fastcall(CUMRDPConnection *__hidden this, char *, int, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800013e8`
- `0x1800015f0`
- `0x1800071c0`
- `0x1800071f0`
- `0x180012200`
- `0x180016d9c`
- `0x18001ef10`
- `0x180033da0`
- `0x180055ca0`
- `0x180058234`
- `0x18014d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001f074`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001f257`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001f26f`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001f287`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001f29f`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001f2b7`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001f2cf`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001f2e7`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001f074`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001f257`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001f26f`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001f287`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001f29f`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001f2b7`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001f2cf`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001f2e7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001ef64`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001f4f0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001ef64`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001f4f0`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18001ef9b`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18001ef9b`

## string_xrefs

- `0x18001f0af`: `CreateVirtualChannel`
- `0x18001f22e`: `CreateVirtualChannel`
- `0x18001f341`: `CreateVirtualChannel`
- `0x18001f3b4`: `CreateVirtualChannel`
- `0x18001f45b`: `CreateVirtualChannel`
- `0x18001f215`: `ValidateChannelCallerTokenSID`
- `0x18001f39e`: `Failed CreateVirtualChannel call on this Connections Stack`

## pseudocode

```c
__int64 __fastcall CUMRDPConnection::CreateVirtualChannel(
        CUMRDPConnection *this,
        char *a2,
        int a3,
        unsigned int a4,
        unsigned __int64 *a5)
{
  GUID v5; // xmm0
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rbx
  __int64 v12; // r14
  __int64 v13; // rsi
  __int64 v14; // rdi
  __int64 v15; // rdx
  int v16; // ecx
  __int64 v17; // r8
  int v18; // r9d
  int v19; // ecx
  int v20; // r9d
  int v21; // ebx
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  int v25; // eax
  unsigned int v26; // edi
  __int16 *v27; // rdx
  const char *v28; // rax
  int v29; // ecx
  int v30; // r9d
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v40; // [rsp+60h] [rbp-61h] BYREF
  char *v41; // [rsp+68h] [rbp-59h] BYREF
  const char *v42; // [rsp+70h] [rbp-51h] BYREF
  const char *v43; // [rsp+78h] [rbp-49h] BYREF
  const char *v44; // [rsp+80h] [rbp-41h] BYREF
  const char *v45; // [rsp+88h] [rbp-39h] BYREF
  const char *v46; // [rsp+90h] [rbp-31h] BYREF
  __int64 v47; // [rsp+98h] [rbp-29h] BYREF
  __int64 v48; // [rsp+A0h] [rbp-21h] BYREF
  __int64 v49; // [rsp+A8h] [rbp-19h] BYREF
  __int64 v50; // [rsp+B0h] [rbp-11h] BYREF
  __int64 v51; // [rsp+B8h] [rbp-9h] BYREF
  GUID ActivityId; // [rsp+C0h] [rbp-1h] BYREF

  v5 = (GUID)*((_OWORD *)this + 47);
  LODWORD(v46) = a3;
  v42 = (const char *)a5;
  ActivityId = v5;
  EventActivityIdControl(4u, &ActivityId);
  v47 = 0;
  v11 = 0;
  v41 = (char *)this + 96;
  v12 = 0;
  v51 = 0;
  v13 = 0;
  v50 = 0;
  v14 = 0;
  v49 = 0;
  v48 = 0;
  if ( *((_DWORD *)this + 26) )
    PAL_System_CritSecEnter(*((_QWORD *)this + 12), v9, v10);
  if ( *((_QWORD *)this + 26) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v50, v9, v10);
    v12 = *((_QWORD *)this + 26);
    v50 = v12;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v50);
  }
  if ( *((_QWORD *)this + 30) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v51, v9, v10);
    v11 = *((_QWORD *)this + 30);
    v51 = v11;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v51);
  }
  v40 = 0;
  if ( *((_QWORD *)this + 22) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v49, v9, v10);
    v49 = *((_QWORD *)this + 22);
    v13 = v49;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v49);
    v40 = v13;
  }
  if ( *((_QWORD *)this + 16) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v48, v9, v10);
    v14 = *((_QWORD *)this + 16);
    v48 = v14;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v48);
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v41);
  if ( !v12 || !v40 )
  {
    v21 = -2147024809;
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_55;
    LODWORD(v40) = 4166;
    v44 = "Called in bad state";
    v27 = &word_1801955D6;
    v43 = "CreateVirtualChannel";
    v42 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    v28 = "Error condition failed";
    goto LABEL_54;
  }
  if ( (_DWORD)v46 )
  {
    if ( !(unsigned int)_o__stricmp("DRDYNVC", a2)
      || !(unsigned int)_o__stricmp("rdpgrfx", a2)
      || !(unsigned int)_o__stricmp("rdpinpt", a2)
      || !(unsigned int)_o__stricmp("rdpcmd", a2)
      || !(unsigned int)_o__stricmp("rdplic", a2)
      || !(unsigned int)_o__stricmp("Microsoft::Windows::RDS::Graphics", a2) )
    {
      v21 = -2147024891;
      goto LABEL_55;
    }
    v26 = a4 | 3;
    if ( (unsigned int)_o__stricmp("RDPSND", a2) )
      v26 = a4;
    v21 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 416LL))(v13, &v47);
    if ( v21 < 0 )
    {
      v16 = dword_1801B76C8;
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_55;
      LODWORD(v40) = 4243;
      v44 = "Failed to Get Stack VC MGr";
      v27 = (__int16 *)byte_1801954FD;
      v43 = "CreateVirtualChannel";
      v42 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v28 = "Error HResult failed";
      goto LABEL_54;
    }
  }
  else
  {
    if ( !(unsigned int)_o__stricmp("Microsoft::Windows::RDS::Telemetry", a2) )
    {
      v21 = -2147024891;
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        LODWORD(v41) = 4180;
        v45 = "Forbidden channel name: Microsoft::Windows::RDS::Telemetry";
        LODWORD(v40) = -2147024891;
        v42 = "CreateVirtualChannel";
        v43 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
        v44 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v19,
          (unsigned int)byte_180195585,
          v17,
          v20,
          (__int64)&v44,
          (__int64)&v40,
          (__int64)&v43,
          (__int64)&v41,
          (__int64)&v42,
          (__int64)&v45);
      }
      goto LABEL_55;
    }
    if ( !v11 )
    {
      v21 = -2147418113;
      goto LABEL_55;
    }
    if ( v11 != v47 )
    {
      TCntPtr<IRdpSQMLogger>::SafeRelease(&v47, v15, v17);
      v47 = v11;
      TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v47);
    }
    LODWORD(v46) = 0;
    if ( v14
      && (*(int (__fastcall **)(__int64, const wchar_t *, const char **))(*(_QWORD *)v14 + 32LL))(
           v14,
           L"DVCRemapChannelName",
           &v46) >= 0
      && (_DWORD)v46 )
    {
      v25 = 0;
      if ( *a2 == 35 )
      {
        if ( a2[1] == 49 )
        {
          v25 = 32;
        }
        else if ( a2[1] == 52 )
        {
          v25 = 64;
        }
      }
      a4 |= v25;
      if ( (unsigned int)dword_1801B76C8 > 4 )
      {
        LODWORD(v40) = (_DWORD)v46;
        v43 = "The TestDVC name remapping feature enabled status";
        v44 = a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v22,
          (unsigned int)&word_18019554E,
          v23,
          v24,
          (__int64)&v43,
          (__int64)&v40,
          (__int64)&v44);
      }
    }
    v26 = a4 | 8;
    if ( (a4 & 0xF8) != 0 )
      v26 = a4;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LockdownDVCs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_LockdownDVCs>::GetImpl'::`2'::impl) )
  {
    v21 = ValidateChannelCallerTokenSID(a2);
    if ( v21 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_55;
      LODWORD(v40) = 4249;
      v44 = "ValidateChannelCallerTokenSID";
      v27 = (__int16 *)&dword_1801954AC;
      v43 = "CreateVirtualChannel";
      v42 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v28 = "Error HResult failed";
LABEL_54:
      v45 = v28;
      LODWORD(v41) = v21;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v16,
        (_DWORD)v27,
        v17,
        v18,
        (__int64)&v45,
        (__int64)&v41,
        (__int64)&v42,
        (__int64)&v40,
        (__int64)&v43,
        (__int64)&v44);
      goto LABEL_55;
    }
  }
  v21 = (*(__int64 (__fastcall **)(__int64, __int64, char *, _QWORD, const char *))(*(_QWORD *)v12 + 32LL))(
          v12,
          v47,
          a2,
          v26,
          v42);
  if ( v21 < 0 && (unsigned int)dword_1801B76C8 > 2 )
  {
    v44 = a2;
    v43 = "Failed CreateVirtualChannel call on this Connections Stack";
    LODWORD(v40) = 4257;
    v42 = "CreateVirtualChannel";
    v45 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    v46 = "Error HResult failed";
    LODWORD(v41) = v21;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v29,
      (unsigned int)&word_18019544E,
      v17,
      v30,
      (__int64)&v46,
      (__int64)&v41,
      (__int64)&v45,
      (__int64)&v40,
      (__int64)&v42,
      (__int64)&v43,
      (__int64)&v44);
  }
LABEL_55:
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v48, v15, v17);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v49, v31, v32);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v50, v33, v34);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v51, v35, v36);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v47, v37, v38);
  EventActivityIdControl(2u, &ActivityId);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x18001ef10  mov     [rsp-8+arg_0], rbx
0x18001ef15  push    rbp
0x18001ef16  push    rsi
0x18001ef17  push    rdi
0x18001ef18  push    r12
0x18001ef1a  push    r13
0x18001ef1c  push    r14
0x18001ef1e  push    r15
0x18001ef20  lea     rbp, [rsp-1Fh]
0x18001ef25  sub     rsp, 0E0h
0x18001ef2c  mov     rax, cs:__security_cookie
0x18001ef33  xor     rax, rsp
0x18001ef36  mov     [rbp+4Fh+var_40], rax
0x18001ef3a  movups  xmm0, xmmword ptr [rcx+2F0h]
0x18001ef41  mov     rax, [rbp+4Fh+arg_20]
0x18001ef45  mov     r15, rdx
0x18001ef48  mov     r13, rcx
0x18001ef4b  mov     dword ptr [rbp+4Fh+var_80], r8d
0x18001ef4f  lea     rdx, [rbp+4Fh+ActivityId]; ActivityId
0x18001ef53  mov     [rbp+4Fh+var_A0], rax
0x18001ef57  mov     ecx, 4; ControlCode
0x18001ef5c  mov     r12d, r9d
0x18001ef5f  movdqu  xmmword ptr [rbp+4Fh+ActivityId.Data1], xmm0
0x18001ef64  call    cs:__imp_EventActivityIdControl
0x18001ef6a  lea     rcx, [r13+60h]
0x18001ef6e  mov     [rbp+4Fh+var_78], 0
0x18001ef76  xor     ebx, ebx
0x18001ef78  mov     [rbp+4Fh+var_A8], rcx
0x18001ef7c  xor     r14d, r14d
0x18001ef7f  mov     [rbp+4Fh+var_58], rbx
0x18001ef83  xor     esi, esi
0x18001ef85  mov     [rbp+4Fh+var_60], r14
0x18001ef89  xor     edi, edi
0x18001ef8b  mov     [rbp+4Fh+var_68], rsi
0x18001ef8f  mov     [rbp+4Fh+var_70], rdi
0x18001ef93  cmp     [rcx+8], ebx
0x18001ef96  jz      short loc_18001EFA1
0x18001ef98  mov     rcx, [rcx]
0x18001ef9b  call    cs:__imp_PAL_System_CritSecEnter
0x18001efa1  cmp     [r13+0D0h], rbx
0x18001efa8  jz      short loc_18001EFC7
0x18001efaa  lea     rcx, [rbp+4Fh+var_60]
0x18001efae  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18001efb3  mov     r14, [r13+0D0h]
0x18001efba  lea     rcx, [rbp+4Fh+var_60]
0x18001efbe  mov     [rbp+4Fh+var_60], r14
0x18001efc2  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18001efc7  cmp     [r13+0F0h], rbx
0x18001efce  jz      short loc_18001EFED
0x18001efd0  lea     rcx, [rbp+4Fh+var_58]
0x18001efd4  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18001efd9  mov     rbx, [r13+0F0h]
0x18001efe0  lea     rcx, [rbp+4Fh+var_58]
0x18001efe4  mov     [rbp+4Fh+var_58], rbx
0x18001efe8  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18001efed  mov     [rbp+4Fh+var_B0], rsi
0x18001eff1  cmp     [r13+0B0h], rsi
0x18001eff8  jz      short loc_18001F01B
0x18001effa  lea     rcx, [rbp+4Fh+var_68]
0x18001effe  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18001f003  mov     rsi, [r13+0B0h]
0x18001f00a  lea     rcx, [rbp+4Fh+var_68]
0x18001f00e  mov     [rbp+4Fh+var_68], rsi
0x18001f012  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18001f017  mov     [rbp+4Fh+var_B0], rsi
0x18001f01b  cmp     [r13+80h], rdi
0x18001f022  jz      short loc_18001F041
0x18001f024  lea     rcx, [rbp+4Fh+var_70]
0x18001f028  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18001f02d  mov     rdi, [r13+80h]
0x18001f034  lea     rcx, [rbp+4Fh+var_70]
0x18001f038  mov     [rbp+4Fh+var_70], rdi
0x18001f03c  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18001f041  lea     rcx, [rbp+4Fh+var_A8]; this
0x18001f045  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18001f04a  xor     r13d, r13d
0x18001f04d  test    r14, r14
0x18001f050  jz      loc_18001F432
0x18001f056  cmp     [rbp+4Fh+var_B0], r13
0x18001f05a  jz      loc_18001F432
0x18001f060  mov     rdx, r15
0x18001f063  cmp     dword ptr [rbp+4Fh+var_80], r13d
0x18001f067  jnz     loc_18001F250
0x18001f06d  lea     rcx, aMicrosoftWindo; "Microsoft::Windows::RDS::Telemetry"
0x18001f074  call    cs:__imp__o__stricmp
0x18001f07a  test    eax, eax
0x18001f07c  jnz     loc_18001F109
0x18001f082  mov     eax, cs:dword_1801B76C8
0x18001f088  mov     ebx, 80070005h
0x18001f08d  cmp     eax, 2
0x18001f090  jbe     loc_18001F4BA
0x18001f096  lea     rax, aForbiddenChann; "Forbidden channel name: Microsoft::Wind"...
0x18001f09d  mov     dword ptr [rbp+4Fh+var_A8], 1054h
0x18001f0a4  mov     [rbp+4Fh+var_88], rax
0x18001f0a8  lea     rdx, byte_180195585
0x18001f0af  lea     rax, aCreatevirtualc; "CreateVirtualChannel"
0x18001f0b6  mov     dword ptr [rbp+4Fh+var_B0], ebx
0x18001f0b9  mov     [rbp+4Fh+var_A0], rax
0x18001f0bd  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18001f0c4  mov     [rbp+4Fh+var_98], rax
0x18001f0c8  lea     rax, aErrorCondition; "Error condition failed"
0x18001f0cf  mov     [rbp+4Fh+var_90], rax
0x18001f0d3  lea     rax, [rbp+4Fh+var_88]
0x18001f0d7  mov     [rsp+110h+var_C8], rax
0x18001f0dc  lea     rax, [rbp+4Fh+var_A0]
0x18001f0e0  mov     [rsp+110h+var_D0], rax
0x18001f0e5  lea     rax, [rbp+4Fh+var_A8]
0x18001f0e9  mov     [rsp+110h+var_D8], rax
0x18001f0ee  lea     rax, [rbp+4Fh+var_98]
0x18001f0f2  mov     [rsp+110h+var_E0], rax
0x18001f0f7  lea     rax, [rbp+4Fh+var_B0]
0x18001f0fb  mov     [rsp+110h+var_E8], rax
0x18001f100  lea     rax, [rbp+4Fh+var_90]
0x18001f104  jmp     loc_18001F4B0
0x18001f109  test    rbx, rbx
0x18001f10c  jnz     short loc_18001F118
0x18001f10e  mov     ebx, 8000FFFFh
0x18001f113  jmp     loc_18001F4BA
0x18001f118  cmp     rbx, [rbp+4Fh+var_78]
0x18001f11c  jz      short loc_18001F134
0x18001f11e  lea     rcx, [rbp+4Fh+var_78]
0x18001f122  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18001f127  lea     rcx, [rbp+4Fh+var_78]
0x18001f12b  mov     [rbp+4Fh+var_78], rbx
0x18001f12f  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18001f134  mov     dword ptr [rbp+4Fh+var_80], r13d
0x18001f138  test    rdi, rdi
0x18001f13b  jz      loc_18001F1D2
0x18001f141  mov     rax, [rdi]
0x18001f144  lea     r8, [rbp+4Fh+var_80]
0x18001f148  lea     rdx, aDvcremapchanne; "DVCRemapChannelName"
0x18001f14f  mov     rcx, rdi
0x18001f152  mov     rax, [rax+20h]
0x18001f156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f15b  test    eax, eax
0x18001f15d  js      short loc_18001F1D2
0x18001f15f  cmp     dword ptr [rbp+4Fh+var_80], r13d
0x18001f163  jz      short loc_18001F1D2
0x18001f165  cmp     byte ptr [r15], 23h ; '#'
0x18001f169  mov     eax, r13d
0x18001f16c  jnz     short loc_18001F188
0x18001f16e  cmp     byte ptr [r15+1], 31h ; '1'
0x18001f173  jz      short loc_18001F183
0x18001f175  cmp     byte ptr [r15+1], 34h ; '4'
0x18001f17a  jnz     short loc_18001F188
0x18001f17c  mov     eax, 40h ; '@'
0x18001f181  jmp     short loc_18001F188
0x18001f183  mov     eax, 20h ; ' '
0x18001f188  or      r12d, eax
0x18001f18b  mov     eax, cs:dword_1801B76C8
0x18001f191  cmp     eax, 4
0x18001f194  jbe     short loc_18001F1D2
0x18001f196  mov     eax, dword ptr [rbp+4Fh+var_80]
0x18001f199  lea     rdx, word_18019554E
0x18001f1a0  mov     dword ptr [rbp+4Fh+var_B0], eax
0x18001f1a3  lea     rax, aTheTestdvcName; "The TestDVC name remapping feature enab"...
0x18001f1aa  mov     [rbp+4Fh+var_98], rax
0x18001f1ae  lea     rax, [rbp+4Fh+var_90]
0x18001f1b2  mov     [rsp+110h+var_E0], rax
0x18001f1b7  lea     rax, [rbp+4Fh+var_B0]
0x18001f1bb  mov     [rsp+110h+var_E8], rax
0x18001f1c0  lea     rax, [rbp+4Fh+var_98]
0x18001f1c4  mov     [rsp+110h+var_F0], rax
0x18001f1c9  mov     [rbp+4Fh+var_90], r15
0x18001f1cd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001f1d2  mov     edi, r12d
0x18001f1d5  or      edi, 8
0x18001f1d8  test    r12b, 0F8h
0x18001f1dc  cmovnz  edi, r12d
0x18001f1e0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LockdownDVCs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LockdownDVCs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LockdownDVCs> `wil::Feature<__WilFeatureTraits_Feature_LockdownDVCs>::GetImpl(void)'::`2'::impl
0x18001f1e7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_LockdownDVCs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LockdownDVCs>::__private_IsEnabled(void)
0x18001f1ec  test    al, al
0x18001f1ee  jz      loc_18001F363
0x18001f1f4  mov     rcx, r15; String1
0x18001f1f7  call    ?ValidateChannelCallerTokenSID@@YAJPEBD@Z; ValidateChannelCallerTokenSID(char const *)
0x18001f1fc  mov     ebx, eax
0x18001f1fe  test    eax, eax
0x18001f200  jns     loc_18001F363
0x18001f206  mov     eax, cs:dword_1801B76C8
0x18001f20c  cmp     eax, 2
0x18001f20f  jbe     loc_18001F4BA
0x18001f215  lea     rax, aValidatechanne; "ValidateChannelCallerTokenSID"
0x18001f21c  mov     dword ptr [rbp+4Fh+var_B0], 1099h
0x18001f223  mov     [rbp+4Fh+var_90], rax
0x18001f227  lea     rdx, dword_1801954AC
0x18001f22e  lea     rax, aCreatevirtualc; "CreateVirtualChannel"
0x18001f235  mov     [rbp+4Fh+var_98], rax
0x18001f239  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18001f240  mov     [rbp+4Fh+var_A0], rax
0x18001f244  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18001f24b  jmp     loc_18001F478
0x18001f250  lea     rcx, aDrdynvc; "DRDYNVC"
0x18001f257  call    cs:__imp__o__stricmp
0x18001f25d  test    eax, eax
0x18001f25f  jz      loc_18001F428
0x18001f265  mov     rdx, r15
0x18001f268  lea     rcx, aRdpgrfx; "rdpgrfx"
0x18001f26f  call    cs:__imp__o__stricmp
0x18001f275  test    eax, eax
0x18001f277  jz      loc_18001F428
0x18001f27d  mov     rdx, r15
0x18001f280  lea     rcx, aRdpinpt; "rdpinpt"
0x18001f287  call    cs:__imp__o__stricmp
0x18001f28d  test    eax, eax
0x18001f28f  jz      loc_18001F428
0x18001f295  mov     rdx, r15
0x18001f298  lea     rcx, aRdpcmd; "rdpcmd"
0x18001f29f  call    cs:__imp__o__stricmp
0x18001f2a5  test    eax, eax
0x18001f2a7  jz      loc_18001F428
0x18001f2ad  mov     rdx, r15
0x18001f2b0  lea     rcx, aRdplic; "rdplic"
0x18001f2b7  call    cs:__imp__o__stricmp
0x18001f2bd  test    eax, eax
0x18001f2bf  jz      loc_18001F428
0x18001f2c5  mov     rdx, r15
0x18001f2c8  lea     rcx, aMicrosoftWindo_0; "Microsoft::Windows::RDS::Graphics"
0x18001f2cf  call    cs:__imp__o__stricmp
0x18001f2d5  test    eax, eax
0x18001f2d7  jz      loc_18001F428
0x18001f2dd  mov     rdx, r15
0x18001f2e0  lea     rcx, aRdpsnd; "RDPSND"
0x18001f2e7  call    cs:__imp__o__stricmp
0x18001f2ed  mov     edi, r12d
0x18001f2f0  lea     rdx, [rbp+4Fh+var_78]
0x18001f2f4  or      edi, 3
0x18001f2f7  mov     rcx, rsi
0x18001f2fa  test    eax, eax
0x18001f2fc  mov     rax, [rsi]
0x18001f2ff  cmovnz  edi, r12d
0x18001f303  mov     rax, [rax+1A0h]
0x18001f30a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f30f  mov     ebx, eax
0x18001f311  test    eax, eax
0x18001f313  jns     loc_18001F1E0
0x18001f319  mov     ecx, cs:dword_1801B76C8
0x18001f31f  cmp     ecx, 2
0x18001f322  jbe     loc_18001F4BA
0x18001f328  lea     rax, aFailedToGetSta_0; "Failed to Get Stack VC MGr"
0x18001f32f  mov     dword ptr [rbp+4Fh+var_B0], 1093h
0x18001f336  mov     [rbp+4Fh+var_90], rax
0x18001f33a  lea     rdx, byte_1801954FD
0x18001f341  lea     rax, aCreatevirtualc; "CreateVirtualChannel"
0x18001f348  mov     [rbp+4Fh+var_98], rax
0x18001f34c  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18001f353  mov     [rbp+4Fh+var_A0], rax
0x18001f357  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18001f35e  jmp     loc_18001F478
0x18001f363  mov     rax, [r14]
0x18001f366  mov     r9d, edi
0x18001f369  mov     rcx, [rbp+4Fh+var_A0]
0x18001f36d  mov     r8, r15
0x18001f370  mov     rdx, [rbp+4Fh+var_78]
0x18001f374  mov     [rsp+110h+var_F0], rcx
0x18001f379  mov     rcx, r14
0x18001f37c  mov     rax, [rax+20h]
0x18001f380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f385  mov     ebx, eax
0x18001f387  test    eax, eax
0x18001f389  jns     loc_18001F4BA
0x18001f38f  mov     eax, cs:dword_1801B76C8
0x18001f395  cmp     eax, 2
0x18001f398  jbe     loc_18001F4BA
0x18001f39e  lea     rax, aFailedCreatevi; "Failed CreateVirtualChannel call on thi"...
0x18001f3a5  mov     [rbp+4Fh+var_90], r15
0x18001f3a9  mov     [rbp+4Fh+var_98], rax
0x18001f3ad  lea     rdx, word_18019544E
0x18001f3b4  lea     rax, aCreatevirtualc; "CreateVirtualChannel"
0x18001f3bb  mov     dword ptr [rbp+4Fh+var_B0], 10A1h
0x18001f3c2  mov     [rbp+4Fh+var_A0], rax
0x18001f3c6  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18001f3cd  mov     [rbp+4Fh+var_88], rax
0x18001f3d1  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18001f3d8  mov     [rbp+4Fh+var_80], rax
0x18001f3dc  lea     rax, [rbp+4Fh+var_90]
0x18001f3e0  mov     [rsp+110h+var_C0], rax
0x18001f3e5  lea     rax, [rbp+4Fh+var_98]
0x18001f3e9  mov     [rsp+110h+var_C8], rax
0x18001f3ee  lea     rax, [rbp+4Fh+var_A0]
0x18001f3f2  mov     [rsp+110h+var_D0], rax
0x18001f3f7  lea     rax, [rbp+4Fh+var_B0]
0x18001f3fb  mov     [rsp+110h+var_D8], rax
0x18001f400  lea     rax, [rbp+4Fh+var_88]
0x18001f404  mov     [rsp+110h+var_E0], rax
0x18001f409  lea     rax, [rbp+4Fh+var_A8]
0x18001f40d  mov     [rsp+110h+var_E8], rax
0x18001f412  lea     rax, [rbp+4Fh+var_80]
0x18001f416  mov     [rsp+110h+var_F0], rax
0x18001f41b  mov     dword ptr [rbp+4Fh+var_A8], ebx
0x18001f41e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001f423  jmp     loc_18001F4BA
0x18001f428  mov     ebx, 80070005h
0x18001f42d  jmp     loc_18001F4BA
0x18001f432  mov     eax, cs:dword_1801B76C8
0x18001f438  mov     ebx, 80070057h
0x18001f43d  cmp     eax, 2
0x18001f440  jbe     short loc_18001F4BA
0x18001f442  lea     rax, aCalledInBadSta; "Called in bad state"
0x18001f449  mov     dword ptr [rbp+4Fh+var_B0], 1046h
0x18001f450  mov     [rbp+4Fh+var_90], rax
  ... truncated ...
```
