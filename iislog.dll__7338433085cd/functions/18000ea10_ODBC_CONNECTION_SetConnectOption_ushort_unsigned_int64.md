# ODBC_CONNECTION::SetConnectOption(ushort,unsigned __int64)

- ea: `0x18000ea10`
- end: `0x18000eae4`
- name: `?SetConnectOption@ODBC_CONNECTION@@QEAAHG_K@Z`
- size: `212`
- prototype: `__int64 __fastcall(ODBC_CONNECTION *__hidden this, unsigned __int16, unsigned __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ea10`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x18000ea8f`
- `IisRTL!PuDbgPrint` at `0x18000eacc`
- `IisRTL!PuDbgPrint` at `0x18000ea8f`
- `IisRTL!PuDbgPrint` at `0x18000eacc`
- `ODBC32!__imp_SQLSetConnectOption` at `0x18000ea31`
- `ODBC32!__imp_SQLSetConnectOption` at `0x18000ea31`

## string_xrefs

- `0x18000ea69`: `inetsrv\iis\svcs\infocomm\log\plugin\odbcconn.cxx`
- `0x18000eac5`: `inetsrv\iis\svcs\infocomm\log\plugin\odbcconn.cxx`

## pseudocode

```c
_BOOL8 __fastcall ODBC_CONNECTION::SetConnectOption(ODBC_CONNECTION *this, SQLUSMALLINT a2, SQLULEN a3)
{
  void *v3; // rcx
  int v4; // edi
  int v5; // esi
  SQLRETURN v6; // ax
  BOOL v7; // ebx

  v3 = (void *)*((_QWORD *)this + 1);
  v4 = a3;
  v5 = a2;
  if ( v3 )
  {
    v6 = SQLSetConnectOption(v3, a2, a3);
    v7 = (unsigned __int16)v6 <= 1u;
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 1) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\odbcconn.cxx",
        1325,
        "ODBC_CONNECTION::SetConnectOption",
        "SQLSetConnectOption( %d, %d) returns code %d.\n",
        v5,
        v4,
        v6);
  }
  else
  {
    v7 = 1;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\odbcconn.cxx",
        1333,
        "ODBC_CONNECTION::SetConnectOption",
        "[SetConnectOption] Warning: Setting option on closed connection\n");
  }
  return v7;
}

```

## disassembly

```asm
0x18000ea10  mov     [rsp+arg_0], rbx
0x18000ea15  mov     [rsp+arg_8], rsi
0x18000ea1a  push    rdi
0x18000ea1b  sub     rsp, 40h
0x18000ea1f  mov     rcx, [rcx+8]; ConnectionHandle
0x18000ea23  mov     rdi, r8
0x18000ea26  movzx   esi, dx
0x18000ea29  test    rcx, rcx
0x18000ea2c  jz      short loc_18000EA97
0x18000ea2e  movzx   edx, si; Option
0x18000ea31  call    cs:__imp_SQLSetConnectOption
0x18000ea37  mov     ecx, cs:g_dwDebugFlags
0x18000ea3d  xor     ebx, ebx
0x18000ea3f  lea     r8d, [rbx+1]
0x18000ea43  cmp     ax, r8w
0x18000ea47  setbe   bl
0x18000ea4a  test    cl, 3
0x18000ea4d  setnz   dl
0x18000ea50  test    r8b, cl
0x18000ea53  setnz   cl
0x18000ea56  test    cl, dl
0x18000ea58  jz      short loc_18000EAD2
0x18000ea5a  mov     rcx, cs:g_pDebug
0x18000ea61  lea     r9, aOdbcConnection_1; "ODBC_CONNECTION::SetConnectOption"
0x18000ea68  cwde
0x18000ea69  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x18000ea70  mov     [rsp+48h+var_10], eax
0x18000ea74  mov     r8d, 52Dh
0x18000ea7a  mov     [rsp+48h+var_18], rdi
0x18000ea7f  lea     rax, aSqlsetconnecto; "SQLSetConnectOption( %d, %d) returns co"...
0x18000ea86  mov     [rsp+48h+var_20], esi
0x18000ea8a  mov     [rsp+48h+var_28], rax
0x18000ea8f  call    cs:__imp_PuDbgPrint
0x18000ea95  jmp     short loc_18000EAD2
0x18000ea97  test    byte ptr cs:g_dwDebugFlags, 3
0x18000ea9e  mov     ebx, 1
0x18000eaa3  jz      short loc_18000EAD2
0x18000eaa5  mov     rcx, cs:g_pDebug
0x18000eaac  lea     rax, aSetconnectopti_0; "[SetConnectOption] Warning: Setting opt"...
0x18000eab3  lea     r9, aOdbcConnection_1; "ODBC_CONNECTION::SetConnectOption"
0x18000eaba  mov     [rsp+48h+var_28], rax
0x18000eabf  mov     r8d, 535h
0x18000eac5  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x18000eacc  call    cs:__imp_PuDbgPrint
0x18000ead2  mov     rsi, [rsp+48h+arg_8]
0x18000ead7  mov     eax, ebx
0x18000ead9  mov     rbx, [rsp+48h+arg_0]
0x18000eade  add     rsp, 40h
0x18000eae2  pop     rdi
0x18000eae3  retn
```
