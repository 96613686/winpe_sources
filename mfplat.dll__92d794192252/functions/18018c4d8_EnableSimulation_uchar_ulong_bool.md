# EnableSimulation(uchar *,ulong,bool *)

- ea: `0x18018c4d8`
- end: `0x18018ca61`
- name: `?EnableSimulation@@YA_NPEAEKPEA_N@Z`
- size: `1417`
- prototype: `bool __fastcall(PVOID pvData, unsigned int, bool *)`
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800dfd98`
- `0x1800f2188`
- `0x1800fcd50`
- `0x18018ae70`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x180082e30`
- `0x1801200d0`
- `0x180120ecc`
- `0x180125918`
- `0x180128588`
- `0x18018c4d8`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18018c62f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18018c62f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18018c53e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18018c53e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18018c585`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18018c61e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18018c585`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18018c61e`
- `d3d11!D3D11CreateDevice` at `0x18018c68a`
- `d3d11!D3D11CreateDevice` at `0x18018c68a`

## string_xrefs

- `0x18018c611`: `HWDRMSimulationPackage`
- `0x18018c578`: `HWDRMSimulationKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
unsigned __int8 __fastcall EnableSimulation(PVOID pvData, DWORD a2, bool *a3)
{
  unsigned __int8 v5; // di
  char v6; // bl
  int v7; // ebx
  CallStackTracing *v8; // rcx
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  CallStackTracing *v11; // rcx
  struct CallStackContext *v12; // rax
  CallStackTracing *v13; // rcx
  struct CallStackContext *v14; // rax
  CallStackTracing *v15; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackScopeTrace v18; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v21; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v22[2]; // [rsp+70h] [rbp-90h] BYREF
  DWORD v23[4]; // [rsp+80h] [rbp-80h] BYREF
  HKEY hkey; // [rsp+90h] [rbp-70h] BYREF
  ID3D11Device *ppDevice; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v26[256]; // [rsp+A0h] [rbp-60h] BYREF
  int v27; // [rsp+1A0h] [rbp+A0h]
  int v28; // [rsp+1A4h] [rbp+A4h]

  v23[0] = a2;
  v5 = 0;
  hkey = 0;
  if ( a3 )
    *a3 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, aSoftwareMicros_16, 0, 1u, &hkey) )
  {
    LODWORD(v19) = 0;
    pcbData = 4;
    if ( !RegGetValueW(hkey, 0, L"HWDRMSimulationKey", 0x10u, 0, &v19, &pcbData) )
    {
      v5 = (_DWORD)v19 == 1;
      CallStackScopeTrace::CallStackScopeTrace(&v18, "EnableSimulation", 50);
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_0a68e11a7a7d34f96639e66736941ba6_Traceguids, v5);
      CallStackScopeTrace::~CallStackScopeTrace(&v18);
    }
    if ( pvData && v23[0] && a3 && !RegGetValueW(hkey, 0, L"HWDRMSimulationPackage", 2u, 0, pvData, v23) )
      *a3 = 1;
    RegCloseKey(hkey);
    if ( v5 )
    {
      pcbData = 0;
      ppDevice = 0;
      v6 = 0;
      if ( D3D11CreateDevice(
             0,
             D3D_DRIVER_TYPE_HARDWARE,
             0,
             0x800u,
             &dword_1801E03A8,
             7u,
             7u,
             &ppDevice,
             (D3D_FEATURE_LEVEL *)&pcbData,
             0) < 0 )
      {
LABEL_64:
        v5 &= v6;
        ATL::CComPtrBase<CMFSimulatedContentProtectionDevice>::~CComPtrBase<CMFSimulatedContentProtectionDevice>(&ppDevice);
        return v5;
      }
      v22[0] = 0;
      v21 = 0;
      memset_0(v26, 0, 0x140u);
      v19 = 0;
      CallStackScopeTrace::CallStackScopeTrace(&v18, "EnableSimulation", 90);
      v7 = ppDevice->QueryInterface(ppDevice, &GUID_05008617_fbfd_4051_a790_144884b4f6a9, (void **)v22);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v22[0] + 56LL))(
               v22[0],
               &v19);
        if ( v7 >= 0 )
        {
          v7 = (**v19)(v19, &GUID_0aa1ae0a_fa0e_4b84_8644_e05ff8e5acb5, &v21);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v21 + 88LL))(v21, v26);
            if ( v7 >= 0 )
            {
              if ( v27 == 5140 && v28 == 140 )
              {
                if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 2u )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_0a68e11a7a7d34f96639e66736941ba6_Traceguids);
                v6 = 0;
              }
              else
              {
                v6 = 1;
              }
              CallStackScopeTrace::~CallStackScopeTrace(&v18);
              ATL::CComPtrBase<CMFSimulatedContentProtectionDevice>::~CComPtrBase<CMFSimulatedContentProtectionDevice>(&v19);
              ATL::CComPtrBase<CMFSimulatedContentProtectionDevice>::~CComPtrBase<CMFSimulatedContentProtectionDevice>(&v21);
              ATL::CComPtrBase<CMFSimulatedContentProtectionDevice>::~CComPtrBase<CMFSimulatedContentProtectionDevice>(v22);
              goto LABEL_64;
            }
            v15 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v15 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v15 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v15->m_fEnabled )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v15);
              if ( ThreadRelativeContext->m_result != v7 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "EnableSimulation", 93, v7);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_26;
            v10 = 14;
          }
          else
          {
            v13 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v13 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v13 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v13->m_fEnabled )
            {
              v14 = CallStackTracing::GetThreadRelativeContext(v13);
              if ( v14->m_result != v7 )
                CallStackContext::TraceFailure(v14, "EnableSimulation", 92, v7);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_26;
            v10 = 13;
          }
        }
        else
        {
          v11 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v11 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v11 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v11->m_fEnabled )
          {
            v12 = CallStackTracing::GetThreadRelativeContext(v11);
            if ( v12->m_result != v7 )
              CallStackContext::TraceFailure(v12, "EnableSimulation", 91, v7);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_26;
          v10 = 12;
        }
      }
      else
      {
        v8 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v8 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v8 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v8->m_fEnabled )
        {
          v9 = CallStackTracing::GetThreadRelativeContext(v8);
          if ( v9->m_result != v7 )
            CallStackContext::TraceFailure(v9, "EnableSimulation", 90, v7);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_26;
        v10 = 11;
      }
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_0a68e11a7a7d34f96639e66736941ba6_Traceguids, 0, v7);
LABEL_26:
      CallStackScopeTrace::~CallStackScopeTrace(&v18);
      ATL::CComPtrBase<CMFSimulatedContentProtectionDevice>::~CComPtrBase<CMFSimulatedContentProtectionDevice>(&v19);
      ATL::CComPtrBase<CMFSimulatedContentProtectionDevice>::~CComPtrBase<CMFSimulatedContentProtectionDevice>(&v21);
      ATL::CComPtrBase<CMFSimulatedContentProtectionDevice>::~CComPtrBase<CMFSimulatedContentProtectionDevice>(v22);
      v6 = 0;
      goto LABEL_64;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18018c4d8  push    rbp
0x18018c4da  push    rbx
0x18018c4db  push    rsi
0x18018c4dc  push    rdi
0x18018c4dd  push    r12
0x18018c4df  push    r13
0x18018c4e1  push    r14
0x18018c4e3  lea     rbp, [rsp-0F0h]
0x18018c4eb  sub     rsp, 1F0h
0x18018c4f2  mov     rax, cs:__security_cookie
0x18018c4f9  xor     rax, rsp
0x18018c4fc  mov     [rbp+120h+var_40], rax
0x18018c503  mov     rbx, r8
0x18018c506  mov     rsi, rcx
0x18018c509  mov     [rbp+120h+var_1A0], edx
0x18018c50c  xor     r14d, r14d
0x18018c50f  mov     dil, r14b
0x18018c512  mov     [rbp+120h+hkey], r14
0x18018c516  test    r8, r8
0x18018c519  jz      short loc_18018C51E
0x18018c51b  mov     [r8], r14b
0x18018c51e  lea     rax, [rbp+120h+hkey]
0x18018c522  mov     [rsp+220h+phkResult], rax; phkResult
0x18018c527  mov     r9d, 1; samDesired
0x18018c52d  xor     r8d, r8d; ulOptions
0x18018c530  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Scrunch\\CodecPack"...
0x18018c537  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18018c53e  call    cs:__imp_RegOpenKeyExW
0x18018c544  test    eax, eax
0x18018c546  jnz     loc_18018CA3D
0x18018c54c  mov     dword ptr [rsp+220h+var_1C8], r14d
0x18018c551  mov     [rsp+220h+var_1C0], 4
0x18018c559  lea     rax, [rsp+220h+var_1C0]
0x18018c55e  mov     [rsp+220h+pcbData], rax; pcbData
0x18018c563  lea     rax, [rsp+220h+var_1C8]
0x18018c568  mov     [rsp+220h+pvData], rax; pvData
0x18018c56d  mov     [rsp+220h+phkResult], r14; pdwType
0x18018c572  mov     r9d, 10h; dwFlags
0x18018c578  lea     r8, aHwdrmsimulatio; "HWDRMSimulationKey"
0x18018c57f  xor     edx, edx; lpSubKey
0x18018c581  mov     rcx, [rbp+120h+hkey]; hkey
0x18018c585  call    cs:__imp_RegGetValueW
0x18018c58b  lea     r13, aEnablesimulati; "EnableSimulation"
0x18018c592  lea     r12, WPP_0a68e11a7a7d34f96639e66736941ba6_Traceguids
0x18018c599  test    eax, eax
0x18018c59b  jnz     short loc_18018C5E8
0x18018c59d  cmp     dword ptr [rsp+220h+var_1C8], 1
0x18018c5a2  setz    dil
0x18018c5a6  lea     r8d, [rax+32h]; int
0x18018c5aa  mov     rdx, r13; char *
0x18018c5ad  lea     rcx, [rsp+220h+var_1D0]; this
0x18018c5b2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18018c5b7  nop
0x18018c5b8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 2; MFWppLevels g_wppLevels
0x18018c5bf  jb      short loc_18018C5DE
0x18018c5c1  movzx   r9d, dil
0x18018c5c5  mov     edx, 0Ah
0x18018c5ca  mov     r8, r12
0x18018c5cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18018c5d4  mov     rcx, [rcx+10h]
0x18018c5d8  call    WPP_SF_d
0x18018c5dd  nop
0x18018c5de  lea     rcx, [rsp+220h+var_1D0]; this
0x18018c5e3  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18018c5e8  test    rsi, rsi
0x18018c5eb  jz      short loc_18018C62B
0x18018c5ed  cmp     [rbp+120h+var_1A0], r14d
0x18018c5f1  jbe     short loc_18018C62B
0x18018c5f3  test    rbx, rbx
0x18018c5f6  jz      short loc_18018C62B
0x18018c5f8  lea     rax, [rbp+120h+var_1A0]
0x18018c5fc  mov     [rsp+220h+pcbData], rax; pcbData
0x18018c601  mov     [rsp+220h+pvData], rsi; pvData
0x18018c606  mov     [rsp+220h+phkResult], r14; pdwType
0x18018c60b  mov     r9d, 2; dwFlags
0x18018c611  lea     r8, aHwdrmsimulatio_0; "HWDRMSimulationPackage"
0x18018c618  xor     edx, edx; lpSubKey
0x18018c61a  mov     rcx, [rbp+120h+hkey]; hkey
0x18018c61e  call    cs:__imp_RegGetValueW
0x18018c624  test    eax, eax
0x18018c626  jnz     short loc_18018C62B
0x18018c628  mov     byte ptr [rbx], 1
0x18018c62b  mov     rcx, [rbp+120h+hkey]; hKey
0x18018c62f  call    cs:__imp_RegCloseKey
0x18018c635  test    dil, dil
0x18018c638  jz      loc_18018CA3D
0x18018c63e  mov     [rsp+220h+var_1C0], r14d
0x18018c643  mov     [rbp+120h+var_188], r14
0x18018c647  mov     bl, r14b
0x18018c64a  mov     [rsp+220h+ppImmediateContext], r14; ppImmediateContext
0x18018c64f  lea     rax, [rsp+220h+var_1C0]
0x18018c654  mov     [rsp+220h+pFeatureLevel], rax; pFeatureLevel
0x18018c659  lea     rax, [rbp+120h+var_188]
0x18018c65d  mov     [rsp+220h+ppDevice], rax; ppDevice
0x18018c662  mov     eax, 7
0x18018c667  mov     dword ptr [rsp+220h+pcbData], eax; SDKVersion
0x18018c66b  mov     dword ptr [rsp+220h+pvData], eax; FeatureLevels
0x18018c66f  lea     rax, dword_1801E03A8
0x18018c676  mov     [rsp+220h+phkResult], rax; pFeatureLevels
0x18018c67b  mov     r9d, 800h; Flags
0x18018c681  xor     r8d, r8d; Software
0x18018c684  lea     edx, [r8+1]; DriverType
0x18018c688  xor     ecx, ecx; pAdapter
0x18018c68a  call    cs:__imp_D3D11CreateDevice
0x18018c690  test    eax, eax
0x18018c692  js      loc_18018CA31
0x18018c698  mov     [rsp+220h+var_1B0], r14
0x18018c69d  mov     [rsp+220h+var_1B8], r14
0x18018c6a2  xor     edx, edx; Val
0x18018c6a4  mov     r8d, 140h; Size
0x18018c6aa  lea     rcx, [rbp+120h+var_180]; void *
0x18018c6ae  call    memset_0
0x18018c6b3  mov     [rsp+220h+var_1C8], r14
0x18018c6b8  mov     esi, 5Ah ; 'Z'
0x18018c6bd  mov     r8d, esi; int
0x18018c6c0  mov     rdx, r13; char *
0x18018c6c3  lea     rcx, [rsp+220h+var_1D0]; this
0x18018c6c8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18018c6cd  nop
0x18018c6ce  mov     rcx, [rbp+120h+var_188]
0x18018c6d2  mov     rax, [rcx]
0x18018c6d5  lea     r8, [rsp+220h+var_1B0]
0x18018c6da  lea     rdx, _GUID_05008617_fbfd_4051_a790_144884b4f6a9
0x18018c6e1  mov     rax, [rax]
0x18018c6e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018c6e9  mov     ebx, eax
0x18018c6eb  test    eax, eax
0x18018c6ed  jns     loc_18018C7C0
0x18018c6f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18018c6fa  test    rcx, rcx
0x18018c6fd  jnz     short loc_18018C740
0x18018c6ff  lea     r8, stru_1801FC290
0x18018c706  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18018c70d  mov     rdx, cs:stru_1801FC290.__vftable
0x18018c714  mov     rax, [rdx+8]
0x18018c718  mov     edx, 7F0h
0x18018c71d  mov     rcx, r8
0x18018c720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018c725  test    eax, eax
0x18018c727  jnz     short loc_18018C739
0x18018c729  lea     rcx, stru_1801F8A30
0x18018c730  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18018c737  jmp     short loc_18018C740
0x18018c739  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18018c740  cmp     [rcx+8], r14b
0x18018c744  jz      short loc_18018C764
0x18018c746  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18018c74b  cmp     [rax+7CCh], ebx
0x18018c751  jz      short loc_18018C764
0x18018c753  mov     r9d, ebx; int
0x18018c756  mov     r8d, esi; int
0x18018c759  mov     rdx, r13; char *
0x18018c75c  mov     rcx, rax; this
0x18018c75f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18018c764  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18018c76b  jb      short loc_18018C78D
0x18018c76d  mov     edx, 0Bh
0x18018c772  mov     dword ptr [rsp+220h+phkResult], ebx
0x18018c776  xor     r9d, r9d
0x18018c779  mov     r8, r12
0x18018c77c  mov     rcx, cs:WPP_GLOBAL_Control
0x18018c783  mov     rcx, [rcx+10h]
0x18018c787  call    WPP_SF_qD
0x18018c78c  nop
0x18018c78d  lea     rcx, [rsp+220h+var_1D0]; this
0x18018c792  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18018c797  nop
0x18018c798  lea     rcx, [rsp+220h+var_1C8]
0x18018c79d  call    ??1?$CComPtrBase@VCMFSimulatedContentProtectionDevice@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CMFSimulatedContentProtectionDevice>::~CComPtrBase<CMFSimulatedContentProtectionDevice>(void)
0x18018c7a2  nop
0x18018c7a3  lea     rcx, [rsp+220h+var_1B8]
0x18018c7a8  call    ??1?$CComPtrBase@VCMFSimulatedContentProtectionDevice@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CMFSimulatedContentProtectionDevice>::~CComPtrBase<CMFSimulatedContentProtectionDevice>(void)
0x18018c7ad  nop
0x18018c7ae  lea     rcx, [rsp+220h+var_1B0]
0x18018c7b3  call    ??1?$CComPtrBase@VCMFSimulatedContentProtectionDevice@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CMFSimulatedContentProtectionDevice>::~CComPtrBase<CMFSimulatedContentProtectionDevice>(void)
0x18018c7b8  mov     bl, r14b
0x18018c7bb  jmp     loc_18018CA31
0x18018c7c0  mov     rcx, [rsp+220h+var_1B0]
0x18018c7c5  mov     rax, [rcx]
0x18018c7c8  lea     rdx, [rsp+220h+var_1C8]
0x18018c7cd  mov     rax, [rax+38h]
0x18018c7d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018c7d6  mov     ebx, eax
0x18018c7d8  test    eax, eax
0x18018c7da  jns     loc_18018C86B
0x18018c7e0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18018c7e7  test    rcx, rcx
0x18018c7ea  jnz     short loc_18018C82D
0x18018c7ec  lea     r8, stru_1801FC290
0x18018c7f3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18018c7fa  mov     rcx, cs:stru_1801FC290.__vftable
0x18018c801  mov     rax, [rcx+8]
0x18018c805  mov     edx, 7F0h
0x18018c80a  mov     rcx, r8
0x18018c80d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018c812  test    eax, eax
0x18018c814  jnz     short loc_18018C826
0x18018c816  lea     rcx, stru_1801F8A30
0x18018c81d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18018c824  jmp     short loc_18018C82D
0x18018c826  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18018c82d  cmp     [rcx+8], r14b
0x18018c831  jz      short loc_18018C854
0x18018c833  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18018c838  cmp     [rax+7CCh], ebx
0x18018c83e  jz      short loc_18018C854
0x18018c840  mov     r9d, ebx; int
0x18018c843  mov     r8d, 5Bh ; '['; int
0x18018c849  mov     rdx, r13; char *
0x18018c84c  mov     rcx, rax; this
0x18018c84f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18018c854  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18018c85b  jb      loc_18018C78D
0x18018c861  mov     edx, 0Ch
0x18018c866  jmp     loc_18018C772
0x18018c86b  mov     rcx, [rsp+220h+var_1C8]
0x18018c870  mov     rax, [rcx]
0x18018c873  lea     r8, [rsp+220h+var_1B8]
0x18018c878  lea     rdx, _GUID_0aa1ae0a_fa0e_4b84_8644_e05ff8e5acb5
0x18018c87f  mov     rax, [rax]
0x18018c882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018c887  mov     ebx, eax
0x18018c889  test    eax, eax
0x18018c88b  jns     loc_18018C91C
0x18018c891  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18018c898  test    rcx, rcx
0x18018c89b  jnz     short loc_18018C8DE
0x18018c89d  lea     r8, stru_1801FC290
0x18018c8a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18018c8ab  mov     rcx, cs:stru_1801FC290.__vftable
0x18018c8b2  mov     rax, [rcx+8]
0x18018c8b6  mov     edx, 7F0h
0x18018c8bb  mov     rcx, r8
0x18018c8be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018c8c3  test    eax, eax
0x18018c8c5  jnz     short loc_18018C8D7
0x18018c8c7  lea     rcx, stru_1801F8A30
0x18018c8ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18018c8d5  jmp     short loc_18018C8DE
0x18018c8d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18018c8de  cmp     [rcx+8], r14b
0x18018c8e2  jz      short loc_18018C905
0x18018c8e4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18018c8e9  cmp     [rax+7CCh], ebx
0x18018c8ef  jz      short loc_18018C905
0x18018c8f1  mov     r9d, ebx; int
0x18018c8f4  mov     r8d, 5Ch ; '\'; int
0x18018c8fa  mov     rdx, r13; char *
0x18018c8fd  mov     rcx, rax; this
0x18018c900  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18018c905  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18018c90c  jb      loc_18018C78D
0x18018c912  mov     edx, 0Dh
0x18018c917  jmp     loc_18018C772
0x18018c91c  mov     rcx, [rsp+220h+var_1B8]
0x18018c921  mov     rax, [rcx]
0x18018c924  lea     rdx, [rbp+120h+var_180]
0x18018c928  mov     rax, [rax+58h]
0x18018c92c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018c931  mov     ebx, eax
0x18018c933  test    eax, eax
0x18018c935  jns     loc_18018C9C6
0x18018c93b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18018c942  test    rcx, rcx
0x18018c945  jnz     short loc_18018C988
0x18018c947  lea     r8, stru_1801FC290
0x18018c94e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18018c955  mov     rcx, cs:stru_1801FC290.__vftable
0x18018c95c  mov     rax, [rcx+8]
0x18018c960  mov     edx, 7F0h
0x18018c965  mov     rcx, r8
0x18018c968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018c96d  test    eax, eax
0x18018c96f  jnz     short loc_18018C981
0x18018c971  lea     rcx, stru_1801F8A30
0x18018c978  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18018c97f  jmp     short loc_18018C988
0x18018c981  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18018c988  cmp     [rcx+8], r14b
0x18018c98c  jz      short loc_18018C9AF
0x18018c98e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18018c993  cmp     [rax+7CCh], ebx
0x18018c999  jz      short loc_18018C9AF
0x18018c99b  mov     r9d, ebx; int
0x18018c99e  mov     r8d, 5Dh ; ']'; int
0x18018c9a4  mov     rdx, r13; char *
0x18018c9a7  mov     rcx, rax; this
0x18018c9aa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18018c9af  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18018c9b6  jb      loc_18018C78D
0x18018c9bc  mov     edx, 0Eh
0x18018c9c1  jmp     loc_18018C772
0x18018c9c6  cmp     [rbp+120h+var_80], 1414h
0x18018c9d0  jnz     short loc_18018CA04
0x18018c9d2  cmp     [rbp+120h+var_7C], 8Ch
0x18018c9dc  jnz     short loc_18018CA04
0x18018c9de  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 2; MFWppLevels g_wppLevels
0x18018c9e5  jb      short loc_18018C9FF
0x18018c9e7  mov     edx, 0Fh
0x18018c9ec  mov     r8, r12
  ... truncated ...
```
