# collectCommandExecution

- ea: `0x1800efab4`
- end: `0x1800efd52`
- name: `collectCommandExecution`
- size: `670`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800f21ac`

## callees

- `0x180019000`
- `0x180019fc4`
- `0x1800a9e20`
- `0x1800e62f4`
- `0x1800eb35c`
- `0x1800ec924`
- `0x1800ece3c`
- `0x1800ece5c`
- `0x1800ed5fc`
- `0x1800ed6e4`
- `0x1800ef134`
- `0x1800efab4`
- `0x1800f05a4`
- `0x1801189ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800efb88`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800efb88`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800efbac`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800efbac`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800efc96`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800efc96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800efcc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800efcc7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800efb4a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800efb4a`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800efc6a`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800efc6a`

## string_xrefs

- `0x1800efb6e`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800efbd1`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800efcfe`: `Command execution failed.`

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
0x1800efab4  mov     [rsp-8+arg_10], rbx
0x1800efab9  mov     [rsp-8+arg_18], rsi
0x1800efabe  push    rbp
0x1800efabf  push    rdi
0x1800efac0  push    r14
0x1800efac2  lea     rbp, [rsp-1160h]
0x1800efaca  mov     eax, 1260h
0x1800efacf  call    _alloca_probe
0x1800efad4  sub     rsp, rax
0x1800efad7  mov     rax, cs:__security_cookie
0x1800efade  xor     rax, rsp
0x1800efae1  mov     [rbp+1170h+var_20], rax
0x1800efae8  mov     rsi, rdx
0x1800efaeb  mov     rbx, rcx
0x1800efaee  mov     edi, 800h
0x1800efaf3  mov     r8d, edi; Size
0x1800efaf6  xor     edx, edx; Val
0x1800efaf8  lea     rcx, [rbp+1170h+CommandLine]; void *
0x1800efaff  call    memset_0
0x1800efb04  mov     r8d, edi; Size
0x1800efb07  xor     edx, edx; Val
0x1800efb09  lea     rcx, [rbp+1170h+Dst]; void *
0x1800efb10  call    memset_0
0x1800efb15  lea     rcx, [rsp+1270h+lpExistingFileName]
0x1800efb1a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800efb1f  nop
0x1800efb20  mov     [rsp+1270h+ExitCode], 0
0x1800efb28  xor     edx, edx; Val
0x1800efb2a  mov     r8d, 208h; Size
0x1800efb30  lea     rcx, [rsp+1270h+NewFileName]; void *
0x1800efb35  call    memset_0
0x1800efb3a  mov     r8d, 104h; nSize
0x1800efb40  lea     rdx, [rbp+1170h+Dst]; lpDst
0x1800efb47  mov     rcx, rbx; lpSrc
0x1800efb4a  call    cs:__imp_ExpandEnvironmentStringsW
0x1800efb50  lea     r8, [rbp+1170h+Dst]; unsigned __int16 *
0x1800efb57  mov     edx, 400h; unsigned __int64
0x1800efb5c  lea     rcx, [rbp+1170h+CommandLine]; unsigned __int16 *
0x1800efb63  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800efb68  mov     ebx, eax
0x1800efb6a  test    eax, eax
0x1800efb6c  jns     short loc_1800EFB7F
0x1800efb6e  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800efb75  mov     edx, 1C0h
0x1800efb7a  jmp     loc_1800EFC00
0x1800efb7f  xor     bl, bl
0x1800efb81  lea     rcx, [rbp+1170h+Dst]
0x1800efb88  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x1800efb8e  xor     edi, edi
0x1800efb90  lea     r14d, [rdi+1]
0x1800efb94  imul    rdx, rdi, 208h
0x1800efb9b  lea     rax, ?whitelistedCommandsExpanded@@3PAY0BAE@GA; ushort (near * whitelistedCommandsExpanded)[260]
0x1800efba2  add     rdx, rax; SubStr
0x1800efba5  lea     rcx, [rbp+1170h+Dst]; Str
0x1800efbac  call    cs:__imp_wcsstr
0x1800efbb2  test    rax, rax
0x1800efbb5  jz      short loc_1800EFBC8
0x1800efbb7  movzx   ebx, bl
0x1800efbba  lea     rcx, [rbp+1170h+Dst]
0x1800efbc1  cmp     rax, rcx
0x1800efbc4  cmovz   ebx, r14d
0x1800efbc8  add     rdi, r14
0x1800efbcb  cmp     rdi, 12h
0x1800efbcf  jnz     short loc_1800EFB94
0x1800efbd1  lea     rdi, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800efbd8  test    bl, bl
0x1800efbda  jz      loc_1800EFCF2
0x1800efbe0  mov     r8, rsi; unsigned __int16 *
0x1800efbe3  mov     edx, 104h; unsigned __int64
0x1800efbe8  lea     rcx, [rsp+1270h+NewFileName]; unsigned __int16 *
0x1800efbed  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800efbf2  mov     ebx, eax
0x1800efbf4  test    eax, eax
0x1800efbf6  jns     short loc_1800EFC14
0x1800efbf8  mov     edx, 1D1h; void *
0x1800efbfd  mov     r8, rdi; unsigned int
0x1800efc00  mov     rcx, [rbp+1178h]; this
0x1800efc07  mov     r9d, eax; char *
0x1800efc0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800efc0f  jmp     loc_1800EFD1B
0x1800efc14  lea     r8, aOutputLog; "output.log"
0x1800efc1b  mov     edx, 104h; unsigned __int64
0x1800efc20  lea     rcx, [rsp+1270h+NewFileName]; unsigned __int16 *
0x1800efc25  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800efc2a  mov     ebx, eax
0x1800efc2c  test    eax, eax
0x1800efc2e  jns     short loc_1800EFC37
0x1800efc30  mov     edx, 1D3h
0x1800efc35  jmp     short loc_1800EFBFD
0x1800efc37  lea     rdx, [rbp+1170h+CommandLine]; unsigned __int16 *
0x1800efc3e  call    ?Write@TelemetryWriter@@QEAAXPEBG@Z; TelemetryWriter::Write(ushort const *)
0x1800efc43  lea     r8, [rsp+1270h+lpExistingFileName]
0x1800efc48  lea     rdx, [rsp+1270h+ExitCode]; lpExitCode
0x1800efc4d  lea     rcx, [rbp+1170h+CommandLine]; lpCommandLine
0x1800efc54  call    ?createProcessAndWait@@YAHPEAGPEAKAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; createProcessAndWait(ushort *,ulong *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800efc59  test    eax, eax
0x1800efc5b  jz      short loc_1800EFCC7
0x1800efc5d  xor     r8d, r8d; bFailIfExists
0x1800efc60  lea     rdx, [rsp+1270h+NewFileName]; lpNewFileName
0x1800efc65  mov     rcx, [rsp+1270h+lpExistingFileName]; lpExistingFileName
0x1800efc6a  call    cs:__imp_CopyFileW
0x1800efc70  test    eax, eax
0x1800efc72  jnz     short loc_1800EFC8F
0x1800efc74  mov     rcx, [rbp+1178h]; this
0x1800efc7b  mov     r8, rdi; unsigned int
0x1800efc7e  mov     edx, 1DCh; void *
0x1800efc83  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800efc88  mov     ebx, eax
0x1800efc8a  jmp     loc_1800EFD1B
0x1800efc8f  xor     ebx, ebx
0x1800efc91  mov     rcx, [rsp+1270h+lpExistingFileName]; lpFileName
0x1800efc96  call    cs:__imp_DeleteFileW
0x1800efc9c  mov     esi, 80070000h
0x1800efca1  test    eax, eax
0x1800efca3  jle     short loc_1800EFCAA
0x1800efca5  movzx   eax, ax
0x1800efca8  or      eax, esi
0x1800efcaa  mov     rcx, [rbp+1178h]; this
0x1800efcb1  test    eax, eax
0x1800efcb3  jns     short loc_1800EFCDD
0x1800efcb5  mov     r9d, eax; char *
0x1800efcb8  mov     r8, rdi; unsigned int
0x1800efcbb  mov     edx, 1E0h; void *
0x1800efcc0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800efcc5  jmp     short loc_1800EFCDD
0x1800efcc7  call    cs:__imp_GetLastError
0x1800efccd  mov     ebx, eax
0x1800efccf  mov     esi, 80070000h
0x1800efcd4  test    eax, eax
0x1800efcd6  jle     short loc_1800EFCDD
0x1800efcd8  movzx   ebx, ax
0x1800efcdb  or      ebx, esi
0x1800efcdd  mov     eax, [rsp+1270h+ExitCode]
0x1800efce1  test    eax, eax
0x1800efce3  jz      short loc_1800EFCF7
0x1800efce5  jg      short loc_1800EFCEB
0x1800efce7  mov     ebx, eax
0x1800efce9  jmp     short loc_1800EFCF7
0x1800efceb  movzx   ebx, ax
0x1800efcee  or      ebx, esi
0x1800efcf0  jmp     short loc_1800EFCF7
0x1800efcf2  mov     ebx, 8000FFFFh
0x1800efcf7  mov     rcx, [rbp+1178h]; this
0x1800efcfe  lea     rax, aCommandExecuti; "Command execution failed."
0x1800efd05  mov     qword ptr [rsp+1270h+var_1250], rax; int
0x1800efd0a  mov     r9d, ebx; char *
0x1800efd0d  mov     r8, rdi; unsigned int
0x1800efd10  mov     edx, 1F1h; void *
0x1800efd15  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800efd1a  nop
0x1800efd1b  mov     rcx, [rsp+1270h+lpExistingFileName]
0x1800efd20  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800efd24  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800efd29  mov     eax, ebx
0x1800efd2b  mov     rcx, [rbp+1170h+var_20]
0x1800efd32  xor     rcx, rsp; StackCookie
0x1800efd35  call    __security_check_cookie
0x1800efd3a  lea     r11, [rsp+1270h+var_10]
0x1800efd42  mov     rbx, [r11+30h]
0x1800efd46  mov     rsi, [r11+38h]
0x1800efd4a  mov     rsp, r11
0x1800efd4d  pop     r14
0x1800efd4f  pop     rdi
0x1800efd50  pop     rbp
0x1800efd51  retn
```
