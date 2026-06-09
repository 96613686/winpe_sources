# WcsSetCalibrationManagementState

- ea: `0x18004ba30`
- end: `0x18004bd67`
- name: `WcsSetCalibrationManagementState`
- size: `823`
- prototype: `BOOL __stdcall(BOOL bIsEnabled)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800028d8`
- `0x180006e34`
- `0x180019610`
- `0x18001fb80`
- `0x1800223b8`
- `0x180023a4c`
- `0x18002e5f0`
- `0x180049040`
- `0x18004aef8`
- `0x18004b680`
- `0x18004ba30`
- `0x180084010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18004bc7c`
- `ntdll!EtwEventWrite` at `0x18004bc7c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004bb72`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004bb72`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004bb09`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004bb33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004bb09`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004bb33`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004bbbe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004bbbe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004bc92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004bca1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004bc92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004bca1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004bcbd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004bcbd`

## pseudocode

```c
BOOL __stdcall WcsSetCalibrationManagementState(BOOL bIsEnabled)
{
  struct IRegisteredTask *v1; // rdi
  HRESULT v2; // ebx
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rdx
  __int64 v6; // rcx
  LSTATUS v7; // ebx
  LSTATUS v8; // eax
  int CalibrationTask; // edi
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  BYTE Data[4]; // [rsp+50h] [rbp-29h] BYREF
  int v17; // [rsp+54h] [rbp-25h] BYREF
  struct IRegisteredTask *v18; // [rsp+58h] [rbp-21h] BYREF
  DWORD Type; // [rsp+60h] [rbp-19h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-15h] BYREF
  int v21; // [rsp+68h] [rbp-11h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-9h] BYREF
  BYTE v23[4]; // [rsp+78h] [rbp-1h] BYREF
  BOOL v24; // [rsp+7Ch] [rbp+3h] BYREF
  __int64 v25; // [rsp+80h] [rbp+7h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v27; // [rsp+90h] [rbp+17h] BYREF
  _QWORD v28[2]; // [rsp+98h] [rbp+1Fh] BYREF
  BOOL v29; // [rsp+E0h] [rbp+67h] BYREF

  v29 = bIsEnabled;
  v1 = 0;
  hKey = 0;
  v18 = 0;
  *(_DWORD *)Data = 0;
  v21 = 0;
  phkResult = 0;
  v2 = COMInit::CoInitialize((COMInit *)&v21);
  if ( (unsigned int)dword_18009E080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009E080, 0x200000000000LL) )
  {
    v17 = v29;
    v25 = 0x2000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (__int64)&dword_18009E080,
      (unsigned __int8 *)byte_1800918D1,
      v3,
      v4,
      (__int64)&v17,
      (__int64)&v25);
  }
  if ( v2 < 0 )
  {
    v5 = (unsigned int)v2;
    v6 = (unsigned int)v2;
LABEL_6:
    v7 = Win32StatusFromHRESULT(v6, v5);
    goto LABEL_28;
  }
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, gszICMRegPath, 0, 0x2011Fu, &hKey);
  if ( !v7 )
  {
    v7 = RegOpenKeyExW(hKey, L"Calibration", 0, 0x2011Fu, &phkResult);
    if ( !v7 )
    {
      Type = 0;
      cbData = 4;
      v8 = RegQueryValueExW(phkResult, L"CalibrationManagementEnabled", 0, &Type, Data, &cbData);
      v7 = v8;
      if ( !v8 )
      {
        if ( Type == 4 && cbData == 4 )
        {
          LOBYTE(v8) = v29;
          *(_DWORD *)v23 = v8;
          v7 = RegSetValueExW(phkResult, L"CalibrationManagementEnabled", 0, 4u, v23, 4u);
          if ( v7 )
            goto LABEL_28;
          if ( v29 != (*(_DWORD *)Data != 0) )
          {
            CalibrationTask = GetCalibrationTask(&v18);
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::GetImpl'::`2'::impl) )
            {
              if ( CalibrationTask < 0 )
              {
LABEL_16:
                v1 = v18;
                goto LABEL_28;
              }
            }
            else if ( CalibrationTask < 0 )
            {
              v7 = Win32StatusFromHRESULT((unsigned int)CalibrationTask, (unsigned int)CalibrationTask);
              goto LABEL_16;
            }
            v1 = v18;
            if ( v29 )
              v10 = 0xFFFFFFFFLL;
            else
              v10 = 0;
            v11 = ((__int64 (__fastcall *)(struct IRegisteredTask *, __int64))v18->lpVtbl->put_Enabled)(v18, v10);
            v5 = (unsigned int)v11;
            if ( v11 < 0 )
            {
              v6 = (unsigned int)v11;
              goto LABEL_6;
            }
            if ( v29 )
              InternalRefreshCalibration(0, 1u);
          }
          v28[0] = &v29;
          v28[1] = 4;
          EtwEventWrite(g_etwHandle, SETTING_CALIBRATION_MANAGEMENT, 1, v28);
        }
        else
        {
          v7 = 87;
        }
      }
    }
  }
LABEL_28:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v1 )
    ((void (__fastcall *)(struct IRegisteredTask *))v1->lpVtbl->Release)(v1);
  SetLastError(v7);
  if ( (unsigned int)dword_18009E080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009E080, 0x400000000000LL) )
  {
    v17 = *(_DWORD *)Data;
    v24 = v29;
    v27 = 0x2000000;
    LODWORD(v25) = v7;
    LODWORD(v18) = v7 == 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v12,
      (__int64)byte_180091AE3,
      v13,
      v14,
      (__int64)&v18,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&v17,
      (__int64)&v27);
  }
  COMInit::~COMInit((COMInit *)&v21);
  return v7 == 0;
}

```

## disassembly

```asm
0x18004ba30  mov     [rsp-8+arg_0], ecx
0x18004ba34  push    rbp
0x18004ba35  push    rbx
0x18004ba36  push    rdi
0x18004ba37  push    r14
0x18004ba39  lea     rbp, [rsp-3Fh]
0x18004ba3e  sub     rsp, 0B8h
0x18004ba45  mov     rax, cs:__security_cookie
0x18004ba4c  xor     rax, rsp
0x18004ba4f  mov     [rbp+57h+var_28], rax
0x18004ba53  xor     edi, edi
0x18004ba55  mov     [rbp+57h+hKey], 0
0x18004ba5d  lea     rcx, [rbp+57h+var_68]; this
0x18004ba61  mov     [rbp+57h+var_78], rdi
0x18004ba65  mov     dword ptr [rbp+57h+Data], edi
0x18004ba68  mov     [rbp+57h+var_68], edi
0x18004ba6b  mov     [rbp+57h+var_60], 0
0x18004ba73  call    ?CoInitialize@COMInit@@QEAAJXZ; COMInit::CoInitialize(void)
0x18004ba78  mov     ecx, cs:dword_18009E080
0x18004ba7e  mov     ebx, eax
0x18004ba80  cmp     ecx, 5
0x18004ba83  jbe     short loc_18004BAD2
0x18004ba85  mov     rdx, 200000000000h
0x18004ba8f  lea     rcx, dword_18009E080
0x18004ba96  call    _tlgKeywordOn
0x18004ba9b  test    al, al
0x18004ba9d  jz      short loc_18004BAD2
0x18004ba9f  mov     eax, [rbp+57h+arg_0]
0x18004baa2  lea     rdx, byte_1800918D1
0x18004baa9  mov     [rbp+57h+var_7C], eax
0x18004baac  lea     rcx, dword_18009E080
0x18004bab3  lea     rax, [rbp+57h+var_50]
0x18004bab7  mov     [rbp+57h+var_50], 2000000h
0x18004babf  mov     [rsp+0D0h+lpcbData], rax
0x18004bac4  lea     rax, [rbp+57h+var_7C]
0x18004bac8  mov     [rsp+0D0h+phkResult], rax
0x18004bacd  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18004bad2  test    ebx, ebx
0x18004bad4  jns     short loc_18004BAE6
0x18004bad6  mov     edx, ebx
0x18004bad8  mov     ecx, ebx
0x18004bada  call    Win32StatusFromHRESULT
0x18004badf  mov     ebx, eax
0x18004bae1  jmp     loc_18004BC89
0x18004bae6  lea     rax, [rbp+57h+hKey]
0x18004baea  mov     r14d, 2011Fh
0x18004baf0  mov     r9d, r14d; samDesired
0x18004baf3  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18004baf8  xor     r8d, r8d; ulOptions
0x18004bafb  lea     rdx, gszICMRegPath; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18004bb02  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004bb09  call    cs:__imp_RegOpenKeyExW
0x18004bb0f  mov     ebx, eax
0x18004bb11  test    eax, eax
0x18004bb13  jnz     loc_18004BC89
0x18004bb19  mov     rcx, [rbp+57h+hKey]; hKey
0x18004bb1d  lea     rax, [rbp+57h+var_60]
0x18004bb21  mov     r9d, r14d; samDesired
0x18004bb24  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18004bb29  xor     r8d, r8d; ulOptions
0x18004bb2c  lea     rdx, SubKey; "Calibration"
0x18004bb33  call    cs:__imp_RegOpenKeyExW
0x18004bb39  mov     ebx, eax
0x18004bb3b  test    eax, eax
0x18004bb3d  jnz     loc_18004BC89
0x18004bb43  mov     rcx, [rbp+57h+var_60]; hKey
0x18004bb47  lea     r14d, [rax+4]
0x18004bb4b  lea     rax, [rbp+57h+cbData]
0x18004bb4f  mov     [rbp+57h+Type], edi
0x18004bb52  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18004bb57  lea     r9, [rbp+57h+Type]; lpType
0x18004bb5b  lea     rax, [rbp+57h+Data]
0x18004bb5f  mov     [rbp+57h+cbData], r14d
0x18004bb63  xor     r8d, r8d; lpReserved
0x18004bb66  mov     [rsp+0D0h+phkResult], rax; lpData
0x18004bb6b  lea     rdx, ValueName; "CalibrationManagementEnabled"
0x18004bb72  call    cs:__imp_RegQueryValueExW
0x18004bb78  mov     ebx, eax
0x18004bb7a  test    eax, eax
0x18004bb7c  jnz     loc_18004BC89
0x18004bb82  cmp     [rbp+57h+Type], r14d
0x18004bb86  jnz     loc_18004BC84
0x18004bb8c  cmp     [rbp+57h+cbData], r14d
0x18004bb90  jnz     loc_18004BC84
0x18004bb96  cmp     [rbp+57h+arg_0], eax
0x18004bb99  lea     rdx, ValueName; "CalibrationManagementEnabled"
0x18004bba0  mov     rcx, [rbp+57h+var_60]; hKey
0x18004bba4  mov     r9d, r14d; dwType
0x18004bba7  setnz   al
0x18004bbaa  mov     dword ptr [rsp+0D0h+lpcbData], r14d; cbData
0x18004bbaf  mov     dword ptr [rbp+57h+var_58], eax
0x18004bbb2  xor     r8d, r8d; Reserved
0x18004bbb5  lea     rax, [rbp+57h+var_58]
0x18004bbb9  mov     [rsp+0D0h+phkResult], rax; lpData
0x18004bbbe  call    cs:__imp_RegSetValueExW
0x18004bbc4  mov     ebx, eax
0x18004bbc6  test    eax, eax
0x18004bbc8  jnz     loc_18004BC89
0x18004bbce  xor     ecx, ecx
0x18004bbd0  cmp     [rbp+57h+arg_0], ecx
0x18004bbd3  setnz   cl
0x18004bbd6  cmp     dword ptr [rbp+57h+Data], eax
0x18004bbd9  setnz   al
0x18004bbdc  cmp     ecx, eax
0x18004bbde  jz      short loc_18004BC58
0x18004bbe0  lea     rcx, [rbp+57h+var_78]; struct IRegisteredTask **
0x18004bbe4  call    ?GetCalibrationTask@@YAJPEAPEAUIRegisteredTask@@@Z; GetCalibrationTask(IRegisteredTask * *)
0x18004bbe9  mov     edi, eax
0x18004bbeb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer> `wil::Feature<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::GetImpl(void)'::`2'::impl
0x18004bbf2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::__private_IsEnabled(void)
0x18004bbf7  test    al, al
0x18004bbf9  jz      short loc_18004BC08
0x18004bbfb  test    edi, edi
0x18004bbfd  jns     short loc_18004BC19
0x18004bbff  mov     rdi, [rbp+57h+var_78]
0x18004bc03  jmp     loc_18004BC89
0x18004bc08  test    edi, edi
0x18004bc0a  jns     short loc_18004BC19
0x18004bc0c  mov     edx, edi
0x18004bc0e  mov     ecx, edi
0x18004bc10  call    Win32StatusFromHRESULT
0x18004bc15  mov     ebx, eax
0x18004bc17  jmp     short loc_18004BBFF
0x18004bc19  cmp     [rbp+57h+arg_0], 0
0x18004bc1d  mov     rdi, [rbp+57h+var_78]
0x18004bc21  mov     rax, [rdi]
0x18004bc24  jz      short loc_18004BC2B
0x18004bc26  or      edx, 0FFFFFFFFh
0x18004bc29  jmp     short loc_18004BC2D
0x18004bc2b  xor     edx, edx
0x18004bc2d  mov     rax, [rax+58h]
0x18004bc31  mov     rcx, rdi
0x18004bc34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bc39  mov     edx, eax
0x18004bc3b  test    eax, eax
0x18004bc3d  jns     short loc_18004BC46
0x18004bc3f  mov     ecx, eax
0x18004bc41  jmp     loc_18004BADA
0x18004bc46  cmp     [rbp+57h+arg_0], 0
0x18004bc4a  jz      short loc_18004BC58
0x18004bc4c  mov     edx, 1
0x18004bc51  xor     ecx, ecx; lpString1
0x18004bc53  call    InternalRefreshCalibration
0x18004bc58  mov     rcx, cs:g_etwHandle
0x18004bc5f  lea     rax, [rbp+57h+arg_0]
0x18004bc63  lea     r9, [rbp+57h+var_38]
0x18004bc67  mov     [rbp+57h+var_38], rax
0x18004bc6b  mov     r8d, 1
0x18004bc71  mov     [rbp+57h+var_30], r14
0x18004bc75  lea     rdx, SETTING_CALIBRATION_MANAGEMENT
0x18004bc7c  call    cs:__imp_EtwEventWrite
0x18004bc82  jmp     short loc_18004BC89
0x18004bc84  mov     ebx, 57h ; 'W'
0x18004bc89  mov     rcx, [rbp+57h+hKey]; hKey
0x18004bc8d  test    rcx, rcx
0x18004bc90  jz      short loc_18004BC98
0x18004bc92  call    cs:__imp_RegCloseKey
0x18004bc98  mov     rcx, [rbp+57h+var_60]; hKey
0x18004bc9c  test    rcx, rcx
0x18004bc9f  jz      short loc_18004BCA7
0x18004bca1  call    cs:__imp_RegCloseKey
0x18004bca7  test    rdi, rdi
0x18004bcaa  jz      short loc_18004BCBB
0x18004bcac  mov     rax, [rdi]
0x18004bcaf  mov     rcx, rdi
0x18004bcb2  mov     rax, [rax+10h]
0x18004bcb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bcbb  mov     ecx, ebx; dwErrCode
0x18004bcbd  call    cs:__imp_SetLastError
0x18004bcc3  mov     eax, cs:dword_18009E080
0x18004bcc9  xor     edi, edi
0x18004bccb  test    ebx, ebx
0x18004bccd  setz    dil
0x18004bcd1  cmp     eax, 5
0x18004bcd4  jbe     short loc_18004BD43
0x18004bcd6  mov     rdx, 400000000000h
0x18004bce0  lea     rcx, dword_18009E080
0x18004bce7  call    _tlgKeywordOn
0x18004bcec  test    al, al
0x18004bcee  jz      short loc_18004BD43
0x18004bcf0  mov     eax, dword ptr [rbp+57h+Data]
0x18004bcf3  lea     rdx, byte_180091AE3
0x18004bcfa  mov     [rbp+57h+var_7C], eax
0x18004bcfd  mov     eax, [rbp+57h+arg_0]
0x18004bd00  mov     [rbp+57h+var_54], eax
0x18004bd03  lea     rax, [rbp+57h+var_40]
0x18004bd07  mov     [rsp+0D0h+var_90], rax
0x18004bd0c  lea     rax, [rbp+57h+var_7C]
0x18004bd10  mov     [rsp+0D0h+var_98], rax
0x18004bd15  lea     rax, [rbp+57h+var_54]
0x18004bd19  mov     [rsp+0D0h+var_A0], rax
0x18004bd1e  lea     rax, [rbp+57h+var_50]
0x18004bd22  mov     [rsp+0D0h+lpcbData], rax
0x18004bd27  lea     rax, [rbp+57h+var_78]
0x18004bd2b  mov     [rsp+0D0h+phkResult], rax
0x18004bd30  mov     [rbp+57h+var_40], 2000000h
0x18004bd38  mov     dword ptr [rbp+57h+var_50], ebx
0x18004bd3b  mov     dword ptr [rbp+57h+var_78], edi
0x18004bd3e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18004bd43  lea     rcx, [rbp+57h+var_68]; this
0x18004bd47  call    ??1COMInit@@QEAA@XZ; COMInit::~COMInit(void)
0x18004bd4c  mov     eax, edi
0x18004bd4e  mov     rcx, [rbp+57h+var_28]
0x18004bd52  xor     rcx, rsp; StackCookie
0x18004bd55  call    __security_check_cookie
0x18004bd5a  add     rsp, 0B8h
0x18004bd61  pop     r14
0x18004bd63  pop     rdi
0x18004bd64  pop     rbx
0x18004bd65  pop     rbp
0x18004bd66  retn
```
