# collectCommandExecution

- ea: `0x1800f029c`
- end: `0x1800f055f`
- name: `collectCommandExecution`
- size: `707`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800f2b84`

## callees

- `0x180019080`
- `0x18001a054`
- `0x1800a9fc0`
- `0x1800e6494`
- `0x1800eb814`
- `0x1800ecf1c`
- `0x1800ed44c`
- `0x1800ed46c`
- `0x1800edc3c`
- `0x1800edd28`
- `0x1800ef868`
- `0x1800f029c`
- `0x1800f0da4`
- `0x18011a1f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800f0376`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800f0376`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800f03a0`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800f03a0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f0496`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f0496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f04cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f04cd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800f0332`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800f0332`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800f0464`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800f0464`

## string_xrefs

- `0x1800f035c`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800f03cb`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800f050a`: `Command execution failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall collectCommandExecution(const WCHAR *a1, const unsigned __int16 *a2)
{
  int v4; // eax
  char v5; // dl
  __int16 v6; // r8
  int v7; // r9d
  unsigned int LastError; // ebx
  __int64 v9; // rdx
  char v10; // bl
  __int64 i; // rdi
  WCHAR *v12; // rax
  TelemetryWriter *v13; // rcx
  const char *v14; // r9
  int v15; // eax
  signed int v16; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  long double v19; // [rsp+28h] [rbp-D8h]
  const char *v20; // [rsp+28h] [rbp-D8h]
  DWORD ExitCode; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR NewFileName[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Dst[1024]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR CommandLine[1024]; // [rsp+A50h] [rbp+950h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1278h] [rbp+1178h]

  memset_0(CommandLine, 0, sizeof(CommandLine));
  memset_0(Dst, 0, sizeof(Dst));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpExistingFileName);
  ExitCode = 0;
  memset_0(NewFileName, 0, 0x208u);
  ExpandEnvironmentStringsW(a1, Dst, 0x104u);
  v4 = StringCchCopyW(CommandLine, 0x400u, Dst);
  LastError = v4;
  if ( v4 >= 0 )
  {
    v10 = 0;
    o((wchar_t)Dst, v5, v6, v7, v18, v19);
    for ( i = 0; i != 18; ++i )
    {
      v12 = wcsstr(Dst, (const wchar_t *)&(&whitelistedCommandsExpanded)[65 * i]);
      if ( v12 && v12 == Dst )
        v10 = 1;
    }
    if ( v10 )
    {
      v4 = StringCchCopyW(NewFileName, 0x104u, a2);
      LastError = v4;
      if ( v4 < 0 )
      {
        v9 = 465;
        goto LABEL_11;
      }
      v4 = StringCchCatW(NewFileName, 0x104u, L"output.log");
      LastError = v4;
      if ( v4 < 0 )
      {
        v9 = 467;
        goto LABEL_11;
      }
      TelemetryWriter::Write(v13, CommandLine);
      if ( (unsigned int)createProcessAndWait(CommandLine, &ExitCode, (__int64)&lpExistingFileName) )
      {
        if ( !CopyFileW(lpExistingFileName, NewFileName, 0) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x1DC,
                        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\archivetooling.cpp",
                        v14);
          goto LABEL_29;
        }
        LastError = 0;
        v15 = DeleteFileW(lpExistingFileName);
        if ( v15 > 0 )
          v15 = (unsigned __int16)v15 | 0x80070000;
        if ( v15 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1E0,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\archivetooling.cpp",
            (const char *)(unsigned int)v15,
            v18);
      }
      else
      {
        v16 = GetLastError();
        LastError = v16;
        if ( v16 > 0 )
          LastError = (unsigned __int16)v16 | 0x80070000;
      }
      if ( ExitCode )
      {
        if ( (int)ExitCode > 0 )
          LastError = (unsigned __int16)ExitCode | 0x80070000;
        else
          LastError = ExitCode;
      }
    }
    else
    {
      LastError = -2147418113;
    }
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x1F1,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\archivetooling.cpp",
      (const char *)LastError,
      (int)"Command execution failed.",
      v20);
    goto LABEL_29;
  }
  v9 = 448;
LABEL_11:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\archivetooling.cpp",
    (const char *)(unsigned int)v4,
    v18);
LABEL_29:
  ATL::CStringData::Release((ATL::CStringData *)(lpExistingFileName - 12));
  return LastError;
}

```

## disassembly

```asm
0x1800f029c  mov     [rsp-8+arg_10], rbx
0x1800f02a1  mov     [rsp-8+arg_18], rsi
0x1800f02a6  push    rbp
0x1800f02a7  push    rdi
0x1800f02a8  push    r14
0x1800f02aa  lea     rbp, [rsp-1160h]
0x1800f02b2  mov     eax, 1260h
0x1800f02b7  call    _alloca_probe
0x1800f02bc  sub     rsp, rax
0x1800f02bf  mov     rax, cs:__security_cookie
0x1800f02c6  xor     rax, rsp
0x1800f02c9  mov     [rbp+1170h+var_20], rax
0x1800f02d0  mov     rsi, rdx
0x1800f02d3  mov     rbx, rcx
0x1800f02d6  mov     edi, 800h
0x1800f02db  mov     r8d, edi; Size
0x1800f02de  xor     edx, edx; Val
0x1800f02e0  lea     rcx, [rbp+1170h+CommandLine]; void *
0x1800f02e7  call    memset_0
0x1800f02ec  mov     r8d, edi; Size
0x1800f02ef  xor     edx, edx; Val
0x1800f02f1  lea     rcx, [rbp+1170h+Dst]; void *
0x1800f02f8  call    memset_0
0x1800f02fd  lea     rcx, [rsp+1270h+lpExistingFileName]
0x1800f0302  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800f0307  nop
0x1800f0308  mov     [rsp+1270h+ExitCode], 0
0x1800f0310  xor     edx, edx; Val
0x1800f0312  mov     r8d, 208h; Size
0x1800f0318  lea     rcx, [rsp+1270h+NewFileName]; void *
0x1800f031d  call    memset_0
0x1800f0322  mov     r8d, 104h; nSize
0x1800f0328  lea     rdx, [rbp+1170h+Dst]; lpDst
0x1800f032f  mov     rcx, rbx; lpSrc
0x1800f0332  call    cs:__imp_ExpandEnvironmentStringsW
0x1800f0339  nop     dword ptr [rax+rax+00h]
0x1800f033e  lea     r8, [rbp+1170h+Dst]; unsigned __int16 *
0x1800f0345  mov     edx, 400h; unsigned __int64
0x1800f034a  lea     rcx, [rbp+1170h+CommandLine]; unsigned __int16 *
0x1800f0351  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800f0356  mov     ebx, eax
0x1800f0358  test    eax, eax
0x1800f035a  jns     short loc_1800F036D
0x1800f035c  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f0363  mov     edx, 1C0h
0x1800f0368  jmp     loc_1800F03FA
0x1800f036d  xor     bl, bl
0x1800f036f  lea     rcx, [rbp+1170h+Dst]
0x1800f0376  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x1800f037d  nop     dword ptr [rax+rax+00h]
0x1800f0382  xor     edi, edi
0x1800f0384  lea     r14d, [rdi+1]
0x1800f0388  imul    rdx, rdi, 208h
0x1800f038f  lea     rax, ?whitelistedCommandsExpanded@@3PAY0BAE@GA; ushort (near * whitelistedCommandsExpanded)[260]
0x1800f0396  add     rdx, rax; SubStr
0x1800f0399  lea     rcx, [rbp+1170h+Dst]; Str
0x1800f03a0  call    cs:__imp_wcsstr
0x1800f03a7  nop     dword ptr [rax+rax+00h]
0x1800f03ac  test    rax, rax
0x1800f03af  jz      short loc_1800F03C2
0x1800f03b1  movzx   ebx, bl
0x1800f03b4  lea     rcx, [rbp+1170h+Dst]
0x1800f03bb  cmp     rax, rcx
0x1800f03be  cmovz   ebx, r14d
0x1800f03c2  add     rdi, r14
0x1800f03c5  cmp     rdi, 12h
0x1800f03c9  jnz     short loc_1800F0388
0x1800f03cb  lea     rdi, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f03d2  test    bl, bl
0x1800f03d4  jz      loc_1800F04FE
0x1800f03da  mov     r8, rsi; unsigned __int16 *
0x1800f03dd  mov     edx, 104h; unsigned __int64
0x1800f03e2  lea     rcx, [rsp+1270h+NewFileName]; unsigned __int16 *
0x1800f03e7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800f03ec  mov     ebx, eax
0x1800f03ee  test    eax, eax
0x1800f03f0  jns     short loc_1800F040E
0x1800f03f2  mov     edx, 1D1h; void *
0x1800f03f7  mov     r8, rdi; unsigned int
0x1800f03fa  mov     rcx, [rbp+1178h]; this
0x1800f0401  mov     r9d, eax; char *
0x1800f0404  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0409  jmp     loc_1800F0527
0x1800f040e  lea     r8, aOutputLog; "output.log"
0x1800f0415  mov     edx, 104h; unsigned __int64
0x1800f041a  lea     rcx, [rsp+1270h+NewFileName]; unsigned __int16 *
0x1800f041f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f0424  mov     ebx, eax
0x1800f0426  test    eax, eax
0x1800f0428  jns     short loc_1800F0431
0x1800f042a  mov     edx, 1D3h
0x1800f042f  jmp     short loc_1800F03F7
0x1800f0431  lea     rdx, [rbp+1170h+CommandLine]; unsigned __int16 *
0x1800f0438  call    ?Write@TelemetryWriter@@QEAAXPEBG@Z; TelemetryWriter::Write(ushort const *)
0x1800f043d  lea     r8, [rsp+1270h+lpExistingFileName]
0x1800f0442  lea     rdx, [rsp+1270h+ExitCode]; lpExitCode
0x1800f0447  lea     rcx, [rbp+1170h+CommandLine]; lpCommandLine
0x1800f044e  call    ?createProcessAndWait@@YAHPEAGPEAKAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; createProcessAndWait(ushort *,ulong *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800f0453  test    eax, eax
0x1800f0455  jz      short loc_1800F04CD
0x1800f0457  xor     r8d, r8d; bFailIfExists
0x1800f045a  lea     rdx, [rsp+1270h+NewFileName]; lpNewFileName
0x1800f045f  mov     rcx, [rsp+1270h+lpExistingFileName]; lpExistingFileName
0x1800f0464  call    cs:__imp_CopyFileW
0x1800f046b  nop     dword ptr [rax+rax+00h]
0x1800f0470  test    eax, eax
0x1800f0472  jnz     short loc_1800F048F
0x1800f0474  mov     rcx, [rbp+1178h]; this
0x1800f047b  mov     r8, rdi; unsigned int
0x1800f047e  mov     edx, 1DCh; void *
0x1800f0483  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800f0488  mov     ebx, eax
0x1800f048a  jmp     loc_1800F0527
0x1800f048f  xor     ebx, ebx
0x1800f0491  mov     rcx, [rsp+1270h+lpExistingFileName]; lpFileName
0x1800f0496  call    cs:__imp_DeleteFileW
0x1800f049d  nop     dword ptr [rax+rax+00h]
0x1800f04a2  mov     esi, 80070000h
0x1800f04a7  test    eax, eax
0x1800f04a9  jle     short loc_1800F04B0
0x1800f04ab  movzx   eax, ax
0x1800f04ae  or      eax, esi
0x1800f04b0  mov     rcx, [rbp+1178h]; this
0x1800f04b7  test    eax, eax
0x1800f04b9  jns     short loc_1800F04E9
0x1800f04bb  mov     r9d, eax; char *
0x1800f04be  mov     r8, rdi; unsigned int
0x1800f04c1  mov     edx, 1E0h; void *
0x1800f04c6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f04cb  jmp     short loc_1800F04E9
0x1800f04cd  call    cs:__imp_GetLastError
0x1800f04d4  nop     dword ptr [rax+rax+00h]
0x1800f04d9  mov     ebx, eax
0x1800f04db  mov     esi, 80070000h
0x1800f04e0  test    eax, eax
0x1800f04e2  jle     short loc_1800F04E9
0x1800f04e4  movzx   ebx, ax
0x1800f04e7  or      ebx, esi
0x1800f04e9  mov     eax, [rsp+1270h+ExitCode]
0x1800f04ed  test    eax, eax
0x1800f04ef  jz      short loc_1800F0503
0x1800f04f1  jg      short loc_1800F04F7
0x1800f04f3  mov     ebx, eax
0x1800f04f5  jmp     short loc_1800F0503
0x1800f04f7  movzx   ebx, ax
0x1800f04fa  or      ebx, esi
0x1800f04fc  jmp     short loc_1800F0503
0x1800f04fe  mov     ebx, 8000FFFFh
0x1800f0503  mov     rcx, [rbp+1178h]; this
0x1800f050a  lea     rax, aCommandExecuti; "Command execution failed."
0x1800f0511  mov     qword ptr [rsp+1270h+var_1250], rax; int
0x1800f0516  mov     r9d, ebx; char *
0x1800f0519  mov     r8, rdi; unsigned int
0x1800f051c  mov     edx, 1F1h; void *
0x1800f0521  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800f0526  nop
0x1800f0527  mov     rcx, [rsp+1270h+lpExistingFileName]
0x1800f052c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800f0530  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800f0535  mov     eax, ebx
0x1800f0537  mov     rcx, [rbp+1170h+var_20]
0x1800f053e  xor     rcx, rsp; StackCookie
0x1800f0541  call    __security_check_cookie
0x1800f0546  lea     r11, [rsp+1270h+var_10]
0x1800f054e  mov     rbx, [r11+30h]
0x1800f0552  mov     rsi, [r11+38h]
0x1800f0556  mov     rsp, r11
0x1800f0559  pop     r14
0x1800f055b  pop     rdi
0x1800f055c  pop     rbp
0x1800f055d  retn
```
