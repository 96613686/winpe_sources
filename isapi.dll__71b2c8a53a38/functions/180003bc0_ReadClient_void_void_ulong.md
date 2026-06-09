# ReadClient(void *,void *,ulong *)

- ea: `0x180003bc0`
- end: `0x180003eea`
- name: `?ReadClient@@YAHPEAX0PEAK@Z`
- size: `810`
- prototype: `__int64 __fastcall(_QWORD *, void *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800033a0`
- `0x180003bc0`
- `0x180005ed0`
- `0x1800124c0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003ebb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003ebb`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003e15`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003e15`
- `iisutil!PuDbgPrint` at `0x180003c49`
- `iisutil!PuDbgPrint` at `0x180003cc0`
- `iisutil!PuDbgPrint` at `0x180003d51`
- `iisutil!PuDbgPrint` at `0x180003da5`
- `iisutil!PuDbgPrint` at `0x180003e48`
- `iisutil!PuDbgPrint` at `0x180003eb0`
- `iisutil!PuDbgPrint` at `0x180003c49`
- `iisutil!PuDbgPrint` at `0x180003cc0`
- `iisutil!PuDbgPrint` at `0x180003d51`
- `iisutil!PuDbgPrint` at `0x180003da5`
- `iisutil!PuDbgPrint` at `0x180003e48`
- `iisutil!PuDbgPrint` at `0x180003eb0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003e53`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003e53`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180003dce`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180003dce`
- `iisutil!?CopyBinary@STRA@@QEAAJPEAXK@Z` at `0x180003deb`
- `iisutil!?CopyBinary@STRA@@QEAAJPEAXK@Z` at `0x180003deb`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180003e01`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180003e01`

## string_xrefs

- `0x180003c03`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\w3isapi.cxx`
- `0x180003c33`: `\n  ReadClient[%p]: Function Entry\n    Bytes to Read: %d\n  <END>\n\n`
- `0x180003bf8`: `ReadClient`
- `0x180003e9f`: `\n  ReadClient[%p]: Parameter validation failure\n    Bytes to Read Ptr: %p\n    Bytes to Read: %d\n    Buffer Ptr: %p\n    Returning FALSE, LastError=ERROR_INVALID_PARAMETER\n  <END>\n\n`
- `0x180003ca3`: `\n  ReadClient[%p]: Failed to get interface to server core\n    Returning FALSE, LastError=ERROR_INVALID_PARAMETER\n  <END>\n\n`
- `0x180003d3d`: `\n  ReadClient[%p]: Failed\n    Returning FALSE, LastError=0x%08x (%d)\n  <END>\n\n`
- `0x180003d94`: `\n  ReadClient[%p]: Succeeded\n    Bytes Read: %d\n    Returning TRUE\n  <END>\n\n`
- `0x180003e20`: `\n  ReadClient[%p]: Dump of up to %d bytes of receive buffer\n%s  <END>\n\n`

## pseudocode

```c
__int64 __fastcall ReadClient(_QWORD *a1, void *a2, unsigned int *a3)
{
  int v4; // r8d
  __int64 v7; // rcx
  int v8; // esi
  ISAPI_CONTEXT *v9; // rcx
  int v10; // ecx
  unsigned int v11; // eax
  DWORD v12; // ecx
  unsigned int v13; // r8d
  const char *Str; // rax
  int v16; // eax
  void *v17; // [rsp+50h] [rbp-278h] BYREF
  _BYTE v18[56]; // [rsp+58h] [rbp-270h] BYREF
  char v19[512]; // [rsp+90h] [rbp-238h] BYREF

  v17 = 0;
  v4 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x400000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
      917,
      "ReadClient",
      "\r\n  ReadClient[%p]: Function Entry\r\n    Bytes to Read: %d\r\n  <END>\r\n\r\n",
      a1,
      *a3);
    v4 = g_dwDebugFlags;
  }
  if ( !a1 || !a3 || *a3 && !a2 )
  {
    if ( (v4 & 3) != 0 && (v4 & 0x100000) != 0 )
    {
      if ( a3 )
        v16 = *a3;
      else
        v16 = 0;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
        941,
        "ReadClient",
        "\r\n"
        "  ReadClient[%p]: Parameter validation failure\r\n"
        "    Bytes to Read Ptr: %p\r\n"
        "    Bytes to Read: %d\r\n"
        "    Buffer Ptr: %p\r\n"
        "    Returning FALSE, LastError=ERROR_INVALID_PARAMETER\r\n"
        "  <END>\r\n"
        "\r\n",
        a1,
        a3,
        v16,
        a2);
    }
    goto LABEL_31;
  }
  v7 = a1[24];
  if ( !v7 )
  {
    if ( (v4 & 3) != 0 && (v4 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
        959,
        "ReadClient",
        "\r\n"
        "  ReadClient[%p]: Failed to get interface to server core\r\n"
        "    Returning FALSE, LastError=ERROR_INVALID_PARAMETER\r\n"
        "  <END>\r\n"
        "\r\n",
        a1);
LABEL_31:
    v12 = 87;
LABEL_32:
    SetLastError(v12);
    return 0;
  }
  v17 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, void *))(*(_QWORD *)v7 + 8LL))(v7, 0, a2);
  ISAPI_CONTEXT::IsapiUndoRevertHack(v9, &v17);
  v10 = g_dwDebugFlags;
  if ( v8 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
    {
      v11 = WIN32_FROM_HRESULT(v8);
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
        991,
        "ReadClient",
        "\r\n  ReadClient[%p]: Failed\r\n    Returning FALSE, LastError=0x%08x (%d)\r\n  <END>\r\n\r\n",
        a1,
        v8,
        v11);
    }
    v12 = WIN32_FROM_HRESULT(v8);
    goto LABEL_32;
  }
  if ( (g_dwDebugFlags & 0x600000) == 0x600000 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
        1009,
        "ReadClient",
        "\r\n  ReadClient[%p]: Succeeded\r\n    Bytes Read: %d\r\n    Returning TRUE\r\n  <END>\r\n\r\n",
        a1,
        *a3);
      v10 = g_dwDebugFlags;
    }
    if ( (v10 & 0x8000000) != 0 )
    {
      STRA::STRA((STRA *)v18, v19, 0x200u);
      v13 = *a3;
      if ( *a3 > 0xA0 )
        v13 = 160;
      if ( (int)STRA::CopyBinary((STRA *)v18, a2, v13) < 0 )
        STRA::Copy((STRA *)v18, (const char *)word_180016DBA);
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        Str = STRA::QueryStr((STRA *)v18);
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
          1033,
          "ReadClient",
          "\r\n  ReadClient[%p]: Dump of up to %d bytes of receive buffer\r\n%s  <END>\r\n\r\n",
          a1,
          160,
          Str);
      }
      STRA::~STRA((STRA *)v18);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180003bc0  mov     [rsp+arg_18], rbx
0x180003bc5  push    rbp
0x180003bc6  push    rsi
0x180003bc7  push    rdi
0x180003bc8  push    r12
0x180003bca  push    r15
0x180003bcc  sub     rsp, 2A0h
0x180003bd3  mov     rax, cs:__security_cookie
0x180003bda  xor     rax, rsp
0x180003bdd  mov     [rsp+2C8h+var_38], rax
0x180003be5  mov     rbx, r8
0x180003be8  mov     [rsp+2C8h+var_278], 0
0x180003bf1  mov     r8d, cs:g_dwDebugFlags
0x180003bf8  lea     r15, aReadclient; "ReadClient"
0x180003bff  test    r8b, 3
0x180003c03  lea     r12, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003c0a  mov     rbp, rdx
0x180003c0d  mov     rdi, rcx
0x180003c10  setnz   dl
0x180003c13  bt      r8d, 16h
0x180003c18  setb    al
0x180003c1b  test    al, dl
0x180003c1d  jz      short loc_180003C56
0x180003c1f  mov     eax, [rbx]
0x180003c21  mov     r9, r15
0x180003c24  mov     dword ptr [rsp+2C8h+var_298], eax
0x180003c28  mov     r8d, 395h
0x180003c2e  mov     [rsp+2C8h+var_2A0], rcx
0x180003c33  lea     rax, aReadclientPFun; "\r\n  ReadClient[%p]: Function Entry\r"...
0x180003c3a  mov     rcx, cs:g_pDebug
0x180003c41  mov     rdx, r12
0x180003c44  mov     [rsp+2C8h+var_2A8], rax
0x180003c49  call    cs:__imp_PuDbgPrint
0x180003c4f  mov     r8d, cs:g_dwDebugFlags
0x180003c56  test    rdi, rdi
0x180003c59  jz      loc_180003E60
0x180003c5f  test    rbx, rbx
0x180003c62  jz      loc_180003E60
0x180003c68  mov     r9d, [rbx]
0x180003c6b  test    r9d, r9d
0x180003c6e  jz      short loc_180003C79
0x180003c70  test    rbp, rbp
0x180003c73  jz      loc_180003E60
0x180003c79  mov     rcx, [rdi+0C0h]
0x180003c80  test    rcx, rcx
0x180003c83  jnz     short loc_180003CCB
0x180003c85  test    r8b, 3
0x180003c89  setnz   cl
0x180003c8c  bt      r8d, 14h
0x180003c91  setb    al
0x180003c94  test    al, cl
0x180003c96  jz      loc_180003EB6
0x180003c9c  mov     rcx, cs:g_pDebug
0x180003ca3  lea     rax, aReadclientPFai_0; "\r\n  ReadClient[%p]: Failed to get int"...
0x180003caa  mov     [rsp+2C8h+var_2A0], rdi
0x180003caf  mov     r9, r15
0x180003cb2  mov     r8d, 3BFh
0x180003cb8  mov     [rsp+2C8h+var_2A8], rax
0x180003cbd  mov     rdx, r12
0x180003cc0  call    cs:__imp_PuDbgPrint
0x180003cc6  jmp     loc_180003EB6
0x180003ccb  mov     [rsp+2C8h+var_278], 0
0x180003cd4  mov     r8, rbp
0x180003cd7  mov     rax, [rcx]
0x180003cda  xor     edx, edx
0x180003cdc  mov     dword ptr [rsp+2C8h+var_298], 1
0x180003ce4  mov     [rsp+2C8h+var_2A0], rbx
0x180003ce9  mov     dword ptr [rsp+2C8h+var_2A8], r9d
0x180003cee  mov     rax, [rax+8]
0x180003cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cf7  lea     rdx, [rsp+2C8h+var_278]; void **
0x180003cfc  mov     esi, eax
0x180003cfe  call    ?IsapiUndoRevertHack@ISAPI_CONTEXT@@QEAAXPEAPEAX@Z; ISAPI_CONTEXT::IsapiUndoRevertHack(void * *)
0x180003d03  mov     ecx, cs:g_dwDebugFlags
0x180003d09  test    esi, esi
0x180003d0b  jns     short loc_180003D65
0x180003d0d  test    cl, 3
0x180003d10  setnz   dl
0x180003d13  bt      ecx, 14h
0x180003d17  setb    cl
0x180003d1a  test    cl, dl
0x180003d1c  jz      short loc_180003D57
0x180003d1e  mov     ecx, esi; int
0x180003d20  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180003d25  mov     rcx, cs:g_pDebug
0x180003d2c  mov     r9, r15
0x180003d2f  mov     dword ptr [rsp+2C8h+var_290], eax
0x180003d33  mov     r8d, 3DFh
0x180003d39  mov     dword ptr [rsp+2C8h+var_298], esi
0x180003d3d  lea     rax, aReadclientPFai; "\r\n  ReadClient[%p]: Failed\r\n    Ret"...
0x180003d44  mov     [rsp+2C8h+var_2A0], rdi
0x180003d49  mov     rdx, r12
0x180003d4c  mov     [rsp+2C8h+var_2A8], rax
0x180003d51  call    cs:__imp_PuDbgPrint
0x180003d57  mov     ecx, esi; int
0x180003d59  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180003d5e  mov     ecx, eax
0x180003d60  jmp     loc_180003EBB
0x180003d65  mov     edx, 600000h
0x180003d6a  mov     eax, ecx
0x180003d6c  and     eax, edx
0x180003d6e  cmp     eax, edx
0x180003d70  jnz     loc_180003E59
0x180003d76  test    cl, 3
0x180003d79  jz      short loc_180003DB1
0x180003d7b  mov     eax, [rbx]
0x180003d7d  mov     r9, r15
0x180003d80  mov     rcx, cs:g_pDebug
0x180003d87  mov     r8d, 3F1h
0x180003d8d  mov     dword ptr [rsp+2C8h+var_298], eax
0x180003d91  mov     rdx, r12
0x180003d94  lea     rax, aReadclientPSuc; "\r\n  ReadClient[%p]: Succeeded\r\n    "...
0x180003d9b  mov     [rsp+2C8h+var_2A0], rdi
0x180003da0  mov     [rsp+2C8h+var_2A8], rax
0x180003da5  call    cs:__imp_PuDbgPrint
0x180003dab  mov     ecx, cs:g_dwDebugFlags
0x180003db1  bt      ecx, 1Bh
0x180003db5  jnb     loc_180003E59
0x180003dbb  mov     r8d, 200h
0x180003dc1  lea     rdx, [rsp+2C8h+var_238]
0x180003dc9  lea     rcx, [rsp+2C8h+var_270]
0x180003dce  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180003dd4  mov     r8d, [rbx]
0x180003dd7  lea     rcx, [rsp+2C8h+var_270]
0x180003ddc  mov     ebx, 0A0h
0x180003de1  mov     rdx, rbp
0x180003de4  cmp     r8d, ebx
0x180003de7  cmova   r8d, ebx
0x180003deb  call    cs:__imp_?CopyBinary@STRA@@QEAAJPEAXK@Z; STRA::CopyBinary(void *,ulong)
0x180003df1  test    eax, eax
0x180003df3  jns     short loc_180003E07
0x180003df5  lea     rdx, word_180016DBA
0x180003dfc  lea     rcx, [rsp+2C8h+var_270]
0x180003e01  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180003e07  test    byte ptr cs:g_dwDebugFlags, 3
0x180003e0e  jz      short loc_180003E4E
0x180003e10  lea     rcx, [rsp+2C8h+var_270]
0x180003e15  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180003e1b  mov     [rsp+2C8h+var_290], rax
0x180003e20  lea     rcx, aReadclientPDum; "\r\n  ReadClient[%p]: Dump of up to %d "...
0x180003e27  mov     dword ptr [rsp+2C8h+var_298], ebx
0x180003e2b  mov     r9, r15
0x180003e2e  mov     [rsp+2C8h+var_2A0], rdi
0x180003e33  mov     r8d, 409h
0x180003e39  mov     [rsp+2C8h+var_2A8], rcx
0x180003e3e  mov     rdx, r12
0x180003e41  mov     rcx, cs:g_pDebug
0x180003e48  call    cs:__imp_PuDbgPrint
0x180003e4e  lea     rcx, [rsp+2C8h+var_270]
0x180003e53  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180003e59  mov     eax, 1
0x180003e5e  jmp     short loc_180003EC3
0x180003e60  test    r8b, 3
0x180003e64  setnz   cl
0x180003e67  bt      r8d, 14h
0x180003e6c  setb    al
0x180003e6f  test    al, cl
0x180003e71  jz      short loc_180003EB6
0x180003e73  test    rbx, rbx
0x180003e76  jz      short loc_180003E7C
0x180003e78  mov     eax, [rbx]
0x180003e7a  jmp     short loc_180003E7E
0x180003e7c  xor     eax, eax
0x180003e7e  mov     rcx, cs:g_pDebug
0x180003e85  mov     r9, r15
0x180003e88  mov     [rsp+2C8h+var_288], rbp
0x180003e8d  mov     r8d, 3ADh
0x180003e93  mov     dword ptr [rsp+2C8h+var_290], eax
0x180003e97  mov     rdx, r12
0x180003e9a  mov     [rsp+2C8h+var_298], rbx
0x180003e9f  lea     rax, aReadclientPPar; "\r\n  ReadClient[%p]: Parameter validat"...
0x180003ea6  mov     [rsp+2C8h+var_2A0], rdi
0x180003eab  mov     [rsp+2C8h+var_2A8], rax
0x180003eb0  call    cs:__imp_PuDbgPrint
0x180003eb6  mov     ecx, 57h ; 'W'; dwErrCode
0x180003ebb  call    cs:__imp_SetLastError
0x180003ec1  xor     eax, eax
0x180003ec3  mov     rcx, [rsp+2C8h+var_38]
0x180003ecb  xor     rcx, rsp; StackCookie
0x180003ece  call    __security_check_cookie
0x180003ed3  mov     rbx, [rsp+2C8h+arg_18]
0x180003edb  add     rsp, 2A0h
0x180003ee2  pop     r15
0x180003ee4  pop     r12
0x180003ee6  pop     rdi
0x180003ee7  pop     rsi
0x180003ee8  pop     rbp
0x180003ee9  retn
```
