# PostServiceInit

- ea: `0x180025c1c`
- end: `0x180025df7`
- name: `PostServiceInit`
- size: `475`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task`

## callers

- `0x180037a5c`

## callees

- `0x18000bb98`
- `0x18001ad74`
- `0x18001aea4`
- `0x1800253cc`
- `0x1800257cc`
- `0x180025be0`
- `0x180025c1c`
- `0x180026fe4`
- `0x18002fe7c`
- `0x180047984`
- `0x18004a668`
- `0x18004d840`
- `0x18007da44`

## import_xrefs

- `mstlsapi!__imp_TLSInDomain` at `0x180025d09`
- `mstlsapi!__imp_TLSInDomain` at `0x180025d09`
- `VSSAPI!?Initialize@CVssJetWriter@@QEAAJU_GUID@@PEBG_N211K@Z` at `0x180025c96`
- `VSSAPI!?Initialize@CVssJetWriter@@QEAAJU_GUID@@PEBG_N211K@Z` at `0x180025c96`
- `KERNEL32!GetLastError` at `0x180025c3c`
- `KERNEL32!GetLastError` at `0x180025c3c`

## pseudocode

```c
__int64 PostServiceInit()
{
  struct IRdlsDBConnection *v0; // rax
  struct CWorkStorage *v1; // rdx
  CWorkManager *v2; // rcx
  int LastError; // eax
  int v4; // ebx
  int v5; // eax
  __int64 result; // rax
  unsigned int v7; // ebx
  CTLSPolicyMgr *v8; // rcx
  GUID v9; // [rsp+40h] [rbp-18h] BYREF
  int v10; // [rsp+60h] [rbp+8h] BYREF
  __int64 v11; // [rsp+68h] [rbp+10h]

  v10 = 0;
  v0 = CRdlsDBManager::AcquireRdlsDBConnection((CRdlsDBManager *)g_RdlsDBManager);
  if ( v0 )
  {
    qword_1800E3170 = (__int64)v0;
    LastError = CWorkManager::Startup(v2, v1);
  }
  else
  {
    LastError = GetLastError();
  }
  v4 = LastError;
  v9 = idWriter;
  v5 = CVssJetWriter::Initialize(g_pWriter, &v9, L"TermServLicensing", 1, 0, &pszSrc, &pszSrc, 0);
  if ( v5 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_86a5617ab3d63806f44b8abc90678c18_Traceguids, (unsigned int)v5);
  if ( v4 )
    return 33;
  if ( InitNamedPipeThread()
    || !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_1594457400>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_1594457400>::GetImpl'::`2'::impl)
    && !(unsigned int)TLSInDomain(&v10, 0)
    && !v10
    && InitMailSlotThread()
    || InitExpirePermanentThread() )
  {
    CrimsonHelper::RaiseEventInternal(
      (CrimsonHelper *)CrimsonHelper::s_instance,
      &TLS_E_SERVICE_STARTUP_CREATE_THREAD,
      0,
      0);
    return 30;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_86a5617ab3d63806f44b8abc90678c18_Traceguids,
        (unsigned int)L"Enforce",
        1);
    if ( (g_SrvRole & 1) != 0
      || (v11 = *((_QWORD *)g_RdlsDBManager + 330),
          result = TLSStartAnnounceLicenseServerJob((unsigned __int16 *)String1),
          !(_DWORD)result) )
    {
      v11 = *((_QWORD *)g_RdlsDBManager + 330);
      v7 = TLSStartAnnounceToEServerJob((unsigned __int16 *)String1);
      CTLSPolicyMgr::InitProductPolicyModule(v8);
      return v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180025c1c  mov     [rsp+arg_10], rbx
0x180025c21  push    rsi
0x180025c22  sub     rsp, 50h
0x180025c26  mov     rcx, cs:?g_RdlsDBManager@@3PEAVCRdlsDBManager@@EA; this
0x180025c2d  and     [rsp+58h+arg_0], 0
0x180025c32  call    ?AcquireRdlsDBConnection@CRdlsDBManager@@QEAAPEAVIRdlsDBConnection@@XZ; CRdlsDBManager::AcquireRdlsDBConnection(void)
0x180025c37  test    rax, rax
0x180025c3a  jnz     short loc_180025C4A
0x180025c3c  call    cs:__imp_GetLastError
0x180025c43  nop     dword ptr [rax+rax+00h]
0x180025c48  jmp     short loc_180025C56
0x180025c4a  mov     cs:qword_1800E3170, rax
0x180025c51  call    ?Startup@CWorkManager@@QEAAKPEAVCWorkStorage@@KK@Z; CWorkManager::Startup(CWorkStorage *,ulong,ulong)
0x180025c56  mov     ebx, eax
0x180025c58  and     [rsp+58h+var_20], 0
0x180025c5d  lea     rax, pszSrc
0x180025c64  movups  xmm0, xmmword ptr cs:?idWriter@@3U_GUID@@A.Data1; _GUID idWriter ...
0x180025c6b  mov     rcx, cs:?g_pWriter@@3PEAVCTlsVssJetWriter@@EA; CTlsVssJetWriter * g_pWriter
0x180025c72  lea     r8, ServiceName; "TermServLicensing"
0x180025c79  mov     [rsp+58h+var_28], rax
0x180025c7e  lea     rdx, [rsp+58h+var_18]
0x180025c83  mov     [rsp+58h+var_30], rax
0x180025c88  mov     r9b, 1
0x180025c8b  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm0
0x180025c91  mov     byte ptr [rsp+58h+var_38], 0
0x180025c96  call    cs:__imp_?Initialize@CVssJetWriter@@QEAAJU_GUID@@PEBG_N211K@Z; CVssJetWriter::Initialize(_GUID,ushort const *,bool,bool,ushort const *,ushort const *,ulong)
0x180025c9d  nop     dword ptr [rax+rax+00h]
0x180025ca2  lea     rsi, WPP_GLOBAL_Control
0x180025ca9  test    eax, eax
0x180025cab  jns     short loc_180025CD7
0x180025cad  mov     rcx, cs:WPP_GLOBAL_Control
0x180025cb4  cmp     rcx, rsi
0x180025cb7  jz      short loc_180025CD7
0x180025cb9  test    byte ptr [rcx+1Ch], 40h
0x180025cbd  jz      short loc_180025CD7
0x180025cbf  mov     rcx, [rcx+10h]
0x180025cc3  lea     r8, WPP_86a5617ab3d63806f44b8abc90678c18_Traceguids
0x180025cca  mov     edx, 0Ah
0x180025ccf  mov     r9d, eax
0x180025cd2  call    WPP_SF_D
0x180025cd7  test    ebx, ebx
0x180025cd9  jz      short loc_180025CE5
0x180025cdb  mov     eax, 21h ; '!'
0x180025ce0  jmp     loc_180025DEB
0x180025ce5  call    InitNamedPipeThread
0x180025cea  test    eax, eax
0x180025cec  jnz     loc_180025DCD
0x180025cf2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_1594457400@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_1594457400@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_1594457400> `wil::Feature<__WilFeatureTraits_Feature_1594457400>::GetImpl(void)'::`2'::impl
0x180025cf9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_1594457400@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_1594457400>::__private_IsEnabled(void)
0x180025cfe  test    al, al
0x180025d00  jnz     short loc_180025D2C
0x180025d02  xor     edx, edx
0x180025d04  lea     rcx, [rsp+58h+arg_0]
0x180025d09  call    cs:__imp_TLSInDomain
0x180025d10  nop     dword ptr [rax+rax+00h]
0x180025d15  test    eax, eax
0x180025d17  jnz     short loc_180025D2C
0x180025d19  cmp     [rsp+58h+arg_0], eax
0x180025d1d  jnz     short loc_180025D2C
0x180025d1f  call    InitMailSlotThread
0x180025d24  test    eax, eax
0x180025d26  jnz     loc_180025DCD
0x180025d2c  call    InitExpirePermanentThread
0x180025d31  test    eax, eax
0x180025d33  jnz     loc_180025DCD
0x180025d39  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d40  cmp     rcx, rsi
0x180025d43  jz      short loc_180025D6D
0x180025d45  test    byte ptr [rcx+1Ch], 20h
0x180025d49  jz      short loc_180025D6D
0x180025d4b  mov     rcx, [rcx+10h]
0x180025d4f  lea     edx, [rax+0Bh]
0x180025d52  lea     r9, aEnforce; "Enforce"
0x180025d59  mov     [rsp+58h+var_38], 1
0x180025d61  lea     r8, WPP_86a5617ab3d63806f44b8abc90678c18_Traceguids
0x180025d68  call    WPP_SF_SD
0x180025d6d  test    byte ptr cs:?g_SrvRole@@3KA, 1; ulong g_SrvRole
0x180025d74  jnz     short loc_180025D9E
0x180025d76  mov     rax, cs:?g_RdlsDBManager@@3PEAVCRdlsDBManager@@EA; CRdlsDBManager * g_RdlsDBManager
0x180025d7d  lea     r9, [rsp+58h+arg_8]
0x180025d82  mov     rcx, [rax+0A50h]
0x180025d89  mov     [rsp+58h+arg_8], rcx
0x180025d8e  mov     rcx, cs:String1; unsigned __int16 *
0x180025d95  call    TLSStartAnnounceLicenseServerJob
0x180025d9a  test    eax, eax
0x180025d9c  jnz     short loc_180025DEB
0x180025d9e  mov     rax, cs:?g_RdlsDBManager@@3PEAVCRdlsDBManager@@EA; CRdlsDBManager * g_RdlsDBManager
0x180025da5  lea     r9, [rsp+58h+arg_8]
0x180025daa  mov     rcx, [rax+0A50h]
0x180025db1  mov     [rsp+58h+arg_8], rcx
0x180025db6  mov     rcx, cs:String1; unsigned __int16 *
0x180025dbd  call    TLSStartAnnounceToEServerJob
0x180025dc2  mov     ebx, eax
0x180025dc4  call    ?InitProductPolicyModule@CTLSPolicyMgr@@QEAAKXZ; CTLSPolicyMgr::InitProductPolicyModule(void)
0x180025dc9  mov     eax, ebx
0x180025dcb  jmp     short loc_180025DEB
0x180025dcd  xor     r9d, r9d; struct _EVENT_DATA_DESCRIPTOR *
0x180025dd0  lea     rdx, TLS_E_SERVICE_STARTUP_CREATE_THREAD; struct _EVENT_DESCRIPTOR *
0x180025dd7  xor     r8d, r8d; unsigned int
0x180025dda  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; this
0x180025de1  call    ?RaiseEventInternal@CrimsonHelper@@AEAAKAEBU_EVENT_DESCRIPTOR@@KQEAU_EVENT_DATA_DESCRIPTOR@@@Z; CrimsonHelper::RaiseEventInternal(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR * const)
0x180025de6  mov     eax, 1Eh
0x180025deb  mov     rbx, [rsp+58h+arg_10]
0x180025df0  add     rsp, 50h
0x180025df4  pop     rsi
0x180025df5  retn
```
