# EnergyWizardImpl::SaveReport(ushort const *)

- ea: `0x18000f788`
- end: `0x18000fb5b`
- name: `?SaveReport@EnergyWizardImpl@@QEAAJPEBG@Z`
- size: `979`
- prototype: `__int64 __fastcall(EnergyWizardImpl *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005e230`

## callees

- `0x180004e20`
- `0x180008740`
- `0x18000f36c`
- `0x18000f788`
- `0x18000fb64`
- `0x18000fbcc`
- `0x18000fd1c`
- `0x18001107c`
- `0x180023560`
- `0x180036450`
- `0x18003f13c`
- `0x18003f274`
- `0x180040940`
- `0x180042d60`
- `0x180043fbc`
- `0x18004d92c`
- `0x18005e2d4`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!__doserrno` at `0x18000f817`
- `api-ms-win-crt-runtime-l1-1-0!__doserrno` at `0x18000f817`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18000f80d`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18000f80d`

## pseudocode

```c
__int64 __fastcall EnergyWizardImpl::SaveReport(EnergyWizardImpl *this, const unsigned __int16 *a2)
{
  const wchar_t *v3; // rdx
  signed int v4; // ebx
  _DWORD *v5; // r15
  int v6; // eax
  Troubleshooter **v7; // rdi
  int v8; // ecx
  int v9; // eax
  int v10; // eax
  __int64 LogEntries; // rax
  struct LogEntry *v12; // rsi
  int v13; // edx
  int v14; // edx
  const struct Detail *i; // rbx
  int v16; // eax
  int v17; // eax
  FILE *Stream; // [rsp+30h] [rbp-88h] BYREF
  int v20; // [rsp+38h] [rbp-80h]
  __int128 v21; // [rsp+40h] [rbp-78h] BYREF
  __int64 v22; // [rsp+50h] [rbp-68h]
  struct LogEntry *v23[3]; // [rsp+58h] [rbp-60h] BYREF
  struct Detail *v24[4]; // [rsp+70h] [rbp-48h] BYREF
  int v25; // [rsp+C0h] [rbp+8h]

  v25 = 0;
  std::vector<ServicePowerRequest>::vector<ServicePowerRequest>(v24);
  std::vector<ServicePowerRequest>::vector<ServicePowerRequest>(v23);
  if ( *((_QWORD *)this + 1) == *(_QWORD *)this
    || (v5 = (_DWORD *)((char *)this + 112), (unsigned int)(*((_DWORD *)this + 28) - 1) > 1) )
  {
    v4 = -2147467259;
  }
  else
  {
    Stream = 0;
    v20 = 0;
    *(_QWORD *)((char *)this + 92) = 0;
    *((_DWORD *)this + 25) = 0;
    if ( _wfopen_s(&Stream, v3, L"w, ccs=UTF-8") )
    {
      v4 = *__doserrno();
      if ( v4 )
      {
        if ( v4 > 0 )
          v4 = (unsigned __int16)v4 | 0x80070000;
LABEL_8:
        XmlReporter::CloseReport((XmlReporter *)&Stream);
        goto LABEL_56;
      }
    }
    else
    {
      v20 = 1;
    }
    v6 = EnergyXmlReporter::WriteReportHeader(
           (EnergyXmlReporter *)&Stream,
           *(union _LARGE_INTEGER *)((char *)this + 72),
           *(union _LARGE_INTEGER *)((char *)this + 80),
           *((_DWORD *)this + 26),
           *((_DWORD *)this + 27));
    v4 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
      goto LABEL_8;
    }
    v7 = *(Troubleshooter ***)this;
    v8 = v20;
    while ( v7 != *((Troubleshooter ***)this + 1) )
    {
      try
      {
        if ( !*v7 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        Troubleshooter::ValidateSelf(*v7);
        EnergyXmlReporter::WriteTroubleshooterHeader((EnergyXmlReporter *)&Stream, *v7);
        LogEntries = Troubleshooter::GetLogEntries(*v7, &v21);
        std::vector<LogEntry>::operator=(v23, LogEntries);
        std::vector<LogEntry>::_Tidy(&v21);
        v12 = v23[0];
        v8 = v20;
        while ( v12 != v23[1] )
        {
          v13 = *(_DWORD *)(*(_QWORD *)v12 + 16LL);
          if ( v13 )
          {
            v14 = v13 - 1;
            if ( v14 )
            {
              if ( v14 == 1 )
                ++*((_DWORD *)this + 23);
            }
            else
            {
              ++*((_DWORD *)this + 24);
            }
          }
          else
          {
            ++*((_DWORD *)this + 25);
          }
          EnergyXmlReporter::WriteLogEntryHeader((EnergyXmlReporter *)&Stream, v12);
          v21 = 0;
          v22 = 0;
          std::vector<Detail>::_Construct_n<Detail * const &,Detail * const &>(
            &v21,
            0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)v12 + 2) - *((_QWORD *)v12 + 1)) >> 3),
            (char *)v12 + 8,
            (char *)v12 + 16);
          std::vector<Detail>::_Assign_counted_range<Detail *>(
            v24,
            v21,
            0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v21 + 1) - v21) >> 3));
          std::vector<Detail>::_Tidy(&v21);
          for ( i = v24[0]; i != v24[1]; i = (const struct Detail *)((char *)i + 40) )
            EnergyXmlReporter::WriteDetail((EnergyXmlReporter *)&Stream, i);
          v25 |= 1u;
          v8 = v20;
          if ( v20 == 7 )
          {
            if ( !(-858993459 * (unsigned int)((__int64)(*((_QWORD *)v12 + 2) - *((_QWORD *)v12 + 1)) >> 3)) )
              goto LABEL_46;
            v16 = fwprintf_s(Stream, L"%s", L"        </Details>\n");
            v8 = v20;
            if ( v16 < 0 )
              v8 = 3;
            v20 = v8;
            if ( v8 == 7 )
            {
LABEL_46:
              v8 = 8;
              v20 = 8;
            }
          }
          if ( v8 == 8 )
          {
            v17 = fwprintf_s(Stream, L"%s", L"      </LogEntry>\n");
            v8 = v20;
            if ( v17 < 0 )
              v8 = 3;
            if ( v8 == 8 )
              v8 = 6;
            v20 = v8;
          }
          v12 = (struct LogEntry *)((char *)v12 + 32);
        }
        if ( v8 == 6 )
        {
          XmlReporter::WriteRawString((XmlReporter *)&Stream, L"    </AnalysisLog>\n");
          XmlReporter::WriteRawString((XmlReporter *)&Stream, L"  </Troubleshooter>\n");
          v8 = v20;
          if ( v20 == 6 )
            v8 = 5;
          v20 = v8;
        }
        ++v7;
      }
      catch ( std::bad_alloc )
      {
        v5 = (_DWORD *)((char *)this + 112);
        v4 = -2147024882;
        goto LABEL_55;
      }
      catch ( ... )
      {
        v5 = (_DWORD *)((char *)this + 112);
        v4 = -2147467259;
        goto LABEL_55;
      }
    }
    if ( v8 == 5 )
    {
      XmlReporter::WriteRawString((XmlReporter *)&Stream, L"</EnergyReport>\n");
      v9 = v20;
      if ( v20 == 5 )
        v9 = 2;
      v20 = v9;
    }
    v10 = XmlReporter::CloseReport((XmlReporter *)&Stream);
    v4 = v10;
    if ( v10 > 0 )
      v4 = (unsigned __int16)v10 | 0x80070000;
    XmlReporter::CloseReport((XmlReporter *)&Stream);
    if ( v4 < 0 )
LABEL_55:
      *v5 = 1;
    else
      *v5 = 2;
  }
LABEL_56:
  std::vector<LogEntry>::_Tidy(v23);
  std::vector<Detail>::_Tidy(v24);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000f788  mov     [rsp+arg_8], rbx
0x18000f78d  mov     [rsp+arg_18], rsi
0x18000f792  push    rdi
0x18000f793  push    r12
0x18000f795  push    r13
0x18000f797  push    r14
0x18000f799  push    r15
0x18000f79b  sub     rsp, 90h
0x18000f7a2  mov     r14, rcx
0x18000f7a5  xor     r12d, r12d
0x18000f7a8  mov     [rsp+0B8h+arg_0], r12d
0x18000f7b0  lea     rcx, [rsp+0B8h+var_48]; void *
0x18000f7b5  call    ??0?$vector@VServicePowerRequest@@V?$allocator@VServicePowerRequest@@@std@@@std@@QEAA@XZ; std::vector<ServicePowerRequest>::vector<ServicePowerRequest>(void)
0x18000f7ba  nop
0x18000f7bb  lea     rcx, [rsp+0B8h+var_60]; void *
0x18000f7c0  call    ??0?$vector@VServicePowerRequest@@V?$allocator@VServicePowerRequest@@@std@@@std@@QEAA@XZ; std::vector<ServicePowerRequest>::vector<ServicePowerRequest>(void)
0x18000f7c5  nop
0x18000f7c6  mov     rax, [r14+8]
0x18000f7ca  cmp     rax, [r14]
0x18000f7cd  jnz     short loc_18000F7D9
0x18000f7cf  mov     ebx, 80004005h
0x18000f7d4  jmp     loc_18000FB27
0x18000f7d9  lea     r15, [r14+70h]
0x18000f7dd  mov     [rsp+0B8h+arg_10], r15
0x18000f7e5  mov     eax, [r15]
0x18000f7e8  dec     eax
0x18000f7ea  cmp     eax, 1
0x18000f7ed  ja      short loc_18000F7CF
0x18000f7ef  mov     [rsp+0B8h+Stream], r12
0x18000f7f4  mov     [rsp+0B8h+var_80], r12d
0x18000f7f9  mov     [r14+5Ch], r12
0x18000f7fd  mov     [r14+64h], r12d
0x18000f801  lea     r8, aWCcsUtf8; "w, ccs=UTF-8"
0x18000f808  lea     rcx, [rsp+0B8h+Stream]; Stream
0x18000f80d  call    cs:__imp__wfopen_s
0x18000f813  test    eax, eax
0x18000f815  jz      short loc_18000F83E
0x18000f817  call    cs:__imp___doserrno
0x18000f81d  mov     ebx, [rax]
0x18000f81f  test    ebx, ebx
0x18000f821  jz      short loc_18000F846
0x18000f823  jle     short loc_18000F82E
0x18000f825  movzx   ebx, bx
0x18000f828  or      ebx, 80070000h
0x18000f82e  lea     rcx, [rsp+0B8h+Stream]; this
0x18000f833  call    ?CloseReport@XmlReporter@@QEAAKXZ; XmlReporter::CloseReport(void)
0x18000f838  nop
0x18000f839  jmp     loc_18000FB27
0x18000f83e  mov     [rsp+0B8h+var_80], 1
0x18000f846  mov     eax, [r14+6Ch]
0x18000f84a  mov     [rsp+0B8h+var_98], eax; unsigned int
0x18000f84e  mov     r9d, [r14+68h]; unsigned int
0x18000f852  mov     r8, [r14+50h]; union _LARGE_INTEGER
0x18000f856  mov     rdx, [r14+48h]; union _LARGE_INTEGER
0x18000f85a  lea     rcx, [rsp+0B8h+Stream]; this
0x18000f85f  call    ?WriteReportHeader@EnergyXmlReporter@@QEAAKT_LARGE_INTEGER@@0KK@Z; EnergyXmlReporter::WriteReportHeader(_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong)
0x18000f864  mov     ebx, eax
0x18000f866  test    eax, eax
0x18000f868  jz      short loc_18000F885
0x18000f86a  jle     short loc_18000F875
0x18000f86c  movzx   ebx, ax
0x18000f86f  or      ebx, 80070000h
0x18000f875  lea     rcx, [rsp+0B8h+Stream]; this
0x18000f87a  call    ?CloseReport@XmlReporter@@QEAAKXZ; XmlReporter::CloseReport(void)
0x18000f87f  nop
0x18000f880  jmp     loc_18000FB27
0x18000f885  mov     rdi, [r14]
0x18000f888  mov     ebx, 5
0x18000f88d  lea     r13d, [rbx+1]
0x18000f891  mov     ecx, [rsp+0B8h+var_80]
0x18000f895  cmp     rdi, [r14+8]
0x18000f899  jnz     short loc_18000F8FD
0x18000f89b  cmp     ecx, ebx
0x18000f89d  jnz     short loc_18000F8C4
0x18000f89f  lea     rdx, aEnergyreport; "</EnergyReport>\n"
0x18000f8a6  lea     rcx, [rsp+0B8h+Stream]; this
0x18000f8ab  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18000f8b0  mov     eax, [rsp+0B8h+var_80]
0x18000f8b4  mov     edi, 2
0x18000f8b9  cmp     eax, ebx
0x18000f8bb  cmovz   eax, edi
0x18000f8be  mov     [rsp+0B8h+var_80], eax
0x18000f8c2  jmp     short loc_18000F8C9
0x18000f8c4  mov     edi, 2
0x18000f8c9  lea     rcx, [rsp+0B8h+Stream]; this
0x18000f8ce  call    ?CloseReport@XmlReporter@@QEAAKXZ; XmlReporter::CloseReport(void)
0x18000f8d3  mov     ebx, eax
0x18000f8d5  test    eax, eax
0x18000f8d7  jle     short loc_18000F8E2
0x18000f8d9  movzx   ebx, ax
0x18000f8dc  or      ebx, 80070000h
0x18000f8e2  lea     rcx, [rsp+0B8h+Stream]; this
0x18000f8e7  call    ?CloseReport@XmlReporter@@QEAAKXZ; XmlReporter::CloseReport(void)
0x18000f8ec  nop
0x18000f8ed  test    ebx, ebx
0x18000f8ef  js      loc_18000FB20
0x18000f8f5  mov     [r15], edi
0x18000f8f8  jmp     loc_18000FB27
0x18000f8fd  cmp     [rdi], r12
0x18000f900  jnz     short loc_18000F907
0x18000f902  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000f907  mov     rcx, [rdi]; this
0x18000f90a  call    ?ValidateSelf@Troubleshooter@@QEAAKXZ; Troubleshooter::ValidateSelf(void)
0x18000f90f  mov     rdx, [rdi]; struct Troubleshooter *
0x18000f912  lea     rcx, [rsp+0B8h+Stream]; this
0x18000f917  call    ?WriteTroubleshooterHeader@EnergyXmlReporter@@QEAAKPEAVTroubleshooter@@@Z; EnergyXmlReporter::WriteTroubleshooterHeader(Troubleshooter *)
0x18000f91c  lea     rdx, [rsp+0B8h+var_78]
0x18000f921  mov     rcx, [rdi]
0x18000f924  call    ?GetLogEntries@Troubleshooter@@QEAA?AV?$vector@VLogEntry@@V?$allocator@VLogEntry@@@std@@@std@@XZ; Troubleshooter::GetLogEntries(void)
0x18000f929  mov     rdx, rax
0x18000f92c  lea     rcx, [rsp+0B8h+var_60]
0x18000f931  call    ??4?$vector@VLogEntry@@V?$allocator@VLogEntry@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<LogEntry>::operator=(std::vector<LogEntry> &&)
0x18000f936  lea     rcx, [rsp+0B8h+var_78]
0x18000f93b  call    ?_Tidy@?$vector@VLogEntry@@V?$allocator@VLogEntry@@@std@@@std@@AEAAXXZ; std::vector<LogEntry>::_Tidy(void)
0x18000f940  mov     rsi, [rsp+0B8h+var_60]
0x18000f945  mov     ecx, [rsp+0B8h+var_80]
0x18000f949  cmp     rsi, [rsp+0B8h+var_58]
0x18000f94e  jnz     short loc_18000F98E
0x18000f950  cmp     ecx, r13d
0x18000f953  jnz     short loc_18000F985
0x18000f955  lea     rdx, aAnalysislog_0; "    </AnalysisLog>\n"
0x18000f95c  lea     rcx, [rsp+0B8h+Stream]; this
0x18000f961  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18000f966  lea     rdx, aTroubleshooter; "  </Troubleshooter>\n"
0x18000f96d  lea     rcx, [rsp+0B8h+Stream]; this
0x18000f972  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18000f977  mov     ecx, [rsp+0B8h+var_80]
0x18000f97b  cmp     ecx, r13d
0x18000f97e  cmovz   ecx, ebx
0x18000f981  mov     [rsp+0B8h+var_80], ecx
0x18000f985  add     rdi, 8
0x18000f989  jmp     loc_18000F895
0x18000f98e  mov     rcx, [rsi]
0x18000f991  mov     edx, [rcx+10h]
0x18000f994  test    edx, edx
0x18000f996  jz      short loc_18000F9AE
0x18000f998  sub     edx, 1
0x18000f99b  jz      short loc_18000F9A8
0x18000f99d  cmp     edx, 1
0x18000f9a0  jnz     short loc_18000F9B2
0x18000f9a2  inc     dword ptr [r14+5Ch]
0x18000f9a6  jmp     short loc_18000F9B2
0x18000f9a8  inc     dword ptr [r14+60h]
0x18000f9ac  jmp     short loc_18000F9B2
0x18000f9ae  inc     dword ptr [r14+64h]
0x18000f9b2  mov     rdx, rsi; struct LogEntry *
0x18000f9b5  lea     rcx, [rsp+0B8h+Stream]; this
0x18000f9ba  call    ?WriteLogEntryHeader@EnergyXmlReporter@@QEAAKAEBVLogEntry@@@Z; EnergyXmlReporter::WriteLogEntryHeader(LogEntry const &)
0x18000f9bf  xorps   xmm0, xmm0
0x18000f9c2  movdqu  [rsp+0B8h+var_78], xmm0
0x18000f9c8  mov     [rsp+0B8h+var_68], r12
0x18000f9cd  lea     r12, [rsi+10h]
0x18000f9d1  lea     r13, [rsi+8]
0x18000f9d5  mov     rdx, [r12]
0x18000f9d9  sub     rdx, [r13+0]
0x18000f9dd  sar     rdx, 3
0x18000f9e1  mov     rbx, 0CCCCCCCCCCCCCCCDh
0x18000f9eb  imul    rdx, rbx
0x18000f9ef  mov     r9, r12
0x18000f9f2  mov     r8, r13
0x18000f9f5  lea     rcx, [rsp+0B8h+var_78]
0x18000f9fa  call    ??$_Construct_n@AEBQEAVDetail@@AEBQEAV1@@?$vector@VDetail@@V?$allocator@VDetail@@@std@@@std@@AEAAX_KAEBQEAVDetail@@1@Z; std::vector<Detail>::_Construct_n<Detail * const &,Detail * const &>(unsigned __int64,Detail * const &,Detail * const &)
0x18000f9ff  nop
0x18000fa00  mov     rdx, qword ptr [rsp+0B8h+var_78]
0x18000fa05  mov     r8, qword ptr [rsp+0B8h+var_78+8]
0x18000fa0a  sub     r8, rdx
0x18000fa0d  sar     r8, 3
0x18000fa11  imul    r8, rbx
0x18000fa15  lea     rcx, [rsp+0B8h+var_48]
0x18000fa1a  call    ??$_Assign_counted_range@PEAVDetail@@@?$vector@VDetail@@V?$allocator@VDetail@@@std@@@std@@AEAAXPEAVDetail@@_K@Z; std::vector<Detail>::_Assign_counted_range<Detail *>(Detail *,unsigned __int64)
0x18000fa1f  nop
0x18000fa20  lea     rcx, [rsp+0B8h+var_78]
0x18000fa25  call    ?_Tidy@?$vector@VDetail@@V?$allocator@VDetail@@@std@@@std@@AEAAXXZ; std::vector<Detail>::_Tidy(void)
0x18000fa2a  mov     rbx, [rsp+0B8h+var_48]
0x18000fa2f  cmp     rbx, [rsp+0B8h+var_40]
0x18000fa34  jnz     loc_18000FAF9
0x18000fa3a  or      [rsp+0B8h+arg_0], 1
0x18000fa42  mov     ecx, [rsp+0B8h+var_80]
0x18000fa46  cmp     ecx, 7
0x18000fa49  jnz     short loc_18000FAA6
0x18000fa4b  mov     rax, [r12]
0x18000fa4f  sub     rax, [r13+0]
0x18000fa53  sar     rax, 3
0x18000fa57  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x18000fa61  imul    rax, rcx
0x18000fa65  xor     r12d, r12d
0x18000fa68  test    eax, eax
0x18000fa6a  jz      short loc_18000FA9B
0x18000fa6c  lea     r8, aDetails; "        </Details>\n"
0x18000fa73  lea     rdx, aS; "%s"
0x18000fa7a  mov     rcx, [rsp+0B8h+Stream]; Stream
0x18000fa7f  call    fwprintf_s
0x18000fa84  mov     ecx, [rsp+0B8h+var_80]
0x18000fa88  test    eax, eax
0x18000fa8a  lea     eax, [r12+3]
0x18000fa8f  cmovs   ecx, eax
0x18000fa92  mov     [rsp+0B8h+var_80], ecx
0x18000fa96  cmp     ecx, 7
0x18000fa99  jnz     short loc_18000FAA9
0x18000fa9b  mov     ecx, 8
0x18000faa0  mov     [rsp+0B8h+var_80], ecx
0x18000faa4  jmp     short loc_18000FAA9
0x18000faa6  xor     r12d, r12d
0x18000faa9  cmp     ecx, 8
0x18000faac  jnz     short loc_18000FAE5
0x18000faae  lea     r8, aLogentry; "      </LogEntry>\n"
0x18000fab5  lea     rdx, aS; "%s"
0x18000fabc  mov     rcx, [rsp+0B8h+Stream]; Stream
0x18000fac1  call    fwprintf_s
0x18000fac6  mov     ecx, [rsp+0B8h+var_80]
0x18000faca  test    eax, eax
0x18000facc  mov     eax, 3
0x18000fad1  cmovs   ecx, eax
0x18000fad4  cmp     ecx, 8
0x18000fad7  lea     r13d, [rax+3]
0x18000fadb  cmovz   ecx, r13d
0x18000fadf  mov     [rsp+0B8h+var_80], ecx
0x18000fae3  jmp     short loc_18000FAEB
0x18000fae5  mov     r13d, 6
0x18000faeb  add     rsi, 20h ; ' '
0x18000faef  mov     ebx, 5
0x18000faf4  jmp     loc_18000F949
0x18000faf9  mov     rdx, rbx; struct Detail *
0x18000fafc  lea     rcx, [rsp+0B8h+Stream]; this
0x18000fb01  call    ?WriteDetail@EnergyXmlReporter@@QEAAKAEBVDetail@@@Z; EnergyXmlReporter::WriteDetail(Detail const &)
0x18000fb06  add     rbx, 28h ; '('
0x18000fb0a  jmp     loc_18000FA2F
0x18000fb0f  jmp     short $+2
0x18000fb11  mov     r15, [rsp+0B8h+arg_10]
0x18000fb19  mov     ebx, [rsp+0B8h+arg_0]
0x18000fb20  mov     dword ptr [r15], 1
0x18000fb27  lea     rcx, [rsp+0B8h+var_60]
0x18000fb2c  call    ?_Tidy@?$vector@VLogEntry@@V?$allocator@VLogEntry@@@std@@@std@@AEAAXXZ; std::vector<LogEntry>::_Tidy(void)
0x18000fb31  nop
0x18000fb32  lea     rcx, [rsp+0B8h+var_48]
0x18000fb37  call    ?_Tidy@?$vector@VDetail@@V?$allocator@VDetail@@@std@@@std@@AEAAXXZ; std::vector<Detail>::_Tidy(void)
0x18000fb3c  mov     eax, ebx
0x18000fb3e  lea     r11, [rsp+0B8h+var_28]
0x18000fb46  mov     rbx, [r11+38h]
0x18000fb4a  mov     rsi, [r11+48h]
0x18000fb4e  mov     rsp, r11
0x18000fb51  pop     r15
0x18000fb53  pop     r14
0x18000fb55  pop     r13
0x18000fb57  pop     r12
0x18000fb59  pop     rdi
0x18000fb5a  retn
```
