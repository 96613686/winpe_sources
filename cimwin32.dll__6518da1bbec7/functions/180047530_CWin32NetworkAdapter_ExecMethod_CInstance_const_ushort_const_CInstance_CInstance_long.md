# CWin32NetworkAdapter::ExecMethod(CInstance const &,ushort * const,CInstance *,CInstance *,long)

- ea: `0x180047530`
- end: `0x180047a8a`
- name: `?ExecMethod@CWin32NetworkAdapter@@UEAAJAEBVCInstance@@QEAGPEAV2@2J@Z`
- size: `1370`
- prototype: `int(CWin32NetworkAdapter *__hidden this, const struct CInstance *, unsigned __int16 *const, struct CInstance *, struct CInstance *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180020e5c`
- `0x180036950`
- `0x180047530`
- `0x18008c2e4`
- `0x1800fc902`
- `0x1800fc980`
- `0x180110010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18004760d`
- `msvcrt!_wcsicmp` at `0x180047666`
- `msvcrt!_wcsicmp` at `0x18004760d`
- `msvcrt!_wcsicmp` at `0x180047666`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004770f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047749`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800477b2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800477fe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047749`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800477b2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800477fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004763b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800479b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800479d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004763b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800479b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800479d2`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800475c2`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800475c2`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800475f5`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800475f5`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x180047761`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x180047761`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180047593`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180047a24`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180047593`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180047a24`
- `framedynos!?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z` at `0x1800475d8`
- `framedynos!?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z` at `0x1800475d8`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800479f7`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180047a46`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180047a55`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800479f7`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180047a46`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180047a55`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiGetClassDevsW` at `0x18004762c`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiGetClassDevsW` at `0x18004762c`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiEnumDeviceInfo` at `0x1800476c0`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiEnumDeviceInfo` at `0x1800476c0`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiCallClassInstaller` at `0x18004796d`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiCallClassInstaller` at `0x1800479ad`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiCallClassInstaller` at `0x18004796d`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiCallClassInstaller` at `0x1800479ad`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiDestroyDeviceInfoList` at `0x18004767d`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiSetClassInstallParamsW` at `0x18004795a`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiSetClassInstallParamsW` at `0x18004799a`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiSetClassInstallParamsW` at `0x18004795a`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiSetClassInstallParamsW` at `0x18004799a`
- `ext-ms-win-setupapi-classinstallers-l1-1-2!SetupDiOpenDevRegKey` at `0x1800476f9`
- `ext-ms-win-setupapi-classinstallers-l1-1-2!SetupDiOpenDevRegKey` at `0x1800476f9`
- `NSI!NsiGetAllParametersEx` at `0x1800478e8`
- `NSI!NsiGetAllParametersEx` at `0x1800478e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWin32NetworkAdapter::ExecMethod(
        CWin32NetworkAdapter *this,
        const struct CInstance *a2,
        unsigned __int16 *const a3,
        struct CInstance *a4,
        struct CInstance *a5)
{
  __int64 result; // rax
  signed int v9; // edi
  char v10; // r12
  HDEVINFO ClassDevsW; // rax
  void *v12; // rsi
  signed int LastError; // eax
  unsigned int v14; // ebx
  DWORD i; // r15d
  HKEY v16; // rax
  HKEY v17; // r14
  LSTATUS v18; // eax
  bool v19; // cc
  LSTATUS v20; // eax
  signed int AllParameters; // eax
  bool v22; // cc
  int v23; // eax
  signed int v24; // eax
  unsigned int v25; // r8d
  bool v26; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  DWORD v28; // [rsp+38h] [rbp-C8h] BYREF
  BYTE v29[4]; // [rsp+3Ch] [rbp-C4h] BYREF
  BYTE v30[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v31[8]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v33[8]; // [rsp+58h] [rbp-A8h] BYREF
  void (__fastcall *v34)(__int64); // [rsp+60h] [rbp-A0h]
  __int64 v35; // [rsp+68h] [rbp-98h]
  _BYTE v36[8]; // [rsp+70h] [rbp-90h] BYREF
  void (__fastcall *v37)(__int64); // [rsp+78h] [rbp-88h]
  __int64 v38; // [rsp+80h] [rbp-80h]
  unsigned __int64 v39; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v40[16]; // [rsp+A0h] [rbp-60h] BYREF
  const NPI_MODULEID *v41; // [rsp+B0h] [rbp-50h]
  int v42; // [rsp+B8h] [rbp-48h]
  __int64 v43; // [rsp+C0h] [rbp-40h]
  unsigned __int64 *v44; // [rsp+C8h] [rbp-38h]
  int v45; // [rsp+D0h] [rbp-30h]
  __int64 v46; // [rsp+D8h] [rbp-28h]
  int v47; // [rsp+E0h] [rbp-20h]
  _DWORD *v48; // [rsp+E8h] [rbp-18h]
  int v49; // [rsp+F0h] [rbp-10h]
  __int64 v50; // [rsp+F8h] [rbp-8h]
  int v51; // [rsp+100h] [rbp+0h]
  _SP_CLASSINSTALL_HEADER ClassInstallParams; // [rsp+110h] [rbp+10h] BYREF
  int v53; // [rsp+118h] [rbp+18h]
  __int64 v54; // [rsp+11Ch] [rbp+1Ch]
  _SP_DEVINFO_DATA DeviceInfoData; // [rsp+128h] [rbp+28h] BYREF
  _DWORD v56[56]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 Data[264]; // [rsp+230h] [rbp+130h] BYREF

  if ( !(unsigned __int8)IsSetupDiGetClassDevsWPresent(this, a2, a3, a4) )
    return 2147749973LL;
  CInstance::SetDWORD(a5, L"ReturnValue", 0);
  result = (*(__int64 (__fastcall **)(CWin32NetworkAdapter *, const struct CInstance *, _QWORD))(*(_QWORD *)this + 56LL))(
             this,
             a2,
             0);
  v9 = result;
  if ( (int)result >= 0 )
  {
    v26 = 0;
    CHString::CHString((CHString *)v31);
    if ( !CInstance::Getbool(a2, L"NetEnabled", &v26) || !CInstance::GetCHString(a2, L"GUID", (struct CHString *)v31) )
    {
      CHString::~CHString((CHString *)v31);
      return 2147749935LL;
    }
    if ( _wcsicmp(a3, L"Enable") )
    {
      v10 = 0;
      if ( _wcsicmp(a3, L"Disable") )
      {
        v14 = -2147217362;
        goto LABEL_54;
      }
    }
    else
    {
      v10 = 1;
    }
    ClassDevsW = SetupDiGetClassDevsW(&GUID_DEVCLASS_NET, 0, 0, 2u);
    v12 = ClassDevsW;
    if ( ClassDevsW == (HDEVINFO)-1LL )
    {
      LastError = GetLastError();
      v14 = LastError;
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_54;
    }
    MakeGuard<void (*)(void *),void *>(v36, SetupDiDestroyDeviceInfoList, ClassDevsW);
    memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
    DeviceInfoData.cbSize = 32;
    *(_DWORD *)v30 = 0;
    *(_DWORD *)v29 = 0;
    cbData = 260;
    for ( i = 0; ; ++i )
    {
      if ( !SetupDiEnumDeviceInfo(v12, i, &DeviceInfoData) )
      {
        v9 = -2147217406;
        goto LABEL_56;
      }
      Type = 0;
      v28 = 4;
      v16 = SetupDiOpenDevRegKey(v12, &DeviceInfoData, 1u, 0, 2u, 0x20019u);
      v17 = v16;
      if ( v16 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
        break;
      MakeGuard<void (*)(void *),void *>(v33, RegCloseKey, v16);
      v18 = RegQueryValueExW(v17, L"NetCfgInstanceId", 0, &Type, (LPBYTE)Data, &cbData);
      v14 = v18;
      v19 = v18 <= 0;
      if ( v18 )
        goto LABEL_22;
      if ( !CHString::CompareNoCase((CHString *)v31, Data) )
      {
        v18 = RegQueryValueExW(v17, L"NetLuidIndex", 0, &Type, v30, &v28);
        v14 = v18;
        v19 = v18 <= 0;
        if ( v18 )
        {
LABEL_22:
          if ( !v19 )
            v14 = (unsigned __int16)v18 | 0x80070000;
          ScopeGuardImpl1<long (*)(void *),_SECURITY_LOGON_SESSION_DATA *>::~ScopeGuardImpl1<long (*)(void *),_SECURITY_LOGON_SESSION_DATA *>((__int64)v33);
LABEL_53:
          ScopeGuardImpl1<long (*)(void *),_SECURITY_LOGON_SESSION_DATA *>::~ScopeGuardImpl1<long (*)(void *),_SECURITY_LOGON_SESSION_DATA *>((__int64)v36);
          goto LABEL_54;
        }
        v20 = RegQueryValueExW(v17, L"*IfType", 0, &Type, v29, &v28);
        v14 = v20;
        if ( v20 )
        {
          if ( v20 > 0 )
            v14 = (unsigned __int16)v20 | 0x80070000;
          if ( !v33[0] )
            v34(v35);
          if ( !v36[0] )
            v37(v38);
LABEL_54:
          CHString::~CHString((CHString *)v31);
          return v14;
        }
        if ( !v33[0] )
          v34(v35);
        v39 = (*(_DWORD *)v30 & 0xFFFFFF | ((unsigned __int64)*(unsigned int *)v29 << 24)) << 24;
        memset_0(v56, 0, 0xD8u);
        memset_0(v40, 0, 0x68u);
        v41 = &NPI_MS_NDIS_MODULEID;
        v42 = 0;
        v44 = &v39;
        v45 = 8;
        v46 = 0;
        v47 = 0;
        v48 = v56;
        v49 = 216;
        v50 = 0;
        v51 = 0;
        v43 = 1;
        AllParameters = NsiGetAllParametersEx(v40);
        v14 = AllParameters;
        v22 = AllParameters <= 0;
        if ( !AllParameters )
        {
          if ( v10 )
          {
            if ( v56[0] != 1 )
            {
              ClassInstallParams.cbSize = 8;
              ClassInstallParams.InstallFunction = 18;
              v53 = 1;
              v54 = 1;
              if ( SetupDiSetClassInstallParamsW(v12, &DeviceInfoData, &ClassInstallParams, 0x14u) )
                SetupDiCallClassInstaller(0x12u, v12, &DeviceInfoData);
              v53 = 1;
              v54 = 2;
LABEL_44:
              ClassInstallParams.cbSize = 8;
              ClassInstallParams.InstallFunction = 18;
              if ( !SetupDiSetClassInstallParamsW(v12, &DeviceInfoData, &ClassInstallParams, 0x14u)
                || !SetupDiCallClassInstaller(0x12u, v12, &DeviceInfoData) )
              {
                v24 = GetLastError();
                v9 = v24;
                if ( v24 > 0 )
                  v9 = (unsigned __int16)v24 | 0x80070000;
              }
            }
          }
          else if ( (unsigned int)(v56[0] - 3) > 1 )
          {
            v23 = AllParameters + 2;
            if ( v56[0] != v23 || v56[2] == v23 )
            {
              v53 = v14 + 2;
              v54 = v14 + 2;
              goto LABEL_44;
            }
          }
          if ( v9 >= 0 )
          {
LABEL_59:
            if ( !v36[0] )
              v37(v38);
            CHString::~CHString((CHString *)v31);
            return 0;
          }
LABEL_56:
          v25 = (unsigned __int16)v9;
          if ( (v9 & 0x1FFF0000) != 0x70000 )
            v25 = v9;
          CInstance::SetDWORD(a5, L"ReturnValue", v25);
          goto LABEL_59;
        }
LABEL_51:
        if ( !v22 )
          v14 = (unsigned __int16)AllParameters | 0x80070000;
        goto LABEL_53;
      }
      if ( !v33[0] )
        v34(v35);
    }
    AllParameters = GetLastError();
    v14 = AllParameters;
    v22 = AllParameters <= 0;
    goto LABEL_51;
  }
  return result;
}

```

## disassembly

```asm
0x180047530  mov     [rsp-8+arg_18], rbx
0x180047535  push    rbp
0x180047536  push    rsi
0x180047537  push    rdi
0x180047538  push    r12
0x18004753a  push    r13
0x18004753c  push    r14
0x18004753e  push    r15
0x180047540  lea     rbp, [rsp-350h]
0x180047548  sub     rsp, 450h
0x18004754f  mov     rax, cs:__security_cookie
0x180047556  xor     rax, rsp
0x180047559  mov     [rbp+380h+var_40], rax
0x180047560  mov     rsi, r8
0x180047563  mov     rbx, rdx
0x180047566  mov     rdi, rcx
0x180047569  mov     r13, [rbp+380h+arg_20]
0x180047570  xor     r14d, r14d
0x180047573  call    IsSetupDiGetClassDevsWPresent
0x180047578  test    al, al
0x18004757a  jnz     short loc_180047586
0x18004757c  mov     eax, 80041055h
0x180047581  jmp     loc_180047A60
0x180047586  xor     r8d, r8d
0x180047589  lea     rdx, aReturnvalue; "ReturnValue"
0x180047590  mov     rcx, r13
0x180047593  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180047599  mov     rax, [rdi]
0x18004759c  xor     r8d, r8d
0x18004759f  mov     rdx, rbx
0x1800475a2  mov     rcx, rdi
0x1800475a5  mov     rax, [rax+38h]
0x1800475a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800475ae  mov     edi, eax
0x1800475b0  test    eax, eax
0x1800475b2  js      loc_180047A60
0x1800475b8  mov     [rsp+480h+var_450], r14b
0x1800475bd  lea     rcx, [rsp+480h+var_438]
0x1800475c2  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800475c8  nop
0x1800475c9  lea     r8, [rsp+480h+var_450]
0x1800475ce  lea     rdx, aNetenabled; "NetEnabled"
0x1800475d5  mov     rcx, rbx
0x1800475d8  call    cs:__imp_?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z; CInstance::Getbool(ushort const *,bool &)
0x1800475de  test    al, al
0x1800475e0  jz      loc_180047A50
0x1800475e6  lea     r8, [rsp+480h+var_438]
0x1800475eb  lea     rdx, aGuid; "GUID"
0x1800475f2  mov     rcx, rbx
0x1800475f5  call    cs:__imp_?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z; CInstance::GetCHString(ushort const *,CHString &)
0x1800475fb  test    al, al
0x1800475fd  jz      loc_180047A50
0x180047603  lea     rdx, aEnable; "Enable"
0x18004760a  mov     rcx, rsi; String1
0x18004760d  call    cs:__imp__wcsicmp
0x180047613  test    eax, eax
0x180047615  jnz     short loc_180047659
0x180047617  mov     r12b, 1
0x18004761a  mov     r9d, 2; Flags
0x180047620  xor     r8d, r8d; hwndParent
0x180047623  xor     edx, edx; Enumerator
0x180047625  lea     rcx, GUID_DEVCLASS_NET; ClassGuid
0x18004762c  call    cs:__imp_SetupDiGetClassDevsW
0x180047632  mov     rsi, rax
0x180047635  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180047639  jnz     short loc_18004767A
0x18004763b  call    cs:__imp_GetLastError
0x180047641  mov     ebx, eax
0x180047643  test    eax, eax
0x180047645  jle     loc_1800479F2
0x18004764b  movzx   ebx, ax
0x18004764e  or      ebx, 80070000h
0x180047654  jmp     loc_1800479F2
0x180047659  mov     r12b, r14b
0x18004765c  lea     rdx, aDisable_0; "Disable"
0x180047663  mov     rcx, rsi; String1
0x180047666  call    cs:__imp__wcsicmp
0x18004766c  test    eax, eax
0x18004766e  jz      short loc_18004761A
0x180047670  mov     ebx, 8004102Eh
0x180047675  jmp     loc_1800479F2
0x18004767a  mov     r8, rsi
0x18004767d  mov     rdx, cs:__imp_SetupDiDestroyDeviceInfoList
0x180047684  lea     rcx, [rsp+480h+var_410]
0x180047689  call    ??$MakeGuard@P6AXPEAX@ZPEAX@@YA?AV?$ScopeGuardImpl1@P6AXPEAX@ZPEAX@@P6AXPEAX@Z0@Z; MakeGuard<void (*)(void *),void *>(void (*)(void *),void *)
0x18004768e  nop
0x18004768f  xorps   xmm0, xmm0
0x180047692  movups  xmmword ptr [rbp+380h+DeviceInfoData.cbSize], xmm0
0x180047696  movups  xmmword ptr [rbp+380h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x18004769a  mov     [rbp+380h+DeviceInfoData.cbSize], 20h ; ' '
0x1800476a1  mov     dword ptr [rsp+480h+var_440], r14d
0x1800476a6  mov     dword ptr [rsp+480h+var_444], r14d
0x1800476ab  mov     [rsp+480h+cbData], 104h
0x1800476b3  mov     r15d, r14d
0x1800476b6  lea     r8, [rbp+380h+DeviceInfoData]; DeviceInfoData
0x1800476ba  mov     edx, r15d; MemberIndex
0x1800476bd  mov     rcx, rsi; DeviceInfoSet
0x1800476c0  call    cs:__imp_SetupDiEnumDeviceInfo
0x1800476c6  test    eax, eax
0x1800476c8  jz      loc_180047A01
0x1800476ce  mov     [rsp+480h+Type], r14d
0x1800476d3  mov     [rsp+480h+var_448], 4
0x1800476db  mov     [rsp+480h+samDesired], 20019h; samDesired
0x1800476e3  mov     [rsp+480h+KeyType], 2; KeyType
0x1800476eb  xor     r9d, r9d; HwProfile
0x1800476ee  lea     r8d, [r9+1]; Scope
0x1800476f2  lea     rdx, [rbp+380h+DeviceInfoData]; DeviceInfoData
0x1800476f6  mov     rcx, rsi; DeviceInfoSet
0x1800476f9  call    cs:__imp_SetupDiOpenDevRegKey
0x1800476ff  mov     r14, rax
0x180047702  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180047706  jz      loc_1800479D2
0x18004770c  mov     r8, rax
0x18004770f  mov     rdx, cs:__imp_RegCloseKey
0x180047716  lea     rcx, [rsp+480h+var_428]
0x18004771b  call    ??$MakeGuard@P6AXPEAX@ZPEAX@@YA?AV?$ScopeGuardImpl1@P6AXPEAX@ZPEAX@@P6AXPEAX@Z0@Z; MakeGuard<void (*)(void *),void *>(void (*)(void *),void *)
0x180047720  nop
0x180047721  lea     rax, [rsp+480h+cbData]
0x180047726  mov     qword ptr [rsp+480h+samDesired], rax; lpcbData
0x18004772b  lea     rax, [rbp+380h+Data]
0x180047732  mov     qword ptr [rsp+480h+KeyType], rax; lpData
0x180047737  lea     r9, [rsp+480h+Type]; lpType
0x18004773c  xor     r8d, r8d; lpReserved
0x18004773f  lea     rdx, aNetcfginstance; "NetCfgInstanceId"
0x180047746  mov     rcx, r14; hKey
0x180047749  call    cs:__imp_RegQueryValueExW
0x18004774f  mov     ebx, eax
0x180047751  test    eax, eax
0x180047753  jnz     short loc_1800477BE
0x180047755  lea     rdx, [rbp+380h+Data]
0x18004775c  lea     rcx, [rsp+480h+var_438]
0x180047761  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x180047767  test    eax, eax
0x180047769  jz      short loc_18004778C
0x18004776b  xor     r14d, r14d
0x18004776e  cmp     [rsp+480h+var_428], r14b
0x180047773  jnz     short loc_180047784
0x180047775  mov     rcx, [rsp+480h+var_418]
0x18004777a  mov     rax, [rsp+480h+var_420]
0x18004777f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047784  inc     r15d
0x180047787  jmp     loc_1800476B6
0x18004778c  lea     rax, [rsp+480h+var_448]
0x180047791  mov     qword ptr [rsp+480h+samDesired], rax; lpcbData
0x180047796  lea     rax, [rsp+480h+var_440]
0x18004779b  mov     qword ptr [rsp+480h+KeyType], rax; lpData
0x1800477a0  lea     r9, [rsp+480h+Type]; lpType
0x1800477a5  xor     r8d, r8d; lpReserved
0x1800477a8  lea     rdx, aNetluidindex; "NetLuidIndex"
0x1800477af  mov     rcx, r14; hKey
0x1800477b2  call    cs:__imp_RegQueryValueExW
0x1800477b8  mov     ebx, eax
0x1800477ba  test    eax, eax
0x1800477bc  jz      short loc_1800477D8
0x1800477be  jle     short loc_1800477C9
0x1800477c0  movzx   ebx, ax
0x1800477c3  or      ebx, 80070000h
0x1800477c9  lea     rcx, [rsp+480h+var_428]
0x1800477ce  call    ??1?$ScopeGuardImpl1@P6AJPEAX@ZPEAU_SECURITY_LOGON_SESSION_DATA@@@@QEAA@XZ; ScopeGuardImpl1<long (*)(void *),_SECURITY_LOGON_SESSION_DATA *>::~ScopeGuardImpl1<long (*)(void *),_SECURITY_LOGON_SESSION_DATA *>(void)
0x1800477d3  jmp     loc_1800479E7
0x1800477d8  lea     rax, [rsp+480h+var_448]
0x1800477dd  mov     qword ptr [rsp+480h+samDesired], rax; lpcbData
0x1800477e2  lea     rax, [rsp+480h+var_444]
0x1800477e7  mov     qword ptr [rsp+480h+KeyType], rax; lpData
0x1800477ec  lea     r9, [rsp+480h+Type]; lpType
0x1800477f1  xor     r8d, r8d; lpReserved
0x1800477f4  lea     rdx, ValueName; "*IfType"
0x1800477fb  mov     rcx, r14; hKey
0x1800477fe  call    cs:__imp_RegQueryValueExW
0x180047804  mov     ebx, eax
0x180047806  xor     r14d, r14d
0x180047809  test    eax, eax
0x18004780b  jz      short loc_18004784D
0x18004780d  jle     short loc_180047818
0x18004780f  movzx   ebx, ax
0x180047812  or      ebx, 80070000h
0x180047818  cmp     [rsp+480h+var_428], r14b
0x18004781d  jnz     short loc_18004782F
0x18004781f  mov     rcx, [rsp+480h+var_418]
0x180047824  mov     rax, [rsp+480h+var_420]
0x180047829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004782e  nop
0x18004782f  cmp     [rsp+480h+var_410], r14b
0x180047834  jnz     loc_1800479F2
0x18004783a  mov     rcx, [rbp+380h+var_400]
0x18004783e  mov     rax, [rsp+480h+var_408]
0x180047843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047848  jmp     loc_1800479F2
0x18004784d  cmp     [rsp+480h+var_428], r14b
0x180047852  jnz     short loc_180047863
0x180047854  mov     rcx, [rsp+480h+var_418]
0x180047859  mov     rax, [rsp+480h+var_420]
0x18004785e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047863  mov     ecx, dword ptr [rsp+480h+var_444]
0x180047867  shl     rcx, 18h
0x18004786b  mov     eax, dword ptr [rsp+480h+var_440]
0x18004786f  and     eax, 0FFFFFFh
0x180047874  or      rcx, rax
0x180047877  shl     rcx, 18h
0x18004787b  mov     [rbp+380h+var_3F0], rcx
0x18004787f  mov     ebx, 0D8h
0x180047884  mov     r8d, ebx; Size
0x180047887  xor     edx, edx; Val
0x180047889  lea     rcx, [rbp+380h+var_330]; void *
0x18004788d  call    memset_0
0x180047892  xor     edx, edx; Val
0x180047894  lea     r8d, [rbx-70h]; Size
0x180047898  lea     rcx, [rbp+380h+var_3E0]; void *
0x18004789c  call    memset_0
0x1800478a1  lea     rax, NPI_MS_NDIS_MODULEID
0x1800478a8  mov     [rbp+380h+var_3D0], rax
0x1800478ac  mov     [rbp+380h+var_3C8], r14d
0x1800478b0  lea     rax, [rbp+380h+var_3F0]
0x1800478b4  mov     [rbp+380h+var_3B8], rax
0x1800478b8  mov     [rbp+380h+var_3B0], 8
0x1800478bf  mov     [rbp+380h+var_3A8], r14
0x1800478c3  mov     [rbp+380h+var_3A0], r14d
0x1800478c7  lea     rax, [rbp+380h+var_330]
0x1800478cb  mov     [rbp+380h+var_398], rax
0x1800478cf  mov     [rbp+380h+var_390], ebx
0x1800478d2  mov     [rbp+380h+var_388], r14
0x1800478d6  mov     [rbp+380h+var_380], r14d
0x1800478da  mov     r15d, 1
0x1800478e0  mov     [rbp+380h+var_3C0], r15
0x1800478e4  lea     rcx, [rbp+380h+var_3E0]
0x1800478e8  call    cs:__imp_NsiGetAllParametersEx
0x1800478ee  mov     ebx, eax
0x1800478f0  test    eax, eax
0x1800478f2  jnz     loc_1800479DC
0x1800478f8  test    r12b, r12b
0x1800478fb  jnz     short loc_18004792A
0x1800478fd  mov     ecx, [rbp+380h+var_330]
0x180047900  lea     eax, [rcx-3]
0x180047903  cmp     eax, r15d
0x180047906  jbe     loc_1800479CC
0x18004790c  lea     eax, [rbx+2]
0x18004790f  cmp     ecx, eax
0x180047911  jnz     short loc_18004791C
0x180047913  cmp     [rbp+380h+var_328], eax
0x180047916  jnz     loc_1800479CC
0x18004791c  mov     ebx, 12h
0x180047921  mov     [rbp+380h+var_368], eax
0x180047924  mov     [rbp+380h+var_364], rax
0x180047928  jmp     short loc_18004797F
0x18004792a  cmp     [rbp+380h+var_330], r15d
0x18004792e  jz      loc_1800479CC
0x180047934  mov     [rbp+380h+ClassInstallParams.cbSize], 8
0x18004793b  mov     ebx, 12h
0x180047940  mov     [rbp+380h+ClassInstallParams.InstallFunction], ebx
0x180047943  mov     [rbp+380h+var_368], r15d
0x180047947  mov     [rbp+380h+var_364], r15
0x18004794b  lea     r9d, [rbx+2]; ClassInstallParamsSize
0x18004794f  lea     r8, [rbp+380h+ClassInstallParams]; ClassInstallParams
0x180047953  lea     rdx, [rbp+380h+DeviceInfoData]; DeviceInfoData
0x180047957  mov     rcx, rsi; DeviceInfoSet
0x18004795a  call    cs:__imp_SetupDiSetClassInstallParamsW
0x180047960  test    eax, eax
0x180047962  jz      short loc_180047973
0x180047964  lea     r8, [rbp+380h+DeviceInfoData]; DeviceInfoData
0x180047968  mov     rdx, rsi; DeviceInfoSet
0x18004796b  mov     ecx, ebx; InstallFunction
0x18004796d  call    cs:__imp_SetupDiCallClassInstaller
0x180047973  mov     [rbp+380h+var_368], r15d
0x180047977  mov     [rbp+380h+var_364], 2
0x18004797f  mov     [rbp+380h+ClassInstallParams.cbSize], 8
0x180047986  mov     [rbp+380h+ClassInstallParams.InstallFunction], ebx
0x180047989  mov     r9d, 14h; ClassInstallParamsSize
0x18004798f  lea     r8, [rbp+380h+ClassInstallParams]; ClassInstallParams
0x180047993  lea     rdx, [rbp+380h+DeviceInfoData]; DeviceInfoData
0x180047997  mov     rcx, rsi; DeviceInfoSet
0x18004799a  call    cs:__imp_SetupDiSetClassInstallParamsW
0x1800479a0  test    eax, eax
0x1800479a2  jz      short loc_1800479B7
0x1800479a4  lea     r8, [rbp+380h+DeviceInfoData]; DeviceInfoData
0x1800479a8  mov     rdx, rsi; DeviceInfoSet
0x1800479ab  mov     ecx, ebx; InstallFunction
0x1800479ad  call    cs:__imp_SetupDiCallClassInstaller
0x1800479b3  test    eax, eax
0x1800479b5  jnz     short loc_1800479CC
0x1800479b7  call    cs:__imp_GetLastError
0x1800479bd  test    eax, eax
0x1800479bf  mov     edi, eax
0x1800479c1  jle     short loc_1800479CC
0x1800479c3  movzx   edi, ax
0x1800479c6  or      edi, 80070000h
0x1800479cc  test    edi, edi
0x1800479ce  js      short loc_180047A06
0x1800479d0  jmp     short loc_180047A2B
0x1800479d2  call    cs:__imp_GetLastError
0x1800479d8  mov     ebx, eax
0x1800479da  test    eax, eax
0x1800479dc  jle     short loc_1800479E7
0x1800479de  movzx   ebx, ax
0x1800479e1  or      ebx, 80070000h
0x1800479e7  lea     rcx, [rsp+480h+var_410]
0x1800479ec  call    ??1?$ScopeGuardImpl1@P6AJPEAX@ZPEAU_SECURITY_LOGON_SESSION_DATA@@@@QEAA@XZ; ScopeGuardImpl1<long (*)(void *),_SECURITY_LOGON_SESSION_DATA *>::~ScopeGuardImpl1<long (*)(void *),_SECURITY_LOGON_SESSION_DATA *>(void)
0x1800479f1  nop
0x1800479f2  lea     rcx, [rsp+480h+var_438]
0x1800479f7  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800479fd  mov     eax, ebx
  ... truncated ...
```
