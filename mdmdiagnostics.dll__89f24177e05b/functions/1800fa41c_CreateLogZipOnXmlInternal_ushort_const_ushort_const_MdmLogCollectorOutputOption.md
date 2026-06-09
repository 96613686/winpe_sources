# CreateLogZipOnXmlInternal(ushort const *,ushort const *,MdmLogCollectorOutputOption)

- ea: `0x1800fa41c`
- end: `0x1800faad3`
- name: `?CreateLogZipOnXmlInternal@@YAJPEBG0W4MdmLogCollectorOutputOption@@@Z`
- size: `1719`
- prototype: `__int64 __fastcall(const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800fa400`

## callees

- `0x180019000`
- `0x180019514`
- `0x180019fc4`
- `0x1800e62f4`
- `0x1800e84b0`
- `0x1800ec924`
- `0x1800ed4a0`
- `0x1800ed5fc`
- `0x1800ed6e4`
- `0x1800ef134`
- `0x1800f13e4`
- `0x1800f21ac`
- `0x1800f4e94`
- `0x1800f9534`
- `0x1800f9720`
- `0x1800fa41c`
- `0x1801040e4`
- `0x180118954`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800fa8ef`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800fa909`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800fa8ef`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800fa909`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800fa61c`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800fa61c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800fa644`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800fa644`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800fa547`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800fa547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fa64e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fa64e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800fa76e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800fa76e`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800fa758`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800fa758`
- `RPCRT4!UuidToStringW` at `0x1800fa78e`
- `RPCRT4!UuidToStringW` at `0x1800fa78e`

## string_xrefs

- `0x1800fa948`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\dllmain.cpp`
- `0x1800fa73b`: `MDMDiagnostics collector execution completed`
- `0x1800fa8c6`: `MDMDiagnostics collector finished saving upload result in registry.`
- `0x1800fa8de`: `MDMDiagnostics collector execution completed but was run previously.`
- `0x1800fa8fa`: `MDMDiagnostics collector execution completed with errors.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall CreateLogZipOnXmlInternal(const WCHAR *a1, __int64 a2)
{
  HANDLE FileW; // rbx
  DWORD FileSize; // eax
  __int64 v7; // r14
  void *v8; // rdi
  signed int LastError; // eax
  int v10; // ebx
  bool v11; // zf
  __int64 v12; // rdi
  __int64 v13; // r8
  TelemetryWriter *v14; // rcx
  int v15; // eax
  TelemetryWriter *v16; // rcx
  TelemetryWriter *v17; // rcx
  TelemetryWriter *v18; // rcx
  int v19; // eax
  TelemetryWriter *v20; // rcx
  unsigned __int16 *v21; // rax
  __int64 v22; // rsi
  int v23; // r8d
  int v24; // edx
  int v25; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-508h]
  DWORD NumberOfBytesRead; // [rsp+50h] [rbp-4D8h] BYREF
  unsigned __int16 *v28; // [rsp+58h] [rbp-4D0h] BYREF
  LPCWSTR lpFileName; // [rsp+60h] [rbp-4C8h] BYREF
  int v30; // [rsp+68h] [rbp-4C0h] BYREF
  int v31; // [rsp+6Ch] [rbp-4BCh] BYREF
  int v32; // [rsp+70h] [rbp-4B8h] BYREF
  __int64 v33; // [rsp+78h] [rbp-4B0h] BYREF
  __int64 v34; // [rsp+80h] [rbp-4A8h] BYREF
  int v35[2]; // [rsp+88h] [rbp-4A0h] BYREF
  __int64 v36; // [rsp+90h] [rbp-498h] BYREF
  __int64 v37; // [rsp+98h] [rbp-490h] BYREF
  __int64 v38; // [rsp+A0h] [rbp-488h] BYREF
  __int64 v39; // [rsp+A8h] [rbp-480h] BYREF
  RPC_WSTR StringUuid; // [rsp+B0h] [rbp-478h] BYREF
  HANDLE v41; // [rsp+B8h] [rbp-470h] BYREF
  GUID pguid; // [rsp+C0h] [rbp-468h] BYREF
  unsigned __int16 v43[264]; // [rsp+D0h] [rbp-458h] BYREF
  unsigned __int16 v44[264]; // [rsp+2E0h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+0h]

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v39);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v28);
  NumberOfBytesRead = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v38);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpFileName);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v37);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v36);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v35);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v34);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v33);
  v32 = 0;
  v31 = 0;
  v30 = 0;
  memset_0(v44, 0, 0x208u);
  pguid = 0;
  StringUuid = 0;
  memset_0(v43, 0, 0x208u);
  if ( !a1 || !a2 )
  {
    ATL::CStringData::Release((ATL::CStringData *)(v33 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v34 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)v35 - 24LL));
    ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v37 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(lpFileName - 12));
    ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v28 - 12));
    ATL::CStringData::Release((ATL::CStringData *)(v39 - 24));
    return 2147942487LL;
  }
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v41 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v41);
    ATL::CStringData::Release((ATL::CStringData *)(v33 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v34 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)v35 - 24LL));
    ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v37 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(lpFileName - 12));
    ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v28 - 12));
    ATL::CStringData::Release((ATL::CStringData *)(v39 - 24));
    return 2147942487LL;
  }
  FileSize = GetFileSize(FileW, 0);
  v7 = FileSize;
  v8 = operator new[](FileSize + 1);
  if ( !ReadFile(FileW, v8, v7, &NumberOfBytesRead, 0) )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    v11 = v10 == 0;
    if ( v10 < 0 )
      goto LABEL_22;
  }
  *((_BYTE *)v8 + v7) = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(&v38, v8);
  ATL::CSimpleStringT<unsigned short,0>::operator=(&v39, &v38);
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)(a2 + 2 * v13) );
  ATL::CSimpleStringT<unsigned short,0>::SetString(&v28, a2);
  TelemetryWriter::Write(v14, "MDMDiagnostics collector execution started", 0);
  v15 = CArchiveTooling::setupCollectorPathsAndCollect(
          (unsigned int)&v39,
          (unsigned int)&v28,
          (unsigned int)&v37,
          (unsigned int)&v36,
          (__int64)v35,
          (__int64)&v34,
          (__int64)&v33,
          (__int64)&v32,
          (__int64)&v31,
          (__int64)&v30);
  v10 = v15;
  if ( v15 >= 0 )
  {
    if ( v15 == 1 )
    {
      v10 = 0;
      TelemetryWriter::Write(v16, "MDMDiagnostics collector execution completed but was run previously.", 0);
LABEL_25:
      DeleteFileW(lpFileName);
      goto LABEL_27;
    }
    TelemetryWriter::Write(v16, "MDMDiagnostics collector execution completed", v15);
    if ( (unsigned int)GetTempPath2W(260, v44) )
    {
      v10 = CoCreateGuid(&pguid);
      if ( v10 >= 0 )
      {
        UuidToStringW(&pguid, &StringUuid);
        v10 = StringCchCopyW(v43, 0x104u, v44);
        if ( v10 >= 0 )
        {
          v10 = StringCchCatW(v43, 0x104u, StringUuid);
          if ( v10 >= 0 )
          {
            v10 = StringCchCatW(v43, 0x104u, L"\\");
            if ( v10 >= 0 )
            {
              v10 = StringCchCatW(v43, 0x104u, L"diagnostics.zip");
              if ( v10 >= 0 )
              {
                do
                  ++v12;
                while ( v43[v12] );
                ATL::CSimpleStringT<unsigned short,0>::SetString(&lpFileName, v43);
                TelemetryWriter::Write(v17, "MDMDiagnostics collector execution upload started", 0);
                v10 = CArchiveTooling::zipAndUpload(
                        (unsigned int)&lpFileName,
                        (unsigned int)&v28,
                        (unsigned int)&v37,
                        (unsigned int)&v36,
                        (__int64)v35,
                        (__int64)&v34,
                        (__int64)&v33,
                        v32,
                        v31,
                        v30);
                TelemetryWriter::Write(v18, "MDMDiagnostics collector uploaded finished with result.", v10);
                v19 = CArchiveTooling::saveUploadHrToSasUrlNodeInRegitry(v10);
                TelemetryWriter::Write(v20, "MDMDiagnostics collector finished saving upload result in registry.", v19);
              }
            }
          }
        }
      }
    }
    v11 = v10 == 0;
LABEL_22:
    if ( !v11 )
      goto LABEL_27;
    goto LABEL_25;
  }
  TelemetryWriter::Write(v16, "MDMDiagnostics collector execution completed with errors.", v15);
LABEL_27:
  DeleteFileW(a1);
  v21 = v28;
  v22 = a2 - (_QWORD)v28;
  do
  {
    v23 = *(unsigned __int16 *)((char *)v21 + v22);
    v24 = *v21 - v23;
    if ( v24 )
      break;
    ++v21;
  }
  while ( v23 );
  if ( v24 )
  {
    v25 = RemoveOutputDirectoryRecursive(v28);
    if ( v25 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x34A,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\dllmain.cpp",
        (const char *)(unsigned int)v25,
        dwCreationDisposition);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v41);
  ATL::CStringData::Release((ATL::CStringData *)(v33 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v34 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)v35 - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v37 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(lpFileName - 12));
  ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v28 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(v39 - 24));
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800fa41c  mov     [rsp+arg_10], rbx
0x1800fa421  push    rsi
0x1800fa422  push    rdi
0x1800fa423  push    r12
0x1800fa425  push    r14
0x1800fa427  push    r15
0x1800fa429  sub     rsp, 500h
0x1800fa430  mov     rax, cs:__security_cookie
0x1800fa437  xor     rax, rsp
0x1800fa43a  mov     [rsp+528h+var_38], rax
0x1800fa442  mov     rsi, rdx
0x1800fa445  mov     r15, rcx
0x1800fa448  lea     rcx, [rsp+528h+var_480]
0x1800fa450  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800fa455  nop
0x1800fa456  lea     rcx, [rsp+528h+var_4D0]
0x1800fa45b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800fa460  nop
0x1800fa461  xor     r12d, r12d
0x1800fa464  mov     [rsp+528h+NumberOfBytesRead], r12d
0x1800fa469  lea     rcx, [rsp+528h+var_488]
0x1800fa471  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800fa476  nop
0x1800fa477  lea     rcx, [rsp+528h+lpFileName]
0x1800fa47c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800fa481  nop
0x1800fa482  lea     rcx, [rsp+528h+var_490]
0x1800fa48a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800fa48f  nop
0x1800fa490  lea     rcx, [rsp+528h+var_498]
0x1800fa498  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800fa49d  nop
0x1800fa49e  lea     rcx, [rsp+528h+var_4A0]
0x1800fa4a6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800fa4ab  nop
0x1800fa4ac  lea     rcx, [rsp+528h+var_4A8]
0x1800fa4b4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800fa4b9  nop
0x1800fa4ba  lea     rcx, [rsp+528h+var_4B0]
0x1800fa4bf  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800fa4c4  nop
0x1800fa4c5  mov     [rsp+528h+var_4B8], r12d
0x1800fa4ca  mov     [rsp+528h+var_4BC], r12d
0x1800fa4cf  mov     [rsp+528h+var_4C0], r12d
0x1800fa4d4  mov     ebx, 208h
0x1800fa4d9  mov     r8d, ebx; Size
0x1800fa4dc  xor     edx, edx; Val
0x1800fa4de  lea     rcx, [rsp+528h+var_248]; void *
0x1800fa4e6  call    memset_0
0x1800fa4eb  xorps   xmm0, xmm0
0x1800fa4ee  movups  xmmword ptr [rsp+528h+pguid.Data1], xmm0
0x1800fa4f6  mov     [rsp+528h+StringUuid], r12
0x1800fa4fe  mov     r8d, ebx; Size
0x1800fa501  xor     edx, edx; Val
0x1800fa503  lea     rcx, [rsp+528h+var_458]; void *
0x1800fa50b  call    memset_0
0x1800fa510  test    r15, r15
0x1800fa513  jz      loc_1800FAA07
0x1800fa519  test    rsi, rsi
0x1800fa51c  jz      loc_1800FAA07
0x1800fa522  mov     [rsp+528h+hTemplateFile], r12; hTemplateFile
0x1800fa527  mov     [rsp+528h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800fa52f  mov     [rsp+528h+dwCreationDisposition], 3; dwCreationDisposition
0x1800fa537  xor     r9d, r9d; lpSecurityAttributes
0x1800fa53a  mov     edx, 80000000h; dwDesiredAccess
0x1800fa53f  lea     r8d, [r12+1]; dwShareMode
0x1800fa544  mov     rcx, r15; lpFileName
0x1800fa547  call    cs:__imp_CreateFileW
0x1800fa54d  mov     rbx, rax
0x1800fa550  mov     [rsp+528h+var_470], rax
0x1800fa558  inc     rax
0x1800fa55b  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800fa561  jnz     loc_1800FA617
0x1800fa567  lea     rcx, [rsp+528h+var_470]
0x1800fa56f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800fa574  nop
0x1800fa575  mov     rcx, [rsp+528h+var_4B0]
0x1800fa57a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800fa57e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800fa583  nop
0x1800fa584  mov     rcx, [rsp+528h+var_4A8]
0x1800fa58c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800fa590  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800fa595  nop
0x1800fa596  mov     rcx, qword ptr [rsp+528h+var_4A0]
0x1800fa59e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800fa5a2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800fa5a7  nop
0x1800fa5a8  mov     rcx, [rsp+528h+var_498]
0x1800fa5b0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800fa5b4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800fa5b9  nop
0x1800fa5ba  mov     rcx, [rsp+528h+var_490]
0x1800fa5c2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800fa5c6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800fa5cb  nop
0x1800fa5cc  mov     rcx, [rsp+528h+lpFileName]
0x1800fa5d1  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800fa5d5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800fa5da  nop
0x1800fa5db  mov     rcx, [rsp+528h+var_488]
0x1800fa5e3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800fa5e7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800fa5ec  nop
0x1800fa5ed  mov     rcx, [rsp+528h+var_4D0]
0x1800fa5f2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800fa5f6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800fa5fb  nop
0x1800fa5fc  mov     rcx, [rsp+528h+var_480]
0x1800fa604  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800fa608  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800fa60d  mov     eax, 80070057h
0x1800fa612  jmp     loc_1800FAAAA
0x1800fa617  xor     edx, edx; lpFileSizeHigh
0x1800fa619  mov     rcx, rbx; hFile
0x1800fa61c  call    cs:__imp_GetFileSize
0x1800fa622  mov     r14d, eax
0x1800fa625  lea     ecx, [r14+1]; unsigned __int64
0x1800fa629  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800fa62e  mov     rdi, rax
0x1800fa631  mov     qword ptr [rsp+528h+dwCreationDisposition], r12; lpOverlapped
0x1800fa636  lea     r9, [rsp+528h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800fa63b  mov     r8d, r14d; nNumberOfBytesToRead
0x1800fa63e  mov     rdx, rax; lpBuffer
0x1800fa641  mov     rcx, rbx; hFile
0x1800fa644  call    cs:__imp_ReadFile
0x1800fa64a  test    eax, eax
0x1800fa64c  jnz     short loc_1800FA66B
0x1800fa64e  call    cs:__imp_GetLastError
0x1800fa654  mov     ebx, eax
0x1800fa656  test    eax, eax
0x1800fa658  jle     short loc_1800FA663
0x1800fa65a  movzx   ebx, ax
0x1800fa65d  or      ebx, 80070000h
0x1800fa663  test    ebx, ebx
0x1800fa665  js      loc_1800FA8D4
0x1800fa66b  mov     [r14+rdi], r12b
0x1800fa66f  mov     rdx, rdi
0x1800fa672  lea     rcx, [rsp+528h+var_488]
0x1800fa67a  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x1800fa67f  lea     rdx, [rsp+528h+var_488]
0x1800fa687  lea     rcx, [rsp+528h+var_480]
0x1800fa68f  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1800fa694  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800fa698  mov     r8, rdi
0x1800fa69b  inc     r8
0x1800fa69e  cmp     [rsi+r8*2], r12w
0x1800fa6a3  jnz     short loc_1800FA69B
0x1800fa6a5  mov     rdx, rsi
0x1800fa6a8  lea     rcx, [rsp+528h+var_4D0]
0x1800fa6ad  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800fa6b2  xor     r8d, r8d; int
0x1800fa6b5  lea     rdx, aMdmdiagnostics_6; "MDMDiagnostics collector execution star"...
0x1800fa6bc  call    ?Write@TelemetryWriter@@QEAAXPEBDJ@Z; TelemetryWriter::Write(char const *,long)
0x1800fa6c1  lea     rax, [rsp+528h+var_4C0]
0x1800fa6c6  mov     [rsp+528h+var_4E0], rax
0x1800fa6cb  lea     rax, [rsp+528h+var_4BC]
0x1800fa6d0  mov     [rsp+528h+var_4E8], rax
0x1800fa6d5  lea     rax, [rsp+528h+var_4B8]
0x1800fa6da  mov     [rsp+528h+var_4F0], rax
0x1800fa6df  lea     rax, [rsp+528h+var_4B0]
0x1800fa6e4  mov     [rsp+528h+hTemplateFile], rax
0x1800fa6e9  lea     rax, [rsp+528h+var_4A8]
0x1800fa6f1  mov     qword ptr [rsp+528h+dwFlagsAndAttributes], rax
0x1800fa6f6  lea     rax, [rsp+528h+var_4A0]
0x1800fa6fe  mov     qword ptr [rsp+528h+dwCreationDisposition], rax; int
0x1800fa703  lea     r9, [rsp+528h+var_498]
0x1800fa70b  lea     r8, [rsp+528h+var_490]
0x1800fa713  lea     rdx, [rsp+528h+var_4D0]
0x1800fa718  lea     rcx, [rsp+528h+var_480]
0x1800fa720  call    ?setupCollectorPathsAndCollect@CArchiveTooling@@SAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@000000AEAH1AEAW4StorageEndpointApi@@@Z; CArchiveTooling::setupCollectorPathsAndCollect(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,int &,int &,StorageEndpointApi &)
0x1800fa725  mov     ebx, eax
0x1800fa727  test    eax, eax
0x1800fa729  js      loc_1800FA8F7
0x1800fa72f  cmp     eax, 1
0x1800fa732  jz      loc_1800FA8D8
0x1800fa738  mov     r8d, eax; int
0x1800fa73b  lea     rdx, aMdmdiagnostics_2; "MDMDiagnostics collector execution comp"...
0x1800fa742  call    ?Write@TelemetryWriter@@QEAAXPEBDJ@Z; TelemetryWriter::Write(char const *,long)
0x1800fa747  lea     rdx, [rsp+528h+var_248]
0x1800fa74f  mov     r14d, 104h
0x1800fa755  mov     ecx, r14d
0x1800fa758  call    cs:__imp_GetTempPath2W
0x1800fa75e  test    eax, eax
0x1800fa760  jz      loc_1800FA8D2
0x1800fa766  lea     rcx, [rsp+528h+pguid]; pguid
0x1800fa76e  call    cs:__imp_CoCreateGuid
0x1800fa774  mov     ebx, eax
0x1800fa776  test    eax, eax
0x1800fa778  js      loc_1800FA8D2
0x1800fa77e  lea     rdx, [rsp+528h+StringUuid]; StringUuid
0x1800fa786  lea     rcx, [rsp+528h+pguid]; Uuid
0x1800fa78e  call    cs:__imp_UuidToStringW
0x1800fa794  lea     r8, [rsp+528h+var_248]; unsigned __int16 *
0x1800fa79c  mov     edx, r14d; unsigned __int64
0x1800fa79f  lea     rcx, [rsp+528h+var_458]; unsigned __int16 *
0x1800fa7a7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800fa7ac  mov     ebx, eax
0x1800fa7ae  test    eax, eax
0x1800fa7b0  js      loc_1800FA8D2
0x1800fa7b6  mov     r8, [rsp+528h+StringUuid]; unsigned __int16 *
0x1800fa7be  mov     edx, r14d; unsigned __int64
0x1800fa7c1  lea     rcx, [rsp+528h+var_458]; unsigned __int16 *
0x1800fa7c9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800fa7ce  mov     ebx, eax
0x1800fa7d0  test    eax, eax
0x1800fa7d2  js      loc_1800FA8D2
0x1800fa7d8  lea     r8, psz; "\\"
0x1800fa7df  mov     edx, r14d; unsigned __int64
0x1800fa7e2  lea     rcx, [rsp+528h+var_458]; unsigned __int16 *
0x1800fa7ea  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800fa7ef  mov     ebx, eax
0x1800fa7f1  test    eax, eax
0x1800fa7f3  js      loc_1800FA8D2
0x1800fa7f9  lea     r8, aDiagnosticsZip; "diagnostics.zip"
0x1800fa800  mov     edx, r14d; unsigned __int64
0x1800fa803  lea     rcx, [rsp+528h+var_458]; unsigned __int16 *
0x1800fa80b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800fa810  mov     ebx, eax
0x1800fa812  test    eax, eax
0x1800fa814  js      loc_1800FA8D2
0x1800fa81a  lea     rax, [rsp+528h+var_458]
0x1800fa822  inc     rdi
0x1800fa825  cmp     [rax+rdi*2], r12w
0x1800fa82a  jnz     short loc_1800FA822
0x1800fa82c  mov     r8d, edi
0x1800fa82f  lea     rdx, [rsp+528h+var_458]
0x1800fa837  lea     rcx, [rsp+528h+lpFileName]
0x1800fa83c  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800fa841  xor     r8d, r8d; int
0x1800fa844  lea     rdx, aMdmdiagnostics_5; "MDMDiagnostics collector execution uplo"...
0x1800fa84b  call    ?Write@TelemetryWriter@@QEAAXPEBDJ@Z; TelemetryWriter::Write(char const *,long)
0x1800fa850  mov     eax, [rsp+528h+var_4C0]
0x1800fa854  mov     dword ptr [rsp+528h+var_4E0], eax
0x1800fa858  mov     eax, [rsp+528h+var_4BC]
0x1800fa85c  mov     dword ptr [rsp+528h+var_4E8], eax
0x1800fa860  mov     eax, [rsp+528h+var_4B8]
0x1800fa864  mov     dword ptr [rsp+528h+var_4F0], eax
0x1800fa868  lea     rax, [rsp+528h+var_4B0]
0x1800fa86d  mov     [rsp+528h+hTemplateFile], rax
0x1800fa872  lea     rax, [rsp+528h+var_4A8]
0x1800fa87a  mov     qword ptr [rsp+528h+dwFlagsAndAttributes], rax
0x1800fa87f  lea     rax, [rsp+528h+var_4A0]
0x1800fa887  mov     qword ptr [rsp+528h+dwCreationDisposition], rax
0x1800fa88c  lea     r9, [rsp+528h+var_498]
0x1800fa894  lea     r8, [rsp+528h+var_490]
0x1800fa89c  lea     rdx, [rsp+528h+var_4D0]
0x1800fa8a1  lea     rcx, [rsp+528h+lpFileName]
0x1800fa8a6  call    ?zipAndUpload@CArchiveTooling@@SAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@000000HHW4StorageEndpointApi@@@Z; CArchiveTooling::zipAndUpload(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,int,int,StorageEndpointApi)
0x1800fa8ab  mov     ebx, eax
0x1800fa8ad  mov     r8d, eax; int
0x1800fa8b0  lea     rdx, aMdmdiagnostics_3; "MDMDiagnostics collector uploaded finis"...
0x1800fa8b7  call    ?Write@TelemetryWriter@@QEAAXPEBDJ@Z; TelemetryWriter::Write(char const *,long)
0x1800fa8bc  mov     ecx, ebx; int
0x1800fa8be  call    ?saveUploadHrToSasUrlNodeInRegitry@CArchiveTooling@@SAJJ@Z; CArchiveTooling::saveUploadHrToSasUrlNodeInRegitry(long)
0x1800fa8c3  mov     r8d, eax; int
0x1800fa8c6  lea     rdx, aMdmdiagnostics_0; "MDMDiagnostics collector finished savin"...
0x1800fa8cd  call    ?Write@TelemetryWriter@@QEAAXPEBDJ@Z; TelemetryWriter::Write(char const *,long)
0x1800fa8d2  test    ebx, ebx
0x1800fa8d4  jnz     short loc_1800FA906
0x1800fa8d6  jmp     short loc_1800FA8EA
0x1800fa8d8  mov     ebx, r12d
0x1800fa8db  xor     r8d, r8d; int
0x1800fa8de  lea     rdx, aMdmdiagnostics_1; "MDMDiagnostics collector execution comp"...
0x1800fa8e5  call    ?Write@TelemetryWriter@@QEAAXPEBDJ@Z; TelemetryWriter::Write(char const *,long)
0x1800fa8ea  mov     rcx, [rsp+528h+lpFileName]; lpFileName
0x1800fa8ef  call    cs:__imp_DeleteFileW
0x1800fa8f5  jmp     short loc_1800FA906
0x1800fa8f7  mov     r8d, eax; int
0x1800fa8fa  lea     rdx, aMdmdiagnostics_4; "MDMDiagnostics collector execution comp"...
0x1800fa901  call    ?Write@TelemetryWriter@@QEAAXPEBDJ@Z; TelemetryWriter::Write(char const *,long)
0x1800fa906  mov     rcx, r15; lpFileName
0x1800fa909  call    cs:__imp_DeleteFileW
0x1800fa90f  mov     rcx, [rsp+528h+var_4D0]; unsigned __int16 *
0x1800fa914  mov     rax, rcx
0x1800fa917  sub     rsi, rcx
0x1800fa91a  movzx   edx, word ptr [rax]
0x1800fa91d  movzx   r8d, word ptr [rax+rsi]
0x1800fa922  sub     edx, r8d
0x1800fa925  jnz     short loc_1800FA930
0x1800fa927  add     rax, 2
0x1800fa92b  test    r8d, r8d
0x1800fa92e  jnz     short loc_1800FA91A
0x1800fa930  test    edx, edx
0x1800fa932  jz      short loc_1800FA95A
0x1800fa934  call    ?RemoveOutputDirectoryRecursive@@YAJPEBG@Z; RemoveOutputDirectoryRecursive(ushort const *)
0x1800fa939  mov     rcx, [rsp+528h]; this
0x1800fa941  test    eax, eax
0x1800fa943  jns     short loc_1800FA95A
0x1800fa945  mov     r9d, eax; char *
0x1800fa948  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800fa94f  mov     edx, 34Ah; void *
0x1800fa954  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800fa959  nop
0x1800fa95a  lea     rcx, [rsp+528h+var_470]
0x1800fa962  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800fa967  nop
0x1800fa968  mov     rcx, [rsp+528h+var_4B0]
0x1800fa96d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800fa971  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
  ... truncated ...
```
