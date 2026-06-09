# CUMRDPConnection::GetSessionIdFromArcInfo(_TS_AUTORECONNECTINFO *,uchar *,ulong,ulong *)

- ea: `0x180049a4c`
- end: `0x180049f72`
- name: `?GetSessionIdFromArcInfo@CUMRDPConnection@@IEAAJPEAU_TS_AUTORECONNECTINFO@@PEAEKPEAK@Z`
- size: `1318`
- prototype: `int(CUMRDPConnection *__hidden this, struct _TS_AUTORECONNECTINFO *, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180045c60`

## callees

- `0x1800014d8`
- `0x1800015f0`
- `0x1800071c0`
- `0x1800071f0`
- `0x180012200`
- `0x180033da0`
- `0x180034970`
- `0x18004677c`
- `0x1800498f0`
- `0x180049a4c`
- `0x18014d010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180049ac7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180049f28`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180049ac7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180049f28`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180049cb7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180049cb7`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180049e5a`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180049e5a`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180049ae1`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180049ae1`

## string_xrefs

- `0x180049c30`: `ProtocolManager->GetAutoReconnectInfo`
- `0x180049e8d`: `m_spProtocolManager is not initialized!`
- `0x180049e11`: `ComputerHMACVerifier failed`

## pseudocode

```c
__int64 __fastcall CUMRDPConnection::GetSessionIdFromArcInfo(
        CUMRDPConnection *this,
        struct _TS_AUTORECONNECTINFO *a2,
        unsigned __int8 *a3,
        int a4,
        unsigned int *a5)
{
  GUID v9; // xmm0
  __int64 v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdi
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  __int64 v17; // rdi
  int ServerAutoReconnectInfo; // ebx
  unsigned int v19; // esi
  char *v20; // rdx
  const char **v21; // rax
  const char *v22; // rax
  struct _FILETIME v23; // rcx
  struct _FILETIME v24; // rax
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  unsigned __int8 *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rdx
  __int64 v34; // r8
  int v36; // [rsp+28h] [rbp-D8h]
  const char **v37; // [rsp+30h] [rbp-D0h]
  const char **v38; // [rsp+40h] [rbp-C0h]
  const char **v39; // [rsp+48h] [rbp-B8h]
  int v40; // [rsp+50h] [rbp-B0h] BYREF
  char *v41; // [rsp+58h] [rbp-A8h] BYREF
  const char *v42; // [rsp+60h] [rbp-A0h] BYREF
  const char *v43; // [rsp+68h] [rbp-98h] BYREF
  const char *v44; // [rsp+70h] [rbp-90h] BYREF
  const char *v45; // [rsp+78h] [rbp-88h] BYREF
  __int64 v46; // [rsp+80h] [rbp-80h] BYREF
  __int64 v47; // [rsp+88h] [rbp-78h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+90h] [rbp-70h] BYREF
  GUID ActivityId; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int8 v50[2]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int8 v51[134]; // [rsp+B2h] [rbp-4Eh] BYREF
  struct _FILETIME v52; // [rsp+138h] [rbp+38h]
  __int64 v53; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int8 Source1[16]; // [rsp+150h] [rbp+50h] BYREF

  v52 = 0;
  v53 = 0;
  memset_0(v50, 0, 0x82u);
  v9 = *(GUID *)((char *)this + 808);
  v10 = 0;
  v47 = 0;
  v46 = 0;
  ActivityId = v9;
  EventActivityIdControl(4u, &ActivityId);
  v41 = (char *)this + 152;
  if ( *((_DWORD *)this + 40) )
    PAL_System_CritSecEnter(*((_QWORD *)this + 19), v11, v12);
  if ( *((_QWORD *)this + 79) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v47, v11, v12);
    v10 = *((_QWORD *)this + 79);
    v47 = v10;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v47);
  }
  if ( *((_QWORD *)this + 80) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v46, v11, v12);
    v13 = *((_QWORD *)this + 80);
    v46 = v13;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v46);
  }
  else
  {
    v13 = 0;
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v41);
  if ( v13 )
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v13 + 80LL))(v13, L"GetSessionIdFromArcInfo");
  v17 = 16;
  if ( *(_DWORD *)((char *)a2 + 2) < 0x1Cu )
  {
    ServerAutoReconnectInfo = -2147024809;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v40 = 4956;
      v45 = "GetSessionIdFromArcInfo";
      LODWORD(v41) = -2147024809;
      v42 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v43 = "GetSessionFromArcInfo ARC length invalid bailing out";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v14,
        (unsigned int)&dword_180194BD4,
        v15,
        v16,
        (__int64)&v43,
        (__int64)&v41,
        (__int64)&v42,
        (__int64)&v40,
        (__int64)&v45);
    }
    goto LABEL_37;
  }
  if ( !v10 )
  {
    ServerAutoReconnectInfo = -2147019873;
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_37;
    v22 = "m_spProtocolManager is not initialized!";
    LODWORD(v41) = 4970;
    v20 = (char *)word_180194B32;
LABEL_35:
    v44 = v22;
    v43 = "GetSessionIdFromArcInfo";
    v42 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    v45 = "Error HResult failed";
    v39 = &v44;
    v38 = &v43;
    v37 = &v42;
    v21 = &v45;
    goto LABEL_36;
  }
  v19 = *(_DWORD *)((char *)a2 + 10);
  ServerAutoReconnectInfo = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int8 *))(*(_QWORD *)(v10 + 8) + 24LL))(
                              v10 + 8,
                              v19,
                              v50);
  if ( ServerAutoReconnectInfo < 0 )
  {
    v14 = dword_1801B76C8;
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_37;
    LODWORD(v41) = 4966;
    v43 = "ProtocolManager->GetAutoReconnectInfo";
    v20 = byte_180194B83;
    v42 = "GetSessionIdFromArcInfo";
    v45 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    v44 = "Error HResult failed";
    v39 = &v43;
    v38 = &v42;
    v37 = &v45;
    v21 = &v44;
LABEL_36:
    v40 = ServerAutoReconnectInfo;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v14,
      (_DWORD)v20,
      v15,
      v16,
      (__int64)v21,
      (__int64)&v40,
      (__int64)v37,
      (__int64)&v41,
      (__int64)v38,
      (__int64)v39);
    goto LABEL_37;
  }
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( v53 )
  {
    ServerAutoReconnectInfo = CUMRDPConnection::GetServerAutoReconnectInfo(
                                (CUMRDPConnection *)((v53 - 56) & -(__int64)(v53 != 0)),
                                v50,
                                0x82u);
    if ( ServerAutoReconnectInfo < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_37;
      v22 = "GetServerAutoReconnect";
      LODWORD(v41) = 4981;
      v20 = byte_180194AE1;
      goto LABEL_35;
    }
    v23 = SystemTimeAsFileTime;
    v24 = SystemTimeAsFileTime;
    v52 = SystemTimeAsFileTime;
  }
  else
  {
    v24 = v52;
    v23 = SystemTimeAsFileTime;
  }
  if ( *(unsigned __int64 *)&v23 <= *(_QWORD *)&v24 + 36000000000LL )
  {
    if ( (unsigned int)ComputeHMACVerifier(v51, 1640261632, a3, a4, Source1, v36) )
    {
      if ( RtlCompareMemory(Source1, (char *)a2 + 14, 0x10u) == 16 )
      {
        ServerAutoReconnectInfo = 0;
        *a5 = v19;
      }
      else
      {
        ServerAutoReconnectInfo = -2147024891;
      }
    }
    else
    {
      ServerAutoReconnectInfo = -2147024891;
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        LODWORD(v41) = 5007;
        v44 = "GetSessionIdFromArcInfo";
        v40 = -2147024891;
        v43 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
        v42 = "ComputerHMACVerifier failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v25,
          (unsigned int)&byte_180194A4F,
          v26,
          v27,
          (__int64)&v42,
          (__int64)&v40,
          (__int64)&v43,
          (__int64)&v41,
          (__int64)&v44);
      }
    }
  }
  else
  {
    ServerAutoReconnectInfo = -2147024891;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v41) = 4992;
      v44 = "GetSessionIdFromArcInfo";
      v40 = -2147024891;
      v43 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v42 = "Autoreconnect cookie expired";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v23.dwLowDateTime,
        (unsigned int)qword_180194A98,
        v15,
        v16,
        (__int64)&v42,
        (__int64)&v40,
        (__int64)&v43,
        (__int64)&v41,
        (__int64)&v44);
    }
  }
LABEL_37:
  v28 = Source1;
  do
  {
    *v28++ = 0;
    --v17;
  }
  while ( v17 );
  EventActivityIdControl(2u, &ActivityId);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v46, v29, v30);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v47, v31, v32);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v53, v33, v34);
  return (unsigned int)ServerAutoReconnectInfo;
}

```

## disassembly

```asm
0x180049a4c  mov     [rsp-8+arg_0], rbx
0x180049a51  push    rbp
0x180049a52  push    rsi
0x180049a53  push    rdi
0x180049a54  push    r12
0x180049a56  push    r13
0x180049a58  push    r14
0x180049a5a  push    r15
0x180049a5c  lea     rbp, [rsp-70h]
0x180049a61  sub     rsp, 170h
0x180049a68  mov     rax, cs:__security_cookie
0x180049a6f  xor     rax, rsp
0x180049a72  mov     [rbp+0A0h+var_40], rax
0x180049a76  mov     r15, [rbp+0A0h+arg_20]
0x180049a7d  mov     r12, r8
0x180049a80  mov     r14, rdx
0x180049a83  mov     [rbp+0A0h+var_68], 0
0x180049a8b  mov     rdi, rcx
0x180049a8e  mov     [rbp+0A0h+var_60], 0
0x180049a96  xor     edx, edx; Val
0x180049a98  lea     rcx, [rbp+0A0h+var_F0]; void *
0x180049a9c  mov     r8d, 82h; Size
0x180049aa2  mov     r13d, r9d
0x180049aa5  call    memset_0
0x180049aaa  movups  xmm0, xmmword ptr [rdi+328h]
0x180049ab1  xor     ebx, ebx
0x180049ab3  lea     rdx, [rbp+0A0h+ActivityId]; ActivityId
0x180049ab7  mov     [rbp+0A0h+var_118], rbx
0x180049abb  mov     [rbp+0A0h+var_120], rbx
0x180049abf  movdqu  xmmword ptr [rbp+0A0h+ActivityId.Data1], xmm0
0x180049ac4  lea     ecx, [rbx+4]; ControlCode
0x180049ac7  call    cs:__imp_EventActivityIdControl
0x180049acd  lea     rcx, [rdi+98h]
0x180049ad4  mov     [rsp+1A0h+var_148], rcx
0x180049ad9  cmp     [rcx+8], ebx
0x180049adc  jz      short loc_180049AE7
0x180049ade  mov     rcx, [rcx]
0x180049ae1  call    cs:__imp_PAL_System_CritSecEnter
0x180049ae7  cmp     [rdi+278h], rbx
0x180049aee  jz      short loc_180049B0D
0x180049af0  lea     rcx, [rbp+0A0h+var_118]
0x180049af4  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x180049af9  mov     rbx, [rdi+278h]
0x180049b00  lea     rcx, [rbp+0A0h+var_118]
0x180049b04  mov     [rbp+0A0h+var_118], rbx
0x180049b08  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x180049b0d  cmp     qword ptr [rdi+280h], 0
0x180049b15  jnz     short loc_180049B1B
0x180049b17  xor     edi, edi
0x180049b19  jmp     short loc_180049B38
0x180049b1b  lea     rcx, [rbp+0A0h+var_120]
0x180049b1f  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x180049b24  mov     rdi, [rdi+280h]
0x180049b2b  lea     rcx, [rbp+0A0h+var_120]
0x180049b2f  mov     [rbp+0A0h+var_120], rdi
0x180049b33  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x180049b38  lea     rcx, [rsp+1A0h+var_148]; this
0x180049b3d  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180049b42  test    rdi, rdi
0x180049b45  jz      short loc_180049B5D
0x180049b47  mov     rax, [rdi]
0x180049b4a  lea     rdx, aGetsessionidfr_0; "GetSessionIdFromArcInfo"
0x180049b51  mov     rcx, rdi
0x180049b54  mov     rax, [rax+50h]
0x180049b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b5d  cmp     dword ptr [r14+2], 1Ch
0x180049b62  mov     edi, 10h
0x180049b67  jnb     loc_180049BF4
0x180049b6d  mov     eax, cs:dword_1801B76C8
0x180049b73  mov     ebx, 80070057h
0x180049b78  cmp     eax, 2
0x180049b7b  jbe     loc_180049F11
0x180049b81  lea     rax, aGetsessionidfr; "GetSessionIdFromArcInfo"
0x180049b88  mov     [rsp+1A0h+var_150], 135Ch
0x180049b90  mov     [rsp+1A0h+var_128], rax
0x180049b95  lea     rdx, dword_180194BD4
0x180049b9c  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180049ba3  mov     dword ptr [rsp+1A0h+var_148], ebx
0x180049ba7  mov     [rsp+1A0h+var_140], rax
0x180049bac  lea     rax, aGetsessionfrom; "GetSessionFromArcInfo ARC length invali"...
0x180049bb3  mov     [rsp+1A0h+var_138], rax
0x180049bb8  lea     rax, [rsp+1A0h+var_128]
0x180049bbd  mov     [rsp+1A0h+var_160], rax
0x180049bc2  lea     rax, [rsp+1A0h+var_150]
0x180049bc7  mov     [rsp+1A0h+var_168], rax
0x180049bcc  lea     rax, [rsp+1A0h+var_140]
0x180049bd1  mov     [rsp+1A0h+var_170], rax
0x180049bd6  lea     rax, [rsp+1A0h+var_148]
0x180049bdb  mov     [rsp+1A0h+var_178], rax
0x180049be0  lea     rax, [rsp+1A0h+var_138]
0x180049be5  mov     [rsp+1A0h+var_180], rax
0x180049bea  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180049bef  jmp     loc_180049F11
0x180049bf4  test    rbx, rbx
0x180049bf7  jz      loc_180049E79
0x180049bfd  mov     esi, [r14+0Ah]
0x180049c01  lea     rcx, [rbx+8]
0x180049c05  mov     rax, [rcx]
0x180049c08  lea     r8, [rbp+0A0h+var_F0]
0x180049c0c  mov     edx, esi
0x180049c0e  mov     rax, [rax+18h]
0x180049c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c17  mov     ebx, eax
0x180049c19  test    eax, eax
0x180049c1b  jns     loc_180049CAB
0x180049c21  mov     ecx, cs:dword_1801B76C8
0x180049c27  cmp     ecx, 2
0x180049c2a  jbe     loc_180049F11
0x180049c30  lea     rax, aProtocolmanage; "ProtocolManager->GetAutoReconnectInfo"
0x180049c37  mov     dword ptr [rsp+1A0h+var_148], 1366h
0x180049c3f  mov     [rsp+1A0h+var_138], rax
0x180049c44  lea     rdx, byte_180194B83
0x180049c4b  lea     rax, aGetsessionidfr; "GetSessionIdFromArcInfo"
0x180049c52  mov     [rsp+1A0h+var_140], rax
0x180049c57  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180049c5e  mov     [rsp+1A0h+var_128], rax
0x180049c63  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180049c6a  mov     [rsp+1A0h+var_130], rax
0x180049c6f  lea     rax, [rsp+1A0h+var_138]
0x180049c74  mov     [rsp+1A0h+var_158], rax
0x180049c79  lea     rax, [rsp+1A0h+var_140]
0x180049c7e  mov     [rsp+1A0h+var_160], rax
0x180049c83  lea     rax, [rsp+1A0h+var_148]
0x180049c88  mov     [rsp+1A0h+var_168], rax
0x180049c8d  lea     rax, [rsp+1A0h+var_128]
0x180049c92  mov     [rsp+1A0h+var_170], rax
0x180049c97  lea     rax, [rsp+1A0h+var_150]
0x180049c9c  mov     [rsp+1A0h+var_178], rax
0x180049ca1  lea     rax, [rsp+1A0h+var_130]
0x180049ca6  jmp     loc_180049F03
0x180049cab  lea     rcx, [rbp+0A0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180049caf  mov     qword ptr [rbp+0A0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180049cb7  call    cs:__imp_GetSystemTimeAsFileTime
0x180049cbd  mov     rcx, [rbp+0A0h+var_60]
0x180049cc1  test    rcx, rcx
0x180049cc4  jz      short loc_180049D1F
0x180049cc6  lea     rax, [rcx-38h]
0x180049cca  mov     r8d, 82h; unsigned int
0x180049cd0  neg     rcx
0x180049cd3  lea     rdx, [rbp+0A0h+var_F0]; unsigned __int8 *
0x180049cd7  sbb     rcx, rcx
0x180049cda  and     rcx, rax; this
0x180049cdd  call    ?GetServerAutoReconnectInfo@CUMRDPConnection@@UEAAJPEAEK@Z; CUMRDPConnection::GetServerAutoReconnectInfo(uchar *,ulong)
0x180049ce2  mov     ebx, eax
0x180049ce4  test    eax, eax
0x180049ce6  jns     short loc_180049D12
0x180049ce8  mov     eax, cs:dword_1801B76C8
0x180049cee  cmp     eax, 2
0x180049cf1  jbe     loc_180049F11
0x180049cf7  lea     rax, aGetserverautor; "GetServerAutoReconnect"
0x180049cfe  mov     dword ptr [rsp+1A0h+var_148], 1375h
0x180049d06  lea     rdx, byte_180194AE1
0x180049d0d  jmp     loc_180049EA3
0x180049d12  mov     rcx, qword ptr [rbp+0A0h+SystemTimeAsFileTime.dwLowDateTime]
0x180049d16  mov     rax, rcx
0x180049d19  mov     [rbp+0A0h+var_68], rcx
0x180049d1d  jmp     short loc_180049D27
0x180049d1f  mov     rax, [rbp+0A0h+var_68]
0x180049d23  mov     rcx, qword ptr [rbp+0A0h+SystemTimeAsFileTime.dwLowDateTime]
0x180049d27  mov     rdx, 861C46800h; int
0x180049d31  add     rax, rdx
0x180049d34  cmp     rcx, rax
0x180049d37  jbe     short loc_180049DB6
0x180049d39  mov     eax, cs:dword_1801B76C8
0x180049d3f  mov     ebx, 80070005h
0x180049d44  cmp     eax, 2
0x180049d47  jbe     loc_180049F11
0x180049d4d  lea     rax, aGetsessionidfr; "GetSessionIdFromArcInfo"
0x180049d54  mov     dword ptr [rsp+1A0h+var_148], 1380h
0x180049d5c  mov     [rsp+1A0h+var_130], rax
0x180049d61  lea     rdx, qword_180194A98
0x180049d68  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180049d6f  mov     [rsp+1A0h+var_150], ebx
0x180049d73  mov     [rsp+1A0h+var_138], rax
0x180049d78  lea     rax, aAutoreconnectC; "Autoreconnect cookie expired"
0x180049d7f  mov     [rsp+1A0h+var_140], rax
0x180049d84  lea     rax, [rsp+1A0h+var_130]
0x180049d89  mov     [rsp+1A0h+var_160], rax
0x180049d8e  lea     rax, [rsp+1A0h+var_148]
0x180049d93  mov     [rsp+1A0h+var_168], rax
0x180049d98  lea     rax, [rsp+1A0h+var_138]
0x180049d9d  mov     [rsp+1A0h+var_170], rax
0x180049da2  lea     rax, [rsp+1A0h+var_150]
0x180049da7  mov     [rsp+1A0h+var_178], rax
0x180049dac  lea     rax, [rsp+1A0h+var_140]
0x180049db1  jmp     loc_180049BE5
0x180049db6  lea     rax, [rbp+0A0h+Source1]
0x180049dba  mov     r9d, r13d; int
0x180049dbd  mov     r8, r12; unsigned __int8 *
0x180049dc0  mov     [rsp+1A0h+var_180], rax; unsigned __int8 *
0x180049dc5  lea     rcx, [rbp+0A0h+var_EE]; unsigned __int8 *
0x180049dc9  call    ?ComputeHMACVerifier@@YAHPEAEJ0J0J@Z; ComputeHMACVerifier(uchar *,long,uchar *,long,uchar *,long)
0x180049dce  test    eax, eax
0x180049dd0  jnz     short loc_180049E4F
0x180049dd2  mov     eax, cs:dword_1801B76C8
0x180049dd8  mov     ebx, 80070005h
0x180049ddd  cmp     eax, 2
0x180049de0  jbe     loc_180049F11
0x180049de6  lea     rax, aGetsessionidfr; "GetSessionIdFromArcInfo"
0x180049ded  mov     dword ptr [rsp+1A0h+var_148], 138Fh
0x180049df5  mov     [rsp+1A0h+var_130], rax
0x180049dfa  lea     rdx, byte_180194A4F
0x180049e01  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180049e08  mov     [rsp+1A0h+var_150], ebx
0x180049e0c  mov     [rsp+1A0h+var_138], rax
0x180049e11  lea     rax, aComputerhmacve; "ComputerHMACVerifier failed"
0x180049e18  mov     [rsp+1A0h+var_140], rax
0x180049e1d  lea     rax, [rsp+1A0h+var_130]
0x180049e22  mov     [rsp+1A0h+var_160], rax
0x180049e27  lea     rax, [rsp+1A0h+var_148]
0x180049e2c  mov     [rsp+1A0h+var_168], rax
0x180049e31  lea     rax, [rsp+1A0h+var_138]
0x180049e36  mov     [rsp+1A0h+var_170], rax
0x180049e3b  lea     rax, [rsp+1A0h+var_150]
0x180049e40  mov     [rsp+1A0h+var_178], rax
0x180049e45  lea     rax, [rsp+1A0h+var_140]
0x180049e4a  jmp     loc_180049BE5
0x180049e4f  lea     rdx, [r14+0Eh]; Source2
0x180049e53  mov     r8, rdi; Length
0x180049e56  lea     rcx, [rbp+0A0h+Source1]; Source1
0x180049e5a  call    cs:__imp_RtlCompareMemory
0x180049e60  cmp     rax, rdi
0x180049e63  jz      short loc_180049E6F
0x180049e65  mov     ebx, 80070005h
0x180049e6a  jmp     loc_180049F11
0x180049e6f  xor     ebx, ebx
0x180049e71  mov     [r15], esi
0x180049e74  jmp     loc_180049F11
0x180049e79  mov     eax, cs:dword_1801B76C8
0x180049e7f  mov     ebx, 8007139Fh
0x180049e84  cmp     eax, 2
0x180049e87  jbe     loc_180049F11
0x180049e8d  lea     rax, aMSpprotocolman; "m_spProtocolManager is not initialized!"
0x180049e94  mov     dword ptr [rsp+1A0h+var_148], 136Ah
0x180049e9c  lea     rdx, word_180194B32
0x180049ea3  mov     [rsp+1A0h+var_130], rax
0x180049ea8  lea     rax, aGetsessionidfr; "GetSessionIdFromArcInfo"
0x180049eaf  mov     [rsp+1A0h+var_138], rax
0x180049eb4  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180049ebb  mov     [rsp+1A0h+var_140], rax
0x180049ec0  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180049ec7  mov     [rsp+1A0h+var_128], rax
0x180049ecc  lea     rax, [rsp+1A0h+var_130]
0x180049ed1  mov     [rsp+1A0h+var_158], rax
0x180049ed6  lea     rax, [rsp+1A0h+var_138]
0x180049edb  mov     [rsp+1A0h+var_160], rax
0x180049ee0  lea     rax, [rsp+1A0h+var_148]
0x180049ee5  mov     [rsp+1A0h+var_168], rax
0x180049eea  lea     rax, [rsp+1A0h+var_140]
0x180049eef  mov     [rsp+1A0h+var_170], rax
0x180049ef4  lea     rax, [rsp+1A0h+var_150]
0x180049ef9  mov     [rsp+1A0h+var_178], rax
0x180049efe  lea     rax, [rsp+1A0h+var_128]
0x180049f03  mov     [rsp+1A0h+var_180], rax
0x180049f08  mov     [rsp+1A0h+var_150], ebx
0x180049f0c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180049f11  lea     rax, [rbp+0A0h+Source1]
0x180049f15  mov     byte ptr [rax], 0
0x180049f18  inc     rax
0x180049f1b  sub     rdi, 1
0x180049f1f  jnz     short loc_180049F15
0x180049f21  lea     rdx, [rbp+0A0h+ActivityId]; ActivityId
0x180049f25  lea     ecx, [rdi+2]; ControlCode
0x180049f28  call    cs:__imp_EventActivityIdControl
0x180049f2e  lea     rcx, [rbp+0A0h+var_120]
0x180049f32  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x180049f37  lea     rcx, [rbp+0A0h+var_118]
0x180049f3b  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x180049f40  lea     rcx, [rbp+0A0h+var_60]
0x180049f44  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x180049f49  mov     eax, ebx
0x180049f4b  mov     rcx, [rbp+0A0h+var_40]
0x180049f4f  xor     rcx, rsp; StackCookie
0x180049f52  call    __security_check_cookie
0x180049f57  mov     rbx, [rsp+1A0h+arg_0]
0x180049f5f  add     rsp, 170h
0x180049f66  pop     r15
0x180049f68  pop     r14
0x180049f6a  pop     r13
0x180049f6c  pop     r12
0x180049f6e  pop     rdi
0x180049f6f  pop     rsi
0x180049f70  pop     rbp
0x180049f71  retn
```
