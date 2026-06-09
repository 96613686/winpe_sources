# ClassInstall_SelectBestCompatDrv(void *,_SP_DEVINFO_DATA *,_SP_DEVINSTALL_PARAMS_W *)

- ea: `0x1800145fc`
- end: `0x1800148b6`
- name: `?ClassInstall_SelectBestCompatDrv@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z`
- size: `698`
- prototype: `unsigned int __fastcall(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData, struct _SP_DEVINSTALL_PARAMS_W *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013260`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000d57c`
- `0x18000d624`
- `0x1800145fc`
- `0x1800162c8`
- `0x18001bc44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800146f1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014707`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800146f1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001481e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001481e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001477a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001477a`
- `KERNEL32!lstrcmpiW` at `0x180014739`
- `KERNEL32!lstrcmpiW` at `0x180014739`
- `SETUPAPI!SetupDiGetDriverInstallParamsW` at `0x180014691`
- `SETUPAPI!SetupDiGetDriverInstallParamsW` at `0x1800147ba`
- `SETUPAPI!SetupDiGetDriverInstallParamsW` at `0x180014691`
- `SETUPAPI!SetupDiGetDriverInstallParamsW` at `0x1800147ba`
- `SETUPAPI!SetupDiSetDriverInstallParamsW` at `0x180014814`
- `SETUPAPI!SetupDiSetDriverInstallParamsW` at `0x180014814`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x180014769`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x18001485f`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x180014769`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x18001485f`

## string_xrefs

- `0x18001464d`: `ClassInstall_SelectBestCompatDrv - Enter`
- `0x180014654`: `ClassInstall_SelectBestCompatDrv`
- `0x1800146c4`: `ClassInstall_SelectBestCompatDrv`
- `0x1800147ec`: `ClassInstall_SelectBestCompatDrv`
- `0x180014833`: `ClassInstall_SelectBestCompatDrv`
- `0x18001487b`: `ClassInstall_SelectBestCompatDrv`
- `0x180014871`: `ClassInstall_SelectBestCompatDrv - Exit and let the PNP to do driver selection: dwRank0Matches=%u, bV4Connection=%u`

## pseudocode

```c
__int64 __fastcall ClassInstall_SelectBestCompatDrv(
        HDEVINFO DeviceInfoSet,
        PSP_DEVINFO_DATA DeviceInfoData,
        struct _SP_DEVINSTALL_PARAMS_W *a3)
{
  char v5; // r13
  unsigned __int8 v6; // r15
  WCHAR *v7; // rdi
  unsigned int v8; // ebx
  DWORD v9; // r12d
  DWORD i; // r9d
  unsigned __int16 Rank; // cx
  DWORD v12; // edi
  DWORD j; // r9d
  DWORD LastError; // eax
  _SP_DRVINSTALL_PARAMS DriverInstallParams; // [rsp+30h] [rbp-D0h] BYREF
  struct _SP_DRVINFO_DATA_V2_W DriverInfoData; // [rsp+50h] [rbp-B0h] BYREF

  v5 = 0;
  v6 = 0;
  memset_0(&DriverInfoData, 0, sizeof(DriverInfoData));
  v7 = 0;
  memset(&DriverInstallParams, 0, sizeof(DriverInstallParams));
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "ClassInstall_SelectBestCompatDrv",
    L"ClassInstall_SelectBestCompatDrv - Enter");
  v8 = 0;
  v9 = 0;
  for ( i = 0; ; i = v9 )
  {
    DriverInfoData.cbSize = 1568;
    if ( !SetupDiEnumDriverInfoW(DeviceInfoSet, DeviceInfoData, 2u, i, &DriverInfoData) )
      break;
    DriverInstallParams.cbSize = 32;
    if ( SetupDiGetDriverInstallParamsW(DeviceInfoSet, DeviceInfoData, &DriverInfoData, &DriverInstallParams) )
    {
      Rank = DriverInstallParams.Rank;
      if ( (DriverInstallParams.Rank & 0xFF0000) < 0xFF0000 && (DriverInstallParams.Rank & 0xFFF) > 2 )
      {
        v5 = 1;
        ClassInstallerTelemetry::WriteDbgTraceWarning(
          "ClassInstall_SelectBestCompatDrv",
          L"Found a driver match '%ws' for a v4 connection with rank 0x%X",
          DriverInfoData.Description,
          DriverInstallParams.Rank);
        Rank = DriverInstallParams.Rank;
      }
      if ( Rank <= 0xFFFu )
      {
        if ( !(unsigned int)_o__wcsicmp(DriverInfoData.Description, L"Microsoft enhanced Point and Print driver")
          || !(unsigned int)_o__wcsicmp(DriverInfoData.Description, L"Microsoft 3D Point and Print driver") )
        {
          v6 = 1;
        }
        if ( v7 )
        {
          if ( !lstrcmpiW(v7, DriverInfoData.Description) )
            goto LABEL_15;
        }
        else
        {
          v7 = (WCHAR *)AllocStr(DriverInfoData.Description);
          if ( !v7 )
            return 3758096910LL;
        }
        ++v8;
      }
    }
LABEL_15:
    ++v9;
  }
  LocalFree(v7);
  if ( v6 && v5 )
  {
    v8 = 0;
    v12 = 0;
    for ( j = 0; ; j = v12 )
    {
      DriverInfoData.cbSize = 1568;
      if ( !SetupDiEnumDriverInfoW(DeviceInfoSet, DeviceInfoData, 2u, j, &DriverInfoData) )
        break;
      DriverInstallParams.cbSize = 32;
      if ( SetupDiGetDriverInstallParamsW(DeviceInfoSet, DeviceInfoData, &DriverInfoData, &DriverInstallParams) )
      {
        if ( (DriverInstallParams.Rank & 0xFF0000) < 0xFF0000 && (DriverInstallParams.Rank & 0xFFF) > 2 )
        {
          DriverInstallParams.Rank |= 0xFF0000u;
          ClassInstallerTelemetry::WriteDbgTraceWarning(
            "ClassInstall_SelectBestCompatDrv",
            L"Setting rank of driver '%ws' to 0x%X",
            DriverInfoData.Description);
          if ( !SetupDiSetDriverInstallParamsW(DeviceInfoSet, DeviceInfoData, &DriverInfoData, &DriverInstallParams) )
          {
            LastError = GetLastError();
            ClassInstallerTelemetry::WriteDbgTraceError(
              "ClassInstall_SelectBestCompatDrv",
              L"Error while setting rank of driver '%ws': %d",
              DriverInfoData.Description,
              LastError);
          }
        }
      }
      ++v12;
    }
  }
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "ClassInstall_SelectBestCompatDrv",
    L"ClassInstall_SelectBestCompatDrv - Exit and let the PNP to do driver selection: dwRank0Matches=%u, bV4Connection=%u",
    v8,
    v6);
  return 3758096910LL;
}

```

## disassembly

```asm
0x1800145fc  mov     [rsp-8+arg_10], rbx
0x180014601  push    rbp
0x180014602  push    rsi
0x180014603  push    rdi
0x180014604  push    r12
0x180014606  push    r13
0x180014608  push    r14
0x18001460a  push    r15
0x18001460c  lea     rbp, [rsp-580h]
0x180014614  sub     rsp, 680h
0x18001461b  mov     rax, cs:__security_cookie
0x180014622  xor     rax, rsp
0x180014625  mov     [rbp+5B0h+var_40], rax
0x18001462c  mov     r14, rdx
0x18001462f  mov     rsi, rcx
0x180014632  xor     edx, edx; Val
0x180014634  lea     rcx, [rsp+6B0h+DriverInfoData]; void *
0x180014639  mov     r8d, 620h; Size
0x18001463f  xor     r13b, r13b
0x180014642  xor     r15b, r15b
0x180014645  call    memset_0
0x18001464a  xorps   xmm0, xmm0
0x18001464d  lea     rdx, aClassinstallSe_0; "ClassInstall_SelectBestCompatDrv - Ente"...
0x180014654  lea     rcx, aClassinstallSe; "ClassInstall_SelectBestCompatDrv"
0x18001465b  xor     edi, edi
0x18001465d  movups  xmmword ptr [rsp+6B0h+DriverInstallParams.cbSize], xmm0
0x180014662  movups  xmmword ptr [rsp+6B0h+DriverInstallParams.PrivateData], xmm0
0x180014667  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001466c  xor     ebx, ebx
0x18001466e  xor     r12d, r12d
0x180014671  xor     r9d, r9d
0x180014674  jmp     loc_18001474B
0x180014679  lea     r9, [rsp+6B0h+DriverInstallParams]; DriverInstallParams
0x18001467e  mov     [rsp+6B0h+DriverInstallParams.cbSize], 20h ; ' '
0x180014686  lea     r8, [rsp+6B0h+DriverInfoData]; DriverInfoData
0x18001468b  mov     rdx, r14; DeviceInfoData
0x18001468e  mov     rcx, rsi; DeviceInfoSet
0x180014691  call    cs:__imp_SetupDiGetDriverInstallParamsW
0x180014697  test    eax, eax
0x180014699  jz      loc_180014745
0x18001469f  mov     ecx, [rsp+6B0h+DriverInstallParams.Rank]
0x1800146a3  mov     edx, 0FF0000h
0x1800146a8  mov     eax, ecx
0x1800146aa  and     eax, edx
0x1800146ac  cmp     eax, edx
0x1800146ae  jnb     short loc_1800146DE
0x1800146b0  mov     eax, ecx
0x1800146b2  and     eax, 0FFFh
0x1800146b7  cmp     eax, 2
0x1800146ba  jbe     short loc_1800146DE
0x1800146bc  mov     r9d, ecx
0x1800146bf  lea     r8, [rsp+6B0h+DriverInfoData.Description]
0x1800146c4  lea     rcx, aClassinstallSe; "ClassInstall_SelectBestCompatDrv"
0x1800146cb  mov     r13b, 1
0x1800146ce  lea     rdx, aFoundADriverMa; "Found a driver match '%ws' for a v4 con"...
0x1800146d5  call    ?WriteDbgTraceWarning@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800146da  mov     ecx, [rsp+6B0h+DriverInstallParams.Rank]
0x1800146de  cmp     cx, 0FFFh
0x1800146e3  ja      short loc_180014745
0x1800146e5  lea     rdx, aMicrosoftEnhan; "Microsoft enhanced Point and Print driv"...
0x1800146ec  lea     rcx, [rsp+6B0h+DriverInfoData.Description]
0x1800146f1  call    cs:__imp__o__wcsicmp
0x1800146f7  test    eax, eax
0x1800146f9  jz      short loc_180014711
0x1800146fb  lea     rdx, aMicrosoft3dPoi; "Microsoft 3D Point and Print driver"
0x180014702  lea     rcx, [rsp+6B0h+DriverInfoData.Description]
0x180014707  call    cs:__imp__o__wcsicmp
0x18001470d  test    eax, eax
0x18001470f  jnz     short loc_180014714
0x180014711  mov     r15b, 1
0x180014714  test    rdi, rdi
0x180014717  jnz     short loc_180014731
0x180014719  lea     rcx, [rsp+6B0h+DriverInfoData.Description]; unsigned __int16 *
0x18001471e  call    AllocStr
0x180014723  mov     rdi, rax
0x180014726  test    rax, rax
0x180014729  jz      loc_180014887
0x18001472f  jmp     short loc_180014743
0x180014731  lea     rdx, [rsp+6B0h+DriverInfoData.Description]; lpString2
0x180014736  mov     rcx, rdi; lpString1
0x180014739  call    cs:__imp_lstrcmpiW
0x18001473f  test    eax, eax
0x180014741  jz      short loc_180014745
0x180014743  inc     ebx
0x180014745  inc     r12d
0x180014748  mov     r9d, r12d; MemberIndex
0x18001474b  lea     rax, [rsp+6B0h+DriverInfoData]
0x180014750  mov     [rsp+6B0h+DriverInfoData.cbSize], 620h
0x180014758  mov     r8d, 2; DriverType
0x18001475e  mov     [rsp+6B0h+var_690], rax; DriverInfoData
0x180014763  mov     rdx, r14; DeviceInfoData
0x180014766  mov     rcx, rsi; DeviceInfoSet
0x180014769  call    cs:__imp_SetupDiEnumDriverInfoW
0x18001476f  test    eax, eax
0x180014771  jnz     loc_180014679
0x180014777  mov     rcx, rdi; hMem
0x18001477a  call    cs:__imp_LocalFree
0x180014780  test    r15b, r15b
0x180014783  jz      loc_18001486D
0x180014789  test    r13b, r13b
0x18001478c  jz      loc_18001486D
0x180014792  xor     ebx, ebx
0x180014794  xor     edi, edi
0x180014796  xor     r9d, r9d
0x180014799  lea     r12d, [rbx+2]
0x18001479d  jmp     loc_180014844
0x1800147a2  lea     r9, [rsp+6B0h+DriverInstallParams]; DriverInstallParams
0x1800147a7  mov     [rsp+6B0h+DriverInstallParams.cbSize], 20h ; ' '
0x1800147af  lea     r8, [rsp+6B0h+DriverInfoData]; DriverInfoData
0x1800147b4  mov     rdx, r14; DeviceInfoData
0x1800147b7  mov     rcx, rsi; DeviceInfoSet
0x1800147ba  call    cs:__imp_SetupDiGetDriverInstallParamsW
0x1800147c0  test    eax, eax
0x1800147c2  jz      short loc_18001483F
0x1800147c4  mov     r9d, [rsp+6B0h+DriverInstallParams.Rank]
0x1800147c9  mov     ecx, 0FF0000h
0x1800147ce  mov     eax, r9d
0x1800147d1  and     eax, ecx
0x1800147d3  cmp     eax, ecx
0x1800147d5  jnb     short loc_18001483F
0x1800147d7  mov     eax, r9d
0x1800147da  and     eax, 0FFFh
0x1800147df  cmp     eax, r12d
0x1800147e2  jbe     short loc_18001483F
0x1800147e4  or      r9d, ecx
0x1800147e7  lea     r8, [rsp+6B0h+DriverInfoData.Description]
0x1800147ec  lea     rcx, aClassinstallSe; "ClassInstall_SelectBestCompatDrv"
0x1800147f3  mov     [rsp+6B0h+DriverInstallParams.Rank], r9d
0x1800147f8  lea     rdx, aSettingRankOfD; "Setting rank of driver '%ws' to 0x%X"
0x1800147ff  call    ?WriteDbgTraceWarning@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180014804  lea     r9, [rsp+6B0h+DriverInstallParams]; DriverInstallParams
0x180014809  mov     rdx, r14; DeviceInfoData
0x18001480c  lea     r8, [rsp+6B0h+DriverInfoData]; DriverInfoData
0x180014811  mov     rcx, rsi; DeviceInfoSet
0x180014814  call    cs:__imp_SetupDiSetDriverInstallParamsW
0x18001481a  test    eax, eax
0x18001481c  jnz     short loc_18001483F
0x18001481e  call    cs:__imp_GetLastError
0x180014824  mov     r9d, eax
0x180014827  lea     r8, [rsp+6B0h+DriverInfoData.Description]
0x18001482c  lea     rdx, aErrorWhileSett; "Error while setting rank of driver '%ws"...
0x180014833  lea     rcx, aClassinstallSe; "ClassInstall_SelectBestCompatDrv"
0x18001483a  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001483f  inc     edi
0x180014841  mov     r9d, edi; MemberIndex
0x180014844  lea     rax, [rsp+6B0h+DriverInfoData]
0x180014849  mov     [rsp+6B0h+DriverInfoData.cbSize], 620h
0x180014851  mov     r8d, r12d; DriverType
0x180014854  mov     [rsp+6B0h+var_690], rax; DriverInfoData
0x180014859  mov     rdx, r14; DeviceInfoData
0x18001485c  mov     rcx, rsi; DeviceInfoSet
0x18001485f  call    cs:__imp_SetupDiEnumDriverInfoW
0x180014865  test    eax, eax
0x180014867  jnz     loc_1800147A2
0x18001486d  movzx   r9d, r15b
0x180014871  lea     rdx, aClassinstallSe_3; "ClassInstall_SelectBestCompatDrv - Exit"...
0x180014878  mov     r8d, ebx
0x18001487b  lea     rcx, aClassinstallSe; "ClassInstall_SelectBestCompatDrv"
0x180014882  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180014887  mov     eax, 0E000020Eh
0x18001488c  mov     rcx, [rbp+5B0h+var_40]
0x180014893  xor     rcx, rsp; StackCookie
0x180014896  call    __security_check_cookie
0x18001489b  mov     rbx, [rsp+6B0h+arg_10]
0x1800148a3  add     rsp, 680h
0x1800148aa  pop     r15
0x1800148ac  pop     r14
0x1800148ae  pop     r13
0x1800148b0  pop     r12
0x1800148b2  pop     rdi
0x1800148b3  pop     rsi
0x1800148b4  pop     rbp
0x1800148b5  retn
```
