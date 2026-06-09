# ODBC_CONNECTION::GetLastErrorText(STR *,void *,short)

- ea: `0x18000df20`
- end: `0x18000e0c5`
- name: `?GetLastErrorText@ODBC_CONNECTION@@QEBAHPEAVSTR@@PEAXF@Z`
- size: `421`
- prototype: `int(ODBC_CONNECTION *__hidden this, struct STR *, void *, __int16)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000e300`

## callees

- `0x18000df20`
- `0x18000eca0`

## import_xrefs

- `msvcrt!sprintf_s` at `0x18000e00a`
- `msvcrt!sprintf_s` at `0x18000e00a`
- `IisRTL!PuDbgPrint` at `0x18000e071`
- `IisRTL!PuDbgPrint` at `0x18000e071`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x18000e01a`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x18000e01a`
- `IisRTL!?LoadStringA@STR@@QEAAHKPEBDK@Z` at `0x18000e098`
- `IisRTL!?LoadStringA@STR@@QEAAHKPEBDK@Z` at `0x18000e098`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x18000df79`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x18000df79`
- `KERNEL32!SetLastError` at `0x18000e07c`
- `KERNEL32!SetLastError` at `0x18000e07c`
- `KERNEL32!GetLastError` at `0x18000e087`
- `KERNEL32!GetLastError` at `0x18000e087`
- `ODBC32!__imp_SQLError` at `0x18000dfc6`
- `ODBC32!__imp_SQLError` at `0x18000dfc6`

## string_xrefs

- `0x18000e06a`: `inetsrv\iis\svcs\infocomm\log\plugin\odbcconn.cxx`

## pseudocode

```c
int __fastcall ODBC_CONNECTION::GetLastErrorText(ODBC_CONNECTION *this, struct STR *a2, void *a3, unsigned __int16 a4)
{
  int result; // eax
  int v8; // edi
  void *v9; // rdx
  SQLRETURN v10; // ax
  int v11; // ebx
  DWORD LastError; // eax
  SQLSMALLINT TextLength[2]; // [rsp+40h] [rbp-C0h] BYREF
  SQLINTEGER NativeError; // [rsp+44h] [rbp-BCh] BYREF
  SQLCHAR Sqlstate[40]; // [rsp+48h] [rbp-B8h] BYREF
  SQLCHAR MessageText[528]; // [rsp+70h] [rbp-90h] BYREF
  char Buffer[624]; // [rsp+280h] [rbp+180h] BYREF

  if ( a4 <= 1u )
  {
    LastError = GetLastError();
    return STR::LoadStringA(a2, LastError, 0, 0);
  }
  TextLength[0] = 0;
  NativeError = 0;
  result = STR::Copy(a2, 0);
  if ( result )
  {
    v8 = 1;
    while ( 1 )
    {
      v9 = (void *)*((_QWORD *)this + 1);
      TextLength[0] = 512;
      v10 = SQLError(*(SQLHENV *)this, v9, a3, Sqlstate, &NativeError, MessageText, 512, TextLength);
      v11 = v10;
      if ( (unsigned __int16)v10 <= 1u )
      {
        sprintf_s(
          Buffer,
          0x264u,
          "[State=%s][Error=%d]%s\n",
          (const char *)Sqlstate,
          NativeError,
          (const char *)MessageText);
        if ( !STR::Append(a2, Buffer) )
        {
          v8 = 0;
          if ( (unsigned __int16)v11 < 2u )
            return v8;
LABEL_11:
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\odbcconn.cxx",
              1439,
              "ODBC_CONNECTION::GetLastErrorText",
              "[GetLastErrorText] SqlError() returned error %d.\n",
              v11);
          SetLastError(0x1Fu);
          return 0;
        }
      }
      else if ( v10 == 100 )
      {
        return v8;
      }
      if ( (unsigned __int16)v11 > 1u )
        goto LABEL_11;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000df20  push    rbp
0x18000df22  push    rbx
0x18000df23  push    rsi
0x18000df24  push    rdi
0x18000df25  push    r12
0x18000df27  push    r13
0x18000df29  push    r14
0x18000df2b  push    r15
0x18000df2d  lea     rbp, [rsp-408h]
0x18000df35  sub     rsp, 508h
0x18000df3c  mov     rax, cs:__security_cookie
0x18000df43  xor     rax, rsp
0x18000df46  mov     [rbp+440h+var_50], rax
0x18000df4d  mov     r13d, 1
0x18000df53  mov     r15, r8
0x18000df56  mov     rsi, rdx
0x18000df59  mov     r14, rcx
0x18000df5c  cmp     r9w, r13w
0x18000df60  jbe     loc_18000E087
0x18000df66  xor     r12d, r12d
0x18000df69  xor     edx, edx
0x18000df6b  mov     rcx, rsi
0x18000df6e  mov     [rsp+540h+var_500], r12w
0x18000df74  mov     [rsp+540h+var_4FC], r12d
0x18000df79  call    cs:__imp_?Copy@STR@@QEAAHPEBD@Z; STR::Copy(char const *)
0x18000df7f  test    eax, eax
0x18000df81  jz      loc_18000E0A2
0x18000df87  mov     edi, r13d
0x18000df8a  mov     rdx, [r14+8]; ConnectionHandle
0x18000df8e  lea     rax, [rsp+540h+var_500]
0x18000df93  mov     [rsp+540h+TextLength], rax; TextLength
0x18000df98  lea     r9, [rsp+540h+Sqlstate]; Sqlstate
0x18000df9d  mov     ecx, 200h
0x18000dfa2  lea     rax, [rsp+540h+var_4D0]
0x18000dfa7  mov     [rsp+540h+BufferLength], cx; BufferLength
0x18000dfac  mov     r8, r15; StatementHandle
0x18000dfaf  mov     [rsp+540h+MessageText], rax; MessageText
0x18000dfb4  lea     rax, [rsp+540h+var_4FC]
0x18000dfb9  mov     [rsp+540h+var_500], cx
0x18000dfbe  mov     rcx, [r14]; EnvironmentHandle
0x18000dfc1  mov     [rsp+540h+NativeError], rax; NativeError
0x18000dfc6  call    cs:__imp_SQLError
0x18000dfcc  movsx   ebx, ax
0x18000dfcf  cmp     bx, r13w
0x18000dfd3  jbe     short loc_18000DFE0
0x18000dfd5  cmp     ebx, 64h ; 'd'
0x18000dfd8  jz      loc_18000E0A0
0x18000dfde  jmp     short loc_18000E024
0x18000dfe0  lea     rax, [rsp+540h+var_4D0]
0x18000dfe5  mov     edx, 264h; BufferCount
0x18000dfea  mov     [rsp+540h+MessageText], rax
0x18000dfef  lea     r9, [rsp+540h+Sqlstate]
0x18000dff4  mov     eax, [rsp+540h+var_4FC]
0x18000dff8  lea     r8, aStateSErrorDS; "[State=%s][Error=%d]%s\n"
0x18000dfff  lea     rcx, [rbp+440h+Buffer]; Buffer
0x18000e006  mov     dword ptr [rsp+540h+NativeError], eax
0x18000e00a  call    cs:__imp_sprintf_s
0x18000e010  lea     rdx, [rbp+440h+Buffer]
0x18000e017  mov     rcx, rsi
0x18000e01a  call    cs:__imp_?Append@STR@@QEAAHPEBD@Z; STR::Append(char const *)
0x18000e020  test    eax, eax
0x18000e022  jz      short loc_18000E02F
0x18000e024  cmp     bx, r13w
0x18000e028  ja      short loc_18000E03D
0x18000e02a  jmp     loc_18000DF8A
0x18000e02f  mov     edi, r12d
0x18000e032  test    bx, bx
0x18000e035  jz      short loc_18000E0A0
0x18000e037  cmp     bx, r13w
0x18000e03b  jz      short loc_18000E0A0
0x18000e03d  test    byte ptr cs:g_dwDebugFlags, 3
0x18000e044  jz      short loc_18000E077
0x18000e046  mov     rcx, cs:g_pDebug
0x18000e04d  lea     rax, aGetlasterrorte_1; "[GetLastErrorText] SqlError() returned "...
0x18000e054  mov     dword ptr [rsp+540h+MessageText], ebx
0x18000e058  lea     r9, aOdbcConnection_2; "ODBC_CONNECTION::GetLastErrorText"
0x18000e05f  mov     r8d, 59Fh
0x18000e065  mov     [rsp+540h+NativeError], rax
0x18000e06a  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x18000e071  call    cs:__imp_PuDbgPrint
0x18000e077  mov     ecx, 1Fh; dwErrCode
0x18000e07c  call    cs:__imp_SetLastError
0x18000e082  mov     edi, r12d
0x18000e085  jmp     short loc_18000E0A0
0x18000e087  call    cs:__imp_GetLastError
0x18000e08d  xor     r9d, r9d
0x18000e090  xor     r8d, r8d
0x18000e093  mov     edx, eax
0x18000e095  mov     rcx, rsi
0x18000e098  call    cs:__imp_?LoadStringA@STR@@QEAAHKPEBDK@Z; STR::LoadStringA(ulong,char const *,ulong)
0x18000e09e  mov     edi, eax
0x18000e0a0  mov     eax, edi
0x18000e0a2  mov     rcx, [rbp+440h+var_50]
0x18000e0a9  xor     rcx, rsp; StackCookie
0x18000e0ac  call    __security_check_cookie
0x18000e0b1  add     rsp, 508h
0x18000e0b8  pop     r15
0x18000e0ba  pop     r14
0x18000e0bc  pop     r13
0x18000e0be  pop     r12
0x18000e0c0  pop     rdi
0x18000e0c1  pop     rsi
0x18000e0c2  pop     rbx
0x18000e0c3  pop     rbp
0x18000e0c4  retn
```
