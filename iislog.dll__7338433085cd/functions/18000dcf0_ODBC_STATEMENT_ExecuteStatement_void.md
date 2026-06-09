# ODBC_STATEMENT::ExecuteStatement(void)

- ea: `0x18000dcf0`
- end: `0x18000dd55`
- name: `?ExecuteStatement@ODBC_STATEMENT@@QEAAHXZ`
- size: `101`
- prototype: `_BOOL8 __fastcall(ODBC_STATEMENT *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b120`

## callees

- `0x18000dcf0`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x18000dd30`
- `IisRTL!PuDbgPrint` at `0x18000dd30`
- `ODBC32!__imp_SQLExecute` at `0x18000dd3a`
- `ODBC32!__imp_SQLExecute` at `0x18000dd3a`

## string_xrefs

- `0x18000dd29`: `inetsrv\iis\svcs\infocomm\log\plugin\odbcconn.cxx`
- `0x18000dd10`: `!!WARNING!! - Attempting to use Invalid ODBC Connection!\n`

## pseudocode

```c
_BOOL8 __fastcall ODBC_STATEMENT::ExecuteStatement(ODBC_STATEMENT *this)
{
  SQLRETURN v2; // ax

  if ( *((_WORD *)this + 12) > 1u && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\odbcconn.cxx",
      547,
      "ODBC_STATEMENT::ExecuteStatement",
      "!!WARNING!! - Attempting to use Invalid ODBC Connection!\n");
  v2 = SQLExecute(*((SQLHSTMT *)this + 2));
  *((_WORD *)this + 12) = v2;
  return (unsigned __int16)v2 <= 1u;
}

```

## disassembly

```asm
0x18000dcf0  push    rbx
0x18000dcf2  sub     rsp, 30h
0x18000dcf6  cmp     word ptr [rcx+18h], 1
0x18000dcfb  mov     rbx, rcx
0x18000dcfe  jbe     short loc_18000DD36
0x18000dd00  test    byte ptr cs:g_dwDebugFlags, 3
0x18000dd07  jz      short loc_18000DD36
0x18000dd09  mov     rcx, cs:g_pDebug
0x18000dd10  lea     rax, aWarningAttempt; "!!WARNING!! - Attempting to use Invalid"...
0x18000dd17  lea     r9, aOdbcStatementE_0; "ODBC_STATEMENT::ExecuteStatement"
0x18000dd1e  mov     [rsp+38h+var_18], rax
0x18000dd23  mov     r8d, 223h
0x18000dd29  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x18000dd30  call    cs:__imp_PuDbgPrint
0x18000dd36  mov     rcx, [rbx+10h]; StatementHandle
0x18000dd3a  call    cs:__imp_SQLExecute
0x18000dd40  xor     ecx, ecx
0x18000dd42  mov     [rbx+18h], ax
0x18000dd46  cmp     ax, 1
0x18000dd4a  setbe   cl
0x18000dd4d  mov     eax, ecx
0x18000dd4f  add     rsp, 30h
0x18000dd53  pop     rbx
0x18000dd54  retn
```
