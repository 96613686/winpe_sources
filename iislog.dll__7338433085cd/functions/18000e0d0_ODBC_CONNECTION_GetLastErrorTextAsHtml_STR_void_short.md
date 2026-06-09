# ODBC_CONNECTION::GetLastErrorTextAsHtml(STR *,void *,short)

- ea: `0x18000e0d0`
- end: `0x18000e293`
- name: `?GetLastErrorTextAsHtml@ODBC_CONNECTION@@QEBAHPEAVSTR@@PEAXF@Z`
- size: `451`
- prototype: `int(ODBC_CONNECTION *__hidden this, struct STR *, void *, __int16)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18000e0d0`
- `0x18000eca0`

## import_xrefs

- `msvcrt!sprintf_s` at `0x18000e1d7`
- `msvcrt!sprintf_s` at `0x18000e1d7`
- `IisRTL!PuDbgPrint` at `0x18000e23f`
- `IisRTL!PuDbgPrint` at `0x18000e23f`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x18000e198`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x18000e1e7`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x18000e198`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x18000e1e7`
- `IisRTL!?LoadStringA@STR@@QEAAHKPEBDK@Z` at `0x18000e266`
- `IisRTL!?LoadStringA@STR@@QEAAHKPEBDK@Z` at `0x18000e266`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x18000e12e`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x18000e12e`
- `KERNEL32!SetLastError` at `0x18000e24a`
- `KERNEL32!SetLastError` at `0x18000e24a`
- `KERNEL32!GetLastError` at `0x18000e255`
- `KERNEL32!GetLastError` at `0x18000e255`
- `ODBC32!__imp_SQLError` at `0x18000e177`
- `ODBC32!__imp_SQLError` at `0x18000e177`

## string_xrefs

- `0x18000e238`: `inetsrv\iis\svcs\infocomm\log\plugin\odbcconn.cxx`

## pseudocode

```c
__int64 __fastcall ODBC_CONNECTION::GetLastErrorTextAsHtml(
        ODBC_CONNECTION *this,
        struct STR *a2,
        void *a3,
        unsigned __int16 a4)
{
  void *v7; // rdx
  void *v8; // rcx
  SQLRETURN v9; // ax
  int v10; // ebx
  unsigned int v11; // edi
  DWORD LastError; // eax
  SQLSMALLINT TextLength[2]; // [rsp+40h] [rbp-C0h] BYREF
  SQLINTEGER NativeError; // [rsp+44h] [rbp-BCh] BYREF
  SQLCHAR Sqlstate[40]; // [rsp+48h] [rbp-B8h] BYREF
  SQLCHAR MessageText[528]; // [rsp+70h] [rbp-90h] BYREF
  char Buffer[624]; // [rsp+280h] [rbp+180h] BYREF

  if ( a4 <= 1u )
  {
    LastError = GetLastError();
    return (unsigned int)STR::LoadStringA(a2, LastError, 0, 0);
  }
  TextLength[0] = 0;
  NativeError = 0;
  if ( !STR::Copy(a2, "<UL>") )
    return 0;
  while ( 1 )
  {
    v7 = (void *)*((_QWORD *)this + 1);
    v8 = *(void **)this;
    TextLength[0] = 512;
    v9 = SQLError(v8, v7, a3, Sqlstate, &NativeError, MessageText, 512, TextLength);
    v10 = v9;
    if ( (unsigned __int16)v9 > 1u )
      break;
    sprintf_s(
      Buffer,
      0x264u,
      "<LI>[State=%s][Error=%d]%s\n",
      (const char *)Sqlstate,
      NativeError,
      (const char *)MessageText);
    if ( !STR::Append(a2, Buffer) )
    {
      v11 = 0;
      if ( (unsigned __int16)v10 < 2u )
        return v11;
LABEL_11:
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\odbcconn.cxx",
          1554,
          "ODBC_CONNECTION::GetLastErrorTextAsHtml",
          "[GetLastErrorText] SqlError() returned error %d.\n",
          v10);
      SetLastError(0x1Fu);
      return 0;
    }
LABEL_8:
    if ( (unsigned __int16)v10 > 1u )
      goto LABEL_11;
  }
  if ( v9 != 100 )
    goto LABEL_8;
  v11 = 1;
  if ( STR::Append(a2, "</UL>") )
    return v11;
  return 0;
}

```

## disassembly

```asm
0x18000e0d0  push    rbp
0x18000e0d2  push    rbx
0x18000e0d3  push    rsi
0x18000e0d4  push    rdi
0x18000e0d5  push    r12
0x18000e0d7  push    r13
0x18000e0d9  push    r14
0x18000e0db  push    r15
0x18000e0dd  lea     rbp, [rsp-408h]
0x18000e0e5  sub     rsp, 508h
0x18000e0ec  mov     rax, cs:__security_cookie
0x18000e0f3  xor     rax, rsp
0x18000e0f6  mov     [rbp+440h+var_50], rax
0x18000e0fd  mov     r12d, 1
0x18000e103  mov     r14, r8
0x18000e106  mov     rsi, rdx
0x18000e109  mov     rdi, rcx
0x18000e10c  cmp     r9w, r12w
0x18000e110  jbe     loc_18000E255
0x18000e116  xor     r15d, r15d
0x18000e119  lea     rdx, aUl; "<UL>"
0x18000e120  mov     rcx, rsi
0x18000e123  mov     [rsp+540h+var_500], r15w
0x18000e129  mov     [rsp+540h+var_4FC], r15d
0x18000e12e  call    cs:__imp_?Copy@STR@@QEAAHPEBD@Z; STR::Copy(char const *)
0x18000e134  test    eax, eax
0x18000e136  jz      short loc_18000E1A6
0x18000e138  mov     r13d, 200h
0x18000e13e  mov     rdx, [rdi+8]; ConnectionHandle
0x18000e142  lea     rax, [rsp+540h+var_500]
0x18000e147  mov     rcx, [rdi]; EnvironmentHandle
0x18000e14a  lea     r9, [rsp+540h+Sqlstate]; Sqlstate
0x18000e14f  mov     [rsp+540h+TextLength], rax; TextLength
0x18000e154  mov     r8, r14; StatementHandle
0x18000e157  lea     rax, [rsp+540h+var_4D0]
0x18000e15c  mov     [rsp+540h+BufferLength], r13w; BufferLength
0x18000e162  mov     [rsp+540h+MessageText], rax; MessageText
0x18000e167  lea     rax, [rsp+540h+var_4FC]
0x18000e16c  mov     [rsp+540h+NativeError], rax; NativeError
0x18000e171  mov     [rsp+540h+var_500], r13w
0x18000e177  call    cs:__imp_SQLError
0x18000e17d  movsx   ebx, ax
0x18000e180  cmp     bx, r12w
0x18000e184  jbe     short loc_18000E1AD
0x18000e186  cmp     ebx, 64h ; 'd'
0x18000e189  jnz     short loc_18000E1F1
0x18000e18b  lea     rdx, aUl_0; "</UL>"
0x18000e192  mov     rcx, rsi
0x18000e195  mov     edi, r12d
0x18000e198  call    cs:__imp_?Append@STR@@QEAAHPEBD@Z; STR::Append(char const *)
0x18000e19e  test    eax, eax
0x18000e1a0  jnz     loc_18000E26E
0x18000e1a6  xor     eax, eax
0x18000e1a8  jmp     loc_18000E270
0x18000e1ad  lea     rax, [rsp+540h+var_4D0]
0x18000e1b2  mov     edx, 264h; BufferCount
0x18000e1b7  mov     [rsp+540h+MessageText], rax
0x18000e1bc  lea     r9, [rsp+540h+Sqlstate]
0x18000e1c1  mov     eax, [rsp+540h+var_4FC]
0x18000e1c5  lea     r8, aLiStateSErrorD; "<LI>[State=%s][Error=%d]%s\n"
0x18000e1cc  lea     rcx, [rbp+440h+Buffer]; Buffer
0x18000e1d3  mov     dword ptr [rsp+540h+NativeError], eax
0x18000e1d7  call    cs:__imp_sprintf_s
0x18000e1dd  lea     rdx, [rbp+440h+Buffer]
0x18000e1e4  mov     rcx, rsi
0x18000e1e7  call    cs:__imp_?Append@STR@@QEAAHPEBD@Z; STR::Append(char const *)
0x18000e1ed  test    eax, eax
0x18000e1ef  jz      short loc_18000E1FD
0x18000e1f1  cmp     bx, r12w
0x18000e1f5  jbe     loc_18000E13E
0x18000e1fb  jmp     short loc_18000E20B
0x18000e1fd  mov     edi, r15d
0x18000e200  test    bx, bx
0x18000e203  jz      short loc_18000E26E
0x18000e205  cmp     bx, r12w
0x18000e209  jz      short loc_18000E26E
0x18000e20b  test    byte ptr cs:g_dwDebugFlags, 3
0x18000e212  jz      short loc_18000E245
0x18000e214  mov     rcx, cs:g_pDebug
0x18000e21b  lea     rax, aGetlasterrorte_1; "[GetLastErrorText] SqlError() returned "...
0x18000e222  mov     dword ptr [rsp+540h+MessageText], ebx
0x18000e226  lea     r9, aOdbcConnection; "ODBC_CONNECTION::GetLastErrorTextAsHtml"
0x18000e22d  mov     r8d, 612h
0x18000e233  mov     [rsp+540h+NativeError], rax
0x18000e238  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x18000e23f  call    cs:__imp_PuDbgPrint
0x18000e245  mov     ecx, 1Fh; dwErrCode
0x18000e24a  call    cs:__imp_SetLastError
0x18000e250  mov     edi, r15d
0x18000e253  jmp     short loc_18000E26E
0x18000e255  call    cs:__imp_GetLastError
0x18000e25b  xor     r9d, r9d
0x18000e25e  xor     r8d, r8d
0x18000e261  mov     edx, eax
0x18000e263  mov     rcx, rsi
0x18000e266  call    cs:__imp_?LoadStringA@STR@@QEAAHKPEBDK@Z; STR::LoadStringA(ulong,char const *,ulong)
0x18000e26c  mov     edi, eax
0x18000e26e  mov     eax, edi
0x18000e270  mov     rcx, [rbp+440h+var_50]
0x18000e277  xor     rcx, rsp; StackCookie
0x18000e27a  call    __security_check_cookie
0x18000e27f  add     rsp, 508h
0x18000e286  pop     r15
0x18000e288  pop     r14
0x18000e28a  pop     r13
0x18000e28c  pop     r12
0x18000e28e  pop     rdi
0x18000e28f  pop     rsi
0x18000e290  pop     rbx
0x18000e291  pop     rbp
0x18000e292  retn
```
