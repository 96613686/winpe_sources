# CMSMQRuleHandler::InvokeEXE(IMSMQPropertyBag *)

- ea: `0x18000897c`
- end: `0x180008d0b`
- name: `?InvokeEXE@CMSMQRuleHandler@@QEAAJPEAUIMSMQPropertyBag@@@Z`
- size: `911`
- prototype: `__int64 __fastcall(CMSMQRuleHandler *__hidden this, struct IMSMQPropertyBag *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006bec`

## callees

- `0x180004d20`
- `0x180004dfc`
- `0x18000897c`
- `0x180008d68`
- `0x180009ab0`
- `0x180009c74`
- `0x180014d30`
- `0x18001e35a`
- `0x180022010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180008cbd`
- `KERNEL32!WaitForSingleObject` at `0x180008cbd`
- `KERNEL32!CloseHandle` at `0x180008ca7`
- `KERNEL32!CloseHandle` at `0x180008cc7`
- `KERNEL32!CloseHandle` at `0x180008ca7`
- `KERNEL32!CloseHandle` at `0x180008cc7`
- `KERNEL32!GetLastError` at `0x180008bc4`
- `KERNEL32!GetLastError` at `0x180008bc4`
- `KERNEL32!CreateProcessW` at `0x180008ba4`
- `KERNEL32!CreateProcessW` at `0x180008ba4`

## pseudocode

```c
__int64 __fastcall CMSMQRuleHandler::InvokeEXE(CMSMQRuleHandler *this, struct IMSMQPropertyBag *a2)
{
  int v4; // eax
  unsigned int v5; // eax
  WCHAR **v6; // rbx
  wchar_t *v7; // r8
  WCHAR *v8; // rdx
  const WCHAR *v9; // rcx
  char LastError; // al
  unsigned int v11; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-69h] BYREF
  struct IMSMQPropertyBag *v14; // [rsp+78h] [rbp-51h]
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-49h] BYREF
  __int16 v16; // [rsp+130h] [rbp+67h] BYREF
  int v17; // [rsp+138h] [rbp+6Fh] BYREF
  wchar_t **v18; // [rsp+140h] [rbp+77h] BYREF
  const WCHAR **v19; // [rsp+148h] [rbp+7Fh] BYREF

  v14 = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct IMSMQPropertyBag *))(*(_QWORD *)a2 + 8LL))(a2);
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  StartupInfo.cb = 104;
  StartupInfo.dwFlags = 1;
  if ( *((_BYTE *)this + 173) )
    StartupInfo.wShowWindow = 5;
  else
    StartupInfo.wShowWindow = 0;
  v19 = 0;
  v18 = 0;
  v4 = CMSMQRuleHandler::PrepareEXECommandLine(this, a2, (struct _bstr_t *)&v19, (struct _bstr_t *)&v18);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4);
    v16 = 230;
    v17 = -1072820724;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v5 = mqwcslen(L"trigobjs/rulehdlr");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v5 + 1),
        L"trigobjs/rulehdlr",
        2,
        &v16,
        4,
        &v17,
        0,
        0);
    }
    _bstr_t::_Free((_bstr_t *)&v18);
    _bstr_t::_Free((_bstr_t *)&v19);
    if ( a2 )
      (*(void (__fastcall **)(struct IMSMQPropertyBag *))(*(_QWORD *)a2 + 16LL))(a2);
    return 3222146572LL;
  }
  v6 = v18;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    if ( v18 )
      v7 = *v18;
    else
      v7 = 0;
    WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), v7);
  }
  if ( v6 )
    v8 = *v6;
  else
    v8 = 0;
  if ( v19 )
    v9 = *v19;
  else
    v9 = 0;
  if ( !CreateProcessW(v9, v8, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), LastError);
    }
    v16 = 240;
    v17 = -1072820724;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v11 = mqwcslen(L"trigobjs/rulehdlr");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v11 + 1),
        L"trigobjs/rulehdlr",
        2,
        &v16,
        4,
        &v17,
        0,
        0);
    }
    _bstr_t::_Free((_bstr_t *)&v18);
    _bstr_t::_Free((_bstr_t *)&v19);
    if ( a2 )
      (*(void (__fastcall **)(struct IMSMQPropertyBag *))(*(_QWORD *)a2 + 16LL))(a2);
    return 3222146572LL;
  }
  CloseHandle(ProcessInformation.hThread);
  if ( *((_BYTE *)this + 172) )
    WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
  CloseHandle(ProcessInformation.hProcess);
  _bstr_t::_Free((_bstr_t *)&v18);
  _bstr_t::_Free((_bstr_t *)&v19);
  if ( a2 )
    (*(void (__fastcall **)(struct IMSMQPropertyBag *))(*(_QWORD *)a2 + 16LL))(a2);
  return 0;
}

```

## disassembly

```asm
0x18000897c  push    rbp
0x18000897e  push    rbx
0x18000897f  push    rsi
0x180008980  push    rdi
0x180008981  push    r12
0x180008983  push    r14
0x180008985  push    r15
0x180008987  lea     rbp, [rsp-27h]
0x18000898c  sub     rsp, 0F0h
0x180008993  mov     rdi, rdx
0x180008996  mov     rsi, rcx
0x180008999  mov     [rbp+57h+var_A8], rdx
0x18000899d  xor     r15d, r15d
0x1800089a0  test    rdx, rdx
0x1800089a3  jz      short loc_1800089B5
0x1800089a5  mov     rax, [rdx]
0x1800089a8  mov     rcx, rdx
0x1800089ab  mov     rax, [rax+8]
0x1800089af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089b4  nop
0x1800089b5  mov     ebx, 68h ; 'h'
0x1800089ba  mov     r8d, ebx; Size
0x1800089bd  xor     edx, edx; Val
0x1800089bf  lea     rcx, [rbp+57h+StartupInfo]; void *
0x1800089c3  call    memset_0
0x1800089c8  xorps   xmm0, xmm0
0x1800089cb  xor     eax, eax
0x1800089cd  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x1800089d1  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x1800089d5  mov     [rbp+57h+StartupInfo.cb], ebx
0x1800089d8  lea     r12d, [rbx-67h]
0x1800089dc  mov     [rbp+57h+StartupInfo.dwFlags], r12d
0x1800089e0  cmp     [rsi+0ADh], r15b
0x1800089e7  jz      short loc_1800089F2
0x1800089e9  lea     eax, [rbx-63h]
0x1800089ec  mov     [rbp+57h+StartupInfo.wShowWindow], ax
0x1800089f0  jmp     short loc_1800089F7
0x1800089f2  mov     [rbp+57h+StartupInfo.wShowWindow], r15w
0x1800089f7  mov     [rbp+57h+arg_18], r15
0x1800089fb  mov     [rbp+57h+arg_10], r15
0x1800089ff  lea     r9, [rbp+57h+arg_10]; struct _bstr_t *
0x180008a03  lea     r8, [rbp+57h+arg_18]; struct _bstr_t *
0x180008a07  mov     rdx, rdi; struct IMSMQPropertyBag *
0x180008a0a  mov     rcx, rsi; this
0x180008a0d  call    ?PrepareEXECommandLine@CMSMQRuleHandler@@QEAAJPEAUIMSMQPropertyBag@@PEAV_bstr_t@@1@Z; CMSMQRuleHandler::PrepareEXECommandLine(IMSMQPropertyBag *,_bstr_t *,_bstr_t *)
0x180008a12  mov     r8d, eax
0x180008a15  test    eax, eax
0x180008a17  jns     loc_180008B02
0x180008a1d  lea     r14, WPP_GLOBAL_Control
0x180008a24  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a2b  cmp     rcx, r14
0x180008a2e  jz      short loc_180008A64
0x180008a30  test    [rcx+1Ch], r12b
0x180008a34  jz      short loc_180008A64
0x180008a36  mov     rax, [rsi+90h]
0x180008a3d  test    rax, rax
0x180008a40  jz      short loc_180008A47
0x180008a42  mov     r9, [rax]
0x180008a45  jmp     short loc_180008A4A
0x180008a47  mov     r9, r15
0x180008a4a  mov     edx, 1Bh
0x180008a4f  mov     [rsp+120h+bInheritHandles], r8d; char
0x180008a54  lea     r8, WPP_07c04997ef9c358328a47f0c936100cf_Traceguids
0x180008a5b  mov     rcx, [rcx+10h]; LoggerHandle
0x180008a5f  call    WPP_SF_SD
0x180008a64  mov     eax, 0E6h
0x180008a69  mov     [rbp+57h+arg_0], ax
0x180008a6d  mov     [rbp+57h+arg_8], 0C00E0E0Ch
0x180008a74  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r15; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180008a7b  jz      short loc_180008AD9
0x180008a7d  lea     rbx, aTrigobjsRulehd; "trigobjs/rulehdlr"
0x180008a84  mov     rcx, rbx; wchar_t *
0x180008a87  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180008a8c  lea     r9d, [r12+rax]
0x180008a90  add     r9, r9
0x180008a93  mov     [rsp+120h+var_D0], r15
0x180008a98  mov     [rsp+120h+lpProcessInformation], r15
0x180008a9d  lea     rax, [rbp+57h+arg_8]
0x180008aa1  mov     [rsp+120h+lpStartupInfo], rax
0x180008aa6  mov     [rsp+120h+lpCurrentDirectory], 4
0x180008aaf  lea     rax, [rbp+57h+arg_0]
0x180008ab3  mov     [rsp+120h+lpEnvironment], rax
0x180008ab8  mov     qword ptr [rsp+120h+dwCreationFlags], 2
0x180008ac1  mov     qword ptr [rsp+120h+bInheritHandles], rbx
0x180008ac6  mov     r8d, r12d
0x180008ac9  mov     edx, r12d
0x180008acc  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180008ad3  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180008ad8  nop
0x180008ad9  lea     rcx, [rbp+57h+arg_10]; this
0x180008add  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180008ae2  nop
0x180008ae3  lea     rcx, [rbp+57h+arg_18]; this
0x180008ae7  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180008aec  nop
0x180008aed  test    rdi, rdi
0x180008af0  jz      loc_180008C9C
0x180008af6  mov     rax, [rdi]
0x180008af9  mov     rax, [rax+10h]
0x180008afd  jmp     loc_180008C93
0x180008b02  lea     r14, WPP_GLOBAL_Control
0x180008b09  mov     rbx, [rbp+57h+arg_10]
0x180008b0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b14  cmp     rcx, r14
0x180008b17  jz      short loc_180008B5A
0x180008b19  test    byte ptr [rcx+1Ch], 4
0x180008b1d  jz      short loc_180008B5A
0x180008b1f  test    rbx, rbx
0x180008b22  jz      short loc_180008B29
0x180008b24  mov     r8, [rbx]
0x180008b27  jmp     short loc_180008B2C
0x180008b29  mov     r8, r15
0x180008b2c  mov     rax, [rsi+90h]
0x180008b33  test    rax, rax
0x180008b36  jz      short loc_180008B3D
0x180008b38  mov     r9, [rax]
0x180008b3b  jmp     short loc_180008B40
0x180008b3d  mov     r9, r15
0x180008b40  mov     edx, 1Ch
0x180008b45  mov     qword ptr [rsp+120h+bInheritHandles], r8; wchar_t *
0x180008b4a  lea     r8, WPP_07c04997ef9c358328a47f0c936100cf_Traceguids
0x180008b51  mov     rcx, [rcx+10h]; LoggerHandle
0x180008b55  call    WPP_SF_SS
0x180008b5a  test    rbx, rbx
0x180008b5d  jz      short loc_180008B64
0x180008b5f  mov     rdx, [rbx]
0x180008b62  jmp     short loc_180008B67
0x180008b64  mov     rdx, r15; lpCommandLine
0x180008b67  mov     rax, [rbp+57h+arg_18]
0x180008b6b  test    rax, rax
0x180008b6e  jz      short loc_180008B75
0x180008b70  mov     rcx, [rax]
0x180008b73  jmp     short loc_180008B78
0x180008b75  mov     rcx, r15; lpApplicationName
0x180008b78  lea     rax, [rbp+57h+ProcessInformation]
0x180008b7c  mov     [rsp+120h+lpProcessInformation], rax; lpProcessInformation
0x180008b81  lea     rax, [rbp+57h+StartupInfo]
0x180008b85  mov     [rsp+120h+lpStartupInfo], rax; lpStartupInfo
0x180008b8a  mov     [rsp+120h+lpCurrentDirectory], r15; lpCurrentDirectory
0x180008b8f  mov     [rsp+120h+lpEnvironment], r15; lpEnvironment
0x180008b94  mov     [rsp+120h+dwCreationFlags], r15d; dwCreationFlags
0x180008b99  mov     [rsp+120h+bInheritHandles], r15d; bInheritHandles
0x180008b9e  xor     r9d, r9d; lpThreadAttributes
0x180008ba1  xor     r8d, r8d; lpProcessAttributes
0x180008ba4  call    cs:__imp_CreateProcessW
0x180008baa  test    eax, eax
0x180008bac  jnz     loc_180008CA3
0x180008bb2  mov     rax, cs:WPP_GLOBAL_Control
0x180008bb9  cmp     rax, r14
0x180008bbc  jz      short loc_180008BFE
0x180008bbe  test    [rax+1Ch], r12b
0x180008bc2  jz      short loc_180008BFE
0x180008bc4  call    cs:__imp_GetLastError
0x180008bca  mov     rcx, [rsi+90h]
0x180008bd1  test    rcx, rcx
0x180008bd4  jz      short loc_180008BDB
0x180008bd6  mov     r9, [rcx]
0x180008bd9  jmp     short loc_180008BDE
0x180008bdb  mov     r9, r15
0x180008bde  mov     edx, 1Dh
0x180008be3  mov     [rsp+120h+bInheritHandles], eax; char
0x180008be7  lea     r8, WPP_07c04997ef9c358328a47f0c936100cf_Traceguids
0x180008bee  mov     rcx, cs:WPP_GLOBAL_Control
0x180008bf5  mov     rcx, [rcx+10h]; LoggerHandle
0x180008bf9  call    WPP_SF_SD
0x180008bfe  mov     eax, 0F0h
0x180008c03  mov     [rbp+57h+arg_0], ax
0x180008c07  mov     [rbp+57h+arg_8], 0C00E0E0Ch
0x180008c0e  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r15; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180008c15  jz      short loc_180008C73
0x180008c17  lea     rbx, aTrigobjsRulehd; "trigobjs/rulehdlr"
0x180008c1e  mov     rcx, rbx; wchar_t *
0x180008c21  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180008c26  lea     r9d, [r12+rax]
0x180008c2a  add     r9, r9
0x180008c2d  mov     [rsp+120h+var_D0], r15
0x180008c32  mov     [rsp+120h+lpProcessInformation], r15
0x180008c37  lea     rax, [rbp+57h+arg_8]
0x180008c3b  mov     [rsp+120h+lpStartupInfo], rax
0x180008c40  mov     [rsp+120h+lpCurrentDirectory], 4
0x180008c49  lea     rax, [rbp+57h+arg_0]
0x180008c4d  mov     [rsp+120h+lpEnvironment], rax
0x180008c52  mov     qword ptr [rsp+120h+dwCreationFlags], 2
0x180008c5b  mov     qword ptr [rsp+120h+bInheritHandles], rbx
0x180008c60  mov     r8d, r12d
0x180008c63  mov     edx, r12d
0x180008c66  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180008c6d  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180008c72  nop
0x180008c73  lea     rcx, [rbp+57h+arg_10]; this
0x180008c77  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180008c7c  nop
0x180008c7d  lea     rcx, [rbp+57h+arg_18]; this
0x180008c81  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180008c86  nop
0x180008c87  test    rdi, rdi
0x180008c8a  jz      short loc_180008C9C
0x180008c8c  mov     rcx, [rdi]
0x180008c8f  mov     rax, [rcx+10h]
0x180008c93  mov     rcx, rdi
0x180008c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c9b  nop
0x180008c9c  mov     eax, 0C00E0E0Ch
0x180008ca1  jmp     short loc_180008CF9
0x180008ca3  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x180008ca7  call    cs:__imp_CloseHandle
0x180008cad  cmp     [rsi+0ACh], r15b
0x180008cb4  jz      short loc_180008CC3
0x180008cb6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008cb9  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hHandle
0x180008cbd  call    cs:__imp_WaitForSingleObject
0x180008cc3  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x180008cc7  call    cs:__imp_CloseHandle
0x180008ccd  nop
0x180008cce  lea     rcx, [rbp+57h+arg_10]; this
0x180008cd2  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180008cd7  nop
0x180008cd8  lea     rcx, [rbp+57h+arg_18]; this
0x180008cdc  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180008ce1  nop
0x180008ce2  test    rdi, rdi
0x180008ce5  jz      short loc_180008CF7
0x180008ce7  mov     rax, [rdi]
0x180008cea  mov     rcx, rdi
0x180008ced  mov     rax, [rax+10h]
0x180008cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cf6  nop
0x180008cf7  xor     eax, eax
0x180008cf9  add     rsp, 0F0h
0x180008d00  pop     r15
0x180008d02  pop     r14
0x180008d04  pop     r12
0x180008d06  pop     rdi
0x180008d07  pop     rsi
0x180008d08  pop     rbx
0x180008d09  pop     rbp
0x180008d0a  retn
```
