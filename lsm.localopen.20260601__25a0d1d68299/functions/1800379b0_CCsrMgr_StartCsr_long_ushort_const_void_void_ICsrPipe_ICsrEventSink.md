# CCsrMgr::StartCsr(long *,ushort const *,void * *,void * *,ICsrPipe * *,ICsrEventSink *)

- ea: `0x1800379b0`
- end: `0x180038013`
- name: `?StartCsr@CCsrMgr@@UEAAJPEAJPEBGPEAPEAX2PEAPEAVICsrPipe@@PEAVICsrEventSink@@@Z`
- size: `1635`
- prototype: `int(CCsrMgr *__hidden this, int *, const unsigned __int16 *, void **, void **, struct ICsrPipe **, struct ICsrEventSink *)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001b90`
- `0x18000c684`
- `0x180010db4`
- `0x1800129d0`
- `0x180012e04`
- `0x180014b20`
- `0x18001d170`
- `0x180021bc0`
- `0x1800248e8`
- `0x18002701c`
- `0x18002772c`
- `0x1800291f4`
- `0x18002b8b8`
- `0x18002bd0c`
- `0x1800379b0`
- `0x1800495f0`
- `0x180049998`
- `0x18004a784`
- `0x18004ec5c`
- `0x18009c010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180037a7f`
- `ntdll!RtlInitUnicodeString` at `0x180037a7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037c48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037cb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037d83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037c48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037cb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037d83`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180037ca9`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180037ca9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037fac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037fc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037fac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037fc8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180037c33`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180037d6f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180037c33`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180037d6f`

## string_xrefs

- `0x180037c72`: `OpenProcess(InitialCommandProcessId) failed`
- `0x180037ce3`: `ProcessIdToSessionId(InitialCommandProcessId) failed`
- `0x180037d25`: `Wrong Initial Command Session ID (doesn't match pSessionId)`
- `0x180037dad`: `OpenProcess(WindwsSubSysProcessId) failed`

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
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  void **v14; // r15
  int v15; // edi
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  struct _UNICODE_STRING *p_DestinationString; // rdi
  int started; // eax
  int v21; // edx
  int v22; // r8d
  int v23; // r9d
  int v24; // ecx
  DWORD *v25; // rax
  __int16 *v26; // rdx
  DWORD v27; // esi
  int v28; // r8d
  DWORD v29; // ebx
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  HANDLE v33; // rax
  signed int LastError; // eax
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  const char *v38; // rax
  char *v39; // rdx
  int v40; // ecx
  int v41; // r8d
  int v42; // r9d
  signed int v43; // eax
  HANDLE v44; // rax
  signed int v45; // eax
  CCsrPipe *v46; // rax
  struct ICsrPipe *v47; // rbx
  int v48; // ecx
  int v49; // r8d
  int v50; // r9d
  int v51; // eax
  int v52; // r8d
  int v53; // r9d
  int *v55; // [rsp+28h] [rbp-59h]
  int *v56; // [rsp+28h] [rbp-59h]
  const char **v57; // [rsp+38h] [rbp-49h]
  const char *v58; // [rsp+40h] [rbp-41h] BYREF
  DWORD dwProcessId[2]; // [rsp+48h] [rbp-39h] BYREF
  const char *v60; // [rsp+50h] [rbp-31h] BYREF
  int v61[4]; // [rsp+58h] [rbp-29h] BYREF
  struct ICsrPipe *v62; // [rsp+68h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-11h] BYREF
  _BYTE v64[64]; // [rsp+80h] [rbp-1h] BYREF
  const char *v65; // [rsp+D0h] [rbp+4Fh] BYREF
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
    if ( (unsigned int)dword_1800DF020 > 2 )
    {
      v65 = "Shutting down. Can't StartCsr";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v11,
        (unsigned int)&dword_1800CB284,
        v12,
        v13,
        (__int64)&v65);
    }
    v15 = -805305602;
    goto LABEL_66;
  }
  if ( a3 )
  {
    RtlInitUnicodeString(&DestinationString, a3);
    p_DestinationString = &DestinationString;
    if ( (unsigned int)dword_1800DF020 > 5 )
    {
      *(_QWORD *)v61 = a3;
      v60 = "Starting session";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v16,
        (unsigned int)&word_1800CB24E,
        v17,
        v18,
        (__int64)&v60,
        (__int64)v61);
    }
  }
  else
  {
    if ( (unsigned int)dword_1800DF020 > 5 )
    {
      v60 = "Starting session";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v11,
        (unsigned int)byte_1800CB229,
        v12,
        v13,
        (__int64)&v60);
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
    if ( (unsigned int)dword_1800DF020 <= 3 )
    {
LABEL_51:
      if ( v15 >= 0 || v24 != 1 )
        goto LABEL_66;
      goto LABEL_57;
    }
    v60 = "StartCsr";
    *(_QWORD *)dwProcessId = "SmStartCsr failed";
    v58 = "Warning HResult failed";
    v57 = &v60;
    v55 = (int *)dwProcessId;
    v25 = (DWORD *)&v58;
    v26 = word_1800CB1EA;
LABEL_16:
    v61[0] = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v24,
      (_DWORD)v26,
      v22,
      v23,
      (__int64)v25,
      (__int64)v55,
      (__int64)v61,
      (__int64)v57);
LABEL_50:
    v24 = (int)v65;
    goto LABEL_51;
  }
  v27 = (unsigned int)v65;
  v28 = *a2;
  if ( a3 )
  {
    v56 = (int *)a3;
    v29 = dwProcessId[0];
    CrimsonHelper::RaiseEvent<long,unsigned long,unsigned long,unsigned short const *>(
      (unsigned int)&CrimsonHelper::s_instance,
      v21,
      v28,
      dwProcessId[0],
      (char)v65,
      (__int64)v56);
  }
  else
  {
    v29 = dwProcessId[0];
    CrimsonHelper::RaiseEvent<long,unsigned long,unsigned long>(
      (unsigned int)&CrimsonHelper::s_instance,
      v21,
      v28,
      dwProcessId[0],
      (char)v65);
  }
  if ( (unsigned int)dword_1800DF020 > 5 )
  {
    v65 = (const char *)v27;
    v58 = (const char *)v29;
    v60 = (const char *)*a2;
    *(_QWORD *)dwProcessId = "Started session";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      v30,
      (unsigned int)byte_1800CB175,
      v31,
      v32,
      (__int64)dwProcessId,
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
    if ( (unsigned int)dword_1800DF020 <= 2 )
      goto LABEL_50;
    v38 = "OpenProcess(InitialCommandProcessId) failed";
    v39 = byte_1800CB14B;
    goto LABEL_27;
  }
  if ( !ProcessIdToSessionId(v29, &pSessionId) )
  {
    v43 = GetLastError();
    v15 = v43;
    if ( v43 > 0 )
      v15 = (unsigned __int16)v43 | 0x80070000;
    if ( (unsigned int)dword_1800DF020 <= 2 )
      goto LABEL_50;
    v38 = "ProcessIdToSessionId(InitialCommandProcessId) failed";
    v39 = byte_1800CB121;
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
      if ( (unsigned int)dword_1800DF020 <= 2 )
        goto LABEL_50;
      v38 = "OpenProcess(WindwsSubSysProcessId) failed";
      v39 = (char *)qword_1800CB0A8;
LABEL_27:
      v58 = v38;
      v61[0] = v15;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v35,
        (_DWORD)v39,
        v36,
        v37,
        (__int64)&v58,
        (__int64)v61);
      goto LABEL_50;
    }
    v46 = (CCsrPipe *)operator new(0x750u, (const struct std::nothrow_t *)&std::nothrow);
    v58 = (const char *)v46;
    if ( v46 )
    {
      v46 = CCsrPipe::CCsrPipe(v46, *a2, *v14, *a4, a7, v61);
      v15 = v61[0];
    }
    SmartPtr<IWinlogonNotify>::operator=(&v62, v46);
    v47 = v62;
    if ( v62 )
    {
      if ( v15 < 0 )
      {
        if ( (unsigned int)dword_1800DF020 <= 3 )
          goto LABEL_50;
        v58 = "StartCsr";
        v60 = "CCsrPipe::CCsrPipe";
        *(_QWORD *)dwProcessId = "Warning HResult failed";
        v57 = &v58;
        v55 = (int *)&v60;
        v25 = dwProcessId;
        v26 = (__int16 *)byte_1800CB069;
        goto LABEL_16;
      }
      CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v61, (CCsrMgr *)((char *)this + 1720));
      if ( (unsigned int)SmartArray<CCsrPipe,long>::AddAt((char *)this + 1696, (unsigned int)*a2, v47) )
      {
        v15 = 0;
        CAutoLock::Unlock((CAutoLock *)v61);
        *a6 = v47;
        (*(void (__fastcall **)(struct ICsrPipe *))(*(_QWORD *)v47 + 8LL))(v47);
        goto LABEL_50;
      }
      v15 = -2147024882;
      if ( (unsigned int)dword_1800DF020 > 3 )
      {
        v58 = "StartCsr";
        LODWORD(v65) = -2147024882;
        v60 = "CsrPipes.AddAt";
        *(_QWORD *)dwProcessId = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v48,
          (unsigned int)word_1800CB02A,
          v49,
          v50,
          (__int64)dwProcessId,
          (__int64)&v60,
          (__int64)&v65,
          (__int64)&v58);
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
    if ( (unsigned int)dword_1800DF020 > 2 )
    {
      v58 = (const char *)(unsigned int)*a2;
      v60 = (const char *)(int)pSessionId;
      LODWORD(v65) = -2147024883;
      *(_QWORD *)dwProcessId = "Wrong Initial Command Session ID (doesn't match pSessionId)";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v40,
        (unsigned int)word_1800CB0D2,
        v41,
        v42,
        (__int64)dwProcessId,
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
  else if ( (unsigned int)dword_1800DF020 > 2 )
  {
    LODWORD(v65) = v51;
    v58 = "Failed to stop CSR";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_1800DF020,
      (unsigned int)byte_1800CAFFD,
      v52,
      v53,
      (__int64)&v58,
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
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v62);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800379b0  mov     [rsp-8+arg_8], rbx
0x1800379b5  push    rbp
0x1800379b6  push    rsi
0x1800379b7  push    rdi
0x1800379b8  push    r12
0x1800379ba  push    r13
0x1800379bc  push    r14
0x1800379be  push    r15
0x1800379c0  lea     rbp, [rsp-0Fh]
0x1800379c5  sub     rsp, 90h
0x1800379cc  mov     r12, r9
0x1800379cf  mov     rbx, r8
0x1800379d2  mov     r14, rdx
0x1800379d5  mov     r13, rcx
0x1800379d8  xorps   xmm0, xmm0
0x1800379db  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x1800379df  mov     [rbp+3Fh+arg_0], 0
0x1800379e7  mov     qword ptr [rbp+3Fh+dwProcessId], 0
0x1800379ef  mov     [rbp+3Fh+var_58], 0
0x1800379f7  mov     [rbp+3Fh+pSessionId], 0
0x1800379fe  lea     rdx, [rcx+638h]; struct CResource *
0x180037a05  lea     rcx, [rbp+3Fh+var_40]; this
0x180037a09  call    ??0CAutoSharedLock@@QEAA@AEAVCResource@@@Z; CAutoSharedLock::CAutoSharedLock(CResource &)
0x180037a0e  nop
0x180037a0f  test    r12, r12
0x180037a12  jz      loc_180037FDD
0x180037a18  mov     qword ptr [r12], 0
0x180037a20  mov     r15, [rbp+3Fh+arg_20]
0x180037a24  test    r15, r15
0x180037a27  jz      loc_180037FDD
0x180037a2d  mov     qword ptr [r15], 0
0x180037a34  cmp     dword ptr [r13+730h], 0
0x180037a3c  jz      short loc_180037A73
0x180037a3e  mov     eax, cs:dword_1800DF020
0x180037a44  cmp     eax, 2
0x180037a47  jbe     short loc_180037A69
0x180037a49  lea     rax, aShuttingDownCa; "Shutting down. Can't StartCsr"
0x180037a50  mov     [rbp+3Fh+arg_0], rax
0x180037a54  lea     rax, [rbp+3Fh+arg_0]
0x180037a58  mov     [rsp+0C0h+var_A0], rax
0x180037a5d  lea     rdx, dword_1800CB284
0x180037a64  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180037a69  mov     edi, 0D00002FEh
0x180037a6e  jmp     loc_180037FE2
0x180037a73  test    rbx, rbx
0x180037a76  jz      short loc_180037AC9
0x180037a78  mov     rdx, rbx; SourceString
0x180037a7b  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x180037a7f  call    cs:__imp_RtlInitUnicodeString
0x180037a86  nop     dword ptr [rax+rax+00h]
0x180037a8b  lea     rdi, [rbp+3Fh+DestinationString]
0x180037a8f  mov     eax, cs:dword_1800DF020
0x180037a95  cmp     eax, 5
0x180037a98  jbe     short loc_180037AF6
0x180037a9a  mov     qword ptr [rbp+3Fh+var_68], rbx
0x180037a9e  lea     rax, aStartingSessio; "Starting session"
0x180037aa5  mov     [rbp+3Fh+var_70], rax
0x180037aa9  lea     rax, [rbp+3Fh+var_68]
0x180037aad  mov     [rsp+0C0h+var_98], rax
0x180037ab2  lea     rax, [rbp+3Fh+var_70]
0x180037ab6  mov     [rsp+0C0h+var_A0], rax
0x180037abb  lea     rdx, word_1800CB24E
0x180037ac2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180037ac7  jmp     short loc_180037AF6
0x180037ac9  mov     eax, cs:dword_1800DF020
0x180037acf  cmp     eax, 5
0x180037ad2  jbe     short loc_180037AF4
0x180037ad4  lea     rax, aStartingSessio; "Starting session"
0x180037adb  mov     [rbp+3Fh+var_70], rax
0x180037adf  lea     rax, [rbp+3Fh+var_70]
0x180037ae3  mov     [rsp+0C0h+var_A0], rax
0x180037ae8  lea     rdx, byte_1800CB229
0x180037aef  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180037af4  xor     edi, edi
0x180037af6  lea     rax, [rbp+3Fh+arg_0]
0x180037afa  mov     [rsp+0C0h+var_A0], rax
0x180037aff  lea     r9, [rbp+3Fh+dwProcessId]
0x180037b03  mov     r8, rdi
0x180037b06  mov     rdx, r14
0x180037b09  mov     rcx, [r13+728h]
0x180037b10  call    SmStartCsr
0x180037b15  mov     edi, eax
0x180037b17  or      edi, 10000000h
0x180037b1d  mov     [rbp+3Fh+var_68], edi
0x180037b20  jge     short loc_180037B8F
0x180037b22  xor     ecx, ecx
0x180037b24  mov     dword ptr [rbp+3Fh+arg_0], ecx
0x180037b27  mov     eax, cs:dword_1800DF020
0x180037b2d  cmp     eax, 3
0x180037b30  jbe     loc_180037ECB
0x180037b36  lea     rax, aStartcsr; "StartCsr"
0x180037b3d  mov     [rbp+3Fh+var_70], rax
0x180037b41  lea     rax, aSmstartcsrFail; "SmStartCsr failed"
0x180037b48  mov     qword ptr [rbp+3Fh+dwProcessId], rax
0x180037b4c  lea     rax, aWarningHresult; "Warning HResult failed"
0x180037b53  mov     [rbp+3Fh+var_80], rax
0x180037b57  lea     rax, [rbp+3Fh+var_70]
0x180037b5b  mov     [rsp+0C0h+var_88], rax
0x180037b60  lea     rax, [rbp+3Fh+var_68]
0x180037b64  mov     [rsp+0C0h+var_90], rax
0x180037b69  lea     rax, [rbp+3Fh+dwProcessId]
0x180037b6d  mov     [rsp+0C0h+var_98], rax
0x180037b72  lea     rax, [rbp+3Fh+var_80]
0x180037b76  lea     rdx, word_1800CB1EA
0x180037b7d  mov     [rsp+0C0h+var_A0], rax
0x180037b82  mov     [rbp+3Fh+var_68], edi
0x180037b85  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180037b8a  jmp     loc_180037EC8
0x180037b8f  mov     rsi, [rbp+3Fh+arg_0]
0x180037b93  mov     r8d, [r14]
0x180037b96  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x180037b9d  test    rbx, rbx
0x180037ba0  jnz     short loc_180037BB4
0x180037ba2  mov     dword ptr [rsp+0C0h+var_A0], esi
0x180037ba6  mov     rbx, qword ptr [rbp+3Fh+dwProcessId]
0x180037baa  mov     r9d, ebx
0x180037bad  call    ??$RaiseEvent@JKK@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@JKK@Z; CrimsonHelper::RaiseEvent<long,ulong,ulong>(_EVENT_DESCRIPTOR const &,long,ulong,ulong)
0x180037bb2  jmp     short loc_180037BC9
0x180037bb4  mov     [rsp+0C0h+var_98], rbx
0x180037bb9  mov     dword ptr [rsp+0C0h+var_A0], esi
0x180037bbd  mov     rbx, qword ptr [rbp+3Fh+dwProcessId]
0x180037bc1  mov     r9d, ebx
0x180037bc4  call    ??$RaiseEvent@JKKPEBG@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@JKKPEBG@Z; CrimsonHelper::RaiseEvent<long,ulong,ulong,ushort const *>(_EVENT_DESCRIPTOR const &,long,ulong,ulong,ushort const *)
0x180037bc9  mov     eax, cs:dword_1800DF020
0x180037bcf  cmp     eax, 5
0x180037bd2  jbe     short loc_180037C22
0x180037bd4  mov     eax, esi
0x180037bd6  mov     [rbp+3Fh+arg_0], rax
0x180037bda  mov     eax, ebx
0x180037bdc  mov     [rbp+3Fh+var_80], rax
0x180037be0  movsxd  rax, dword ptr [r14]
0x180037be3  mov     [rbp+3Fh+var_70], rax
0x180037be7  lea     rax, aStartedSession; "Started session"
0x180037bee  mov     qword ptr [rbp+3Fh+dwProcessId], rax
0x180037bf2  lea     rax, [rbp+3Fh+arg_0]
0x180037bf6  mov     [rsp+0C0h+var_88], rax
0x180037bfb  lea     rax, [rbp+3Fh+var_80]
0x180037bff  mov     [rsp+0C0h+var_90], rax
0x180037c04  lea     rax, [rbp+3Fh+var_70]
0x180037c08  mov     [rsp+0C0h+var_98], rax
0x180037c0d  lea     rax, [rbp+3Fh+dwProcessId]
0x180037c11  mov     [rsp+0C0h+var_A0], rax
0x180037c16  lea     rdx, byte_1800CB175
0x180037c1d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180037c22  mov     dword ptr [rbp+3Fh+arg_0], 1
0x180037c29  mov     r8d, ebx; dwProcessId
0x180037c2c  xor     edx, edx; bInheritHandle
0x180037c2e  mov     ecx, 100000h; dwDesiredAccess
0x180037c33  call    cs:__imp_OpenProcess
0x180037c3a  nop     dword ptr [rax+rax+00h]
0x180037c3f  mov     [r12], rax
0x180037c43  test    rax, rax
0x180037c46  jnz     short loc_180037CA3
0x180037c48  call    cs:__imp_GetLastError
0x180037c4f  nop     dword ptr [rax+rax+00h]
0x180037c54  mov     edi, eax
0x180037c56  test    eax, eax
0x180037c58  jle     short loc_180037C63
0x180037c5a  movzx   edi, ax
0x180037c5d  or      edi, 80070000h
0x180037c63  mov     eax, cs:dword_1800DF020
0x180037c69  cmp     eax, 2
0x180037c6c  jbe     loc_180037EC8
0x180037c72  lea     rax, aOpenprocessIni; "OpenProcess(InitialCommandProcessId) fa"...
0x180037c79  lea     rdx, byte_1800CB14B
0x180037c80  mov     [rbp+3Fh+var_80], rax
0x180037c84  lea     rax, [rbp+3Fh+var_68]
0x180037c88  mov     [rsp+0C0h+var_98], rax
0x180037c8d  lea     rax, [rbp+3Fh+var_80]
0x180037c91  mov     [rsp+0C0h+var_A0], rax
0x180037c96  mov     [rbp+3Fh+var_68], edi
0x180037c99  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180037c9e  jmp     loc_180037EC8
0x180037ca3  lea     rdx, [rbp+3Fh+pSessionId]; pSessionId
0x180037ca7  mov     ecx, ebx; dwProcessId
0x180037ca9  call    cs:__imp_ProcessIdToSessionId
0x180037cb0  nop     dword ptr [rax+rax+00h]
0x180037cb5  test    eax, eax
0x180037cb7  jnz     short loc_180037CF3
0x180037cb9  call    cs:__imp_GetLastError
0x180037cc0  nop     dword ptr [rax+rax+00h]
0x180037cc5  mov     edi, eax
0x180037cc7  test    eax, eax
0x180037cc9  jle     short loc_180037CD4
0x180037ccb  movzx   edi, ax
0x180037cce  or      edi, 80070000h
0x180037cd4  mov     eax, cs:dword_1800DF020
0x180037cda  cmp     eax, 2
0x180037cdd  jbe     loc_180037EC8
0x180037ce3  lea     rax, aProcessidtoses; "ProcessIdToSessionId(InitialCommandProc"...
0x180037cea  lea     rdx, byte_1800CB121
0x180037cf1  jmp     short loc_180037C80
0x180037cf3  mov     eax, [r14]
0x180037cf6  cmp     [rbp+3Fh+pSessionId], eax
0x180037cf9  jz      short loc_180037D65
0x180037cfb  mov     edi, 8007000Dh
0x180037d00  mov     eax, cs:dword_1800DF020
0x180037d06  cmp     eax, 2
0x180037d09  jbe     loc_180037F4D
0x180037d0f  mov     eax, [r14]
0x180037d12  mov     [rbp+3Fh+var_80], rax
0x180037d16  movsxd  rax, [rbp+3Fh+pSessionId]
0x180037d1a  mov     [rbp+3Fh+var_70], rax
0x180037d1e  mov     dword ptr [rbp+3Fh+arg_0], 8007000Dh
0x180037d25  lea     rax, aWrongInitialCo; "Wrong Initial Command Session ID (doesn"...
0x180037d2c  mov     qword ptr [rbp+3Fh+dwProcessId], rax
0x180037d30  lea     rax, [rbp+3Fh+var_80]
0x180037d34  mov     [rsp+0C0h+var_88], rax
0x180037d39  lea     rax, [rbp+3Fh+var_70]
0x180037d3d  mov     [rsp+0C0h+var_90], rax
0x180037d42  lea     rax, [rbp+3Fh+arg_0]
0x180037d46  mov     [rsp+0C0h+var_98], rax
0x180037d4b  lea     rax, [rbp+3Fh+dwProcessId]
0x180037d4f  mov     [rsp+0C0h+var_A0], rax
0x180037d54  lea     rdx, word_1800CB0D2
0x180037d5b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180037d60  jmp     loc_180037F4D
0x180037d65  mov     r8d, esi; dwProcessId
0x180037d68  xor     edx, edx; bInheritHandle
0x180037d6a  mov     ecx, 101000h; dwDesiredAccess
0x180037d6f  call    cs:__imp_OpenProcess
0x180037d76  nop     dword ptr [rax+rax+00h]
0x180037d7b  mov     [r15], rax
0x180037d7e  test    rax, rax
0x180037d81  jnz     short loc_180037DC0
0x180037d83  call    cs:__imp_GetLastError
0x180037d8a  nop     dword ptr [rax+rax+00h]
0x180037d8f  mov     edi, eax
0x180037d91  test    eax, eax
0x180037d93  jle     short loc_180037D9E
0x180037d95  movzx   edi, ax
0x180037d98  or      edi, 80070000h
0x180037d9e  mov     eax, cs:dword_1800DF020
0x180037da4  cmp     eax, 2
0x180037da7  jbe     loc_180037EC8
0x180037dad  lea     rax, aOpenprocessWin; "OpenProcess(WindwsSubSysProcessId) fail"...
0x180037db4  lea     rdx, qword_1800CB0A8
0x180037dbb  jmp     loc_180037C80
0x180037dc0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180037dc7  mov     ecx, 750h; unsigned __int64
0x180037dcc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180037dd1  mov     [rbp+3Fh+var_80], rax
0x180037dd5  test    rax, rax
0x180037dd8  jz      short loc_180037E01
0x180037dda  lea     rcx, [rbp+3Fh+var_68]
0x180037dde  mov     [rsp+0C0h+var_98], rcx; int *
0x180037de3  mov     rcx, [rbp+3Fh+arg_30]
0x180037de7  mov     [rsp+0C0h+var_A0], rcx; struct ICsrEventSink *
0x180037dec  mov     r9, [r12]; void *
0x180037df0  mov     r8, [r15]; void *
0x180037df3  mov     edx, [r14]; int
0x180037df6  mov     rcx, rax; this
0x180037df9  call    ??0CCsrPipe@@QEAA@JPEAX0PEAVICsrEventSink@@PEAJ@Z; CCsrPipe::CCsrPipe(long,void *,void *,ICsrEventSink *,long *)
0x180037dfe  mov     edi, [rbp+3Fh+var_68]
0x180037e01  mov     rdx, rax
0x180037e04  lea     rcx, [rbp+3Fh+var_58]
0x180037e08  call    ??4?$SmartPtr@VIWinlogonNotify@@@@QEAAAEAV0@PEAVIWinlogonNotify@@@Z; SmartPtr<IWinlogonNotify>::operator=(IWinlogonNotify *)
0x180037e0d  mov     rbx, [rbp+3Fh+var_58]
0x180037e11  test    rbx, rbx
0x180037e14  jnz     short loc_180037E20
0x180037e16  mov     edi, 8007000Eh
0x180037e1b  jmp     loc_180037F4D
0x180037e20  test    edi, edi
0x180037e22  jns     short loc_180037E7F
0x180037e24  mov     eax, cs:dword_1800DF020
0x180037e2a  cmp     eax, 3
0x180037e2d  jbe     loc_180037EC8
0x180037e33  lea     rax, aStartcsr; "StartCsr"
0x180037e3a  mov     [rbp+3Fh+var_80], rax
0x180037e3e  lea     rax, aCcsrpipeCcsrpi; "CCsrPipe::CCsrPipe"
0x180037e45  mov     [rbp+3Fh+var_70], rax
0x180037e49  lea     rax, aWarningHresult; "Warning HResult failed"
0x180037e50  mov     qword ptr [rbp+3Fh+dwProcessId], rax
0x180037e54  lea     rax, [rbp+3Fh+var_80]
0x180037e58  mov     [rsp+0C0h+var_88], rax
0x180037e5d  lea     rax, [rbp+3Fh+var_68]
0x180037e61  mov     [rsp+0C0h+var_90], rax
0x180037e66  lea     rax, [rbp+3Fh+var_70]
0x180037e6a  mov     [rsp+0C0h+var_98], rax
0x180037e6f  lea     rax, [rbp+3Fh+dwProcessId]
0x180037e73  lea     rdx, byte_1800CB069
0x180037e7a  jmp     loc_180037B7D
0x180037e7f  lea     rdx, [r13+6B8h]; struct CResource *
0x180037e86  lea     rcx, [rbp+3Fh+var_68]; this
0x180037e8a  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x180037e8f  nop
0x180037e90  lea     rcx, [r13+6A0h]
0x180037e97  mov     r8, rbx
0x180037e9a  mov     edx, [r14]
0x180037e9d  call    ?AddAt@?$SmartArray@VCCsrPipe@@J@@QEAAHJPEAVCCsrPipe@@@Z; SmartArray<CCsrPipe,long>::AddAt(long,CCsrPipe *)
0x180037ea2  test    eax, eax
0x180037ea4  jz      short loc_180037EDE
0x180037ea6  xor     edi, edi
0x180037ea8  lea     rcx, [rbp+3Fh+var_68]; this
0x180037eac  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180037eb1  nop
0x180037eb2  mov     rax, [rbp+3Fh+arg_28]
0x180037eb6  mov     [rax], rbx
0x180037eb9  mov     rax, [rbx]
0x180037ebc  mov     rcx, rbx
  ... truncated ...
```
