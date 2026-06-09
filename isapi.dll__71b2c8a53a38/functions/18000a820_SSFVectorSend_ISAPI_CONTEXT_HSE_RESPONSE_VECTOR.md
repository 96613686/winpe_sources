# SSFVectorSend(ISAPI_CONTEXT *,_HSE_RESPONSE_VECTOR *)

- ea: `0x18000a820`
- end: `0x18000b057`
- name: `?SSFVectorSend@@YAJPEAVISAPI_CONTEXT@@PEAU_HSE_RESPONSE_VECTOR@@@Z`
- size: `2103`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *this, struct _HSE_RESPONSE_VECTOR *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003ef0`
- `0x18000b060`

## callees

- `0x180005e34`
- `0x180005ff4`
- `0x18000a820`
- `0x180012482`
- `0x1800124c0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad54`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18000aca2`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18000aca2`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000a9ca`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000a9ca`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000abea`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ac02`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000abea`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ac02`
- `iisutil!PuDbgPrint` at `0x18000a925`
- `iisutil!PuDbgPrint` at `0x18000aa0a`
- `iisutil!PuDbgPrint` at `0x18000aa77`
- `iisutil!PuDbgPrint` at `0x18000ab4f`
- `iisutil!PuDbgPrint` at `0x18000ae30`
- `iisutil!PuDbgPrint` at `0x18000af61`
- `iisutil!PuDbgPrint` at `0x18000afb3`
- `iisutil!PuDbgPrint` at `0x18000b017`
- `iisutil!PuDbgPrint` at `0x18000a925`
- `iisutil!PuDbgPrint` at `0x18000aa0a`
- `iisutil!PuDbgPrint` at `0x18000aa77`
- `iisutil!PuDbgPrint` at `0x18000ab4f`
- `iisutil!PuDbgPrint` at `0x18000ae30`
- `iisutil!PuDbgPrint` at `0x18000af61`
- `iisutil!PuDbgPrint` at `0x18000afb3`
- `iisutil!PuDbgPrint` at `0x18000b017`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000aa8c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000aa8c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000af09`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000b022`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000af09`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000b022`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000a95c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000a95c`
- `iisutil!?CopyBinary@STRA@@QEAAJPEAXK@Z` at `0x18000a99e`
- `iisutil!?CopyBinary@STRA@@QEAAJPEAXK@Z` at `0x18000a99e`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000abc1`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000abc1`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000a875`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000a875`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000a9b3`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000a9b3`

## string_xrefs

- `0x18000a8fc`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000a9e3`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000aa47`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000ab48`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000ae1e`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000af55`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000afa1`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000b00b`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000afeb`: `\n  HSE_REQ_VECTOR_SEND[%p]: Failed\n    Another async operation is already pending\n  <END>\n\n`

## pseudocode

```c
__int64 __fastcall SSFVectorSend(struct ISAPI_CONTEXT *this, struct _HSE_RESPONSE_VECTOR *a2)
{
  int v4; // edx
  DWORD v5; // r15d
  DWORD dwFlags; // r9d
  const char *v7; // rax
  const char *pszHeaders; // rdx
  const char *pszStatus; // rcx
  DWORD v10; // r10d
  DWORD nElementCount; // r8d
  DWORD i; // ebx
  LPHSE_VECTOR_ELEMENT lpElementArray; // rdx
  __int64 v14; // rcx
  unsigned int cbSize; // r8d
  PVOID pvContext; // rdx
  const char *Str; // rax
  int inited; // eax
  LPSTR v19; // r8
  signed int v20; // ebx
  size_t v21; // rbx
  unsigned __int64 v22; // r13
  void *Ptr; // rax
  _DWORD *v24; // r12
  int v25; // edx
  LPHSE_VECTOR_ELEMENT v26; // r14
  __int64 v27; // rbx
  PVOID v28; // rcx
  DWORD ElementType; // r8d
  __int64 v30; // rax
  ULONGLONG cbSize_low; // rax
  signed int LastError; // eax
  __int64 v34; // [rsp+30h] [rbp-D0h]
  __int64 v35; // [rsp+38h] [rbp-C8h]
  union _LARGE_INTEGER FileSize; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+68h] [rbp-98h]
  _BYTE v38[48]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v39[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 v40[512]; // [rsp+E0h] [rbp-20h] BYREF
  char v41[512]; // [rsp+2E0h] [rbp+1E0h] BYREF

  memset_0(v40, 0, sizeof(v40));
  BUFFER::BUFFER((BUFFER *)v38, v40, 0x200u);
  v4 = g_dwDebugFlags;
  v5 = 0;
  if ( (g_dwDebugFlags & 0x4000000) != 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      if ( a2 )
      {
        dwFlags = a2->dwFlags;
        v7 = "Asynchronous";
        pszHeaders = a2->pszHeaders;
        if ( (a2->dwFlags & 2) == 0 )
          v7 = "Synchronous";
        pszStatus = a2->pszStatus;
        v10 = a2->dwFlags;
        nElementCount = a2->nElementCount;
      }
      else
      {
        v7 = (const char *)word_180016DBA;
        pszStatus = 0;
        pszHeaders = 0;
        nElementCount = 0;
        dwFlags = 0;
        v10 = 0;
      }
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        2877,
        "SSFVectorSend",
        "\r\n"
        "  HSE_REQ_VECTOR_SEND[%p]: Function Entry (%s)\r\n"
        "    Status: '%s'\r\n"
        "    Headers: '%s'\r\n"
        "    Element Count: %d\r\n"
        "    Flags: 0x%08x (%d)\r\n"
        "  <END>\r\n"
        "\r\n",
        this,
        v7,
        pszStatus,
        pszHeaders,
        nElementCount,
        dwFlags,
        v10);
      v4 = g_dwDebugFlags;
    }
    if ( (v4 & 0x8000000) != 0 && a2 && a2->nElementCount )
    {
      STRA::STRA((STRA *)v39, v41, 0x200u);
      for ( i = 0; i < a2->nElementCount; ++i )
      {
        lpElementArray = a2->lpElementArray;
        v14 = i;
        if ( lpElementArray[v14].ElementType )
        {
          if ( lpElementArray[v14].ElementType == 1 && (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
              2926,
              "SSFVectorSend",
              "\r\n",
              "  HSE_REQ_VECTOR_SEND[%p]: Element %d\r\n"
              "    File Handle: %p\r\n"
              "    Offset: %d\r\n"
              "    Bytes To Send: %d\r\n"
              "  <END>\r\n"
              "\r\n",
              this,
              lpElementArray[v14].pvContext,
              lpElementArray[v14].cbOffset,
              lpElementArray[v14].cbSize);
        }
        else
        {
          cbSize = lpElementArray[v14].cbSize;
          pvContext = lpElementArray[v14].pvContext;
          if ( cbSize > 0xA0 )
            cbSize = 160;
          if ( (int)STRA::CopyBinary((STRA *)v39, pvContext, cbSize) < 0 )
            STRA::Copy((STRA *)v39, (const char *)word_180016DBA);
          if ( (g_dwDebugFlags & 3) != 0 )
          {
            Str = STRA::QueryStr((STRA *)v39);
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
              2912,
              "SSFVectorSend",
              "\r\n  HSE_REQ_VECTOR_SEND[%p]: Dump of up to %d bytes of element %d\r\n%s  <END>\r\n\r\n",
              this,
              160,
              i,
              Str);
          }
        }
      }
      STRA::~STRA((STRA *)v39);
      v4 = g_dwDebugFlags;
    }
  }
  v37 = *((_QWORD *)this + 24);
  if ( !v37 )
  {
    if ( (v4 & 3) != 0 && (v4 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        2943,
        "SSFVectorSend",
        "\r\n  HSE_REQ_VECTOR_SEND[%p]: Failed to get interface to server core\r\n  <END>\r\n\r\n",
        this);
LABEL_95:
    BUFFER::~BUFFER((BUFFER *)v38);
    return 2147942487LL;
  }
  if ( !a2
    || (a2->dwFlags & 2) != 0
    && (!*((_QWORD *)this + 28) || (inited = ISAPI_CONTEXT::TryInitAsyncIo(this, 4), v4 = g_dwDebugFlags, !inited)) )
  {
    if ( (v4 & 3) != 0 && (v4 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        2965,
        "SSFVectorSend",
        "\r\n  HSE_REQ_VECTOR_SEND[%p]: Failed\r\n    Another async operation is already pending\r\n  <END>\r\n\r\n",
        this);
    goto LABEL_95;
  }
  if ( (a2->dwFlags & 3) == 3 )
  {
    if ( ((unsigned __int8)v4 & a2->dwFlags & 3) != 0 && (v4 & 0x100000) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        2981,
        "SSFVectorSend",
        "\r\n"
        "  HSE_REQ_VECTOR_SEND[%p]: Parameter validation failure\r\n"
        "    Both HSE_IO_SYNC and HSE_IO_ASYNC were specified\r\n"
        "  <END>\r\n"
        "\r\n",
        this);
LABEL_87:
      v4 = g_dwDebugFlags;
      goto LABEL_88;
    }
    goto LABEL_88;
  }
  v19 = a2->pszStatus;
  if ( (a2->dwFlags & 8) != 0 )
  {
    if ( !v19 || !a2->pszHeaders )
    {
      if ( (v4 & 3) != 0 && (v4 & 0x100000) != 0 )
      {
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
          3004,
          "SSFVectorSend",
          "\r\n"
          "  HSE_REQ_VECTOR_SEND[%p]: Parameter validation failure\r\n"
          "    HSE_IO_SEND_HEADERS was specified, but some required info is missing\r\n"
          "    Status: '%s'\r\n"
          "    Headers: '%s'\r\n"
          "  <END>\r\n"
          "\r\n",
          this,
          v19,
          a2->pszHeaders);
        goto LABEL_87;
      }
LABEL_88:
      v20 = -2147024809;
LABEL_89:
      if ( (v4 & 3) != 0 && (v4 & 0x100000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
          3261,
          "SSFVectorSend",
          "\r\n  HSE_REQ_VECTOR_SEND[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
          this,
          v20);
      if ( (a2->dwFlags & 2) != 0 )
      {
        *((_QWORD *)this + 27) = 0;
        ISAPI_CONTEXT::DereferenceIsapiContext(this);
      }
      goto LABEL_84;
    }
  }
  else if ( v19 || a2->pszHeaders )
  {
    if ( (v4 & 3) != 0 && (v4 & 0x100000) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        3027,
        "SSFVectorSend",
        "\r\n"
        "  HSE_REQ_VECTOR_SEND[%p]: Parameter validation failure\r\n"
        "    HSE_IO_SEND_HEADERS was not specified, yet status or header info was provided\r\n"
        "    Status: '%s'\r\n"
        "    Headers: '%s'\r\n"
        "  <END>\r\n"
        "\r\n",
        this,
        v19,
        a2->pszHeaders);
      goto LABEL_87;
    }
    goto LABEL_88;
  }
  if ( !BUFFER::Resize((BUFFER *)v38, 32 * a2->nElementCount) )
  {
    v20 = -2147024888;
LABEL_44:
    v4 = g_dwDebugFlags;
    goto LABEL_89;
  }
  v21 = 32LL * a2->nElementCount;
  v22 = 0;
  Ptr = BUFFER::QueryPtr((BUFFER *)v38);
  memset_0(Ptr, 0, v21);
  v24 = BUFFER::QueryPtr((BUFFER *)v38);
  v25 = -1;
  while ( v5 < a2->nElementCount )
  {
    v26 = a2->lpElementArray;
    v27 = 32LL * v5;
    v28 = v26[(unsigned __int64)v27 / 0x20].pvContext;
    if ( !v28 )
    {
      v4 = g_dwDebugFlags;
      if ( (g_dwDebugFlags & 3) == 0 || (g_dwDebugFlags & 0x100000) == 0 )
        goto LABEL_88;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        3060,
        "SSFVectorSend",
        "\r\n"
        "  HSE_REQ_VECTOR_SEND[%p]: Parameter validation failure\r\n"
        "    Context: NULL on element %d in the array\r\n"
        "  <END>\r\n"
        "\r\n",
        this,
        v5);
      goto LABEL_87;
    }
    ElementType = v26[v5].ElementType;
    if ( !ElementType )
    {
      if ( v26[(unsigned __int64)v27 / 0x20].cbSize > 0xFFFFFFFF )
      {
        v4 = g_dwDebugFlags;
        if ( (g_dwDebugFlags & 3) == 0 || (g_dwDebugFlags & 0x100000) == 0 )
          goto LABEL_88;
        LODWORD(v34) = v5;
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
          3082,
          "SSFVectorSend",
          "\r\n"
          "  HSE_REQ_VECTOR_SEND[%p]: Parameter validation failure\r\n"
          "    Invalid memory buffer size on element %d in the array\r\n"
          "    Size: %d\r\n"
          "  <END>\r\n"
          "\r\n",
          this,
          v34,
          v26[(unsigned __int64)v27 / 0x20].cbSize);
        goto LABEL_87;
      }
      v24[8 * v5] = 0;
      *(_QWORD *)&v24[(unsigned __int64)v27 / 4 + 2] = v26[(unsigned __int64)v27 / 0x20].pvContext;
      cbSize_low = LODWORD(v26[(unsigned __int64)v27 / 0x20].cbSize);
      v24[(unsigned __int64)v27 / 4 + 4] = cbSize_low;
      goto LABEL_61;
    }
    if ( ElementType == 1 )
    {
      if ( v28 == (PVOID)-1LL )
      {
        v4 = g_dwDebugFlags;
        if ( (g_dwDebugFlags & 3) == 0 || (g_dwDebugFlags & 0x100000) == 0 )
          goto LABEL_88;
        LODWORD(v34) = v5;
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
          3107,
          "SSFVectorSend",
          "\r\n"
          "  HSE_REQ_VECTOR_SEND[%p]: Parameter validation failure\r\n"
          "    Handle on file handle element %d in the array is invalid\r\n"
          "    File Handle: %p\r\n"
          "  <END>\r\n"
          "\r\n",
          this,
          v34,
          -1);
        goto LABEL_87;
      }
      if ( !v26[(unsigned __int64)v27 / 0x20].cbSize )
      {
        FileSize.QuadPart = 0;
        if ( !GetFileSizeEx(v28, &FileSize) )
        {
          LastError = GetLastError();
          v20 = LastError;
          if ( LastError > 0 )
            v20 = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_44;
        }
        v25 = -1;
        v26[(unsigned __int64)v27 / 0x20].cbSize = FileSize.QuadPart - v26[(unsigned __int64)v27 / 0x20].cbOffset;
      }
      v24[8 * v5] = 1;
      *(_QWORD *)&v24[(unsigned __int64)v27 / 4 + 6] = v26[(unsigned __int64)v27 / 0x20].pvContext;
      *(_QWORD *)&v24[(unsigned __int64)v27 / 4 + 2] = v26[(unsigned __int64)v27 / 0x20].cbOffset;
      cbSize_low = v26[(unsigned __int64)v27 / 0x20].cbSize;
      *(_QWORD *)&v24[(unsigned __int64)v27 / 4 + 4] = cbSize_low;
LABEL_61:
      v22 += cbSize_low;
      goto LABEL_62;
    }
    if ( ElementType != 2 )
    {
      v4 = g_dwDebugFlags;
      if ( (g_dwDebugFlags & 3) == 0 || (g_dwDebugFlags & 0x100000) == 0 )
        goto LABEL_88;
      LODWORD(v35) = v26[v5].ElementType;
      LODWORD(v34) = v5;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        3159,
        "SSFVectorSend",
        "\r\n"
        "  HSE_REQ_VECTOR_SEND[%p]: Parameter validation failure\r\n"
        "    Unknown type on element %d in the array\r\n"
        "    Element Type: %d\r\n"
        "  <END>\r\n"
        "\r\n",
        this,
        v34,
        v35);
      goto LABEL_87;
    }
    v24[8 * v5] = 2;
    *(_QWORD *)&v24[(unsigned __int64)v27 / 4 + 4] = v26[(unsigned __int64)v27 / 0x20].pvContext;
    v30 = -1;
    do
      ++v30;
    while ( *((_WORD *)v26[(unsigned __int64)v27 / 0x20].pvContext + v30) );
    LOWORD(v24[(unsigned __int64)v27 / 4 + 2]) = 2 * v30;
LABEL_62:
    ++v5;
  }
  if ( v22 <= 0xFFFFFFFF )
    v25 = v22;
  *((_DWORD *)this + 55) = v25;
  if ( (a2->dwFlags & 4) != 0 )
  {
    *((_DWORD *)this + 63) = 0;
LABEL_81:
    if ( (a2->dwFlags & 8) != 0 )
      *((_DWORD *)this + 64) = 1;
  }
  else
  {
    if ( !*((_DWORD *)this + 62) || *((_DWORD *)this + 64) )
      goto LABEL_81;
    if ( (a2->dwFlags & 8) != 0 )
    {
      *((_DWORD *)this + 63) = 1;
      goto LABEL_81;
    }
  }
  v20 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, bool, LPSTR, LPSTR, _DWORD *, DWORD, DWORD, DWORD, DWORD))(*(_QWORD *)v37 + 112LL))(
          v37,
          (unsigned __int64)this & -(__int64)((a2->dwFlags & 2) != 0),
          *((_DWORD *)this + 63) == 0,
          a2->pszStatus,
          a2->pszHeaders,
          v24,
          a2->nElementCount,
          (a2->dwFlags >> 4) & 1,
          (a2->dwFlags >> 5) & 1,
          (a2->dwFlags >> 6) & 1);
  if ( v20 < 0 )
    goto LABEL_44;
LABEL_84:
  BUFFER::~BUFFER((BUFFER *)v38);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x18000a820  mov     [rsp-8+arg_10], rbx
0x18000a825  push    rbp
0x18000a826  push    rsi
0x18000a827  push    rdi
0x18000a828  push    r12
0x18000a82a  push    r13
0x18000a82c  push    r14
0x18000a82e  push    r15
0x18000a830  lea     rbp, [rsp-3F0h]
0x18000a838  sub     rsp, 4F0h
0x18000a83f  mov     rax, cs:__security_cookie
0x18000a846  xor     rax, rsp
0x18000a849  mov     [rbp+420h+var_40], rax
0x18000a850  mov     rsi, rdx
0x18000a853  mov     rdi, rcx
0x18000a856  mov     ebx, 200h
0x18000a85b  lea     rcx, [rbp+420h+var_440]; void *
0x18000a85f  mov     r8d, ebx; Size
0x18000a862  xor     edx, edx; Val
0x18000a864  call    memset_0
0x18000a869  mov     r8d, ebx
0x18000a86c  lea     rdx, [rbp+420h+var_440]
0x18000a870  lea     rcx, [rsp+520h+var_4B0]
0x18000a875  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18000a87b  mov     edx, cs:g_dwDebugFlags
0x18000a881  xor     r15d, r15d
0x18000a884  bt      edx, 1Ah
0x18000a888  jnb     loc_18000AA98
0x18000a88e  test    dl, 3
0x18000a891  jz      loc_18000A931
0x18000a897  test    rsi, rsi
0x18000a89a  jz      short loc_18000A8C5
0x18000a89c  test    byte ptr [rsi], 2
0x18000a89f  lea     rcx, aSynchronous; "Synchronous"
0x18000a8a6  mov     r9d, [rsi]
0x18000a8a9  lea     rax, aAsynchronous; "Asynchronous"
0x18000a8b0  mov     rdx, [rsi+10h]
0x18000a8b4  cmovz   rax, rcx
0x18000a8b8  mov     rcx, [rsi+8]
0x18000a8bc  mov     r10d, r9d
0x18000a8bf  mov     r8d, [rsi+18h]
0x18000a8c3  jmp     short loc_18000A8DB
0x18000a8c5  lea     rax, word_180016DBA
0x18000a8cc  mov     rcx, r15
0x18000a8cf  mov     rdx, r15
0x18000a8d2  mov     r8d, r15d
0x18000a8d5  mov     r9d, r15d
0x18000a8d8  mov     r10d, r15d
0x18000a8db  mov     [rsp+520h+var_4C8], r10d
0x18000a8e0  mov     [rsp+520h+var_4D0], r9d
0x18000a8e5  lea     r9, aSsfvectorsend; "SSFVectorSend"
0x18000a8ec  mov     dword ptr [rsp+520h+var_4D8], r8d
0x18000a8f1  mov     r8d, 0B3Dh
0x18000a8f7  mov     [rsp+520h+var_4E0], rdx
0x18000a8fc  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000a903  mov     [rsp+520h+var_4E8], rcx
0x18000a908  mov     rcx, cs:g_pDebug
0x18000a90f  mov     [rsp+520h+var_4F0], rax
0x18000a914  lea     rax, aHseReqVectorSe_0; "\r\n  HSE_REQ_VECTOR_SEND[%p]: Function"...
0x18000a91b  mov     [rsp+520h+var_4F8], rdi
0x18000a920  mov     [rsp+520h+var_500], rax
0x18000a925  call    cs:__imp_PuDbgPrint
0x18000a92b  mov     edx, cs:g_dwDebugFlags
0x18000a931  bt      edx, 1Bh
0x18000a935  jnb     loc_18000AA98
0x18000a93b  test    rsi, rsi
0x18000a93e  jz      loc_18000AA98
0x18000a944  cmp     [rsi+18h], r15d
0x18000a948  jz      loc_18000AA98
0x18000a94e  mov     r8d, ebx
0x18000a951  lea     rdx, [rbp+420h+var_240]
0x18000a958  lea     rcx, [rbp+420h+var_480]
0x18000a95c  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000a962  mov     ebx, r15d
0x18000a965  cmp     [rsi+18h], r15d
0x18000a969  jbe     loc_18000AA88
0x18000a96f  mov     r14d, 0A0h
0x18000a975  mov     rdx, [rsi+20h]
0x18000a979  mov     ecx, ebx
0x18000a97b  shl     rcx, 5
0x18000a97f  cmp     [rcx+rdx], r15d
0x18000a983  jnz     loc_18000AA12
0x18000a989  mov     r8d, [rcx+rdx+18h]
0x18000a98e  cmp     r8d, r14d
0x18000a991  mov     rdx, [rcx+rdx+8]
0x18000a996  lea     rcx, [rbp+420h+var_480]
0x18000a99a  cmova   r8d, r14d
0x18000a99e  call    cs:__imp_?CopyBinary@STRA@@QEAAJPEAXK@Z; STRA::CopyBinary(void *,ulong)
0x18000a9a4  test    eax, eax
0x18000a9a6  jns     short loc_18000A9B9
0x18000a9a8  lea     rdx, word_180016DBA
0x18000a9af  lea     rcx, [rbp+420h+var_480]
0x18000a9b3  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x18000a9b9  test    byte ptr cs:g_dwDebugFlags, 3
0x18000a9c0  jz      loc_18000AA7D
0x18000a9c6  lea     rcx, [rbp+420h+var_480]
0x18000a9ca  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18000a9d0  mov     rcx, cs:g_pDebug
0x18000a9d7  lea     r9, aSsfvectorsend; "SSFVectorSend"
0x18000a9de  mov     [rsp+520h+var_4E0], rax
0x18000a9e3  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000a9ea  mov     dword ptr [rsp+520h+var_4E8], ebx
0x18000a9ee  lea     rax, aHseReqVectorSe_12; "\r\n  HSE_REQ_VECTOR_SEND[%p]: Dump of "...
0x18000a9f5  mov     dword ptr [rsp+520h+var_4F0], r14d
0x18000a9fa  mov     r8d, 0B60h
0x18000aa00  mov     [rsp+520h+var_4F8], rdi
0x18000aa05  mov     [rsp+520h+var_500], rax
0x18000aa0a  call    cs:__imp_PuDbgPrint
0x18000aa10  jmp     short loc_18000AA7D
0x18000aa12  cmp     dword ptr [rcx+rdx], 1
0x18000aa16  jnz     short loc_18000AA7D
0x18000aa18  test    byte ptr cs:g_dwDebugFlags, 3
0x18000aa1f  jz      short loc_18000AA7D
0x18000aa21  mov     rax, [rcx+rdx+18h]
0x18000aa26  lea     r9, aSsfvectorsend; "SSFVectorSend"
0x18000aa2d  mov     [rsp+520h+var_4D8], rax
0x18000aa32  mov     r8d, 0B6Eh
0x18000aa38  mov     rax, [rcx+rdx+10h]
0x18000aa3d  mov     [rsp+520h+var_4E0], rax
0x18000aa42  mov     rax, [rcx+rdx+8]
0x18000aa47  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000aa4e  mov     rcx, cs:g_pDebug
0x18000aa55  mov     [rsp+520h+var_4E8], rax
0x18000aa5a  lea     rax, aHseReqVectorSe_8; "  HSE_REQ_VECTOR_SEND[%p]: Element %d\r"...
0x18000aa61  mov     [rsp+520h+var_4F0], rdi
0x18000aa66  mov     [rsp+520h+var_4F8], rax
0x18000aa6b  lea     rax, Control; "\r\n"
0x18000aa72  mov     [rsp+520h+var_500], rax
0x18000aa77  call    cs:__imp_PuDbgPrint
0x18000aa7d  inc     ebx
0x18000aa7f  cmp     ebx, [rsi+18h]
0x18000aa82  jb      loc_18000A975
0x18000aa88  lea     rcx, [rbp+420h+var_480]
0x18000aa8c  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000aa92  mov     edx, cs:g_dwDebugFlags
0x18000aa98  mov     r14, [rdi+0C0h]
0x18000aa9f  mov     [rsp+520h+var_4B8], r14
0x18000aaa4  test    r14, r14
0x18000aaa7  jnz     short loc_18000AAD0
0x18000aaa9  test    dl, 3
0x18000aaac  setnz   cl
0x18000aaaf  bt      edx, 14h
0x18000aab3  setb    al
0x18000aab6  test    al, cl
0x18000aab8  jz      loc_18000B01D
0x18000aabe  lea     rax, aHseReqVectorSe_15; "\r\n  HSE_REQ_VECTOR_SEND[%p]: Failed t"...
0x18000aac5  mov     r8d, 0B7Fh
0x18000aacb  jmp     loc_18000AFF8
0x18000aad0  test    rsi, rsi
0x18000aad3  jz      loc_18000AFDA
0x18000aad9  test    byte ptr [rsi], 2
0x18000aadc  jz      short loc_18000AB06
0x18000aade  cmp     [rdi+0E0h], r15
0x18000aae5  jz      loc_18000AFDA
0x18000aaeb  mov     edx, 4
0x18000aaf0  mov     rcx, rdi
0x18000aaf3  call    ?TryInitAsyncIo@ISAPI_CONTEXT@@QEAAHW4ASYNC_PENDING@@@Z; ISAPI_CONTEXT::TryInitAsyncIo(ASYNC_PENDING)
0x18000aaf8  mov     edx, cs:g_dwDebugFlags
0x18000aafe  test    eax, eax
0x18000ab00  jz      loc_18000AFDA
0x18000ab06  mov     eax, [rsi]
0x18000ab08  and     eax, 3
0x18000ab0b  cmp     al, 3
0x18000ab0d  jnz     short loc_18000AB5A
0x18000ab0f  test    al, dl
0x18000ab11  setnz   cl
0x18000ab14  bt      edx, 14h
0x18000ab18  setb    al
0x18000ab1b  test    al, cl
0x18000ab1d  jz      loc_18000AF6D
0x18000ab23  mov     rcx, cs:g_pDebug
0x18000ab2a  lea     rax, aHseReqVectorSe_3; "\r\n  HSE_REQ_VECTOR_SEND[%p]: Paramete"...
0x18000ab31  mov     [rsp+520h+var_4F8], rdi
0x18000ab36  lea     r9, aSsfvectorsend; "SSFVectorSend"
0x18000ab3d  mov     r8d, 0BA5h
0x18000ab43  mov     [rsp+520h+var_500], rax
0x18000ab48  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000ab4f  call    cs:__imp_PuDbgPrint
0x18000ab55  jmp     loc_18000AF67
0x18000ab5a  test    byte ptr [rsi], 8
0x18000ab5d  mov     r8, [rsi+8]
0x18000ab61  jz      short loc_18000ABA3
0x18000ab63  test    r8, r8
0x18000ab66  jz      short loc_18000AB6E
0x18000ab68  cmp     [rsi+10h], r15
0x18000ab6c  jnz     short loc_18000ABB6
0x18000ab6e  test    dl, 3
0x18000ab71  setnz   cl
0x18000ab74  bt      edx, 14h
0x18000ab78  setb    al
0x18000ab7b  test    al, cl
0x18000ab7d  jz      loc_18000AF6D
0x18000ab83  mov     rax, [rsi+10h]
0x18000ab87  mov     [rsp+520h+var_4E8], rax
0x18000ab8c  lea     rax, aHseReqVectorSe_4; "\r\n  HSE_REQ_VECTOR_SEND[%p]: Paramete"...
0x18000ab93  mov     [rsp+520h+var_4F0], r8
0x18000ab98  mov     r8d, 0BBCh
0x18000ab9e  jmp     loc_18000AF42
0x18000aba3  test    r8, r8
0x18000aba6  jnz     loc_18000AF16
0x18000abac  cmp     [rsi+10h], r15
0x18000abb0  jnz     loc_18000AF16
0x18000abb6  mov     edx, [rsi+18h]
0x18000abb9  lea     rcx, [rsp+520h+var_4B0]
0x18000abbe  shl     edx, 5
0x18000abc1  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000abc7  test    al, al
0x18000abc9  jnz     short loc_18000ABDB
0x18000abcb  mov     ebx, 80070008h
0x18000abd0  mov     edx, cs:g_dwDebugFlags
0x18000abd6  jmp     loc_18000AF72
0x18000abdb  mov     ebx, [rsi+18h]
0x18000abde  lea     rcx, [rsp+520h+var_4B0]
0x18000abe3  shl     rbx, 5
0x18000abe7  mov     r13, r15
0x18000abea  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000abf0  mov     r8, rbx; Size
0x18000abf3  xor     edx, edx; Val
0x18000abf5  mov     rcx, rax; void *
0x18000abf8  call    memset_0
0x18000abfd  lea     rcx, [rsp+520h+var_4B0]
0x18000ac02  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000ac08  mov     r12, rax
0x18000ac0b  mov     edx, 0FFFFFFFFh
0x18000ac10  cmp     r15d, [rsi+18h]
0x18000ac14  jnb     loc_18000AE3B
0x18000ac1a  mov     r14, [rsi+20h]
0x18000ac1e  xor     r9d, r9d
0x18000ac21  mov     ebx, r15d
0x18000ac24  shl     rbx, 5
0x18000ac28  mov     rcx, [r14+rbx+8]; hFile
0x18000ac2d  test    rcx, rcx
0x18000ac30  jz      loc_18000ADE4
0x18000ac36  mov     r8d, [r14+rbx]
0x18000ac3a  mov     eax, r8d
0x18000ac3d  test    r8d, r8d
0x18000ac40  jz      loc_18000ACEC
0x18000ac46  sub     eax, 1
0x18000ac49  jz      short loc_18000AC87
0x18000ac4b  cmp     eax, 1
0x18000ac4e  jnz     loc_18000AD1D
0x18000ac54  mov     dword ptr [r12+rbx], 2
0x18000ac5c  mov     rax, [r14+rbx+8]
0x18000ac61  mov     [r12+rbx+10h], rax
0x18000ac66  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ac6a  mov     rcx, [r14+rbx+8]
0x18000ac6f  inc     rax
0x18000ac72  cmp     [rcx+rax*2], r9w
0x18000ac77  jnz     short loc_18000AC6F
0x18000ac79  add     ax, ax
0x18000ac7c  mov     [r12+rbx+8], ax
0x18000ac82  jmp     loc_18000AD15
0x18000ac87  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ac8b  jz      loc_18000AD72
0x18000ac91  cmp     [r14+rbx+18h], r9
0x18000ac96  jnz     short loc_18000ACC4
0x18000ac98  lea     rdx, [rsp+520h+FileSize]; lpFileSize
0x18000ac9d  mov     qword ptr [rsp+520h+FileSize], r9
0x18000aca2  call    cs:__imp_GetFileSizeEx
0x18000aca8  test    eax, eax
0x18000acaa  jz      loc_18000AD54
0x18000acb0  mov     rax, qword ptr [rsp+520h+FileSize]
0x18000acb5  mov     edx, 0FFFFFFFFh
0x18000acba  sub     rax, [r14+rbx+10h]
0x18000acbf  mov     [r14+rbx+18h], rax
0x18000acc4  mov     dword ptr [r12+rbx], 1
0x18000accc  mov     rax, [r14+rbx+8]
0x18000acd1  mov     [r12+rbx+18h], rax
0x18000acd6  mov     rax, [r14+rbx+10h]
0x18000acdb  mov     [r12+rbx+8], rax
0x18000ace0  mov     rax, [r14+rbx+18h]
0x18000ace5  mov     [r12+rbx+10h], rax
0x18000acea  jmp     short loc_18000AD12
0x18000acec  mov     r8, [r14+rbx+18h]
0x18000acf1  cmp     r8, rdx
0x18000acf4  ja      loc_18000ADAD
0x18000acfa  mov     [r12+rbx], r9d
0x18000acfe  mov     rax, [r14+rbx+8]
0x18000ad03  mov     [r12+rbx+8], rax
0x18000ad08  mov     eax, [r14+rbx+18h]
0x18000ad0d  mov     [r12+rbx+10h], eax
0x18000ad12  add     r13, rax
0x18000ad15  inc     r15d
0x18000ad18  jmp     loc_18000AC10
0x18000ad1d  mov     edx, cs:g_dwDebugFlags
0x18000ad23  test    dl, 3
0x18000ad26  setnz   cl
0x18000ad29  bt      edx, 14h
0x18000ad2d  setb    al
0x18000ad30  test    al, cl
0x18000ad32  jz      loc_18000AF6D
0x18000ad38  mov     dword ptr [rsp+520h+var_4E8], r8d
0x18000ad3d  lea     rax, aHseReqVectorSe_5; "\r\n  HSE_REQ_VECTOR_SEND[%p]: Paramete"...
0x18000ad44  mov     dword ptr [rsp+520h+var_4F0], r15d
0x18000ad49  mov     r8d, 0C57h
0x18000ad4f  jmp     loc_18000AF42
0x18000ad54  call    cs:__imp_GetLastError
0x18000ad5a  mov     ebx, eax
0x18000ad5c  test    eax, eax
0x18000ad5e  jle     loc_18000ABD0
  ... truncated ...
```
