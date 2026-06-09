# NtlmLogging::SspLogNtlmClientBlocked(_SSP_CONTEXT const *,_LUID const *,NtlmHelper::AvPairHelper const &,utl::pair<NtlmHelper::Blocking::Decision,NtlmHelper::Blocking::Reason> const &)

- ea: `0x180059760`
- end: `0x180059efe`
- name: `?SspLogNtlmClientBlocked@NtlmLogging@@YAXPEBU_SSP_CONTEXT@@PEBU_LUID@@AEBVAvPairHelper@NtlmHelper@@AEBU?$pair@W4Decision@Blocking@NtlmHelper@@UReason@23@@utl@@@Z`
- size: `1950`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004e098`

## callees

- `0x18000c5d0`
- `0x18000cba0`
- `0x180012fd0`
- `0x18001eaec`
- `0x18001f878`
- `0x180021acc`
- `0x18002e3e8`
- `0x18002e7a8`
- `0x18002f03c`
- `0x18002fb50`
- `0x18004c660`
- `0x18004c874`
- `0x180057bb8`
- `0x180057c9c`
- `0x180057d1c`
- `0x180057d80`
- `0x180057de8`
- `0x180057e48`
- `0x180057ecc`
- `0x180057f4c`
- `0x180058068`
- `0x180059760`
- `0x18005a2f0`
- `0x18005a318`
- `0x1800696dc`
- `0x18006d010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x1800597b7`
- `ntdll!EtwEventEnabled` at `0x1800597b7`
- `ntdll!EtwEventWrite` at `0x180059eb9`
- `ntdll!EtwEventWrite` at `0x180059eb9`
- `ntdll!RtlReleaseResource` at `0x18005991d`
- `ntdll!RtlReleaseResource` at `0x180059993`
- `ntdll!RtlReleaseResource` at `0x1800599b7`
- `ntdll!RtlReleaseResource` at `0x1800599de`
- `ntdll!RtlReleaseResource` at `0x1800599ed`
- `ntdll!RtlReleaseResource` at `0x18005991d`
- `ntdll!RtlReleaseResource` at `0x180059993`
- `ntdll!RtlReleaseResource` at `0x1800599b7`
- `ntdll!RtlReleaseResource` at `0x1800599de`
- `ntdll!RtlReleaseResource` at `0x1800599ed`
- `ntdll!RtlAcquireResourceShared` at `0x1800598ee`
- `ntdll!RtlAcquireResourceShared` at `0x1800598ee`
- `LSASRV!LsaIFreeHeap` at `0x180059ad1`
- `LSASRV!LsaIFreeHeap` at `0x180059adc`
- `LSASRV!LsaIFreeHeap` at `0x180059b2a`
- `LSASRV!LsaIFreeHeap` at `0x180059b35`
- `LSASRV!LsaIFreeHeap` at `0x180059b89`
- `LSASRV!LsaIFreeHeap` at `0x180059b94`
- `LSASRV!LsaIFreeHeap` at `0x180059c14`
- `LSASRV!LsaIFreeHeap` at `0x180059c1f`
- `LSASRV!LsaIFreeHeap` at `0x180059c69`
- `LSASRV!LsaIFreeHeap` at `0x180059c74`
- `LSASRV!LsaIFreeHeap` at `0x180059cb5`
- `LSASRV!LsaIFreeHeap` at `0x180059cc0`
- `LSASRV!LsaIFreeHeap` at `0x180059d01`
- `LSASRV!LsaIFreeHeap` at `0x180059d0c`
- `LSASRV!LsaIFreeHeap` at `0x180059d54`
- `LSASRV!LsaIFreeHeap` at `0x180059d5f`
- `LSASRV!LsaIFreeHeap` at `0x180059dbf`
- `LSASRV!LsaIFreeHeap` at `0x180059dca`
- `LSASRV!LsaIFreeHeap` at `0x180059e0f`
- `LSASRV!LsaIFreeHeap` at `0x180059e1a`
- `LSASRV!LsaIFreeHeap` at `0x180059e6b`
- `LSASRV!LsaIFreeHeap` at `0x180059e76`
- `LSASRV!LsaIFreeHeap` at `0x180059ece`
- `LSASRV!LsaIFreeHeap` at `0x180059ed9`
- `LSASRV!LsaIFreeHeap` at `0x180059ad1`
- `LSASRV!LsaIFreeHeap` at `0x180059adc`
- `LSASRV!LsaIFreeHeap` at `0x180059b2a`
- `LSASRV!LsaIFreeHeap` at `0x180059b35`
- `LSASRV!LsaIFreeHeap` at `0x180059b89`
- `LSASRV!LsaIFreeHeap` at `0x180059b94`
- `LSASRV!LsaIFreeHeap` at `0x180059c14`
- `LSASRV!LsaIFreeHeap` at `0x180059c1f`
- `LSASRV!LsaIFreeHeap` at `0x180059c69`
- `LSASRV!LsaIFreeHeap` at `0x180059c74`
- `LSASRV!LsaIFreeHeap` at `0x180059cb5`
- `LSASRV!LsaIFreeHeap` at `0x180059cc0`
- `LSASRV!LsaIFreeHeap` at `0x180059d01`
- `LSASRV!LsaIFreeHeap` at `0x180059d0c`
- `LSASRV!LsaIFreeHeap` at `0x180059d54`
- `LSASRV!LsaIFreeHeap` at `0x180059d5f`
- `LSASRV!LsaIFreeHeap` at `0x180059dbf`
- `LSASRV!LsaIFreeHeap` at `0x180059dca`
- `LSASRV!LsaIFreeHeap` at `0x180059e0f`
- `LSASRV!LsaIFreeHeap` at `0x180059e1a`
- `LSASRV!LsaIFreeHeap` at `0x180059e6b`
- `LSASRV!LsaIFreeHeap` at `0x180059e76`
- `LSASRV!LsaIFreeHeap` at `0x180059ece`
- `LSASRV!LsaIFreeHeap` at `0x180059ed9`
- `LSASRV!LsaIGetNetworkInfo` at `0x180059bc2`
- `LSASRV!LsaIGetNetworkInfo` at `0x180059bc2`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall NtlmLogging::SspLogNtlmClientBlocked(__int64 a1, void *a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax
  __int64 v9; // r8
  __int64 v10; // rbx
  __int64 ActiveLogon; // rax
  __int64 v12; // rbx
  const wchar_t *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v16; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v17[3]; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING v18; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING v19; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v20[4]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v21[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v22[32]; // [rsp+A8h] [rbp-58h] BYREF
  void *v23[5]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v24[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v25[64]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v26[8]; // [rsp+150h] [rbp+50h] BYREF
  unsigned int v27[6]; // [rsp+158h] [rbp+58h] BYREF
  _WORD v28[788]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v29[8]; // [rsp+798h] [rbp+698h] BYREF

  result = SspInitEtwLogHandle();
  if ( (int)result >= 0 )
  {
    result = EtwEventEnabled(MsvEtwLogHandle, NTLMLessBlockingPolicyDeny);
    if ( (_BYTE)result )
    {
      if ( a1 && (*(_DWORD *)(a1 + 48) & 0x4000) == 0 )
      {
        SspTelemetry::ClientImageInfo::ClientImageInfo((SspTelemetry::ClientImageInfo *)v26, LsaFunctions);
        SspTelemetry::ClientImageInfo::GetSvchostServiceTag(v26, &v15);
        NtlmLogging::EventDataHelper::EventDataHelper((NtlmLogging::EventDataHelper *)v17, 0xCu);
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v20);
        v9 = -1;
        do
          ++v9;
        while ( v28[v9] );
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          v20,
          v28,
          v9);
        if ( v20[0] == v20[1] && v27[0] == 4 )
        {
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
            v20,
            L"SYSTEM",
            6);
        }
        else
        {
          v10 = v15;
          if ( v15 )
          {
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
              v20,
              L" (",
              2);
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
              v20,
              v10);
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
              v20,
              L")",
              1);
          }
        }
        if ( !(unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(v17, v20)
          || !NtlmLogging::EventDataHelper::AddULong((NtlmLogging::EventDataHelper *)v17, v27) )
        {
          goto LABEL_19;
        }
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v21);
        if ( *(_BYTE *)(a1 + 384) )
        {
          RtlAcquireResourceShared(&NlpActiveLogonLock, 1u);
          ActiveLogon = NlpFindActiveLogon(a2);
          v12 = ActiveLogon;
          if ( ActiveLogon )
          {
            if ( !NtlmLogging::EventDataHelper::AddUnicodeString(
                    (NtlmLogging::EventDataHelper *)v17,
                    (const struct _UNICODE_STRING *)(ActiveLogon + 72))
              || !NtlmLogging::EventDataHelper::AddUnicodeString(
                    (NtlmLogging::EventDataHelper *)v17,
                    (const struct _UNICODE_STRING *)(v12 + 88)) )
            {
LABEL_17:
              RtlReleaseResource(&NlpActiveLogonLock);
LABEL_18:
              utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v21);
LABEL_19:
              utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v20);
              utl::vector<utl::basic_string_view<unsigned short,utl::char_traits<unsigned short>>,utl::allocator<utl::basic_string_view<unsigned short,utl::char_traits<unsigned short>>>>::_Uninit(v17);
              wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(&v15);
              return wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(v29);
            }
          }
          else if ( !NtlmLogging::EventDataHelper::AddBuffer((NtlmLogging::EventDataHelper *)v17, L"Unknown", 0x10u)
                 || !NtlmLogging::EventDataHelper::AddBuffer((NtlmLogging::EventDataHelper *)v17, L"Unknown", 0x10u) )
          {
            goto LABEL_17;
          }
          RtlReleaseResource(&NlpActiveLogonLock);
        }
        else if ( !NtlmLogging::EventDataHelper::AddUnicodeString(
                     (NtlmLogging::EventDataHelper *)v17,
                     (const struct _UNICODE_STRING *)(a1 + 136))
               || !NtlmLogging::EventDataHelper::AddUnicodeString(
                     (NtlmLogging::EventDataHelper *)v17,
                     (const struct _UNICODE_STRING *)(a1 + 120)) )
        {
          goto LABEL_18;
        }
        if ( !NtlmLogging::EventDataHelper::AddUnicodeString(
                (NtlmLogging::EventDataHelper *)v17,
                &NtLmGlobalUnicodeComputerNameString) )
          goto LABEL_18;
        v13 = L"Single Sign-On";
        if ( !*(_BYTE *)(a1 + 384) )
          v13 = L"Supplied Credentials";
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
          v21,
          v13,
          (-(__int64)(*(_BYTE *)(a1 + 384) != 0) & 0xFFFFFFFFFFFFFFFAuLL) + 20);
        if ( !(unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(v17, v21) )
          goto LABEL_18;
        v16 = 0;
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v22);
        v18 = 0;
        v19 = 0;
        NtlmHelper::AvPairHelper::GetTargetInfo(a3, v24);
        if ( (unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(v17, v24) )
        {
          if ( (unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(v17, v25) )
          {
            NtLmDuplicateUnicodeString(&v19, a1 + 256);
            if ( NtlmLogging::EventDataHelper::AddUnicodeString((NtlmLogging::EventDataHelper *)v17, &v19) )
            {
              if ( (int)LsaIGetNetworkInfo(&v16, &v18) < 0 )
              {
                if ( !NtlmLogging::EventDataHelper::AddNullString((NtlmLogging::EventDataHelper *)v17)
                  || !NtlmLogging::EventDataHelper::AddNullString((NtlmLogging::EventDataHelper *)v17) )
                {
                  goto LABEL_33;
                }
              }
              else
              {
                v14 = NtlmLogging::IpToString(v23, v16);
                utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
                  v22,
                  v14);
                utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v23);
                if ( !(unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(v17, v22)
                  || !NtlmLogging::EventDataHelper::AddUnicodeString((NtlmLogging::EventDataHelper *)v17, &v18) )
                {
                  goto LABEL_33;
                }
              }
              if ( NtlmLogging::EventDataHelper::AddULong(
                     (NtlmLogging::EventDataHelper *)v17,
                     (const unsigned int *)(a1 + 380)) )
              {
                NtlmLogging::FailureReasonToString(v23, *(unsigned int *)(a1 + 380));
                if ( NtlmLogging::EventDataHelper::AddBuffer(
                       (NtlmLogging::EventDataHelper *)v17,
                       v23[0],
                       2 * (__int64)v23[1] + 2)
                  && NtlmLogging::EventDataHelper::AddULong(
                       (NtlmLogging::EventDataHelper *)v17,
                       (const unsigned int *)(a4 + 8))
                  && NtlmLogging::EventDataHelper::AddBuffer(
                       (NtlmLogging::EventDataHelper *)v17,
                       *(const void **)(a4 + 16),
                       2LL * *(_QWORD *)(a4 + 24) + 2) )
                {
                  EtwEventWrite(MsvEtwLogHandle, NTLMLessBlockingPolicyDeny, (__int64)(v17[1] - v17[0]) >> 4);
                }
              }
            }
          }
        }
LABEL_33:
        NtlmHelper::AuthenticateHeader::~AuthenticateHeader((NtlmHelper::AuthenticateHeader *)v24);
        LsaIFreeHeap(v16);
        LsaIFreeHeap(v18.Buffer);
        ((void (__fastcall *)(PWSTR))LsaFunctions->FreePrivateHeap)(v19.Buffer);
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v22);
        goto LABEL_18;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180059760  push    rbp
0x180059762  push    rbx
0x180059763  push    rsi
0x180059764  push    rdi
0x180059765  push    r12
0x180059767  push    r13
0x180059769  push    r14
0x18005976b  push    r15
0x18005976d  lea     rbp, [rsp-6B8h]
0x180059775  sub     rsp, 7B8h
0x18005977c  mov     rax, cs:__security_cookie
0x180059783  xor     rax, rsp
0x180059786  mov     [rbp+6F0h+var_50], rax
0x18005978d  mov     rsi, r9
0x180059790  mov     r15, r8
0x180059793  mov     r14, rdx
0x180059796  mov     rdi, rcx
0x180059799  call    SspInitEtwLogHandle
0x18005979e  xor     r12d, r12d
0x1800597a1  test    eax, eax
0x1800597a3  js      loc_18005995B
0x1800597a9  lea     rdx, NTLMLessBlockingPolicyDeny
0x1800597b0  mov     rcx, cs:MsvEtwLogHandle
0x1800597b7  call    cs:__imp_EtwEventEnabled
0x1800597bd  test    al, al
0x1800597bf  jz      loc_18005995B
0x1800597c5  test    rdi, rdi
0x1800597c8  jz      loc_18005995B
0x1800597ce  test    dword ptr [rdi+30h], 4000h
0x1800597d5  jnz     loc_18005995B
0x1800597db  mov     rdx, cs:LsaFunctions; struct _LSA_SECPKG_FUNCTION_TABLE *
0x1800597e2  lea     rcx, [rbp+6F0h+var_6A0]; this
0x1800597e6  call    ??0ClientImageInfo@SspTelemetry@@QEAA@PEAU_LSA_SECPKG_FUNCTION_TABLE@@@Z; SspTelemetry::ClientImageInfo::ClientImageInfo(_LSA_SECPKG_FUNCTION_TABLE *)
0x1800597eb  nop
0x1800597ec  lea     rdx, [rsp+7F0h+var_7D0]
0x1800597f1  lea     rcx, [rbp+6F0h+var_6A0]
0x1800597f5  call    ?GetSvchostServiceTag@ClientImageInfo@SspTelemetry@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SspTelemetry::ClientImageInfo::GetSvchostServiceTag(void)
0x1800597fa  nop
0x1800597fb  lea     edx, [r12+0Ch]; unsigned int
0x180059800  lea     rcx, [rsp+7F0h+var_7C0]; this
0x180059805  call    ??0EventDataHelper@NtlmLogging@@QEAA@I@Z; NtlmLogging::EventDataHelper::EventDataHelper(uint)
0x18005980a  nop
0x18005980b  lea     rcx, [rsp+7F0h+var_788]
0x180059810  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180059815  nop
0x180059816  lea     rax, [rbp+6F0h+var_680]
0x18005981a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005981e  inc     r8
0x180059821  cmp     [rax+r8*2], r12w
0x180059826  jnz     short loc_18005981E
0x180059828  lea     rdx, [rbp+6F0h+var_680]
0x18005982c  lea     rcx, [rsp+7F0h+var_788]
0x180059831  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180059836  mov     rax, [rsp+7F0h+var_780]
0x18005983b  cmp     [rsp+7F0h+var_788], rax
0x180059840  jnz     short loc_180059861
0x180059842  cmp     [rbp+6F0h+var_698], 4
0x180059846  jnz     short loc_180059861
0x180059848  mov     r8d, 6
0x18005984e  lea     rdx, aSystem; "SYSTEM"
0x180059855  lea     rcx, [rsp+7F0h+var_788]
0x18005985a  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18005985f  jmp     short loc_1800598A6
0x180059861  mov     rbx, [rsp+7F0h+var_7D0]
0x180059866  test    rbx, rbx
0x180059869  jz      short loc_1800598A6
0x18005986b  mov     r8d, 2
0x180059871  lea     rdx, asc_18007659C; " ("
0x180059878  lea     rcx, [rsp+7F0h+var_788]
0x18005987d  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180059882  mov     rdx, rbx
0x180059885  lea     rcx, [rsp+7F0h+var_788]
0x18005988a  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18005988f  mov     r8d, 1
0x180059895  lea     rdx, asc_180076728; ")"
0x18005989c  lea     rcx, [rsp+7F0h+var_788]
0x1800598a1  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800598a6  lea     rdx, [rsp+7F0h+var_788]
0x1800598ab  lea     rcx, [rsp+7F0h+var_7C0]
0x1800598b0  call    ?AddUtlString@EventDataHelper@NtlmLogging@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; NtlmLogging::EventDataHelper::AddUtlString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x1800598b5  test    al, al
0x1800598b7  jz      short loc_18005992E
0x1800598b9  lea     rdx, [rbp+6F0h+var_698]; unsigned int *
0x1800598bd  lea     rcx, [rsp+7F0h+var_7C0]; this
0x1800598c2  call    ?AddULong@EventDataHelper@NtlmLogging@@QEAA_NPEBK@Z; NtlmLogging::EventDataHelper::AddULong(ulong const *)
0x1800598c7  test    al, al
0x1800598c9  jz      short loc_18005992E
0x1800598cb  lea     rcx, [rbp+6F0h+var_768]
0x1800598cf  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800598d4  nop
0x1800598d5  cmp     [rdi+180h], r12b
0x1800598dc  jz      loc_1800599F6
0x1800598e2  mov     dl, 1; Wait
0x1800598e4  lea     r13, NlpActiveLogonLock
0x1800598eb  mov     rcx, r13; Resource
0x1800598ee  call    cs:__imp_RtlAcquireResourceShared
0x1800598f4  mov     rcx, r14; void *
0x1800598f7  call    NlpFindActiveLogon
0x1800598fc  mov     rbx, rax
0x1800598ff  lea     rcx, [rsp+7F0h+var_7C0]; this
0x180059904  test    rax, rax
0x180059907  jz      loc_18005999C
0x18005990d  lea     rdx, [rax+48h]; struct _UNICODE_STRING *
0x180059911  call    ?AddUnicodeString@EventDataHelper@NtlmLogging@@QEAA_NPEBU_UNICODE_STRING@@@Z; NtlmLogging::EventDataHelper::AddUnicodeString(_UNICODE_STRING const *)
0x180059916  test    al, al
0x180059918  jnz     short loc_18005997E
0x18005991a  mov     rcx, r13; Resource
0x18005991d  call    cs:__imp_RtlReleaseResource
0x180059923  nop
0x180059924  lea     rcx, [rbp+6F0h+var_768]
0x180059928  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18005992d  nop
0x18005992e  lea     rcx, [rsp+7F0h+var_788]
0x180059933  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180059938  nop
0x180059939  lea     rcx, [rsp+7F0h+var_7C0]
0x18005993e  call    ?_Uninit@?$vector@V?$basic_string_view@GU?$char_traits@G@utl@@@utl@@V?$allocator@V?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string_view<ushort,utl::char_traits<ushort>>,utl::allocator<utl::basic_string_view<ushort,utl::char_traits<ushort>>>>::_Uninit(void)
0x180059943  nop
0x180059944  lea     rcx, [rsp+7F0h+var_7D0]
0x180059949  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROCESS_BASIC_INFORMATION@@P6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(void)
0x18005994e  nop
0x18005994f  lea     rcx, [rbp+6F0h+var_58]
0x180059956  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROCESS_BASIC_INFORMATION@@P6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(void)
0x18005995b  mov     rcx, [rbp+6F0h+var_50]
0x180059962  xor     rcx, rsp; StackCookie
0x180059965  call    __security_check_cookie
0x18005996a  add     rsp, 7B8h
0x180059971  pop     r15
0x180059973  pop     r14
0x180059975  pop     r13
0x180059977  pop     r12
0x180059979  pop     rdi
0x18005997a  pop     rsi
0x18005997b  pop     rbx
0x18005997c  pop     rbp
0x18005997d  retn
0x18005997e  lea     rdx, [rbx+58h]; struct _UNICODE_STRING *
0x180059982  lea     rcx, [rsp+7F0h+var_7C0]; this
0x180059987  call    ?AddUnicodeString@EventDataHelper@NtlmLogging@@QEAA_NPEBU_UNICODE_STRING@@@Z; NtlmLogging::EventDataHelper::AddUnicodeString(_UNICODE_STRING const *)
0x18005998c  test    al, al
0x18005998e  jnz     short loc_1800599EA
0x180059990  mov     rcx, r13; Resource
0x180059993  call    cs:__imp_RtlReleaseResource
0x180059999  nop
0x18005999a  jmp     short loc_180059924
0x18005999c  mov     ebx, 10h
0x1800599a1  mov     r8d, ebx; unsigned __int64
0x1800599a4  lea     rdx, aUnknown; "Unknown"
0x1800599ab  call    ?AddBuffer@EventDataHelper@NtlmLogging@@QEAA_NPEBX_K@Z; NtlmLogging::EventDataHelper::AddBuffer(void const *,unsigned __int64)
0x1800599b0  test    al, al
0x1800599b2  jnz     short loc_1800599C3
0x1800599b4  mov     rcx, r13; Resource
0x1800599b7  call    cs:__imp_RtlReleaseResource
0x1800599bd  nop
0x1800599be  jmp     loc_180059924
0x1800599c3  mov     r8, rbx; unsigned __int64
0x1800599c6  lea     rdx, aUnknown; "Unknown"
0x1800599cd  lea     rcx, [rsp+7F0h+var_7C0]; this
0x1800599d2  call    ?AddBuffer@EventDataHelper@NtlmLogging@@QEAA_NPEBX_K@Z; NtlmLogging::EventDataHelper::AddBuffer(void const *,unsigned __int64)
0x1800599d7  test    al, al
0x1800599d9  jnz     short loc_1800599EA
0x1800599db  mov     rcx, r13; Resource
0x1800599de  call    cs:__imp_RtlReleaseResource
0x1800599e4  nop
0x1800599e5  jmp     loc_180059924
0x1800599ea  mov     rcx, r13; Resource
0x1800599ed  call    cs:__imp_RtlReleaseResource
0x1800599f3  nop
0x1800599f4  jmp     short loc_180059A25
0x1800599f6  lea     rdx, [rdi+88h]; struct _UNICODE_STRING *
0x1800599fd  lea     rcx, [rsp+7F0h+var_7C0]; this
0x180059a02  call    ?AddUnicodeString@EventDataHelper@NtlmLogging@@QEAA_NPEBU_UNICODE_STRING@@@Z; NtlmLogging::EventDataHelper::AddUnicodeString(_UNICODE_STRING const *)
0x180059a07  test    al, al
0x180059a09  jz      loc_180059924
0x180059a0f  lea     rdx, [rdi+78h]; struct _UNICODE_STRING *
0x180059a13  lea     rcx, [rsp+7F0h+var_7C0]; this
0x180059a18  call    ?AddUnicodeString@EventDataHelper@NtlmLogging@@QEAA_NPEBU_UNICODE_STRING@@@Z; NtlmLogging::EventDataHelper::AddUnicodeString(_UNICODE_STRING const *)
0x180059a1d  test    al, al
0x180059a1f  jz      loc_180059924
0x180059a25  lea     rdx, NtLmGlobalUnicodeComputerNameString; struct _UNICODE_STRING *
0x180059a2c  lea     rcx, [rsp+7F0h+var_7C0]; this
0x180059a31  call    ?AddUnicodeString@EventDataHelper@NtlmLogging@@QEAA_NPEBU_UNICODE_STRING@@@Z; NtlmLogging::EventDataHelper::AddUnicodeString(_UNICODE_STRING const *)
0x180059a36  test    al, al
0x180059a38  jz      loc_180059924
0x180059a3e  mov     cl, [rdi+180h]
0x180059a44  mov     al, cl
0x180059a46  neg     al
0x180059a48  sbb     r8, r8
0x180059a4b  and     r8, 0FFFFFFFFFFFFFFFAh
0x180059a4f  add     r8, 14h
0x180059a53  lea     rax, aSuppliedCreden; "Supplied Credentials"
0x180059a5a  lea     rdx, aSingleSignOn; "Single Sign-On"
0x180059a61  test    cl, cl
0x180059a63  cmovz   rdx, rax
0x180059a67  lea     rcx, [rbp+6F0h+var_768]
0x180059a6b  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180059a70  lea     rdx, [rbp+6F0h+var_768]
0x180059a74  lea     rcx, [rsp+7F0h+var_7C0]
0x180059a79  call    ?AddUtlString@EventDataHelper@NtlmLogging@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; NtlmLogging::EventDataHelper::AddUtlString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180059a7e  test    al, al
0x180059a80  jz      loc_180059924
0x180059a86  mov     [rsp+7F0h+var_7C8], r12
0x180059a8b  lea     rcx, [rbp+6F0h+var_748]
0x180059a8f  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180059a94  xorps   xmm0, xmm0
0x180059a97  movups  xmmword ptr [rsp+7F0h+var_7A8.Length], xmm0
0x180059a9c  xorps   xmm1, xmm1
0x180059a9f  movups  xmmword ptr [rsp+7F0h+var_798.Length], xmm1
0x180059aa4  lea     rdx, [rbp+6F0h+var_700]
0x180059aa8  mov     rcx, r15
0x180059aab  call    ?GetTargetInfo@AvPairHelper@NtlmHelper@@QEBA?AUNtlmTargetInfo@2@XZ; NtlmHelper::AvPairHelper::GetTargetInfo(void)
0x180059ab0  lea     rdx, [rbp+6F0h+var_700]
0x180059ab4  lea     rcx, [rsp+7F0h+var_7C0]
0x180059ab9  call    ?AddUtlString@EventDataHelper@NtlmLogging@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; NtlmLogging::EventDataHelper::AddUtlString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180059abe  test    al, al
0x180059ac0  jnz     short loc_180059B09
0x180059ac2  lea     rcx, [rbp+6F0h+var_700]; this
0x180059ac6  call    ??1AuthenticateHeader@NtlmHelper@@QEAA@XZ; NtlmHelper::AuthenticateHeader::~AuthenticateHeader(void)
0x180059acb  nop
0x180059acc  mov     rcx, [rsp+7F0h+var_7C8]
0x180059ad1  call    cs:__imp_LsaIFreeHeap
0x180059ad7  mov     rcx, [rsp+7F0h+var_7A8.Buffer]
0x180059adc  call    cs:__imp_LsaIFreeHeap
0x180059ae2  mov     rax, cs:LsaFunctions
0x180059ae9  mov     rcx, [rsp+7F0h+var_798.Buffer]
0x180059aee  mov     rax, [rax+188h]
0x180059af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059afa  nop
0x180059afb  lea     rcx, [rbp+6F0h+var_748]
0x180059aff  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180059b04  jmp     loc_180059924
0x180059b09  lea     rdx, [rbp+6F0h+var_6E0]
0x180059b0d  lea     rcx, [rsp+7F0h+var_7C0]
0x180059b12  call    ?AddUtlString@EventDataHelper@NtlmLogging@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; NtlmLogging::EventDataHelper::AddUtlString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180059b17  test    al, al
0x180059b19  jnz     short loc_180059B56
0x180059b1b  lea     rcx, [rbp+6F0h+var_700]; this
0x180059b1f  call    ??1AuthenticateHeader@NtlmHelper@@QEAA@XZ; NtlmHelper::AuthenticateHeader::~AuthenticateHeader(void)
0x180059b24  nop
0x180059b25  mov     rcx, [rsp+7F0h+var_7C8]
0x180059b2a  call    cs:__imp_LsaIFreeHeap
0x180059b30  mov     rcx, [rsp+7F0h+var_7A8.Buffer]
0x180059b35  call    cs:__imp_LsaIFreeHeap
0x180059b3b  mov     rax, cs:LsaFunctions
0x180059b42  mov     rcx, [rsp+7F0h+var_798.Buffer]
0x180059b47  mov     rax, [rax+188h]
0x180059b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059b53  nop
0x180059b54  jmp     short loc_180059AFB
0x180059b56  lea     rdx, [rdi+100h]
0x180059b5d  lea     rcx, [rsp+7F0h+var_798]
0x180059b62  call    NtLmDuplicateUnicodeString
0x180059b67  lea     rdx, [rsp+7F0h+var_798]; struct _UNICODE_STRING *
0x180059b6c  lea     rcx, [rsp+7F0h+var_7C0]; this
0x180059b71  call    ?AddUnicodeString@EventDataHelper@NtlmLogging@@QEAA_NPEBU_UNICODE_STRING@@@Z; NtlmLogging::EventDataHelper::AddUnicodeString(_UNICODE_STRING const *)
0x180059b76  test    al, al
0x180059b78  jnz     short loc_180059BB8
0x180059b7a  lea     rcx, [rbp+6F0h+var_700]; this
0x180059b7e  call    ??1AuthenticateHeader@NtlmHelper@@QEAA@XZ; NtlmHelper::AuthenticateHeader::~AuthenticateHeader(void)
0x180059b83  nop
0x180059b84  mov     rcx, [rsp+7F0h+var_7C8]
0x180059b89  call    cs:__imp_LsaIFreeHeap
0x180059b8f  mov     rcx, [rsp+7F0h+var_7A8.Buffer]
0x180059b94  call    cs:__imp_LsaIFreeHeap
0x180059b9a  mov     rax, cs:LsaFunctions
0x180059ba1  mov     rcx, [rsp+7F0h+var_798.Buffer]
0x180059ba6  mov     rax, [rax+188h]
0x180059bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059bb2  nop
0x180059bb3  jmp     loc_180059AFB
0x180059bb8  lea     rdx, [rsp+7F0h+var_7A8]
0x180059bbd  lea     rcx, [rsp+7F0h+var_7C8]
0x180059bc2  call    cs:__imp_LsaIGetNetworkInfo
0x180059bc8  test    eax, eax
0x180059bca  js      loc_180059C98
0x180059bd0  mov     rdx, [rsp+7F0h+var_7C8]
0x180059bd5  lea     rcx, [rbp+6F0h+var_728]
0x180059bd9  call    ?IpToString@NtlmLogging@@YA?AV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAE@Z; NtlmLogging::IpToString(uchar * const)
0x180059bde  mov     rdx, rax
0x180059be1  lea     rcx, [rbp+6F0h+var_748]
0x180059be5  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x180059bea  lea     rcx, [rbp+6F0h+var_728]
0x180059bee  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180059bf3  lea     rdx, [rbp+6F0h+var_748]
0x180059bf7  lea     rcx, [rsp+7F0h+var_7C0]
0x180059bfc  call    ?AddUtlString@EventDataHelper@NtlmLogging@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; NtlmLogging::EventDataHelper::AddUtlString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180059c01  test    al, al
0x180059c03  jnz     short loc_180059C43
0x180059c05  lea     rcx, [rbp+6F0h+var_700]; this
0x180059c09  call    ??1AuthenticateHeader@NtlmHelper@@QEAA@XZ; NtlmHelper::AuthenticateHeader::~AuthenticateHeader(void)
0x180059c0e  nop
0x180059c0f  mov     rcx, [rsp+7F0h+var_7C8]
0x180059c14  call    cs:__imp_LsaIFreeHeap
0x180059c1a  mov     rcx, [rsp+7F0h+var_7A8.Buffer]
0x180059c1f  call    cs:__imp_LsaIFreeHeap
0x180059c25  mov     rax, cs:LsaFunctions
0x180059c2c  mov     rcx, [rsp+7F0h+var_798.Buffer]
0x180059c31  mov     rax, [rax+188h]
0x180059c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059c3d  nop
  ... truncated ...
```
