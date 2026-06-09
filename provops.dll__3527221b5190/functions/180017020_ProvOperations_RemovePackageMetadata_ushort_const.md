# ProvOperations::RemovePackageMetadata(ushort const *)

- ea: `0x180017020`
- end: `0x180017377`
- name: `?RemovePackageMetadata@ProvOperations@@UEAAJPEBG@Z`
- size: `855`
- prototype: `__int64 __fastcall(ProvOperations *this, char *)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callees

- `0x180007674`
- `0x18000afb8`
- `0x18000ca00`
- `0x18000d1e4`
- `0x18000e454`
- `0x1800122e4`
- `0x1800161e4`
- `0x180016d64`
- `0x180017020`
- `0x180018bc0`
- `0x180019238`
- `0x18001b388`
- `0x1800202e4`
- `0x1800226dc`
- `0x180022784`
- `0x180024880`
- `0x18002a170`
- `0x18002ac38`
- `0x180033ed0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001725b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001725b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18001722b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18001722b`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x180017212`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x180017212`
- `policymanager!PolicyManager_GetPolicyInt` at `0x18001711b`
- `policymanager!PolicyManager_GetPolicyInt` at `0x18001711b`

## string_xrefs

- `0x180017364`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18001705e`: `RemovePackageMetadata`
- `0x1800170ac`: `Security`
- `0x1800170ca`: `AllowRemoveProvisioningPackage`

## pseudocode

```c
__int64 __fastcall ProvOperations::RemovePackageMetadata(ProvOperations *this, char *a2)
{
  char *v2; // rbx
  const unsigned __int16 *v3; // rdi
  int PolicyInt; // eax
  unsigned int v5; // edi
  __int64 v6; // r9
  __int64 v7; // rdx
  ProvOperations *v9; // rcx
  int v10; // eax
  int v11; // esi
  const struct expanded_wstring *ProgramDataProvisioningFolderPath; // r15
  __int64 v13; // rdx
  char *v14; // rdi
  HRESULT v15; // eax
  wil *v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  char v19; // di
  int v20; // ecx
  ULONG dwFlags; // [rsp+20h] [rbp-238h]
  ULONG dwFlagsa; // [rsp+20h] [rbp-238h]
  int v23; // [rsp+30h] [rbp-228h] BYREF
  int v24; // [rsp+34h] [rbp-224h] BYREF
  int v25; // [rsp+38h] [rbp-220h] BYREF
  const unsigned __int16 *v26; // [rsp+40h] [rbp-218h] BYREF
  PWSTR pszPathOut[2]; // [rsp+48h] [rbp-210h] BYREF
  __int64 v28; // [rsp+58h] [rbp-200h]
  _QWORD *v29; // [rsp+60h] [rbp-1F8h]
  char v30; // [rsp+68h] [rbp-1F0h]
  HANDLE v31[4]; // [rsp+70h] [rbp-1E8h] BYREF
  _QWORD v32[42]; // [rsp+90h] [rbp-1C8h] BYREF
  __int128 v33; // [rsp+1E0h] [rbp-78h] BYREF
  wchar_t v34; // [rsp+1F0h] [rbp-68h]
  _OWORD v35[2]; // [rsp+1F8h] [rbp-60h] BYREF
  _OWORD v36[2]; // [rsp+218h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  v2 = a2;
  v26 = (const unsigned __int16 *)a2;
  v3 = (const unsigned __int16 *)((char *)this + 16);
  if ( *((_QWORD *)this + 5) >= 8u )
    v3 = *(const unsigned __int16 **)v3;
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v32,
    "RemovePackageMetadata");
  v32[0] = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackageMetadata::`vftable';
  Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackageMetadata::StartActivity(
    (Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackageMetadata *)v32,
    v3);
  v29 = v32;
  v30 = 1;
  v25 = 0;
  v33 = *(_OWORD *)L"Security";
  v34 = aSecurity[8];
  v35[0] = *(_OWORD *)L"AllowRemoveProvisioningPackage";
  v35[1] = *(_OWORD *)L"oveProvisioningPackage";
  v36[0] = *(_OWORD *)L"sioningPackage";
  *(_OWORD *)((char *)v36 + 14) = *(_OWORD *)L"Package";
  PolicyInt = PolicyManager_GetPolicyInt(&v33, v35, &v25);
  v5 = PolicyInt;
  if ( PolicyInt < 0 )
  {
    v6 = (unsigned int)PolicyInt;
    v7 = 527;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
      (const char *)v6,
      dwFlags);
    wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v32);
    v32[0] = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackageMetadata::`vftable';
    wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v32);
    wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v32);
    return v5;
  }
  if ( !v25 )
  {
    v5 = -2147024891;
    v6 = 2147942405LL;
    v7 = 528;
    goto LABEL_7;
  }
  try
  {
    v24 = 0;
    ProvAgent::ProvAgent((ProvAgent *)v31);
    ProvAgent::LockForProvisioning(v31);
    v10 = ProvOperations::RemovePackageInternal(v9, v2, (enum RemoveStages *)&v24);
    try
    {
      v11 = v10;
      ProgramDataProvisioningFolderPath = ProvisioningPaths::GetProgramDataProvisioningFolderPath();
      *(_OWORD *)pszPathOut = 0;
      v13 = 0;
      v28 = 0;
      if ( *((_DWORD *)ProgramDataProvisioningFolderPath + 2) != -266 )
      {
        std::vector<unsigned short>::_Reallocate(
          pszPathOut,
          (unsigned int)(*((_DWORD *)ProgramDataProvisioningFolderPath + 2) + 260) + 6LL);
        v13 = v28;
      }
      v14 = (char *)pszPathOut[0];
      v15 = PathCchCombineEx(
              pszPathOut[0],
              (signed __int64)(v13 - (unsigned __int64)pszPathOut[0]) >> 1,
              *(PCWSTR *)ProgramDataProvisioningFolderPath,
              (PCWSTR)v2,
              1u);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x22B,
          (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
          (const char *)(unsigned int)v15,
          dwFlagsa);
      if ( PathFileExistsW((LPCWSTR)v14) )
      {
        v17 = wil::RemoveDirectoryRecursiveNoThrow(v14, 0, (void *)0xFFFFFFFFFFFFFFFFLL);
        v16 = retaddr;
        if ( v17 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x186,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
            (const char *)(unsigned int)v17,
            dwFlagsa);
      }
      if ( v14 )
        operator delete(v14);
    }
    catch ( ... )
    {
      v24 |= 8u;
      v23 = wil::ResultFromCaughtException(v16);
      v11 = v23;
      v2 = (char *)v26;
    }
  }
  catch ( ... )
  {
    v23 = wil::ResultFromCaughtException(v16);
    v11 = v23;
    v2 = (char *)v26;
    goto LABEL_17;
  }
  ProvAgent::~ProvAgent((ProvAgent *)v31);
LABEL_17:
  v19 = v24;
  if ( v24 || v11 < 0 )
  {
    v23 = v24;
    Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackageMetadata::RemovePackageMetadataFailure<unsigned short const * &,unsigned int>(
      (__int64)v32,
      (__int64 *)&v26,
      &v23);
    if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 2) != 0 )
      McTemplateU0dzq_EventWriteTransfer(v20, (unsigned int)ProvOpsRemovePackageMetadataFailed, v11, (_DWORD)v2, v19);
  }
  else if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 1) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(v18, ProvOpsRemovePackageMetadataSucceeded, v2);
  }
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v32);
  v32[0] = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackageMetadata::`vftable';
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v32);
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v32);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180017020  mov     [rsp+arg_10], rbx
0x180017025  mov     [rsp+arg_18], rsi
0x18001702a  push    rdi
0x18001702b  push    r14
0x18001702d  push    r15
0x18001702f  sub     rsp, 240h
0x180017036  mov     rax, cs:__security_cookie
0x18001703d  xor     rax, rsp
0x180017040  mov     [rsp+258h+var_20], rax
0x180017048  mov     rbx, rdx
0x18001704b  mov     [rsp+258h+var_218], rdx
0x180017050  lea     rdi, [rcx+10h]
0x180017054  cmp     qword ptr [rdi+18h], 8
0x180017059  jb      short loc_18001705E
0x18001705b  mov     rdi, [rdi]
0x18001705e  lea     rdx, aRemovepackagem; "RemovePackageMetadata"
0x180017065  lea     rcx, [rsp+258h+var_1C8]
0x18001706d  call    ??0?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180017072  lea     r14, ??_7RemovePackageMetadata@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@6B@; const Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackageMetadata::`vftable'
0x180017079  mov     [rsp+258h+var_1C8], r14
0x180017081  mov     rdx, rdi; unsigned __int16 *
0x180017084  lea     rcx, [rsp+258h+var_1C8]; this
0x18001708c  call    ?StartActivity@RemovePackageMetadata@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAXPEBG@Z; Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackageMetadata::StartActivity(ushort const *)
0x180017091  nop
0x180017092  lea     rax, [rsp+258h+var_1C8]
0x18001709a  mov     [rsp+258h+var_1F8], rax
0x18001709f  mov     [rsp+258h+var_1F0], 1
0x1800170a4  mov     [rsp+258h+var_220], 0
0x1800170ac  movups  xmm0, xmmword ptr cs:aSecurity; "Security"
0x1800170b3  movups  [rsp+258h+var_78], xmm0
0x1800170bb  movzx   eax, word ptr cs:aSecurity+10h; ""
0x1800170c2  mov     [rsp+258h+var_68], ax
0x1800170ca  movups  xmm0, xmmword ptr cs:aAllowremovepro; "AllowRemoveProvisioningPackage"
0x1800170d1  movups  [rsp+258h+var_60], xmm0
0x1800170d9  movups  xmm1, xmmword ptr cs:aAllowremovepro+10h; "oveProvisioningPackage"
0x1800170e0  movups  [rsp+258h+var_50], xmm1
0x1800170e8  movups  xmm0, xmmword ptr cs:aAllowremovepro+20h; "sioningPackage"
0x1800170ef  movups  xmmword ptr [rsp+258h+var_40], xmm0
0x1800170f7  movups  xmm1, xmmword ptr cs:aAllowremovepro+2Eh; "Package"
0x1800170fe  movups  xmmword ptr [rsp+258h+var_40+0Eh], xmm1
0x180017106  lea     r8, [rsp+258h+var_220]
0x18001710b  lea     rdx, [rsp+258h+var_60]
0x180017113  lea     rcx, [rsp+258h+var_78]
0x18001711b  call    cs:__imp_PolicyManager_GetPolicyInt
0x180017121  mov     edi, eax
0x180017123  test    eax, eax
0x180017125  jns     short loc_180017131
0x180017127  mov     r9d, eax
0x18001712a  mov     edx, 20Fh
0x18001712f  jmp     short loc_180017145
0x180017131  cmp     [rsp+258h+var_220], 0
0x180017136  jnz     short loc_180017191
0x180017138  mov     edi, 80070005h
0x18001713d  mov     r9d, edi; char *
0x180017140  mov     edx, 210h; void *
0x180017145  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x18001714c  mov     rcx, [rsp+258h]; this
0x180017154  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017159  nop
0x18001715a  lea     rcx, [rsp+258h+var_1C8]
0x180017162  call    ?Stop@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180017167  nop
0x180017168  mov     [rsp+258h+var_1C8], r14
0x180017170  lea     rcx, [rsp+258h+var_1C8]
0x180017178  call    ?Destroy@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001717d  lea     rcx, [rsp+258h+var_1C8]
0x180017185  call    ??1?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001718a  mov     eax, edi
0x18001718c  jmp     loc_180017324
0x180017191  mov     [rsp+258h+var_224], 0
0x180017199  lea     rcx, [rsp+258h+var_1E8]; this
0x18001719e  call    ??0ProvAgent@@QEAA@XZ; ProvAgent::ProvAgent(void)
0x1800171a3  nop
0x1800171a4  lea     rcx, [rsp+258h+var_1E8]; this
0x1800171a9  call    ?LockForProvisioning@ProvAgent@@QEAAXXZ; ProvAgent::LockForProvisioning(void)
0x1800171ae  lea     r8, [rsp+258h+var_224]; enum RemoveStages *
0x1800171b3  mov     rdx, rbx; unsigned __int16 *
0x1800171b6  call    ?RemovePackageInternal@ProvOperations@@AEAAJPEBGAEAW4RemoveStages@@@Z; ProvOperations::RemovePackageInternal(ushort const *,RemoveStages &)
0x1800171bb  mov     esi, eax
0x1800171bd  call    ?GetProgramDataProvisioningFolderPath@ProvisioningPaths@@SAAEBVexpanded_wstring@@XZ; ProvisioningPaths::GetProgramDataProvisioningFolderPath(void)
0x1800171c2  mov     r15, rax
0x1800171c5  xorps   xmm0, xmm0
0x1800171c8  movdqu  xmmword ptr [rsp+258h+pszPathOut], xmm0
0x1800171ce  xor     edx, edx
0x1800171d0  mov     [rsp+258h+var_200], rdx
0x1800171d5  mov     ecx, [rax+8]
0x1800171d8  add     ecx, 104h
0x1800171de  add     rcx, 6
0x1800171e2  jz      short loc_1800171F6
0x1800171e4  mov     rdx, rcx
0x1800171e7  lea     rcx, [rsp+258h+pszPathOut]
0x1800171ec  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x1800171f1  mov     rdx, [rsp+258h+var_200]
0x1800171f6  mov     rdi, [rsp+258h+pszPathOut]
0x1800171fb  sub     rdx, rdi
0x1800171fe  sar     rdx, 1; cchPathOut
0x180017201  mov     [rsp+258h+dwFlags], 1; int
0x180017209  mov     r9, rbx; pszMore
0x18001720c  mov     r8, [r15]; pszPathIn
0x18001720f  mov     rcx, rdi; pszPathOut
0x180017212  call    cs:__imp_PathCchCombineEx
0x180017218  mov     rcx, [rsp+258h]; this
0x180017220  test    eax, eax
0x180017222  js      loc_18001734D
0x180017228  mov     rcx, rdi; pszPath
0x18001722b  call    cs:__imp_PathFileExistsW
0x180017231  test    eax, eax
0x180017233  jz      short loc_180017253
0x180017235  or      r8, 0FFFFFFFFFFFFFFFFh
0x180017239  xor     edx, edx
0x18001723b  mov     rcx, rdi
0x18001723e  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x180017243  mov     rcx, [rsp+258h]; this
0x18001724b  test    eax, eax
0x18001724d  js      loc_180017361
0x180017253  test    rdi, rdi
0x180017256  jz      short loc_180017262
0x180017258  mov     rcx, rdi
0x18001725b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180017261  nop
0x180017262  jmp     short loc_180017274
0x180017264  lea     r14, ??_7RemovePackageMetadata@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@6B@; const Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackageMetadata::`vftable'
0x18001726b  mov     esi, [rsp+258h+var_228]
0x18001726f  mov     rbx, [rsp+258h+var_218]
0x180017274  lea     rcx, [rsp+258h+var_1E8]; this
0x180017279  call    ??1ProvAgent@@QEAA@XZ; ProvAgent::~ProvAgent(void)
0x18001727e  nop
0x18001727f  jmp     short loc_180017291
0x180017281  lea     r14, ??_7RemovePackageMetadata@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@6B@; const Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackageMetadata::`vftable'
0x180017288  mov     esi, [rsp+258h+var_228]
0x18001728c  mov     rbx, [rsp+258h+var_218]
0x180017291  mov     edi, [rsp+258h+var_224]
0x180017295  test    edi, edi
0x180017297  jnz     short loc_1800172B7
0x180017299  test    esi, esi
0x18001729b  js      short loc_1800172B7
0x18001729d  test    cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, 1
0x1800172a4  jz      short loc_1800172F2
0x1800172a6  mov     r8, rbx
0x1800172a9  lea     rdx, ProvOpsRemovePackageMetadataSucceeded
0x1800172b0  call    McTemplateU0z_EventWriteTransfer
0x1800172b5  jmp     short loc_1800172F2
0x1800172b7  mov     [rsp+258h+var_228], edi
0x1800172bb  lea     r8, [rsp+258h+var_228]
0x1800172c0  lea     rdx, [rsp+258h+var_218]
0x1800172c5  lea     rcx, [rsp+258h+var_1C8]
0x1800172cd  call    ??$RemovePackageMetadataFailure@AEAPEBGI@RemovePackageMetadata@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAXAEAPEBG$$QEAI@Z; Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackageMetadata::RemovePackageMetadataFailure<ushort const * &,uint>(ushort const * &,uint &&)
0x1800172d2  test    cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, 2
0x1800172d9  jz      short loc_1800172F2
0x1800172db  mov     [rsp+258h+dwFlags], edi
0x1800172df  mov     r9, rbx
0x1800172e2  mov     r8d, esi
0x1800172e5  lea     rdx, ProvOpsRemovePackageMetadataFailed
0x1800172ec  call    McTemplateU0dzq_EventWriteTransfer
0x1800172f1  nop
0x1800172f2  lea     rcx, [rsp+258h+var_1C8]
0x1800172fa  call    ?Stop@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800172ff  nop
0x180017300  mov     [rsp+258h+var_1C8], r14
0x180017308  lea     rcx, [rsp+258h+var_1C8]
0x180017310  call    ?Destroy@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180017315  lea     rcx, [rsp+258h+var_1C8]
0x18001731d  call    ??1?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180017322  mov     eax, esi
0x180017324  mov     rcx, [rsp+258h+var_20]
0x18001732c  xor     rcx, rsp; StackCookie
0x18001732f  call    __security_check_cookie
0x180017334  lea     r11, [rsp+258h+var_18]
0x18001733c  mov     rbx, [r11+30h]
0x180017340  mov     rsi, [r11+38h]
0x180017344  mov     rsp, r11
0x180017347  pop     r15
0x180017349  pop     r14
0x18001734b  pop     rdi
0x18001734c  retn
0x18001734d  mov     r9d, eax; char *
0x180017350  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x180017357  mov     edx, 22Bh; void *
0x18001735c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180017361  mov     r9d, eax; char *
0x180017364  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001736b  mov     edx, 186h; void *
0x180017370  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
