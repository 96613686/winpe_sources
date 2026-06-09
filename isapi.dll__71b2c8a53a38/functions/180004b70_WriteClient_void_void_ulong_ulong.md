# WriteClient(void *,void *,ulong *,ulong)

- ea: `0x180004b70`
- end: `0x180004fea`
- name: `?WriteClient@@YAHPEAX0PEAKK@Z`
- size: `1146`
- prototype: `__int64 __fastcall(ISAPI_CONTEXT *this, void *, unsigned int *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800033a0`
- `0x180004b70`
- `0x180005e34`
- `0x180005ed0`
- `0x180005ff4`
- `0x1800124c0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004fbb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004fbb`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180004cb9`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180004cb9`
- `iisutil!PuDbgPrint` at `0x180004c47`
- `iisutil!PuDbgPrint` at `0x180004cf0`
- `iisutil!PuDbgPrint` at `0x180004daa`
- `iisutil!PuDbgPrint` at `0x180004e82`
- `iisutil!PuDbgPrint` at `0x180004f1b`
- `iisutil!PuDbgPrint` at `0x180004fb0`
- `iisutil!PuDbgPrint` at `0x180004c47`
- `iisutil!PuDbgPrint` at `0x180004cf0`
- `iisutil!PuDbgPrint` at `0x180004daa`
- `iisutil!PuDbgPrint` at `0x180004e82`
- `iisutil!PuDbgPrint` at `0x180004f1b`
- `iisutil!PuDbgPrint` at `0x180004fb0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180004cfb`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180004cfb`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180004c72`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180004c72`
- `iisutil!?CopyBinary@STRA@@QEAAJPEAXK@Z` at `0x180004c8f`
- `iisutil!?CopyBinary@STRA@@QEAAJPEAXK@Z` at `0x180004c8f`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180004ca5`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180004ca5`

## string_xrefs

- `0x180004baf`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\w3isapi.cxx`
- `0x180004da0`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\w3isapi.cxx`
- `0x180004e6e`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\w3isapi.cxx`
- `0x180004ee6`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\w3isapi.cxx`
- `0x180004c19`: `\n  WriteClient[%p]: Function Entry\n    Extension: %S\n    Bytes to Send: %d\n    Sync Flag: %s\n  <END>\n\n`
- `0x180004ba8`: `WriteClient`
- `0x180004cdc`: `\n  WriteClient[%p]: Dump of up to %d bytes of send buffer\n%s  <END>\n\n`
- `0x180004f89`: `\n  WriteClient[%p]: Parameter validation failed\n    Bytes to send: %d\n    Buffer Pointer: %p.\n    Returning FALSE, LastError=ERROR_INVALID_PARAMETER\n  <END>\n\n`
- `0x180004d4e`: `\n  WriteClient[%p]: Failed to get interface to server core\n    Returning FALSE, LastError=ERROR_INVALID_PARAMETER\n  <END>\n\n`
- `0x180004d82`: `\n  WriteClient[%p]: Bytes to send is zero\n    Returning TRUE\n  <END>\n\n`
- `0x180004e5a`: `\n  WriteClient[%p]: Failed to perform asynchronous send\n    Another async operation was already pending.\n    Returning FALSE, LastError=ERROR_INVALID_PARAMETER\n  <END>\n\n`
- `0x180004f0f`: `\n  WriteClient[%p]: Attempt to write failed\n`
- `0x180004f53`: `\n  WriteClient[%p]: Succeeded\n    Returning TRUE\n  <END>\n\n`

## pseudocode

```c
__int64 __fastcall WriteClient(ISAPI_CONTEXT *this, void *a2, unsigned int *a3, int a4)
{
  int v5; // r8d
  char v6; // bp
  const char *v9; // rcx
  const wchar_t *v10; // rdx
  unsigned int v11; // r8d
  const char *Str; // rax
  __int64 v13; // rsi
  __int64 v15; // r9
  int v16; // edi
  ISAPI_CONTEXT *v17; // rcx
  ISAPI_CONTEXT *v18; // rcx
  DWORD v19; // ecx
  void *v20; // [rsp+50h] [rbp-278h] BYREF
  _BYTE v21[56]; // [rsp+58h] [rbp-270h] BYREF
  char v22[512]; // [rsp+90h] [rbp-238h] BYREF

  v20 = 0;
  v5 = g_dwDebugFlags;
  v6 = a4;
  if ( (g_dwDebugFlags & 0x800000) != 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      if ( a4 )
      {
        v9 = "HSE_IO_SYNC";
        if ( (a4 & 1) == 0 )
          v9 = "HSE_IO_ASYNC";
      }
      else
      {
        v9 = "0";
      }
      if ( this )
        v10 = *(const wchar_t **)(*((_QWORD *)this + 25) + 24LL);
      else
        v10 = L"*";
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
        654,
        "WriteClient",
        "\r\n"
        "  WriteClient[%p]: Function Entry\r\n"
        "    Extension: %S\r\n"
        "    Bytes to Send: %d\r\n"
        "    Sync Flag: %s\r\n"
        "  <END>\r\n"
        "\r\n",
        this,
        v10,
        *a3,
        v9);
      v5 = g_dwDebugFlags;
    }
    if ( (v5 & 0x8000000) != 0 )
    {
      STRA::STRA((STRA *)v21, v22, 0x200u);
      v11 = *a3;
      if ( *a3 > 0xA0 )
        v11 = 160;
      if ( (int)STRA::CopyBinary((STRA *)v21, a2, v11) < 0 )
        STRA::Copy((STRA *)v21, (const char *)word_180016DBA);
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        Str = STRA::QueryStr((STRA *)v21);
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
          678,
          "WriteClient",
          "\r\n  WriteClient[%p]: Dump of up to %d bytes of send buffer\r\n%s  <END>\r\n\r\n",
          this,
          160,
          Str);
      }
      STRA::~STRA((STRA *)v21);
      v5 = g_dwDebugFlags;
    }
  }
  if ( !this || !a3 || *a3 && !a2 )
  {
    if ( (v5 & 3) != 0 && (v5 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
        701,
        "WriteClient",
        "\r\n"
        "  WriteClient[%p]: Parameter validation failed\r\n"
        "    Bytes to send: %d\r\n"
        "    Buffer Pointer: %p.\r\n"
        "    Returning FALSE, LastError=ERROR_INVALID_PARAMETER\r\n"
        "  <END>\r\n"
        "\r\n",
        this,
        (_DWORD)a3,
        a2);
    goto LABEL_48;
  }
  v13 = *((_QWORD *)this + 24);
  if ( v13 )
  {
    if ( !*a3 )
    {
      if ( (v5 & 0x800000) != 0 && (v5 & 3) != 0 && (v5 & 0x200000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
          750,
          "WriteClient",
          "\r\n  WriteClient[%p]: Bytes to send is zero\r\n    Returning TRUE\r\n  <END>\r\n\r\n",
          this);
      return 1;
    }
    if ( (v6 & 2) != 0 )
    {
      if ( *((_QWORD *)this + 28) )
      {
        if ( (unsigned int)ISAPI_CONTEXT::TryInitAsyncIo(this, 1) )
        {
          *((_DWORD *)this + 55) = *a3;
          v15 = *a3;
          v20 = 0;
          v16 = (*(__int64 (__fastcall **)(__int64, ISAPI_CONTEXT *, void *, __int64, int))(*(_QWORD *)v13 + 16LL))(
                  v13,
                  this,
                  a2,
                  v15,
                  2);
          ISAPI_CONTEXT::IsapiUndoRevertHack(v17, &v20);
          if ( v16 < 0 )
          {
            *((_QWORD *)this + 27) = 0;
            ISAPI_CONTEXT::DereferenceIsapiContext(this);
LABEL_41:
            if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
            {
              WIN32_FROM_HRESULT(v16);
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
                850,
                "WriteClient",
                "\r\n  WriteClient[%p]: Attempt to write failed\r\n",
                "    Returning FALSE, LastError=0x%08x ( %d )\r\n  <END>\r\n\r\n");
            }
            v19 = WIN32_FROM_HRESULT(v16);
            goto LABEL_49;
          }
LABEL_44:
          if ( (g_dwDebugFlags & 0x800000) != 0 && (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x200000) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
              866,
              "WriteClient",
              "\r\n  WriteClient[%p]: Succeeded\r\n    Returning TRUE\r\n  <END>\r\n\r\n",
              this);
          return 1;
        }
        v5 = g_dwDebugFlags;
      }
      if ( (v5 & 3) != 0 && (v5 & 0x100000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
          782,
          "WriteClient",
          "\r\n"
          "  WriteClient[%p]: Failed to perform asynchronous send\r\n"
          "    Another async operation was already pending.\r\n"
          "    Returning FALSE, LastError=ERROR_INVALID_PARAMETER\r\n"
          "  <END>\r\n"
          "\r\n",
          this);
      goto LABEL_48;
    }
    v20 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, void *))(*(_QWORD *)v13 + 16LL))(v13, 0, a2);
    ISAPI_CONTEXT::IsapiUndoRevertHack(v18, &v20);
    if ( v16 < 0 )
      goto LABEL_41;
    goto LABEL_44;
  }
  if ( (v5 & 3) != 0 && (v5 & 0x100000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
      723,
      "WriteClient",
      "\r\n"
      "  WriteClient[%p]: Failed to get interface to server core\r\n"
      "    Returning FALSE, LastError=ERROR_INVALID_PARAMETER\r\n"
      "  <END>\r\n"
      "\r\n",
      this);
LABEL_48:
  v19 = 87;
LABEL_49:
  SetLastError(v19);
  return 0;
}

```

## disassembly

```asm
0x180004b70  mov     [rsp+arg_18], rbx
0x180004b75  push    rbp
0x180004b76  push    rsi
0x180004b77  push    rdi
0x180004b78  push    r13
0x180004b7a  push    r14
0x180004b7c  sub     rsp, 2A0h
0x180004b83  mov     rax, cs:__security_cookie
0x180004b8a  xor     rax, rsp
0x180004b8d  mov     [rsp+2C8h+var_38], rax
0x180004b95  mov     rdi, r8
0x180004b98  mov     [rsp+2C8h+var_278], 0
0x180004ba1  mov     r8d, cs:g_dwDebugFlags
0x180004ba8  lea     r13, aWriteclient; "WriteClient"
0x180004baf  lea     rsi, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004bb6  mov     ebp, r9d
0x180004bb9  mov     r14, rdx
0x180004bbc  mov     rbx, rcx
0x180004bbf  bt      r8d, 17h
0x180004bc4  jnb     loc_180004D08
0x180004bca  test    r8b, 3
0x180004bce  jz      loc_180004C54
0x180004bd4  test    r9d, r9d
0x180004bd7  jz      short loc_180004BF1
0x180004bd9  test    bpl, 1
0x180004bdd  lea     rax, aHseIoAsync; "HSE_IO_ASYNC"
0x180004be4  lea     rcx, aHseIoSync; "HSE_IO_SYNC"
0x180004beb  cmovz   rcx, rax
0x180004bef  jmp     short loc_180004BF8
0x180004bf1  lea     rcx, a0; "0"
0x180004bf8  mov     r8d, [rdi]
0x180004bfb  test    rbx, rbx
0x180004bfe  jz      short loc_180004C0D
0x180004c00  mov     rax, [rbx+0C8h]
0x180004c07  mov     rdx, [rax+18h]
0x180004c0b  jmp     short loc_180004C14
0x180004c0d  lea     rdx, asc_180015F24; "*"
0x180004c14  mov     [rsp+2C8h+var_288], rcx
0x180004c19  lea     rax, aWriteclientPFu; "\r\n  WriteClient[%p]: Function Entry\r"...
0x180004c20  mov     rcx, cs:g_pDebug
0x180004c27  mov     r9, r13
0x180004c2a  mov     dword ptr [rsp+2C8h+var_290], r8d
0x180004c2f  mov     r8d, 28Eh
0x180004c35  mov     [rsp+2C8h+var_298], rdx
0x180004c3a  mov     rdx, rsi
0x180004c3d  mov     [rsp+2C8h+var_2A0], rbx
0x180004c42  mov     [rsp+2C8h+var_2A8], rax
0x180004c47  call    cs:__imp_PuDbgPrint
0x180004c4d  mov     r8d, cs:g_dwDebugFlags
0x180004c54  bt      r8d, 1Bh
0x180004c59  jnb     loc_180004D08
0x180004c5f  mov     r8d, 200h
0x180004c65  lea     rdx, [rsp+2C8h+var_238]
0x180004c6d  lea     rcx, [rsp+2C8h+var_270]
0x180004c72  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180004c78  mov     r8d, [rdi]
0x180004c7b  lea     rcx, [rsp+2C8h+var_270]
0x180004c80  mov     eax, 0A0h
0x180004c85  mov     rdx, r14
0x180004c88  cmp     r8d, eax
0x180004c8b  cmova   r8d, eax
0x180004c8f  call    cs:__imp_?CopyBinary@STRA@@QEAAJPEAXK@Z; STRA::CopyBinary(void *,ulong)
0x180004c95  test    eax, eax
0x180004c97  jns     short loc_180004CAB
0x180004c99  lea     rdx, word_180016DBA
0x180004ca0  lea     rcx, [rsp+2C8h+var_270]
0x180004ca5  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180004cab  test    byte ptr cs:g_dwDebugFlags, 3
0x180004cb2  jz      short loc_180004CF6
0x180004cb4  lea     rcx, [rsp+2C8h+var_270]
0x180004cb9  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180004cbf  mov     rcx, cs:g_pDebug
0x180004cc6  mov     r9, r13
0x180004cc9  mov     [rsp+2C8h+var_290], rax
0x180004cce  mov     r8d, 2A6h
0x180004cd4  mov     dword ptr [rsp+2C8h+var_298], 0A0h
0x180004cdc  lea     rax, aWriteclientPDu; "\r\n  WriteClient[%p]: Dump of up to %d"...
0x180004ce3  mov     [rsp+2C8h+var_2A0], rbx
0x180004ce8  mov     rdx, rsi
0x180004ceb  mov     [rsp+2C8h+var_2A8], rax
0x180004cf0  call    cs:__imp_PuDbgPrint
0x180004cf6  lea     rcx, [rsp+2C8h+var_270]
0x180004cfb  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180004d01  mov     r8d, cs:g_dwDebugFlags
0x180004d08  test    rbx, rbx
0x180004d0b  jz      loc_180004F6F
0x180004d11  test    rdi, rdi
0x180004d14  jz      loc_180004F6F
0x180004d1a  mov     r9d, [rdi]
0x180004d1d  test    r9d, r9d
0x180004d20  jz      short loc_180004D2B
0x180004d22  test    r14, r14
0x180004d25  jz      loc_180004F6F
0x180004d2b  mov     rsi, [rbx+0C0h]
0x180004d32  test    rsi, rsi
0x180004d35  jnz     short loc_180004D60
0x180004d37  test    r8b, 3
0x180004d3b  setnz   cl
0x180004d3e  bt      r8d, 14h
0x180004d43  setb    al
0x180004d46  test    al, cl
0x180004d48  jz      loc_180004FB6
0x180004d4e  lea     rax, aWriteclientPFa_0; "\r\n  WriteClient[%p]: Failed to get in"...
0x180004d55  mov     r8d, 2D3h
0x180004d5b  jmp     loc_180004E67
0x180004d60  test    r9d, r9d
0x180004d63  jnz     short loc_180004DBA
0x180004d65  test    r8b, 3
0x180004d69  setnz   dl
0x180004d6c  bt      r8d, 17h
0x180004d71  setb    al
0x180004d74  and     dl, al
0x180004d76  bt      r8d, 15h
0x180004d7b  setb    cl
0x180004d7e  test    cl, dl
0x180004d80  jz      short loc_180004DB0
0x180004d82  lea     rcx, aWriteclientPBy; "\r\n  WriteClient[%p]: Bytes to send is"...
0x180004d89  mov     [rsp+2C8h+var_2A0], rbx
0x180004d8e  mov     [rsp+2C8h+var_2A8], rcx
0x180004d93  mov     r8d, 2EEh
0x180004d99  mov     rcx, cs:g_pDebug
0x180004da0  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004da7  mov     r9, r13
0x180004daa  call    cs:__imp_PuDbgPrint
0x180004db0  mov     eax, 1
0x180004db5  jmp     loc_180004FC3
0x180004dba  test    bpl, 2
0x180004dbe  jz      loc_180004E8D
0x180004dc4  cmp     qword ptr [rbx+0E0h], 0
0x180004dcc  jz      short loc_180004E43
0x180004dce  mov     edx, 1
0x180004dd3  mov     rcx, rbx
0x180004dd6  call    ?TryInitAsyncIo@ISAPI_CONTEXT@@QEAAHW4ASYNC_PENDING@@@Z; ISAPI_CONTEXT::TryInitAsyncIo(ASYNC_PENDING)
0x180004ddb  test    eax, eax
0x180004ddd  jz      short loc_180004E3C
0x180004ddf  mov     eax, [rdi]
0x180004de1  mov     r8, r14
0x180004de4  mov     [rbx+0DCh], eax
0x180004dea  mov     rdx, rbx
0x180004ded  mov     r9d, [rdi]
0x180004df0  mov     rcx, rsi
0x180004df3  mov     [rsp+2C8h+var_278], 0
0x180004dfc  mov     rax, [rsi]
0x180004dff  mov     dword ptr [rsp+2C8h+var_2A8], 2
0x180004e07  mov     rax, [rax+10h]
0x180004e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e10  lea     rdx, [rsp+2C8h+var_278]; void **
0x180004e15  mov     edi, eax
0x180004e17  call    ?IsapiUndoRevertHack@ISAPI_CONTEXT@@QEAAXPEAPEAX@Z; ISAPI_CONTEXT::IsapiUndoRevertHack(void * *)
0x180004e1c  test    edi, edi
0x180004e1e  jns     loc_180004F2F
0x180004e24  mov     rcx, rbx; this
0x180004e27  mov     qword ptr [rbx+0D8h], 0
0x180004e32  call    ?DereferenceIsapiContext@ISAPI_CONTEXT@@QEAAXXZ; ISAPI_CONTEXT::DereferenceIsapiContext(void)
0x180004e37  jmp     loc_180004EC2
0x180004e3c  mov     r8d, cs:g_dwDebugFlags
0x180004e43  test    r8b, 3
0x180004e47  setnz   cl
0x180004e4a  bt      r8d, 14h
0x180004e4f  setb    al
0x180004e52  test    al, cl
0x180004e54  jz      loc_180004FB6
0x180004e5a  lea     rax, aWriteclientPFa; "\r\n  WriteClient[%p]: Failed to perfor"...
0x180004e61  mov     r8d, 30Eh
0x180004e67  mov     rcx, cs:g_pDebug
0x180004e6e  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004e75  mov     [rsp+2C8h+var_2A0], rbx
0x180004e7a  mov     r9, r13
0x180004e7d  mov     [rsp+2C8h+var_2A8], rax
0x180004e82  call    cs:__imp_PuDbgPrint
0x180004e88  jmp     loc_180004FB6
0x180004e8d  mov     [rsp+2C8h+var_278], 0
0x180004e96  mov     r8, r14
0x180004e99  mov     rax, [rsi]
0x180004e9c  xor     edx, edx
0x180004e9e  mov     rcx, rsi
0x180004ea1  mov     dword ptr [rsp+2C8h+var_2A8], 1
0x180004ea9  mov     rax, [rax+10h]
0x180004ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eb2  lea     rdx, [rsp+2C8h+var_278]; void **
0x180004eb7  mov     edi, eax
0x180004eb9  call    ?IsapiUndoRevertHack@ISAPI_CONTEXT@@QEAAXPEAPEAX@Z; ISAPI_CONTEXT::IsapiUndoRevertHack(void * *)
0x180004ebe  test    edi, edi
0x180004ec0  jns     short loc_180004F2F
0x180004ec2  mov     eax, cs:g_dwDebugFlags
0x180004ec8  test    al, 3
0x180004eca  setnz   cl
0x180004ecd  bt      eax, 14h
0x180004ed1  setb    al
0x180004ed4  test    al, cl
0x180004ed6  jz      short loc_180004F21
0x180004ed8  mov     ecx, edi; int
0x180004eda  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180004edf  mov     rcx, cs:g_pDebug
0x180004ee6  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004eed  mov     dword ptr [rsp+2C8h+var_288], eax
0x180004ef1  mov     r9, r13
0x180004ef4  mov     dword ptr [rsp+2C8h+var_290], edi
0x180004ef8  lea     rax, aReturningFalse; "    Returning FALSE, LastError=0x%08x ("...
0x180004eff  mov     [rsp+2C8h+var_298], rbx
0x180004f04  mov     r8d, 352h
0x180004f0a  mov     [rsp+2C8h+var_2A0], rax
0x180004f0f  lea     rax, aWriteclientPAt; "\r\n  WriteClient[%p]: Attempt to write"...
0x180004f16  mov     [rsp+2C8h+var_2A8], rax
0x180004f1b  call    cs:__imp_PuDbgPrint
0x180004f21  mov     ecx, edi; int
0x180004f23  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180004f28  mov     ecx, eax
0x180004f2a  jmp     loc_180004FBB
0x180004f2f  mov     ecx, cs:g_dwDebugFlags
0x180004f35  test    cl, 3
0x180004f38  setnz   dl
0x180004f3b  bt      ecx, 17h
0x180004f3f  setb    al
0x180004f42  and     dl, al
0x180004f44  bt      ecx, 15h
0x180004f48  setb    al
0x180004f4b  test    al, dl
0x180004f4d  jz      loc_180004DB0
0x180004f53  lea     rax, aWriteclientPSu; "\r\n  WriteClient[%p]: Succeeded\r\n   "...
0x180004f5a  mov     [rsp+2C8h+var_2A0], rbx
0x180004f5f  mov     [rsp+2C8h+var_2A8], rax
0x180004f64  mov     r8d, 362h
0x180004f6a  jmp     loc_180004D99
0x180004f6f  test    r8b, 3
0x180004f73  setnz   cl
0x180004f76  bt      r8d, 14h
0x180004f7b  setb    al
0x180004f7e  test    al, cl
0x180004f80  jz      short loc_180004FB6
0x180004f82  mov     rcx, cs:g_pDebug
0x180004f89  lea     rax, aWriteclientPPa; "\r\n  WriteClient[%p]: Parameter valida"...
0x180004f90  mov     [rsp+2C8h+var_290], r14
0x180004f95  mov     r9, r13
0x180004f98  mov     [rsp+2C8h+var_298], rdi
0x180004f9d  mov     r8d, 2BDh
0x180004fa3  mov     [rsp+2C8h+var_2A0], rbx
0x180004fa8  mov     rdx, rsi
0x180004fab  mov     [rsp+2C8h+var_2A8], rax
0x180004fb0  call    cs:__imp_PuDbgPrint
0x180004fb6  mov     ecx, 57h ; 'W'; dwErrCode
0x180004fbb  call    cs:__imp_SetLastError
0x180004fc1  xor     eax, eax
0x180004fc3  mov     rcx, [rsp+2C8h+var_38]
0x180004fcb  xor     rcx, rsp; StackCookie
0x180004fce  call    __security_check_cookie
0x180004fd3  mov     rbx, [rsp+2C8h+arg_18]
0x180004fdb  add     rsp, 2A0h
0x180004fe2  pop     r14
0x180004fe4  pop     r13
0x180004fe6  pop     rdi
0x180004fe7  pop     rsi
0x180004fe8  pop     rbp
0x180004fe9  retn
```
