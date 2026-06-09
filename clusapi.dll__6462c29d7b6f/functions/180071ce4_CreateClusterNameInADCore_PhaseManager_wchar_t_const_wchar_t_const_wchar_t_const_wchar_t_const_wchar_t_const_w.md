# CreateClusterNameInADCore(PhaseManager &,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,ulong,int,CreateClusterADState * *,int)

- ea: `0x180071ce4`
- end: `0x180072434`
- name: `?CreateClusterNameInADCore@@YAKAEAVPhaseManager@@PEB_W11111KHPEAPEAVCreateClusterADState@@H@Z`
- size: `1872`
- prototype: `unsigned int __fastcall(struct PhaseManager *, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, unsigned int, int, struct CreateClusterADState **, int)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180071b48`

## callees

- `0x180002f50`
- `0x18000335c`
- `0x18001cc08`
- `0x18001cc2c`
- `0x18001ecdc`
- `0x180028f30`
- `0x180029578`
- `0x18006ef68`
- `0x18006f06c`
- `0x18006f22c`
- `0x18006f910`
- `0x180071028`
- `0x180071324`
- `0x180071ce4`
- `0x18007243c`
- `0x180072790`
- `0x180072f10`
- `0x1800766b8`
- `0x1800766e0`
- `0x18007688c`
- `0x1800a1c78`
- `0x1800a4618`
- `0x1800a5140`
- `0x1800a5e2c`
- `0x1800a6fe8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800721d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800721d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800723d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800723d9`
- `SspiCli!LogonUserExExW` at `0x1800721cb`
- `SspiCli!LogonUserExExW` at `0x1800721cb`

## string_xrefs

- `0x180071de1`: `CreateClusterNameInADCore`
- `0x180071e8f`: `CreateClusterNameInADCore`
- `0x180071fa6`: `Getting SID for user failed. Error %d.`
- `0x180072031`: `Read-Only`
- `0x18007202a`: `Read-Write`
- `0x180072051`: `Create cluster %ws will be using a %ws DC %ws.`
- `0x180072152`: `Node computer object %ws not found on DC %ws.`
- `0x1800721f3`: `Failed to obtain a logon token for user %ws in domain %ws, error %d.`
- `0x18007227a`: `The AD environment is Read-Only. But the CNO <%ws> is not found on DC <%ws>. The account needs to be pre-created and enabled.`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CreateClusterNameInADCore(
        struct PhaseManager *a1,
        wchar_t *a2,
        wchar_t *a3,
        const wchar_t *a4,
        wchar_t *a5,
        wchar_t *a6,
        wchar_t *a7,
        unsigned int a8,
        int a9,
        struct CreateClusterADState **a10,
        int a11)
{
  unsigned int v15; // eax
  unsigned int DC; // ebx
  __int64 DCName; // rax
  __int64 v18; // rax
  const WCHAR *v19; // rcx
  int SidForCreds; // eax
  int v21; // r12d
  const wchar_t *v22; // rax
  __int64 v23; // r9
  __int64 v24; // rax
  bool v25; // zf
  int v26; // ebx
  int v27; // eax
  const wchar_t *v28; // rdx
  wchar_t *v29; // rbx
  __int64 v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rax
  HANDLE v33; // rcx
  bool v34; // cc
  __int64 v35; // rax
  const wchar_t *v36; // rax
  int v37; // r13d
  char v38; // di
  int v39; // esi
  HANDLE v40; // r10
  __int64 ClusterADState; // rax
  wchar_t *v43; // [rsp+20h] [rbp-E0h]
  wchar_t *v44; // [rsp+20h] [rbp-E0h]
  wchar_t *v45; // [rsp+28h] [rbp-D8h]
  wchar_t *v46; // [rsp+28h] [rbp-D8h]
  wchar_t *v47; // [rsp+30h] [rbp-D0h]
  wchar_t *v48; // [rsp+30h] [rbp-D0h]
  struct ClusterADLdap **v49; // [rsp+38h] [rbp-C8h]
  bool v50; // [rsp+60h] [rbp-A0h]
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  int v52; // [rsp+70h] [rbp-90h] BYREF
  struct ClusterADObject *v53; // [rsp+78h] [rbp-88h] BYREF
  int v54; // [rsp+80h] [rbp-80h]
  struct ClusterADObject *v55; // [rsp+88h] [rbp-78h] BYREF
  struct ClusterADLdap *v56; // [rsp+90h] [rbp-70h] BYREF
  int v57; // [rsp+98h] [rbp-68h] BYREF
  int v58; // [rsp+9Ch] [rbp-64h]
  struct ClusterADLdap *v59; // [rsp+A0h] [rbp-60h]
  const wchar_t *v60; // [rsp+A8h] [rbp-58h]
  wchar_t *v61; // [rsp+B0h] [rbp-50h]
  struct ClusterADObject *v62; // [rsp+B8h] [rbp-48h]
  wchar_t *v63; // [rsp+C0h] [rbp-40h]
  wchar_t *v64; // [rsp+C8h] [rbp-38h]
  wchar_t *v65; // [rsp+D0h] [rbp-30h]
  struct ClusterADObject *v66; // [rsp+D8h] [rbp-28h]
  struct CreateClusterADState **v67; // [rsp+E0h] [rbp-20h]
  _BYTE v68[32]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v69[32]; // [rsp+108h] [rbp+8h] BYREF
  int v70[8]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v71[32]; // [rsp+148h] [rbp+48h] BYREF

  v60 = a4;
  v61 = a3;
  v64 = a5;
  v63 = a6;
  v65 = a7;
  v67 = a10;
  v54 = 0;
  v57 = 0;
  v52 = 0;
  std::wstring::wstring(v69);
  std::wstring::wstring(v68);
  v56 = 0;
  v53 = 0;
  v62 = 0;
  v55 = 0;
  hObject = 0;
  PhaseManager::StartPhase(a1, 106, a3);
  v15 = DoesAccountExistInGC(a1, a3, a2, a4, a5, a6, a8, &v57);
  DC = v15;
  if ( v15 )
  {
    LODWORD(v45) = v15;
    TraceMsg(2, 0, L"CreateClusterNameInADCore", 360, L"Failed to find CNO in GC. Error %d.", v45);
LABEL_46:
    PhaseManager::EndPhase(a1, DC, 1, 3);
    goto LABEL_47;
  }
  PhaseManager::EndPhase(a1, 0, 1, 1);
  v58 = v57;
  DC = FindDC(
         a1,
         a3,
         a2,
         a4,
         a5,
         v63,
         a8,
         &v56,
         (struct ClusterADObject **)((unsigned __int64)&v53 & -(__int64)(v57 != 0)));
  v59 = v56;
  if ( v56 )
  {
    DCName = ClusterADLdap::GetDCName(v56, v70);
    std::wstring::operator=(v68, DCName);
    std::wstring::_Tidy_deallocate(v70);
  }
  v66 = v53;
  if ( v57 && !v53 )
  {
    TraceMsg(
      4,
      0,
      L"CreateClusterNameInADCore",
      385,
      L"Global Catalog had an entry for the CNO but the object was not found when searching.");
    v58 = 0;
  }
  v18 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v68);
  v19 = &base;
  if ( v18 )
    v19 = (const WCHAR *)v18;
  ReportPhaseStatus(
    a1,
    DC,
    (enum _CLUSTER_SETUP_PHASE_SEVERITY)(DC != 0 ? ClusterSetupPhaseFatal : ClusterSetupPhaseInformational),
    2u,
    v19);
  if ( DC )
  {
    LODWORD(v46) = DC;
    TraceMsg(2, 0, L"CreateClusterNameInADCore", 400, L"Failed to find suitable Creating DC. Error %d.", v46);
    goto LABEL_46;
  }
  if ( a5 )
  {
    std::wstring::wstring(v70, v60);
    v54 = 1;
    SidForCreds = ClusterADLdap::GetSidForCreds((__int64)v59);
  }
  else
  {
    SidForCreds = ClusterADLdap::s_GetSidOfCallingThread((__int64)v69);
  }
  v21 = SidForCreds;
  if ( (v54 & 1) != 0 )
    std::wstring::_Tidy_deallocate(v70);
  if ( v21 < 0 )
  {
    if ( (v21 & 0x1FFF0000) != 0x70000 || (DC = (unsigned __int16)v21, !(_WORD)v21) )
      DC = v21;
    LODWORD(v46) = DC;
    TraceMsg(2, 0, L"CreateClusterNameInADCore", 411, L"Getting SID for user failed. Error %d.", v46);
    goto LABEL_47;
  }
  DC = ClRtlIsMachineDomainJoined(a2, &v52);
  if ( !DC )
  {
    v24 = *((_QWORD *)v59 + 4);
    v25 = (*(_DWORD *)(v24 + 56) & 0x100) == 0;
    v54 = *(_DWORD *)(v24 + 56) & 0x100;
    v26 = v54;
    v50 = v25;
    v27 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v68);
    v28 = L"Read-Only";
    if ( v26 )
      v28 = L"Read-Write";
    LODWORD(v49) = v27;
    v29 = v61;
    TraceMsg(4, 0, L"CreateClusterNameInADCore", 423, L"Create cluster %ws will be using a %ws DC %ws.", v61, v28);
    if ( v52 )
    {
      v30 = std::wstring::wstring(v71);
      std::wstring::wstring(v70, a2);
      DC = ClusterADLdap::SearchForObject((__int64)v59, (int)v70, v30);
      v52 = DC;
      std::wstring::_Tidy_deallocate(v70);
      std::wstring::_Tidy_deallocate(v71);
      if ( (DC & 0x1FFF0000) == 0x70000 )
      {
        DC = (unsigned __int16)DC;
        if ( !(_WORD)DC )
          DC = v52;
      }
      v31 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v68);
      ReportPhaseStatus(
        a1,
        DC,
        (enum _CLUSTER_SETUP_PHASE_SEVERITY)(DC != 0 ? ClusterSetupPhaseFatal : ClusterSetupPhaseInformational),
        3u,
        a2,
        a2,
        v31);
      if ( v52 < 0 )
      {
        v22 = L"Searching for node object %ws failed. Error %d.";
        v23 = 441;
        goto LABEL_24;
      }
      v62 = v55;
      if ( !v55 )
      {
        v32 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v68);
        TraceMsg(2, 0, L"CreateClusterNameInADCore", 447, L"Node computer object %ws not found on DC %ws.", a2, v32);
        DC = 4312;
        ReportPhaseStatus(a1, 0x10D8u, ClusterSetupPhaseFatal, 5u, a2);
        goto LABEL_47;
      }
      v29 = v61;
    }
    else
    {
      v49 = 0;
      if ( !(unsigned int)LogonUserExExW(v64, v60, v63, 9, 0, 0, &hObject) )
      {
        DC = GetLastError();
        LODWORD(v49) = DC;
        TraceMsg(
          2,
          0,
          L"CreateClusterNameInADCore",
          472,
          L"Failed to obtain a logon token for user %ws in domain %ws, error %d.",
          v64,
          v60,
          v49);
        v33 = hObject;
        v34 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
        goto LABEL_48;
      }
    }
    if ( v58 )
    {
      PhaseManager::StartPhase(a1, 107, v29);
      v39 = (int)v66;
      DC = ValidateExistingObject(a1, v66, v65, v50);
      if ( DC )
        goto LABEL_46;
      v38 = 0;
      v37 = (int)v62;
    }
    else
    {
      if ( !v54 )
      {
        v35 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v68);
        v43 = v29;
        DC = 4312;
        ReportPhaseStatus(a1, 0x10D8u, ClusterSetupPhaseFatal, 0xCu, v43, v35);
        v48 = (wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v68);
        TraceMsg(
          2,
          0,
          L"CreateClusterNameInADCore",
          493,
          L"The AD environment is Read-Only. But the CNO <%ws> is not found on DC <%ws>. The account needs to be pre-created and enabled.",
          v61,
          v48);
        goto LABEL_47;
      }
      PhaseManager::StartPhase(a1, 108, v29);
      v36 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v68);
      v44 = a2;
      v37 = (int)v62;
      DC = CreateClusterObjectInAD((wchar_t *)a1, v59, v62, v29, v44, v36, v65, (int)v49, (wchar_t **)&v53, a11);
      if ( DC )
        goto LABEL_46;
      v38 = 1;
      v39 = (int)v53;
    }
    PhaseManager::EndPhase(a1, 0, ClusterSetupPhaseInformational);
    v66 = (struct ClusterADObject *)operator new(0x68u);
    v40 = hObject;
    hObject = 0;
    v55 = 0;
    v53 = 0;
    v56 = 0;
    ClusterADState = CreateClusterADState::CreateClusterADState(
                       (_DWORD)v66,
                       (_DWORD)v59,
                       v39,
                       v37,
                       v38,
                       a9 != 0,
                       v50,
                       (__int64)v69,
                       (__int64)v40,
                       (__int64)v68);
    *v67 = (struct CreateClusterADState *)ClusterADState;
    goto LABEL_47;
  }
  v22 = L"Failed to determine if machine %ws is domain joined. Error %d.";
  v23 = 418;
LABEL_24:
  LODWORD(v47) = DC;
  TraceMsg(2, 0, L"CreateClusterNameInADCore", v23, v22, a2, v47);
LABEL_47:
  v33 = hObject;
  v34 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_48:
  hObject = 0;
  if ( v34 )
    CloseHandle(v33);
  CTSmartObj<ClusterADObject *,CTSmartPtr_PolicyComplete<CTSmartPtr_PolicyNewMem>>::Release(&v55);
  CTSmartObj<ClusterADObject *,CTSmartPtr_PolicyComplete<CTSmartPtr_PolicyNewMem>>::Release(&v53);
  CAutoMemPtr<ClusterADLdap>::~CAutoMemPtr<ClusterADLdap>(&v56);
  std::wstring::_Tidy_deallocate(v68);
  std::wstring::_Tidy_deallocate(v69);
  return DC;
}

```

## disassembly

```asm
0x180071ce4  push    rbp
0x180071ce6  push    rbx
0x180071ce7  push    rsi
0x180071ce8  push    rdi
0x180071ce9  push    r12
0x180071ceb  push    r13
0x180071ced  push    r14
0x180071cef  push    r15
0x180071cf1  lea     rbp, [rsp-78h]
0x180071cf6  sub     rsp, 178h
0x180071cfd  mov     rax, cs:__security_cookie
0x180071d04  xor     rax, rsp
0x180071d07  mov     [rbp+0B0h+var_48], rax
0x180071d0b  mov     rsi, r9
0x180071d0e  mov     [rbp+0B0h+var_108], r9
0x180071d12  mov     rdi, r8
0x180071d15  mov     [rbp+0B0h+var_100], r8
0x180071d19  mov     r13, rdx
0x180071d1c  mov     r14, rcx
0x180071d1f  mov     r12, [rbp+0B0h+arg_20]
0x180071d26  mov     [rbp+0B0h+var_E8], r12
0x180071d2a  mov     rbx, [rbp+0B0h+arg_28]
0x180071d31  mov     [rbp+0B0h+var_F0], rbx
0x180071d35  mov     rax, [rbp+0B0h+arg_30]
0x180071d3c  mov     [rbp+0B0h+var_E0], rax
0x180071d40  mov     rax, [rbp+0B0h+arg_48]
0x180071d47  mov     [rbp+0B0h+var_D0], rax
0x180071d4b  xor     r15d, r15d
0x180071d4e  mov     [rbp+0B0h+var_130], r15d
0x180071d52  mov     [rbp+0B0h+var_118], r15d
0x180071d56  mov     [rsp+1B0h+var_140], r15d
0x180071d5b  lea     rcx, [rbp+0B0h+var_A8]
0x180071d5f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180071d64  nop
0x180071d65  lea     rcx, [rbp+0B0h+var_C8]
0x180071d69  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180071d6e  nop
0x180071d6f  mov     [rbp+0B0h+var_120], r15
0x180071d73  mov     [rsp+1B0h+var_138], r15
0x180071d78  mov     eax, r15d
0x180071d7b  mov     [rbp+0B0h+var_F8], rax
0x180071d7f  mov     [rbp+0B0h+var_128], rax
0x180071d83  mov     [rsp+1B0h+hObject], r15
0x180071d88  mov     r8, rdi
0x180071d8b  lea     edx, [r15+6Ah]
0x180071d8f  mov     rcx, r14
0x180071d92  call    ?StartPhase@PhaseManager@@QEAAXW4_CLUSTER_SETUP_PHASE@@PEB_WW4Enum@CancelAllowed@@@Z; PhaseManager::StartPhase(_CLUSTER_SETUP_PHASE,wchar_t const *,CancelAllowed::Enum)
0x180071d97  lea     rax, [rbp+0B0h+var_118]
0x180071d9b  mov     [rsp+1B0h+var_178], rax; int *
0x180071da0  mov     eax, [rbp+0B0h+arg_38]
0x180071da6  mov     dword ptr [rsp+1B0h+var_180], eax; unsigned int
0x180071daa  mov     [rsp+1B0h+var_188], rbx; wchar_t *
0x180071daf  mov     [rsp+1B0h+var_190], r12; wchar_t *
0x180071db4  mov     r9, rsi; wchar_t *
0x180071db7  mov     r8, r13; wchar_t *
0x180071dba  mov     rdx, rdi; wchar_t *
0x180071dbd  mov     rcx, r14; this
0x180071dc0  call    ?DoesAccountExistInGC@@YAKAEAVPhaseManager@@PEB_W1111KPEAH@Z; DoesAccountExistInGC(PhaseManager &,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,ulong,int *)
0x180071dc5  mov     ebx, eax
0x180071dc7  test    eax, eax
0x180071dc9  jz      short loc_180071DFF
0x180071dcb  mov     dword ptr [rsp+1B0h+var_188], eax
0x180071dcf  lea     rax, aFailedToFindCn; "Failed to find CNO in GC. Error %d."
0x180071dd6  mov     [rsp+1B0h+var_190], rax
0x180071ddb  mov     r9d, 168h
0x180071de1  lea     r8, aCreateclustern_6; "CreateClusterNameInADCore"
0x180071de8  xor     edx, edx
0x180071dea  lea     ecx, [rdx+2]
0x180071ded  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180071df2  lea     r9d, [r15+3]
0x180071df6  lea     r8d, [r15+1]
0x180071dfa  jmp     loc_1800723B6
0x180071dff  mov     r15d, 1
0x180071e05  mov     r9d, r15d
0x180071e08  mov     r8d, r15d
0x180071e0b  xor     edx, edx
0x180071e0d  mov     rcx, r14
0x180071e10  call    ?EndPhase@PhaseManager@@QEAAXKW4Enum@CancelAllowed@@W4_CLUSTER_SETUP_PHASE_SEVERITY@@@Z; PhaseManager::EndPhase(ulong,CancelAllowed::Enum,_CLUSTER_SETUP_PHASE_SEVERITY)
0x180071e15  mov     eax, [rbp+0B0h+var_118]
0x180071e18  mov     [rbp+0B0h+var_114], eax
0x180071e1b  neg     eax
0x180071e1d  sbb     rcx, rcx
0x180071e20  lea     rax, [rsp+1B0h+var_138]
0x180071e25  and     rcx, rax
0x180071e28  mov     [rsp+1B0h+var_170], rcx; struct ClusterADObject **
0x180071e2d  lea     rax, [rbp+0B0h+var_120]
0x180071e31  mov     [rsp+1B0h+var_178], rax; struct ClusterADLdap **
0x180071e36  mov     eax, [rbp+0B0h+arg_38]
0x180071e3c  mov     dword ptr [rsp+1B0h+var_180], eax; unsigned int
0x180071e40  mov     rax, [rbp+0B0h+var_F0]
0x180071e44  mov     [rsp+1B0h+var_188], rax; wchar_t *
0x180071e49  mov     [rsp+1B0h+var_190], r12; wchar_t *
0x180071e4e  mov     r9, rsi; wchar_t *
0x180071e51  mov     r8, r13; wchar_t *
0x180071e54  mov     rdx, rdi; wchar_t *
0x180071e57  mov     rcx, r14; struct PhaseManager *
0x180071e5a  call    ?FindDC@@YAKAEAVPhaseManager@@PEB_W1111KPEAPEAVClusterADLdap@@PEAPEAVClusterADObject@@@Z; FindDC(PhaseManager &,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,ulong,ClusterADLdap * *,ClusterADObject * *)
0x180071e5f  mov     ebx, eax
0x180071e61  mov     rax, [rbp+0B0h+var_120]
0x180071e65  mov     [rbp+0B0h+var_110], rax
0x180071e69  test    rax, rax
0x180071e6c  jz      short loc_180071E8F
0x180071e6e  lea     rdx, [rbp+0B0h+var_88]
0x180071e72  mov     rcx, rax
0x180071e75  call    ?GetDCName@ClusterADLdap@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; ClusterADLdap::GetDCName(void)
0x180071e7a  mov     rdx, rax
0x180071e7d  lea     rcx, [rbp+0B0h+var_C8]
0x180071e81  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180071e86  lea     rcx, [rbp+0B0h+var_88]
0x180071e8a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180071e8f  lea     rsi, aCreateclustern_6; "CreateClusterNameInADCore"
0x180071e96  mov     rax, [rsp+1B0h+var_138]
0x180071e9b  mov     [rbp+0B0h+var_D8], rax
0x180071e9f  cmp     [rbp+0B0h+var_118], 0
0x180071ea3  jz      short loc_180071ED0
0x180071ea5  test    rax, rax
0x180071ea8  jnz     short loc_180071ED0
0x180071eaa  lea     rax, aGlobalCatalogH; "Global Catalog had an entry for the CNO"...
0x180071eb1  mov     [rsp+1B0h+var_190], rax
0x180071eb6  mov     r9d, 181h
0x180071ebc  mov     r8, rsi
0x180071ebf  xor     edx, edx
0x180071ec1  lea     ecx, [rdx+4]
0x180071ec4  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180071ec9  mov     [rbp+0B0h+var_114], 0
0x180071ed0  lea     rcx, [rbp+0B0h+var_C8]
0x180071ed4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180071ed9  lea     rcx, base
0x180071ee0  test    rax, rax
0x180071ee3  cmovnz  rcx, rax
0x180071ee7  mov     eax, ebx
0x180071ee9  neg     eax
0x180071eeb  sbb     r8d, r8d
0x180071eee  mov     edi, 2
0x180071ef3  and     r8d, edi
0x180071ef6  add     r8d, r15d; enum _CLUSTER_SETUP_PHASE_SEVERITY
0x180071ef9  mov     [rsp+1B0h+var_190], rcx
0x180071efe  mov     r9d, edi; unsigned int
0x180071f01  mov     edx, ebx; unsigned int
0x180071f03  mov     rcx, r14; this
0x180071f06  call    ?ReportPhaseStatus@@YAXAEAVPhaseManager@@KW4_CLUSTER_SETUP_PHASE_SEVERITY@@KZZ; ReportPhaseStatus(PhaseManager &,ulong,_CLUSTER_SETUP_PHASE_SEVERITY,ulong,...)
0x180071f0b  test    ebx, ebx
0x180071f0d  jz      short loc_180071F3A
0x180071f0f  mov     dword ptr [rsp+1B0h+var_188], ebx
0x180071f13  lea     rax, aFailedToFindSu; "Failed to find suitable Creating DC. Er"...
0x180071f1a  mov     [rsp+1B0h+var_190], rax
0x180071f1f  mov     r9d, 190h
0x180071f25  mov     r8, rsi
0x180071f28  xor     edx, edx
0x180071f2a  mov     ecx, edi
0x180071f2c  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180071f31  lea     r9d, [rdi+1]
0x180071f35  jmp     loc_1800723B3
0x180071f3a  test    r12, r12
0x180071f3d  jz      short loc_180071F67
0x180071f3f  mov     rdx, [rbp+0B0h+var_108]
0x180071f43  lea     rcx, [rbp+0B0h+var_88]
0x180071f47  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180071f4c  nop
0x180071f4d  mov     [rbp+0B0h+var_130], r15d
0x180071f51  mov     r9, r12
0x180071f54  lea     r8, [rbp+0B0h+var_88]
0x180071f58  lea     rdx, [rbp+0B0h+var_A8]
0x180071f5c  mov     rcx, [rbp+0B0h+var_110]; __int64
0x180071f60  call    ?GetSidForCreds@ClusterADLdap@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@PEB_W@Z; ClusterADLdap::GetSidForCreds(std::wstring &,std::wstring const &,wchar_t const *)
0x180071f65  jmp     short loc_180071F71
0x180071f67  lea     rcx, [rbp+0B0h+var_A8]
0x180071f6b  call    ?s_GetSidOfCallingThread@ClusterADLdap@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; ClusterADLdap::s_GetSidOfCallingThread(std::wstring &)
0x180071f70  nop
0x180071f71  mov     r12d, eax
0x180071f74  test    byte ptr [rbp+0B0h+var_130], r15b
0x180071f78  jz      short loc_180071F83
0x180071f7a  lea     rcx, [rbp+0B0h+var_88]
0x180071f7e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180071f83  test    r12d, r12d
0x180071f86  jns     short loc_180071FC9
0x180071f88  mov     eax, r12d
0x180071f8b  and     eax, 1FFF0000h
0x180071f90  cmp     eax, 70000h
0x180071f95  jnz     short loc_180071F9F
0x180071f97  movzx   ebx, r12w
0x180071f9b  test    ebx, ebx
0x180071f9d  jnz     short loc_180071FA2
0x180071f9f  mov     ebx, r12d
0x180071fa2  mov     dword ptr [rsp+1B0h+var_188], ebx
0x180071fa6  lea     rax, aGettingSidForU; "Getting SID for user failed. Error %d."
0x180071fad  mov     [rsp+1B0h+var_190], rax
0x180071fb2  mov     r9d, 19Bh
0x180071fb8  mov     r8, rsi
0x180071fbb  xor     edx, edx
0x180071fbd  mov     ecx, edi
0x180071fbf  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180071fc4  jmp     loc_1800723C1
0x180071fc9  lea     rdx, [rsp+1B0h+var_140]
0x180071fce  mov     rcx, r13
0x180071fd1  call    ClRtlIsMachineDomainJoined
0x180071fd6  mov     ebx, eax
0x180071fd8  test    eax, eax
0x180071fda  jz      short loc_180072008
0x180071fdc  lea     rax, aFailedToDeterm_1; "Failed to determine if machine %ws is d"...
0x180071fe3  mov     r9d, 1A2h
0x180071fe9  mov     dword ptr [rsp+1B0h+var_180], ebx
0x180071fed  mov     [rsp+1B0h+var_188], r13
0x180071ff2  mov     [rsp+1B0h+var_190], rax
0x180071ff7  mov     r8, rsi
0x180071ffa  xor     edx, edx
0x180071ffc  mov     ecx, edi
0x180071ffe  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180072003  jmp     loc_1800723C1
0x180072008  mov     rax, [rbp+0B0h+var_110]
0x18007200c  mov     rax, [rax+20h]
0x180072010  mov     ebx, [rax+38h]
0x180072013  and     ebx, 100h
0x180072019  mov     [rbp+0B0h+var_130], ebx
0x18007201c  setz    [rsp+1B0h+var_150]
0x180072021  lea     rcx, [rbp+0B0h+var_C8]
0x180072025  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18007202a  lea     r8, aReadWrite; "Read-Write"
0x180072031  lea     rdx, aReadOnly; "Read-Only"
0x180072038  test    ebx, ebx
0x18007203a  cmovnz  rdx, r8
0x18007203e  mov     [rsp+1B0h+var_178], rax; int
0x180072043  mov     [rsp+1B0h+var_180], rdx
0x180072048  mov     rbx, [rbp+0B0h+var_100]
0x18007204c  mov     [rsp+1B0h+var_188], rbx
0x180072051  lea     rax, aCreateClusterW; "Create cluster %ws will be using a %ws "...
0x180072058  mov     [rsp+1B0h+var_190], rax
0x18007205d  mov     r9d, 1A7h
0x180072063  mov     r8, rsi
0x180072066  xor     edx, edx
0x180072068  lea     ecx, [rdx+4]
0x18007206b  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180072070  xor     ecx, ecx
0x180072072  lea     r12d, [rcx+3]
0x180072076  cmp     [rsp+1B0h+var_140], ecx
0x18007207a  jz      loc_180072192
0x180072080  lea     rcx, [rbp+0B0h+var_68]
0x180072084  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180072089  mov     rbx, rax
0x18007208c  mov     rdx, r13
0x18007208f  lea     rcx, [rbp+0B0h+var_88]
0x180072093  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180072098  nop
0x180072099  mov     [rsp+1B0h+var_190], rbx; __int64
0x18007209e  lea     r8, [rbp+0B0h+var_128]
0x1800720a2  lea     rdx, [rbp+0B0h+var_88]; int
0x1800720a6  mov     rcx, [rbp+0B0h+var_110]; __int64
0x1800720aa  call    ?SearchForObject@ClusterADLdap@@QEAAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAPEAVClusterADObject@@H0@Z; ClusterADLdap::SearchForObject(std::wstring const &,ClusterADObject * *,int,std::wstring const &)
0x1800720af  mov     ebx, eax
0x1800720b1  mov     [rsp+1B0h+var_140], eax
0x1800720b5  lea     rcx, [rbp+0B0h+var_88]
0x1800720b9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800720be  nop
0x1800720bf  lea     rcx, [rbp+0B0h+var_68]
0x1800720c3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800720c8  mov     ecx, ebx
0x1800720ca  and     ecx, 1FFF0000h
0x1800720d0  cmp     ecx, 70000h
0x1800720d6  jnz     short loc_1800720E3
0x1800720d8  movzx   ebx, bx
0x1800720db  test    ebx, ebx
0x1800720dd  jnz     short loc_1800720E3
0x1800720df  mov     ebx, [rsp+1B0h+var_140]
0x1800720e3  lea     rcx, [rbp+0B0h+var_C8]
0x1800720e7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800720ec  mov     ecx, ebx
0x1800720ee  neg     ecx
0x1800720f0  sbb     r8d, r8d
0x1800720f3  and     r8d, edi
0x1800720f6  add     r8d, r15d; enum _CLUSTER_SETUP_PHASE_SEVERITY
0x1800720f9  mov     [rsp+1B0h+var_180], rax
0x1800720fe  mov     [rsp+1B0h+var_188], r13
0x180072103  mov     [rsp+1B0h+var_190], r13
0x180072108  mov     r9d, r12d; unsigned int
0x18007210b  mov     edx, ebx; unsigned int
0x18007210d  mov     rcx, r14; this
0x180072110  call    ?ReportPhaseStatus@@YAXAEAVPhaseManager@@KW4_CLUSTER_SETUP_PHASE_SEVERITY@@KZZ; ReportPhaseStatus(PhaseManager &,ulong,_CLUSTER_SETUP_PHASE_SEVERITY,ulong,...)
0x180072115  cmp     [rsp+1B0h+var_140], 0
0x18007211a  jge     short loc_18007212E
0x18007211c  lea     rax, aSearchingForNo; "Searching for node object %ws failed. E"...
0x180072123  mov     r9d, 1B9h
0x180072129  jmp     loc_180071FE9
0x18007212e  mov     rax, [rbp+0B0h+var_128]
0x180072132  mov     [rbp+0B0h+var_F8], rax
0x180072136  test    rax, rax
0x180072139  jnz     loc_180072224
0x18007213f  lea     rcx, [rbp+0B0h+var_C8]
0x180072143  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180072148  mov     [rsp+1B0h+var_180], rax
0x18007214d  mov     [rsp+1B0h+var_188], r13
0x180072152  lea     rax, aNodeComputerOb_0; "Node computer object %ws not found on D"...
0x180072159  mov     [rsp+1B0h+var_190], rax
0x18007215e  mov     r9d, 1BFh
0x180072164  mov     r8, rsi
0x180072167  xor     edx, edx
0x180072169  mov     ecx, edi
0x18007216b  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180072170  mov     [rsp+1B0h+var_190], r13
0x180072175  mov     r9d, 5; unsigned int
0x18007217b  mov     r8d, r12d; enum _CLUSTER_SETUP_PHASE_SEVERITY
  ... truncated ...
```
