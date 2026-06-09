# ODBC_CONNECTION::GetInfo(ulong,void *,ulong,ulong *)

- ea: `0x18000de20`
- end: `0x18000df13`
- name: `?GetInfo@ODBC_CONNECTION@@QEAAHKPEAXKPEAK@Z`
- size: `243`
- prototype: `__int64 __fastcall(ODBC_CONNECTION *__hidden this, unsigned int, void *, unsigned int, SQLSMALLINT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a7ac`

## callees

- `0x18000de20`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x18000dec4`
- `IisRTL!PuDbgPrint` at `0x18000defe`
- `IisRTL!PuDbgPrint` at `0x18000dec4`
- `IisRTL!PuDbgPrint` at `0x18000defe`
- `ODBC32!__imp_SQLGetInfo` at `0x18000de53`
- `ODBC32!__imp_SQLGetInfo` at `0x18000de53`

## string_xrefs

- `0x18000de8b`: `inetsrv\iis\svcs\infocomm\log\plugin\odbcconn.cxx`
- `0x18000def7`: `inetsrv\iis\svcs\infocomm\log\plugin\odbcconn.cxx`

## pseudocode

```c
_BOOL8 __fastcall ODBC_CONNECTION::GetInfo(
        ODBC_CONNECTION *this,
        int a2,
        void *a3,
        int a4,
        SQLSMALLINT *StringLengthPtr)
{
  void *v7; // rcx
  int v8; // ebp
  SQLRETURN v10; // ax
  BOOL v11; // ebx

  v7 = (void *)*((_QWORD *)this + 1);
  v8 = (int)a3;
  if ( v7 )
  {
    v10 = SQLGetInfo(v7, a2, a3, a4, StringLengthPtr);
    v11 = (unsigned __int16)v10 <= 1u;
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 1) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\odbcconn.cxx",
        1611,
        "ODBC_CONNECTION::GetInfo",
        "SQLGetInfo( %08x, %d, %08x, %d, %08x) returns %d.\n",
        *((_QWORD *)this + 1),
        a2,
        v8,
        a4,
        (_DWORD)StringLengthPtr,
        v10);
  }
  else
  {
    v11 = 0;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\odbcconn.cxx",
        1618,
        "ODBC_CONNECTION::GetInfo",
        "[SQLGetInfo] Invalid Connection to ODBC\n");
  }
  return v11;
}

```

## disassembly

```asm
0x18000de20  push    rbx
0x18000de22  push    rbp
0x18000de23  push    rsi
0x18000de24  push    rdi
0x18000de25  push    r14
0x18000de27  push    r15
0x18000de29  sub     rsp, 68h
0x18000de2d  mov     rdi, rcx
0x18000de30  mov     esi, r9d
0x18000de33  mov     rcx, [rcx+8]; ConnectionHandle
0x18000de37  mov     rbp, r8
0x18000de3a  mov     r14d, edx
0x18000de3d  test    rcx, rcx
0x18000de40  jz      loc_18000DECC
0x18000de46  mov     r15, [rsp+98h+arg_20]
0x18000de4e  mov     [rsp+98h+StringLengthPtr], r15; StringLengthPtr
0x18000de53  call    cs:__imp_SQLGetInfo
0x18000de59  mov     ecx, cs:g_dwDebugFlags
0x18000de5f  xor     ebx, ebx
0x18000de61  cmp     ax, 1
0x18000de65  setbe   bl
0x18000de68  test    cl, 3
0x18000de6b  setnz   dl
0x18000de6e  test    cl, 1
0x18000de71  setnz   cl
0x18000de74  test    cl, dl
0x18000de76  jz      loc_18000DF04
0x18000de7c  mov     rcx, cs:g_pDebug
0x18000de83  lea     r9, aOdbcConnection_3; "ODBC_CONNECTION::GetInfo"
0x18000de8a  cwde
0x18000de8b  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x18000de92  mov     [rsp+98h+var_48], eax
0x18000de96  mov     r8d, 64Bh
0x18000de9c  mov     rax, [rdi+8]
0x18000dea0  mov     [rsp+98h+var_50], r15
0x18000dea5  mov     [rsp+98h+var_58], esi
0x18000dea9  mov     [rsp+98h+var_60], rbp
0x18000deae  mov     [rsp+98h+var_68], r14d
0x18000deb3  mov     [rsp+98h+var_70], rax
0x18000deb8  lea     rax, aSqlgetinfo08xD; "SQLGetInfo( %08x, %d, %08x, %d, %08x) r"...
0x18000debf  mov     [rsp+98h+StringLengthPtr], rax
0x18000dec4  call    cs:__imp_PuDbgPrint
0x18000deca  jmp     short loc_18000DF04
0x18000decc  xor     ebx, ebx
0x18000dece  test    byte ptr cs:g_dwDebugFlags, 3
0x18000ded5  jz      short loc_18000DF04
0x18000ded7  mov     rcx, cs:g_pDebug
0x18000dede  lea     rax, aSqlgetinfoInva; "[SQLGetInfo] Invalid Connection to ODBC"...
0x18000dee5  lea     r9, aOdbcConnection_3; "ODBC_CONNECTION::GetInfo"
0x18000deec  mov     [rsp+98h+StringLengthPtr], rax
0x18000def1  mov     r8d, 652h
0x18000def7  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x18000defe  call    cs:__imp_PuDbgPrint
0x18000df04  mov     eax, ebx
0x18000df06  add     rsp, 68h
0x18000df0a  pop     r15
0x18000df0c  pop     r14
0x18000df0e  pop     rdi
0x18000df0f  pop     rsi
0x18000df10  pop     rbp
0x18000df11  pop     rbx
0x18000df12  retn
```
