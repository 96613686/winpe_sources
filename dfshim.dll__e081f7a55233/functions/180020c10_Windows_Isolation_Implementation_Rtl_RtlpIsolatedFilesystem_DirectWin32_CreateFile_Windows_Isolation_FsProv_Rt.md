# Windows::Isolation::Implementation::Rtl::RtlpIsolatedFilesystem_DirectWin32_CreateFile(Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM *,Windows::Isolation::FsProv::Rtl::_PROVIDER_ISOLATED_FILE *,ulong,Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES const *,_IO_STATUS_BLOCK *,_LARGE_INTEGER *,ulong,ulong,ulong,ulong,void const *,unsigned __int64,_RTL_ALTERNATE_STATUS *)

- ea: `0x180020c10`
- end: `0x1800213f3`
- name: `?RtlpIsolatedFilesystem_DirectWin32_CreateFile@Rtl@Implementation@Isolation@Windows@@YAJPEAU_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM@1FsProv@34@PEAT_PROVIDER_ISOLATED_FILE@1634@KPEBU_ISOLATED_OBJECT_ATTRIBUTES@134@PEAU_IO_STATUS_BLOCK@@PEAT_LARGE_INTEGER@@KKKKPEBX_KPEAU_RTL_ALTERNATE_STATUS@@@Z`
- size: `2019`
- prototype: `int(Windows::Isolation::Implementation::Rtl *__hidden this, struct Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM *, union Windows::Isolation::FsProv::Rtl::_PROVIDER_ISOLATED_FILE *, unsigned int, const struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *, struct _IO_STATUS_BLOCK *, union _LARGE_INTEGER *, unsigned int, unsigned int, unsigned int, unsigned int, const void *, unsigned __int64, struct _RTL_ALTERNATE_STATUS *)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, reparse_path, broker_com_uri`

## callees

- `0x1800069a9`
- `0x1800069b5`
- `0x1800069c1`
- `0x1800069e5`
- `0x1800069fd`
- `0x180012950`
- `0x180012b1c`
- `0x180018b30`
- `0x18001f960`
- `0x18001faf4`
- `0x18001fec0`
- `0x1800203d4`
- `0x180020c10`
- `0x180056968`
- `0x1800b8a90`
- `0x1800b93e8`
- `0x1800b9988`
- `0x1800b9ad4`
- `0x1800fe440`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002102c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002102c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryA` at `0x180020ff2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryA` at `0x180020ff2`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180021257`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180021257`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020fe0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002101a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020fe0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002101a`

## string_xrefs

- `0x180020c46`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\win32\isofs_direct.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Isolation::Implementation::Rtl::RtlpIsolatedFilesystem_DirectWin32_CreateFile(
        Windows::Isolation::Implementation::Rtl *this,
        struct Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM *a2,
        union Windows::Isolation::FsProv::Rtl::_PROVIDER_ISOLATED_FILE *a3,
        __int64 a4,
        const struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *a5,
        struct _IO_STATUS_BLOCK *a6,
        union _LARGE_INTEGER *a7,
        unsigned int a8,
        unsigned int a9,
        unsigned int a10,
        struct _SECURITY_ATTRIBUTES *a11,
        struct _SECURITY_ATTRIBUTES *a12,
        struct _RTL_ALTERNATE_STATUS *a13)
{
  unsigned int v13; // ebx
  int v14; // ebx
  struct _SECURITY_ATTRIBUTES *v15; // r8
  int v16; // r9d
  unsigned int v17; // ecx
  unsigned int v18; // edx
  __int64 v19; // rdx
  signed int Version_0; // eax
  unsigned int v21; // r15d
  __int64 v22; // r12
  int v23; // r14d
  int v24; // r13d
  struct _SECURITY_ATTRIBUTES *v25; // rax
  int v26; // r9d
  int v27; // eax
  unsigned int v28; // r15d
  unsigned int *FileAttributes; // rax
  int v30; // r9d
  unsigned int v31; // ecx
  int v32; // eax
  int v33; // r9d
  __int64 v34; // rdx
  struct _SECURITY_ATTRIBUTES *v35; // rbx
  struct _SECURITY_ATTRIBUTES *v36; // rcx
  BOOL DirectoryA; // eax
  struct _SECURITY_ATTRIBUTES *v38; // rcx
  DWORD LastError_0; // eax
  int v40; // eax
  int v41; // r9d
  void *v42; // rcx
  void *v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rdx
  void *v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rcx
  __int64 v50; // rax
  __int64 v51; // rax
  HANDLE ProcessHeap_0; // rax
  char *v53; // rax
  struct _LUNICODE_STRING *v54; // r8
  void (__fastcall ***v55)(_QWORD, _QWORD); // rdi
  struct _LUNICODE_STRING *v56; // r8
  HANDLE v57; // rax
  void *v58; // rcx
  struct _SECURITY_ATTRIBUTES *v60; // [rsp+48h] [rbp-C0h] BYREF
  struct _SECURITY_ATTRIBUTES *v61; // [rsp+50h] [rbp-B8h]
  void *v62; // [rsp+58h] [rbp-B0h]
  struct _SECURITY_ATTRIBUTES *v63; // [rsp+60h] [rbp-A8h]
  struct _SECURITY_ATTRIBUTES *v64; // [rsp+68h] [rbp-A0h]
  void *lpMem; // [rsp+70h] [rbp-98h]
  struct _SECURITY_ATTRIBUTES *v66; // [rsp+78h] [rbp-90h]
  int v67; // [rsp+80h] [rbp-88h]
  char v68[8]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v69; // [rsp+90h] [rbp-78h]
  const char *v70; // [rsp+98h] [rbp-70h] BYREF
  int v71; // [rsp+A0h] [rbp-68h]
  unsigned int v72; // [rsp+A8h] [rbp-60h]
  __int64 v73; // [rsp+B0h] [rbp-58h] BYREF
  struct _SECURITY_ATTRIBUTES *v74; // [rsp+B8h] [rbp-50h]
  __int64 v75; // [rsp+C0h] [rbp-48h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+C8h] [rbp-40h]
  const char *v77; // [rsp+D0h] [rbp-38h] BYREF
  int v78; // [rsp+D8h] [rbp-30h]
  int v79; // [rsp+E0h] [rbp-28h]
  char v80[32]; // [rsp+E8h] [rbp-20h] BYREF
  char v81[16]; // [rsp+108h] [rbp+0h] BYREF
  char v82[64]; // [rsp+118h] [rbp+10h] BYREF
  unsigned int v83; // [rsp+168h] [rbp+60h]

  v72 = -1073741595;
  v70 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isofs_direct.cpp";
  v13 = (unsigned int)a3;
  if ( this != (Windows::Isolation::Implementation::Rtl *)&Windows::Isolation::Implementation::Rtl::RtlpDirectWin32IsolatedFilesystem )
  {
    v71 = 963;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
      &v70,
      &v70);
    return v72;
  }
  if ( a2 )
    *(_QWORD *)a2 = 0;
  if ( a13 )
    *((_DWORD *)a13 + 4) = 0;
  if ( a5 )
    *(_OWORD *)a5 = 0;
  if ( !a2 )
  {
    v71 = 974;
LABEL_11:
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v70);
    return v72;
  }
  if ( !a4 )
  {
    v71 = 975;
    goto LABEL_11;
  }
  if ( !a5 )
  {
    v71 = 976;
    goto LABEL_11;
  }
  if ( !isowin32_IsObjectAttributesValidForWin32Filesystem((const struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *)a4) )
  {
    v71 = 977;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v70);
    return v72;
  }
  v17 = a10;
  v18 = a10 & 1;
  v83 = v18;
  if ( ((a10 & 0x40) != 0) == (_BYTE)v18 )
  {
    v19 = 989;
LABEL_21:
    v14 = -1073741637;
LABEL_22:
    Windows::ErrorHandling::COM::ReportNtErrorOrigination(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isofs_direct.cpp",
      (const char *)v19,
      v14,
      v16);
    return (unsigned int)v14;
  }
  if ( (a8 & 4) != 0 )
  {
    Version_0 = GetVersion_0();
    v17 = a10;
    v15 = 0;
    v18 = v83;
    if ( Version_0 < 0 )
      a8 &= ~4u;
  }
  if ( a11 != v15 )
  {
    v14 = -1073741745;
    v19 = 1002;
    goto LABEL_22;
  }
  if ( a12 != v15 )
  {
    v14 = -1073741745;
    v19 = 1007;
    goto LABEL_22;
  }
  if ( (v17 & 0xF0A390) != 0 )
  {
    v19 = 878;
    goto LABEL_21;
  }
  if ( (~(_BYTE)v17 & 0x20) != 0 )
  {
    v19 = 883;
    goto LABEL_21;
  }
  if ( (v17 & 0x4000) != 0 && !v18 )
  {
    v19 = 898;
    goto LABEL_21;
  }
  v21 = v13;
  if ( (v13 & 0x120089) == 0x120089 )
    v21 = v13 & 0x7FEDFF76 | 0x80000000;
  if ( (v13 & 0x120116) == 0x120116 )
    v21 = v21 & 0xBFEDFEE9 | 0x40000100;
  v79 = -1073741595;
  v77 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isofs_direct.cpp";
  v22 = 2;
  if ( (v13 & 0x1F01FF) == 0x1F01FF )
    v21 = -1073676032;
  if ( (v13 & 0x10000000) != 0 )
    v21 = -1073676032;
  switch ( a9 )
  {
    case 0u:
LABEL_54:
      v23 = 2;
      break;
    case 1u:
      v23 = 3;
      break;
    case 2u:
      v23 = 1;
      break;
    case 3u:
      v23 = 4;
      break;
    default:
      if ( a9 - 4 >= 2 )
      {
        v23 = (int)v15;
        v78 = 830;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v77);
        v17 = a10;
        v15 = 0;
        v14 = v79;
        goto LABEL_56;
      }
      goto LABEL_54;
  }
  v14 = (int)v15;
LABEL_56:
  if ( v14 < 0 )
    return (unsigned int)v14;
  v24 = (int)v15;
  v25 = v15;
  do
  {
    if ( (v17 & *((_DWORD *)qword_1801423D0 + (_QWORD)v25)) != 0 )
      v24 |= *((_DWORD *)qword_1801423D0 + (_QWORD)v25 + 1);
    v25 = (struct _SECURITY_ATTRIBUTES *)((char *)v25 + 2);
  }
  while ( v25 != (struct _SECURITY_ATTRIBUTES *)8 );
  lpSecurityAttributes = v15;
  v73 = 24;
  v75 = 0;
  v74 = v15;
  v61 = v15;
  v60 = v15;
  v62 = v15;
  v64 = v15;
  v63 = v15;
  lpMem = v15;
  v66 = v15;
  v67 = (int)v15;
  v68[0] = (char)v15;
  v69 = -1;
  v14 = Windows::Isolation::Implementation::Rtl::CWin32FullPath::Initialize(
          (Windows::Isolation::Implementation::Rtl::CWin32FullPath *)&v60,
          (const struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *)a4);
  if ( v14 >= 0 )
  {
    v27 = *(_DWORD *)(a4 + 24) & 2;
    if ( v27 )
      LODWORD(v75) = 1;
    if ( *(_QWORD *)(a4 + 32) )
    {
      v74 = *(struct _SECURITY_ATTRIBUTES **)(a4 + 32);
    }
    else if ( !v27 )
    {
      goto LABEL_68;
    }
    lpSecurityAttributes = (LPSECURITY_ATTRIBUTES)&v73;
LABEL_68:
    v28 = v21 & 0xC0010100;
    if ( (_BYTE)v83 )
    {
      if ( v23 == 2 )
      {
        v14 = -1073740756;
        Windows::ErrorHandling::COM::ReportNtErrorOrigination(
          (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isofs_direct.cpp",
          (const char *)0x40E,
          -1073740756,
          v26);
        goto LABEL_140;
      }
      FileAttributes = (unsigned int *)Windows::Isolation::Implementation::Rtl::GetFileAttributes(v80, &v60);
      v31 = FileAttributes[2];
      if ( v31 == -1 )
      {
        if ( v23 != 1 && v23 != 4 )
        {
          v32 = isowin32private_Win32ErrorAltStatusHelper(*FileAttributes, a13);
          v14 = v32;
          if ( v32 < 0 )
          {
            v34 = 1051;
LABEL_76:
            Windows::ErrorHandling::COM::ReportNtErrorOrigination(
              (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isofs_direct.cpp",
              (const char *)v34,
              v32,
              v33);
            goto LABEL_140;
          }
LABEL_139:
          v14 = 0;
          goto LABEL_140;
        }
        v35 = lpSecurityAttributes;
        if ( v67 == 1 )
        {
          v36 = v66;
          if ( !v66 )
          {
            RaiseException(0xC00000E5, 1u, 0, 0);
            v36 = v66;
          }
          DirectoryA = CreateDirectoryA(*(LPCSTR *)&v36->bInheritHandle, v35);
        }
        else
        {
          if ( v67 != 2 || (v38 = v66) == 0 )
          {
            RaiseException(0xC00000E5, 1u, 0, 0);
            v38 = v66;
          }
          DirectoryA = CreateDirectoryW(*(LPCWSTR *)&v38->bInheritHandle, v35);
        }
        if ( !DirectoryA )
        {
          LastError_0 = GetLastError_0();
          v40 = isowin32private_Win32ErrorAltStatusHelper(LastError_0, a13);
          v14 = v40;
          if ( v40 >= 0 )
            v14 = 0;
          else
            Windows::ErrorHandling::COM::ReportNtErrorOrigination(
              (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isofs_direct.cpp",
              (const char *)0x427,
              v40,
              v41);
          CWin32HandleBase<CWin32FileHandle>::Close(v68);
          v42 = lpMem;
          if ( lpMem )
          {
            v64 = 0;
            v63 = 0;
            lpMem = 0;
            IsolationFreeStringRoutine(v42);
          }
          v43 = v62;
          if ( !v62 )
            return (unsigned int)v14;
          v61 = 0;
          v60 = 0;
          v62 = 0;
          goto LABEL_144;
        }
LABEL_128:
        *((_QWORD *)a5 + 1) = v22;
        if ( !a13 )
          goto LABEL_131;
        goto LABEL_129;
      }
      if ( v23 == 1 )
      {
        v14 = 0x40000000;
        if ( a13 )
        {
          *((_DWORD *)a13 + 4) = 0x40000000;
          if ( *(_QWORD *)a13 )
          {
            v44 = 0;
            while ( *(_DWORD *)(*((_QWORD *)a13 + 1) + 4 * v44) != 0x40000000 )
            {
              if ( (unsigned __int64)++v44 >= *(_QWORD *)a13 )
                goto LABEL_99;
            }
            goto LABEL_129;
          }
        }
LABEL_99:
        v45 = 1077;
      }
      else
      {
        if ( (v31 & 0x10) != 0 )
        {
          *((_QWORD *)a5 + 1) = 1;
          if ( !a13 )
            goto LABEL_131;
          *((_DWORD *)a13 + 4) = 0;
          goto LABEL_129;
        }
        v14 = -1073741788;
        if ( a13 )
        {
          *((_DWORD *)a13 + 4) = -1073741788;
          if ( *(_QWORD *)a13 )
          {
            v47 = 0;
            while ( *(_DWORD *)(*((_QWORD *)a13 + 1) + 4 * v47) != -1073741788 )
            {
              if ( (unsigned __int64)++v47 >= *(_QWORD *)a13 )
                goto LABEL_111;
            }
LABEL_129:
            if ( *((int *)a13 + 4) < 0 )
            {
              v14 = -1073741536;
              goto LABEL_101;
            }
LABEL_131:
            ProcessHeap_0 = GetProcessHeap_0();
            v53 = (char *)HeapAlloc_0(ProcessHeap_0, 0, 0x70u);
            v55 = (void (__fastcall ***)(_QWORD, _QWORD))v53;
            if ( v53 )
            {
              *((_QWORD *)v53 + 2) = 0;
              *((_QWORD *)v53 + 1) = 0;
              *((_QWORD *)v53 + 3) = 0;
              *(_QWORD *)v53 = &Windows::Isolation::Implementation::Rtl::CDirectWin32FsObject::`vftable';
              *((_QWORD *)v53 + 9) = -1;
              *((_QWORD *)v53 + 11) = -1;
              *((_QWORD *)v53 + 5) = 0;
              *((_QWORD *)v53 + 4) = 0;
              *((_QWORD *)v53 + 6) = 0;
              *((_WORD *)v53 + 28) = 0;
              v53[64] = 0;
              v53[80] = 0;
              *((_DWORD *)v53 + 24) = 0;
              v14 = Windows::Isolation::Implementation::Rtl::ObjectAttributesToNtPath(
                      (Windows::Isolation::Implementation::Rtl *)a4,
                      (const struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *)(v53 + 32),
                      v54);
              if ( v14 < 0
                || (v14 = Windows::Isolation::Implementation::Rtl::ObjectAttributesToWin32Path(
                            (Windows::Isolation::Implementation::Rtl *)a4,
                            (const struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *)(v55 + 1),
                            v56),
                    v14 < 0) )
              {
                (**v55)(v55, 0);
                v57 = GetProcessHeap_0();
                HeapFree_0(v57, 0, v55);
              }
              else
              {
                v69 = -1;
                v68[0] = 0;
                CWin32FileHandle::operator=(v55 + 8);
                v14 = 0;
                *((_BYTE *)v55 + 56) = v83;
                *((_BYTE *)v55 + 57) = (a10 & 0x1000) != 0;
                *((_DWORD *)v55 + 24) = v28;
                *(_QWORD *)a2 = v55;
              }
            }
            else
            {
              v14 = -1073741801;
            }
            goto LABEL_101;
          }
        }
LABEL_111:
        v45 = 1084;
      }
LABEL_100:
      Windows::ErrorHandling::COM::ReportNtErrorOrigination(
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isofs_direct.cpp",
        (const char *)v45,
        v14,
        v30);
LABEL_101:
      CWin32HandleBase<CWin32FileHandle>::Close(v68);
      v46 = lpMem;
      if ( lpMem )
      {
        v64 = 0;
        v63 = 0;
        lpMem = 0;
        IsolationFreeStringRoutine(v46);
      }
      v43 = v62;
      if ( !v62 )
        return (unsigned int)v14;
      v61 = 0;
      v60 = 0;
      v62 = 0;
LABEL_144:
      IsolationFreeStringRoutine(v43);
      return (unsigned int)v14;
    }
    v48 = Windows::Isolation::Implementation::Rtl::GetFileAttributes(v81, &v60);
    v49 = *(_QWORD *)(v48 + 8);
    if ( (_DWORD)v49 == -1 )
    {
      if ( (unsigned int)(*(_DWORD *)v48 - 2) <= 1 )
      {
LABEL_124:
        v51 = Windows::Isolation::Implementation::Rtl::CreateFile(v82, &v60, v28, a8, lpSecurityAttributes, v23, v24);
        if ( *(_QWORD *)(v51 + 8) == -1 )
        {
          v32 = isowin32private_Win32ErrorAltStatusHelper(*(_DWORD *)v51, a13);
          v14 = v32;
          if ( v32 < 0 )
          {
            v34 = 1157;
            goto LABEL_76;
          }
          goto LABEL_139;
        }
        CWin32FileHandle::operator=(v68);
        if ( g_KernelHandleToBreakOnCreation && (void *)v69 == g_KernelHandleToBreakOnCreation )
          DebugBreak();
        goto LABEL_128;
      }
    }
    else if ( (v49 & 0x10) != 0 )
    {
      v14 = -1073741638;
      if ( !a13 || (*((_DWORD *)a13 + 4) = -1073741638, !*(_QWORD *)a13) )
      {
LABEL_121:
        v45 = 1128;
        goto LABEL_100;
      }
      v50 = 0;
      while ( *(_DWORD *)(*((_QWORD *)a13 + 1) + 4 * v50) != -1073741638 )
      {
        if ( (unsigned __int64)++v50 >= *(_QWORD *)a13 )
          goto LABEL_121;
      }
    }
    v22 = 1;
    goto LABEL_124;
  }
LABEL_140:
  CWin32HandleBase<CWin32FileHandle>::Close(v68);
  v58 = lpMem;
  if ( lpMem )
  {
    v64 = 0;
    v63 = 0;
    lpMem = 0;
    IsolationFreeStringRoutine(v58);
  }
  v43 = v62;
  if ( v62 )
  {
    v62 = 0;
    v60 = 0;
    v61 = 0;
    goto LABEL_144;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180020c10  mov     rax, rsp
0x180020c13  mov     [rax+18h], rbx
0x180020c17  mov     [rax+20h], r9
0x180020c1b  mov     [rax+10h], rdx
0x180020c1f  push    rbp
0x180020c20  push    rsi
0x180020c21  push    rdi
0x180020c22  push    r12
0x180020c24  push    r13
0x180020c26  push    r14
0x180020c28  push    r15
0x180020c2a  lea     rbp, [rax-58h]
0x180020c2e  sub     rsp, 120h
0x180020c35  lea     rax, ?RtlpDirectWin32IsolatedFilesystem@Rtl@Implementation@Isolation@Windows@@3U_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM@1FsProv@34@B; Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM const Windows::Isolation::Implementation::Rtl::RtlpDirectWin32IsolatedFilesystem
0x180020c3c  mov     r12d, 0C00000E5h
0x180020c42  mov     [rbp+50h+var_B0], r12d
0x180020c46  lea     rsi, aOnecoreComNetf_79; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180020c4d  mov     [rbp+50h+var_C0], rsi
0x180020c51  mov     ebx, r8d
0x180020c54  cmp     rcx, rax
0x180020c57  jz      short loc_180020C6F
0x180020c59  mov     [rbp+50h+var_B8], 3C3h
0x180020c60  lea     rdx, [rbp+50h+var_C0]
0x180020c64  lea     rcx, [rbp+50h+var_C0]
0x180020c68  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180020c6d  jmp     short loc_180020CB1
0x180020c6f  xor     r8d, r8d
0x180020c72  test    rdx, rdx
0x180020c75  jz      short loc_180020C7A
0x180020c77  mov     [rdx], r8
0x180020c7a  mov     rdi, [rbp+50h+arg_60]
0x180020c81  test    rdi, rdi
0x180020c84  jz      short loc_180020C8A
0x180020c86  mov     [rdi+10h], r8d
0x180020c8a  mov     rax, [rbp+50h+arg_20]
0x180020c91  test    rax, rax
0x180020c94  jz      short loc_180020C9C
0x180020c96  xorps   xmm0, xmm0
0x180020c99  movups  xmmword ptr [rax], xmm0
0x180020c9c  test    rdx, rdx
0x180020c9f  jnz     short loc_180020CB9
0x180020ca1  mov     [rbp+50h+var_B8], 3CEh
0x180020ca8  lea     rcx, [rbp+50h+var_C0]
0x180020cac  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x180020cb1  mov     ebx, [rbp+50h+var_B0]
0x180020cb4  jmp     loc_1800213D6
0x180020cb9  test    r9, r9
0x180020cbc  jnz     short loc_180020CC7
0x180020cbe  mov     [rbp+50h+var_B8], 3CFh
0x180020cc5  jmp     short loc_180020CA8
0x180020cc7  test    rax, rax
0x180020cca  jnz     short loc_180020CD5
0x180020ccc  mov     [rbp+50h+var_B8], 3D0h
0x180020cd3  jmp     short loc_180020CA8
0x180020cd5  mov     rcx, r9; struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *
0x180020cd8  call    ?isowin32_IsObjectAttributesValidForWin32Filesystem@@YAEPEBU_ISOLATED_OBJECT_ATTRIBUTES@Rtl@Isolation@Windows@@@Z; isowin32_IsObjectAttributesValidForWin32Filesystem(Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES const *)
0x180020cdd  test    al, al
0x180020cdf  jnz     short loc_180020CF3
0x180020ce1  mov     [rbp+50h+var_B8], 3D1h
0x180020ce8  lea     rcx, [rbp+50h+var_C0]
0x180020cec  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x180020cf1  jmp     short loc_180020CB1
0x180020cf3  mov     ecx, [rbp+50h+arg_48]
0x180020cf9  mov     eax, ecx
0x180020cfb  shr     eax, 6
0x180020cfe  mov     edx, ecx
0x180020d00  and     edx, 1
0x180020d03  and     al, 1
0x180020d05  mov     [rbp+50h+arg_0], edx
0x180020d08  cmp     al, dl
0x180020d0a  jnz     short loc_180020D26
0x180020d0c  mov     edx, 3DDh; char *
0x180020d11  mov     ebx, 0C00000BBh
0x180020d16  mov     r8d, ebx; int
0x180020d19  mov     rcx, rsi; this
0x180020d1c  call    ?ReportNtErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportNtErrorOrigination(char const *,int,long)
0x180020d21  jmp     loc_1800213D6
0x180020d26  mov     r14d, [rbp+50h+arg_38]
0x180020d2d  test    r14b, 4
0x180020d31  jz      short loc_180020D53
0x180020d33  call    GetVersion_0
0x180020d38  mov     ecx, [rbp+50h+arg_48]
0x180020d3e  xor     r8d, r8d
0x180020d41  mov     edx, [rbp+50h+arg_0]
0x180020d44  test    eax, eax
0x180020d46  jns     short loc_180020D53
0x180020d48  and     r14d, 0FFFFFFFBh
0x180020d4c  mov     [rbp+50h+arg_38], r14d
0x180020d53  cmp     [rbp+50h+arg_50], r8
0x180020d5a  jz      short loc_180020D68
0x180020d5c  mov     ebx, 0C000004Fh
0x180020d61  mov     edx, 3EAh
0x180020d66  jmp     short loc_180020D16
0x180020d68  cmp     [rbp+50h+arg_58], r8
0x180020d6f  jz      short loc_180020D7D
0x180020d71  mov     ebx, 0C000004Fh
0x180020d76  mov     edx, 3EFh
0x180020d7b  jmp     short loc_180020D16
0x180020d7d  test    ecx, 0F0A390h
0x180020d83  jz      short loc_180020D8C
0x180020d85  mov     edx, 36Eh
0x180020d8a  jmp     short loc_180020D11
0x180020d8c  mov     eax, ecx
0x180020d8e  not     eax
0x180020d90  test    al, 20h
0x180020d92  jz      short loc_180020D9E
0x180020d94  mov     edx, 373h
0x180020d99  jmp     loc_180020D11
0x180020d9e  bt      ecx, 0Eh
0x180020da2  jnb     short loc_180020DB2
0x180020da4  test    edx, edx
0x180020da6  jnz     short loc_180020DB2
0x180020da8  mov     edx, 382h
0x180020dad  jmp     loc_180020D11
0x180020db2  mov     edx, 120089h
0x180020db7  mov     eax, ebx
0x180020db9  and     eax, edx
0x180020dbb  mov     r15d, ebx
0x180020dbe  cmp     eax, edx
0x180020dc0  jnz     short loc_180020DCE
0x180020dc2  and     r15d, 0FFEDFF76h
0x180020dc9  bts     r15d, 1Fh
0x180020dce  mov     edx, 120116h
0x180020dd3  mov     eax, ebx
0x180020dd5  and     eax, edx
0x180020dd7  cmp     eax, edx
0x180020dd9  jnz     short loc_180020DE9
0x180020ddb  and     r15d, 0FFEDFFE9h
0x180020de2  or      r15d, 40000100h
0x180020de9  mov     edx, 1F01FFh
0x180020dee  mov     [rbp+50h+var_78], r12d
0x180020df2  mov     r9d, 0C0010100h
0x180020df8  mov     [rbp+50h+var_88], rsi
0x180020dfc  mov     eax, ebx
0x180020dfe  mov     r12d, 2
0x180020e04  and     eax, edx
0x180020e06  cmp     eax, edx
0x180020e08  mov     eax, [rbp+50h+arg_40]
0x180020e0e  cmovz   r15d, r9d
0x180020e12  bt      ebx, 1Ch
0x180020e16  cmovb   r15d, r9d
0x180020e1a  test    eax, eax
0x180020e1c  jz      short loc_180020E70
0x180020e1e  sub     eax, 1
0x180020e21  jz      short loc_180020E68
0x180020e23  sub     eax, 1
0x180020e26  jz      short loc_180020E60
0x180020e28  sub     eax, 1
0x180020e2b  jz      short loc_180020E58
0x180020e2d  sub     eax, 1
0x180020e30  jz      short loc_180020E70
0x180020e32  cmp     eax, 1
0x180020e35  jz      short loc_180020E70
0x180020e37  mov     r14d, r8d
0x180020e3a  mov     [rbp+50h+var_80], 33Eh
0x180020e41  lea     rcx, [rbp+50h+var_88]
0x180020e45  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x180020e4a  mov     ecx, [rbp+50h+arg_48]
0x180020e50  xor     r8d, r8d
0x180020e53  mov     ebx, [rbp+50h+var_78]
0x180020e56  jmp     short loc_180020E76
0x180020e58  mov     r14d, 4
0x180020e5e  jmp     short loc_180020E73
0x180020e60  mov     r14d, 1
0x180020e66  jmp     short loc_180020E73
0x180020e68  mov     r14d, 3
0x180020e6e  jmp     short loc_180020E73
0x180020e70  mov     r14d, r12d
0x180020e73  mov     ebx, r8d
0x180020e76  test    ebx, ebx
0x180020e78  js      loc_1800213D6
0x180020e7e  mov     r13d, r8d
0x180020e81  lea     rdx, qword_1801423D0
0x180020e88  mov     rax, r8
0x180020e8b  test    [rdx+rax*4], ecx
0x180020e8e  jz      short loc_180020E95
0x180020e90  or      r13d, [rdx+rax*4+4]
0x180020e95  add     rax, r12
0x180020e98  cmp     rax, 8
0x180020e9c  jnz     short loc_180020E8B
0x180020e9e  mov     rdx, [rbp+50h+arg_18]; struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *
0x180020ea2  lea     rcx, [rsp+150h+var_110]; this
0x180020ea7  mov     [rbp+50h+lpSecurityAttributes], r8
0x180020eab  mov     [rbp+50h+var_A8], 18h
0x180020eb3  mov     [rbp+50h+var_98], 0
0x180020ebb  mov     [rbp+50h+var_A0], r8
0x180020ebf  mov     [rsp+150h+var_108], r8
0x180020ec4  mov     [rsp+150h+var_110], r8
0x180020ec9  mov     [rsp+150h+var_100], r8
0x180020ece  mov     [rsp+150h+var_F0], r8
0x180020ed3  mov     [rsp+150h+var_F8], r8
0x180020ed8  mov     [rsp+150h+lpMem], r8
0x180020edd  mov     [rsp+150h+var_E0], r8
0x180020ee2  mov     [rsp+150h+var_D8], r8d
0x180020ee7  mov     [rbp+50h+var_D0], r8b
0x180020eeb  mov     [rbp+50h+var_C8], 0FFFFFFFFFFFFFFFFh
0x180020ef3  call    ?Initialize@CWin32FullPath@Rtl@Implementation@Isolation@Windows@@QEAAJAEBU_ISOLATED_OBJECT_ATTRIBUTES@245@@Z; Windows::Isolation::Implementation::Rtl::CWin32FullPath::Initialize(Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES const &)
0x180020ef8  mov     ebx, eax
0x180020efa  test    eax, eax
0x180020efc  jns     short loc_180020F0E
0x180020efe  lea     rcx, [rbp+50h+var_D0]
0x180020f02  call    ?Close@?$CWin32HandleBase@VCWin32FileHandle@@@@QEAAXXZ; CWin32HandleBase<CWin32FileHandle>::Close(void)
0x180020f07  xor     edi, edi
0x180020f09  jmp     loc_18002139A
0x180020f0e  mov     rcx, [rbp+50h+arg_18]
0x180020f12  mov     eax, [rcx+18h]
0x180020f15  and     eax, r12d
0x180020f18  jz      short loc_180020F21
0x180020f1a  mov     dword ptr [rbp+50h+var_98], 1
0x180020f21  mov     rcx, [rcx+20h]
0x180020f25  test    rcx, rcx
0x180020f28  jz      short loc_180020F30
0x180020f2a  mov     [rbp+50h+var_A0], rcx
0x180020f2e  jmp     short loc_180020F34
0x180020f30  test    eax, eax
0x180020f32  jz      short loc_180020F3C
0x180020f34  lea     rax, [rbp+50h+var_A8]
0x180020f38  mov     [rbp+50h+lpSecurityAttributes], rax
0x180020f3c  and     r15d, 0C0010100h
0x180020f43  cmp     byte ptr [rbp+50h+arg_0], 0
0x180020f47  jz      loc_1800211A4
0x180020f4d  cmp     r14d, r12d
0x180020f50  jnz     short loc_180020F69
0x180020f52  mov     ebx, 0C000042Ch
0x180020f57  mov     edx, 40Eh; char *
0x180020f5c  mov     r8d, ebx; int
0x180020f5f  mov     rcx, rsi; this
0x180020f62  call    ?ReportNtErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportNtErrorOrigination(char const *,int,long)
0x180020f67  jmp     short loc_180020EFE
0x180020f69  lea     rdx, [rsp+150h+var_110]
0x180020f6e  lea     rcx, [rbp+50h+var_70]
0x180020f72  call    ?GetFileAttributes@Rtl@Implementation@Isolation@Windows@@YA?AU_WIN32_FUNCTION_RETURN_STATUS@@AEBVCWin32FullPath@1234@@Z; Windows::Isolation::Implementation::Rtl::GetFileAttributes(Windows::Isolation::Implementation::Rtl::CWin32FullPath const &)
0x180020f77  mov     ecx, [rax+8]
0x180020f7a  cmp     ecx, 0FFFFFFFFh
0x180020f7d  jnz     loc_1800210BA
0x180020f83  cmp     r14d, 1
0x180020f87  jz      short loc_180020FBA
0x180020f89  cmp     r14d, 4
0x180020f8d  jz      short loc_180020FBA
0x180020f8f  mov     ecx, [rax]; unsigned int
0x180020f91  mov     rdx, rdi; struct _RTL_ALTERNATE_STATUS *
0x180020f94  call    ?isowin32private_Win32ErrorAltStatusHelper@@YAJKPEAU_RTL_ALTERNATE_STATUS@@@Z; isowin32private_Win32ErrorAltStatusHelper(ulong,_RTL_ALTERNATE_STATUS *)
0x180020f99  xor     edi, edi
0x180020f9b  mov     ebx, eax
0x180020f9d  test    eax, eax
0x180020f9f  jns     loc_18002138F
0x180020fa5  mov     edx, 41Bh; char *
0x180020faa  mov     r8d, eax; int
0x180020fad  mov     rcx, rsi; this
0x180020fb0  call    ?ReportNtErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportNtErrorOrigination(char const *,int,long)
0x180020fb5  jmp     loc_180021391
0x180020fba  mov     rbx, [rbp+50h+lpSecurityAttributes]
0x180020fbe  xor     r14d, r14d
0x180020fc1  cmp     [rsp+150h+var_D8], 1
0x180020fc6  jnz     short loc_180020FFA
0x180020fc8  mov     rcx, [rsp+150h+var_E0]
0x180020fcd  test    rcx, rcx
0x180020fd0  jnz     short loc_180020FEB
0x180020fd2  lea     edx, [rcx+1]; dwExceptionFlags
0x180020fd5  xor     r9d, r9d; lpArguments
0x180020fd8  mov     ecx, 0C00000E5h; dwExceptionCode
0x180020fdd  xor     r8d, r8d; nNumberOfArguments
0x180020fe0  call    cs:__imp_RaiseException
0x180020fe6  mov     rcx, [rsp+150h+var_E0]
0x180020feb  mov     rcx, [rcx+10h]; lpPathName
0x180020fef  mov     rdx, rbx; lpSecurityAttributes
0x180020ff2  call    cs:__imp_CreateDirectoryA
0x180020ff8  jmp     short loc_180021032
0x180020ffa  cmp     [rsp+150h+var_D8], r12d
0x180020fff  jnz     short loc_18002100B
0x180021001  mov     rcx, [rsp+150h+var_E0]
0x180021006  test    rcx, rcx
0x180021009  jnz     short loc_180021025
0x18002100b  xor     r9d, r9d; lpArguments
0x18002100e  xor     r8d, r8d; nNumberOfArguments
0x180021011  mov     ecx, 0C00000E5h; dwExceptionCode
0x180021016  lea     edx, [r9+1]; dwExceptionFlags
0x18002101a  call    cs:__imp_RaiseException
0x180021020  mov     rcx, [rsp+150h+var_E0]
0x180021025  mov     rcx, [rcx+10h]; lpPathName
0x180021029  mov     rdx, rbx; lpSecurityAttributes
0x18002102c  call    cs:__imp_CreateDirectoryW
0x180021032  mov     ebx, eax
0x180021034  mov     eax, r14d
0x180021037  test    ebx, ebx
0x180021039  jnz     loc_18002125D
0x18002103f  call    GetLastError_0
0x180021044  test    ebx, ebx
0x180021046  jnz     loc_18002125D
0x18002104c  mov     rdx, rdi; struct _RTL_ALTERNATE_STATUS *
0x18002104f  mov     ecx, eax; unsigned int
0x180021051  call    ?isowin32private_Win32ErrorAltStatusHelper@@YAJKPEAU_RTL_ALTERNATE_STATUS@@@Z; isowin32private_Win32ErrorAltStatusHelper(ulong,_RTL_ALTERNATE_STATUS *)
0x180021056  mov     ebx, eax
0x180021058  test    eax, eax
0x18002105a  jns     short loc_1800210B5
0x18002105c  mov     r8d, eax; int
0x18002105f  mov     edx, 427h; char *
0x180021064  mov     rcx, rsi; this
0x180021067  call    ?ReportNtErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportNtErrorOrigination(char const *,int,long)
0x18002106c  lea     rcx, [rbp+50h+var_D0]
  ... truncated ...
```
