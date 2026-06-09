# FeedbackHubEscalateInternal(_GUID,int)

- ea: `0x18007fca8`
- end: `0x18007ff82`
- name: `?FeedbackHubEscalateInternal@@YAJU_GUID@@H@Z`
- size: `730`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002b418`
- `0x18007ff90`

## callees

- `0x18002701c`
- `0x18002772c`
- `0x180053174`
- `0x18007fbd8`
- `0x18007fca8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ff5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ff5d`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18007fcc8`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18007fcc8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007feaa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007ff38`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007feaa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007ff38`

## string_xrefs

- `0x18007fd7b`: `stableid\RDPDiagnosticsStart\complete`
- `0x18007fd74`: `stableid\RDPDiagnosticsStop\complete`
- `0x18007fda8`: `We tried to start, but we're already running? what?`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FeedbackHubEscalateInternal(struct _GUID *a1, int a2)
{
  HRESULT v4; // eax
  int v5; // r8d
  int v6; // r9d
  __int64 v8; // rcx
  const wchar_t *v9; // r8
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  const char *v13; // [rsp+50h] [rbp-29h] BYREF
  int v14; // [rsp+58h] [rbp-21h] BYREF
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
      if ( (unsigned int)dword_1800DF020 > 2 )
      {
        v13 = "We tried to start, but we're already running? what?";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v8,
          (unsigned int)qword_1800CC728,
          (_DWORD)v9,
          a2 == 0,
          (__int64)&v13);
      }
      goto LABEL_24;
    }
    v10 = Microsoft::Diagnostics::UtcApiWrapper::EscalateScenarioEx(v8, v9);
    if ( v10 < 0 )
    {
      if ( (unsigned int)dword_1800DF020 > 2 )
      {
        v14 = v10;
        v13 = "Did not start escalation of logs";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v10,
          (unsigned int)qword_1800CC6C0,
          v11,
          v12,
          (__int64)&v13,
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
        if ( (unsigned int)dword_1800DF020 > 4 )
        {
          v13 = "Successfully started collection";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v10,
            (unsigned int)&byte_1800CC707,
            v11,
            v12,
            (__int64)&v13);
        }
        g_EscalationStatus = 1;
        xmmword_1800DFDC0 = (__int128)*a1;
        qword_1800DFDB8 = GetTickCount64();
        goto LABEL_24;
      }
      if ( (unsigned int)dword_1800DF020 > 4 )
      {
        v13 = "Successfully stopped collection";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v10,
          (unsigned int)&word_1800CC6E6,
          v11,
          v12,
          (__int64)&v13);
      }
    }
    if ( !a2 )
    {
      g_EscalationStatus = 0;
      qword_1800DFDB0 = GetTickCount64();
      xmmword_1800DFDC0 = 0u;
    }
    goto LABEL_24;
  }
  if ( (unsigned int)dword_1800DF020 > 2 )
  {
    v14 = v4;
    v13 = "Failed to convert activityid";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_1800DF020,
      (unsigned int)byte_1800CC749,
      v5,
      v6,
      (__int64)&v13,
      (__int64)&v14);
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18007fca8  push    rbp
0x18007fcaa  push    rbx
0x18007fcab  push    rsi
0x18007fcac  push    rdi
0x18007fcad  lea     rbp, [rsp-3Fh]
0x18007fcb2  sub     rsp, 0B8h
0x18007fcb9  mov     edi, edx
0x18007fcbb  mov     rbx, rcx
0x18007fcbe  xor     esi, esi
0x18007fcc0  mov     [rbp+57h+lpsz], rsi
0x18007fcc4  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x18007fcc8  call    cs:__imp_StringFromCLSID
0x18007fccf  nop     dword ptr [rax+rax+00h]
0x18007fcd4  test    eax, eax
0x18007fcd6  jns     short loc_18007FD19
0x18007fcd8  mov     ecx, cs:dword_1800DF020
0x18007fcde  cmp     ecx, 2
0x18007fce1  jbe     short loc_18007FD0F
0x18007fce3  mov     [rbp+57h+var_78], eax
0x18007fce6  lea     rax, aFailedToConver_0; "Failed to convert activityid"
0x18007fced  mov     [rbp+57h+var_80], rax
0x18007fcf1  lea     rax, [rbp+57h+var_78]
0x18007fcf5  mov     [rsp+0D0h+var_A8], rax
0x18007fcfa  lea     rax, [rbp+57h+var_80]
0x18007fcfe  mov     [rsp+0D0h+var_B0], rax
0x18007fd03  lea     rdx, byte_1800CC749
0x18007fd0a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007fd0f  mov     eax, 80004005h
0x18007fd14  jmp     loc_18007FF75
0x18007fd19  lea     rax, aCollectweretwl; "_collectweretwlogs"
0x18007fd20  mov     [rbp+57h+var_60], rax
0x18007fd24  lea     rcx, aTrue; "true"
0x18007fd2b  mov     [rbp+57h+var_68], rcx
0x18007fd2f  mov     [rbp+57h+var_38], rax
0x18007fd33  lea     rax, aInstanceid; "_instanceid"
0x18007fd3a  mov     [rbp+57h+var_30], rax
0x18007fd3e  mov     [rbp+57h+var_48], rcx
0x18007fd42  mov     rax, [rbp+57h+lpsz]
0x18007fd46  mov     [rbp+57h+var_40], rax
0x18007fd4a  mov     eax, edi
0x18007fd4c  neg     eax
0x18007fd4e  sbb     ecx, ecx
0x18007fd50  add     ecx, 2
0x18007fd53  lea     rax, [rbp+57h+var_48]
0x18007fd57  lea     rdx, [rbp+57h+var_68]
0x18007fd5b  test    edi, edi
0x18007fd5d  cmovnz  rax, rdx
0x18007fd61  lea     rdx, [rbp+57h+var_38]
0x18007fd65  lea     r8, [rbp+57h+var_60]
0x18007fd69  cmovnz  rdx, r8
0x18007fd6d  mov     r9d, esi
0x18007fd70  setz    r9b
0x18007fd74  lea     r10, aStableidRdpdia; "stableid\\RDPDiagnosticsStop\\complete"
0x18007fd7b  lea     r8, aStableidRdpdia_0; "stableid\\RDPDiagnosticsStart\\complete"
0x18007fd82  cmovz   r8, r10
0x18007fd86  mov     [rbp+57h+var_58], rsi
0x18007fd8a  mov     [rbp+57h+var_50], esi
0x18007fd8d  cmp     cs:?g_EscalationStatus@@3UESCALATION_STATUS@@A, esi; ESCALATION_STATUS g_EscalationStatus
0x18007fd93  jz      short loc_18007FDCD
0x18007fd95  test    edi, edi
0x18007fd97  jz      short loc_18007FDCD
0x18007fd99  mov     eax, cs:dword_1800DF020
0x18007fd9f  cmp     eax, 2
0x18007fda2  jbe     loc_18007FF59
0x18007fda8  lea     rax, aWeTriedToStart; "We tried to start, but we're already ru"...
0x18007fdaf  mov     [rbp+57h+var_80], rax
0x18007fdb3  lea     rax, [rbp+57h+var_80]
0x18007fdb7  mov     [rsp+0D0h+var_B0], rax
0x18007fdbc  lea     rdx, qword_1800CC728
0x18007fdc3  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18007fdc8  jmp     loc_18007FF59
0x18007fdcd  lea     r10, [rbp+57h+var_58]
0x18007fdd1  mov     [rsp+0D0h+var_88], r10
0x18007fdd6  mov     [rsp+0D0h+var_90], rax
0x18007fddb  mov     [rsp+0D0h+var_98], rdx
0x18007fde0  mov     [rsp+0D0h+var_A0], ecx
0x18007fde4  mov     dword ptr [rsp+0D0h+var_A8], r9d
0x18007fde9  mov     rdx, r8
0x18007fdec  call    ?EscalateScenarioEx@UtcApiWrapper@Diagnostics@Microsoft@@QEAAJPEBG0HHW4__MIDL_UtcApiStructures_0004@@KPEAPEBG2AEAVAutoEscalationResultsList@123@@Z; Microsoft::Diagnostics::UtcApiWrapper::EscalateScenarioEx(ushort const *,ushort const *,int,int,__MIDL_UtcApiStructures_0004,ulong,ushort const * *,ushort const * *,Microsoft::Diagnostics::UtcApiWrapper::AutoEscalationResultsList &)
0x18007fdf1  mov     ecx, eax
0x18007fdf3  test    eax, eax
0x18007fdf5  js      loc_18007FEF7
0x18007fdfb  cmp     cs:?g_EscalationStatus@@3UESCALATION_STATUS@@A, esi; ESCALATION_STATUS g_EscalationStatus
0x18007fe01  jnz     loc_18007FEC2
0x18007fe07  test    edi, edi
0x18007fe09  jz      loc_18007FECA
0x18007fe0f  mov     eax, cs:dword_1800DF020
0x18007fe15  cmp     eax, 4
0x18007fe18  jbe     short loc_18007FE3A
0x18007fe1a  lea     rax, aSuccessfullySt_0; "Successfully started collection"
0x18007fe21  mov     [rbp+57h+var_80], rax
0x18007fe25  lea     rax, [rbp+57h+var_80]
0x18007fe29  mov     [rsp+0D0h+var_B0], rax
0x18007fe2e  lea     rdx, byte_1800CC707
0x18007fe35  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18007fe3a  mov     cs:?g_EscalationStatus@@3UESCALATION_STATUS@@A, 1; ESCALATION_STATUS g_EscalationStatus
0x18007fe44  mov     eax, [rbx]
0x18007fe46  mov     dword ptr cs:xmmword_1800DFDC0, eax
0x18007fe4c  movzx   eax, word ptr [rbx+4]
0x18007fe50  mov     word ptr cs:xmmword_1800DFDC0+4, ax
0x18007fe57  movzx   eax, word ptr [rbx+6]
0x18007fe5b  mov     word ptr cs:xmmword_1800DFDC0+6, ax
0x18007fe62  mov     al, [rbx+8]
0x18007fe65  mov     byte ptr cs:xmmword_1800DFDC0+8, al
0x18007fe6b  mov     al, [rbx+9]
0x18007fe6e  mov     byte ptr cs:xmmword_1800DFDC0+9, al
0x18007fe74  mov     al, [rbx+0Ah]
0x18007fe77  mov     byte ptr cs:xmmword_1800DFDC0+0Ah, al
0x18007fe7d  mov     al, [rbx+0Bh]
0x18007fe80  mov     byte ptr cs:xmmword_1800DFDC0+0Bh, al
0x18007fe86  mov     al, [rbx+0Ch]
0x18007fe89  mov     byte ptr cs:xmmword_1800DFDC0+0Ch, al
0x18007fe8f  mov     al, [rbx+0Dh]
0x18007fe92  mov     byte ptr cs:xmmword_1800DFDC0+0Dh, al
0x18007fe98  mov     al, [rbx+0Eh]
0x18007fe9b  mov     byte ptr cs:xmmword_1800DFDC0+0Eh, al
0x18007fea1  mov     al, [rbx+0Fh]
0x18007fea4  mov     byte ptr cs:xmmword_1800DFDC0+0Fh, al
0x18007feaa  call    cs:__imp_GetTickCount64
0x18007feb1  nop     dword ptr [rax+rax+00h]
0x18007feb6  mov     cs:qword_1800DFDB8, rax
0x18007febd  jmp     loc_18007FF59
0x18007fec2  test    edi, edi
0x18007fec4  jnz     loc_18007FF59
0x18007feca  mov     eax, cs:dword_1800DF020
0x18007fed0  cmp     eax, 4
0x18007fed3  jbe     short loc_18007FF2E
0x18007fed5  lea     rax, aSuccessfullySt; "Successfully stopped collection"
0x18007fedc  mov     [rbp+57h+var_80], rax
0x18007fee0  lea     rax, [rbp+57h+var_80]
0x18007fee4  mov     [rsp+0D0h+var_B0], rax
0x18007fee9  lea     rdx, word_1800CC6E6
0x18007fef0  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18007fef5  jmp     short loc_18007FF2E
0x18007fef7  mov     eax, cs:dword_1800DF020
0x18007fefd  cmp     eax, 2
0x18007ff00  jbe     short loc_18007FF2E
0x18007ff02  mov     [rbp+57h+var_78], ecx
0x18007ff05  lea     rax, aDidNotStartEsc; "Did not start escalation of logs"
0x18007ff0c  mov     [rbp+57h+var_80], rax
0x18007ff10  lea     rax, [rbp+57h+var_78]
0x18007ff14  mov     [rsp+0D0h+var_A8], rax
0x18007ff19  lea     rax, [rbp+57h+var_80]
0x18007ff1d  mov     [rsp+0D0h+var_B0], rax
0x18007ff22  lea     rdx, qword_1800CC6C0
0x18007ff29  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007ff2e  test    edi, edi
0x18007ff30  jnz     short loc_18007FF59
0x18007ff32  mov     cs:?g_EscalationStatus@@3UESCALATION_STATUS@@A, esi; ESCALATION_STATUS g_EscalationStatus
0x18007ff38  call    cs:__imp_GetTickCount64
0x18007ff3f  nop     dword ptr [rax+rax+00h]
0x18007ff44  mov     cs:qword_1800DFDB0, rax
0x18007ff4b  mov     qword ptr cs:xmmword_1800DFDC0, rsi
0x18007ff52  mov     qword ptr cs:xmmword_1800DFDC0+8, rsi
0x18007ff59  mov     rcx, [rbp+57h+lpsz]; pv
0x18007ff5d  call    cs:__imp_CoTaskMemFree
0x18007ff64  nop     dword ptr [rax+rax+00h]
0x18007ff69  nop
0x18007ff6a  lea     rcx, [rbp+57h+var_58]
0x18007ff6e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007ff73  xor     eax, eax
0x18007ff75  add     rsp, 0B8h
0x18007ff7c  pop     rdi
0x18007ff7d  pop     rsi
0x18007ff7e  pop     rbx
0x18007ff7f  pop     rbp
0x18007ff80  retn
```
