# InitComAdmindata

- ea: `0x18000a0b0`
- end: `0x18000a6ba`
- name: `InitComAdmindata`
- size: `1546`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001064`
- `0x180006128`
- `0x18000a0b0`
- `0x18000b2d4`
- `0x18000b72c`
- `0x18000d9e4`
- `0x18000dafc`
- `0x18000dc5c`
- `0x18000dd4c`
- `0x18000fb1e`
- `0x18000fb50`
- `0x180010010`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18000a1e7`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18000a1e7`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18000a204`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18000a204`
- `ADVAPI32!AddAccessAllowedAce` at `0x18000a1b1`
- `ADVAPI32!AddAccessAllowedAce` at `0x18000a1b1`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x18000a1cc`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x18000a1cc`
- `ADVAPI32!InitializeAcl` at `0x18000a191`
- `ADVAPI32!InitializeAcl` at `0x18000a191`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18000a14f`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18000a14f`
- `ADVAPI32!CreateWellKnownSid` at `0x18000a173`
- `ADVAPI32!CreateWellKnownSid` at `0x18000a173`
- `ole32!CoRegisterClassObject` at `0x18000a499`
- `ole32!CoRegisterClassObject` at `0x18000a499`
- `ole32!CoRevokeClassObject` at `0x18000a5b3`
- `ole32!CoRevokeClassObject` at `0x18000a5b3`
- `ole32!CoCreateInstance` at `0x18000a3da`
- `ole32!CoCreateInstance` at `0x18000a3da`
- `KERNEL32!OutputDebugStringA` at `0x18000a11e`
- `KERNEL32!OutputDebugStringA` at `0x18000a11e`
- `KERNEL32!GetLastError` at `0x18000a20e`
- `KERNEL32!GetLastError` at `0x18000a31c`
- `KERNEL32!GetLastError` at `0x18000a4af`
- `KERNEL32!GetLastError` at `0x18000a4f7`
- `KERNEL32!GetLastError` at `0x18000a508`
- `KERNEL32!GetLastError` at `0x18000a20e`
- `KERNEL32!GetLastError` at `0x18000a31c`
- `KERNEL32!GetLastError` at `0x18000a4af`
- `KERNEL32!GetLastError` at `0x18000a4f7`
- `KERNEL32!GetLastError` at `0x18000a508`
- `AUTHZ!AuthzRegisterSecurityEventSource` at `0x18000a2b7`
- `AUTHZ!AuthzRegisterSecurityEventSource` at `0x18000a340`
- `AUTHZ!AuthzRegisterSecurityEventSource` at `0x18000a2b7`
- `AUTHZ!AuthzRegisterSecurityEventSource` at `0x18000a340`
- `AUTHZ!AuthzInstallSecurityEventSource` at `0x18000a312`
- `AUTHZ!AuthzInstallSecurityEventSource` at `0x18000a312`
- `IisRTL!PuCreateDebugPrintsObject` at `0x18000a105`
- `IisRTL!PuCreateDebugPrintsObject` at `0x18000a105`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x18000a68e`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x18000a68e`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x18000a2ec`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x18000a2ec`
- `IisRTL!PuDbgPrint` at `0x18000a25d`
- `IisRTL!PuDbgPrint` at `0x18000a4e0`
- `IisRTL!PuDbgPrint` at `0x18000a539`
- `IisRTL!PuDbgPrint` at `0x18000a25d`
- `IisRTL!PuDbgPrint` at `0x18000a4e0`
- `IisRTL!PuDbgPrint` at `0x18000a539`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x18000a0f3`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x18000a0f3`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a2d0`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a2d0`
- `IisRTL!IISGetPlatformType` at `0x18000a139`
- `IisRTL!IISGetPlatformType` at `0x18000a139`
- `IisRTL!PuLoadDebugFlagsFromRegStr` at `0x18000a12d`
- `IisRTL!PuLoadDebugFlagsFromRegStr` at `0x18000a12d`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18000a29e`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18000a590`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18000a681`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18000a29e`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18000a590`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18000a681`

## string_xrefs

- `0x18000a117`: `Unable to Create Debug Print Object \n`
- `0x18000a126`: `System\CurrentControlSet\Services\iisadmin\Parameters`
- `0x18000a23c`: `[InitComAdmindata] AdminAclInitAclCache failed, hr 0x%8x\n`
- `0x18000a24a`: `InitComAdmindata`
- `0x18000a4bc`: `InitComAdmindata`
- `0x18000a515`: `InitComAdmindata`
- `0x18000a2e1`: `\system32\inetsrv\iisres.dll`
- `0x18000a380`: `[InitComAdmindata] g_ohMasterRootHandle.Init failed, hr 0x%8x\n`
- `0x18000a3af`: `[InitComAdmindata] CADMCOMW::GetPids failed, hr 0x%08x\n`
- `0x18000a41c`: `[InitComAdmindata] Error initialize MDCOM object.  hr = %x\n`
- `0x18000a44b`: `[InitComAdmindata] Error initialize AboWrapper.  hr = %x\n`
- `0x18000a527`: `[InitComAdmindata] CADMCOMSrvFactoryW failed, error %lx\n`
- `0x18000a4ce`: `[InitComAdmindata] CoRegisterClassObject failed, error %lx\n`

## pseudocode

```c
__int64 __fastcall InitComAdmindata(__int64 a1)
{
  signed int LastError; // eax
  signed int v3; // eax
  int v4; // eax
  int Pids; // eax
  int v6; // eax
  int v7; // eax
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  DWORD v10; // eax
  signed int v11; // ebx
  DWORD v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // ebx
  HRESULT Instance; // [rsp+40h] [rbp-59h] BYREF
  DWORD cbSid[3]; // [rsp+44h] [rbp-55h] BYREF
  _AUTHZ_SOURCE_SCHEMA_REGISTRATION pRegistration; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v19[32]; // [rsp+A0h] [rbp+7h] BYREF
  WCHAR *v20; // [rsp+C0h] [rbp+27h]

  Instance = 0;
  memset_0(&pRegistration, 0, sizeof(pRegistration));
  STRU::STRU((STRU *)v19);
  g_pDebug = PuCreateDebugPrintsObject("coadmin", 1);
  if ( !g_pDebug )
    OutputDebugStringA("Unable to Create Debug Print Object \n");
  g_dwDebugFlags = PuLoadDebugFlagsFromRegStr("System\\CurrentControlSet\\Services\\iisadmin\\Parameters", 0);
  IISGetPlatformType();
  cbSid[0] = 68;
  if ( InitializeSecurityDescriptor(qword_180016FB0, 1u)
    && CreateWellKnownSid(WinLocalSystemSid, 0, qword_180017040, cbSid)
    && InitializeAcl(&pDacl, 0x58u, 2u)
    && AddAccessAllowedAce(&pDacl, 2u, 1u, qword_180017040)
    && SetSecurityDescriptorOwner(qword_180016FB0, qword_180017040, 0)
    && SetSecurityDescriptorGroup(qword_180016FB0, qword_180017040, 0)
    && SetSecurityDescriptorDacl(qword_180016FB0, 1, &pDacl, 0) )
  {
    Instance = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Instance = LastError;
    if ( LastError < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx",
          44,
          "InitComAdmindata",
          "[InitComAdmindata] AdminAclInitAclCache failed, hr 0x%8x\n",
          LastError);
      goto LABEL_52;
    }
  }
  CADMCOMW::InitObjectList();
  g_pEtwCoAdminTracer = (struct CEtwTracer *)a1;
  if ( *(_DWORD *)(a1 + 8) && (*(_BYTE *)(a1 + 40) & 1) != 0 && *(_DWORD *)(a1 + 44) >= 4u )
    CEtwTracer::EtwTraceEvent((CEtwTracer *)a1, (const struct _GUID *)IISAdminStatupGuid, 0xAu);
  if ( AuthzRegisterSecurityEventSource(0, L"IIS-METABASE", &g_hEventProvider) )
    goto LABEL_29;
  Instance = STRU::Copy((STRU *)v19, L"%SystemRoot%");
  if ( Instance < 0 )
    goto LABEL_52;
  Instance = STRU::Append((STRU *)v19, L"\\system32\\inetsrv\\iisres.dll");
  if ( Instance < 0 )
    goto LABEL_52;
  pRegistration.szEventMessageFile = v20;
  pRegistration.dwFlags = 1;
  pRegistration.szEventSourceName = (PWSTR)L"IIS-METABASE";
  if ( AuthzInstallSecurityEventSource(0, &pRegistration)
    && AuthzRegisterSecurityEventSource(0, L"IIS-METABASE", &g_hEventProvider) )
  {
LABEL_29:
    v4 = COpenHandle::Init((COpenHandle *)&g_ohMasterRootHandle, 0, &byte_1800127D8, &byte_1800127D8);
    Instance = v4;
    if ( v4 >= 0 )
    {
      Pids = CADMCOMW::GetPids();
      Instance = Pids;
      if ( Pids >= 0 )
      {
        Instance = CoCreateInstance(&CLSID_MDCOM, 0, 1u, &IID_IMDCOM3, &g_pcCom);
        if ( Instance >= 0 )
        {
          v6 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)g_pcCom + 24LL))(g_pcCom);
          Instance = v6;
          if ( v6 >= 0 )
          {
            v7 = CADMCOMW::InitializeAboWrapper();
            Instance = v7;
            if ( v7 >= 0 )
            {
              v8 = operator new(0x10u);
              v9 = v8;
              if ( v8 )
              {
                v8[2] = 1;
                *(_QWORD *)v8 = &CADMCOMSrvFactoryW::`vftable';
                Instance = CoRegisterClassObject(&CLSID_MSAdminBase_W, (LPUNKNOWN)v8, 0x15u, 1u, &g_dwComRegisterW);
                if ( Instance < 0 && (g_dwDebugFlags & 3) != 0 )
                {
                  v10 = GetLastError();
                  PuDbgPrint(
                    g_pDebug,
                    "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx",
                    176,
                    "InitComAdmindata",
                    "[InitComAdmindata] CoRegisterClassObject failed, error %lx\n",
                    v10);
                }
                (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
              }
              else
              {
                v11 = GetLastError();
                if ( (g_dwDebugFlags & 3) != 0 )
                {
                  v12 = GetLastError();
                  PuDbgPrint(
                    g_pDebug,
                    "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx",
                    165,
                    "InitComAdmindata",
                    "[InitComAdmindata] CADMCOMSrvFactoryW failed, error %lx\n",
                    v12);
                }
                if ( v11 > 0 )
                  v11 = (unsigned __int16)v11 | 0x80070000;
                Instance = v11;
              }
            }
            else if ( (g_dwDebugFlags & 3) != 0 )
            {
              PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx",
                155,
                "InitComAdmindata",
                "[InitComAdmindata] Error initialize AboWrapper.  hr = %x\n",
                v7);
            }
          }
          else if ( (g_dwDebugFlags & 3) != 0 )
          {
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx",
              146,
              "InitComAdmindata",
              "[InitComAdmindata] Error initialize MDCOM object.  hr = %x\n",
              v6);
          }
        }
      }
      else if ( (g_dwDebugFlags & 3) != 0 )
      {
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx",
          131,
          "InitComAdmindata",
          "[InitComAdmindata] CADMCOMW::GetPids failed, hr 0x%08x\n",
          Pids);
      }
    }
    else if ( (g_dwDebugFlags & 3) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx",
        121,
        "InitComAdmindata",
        "[InitComAdmindata] g_ohMasterRootHandle.Init failed, hr 0x%8x\n",
        v4);
    }
  }
  else
  {
    v3 = GetLastError();
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    Instance = v3;
  }
LABEL_52:
  if ( Instance >= 0 )
    goto LABEL_64;
  if ( *((_DWORD *)g_pEtwCoAdminTracer + 2)
    && (*((_BYTE *)g_pEtwCoAdminTracer + 40) & 1) != 0
    && *((_DWORD *)g_pEtwCoAdminTracer + 11) )
  {
    CEtwTracer::EtwTraceEvent(g_pEtwCoAdminTracer, (const struct _GUID *)IISAdminStatupGuid, 0xBu, &Instance, 4, 0, 0);
  }
  _InterlockedDecrement((volatile signed __int32 *)&g_AclCache);
  CAdminAclCache::Flush((CAdminAclCache *)&g_AclCache);
  if ( g_dwComRegisterW )
  {
    CoRevokeClassObject(g_dwComRegisterW);
    g_dwComRegisterW = 0;
  }
  if ( g_pcCom )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)g_pcCom + 520LL))(g_pcCom);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)g_pcCom + 512LL))(g_pcCom);
  }
  CADMCOMW::ShutDownObjects();
  CADMCOMW::TerminateObjectList();
  if ( g_pcCom )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)g_pcCom + 40LL))(g_pcCom);
    (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)g_pcCom + 32LL))(g_pcCom, 0);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)g_pcCom + 16LL))(g_pcCom);
    g_pcCom = 0;
  }
  v13 = 0;
  if ( Instance >= 0 )
LABEL_64:
    v13 = 1;
  g_bInitialized = v13;
  if ( *((_DWORD *)g_pEtwCoAdminTracer + 2)
    && (*((_BYTE *)g_pEtwCoAdminTracer + 40) & 1) != 0
    && *((_DWORD *)g_pEtwCoAdminTracer + 11) >= 4u )
  {
    CEtwTracer::EtwTraceEvent(g_pEtwCoAdminTracer, (const struct _GUID *)IISAdminStatupGuid, 0xCu);
  }
  v14 = Instance;
  STRU::~STRU((STRU *)v19);
  return v14;
}

```

## disassembly

```asm
0x18000a0b0  mov     [rsp-8+arg_8], rbx
0x18000a0b5  mov     [rsp-8+arg_10], rsi
0x18000a0ba  push    rbp
0x18000a0bb  push    rdi
0x18000a0bc  push    r14
0x18000a0be  lea     rbp, [rsp-47h]
0x18000a0c3  sub     rsp, 0E0h
0x18000a0ca  mov     rax, cs:__security_cookie
0x18000a0d1  xor     rax, rsp
0x18000a0d4  mov     [rbp+57h+var_18], rax
0x18000a0d8  xor     edi, edi
0x18000a0da  mov     rbx, rcx
0x18000a0dd  xor     edx, edx; Val
0x18000a0df  mov     [rbp+57h+var_B0], edi
0x18000a0e2  lea     rcx, [rbp+57h+pRegistration]; void *
0x18000a0e6  lea     r8d, [rdi+50h]; Size
0x18000a0ea  call    memset_0
0x18000a0ef  lea     rcx, [rbp+57h+var_50]
0x18000a0f3  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000a0f9  lea     esi, [rdi+1]
0x18000a0fc  mov     edx, esi
0x18000a0fe  lea     rcx, aCoadmin; "coadmin"
0x18000a105  call    cs:__imp_PuCreateDebugPrintsObject
0x18000a10b  mov     cs:g_pDebug, rax
0x18000a112  test    rax, rax
0x18000a115  jnz     short loc_18000A124
0x18000a117  lea     rcx, OutputString; "Unable to Create Debug Print Object \n"
0x18000a11e  call    cs:__imp_OutputDebugStringA
0x18000a124  xor     edx, edx
0x18000a126  lea     rcx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\ii"...
0x18000a12d  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x18000a133  mov     cs:g_dwDebugFlags, eax
0x18000a139  call    cs:__imp_IISGetPlatformType
0x18000a13f  mov     edx, esi; dwRevision
0x18000a141  mov     [rbp+57h+cbSid], 44h ; 'D'
0x18000a148  lea     rcx, qword_180016FB0; pSecurityDescriptor
0x18000a14f  call    cs:__imp_InitializeSecurityDescriptor
0x18000a155  mov     r14d, 80070000h
0x18000a15b  test    eax, eax
0x18000a15d  jz      loc_18000A20E
0x18000a163  xor     edx, edx; DomainSid
0x18000a165  lea     r9, [rbp+57h+cbSid]; cbSid
0x18000a169  lea     r8, qword_180017040; pSid
0x18000a170  lea     ecx, [rdx+16h]; WellKnownSidType
0x18000a173  call    cs:__imp_CreateWellKnownSid
0x18000a179  test    eax, eax
0x18000a17b  jz      loc_18000A20E
0x18000a181  mov     edx, 58h ; 'X'; nAclLength
0x18000a186  lea     rcx, pDacl; pAcl
0x18000a18d  lea     r8d, [rdx-56h]; dwAclRevision
0x18000a191  call    cs:__imp_InitializeAcl
0x18000a197  test    eax, eax
0x18000a199  jz      short loc_18000A20E
0x18000a19b  lea     r9, qword_180017040; pSid
0x18000a1a2  mov     r8d, esi; AccessMask
0x18000a1a5  mov     edx, 2; dwAceRevision
0x18000a1aa  lea     rcx, pDacl; pAcl
0x18000a1b1  call    cs:__imp_AddAccessAllowedAce
0x18000a1b7  test    eax, eax
0x18000a1b9  jz      short loc_18000A20E
0x18000a1bb  xor     r8d, r8d; bOwnerDefaulted
0x18000a1be  lea     rdx, qword_180017040; pOwner
0x18000a1c5  lea     rcx, qword_180016FB0; pSecurityDescriptor
0x18000a1cc  call    cs:__imp_SetSecurityDescriptorOwner
0x18000a1d2  test    eax, eax
0x18000a1d4  jz      short loc_18000A20E
0x18000a1d6  xor     r8d, r8d; bGroupDefaulted
0x18000a1d9  lea     rdx, qword_180017040; pGroup
0x18000a1e0  lea     rcx, qword_180016FB0; pSecurityDescriptor
0x18000a1e7  call    cs:__imp_SetSecurityDescriptorGroup
0x18000a1ed  test    eax, eax
0x18000a1ef  jz      short loc_18000A20E
0x18000a1f1  xor     r9d, r9d; bDaclDefaulted
0x18000a1f4  lea     r8, pDacl; pDacl
0x18000a1fb  mov     edx, esi; bDaclPresent
0x18000a1fd  lea     rcx, qword_180016FB0; pSecurityDescriptor
0x18000a204  call    cs:__imp_SetSecurityDescriptorDacl
0x18000a20a  test    eax, eax
0x18000a20c  jnz     short loc_18000A268
0x18000a20e  call    cs:__imp_GetLastError
0x18000a214  test    eax, eax
0x18000a216  jle     short loc_18000A21E
0x18000a218  movzx   eax, ax
0x18000a21b  or      eax, r14d
0x18000a21e  mov     [rbp+57h+var_B0], eax
0x18000a221  test    eax, eax
0x18000a223  jns     short loc_18000A26B
0x18000a225  test    byte ptr cs:g_dwDebugFlags, 3
0x18000a22c  jz      loc_18000A54C
0x18000a232  mov     dword ptr [rsp+0F0h+var_C8], eax
0x18000a236  mov     r8d, 2Ch ; ','
0x18000a23c  lea     rax, aInitcomadminda_6; "[InitComAdmindata] AdminAclInitAclCache"...
0x18000a243  mov     rcx, cs:g_pDebug
0x18000a24a  lea     r9, aInitcomadminda_2; "InitComAdmindata"
0x18000a251  lea     rdx, aInetsrvIisMbCo_1; "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx"
0x18000a258  mov     [rsp+0F0h+ppv], rax
0x18000a25d  call    cs:__imp_PuDbgPrint
0x18000a263  jmp     loc_18000A54C
0x18000a268  mov     [rbp+57h+var_B0], edi
0x18000a26b  call    ?InitObjectList@CADMCOMW@@SAXXZ; CADMCOMW::InitObjectList(void)
0x18000a270  mov     cs:?g_pEtwCoAdminTracer@@3PEAVCEtwTracer@@EA, rbx; CEtwTracer * g_pEtwCoAdminTracer
0x18000a277  cmp     [rbx+8], edi
0x18000a27a  jz      short loc_18000A2A4
0x18000a27c  test    [rbx+28h], sil
0x18000a280  jz      short loc_18000A2A4
0x18000a282  cmp     dword ptr [rbx+2Ch], 4
0x18000a286  jb      short loc_18000A2A4
0x18000a288  xor     r9d, r9d
0x18000a28b  mov     [rsp+0F0h+ppv], rdi
0x18000a290  lea     rdx, IISAdminStatupGuid
0x18000a297  mov     rcx, rbx
0x18000a29a  lea     r8d, [r9+0Ah]
0x18000a29e  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x18000a2a4  lea     rbx, szEventSourceName; "IIS-METABASE"
0x18000a2ab  xor     ecx, ecx; dwFlags
0x18000a2ad  mov     rdx, rbx; szEventSourceName
0x18000a2b0  lea     r8, ?g_hEventProvider@@3PEAUAUTHZ_SECURITY_EVENT_PROVIDER_HANDLE__@@EA; phEventProvider
0x18000a2b7  call    cs:__imp_AuthzRegisterSecurityEventSource
0x18000a2bd  test    eax, eax
0x18000a2bf  jnz     loc_18000A34A
0x18000a2c5  lea     rdx, aSystemroot; "%SystemRoot%"
0x18000a2cc  lea     rcx, [rbp+57h+var_50]
0x18000a2d0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000a2d6  mov     [rbp+57h+var_B0], eax
0x18000a2d9  test    eax, eax
0x18000a2db  js      loc_18000A54C
0x18000a2e1  lea     rdx, aSystem32Inetsr; "\\system32\\inetsrv\\iisres.dll"
0x18000a2e8  lea     rcx, [rbp+57h+var_50]
0x18000a2ec  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000a2f2  mov     [rbp+57h+var_B0], eax
0x18000a2f5  test    eax, eax
0x18000a2f7  js      loc_18000A54C
0x18000a2fd  mov     rax, [rbp+57h+var_30]
0x18000a301  lea     rdx, [rbp+57h+pRegistration]; pRegistration
0x18000a305  xor     ecx, ecx; dwFlags
0x18000a307  mov     [rbp+57h+pRegistration.szEventMessageFile], rax
0x18000a30b  mov     [rbp+57h+pRegistration.dwFlags], esi
0x18000a30e  mov     [rbp+57h+pRegistration.szEventSourceName], rbx
0x18000a312  call    cs:__imp_AuthzInstallSecurityEventSource
0x18000a318  test    eax, eax
0x18000a31a  jnz     short loc_18000A334
0x18000a31c  call    cs:__imp_GetLastError
0x18000a322  test    eax, eax
0x18000a324  jle     short loc_18000A32C
0x18000a326  movzx   eax, ax
0x18000a329  or      eax, r14d
0x18000a32c  mov     [rbp+57h+var_B0], eax
0x18000a32f  jmp     loc_18000A54C
0x18000a334  lea     r8, ?g_hEventProvider@@3PEAUAUTHZ_SECURITY_EVENT_PROVIDER_HANDLE__@@EA; phEventProvider
0x18000a33b  mov     rdx, rbx; szEventSourceName
0x18000a33e  xor     ecx, ecx; dwFlags
0x18000a340  call    cs:__imp_AuthzRegisterSecurityEventSource
0x18000a346  test    eax, eax
0x18000a348  jz      short loc_18000A31C
0x18000a34a  lea     r8, byte_1800127D8; unsigned __int16 *
0x18000a351  xor     edx, edx; unsigned int
0x18000a353  mov     r9, r8; unsigned __int16 *
0x18000a356  lea     rcx, ?g_ohMasterRootHandle@@3VCOpenHandle@@A; this
0x18000a35d  call    ?Init@COpenHandle@@QEAAJKPEBG0@Z; COpenHandle::Init(ulong,ushort const *,ushort const *)
0x18000a362  mov     [rbp+57h+var_B0], eax
0x18000a365  test    eax, eax
0x18000a367  jns     short loc_18000A38C
0x18000a369  test    byte ptr cs:g_dwDebugFlags, 3
0x18000a370  jz      loc_18000A54C
0x18000a376  mov     dword ptr [rsp+0F0h+var_C8], eax
0x18000a37a  mov     r8d, 79h ; 'y'
0x18000a380  lea     rax, aInitcomadminda_5; "[InitComAdmindata] g_ohMasterRootHandle"...
0x18000a387  jmp     loc_18000A243
0x18000a38c  call    ?GetPids@CADMCOMW@@SAJXZ; CADMCOMW::GetPids(void)
0x18000a391  mov     [rbp+57h+var_B0], eax
0x18000a394  test    eax, eax
0x18000a396  jns     short loc_18000A3BB
0x18000a398  test    byte ptr cs:g_dwDebugFlags, 3
0x18000a39f  jz      loc_18000A54C
0x18000a3a5  mov     dword ptr [rsp+0F0h+var_C8], eax
0x18000a3a9  mov     r8d, 83h
0x18000a3af  lea     rax, aInitcomadminda_7; "[InitComAdmindata] CADMCOMW::GetPids fa"...
0x18000a3b6  jmp     loc_18000A243
0x18000a3bb  lea     rax, ?g_pcCom@@3PEAUIMDCOM3@@EA; IMDCOM3 * g_pcCom
0x18000a3c2  mov     r8d, esi; dwClsContext
0x18000a3c5  lea     r9, IID_IMDCOM3; riid
0x18000a3cc  mov     [rsp+0F0h+ppv], rax; ppv
0x18000a3d1  xor     edx, edx; pUnkOuter
0x18000a3d3  lea     rcx, CLSID_MDCOM; rclsid
0x18000a3da  call    cs:__imp_CoCreateInstance
0x18000a3e0  mov     [rbp+57h+var_B0], eax
0x18000a3e3  test    eax, eax
0x18000a3e5  js      loc_18000A54C
0x18000a3eb  mov     rcx, cs:?g_pcCom@@3PEAUIMDCOM3@@EA; IMDCOM3 * g_pcCom
0x18000a3f2  mov     rax, [rcx]
0x18000a3f5  mov     rax, [rax+18h]
0x18000a3f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3fe  mov     [rbp+57h+var_B0], eax
0x18000a401  test    eax, eax
0x18000a403  jns     short loc_18000A428
0x18000a405  test    byte ptr cs:g_dwDebugFlags, 3
0x18000a40c  jz      loc_18000A54C
0x18000a412  mov     dword ptr [rsp+0F0h+var_C8], eax
0x18000a416  mov     r8d, 92h
0x18000a41c  lea     rax, aInitcomadminda_0; "[InitComAdmindata] Error initialize MDC"...
0x18000a423  jmp     loc_18000A243
0x18000a428  call    ?InitializeAboWrapper@CADMCOMW@@SAJXZ; CADMCOMW::InitializeAboWrapper(void)
0x18000a42d  mov     [rbp+57h+var_B0], eax
0x18000a430  test    eax, eax
0x18000a432  jns     short loc_18000A457
0x18000a434  test    byte ptr cs:g_dwDebugFlags, 3
0x18000a43b  jz      loc_18000A54C
0x18000a441  mov     dword ptr [rsp+0F0h+var_C8], eax
0x18000a445  mov     r8d, 9Bh
0x18000a44b  lea     rax, aInitcomadminda_3; "[InitComAdmindata] Error initialize Abo"...
0x18000a452  jmp     loc_18000A243
0x18000a457  mov     ecx, 10h; Size
0x18000a45c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a461  mov     rbx, rax
0x18000a464  test    rax, rax
0x18000a467  jz      loc_18000A4F7
0x18000a46d  lea     rax, ??_7CADMCOMSrvFactoryW@@6B@; const CADMCOMSrvFactoryW::`vftable'
0x18000a474  mov     [rbx+8], esi
0x18000a477  mov     [rbx], rax
0x18000a47a  lea     rcx, CLSID_MSAdminBase_W; rclsid
0x18000a481  lea     rax, ?g_dwComRegisterW@@3KA; ulong g_dwComRegisterW
0x18000a488  mov     r9d, esi; flags
0x18000a48b  mov     r8d, 15h; dwClsContext
0x18000a491  mov     [rsp+0F0h+ppv], rax; lpdwRegister
0x18000a496  mov     rdx, rbx; pUnk
0x18000a499  call    cs:__imp_CoRegisterClassObject
0x18000a49f  mov     [rbp+57h+var_B0], eax
0x18000a4a2  test    eax, eax
0x18000a4a4  jns     short loc_18000A4E6
0x18000a4a6  test    byte ptr cs:g_dwDebugFlags, 3
0x18000a4ad  jz      short loc_18000A4E6
0x18000a4af  call    cs:__imp_GetLastError
0x18000a4b5  mov     rcx, cs:g_pDebug
0x18000a4bc  lea     r9, aInitcomadminda_2; "InitComAdmindata"
0x18000a4c3  mov     dword ptr [rsp+0F0h+var_C8], eax
0x18000a4c7  lea     rdx, aInetsrvIisMbCo_1; "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx"
0x18000a4ce  lea     rax, aInitcomadminda_4; "[InitComAdmindata] CoRegisterClassObjec"...
0x18000a4d5  mov     r8d, 0B0h
0x18000a4db  mov     [rsp+0F0h+ppv], rax
0x18000a4e0  call    cs:__imp_PuDbgPrint
0x18000a4e6  mov     rax, [rbx]
0x18000a4e9  mov     rcx, rbx
0x18000a4ec  mov     rax, [rax+10h]
0x18000a4f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4f5  jmp     short loc_18000A54C
0x18000a4f7  call    cs:__imp_GetLastError
0x18000a4fd  test    byte ptr cs:g_dwDebugFlags, 3
0x18000a504  mov     ebx, eax
0x18000a506  jz      short loc_18000A53F
0x18000a508  call    cs:__imp_GetLastError
0x18000a50e  mov     rcx, cs:g_pDebug
0x18000a515  lea     r9, aInitcomadminda_2; "InitComAdmindata"
0x18000a51c  mov     dword ptr [rsp+0F0h+var_C8], eax
0x18000a520  lea     rdx, aInetsrvIisMbCo_1; "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx"
0x18000a527  lea     rax, aInitcomadminda_1; "[InitComAdmindata] CADMCOMSrvFactoryW f"...
0x18000a52e  mov     r8d, 0A5h
0x18000a534  mov     [rsp+0F0h+ppv], rax
0x18000a539  call    cs:__imp_PuDbgPrint
0x18000a53f  test    ebx, ebx
0x18000a541  jle     short loc_18000A549
0x18000a543  movzx   ebx, bx
0x18000a546  or      ebx, r14d
0x18000a549  mov     [rbp+57h+var_B0], ebx
0x18000a54c  cmp     [rbp+57h+var_B0], edi
0x18000a54f  jge     loc_18000A64E
0x18000a555  mov     rcx, cs:?g_pEtwCoAdminTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwCoAdminTracer
0x18000a55c  cmp     [rcx+8], edi
0x18000a55f  jz      short loc_18000A596
0x18000a561  test    [rcx+28h], sil
0x18000a565  jz      short loc_18000A596
0x18000a567  cmp     [rcx+2Ch], esi
0x18000a56a  jb      short loc_18000A596
0x18000a56c  mov     [rsp+0F0h+var_C0], rdi
0x18000a571  lea     r9, [rbp+57h+var_B0]
0x18000a575  mov     [rsp+0F0h+var_C8], rdi
0x18000a57a  lea     rdx, IISAdminStatupGuid
0x18000a581  mov     r8d, 0Bh
0x18000a587  mov     [rsp+0F0h+ppv], 4
0x18000a590  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x18000a596  lock dec cs:?g_AclCache@@3VCAdminAclCache@@A; CAdminAclCache g_AclCache
0x18000a59d  lea     rcx, ?g_AclCache@@3VCAdminAclCache@@A; this
0x18000a5a4  call    ?Flush@CAdminAclCache@@QEAAJXZ; CAdminAclCache::Flush(void)
0x18000a5a9  mov     ecx, cs:?g_dwComRegisterW@@3KA; dwRegister
0x18000a5af  test    ecx, ecx
0x18000a5b1  jz      short loc_18000A5BF
0x18000a5b3  call    cs:__imp_CoRevokeClassObject
0x18000a5b9  mov     cs:?g_dwComRegisterW@@3KA, edi; ulong g_dwComRegisterW
0x18000a5bf  mov     rcx, cs:?g_pcCom@@3PEAUIMDCOM3@@EA; IMDCOM3 * g_pcCom
0x18000a5c6  test    rcx, rcx
0x18000a5c9  jz      short loc_18000A5F0
0x18000a5cb  mov     rax, [rcx]
0x18000a5ce  mov     rax, [rax+208h]
0x18000a5d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5da  mov     rcx, cs:?g_pcCom@@3PEAUIMDCOM3@@EA; IMDCOM3 * g_pcCom
0x18000a5e1  mov     rax, [rcx]
0x18000a5e4  mov     rax, [rax+200h]
0x18000a5eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5f0  call    ?ShutDownObjects@CADMCOMW@@SAXXZ; CADMCOMW::ShutDownObjects(void)
0x18000a5f5  call    ?TerminateObjectList@CADMCOMW@@SAXXZ; CADMCOMW::TerminateObjectList(void)
0x18000a5fa  mov     rcx, cs:?g_pcCom@@3PEAUIMDCOM3@@EA; IMDCOM3 * g_pcCom
  ... truncated ...
```
