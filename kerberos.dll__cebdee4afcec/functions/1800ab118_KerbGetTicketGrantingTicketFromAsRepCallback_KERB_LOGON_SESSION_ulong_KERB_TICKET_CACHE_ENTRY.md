# KerbGetTicketGrantingTicketFromAsRepCallback(_KERB_LOGON_SESSION *,ulong,_KERB_TICKET_CACHE_ENTRY * *)

- ea: `0x1800ab118`
- end: `0x1800ab83f`
- name: `?KerbGetTicketGrantingTicketFromAsRepCallback@@YA?AU?$pair@JJ@std@@PEAU_KERB_LOGON_SESSION@@KPEAPEAU_KERB_TICKET_CACHE_ENTRY@@@Z`
- size: `1831`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update`

## callers

- `0x18000b5c0`

## callees

- `0x180001928`
- `0x18001e570`
- `0x180030a14`
- `0x1800350b4`
- `0x180035de0`
- `0x180036bb8`
- `0x18003aef0`
- `0x180040fb8`
- `0x18004ed20`
- `0x180059cec`
- `0x18005a1d0`
- `0x180070680`
- `0x18007108c`
- `0x18008b70c`
- `0x18008f410`
- `0x1800a8194`
- `0x1800a99e8`
- `0x1800aa2f4`
- `0x1800ab118`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ab438`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ab525`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ab438`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ab525`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x1800ab7b5`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x1800ab7c9`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x1800ab7b5`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x1800ab7c9`

## string_xrefs

- `0x1800ab321`: `Failed to update logon session names from AS_REP: 0x%x`
- `0x1800ab3b1`: `Failed to create ticket cache entry for AS_REP credential: 0x%x`
- `0x1800ab73a`: `Failed to cache TGT redeemed from AS_REP ticket: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
int *__fastcall KerbGetTicketGrantingTicketFromAsRepCallback(
        int *a1,
        __int64 a2,
        unsigned int a3,
        struct _KERB_TICKET_CACHE_ENTRY **a4)
{
  __int64 v7; // r12
  int *v8; // rax
  int v9; // ecx
  int v10; // r14d
  int v11; // eax
  int v12; // esi
  int updated; // eax
  int v14; // esi
  int v15; // eax
  int TgsTicket; // esi
  _DWORD *v17; // r9
  int v18; // eax
  int v19; // r9d
  unsigned int v20; // eax
  unsigned int v21; // ebx
  int v22; // eax
  int v23; // esi
  DWORD CurrentThreadId; // [rsp+B0h] [rbp-80h] BYREF
  int v26; // [rsp+B4h] [rbp-7Ch] BYREF
  HLOCAL hMem; // [rsp+B8h] [rbp-78h] BYREF
  struct KERB_KDC_REPLY *v28; // [rsp+C0h] [rbp-70h] BYREF
  struct _KERB_TICKET_CACHE_ENTRY *v29; // [rsp+C8h] [rbp-68h] BYREF
  struct _UNICODE_STRING v30; // [rsp+D0h] [rbp-60h] BYREF
  unsigned int v31; // [rsp+E0h] [rbp-50h] BYREF
  unsigned int v32; // [rsp+E4h] [rbp-4Ch] BYREF
  struct KERB_ENCRYPTED_KDC_REPLY *v33; // [rsp+E8h] [rbp-48h] BYREF
  struct _KERB_TICKET_CACHE_ENTRY *v34; // [rsp+F0h] [rbp-40h] BYREF
  struct KERB_ENCRYPTED_KDC_REPLY *v35; // [rsp+F8h] [rbp-38h] BYREF
  struct KERB_KDC_REPLY *v36; // [rsp+100h] [rbp-30h] BYREF
  struct _KERB_TICKET_CACHE_ENTRY **v37; // [rsp+108h] [rbp-28h] BYREF
  _QWORD v38[2]; // [rsp+110h] [rbp-20h] BYREF
  _QWORD v39[11]; // [rsp+120h] [rbp-10h] BYREF
  char v40; // [rsp+178h] [rbp+48h]
  struct _UNICODE_STRING v41; // [rsp+180h] [rbp+50h] BYREF
  _BYTE *v42; // [rsp+190h] [rbp+60h] BYREF
  __int64 v43; // [rsp+198h] [rbp+68h] BYREF
  int v44; // [rsp+1A0h] [rbp+70h]
  __int64 v45; // [rsp+1A8h] [rbp+78h]
  int v46; // [rsp+1B0h] [rbp+80h]
  int v47; // [rsp+200h] [rbp+D0h] BYREF
  char v48; // [rsp+204h] [rbp+D4h]
  _BYTE v49[16]; // [rsp+208h] [rbp+D8h] BYREF
  _DWORD v50[4]; // [rsp+218h] [rbp+E8h] BYREF

  v37 = a4;
  v26 = 0;
  memset_0(&v42, 0, 0x68u);
  v28 = 0;
  v33 = 0;
  v34 = 0;
  v36 = 0;
  v35 = 0;
  v32 = 0;
  v41 = 0;
  v31 = 0;
  hMem = 0;
  v29 = 0;
  *(_QWORD *)&v30.Length = 2883626;
  v30.Buffer = L"TicketSuppliedAtLogon";
  v7 = a2 + 64;
  KerbTracerT::Log(
    3,
    "KerbGetTicketGrantingTicketFromAsRepCallback",
    7061,
    "starting for logon 0x%x:0x%x flags %d",
    *(_DWORD *)(a2 + 68),
    *(_DWORD *)(a2 + 64),
    a3);
  v39[0] = &v26;
  v39[1] = &v42;
  v39[2] = &v34;
  v39[3] = &v29;
  v39[4] = &v37;
  v39[5] = &v28;
  v39[6] = &v33;
  v39[7] = &v36;
  v39[8] = &v35;
  v39[9] = &hMem;
  v39[10] = &v41;
  v40 = 1;
  v8 = (int *)KerbConsumeAsRepCallbackAndInitializeCloudKerb(v38, a2, &v42);
  v9 = *v8;
  v26 = v9;
  v10 = v8[1];
  if ( v9 < 0 )
  {
    *a1 = v9;
    a1[1] = v10;
    v40 = 0;
    lambda_65afc242962a8f822b64f2d14de57fb0_::operator()(v39);
    return a1;
  }
  if ( v45 && v46 && v43 && v44 )
  {
    KerbTracerT::Log(8, "KerbGetTicketGrantingTicketFromAsRepCallback", 7107, ": Unpacking the McTicket");
    v11 = KerbDecryptAndUnpackAsRepCredential((struct _KERB_AS_REP_PACKAGE *)&v43, &v28, &v33);
    v12 = v11;
    if ( v11 < 0 )
    {
      KerbTracerT::Log(
        1,
        "KerbGetTicketGrantingTicketFromAsRepCallback",
        7117,
        "Failed to decrypt and unpack McTicket AS_REP credential: 0x%x",
        v11);
      *a1 = v12;
      a1[1] = v10;
      v40 = 0;
      lambda_65afc242962a8f822b64f2d14de57fb0_::operator()(v39);
      return a1;
    }
    updated = KerbUpdatePrimaryCredentialsNamesFromAsRep((struct _UNICODE_STRING *)(a2 + 120), v28, 0);
    v14 = updated;
    if ( updated < 0 )
    {
      KerbTracerT::Log(
        1,
        "KerbGetTicketGrantingTicketFromAsRepCallback",
        7126,
        "Failed to update logon session names from AS_REP: 0x%x",
        updated);
      *a1 = v14;
      a1[1] = v10;
      v40 = 0;
      lambda_65afc242962a8f822b64f2d14de57fb0_::operator()(v39);
      return a1;
    }
    v15 = KerbCreateTicketCacheEntry(v28, v33, LocalhostKerbCredIsoObj::IsoObj, 0, 0, 0x400u, 0, 0, 0, &v30, 0, 0, &v34);
    TgsTicket = v15;
    if ( v15 < 0 )
    {
      KerbTracerT::Log(
        1,
        "KerbGetTicketGrantingTicketFromAsRepCallback",
        7148,
        "Failed to create ticket cache entry for AS_REP credential: 0x%x",
        v15);
      *a1 = TgsTicket;
      a1[1] = v10;
      v40 = 0;
      lambda_65afc242962a8f822b64f2d14de57fb0_::operator()(v39);
      return a1;
    }
    if ( KerbGlobalKeyListReqSupportOverride )
    {
      v47 = 0;
      v48 = 0;
      _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const KerbTraceLogger,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v47);
      if ( (unsigned int)dword_180140048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180140048, 0x400000000000LL) )
      {
        CurrentThreadId = GetCurrentThreadId();
        *(_QWORD *)&v30.Length = 0x1000000;
        if ( v48 && (v50[0] || v50[1] || v50[2] || v50[3]) )
          v17 = v50;
        else
          LODWORD(v17) = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_180140048,
          (unsigned int)&byte_18012C3E7,
          (unsigned int)v49,
          (_DWORD)v17,
          (__int64)&v30,
          (__int64)&CurrentThreadId);
      }
      v18 = KerbAddKeyListReqPreAuth(&hMem);
      TgsTicket = v18;
      if ( v18 >= 0 )
      {
        a3 |= 0x8000000u;
      }
      else
      {
        KerbTracerT::Log(
          2,
          "KerbGetTicketGrantingTicketFromAsRepCallback",
          7166,
          "Failed to add key list req to PA data: 0x%x",
          v18);
        KerbFreePreAuthData(hMem);
        hMem = 0;
      }
      v47 = 2;
      if ( (unsigned int)dword_180140048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180140048, 0x400000000000LL) )
      {
        CurrentThreadId = TgsTicket;
        *(_DWORD *)&v30.Length = GetCurrentThreadId();
        v38[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_180140048,
          (unsigned int)&dword_18012C3A4,
          (unsigned int)v49,
          v19,
          (__int64)v38,
          (__int64)&v30,
          (__int64)&CurrentThreadId);
      }
      _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const KerbTraceLogger,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const KerbTraceLogger,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v47);
    }
    KerbTracerT::Log(8, "KerbGetTicketGrantingTicketFromAsRepCallback", 7185, ": using the McTicket to get a TGT...");
    if ( (*v42 & 1) == 0 )
      TgsTicket = KerbGetTgsTicketEx(
                    (struct _KERB_LOGON_SESSION *)a2,
                    0,
                    0,
                    v34,
                    *((struct _KERB_INTERNAL_NAME **)v34 + 4),
                    a3,
                    0x40810010u,
                    0,
                    0,
                    0,
                    0,
                    (struct KERB_KDC_REQUEST_preauth_data_s *)hMem,
                    0,
                    0,
                    0,
                    0,
                    &v36,
                    &v35,
                    &v32,
                    &v41,
                    &v31,
                    0);
    if ( TgsTicket < 0 )
    {
      KerbTracerT::Log(
        1,
        "KerbGetTicketGrantingTicketFromAsRepCallback",
        7223,
        "Failed to redeem AS_REP ticket (McTicket) for Hub TGT: 0x%x",
        TgsTicket);
      if ( TgsTicket == -1073741711 || TgsTicket == -1073741276 )
      {
        v20 = *(_DWORD *)(a2 + 904);
        v21 = (v20 >> 26) & 1;
        KerbTracerT::Log(
          1,
          "KerbGetTicketGrantingTicketFromAsRepCallback",
          7239,
          "%hs: Showing Stale Cred Notification Balloon from AS_REP cred, Status 0x%x, BalloonType %x, LogonSessionFlags 0x%x",
          "KerbGetTicketGrantingTicketFromAsRepCallback",
          TgsTicket,
          v21,
          v20);
        KerbPingWlBalloon(v7, v21);
      }
      *a1 = TgsTicket;
      a1[1] = v10;
      v40 = 0;
      lambda_65afc242962a8f822b64f2d14de57fb0_::operator()(v39);
      return a1;
    }
    v22 = KerbCreateTicketCacheEntry(
            v36,
            v35,
            LocalhostKerbCredIsoObj::IsoObj,
            0,
            0,
            1u,
            0,
            (struct _KERB_TICKET_CACHE *)(a2 + 360),
            0,
            &v41,
            0,
            0,
            &v29);
    v23 = v22;
    if ( v22 < 0 )
    {
      KerbTracerT::Log(
        1,
        "KerbGetTicketGrantingTicketFromAsRepCallback",
        7265,
        "Failed to cache TGT redeemed from AS_REP ticket: 0x%x",
        v22);
      *a1 = v23;
      a1[1] = v10;
      v40 = 0;
      lambda_65afc242962a8f822b64f2d14de57fb0_::operator()(v39);
      return a1;
    }
    KerbTracerT::Log(
      3,
      "KerbGetTicketGrantingTicketFromAsRepCallback",
      7269,
      "Redeemed McTicket for TGT, cleaning up non-AS_REP credentials since the AS_REP worked");
    *(_DWORD *)(a2 + 904) = *(_DWORD *)(a2 + 904) & 0xFFBFFF7F | 0x400000;
    KerbCleanupLogonSessionCredentials((struct _KERB_LOGON_SESSION *)a2);
    KerbClientFreeStoredCred(*(struct _KERB_STORED_CREDENTIAL **)(a2 + 264));
    *(_QWORD *)(a2 + 264) = 0;
    KerbClientFreeStoredCred(*(struct _KERB_STORED_CREDENTIAL **)(a2 + 272));
    *(_QWORD *)(a2 + 272) = 0;
  }
  if ( v37 )
  {
    *v37 = v29;
    v29 = 0;
  }
  KerbTracerT::Log(3, "KerbGetTicketGrantingTicketFromAsRepCallback", 7290, "Successfully redeemed AS_REP credential");
  *a1 = 0;
  a1[1] = v10;
  v40 = 0;
  lambda_65afc242962a8f822b64f2d14de57fb0_::operator()(v39);
  return a1;
}

```

## disassembly

```asm
0x1800ab118  push    rbp
0x1800ab11a  push    rbx
0x1800ab11b  push    rsi
0x1800ab11c  push    rdi
0x1800ab11d  push    r12
0x1800ab11f  push    r13
0x1800ab121  push    r14
0x1800ab123  push    r15
0x1800ab125  lea     rbp, [rsp-108h]
0x1800ab12d  sub     rsp, 238h
0x1800ab134  mov     rax, cs:__security_cookie
0x1800ab13b  xor     rax, rsp
0x1800ab13e  mov     [rbp+140h+var_48], rax
0x1800ab145  mov     r15d, r8d
0x1800ab148  mov     rbx, rdx
0x1800ab14b  mov     rdi, rcx
0x1800ab14e  mov     [rbp+140h+var_168], r9
0x1800ab152  xor     r13d, r13d
0x1800ab155  mov     [rbp+140h+var_1BC], r13d
0x1800ab159  xor     edx, edx; Val
0x1800ab15b  lea     r8d, [r13+68h]; Size
0x1800ab15f  lea     rcx, [rbp+140h+var_E0]; void *
0x1800ab163  call    memset_0
0x1800ab168  mov     [rbp+140h+var_1B0], r13
0x1800ab16c  mov     [rbp+140h+var_188], r13
0x1800ab170  mov     [rbp+140h+var_180], r13
0x1800ab174  mov     [rbp+140h+var_170], r13
0x1800ab178  mov     [rbp+140h+var_178], r13
0x1800ab17c  mov     [rbp+140h+var_18C], r13d
0x1800ab180  xorps   xmm0, xmm0
0x1800ab183  movups  xmmword ptr [rbp+140h+var_F0.Length], xmm0
0x1800ab187  mov     [rbp+140h+var_190], r13d
0x1800ab18b  mov     [rbp+140h+hMem], r13
0x1800ab18f  mov     [rbp+140h+var_1A8], r13
0x1800ab193  mov     qword ptr [rbp+140h+var_1A0.Length], 2C002Ah
0x1800ab19b  lea     rax, aTicketsupplied; "TicketSuppliedAtLogon"
0x1800ab1a2  mov     [rbp+140h+var_1A0.Buffer], rax
0x1800ab1a6  lea     r12, [rbx+40h]
0x1800ab1aa  mov     [rsp+270h+var_240], r15d
0x1800ab1af  mov     eax, [r12]
0x1800ab1b3  mov     [rsp+270h+var_248], eax
0x1800ab1b7  mov     eax, [rbx+44h]
0x1800ab1ba  mov     dword ptr [rsp+270h+var_250], eax
0x1800ab1be  lea     r9, aStartingForLog; "starting for logon 0x%x:0x%x flags %d"
0x1800ab1c5  mov     r8d, 1B95h
0x1800ab1cb  lea     rsi, aKerbgetticketg_5; "KerbGetTicketGrantingTicketFromAsRepCal"...
0x1800ab1d2  mov     rdx, rsi
0x1800ab1d5  lea     ecx, [r13+3]
0x1800ab1d9  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800ab1de  lea     rax, [rbp+140h+var_1BC]
0x1800ab1e2  mov     [rbp+140h+var_150], rax
0x1800ab1e6  lea     rax, [rbp+140h+var_E0]
0x1800ab1ea  mov     [rbp+140h+var_148], rax
0x1800ab1ee  lea     rax, [rbp+140h+var_180]
0x1800ab1f2  mov     [rbp+140h+var_140], rax
0x1800ab1f6  lea     rax, [rbp+140h+var_1A8]
0x1800ab1fa  mov     [rbp+140h+var_138], rax
0x1800ab1fe  lea     rax, [rbp+140h+var_168]
0x1800ab202  mov     [rbp+140h+var_130], rax
0x1800ab206  lea     rax, [rbp+140h+var_1B0]
0x1800ab20a  mov     [rbp+140h+var_128], rax
0x1800ab20e  lea     rax, [rbp+140h+var_188]
0x1800ab212  mov     [rbp+140h+var_120], rax
0x1800ab216  lea     rax, [rbp+140h+var_170]
0x1800ab21a  mov     [rbp+140h+var_118], rax
0x1800ab21e  lea     rax, [rbp+140h+var_178]
0x1800ab222  mov     [rbp+140h+var_110], rax
0x1800ab226  lea     rax, [rbp+140h+hMem]
0x1800ab22a  mov     [rbp+140h+var_108], rax
0x1800ab22e  lea     rax, [rbp+140h+var_F0]
0x1800ab232  mov     [rbp+140h+var_100], rax
0x1800ab236  mov     [rbp+140h+var_F8], 1
0x1800ab23a  lea     r8, [rbp+140h+var_E0]
0x1800ab23e  mov     rdx, rbx
0x1800ab241  lea     rcx, [rbp+140h+var_160]
0x1800ab245  call    ?KerbConsumeAsRepCallbackAndInitializeCloudKerb@@YA?AU?$pair@JJ@std@@PEAU_KERB_LOGON_SESSION@@PEAU_KERB_AS_REP_PROCESSED_CREDENTIAL@@@Z; KerbConsumeAsRepCallbackAndInitializeCloudKerb(_KERB_LOGON_SESSION *,_KERB_AS_REP_PROCESSED_CREDENTIAL *)
0x1800ab24a  mov     ecx, [rax]
0x1800ab24c  mov     [rbp+140h+var_1BC], ecx
0x1800ab24f  mov     r14d, [rax+4]
0x1800ab253  test    ecx, ecx
0x1800ab255  jns     short loc_1800AB270
0x1800ab257  mov     [rdi], ecx
0x1800ab259  mov     [rdi+4], r14d
0x1800ab25d  mov     [rbp+140h+var_F8], r13b
0x1800ab261  lea     rcx, [rbp+140h+var_150]
0x1800ab265  call    _lambda_65afc242962a8f822b64f2d14de57fb0___operator__
0x1800ab26a  nop
0x1800ab26b  jmp     loc_1800AB819
0x1800ab270  cmp     [rbp+140h+var_C8], r13
0x1800ab274  jz      loc_1800AB7D6
0x1800ab27a  cmp     [rbp+140h+var_C0], r13d
0x1800ab281  jz      loc_1800AB7D6
0x1800ab287  cmp     [rbp+140h+var_D8], r13
0x1800ab28b  jz      loc_1800AB7D6
0x1800ab291  cmp     [rbp+140h+var_D0], r13d
0x1800ab295  jz      loc_1800AB7D6
0x1800ab29b  lea     r9, aUnpackingTheMc; ": Unpacking the McTicket"
0x1800ab2a2  mov     r8d, 1BC3h
0x1800ab2a8  mov     rdx, rsi
0x1800ab2ab  mov     ecx, 8
0x1800ab2b0  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800ab2b5  lea     r8, [rbp+140h+var_188]; struct KERB_ENCRYPTED_KDC_REPLY **
0x1800ab2b9  lea     rdx, [rbp+140h+var_1B0]; struct KERB_KDC_REPLY **
0x1800ab2bd  lea     rcx, [rbp+140h+var_D8]; struct _KERB_AS_REP_PACKAGE *
0x1800ab2c1  call    ?KerbDecryptAndUnpackAsRepCredential@@YAJAEAU_KERB_AS_REP_PACKAGE@@PEAPEAUKERB_KDC_REPLY@@PEAPEAUKERB_ENCRYPTED_KDC_REPLY@@@Z; KerbDecryptAndUnpackAsRepCredential(_KERB_AS_REP_PACKAGE &,KERB_KDC_REPLY * *,KERB_ENCRYPTED_KDC_REPLY * *)
0x1800ab2c6  mov     esi, eax
0x1800ab2c8  test    eax, eax
0x1800ab2ca  jns     short loc_1800AB307
0x1800ab2cc  mov     dword ptr [rsp+270h+var_250], eax
0x1800ab2d0  lea     r9, aFailedToDecryp_1; "Failed to decrypt and unpack McTicket A"...
0x1800ab2d7  mov     r8d, 1BCDh
0x1800ab2dd  lea     rdx, aKerbgetticketg_5; "KerbGetTicketGrantingTicketFromAsRepCal"...
0x1800ab2e4  mov     ecx, 1
0x1800ab2e9  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800ab2ee  mov     [rdi], esi
0x1800ab2f0  mov     [rdi+4], r14d
0x1800ab2f4  mov     [rbp+140h+var_F8], r13b
0x1800ab2f8  lea     rcx, [rbp+140h+var_150]
0x1800ab2fc  call    _lambda_65afc242962a8f822b64f2d14de57fb0___operator__
0x1800ab301  nop
0x1800ab302  jmp     loc_1800AB819
0x1800ab307  lea     rcx, [rbx+78h]; struct _UNICODE_STRING *
0x1800ab30b  xor     r8d, r8d; struct _UNICODE_STRING *
0x1800ab30e  mov     rdx, [rbp+140h+var_1B0]; struct KERB_KDC_REPLY *
0x1800ab312  call    ?KerbUpdatePrimaryCredentialsNamesFromAsRep@@YAJPEAU_KERB_PRIMARY_CREDENTIAL@@QEAUKERB_KDC_REPLY@@PEAU_UNICODE_STRING@@@Z; KerbUpdatePrimaryCredentialsNamesFromAsRep(_KERB_PRIMARY_CREDENTIAL *,KERB_KDC_REPLY * const,_UNICODE_STRING *)
0x1800ab317  mov     esi, eax
0x1800ab319  test    eax, eax
0x1800ab31b  jns     short loc_1800AB358
0x1800ab31d  mov     dword ptr [rsp+270h+var_250], eax
0x1800ab321  lea     r9, aFailedToUpdate_0; "Failed to update logon session names fr"...
0x1800ab328  mov     r8d, 1BD6h
0x1800ab32e  lea     rdx, aKerbgetticketg_5; "KerbGetTicketGrantingTicketFromAsRepCal"...
0x1800ab335  mov     ecx, 1
0x1800ab33a  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800ab33f  mov     [rdi], esi
0x1800ab341  mov     [rdi+4], r14d
0x1800ab345  mov     [rbp+140h+var_F8], r13b
0x1800ab349  lea     rcx, [rbp+140h+var_150]
0x1800ab34d  call    _lambda_65afc242962a8f822b64f2d14de57fb0___operator__
0x1800ab352  nop
0x1800ab353  jmp     loc_1800AB819
0x1800ab358  lea     rax, [rbp+140h+var_180]
0x1800ab35c  mov     [rsp+270h+var_210], rax; struct _KERB_TICKET_CACHE_ENTRY **
0x1800ab361  mov     [rsp+270h+var_218], r13; unsigned __int64
0x1800ab366  mov     [rsp+270h+var_220], r13; struct _UNICODE_STRING *
0x1800ab36b  lea     rax, [rbp+140h+var_1A0]
0x1800ab36f  mov     [rsp+270h+var_228], rax; struct _UNICODE_STRING *
0x1800ab374  mov     [rsp+270h+var_230], r13; struct _KERB_ENCRYPTION_KEY *
0x1800ab379  mov     [rsp+270h+var_238], r13; struct _KERB_TICKET_CACHE *
0x1800ab37e  mov     [rsp+270h+var_240], r13d; int
0x1800ab383  mov     [rsp+270h+var_248], 400h; unsigned int
0x1800ab38b  mov     [rsp+270h+var_250], r13; struct _UNICODE_STRING *
0x1800ab390  xor     r9d, r9d; struct _KERB_INTERNAL_NAME *
0x1800ab393  mov     r8, cs:?IsoObj@LocalhostKerbCredIsoObj@@0PEAVKerbCredIsoApi@@EA; struct KerbCredIsoApi *
0x1800ab39a  mov     rdx, [rbp+140h+var_188]; struct KERB_ENCRYPTED_KDC_REPLY *
0x1800ab39e  mov     rcx, [rbp+140h+var_1B0]; struct KERB_KDC_REPLY *
0x1800ab3a2  call    ?KerbCreateTicketCacheEntry@@YAJPEAUKERB_KDC_REPLY@@PEAUKERB_ENCRYPTED_KDC_REPLY@@PEAVKerbCredIsoApi@@PEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@KJPEAU_KERB_TICKET_CACHE@@PEAU_KERB_ENCRYPTION_KEY@@44_KPEAPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbCreateTicketCacheEntry(KERB_KDC_REPLY *,KERB_ENCRYPTED_KDC_REPLY *,KerbCredIsoApi *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *,ulong,long,_KERB_TICKET_CACHE *,_KERB_ENCRYPTION_KEY *,_UNICODE_STRING *,_UNICODE_STRING *,unsigned __int64,_KERB_TICKET_CACHE_ENTRY * *)
0x1800ab3a7  mov     esi, eax
0x1800ab3a9  test    eax, eax
0x1800ab3ab  jns     short loc_1800AB3E8
0x1800ab3ad  mov     dword ptr [rsp+270h+var_250], eax
0x1800ab3b1  lea     r9, aFailedToCreate_1; "Failed to create ticket cache entry for"...
0x1800ab3b8  mov     r8d, 1BECh
0x1800ab3be  lea     rdx, aKerbgetticketg_5; "KerbGetTicketGrantingTicketFromAsRepCal"...
0x1800ab3c5  mov     ecx, 1
0x1800ab3ca  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800ab3cf  mov     [rdi], esi
0x1800ab3d1  mov     [rdi+4], r14d
0x1800ab3d5  mov     [rbp+140h+var_F8], r13b
0x1800ab3d9  lea     rcx, [rbp+140h+var_150]
0x1800ab3dd  call    _lambda_65afc242962a8f822b64f2d14de57fb0___operator__
0x1800ab3e2  nop
0x1800ab3e3  jmp     loc_1800AB819
0x1800ab3e8  cmp     cs:?KerbGlobalKeyListReqSupportOverride@@3KA, r13d; ulong KerbGlobalKeyListReqSupportOverride
0x1800ab3ef  jz      loc_1800AB578
0x1800ab3f5  mov     [rbp+140h+var_70], r13d
0x1800ab3fc  mov     [rbp+140h+var_6C], r13b
0x1800ab403  lea     rcx, [rbp+140h+var_70]
0x1800ab40a  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?KerbTraceLogger@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const KerbTraceLogger,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x1800ab40f  mov     eax, cs:dword_180140048
0x1800ab415  cmp     eax, 5
0x1800ab418  jbe     loc_1800AB4AE
0x1800ab41e  mov     rdx, 400000000000h
0x1800ab428  lea     rcx, dword_180140048
0x1800ab42f  call    _tlgKeywordOn
0x1800ab434  test    al, al
0x1800ab436  jz      short loc_1800AB4AE
0x1800ab438  call    cs:__imp_GetCurrentThreadId
0x1800ab43e  mov     [rbp+140h+var_1C0], eax
0x1800ab441  mov     qword ptr [rbp+140h+var_1A0.Length], 1000000h
0x1800ab449  cmp     [rbp+140h+var_6C], r13b
0x1800ab450  jz      short loc_1800AB47F
0x1800ab452  cmp     [rbp+140h+var_58], r13d
0x1800ab459  jnz     short loc_1800AB476
0x1800ab45b  cmp     [rbp+140h+var_54], r13d
0x1800ab462  jnz     short loc_1800AB476
0x1800ab464  cmp     [rbp+140h+var_50], r13d
0x1800ab46b  jnz     short loc_1800AB476
0x1800ab46d  cmp     [rbp+140h+var_4C], r13d
0x1800ab474  jz      short loc_1800AB47F
0x1800ab476  lea     r9, [rbp+140h+var_58]
0x1800ab47d  jmp     short loc_1800AB482
0x1800ab47f  mov     r9, r13
0x1800ab482  lea     rax, [rbp+140h+var_1C0]
0x1800ab486  mov     qword ptr [rsp+270h+var_248], rax
0x1800ab48b  lea     rax, [rbp+140h+var_1A0]
0x1800ab48f  mov     [rsp+270h+var_250], rax
0x1800ab494  lea     r8, [rbp+140h+var_68]
0x1800ab49b  lea     rdx, byte_18012C3E7
0x1800ab4a2  lea     rcx, dword_180140048
0x1800ab4a9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800ab4ae  lea     rcx, [rbp+140h+hMem]
0x1800ab4b2  call    KerbAddKeyListReqPreAuth
0x1800ab4b7  mov     esi, eax
0x1800ab4b9  test    eax, eax
0x1800ab4bb  jns     short loc_1800AB4EE
0x1800ab4bd  mov     dword ptr [rsp+270h+var_250], eax
0x1800ab4c1  lea     r9, aFailedToAddKey; "Failed to add key list req to PA data: "...
0x1800ab4c8  mov     r8d, 1BFEh
0x1800ab4ce  lea     rdx, aKerbgetticketg_5; "KerbGetTicketGrantingTicketFromAsRepCal"...
0x1800ab4d5  mov     ecx, 2
0x1800ab4da  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800ab4df  mov     rcx, [rbp+140h+hMem]; hMem
0x1800ab4e3  call    KerbFreePreAuthData
0x1800ab4e8  mov     [rbp+140h+hMem], r13
0x1800ab4ec  jmp     short loc_1800AB4F3
0x1800ab4ee  bts     r15d, 1Bh
0x1800ab4f3  mov     [rbp+140h+var_70], 2
0x1800ab4fd  mov     eax, cs:dword_180140048
0x1800ab503  cmp     eax, 5
0x1800ab506  jbe     short loc_1800AB56C
0x1800ab508  mov     rdx, 400000000000h
0x1800ab512  lea     rcx, dword_180140048
0x1800ab519  call    _tlgKeywordOn
0x1800ab51e  test    al, al
0x1800ab520  jz      short loc_1800AB56C
0x1800ab522  mov     [rbp+140h+var_1C0], esi
0x1800ab525  call    cs:__imp_GetCurrentThreadId
0x1800ab52b  mov     dword ptr [rbp+140h+var_1A0.Length], eax
0x1800ab52e  mov     [rbp+140h+var_160], 1000000h
0x1800ab536  lea     rax, [rbp+140h+var_1C0]
0x1800ab53a  mov     qword ptr [rsp+270h+var_240], rax
0x1800ab53f  lea     rax, [rbp+140h+var_1A0]
0x1800ab543  mov     qword ptr [rsp+270h+var_248], rax
0x1800ab548  lea     rax, [rbp+140h+var_160]
0x1800ab54c  mov     [rsp+270h+var_250], rax
0x1800ab551  lea     r8, [rbp+140h+var_68]
0x1800ab558  lea     rdx, dword_18012C3A4
0x1800ab55f  lea     rcx, dword_180140048
0x1800ab566  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ab56b  nop
0x1800ab56c  lea     rcx, [rbp+140h+var_70]
0x1800ab573  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?KerbTraceLogger@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const KerbTraceLogger,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const KerbTraceLogger,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x1800ab578  lea     r9, aUsingTheMctick; ": using the McTicket to get a TGT..."
0x1800ab57f  mov     r8d, 1C11h
0x1800ab585  lea     rdx, aKerbgetticketg_5; "KerbGetTicketGrantingTicketFromAsRepCal"...
0x1800ab58c  mov     ecx, 8
0x1800ab591  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800ab596  mov     rax, [rbp+140h+var_E0]
0x1800ab59a  test    byte ptr [rax], 1
0x1800ab59d  jnz     loc_1800AB641
0x1800ab5a3  mov     [rsp+270h+var_1C8], r13; struct _DMSA_KEY_PACKAGE *
0x1800ab5ab  lea     rax, [rbp+140h+var_190]
0x1800ab5af  mov     [rsp+270h+var_1D0], rax; unsigned int *
0x1800ab5b7  lea     rax, [rbp+140h+var_F0]
0x1800ab5bb  mov     [rsp+270h+var_1D8], rax; struct _UNICODE_STRING *
0x1800ab5c3  lea     rax, [rbp+140h+var_18C]
0x1800ab5c7  mov     [rsp+270h+var_1E0], rax; unsigned int *
0x1800ab5cf  lea     rax, [rbp+140h+var_178]
0x1800ab5d3  mov     [rsp+270h+var_1E8], rax; struct KERB_ENCRYPTED_KDC_REPLY **
0x1800ab5db  lea     rax, [rbp+140h+var_170]
0x1800ab5df  mov     [rsp+270h+var_1F0], rax; struct KERB_KDC_REPLY **
0x1800ab5e7  mov     [rsp+270h+var_1F8], r13; union _LARGE_INTEGER *
0x1800ab5ec  mov     [rsp+270h+var_200], r13; struct _KERB_ENCRYPTION_KEY *
0x1800ab5f1  mov     [rsp+270h+var_208], r13; struct KERB_TICKET *
0x1800ab5f6  mov     [rsp+270h+var_210], r13; struct KERB_TGT_REPLY *
0x1800ab5fb  mov     rax, [rbp+140h+hMem]
0x1800ab5ff  mov     [rsp+270h+var_218], rax; struct KERB_KDC_REQUEST_preauth_data_s *
0x1800ab604  mov     [rsp+270h+var_220], r13; struct PA_S4U_X509_USER *
0x1800ab609  mov     [rsp+270h+var_228], r13; struct KERB_PA_FOR_USER *
0x1800ab60e  mov     [rsp+270h+var_230], r13; struct PKERB_AUTHORIZATION_DATA_s *
0x1800ab613  mov     dword ptr [rsp+270h+var_238], r13d; unsigned int
0x1800ab618  mov     [rsp+270h+var_240], 40810010h; unsigned int
0x1800ab620  mov     [rsp+270h+var_248], r15d; unsigned int
0x1800ab625  mov     r9, [rbp+140h+var_180]; struct _KERB_TICKET_CACHE_ENTRY *
0x1800ab629  mov     rax, [r9+20h]
0x1800ab62d  mov     [rsp+270h+var_250], rax; struct _KERB_INTERNAL_NAME *
0x1800ab632  xor     r8d, r8d; struct _KERB_PROXY_LOGON_CRED *
0x1800ab635  xor     edx, edx; struct _KERB_CREDENTIAL *
0x1800ab637  mov     rcx, rbx; struct _KERB_LOGON_SESSION *
0x1800ab63a  call    ?KerbGetTgsTicketEx@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAU_KERB_PROXY_LOGON_CRED@@PEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KERB_INTERNAL_NAME@@KKKPEAUPKERB_AUTHORIZATION_DATA_s@@PEAUKERB_PA_FOR_USER@@PEAUPA_S4U_X509_USER@@PEAUKERB_KDC_REQUEST_preauth_data_s@@PEAUKERB_TGT_REPLY@@PEAUKERB_TICKET@@PEAU_KERB_ENCRYPTION_KEY@@PEAT_LARGE_INTEGER@@PEAPEAUKERB_KDC_REPLY@@PEAPEAUKERB_ENCRYPTED_KDC_REPLY@@PEAKPEAU_UNICODE_STRING@@PEAKPEAU_DMSA_KEY_PACKAGE@@@Z; KerbGetTgsTicketEx(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_KERB_PROXY_LOGON_CRED *,_KERB_TICKET_CACHE_ENTRY *,_KERB_INTERNAL_NAME *,ulong,ulong,ulong,PKERB_AUTHORIZATION_DATA_s *,KERB_PA_FOR_USER *,PA_S4U_X509_USER *,KERB_KDC_REQUEST_preauth_data_s *,KERB_TGT_REPLY *,KERB_TICKET *,_KERB_ENCRYPTION_KEY *,_LARGE_INTEGER *,KERB_KDC_REPLY * *,KERB_ENCRYPTED_KDC_REPLY * *,ulong *,_UNICODE_STRING *,ulong *,_DMSA_KEY_PACKAGE *)
0x1800ab63f  mov     esi, eax
0x1800ab641  test    esi, esi
0x1800ab643  jns     loc_1800AB6DA
0x1800ab649  mov     dword ptr [rsp+270h+var_250], esi
0x1800ab64d  lea     r9, aFailedToRedeem; "Failed to redeem AS_REP ticket (McTicke"...
0x1800ab654  mov     r8d, 1C37h
0x1800ab65a  lea     r15, aKerbgetticketg_5; "KerbGetTicketGrantingTicketFromAsRepCal"...
0x1800ab661  mov     rdx, r15
0x1800ab664  mov     ecx, 1
  ... truncated ...
```
