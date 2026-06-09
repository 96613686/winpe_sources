# KerbQuerySpnOracle(_KERB_LOGON_SESSION *,_KERB_PRIMARY_CREDENTIAL *,ulong *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *)

- ea: `0x180041d18`
- end: `0x180041fea`
- name: `?KerbQuerySpnOracle@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_PRIMARY_CREDENTIAL@@PEAKPEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@@Z`
- size: `722`
- prototype: `int(struct _KERB_LOGON_SESSION *, struct _KERB_PRIMARY_CREDENTIAL *, unsigned int *, struct _KERB_INTERNAL_NAME *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003eb80`

## callees

- `0x180001928`
- `0x1800068d0`
- `0x180030a14`
- `0x180032964`
- `0x1800350b4`
- `0x180035de0`
- `0x180036bb8`
- `0x18003aef0`
- `0x180041d18`
- `0x180070680`
- `0x18008a304`
- `0x18008b70c`
- `0x1800d3de0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041e2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041ed4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041e2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041ed4`
- `ntdll!RtlEnterCriticalSection` at `0x180041d5b`
- `ntdll!RtlEnterCriticalSection` at `0x180041d77`
- `ntdll!RtlEnterCriticalSection` at `0x180041d5b`
- `ntdll!RtlEnterCriticalSection` at `0x180041d77`
- `ntdll!RtlLeaveCriticalSection` at `0x180041dd0`
- `ntdll!RtlLeaveCriticalSection` at `0x180041ea3`
- `ntdll!RtlLeaveCriticalSection` at `0x180041fc4`
- `ntdll!RtlLeaveCriticalSection` at `0x180041dd0`
- `ntdll!RtlLeaveCriticalSection` at `0x180041ea3`
- `ntdll!RtlLeaveCriticalSection` at `0x180041fc4`

## string_xrefs

- `0x180041dbc`: `KerbQuerySpnOracle`
- `0x180041f3a`: `KerbQuerySpnOracle`
- `0x180041f9f`: `KerbQuerySpnOracle`
- `0x180041f2d`: `SPN Oracle found realm: %wZ`
- `0x180041f92`: `SPN Oracle lookup failed: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KerbQuerySpnOracle(
        struct _RTL_CRITICAL_SECTION *a1,
        struct _RTL_CRITICAL_SECTION *a2,
        unsigned int *a3,
        struct _KERB_INTERNAL_NAME *a4,
        struct _UNICODE_STRING *a5)
{
  struct _RTL_CRITICAL_SECTION *v9; // rsi
  __int64 v10; // rcx
  __int64 v11; // rcx
  _DWORD *v12; // rax
  int v13; // ecx
  struct _UNICODE_STRING *v14; // r9
  _DWORD *v15; // r9
  int v16; // ebx
  int v17; // r9d
  DWORD CurrentThreadId; // [rsp+40h] [rbp-41h] BYREF
  _QWORD v20[2]; // [rsp+48h] [rbp-39h] BYREF
  __int64 v21; // [rsp+58h] [rbp-29h] BYREF
  struct _UNICODE_STRING v22; // [rsp+60h] [rbp-21h] BYREF
  int v23; // [rsp+70h] [rbp-11h] BYREF
  char v24; // [rsp+74h] [rbp-Dh]
  _BYTE v25[16]; // [rsp+78h] [rbp-9h] BYREF
  _DWORD v26[4]; // [rsp+88h] [rbp+7h] BYREF

  v22 = 0;
  v9 = a1 + 2;
  RtlEnterCriticalSection(a1 + 2);
  if ( a2[15].DebugInfo && (a2[10].LockCount & 8) == 0 )
  {
    RtlEnterCriticalSection(v9);
    if ( a2 != &a1[3] )
      MicrosoftTelemetryAssertTriggeredNoArgs(v11);
    v12 = (_DWORD *)KerbConsumeAsRepCallbackAndInitializeCloudKerb(&v21, a1, 0);
    v13 = v12[1];
    if ( (int)*v12 < 0 || v13 < 0 )
      KerbTracerT::Log(
        2,
        "KerbQuerySpnOracle",
        6659,
        "Failed to get metadata from AS_REP callback: 0x%x, 0x%x - continuing anyway...",
        *v12,
        v13);
    RtlLeaveCriticalSection(v9);
  }
  if ( a2[15].OwningThread )
  {
    if ( a2 != &a1[3] )
      MicrosoftTelemetryAssertTriggeredNoArgs(v10);
    v23 = 0;
    v24 = 0;
    _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const KerbTraceLogger,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v23);
    if ( (unsigned int)dword_180140048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180140048, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v20[0] = 0x1000000;
      if ( v24 && (v26[0] || v26[1] || v26[2] || v26[3]) )
        v15 = v26;
      else
        LODWORD(v15) = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_180140048,
        (unsigned int)&byte_18012B807,
        (unsigned int)v25,
        (_DWORD)v15,
        (__int64)v20,
        (__int64)&CurrentThreadId);
    }
    v16 = SpnOracleLib::DoSpnOracleLookup(
            (SpnOracleLib *)a2[15].OwningThread,
            a4,
            (const struct _KERB_INTERNAL_NAME *)&v22,
            v14);
    RtlLeaveCriticalSection(v9);
    v23 = 2;
    if ( (unsigned int)dword_180140048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180140048, 0x400000000000LL) )
    {
      CurrentThreadId = v16;
      LODWORD(v20[0]) = GetCurrentThreadId();
      v21 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_180140048,
        (unsigned int)word_18012B7C2,
        (unsigned int)v25,
        v17,
        (__int64)&v21,
        (__int64)v20,
        (__int64)&CurrentThreadId);
    }
    if ( v16 < 0 )
    {
      if ( v16 != -1073741198 )
        KerbTracerT::Log(19, "KerbQuerySpnOracle", 6704, "SPN Oracle lookup failed: 0x%x", v16);
    }
    else
    {
      KerbFreeString((__int64)a5);
      *a5 = v22;
      KerbTracerT::Log(19, "KerbQuerySpnOracle", 6697, "SPN Oracle found realm: %wZ", a5);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
        WPP_SF__KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_6aa791a05c093f7e04cd3adcd492ce53_Traceguids, a4);
      *a3 |= 0x10000000u;
    }
    _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const KerbTraceLogger,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const KerbTraceLogger,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v23);
  }
  else
  {
    v16 = -1073741198;
    RtlLeaveCriticalSection(v9);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180041d18  push    rbp
0x180041d1a  push    rbx
0x180041d1b  push    rsi
0x180041d1c  push    rdi
0x180041d1d  push    r12
0x180041d1f  push    r14
0x180041d21  push    r15
0x180041d23  lea     rbp, [rsp-1Fh]
0x180041d28  sub     rsp, 0A0h
0x180041d2f  mov     rax, cs:__security_cookie
0x180041d36  xor     rax, rsp
0x180041d39  mov     [rbp+4Fh+var_38], rax
0x180041d3d  mov     r12, r9
0x180041d40  mov     r14, r8
0x180041d43  mov     rbx, rdx
0x180041d46  mov     rdi, rcx
0x180041d49  mov     r15, [rbp+4Fh+arg_20]
0x180041d4d  xorps   xmm0, xmm0
0x180041d50  movups  [rbp+4Fh+var_70], xmm0
0x180041d54  lea     rsi, [rcx+50h]
0x180041d58  mov     rcx, rsi; CriticalSection
0x180041d5b  call    cs:__imp_RtlEnterCriticalSection
0x180041d61  cmp     qword ptr [rbx+258h], 0
0x180041d69  jz      short loc_180041DD6
0x180041d6b  test    byte ptr [rbx+198h], 8
0x180041d72  jnz     short loc_180041DD6
0x180041d74  mov     rcx, rsi; CriticalSection
0x180041d77  call    cs:__imp_RtlEnterCriticalSection
0x180041d7d  lea     rax, [rdi+78h]
0x180041d81  cmp     rbx, rax
0x180041d84  jz      short loc_180041D8B
0x180041d86  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180041d8b  xor     r8d, r8d
0x180041d8e  mov     rdx, rdi
0x180041d91  lea     rcx, [rbp+4Fh+var_78]
0x180041d95  call    ?KerbConsumeAsRepCallbackAndInitializeCloudKerb@@YA?AU?$pair@JJ@std@@PEAU_KERB_LOGON_SESSION@@PEAU_KERB_AS_REP_PROCESSED_CREDENTIAL@@@Z; KerbConsumeAsRepCallbackAndInitializeCloudKerb(_KERB_LOGON_SESSION *,_KERB_AS_REP_PROCESSED_CREDENTIAL *)
0x180041d9a  mov     edx, [rax]
0x180041d9c  mov     ecx, [rax+4]
0x180041d9f  test    edx, edx
0x180041da1  js      short loc_180041DA7
0x180041da3  test    ecx, ecx
0x180041da5  jns     short loc_180041DCD
0x180041da7  mov     dword ptr [rsp+0D0h+var_A8], ecx
0x180041dab  mov     dword ptr [rsp+0D0h+var_B0], edx
0x180041daf  lea     r9, aFailedToGetMet; "Failed to get metadata from AS_REP call"...
0x180041db6  mov     r8d, 1A03h
0x180041dbc  lea     rdx, aKerbqueryspnor; "KerbQuerySpnOracle"
0x180041dc3  mov     ecx, 2
0x180041dc8  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180041dcd  mov     rcx, rsi; CriticalSection
0x180041dd0  call    cs:__imp_RtlLeaveCriticalSection
0x180041dd6  cmp     qword ptr [rbx+268h], 0
0x180041dde  jz      loc_180041FBC
0x180041de4  lea     rax, [rdi+78h]
0x180041de8  cmp     rbx, rax
0x180041deb  jz      short loc_180041DF2
0x180041ded  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180041df2  mov     [rbp+4Fh+var_60], 0
0x180041df9  mov     [rbp+4Fh+var_5C], 0
0x180041dfd  lea     rcx, [rbp+4Fh+var_60]
0x180041e01  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?KerbTraceLogger@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const KerbTraceLogger,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x180041e06  mov     eax, cs:dword_180140048
0x180041e0c  lea     rdi, dword_180140048
0x180041e13  cmp     eax, 5
0x180041e16  jbe     short loc_180041E8B
0x180041e18  mov     rdx, 400000000000h
0x180041e22  mov     rcx, rdi
0x180041e25  call    _tlgKeywordOn
0x180041e2a  test    al, al
0x180041e2c  jz      short loc_180041E8B
0x180041e2e  call    cs:__imp_GetCurrentThreadId
0x180041e34  mov     [rbp+4Fh+var_90], eax
0x180041e37  mov     [rbp+4Fh+var_88], 1000000h
0x180041e3f  cmp     [rbp+4Fh+var_5C], 0
0x180041e43  jz      short loc_180041E63
0x180041e45  cmp     [rbp+4Fh+var_48], 0
0x180041e49  jnz     short loc_180041E5D
0x180041e4b  cmp     [rbp+4Fh+var_44], 0
0x180041e4f  jnz     short loc_180041E5D
0x180041e51  cmp     [rbp+4Fh+var_40], 0
0x180041e55  jnz     short loc_180041E5D
0x180041e57  cmp     [rbp+4Fh+var_3C], 0
0x180041e5b  jz      short loc_180041E63
0x180041e5d  lea     r9, [rbp+4Fh+var_48]
0x180041e61  jmp     short loc_180041E66
0x180041e63  xor     r9d, r9d
0x180041e66  lea     rax, [rbp+4Fh+var_90]
0x180041e6a  mov     [rsp+0D0h+var_A8], rax
0x180041e6f  lea     rax, [rbp+4Fh+var_88]
0x180041e73  mov     [rsp+0D0h+var_B0], rax
0x180041e78  lea     r8, [rbp+4Fh+var_58]
0x180041e7c  lea     rdx, byte_18012B807
0x180041e83  mov     rcx, rdi
0x180041e86  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180041e8b  lea     r8, [rbp+4Fh+var_70]; struct _KERB_INTERNAL_NAME *
0x180041e8f  mov     rdx, r12; struct SpnOracleLib::SpnOracle *
0x180041e92  mov     rcx, [rbx+268h]; this
0x180041e99  call    ?DoSpnOracleLookup@SpnOracleLib@@YAJPEBVSpnOracle@1@PEBU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@@Z; SpnOracleLib::DoSpnOracleLookup(SpnOracleLib::SpnOracle const *,_KERB_INTERNAL_NAME const *,_UNICODE_STRING *)
0x180041e9e  mov     ebx, eax
0x180041ea0  mov     rcx, rsi; CriticalSection
0x180041ea3  call    cs:__imp_RtlLeaveCriticalSection
0x180041ea9  mov     [rbp+4Fh+var_60], 2
0x180041eb0  mov     ecx, cs:dword_180140048
0x180041eb6  cmp     ecx, 5
0x180041eb9  jbe     short loc_180041F13
0x180041ebb  mov     rdx, 400000000000h
0x180041ec5  mov     rcx, rdi
0x180041ec8  call    _tlgKeywordOn
0x180041ecd  test    al, al
0x180041ecf  jz      short loc_180041F13
0x180041ed1  mov     [rbp+4Fh+var_90], ebx
0x180041ed4  call    cs:__imp_GetCurrentThreadId
0x180041eda  mov     dword ptr [rbp+4Fh+var_88], eax
0x180041edd  mov     [rbp+4Fh+var_78], 1000000h
0x180041ee5  lea     rax, [rbp+4Fh+var_90]
0x180041ee9  mov     [rsp+0D0h+var_A0], rax
0x180041eee  lea     rax, [rbp+4Fh+var_88]
0x180041ef2  mov     [rsp+0D0h+var_A8], rax
0x180041ef7  lea     rax, [rbp+4Fh+var_78]
0x180041efb  mov     [rsp+0D0h+var_B0], rax
0x180041f00  lea     r8, [rbp+4Fh+var_58]
0x180041f04  lea     rdx, word_18012B7C2
0x180041f0b  mov     rcx, rdi
0x180041f0e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180041f13  test    ebx, ebx
0x180041f15  js      short loc_180041F86
0x180041f17  mov     rcx, r15
0x180041f1a  call    KerbFreeString
0x180041f1f  movups  xmm0, [rbp+4Fh+var_70]
0x180041f23  movdqu  xmmword ptr [r15], xmm0
0x180041f28  mov     [rsp+0D0h+var_B0], r15
0x180041f2d  lea     r9, aSpnOracleFound; "SPN Oracle found realm: %wZ"
0x180041f34  mov     r8d, 1A29h
0x180041f3a  lea     rdx, aKerbqueryspnor; "KerbQuerySpnOracle"
0x180041f41  mov     ecx, 13h
0x180041f46  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180041f4b  lea     rax, WPP_GLOBAL_Control
0x180041f52  mov     rcx, cs:WPP_GLOBAL_Control
0x180041f59  cmp     rcx, rax
0x180041f5c  jz      short loc_180041F7F
0x180041f5e  test    dword ptr [rcx+1Ch], 40000h
0x180041f65  jz      short loc_180041F7F
0x180041f67  mov     edx, 13h
0x180041f6c  mov     r9, r12
0x180041f6f  lea     r8, WPP_6aa791a05c093f7e04cd3adcd492ce53_Traceguids
0x180041f76  mov     rcx, [rcx+10h]
0x180041f7a  call    WPP_SF__KERB_NAME_
0x180041f7f  bts     dword ptr [r14], 1Ch
0x180041f84  jmp     short loc_180041FB1
0x180041f86  cmp     ebx, 0C0000272h
0x180041f8c  jz      short loc_180041FB1
0x180041f8e  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x180041f92  lea     r9, aSpnOracleLooku; "SPN Oracle lookup failed: 0x%x"
0x180041f99  mov     r8d, 1A30h
0x180041f9f  lea     rdx, aKerbqueryspnor; "KerbQuerySpnOracle"
0x180041fa6  mov     ecx, 13h
0x180041fab  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180041fb0  nop
0x180041fb1  lea     rcx, [rbp+4Fh+var_60]
0x180041fb5  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?KerbTraceLogger@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const KerbTraceLogger,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const KerbTraceLogger,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x180041fba  jmp     short loc_180041FCA
0x180041fbc  mov     ebx, 0C0000272h
0x180041fc1  mov     rcx, rsi; CriticalSection
0x180041fc4  call    cs:__imp_RtlLeaveCriticalSection
0x180041fca  mov     eax, ebx
0x180041fcc  mov     rcx, [rbp+4Fh+var_38]
0x180041fd0  xor     rcx, rsp; StackCookie
0x180041fd3  call    __security_check_cookie
0x180041fd8  add     rsp, 0A0h
0x180041fdf  pop     r15
0x180041fe1  pop     r14
0x180041fe3  pop     r12
0x180041fe5  pop     rdi
0x180041fe6  pop     rsi
0x180041fe7  pop     rbx
0x180041fe8  pop     rbp
0x180041fe9  retn
```
