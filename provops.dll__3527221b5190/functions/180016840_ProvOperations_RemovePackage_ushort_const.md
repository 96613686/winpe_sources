# ProvOperations::RemovePackage(ushort const *)

- ea: `0x180016840`
- end: `0x180016d5d`
- name: `?RemovePackage@ProvOperations@@UEAAJPEBG@Z`
- size: `1309`
- prototype: `__int64 __fastcall(ProvOperations *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `28`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001678`
- `0x180004d68`
- `0x180006f50`
- `0x180007674`
- `0x18000af3c`
- `0x18000ca00`
- `0x18000d1e4`
- `0x18000de84`
- `0x18000e454`
- `0x1800122e4`
- `0x180016840`
- `0x180016d64`
- `0x180018abc`
- `0x180019238`
- `0x18001b388`
- `0x18001b3a8`
- `0x180020fe0`
- `0x1800210f0`
- `0x180022784`
- `0x180024880`
- `0x180028df4`
- `0x180028e74`
- `0x180028f28`
- `0x1800296a0`
- `0x18002a170`
- `0x18002ac38`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180016a9b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016b7c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016c07`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016a9b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016b7c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016c07`
- `msvcrt!_wcsicmp` at `0x180016a7e`
- `msvcrt!_wcsicmp` at `0x180016a7e`
- `policymanager!PolicyManager_GetPolicyInt` at `0x180016957`
- `policymanager!PolicyManager_GetPolicyInt` at `0x180016957`

## string_xrefs

- `0x180016882`: `RemovePackage`
- `0x1800168e8`: `Security`
- `0x180016906`: `AllowRemoveProvisioningPackage`

## pseudocode

```c
__int64 __fastcall ProvOperations::RemovePackage(ProvOperations *this, const unsigned __int16 *a2)
{
  const wchar_t *v2; // r12
  const unsigned __int16 *v3; // rbx
  __int64 v4; // rcx
  wil *v5; // rsi
  int PolicyInt; // eax
  unsigned int v7; // ebx
  __int64 v8; // r9
  __int64 v9; // rdx
  wil *v10; // rcx
  __int64 v12; // rax
  int v13; // eax
  ProvOperations *v14; // rcx
  int v15; // eax
  char *v16; // rdx
  unsigned __int64 v17; // r8
  __int64 v18; // r13
  wil *v19; // rcx
  _QWORD *v20; // rdi
  _QWORD *v21; // rax
  char v22; // r13
  _QWORD *v23; // rbx
  __int64 v24; // rcx
  const struct _tlgProvider_t *v25; // rax
  const char *v26; // r9
  char v27; // bl
  int v28; // eax
  int v29; // ecx
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // ebx
  unsigned int v33; // r8d
  const char *v34; // r9
  unsigned int v35; // [rsp+20h] [rbp-2C8h]
  int v36; // [rsp+30h] [rbp-2B8h]
  int v37; // [rsp+34h] [rbp-2B4h] BYREF
  int v38; // [rsp+38h] [rbp-2B0h] BYREF
  void (__fastcall *v39)(__int64, void **); // [rsp+40h] [rbp-2A8h] BYREF
  _QWORD *v40; // [rsp+48h] [rbp-2A0h] BYREF
  const unsigned __int16 *v41; // [rsp+50h] [rbp-298h]
  _QWORD *v42; // [rsp+58h] [rbp-290h]
  wil *v43; // [rsp+60h] [rbp-288h]
  char v44; // [rsp+68h] [rbp-280h]
  _QWORD *v45; // [rsp+70h] [rbp-278h] BYREF
  _QWORD *v46; // [rsp+78h] [rbp-270h]
  HANDLE v47[3]; // [rsp+90h] [rbp-258h] BYREF
  void *v48[3]; // [rsp+A8h] [rbp-240h] BYREF
  unsigned __int64 v49; // [rsp+C0h] [rbp-228h]
  void *v50[3]; // [rsp+C8h] [rbp-220h] BYREF
  unsigned __int64 v51; // [rsp+E0h] [rbp-208h]
  _QWORD v52[42]; // [rsp+F0h] [rbp-1F8h] BYREF
  _BYTE v53[32]; // [rsp+240h] [rbp-A8h] BYREF
  __int128 v54; // [rsp+260h] [rbp-88h] BYREF
  wchar_t v55; // [rsp+270h] [rbp-78h]
  _OWORD v56[2]; // [rsp+278h] [rbp-70h] BYREF
  _OWORD v57[2]; // [rsp+298h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+0h]

  v2 = a2;
  v41 = a2;
  v3 = (const unsigned __int16 *)((char *)this + 16);
  if ( *((_QWORD *)this + 5) >= 8u )
    v3 = *(const unsigned __int16 **)v3;
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v52,
    "RemovePackage");
  v52[0] = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackage::`vftable';
  Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackage::StartActivity(
    (Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackage *)v52,
    v3);
  v5 = (wil *)v52;
  v43 = (wil *)v52;
  v44 = 1;
  if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(v4, ProvOpsRemovePackageInitiated, v2);
  v38 = 0;
  v54 = *(_OWORD *)L"Security";
  v55 = aSecurity[8];
  v56[0] = *(_OWORD *)L"AllowRemoveProvisioningPackage";
  v56[1] = *(_OWORD *)L"oveProvisioningPackage";
  v57[0] = *(_OWORD *)L"sioningPackage";
  *(_OWORD *)((char *)v57 + 14) = *(_OWORD *)L"Package";
  PolicyInt = PolicyManager_GetPolicyInt(&v54, v56, &v38);
  v7 = PolicyInt;
  if ( PolicyInt < 0 )
  {
    v8 = (unsigned int)PolicyInt;
    v9 = 635;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
      (const char *)v8,
      v35);
    v10 = (wil *)v52;
    goto LABEL_10;
  }
  if ( !v38 )
  {
    v7 = -2147024891;
    v8 = 2147942405LL;
    v9 = 636;
    goto LABEL_9;
  }
  try
  {
    v36 = 0;
    v22 = 0;
    v37 = 0;
    ProvAgent::ProvAgent((ProvAgent *)v47);
    ProvAgent::LockForProvisioning(v47);
    PackageCollector::PackageCollector((PackageCollector *)v53);
    PackageCollector::AddDefaultSearchPaths((PackageCollector *)v53);
    PackageCollector::Search((__int64)v53, &v45);
    v23 = v45;
    v20 = v46;
    v42 = v46;
    while ( 1 )
    {
      v40 = v23;
      if ( v23 == v20 )
        break;
      if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 72LL))(*v23) )
      {
        v26 = (const char *)(unsigned int)wil::verify_hresult<long>(0x8000FFFF);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x290,
          (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
          v26,
          v35);
      }
      v12 = (*(__int64 (__fastcall **)(_QWORD, void **))(*(_QWORD *)*v23 + 16LL))(*v23, v48);
      if ( *(_QWORD *)(v12 + 24) >= 8u )
        v12 = *(_QWORD *)v12;
      v13 = _wcsicmp(v2, (const wchar_t *)v12);
      LODWORD(v39) = v13;
      if ( v49 >= 8 )
      {
        operator delete(v48[0]);
        v13 = (int)v39;
      }
      if ( !v13 )
      {
        v15 = ProvOperations::RemovePackageInternal(v14, v2, (enum RemoveStages *)&v37);
        try
        {
          v36 = v15;
          v16 = *(char **)ProvisioningPaths::GetProgramDataProvisioningFolderPath();
          v51 = 7;
          v50[2] = 0;
          LOWORD(v50[0]) = 0;
          if ( *(_WORD *)v16 )
          {
            v17 = -1;
            do
              ++v17;
            while ( *(_WORD *)&v16[2 * v17] );
          }
          else
          {
            v17 = 0;
          }
          std::wstring::assign(v50, v16, v17);
          v18 = *v23;
          v39 = *(void (__fastcall **)(__int64, void **))(*(_QWORD *)*v23 + 96LL);
          v49 = 7;
          v48[2] = 0;
          LOWORD(v48[0]) = 0;
          std::wstring::assign(v48, v50, 0, 0xFFFFFFFFFFFFFFFFuLL);
          v39(v18, v48);
          if ( v51 >= 8 )
            operator delete(v50[0]);
        }
        catch ( ... )
        {
          v27 = v37 | 8;
          v37 |= 8u;
          v28 = wil::ResultFromCaughtException(v19);
          v36 = v28;
          if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 2) != 0 )
            McTemplateU0dzq_EventWriteTransfer(v29, (unsigned int)ProvOpsRemovePackageFailed, v28, (_DWORD)v41, v27);
          wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x2A2, v30, v31);
          v5 = v43;
          v23 = v40;
          v20 = v42;
          v2 = v41;
        }
        if ( v37 )
        {
          LODWORD(v39) = v37;
          v21 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, void **))(*(_QWORD *)*v23 + 8LL))(*v23, v48);
          if ( v21[3] >= 8u )
            v21 = (_QWORD *)*v21;
          v40 = v21;
          Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackage::RemovePackageFailure<unsigned short const *,unsigned int>(
            (__int64)v52,
            (__int64 *)&v40,
            (int *)&v39);
          if ( v49 >= 8 )
            operator delete(v48[0]);
        }
        v22 = 1;
      }
      ++v23;
    }
    std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>((__int64)&v45);
    if ( !v22 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2AF,
        (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
        (const char *)2,
        v35);
    PackageCollector::~PackageCollector((PackageCollector *)v53);
    ProvAgent::~ProvAgent((ProvAgent *)v47);
    v7 = v36;
    if ( v36 >= 0 )
    {
      if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(v24, ProvOpsRemovePackageSucceeded, v2);
      v25 = Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider();
      if ( *(_DWORD *)v25 > 5u )
        tlgWriteTransfer_EventWriteTransfer(v25, byte_180040C7B, v52[34] + 8LL, 0);
    }
    v10 = v5;
  }
  catch ( ... )
  {
    v32 = wil::ResultFromCaughtException(v10);
    wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x2B5, v33, v34);
    if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 2) != 0 )
      McTemplateU0dzq_EventWriteTransfer(v37, (unsigned int)ProvOpsRemovePackageFailed, v32, (_DWORD)v41, v37);
    wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v43);
    v52[0] = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackage::`vftable';
    wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v52);
    wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v52);
    return v32;
  }
LABEL_10:
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v10);
  v52[0] = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackage::`vftable';
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v52);
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v52);
  return v7;
}

```

## disassembly

```asm
0x180016840  mov     [rsp+arg_10], rbx
0x180016845  mov     [rsp+arg_18], rsi
0x18001684a  push    rdi
0x18001684b  push    r12
0x18001684d  push    r13
0x18001684f  push    r14
0x180016851  push    r15
0x180016853  sub     rsp, 2C0h
0x18001685a  mov     rax, cs:__security_cookie
0x180016861  xor     rax, rsp
0x180016864  mov     [rsp+2E8h+var_30], rax
0x18001686c  mov     r12, rdx
0x18001686f  mov     [rsp+2E8h+var_298], rdx
0x180016874  lea     rbx, [rcx+10h]
0x180016878  cmp     qword ptr [rbx+18h], 8
0x18001687d  jb      short loc_180016882
0x18001687f  mov     rbx, [rbx]
0x180016882  lea     rdx, aRemovepackage; "RemovePackage"
0x180016889  lea     rcx, [rsp+2E8h+var_1F8]
0x180016891  call    ??0?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180016896  lea     r15, ??_7RemovePackage@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@6B@; const Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackage::`vftable'
0x18001689d  mov     [rsp+2E8h+var_1F8], r15
0x1800168a5  mov     rdx, rbx; unsigned __int16 *
0x1800168a8  lea     rcx, [rsp+2E8h+var_1F8]; this
0x1800168b0  call    ?StartActivity@RemovePackage@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAXPEBG@Z; Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackage::StartActivity(ushort const *)
0x1800168b5  nop
0x1800168b6  lea     rsi, [rsp+2E8h+var_1F8]
0x1800168be  mov     [rsp+2E8h+var_288], rsi
0x1800168c3  mov     [rsp+2E8h+var_280], 1
0x1800168c8  test    cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, 1
0x1800168cf  jz      short loc_1800168E0
0x1800168d1  mov     r8, r12
0x1800168d4  lea     rdx, ProvOpsRemovePackageInitiated
0x1800168db  call    McTemplateU0z_EventWriteTransfer
0x1800168e0  xor     r14d, r14d
0x1800168e3  mov     [rsp+2E8h+var_2B0], r14d
0x1800168e8  movups  xmm0, xmmword ptr cs:aSecurity; "Security"
0x1800168ef  movups  [rsp+2E8h+var_88], xmm0
0x1800168f7  movzx   eax, word ptr cs:aSecurity+10h; ""
0x1800168fe  mov     [rsp+2E8h+var_78], ax
0x180016906  movups  xmm0, xmmword ptr cs:aAllowremovepro; "AllowRemoveProvisioningPackage"
0x18001690d  movups  [rsp+2E8h+var_70], xmm0
0x180016915  movups  xmm1, xmmword ptr cs:aAllowremovepro+10h; "oveProvisioningPackage"
0x18001691c  movups  [rsp+2E8h+var_60], xmm1
0x180016924  movups  xmm0, xmmword ptr cs:aAllowremovepro+20h; "sioningPackage"
0x18001692b  movups  xmmword ptr [rsp+2E8h+var_50], xmm0
0x180016933  movups  xmm1, xmmword ptr cs:aAllowremovepro+2Eh; "Package"
0x18001693a  movups  xmmword ptr [rsp+2E8h+var_50+0Eh], xmm1
0x180016942  lea     r8, [rsp+2E8h+var_2B0]
0x180016947  lea     rdx, [rsp+2E8h+var_70]
0x18001694f  lea     rcx, [rsp+2E8h+var_88]
0x180016957  call    cs:__imp_PolicyManager_GetPolicyInt
0x18001695d  mov     ebx, eax
0x18001695f  test    eax, eax
0x180016961  jns     short loc_18001696D
0x180016963  mov     r9d, eax
0x180016966  mov     edx, 27Bh
0x18001696b  jmp     short loc_180016981
0x18001696d  cmp     [rsp+2E8h+var_2B0], r14d
0x180016972  jnz     short loc_1800169CD
0x180016974  mov     ebx, 80070005h
0x180016979  mov     r9d, ebx; char *
0x18001697c  mov     edx, 27Ch; void *
0x180016981  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x180016988  mov     rcx, [rsp+2E8h]; this
0x180016990  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016995  nop
0x180016996  lea     rcx, [rsp+2E8h+var_1F8]
0x18001699e  call    ?Stop@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800169a3  nop
0x1800169a4  mov     [rsp+2E8h+var_1F8], r15
0x1800169ac  lea     rcx, [rsp+2E8h+var_1F8]
0x1800169b4  call    ?Destroy@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800169b9  lea     rcx, [rsp+2E8h+var_1F8]
0x1800169c1  call    ??1?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800169c6  mov     eax, ebx
0x1800169c8  jmp     loc_180016CE8
0x1800169cd  mov     [rsp+2E8h+var_2B8], r14d
0x1800169d2  mov     r13b, r14b
0x1800169d5  mov     [rsp+2E8h+var_2B4], r14d
0x1800169da  lea     rcx, [rsp+2E8h+var_258]; this
0x1800169e2  call    ??0ProvAgent@@QEAA@XZ; ProvAgent::ProvAgent(void)
0x1800169e7  nop
0x1800169e8  lea     rcx, [rsp+2E8h+var_258]; this
0x1800169f0  call    ?LockForProvisioning@ProvAgent@@QEAAXXZ; ProvAgent::LockForProvisioning(void)
0x1800169f5  lea     rcx, [rsp+2E8h+var_A8]; this
0x1800169fd  call    ??0PackageCollector@@QEAA@XZ; PackageCollector::PackageCollector(void)
0x180016a02  nop
0x180016a03  lea     rcx, [rsp+2E8h+var_A8]; this
0x180016a0b  call    ?AddDefaultSearchPaths@PackageCollector@@QEAAXXZ; PackageCollector::AddDefaultSearchPaths(void)
0x180016a10  lea     rdx, [rsp+2E8h+var_278]
0x180016a15  lea     rcx, [rsp+2E8h+var_A8]
0x180016a1d  call    ?Search@PackageCollector@@QEAA?AV?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@XZ; PackageCollector::Search(void)
0x180016a22  nop
0x180016a23  mov     rbx, [rsp+2E8h+var_278]
0x180016a28  mov     rdi, [rsp+2E8h+var_270]
0x180016a2d  mov     [rsp+2E8h+var_290], rdi
0x180016a32  mov     [rsp+2E8h+var_2A0], rbx
0x180016a37  cmp     rbx, rdi
0x180016a3a  jz      loc_180016C19
0x180016a40  mov     rcx, [rbx]
0x180016a43  mov     rax, [rcx]
0x180016a46  mov     rax, [rax+48h]
0x180016a4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a4f  test    al, al
0x180016a51  jz      loc_180016D15
0x180016a57  mov     rcx, [rbx]
0x180016a5a  mov     rax, [rcx]
0x180016a5d  lea     rdx, [rsp+2E8h+var_240]
0x180016a65  mov     rax, [rax+10h]
0x180016a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a6e  cmp     qword ptr [rax+18h], 8
0x180016a73  jb      short loc_180016A78
0x180016a75  mov     rax, [rax]
0x180016a78  mov     rdx, rax; String2
0x180016a7b  mov     rcx, r12; String1
0x180016a7e  call    cs:__imp__wcsicmp
0x180016a84  mov     dword ptr [rsp+2E8h+var_2A8], eax
0x180016a88  cmp     [rsp+2E8h+var_228], 8
0x180016a91  jb      short loc_180016AA5
0x180016a93  mov     rcx, [rsp+2E8h+var_240]
0x180016a9b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180016aa1  mov     eax, dword ptr [rsp+2E8h+var_2A8]
0x180016aa5  test    eax, eax
0x180016aa7  jnz     loc_180016C10
0x180016aad  lea     r8, [rsp+2E8h+var_2B4]; enum RemoveStages *
0x180016ab2  mov     rdx, r12; unsigned __int16 *
0x180016ab5  call    ?RemovePackageInternal@ProvOperations@@AEAAJPEBGAEAW4RemoveStages@@@Z; ProvOperations::RemovePackageInternal(ushort const *,RemoveStages &)
0x180016aba  mov     [rsp+2E8h+var_2B8], eax
0x180016abe  call    ?GetProgramDataProvisioningFolderPath@ProvisioningPaths@@SAAEBVexpanded_wstring@@XZ; ProvisioningPaths::GetProgramDataProvisioningFolderPath(void)
0x180016ac3  mov     rdx, [rax]; Src
0x180016ac6  mov     [rsp+2E8h+var_208], 7
0x180016ad2  mov     [rsp+2E8h+var_210], r14
0x180016ada  mov     word ptr [rsp+2E8h+var_220], r14w
0x180016ae3  cmp     [rdx], r14w
0x180016ae7  jnz     short loc_180016AEE
0x180016ae9  mov     r8, r14
0x180016aec  jmp     short loc_180016AFC
0x180016aee  or      r8, 0FFFFFFFFFFFFFFFFh
0x180016af2  inc     r8
0x180016af5  cmp     [rdx+r8*2], r14w
0x180016afa  jnz     short loc_180016AF2
0x180016afc  lea     rcx, [rsp+2E8h+var_220]; void *
0x180016b04  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180016b09  nop
0x180016b0a  mov     r13, [rbx]
0x180016b0d  mov     rax, [r13+0]
0x180016b11  mov     rax, [rax+60h]
0x180016b15  mov     [rsp+2E8h+var_2A8], rax
0x180016b1a  mov     [rsp+2E8h+var_228], 7
0x180016b26  mov     [rsp+2E8h+var_230], r14
0x180016b2e  mov     word ptr [rsp+2E8h+var_240], r14w
0x180016b37  or      r9, 0FFFFFFFFFFFFFFFFh
0x180016b3b  xor     r8d, r8d
0x180016b3e  lea     rdx, [rsp+2E8h+var_220]
0x180016b46  lea     rcx, [rsp+2E8h+var_240]; void *
0x180016b4e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180016b53  lea     rdx, [rsp+2E8h+var_240]
0x180016b5b  mov     rcx, r13
0x180016b5e  mov     rax, [rsp+2E8h+var_2A8]
0x180016b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b68  nop
0x180016b69  cmp     [rsp+2E8h+var_208], 8
0x180016b72  jb      short loc_180016B83
0x180016b74  mov     rcx, [rsp+2E8h+var_220]
0x180016b7c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180016b82  nop
0x180016b83  jmp     short loc_180016BAB
0x180016b85  lea     r15, ??_7RemovePackage@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@6B@; const Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackage::`vftable'
0x180016b8c  xor     r14d, r14d
0x180016b8f  mov     eax, [rsp+2E8h+var_2B8]
0x180016b93  mov     [rsp+2E8h+var_2B8], eax
0x180016b97  mov     rsi, [rsp+2E8h+var_288]
0x180016b9c  mov     rbx, [rsp+2E8h+var_2A0]
0x180016ba1  mov     rdi, [rsp+2E8h+var_290]
0x180016ba6  mov     r12, [rsp+2E8h+var_298]
0x180016bab  mov     eax, [rsp+2E8h+var_2B4]
0x180016baf  test    eax, eax
0x180016bb1  jz      short loc_180016C0D
0x180016bb3  mov     dword ptr [rsp+2E8h+var_2A8], eax
0x180016bb7  mov     rcx, [rbx]
0x180016bba  mov     rax, [rcx]
0x180016bbd  lea     rdx, [rsp+2E8h+var_240]
0x180016bc5  mov     rax, [rax+8]
0x180016bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016bce  cmp     qword ptr [rax+18h], 8
0x180016bd3  jb      short loc_180016BD8
0x180016bd5  mov     rax, [rax]
0x180016bd8  mov     [rsp+2E8h+var_2A0], rax
0x180016bdd  lea     r8, [rsp+2E8h+var_2A8]
0x180016be2  lea     rdx, [rsp+2E8h+var_2A0]
0x180016be7  lea     rcx, [rsp+2E8h+var_1F8]
0x180016bef  call    ??$RemovePackageFailure@PEBGI@RemovePackage@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAX$$QEAPEBG$$QEAI@Z; Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackage::RemovePackageFailure<ushort const *,uint>(ushort const * &&,uint &&)
0x180016bf4  cmp     [rsp+2E8h+var_228], 8
0x180016bfd  jb      short loc_180016C0D
0x180016bff  mov     rcx, [rsp+2E8h+var_240]
0x180016c07  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180016c0d  mov     r13b, 1
0x180016c10  add     rbx, 8
0x180016c14  jmp     loc_180016A32
0x180016c19  lea     rcx, [rsp+2E8h+var_278]
0x180016c1e  call    ??1?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>(void)
0x180016c23  test    r13b, r13b
0x180016c26  jz      loc_180016D3C
0x180016c2c  lea     rcx, [rsp+2E8h+var_A8]; this
0x180016c34  call    ??1PackageCollector@@UEAA@XZ; PackageCollector::~PackageCollector(void)
0x180016c39  nop
0x180016c3a  lea     rcx, [rsp+2E8h+var_258]; this
0x180016c42  call    ??1ProvAgent@@QEAA@XZ; ProvAgent::~ProvAgent(void)
0x180016c47  nop
0x180016c48  mov     ebx, [rsp+2E8h+var_2B8]
0x180016c4c  test    ebx, ebx
0x180016c4e  js      short loc_180016CA8
0x180016c50  test    cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, 1
0x180016c57  jz      short loc_180016C68
0x180016c59  mov     r8, r12
0x180016c5c  lea     rdx, ProvOpsRemovePackageSucceeded
0x180016c63  call    McTemplateU0z_EventWriteTransfer
0x180016c68  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x180016c6d  mov     ecx, [rax]
0x180016c6f  cmp     ecx, 5
0x180016c72  jbe     short loc_180016CA8
0x180016c74  mov     r8, [rsp+2E8h+var_E8]
0x180016c7c  add     r8, 8
0x180016c80  lea     rcx, [rsp+2E8h+var_A8]
0x180016c88  mov     [rsp+2E8h+var_2C0], rcx
0x180016c8d  mov     [rsp+2E8h+var_2C8], 2
0x180016c95  xor     r9d, r9d
0x180016c98  lea     rdx, byte_180040C7B
0x180016c9f  mov     rcx, rax
0x180016ca2  call    _tlgWriteTransfer_EventWriteTransfer
0x180016ca7  nop
0x180016ca8  mov     rcx, rsi
0x180016cab  jmp     loc_18001699E
0x180016cb0  mov     rcx, [rsp+2E8h+var_288]
0x180016cb5  call    ?Stop@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180016cba  nop
0x180016cbb  lea     r15, ??_7RemovePackage@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@6B@; const Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackage::`vftable'
0x180016cc2  mov     [rsp+2E8h+var_1F8], r15
0x180016cca  lea     rcx, [rsp+2E8h+var_1F8]
0x180016cd2  call    ?Destroy@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180016cd7  lea     rcx, [rsp+2E8h+var_1F8]
0x180016cdf  call    ??1?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180016ce4  mov     eax, [rsp+2E8h+var_2B8]
0x180016ce8  mov     rcx, [rsp+2E8h+var_30]
0x180016cf0  xor     rcx, rsp; StackCookie
0x180016cf3  call    __security_check_cookie
0x180016cf8  lea     r11, [rsp+2E8h+var_28]
0x180016d00  mov     rbx, [r11+40h]
0x180016d04  mov     rsi, [r11+48h]
0x180016d08  mov     rsp, r11
0x180016d0b  pop     r15
0x180016d0d  pop     r14
0x180016d0f  pop     r13
0x180016d11  pop     r12
0x180016d13  pop     rdi
0x180016d14  retn
0x180016d15  mov     ecx, 8000FFFFh
0x180016d1a  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180016d1f  mov     r9d, eax; char *
0x180016d22  mov     rcx, [rsp+2E8h]; this
0x180016d2a  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x180016d31  mov     edx, 290h; void *
0x180016d36  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180016d3c  mov     rcx, [rsp+2E8h]; this
0x180016d44  mov     r9d, 2; char *
0x180016d4a  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x180016d51  mov     edx, 2AFh; void *
0x180016d56  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
