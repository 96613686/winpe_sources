# KerbGetTicketForCredential(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_KERB_CREDMAN_CRED *,_KERB_EXTRA_CRED *,_KERB_PROXY_LOGON_CRED *,_UNICODE_STRING *,ulong,_KERB_TICKET_CACHE_ENTRY * *)

- ea: `0x18000b5c0`
- end: `0x18000bf7e`
- name: `?KerbGetTicketForCredential@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAU_KERB_CREDMAN_CRED@@PEAU_KERB_EXTRA_CRED@@PEAU_KERB_PROXY_LOGON_CRED@@PEAU_UNICODE_STRING@@KPEAPEAU_KERB_TICKET_CACHE_ENTRY@@@Z`
- size: `2494`
- prototype: `__int64 __usercall@<rax>(struct _KERB_LOGON_SESSION *@<rcx>, struct _KERB_CREDENTIAL *@<rdx>, struct _KERB_CREDMAN_CRED *@<r8>, struct _KERB_EXTRA_CRED *@<r9>, struct _KERB_PROXY_LOGON_CRED *, struct _UNICODE_STRING *, unsigned int, struct _KERB_TICKET_CACHE_ENTRY **)`
- caller_count: `9`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b430`
- `0x180025680`
- `0x180041178`
- `0x18004969c`
- `0x18005b210`
- `0x1800819b0`
- `0x180088264`
- `0x18008868c`
- `0x18008e4f4`

## callees

- `0x1800063e8`
- `0x180009afc`
- `0x18000a650`
- `0x18000b5c0`
- `0x180032964`
- `0x180036bb8`
- `0x180058f14`
- `0x180070680`
- `0x18008b70c`
- `0x1800ab118`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b7a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bc1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b7a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bc1d`
- `ntdll!EtwEventActivityIdControl` at `0x18000b738`
- `ntdll!EtwEventActivityIdControl` at `0x18000b74f`
- `ntdll!EtwEventActivityIdControl` at `0x18000bba6`
- `ntdll!EtwEventActivityIdControl` at `0x18000be87`
- `ntdll!EtwEventActivityIdControl` at `0x18000b738`
- `ntdll!EtwEventActivityIdControl` at `0x18000b74f`
- `ntdll!EtwEventActivityIdControl` at `0x18000bba6`
- `ntdll!EtwEventActivityIdControl` at `0x18000be87`
- `ntdll!EtwEventWriteTransfer` at `0x18000b88e`
- `ntdll!EtwEventWriteTransfer` at `0x18000bd7a`
- `ntdll!EtwEventWriteTransfer` at `0x18000bf53`
- `ntdll!EtwEventWriteTransfer` at `0x18000b88e`
- `ntdll!EtwEventWriteTransfer` at `0x18000bd7a`
- `ntdll!EtwEventWriteTransfer` at `0x18000bf53`
- `ntdll!RtlEnterCriticalSection` at `0x18000b8a4`
- `ntdll!RtlEnterCriticalSection` at `0x18000bae9`
- `ntdll!RtlEnterCriticalSection` at `0x18000bb1a`
- `ntdll!RtlEnterCriticalSection` at `0x18000bb43`
- `ntdll!RtlEnterCriticalSection` at `0x18000bb6d`
- `ntdll!RtlEnterCriticalSection` at `0x18000bdb2`
- `ntdll!RtlEnterCriticalSection` at `0x18000be02`
- `ntdll!RtlEnterCriticalSection` at `0x18000b8a4`
- `ntdll!RtlEnterCriticalSection` at `0x18000bae9`
- `ntdll!RtlEnterCriticalSection` at `0x18000bb1a`
- `ntdll!RtlEnterCriticalSection` at `0x18000bb43`
- `ntdll!RtlEnterCriticalSection` at `0x18000bb6d`
- `ntdll!RtlEnterCriticalSection` at `0x18000bdb2`
- `ntdll!RtlEnterCriticalSection` at `0x18000be02`
- `ntdll!RtlLeaveCriticalSection` at `0x18000ba2e`
- `ntdll!RtlLeaveCriticalSection` at `0x18000ba84`
- `ntdll!RtlLeaveCriticalSection` at `0x18000bb2f`
- `ntdll!RtlLeaveCriticalSection` at `0x18000bb5b`
- `ntdll!RtlLeaveCriticalSection` at `0x18000bb82`
- `ntdll!RtlLeaveCriticalSection` at `0x18000bb8b`
- `ntdll!RtlLeaveCriticalSection` at `0x18000bd85`
- `ntdll!RtlLeaveCriticalSection` at `0x18000be17`
- `ntdll!RtlLeaveCriticalSection` at `0x18000be21`
- `ntdll!RtlLeaveCriticalSection` at `0x18000ba2e`
- `ntdll!RtlLeaveCriticalSection` at `0x18000ba84`
- `ntdll!RtlLeaveCriticalSection` at `0x18000bb2f`
- `ntdll!RtlLeaveCriticalSection` at `0x18000bb5b`
- `ntdll!RtlLeaveCriticalSection` at `0x18000bb82`
- `ntdll!RtlLeaveCriticalSection` at `0x18000bb8b`
- `ntdll!RtlLeaveCriticalSection` at `0x18000bd85`
- `ntdll!RtlLeaveCriticalSection` at `0x18000be17`
- `ntdll!RtlLeaveCriticalSection` at `0x18000be21`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KerbGetTicketForCredential(
        struct _KERB_LOGON_SESSION *a1,
        struct _KERB_CREDENTIAL *a2,
        struct _KERB_CREDMAN_CRED *a3,
        struct _KERB_EXTRA_CRED *a4,
        struct _KERB_PROXY_LOGON_CRED *a5,
        struct _UNICODE_STRING *a6,
        unsigned int a7,
        struct _KERB_TICKET_CACHE_ENTRY **a8)
{
  unsigned int v8; // r12d
  struct _KERB_EXTRA_CRED *v9; // r15
  struct _KERB_CREDMAN_CRED *v10; // rax
  struct _KERB_CREDENTIAL *v11; // r14
  char v12; // r13
  unsigned int v13; // esi
  struct _KERB_LOGON_SESSION *LogonSession; // rdi
  signed int TicketGrantingTicket; // ebx
  __int128 *v16; // r9
  struct _RTL_CRITICAL_SECTION *v17; // r13
  __int64 v18; // rcx
  bool v20; // r15
  __int64 v21; // rax
  bool v22; // bl
  __int64 v23; // r12
  int v24; // esi
  int v25; // r14d
  int *TicketGrantingTicketFromAsRepCallback; // rax
  int v27; // r14d
  char v28; // bl
  int v29; // eax
  char v31; // [rsp+50h] [rbp-B0h] BYREF
  char v32; // [rsp+51h] [rbp-AFh] BYREF
  char v33; // [rsp+52h] [rbp-AEh] BYREF
  unsigned int v34; // [rsp+54h] [rbp-ACh]
  DWORD v35; // [rsp+58h] [rbp-A8h] BYREF
  int v36; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v37; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v38; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD CurrentThreadId; // [rsp+68h] [rbp-98h] BYREF
  int v40; // [rsp+70h] [rbp-90h] BYREF
  int v41; // [rsp+74h] [rbp-8Ch]
  __int64 v42; // [rsp+78h] [rbp-88h]
  struct _KERB_CREDMAN_CRED *v43; // [rsp+80h] [rbp-80h]
  struct _KERB_TICKET_CACHE_ENTRY *v44; // [rsp+88h] [rbp-78h] BYREF
  struct _KERB_CREDENTIAL *v45; // [rsp+90h] [rbp-70h]
  struct _KERB_EXTRA_CRED *v46; // [rsp+98h] [rbp-68h]
  __int64 v47; // [rsp+A0h] [rbp-60h] BYREF
  struct _KERB_PROXY_LOGON_CRED *v48; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING *v49; // [rsp+B8h] [rbp-48h]
  struct _KERB_LOGON_SESSION *v50; // [rsp+C0h] [rbp-40h]
  struct _KERB_TICKET_CACHE_ENTRY **v51; // [rsp+C8h] [rbp-38h]
  int v52; // [rsp+D0h] [rbp-30h]
  char v53; // [rsp+D4h] [rbp-2Ch]
  __int128 v54; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v55; // [rsp+E8h] [rbp-18h] BYREF
  char *v56; // [rsp+100h] [rbp+0h] BYREF
  int v57; // [rsp+108h] [rbp+8h]
  int v58; // [rsp+10Ch] [rbp+Ch]
  char *v59; // [rsp+110h] [rbp+10h]
  int v60; // [rsp+118h] [rbp+18h]
  int v61; // [rsp+11Ch] [rbp+1Ch]
  __int64 *v62; // [rsp+120h] [rbp+20h]
  __int64 v63; // [rsp+128h] [rbp+28h]
  DWORD *p_CurrentThreadId; // [rsp+130h] [rbp+30h]
  __int64 v65; // [rsp+138h] [rbp+38h]
  char *v66; // [rsp+140h] [rbp+40h] BYREF
  int v67; // [rsp+148h] [rbp+48h]
  int v68; // [rsp+14Ch] [rbp+4Ch]
  __int16 *v69; // [rsp+150h] [rbp+50h]
  int v70; // [rsp+158h] [rbp+58h]
  int v71; // [rsp+15Ch] [rbp+5Ch]
  struct _KERB_PROXY_LOGON_CRED **v72; // [rsp+160h] [rbp+60h]
  __int64 v73; // [rsp+168h] [rbp+68h]
  DWORD *v74; // [rsp+170h] [rbp+70h]
  __int64 v75; // [rsp+178h] [rbp+78h]
  int *v76; // [rsp+180h] [rbp+80h]
  __int64 v77; // [rsp+188h] [rbp+88h]
  char *v78; // [rsp+190h] [rbp+90h]
  __int64 v79; // [rsp+198h] [rbp+98h]
  char *v80; // [rsp+1A0h] [rbp+A0h]
  __int64 v81; // [rsp+1A8h] [rbp+A8h]
  char *v82; // [rsp+1B0h] [rbp+B0h]
  __int64 v83; // [rsp+1B8h] [rbp+B8h]
  unsigned int *v84; // [rsp+1C0h] [rbp+C0h]
  __int64 v85; // [rsp+1C8h] [rbp+C8h]
  DWORD *v86; // [rsp+1D0h] [rbp+D0h]
  __int64 v87; // [rsp+1D8h] [rbp+D8h]
  unsigned int *v88; // [rsp+1E0h] [rbp+E0h]
  __int64 v89; // [rsp+1E8h] [rbp+E8h]

  v9 = a4;
  v46 = a4;
  v10 = a3;
  v43 = a3;
  v11 = a2;
  v45 = a2;
  v50 = a1;
  v48 = a5;
  v49 = a6;
  v38 = a7;
  v51 = a8;
  v44 = 0;
  v12 = 0;
  v31 = 0;
  v36 = 0;
  v32 = 0;
  v35 = 0;
  v13 = 0;
  LOBYTE(v8) = 0;
  v34 = v8;
  v52 = 0;
  v53 = 0;
  if ( a1 )
  {
    LogonSession = a1;
  }
  else
  {
    LogonSession = KerbLocateLogonSession((const struct _LUID *)((char *)a2 + 28), 0);
    if ( !LogonSession )
    {
      TicketGrantingTicket = -1073741729;
      goto LABEL_92;
    }
    v10 = v43;
  }
  if ( v11 && *((_QWORD *)v11 + 9) || v10 || v9 )
  {
    KerbTracerT::Log(8, "KerbGetTicketForCredential", 730, "Got a credential && a logon session\n");
  }
  else
  {
    v12 = 1;
    v31 = 1;
    KerbTracerT::Log(
      8,
      "KerbGetTicketForCredential",
      726,
      "Getting Credentials for primary logon session - %p\n",
      (const void *)WORD1(LogonSession));
  }
  if ( (unsigned int)dword_180140048 > 5
    && (qword_180140058 & 0x400000000000LL) != 0
    && (qword_180140060 & 0x400000000000LL) == qword_180140060 )
  {
    EtwEventActivityIdControl(3, &v54);
    v55 = v54;
    EtwEventActivityIdControl(4, &v55);
    v53 = 1;
  }
  else
  {
    v54 = 0;
  }
  v52 = 1;
  if ( (unsigned int)dword_180140048 > 5
    && (qword_180140058 & 0x400000000000LL) != 0
    && (qword_180140060 & 0x400000000000LL) == qword_180140060 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v47 = 0x1000000;
    if ( v53 && ((_DWORD)v55 || __PAIR64__(DWORD1(v55), 0) != DWORD2(v55) || HIDWORD(v55)) )
      v16 = &v55;
    else
      v16 = 0;
    p_CurrentThreadId = &CurrentThreadId;
    v65 = 4;
    v62 = &v47;
    v63 = 8;
    v40 = 184549376;
    v41 = 261;
    v42 = 0x400000000000LL;
    v56 = (char *)off_180140050;
    v57 = *(unsigned __int16 *)off_180140050;
    v58 = 2;
    v59 = byte_18012B9D5;
    v60 = 69;
    v61 = 1;
    v37 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(qword_180140068, &v40, &v54, v16, 4, &v56);
  }
  if ( !v12 )
    goto LABEL_78;
  v17 = (struct _RTL_CRITICAL_SECTION *)((char *)LogonSession + 80);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)LogonSession + 2);
  v36 = *((_DWORD *)LogonSession + 233);
  if ( v36 == 2 )
  {
    if ( *((_QWORD *)LogonSession + 90) )
      goto LABEL_32;
    MicrosoftTelemetryAssertTriggeredNoArgs(v18);
  }
  if ( !*((_QWORD *)LogonSession + 90) )
  {
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)LogonSession + 2);
    v32 = 0;
    v35 = 0;
    v13 = 0;
    LOBYTE(v8) = 0;
    goto LABEL_78;
  }
LABEL_32:
  v20 = 0;
  if ( *((_QWORD *)LogonSession + 22) )
  {
    if ( *((_DWORD *)LogonSession + 40) == 1 ? *((_DWORD *)LogonSession + 42) : *((unsigned __int16 *)LogonSession + 84) )
      v20 = 1;
  }
  v21 = *((_QWORD *)LogonSession + 33);
  v22 = v21 && *(_WORD *)(v21 + 4);
  v23 = *((_QWORD *)LogonSession + 50);
  v24 = *((_DWORD *)LogonSession + 226) & 0x800;
  v25 = *((_DWORD *)LogonSession + 233);
  if ( !v20 && !v22 )
  {
    if ( !v23 )
      goto LABEL_61;
LABEL_52:
    if ( v25 == 2 )
    {
      if ( (*((_DWORD *)LogonSession + 226) & 0x1000000) != 0 )
        goto LABEL_57;
    }
    else if ( !v25 )
    {
      goto LABEL_57;
    }
    MicrosoftTelemetryAssertTriggeredNoArgs(v18);
LABEL_57:
    if ( (v20 || v22) && !v24 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v18);
    goto LABEL_61;
  }
  if ( v25 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v18);
  if ( v23 )
  {
    if ( !v24 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v18);
    goto LABEL_52;
  }
LABEL_61:
  if ( ((v25 - 1) & 0xFFFFFFFD) == 0 )
  {
    if ( !v20 && !v22 && !v23 && !v24 )
      goto LABEL_71;
    MicrosoftTelemetryAssertTriggeredNoArgs(v18);
  }
  if ( v20 || v22 || v23 && v25 != 2 )
  {
    KerbTracerT::Log(8, "KerbGetTicketForCredential", 777, "calling AS_REP callback for metadata and McFerral");
    v13 = *(_DWORD *)(KerbConsumeAsRepCallbackAndInitializeCloudKerb(&v47, LogonSession, 0) + 4);
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)LogonSession + 2);
    v9 = v46;
    LOBYTE(v8) = v34;
LABEL_77:
    v11 = v45;
LABEL_78:
    TicketGrantingTicket = KerbGetTicketGrantingTicket(LogonSession, v11, v43, v9, v48, v49, v38, &v44, 0, 0);
    v17 = (struct _RTL_CRITICAL_SECTION *)((char *)LogonSession + 80);
    goto LABEL_79;
  }
LABEL_71:
  KerbTracerT::Log(8, "KerbGetTicketForCredential", 756, "calling AS_REP callback as primary credential");
  TicketGrantingTicketFromAsRepCallback = (int *)KerbGetTicketGrantingTicketFromAsRepCallback(
                                                   &v47,
                                                   LogonSession,
                                                   v38,
                                                   &v44);
  v27 = *TicketGrantingTicketFromAsRepCallback;
  v35 = v27;
  v13 = TicketGrantingTicketFromAsRepCallback[1];
  v28 = v34;
  if ( v27 < 0 && v36 == 2 )
    v28 = 1;
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)LogonSession + 2);
  v32 = 1;
  LOBYTE(v8) = v28;
  v9 = v46;
  if ( v28 )
    goto LABEL_77;
  TicketGrantingTicket = v27;
  v11 = v45;
LABEL_79:
  if ( TicketGrantingTicket >= 0 )
  {
    RtlEnterCriticalSection(v17);
    if ( v31 )
    {
      v29 = *((_DWORD *)LogonSession + 226);
      if ( (v29 & 1) != 0 )
        *((_DWORD *)LogonSession + 226) = v29 & 0xFFFFFFFE;
    }
    if ( v11 && !v9 )
    {
      RtlEnterCriticalSection(&KerbGlobalCredentialsLock);
      *((_DWORD *)v11 + 16) |= 0x80800000;
      RtlLeaveCriticalSection(&KerbGlobalCredentialsLock);
    }
    if ( v43 )
    {
      RtlEnterCriticalSection(&KerbGlobalCredentialsLock);
      *((_DWORD *)v43 + 6) |= 0x80800000;
      RtlLeaveCriticalSection(&KerbGlobalCredentialsLock);
    }
    if ( v9 )
    {
      RtlEnterCriticalSection(&KerbGlobalCredentialsLock);
      *((_DWORD *)v9 + 7) |= 0x80800000;
      RtlLeaveCriticalSection(&KerbGlobalCredentialsLock);
    }
    RtlLeaveCriticalSection(v17);
  }
  v12 = v31;
LABEL_92:
  if ( v53 )
    EtwEventActivityIdControl(4, &v55);
  v52 = 2;
  if ( (unsigned int)dword_180140048 > 5
    && (qword_180140058 & 0x400000000000LL) != 0
    && (qword_180140060 & 0x400000000000LL) == qword_180140060 )
  {
    v37 = v13;
    CurrentThreadId = v35;
    v38 = TicketGrantingTicket;
    v31 = v8;
    v33 = v12;
    v35 = GetCurrentThreadId();
    v48 = (struct _KERB_PROXY_LOGON_CRED *)0x1000000;
    v88 = &v37;
    v89 = 4;
    v86 = &CurrentThreadId;
    v87 = 4;
    v84 = &v38;
    v85 = 4;
    v82 = &v31;
    v83 = 1;
    v80 = &v32;
    v81 = 1;
    v78 = &v33;
    v79 = 1;
    v76 = &v36;
    v77 = 4;
    v74 = &v35;
    v75 = 4;
    v72 = &v48;
    v73 = 8;
    v40 = 184549376;
    v41 = 517;
    v42 = 0x400000000000LL;
    v66 = (char *)off_180140050;
    v67 = *(unsigned __int16 *)off_180140050;
    v68 = 2;
    v69 = word_18012B8E2;
    v70 = 231;
    v71 = 1;
    v34 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(qword_180140068, &v40, &v54, 0, 11, &v66);
  }
  if ( LogonSession && TicketGrantingTicket < 0 )
  {
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)LogonSession + 2);
    if ( v12 )
    {
      *((_DWORD *)LogonSession + 226) |= 1u;
      KerbTracerT::Log(
        8,
        "KerbGetTicketForCredential",
        914,
        "Toggling ON logon deferred bit for logon session %p\n",
        (const void *)WORD1(LogonSession));
    }
    if ( v11 && !v9 )
    {
      RtlEnterCriticalSection(&KerbGlobalCredentialsLock);
      *((_DWORD *)v11 + 16) &= ~0x80000000;
      RtlLeaveCriticalSection(&KerbGlobalCredentialsLock);
    }
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)LogonSession + 2);
  }
  if ( !v50 && LogonSession && _InterlockedExchangeAdd((volatile signed __int32 *)LogonSession, 0xFFFFFFFF) == 1 )
    KerbFreeLogonSession(LogonSession);
  if ( v44 )
  {
    if ( v51 )
    {
      *v51 = v44;
      v44 = 0;
    }
    else
    {
      KerbDereferenceTicketCacheEntry(v44);
    }
  }
  if ( v52 == 1 )
  {
    if ( v53 )
      EtwEventActivityIdControl(4, &v55);
    v52 = 2;
    if ( (unsigned int)dword_180140048 > 5
      && (qword_180140058 & 0x400000000000LL) != 0
      && (qword_180140060 & 0x400000000000LL) == qword_180140060 )
    {
      v40 = 184549376;
      v41 = 517;
      v42 = 0x400000000000LL;
      v56 = (char *)off_180140050;
      v57 = *(unsigned __int16 *)off_180140050;
      v58 = 2;
      v59 = byte_18012B753;
      v60 = 32;
      v61 = 1;
      v37 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(qword_180140068, &v40, &v54, 0, 2, &v56);
    }
  }
  return (unsigned int)TicketGrantingTicket;
}

```

## disassembly

```asm
0x18000b5c0  push    rbp
0x18000b5c2  push    rbx
0x18000b5c3  push    rsi
0x18000b5c4  push    rdi
0x18000b5c5  push    r12
0x18000b5c7  push    r13
0x18000b5c9  push    r14
0x18000b5cb  push    r15
0x18000b5cd  lea     rbp, [rsp-108h]
0x18000b5d5  sub     rsp, 208h
0x18000b5dc  mov     rax, cs:__security_cookie
0x18000b5e3  xor     rax, rsp
0x18000b5e6  mov     [rbp+140h+var_50], rax
0x18000b5ed  mov     r15, r9
0x18000b5f0  mov     [rbp+140h+var_1A8], r9
0x18000b5f4  mov     rax, r8
0x18000b5f7  mov     [rbp+140h+var_1C0], rax
0x18000b5fb  mov     r14, rdx
0x18000b5fe  mov     [rbp+140h+var_1B0], rdx
0x18000b602  mov     rdx, rcx; unsigned __int8
0x18000b605  mov     [rbp+140h+var_180], rcx
0x18000b609  mov     rcx, [rbp+140h+arg_20]
0x18000b610  mov     [rbp+140h+var_198], rcx
0x18000b614  mov     rcx, [rbp+140h+arg_28]
0x18000b61b  mov     [rbp+140h+var_188], rcx
0x18000b61f  mov     ecx, [rbp+140h+arg_30]
0x18000b625  mov     [rsp+240h+var_1DC], ecx
0x18000b629  mov     rcx, [rbp+140h+arg_38]
0x18000b630  mov     [rbp+140h+var_178], rcx
0x18000b634  xor     ebx, ebx
0x18000b636  mov     [rbp+140h+var_1B8], rbx
0x18000b63a  xor     r13b, r13b
0x18000b63d  mov     [rsp+240h+var_1F0], r13b
0x18000b642  mov     [rsp+240h+var_1E4], ebx
0x18000b646  mov     [rsp+240h+var_1EF], bl
0x18000b64a  mov     [rsp+240h+var_1E8], ebx
0x18000b64e  mov     esi, ebx
0x18000b650  xor     r12b, r12b
0x18000b653  mov     [rsp+240h+var_1EC], r12d
0x18000b658  mov     [rbp+140h+var_170], ebx
0x18000b65b  mov     [rbp+140h+var_16C], bl
0x18000b65e  test    rdx, rdx
0x18000b661  jnz     short loc_18000B67E
0x18000b663  lea     rcx, [r14+1Ch]; struct _LUID *
0x18000b667  call    ?KerbLocateLogonSession@@YAPEAU_KERB_LOGON_SESSION@@PEBU_LUID@@E@Z; KerbLocateLogonSession(_LUID const *,uchar)
0x18000b66c  mov     rdi, rax
0x18000b66f  test    rax, rax
0x18000b672  jnz     short loc_18000B683
0x18000b674  mov     ebx, 0C000005Fh
0x18000b679  jmp     loc_18000BB97
0x18000b67e  mov     rdi, rdx
0x18000b681  jmp     short loc_18000B687
0x18000b683  mov     rax, [rbp+140h+var_1C0]
0x18000b687  test    r14, r14
0x18000b68a  jz      short loc_18000B693
0x18000b68c  cmp     qword ptr [r14+48h], 0
0x18000b691  jnz     short loc_18000B6DE
0x18000b693  test    rax, rax
0x18000b696  jnz     short loc_18000B6DE
0x18000b698  test    r15, r15
0x18000b69b  jnz     short loc_18000B6DE
0x18000b69d  mov     r13b, 1
0x18000b6a0  mov     [rsp+240h+var_1F0], r13b
0x18000b6a5  test    rdi, rdi
0x18000b6a8  jz      short loc_18000B6B6
0x18000b6aa  mov     rax, rdi
0x18000b6ad  shr     rax, 10h
0x18000b6b1  movzx   ecx, ax
0x18000b6b4  jmp     short loc_18000B6B9
0x18000b6b6  mov     rcx, rbx
0x18000b6b9  mov     [rsp+240h+var_220], rcx
0x18000b6be  lea     r9, aGettingCredent; "Getting Credentials for primary logon s"...
0x18000b6c5  mov     r8d, 2D6h
0x18000b6cb  lea     rdx, aKerbgetticketf; "KerbGetTicketForCredential"
0x18000b6d2  mov     ecx, 8
0x18000b6d7  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18000b6dc  jmp     short loc_18000B6FC
0x18000b6de  lea     r9, aGotACredential; "Got a credential && a logon session\n"
0x18000b6e5  mov     r8d, 2DAh
0x18000b6eb  lea     rdx, aKerbgetticketf; "KerbGetTicketForCredential"
0x18000b6f2  mov     ecx, 8
0x18000b6f7  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18000b6fc  mov     eax, cs:dword_180140048
0x18000b702  cmp     eax, 5
0x18000b705  jbe     short loc_18000B75B
0x18000b707  mov     rcx, cs:qword_180140060
0x18000b70e  mov     rax, cs:qword_180140058
0x18000b715  mov     rdx, 400000000000h
0x18000b71f  test    rdx, rax
0x18000b722  jz      short loc_18000B75B
0x18000b724  mov     rax, rcx
0x18000b727  and     rax, rdx
0x18000b72a  cmp     rax, rcx
0x18000b72d  jnz     short loc_18000B75B
0x18000b72f  lea     rdx, [rbp+140h+var_168]
0x18000b733  mov     ecx, 3
0x18000b738  call    cs:__imp_EtwEventActivityIdControl
0x18000b73e  movups  xmm0, [rbp+140h+var_168]
0x18000b742  movups  [rbp+140h+var_158], xmm0
0x18000b746  lea     rdx, [rbp+140h+var_158]
0x18000b74a  mov     ecx, 4
0x18000b74f  call    cs:__imp_EtwEventActivityIdControl
0x18000b755  mov     [rbp+140h+var_16C], 1
0x18000b759  jmp     short loc_18000B762
0x18000b75b  xorps   xmm0, xmm0
0x18000b75e  movups  [rbp+140h+var_168], xmm0
0x18000b762  mov     [rbp+140h+var_170], 1
0x18000b769  mov     eax, cs:dword_180140048
0x18000b76f  cmp     eax, 5
0x18000b772  jbe     loc_18000B894
0x18000b778  mov     rcx, cs:qword_180140060
0x18000b77f  mov     rax, cs:qword_180140058
0x18000b786  mov     rdx, 400000000000h
0x18000b790  test    rdx, rax
0x18000b793  jz      loc_18000B894
0x18000b799  mov     rax, rcx
0x18000b79c  and     rax, rdx
0x18000b79f  cmp     rax, rcx
0x18000b7a2  jnz     loc_18000B894
0x18000b7a8  call    cs:__imp_GetCurrentThreadId
0x18000b7ae  mov     [rsp+240h+var_1D8], eax
0x18000b7b2  mov     [rbp+140h+var_1A0], 1000000h
0x18000b7ba  cmp     [rbp+140h+var_16C], 0
0x18000b7be  jz      short loc_18000B7DE
0x18000b7c0  cmp     dword ptr [rbp+140h+var_158], 0
0x18000b7c4  jnz     short loc_18000B7D8
0x18000b7c6  cmp     dword ptr [rbp+140h+var_158+4], 0
0x18000b7ca  jnz     short loc_18000B7D8
0x18000b7cc  cmp     dword ptr [rbp+140h+var_158+8], 0
0x18000b7d0  jnz     short loc_18000B7D8
0x18000b7d2  cmp     dword ptr [rbp+140h+var_158+0Ch], 0
0x18000b7d6  jz      short loc_18000B7DE
0x18000b7d8  lea     r9, [rbp+140h+var_158]
0x18000b7dc  jmp     short loc_18000B7E1
0x18000b7de  mov     r9, rbx
0x18000b7e1  lea     rax, [rsp+240h+var_1D8]
0x18000b7e6  mov     [rbp+140h+var_110], rax
0x18000b7ea  mov     [rbp+140h+var_108], 4
0x18000b7f2  lea     rax, [rbp+140h+var_1A0]
0x18000b7f6  mov     [rbp+140h+var_120], rax
0x18000b7fa  mov     [rbp+140h+var_118], 8
0x18000b802  mov     [rsp+240h+var_1D0], 0B000000h
0x18000b80a  movzx   eax, cs:word_18012B9CB
0x18000b811  mov     [rsp+240h+var_1CC], eax
0x18000b815  mov     rdx, 400000000000h
0x18000b81f  mov     [rsp+240h+var_1C8], rdx
0x18000b824  mov     rax, cs:off_180140050
0x18000b82b  mov     [rbp+140h+var_140], rax
0x18000b82f  movzx   eax, word ptr [rax]
0x18000b832  mov     [rbp+140h+var_138], eax
0x18000b835  mov     [rbp+140h+var_134], 2
0x18000b83c  lea     rax, byte_18012B9D5
0x18000b843  mov     [rbp+140h+var_130], rax
0x18000b847  mov     [rbp+140h+var_128], 45h ; 'E'
0x18000b84e  mov     [rbp+140h+var_124], 1
0x18000b855  lea     rax, _TraceLoggingMetadataEnd
0x18000b85c  lea     rcx, _TraceLoggingMetadata
0x18000b863  sub     eax, ecx
0x18000b865  mov     [rsp+240h+var_1E0], eax
0x18000b869  mov     eax, [rsp+240h+var_1E0]
0x18000b86d  lea     rax, [rbp+140h+var_140]
0x18000b871  mov     [rsp+240h+var_218], rax
0x18000b876  mov     dword ptr [rsp+240h+var_220], 4
0x18000b87e  lea     r8, [rbp+140h+var_168]
0x18000b882  lea     rdx, [rsp+240h+var_1D0]
0x18000b887  mov     rcx, cs:qword_180140068
0x18000b88e  call    cs:__imp_EtwEventWriteTransfer
0x18000b894  test    r13b, r13b
0x18000b897  jz      loc_18000BA99
0x18000b89d  lea     r13, [rdi+50h]
0x18000b8a1  mov     rcx, r13; CriticalSection
0x18000b8a4  call    cs:__imp_RtlEnterCriticalSection
0x18000b8aa  mov     eax, [rdi+3A4h]
0x18000b8b0  mov     [rsp+240h+var_1E4], eax
0x18000b8b4  cmp     eax, 2
0x18000b8b7  jnz     short loc_18000B8C8
0x18000b8b9  cmp     qword ptr [rdi+2D0h], 0
0x18000b8c1  jnz     short loc_18000B8D6
0x18000b8c3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b8c8  cmp     qword ptr [rdi+2D0h], 0
0x18000b8d0  jz      loc_18000BD82
0x18000b8d6  mov     eax, [rdi+0A0h]
0x18000b8dc  cmp     qword ptr [rdi+0B0h], 0
0x18000b8e4  jz      short loc_18000B903
0x18000b8e6  cmp     eax, 1
0x18000b8e9  jnz     short loc_18000B8F3
0x18000b8eb  mov     eax, [rdi+0A8h]
0x18000b8f1  jmp     short loc_18000B8FA
0x18000b8f3  movzx   eax, word ptr [rdi+0A8h]
0x18000b8fa  test    eax, eax
0x18000b8fc  jz      short loc_18000B903
0x18000b8fe  mov     r15b, 1
0x18000b901  jmp     short loc_18000B906
0x18000b903  xor     r15b, r15b
0x18000b906  mov     rax, [rdi+108h]
0x18000b90d  test    rax, rax
0x18000b910  jz      short loc_18000B91D
0x18000b912  cmp     word ptr [rax+4], 0
0x18000b917  jz      short loc_18000B91D
0x18000b919  mov     bl, 1
0x18000b91b  jmp     short loc_18000B91F
0x18000b91d  xor     bl, bl
0x18000b91f  mov     r12, [rdi+190h]
0x18000b926  mov     esi, [rdi+388h]
0x18000b92c  and     esi, 800h
0x18000b932  mov     r14d, [rdi+3A4h]
0x18000b939  test    r15b, r15b
0x18000b93c  jnz     short loc_18000B949
0x18000b93e  test    bl, bl
0x18000b940  jnz     short loc_18000B949
0x18000b942  test    r12, r12
0x18000b945  jz      short loc_18000B996
0x18000b947  jmp     short loc_18000B961
0x18000b949  test    r14d, r14d
0x18000b94c  jz      short loc_18000B953
0x18000b94e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b953  test    r12, r12
0x18000b956  jz      short loc_18000B996
0x18000b958  test    esi, esi
0x18000b95a  jnz     short loc_18000B961
0x18000b95c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b961  cmp     r14d, 2
0x18000b965  jnz     short loc_18000B97A
0x18000b967  test    dword ptr [rdi+388h], 1000000h
0x18000b971  jnz     short loc_18000B984
0x18000b973  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b978  jmp     short loc_18000B984
0x18000b97a  test    r14d, r14d
0x18000b97d  jz      short loc_18000B984
0x18000b97f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b984  test    r15b, r15b
0x18000b987  jnz     short loc_18000B98D
0x18000b989  test    bl, bl
0x18000b98b  jz      short loc_18000B996
0x18000b98d  test    esi, esi
0x18000b98f  jnz     short loc_18000B996
0x18000b991  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b996  lea     eax, [r14-1]
0x18000b99a  test    eax, 0FFFFFFFDh
0x18000b99f  jnz     short loc_18000B9B8
0x18000b9a1  test    r15b, r15b
0x18000b9a4  jnz     short loc_18000B9B3
0x18000b9a6  test    bl, bl
0x18000b9a8  jnz     short loc_18000B9B3
0x18000b9aa  test    r12, r12
0x18000b9ad  jnz     short loc_18000B9B3
0x18000b9af  test    esi, esi
0x18000b9b1  jz      short loc_18000B9D4
0x18000b9b3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b9b8  test    r15b, r15b
0x18000b9bb  jnz     loc_18000BA51
0x18000b9c1  test    bl, bl
0x18000b9c3  jnz     loc_18000BA51
0x18000b9c9  test    r12, r12
0x18000b9cc  jz      short loc_18000B9D4
0x18000b9ce  cmp     r14d, 2
0x18000b9d2  jnz     short loc_18000BA51
0x18000b9d4  lea     r9, aCallingAsRepCa_0; "calling AS_REP callback as primary cred"...
0x18000b9db  mov     r8d, 2F4h
0x18000b9e1  lea     rdx, aKerbgetticketf; "KerbGetTicketForCredential"
0x18000b9e8  mov     ecx, 8
0x18000b9ed  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18000b9f2  lea     r9, [rbp+140h+var_1B8]
0x18000b9f6  mov     r8d, [rsp+240h+var_1DC]
0x18000b9fb  mov     rdx, rdi
0x18000b9fe  lea     rcx, [rbp+140h+var_1A0]
0x18000ba02  call    ?KerbGetTicketGrantingTicketFromAsRepCallback@@YA?AU?$pair@JJ@std@@PEAU_KERB_LOGON_SESSION@@KPEAPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbGetTicketGrantingTicketFromAsRepCallback(_KERB_LOGON_SESSION *,ulong,_KERB_TICKET_CACHE_ENTRY * *)
0x18000ba07  mov     r14d, [rax]
0x18000ba0a  mov     [rsp+240h+var_1E8], r14d
0x18000ba0f  mov     esi, [rax+4]
0x18000ba12  mov     ebx, [rsp+240h+var_1EC]
0x18000ba16  test    r14d, r14d
0x18000ba19  jns     short loc_18000BA2B
0x18000ba1b  movzx   ebx, bl
0x18000ba1e  cmp     [rsp+240h+var_1E4], 2
0x18000ba23  mov     eax, 1
0x18000ba28  cmovz   ebx, eax
0x18000ba2b  mov     rcx, r13; CriticalSection
0x18000ba2e  call    cs:__imp_RtlLeaveCriticalSection
0x18000ba34  mov     [rsp+240h+var_1EF], 1
0x18000ba39  movzx   r12d, bl
0x18000ba3d  mov     r15, [rbp+140h+var_1A8]
0x18000ba41  test    bl, bl
0x18000ba43  jnz     short loc_18000BA93
0x18000ba45  mov     ebx, r14d
0x18000ba48  mov     r14, [rbp+140h+var_1B0]
0x18000ba4c  jmp     loc_18000BADE
0x18000ba51  lea     r9, aCallingAsRepCa_1; "calling AS_REP callback for metadata an"...
0x18000ba58  mov     r8d, 309h
0x18000ba5e  lea     rdx, aKerbgetticketf; "KerbGetTicketForCredential"
0x18000ba65  mov     ecx, 8
0x18000ba6a  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18000ba6f  xor     r8d, r8d
0x18000ba72  mov     rdx, rdi
0x18000ba75  lea     rcx, [rbp+140h+var_1A0]
0x18000ba79  call    ?KerbConsumeAsRepCallbackAndInitializeCloudKerb@@YA?AU?$pair@JJ@std@@PEAU_KERB_LOGON_SESSION@@PEAU_KERB_AS_REP_PROCESSED_CREDENTIAL@@@Z; KerbConsumeAsRepCallbackAndInitializeCloudKerb(_KERB_LOGON_SESSION *,_KERB_AS_REP_PROCESSED_CREDENTIAL *)
0x18000ba7e  mov     esi, [rax+4]
0x18000ba81  mov     rcx, r13; CriticalSection
0x18000ba84  call    cs:__imp_RtlLeaveCriticalSection
0x18000ba8a  mov     r15, [rbp+140h+var_1A8]
  ... truncated ...
```
