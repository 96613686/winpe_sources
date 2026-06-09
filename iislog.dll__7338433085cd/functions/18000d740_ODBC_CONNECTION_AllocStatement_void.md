# ODBC_CONNECTION::AllocStatement(void)

- ea: `0x18000d740`
- end: `0x18000d806`
- name: `?AllocStatement@ODBC_CONNECTION@@QEAAPEAVODBC_STATEMENT@@XZ`
- size: `198`
- prototype: `struct ODBC_STATEMENT *__fastcall(ODBC_CONNECTION *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bc18`

## callees

- `0x180001008`
- `0x18000d740`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x18000d7b6`
- `IisRTL!PuDbgPrint` at `0x18000d7b6`
- `ODBC32!__imp_SQLAllocStmt` at `0x18000d75b`
- `ODBC32!__imp_SQLAllocStmt` at `0x18000d75b`

## string_xrefs

- `0x18000d78d`: `inetsrv\iis\svcs\infocomm\log\plugin\odbcconn.cxx`

## pseudocode

```c
SQLHDBC **__fastcall ODBC_CONNECTION::AllocStatement(SQLHDBC *this)
{
  SQLRETURN v2; // ax
  char v3; // r8
  bool v4; // zf
  SQLHDBC **v5; // rax
  SQLHDBC **v6; // rcx
  SQLHSTMT StatementHandle; // [rsp+50h] [rbp+8h] BYREF

  StatementHandle = 0;
  v2 = SQLAllocStmt(this[1], &StatementHandle);
  v3 = g_dwDebugFlags;
  v4 = (g_dwDebugFlags & 3) == 0;
  *((_WORD *)this + 8) = v2;
  if ( !v4 && (v3 & 1) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\odbcconn.cxx",
      1264,
      "ODBC_CONNECTION::AllocStatement",
      "SqlAllocStmt() returns code %d. New Hstmt is : %08x\n",
      v2,
      (_DWORD)StatementHandle);
  if ( *((_WORD *)this + 8) > 1u )
    return 0;
  v5 = (SQLHDBC **)operator new(0x38u);
  v6 = v5;
  if ( !v5 )
    return 0;
  v5[2] = (SQLHDBC *)StatementHandle;
  *((_DWORD *)v5 + 6) = 0;
  v5[4] = 0;
  v5[5] = 0;
  v5[6] = 0;
  *v5 = this;
  *((_DWORD *)v5 + 2) = 0;
  return v6;
}

```

## disassembly

```asm
0x18000d740  push    rbx
0x18000d742  sub     rsp, 40h
0x18000d746  mov     rbx, rcx
0x18000d749  mov     [rsp+48h+StatementHandle], 0
0x18000d752  mov     rcx, [rcx+8]; ConnectionHandle
0x18000d756  lea     rdx, [rsp+48h+StatementHandle]; StatementHandle
0x18000d75b  call    cs:__imp_SQLAllocStmt
0x18000d761  mov     r8d, cs:g_dwDebugFlags
0x18000d768  test    r8b, 3
0x18000d76c  mov     [rbx+10h], ax
0x18000d770  setnz   dl
0x18000d773  test    r8b, 1
0x18000d777  setnz   cl
0x18000d77a  test    cl, dl
0x18000d77c  jz      short loc_18000D7BC
0x18000d77e  movsx   ecx, ax
0x18000d781  lea     r9, aOdbcConnection_5; "ODBC_CONNECTION::AllocStatement"
0x18000d788  mov     rax, [rsp+48h+StatementHandle]
0x18000d78d  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x18000d794  mov     [rsp+48h+var_18], rax
0x18000d799  mov     r8d, 4F0h
0x18000d79f  mov     [rsp+48h+var_20], ecx
0x18000d7a3  lea     rax, aSqlallocstmtRe; "SqlAllocStmt() returns code %d. New Hst"...
0x18000d7aa  mov     rcx, cs:g_pDebug
0x18000d7b1  mov     [rsp+48h+var_28], rax
0x18000d7b6  call    cs:__imp_PuDbgPrint
0x18000d7bc  cmp     word ptr [rbx+10h], 1
0x18000d7c1  ja      short loc_18000D7FB
0x18000d7c3  mov     ecx, 38h ; '8'; Size
0x18000d7c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d7cd  mov     rcx, rax
0x18000d7d0  test    rax, rax
0x18000d7d3  jz      short loc_18000D7FB
0x18000d7d5  mov     rax, [rsp+48h+StatementHandle]
0x18000d7da  mov     [rcx+10h], rax
0x18000d7de  xor     eax, eax
0x18000d7e0  mov     [rcx+18h], eax
0x18000d7e3  mov     [rcx+20h], rax
0x18000d7e7  mov     [rcx+28h], rax
0x18000d7eb  mov     [rcx+30h], rax
0x18000d7ef  mov     [rcx], rbx
0x18000d7f2  mov     dword ptr [rcx+8], 0
0x18000d7f9  jmp     short loc_18000D7FD
0x18000d7fb  xor     ecx, ecx
0x18000d7fd  mov     rax, rcx
0x18000d800  add     rsp, 40h
0x18000d804  pop     rbx
0x18000d805  retn
```
