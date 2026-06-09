# CMsiOpExecute::RollbackServiceConfiguration(SC_HANDLE__ * const,IMsiString const &,IMsiRecord &)

- ea: `0x1801f7864`
- end: `0x1801f7e14`
- name: `?RollbackServiceConfiguration@CMsiOpExecute@@IEAA_NQEAUSC_HANDLE__@@AEBVIMsiString@@AEAVIMsiRecord@@@Z`
- size: `1456`
- prototype: `bool(CMsiOpExecute *__hidden this, struct SC_HANDLE__ *const, const struct IMsiString *, struct IMsiRecord *)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180172b40`
- `0x1801e6fa8`

## callees

- `0x180003b10`
- `0x180005af8`
- `0x18000c4bc`
- `0x180014528`
- `0x180067fec`
- `0x18007adb4`
- `0x18007b9e8`
- `0x18008c93c`
- `0x1800ae46c`
- `0x1800af0e8`
- `0x180149e8c`
- `0x1801e9cf0`
- `0x1801f7864`
- `0x1802651d2`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!QueryServiceConfigW` at `0x1801f78d2`
- `ADVAPI32!QueryServiceConfigW` at `0x1801f7938`
- `ADVAPI32!QueryServiceConfigW` at `0x1801f78d2`
- `ADVAPI32!QueryServiceConfigW` at `0x1801f7938`
- `KERNEL32!GetLastError` at `0x1801f78eb`
- `KERNEL32!GetLastError` at `0x1801f79fa`
- `KERNEL32!GetLastError` at `0x1801f78eb`
- `KERNEL32!GetLastError` at `0x1801f79fa`
- `KERNEL32!GlobalFree` at `0x1801f7cb3`
- `KERNEL32!GlobalFree` at `0x1801f7cdb`
- `KERNEL32!GlobalFree` at `0x1801f7db3`
- `KERNEL32!GlobalFree` at `0x1801f7ddb`
- `KERNEL32!GlobalFree` at `0x1801f7cb3`
- `KERNEL32!GlobalFree` at `0x1801f7cdb`
- `KERNEL32!GlobalFree` at `0x1801f7db3`
- `KERNEL32!GlobalFree` at `0x1801f7ddb`

## string_xrefs

- `0x1801f7971`: `Service configuration for: %s is invalid. If the install is rolledback the service configuration might not be restored to its previous state.`

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
0x1801f7864  mov     [rsp-8+arg_0], rbx
0x1801f7869  push    rbp
0x1801f786a  push    rsi
0x1801f786b  push    rdi
0x1801f786c  push    r12
0x1801f786e  push    r13
0x1801f7870  push    r14
0x1801f7872  push    r15
0x1801f7874  lea     rbp, [rsp-3C0h]
0x1801f787c  sub     rsp, 4C0h
0x1801f7883  mov     rax, cs:__security_cookie
0x1801f788a  xor     rax, rsp
0x1801f788d  mov     [rbp+3F0h+var_40], rax
0x1801f7894  mov     rdi, rdx
0x1801f7897  mov     [rsp+4F0h+pcbBytesNeeded], 0
0x1801f789f  mov     r13d, 200h
0x1801f78a5  lea     rax, [rbp+3F0h+ServiceConfig]
0x1801f78ac  mov     r14, r9
0x1801f78af  mov     [rbp+3F0h+var_248], r13d
0x1801f78b6  mov     r12, r8
0x1801f78b9  mov     [rbp+3F0h+lpServiceConfig], rax
0x1801f78c0  mov     r8d, r13d; cbBufSize
0x1801f78c3  lea     r9, [rsp+4F0h+pcbBytesNeeded]; pcbBytesNeeded
0x1801f78c8  mov     rcx, rdi; hService
0x1801f78cb  lea     rdx, [rbp+3F0h+ServiceConfig]; lpServiceConfig
0x1801f78d2  call    cs:__imp_QueryServiceConfigW
0x1801f78d9  nop     dword ptr [rax+rax+00h]
0x1801f78de  mov     ebx, 2
0x1801f78e3  test    eax, eax
0x1801f78e5  jnz     loc_1801F79AA
0x1801f78eb  call    cs:__imp_GetLastError
0x1801f78f2  nop     dword ptr [rax+rax+00h]
0x1801f78f7  cmp     eax, ebx
0x1801f78f9  jz      loc_1801F7CCB
0x1801f78ff  cmp     eax, 7Ah ; 'z'
0x1801f7902  jnz     short loc_1801F7946
0x1801f7904  mov     edx, [rsp+4F0h+pcbBytesNeeded]
0x1801f7908  cmp     edx, r13d
0x1801f790b  jbe     short loc_1801F7946
0x1801f790d  lea     rcx, [rbp+3F0h+lpServiceConfig]
0x1801f7914  call    ?SetSize@?$CAPITempBuffer@D$0CAA@@@QEAA_NH_N@Z; CAPITempBuffer<char,512>::SetSize(int,bool)
0x1801f7919  test    al, al
0x1801f791b  jz      loc_1801F7CCB
0x1801f7921  mov     rsi, [rbp+3F0h+lpServiceConfig]
0x1801f7928  lea     r9, [rsp+4F0h+pcbBytesNeeded]; pcbBytesNeeded
0x1801f792d  mov     r8d, [rsp+4F0h+pcbBytesNeeded]; cbBufSize
0x1801f7932  mov     rdx, rsi; lpServiceConfig
0x1801f7935  mov     rcx, rdi; hService
0x1801f7938  call    cs:__imp_QueryServiceConfigW
0x1801f793f  nop     dword ptr [rax+rax+00h]
0x1801f7944  jmp     short loc_1801F79B1
0x1801f7946  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x1801f794d  jz      loc_1801F7CCB
0x1801f7953  mov     rax, [r12]
0x1801f7957  mov     rcx, r12
0x1801f795a  mov     rax, [rax+50h]
0x1801f795e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7963  lea     rcx, aNull; "(NULL)"
0x1801f796a  xor     edx, edx; unsigned __int16
0x1801f796c  mov     [rsp+4F0h+var_498], rdx; void *
0x1801f7971  lea     r9, aServiceConfigu; "Service configuration for: %s is invali"...
0x1801f7978  mov     [rsp+4F0h+var_4A0], edx; unsigned int
0x1801f797c  xor     r8d, r8d; int
0x1801f797f  mov     [rsp+4F0h+var_4A8], rcx; unsigned __int16 *
0x1801f7984  mov     [rsp+4F0h+var_4B0], rcx; unsigned __int16 *
0x1801f7989  mov     [rsp+4F0h+var_4B8], rcx; unsigned __int16 *
0x1801f798e  mov     [rsp+4F0h+var_4C0], rcx; unsigned __int16 *
0x1801f7993  mov     [rsp+4F0h+var_4C8], rcx; unsigned __int16 *
0x1801f7998  lea     ecx, [rdx+0Ah]; int
0x1801f799b  mov     [rsp+4F0h+var_4D0], rax; unsigned __int16 *
0x1801f79a0  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801f79a5  jmp     loc_1801F7CCB
0x1801f79aa  lea     rsi, [rbp+3F0h+ServiceConfig]
0x1801f79b1  lea     rax, [rbp+3F0h+var_450]
0x1801f79b5  mov     [rbp+3F0h+var_458], r13d
0x1801f79b9  mov     [rbp+3F0h+hMem], rax
0x1801f79bd  lea     r15, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801f79c4  lea     rax, [rsp+4F0h+var_48C]
0x1801f79c9  mov     [rsp+4F0h+var_48C], 0
0x1801f79d1  mov     [rsp+4F0h+var_4D0], rax
0x1801f79d6  lea     r8, [rbp+3F0h+var_450]
0x1801f79da  mov     rax, cs:?QueryServiceConfig2W@ADVAPI32@@3P6AHPEAUSC_HANDLE__@@KPEAEKPEAK@ZEA; int (*ADVAPI32::QueryServiceConfig2W)(SC_HANDLE__ *,ulong,uchar *,ulong,ulong *)
0x1801f79e1  mov     r9d, r13d
0x1801f79e4  mov     edx, 1
0x1801f79e9  mov     [rsp+4F0h+var_488], r15
0x1801f79ee  mov     rcx, rdi
0x1801f79f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f79f6  test    eax, eax
0x1801f79f8  jnz     short loc_1801F7A65
0x1801f79fa  call    cs:__imp_GetLastError
0x1801f7a01  nop     dword ptr [rax+rax+00h]
0x1801f7a06  cmp     eax, 1
0x1801f7a09  jz      loc_1801F7AB3
0x1801f7a0f  cmp     eax, ebx
0x1801f7a11  jz      loc_1801F7C98
0x1801f7a17  mov     edx, [rsp+4F0h+var_48C]
0x1801f7a1b  cmp     edx, r13d
0x1801f7a1e  jbe     loc_1801F7AB3
0x1801f7a24  lea     rcx, [rbp+3F0h+hMem]
0x1801f7a28  call    ?SetSize@?$CAPITempBuffer@D$0CAA@@@QEAA_NH_N@Z; CAPITempBuffer<char,512>::SetSize(int,bool)
0x1801f7a2d  test    al, al
0x1801f7a2f  jz      loc_1801F7C98
0x1801f7a35  mov     r15, [rbp+3F0h+hMem]
0x1801f7a39  lea     rax, [rsp+4F0h+var_48C]
0x1801f7a3e  mov     r9d, [rsp+4F0h+var_48C]
0x1801f7a43  mov     r8, r15
0x1801f7a46  mov     [rsp+4F0h+var_4D0], rax
0x1801f7a4b  mov     edx, 1
0x1801f7a50  mov     rax, cs:?QueryServiceConfig2W@ADVAPI32@@3P6AHPEAUSC_HANDLE__@@KPEAEKPEAK@ZEA; int (*ADVAPI32::QueryServiceConfig2W)(SC_HANDLE__ *,ulong,uchar *,ulong,ulong *)
0x1801f7a57  mov     rcx, rdi
0x1801f7a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7a5f  test    eax, eax
0x1801f7a61  jz      short loc_1801F7AAC
0x1801f7a63  jmp     short loc_1801F7A69
0x1801f7a65  lea     r15, [rbp+3F0h+var_450]
0x1801f7a69  mov     rdx, [r15]
0x1801f7a6c  lea     rcx, [rsp+4F0h+var_488]
0x1801f7a71  call    ??4MsiString@@QEAAAEAV0@PEBG@Z; MsiString::operator=(ushort const *)
0x1801f7a76  mov     rcx, [rsp+4F0h+var_488]
0x1801f7a7b  mov     rax, [rcx]
0x1801f7a7e  mov     rax, [rax+38h]
0x1801f7a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7a87  test    eax, eax
0x1801f7a89  jnz     short loc_1801F7AAC
0x1801f7a8b  xor     r8d, r8d
0x1801f7a8e  lea     edx, [rax+1]
0x1801f7a91  lea     rcx, [rsp+4F0h+var_488]
0x1801f7a96  call    ?AllocateString@MsiString@@QEAAPEAGIW4Bool@@@Z; MsiString::AllocateString(uint,Bool)
0x1801f7a9b  mov     rcx, rax
0x1801f7a9e  test    rax, rax
0x1801f7aa1  jz      loc_1801F7C98
0x1801f7aa7  xor     eax, eax
0x1801f7aa9  mov     [rcx], ax
0x1801f7aac  lea     r15, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801f7ab3  mov     dl, 1; bool
0x1801f7ab5  mov     [rbp+3F0h+var_470], 0
0x1801f7abd  lea     rcx, [rsp+4F0h+var_480]; this
0x1801f7ac2  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x1801f7ac7  mov     dl, 1
0x1801f7ac9  xor     ecx, ecx
0x1801f7acb  call    ?RefCountedTokenPrivilegesCore@@YA_NW4itkpEnum@@_N@Z; RefCountedTokenPrivilegesCore(itkpEnum,bool)
0x1801f7ad0  xor     ecx, ecx
0x1801f7ad2  mov     r8d, ebx
0x1801f7ad5  test    al, al
0x1801f7ad7  cmovnz  r8d, ecx
0x1801f7adb  lea     rcx, [rbp+3F0h+var_470]
0x1801f7adf  mov     [rbp+3F0h+var_468], r8d
0x1801f7ae3  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x1801f7ae8  mov     r8, rax; struct IMsiStream **
0x1801f7aeb  mov     rdx, rdi; struct SC_HANDLE__ *
0x1801f7aee  call    ?GetSDFromService@CMsiOpExecute@@IEAA_NQEAUSC_HANDLE__@@AEAPEAVIMsiStream@@@Z; CMsiOpExecute::GetSDFromService(SC_HANDLE__ * const,IMsiStream * &)
0x1801f7af3  lea     rcx, [rbp+3F0h+var_468]; this
0x1801f7af7  call    ??1CRefCountedTokenPrivileges@@QEAA@XZ; CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges(void)
0x1801f7afc  lea     rcx, [rsp+4F0h+var_480]; this
0x1801f7b01  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x1801f7b06  mov     rax, [r14]
0x1801f7b09  mov     r8, r12
0x1801f7b0c  mov     edx, 1
0x1801f7b11  mov     rcx, r14
0x1801f7b14  mov     rax, [rax+78h]
0x1801f7b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7b1d  mov     rax, [r14]
0x1801f7b20  lea     rcx, [rsp+4F0h+var_480]; this
0x1801f7b25  mov     rdx, [rsi+38h]; unsigned __int16 *
0x1801f7b29  mov     rdi, [rax+78h]
0x1801f7b2d  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x1801f7b32  mov     edx, ebx
0x1801f7b34  mov     rcx, r14
0x1801f7b37  mov     r8, [rax]
0x1801f7b3a  mov     rax, rdi
0x1801f7b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7b42  mov     rcx, [rsp+4F0h+var_480]
0x1801f7b47  mov     rax, [rcx]
0x1801f7b4a  mov     rax, [rax+10h]
0x1801f7b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7b53  mov     rax, [r14]
0x1801f7b56  lea     rcx, [rsp+4F0h+var_480]; this
0x1801f7b5b  mov     rdx, [rsi+10h]; unsigned __int16 *
0x1801f7b5f  mov     rbx, [rax+78h]
0x1801f7b63  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x1801f7b68  mov     edx, 3
0x1801f7b6d  mov     rcx, r14
0x1801f7b70  mov     r8, [rax]
0x1801f7b73  mov     rax, rbx
0x1801f7b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7b7b  mov     rcx, [rsp+4F0h+var_480]
0x1801f7b80  mov     rax, [rcx]
0x1801f7b83  mov     rax, [rax+10h]
0x1801f7b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7b8c  mov     rax, [r14]
0x1801f7b8f  mov     edx, 4
0x1801f7b94  mov     r8d, [rsi]
0x1801f7b97  mov     rcx, r14
0x1801f7b9a  mov     rax, [rax+68h]
0x1801f7b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7ba3  mov     rax, [r14]
0x1801f7ba6  mov     edx, 5
0x1801f7bab  mov     r8d, [rsi+4]
0x1801f7baf  mov     rcx, r14
0x1801f7bb2  mov     rax, [rax+68h]
0x1801f7bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7bbb  mov     rax, [r14]
0x1801f7bbe  mov     edx, 6
0x1801f7bc3  mov     r8d, [rsi+8]
0x1801f7bc7  mov     rcx, r14
0x1801f7bca  mov     rax, [rax+68h]
0x1801f7bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7bd3  mov     rax, [r14]
0x1801f7bd6  lea     rcx, [rsp+4F0h+var_480]; this
0x1801f7bdb  mov     rdx, [rsi+18h]; unsigned __int16 *
0x1801f7bdf  mov     rbx, [rax+78h]
0x1801f7be3  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x1801f7be8  mov     edx, 7
0x1801f7bed  mov     rcx, r14
0x1801f7bf0  mov     r8, [rax]
0x1801f7bf3  mov     rax, rbx
0x1801f7bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7bfb  mov     rcx, [rsp+4F0h+var_480]
0x1801f7c00  mov     rax, [rcx]
0x1801f7c03  mov     rax, [rax+10h]
0x1801f7c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7c0c  mov     rax, [r14]
0x1801f7c0f  mov     edx, 0Ch
0x1801f7c14  mov     r8, [rsp+4F0h+var_488]
0x1801f7c19  mov     rcx, r14
0x1801f7c1c  mov     rax, [rax+78h]
0x1801f7c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7c25  mov     rax, [r14]
0x1801f7c28  mov     edx, 0Dh
0x1801f7c2d  mov     r8, [rbp+3F0h+var_470]
0x1801f7c31  mov     rcx, r14
0x1801f7c34  mov     rax, [rax+70h]
0x1801f7c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7c3d  mov     rcx, [rsi+28h]
0x1801f7c41  xor     eax, eax
0x1801f7c43  cmp     ax, [rcx]
0x1801f7c46  jnz     short loc_1801F7C4E
0x1801f7c48  cmp     ax, [rcx+2]
0x1801f7c4c  jz      short loc_1801F7C54
0x1801f7c4e  add     rcx, 2
0x1801f7c52  jmp     short loc_1801F7C41
0x1801f7c54  mov     [rsp+4F0h+var_478], r15
0x1801f7c59  mov     r8d, 1
0x1801f7c5f  sub     rcx, [rsi+28h]
0x1801f7c63  sar     rcx, 1
0x1801f7c66  lea     ebx, [rcx+2]
0x1801f7c69  mov     edx, ebx
0x1801f7c6b  lea     rcx, [rsp+4F0h+var_478]
0x1801f7c70  call    ?AllocateString@MsiString@@QEAAPEAGIW4Bool@@@Z; MsiString::AllocateString(uint,Bool)
0x1801f7c75  test    ebx, ebx
0x1801f7c77  jz      short loc_1801F7CEE
0x1801f7c79  test    rax, rax
0x1801f7c7c  jnz     short loc_1801F7CEE
0x1801f7c7e  mov     rcx, [rsp+4F0h+var_478]
0x1801f7c83  mov     rax, [rcx]
0x1801f7c86  mov     rax, [rax+10h]
0x1801f7c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7c8f  lea     rcx, [rbp+3F0h+var_470]
0x1801f7c93  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1801f7c98  mov     rcx, [rsp+4F0h+var_488]
0x1801f7c9d  mov     rax, [rcx]
0x1801f7ca0  mov     rax, [rax+10h]
0x1801f7ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7ca9  cmp     [rbp+3F0h+var_458], r13d
0x1801f7cad  jle     short loc_1801F7CBF
0x1801f7caf  mov     rcx, [rbp+3F0h+hMem]; hMem
0x1801f7cb3  call    cs:__imp_GlobalFree
0x1801f7cba  nop     dword ptr [rax+rax+00h]
0x1801f7cbf  lea     rax, [rbp+3F0h+var_450]
0x1801f7cc3  mov     [rbp+3F0h+var_458], r13d
0x1801f7cc7  mov     [rbp+3F0h+hMem], rax
0x1801f7ccb  cmp     [rbp+3F0h+var_248], r13d
0x1801f7cd2  jle     short loc_1801F7CE7
0x1801f7cd4  mov     rcx, [rbp+3F0h+lpServiceConfig]; hMem
0x1801f7cdb  call    cs:__imp_GlobalFree
0x1801f7ce2  nop     dword ptr [rax+rax+00h]
0x1801f7ce7  xor     al, al
0x1801f7ce9  jmp     loc_1801F7DE9
0x1801f7cee  mov     rdx, [rsi+28h]; Src
0x1801f7cf2  mov     rcx, rax; void *
0x1801f7cf5  mov     r8d, ebx
0x1801f7cf8  add     r8, r8; Size
0x1801f7cfb  call    memcpy_0
0x1801f7d00  mov     rax, [r14]
0x1801f7d03  mov     edx, 8
0x1801f7d08  mov     r8, [rsp+4F0h+var_478]
0x1801f7d0d  mov     rcx, r14
0x1801f7d10  mov     rax, [rax+78h]
0x1801f7d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7d19  mov     rax, [r14]
0x1801f7d1c  mov     edx, 9
0x1801f7d21  mov     r8d, [rsi+20h]
0x1801f7d25  mov     rcx, r14
0x1801f7d28  mov     rax, [rax+68h]
0x1801f7d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7d31  mov     rax, [r14]
0x1801f7d34  lea     rcx, [rsp+4F0h+var_480]; this
0x1801f7d39  mov     rdx, [rsi+30h]; unsigned __int16 *
0x1801f7d3d  mov     rbx, [rax+78h]
0x1801f7d41  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
  ... truncated ...
```
