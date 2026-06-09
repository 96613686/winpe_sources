# collectRegistrySelection

- ea: `0x1800f02b4`
- end: `0x1800f049c`
- name: `collectRegistrySelection`
- size: `488`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f21ac`

## callees

- `0x180019000`
- `0x180019fc4`
- `0x1800e62f4`
- `0x1800ec924`
- `0x1800ece5c`
- `0x1800ed5fc`
- `0x1800ed6e4`
- `0x1800ef134`
- `0x1800f02b4`
- `0x1800f05a4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f03fb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f03fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f040a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f043c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f040a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f043c`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800f03ec`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800f03ec`

## string_xrefs

- `0x1800f0359`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800f0427`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall collectRegistrySelection(unsigned __int16 *a1, unsigned __int16 *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  signed int LastError; // eax
  signed int v8; // eax
  DWORD ExitCode; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR CommandLine[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  memset_0(CommandLine, 0, 0x208u);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpExistingFileName);
  ExitCode = 0;
  v4 = StringCchCopyW(CommandLine, 0x104u, L"reg.exe export ");
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 391;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\archivetooling.cpp",
      (const char *)(unsigned int)v4,
      ExitCode);
    goto LABEL_27;
  }
  v4 = StringCchCatW(CommandLine, 0x104u, a1);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 393;
    goto LABEL_5;
  }
  v4 = StringCchCatW(CommandLine, 0x104u, L" ");
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 395;
    goto LABEL_5;
  }
  v4 = StringCchCatW(CommandLine, 0x104u, a2);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 397;
    goto LABEL_5;
  }
  v4 = StringCchCatW(CommandLine, 0x104u, L"export.reg /y");
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 399;
    goto LABEL_5;
  }
  if ( (unsigned int)createProcessAndWait(CommandLine, &ExitCode, (__int64)&lpExistingFileName)
    && CopyFileW(lpExistingFileName, a2, 0) )
  {
    if ( !DeleteFileW(lpExistingFileName) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x19B,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\archivetooling.cpp",
          (const char *)(unsigned int)LastError,
          ExitCode);
    }
    v8 = 0;
  }
  else
  {
    v8 = GetLastError();
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
  }
  if ( ExitCode )
  {
    if ( (int)ExitCode > 0 )
      v8 = (unsigned __int16)ExitCode | 0x80070000;
    else
      v8 = ExitCode;
  }
  v5 = v8;
LABEL_27:
  ATL::CStringData::Release((ATL::CStringData *)(lpExistingFileName - 12));
  return v5;
}

```

## disassembly

```asm
0x1800f02b4  mov     [rsp-8+arg_10], rbx
0x1800f02b9  mov     [rsp-8+arg_18], rsi
0x1800f02be  push    rbp
0x1800f02bf  push    rdi
0x1800f02c0  push    r14
0x1800f02c2  lea     rbp, [rsp-150h]
0x1800f02ca  sub     rsp, 250h
0x1800f02d1  mov     rax, cs:__security_cookie
0x1800f02d8  xor     rax, rsp
0x1800f02db  mov     [rbp+160h+var_20], rax
0x1800f02e2  mov     rdi, rdx
0x1800f02e5  mov     rsi, rcx
0x1800f02e8  xor     edx, edx; Val
0x1800f02ea  mov     r8d, 208h; Size
0x1800f02f0  lea     rcx, [rsp+260h+CommandLine]; void *
0x1800f02f5  call    memset_0
0x1800f02fa  lea     rcx, [rsp+260h+lpExistingFileName]
0x1800f02ff  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800f0304  nop
0x1800f0305  mov     [rsp+260h+ExitCode], 0; int
0x1800f030d  lea     r8, aRegExeExport; "reg.exe export "
0x1800f0314  mov     r14d, 104h
0x1800f031a  mov     edx, r14d; unsigned __int64
0x1800f031d  lea     rcx, [rsp+260h+CommandLine]; unsigned __int16 *
0x1800f0322  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800f0327  mov     ebx, eax
0x1800f0329  test    eax, eax
0x1800f032b  jns     short loc_1800F0334
0x1800f032d  mov     edx, 187h
0x1800f0332  jmp     short loc_1800F034F
0x1800f0334  mov     r8, rsi; unsigned __int16 *
0x1800f0337  mov     rdx, r14; unsigned __int64
0x1800f033a  lea     rcx, [rsp+260h+CommandLine]; unsigned __int16 *
0x1800f033f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f0344  mov     ebx, eax
0x1800f0346  test    eax, eax
0x1800f0348  jns     short loc_1800F036A
0x1800f034a  mov     edx, 189h; void *
0x1800f034f  mov     rcx, [rbp+168h]; this
0x1800f0356  mov     r9d, eax; char *
0x1800f0359  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f0360  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0365  jmp     loc_1800F0465
0x1800f036a  lea     r8, asc_1801BAB3C; " "
0x1800f0371  mov     rdx, r14; unsigned __int64
0x1800f0374  lea     rcx, [rsp+260h+CommandLine]; unsigned __int16 *
0x1800f0379  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f037e  mov     ebx, eax
0x1800f0380  test    eax, eax
0x1800f0382  jns     short loc_1800F038B
0x1800f0384  mov     edx, 18Bh
0x1800f0389  jmp     short loc_1800F034F
0x1800f038b  mov     r8, rdi; unsigned __int16 *
0x1800f038e  mov     rdx, r14; unsigned __int64
0x1800f0391  lea     rcx, [rsp+260h+CommandLine]; unsigned __int16 *
0x1800f0396  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f039b  mov     ebx, eax
0x1800f039d  test    eax, eax
0x1800f039f  jns     short loc_1800F03A8
0x1800f03a1  mov     edx, 18Dh
0x1800f03a6  jmp     short loc_1800F034F
0x1800f03a8  lea     r8, aExportRegY; "export.reg /y"
0x1800f03af  mov     rdx, r14; unsigned __int64
0x1800f03b2  lea     rcx, [rsp+260h+CommandLine]; unsigned __int16 *
0x1800f03b7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f03bc  mov     ebx, eax
0x1800f03be  test    eax, eax
0x1800f03c0  jns     short loc_1800F03C9
0x1800f03c2  mov     edx, 18Fh
0x1800f03c7  jmp     short loc_1800F034F
0x1800f03c9  lea     r8, [rsp+260h+lpExistingFileName]
0x1800f03ce  lea     rdx, [rsp+260h+ExitCode]; lpExitCode
0x1800f03d3  lea     rcx, [rsp+260h+CommandLine]; lpCommandLine
0x1800f03d8  call    ?createProcessAndWait@@YAHPEAGPEAKAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; createProcessAndWait(ushort *,ulong *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800f03dd  test    eax, eax
0x1800f03df  jz      short loc_1800F043C
0x1800f03e1  xor     r8d, r8d; bFailIfExists
0x1800f03e4  mov     rdx, rdi; lpNewFileName
0x1800f03e7  mov     rcx, [rsp+260h+lpExistingFileName]; lpExistingFileName
0x1800f03ec  call    cs:__imp_CopyFileW
0x1800f03f2  test    eax, eax
0x1800f03f4  jz      short loc_1800F043C
0x1800f03f6  mov     rcx, [rsp+260h+lpExistingFileName]; lpFileName
0x1800f03fb  call    cs:__imp_DeleteFileW
0x1800f0401  mov     ebx, 80070000h
0x1800f0406  test    eax, eax
0x1800f0408  jnz     short loc_1800F0438
0x1800f040a  call    cs:__imp_GetLastError
0x1800f0410  test    eax, eax
0x1800f0412  jle     short loc_1800F0419
0x1800f0414  movzx   eax, ax
0x1800f0417  or      eax, ebx
0x1800f0419  mov     rcx, [rbp+168h]; this
0x1800f0420  test    eax, eax
0x1800f0422  jns     short loc_1800F0438
0x1800f0424  mov     r9d, eax; char *
0x1800f0427  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f042e  mov     edx, 19Bh; void *
0x1800f0433  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f0438  xor     eax, eax
0x1800f043a  jmp     short loc_1800F0450
0x1800f043c  call    cs:__imp_GetLastError
0x1800f0442  test    eax, eax
0x1800f0444  mov     ebx, 80070000h
0x1800f0449  jle     short loc_1800F0450
0x1800f044b  movzx   eax, ax
0x1800f044e  or      eax, ebx
0x1800f0450  mov     ecx, [rsp+260h+ExitCode]
0x1800f0454  test    ecx, ecx
0x1800f0456  jz      short loc_1800F0463
0x1800f0458  jg      short loc_1800F045E
0x1800f045a  mov     eax, ecx
0x1800f045c  jmp     short loc_1800F0463
0x1800f045e  movzx   eax, cx
0x1800f0461  or      eax, ebx
0x1800f0463  mov     ebx, eax
0x1800f0465  mov     rcx, [rsp+260h+lpExistingFileName]
0x1800f046a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800f046e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800f0473  mov     eax, ebx
0x1800f0475  mov     rcx, [rbp+160h+var_20]
0x1800f047c  xor     rcx, rsp; StackCookie
0x1800f047f  call    __security_check_cookie
0x1800f0484  lea     r11, [rsp+260h+var_10]
0x1800f048c  mov     rbx, [r11+30h]
0x1800f0490  mov     rsi, [r11+38h]
0x1800f0494  mov     rsp, r11
0x1800f0497  pop     r14
0x1800f0499  pop     rdi
0x1800f049a  pop     rbp
0x1800f049b  retn
```
