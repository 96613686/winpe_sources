# SSFTransmitFile(ISAPI_CONTEXT *,_HSE_TF_INFO *)

- ea: `0x18000a1ec`
- end: `0x18000a818`
- name: `?SSFTransmitFile@@YAJPEAVISAPI_CONTEXT@@PEAU_HSE_TF_INFO@@@Z`
- size: `1580`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *this, struct _HSE_TF_INFO *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180005e34`
- `0x180005ff4`
- `0x18000a1ec`
- `0x1800124c0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a546`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18000a53c`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18000a53c`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000a39e`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000a3ab`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000a39e`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000a3ab`
- `iisutil!PuDbgPrint` at `0x18000a2e4`
- `iisutil!PuDbgPrint` at `0x18000a3ef`
- `iisutil!PuDbgPrint` at `0x18000a51f`
- `iisutil!PuDbgPrint` at `0x18000a5d6`
- `iisutil!PuDbgPrint` at `0x18000a72c`
- `iisutil!PuDbgPrint` at `0x18000a7e2`
- `iisutil!PuDbgPrint` at `0x18000a2e4`
- `iisutil!PuDbgPrint` at `0x18000a3ef`
- `iisutil!PuDbgPrint` at `0x18000a51f`
- `iisutil!PuDbgPrint` at `0x18000a5d6`
- `iisutil!PuDbgPrint` at `0x18000a72c`
- `iisutil!PuDbgPrint` at `0x18000a7e2`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000a403`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000a40d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000a417`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000a403`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000a40d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000a417`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000a25a`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000a311`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000a326`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000a25a`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000a311`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000a326`
- `iisutil!?CopyBinary@STRA@@QEAAJPEAXK@Z` at `0x18000a345`
- `iisutil!?CopyBinary@STRA@@QEAAJPEAXK@Z` at `0x18000a374`
- `iisutil!?CopyBinary@STRA@@QEAAJPEAXK@Z` at `0x18000a345`
- `iisutil!?CopyBinary@STRA@@QEAAJPEAXK@Z` at `0x18000a374`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000a35a`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000a38a`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000a35a`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000a38a`

## string_xrefs

- `0x18000a22e`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000a2bb`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000a3b8`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000a423`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000a71a`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000a2d3`: `\n  HSE_REQ_TRANSMIT_FILE[%p]: Function Entry\n    Completion Routine: %p\n    Context: %p\n    File Handle: %p\n    Status Code: '%s'\n    Bytes To Write: %d\n    Offset: %d\n  <END>\n\n`
- `0x18000a7b9`: `    File Handle: %p\n    Head: %p\n    Head Length: %d\n    Tail: %p\n    Tail Length: %d\n    Completion Routine: %p\n  <END>\n\n`
- `0x18000a4fb`: `\n  HSE_REQ_TRANSMIT_FILE[%p]: Failed\n    Another async operation is already pending.\n  <END>\n\n`
- `0x18000a5c5`: `\n  HSE_REQ_TRANSMIT_FILE[%p]: Parameter validation failure\n    File Size: %d\n    Offset: %d\n    Bytes to Write: %d\n  <END>\n\n`

## pseudocode

```c
__int64 __fastcall SSFTransmitFile(struct ISAPI_CONTEXT *this, struct _HSE_TF_INFO *a2)
{
  int v2; // eax
  int v5; // eax
  PFN_HSE_IO_COMPLETION pfnHseIO; // rax
  PVOID pContext; // rcx
  HANDLE hFile; // rdx
  const char *pszStatusCode; // r8
  DWORD BytesToWrite; // r9d
  DWORD Offset; // r10d
  DWORD HeadLength; // r8d
  DWORD TailLength; // r8d
  const char *Str; // rbx
  const char *v15; // rax
  __int64 v16; // r15
  HANDLE v17; // rcx
  signed int LastError; // eax
  unsigned int v19; // ebx
  union _LARGE_INTEGER v20; // r9
  union _LARGE_INTEGER v21; // rax
  int v22; // r8d
  PVOID v23; // rcx
  LONGLONG v24; // rax
  DWORD dwFlags; // edx
  LPCSTR v26; // rcx
  union _LARGE_INTEGER FileSize; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v29[56]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v30[56]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v31[56]; // [rsp+E8h] [rbp-18h] BYREF
  char v32[272]; // [rsp+120h] [rbp+20h] BYREF
  char v33[272]; // [rsp+230h] [rbp+130h] BYREF
  char v34[272]; // [rsp+340h] [rbp+240h] BYREF

  v2 = g_dwDebugFlags;
  FileSize.QuadPart = 0;
  if ( (g_dwDebugFlags & 0x4000000) != 0 )
  {
    STRA::STRA((STRA *)v31, v32, 0x104u);
    v5 = g_dwDebugFlags;
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      if ( a2 )
      {
        pfnHseIO = a2->pfnHseIO;
        pContext = a2->pContext;
        hFile = a2->hFile;
        pszStatusCode = a2->pszStatusCode;
        BytesToWrite = a2->BytesToWrite;
        Offset = a2->Offset;
      }
      else
      {
        pfnHseIO = 0;
        pContext = 0;
        hFile = 0;
        pszStatusCode = 0;
        BytesToWrite = 0;
        Offset = 0;
      }
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        1331,
        "SSFTransmitFile",
        "\r\n"
        "  HSE_REQ_TRANSMIT_FILE[%p]: Function Entry\r\n"
        "    Completion Routine: %p\r\n"
        "    Context: %p\r\n"
        "    File Handle: %p\r\n"
        "    Status Code: '%s'\r\n"
        "    Bytes To Write: %d\r\n"
        "    Offset: %d\r\n"
        "  <END>\r\n"
        "\r\n",
        this,
        pfnHseIO,
        pContext,
        hFile,
        pszStatusCode,
        BytesToWrite,
        Offset);
      v5 = g_dwDebugFlags;
    }
    if ( (v5 & 0x8000000) != 0 && a2 )
    {
      STRA::STRA((STRA *)v30, v33, 0x104u);
      STRA::STRA((STRA *)v29, v34, 0x104u);
      HeadLength = a2->HeadLength;
      if ( HeadLength > 0xA0 )
        HeadLength = 160;
      if ( (int)STRA::CopyBinary((STRA *)v30, a2->pHead, HeadLength) < 0 )
        STRA::Copy((STRA *)v30, (const char *)word_180016DBA);
      TailLength = a2->TailLength;
      if ( TailLength > 0xA0 )
        TailLength = 160;
      if ( (int)STRA::CopyBinary((STRA *)v29, a2->pTail, TailLength) < 0 )
        STRA::Copy((STRA *)v29, (const char *)word_180016DBA);
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        Str = STRA::QueryStr((STRA *)v29);
        v15 = STRA::QueryStr((STRA *)v30);
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
          1376,
          "SSFTransmitFile",
          "\r\n"
          "  HSE_REQ_TRANSMIT_FILE[%p]: Dump of up to %d bytes of head and tail data\r\n"
          "    Head Data:\r\n"
          "%s    Tail Data:\r\n"
          "%s  <END>\r\n",
          this,
          160,
          v15,
          Str);
      }
      STRA::~STRA((STRA *)v29);
      STRA::~STRA((STRA *)v30);
    }
    STRA::~STRA((STRA *)v31);
    v2 = g_dwDebugFlags;
  }
  v16 = *((_QWORD *)this + 24);
  if ( v16 )
  {
    if ( !a2 )
    {
      if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
          1420,
          "SSFTransmitFile",
          "\r\n"
          "  HSE_REQ_TRANSMIT_FILE[%p]: Parameter validation failure\r\n"
          "    Transmit File Info Ptr: NULL\r\n"
          "  <END>\r\n"
          "\r\n",
          this);
      return 2147942487LL;
    }
    if ( (a2->dwFlags & 2) == 0
      || a2->hFile == (HANDLE)-1LL
      || a2->HeadLength && !a2->pHead
      || a2->TailLength && !a2->pTail
      || !*((_QWORD *)this + 28) && !a2->pfnHseIO )
    {
      if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
          1453,
          "SSFTransmitFile",
          "\r\n  HSE_REQ_TRANSMIT_FILE[%p]: Parameter validation failure\r\n    %s\r\n",
          "    File Handle: %p\r\n"
          "    Head: %p\r\n"
          "    Head Length: %d\r\n"
          "    Tail: %p\r\n"
          "    Tail Length: %d\r\n"
          "    Completion Routine: %p\r\n"
          "  <END>\r\n"
          "\r\n",
          (const char *)this);
      return 2147942487LL;
    }
    if ( !(unsigned int)ISAPI_CONTEXT::TryInitAsyncIo(this, 1) )
    {
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
          1468,
          "SSFTransmitFile",
          "\r\n"
          "  HSE_REQ_TRANSMIT_FILE[%p]: Failed\r\n"
          "    Another async operation is already pending.\r\n"
          "  <END>\r\n"
          "\r\n",
          this);
      return 2147942487LL;
    }
    v17 = a2->hFile;
    if ( v17 )
    {
      if ( !GetFileSizeEx(v17, &FileSize) )
      {
        LastError = GetLastError();
        v19 = LastError;
        if ( LastError > 0 )
          v19 = (unsigned __int16)LastError | 0x80070000;
LABEL_71:
        if ( (v19 & 0x80000000) == 0 )
          return v19;
        v22 = g_dwDebugFlags;
LABEL_73:
        if ( (v22 & 3) != 0 && (v22 & 0x100000) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
            1623,
            "SSFTransmitFile",
            "\r\n  HSE_REQ_TRANSMIT_FILE[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
            this,
            v19);
        *((_QWORD *)this + 27) = 0;
        ISAPI_CONTEXT::DereferenceIsapiContext(this);
        return v19;
      }
      v20.QuadPart = a2->Offset;
      v21 = FileSize;
      if ( v20.QuadPart > FileSize.QuadPart
        || v20.LowPart && v20.QuadPart == FileSize.QuadPart
        || v20.LowPart + a2->BytesToWrite > FileSize.QuadPart )
      {
        v22 = g_dwDebugFlags;
        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
        {
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
            1511,
            "SSFTransmitFile",
            "\r\n"
            "  HSE_REQ_TRANSMIT_FILE[%p]: Parameter validation failure\r\n"
            "    File Size: %d\r\n"
            "    Offset: %d\r\n"
            "    Bytes to Write: %d\r\n"
            "  <END>\r\n"
            "\r\n",
            this,
            FileSize.LowPart,
            v20.LowPart,
            a2->BytesToWrite);
          v22 = g_dwDebugFlags;
        }
        v19 = -2147024809;
        goto LABEL_73;
      }
    }
    else
    {
      v21.QuadPart = 0;
      FileSize.QuadPart = 0;
    }
    if ( a2->pfnHseIO )
      *((_QWORD *)this + 28) = a2->pfnHseIO;
    v23 = a2->pContext;
    if ( v23 )
      *((_QWORD *)this + 29) = v23;
    if ( (a2->dwFlags & 4) != 0 )
    {
      *((_DWORD *)this + 63) = 0;
    }
    else if ( *((_DWORD *)this + 62) && !*((_DWORD *)this + 64) && (a2->dwFlags & 8) != 0 )
    {
      *((_DWORD *)this + 63) = 1;
    }
    if ( !*((_DWORD *)this + 63) )
      a2->dwFlags |= 4u;
    if ( (a2->dwFlags & 8) != 0 )
      *((_DWORD *)this + 64) = 1;
    if ( a2->BytesToWrite )
      v24 = a2->BytesToWrite;
    else
      v24 = v21.QuadPart - a2->Offset;
    *((_DWORD *)this + 55) = v24;
    dwFlags = a2->dwFlags;
    if ( (dwFlags & 8) != 0 )
      v26 = a2->pszStatusCode;
    else
      v26 = 0;
    v19 = (*(__int64 (__fastcall **)(__int64, struct ISAPI_CONTEXT *, HANDLE, _QWORD, LONGLONG, LPCSTR, PVOID, DWORD, PVOID, DWORD, DWORD))(*(_QWORD *)v16 + 48LL))(
            v16,
            this,
            a2->hFile,
            a2->Offset,
            v24,
            v26,
            a2->pHead,
            a2->HeadLength,
            a2->pTail,
            a2->TailLength,
            dwFlags);
    goto LABEL_71;
  }
  if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      1391,
      "SSFTransmitFile",
      "\r\n  HSE_REQ_TRANSMIT_FILE[%p]: Failed to get interface to server core\r\n  <END>\r\n\r\n",
      this);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000a1ec  mov     [rsp-8+arg_10], rbx
0x18000a1f1  mov     [rsp-8+arg_18], rsi
0x18000a1f6  push    rbp
0x18000a1f7  push    rdi
0x18000a1f8  push    r12
0x18000a1fa  push    r14
0x18000a1fc  push    r15
0x18000a1fe  lea     rbp, [rsp-360h]
0x18000a206  sub     rsp, 460h
0x18000a20d  mov     rax, cs:__security_cookie
0x18000a214  xor     rax, rsp
0x18000a217  mov     [rbp+380h+var_30], rax
0x18000a21e  mov     eax, cs:g_dwDebugFlags
0x18000a224  lea     r14, aSsftransmitfil; "SSFTransmitFile"
0x18000a22b  xor     r12d, r12d
0x18000a22e  lea     rbx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000a235  mov     qword ptr [rsp+480h+FileSize], r12
0x18000a23a  mov     rdi, rdx
0x18000a23d  mov     rsi, rcx
0x18000a240  bt      eax, 1Ah
0x18000a244  jnb     loc_18000A42A
0x18000a24a  mov     ebx, 104h
0x18000a24f  lea     rdx, [rbp+380h+var_360]
0x18000a253  mov     r8d, ebx
0x18000a256  lea     rcx, [rbp+380h+var_398]
0x18000a25a  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000a260  mov     eax, cs:g_dwDebugFlags
0x18000a266  test    al, 3
0x18000a268  jz      loc_18000A2F0
0x18000a26e  test    rdi, rdi
0x18000a271  jz      short loc_18000A28C
0x18000a273  mov     rax, [rdi]
0x18000a276  mov     rcx, [rdi+8]
0x18000a27a  mov     rdx, [rdi+10h]
0x18000a27e  mov     r8, [rdi+18h]
0x18000a282  mov     r9d, [rdi+20h]
0x18000a286  mov     r10d, [rdi+24h]
0x18000a28a  jmp     short loc_18000A29E
0x18000a28c  mov     rax, r12
0x18000a28f  mov     rcx, r12
0x18000a292  mov     rdx, r12
0x18000a295  mov     r8, r12
0x18000a298  mov     r9d, r12d
0x18000a29b  mov     r10d, r12d
0x18000a29e  mov     dword ptr [rsp+480h+var_428], r10d
0x18000a2a3  mov     [rsp+480h+var_430], r9d
0x18000a2a8  mov     r9, r14
0x18000a2ab  mov     [rsp+480h+var_438], r8
0x18000a2b0  mov     r8d, 533h
0x18000a2b6  mov     [rsp+480h+var_440], rdx
0x18000a2bb  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000a2c2  mov     [rsp+480h+var_448], rcx
0x18000a2c7  mov     rcx, cs:g_pDebug
0x18000a2ce  mov     [rsp+480h+var_450], rax
0x18000a2d3  lea     rax, aHseReqTransmit_4; "\r\n  HSE_REQ_TRANSMIT_FILE[%p]: Functi"...
0x18000a2da  mov     [rsp+480h+var_458], rsi
0x18000a2df  mov     [rsp+480h+var_460], rax
0x18000a2e4  call    cs:__imp_PuDbgPrint
0x18000a2ea  mov     eax, cs:g_dwDebugFlags
0x18000a2f0  bt      eax, 1Bh
0x18000a2f4  jnb     loc_18000A413
0x18000a2fa  test    rdi, rdi
0x18000a2fd  jz      loc_18000A413
0x18000a303  mov     r8d, ebx
0x18000a306  lea     rdx, [rbp+380h+var_250]
0x18000a30d  lea     rcx, [rbp+380h+var_3D0]
0x18000a311  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000a317  mov     r8d, ebx
0x18000a31a  lea     rdx, [rbp+380h+var_140]
0x18000a321  lea     rcx, [rsp+480h+var_408]
0x18000a326  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000a32c  mov     r8d, [rdi+30h]
0x18000a330  lea     rcx, [rbp+380h+var_3D0]
0x18000a334  mov     rdx, [rdi+28h]
0x18000a338  mov     r14d, 0A0h
0x18000a33e  cmp     r8d, r14d
0x18000a341  cmova   r8d, r14d
0x18000a345  call    cs:__imp_?CopyBinary@STRA@@QEAAJPEAXK@Z; STRA::CopyBinary(void *,ulong)
0x18000a34b  test    eax, eax
0x18000a34d  jns     short loc_18000A360
0x18000a34f  lea     rdx, word_180016DBA
0x18000a356  lea     rcx, [rbp+380h+var_3D0]
0x18000a35a  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x18000a360  mov     r8d, [rdi+40h]
0x18000a364  lea     rcx, [rsp+480h+var_408]
0x18000a369  mov     rdx, [rdi+38h]
0x18000a36d  cmp     r8d, r14d
0x18000a370  cmova   r8d, r14d
0x18000a374  call    cs:__imp_?CopyBinary@STRA@@QEAAJPEAXK@Z; STRA::CopyBinary(void *,ulong)
0x18000a37a  test    eax, eax
0x18000a37c  jns     short loc_18000A390
0x18000a37e  lea     rdx, word_180016DBA
0x18000a385  lea     rcx, [rsp+480h+var_408]
0x18000a38a  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x18000a390  test    byte ptr cs:g_dwDebugFlags, 3
0x18000a397  jz      short loc_18000A3F7
0x18000a399  lea     rcx, [rsp+480h+var_408]
0x18000a39e  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18000a3a4  lea     rcx, [rbp+380h+var_3D0]
0x18000a3a8  mov     rbx, rax
0x18000a3ab  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18000a3b1  mov     rcx, cs:g_pDebug
0x18000a3b8  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000a3bf  mov     [rsp+480h+var_440], rbx
0x18000a3c4  mov     r8d, 560h
0x18000a3ca  mov     [rsp+480h+var_448], rax
0x18000a3cf  lea     rax, aHseReqTransmit_0; "\r\n  HSE_REQ_TRANSMIT_FILE[%p]: Dump o"...
0x18000a3d6  mov     dword ptr [rsp+480h+var_450], r14d
0x18000a3db  lea     r14, aSsftransmitfil; "SSFTransmitFile"
0x18000a3e2  mov     r9, r14
0x18000a3e5  mov     [rsp+480h+var_458], rsi
0x18000a3ea  mov     [rsp+480h+var_460], rax
0x18000a3ef  call    cs:__imp_PuDbgPrint
0x18000a3f5  jmp     short loc_18000A3FE
0x18000a3f7  lea     r14, aSsftransmitfil; "SSFTransmitFile"
0x18000a3fe  lea     rcx, [rsp+480h+var_408]
0x18000a403  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000a409  lea     rcx, [rbp+380h+var_3D0]
0x18000a40d  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000a413  lea     rcx, [rbp+380h+var_398]
0x18000a417  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000a41d  mov     eax, cs:g_dwDebugFlags
0x18000a423  lea     rbx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000a42a  mov     r15, [rsi+0C0h]
0x18000a431  test    r15, r15
0x18000a434  jnz     short loc_18000A45C
0x18000a436  test    al, 3
0x18000a438  setnz   cl
0x18000a43b  bt      eax, 14h
0x18000a43f  setb    al
0x18000a442  test    al, cl
0x18000a444  jz      loc_18000A7E8
0x18000a44a  lea     rax, aHseReqTransmit_5; "\r\n  HSE_REQ_TRANSMIT_FILE[%p]: Failed"...
0x18000a451  mov     r8d, 56Fh
0x18000a457  jmp     loc_18000A508
0x18000a45c  test    rdi, rdi
0x18000a45f  jnz     short loc_18000A487
0x18000a461  test    al, 3
0x18000a463  setnz   cl
0x18000a466  bt      eax, 14h
0x18000a46a  setb    al
0x18000a46d  test    al, cl
0x18000a46f  jz      loc_18000A7E8
0x18000a475  lea     rax, aHseReqTransmit_7; "\r\n  HSE_REQ_TRANSMIT_FILE[%p]: Parame"...
0x18000a47c  mov     r8d, 58Ch
0x18000a482  jmp     loc_18000A508
0x18000a487  mov     edx, [rdi+44h]
0x18000a48a  and     edx, 2
0x18000a48d  jz      loc_18000A748
0x18000a493  cmp     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x18000a498  jz      loc_18000A748
0x18000a49e  cmp     [rdi+30h], r12d
0x18000a4a2  jz      short loc_18000A4AE
0x18000a4a4  cmp     [rdi+28h], r12
0x18000a4a8  jz      loc_18000A748
0x18000a4ae  cmp     [rdi+40h], r12d
0x18000a4b2  jz      short loc_18000A4BE
0x18000a4b4  cmp     [rdi+38h], r12
0x18000a4b8  jz      loc_18000A748
0x18000a4be  cmp     [rsi+0E0h], r12
0x18000a4c5  jnz     short loc_18000A4D0
0x18000a4c7  cmp     [rdi], r12
0x18000a4ca  jz      loc_18000A748
0x18000a4d0  mov     edx, 1
0x18000a4d5  mov     rcx, rsi
0x18000a4d8  call    ?TryInitAsyncIo@ISAPI_CONTEXT@@QEAAHW4ASYNC_PENDING@@@Z; ISAPI_CONTEXT::TryInitAsyncIo(ASYNC_PENDING)
0x18000a4dd  test    eax, eax
0x18000a4df  jnz     short loc_18000A52A
0x18000a4e1  mov     eax, cs:g_dwDebugFlags
0x18000a4e7  test    al, 3
0x18000a4e9  setnz   cl
0x18000a4ec  bt      eax, 14h
0x18000a4f0  setb    al
0x18000a4f3  test    al, cl
0x18000a4f5  jz      loc_18000A7E8
0x18000a4fb  lea     rax, aHseReqTransmit_2; "\r\n  HSE_REQ_TRANSMIT_FILE[%p]: Failed"...
0x18000a502  mov     r8d, 5BCh
0x18000a508  mov     rcx, cs:g_pDebug
0x18000a50f  mov     r9, r14
0x18000a512  mov     [rsp+480h+var_458], rsi
0x18000a517  mov     rdx, rbx
0x18000a51a  mov     [rsp+480h+var_460], rax
0x18000a51f  call    cs:__imp_PuDbgPrint
0x18000a525  jmp     loc_18000A7E8
0x18000a52a  mov     rcx, [rdi+10h]; hFile
0x18000a52e  test    rcx, rcx
0x18000a531  jz      loc_18000A5ED
0x18000a537  lea     rdx, [rsp+480h+FileSize]; lpFileSize
0x18000a53c  call    cs:__imp_GetFileSizeEx
0x18000a542  test    eax, eax
0x18000a544  jnz     short loc_18000A564
0x18000a546  call    cs:__imp_GetLastError
0x18000a54c  mov     ebx, eax
0x18000a54e  test    eax, eax
0x18000a550  jle     loc_18000A6DE
0x18000a556  movzx   ebx, ax
0x18000a559  or      ebx, 80070000h
0x18000a55f  jmp     loc_18000A6DE
0x18000a564  mov     r9d, [rdi+24h]
0x18000a568  mov     rax, qword ptr [rsp+480h+FileSize]
0x18000a56d  cmp     r9, rax
0x18000a570  jg      short loc_18000A587
0x18000a572  test    r9d, r9d
0x18000a575  jz      short loc_18000A57C
0x18000a577  cmp     r9, rax
0x18000a57a  jz      short loc_18000A587
0x18000a57c  mov     ecx, [rdi+20h]
0x18000a57f  add     ecx, r9d
0x18000a582  cmp     rcx, rax
0x18000a585  jle     short loc_18000A5F5
0x18000a587  mov     r8d, cs:g_dwDebugFlags
0x18000a58e  test    r8b, 3
0x18000a592  setnz   dl
0x18000a595  bt      r8d, 14h
0x18000a59a  setb    cl
0x18000a59d  test    cl, dl
0x18000a59f  jz      short loc_18000A5E3
0x18000a5a1  mov     ecx, [rdi+20h]
0x18000a5a4  mov     r8d, 5E7h
0x18000a5aa  mov     dword ptr [rsp+480h+var_440], ecx
0x18000a5ae  mov     rdx, rbx
0x18000a5b1  mov     rcx, cs:g_pDebug
0x18000a5b8  mov     dword ptr [rsp+480h+var_448], r9d
0x18000a5bd  mov     r9, r14
0x18000a5c0  mov     [rsp+480h+var_450], rax
0x18000a5c5  lea     rax, aHseReqTransmit_1; "\r\n  HSE_REQ_TRANSMIT_FILE[%p]: Parame"...
0x18000a5cc  mov     [rsp+480h+var_458], rsi
0x18000a5d1  mov     [rsp+480h+var_460], rax
0x18000a5d6  call    cs:__imp_PuDbgPrint
0x18000a5dc  mov     r8d, cs:g_dwDebugFlags
0x18000a5e3  mov     ebx, 80070057h
0x18000a5e8  jmp     loc_18000A6E9
0x18000a5ed  mov     rax, r12
0x18000a5f0  mov     qword ptr [rsp+480h+FileSize], rax
0x18000a5f5  mov     rcx, [rdi]
0x18000a5f8  test    rcx, rcx
0x18000a5fb  jz      short loc_18000A604
0x18000a5fd  mov     [rsi+0E0h], rcx
0x18000a604  mov     rcx, [rdi+8]
0x18000a608  test    rcx, rcx
0x18000a60b  jz      short loc_18000A614
0x18000a60d  mov     [rsi+0E8h], rcx
0x18000a614  test    byte ptr [rdi+44h], 4
0x18000a618  mov     r9b, 8
0x18000a61b  jz      short loc_18000A626
0x18000a61d  mov     [rsi+0FCh], r12d
0x18000a624  jmp     short loc_18000A648
0x18000a626  cmp     [rsi+0F8h], r12d
0x18000a62d  jz      short loc_18000A648
0x18000a62f  cmp     [rsi+100h], r12d
0x18000a636  jnz     short loc_18000A648
0x18000a638  test    [rdi+44h], r9b
0x18000a63c  jz      short loc_18000A648
0x18000a63e  mov     dword ptr [rsi+0FCh], 1
0x18000a648  cmp     [rsi+0FCh], r12d
0x18000a64f  jnz     short loc_18000A655
0x18000a651  or      dword ptr [rdi+44h], 4
0x18000a655  test    [rdi+44h], r9b
0x18000a659  jz      short loc_18000A665
0x18000a65b  mov     dword ptr [rsi+100h], 1
0x18000a665  cmp     [rdi+20h], r12d
0x18000a669  jz      short loc_18000A670
0x18000a66b  mov     eax, [rdi+20h]
0x18000a66e  jmp     short loc_18000A676
0x18000a670  mov     ecx, [rdi+24h]
0x18000a673  sub     rax, rcx
0x18000a676  mov     [rsi+0DCh], eax
0x18000a67c  mov     rcx, [r15]
0x18000a67f  mov     edx, [rdi+44h]
0x18000a682  mov     r8d, [rdi+40h]
0x18000a686  mov     r10, [rdi+38h]
0x18000a68a  mov     r14, [rcx+30h]
0x18000a68e  mov     r11d, [rdi+30h]
0x18000a692  mov     rbx, [rdi+28h]
0x18000a696  test    r9b, dl
0x18000a699  jz      short loc_18000A6A1
0x18000a69b  mov     rcx, [rdi+18h]
0x18000a69f  jmp     short loc_18000A6A4
0x18000a6a1  mov     rcx, r12
0x18000a6a4  mov     r9d, [rdi+24h]
0x18000a6a8  mov     [rsp+480h+var_430], edx
0x18000a6ac  mov     rdx, rsi
0x18000a6af  mov     dword ptr [rsp+480h+var_438], r8d
0x18000a6b4  mov     r8, [rdi+10h]
0x18000a6b8  mov     [rsp+480h+var_440], r10
0x18000a6bd  mov     dword ptr [rsp+480h+var_448], r11d
0x18000a6c2  mov     [rsp+480h+var_450], rbx
0x18000a6c7  mov     [rsp+480h+var_458], rcx
0x18000a6cc  mov     rcx, r15
0x18000a6cf  mov     [rsp+480h+var_460], rax
0x18000a6d4  mov     rax, r14
0x18000a6d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6dc  mov     ebx, eax
0x18000a6de  test    ebx, ebx
0x18000a6e0  jns     short loc_18000A741
0x18000a6e2  mov     r8d, cs:g_dwDebugFlags
0x18000a6e9  test    r8b, 3
0x18000a6ed  setnz   dl
0x18000a6f0  bt      r8d, 14h
0x18000a6f5  setb    cl
  ... truncated ...
```
