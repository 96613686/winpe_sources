# ODBC_CONNECTION::Close(void)

- ea: `0x18000d8b0`
- end: `0x18000da15`
- name: `?Close@ODBC_CONNECTION@@QEAAHXZ`
- size: `357`
- prototype: `__int64 __fastcall(ODBC_CONNECTION *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bdc0`
- `0x18000d6a0`

## callees

- `0x18000d8b0`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x18000d923`
- `IisRTL!PuDbgPrint` at `0x18000d98a`
- `IisRTL!PuDbgPrint` at `0x18000d9fd`
- `IisRTL!PuDbgPrint` at `0x18000d923`
- `IisRTL!PuDbgPrint` at `0x18000d98a`
- `IisRTL!PuDbgPrint` at `0x18000d9fd`
- `ODBC32!__imp_SQLDisconnect` at `0x18000d8d6`
- `ODBC32!__imp_SQLDisconnect` at `0x18000d8d6`
- `ODBC32!__imp_SQLFreeConnect` at `0x18000d92d`
- `ODBC32!__imp_SQLFreeConnect` at `0x18000d92d`
- `ODBC32!__imp_SQLFreeEnv` at `0x18000d998`
- `ODBC32!__imp_SQLFreeEnv` at `0x18000d998`

## string_xrefs

- `0x18000d911`: `inetsrv\iis\svcs\infocomm\log\plugin\odbcconn.cxx`
- `0x18000d978`: `inetsrv\iis\svcs\infocomm\log\plugin\odbcconn.cxx`
- `0x18000d9eb`: `inetsrv\iis\svcs\infocomm\log\plugin\odbcconn.cxx`

## pseudocode

```c
_BOOL8 __fastcall ODBC_CONNECTION::Close(ODBC_CONNECTION *this)
{
  void *v2; // rcx
  BOOL v3; // ebx
  int v4; // edx
  char v5; // al
  bool v6; // zf
  SQLRETURN v7; // ax
  int v8; // edx
  SQLRETURN v9; // ax

  v2 = (void *)*((_QWORD *)this + 1);
  v3 = 1;
  if ( v2 )
  {
    v4 = SQLDisconnect(v2);
    v5 = g_dwDebugFlags;
    v6 = (g_dwDebugFlags & 3) == 0;
    *((_WORD *)this + 8) = v4;
    if ( !v6 && (v5 & 1) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\odbcconn.cxx",
        1189,
        "ODBC_CONNECTION::Close",
        "Warning: SQLDisconnect() returns code %d.\n",
        v4);
    v7 = SQLFreeConnect(*((SQLHDBC *)this + 1));
    *((_QWORD *)this + 1) = 0;
    v8 = v7;
    LOBYTE(v7) = g_dwDebugFlags;
    *((_WORD *)this + 8) = v8;
    v3 = (unsigned __int16)v8 <= 1u;
    if ( (v7 & 3) != 0 && (v7 & 1) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\odbcconn.cxx",
        1202,
        "ODBC_CONNECTION::Close",
        "SQLFreeConnect() returns code %d.\n",
        v8);
  }
  if ( *(_QWORD *)this )
  {
    v9 = SQLFreeEnv(*(SQLHENV *)this);
    *(_QWORD *)this = 0;
    *((_WORD *)this + 8) = v9;
    v3 = v3 && (unsigned __int16)v9 <= 1u;
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 1) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\odbcconn.cxx",
        1221,
        "ODBC_CONNECTION::Close",
        "SQLFreeEnv() returns code %d.\n",
        v9);
  }
  return v3;
}

```

## disassembly

```asm
0x18000d8b0  mov     [rsp+arg_0], rbx
0x18000d8b5  mov     [rsp+arg_8], rsi
0x18000d8ba  push    rdi
0x18000d8bb  sub     rsp, 30h
0x18000d8bf  mov     rdi, rcx
0x18000d8c2  mov     esi, 1
0x18000d8c7  mov     rcx, [rcx+8]; ConnectionHandle
0x18000d8cb  mov     ebx, esi
0x18000d8cd  test    rcx, rcx
0x18000d8d0  jz      loc_18000D990
0x18000d8d6  call    cs:__imp_SQLDisconnect
0x18000d8dc  movsx   edx, ax
0x18000d8df  mov     eax, cs:g_dwDebugFlags
0x18000d8e5  test    al, 3
0x18000d8e7  mov     [rdi+10h], dx
0x18000d8eb  setnz   cl
0x18000d8ee  test    sil, al
0x18000d8f1  setnz   al
0x18000d8f4  test    al, cl
0x18000d8f6  jz      short loc_18000D929
0x18000d8f8  mov     rcx, cs:g_pDebug
0x18000d8ff  lea     rax, aWarningSqldisc; "Warning: SQLDisconnect() returns code %"...
0x18000d906  mov     [rsp+38h+var_10], edx
0x18000d90a  lea     r9, aOdbcConnection_0; "ODBC_CONNECTION::Close"
0x18000d911  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x18000d918  mov     [rsp+38h+var_18], rax
0x18000d91d  mov     r8d, 4A5h
0x18000d923  call    cs:__imp_PuDbgPrint
0x18000d929  mov     rcx, [rdi+8]; ConnectionHandle
0x18000d92d  call    cs:__imp_SQLFreeConnect
0x18000d933  xor     ebx, ebx
0x18000d935  mov     qword ptr [rdi+8], 0
0x18000d93d  movsx   edx, ax
0x18000d940  mov     eax, cs:g_dwDebugFlags
0x18000d946  cmp     dx, si
0x18000d949  mov     [rdi+10h], dx
0x18000d94d  setbe   bl
0x18000d950  test    al, 3
0x18000d952  setnz   cl
0x18000d955  test    sil, al
0x18000d958  setnz   al
0x18000d95b  test    al, cl
0x18000d95d  jz      short loc_18000D990
0x18000d95f  mov     rcx, cs:g_pDebug
0x18000d966  lea     rax, aSqlfreeconnect; "SQLFreeConnect() returns code %d.\n"
0x18000d96d  mov     [rsp+38h+var_10], edx
0x18000d971  lea     r9, aOdbcConnection_0; "ODBC_CONNECTION::Close"
0x18000d978  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x18000d97f  mov     [rsp+38h+var_18], rax
0x18000d984  mov     r8d, 4B2h
0x18000d98a  call    cs:__imp_PuDbgPrint
0x18000d990  mov     rcx, [rdi]; EnvironmentHandle
0x18000d993  test    rcx, rcx
0x18000d996  jz      short loc_18000DA03
0x18000d998  call    cs:__imp_SQLFreeEnv
0x18000d99e  mov     qword ptr [rdi], 0
0x18000d9a5  movsx   edx, ax
0x18000d9a8  mov     [rdi+10h], dx
0x18000d9ac  test    ebx, ebx
0x18000d9ae  jz      short loc_18000D9B9
0x18000d9b0  cmp     dx, si
0x18000d9b3  ja      short loc_18000D9B9
0x18000d9b5  mov     ebx, esi
0x18000d9b7  jmp     short loc_18000D9BB
0x18000d9b9  xor     ebx, ebx
0x18000d9bb  mov     eax, cs:g_dwDebugFlags
0x18000d9c1  test    al, 3
0x18000d9c3  setnz   r8b
0x18000d9c7  test    sil, al
0x18000d9ca  setnz   cl
0x18000d9cd  test    cl, r8b
0x18000d9d0  jz      short loc_18000DA03
0x18000d9d2  mov     rcx, cs:g_pDebug
0x18000d9d9  lea     rax, aSqlfreeenvRetu; "SQLFreeEnv() returns code %d.\n"
0x18000d9e0  mov     [rsp+38h+var_10], edx
0x18000d9e4  lea     r9, aOdbcConnection_0; "ODBC_CONNECTION::Close"
0x18000d9eb  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x18000d9f2  mov     [rsp+38h+var_18], rax
0x18000d9f7  mov     r8d, 4C5h
0x18000d9fd  call    cs:__imp_PuDbgPrint
0x18000da03  mov     rsi, [rsp+38h+arg_8]
0x18000da08  mov     eax, ebx
0x18000da0a  mov     rbx, [rsp+38h+arg_0]
0x18000da0f  add     rsp, 30h
0x18000da13  pop     rdi
0x18000da14  retn
```
