# BuildInternalData

- ea: `0x180026820`
- end: `0x180026bfc`
- name: `BuildInternalData`
- size: `988`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `12`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18000ed30`
- `0x180011c70`
- `0x180013804`
- `0x180013e68`
- `0x180014cf8`
- `0x18001de14`
- `0x1800279d0`
- `0x180027a10`
- `0x180027a50`
- `0x180027c80`
- `0x18002c0f0`
- `0x1800344b0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000d57c`
- `0x18000d624`
- `0x18001bc44`
- `0x18001c5c0`
- `0x180026820`
- `0x1800271a8`
- `0x180033f80`
- `0x180035ef8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002693d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026a2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026bb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002693d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026a2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026bb4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026b77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026b8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026b77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026b8a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026897`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800268a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026897`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800268a5`
- `SETUPAPI!SetupGetInfDriverStoreLocationW` at `0x1800269f3`
- `SETUPAPI!SetupGetInfDriverStoreLocationW` at `0x1800269f3`
- `SETUPAPI!SetupDiGetDriverInstallParamsW` at `0x180026933`
- `SETUPAPI!SetupDiGetDriverInstallParamsW` at `0x180026933`
- `SETUPAPI!SetupDiGetSelectedDriverW` at `0x1800268f4`
- `SETUPAPI!SetupDiGetSelectedDriverW` at `0x1800268f4`

## string_xrefs

- `0x180026943`: `Error retrieving the driver install params: %d`

## pseudocode

```c
_QWORD *__fastcall BuildInternalData(void *a1, struct _SP_DEVINFO_DATA *a2, int a3)
{
  _QWORD *v5; // rbx
  char *v6; // rax
  char *v7; // rdi
  int v8; // esi
  DWORD v9; // eax
  DWORD v10; // eax
  __int64 v11; // r13
  BOOL InfDriverStoreLocationW; // eax
  __int64 v13; // r8
  DWORD LastError; // eax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  DWORD v22; // eax
  struct _SP_ALTPLATFORM_INFO_V2 AlternatePlatformInfo; // [rsp+40h] [rbp-C0h] BYREF
  struct _SP_DRVINFO_DATA_V2_W DriverInfoData; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ReturnBuffer[264]; // [rsp+680h] [rbp+580h] BYREF

  memset_0(&DriverInfoData, 0, sizeof(DriverInfoData));
  memset_0(ReturnBuffer, 0, 0x208u);
  v5 = LocalAlloc(0x40u, 0x1B8u);
  v6 = (char *)LocalAlloc(0x40u, 0x20u);
  v7 = v6;
  if ( v5 )
  {
    if ( !v6 )
      goto LABEL_29;
    v5[3] = a2;
    *((_DWORD *)v5 + 40) = 38277;
    DriverInfoData.cbSize = 1568;
    v8 = 0;
    ClassInstallerTelemetry::WriteDbgTraceInfo(
      "BuildInternalData",
      L"Populating the PSETUP_LOCAL_DATA structure with information about the currently selected driver");
    if ( SetupDiGetSelectedDriverW(a1, a2, &DriverInfoData) )
    {
      *(_DWORD *)v7 = 32;
      if ( SetupDiGetDriverInstallParamsW(a1, a2, &DriverInfoData, (PSP_DRVINSTALL_PARAMS)v7) )
      {
        if ( v7[8] < 0 )
          *((_DWORD *)v5 + 20) |= 2u;
        if ( (unsigned int)GetDriverInfoDetail(a1, a2, &DriverInfoData) )
        {
          v11 = 544;
          if ( (unsigned int)IsInInfDir(544) )
          {
            *(_QWORD *)&AlternatePlatformInfo.MajorVersion = 0;
            *(_QWORD *)&AlternatePlatformInfo.Reserved = 0;
            AlternatePlatformInfo.Platform = *(&PlatformArch + 2 * a3);
            AlternatePlatformInfo.ProcessorArchitecture = *((_WORD *)&PlatformArch + 4 * a3 + 2);
            HIWORD(AlternatePlatformInfo.FirstValidatedMinorVersion) = 0;
            AlternatePlatformInfo.cbSize = 28;
            InfDriverStoreLocationW = SetupGetInfDriverStoreLocationW(
                                        (PCWSTR)0x220,
                                        &AlternatePlatformInfo,
                                        0,
                                        ReturnBuffer,
                                        0x104u,
                                        0);
            v13 = (__int64)ReturnBuffer;
            if ( !InfDriverStoreLocationW )
              v13 = 544;
            v11 = v13;
          }
          if ( (unsigned int)GetVersionAndClassFromInf((int)a1, (int)a2, (int)&DriverInfoData, (int)v5 + 96, v5 + 16) )
          {
            v15 = AllocStr((unsigned __int16 *)v11);
            *v5 = v15;
            ClassInstallerTelemetry::WriteDbgTraceInfo("BuildInternalData", L"pszInfName=%ws", v15);
            v16 = AllocStr((unsigned __int16 *)0x20);
            v5[2] = v16;
            ClassInstallerTelemetry::WriteDbgTraceInfo("BuildInternalData", L"pszDriverSection=%ws", v16);
            v17 = AllocStr(DriverInfoData.Description);
            v5[1] = v17;
            ClassInstallerTelemetry::WriteDbgTraceInfo("BuildInternalData", L"pszModelName=%ws", v17);
            v18 = AllocStr(DriverInfoData.MfgName);
            v5[5] = v18;
            ClassInstallerTelemetry::WriteDbgTraceInfo("BuildInternalData", L"pszManufacturer=%ws", v18);
            v19 = AllocStr(DriverInfoData.ProviderName);
            v5[7] = v19;
            ClassInstallerTelemetry::WriteDbgTraceInfo("BuildInternalData", L"pszProvider=%ws", v19);
            v5[8] = DriverInfoData.DriverDate;
            v5[9] = DriverInfoData.DriverVersion;
            if ( !MEMORY[0x628]
              || (v20 = AllocStr((unsigned __int16 *)0x628),
                  v5[4] = v20,
                  ClassInstallerTelemetry::WriteDbgTraceInfo("BuildInternalData", L"pszHardwareID=%ws", v20),
                  v5[4]) )
            {
              if ( *v5 && v5[2] && v5[1] && v5[7] )
              {
                if ( v5[5] )
                  v8 = 1;
              }
            }
          }
          else
          {
            LastError = GetLastError();
            ClassInstallerTelemetry::WriteDbgTraceError(
              "BuildInternalData",
              L"Error retrieving version and class status: %d",
              LastError);
          }
        }
        else
        {
          ClassInstallerTelemetry::WriteDbgTraceError(
            "BuildInternalData",
            L"Error retrieving the driver info structure");
        }
      }
      else
      {
        v10 = GetLastError();
        ClassInstallerTelemetry::WriteDbgTraceError(
          "BuildInternalData",
          L"Error retrieving the driver install params: %d",
          v10);
      }
    }
    else
    {
      v9 = GetLastError();
      ClassInstallerTelemetry::WriteDbgTraceError("BuildInternalData", L"Error retrieving the selected driver: %d", v9);
    }
  }
  else
  {
    v8 = 0;
    if ( !v6 )
      goto LABEL_29;
  }
  LocalFree(v7);
  if ( v8 )
  {
    ClassInstallerTelemetry::WriteDbgTraceInfo(
      "BuildInternalData",
      L"Successfully populated the PSETUP_LOCAL_DATA structure");
    return v5;
  }
LABEL_29:
  DestroyLocalData(v5);
  v22 = GetLastError();
  ClassInstallerTelemetry::WriteDbgTraceError(
    "BuildInternalData",
    L"Error populating the PSETUP_LOCAL_DATA structure: %d",
    v22);
  return 0;
}

```

## disassembly

```asm
0x180026820  mov     [rsp-8+arg_18], rbx
0x180026825  push    rbp
0x180026826  push    rsi
0x180026827  push    rdi
0x180026828  push    r12
0x18002682a  push    r13
0x18002682c  push    r14
0x18002682e  push    r15
0x180026830  lea     rbp, [rsp-7A0h]
0x180026838  sub     rsp, 8A0h
0x18002683f  mov     rax, cs:__security_cookie
0x180026846  xor     rax, rsp
0x180026849  mov     [rbp+7D0h+var_40], rax
0x180026850  mov     [rsp+8D0h+var_8A0], r8d
0x180026855  mov     r14, rdx
0x180026858  mov     r12, rcx
0x18002685b  mov     r15d, 620h
0x180026861  xor     r13d, r13d
0x180026864  lea     rcx, [rsp+8D0h+DriverInfoData]; void *
0x180026869  mov     r8d, r15d; Size
0x18002686c  mov     [rsp+8D0h+hMem], r13
0x180026871  xor     edx, edx; Val
0x180026873  call    memset_0
0x180026878  xor     edx, edx; Val
0x18002687a  lea     rcx, [rbp+7D0h+ReturnBuffer]; void *
0x180026881  mov     r8d, 208h; Size
0x180026887  call    memset_0
0x18002688c  lea     edi, [r13+40h]
0x180026890  mov     edx, 1B8h; uBytes
0x180026895  mov     ecx, edi; uFlags
0x180026897  call    cs:__imp_LocalAlloc
0x18002689d  lea     edx, [rdi-20h]; uBytes
0x1800268a0  mov     ecx, edi; uFlags
0x1800268a2  mov     rbx, rax
0x1800268a5  call    cs:__imp_LocalAlloc
0x1800268ab  mov     rdi, rax
0x1800268ae  test    rbx, rbx
0x1800268b1  jz      loc_180026B7F
0x1800268b7  test    rax, rax
0x1800268ba  jz      loc_180026BAC
0x1800268c0  mov     [rbx+18h], r14
0x1800268c4  lea     rdx, aPopulatingTheP; "Populating the PSETUP_LOCAL_DATA struct"...
0x1800268cb  mov     dword ptr [rbx+0A0h], 9585h
0x1800268d5  lea     rcx, aBuildinternald_1; "BuildInternalData"
0x1800268dc  mov     [rsp+8D0h+DriverInfoData.cbSize], r15d
0x1800268e1  mov     esi, r13d
0x1800268e4  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800268e9  lea     r8, [rsp+8D0h+DriverInfoData]; DriverInfoData
0x1800268ee  mov     rdx, r14; DeviceInfoData
0x1800268f1  mov     rcx, r12; DeviceInfoSet
0x1800268f4  call    cs:__imp_SetupDiGetSelectedDriverW
0x1800268fa  test    eax, eax
0x1800268fc  jnz     short loc_18002691F
0x1800268fe  call    cs:__imp_GetLastError
0x180026904  lea     rdx, aErrorRetrievin_5; "Error retrieving the selected driver: %"...
0x18002690b  mov     r8d, eax
0x18002690e  lea     rcx, aBuildinternald_1; "BuildInternalData"
0x180026915  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18002691a  jmp     loc_180026B87
0x18002691f  mov     r9, rdi; DriverInstallParams
0x180026922  mov     dword ptr [rdi], 20h ; ' '
0x180026928  lea     r8, [rsp+8D0h+DriverInfoData]; DriverInfoData
0x18002692d  mov     rdx, r14; DeviceInfoData
0x180026930  mov     rcx, r12; DeviceInfoSet
0x180026933  call    cs:__imp_SetupDiGetDriverInstallParamsW
0x180026939  test    eax, eax
0x18002693b  jnz     short loc_18002694C
0x18002693d  call    cs:__imp_GetLastError
0x180026943  lea     rdx, aErrorRetrievin_14; "Error retrieving the driver install par"...
0x18002694a  jmp     short loc_18002690B
0x18002694c  test    byte ptr [rdi+8], 80h
0x180026950  jz      short loc_180026956
0x180026952  or      dword ptr [rbx+50h], 2
0x180026956  lea     r9, [rsp+8D0h+hMem]
0x18002695b  mov     rdx, r14; DeviceInfoData
0x18002695e  lea     r8, [rsp+8D0h+DriverInfoData]; DriverInfoData
0x180026963  mov     rcx, r12; DeviceInfoSet
0x180026966  call    GetDriverInfoDetail
0x18002696b  mov     r15, [rsp+8D0h+hMem]
0x180026970  test    eax, eax
0x180026972  jnz     short loc_18002698C
0x180026974  lea     rdx, aErrorRetrievin_4; "Error retrieving the driver info struct"...
0x18002697b  lea     rcx, aBuildinternald_1; "BuildInternalData"
0x180026982  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180026987  jmp     loc_180026B6F
0x18002698c  lea     r13, [r15+220h]
0x180026993  mov     rcx, r13
0x180026996  call    IsInInfDir
0x18002699b  xor     r8d, r8d; LocaleName
0x18002699e  test    eax, eax
0x1800269a0  jz      short loc_180026A09
0x1800269a2  movsxd  rcx, [rsp+8D0h+var_8A0]
0x1800269a7  lea     rdx, PlatformArch
0x1800269ae  mov     [rsp+8D0h+RequiredSize], r8; RequiredSize
0x1800269b3  lea     r9, [rbp+7D0h+ReturnBuffer]; ReturnBuffer
0x1800269ba  mov     qword ptr [rsp+8D0h+AlternatePlatformInfo.MajorVersion], r8
0x1800269bf  mov     qword ptr [rsp+8D0h+AlternatePlatformInfo.12h], r8
0x1800269c4  mov     eax, [rdx+rcx*8]
0x1800269c7  mov     [rsp+8D0h+AlternatePlatformInfo.Platform], eax
0x1800269cb  movzx   eax, word ptr [rdx+rcx*8+4]
0x1800269d0  lea     rdx, [rsp+8D0h+AlternatePlatformInfo]; AlternatePlatformInfo
0x1800269d5  mov     rcx, r13; FileName
0x1800269d8  mov     [rsp+8D0h+AlternatePlatformInfo.ProcessorArchitecture], ax
0x1800269dd  mov     word ptr [rsp+8D0h+AlternatePlatformInfo.FirstValidatedMinorVersion+2], r8w
0x1800269e3  mov     [rsp+8D0h+AlternatePlatformInfo.cbSize], 1Ch
0x1800269eb  mov     [rsp+8D0h+ReturnBufferSize], 104h; ReturnBufferSize
0x1800269f3  call    cs:__imp_SetupGetInfDriverStoreLocationW
0x1800269f9  test    eax, eax
0x1800269fb  lea     r8, [rbp+7D0h+ReturnBuffer]
0x180026a02  cmovz   r8, r13
0x180026a06  mov     r13, r8
0x180026a09  lea     rax, [rbx+80h]
0x180026a10  mov     rdx, r14; int
0x180026a13  lea     r9, [rbx+60h]; int
0x180026a17  mov     qword ptr [rsp+8D0h+ReturnBufferSize], rax; hMem
0x180026a1c  lea     r8, [rsp+8D0h+DriverInfoData]; int
0x180026a21  mov     rcx, r12; int
0x180026a24  call    GetVersionAndClassFromInf
0x180026a29  test    eax, eax
0x180026a2b  jnz     short loc_180026A4E
0x180026a2d  call    cs:__imp_GetLastError
0x180026a33  mov     r8d, eax
0x180026a36  lea     rdx, aErrorRetrievin; "Error retrieving version and class stat"...
0x180026a3d  lea     rcx, aBuildinternald_1; "BuildInternalData"
0x180026a44  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180026a49  jmp     loc_180026B6F
0x180026a4e  mov     rcx, r13; unsigned __int16 *
0x180026a51  call    AllocStr
0x180026a56  mov     r8, rax
0x180026a59  mov     [rbx], rax
0x180026a5c  lea     rdx, aPszinfnameWs; "pszInfName=%ws"
0x180026a63  lea     rcx, aBuildinternald_1; "BuildInternalData"
0x180026a6a  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180026a6f  lea     rcx, [r15+20h]; unsigned __int16 *
0x180026a73  call    AllocStr
0x180026a78  mov     r8, rax
0x180026a7b  mov     [rbx+10h], rax
0x180026a7f  lea     rdx, aPszdriversecti; "pszDriverSection=%ws"
0x180026a86  lea     rcx, aBuildinternald_1; "BuildInternalData"
0x180026a8d  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180026a92  lea     rcx, [rsp+8D0h+DriverInfoData.Description]; unsigned __int16 *
0x180026a97  call    AllocStr
0x180026a9c  mov     r8, rax
0x180026a9f  mov     [rbx+8], rax
0x180026aa3  lea     rdx, aPszmodelnameWs; "pszModelName=%ws"
0x180026aaa  lea     rcx, aBuildinternald_1; "BuildInternalData"
0x180026ab1  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180026ab6  lea     rcx, [rbp+7D0h+DriverInfoData.MfgName]; unsigned __int16 *
0x180026abd  call    AllocStr
0x180026ac2  mov     r8, rax
0x180026ac5  mov     [rbx+28h], rax
0x180026ac9  lea     rdx, aPszmanufacture; "pszManufacturer=%ws"
0x180026ad0  lea     rcx, aBuildinternald_1; "BuildInternalData"
0x180026ad7  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180026adc  lea     rcx, [rbp+7D0h+DriverInfoData.ProviderName]; unsigned __int16 *
0x180026ae3  call    AllocStr
0x180026ae8  mov     r8, rax
0x180026aeb  mov     [rbx+38h], rax
0x180026aef  lea     rdx, aPszproviderWs; "pszProvider=%ws"
0x180026af6  lea     rcx, aBuildinternald_1; "BuildInternalData"
0x180026afd  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180026b02  mov     rax, qword ptr [rbp+7D0h+DriverInfoData.DriverDate.dwLowDateTime]
0x180026b09  lea     rcx, [r15+628h]; unsigned __int16 *
0x180026b10  mov     [rbx+40h], rax
0x180026b14  xor     r13d, r13d
0x180026b17  mov     rax, [rbp+7D0h+DriverInfoData.DriverVersion]
0x180026b1e  mov     [rbx+48h], rax
0x180026b22  cmp     [rcx], r13w
0x180026b26  jz      short loc_180026B4D
0x180026b28  call    AllocStr
0x180026b2d  mov     r8, rax
0x180026b30  mov     [rbx+20h], rax
0x180026b34  lea     rdx, aPszhardwareidW; "pszHardwareID=%ws"
0x180026b3b  lea     rcx, aBuildinternald_1; "BuildInternalData"
0x180026b42  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180026b47  cmp     [rbx+20h], r13
0x180026b4b  jz      short loc_180026B6F
0x180026b4d  cmp     [rbx], r13
0x180026b50  jz      short loc_180026B6F
0x180026b52  cmp     [rbx+10h], r13
0x180026b56  jz      short loc_180026B6F
0x180026b58  cmp     [rbx+8], r13
0x180026b5c  jz      short loc_180026B6F
0x180026b5e  cmp     [rbx+38h], r13
0x180026b62  jz      short loc_180026B6F
0x180026b64  cmp     [rbx+28h], r13
0x180026b68  jz      short loc_180026B6F
0x180026b6a  mov     esi, 1
0x180026b6f  test    r15, r15
0x180026b72  jz      short loc_180026B87
0x180026b74  mov     rcx, r15; hMem
0x180026b77  call    cs:__imp_LocalFree
0x180026b7d  jmp     short loc_180026B87
0x180026b7f  mov     esi, r13d
0x180026b82  test    rdi, rdi
0x180026b85  jz      short loc_180026BAC
0x180026b87  mov     rcx, rdi; hMem
0x180026b8a  call    cs:__imp_LocalFree
0x180026b90  test    esi, esi
0x180026b92  jz      short loc_180026BAC
0x180026b94  lea     rdx, aSuccessfullyPo; "Successfully populated the PSETUP_LOCAL"...
0x180026b9b  lea     rcx, aBuildinternald_1; "BuildInternalData"
0x180026ba2  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180026ba7  mov     rax, rbx
0x180026baa  jmp     short loc_180026BD2
0x180026bac  mov     rcx, rbx; hMem
0x180026baf  call    DestroyLocalData
0x180026bb4  call    cs:__imp_GetLastError
0x180026bba  mov     r8d, eax
0x180026bbd  lea     rdx, aErrorPopulatin_0; "Error populating the PSETUP_LOCAL_DATA "...
0x180026bc4  lea     rcx, aBuildinternald_1; "BuildInternalData"
0x180026bcb  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180026bd0  xor     eax, eax
0x180026bd2  mov     rcx, [rbp+7D0h+var_40]
0x180026bd9  xor     rcx, rsp; StackCookie
0x180026bdc  call    __security_check_cookie
0x180026be1  mov     rbx, [rsp+8D0h+arg_18]
0x180026be9  add     rsp, 8A0h
0x180026bf0  pop     r15
0x180026bf2  pop     r14
0x180026bf4  pop     r13
0x180026bf6  pop     r12
0x180026bf8  pop     rdi
0x180026bf9  pop     rsi
0x180026bfa  pop     rbp
0x180026bfb  retn
```
