# ODBC_CONNECTION::Open(char const *,char const *,char const *,int)

- ea: `0x18000e300`
- end: `0x18000e559`
- name: `?Open@ODBC_CONNECTION@@QEAAHPEBD00H@Z`
- size: `601`
- prototype: `__int64 __fastcall(ODBC_CONNECTION *__hidden this, SQLCHAR *ServerName, SQLCHAR *UserName, SQLCHAR *Authentication, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000afb0`
- `0x18000b120`

## callees

- `0x18000df20`
- `0x18000e300`
- `0x18000eca0`

## import_xrefs

- `IisRTL!??0STR@@QEAA@XZ` at `0x18000e464`
- `IisRTL!??0STR@@QEAA@XZ` at `0x18000e464`
- `IisRTL!??1STR@@QEAA@XZ` at `0x18000e4c1`
- `IisRTL!??1STR@@QEAA@XZ` at `0x18000e4c1`
- `IisRTL!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBDK@Z` at `0x18000e4b6`
- `IisRTL!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBDK@Z` at `0x18000e4b6`
- `IisRTL!PuDbgPrint` at `0x18000e396`
- `IisRTL!PuDbgPrint` at `0x18000e40d`
- `IisRTL!PuDbgPrint` at `0x18000e51f`
- `IisRTL!PuDbgPrint` at `0x18000e396`
- `IisRTL!PuDbgPrint` at `0x18000e40d`
- `IisRTL!PuDbgPrint` at `0x18000e51f`
- `KERNEL32!SetLastError` at `0x18000e52f`
- `KERNEL32!SetLastError` at `0x18000e52f`
- `ODBC32!__imp_SQLAllocConnect` at `0x18000e3ae`
- `ODBC32!__imp_SQLAllocConnect` at `0x18000e3ae`
- `ODBC32!__imp_SQLAllocEnv` at `0x18000e330`
- `ODBC32!__imp_SQLAllocEnv` at `0x18000e330`
- `ODBC32!__imp_SQLConnect` at `0x18000e43b`
- `ODBC32!__imp_SQLConnect` at `0x18000e43b`

## string_xrefs

- `0x18000e373`: `inetsrv\iis\svcs\infocomm\log\plugin\odbcconn.cxx`
- `0x18000e3e4`: `inetsrv\iis\svcs\infocomm\log\plugin\odbcconn.cxx`
- `0x18000e4f3`: `inetsrv\iis\svcs\infocomm\log\plugin\odbcconn.cxx`
- `0x18000e365`: `ODBC_CONNECTION::Open`
- `0x18000e3da`: `ODBC_CONNECTION::Open`
- `0x18000e4e5`: `ODBC_CONNECTION::Open`

## pseudocode

```c
_BOOL8 __fastcall ODBC_CONNECTION::Open(
        SQLHENV *this,
        SQLCHAR *ServerName,
        SQLCHAR *UserName,
        SQLCHAR *Authentication,
        int a5)
{
  SQLRETURN v9; // ax
  char v10; // cl
  BOOL v11; // ebx
  SQLHDBC *v12; // rsi
  SQLRETURN v13; // ax
  char v14; // cl
  SQLRETURN v15; // ax
  __int16 v16; // r9
  unsigned int NameLength2; // [rsp+20h] [rbp-B8h]
  const char *v19[2]; // [rsp+50h] [rbp-88h] BYREF
  _BYTE v20[32]; // [rsp+60h] [rbp-78h] BYREF
  const char *v21; // [rsp+80h] [rbp-58h]

  v9 = SQLAllocEnv(this);
  v10 = g_dwDebugFlags;
  *((_WORD *)this + 8) = v9;
  v11 = (unsigned __int16)v9 <= 1u;
  if ( (v10 & 3) != 0 && (v10 & 1) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\odbcconn.cxx",
      954,
      "ODBC_CONNECTION::Open",
      "SQLAllocEnv() returned ErrorCode %d. henv = %08x\n",
      v9,
      (unsigned int)*this);
  if ( v11 )
  {
    v12 = this + 1;
    v13 = SQLAllocConnect(*this, this + 1);
    v14 = g_dwDebugFlags;
    *((_WORD *)this + 8) = v13;
    v11 = (unsigned __int16)v13 <= 1u;
    if ( (v14 & 3) != 0 && (v14 & 1) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\odbcconn.cxx",
        972,
        "ODBC_CONNECTION::Open",
        "SQLAllocConnect() returns code %d. hdbc = %08x\n",
        v13,
        (unsigned int)*v12);
    if ( v11 )
    {
      v15 = SQLConnect(*v12, ServerName, -3, UserName, -3, Authentication, -3);
      *((_WORD *)this + 8) = v15;
      if ( (unsigned __int16)v15 <= 1u )
      {
        v11 = 1;
      }
      else
      {
        v11 = 0;
        if ( g_eventLog && a5 )
        {
          STR::STR((STR *)v20);
          v16 = *((_WORD *)this + 8);
          v19[0] = 0;
          ODBC_CONNECTION::GetLastErrorText((ODBC_CONNECTION *)this, (struct STR *)v20, 0, v16);
          v19[1] = v21;
          NameLength2 = *((__int16 *)this + 8);
          v19[0] = (const char *)ServerName;
          EVENT_LOG::LogEvent((EVENT_LOG *)g_eventLog, 0xC0000005, 2u, v19, NameLength2);
          STR::~STR((STR *)v20);
        }
      }
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 1) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\odbcconn.cxx",
          1054,
          "ODBC_CONNECTION::Open",
          "SQLConnect( %s, %s, %s) returns code %d.\n",
          (const char *)ServerName,
          (const char *)UserName,
          (const char *)Authentication,
          *((__int16 *)this + 8));
    }
  }
  *((_DWORD *)this + 5) = v11;
  if ( !v11 )
    SetLastError(0x1Fu);
  return v11;
}

```

## disassembly

```asm
0x18000e300  push    rbx
0x18000e302  push    rbp
0x18000e303  push    rsi
0x18000e304  push    rdi
0x18000e305  push    r12
0x18000e307  push    r14
0x18000e309  push    r15
0x18000e30b  sub     rsp, 0A0h
0x18000e312  mov     rax, cs:__security_cookie
0x18000e319  xor     rax, rsp
0x18000e31c  mov     [rsp+0D8h+var_40], rax
0x18000e324  mov     r15, r9
0x18000e327  mov     r14, r8
0x18000e32a  mov     rbp, rdx
0x18000e32d  mov     rdi, rcx
0x18000e330  call    cs:__imp_SQLAllocEnv
0x18000e336  mov     ecx, cs:g_dwDebugFlags
0x18000e33c  xor     ebx, ebx
0x18000e33e  movsx   r10d, ax
0x18000e342  mov     [rdi+10h], r10w
0x18000e347  lea     r12d, [rbx+1]
0x18000e34b  cmp     r10w, r12w
0x18000e34f  setbe   bl
0x18000e352  test    cl, 3
0x18000e355  setnz   dl
0x18000e358  test    r12b, cl
0x18000e35b  setnz   al
0x18000e35e  test    al, dl
0x18000e360  jz      short loc_18000E39C
0x18000e362  mov     rax, [rdi]
0x18000e365  lea     r9, aOdbcConnection_4; "ODBC_CONNECTION::Open"
0x18000e36c  mov     rcx, cs:g_pDebug
0x18000e373  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x18000e37a  mov     qword ptr [rsp+0D8h+NameLength3], rax
0x18000e37f  mov     r8d, 3BAh
0x18000e385  lea     rax, aSqlallocenvRet; "SQLAllocEnv() returned ErrorCode %d. he"...
0x18000e38c  mov     dword ptr [rsp+0D8h+Authentication], r10d
0x18000e391  mov     qword ptr [rsp+0D8h+NameLength2], rax
0x18000e396  call    cs:__imp_PuDbgPrint
0x18000e39c  test    ebx, ebx
0x18000e39e  jz      loc_18000E525
0x18000e3a4  mov     rcx, [rdi]; EnvironmentHandle
0x18000e3a7  lea     rsi, [rdi+8]
0x18000e3ab  mov     rdx, rsi; ConnectionHandle
0x18000e3ae  call    cs:__imp_SQLAllocConnect
0x18000e3b4  mov     ecx, cs:g_dwDebugFlags
0x18000e3ba  xor     ebx, ebx
0x18000e3bc  cmp     ax, r12w
0x18000e3c0  mov     [rdi+10h], ax
0x18000e3c4  setbe   bl
0x18000e3c7  test    cl, 3
0x18000e3ca  setnz   dl
0x18000e3cd  test    r12b, cl
0x18000e3d0  setnz   cl
0x18000e3d3  test    cl, dl
0x18000e3d5  jz      short loc_18000E413
0x18000e3d7  movsx   ecx, ax
0x18000e3da  lea     r9, aOdbcConnection_4; "ODBC_CONNECTION::Open"
0x18000e3e1  mov     rax, [rsi]
0x18000e3e4  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x18000e3eb  mov     qword ptr [rsp+0D8h+NameLength3], rax
0x18000e3f0  mov     r8d, 3CCh
0x18000e3f6  mov     dword ptr [rsp+0D8h+Authentication], ecx
0x18000e3fa  lea     rax, aSqlallocconnec; "SQLAllocConnect() returns code %d. hdbc"...
0x18000e401  mov     rcx, cs:g_pDebug
0x18000e408  mov     qword ptr [rsp+0D8h+NameLength2], rax
0x18000e40d  call    cs:__imp_PuDbgPrint
0x18000e413  test    ebx, ebx
0x18000e415  jz      loc_18000E525
0x18000e41b  mov     rcx, [rsi]; ConnectionHandle
0x18000e41e  mov     eax, 0FFFFFFFDh
0x18000e423  mov     [rsp+0D8h+NameLength3], ax; NameLength3
0x18000e428  mov     r8d, eax; NameLength1
0x18000e42b  mov     [rsp+0D8h+Authentication], r15; Authentication
0x18000e430  mov     r9, r14; UserName
0x18000e433  mov     rdx, rbp; ServerName
0x18000e436  mov     [rsp+0D8h+NameLength2], ax; NameLength2
0x18000e43b  call    cs:__imp_SQLConnect
0x18000e441  mov     [rdi+10h], ax
0x18000e445  cmp     ax, r12w
0x18000e449  jbe     short loc_18000E4C9
0x18000e44b  xor     ebx, ebx
0x18000e44d  cmp     cs:?g_eventLog@@3PEAVEVENT_LOG@@EA, rbx; EVENT_LOG * g_eventLog
0x18000e454  jz      short loc_18000E4CC
0x18000e456  cmp     [rsp+0D8h+arg_20], ebx
0x18000e45d  jz      short loc_18000E4CC
0x18000e45f  lea     rcx, [rsp+0D8h+var_78]
0x18000e464  call    cs:__imp_??0STR@@QEAA@XZ; STR::STR(void)
0x18000e46a  movzx   r9d, word ptr [rdi+10h]; __int16
0x18000e46f  lea     rdx, [rsp+0D8h+var_78]; struct STR *
0x18000e474  xorps   xmm0, xmm0
0x18000e477  xor     r8d, r8d; void *
0x18000e47a  mov     rcx, rdi; this
0x18000e47d  movups  [rsp+0D8h+var_88], xmm0
0x18000e482  call    ?GetLastErrorText@ODBC_CONNECTION@@QEBAHPEAVSTR@@PEAXF@Z; ODBC_CONNECTION::GetLastErrorText(STR *,void *,short)
0x18000e487  mov     rax, [rsp+0D8h+var_58]
0x18000e48f  lea     r8d, [rbx+2]
0x18000e493  mov     rcx, cs:?g_eventLog@@3PEAVEVENT_LOG@@EA; EVENT_LOG * g_eventLog
0x18000e49a  lea     r9, [rsp+0D8h+var_88]
0x18000e49f  mov     qword ptr [rsp+0D8h+var_88+8], rax
0x18000e4a4  mov     edx, 0C0000005h
0x18000e4a9  movsx   eax, word ptr [rdi+10h]
0x18000e4ad  mov     dword ptr [rsp+0D8h+NameLength2], eax
0x18000e4b1  mov     qword ptr [rsp+0D8h+var_88], rbp
0x18000e4b6  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBDK@Z; EVENT_LOG::LogEvent(ulong,ushort,char const * * const,ulong)
0x18000e4bc  lea     rcx, [rsp+0D8h+var_78]
0x18000e4c1  call    cs:__imp_??1STR@@QEAA@XZ; STR::~STR(void)
0x18000e4c7  jmp     short loc_18000E4CC
0x18000e4c9  mov     ebx, r12d
0x18000e4cc  mov     eax, cs:g_dwDebugFlags
0x18000e4d2  test    al, 3
0x18000e4d4  setnz   cl
0x18000e4d7  test    r12b, al
0x18000e4da  setnz   al
0x18000e4dd  test    al, cl
0x18000e4df  jz      short loc_18000E525
0x18000e4e1  movsx   eax, word ptr [rdi+10h]
0x18000e4e5  lea     r9, aOdbcConnection_4; "ODBC_CONNECTION::Open"
0x18000e4ec  mov     rcx, cs:g_pDebug
0x18000e4f3  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x18000e4fa  mov     [rsp+0D8h+var_98], eax
0x18000e4fe  mov     r8d, 41Eh
0x18000e504  mov     [rsp+0D8h+var_A0], r15
0x18000e509  lea     rax, aSqlconnectSSSR; "SQLConnect( %s, %s, %s) returns code %d"...
0x18000e510  mov     qword ptr [rsp+0D8h+NameLength3], r14
0x18000e515  mov     [rsp+0D8h+Authentication], rbp
0x18000e51a  mov     qword ptr [rsp+0D8h+NameLength2], rax
0x18000e51f  call    cs:__imp_PuDbgPrint
0x18000e525  mov     [rdi+14h], ebx
0x18000e528  test    ebx, ebx
0x18000e52a  jnz     short loc_18000E535
0x18000e52c  lea     ecx, [rbx+1Fh]; dwErrCode
0x18000e52f  call    cs:__imp_SetLastError
0x18000e535  mov     eax, ebx
0x18000e537  mov     rcx, [rsp+0D8h+var_40]
0x18000e53f  xor     rcx, rsp; StackCookie
0x18000e542  call    __security_check_cookie
0x18000e547  add     rsp, 0A0h
0x18000e54e  pop     r15
0x18000e550  pop     r14
0x18000e552  pop     r12
0x18000e554  pop     rdi
0x18000e555  pop     rsi
0x18000e556  pop     rbp
0x18000e557  pop     rbx
0x18000e558  retn
```
