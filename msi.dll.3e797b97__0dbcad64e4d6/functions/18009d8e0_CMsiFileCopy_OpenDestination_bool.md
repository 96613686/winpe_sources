# CMsiFileCopy::OpenDestination(bool)

- ea: `0x18009d8e0`
- end: `0x18009e34c`
- name: `?OpenDestination@CMsiFileCopy@@IEAAPEAVIMsiRecord@@_N@Z`
- size: `2668`
- prototype: `struct IMsiRecord *__fastcall(CMsiFileCopy *__hidden this, bool)`
- caller_count: `2`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18007de60`
- `0x18009d8e0`

## callees

- `0x180005af8`
- `0x18000c4bc`
- `0x180014528`
- `0x180016154`
- `0x180018ee0`
- `0x180019cc0`
- `0x180027634`
- `0x180056574`
- `0x180067fec`
- `0x18007ad94`
- `0x18007d678`
- `0x18007dd00`
- `0x18007f014`
- `0x180097608`
- `0x18009ca0c`
- `0x18009cdb8`
- `0x18009d06c`
- `0x18009d8e0`
- `0x18009f2d4`
- `0x180128db0`
- `0x18013fa30`
- `0x18014676c`
- `0x180153e68`
- `0x18020c928`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!IsValidSecurityDescriptor` at `0x18009dd09`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18009dd18`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18009dd09`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18009dd18`
- `KERNEL32!CloseHandle` at `0x18009de4d`
- `KERNEL32!CloseHandle` at `0x18009dfa1`
- `KERNEL32!CloseHandle` at `0x18009e043`
- `KERNEL32!CloseHandle` at `0x18009e0cb`
- `KERNEL32!CloseHandle` at `0x18009de4d`
- `KERNEL32!CloseHandle` at `0x18009dfa1`
- `KERNEL32!CloseHandle` at `0x18009e043`
- `KERNEL32!CloseHandle` at `0x18009e0cb`
- `KERNEL32!GetLastError` at `0x18009ddd6`
- `KERNEL32!GetLastError` at `0x18009de7b`
- `KERNEL32!GetLastError` at `0x18009df31`
- `KERNEL32!GetLastError` at `0x18009e06f`
- `KERNEL32!GetLastError` at `0x18009ddd6`
- `KERNEL32!GetLastError` at `0x18009de7b`
- `KERNEL32!GetLastError` at `0x18009df31`
- `KERNEL32!GetLastError` at `0x18009e06f`
- `KERNEL32!SetLastError` at `0x18009de63`
- `KERNEL32!SetLastError` at `0x18009dfb7`
- `KERNEL32!SetLastError` at `0x18009e05c`
- `KERNEL32!SetLastError` at `0x18009de63`
- `KERNEL32!SetLastError` at `0x18009dfb7`
- `KERNEL32!SetLastError` at `0x18009e05c`
- `KERNEL32!CreateFileW` at `0x18009def4`
- `KERNEL32!CreateFileW` at `0x18009def4`
- `KERNEL32!GetFileType` at `0x18009dfd6`
- `KERNEL32!GetFileType` at `0x18009dfd6`
- `KERNEL32!GetFileSize` at `0x18009e099`
- `KERNEL32!GetFileSize` at `0x18009e099`

## string_xrefs

- `0x18009e008`: `Error: This is not a valid file, hence failing to create: %s`
- `0x18009de17`: `Error: This file path is updated, hence failing to create: %s`
- `0x18009df66`: `Error: This file path is updated, hence failing to create: %s`
- `0x18009da5c`: `Using source file security for destination.`
- `0x18009dbe6`: `File will have security applied from OpCode.`

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
LABEL_98:
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
LABEL_97:
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v65);
        goto LABEL_98;
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
      ++HIDWORD(qword_1803136AC);
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
    if ( *((_BYTE *)this + 80) )
      MsiUIMessageContext::EnableTimeout((MsiUIMessageContext *)v30);
    goto LABEL_73;
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
      ++HIDWORD(qword_1803136AC);
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
    if ( *((_BYTE *)this + 80) )
      MsiUIMessageContext::EnableTimeout((MsiUIMessageContext *)v30);
    if ( v74 > 512 )
      operator delete(pSecurityDescriptor);
LABEL_73:
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
LABEL_89:
          v43 = PostError(v42, v41);
LABEL_96:
          v6 = v43;
          goto LABEL_97;
        }
      }
      else
      {
        if ( v19 == 112 )
        {
          v41 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 80LL))(*((_QWORD *)this + 8));
          v42 = 1307;
          goto LABEL_89;
        }
        if ( v19 == 1 && !v4 )
        {
          v43 = CMsiFileCopy::OpenDestination(this, 1);
          goto LABEL_96;
        }
      }
      v44 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 80LL))(*((_QWORD *)this + 8));
      v43 = PostError(1310, v19, v44);
      goto LABEL_96;
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
0x18009d8e0  push    rbp
0x18009d8e2  push    rbx
0x18009d8e3  push    rsi
0x18009d8e4  push    rdi
0x18009d8e5  push    r12
0x18009d8e7  push    r13
0x18009d8e9  push    r14
0x18009d8eb  push    r15
0x18009d8ed  lea     rbp, [rsp-1D8h]
0x18009d8f5  sub     rsp, 2D8h
0x18009d8fc  mov     rax, cs:__security_cookie
0x18009d903  xor     rax, rsp
0x18009d906  mov     [rbp+210h+var_50], rax
0x18009d90d  mov     r14, rcx
0x18009d910  mov     sil, dl
0x18009d913  mov     rcx, [rcx+20h]
0x18009d917  mov     edx, 4
0x18009d91c  mov     rax, [rcx]
0x18009d91f  mov     rax, [rax+38h]
0x18009d923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d928  xor     r12d, r12d
0x18009d92b  mov     r13d, eax
0x18009d92e  cmp     [r14+18h], r12
0x18009d932  jz      loc_18009E22D
0x18009d938  mov     ecx, 0C00h; unsigned __int64
0x18009d93d  mov     qword ptr [r14+30h], 0FFFFFFFFFFFFFFFFh
0x18009d945  mov     [rbp+210h+var_278], ecx
0x18009d948  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009d94d  mov     [rbp+210h+var_280], rax
0x18009d951  test    rax, rax
0x18009d954  jnz     short loc_18009D96A
0x18009d956  lea     ecx, [rax+11h]; int
0x18009d959  mov     [rbp+210h+var_278], r12d
0x18009d95d  call    ?PostError@@YAPEAVIMsiRecord@@H@Z; PostError(int)
0x18009d962  mov     rbx, rax
0x18009d965  jmp     loc_18009E1C3
0x18009d96a  mov     rcx, [r14+18h]
0x18009d96e  mov     ebx, r12d
0x18009d971  mov     rax, [rcx]
0x18009d974  mov     rax, [rax+48h]
0x18009d978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d97d  mov     rdi, rax
0x18009d980  mov     [rsp+310h+var_2A0], rax
0x18009d985  mov     rcx, rdi
0x18009d988  mov     rax, [rax]
0x18009d98b  mov     rax, [rax+70h]
0x18009d98f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d994  mov     r15d, eax
0x18009d997  and     r15d, 8
0x18009d99b  bt      r13d, 0Fh
0x18009d9a0  jnb     loc_18009DAF6
0x18009d9a6  mov     rdx, [r14+70h]
0x18009d9aa  mov     rcx, [rdx]
0x18009d9ad  mov     rax, [rcx+48h]
0x18009d9b1  mov     rcx, rdx
0x18009d9b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d9b9  mov     rdx, rax
0x18009d9bc  mov     [rsp+310h+var_2A8], rax
0x18009d9c1  mov     rcx, [rax]
0x18009d9c4  mov     rax, [rcx+70h]
0x18009d9c8  mov     rcx, rdx
0x18009d9cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d9d0  lea     rcx, [rsp+310h+var_2A8]
0x18009d9d5  mov     ebx, eax
0x18009d9d7  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x18009d9dc  mov     rdx, [r14+48h]
0x18009d9e0  mov     rcx, [rdx]
0x18009d9e3  mov     rax, [rcx+50h]
0x18009d9e7  mov     rcx, rdx
0x18009d9ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d9ef  mov     rcx, rax; lpFileName
0x18009d9f2  call    ?GetImpersonationFromPath@@YA_NPEBG@Z; GetImpersonationFromPath(ushort const *)
0x18009d9f7  bt      ebx, 3
0x18009d9fb  jnb     loc_18009DAF3
0x18009da01  test    r15d, r15d
0x18009da04  jz      loc_18009DAF3
0x18009da0a  test    al, al
0x18009da0c  jnz     loc_18009DAF3
0x18009da12  mov     rcx, [r14+20h]
0x18009da16  mov     edx, 0Ch
0x18009da1b  mov     rax, [rcx]
0x18009da1e  mov     rax, [rax+20h]
0x18009da22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009da27  test    eax, eax
0x18009da29  jz      loc_18009DAF3
0x18009da2f  mov     ebx, 1
0x18009da34  lea     rcx, [rsp+310h+var_2A8]; this
0x18009da39  mov     dl, bl; bool
0x18009da3b  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x18009da40  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x18009da47  mov     [rsp+310h+var_2B0], r12d
0x18009da4c  jz      short loc_18009DA87
0x18009da4e  lea     rax, aNull_0; "(NULL)"
0x18009da55  xor     edx, edx; unsigned __int16
0x18009da57  mov     [rsp+310h+var_2C8], rax; char *
0x18009da5c  lea     r9, aUsingSourceFil; "Using source file security for destinat"...
0x18009da63  mov     [rsp+310h+var_2D0], rax; char *
0x18009da68  lea     ecx, [rbx+9]; int
0x18009da6b  mov     [rsp+310h+var_2D8], rax; char *
0x18009da70  xor     r8d, r8d; int
0x18009da73  mov     [rsp+310h+hTemplateFile], rax; char *
0x18009da78  mov     qword ptr [rsp+310h+dwFlagsAndAttributes], rax; char *
0x18009da7d  mov     qword ptr [rsp+310h+dwCreationDisposition], rax; char *
0x18009da82  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x18009da87  mov     rcx, [r14+48h]
0x18009da8b  mov     [rbp+210h+var_274], ebx
0x18009da8e  mov     rax, [rcx]
0x18009da91  mov     rax, [rax+50h]
0x18009da95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009da9a  lea     r9, [rsp+310h+var_2B0]
0x18009da9f  mov     edx, 0Fh; RequestedInformation
0x18009daa4  lea     r8, [rbp+210h+var_280]
0x18009daa8  mov     rcx, rax; lpFileName
0x18009daab  call    ?MsiGetFileSecurity@@YA_NPEBGKAEAV?$CTempBufferRef@E@@AEAK@Z; MsiGetFileSecurity(ushort const *,ulong,CTempBufferRef<uchar> &,ulong &)
0x18009dab0  test    al, al
0x18009dab2  jnz     short loc_18009DAE7
0x18009dab4  mov     rcx, [r14+48h]
0x18009dab8  mov     rax, [rcx]
0x18009dabb  mov     rax, [rax+50h]
0x18009dabf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dac4  mov     edx, [rsp+310h+var_2B0]; int
0x18009dac8  mov     r8, rax; unsigned __int16 *
0x18009dacb  mov     ecx, 52Eh; int
0x18009dad0  call    ?PostError@@YAPEAVIMsiRecord@@HHPEBG@Z; PostError(int,int,ushort const *)
0x18009dad5  lea     rcx, [rsp+310h+var_2A8]; this
0x18009dada  mov     rbx, rax
0x18009dadd  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x18009dae2  jmp     loc_18009E1B9
0x18009dae7  lea     rcx, [rsp+310h+var_2A8]; this
0x18009daec  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x18009daf1  jmp     short loc_18009DAF6
0x18009daf3  mov     ebx, r12d
0x18009daf6  and     r13d, 7
0x18009dafa  test    sil, sil
0x18009dafd  jnz     short loc_18009DB4E
0x18009daff  mov     rcx, [r14+40h]
0x18009db03  mov     rax, [rcx]
0x18009db06  mov     rax, [rax+50h]
0x18009db0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009db0f  mov     rcx, rax; lpFileName
0x18009db12  call    ?GetImpersonationFromPath@@YA_NPEBG@Z; GetImpersonationFromPath(ushort const *)
0x18009db17  test    al, al
0x18009db19  jnz     short loc_18009DB4E
0x18009db1b  mov     rcx, [r14+18h]
0x18009db1f  mov     rax, [rcx]
0x18009db22  mov     rax, [rax+248h]
0x18009db29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009db2e  test    al, al
0x18009db30  jnz     short loc_18009DB4E
0x18009db32  mov     rcx, [r14+40h]
0x18009db36  mov     rax, [rcx]
0x18009db39  mov     rax, [rax+50h]
0x18009db3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009db42  mov     rcx, rax; unsigned __int16 *
0x18009db45  call    ?IsSubstDrive@@YA_NPEBG@Z; IsSubstDrive(ushort const *)
0x18009db4a  test    al, al
0x18009db4c  jz      short loc_18009DB5A
0x18009db4e  mov     r12b, 1
0x18009db51  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x18009db56  mov     [r14+50h], r12b
0x18009db5a  xor     esi, esi
0x18009db5c  mov     [rsp+310h+var_2B0], esi
0x18009db60  test    r15d, r15d
0x18009db63  jz      loc_18009DEB3
0x18009db69  mov     rcx, [r14+20h]
0x18009db6d  lea     edx, [rsi+0Ch]
0x18009db70  mov     rax, [rcx]
0x18009db73  mov     rax, [rax+20h]
0x18009db77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009db7c  test    eax, eax
0x18009db7e  jz      short loc_18009DB88
0x18009db80  test    ebx, ebx
0x18009db82  jz      loc_18009DEB3
0x18009db88  xor     ebx, ebx
0x18009db8a  lea     rcx, [rbp+210h+var_250]; void *
0x18009db8e  mov     r15d, 200h
0x18009db94  mov     [rsp+310h+var_294], ebx
0x18009db98  mov     r8d, r15d; Size
0x18009db9b  mov     [rbp+210h+var_284], ebx
0x18009db9e  xor     edx, edx; Val
0x18009dba0  call    memset_0
0x18009dba5  mov     rcx, [r14+20h]
0x18009dba9  lea     rax, [rbp+210h+var_250]
0x18009dbad  mov     [rbp+210h+var_258], r15d
0x18009dbb1  lea     r15d, [rbx+0Ch]
0x18009dbb5  mov     [rbp+210h+pSecurityDescriptor], rax
0x18009dbb9  mov     edx, r15d
0x18009dbbc  mov     rax, [rcx]
0x18009dbbf  mov     rax, [rax+20h]
0x18009dbc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dbc8  test    eax, eax
0x18009dbca  jnz     loc_18009DD37
0x18009dbd0  cmp     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x18009dbd6  jz      short loc_18009DC11
0x18009dbd8  lea     rax, aNull_0; "(NULL)"
0x18009dbdf  xor     edx, edx; unsigned __int16
0x18009dbe1  mov     [rsp+310h+var_2C8], rax; char *
0x18009dbe6  lea     r9, aFileWillHaveSe; "File will have security applied from Op"...
0x18009dbed  mov     [rsp+310h+var_2D0], rax; char *
0x18009dbf2  lea     ecx, [rbx+0Ah]; int
0x18009dbf5  mov     [rsp+310h+var_2D8], rax; char *
0x18009dbfa  xor     r8d, r8d; int
0x18009dbfd  mov     [rsp+310h+hTemplateFile], rax; char *
0x18009dc02  mov     qword ptr [rsp+310h+dwFlagsAndAttributes], rax; char *
0x18009dc07  mov     qword ptr [rsp+310h+dwCreationDisposition], rax; char *
0x18009dc0c  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x18009dc11  mov     rcx, [r14+20h]
0x18009dc15  mov     edx, r15d
0x18009dc18  mov     rax, [rcx]
0x18009dc1b  mov     rax, [rax+40h]
0x18009dc1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dc24  mov     rbx, rax
0x18009dc27  mov     rcx, rbx
0x18009dc2a  mov     rax, [rax]
0x18009dc2d  mov     rax, [rax+70h]
0x18009dc31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dc36  mov     rax, [rbx]
0x18009dc39  mov     rcx, rbx
0x18009dc3c  mov     rax, [rax+20h]
0x18009dc40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dc45  movsxd  r15, eax
0x18009dc48  mov     dword ptr [rsp+310h+var_2A8], r15d
0x18009dc4d  cmp     r15d, 200h
0x18009dc54  jle     loc_18009DCEA
0x18009dc5a  cmp     [rbp+210h+var_258], 200h
0x18009dc61  jle     short loc_18009DC6C
0x18009dc63  mov     rcx, [rbp+210h+pSecurityDescriptor]; void *
0x18009dc67  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009dc6c  mov     rcx, r15; unsigned __int64
0x18009dc6f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009dc74  mov     r8d, dword ptr [rsp+310h+var_2A8]
0x18009dc79  mov     rcx, rax
0x18009dc7c  neg     rcx
0x18009dc7f  mov     [rbp+210h+pSecurityDescriptor], rax
0x18009dc83  mov     r15, rax
0x18009dc86  sbb     edx, edx
0x18009dc88  and     edx, r8d
0x18009dc8b  mov     [rbp+210h+var_258], edx
0x18009dc8e  test    rax, rax
0x18009dc91  jnz     short loc_18009DCF3
0x18009dc93  lea     ecx, [rax+11h]; int
0x18009dc96  call    ?PostError@@YAPEAVIMsiRecord@@H@Z; PostError(int)
0x18009dc9b  mov     rcx, [rbx]
0x18009dc9e  mov     rsi, rax
0x18009dca1  mov     rax, [rcx+10h]
0x18009dca5  mov     rcx, rbx
0x18009dca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dcad  cmp     [rbp+210h+var_258], 200h
0x18009dcb4  jle     short loc_18009DCBF
0x18009dcb6  mov     rcx, [rbp+210h+pSecurityDescriptor]; void *
0x18009dcba  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009dcbf  test    rdi, rdi
0x18009dcc2  jz      short loc_18009DCD3
0x18009dcc4  mov     rax, [rdi]
0x18009dcc7  mov     rcx, rdi
0x18009dcca  mov     rax, [rax+10h]
0x18009dcce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dcd3  cmp     [rbp+210h+var_278], 1
0x18009dcd7  jle     short loc_18009DCE2
0x18009dcd9  mov     rcx, [rbp+210h+var_280]; void *
0x18009dcdd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009dce2  mov     rax, rsi
0x18009dce5  jmp     loc_18009E328
0x18009dcea  mov     r15, [rbp+210h+pSecurityDescriptor]
0x18009dcee  mov     r8d, dword ptr [rsp+310h+var_2A8]
0x18009dcf3  mov     rax, [rbx]
0x18009dcf6  mov     rdx, r15
0x18009dcf9  mov     rcx, rbx
0x18009dcfc  mov     rax, [rax+40h]
0x18009dd00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dd05  mov     rcx, [rbp+210h+pSecurityDescriptor]; pSecurityDescriptor
0x18009dd09  call    cs:__imp_IsValidSecurityDescriptor
0x18009dd10  nop     dword ptr [rax+rax+00h]
0x18009dd15  mov     rcx, r15; pSecurityDescriptor
0x18009dd18  call    cs:__imp_IsValidSecurityDescriptor
0x18009dd1f  nop     dword ptr [rax+rax+00h]
0x18009dd24  mov     rax, [rbx]
0x18009dd27  mov     rcx, rbx
0x18009dd2a  mov     rax, [rax+10h]
0x18009dd2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dd33  xor     ebx, ebx
0x18009dd35  jmp     short loc_18009DD3B
0x18009dd37  mov     r15, [rbp+210h+var_280]
0x18009dd3b  mov     [rsp+310h+var_298], 18h
0x18009dd43  mov     [rbp+210h+var_290], r15
0x18009dd47  mov     [rbp+210h+var_288], ebx
0x18009dd4a  cmp     [r14+50h], bl
0x18009dd4e  jz      short loc_18009DD56
0x18009dd50  inc     dword ptr cs:qword_1803136AC+4
0x18009dd56  mov     rcx, [r14+20h]
0x18009dd5a  mov     r15d, 9
0x18009dd60  mov     edx, r15d
0x18009dd63  mov     rax, [rcx]
0x18009dd66  mov     rax, [rax+20h]
0x18009dd6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dd6f  test    eax, eax
0x18009dd71  jnz     short loc_18009DD88
0x18009dd73  mov     rcx, [r14+20h]
0x18009dd77  mov     edx, r15d
0x18009dd7a  mov     rax, [rcx]
  ... truncated ...
```
