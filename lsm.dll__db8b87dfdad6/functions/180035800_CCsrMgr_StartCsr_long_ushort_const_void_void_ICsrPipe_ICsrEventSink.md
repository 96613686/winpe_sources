# CCsrMgr::StartCsr(long *,ushort const *,void * *,void * *,ICsrPipe * *,ICsrEventSink *)

- ea: `0x180035800`
- end: `0x180035e2c`
- name: `?StartCsr@CCsrMgr@@UEAAJPEAJPEBGPEAPEAX2PEAPEAVICsrPipe@@PEAVICsrEventSink@@@Z`
- size: `1580`
- prototype: `int(CCsrMgr *__hidden this, int *, const unsigned __int16 *, void **, void **, struct ICsrPipe **, struct ICsrEventSink *)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001b80`
- `0x180008f64`
- `0x18000a808`
- `0x18000f260`
- `0x180010fb0`
- `0x18001ce00`
- `0x18001cec0`
- `0x18001f7bc`
- `0x180022a04`
- `0x180025070`
- `0x180025890`
- `0x180027030`
- `0x180029144`
- `0x180029c14`
- `0x180035800`
- `0x180046728`
- `0x1800469fc`
- `0x1800476cc`
- `0x18004b86c`
- `0x180097010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800358cf`
- `ntdll!RtlInitUnicodeString` at `0x1800358cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035a8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035af1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035baf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035a8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035af1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035baf`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180035ae7`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180035ae7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035dd2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035de8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035dd2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035de8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180035a7d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180035ba1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180035a7d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180035ba1`

## string_xrefs

- `0x180035ab0`: `OpenProcess(InitialCommandProcessId) failed`
- `0x180035b15`: `ProcessIdToSessionId(InitialCommandProcessId) failed`
- `0x180035b57`: `Wrong Initial Command Session ID (doesn't match pSessionId)`
- `0x180035bd3`: `OpenProcess(WindwsSubSysProcessId) failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CCsrMgr::StartCsr(
        CCsrMgr *this,
        int *a2,
        WCHAR *a3,
        void **a4,
        void **a5,
        struct ICsrPipe **a6,
        struct ICsrEventSink *a7)
{
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  void **v14; // r15
  int v15; // edi
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  struct _UNICODE_STRING *p_DestinationString; // rdi
  int started; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rcx
  const unsigned __int16 **v25; // rax
  __int16 *v26; // rdx
  DWORD v27; // esi
  int v28; // r8d
  DWORD v29; // ebx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  HANDLE v33; // rax
  signed int LastError; // eax
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  const char *v38; // rax
  char *v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // r8
  __int64 v42; // r9
  signed int v43; // eax
  HANDLE v44; // rax
  signed int v45; // eax
  unsigned __int16 *v46; // rax
  struct ICsrPipe *v47; // rbx
  __int64 v48; // rcx
  __int64 v49; // r8
  __int64 v50; // r9
  int v51; // eax
  __int64 v52; // r8
  __int64 v53; // r9
  int *v55; // [rsp+28h] [rbp-59h]
  int *v56; // [rsp+28h] [rbp-59h]
  const char **v57; // [rsp+38h] [rbp-49h]
  const char *v58; // [rsp+40h] [rbp-41h] BYREF
  DWORD dwProcessId[2]; // [rsp+48h] [rbp-39h] BYREF
  const char *v60; // [rsp+50h] [rbp-31h] BYREF
  int v61[2]; // [rsp+58h] [rbp-29h] BYREF
  struct ICsrPipe *v62; // [rsp+68h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-11h] BYREF
  _BYTE v64[64]; // [rsp+80h] [rbp-1h] BYREF
  unsigned __int64 v65; // [rsp+D0h] [rbp+4Fh] BYREF
  DWORD pSessionId; // [rsp+E8h] [rbp+67h] BYREF

  DestinationString = 0;
  v65 = 0;
  *(_QWORD *)dwProcessId = 0;
  v62 = 0;
  pSessionId = 0;
  CAutoSharedLock::CAutoSharedLock((CAutoSharedLock *)v64, (CCsrMgr *)((char *)this + 1592));
  if ( !a4 || (*a4 = 0, (v14 = a5) == 0) )
  {
    v15 = -2147024809;
    goto LABEL_66;
  }
  *a5 = 0;
  if ( *((_DWORD *)this + 460) )
  {
    if ( (unsigned int)dword_1800DA020 > 2 )
    {
      v65 = (unsigned __int64)"Shutting down. Can't StartCsr";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v11,
        (unsigned __int8 *)&dword_1800C60FC,
        v12,
        v13,
        (const unsigned __int16 **)&v65);
    }
    v15 = -805305602;
    goto LABEL_66;
  }
  if ( a3 )
  {
    RtlInitUnicodeString(&DestinationString, a3);
    p_DestinationString = &DestinationString;
    if ( (unsigned int)dword_1800DA020 > 5 )
    {
      *(_QWORD *)v61 = a3;
      v60 = "Starting session";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v16,
        (unsigned __int8 *)&word_1800C60C6,
        v17,
        v18,
        (const unsigned __int16 **)&v60,
        (__int64 **)v61);
    }
  }
  else
  {
    if ( (unsigned int)dword_1800DA020 > 5 )
    {
      v60 = "Starting session";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v11,
        (unsigned __int8 *)byte_1800C60A1,
        v12,
        v13,
        (const unsigned __int16 **)&v60);
    }
    LODWORD(p_DestinationString) = 0;
  }
  started = SmStartCsr(
              *((_QWORD *)this + 229),
              (_DWORD)a2,
              (_DWORD)p_DestinationString,
              (unsigned int)dwProcessId,
              (__int64)&v65);
  v15 = started | 0x10000000;
  v61[0] = started | 0x10000000;
  if ( started < 0 )
  {
    v24 = 0;
    LODWORD(v65) = 0;
    if ( (unsigned int)dword_1800DA020 <= 3 )
    {
LABEL_51:
      if ( v15 >= 0 || (_DWORD)v24 != 1 )
        goto LABEL_66;
      goto LABEL_57;
    }
    v60 = "StartCsr";
    *(_QWORD *)dwProcessId = "SmStartCsr failed";
    v58 = "Warning HResult failed";
    v57 = &v60;
    v55 = (int *)dwProcessId;
    v25 = (const unsigned __int16 **)&v58;
    v26 = word_1800C6062;
LABEL_16:
    v61[0] = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v24,
      (int)v26,
      v22,
      v23,
      v25,
      (const unsigned __int16 **)v55,
      (__int64)v61,
      (const unsigned __int16 **)v57);
LABEL_50:
    LODWORD(v24) = v65;
    goto LABEL_51;
  }
  v27 = v65;
  v28 = *a2;
  if ( a3 )
  {
    v56 = (int *)a3;
    v29 = dwProcessId[0];
    CrimsonHelper::RaiseEvent<long,unsigned long,unsigned long,unsigned short const *>(
      (CrimsonHelper *)&CrimsonHelper::s_instance,
      v21,
      v28,
      dwProcessId[0],
      v65,
      (__int64)v56);
  }
  else
  {
    v29 = dwProcessId[0];
    CrimsonHelper::RaiseEvent<long,unsigned long,unsigned long>(
      (CrimsonHelper *)&CrimsonHelper::s_instance,
      v21,
      v28,
      dwProcessId[0],
      v65);
  }
  if ( (unsigned int)dword_1800DA020 > 5 )
  {
    v65 = v27;
    v58 = (const char *)v29;
    v60 = (const char *)*a2;
    *(_QWORD *)dwProcessId = "Started session";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      v30,
      (unsigned __int8 *)byte_1800C5FED,
      v31,
      v32,
      (const unsigned __int16 **)dwProcessId,
      (__int64)&v60,
      (__int64)&v58,
      (__int64)&v65);
  }
  LODWORD(v65) = 1;
  v33 = OpenProcess(0x100000u, 0, v29);
  *a4 = v33;
  if ( !v33 )
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_1800DA020 <= 2 )
      goto LABEL_50;
    v38 = "OpenProcess(InitialCommandProcessId) failed";
    v39 = byte_1800C5FC3;
    goto LABEL_27;
  }
  if ( !ProcessIdToSessionId(v29, &pSessionId) )
  {
    v43 = GetLastError();
    v15 = v43;
    if ( v43 > 0 )
      v15 = (unsigned __int16)v43 | 0x80070000;
    if ( (unsigned int)dword_1800DA020 <= 2 )
      goto LABEL_50;
    v38 = "ProcessIdToSessionId(InitialCommandProcessId) failed";
    v39 = byte_1800C5F99;
    goto LABEL_27;
  }
  if ( pSessionId == *a2 )
  {
    v44 = OpenProcess(0x101000u, 0, v27);
    *v14 = v44;
    if ( !v44 )
    {
      v45 = GetLastError();
      v15 = v45;
      if ( v45 > 0 )
        v15 = (unsigned __int16)v45 | 0x80070000;
      if ( (unsigned int)dword_1800DA020 <= 2 )
        goto LABEL_50;
      v38 = "OpenProcess(WindwsSubSysProcessId) failed";
      v39 = (char *)qword_1800C5F20;
LABEL_27:
      v58 = v38;
      v61[0] = v15;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v35,
        (unsigned __int8 *)v39,
        v36,
        v37,
        (const unsigned __int16 **)&v58,
        (__int64)v61);
      goto LABEL_50;
    }
    v46 = (unsigned __int16 *)operator new(0x750u, (const struct std::nothrow_t *)&std::nothrow);
    v58 = (const char *)v46;
    if ( v46 )
    {
      v46 = (unsigned __int16 *)CCsrPipe::CCsrPipe((CCsrPipe *)v46, *a2, *v14, *a4, a7, v61);
      v15 = v61[0];
    }
    SmartPtr<IWinlogonNotify>::operator=((__int64 *)&v62, (__int64)v46);
    v47 = v62;
    if ( v62 )
    {
      if ( v15 < 0 )
      {
        if ( (unsigned int)dword_1800DA020 <= 3 )
          goto LABEL_50;
        v58 = "StartCsr";
        v60 = "CCsrPipe::CCsrPipe";
        *(_QWORD *)dwProcessId = "Warning HResult failed";
        v57 = &v58;
        v55 = (int *)&v60;
        v25 = (const unsigned __int16 **)dwProcessId;
        v26 = (__int16 *)byte_1800C5EE1;
        goto LABEL_16;
      }
      CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v61, (struct _RTL_RESOURCE *)((char *)this + 1720));
      if ( (unsigned int)SmartArray<CCsrPipe,long>::AddAt((char *)this + 1696, (unsigned int)*a2, v47) )
      {
        v15 = 0;
        CAutoLock::Unlock((CAutoLock *)v61);
        *a6 = v47;
        (*(void (__fastcall **)(struct ICsrPipe *))(*(_QWORD *)v47 + 8LL))(v47);
        goto LABEL_50;
      }
      v15 = -2147024882;
      if ( (unsigned int)dword_1800DA020 > 3 )
      {
        v58 = "StartCsr";
        LODWORD(v65) = -2147024882;
        v60 = "CsrPipes.AddAt";
        *(_QWORD *)dwProcessId = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v48,
          (int)word_1800C5EA2,
          v49,
          v50,
          (const unsigned __int16 **)dwProcessId,
          (const unsigned __int16 **)&v60,
          (__int64)&v65,
          (const unsigned __int16 **)&v58);
      }
      CAutoLock::Unlock((CAutoLock *)v61);
    }
    else
    {
      v15 = -2147024882;
    }
  }
  else
  {
    v15 = -2147024883;
    if ( (unsigned int)dword_1800DA020 > 2 )
    {
      v58 = (const char *)(unsigned int)*a2;
      v60 = (const char *)(int)pSessionId;
      LODWORD(v65) = -2147024883;
      *(_QWORD *)dwProcessId = "Wrong Initial Command Session ID (doesn't match pSessionId)";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v40,
        (int)word_1800C5F4A,
        v41,
        v42,
        (const unsigned __int16 **)dwProcessId,
        (__int64)&v65,
        (__int64)&v60,
        (__int64)&v58);
    }
  }
LABEL_57:
  v51 = SmStopCsr(*((_QWORD *)this + 229), (unsigned int)*a2) | 0x10000000;
  if ( v51 >= 0 )
  {
    *a2 = -1;
  }
  else if ( (unsigned int)dword_1800DA020 > 2 )
  {
    LODWORD(v65) = v51;
    v58 = "Failed to stop CSR";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)dword_1800DA020,
      (unsigned __int8 *)byte_1800C5E75,
      v52,
      v53,
      (const unsigned __int16 **)&v58,
      (__int64)&v65);
  }
  if ( *a4 )
  {
    CloseHandle(*a4);
    *a4 = 0;
  }
  if ( *v14 )
  {
    CloseHandle(*v14);
    *v14 = 0;
  }
LABEL_66:
  CAutoLock::Unlock((CAutoLock *)v64);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>((__int64 *)&v62);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180035800  mov     [rsp-8+arg_8], rbx
0x180035805  push    rbp
0x180035806  push    rsi
0x180035807  push    rdi
0x180035808  push    r12
0x18003580a  push    r13
0x18003580c  push    r14
0x18003580e  push    r15
0x180035810  lea     rbp, [rsp-0Fh]
0x180035815  sub     rsp, 90h
0x18003581c  mov     r12, r9
0x18003581f  mov     rbx, r8
0x180035822  mov     r14, rdx
0x180035825  mov     r13, rcx
0x180035828  xorps   xmm0, xmm0
0x18003582b  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x18003582f  mov     [rbp+3Fh+arg_0], 0
0x180035837  mov     qword ptr [rbp+3Fh+dwProcessId], 0
0x18003583f  mov     [rbp+3Fh+var_58], 0
0x180035847  mov     [rbp+3Fh+pSessionId], 0
0x18003584e  lea     rdx, [rcx+638h]; struct CResource *
0x180035855  lea     rcx, [rbp+3Fh+var_40]; this
0x180035859  call    ??0CAutoSharedLock@@QEAA@AEAVCResource@@@Z; CAutoSharedLock::CAutoSharedLock(CResource &)
0x18003585e  nop
0x18003585f  test    r12, r12
0x180035862  jz      loc_180035DF7
0x180035868  mov     qword ptr [r12], 0
0x180035870  mov     r15, [rbp+3Fh+arg_20]
0x180035874  test    r15, r15
0x180035877  jz      loc_180035DF7
0x18003587d  mov     qword ptr [r15], 0
0x180035884  cmp     dword ptr [r13+730h], 0
0x18003588c  jz      short loc_1800358C3
0x18003588e  mov     eax, cs:dword_1800DA020
0x180035894  cmp     eax, 2
0x180035897  jbe     short loc_1800358B9
0x180035899  lea     rax, aShuttingDownCa; "Shutting down. Can't StartCsr"
0x1800358a0  mov     [rbp+3Fh+arg_0], rax
0x1800358a4  lea     rax, [rbp+3Fh+arg_0]
0x1800358a8  mov     [rsp+0C0h+var_A0], rax
0x1800358ad  lea     rdx, dword_1800C60FC
0x1800358b4  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800358b9  mov     edi, 0D00002FEh
0x1800358be  jmp     loc_180035DFC
0x1800358c3  test    rbx, rbx
0x1800358c6  jz      short loc_180035913
0x1800358c8  mov     rdx, rbx; SourceString
0x1800358cb  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x1800358cf  call    cs:__imp_RtlInitUnicodeString
0x1800358d5  lea     rdi, [rbp+3Fh+DestinationString]
0x1800358d9  mov     eax, cs:dword_1800DA020
0x1800358df  cmp     eax, 5
0x1800358e2  jbe     short loc_180035940
0x1800358e4  mov     qword ptr [rbp+3Fh+var_68], rbx
0x1800358e8  lea     rax, aStartingSessio; "Starting session"
0x1800358ef  mov     [rbp+3Fh+var_70], rax
0x1800358f3  lea     rax, [rbp+3Fh+var_68]
0x1800358f7  mov     [rsp+0C0h+var_98], rax
0x1800358fc  lea     rax, [rbp+3Fh+var_70]
0x180035900  mov     [rsp+0C0h+var_A0], rax
0x180035905  lea     rdx, word_1800C60C6
0x18003590c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180035911  jmp     short loc_180035940
0x180035913  mov     eax, cs:dword_1800DA020
0x180035919  cmp     eax, 5
0x18003591c  jbe     short loc_18003593E
0x18003591e  lea     rax, aStartingSessio; "Starting session"
0x180035925  mov     [rbp+3Fh+var_70], rax
0x180035929  lea     rax, [rbp+3Fh+var_70]
0x18003592d  mov     [rsp+0C0h+var_A0], rax
0x180035932  lea     rdx, byte_1800C60A1
0x180035939  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003593e  xor     edi, edi
0x180035940  lea     rax, [rbp+3Fh+arg_0]
0x180035944  mov     [rsp+0C0h+var_A0], rax
0x180035949  lea     r9, [rbp+3Fh+dwProcessId]
0x18003594d  mov     r8, rdi
0x180035950  mov     rdx, r14
0x180035953  mov     rcx, [r13+728h]
0x18003595a  call    SmStartCsr
0x18003595f  mov     edi, eax
0x180035961  or      edi, 10000000h
0x180035967  mov     [rbp+3Fh+var_68], edi
0x18003596a  jge     short loc_1800359D9
0x18003596c  xor     ecx, ecx
0x18003596e  mov     dword ptr [rbp+3Fh+arg_0], ecx
0x180035971  mov     eax, cs:dword_1800DA020
0x180035977  cmp     eax, 3
0x18003597a  jbe     loc_180035CF1
0x180035980  lea     rax, aStartcsr; "StartCsr"
0x180035987  mov     [rbp+3Fh+var_70], rax
0x18003598b  lea     rax, aSmstartcsrFail; "SmStartCsr failed"
0x180035992  mov     qword ptr [rbp+3Fh+dwProcessId], rax
0x180035996  lea     rax, aWarningHresult; "Warning HResult failed"
0x18003599d  mov     [rbp+3Fh+var_80], rax
0x1800359a1  lea     rax, [rbp+3Fh+var_70]
0x1800359a5  mov     [rsp+0C0h+var_88], rax
0x1800359aa  lea     rax, [rbp+3Fh+var_68]
0x1800359ae  mov     [rsp+0C0h+var_90], rax
0x1800359b3  lea     rax, [rbp+3Fh+dwProcessId]
0x1800359b7  mov     [rsp+0C0h+var_98], rax
0x1800359bc  lea     rax, [rbp+3Fh+var_80]
0x1800359c0  lea     rdx, word_1800C6062
0x1800359c7  mov     [rsp+0C0h+var_A0], rax
0x1800359cc  mov     [rbp+3Fh+var_68], edi
0x1800359cf  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800359d4  jmp     loc_180035CEE
0x1800359d9  mov     rsi, [rbp+3Fh+arg_0]
0x1800359dd  mov     r8d, [r14]
0x1800359e0  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x1800359e7  test    rbx, rbx
0x1800359ea  jnz     short loc_1800359FE
0x1800359ec  mov     dword ptr [rsp+0C0h+var_A0], esi
0x1800359f0  mov     rbx, qword ptr [rbp+3Fh+dwProcessId]
0x1800359f4  mov     r9d, ebx
0x1800359f7  call    ??$RaiseEvent@JKK@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@JKK@Z; CrimsonHelper::RaiseEvent<long,ulong,ulong>(_EVENT_DESCRIPTOR const &,long,ulong,ulong)
0x1800359fc  jmp     short loc_180035A13
0x1800359fe  mov     [rsp+0C0h+var_98], rbx
0x180035a03  mov     dword ptr [rsp+0C0h+var_A0], esi
0x180035a07  mov     rbx, qword ptr [rbp+3Fh+dwProcessId]
0x180035a0b  mov     r9d, ebx
0x180035a0e  call    ??$RaiseEvent@JKKPEBG@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@JKKPEBG@Z; CrimsonHelper::RaiseEvent<long,ulong,ulong,ushort const *>(_EVENT_DESCRIPTOR const &,long,ulong,ulong,ushort const *)
0x180035a13  mov     eax, cs:dword_1800DA020
0x180035a19  cmp     eax, 5
0x180035a1c  jbe     short loc_180035A6C
0x180035a1e  mov     eax, esi
0x180035a20  mov     [rbp+3Fh+arg_0], rax
0x180035a24  mov     eax, ebx
0x180035a26  mov     [rbp+3Fh+var_80], rax
0x180035a2a  movsxd  rax, dword ptr [r14]
0x180035a2d  mov     [rbp+3Fh+var_70], rax
0x180035a31  lea     rax, aStartedSession; "Started session"
0x180035a38  mov     qword ptr [rbp+3Fh+dwProcessId], rax
0x180035a3c  lea     rax, [rbp+3Fh+arg_0]
0x180035a40  mov     [rsp+0C0h+var_88], rax
0x180035a45  lea     rax, [rbp+3Fh+var_80]
0x180035a49  mov     [rsp+0C0h+var_90], rax
0x180035a4e  lea     rax, [rbp+3Fh+var_70]
0x180035a52  mov     [rsp+0C0h+var_98], rax
0x180035a57  lea     rax, [rbp+3Fh+dwProcessId]
0x180035a5b  mov     [rsp+0C0h+var_A0], rax
0x180035a60  lea     rdx, byte_1800C5FED
0x180035a67  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180035a6c  mov     dword ptr [rbp+3Fh+arg_0], 1
0x180035a73  mov     r8d, ebx; dwProcessId
0x180035a76  xor     edx, edx; bInheritHandle
0x180035a78  mov     ecx, 100000h; dwDesiredAccess
0x180035a7d  call    cs:__imp_OpenProcess
0x180035a83  mov     [r12], rax
0x180035a87  test    rax, rax
0x180035a8a  jnz     short loc_180035AE1
0x180035a8c  call    cs:__imp_GetLastError
0x180035a92  mov     edi, eax
0x180035a94  test    eax, eax
0x180035a96  jle     short loc_180035AA1
0x180035a98  movzx   edi, ax
0x180035a9b  or      edi, 80070000h
0x180035aa1  mov     eax, cs:dword_1800DA020
0x180035aa7  cmp     eax, 2
0x180035aaa  jbe     loc_180035CEE
0x180035ab0  lea     rax, aOpenprocessIni; "OpenProcess(InitialCommandProcessId) fa"...
0x180035ab7  lea     rdx, byte_1800C5FC3
0x180035abe  mov     [rbp+3Fh+var_80], rax
0x180035ac2  lea     rax, [rbp+3Fh+var_68]
0x180035ac6  mov     [rsp+0C0h+var_98], rax
0x180035acb  lea     rax, [rbp+3Fh+var_80]
0x180035acf  mov     [rsp+0C0h+var_A0], rax
0x180035ad4  mov     [rbp+3Fh+var_68], edi
0x180035ad7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180035adc  jmp     loc_180035CEE
0x180035ae1  lea     rdx, [rbp+3Fh+pSessionId]; pSessionId
0x180035ae5  mov     ecx, ebx; dwProcessId
0x180035ae7  call    cs:__imp_ProcessIdToSessionId
0x180035aed  test    eax, eax
0x180035aef  jnz     short loc_180035B25
0x180035af1  call    cs:__imp_GetLastError
0x180035af7  mov     edi, eax
0x180035af9  test    eax, eax
0x180035afb  jle     short loc_180035B06
0x180035afd  movzx   edi, ax
0x180035b00  or      edi, 80070000h
0x180035b06  mov     eax, cs:dword_1800DA020
0x180035b0c  cmp     eax, 2
0x180035b0f  jbe     loc_180035CEE
0x180035b15  lea     rax, aProcessidtoses; "ProcessIdToSessionId(InitialCommandProc"...
0x180035b1c  lea     rdx, byte_1800C5F99
0x180035b23  jmp     short loc_180035ABE
0x180035b25  mov     eax, [r14]
0x180035b28  cmp     [rbp+3Fh+pSessionId], eax
0x180035b2b  jz      short loc_180035B97
0x180035b2d  mov     edi, 8007000Dh
0x180035b32  mov     eax, cs:dword_1800DA020
0x180035b38  cmp     eax, 2
0x180035b3b  jbe     loc_180035D73
0x180035b41  mov     eax, [r14]
0x180035b44  mov     [rbp+3Fh+var_80], rax
0x180035b48  movsxd  rax, [rbp+3Fh+pSessionId]
0x180035b4c  mov     [rbp+3Fh+var_70], rax
0x180035b50  mov     dword ptr [rbp+3Fh+arg_0], 8007000Dh
0x180035b57  lea     rax, aWrongInitialCo; "Wrong Initial Command Session ID (doesn"...
0x180035b5e  mov     qword ptr [rbp+3Fh+dwProcessId], rax
0x180035b62  lea     rax, [rbp+3Fh+var_80]
0x180035b66  mov     [rsp+0C0h+var_88], rax
0x180035b6b  lea     rax, [rbp+3Fh+var_70]
0x180035b6f  mov     [rsp+0C0h+var_90], rax
0x180035b74  lea     rax, [rbp+3Fh+arg_0]
0x180035b78  mov     [rsp+0C0h+var_98], rax
0x180035b7d  lea     rax, [rbp+3Fh+dwProcessId]
0x180035b81  mov     [rsp+0C0h+var_A0], rax
0x180035b86  lea     rdx, word_1800C5F4A
0x180035b8d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180035b92  jmp     loc_180035D73
0x180035b97  mov     r8d, esi; dwProcessId
0x180035b9a  xor     edx, edx; bInheritHandle
0x180035b9c  mov     ecx, 101000h; dwDesiredAccess
0x180035ba1  call    cs:__imp_OpenProcess
0x180035ba7  mov     [r15], rax
0x180035baa  test    rax, rax
0x180035bad  jnz     short loc_180035BE6
0x180035baf  call    cs:__imp_GetLastError
0x180035bb5  mov     edi, eax
0x180035bb7  test    eax, eax
0x180035bb9  jle     short loc_180035BC4
0x180035bbb  movzx   edi, ax
0x180035bbe  or      edi, 80070000h
0x180035bc4  mov     eax, cs:dword_1800DA020
0x180035bca  cmp     eax, 2
0x180035bcd  jbe     loc_180035CEE
0x180035bd3  lea     rax, aOpenprocessWin; "OpenProcess(WindwsSubSysProcessId) fail"...
0x180035bda  lea     rdx, qword_1800C5F20
0x180035be1  jmp     loc_180035ABE
0x180035be6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180035bed  mov     ecx, 750h; unsigned __int64
0x180035bf2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180035bf7  mov     [rbp+3Fh+var_80], rax
0x180035bfb  test    rax, rax
0x180035bfe  jz      short loc_180035C27
0x180035c00  lea     rcx, [rbp+3Fh+var_68]
0x180035c04  mov     [rsp+0C0h+var_98], rcx; int *
0x180035c09  mov     rcx, [rbp+3Fh+arg_30]
0x180035c0d  mov     [rsp+0C0h+var_A0], rcx; struct ICsrEventSink *
0x180035c12  mov     r9, [r12]; void *
0x180035c16  mov     r8, [r15]; void *
0x180035c19  mov     edx, [r14]; int
0x180035c1c  mov     rcx, rax; this
0x180035c1f  call    ??0CCsrPipe@@QEAA@JPEAX0PEAVICsrEventSink@@PEAJ@Z; CCsrPipe::CCsrPipe(long,void *,void *,ICsrEventSink *,long *)
0x180035c24  mov     edi, [rbp+3Fh+var_68]
0x180035c27  mov     rdx, rax
0x180035c2a  lea     rcx, [rbp+3Fh+var_58]
0x180035c2e  call    ??4?$SmartPtr@VIWinlogonNotify@@@@QEAAAEAV0@PEAVIWinlogonNotify@@@Z; SmartPtr<IWinlogonNotify>::operator=(IWinlogonNotify *)
0x180035c33  mov     rbx, [rbp+3Fh+var_58]
0x180035c37  test    rbx, rbx
0x180035c3a  jnz     short loc_180035C46
0x180035c3c  mov     edi, 8007000Eh
0x180035c41  jmp     loc_180035D73
0x180035c46  test    edi, edi
0x180035c48  jns     short loc_180035CA5
0x180035c4a  mov     eax, cs:dword_1800DA020
0x180035c50  cmp     eax, 3
0x180035c53  jbe     loc_180035CEE
0x180035c59  lea     rax, aStartcsr; "StartCsr"
0x180035c60  mov     [rbp+3Fh+var_80], rax
0x180035c64  lea     rax, aCcsrpipeCcsrpi; "CCsrPipe::CCsrPipe"
0x180035c6b  mov     [rbp+3Fh+var_70], rax
0x180035c6f  lea     rax, aWarningHresult; "Warning HResult failed"
0x180035c76  mov     qword ptr [rbp+3Fh+dwProcessId], rax
0x180035c7a  lea     rax, [rbp+3Fh+var_80]
0x180035c7e  mov     [rsp+0C0h+var_88], rax
0x180035c83  lea     rax, [rbp+3Fh+var_68]
0x180035c87  mov     [rsp+0C0h+var_90], rax
0x180035c8c  lea     rax, [rbp+3Fh+var_70]
0x180035c90  mov     [rsp+0C0h+var_98], rax
0x180035c95  lea     rax, [rbp+3Fh+dwProcessId]
0x180035c99  lea     rdx, byte_1800C5EE1
0x180035ca0  jmp     loc_1800359C7
0x180035ca5  lea     rdx, [r13+6B8h]; struct CResource *
0x180035cac  lea     rcx, [rbp+3Fh+var_68]; this
0x180035cb0  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x180035cb5  nop
0x180035cb6  lea     rcx, [r13+6A0h]
0x180035cbd  mov     r8, rbx
0x180035cc0  mov     edx, [r14]
0x180035cc3  call    ?AddAt@?$SmartArray@VCCsrPipe@@J@@QEAAHJPEAVCCsrPipe@@@Z; SmartArray<CCsrPipe,long>::AddAt(long,CCsrPipe *)
0x180035cc8  test    eax, eax
0x180035cca  jz      short loc_180035D04
0x180035ccc  xor     edi, edi
0x180035cce  lea     rcx, [rbp+3Fh+var_68]; this
0x180035cd2  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180035cd7  nop
0x180035cd8  mov     rax, [rbp+3Fh+arg_28]
0x180035cdc  mov     [rax], rbx
0x180035cdf  mov     rax, [rbx]
0x180035ce2  mov     rcx, rbx
0x180035ce5  mov     rax, [rax+8]
0x180035ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035cee  mov     ecx, dword ptr [rbp+3Fh+arg_0]
0x180035cf1  test    edi, edi
0x180035cf3  jns     loc_180035DFC
0x180035cf9  cmp     ecx, 1
0x180035cfc  jnz     loc_180035DFC
  ... truncated ...
```
