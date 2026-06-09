# CreateLogZipOnXmlInternal(ushort const *,ushort const *,MdmLogCollectorOutputOption)

- ea: `0x1800fb4ac`
- end: `0x1800fbb99`
- name: `?CreateLogZipOnXmlInternal@@YAJPEBG0W4MdmLogCollectorOutputOption@@@Z`
- size: `1773`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800fb490`

## callees

- `0x180019080`
- `0x180019594`
- `0x18001a054`
- `0x1800e6494`
- `0x1800e86e0`
- `0x1800ecf1c`
- `0x1800edae0`
- `0x1800edc3c`
- `0x1800edd28`
- `0x1800ef868`
- `0x1800f1d50`
- `0x1800f2b84`
- `0x1800f5b18`
- `0x1800fa50c`
- `0x1800fa718`
- `0x1800fb4ac`
- `0x180105270`
- `0x18011a15c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800fb9a9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800fb9c9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800fb9a9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800fb9c9`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800fb6b2`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800fb6b2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800fb6e0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800fb6e0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800fb5d7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800fb5d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fb6f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fb6f0`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800fb81c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800fb81c`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800fb800`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800fb800`
- `RPCRT4!UuidToStringW` at `0x1800fb842`
- `RPCRT4!UuidToStringW` at `0x1800fb842`

## string_xrefs

- `0x1800fba0e`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\dllmain.cpp`
- `0x1800fb7e3`: `MDMDiagnostics collector execution completed`
- `0x1800fb980`: `MDMDiagnostics collector finished saving upload result in registry.`
- `0x1800fb998`: `MDMDiagnostics collector execution completed but was run previously.`
- `0x1800fb9ba`: `MDMDiagnostics collector execution completed with errors.`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
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
          &v39,
          (const unsigned __int16 **)&v28,
          (__int64)&v37,
          (__int64)&v36,
          (__int64)v35,
          (__int64)&v34,
          (__int64)&v33,
          &v32,
          &v31,
          &v30);
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
                        &lpFileName,
                        &v28,
                        &v37,
                        &v36,
                        (const WCHAR **)v35,
                        &v34,
                        &v33,
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
0x1800fb4ac  mov     [rsp+arg_10], rbx
0x1800fb4b1  push    rsi
0x1800fb4b2  push    rdi
0x1800fb4b3  push    r12
0x1800fb4b5  push    r14
0x1800fb4b7  push    r15
0x1800fb4b9  sub     rsp, 500h
0x1800fb4c0  mov     rax, cs:__security_cookie
0x1800fb4c7  xor     rax, rsp
0x1800fb4ca  mov     [rsp+528h+var_38], rax
0x1800fb4d2  mov     rsi, rdx
0x1800fb4d5  mov     r15, rcx
0x1800fb4d8  lea     rcx, [rsp+528h+var_480]
0x1800fb4e0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800fb4e5  nop
0x1800fb4e6  lea     rcx, [rsp+528h+var_4D0]
0x1800fb4eb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800fb4f0  nop
0x1800fb4f1  xor     r12d, r12d
0x1800fb4f4  mov     [rsp+528h+NumberOfBytesRead], r12d
0x1800fb4f9  lea     rcx, [rsp+528h+var_488]
0x1800fb501  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800fb506  nop
0x1800fb507  lea     rcx, [rsp+528h+lpFileName]
0x1800fb50c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800fb511  nop
0x1800fb512  lea     rcx, [rsp+528h+var_490]
0x1800fb51a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800fb51f  nop
0x1800fb520  lea     rcx, [rsp+528h+var_498]
0x1800fb528  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800fb52d  nop
0x1800fb52e  lea     rcx, [rsp+528h+var_4A0]
0x1800fb536  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800fb53b  nop
0x1800fb53c  lea     rcx, [rsp+528h+var_4A8]
0x1800fb544  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800fb549  nop
0x1800fb54a  lea     rcx, [rsp+528h+var_4B0]
0x1800fb54f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800fb554  nop
0x1800fb555  mov     [rsp+528h+var_4B8], r12d
0x1800fb55a  mov     [rsp+528h+var_4BC], r12d
0x1800fb55f  mov     [rsp+528h+var_4C0], r12d
0x1800fb564  mov     ebx, 208h
0x1800fb569  mov     r8d, ebx; Size
0x1800fb56c  xor     edx, edx; Val
0x1800fb56e  lea     rcx, [rsp+528h+var_248]; void *
0x1800fb576  call    memset_0
0x1800fb57b  xorps   xmm0, xmm0
0x1800fb57e  movups  xmmword ptr [rsp+528h+pguid.Data1], xmm0
0x1800fb586  mov     [rsp+528h+StringUuid], r12
0x1800fb58e  mov     r8d, ebx; Size
0x1800fb591  xor     edx, edx; Val
0x1800fb593  lea     rcx, [rsp+528h+var_458]; void *
0x1800fb59b  call    memset_0
0x1800fb5a0  test    r15, r15
0x1800fb5a3  jz      loc_1800FBACD
0x1800fb5a9  test    rsi, rsi
0x1800fb5ac  jz      loc_1800FBACD
0x1800fb5b2  mov     [rsp+528h+hTemplateFile], r12; hTemplateFile
0x1800fb5b7  mov     [rsp+528h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800fb5bf  mov     [rsp+528h+dwCreationDisposition], 3; dwCreationDisposition
0x1800fb5c7  xor     r9d, r9d; lpSecurityAttributes
0x1800fb5ca  mov     edx, 80000000h; dwDesiredAccess
0x1800fb5cf  lea     r8d, [r12+1]; dwShareMode
0x1800fb5d4  mov     rcx, r15; lpFileName
0x1800fb5d7  call    cs:__imp_CreateFileW
0x1800fb5de  nop     dword ptr [rax+rax+00h]
0x1800fb5e3  mov     rbx, rax
0x1800fb5e6  mov     [rsp+528h+var_470], rax
0x1800fb5ee  inc     rax
0x1800fb5f1  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800fb5f7  jnz     loc_1800FB6AD
0x1800fb5fd  lea     rcx, [rsp+528h+var_470]
0x1800fb605  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800fb60a  nop
0x1800fb60b  mov     rcx, [rsp+528h+var_4B0]
0x1800fb610  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800fb614  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800fb619  nop
0x1800fb61a  mov     rcx, [rsp+528h+var_4A8]
0x1800fb622  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800fb626  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800fb62b  nop
0x1800fb62c  mov     rcx, qword ptr [rsp+528h+var_4A0]
0x1800fb634  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800fb638  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800fb63d  nop
0x1800fb63e  mov     rcx, [rsp+528h+var_498]
0x1800fb646  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800fb64a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800fb64f  nop
0x1800fb650  mov     rcx, [rsp+528h+var_490]
0x1800fb658  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800fb65c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800fb661  nop
0x1800fb662  mov     rcx, [rsp+528h+lpFileName]
0x1800fb667  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800fb66b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800fb670  nop
0x1800fb671  mov     rcx, [rsp+528h+var_488]
0x1800fb679  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800fb67d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800fb682  nop
0x1800fb683  mov     rcx, [rsp+528h+var_4D0]
0x1800fb688  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800fb68c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800fb691  nop
0x1800fb692  mov     rcx, [rsp+528h+var_480]
0x1800fb69a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800fb69e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800fb6a3  mov     eax, 80070057h
0x1800fb6a8  jmp     loc_1800FBB70
0x1800fb6ad  xor     edx, edx; lpFileSizeHigh
0x1800fb6af  mov     rcx, rbx; hFile
0x1800fb6b2  call    cs:__imp_GetFileSize
0x1800fb6b9  nop     dword ptr [rax+rax+00h]
0x1800fb6be  mov     r14d, eax
0x1800fb6c1  lea     ecx, [r14+1]; unsigned __int64
0x1800fb6c5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800fb6ca  mov     rdi, rax
0x1800fb6cd  mov     qword ptr [rsp+528h+dwCreationDisposition], r12; lpOverlapped
0x1800fb6d2  lea     r9, [rsp+528h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800fb6d7  mov     r8d, r14d; nNumberOfBytesToRead
0x1800fb6da  mov     rdx, rax; lpBuffer
0x1800fb6dd  mov     rcx, rbx; hFile
0x1800fb6e0  call    cs:__imp_ReadFile
0x1800fb6e7  nop     dword ptr [rax+rax+00h]
0x1800fb6ec  test    eax, eax
0x1800fb6ee  jnz     short loc_1800FB713
0x1800fb6f0  call    cs:__imp_GetLastError
0x1800fb6f7  nop     dword ptr [rax+rax+00h]
0x1800fb6fc  mov     ebx, eax
0x1800fb6fe  test    eax, eax
0x1800fb700  jle     short loc_1800FB70B
0x1800fb702  movzx   ebx, ax
0x1800fb705  or      ebx, 80070000h
0x1800fb70b  test    ebx, ebx
0x1800fb70d  js      loc_1800FB98E
0x1800fb713  mov     [r14+rdi], r12b
0x1800fb717  mov     rdx, rdi
0x1800fb71a  lea     rcx, [rsp+528h+var_488]
0x1800fb722  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x1800fb727  lea     rdx, [rsp+528h+var_488]
0x1800fb72f  lea     rcx, [rsp+528h+var_480]
0x1800fb737  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1800fb73c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800fb740  mov     r8, rdi
0x1800fb743  inc     r8
0x1800fb746  cmp     [rsi+r8*2], r12w
0x1800fb74b  jnz     short loc_1800FB743
0x1800fb74d  mov     rdx, rsi
0x1800fb750  lea     rcx, [rsp+528h+var_4D0]
0x1800fb755  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800fb75a  xor     r8d, r8d; int
0x1800fb75d  lea     rdx, aMdmdiagnostics_6; "MDMDiagnostics collector execution star"...
0x1800fb764  call    ?Write@TelemetryWriter@@QEAAXPEBDJ@Z; TelemetryWriter::Write(char const *,long)
0x1800fb769  lea     rax, [rsp+528h+var_4C0]
0x1800fb76e  mov     [rsp+528h+var_4E0], rax
0x1800fb773  lea     rax, [rsp+528h+var_4BC]
0x1800fb778  mov     [rsp+528h+var_4E8], rax
0x1800fb77d  lea     rax, [rsp+528h+var_4B8]
0x1800fb782  mov     [rsp+528h+var_4F0], rax
0x1800fb787  lea     rax, [rsp+528h+var_4B0]
0x1800fb78c  mov     [rsp+528h+hTemplateFile], rax
0x1800fb791  lea     rax, [rsp+528h+var_4A8]
0x1800fb799  mov     qword ptr [rsp+528h+dwFlagsAndAttributes], rax
0x1800fb79e  lea     rax, [rsp+528h+var_4A0]
0x1800fb7a6  mov     qword ptr [rsp+528h+dwCreationDisposition], rax; int
0x1800fb7ab  lea     r9, [rsp+528h+var_498]
0x1800fb7b3  lea     r8, [rsp+528h+var_490]
0x1800fb7bb  lea     rdx, [rsp+528h+var_4D0]
0x1800fb7c0  lea     rcx, [rsp+528h+var_480]
0x1800fb7c8  call    ?setupCollectorPathsAndCollect@CArchiveTooling@@SAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@000000AEAH1AEAW4StorageEndpointApi@@@Z; CArchiveTooling::setupCollectorPathsAndCollect(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,int &,int &,StorageEndpointApi &)
0x1800fb7cd  mov     ebx, eax
0x1800fb7cf  test    eax, eax
0x1800fb7d1  js      loc_1800FB9B7
0x1800fb7d7  cmp     eax, 1
0x1800fb7da  jz      loc_1800FB992
0x1800fb7e0  mov     r8d, eax; int
0x1800fb7e3  lea     rdx, aMdmdiagnostics_2; "MDMDiagnostics collector execution comp"...
0x1800fb7ea  call    ?Write@TelemetryWriter@@QEAAXPEBDJ@Z; TelemetryWriter::Write(char const *,long)
0x1800fb7ef  lea     rdx, [rsp+528h+var_248]
0x1800fb7f7  mov     r14d, 104h
0x1800fb7fd  mov     ecx, r14d
0x1800fb800  call    cs:__imp_GetTempPath2W
0x1800fb807  nop     dword ptr [rax+rax+00h]
0x1800fb80c  test    eax, eax
0x1800fb80e  jz      loc_1800FB98C
0x1800fb814  lea     rcx, [rsp+528h+pguid]; pguid
0x1800fb81c  call    cs:__imp_CoCreateGuid
0x1800fb823  nop     dword ptr [rax+rax+00h]
0x1800fb828  mov     ebx, eax
0x1800fb82a  test    eax, eax
0x1800fb82c  js      loc_1800FB98C
0x1800fb832  lea     rdx, [rsp+528h+StringUuid]; StringUuid
0x1800fb83a  lea     rcx, [rsp+528h+pguid]; Uuid
0x1800fb842  call    cs:__imp_UuidToStringW
0x1800fb849  nop     dword ptr [rax+rax+00h]
0x1800fb84e  lea     r8, [rsp+528h+var_248]; unsigned __int16 *
0x1800fb856  mov     edx, r14d; unsigned __int64
0x1800fb859  lea     rcx, [rsp+528h+var_458]; unsigned __int16 *
0x1800fb861  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800fb866  mov     ebx, eax
0x1800fb868  test    eax, eax
0x1800fb86a  js      loc_1800FB98C
0x1800fb870  mov     r8, [rsp+528h+StringUuid]; unsigned __int16 *
0x1800fb878  mov     edx, r14d; unsigned __int64
0x1800fb87b  lea     rcx, [rsp+528h+var_458]; unsigned __int16 *
0x1800fb883  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800fb888  mov     ebx, eax
0x1800fb88a  test    eax, eax
0x1800fb88c  js      loc_1800FB98C
0x1800fb892  lea     r8, psz; "\\"
0x1800fb899  mov     edx, r14d; unsigned __int64
0x1800fb89c  lea     rcx, [rsp+528h+var_458]; unsigned __int16 *
0x1800fb8a4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800fb8a9  mov     ebx, eax
0x1800fb8ab  test    eax, eax
0x1800fb8ad  js      loc_1800FB98C
0x1800fb8b3  lea     r8, aDiagnosticsZip; "diagnostics.zip"
0x1800fb8ba  mov     edx, r14d; unsigned __int64
0x1800fb8bd  lea     rcx, [rsp+528h+var_458]; unsigned __int16 *
0x1800fb8c5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800fb8ca  mov     ebx, eax
0x1800fb8cc  test    eax, eax
0x1800fb8ce  js      loc_1800FB98C
0x1800fb8d4  lea     rax, [rsp+528h+var_458]
0x1800fb8dc  inc     rdi
0x1800fb8df  cmp     [rax+rdi*2], r12w
0x1800fb8e4  jnz     short loc_1800FB8DC
0x1800fb8e6  mov     r8d, edi
0x1800fb8e9  lea     rdx, [rsp+528h+var_458]
0x1800fb8f1  lea     rcx, [rsp+528h+lpFileName]
0x1800fb8f6  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800fb8fb  xor     r8d, r8d; int
0x1800fb8fe  lea     rdx, aMdmdiagnostics_5; "MDMDiagnostics collector execution uplo"...
0x1800fb905  call    ?Write@TelemetryWriter@@QEAAXPEBDJ@Z; TelemetryWriter::Write(char const *,long)
0x1800fb90a  mov     eax, [rsp+528h+var_4C0]
0x1800fb90e  mov     dword ptr [rsp+528h+var_4E0], eax
0x1800fb912  mov     eax, [rsp+528h+var_4BC]
0x1800fb916  mov     dword ptr [rsp+528h+var_4E8], eax
0x1800fb91a  mov     eax, [rsp+528h+var_4B8]
0x1800fb91e  mov     dword ptr [rsp+528h+var_4F0], eax
0x1800fb922  lea     rax, [rsp+528h+var_4B0]
0x1800fb927  mov     [rsp+528h+hTemplateFile], rax
0x1800fb92c  lea     rax, [rsp+528h+var_4A8]
0x1800fb934  mov     qword ptr [rsp+528h+dwFlagsAndAttributes], rax
0x1800fb939  lea     rax, [rsp+528h+var_4A0]
0x1800fb941  mov     qword ptr [rsp+528h+dwCreationDisposition], rax
0x1800fb946  lea     r9, [rsp+528h+var_498]
0x1800fb94e  lea     r8, [rsp+528h+var_490]
0x1800fb956  lea     rdx, [rsp+528h+var_4D0]
0x1800fb95b  lea     rcx, [rsp+528h+lpFileName]
0x1800fb960  call    ?zipAndUpload@CArchiveTooling@@SAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@000000HHW4StorageEndpointApi@@@Z; CArchiveTooling::zipAndUpload(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,int,int,StorageEndpointApi)
0x1800fb965  mov     ebx, eax
0x1800fb967  mov     r8d, eax; int
0x1800fb96a  lea     rdx, aMdmdiagnostics_3; "MDMDiagnostics collector uploaded finis"...
0x1800fb971  call    ?Write@TelemetryWriter@@QEAAXPEBDJ@Z; TelemetryWriter::Write(char const *,long)
0x1800fb976  mov     ecx, ebx; int
0x1800fb978  call    ?saveUploadHrToSasUrlNodeInRegitry@CArchiveTooling@@SAJJ@Z; CArchiveTooling::saveUploadHrToSasUrlNodeInRegitry(long)
0x1800fb97d  mov     r8d, eax; int
0x1800fb980  lea     rdx, aMdmdiagnostics_0; "MDMDiagnostics collector finished savin"...
0x1800fb987  call    ?Write@TelemetryWriter@@QEAAXPEBDJ@Z; TelemetryWriter::Write(char const *,long)
0x1800fb98c  test    ebx, ebx
0x1800fb98e  jnz     short loc_1800FB9C6
0x1800fb990  jmp     short loc_1800FB9A4
0x1800fb992  mov     ebx, r12d
0x1800fb995  xor     r8d, r8d; int
0x1800fb998  lea     rdx, aMdmdiagnostics_1; "MDMDiagnostics collector execution comp"...
0x1800fb99f  call    ?Write@TelemetryWriter@@QEAAXPEBDJ@Z; TelemetryWriter::Write(char const *,long)
0x1800fb9a4  mov     rcx, [rsp+528h+lpFileName]; lpFileName
0x1800fb9a9  call    cs:__imp_DeleteFileW
0x1800fb9b0  nop     dword ptr [rax+rax+00h]
0x1800fb9b5  jmp     short loc_1800FB9C6
0x1800fb9b7  mov     r8d, eax; int
0x1800fb9ba  lea     rdx, aMdmdiagnostics_4; "MDMDiagnostics collector execution comp"...
0x1800fb9c1  call    ?Write@TelemetryWriter@@QEAAXPEBDJ@Z; TelemetryWriter::Write(char const *,long)
0x1800fb9c6  mov     rcx, r15; lpFileName
0x1800fb9c9  call    cs:__imp_DeleteFileW
0x1800fb9d0  nop     dword ptr [rax+rax+00h]
0x1800fb9d5  mov     rcx, [rsp+528h+var_4D0]; unsigned __int16 *
0x1800fb9da  mov     rax, rcx
0x1800fb9dd  sub     rsi, rcx
0x1800fb9e0  movzx   edx, word ptr [rax]
0x1800fb9e3  movzx   r8d, word ptr [rax+rsi]
0x1800fb9e8  sub     edx, r8d
0x1800fb9eb  jnz     short loc_1800FB9F6
0x1800fb9ed  add     rax, 2
0x1800fb9f1  test    r8d, r8d
0x1800fb9f4  jnz     short loc_1800FB9E0
0x1800fb9f6  test    edx, edx
0x1800fb9f8  jz      short loc_1800FBA20
0x1800fb9fa  call    ?RemoveOutputDirectoryRecursive@@YAJPEBG@Z; RemoveOutputDirectoryRecursive(ushort const *)
0x1800fb9ff  mov     rcx, [rsp+528h]; this
0x1800fba07  test    eax, eax
0x1800fba09  jns     short loc_1800FBA20
0x1800fba0b  mov     r9d, eax; char *
0x1800fba0e  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
  ... truncated ...
```
