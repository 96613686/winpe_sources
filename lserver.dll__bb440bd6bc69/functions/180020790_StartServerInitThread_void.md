# StartServerInitThread(void *)

- ea: `0x180020790`
- end: `0x180020b6b`
- name: `?StartServerInitThread@@YAKPEAX@Z`
- size: `987`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000205c`
- `0x18000bb98`
- `0x180020284`
- `0x180020614`
- `0x180020790`
- `0x180020cb4`
- `0x180022910`
- `0x180031408`
- `0x1800648e4`
- `0x180078610`
- `0x18007d56c`
- `0x18007e360`
- `0x18007e4d8`
- `0x18007eff0`
- `0x18007f408`
- `0x1800a5010`

## import_xrefs

- `mstlsapi!__imp_TLSInit` at `0x180020816`
- `mstlsapi!__imp_TLSInit` at `0x180020816`
- `mstlsapi!__imp_TLSInDomain` at `0x1800209b9`
- `mstlsapi!__imp_TLSInDomain` at `0x1800209b9`
- `KERNEL32!ExitThread` at `0x180020b5e`
- `KERNEL32!ExitThread` at `0x180020b5e`
- `KERNEL32!GetVersion` at `0x1800209a1`
- `KERNEL32!GetVersion` at `0x1800209a1`
- `KERNEL32!LocalAlloc` at `0x180020a0d`
- `KERNEL32!LocalAlloc` at `0x180020a0d`
- `lstelemetry!RegisterAndEnableLicensingTelemetry` at `0x180020b50`
- `lstelemetry!RegisterAndEnableLicensingTelemetry` at `0x180020b50`
- `lstelemetry!InitRDLSTelemetryCommonData` at `0x1800209ef`
- `lstelemetry!InitRDLSTelemetryCommonData` at `0x1800209ef`
- `TlsBrand!UpdateRDLSConfig` at `0x18002083d`
- `TlsBrand!UpdateRDLSConfig` at `0x18002083d`
- `TlsBrand!LoadRDLSConfig` at `0x180020849`
- `TlsBrand!LoadRDLSConfig` at `0x180020849`

## string_xrefs

- `0x18002087e`: `CRdlsSecretsCache`

## pseudocode

```c
__int64 __fastcall StartServerInitThread(PVOID Parameter)
{
  CRdlsDBManager *v2; // rax
  const wchar_t *v3; // r8
  DWORD started; // ebx
  int v6; // edx
  CRdlsDBManager *v7; // rcx
  int v8; // r8d
  RdlsSecretsCache *v9; // rcx
  int v10; // eax
  CRdlsDBManager *v11; // rcx
  unsigned int v12; // edx
  unsigned __int16 *v13; // rcx
  struct IRdlsDB *DBInstance; // rax
  unsigned __int16 *v15; // rcx
  DWORD Version; // ebx
  __int64 v17; // rcx
  HLOCAL v18; // rax
  __int64 v19; // rcx
  CRdlsDBManager *v20; // rcx
  int v21; // r8d
  struct _EVENT_DESCRIPTOR v22; // [rsp+30h] [rbp-10h] BYREF
  CRdlsDBManager *v23; // [rsp+50h] [rbp+10h] BYREF

  v2 = CRdlsDBManager::m_DBManager;
  if ( !CRdlsDBManager::m_DBManager )
  {
    v2 = (CRdlsDBManager *)operator new(0xAF0u);
    v23 = v2;
    if ( v2 )
      v2 = CRdlsDBManager::CRdlsDBManager(v2);
    CRdlsDBManager::m_DBManager = v2;
  }
  g_RdlsDBManager = (LPBYTE)v2;
  if ( v2 )
  {
    TLSInit();
    started = TLSLoadRuntimeParameters();
    if ( started )
      goto LABEL_40;
    CRdlsDBManager::Initialize((CRdlsDBManager *)g_RdlsDBManager);
    UpdateRDLSConfig();
    LoadRDLSConfig();
    started = CRdlsDBManager::StartRdlsDBWorkspaceEngine(v7, v6, v8);
    if ( started )
      goto LABEL_40;
    v9 = (RdlsSecretsCache *)*((_QWORD *)g_RdlsDBManager + 329);
    g_RdlsSecrets = v9;
    if ( !v9 )
    {
      v3 = L"CRdlsSecretsCache";
      goto LABEL_7;
    }
    v10 = (*(__int64 (__fastcall **)(RdlsSecretsCache *, size_t *))(*(_QWORD *)v9 + 72LL))(v9, &g_ServerIDComponents);
    started = -1073676265;
    if ( v10 == -1073676265 )
      goto LABEL_38;
    if ( v10 )
    {
      started = TLSGeneratePid(&String1, &g_ServerIDComponents, &hMem, &dword_1800E8A20);
      if ( started )
      {
        v12 = -1073676263;
LABEL_39:
        v22 = (struct _EVENT_DESCRIPTOR)TLS_E_SERVICEINIT;
        TLSLogEvent(&v22, v12);
        goto LABEL_40;
      }
      if ( (*(unsigned int (__fastcall **)(RdlsSecretsCache *, size_t *, _QWORD, _QWORD))(*(_QWORD *)g_RdlsSecrets + 80LL))(
             g_RdlsSecrets,
             &g_ServerIDComponents,
             0,
             0) )
      {
        started = -1073676264;
LABEL_38:
        v12 = started;
        goto LABEL_39;
      }
    }
    else
    {
      if ( !hMem || !dword_1800E8A20 || !String1 || !(_DWORD)g_ServerIDComponents )
      {
        started = 4096;
        goto LABEL_38;
      }
      DBInstance = CRdlsDBManager::GetDBInstance(v11);
      if ( !(*(unsigned int (__fastcall **)(struct IRdlsDB *))(*(_QWORD *)DBInstance + 40LL))(DBInstance) )
      {
        started = CheckAndUpdatePid();
        if ( started )
          goto LABEL_40;
      }
    }
    TLSReadRegistryValue(v13, L"ProductId", (unsigned __int16 **)&g_pszServerOSPID, &g_cbServerOSPID);
    TLSReadRegistryValue(v15, L"EditionID", (unsigned __int16 **)&g_pszServerEdition, &g_cbServerEdition);
    Version = GetVersion();
    LODWORD(v23) = 0;
    TLSInDomain(&v23, 0);
    InitRDLSTelemetryCommonData(
      Version,
      (unsigned __int16 *)g_pszServerOSPID,
      (unsigned __int16 *)g_pszServerEdition,
      (unsigned __int16 *)String1,
      (unsigned __int16 *)Src,
      (_DWORD)v23);
    LicenseGetSecretKey(v17, 0);
    v18 = LocalAlloc(0x40u, (unsigned int)g_cbSecretKey);
    g_pbSecretKey = v18;
    if ( !v18 )
    {
      started = 4117;
      goto LABEL_38;
    }
    if ( (unsigned int)LicenseGetSecretKey(v19, v18) )
    {
      started = -1073676266;
      goto LABEL_38;
    }
    ServiceLoadAllPolicyModule();
    started = CRdlsDBManager::PerformPostRdlsDBInit(v20, Parameter == 0, v21);
    if ( !started )
    {
      if ( !(*(unsigned int (__fastcall **)(RdlsSecretsCache *, __int64))(*(_QWORD *)g_RdlsSecrets + 40LL))(
              g_RdlsSecrets,
              1) )
      {
        if ( (*(unsigned int (__fastcall **)(RdlsSecretsCache *, __int64))(*(_QWORD *)g_RdlsSecrets + 40LL))(
               g_RdlsSecrets,
               2) == 2
          && (*(unsigned int (__fastcall **)(RdlsSecretsCache *, __int64, __int64))(*(_QWORD *)g_RdlsSecrets + 56LL))(
               g_RdlsSecrets,
               1,
               2) )
        {
          CrimsonHelper::RaiseEventInternal((CrimsonHelper *)CrimsonHelper::s_instance, &TLS_W_BACKUPCERTIFICATE, 0, 0);
        }
        if ( (*(unsigned int (__fastcall **)(RdlsSecretsCache *, __int64))(*(_QWORD *)g_RdlsSecrets + 40LL))(
               g_RdlsSecrets,
               3) == 2
          && (*(unsigned int (__fastcall **)(RdlsSecretsCache *, __int64, __int64))(*(_QWORD *)g_RdlsSecrets + 56LL))(
               g_RdlsSecrets,
               1,
               3) )
        {
          CrimsonHelper::RaiseEventInternal((CrimsonHelper *)CrimsonHelper::s_instance, &TLS_W_BACKUPCERTIFICATE, 0, 0);
        }
      }
      started = 0;
    }
LABEL_40:
    RegisterAndEnableLicensingTelemetry();
    ExitThread(started);
  }
  v3 = L"CRdlsDBManager";
LABEL_7:
  v22 = (struct _EVENT_DESCRIPTOR)TLS_E_SERVICEINIT;
  TLSLogEvent(&v22, 0xC001001B, v3);
  return 3221291035LL;
}

```

## disassembly

```asm
0x180020790  mov     [rsp-8+arg_8], rbx
0x180020795  mov     [rsp-8+arg_10], rdi
0x18002079a  push    rbp
0x18002079b  mov     rbp, rsp
0x18002079e  sub     rsp, 40h
0x1800207a2  mov     rdi, rcx
0x1800207a5  mov     rax, cs:?m_DBManager@CRdlsDBManager@@0PEAV1@EA; CRdlsDBManager * CRdlsDBManager::m_DBManager
0x1800207ac  test    rax, rax
0x1800207af  jnz     short loc_1800207D4
0x1800207b1  mov     ecx, 0AF0h; Size
0x1800207b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800207bb  mov     [rbp+arg_0], rax
0x1800207bf  test    rax, rax
0x1800207c2  jz      short loc_1800207CD
0x1800207c4  mov     rcx, rax; this
0x1800207c7  call    ??0CRdlsDBManager@@AEAA@XZ; CRdlsDBManager::CRdlsDBManager(void)
0x1800207cc  nop
0x1800207cd  mov     cs:?m_DBManager@CRdlsDBManager@@0PEAV1@EA, rax; CRdlsDBManager * CRdlsDBManager::m_DBManager
0x1800207d4  mov     cs:?g_RdlsDBManager@@3PEAVCRdlsDBManager@@EA, rax; CRdlsDBManager * g_RdlsDBManager
0x1800207db  test    rax, rax
0x1800207de  jnz     short loc_180020816
0x1800207e0  lea     r8, aCrdlsdbmanager; "CRdlsDBManager"
0x1800207e7  movups  xmm0, cs:TLS_E_SERVICEINIT
0x1800207ee  movdqu  xmmword ptr [rbp+var_10.Id], xmm0
0x1800207f3  mov     ebx, 0C001001Bh
0x1800207f8  mov     edx, ebx; unsigned int
0x1800207fa  lea     rcx, [rbp+var_10]; struct _EVENT_DESCRIPTOR
0x1800207fe  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x180020803  mov     eax, ebx
0x180020805  mov     rbx, [rsp+40h+arg_8]
0x18002080a  mov     rdi, [rsp+40h+arg_10]
0x18002080f  add     rsp, 40h
0x180020813  pop     rbp
0x180020814  retn
0x180020816  call    cs:__imp_TLSInit
0x18002081d  nop     dword ptr [rax+rax+00h]
0x180020822  call    ?TLSLoadRuntimeParameters@@YAKXZ; TLSLoadRuntimeParameters(void)
0x180020827  mov     ebx, eax
0x180020829  test    eax, eax
0x18002082b  jnz     loc_180020B50
0x180020831  mov     rcx, cs:?g_RdlsDBManager@@3PEAVCRdlsDBManager@@EA; this
0x180020838  call    ?Initialize@CRdlsDBManager@@QEAAKXZ; CRdlsDBManager::Initialize(void)
0x18002083d  call    cs:__imp_UpdateRDLSConfig
0x180020844  nop     dword ptr [rax+rax+00h]
0x180020849  call    cs:__imp_LoadRDLSConfig
0x180020850  nop     dword ptr [rax+rax+00h]
0x180020855  call    ?StartRdlsDBWorkspaceEngine@CRdlsDBManager@@QEAAKHH@Z; CRdlsDBManager::StartRdlsDBWorkspaceEngine(int,int)
0x18002085a  mov     ebx, eax
0x18002085c  test    eax, eax
0x18002085e  jnz     loc_180020B50
0x180020864  mov     rax, cs:?g_RdlsDBManager@@3PEAVCRdlsDBManager@@EA; CRdlsDBManager * g_RdlsDBManager
0x18002086b  mov     rcx, [rax+0A48h]
0x180020872  mov     cs:?g_RdlsSecrets@@3PEAVRdlsSecretsCache@@EA, rcx; RdlsSecretsCache * g_RdlsSecrets
0x180020879  test    rcx, rcx
0x18002087c  jnz     short loc_18002088A
0x18002087e  lea     r8, aCrdlssecretsca; "CRdlsSecretsCache"
0x180020885  jmp     loc_1800207E7
0x18002088a  mov     rax, [rcx]
0x18002088d  lea     rdx, ?g_ServerIDComponents@@3U_ServerIDComponents@@A; _ServerIDComponents g_ServerIDComponents
0x180020894  mov     rax, [rax+48h]
0x180020898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002089d  mov     ebx, 0C0010017h
0x1800208a2  cmp     eax, ebx
0x1800208a4  jz      loc_180020B39
0x1800208aa  test    eax, eax
0x1800208ac  jz      short loc_18002090D
0x1800208ae  lea     r9, dword_1800E8A20
0x1800208b5  lea     r8, hMem
0x1800208bc  lea     rdx, ?g_ServerIDComponents@@3U_ServerIDComponents@@A; _ServerIDComponents g_ServerIDComponents
0x1800208c3  lea     rcx, String1
0x1800208ca  call    TLSGeneratePid
0x1800208cf  mov     ebx, eax
0x1800208d1  test    eax, eax
0x1800208d3  jz      short loc_1800208DF
0x1800208d5  mov     edx, 0C0010019h
0x1800208da  jmp     loc_180020B3B
0x1800208df  mov     rcx, cs:?g_RdlsSecrets@@3PEAVRdlsSecretsCache@@EA; RdlsSecretsCache * g_RdlsSecrets
0x1800208e6  mov     rax, [rcx]
0x1800208e9  xor     r9d, r9d
0x1800208ec  xor     r8d, r8d
0x1800208ef  lea     rdx, ?g_ServerIDComponents@@3U_ServerIDComponents@@A; _ServerIDComponents g_ServerIDComponents
0x1800208f6  mov     rax, [rax+50h]
0x1800208fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208ff  test    eax, eax
0x180020901  jz      short loc_18002096D
0x180020903  mov     ebx, 0C0010018h
0x180020908  jmp     loc_180020B39
0x18002090d  cmp     cs:hMem, 0
0x180020915  jz      loc_180020B34
0x18002091b  cmp     cs:dword_1800E8A20, 0
0x180020922  jz      loc_180020B34
0x180020928  cmp     cs:String1, 0
0x180020930  jz      loc_180020B34
0x180020936  cmp     cs:?g_ServerIDComponents@@3U_ServerIDComponents@@A, 0; _ServerIDComponents g_ServerIDComponents
0x18002093d  jz      loc_180020B34
0x180020943  call    ?GetDBInstance@CRdlsDBManager@@QEAAPEAVIRdlsDB@@XZ; CRdlsDBManager::GetDBInstance(void)
0x180020948  mov     rdx, rax
0x18002094b  mov     rcx, [rax]
0x18002094e  mov     rax, [rcx+28h]
0x180020952  mov     rcx, rdx
0x180020955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002095a  test    eax, eax
0x18002095c  jnz     short loc_18002096D
0x18002095e  call    ?CheckAndUpdatePid@@YAKXZ; CheckAndUpdatePid(void)
0x180020963  mov     ebx, eax
0x180020965  test    eax, eax
0x180020967  jnz     loc_180020B50
0x18002096d  lea     r9, ?g_cbServerOSPID@@3KA; unsigned int *
0x180020974  lea     r8, ?g_pszServerOSPID@@3PEAGEA; unsigned __int16 **
0x18002097b  lea     rdx, aProductid; "ProductId"
0x180020982  call    ?TLSReadRegistryValue@@YAKPEAG0PEAPEAGPEAK@Z; TLSReadRegistryValue(ushort *,ushort *,ushort * *,ulong *)
0x180020987  lea     r9, ?g_cbServerEdition@@3KA; unsigned int *
0x18002098e  lea     r8, ?g_pszServerEdition@@3PEAGEA; unsigned __int16 **
0x180020995  lea     rdx, aEditionid; "EditionID"
0x18002099c  call    ?TLSReadRegistryValue@@YAKPEAG0PEAPEAGPEAK@Z; TLSReadRegistryValue(ushort *,ushort *,ushort * *,ulong *)
0x1800209a1  call    cs:__imp_GetVersion
0x1800209a8  nop     dword ptr [rax+rax+00h]
0x1800209ad  mov     ebx, eax
0x1800209af  and     dword ptr [rbp+arg_0], 0
0x1800209b3  xor     edx, edx
0x1800209b5  lea     rcx, [rbp+arg_0]
0x1800209b9  call    cs:__imp_TLSInDomain
0x1800209c0  nop     dword ptr [rax+rax+00h]
0x1800209c5  mov     ecx, dword ptr [rbp+arg_0]
0x1800209c8  mov     [rsp+40h+var_18], ecx
0x1800209cc  mov     rcx, cs:Src
0x1800209d3  mov     [rsp+40h+var_20], rcx
0x1800209d8  mov     r9, cs:String1
0x1800209df  mov     r8, cs:?g_pszServerEdition@@3PEAGEA; ushort * g_pszServerEdition
0x1800209e6  mov     rdx, cs:?g_pszServerOSPID@@3PEAGEA; ushort * g_pszServerOSPID
0x1800209ed  mov     ecx, ebx
0x1800209ef  call    cs:__imp_?InitRDLSTelemetryCommonData@@YAKKPEAG000H@Z; InitRDLSTelemetryCommonData(ulong,ushort *,ushort *,ushort *,ushort *,int)
0x1800209f6  nop     dword ptr [rax+rax+00h]
0x1800209fb  xor     edx, edx
0x1800209fd  call    LicenseGetSecretKey
0x180020a02  mov     edx, cs:?g_cbSecretKey@@3KA; uBytes
0x180020a08  mov     ecx, 40h ; '@'; uFlags
0x180020a0d  call    cs:__imp_LocalAlloc
0x180020a14  nop     dword ptr [rax+rax+00h]
0x180020a19  mov     cs:?g_pbSecretKey@@3PEAEEA, rax; uchar * g_pbSecretKey
0x180020a20  test    rax, rax
0x180020a23  jnz     short loc_180020A2F
0x180020a25  mov     ebx, 1015h
0x180020a2a  jmp     loc_180020B39
0x180020a2f  mov     rdx, rax
0x180020a32  call    LicenseGetSecretKey
0x180020a37  test    eax, eax
0x180020a39  jz      short loc_180020A45
0x180020a3b  mov     ebx, 0C0010016h
0x180020a40  jmp     loc_180020B39
0x180020a45  call    ServiceLoadAllPolicyModule
0x180020a4a  xor     edx, edx
0x180020a4c  test    rdi, rdi
0x180020a4f  setz    dl; int
0x180020a52  call    ?PerformPostRdlsDBInit@CRdlsDBManager@@QEAAKHH@Z; CRdlsDBManager::PerformPostRdlsDBInit(int,int)
0x180020a57  mov     ebx, eax
0x180020a59  test    eax, eax
0x180020a5b  jnz     loc_180020B50
0x180020a61  mov     rcx, cs:?g_RdlsSecrets@@3PEAVRdlsSecretsCache@@EA; RdlsSecretsCache * g_RdlsSecrets
0x180020a68  mov     rax, [rcx]
0x180020a6b  lea     edi, [rbx+1]
0x180020a6e  mov     edx, edi
0x180020a70  mov     rax, [rax+28h]
0x180020a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a79  test    eax, eax
0x180020a7b  jz      short loc_180020A84
0x180020a7d  xor     ebx, ebx
0x180020a7f  jmp     loc_180020B50
0x180020a84  mov     rcx, cs:?g_RdlsSecrets@@3PEAVRdlsSecretsCache@@EA; RdlsSecretsCache * g_RdlsSecrets
0x180020a8b  mov     rax, [rcx]
0x180020a8e  mov     ebx, 2
0x180020a93  mov     edx, ebx
0x180020a95  mov     rax, [rax+28h]
0x180020a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a9e  cmp     eax, ebx
0x180020aa0  jnz     short loc_180020AD7
0x180020aa2  mov     rcx, cs:?g_RdlsSecrets@@3PEAVRdlsSecretsCache@@EA; RdlsSecretsCache * g_RdlsSecrets
0x180020aa9  mov     rax, [rcx]
0x180020aac  mov     r8d, ebx
0x180020aaf  mov     edx, edi
0x180020ab1  mov     rax, [rax+38h]
0x180020ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020aba  test    eax, eax
0x180020abc  jz      short loc_180020AD7
0x180020abe  xor     r9d, r9d; struct _EVENT_DATA_DESCRIPTOR *
0x180020ac1  xor     r8d, r8d; unsigned int
0x180020ac4  lea     rdx, TLS_W_BACKUPCERTIFICATE; struct _EVENT_DESCRIPTOR *
0x180020acb  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; this
0x180020ad2  call    ?RaiseEventInternal@CrimsonHelper@@AEAAKAEBU_EVENT_DESCRIPTOR@@KQEAU_EVENT_DATA_DESCRIPTOR@@@Z; CrimsonHelper::RaiseEventInternal(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR * const)
0x180020ad7  mov     rcx, cs:?g_RdlsSecrets@@3PEAVRdlsSecretsCache@@EA; RdlsSecretsCache * g_RdlsSecrets
0x180020ade  mov     rax, [rcx]
0x180020ae1  mov     edx, 3
0x180020ae6  mov     rax, [rax+28h]
0x180020aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020aef  cmp     eax, ebx
0x180020af1  jnz     short loc_180020A7D
0x180020af3  mov     rcx, cs:?g_RdlsSecrets@@3PEAVRdlsSecretsCache@@EA; RdlsSecretsCache * g_RdlsSecrets
0x180020afa  mov     rax, [rcx]
0x180020afd  mov     r8d, 3
0x180020b03  mov     edx, edi
0x180020b05  mov     rax, [rax+38h]
0x180020b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b0e  test    eax, eax
0x180020b10  jz      loc_180020A7D
0x180020b16  xor     r9d, r9d; struct _EVENT_DATA_DESCRIPTOR *
0x180020b19  xor     r8d, r8d; unsigned int
0x180020b1c  lea     rdx, TLS_W_BACKUPCERTIFICATE; struct _EVENT_DESCRIPTOR *
0x180020b23  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; this
0x180020b2a  call    ?RaiseEventInternal@CrimsonHelper@@AEAAKAEBU_EVENT_DESCRIPTOR@@KQEAU_EVENT_DATA_DESCRIPTOR@@@Z; CrimsonHelper::RaiseEventInternal(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR * const)
0x180020b2f  jmp     loc_180020A7D
0x180020b34  mov     ebx, 1000h
0x180020b39  mov     edx, ebx; unsigned int
0x180020b3b  movups  xmm0, cs:TLS_E_SERVICEINIT
0x180020b42  movdqu  xmmword ptr [rbp+var_10.Id], xmm0
0x180020b47  lea     rcx, [rbp+var_10]; struct _EVENT_DESCRIPTOR
0x180020b4b  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x180020b50  call    cs:__imp_?RegisterAndEnableLicensingTelemetry@@YAKXZ; RegisterAndEnableLicensingTelemetry(void)
0x180020b57  nop     dword ptr [rax+rax+00h]
0x180020b5c  mov     ecx, ebx; dwExitCode
0x180020b5e  call    cs:__imp_ExitThread
```
