# FREB_XML_SERIALIZER::SerializeTraceEvent(TRACE_EVENTS_LIST_ENTRY *,PROVIDER_DEFINITIONS_STORED_LIST *)

- ea: `0x180009948`
- end: `0x18000a2ab`
- name: `?SerializeTraceEvent@FREB_XML_SERIALIZER@@QEAAJPEAVTRACE_EVENTS_LIST_ENTRY@@PEAVPROVIDER_DEFINITIONS_STORED_LIST@@@Z`
- size: `2403`
- prototype: `__int64 __fastcall(FREB_XML_SERIALIZER *__hidden this, struct TRACE_EVENTS_LIST_ENTRY *, struct PROVIDER_DEFINITIONS_STORED_LIST *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180004ae4`

## callees

- `0x180001728`
- `0x18000927c`
- `0x1800092e0`
- `0x180009360`
- `0x180009458`
- `0x1800094bc`
- `0x180009520`
- `0x1800095dc`
- `0x180009948`
- `0x18000ac5e`
- `0x18000ac90`
- `0x18000b010`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x180009a86`
- `msvcrt!_snprintf_s` at `0x180009a86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009d65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009d65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009d8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009d8a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180009a07`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180009a07`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a144`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a144`
- `iisutil!PuDbgPrint` at `0x1800099d3`
- `iisutil!PuDbgPrint` at `0x1800099d3`

## string_xrefs

- `0x1800099a7`: `FREB_XML_SERIALIZER::SerializeTraceEvent`
- `0x1800099b5`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_xml_serializer.cxx`
- `0x180009aa0`: `<Event xmlns="http://schemas.microsoft.com/win/2004/08/events/event">\n`
- `0x180009c74`: `  <TimeCreated SystemTime="`
- `0x180009d56`: `  <Execution ProcessID="`
- `0x180009d7b`: `" ThreadID="`
- `0x180009dae`: `  <Computer>`
- `0x180009dd2`: `</Computer>\n`
- `0x18000a21e`: ` <ExtendedTracingInfo xmlns="http://schemas.microsoft.com/win/2004/08/events/trace">\n`

## pseudocode

```c
signed int __fastcall FREB_XML_SERIALIZER::SerializeTraceEvent(
        FREB_XML_SERIALIZER *this,
        struct TRACE_EVENTS_LIST_ENTRY *a2,
        struct PROVIDER_DEFINITIONS_STORED_LIST *a3)
{
  signed int result; // eax
  unsigned int v7; // r10d
  const unsigned __int16 *v8; // rsi
  const unsigned __int16 *v9; // r12
  _QWORD *v10; // r9
  unsigned int v11; // r8d
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned int v14; // r8d
  unsigned int v15; // eax
  __int64 v16; // r9
  unsigned __int64 v17; // rcx
  unsigned int v18; // r8d
  unsigned int v19; // r8d
  unsigned int v20; // r8d
  unsigned int v21; // r8d
  __int64 v22; // rax
  const struct _GUID *v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  const struct _GUID *v26; // rax
  DWORD CurrentProcessId; // eax
  unsigned int v28; // r8d
  DWORD CurrentThreadId; // eax
  unsigned int v30; // r8d
  __int64 v31; // r15
  __int64 v32; // r14
  unsigned int v33; // r8d
  unsigned __int64 *v34; // r10
  int v35; // ecx
  __int64 v36; // rax
  const struct _GUID *v37; // rdx
  int v38; // ecx
  int v39; // ecx
  int v40; // ecx
  int v41; // ecx
  int v42; // ecx
  unsigned int v43; // edx
  const char *v44; // r9
  const char *v45; // rdx
  int v46; // ecx
  int v47; // ecx
  int v48; // ecx
  int v49; // ecx
  const char *v50; // r9
  __int64 v51; // r15
  __int64 v52; // r14
  DWORD v53; // eax
  unsigned int v54; // r8d
  FILETIME FileTime; // [rsp+60h] [rbp-A0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-98h] BYREF
  char Buffer[112]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR lpBuffer[304]; // [rsp+F0h] [rbp-10h] BYREF

  FileTime = 0;
  SystemTime = 0;
  if ( (g_dwDebugFlags & 3) != 0 && g_dwDebugFlags < 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_xml_serializer.cxx",
      263,
      "FREB_XML_SERIALIZER::SerializeTraceEvent",
      "Freb: add event to log file:%S\n",
      *((const wchar_t **)a2 + 6));
  result = *((_DWORD *)this + 7);
  if ( !result )
  {
    FileTime = (FILETIME)(*((_QWORD *)this + 5) - 10000LL * (unsigned int)(*((_DWORD *)this + 8) - *((_DWORD *)a2 + 26)));
    if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    if ( _snprintf_s(
           Buffer,
           0x64u,
           0xFFFFFFFFFFFFFFFFuLL,
           "%04.4d-%02.2d-%02.2dT%02.2d:%02.2d:%02.2d.%03.3dZ",
           SystemTime.wYear,
           SystemTime.wMonth,
           SystemTime.wDay,
           SystemTime.wHour,
           SystemTime.wMinute,
           SystemTime.wSecond,
           SystemTime.wMilliseconds) < 0 )
    {
      result = -2147024882;
      *((_DWORD *)this + 7) = -2147024882;
      return result;
    }
    FREB_XML_SERIALIZER::AddString(
      this,
      "<Event xmlns=\"http://schemas.microsoft.com/win/2004/08/events/event\">\r\n",
      0);
    FREB_XML_SERIALIZER::AddString(this, " <System>\r\n", 0);
    v7 = *((_DWORD *)a3 + 2);
    v8 = 0;
    v9 = 0;
    if ( v7 )
    {
      v10 = (_QWORD *)*((_QWORD *)a2 + 2);
      v11 = 0;
      v12 = *(_QWORD *)a3;
      while ( 1 )
      {
        v13 = 88LL * v11;
        if ( *v10 == *(_QWORD *)(v13 + v12 + 56) && v10[1] == *(_QWORD *)(v13 + v12 + 64) )
          break;
        if ( ++v11 >= v7 )
          goto LABEL_21;
      }
      v14 = *(_DWORD *)(v13 + v12 + 72);
      v8 = *(const unsigned __int16 **)(v13 + v12 + 32);
      if ( v14 )
      {
        v15 = 0;
        v16 = *(_QWORD *)(v13 + v12 + 80);
        while ( 1 )
        {
          v17 = (unsigned __int64)v15 << 6;
          if ( *((_DWORD *)a2 + 6) == *(_DWORD *)(v17 + v16 + 56) )
            break;
          if ( ++v15 >= v14 )
            goto LABEL_21;
        }
        v9 = *(const unsigned __int16 **)(v17 + v16 + 32);
      }
    }
LABEL_21:
    FREB_XML_SERIALIZER::AddString(this, "  <Provider Name=\"", 0);
    if ( v8 )
      FREB_XML_SERIALIZER::AddString(this, v8, 0);
    FREB_XML_SERIALIZER::AddString(this, "\" Guid=\"", 0);
    FREB_XML_SERIALIZER::AddString(this, *((const struct _GUID **)a2 + 2));
    FREB_XML_SERIALIZER::AddString(this, "\"/>\r\n", 0);
    FREB_XML_SERIALIZER::AddString(this, "  <EventID>0</EventID>\r\n", 0);
    FREB_XML_SERIALIZER::AddString(this, "  <Version>", 0);
    FREB_XML_SERIALIZER::AddString(this, *((_DWORD *)a2 + 14), v18, "%u");
    FREB_XML_SERIALIZER::AddString(this, "</Version>\r\n", 0);
    FREB_XML_SERIALIZER::AddString(this, "  <Level>", 0);
    FREB_XML_SERIALIZER::AddString(this, *((_DWORD *)a2 + 15), v19, "%u");
    FREB_XML_SERIALIZER::AddString(this, "</Level>\r\n", 0);
    FREB_XML_SERIALIZER::AddString(this, "  <Opcode>", 0);
    FREB_XML_SERIALIZER::AddString(this, *((_DWORD *)a2 + 10), v20, "%u");
    FREB_XML_SERIALIZER::AddString(this, "</Opcode>\r\n", 0);
    FREB_XML_SERIALIZER::AddString(this, "  <Keywords>", 0);
    FREB_XML_SERIALIZER::AddString(this, *((_DWORD *)a2 + 6), v21, "0x%x");
    FREB_XML_SERIALIZER::AddString(this, "</Keywords>\r\n", 0);
    FREB_XML_SERIALIZER::AddString(this, "  <TimeCreated SystemTime=\"", 0);
    FREB_XML_SERIALIZER::AddString(this, Buffer, 0);
    FREB_XML_SERIALIZER::AddString(this, "\"/>\r\n", 0);
    FREB_XML_SERIALIZER::AddString(this, "  <Correlation ActivityID=\"", 0);
    v22 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 272LL))(*(_QWORD *)this);
    v23 = (const struct _GUID *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 24LL))(v22);
    FREB_XML_SERIALIZER::AddString(this, v23);
    if ( (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 232LL))(*(_QWORD *)this) )
    {
      FREB_XML_SERIALIZER::AddString(this, "\" RelatedActivityID=\"", 0);
      v24 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 232LL))(*(_QWORD *)this);
      v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 272LL))(v24);
      v26 = (const struct _GUID *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 24LL))(v25);
      FREB_XML_SERIALIZER::AddString(this, v26);
    }
    FREB_XML_SERIALIZER::AddString(this, "\"/>\r\n", 0);
    FREB_XML_SERIALIZER::AddString(this, "  <Execution ProcessID=\"", 0);
    CurrentProcessId = GetCurrentProcessId();
    FREB_XML_SERIALIZER::AddString(this, CurrentProcessId, v28, "%u");
    FREB_XML_SERIALIZER::AddString(this, "\" ThreadID=\"", 0);
    CurrentThreadId = GetCurrentThreadId();
    FREB_XML_SERIALIZER::AddString(this, CurrentThreadId, v30, "%u");
    FREB_XML_SERIALIZER::AddString(this, "\"/>\r\n", 0);
    FREB_XML_SERIALIZER::AddString(this, "  <Computer>", 0);
    FREB_XML_SERIALIZER::AddString(this, FREB_XML_SERIALIZER::sm_pszComputerName, 0);
    FREB_XML_SERIALIZER::AddString(this, "</Computer>\r\n", 0);
    FREB_XML_SERIALIZER::AddString(this, " </System>\r\n", 0);
    FREB_XML_SERIALIZER::AddString(this, " <EventData>\r\n", 0);
    v31 = 0;
    if ( *((_DWORD *)a2 + 22) )
    {
      while ( 1 )
      {
        v32 = *((_QWORD *)a2 + 12);
        FREB_XML_SERIALIZER::AddString(this, "  <Data Name=\"", 0);
        FREB_XML_SERIALIZER::AddStringXmlEscaped(this, *(const unsigned __int16 **)(v32 + 40 * v31));
        FREB_XML_SERIALIZER::AddString(this, "\">", 0);
        v34 = *(unsigned __int64 **)(v32 + 40 * v31 + 16);
        v35 = *(_DWORD *)(v32 + 40 * v31 + 8);
        if ( !v34 )
          break;
        if ( v35 > 19 )
        {
          v46 = v35 - 20;
          if ( !v46 )
          {
            v50 = "%ld";
            goto LABEL_61;
          }
          v47 = v46 - 1;
          if ( !v47 )
          {
            v50 = "%lu";
LABEL_61:
            FREB_XML_SERIALIZER::AddString(this, *v34, v33, v50);
            goto LABEL_62;
          }
          v48 = v47 - 9;
          if ( !v48 )
          {
            FREB_XML_SERIALIZER::AddStringXmlEscaped(
              this,
              *(const char **)(v32 + 40 * v31 + 16),
              *(_DWORD *)(v32 + 40 * v31 + 24));
            goto LABEL_62;
          }
          v49 = v48 - 1;
          if ( !v49 )
          {
            FREB_XML_SERIALIZER::AddStringXmlEscaped(this, *(const unsigned __int16 **)(v32 + 40 * v31 + 16));
            goto LABEL_62;
          }
          if ( v49 == 41 )
          {
            v37 = *(const struct _GUID **)(v32 + 40 * v31 + 16);
LABEL_30:
            FREB_XML_SERIALIZER::AddString(this, v37);
          }
        }
        else
        {
          if ( v35 == 19 )
          {
            v44 = "%u";
            goto LABEL_46;
          }
          v38 = v35 - 2;
          if ( !v38 )
          {
            v43 = *(__int16 *)v34;
            goto LABEL_48;
          }
          v39 = v38 - 1;
          if ( !v39 )
          {
            v44 = "%d";
LABEL_46:
            v43 = *(_DWORD *)v34;
            goto LABEL_49;
          }
          v40 = v39 - 8;
          if ( !v40 )
          {
            v45 = "true";
            if ( !*(_DWORD *)v34 )
              v45 = "false";
            FREB_XML_SERIALIZER::AddString(this, v45, 0);
            goto LABEL_62;
          }
          v41 = v40 - 5;
          if ( !v41 )
          {
            v43 = *(char *)v34;
            v44 = "%d";
LABEL_49:
            FREB_XML_SERIALIZER::AddString(this, v43, v33, v44);
            goto LABEL_62;
          }
          v42 = v41 - 1;
          if ( !v42 )
          {
            v43 = *(unsigned __int8 *)v34;
            goto LABEL_48;
          }
          if ( v42 == 1 )
          {
            v43 = *(unsigned __int16 *)v34;
LABEL_48:
            v44 = "%u";
            goto LABEL_49;
          }
        }
LABEL_62:
        FREB_XML_SERIALIZER::AddString(this, "</Data>\r\n", 0);
        v31 = (unsigned int)(v31 + 1);
        if ( (unsigned int)v31 >= *((_DWORD *)a2 + 22) )
          goto LABEL_63;
      }
      if ( v35 != 72 || wcscmp_0(*(const wchar_t **)(v32 + 40 * v31), L"ContextId") )
        goto LABEL_62;
      v36 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 272LL))(*(_QWORD *)this);
      v37 = (const struct _GUID *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 24LL))(v36);
      goto LABEL_30;
    }
LABEL_63:
    FREB_XML_SERIALIZER::AddString(this, " </EventData>\r\n", 0);
    FREB_XML_SERIALIZER::AddString(this, " <RenderingInfo Culture=\"", 0);
    FREB_XML_SERIALIZER::AddString(this, FREB_XML_SERIALIZER::sm_pszSystemLocale, 0);
    FREB_XML_SERIALIZER::AddString(this, "\">\r\n", 0);
    FREB_XML_SERIALIZER::AddString(this, "  <Opcode>", 0);
    FREB_XML_SERIALIZER::AddStringXmlEscaped(this, *((const unsigned __int16 **)a2 + 6));
    FREB_XML_SERIALIZER::AddString(this, "</Opcode>\r\n", 0);
    if ( v9 )
    {
      FREB_XML_SERIALIZER::AddString(this, "  <Keywords>\r\n", 0);
      FREB_XML_SERIALIZER::AddString(this, "   <Keyword>", 0);
      FREB_XML_SERIALIZER::AddString(this, v9, 0);
      FREB_XML_SERIALIZER::AddString(this, "</Keyword>\r\n", 0);
      FREB_XML_SERIALIZER::AddString(this, "  </Keywords>\r\n", 0);
    }
    v51 = 0;
    if ( !*((_DWORD *)a2 + 22) )
    {
LABEL_77:
      FREB_XML_SERIALIZER::AddString(this, " </RenderingInfo>\r\n", 0);
      FREB_XML_SERIALIZER::AddString(
        this,
        " <ExtendedTracingInfo xmlns=\"http://schemas.microsoft.com/win/2004/08/events/trace\">\r\n",
        0);
      FREB_XML_SERIALIZER::AddString(this, "  <EventGuid>", 0);
      FREB_XML_SERIALIZER::AddString(this, *((const struct _GUID **)a2 + 4));
      FREB_XML_SERIALIZER::AddString(this, "</EventGuid>\r\n", 0);
      FREB_XML_SERIALIZER::AddString(this, " </ExtendedTracingInfo>\r\n", 0);
      FREB_XML_SERIALIZER::AddString(this, "</Event>\r\n", 0);
      return *((_DWORD *)this + 7);
    }
    while ( 1 )
    {
      v52 = *((_QWORD *)a2 + 12);
      if ( *(_QWORD *)(v52 + 40 * v51 + 32) )
      {
        FREB_XML_SERIALIZER::AddString(this, "  <freb:Description Data=\"", 0);
        FREB_XML_SERIALIZER::AddStringXmlEscaped(this, *(const unsigned __int16 **)(v52 + 40 * v51));
        FREB_XML_SERIALIZER::AddString(this, "\">", 0);
        FREB_XML_SERIALIZER::AddStringXmlEscaped(this, *(const unsigned __int16 **)(v52 + 40 * v51 + 32));
      }
      else
      {
        if ( *(_DWORD *)(v52 + 40 * v51 + 8) != 19 )
          goto LABEL_76;
        if ( wcscmp_0(*(const wchar_t **)(v52 + 40 * v51), L"ErrorCode") )
          goto LABEL_76;
        v53 = FormatMessageW(0x1200u, 0, **(_DWORD **)(v52 + 40 * v51 + 16), 0x400u, lpBuffer, 0x12Cu, 0);
        if ( !v53 )
          goto LABEL_76;
        if ( lpBuffer[v53 - 1] == 10 )
        {
          if ( 2 * (unsigned __int64)(v53 - 1) >= 0x258 )
            _report_rangecheckfailure();
          lpBuffer[v53 - 1] = 0;
        }
        FREB_XML_SERIALIZER::AddString(this, "  <freb:Description Data=\"", 0);
        FREB_XML_SERIALIZER::AddStringXmlEscaped(this, *(const unsigned __int16 **)(v52 + 40 * v51));
        FREB_XML_SERIALIZER::AddString(this, "\">", 0);
        FREB_XML_SERIALIZER::AddStringXmlEscaped(this, lpBuffer);
        FREB_XML_SERIALIZER::AddString(this, " (", 0);
        FREB_XML_SERIALIZER::AddString(this, **(_DWORD **)(v52 + 40 * v51 + 16), v54, "0x%x");
        FREB_XML_SERIALIZER::AddString(this, ")", 0);
      }
      FREB_XML_SERIALIZER::AddString(this, "</freb:Description>\r\n", 0);
LABEL_76:
      v51 = (unsigned int)(v51 + 1);
      if ( (unsigned int)v51 >= *((_DWORD *)a2 + 22) )
        goto LABEL_77;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009948  push    rbp
0x18000994a  push    rbx
0x18000994b  push    rsi
0x18000994c  push    rdi
0x18000994d  push    r12
0x18000994f  push    r14
0x180009951  push    r15
0x180009953  lea     rbp, [rsp-260h]
0x18000995b  sub     rsp, 360h
0x180009962  mov     rax, cs:__security_cookie
0x180009969  xor     rax, rsp
0x18000996c  mov     [rbp+290h+var_40], rax
0x180009973  mov     eax, cs:g_dwDebugFlags
0x180009979  mov     rbx, rcx
0x18000997c  test    al, 3
0x18000997e  mov     qword ptr [rsp+390h+FileTime.dwLowDateTime], 0
0x180009987  xorps   xmm0, xmm0
0x18000998a  mov     r14, r8
0x18000998d  setnz   cl
0x180009990  mov     rdi, rdx
0x180009993  bt      eax, 1Fh
0x180009997  movups  xmmword ptr [rsp+390h+SystemTime.wYear], xmm0
0x18000999c  setb    al
0x18000999f  test    al, cl
0x1800099a1  jz      short loc_1800099D9
0x1800099a3  mov     rax, [rdx+30h]
0x1800099a7  lea     r9, aFrebXmlSeriali; "FREB_XML_SERIALIZER::SerializeTraceEven"...
0x1800099ae  mov     rcx, cs:g_pDebug
0x1800099b5  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800099bc  mov     qword ptr [rsp+390h+nSize], rax
0x1800099c1  mov     r8d, 107h
0x1800099c7  lea     rax, aFrebAddEventTo; "Freb: add event to log file:%S\n"
0x1800099ce  mov     [rsp+390h+lpBuffer], rax
0x1800099d3  call    cs:__imp_PuDbgPrint
0x1800099d9  mov     eax, [rbx+1Ch]
0x1800099dc  test    eax, eax
0x1800099de  jnz     loc_18000A284
0x1800099e4  mov     eax, [rbx+20h]
0x1800099e7  lea     rdx, [rsp+390h+SystemTime]; lpSystemTime
0x1800099ec  sub     eax, [rdi+68h]
0x1800099ef  imul    rcx, rax, 2710h
0x1800099f6  mov     rax, [rbx+28h]
0x1800099fa  sub     rax, rcx
0x1800099fd  lea     rcx, [rsp+390h+FileTime]; lpFileTime
0x180009a02  mov     qword ptr [rsp+390h+FileTime.dwLowDateTime], rax
0x180009a07  call    cs:__imp_FileTimeToSystemTime
0x180009a0d  test    eax, eax
0x180009a0f  jnz     short loc_180009A2C
0x180009a11  call    cs:__imp_GetLastError
0x180009a17  test    eax, eax
0x180009a19  jle     loc_18000A284
0x180009a1f  movzx   eax, ax
0x180009a22  or      eax, 80070000h
0x180009a27  jmp     loc_18000A284
0x180009a2c  movzx   ecx, [rsp+390h+SystemTime.wSecond]
0x180009a31  movzx   edx, [rsp+390h+SystemTime.wMinute]
0x180009a36  movzx   r8d, [rsp+390h+SystemTime.wHour]
0x180009a3c  movzx   r9d, [rsp+390h+SystemTime.wDay]
0x180009a42  movzx   eax, [rsp+390h+SystemTime.wMilliseconds]
0x180009a47  movzx   r10d, [rsp+390h+SystemTime.wMonth]
0x180009a4d  movzx   r11d, [rsp+390h+SystemTime.wYear]
0x180009a53  mov     [rsp+390h+var_340], eax
0x180009a57  mov     [rsp+390h+var_348], ecx
0x180009a5b  lea     rcx, [rbp+290h+Buffer]; Buffer
0x180009a5f  mov     [rsp+390h+var_350], edx
0x180009a63  mov     [rsp+390h+var_358], r8d
0x180009a68  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180009a6c  mov     dword ptr [rsp+390h+Arguments], r9d
0x180009a71  lea     r9, Format; "%04.4d-%02.2d-%02.2dT%02.2d:%02.2d:%02."...
0x180009a78  mov     [rsp+390h+nSize], r10d
0x180009a7d  mov     dword ptr [rsp+390h+lpBuffer], r11d
0x180009a82  lea     edx, [r8+65h]; BufferCount
0x180009a86  call    cs:__imp__snprintf_s
0x180009a8c  test    eax, eax
0x180009a8e  jns     short loc_180009A9D
0x180009a90  mov     eax, 8007000Eh
0x180009a95  mov     [rbx+1Ch], eax
0x180009a98  jmp     loc_18000A284
0x180009a9d  xor     r8d, r8d; unsigned int
0x180009aa0  lea     rdx, aEventXmlnsHttp; "<Event xmlns=\"http://schemas.microsoft"...
0x180009aa7  mov     rcx, rbx; this
0x180009aaa  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009aaf  xor     r8d, r8d; unsigned int
0x180009ab2  lea     rdx, aSystem_0; " <System>\r\n"
0x180009ab9  mov     rcx, rbx; this
0x180009abc  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009ac1  mov     r10d, [r14+8]
0x180009ac5  xor     esi, esi
0x180009ac7  xor     r12d, r12d
0x180009aca  test    r10d, r10d
0x180009acd  jz      short loc_180009B34
0x180009acf  mov     r9, [rdi+10h]
0x180009ad3  xor     r8d, r8d
0x180009ad6  mov     rdx, [r14]
0x180009ad9  mov     eax, r8d
0x180009adc  imul    rcx, rax, 58h ; 'X'
0x180009ae0  mov     rax, [r9]
0x180009ae3  cmp     rax, [rcx+rdx+38h]
0x180009ae8  jnz     short loc_180009AF5
0x180009aea  mov     rax, [r9+8]
0x180009aee  cmp     rax, [rcx+rdx+40h]
0x180009af3  jz      short loc_180009AFF
0x180009af5  inc     r8d
0x180009af8  cmp     r8d, r10d
0x180009afb  jb      short loc_180009AD9
0x180009afd  jmp     short loc_180009B34
0x180009aff  mov     r8d, [rcx+rdx+48h]
0x180009b04  mov     rsi, [rcx+rdx+20h]
0x180009b09  test    r8d, r8d
0x180009b0c  jz      short loc_180009B34
0x180009b0e  mov     r10d, [rdi+18h]
0x180009b12  xor     eax, eax
0x180009b14  mov     r9, [rcx+rdx+50h]
0x180009b19  mov     ecx, eax
0x180009b1b  shl     rcx, 6
0x180009b1f  cmp     r10d, [rcx+r9+38h]
0x180009b24  jz      short loc_180009B2F
0x180009b26  inc     eax
0x180009b28  cmp     eax, r8d
0x180009b2b  jb      short loc_180009B19
0x180009b2d  jmp     short loc_180009B34
0x180009b2f  mov     r12, [rcx+r9+20h]
0x180009b34  xor     r8d, r8d; unsigned int
0x180009b37  lea     rdx, aProviderName; "  <Provider Name=\""
0x180009b3e  mov     rcx, rbx; this
0x180009b41  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009b46  test    rsi, rsi
0x180009b49  jz      short loc_180009B59
0x180009b4b  xor     r8d, r8d; unsigned int
0x180009b4e  mov     rdx, rsi; unsigned __int16 *
0x180009b51  mov     rcx, rbx; this
0x180009b54  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBGK@Z; FREB_XML_SERIALIZER::AddString(ushort const *,ulong)
0x180009b59  xor     r8d, r8d; unsigned int
0x180009b5c  lea     rdx, aGuid; "\" Guid=\""
0x180009b63  mov     rcx, rbx; this
0x180009b66  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009b6b  mov     rdx, [rdi+10h]; struct _GUID *
0x180009b6f  mov     rcx, rbx; this
0x180009b72  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBU_GUID@@@Z; FREB_XML_SERIALIZER::AddString(_GUID const *)
0x180009b77  lea     r14, asc_18000E9AC; "\"/>\r\n"
0x180009b7e  xor     r8d, r8d; unsigned int
0x180009b81  mov     rdx, r14; Src
0x180009b84  mov     rcx, rbx; this
0x180009b87  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009b8c  xor     r8d, r8d; unsigned int
0x180009b8f  lea     rdx, aEventid0Eventi; "  <EventID>0</EventID>\r\n"
0x180009b96  mov     rcx, rbx; this
0x180009b99  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009b9e  xor     r8d, r8d; unsigned int
0x180009ba1  lea     rdx, aVersion; "  <Version>"
0x180009ba8  mov     rcx, rbx; this
0x180009bab  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009bb0  mov     edx, [rdi+38h]; unsigned int
0x180009bb3  lea     rsi, aU; "%u"
0x180009bba  mov     r9, rsi; char *
0x180009bbd  mov     rcx, rbx; this
0x180009bc0  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXKKPEBD@Z; FREB_XML_SERIALIZER::AddString(ulong,ulong,char const *)
0x180009bc5  xor     r8d, r8d; unsigned int
0x180009bc8  lea     rdx, aVersion_0; "</Version>\r\n"
0x180009bcf  mov     rcx, rbx; this
0x180009bd2  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009bd7  xor     r8d, r8d; unsigned int
0x180009bda  lea     rdx, aLevel; "  <Level>"
0x180009be1  mov     rcx, rbx; this
0x180009be4  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009be9  mov     edx, [rdi+3Ch]; unsigned int
0x180009bec  mov     r9, rsi; char *
0x180009bef  mov     rcx, rbx; this
0x180009bf2  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXKKPEBD@Z; FREB_XML_SERIALIZER::AddString(ulong,ulong,char const *)
0x180009bf7  xor     r8d, r8d; unsigned int
0x180009bfa  lea     rdx, aLevel_0; "</Level>\r\n"
0x180009c01  mov     rcx, rbx; this
0x180009c04  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009c09  xor     r8d, r8d; unsigned int
0x180009c0c  lea     rdx, aOpcode_0; "  <Opcode>"
0x180009c13  mov     rcx, rbx; this
0x180009c16  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009c1b  mov     edx, [rdi+28h]; unsigned int
0x180009c1e  mov     r9, rsi; char *
0x180009c21  mov     rcx, rbx; this
0x180009c24  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXKKPEBD@Z; FREB_XML_SERIALIZER::AddString(ulong,ulong,char const *)
0x180009c29  xor     r8d, r8d; unsigned int
0x180009c2c  lea     rdx, aOpcode; "</Opcode>\r\n"
0x180009c33  mov     rcx, rbx; this
0x180009c36  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009c3b  xor     r8d, r8d; unsigned int
0x180009c3e  lea     rdx, aKeywords; "  <Keywords>"
0x180009c45  mov     rcx, rbx; this
0x180009c48  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009c4d  mov     edx, [rdi+18h]; unsigned int
0x180009c50  lea     r9, a0xX; "0x%x"
0x180009c57  mov     rcx, rbx; this
0x180009c5a  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXKKPEBD@Z; FREB_XML_SERIALIZER::AddString(ulong,ulong,char const *)
0x180009c5f  xor     r8d, r8d; unsigned int
0x180009c62  lea     rdx, aKeywords_0; "</Keywords>\r\n"
0x180009c69  mov     rcx, rbx; this
0x180009c6c  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009c71  xor     r8d, r8d; unsigned int
0x180009c74  lea     rdx, aTimecreatedSys; "  <TimeCreated SystemTime=\""
0x180009c7b  mov     rcx, rbx; this
0x180009c7e  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009c83  xor     r8d, r8d; unsigned int
0x180009c86  lea     rdx, [rbp+290h+Buffer]; Src
0x180009c8a  mov     rcx, rbx; this
0x180009c8d  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009c92  xor     r8d, r8d; unsigned int
0x180009c95  mov     rdx, r14; Src
0x180009c98  mov     rcx, rbx; this
0x180009c9b  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009ca0  xor     r8d, r8d; unsigned int
0x180009ca3  lea     rdx, aCorrelationAct; "  <Correlation ActivityID=\""
0x180009caa  mov     rcx, rbx; this
0x180009cad  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009cb2  mov     rcx, [rbx]
0x180009cb5  mov     rax, [rcx]
0x180009cb8  mov     rax, [rax+110h]
0x180009cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cc4  mov     rcx, rax
0x180009cc7  mov     rax, [rax]
0x180009cca  mov     rax, [rax+18h]
0x180009cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cd3  mov     rdx, rax; struct _GUID *
0x180009cd6  mov     rcx, rbx; this
0x180009cd9  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBU_GUID@@@Z; FREB_XML_SERIALIZER::AddString(_GUID const *)
0x180009cde  mov     rcx, [rbx]
0x180009ce1  mov     rax, [rcx]
0x180009ce4  mov     rax, [rax+0E8h]
0x180009ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cf0  test    rax, rax
0x180009cf3  jz      short loc_180009D45
0x180009cf5  xor     r8d, r8d; unsigned int
0x180009cf8  lea     rdx, aRelatedactivit; "\" RelatedActivityID=\""
0x180009cff  mov     rcx, rbx; this
0x180009d02  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009d07  mov     rcx, [rbx]
0x180009d0a  mov     rax, [rcx]
0x180009d0d  mov     rax, [rax+0E8h]
0x180009d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d19  mov     rcx, rax
0x180009d1c  mov     rax, [rax]
0x180009d1f  mov     rax, [rax+110h]
0x180009d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d2b  mov     rcx, rax
0x180009d2e  mov     rax, [rax]
0x180009d31  mov     rax, [rax+18h]
0x180009d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d3a  mov     rdx, rax; struct _GUID *
0x180009d3d  mov     rcx, rbx; this
0x180009d40  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBU_GUID@@@Z; FREB_XML_SERIALIZER::AddString(_GUID const *)
0x180009d45  xor     r8d, r8d; unsigned int
0x180009d48  mov     rdx, r14; Src
0x180009d4b  mov     rcx, rbx; this
0x180009d4e  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009d53  xor     r8d, r8d; unsigned int
0x180009d56  lea     rdx, aExecutionProce; "  <Execution ProcessID=\""
0x180009d5d  mov     rcx, rbx; this
0x180009d60  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009d65  call    cs:__imp_GetCurrentProcessId
0x180009d6b  mov     r9, rsi; char *
0x180009d6e  mov     rcx, rbx; this
0x180009d71  mov     edx, eax; unsigned int
0x180009d73  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXKKPEBD@Z; FREB_XML_SERIALIZER::AddString(ulong,ulong,char const *)
0x180009d78  xor     r8d, r8d; unsigned int
0x180009d7b  lea     rdx, aThreadid; "\" ThreadID=\""
0x180009d82  mov     rcx, rbx; this
0x180009d85  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009d8a  call    cs:__imp_GetCurrentThreadId
0x180009d90  mov     r9, rsi; char *
0x180009d93  mov     rcx, rbx; this
0x180009d96  mov     edx, eax; unsigned int
0x180009d98  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXKKPEBD@Z; FREB_XML_SERIALIZER::AddString(ulong,ulong,char const *)
0x180009d9d  xor     r8d, r8d; unsigned int
0x180009da0  mov     rdx, r14; Src
0x180009da3  mov     rcx, rbx; this
0x180009da6  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009dab  xor     r8d, r8d; unsigned int
0x180009dae  lea     rdx, aComputer; "  <Computer>"
0x180009db5  mov     rcx, rbx; this
0x180009db8  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009dbd  mov     rdx, cs:?sm_pszComputerName@FREB_XML_SERIALIZER@@0PEAGEA; unsigned __int16 *
0x180009dc4  xor     r8d, r8d; unsigned int
0x180009dc7  mov     rcx, rbx; this
0x180009dca  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBGK@Z; FREB_XML_SERIALIZER::AddString(ushort const *,ulong)
0x180009dcf  xor     r8d, r8d; unsigned int
0x180009dd2  lea     rdx, aComputer_0; "</Computer>\r\n"
0x180009dd9  mov     rcx, rbx; this
0x180009ddc  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009de1  xor     r8d, r8d; unsigned int
0x180009de4  lea     rdx, aSystem; " </System>\r\n"
0x180009deb  mov     rcx, rbx; this
0x180009dee  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009df3  xor     r8d, r8d; unsigned int
0x180009df6  lea     rdx, aEventdata_0; " <EventData>\r\n"
0x180009dfd  mov     rcx, rbx; this
0x180009e00  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x180009e05  xor     r15d, r15d
0x180009e08  cmp     [rdi+58h], r15d
0x180009e0c  jbe     loc_180009FBF
0x180009e12  mov     r14, [rdi+60h]
0x180009e16  lea     rdx, aDataName; "  <Data Name=\""
  ... truncated ...
```
