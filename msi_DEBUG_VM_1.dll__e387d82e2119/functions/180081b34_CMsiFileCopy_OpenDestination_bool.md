# CMsiFileCopy::OpenDestination(bool)

- ea: `0x180081b34`
- end: `0x180082559`
- name: `?OpenDestination@CMsiFileCopy@@IEAAPEAVIMsiRecord@@_N@Z`
- size: `2597`
- prototype: `struct IMsiRecord *__fastcall(CMsiFileCopy *__hidden this, bool)`
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18007fb70`
- `0x180081b34`

## callees

- `0x18000a150`
- `0x180025904`
- `0x180025a18`
- `0x180026ffc`
- `0x18005e548`
- `0x180061334`
- `0x1800620e4`
- `0x180066074`
- `0x180068680`
- `0x180071494`
- `0x18007cccc`
- `0x18007f42c`
- `0x18007fa28`
- `0x180080cd0`
- `0x180081b34`
- `0x180083178`
- `0x1800833ec`
- `0x1800cb9d8`
- `0x180123598`
- `0x18013a830`
- `0x18014148c`
- `0x18014e4d4`
- `0x180203600`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!IsValidSecurityDescriptor` at `0x180081f5d`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x180081f66`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x180081f5d`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x180081f66`
- `KERNEL32!CloseHandle` at `0x18008208f`
- `KERNEL32!CloseHandle` at `0x1800821d2`
- `KERNEL32!CloseHandle` at `0x180082262`
- `KERNEL32!CloseHandle` at `0x1800822df`
- `KERNEL32!CloseHandle` at `0x18008208f`
- `KERNEL32!CloseHandle` at `0x1800821d2`
- `KERNEL32!CloseHandle` at `0x180082262`
- `KERNEL32!CloseHandle` at `0x1800822df`
- `KERNEL32!GetLastError` at `0x18008201e`
- `KERNEL32!GetLastError` at `0x1800820b1`
- `KERNEL32!GetLastError` at `0x180082168`
- `KERNEL32!GetLastError` at `0x180082282`
- `KERNEL32!GetLastError` at `0x18008201e`
- `KERNEL32!GetLastError` at `0x1800820b1`
- `KERNEL32!GetLastError` at `0x180082168`
- `KERNEL32!GetLastError` at `0x180082282`
- `KERNEL32!SetLastError` at `0x18008209f`
- `KERNEL32!SetLastError` at `0x1800821e2`
- `KERNEL32!SetLastError` at `0x180082275`
- `KERNEL32!SetLastError` at `0x18008209f`
- `KERNEL32!SetLastError` at `0x1800821e2`
- `KERNEL32!SetLastError` at `0x180082275`
- `KERNEL32!CreateFileW` at `0x180082131`
- `KERNEL32!CreateFileW` at `0x180082131`
- `KERNEL32!GetFileType` at `0x1800821fb`
- `KERNEL32!GetFileType` at `0x1800821fb`
- `KERNEL32!GetFileSize` at `0x1800822b3`
- `KERNEL32!GetFileSize` at `0x1800822b3`

## string_xrefs

- `0x180082227`: `Error: This is not a valid file, hence failing to create: %s`
- `0x180082059`: `Error: This file path is updated, hence failing to create: %s`
- `0x180082197`: `Error: This file path is updated, hence failing to create: %s`
- `0x180081cb0`: `Using source file security for destination.`
- `0x180081e3a`: `File will have security applied from OpCode.`

## pseudocode

```c
struct IMsiRecord *__fastcall CMsiFileCopy::OpenDestination(CMsiFileCopy *this, char a2)
{
  char v4; // r12
  __int16 v5; // r13
  struct IMsiRecord *v6; // rbx
  int v7; // ebx
  __int64 v8; // rdi
  __int64 v9; // r15
  char v10; // bl
  const WCHAR *v11; // rax
  bool ImpersonationFromPath; // al
  __int64 v13; // rcx
  const WCHAR *v14; // rax
  const unsigned __int16 *v15; // rax
  DWORD v16; // r13d
  const WCHAR *v17; // rax
  const unsigned __int16 *v18; // rax
  unsigned int v19; // esi
  char v20; // bl
  __int64 v21; // rcx
  __int64 v22; // rbx
  int v23; // eax
  unsigned __int64 v24; // r15
  void *v25; // r15
  struct IMsiRecord *v26; // rsi
  const WCHAR *v28; // rax
  __int64 v29; // rax
  void *v30; // rcx
  const unsigned __int16 *v31; // rax
  const WCHAR *v32; // rax
  HANDLE FileW; // rax
  const unsigned __int16 *v34; // rax
  const unsigned __int16 *v35; // rax
  LONG FileSize; // eax
  __int64 v37; // rcx
  const WCHAR *v38; // rax
  bool v39; // cl
  unsigned int FileAttributes; // ebx
  const unsigned __int16 *v41; // rax
  int v42; // ecx
  struct IMsiRecord *v43; // rax
  const unsigned __int16 *v44; // rax
  __int64 v45; // rax
  __int64 v46; // rbx
  __int64 v47; // r15
  __int64 v48; // rcx
  __int64 (__fastcall *v49)(__int64, _QWORD, __int64, BOOL, _DWORD, char *, _QWORD); // r12
  BOOL v50; // edi
  __int64 v51; // rax
  int v52; // eax
  CMsiCustomActionManager *v53; // rsi
  BOOL v54; // edi
  const unsigned __int16 *v55; // rax
  int v56; // edi
  __int64 v57; // rax
  const unsigned __int16 *v58; // rax
  struct IMsiRecord *v59; // rdi
  struct _FILETIME *dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  unsigned int v61; // [rsp+50h] [rbp-B0h]
  void *v62; // [rsp+58h] [rbp-A8h]
  unsigned int LastError; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v64; // [rsp+68h] [rbp-98h] BYREF
  __int64 v65; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v66[2]; // [rsp+78h] [rbp-88h] BYREF
  void *v67; // [rsp+80h] [rbp-80h]
  int v68; // [rsp+88h] [rbp-78h]
  int v69; // [rsp+8Ch] [rbp-74h]
  void *v70; // [rsp+90h] [rbp-70h] BYREF
  int v71; // [rsp+98h] [rbp-68h]
  int v72; // [rsp+9Ch] [rbp-64h]
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+B0h] [rbp-50h]
  int v74; // [rsp+B8h] [rbp-48h]
  _BYTE v75[512]; // [rsp+C0h] [rbp-40h] BYREF

  v4 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 4) + 56LL))(*((_QWORD *)this + 4), 4);
  if ( !*((_QWORD *)this + 3) )
  {
    v45 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 4) + 72LL))(*((_QWORD *)this + 4), 3);
    v46 = v45;
    if ( *((_BYTE *)this + 121) )
    {
      v53 = (CMsiCustomActionManager *)*((_QWORD *)this + 16);
      v54 = *((_BYTE *)this + 120) != 0;
      v55 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 80LL))(v45);
      v52 = CMsiCustomActionManager::URTCreateAssemblyFileStream(v53, v55, v54);
    }
    else
    {
      v47 = *((_QWORD *)this + 12);
      v48 = *((_QWORD *)this + 13);
      v49 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, BOOL, _DWORD, char *, _QWORD))(*(_QWORD *)v47 + 24LL);
      if ( v48 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
      *((_QWORD *)this + 13) = 0;
      v50 = *((_BYTE *)this + 120) != 0;
      v51 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v46 + 80LL))(v46);
      v52 = v49(v47, 0, v51, v50, 0, (char *)this + 104, 0);
    }
    v56 = v52;
    v57 = *(_QWORD *)v46;
    if ( v56 < 0 )
    {
      v58 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(v57 + 80))(v46);
      v59 = PostError(1310, (unsigned __int16)v56, v58);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      return v59;
    }
    (*(void (__fastcall **)(__int64))(v57 + 16))(v46);
    return 0;
  }
  *((_QWORD *)this + 6) = -1;
  v71 = 3072;
  v70 = operator new(0xC00u);
  if ( !v70 )
  {
    v71 = 0;
    v6 = PostError(17);
LABEL_100:
    CTempBuffer<unsigned short *,1>::~CTempBuffer<unsigned short *,1>(&v70);
    return v6;
  }
  v7 = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 72LL))(*((_QWORD *)this + 3));
  v65 = v8;
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 112LL))(v8) & 8;
  if ( v5 < 0 )
  {
    v64 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 14) + 72LL))(*((_QWORD *)this + 14));
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v64 + 112LL))(v64);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v64);
    v11 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 80LL))(*((_QWORD *)this + 9));
    ImpersonationFromPath = GetImpersonationFromPath(v11);
    if ( (v10 & 8) != 0
      && (_DWORD)v9
      && !ImpersonationFromPath
      && (*(unsigned int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 4) + 32LL))(*((_QWORD *)this + 4), 12) )
    {
      v7 = 1;
      CElevate::CElevate((CElevate *)&v64, 1);
      LastError = 0;
      if ( g_dmDiagnosticMode )
        DebugString(
          10,
          0,
          0,
          "Using source file security for destination.",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          v61,
          v62);
      v13 = *((_QWORD *)this + 9);
      v72 = 1;
      v14 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 80LL))(v13);
      if ( !(unsigned __int8)MsiGetFileSecurity(v14, 0xFu) )
      {
        v15 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 80LL))(*((_QWORD *)this + 9));
        v6 = PostError(1326, LastError, v15);
        CElevate::~CElevate((CElevate *)&v64);
LABEL_99:
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v65);
        goto LABEL_100;
      }
      CElevate::~CElevate((CElevate *)&v64);
    }
    else
    {
      v7 = 0;
    }
  }
  v16 = v5 & 7;
  if ( a2
    || (v17 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 80LL))(*((_QWORD *)this + 8)),
        GetImpersonationFromPath(v17))
    || (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 584LL))(*((_QWORD *)this + 3))
    || (v18 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 80LL))(*((_QWORD *)this + 8)),
        IsSubstDrive(v18)) )
  {
    v4 = 1;
    StartImpersonating();
    *((_BYTE *)this + 80) = 1;
  }
  v19 = 0;
  LastError = 0;
  if ( !(_DWORD)v9
    || (*(unsigned int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 4) + 32LL))(*((_QWORD *)this + 4), 12)
    && !v7 )
  {
    if ( *((_BYTE *)this + 80) )
      ++HIDWORD(qword_1803096FC);
    v32 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 80LL))(*((_QWORD *)this + 8));
    FileW = CreateFileW(v32, 0x40000000u, 0, 0, 2u, v16 | 0x100000, 0);
    *((_QWORD *)this + 6) = FileW;
    if ( FileW != (HANDLE)-1LL && !CMsiFileCopy::VerifyDestination(this, v4) )
    {
      LastError = GetLastError();
      v19 = LastError;
      if ( LastError != 1 && g_dmDiagnosticMode )
      {
        v34 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 80LL))(*((_QWORD *)this + 8));
        DebugString(
          9,
          0,
          0,
          L"Error: This file path is updated, hence failing to create: %s",
          v34,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
      CloseHandle(*((HANDLE *)this + 6));
      *((_QWORD *)this + 6) = -1;
      SetLastError(v19);
    }
    v30 = (void *)*((_QWORD *)this + 6);
    if ( v30 != (void *)-1LL && GetFileType(v30) - 2 <= 1 )
    {
      if ( g_dmDiagnosticMode )
      {
        v35 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 80LL))(*((_QWORD *)this + 8));
        DebugString(
          9,
          0,
          0,
          L"Error: This is not a valid file, hence failing to create: %s",
          v35,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
      CloseHandle(*((HANDLE *)this + 6));
      *((_QWORD *)this + 6) = -1;
      SetLastError(0x6Eu);
    }
    if ( *((_QWORD *)this + 6) == -1 )
    {
      v19 = GetLastError();
      LastError = v19;
    }
    if ( *((_BYTE *)this + 80) && HIDWORD(qword_1803096FC) )
      --HIDWORD(qword_1803096FC);
    goto LABEL_75;
  }
  v20 = 0;
  v66[1] = 0;
  v69 = 0;
  memset_0(v75, 0, sizeof(v75));
  v21 = *((_QWORD *)this + 4);
  v74 = 512;
  pSecurityDescriptor = v75;
  if ( (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 32LL))(v21, 12) )
  {
    v25 = v70;
    goto LABEL_40;
  }
  if ( g_dmDiagnosticMode )
    DebugString(
      10,
      0,
      0,
      "File will have security applied from OpCode.",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      v61,
      v62);
  v22 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 4) + 64LL))(*((_QWORD *)this + 4), 12);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 112LL))(v22);
  v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 32LL))(v22);
  v24 = v23;
  LODWORD(v64) = v23;
  if ( v23 <= 512 )
  {
    v25 = pSecurityDescriptor;
LABEL_38:
    (*(void (__fastcall **)(__int64, void *))(*(_QWORD *)v22 + 64LL))(v22, v25);
    IsValidSecurityDescriptor(pSecurityDescriptor);
    IsValidSecurityDescriptor(v25);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v20 = 0;
LABEL_40:
    v66[0] = 24;
    v67 = v25;
    v68 = 0;
    if ( *((_BYTE *)this + 80) )
      ++HIDWORD(qword_1803096FC);
    if ( !(*(unsigned int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 4) + 32LL))(*((_QWORD *)this + 4), 9) )
      v20 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 4) + 56LL))(*((_QWORD *)this + 4), 9);
    v28 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 80LL))(*((_QWORD *)this + 8));
    v29 = MsiCreateFileWithUserAccessCheck(v28, (__int64)v66, v16, v4, v20);
    *((_QWORD *)this + 6) = v29;
    if ( v29 != -1 && !CMsiFileCopy::VerifyDestination(this, v4) )
    {
      LastError = GetLastError();
      v19 = LastError;
      if ( LastError != 1 && g_dmDiagnosticMode )
      {
        v31 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 80LL))(*((_QWORD *)this + 8));
        DebugString(
          9,
          0,
          0,
          L"Error: This file path is updated, hence failing to create: %s",
          v31,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
      CloseHandle(*((HANDLE *)this + 6));
      *((_QWORD *)this + 6) = -1;
      SetLastError(v19);
    }
    if ( *((_QWORD *)this + 6) == -1 )
    {
      v19 = GetLastError();
      LastError = v19;
    }
    if ( *((_BYTE *)this + 80) && HIDWORD(qword_1803096FC) )
      --HIDWORD(qword_1803096FC);
    if ( v74 > 512 )
      operator delete(pSecurityDescriptor);
LABEL_75:
    if ( *((_QWORD *)this + 6) != -1 )
    {
      FileSize = GetFileSize(*((HANDLE *)this + 7), 0);
      LOBYTE(v30) = FileSize - 1;
      if ( (unsigned int)(FileSize - 65537) <= 0xFFFEFFFD )
      {
        if ( !MsiSetFileSize(*((HANDLE *)this + 6), FileSize, &LastError) )
        {
          CloseHandle(*((HANDLE *)this + 6));
          *((_QWORD *)this + 6) = -1;
        }
        v19 = LastError;
      }
    }
    if ( v4 )
      StopImpersonating((bool)v30);
    v37 = *((_QWORD *)this + 6);
    if ( v37 == -1 )
    {
      if ( v19 == 5 )
      {
        if ( v4 )
          StartImpersonating();
        v38 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 80LL))(*((_QWORD *)this + 8));
        FileAttributes = MsiGetFileAttributesEx(v38, 0, 0, 0, dwCreationDisposition, 0);
        if ( v4 )
          StopImpersonating(v39);
        if ( FileAttributes != -1 && (FileAttributes & 0x10) != 0 )
        {
          v41 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 80LL))(*((_QWORD *)this + 8));
          v42 = 1301;
LABEL_91:
          v43 = PostError(v42, v41);
LABEL_98:
          v6 = v43;
          goto LABEL_99;
        }
      }
      else
      {
        if ( v19 == 112 )
        {
          v41 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 80LL))(*((_QWORD *)this + 8));
          v42 = 1307;
          goto LABEL_91;
        }
        if ( v19 == 1 && !v4 )
        {
          v43 = CMsiFileCopy::OpenDestination(this, 1);
          goto LABEL_98;
        }
      }
      v44 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 80LL))(*((_QWORD *)this + 8));
      v43 = PostError(1310, v19, v44);
      goto LABEL_98;
    }
    if ( !(unsigned int)MsiRegisterSysHandle(v37) )
    {
      *((_QWORD *)this + 6) = -1;
      v6 = PostError(17);
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      if ( v71 > 1 )
        operator delete(v70);
      return v6;
    }
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v65);
    CTempBuffer<unsigned short *,1>::~CTempBuffer<unsigned short *,1>(&v70);
    return 0;
  }
  if ( v74 > 512 )
    operator delete(pSecurityDescriptor);
  pSecurityDescriptor = operator new(v24);
  v25 = pSecurityDescriptor;
  v74 = pSecurityDescriptor != 0 ? v64 : 0;
  if ( pSecurityDescriptor )
    goto LABEL_38;
  v26 = PostError(17);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v74 > 512 )
    operator delete(pSecurityDescriptor);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v71 > 1 )
    operator delete(v70);
  return v26;
}

```

## disassembly

```asm
0x180081b34  push    rbp
0x180081b36  push    rbx
0x180081b37  push    rsi
0x180081b38  push    rdi
0x180081b39  push    r12
0x180081b3b  push    r13
0x180081b3d  push    r14
0x180081b3f  push    r15
0x180081b41  lea     rbp, [rsp-1D8h]
0x180081b49  sub     rsp, 2D8h
0x180081b50  mov     rax, cs:__security_cookie
0x180081b57  xor     rax, rsp
0x180081b5a  mov     [rbp+210h+var_50], rax
0x180081b61  mov     r14, rcx
0x180081b64  mov     sil, dl
0x180081b67  mov     rcx, [rcx+20h]
0x180081b6b  mov     edx, 4
0x180081b70  mov     rax, [rcx]
0x180081b73  mov     rax, [rax+38h]
0x180081b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081b7c  xor     r12d, r12d
0x180081b7f  mov     r13d, eax
0x180081b82  cmp     [r14+18h], r12
0x180081b86  jz      loc_18008243B
0x180081b8c  mov     ecx, 0C00h; unsigned __int64
0x180081b91  mov     qword ptr [r14+30h], 0FFFFFFFFFFFFFFFFh
0x180081b99  mov     [rbp+210h+var_278], ecx
0x180081b9c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180081ba1  mov     [rbp+210h+var_280], rax
0x180081ba5  test    rax, rax
0x180081ba8  jnz     short loc_180081BBE
0x180081baa  lea     ecx, [rax+11h]; int
0x180081bad  mov     [rbp+210h+var_278], r12d
0x180081bb1  call    ?PostError@@YAPEAVIMsiRecord@@H@Z; PostError(int)
0x180081bb6  mov     rbx, rax
0x180081bb9  jmp     loc_1800823D1
0x180081bbe  mov     rcx, [r14+18h]
0x180081bc2  mov     ebx, r12d
0x180081bc5  mov     rax, [rcx]
0x180081bc8  mov     rax, [rax+48h]
0x180081bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081bd1  mov     rdi, rax
0x180081bd4  mov     [rsp+310h+var_2A0], rax
0x180081bd9  mov     rcx, rdi
0x180081bdc  mov     rax, [rax]
0x180081bdf  mov     rax, [rax+70h]
0x180081be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081be8  mov     r15d, eax
0x180081beb  and     r15d, 8
0x180081bef  bt      r13d, 0Fh
0x180081bf4  jnb     loc_180081D4A
0x180081bfa  mov     rdx, [r14+70h]
0x180081bfe  mov     rcx, [rdx]
0x180081c01  mov     rax, [rcx+48h]
0x180081c05  mov     rcx, rdx
0x180081c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081c0d  mov     rdx, rax
0x180081c10  mov     [rsp+310h+var_2A8], rax
0x180081c15  mov     rcx, [rax]
0x180081c18  mov     rax, [rcx+70h]
0x180081c1c  mov     rcx, rdx
0x180081c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081c24  lea     rcx, [rsp+310h+var_2A8]
0x180081c29  mov     ebx, eax
0x180081c2b  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x180081c30  mov     rdx, [r14+48h]
0x180081c34  mov     rcx, [rdx]
0x180081c37  mov     rax, [rcx+50h]
0x180081c3b  mov     rcx, rdx
0x180081c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081c43  mov     rcx, rax; lpFileName
0x180081c46  call    ?GetImpersonationFromPath@@YA_NPEBG@Z; GetImpersonationFromPath(ushort const *)
0x180081c4b  bt      ebx, 3
0x180081c4f  jnb     loc_180081D47
0x180081c55  test    r15d, r15d
0x180081c58  jz      loc_180081D47
0x180081c5e  test    al, al
0x180081c60  jnz     loc_180081D47
0x180081c66  mov     rcx, [r14+20h]
0x180081c6a  mov     edx, 0Ch
0x180081c6f  mov     rax, [rcx]
0x180081c72  mov     rax, [rax+20h]
0x180081c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081c7b  test    eax, eax
0x180081c7d  jz      loc_180081D47
0x180081c83  mov     ebx, 1
0x180081c88  lea     rcx, [rsp+310h+var_2A8]; this
0x180081c8d  mov     dl, bl; bool
0x180081c8f  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x180081c94  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180081c9b  mov     [rsp+310h+var_2B0], r12d
0x180081ca0  jz      short loc_180081CDB
0x180081ca2  lea     rax, aNull_0; "(NULL)"
0x180081ca9  xor     edx, edx; unsigned __int16
0x180081cab  mov     [rsp+310h+var_2C8], rax; char *
0x180081cb0  lea     r9, aUsingSourceFil; "Using source file security for destinat"...
0x180081cb7  mov     [rsp+310h+var_2D0], rax; char *
0x180081cbc  lea     ecx, [rbx+9]; int
0x180081cbf  mov     [rsp+310h+var_2D8], rax; char *
0x180081cc4  xor     r8d, r8d; int
0x180081cc7  mov     [rsp+310h+hTemplateFile], rax; char *
0x180081ccc  mov     qword ptr [rsp+310h+dwFlagsAndAttributes], rax; char *
0x180081cd1  mov     qword ptr [rsp+310h+dwCreationDisposition], rax; char *
0x180081cd6  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x180081cdb  mov     rcx, [r14+48h]
0x180081cdf  mov     [rbp+210h+var_274], ebx
0x180081ce2  mov     rax, [rcx]
0x180081ce5  mov     rax, [rax+50h]
0x180081ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081cee  lea     r9, [rsp+310h+var_2B0]
0x180081cf3  mov     edx, 0Fh; RequestedInformation
0x180081cf8  lea     r8, [rbp+210h+var_280]
0x180081cfc  mov     rcx, rax; lpFileName
0x180081cff  call    ?MsiGetFileSecurity@@YA_NPEBGKAEAV?$CTempBufferRef@E@@AEAK@Z; MsiGetFileSecurity(ushort const *,ulong,CTempBufferRef<uchar> &,ulong &)
0x180081d04  test    al, al
0x180081d06  jnz     short loc_180081D3B
0x180081d08  mov     rcx, [r14+48h]
0x180081d0c  mov     rax, [rcx]
0x180081d0f  mov     rax, [rax+50h]
0x180081d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081d18  mov     edx, [rsp+310h+var_2B0]; int
0x180081d1c  mov     r8, rax; unsigned __int16 *
0x180081d1f  mov     ecx, 52Eh; int
0x180081d24  call    ?PostError@@YAPEAVIMsiRecord@@HHPEBG@Z; PostError(int,int,ushort const *)
0x180081d29  lea     rcx, [rsp+310h+var_2A8]; this
0x180081d2e  mov     rbx, rax
0x180081d31  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x180081d36  jmp     loc_1800823C7
0x180081d3b  lea     rcx, [rsp+310h+var_2A8]; this
0x180081d40  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x180081d45  jmp     short loc_180081D4A
0x180081d47  mov     ebx, r12d
0x180081d4a  and     r13d, 7
0x180081d4e  test    sil, sil
0x180081d51  jnz     short loc_180081DA2
0x180081d53  mov     rcx, [r14+40h]
0x180081d57  mov     rax, [rcx]
0x180081d5a  mov     rax, [rax+50h]
0x180081d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081d63  mov     rcx, rax; lpFileName
0x180081d66  call    ?GetImpersonationFromPath@@YA_NPEBG@Z; GetImpersonationFromPath(ushort const *)
0x180081d6b  test    al, al
0x180081d6d  jnz     short loc_180081DA2
0x180081d6f  mov     rcx, [r14+18h]
0x180081d73  mov     rax, [rcx]
0x180081d76  mov     rax, [rax+248h]
0x180081d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081d82  test    al, al
0x180081d84  jnz     short loc_180081DA2
0x180081d86  mov     rcx, [r14+40h]
0x180081d8a  mov     rax, [rcx]
0x180081d8d  mov     rax, [rax+50h]
0x180081d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081d96  mov     rcx, rax; unsigned __int16 *
0x180081d99  call    ?IsSubstDrive@@YA_NPEBG@Z; IsSubstDrive(ushort const *)
0x180081d9e  test    al, al
0x180081da0  jz      short loc_180081DAE
0x180081da2  mov     r12b, 1
0x180081da5  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x180081daa  mov     [r14+50h], r12b
0x180081dae  xor     esi, esi
0x180081db0  mov     [rsp+310h+var_2B0], esi
0x180081db4  test    r15d, r15d
0x180081db7  jz      loc_1800820F0
0x180081dbd  mov     rcx, [r14+20h]
0x180081dc1  lea     edx, [rsi+0Ch]
0x180081dc4  mov     rax, [rcx]
0x180081dc7  mov     rax, [rax+20h]
0x180081dcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081dd0  test    eax, eax
0x180081dd2  jz      short loc_180081DDC
0x180081dd4  test    ebx, ebx
0x180081dd6  jz      loc_1800820F0
0x180081ddc  xor     ebx, ebx
0x180081dde  lea     rcx, [rbp+210h+var_250]; void *
0x180081de2  mov     r15d, 200h
0x180081de8  mov     [rsp+310h+var_294], ebx
0x180081dec  mov     r8d, r15d; Size
0x180081def  mov     [rbp+210h+var_284], ebx
0x180081df2  xor     edx, edx; Val
0x180081df4  call    memset_0
0x180081df9  mov     rcx, [r14+20h]
0x180081dfd  lea     rax, [rbp+210h+var_250]
0x180081e01  mov     [rbp+210h+var_258], r15d
0x180081e05  lea     r15d, [rbx+0Ch]
0x180081e09  mov     [rbp+210h+pSecurityDescriptor], rax
0x180081e0d  mov     edx, r15d
0x180081e10  mov     rax, [rcx]
0x180081e13  mov     rax, [rax+20h]
0x180081e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081e1c  test    eax, eax
0x180081e1e  jnz     loc_180081F7F
0x180081e24  cmp     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x180081e2a  jz      short loc_180081E65
0x180081e2c  lea     rax, aNull_0; "(NULL)"
0x180081e33  xor     edx, edx; unsigned __int16
0x180081e35  mov     [rsp+310h+var_2C8], rax; char *
0x180081e3a  lea     r9, aFileWillHaveSe; "File will have security applied from Op"...
0x180081e41  mov     [rsp+310h+var_2D0], rax; char *
0x180081e46  lea     ecx, [rbx+0Ah]; int
0x180081e49  mov     [rsp+310h+var_2D8], rax; char *
0x180081e4e  xor     r8d, r8d; int
0x180081e51  mov     [rsp+310h+hTemplateFile], rax; char *
0x180081e56  mov     qword ptr [rsp+310h+dwFlagsAndAttributes], rax; char *
0x180081e5b  mov     qword ptr [rsp+310h+dwCreationDisposition], rax; char *
0x180081e60  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x180081e65  mov     rcx, [r14+20h]
0x180081e69  mov     edx, r15d
0x180081e6c  mov     rax, [rcx]
0x180081e6f  mov     rax, [rax+40h]
0x180081e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081e78  mov     rbx, rax
0x180081e7b  mov     rcx, rbx
0x180081e7e  mov     rax, [rax]
0x180081e81  mov     rax, [rax+70h]
0x180081e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081e8a  mov     rax, [rbx]
0x180081e8d  mov     rcx, rbx
0x180081e90  mov     rax, [rax+20h]
0x180081e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081e99  movsxd  r15, eax
0x180081e9c  mov     dword ptr [rsp+310h+var_2A8], r15d
0x180081ea1  cmp     r15d, 200h
0x180081ea8  jle     loc_180081F3E
0x180081eae  cmp     [rbp+210h+var_258], 200h
0x180081eb5  jle     short loc_180081EC0
0x180081eb7  mov     rcx, [rbp+210h+pSecurityDescriptor]; void *
0x180081ebb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180081ec0  mov     rcx, r15; unsigned __int64
0x180081ec3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180081ec8  mov     r8d, dword ptr [rsp+310h+var_2A8]
0x180081ecd  mov     rcx, rax
0x180081ed0  neg     rcx
0x180081ed3  mov     [rbp+210h+pSecurityDescriptor], rax
0x180081ed7  mov     r15, rax
0x180081eda  sbb     edx, edx
0x180081edc  and     edx, r8d
0x180081edf  mov     [rbp+210h+var_258], edx
0x180081ee2  test    rax, rax
0x180081ee5  jnz     short loc_180081F47
0x180081ee7  lea     ecx, [rax+11h]; int
0x180081eea  call    ?PostError@@YAPEAVIMsiRecord@@H@Z; PostError(int)
0x180081eef  mov     rcx, [rbx]
0x180081ef2  mov     rsi, rax
0x180081ef5  mov     rax, [rcx+10h]
0x180081ef9  mov     rcx, rbx
0x180081efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081f01  cmp     [rbp+210h+var_258], 200h
0x180081f08  jle     short loc_180081F13
0x180081f0a  mov     rcx, [rbp+210h+pSecurityDescriptor]; void *
0x180081f0e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180081f13  test    rdi, rdi
0x180081f16  jz      short loc_180081F27
0x180081f18  mov     rax, [rdi]
0x180081f1b  mov     rcx, rdi
0x180081f1e  mov     rax, [rax+10h]
0x180081f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081f27  cmp     [rbp+210h+var_278], 1
0x180081f2b  jle     short loc_180081F36
0x180081f2d  mov     rcx, [rbp+210h+var_280]; void *
0x180081f31  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180081f36  mov     rax, rsi
0x180081f39  jmp     loc_180082536
0x180081f3e  mov     r15, [rbp+210h+pSecurityDescriptor]
0x180081f42  mov     r8d, dword ptr [rsp+310h+var_2A8]
0x180081f47  mov     rax, [rbx]
0x180081f4a  mov     rdx, r15
0x180081f4d  mov     rcx, rbx
0x180081f50  mov     rax, [rax+40h]
0x180081f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081f59  mov     rcx, [rbp+210h+pSecurityDescriptor]; pSecurityDescriptor
0x180081f5d  call    cs:__imp_IsValidSecurityDescriptor
0x180081f63  mov     rcx, r15; pSecurityDescriptor
0x180081f66  call    cs:__imp_IsValidSecurityDescriptor
0x180081f6c  mov     rax, [rbx]
0x180081f6f  mov     rcx, rbx
0x180081f72  mov     rax, [rax+10h]
0x180081f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081f7b  xor     ebx, ebx
0x180081f7d  jmp     short loc_180081F83
0x180081f7f  mov     r15, [rbp+210h+var_280]
0x180081f83  mov     [rsp+310h+var_298], 18h
0x180081f8b  mov     [rbp+210h+var_290], r15
0x180081f8f  mov     [rbp+210h+var_288], ebx
0x180081f92  cmp     [r14+50h], bl
0x180081f96  jz      short loc_180081F9E
0x180081f98  inc     dword ptr cs:qword_1803096FC+4
0x180081f9e  mov     rcx, [r14+20h]
0x180081fa2  mov     r15d, 9
0x180081fa8  mov     edx, r15d
0x180081fab  mov     rax, [rcx]
0x180081fae  mov     rax, [rax+20h]
0x180081fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081fb7  test    eax, eax
0x180081fb9  jnz     short loc_180081FD0
0x180081fbb  mov     rcx, [r14+20h]
0x180081fbf  mov     edx, r15d
0x180081fc2  mov     rax, [rcx]
0x180081fc5  mov     rax, [rax+38h]
0x180081fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
