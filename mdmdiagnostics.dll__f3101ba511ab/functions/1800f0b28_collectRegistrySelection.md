# collectRegistrySelection

- ea: `0x1800f0b28`
- end: `0x1800f0d29`
- name: `collectRegistrySelection`
- size: `513`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f2b84`

## callees

- `0x180019080`
- `0x18001a054`
- `0x1800e6494`
- `0x1800ecf1c`
- `0x1800ed46c`
- `0x1800edc3c`
- `0x1800edd28`
- `0x1800ef868`
- `0x1800f0b28`
- `0x1800f0da4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f0c75`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f0c75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0c8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0cc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0c8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0cc2`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800f0c60`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800f0c60`

## string_xrefs

- `0x1800f0bcd`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800f0cad`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`

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
0x1800f0b28  mov     [rsp-8+arg_10], rbx
0x1800f0b2d  mov     [rsp-8+arg_18], rsi
0x1800f0b32  push    rbp
0x1800f0b33  push    rdi
0x1800f0b34  push    r14
0x1800f0b36  lea     rbp, [rsp-150h]
0x1800f0b3e  sub     rsp, 250h
0x1800f0b45  mov     rax, cs:__security_cookie
0x1800f0b4c  xor     rax, rsp
0x1800f0b4f  mov     [rbp+160h+var_20], rax
0x1800f0b56  mov     rdi, rdx
0x1800f0b59  mov     rsi, rcx
0x1800f0b5c  xor     edx, edx; Val
0x1800f0b5e  mov     r8d, 208h; Size
0x1800f0b64  lea     rcx, [rsp+260h+CommandLine]; void *
0x1800f0b69  call    memset_0
0x1800f0b6e  lea     rcx, [rsp+260h+lpExistingFileName]
0x1800f0b73  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800f0b78  nop
0x1800f0b79  mov     [rsp+260h+ExitCode], 0; int
0x1800f0b81  lea     r8, aRegExeExport; "reg.exe export "
0x1800f0b88  mov     r14d, 104h
0x1800f0b8e  mov     edx, r14d; unsigned __int64
0x1800f0b91  lea     rcx, [rsp+260h+CommandLine]; unsigned __int16 *
0x1800f0b96  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800f0b9b  mov     ebx, eax
0x1800f0b9d  test    eax, eax
0x1800f0b9f  jns     short loc_1800F0BA8
0x1800f0ba1  mov     edx, 187h
0x1800f0ba6  jmp     short loc_1800F0BC3
0x1800f0ba8  mov     r8, rsi; unsigned __int16 *
0x1800f0bab  mov     rdx, r14; unsigned __int64
0x1800f0bae  lea     rcx, [rsp+260h+CommandLine]; unsigned __int16 *
0x1800f0bb3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f0bb8  mov     ebx, eax
0x1800f0bba  test    eax, eax
0x1800f0bbc  jns     short loc_1800F0BDE
0x1800f0bbe  mov     edx, 189h; void *
0x1800f0bc3  mov     rcx, [rbp+168h]; this
0x1800f0bca  mov     r9d, eax; char *
0x1800f0bcd  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f0bd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0bd9  jmp     loc_1800F0CF1
0x1800f0bde  lea     r8, asc_1801BCB3C; " "
0x1800f0be5  mov     rdx, r14; unsigned __int64
0x1800f0be8  lea     rcx, [rsp+260h+CommandLine]; unsigned __int16 *
0x1800f0bed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f0bf2  mov     ebx, eax
0x1800f0bf4  test    eax, eax
0x1800f0bf6  jns     short loc_1800F0BFF
0x1800f0bf8  mov     edx, 18Bh
0x1800f0bfd  jmp     short loc_1800F0BC3
0x1800f0bff  mov     r8, rdi; unsigned __int16 *
0x1800f0c02  mov     rdx, r14; unsigned __int64
0x1800f0c05  lea     rcx, [rsp+260h+CommandLine]; unsigned __int16 *
0x1800f0c0a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f0c0f  mov     ebx, eax
0x1800f0c11  test    eax, eax
0x1800f0c13  jns     short loc_1800F0C1C
0x1800f0c15  mov     edx, 18Dh
0x1800f0c1a  jmp     short loc_1800F0BC3
0x1800f0c1c  lea     r8, aExportRegY; "export.reg /y"
0x1800f0c23  mov     rdx, r14; unsigned __int64
0x1800f0c26  lea     rcx, [rsp+260h+CommandLine]; unsigned __int16 *
0x1800f0c2b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f0c30  mov     ebx, eax
0x1800f0c32  test    eax, eax
0x1800f0c34  jns     short loc_1800F0C3D
0x1800f0c36  mov     edx, 18Fh
0x1800f0c3b  jmp     short loc_1800F0BC3
0x1800f0c3d  lea     r8, [rsp+260h+lpExistingFileName]
0x1800f0c42  lea     rdx, [rsp+260h+ExitCode]; lpExitCode
0x1800f0c47  lea     rcx, [rsp+260h+CommandLine]; lpCommandLine
0x1800f0c4c  call    ?createProcessAndWait@@YAHPEAGPEAKAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; createProcessAndWait(ushort *,ulong *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800f0c51  test    eax, eax
0x1800f0c53  jz      short loc_1800F0CC2
0x1800f0c55  xor     r8d, r8d; bFailIfExists
0x1800f0c58  mov     rdx, rdi; lpNewFileName
0x1800f0c5b  mov     rcx, [rsp+260h+lpExistingFileName]; lpExistingFileName
0x1800f0c60  call    cs:__imp_CopyFileW
0x1800f0c67  nop     dword ptr [rax+rax+00h]
0x1800f0c6c  test    eax, eax
0x1800f0c6e  jz      short loc_1800F0CC2
0x1800f0c70  mov     rcx, [rsp+260h+lpExistingFileName]; lpFileName
0x1800f0c75  call    cs:__imp_DeleteFileW
0x1800f0c7c  nop     dword ptr [rax+rax+00h]
0x1800f0c81  mov     ebx, 80070000h
0x1800f0c86  test    eax, eax
0x1800f0c88  jnz     short loc_1800F0CBE
0x1800f0c8a  call    cs:__imp_GetLastError
0x1800f0c91  nop     dword ptr [rax+rax+00h]
0x1800f0c96  test    eax, eax
0x1800f0c98  jle     short loc_1800F0C9F
0x1800f0c9a  movzx   eax, ax
0x1800f0c9d  or      eax, ebx
0x1800f0c9f  mov     rcx, [rbp+168h]; this
0x1800f0ca6  test    eax, eax
0x1800f0ca8  jns     short loc_1800F0CBE
0x1800f0caa  mov     r9d, eax; char *
0x1800f0cad  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f0cb4  mov     edx, 19Bh; void *
0x1800f0cb9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f0cbe  xor     eax, eax
0x1800f0cc0  jmp     short loc_1800F0CDC
0x1800f0cc2  call    cs:__imp_GetLastError
0x1800f0cc9  nop     dword ptr [rax+rax+00h]
0x1800f0cce  test    eax, eax
0x1800f0cd0  mov     ebx, 80070000h
0x1800f0cd5  jle     short loc_1800F0CDC
0x1800f0cd7  movzx   eax, ax
0x1800f0cda  or      eax, ebx
0x1800f0cdc  mov     ecx, [rsp+260h+ExitCode]
0x1800f0ce0  test    ecx, ecx
0x1800f0ce2  jz      short loc_1800F0CEF
0x1800f0ce4  jg      short loc_1800F0CEA
0x1800f0ce6  mov     eax, ecx
0x1800f0ce8  jmp     short loc_1800F0CEF
0x1800f0cea  movzx   eax, cx
0x1800f0ced  or      eax, ebx
0x1800f0cef  mov     ebx, eax
0x1800f0cf1  mov     rcx, [rsp+260h+lpExistingFileName]
0x1800f0cf6  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800f0cfa  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800f0cff  mov     eax, ebx
0x1800f0d01  mov     rcx, [rbp+160h+var_20]
0x1800f0d08  xor     rcx, rsp; StackCookie
0x1800f0d0b  call    __security_check_cookie
0x1800f0d10  lea     r11, [rsp+260h+var_10]
0x1800f0d18  mov     rbx, [r11+30h]
0x1800f0d1c  mov     rsi, [r11+38h]
0x1800f0d20  mov     rsp, r11
0x1800f0d23  pop     r14
0x1800f0d25  pop     rdi
0x1800f0d26  pop     rbp
0x1800f0d27  retn
```
