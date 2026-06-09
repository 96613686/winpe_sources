# ODBC_STATEMENT::ExecDirect(char const *,ulong)

- ea: `0x18000dc00`
- end: `0x18000dcde`
- name: `?ExecDirect@ODBC_STATEMENT@@QEAAHPEBDK@Z`
- size: `222`
- prototype: `_BOOL8 __fastcall(SQLHSTMT *this, SQLCHAR *, SQLINTEGER)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000dc00`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x18000dc5d`
- `IisRTL!PuDbgPrint` at `0x18000dcc6`
- `IisRTL!PuDbgPrint` at `0x18000dc5d`
- `IisRTL!PuDbgPrint` at `0x18000dcc6`
- `ODBC32!__imp_SQLExecDirect` at `0x18000dc6d`
- `ODBC32!__imp_SQLExecDirect` at `0x18000dc6d`

## string_xrefs

- `0x18000dc4c`: `inetsrv\iis\svcs\infocomm\log\plugin\odbcconn.cxx`
- `0x18000dcb4`: `inetsrv\iis\svcs\infocomm\log\plugin\odbcconn.cxx`
- `0x18000dc36`: ` Executing the SQL command (%d bytes) %s.\n`

## pseudocode

```c
_BOOL8 __fastcall ODBC_STATEMENT::ExecDirect(SQLHSTMT *this, SQLCHAR *a2, SQLINTEGER a3)
{
  SQLRETURN v6; // ax
  char v7; // cl
  BOOL v8; // ebx

  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 1) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\odbcconn.cxx",
      390,
      "ODBC_STATEMENT::ExecDirect",
      " Executing the SQL command (%d bytes) %s.\n",
      a3,
      (const char *)a2);
  v6 = SQLExecDirect(this[2], a2, a3);
  v7 = g_dwDebugFlags;
  *((_WORD *)this + 12) = v6;
  v8 = (unsigned __int16)v6 <= 1u;
  if ( (v7 & 3) != 0 && (v7 & 1) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\odbcconn.cxx",
      403,
      "ODBC_STATEMENT::ExecDirect",
      " SQLExecDirect() returns code %d\n",
      v6);
  return v8;
}

```

## disassembly

```asm
0x18000dc00  mov     r11, rsp
0x18000dc03  mov     [r11+8], rbx
0x18000dc07  mov     [r11+10h], rsi
0x18000dc0b  push    rdi
0x18000dc0c  sub     rsp, 40h
0x18000dc10  mov     eax, cs:g_dwDebugFlags
0x18000dc16  mov     rdi, rdx
0x18000dc19  test    al, 3
0x18000dc1b  mov     ebx, r8d
0x18000dc1e  mov     rsi, rcx
0x18000dc21  setnz   r9b
0x18000dc25  test    al, 1
0x18000dc27  setnz   al
0x18000dc2a  test    al, r9b
0x18000dc2d  jz      short loc_18000DC63
0x18000dc2f  mov     rcx, cs:g_pDebug
0x18000dc36  lea     rax, aExecutingTheSq; " Executing the SQL command (%d bytes) %"...
0x18000dc3d  mov     [r11-18h], rdx
0x18000dc41  lea     r9, aOdbcStatementE; "ODBC_STATEMENT::ExecDirect"
0x18000dc48  mov     [r11-20h], rbx
0x18000dc4c  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x18000dc53  mov     r8d, 186h
0x18000dc59  mov     [r11-28h], rax
0x18000dc5d  call    cs:__imp_PuDbgPrint
0x18000dc63  mov     rcx, [rsi+10h]; StatementHandle
0x18000dc67  mov     r8d, ebx; TextLength
0x18000dc6a  mov     rdx, rdi; StatementText
0x18000dc6d  call    cs:__imp_SQLExecDirect
0x18000dc73  mov     ecx, cs:g_dwDebugFlags
0x18000dc79  xor     ebx, ebx
0x18000dc7b  cmp     ax, 1
0x18000dc7f  mov     [rsi+18h], ax
0x18000dc83  setbe   bl
0x18000dc86  test    cl, 3
0x18000dc89  setnz   r8b
0x18000dc8d  test    cl, 1
0x18000dc90  setnz   cl
0x18000dc93  test    cl, r8b
0x18000dc96  jz      short loc_18000DCCC
0x18000dc98  movsx   ecx, ax
0x18000dc9b  lea     r9, aOdbcStatementE; "ODBC_STATEMENT::ExecDirect"
0x18000dca2  mov     [rsp+48h+var_20], ecx
0x18000dca6  lea     rax, aSqlexecdirectR; " SQLExecDirect() returns code %d\n"
0x18000dcad  mov     rcx, cs:g_pDebug
0x18000dcb4  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x18000dcbb  mov     r8d, 193h
0x18000dcc1  mov     [rsp+48h+var_28], rax
0x18000dcc6  call    cs:__imp_PuDbgPrint
0x18000dccc  mov     rsi, [rsp+48h+arg_8]
0x18000dcd1  mov     eax, ebx
0x18000dcd3  mov     rbx, [rsp+48h+arg_0]
0x18000dcd8  add     rsp, 40h
0x18000dcdc  pop     rdi
0x18000dcdd  retn
```
