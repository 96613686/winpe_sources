# CMsiOpExecute::CreateFileFromData(IMsiPath &,IMsiString const &,IMsiData const *,_SECURITY_ATTRIBUTES *)

- ea: `0x180146828`
- end: `0x180146e60`
- name: `?CreateFileFromData@CMsiOpExecute@@IEAA?AW4iesEnum@@AEAVIMsiPath@@AEBVIMsiString@@PEBVIMsiData@@PEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `1592`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64 *, unsigned int (__fastcall ***)(_QWORD, GUID *, __int64), struct _SECURITY_ATTRIBUTES *)`
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1801465c0`
- `0x1801f0a90`

## callees

- `0x180012620`
- `0x180024f9c`
- `0x180025904`
- `0x180025a18`
- `0x180035a8c`
- `0x180066074`
- `0x180068680`
- `0x180076e28`
- `0x18007cccc`
- `0x18007ccec`
- `0x18007d8cc`
- `0x180083178`
- `0x1800833ec`
- `0x1800a55e0`
- `0x1800cb9d8`
- `0x18011643c`
- `0x18011d2c4`
- `0x18013a830`
- `0x1801446ac`
- `0x180146828`
- `0x180154ed4`
- `0x18016d71c`
- `0x1801de4e0`
- `0x180216884`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!SetFileSecurityW` at `0x180146b9e`
- `ADVAPI32!SetFileSecurityW` at `0x180146b9e`
- `KERNEL32!SetFileInformationByHandle` at `0x180146c83`
- `KERNEL32!SetFileInformationByHandle` at `0x180146d55`
- `KERNEL32!SetFileInformationByHandle` at `0x180146c83`
- `KERNEL32!SetFileInformationByHandle` at `0x180146d55`
- `KERNEL32!CloseHandle` at `0x180146aee`
- `KERNEL32!CloseHandle` at `0x180146be0`
- `KERNEL32!CloseHandle` at `0x180146c8c`
- `KERNEL32!CloseHandle` at `0x180146d5e`
- `KERNEL32!CloseHandle` at `0x180146d97`
- `KERNEL32!CloseHandle` at `0x180146e0a`
- `KERNEL32!CloseHandle` at `0x180146aee`
- `KERNEL32!CloseHandle` at `0x180146be0`
- `KERNEL32!CloseHandle` at `0x180146c8c`
- `KERNEL32!CloseHandle` at `0x180146d5e`
- `KERNEL32!CloseHandle` at `0x180146d97`
- `KERNEL32!CloseHandle` at `0x180146e0a`
- `KERNEL32!GetLastError` at `0x180146b01`
- `KERNEL32!GetLastError` at `0x180146bbb`
- `KERNEL32!GetLastError` at `0x180146b01`
- `KERNEL32!GetLastError` at `0x180146bbb`
- `KERNEL32!SetLastError` at `0x180146afb`
- `KERNEL32!SetLastError` at `0x180146afb`
- `KERNEL32!CreateFileW` at `0x180146a6b`
- `KERNEL32!CreateFileW` at `0x180146a6b`
- `KERNEL32!GetFileType` at `0x180146a81`
- `KERNEL32!GetFileType` at `0x180146a81`
- `KERNEL32!WriteFile` at `0x180146d2e`
- `KERNEL32!WriteFile` at `0x180146d2e`

## string_xrefs

- `0x180146ab9`: `Error: This is not a valid file, hence failing to create: %s`

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
0x180146828  push    rbp
0x18014682a  push    rbx
0x18014682b  push    rsi
0x18014682c  push    rdi
0x18014682d  push    r12
0x18014682f  push    r13
0x180146831  push    r14
0x180146833  push    r15
0x180146835  lea     rbp, [rsp-17h]
0x18014683a  sub     rsp, 0D8h
0x180146841  mov     rax, cs:__security_cookie
0x180146848  xor     rax, rsp
0x18014684b  mov     [rbp+4Fh+var_50], rax
0x18014684f  mov     rbx, [rbp+4Fh+arg_20]
0x180146853  lea     r13, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18014685a  xor     esi, esi
0x18014685c  mov     [rbp+4Fh+lpSecurityAttributes], rbx
0x180146860  mov     [rbp+4Fh+NumberOfBytesWritten], esi
0x180146863  mov     r15, rcx
0x180146866  mov     rax, [rdx]
0x180146869  mov     rcx, r13
0x18014686c  mov     r14, r9
0x18014686f  mov     [rbp+4Fh+var_A0], rsi
0x180146873  mov     r12, r8
0x180146876  mov     [rbp+4Fh+var_A8], r13
0x18014687a  mov     rdi, rdx
0x18014687d  mov     rbx, [rax+88h]
0x180146884  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18014688b  mov     rax, [rax+10h]
0x18014688f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146894  mov     rcx, [r12]
0x180146898  mov     [rbp+4Fh+var_A8], r13
0x18014689c  mov     rax, [rcx+50h]
0x1801468a0  mov     rcx, r12
0x1801468a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801468a8  mov     rdx, rax
0x1801468ab  lea     r8, [rbp+4Fh+var_A8]
0x1801468af  mov     rax, rbx
0x1801468b2  mov     rcx, rdi
0x1801468b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801468ba  mov     rdx, rax
0x1801468bd  lea     rcx, [rbp+4Fh+var_A0]
0x1801468c1  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x1801468c6  cmp     [rax], rsi
0x1801468c9  jz      short loc_1801468E1
0x1801468cb  mov     r8, [rbp+4Fh+var_A0]
0x1801468cf  mov     edx, 1000000h
0x1801468d4  mov     rcx, r15
0x1801468d7  call    ?Message@CMsiOpExecute@@IEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::Message(imtEnum,IMsiRecord &)
0x1801468dc  jmp     loc_180146E22
0x1801468e1  lea     rcx, [rbp+4Fh+var_98]
0x1801468e5  mov     [rbp+4Fh+var_98], rsi
0x1801468e9  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x1801468ee  mov     rdx, [r14]
0x1801468f1  mov     r8, rax
0x1801468f4  mov     rcx, r14
0x1801468f7  mov     r9, [rdx]
0x1801468fa  lea     rdx, IID_IMsiStream
0x180146901  mov     rax, r9
0x180146904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146909  xor     r14d, r14d
0x18014690c  mov     rcx, r15
0x18014690f  test    eax, eax
0x180146911  jz      short loc_18014692C
0x180146913  mov     r9, [rbp+4Fh+var_A8]
0x180146917  mov     edx, 1000000h
0x18014691c  mov     r8d, 0B74h
0x180146922  call    ?DispatchError@CMsiOpExecute@@QEAA?AW4imsEnum@@W4imtEnum@@HAEBVIMsiString@@@Z; CMsiOpExecute::DispatchError(imtEnum,int,IMsiString const &)
0x180146927  jmp     loc_180146E19
0x18014692c  mov     dword ptr [rsp+110h+var_D8], r14d
0x180146931  xor     r9d, r9d
0x180146934  mov     dword ptr [rsp+110h+hTemplateFile], r14d
0x180146939  xor     r8d, r8d
0x18014693c  mov     [rsp+110h+dwFlagsAndAttributes], 1
0x180146944  mov     rdx, rdi
0x180146947  mov     qword ptr [rsp+110h+dwCreationDisposition], r14
0x18014694c  mov     [rbp+4Fh+var_88], r14
0x180146950  call    ?CreateFolder@CMsiOpExecute@@IEAA?AW4iesEnum@@AEAVIMsiPath@@W4Bool@@1PEAVIMsiStream@@111@Z; CMsiOpExecute::CreateFolder(IMsiPath &,Bool,Bool,IMsiStream *,Bool,Bool,Bool)
0x180146955  cmp     eax, 1
0x180146958  jnz     loc_180146E10
0x18014695e  mov     rax, [rdi]
0x180146961  mov     rcx, r12
0x180146964  mov     rdx, [r12]
0x180146968  mov     rbx, [rax+190h]
0x18014696f  mov     rax, [rdx+50h]
0x180146973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146978  mov     rdx, rax
0x18014697b  xor     r8d, r8d
0x18014697e  mov     rax, rbx
0x180146981  mov     rcx, rdi
0x180146984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146989  mov     rdx, rax
0x18014698c  lea     rcx, [rbp+4Fh+var_A0]
0x180146990  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x180146995  cmp     [rax], r14
0x180146998  jz      short loc_1801469B0
0x18014699a  mov     r8, [rbp+4Fh+var_A0]
0x18014699e  mov     edx, 1000000h
0x1801469a3  mov     rcx, r15
0x1801469a6  call    ?Message@CMsiOpExecute@@IEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::Message(imtEnum,IMsiRecord &)
0x1801469ab  jmp     loc_180146E10
0x1801469b0  call    ?RunningAsLocalSystem@@YA?AW4TRI@@XZ; RunningAsLocalSystem(void)
0x1801469b5  mov     r13d, eax
0x1801469b8  cmp     eax, 0FFFFFFFFh
0x1801469bb  jnz     short loc_1801469E9
0x1801469bd  mov     ecx, 5DDh; int
0x1801469c2  call    ?PostError@@YAPEAVIMsiRecord@@H@Z; PostError(int)
0x1801469c7  mov     r8, rax
0x1801469ca  mov     [rbp+4Fh+var_80], rax
0x1801469ce  mov     edx, 1000000h
0x1801469d3  mov     rcx, r15
0x1801469d6  call    ?Message@CMsiOpExecute@@IEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::Message(imtEnum,IMsiRecord &)
0x1801469db  lea     rcx, [rbp+4Fh+var_80]
0x1801469df  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1801469e4  jmp     loc_180146E10
0x1801469e9  mov     ebx, 1
0x1801469ee  cmp     r13d, ebx
0x1801469f1  jnz     short loc_180146A17
0x1801469f3  mov     rax, [rdi]
0x1801469f6  mov     rcx, rdi
0x1801469f9  mov     rax, [rax+48h]
0x1801469fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146a02  mov     rcx, rax; struct IMsiVolume *
0x180146a05  mov     [rbp+4Fh+var_80], rax
0x180146a09  mov     esi, ebx
0x180146a0b  call    ?FVolumeRequiresImpersonation@@YA_NAEAVIMsiVolume@@@Z; FVolumeRequiresImpersonation(IMsiVolume &)
0x180146a10  mov     r12b, bl
0x180146a13  test    al, al
0x180146a15  jnz     short loc_180146A1A
0x180146a17  mov     r12b, r14b
0x180146a1a  test    bl, sil
0x180146a1d  jz      short loc_180146A28
0x180146a1f  lea     rcx, [rbp+4Fh+var_80]
0x180146a23  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x180146a28  test    r12b, r12b
0x180146a2b  jz      short loc_180146A32
0x180146a2d  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x180146a32  mov     rcx, [rbp+4Fh+var_A8]
0x180146a36  mov     rax, [rcx]
0x180146a39  mov     rax, [rax+50h]
0x180146a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146a42  mov     rdi, [rbp+4Fh+lpSecurityAttributes]
0x180146a46  mov     ebx, 2
0x180146a4b  mov     [rsp+110h+hTemplateFile], r14; hTemplateFile
0x180146a50  mov     r9, rdi; lpSecurityAttributes
0x180146a53  mov     [rsp+110h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180146a5b  mov     edx, 40010000h; dwDesiredAccess
0x180146a60  mov     rcx, rax; lpFileName
0x180146a63  mov     [rsp+110h+dwCreationDisposition], ebx; dwCreationDisposition
0x180146a67  lea     r8d, [rbx-1]; dwShareMode
0x180146a6b  call    cs:__imp_CreateFileW
0x180146a71  mov     rsi, rax
0x180146a74  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180146a78  jz      loc_180146B01
0x180146a7e  mov     rcx, rax; hFile
0x180146a81  call    cs:__imp_GetFileType
0x180146a87  add     eax, 0FFFFFFFEh
0x180146a8a  cmp     eax, 1
0x180146a8d  ja      short loc_180146B01
0x180146a8f  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x180146a96  jz      short loc_180146AEB
0x180146a98  mov     rcx, [rbp+4Fh+var_A8]
0x180146a9c  mov     rax, [rcx]
0x180146a9f  mov     rax, [rax+50h]
0x180146aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146aa8  lea     rcx, aNull; "(NULL)"
0x180146aaf  mov     [rsp+110h+var_B8], r14; void *
0x180146ab4  mov     [rsp+110h+var_C0], r14d; unsigned int
0x180146ab9  lea     r9, aErrorThisIsNot; "Error: This is not a valid file, hence "...
0x180146ac0  mov     [rsp+110h+var_C8], rcx; unsigned __int16 *
0x180146ac5  xor     edx, edx; unsigned __int16
0x180146ac7  mov     [rsp+110h+var_D0], rcx; unsigned __int16 *
0x180146acc  xor     r8d, r8d; int
0x180146acf  mov     [rsp+110h+var_D8], rcx; unsigned __int16 *
0x180146ad4  mov     [rsp+110h+hTemplateFile], rcx; unsigned __int16 *
0x180146ad9  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], rcx; unsigned __int16 *
0x180146ade  lea     ecx, [rbx+7]; int
0x180146ae1  mov     qword ptr [rsp+110h+dwCreationDisposition], rax; unsigned __int16 *
0x180146ae6  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180146aeb  mov     rcx, rsi; hObject
0x180146aee  call    cs:__imp_CloseHandle
0x180146af4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180146af8  lea     ecx, [rsi+6Fh]; dwErrCode
0x180146afb  call    cs:__imp_SetLastError
0x180146b01  call    cs:__imp_GetLastError
0x180146b07  mov     [rbp+4Fh+var_8C], eax
0x180146b0a  mov     r14d, eax
0x180146b0d  cmp     eax, 0B7h
0x180146b12  jnz     loc_180146C23
0x180146b18  xor     r14d, r14d
0x180146b1b  mov     [rbp+4Fh+var_8C], r14d
0x180146b1f  test    rdi, rdi
0x180146b22  jz      loc_180146C23
0x180146b28  cmp     [rdi+8], r14
0x180146b2c  jz      loc_180146C23
0x180146b32  cmp     r13d, 1
0x180146b36  lea     r13d, [r14+1]
0x180146b3a  jnz     loc_180146C29
0x180146b40  mov     dl, r13b; bool
0x180146b43  lea     rcx, [rbp+4Fh+var_80]; this
0x180146b47  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x180146b4c  mov     rcx, [rdi+8]; pSecurityDescriptor
0x180146b50  call    ?GetSecurityInformation@@YAKPEAX@Z; GetSecurityInformation(void *)
0x180146b55  mov     dl, r13b
0x180146b58  mov     ecx, r13d
0x180146b5b  mov     edi, eax
0x180146b5d  call    ?RefCountedTokenPrivilegesCore@@YA_NW4itkpEnum@@_N@Z; RefCountedTokenPrivilegesCore(itkpEnum,bool)
0x180146b62  test    al, al
0x180146b64  lea     rcx, [rbp+4Fh+var_78]
0x180146b68  mov     r8d, edi
0x180146b6b  cmovnz  ebx, r13d
0x180146b6f  shr     r8d, 3
0x180146b73  and     r8d, r13d
0x180146b76  mov     [rbp+4Fh+NumberOfBytesWritten], ebx
0x180146b79  call    ??0CRefCountedTokenPrivileges@@QEAA@W4itkpEnum@@W4Bool@@@Z; CRefCountedTokenPrivileges::CRefCountedTokenPrivileges(itkpEnum,Bool)
0x180146b7e  mov     rcx, [rbp+4Fh+var_A8]
0x180146b82  mov     rbx, [rbp+4Fh+lpSecurityAttributes]
0x180146b86  mov     rax, [rcx]
0x180146b89  mov     rbx, [rbx+8]
0x180146b8d  mov     rax, [rax+50h]
0x180146b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146b96  mov     r8, rbx; pSecurityDescriptor
0x180146b99  mov     edx, edi; SecurityInformation
0x180146b9b  mov     rcx, rax; lpFileName
0x180146b9e  call    cs:__imp_SetFileSecurityW
0x180146ba4  test    eax, eax
0x180146ba6  jnz     short loc_180146C06
0x180146ba8  mov     rcx, [rbp+4Fh+var_A8]
0x180146bac  mov     rax, [rcx]
0x180146baf  mov     rax, [rax+50h]
0x180146bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146bb8  mov     rbx, rax
0x180146bbb  call    cs:__imp_GetLastError
0x180146bc1  mov     r8d, 786h
0x180146bc7  mov     qword ptr [rsp+110h+dwCreationDisposition], rbx
0x180146bcc  mov     r9d, eax
0x180146bcf  mov     rcx, r15
0x180146bd2  call    ?DispatchError@CMsiOpExecute@@QEAA?AW4imsEnum@@W4imtEnum@@HHPEBG@Z; CMsiOpExecute::DispatchError(imtEnum,int,int,ushort const *)
0x180146bd7  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180146bdb  jz      short loc_180146BE6
0x180146bdd  mov     rcx, rsi; hObject
0x180146be0  call    cs:__imp_CloseHandle
0x180146be6  lea     rcx, [rbp+4Fh+var_78]; this
0x180146bea  call    ??1CRefCountedTokenPrivileges@@QEAA@XZ; CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges(void)
0x180146bef  lea     rcx, [rbp+4Fh+NumberOfBytesWritten]; this
0x180146bf3  call    ??1CRefCountedTokenPrivileges@@QEAA@XZ; CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges(void)
0x180146bf8  lea     rcx, [rbp+4Fh+var_80]; this
0x180146bfc  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x180146c01  jmp     loc_180146E10
0x180146c06  lea     rcx, [rbp+4Fh+var_78]; this
0x180146c0a  call    ??1CRefCountedTokenPrivileges@@QEAA@XZ; CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges(void)
0x180146c0f  lea     rcx, [rbp+4Fh+NumberOfBytesWritten]; this
0x180146c13  call    ??1CRefCountedTokenPrivileges@@QEAA@XZ; CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges(void)
0x180146c18  lea     rcx, [rbp+4Fh+var_80]; this
0x180146c1c  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x180146c21  jmp     short loc_180146C29
0x180146c23  mov     r13d, 1
0x180146c29  test    r12b, r12b
0x180146c2c  jz      short loc_180146C33
0x180146c2e  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x180146c33  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180146c37  jz      loc_180146DD6
0x180146c3d  test    r14d, r14d
0x180146c40  jnz     loc_180146DD6
0x180146c46  mov     rcx, [rbp+4Fh+var_98]
0x180146c4a  mov     rax, [rcx]
0x180146c4d  mov     rax, [rax+38h]
0x180146c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146c56  mov     ebx, 10000h
0x180146c5b  cmp     eax, ebx
0x180146c5d  jbe     short loc_180146CCA
0x180146c5f  lea     r8, [rbp+4Fh+var_8C]; unsigned int *
0x180146c63  mov     edx, eax; lDistanceToMove
0x180146c65  mov     rcx, rsi; hFile
0x180146c68  call    ?MsiSetFileSize@@YA_NPEAXIPEAK@Z; MsiSetFileSize(void *,uint,ulong *)
0x180146c6d  test    al, al
0x180146c6f  jnz     short loc_180146CC4
0x180146c71  mov     r9d, r13d; dwBufferSize
0x180146c74  mov     [rbp+4Fh+FileInformation], r13b
0x180146c78  lea     r8, [rbp+4Fh+FileInformation]; lpFileInformation
0x180146c7c  mov     rcx, rsi; hFile
0x180146c7f  lea     edx, [r14+4]; FileInformationClass
0x180146c83  call    cs:__imp_SetFileInformationByHandle
0x180146c89  mov     rcx, rsi; hObject
0x180146c8c  call    cs:__imp_CloseHandle
0x180146c92  mov     rcx, [rbp+4Fh+var_A8]
0x180146c96  mov     rax, [rcx]
0x180146c99  mov     rax, [rax+50h]
0x180146c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146ca2  mov     ecx, [rbp+4Fh+var_8C]
0x180146ca5  mov     r9, rax
0x180146ca8  mov     [rsp+110h+dwCreationDisposition], ecx
0x180146cac  mov     edx, 1000000h
0x180146cb1  mov     rcx, r15
0x180146cb4  mov     r8d, 0B74h
0x180146cba  call    ?DispatchError@CMsiOpExecute@@QEAA?AW4imsEnum@@W4imtEnum@@HPEBGH@Z; CMsiOpExecute::DispatchError(imtEnum,int,ushort const *,int)
0x180146cbf  jmp     loc_180146E10
0x180146cc4  mov     r14d, [rbp+4Fh+var_8C]
0x180146cc8  jmp     short loc_180146CD2
0x180146cca  test    eax, eax
  ... truncated ...
```
