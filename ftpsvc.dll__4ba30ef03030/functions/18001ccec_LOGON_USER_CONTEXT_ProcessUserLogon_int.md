# LOGON_USER_CONTEXT::ProcessUserLogon(int *)

- ea: `0x18001ccec`
- end: `0x18001d2e5`
- name: `?ProcessUserLogon@LOGON_USER_CONTEXT@@QEAAJPEAH@Z`
- size: `1529`
- prototype: `__int64 __fastcall(LOGON_USER_CONTEXT *__hidden this, int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001bd7c`
- `0x18001c15c`

## callees

- `0x180009090`
- `0x180015928`
- `0x18001af2c`
- `0x18001b3ac`
- `0x18001b90c`
- `0x18001c450`
- `0x18001c998`
- `0x18001ccec`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001ced8`
- `msvcrt!_wcsicmp` at `0x18001ced8`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001cd30`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001cd30`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001d290`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001d290`
- `iisutil!PuDbgPrint` at `0x18001ce14`
- `iisutil!PuDbgPrint` at `0x18001ce5b`
- `iisutil!PuDbgPrint` at `0x18001d09e`
- `iisutil!PuDbgPrint` at `0x18001ce14`
- `iisutil!PuDbgPrint` at `0x18001ce5b`
- `iisutil!PuDbgPrint` at `0x18001d09e`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001cd65`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001cd65`
- `iisutil!WriteRefTraceLog` at `0x18001cd55`
- `iisutil!WriteRefTraceLog` at `0x18001d26e`
- `iisutil!WriteRefTraceLog` at `0x18001cd55`
- `iisutil!WriteRefTraceLog` at `0x18001d26e`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18001cf86`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18001cf86`

## string_xrefs

- `0x18001d2ae`: `An error occurred during the authentication process.`
- `0x18001cded`: `Warning: Client Cert logon attempt failed with 0x%x.\nNext supported authentication method will be attempted\n`
- `0x18001ce34`: `Client cert logon attempt failed with 0x%x.\n`
- `0x18001cfc6`: `Anonymous logon attempt failed with 0x%x.\n`
- `0x18001d077`: `Warning: Basic logon attempt failed with 0x%x.\nNext supported authentication method will be attempted\n`
- `0x18001d0be`: `Basic logon attempt failed with 0x%x.\n`
- `0x18001d245`: `Home directory lookup failed.`

## pseudocode

```c
__int64 __fastcall LOGON_USER_CONTEXT::ProcessUserLogon(LOGON_USER_CONTEXT *this, int *a2)
{
  int v4; // ebx
  __int64 v5; // rsi
  __int64 v6; // rdx
  __int64 v7; // r14
  const wchar_t *v8; // r15
  const unsigned __int16 *v9; // r12
  void *v10; // rdx
  int v11; // eax
  unsigned __int32 v12; // ecx
  unsigned __int32 v13; // edx
  unsigned __int32 v14; // eax
  FTP_SITE_PERF_CTRS *j; // rcx
  unsigned __int32 v16; // eax
  __int64 v17; // rax
  __int64 v18; // rbx
  CEtwTracer *v19; // rax
  const wchar_t *v20; // rax
  int v21; // eax
  unsigned __int32 v22; // ecx
  unsigned __int32 v23; // edx
  unsigned __int32 v24; // eax
  FTP_SITE_PERF_CTRS *k; // rcx
  unsigned __int32 v26; // eax
  int v27; // eax
  unsigned __int32 v28; // ecx
  unsigned __int32 v29; // edx
  unsigned __int32 v30; // eax
  FTP_SITE_PERF_CTRS *m; // rcx
  unsigned __int32 v32; // eax
  int v33; // eax
  unsigned __int32 v34; // edx
  unsigned __int32 v35; // ecx
  unsigned __int32 v36; // eax
  FTP_SITE_PERF_CTRS *i; // rdx
  unsigned __int32 v38; // eax
  int v39; // eax
  bool v40; // zf
  __int64 v41; // rcx
  _BYTE *v42; // rax
  unsigned __int32 v43; // esi
  const unsigned __int16 *v45; // [rsp+20h] [rbp-49h]
  unsigned __int16 *v46; // [rsp+28h] [rbp-41h]
  unsigned __int16 *v47; // [rsp+28h] [rbp-41h]
  __int16 v48; // [rsp+40h] [rbp-29h] BYREF
  __int128 v49; // [rsp+42h] [rbp-27h]
  __int128 v50; // [rsp+52h] [rbp-17h]
  _BYTE v51[22]; // [rsp+62h] [rbp-7h]
  int v52; // [rsp+78h] [rbp+Fh]
  int v53; // [rsp+7Ch] [rbp+13h]

  v4 = 0;
  v5 = *(_QWORD *)(*((_QWORD *)this + 1) + 16LL);
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v5 + 208));
  v6 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v5 + 192));
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v6);
  v7 = *(_QWORD *)(v5 + 192);
  CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)(v5 + 208));
  v8 = (const wchar_t *)*((_QWORD *)this + 7);
  v9 = (const unsigned __int16 *)*((_QWORD *)this + 14);
  v10 = (void *)*((_QWORD *)this + 28);
  *a2 = 0;
  if ( *((_DWORD *)this + 120) != 100 )
  {
    if ( *((_DWORD *)this + 120) == 101 )
    {
LABEL_74:
      v4 = LOGON_USER_CONTEXT::LookupHomeDirectory(this, a2);
      if ( v4 >= 0 )
        goto LABEL_77;
      *((_DWORD *)this + 126) = 33;
      v20 = L"Home directory lookup failed.";
      goto LABEL_76;
    }
    if ( *((_DWORD *)this + 120) != 102 )
    {
      if ( *((_DWORD *)this + 120) != 103 )
        goto LABEL_77;
      goto LABEL_62;
    }
LABEL_58:
    if ( !*((_DWORD *)this + 54) )
    {
      v4 = LOGON_USER_CONTEXT::ProcessCustomAuthentication(this, v4, a2);
      if ( v4 < 0 || *a2 )
        goto LABEL_77;
      *((_DWORD *)this + 120) = 103;
    }
LABEL_62:
    if ( *((_DWORD *)this + 120) == 103 )
    {
      v33 = FTP_USER::Initialize(
              (FTP_USER *)(*((_QWORD *)this + 1) + 24LL),
              *((struct USER_SESSION **)this + 1),
              0,
              *((const unsigned __int16 **)this + 7),
              v45,
              (wchar_t *)L"CustomAuth",
              1);
      v4 = v33;
      if ( v33 < 0 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          LODWORD(v47) = v33;
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\logon_user_context.cxx",
            425,
            "LOGON_USER_CONTEXT::ProcessUserLogon",
            "Custom authentication user context initialization failed with 0x%x.\r\n",
            v47);
        }
        goto LABEL_77;
      }
      v34 = _InterlockedIncrement((volatile signed __int32 *)(v5 + 120));
      v35 = _InterlockedIncrement((volatile signed __int32 *)FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal + 12);
      while ( 1 )
      {
        v36 = *(_DWORD *)(v5 + 136);
        if ( v36 >= v34 )
          break;
        _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 136), v34, v36);
      }
      for ( i = FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal;
            ;
            _InterlockedCompareExchange((volatile signed __int32 *)i + 16, v35, v38) )
      {
        v38 = *((_DWORD *)i + 16);
        if ( v38 >= v35 )
          break;
      }
      _InterlockedAdd((volatile signed __int32 *)(v5 + 128), 1u);
      v39 = *((_DWORD *)this + 32);
      v40 = 2 * v39 == 0;
      v41 = (unsigned int)(2 * v39);
      v42 = (_BYTE *)*((_QWORD *)this + 14);
      if ( !v40 )
      {
        do
        {
          *v42++ = 0;
          --v41;
        }
        while ( v41 );
      }
    }
    goto LABEL_74;
  }
  if ( !*((_DWORD *)this + 54) && *(_DWORD *)(v7 + 256) && v10 )
  {
    v11 = LOGON_USER_CONTEXT::HandleClientCertAuthLogon(this, v10);
    v4 = v11;
    if ( v11 == -2147023570 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\logon_user_context.cxx",
          250,
          "LOGON_USER_CONTEXT::ProcessUserLogon",
          "Warning: Client Cert logon attempt failed with 0x%x.\r\n"
          "Next supported authentication method will be attempted\r\n",
          -2147023570);
    }
    else
    {
      if ( v11 < 0 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\logon_user_context.cxx",
            258,
            "LOGON_USER_CONTEXT::ProcessUserLogon",
            "Client cert logon attempt failed with 0x%x.\r\n",
            v11);
        goto LABEL_77;
      }
      v12 = _InterlockedIncrement((volatile signed __int32 *)(v5 + 120));
      v13 = _InterlockedIncrement((volatile signed __int32 *)FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal + 12);
      while ( 1 )
      {
        v14 = *(_DWORD *)(v5 + 136);
        if ( v14 >= v12 )
          break;
        _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 136), v12, v14);
      }
      for ( j = FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal;
            ;
            _InterlockedCompareExchange((volatile signed __int32 *)j + 16, v13, v16) )
      {
        v16 = *((_DWORD *)j + 16);
        if ( v16 >= v13 )
          break;
      }
      _InterlockedAdd((volatile signed __int32 *)(v5 + 128), 1u);
      *((_DWORD *)this + 54) = 1;
    }
  }
  if ( *((_DWORD *)this + 54) )
    goto LABEL_62;
  if ( !_wcsicmp(v8, L"Anonymous") )
  {
    if ( !*(_DWORD *)(v7 + 184) )
    {
      v17 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      if ( *(_DWORD *)(v17 + 8) && (*(_BYTE *)(v17 + 40) & 8) != 0 && *(_DWORD *)(v17 + 44) >= 2u )
      {
        v18 = *((_QWORD *)this + 1) + 1272LL;
        v19 = (CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
        v49 = 0;
        v50 = 0;
        *(_OWORD *)v51 = 0;
        v53 = 0;
        *(_DWORD *)&v51[10] = 1703936;
        v48 = 64;
        WORD2(v49) = 1;
        BYTE2(v49) = 12;
        *(_QWORD *)((char *)&v50 + 6) = &`FtpAuthenticationEvents::GetAreaGuid'::`2'::AreaGuid;
        *(_QWORD *)&v51[14] = v18;
        v52 = 16;
        CEtwTracer::EtwTraceEvent(v19, (struct _EVENT_TRACE_HEADER *)&v48);
      }
      *((_DWORD *)this + 126) = 42;
      v20 = L"Anonymous authentication is not allowed.";
      v4 = -2147023570;
LABEL_76:
      *((_QWORD *)this + 64) = v20;
      goto LABEL_77;
    }
    v21 = LOGON_USER_CONTEXT::HandleAnonymousLogon(this, (struct ANONYMOUS_AUTHENTICATION_CONFIG_ELEMENT *)(v7 + 176));
    v4 = v21;
    if ( v21 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(v46) = v21;
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\logon_user_context.cxx",
          303,
          "LOGON_USER_CONTEXT::ProcessUserLogon",
          "Anonymous logon attempt failed with 0x%x.\r\n",
          v46);
      }
      goto LABEL_77;
    }
    v22 = _InterlockedIncrement((volatile signed __int32 *)(v5 + 116));
    v23 = _InterlockedIncrement((volatile signed __int32 *)FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal + 11);
    _InterlockedAdd((volatile signed __int32 *)(v5 + 124), 1u);
    while ( 1 )
    {
      v24 = *(_DWORD *)(v5 + 132);
      if ( v24 >= v22 )
        break;
      _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 132), v22, v24);
    }
    for ( k = FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal;
          ;
          _InterlockedCompareExchange((volatile signed __int32 *)k + 15, v23, v26) )
    {
      v26 = *((_DWORD *)k + 15);
      if ( v26 >= v23 )
        break;
    }
    *((_DWORD *)this + 54) = 1;
  }
  if ( *((_DWORD *)this + 54) )
    goto LABEL_62;
  if ( !*(_DWORD *)(v7 + 224) )
    goto LABEL_58;
  v27 = LOGON_USER_CONTEXT::HandleBasicLogon(this, v8, v9, (struct BASIC_AUTHENTICATION_CONFIG_ELEMENT *)(v7 + 216));
  v4 = v27;
  if ( v27 == -2147023570 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\logon_user_context.cxx",
        335,
        "LOGON_USER_CONTEXT::ProcessUserLogon",
        "Warning: Basic logon attempt failed with 0x%x.\r\nNext supported authentication method will be attempted\r\n",
        -2147023570);
    goto LABEL_58;
  }
  if ( v27 >= 0 )
  {
    v28 = _InterlockedIncrement((volatile signed __int32 *)(v5 + 120));
    v29 = _InterlockedIncrement((volatile signed __int32 *)FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal + 12);
    while ( 1 )
    {
      v30 = *(_DWORD *)(v5 + 136);
      if ( v30 >= v28 )
        break;
      _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 136), v28, v30);
    }
    for ( m = FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal;
          ;
          _InterlockedCompareExchange((volatile signed __int32 *)m + 16, v29, v32) )
    {
      v32 = *((_DWORD *)m + 16);
      if ( v32 >= v29 )
        break;
    }
    _InterlockedAdd((volatile signed __int32 *)(v5 + 128), 1u);
    *((_DWORD *)this + 54) = 1;
    goto LABEL_58;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    LODWORD(v46) = v27;
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\logon_user_context.cxx",
      343,
      "LOGON_USER_CONTEXT::ProcessUserLogon",
      "Basic logon attempt failed with 0x%x.\r\n",
      v46);
  }
LABEL_77:
  v43 = _InterlockedDecrement((volatile signed __int32 *)v7);
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v43);
  if ( !v43 && v7 )
  {
    FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v7);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v7);
  }
  if ( v4 < 0 && !*((_DWORD *)this + 126) )
  {
    *((_DWORD *)this + 126) = 41;
    *((_QWORD *)this + 64) = L"An error occurred during the authentication process.";
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001ccec  mov     [rsp-8+arg_10], rbx
0x18001ccf1  push    rbp
0x18001ccf2  push    rsi
0x18001ccf3  push    rdi
0x18001ccf4  push    r12
0x18001ccf6  push    r13
0x18001ccf8  push    r14
0x18001ccfa  push    r15
0x18001ccfc  lea     rbp, [rsp-27h]
0x18001cd01  sub     rsp, 90h
0x18001cd08  mov     rax, cs:__security_cookie
0x18001cd0f  xor     rax, rsp
0x18001cd12  mov     [rbp+57h+var_40], rax
0x18001cd16  mov     r13, rdx
0x18001cd19  mov     rdi, rcx
0x18001cd1c  xor     ebx, ebx
0x18001cd1e  mov     rax, [rcx+8]
0x18001cd22  mov     rsi, [rax+10h]
0x18001cd26  lea     r15, [rsi+0D0h]
0x18001cd2d  mov     rcx, r15
0x18001cd30  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18001cd36  mov     r8, [rsi+0C0h]
0x18001cd3d  lea     eax, [rbx+1]
0x18001cd40  mov     edx, eax
0x18001cd42  lock xadd [r8], edx
0x18001cd47  add     edx, eax
0x18001cd49  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18001cd50  test    rcx, rcx
0x18001cd53  jz      short loc_18001CD5B
0x18001cd55  call    cs:__imp_WriteRefTraceLog
0x18001cd5b  mov     r14, [rsi+0C0h]
0x18001cd62  mov     rcx, r15
0x18001cd65  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18001cd6b  mov     r15, [rdi+38h]
0x18001cd6f  mov     r12, [rdi+70h]
0x18001cd73  mov     rdx, [rdi+0E0h]; void *
0x18001cd7a  mov     [r13+0], ebx
0x18001cd7e  mov     ecx, [rdi+1E0h]
0x18001cd84  sub     ecx, 64h ; 'd'
0x18001cd87  jz      short loc_18001CDA9
0x18001cd89  sub     ecx, 1
0x18001cd8c  jz      loc_18001D22A
0x18001cd92  sub     ecx, 1
0x18001cd95  jz      loc_18001D12B
0x18001cd9b  cmp     ecx, 1
0x18001cd9e  jz      loc_18001D160
0x18001cda4  jmp     loc_18001D253
0x18001cda9  cmp     [rdi+0D8h], ebx
0x18001cdaf  jnz     loc_18001CEC1
0x18001cdb5  cmp     [r14+100h], ebx
0x18001cdbc  jz      loc_18001CEC1
0x18001cdc2  test    rdx, rdx
0x18001cdc5  jz      loc_18001CEC1
0x18001cdcb  mov     rcx, rdi; this
0x18001cdce  call    ?HandleClientCertAuthLogon@LOGON_USER_CONTEXT@@AEAAJPEAX@Z; LOGON_USER_CONTEXT::HandleClientCertAuthLogon(void *)
0x18001cdd3  mov     ebx, eax
0x18001cdd5  cmp     eax, 8007052Eh
0x18001cdda  jnz     short loc_18001CE1F
0x18001cddc  test    byte ptr cs:g_dwDebugFlags, 3
0x18001cde3  jz      loc_18001CEC1
0x18001cde9  mov     dword ptr [rsp+0C0h+var_98], eax
0x18001cded  lea     rax, aWarningClientC; "Warning: Client Cert logon attempt fail"...
0x18001cdf4  mov     [rsp+0C0h+var_A0], rax
0x18001cdf9  lea     r9, aLogonUserConte_3; "LOGON_USER_CONTEXT::ProcessUserLogon"
0x18001ce00  mov     r8d, 0FAh
0x18001ce06  lea     rdx, aInetsrvIisIisr_4; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001ce0d  mov     rcx, cs:g_pDebug
0x18001ce14  call    cs:__imp_PuDbgPrint
0x18001ce1a  jmp     loc_18001CEC1
0x18001ce1f  test    eax, eax
0x18001ce21  jns     short loc_18001CE66
0x18001ce23  test    byte ptr cs:g_dwDebugFlags, 3
0x18001ce2a  jz      loc_18001D253
0x18001ce30  mov     dword ptr [rsp+0C0h+var_98], eax
0x18001ce34  lea     rax, aClientCertLogo; "Client cert logon attempt failed with 0"...
0x18001ce3b  mov     r8d, 102h
0x18001ce41  lea     r9, aLogonUserConte_3; "LOGON_USER_CONTEXT::ProcessUserLogon"
0x18001ce48  mov     [rsp+0C0h+var_A0], rax
0x18001ce4d  lea     rdx, aInetsrvIisIisr_4; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001ce54  mov     rcx, cs:g_pDebug
0x18001ce5b  call    cs:__imp_PuDbgPrint
0x18001ce61  jmp     loc_18001D253
0x18001ce66  mov     r8d, 1
0x18001ce6c  mov     ecx, r8d
0x18001ce6f  lock xadd [rsi+78h], ecx
0x18001ce74  add     ecx, r8d
0x18001ce77  mov     rax, cs:?sm_pPerfCtrsGlobal@FTP_SITE_PERF_CTRS@@0PEAV1@EA; FTP_SITE_PERF_CTRS * FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal
0x18001ce7e  mov     edx, r8d
0x18001ce81  lock xadd [rax+30h], edx
0x18001ce86  add     edx, r8d
0x18001ce89  jmp     short loc_18001CE93
0x18001ce8b  lock cmpxchg [rsi+88h], ecx
0x18001ce93  mov     eax, [rsi+88h]
0x18001ce99  cmp     eax, ecx
0x18001ce9b  jb      short loc_18001CE8B
0x18001ce9d  mov     rcx, cs:?sm_pPerfCtrsGlobal@FTP_SITE_PERF_CTRS@@0PEAV1@EA; FTP_SITE_PERF_CTRS * FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal
0x18001cea4  jmp     short loc_18001CEAB
0x18001cea6  lock cmpxchg [rcx+40h], edx
0x18001ceab  mov     eax, [rcx+40h]
0x18001ceae  cmp     eax, edx
0x18001ceb0  jb      short loc_18001CEA6
0x18001ceb2  lock add [rsi+80h], r8d
0x18001ceba  mov     [rdi+0D8h], r8d
0x18001cec1  cmp     dword ptr [rdi+0D8h], 0
0x18001cec8  jnz     loc_18001D160
0x18001cece  lea     rdx, aAnonymous; "Anonymous"
0x18001ced5  mov     rcx, r15; String1
0x18001ced8  call    cs:__imp__wcsicmp
0x18001cede  test    eax, eax
0x18001cee0  jnz     loc_18001D030
0x18001cee6  lea     rdx, [r14+0B0h]; struct ANONYMOUS_AUTHENTICATION_CONFIG_ELEMENT *
0x18001ceed  cmp     [rdx+8], eax
0x18001cef0  jnz     loc_18001CFA7
0x18001cef6  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001cefd  mov     rax, [rcx]
0x18001cf00  mov     rax, [rax+20h]
0x18001cf04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf09  cmp     dword ptr [rax+8], 0
0x18001cf0d  jz      short loc_18001CF8C
0x18001cf0f  test    byte ptr [rax+28h], 8
0x18001cf13  jz      short loc_18001CF8C
0x18001cf15  cmp     dword ptr [rax+2Ch], 2
0x18001cf19  jb      short loc_18001CF8C
0x18001cf1b  mov     rbx, [rdi+8]
0x18001cf1f  add     rbx, 4F8h
0x18001cf26  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001cf2d  mov     rax, [rcx]
0x18001cf30  mov     rax, [rax+20h]
0x18001cf34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf39  xorps   xmm0, xmm0
0x18001cf3c  movups  [rbp+57h+var_7E], xmm0
0x18001cf40  movups  [rbp+57h+var_6E], xmm0
0x18001cf44  movups  xmmword ptr [rbp+57h+var_5E], xmm0
0x18001cf48  movups  xmmword ptr [rbp+57h+var_5E+0Eh], xmm0
0x18001cf4c  mov     dword ptr [rbp+57h+var_5E+0Ah], 1A0000h
0x18001cf53  mov     ecx, 40h ; '@'
0x18001cf58  mov     [rbp+57h+var_80], cx
0x18001cf5c  mov     ecx, 1
0x18001cf61  mov     word ptr [rbp+57h+var_7E+4], cx
0x18001cf65  mov     byte ptr [rbp+57h+var_7E+2], 0Ch
0x18001cf69  lea     rcx, ?AreaGuid@?1??GetAreaGuid@FtpAuthenticationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `FtpAuthenticationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18001cf70  mov     qword ptr [rbp+57h+var_6E+6], rcx
0x18001cf74  mov     qword ptr [rbp+57h+var_5E+0Eh], rbx
0x18001cf78  mov     [rbp+57h+var_48], 10h
0x18001cf7f  lea     rdx, [rbp+57h+var_80]
0x18001cf83  mov     rcx, rax
0x18001cf86  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x18001cf8c  mov     dword ptr [rdi+1F8h], 2Ah ; '*'
0x18001cf96  lea     rax, aAnonymousAuthe_0; "Anonymous authentication is not allowed"...
0x18001cf9d  mov     ebx, 8007052Eh
0x18001cfa2  jmp     loc_18001D24C
0x18001cfa7  mov     rcx, rdi; this
0x18001cfaa  call    ?HandleAnonymousLogon@LOGON_USER_CONTEXT@@AEAAJPEAVANONYMOUS_AUTHENTICATION_CONFIG_ELEMENT@@@Z; LOGON_USER_CONTEXT::HandleAnonymousLogon(ANONYMOUS_AUTHENTICATION_CONFIG_ELEMENT *)
0x18001cfaf  mov     ebx, eax
0x18001cfb1  test    eax, eax
0x18001cfb3  jns     short loc_18001CFD8
0x18001cfb5  test    byte ptr cs:g_dwDebugFlags, 3
0x18001cfbc  jz      loc_18001D253
0x18001cfc2  mov     dword ptr [rsp+0C0h+var_98], eax
0x18001cfc6  lea     rax, aAnonymousLogon; "Anonymous logon attempt failed with 0x%"...
0x18001cfcd  mov     r8d, 12Fh
0x18001cfd3  jmp     loc_18001CE41
0x18001cfd8  mov     r8d, 1
0x18001cfde  mov     ecx, r8d
0x18001cfe1  lock xadd [rsi+74h], ecx
0x18001cfe6  add     ecx, r8d
0x18001cfe9  mov     rax, cs:?sm_pPerfCtrsGlobal@FTP_SITE_PERF_CTRS@@0PEAV1@EA; FTP_SITE_PERF_CTRS * FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal
0x18001cff0  mov     edx, r8d
0x18001cff3  lock xadd [rax+2Ch], edx
0x18001cff8  add     edx, r8d
0x18001cffb  lock add [rsi+7Ch], r8d
0x18001d000  jmp     short loc_18001D00A
0x18001d002  lock cmpxchg [rsi+84h], ecx
0x18001d00a  mov     eax, [rsi+84h]
0x18001d010  cmp     eax, ecx
0x18001d012  jb      short loc_18001D002
0x18001d014  mov     rcx, cs:?sm_pPerfCtrsGlobal@FTP_SITE_PERF_CTRS@@0PEAV1@EA; FTP_SITE_PERF_CTRS * FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal
0x18001d01b  jmp     short loc_18001D022
0x18001d01d  lock cmpxchg [rcx+3Ch], edx
0x18001d022  mov     eax, [rcx+3Ch]
0x18001d025  cmp     eax, edx
0x18001d027  jb      short loc_18001D01D
0x18001d029  mov     [rdi+0D8h], r8d
0x18001d030  cmp     dword ptr [rdi+0D8h], 0
0x18001d037  jnz     loc_18001D160
0x18001d03d  lea     r9, [r14+0D8h]; struct BASIC_AUTHENTICATION_CONFIG_ELEMENT *
0x18001d044  cmp     dword ptr [r9+8], 0
0x18001d049  jz      loc_18001D12B
0x18001d04f  mov     r8, r12; unsigned __int16 *
0x18001d052  mov     rdx, r15; unsigned __int16 *
0x18001d055  mov     rcx, rdi; this
0x18001d058  call    ?HandleBasicLogon@LOGON_USER_CONTEXT@@AEAAJPEBG0PEAVBASIC_AUTHENTICATION_CONFIG_ELEMENT@@@Z; LOGON_USER_CONTEXT::HandleBasicLogon(ushort const *,ushort const *,BASIC_AUTHENTICATION_CONFIG_ELEMENT *)
0x18001d05d  mov     ebx, eax
0x18001d05f  cmp     eax, 8007052Eh
0x18001d064  jnz     short loc_18001D0A9
0x18001d066  test    byte ptr cs:g_dwDebugFlags, 3
0x18001d06d  jz      loc_18001D12B
0x18001d073  mov     dword ptr [rsp+0C0h+var_98], eax
0x18001d077  lea     rax, aWarningBasicLo; "Warning: Basic logon attempt failed wit"...
0x18001d07e  mov     [rsp+0C0h+var_A0], rax
0x18001d083  lea     r9, aLogonUserConte_3; "LOGON_USER_CONTEXT::ProcessUserLogon"
0x18001d08a  mov     r8d, 14Fh
0x18001d090  lea     rdx, aInetsrvIisIisr_4; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001d097  mov     rcx, cs:g_pDebug
0x18001d09e  call    cs:__imp_PuDbgPrint
0x18001d0a4  jmp     loc_18001D12B
0x18001d0a9  test    eax, eax
0x18001d0ab  jns     short loc_18001D0D0
0x18001d0ad  test    byte ptr cs:g_dwDebugFlags, 3
0x18001d0b4  jz      loc_18001D253
0x18001d0ba  mov     dword ptr [rsp+0C0h+var_98], eax
0x18001d0be  lea     rax, aBasicLogonAtte; "Basic logon attempt failed with 0x%x.\r"...
0x18001d0c5  mov     r8d, 157h
0x18001d0cb  jmp     loc_18001CE41
0x18001d0d0  mov     r8d, 1
0x18001d0d6  mov     ecx, r8d
0x18001d0d9  lock xadd [rsi+78h], ecx
0x18001d0de  add     ecx, r8d
0x18001d0e1  mov     rax, cs:?sm_pPerfCtrsGlobal@FTP_SITE_PERF_CTRS@@0PEAV1@EA; FTP_SITE_PERF_CTRS * FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal
0x18001d0e8  mov     edx, r8d
0x18001d0eb  lock xadd [rax+30h], edx
0x18001d0f0  add     edx, r8d
0x18001d0f3  jmp     short loc_18001D0FD
0x18001d0f5  lock cmpxchg [rsi+88h], ecx
0x18001d0fd  mov     eax, [rsi+88h]
0x18001d103  cmp     eax, ecx
0x18001d105  jb      short loc_18001D0F5
0x18001d107  mov     rcx, cs:?sm_pPerfCtrsGlobal@FTP_SITE_PERF_CTRS@@0PEAV1@EA; FTP_SITE_PERF_CTRS * FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal
0x18001d10e  jmp     short loc_18001D115
0x18001d110  lock cmpxchg [rcx+40h], edx
0x18001d115  mov     eax, [rcx+40h]
0x18001d118  cmp     eax, edx
0x18001d11a  jb      short loc_18001D110
0x18001d11c  lock add [rsi+80h], r8d
0x18001d124  mov     [rdi+0D8h], r8d
0x18001d12b  cmp     dword ptr [rdi+0D8h], 0
0x18001d132  jnz     short loc_18001D160
0x18001d134  mov     r8, r13; int *
0x18001d137  mov     edx, ebx; int
0x18001d139  mov     rcx, rdi; this
0x18001d13c  call    ?ProcessCustomAuthentication@LOGON_USER_CONTEXT@@AEAAJJPEAH@Z; LOGON_USER_CONTEXT::ProcessCustomAuthentication(long,int *)
0x18001d141  mov     ebx, eax
0x18001d143  test    eax, eax
0x18001d145  js      loc_18001D253
0x18001d14b  cmp     dword ptr [r13+0], 0
0x18001d150  jnz     loc_18001D253
0x18001d156  mov     dword ptr [rdi+1E0h], 67h ; 'g'
0x18001d160  cmp     dword ptr [rdi+1E0h], 67h ; 'g'
0x18001d167  jnz     loc_18001D22A
0x18001d16d  mov     rdx, [rdi+8]; struct USER_SESSION *
0x18001d171  lea     rcx, [rdx+18h]; this
0x18001d175  mov     r15d, 1
0x18001d17b  mov     [rsp+0C0h+var_90], r15d; int
0x18001d180  lea     rax, aCustomauth; "CustomAuth"
0x18001d187  mov     [rsp+0C0h+var_98], rax; unsigned __int16 *
0x18001d18c  mov     r9, [rdi+38h]; unsigned __int16 *
0x18001d190  xor     r8d, r8d; struct TOKEN_CACHE_ENTRY *
0x18001d193  call    ?Initialize@FTP_USER@@QEAAJPEAVUSER_SESSION@@PEAVTOKEN_CACHE_ENTRY@@PEBG22H@Z; FTP_USER::Initialize(USER_SESSION *,TOKEN_CACHE_ENTRY *,ushort const *,ushort const *,ushort const *,int)
0x18001d198  mov     ebx, eax
0x18001d19a  test    eax, eax
0x18001d19c  jns     short loc_18001D1C1
0x18001d19e  test    byte ptr cs:g_dwDebugFlags, 3
0x18001d1a5  jz      loc_18001D253
0x18001d1ab  mov     dword ptr [rsp+0C0h+var_98], eax
0x18001d1af  lea     rax, aCustomAuthenti; "Custom authentication user context init"...
0x18001d1b6  mov     r8d, 1A9h
0x18001d1bc  jmp     loc_18001CE41
0x18001d1c1  mov     edx, r15d
0x18001d1c4  lock xadd [rsi+78h], edx
0x18001d1c9  add     edx, r15d
0x18001d1cc  mov     rax, cs:?sm_pPerfCtrsGlobal@FTP_SITE_PERF_CTRS@@0PEAV1@EA; FTP_SITE_PERF_CTRS * FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal
0x18001d1d3  mov     ecx, r15d
0x18001d1d6  lock xadd [rax+30h], ecx
0x18001d1db  add     ecx, r15d
0x18001d1de  jmp     short loc_18001D1E8
0x18001d1e0  lock cmpxchg [rsi+88h], edx
0x18001d1e8  mov     eax, [rsi+88h]
0x18001d1ee  cmp     eax, edx
0x18001d1f0  jb      short loc_18001D1E0
0x18001d1f2  mov     rdx, cs:?sm_pPerfCtrsGlobal@FTP_SITE_PERF_CTRS@@0PEAV1@EA; FTP_SITE_PERF_CTRS * FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal
0x18001d1f9  jmp     short loc_18001D200
0x18001d1fb  lock cmpxchg [rdx+40h], ecx
0x18001d200  mov     eax, [rdx+40h]
0x18001d203  cmp     eax, ecx
0x18001d205  jb      short loc_18001D1FB
0x18001d207  lock add [rsi+80h], r15d
0x18001d20f  mov     eax, [rdi+80h]
0x18001d215  add     eax, eax
0x18001d217  mov     ecx, eax
0x18001d219  mov     rax, [rdi+70h]
0x18001d21d  jz      short loc_18001D22A
0x18001d21f  mov     byte ptr [rax], 0
0x18001d222  add     rax, r15
0x18001d225  sub     rcx, r15
0x18001d228  jnz     short loc_18001D21F
0x18001d22a  mov     rdx, r13; int *
0x18001d22d  mov     rcx, rdi; this
0x18001d230  call    ?LookupHomeDirectory@LOGON_USER_CONTEXT@@AEAAJPEAH@Z; LOGON_USER_CONTEXT::LookupHomeDirectory(int *)
0x18001d235  mov     ebx, eax
0x18001d237  test    eax, eax
  ... truncated ...
```
