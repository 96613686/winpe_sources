# SplFindCompatibleDriver(ushort const *,ushort const *,ushort *,ulong,ulong *,ushort *,ulong,ulong *,ulong *)

- ea: `0x1800bd740`
- end: `0x1800bdaab`
- name: `?SplFindCompatibleDriver@@YAJPEBG0PEAGKPEAK1K22@Z`
- size: `875`
- prototype: `__int64 __usercall@<rax>(BYTE *PropertyBuffer@<rcx>, BYTE *lpData@<rdx>, unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int *, unsigned __int16 *, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180011f00`
- `0x180012510`
- `0x1800159d8`
- `0x18003ea2c`
- `0x180046650`
- `0x180047330`
- `0x1800bd578`
- `0x1800bd740`

## import_xrefs

- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1800bda80`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1800bda80`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x1800bd838`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x1800bd838`
- `SETUPAPI!SetupDiBuildDriverInfoList` at `0x1800bd8a4`
- `SETUPAPI!SetupDiBuildDriverInfoList` at `0x1800bd8a4`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x1800bd8e0`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x1800bd8e0`
- `SETUPAPI!SetupDiGetSelectedDriverW` at `0x1800bd922`
- `SETUPAPI!SetupDiGetSelectedDriverW` at `0x1800bd922`
- `SETUPAPI!SetupDiDeleteDeviceInfo` at `0x1800bda6d`
- `SETUPAPI!SetupDiDeleteDeviceInfo` at `0x1800bda6d`
- `SETUPAPI!SetupDiDestroyDriverInfoList` at `0x1800bda58`
- `SETUPAPI!SetupDiDestroyDriverInfoList` at `0x1800bda58`
- `SETUPAPI!SetupDiGetDriverInstallParamsW` at `0x1800bd96a`
- `SETUPAPI!SetupDiGetDriverInstallParamsW` at `0x1800bd96a`

## string_xrefs

- `0x1800bd84f`: `SetupDiCreateDeviceInfoList failed with error code hr: 0x%x`
- `0x1800bd856`: `SplFindCompatibleDriver`
- `0x1800bd8bd`: `SplFindCompatibleDriver`
- `0x1800bd8f9`: `SplFindCompatibleDriver`
- `0x1800bd93b`: `SplFindCompatibleDriver`
- `0x1800bda36`: `SplFindCompatibleDriver`
- `0x1800bd8f2`: `SetupDiCallClassInstaller failed with error code hr: 0x%x`
- `0x1800bda2f`: `SetupDiGetDriverInstallParams failed with error code hr: 0x%x`

## pseudocode

```c
__int64 __fastcall SplFindCompatibleDriver(
        BYTE *PropertyBuffer,
        BYTE *lpData,
        unsigned __int16 *a3,
        int a4,
        unsigned int *a5,
        unsigned __int16 *a6,
        unsigned int a7,
        unsigned int *a8,
        unsigned int *a9)
{
  BYTE *LastErrorAsHResult; // rbx
  __int64 DeviceInfoList; // rdi
  unsigned int v14; // r10d
  unsigned __int64 v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+28h] [rbp-D8h]
  _DWORD v18[3]; // [rsp+2Ch] [rbp-D4h]
  unsigned int *v19; // [rsp+38h] [rbp-C8h]
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+40h] [rbp-C0h] BYREF
  _SP_DRVINSTALL_PARAMS DriverInstallParams; // [rsp+60h] [rbp-A0h] BYREF
  _SP_DRVINFO_DATA_V2_W DriverInfoData; // [rsp+80h] [rbp-80h] BYREF

  LastErrorAsHResult = PropertyBuffer;
  v16 = (unsigned __int64)PropertyBuffer;
  v19 = a5;
  *(_QWORD *)&v18[1] = a8;
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  v18[0] = a4;
  memset_0(&DriverInfoData, 0, sizeof(DriverInfoData));
  v17 = 0;
  memset(&DriverInstallParams, 0, sizeof(DriverInstallParams));
  if ( LastErrorAsHResult && lpData && (a3 || !a4) && (a6 || !a7) && a5 && *(_QWORD *)&v18[1] && a9 )
  {
    DeviceInfoList = (__int64)SetupDiCreateDeviceInfoList(&GUID_DEVCLASS_PRINTER, 0);
    if ( DeviceInfoList == -1 )
    {
      LastErrorAsHResult = (BYTE *)(unsigned int)GetLastErrorAsHResult();
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "SplFindCompatibleDriver",
        L"SetupDiCreateDeviceInfoList failed with error code hr: 0x%x",
        LastErrorAsHResult);
      if ( (int)LastErrorAsHResult < 0 )
        goto LABEL_31;
      LastErrorAsHResult = (BYTE *)v16;
    }
    LODWORD(LastErrorAsHResult) = PSetupCreateDevInfoFromPnpID(
                                    (HDEVINFO)DeviceInfoList,
                                    LastErrorAsHResult,
                                    lpData,
                                    &DeviceInfoData);
    if ( (int)LastErrorAsHResult >= 0 )
    {
      v17 = 1;
      if ( SetupDiBuildDriverInfoList((HDEVINFO)DeviceInfoList, &DeviceInfoData, 2u)
        || (LastErrorAsHResult = (BYTE *)(unsigned int)GetLastErrorAsHResult(),
            LocalSpoolerTelemetry::WriteDbgTraceError(
              "SplFindCompatibleDriver",
              L"SetupDiBuildDriverInfoList failed with error code hr: 0x%x",
              LastErrorAsHResult),
            (int)LastErrorAsHResult >= 0) )
      {
        if ( SetupDiCallClassInstaller(0x17u, (HDEVINFO)DeviceInfoList, &DeviceInfoData)
          || (LastErrorAsHResult = (BYTE *)(unsigned int)GetLastErrorAsHResult(),
              LocalSpoolerTelemetry::WriteDbgTraceError(
                "SplFindCompatibleDriver",
                L"SetupDiCallClassInstaller failed with error code hr: 0x%x",
                LastErrorAsHResult),
              (int)LastErrorAsHResult >= 0) )
        {
          DriverInfoData.cbSize = 1568;
          if ( SetupDiGetSelectedDriverW((HDEVINFO)DeviceInfoList, &DeviceInfoData, &DriverInfoData)
            || (LastErrorAsHResult = (BYTE *)(unsigned int)GetLastErrorAsHResult(),
                LocalSpoolerTelemetry::WriteDbgTraceError(
                  "SplFindCompatibleDriver",
                  L"SetupDiGetSelectedDriver failed with error code hr: 0x%x",
                  LastErrorAsHResult),
                (int)LastErrorAsHResult >= 0) )
          {
            DriverInstallParams.cbSize = 32;
            if ( SetupDiGetDriverInstallParamsW(
                   (HDEVINFO)DeviceInfoList,
                   &DeviceInfoData,
                   &DriverInfoData,
                   &DriverInstallParams) )
            {
              if ( (DriverInstallParams.Rank & 0x80000FFF) == 0 )
                *a9 = 1;
              v16 = 0;
              LODWORD(LastErrorAsHResult) = StringCchLengthW(DriverInfoData.MfgName, 0x7FFFFFFFu, &v16);
              *v19 = v16 + 1;
              if ( (int)LastErrorAsHResult >= 0 )
              {
                v16 = 0;
                LODWORD(LastErrorAsHResult) = StringCchLengthW(DriverInfoData.Description, v14, &v16);
                **(_DWORD **)&v18[1] = v16 + 1;
                if ( (int)LastErrorAsHResult >= 0 )
                {
                  if ( !a6
                    || (LODWORD(LastErrorAsHResult) = StringCchCopyW(a6, a7, DriverInfoData.Description),
                        (int)LastErrorAsHResult >= 0) )
                  {
                    if ( a3 )
                      LODWORD(LastErrorAsHResult) = StringCchCopyW(a3, v18[0], DriverInfoData.MfgName);
                  }
                }
              }
            }
            else
            {
              LastErrorAsHResult = (BYTE *)(unsigned int)GetLastErrorAsHResult();
              LocalSpoolerTelemetry::WriteDbgTraceError(
                "SplFindCompatibleDriver",
                L"SetupDiGetDriverInstallParams failed with error code hr: 0x%x",
                LastErrorAsHResult);
            }
          }
        }
      }
    }
  }
  else
  {
    DeviceInfoList = -1;
    LODWORD(LastErrorAsHResult) = -2147024809;
  }
LABEL_31:
  SetupDiDestroyDriverInfoList((HDEVINFO)DeviceInfoList, 0, 1u);
  if ( v17 )
    SetupDiDeleteDeviceInfo((HDEVINFO)DeviceInfoList, &DeviceInfoData);
  if ( (unsigned __int64)(DeviceInfoList - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    SetupDiDestroyDeviceInfoList((HDEVINFO)DeviceInfoList);
  return (unsigned int)LastErrorAsHResult;
}

```

## disassembly

```asm
0x1800bd740  push    rbp
0x1800bd742  push    rbx
0x1800bd743  push    rsi
0x1800bd744  push    rdi
0x1800bd745  push    r12
0x1800bd747  push    r13
0x1800bd749  push    r14
0x1800bd74b  push    r15
0x1800bd74d  lea     rbp, [rsp-5B8h]
0x1800bd755  sub     rsp, 6B8h
0x1800bd75c  mov     rax, cs:__security_cookie
0x1800bd763  xor     rax, rsp
0x1800bd766  mov     [rbp+5F0h+var_50], rax
0x1800bd76d  mov     rax, [rbp+5F0h+arg_38]
0x1800bd774  xorps   xmm0, xmm0
0x1800bd777  mov     rdi, [rbp+5F0h+arg_20]
0x1800bd77e  mov     rsi, r8
0x1800bd781  mov     r15, [rbp+5F0h+arg_28]
0x1800bd788  mov     r14, rdx
0x1800bd78b  mov     r13, [rbp+5F0h+arg_40]
0x1800bd792  mov     rbx, rcx
0x1800bd795  mov     [rsp+6F0h+var_6D0], rcx
0x1800bd79a  xor     edx, edx; Val
0x1800bd79c  mov     r8d, 620h; Size
0x1800bd7a2  mov     [rsp+6F0h+var_6B8], rdi
0x1800bd7a7  lea     rcx, [rbp+5F0h+DriverInfoData]; void *
0x1800bd7ab  mov     qword ptr [rsp+6F0h+var_6C4+4], rax
0x1800bd7b0  movups  xmmword ptr [rsp+6F0h+DeviceInfoData.cbSize], xmm0
0x1800bd7b5  mov     r12d, r9d
0x1800bd7b8  mov     dword ptr [rsp+6F0h+var_6C4], r9d
0x1800bd7bd  movups  xmmword ptr [rsp+6F0h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x1800bd7c2  call    memset_0
0x1800bd7c7  mov     [rsp+6F0h+var_6C8], 0
0x1800bd7cf  xorps   xmm0, xmm0
0x1800bd7d2  movups  xmmword ptr [rsp+6F0h+DriverInstallParams.cbSize], xmm0
0x1800bd7d7  movups  xmmword ptr [rsp+6F0h+DriverInstallParams.PrivateData], xmm0
0x1800bd7dc  test    rbx, rbx
0x1800bd7df  jz      loc_1800BDA46
0x1800bd7e5  test    r14, r14
0x1800bd7e8  jz      loc_1800BDA46
0x1800bd7ee  test    rsi, rsi
0x1800bd7f1  jnz     short loc_1800BD7FC
0x1800bd7f3  test    r12d, r12d
0x1800bd7f6  jnz     loc_1800BDA46
0x1800bd7fc  mov     r12d, [rbp+5F0h+arg_30]
0x1800bd803  test    r15, r15
0x1800bd806  jnz     short loc_1800BD811
0x1800bd808  test    r12d, r12d
0x1800bd80b  jnz     loc_1800BDA46
0x1800bd811  test    rdi, rdi
0x1800bd814  jz      loc_1800BDA46
0x1800bd81a  cmp     qword ptr [rsp+6F0h+var_6C4+4], 0
0x1800bd820  jz      loc_1800BDA46
0x1800bd826  test    r13, r13
0x1800bd829  jz      loc_1800BDA46
0x1800bd82f  xor     edx, edx; hwndParent
0x1800bd831  lea     rcx, GUID_DEVCLASS_PRINTER; ClassGuid
0x1800bd838  call    cs:__imp_SetupDiCreateDeviceInfoList
0x1800bd83e  mov     rdi, rax
0x1800bd841  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800bd845  jnz     short loc_1800BD871
0x1800bd847  call    GetLastErrorAsHResult
0x1800bd84c  mov     r8d, eax
0x1800bd84f  lea     rdx, aSetupdicreated_3; "SetupDiCreateDeviceInfoList failed with"...
0x1800bd856  lea     rcx, aSplfindcompati; "SplFindCompatibleDriver"
0x1800bd85d  mov     ebx, eax
0x1800bd85f  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800bd864  test    ebx, ebx
0x1800bd866  js      loc_1800BDA4F
0x1800bd86c  mov     rbx, [rsp+6F0h+var_6D0]
0x1800bd871  lea     r9, [rsp+6F0h+DeviceInfoData]; DeviceInfoData
0x1800bd876  mov     r8, r14; lpData
0x1800bd879  mov     rdx, rbx; PropertyBuffer
0x1800bd87c  mov     rcx, rdi; DeviceInfoSet
0x1800bd87f  call    ?PSetupCreateDevInfoFromPnpID@@YAJPEAXPEBG1PEAU_SP_DEVINFO_DATA@@@Z; PSetupCreateDevInfoFromPnpID(void *,ushort const *,ushort const *,_SP_DEVINFO_DATA *)
0x1800bd884  mov     ebx, eax
0x1800bd886  test    eax, eax
0x1800bd888  js      loc_1800BDA4F
0x1800bd88e  mov     r8d, 2; DriverType
0x1800bd894  mov     [rsp+6F0h+var_6C8], 1
0x1800bd89c  lea     rdx, [rsp+6F0h+DeviceInfoData]; DeviceInfoData
0x1800bd8a1  mov     rcx, rdi; DeviceInfoSet
0x1800bd8a4  call    cs:__imp_SetupDiBuildDriverInfoList
0x1800bd8aa  test    eax, eax
0x1800bd8ac  jnz     short loc_1800BD8D3
0x1800bd8ae  call    GetLastErrorAsHResult
0x1800bd8b3  mov     r8d, eax
0x1800bd8b6  lea     rdx, aSetupdibuilddr_0; "SetupDiBuildDriverInfoList failed with "...
0x1800bd8bd  lea     rcx, aSplfindcompati; "SplFindCompatibleDriver"
0x1800bd8c4  mov     ebx, eax
0x1800bd8c6  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800bd8cb  test    ebx, ebx
0x1800bd8cd  js      loc_1800BDA4F
0x1800bd8d3  lea     r8, [rsp+6F0h+DeviceInfoData]; DeviceInfoData
0x1800bd8d8  mov     rdx, rdi; DeviceInfoSet
0x1800bd8db  mov     ecx, 17h; InstallFunction
0x1800bd8e0  call    cs:__imp_SetupDiCallClassInstaller
0x1800bd8e6  test    eax, eax
0x1800bd8e8  jnz     short loc_1800BD90F
0x1800bd8ea  call    GetLastErrorAsHResult
0x1800bd8ef  mov     r8d, eax
0x1800bd8f2  lea     rdx, aSetupdicallcla_0; "SetupDiCallClassInstaller failed with e"...
0x1800bd8f9  lea     rcx, aSplfindcompati; "SplFindCompatibleDriver"
0x1800bd900  mov     ebx, eax
0x1800bd902  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800bd907  test    ebx, ebx
0x1800bd909  js      loc_1800BDA4F
0x1800bd90f  lea     r8, [rbp+5F0h+DriverInfoData]; DriverInfoData
0x1800bd913  mov     [rbp+5F0h+DriverInfoData.cbSize], 620h
0x1800bd91a  lea     rdx, [rsp+6F0h+DeviceInfoData]; DeviceInfoData
0x1800bd91f  mov     rcx, rdi; DeviceInfoSet
0x1800bd922  call    cs:__imp_SetupDiGetSelectedDriverW
0x1800bd928  test    eax, eax
0x1800bd92a  jnz     short loc_1800BD951
0x1800bd92c  call    GetLastErrorAsHResult
0x1800bd931  mov     r8d, eax
0x1800bd934  lea     rdx, aSetupdigetsele_0; "SetupDiGetSelectedDriver failed with er"...
0x1800bd93b  lea     rcx, aSplfindcompati; "SplFindCompatibleDriver"
0x1800bd942  mov     ebx, eax
0x1800bd944  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800bd949  test    ebx, ebx
0x1800bd94b  js      loc_1800BDA4F
0x1800bd951  lea     r9, [rsp+6F0h+DriverInstallParams]; DriverInstallParams
0x1800bd956  mov     [rsp+6F0h+DriverInstallParams.cbSize], 20h ; ' '
0x1800bd95e  lea     r8, [rbp+5F0h+DriverInfoData]; DriverInfoData
0x1800bd962  mov     rcx, rdi; DeviceInfoSet
0x1800bd965  lea     rdx, [rsp+6F0h+DeviceInfoData]; DeviceInfoData
0x1800bd96a  call    cs:__imp_SetupDiGetDriverInstallParamsW
0x1800bd970  test    eax, eax
0x1800bd972  jz      loc_1800BDA27
0x1800bd978  test    [rsp+6F0h+DriverInstallParams.Rank], 80000FFFh
0x1800bd980  jnz     short loc_1800BD98A
0x1800bd982  mov     dword ptr [r13+0], 1
0x1800bd98a  mov     r10d, 7FFFFFFFh
0x1800bd990  mov     [rsp+6F0h+var_6D0], 0
0x1800bd999  mov     edx, r10d; unsigned __int64
0x1800bd99c  lea     r8, [rsp+6F0h+var_6D0]; unsigned __int64 *
0x1800bd9a1  lea     rcx, [rbp+5F0h+DriverInfoData.MfgName]; unsigned __int16 *
0x1800bd9a8  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800bd9ad  mov     rcx, [rsp+6F0h+var_6B8]
0x1800bd9b2  mov     ebx, eax
0x1800bd9b4  mov     eax, dword ptr [rsp+6F0h+var_6D0]
0x1800bd9b8  inc     eax
0x1800bd9ba  mov     [rcx], eax
0x1800bd9bc  test    ebx, ebx
0x1800bd9be  js      loc_1800BDA4F
0x1800bd9c4  lea     r8, [rsp+6F0h+var_6D0]; unsigned __int64 *
0x1800bd9c9  mov     [rsp+6F0h+var_6D0], 0
0x1800bd9d2  mov     edx, r10d; unsigned __int64
0x1800bd9d5  lea     rcx, [rbp+5F0h+DriverInfoData.Description]; unsigned __int16 *
0x1800bd9d9  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800bd9de  mov     rcx, qword ptr [rsp+6F0h+var_6C4+4]
0x1800bd9e3  mov     ebx, eax
0x1800bd9e5  mov     eax, dword ptr [rsp+6F0h+var_6D0]
0x1800bd9e9  inc     eax
0x1800bd9eb  mov     [rcx], eax
0x1800bd9ed  test    ebx, ebx
0x1800bd9ef  js      short loc_1800BDA4F
0x1800bd9f1  test    r15, r15
0x1800bd9f4  jz      short loc_1800BDA0B
0x1800bd9f6  mov     rdx, r12; unsigned __int64
0x1800bd9f9  lea     r8, [rbp+5F0h+DriverInfoData.Description]; unsigned __int16 *
0x1800bd9fd  mov     rcx, r15; unsigned __int16 *
0x1800bda00  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800bda05  mov     ebx, eax
0x1800bda07  test    eax, eax
0x1800bda09  js      short loc_1800BDA4F
0x1800bda0b  test    rsi, rsi
0x1800bda0e  jz      short loc_1800BDA4F
0x1800bda10  mov     edx, dword ptr [rsp+6F0h+var_6C4]; unsigned __int64
0x1800bda14  lea     r8, [rbp+5F0h+DriverInfoData.MfgName]; unsigned __int16 *
0x1800bda1b  mov     rcx, rsi; unsigned __int16 *
0x1800bda1e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800bda23  mov     ebx, eax
0x1800bda25  jmp     short loc_1800BDA4F
0x1800bda27  call    GetLastErrorAsHResult
0x1800bda2c  mov     r8d, eax
0x1800bda2f  lea     rdx, aSetupdigetdriv_0; "SetupDiGetDriverInstallParams failed wi"...
0x1800bda36  lea     rcx, aSplfindcompati; "SplFindCompatibleDriver"
0x1800bda3d  mov     ebx, eax
0x1800bda3f  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800bda44  jmp     short loc_1800BDA4F
0x1800bda46  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800bda4a  mov     ebx, 80070057h
0x1800bda4f  xor     edx, edx; DeviceInfoData
0x1800bda51  mov     rcx, rdi; DeviceInfoSet
0x1800bda54  lea     r8d, [rdx+1]; DriverType
0x1800bda58  call    cs:__imp_SetupDiDestroyDriverInfoList
0x1800bda5e  cmp     [rsp+6F0h+var_6C8], 0
0x1800bda63  jz      short loc_1800BDA73
0x1800bda65  lea     rdx, [rsp+6F0h+DeviceInfoData]; DeviceInfoData
0x1800bda6a  mov     rcx, rdi; DeviceInfoSet
0x1800bda6d  call    cs:__imp_SetupDiDeleteDeviceInfo
0x1800bda73  lea     rax, [rdi-1]
0x1800bda77  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800bda7b  ja      short loc_1800BDA86
0x1800bda7d  mov     rcx, rdi; DeviceInfoSet
0x1800bda80  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x1800bda86  mov     eax, ebx
0x1800bda88  mov     rcx, [rbp+5F0h+var_50]
0x1800bda8f  xor     rcx, rsp; StackCookie
0x1800bda92  call    __security_check_cookie
0x1800bda97  add     rsp, 6B8h
0x1800bda9e  pop     r15
0x1800bdaa0  pop     r14
0x1800bdaa2  pop     r13
0x1800bdaa4  pop     r12
0x1800bdaa6  pop     rdi
0x1800bdaa7  pop     rsi
0x1800bdaa8  pop     rbx
0x1800bdaa9  pop     rbp
0x1800bdaaa  retn
```
