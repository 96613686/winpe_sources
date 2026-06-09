# Windows::Isolation::Implementation::Rtl::RtlpIsolatedFilesystem_DirectWin32_GetFileContents(Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM *,Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES const *,_LBLOB *,_RTL_ALTERNATE_STATUS *)

- ea: `0x180021be0`
- end: `0x180021f1d`
- name: `?RtlpIsolatedFilesystem_DirectWin32_GetFileContents@Rtl@Implementation@Isolation@Windows@@YAJPEAU_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM@1FsProv@34@PEBU_ISOLATED_OBJECT_ATTRIBUTES@134@PEAU_LBLOB@@PEAU_RTL_ALTERNATE_STATUS@@@Z`
- size: `829`
- prototype: `int(Windows::Isolation::Implementation::Rtl *__hidden this, struct Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM *, const struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *, struct _LBLOB *, struct _RTL_ALTERNATE_STATUS *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800069e5`
- `0x180012950`
- `0x180012b1c`
- `0x180018b30`
- `0x18001f960`
- `0x18001faf4`
- `0x18001fec0`
- `0x180021be0`
- `0x180049e7c`
- `0x1800567b4`
- `0x180056968`
- `0x1800b8a90`
- `0x1800b93e8`
- `0x1800fe440`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180021e7e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180021e7e`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180021de6`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180021de6`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180021dd4`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180021dd4`

## string_xrefs

- `0x180021c03`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\win32\isofs_direct.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Isolation::Implementation::Rtl::RtlpIsolatedFilesystem_DirectWin32_GetFileContents(
        Windows::Isolation::Implementation::Rtl *this,
        struct Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM *a2,
        const struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *a3,
        struct _LBLOB *a4)
{
  void *v6; // rcx
  void *v7; // rcx
  int v8; // ebx
  const struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *v9; // rdx
  void *v10; // rcx
  void *v11; // rcx
  __int64 File; // rax
  int v13; // eax
  int v14; // r9d
  __int64 v15; // rdx
  int v16; // r8d
  DWORD FileSize; // eax
  __int64 v18; // r8
  DWORD LastError_0; // eax
  void *v20; // rcx
  LPVOID v21; // rdi
  DWORD v22; // eax
  int v23; // r9d
  void *v24; // rcx
  void *v25; // rcx
  __int64 v27; // [rsp+40h] [rbp-69h] BYREF
  __int64 v28; // [rsp+48h] [rbp-61h]
  void *v29; // [rsp+50h] [rbp-59h]
  __int64 v30; // [rsp+58h] [rbp-51h]
  __int64 v31; // [rsp+60h] [rbp-49h]
  void *lpMem; // [rsp+68h] [rbp-41h]
  __int64 v33; // [rsp+70h] [rbp-39h]
  int v34; // [rsp+78h] [rbp-31h]
  _BYTE v35[8]; // [rsp+80h] [rbp-29h] BYREF
  HANDLE hFile; // [rsp+88h] [rbp-21h]
  __int64 nNumberOfBytesToRead; // [rsp+90h] [rbp-19h] BYREF
  const char *v38; // [rsp+98h] [rbp-11h] BYREF
  int v39; // [rsp+A0h] [rbp-9h]
  unsigned int v40; // [rsp+A8h] [rbp-1h]
  __int128 v41; // [rsp+B0h] [rbp+7h] BYREF
  LPVOID lpBuffer; // [rsp+C0h] [rbp+17h]
  DWORD NumberOfBytesRead; // [rsp+110h] [rbp+67h] BYREF

  v40 = -1073741595;
  v38 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isofs_direct.cpp";
  if ( this != (Windows::Isolation::Implementation::Rtl *)&Windows::Isolation::Implementation::Rtl::RtlpDirectWin32IsolatedFilesystem )
  {
    v39 = 1670;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
      &v38,
      &v38);
    return v40;
  }
  hFile = (HANDLE)-1LL;
  v28 = 0;
  v27 = 0;
  v29 = 0;
  v31 = 0;
  v30 = 0;
  lpMem = 0;
  v33 = 0;
  v34 = 0;
  v41 = 0u;
  lpBuffer = 0;
  v35[0] = 0;
  if ( a3 )
  {
    *(_OWORD *)a3 = 0;
    *((_QWORD *)a3 + 2) = 0;
  }
  if ( !a2 )
  {
    v39 = 1680;
LABEL_7:
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v38);
    CWin32HandleBase<CWin32FileHandle>::Close(v35);
    v6 = lpMem;
    if ( lpMem )
    {
      v31 = 0;
      v30 = 0;
      lpMem = 0;
      IsolationFreeStringRoutine(v6);
    }
    v7 = v29;
    if ( v29 )
    {
      v28 = 0;
      v27 = 0;
      v29 = 0;
      IsolationFreeStringRoutine(v7);
    }
    return v40;
  }
  if ( !isowin32_IsObjectAttributesValidForWin32Filesystem(a2) )
  {
    v39 = 1681;
    CWin32HandleBase<CWin32FileHandle>::Close(v35);
    v10 = lpMem;
    if ( lpMem )
    {
      v31 = 0;
      v30 = 0;
      lpMem = 0;
      IsolationFreeStringRoutine(v10);
    }
    v11 = v29;
    if ( v29 )
    {
      v28 = 0;
      v27 = 0;
      v29 = 0;
      IsolationFreeStringRoutine(v11);
    }
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v38);
    return v40;
  }
  if ( !a3 )
  {
    v39 = 1682;
    goto LABEL_7;
  }
  v8 = Windows::Isolation::Implementation::Rtl::CWin32FullPath::Initialize(
         (Windows::Isolation::Implementation::Rtl::CWin32FullPath *)&v27,
         v9);
  if ( v8 < 0 )
    goto LABEL_44;
  File = Windows::Isolation::Implementation::Rtl::CreateFile((__int64)&v38, (__int64)&v27, 0x80000000, 1u, 0, 3u, 0x80u);
  if ( *(_QWORD *)(File + 8) == -1 )
  {
    v13 = isowin32private_Win32ErrorAltStatusHelper(*(_DWORD *)File, a4);
    v8 = v13;
    if ( v13 < 0 )
    {
      v15 = 1698;
LABEL_24:
      v16 = v13;
LABEL_25:
      Windows::ErrorHandling::COM::ReportNtErrorOrigination(
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isofs_direct.cpp",
        (const char *)v15,
        v16,
        v14);
LABEL_44:
      CWin32HandleBase<CWin32FileHandle>::Close(v35);
      goto LABEL_45;
    }
    goto LABEL_43;
  }
  CWin32FileHandle::operator=(v35);
  if ( g_KernelHandleToBreakOnCreation && hFile == g_KernelHandleToBreakOnCreation )
    DebugBreak();
  nNumberOfBytesToRead = 0;
  FileSize = GetFileSize(hFile, (LPDWORD)&nNumberOfBytesToRead + 1);
  LODWORD(nNumberOfBytesToRead) = FileSize;
  if ( FileSize == -1 )
  {
    if ( GetLastError_0() )
    {
      LastError_0 = GetLastError_0();
      v13 = isowin32private_Win32ErrorAltStatusHelper(LastError_0, a4);
      v8 = v13;
      if ( v13 < 0 )
      {
        v15 = 1706;
        goto LABEL_24;
      }
LABEL_43:
      v8 = 0;
      goto LABEL_44;
    }
    FileSize = nNumberOfBytesToRead;
  }
  if ( HIDWORD(nNumberOfBytesToRead) )
  {
    v8 = -1073740764;
    v15 = 1711;
    v16 = -1073740764;
    goto LABEL_25;
  }
  v8 = RtlAllocateLBlob(FileSize, &v41, v18);
  if ( v8 >= 0 )
  {
    v21 = lpBuffer;
    NumberOfBytesRead = 0;
    if ( ReadFile(hFile, lpBuffer, nNumberOfBytesToRead, &NumberOfBytesRead, 0) )
    {
      *(_QWORD *)&v41 = (unsigned int)nNumberOfBytesToRead;
      *(_OWORD *)a3 = v41;
      *((_QWORD *)a3 + 2) = v21;
      goto LABEL_43;
    }
    v22 = GetLastError_0();
    v8 = isowin32_ConvertWin32ErrorToNtStatus(v22);
    Windows::ErrorHandling::COM::ReportNtErrorOrigination(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isofs_direct.cpp",
      (const char *)0x6BA,
      v8,
      v23);
    CWin32HandleBase<CWin32FileHandle>::Close(v35);
    if ( v21 )
    {
      v20 = v21;
      goto LABEL_38;
    }
  }
  else
  {
    CWin32HandleBase<CWin32FileHandle>::Close(v35);
    v20 = lpBuffer;
    if ( lpBuffer )
LABEL_38:
      IsolationFreeStringRoutine(v20);
  }
LABEL_45:
  v24 = lpMem;
  if ( lpMem )
  {
    v31 = 0;
    v30 = 0;
    lpMem = 0;
    IsolationFreeStringRoutine(v24);
  }
  v25 = v29;
  if ( v29 )
  {
    v29 = 0;
    v27 = 0;
    v28 = 0;
    IsolationFreeStringRoutine(v25);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180021be0  push    rbp
0x180021be2  push    rbx
0x180021be3  push    rsi
0x180021be4  push    rdi
0x180021be5  push    r12
0x180021be7  push    r15
0x180021be9  lea     rbp, [rsp-2Fh]
0x180021bee  sub     rsp, 0D8h
0x180021bf5  lea     rax, ?RtlpDirectWin32IsolatedFilesystem@Rtl@Implementation@Isolation@Windows@@3U_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM@1FsProv@34@B; Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM const Windows::Isolation::Implementation::Rtl::RtlpDirectWin32IsolatedFilesystem
0x180021bfc  mov     [rbp+57h+var_58], 0C00000E5h
0x180021c03  lea     r12, aOnecoreComNetf_79; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180021c0a  mov     rdi, r9
0x180021c0d  mov     [rbp+57h+var_68], r12
0x180021c11  mov     rsi, r8
0x180021c14  cmp     rcx, rax
0x180021c17  jz      short loc_180021C32
0x180021c19  mov     [rbp+57h+var_60], 686h
0x180021c20  lea     rdx, [rbp+57h+var_68]
0x180021c24  lea     rcx, [rbp+57h+var_68]
0x180021c28  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180021c2d  jmp     loc_180021CD1
0x180021c32  xor     r15d, r15d
0x180021c35  mov     [rbp+57h+hFile], 0FFFFFFFFFFFFFFFFh
0x180021c3d  xor     eax, eax
0x180021c3f  mov     [rbp+57h+var_B8], r15
0x180021c43  mov     [rbp+57h+var_C0], r15
0x180021c47  xorps   xmm0, xmm0
0x180021c4a  mov     [rbp+57h+var_B0], r15
0x180021c4e  mov     [rbp+57h+var_A0], r15
0x180021c52  mov     [rbp+57h+var_A8], r15
0x180021c56  mov     [rbp+57h+lpMem], r15
0x180021c5a  mov     [rbp+57h+var_90], r15
0x180021c5e  mov     [rbp+57h+var_88], r15d
0x180021c62  mov     qword ptr [rbp+57h+var_50+8], r15
0x180021c66  mov     qword ptr [rbp+57h+var_50], r15
0x180021c6a  mov     [rbp+57h+lpBuffer], r15
0x180021c6e  mov     [rbp+57h+var_80], r15b
0x180021c72  test    rsi, rsi
0x180021c75  jz      short loc_180021C7F
0x180021c77  movups  xmmword ptr [r8], xmm0
0x180021c7b  mov     [r8+10h], rax
0x180021c7f  test    rdx, rdx
0x180021c82  jnz     short loc_180021CD9
0x180021c84  mov     [rbp+57h+var_60], 690h
0x180021c8b  lea     rcx, [rbp+57h+var_68]
0x180021c8f  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x180021c94  lea     rcx, [rbp+57h+var_80]
0x180021c98  call    ?Close@?$CWin32HandleBase@VCWin32FileHandle@@@@QEAAXXZ; CWin32HandleBase<CWin32FileHandle>::Close(void)
0x180021c9d  mov     rcx, [rbp+57h+lpMem]; lpMem
0x180021ca1  test    rcx, rcx
0x180021ca4  jz      short loc_180021CB7
0x180021ca6  mov     [rbp+57h+var_A0], r15
0x180021caa  mov     [rbp+57h+var_A8], r15
0x180021cae  mov     [rbp+57h+lpMem], r15
0x180021cb2  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180021cb7  mov     rcx, [rbp+57h+var_B0]; lpMem
0x180021cbb  test    rcx, rcx
0x180021cbe  jz      short loc_180021CD1
0x180021cc0  mov     [rbp+57h+var_B8], r15
0x180021cc4  mov     [rbp+57h+var_C0], r15
0x180021cc8  mov     [rbp+57h+var_B0], r15
0x180021ccc  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180021cd1  mov     ebx, [rbp+57h+var_58]
0x180021cd4  jmp     loc_180021F0B
0x180021cd9  mov     rcx, rdx; struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *
0x180021cdc  call    ?isowin32_IsObjectAttributesValidForWin32Filesystem@@YAEPEBU_ISOLATED_OBJECT_ATTRIBUTES@Rtl@Isolation@Windows@@@Z; isowin32_IsObjectAttributesValidForWin32Filesystem(Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES const *)
0x180021ce1  test    al, al
0x180021ce3  jnz     short loc_180021D34
0x180021ce5  lea     rcx, [rbp+57h+var_80]
0x180021ce9  mov     [rbp+57h+var_60], 691h
0x180021cf0  call    ?Close@?$CWin32HandleBase@VCWin32FileHandle@@@@QEAAXXZ; CWin32HandleBase<CWin32FileHandle>::Close(void)
0x180021cf5  mov     rcx, [rbp+57h+lpMem]; lpMem
0x180021cf9  test    rcx, rcx
0x180021cfc  jz      short loc_180021D0F
0x180021cfe  mov     [rbp+57h+var_A0], r15
0x180021d02  mov     [rbp+57h+var_A8], r15
0x180021d06  mov     [rbp+57h+lpMem], r15
0x180021d0a  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180021d0f  mov     rcx, [rbp+57h+var_B0]; lpMem
0x180021d13  test    rcx, rcx
0x180021d16  jz      short loc_180021D29
0x180021d18  mov     [rbp+57h+var_B8], r15
0x180021d1c  mov     [rbp+57h+var_C0], r15
0x180021d20  mov     [rbp+57h+var_B0], r15
0x180021d24  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180021d29  lea     rcx, [rbp+57h+var_68]
0x180021d2d  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x180021d32  jmp     short loc_180021CD1
0x180021d34  test    rsi, rsi
0x180021d37  jnz     short loc_180021D45
0x180021d39  mov     [rbp+57h+var_60], 692h
0x180021d40  jmp     loc_180021C8B
0x180021d45  lea     rcx, [rbp+57h+var_C0]; this
0x180021d49  call    ?Initialize@CWin32FullPath@Rtl@Implementation@Isolation@Windows@@QEAAJAEBU_ISOLATED_OBJECT_ATTRIBUTES@245@@Z; Windows::Isolation::Implementation::Rtl::CWin32FullPath::Initialize(Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES const &)
0x180021d4e  mov     ebx, eax
0x180021d50  test    eax, eax
0x180021d52  js      loc_180021ECE
0x180021d58  mov     [rsp+100h+var_D0], 80h
0x180021d60  lea     rdx, [rbp+57h+var_C0]
0x180021d64  mov     [rsp+100h+var_D8], 3
0x180021d6c  lea     rcx, [rbp+57h+var_68]
0x180021d70  mov     r9d, 1
0x180021d76  mov     [rsp+100h+lpOverlapped], r15
0x180021d7b  mov     r8d, 80000000h
0x180021d81  call    ?CreateFile@Rtl@Implementation@Isolation@Windows@@YA?AU_WIN32_FUNCTION_RETURN_STATUS@@AEBVCWin32FullPath@1234@KKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; Windows::Isolation::Implementation::Rtl::CreateFile(Windows::Isolation::Implementation::Rtl::CWin32FullPath const &,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x180021d86  mov     rdx, [rax+8]
0x180021d8a  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180021d8e  jnz     short loc_180021DB9
0x180021d90  mov     ecx, [rax]; unsigned int
0x180021d92  mov     rdx, rdi; struct _RTL_ALTERNATE_STATUS *
0x180021d95  call    ?isowin32private_Win32ErrorAltStatusHelper@@YAJKPEAU_RTL_ALTERNATE_STATUS@@@Z; isowin32private_Win32ErrorAltStatusHelper(ulong,_RTL_ALTERNATE_STATUS *)
0x180021d9a  mov     ebx, eax
0x180021d9c  test    eax, eax
0x180021d9e  jns     loc_180021ECB
0x180021da4  mov     edx, 6A2h; char *
0x180021da9  mov     r8d, eax; int
0x180021dac  mov     rcx, r12; this
0x180021daf  call    ?ReportNtErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportNtErrorOrigination(char const *,int,long)
0x180021db4  jmp     loc_180021ECE
0x180021db9  lea     rcx, [rbp+57h+var_80]
0x180021dbd  call    ??4CWin32FileHandle@@QEAAPEAXPEAX@Z; CWin32FileHandle::operator=(void *)
0x180021dc2  mov     rax, cs:?g_KernelHandleToBreakOnCreation@@3PEAXEA; void * g_KernelHandleToBreakOnCreation
0x180021dc9  test    rax, rax
0x180021dcc  jz      short loc_180021DDA
0x180021dce  cmp     [rbp+57h+hFile], rax
0x180021dd2  jnz     short loc_180021DDA
0x180021dd4  call    cs:__imp_DebugBreak
0x180021dda  mov     rcx, [rbp+57h+hFile]; hFile
0x180021dde  lea     rdx, [rbp+57h+FileSizeHigh]; lpFileSizeHigh
0x180021de2  mov     [rbp-19h], r15
0x180021de6  call    cs:__imp_GetFileSize
0x180021dec  mov     [rbp+57h+nNumberOfBytesToRead], eax
0x180021def  cmp     eax, 0FFFFFFFFh
0x180021df2  jnz     short loc_180021E20
0x180021df4  call    GetLastError_0
0x180021df9  test    eax, eax
0x180021dfb  jz      short loc_180021E1D
0x180021dfd  call    GetLastError_0
0x180021e02  mov     ecx, eax; unsigned int
0x180021e04  mov     rdx, rdi; struct _RTL_ALTERNATE_STATUS *
0x180021e07  call    ?isowin32private_Win32ErrorAltStatusHelper@@YAJKPEAU_RTL_ALTERNATE_STATUS@@@Z; isowin32private_Win32ErrorAltStatusHelper(ulong,_RTL_ALTERNATE_STATUS *)
0x180021e0c  mov     ebx, eax
0x180021e0e  test    eax, eax
0x180021e10  jns     loc_180021ECB
0x180021e16  mov     edx, 6AAh
0x180021e1b  jmp     short loc_180021DA9
0x180021e1d  mov     eax, [rbp+57h+nNumberOfBytesToRead]
0x180021e20  cmp     [rbp+57h+FileSizeHigh], r15d
0x180021e24  jz      short loc_180021E38
0x180021e26  mov     ebx, 0C0000424h
0x180021e2b  mov     edx, 6AFh
0x180021e30  mov     r8d, ebx
0x180021e33  jmp     loc_180021DAC
0x180021e38  mov     ecx, eax
0x180021e3a  lea     rdx, [rbp+57h+var_50]
0x180021e3e  call    RtlAllocateLBlob
0x180021e43  mov     ebx, eax
0x180021e45  test    eax, eax
0x180021e47  jns     short loc_180021E62
0x180021e49  lea     rcx, [rbp+57h+var_80]
0x180021e4d  call    ?Close@?$CWin32HandleBase@VCWin32FileHandle@@@@QEAAXXZ; CWin32HandleBase<CWin32FileHandle>::Close(void)
0x180021e52  mov     rcx, [rbp+57h+lpBuffer]; lpMem
0x180021e56  test    rcx, rcx
0x180021e59  jz      short loc_180021ED7
0x180021e5b  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180021e60  jmp     short loc_180021ED7
0x180021e62  mov     rdi, [rbp+57h+lpBuffer]
0x180021e66  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180021e6a  mov     r8d, [rbp+57h+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x180021e6e  mov     rdx, rdi; lpBuffer
0x180021e71  mov     rcx, [rbp+57h+hFile]; hFile
0x180021e75  mov     [rbp+57h+NumberOfBytesRead], r15d
0x180021e79  mov     [rsp+100h+lpOverlapped], r15; lpOverlapped
0x180021e7e  call    cs:__imp_ReadFile
0x180021e84  test    eax, eax
0x180021e86  jnz     short loc_180021EB9
0x180021e88  call    GetLastError_0
0x180021e8d  mov     ecx, eax; unsigned int
0x180021e8f  call    ?isowin32_ConvertWin32ErrorToNtStatus@@YAJK@Z; isowin32_ConvertWin32ErrorToNtStatus(ulong)
0x180021e94  mov     r8d, eax; int
0x180021e97  mov     edx, 6BAh; char *
0x180021e9c  mov     rcx, r12; this
0x180021e9f  mov     ebx, eax
0x180021ea1  call    ?ReportNtErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportNtErrorOrigination(char const *,int,long)
0x180021ea6  lea     rcx, [rbp+57h+var_80]
0x180021eaa  call    ?Close@?$CWin32HandleBase@VCWin32FileHandle@@@@QEAAXXZ; CWin32HandleBase<CWin32FileHandle>::Close(void)
0x180021eaf  test    rdi, rdi
0x180021eb2  jz      short loc_180021ED7
0x180021eb4  mov     rcx, rdi
0x180021eb7  jmp     short loc_180021E5B
0x180021eb9  mov     eax, [rbp+57h+nNumberOfBytesToRead]
0x180021ebc  mov     qword ptr [rbp+57h+var_50], rax
0x180021ec0  movups  xmm0, [rbp+57h+var_50]
0x180021ec4  movups  xmmword ptr [rsi], xmm0
0x180021ec7  mov     [rsi+10h], rdi
0x180021ecb  mov     ebx, r15d
0x180021ece  lea     rcx, [rbp+57h+var_80]
0x180021ed2  call    ?Close@?$CWin32HandleBase@VCWin32FileHandle@@@@QEAAXXZ; CWin32HandleBase<CWin32FileHandle>::Close(void)
0x180021ed7  mov     rcx, [rbp+57h+lpMem]; lpMem
0x180021edb  test    rcx, rcx
0x180021ede  jz      short loc_180021EF1
0x180021ee0  mov     [rbp+57h+var_A0], r15
0x180021ee4  mov     [rbp+57h+var_A8], r15
0x180021ee8  mov     [rbp+57h+lpMem], r15
0x180021eec  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180021ef1  mov     rcx, [rbp+57h+var_B0]; lpMem
0x180021ef5  test    rcx, rcx
0x180021ef8  jz      short loc_180021F0B
0x180021efa  mov     [rbp+57h+var_B0], r15
0x180021efe  mov     [rbp+57h+var_C0], r15
0x180021f02  mov     [rbp+57h+var_B8], r15
0x180021f06  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180021f0b  mov     eax, ebx
0x180021f0d  add     rsp, 0D8h
0x180021f14  pop     r15
0x180021f16  pop     r12
0x180021f18  pop     rdi
0x180021f19  pop     rsi
0x180021f1a  pop     rbx
0x180021f1b  pop     rbp
0x180021f1c  retn
```
