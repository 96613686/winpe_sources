# FeedbackHubEscalateInternal(_GUID,int)

- ea: `0x18007b454`
- end: `0x18007b715`
- name: `?FeedbackHubEscalateInternal@@YAJU_GUID@@H@Z`
- size: `705`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180029398`
- `0x18007b720`

## callees

- `0x180025070`
- `0x180025890`
- `0x18004fbc0`
- `0x18007b388`
- `0x18007b454`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b6f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b6f7`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18007b474`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18007b474`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007b650`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007b6d8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007b650`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007b6d8`

## string_xrefs

- `0x18007b51a`: `stableid\RDPDiagnosticsStop\complete`
- `0x18007b521`: `stableid\RDPDiagnosticsStart\complete`
- `0x18007b54e`: `We tried to start, but we're already running? what?`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FeedbackHubEscalateInternal(struct _GUID *a1, int a2)
{
  HRESULT v4; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v8; // rcx
  const wchar_t *v9; // r8
  unsigned int v10; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  const char *v13; // [rsp+50h] [rbp-29h] BYREF
  unsigned int v14; // [rsp+58h] [rbp-21h] BYREF
  LPOLESTR lpsz[3]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v16; // [rsp+78h] [rbp-1h] BYREF
  int v17; // [rsp+80h] [rbp+7h]
  const wchar_t *v18; // [rsp+88h] [rbp+Fh]
  LPOLESTR v19; // [rsp+90h] [rbp+17h]
  const wchar_t *v20; // [rsp+98h] [rbp+1Fh]
  const wchar_t *v21; // [rsp+A0h] [rbp+27h]

  lpsz[0] = 0;
  v4 = StringFromCLSID(a1, lpsz);
  if ( v4 >= 0 )
  {
    lpsz[2] = L"_collectweretwlogs";
    lpsz[1] = L"true";
    v20 = L"_collectweretwlogs";
    v21 = L"_instanceid";
    v18 = L"true";
    v19 = lpsz[0];
    v8 = 2 - (unsigned int)(a2 != 0);
    v9 = L"stableid\\RDPDiagnosticsStart\\complete";
    if ( !a2 )
      v9 = L"stableid\\RDPDiagnosticsStop\\complete";
    v16 = 0;
    v17 = 0;
    if ( g_EscalationStatus && a2 )
    {
      if ( (unsigned int)dword_1800DA020 > 2 )
      {
        v13 = "We tried to start, but we're already running? what?";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v8,
          (unsigned __int8 *)&byte_1800C757F,
          (__int64)v9,
          a2 == 0,
          (const unsigned __int16 **)&v13);
      }
      goto LABEL_24;
    }
    v10 = Microsoft::Diagnostics::UtcApiWrapper::EscalateScenarioEx(v8, v9);
    if ( (v10 & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_1800DA020 > 2 )
      {
        v14 = v10;
        v13 = "Did not start escalation of logs";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v10,
          (unsigned __int8 *)byte_1800C7559,
          v11,
          v12,
          (const unsigned __int16 **)&v13,
          (__int64)&v14);
      }
    }
    else
    {
      if ( g_EscalationStatus )
      {
        if ( a2 )
        {
LABEL_24:
          CoTaskMemFree(lpsz[0]);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v16);
          return 0;
        }
      }
      else if ( a2 )
      {
        if ( (unsigned int)dword_1800DA020 > 4 )
        {
          v13 = "Successfully started collection";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v10,
            (unsigned __int8 *)qword_1800C75A0,
            v11,
            v12,
            (const unsigned __int16 **)&v13);
        }
        g_EscalationStatus = 1;
        xmmword_1800DADB0 = (__int128)*a1;
        qword_1800DADA8 = GetTickCount64();
        goto LABEL_24;
      }
      if ( (unsigned int)dword_1800DA020 > 4 )
      {
        v13 = "Successfully stopped collection";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v10,
          (unsigned __int8 *)qword_1800C7538,
          v11,
          v12,
          (const unsigned __int16 **)&v13);
      }
    }
    if ( !a2 )
    {
      g_EscalationStatus = 0;
      qword_1800DADA0 = GetTickCount64();
      xmmword_1800DADB0 = 0u;
    }
    goto LABEL_24;
  }
  if ( (unsigned int)dword_1800DA020 > 2 )
  {
    v14 = v4;
    v13 = "Failed to convert activityid";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)dword_1800DA020,
      (unsigned __int8 *)byte_1800C75C1,
      v5,
      v6,
      (const unsigned __int16 **)&v13,
      (__int64)&v14);
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18007b454  push    rbp
0x18007b456  push    rbx
0x18007b457  push    rsi
0x18007b458  push    rdi
0x18007b459  lea     rbp, [rsp-3Fh]
0x18007b45e  sub     rsp, 0B8h
0x18007b465  mov     edi, edx
0x18007b467  mov     rbx, rcx
0x18007b46a  xor     esi, esi
0x18007b46c  mov     [rbp+57h+lpsz], rsi
0x18007b470  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x18007b474  call    cs:__imp_StringFromCLSID
0x18007b47a  test    eax, eax
0x18007b47c  jns     short loc_18007B4BF
0x18007b47e  mov     ecx, cs:dword_1800DA020
0x18007b484  cmp     ecx, 2
0x18007b487  jbe     short loc_18007B4B5
0x18007b489  mov     [rbp+57h+var_78], eax
0x18007b48c  lea     rax, aFailedToConver_0; "Failed to convert activityid"
0x18007b493  mov     [rbp+57h+var_80], rax
0x18007b497  lea     rax, [rbp+57h+var_78]
0x18007b49b  mov     [rsp+0D0h+var_A8], rax
0x18007b4a0  lea     rax, [rbp+57h+var_80]
0x18007b4a4  mov     [rsp+0D0h+var_B0], rax
0x18007b4a9  lea     rdx, byte_1800C75C1
0x18007b4b0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007b4b5  mov     eax, 80004005h
0x18007b4ba  jmp     loc_18007B709
0x18007b4bf  lea     rax, aCollectweretwl; "_collectweretwlogs"
0x18007b4c6  mov     [rbp+57h+var_60], rax
0x18007b4ca  lea     rcx, aTrue; "true"
0x18007b4d1  mov     [rbp+57h+var_68], rcx
0x18007b4d5  mov     [rbp+57h+var_38], rax
0x18007b4d9  lea     rax, aInstanceid; "_instanceid"
0x18007b4e0  mov     [rbp+57h+var_30], rax
0x18007b4e4  mov     [rbp+57h+var_48], rcx
0x18007b4e8  mov     rax, [rbp+57h+lpsz]
0x18007b4ec  mov     [rbp+57h+var_40], rax
0x18007b4f0  mov     eax, edi
0x18007b4f2  neg     eax
0x18007b4f4  sbb     ecx, ecx
0x18007b4f6  add     ecx, 2
0x18007b4f9  lea     rax, [rbp+57h+var_48]
0x18007b4fd  lea     rdx, [rbp+57h+var_68]
0x18007b501  test    edi, edi
0x18007b503  cmovnz  rax, rdx
0x18007b507  lea     rdx, [rbp+57h+var_38]
0x18007b50b  lea     r8, [rbp+57h+var_60]
0x18007b50f  cmovnz  rdx, r8
0x18007b513  mov     r9d, esi
0x18007b516  setz    r9b
0x18007b51a  lea     r10, aStableidRdpdia; "stableid\\RDPDiagnosticsStop\\complete"
0x18007b521  lea     r8, aStableidRdpdia_0; "stableid\\RDPDiagnosticsStart\\complete"
0x18007b528  cmovz   r8, r10
0x18007b52c  mov     [rbp+57h+var_58], rsi
0x18007b530  mov     [rbp+57h+var_50], esi
0x18007b533  cmp     cs:?g_EscalationStatus@@3UESCALATION_STATUS@@A, esi; ESCALATION_STATUS g_EscalationStatus
0x18007b539  jz      short loc_18007B573
0x18007b53b  test    edi, edi
0x18007b53d  jz      short loc_18007B573
0x18007b53f  mov     eax, cs:dword_1800DA020
0x18007b545  cmp     eax, 2
0x18007b548  jbe     loc_18007B6F3
0x18007b54e  lea     rax, aWeTriedToStart; "We tried to start, but we're already ru"...
0x18007b555  mov     [rbp+57h+var_80], rax
0x18007b559  lea     rax, [rbp+57h+var_80]
0x18007b55d  mov     [rsp+0D0h+var_B0], rax
0x18007b562  lea     rdx, byte_1800C757F
0x18007b569  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18007b56e  jmp     loc_18007B6F3
0x18007b573  lea     r10, [rbp+57h+var_58]
0x18007b577  mov     [rsp+0D0h+var_88], r10
0x18007b57c  mov     [rsp+0D0h+var_90], rax
0x18007b581  mov     [rsp+0D0h+var_98], rdx
0x18007b586  mov     [rsp+0D0h+var_A0], ecx
0x18007b58a  mov     dword ptr [rsp+0D0h+var_A8], r9d
0x18007b58f  mov     rdx, r8
0x18007b592  call    ?EscalateScenarioEx@UtcApiWrapper@Diagnostics@Microsoft@@QEAAJPEBG0HHW4__MIDL_UtcApiStructures_0004@@KPEAPEBG2AEAVAutoEscalationResultsList@123@@Z; Microsoft::Diagnostics::UtcApiWrapper::EscalateScenarioEx(ushort const *,ushort const *,int,int,__MIDL_UtcApiStructures_0004,ulong,ushort const * *,ushort const * *,Microsoft::Diagnostics::UtcApiWrapper::AutoEscalationResultsList &)
0x18007b597  mov     ecx, eax
0x18007b599  test    eax, eax
0x18007b59b  js      loc_18007B697
0x18007b5a1  cmp     cs:?g_EscalationStatus@@3UESCALATION_STATUS@@A, esi; ESCALATION_STATUS g_EscalationStatus
0x18007b5a7  jnz     loc_18007B662
0x18007b5ad  test    edi, edi
0x18007b5af  jz      loc_18007B66A
0x18007b5b5  mov     eax, cs:dword_1800DA020
0x18007b5bb  cmp     eax, 4
0x18007b5be  jbe     short loc_18007B5E0
0x18007b5c0  lea     rax, aSuccessfullySt_0; "Successfully started collection"
0x18007b5c7  mov     [rbp+57h+var_80], rax
0x18007b5cb  lea     rax, [rbp+57h+var_80]
0x18007b5cf  mov     [rsp+0D0h+var_B0], rax
0x18007b5d4  lea     rdx, qword_1800C75A0
0x18007b5db  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18007b5e0  mov     cs:?g_EscalationStatus@@3UESCALATION_STATUS@@A, 1; ESCALATION_STATUS g_EscalationStatus
0x18007b5ea  mov     eax, [rbx]
0x18007b5ec  mov     dword ptr cs:xmmword_1800DADB0, eax
0x18007b5f2  movzx   eax, word ptr [rbx+4]
0x18007b5f6  mov     word ptr cs:xmmword_1800DADB0+4, ax
0x18007b5fd  movzx   eax, word ptr [rbx+6]
0x18007b601  mov     word ptr cs:xmmword_1800DADB0+6, ax
0x18007b608  mov     al, [rbx+8]
0x18007b60b  mov     byte ptr cs:xmmword_1800DADB0+8, al
0x18007b611  mov     al, [rbx+9]
0x18007b614  mov     byte ptr cs:xmmword_1800DADB0+9, al
0x18007b61a  mov     al, [rbx+0Ah]
0x18007b61d  mov     byte ptr cs:xmmword_1800DADB0+0Ah, al
0x18007b623  mov     al, [rbx+0Bh]
0x18007b626  mov     byte ptr cs:xmmword_1800DADB0+0Bh, al
0x18007b62c  mov     al, [rbx+0Ch]
0x18007b62f  mov     byte ptr cs:xmmword_1800DADB0+0Ch, al
0x18007b635  mov     al, [rbx+0Dh]
0x18007b638  mov     byte ptr cs:xmmword_1800DADB0+0Dh, al
0x18007b63e  mov     al, [rbx+0Eh]
0x18007b641  mov     byte ptr cs:xmmword_1800DADB0+0Eh, al
0x18007b647  mov     al, [rbx+0Fh]
0x18007b64a  mov     byte ptr cs:xmmword_1800DADB0+0Fh, al
0x18007b650  call    cs:__imp_GetTickCount64
0x18007b656  mov     cs:qword_1800DADA8, rax
0x18007b65d  jmp     loc_18007B6F3
0x18007b662  test    edi, edi
0x18007b664  jnz     loc_18007B6F3
0x18007b66a  mov     eax, cs:dword_1800DA020
0x18007b670  cmp     eax, 4
0x18007b673  jbe     short loc_18007B6CE
0x18007b675  lea     rax, aSuccessfullySt; "Successfully stopped collection"
0x18007b67c  mov     [rbp+57h+var_80], rax
0x18007b680  lea     rax, [rbp+57h+var_80]
0x18007b684  mov     [rsp+0D0h+var_B0], rax
0x18007b689  lea     rdx, qword_1800C7538
0x18007b690  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18007b695  jmp     short loc_18007B6CE
0x18007b697  mov     eax, cs:dword_1800DA020
0x18007b69d  cmp     eax, 2
0x18007b6a0  jbe     short loc_18007B6CE
0x18007b6a2  mov     [rbp+57h+var_78], ecx
0x18007b6a5  lea     rax, aDidNotStartEsc; "Did not start escalation of logs"
0x18007b6ac  mov     [rbp+57h+var_80], rax
0x18007b6b0  lea     rax, [rbp+57h+var_78]
0x18007b6b4  mov     [rsp+0D0h+var_A8], rax
0x18007b6b9  lea     rax, [rbp+57h+var_80]
0x18007b6bd  mov     [rsp+0D0h+var_B0], rax
0x18007b6c2  lea     rdx, byte_1800C7559
0x18007b6c9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007b6ce  test    edi, edi
0x18007b6d0  jnz     short loc_18007B6F3
0x18007b6d2  mov     cs:?g_EscalationStatus@@3UESCALATION_STATUS@@A, esi; ESCALATION_STATUS g_EscalationStatus
0x18007b6d8  call    cs:__imp_GetTickCount64
0x18007b6de  mov     cs:qword_1800DADA0, rax
0x18007b6e5  mov     qword ptr cs:xmmword_1800DADB0, rsi
0x18007b6ec  mov     qword ptr cs:xmmword_1800DADB0+8, rsi
0x18007b6f3  mov     rcx, [rbp+57h+lpsz]; pv
0x18007b6f7  call    cs:__imp_CoTaskMemFree
0x18007b6fd  nop
0x18007b6fe  lea     rcx, [rbp+57h+var_58]
0x18007b702  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007b707  xor     eax, eax
0x18007b709  add     rsp, 0B8h
0x18007b710  pop     rdi
0x18007b711  pop     rsi
0x18007b712  pop     rbx
0x18007b713  pop     rbp
0x18007b714  retn
```
