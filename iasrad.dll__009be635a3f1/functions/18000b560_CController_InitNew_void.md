# CController::InitNew(void)

- ea: `0x18000b560`
- end: `0x18000c468`
- name: `?InitNew@CController@@UEAAJXZ`
- size: `3848`
- prototype: `__int64 __fastcall(CController *__hidden this)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000c470`

## callees

- `0x1800094e4`
- `0x180009b10`
- `0x180009d88`
- `0x18000ae94`
- `0x18000aebc`
- `0x18000b560`
- `0x18000c614`
- `0x18000dcc8`
- `0x18000e4e0`
- `0x1800125c0`
- `0x18001273c`
- `0x180014d54`
- `0x180016618`
- `0x180016a08`
- `0x1800178b8`
- `0x180018bec`
- `0x18001be88`
- `0x18001d124`
- `0x18001d31c`
- `0x18001e500`
- `0x1800282fc`
- `0x1800288c8`
- `0x180028970`
- `0x180029bb4`
- `0x18002e230`
- `0x180030010`

## import_xrefs

- `msvcrt!free` at `0x18000b8e0`
- `msvcrt!free` at `0x18000b8e0`
- `iassvcs!IASReportEvent` at `0x18000c38c`
- `iassvcs!IASReportEvent` at `0x18000c38c`
- `KERNEL32!InitializeCriticalSection` at `0x18000bc30`
- `KERNEL32!InitializeCriticalSection` at `0x18000bc30`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c30a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c30a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18000c2dc`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18000c2dc`

## string_xrefs

- `0x18000b684`: `Unable to create ReportEvent object in Controller initialization`
- `0x18000b73a`: `Unable to create CEventLogResult object in Controller initialization`
- `0x18000b7e2`: `Unable to create Tunnel-Password object in Controller initialization`
- `0x18000b87a`: `Unable to create VSA-Filter object in Controller initialization`
- `0x18000b988`: `Unable to create Packet-Sender object in Controller initialization`
- `0x18000ba3b`: `Unable to create HMAC-MD5 object in Controller initialization`
- `0x18000bad7`: `Unable to create MD5 object in Controller initialization`
- `0x18000bb61`: `Unable to create Dictionary object in Controller initialization`
- `0x18000bc67`: `Unable to create clients object in Controller initialization`
- `0x18000bd7d`: `Unable to create Send-To-Pipe object in Controller initialization`
- `0x18000be2d`: `Unable to create Pre-Processor object in Controller initialization`
- `0x18000beda`: `Unable to create Pre-Validator object in Controller initialization`
- `0x18000c0a6`: `Unable to create RecvFromPipe object in Controller initialization`
- `0x18000c1a6`: `Unable to create Packet-Receiver object in Controller initialization`
- `0x18000c3bd`: `Unable to create InfoBase auditor in Controller initialization`

## pseudocode

```c
__int64 __fastcall CController::InitNew(CController *this, const struct std::nothrow_t *a2)
{
  HRESULT inited; // ebx
  CReportEvent *v4; // rax
  const struct std::nothrow_t *v5; // rdx
  CReportEvent *v6; // rax
  __int64 v7; // rdx
  CEventLogResult *v8; // rax
  CEventLogResult *v9; // rdi
  const struct std::nothrow_t *v10; // rdx
  void *v11; // rax
  const struct std::nothrow_t *v12; // rdx
  __int64 v13; // rdx
  void *v14; // rax
  VSADictionary *v15; // rcx
  const struct std::nothrow_t *v16; // rdx
  CPacketIo *v17; // rax
  Perimeter *v18; // rbx
  const struct std::nothrow_t *v19; // rdx
  _QWORD *v20; // rax
  const struct std::nothrow_t *v21; // rdx
  _QWORD *v22; // rax
  const struct std::nothrow_t *v23; // rdx
  CDictionary *v24; // rax
  const struct std::nothrow_t *v25; // rdx
  struct _RTL_CRITICAL_SECTION *v26; // rax
  struct _RTL_CRITICAL_SECTION *v27; // rbx
  const struct std::nothrow_t *v28; // rdx
  CClients *v29; // rcx
  _QWORD *v30; // rax
  const struct std::nothrow_t *v31; // rdx
  _QWORD *v32; // rax
  const struct std::nothrow_t *v33; // rdx
  struct CPreValidator *v34; // rdx
  const struct std::nothrow_t *v35; // rdx
  const struct std::nothrow_t *v36; // rdx
  CRecvFromPipe *v37; // r12
  __int64 v38; // rdi
  __int64 v39; // rbx
  __int64 v40; // r11
  __int64 v41; // r10
  __int64 v42; // r9
  __int64 v43; // r8
  __int64 v44; // rdx
  int Configuration; // eax
  CPacketIo *v46; // rax
  CPacketIo *v47; // rbx
  __int64 v48; // rcx
  int GlobalConfig; // edi
  int v50; // eax
  const wchar_t *v51; // rax
  CEventLogResult *v52; // rcx
  struct CReportEvent *v54; // [rsp+28h] [rbp-80h]
  const wchar_t *v55; // [rsp+40h] [rbp-68h] BYREF
  GUID clsid; // [rsp+48h] [rbp-60h] BYREF

  if ( *((_DWORD *)this + 322) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Incorrect state for calling InitNew");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
    }
    inited = -2147418113;
    goto LABEL_239;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Initializing CReportEvent class");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
  }
  v4 = (CReportEvent *)operator new[](0x10u, a2);
  if ( v4 )
    v6 = CReportEvent::CReportEvent(v4);
  else
    v6 = 0;
  *((_QWORD *)this + 19) = v6;
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_20;
    }
    WppDbgPrint("Unable to create ReportEvent object in Controller initialization");
    v7 = 12;
LABEL_19:
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
LABEL_20:
    inited = -2147024882;
LABEL_239:
    CController::InternalCleanup(this);
    return (unsigned int)inited;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Initializing CEventLogResult class");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
  }
  v8 = (CEventLogResult *)operator new[](0x10u, v5);
  v9 = v8;
  if ( v8 )
  {
    *(_QWORD *)v8 = 0;
    *((_QWORD *)v8 + 1) = 0;
  }
  else
  {
    v9 = 0;
  }
  *((_QWORD *)this + 20) = v9;
  if ( !v9 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_20;
    }
    WppDbgPrint("Unable to create CEventLogResult object in Controller initialization");
    v7 = 14;
    goto LABEL_19;
  }
  inited = CEventLogResult::InitNullSID(v9);
  if ( inited < 0 || (inited = CEventLogResult::InitMachineName(v9), inited < 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Unable to initialize CEventLogResult object in Controller initialization");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
    }
    v52 = (CEventLogResult *)*((_QWORD *)this + 20);
    if ( v52 )
      CEventLogResult::`scalar deleting destructor'(v52, (unsigned int)v10);
    *((_QWORD *)this + 20) = 0;
    goto LABEL_239;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Initializing CTunnelPassword class");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
  }
  v11 = operator new[](1u, v10);
  *((_QWORD *)this + 21) = v11;
  if ( !v11 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_45;
    }
    WppDbgPrint("Unable to create Tunnel-Password object in Controller initialization");
    v13 = 17;
LABEL_44:
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
LABEL_45:
    inited = -2147467259;
    goto LABEL_239;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Initializing VSAFilter class");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
  }
  v14 = operator new[](1u, v12);
  *((_QWORD *)this + 22) = v14;
  if ( !v14 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_45;
    }
    WppDbgPrint("Unable to create VSA-Filter object in Controller initialization");
    v13 = 19;
    goto LABEL_44;
  }
  inited = VSADictionary::initialize(v15);
  if ( inited < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Unable to initalize VSA-Filter object in Controller initialization");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
    }
    free(*((void **)this + 22));
    *((_QWORD *)this + 22) = 0;
    goto LABEL_239;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Initializing CPacketSender class");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
  }
  v17 = (CPacketIo *)operator new[](0x68u, v16);
  v18 = v17;
  if ( v17 )
  {
    CPacketIo::CPacketIo(v17);
    *(_QWORD *)v18 = &CPacketSender::`vftable';
  }
  else
  {
    v18 = 0;
  }
  *((_QWORD *)this + 18) = v18;
  if ( !v18 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_20;
    }
    WppDbgPrint("Unable to create Packet-Sender object in Controller initialization");
    v7 = 22;
    goto LABEL_19;
  }
  inited = Perimeter::FinalConstruct(v18);
  if ( inited < 0 )
    goto LABEL_239;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Initializing CHashHmacMD5 class");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
  }
  v20 = operator new[](8u, v19);
  if ( v20 )
    *v20 = &CHashHmacMD5::`vftable';
  else
    v20 = 0;
  *((_QWORD *)this + 16) = v20;
  if ( !v20 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_20;
    }
    WppDbgPrint("Unable to create HMAC-MD5 object in Controller initialization");
    v7 = 24;
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Initializing CHashMD5 class");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
  }
  v22 = operator new[](8u, v21);
  if ( v22 )
    *v22 = &CHashMD5::`vftable';
  else
    v22 = 0;
  *((_QWORD *)this + 15) = v22;
  if ( !v22 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_20;
    }
    WppDbgPrint("Unable to create MD5 object in Controller initialization");
    v7 = 26;
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Initializing CDictionary class");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
  }
  v24 = (CDictionary *)operator new[](0x400u, v23);
  *((_QWORD *)this + 13) = v24;
  if ( !v24 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_20;
    }
    WppDbgPrint("Unable to create Dictionary object in Controller initialization");
    v7 = 28;
    goto LABEL_19;
  }
  if ( !(unsigned int)CDictionary::Init(v24) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_45;
    }
    WppDbgPrint("Unable to initialize Dictionary object in Controller initialization");
    v13 = 29;
    goto LABEL_44;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Initializing CClients class");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
  }
  v26 = (struct _RTL_CRITICAL_SECTION *)operator new[](0x58u, v25);
  v27 = v26;
  if ( v26 )
  {
    ATL::CComPtr<IClassFactory>::CComPtr<IClassFactory>(&v26[1]);
    *(_QWORD *)&v27[1].LockCount = 0;
    v27[1].OwningThread = 0;
    v27[1].LockSemaphore = 0;
    v27[1].SpinCount = 0;
    LODWORD(v27[2].DebugInfo) = 0;
    BYTE4(v27[2].DebugInfo) = 0;
    InitializeCriticalSection(v27);
  }
  else
  {
    v27 = 0;
  }
  *((_QWORD *)this + 14) = v27;
  if ( !v27 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_20;
    }
    WppDbgPrint("Unable to create clients object in Controller initialization");
    v7 = 31;
    goto LABEL_19;
  }
  inited = CClients::Init((CClients *)v27);
  if ( inited < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Unable to initialize clients object in Controller initialization");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
    }
    v29 = (CClients *)*((_QWORD *)this + 14);
    if ( v29 )
      CClients::`scalar deleting destructor'(v29, (unsigned int)v28);
    *((_QWORD *)this + 14) = 0;
    goto LABEL_239;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Initializing CSendToPipe class");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
  }
  v30 = operator new[](0x30u, v28);
  if ( v30 )
  {
    v30[1] = 0;
    *v30 = &CSendToPipe::`vftable';
    v30[2] = 0;
    v30[3] = 0;
    v30[4] = 0;
    v30[5] = 0;
  }
  else
  {
    v30 = 0;
  }
  *((_QWORD *)this + 17) = v30;
  if ( !v30 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_20;
    }
    WppDbgPrint("Unable to create Send-To-Pipe object in Controller initialization");
    v7 = 34;
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Initializing CPreProcessor class");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
  }
  v32 = operator new[](0x28u, v31);
  if ( v32 )
  {
    v32[1] = 0;
    *v32 = &CPreProcessor::`vftable';
    v32[2] = 0;
    v32[3] = 0;
    v32[4] = 0;
  }
  else
  {
    v32 = 0;
  }
  *((_QWORD *)this + 11) = v32;
  if ( !v32 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_20;
    }
    WppDbgPrint("Unable to create Pre-Processor object in Controller initialization");
    v7 = 36;
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Initializing CPreValidator class");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
  }
  v34 = (struct CPreValidator *)operator new[](0x20u, v33);
  if ( v34 )
  {
    *((_QWORD *)v34 + 1) = 0;
    *(_QWORD *)v34 = &CPreValidator::`vftable';
    *((_QWORD *)v34 + 2) = 0;
    *((_QWORD *)v34 + 3) = 0;
  }
  else
  {
    v34 = 0;
  }
  *((_QWORD *)this + 12) = v34;
  if ( !v34 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_20;
    }
    WppDbgPrint("Unable to create Pre-Validator object in Controller initialization");
    v7 = 38;
    goto LABEL_19;
  }
  if ( !(unsigned int)CPreProcessor::Init(
                        *((CPreProcessor **)this + 11),
                        v34,
                        *((struct CHashMD5 **)this + 15),
                        *((struct CSendToPipe **)this + 17),
                        *((struct CPacketSender **)this + 18),
                        v54) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_45;
    }
    WppDbgPrint("Unable to initialize Pre-Processor object in Controller initialization");
    v13 = 39;
    goto LABEL_44;
  }
  if ( !(unsigned int)CPreValidator::Init(
                        *((CPreValidator **)this + 12),
                        *((struct CDictionary **)this + 13),
                        *((struct CPreProcessor **)this + 11),
                        *((struct CClients **)this + 14),
                        *((struct CHashMD5 **)this + 15),
                        *((struct CReportEvent **)this + 19)) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_45;
    }
    WppDbgPrint("Unable to initialize Pre-Validator object in Controller initialization");
    v13 = 40;
    goto LABEL_44;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Initializing CRecvFromPipe class");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
  }
  v37 = (CRecvFromPipe *)operator new[](0x50u, v35);
  if ( v37 )
  {
    v38 = *((_QWORD *)this + 20);
    v39 = *((_QWORD *)this + 19);
    v40 = *((_QWORD *)this + 21);
    v41 = *((_QWORD *)this + 22);
    v42 = *((_QWORD *)this + 14);
    v43 = *((_QWORD *)this + 16);
    v44 = *((_QWORD *)this + 15);
    *((_QWORD *)v37 + 2) = *((_QWORD *)this + 11);
    *(_QWORD *)v37 = &CProcAccess::`vftable';
    *((_QWORD *)v37 + 3) = v44;
    *((_QWORD *)v37 + 4) = v43;
    *((_QWORD *)v37 + 5) = v42;
    *((_QWORD *)v37 + 6) = v41;
    *((_QWORD *)v37 + 7) = v40;
    *((_QWORD *)v37 + 8) = v39;
    *((_QWORD *)v37 + 9) = v38;
    Configuration = CRecvFromPipe::LoadConfiguration(v37);
    if ( Configuration < 0 )
      _com_issue_error(Configuration);
  }
  else
  {
    v37 = 0;
  }
  *((_QWORD *)this + 10) = v37;
  if ( !v37 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_45;
    }
    WppDbgPrint("Unable to create RecvFromPipe object in Controller initialization");
    v13 = 42;
    goto LABEL_44;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Initializing CPacketReceiver class");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
  }
  v46 = (CPacketIo *)operator new[](0x600u, v36);
  v47 = v46;
  if ( v46 )
  {
    CPacketIo::CPacketIo(v46);
    *((_QWORD *)v47 + 13) = 0;
    *(_QWORD *)v47 = &CPacketReceiver::`vftable';
    *((_QWORD *)v47 + 14) = 0;
    *((_QWORD *)v47 + 15) = 0;
    *((_QWORD *)v47 + 16) = 0;
    *((_QWORD *)v47 + 17) = 0;
    *((_QWORD *)v47 + 18) = 0;
    *((_QWORD *)v47 + 19) = 0;
    *((_QWORD *)v47 + 20) = 0;
    *((_DWORD *)v47 + 42) = 0;
    memory_pool<4096,task_allocator>::memory_pool<4096,task_allocator>((char *)v47 + 176);
    *((_QWORD *)v47 + 158) = -1;
    *((_QWORD *)v47 + 175) = -1;
  }
  else
  {
    v47 = 0;
  }
  *((_QWORD *)this + 9) = v47;
  if ( !v47 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_20;
    }
    WppDbgPrint("Unable to create Packet-Receiver object in Controller initialization");
    v7 = 44;
    goto LABEL_19;
  }
  if ( !(unsigned int)CPacketReceiver::Init(
                        v47,
                        *((struct CDictionary **)this + 13),
                        *((struct CPreValidator **)this + 12),
                        *((struct CHashMD5 **)this + 15),
                        *((struct CHashHmacMD5 **)this + 16),
                        *((struct CClients **)this + 14),
                        *((struct CReportEvent **)this + 19)) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_45;
    }
    WppDbgPrint("Unable to initialize Packet-Receiver object in Controller initialization");
    v13 = 45;
    goto LABEL_44;
  }
  if ( !(unsigned int)CSendToPipe::Init(
                        *((CSendToPipe **)this + 17),
                        (CController *)((char *)this + 1272),
                        *((struct VSAFilter **)this + 22),
                        *((struct CReportEvent **)this + 19)) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_45;
    }
    WppDbgPrint("Unable to initialize Send-to-pipe object in Controller initialization");
    v13 = 46;
    goto LABEL_44;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Initializing InfoBase object");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
  }
  clsid = 0;
  inited = CLSIDFromProgID(L"IAS.InfoBase", &clsid);
  if ( inited < 0
    || (inited = CoCreateInstance(&clsid, 0, 1u, &GUID_6bc096b4_0ce6_11d1_baae_00c04fc2e20d, (LPVOID *)this + 23),
        inited < 0)
    || (inited = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 23) + 88LL))(*((_QWORD *)this + 23)),
        inited < 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Unable to create InfoBase auditor in Controller initialization");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
    }
    goto LABEL_239;
  }
  g_lPacketCount = 0;
  g_lThreadCount = 0;
  LOBYTE(v48) = 1;
  GlobalConfig = RegistryUtil::getGlobalConfig(v48);
  v50 = RegistryUtil::getGlobalConfig(0);
  if ( GlobalConfig && v50 )
  {
    if ( GlobalConfig != 1 && v50 != 1 )
      goto LABEL_227;
    v51 = L"Audit";
  }
  else
  {
    v51 = L"Disable";
  }
  v55 = v51;
  IASReportEvent(2147488069LL, 1, 0, &v55, 0);
LABEL_227:
  *((_DWORD *)this + 322) = 1;
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000b560  push    rbx
0x18000b562  push    rbp
0x18000b563  push    rsi
0x18000b564  push    rdi
0x18000b565  push    r12
0x18000b567  push    r13
0x18000b569  push    r14
0x18000b56b  push    r15
0x18000b56d  sub     rsp, 68h
0x18000b571  mov     rax, cs:__security_cookie
0x18000b578  xor     rax, rsp
0x18000b57b  mov     [rsp+0A8h+var_50], rax
0x18000b580  xor     r12d, r12d
0x18000b583  mov     r13, rcx
0x18000b586  cmp     [rcx+508h], r12d
0x18000b58d  jz      short loc_18000B5EB
0x18000b58f  mov     rax, cs:WPP_GLOBAL_Control
0x18000b596  lea     rsi, WPP_GLOBAL_Control
0x18000b59d  cmp     rax, rsi
0x18000b5a0  jz      short loc_18000B5E1
0x18000b5a2  cmp     byte ptr [rax+19h], 2
0x18000b5a6  jb      short loc_18000B5E1
0x18000b5a8  mov     ebp, 100h
0x18000b5ad  test    [rax+1Ch], ebp
0x18000b5b0  jz      short loc_18000B5E1
0x18000b5b2  lea     rcx, aIncorrectState; "Incorrect state for calling InitNew"
0x18000b5b9  call    WppDbgPrint
0x18000b5be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5c5  lea     edx, [r12+0Ah]
0x18000b5ca  lea     r9, aNpsrad; "NPSRAD"
0x18000b5d1  lea     r8, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids
0x18000b5d8  mov     rcx, [rcx+10h]
0x18000b5dc  call    WPP_SF_s
0x18000b5e1  mov     ebx, 8000FFFFh
0x18000b5e6  jmp     loc_18000C440
0x18000b5eb  mov     rax, cs:WPP_GLOBAL_Control
0x18000b5f2  lea     rsi, WPP_GLOBAL_Control
0x18000b5f9  lea     r14, aNpsrad; "NPSRAD"
0x18000b600  mov     ebp, 100h
0x18000b605  lea     r15, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids
0x18000b60c  cmp     rax, rsi
0x18000b60f  jz      short loc_18000B643
0x18000b611  cmp     byte ptr [rax+19h], 4
0x18000b615  jb      short loc_18000B643
0x18000b617  test    [rax+1Ch], ebp
0x18000b61a  jz      short loc_18000B643
0x18000b61c  lea     rcx, aInitializingCr; "Initializing CReportEvent class"
0x18000b623  call    WppDbgPrint
0x18000b628  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b62f  mov     edx, 0Bh
0x18000b634  mov     r9, r14
0x18000b637  mov     r8, r15
0x18000b63a  mov     rcx, [rcx+10h]
0x18000b63e  call    WPP_SF_s
0x18000b643  mov     ebx, 10h
0x18000b648  mov     ecx, ebx; Size
0x18000b64a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000b64f  test    rax, rax
0x18000b652  jz      short loc_18000B65E
0x18000b654  mov     rcx, rax; this
0x18000b657  call    ??0CReportEvent@@QEAA@XZ; CReportEvent::CReportEvent(void)
0x18000b65c  jmp     short loc_18000B661
0x18000b65e  mov     rax, r12
0x18000b661  mov     [r13+98h], rax
0x18000b668  test    rax, rax
0x18000b66b  jnz     short loc_18000B6B5
0x18000b66d  mov     rax, cs:WPP_GLOBAL_Control
0x18000b674  cmp     rax, rsi
0x18000b677  jz      short loc_18000B6AB
0x18000b679  cmp     byte ptr [rax+19h], 2
0x18000b67d  jb      short loc_18000B6AB
0x18000b67f  test    [rax+1Ch], ebp
0x18000b682  jz      short loc_18000B6AB
0x18000b684  lea     rcx, aUnableToCreate_15; "Unable to create ReportEvent object in "...
0x18000b68b  call    WppDbgPrint
0x18000b690  mov     edx, 0Ch
0x18000b695  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b69c  mov     r9, r14
0x18000b69f  mov     r8, r15
0x18000b6a2  mov     rcx, [rcx+10h]
0x18000b6a6  call    WPP_SF_s
0x18000b6ab  mov     ebx, 8007000Eh
0x18000b6b0  jmp     loc_18000C440
0x18000b6b5  mov     rax, cs:WPP_GLOBAL_Control
0x18000b6bc  cmp     rax, rsi
0x18000b6bf  jz      short loc_18000B6F3
0x18000b6c1  cmp     byte ptr [rax+19h], 4
0x18000b6c5  jb      short loc_18000B6F3
0x18000b6c7  test    [rax+1Ch], ebp
0x18000b6ca  jz      short loc_18000B6F3
0x18000b6cc  lea     rcx, aInitializingCe; "Initializing CEventLogResult class"
0x18000b6d3  call    WppDbgPrint
0x18000b6d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6df  mov     edx, 0Dh
0x18000b6e4  mov     r9, r14
0x18000b6e7  mov     r8, r15
0x18000b6ea  mov     rcx, [rcx+10h]
0x18000b6ee  call    WPP_SF_s
0x18000b6f3  mov     rcx, rbx; Size
0x18000b6f6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000b6fb  mov     rdi, rax
0x18000b6fe  test    rax, rax
0x18000b701  jz      short loc_18000B70C
0x18000b703  mov     [rax], r12
0x18000b706  mov     [rax+8], r12
0x18000b70a  jmp     short loc_18000B70F
0x18000b70c  mov     rdi, r12
0x18000b70f  mov     [r13+0A0h], rdi
0x18000b716  test    rdi, rdi
0x18000b719  jnz     short loc_18000B74E
0x18000b71b  mov     rax, cs:WPP_GLOBAL_Control
0x18000b722  cmp     rax, rsi
0x18000b725  jz      short loc_18000B6AB
0x18000b727  cmp     byte ptr [rax+19h], 2
0x18000b72b  jb      loc_18000B6AB
0x18000b731  test    [rax+1Ch], ebp
0x18000b734  jz      loc_18000B6AB
0x18000b73a  lea     rcx, aUnableToCreate_9; "Unable to create CEventLogResult object"...
0x18000b741  call    WppDbgPrint
0x18000b746  lea     edx, [rdi+0Eh]
0x18000b749  jmp     loc_18000B695
0x18000b74e  mov     rcx, rdi; this
0x18000b751  call    ?InitNullSID@CEventLogResult@@AEAAJXZ; CEventLogResult::InitNullSID(void)
0x18000b756  mov     ebx, eax
0x18000b758  test    eax, eax
0x18000b75a  js      loc_18000C3E6
0x18000b760  mov     rcx, rdi; this
0x18000b763  call    ?InitMachineName@CEventLogResult@@AEAAJXZ; CEventLogResult::InitMachineName(void)
0x18000b768  mov     ebx, eax
0x18000b76a  test    eax, eax
0x18000b76c  js      loc_18000C3E6
0x18000b772  mov     rax, cs:WPP_GLOBAL_Control
0x18000b779  mov     dil, 4
0x18000b77c  cmp     rax, rsi
0x18000b77f  jz      short loc_18000B7B3
0x18000b781  cmp     [rax+19h], dil
0x18000b785  jb      short loc_18000B7B3
0x18000b787  test    [rax+1Ch], ebp
0x18000b78a  jz      short loc_18000B7B3
0x18000b78c  lea     rcx, aInitializingCt; "Initializing CTunnelPassword class"
0x18000b793  call    WppDbgPrint
0x18000b798  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b79f  mov     edx, 10h
0x18000b7a4  mov     r9, r14
0x18000b7a7  mov     r8, r15
0x18000b7aa  mov     rcx, [rcx+10h]
0x18000b7ae  call    WPP_SF_s
0x18000b7b3  mov     ebx, 1
0x18000b7b8  mov     ecx, ebx; Size
0x18000b7ba  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000b7bf  mov     [r13+0A8h], rax
0x18000b7c6  test    rax, rax
0x18000b7c9  jnz     short loc_18000B811
0x18000b7cb  mov     rax, cs:WPP_GLOBAL_Control
0x18000b7d2  cmp     rax, rsi
0x18000b7d5  jz      short loc_18000B807
0x18000b7d7  cmp     byte ptr [rax+19h], 2
0x18000b7db  jb      short loc_18000B807
0x18000b7dd  test    [rax+1Ch], ebp
0x18000b7e0  jz      short loc_18000B807
0x18000b7e2  lea     rcx, aUnableToCreate_7; "Unable to create Tunnel-Password object"...
0x18000b7e9  call    WppDbgPrint
0x18000b7ee  lea     edx, [rbx+10h]
0x18000b7f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b7f8  mov     r9, r14
0x18000b7fb  mov     r8, r15
0x18000b7fe  mov     rcx, [rcx+10h]
0x18000b802  call    WPP_SF_s
0x18000b807  mov     ebx, 80004005h
0x18000b80c  jmp     loc_18000C440
0x18000b811  mov     rax, cs:WPP_GLOBAL_Control
0x18000b818  cmp     rax, rsi
0x18000b81b  jz      short loc_18000B84F
0x18000b81d  cmp     [rax+19h], dil
0x18000b821  jb      short loc_18000B84F
0x18000b823  test    [rax+1Ch], ebp
0x18000b826  jz      short loc_18000B84F
0x18000b828  lea     rcx, aInitializingVs; "Initializing VSAFilter class"
0x18000b82f  call    WppDbgPrint
0x18000b834  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b83b  mov     edx, 12h
0x18000b840  mov     r9, r14
0x18000b843  mov     r8, r15
0x18000b846  mov     rcx, [rcx+10h]
0x18000b84a  call    WPP_SF_s
0x18000b84f  mov     rcx, rbx; Size
0x18000b852  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000b857  mov     [r13+0B0h], rax
0x18000b85e  test    rax, rax
0x18000b861  jnz     short loc_18000B890
0x18000b863  mov     rax, cs:WPP_GLOBAL_Control
0x18000b86a  cmp     rax, rsi
0x18000b86d  jz      short loc_18000B807
0x18000b86f  cmp     byte ptr [rax+19h], 2
0x18000b873  jb      short loc_18000B807
0x18000b875  test    [rax+1Ch], ebp
0x18000b878  jz      short loc_18000B807
0x18000b87a  lea     rcx, aUnableToCreate_3; "Unable to create VSA-Filter object in C"...
0x18000b881  call    WppDbgPrint
0x18000b886  mov     edx, 13h
0x18000b88b  jmp     loc_18000B7F1
0x18000b890  call    ?initialize@VSADictionary@@QEAAJXZ; VSADictionary::initialize(void)
0x18000b895  mov     ebx, eax
0x18000b897  test    eax, eax
0x18000b899  jns     short loc_18000B8F2
0x18000b89b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8a2  cmp     rcx, rsi
0x18000b8a5  jz      short loc_18000B8D9
0x18000b8a7  cmp     byte ptr [rcx+19h], 2
0x18000b8ab  jb      short loc_18000B8D9
0x18000b8ad  test    [rcx+1Ch], ebp
0x18000b8b0  jz      short loc_18000B8D9
0x18000b8b2  lea     rcx, aUnableToInital; "Unable to initalize VSA-Filter object i"...
0x18000b8b9  call    WppDbgPrint
0x18000b8be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8c5  mov     edx, 14h
0x18000b8ca  mov     r9, r14
0x18000b8cd  mov     r8, r15
0x18000b8d0  mov     rcx, [rcx+10h]
0x18000b8d4  call    WPP_SF_s
0x18000b8d9  mov     rcx, [r13+0B0h]; Block
0x18000b8e0  call    cs:__imp_free
0x18000b8e6  mov     [r13+0B0h], r12
0x18000b8ed  jmp     loc_18000C440
0x18000b8f2  mov     rax, cs:WPP_GLOBAL_Control
0x18000b8f9  cmp     rax, rsi
0x18000b8fc  jz      short loc_18000B930
0x18000b8fe  cmp     [rax+19h], dil
0x18000b902  jb      short loc_18000B930
0x18000b904  test    [rax+1Ch], ebp
0x18000b907  jz      short loc_18000B930
0x18000b909  lea     rcx, aInitializingCp_1; "Initializing CPacketSender class"
0x18000b910  call    WppDbgPrint
0x18000b915  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b91c  mov     edx, 15h
0x18000b921  mov     r9, r14
0x18000b924  mov     r8, r15
0x18000b927  mov     rcx, [rcx+10h]
0x18000b92b  call    WPP_SF_s
0x18000b930  mov     ecx, 68h ; 'h'; Size
0x18000b935  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000b93a  mov     rbx, rax
0x18000b93d  test    rax, rax
0x18000b940  jz      short loc_18000B956
0x18000b942  mov     rcx, rax; this
0x18000b945  call    ??0CPacketIo@@QEAA@XZ; CPacketIo::CPacketIo(void)
0x18000b94a  lea     rax, ??_7CPacketSender@@6B@; const CPacketSender::`vftable'
0x18000b951  mov     [rbx], rax
0x18000b954  jmp     short loc_18000B959
0x18000b956  mov     rbx, r12
0x18000b959  mov     [r13+90h], rbx
0x18000b960  test    rbx, rbx
0x18000b963  jnz     short loc_18000B99C
0x18000b965  mov     rax, cs:WPP_GLOBAL_Control
0x18000b96c  cmp     rax, rsi
0x18000b96f  jz      loc_18000B6AB
0x18000b975  cmp     byte ptr [rax+19h], 2
0x18000b979  jb      loc_18000B6AB
0x18000b97f  test    [rax+1Ch], ebp
0x18000b982  jz      loc_18000B6AB
0x18000b988  lea     rcx, aUnableToCreate_1; "Unable to create Packet-Sender object i"...
0x18000b98f  call    WppDbgPrint
0x18000b994  lea     edx, [rbx+16h]
0x18000b997  jmp     loc_18000B695
0x18000b99c  mov     rcx, rbx; this
0x18000b99f  call    ?FinalConstruct@Perimeter@@QEAAJXZ; Perimeter::FinalConstruct(void)
0x18000b9a4  mov     ebx, eax
0x18000b9a6  test    eax, eax
0x18000b9a8  js      loc_18000C440
0x18000b9ae  mov     rax, cs:WPP_GLOBAL_Control
0x18000b9b5  cmp     rax, rsi
0x18000b9b8  jz      short loc_18000B9EC
0x18000b9ba  cmp     [rax+19h], dil
0x18000b9be  jb      short loc_18000B9EC
0x18000b9c0  test    [rax+1Ch], ebp
0x18000b9c3  jz      short loc_18000B9EC
0x18000b9c5  lea     rcx, aInitializingCh; "Initializing CHashHmacMD5 class"
0x18000b9cc  call    WppDbgPrint
0x18000b9d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b9d8  mov     edx, 17h
0x18000b9dd  mov     r9, r14
0x18000b9e0  mov     r8, r15
0x18000b9e3  mov     rcx, [rcx+10h]
0x18000b9e7  call    WPP_SF_s
0x18000b9ec  mov     ebx, 8
0x18000b9f1  mov     ecx, ebx; Size
0x18000b9f3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000b9f8  test    rax, rax
0x18000b9fb  jz      short loc_18000BA09
0x18000b9fd  lea     rcx, ??_7CHashHmacMD5@@6B@; const CHashHmacMD5::`vftable'
0x18000ba04  mov     [rax], rcx
0x18000ba07  jmp     short loc_18000BA0C
0x18000ba09  mov     rax, r12
0x18000ba0c  mov     [r13+80h], rax
0x18000ba13  test    rax, rax
0x18000ba16  jnz     short loc_18000BA51
0x18000ba18  mov     rax, cs:WPP_GLOBAL_Control
0x18000ba1f  cmp     rax, rsi
0x18000ba22  jz      loc_18000B6AB
0x18000ba28  cmp     byte ptr [rax+19h], 2
  ... truncated ...
```
