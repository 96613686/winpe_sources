# TcpCreateAndConnectTcb

- ea: `0x1400fb040`
- end: `0x1400fbee7`
- name: `TcpCreateAndConnectTcb`
- size: `3751`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400fb010`

## callees

- `0x1400158e0`
- `0x140017060`
- `0x1400175b0`
- `0x140024850`
- `0x14002f4a0`
- `0x140039b00`
- `0x140052870`
- `0x140054010`
- `0x140054138`
- `0x1400ae7f8`
- `0x1400b5730`
- `0x1400b82e0`
- `0x1400d2500`
- `0x1400fb040`
- `0x1400ff4e0`
- `0x140109488`
- `0x1401154a8`
- `0x14011e6e8`
- `0x14012d104`
- `0x140130290`
- `0x14015f97c`
- `0x1401bf4d0`
- `0x1401bf700`
- `0x1401bf780`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x1400fbde1`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x1400fbde1`
- `ntoskrnl!ObfReferenceObject` at `0x1400fb713`
- `ntoskrnl!ObfReferenceObject` at `0x1400fb9e0`
- `ntoskrnl!ObfReferenceObject` at `0x1400fbb03`
- `ntoskrnl!ObfReferenceObject` at `0x1400fbce8`
- `ntoskrnl!ObfReferenceObject` at `0x1400fb713`
- `ntoskrnl!ObfReferenceObject` at `0x1400fb9e0`
- `ntoskrnl!ObfReferenceObject` at `0x1400fbb03`
- `ntoskrnl!ObfReferenceObject` at `0x1400fbce8`
- `ntoskrnl!KeBugCheck` at `0x1400fbe73`
- `ntoskrnl!KeBugCheck` at `0x1400fbe73`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1400fb6ef`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1400fb88d`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1400fb6ef`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1400fb88d`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400fb496`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400fb569`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400fb496`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400fb569`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400fb445`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400fb445`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400fb3ec`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400fb3ec`
- `ntoskrnl!SeAccessCheck` at `0x1400fb432`
- `ntoskrnl!SeAccessCheck` at `0x1400fb432`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x1400fb3e0`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x1400fb3e0`
- `ntoskrnl!PsGetProcessId` at `0x1400fb47c`
- `ntoskrnl!PsGetProcessId` at `0x1400fb54f`
- `ntoskrnl!PsGetProcessId` at `0x1400fb47c`
- `ntoskrnl!PsGetProcessId` at `0x1400fb54f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400fbe17`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400fbe17`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400fbdb3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400fbdb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400fb0d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400fb0d9`
- `ntoskrnl!ExAllocatePool2` at `0x1400fb606`
- `ntoskrnl!ExAllocatePool2` at `0x1400fb606`
- `ntoskrnl!EtwWriteTransfer` at `0x1400fb28b`
- `ntoskrnl!EtwWriteTransfer` at `0x1400fb28b`
- `NETIO!NetioInsertWorkQueue` at `0x1400fbec7`
- `NETIO!NetioInsertWorkQueue` at `0x1400fbec7`
- `NETIO!KfdIsTfoIncompatibleFilterPresent` at `0x1400fb199`
- `NETIO!KfdIsTfoIncompatibleFilterPresent` at `0x1400fb199`
- `NETIO!NetioNrtAssociateContext` at `0x1400fbc0c`
- `NETIO!NetioNrtAssociateContext` at `0x1400fbc0c`
- `NETIO!RtlInsertElementGenericTableBasicAvl` at `0x1400fbe04`
- `NETIO!RtlInsertElementGenericTableBasicAvl` at `0x1400fbe04`

## string_xrefs

- `0x1400fb7fd`: `Initializing Template Connect TCB`

## pseudocode

```c
__int64 __fastcall TcpCreateAndConnectTcb(KSPIN_LOCK a1, __int64 a2, __int64 a3)
{
  __int16 *v4; // rdx
  __int16 v7; // cx
  int v8; // eax
  __int64 v9; // r13
  __int64 v10; // rdi
  void *v11; // rcx
  _WORD *v12; // rax
  char v13; // al
  char v15; // al
  __int64 v16; // rbx
  __int64 v17; // r8
  KSPIN_LOCK *v18; // rax
  KSPIN_LOCK *v19; // rsi
  __int64 v20; // r8
  const wchar_t *v21; // r9
  struct _KPROCESS *v22; // rsi
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v24; // bl
  unsigned __int8 v25; // al
  char v26; // bl
  ADDRESS_FAMILY *v27; // r11
  UCHAR v28; // al
  char v29; // dl
  int v30; // r8d
  __int64 v31; // r10
  __int64 v32; // r11
  unsigned __int8 ProcessId; // al
  char v34; // bl
  ADDRESS_FAMILY *v35; // r11
  UCHAR v36; // al
  char v37; // dl
  int v38; // r8d
  __int64 v39; // r10
  __int64 v40; // r11
  __int64 Pool2; // rax
  int v42; // ecx
  KSPIN_LOCK v43; // rax
  unsigned __int8 v44; // dl
  int v45; // eax
  void *ClientProcess; // rax
  __int64 ProcessTag; // rax
  KSPIN_LOCK v48; // rcx
  __int64 v49; // rdx
  __int64 v50; // rcx
  KSPIN_LOCK v51; // rax
  void *v52; // rcx
  KSPIN_LOCK v53; // rcx
  __int64 v54; // rdx
  __int64 v55; // rax
  __int64 (__fastcall *v56)(struct _SECURITY_SUBJECT_CONTEXT *); // rdx
  int v57; // eax
  unsigned __int8 v58; // cl
  void *v59; // rcx
  KSPIN_LOCK v60; // rcx
  __int64 v61; // rdx
  __int64 v62; // rax
  __int64 (__fastcall *v63)(struct _SECURITY_SUBJECT_CONTEXT *); // rdx
  int v64; // eax
  unsigned __int8 ProcessAuditId; // cl
  __int64 v66; // r8
  char v67; // al
  char v68; // al
  KSPIN_LOCK v69; // rcx
  void *v70; // rcx
  UCHAR v71; // al
  UCHAR v72; // al
  const void *v73; // rdx
  char *v74; // rdi
  KIRQL v75; // al
  void *v76; // rdx
  KIRQL v77; // r14
  KSPIN_LOCK v78; // r8
  __int64 v79; // rax
  __int64 v80; // r8
  __int64 v81; // r15
  _QWORD *v82; // rdx
  char UserDataCount; // [rsp+20h] [rbp-69h]
  char UserData; // [rsp+28h] [rbp-61h]
  PEVENT_DATA_DESCRIPTOR UserDataa; // [rsp+28h] [rbp-61h]
  int AccessStatus; // [rsp+60h] [rbp-29h] BYREF
  TABLE_SEARCH_RESULT SearchResult; // [rsp+64h] [rbp-25h] BYREF
  DWORD GrantedAccess; // [rsp+68h] [rbp-21h] BYREF
  PVOID NodeOrParent; // [rsp+70h] [rbp-19h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+78h] [rbp-11h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT v91; // [rsp+88h] [rbp-1h] BYREF

  v4 = *(__int16 **)(a2 + 88);
  NodeOrParent = 0;
  SearchResult = TableEmptyTree;
  *(_QWORD *)&EventDescriptor.Id = a3;
  if ( !v4[1] )
    return 3221225991LL;
  v7 = *v4;
  if ( *v4 != 2 && v7 != 23 )
    return 3221225991LL;
  v8 = *(_DWORD *)(a2 + 16);
  v9 = 0;
  if ( v8 < 0 )
  {
    v10 = *(_QWORD *)(a2 + 24);
    v11 = *(void **)(v10 + 296);
    if ( v11 )
    {
      ExFreePoolWithTag(v11, 0x49546354u);
      *(_QWORD *)(v10 + 296) = 0;
    }
    if ( (*(_DWORD *)(v10 + 16) & 8) == 0
      || (v12 = *(_WORD **)(a2 + 88), *v12 != 23)
      || !v12[4] && !v12[5] && !v12[6] && !v12[7] && !v12[8] && v12[9] == 0xFFFF )
    {
      v13 = *(_BYTE *)(v10 + 205);
      if ( (v13 & 4) != 0 )
        return 3221225860LL;
      if ( a3 )
      {
        if ( (v13 & 0x10) == 0 )
          return 3221226029LL;
        if ( (unsigned __int8)KfdIsTfoIncompatibleFilterPresent() )
        {
          if ( !dword_1402244A0
            && !_InterlockedCompareExchange(&dword_1402244A0, 1, 0)
            && (unsigned int)dword_1402201F8 > 5
            && (qword_140220208 & 0x400000000000LL) != 0
            && (qword_140220210 & 0x400000000000LL) == qword_140220210 )
          {
            *(_DWORD *)&EventDescriptor.Level = 5;
            v91.ClientToken = off_140220200;
            EventDescriptor.Keyword = 0x400000000000LL;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            v91.ImpersonationLevel = *(unsigned __int16 *)off_140220200;
            v91.PrimaryToken = &byte_1401F2F57;
            *((_DWORD *)&v91.ImpersonationLevel + 1) = 2;
            v91.ProcessAuditId = (PVOID)0x10000001FLL;
            AccessStatus = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, (PEVENT_DATA_DESCRIPTOR)&v91);
          }
          if ( dword_1402201D4 && *((char *)&WPP_MAIN_CB.Reserved + 11) < 0 )
          {
            EventDescriptor.Keyword = 0;
            *(_QWORD *)&EventDescriptor.Id = v10;
            McTemplateK0p_EtwWriteTransfer(
              &MICROSOFT_TCPIP_PROVIDER_Context,
              TCP_FASTOPEN_INCOMPAT_CALLOUT,
              &EventDescriptor,
              v10);
          }
          v15 = *(_BYTE *)(v10 + 205);
          if ( (v15 & 0x10) != 0 )
            *(_BYTE *)(v10 + 205) = v15 & 0xEF;
          return 3221226029LL;
        }
      }
      v16 = *(_QWORD *)(v10 + 32);
      goto LABEL_44;
    }
    return 3221226044LL;
  }
  v10 = 0;
  if ( (v8 & 0x40000000) != 0 )
  {
    v9 = *(_QWORD *)(a2 + 24);
    if ( (*(_DWORD *)(v9 + 32) & 8) == 0 || v7 != 23 || !v4[4] && !v4[5] && !v4[6] && !v4[7] && !v4[8] && v4[9] == -1 )
    {
      v16 = *(_QWORD *)(v9 + 48);
LABEL_44:
      v17 = *(_QWORD *)(v16 + 16);
      if ( (_InterlockedExchangeAdd64(
              (volatile signed __int64 *)(*(_QWORD *)v17
                                        + (unsigned int)(*(_DWORD *)(v17 + 16)
                                                       * (HIDWORD(KeGetPcr()[1].LockArray) % *(_DWORD *)(v17 + 20)))),
              2u)
          & 1) != 0 )
        _InterlockedAdd64((volatile signed __int64 *)(v17 + 24), 2u);
LABEL_46:
      v18 = (KSPIN_LOCK *)PplAllocateFromLookasideList(TcpTcbPool);
      v19 = v18;
      if ( !v18 )
      {
        InetDereferenceAf(v16);
        if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
        {
          v21 = L"TCB allocation (TCP)";
LABEL_64:
          McTemplateK0z_EtwWriteTransfer(&MICROSOFT_TCPIP_PROVIDER_Context, TCPIP_MEMORY_FAILURES, v20, v21);
          return 3221225495LL;
        }
        return 3221225495LL;
      }
      TcpInitializeTcb(v18);
      *((_WORD *)v19 + 402) |= 0x80u;
      Pool2 = ExAllocatePool2(64, 368, 1380148052);
      v19[85] = Pool2;
      if ( !Pool2 )
      {
        PplFreeToLookasideList(TcpTcbPool);
        InetDereferenceAf(v16);
        if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
        {
          v21 = L"TCB Connect Request Pool (TCP)";
          goto LABEL_64;
        }
        return 3221225495LL;
      }
      TcpipTraceActivityIDStart(v19, 7);
      *((_DWORD *)v19 + 28) = 2;
      v19[3] = v16;
      v19[2] = a1;
      if ( _InterlockedIncrement64((volatile signed __int64 *)(a1 + 16)) <= 1 )
        __fastfail(0xEu);
      v42 = *((_DWORD *)v19 + 202);
      v43 = v19[3];
      *((_DWORD *)v19 + 30) |= 1u;
      v44 = *(_BYTE *)(v43 + 162);
      v45 = v42 ^ ((unsigned __int16)v42 ^ (unsigned __int16)(v44 << 10)) & 0x400;
      *((_DWORD *)v19 + 202) = v45;
      if ( (v44 & 1) != 0 )
        *((_DWORD *)v19 + 202) = v45 | 0x1800;
      if ( v10 )
      {
        if ( !v9 )
        {
          v59 = *(void **)(v10 + 40);
          v19[106] = (KSPIN_LOCK)v59;
          ObfReferenceObject(v59);
          v60 = v19[3];
          v19[108] = *(_QWORD *)(v10 + 64);
          v19[112] = *(_QWORD *)(v10 + 72);
          if ( *(_QWORD *)(v10 + 32) == v60 )
          {
            v61 = *(_QWORD *)(v10 + 208);
          }
          else if ( v60 == *(_QWORD *)(v10 + 232) )
          {
            v61 = *(_QWORD *)(v10 + 224);
          }
          else
          {
            v61 = 0;
          }
          v91.ClientToken = *(PACCESS_TOKEN *)(v60 + 40);
          v62 = *(_QWORD *)(v60 + 48);
          *(_OWORD *)&v91.PrimaryToken = 0;
          *(_QWORD *)&v91.ImpersonationLevel = v61;
          v63 = *(__int64 (__fastcall **)(struct _SECURITY_SUBJECT_CONTEXT *))(v62 + 272);
          if ( (char *)v63 == (char *)IpNlpInheritSessionInfo )
            v64 = IpNlpInheritSessionInfo(&v91);
          else
            v64 = v63(&v91);
          if ( v64 < 0 )
          {
            v19[114] = 0;
            ProcessAuditId = 0;
          }
          else
          {
            ProcessAuditId = (unsigned __int8)v91.ProcessAuditId;
            v19[114] = (KSPIN_LOCK)v91.PrimaryToken;
          }
          *((_DWORD *)v19 + 202) ^= ((unsigned __int16)*((_DWORD *)v19 + 202)
                                   ^ (unsigned __int16)(ProcessAuditId << 15))
                                  & 0x8000;
          *(_OWORD *)(v19 + 95) = *(_OWORD *)(v10 + 168);
          *(_OWORD *)(v19 + 97) = *(_OWORD *)(v10 + 184);
          v19[99] = *(_QWORD *)(v10 + 200);
          v66 = *(_QWORD *)(v10 + 288);
          if ( v66 )
          {
            v67 = NetioNrtAssociateContext(v19, 0, v66, v19 + 139);
            if ( dword_1402201D4 )
            {
              if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 10) & 0x20) != 0 )
              {
                UserDataa = *(PEVENT_DATA_DESCRIPTOR *)(v10 + 288);
                *(_QWORD *)&v91.ImpersonationLevel = 0;
                v91.ClientToken = v19;
                McTemplateK0pqpq_EtwWriteTransfer(
                  (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
                  v49,
                  (unsigned int)&v91,
                  (_DWORD)v19,
                  1,
                  (char)UserDataa,
                  v67);
              }
            }
          }
          if ( Microsoft_Windows_Networking_CorrelationEnabled )
            TcpipEtwTransferActivity(v19, v10, 6);
          goto LABEL_79;
        }
      }
      else if ( !v9 )
      {
        KeQuerySystemTimePrecise(v19 + 108);
        ClientProcess = *(void **)(a2 + 40);
        if ( !ClientProcess )
          ClientProcess = (void *)InetGetClientProcess();
        v19[106] = (KSPIN_LOCK)ClientProcess;
        ObfReferenceObject(ClientProcess);
        ProcessTag = InetGetProcessTag(*(_QWORD *)(a2 + 40), *(_QWORD *)(a2 + 48));
        v48 = v19[3];
        v19[112] = ProcessTag;
        TcpInitializeOptions(v48, v19 + 95);
        if ( (*(_DWORD *)(a2 + 16) & 0x20000000) != 0 )
          *((_BYTE *)v19 + 798) |= 0x40u;
        if ( Microsoft_Windows_Networking_CorrelationEnabled )
        {
          v49 = *(_QWORD *)(a2 + 32);
          if ( v49 )
            TcpipEtwTransferActivity(v19, v49, 4);
        }
LABEL_79:
        *((_WORD *)v19 + 402) &= (*((_BYTE *)v19 + 798) >> 6 << 11) | 0xF7FF;
        if ( dword_1402201D4 )
        {
          if ( SBYTE2(WPP_MAIN_CB.Reserved) < 0 )
          {
            *(_QWORD *)&v91.ImpersonationLevel = 0;
            v91.ClientToken = v19;
            McTemplateK0p_EtwWriteTransfer(&MICROSOFT_TCPIP_PROVIDER_Context, TCP_SEND_TRACKER_ENABLED, &v91, v19);
          }
          if ( dword_1402201D4 )
          {
            if ( (!TcpipTraceFiltersExist || *((char *)v19 + 804) < 0) && (HIBYTE(WPP_MAIN_CB.Reserved) & 1) != 0 )
            {
              UserDataCount = *((_BYTE *)v19 + 756);
              *(_QWORD *)&v91.ImpersonationLevel = 0;
              v91.ClientToken = v19;
              McTemplateK0pqz_EtwWriteTransfer(
                (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
                v49,
                (unsigned int)&v91,
                (_DWORD)v19,
                UserDataCount,
                (__int64)L"Initializing Template Connect TCB");
            }
            if ( dword_1402201D4
              && (!TcpipTraceFiltersExist || *((char *)v19 + 804) < 0)
              && (BYTE1(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
            {
              UserData = *((_DWORD *)v19 + 35);
              *(_QWORD *)&v91.ImpersonationLevel = 0;
              v91.ClientToken = v19;
              McTemplateK0qqqp_EtwWriteTransfer(
                (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
                v49,
                (unsigned int)&v91,
                0,
                2,
                UserData,
                (char)v19);
            }
          }
        }
        KeQuerySystemTimePrecise(v19 + 111);
        *(_QWORD *)v19[85] = *(_QWORD *)a2;
        *(_QWORD *)(v19[85] + 8) = *(_QWORD *)(a2 + 8);
        *(_QWORD *)(v19[85] + 56) = v19;
        *(_QWORD *)(v19[85] + 64) = v10;
        *(_QWORD *)(v19[85] + 72) = v9;
        *(_QWORD *)(v19[85] + 104) = *(_QWORD *)(a2 + 96);
        *(_QWORD *)(v19[85] + 120) = *(_QWORD *)(a2 + 72);
        *(_QWORD *)(v19[85] + 112) = *(_QWORD *)(a2 + 112);
        v50 = *(_QWORD *)&EventDescriptor.Id;
        if ( *(_QWORD *)&EventDescriptor.Id )
        {
          v51 = v19[85];
          *(_OWORD *)(v51 + 280) = *(_OWORD *)*(_QWORD *)&EventDescriptor.Id;
          *(_OWORD *)(v51 + 296) = *(_OWORD *)(v50 + 16);
          *(_OWORD *)(v51 + 312) = *(_OWORD *)(v50 + 32);
          *(_OWORD *)(v51 + 328) = *(_OWORD *)(v50 + 48);
          *(_OWORD *)(v51 + 344) = *(_OWORD *)(v50 + 64);
          *(_QWORD *)(v51 + 360) = *(_QWORD *)(v50 + 80);
          *((_WORD *)v19 + 64) |= 0x300u;
          if ( (*((_BYTE *)v19 + 797) & 0x10) != 0
            && dword_1402201D4
            && (!TcpipTraceFiltersExist || *((char *)v19 + 804) < 0)
            && *((char *)&WPP_MAIN_CB.Reserved + 11) < 0 )
          {
            *(_QWORD *)&v91.ImpersonationLevel = 0;
            v91.ClientToken = v19;
            McTemplateK0p_EtwWriteTransfer(&MICROSOFT_TCPIP_PROVIDER_Context, TCP_FASTOPEN_REQUESTED, &v91, v19);
          }
        }
        else
        {
          v68 = *((_BYTE *)v19 + 797);
          if ( (v68 & 0x10) != 0 )
            *((_BYTE *)v19 + 797) = v68 & 0xEF;
        }
        if ( v10 || v9 )
        {
          v19[107] = 0;
          v69 = v19[85];
          if ( v9 )
            *(_QWORD *)(v69 + 88) = 0;
          else
            *(_QWORD *)(v69 + 88) = *(_QWORD *)(v10 + 48);
        }
        else
        {
          *(_QWORD *)(v19[85] + 88) = *(_QWORD *)(a2 + 48);
          v19[107] = *(_QWORD *)(a2 + 56);
        }
        v70 = *(void **)(v19[85] + 88);
        if ( v70 )
          ObfReferenceObject(v70);
        if ( !v9 && (!v10 || (*(_DWORD *)(v10 + 16) & 1) == 0) )
        {
          v71 = SOCKADDR_SIZE(*(_WORD *)(v19[3] + 24));
          memmove((void *)(v19[85] + 156), *(const void **)(a2 + 64), v71);
        }
        v72 = SOCKADDR_SIZE(**(_WORD **)(a2 + 88));
        memmove((void *)(v19[85] + 184), v73, v72);
        *((_DWORD *)v19 + 168) = HIDWORD(KeGetPcr()[1].LockArray);
        *(_QWORD *)(v19[85] + 48) = 0;
        *(_DWORD *)(v19[85] + 48) = *((_DWORD *)v19 + 168);
        v74 = (char *)TcpCreateAndConnectTcbCancelQueue + 120 * *((unsigned int *)v19 + 168);
        *(_DWORD *)(v19[85] + 52) = _InterlockedExchangeAdd64((volatile signed __int64 *)v74 + 1, 1u) + 1;
        *(_QWORD *)(a2 + 104) = *(_QWORD *)(v19[85] + 48);
        v75 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v74);
        v76 = (void *)(v19[85] + 48);
        *((_BYTE *)v19 + 676) = 0;
        v77 = v75;
        RtlLookupElementGenericTableFullAvl((PRTL_AVL_TABLE)(v74 + 16), v76, &NodeOrParent, &SearchResult);
        RtlInsertElementGenericTableBasicAvl(v74 + 16, v19[85] + 16, NodeOrParent, (unsigned int)SearchResult);
        KeReleaseSpinLock((PKSPIN_LOCK)v74, v77);
        v78 = v19[85];
        v79 = *(_QWORD *)(v78 + 72);
        if ( v79 )
        {
          if ( _InterlockedIncrement64((volatile signed __int64 *)(v79 + 24)) <= 1 )
            __fastfail(0xEu);
          *(_BYTE *)(v19[85] + 81) = 1;
        }
        else
        {
          v80 = *(_QWORD *)(v78 + 64);
          if ( v80 )
          {
            v81 = _InterlockedIncrement64((volatile signed __int64 *)(v80 + 8));
            if ( v81 <= 1 )
              KeBugCheck(0x1Cu);
            if ( EndpointReferenceHistory )
              RhAppendHistory(EndpointReferenceHistory, (unsigned int)v81, v80);
            *(_BYTE *)(v19[85] + 80) = 1;
          }
        }
        v82 = v19 + 87;
        if ( v77 )
        {
          NetioInsertWorkQueue(TcpCreateAndConnectTcbWorkQueue, v82);
        }
        else
        {
          *v82 = 0;
          TcpCreateAndConnectTcbWorkQueueRoutine(v19 + 87);
        }
        return 259;
      }
      v52 = *(void **)(v9 + 56);
      v19[106] = (KSPIN_LOCK)v52;
      ObfReferenceObject(v52);
      v53 = v19[3];
      v19[108] = *(_QWORD *)(v9 + 72);
      v19[112] = *(_QWORD *)(v9 + 80);
      if ( *(_QWORD *)(v9 + 48) == v53 )
      {
        v54 = *(_QWORD *)(v9 + 280);
      }
      else if ( v53 == *(_QWORD *)(v9 + 304) )
      {
        v54 = *(_QWORD *)(v9 + 296);
      }
      else
      {
        v54 = 0;
      }
      v91.ClientToken = *(PACCESS_TOKEN *)(v53 + 40);
      v55 = *(_QWORD *)(v53 + 48);
      *(_OWORD *)&v91.PrimaryToken = 0;
      *(_QWORD *)&v91.ImpersonationLevel = v54;
      v56 = *(__int64 (__fastcall **)(struct _SECURITY_SUBJECT_CONTEXT *))(v55 + 272);
      if ( (char *)v56 == (char *)IpNlpInheritSessionInfo )
        v57 = IpNlpInheritSessionInfo(&v91);
      else
        v57 = v56(&v91);
      if ( v57 < 0 )
      {
        v19[114] = 0;
        v58 = 0;
      }
      else
      {
        v58 = (unsigned __int8)v91.ProcessAuditId;
        v19[114] = (KSPIN_LOCK)v91.PrimaryToken;
      }
      *((_DWORD *)v19 + 202) ^= ((unsigned __int16)*((_DWORD *)v19 + 202) ^ (unsigned __int16)(v58 << 15)) & 0x8000;
      *(_OWORD *)(v19 + 95) = *(_OWORD *)(v9 + 240);
      *(_OWORD *)(v19 + 97) = *(_OWORD *)(v9 + 256);
      v19[99] = *(_QWORD *)(v9 + 272);
      if ( Microsoft_Windows_Networking_CorrelationEnabled )
        TcpipEtwTransferActivity(v19, v9, 5);
      goto LABEL_79;
    }
    return 3221226044LL;
  }
  v22 = *(struct _KPROCESS **)(a2 + 40);
  AccessStatus = 0;
  GrantedAccess = 0;
  memset(&v91, 0, sizeof(v91));
  if ( !v22 )
    v22 = (struct _KPROCESS *)InetGetClientProcess();
  SeCaptureSubjectContextEx(*(PETHREAD *)(a2 + 48), v22, &v91);
  GenericMapping = IoGetFileObjectGenericMapping();
  v24 = SeAccessCheck(
          TcpipEndpointCreationSdData,
          &v91,
          0,
          0x1200A9u,
          0,
          0,
          GenericMapping,
          1,
          &GrantedAccess,
          &AccessStatus);
  SeReleaseSubjectContext(&v91);
  if ( v24 )
  {
    v16 = InetFindAndReferenceAf(&TcpInetTransport, **(unsigned __int16 **)(a2 + 64));
    if ( v16 )
      goto LABEL_46;
    if ( dword_1402201D4 )
    {
      EventDescriptor = 0;
      if ( (BYTE1(WPP_MAIN_CB.Reserved) & 8) != 0 )
      {
        ProcessId = (unsigned __int8)PsGetProcessId(v22);
        EventDescriptor.Keyword = 0;
        v34 = ProcessId;
        *(_QWORD *)&EventDescriptor.Id = 0;
        PsGetProcessStartKey(v22);
        SOCKADDR_SIZE(**(_WORD **)(a2 + 88));
        v36 = SOCKADDR_SIZE(*v35);
        McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCP_CONNECT_TCB_FAILED_AF_V1,
          (unsigned int)&EventDescriptor,
          v36,
          v40,
          v38,
          v39,
          0,
          v34,
          0,
          0,
          v37);
      }
    }
    return 3221225488LL;
  }
  else
  {
    if ( dword_1402201D4 )
    {
      EventDescriptor = 0;
      if ( (BYTE1(WPP_MAIN_CB.Reserved) & 8) != 0 )
      {
        v25 = (unsigned __int8)PsGetProcessId(v22);
        EventDescriptor.Keyword = 0;
        v26 = v25;
        *(_QWORD *)&EventDescriptor.Id = 0;
        PsGetProcessStartKey(v22);
        SOCKADDR_SIZE(**(_WORD **)(a2 + 88));
        v28 = SOCKADDR_SIZE(*v27);
        McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCP_CONNECT_TCB_FAILED_ACCESS_V1,
          (unsigned int)&EventDescriptor,
          v28,
          v32,
          v30,
          v31,
          0,
          v26,
          0,
          0,
          v29);
      }
    }
    return (unsigned int)AccessStatus;
  }
}

```

## disassembly

```asm
0x1400fb040  push    rbp
0x1400fb042  push    rbx
0x1400fb043  push    r12
0x1400fb045  push    r14
0x1400fb047  push    r15
0x1400fb049  lea     rbp, [rsp-37h]
0x1400fb04e  sub     rsp, 0C0h
0x1400fb055  mov     rax, cs:__security_cookie
0x1400fb05c  xor     rax, rsp
0x1400fb05f  mov     [rbp+57h+var_38], rax
0x1400fb063  xor     r15d, r15d
0x1400fb066  mov     r14, rdx
0x1400fb069  mov     rdx, [rdx+58h]
0x1400fb06d  mov     rbx, r8
0x1400fb070  mov     [rbp+57h+NodeOrParent], r15
0x1400fb074  mov     r12, rcx
0x1400fb077  mov     [rbp+57h+SearchResult], r15d
0x1400fb07b  mov     qword ptr [rbp+57h+EventDescriptor.Id], rbx
0x1400fb07f  cmp     [rdx+2], r15w
0x1400fb084  jz      loc_1400FBEDD
0x1400fb08a  movzx   ecx, word ptr [rdx]
0x1400fb08d  cmp     cx, 2
0x1400fb091  jz      short loc_1400FB09D
0x1400fb093  cmp     cx, 17h
0x1400fb097  jnz     loc_1400FBEDD
0x1400fb09d  mov     eax, [r14+10h]
0x1400fb0a1  mov     [rsp+0E0h+arg_10], rsi
0x1400fb0a9  mov     [rsp+0E0h+var_28], rdi
0x1400fb0b1  mov     [rsp+0E0h+var_30], r13
0x1400fb0b9  mov     r13, r15
0x1400fb0bc  test    eax, eax
0x1400fb0be  jns     loc_1400FB2F1
0x1400fb0c4  mov     rdi, [r14+18h]
0x1400fb0c8  mov     rcx, [rdi+128h]; P
0x1400fb0cf  test    rcx, rcx
0x1400fb0d2  jz      short loc_1400FB0EC
0x1400fb0d4  mov     edx, 49546354h; Tag
0x1400fb0d9  call    cs:__imp_ExFreePoolWithTag
0x1400fb0e0  nop     dword ptr [rax+rax+00h]
0x1400fb0e5  mov     [rdi+128h], r15
0x1400fb0ec  mov     eax, [rdi+10h]
0x1400fb0ef  test    al, 8
0x1400fb0f1  jz      short loc_1400FB143
0x1400fb0f3  mov     rax, [r14+58h]
0x1400fb0f7  cmp     word ptr [rax], 17h
0x1400fb0fb  jnz     short loc_1400FB143
0x1400fb0fd  cmp     [rax+8], r13w
0x1400fb102  jnz     loc_1400FB339
0x1400fb108  cmp     [rax+0Ah], r13w
0x1400fb10d  jnz     loc_1400FB339
0x1400fb113  cmp     [rax+0Ch], r13w
0x1400fb118  jnz     loc_1400FB339
0x1400fb11e  cmp     [rax+0Eh], r13w
0x1400fb123  jnz     loc_1400FB339
0x1400fb129  cmp     [rax+10h], r13w
0x1400fb12e  jnz     loc_1400FB339
0x1400fb134  mov     ecx, 0FFFFh
0x1400fb139  cmp     [rax+12h], cx
0x1400fb13d  jnz     loc_1400FB339
0x1400fb143  movzx   eax, byte ptr [rdi+0CDh]
0x1400fb14a  test    al, 4
0x1400fb14c  jz      short loc_1400FB188
0x1400fb14e  mov     eax, 0C0000184h
0x1400fb153  mov     rdi, [rsp+0E0h+var_28]
0x1400fb15b  mov     rsi, [rsp+0E0h+arg_10]
0x1400fb163  mov     r13, [rsp+0E0h+var_30]
0x1400fb16b  mov     rcx, [rbp+57h+var_38]
0x1400fb16f  xor     rcx, rsp; StackCookie
0x1400fb172  call    __security_check_cookie
0x1400fb177  add     rsp, 0C0h
0x1400fb17e  pop     r15
0x1400fb180  pop     r14
0x1400fb182  pop     r12
0x1400fb184  pop     rbx
0x1400fb185  pop     rbp
0x1400fb186  retn
0x1400fb188  test    rbx, rbx
0x1400fb18b  jz      loc_1400FB2EB
0x1400fb191  test    al, 10h
0x1400fb193  jz      loc_1400FB2E1
0x1400fb199  call    cs:__imp_KfdIsTfoIncompatibleFilterPresent
0x1400fb1a0  nop     dword ptr [rax+rax+00h]
0x1400fb1a5  test    al, al
0x1400fb1a7  jz      loc_1400FB2EB
0x1400fb1ad  cmp     cs:dword_1402244A0, r13d
0x1400fb1b4  jnz     loc_1400FB29A
0x1400fb1ba  xor     eax, eax
0x1400fb1bc  mov     r15d, 1
0x1400fb1c2  lock cmpxchg cs:dword_1402244A0, r15d
0x1400fb1cb  jnz     loc_1400FB297
0x1400fb1d1  mov     eax, cs:dword_1402201F8
0x1400fb1d7  cmp     eax, 5
0x1400fb1da  jbe     loc_1400FB297
0x1400fb1e0  mov     rcx, cs:qword_140220210
0x1400fb1e7  mov     rdx, 400000000000h
0x1400fb1f1  mov     rax, cs:qword_140220208
0x1400fb1f8  test    rdx, rax
0x1400fb1fb  jz      loc_1400FB297
0x1400fb201  mov     rax, rcx
0x1400fb204  and     rax, rdx
0x1400fb207  cmp     rax, rcx
0x1400fb20a  jnz     loc_1400FB297
0x1400fb210  movzx   eax, cs:word_1401F2F4D
0x1400fb217  lea     rcx, _TraceLoggingMetadata
0x1400fb21e  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1400fb221  xor     r9d, r9d; RelatedActivityId
0x1400fb224  mov     rax, cs:off_140220200
0x1400fb22b  xor     r8d, r8d; ActivityId
0x1400fb22e  mov     [rbp+57h+var_58.Ptr], rax
0x1400fb232  mov     [rbp+57h+EventDescriptor.Keyword], rdx
0x1400fb236  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x1400fb23a  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x1400fb241  movzx   eax, word ptr [rax]
0x1400fb244  mov     [rbp+57h+var_58.Size], eax
0x1400fb247  lea     rax, byte_1401F2F57
0x1400fb24e  mov     qword ptr [rbp+57h+var_48], rax
0x1400fb252  lea     rax, _TraceLoggingMetadataEnd
0x1400fb259  sub     eax, ecx
0x1400fb25b  mov     dword ptr [rbp+57h+var_58.0Ch], 2
0x1400fb262  mov     dword ptr [rbp+57h+var_48+8], 1Fh
0x1400fb269  mov     dword ptr [rbp+57h+var_48+0Ch], r15d
0x1400fb26d  mov     [rbp+57h+var_80], eax
0x1400fb270  mov     eax, [rbp+57h+var_80]
0x1400fb273  mov     rcx, cs:RegHandle; RegHandle
0x1400fb27a  lea     rax, [rbp+57h+var_58]
0x1400fb27e  mov     [rsp+0E0h+UserData], rax; UserData
0x1400fb283  mov     [rsp+0E0h+UserDataCount], 2; UserDataCount
0x1400fb28b  call    cs:__imp_EtwWriteTransfer
0x1400fb292  nop     dword ptr [rax+rax+00h]
0x1400fb297  xor     r15d, r15d
0x1400fb29a  cmp     cs:dword_1402201D4, r13d
0x1400fb2a1  jz      short loc_1400FB2CE
0x1400fb2a3  cmp     byte ptr cs:WPP_MAIN_CB+14Bh, r13b
0x1400fb2aa  jge     short loc_1400FB2CE
0x1400fb2ac  mov     r9, rdi
0x1400fb2af  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x1400fb2b3  lea     r8, [rbp+57h+EventDescriptor]
0x1400fb2b7  mov     qword ptr [rbp+57h+EventDescriptor.Id], rdi
0x1400fb2bb  lea     rdx, TCP_FASTOPEN_INCOMPAT_CALLOUT
0x1400fb2c2  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400fb2c9  call    McTemplateK0p_EtwWriteTransfer
0x1400fb2ce  movzx   eax, byte ptr [rdi+0CDh]
0x1400fb2d5  test    al, 10h
0x1400fb2d7  jz      short loc_1400FB2E1
0x1400fb2d9  and     al, 0EFh
0x1400fb2db  mov     [rdi+0CDh], al
0x1400fb2e1  mov     eax, 0C000022Dh
0x1400fb2e6  jmp     loc_1400FB153
0x1400fb2eb  mov     rbx, [rdi+20h]
0x1400fb2ef  jmp     short loc_1400FB347
0x1400fb2f1  mov     rdi, r15
0x1400fb2f4  bt      eax, 1Eh
0x1400fb2f8  jnb     loc_1400FB3B1
0x1400fb2fe  mov     r13, [r14+18h]
0x1400fb302  mov     eax, [r13+20h]
0x1400fb306  test    al, 8
0x1400fb308  jz      short loc_1400FB343
0x1400fb30a  cmp     cx, 17h
0x1400fb30e  jnz     short loc_1400FB343
0x1400fb310  cmp     [rdx+8], di
0x1400fb314  jnz     short loc_1400FB339
0x1400fb316  cmp     [rdx+0Ah], di
0x1400fb31a  jnz     short loc_1400FB339
0x1400fb31c  cmp     [rdx+0Ch], di
0x1400fb320  jnz     short loc_1400FB339
0x1400fb322  cmp     [rdx+0Eh], di
0x1400fb326  jnz     short loc_1400FB339
0x1400fb328  cmp     [rdx+10h], di
0x1400fb32c  jnz     short loc_1400FB339
0x1400fb32e  mov     ecx, 0FFFFh
0x1400fb333  cmp     [rdx+12h], cx
0x1400fb337  jz      short loc_1400FB343
0x1400fb339  mov     eax, 0C000023Ch
0x1400fb33e  jmp     loc_1400FB153
0x1400fb343  mov     rbx, [r13+30h]
0x1400fb347  mov     eax, gs:1A4h
0x1400fb34f  xor     edx, edx
0x1400fb351  mov     r8, [rbx+10h]
0x1400fb355  mov     ecx, 2
0x1400fb35a  div     dword ptr [r8+14h]
0x1400fb35e  imul    edx, [r8+10h]
0x1400fb363  mov     eax, edx
0x1400fb365  add     rax, [r8]
0x1400fb368  lock xadd [rax], rcx
0x1400fb36d  test    cl, 1
0x1400fb370  jz      short loc_1400FB378
0x1400fb372  lock add qword ptr [r8+18h], 2
0x1400fb378  mov     rcx, cs:TcpTcbPool
0x1400fb37f  call    PplAllocateFromLookasideList
0x1400fb384  mov     rsi, rax
0x1400fb387  test    rax, rax
0x1400fb38a  jnz     loc_1400FB5E2
0x1400fb390  mov     rcx, rbx
0x1400fb393  call    _InetDereferenceAf
0x1400fb398  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r15b
0x1400fb39f  jge     loc_1400FB658
0x1400fb3a5  lea     r9, aTcbAllocationT; "TCB allocation (TCP)"
0x1400fb3ac  jmp     loc_1400FB645
0x1400fb3b1  mov     rsi, [r14+28h]
0x1400fb3b5  xorps   xmm0, xmm0
0x1400fb3b8  mov     [rbp+57h+var_80], r15d
0x1400fb3bc  mov     [rbp+57h+var_78], r15d
0x1400fb3c0  movups  xmmword ptr [rbp+57h+var_58.Ptr], xmm0
0x1400fb3c4  movups  [rbp+57h+var_48], xmm0
0x1400fb3c8  test    rsi, rsi
0x1400fb3cb  jnz     short loc_1400FB3D5
0x1400fb3cd  call    InetGetClientProcess
0x1400fb3d2  mov     rsi, rax
0x1400fb3d5  mov     rcx, [r14+30h]; Thread
0x1400fb3d9  lea     r8, [rbp+57h+var_58]; SubjectContext
0x1400fb3dd  mov     rdx, rsi; Process
0x1400fb3e0  call    cs:__imp_SeCaptureSubjectContextEx
0x1400fb3e7  nop     dword ptr [rax+rax+00h]
0x1400fb3ec  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400fb3f3  nop     dword ptr [rax+rax+00h]
0x1400fb3f8  lea     rcx, [rbp+57h+var_80]
0x1400fb3fc  mov     r9d, 1200A9h; DesiredAccess
0x1400fb402  mov     [rsp+0E0h+AccessStatus], rcx; AccessStatus
0x1400fb407  lea     rdx, [rbp+57h+var_58]; SubjectSecurityContext
0x1400fb40b  lea     rcx, [rbp+57h+var_78]
0x1400fb40f  xor     r8d, r8d; SubjectContextLocked
0x1400fb412  mov     [rsp+0E0h+GrantedAccess], rcx; GrantedAccess
0x1400fb417  lea     rcx, TcpipEndpointCreationSdData; SecurityDescriptor
0x1400fb41e  mov     [rsp+0E0h+AccessMode], 1; AccessMode
0x1400fb423  mov     [rsp+0E0h+GenericMapping], rax; GenericMapping
0x1400fb428  mov     [rsp+0E0h+UserData], r15; Privileges
0x1400fb42d  mov     [rsp+0E0h+UserDataCount], r15d; PreviouslyGrantedAccess
0x1400fb432  call    cs:__imp_SeAccessCheck
0x1400fb439  nop     dword ptr [rax+rax+00h]
0x1400fb43e  lea     rcx, [rbp+57h+var_58]; SubjectContext
0x1400fb442  movzx   ebx, al
0x1400fb445  call    cs:__imp_SeReleaseSubjectContext
0x1400fb44c  nop     dword ptr [rax+rax+00h]
0x1400fb451  test    bl, bl
0x1400fb453  jnz     loc_1400FB50D
0x1400fb459  cmp     cs:dword_1402201D4, edi
0x1400fb45f  jz      loc_1400FB505
0x1400fb465  test    byte ptr cs:WPP_MAIN_CB.Reserved+1, 8
0x1400fb46c  xorps   xmm0, xmm0
0x1400fb46f  movups  xmmword ptr [rbp+57h+EventDescriptor.Id], xmm0
0x1400fb473  jz      loc_1400FB505
0x1400fb479  mov     rcx, rsi; Process
0x1400fb47c  call    cs:__imp_PsGetProcessId
0x1400fb483  nop     dword ptr [rax+rax+00h]
0x1400fb488  mov     rcx, rsi
0x1400fb48b  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x1400fb48f  mov     rbx, rax
0x1400fb492  mov     qword ptr [rbp+57h+EventDescriptor.Id], r15
0x1400fb496  call    cs:__imp_PsGetProcessStartKey
0x1400fb49d  nop     dword ptr [rax+rax+00h]
0x1400fb4a2  mov     r10, [r14+58h]
0x1400fb4a6  mov     rdx, rax
0x1400fb4a9  mov     r11, [r14+40h]
0x1400fb4ad  movzx   ecx, word ptr [r10]; af
0x1400fb4b1  call    SOCKADDR_SIZE
0x1400fb4b6  movzx   ecx, word ptr [r11]; af
0x1400fb4ba  movzx   r8d, al
0x1400fb4be  call    SOCKADDR_SIZE
0x1400fb4c3  mov     [rsp+0E0h+var_88], rdx
0x1400fb4c8  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400fb4cf  mov     [rsp+0E0h+var_90], r15
0x1400fb4d4  lea     rdx, TCP_CONNECT_TCB_FAILED_ACCESS_V1
0x1400fb4db  mov     dword ptr [rsp+0E0h+AccessStatus], r15d
0x1400fb4e0  mov     dword ptr [rsp+0E0h+GrantedAccess], ebx
0x1400fb4e4  mov     dword ptr [rsp+0E0h+AccessMode], r15d
0x1400fb4e9  mov     [rsp+0E0h+GenericMapping], r10
0x1400fb4ee  mov     dword ptr [rsp+0E0h+UserData], r8d
0x1400fb4f3  lea     r8, [rbp+57h+EventDescriptor]
0x1400fb4f7  movzx   r9d, al
0x1400fb4fb  mov     qword ptr [rsp+0E0h+UserDataCount], r11
0x1400fb500  call    McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer
0x1400fb505  mov     eax, [rbp+57h+var_80]
0x1400fb508  jmp     loc_1400FB153
0x1400fb50d  mov     rdx, [r14+40h]
0x1400fb511  lea     rcx, TcpInetTransport
0x1400fb518  movzx   edx, word ptr [rdx]
0x1400fb51b  call    InetFindAndReferenceAf
0x1400fb520  mov     rbx, rax
0x1400fb523  test    rax, rax
0x1400fb526  jnz     loc_1400FB378
0x1400fb52c  cmp     cs:dword_1402201D4, edi
0x1400fb532  jz      loc_1400FB5D8
0x1400fb538  test    byte ptr cs:WPP_MAIN_CB.Reserved+1, 8
0x1400fb53f  xorps   xmm0, xmm0
0x1400fb542  movups  xmmword ptr [rbp+57h+EventDescriptor.Id], xmm0
0x1400fb546  jz      loc_1400FB5D8
0x1400fb54c  mov     rcx, rsi; Process
0x1400fb54f  call    cs:__imp_PsGetProcessId
0x1400fb556  nop     dword ptr [rax+rax+00h]
0x1400fb55b  mov     rcx, rsi
0x1400fb55e  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x1400fb562  mov     rbx, rax
0x1400fb565  mov     qword ptr [rbp+57h+EventDescriptor.Id], r15
0x1400fb569  call    cs:__imp_PsGetProcessStartKey
0x1400fb570  nop     dword ptr [rax+rax+00h]
0x1400fb575  mov     r10, [r14+58h]
0x1400fb579  mov     rdx, rax
0x1400fb57c  mov     r11, [r14+40h]
0x1400fb580  movzx   ecx, word ptr [r10]; af
0x1400fb584  call    SOCKADDR_SIZE
  ... truncated ...
```
