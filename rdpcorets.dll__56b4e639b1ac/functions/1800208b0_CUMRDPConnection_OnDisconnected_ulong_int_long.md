# CUMRDPConnection::OnDisconnected(ulong,int,long)

- ea: `0x1800208b0`
- end: `0x180020d65`
- name: `?OnDisconnected@CUMRDPConnection@@UEAAXKHJ@Z`
- size: `1205`
- prototype: `void(CUMRDPConnection *__hidden this, unsigned int, int, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180002634`
- `0x180002fcc`
- `0x1800071c0`
- `0x1800071f0`
- `0x18000f784`
- `0x180012200`
- `0x180012228`
- `0x18001e49c`
- `0x1800208b0`
- `0x1800231f0`
- `0x180026158`
- `0x180033da0`
- `0x1800463c4`
- `0x180048554`
- `0x18004c178`
- `0x18014d010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002090e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180020d26`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002090e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180020d26`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180020925`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180020925`
- `RDPBASE!RDPServerStackDiagnostics_LogFailure` at `0x180020aa2`
- `RDPBASE!RDPServerStackDiagnostics_LogFailure` at `0x180020aa2`
- `RDPBASE!RDPServerStackDiagnostics_GetSymbolicNameFromCode` at `0x180020ac0`
- `RDPBASE!RDPServerStackDiagnostics_GetSymbolicNameFromCode` at `0x180020ac0`

## string_xrefs

- `0x180020bdb`: `ProtocolProvider`

## pseudocode

```c
void __fastcall CUMRDPConnection::OnDisconnected(CUMRDPConnection *this, __int64 a2, unsigned int a3, int a4)
{
  GUID v4; // xmm0
  __int64 v6; // rbx
  int v7; // r15d
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rsi
  const wchar_t *v12; // rdx
  int DisconnectReasonAndHresult; // eax
  int v14; // ecx
  __int64 v15; // r8
  unsigned int v16; // r9d
  int v17; // r13d
  unsigned int v18; // esi
  unsigned int v19; // r14d
  int v20; // r9d
  unsigned int v21; // esi
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  unsigned int v25; // eax
  __int128 v26; // xmm0
  int v27; // eax
  int v28; // r8d
  int v29; // r9d
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // r8
  unsigned int v34; // [rsp+20h] [rbp-B9h]
  int v35; // [rsp+70h] [rbp-69h] BYREF
  int v36; // [rsp+74h] [rbp-65h] BYREF
  unsigned int v37; // [rsp+78h] [rbp-61h] BYREF
  unsigned int v38; // [rsp+7Ch] [rbp-5Dh]
  char *v39; // [rsp+80h] [rbp-59h] BYREF
  const char *v40; // [rsp+88h] [rbp-51h] BYREF
  const char *v41; // [rsp+90h] [rbp-49h] BYREF
  __int64 v42; // [rsp+98h] [rbp-41h] BYREF
  __int64 v43; // [rsp+A0h] [rbp-39h] BYREF
  const char *v44; // [rsp+A8h] [rbp-31h] BYREF
  _QWORD v45[2]; // [rsp+B0h] [rbp-29h] BYREF
  __int128 v46; // [rsp+C0h] [rbp-19h] BYREF
  GUID ActivityId; // [rsp+D0h] [rbp-9h] BYREF
  __int128 v48; // [rsp+E0h] [rbp+7h] BYREF

  v4 = *(GUID *)((char *)this + 728);
  v38 = a4;
  v35 = a3;
  v6 = 0;
  v42 = 0;
  v43 = 0;
  v7 = a4;
  ActivityId = v4;
  EventActivityIdControl(4u, &ActivityId);
  v39 = (char *)this + 72;
  if ( *((_DWORD *)this + 20) )
    PAL_System_CritSecEnter(*((_QWORD *)this + 9), v9, v10);
  if ( *((_QWORD *)this + 20) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v43, v9, v10);
    v6 = *((_QWORD *)this + 20);
    v43 = v6;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v43);
  }
  v11 = 0;
  if ( *((_QWORD *)this + 70) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v42, v9, v10);
    v11 = *((_QWORD *)this + 70);
    v42 = v11;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v42);
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v39);
  if ( v11 )
  {
    v12 = L"OnDisconnected(server initiated)";
    if ( !a3 )
      v12 = L"OnDisconnected";
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v11 + 80LL))(v11, v12);
  }
  v36 = 0;
  v37 = 0;
  DisconnectReasonAndHresult = CUMRDPConnection::GetDisconnectReasonAndHresult(
                                 (CUMRDPConnection *)((char *)this - 80),
                                 &v36,
                                 &v37);
  v17 = v36;
  v18 = DisconnectReasonAndHresult;
  if ( !v36 )
    v17 = v7;
  if ( DisconnectReasonAndHresult && DisconnectReasonAndHresult != 4410 && DisconnectReasonAndHresult != 4407 )
  {
    v46 = *(_OWORD *)((char *)this + 728);
    RDPStackTraceLogging::LogRdpDisconnectReason(
      (RDPStackTraceLogging *)&v46,
      (struct _GUID *)a3,
      DisconnectReasonAndHresult,
      v16);
  }
  if ( !*((_DWORD *)this + 163) )
  {
    *((_DWORD *)this + 163) = 1;
    if ( v7 < 0 )
    {
      v19 = v18;
      if ( v18 == -1 )
      {
        v21 = v38;
        if ( *((_DWORD *)this + 190) )
        {
          v46 = *(_OWORD *)((char *)this + 728);
          RDPServerStackDiagnostics_LogFailure(
            &v46,
            777,
            2,
            v38,
            "Connection failed, disconnect reason is not available. See HRESULT code for details.",
            0,
            1,
            7);
        }
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          v44 = "Connection failed, disconnect reason is not available. See HRESULT code for details.";
          v35 = 2;
          v45[0] = RDPServerStackDiagnostics_GetSymbolicNameFromCode(2, 0, v15);
          v41 = "OnDisconnected";
          v40 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
          *(_QWORD *)&v46 = "RDP OnDisconnected RDPServerStackDiagnostics_LogFailure";
          v37 = 777;
          v36 = 1594;
          LODWORD(v39) = v21;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v22,
            (unsigned int)byte_180197009,
            v23,
            v24,
            (__int64)&v46,
            (__int64)&v39,
            (__int64)&v40,
            (__int64)&v36,
            (__int64)&v41,
            (__int64)&v37,
            (__int64)&v35,
            (__int64)v45,
            (__int64)&v44);
        }
        goto LABEL_32;
      }
      if ( v18 - 12 <= 1 )
      {
        v25 = CUMRDPConnection::CheckForUserDisconnectBeforeLogon((CUMRDPConnection *)((char *)this - 80));
        if ( v25 != -1 )
          v19 = v25;
      }
      v20 = v17;
      v34 = v37;
    }
    else
    {
      v19 = 0;
      v34 = 0;
      if ( v18 != -1 )
        v19 = v18;
      v20 = 0;
    }
    CUMRDPConnection::LogDisconnectDiagnosticsEvent((CUMRDPConnection *)((char *)this - 80), v19, v35, v20, v34);
LABEL_32:
    if ( (unsigned int)dword_1801B76C8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801B76C8, 0x470000000000LL) )
    {
      v26 = *(_OWORD *)((char *)this + 728);
      v35 = *((_DWORD *)this + 158);
      *(_QWORD *)&v46 = &v48;
      v40 = "ProtocolProvider";
      v41 = "Stack";
      v44 = "Checkpoint";
      LODWORD(v39) = v19;
      v48 = v26;
      v45[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v14,
        (unsigned int)&dword_180196F94,
        v15,
        v16,
        (__int64)&v44,
        (__int64)v45,
        (__int64)&v41,
        (__int64)&v40,
        (__int64)&v46,
        (__int64)&v35,
        (__int64)&v39);
    }
    v7 = v38;
  }
  if ( v6 )
  {
    v27 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v6 + 32LL))(v6, (unsigned int)v7, 0);
    if ( v27 < 0 && (unsigned int)dword_1801B76C8 > 3 )
    {
      LODWORD(v39) = v27;
      *(_QWORD *)&v46 = "OnDisconnected";
      v40 = "Failed to disconnect attendee";
      v41 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        dword_1801B76C8,
        (unsigned int)byte_180196F55,
        v28,
        v29,
        (__int64)&v41,
        (__int64)&v40,
        (__int64)&v39,
        (__int64)&v46);
    }
  }
  else if ( (unsigned int)dword_1801B76C8 > 4 )
  {
    *(_QWORD *)&v46 = (char *)this - 80;
    v40 = "UMRDP::OnDisconnected:  Received attendee disconnect after close";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      v14,
      (unsigned int)byte_180196F29,
      v15,
      v16,
      (__int64)&v40,
      (__int64)&v46);
  }
  CUMRDPConnection::TerminateInstance((CUMRDPConnection *)((char *)this - 32));
  EventActivityIdControl(2u, &ActivityId);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v42, v30, v31);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v43, v32, v33);
}

```

## disassembly

```asm
0x1800208b0  mov     [rsp-8+arg_8], rbx
0x1800208b5  push    rbp
0x1800208b6  push    rsi
0x1800208b7  push    rdi
0x1800208b8  push    r12
0x1800208ba  push    r13
0x1800208bc  push    r14
0x1800208be  push    r15
0x1800208c0  lea     rbp, [rsp-27h]
0x1800208c5  sub     rsp, 100h
0x1800208cc  mov     rax, cs:__security_cookie
0x1800208d3  xor     rax, rsp
0x1800208d6  mov     [rbp+57h+var_40], rax
0x1800208da  movups  xmm0, xmmword ptr [rcx+2D8h]
0x1800208e1  xor     r12d, r12d
0x1800208e4  mov     [rbp+57h+var_B4], r9d
0x1800208e8  mov     rdi, rcx
0x1800208eb  mov     [rbp+57h+var_C0], r8d
0x1800208ef  mov     ebx, r12d
0x1800208f2  mov     [rbp+57h+var_98], r12
0x1800208f6  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x1800208fa  mov     [rbp+57h+var_90], rbx
0x1800208fe  lea     ecx, [r12+4]; ControlCode
0x180020903  mov     r15d, r9d
0x180020906  mov     r14d, r8d
0x180020909  movdqu  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x18002090e  call    cs:__imp_EventActivityIdControl
0x180020914  lea     rcx, [rdi+48h]
0x180020918  mov     [rbp+57h+var_B0], rcx
0x18002091c  cmp     [rcx+8], r12d
0x180020920  jz      short loc_18002092B
0x180020922  mov     rcx, [rcx]
0x180020925  call    cs:__imp_PAL_System_CritSecEnter
0x18002092b  cmp     [rdi+0A0h], r12
0x180020932  jz      short loc_180020951
0x180020934  lea     rcx, [rbp+57h+var_90]
0x180020938  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18002093d  mov     rbx, [rdi+0A0h]
0x180020944  lea     rcx, [rbp+57h+var_90]
0x180020948  mov     [rbp+57h+var_90], rbx
0x18002094c  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x180020951  mov     rsi, r12
0x180020954  cmp     [rdi+230h], r12
0x18002095b  jz      short loc_18002097A
0x18002095d  lea     rcx, [rbp+57h+var_98]
0x180020961  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x180020966  mov     rsi, [rdi+230h]
0x18002096d  lea     rcx, [rbp+57h+var_98]
0x180020971  mov     [rbp+57h+var_98], rsi
0x180020975  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18002097a  lea     rcx, [rbp+57h+var_B0]; this
0x18002097e  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180020983  test    rsi, rsi
0x180020986  jz      short loc_1800209AC
0x180020988  mov     rax, [rsi]
0x18002098b  lea     rcx, aOndisconnected_0; "OnDisconnected"
0x180020992  test    r14d, r14d
0x180020995  lea     rdx, aOndisconnected_1; "OnDisconnected(server initiated)"
0x18002099c  cmovz   rdx, rcx
0x1800209a0  mov     rcx, rsi
0x1800209a3  mov     rax, [rax+50h]
0x1800209a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209ac  mov     [rbp+57h+var_BC], r12d
0x1800209b0  lea     r8, [rbp+57h+var_B8]; unsigned int *
0x1800209b4  mov     [rbp+57h+var_B8], r12d
0x1800209b8  lea     rdx, [rbp+57h+var_BC]; int *
0x1800209bc  lea     r12, [rdi-50h]
0x1800209c0  mov     rcx, r12; this
0x1800209c3  call    ?GetDisconnectReasonAndHresult@CUMRDPConnection@@IEAAKPEAJPEAK@Z; CUMRDPConnection::GetDisconnectReasonAndHresult(long *,ulong *)
0x1800209c8  mov     r13d, [rbp+57h+var_BC]
0x1800209cc  mov     esi, eax
0x1800209ce  test    r13d, r13d
0x1800209d1  cmovz   r13d, r15d
0x1800209d5  test    eax, eax
0x1800209d7  jz      short loc_180020A02
0x1800209d9  cmp     eax, 113Ah
0x1800209de  jz      short loc_180020A02
0x1800209e0  cmp     eax, 1137h
0x1800209e5  jz      short loc_180020A02
0x1800209e7  movups  xmm0, xmmword ptr [rdi+2D8h]
0x1800209ee  mov     r8d, eax; int
0x1800209f1  lea     rcx, [rbp+57h+var_70]; this
0x1800209f5  mov     edx, r14d; struct _GUID
0x1800209f8  movdqu  [rbp+57h+var_70], xmm0
0x1800209fd  call    ?LogRdpDisconnectReason@RDPStackTraceLogging@@YAXU_GUID@@HK@Z; RDPStackTraceLogging::LogRdpDisconnectReason(_GUID,int,ulong)
0x180020a02  cmp     dword ptr [rdi+28Ch], 0
0x180020a09  lea     r14, aOndisconnected; "OnDisconnected"
0x180020a10  jnz     loc_180020C5C
0x180020a16  mov     dword ptr [rdi+28Ch], 1
0x180020a20  test    r15d, r15d
0x180020a23  js      short loc_180020A43
0x180020a25  xor     r14d, r14d
0x180020a28  mov     [rsp+130h+var_110], 0
0x180020a30  or      r15d, 0FFFFFFFFh
0x180020a34  cmp     esi, r15d
0x180020a37  cmovnz  r14d, esi
0x180020a3b  xor     r9d, r9d
0x180020a3e  jmp     loc_180020B80
0x180020a43  or      r15d, 0FFFFFFFFh
0x180020a47  mov     r14d, esi
0x180020a4a  cmp     esi, r15d
0x180020a4d  jnz     loc_180020B5F
0x180020a53  cmp     dword ptr [rdi+2F8h], 0
0x180020a5a  lea     r13, aConnectionFail_43; "Connection failed, disconnect reason is"...
0x180020a61  mov     esi, [rbp+57h+var_B4]
0x180020a64  mov     r15d, 309h
0x180020a6a  jz      short loc_180020AA8
0x180020a6c  movups  xmm0, xmmword ptr [rdi+2D8h]
0x180020a73  mov     dword ptr [rsp+130h+var_F8], 7
0x180020a7b  lea     rcx, [rbp+57h+var_70]
0x180020a7f  mov     byte ptr [rsp+130h+var_100], 1
0x180020a84  mov     r9d, esi
0x180020a87  mov     dword ptr [rsp+130h+var_108], 0
0x180020a8f  mov     r8d, 2
0x180020a95  mov     edx, r15d
0x180020a98  mov     qword ptr [rsp+130h+var_110], r13
0x180020a9d  movdqu  [rbp+57h+var_70], xmm0
0x180020aa2  call    cs:__imp_RDPServerStackDiagnostics_LogFailure
0x180020aa8  mov     eax, cs:dword_1801B76C8
0x180020aae  cmp     eax, 2
0x180020ab1  jbe     loc_180020B8F
0x180020ab7  xor     edx, edx
0x180020ab9  mov     [rbp+57h+var_88], r13
0x180020abd  lea     ecx, [rdx+2]
0x180020ac0  call    cs:__imp_RDPServerStackDiagnostics_GetSymbolicNameFromCode
0x180020ac6  lea     rdx, byte_180197009
0x180020acd  mov     [rbp+57h+var_C0], 2
0x180020ad4  mov     [rbp+57h+var_80], rax
0x180020ad8  lea     rax, aOndisconnected; "OnDisconnected"
0x180020adf  mov     [rbp+57h+var_A0], rax
0x180020ae3  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180020aea  mov     [rbp+57h+var_A8], rax
0x180020aee  lea     rax, aRdpOndisconnec; "RDP OnDisconnected RDPServerStackDiagno"...
0x180020af5  mov     qword ptr [rbp+57h+var_70], rax
0x180020af9  lea     rax, [rbp+57h+var_88]
0x180020afd  mov     [rsp+130h+var_D0], rax
0x180020b02  lea     rax, [rbp+57h+var_80]
0x180020b06  mov     [rsp+130h+var_D8], rax
0x180020b0b  lea     rax, [rbp+57h+var_C0]
0x180020b0f  mov     [rsp+130h+var_E0], rax
0x180020b14  lea     rax, [rbp+57h+var_B8]
0x180020b18  mov     [rsp+130h+var_E8], rax
0x180020b1d  lea     rax, [rbp+57h+var_A0]
0x180020b21  mov     [rsp+130h+var_F0], rax
0x180020b26  lea     rax, [rbp+57h+var_BC]
0x180020b2a  mov     [rsp+130h+var_F8], rax
0x180020b2f  lea     rax, [rbp+57h+var_A8]
0x180020b33  mov     [rsp+130h+var_100], rax
0x180020b38  lea     rax, [rbp+57h+var_B0]
0x180020b3c  mov     [rsp+130h+var_108], rax
0x180020b41  lea     rax, [rbp+57h+var_70]
0x180020b45  mov     qword ptr [rsp+130h+var_110], rax
0x180020b4a  mov     [rbp+57h+var_B8], r15d
0x180020b4e  mov     [rbp+57h+var_BC], 63Ah
0x180020b55  mov     dword ptr [rbp+57h+var_B0], esi
0x180020b58  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180020b5d  jmp     short loc_180020B8F
0x180020b5f  lea     eax, [rsi-0Ch]
0x180020b62  cmp     eax, 1
0x180020b65  ja      short loc_180020B76
0x180020b67  mov     rcx, r12; this
0x180020b6a  call    ?CheckForUserDisconnectBeforeLogon@CUMRDPConnection@@IEAAKXZ; CUMRDPConnection::CheckForUserDisconnectBeforeLogon(void)
0x180020b6f  cmp     eax, r15d
0x180020b72  cmovnz  r14d, eax
0x180020b76  mov     eax, [rbp+57h+var_B8]
0x180020b79  mov     r9d, r13d; int
0x180020b7c  mov     [rsp+130h+var_110], eax; unsigned int
0x180020b80  mov     r8d, [rbp+57h+var_C0]; int
0x180020b84  mov     edx, r14d; unsigned int
0x180020b87  mov     rcx, r12; this
0x180020b8a  call    ?LogDisconnectDiagnosticsEvent@CUMRDPConnection@@IEBAXKHJK@Z; CUMRDPConnection::LogDisconnectDiagnosticsEvent(ulong,int,long,ulong)
0x180020b8f  mov     eax, cs:dword_1801B76C8
0x180020b95  cmp     eax, 4
0x180020b98  jbe     loc_180020C51
0x180020b9e  mov     rdx, 470000000000h
0x180020ba8  lea     rcx, dword_1801B76C8
0x180020baf  call    _tlgKeywordOn
0x180020bb4  test    al, al
0x180020bb6  jz      loc_180020C51
0x180020bbc  mov     eax, [rdi+278h]
0x180020bc2  lea     rdx, dword_180196F94
0x180020bc9  movups  xmm0, xmmword ptr [rdi+2D8h]
0x180020bd0  mov     [rbp+57h+var_C0], eax
0x180020bd3  lea     rax, [rbp+57h+var_50]
0x180020bd7  mov     qword ptr [rbp+57h+var_70], rax
0x180020bdb  lea     rax, aProtocolprovid; "ProtocolProvider"
0x180020be2  mov     [rbp+57h+var_A8], rax
0x180020be6  lea     rax, aStack; "Stack"
0x180020bed  mov     [rbp+57h+var_A0], rax
0x180020bf1  lea     rax, aCheckpoint; "Checkpoint"
0x180020bf8  mov     [rbp+57h+var_88], rax
0x180020bfc  lea     rax, [rbp+57h+var_B0]
0x180020c00  mov     [rsp+130h+var_E0], rax
0x180020c05  lea     rax, [rbp+57h+var_C0]
0x180020c09  mov     [rsp+130h+var_E8], rax
0x180020c0e  lea     rax, [rbp+57h+var_70]
0x180020c12  mov     [rsp+130h+var_F0], rax
0x180020c17  lea     rax, [rbp+57h+var_A8]
0x180020c1b  mov     [rsp+130h+var_F8], rax
0x180020c20  lea     rax, [rbp+57h+var_A0]
0x180020c24  mov     [rsp+130h+var_100], rax
0x180020c29  lea     rax, [rbp+57h+var_80]
0x180020c2d  mov     [rsp+130h+var_108], rax
0x180020c32  lea     rax, [rbp+57h+var_88]
0x180020c36  mov     qword ptr [rsp+130h+var_110], rax
0x180020c3b  mov     dword ptr [rbp+57h+var_B0], r14d
0x180020c3f  movdqu  [rbp+57h+var_50], xmm0
0x180020c44  mov     [rbp+57h+var_80], 1000000h
0x180020c4c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180020c51  mov     r15d, [rbp+57h+var_B4]
0x180020c55  lea     r14, aOndisconnected; "OnDisconnected"
0x180020c5c  test    rbx, rbx
0x180020c5f  jz      short loc_180020CDC
0x180020c61  mov     rax, [rbx]
0x180020c64  xor     r8d, r8d
0x180020c67  mov     edx, r15d
0x180020c6a  mov     rcx, rbx
0x180020c6d  mov     rax, [rax+20h]
0x180020c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c76  test    eax, eax
0x180020c78  jns     loc_180020D14
0x180020c7e  mov     ecx, cs:dword_1801B76C8
0x180020c84  cmp     ecx, 3
0x180020c87  jbe     loc_180020D14
0x180020c8d  mov     dword ptr [rbp+57h+var_B0], eax
0x180020c90  lea     rdx, byte_180196F55
0x180020c97  lea     rax, aFailedToDiscon; "Failed to disconnect attendee"
0x180020c9e  mov     qword ptr [rbp+57h+var_70], r14
0x180020ca2  mov     [rbp+57h+var_A8], rax
0x180020ca6  lea     rax, aHresultFailedB; "HResult failed but continue"
0x180020cad  mov     [rbp+57h+var_A0], rax
0x180020cb1  lea     rax, [rbp+57h+var_70]
0x180020cb5  mov     [rsp+130h+var_F8], rax
0x180020cba  lea     rax, [rbp+57h+var_B0]
0x180020cbe  mov     [rsp+130h+var_100], rax
0x180020cc3  lea     rax, [rbp+57h+var_A8]
0x180020cc7  mov     [rsp+130h+var_108], rax
0x180020ccc  lea     rax, [rbp+57h+var_A0]
0x180020cd0  mov     qword ptr [rsp+130h+var_110], rax
0x180020cd5  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180020cda  jmp     short loc_180020D14
0x180020cdc  mov     eax, cs:dword_1801B76C8
0x180020ce2  cmp     eax, 4
0x180020ce5  jbe     short loc_180020D14
0x180020ce7  lea     rax, aUmrdpOndisconn; "UMRDP::OnDisconnected:  Received attend"...
0x180020cee  mov     qword ptr [rbp+57h+var_70], r12
0x180020cf2  mov     [rbp+57h+var_A8], rax
0x180020cf6  lea     rdx, byte_180196F29
0x180020cfd  lea     rax, [rbp+57h+var_70]
0x180020d01  mov     [rsp+130h+var_108], rax
0x180020d06  lea     rax, [rbp+57h+var_A8]
0x180020d0a  mov     qword ptr [rsp+130h+var_110], rax
0x180020d0f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180020d14  lea     rcx, [rdi-20h]; this
0x180020d18  call    ?TerminateInstance@CUMRDPConnection@@UEAAJXZ; CUMRDPConnection::TerminateInstance(void)
0x180020d1d  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180020d21  mov     ecx, 2; ControlCode
0x180020d26  call    cs:__imp_EventActivityIdControl
0x180020d2c  lea     rcx, [rbp+57h+var_98]
0x180020d30  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x180020d35  lea     rcx, [rbp+57h+var_90]
0x180020d39  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x180020d3e  mov     rcx, [rbp+57h+var_40]
0x180020d42  xor     rcx, rsp; StackCookie
0x180020d45  call    __security_check_cookie
0x180020d4a  mov     rbx, [rsp+130h+arg_8]
0x180020d52  add     rsp, 100h
0x180020d59  pop     r15
0x180020d5b  pop     r14
0x180020d5d  pop     r13
0x180020d5f  pop     r12
0x180020d61  pop     rdi
0x180020d62  pop     rsi
0x180020d63  pop     rbp
0x180020d64  retn
```
