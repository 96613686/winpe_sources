# ODBC_STATEMENT::~ODBC_STATEMENT(void)

- ea: `0x18000d6b0`
- end: `0x18000d72e`
- name: `??1ODBC_STATEMENT@@QEAA@XZ`
- size: `126`
- prototype: `void __fastcall(ODBC_STATEMENT *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bdc0`

## callees

- `0x18000d6b0`
- `0x18000dd60`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x18000d71b`
- `IisRTL!PuDbgPrint` at `0x18000d71b`
- `ODBC32!__imp_SQLFreeStmt` at `0x18000d6c7`
- `ODBC32!__imp_SQLFreeStmt` at `0x18000d6c7`

## string_xrefs

- `0x18000d6fe`: `inetsrv\iis\svcs\infocomm\log\plugin\odbcconn.cxx`

## pseudocode

```c
void __fastcall ODBC_STATEMENT::~ODBC_STATEMENT(ODBC_STATEMENT *this)
{
  void *v2; // rcx
  SQLRETURN v3; // ax
  char v4; // cl
  bool v5; // zf

  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    v3 = SQLFreeStmt(v2, 1u);
    v4 = g_dwDebugFlags;
    v5 = (g_dwDebugFlags & 3) == 0;
    *((_WORD *)this + 12) = v3;
    *((_QWORD *)this + 2) = 0;
    if ( !v5 && (v4 & 1) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\odbcconn.cxx",
        365,
        "ODBC_STATEMENT::~ODBC_STATEMENT",
        "SqlFreeStmt() return code %d.\n",
        v3);
  }
  ODBC_STATEMENT::FreeColumnMemory(this);
}

```

## disassembly

```asm
0x18000d6b0  push    rbx
0x18000d6b2  sub     rsp, 30h
0x18000d6b6  mov     rbx, rcx
0x18000d6b9  mov     rcx, [rcx+10h]; StatementHandle
0x18000d6bd  test    rcx, rcx
0x18000d6c0  jz      short loc_18000D721
0x18000d6c2  mov     edx, 1; Option
0x18000d6c7  call    cs:__imp_SQLFreeStmt
0x18000d6cd  mov     ecx, cs:g_dwDebugFlags
0x18000d6d3  test    cl, 3
0x18000d6d6  mov     [rbx+18h], ax
0x18000d6da  setnz   dl
0x18000d6dd  mov     qword ptr [rbx+10h], 0
0x18000d6e5  test    cl, 1
0x18000d6e8  setnz   cl
0x18000d6eb  test    cl, dl
0x18000d6ed  jz      short loc_18000D721
0x18000d6ef  mov     rcx, cs:g_pDebug
0x18000d6f6  lea     r9, aOdbcStatementO; "ODBC_STATEMENT::~ODBC_STATEMENT"
0x18000d6fd  cwde
0x18000d6fe  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x18000d705  mov     [rsp+38h+var_10], eax
0x18000d709  mov     r8d, 16Dh
0x18000d70f  lea     rax, aSqlfreestmtRet; "SqlFreeStmt() return code %d.\n"
0x18000d716  mov     [rsp+38h+var_18], rax
0x18000d71b  call    cs:__imp_PuDbgPrint
0x18000d721  mov     rcx, rbx; this
0x18000d724  add     rsp, 30h
0x18000d728  pop     rbx
0x18000d729  jmp     ?FreeColumnMemory@ODBC_STATEMENT@@QEAAXXZ; ODBC_STATEMENT::FreeColumnMemory(void)
```
