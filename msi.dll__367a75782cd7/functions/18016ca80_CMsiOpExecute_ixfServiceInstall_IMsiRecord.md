# CMsiOpExecute::ixfServiceInstall(IMsiRecord &)

- ea: `0x18016ca80`
- end: `0x18016d713`
- name: `?ixfServiceInstall@CMsiOpExecute@@IEAA?AW4iesEnum@@AEAVIMsiRecord@@@Z`
- size: `3219`
- prototype: `__int64 __fastcall(CMsiOpExecute *, __int64 *)`
- caller_count: `4`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800da4bc`
- `0x1800db2d0`
- `0x1800e12c4`
- `0x1801df8c0`

## callees

- `0x180012620`
- `0x180025904`
- `0x180035a8c`
- `0x18004295c`
- `0x1800620e4`
- `0x180066074`
- `0x180066db0`
- `0x180068680`
- `0x180076e28`
- `0x18007ccec`
- `0x18007d8cc`
- `0x180086134`
- `0x1800861d4`
- `0x1800888e8`
- `0x1800d6ff0`
- `0x1800e80a4`
- `0x18011d2c4`
- `0x18014a65c`
- `0x18016ca80`
- `0x18016d71c`
- `0x18016d7a4`
- `0x1801de458`
- `0x1801e113c`
- `0x1801ee834`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!SetServiceObjectSecurity` at `0x18016d3c5`
- `ADVAPI32!SetServiceObjectSecurity` at `0x18016d3c5`
- `ADVAPI32!ChangeServiceConfigW` at `0x18016cfde`
- `ADVAPI32!ChangeServiceConfigW` at `0x18016cfde`
- `ADVAPI32!CreateServiceW` at `0x18016ce21`
- `ADVAPI32!CreateServiceW` at `0x18016ce21`
- `ADVAPI32!CloseServiceHandle` at `0x18016cfeb`
- `ADVAPI32!CloseServiceHandle` at `0x18016d34d`
- `ADVAPI32!CloseServiceHandle` at `0x18016d40a`
- `ADVAPI32!CloseServiceHandle` at `0x18016d633`
- `ADVAPI32!CloseServiceHandle` at `0x18016cfeb`
- `ADVAPI32!CloseServiceHandle` at `0x18016d34d`
- `ADVAPI32!CloseServiceHandle` at `0x18016d40a`
- `ADVAPI32!CloseServiceHandle` at `0x18016d633`
- `ADVAPI32!OpenSCManagerW` at `0x18016cc37`
- `ADVAPI32!OpenSCManagerW` at `0x18016cc37`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18016d2fd`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18016d2fd`
- `KERNEL32!GetLastError` at `0x18016ce75`
- `KERNEL32!GetLastError` at `0x18016d076`
- `KERNEL32!GetLastError` at `0x18016d41e`
- `KERNEL32!GetLastError` at `0x18016d597`
- `KERNEL32!GetLastError` at `0x18016d5e3`
- `KERNEL32!GetLastError` at `0x18016ce75`
- `KERNEL32!GetLastError` at `0x18016d076`
- `KERNEL32!GetLastError` at `0x18016d41e`
- `KERNEL32!GetLastError` at `0x18016d597`
- `KERNEL32!GetLastError` at `0x18016d5e3`

## string_xrefs

- `0x18016d4d9`: `ServiceInstall`
- `0x18016cc2e`: `ServicesActive`
- `0x18016cb6d`: `System\CurrentControlSet\Services\`

## pseudocode

```c
__int64 __fastcall CMsiOpExecute::ixfServiceInstall(CMsiOpExecute *a1, __int64 *a2)
{
  __int64 v2; // rax
  CMsiOpExecute *v4; // r12
  struct IMsiString *v5; // r15
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rdi
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // r14
  __int64 (__fastcall *v13)(__int64, __int64, _QWORD, __int64); // rbx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 *v17; // rbx
  unsigned int v18; // r14d
  DWORD v19; // eax
  __int64 v20; // rax
  int v21; // r13d
  const struct IMsiString **v22; // rax
  SC_HANDLE ServiceHandle; // r14
  const WCHAR *v24; // rax
  __int64 v25; // rcx
  const WCHAR *v26; // rax
  __int64 v27; // rcx
  const WCHAR *v28; // r13
  const WCHAR *lpBinaryPathName; // r12
  DWORD v30; // r15d
  DWORD v31; // r14d
  const WCHAR *v32; // rbx
  const WCHAR *v33; // rax
  const WCHAR *ServiceW; // rax
  __int64 v35; // r9
  WCHAR *v36; // r14
  DWORD v37; // eax
  const WCHAR *v38; // rax
  CMsiOpExecute *v39; // rcx
  const WCHAR *v40; // rax
  __int64 v41; // rcx
  const WCHAR *v42; // rax
  __int64 v43; // rcx
  __int64 v44; // r13
  const WCHAR *v45; // r12
  __int64 v46; // r15
  __int64 v47; // r14
  DWORD v48; // ebx
  DWORD v49; // eax
  DWORD v50; // r15d
  __int64 v51; // rbx
  const wchar_t *v52; // r15
  const wchar_t *v53; // rax
  DWORD LastError; // eax
  struct IMsiRecord *v55; // rbx
  __int64 v56; // r9
  int v57; // eax
  __int64 v58; // r8
  const struct IMsiString *v59; // rbx
  struct IMsiStream **v60; // rax
  __int64 v61; // rax
  int v62; // eax
  unsigned int v63; // ebx
  unsigned int SecurityInformation; // eax
  bool v65; // zf
  char v66; // bl
  __int64 v67; // rdx
  char v68; // al
  int v69; // ecx
  __int64 v70; // rdx
  char v71; // al
  int v72; // edx
  const struct IMsiString **v73; // rax
  WCHAR *v74; // rbx
  BOOL v75; // ebx
  unsigned int v76; // ebx
  int v77; // eax
  MsiString *v78; // rax
  __int64 v79; // rbx
  DWORD v80; // eax
  __int64 v81; // rdx
  __int64 v82; // rbx
  DWORD v83; // eax
  __int64 v84; // rdx
  const WCHAR *dwServiceType; // [rsp+20h] [rbp-E0h]
  const WCHAR *dwStartType; // [rsp+28h] [rbp-D8h]
  const WCHAR *lpLoadOrderGroup; // [rsp+40h] [rbp-C0h]
  bool v88; // [rsp+70h] [rbp-90h]
  int v89; // [rsp+74h] [rbp-8Ch] BYREF
  LPCWSTR lpDependencies; // [rsp+78h] [rbp-88h] BYREF
  DWORD dwErrorControl; // [rsp+80h] [rbp-80h]
  int v92; // [rsp+84h] [rbp-7Ch] BYREF
  __int64 *v93; // [rsp+88h] [rbp-78h]
  __int64 v94; // [rsp+90h] [rbp-70h] BYREF
  __int64 v95; // [rsp+98h] [rbp-68h] BYREF
  struct IMsiString *v96; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v97; // [rsp+A8h] [rbp-58h] BYREF
  LPCWSTR lpPassword; // [rsp+B0h] [rbp-50h]
  CMsiOpExecute *v99; // [rsp+B8h] [rbp-48h]
  __int64 v100; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v101; // [rsp+C8h] [rbp-38h] BYREF
  int v102; // [rsp+D0h] [rbp-30h]
  int v103; // [rsp+D4h] [rbp-2Ch] BYREF
  __int64 v104; // [rsp+D8h] [rbp-28h] BYREF
  struct IMsiRecord *SharedRecord; // [rsp+E0h] [rbp-20h]
  LPCWSTR lpServiceStartName; // [rsp+E8h] [rbp-18h]
  _BYTE v107[8]; // [rsp+F0h] [rbp-10h] BYREF
  SC_HANDLE hSCManager; // [rsp+F8h] [rbp-8h]
  __int64 v109; // [rsp+100h] [rbp+0h] BYREF
  LPCWSTR lpDisplayName; // [rsp+108h] [rbp+8h]
  LPCWSTR v111; // [rsp+110h] [rbp+10h]
  const wchar_t *v112; // [rsp+118h] [rbp+18h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+120h] [rbp+20h] BYREF
  int v114; // [rsp+128h] [rbp+28h]
  _BYTE v115[512]; // [rsp+130h] [rbp+30h] BYREF

  v2 = *a2;
  v93 = a2;
  v4 = a1;
  v99 = a1;
  v5 = (struct IMsiString *)(*(__int64 (__fastcall **)(__int64 *, __int64))(v2 + 72))(a2, 1);
  v96 = v5;
  v6 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*a2 + 72))(a2, 2);
  v7 = *(_QWORD *)v4;
  v8 = v6;
  v103 = 0;
  v101 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 48LL))(v7, 1);
  (*(void (__fastcall **)(__int64, __int64, struct IMsiString *))(*(_QWORD *)v101 + 120LL))(v101, 1, v5);
  if ( (unsigned int)CMsiOpExecute::Message(v4, 150994944, v101) == 2 )
  {
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v101);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v5 + 16LL))(v5);
    return 2;
  }
  v100 = 0;
  MsiString::MsiString((MsiString *)&v97, L"System\\CurrentControlSet\\Services\\");
  MsiString::operator+=(&v97, &v96);
  v10 = *(_QWORD *)v4;
  v94 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v10 + 192LL))(v10, 2147483650LL, 0xFFFFFFFFLL);
  if ( !*(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v94, v11)
    || (v12 = v94,
        v13 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v94 + 112LL),
        v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v97 + 80LL))(v97),
        v15 = v13(v12, v14, 0, 0xFFFFFFFFLL),
        !*(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v94, v15)) )
  {
    CMsiOpExecute::Message(v4, 0x1000000, &off_180305DB0);
    goto LABEL_93;
  }
  v16 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v94 + 88LL))(v94, &v103);
  CComPointer<IMsiDatabase>::operator=(&v100, v16);
  hSCManager = OpenSCManagerW(0, L"ServicesActive", 0xF003Fu);
  if ( hSCManager )
  {
    v17 = v93;
    v18 = 3;
    v19 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v93 + 56))(v93, 6);
    dwErrorControl = v19;
    if ( (v19 & 0x8000) != 0 )
    {
      v102 = 1;
      dwErrorControl = v19 - 0x8000;
    }
    else
    {
      v102 = 0;
    }
    v20 = *v93;
    v21 = 1;
    v89 = 1;
    lpServiceStartName = (LPCWSTR)(*(__int64 (__fastcall **)(__int64 *, __int64))(v20 + 80))(v93, 10);
    while ( 1 )
    {
      if ( !v21 )
      {
        CloseServiceHandle(hSCManager);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v94);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v100);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v101);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v5 + 16LL))(v5);
        return v18;
      }
      ++HIDWORD(qword_1803096FC);
      v22 = (const struct IMsiString **)MsiString::MsiString((MsiString *)&v109, &Default);
      ServiceHandle = GetServiceHandle(*v22, v5, 0xE0007u);
      lpPassword = (LPCWSTR)ServiceHandle;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
      v88 = 1;
      SharedRecord = 0;
      if ( !ServiceHandle )
        break;
      v92 = 1;
      lpDependencies = (LPCWSTR)((char *)v4 + 32);
      if ( *((_QWORD *)v4 + 4) )
      {
        SharedRecord = CMsiOpExecute::GetSharedRecord(v4, 14);
        v88 = CMsiOpExecute::RollbackServiceConfiguration(v39, ServiceHandle, v5, SharedRecord);
      }
      v40 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 80LL))(v8);
      v41 = *v17;
      lpDisplayName = v40;
      v42 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64 *, __int64))(v41 + 80))(v17, 11);
      v43 = *v17;
      v111 = v42;
      v44 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v43 + 80))(v17, 10);
      v45 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64 *, __int64))(*v17 + 80))(v17, 8);
      v46 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v17 + 80))(v17, 7);
      v47 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v17 + 80))(v17, 3);
      v48 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v17 + 56))(v17, 5);
      v49 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v93 + 56))(v93, 4);
      lpLoadOrderGroup = (const WCHAR *)v44;
      v21 = 0;
      dwStartType = (const WCHAR *)v46;
      v50 = dwErrorControl;
      dwServiceType = (const WCHAR *)v47;
      v36 = (WCHAR *)lpPassword;
      if ( ChangeServiceConfigW(
             (SC_HANDLE)lpPassword,
             v49,
             v48,
             dwErrorControl,
             dwServiceType,
             dwStartType,
             0,
             v45,
             lpLoadOrderGroup,
             v111,
             lpDisplayName) )
      {
        v51 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v93 + 72))(v93, 12);
        v52 = 0;
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v51 + 56LL))(v51) )
        {
          v53 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v51 + 80LL))(v51);
          v52 = &Default;
          if ( *v53 )
            v52 = v53;
        }
        v112 = v52;
        if ( (unsigned int)((__int64 (__fastcall *)(WCHAR *, __int64, const wchar_t **))ADVAPI32::ChangeServiceConfig2W)(
                             v36,
                             1,
                             &v112) )
        {
          v4 = v99;
        }
        else
        {
          LastError = GetLastError();
          v4 = v99;
          if ( LastError != 1 )
            CMsiOpExecute::DispatchError(v99, 0x4000000, 1930, v8, v96);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        v38 = lpDependencies;
        goto LABEL_31;
      }
      CloseServiceHandle((SC_HANDLE)v36);
      v38 = lpDependencies;
      v36 = 0;
      v4 = v99;
      lpPassword = 0;
LABEL_32:
      if ( HIDWORD(qword_1803096FC) )
        --HIDWORD(qword_1803096FC);
      if ( v36 )
      {
        v18 = 1;
        if ( *(_QWORD *)v38 )
        {
          if ( !v92 )
          {
            v55 = CMsiOpExecute::GetSharedRecord(v4, 5);
            (*(void (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)v55 + 96LL))(v55, 1);
            v5 = v96;
            (*(void (__fastcall **)(struct IMsiRecord *, __int64, struct IMsiString *))(*(_QWORD *)v55 + 120LL))(
              v55,
              2,
              v96);
            (*(void (__fastcall **)(struct IMsiRecord *, __int64, __int64))(*(_QWORD *)v55 + 104LL))(v55, 3, 8);
            (*(void (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)v55 + 96LL))(v55, 4);
            (*(void (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)v55 + 96LL))(v55, 5);
            LOBYTE(v56) = 1;
            v18 = 2
                * ((unsigned __int8)WriteScriptRecord(*(_QWORD *)lpDependencies, 77, v55, v56, *((_QWORD *)v4 + 2)) ^ 1)
                + 1;
            goto LABEL_42;
          }
          if ( v88 )
          {
            LOBYTE(v35) = 1;
            if ( !(unsigned __int8)WriteScriptRecord(*(_QWORD *)v38, 78, SharedRecord, v35, *((_QWORD *)v4 + 2)) )
              v18 = 3;
          }
        }
        v5 = v96;
LABEL_42:
        v17 = v93;
        v95 = 0;
        v57 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v93 + 32))(v93, 14);
        v58 = *v17;
        if ( v57 )
        {
          if ( (*(unsigned int (__fastcall **)(__int64 *, __int64))(v58 + 32))(v17, 13) )
            goto LABEL_62;
          v61 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v17 + 64))(v17, 13);
          CComPointer<IMsiDatabase>::operator=(&v95, v61);
        }
        else
        {
          v59 = (const struct IMsiString *)(*(__int64 (__fastcall **)(__int64 *, __int64))(v58 + 72))(v17, 14);
          v60 = (struct IMsiStream **)CComPointer<IEnumMsiRecord>::operator=(&v95);
          if ( !GenerateSDFromSDDL(v59, v60) )
          {
            v78 = MsiString::MsiString((MsiString *)&v104, L"ServiceInstall");
            CMsiOpExecute::DispatchError(v4, 0x1000000, 1943, v59, v5, *(_QWORD *)v78);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
            (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v59 + 16LL))(v59);
            goto LABEL_85;
          }
          (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v59 + 16LL))(v59);
        }
        memset_0(v115, 0, sizeof(v115));
        pSecurityDescriptor = v115;
        v114 = 512;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 112LL))(v95);
        v62 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v95 + 32LL))(v95);
        v63 = v62;
        if ( v62 > 512 )
          CTempBuffer<char,512>::SetSize(&pSecurityDescriptor, (unsigned int)v62);
        if ( !pSecurityDescriptor )
        {
          CMsiOpExecute::DispatchError(v4, 0x1000000, 2402);
          goto LABEL_89;
        }
        (*(void (__fastcall **)(__int64, PSECURITY_DESCRIPTOR, _QWORD))(*(_QWORD *)v95 + 64LL))(
          v95,
          pSecurityDescriptor,
          v63);
        IsValidSecurityDescriptor(pSecurityDescriptor);
        SecurityInformation = GetSecurityInformation(pSecurityDescriptor);
        v65 = *((_DWORD *)v4 + 125) == 2;
        v66 = SecurityInformation;
        LODWORD(lpDependencies) = SecurityInformation;
        CElevate::CElevate((CElevate *)v107, v65);
        LOBYTE(v67) = 1;
        v68 = RefCountedTokenPrivilegesCore(1, v67);
        v69 = 2;
        if ( v68 )
          v69 = 1;
        v89 = v69;
        if ( (v66 & 8) != 0 )
        {
          CloseServiceHandle((SC_HANDLE)lpPassword);
          LOBYTE(v70) = 1;
          v71 = RefCountedTokenPrivilegesCore(0, v70);
          v72 = 2;
          if ( v71 )
            v72 = 0;
          v92 = v72;
          v73 = (const struct IMsiString **)MsiString::MsiString((MsiString *)&v104, &Default);
          v74 = (WCHAR *)GetServiceHandle(*v73, v5, 0x10C0000u);
          lpPassword = v74;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
          if ( !v74 )
          {
            v79 = (*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)v5 + 80LL))(v5);
            v80 = GetLastError();
            CMsiOpExecute::DispatchError(v4, v81, 1944, v80, v79);
            CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges((CRefCountedTokenPrivileges *)&v92);
            CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges((CRefCountedTokenPrivileges *)&v89);
            CElevate::~CElevate((CElevate *)v107);
LABEL_89:
            if ( v114 > 512 )
              operator delete(pSecurityDescriptor);
LABEL_85:
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v95);
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v94);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v100);
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v101);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
            (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v5 + 16LL))(v5);
            return 3;
          }
          CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges((CRefCountedTokenPrivileges *)&v92);
        }
        else
        {
          v74 = (WCHAR *)lpPassword;
        }
        v75 = SetServiceObjectSecurity((SC_HANDLE)v74, (SECURITY_INFORMATION)lpDependencies, pSecurityDescriptor);
        CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges((CRefCountedTokenPrivileges *)&v89);
        CElevate::~CElevate((CElevate *)v107);
        if ( !v75 )
        {
          v82 = (*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)v5 + 80LL))(v5);
          v83 = GetLastError();
          CMsiOpExecute::DispatchError(v4, v84, 1944, v83, v82);
          goto LABEL_89;
        }
        if ( v114 > 512 )
          operator delete(pSecurityDescriptor);
        v17 = v93;
LABEL_62:
        v21 = 0;
        v89 = 0;
        CloseServiceHandle((SC_HANDLE)lpPassword);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v95);
      }
      else
      {
        GetLastError();
        if ( !lpServiceStartName || *((_DWORD *)v4 + 10) != 2 )
        {
          if ( v102 )
            goto LABEL_69;
          if ( v50 )
          {
            if ( v50 == 1 )
            {
              v76 = 16777730;
              goto LABEL_72;
            }
            if ( v50 - 2 <= 1 )
            {
LABEL_69:
              v76 = 16777221;
              goto LABEL_72;
            }
          }
        }
        v76 = 0x4000000;
LABEL_72:
        v5 = v96;
        v77 = CMsiOpExecute::DispatchError(v4, v76, 1923, v8, v96);
        if ( v77 == 4 )
        {
          v21 = v89;
LABEL_82:
          v18 = 3;
          goto LABEL_83;
        }
        v89 = 0;
        if ( v77 == 5 )
        {
          v21 = 0;
          v18 = 1;
          v89 = 0;
          goto LABEL_83;
        }
        if ( v77 )
          goto LABEL_82;
        if ( v76 == 0x4000000 )
        {
          v18 = 1;
        }
        else
        {
          v18 = 3;
          if ( (v76 & 0x202) == 0x202 )
            v18 = 1;
        }
LABEL_83:
        v17 = v93;
      }
    }
    v92 = 0;
    v24 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64 *, __int64))(*v17 + 80))(v17, 11);
    v25 = *v17;
    lpPassword = v24;
    v26 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64 *, __int64))(v25 + 80))(v17, 8);
    v27 = *v17;
    lpDependencies = v26;
    v28 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64 *, __int64))(v27 + 80))(v17, 7);
    lpBinaryPathName = (const WCHAR *)(*(__int64 (__fastcall **)(__int64 *, __int64))(*v17 + 80))(v17, 3);
    v30 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v17 + 56))(v17, 5);
    v31 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v17 + 56))(v17, 4);
    v32 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 80LL))(v8);
    v33 = (const WCHAR *)(*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)v96 + 80LL))(v96);
    ServiceW = (const WCHAR *)CreateServiceW(
                                hSCManager,
                                v33,
                                v32,
                                0xF0002u,
                                v31,
                                v30,
                                dwErrorControl,
                                lpBinaryPathName,
                                v28,
                                0,
                                lpDependencies,
                                lpServiceStartName,
                                lpPassword);
    v21 = 0;
    lpPassword = ServiceW;
    v36 = (WCHAR *)ServiceW;
    if ( !ServiceW
      || (lpDependencies = 0,
          lpDependencies = (LPCWSTR)(*(__int64 (__fastcall **)(__int64 *, __int64))(*v93 + 80))(v93, 12),
          (unsigned int)((__int64 (__fastcall *)(WCHAR *, __int64, LPCWSTR *))ADVAPI32::ChangeServiceConfig2W)(
                          v36,
                          1,
                          &lpDependencies)) )
    {
      v4 = v99;
    }
    else
    {
      v37 = GetLastError();
      v4 = v99;
      if ( v37 != 1 )
        CMsiOpExecute::DispatchError(v99, 0x4000000, 1930, v8, v96);
    }
    v38 = (const WCHAR *)((char *)v4 + 32);
LABEL_31:
    v50 = dwErrorControl;
    lpDependencies = v38;
    goto LABEL_32;
  }
  CMsiOpExecute::DispatchError(v4, 0x1000000, 1923, v8, v5);
LABEL_93:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v94);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v100);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v101);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v5 + 16LL))(v5);
  return 3;
}

```

## disassembly

```asm
0x18016ca80  mov     [rsp-8+arg_10], rbx
0x18016ca85  push    rbp
0x18016ca86  push    rsi
0x18016ca87  push    rdi
0x18016ca88  push    r12
0x18016ca8a  push    r13
0x18016ca8c  push    r14
0x18016ca8e  push    r15
0x18016ca90  lea     rbp, [rsp-240h]
0x18016ca98  sub     rsp, 340h
0x18016ca9f  mov     rax, cs:__security_cookie
0x18016caa6  xor     rax, rsp
0x18016caa9  mov     [rbp+270h+var_40], rax
0x18016cab0  mov     rax, [rdx]
0x18016cab3  mov     rbx, rdx
0x18016cab6  mov     [rbp+270h+var_2E8], rdx
0x18016caba  mov     r12, rcx
0x18016cabd  mov     [rbp+270h+var_2B8], rcx
0x18016cac1  mov     r14d, 1
0x18016cac7  mov     edx, r14d
0x18016caca  mov     rcx, rbx
0x18016cacd  mov     rax, [rax+48h]
0x18016cad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016cad6  mov     r15, rax
0x18016cad9  mov     [rbp+270h+var_2D0], rax
0x18016cadd  mov     rax, [rbx]
0x18016cae0  lea     esi, [r14+1]
0x18016cae4  mov     edx, esi
0x18016cae6  mov     rcx, rbx
0x18016cae9  mov     rax, [rax+48h]
0x18016caed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016caf2  mov     rcx, [r12]
0x18016caf6  mov     rdi, rax
0x18016caf9  xor     r13d, r13d
0x18016cafc  mov     edx, r14d
0x18016caff  mov     [rbp+270h+var_29C], r13d
0x18016cb03  mov     rax, [rcx]
0x18016cb06  mov     rax, [rax+30h]
0x18016cb0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016cb0f  mov     rbx, rax
0x18016cb12  mov     [rbp+270h+var_2A8], rax
0x18016cb16  mov     r8, r15
0x18016cb19  mov     edx, r14d
0x18016cb1c  mov     rcx, rbx
0x18016cb1f  mov     rax, [rax]
0x18016cb22  mov     rax, [rax+78h]
0x18016cb26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016cb2b  mov     r8, rbx
0x18016cb2e  mov     edx, 9000000h
0x18016cb33  mov     rcx, r12
0x18016cb36  call    ?Message@CMsiOpExecute@@IEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::Message(imtEnum,IMsiRecord &)
0x18016cb3b  cmp     eax, esi
0x18016cb3d  jnz     short loc_18016CB6D
0x18016cb3f  lea     rcx, [rbp+270h+var_2A8]
0x18016cb43  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x18016cb48  mov     rax, [rdi]
0x18016cb4b  mov     rcx, rdi
0x18016cb4e  mov     rax, [rax+10h]
0x18016cb52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016cb57  mov     rax, [r15]
0x18016cb5a  mov     rcx, r15
0x18016cb5d  mov     rax, [rax+10h]
0x18016cb61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016cb66  mov     eax, esi
0x18016cb68  jmp     loc_18016D6E9
0x18016cb6d  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\"
0x18016cb74  mov     [rbp+270h+var_2B0], r13
0x18016cb78  lea     rcx, [rbp+270h+var_2C8]; this
0x18016cb7c  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x18016cb81  lea     rdx, [rbp+270h+var_2D0]
0x18016cb85  lea     rcx, [rbp+270h+var_2C8]
0x18016cb89  call    ??YMsiString@@QEAAAEAV0@AEBV0@@Z; MsiString::operator+=(MsiString const &)
0x18016cb8e  mov     rcx, [r12]
0x18016cb92  or      r8d, 0FFFFFFFFh
0x18016cb96  mov     [rbp+270h+var_2E0], r13
0x18016cb9a  mov     edx, 80000002h
0x18016cb9f  mov     rax, [rcx]
0x18016cba2  mov     rax, [rax+0C0h]
0x18016cba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016cbae  mov     rdx, rax
0x18016cbb1  lea     rcx, [rbp+270h+var_2E0]
0x18016cbb5  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x18016cbba  cmp     [rax], r13
0x18016cbbd  jz      loc_18016D687
0x18016cbc3  mov     r14, [rbp+270h+var_2E0]
0x18016cbc7  mov     rcx, [rbp+270h+var_2C8]
0x18016cbcb  mov     rax, [r14]
0x18016cbce  mov     rdx, [rcx]
0x18016cbd1  mov     rbx, [rax+70h]
0x18016cbd5  mov     rax, [rdx+50h]
0x18016cbd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016cbde  mov     rdx, rax
0x18016cbe1  or      r9d, 0FFFFFFFFh
0x18016cbe5  mov     rax, rbx
0x18016cbe8  xor     r8d, r8d
0x18016cbeb  mov     rcx, r14
0x18016cbee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016cbf3  mov     rdx, rax
0x18016cbf6  lea     rcx, [rbp+270h+var_2E0]
0x18016cbfa  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x18016cbff  cmp     [rax], r13
0x18016cc02  jz      loc_18016D687
0x18016cc08  mov     rcx, [rbp+270h+var_2E0]
0x18016cc0c  lea     rdx, [rbp+270h+var_29C]
0x18016cc10  mov     rax, [rcx]
0x18016cc13  mov     rax, [rax+58h]
0x18016cc17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016cc1c  mov     rdx, rax
0x18016cc1f  lea     rcx, [rbp+270h+var_2B0]
0x18016cc23  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x18016cc28  mov     r8d, 0F003Fh; dwDesiredAccess
0x18016cc2e  lea     rdx, DatabaseName; "ServicesActive"
0x18016cc35  xor     ecx, ecx; lpMachineName
0x18016cc37  call    cs:__imp_OpenSCManagerW
0x18016cc3d  mov     [rbp+270h+hSCManager], rax
0x18016cc41  test    rax, rax
0x18016cc44  jnz     short loc_18016CC66
0x18016cc46  mov     r9, rdi
0x18016cc49  mov     qword ptr [rsp+370h+dwServiceType], r15
0x18016cc4e  mov     edx, 1000000h
0x18016cc53  mov     r8d, 783h
0x18016cc59  mov     rcx, r12
0x18016cc5c  call    ?DispatchError@CMsiOpExecute@@QEAA?AW4imsEnum@@W4imtEnum@@HAEBVIMsiString@@1@Z; CMsiOpExecute::DispatchError(imtEnum,int,IMsiString const &,IMsiString const &)
0x18016cc61  jmp     loc_18016D69B
0x18016cc66  mov     rbx, [rbp+270h+var_2E8]
0x18016cc6a  mov     r14d, 3
0x18016cc70  mov     rcx, rbx
0x18016cc73  mov     rax, [rbx]
0x18016cc76  lea     edx, [r14+3]
0x18016cc7a  mov     rax, [rax+38h]
0x18016cc7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016cc83  mov     [rbp+270h+var_2F0], eax
0x18016cc86  lea     edx, [r14-2]
0x18016cc8a  bt      eax, 0Fh
0x18016cc8e  jnb     short loc_18016CC9D
0x18016cc90  add     eax, 0FFFF8000h
0x18016cc95  mov     [rbp+270h+var_2A0], edx
0x18016cc98  mov     [rbp+270h+var_2F0], eax
0x18016cc9b  jmp     short loc_18016CCA1
0x18016cc9d  mov     [rbp+270h+var_2A0], r13d
0x18016cca1  mov     rax, [rbx]
0x18016cca4  mov     r13d, edx
0x18016cca7  mov     [rsp+370h+var_2FC], edx
0x18016ccab  mov     rcx, rbx
0x18016ccae  mov     edx, 0Ah
0x18016ccb3  mov     rax, [rax+50h]
0x18016ccb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016ccbc  mov     [rbp+270h+var_288], rax
0x18016ccc0  test    r13d, r13d
0x18016ccc3  jz      loc_18016D62F
0x18016ccc9  mov     r13d, 1
0x18016cccf  lea     rdx, Default; unsigned __int16 *
0x18016ccd6  add     dword ptr cs:qword_1803096FC+4, r13d
0x18016ccdd  lea     rcx, [rbp+270h+var_270]; this
0x18016cce1  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x18016cce6  mov     r8d, 0E0007h; unsigned int
0x18016ccec  mov     rdx, r15; struct IMsiString *
0x18016ccef  mov     rcx, [rax]; struct IMsiString *
0x18016ccf2  call    ?GetServiceHandle@@YAPEAUSC_HANDLE__@@AEBVIMsiString@@0K@Z; GetServiceHandle(IMsiString const &,IMsiString const &,ulong)
0x18016ccf7  mov     rcx, [rbp+270h+var_270]
0x18016ccfb  mov     r14, rax
0x18016ccfe  mov     [rbp+270h+var_2C0], rax
0x18016cd02  mov     rdx, [rcx]
0x18016cd05  mov     rax, [rdx+10h]
0x18016cd09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016cd0e  xor     eax, eax
0x18016cd10  mov     [rsp+370h+var_300], r13b
0x18016cd15  mov     [rbp+270h+var_290], rax
0x18016cd19  test    r14, r14
0x18016cd1c  jnz     loc_18016CEB2
0x18016cd22  mov     [rbp+270h+var_2EC], eax
0x18016cd25  lea     edx, [r13+0Ah]
0x18016cd29  mov     rax, [rbx]
0x18016cd2c  mov     rcx, rbx
0x18016cd2f  mov     rax, [rax+50h]
0x18016cd33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016cd38  mov     rcx, [rbx]
0x18016cd3b  lea     edx, [r13+7]
0x18016cd3f  mov     [rbp+270h+var_2C0], rax
0x18016cd43  mov     rax, [rcx+50h]
0x18016cd47  mov     rcx, rbx
0x18016cd4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016cd4f  mov     rcx, [rbx]
0x18016cd52  lea     edx, [r13+6]
0x18016cd56  mov     [rsp+370h+var_2F8], rax
0x18016cd5b  mov     rax, [rcx+50h]
0x18016cd5f  mov     rcx, rbx
0x18016cd62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016cd67  mov     rcx, [rbx]
0x18016cd6a  lea     edx, [r14+3]
0x18016cd6e  mov     r13, rax
0x18016cd71  mov     rax, [rcx+50h]
0x18016cd75  mov     rcx, rbx
0x18016cd78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016cd7d  mov     rcx, [rbx]
0x18016cd80  lea     edx, [r14+5]
0x18016cd84  mov     r12, rax
0x18016cd87  mov     rax, [rcx+38h]
0x18016cd8b  mov     rcx, rbx
0x18016cd8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016cd93  mov     rcx, [rbx]
0x18016cd96  lea     edx, [r14+4]
0x18016cd9a  mov     r15d, eax
0x18016cd9d  mov     rax, [rcx+38h]
0x18016cda1  mov     rcx, rbx
0x18016cda4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016cda9  mov     rcx, [rdi]
0x18016cdac  mov     r14d, eax
0x18016cdaf  mov     rax, [rcx+50h]
0x18016cdb3  mov     rcx, rdi
0x18016cdb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016cdbb  mov     rdx, [rbp+270h+var_2D0]
0x18016cdbf  mov     rbx, rax
0x18016cdc2  mov     rcx, [rdx]
0x18016cdc5  mov     rax, [rcx+50h]
0x18016cdc9  mov     rcx, rdx
0x18016cdcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016cdd1  mov     rcx, [rbp+270h+var_2C0]
0x18016cdd5  mov     r9d, 0F0002h; dwDesiredAccess
0x18016cddb  mov     [rsp+370h+lpPassword], rcx; lpPassword
0x18016cde0  mov     r8, rbx; lpDisplayName
0x18016cde3  mov     rcx, [rbp+270h+var_288]
0x18016cde7  mov     rdx, rax; lpServiceName
0x18016cdea  mov     [rsp+370h+lpServiceStartName], rcx; lpServiceStartName
0x18016cdef  mov     rcx, [rsp+370h+var_2F8]
0x18016cdf4  mov     [rsp+370h+lpDependencies], rcx; lpDependencies
0x18016cdf9  mov     ecx, [rbp+270h+var_2F0]
0x18016cdfc  mov     [rsp+370h+lpdwTagId], 0; lpdwTagId
0x18016ce05  mov     [rsp+370h+lpLoadOrderGroup], r13; lpLoadOrderGroup
0x18016ce0a  mov     [rsp+370h+lpBinaryPathName], r12; lpBinaryPathName
0x18016ce0f  mov     [rsp+370h+dwErrorControl], ecx; dwErrorControl
0x18016ce13  mov     rcx, [rbp+270h+hSCManager]; hSCManager
0x18016ce17  mov     [rsp+370h+dwStartType], r15d; dwStartType
0x18016ce1c  mov     [rsp+370h+dwServiceType], r14d; dwServiceType
0x18016ce21  call    cs:__imp_CreateServiceW
0x18016ce27  xor     r13d, r13d
0x18016ce2a  mov     [rbp+270h+var_2C0], rax
0x18016ce2e  mov     r14, rax
0x18016ce31  test    rax, rax
0x18016ce34  jz      short loc_18016CEA4
0x18016ce36  mov     r8, [rbp+270h+var_2E8]
0x18016ce3a  lea     edx, [r13+0Ch]
0x18016ce3e  mov     rcx, r8
0x18016ce41  mov     [rsp+370h+var_2F8], r13
0x18016ce46  mov     rax, [r8]
0x18016ce49  mov     rax, [rax+50h]
0x18016ce4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016ce52  mov     [rsp+370h+var_2F8], rax
0x18016ce57  lea     ebx, [r13+1]
0x18016ce5b  mov     rax, cs:?ChangeServiceConfig2W@ADVAPI32@@3P6AHPEAUSC_HANDLE__@@KPEAX@ZEA; int (*ADVAPI32::ChangeServiceConfig2W)(SC_HANDLE__ *,ulong,void *)
0x18016ce62  lea     r8, [rsp+370h+var_2F8]
0x18016ce67  mov     edx, ebx
0x18016ce69  mov     rcx, r14
0x18016ce6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016ce71  test    eax, eax
0x18016ce73  jnz     short loc_18016CEA4
0x18016ce75  call    cs:__imp_GetLastError
0x18016ce7b  mov     r12, [rbp+270h+var_2B8]
0x18016ce7f  cmp     eax, ebx
0x18016ce81  jz      short loc_18016CEA8
0x18016ce83  mov     rax, [rbp+270h+var_2D0]
0x18016ce87  mov     r9, rdi
0x18016ce8a  mov     edx, 4000000h
0x18016ce8f  mov     qword ptr [rsp+370h+dwServiceType], rax
0x18016ce94  mov     r8d, 78Ah
0x18016ce9a  mov     rcx, r12
0x18016ce9d  call    ?DispatchError@CMsiOpExecute@@QEAA?AW4imsEnum@@W4imtEnum@@HAEBVIMsiString@@1@Z; CMsiOpExecute::DispatchError(imtEnum,int,IMsiString const &,IMsiString const &)
0x18016cea2  jmp     short loc_18016CEA8
0x18016cea4  mov     r12, [rbp+270h+var_2B8]
0x18016cea8  lea     rax, [r12+20h]
0x18016cead  jmp     loc_18016D0BE
0x18016ceb2  lea     rcx, [r12+20h]
0x18016ceb7  mov     [rbp+270h+var_2EC], r13d
0x18016cebb  mov     [rsp+370h+var_2F8], rcx
0x18016cec0  cmp     [rcx], rax
0x18016cec3  jz      short loc_18016CEE8
0x18016cec5  mov     edx, 0Eh; int
0x18016ceca  mov     rcx, r12; this
0x18016cecd  call    ?GetSharedRecord@CMsiOpExecute@@IEAAAEAVIMsiRecord@@H@Z; CMsiOpExecute::GetSharedRecord(int)
0x18016ced2  mov     r9, rax; struct IMsiRecord *
0x18016ced5  mov     [rbp+270h+var_290], rax
0x18016ced9  mov     r8, r15; struct IMsiString *
0x18016cedc  mov     rdx, r14; struct SC_HANDLE__ *
0x18016cedf  call    ?RollbackServiceConfiguration@CMsiOpExecute@@IEAA_NQEAUSC_HANDLE__@@AEBVIMsiString@@AEAVIMsiRecord@@@Z; CMsiOpExecute::RollbackServiceConfiguration(SC_HANDLE__ * const,IMsiString const &,IMsiRecord &)
0x18016cee4  mov     [rsp+370h+var_300], al
0x18016cee8  mov     rcx, [rdi]
0x18016ceeb  mov     rax, [rcx+50h]
0x18016ceef  mov     rcx, rdi
0x18016cef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016cef7  mov     rcx, [rbx]
0x18016cefa  mov     edx, 0Bh
0x18016ceff  mov     [rbp+270h+lpDisplayName], rax
0x18016cf03  mov     rax, [rcx+50h]
0x18016cf07  mov     rcx, rbx
0x18016cf0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016cf0f  mov     rcx, [rbx]
0x18016cf12  mov     edx, 0Ah
0x18016cf17  mov     [rbp+270h+var_260], rax
0x18016cf1b  mov     rax, [rcx+50h]
0x18016cf1f  mov     rcx, rbx
  ... truncated ...
```
