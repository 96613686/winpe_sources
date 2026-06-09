# PreSelectDriverEx

- ea: `0x1800284d0`
- end: `0x180028897`
- name: `PreSelectDriverEx`
- size: `967`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, LPCWSTR lpString1@<rdx>, LPCWSTR@<r8>, int, int)`
- caller_count: `7`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000ed30`
- `0x180011c70`
- `0x18001de14`
- `0x180027a50`
- `0x180027c90`
- `0x18002c0f0`
- `0x1800344b0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000d57c`
- `0x18000d624`
- `0x1800162c8`
- `0x1800272bc`
- `0x1800284d0`
- `0x180033f80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028865`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028865`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028829`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028829`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180028751`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180028751`
- `KERNEL32!lstrcmpiW` at `0x180028638`
- `KERNEL32!lstrcmpiW` at `0x18002866c`
- `KERNEL32!lstrcmpiW` at `0x180028638`
- `KERNEL32!lstrcmpiW` at `0x18002866c`
- `SETUPAPI!SetupDiSetSelectedDriverW` at `0x180028818`
- `SETUPAPI!SetupDiSetSelectedDriverW` at `0x180028818`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x180028615`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x180028804`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x180028615`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x180028804`

## pseudocode

```c
__int64 __fastcall PreSelectDriverEx(void *a1, LPCWSTR lpString1, LPCWSTR a3, int a4, int a5, int a6)
{
  const wchar_t *v10; // rcx
  const wchar_t *v11; // rax
  DWORD v12; // esi
  DWORDLONG DriverVersion; // r12
  int v14; // r15d
  int v15; // r14d
  int v16; // edx
  LONG v17; // eax
  DWORD LastError; // eax
  int hMem; // [rsp+30h] [rbp-D0h] BYREF
  int hMem_4; // [rsp+34h] [rbp-CCh]
  int v22; // [rsp+38h] [rbp-C8h]
  int v23; // [rsp+3Ch] [rbp-C4h] BYREF
  FILETIME FileTime1; // [rsp+40h] [rbp-C0h] BYREF
  struct _SP_DRVINFO_DATA_V2_W DriverInfoData; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ReturnBuffer[264]; // [rsp+670h] [rbp+570h] BYREF

  v22 = a4;
  memset_0(&DriverInfoData, 0, sizeof(DriverInfoData));
  FileTime1 = 0;
  memset_0(ReturnBuffer, 0, 0x208u);
  if ( lpString1 )
    lpString1 = (LPCWSTR)(-(__int64)(*lpString1 != 0) & (unsigned __int64)lpString1);
  if ( a3 )
    a3 = (LPCWSTR)(-(__int64)(*a3 != 0) & (unsigned __int64)a3);
  v10 = L"true";
  if ( !a6 )
    v10 = L"false";
  v11 = L"with";
  if ( !a4 )
    v11 = L"without";
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "PreSelectDriverEx",
    L"Preselecting a driver for %ws - %ws %ws versioning, bClassDriverRequired = %ws.",
    lpString1,
    a3,
    v11,
    v10);
  if ( a4 && !a3 )
  {
    ClassInstallerTelemetry::WriteDbgTraceWarning(
      "PreSelectDriverEx",
      L"Can't preselect a driver if no model or INF was specified");
    return 0;
  }
  v12 = 0;
  if ( lpString1 || a3 )
  {
    DriverVersion = 0;
    hMem_4 = 1;
    DriverInfoData.cbSize = 1568;
    v14 = -1;
    v15 = -1;
    while ( 1 )
    {
      if ( !SetupDiEnumDriverInfoW(a1, 0, 1u, v12, &DriverInfoData) )
      {
        if ( v15 != -1 )
        {
          v12 = v15;
          break;
        }
        if ( v14 != -1 )
        {
          v12 = v14;
          break;
        }
        ClassInstallerTelemetry::WriteDbgTraceError(
          "PreSelectDriverEx",
          L"Couldn't find a match for %ws - %ws",
          lpString1,
          a3);
        SetLastError(0x705u);
        return 0;
      }
      if ( lpString1 && v14 == -1 && !lstrcmpiW(lpString1, DriverInfoData.MfgName) )
      {
        ClassInstallerTelemetry::WriteDbgTraceInfo("PreSelectDriverEx", L"Found the manufacturer %ws", lpString1);
        v14 = v12;
      }
      if ( a3 )
      {
        if ( !lstrcmpiW(a3, DriverInfoData.Description) )
        {
          ClassInstallerTelemetry::WriteDbgTraceInfo("PreSelectDriverEx", L"Found a model matching %ws", a3);
          hMem = 0;
          if ( !v22
            || (hMem_4 = GetDriverStorePathFromDeviceInfo(
                           (int)a1,
                           v16,
                           (int)&DriverInfoData,
                           a5,
                           (__int64)&hMem,
                           ReturnBuffer)) != 0
            && hMem )
          {
            hMem = 0;
            v23 = 0;
            if ( !a6
              || (unsigned int)GetVersionAndClassFromInf((int)a1, 0, (int)&DriverInfoData, (int)&v23, &hMem) && hMem )
            {
              if ( v15 == -1 )
              {
                DriverVersion = DriverInfoData.DriverVersion;
                FileTime1 = DriverInfoData.DriverDate;
LABEL_35:
                v15 = v12;
                goto LABEL_36;
              }
              v17 = CompareFileTime(&FileTime1, &DriverInfoData.DriverDate);
              if ( v17 != -1 )
              {
                if ( v17 || DriverInfoData.DriverVersion <= DriverVersion )
                  goto LABEL_36;
                DriverVersion = DriverInfoData.DriverVersion;
                ClassInstallerTelemetry::WriteDbgTraceInfo(
                  "PreSelectDriverEx",
                  L"Found a driver with a higher version for %ws",
                  a3);
                goto LABEL_35;
              }
              DriverVersion = DriverInfoData.DriverVersion;
              FileTime1 = DriverInfoData.DriverDate;
              v15 = v12;
              ClassInstallerTelemetry::WriteDbgTraceInfo(
                "PreSelectDriverEx",
                L"Found a driver with a newer date for %ws",
                a3);
            }
          }
        }
      }
LABEL_36:
      ++v12;
      DriverInfoData.cbSize = 1568;
      if ( !hMem_4 )
        return 0;
    }
  }
  DriverInfoData.cbSize = 1568;
  if ( !SetupDiEnumDriverInfoW(a1, 0, 1u, v12, &DriverInfoData) || !SetupDiSetSelectedDriverW(a1, 0, &DriverInfoData) )
  {
    LastError = GetLastError();
    ClassInstallerTelemetry::WriteDbgTraceError(
      "PreSelectDriverEx",
      L"Error selecting the correct driver: %d",
      LastError);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800284d0  mov     [rsp-8+arg_18], rbx
0x1800284d5  push    rbp
0x1800284d6  push    rsi
0x1800284d7  push    rdi
0x1800284d8  push    r12
0x1800284da  push    r13
0x1800284dc  push    r14
0x1800284de  push    r15
0x1800284e0  lea     rbp, [rsp-790h]
0x1800284e8  sub     rsp, 890h
0x1800284ef  mov     rax, cs:__security_cookie
0x1800284f6  xor     rax, rsp
0x1800284f9  mov     [rbp+7C0h+var_40], rax
0x180028500  mov     rbx, r8
0x180028503  mov     [rsp+8C0h+var_888], r9d
0x180028508  mov     rdi, rdx
0x18002850b  mov     r13, rcx
0x18002850e  xor     edx, edx; Val
0x180028510  lea     rcx, [rsp+8C0h+var_870]; void *
0x180028515  mov     r8d, 620h; Size
0x18002851b  mov     esi, r9d
0x18002851e  call    memset_0
0x180028523  xor     edx, edx; Val
0x180028525  mov     qword ptr [rsp+8C0h+FileTime1.dwLowDateTime], 0
0x18002852e  mov     r8d, 208h; Size
0x180028534  lea     rcx, [rbp+7C0h+var_250]; void *
0x18002853b  call    memset_0
0x180028540  test    rdi, rdi
0x180028543  jz      short loc_180028551
0x180028545  movzx   eax, word ptr [rdi]
0x180028548  neg     ax
0x18002854b  sbb     rcx, rcx
0x18002854e  and     rdi, rcx
0x180028551  test    rbx, rbx
0x180028554  jz      short loc_180028562
0x180028556  movzx   eax, word ptr [rbx]
0x180028559  neg     ax
0x18002855c  sbb     rcx, rcx
0x18002855f  and     rbx, rcx
0x180028562  cmp     [rbp+7C0h+arg_28], 0
0x180028569  lea     rax, aFalse; "false"
0x180028570  lea     rdx, aWithout; "without"
0x180028577  mov     r9, rbx
0x18002857a  lea     rcx, aTrue; "true"
0x180028581  mov     r8, rdi
0x180028584  cmovz   rcx, rax
0x180028588  test    esi, esi
0x18002858a  mov     [rsp+8C0h+ReturnBuffer], rcx
0x18002858f  lea     rax, aWith; "with"
0x180028596  cmovz   rax, rdx
0x18002859a  lea     rcx, aPreselectdrive; "PreSelectDriverEx"
0x1800285a1  lea     rdx, aPreselectingAD; "Preselecting a driver for %ws - %ws %ws"...
0x1800285a8  mov     [rsp+8C0h+DriverInfoData], rax
0x1800285ad  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800285b2  test    esi, esi
0x1800285b4  jz      short loc_1800285D3
0x1800285b6  test    rbx, rbx
0x1800285b9  jnz     short loc_1800285D3
0x1800285bb  lea     rdx, aCanTPreselectA; "Can't preselect a driver if no model or"...
0x1800285c2  lea     rcx, aPreselectdrive; "PreSelectDriverEx"
0x1800285c9  call    ?WriteDbgTraceWarning@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800285ce  jmp     loc_18002886B
0x1800285d3  xor     esi, esi
0x1800285d5  test    rdi, rdi
0x1800285d8  jnz     short loc_1800285E3
0x1800285da  test    rbx, rbx
0x1800285dd  jz      loc_1800287E6
0x1800285e3  xor     r12d, r12d
0x1800285e6  mov     dword ptr [rsp+8C0h+hMem+4], 1
0x1800285ee  or      eax, 0FFFFFFFFh
0x1800285f1  mov     [rsp+8C0h+var_870.cbSize], 620h
0x1800285f9  mov     r15d, eax
0x1800285fc  mov     r14d, eax
0x1800285ff  xor     edx, edx; DeviceInfoData
0x180028601  lea     rax, [rsp+8C0h+var_870]
0x180028606  mov     r9d, esi; MemberIndex
0x180028609  mov     [rsp+8C0h+DriverInfoData], rax; DriverInfoData
0x18002860e  mov     rcx, r13; DeviceInfoSet
0x180028611  lea     r8d, [rdx+1]; DriverType
0x180028615  call    cs:__imp_SetupDiEnumDriverInfoW
0x18002861b  test    eax, eax
0x18002861d  jz      loc_1800287D1
0x180028623  test    rdi, rdi
0x180028626  jz      short loc_18002865B
0x180028628  cmp     r15d, 0FFFFFFFFh
0x18002862c  jnz     short loc_18002865B
0x18002862e  lea     rdx, [rbp+7C0h+var_870.MfgName]; lpString2
0x180028635  mov     rcx, rdi; lpString1
0x180028638  call    cs:__imp_lstrcmpiW
0x18002863e  test    eax, eax
0x180028640  jnz     short loc_18002865B
0x180028642  mov     r8, rdi
0x180028645  lea     rdx, aFoundTheManufa; "Found the manufacturer %ws"
0x18002864c  lea     rcx, aPreselectdrive; "PreSelectDriverEx"
0x180028653  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180028658  mov     r15d, esi
0x18002865b  test    rbx, rbx
0x18002865e  jz      loc_1800287B7
0x180028664  lea     rdx, [rsp+8C0h+var_870.Description]; lpString2
0x180028669  mov     rcx, rbx; lpString1
0x18002866c  call    cs:__imp_lstrcmpiW
0x180028672  test    eax, eax
0x180028674  jnz     loc_1800287B7
0x18002867a  mov     r8, rbx
0x18002867d  lea     rdx, aFoundAModelMat; "Found a model matching %ws"
0x180028684  lea     rcx, aPreselectdrive; "PreSelectDriverEx"
0x18002868b  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180028690  cmp     [rsp+8C0h+var_888], 0
0x180028695  mov     dword ptr [rsp+8C0h+hMem], 0
0x18002869d  jz      short loc_1800286E0
0x18002869f  mov     r9d, [rbp+7C0h+arg_20]; int
0x1800286a6  lea     rax, [rbp+7C0h+var_250]
0x1800286ad  mov     [rsp+8C0h+ReturnBuffer], rax; ReturnBuffer
0x1800286b2  lea     r8, [rsp+8C0h+var_870]; int
0x1800286b7  lea     rax, [rsp+8C0h+hMem]
0x1800286bc  mov     rcx, r13; int
0x1800286bf  mov     [rsp+8C0h+DriverInfoData], rax; __int64
0x1800286c4  call    GetDriverStorePathFromDeviceInfo
0x1800286c9  mov     dword ptr [rsp+8C0h+hMem+4], eax
0x1800286cd  test    eax, eax
0x1800286cf  jz      loc_1800287B7
0x1800286d5  cmp     dword ptr [rsp+8C0h+hMem], 0
0x1800286da  jz      loc_1800287B7
0x1800286e0  cmp     [rbp+7C0h+arg_28], 0
0x1800286e7  mov     dword ptr [rsp+8C0h+hMem], 0
0x1800286ef  mov     [rsp+8C0h+var_884], 0
0x1800286f7  jz      short loc_18002872A
0x1800286f9  lea     rax, [rsp+8C0h+hMem]
0x1800286fe  xor     edx, edx; int
0x180028700  lea     r9, [rsp+8C0h+var_884]; int
0x180028705  mov     [rsp+8C0h+DriverInfoData], rax; hMem
0x18002870a  lea     r8, [rsp+8C0h+var_870]; int
0x18002870f  mov     rcx, r13; int
0x180028712  call    GetVersionAndClassFromInf
0x180028717  test    eax, eax
0x180028719  jz      loc_1800287B7
0x18002871f  cmp     dword ptr [rsp+8C0h+hMem], 0
0x180028724  jz      loc_1800287B7
0x18002872a  cmp     r14d, 0FFFFFFFFh
0x18002872e  jnz     short loc_180028745
0x180028730  mov     rax, qword ptr [rbp+7C0h+var_870.DriverDate.dwLowDateTime]
0x180028737  mov     r12, [rbp+7C0h+var_870.DriverVersion]
0x18002873e  mov     qword ptr [rsp+8C0h+FileTime1.dwLowDateTime], rax
0x180028743  jmp     short loc_1800287B4
0x180028745  lea     rdx, [rbp+7C0h+var_870.DriverDate]; lpFileTime2
0x18002874c  lea     rcx, [rsp+8C0h+FileTime1]; lpFileTime1
0x180028751  call    cs:__imp_CompareFileTime
0x180028757  cmp     eax, 0FFFFFFFFh
0x18002875a  jnz     short loc_18002878A
0x18002875c  mov     rax, qword ptr [rbp+7C0h+var_870.DriverDate.dwLowDateTime]
0x180028763  lea     rdx, aFoundADriverWi; "Found a driver with a newer date for %w"...
0x18002876a  mov     r12, [rbp+7C0h+var_870.DriverVersion]
0x180028771  lea     rcx, aPreselectdrive; "PreSelectDriverEx"
0x180028778  mov     r8, rbx
0x18002877b  mov     qword ptr [rsp+8C0h+FileTime1.dwLowDateTime], rax
0x180028780  mov     r14d, esi
0x180028783  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180028788  jmp     short loc_1800287B7
0x18002878a  test    eax, eax
0x18002878c  jnz     short loc_1800287B7
0x18002878e  cmp     [rbp+7C0h+var_870.DriverVersion], r12
0x180028795  jbe     short loc_1800287B7
0x180028797  mov     r12, [rbp+7C0h+var_870.DriverVersion]
0x18002879e  lea     rdx, aFoundADriverWi_0; "Found a driver with a higher version fo"...
0x1800287a5  mov     r8, rbx
0x1800287a8  lea     rcx, aPreselectdrive; "PreSelectDriverEx"
0x1800287af  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800287b4  mov     r14d, esi
0x1800287b7  inc     esi
0x1800287b9  mov     [rsp+8C0h+var_870.cbSize], 620h
0x1800287c1  cmp     dword ptr [rsp+8C0h+hMem+4], 0
0x1800287c6  jnz     loc_1800285FF
0x1800287cc  jmp     loc_18002886B
0x1800287d1  or      eax, 0FFFFFFFFh
0x1800287d4  cmp     r14d, eax
0x1800287d7  jz      short loc_1800287DE
0x1800287d9  mov     esi, r14d
0x1800287dc  jmp     short loc_1800287E6
0x1800287de  cmp     r15d, eax
0x1800287e1  jz      short loc_180028847
0x1800287e3  mov     esi, r15d
0x1800287e6  xor     edx, edx; DeviceInfoData
0x1800287e8  mov     [rsp+8C0h+var_870.cbSize], 620h
0x1800287f0  lea     rax, [rsp+8C0h+var_870]
0x1800287f5  mov     r9d, esi; MemberIndex
0x1800287f8  mov     rcx, r13; DeviceInfoSet
0x1800287fb  mov     [rsp+8C0h+DriverInfoData], rax; DriverInfoData
0x180028800  lea     r8d, [rdx+1]; DriverType
0x180028804  call    cs:__imp_SetupDiEnumDriverInfoW
0x18002880a  test    eax, eax
0x18002880c  jz      short loc_180028829
0x18002880e  lea     r8, [rsp+8C0h+var_870]; DriverInfoData
0x180028813  xor     edx, edx; DeviceInfoData
0x180028815  mov     rcx, r13; DeviceInfoSet
0x180028818  call    cs:__imp_SetupDiSetSelectedDriverW
0x18002881e  test    eax, eax
0x180028820  jz      short loc_180028829
0x180028822  mov     eax, 1
0x180028827  jmp     short loc_18002886D
0x180028829  call    cs:__imp_GetLastError
0x18002882f  mov     r8d, eax
0x180028832  lea     rdx, aErrorSelecting; "Error selecting the correct driver: %d"
0x180028839  lea     rcx, aPreselectdrive; "PreSelectDriverEx"
0x180028840  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180028845  jmp     short loc_18002886B
0x180028847  mov     r9, rbx
0x18002884a  lea     rdx, aCouldnTFindAMa; "Couldn't find a match for %ws - %ws"
0x180028851  mov     r8, rdi
0x180028854  lea     rcx, aPreselectdrive; "PreSelectDriverEx"
0x18002885b  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180028860  mov     ecx, 705h; dwErrCode
0x180028865  call    cs:__imp_SetLastError
0x18002886b  xor     eax, eax
0x18002886d  mov     rcx, [rbp+7C0h+var_40]
0x180028874  xor     rcx, rsp; StackCookie
0x180028877  call    __security_check_cookie
0x18002887c  mov     rbx, [rsp+8C0h+arg_18]
0x180028884  add     rsp, 890h
0x18002888b  pop     r15
0x18002888d  pop     r14
0x18002888f  pop     r13
0x180028891  pop     r12
0x180028893  pop     rdi
0x180028894  pop     rsi
0x180028895  pop     rbp
0x180028896  retn
```
