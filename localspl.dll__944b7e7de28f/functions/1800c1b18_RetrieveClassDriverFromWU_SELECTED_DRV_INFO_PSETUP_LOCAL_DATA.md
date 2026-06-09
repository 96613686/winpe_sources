# RetrieveClassDriverFromWU(_SELECTED_DRV_INFO *,_PSETUP_LOCAL_DATA * *)

- ea: `0x1800c1b18`
- end: `0x1800c225a`
- name: `?RetrieveClassDriverFromWU@@YAJPEAU_SELECTED_DRV_INFO@@PEAPEAU_PSETUP_LOCAL_DATA@@@Z`
- size: `1858`
- prototype: `__int64 __fastcall(struct _SELECTED_DRV_INFO *, struct _PSETUP_LOCAL_DATA **)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800adb34`

## callees

- `0x180015e28`
- `0x1800166b4`
- `0x18001683c`
- `0x180019c90`
- `0x180020dd0`
- `0x180026558`
- `0x18002fda0`
- `0x18002fdcc`
- `0x180031550`
- `0x180034308`
- `0x18003e984`
- `0x18003ea2c`
- `0x1800417d4`
- `0x180046650`
- `0x180047330`
- `0x18004eb80`
- `0x1800c1b18`
- `0x1800ca284`
- `0x1800cb798`
- `0x1800cf2bc`
- `0x1800d020c`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c1bae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c21ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c1bae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c21ad`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c1b7f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c1b7f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800c2040`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800c2040`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c1d64`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c1d64`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c220a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c220a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c1da4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c1e1d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c2067`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c1da4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c1e1d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c2067`

## string_xrefs

- `0x1800c1b78`: `ntprint.dll`
- `0x1800c1d0a`: `Failed to create devnode for WU class driver search:hr: 0x%x`
- `0x1800c1f2e`: `No updates found`
- `0x1800c1c56`: `Attempting to search WU for class driver '%ws' with printer driver ID '%ws'`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall RetrieveClassDriverFromWU(struct _SELECTED_DRV_INFO *a1, struct _PSETUP_LOCAL_DATA **a2)
{
  struct DeviceObject *v3; // r15
  HRESULT LastErrorAsFailHRNoBreak; // r14d
  HMODULE v5; // r12
  HMODULE Library; // rax
  NCoreLibrary *v7; // rcx
  unsigned int (*ProcAddress)(void); // rax
  NCoreLibrary *v9; // rcx
  OLECHAR *v10; // rbx
  OLECHAR *v11; // rdi
  char v12; // si
  int v13; // eax
  BSTR v14; // r14
  BSTR v15; // rdx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rcx
  NCoreLibrary *v19; // rcx
  BSTR v20; // r14
  char v21; // r15
  NCoreLibrary::TString *v22; // rcx
  NCoreLibrary::TMultiString *v23; // rcx
  FARPROC v24; // rax
  NCoreLibrary *v25; // rcx
  HRESULT v26; // eax
  NCoreLibrary::TString *v27; // rcx
  char v29; // [rsp+80h] [rbp-80h] BYREF
  char v30; // [rsp+81h] [rbp-7Fh]
  int v31; // [rsp+84h] [rbp-7Ch] BYREF
  int v32; // [rsp+88h] [rbp-78h] BYREF
  LPVOID ppv; // [rsp+90h] [rbp-70h] BYREF
  __int64 v34; // [rsp+98h] [rbp-68h] BYREF
  __int64 v35; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v36; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v37; // [rsp+B0h] [rbp-50h] BYREF
  BSTR v38; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v39; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v40; // [rsp+C8h] [rbp-38h] BYREF
  BSTR v41; // [rsp+D0h] [rbp-30h] BYREF
  HMODULE hModule; // [rsp+D8h] [rbp-28h] BYREF
  struct _GUID v43; // [rsp+E0h] [rbp-20h] BYREF
  BSTR v44; // [rsp+F0h] [rbp-10h] BYREF
  struct _PSETUP_LOCAL_DATA **v45; // [rsp+F8h] [rbp-8h]
  int v46; // [rsp+100h] [rbp+0h] BYREF
  void *v47; // [rsp+108h] [rbp+8h]
  int v48; // [rsp+110h] [rbp+10h]
  __int128 v49; // [rsp+118h] [rbp+18h] BYREF
  int v50; // [rsp+128h] [rbp+28h]
  int v51; // [rsp+12Ch] [rbp+2Ch]
  __int64 v52; // [rsp+130h] [rbp+30h]
  int v53; // [rsp+138h] [rbp+38h]
  int v54; // [rsp+13Ch] [rbp+3Ch]
  int *v55; // [rsp+140h] [rbp+40h]
  WCHAR PathName[264]; // [rsp+150h] [rbp+50h] BYREF

  v45 = a2;
  v3 = 0;
  if ( !*((_QWORD *)a1 + 14) || (LastErrorAsFailHRNoBreak = 0, !*((_QWORD *)a1 + 15)) )
    LastErrorAsFailHRNoBreak = -2147023099;
  v5 = 0;
  hModule = 0;
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    Library = LoadLibraryExW(L"ntprint.dll", 0, 0);
    NCoreLibrary::TAutoHandleHMODULE::operator=(&hModule, Library);
    v5 = hModule;
    if ( hModule
      || (LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v7), LastErrorAsFailHRNoBreak >= 0) )
    {
      ProcAddress = (unsigned int (*)(void))GetProcAddress(v5, (LPCSTR)0x6B);
      if ( ProcAddress )
        LastErrorAsFailHRNoBreak = ProcAddress() == 0 ? 0x80240025 : 0;
      else
        LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v9);
    }
  }
  v10 = &NCoreLibrary::TString::gszNullState;
  v11 = &NCoreLibrary::TString::gszNullState;
  *(_QWORD *)&v43.Data1 = &NCoreLibrary::TString::gszNullState;
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    LastErrorAsFailHRNoBreak = NCoreLibrary::GetGuidString(&v43, (struct TString *)a2);
    v11 = *(OLECHAR **)&v43.Data1;
  }
  v46 = 1920234349;
  v47 = &NCoreLibrary::TMultiString::gszzEmpty;
  v48 = 0;
  if ( LastErrorAsFailHRNoBreak >= 0 )
    LastErrorAsFailHRNoBreak = NCoreLibrary::TMultiString::Cat(
                                 (NCoreLibrary::TMultiString *)&v46,
                                 *((const unsigned __int16 **)a1 + 15));
  v12 = 0;
  v29 = 0;
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    LastErrorAsFailHRNoBreak = CoInitializeNothrowRAII::InitPreferMultithreaded((CoInitializeNothrowRAII *)&v29);
    v12 = v29;
  }
  ppv = 0;
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    LocalSpoolerTelemetry::WriteDbgTraceInfo(
      "RetrieveClassDriverFromWU",
      L"Attempting to search WU for class driver '%ws' with printer driver ID '%ws'",
      *((_QWORD *)a1 + 14),
      *((_QWORD *)a1 + 15));
    v32 = 1;
    v49 = xmmword_18011E2D0;
    v50 = 3;
    v51 = 0;
    v52 = 0;
    v53 = 7;
    v55 = &v32;
    v54 = 4;
    v13 = DeviceObject::Create(
            L"SWD\\PRINTENUM\\PrintQueues",
            v11,
            v47,
            0,
            L"{00000000-0000-0000-ffff-ffffffffffff}",
            0,
            0,
            0,
            0,
            &v49,
            1,
            0,
            0,
            1,
            &ppv);
    LastErrorAsFailHRNoBreak = v13;
    if ( v13 < 0 )
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "RetrieveClassDriverFromWU",
        L"Failed to create devnode for WU class driver search:hr: 0x%x",
        (unsigned int)v13);
    v3 = (struct DeviceObject *)ppv;
  }
  memset_0(PathName, 0, 0x208u);
  if ( LastErrorAsFailHRNoBreak < 0 )
    goto LABEL_85;
  v30 = 0;
  ppv = 0;
  LastErrorAsFailHRNoBreak = CoCreateInstance(&CLSID_UpdateSession, 0, 1u, &IID_IUpdateSession, &ppv);
  v37 = 0;
  if ( LastErrorAsFailHRNoBreak >= 0 )
    LastErrorAsFailHRNoBreak = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 96LL))(ppv, &v37);
  v41 = 0;
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    v14 = SysAllocString(L"Print Class Driver Retrieval Client");
    NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v41);
    if ( v14 )
    {
      v41 = v14;
      LastErrorAsFailHRNoBreak = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v37 + 80LL))(v37, v14);
    }
    else
    {
      v41 = 0;
      LastErrorAsFailHRNoBreak = -2147024882;
    }
  }
  *(_QWORD *)v43.Data4 = &NCoreLibrary::TString::gszNullState;
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    LastErrorAsFailHRNoBreak = NCoreLibrary::TString::Format(
                                 (NCoreLibrary::TString *)v43.Data4,
                                 L"Type='Driver' and DriverMatch='Best' and DeviceInstance='SWD\\PRINTENUM\\%ws'",
                                 v11);
    v10 = *(OLECHAR **)v43.Data4;
  }
  v44 = 0;
  v15 = 0;
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    v15 = SysAllocString(v10);
    v44 = v15;
    LastErrorAsFailHRNoBreak = v15 == 0 ? 0x8007000E : 0;
  }
  v36 = 0;
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    v16 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v37 + 152LL))(v37, v15, &v36);
    LastErrorAsFailHRNoBreak = v16;
    if ( v16 < 0 )
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "RetrieveClassDriverFromWU",
        L"WU class driver search (%ws) failed: hr: 0x%x",
        v10,
        (unsigned int)v16);
  }
  if ( v3 )
    ReleasePrintQueueDevnode(v3, 1);
  v31 = 0;
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    LastErrorAsFailHRNoBreak = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v36 + 56LL))(v36, &v31);
    if ( LastErrorAsFailHRNoBreak >= 0 )
    {
      LastErrorAsFailHRNoBreak = v31 != 2 ? 0x80070705 : 0;
      LocalSpoolerTelemetry::WriteDbgTraceInfo(
        "RetrieveClassDriverFromWU",
        L"WU class driver search OperationResultCode=%d");
    }
  }
  v34 = 0;
  if ( LastErrorAsFailHRNoBreak >= 0 )
    LastErrorAsFailHRNoBreak = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 72LL))(v36, &v34);
  v32 = 0;
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    LastErrorAsFailHRNoBreak = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v34 + 80LL))(v34, &v32);
    if ( LastErrorAsFailHRNoBreak >= 0 && !v32 )
    {
      LastErrorAsFailHRNoBreak = -2147023099;
      LocalSpoolerTelemetry::WriteDbgTraceError("RetrieveClassDriverFromWU", L"No updates found");
    }
  }
  v35 = 0;
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    LastErrorAsFailHRNoBreak = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 104LL))(ppv, &v35);
    if ( LastErrorAsFailHRNoBreak >= 0 )
      LastErrorAsFailHRNoBreak = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v35 + 112LL))(v35, v34);
  }
  v40 = 0;
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v35 + 128LL))(v35, &v40);
    LastErrorAsFailHRNoBreak = v17;
    if ( v17 >= 0 )
    {
      LastErrorAsFailHRNoBreak = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v40 + 64LL))(v40, &v31);
      if ( LastErrorAsFailHRNoBreak >= 0 )
      {
        LastErrorAsFailHRNoBreak = v31 != 2 ? 0x80070705 : 0;
        LocalSpoolerTelemetry::WriteDbgTraceInfo(
          "RetrieveClassDriverFromWU",
          L"WU class driver download OperationResultCode=%d");
      }
    }
    else
    {
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "RetrieveClassDriverFromWU",
        L"WU class driver download failed: hr: 0x%x",
        (unsigned int)v17);
    }
  }
  v39 = 0;
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    LastErrorAsFailHRNoBreak = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v34 + 56LL))(
                                 v34,
                                 0,
                                 &v39);
    if ( LastErrorAsFailHRNoBreak >= 0 )
    {
      LastErrorAsFailHRNoBreak = GetUniqueTempDirInPrintShare(v18, szEnvironment, PathName);
      if ( LastErrorAsFailHRNoBreak >= 0 && !CreateDirectoryW(PathName, 0) )
        LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v19);
    }
  }
  NCoreLibrary::TAutoPtrBSTR::TAutoPtrBSTR((NCoreLibrary::TAutoPtrBSTR *)&v38, 0);
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    v20 = SysAllocString(PathName);
    NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v38);
    if ( v20 )
    {
      v38 = v20;
      v21 = 1;
      LastErrorAsFailHRNoBreak = (*(__int64 (__fastcall **)(__int64, BSTR, __int64))(*(_QWORD *)v39 + 392LL))(
                                   v39,
                                   v20,
                                   0xFFFFFFFFLL);
      goto LABEL_63;
    }
    v38 = 0;
    LastErrorAsFailHRNoBreak = -2147024882;
  }
  v21 = v30;
LABEL_63:
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v38);
  if ( v39 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    v39 = 0;
  }
  if ( v40 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    v40 = 0;
  }
  if ( v35 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    v35 = 0;
  }
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
  }
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    v36 = 0;
  }
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v44);
  NCoreLibrary::TString::vFree(v22, v10);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v41);
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
  }
  v23 = (NCoreLibrary::TMultiString *)ppv;
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    v24 = GetProcAddress(v5, (LPCSTR)0x6A);
    if ( v24 )
      v26 = ((__int64 (__fastcall *)(struct _PSETUP_LOCAL_DATA **, _QWORD, WCHAR *))v24)(
              v45,
              *((_QWORD *)a1 + 14),
              PathName);
    else
      v26 = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v25);
    LastErrorAsFailHRNoBreak = v26;
  }
  if ( v21 )
    RecursivelyDeleteDirectory(PathName, 5);
  if ( LastErrorAsFailHRNoBreak < 0 )
LABEL_85:
    LocalSpoolerTelemetry::LogV4SupportError(0, a1, L"RetrieveClassDriverFromWU", 0, LastErrorAsFailHRNoBreak);
  if ( v12 )
    CoUninitialize();
  NCoreLibrary::TMultiString::vFree(v23, v47);
  NCoreLibrary::TString::vFree(v27, v11);
  NCoreLibrary::TGenericSP<HINSTANCE__ *,NCoreLibrary::TAutoHandleHMODULE,HINSTANCE__ *,0,HINSTANCE__ * const *>::Reset(&hModule);
  return (unsigned int)LastErrorAsFailHRNoBreak;
}

```

## disassembly

```asm
0x1800c1b18  mov     [rsp-8+arg_10], rbx
0x1800c1b1d  push    rbp
0x1800c1b1e  push    rsi
0x1800c1b1f  push    rdi
0x1800c1b20  push    r12
0x1800c1b22  push    r13
0x1800c1b24  push    r14
0x1800c1b26  push    r15
0x1800c1b28  lea     rbp, [rsp-270h]
0x1800c1b30  sub     rsp, 370h
0x1800c1b37  mov     rax, cs:__security_cookie
0x1800c1b3e  xor     rax, rsp
0x1800c1b41  mov     [rbp+2A0h+var_40], rax
0x1800c1b48  mov     [rbp+2A0h+var_2A8], rdx
0x1800c1b4c  mov     r13, rcx
0x1800c1b4f  xor     r15d, r15d
0x1800c1b52  cmp     [rcx+70h], r15
0x1800c1b56  jz      short loc_1800C1B61
0x1800c1b58  mov     r14d, r15d
0x1800c1b5b  cmp     [rcx+78h], r15
0x1800c1b5f  jnz     short loc_1800C1B67
0x1800c1b61  mov     r14d, 80070705h
0x1800c1b67  mov     r12, r15
0x1800c1b6a  mov     [rbp+2A0h+hModule], r15
0x1800c1b6e  test    r14d, r14d
0x1800c1b71  js      short loc_1800C1BD7
0x1800c1b73  xor     r8d, r8d; dwFlags
0x1800c1b76  xor     edx, edx; hFile
0x1800c1b78  lea     rcx, aNtprintDll; "ntprint.dll"
0x1800c1b7f  call    cs:__imp_LoadLibraryExW
0x1800c1b85  mov     rdx, rax
0x1800c1b88  lea     rcx, [rbp+2A0h+hModule]
0x1800c1b8c  call    ??4TAutoHandleHMODULE@NCoreLibrary@@QEAAPEAUHINSTANCE__@@PEAU2@@Z; NCoreLibrary::TAutoHandleHMODULE::operator=(HINSTANCE__ *)
0x1800c1b91  mov     r12, [rbp+2A0h+hModule]
0x1800c1b95  test    r12, r12
0x1800c1b98  jnz     short loc_1800C1BA6
0x1800c1b9a  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800c1b9f  mov     r14d, eax
0x1800c1ba2  test    eax, eax
0x1800c1ba4  js      short loc_1800C1BD7
0x1800c1ba6  mov     edx, 6Bh ; 'k'; lpProcName
0x1800c1bab  mov     rcx, r12; hModule
0x1800c1bae  call    cs:__imp_GetProcAddress
0x1800c1bb4  test    rax, rax
0x1800c1bb7  jz      short loc_1800C1BCF
0x1800c1bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1bbe  neg     eax
0x1800c1bc0  sbb     r14d, r14d
0x1800c1bc3  not     r14d
0x1800c1bc6  and     r14d, 80240025h
0x1800c1bcd  jmp     short loc_1800C1BD7
0x1800c1bcf  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800c1bd4  mov     r14d, eax
0x1800c1bd7  lea     rbx, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x1800c1bde  mov     rdi, rbx
0x1800c1be1  mov     qword ptr [rbp+2A0h+var_2C0.Data1], rbx
0x1800c1be5  test    r14d, r14d
0x1800c1be8  js      short loc_1800C1BFA
0x1800c1bea  lea     rcx, [rbp+2A0h+var_2C0]; this
0x1800c1bee  call    ?GetGuidString@NCoreLibrary@@YAJAEAVTString@1@@Z; NCoreLibrary::GetGuidString(NCoreLibrary::TString &)
0x1800c1bf3  mov     r14d, eax
0x1800c1bf6  mov     rdi, qword ptr [rbp+2A0h+var_2C0.Data1]
0x1800c1bfa  mov     [rbp+2A0h+var_2A0], 7274736Dh
0x1800c1c01  lea     rax, ?gszzEmpty@TMultiString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TMultiString::gszzEmpty
0x1800c1c08  mov     [rbp+2A0h+var_298], rax
0x1800c1c0c  mov     [rbp+2A0h+var_290], r15d
0x1800c1c10  test    r14d, r14d
0x1800c1c13  js      short loc_1800C1C25
0x1800c1c15  mov     rdx, [r13+78h]; unsigned __int16 *
0x1800c1c19  lea     rcx, [rbp+2A0h+var_2A0]; this
0x1800c1c1d  call    ?Cat@TMultiString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TMultiString::Cat(ushort const *)
0x1800c1c22  mov     r14d, eax
0x1800c1c25  mov     sil, r15b
0x1800c1c28  mov     [rbp+2A0h+var_320], r15b
0x1800c1c2c  test    r14d, r14d
0x1800c1c2f  js      short loc_1800C1C41
0x1800c1c31  lea     rcx, [rbp+2A0h+var_320]; this
0x1800c1c35  call    ?InitPreferMultithreaded@CoInitializeNothrowRAII@@QEAAJXZ; CoInitializeNothrowRAII::InitPreferMultithreaded(void)
0x1800c1c3a  mov     r14d, eax
0x1800c1c3d  mov     sil, [rbp+2A0h+var_320]
0x1800c1c41  mov     [rbp+2A0h+var_310], r15
0x1800c1c45  test    r14d, r14d
0x1800c1c48  js      loc_1800C1D21
0x1800c1c4e  mov     r9, [r13+78h]
0x1800c1c52  mov     r8, [r13+70h]
0x1800c1c56  lea     rdx, aAttemptingToSe; "Attempting to search WU for class drive"...
0x1800c1c5d  lea     rcx, aRetrieveclassd; "RetrieveClassDriverFromWU"
0x1800c1c64  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800c1c69  mov     ecx, 1
0x1800c1c6e  mov     [rbp+2A0h+var_318], ecx
0x1800c1c71  movups  xmm0, cs:xmmword_18011E2D0
0x1800c1c78  movups  [rbp+2A0h+var_288], xmm0
0x1800c1c7c  mov     eax, cs:dword_18011E2E0
0x1800c1c82  mov     [rbp+2A0h+var_278], eax
0x1800c1c85  xor     r15d, r15d
0x1800c1c88  mov     [rbp+2A0h+var_274], r15d
0x1800c1c8c  mov     [rbp+2A0h+var_270], r15
0x1800c1c90  mov     [rbp+2A0h+var_268], 7
0x1800c1c97  lea     rax, [rbp+2A0h+var_318]
0x1800c1c9b  mov     [rbp+2A0h+var_260], rax
0x1800c1c9f  mov     [rbp+2A0h+var_264], 4
0x1800c1ca6  lea     rax, [rbp+2A0h+var_310]
0x1800c1caa  mov     [rsp+3A0h+var_330], rax
0x1800c1caf  mov     [rsp+3A0h+var_338], ecx
0x1800c1cb3  mov     [rsp+3A0h+var_340], r15
0x1800c1cb8  mov     [rsp+3A0h+var_348], r15
0x1800c1cbd  mov     [rsp+3A0h+var_350], ecx
0x1800c1cc1  lea     rax, [rbp+2A0h+var_288]
0x1800c1cc5  mov     [rsp+3A0h+var_358], rax
0x1800c1cca  mov     [rsp+3A0h+var_360], r15b
0x1800c1ccf  mov     [rsp+3A0h+var_368], r15
0x1800c1cd4  mov     [rsp+3A0h+var_370], r15
0x1800c1cd9  mov     [rsp+3A0h+var_378], r15
0x1800c1cde  lea     rax, a00000000000000; "{00000000-0000-0000-ffff-ffffffffffff}"
0x1800c1ce5  mov     [rsp+3A0h+ppv], rax
0x1800c1cea  xor     r9d, r9d
0x1800c1ced  mov     r8, [rbp+2A0h+var_298]
0x1800c1cf1  mov     rdx, rdi
0x1800c1cf4  lea     rcx, aSwdPrintenumPr_1; "SWD\\PRINTENUM\\PrintQueues"
0x1800c1cfb  call    ?Create@DeviceObject@@SAJPEBG000000PEBU_SECURITY_DESCRIPTOR@@_NPEBU_DEVPROPERTY@@KP6AXPEAV1@JPEAX@Z5W4DeviceObjectCreationWaitMode@@PEAPEAV1@@Z; DeviceObject::Create(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_SECURITY_DESCRIPTOR const *,bool,_DEVPROPERTY const *,ulong,void (*)(DeviceObject *,long,void *),void *,DeviceObjectCreationWaitMode,DeviceObject * *)
0x1800c1d00  mov     r14d, eax
0x1800c1d03  test    eax, eax
0x1800c1d05  jns     short loc_1800C1D1D
0x1800c1d07  mov     r8d, eax
0x1800c1d0a  lea     rdx, aFailedToCreate; "Failed to create devnode for WU class d"...
0x1800c1d11  lea     rcx, aRetrieveclassd; "RetrieveClassDriverFromWU"
0x1800c1d18  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800c1d1d  mov     r15, [rbp+2A0h+var_310]
0x1800c1d21  xor     edx, edx; Val
0x1800c1d23  mov     r8d, 208h; Size
0x1800c1d29  lea     rcx, [rbp+2A0h+PathName]; void *
0x1800c1d2d  call    memset_0
0x1800c1d32  test    r14d, r14d
0x1800c1d35  js      loc_1800C21EB
0x1800c1d3b  mov     [rbp+2A0h+var_31F], 0
0x1800c1d3f  mov     [rbp+2A0h+var_310], 0
0x1800c1d47  lea     rax, [rbp+2A0h+var_310]
0x1800c1d4b  mov     [rsp+3A0h+ppv], rax; ppv
0x1800c1d50  lea     r9, IID_IUpdateSession; riid
0x1800c1d57  xor     edx, edx; pUnkOuter
0x1800c1d59  lea     r8d, [rdx+1]; dwClsContext
0x1800c1d5d  lea     rcx, CLSID_UpdateSession; rclsid
0x1800c1d64  call    cs:__imp_CoCreateInstance
0x1800c1d6a  mov     r14d, eax
0x1800c1d6d  mov     [rbp+2A0h+var_2F0], 0
0x1800c1d75  test    eax, eax
0x1800c1d77  js      short loc_1800C1D90
0x1800c1d79  mov     rcx, [rbp+2A0h+var_310]
0x1800c1d7d  mov     rax, [rcx]
0x1800c1d80  lea     rdx, [rbp+2A0h+var_2F0]
0x1800c1d84  mov     rax, [rax+60h]
0x1800c1d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1d8d  mov     r14d, eax
0x1800c1d90  mov     [rbp+2A0h+var_2D0], 0
0x1800c1d98  test    r14d, r14d
0x1800c1d9b  js      short loc_1800C1DE8
0x1800c1d9d  lea     rcx, aPrintClassDriv; "Print Class Driver Retrieval Client"
0x1800c1da4  call    cs:__imp_SysAllocString
0x1800c1daa  mov     r14, rax
0x1800c1dad  lea     rcx, [rbp+2A0h+var_2D0]
0x1800c1db1  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x1800c1db6  test    r14, r14
0x1800c1db9  jz      short loc_1800C1DDA
0x1800c1dbb  mov     [rbp+2A0h+var_2D0], r14
0x1800c1dbf  mov     r8, [rbp+2A0h+var_2F0]
0x1800c1dc3  mov     rcx, [r8]
0x1800c1dc6  mov     rax, [rcx+50h]
0x1800c1dca  mov     rdx, r14
0x1800c1dcd  mov     rcx, r8
0x1800c1dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1dd5  mov     r14d, eax
0x1800c1dd8  jmp     short loc_1800C1DE8
0x1800c1dda  mov     [rbp+2A0h+var_2D0], 0
0x1800c1de2  mov     r14d, 8007000Eh
0x1800c1de8  mov     qword ptr [rbp+2A0h+var_2C0.Data4], rbx
0x1800c1dec  test    r14d, r14d
0x1800c1def  js      short loc_1800C1E0B
0x1800c1df1  mov     r8, rdi
0x1800c1df4  lea     rdx, aTypeDriverAndD; "Type='Driver' and DriverMatch='Best' an"...
0x1800c1dfb  lea     rcx, [rbp+2A0h+var_2C0.Data4]; this
0x1800c1dff  call    ?Format@TString@NCoreLibrary@@QEAAJPEBGZZ; NCoreLibrary::TString::Format(ushort const *,...)
0x1800c1e04  mov     r14d, eax
0x1800c1e07  mov     rbx, qword ptr [rbp+2A0h+var_2C0.Data4]
0x1800c1e0b  mov     [rbp+2A0h+var_2B0], 0
0x1800c1e13  xor     edx, edx
0x1800c1e15  test    r14d, r14d
0x1800c1e18  js      short loc_1800C1E3A
0x1800c1e1a  mov     rcx, rbx; psz
0x1800c1e1d  call    cs:__imp_SysAllocString
0x1800c1e23  mov     rdx, rax
0x1800c1e26  mov     [rbp+2A0h+var_2B0], rax
0x1800c1e2a  neg     rax
0x1800c1e2d  sbb     r14d, r14d
0x1800c1e30  not     r14d
0x1800c1e33  and     r14d, 8007000Eh
0x1800c1e3a  mov     [rbp+2A0h+var_2F8], 0
0x1800c1e42  test    r14d, r14d
0x1800c1e45  js      short loc_1800C1E7E
0x1800c1e47  mov     rcx, [rbp+2A0h+var_2F0]
0x1800c1e4b  mov     rax, [rcx]
0x1800c1e4e  lea     r8, [rbp+2A0h+var_2F8]
0x1800c1e52  mov     rax, [rax+98h]
0x1800c1e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1e5e  mov     r14d, eax
0x1800c1e61  test    eax, eax
0x1800c1e63  jns     short loc_1800C1E7E
0x1800c1e65  mov     r9d, eax
0x1800c1e68  mov     r8, rbx
0x1800c1e6b  lea     rdx, aWuClassDriverS_0; "WU class driver search (%ws) failed: hr"...
0x1800c1e72  lea     rcx, aRetrieveclassd; "RetrieveClassDriverFromWU"
0x1800c1e79  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800c1e7e  test    r15, r15
0x1800c1e81  jz      short loc_1800C1E90
0x1800c1e83  mov     edx, 1; int
0x1800c1e88  mov     rcx, r15; this
0x1800c1e8b  call    ?ReleasePrintQueueDevnode@@YAJPEAVDeviceObject@@H@Z; ReleasePrintQueueDevnode(DeviceObject *,int)
0x1800c1e90  xor     r15d, r15d
0x1800c1e93  mov     [rbp+2A0h+var_31C], r15d
0x1800c1e97  test    r14d, r14d
0x1800c1e9a  js      short loc_1800C1EDE
0x1800c1e9c  mov     rcx, [rbp+2A0h+var_2F8]
0x1800c1ea0  mov     rax, [rcx]
0x1800c1ea3  lea     rdx, [rbp+2A0h+var_31C]
0x1800c1ea7  mov     rax, [rax+38h]
0x1800c1eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1eb0  mov     r14d, eax
0x1800c1eb3  test    eax, eax
0x1800c1eb5  js      short loc_1800C1EDE
0x1800c1eb7  mov     r8d, [rbp+2A0h+var_31C]
0x1800c1ebb  lea     eax, [r8-2]
0x1800c1ebf  neg     eax
0x1800c1ec1  sbb     r14d, r14d
0x1800c1ec4  and     r14d, 80070705h
0x1800c1ecb  lea     rdx, aWuClassDriverS; "WU class driver search OperationResultC"...
0x1800c1ed2  lea     rcx, aRetrieveclassd; "RetrieveClassDriverFromWU"
0x1800c1ed9  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800c1ede  mov     [rbp+2A0h+var_308], r15
0x1800c1ee2  test    r14d, r14d
0x1800c1ee5  js      short loc_1800C1EFE
0x1800c1ee7  mov     rcx, [rbp+2A0h+var_2F8]
0x1800c1eeb  mov     rax, [rcx]
0x1800c1eee  lea     rdx, [rbp+2A0h+var_308]
0x1800c1ef2  mov     rax, [rax+48h]
0x1800c1ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1efb  mov     r14d, eax
0x1800c1efe  mov     [rbp+2A0h+var_318], r15d
0x1800c1f02  test    r14d, r14d
0x1800c1f05  js      short loc_1800C1F41
0x1800c1f07  mov     rcx, [rbp+2A0h+var_308]
0x1800c1f0b  mov     rax, [rcx]
0x1800c1f0e  lea     rdx, [rbp+2A0h+var_318]
0x1800c1f12  mov     rax, [rax+50h]
0x1800c1f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1f1b  mov     r14d, eax
0x1800c1f1e  test    eax, eax
0x1800c1f20  js      short loc_1800C1F41
0x1800c1f22  cmp     [rbp+2A0h+var_318], r15d
0x1800c1f26  jnz     short loc_1800C1F41
0x1800c1f28  mov     r14d, 80070705h
0x1800c1f2e  lea     rdx, aNoUpdatesFound; "No updates found"
0x1800c1f35  lea     rcx, aRetrieveclassd; "RetrieveClassDriverFromWU"
0x1800c1f3c  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800c1f41  mov     [rbp+2A0h+var_300], r15
0x1800c1f45  test    r14d, r14d
0x1800c1f48  js      short loc_1800C1F7C
0x1800c1f4a  mov     rcx, [rbp+2A0h+var_310]
0x1800c1f4e  mov     rax, [rcx]
0x1800c1f51  lea     rdx, [rbp+2A0h+var_300]
0x1800c1f55  mov     rax, [rax+68h]
0x1800c1f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1f5e  mov     r14d, eax
0x1800c1f61  test    eax, eax
0x1800c1f63  js      short loc_1800C1F7C
0x1800c1f65  mov     rcx, [rbp+2A0h+var_300]
0x1800c1f69  mov     rax, [rcx]
0x1800c1f6c  mov     rdx, [rbp+2A0h+var_308]
0x1800c1f70  mov     rax, [rax+70h]
0x1800c1f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1f79  mov     r14d, eax
0x1800c1f7c  mov     [rbp+2A0h+var_2D8], r15
0x1800c1f80  test    r14d, r14d
0x1800c1f83  js      short loc_1800C1FFD
0x1800c1f85  mov     rcx, [rbp+2A0h+var_300]
0x1800c1f89  mov     rax, [rcx]
0x1800c1f8c  lea     rdx, [rbp+2A0h+var_2D8]
0x1800c1f90  mov     rax, [rax+80h]
0x1800c1f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1f9c  mov     r14d, eax
0x1800c1f9f  test    eax, eax
0x1800c1fa1  jns     short loc_1800C1FBB
0x1800c1fa3  mov     r8d, eax
0x1800c1fa6  lea     rdx, aWuClassDriverD_0; "WU class driver download failed: hr: 0x"...
0x1800c1fad  lea     rcx, aRetrieveclassd; "RetrieveClassDriverFromWU"
0x1800c1fb4  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800c1fb9  jmp     short loc_1800C1FFD
0x1800c1fbb  mov     rcx, [rbp+2A0h+var_2D8]
0x1800c1fbf  mov     rax, [rcx]
0x1800c1fc2  lea     rdx, [rbp+2A0h+var_31C]
0x1800c1fc6  mov     rax, [rax+40h]
0x1800c1fca  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
