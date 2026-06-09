# SSFExecuteUrl(ISAPI_CONTEXT *,void *,int)

- ea: `0x180006970`
- end: `0x1800071c6`
- name: `?SSFExecuteUrl@@YAJPEAVISAPI_CONTEXT@@PEAXH@Z`
- size: `2134`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *this, _QWORD *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180005e34`
- `0x180005ff4`
- `0x180006970`
- `0x180012482`
- `0x1800124c0`
- `0x180013010`

## import_xrefs

- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180006b98`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180006b98`
- `iisutil!PuDbgPrint` at `0x180006b26`
- `iisutil!PuDbgPrint` at `0x180006bd3`
- `iisutil!PuDbgPrint` at `0x180006cbc`
- `iisutil!PuDbgPrint` at `0x180006d2c`
- `iisutil!PuDbgPrint` at `0x180006f09`
- `iisutil!PuDbgPrint` at `0x180007185`
- `iisutil!PuDbgPrint` at `0x180006b26`
- `iisutil!PuDbgPrint` at `0x180006bd3`
- `iisutil!PuDbgPrint` at `0x180006cbc`
- `iisutil!PuDbgPrint` at `0x180006d2c`
- `iisutil!PuDbgPrint` at `0x180006f09`
- `iisutil!PuDbgPrint` at `0x180007185`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180006bdd`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180006bdd`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180006b53`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180006b53`
- `iisutil!?CopyBinary@STRA@@QEAAJPEAXK@Z` at `0x180006b70`
- `iisutil!?CopyBinary@STRA@@QEAAJPEAXK@Z` at `0x180006b70`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180006b85`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180006b85`

## string_xrefs

- `0x180006af0`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180006ba5`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180006ca8`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180006d18`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180006ef8`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000716b`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180006a68`: `\n  HSE_REQ_EXEC_UNICODE_URL[%p]: Function Entry\n    URL: '%S'\n    Method: '%s'\n    Child Headers: '%s'\n    Flags: 0x%08x (%d)\n    Impersonation Token: %p\n    Custom User Name: '%S'\n    Custom Auth Type: '%s'\n  <END>\n\n`
- `0x180006ae4`: `\n  HSE_REQ_EXEC_UNICODE_URL[%p]: Function Entry\n    URL: '%s'\n    Method: '%s'\n    Child Headers: '%s'\n    Flags: 0x%08x (%d)\n    Impersonation Token: %p\n    Custom User Name: '%s'\n    Custom Auth Type: '%s'\n  <END>\n\n`
- `0x180006c5f`: `\n  HSE_REQ_EXEC_URL[%p]: Failed\n    No I/O completion has been set: NULL\n  <END>\n\n`
- `0x180006c94`: `\n  HSE_REQ_EXEC_URL[%p]: Failed\n    An async operation is already pending: NULL\n  <END>\n\n`

## pseudocode

```c
__int64 __fastcall SSFExecuteUrl(struct ISAPI_CONTEXT *this, _QWORD *a2, int a3)
{
  int v6; // eax
  __int64 v7; // rsi
  __int64 *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // r11d
  int v13; // r14d
  __int64 v14; // rcx
  __int64 v15; // r9
  __int64 v16; // r10
  __int64 v17; // r8
  const char *v18; // rax
  __int64 *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  unsigned int v23; // r8d
  const char *Str; // rax
  __int64 v25; // rsi
  _WORD *v27; // rax
  __int64 v28; // rcx
  int v29; // r8d
  int v30; // ebx
  __int64 v31; // rdx
  _BYTE *v32; // rax
  _BYTE *v33; // rax
  _QWORD *v34; // rdx
  int *v35; // rax
  int v36; // edx
  const char *v37; // rax
  __int64 v38; // r8
  __int64 v39; // rax
  __int64 v40; // rdx
  _BYTE *v41; // rax
  _BYTE *v42; // rax
  _QWORD *v43; // rdx
  __int64 v44; // [rsp+30h] [rbp-D0h]
  __int64 v45; // [rsp+58h] [rbp-A8h]
  __int64 v46; // [rsp+60h] [rbp-A0h]
  __int64 v47; // [rsp+68h] [rbp-98h]
  __int128 v48; // [rsp+70h] [rbp-90h] BYREF
  __int128 v49; // [rsp+80h] [rbp-80h] BYREF
  __int128 v50; // [rsp+90h] [rbp-70h]
  __int64 v51; // [rsp+A0h] [rbp-60h]
  int v52; // [rsp+B0h] [rbp-50h] BYREF
  _WORD *v53; // [rsp+B8h] [rbp-48h]
  int v54; // [rsp+C0h] [rbp-40h]
  __int64 v55; // [rsp+C8h] [rbp-38h]
  __int64 v56; // [rsp+D0h] [rbp-30h]
  __int128 *v57; // [rsp+D8h] [rbp-28h]
  __int128 *v58; // [rsp+E0h] [rbp-20h]
  int v59; // [rsp+E8h] [rbp-18h]
  _BYTE v60[64]; // [rsp+F0h] [rbp-10h] BYREF
  char v61[512]; // [rsp+130h] [rbp+30h] BYREF

  v51 = 0;
  v49 = 0;
  v50 = 0;
  v48 = 0;
  memset_0(&v52, 0, 0x40u);
  v6 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 0x4000000) == 0 )
    goto LABEL_35;
  v7 = 0;
  if ( a3 )
  {
    if ( a2 )
    {
      v8 = (__int64 *)a2[3];
      v7 = a2[4];
    }
    else
    {
      v8 = 0;
    }
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      if ( v8 )
      {
        v9 = *v8;
        v10 = v8[1];
        v11 = v8[2];
      }
      else
      {
        v9 = 0;
        v10 = 0;
        v11 = 0;
      }
      if ( a2 )
      {
        v12 = *((_DWORD *)a2 + 10);
        v13 = v12;
        v14 = *a2;
        v15 = a2[1];
        v16 = a2[2];
      }
      else
      {
        v14 = 0;
        v15 = 0;
        v16 = 0;
        v12 = 0;
        v13 = 0;
      }
      v47 = v11;
      v17 = 1996;
      v46 = v10;
      v45 = v9;
      v18 = "\r\n"
            "  HSE_REQ_EXEC_UNICODE_URL[%p]: Function Entry\r\n"
            "    URL: '%S'\r\n"
            "    Method: '%s'\r\n"
            "    Child Headers: '%s'\r\n"
            "    Flags: 0x%08x (%d)\r\n"
            "    Impersonation Token: %p\r\n"
            "    Custom User Name: '%S'\r\n"
            "    Custom Auth Type: '%s'\r\n"
            "  <END>\r\n"
            "\r\n";
LABEL_25:
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        v17,
        "SSFExecuteUrl",
        v18,
        this,
        v14,
        v15,
        v16,
        v12,
        v13,
        v45,
        v46,
        v47,
        v48,
        v49,
        v50,
        v51);
      v6 = g_dwDebugFlags;
    }
  }
  else
  {
    if ( a2 )
    {
      v19 = (__int64 *)a2[3];
      v7 = a2[4];
    }
    else
    {
      v19 = 0;
    }
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      if ( v19 )
      {
        v20 = *v19;
        v21 = v19[1];
        v22 = v19[2];
      }
      else
      {
        v20 = 0;
        v21 = 0;
        v22 = 0;
      }
      if ( a2 )
      {
        v12 = *((_DWORD *)a2 + 10);
        v13 = v12;
        v14 = *a2;
        v15 = a2[1];
        v16 = a2[2];
      }
      else
      {
        v14 = 0;
        v15 = 0;
        v16 = 0;
        v12 = 0;
        v13 = 0;
      }
      v47 = v22;
      v17 = 2028;
      v46 = v21;
      v45 = v20;
      v18 = "\r\n"
            "  HSE_REQ_EXEC_UNICODE_URL[%p]: Function Entry\r\n"
            "    URL: '%s'\r\n"
            "    Method: '%s'\r\n"
            "    Child Headers: '%s'\r\n"
            "    Flags: 0x%08x (%d)\r\n"
            "    Impersonation Token: %p\r\n"
            "    Custom User Name: '%s'\r\n"
            "    Custom Auth Type: '%s'\r\n"
            "  <END>\r\n"
            "\r\n";
      goto LABEL_25;
    }
  }
  if ( (v6 & 0x8000000) != 0 && v7 )
  {
    STRA::STRA((STRA *)v60, v61, 0x200u);
    v23 = *(_DWORD *)v7;
    if ( *(_DWORD *)v7 > 0xA0u )
      v23 = 160;
    if ( (int)STRA::CopyBinary((STRA *)v60, *(void **)(v7 + 8), v23) < 0 )
      STRA::Copy((STRA *)v60, (const char *)word_180016DBA);
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      Str = STRA::QueryStr((STRA *)v60);
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        2055,
        "SSFExecuteUrl",
        "\r\n  HSE_REQ_EXEC_URL[%p]: Dump of up to %d bytes of entity\r\n%s  <END>\r\n\r\n",
        this,
        160,
        Str);
    }
    STRA::~STRA((STRA *)v60);
    v6 = g_dwDebugFlags;
  }
LABEL_35:
  v25 = *((_QWORD *)this + 24);
  if ( !v25 )
  {
    if ( (v6 & 3) != 0 && (v6 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        2070,
        "SSFExecuteUrl",
        "\r\n  HSE_REQ_EXEC_URL[%p]: Failed to get interface to server core\r\n  <END>\r\n\r\n",
        this);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    if ( (v6 & 3) != 0 && (v6 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        2085,
        "SSFExecuteUrl",
        "\r\n  HSE_REQ_EXEC_URL[%p]: Parameter validation failure\r\n    ExecUrl Info: NULL\r\n  <END>\r\n\r\n",
        this);
    return 2147942487LL;
  }
  if ( !*((_QWORD *)this + 28) )
  {
    if ( (v6 & 3) != 0 && (v6 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        2104,
        "SSFExecuteUrl",
        "\r\n  HSE_REQ_EXEC_URL[%p]: Failed\r\n    No I/O completion has been set: NULL\r\n  <END>\r\n\r\n",
        this);
    return 2147942487LL;
  }
  if ( !(unsigned int)ISAPI_CONTEXT::TryInitAsyncIo(this, 3) )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        2119,
        "SSFExecuteUrl",
        "\r\n  HSE_REQ_EXEC_URL[%p]: Failed\r\n    An async operation is already pending: NULL\r\n  <END>\r\n\r\n",
        this);
    return 2147942487LL;
  }
  v27 = (_WORD *)*a2;
  v28 = -1;
  if ( a3 )
  {
    if ( v27 )
    {
      if ( !*v27 )
      {
        v29 = g_dwDebugFlags;
        if ( (g_dwDebugFlags & 3) == 0 || (g_dwDebugFlags & 0x100000) == 0 )
        {
LABEL_54:
          v30 = -2147024809;
LABEL_120:
          if ( (v29 & 3) != 0 && (v29 & 0x100000) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
              2485,
              "SSFExecuteUrl",
              "\r\n  HSE_REQ_EXEC_URL[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
              this,
              v30);
          *((_DWORD *)this + 54) = 0;
          ISAPI_CONTEXT::DereferenceIsapiContext(this);
          return (unsigned int)v30;
        }
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
          2149,
          "SSFExecuteUrl",
          "\r\n"
          "  HSE_REQ_EXEC_UNICODE_URL[%p]: Parameter validation failure\r\n"
          "    URL is an empty string.\r\n"
          "  <END>\r\n"
          "\r\n",
          this);
LABEL_53:
        v29 = g_dwDebugFlags;
        goto LABEL_54;
      }
      v52 = 1;
      v31 = -1;
      v53 = v27;
      do
        ++v31;
      while ( v27[v31] );
      v54 = 2 * v31 + 2;
    }
    else
    {
      v53 = 0;
      v54 = 0;
    }
    v32 = (_BYTE *)a2[1];
    if ( v32 && !*v32 )
    {
      v29 = g_dwDebugFlags;
      if ( (g_dwDebugFlags & 3) == 0 || (g_dwDebugFlags & 0x100000) == 0 )
        goto LABEL_54;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        2177,
        "SSFExecuteUrl",
        "\r\n"
        "  HSE_REQ_EXEC_UNICODE_URL[%p]: Parameter validation failure\r\n"
        "    Method is an empty string\r\n"
        "  <END>\r\n"
        "\r\n",
        this);
      goto LABEL_53;
    }
    v55 = a2[1];
    v33 = (_BYTE *)a2[2];
    if ( v33 && !*v33 )
    {
      v29 = g_dwDebugFlags;
      if ( (g_dwDebugFlags & 3) == 0 || (g_dwDebugFlags & 0x100000) == 0 )
        goto LABEL_54;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        2197,
        "SSFExecuteUrl",
        "\r\n"
        "  HSE_REQ_EXEC_UNICODE_URL[%p]: Parameter validation failure\r\n"
        "    ChildHeaders is an empty string\r\n"
        "  <END>\r\n"
        "\r\n",
        this);
      goto LABEL_53;
    }
    v34 = (_QWORD *)a2[3];
    v56 = a2[2];
    if ( v34 )
    {
      if ( !v34[1] )
      {
        v29 = g_dwDebugFlags;
        if ( (g_dwDebugFlags & 3) == 0 || (g_dwDebugFlags & 0x100000) == 0 )
          goto LABEL_54;
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
          2217,
          "SSFExecuteUrl",
          "\r\n"
          "  HSE_REQ_EXEC_UNICODE_URL[%p]: Parameter validation failure\r\n"
          "    Custom User Name: NULL\r\n"
          "  <END>\r\n"
          "\r\n",
          this);
        goto LABEL_53;
      }
      if ( !v34[2] )
      {
        v29 = g_dwDebugFlags;
        if ( (g_dwDebugFlags & 3) == 0 || (g_dwDebugFlags & 0x100000) == 0 )
          goto LABEL_54;
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
          2233,
          "SSFExecuteUrl",
          "\r\n"
          "  HSE_REQ_EXEC_UNICODE_URL[%p]: Parameter validation failure\r\n"
          "    Custom Auth Type: NULL\r\n"
          "  <END>\r\n"
          "\r\n",
          this);
        goto LABEL_53;
      }
      DWORD2(v49) = 1;
      *(_QWORD *)&v50 = v34[1];
      do
        ++v28;
      while ( *(_WORD *)(v34[1] + 2 * v28) );
      DWORD2(v50) = 2 * v28 + 2;
      v51 = v34[2];
      *(_QWORD *)&v49 = *v34;
      v57 = &v49;
    }
    else
    {
      v57 = 0;
    }
    v35 = (int *)a2[4];
    if ( v35 )
    {
      v36 = *v35;
      if ( *v35 && !*((_QWORD *)v35 + 1) )
      {
        v29 = g_dwDebugFlags;
        if ( (g_dwDebugFlags & 3) == 0 || (g_dwDebugFlags & 0x100000) == 0 )
          goto LABEL_54;
        v37 = "\r\n"
              "  HSE_REQ_EXEC_UNICODE_URL[%p]: Parameter validation failure\r\n"
              "    Available Entity bytes: %d\r\n"
              "    Available Entity Ptr: %p\r\n"
              "  <END>\r\n"
              "\r\n";
        v38 = 2272;
        goto LABEL_83;
      }
LABEL_84:
      LODWORD(v48) = v36;
      v39 = *((_QWORD *)v35 + 1);
      goto LABEL_118;
    }
  }
  else
  {
    if ( v27 )
    {
      if ( !*(_BYTE *)v27 )
      {
        v29 = g_dwDebugFlags;
        if ( (g_dwDebugFlags & 3) == 0 || (g_dwDebugFlags & 0x100000) == 0 )
          goto LABEL_54;
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
          2314,
          "SSFExecuteUrl",
          "\r\n  HSE_REQ_EXEC_URL[%p]: Parameter validation failure\r\n    URL is an empty string\r\n  <END>\r\n\r\n",
          this);
        goto LABEL_53;
      }
      v52 = 0;
      v40 = -1;
      v53 = v27;
      do
        ++v40;
      while ( *((_BYTE *)v27 + v40) );
      v54 = v40 + 1;
    }
    else
    {
      v53 = 0;
      v54 = 0;
    }
    v41 = (_BYTE *)a2[1];
    if ( v41 && !*v41 )
    {
      v29 = g_dwDebugFlags;
      if ( (g_dwDebugFlags & 3) == 0 || (g_dwDebugFlags & 0x100000) == 0 )
        goto LABEL_54;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        2342,
        "SSFExecuteUrl",
        "\r\n  HSE_REQ_EXEC_URL[%p]: Parameter validation failure\r\n    Method is an empty string\r\n  <END>\r\n\r\n",
        this);
      goto LABEL_53;
    }
    v55 = a2[1];
    v42 = (_BYTE *)a2[2];
    if ( v42 && !*v42 )
    {
      v29 = g_dwDebugFlags;
      if ( (g_dwDebugFlags & 3) == 0 || (g_dwDebugFlags & 0x100000) == 0 )
        goto LABEL_54;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        2362,
        "SSFExecuteUrl",
        "\r\n"
        "  HSE_REQ_EXEC_URL[%p]: Parameter validation failure\r\n"
        "    ChildHeaders is an empty string\r\n"
        "  <END>\r\n"
        "\r\n",
        this);
      goto LABEL_53;
    }
    v43 = (_QWORD *)a2[3];
    v56 = a2[2];
    if ( v43 )
    {
      if ( !v43[1] )
      {
        v29 = g_dwDebugFlags;
        if ( (g_dwDebugFlags & 3) == 0 || (g_dwDebugFlags & 0x100000) == 0 )
          goto LABEL_54;
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
          2382,
          "SSFExecuteUrl",
          "\r\n  HSE_REQ_EXEC_URL[%p]: Parameter validation failure\r\n    Custom User Name: NULL\r\n  <END>\r\n\r\n",
          this);
        goto LABEL_53;
      }
      if ( !v43[2] )
      {
        v29 = g_dwDebugFlags;
        if ( (g_dwDebugFlags & 3) == 0 || (g_dwDebugFlags & 0x100000) == 0 )
          goto LABEL_54;
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
          2398,
          "SSFExecuteUrl",
          "\r\n  HSE_REQ_EXEC_URL[%p]: Parameter validation failure\r\n    Custom Auth Type: NULL\r\n  <END>\r\n\r\n",
          this);
        goto LABEL_53;
      }
      DWORD2(v49) = 0;
      *(_QWORD *)&v50 = v43[1];
      do
        ++v28;
      while ( *(_BYTE *)(v43[1] + v28) );
      DWORD2(v50) = v28 + 1;
      v51 = v43[2];
      *(_QWORD *)&v49 = *v43;
      v57 = &v49;
    }
    else
    {
      v57 = 0;
    }
    v35 = (int *)a2[4];
    if ( v35 )
    {
      v36 = *v35;
      if ( *v35 && !*((_QWORD *)v35 + 1) )
      {
        v29 = g_dwDebugFlags;
        if ( (g_dwDebugFlags & 3) == 0 || (g_dwDebugFlags & 0x100000) == 0 )
          goto LABEL_54;
        v37 = "\r\n"
              "  HSE_REQ_EXEC_URL[%p]: Parameter validation failure\r\n"
              "    Available Entity Bytes: %d\r\n"
              "    Available Entity Ptr: %p\r\n"
              "  <END>\r\n"
              "\r\n";
        v38 = 2437;
LABEL_83:
        LODWORD(v44) = v36;
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
          v38,
          "SSFExecuteUrl",
          v37,
          this,
          v44,
          0);
        goto LABEL_53;
      }
      goto LABEL_84;
    }
  }
  LODWORD(v48) = *((_DWORD *)this + 35);
  v39 = *((_QWORD *)this + 18);
LABEL_118:
  *((_QWORD *)&v48 + 1) = v39;
  v58 = &v48;
  v59 = *((_DWORD *)a2 + 10);
  v30 = (*(__int64 (__fastcall **)(__int64, struct ISAPI_CONTEXT *, int *))(*(_QWORD *)v25 + 88LL))(v25, this, &v52);
  if ( v30 < 0 )
  {
    v29 = g_dwDebugFlags;
    goto LABEL_120;
  }
  return (unsigned int)v30;
}

```

## disassembly

```asm
0x180006970  mov     [rsp-8+arg_10], rbx
0x180006975  push    rbp
0x180006976  push    rsi
0x180006977  push    rdi
0x180006978  push    r12
0x18000697a  push    r13
0x18000697c  push    r14
0x18000697e  push    r15
0x180006980  lea     rbp, [rsp-240h]
0x180006988  sub     rsp, 340h
0x18000698f  mov     rax, cs:__security_cookie
0x180006996  xor     rax, rsp
0x180006999  mov     [rbp+270h+var_40], rax
0x1800069a0  xorps   xmm0, xmm0
0x1800069a3  xor     eax, eax
0x1800069a5  mov     r15d, r8d
0x1800069a8  mov     [rbp+270h+var_2D0], rax
0x1800069ac  mov     rbx, rdx
0x1800069af  mov     rdi, rcx
0x1800069b2  xor     edx, edx; Val
0x1800069b4  lea     rcx, [rbp+270h+var_2C0]; void *
0x1800069b8  lea     r8d, [rax+40h]; Size
0x1800069bc  movups  [rbp+270h+var_2F0], xmm0
0x1800069c0  movups  [rbp+270h+var_2E0], xmm0
0x1800069c4  movups  [rsp+370h+var_300], xmm0
0x1800069c9  call    memset_0
0x1800069ce  mov     eax, cs:g_dwDebugFlags
0x1800069d4  lea     r14, aSsfexecuteurl; "SSFExecuteUrl"
0x1800069db  xor     r12d, r12d
0x1800069de  lea     r13d, [r12+3]
0x1800069e3  bt      eax, 1Ah
0x1800069e7  jnb     loc_180006BE9
0x1800069ed  mov     esi, r12d
0x1800069f0  test    r15d, r15d
0x1800069f3  jz      short loc_180006A71
0x1800069f5  test    rbx, rbx
0x1800069f8  jz      short loc_180006A04
0x1800069fa  mov     rcx, [rbx+18h]
0x1800069fe  mov     rsi, [rbx+20h]
0x180006a02  jmp     short loc_180006A07
0x180006a04  mov     rcx, r12
0x180006a07  test    r13b, al
0x180006a0a  jz      loc_180006B32
0x180006a10  test    rcx, rcx
0x180006a13  jz      short loc_180006A22
0x180006a15  mov     rax, [rcx]
0x180006a18  mov     rdx, [rcx+8]
0x180006a1c  mov     r8, [rcx+10h]
0x180006a20  jmp     short loc_180006A2B
0x180006a22  mov     rax, r12
0x180006a25  mov     rdx, r12
0x180006a28  mov     r8, r12
0x180006a2b  test    rbx, rbx
0x180006a2e  jz      short loc_180006A44
0x180006a30  mov     r11d, [rbx+28h]
0x180006a34  mov     r14d, r11d
0x180006a37  mov     rcx, [rbx]
0x180006a3a  mov     r9, [rbx+8]
0x180006a3e  mov     r10, [rbx+10h]
0x180006a42  jmp     short loc_180006A53
0x180006a44  mov     rcx, r12
0x180006a47  mov     r9, r12
0x180006a4a  mov     r10, r12
0x180006a4d  mov     r11d, r12d
0x180006a50  mov     r14d, r12d
0x180006a53  mov     [rsp+370h+var_308], r8
0x180006a58  mov     r8d, 7CCh
0x180006a5e  mov     [rsp+370h+var_310], rdx
0x180006a63  mov     [rsp+370h+var_318], rax
0x180006a68  lea     rax, aHseReqExecUnic_6; "\r\n  HSE_REQ_EXEC_UNICODE_URL[%p]: Fun"...
0x180006a6f  jmp     short loc_180006AEB
0x180006a71  test    rbx, rbx
0x180006a74  jz      short loc_180006A80
0x180006a76  mov     rcx, [rbx+18h]
0x180006a7a  mov     rsi, [rbx+20h]
0x180006a7e  jmp     short loc_180006A83
0x180006a80  mov     rcx, r12
0x180006a83  test    r13b, al
0x180006a86  jz      loc_180006B32
0x180006a8c  test    rcx, rcx
0x180006a8f  jz      short loc_180006A9E
0x180006a91  mov     rax, [rcx]
0x180006a94  mov     rdx, [rcx+8]
0x180006a98  mov     r8, [rcx+10h]
0x180006a9c  jmp     short loc_180006AA7
0x180006a9e  mov     rax, r12
0x180006aa1  mov     rdx, r12
0x180006aa4  mov     r8, r12
0x180006aa7  test    rbx, rbx
0x180006aaa  jz      short loc_180006AC0
0x180006aac  mov     r11d, [rbx+28h]
0x180006ab0  mov     r14d, r11d
0x180006ab3  mov     rcx, [rbx]
0x180006ab6  mov     r9, [rbx+8]
0x180006aba  mov     r10, [rbx+10h]
0x180006abe  jmp     short loc_180006ACF
0x180006ac0  mov     rcx, r12
0x180006ac3  mov     r9, r12
0x180006ac6  mov     r10, r12
0x180006ac9  mov     r11d, r12d
0x180006acc  mov     r14d, r12d
0x180006acf  mov     [rsp+370h+var_308], r8
0x180006ad4  mov     r8d, 7ECh
0x180006ada  mov     [rsp+370h+var_310], rdx
0x180006adf  mov     [rsp+370h+var_318], rax
0x180006ae4  lea     rax, aHseReqExecUnic_5; "\r\n  HSE_REQ_EXEC_UNICODE_URL[%p]: Fun"...
0x180006aeb  mov     [rsp+370h+var_320], r14d
0x180006af0  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006af7  mov     [rsp+370h+var_328], r11d
0x180006afc  lea     r14, aSsfexecuteurl; "SSFExecuteUrl"
0x180006b03  mov     [rsp+370h+var_330], r10
0x180006b08  mov     [rsp+370h+var_338], r9
0x180006b0d  mov     r9, r14
0x180006b10  mov     [rsp+370h+var_340], rcx
0x180006b15  mov     rcx, cs:g_pDebug
0x180006b1c  mov     [rsp+370h+var_348], rdi
0x180006b21  mov     [rsp+370h+var_350], rax
0x180006b26  call    cs:__imp_PuDbgPrint
0x180006b2c  mov     eax, cs:g_dwDebugFlags
0x180006b32  bt      eax, 1Bh
0x180006b36  jnb     loc_180006BE9
0x180006b3c  test    rsi, rsi
0x180006b3f  jz      loc_180006BE9
0x180006b45  mov     r8d, 200h
0x180006b4b  lea     rdx, [rbp+270h+var_240]
0x180006b4f  lea     rcx, [rbp+270h+var_280]
0x180006b53  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180006b59  mov     r8d, [rsi]
0x180006b5c  lea     rcx, [rbp+270h+var_280]
0x180006b60  mov     rdx, [rsi+8]
0x180006b64  mov     eax, 0A0h
0x180006b69  cmp     r8d, eax
0x180006b6c  cmova   r8d, eax
0x180006b70  call    cs:__imp_?CopyBinary@STRA@@QEAAJPEAXK@Z; STRA::CopyBinary(void *,ulong)
0x180006b76  test    eax, eax
0x180006b78  jns     short loc_180006B8B
0x180006b7a  lea     rdx, word_180016DBA
0x180006b81  lea     rcx, [rbp+270h+var_280]
0x180006b85  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180006b8b  test    byte ptr cs:g_dwDebugFlags, r13b
0x180006b92  jz      short loc_180006BD9
0x180006b94  lea     rcx, [rbp+270h+var_280]
0x180006b98  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180006b9e  mov     rcx, cs:g_pDebug
0x180006ba5  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006bac  mov     [rsp+370h+var_338], rax
0x180006bb1  mov     r9, r14
0x180006bb4  mov     dword ptr [rsp+370h+var_340], 0A0h
0x180006bbc  lea     rax, aHseReqExecUrlP_7; "\r\n  HSE_REQ_EXEC_URL[%p]: Dump of up "...
0x180006bc3  mov     [rsp+370h+var_348], rdi
0x180006bc8  mov     r8d, 807h
0x180006bce  mov     [rsp+370h+var_350], rax
0x180006bd3  call    cs:__imp_PuDbgPrint
0x180006bd9  lea     rcx, [rbp+270h+var_280]
0x180006bdd  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180006be3  mov     eax, cs:g_dwDebugFlags
0x180006be9  mov     rsi, [rdi+0C0h]
0x180006bf0  test    rsi, rsi
0x180006bf3  jnz     short loc_180006C1C
0x180006bf5  test    r13b, al
0x180006bf8  setnz   cl
0x180006bfb  bt      eax, 14h
0x180006bff  setb    al
0x180006c02  test    al, cl
0x180006c04  jz      loc_180006CC2
0x180006c0a  lea     rax, aHseReqExecUrlP_8; "\r\n  HSE_REQ_EXEC_URL[%p]: Failed to g"...
0x180006c11  mov     r8d, 816h
0x180006c17  jmp     loc_180006CA1
0x180006c1c  test    rbx, rbx
0x180006c1f  jnz     short loc_180006C45
0x180006c21  test    r13b, al
0x180006c24  setnz   cl
0x180006c27  bt      eax, 14h
0x180006c2b  setb    al
0x180006c2e  test    al, cl
0x180006c30  jz      loc_180006CC2
0x180006c36  lea     rax, aHseReqExecUrlP_1; "\r\n  HSE_REQ_EXEC_URL[%p]: Parameter v"...
0x180006c3d  mov     r8d, 825h
0x180006c43  jmp     short loc_180006CA1
0x180006c45  cmp     [rdi+0E0h], r12
0x180006c4c  jnz     short loc_180006C6E
0x180006c4e  test    r13b, al
0x180006c51  setnz   cl
0x180006c54  bt      eax, 14h
0x180006c58  setb    al
0x180006c5b  test    al, cl
0x180006c5d  jz      short loc_180006CC2
0x180006c5f  lea     rax, aHseReqExecUrlP_3; "\r\n  HSE_REQ_EXEC_URL[%p]: Failed\r\n "...
0x180006c66  mov     r8d, 838h
0x180006c6c  jmp     short loc_180006CA1
0x180006c6e  mov     edx, r13d
0x180006c71  mov     rcx, rdi
0x180006c74  call    ?TryInitAsyncIo@ISAPI_CONTEXT@@QEAAHW4ASYNC_PENDING@@@Z; ISAPI_CONTEXT::TryInitAsyncIo(ASYNC_PENDING)
0x180006c79  test    eax, eax
0x180006c7b  jnz     short loc_180006CCC
0x180006c7d  mov     eax, cs:g_dwDebugFlags
0x180006c83  test    r13b, al
0x180006c86  setnz   cl
0x180006c89  bt      eax, 14h
0x180006c8d  setb    al
0x180006c90  test    al, cl
0x180006c92  jz      short loc_180006CC2
0x180006c94  lea     rax, aHseReqExecUrlP_5; "\r\n  HSE_REQ_EXEC_URL[%p]: Failed\r\n "...
0x180006c9b  mov     r8d, 847h
0x180006ca1  mov     rcx, cs:g_pDebug
0x180006ca8  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006caf  mov     [rsp+370h+var_348], rdi
0x180006cb4  mov     r9, r14
0x180006cb7  mov     [rsp+370h+var_350], rax
0x180006cbc  call    cs:__imp_PuDbgPrint
0x180006cc2  mov     eax, 80070057h
0x180006cc7  jmp     loc_18000719C
0x180006ccc  mov     rax, [rbx]
0x180006ccf  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180006cd3  test    r15d, r15d
0x180006cd6  jz      loc_180006F21
0x180006cdc  lea     r8d, [rcx+2]
0x180006ce0  test    rax, rax
0x180006ce3  jz      short loc_180006D64
0x180006ce5  cmp     [rax], r12w
0x180006ce9  jnz     short loc_180006D43
0x180006ceb  mov     r8d, cs:g_dwDebugFlags
0x180006cf2  test    r13b, r8b
0x180006cf5  setnz   cl
0x180006cf8  bt      r8d, 14h
0x180006cfd  setb    al
0x180006d00  test    al, cl
0x180006d02  jz      short loc_180006D39
0x180006d04  lea     rax, aHseReqExecUnic_1; "\r\n  HSE_REQ_EXEC_UNICODE_URL[%p]: Par"...
0x180006d0b  mov     r8d, 865h
0x180006d11  mov     rcx, cs:g_pDebug
0x180006d18  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006d1f  mov     [rsp+370h+var_348], rdi
0x180006d24  mov     r9, r14
0x180006d27  mov     [rsp+370h+var_350], rax
0x180006d2c  call    cs:__imp_PuDbgPrint
0x180006d32  mov     r8d, cs:g_dwDebugFlags
0x180006d39  mov     ebx, 80070057h
0x180006d3e  jmp     loc_180007147
0x180006d43  mov     [rbp+270h+var_2C0], r8d
0x180006d47  mov     rdx, rcx
0x180006d4a  mov     [rbp+270h+var_2B8], rax
0x180006d4e  inc     rdx
0x180006d51  cmp     [rax+rdx*2], r12w
0x180006d56  jnz     short loc_180006D4E
0x180006d58  lea     eax, ds:2[rdx*2]
0x180006d5f  mov     [rbp+270h+var_2B0], eax
0x180006d62  jmp     short loc_180006D6C
0x180006d64  mov     [rbp+270h+var_2B8], r12
0x180006d68  mov     [rbp+270h+var_2B0], r12d
0x180006d6c  mov     rax, [rbx+8]
0x180006d70  test    rax, rax
0x180006d73  jz      short loc_180006DA5
0x180006d75  cmp     [rax], r12b
0x180006d78  jnz     short loc_180006DA5
0x180006d7a  mov     r8d, cs:g_dwDebugFlags
0x180006d81  test    r13b, r8b
0x180006d84  setnz   cl
0x180006d87  bt      r8d, 14h
0x180006d8c  setb    al
0x180006d8f  test    al, cl
0x180006d91  jz      short loc_180006D39
0x180006d93  lea     rax, aHseReqExecUnic_7; "\r\n  HSE_REQ_EXEC_UNICODE_URL[%p]: Par"...
0x180006d9a  mov     r8d, 881h
0x180006da0  jmp     loc_180006D11
0x180006da5  mov     [rbp+270h+var_2A8], rax
0x180006da9  mov     rax, [rbx+10h]
0x180006dad  test    rax, rax
0x180006db0  jz      short loc_180006DE6
0x180006db2  cmp     [rax], r12b
0x180006db5  jnz     short loc_180006DE6
0x180006db7  mov     r8d, cs:g_dwDebugFlags
0x180006dbe  test    r13b, r8b
0x180006dc1  setnz   cl
0x180006dc4  bt      r8d, 14h
0x180006dc9  setb    al
0x180006dcc  test    al, cl
0x180006dce  jz      loc_180006D39
0x180006dd4  lea     rax, aHseReqExecUnic_3; "\r\n  HSE_REQ_EXEC_UNICODE_URL[%p]: Par"...
0x180006ddb  mov     r8d, 895h
0x180006de1  jmp     loc_180006D11
0x180006de6  mov     rdx, [rbx+18h]
0x180006dea  mov     [rbp+270h+var_2A0], rax
0x180006dee  test    rdx, rdx
0x180006df1  jz      loc_180006E9E
0x180006df7  cmp     [rdx+8], r12
0x180006dfb  jnz     short loc_180006E2C
0x180006dfd  mov     r8d, cs:g_dwDebugFlags
0x180006e04  test    r13b, r8b
0x180006e07  setnz   cl
0x180006e0a  bt      r8d, 14h
0x180006e0f  setb    al
0x180006e12  test    al, cl
0x180006e14  jz      loc_180006D39
0x180006e1a  lea     rax, aHseReqExecUnic; "\r\n  HSE_REQ_EXEC_UNICODE_URL[%p]: Par"...
0x180006e21  mov     r8d, 8A9h
0x180006e27  jmp     loc_180006D11
0x180006e2c  cmp     [rdx+10h], r12
0x180006e30  jnz     short loc_180006E61
0x180006e32  mov     r8d, cs:g_dwDebugFlags
  ... truncated ...
```
