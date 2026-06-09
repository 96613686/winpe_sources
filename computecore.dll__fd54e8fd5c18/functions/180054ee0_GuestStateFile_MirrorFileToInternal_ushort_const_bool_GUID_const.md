# GuestStateFile::MirrorFileToInternal(ushort const *,bool,_GUID const *)

- ea: `0x180054ee0`
- end: `0x1800557f0`
- name: `?MirrorFileToInternal@GuestStateFile@@AEAAXPEBG_NPEBU_GUID@@@Z`
- size: `2320`
- prototype: `void(GuestStateFile *__hidden this, const unsigned __int16 *, bool, const struct _GUID *)`
- caller_count: `0`
- callee_count: `27`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x180009e8c`
- `0x1800115c4`
- `0x180011894`
- `0x18001207c`
- `0x18001223c`
- `0x1800136d0`
- `0x18001587c`
- `0x18001597c`
- `0x18001e220`
- `0x180020c90`
- `0x180027380`
- `0x180046dbc`
- `0x1800526dc`
- `0x180052930`
- `0x180053e24`
- `0x180053f40`
- `0x180054180`
- `0x180054ee0`
- `0x180056d3c`
- `0x180056ea0`
- `0x180057308`
- `0x18005782c`
- `0x18005abf8`
- `0x18005ac60`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180055003`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180055003`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180055681`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180055681`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800550aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800550aa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800550b7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800550b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055200`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005526f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055589`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800555d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055200`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005526f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055589`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800555d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800551ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005525c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055576`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800555b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800551ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005525c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055576`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800555b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800550bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800550bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800551f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055267`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055403`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055581`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800555bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055628`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055672`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800551f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055267`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055403`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055581`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800555bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055628`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055672`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180055379`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180055379`
- `KERNELBASE!Sleep` at `0x180055539`
- `KERNELBASE!Sleep` at `0x180055539`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1800557ac`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1800557ac`
- `VirtDisk!GetVirtualDiskOperationProgress` at `0x18005550b`
- `VirtDisk!GetVirtualDiskOperationProgress` at `0x18005550b`
- `VirtDisk!MirrorVirtualDisk` at `0x1800554d7`
- `VirtDisk!MirrorVirtualDisk` at `0x1800554d7`
- `VirtDisk!OpenVirtualDisk` at `0x180055238`
- `VirtDisk!OpenVirtualDisk` at `0x1800552a7`
- `VirtDisk!OpenVirtualDisk` at `0x180055238`
- `VirtDisk!OpenVirtualDisk` at `0x1800552a7`

## string_xrefs

- `0x180055776`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180055788`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800552d6`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x180055708`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x180055720`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x180055764`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x1800557c9`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x1800557de`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x180055166`: `GuestStateFileOpenVirtualDisk`
- `0x1800552ca`: `Failed to open "%ws"`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall GuestStateFile::MirrorFileToInternal(
        GuestStateFile *this,
        const unsigned __int16 *a2,
        unsigned __int8 a3,
        const struct _GUID *a4)
{
  int v5; // r15d
  __int64 FilePath; // rax
  const unsigned __int16 *v9; // rbx
  __int64 v10; // r8
  bool v11; // zf
  char v12; // al
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // r8
  HANDLE *v17; // r13
  const unsigned __int16 *v18; // rcx
  __int64 v19; // rdi
  _QWORD *v20; // rax
  _QWORD *v21; // rbx
  __int64 v22; // r8
  HANDLE v23; // rdi
  DWORD LastError; // ebx
  const WCHAR *v25; // rdx
  DWORD v26; // eax
  const char *v27; // r9
  HANDLE v28; // rdi
  DWORD v29; // ebx
  const WCHAR *v30; // rdx
  PCWSTR *v31; // rax
  unsigned __int64 v32; // rdx
  LPCWSTR *v33; // rax
  LPCWSTR v34; // rcx
  HANDLE v35; // rbx
  unsigned int v36; // r15d
  LPCWSTR *v37; // r12
  char *FileW; // rdi
  char v39; // r14
  signed int v40; // r14d
  __int64 v41; // r14
  _QWORD *v42; // rax
  _QWORD *v43; // rdi
  __int64 v44; // r8
  unsigned int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // r8
  DWORD VirtualDiskOperationProgress; // eax
  void **v49; // r14
  HANDLE v50; // r12
  void *v51; // r15
  DWORD v52; // edi
  HANDLE v53; // rdi
  DWORD v54; // r14d
  const char *v55; // r9
  const char *v56; // r9
  __int64 v57; // rax
  __int64 v58; // r8
  __int64 v59; // r9
  const char *v60; // rax
  __int64 v61; // rdx
  const char *v62; // r9
  void *v63; // rax
  int Parameters; // [rsp+20h] [rbp-E0h]
  unsigned int Parametersa; // [rsp+20h] [rbp-E0h]
  const char *Handle; // [rsp+28h] [rbp-D8h]
  HANDLE v68; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v69; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v70; // [rsp+60h] [rbp-A0h]
  char *v71; // [rsp+70h] [rbp-90h]
  char v72; // [rsp+78h] [rbp-88h]
  _BYTE v73[32]; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID v74; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE hObject[2]; // [rsp+B0h] [rbp-50h] BYREF
  _VIRTUAL_DISK_PROGRESS Progress; // [rsp+C0h] [rbp-40h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v78; // [rsp+F0h] [rbp-10h]
  PCWSTR Path[2]; // [rsp+100h] [rbp+0h] BYREF
  __m128i si128; // [rsp+110h] [rbp+10h]
  PCWSTR v81[2]; // [rsp+120h] [rbp+20h] BYREF
  __m128i v82; // [rsp+130h] [rbp+30h]
  struct _VIRTUAL_STORAGE_TYPE VirtualStorageType; // [rsp+140h] [rbp+40h] BYREF
  struct _OPEN_VIRTUAL_DISK_PARAMETERS v84; // [rsp+158h] [rbp+58h] BYREF
  _QWORD v85[34]; // [rsp+190h] [rbp+90h] BYREF
  __int64 v86; // [rsp+2A0h] [rbp+1A0h]
  _QWORD v87[42]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _QWORD v88[42]; // [rsp+430h] [rbp+330h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5C8h] [rbp+4C8h]

  v5 = a3;
  memset_0(v85, 0, 0x150u);
  FilePath = GuestStateFile::GetFilePath(this, &v69);
  v9 = (const unsigned __int16 *)FilePath;
  if ( *(_QWORD *)(FilePath + 24) > 7u )
    v9 = *(const unsigned __int16 **)FilePath;
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v85,
    "GuestStateFileMirrorFileToInternal");
  v85[0] = &GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal::`vftable';
  v74 = (struct _GUID)*((_OWORD *)this + 6);
  GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal::StartActivity(
    (GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal *)v85,
    &v74,
    v9,
    a2,
    v5,
    a4);
  std::wstring::~wstring(&v69);
  *(_OWORD *)lpFileName = 0;
  v78 = 0;
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  std::wstring::_Construct<1,unsigned short const *>(lpFileName, a2);
  *(_OWORD *)Path = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Path[0]) = 0;
  *(_OWORD *)v81 = 0;
  v82 = si128;
  LOWORD(v81[0]) = 0;
  AcquireSRWLockShared((PSRWLOCK)this + 5);
  *(_QWORD *)&v74.Data1 = (char *)this + 40;
  v74.Data4[0] = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 40LL))(*((_QWORD *)this + 7))
    || (v11 = (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 56LL))(*((_QWORD *)this + 7)) == 0,
        v12 = 0,
        !v11) )
  {
    v12 = 1;
  }
  if ( v12 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3D4,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
      (const char *)0x8007139FLL,
      Parameters);
  v13 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 72LL))(*((_QWORD *)this + 7));
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(v13 + 2 * v14) );
  std::wstring::_Assign<unsigned short>(Path, v13);
  v15 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 88LL))(*((_QWORD *)this + 7));
  v16 = -1;
  do
    ++v16;
  while ( *(_WORD *)(v15 + 2 * v16) );
  std::wstring::_Assign<unsigned short>(v81, v15);
  ReleaseSRWLockShared((PSRWLOCK)this + 5);
  AcquireSRWLockExclusive((PSRWLOCK)this + 15);
  *((_DWORD *)this + 32) = GetCurrentThreadId();
  v71 = (char *)this + 120;
  v72 = 1;
  v17 = (HANDLE *)((char *)this + 144);
  if ( *((_QWORD *)this + 18) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3E6,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
      (const char *)0x800700AALL,
      Parameters);
  v18 = (const unsigned __int16 *)lpFileName;
  if ( *((_QWORD *)&v78 + 1) > 7u )
    v18 = lpFileName[0];
  GuestStateFile::EnsureDirectoryExists(v18);
  hObject[0] = (HANDLE)-1LL;
  VirtualStorageType.DeviceId = 2;
  VirtualStorageType.VendorId = VIRTUAL_STORAGE_TYPE_VENDOR_MICROSOFT;
  memset(&v84, 0, sizeof(v84));
  v84.Version = OPEN_VIRTUAL_DISK_VERSION_2;
  v84.Version3.ResiliencyGuid = (GUID)*((_OWORD *)this + 6);
  memset_0(v88, 0, sizeof(v88));
  v19 = v86;
  v20 = (_QWORD *)GuestStateFile::GetFilePath(this, v73);
  v21 = v20;
  if ( v20[3] > 7u )
    v21 = (_QWORD *)*v20;
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v88,
    "GuestStateFileOpenVirtualDisk");
  v88[0] = &GuestStateFileTraceProvider::GuestStateFileOpenVirtualDisk::`vftable';
  v69 = 0;
  v70 = 0;
  v22 = -1;
  do
    ++v22;
  while ( *((_WORD *)v21 + v22) );
  std::wstring::_Construct<1,unsigned short const *>(&v69, v21);
  *(_OWORD *)&Progress.OperationStatus = *((_OWORD *)this + 6);
  GuestStateFileTraceProvider::GuestStateFileOpenVirtualDisk::StartActivity(v88, &Progress, &v69, v19 + 8);
  std::wstring::~wstring(v73);
  v23 = hObject[0];
  if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    CloseHandle(v23);
    SetLastError(LastError);
  }
  hObject[0] = (HANDLE)-1LL;
  v25 = (const WCHAR *)Path;
  if ( si128.m128i_i64[1] > 7uLL )
    v25 = Path[0];
  v26 = OpenVirtualDisk(&VirtualStorageType, v25, VIRTUAL_DISK_ACCESS_NONE, OPEN_VIRTUAL_DISK_FLAG_NONE, &v84, hObject);
  v27 = (const char *)v26;
  if ( v26 )
  {
    if ( v26 == 3 )
    {
      v28 = hObject[0];
      if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        v29 = GetLastError();
        CloseHandle(v28);
        SetLastError(v29);
      }
      hObject[0] = (HANDLE)-1LL;
      v30 = (const WCHAR *)v81;
      if ( v82.m128i_i64[1] > 7uLL )
        v30 = v81[0];
      v27 = (const char *)OpenVirtualDisk(
                            &VirtualStorageType,
                            v30,
                            VIRTUAL_DISK_ACCESS_NONE,
                            OPEN_VIRTUAL_DISK_FLAG_NONE,
                            &v84,
                            hObject);
    }
    v31 = Path;
    if ( si128.m128i_i64[1] > 7uLL )
      v31 = (PCWSTR *)Path[0];
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x411,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
      v27,
      (unsigned int)"Failed to open \"%ws\"",
      (const char *)v31);
  }
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v88);
  v68 = 0;
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    &v68,
    1);
  *(_QWORD *)&v74.Data1 = 1;
  v32 = *((_QWORD *)&v78 + 1);
  v33 = lpFileName;
  v34 = lpFileName[0];
  if ( *((_QWORD *)&v78 + 1) > 7u )
    v33 = (LPCWSTR *)lpFileName[0];
  *(_QWORD *)v74.Data4 = v33;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  v35 = v68;
  *((_QWORD *)this + 22) = v68;
  v36 = 2 * v5;
  v37 = lpFileName;
  if ( v32 > 7 )
    v37 = (LPCWSTR *)v34;
  FileW = (char *)CreateFileW((LPCWSTR)v37, 0x80000000, 7u, 0, 3u, 0x100080u, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v40 = GetLastError();
    if ( v40 != 2 && v40 != 3 )
    {
      if ( v40 == 5 || v40 == 32 )
      {
        v39 = 1;
LABEL_49:
        if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
          goto LABEL_51;
        goto LABEL_50;
      }
      if ( (unsigned int)VmlIsDebugTraceEnabled(0x4000) )
      {
        if ( v40 > 0 )
          v40 = (unsigned __int16)v40 | 0x80070000;
        Parametersa = (unsigned int)v37;
        VmlDebugTraceWithError(0x4000, &off_1800AA460, (unsigned int)v40, "`anonymous-namespace'::FileExists");
      }
    }
    v39 = 0;
    goto LABEL_49;
  }
  v39 = 1;
LABEL_50:
  CloseHandle(FileW);
LABEL_51:
  if ( v39 )
    v36 |= 1u;
  memset_0(v87, 0, sizeof(v87));
  v41 = v86;
  v42 = (_QWORD *)GuestStateFile::GetFilePath(this, v73);
  v43 = v42;
  if ( v42[3] > 7u )
    v43 = (_QWORD *)*v42;
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v87,
    "GuestStateFileMirrorVirtualDisk");
  v87[0] = &GuestStateFileTraceProvider::GuestStateFileMirrorVirtualDisk::`vftable';
  v69 = 0;
  v70 = 0;
  v44 = -1;
  do
    ++v44;
  while ( *((_WORD *)v43 + v44) );
  std::wstring::_Construct<1,unsigned short const *>(&v69, v43);
  *(_OWORD *)&Progress.OperationStatus = *((_OWORD *)this + 6);
  GuestStateFileTraceProvider::GuestStateFileMirrorVirtualDisk::StartActivity(v87, &Progress, &v69, v41 + 8);
  std::wstring::~wstring(v73);
  v45 = MirrorVirtualDisk(hObject[0], v36, &v74, (char *)this + 152);
  if ( v45 && v45 != 997 )
  {
    v57 = std::wstring::c_str(lpFileName, v46, v47, v45);
    v60 = (const char *)std::wstring::c_str(Path, v57, v58, v59);
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x441,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
      v62,
      (unsigned int)"Mirror operation of \"%ws\" to \"%ws\" failed.",
      v60,
      v61);
  }
  while ( 1 )
  {
    memset(&Progress, 0, sizeof(Progress));
    VirtualDiskOperationProgress = GetVirtualDiskOperationProgress(
                                     hObject[0],
                                     (LPOVERLAPPED)((char *)this + 152),
                                     &Progress);
    if ( VirtualDiskOperationProgress )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x44A,
        (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
        (const char *)VirtualDiskOperationProgress,
        Parametersa);
    if ( Progress.OperationStatus != 997 )
    {
      v63 = (void *)std::unique_ptr<HyperVAsyncIo,HyperVAsyncIoDeleter>::get((char *)this + 136);
      CancelIoEx(v63, (LPOVERLAPPED)((char *)this + 152));
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x451,
        (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
        (const char *)Progress.OperationStatus,
        (unsigned int)"Mirror operation of failed.",
        Handle);
    }
    if ( Progress.CurrentValue == Progress.CompletionValue )
      break;
    Sleep(0x12Cu);
  }
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v87);
  v49 = (void **)((char *)this + 136);
  if ( (HANDLE *)((char *)this + 136) != hObject )
  {
    v50 = hObject[0];
    v51 = *v49;
    if ( (char *)*v49 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v52 = GetLastError();
      CloseHandle(v51);
      SetLastError(v52);
    }
    *v49 = v50;
    hObject[0] = (HANDLE)-1LL;
  }
  if ( v17 != &v68 )
  {
    v53 = *v17;
    if ( *v17 )
    {
      v54 = GetLastError();
      if ( !CloseHandle(v53) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v55);
      SetLastError(v54);
    }
    *v17 = v35;
    v35 = 0;
  }
  if ( !a3 )
    std::wstring::operator=((char *)this + 184, lpFileName);
  v87[0] = &GuestStateFileTraceProvider::GuestStateFileMirrorVirtualDisk::`vftable';
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v87);
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(v87);
  if ( v35 && !CloseHandle(v35) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v56);
  v88[0] = &GuestStateFileTraceProvider::GuestStateFileOpenVirtualDisk::`vftable';
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v88);
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(v88);
  if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hObject[0]);
  *((_DWORD *)this + 32) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)this + 15);
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v85);
  std::wstring::~wstring(v81);
  std::wstring::~wstring(Path);
  std::wstring::~wstring(lpFileName);
  v85[0] = &GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal::`vftable';
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v85);
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(v85);
}

```

## disassembly

```asm
0x180054ee0  mov     [rsp-8+arg_10], rbx
0x180054ee5  push    rbp
0x180054ee6  push    rsi
0x180054ee7  push    rdi
0x180054ee8  push    r12
0x180054eea  push    r13
0x180054eec  push    r14
0x180054eee  push    r15
0x180054ef0  lea     rbp, [rsp-490h]
0x180054ef8  sub     rsp, 590h
0x180054eff  mov     rax, cs:__security_cookie
0x180054f06  xor     rax, rsp
0x180054f09  mov     [rbp+4C0h+var_40], rax
0x180054f10  mov     r14, r9
0x180054f13  movzx   r15d, r8b
0x180054f17  mov     [rsp+5C0h+var_580], r15b
0x180054f1c  mov     rdi, rdx
0x180054f1f  mov     rsi, rcx
0x180054f22  xor     edx, edx; Val
0x180054f24  mov     r8d, 150h; Size
0x180054f2a  lea     rcx, [rbp+4C0h+var_430]; void *
0x180054f31  call    memset_0
0x180054f36  lea     rdx, [rsp+5C0h+var_570]
0x180054f3b  mov     rcx, rsi
0x180054f3e  call    ?GetFilePath@GuestStateFile@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GuestStateFile::GetFilePath(void)
0x180054f43  mov     rbx, rax
0x180054f46  cmp     qword ptr [rax+18h], 7
0x180054f4b  jbe     short loc_180054F50
0x180054f4d  mov     rbx, [rax]
0x180054f50  lea     rdx, aGueststatefile_3; "GuestStateFileMirrorFileToInternal"
0x180054f57  lea     rcx, [rbp+4C0h+var_430]
0x180054f5e  call    ??0?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180054f63  lea     rax, ??_7GuestStateFileMirrorFileToInternal@GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal::`vftable'
0x180054f6a  mov     [rbp+4C0h+var_430], rax
0x180054f71  movups  xmm0, xmmword ptr [rsi+60h]
0x180054f75  movdqu  xmmword ptr [rbp+4C0h+var_520.Data1], xmm0
0x180054f7a  mov     [rsp+5C0h+Handle], r14; struct _GUID *
0x180054f7f  mov     byte ptr [rsp+5C0h+Parameters], r15b; int
0x180054f84  mov     r9, rdi; unsigned __int16 *
0x180054f87  mov     r8, rbx; unsigned __int16 *
0x180054f8a  lea     rdx, [rbp+4C0h+var_520]; struct _GUID *
0x180054f8e  lea     rcx, [rbp+4C0h+var_430]; this
0x180054f95  call    ?StartActivity@GuestStateFileMirrorFileToInternal@GuestStateFileTraceProvider@@QEAAXU_GUID@@PEBG1_NPEBU3@@Z; GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal::StartActivity(_GUID,ushort const *,ushort const *,bool,_GUID const *)
0x180054f9a  nop
0x180054f9b  lea     rcx, [rsp+5C0h+var_570]
0x180054fa0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180054fa5  xorps   xmm0, xmm0
0x180054fa8  movups  xmmword ptr [rbp+4C0h+lpFileName], xmm0
0x180054fac  xorps   xmm1, xmm1
0x180054faf  movdqu  [rbp+4C0h+var_4D0], xmm1
0x180054fb4  or      r13, 0FFFFFFFFFFFFFFFFh
0x180054fb8  mov     r8, r13
0x180054fbb  xor     r14d, r14d
0x180054fbe  inc     r8
0x180054fc1  cmp     [rdi+r8*2], r14w
0x180054fc6  jnz     short loc_180054FBE
0x180054fc8  mov     rdx, rdi
0x180054fcb  lea     rcx, [rbp+4C0h+lpFileName]
0x180054fcf  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180054fd4  nop
0x180054fd5  xorps   xmm0, xmm0
0x180054fd8  movups  xmmword ptr [rbp+4C0h+Path], xmm0
0x180054fdc  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180054fe4  movdqu  [rbp+4C0h+var_4B0], xmm1
0x180054fe9  mov     word ptr [rbp+4C0h+Path], r14w
0x180054fee  movups  xmmword ptr [rbp+4C0h+var_4A0], xmm0
0x180054ff2  movdqu  [rbp+4C0h+var_490], xmm1
0x180054ff7  mov     word ptr [rbp+4C0h+var_4A0], r14w
0x180054ffc  lea     rbx, [rsi+28h]
0x180055000  mov     rcx, rbx; SRWLock
0x180055003  call    cs:__imp_AcquireSRWLockShared
0x180055009  mov     qword ptr [rbp+4C0h+var_520.Data1], rbx
0x18005500d  mov     r12d, 1
0x180055013  mov     [rbp+4C0h+var_520.Data4], r12b
0x180055017  mov     rcx, [rsi+38h]
0x18005501b  mov     rax, [rcx]
0x18005501e  mov     rax, [rax+28h]
0x180055022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055027  test    al, al
0x180055029  jz      short loc_180055042
0x18005502b  mov     rcx, [rsi+38h]
0x18005502f  mov     rax, [rcx]
0x180055032  mov     rax, [rax+38h]
0x180055036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005503b  test    al, al
0x18005503d  mov     al, r14b
0x180055040  jz      short loc_180055045
0x180055042  mov     al, r12b
0x180055045  mov     rcx, [rbp+4C8h]; this
0x18005504c  test    al, al
0x18005504e  jnz     loc_18005571A
0x180055054  mov     rcx, [rsi+38h]
0x180055058  mov     rax, [rcx]
0x18005505b  mov     rax, [rax+48h]
0x18005505f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055064  mov     r8, r13
0x180055067  inc     r8
0x18005506a  cmp     [rax+r8*2], r14w
0x18005506f  jnz     short loc_180055067
0x180055071  mov     rdx, rax
0x180055074  lea     rcx, [rbp+4C0h+Path]
0x180055078  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005507d  mov     rcx, [rsi+38h]
0x180055081  mov     rax, [rcx]
0x180055084  mov     rax, [rax+58h]
0x180055088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005508d  mov     r8, r13
0x180055090  inc     r8
0x180055093  cmp     [rax+r8*2], r14w
0x180055098  jnz     short loc_180055090
0x18005509a  mov     rdx, rax
0x18005509d  lea     rcx, [rbp+4C0h+var_4A0]
0x1800550a1  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800550a6  nop
0x1800550a7  mov     rcx, rbx; SRWLock
0x1800550aa  call    cs:__imp_ReleaseSRWLockShared
0x1800550b0  lea     rbx, [rsi+78h]
0x1800550b4  mov     rcx, rbx; SRWLock
0x1800550b7  call    cs:__imp_AcquireSRWLockExclusive
0x1800550bd  call    cs:__imp_GetCurrentThreadId
0x1800550c3  mov     [rbx+8], eax
0x1800550c6  mov     [rsp+5C0h+var_550], rbx
0x1800550cb  mov     [rsp+5C0h+var_548], r12b
0x1800550d0  lea     r13, [rsi+90h]
0x1800550d7  mov     rcx, [rbp+4C8h]; this
0x1800550de  cmp     [r13+0], r14
0x1800550e2  jnz     loc_180055702
0x1800550e8  lea     rcx, [rbp+4C0h+lpFileName]
0x1800550ec  cmp     qword ptr [rbp+4C0h+var_4D0+8], 7
0x1800550f1  cmova   rcx, [rbp+4C0h+lpFileName]; unsigned __int16 *
0x1800550f6  call    ?EnsureDirectoryExists@GuestStateFile@@CAXPEBG@Z; GuestStateFile::EnsureDirectoryExists(ushort const *)
0x1800550fb  mov     [rbp+4C0h+hObject], 0FFFFFFFFFFFFFFFFh
0x180055103  mov     ecx, 2
0x180055108  mov     [rbp+4C0h+VirtualStorageType.DeviceId], ecx
0x18005510b  movups  xmm0, xmmword ptr cs:VIRTUAL_STORAGE_TYPE_VENDOR_MICROSOFT.Data1
0x180055112  movdqu  xmmword ptr [rbp+4C0h+VirtualStorageType.VendorId.Data1], xmm0
0x180055117  xorps   xmm1, xmm1
0x18005511a  movups  xmmword ptr [rbp+4C0h+var_468.Version], xmm1
0x18005511e  movups  xmmword ptr [rbp+4C0h+var_468.4+0Ch], xmm1
0x180055122  movups  xmmword ptr [rbp+4C0h+var_468.4+18h], xmm1
0x180055126  mov     [rbp+4C0h+var_468.Version], ecx
0x180055129  movups  xmm0, xmmword ptr [rsi+60h]
0x18005512d  movdqu  xmmword ptr [rbp+4C0h+var_468.4+8], xmm0
0x180055132  xor     edx, edx; Val
0x180055134  mov     r8d, 150h; Size
0x18005513a  lea     rcx, [rbp+4C0h+var_190]; void *
0x180055141  call    memset_0
0x180055146  mov     rdi, [rbp+4C0h+var_320]
0x18005514d  lea     rdx, [rbp+4C0h+var_540]
0x180055151  mov     rcx, rsi
0x180055154  call    ?GetFilePath@GuestStateFile@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GuestStateFile::GetFilePath(void)
0x180055159  mov     rbx, rax
0x18005515c  cmp     qword ptr [rax+18h], 7
0x180055161  jbe     short loc_180055166
0x180055163  mov     rbx, [rax]
0x180055166  lea     rdx, aGueststatefile; "GuestStateFileOpenVirtualDisk"
0x18005516d  lea     rcx, [rbp+4C0h+var_190]
0x180055174  call    ??0?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180055179  lea     rax, ??_7GuestStateFileOpenVirtualDisk@GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::GuestStateFileOpenVirtualDisk::`vftable'
0x180055180  mov     [rbp+4C0h+var_190], rax
0x180055187  xorps   xmm0, xmm0
0x18005518a  movups  [rsp+5C0h+var_570], xmm0
0x18005518f  xorps   xmm1, xmm1
0x180055192  movdqu  [rsp+5C0h+var_560], xmm1
0x180055198  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005519c  inc     r8
0x18005519f  cmp     [rbx+r8*2], r14w
0x1800551a4  jnz     short loc_18005519C
0x1800551a6  mov     rdx, rbx
0x1800551a9  lea     rcx, [rsp+5C0h+var_570]
0x1800551ae  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800551b3  movups  xmm0, xmmword ptr [rsi+60h]
0x1800551b7  movdqu  xmmword ptr [rbp+4C0h+Progress.OperationStatus], xmm0
0x1800551bc  lea     r9, [rdi+8]
0x1800551c0  lea     r8, [rsp+5C0h+var_570]
0x1800551c5  lea     rdx, [rbp+4C0h+Progress]
0x1800551c9  lea     rcx, [rbp+4C0h+var_190]
0x1800551d0  call    ?StartActivity@GuestStateFileOpenVirtualDisk@GuestStateFileTraceProvider@@QEAAXU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU3@@Z; GuestStateFileTraceProvider::GuestStateFileOpenVirtualDisk::StartActivity(_GUID,std::wstring,_GUID const *)
0x1800551d5  nop
0x1800551d6  lea     rcx, [rbp+4C0h+var_540]
0x1800551da  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800551df  mov     rdi, [rbp+4C0h+hObject]
0x1800551e3  lea     rax, [rdi-1]
0x1800551e7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800551eb  ja      short loc_180055206
0x1800551ed  call    cs:__imp_GetLastError
0x1800551f3  mov     ebx, eax
0x1800551f5  mov     rcx, rdi; hObject
0x1800551f8  call    cs:__imp_CloseHandle
0x1800551fe  mov     ecx, ebx; dwErrCode
0x180055200  call    cs:__imp_SetLastError
0x180055206  mov     [rbp+4C0h+hObject], 0FFFFFFFFFFFFFFFFh
0x18005520e  lea     rdx, [rbp+4C0h+Path]
0x180055212  cmp     qword ptr [rbp+4C0h+var_4B0+8], 7
0x180055217  cmova   rdx, [rbp+4C0h+Path]; Path
0x18005521c  lea     rax, [rbp+4C0h+hObject]
0x180055220  mov     [rsp+5C0h+Handle], rax; Handle
0x180055225  lea     rax, [rbp+4C0h+var_468]
0x180055229  mov     [rsp+5C0h+Parameters], rax; Parameters
0x18005522e  xor     r9d, r9d; Flags
0x180055231  xor     r8d, r8d; VirtualDiskAccessMask
0x180055234  lea     rcx, [rbp+4C0h+VirtualStorageType]; VirtualStorageType
0x180055238  call    cs:__imp_OpenVirtualDisk
0x18005523e  mov     r9d, eax
0x180055241  test    eax, eax
0x180055243  jz      loc_1800552E7
0x180055249  cmp     eax, 3
0x18005524c  jnz     short loc_1800552B0
0x18005524e  mov     rdi, [rbp+4C0h+hObject]
0x180055252  lea     rax, [rdi-1]
0x180055256  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005525a  ja      short loc_180055275
0x18005525c  call    cs:__imp_GetLastError
0x180055262  mov     ebx, eax
0x180055264  mov     rcx, rdi; hObject
0x180055267  call    cs:__imp_CloseHandle
0x18005526d  mov     ecx, ebx; dwErrCode
0x18005526f  call    cs:__imp_SetLastError
0x180055275  mov     [rbp+4C0h+hObject], 0FFFFFFFFFFFFFFFFh
0x18005527d  lea     rdx, [rbp+4C0h+var_4A0]
0x180055281  cmp     qword ptr [rbp+4C0h+var_490+8], 7
0x180055286  cmova   rdx, [rbp+4C0h+var_4A0]; Path
0x18005528b  lea     rax, [rbp+4C0h+hObject]
0x18005528f  mov     [rsp+5C0h+Handle], rax; Handle
0x180055294  lea     rax, [rbp+4C0h+var_468]
0x180055298  mov     [rsp+5C0h+Parameters], rax; Parameters
0x18005529d  xor     r9d, r9d; Flags
0x1800552a0  xor     r8d, r8d; VirtualDiskAccessMask
0x1800552a3  lea     rcx, [rbp+4C0h+VirtualStorageType]; VirtualStorageType
0x1800552a7  call    cs:__imp_OpenVirtualDisk
0x1800552ad  mov     r9d, eax; char *
0x1800552b0  lea     rax, [rbp+4C0h+Path]
0x1800552b4  cmp     qword ptr [rbp+4C0h+var_4B0+8], 7
0x1800552b9  cmova   rax, [rbp+4C0h+Path]
0x1800552be  mov     rcx, [rbp+4C8h]; this
0x1800552c5  mov     [rsp+5C0h+Handle], rax; char *
0x1800552ca  lea     rax, aFailedToOpenWs; "Failed to open \"%ws\""
0x1800552d1  mov     [rsp+5C0h+Parameters], rax; unsigned int
0x1800552d6  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\gueststate\\guests"...
0x1800552dd  mov     edx, 411h; void *
0x1800552e2  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x1800552e7  lea     rcx, [rbp+4C0h+var_190]
0x1800552ee  call    ?Stop@?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800552f3  mov     [rsp+5C0h+var_578], r14
0x1800552f8  mov     edx, r12d
0x1800552fb  lea     rcx, [rsp+5C0h+var_578]
0x180055300  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180055305  mov     qword ptr [rbp+4C0h+var_520.Data1], 1
0x18005530d  mov     rdx, qword ptr [rbp+4C0h+var_4D0+8]
0x180055311  lea     rax, [rbp+4C0h+lpFileName]
0x180055315  mov     rcx, [rbp+4C0h+lpFileName]
0x180055319  cmp     rdx, 7
0x18005531d  cmova   rax, rcx
0x180055321  mov     qword ptr [rbp+4C0h+var_520.Data4], rax
0x180055325  mov     [rsi+98h], r14
0x18005532c  mov     [rsi+0A0h], r14
0x180055333  mov     [rsi+0A8h], r14
0x18005533a  mov     rbx, [rsp+5C0h+var_578]
0x18005533f  mov     [rsi+0B0h], rbx
0x180055346  add     r15d, r15d
0x180055349  lea     r12, [rbp+4C0h+lpFileName]
0x18005534d  cmp     rdx, 7
0x180055351  cmova   r12, rcx
0x180055355  mov     [rsp+5C0h+hTemplateFile], r14; hTemplateFile
0x18005535a  mov     dword ptr [rsp+5C0h+Handle], 100080h; char *
0x180055362  mov     dword ptr [rsp+5C0h+Parameters], 3; dwCreationDisposition
0x18005536a  xor     r9d, r9d; lpSecurityAttributes
0x18005536d  mov     edx, 80000000h; dwDesiredAccess
0x180055372  lea     r8d, [r9+7]; dwShareMode
0x180055376  mov     rcx, r12; lpFileName
0x180055379  call    cs:__imp_CreateFileW
0x18005537f  mov     rdi, rax
0x180055382  dec     rax
0x180055385  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180055389  ja      short loc_180055390
0x18005538b  mov     r14b, 1
0x18005538e  jmp     short loc_180055400
0x180055390  call    cs:__imp_GetLastError
0x180055396  mov     r14d, eax
0x180055399  sub     eax, 2
0x18005539c  jz      short loc_1800553F3
0x18005539e  sub     eax, 1
0x1800553a1  jz      short loc_1800553F3
0x1800553a3  sub     eax, 2
0x1800553a6  jz      loc_180055541
0x1800553ac  cmp     eax, 1Bh
0x1800553af  jz      loc_180055541
0x1800553b5  mov     ecx, 4000h
0x1800553ba  call    VmlIsDebugTraceEnabled
0x1800553bf  test    eax, eax
0x1800553c1  jz      short loc_1800553F3
0x1800553c3  test    r14d, r14d
0x1800553c6  jle     short loc_1800553D3
0x1800553c8  movzx   r14d, r14w
0x1800553cc  or      r14d, 80070000h
0x1800553d3  mov     [rsp+5C0h+Parameters], r12; unsigned int
0x1800553d8  lea     r9, aAnonymousNames; "`anonymous-namespace'::FileExists"
0x1800553df  mov     r8d, r14d
0x1800553e2  lea     rdx, off_1800AA460; "%hs: Unable to verify existence of file"...
0x1800553e9  mov     ecx, 4000h
  ... truncated ...
```
