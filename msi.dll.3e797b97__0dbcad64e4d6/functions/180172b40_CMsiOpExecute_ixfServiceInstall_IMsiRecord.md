# CMsiOpExecute::ixfServiceInstall(IMsiRecord &)

- ea: `0x180172b40`
- end: `0x180173814`
- name: `?ixfServiceInstall@CMsiOpExecute@@IEAA?AW4iesEnum@@AEAVIMsiRecord@@@Z`
- size: `3284`
- prototype: ``
- caller_count: `4`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c6ebc`
- `0x18012c888`
- `0x1801328bc`
- `0x1801e8810`

## callees

- `0x180003b10`
- `0x180005af8`
- `0x180014528`
- `0x180019cc0`
- `0x18002e870`
- `0x180038e70`
- `0x180065abc`
- `0x180066708`
- `0x180067fec`
- `0x18007adb4`
- `0x18007b9e8`
- `0x18007f4c8`
- `0x18008c93c`
- `0x18009ca0c`
- `0x1800d8584`
- `0x1800d8740`
- `0x1800dcef8`
- `0x1800ee66c`
- `0x18014fcb8`
- `0x180172b40`
- `0x18017381c`
- `0x1801738a4`
- `0x1801e7390`
- `0x1801ea0fc`
- `0x1801f7864`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!SetServiceObjectSecurity` at `0x1801734a1`
- `ADVAPI32!SetServiceObjectSecurity` at `0x1801734a1`
- `ADVAPI32!ChangeServiceConfigW` at `0x1801730b0`
- `ADVAPI32!ChangeServiceConfigW` at `0x1801730b0`
- `ADVAPI32!CreateServiceW` at `0x180172ee7`
- `ADVAPI32!CreateServiceW` at `0x180172ee7`
- `ADVAPI32!CloseServiceHandle` at `0x1801730c3`
- `ADVAPI32!CloseServiceHandle` at `0x180173423`
- `ADVAPI32!CloseServiceHandle` at `0x1801734ec`
- `ADVAPI32!CloseServiceHandle` at `0x18017372d`
- `ADVAPI32!CloseServiceHandle` at `0x1801730c3`
- `ADVAPI32!CloseServiceHandle` at `0x180173423`
- `ADVAPI32!CloseServiceHandle` at `0x1801734ec`
- `ADVAPI32!CloseServiceHandle` at `0x18017372d`
- `ADVAPI32!OpenSCManagerW` at `0x180172cf7`
- `ADVAPI32!OpenSCManagerW` at `0x180172cf7`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x1801733cd`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x1801733cd`
- `KERNEL32!GetLastError` at `0x180172f41`
- `KERNEL32!GetLastError` at `0x180173154`
- `KERNEL32!GetLastError` at `0x180173506`
- `KERNEL32!GetLastError` at `0x180173685`
- `KERNEL32!GetLastError` at `0x1801736d7`
- `KERNEL32!GetLastError` at `0x180172f41`
- `KERNEL32!GetLastError` at `0x180173154`
- `KERNEL32!GetLastError` at `0x180173506`
- `KERNEL32!GetLastError` at `0x180173685`
- `KERNEL32!GetLastError` at `0x1801736d7`

## string_xrefs

- `0x1801735c7`: `ServiceInstall`
- `0x180172cee`: `ServicesActive`
- `0x180172c2d`: `System\CurrentControlSet\Services\`

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
  struct SC_HANDLE__ *ServiceHandle; // r14
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
  WCHAR *v35; // r14
  DWORD v36; // eax
  MsiUIMessageContext *v37; // rcx
  CMsiOpExecute *v38; // rcx
  const WCHAR *v39; // rax
  __int64 v40; // rcx
  const WCHAR *v41; // rax
  __int64 v42; // rcx
  __int64 v43; // r13
  const WCHAR *v44; // r12
  __int64 v45; // r15
  __int64 v46; // r14
  DWORD v47; // ebx
  DWORD v48; // eax
  DWORD v49; // r15d
  __int64 v50; // rbx
  const wchar_t *v51; // r15
  const wchar_t *v52; // rax
  DWORD LastError; // eax
  __int64 *v54; // rcx
  __int64 v55; // r9
  __int64 v56; // rcx
  struct IMsiRecord *v57; // rbx
  __int64 v58; // r9
  int v59; // eax
  __int64 v60; // r8
  const struct IMsiString *v61; // rbx
  struct IMsiStream **v62; // rax
  __int64 v63; // rax
  int v64; // eax
  unsigned int v65; // ebx
  unsigned int SecurityInformation; // eax
  bool v67; // zf
  char v68; // bl
  __int64 v69; // rdx
  char v70; // al
  int v71; // ecx
  __int64 v72; // rdx
  char v73; // al
  int v74; // edx
  const struct IMsiString **v75; // rax
  WCHAR *v76; // rbx
  BOOL v77; // ebx
  unsigned int v78; // ebx
  int v79; // eax
  MsiString *v80; // rax
  __int64 v81; // rbx
  DWORD v82; // eax
  __int64 v83; // rdx
  __int64 v84; // rbx
  DWORD v85; // eax
  __int64 v86; // rdx
  const WCHAR *dwServiceType; // [rsp+20h] [rbp-E0h]
  const WCHAR *dwStartType; // [rsp+28h] [rbp-D8h]
  const WCHAR *lpLoadOrderGroup; // [rsp+40h] [rbp-C0h]
  bool v90; // [rsp+70h] [rbp-90h]
  int v91; // [rsp+74h] [rbp-8Ch] BYREF
  LPCWSTR lpDependencies; // [rsp+78h] [rbp-88h] BYREF
  DWORD dwErrorControl; // [rsp+80h] [rbp-80h]
  int v94; // [rsp+84h] [rbp-7Ch] BYREF
  __int64 *v95; // [rsp+88h] [rbp-78h]
  __int64 v96; // [rsp+90h] [rbp-70h] BYREF
  __int64 v97; // [rsp+98h] [rbp-68h] BYREF
  struct IMsiString *v98; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v99; // [rsp+A8h] [rbp-58h] BYREF
  LPCWSTR lpPassword; // [rsp+B0h] [rbp-50h]
  CMsiOpExecute *v101; // [rsp+B8h] [rbp-48h]
  __int64 v102; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v103; // [rsp+C8h] [rbp-38h] BYREF
  int v104; // [rsp+D0h] [rbp-30h]
  int v105; // [rsp+D4h] [rbp-2Ch] BYREF
  __int64 v106; // [rsp+D8h] [rbp-28h] BYREF
  struct IMsiRecord *SharedRecord; // [rsp+E0h] [rbp-20h]
  LPCWSTR lpServiceStartName; // [rsp+E8h] [rbp-18h]
  _BYTE v109[8]; // [rsp+F0h] [rbp-10h] BYREF
  SC_HANDLE hSCManager; // [rsp+F8h] [rbp-8h]
  __int64 v111; // [rsp+100h] [rbp+0h] BYREF
  LPCWSTR lpDisplayName; // [rsp+108h] [rbp+8h]
  LPCWSTR v113; // [rsp+110h] [rbp+10h]
  const wchar_t *v114; // [rsp+118h] [rbp+18h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+120h] [rbp+20h] BYREF
  int v116; // [rsp+128h] [rbp+28h]
  _BYTE v117[512]; // [rsp+130h] [rbp+30h] BYREF

  v2 = *a2;
  v95 = a2;
  v4 = a1;
  v101 = a1;
  v5 = (struct IMsiString *)(*(__int64 (__fastcall **)(__int64 *, __int64))(v2 + 72))(a2, 1);
  v98 = v5;
  v6 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*a2 + 72))(a2, 2);
  v7 = *(_QWORD *)v4;
  v8 = v6;
  v105 = 0;
  v103 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 48LL))(v7, 1);
  (*(void (__fastcall **)(__int64, __int64, struct IMsiString *))(*(_QWORD *)v103 + 120LL))(v103, 1, v5);
  if ( (unsigned int)CMsiOpExecute::Message(v4, 150994944, v103) == 2 )
  {
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v103);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v5 + 16LL))(v5);
    return 2;
  }
  v102 = 0;
  MsiString::MsiString((MsiString *)&v99, L"System\\CurrentControlSet\\Services\\");
  MsiString::operator+=(&v99, &v98);
  v10 = *(_QWORD *)v4;
  v96 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v10 + 192LL))(v10, 2147483650LL, 0xFFFFFFFFLL);
  if ( !*(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v96, v11)
    || (v12 = v96,
        v13 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v96 + 112LL),
        v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v99 + 80LL))(v99),
        v15 = v13(v12, v14, 0, 0xFFFFFFFFLL),
        !*(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v96, v15)) )
  {
    CMsiOpExecute::Message(v4, 0x1000000, &off_18030FDB0);
    goto LABEL_91;
  }
  v16 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v96 + 88LL))(v96, &v105);
  CComPointer<IMsiDatabase>::operator=(&v102, v16);
  hSCManager = OpenSCManagerW(0, L"ServicesActive", 0xF003Fu);
  if ( hSCManager )
  {
    v17 = v95;
    v18 = 3;
    v19 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v95 + 56))(v95, 6);
    dwErrorControl = v19;
    if ( (v19 & 0x8000) != 0 )
    {
      v104 = 1;
      dwErrorControl = v19 - 0x8000;
    }
    else
    {
      v104 = 0;
    }
    v20 = *v95;
    v21 = 1;
    v91 = 1;
    lpServiceStartName = (LPCWSTR)(*(__int64 (__fastcall **)(__int64 *, __int64))(v20 + 80))(v95, 10);
    while ( 1 )
    {
      if ( !v21 )
      {
        CloseServiceHandle(hSCManager);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v96);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v102);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v103);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v5 + 16LL))(v5);
        return v18;
      }
      ++HIDWORD(qword_1803136AC);
      v22 = (const struct IMsiString **)MsiString::MsiString((MsiString *)&v111, &Default);
      ServiceHandle = GetServiceHandle(*v22, v5, 0xE0007u);
      lpPassword = (LPCWSTR)ServiceHandle;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
      v90 = 1;
      SharedRecord = 0;
      if ( !ServiceHandle )
        break;
      v94 = 1;
      lpDependencies = (LPCWSTR)((char *)v4 + 32);
      if ( *((_QWORD *)v4 + 4) )
      {
        SharedRecord = CMsiOpExecute::GetSharedRecord(v4, 14);
        v90 = CMsiOpExecute::RollbackServiceConfiguration(v38, ServiceHandle, v5, SharedRecord);
      }
      v39 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 80LL))(v8);
      v40 = *v17;
      lpDisplayName = v39;
      v41 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64 *, __int64))(v40 + 80))(v17, 11);
      v42 = *v17;
      v113 = v41;
      v43 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v42 + 80))(v17, 10);
      v44 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64 *, __int64))(*v17 + 80))(v17, 8);
      v45 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v17 + 80))(v17, 7);
      v46 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v17 + 80))(v17, 3);
      v47 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v17 + 56))(v17, 5);
      v48 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v95 + 56))(v95, 4);
      lpLoadOrderGroup = (const WCHAR *)v43;
      v21 = 0;
      dwStartType = (const WCHAR *)v45;
      v49 = dwErrorControl;
      dwServiceType = (const WCHAR *)v46;
      v35 = (WCHAR *)lpPassword;
      if ( ChangeServiceConfigW(
             (SC_HANDLE)lpPassword,
             v48,
             v47,
             dwErrorControl,
             dwServiceType,
             dwStartType,
             0,
             v44,
             lpLoadOrderGroup,
             v113,
             lpDisplayName) )
      {
        v50 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v95 + 72))(v95, 12);
        v51 = 0;
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v50 + 56LL))(v50) )
        {
          v52 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v50 + 80LL))(v50);
          v51 = &Default;
          if ( *v52 )
            v51 = v52;
        }
        v114 = v51;
        if ( (unsigned int)((__int64 (__fastcall *)(WCHAR *, __int64, const wchar_t **))ADVAPI32::ChangeServiceConfig2W)(
                             v35,
                             1,
                             &v114) )
        {
          v4 = v101;
        }
        else
        {
          LastError = GetLastError();
          v4 = v101;
          if ( LastError != 1 )
            CMsiOpExecute::DispatchError(v101, 0x4000000, 1930, v8, v98);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
        v37 = (MsiUIMessageContext *)lpDependencies;
        goto LABEL_31;
      }
      CloseServiceHandle((SC_HANDLE)v35);
      v37 = (MsiUIMessageContext *)lpDependencies;
      v35 = 0;
      v4 = v101;
      lpPassword = 0;
LABEL_32:
      MsiUIMessageContext::EnableTimeout(v37);
      if ( v35 )
      {
        v56 = *v54;
        v18 = 1;
        if ( v56 )
        {
          if ( !v94 )
          {
            v57 = CMsiOpExecute::GetSharedRecord(v4, 5);
            (*(void (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)v57 + 96LL))(v57, 1);
            v5 = v98;
            (*(void (__fastcall **)(struct IMsiRecord *, __int64, struct IMsiString *))(*(_QWORD *)v57 + 120LL))(
              v57,
              2,
              v98);
            (*(void (__fastcall **)(struct IMsiRecord *, __int64, __int64))(*(_QWORD *)v57 + 104LL))(v57, 3, 8);
            (*(void (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)v57 + 96LL))(v57, 4);
            (*(void (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)v57 + 96LL))(v57, 5);
            LOBYTE(v58) = 1;
            v18 = 2
                * ((unsigned __int8)WriteScriptRecord(*(_QWORD *)lpDependencies, 77, v57, v58, *((_QWORD *)v4 + 2)) ^ 1)
                + 1;
            goto LABEL_40;
          }
          if ( v90 )
          {
            LOBYTE(v55) = 1;
            if ( !(unsigned __int8)WriteScriptRecord(v56, 78, SharedRecord, v55, *((_QWORD *)v4 + 2)) )
              v18 = 3;
          }
        }
        v5 = v98;
LABEL_40:
        v17 = v95;
        v97 = 0;
        v59 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v95 + 32))(v95, 14);
        v60 = *v17;
        if ( v59 )
        {
          if ( (*(unsigned int (__fastcall **)(__int64 *, __int64))(v60 + 32))(v17, 13) )
            goto LABEL_60;
          v63 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v17 + 64))(v17, 13);
          CComPointer<IMsiDatabase>::operator=(&v97, v63);
        }
        else
        {
          v61 = (const struct IMsiString *)(*(__int64 (__fastcall **)(__int64 *, __int64))(v60 + 72))(v17, 14);
          v62 = (struct IMsiStream **)CComPointer<IEnumMsiRecord>::operator=(&v97);
          if ( !GenerateSDFromSDDL(v61, v62) )
          {
            v80 = MsiString::MsiString((MsiString *)&v106, L"ServiceInstall");
            CMsiOpExecute::DispatchError(v4, 0x1000000, 1943, v61, v5, *(_QWORD *)v80);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
            (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v61 + 16LL))(v61);
            goto LABEL_83;
          }
          (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v61 + 16LL))(v61);
        }
        memset_0(v117, 0, sizeof(v117));
        pSecurityDescriptor = v117;
        v116 = 512;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 112LL))(v97);
        v64 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v97 + 32LL))(v97);
        v65 = v64;
        if ( v64 > 512 )
          CTempBuffer<char,512>::SetSize(&pSecurityDescriptor, (unsigned int)v64);
        if ( !pSecurityDescriptor )
        {
          CMsiOpExecute::DispatchError(v4, 0x1000000, 2402);
          goto LABEL_87;
        }
        (*(void (__fastcall **)(__int64, PSECURITY_DESCRIPTOR, _QWORD))(*(_QWORD *)v97 + 64LL))(
          v97,
          pSecurityDescriptor,
          v65);
        IsValidSecurityDescriptor(pSecurityDescriptor);
        SecurityInformation = GetSecurityInformation(pSecurityDescriptor);
        v67 = *((_DWORD *)v4 + 125) == 2;
        v68 = SecurityInformation;
        LODWORD(lpDependencies) = SecurityInformation;
        CElevate::CElevate((CElevate *)v109, v67);
        LOBYTE(v69) = 1;
        v70 = RefCountedTokenPrivilegesCore(1, v69);
        v71 = 2;
        if ( v70 )
          v71 = 1;
        v91 = v71;
        if ( (v68 & 8) != 0 )
        {
          CloseServiceHandle((SC_HANDLE)lpPassword);
          LOBYTE(v72) = 1;
          v73 = RefCountedTokenPrivilegesCore(0, v72);
          v74 = 2;
          if ( v73 )
            v74 = 0;
          v94 = v74;
          v75 = (const struct IMsiString **)MsiString::MsiString((MsiString *)&v106, &Default);
          v76 = (WCHAR *)GetServiceHandle(*v75, v5, 0x10C0000u);
          lpPassword = v76;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
          if ( !v76 )
          {
            v81 = (*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)v5 + 80LL))(v5);
            v82 = GetLastError();
            CMsiOpExecute::DispatchError(v4, v83, 1944, v82, v81);
            CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges((CRefCountedTokenPrivileges *)&v94);
            CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges((CRefCountedTokenPrivileges *)&v91);
            CElevate::~CElevate((CElevate *)v109);
LABEL_87:
            if ( v116 > 512 )
              operator delete(pSecurityDescriptor);
LABEL_83:
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v97);
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v96);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v102);
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v103);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
            (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v5 + 16LL))(v5);
            return 3;
          }
          CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges((CRefCountedTokenPrivileges *)&v94);
        }
        else
        {
          v76 = (WCHAR *)lpPassword;
        }
        v77 = SetServiceObjectSecurity((SC_HANDLE)v76, (SECURITY_INFORMATION)lpDependencies, pSecurityDescriptor);
        CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges((CRefCountedTokenPrivileges *)&v91);
        CElevate::~CElevate((CElevate *)v109);
        if ( !v77 )
        {
          v84 = (*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)v5 + 80LL))(v5);
          v85 = GetLastError();
          CMsiOpExecute::DispatchError(v4, v86, 1944, v85, v84);
          goto LABEL_87;
        }
        if ( v116 > 512 )
          operator delete(pSecurityDescriptor);
        v17 = v95;
LABEL_60:
        v21 = 0;
        v91 = 0;
        CloseServiceHandle((SC_HANDLE)lpPassword);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v97);
      }
      else
      {
        GetLastError();
        if ( !lpServiceStartName || *((_DWORD *)v4 + 10) != 2 )
        {
          if ( v104 )
            goto LABEL_67;
          if ( v49 )
          {
            if ( v49 == 1 )
            {
              v78 = 16777730;
              goto LABEL_70;
            }
            if ( v49 - 2 <= 1 )
            {
LABEL_67:
              v78 = 16777221;
              goto LABEL_70;
            }
          }
        }
        v78 = 0x4000000;
LABEL_70:
        v5 = v98;
        v79 = CMsiOpExecute::DispatchError(v4, v78, 1923, v8, v98);
        if ( v79 == 4 )
        {
          v21 = v91;
LABEL_80:
          v18 = 3;
          goto LABEL_81;
        }
        v91 = 0;
        if ( v79 == 5 )
        {
          v21 = 0;
          v18 = 1;
          v91 = 0;
          goto LABEL_81;
        }
        if ( v79 )
          goto LABEL_80;
        if ( v78 == 0x4000000 )
        {
          v18 = 1;
        }
        else
        {
          v18 = 3;
          if ( (v78 & 0x202) == 0x202 )
            v18 = 1;
        }
LABEL_81:
        v17 = v95;
      }
    }
    v94 = 0;
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
    v33 = (const WCHAR *)(*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)v98 + 80LL))(v98);
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
    v35 = (WCHAR *)ServiceW;
    if ( !ServiceW
      || (lpDependencies = 0,
          lpDependencies = (LPCWSTR)(*(__int64 (__fastcall **)(__int64 *, __int64))(*v95 + 80))(v95, 12),
          (unsigned int)((__int64 (__fastcall *)(WCHAR *, __int64, LPCWSTR *))ADVAPI32::ChangeServiceConfig2W)(
                          v35,
                          1,
                          &lpDependencies)) )
    {
      v4 = v101;
    }
    else
    {
      v36 = GetLastError();
      v4 = v101;
      if ( v36 != 1 )
        CMsiOpExecute::DispatchError(v101, 0x4000000, 1930, v8, v98);
    }
    v37 = (CMsiOpExecute *)((char *)v4 + 32);
LABEL_31:
    v49 = dwErrorControl;
    lpDependencies = (LPCWSTR)v37;
    goto LABEL_32;
  }
  CMsiOpExecute::DispatchError(v4, 0x1000000, 1923, v8, v5);
LABEL_91:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v96);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v102);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v103);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v5 + 16LL))(v5);
  return 3;
}

```

## disassembly

```asm
0x180172b40  mov     [rsp-8+arg_10], rbx
0x180172b45  push    rbp
0x180172b46  push    rsi
0x180172b47  push    rdi
0x180172b48  push    r12
0x180172b4a  push    r13
0x180172b4c  push    r14
0x180172b4e  push    r15
0x180172b50  lea     rbp, [rsp-240h]
0x180172b58  sub     rsp, 340h
0x180172b5f  mov     rax, cs:__security_cookie
0x180172b66  xor     rax, rsp
0x180172b69  mov     [rbp+270h+var_40], rax
0x180172b70  mov     rax, [rdx]
0x180172b73  mov     rbx, rdx
0x180172b76  mov     [rbp+270h+var_2E8], rdx
0x180172b7a  mov     r12, rcx
0x180172b7d  mov     [rbp+270h+var_2B8], rcx
0x180172b81  mov     r14d, 1
0x180172b87  mov     edx, r14d
0x180172b8a  mov     rcx, rbx
0x180172b8d  mov     rax, [rax+48h]
0x180172b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172b96  mov     r15, rax
0x180172b99  mov     [rbp+270h+var_2D0], rax
0x180172b9d  mov     rax, [rbx]
0x180172ba0  lea     esi, [r14+1]
0x180172ba4  mov     edx, esi
0x180172ba6  mov     rcx, rbx
0x180172ba9  mov     rax, [rax+48h]
0x180172bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172bb2  mov     rcx, [r12]
0x180172bb6  mov     rdi, rax
0x180172bb9  xor     r13d, r13d
0x180172bbc  mov     edx, r14d
0x180172bbf  mov     [rbp+270h+var_29C], r13d
0x180172bc3  mov     rax, [rcx]
0x180172bc6  mov     rax, [rax+30h]
0x180172bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172bcf  mov     rbx, rax
0x180172bd2  mov     [rbp+270h+var_2A8], rax
0x180172bd6  mov     r8, r15
0x180172bd9  mov     edx, r14d
0x180172bdc  mov     rcx, rbx
0x180172bdf  mov     rax, [rax]
0x180172be2  mov     rax, [rax+78h]
0x180172be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172beb  mov     r8, rbx
0x180172bee  mov     edx, 9000000h
0x180172bf3  mov     rcx, r12
0x180172bf6  call    ?Message@CMsiOpExecute@@IEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::Message(imtEnum,IMsiRecord &)
0x180172bfb  cmp     eax, esi
0x180172bfd  jnz     short loc_180172C2D
0x180172bff  lea     rcx, [rbp+270h+var_2A8]
0x180172c03  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x180172c08  mov     rax, [rdi]
0x180172c0b  mov     rcx, rdi
0x180172c0e  mov     rax, [rax+10h]
0x180172c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172c17  mov     rax, [r15]
0x180172c1a  mov     rcx, r15
0x180172c1d  mov     rax, [rax+10h]
0x180172c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172c26  mov     eax, esi
0x180172c28  jmp     loc_1801737E9
0x180172c2d  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\"
0x180172c34  mov     [rbp+270h+var_2B0], r13
0x180172c38  lea     rcx, [rbp+270h+var_2C8]; this
0x180172c3c  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x180172c41  lea     rdx, [rbp+270h+var_2D0]
0x180172c45  lea     rcx, [rbp+270h+var_2C8]
0x180172c49  call    ??YMsiString@@QEAAAEAV0@AEBV0@@Z; MsiString::operator+=(MsiString const &)
0x180172c4e  mov     rcx, [r12]
0x180172c52  or      r8d, 0FFFFFFFFh
0x180172c56  mov     [rbp+270h+var_2E0], r13
0x180172c5a  mov     edx, 80000002h
0x180172c5f  mov     rax, [rcx]
0x180172c62  mov     rax, [rax+0C0h]
0x180172c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172c6e  mov     rdx, rax
0x180172c71  lea     rcx, [rbp+270h+var_2E0]
0x180172c75  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x180172c7a  cmp     [rax], r13
0x180172c7d  jz      loc_180173787
0x180172c83  mov     r14, [rbp+270h+var_2E0]
0x180172c87  mov     rcx, [rbp+270h+var_2C8]
0x180172c8b  mov     rax, [r14]
0x180172c8e  mov     rdx, [rcx]
0x180172c91  mov     rbx, [rax+70h]
0x180172c95  mov     rax, [rdx+50h]
0x180172c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172c9e  mov     rdx, rax
0x180172ca1  or      r9d, 0FFFFFFFFh
0x180172ca5  mov     rax, rbx
0x180172ca8  xor     r8d, r8d
0x180172cab  mov     rcx, r14
0x180172cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172cb3  mov     rdx, rax
0x180172cb6  lea     rcx, [rbp+270h+var_2E0]
0x180172cba  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x180172cbf  cmp     [rax], r13
0x180172cc2  jz      loc_180173787
0x180172cc8  mov     rcx, [rbp+270h+var_2E0]
0x180172ccc  lea     rdx, [rbp+270h+var_29C]
0x180172cd0  mov     rax, [rcx]
0x180172cd3  mov     rax, [rax+58h]
0x180172cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172cdc  mov     rdx, rax
0x180172cdf  lea     rcx, [rbp+270h+var_2B0]
0x180172ce3  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x180172ce8  mov     r8d, 0F003Fh; dwDesiredAccess
0x180172cee  lea     rdx, DatabaseName; "ServicesActive"
0x180172cf5  xor     ecx, ecx; lpMachineName
0x180172cf7  call    cs:__imp_OpenSCManagerW
0x180172cfe  nop     dword ptr [rax+rax+00h]
0x180172d03  mov     [rbp+270h+hSCManager], rax
0x180172d07  test    rax, rax
0x180172d0a  jnz     short loc_180172D2C
0x180172d0c  mov     r9, rdi
0x180172d0f  mov     qword ptr [rsp+370h+dwServiceType], r15
0x180172d14  mov     edx, 1000000h
0x180172d19  mov     r8d, 783h
0x180172d1f  mov     rcx, r12
0x180172d22  call    ?DispatchError@CMsiOpExecute@@QEAA?AW4imsEnum@@W4imtEnum@@HAEBVIMsiString@@1@Z; CMsiOpExecute::DispatchError(imtEnum,int,IMsiString const &,IMsiString const &)
0x180172d27  jmp     loc_18017379B
0x180172d2c  mov     rbx, [rbp+270h+var_2E8]
0x180172d30  mov     r14d, 3
0x180172d36  mov     rcx, rbx
0x180172d39  mov     rax, [rbx]
0x180172d3c  lea     edx, [r14+3]
0x180172d40  mov     rax, [rax+38h]
0x180172d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172d49  mov     [rbp+270h+var_2F0], eax
0x180172d4c  lea     edx, [r14-2]
0x180172d50  bt      eax, 0Fh
0x180172d54  jnb     short loc_180172D63
0x180172d56  add     eax, 0FFFF8000h
0x180172d5b  mov     [rbp+270h+var_2A0], edx
0x180172d5e  mov     [rbp+270h+var_2F0], eax
0x180172d61  jmp     short loc_180172D67
0x180172d63  mov     [rbp+270h+var_2A0], r13d
0x180172d67  mov     rax, [rbx]
0x180172d6a  mov     r13d, edx
0x180172d6d  mov     [rsp+370h+var_2FC], edx
0x180172d71  mov     rcx, rbx
0x180172d74  mov     edx, 0Ah
0x180172d79  mov     rax, [rax+50h]
0x180172d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172d82  mov     [rbp+270h+var_288], rax
0x180172d86  test    r13d, r13d
0x180172d89  jz      loc_180173729
0x180172d8f  mov     r13d, 1
0x180172d95  lea     rdx, Default; unsigned __int16 *
0x180172d9c  add     dword ptr cs:qword_1803136AC+4, r13d
0x180172da3  lea     rcx, [rbp+270h+var_270]; this
0x180172da7  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x180172dac  mov     r8d, 0E0007h; unsigned int
0x180172db2  mov     rdx, r15; struct IMsiString *
0x180172db5  mov     rcx, [rax]; struct IMsiString *
0x180172db8  call    ?GetServiceHandle@@YAPEAUSC_HANDLE__@@AEBVIMsiString@@0K@Z; GetServiceHandle(IMsiString const &,IMsiString const &,ulong)
0x180172dbd  mov     rcx, [rbp+270h+var_270]
0x180172dc1  mov     r14, rax
0x180172dc4  mov     [rbp+270h+var_2C0], rax
0x180172dc8  mov     rdx, [rcx]
0x180172dcb  mov     rax, [rdx+10h]
0x180172dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172dd4  xor     eax, eax
0x180172dd6  mov     [rsp+370h+var_300], r13b
0x180172ddb  mov     [rbp+270h+var_290], rax
0x180172ddf  test    r14, r14
0x180172de2  jnz     loc_180172F84
0x180172de8  mov     [rbp+270h+var_2EC], eax
0x180172deb  lea     edx, [r13+0Ah]
0x180172def  mov     rax, [rbx]
0x180172df2  mov     rcx, rbx
0x180172df5  mov     rax, [rax+50h]
0x180172df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172dfe  mov     rcx, [rbx]
0x180172e01  lea     edx, [r13+7]
0x180172e05  mov     [rbp+270h+var_2C0], rax
0x180172e09  mov     rax, [rcx+50h]
0x180172e0d  mov     rcx, rbx
0x180172e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172e15  mov     rcx, [rbx]
0x180172e18  lea     edx, [r13+6]
0x180172e1c  mov     [rsp+370h+var_2F8], rax
0x180172e21  mov     rax, [rcx+50h]
0x180172e25  mov     rcx, rbx
0x180172e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172e2d  mov     rcx, [rbx]
0x180172e30  lea     edx, [r14+3]
0x180172e34  mov     r13, rax
0x180172e37  mov     rax, [rcx+50h]
0x180172e3b  mov     rcx, rbx
0x180172e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172e43  mov     rcx, [rbx]
0x180172e46  lea     edx, [r14+5]
0x180172e4a  mov     r12, rax
0x180172e4d  mov     rax, [rcx+38h]
0x180172e51  mov     rcx, rbx
0x180172e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172e59  mov     rcx, [rbx]
0x180172e5c  lea     edx, [r14+4]
0x180172e60  mov     r15d, eax
0x180172e63  mov     rax, [rcx+38h]
0x180172e67  mov     rcx, rbx
0x180172e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172e6f  mov     rcx, [rdi]
0x180172e72  mov     r14d, eax
0x180172e75  mov     rax, [rcx+50h]
0x180172e79  mov     rcx, rdi
0x180172e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172e81  mov     rdx, [rbp+270h+var_2D0]
0x180172e85  mov     rbx, rax
0x180172e88  mov     rcx, [rdx]
0x180172e8b  mov     rax, [rcx+50h]
0x180172e8f  mov     rcx, rdx
0x180172e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172e97  mov     rcx, [rbp+270h+var_2C0]
0x180172e9b  mov     r9d, 0F0002h; dwDesiredAccess
0x180172ea1  mov     [rsp+370h+lpPassword], rcx; lpPassword
0x180172ea6  mov     r8, rbx; lpDisplayName
0x180172ea9  mov     rcx, [rbp+270h+var_288]
0x180172ead  mov     rdx, rax; lpServiceName
0x180172eb0  mov     [rsp+370h+lpServiceStartName], rcx; lpServiceStartName
0x180172eb5  mov     rcx, [rsp+370h+var_2F8]
0x180172eba  mov     [rsp+370h+lpDependencies], rcx; lpDependencies
0x180172ebf  mov     ecx, [rbp+270h+var_2F0]
0x180172ec2  mov     [rsp+370h+lpdwTagId], 0; lpdwTagId
0x180172ecb  mov     [rsp+370h+lpLoadOrderGroup], r13; lpLoadOrderGroup
0x180172ed0  mov     [rsp+370h+lpBinaryPathName], r12; lpBinaryPathName
0x180172ed5  mov     [rsp+370h+dwErrorControl], ecx; dwErrorControl
0x180172ed9  mov     rcx, [rbp+270h+hSCManager]; hSCManager
0x180172edd  mov     [rsp+370h+dwStartType], r15d; dwStartType
0x180172ee2  mov     [rsp+370h+dwServiceType], r14d; dwServiceType
0x180172ee7  call    cs:__imp_CreateServiceW
0x180172eee  nop     dword ptr [rax+rax+00h]
0x180172ef3  xor     r13d, r13d
0x180172ef6  mov     [rbp+270h+var_2C0], rax
0x180172efa  mov     r14, rax
0x180172efd  test    rax, rax
0x180172f00  jz      short loc_180172F76
0x180172f02  mov     r8, [rbp+270h+var_2E8]
0x180172f06  lea     edx, [r13+0Ch]
0x180172f0a  mov     rcx, r8
0x180172f0d  mov     [rsp+370h+var_2F8], r13
0x180172f12  mov     rax, [r8]
0x180172f15  mov     rax, [rax+50h]
0x180172f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172f1e  mov     [rsp+370h+var_2F8], rax
0x180172f23  lea     ebx, [r13+1]
0x180172f27  mov     rax, cs:?ChangeServiceConfig2W@ADVAPI32@@3P6AHPEAUSC_HANDLE__@@KPEAX@ZEA; int (*ADVAPI32::ChangeServiceConfig2W)(SC_HANDLE__ *,ulong,void *)
0x180172f2e  lea     r8, [rsp+370h+var_2F8]
0x180172f33  mov     edx, ebx
0x180172f35  mov     rcx, r14
0x180172f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172f3d  test    eax, eax
0x180172f3f  jnz     short loc_180172F76
0x180172f41  call    cs:__imp_GetLastError
0x180172f48  nop     dword ptr [rax+rax+00h]
0x180172f4d  mov     r12, [rbp+270h+var_2B8]
0x180172f51  cmp     eax, ebx
0x180172f53  jz      short loc_180172F7A
0x180172f55  mov     rax, [rbp+270h+var_2D0]
0x180172f59  mov     r9, rdi
0x180172f5c  mov     edx, 4000000h
0x180172f61  mov     qword ptr [rsp+370h+dwServiceType], rax
0x180172f66  mov     r8d, 78Ah
0x180172f6c  mov     rcx, r12
0x180172f6f  call    ?DispatchError@CMsiOpExecute@@QEAA?AW4imsEnum@@W4imtEnum@@HAEBVIMsiString@@1@Z; CMsiOpExecute::DispatchError(imtEnum,int,IMsiString const &,IMsiString const &)
0x180172f74  jmp     short loc_180172F7A
0x180172f76  mov     r12, [rbp+270h+var_2B8]
0x180172f7a  lea     rcx, [r12+20h]
0x180172f7f  jmp     loc_1801731A2
0x180172f84  lea     rcx, [r12+20h]
0x180172f89  mov     [rbp+270h+var_2EC], r13d
0x180172f8d  mov     [rsp+370h+var_2F8], rcx
0x180172f92  cmp     [rcx], rax
0x180172f95  jz      short loc_180172FBA
0x180172f97  mov     edx, 0Eh; int
0x180172f9c  mov     rcx, r12; this
0x180172f9f  call    ?GetSharedRecord@CMsiOpExecute@@IEAAAEAVIMsiRecord@@H@Z; CMsiOpExecute::GetSharedRecord(int)
0x180172fa4  mov     r9, rax; struct IMsiRecord *
0x180172fa7  mov     [rbp+270h+var_290], rax
0x180172fab  mov     r8, r15; struct IMsiString *
0x180172fae  mov     rdx, r14; struct SC_HANDLE__ *
0x180172fb1  call    ?RollbackServiceConfiguration@CMsiOpExecute@@IEAA_NQEAUSC_HANDLE__@@AEBVIMsiString@@AEAVIMsiRecord@@@Z; CMsiOpExecute::RollbackServiceConfiguration(SC_HANDLE__ * const,IMsiString const &,IMsiRecord &)
0x180172fb6  mov     [rsp+370h+var_300], al
0x180172fba  mov     rcx, [rdi]
0x180172fbd  mov     rax, [rcx+50h]
0x180172fc1  mov     rcx, rdi
0x180172fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172fc9  mov     rcx, [rbx]
0x180172fcc  mov     edx, 0Bh
0x180172fd1  mov     [rbp+270h+lpDisplayName], rax
0x180172fd5  mov     rax, [rcx+50h]
0x180172fd9  mov     rcx, rbx
0x180172fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172fe1  mov     rcx, [rbx]
0x180172fe4  mov     edx, 0Ah
  ... truncated ...
```
