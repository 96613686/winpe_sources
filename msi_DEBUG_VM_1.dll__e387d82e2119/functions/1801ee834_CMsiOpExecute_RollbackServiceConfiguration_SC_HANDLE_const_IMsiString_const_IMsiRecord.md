# CMsiOpExecute::RollbackServiceConfiguration(SC_HANDLE__ * const,IMsiString const &,IMsiRecord &)

- ea: `0x1801ee834`
- end: `0x1801eedb3`
- name: `?RollbackServiceConfiguration@CMsiOpExecute@@IEAA_NQEAUSC_HANDLE__@@AEBVIMsiString@@AEAVIMsiRecord@@@Z`
- size: `1407`
- prototype: `bool(CMsiOpExecute *__hidden this, struct SC_HANDLE__ *const, const struct IMsiString *, struct IMsiRecord *)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18016ca80`
- `0x1801de0a0`

## callees

- `0x180025904`
- `0x180025a18`
- `0x180035a8c`
- `0x18004295c`
- `0x180066074`
- `0x180068680`
- `0x18007ccec`
- `0x18007d8cc`
- `0x1800a5fc4`
- `0x1800a6c24`
- `0x180144e34`
- `0x1801e0d78`
- `0x1801ee834`
- `0x18025ab12`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!QueryServiceConfigW` at `0x1801ee8a2`
- `ADVAPI32!QueryServiceConfigW` at `0x1801ee8fc`
- `ADVAPI32!QueryServiceConfigW` at `0x1801ee8a2`
- `ADVAPI32!QueryServiceConfigW` at `0x1801ee8fc`
- `KERNEL32!GetLastError` at `0x1801ee8b5`
- `KERNEL32!GetLastError` at `0x1801ee9b8`
- `KERNEL32!GetLastError` at `0x1801ee8b5`
- `KERNEL32!GetLastError` at `0x1801ee9b8`
- `KERNEL32!GlobalFree` at `0x1801eec6b`
- `KERNEL32!GlobalFree` at `0x1801eec8d`
- `KERNEL32!GlobalFree` at `0x1801eed5f`
- `KERNEL32!GlobalFree` at `0x1801eed81`
- `KERNEL32!GlobalFree` at `0x1801eec6b`
- `KERNEL32!GlobalFree` at `0x1801eec8d`
- `KERNEL32!GlobalFree` at `0x1801eed5f`
- `KERNEL32!GlobalFree` at `0x1801eed81`

## string_xrefs

- `0x1801ee92f`: `Service configuration for: %s is invalid. If the install is rolledback the service configuration might not be restored to its previous state.`

## pseudocode

```c
char __fastcall CMsiOpExecute::RollbackServiceConfiguration(
        CMsiOpExecute *this,
        struct SC_HANDLE__ *const a2,
        const struct IMsiString *a3,
        struct IMsiRecord *a4)
{
  DWORD LastError; // eax
  _QUERY_SERVICE_CONFIGW *p_ServiceConfig; // rsi
  const unsigned __int16 *v9; // rax
  DWORD v10; // eax
  _QWORD *v11; // r15
  _WORD *v12; // rcx
  __int64 v13; // rdx
  char v14; // al
  int v15; // r8d
  struct IMsiStream **v16; // rax
  CMsiOpExecute *v17; // rcx
  void (__fastcall *v18)(struct IMsiRecord *, __int64, _QWORD); // rdi
  MsiString *v19; // rax
  void (__fastcall *v20)(struct IMsiRecord *, __int64, _QWORD); // rbx
  MsiString *v21; // rax
  void (__fastcall *v22)(struct IMsiRecord *, __int64, _QWORD); // rbx
  MsiString *v23; // rax
  LPWSTR i; // rcx
  unsigned int v25; // ebx
  void *v26; // rax
  void (__fastcall *v28)(struct IMsiRecord *, __int64, _QWORD); // rbx
  MsiString *v29; // rax
  DWORD pcbBytesNeeded; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v31; // [rsp+64h] [rbp-9Ch] BYREF
  void *v32; // [rsp+68h] [rbp-98h] BYREF
  __int64 v33; // [rsp+70h] [rbp-90h] BYREF
  void *v34; // [rsp+78h] [rbp-88h] BYREF
  __int64 v35; // [rsp+80h] [rbp-80h] BYREF
  int v36; // [rsp+88h] [rbp-78h] BYREF
  HGLOBAL hMem; // [rsp+90h] [rbp-70h] BYREF
  int v38; // [rsp+98h] [rbp-68h]
  _BYTE v39[512]; // [rsp+A0h] [rbp-60h] BYREF
  LPQUERY_SERVICE_CONFIGW lpServiceConfig; // [rsp+2A0h] [rbp+1A0h] BYREF
  int v41; // [rsp+2A8h] [rbp+1A8h]
  _QUERY_SERVICE_CONFIGW ServiceConfig; // [rsp+2B0h] [rbp+1B0h] BYREF

  pcbBytesNeeded = 0;
  v41 = 512;
  lpServiceConfig = &ServiceConfig;
  if ( QueryServiceConfigW(a2, &ServiceConfig, 0x200u, &pcbBytesNeeded) )
  {
    p_ServiceConfig = &ServiceConfig;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 2 )
      goto LABEL_33;
    if ( LastError != 122 || pcbBytesNeeded <= 0x200 )
    {
      if ( g_dmDiagnosticMode )
      {
        v9 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)a3 + 80LL))(a3);
        DebugString(
          10,
          0,
          0,
          L"Service configuration for: %s is invalid. If the install is rolledback the service configuration might not be "
           "restored to its previous state.",
          v9,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
      goto LABEL_33;
    }
    if ( !(unsigned __int8)CAPITempBuffer<char,512>::SetSize(&lpServiceConfig, pcbBytesNeeded) )
    {
LABEL_33:
      if ( v41 > 512 )
        GlobalFree(lpServiceConfig);
      return 0;
    }
    p_ServiceConfig = lpServiceConfig;
    QueryServiceConfigW(a2, lpServiceConfig, pcbBytesNeeded, &pcbBytesNeeded);
  }
  v38 = 512;
  hMem = v39;
  v31 = 0;
  v32 = &MsiString::s_NullString;
  if ( (unsigned int)((__int64 (__fastcall *)(struct SC_HANDLE__ *const, __int64, _BYTE *, __int64, unsigned int *))ADVAPI32::QueryServiceConfig2W)(
                       a2,
                       1,
                       v39,
                       512,
                       &v31) )
  {
    v11 = v39;
  }
  else
  {
    v10 = GetLastError();
    if ( v10 == 1 )
      goto LABEL_21;
    if ( v10 == 2 )
      goto LABEL_30;
    if ( v31 <= 0x200 )
      goto LABEL_21;
    if ( !(unsigned __int8)CAPITempBuffer<char,512>::SetSize(&hMem, v31) )
      goto LABEL_30;
    v11 = hMem;
    if ( !(unsigned int)((__int64 (__fastcall *)(struct SC_HANDLE__ *const, __int64, HGLOBAL, _QWORD, unsigned int *))ADVAPI32::QueryServiceConfig2W)(
                          a2,
                          1,
                          hMem,
                          v31,
                          &v31) )
      goto LABEL_21;
  }
  MsiString::operator=(&v32, *v11);
  if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)v32 + 56LL))(v32) )
    goto LABEL_21;
  v12 = (_WORD *)MsiString::AllocateString(&v32, 1, 0);
  if ( !v12 )
  {
LABEL_30:
    (*(void (__fastcall **)(void *))(*(_QWORD *)v32 + 16LL))(v32);
    if ( v38 > 512 )
      GlobalFree(hMem);
    v38 = 512;
    hMem = v39;
    goto LABEL_33;
  }
  *v12 = 0;
LABEL_21:
  v35 = 0;
  CElevate::CElevate((CElevate *)&v33, 1);
  LOBYTE(v13) = 1;
  v14 = RefCountedTokenPrivilegesCore(0, v13);
  v15 = 2;
  if ( v14 )
    v15 = 0;
  v36 = v15;
  v16 = (struct IMsiStream **)CComPointer<IEnumMsiRecord>::operator=(&v35);
  CMsiOpExecute::GetSDFromService(v17, a2, v16);
  CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges((CRefCountedTokenPrivileges *)&v36);
  CElevate::~CElevate((CElevate *)&v33);
  (*(void (__fastcall **)(struct IMsiRecord *, __int64, const struct IMsiString *))(*(_QWORD *)a4 + 120LL))(a4, 1, a3);
  v18 = *(void (__fastcall **)(struct IMsiRecord *, __int64, _QWORD))(*(_QWORD *)a4 + 120LL);
  v19 = MsiString::MsiString((MsiString *)&v33, p_ServiceConfig->lpDisplayName);
  v18(a4, 2, *(_QWORD *)v19);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  v20 = *(void (__fastcall **)(struct IMsiRecord *, __int64, _QWORD))(*(_QWORD *)a4 + 120LL);
  v21 = MsiString::MsiString((MsiString *)&v33, p_ServiceConfig->lpBinaryPathName);
  v20(a4, 3, *(_QWORD *)v21);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  (*(void (__fastcall **)(struct IMsiRecord *, __int64, _QWORD))(*(_QWORD *)a4 + 104LL))(
    a4,
    4,
    p_ServiceConfig->dwServiceType);
  (*(void (__fastcall **)(struct IMsiRecord *, __int64, _QWORD))(*(_QWORD *)a4 + 104LL))(
    a4,
    5,
    p_ServiceConfig->dwStartType);
  (*(void (__fastcall **)(struct IMsiRecord *, __int64, _QWORD))(*(_QWORD *)a4 + 104LL))(
    a4,
    6,
    p_ServiceConfig->dwErrorControl);
  v22 = *(void (__fastcall **)(struct IMsiRecord *, __int64, _QWORD))(*(_QWORD *)a4 + 120LL);
  v23 = MsiString::MsiString((MsiString *)&v33, p_ServiceConfig->lpLoadOrderGroup);
  v22(a4, 7, *(_QWORD *)v23);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  (*(void (__fastcall **)(struct IMsiRecord *, __int64, void *))(*(_QWORD *)a4 + 120LL))(a4, 12, v32);
  (*(void (__fastcall **)(struct IMsiRecord *, __int64, __int64))(*(_QWORD *)a4 + 112LL))(a4, 13, v35);
  for ( i = p_ServiceConfig->lpDependencies; *i || i[1]; ++i )
    ;
  v34 = &MsiString::s_NullString;
  v25 = i - p_ServiceConfig->lpDependencies + 2;
  v26 = (void *)MsiString::AllocateString(&v34, v25, 1);
  if ( v25 && !v26 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)v34 + 16LL))(v34);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v35);
    goto LABEL_30;
  }
  memcpy_0(v26, p_ServiceConfig->lpDependencies, 2LL * v25);
  (*(void (__fastcall **)(struct IMsiRecord *, __int64, void *))(*(_QWORD *)a4 + 120LL))(a4, 8, v34);
  (*(void (__fastcall **)(struct IMsiRecord *, __int64, _QWORD))(*(_QWORD *)a4 + 104LL))(
    a4,
    9,
    p_ServiceConfig->dwTagId);
  v28 = *(void (__fastcall **)(struct IMsiRecord *, __int64, _QWORD))(*(_QWORD *)a4 + 120LL);
  v29 = MsiString::MsiString((MsiString *)&v33, p_ServiceConfig->lpServiceStartName);
  v28(a4, 10, *(_QWORD *)v29);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  (*(void (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)a4 + 96LL))(a4, 11);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v34 + 16LL))(v34);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v35);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v32 + 16LL))(v32);
  if ( v38 > 512 )
    GlobalFree(hMem);
  v38 = 512;
  hMem = v39;
  if ( v41 > 512 )
    GlobalFree(lpServiceConfig);
  return 1;
}

```

## disassembly

```asm
0x1801ee834  mov     [rsp-8+arg_0], rbx
0x1801ee839  push    rbp
0x1801ee83a  push    rsi
0x1801ee83b  push    rdi
0x1801ee83c  push    r12
0x1801ee83e  push    r13
0x1801ee840  push    r14
0x1801ee842  push    r15
0x1801ee844  lea     rbp, [rsp-3C0h]
0x1801ee84c  sub     rsp, 4C0h
0x1801ee853  mov     rax, cs:__security_cookie
0x1801ee85a  xor     rax, rsp
0x1801ee85d  mov     [rbp+3F0h+var_40], rax
0x1801ee864  mov     rdi, rdx
0x1801ee867  mov     [rsp+4F0h+pcbBytesNeeded], 0
0x1801ee86f  mov     r13d, 200h
0x1801ee875  lea     rax, [rbp+3F0h+ServiceConfig]
0x1801ee87c  mov     r14, r9
0x1801ee87f  mov     [rbp+3F0h+var_248], r13d
0x1801ee886  mov     r12, r8
0x1801ee889  mov     [rbp+3F0h+lpServiceConfig], rax
0x1801ee890  mov     r8d, r13d; cbBufSize
0x1801ee893  lea     r9, [rsp+4F0h+pcbBytesNeeded]; pcbBytesNeeded
0x1801ee898  mov     rcx, rdi; hService
0x1801ee89b  lea     rdx, [rbp+3F0h+ServiceConfig]; lpServiceConfig
0x1801ee8a2  call    cs:__imp_QueryServiceConfigW
0x1801ee8a8  mov     ebx, 2
0x1801ee8ad  test    eax, eax
0x1801ee8af  jnz     loc_1801EE968
0x1801ee8b5  call    cs:__imp_GetLastError
0x1801ee8bb  cmp     eax, ebx
0x1801ee8bd  jz      loc_1801EEC7D
0x1801ee8c3  cmp     eax, 7Ah ; 'z'
0x1801ee8c6  jnz     short loc_1801EE904
0x1801ee8c8  mov     edx, [rsp+4F0h+pcbBytesNeeded]
0x1801ee8cc  cmp     edx, r13d
0x1801ee8cf  jbe     short loc_1801EE904
0x1801ee8d1  lea     rcx, [rbp+3F0h+lpServiceConfig]
0x1801ee8d8  call    ?SetSize@?$CAPITempBuffer@D$0CAA@@@QEAA_NH_N@Z; CAPITempBuffer<char,512>::SetSize(int,bool)
0x1801ee8dd  test    al, al
0x1801ee8df  jz      loc_1801EEC7D
0x1801ee8e5  mov     rsi, [rbp+3F0h+lpServiceConfig]
0x1801ee8ec  lea     r9, [rsp+4F0h+pcbBytesNeeded]; pcbBytesNeeded
0x1801ee8f1  mov     r8d, [rsp+4F0h+pcbBytesNeeded]; cbBufSize
0x1801ee8f6  mov     rdx, rsi; lpServiceConfig
0x1801ee8f9  mov     rcx, rdi; hService
0x1801ee8fc  call    cs:__imp_QueryServiceConfigW
0x1801ee902  jmp     short loc_1801EE96F
0x1801ee904  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x1801ee90b  jz      loc_1801EEC7D
0x1801ee911  mov     rax, [r12]
0x1801ee915  mov     rcx, r12
0x1801ee918  mov     rax, [rax+50h]
0x1801ee91c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ee921  lea     rcx, aNull; "(NULL)"
0x1801ee928  xor     edx, edx; unsigned __int16
0x1801ee92a  mov     [rsp+4F0h+var_498], rdx; void *
0x1801ee92f  lea     r9, aServiceConfigu; "Service configuration for: %s is invali"...
0x1801ee936  mov     [rsp+4F0h+var_4A0], edx; unsigned int
0x1801ee93a  xor     r8d, r8d; int
0x1801ee93d  mov     [rsp+4F0h+var_4A8], rcx; unsigned __int16 *
0x1801ee942  mov     [rsp+4F0h+var_4B0], rcx; unsigned __int16 *
0x1801ee947  mov     [rsp+4F0h+var_4B8], rcx; unsigned __int16 *
0x1801ee94c  mov     [rsp+4F0h+var_4C0], rcx; unsigned __int16 *
0x1801ee951  mov     [rsp+4F0h+var_4C8], rcx; unsigned __int16 *
0x1801ee956  lea     ecx, [rdx+0Ah]; int
0x1801ee959  mov     [rsp+4F0h+var_4D0], rax; unsigned __int16 *
0x1801ee95e  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801ee963  jmp     loc_1801EEC7D
0x1801ee968  lea     rsi, [rbp+3F0h+ServiceConfig]
0x1801ee96f  lea     rax, [rbp+3F0h+var_450]
0x1801ee973  mov     [rbp+3F0h+var_458], r13d
0x1801ee977  mov     [rbp+3F0h+hMem], rax
0x1801ee97b  lea     r15, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801ee982  lea     rax, [rsp+4F0h+var_48C]
0x1801ee987  mov     [rsp+4F0h+var_48C], 0
0x1801ee98f  mov     [rsp+4F0h+var_4D0], rax
0x1801ee994  lea     r8, [rbp+3F0h+var_450]
0x1801ee998  mov     rax, cs:?QueryServiceConfig2W@ADVAPI32@@3P6AHPEAUSC_HANDLE__@@KPEAEKPEAK@ZEA; int (*ADVAPI32::QueryServiceConfig2W)(SC_HANDLE__ *,ulong,uchar *,ulong,ulong *)
0x1801ee99f  mov     r9d, r13d
0x1801ee9a2  mov     edx, 1
0x1801ee9a7  mov     [rsp+4F0h+var_488], r15
0x1801ee9ac  mov     rcx, rdi
0x1801ee9af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ee9b4  test    eax, eax
0x1801ee9b6  jnz     short loc_1801EEA1D
0x1801ee9b8  call    cs:__imp_GetLastError
0x1801ee9be  cmp     eax, 1
0x1801ee9c1  jz      loc_1801EEA6B
0x1801ee9c7  cmp     eax, ebx
0x1801ee9c9  jz      loc_1801EEC50
0x1801ee9cf  mov     edx, [rsp+4F0h+var_48C]
0x1801ee9d3  cmp     edx, r13d
0x1801ee9d6  jbe     loc_1801EEA6B
0x1801ee9dc  lea     rcx, [rbp+3F0h+hMem]
0x1801ee9e0  call    ?SetSize@?$CAPITempBuffer@D$0CAA@@@QEAA_NH_N@Z; CAPITempBuffer<char,512>::SetSize(int,bool)
0x1801ee9e5  test    al, al
0x1801ee9e7  jz      loc_1801EEC50
0x1801ee9ed  mov     r15, [rbp+3F0h+hMem]
0x1801ee9f1  lea     rax, [rsp+4F0h+var_48C]
0x1801ee9f6  mov     r9d, [rsp+4F0h+var_48C]
0x1801ee9fb  mov     r8, r15
0x1801ee9fe  mov     [rsp+4F0h+var_4D0], rax
0x1801eea03  mov     edx, 1
0x1801eea08  mov     rax, cs:?QueryServiceConfig2W@ADVAPI32@@3P6AHPEAUSC_HANDLE__@@KPEAEKPEAK@ZEA; int (*ADVAPI32::QueryServiceConfig2W)(SC_HANDLE__ *,ulong,uchar *,ulong,ulong *)
0x1801eea0f  mov     rcx, rdi
0x1801eea12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eea17  test    eax, eax
0x1801eea19  jz      short loc_1801EEA64
0x1801eea1b  jmp     short loc_1801EEA21
0x1801eea1d  lea     r15, [rbp+3F0h+var_450]
0x1801eea21  mov     rdx, [r15]
0x1801eea24  lea     rcx, [rsp+4F0h+var_488]
0x1801eea29  call    ??4MsiString@@QEAAAEAV0@PEBG@Z; MsiString::operator=(ushort const *)
0x1801eea2e  mov     rcx, [rsp+4F0h+var_488]
0x1801eea33  mov     rax, [rcx]
0x1801eea36  mov     rax, [rax+38h]
0x1801eea3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eea3f  test    eax, eax
0x1801eea41  jnz     short loc_1801EEA64
0x1801eea43  xor     r8d, r8d
0x1801eea46  lea     edx, [rax+1]
0x1801eea49  lea     rcx, [rsp+4F0h+var_488]
0x1801eea4e  call    ?AllocateString@MsiString@@QEAAPEAGIW4Bool@@@Z; MsiString::AllocateString(uint,Bool)
0x1801eea53  mov     rcx, rax
0x1801eea56  test    rax, rax
0x1801eea59  jz      loc_1801EEC50
0x1801eea5f  xor     eax, eax
0x1801eea61  mov     [rcx], ax
0x1801eea64  lea     r15, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801eea6b  mov     dl, 1; bool
0x1801eea6d  mov     [rbp+3F0h+var_470], 0
0x1801eea75  lea     rcx, [rsp+4F0h+var_480]; this
0x1801eea7a  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x1801eea7f  mov     dl, 1
0x1801eea81  xor     ecx, ecx
0x1801eea83  call    ?RefCountedTokenPrivilegesCore@@YA_NW4itkpEnum@@_N@Z; RefCountedTokenPrivilegesCore(itkpEnum,bool)
0x1801eea88  xor     ecx, ecx
0x1801eea8a  mov     r8d, ebx
0x1801eea8d  test    al, al
0x1801eea8f  cmovnz  r8d, ecx
0x1801eea93  lea     rcx, [rbp+3F0h+var_470]
0x1801eea97  mov     [rbp+3F0h+var_468], r8d
0x1801eea9b  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x1801eeaa0  mov     r8, rax; struct IMsiStream **
0x1801eeaa3  mov     rdx, rdi; struct SC_HANDLE__ *
0x1801eeaa6  call    ?GetSDFromService@CMsiOpExecute@@IEAA_NQEAUSC_HANDLE__@@AEAPEAVIMsiStream@@@Z; CMsiOpExecute::GetSDFromService(SC_HANDLE__ * const,IMsiStream * &)
0x1801eeaab  lea     rcx, [rbp+3F0h+var_468]; this
0x1801eeaaf  call    ??1CRefCountedTokenPrivileges@@QEAA@XZ; CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges(void)
0x1801eeab4  lea     rcx, [rsp+4F0h+var_480]; this
0x1801eeab9  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x1801eeabe  mov     rax, [r14]
0x1801eeac1  mov     r8, r12
0x1801eeac4  mov     edx, 1
0x1801eeac9  mov     rcx, r14
0x1801eeacc  mov     rax, [rax+78h]
0x1801eead0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eead5  mov     rax, [r14]
0x1801eead8  lea     rcx, [rsp+4F0h+var_480]; this
0x1801eeadd  mov     rdx, [rsi+38h]; unsigned __int16 *
0x1801eeae1  mov     rdi, [rax+78h]
0x1801eeae5  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x1801eeaea  mov     edx, ebx
0x1801eeaec  mov     rcx, r14
0x1801eeaef  mov     r8, [rax]
0x1801eeaf2  mov     rax, rdi
0x1801eeaf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eeafa  mov     rcx, [rsp+4F0h+var_480]
0x1801eeaff  mov     rax, [rcx]
0x1801eeb02  mov     rax, [rax+10h]
0x1801eeb06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eeb0b  mov     rax, [r14]
0x1801eeb0e  lea     rcx, [rsp+4F0h+var_480]; this
0x1801eeb13  mov     rdx, [rsi+10h]; unsigned __int16 *
0x1801eeb17  mov     rbx, [rax+78h]
0x1801eeb1b  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x1801eeb20  mov     edx, 3
0x1801eeb25  mov     rcx, r14
0x1801eeb28  mov     r8, [rax]
0x1801eeb2b  mov     rax, rbx
0x1801eeb2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eeb33  mov     rcx, [rsp+4F0h+var_480]
0x1801eeb38  mov     rax, [rcx]
0x1801eeb3b  mov     rax, [rax+10h]
0x1801eeb3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eeb44  mov     rax, [r14]
0x1801eeb47  mov     edx, 4
0x1801eeb4c  mov     r8d, [rsi]
0x1801eeb4f  mov     rcx, r14
0x1801eeb52  mov     rax, [rax+68h]
0x1801eeb56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eeb5b  mov     rax, [r14]
0x1801eeb5e  mov     edx, 5
0x1801eeb63  mov     r8d, [rsi+4]
0x1801eeb67  mov     rcx, r14
0x1801eeb6a  mov     rax, [rax+68h]
0x1801eeb6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eeb73  mov     rax, [r14]
0x1801eeb76  mov     edx, 6
0x1801eeb7b  mov     r8d, [rsi+8]
0x1801eeb7f  mov     rcx, r14
0x1801eeb82  mov     rax, [rax+68h]
0x1801eeb86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eeb8b  mov     rax, [r14]
0x1801eeb8e  lea     rcx, [rsp+4F0h+var_480]; this
0x1801eeb93  mov     rdx, [rsi+18h]; unsigned __int16 *
0x1801eeb97  mov     rbx, [rax+78h]
0x1801eeb9b  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x1801eeba0  mov     edx, 7
0x1801eeba5  mov     rcx, r14
0x1801eeba8  mov     r8, [rax]
0x1801eebab  mov     rax, rbx
0x1801eebae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eebb3  mov     rcx, [rsp+4F0h+var_480]
0x1801eebb8  mov     rax, [rcx]
0x1801eebbb  mov     rax, [rax+10h]
0x1801eebbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eebc4  mov     rax, [r14]
0x1801eebc7  mov     edx, 0Ch
0x1801eebcc  mov     r8, [rsp+4F0h+var_488]
0x1801eebd1  mov     rcx, r14
0x1801eebd4  mov     rax, [rax+78h]
0x1801eebd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eebdd  mov     rax, [r14]
0x1801eebe0  mov     edx, 0Dh
0x1801eebe5  mov     r8, [rbp+3F0h+var_470]
0x1801eebe9  mov     rcx, r14
0x1801eebec  mov     rax, [rax+70h]
0x1801eebf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eebf5  mov     rcx, [rsi+28h]
0x1801eebf9  xor     eax, eax
0x1801eebfb  cmp     ax, [rcx]
0x1801eebfe  jnz     short loc_1801EEC06
0x1801eec00  cmp     ax, [rcx+2]
0x1801eec04  jz      short loc_1801EEC0C
0x1801eec06  add     rcx, 2
0x1801eec0a  jmp     short loc_1801EEBF9
0x1801eec0c  mov     [rsp+4F0h+var_478], r15
0x1801eec11  mov     r8d, 1
0x1801eec17  sub     rcx, [rsi+28h]
0x1801eec1b  sar     rcx, 1
0x1801eec1e  lea     ebx, [rcx+2]
0x1801eec21  mov     edx, ebx
0x1801eec23  lea     rcx, [rsp+4F0h+var_478]
0x1801eec28  call    ?AllocateString@MsiString@@QEAAPEAGIW4Bool@@@Z; MsiString::AllocateString(uint,Bool)
0x1801eec2d  test    ebx, ebx
0x1801eec2f  jz      short loc_1801EEC9A
0x1801eec31  test    rax, rax
0x1801eec34  jnz     short loc_1801EEC9A
0x1801eec36  mov     rcx, [rsp+4F0h+var_478]
0x1801eec3b  mov     rax, [rcx]
0x1801eec3e  mov     rax, [rax+10h]
0x1801eec42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eec47  lea     rcx, [rbp+3F0h+var_470]
0x1801eec4b  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1801eec50  mov     rcx, [rsp+4F0h+var_488]
0x1801eec55  mov     rax, [rcx]
0x1801eec58  mov     rax, [rax+10h]
0x1801eec5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eec61  cmp     [rbp+3F0h+var_458], r13d
0x1801eec65  jle     short loc_1801EEC71
0x1801eec67  mov     rcx, [rbp+3F0h+hMem]; hMem
0x1801eec6b  call    cs:__imp_GlobalFree
0x1801eec71  lea     rax, [rbp+3F0h+var_450]
0x1801eec75  mov     [rbp+3F0h+var_458], r13d
0x1801eec79  mov     [rbp+3F0h+hMem], rax
0x1801eec7d  cmp     [rbp+3F0h+var_248], r13d
0x1801eec84  jle     short loc_1801EEC93
0x1801eec86  mov     rcx, [rbp+3F0h+lpServiceConfig]; hMem
0x1801eec8d  call    cs:__imp_GlobalFree
0x1801eec93  xor     al, al
0x1801eec95  jmp     loc_1801EED89
0x1801eec9a  mov     rdx, [rsi+28h]; Src
0x1801eec9e  mov     rcx, rax; void *
0x1801eeca1  mov     r8d, ebx
0x1801eeca4  add     r8, r8; Size
0x1801eeca7  call    memcpy_0
0x1801eecac  mov     rax, [r14]
0x1801eecaf  mov     edx, 8
0x1801eecb4  mov     r8, [rsp+4F0h+var_478]
0x1801eecb9  mov     rcx, r14
0x1801eecbc  mov     rax, [rax+78h]
0x1801eecc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eecc5  mov     rax, [r14]
0x1801eecc8  mov     edx, 9
0x1801eeccd  mov     r8d, [rsi+20h]
0x1801eecd1  mov     rcx, r14
0x1801eecd4  mov     rax, [rax+68h]
0x1801eecd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eecdd  mov     rax, [r14]
0x1801eece0  lea     rcx, [rsp+4F0h+var_480]; this
0x1801eece5  mov     rdx, [rsi+30h]; unsigned __int16 *
0x1801eece9  mov     rbx, [rax+78h]
0x1801eeced  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x1801eecf2  mov     edx, 0Ah
0x1801eecf7  mov     rcx, r14
0x1801eecfa  mov     r8, [rax]
0x1801eecfd  mov     rax, rbx
0x1801eed00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eed05  mov     rcx, [rsp+4F0h+var_480]
  ... truncated ...
```
