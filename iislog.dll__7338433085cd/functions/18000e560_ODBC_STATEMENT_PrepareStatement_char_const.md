# ODBC_STATEMENT::PrepareStatement(char const *)

- ea: `0x18000e560`
- end: `0x18000e5ee`
- name: `?PrepareStatement@ODBC_STATEMENT@@QEAAHPEBD@Z`
- size: `142`
- prototype: `_BOOL8 __fastcall(SQLHSTMT *this, SQLCHAR *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bc18`

## callees

- `0x18000e560`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x18000e5d0`
- `IisRTL!PuDbgPrint` at `0x18000e5d0`
- `ODBC32!__imp_SQLPrepare` at `0x18000e57a`
- `ODBC32!__imp_SQLPrepare` at `0x18000e57a`

## string_xrefs

- `0x18000e5ae`: `inetsrv\iis\svcs\infocomm\log\plugin\odbcconn.cxx`

## pseudocode

```c
_BOOL8 __fastcall ODBC_STATEMENT::PrepareStatement(SQLHSTMT *this, SQLCHAR *a2)
{
  SQLRETURN v4; // ax
  char v5; // r9
  bool v6; // zf
  _BOOL8 result; // rax

  v4 = SQLPrepare(this[2], a2, -3);
  v5 = g_dwDebugFlags;
  v6 = (g_dwDebugFlags & 3) == 0;
  *((_WORD *)this + 12) = v4;
  if ( !v6 && (v5 & 1) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\odbcconn.cxx",
      458,
      "ODBC_STATEMENT::PrepareStatement",
      " SQLPrepare( %s) returns ErrorCode = %d.\n",
      (const char *)a2,
      v4);
  result = *((_WORD *)this + 12) <= 1u;
  *((_DWORD *)this + 2) = result;
  return result;
}

```

## disassembly

```asm
0x18000e560  mov     [rsp+arg_0], rbx
0x18000e565  push    rdi
0x18000e566  sub     rsp, 40h
0x18000e56a  mov     rbx, rcx
0x18000e56d  mov     r8d, 0FFFFFFFDh; TextLength
0x18000e573  mov     rcx, [rcx+10h]; StatementHandle
0x18000e577  mov     rdi, rdx
0x18000e57a  call    cs:__imp_SQLPrepare
0x18000e580  mov     r9d, cs:g_dwDebugFlags
0x18000e587  test    r9b, 3
0x18000e58b  mov     [rbx+18h], ax
0x18000e58f  setnz   r8b
0x18000e593  test    r9b, 1
0x18000e597  setnz   cl
0x18000e59a  test    cl, r8b
0x18000e59d  jz      short loc_18000E5D6
0x18000e59f  mov     rcx, cs:g_pDebug
0x18000e5a6  lea     r9, aOdbcStatementP; "ODBC_STATEMENT::PrepareStatement"
0x18000e5ad  cwde
0x18000e5ae  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x18000e5b5  mov     [rsp+48h+var_18], eax
0x18000e5b9  mov     r8d, 1CAh
0x18000e5bf  lea     rax, aSqlprepareSRet; " SQLPrepare( %s) returns ErrorCode = %d"...
0x18000e5c6  mov     [rsp+48h+var_20], rdi
0x18000e5cb  mov     [rsp+48h+var_28], rax
0x18000e5d0  call    cs:__imp_PuDbgPrint
0x18000e5d6  xor     eax, eax
0x18000e5d8  cmp     word ptr [rbx+18h], 1
0x18000e5dd  setbe   al
0x18000e5e0  mov     [rbx+8], eax
0x18000e5e3  mov     rbx, [rsp+48h+arg_0]
0x18000e5e8  add     rsp, 40h
0x18000e5ec  pop     rdi
0x18000e5ed  retn
```
