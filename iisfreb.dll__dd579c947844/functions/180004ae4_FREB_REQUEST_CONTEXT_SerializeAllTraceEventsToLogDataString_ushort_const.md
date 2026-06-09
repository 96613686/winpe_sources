# FREB_REQUEST_CONTEXT::SerializeAllTraceEventsToLogDataString(ushort const *)

- ea: `0x180004ae4`
- end: `0x180005207`
- name: `?SerializeAllTraceEventsToLogDataString@FREB_REQUEST_CONTEXT@@AEAAJPEBG@Z`
- size: `1827`
- prototype: `__int64 __fastcall(FREB_REQUEST_CONTEXT *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005588`

## callees

- `0x180004ae4`
- `0x18000927c`
- `0x1800092e0`
- `0x180009360`
- `0x180009458`
- `0x1800095dc`
- `0x180009948`
- `0x18000ac52`
- `0x18000ac90`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180004ba2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180004ba2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004be6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004c04`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004be6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004c04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ed3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d60`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180004f12`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180004f12`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180004ea8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180004ea8`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180004bb2`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180004bb2`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180004eea`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180004eea`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800051d8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800051d8`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004b52`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004b52`
- `SspiCli!GetUserNameExW` at `0x180004ec9`
- `SspiCli!GetUserNameExW` at `0x180004f02`
- `SspiCli!GetUserNameExW` at `0x180004ec9`
- `SspiCli!GetUserNameExW` at `0x180004f02`

## string_xrefs

- `0x180004c65`: `<?xml version="1.0" encoding="UTF-8" ?>\n<?xml-stylesheet type='text/xsl' href='freb.xsl'?>\n`
- `0x180004d51`: `               processId="`
- `0x180004f1b`: `               tokenUserName="`
- `0x180005178`: `               xmlns:freb="http://schemas.microsoft.com/win/2006/06/iis/freb"\n`

## pseudocode

```c
__int64 __fastcall FREB_REQUEST_CONTEXT::SerializeAllTraceEventsToLogDataString(
        FREB_REQUEST_CONTEXT *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // rax
  __int64 v5; // r12
  unsigned int v6; // ecx
  int v7; // eax
  signed int LastError; // eax
  signed int v9; // ebx
  struct TRACE_EVENTS_LIST_ENTRY **v10; // r15
  unsigned int v11; // r14d
  _DWORD *v12; // rbx
  int v13; // ebx
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned int v16; // r8d
  unsigned int v17; // eax
  unsigned int v18; // r8d
  const unsigned __int16 *v19; // rax
  DWORD CurrentProcessId; // eax
  unsigned int v21; // r8d
  const char *v22; // rax
  int UserName; // ebx
  __int64 (__fastcall ***v24)(_QWORD); // rax
  const unsigned __int16 *v25; // rax
  unsigned int v26; // r8d
  __int64 v27; // rax
  const unsigned __int16 *v28; // rax
  unsigned int v29; // r8d
  __int64 v30; // rax
  void *v31; // rax
  unsigned int v32; // r8d
  FREB_XML_SERIALIZER *v33; // rcx
  __int64 v34; // rax
  unsigned int v35; // r8d
  __int64 v36; // rax
  __int64 v37; // rax
  const unsigned __int16 *v38; // rax
  const char *v39; // rdx
  __int64 v40; // rax
  const struct _GUID *v41; // rax
  unsigned int v42; // r8d
  unsigned int v43; // r8d
  unsigned int v44; // r8d
  unsigned int v45; // r8d
  unsigned int v46; // r8d
  unsigned int v47; // r8d
  struct TRACE_EVENTS_LIST_ENTRY *i; // r14
  FREB_XML_SERIALIZER *v49; // rcx
  _WORD v51[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v52; // [rsp+64h] [rbp-9Ch] BYREF
  struct _FILETIME FileTime; // [rsp+68h] [rbp-98h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v55[32]; // [rsp+80h] [rbp-80h] BYREF
  LPWSTR lpNameBuffer; // [rsp+A0h] [rbp-60h]
  unsigned int v57; // [rsp+A8h] [rbp-58h]
  unsigned __int16 v58[64]; // [rsp+C0h] [rbp-40h] BYREF

  v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 24LL))(*((_QWORD *)this + 6));
  v52 = 0;
  v51[0] = 0;
  v5 = v4;
  memset_0(v58, 0, sizeof(v58));
  STRU::STRU((STRU *)v55, v58, 0x40u);
  v6 = *((_DWORD *)this + 59);
  if ( v6 <= 0x2000000 )
  {
    v7 = 0x40000;
    if ( v6 > 0x800000 )
      v7 = 0x200000;
    *((_DWORD *)this + 43) = v7;
  }
  else
  {
    *((_DWORD *)this + 43) = 0x800000;
  }
  FileTime = 0;
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    *((struct _FILETIME *)this + 24) = FileTime;
    *((_DWORD *)this + 46) = GetTickCount();
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 < 0 )
      goto LABEL_40;
  }
  v10 = (struct TRACE_EVENTS_LIST_ENTRY **)((char *)this + 96);
  v11 = 0;
  v12 = (_DWORD *)*((_QWORD *)this + 12);
  if ( v12 != (_DWORD *)((char *)this + 96) )
  {
    v13 = v12[26];
    v11 = GetTickCount() - v13;
  }
  v14 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 32LL))(*((_QWORD *)this + 6));
  (*(void (__fastcall **)(__int64, unsigned __int16 *, _WORD *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v14 + 184LL))(
    v14,
    &v52,
    v51,
    0,
    0,
    0,
    0,
    0,
    0,
    0);
  FREB_XML_SERIALIZER::AddString(
    (FREB_REQUEST_CONTEXT *)((char *)this + 152),
    "<?xml version=\"1.0\" encoding=\"UTF-8\" ?>\r\n<?xml-stylesheet type='text/xsl' href='freb.xsl'?>\r\n",
    0);
  FREB_XML_SERIALIZER::AddString(
    (FREB_REQUEST_CONTEXT *)((char *)this + 152),
    "<!-- saved from url=(0014)about:internet -->\r\n",
    0);
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "<failedRequest url=\"", 0);
  v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  FREB_XML_SERIALIZER::AddStringXmlEscaped(
    (FREB_REQUEST_CONTEXT *)((char *)this + 152),
    *(const unsigned __int16 **)(v15 + 72),
    v16);
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "\"\r\n", 0);
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "               siteId=\"", 0);
  v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 176LL))(v5);
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), v17, v18, "%u");
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "\"\r\n", 0);
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "               appPoolId=\"", 0);
  v19 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 8LL))(g_pGlobalInfo);
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), v19, 0);
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "\"\r\n", 0);
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "               processId=\"", 0);
  CurrentProcessId = GetCurrentProcessId();
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), CurrentProcessId, v21, "%u");
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "\"\r\n", 0);
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "               verb=\"", 0);
  v22 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 64LL))(v5);
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), v22, 0);
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "\"\r\n", 0);
  if ( (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 48LL))(*((_QWORD *)this + 6)) )
  {
    UserName = 0;
    FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "               remoteUserName=\"", 0);
    v24 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 48LL))(*((_QWORD *)this + 6));
    v25 = (const unsigned __int16 *)(**v24)(v24);
    FREB_XML_SERIALIZER::AddStringXmlEscaped((FREB_REQUEST_CONTEXT *)((char *)this + 152), v25, v26);
    FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "\"\r\n", 0);
    FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "               userName=\"", 0);
    v27 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 48LL))(*((_QWORD *)this + 6));
    v28 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
    FREB_XML_SERIALIZER::AddStringXmlEscaped((FREB_REQUEST_CONTEXT *)((char *)this + 152), v28, v29);
    FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "\"\r\n", 0);
    v30 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 48LL))(*((_QWORD *)this + 6));
    v31 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 32LL))(v30);
    if ( ImpersonateLoggedOnUser(v31) )
    {
      FileTime.dwLowDateTime = v57 >> 1;
      if ( GetUserNameExW(NameSamCompatible, lpNameBuffer, (PULONG)&FileTime) )
      {
        UserName = 1;
      }
      else if ( GetLastError() == 234 && (int)STRU::Resize((STRU *)v55, 2 * FileTime.dwLowDateTime) >= 0 )
      {
        UserName = GetUserNameExW(NameSamCompatible, lpNameBuffer, (PULONG)&FileTime);
      }
      RevertToSelf();
    }
    FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "               tokenUserName=\"", 0);
    v33 = (FREB_REQUEST_CONTEXT *)((char *)this + 152);
    if ( UserName )
      FREB_XML_SERIALIZER::AddStringXmlEscaped(v33, lpNameBuffer, v32);
    else
      FREB_XML_SERIALIZER::AddString(v33, "NOT_AVAILABLE", 0);
    FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "\"\r\n", 0);
    FREB_XML_SERIALIZER::AddString(
      (FREB_REQUEST_CONTEXT *)((char *)this + 152),
      "               authenticationType=\"",
      0);
    v34 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 48LL))(*((_QWORD *)this + 6));
    if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34)
      && (v36 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 48LL))(*((_QWORD *)this + 6)),
          *(_WORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36)) )
    {
      v37 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 48LL))(*((_QWORD *)this + 6));
      v38 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
    else
    {
      v38 = L"anonymous";
    }
    FREB_XML_SERIALIZER::AddStringXmlEscaped((FREB_REQUEST_CONTEXT *)((char *)this + 152), v38, v35);
    v39 = "\"\r\n";
  }
  else
  {
    v39 = "               authenticationType=\"NOT_AVAILABLE\"";
  }
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), v39, 0);
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "               activityId=\"", 0);
  v40 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 272LL))(*((_QWORD *)this + 6));
  v41 = (const struct _GUID *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 24LL))(v40);
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), v41);
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "\"\r\n", 0);
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "               failureReason=\"", 0);
  FREB_XML_SERIALIZER::AddStringXmlEscaped((FREB_REQUEST_CONTEXT *)((char *)this + 152), a2, v42);
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "\"\r\n", 0);
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "               statusCode=\"", 0);
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), v52, v43, "%u");
  if ( v51[0] )
  {
    FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), ".", 0);
    FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), v51[0], v44, "%u");
  }
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "\"\r\n", 0);
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "               triggerStatusCode=\"", 0);
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), *((_DWORD *)this + 55), v45, "%u");
  if ( *((_DWORD *)this + 56) )
  {
    FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), ".", 0);
    FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), *((_DWORD *)this + 56), v46, "%u");
  }
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "\"\r\n", 0);
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "               timeTaken=\"", 0);
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), v11, v47, "%u");
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "\"\r\n", 0);
  FREB_XML_SERIALIZER::AddString(
    (FREB_REQUEST_CONTEXT *)((char *)this + 152),
    "               xmlns:freb=\"http://schemas.microsoft.com/win/2006/06/iis/freb\"\r\n",
    0);
  FREB_XML_SERIALIZER::AddString((FREB_REQUEST_CONTEXT *)((char *)this + 152), "               >\r\n", 0);
  for ( i = *v10; ; i = *(struct TRACE_EVENTS_LIST_ENTRY **)i )
  {
    v49 = (FREB_REQUEST_CONTEXT *)((char *)this + 152);
    if ( i == (struct TRACE_EVENTS_LIST_ENTRY *)v10 )
      break;
    v9 = FREB_XML_SERIALIZER::SerializeTraceEvent(
           v49,
           i,
           (struct PROVIDER_DEFINITIONS_STORED_LIST *)(*((_QWORD *)this + 7) + 24LL));
    if ( v9 < 0 )
      goto LABEL_40;
  }
  FREB_XML_SERIALIZER::AddString(v49, "</failedRequest>", 0);
  v9 = *((_DWORD *)this + 45);
LABEL_40:
  STRU::~STRU((STRU *)v55);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180004ae4  mov     [rsp-8+arg_10], rbx
0x180004ae9  push    rbp
0x180004aea  push    rsi
0x180004aeb  push    rdi
0x180004aec  push    r12
0x180004aee  push    r13
0x180004af0  push    r14
0x180004af2  push    r15
0x180004af4  lea     rbp, [rsp-50h]
0x180004af9  sub     rsp, 150h
0x180004b00  mov     rax, cs:__security_cookie
0x180004b07  xor     rax, rsp
0x180004b0a  mov     [rbp+80h+var_40], rax
0x180004b0e  mov     rsi, rcx
0x180004b11  mov     r13, rdx
0x180004b14  mov     rcx, [rcx+30h]
0x180004b18  mov     rax, [rcx]
0x180004b1b  mov     rax, [rax+18h]
0x180004b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b24  xor     ecx, ecx
0x180004b26  xor     edx, edx; Val
0x180004b28  mov     [rsp+180h+var_11C], cx
0x180004b2d  mov     r8d, 80h; Size
0x180004b33  mov     [rsp+180h+var_120], cx
0x180004b38  mov     r12, rax
0x180004b3b  lea     rcx, [rbp+80h+var_C0]; void *
0x180004b3f  call    memset_0
0x180004b44  mov     r8d, 40h ; '@'
0x180004b4a  lea     rdx, [rbp+80h+var_C0]
0x180004b4e  lea     rcx, [rbp+80h+var_100]
0x180004b52  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180004b58  mov     ecx, [rsi+0ECh]
0x180004b5e  lea     rdi, [rsi+98h]
0x180004b65  cmp     ecx, 2000000h
0x180004b6b  jbe     short loc_180004B76
0x180004b6d  mov     dword ptr [rdi+14h], 800000h
0x180004b74  jmp     short loc_180004B8C
0x180004b76  cmp     ecx, 800000h
0x180004b7c  mov     eax, 40000h
0x180004b81  mov     edx, 200000h
0x180004b86  cmova   eax, edx
0x180004b89  mov     [rdi+14h], eax
0x180004b8c  xorps   xmm0, xmm0
0x180004b8f  mov     qword ptr [rsp+180h+FileTime.dwLowDateTime], 0
0x180004b98  lea     rcx, [rsp+180h+SystemTime]; lpSystemTime
0x180004b9d  movups  xmmword ptr [rsp+180h+SystemTime.wYear], xmm0
0x180004ba2  call    cs:__imp_GetSystemTime
0x180004ba8  lea     rdx, [rsp+180h+FileTime]; lpFileTime
0x180004bad  lea     rcx, [rsp+180h+SystemTime]; lpSystemTime
0x180004bb2  call    cs:__imp_SystemTimeToFileTime
0x180004bb8  test    eax, eax
0x180004bba  jnz     short loc_180004BDA
0x180004bbc  call    cs:__imp_GetLastError
0x180004bc2  mov     ebx, eax
0x180004bc4  test    eax, eax
0x180004bc6  jle     short loc_180004BD1
0x180004bc8  movzx   ebx, ax
0x180004bcb  or      ebx, 80070000h
0x180004bd1  test    ebx, ebx
0x180004bd3  jns     short loc_180004BF2
0x180004bd5  jmp     loc_1800051D4
0x180004bda  mov     rax, qword ptr [rsp+180h+FileTime.dwLowDateTime]
0x180004bdf  mov     [rsi+0C0h], rax
0x180004be6  call    cs:__imp_GetTickCount
0x180004bec  mov     [rsi+0B8h], eax
0x180004bf2  lea     r15, [rsi+60h]
0x180004bf6  xor     r14d, r14d
0x180004bf9  mov     rbx, [r15]
0x180004bfc  cmp     rbx, r15
0x180004bff  jz      short loc_180004C10
0x180004c01  mov     ebx, [rbx+68h]
0x180004c04  call    cs:__imp_GetTickCount
0x180004c0a  mov     r14d, eax
0x180004c0d  sub     r14d, ebx
0x180004c10  mov     rcx, [rsi+30h]
0x180004c14  mov     rax, [rcx]
0x180004c17  mov     rax, [rax+20h]
0x180004c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c20  mov     r10, rax
0x180004c23  lea     r8, [rsp+180h+var_120]
0x180004c28  xor     r9d, r9d
0x180004c2b  lea     rdx, [rsp+180h+var_11C]
0x180004c30  mov     rcx, [rax]
0x180004c33  mov     rax, [rcx+0B8h]
0x180004c3a  xor     ecx, ecx
0x180004c3c  mov     [rsp+180h+var_138], rcx
0x180004c41  mov     [rsp+180h+var_140], rcx
0x180004c46  mov     [rsp+180h+var_148], rcx
0x180004c4b  mov     [rsp+180h+var_150], rcx
0x180004c50  mov     [rsp+180h+var_158], rcx
0x180004c55  mov     [rsp+180h+var_160], rcx
0x180004c5a  mov     rcx, r10
0x180004c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c62  xor     r8d, r8d; unsigned int
0x180004c65  lea     rdx, Src; "<?xml version=\"1.0\" encoding=\"UTF-8"...
0x180004c6c  mov     rcx, rdi; this
0x180004c6f  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180004c74  xor     r8d, r8d; unsigned int
0x180004c77  lea     rdx, aSavedFromUrl00; "<!-- saved from url=(0014)about:interne"...
0x180004c7e  mov     rcx, rdi; this
0x180004c81  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180004c86  xor     r8d, r8d; unsigned int
0x180004c89  lea     rdx, aFailedrequestU; "<failedRequest url=\""
0x180004c90  mov     rcx, rdi; this
0x180004c93  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180004c98  mov     rax, [r12]
0x180004c9c  mov     rcx, r12
0x180004c9f  mov     rax, [rax+8]
0x180004ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ca8  mov     rcx, rdi; this
0x180004cab  mov     rdx, [rax+48h]; unsigned __int16 *
0x180004caf  call    ?AddStringXmlEscaped@FREB_XML_SERIALIZER@@QEAAXPEBGK@Z; FREB_XML_SERIALIZER::AddStringXmlEscaped(ushort const *,ulong)
0x180004cb4  lea     rbx, asc_18000D878; "\"\r\n"
0x180004cbb  xor     r8d, r8d; unsigned int
0x180004cbe  mov     rdx, rbx; Src
0x180004cc1  mov     rcx, rdi; this
0x180004cc4  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180004cc9  xor     r8d, r8d; unsigned int
0x180004ccc  lea     rdx, aSiteid; "               siteId=\""
0x180004cd3  mov     rcx, rdi; this
0x180004cd6  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180004cdb  mov     rax, [r12]
0x180004cdf  mov     rcx, r12
0x180004ce2  mov     rax, [rax+0B0h]
0x180004ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cee  lea     r9, aU; "%u"
0x180004cf5  mov     edx, eax; unsigned int
0x180004cf7  mov     rcx, rdi; this
0x180004cfa  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXKKPEBD@Z; FREB_XML_SERIALIZER::AddString(ulong,ulong,char const *)
0x180004cff  xor     r8d, r8d; unsigned int
0x180004d02  mov     rdx, rbx; Src
0x180004d05  mov     rcx, rdi; this
0x180004d08  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180004d0d  xor     r8d, r8d; unsigned int
0x180004d10  lea     rdx, aApppoolid; "               appPoolId=\""
0x180004d17  mov     rcx, rdi; this
0x180004d1a  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180004d1f  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180004d26  mov     rax, [rcx]
0x180004d29  mov     rax, [rax+8]
0x180004d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d32  mov     rdx, rax; unsigned __int16 *
0x180004d35  xor     r8d, r8d; unsigned int
0x180004d38  mov     rcx, rdi; this
0x180004d3b  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBGK@Z; FREB_XML_SERIALIZER::AddString(ushort const *,ulong)
0x180004d40  xor     r8d, r8d; unsigned int
0x180004d43  mov     rdx, rbx; Src
0x180004d46  mov     rcx, rdi; this
0x180004d49  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180004d4e  xor     r8d, r8d; unsigned int
0x180004d51  lea     rdx, aProcessid; "               processId=\""
0x180004d58  mov     rcx, rdi; this
0x180004d5b  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180004d60  call    cs:__imp_GetCurrentProcessId
0x180004d66  lea     r9, aU; "%u"
0x180004d6d  mov     edx, eax; unsigned int
0x180004d6f  mov     rcx, rdi; this
0x180004d72  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXKKPEBD@Z; FREB_XML_SERIALIZER::AddString(ulong,ulong,char const *)
0x180004d77  xor     r8d, r8d; unsigned int
0x180004d7a  mov     rdx, rbx; Src
0x180004d7d  mov     rcx, rdi; this
0x180004d80  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180004d85  xor     r8d, r8d; unsigned int
0x180004d88  lea     rdx, aVerb; "               verb=\""
0x180004d8f  mov     rcx, rdi; this
0x180004d92  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180004d97  mov     rax, [r12]
0x180004d9b  mov     rcx, r12
0x180004d9e  mov     rax, [rax+40h]
0x180004da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004da7  mov     rdx, rax; Src
0x180004daa  xor     r8d, r8d; unsigned int
0x180004dad  mov     rcx, rdi; this
0x180004db0  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180004db5  xor     r8d, r8d; unsigned int
0x180004db8  mov     rdx, rbx; Src
0x180004dbb  mov     rcx, rdi; this
0x180004dbe  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180004dc3  mov     rcx, [rsi+30h]
0x180004dc7  mov     rax, [rcx]
0x180004dca  mov     rax, [rax+30h]
0x180004dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dd3  xor     r12d, r12d
0x180004dd6  test    rax, rax
0x180004dd9  jz      loc_180004FFC
0x180004ddf  xor     r8d, r8d; unsigned int
0x180004de2  lea     rdx, aRemoteusername; "               remoteUserName=\""
0x180004de9  mov     rcx, rdi; this
0x180004dec  mov     ebx, r12d
0x180004def  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180004df4  mov     rcx, [rsi+30h]
0x180004df8  mov     rax, [rcx]
0x180004dfb  mov     rax, [rax+30h]
0x180004dff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e04  mov     rdx, rax
0x180004e07  mov     rcx, [rax]
0x180004e0a  mov     rax, [rcx]
0x180004e0d  mov     rcx, rdx
0x180004e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e15  mov     rdx, rax; unsigned __int16 *
0x180004e18  mov     rcx, rdi; this
0x180004e1b  call    ?AddStringXmlEscaped@FREB_XML_SERIALIZER@@QEAAXPEBGK@Z; FREB_XML_SERIALIZER::AddStringXmlEscaped(ushort const *,ulong)
0x180004e20  xor     r8d, r8d; unsigned int
0x180004e23  lea     rdx, asc_18000D878; "\"\r\n"
0x180004e2a  mov     rcx, rdi; this
0x180004e2d  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180004e32  xor     r8d, r8d; unsigned int
0x180004e35  lea     rdx, aUsername; "               userName=\""
0x180004e3c  mov     rcx, rdi; this
0x180004e3f  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180004e44  mov     rcx, [rsi+30h]
0x180004e48  mov     rax, [rcx]
0x180004e4b  mov     rax, [rax+30h]
0x180004e4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e54  mov     rdx, rax
0x180004e57  mov     rcx, [rax]
0x180004e5a  mov     rax, [rcx+8]
0x180004e5e  mov     rcx, rdx
0x180004e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e66  mov     rdx, rax; unsigned __int16 *
0x180004e69  mov     rcx, rdi; this
0x180004e6c  call    ?AddStringXmlEscaped@FREB_XML_SERIALIZER@@QEAAXPEBGK@Z; FREB_XML_SERIALIZER::AddStringXmlEscaped(ushort const *,ulong)
0x180004e71  xor     r8d, r8d; unsigned int
0x180004e74  lea     rdx, asc_18000D878; "\"\r\n"
0x180004e7b  mov     rcx, rdi; this
0x180004e7e  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180004e83  mov     rcx, [rsi+30h]
0x180004e87  mov     rax, [rcx]
0x180004e8a  mov     rax, [rax+30h]
0x180004e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e93  mov     rdx, rax
0x180004e96  mov     rcx, [rax]
0x180004e99  mov     rax, [rcx+20h]
0x180004e9d  mov     rcx, rdx
0x180004ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ea5  mov     rcx, rax; hToken
0x180004ea8  call    cs:__imp_ImpersonateLoggedOnUser
0x180004eae  test    eax, eax
0x180004eb0  jz      short loc_180004F18
0x180004eb2  mov     eax, [rbp+80h+var_D8]
0x180004eb5  lea     r8, [rsp+180h+FileTime]; nSize
0x180004eba  mov     rdx, [rbp+80h+lpNameBuffer]; lpNameBuffer
0x180004ebe  lea     ecx, [r12+2]; NameFormat
0x180004ec3  shr     eax, 1
0x180004ec5  mov     [rsp+180h+FileTime.dwLowDateTime], eax
0x180004ec9  call    cs:__imp_GetUserNameExW
0x180004ecf  test    al, al
0x180004ed1  jnz     short loc_180004F0D
0x180004ed3  call    cs:__imp_GetLastError
0x180004ed9  cmp     eax, 0EAh
0x180004ede  jnz     short loc_180004F12
0x180004ee0  mov     edx, [rsp+180h+FileTime.dwLowDateTime]
0x180004ee4  lea     rcx, [rbp+80h+var_100]
0x180004ee8  add     edx, edx
0x180004eea  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180004ef0  test    eax, eax
0x180004ef2  js      short loc_180004F12
0x180004ef4  mov     rdx, [rbp+80h+lpNameBuffer]; lpNameBuffer
0x180004ef8  lea     r8, [rsp+180h+FileTime]; nSize
0x180004efd  lea     ecx, [r12+2]; NameFormat
0x180004f02  call    cs:__imp_GetUserNameExW
0x180004f08  movzx   ebx, al
0x180004f0b  jmp     short loc_180004F12
0x180004f0d  mov     ebx, 1
0x180004f12  call    cs:__imp_RevertToSelf
0x180004f18  xor     r8d, r8d; unsigned int
0x180004f1b  lea     rdx, aTokenusername; "               tokenUserName=\""
0x180004f22  mov     rcx, rdi; this
0x180004f25  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180004f2a  mov     rcx, rdi; this
0x180004f2d  test    ebx, ebx
0x180004f2f  jz      short loc_180004F3C
0x180004f31  mov     rdx, [rbp+80h+lpNameBuffer]; unsigned __int16 *
0x180004f35  call    ?AddStringXmlEscaped@FREB_XML_SERIALIZER@@QEAAXPEBGK@Z; FREB_XML_SERIALIZER::AddStringXmlEscaped(ushort const *,ulong)
0x180004f3a  jmp     short loc_180004F4B
0x180004f3c  xor     r8d, r8d; unsigned int
0x180004f3f  lea     rdx, aNotAvailable; "NOT_AVAILABLE"
0x180004f46  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180004f4b  lea     rbx, asc_18000D878; "\"\r\n"
0x180004f52  xor     r8d, r8d; unsigned int
0x180004f55  mov     rdx, rbx; Src
0x180004f58  mov     rcx, rdi; this
0x180004f5b  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180004f60  xor     r8d, r8d; unsigned int
0x180004f63  lea     rdx, aAuthentication_0; "               authenticationType=\""
0x180004f6a  mov     rcx, rdi; this
0x180004f6d  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180004f72  mov     rcx, [rsi+30h]
0x180004f76  mov     rax, [rcx]
0x180004f79  mov     rax, [rax+30h]
0x180004f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f82  mov     rdx, rax
0x180004f85  mov     rcx, [rax]
0x180004f88  mov     rax, [rcx+10h]
0x180004f8c  mov     rcx, rdx
0x180004f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f94  test    rax, rax
0x180004f97  jz      short loc_180004FE5
0x180004f99  mov     rcx, [rsi+30h]
0x180004f9d  mov     rax, [rcx]
  ... truncated ...
```
