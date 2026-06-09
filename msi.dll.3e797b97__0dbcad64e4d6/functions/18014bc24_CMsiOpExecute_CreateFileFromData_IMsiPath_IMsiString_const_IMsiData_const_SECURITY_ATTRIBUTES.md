# CMsiOpExecute::CreateFileFromData(IMsiPath &,IMsiString const &,IMsiData const *,_SECURITY_ATTRIBUTES *)

- ea: `0x18014bc24`
- end: `0x18014c2b7`
- name: `?CreateFileFromData@CMsiOpExecute@@IEAA?AW4iesEnum@@AEAVIMsiPath@@AEBVIMsiString@@PEBVIMsiData@@PEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `1683`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18014b9bc`
- `0x1801f9b74`

## callees

- `0x180003b10`
- `0x180005af8`
- `0x18000c4bc`
- `0x180013fe4`
- `0x180014528`
- `0x18002e870`
- `0x180038e70`
- `0x180056574`
- `0x180067fec`
- `0x18007ad94`
- `0x18007adb4`
- `0x18007b9e8`
- `0x18007f4c8`
- `0x18009cdb8`
- `0x18009d06c`
- `0x1800ada5c`
- `0x18011c9cc`
- `0x18013fa30`
- `0x180149a1c`
- `0x18014bc24`
- `0x18015a7c0`
- `0x18017381c`
- `0x1801e7418`
- `0x180220328`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!SetFileSecurityW` at `0x18014bfb8`
- `ADVAPI32!SetFileSecurityW` at `0x18014bfb8`
- `KERNEL32!SetFileInformationByHandle` at `0x18014c0af`
- `KERNEL32!SetFileInformationByHandle` at `0x18014c193`
- `KERNEL32!SetFileInformationByHandle` at `0x18014c0af`
- `KERNEL32!SetFileInformationByHandle` at `0x18014c193`
- `KERNEL32!CloseHandle` at `0x18014bef6`
- `KERNEL32!CloseHandle` at `0x18014c006`
- `KERNEL32!CloseHandle` at `0x18014c0be`
- `KERNEL32!CloseHandle` at `0x18014c1a2`
- `KERNEL32!CloseHandle` at `0x18014c1e1`
- `KERNEL32!CloseHandle` at `0x18014c25a`
- `KERNEL32!CloseHandle` at `0x18014bef6`
- `KERNEL32!CloseHandle` at `0x18014c006`
- `KERNEL32!CloseHandle` at `0x18014c0be`
- `KERNEL32!CloseHandle` at `0x18014c1a2`
- `KERNEL32!CloseHandle` at `0x18014c1e1`
- `KERNEL32!CloseHandle` at `0x18014c25a`
- `KERNEL32!GetLastError` at `0x18014bf15`
- `KERNEL32!GetLastError` at `0x18014bfdb`
- `KERNEL32!GetLastError` at `0x18014bf15`
- `KERNEL32!GetLastError` at `0x18014bfdb`
- `KERNEL32!SetLastError` at `0x18014bf09`
- `KERNEL32!SetLastError` at `0x18014bf09`
- `KERNEL32!CreateFileW` at `0x18014be67`
- `KERNEL32!CreateFileW` at `0x18014be67`
- `KERNEL32!GetFileType` at `0x18014be83`
- `KERNEL32!GetFileType` at `0x18014be83`
- `KERNEL32!WriteFile` at `0x18014c166`
- `KERNEL32!WriteFile` at `0x18014c166`

## string_xrefs

- `0x18014bec1`: `Error: This is not a valid file, hence failing to create: %s`

## pseudocode

```c
__int64 __fastcall CMsiOpExecute::CreateFileFromData(
        __int64 a1,
        __int64 *a2,
        __int64 *a3,
        unsigned int (__fastcall ***a4)(_QWORD, GUID *, __int64),
        struct _SECURITY_ATTRIBUTES *a5)
{
  char v5; // si
  __int64 v7; // rax
  __int64 (__fastcall *v11)(__int64 *, __int64, void **); // rbx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 (__fastcall *v16)(__int64 *, __int64, _QWORD); // rbx
  __int64 v17; // rax
  __int64 v18; // rax
  int v19; // r13d
  char v20; // r12
  const WCHAR *v21; // rax
  LPSECURITY_ATTRIBUTES v22; // rdi
  DWORD v23; // ebx
  HANDLE FileW; // rax
  __int64 v25; // rsi
  const unsigned __int16 *v26; // rax
  bool v27; // cl
  unsigned int v28; // r14d
  unsigned int SecurityInformation; // eax
  __int64 v30; // rdx
  SECURITY_INFORMATION v31; // edi
  __int64 v32; // rdx
  void *lpSecurityDescriptor; // rbx
  const WCHAR *v34; // rax
  __int64 v35; // rbx
  DWORD v36; // eax
  __int64 v37; // rdx
  unsigned int v38; // eax
  unsigned int v39; // ebx
  __int64 v40; // rax
  LPCVOID v41; // rdx
  unsigned int v42; // edi
  DWORD v43; // eax
  DWORD v44; // ebx
  __int64 v45; // rax
  __int64 v47; // rax
  char FileInformation[8]; // [rsp+60h] [rbp-61h] BYREF
  void *v49; // [rsp+68h] [rbp-59h] BYREF
  __int64 v50; // [rsp+70h] [rbp-51h] BYREF
  __int64 v51; // [rsp+78h] [rbp-49h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp-41h] BYREF
  unsigned int LastError; // [rsp+84h] [rbp-3Dh] BYREF
  __int64 v54; // [rsp+88h] [rbp-39h] BYREF
  struct IMsiVolume *v55; // [rsp+90h] [rbp-31h] BYREF
  _BYTE v56[8]; // [rsp+98h] [rbp-29h] BYREF
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+A0h] [rbp-21h]
  LPCVOID lpBuffer; // [rsp+A8h] [rbp-19h] BYREF
  unsigned int v59; // [rsp+B0h] [rbp-11h]

  v5 = 0;
  lpSecurityAttributes = a5;
  NumberOfBytesWritten = 0;
  v7 = *a2;
  v50 = 0;
  v49 = &MsiString::s_NullString;
  v11 = *(__int64 (__fastcall **)(__int64 *, __int64, void **))(v7 + 136);
  (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
  v12 = *a3;
  v49 = &MsiString::s_NullString;
  v13 = (*(__int64 (__fastcall **)(__int64 *))(v12 + 80))(a3);
  v14 = v11(a2, v13, &v49);
  if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v50, v14) )
  {
    CMsiOpExecute::Message(a1, 0x1000000, v50);
LABEL_56:
    (*(void (__fastcall **)(void *))(*(_QWORD *)v49 + 16LL))(v49);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v50);
    return 3;
  }
  v51 = 0;
  v15 = CComPointer<IEnumMsiRecord>::operator=(&v51);
  if ( (**a4)(a4, &IID_IMsiStream, v15) )
  {
    CMsiOpExecute::DispatchError(a1, 0x1000000, 2932, v49);
LABEL_55:
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v51);
    goto LABEL_56;
  }
  v54 = 0;
  if ( (unsigned int)CMsiOpExecute::CreateFolder(a1, a2, 0, 0, 0, 1, 0, 0) != 1 )
  {
LABEL_54:
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v54);
    goto LABEL_55;
  }
  v16 = *(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(*a2 + 400);
  v17 = (*(__int64 (__fastcall **)(__int64 *))(*a3 + 80))(a3);
  v18 = v16(a2, v17, 0);
  if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v50, v18) )
  {
    CMsiOpExecute::Message(a1, 0x1000000, v50);
    goto LABEL_54;
  }
  v19 = RunningAsLocalSystem();
  if ( v19 == -1 )
  {
    v55 = PostError(1501);
    CMsiOpExecute::Message(a1, 0x1000000, v55);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v55);
    goto LABEL_54;
  }
  if ( v19 != 1
    || (v55 = (struct IMsiVolume *)(*(__int64 (__fastcall **)(__int64 *))(*a2 + 72))(a2),
        v5 = 1,
        v20 = 1,
        !FVolumeRequiresImpersonation(v55)) )
  {
    v20 = 0;
  }
  if ( (v5 & 1) != 0 )
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v55);
  if ( v20 )
    StartImpersonating();
  v21 = (const WCHAR *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v49 + 80LL))(v49);
  v22 = lpSecurityAttributes;
  v23 = 2;
  FileW = CreateFileW(v21, 0x40010000u, 1u, lpSecurityAttributes, 2u, 0x100080u, 0);
  v25 = (__int64)FileW;
  if ( FileW != (HANDLE)-1LL && GetFileType(FileW) - 2 <= 1 )
  {
    if ( g_dmDiagnosticMode )
    {
      v26 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v49 + 80LL))(v49);
      DebugString(
        9,
        0,
        0,
        L"Error: This is not a valid file, hence failing to create: %s",
        v26,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    CloseHandle((HANDLE)v25);
    v25 = -1;
    SetLastError(0x6Eu);
  }
  LastError = GetLastError();
  v28 = LastError;
  if ( LastError == 183 )
  {
    v28 = 0;
    LastError = 0;
    if ( v22 )
    {
      if ( v22->lpSecurityDescriptor && v19 == 1 )
      {
        CElevate::CElevate((CElevate *)&v55, 1);
        SecurityInformation = GetSecurityInformation(v22->lpSecurityDescriptor);
        LOBYTE(v30) = 1;
        v31 = SecurityInformation;
        if ( (unsigned __int8)RefCountedTokenPrivilegesCore(1, v30) )
          v23 = 1;
        NumberOfBytesWritten = v23;
        CRefCountedTokenPrivileges::CRefCountedTokenPrivileges(v56, v32, (v31 >> 3) & 1);
        lpSecurityDescriptor = lpSecurityAttributes->lpSecurityDescriptor;
        v34 = (const WCHAR *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v49 + 80LL))(v49);
        if ( !SetFileSecurityW(v34, v31, lpSecurityDescriptor) )
        {
          v35 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v49 + 80LL))(v49);
          v36 = GetLastError();
          CMsiOpExecute::DispatchError(a1, v37, 1926, v36, v35);
          if ( v25 != -1 )
            CloseHandle((HANDLE)v25);
          CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges((CRefCountedTokenPrivileges *)v56);
          CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges((CRefCountedTokenPrivileges *)&NumberOfBytesWritten);
          CElevate::~CElevate((CElevate *)&v55);
          goto LABEL_54;
        }
        CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges((CRefCountedTokenPrivileges *)v56);
        CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges((CRefCountedTokenPrivileges *)&NumberOfBytesWritten);
        CElevate::~CElevate((CElevate *)&v55);
      }
    }
  }
  if ( v20 )
    StopImpersonating(v27);
  if ( v25 == -1 || v28 )
  {
    v47 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v49 + 80LL))(v49);
    CMsiOpExecute::DispatchError(a1, 0x1000000, 2932, v47, v28);
    if ( v25 != -1 )
      CloseHandle((HANDLE)v25);
    goto LABEL_54;
  }
  v38 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v51 + 56LL))(v51);
  v39 = 0x10000;
  if ( v38 <= 0x10000 )
  {
    if ( !v38 )
      v38 = 1;
    v39 = v38;
  }
  else
  {
    if ( !MsiSetFileSize((HANDLE)v25, v38, &LastError) )
    {
      FileInformation[0] = 1;
      SetFileInformationByHandle((HANDLE)v25, FileDispositionInfo, FileInformation, 1u);
      CloseHandle((HANDLE)v25);
      v40 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v49 + 80LL))(v49);
      CMsiOpExecute::DispatchError(a1, 0x1000000, 2932, v40, LastError);
      goto LABEL_54;
    }
    v28 = LastError;
  }
  CTempBuffer<char,1>::CTempBuffer<char,1>(&lpBuffer, v39);
  v41 = lpBuffer;
  if ( !lpBuffer )
  {
LABEL_45:
    CTempBuffer<unsigned short *,1>::~CTempBuffer<unsigned short *,1>(&lpBuffer);
    goto LABEL_54;
  }
  while ( 1 )
  {
    v42 = v59;
    v43 = (*(__int64 (__fastcall **)(__int64, LPCVOID, _QWORD))(*(_QWORD *)v51 + 64LL))(v51, v41, v59);
    v44 = v43;
    if ( v43 )
    {
      NumberOfBytesWritten = 0;
      if ( !WriteFile((HANDLE)v25, lpBuffer, v43, &NumberOfBytesWritten, 0) )
      {
        FileInformation[0] = 1;
        SetFileInformationByHandle((HANDLE)v25, FileDispositionInfo, FileInformation, 1u);
        CloseHandle((HANDLE)v25);
        v45 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v49 + 80LL))(v49);
        CMsiOpExecute::DispatchError(a1, 0x1000000, 2932, v45, v28);
        goto LABEL_45;
      }
    }
    if ( v44 != v42 )
      break;
    v41 = lpBuffer;
  }
  CloseHandle((HANDLE)v25);
  CTempBuffer<unsigned short *,1>::~CTempBuffer<unsigned short *,1>(&lpBuffer);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v54);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v51);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v49 + 16LL))(v49);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v50);
  return 1;
}

```

## disassembly

```asm
0x18014bc24  push    rbp
0x18014bc26  push    rbx
0x18014bc27  push    rsi
0x18014bc28  push    rdi
0x18014bc29  push    r12
0x18014bc2b  push    r13
0x18014bc2d  push    r14
0x18014bc2f  push    r15
0x18014bc31  lea     rbp, [rsp-17h]
0x18014bc36  sub     rsp, 0D8h
0x18014bc3d  mov     rax, cs:__security_cookie
0x18014bc44  xor     rax, rsp
0x18014bc47  mov     [rbp+4Fh+var_50], rax
0x18014bc4b  mov     rbx, [rbp+4Fh+arg_20]
0x18014bc4f  lea     r13, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18014bc56  xor     esi, esi
0x18014bc58  mov     [rbp+4Fh+lpSecurityAttributes], rbx
0x18014bc5c  mov     [rbp+4Fh+NumberOfBytesWritten], esi
0x18014bc5f  mov     r15, rcx
0x18014bc62  mov     rax, [rdx]
0x18014bc65  mov     rcx, r13
0x18014bc68  mov     r14, r9
0x18014bc6b  mov     [rbp+4Fh+var_A0], rsi
0x18014bc6f  mov     r12, r8
0x18014bc72  mov     [rbp+4Fh+var_A8], r13
0x18014bc76  mov     rdi, rdx
0x18014bc79  mov     rbx, [rax+88h]
0x18014bc80  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18014bc87  mov     rax, [rax+10h]
0x18014bc8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014bc90  mov     rcx, [r12]
0x18014bc94  mov     [rbp+4Fh+var_A8], r13
0x18014bc98  mov     rax, [rcx+50h]
0x18014bc9c  mov     rcx, r12
0x18014bc9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014bca4  mov     rdx, rax
0x18014bca7  lea     r8, [rbp+4Fh+var_A8]
0x18014bcab  mov     rax, rbx
0x18014bcae  mov     rcx, rdi
0x18014bcb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014bcb6  mov     rdx, rax
0x18014bcb9  lea     rcx, [rbp+4Fh+var_A0]
0x18014bcbd  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x18014bcc2  cmp     [rax], rsi
0x18014bcc5  jz      short loc_18014BCDD
0x18014bcc7  mov     r8, [rbp+4Fh+var_A0]
0x18014bccb  mov     edx, 1000000h
0x18014bcd0  mov     rcx, r15
0x18014bcd3  call    ?Message@CMsiOpExecute@@IEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::Message(imtEnum,IMsiRecord &)
0x18014bcd8  jmp     loc_18014C278
0x18014bcdd  lea     rcx, [rbp+4Fh+var_98]
0x18014bce1  mov     [rbp+4Fh+var_98], rsi
0x18014bce5  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x18014bcea  mov     rdx, [r14]
0x18014bced  mov     r8, rax
0x18014bcf0  mov     rcx, r14
0x18014bcf3  mov     r9, [rdx]
0x18014bcf6  lea     rdx, IID_IMsiStream
0x18014bcfd  mov     rax, r9
0x18014bd00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014bd05  xor     r14d, r14d
0x18014bd08  mov     rcx, r15
0x18014bd0b  test    eax, eax
0x18014bd0d  jz      short loc_18014BD28
0x18014bd0f  mov     r9, [rbp+4Fh+var_A8]
0x18014bd13  mov     edx, 1000000h
0x18014bd18  mov     r8d, 0B74h
0x18014bd1e  call    ?DispatchError@CMsiOpExecute@@QEAA?AW4imsEnum@@W4imtEnum@@HAEBVIMsiString@@@Z; CMsiOpExecute::DispatchError(imtEnum,int,IMsiString const &)
0x18014bd23  jmp     loc_18014C26F
0x18014bd28  mov     dword ptr [rsp+110h+var_D8], r14d
0x18014bd2d  xor     r9d, r9d
0x18014bd30  mov     dword ptr [rsp+110h+hTemplateFile], r14d
0x18014bd35  xor     r8d, r8d
0x18014bd38  mov     [rsp+110h+dwFlagsAndAttributes], 1
0x18014bd40  mov     rdx, rdi
0x18014bd43  mov     qword ptr [rsp+110h+dwCreationDisposition], r14
0x18014bd48  mov     [rbp+4Fh+var_88], r14
0x18014bd4c  call    ?CreateFolder@CMsiOpExecute@@IEAA?AW4iesEnum@@AEAVIMsiPath@@W4Bool@@1PEAVIMsiStream@@111@Z; CMsiOpExecute::CreateFolder(IMsiPath &,Bool,Bool,IMsiStream *,Bool,Bool,Bool)
0x18014bd51  cmp     eax, 1
0x18014bd54  jnz     loc_18014C266
0x18014bd5a  mov     rax, [rdi]
0x18014bd5d  mov     rcx, r12
0x18014bd60  mov     rdx, [r12]
0x18014bd64  mov     rbx, [rax+190h]
0x18014bd6b  mov     rax, [rdx+50h]
0x18014bd6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014bd74  mov     rdx, rax
0x18014bd77  xor     r8d, r8d
0x18014bd7a  mov     rax, rbx
0x18014bd7d  mov     rcx, rdi
0x18014bd80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014bd85  mov     rdx, rax
0x18014bd88  lea     rcx, [rbp+4Fh+var_A0]
0x18014bd8c  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x18014bd91  cmp     [rax], r14
0x18014bd94  jz      short loc_18014BDAC
0x18014bd96  mov     r8, [rbp+4Fh+var_A0]
0x18014bd9a  mov     edx, 1000000h
0x18014bd9f  mov     rcx, r15
0x18014bda2  call    ?Message@CMsiOpExecute@@IEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::Message(imtEnum,IMsiRecord &)
0x18014bda7  jmp     loc_18014C266
0x18014bdac  call    ?RunningAsLocalSystem@@YA?AW4TRI@@XZ; RunningAsLocalSystem(void)
0x18014bdb1  mov     r13d, eax
0x18014bdb4  cmp     eax, 0FFFFFFFFh
0x18014bdb7  jnz     short loc_18014BDE5
0x18014bdb9  mov     ecx, 5DDh; int
0x18014bdbe  call    ?PostError@@YAPEAVIMsiRecord@@H@Z; PostError(int)
0x18014bdc3  mov     r8, rax
0x18014bdc6  mov     [rbp+4Fh+var_80], rax
0x18014bdca  mov     edx, 1000000h
0x18014bdcf  mov     rcx, r15
0x18014bdd2  call    ?Message@CMsiOpExecute@@IEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::Message(imtEnum,IMsiRecord &)
0x18014bdd7  lea     rcx, [rbp+4Fh+var_80]
0x18014bddb  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x18014bde0  jmp     loc_18014C266
0x18014bde5  mov     ebx, 1
0x18014bdea  cmp     r13d, ebx
0x18014bded  jnz     short loc_18014BE13
0x18014bdef  mov     rax, [rdi]
0x18014bdf2  mov     rcx, rdi
0x18014bdf5  mov     rax, [rax+48h]
0x18014bdf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014bdfe  mov     rcx, rax; struct IMsiVolume *
0x18014be01  mov     [rbp+4Fh+var_80], rax
0x18014be05  mov     esi, ebx
0x18014be07  call    ?FVolumeRequiresImpersonation@@YA_NAEAVIMsiVolume@@@Z; FVolumeRequiresImpersonation(IMsiVolume &)
0x18014be0c  mov     r12b, bl
0x18014be0f  test    al, al
0x18014be11  jnz     short loc_18014BE16
0x18014be13  mov     r12b, r14b
0x18014be16  test    bl, sil
0x18014be19  jz      short loc_18014BE24
0x18014be1b  lea     rcx, [rbp+4Fh+var_80]
0x18014be1f  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x18014be24  test    r12b, r12b
0x18014be27  jz      short loc_18014BE2E
0x18014be29  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x18014be2e  mov     rcx, [rbp+4Fh+var_A8]
0x18014be32  mov     rax, [rcx]
0x18014be35  mov     rax, [rax+50h]
0x18014be39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014be3e  mov     rdi, [rbp+4Fh+lpSecurityAttributes]
0x18014be42  mov     ebx, 2
0x18014be47  mov     [rsp+110h+hTemplateFile], r14; hTemplateFile
0x18014be4c  mov     r9, rdi; lpSecurityAttributes
0x18014be4f  mov     [rsp+110h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x18014be57  mov     edx, 40010000h; dwDesiredAccess
0x18014be5c  mov     rcx, rax; lpFileName
0x18014be5f  mov     [rsp+110h+dwCreationDisposition], ebx; dwCreationDisposition
0x18014be63  lea     r8d, [rbx-1]; dwShareMode
0x18014be67  call    cs:__imp_CreateFileW
0x18014be6e  nop     dword ptr [rax+rax+00h]
0x18014be73  mov     rsi, rax
0x18014be76  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18014be7a  jz      loc_18014BF15
0x18014be80  mov     rcx, rax; hFile
0x18014be83  call    cs:__imp_GetFileType
0x18014be8a  nop     dword ptr [rax+rax+00h]
0x18014be8f  add     eax, 0FFFFFFFEh
0x18014be92  cmp     eax, 1
0x18014be95  ja      short loc_18014BF15
0x18014be97  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x18014be9e  jz      short loc_18014BEF3
0x18014bea0  mov     rcx, [rbp+4Fh+var_A8]
0x18014bea4  mov     rax, [rcx]
0x18014bea7  mov     rax, [rax+50h]
0x18014beab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014beb0  lea     rcx, aNull; "(NULL)"
0x18014beb7  mov     [rsp+110h+var_B8], r14; void *
0x18014bebc  mov     [rsp+110h+var_C0], r14d; unsigned int
0x18014bec1  lea     r9, aErrorThisIsNot; "Error: This is not a valid file, hence "...
0x18014bec8  mov     [rsp+110h+var_C8], rcx; unsigned __int16 *
0x18014becd  xor     edx, edx; unsigned __int16
0x18014becf  mov     [rsp+110h+var_D0], rcx; unsigned __int16 *
0x18014bed4  xor     r8d, r8d; int
0x18014bed7  mov     [rsp+110h+var_D8], rcx; unsigned __int16 *
0x18014bedc  mov     [rsp+110h+hTemplateFile], rcx; unsigned __int16 *
0x18014bee1  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], rcx; unsigned __int16 *
0x18014bee6  lea     ecx, [rbx+7]; int
0x18014bee9  mov     qword ptr [rsp+110h+dwCreationDisposition], rax; unsigned __int16 *
0x18014beee  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18014bef3  mov     rcx, rsi; hObject
0x18014bef6  call    cs:__imp_CloseHandle
0x18014befd  nop     dword ptr [rax+rax+00h]
0x18014bf02  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18014bf06  lea     ecx, [rsi+6Fh]; dwErrCode
0x18014bf09  call    cs:__imp_SetLastError
0x18014bf10  nop     dword ptr [rax+rax+00h]
0x18014bf15  call    cs:__imp_GetLastError
0x18014bf1c  nop     dword ptr [rax+rax+00h]
0x18014bf21  mov     [rbp+4Fh+var_8C], eax
0x18014bf24  mov     r14d, eax
0x18014bf27  cmp     eax, 0B7h
0x18014bf2c  jnz     loc_18014C04F
0x18014bf32  xor     r14d, r14d
0x18014bf35  mov     [rbp+4Fh+var_8C], r14d
0x18014bf39  test    rdi, rdi
0x18014bf3c  jz      loc_18014C04F
0x18014bf42  cmp     [rdi+8], r14
0x18014bf46  jz      loc_18014C04F
0x18014bf4c  cmp     r13d, 1
0x18014bf50  lea     r13d, [r14+1]
0x18014bf54  jnz     loc_18014C055
0x18014bf5a  mov     dl, r13b; bool
0x18014bf5d  lea     rcx, [rbp+4Fh+var_80]; this
0x18014bf61  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x18014bf66  mov     rcx, [rdi+8]; pSecurityDescriptor
0x18014bf6a  call    ?GetSecurityInformation@@YAKPEAX@Z; GetSecurityInformation(void *)
0x18014bf6f  mov     dl, r13b
0x18014bf72  mov     ecx, r13d
0x18014bf75  mov     edi, eax
0x18014bf77  call    ?RefCountedTokenPrivilegesCore@@YA_NW4itkpEnum@@_N@Z; RefCountedTokenPrivilegesCore(itkpEnum,bool)
0x18014bf7c  test    al, al
0x18014bf7e  lea     rcx, [rbp+4Fh+var_78]
0x18014bf82  mov     r8d, edi
0x18014bf85  cmovnz  ebx, r13d
0x18014bf89  shr     r8d, 3
0x18014bf8d  and     r8d, r13d
0x18014bf90  mov     [rbp+4Fh+NumberOfBytesWritten], ebx
0x18014bf93  call    ??0CRefCountedTokenPrivileges@@QEAA@W4itkpEnum@@W4Bool@@@Z; CRefCountedTokenPrivileges::CRefCountedTokenPrivileges(itkpEnum,Bool)
0x18014bf98  mov     rcx, [rbp+4Fh+var_A8]
0x18014bf9c  mov     rbx, [rbp+4Fh+lpSecurityAttributes]
0x18014bfa0  mov     rax, [rcx]
0x18014bfa3  mov     rbx, [rbx+8]
0x18014bfa7  mov     rax, [rax+50h]
0x18014bfab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014bfb0  mov     r8, rbx; pSecurityDescriptor
0x18014bfb3  mov     edx, edi; SecurityInformation
0x18014bfb5  mov     rcx, rax; lpFileName
0x18014bfb8  call    cs:__imp_SetFileSecurityW
0x18014bfbf  nop     dword ptr [rax+rax+00h]
0x18014bfc4  test    eax, eax
0x18014bfc6  jnz     short loc_18014C032
0x18014bfc8  mov     rcx, [rbp+4Fh+var_A8]
0x18014bfcc  mov     rax, [rcx]
0x18014bfcf  mov     rax, [rax+50h]
0x18014bfd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014bfd8  mov     rbx, rax
0x18014bfdb  call    cs:__imp_GetLastError
0x18014bfe2  nop     dword ptr [rax+rax+00h]
0x18014bfe7  mov     r8d, 786h
0x18014bfed  mov     qword ptr [rsp+110h+dwCreationDisposition], rbx
0x18014bff2  mov     r9d, eax
0x18014bff5  mov     rcx, r15
0x18014bff8  call    ?DispatchError@CMsiOpExecute@@QEAA?AW4imsEnum@@W4imtEnum@@HHPEBG@Z; CMsiOpExecute::DispatchError(imtEnum,int,int,ushort const *)
0x18014bffd  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18014c001  jz      short loc_18014C012
0x18014c003  mov     rcx, rsi; hObject
0x18014c006  call    cs:__imp_CloseHandle
0x18014c00d  nop     dword ptr [rax+rax+00h]
0x18014c012  lea     rcx, [rbp+4Fh+var_78]; this
0x18014c016  call    ??1CRefCountedTokenPrivileges@@QEAA@XZ; CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges(void)
0x18014c01b  lea     rcx, [rbp+4Fh+NumberOfBytesWritten]; this
0x18014c01f  call    ??1CRefCountedTokenPrivileges@@QEAA@XZ; CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges(void)
0x18014c024  lea     rcx, [rbp+4Fh+var_80]; this
0x18014c028  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x18014c02d  jmp     loc_18014C266
0x18014c032  lea     rcx, [rbp+4Fh+var_78]; this
0x18014c036  call    ??1CRefCountedTokenPrivileges@@QEAA@XZ; CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges(void)
0x18014c03b  lea     rcx, [rbp+4Fh+NumberOfBytesWritten]; this
0x18014c03f  call    ??1CRefCountedTokenPrivileges@@QEAA@XZ; CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges(void)
0x18014c044  lea     rcx, [rbp+4Fh+var_80]; this
0x18014c048  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x18014c04d  jmp     short loc_18014C055
0x18014c04f  mov     r13d, 1
0x18014c055  test    r12b, r12b
0x18014c058  jz      short loc_18014C05F
0x18014c05a  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x18014c05f  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18014c063  jz      loc_18014C226
0x18014c069  test    r14d, r14d
0x18014c06c  jnz     loc_18014C226
0x18014c072  mov     rcx, [rbp+4Fh+var_98]
0x18014c076  mov     rax, [rcx]
0x18014c079  mov     rax, [rax+38h]
0x18014c07d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014c082  mov     ebx, 10000h
0x18014c087  cmp     eax, ebx
0x18014c089  jbe     short loc_18014C102
0x18014c08b  lea     r8, [rbp+4Fh+var_8C]; unsigned int *
0x18014c08f  mov     edx, eax; lDistanceToMove
0x18014c091  mov     rcx, rsi; hFile
0x18014c094  call    ?MsiSetFileSize@@YA_NPEAXIPEAK@Z; MsiSetFileSize(void *,uint,ulong *)
0x18014c099  test    al, al
0x18014c09b  jnz     short loc_18014C0FC
0x18014c09d  mov     r9d, r13d; dwBufferSize
0x18014c0a0  mov     [rbp+4Fh+FileInformation], r13b
0x18014c0a4  lea     r8, [rbp+4Fh+FileInformation]; lpFileInformation
0x18014c0a8  mov     rcx, rsi; hFile
0x18014c0ab  lea     edx, [r14+4]; FileInformationClass
0x18014c0af  call    cs:__imp_SetFileInformationByHandle
0x18014c0b6  nop     dword ptr [rax+rax+00h]
0x18014c0bb  mov     rcx, rsi; hObject
0x18014c0be  call    cs:__imp_CloseHandle
0x18014c0c5  nop     dword ptr [rax+rax+00h]
0x18014c0ca  mov     rcx, [rbp+4Fh+var_A8]
0x18014c0ce  mov     rax, [rcx]
0x18014c0d1  mov     rax, [rax+50h]
0x18014c0d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014c0da  mov     ecx, [rbp+4Fh+var_8C]
  ... truncated ...
```
