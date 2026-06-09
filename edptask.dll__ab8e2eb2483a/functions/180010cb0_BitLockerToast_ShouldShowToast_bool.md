# BitLockerToast::ShouldShowToast(bool *)

- ea: `0x180010cb0`
- end: `0x180011269`
- name: `?ShouldShowToast@BitLockerToast@@UEAAJPEA_N@Z`
- size: `1465`
- prototype: `__int64 __fastcall(BitLockerToast *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000108c`
- `0x1800056c4`
- `0x18000aa00`
- `0x180010cb0`
- `0x180012d50`
- `0x180012e30`
- `0x180012eb4`
- `0x180012f48`
- `0x1800133e2`
- `0x180013410`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010dc4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011164`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800111dc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010dc4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011164`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800111dc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180011191`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180011191`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180010e75`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180010e75`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180011239`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180011239`
- `ntdll!RtlIsMultiSessionSku` at `0x180010d21`
- `ntdll!RtlIsMultiSessionSku` at `0x180010d21`
- `FVEAPI!FveGetStatusW` at `0x180010f11`
- `FVEAPI!FveGetStatusW` at `0x180010f11`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x180010d47`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x180010fb4`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x1800110d9`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x180010d47`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x180010fb4`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x1800110d9`
- `ext-ms-win-shell-shell32-l1-2-2!__imp_GetSettingsEnvironmentInstance` at `0x180010ddf`
- `ext-ms-win-shell-shell32-l1-2-2!__imp_GetSettingsEnvironmentInstance` at `0x180010ddf`
- `dsreg!DsrIsDeviceJoined` at `0x180010fd6`
- `dsreg!DsrIsDeviceJoined` at `0x180010fd6`

## string_xrefs

- `0x180010daf`: `UserSecurityAreaPolicyQueried`
- `0x180010d62`: `ds\security\efs\edptask\toast\edptoast.cpp`
- `0x180010df5`: `ds\security\efs\edptask\toast\edptoast.cpp`
- `0x180010f54`: `ds\security\efs\edptask\toast\edptoast.cpp`

## pseudocode

```c
__int64 __fastcall BitLockerToast::ShouldShowToast(BitLockerToast *this, bool *a2)
{
  int PolicyInt; // ebx
  __int64 v4; // rdx
  int SettingsEnvironmentInstance; // eax
  __int64 v7; // rcx
  char v8; // si
  __int64 v9; // rcx
  __int64 v10; // rcx
  BOOL v11; // ebx
  int started; // edi
  __int64 v13; // rdx
  DWORD v14; // eax
  BitLockerToast *v15; // rcx
  LSTATUS ValueW; // eax
  bool v17; // sf
  LSTATUS v18; // eax
  bool v19; // sf
  char v20; // [rsp+40h] [rbp-C0h] BYREF
  bool v21; // [rsp+41h] [rbp-BFh] BYREF
  DWORD pcbData[2]; // [rsp+48h] [rbp-B8h] BYREF
  int pvData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v24[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 Data; // [rsp+60h] [rbp-A0h] BYREF
  int v26; // [rsp+68h] [rbp-98h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v28[3]; // [rsp+80h] [rbp-80h] BYREF
  int v29; // [rsp+8Ch] [rbp-74h]
  _OSVERSIONINFOW VersionInformation; // [rsp+110h] [rbp+10h] BYREF
  __int16 v31; // [rsp+228h] [rbp+128h]
  _BYTE v32[32]; // [rsp+230h] [rbp+130h] BYREF
  DWORD *v33; // [rsp+250h] [rbp+150h]
  __int64 v34; // [rsp+258h] [rbp+158h]
  _BYTE v35[528]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+3C8h]

  v20 = 0;
  memset_0(v28, 0, 0x90u);
  memset_0(v35, 0, 0x208u);
  v26 = 0;
  SystemTimeAsFileTime = 0;
  Data = 0;
  *a2 = 0;
  if ( !(unsigned __int8)RtlIsMultiSessionSku() )
    goto LABEL_71;
  v24[0] = 0;
  PolicyInt = PolicyManager_GetPolicyInt(L"BitLocker", L"RequireDeviceEncryption", v24);
  if ( PolicyInt < 0 )
  {
    v4 = 1247;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (int)"ds\\security\\efs\\edptask\\toast\\edptoast.cpp",
      (const char *)(unsigned int)PolicyInt);
    return (unsigned int)PolicyInt;
  }
  if ( v24[0] != 1 )
  {
    pvData = 0;
    pcbData[0] = 4;
    RegGetValueW(
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\BitLockerCsp\\UserOptions",
      L"UserSecurityAreaPolicyQueried",
      0x20000018u,
      0,
      &pvData,
      pcbData);
    if ( pvData != 1 )
      goto LABEL_71;
  }
  *(_QWORD *)pcbData = 0;
  SettingsEnvironmentInstance = GetSettingsEnvironmentInstance(pcbData);
  PolicyInt = SettingsEnvironmentInstance;
  if ( SettingsEnvironmentInstance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4FD,
      (int)"ds\\security\\efs\\edptask\\toast\\edptoast.cpp",
      (const char *)(unsigned int)SettingsEnvironmentInstance);
    v7 = *(_QWORD *)pcbData;
    if ( *(_QWORD *)pcbData )
    {
      *(_QWORD *)pcbData = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return (unsigned int)PolicyInt;
  }
  v8 = 0;
  if ( *(_QWORD *)pcbData
    && (*(unsigned int (__fastcall **)(_QWORD, const wchar_t *, char *))(**(_QWORD **)pcbData + 56LL))(
         *(_QWORD *)pcbData,
         L"SettingsGroupPCSystemDeviceEncryption",
         &v20) == -2147319765 )
  {
    v20 = 1;
  }
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( GetVersionExW(&VersionInformation) )
  {
    if ( VersionInformation.dwPlatformId == 2 && (v31 & 0x200) != 0 )
    {
      v8 = 1;
      if ( !v20 )
      {
        *a2 = 0;
        v9 = *(_QWORD *)pcbData;
        if ( *(_QWORD *)pcbData )
        {
          *(_QWORD *)pcbData = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        }
        return 0;
      }
    }
    else
    {
      v8 = 0;
    }
  }
  v10 = *(_QWORD *)pcbData;
  if ( *(_QWORD *)pcbData )
  {
    *(_QWORD *)pcbData = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  PolicyInt = NgscbGetOSVolume(v35);
  if ( PolicyInt < 0 )
  {
    v4 = 1322;
    goto LABEL_4;
  }
  v28[0] = 144;
  v28[1] = 10;
  PolicyInt = FveGetStatusW(v35, v28);
  if ( PolicyInt < 0 )
  {
    v4 = 1327;
    goto LABEL_4;
  }
  if ( (v29 & 0x2000) != 0 )
    goto LABEL_71;
  v11 = 0;
  if ( (v29 & 1) != 0 )
    v11 = (v29 & 0x400) == 0;
  started = BdeSvcApiStartService();
  if ( started < 0 )
  {
    v13 = 1351;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (int)"ds\\security\\efs\\edptask\\toast\\edptoast.cpp",
      (const char *)(unsigned int)started);
    return (unsigned int)started;
  }
  started = BdeSvcApiIsEncryptableFDVPresent(&v26);
  if ( started < 0 )
  {
    v13 = 1352;
    goto LABEL_34;
  }
  if ( v11 && !v26 )
    goto LABEL_71;
  v24[0] = 1;
  pvData = 0;
  PolicyInt = PolicyManager_GetPolicyInt(L"BitLocker", L"AllowWarningForOtherDiskEncryption", v24);
  if ( PolicyInt < 0 )
  {
    v4 = 1381;
    goto LABEL_4;
  }
  pvData = 0;
  PolicyInt = DsrIsDeviceJoined(&pvData, 0);
  if ( PolicyInt < 0 )
  {
    v4 = 1383;
    goto LABEL_4;
  }
  if ( pvData )
  {
    v14 = v24[0];
  }
  else
  {
    v14 = 1;
    v24[0] = 1;
  }
  if ( !v14 )
  {
    *a2 = 0;
    PolicyInt = BdeSvcApiStartService();
    if ( PolicyInt < 0 )
    {
      if ( (unsigned int)dword_18001D000 > 4
        && (qword_18001D010 & 0x400000000000LL) != 0
        && (qword_18001D018 & 0x400000000000LL) == qword_18001D018 )
      {
        pcbData[0] = PolicyInt;
        v33 = pcbData;
        v34 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_18001D000, byte_180019229, 0, 0, 3, v32);
      }
      v4 = 1408;
      goto LABEL_4;
    }
    if ( !v8 )
    {
      PolicyInt = BdeSvcApiEnableSilentBitLocker();
      if ( PolicyInt < 0 )
      {
        v4 = 1413;
        goto LABEL_4;
      }
    }
    return 0;
  }
  pcbData[0] = 0;
  PolicyInt = PolicyManager_GetPolicyInt(L"BitLocker", L"AllowStandardUserEncryption", pcbData);
  if ( PolicyInt < 0 )
  {
    v4 = 1427;
    goto LABEL_4;
  }
  if ( pcbData[0] == 1 )
  {
    v21 = 0;
    PolicyInt = BitLockerToast::IsAdminUserToken(v15, &v21);
    if ( PolicyInt < 0 )
    {
      v4 = 1438;
      goto LABEL_4;
    }
    if ( !v21 )
      goto LABEL_71;
  }
  pcbData[0] = 0;
  v24[0] = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\BitLockerCsp\\UserOptions",
             L"UserOptedOutEncryptionNotification",
             0x18u,
             0,
             pcbData,
             v24);
  v17 = ValueW < 0;
  if ( ValueW > 0 )
    v17 = 1;
  if ( !v17 && pcbData[0] == 1 )
    goto LABEL_71;
  pcbData[0] = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *(struct _FILETIME *)v24 = SystemTimeAsFileTime;
  pcbData[0] = 8;
  v18 = RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\BitLockerCsp\\UserOptions",
          L"NotificationThrottleEndTime",
          0x20000040u,
          0,
          &Data,
          pcbData);
  v19 = v18 < 0;
  if ( v18 > 0 )
    v19 = 1;
  if ( v19 || *(__int64 *)v24 >= Data )
  {
    *a2 = 1;
    Data = *(_QWORD *)&SystemTimeAsFileTime + 3000000000LL;
    RegSetKeyValueW(
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\BitLockerCsp\\UserOptions",
      L"NotificationThrottleEndTime",
      0xBu,
      &Data,
      8u);
  }
  else
  {
LABEL_71:
    *a2 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180010cb0  push    rbp
0x180010cb2  push    rbx
0x180010cb3  push    rsi
0x180010cb4  push    rdi
0x180010cb5  push    r12
0x180010cb7  push    r13
0x180010cb9  push    r14
0x180010cbb  push    r15
0x180010cbd  lea     rbp, [rsp-388h]
0x180010cc5  sub     rsp, 488h
0x180010ccc  mov     rax, cs:__security_cookie
0x180010cd3  xor     rax, rsp
0x180010cd6  mov     [rbp+3C0h+var_50], rax
0x180010cdd  mov     r14, rdx
0x180010ce0  xor     r15d, r15d
0x180010ce3  mov     [rsp+4C0h+var_480], r15b
0x180010ce8  mov     edi, 90h
0x180010ced  mov     r8d, edi; Size
0x180010cf0  xor     edx, edx; Val
0x180010cf2  lea     rcx, [rbp+3C0h+var_440]; void *
0x180010cf6  call    memset_0
0x180010cfb  xor     edx, edx; Val
0x180010cfd  mov     r8d, 208h; Size
0x180010d03  lea     rcx, [rbp+3C0h+var_260]; void *
0x180010d0a  call    memset_0
0x180010d0f  mov     [rsp+4C0h+var_458], r15d
0x180010d14  mov     qword ptr [rsp+4C0h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180010d19  mov     [rsp+4C0h+Data], r15
0x180010d1e  mov     [r14], r15b
0x180010d21  call    cs:__imp_RtlIsMultiSessionSku
0x180010d27  test    al, al
0x180010d29  jz      loc_180011241
0x180010d2f  mov     [rsp+4C0h+var_468], r15d
0x180010d34  lea     r8, [rsp+4C0h+var_468]
0x180010d39  lea     rdx, aRequiredevicee; "RequireDeviceEncryption"
0x180010d40  lea     rcx, aBitlocker; "BitLocker"
0x180010d47  call    cs:__imp_PolicyManager_GetPolicyInt
0x180010d4d  mov     ebx, eax
0x180010d4f  test    eax, eax
0x180010d51  jns     short loc_180010D75
0x180010d53  mov     edx, 4DFh; void *
0x180010d58  mov     rcx, [rbp+3C8h]; this
0x180010d5f  mov     r9d, ebx; char *
0x180010d62  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x180010d69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010d6e  mov     eax, ebx
0x180010d70  jmp     loc_180011246
0x180010d75  mov     r13d, 4
0x180010d7b  lea     r12d, [r13-3]
0x180010d7f  cmp     [rsp+4C0h+var_468], r12d
0x180010d84  jz      short loc_180010DD5
0x180010d86  mov     [rsp+4C0h+var_470], r15d
0x180010d8b  mov     [rsp+4C0h+var_478], r13d
0x180010d90  lea     rax, [rsp+4C0h+var_478]
0x180010d95  mov     [rsp+4C0h+pcbData], rax; pcbData
0x180010d9a  lea     rax, [rsp+4C0h+var_470]
0x180010d9f  mov     [rsp+4C0h+pvData], rax; pvData
0x180010da4  mov     [rsp+4C0h+pdwType], r15; int
0x180010da9  mov     r9d, 20000018h; dwFlags
0x180010daf  lea     r8, Value; "UserSecurityAreaPolicyQueried"
0x180010db6  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\BitLockerCsp\\User"...
0x180010dbd  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180010dc4  call    cs:__imp_RegGetValueW
0x180010dca  cmp     [rsp+4C0h+var_470], r12d
0x180010dcf  jnz     loc_180011241
0x180010dd5  mov     qword ptr [rsp+4C0h+var_478], r15
0x180010dda  lea     rcx, [rsp+4C0h+var_478]
0x180010ddf  call    cs:__imp_GetSettingsEnvironmentInstance
0x180010de5  mov     ebx, eax
0x180010de7  test    eax, eax
0x180010de9  jns     short loc_180010E28
0x180010deb  mov     rcx, [rbp+3C8h]; this
0x180010df2  mov     r9d, eax; char *
0x180010df5  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x180010dfc  mov     edx, 4FDh; void *
0x180010e01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010e06  nop
0x180010e07  mov     rcx, qword ptr [rsp+4C0h+var_478]
0x180010e0c  test    rcx, rcx
0x180010e0f  jz      short loc_180010E23
0x180010e11  mov     qword ptr [rsp+4C0h+var_478], r15
0x180010e16  mov     rax, [rcx]
0x180010e19  mov     rax, [rax+10h]
0x180010e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e22  nop
0x180010e23  jmp     loc_180010D6E
0x180010e28  mov     sil, r15b
0x180010e2b  mov     rcx, qword ptr [rsp+4C0h+var_478]
0x180010e30  test    rcx, rcx
0x180010e33  jz      short loc_180010E59
0x180010e35  mov     rax, [rcx]
0x180010e38  lea     r8, [rsp+4C0h+var_480]
0x180010e3d  lea     rdx, aSettingsgroupp; "SettingsGroupPCSystemDeviceEncryption"
0x180010e44  mov     rax, [rax+38h]
0x180010e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e4d  cmp     eax, 8002802Bh
0x180010e52  jnz     short loc_180010E59
0x180010e54  mov     [rsp+4C0h+var_480], r12b
0x180010e59  xor     edx, edx; Val
0x180010e5b  mov     r8d, 118h; Size
0x180010e61  lea     rcx, [rbp+3C0h+VersionInformation.dwMajorVersion]; void *
0x180010e65  call    memset_0
0x180010e6a  mov     [rbp+3C0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180010e71  lea     rcx, [rbp+3C0h+VersionInformation]; lpVersionInformation
0x180010e75  call    cs:__imp_GetVersionExW
0x180010e7b  test    eax, eax
0x180010e7d  jz      short loc_180010EC4
0x180010e7f  cmp     [rbp+3C0h+VersionInformation.dwPlatformId], 2
0x180010e83  jnz     short loc_180010EC1
0x180010e85  mov     eax, 200h
0x180010e8a  test    [rbp+3C0h+var_298], ax
0x180010e91  jz      short loc_180010EC1
0x180010e93  mov     sil, r12b
0x180010e96  cmp     [rsp+4C0h+var_480], r15b
0x180010e9b  jnz     short loc_180010EC4
0x180010e9d  mov     [r14], r15b
0x180010ea0  mov     rcx, qword ptr [rsp+4C0h+var_478]
0x180010ea5  test    rcx, rcx
0x180010ea8  jz      short loc_180010EBC
0x180010eaa  mov     qword ptr [rsp+4C0h+var_478], r15
0x180010eaf  mov     rax, [rcx]
0x180010eb2  mov     rax, [rax+10h]
0x180010eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ebb  nop
0x180010ebc  jmp     loc_180011244
0x180010ec1  mov     sil, r15b
0x180010ec4  mov     rcx, qword ptr [rsp+4C0h+var_478]
0x180010ec9  test    rcx, rcx
0x180010ecc  jz      short loc_180010EE0
0x180010ece  mov     qword ptr [rsp+4C0h+var_478], r15
0x180010ed3  mov     rax, [rcx]
0x180010ed6  mov     rax, [rax+10h]
0x180010eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010edf  nop
0x180010ee0  lea     rcx, [rbp+3C0h+var_260]
0x180010ee7  call    NgscbGetOSVolume
0x180010eec  mov     ebx, eax
0x180010eee  test    eax, eax
0x180010ef0  jns     short loc_180010EFC
0x180010ef2  mov     edx, 52Ah
0x180010ef7  jmp     loc_180010D58
0x180010efc  mov     [rbp+3C0h+var_440], edi
0x180010eff  mov     [rbp+3C0h+var_43C], 0Ah
0x180010f06  lea     rdx, [rbp+3C0h+var_440]
0x180010f0a  lea     rcx, [rbp+3C0h+var_260]
0x180010f11  call    cs:__imp_FveGetStatusW
0x180010f17  mov     ebx, eax
0x180010f19  test    eax, eax
0x180010f1b  jns     short loc_180010F27
0x180010f1d  mov     edx, 52Fh
0x180010f22  jmp     loc_180010D58
0x180010f27  mov     eax, [rbp+3C0h+var_434]
0x180010f2a  bt      eax, 0Dh
0x180010f2e  jb      loc_180011241
0x180010f34  mov     ebx, r15d
0x180010f37  test    r12b, al
0x180010f3a  jz      short loc_180010F44
0x180010f3c  bt      eax, 0Ah
0x180010f40  cmovnb  ebx, r12d
0x180010f44  call    ?BdeSvcApiStartService@@YAJXZ; BdeSvcApiStartService(void)
0x180010f49  mov     edi, eax
0x180010f4b  test    eax, eax
0x180010f4d  jns     short loc_180010F71
0x180010f4f  mov     edx, 547h; void *
0x180010f54  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x180010f5b  mov     r9d, edi; char *
0x180010f5e  mov     rcx, [rbp+3C8h]; this
0x180010f65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010f6a  mov     eax, edi
0x180010f6c  jmp     loc_180011246
0x180010f71  lea     rcx, [rsp+4C0h+var_458]; int *
0x180010f76  call    ?BdeSvcApiIsEncryptableFDVPresent@@YAJPEAH@Z; BdeSvcApiIsEncryptableFDVPresent(int *)
0x180010f7b  mov     edi, eax
0x180010f7d  test    eax, eax
0x180010f7f  jns     short loc_180010F88
0x180010f81  mov     edx, 548h
0x180010f86  jmp     short loc_180010F54
0x180010f88  test    ebx, ebx
0x180010f8a  jz      short loc_180010F97
0x180010f8c  cmp     [rsp+4C0h+var_458], r15d
0x180010f91  jz      loc_180011241
0x180010f97  mov     [rsp+4C0h+var_468], r12d
0x180010f9c  mov     [rsp+4C0h+var_470], r15d
0x180010fa1  lea     r8, [rsp+4C0h+var_468]
0x180010fa6  lea     rdx, aAllowwarningfo; "AllowWarningForOtherDiskEncryption"
0x180010fad  lea     rcx, aBitlocker; "BitLocker"
0x180010fb4  call    cs:__imp_PolicyManager_GetPolicyInt
0x180010fba  mov     ebx, eax
0x180010fbc  test    eax, eax
0x180010fbe  jns     short loc_180010FCA
0x180010fc0  mov     edx, 565h
0x180010fc5  jmp     loc_180010D58
0x180010fca  mov     [rsp+4C0h+var_470], r15d
0x180010fcf  xor     edx, edx
0x180010fd1  lea     rcx, [rsp+4C0h+var_470]
0x180010fd6  call    cs:__imp_DsrIsDeviceJoined
0x180010fdc  mov     ebx, eax
0x180010fde  test    eax, eax
0x180010fe0  jns     short loc_180010FEC
0x180010fe2  mov     edx, 567h
0x180010fe7  jmp     loc_180010D58
0x180010fec  cmp     [rsp+4C0h+var_470], r15d
0x180010ff1  jnz     short loc_180010FFC
0x180010ff3  mov     eax, r12d
0x180010ff6  mov     [rsp+4C0h+var_468], eax
0x180010ffa  jmp     short loc_180011000
0x180010ffc  mov     eax, [rsp+4C0h+var_468]
0x180011000  test    eax, eax
0x180011002  jnz     loc_1800110C1
0x180011008  mov     [r14], r15b
0x18001100b  call    ?BdeSvcApiStartService@@YAJXZ; BdeSvcApiStartService(void)
0x180011010  mov     ebx, eax
0x180011012  test    eax, eax
0x180011014  jns     loc_18001109F
0x18001101a  mov     ecx, cs:dword_18001D000
0x180011020  cmp     ecx, r13d
0x180011023  jbe     short loc_180011095
0x180011025  mov     rdx, cs:qword_18001D018
0x18001102c  mov     rcx, cs:qword_18001D010
0x180011033  mov     r8, 400000000000h
0x18001103d  test    r8, rcx
0x180011040  jz      short loc_180011095
0x180011042  mov     rax, rdx
0x180011045  and     rax, r8
0x180011048  cmp     rax, rdx
0x18001104b  jnz     short loc_180011095
0x18001104d  mov     [rsp+4C0h+var_478], ebx
0x180011051  lea     rax, [rsp+4C0h+var_478]
0x180011056  mov     [rbp+3C0h+var_270], rax
0x18001105d  mov     [rbp+3C0h+var_268], 4
0x180011068  lea     rax, [rbp+3C0h+var_290]
0x18001106f  mov     [rsp+4C0h+pvData], rax
0x180011074  mov     dword ptr [rsp+4C0h+pdwType], 3
0x18001107c  xor     r9d, r9d
0x18001107f  xor     r8d, r8d
0x180011082  lea     rdx, byte_180019229
0x180011089  lea     rcx, dword_18001D000
0x180011090  call    _tlgWriteTransfer_EventWriteTransfer
0x180011095  mov     edx, 580h
0x18001109a  jmp     loc_180010D58
0x18001109f  test    sil, sil
0x1800110a2  jnz     loc_180011244
0x1800110a8  call    ?BdeSvcApiEnableSilentBitLocker@@YAJXZ; BdeSvcApiEnableSilentBitLocker(void)
0x1800110ad  mov     ebx, eax
0x1800110af  test    eax, eax
0x1800110b1  jns     loc_180011244
0x1800110b7  mov     edx, 585h
0x1800110bc  jmp     loc_180010D58
0x1800110c1  mov     [rsp+4C0h+var_478], r15d
0x1800110c6  lea     r8, [rsp+4C0h+var_478]
0x1800110cb  lea     rdx, aAllowstandardu; "AllowStandardUserEncryption"
0x1800110d2  lea     rcx, aBitlocker; "BitLocker"
0x1800110d9  call    cs:__imp_PolicyManager_GetPolicyInt
0x1800110df  mov     ebx, eax
0x1800110e1  test    eax, eax
0x1800110e3  jns     short loc_1800110EF
0x1800110e5  mov     edx, 593h
0x1800110ea  jmp     loc_180010D58
0x1800110ef  cmp     [rsp+4C0h+var_478], r12d
0x1800110f4  jnz     short loc_180011120
0x1800110f6  mov     [rsp+4C0h+var_47F], r15b
0x1800110fb  lea     rdx, [rsp+4C0h+var_47F]; bool *
0x180011100  call    ?IsAdminUserToken@BitLockerToast@@QEAAJPEA_N@Z; BitLockerToast::IsAdminUserToken(bool *)
0x180011105  mov     ebx, eax
0x180011107  test    eax, eax
0x180011109  jns     short loc_180011115
0x18001110b  mov     edx, 59Eh
0x180011110  jmp     loc_180010D58
0x180011115  cmp     [rsp+4C0h+var_47F], r15b
0x18001111a  jz      loc_180011241
0x180011120  mov     [rsp+4C0h+var_478], r15d
0x180011125  mov     [rsp+4C0h+var_468], r13d
0x18001112a  lea     rax, [rsp+4C0h+var_468]
0x18001112f  mov     [rsp+4C0h+pcbData], rax; pcbData
0x180011134  lea     rax, [rsp+4C0h+var_478]
0x180011139  mov     [rsp+4C0h+pvData], rax; pvData
0x18001113e  mov     [rsp+4C0h+pdwType], r15; pdwType
0x180011143  mov     r9d, 18h; dwFlags
0x180011149  lea     r8, aUseroptedouten; "UserOptedOutEncryptionNotification"
0x180011150  lea     rsi, aSoftwareMicros; "Software\\Microsoft\\BitLockerCsp\\User"...
0x180011157  mov     rdx, rsi; lpSubKey
0x18001115a  mov     r13, 0FFFFFFFF80000002h
0x180011161  mov     rcx, r13; hkey
0x180011164  call    cs:__imp_RegGetValueW
0x18001116a  mov     ebx, 80070000h
0x18001116f  test    eax, eax
0x180011171  jle     short loc_18001117A
0x180011173  movzx   eax, ax
0x180011176  or      eax, ebx
0x180011178  test    eax, eax
0x18001117a  js      short loc_180011187
0x18001117c  cmp     [rsp+4C0h+var_478], r12d
0x180011181  jz      loc_180011241
0x180011187  mov     [rsp+4C0h+var_478], r15d
0x18001118c  lea     rcx, [rsp+4C0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180011191  call    cs:__imp_GetSystemTimeAsFileTime
0x180011197  mov     eax, [rsp+4C0h+SystemTimeAsFileTime.dwHighDateTime]
0x18001119b  mov     [rsp+4C0h+var_468+4], eax
0x18001119f  mov     eax, [rsp+4C0h+SystemTimeAsFileTime.dwLowDateTime]
0x1800111a3  mov     [rsp+4C0h+var_468], eax
  ... truncated ...
```
