# RegistrationKeyHelper::CreateAik(DSREG_AIK_TYPE,ushort const *,ushort const *,ushort const *,uchar * *,ulong *)

- ea: `0x18007437c`
- end: `0x1800747b6`
- name: `?CreateAik@RegistrationKeyHelper@@SAJW4DSREG_AIK_TYPE@@PEBG11PEAPEAEPEAK@Z`
- size: `1082`
- prototype: `static int __high(enum DSREG_AIK_TYPE, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation`

## callers

- `0x180056418`
- `0x1800b651c`

## callees

- `0x1800012a4`
- `0x180001e6c`
- `0x180005ba0`
- `0x1800084f4`
- `0x180008530`
- `0x180009780`
- `0x18000bac0`
- `0x180012948`
- `0x1800204f0`
- `0x1800307c4`
- `0x180031f44`
- `0x1800334e0`
- `0x18003789c`
- `0x18003c944`
- `0x180044300`
- `0x180055174`
- `0x18005b3c0`
- `0x180067c20`
- `0x18007437c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180074718`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180074718`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800746ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800746ce`
- `popkeycli!NgcCreateTokenBindingAik` at `0x180074636`
- `popkeycli!NgcCreateTokenBindingAik` at `0x180074636`

## string_xrefs

- `0x18007445e`: `RegistrationKeyHelper::CreateAik`
- `0x180074478`: `RegistrationKeyHelper::CreateAik`
- `0x1800744a1`: `RegistrationKeyHelper::CreateAik`
- `0x1800744ce`: `RegistrationKeyHelper::CreateAik`
- `0x1800744ff`: `RegistrationKeyHelper::CreateAik`
- `0x180074537`: `RegistrationKeyHelper::CreateAik`
- `0x180074580`: `RegistrationKeyHelper::CreateAik`
- `0x1800745ee`: `RegistrationKeyHelper::CreateAik`
- `0x180074664`: `RegistrationKeyHelper::CreateAik`
- `0x180074696`: `RegistrationKeyHelper::CreateAik`
- `0x1800746fa`: `RegistrationKeyHelper::CreateAik`
- `0x180074605`: `%s: Calling NgcCreateTokenBindingAik with key type: %d (%s), IDP domain: %s, Tenant-based ID: %s, User SID: %s...`
- `0x1800746a2`: `%s: Token binding AIK (type %s) successfully created. IDP domain: %s, Tenant-based ID: %s, User SID: %s.`
- `0x180074670`: `%s: Token binding AIK (type %s) couldn't be created. NgcCreateTokenBindingAik failed with error code 0x%08x. IDP domain: %s, Tenant-based ID: %s, User SID: %s.`

## pseudocode

```c
__int64 __fastcall RegistrationKeyHelper::CreateAik(
        unsigned int a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        HLOCAL *a5,
        _DWORD *a6)
{
  unsigned __int16 *v6; // rdi
  unsigned int v10; // ebx
  const unsigned __int16 *v11; // rdx
  unsigned int v12; // esi
  int v13; // eax
  unsigned __int16 *v14; // rbx
  unsigned __int16 *v15; // r15
  __int64 AikTypeName; // rax
  int v17; // eax
  const unsigned __int16 *v18; // rdx
  __int64 v19; // rdi
  __int64 v20; // r9
  __int64 *v22; // [rsp+20h] [rbp-79h]
  unsigned __int16 *v23; // [rsp+40h] [rbp-59h] BYREF
  __int64 v24; // [rsp+48h] [rbp-51h] BYREF
  int v25; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int16 *v26; // [rsp+58h] [rbp-41h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-39h] BYREF
  int v28; // [rsp+68h] [rbp-31h] BYREF
  char v29; // [rsp+6Ch] [rbp-2Dh]
  _BYTE v30[16]; // [rsp+70h] [rbp-29h] BYREF
  GUID ActivityId; // [rsp+80h] [rbp-19h] BYREF

  v6 = 0;
  v23 = 0;
  v28 = 0;
  v29 = 0;
  v26 = a4;
  v25 = 0;
  hMem = 0;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v28);
  if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x200000000000LL) )
  {
    v24 = 0x1000000;
    if ( v29 )
      _tlgGuidIsZero(&ActivityId);
    v22 = &v24;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (__int64)&dword_18013D150,
      (__int64)byte_18012A1EB);
  }
  if ( (unsigned int)IsEmptyString(a3) )
  {
    v10 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null or empty.", L"RegistrationKeyHelper::CreateAik", L"tenantId");
    v11 = L"tenantId";
LABEL_8:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationKeyHelper::CreateAik", v11);
    goto LABEL_31;
  }
  if ( (unsigned int)IsEmptyString(a2) )
  {
    v10 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null or empty.", L"RegistrationKeyHelper::CreateAik", L"deviceKeyId");
    v11 = L"deviceKeyId";
    goto LABEL_8;
  }
  if ( !a5 )
  {
    v10 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistrationKeyHelper::CreateAik", L"publicKey");
    v11 = L"publicKey";
    goto LABEL_8;
  }
  *a5 = 0;
  if ( !a6 )
  {
    v10 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistrationKeyHelper::CreateAik", L"publicKeySize");
    v11 = L"publicKeySize";
    goto LABEL_8;
  }
  *a6 = 0;
  if ( a1 )
  {
    if ( a1 == 1 )
    {
      v12 = 1;
    }
    else
    {
      if ( a1 != 2 )
      {
        Logger::TraceError(L"%s: Unknown aikType value: %d", L"RegistrationKeyHelper::CreateAik", a1);
        v10 = -2147024809;
        goto LABEL_31;
      }
      v12 = 2;
    }
  }
  else
  {
    v12 = 0;
  }
  v13 = StringAppend(&v23, a3);
  v10 = v13;
  if ( v13 < 0
    || (v13 = StringAppend(&v23, L"_"), v10 = v13, v13 < 0)
    || (v13 = StringAppend(&v23, a2), v10 = v13, v13 < 0) )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"RegistrationKeyHelper::CreateAik",
      L"StringAppend",
      (unsigned int)v13,
      v22);
    v6 = v23;
  }
  else
  {
    v14 = v26;
    v15 = L"<NULL>";
    if ( v26 )
      v15 = v26;
    AikTypeName = GetAikTypeName(a1);
    v6 = v23;
    v24 = AikTypeName;
    Logger::TraceInformation(
      L"%s: Calling NgcCreateTokenBindingAik with key type: %d (%s), IDP domain: %s, Tenant-based ID: %s, User SID: %s...",
      L"RegistrationKeyHelper::CreateAik",
      v12,
      AikTypeName,
      L"login.windows.net",
      v23,
      v15);
    v17 = NgcCreateTokenBindingAik(v12, L"login.windows.net", v6, v14, &hMem, &v25);
    v10 = v17;
    if ( v17 >= 0 )
    {
      Logger::WriteNgcCreateTokenBindingAikSuccessEvent(v12, v18, v6, v26);
      Logger::TraceInformation(
        L"%s: Token binding AIK (type %s) successfully created. IDP domain: %s, Tenant-based ID: %s, User SID: %s.",
        L"RegistrationKeyHelper::CreateAik",
        v24,
        L"login.windows.net",
        v6,
        v15);
      *a5 = hMem;
      *a6 = v25;
      hMem = 0;
    }
    else
    {
      Logger::WriteNgcCreateTokenBindingAikFailureEvent(v12, v18, v6, v26, v17);
      Logger::TraceWarning(
        (wchar_t *)L"%s: Token binding AIK (type %s) couldn't be created. NgcCreateTokenBindingAik failed with error code "
                    "0x%08x. IDP domain: %s, Tenant-based ID: %s, User SID: %s.",
        L"RegistrationKeyHelper::CreateAik",
        v24,
        v10,
        L"login.windows.net",
        v6,
        v15);
    }
  }
LABEL_31:
  LocalFree(hMem);
  SafeFree(v6);
  v19 = GetAikTypeName(a1);
  Logger::TraceVerbose(
    (wchar_t *)L"%s - hr: 0x%08x. %s: %s.",
    L"RegistrationKeyHelper::CreateAik",
    v10,
    L"aikType",
    v19);
  if ( v29 )
    EventActivityIdControl(4u, &ActivityId);
  v28 = 2;
  if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x200000000000LL) )
  {
    v24 = v19;
    LODWORD(v23) = v10;
    v26 = (unsigned __int16 *)0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (__int64)&dword_18013D150,
      (__int64)&byte_18012A21F,
      (__int64)v30,
      v20,
      (__int64)&v26,
      (__int64)&v23,
      &v24);
  }
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>((__int64)&v28);
  return v10;
}

```

## disassembly

```asm
0x18007437c  push    rbp
0x18007437e  push    rbx
0x18007437f  push    rsi
0x180074380  push    rdi
0x180074381  push    r12
0x180074383  push    r13
0x180074385  push    r14
0x180074387  push    r15
0x180074389  lea     rbp, [rsp-0Fh]
0x18007438e  sub     rsp, 0A8h
0x180074395  mov     rax, cs:__security_cookie
0x18007439c  xor     rax, rsp
0x18007439f  mov     [rbp+47h+var_50], rax
0x1800743a3  mov     r12, [rbp+47h+arg_20]
0x1800743a7  xor     edi, edi
0x1800743a9  mov     r13, [rbp+47h+arg_28]
0x1800743ad  mov     r14d, ecx
0x1800743b0  lea     rcx, [rbp+47h+var_78]
0x1800743b4  mov     [rbp+47h+var_A0], rdi
0x1800743b8  mov     [rbp+47h+var_78], edi
0x1800743bb  mov     rbx, r8
0x1800743be  mov     [rbp+47h+var_74], dil
0x1800743c2  mov     r15, rdx
0x1800743c5  mov     [rbp+47h+var_88], r9
0x1800743c9  mov     [rbp+47h+var_90], 0
0x1800743d0  mov     [rbp+47h+hMem], 0
0x1800743d8  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hcdjTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800743dd  mov     eax, cs:dword_18013D150
0x1800743e3  cmp     eax, 5
0x1800743e6  jbe     short loc_180074446
0x1800743e8  mov     rdx, 200000000000h
0x1800743f2  lea     rcx, dword_18013D150
0x1800743f9  call    _tlgKeywordOn
0x1800743fe  test    al, al
0x180074400  jz      short loc_180074446
0x180074402  mov     [rbp+47h+var_98], 1000000h
0x18007440a  cmp     [rbp+47h+var_74], dil
0x18007440e  jz      short loc_180074423
0x180074410  lea     rcx, [rbp+47h+ActivityId]; struct _GUID *
0x180074414  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180074419  test    al, al
0x18007441b  jnz     short loc_180074423
0x18007441d  lea     r9, [rbp+47h+ActivityId]
0x180074421  jmp     short loc_180074426
0x180074423  xor     r9d, r9d
0x180074426  lea     rax, [rbp+47h+var_98]
0x18007442a  lea     r8, [rbp+47h+var_70]
0x18007442e  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180074433  lea     rdx, byte_18012A1EB
0x18007443a  lea     rcx, dword_18013D150
0x180074441  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x180074446  mov     rcx, rbx; unsigned __int16 *
0x180074449  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18007444e  test    eax, eax
0x180074450  jz      short loc_180074489
0x180074452  lea     r8, aTenantid_1; "tenantId"
0x180074459  mov     ebx, 80070057h
0x18007445e  lea     rdx, aRegistrationke_11; "RegistrationKeyHelper::CreateAik"
0x180074465  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null or empty."
0x18007446c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180074471  lea     rdx, aTenantid_1; "tenantId"
0x180074478  lea     rcx, aRegistrationke_11; "RegistrationKeyHelper::CreateAik"
0x18007447f  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180074484  jmp     loc_1800746CA
0x180074489  mov     rcx, r15; unsigned __int16 *
0x18007448c  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180074491  test    eax, eax
0x180074493  jz      short loc_1800744BD
0x180074495  lea     r8, aDevicekeyid; "deviceKeyId"
0x18007449c  mov     ebx, 80070057h
0x1800744a1  lea     rdx, aRegistrationke_11; "RegistrationKeyHelper::CreateAik"
0x1800744a8  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null or empty."
0x1800744af  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800744b4  lea     rdx, aDevicekeyid; "deviceKeyId"
0x1800744bb  jmp     short loc_180074478
0x1800744bd  test    r12, r12
0x1800744c0  jnz     short loc_1800744EA
0x1800744c2  lea     r8, aPublickey; "publicKey"
0x1800744c9  mov     ebx, 80070057h
0x1800744ce  lea     rdx, aRegistrationke_11; "RegistrationKeyHelper::CreateAik"
0x1800744d5  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800744dc  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800744e1  lea     rdx, aPublickey; "publicKey"
0x1800744e8  jmp     short loc_180074478
0x1800744ea  mov     [r12], rdi
0x1800744ee  test    r13, r13
0x1800744f1  jnz     short loc_18007451E
0x1800744f3  lea     r8, aPublickeysize; "publicKeySize"
0x1800744fa  mov     ebx, 80070057h
0x1800744ff  lea     rdx, aRegistrationke_11; "RegistrationKeyHelper::CreateAik"
0x180074506  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18007450d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180074512  lea     rdx, aPublickeysize; "publicKeySize"
0x180074519  jmp     loc_180074478
0x18007451e  mov     [r13+0], edi
0x180074522  mov     ecx, r14d
0x180074525  test    r14d, r14d
0x180074528  jz      short loc_180074562
0x18007452a  sub     ecx, 1
0x18007452d  jz      short loc_18007455B
0x18007452f  cmp     ecx, 1
0x180074532  jz      short loc_180074554
0x180074534  mov     r8d, r14d
0x180074537  lea     rdx, aRegistrationke_11; "RegistrationKeyHelper::CreateAik"
0x18007453e  lea     rcx, aSUnknownAiktyp; "%s: Unknown aikType value: %d"
0x180074545  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007454a  mov     ebx, 80070057h
0x18007454f  jmp     loc_1800746CA
0x180074554  mov     esi, 2
0x180074559  jmp     short loc_180074564
0x18007455b  mov     esi, 1
0x180074560  jmp     short loc_180074564
0x180074562  xor     esi, esi
0x180074564  mov     rdx, rbx; unsigned __int16 *
0x180074567  lea     rcx, [rbp+47h+var_A0]; unsigned __int16 **
0x18007456b  call    ?StringAppend@@YAJPEAPEAGPEBG@Z; StringAppend(ushort * *,ushort const *)
0x180074570  mov     ebx, eax
0x180074572  test    eax, eax
0x180074574  jns     short loc_18007459C
0x180074576  mov     r9d, eax
0x180074579  lea     r8, aStringappend; "StringAppend"
0x180074580  lea     rdx, aRegistrationke_11; "RegistrationKeyHelper::CreateAik"
0x180074587  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18007458e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180074593  mov     rdi, [rbp+47h+var_A0]
0x180074597  jmp     loc_1800746CA
0x18007459c  lea     rdx, asc_1800F0FF4; "_"
0x1800745a3  lea     rcx, [rbp+47h+var_A0]; unsigned __int16 **
0x1800745a7  call    ?StringAppend@@YAJPEAPEAGPEBG@Z; StringAppend(ushort * *,ushort const *)
0x1800745ac  mov     ebx, eax
0x1800745ae  test    eax, eax
0x1800745b0  js      short loc_180074576
0x1800745b2  mov     rdx, r15; unsigned __int16 *
0x1800745b5  lea     rcx, [rbp+47h+var_A0]; unsigned __int16 **
0x1800745b9  call    ?StringAppend@@YAJPEAPEAGPEBG@Z; StringAppend(ushort * *,ushort const *)
0x1800745be  mov     ebx, eax
0x1800745c0  test    eax, eax
0x1800745c2  js      short loc_180074576
0x1800745c4  mov     rbx, [rbp+47h+var_88]
0x1800745c8  lea     r15, aNull_2; "<NULL>"
0x1800745cf  test    rbx, rbx
0x1800745d2  mov     ecx, r14d
0x1800745d5  cmovnz  r15, rbx
0x1800745d9  call    GetAikTypeName
0x1800745de  mov     rdi, [rbp+47h+var_A0]
0x1800745e2  lea     rcx, aLoginWindowsNe; "login.windows.net"
0x1800745e9  mov     [rsp+0E0h+var_B0], r15
0x1800745ee  lea     rdx, aRegistrationke_11; "RegistrationKeyHelper::CreateAik"
0x1800745f5  mov     [rsp+0E0h+var_B8], rdi
0x1800745fa  mov     r9, rax
0x1800745fd  mov     qword ptr [rsp+0E0h+var_C0], rcx
0x180074602  mov     r8d, esi
0x180074605  lea     rcx, aSCallingNgccre; "%s: Calling NgcCreateTokenBindingAik wi"...
0x18007460c  mov     [rbp+47h+var_98], rax
0x180074610  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180074615  lea     rax, [rbp+47h+var_90]
0x180074619  mov     r9, rbx
0x18007461c  mov     [rsp+0E0h+var_B8], rax
0x180074621  lea     rdx, aLoginWindowsNe; "login.windows.net"
0x180074628  lea     rax, [rbp+47h+hMem]
0x18007462c  mov     r8, rdi
0x18007462f  mov     ecx, esi
0x180074631  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180074636  call    cs:__imp_NgcCreateTokenBindingAik
0x18007463c  mov     r9, [rbp+47h+var_88]; unsigned __int16 *
0x180074640  mov     r8, rdi; unsigned __int16 *
0x180074643  mov     ebx, eax
0x180074645  mov     ecx, esi; unsigned int
0x180074647  test    eax, eax
0x180074649  jns     short loc_180074686
0x18007464b  mov     [rsp+0E0h+var_C0], eax; int
0x18007464f  call    ?WriteNgcCreateTokenBindingAikFailureEvent@Logger@@SAJKPEBG00J@Z; Logger::WriteNgcCreateTokenBindingAikFailureEvent(ulong,ushort const *,ushort const *,ushort const *,long)
0x180074654  mov     r8, [rbp+47h+var_98]
0x180074658  lea     rax, aLoginWindowsNe; "login.windows.net"
0x18007465f  mov     [rsp+0E0h+var_B0], r15
0x180074664  lea     rdx, aRegistrationke_11; "RegistrationKeyHelper::CreateAik"
0x18007466b  mov     [rsp+0E0h+var_B8], rdi
0x180074670  lea     rcx, aSTokenBindingA_1; "%s: Token binding AIK (type %s) couldn'"...
0x180074677  mov     r9d, ebx
0x18007467a  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18007467f  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180074684  jmp     short loc_1800746CA
0x180074686  call    ?WriteNgcCreateTokenBindingAikSuccessEvent@Logger@@SAJKPEBG00@Z; Logger::WriteNgcCreateTokenBindingAikSuccessEvent(ulong,ushort const *,ushort const *,ushort const *)
0x18007468b  mov     r8, [rbp+47h+var_98]
0x18007468f  lea     r9, aLoginWindowsNe; "login.windows.net"
0x180074696  lea     rdx, aRegistrationke_11; "RegistrationKeyHelper::CreateAik"
0x18007469d  mov     [rsp+0E0h+var_B8], r15
0x1800746a2  lea     rcx, aSTokenBindingA_7; "%s: Token binding AIK (type %s) success"...
0x1800746a9  mov     qword ptr [rsp+0E0h+var_C0], rdi
0x1800746ae  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800746b3  mov     rax, [rbp+47h+hMem]
0x1800746b7  mov     [r12], rax
0x1800746bb  mov     eax, [rbp+47h+var_90]
0x1800746be  mov     [r13+0], eax
0x1800746c2  mov     [rbp+47h+hMem], 0
0x1800746ca  mov     rcx, [rbp+47h+hMem]; hMem
0x1800746ce  call    cs:__imp_LocalFree
0x1800746d4  mov     rcx, rdi; lpMem
0x1800746d7  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800746dc  mov     ecx, r14d
0x1800746df  call    GetAikTypeName
0x1800746e4  lea     rcx, aSHr0x08xSS; "%s - hr: 0x%08x. %s: %s."
0x1800746eb  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800746f0  lea     r9, aAiktype; "aikType"
0x1800746f7  mov     r8d, ebx
0x1800746fa  lea     rdx, aRegistrationke_11; "RegistrationKeyHelper::CreateAik"
0x180074701  mov     rdi, rax
0x180074704  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180074709  cmp     [rbp+47h+var_74], 0
0x18007470d  jz      short loc_18007471E
0x18007470f  lea     rdx, [rbp+47h+ActivityId]; ActivityId
0x180074713  mov     ecx, 4; ControlCode
0x180074718  call    cs:__imp_EventActivityIdControl
0x18007471e  mov     eax, cs:dword_18013D150
0x180074724  mov     [rbp+47h+var_78], 2
0x18007472b  cmp     eax, 5
0x18007472e  jbe     short loc_18007478B
0x180074730  mov     rdx, 200000000000h
0x18007473a  lea     rcx, dword_18013D150
0x180074741  call    _tlgKeywordOn
0x180074746  test    al, al
0x180074748  jz      short loc_18007478B
0x18007474a  lea     rax, [rbp+47h+var_98]
0x18007474e  mov     [rbp+47h+var_98], rdi
0x180074752  mov     [rsp+0E0h+var_B0], rax
0x180074757  lea     r8, [rbp+47h+var_70]
0x18007475b  lea     rax, [rbp+47h+var_A0]
0x18007475f  mov     dword ptr [rbp+47h+var_A0], ebx
0x180074762  mov     [rsp+0E0h+var_B8], rax
0x180074767  lea     rdx, byte_18012A21F
0x18007476e  lea     rax, [rbp+47h+var_88]
0x180074772  mov     [rbp+47h+var_88], 1000000h
0x18007477a  lea     rcx, dword_18013D150
0x180074781  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180074786  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18007478b  lea     rcx, [rbp+47h+var_78]
0x18007478f  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hcdjTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(void)
0x180074794  mov     eax, ebx
0x180074796  mov     rcx, [rbp+47h+var_50]
0x18007479a  xor     rcx, rsp; StackCookie
0x18007479d  call    __security_check_cookie
0x1800747a2  add     rsp, 0A8h
0x1800747a9  pop     r15
0x1800747ab  pop     r14
0x1800747ad  pop     r13
0x1800747af  pop     r12
0x1800747b1  pop     rdi
0x1800747b2  pop     rsi
0x1800747b3  pop     rbx
0x1800747b4  pop     rbp
0x1800747b5  retn
```
