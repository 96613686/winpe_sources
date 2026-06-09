# Microsoft::Windows::MDM::OmadmClient::DpuManager::InitializeDpu(tagSyncMLDPUInit &,ushort const *,IProvisioningSyncMlDPU * *)

- ea: `0x14002d800`
- end: `0x14002d990`
- name: `?InitializeDpu@DpuManager@OmadmClient@MDM@Windows@Microsoft@@UEAAJAEAUtagSyncMLDPUInit@@PEBGPEAPEAUIProvisioningSyncMlDPU@@@Z`
- size: `400`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::DpuManager *__hidden this, struct tagSyncMLDPUInit *, const unsigned __int16 *, struct IProvisioningSyncMlDPU **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14000b0f4`
- `0x14000e610`
- `0x140013404`
- `0x14002abd4`
- `0x14002d800`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002d937`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002d937`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x14002d8ca`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x14002d8ca`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14002d884`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14002d884`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::DpuManager::InitializeDpu(
        Microsoft::Windows::MDM::OmadmClient::DpuManager *this,
        struct tagSyncMLDPUInit *a2,
        WCHAR *a3,
        IUnknown **a4)
{
  HRESULT v7; // eax
  unsigned int hr; // ebx
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  HRESULT Instance; // eax
  int dwCount; // [rsp+20h] [rbp-59h]
  _QWORD v14[3]; // [rsp+30h] [rbp-49h] BYREF
  int v15; // [rsp+48h] [rbp-31h]
  HRESULT *v16; // [rsp+50h] [rbp-29h]
  ULONGLONG TickCount64; // [rsp+58h] [rbp-21h] BYREF
  MULTI_QI pResults; // [rsp+60h] [rbp-19h] BYREF
  _QWORD v19[2]; // [rsp+78h] [rbp-1h] BYREF
  char v20; // [rsp+88h] [rbp+Fh]
  COSERVERINFO pServerInfo; // [rsp+90h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  HRESULT v23; // [rsp+F0h] [rbp+77h] BYREF

  v23 = 0;
  v14[0] = 0;
  v14[1] = "InitializeDpu";
  v14[2] = COmaDmLogger::GetLogger();
  v15 = 2;
  v16 = &v23;
  if ( !a3 )
  {
    Instance = CoCreateInstance(
                 &GUID_e3784839_6bd5_4702_a7b0_59c7592fb7b8,
                 0,
                 1u,
                 &GUID_9319e61f_2b35_4d32_abf2_cc1246fdbe88,
                 (LPVOID *)a4);
    v23 = Instance;
    goto LABEL_9;
  }
  *(_QWORD *)&pServerInfo.dwReserved1 = 0;
  pServerInfo.pAuthInfo = 0;
  *(_QWORD *)&pServerInfo.dwReserved2 = 1;
  pServerInfo.pwszName = a3;
  *(_OWORD *)&pResults.pItf = 0;
  pResults.pIID = &GUID_9319e61f_2b35_4d32_abf2_cc1246fdbe88;
  TickCount64 = GetTickCount64();
  v19[0] = &TickCount64;
  v19[1] = &v23;
  v20 = 1;
  v7 = CoCreateInstanceEx(&GUID_3d5fea35_6973_4d5b_9937_dd8e53482a56, 0, 0x10u, &pServerInfo, 1u, &pResults);
  hr = v7;
  if ( v7 >= 0 )
  {
    hr = pResults.hr;
    if ( pResults.hr < 0 )
    {
      v9 = (unsigned int)pResults.hr;
      v10 = 126;
      goto LABEL_6;
    }
    *a4 = pResults.pItf;
    wil::details::ScopeExitFn__lambda_dbbe5bef42fc12e28443159da8af494e___::_ScopeExitFn__lambda_dbbe5bef42fc12e28443159da8af494e___(v19);
    Instance = v23;
LABEL_9:
    if ( Instance >= 0 )
    {
      Instance = ((__int64 (__fastcall *)(IUnknown *, struct tagSyncMLDPUInit *))(*a4)->lpVtbl[1].QueryInterface)(
                   *a4,
                   a2);
      v23 = Instance;
      if ( Instance >= 0 )
      {
LABEL_14:
        hr = Instance;
        goto LABEL_15;
      }
      LODWORD(v14[0]) = 21016;
    }
    else
    {
      LODWORD(v14[0]) = 21015;
    }
    HIDWORD(v14[0]) = Instance;
    goto LABEL_14;
  }
  v9 = (unsigned int)v7;
  v10 = 125;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\dpumanager.cpp",
    (const char *)v9,
    dwCount);
  wil::details::ScopeExitFn__lambda_dbbe5bef42fc12e28443159da8af494e___::_ScopeExitFn__lambda_dbbe5bef42fc12e28443159da8af494e___(v19);
LABEL_15:
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v14);
  return hr;
}

```

## disassembly

```asm
0x14002d800  push    rbp
0x14002d802  push    rbx
0x14002d803  push    rsi
0x14002d804  push    rdi
0x14002d805  lea     rbp, [rsp-3Fh]
0x14002d80a  sub     rsp, 0B8h
0x14002d811  mov     rdi, r9
0x14002d814  mov     rbx, r8
0x14002d817  mov     rsi, rdx
0x14002d81a  mov     [rbp+57h+arg_10], 0
0x14002d821  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14002d826  mov     [rbp+57h+var_A0], 0
0x14002d82e  lea     rcx, aInitializedpu; "InitializeDpu"
0x14002d835  mov     [rbp+57h+var_98], rcx
0x14002d839  mov     [rbp+57h+var_90], rax
0x14002d83d  mov     [rbp+57h+var_88], 2
0x14002d844  lea     rax, [rbp+57h+arg_10]
0x14002d848  mov     [rbp+57h+var_80], rax
0x14002d84c  lea     r9, _GUID_9319e61f_2b35_4d32_abf2_cc1246fdbe88; riid
0x14002d853  test    rbx, rbx
0x14002d856  jz      loc_14002D925
0x14002d85c  mov     qword ptr [rbp+57h+pServerInfo.dwReserved1], 0
0x14002d864  mov     [rbp+57h+pServerInfo.pAuthInfo], 0
0x14002d86c  mov     qword ptr [rbp+57h+pServerInfo.dwReserved2], 1
0x14002d874  mov     [rbp+57h+pServerInfo.pwszName], rbx
0x14002d878  xorps   xmm0, xmm0
0x14002d87b  movdqu  xmmword ptr [rbp+57h+var_70.pItf], xmm0
0x14002d880  mov     [rbp+57h+var_70.pIID], r9
0x14002d884  call    cs:__imp_GetTickCount64
0x14002d88b  nop     dword ptr [rax+rax+00h]
0x14002d890  mov     [rbp+57h+var_78], rax
0x14002d894  lea     rax, [rbp+57h+var_78]
0x14002d898  mov     [rbp+57h+var_58], rax
0x14002d89c  lea     rax, [rbp+57h+arg_10]
0x14002d8a0  mov     [rbp+57h+var_50], rax
0x14002d8a4  mov     [rbp+57h+var_48], 1
0x14002d8a8  lea     rax, [rbp+57h+var_70]
0x14002d8ac  mov     [rsp+0D0h+pResults], rax; pResults
0x14002d8b1  mov     [rsp+0D0h+dwCount], 1; int
0x14002d8b9  lea     r9, [rbp+57h+pServerInfo]; pServerInfo
0x14002d8bd  xor     edx, edx; punkOuter
0x14002d8bf  lea     r8d, [rdx+10h]; dwClsCtx
0x14002d8c3  lea     rcx, _GUID_3d5fea35_6973_4d5b_9937_dd8e53482a56; Clsid
0x14002d8ca  call    cs:__imp_CoCreateInstanceEx
0x14002d8d1  nop     dword ptr [rax+rax+00h]
0x14002d8d6  mov     ebx, eax
0x14002d8d8  test    eax, eax
0x14002d8da  jns     short loc_14002D8E6
0x14002d8dc  mov     r9d, eax
0x14002d8df  mov     edx, 7Dh ; '}'
0x14002d8e4  jmp     short loc_14002D8F5
0x14002d8e6  mov     ebx, [rbp+57h+var_70.hr]
0x14002d8e9  test    ebx, ebx
0x14002d8eb  jns     short loc_14002D910
0x14002d8ed  mov     r9d, ebx; char *
0x14002d8f0  mov     edx, 7Eh ; '~'; void *
0x14002d8f5  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14002d8fc  mov     rcx, [rbp+5Fh]; this
0x14002d900  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002d905  lea     rcx, [rbp+57h+var_58]
0x14002d909  call    wil__details__ScopeExitFn__lambda_dbbe5bef42fc12e28443159da8af494e______ScopeExitFn__lambda_dbbe5bef42fc12e28443159da8af494e___
0x14002d90e  jmp     short loc_14002D978
0x14002d910  mov     rax, [rbp+57h+var_70.pItf]
0x14002d914  mov     [rdi], rax
0x14002d917  lea     rcx, [rbp+57h+var_58]
0x14002d91b  call    wil__details__ScopeExitFn__lambda_dbbe5bef42fc12e28443159da8af494e______ScopeExitFn__lambda_dbbe5bef42fc12e28443159da8af494e___
0x14002d920  mov     eax, [rbp+57h+arg_10]
0x14002d923  jmp     short loc_14002D946
0x14002d925  mov     qword ptr [rsp+0D0h+dwCount], rdi; ppv
0x14002d92a  xor     edx, edx; pUnkOuter
0x14002d92c  lea     r8d, [rdx+1]; dwClsContext
0x14002d930  lea     rcx, _GUID_e3784839_6bd5_4702_a7b0_59c7592fb7b8; rclsid
0x14002d937  call    cs:__imp_CoCreateInstance
0x14002d93e  nop     dword ptr [rax+rax+00h]
0x14002d943  mov     [rbp+57h+arg_10], eax
0x14002d946  test    eax, eax
0x14002d948  jns     short loc_14002D953
0x14002d94a  mov     dword ptr [rbp+57h+var_A0], 5217h
0x14002d951  jmp     short loc_14002D973
0x14002d953  mov     rcx, [rdi]
0x14002d956  mov     rax, [rcx]
0x14002d959  mov     rdx, rsi
0x14002d95c  mov     rax, [rax+18h]
0x14002d960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d965  mov     [rbp+57h+arg_10], eax
0x14002d968  test    eax, eax
0x14002d96a  jns     short loc_14002D976
0x14002d96c  mov     dword ptr [rbp+57h+var_A0], 5218h
0x14002d973  mov     dword ptr [rbp+57h+var_A0+4], eax
0x14002d976  mov     ebx, eax
0x14002d978  lea     rcx, [rbp+57h+var_A0]; this
0x14002d97c  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14002d981  mov     eax, ebx
0x14002d983  add     rsp, 0B8h
0x14002d98a  pop     rdi
0x14002d98b  pop     rsi
0x14002d98c  pop     rbx
0x14002d98d  pop     rbp
0x14002d98e  retn
```
