# GetInfAndBuildDrivers

- ea: `0x18001de14`
- end: `0x18001e076`
- name: `GetInfAndBuildDrivers`
- size: `610`
- prototype: `__int64 __usercall@<rax>(HWND hWnd@<rcx>, UINT uID@<edx>, char, int, int, LPCWSTR, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x18000b498`

## callees

- `0x18000db24`
- `0x180017c50`
- `0x18001afa8`
- `0x18001de14`
- `0x18001e470`
- `0x1800211e0`
- `0x180026634`
- `0x180026820`
- `0x180026ed4`
- `0x180027e90`
- `0x1800284d0`
- `0x180028a24`
- `0x180035ef8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e036`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e05e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e036`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e05e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001df38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dfaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001df38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dfaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e024`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e043`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e051`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e043`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e051`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x18001de7a`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x18001de7a`
- `SETUPAPI!SetupDiDestroyDriverInfoList` at `0x18001dfd9`
- `SETUPAPI!SetupDiDestroyDriverInfoList` at `0x18001dfd9`

## pseudocode

```c
__int64 __fastcall GetInfAndBuildDrivers(
        HWND hWnd,
        UINT uID,
        __int64 a3,
        WCHAR *a4,
        char a5,
        unsigned int a6,
        unsigned int a7,
        LPCWSTR a8,
        WCHAR *a9,
        _QWORD *a10)
{
  __int64 v10; // rdi
  DWORD v13; // ecx
  WCHAR *StringFromRcFile; // r14
  WCHAR *v15; // rsi
  char *DeviceInfoList; // rax
  bool v17; // zf
  int v18; // eax
  _QWORD *v19; // rax
  DWORD LastError; // ebx

  v10 = -1;
  if ( !uID )
  {
    v13 = 87;
    goto LABEL_31;
  }
  if ( (a5 & 8) != 0 )
  {
    v13 = 2;
LABEL_31:
    SetLastError(v13);
    return v10;
  }
  StringFromRcFile = (WCHAR *)GetStringFromRcFile(uID);
  if ( StringFromRcFile )
  {
    v15 = (WCHAR *)GetStringFromRcFile(0x403u);
    if ( v15 )
    {
      DeviceInfoList = (char *)SetupDiCreateDeviceInfoList(&GUID_DEVCLASS_PRINTER, hWnd);
      v10 = (__int64)DeviceInfoList;
      if ( DeviceInfoList != (char *)-1LL )
      {
        if ( (unsigned int)PSetupSetDriverPlatform(DeviceInfoList, a6, 0, a9, 0, 0) )
        {
          GetCDRomDrive(a4);
          while ( (unsigned int)PSetupGetPathToSearch(hWnd, StringFromRcFile, v15, L"*.inf", 1, a4) )
          {
            if ( (unsigned int)CheckInfPath(hWnd, a4, a7, a6) )
            {
LABEL_11:
              if ( !SetDevInstallParams((HDEVINFO)v10, 0, a4) )
                break;
              if ( (unsigned int)BuildClassDriverList((HDEVINFO)v10) )
              {
                if ( !a8 || !a10 )
                  goto LABEL_28;
                v18 = IsInInfDir((__int64)a4);
                if ( (unsigned int)PreSelectDriverEx((void *)v10, 0, a8, v18, a6, 0) )
                {
                  v19 = BuildInternalData((void *)v10, 0, a6);
                  *a10 = v19;
                  if ( v19 )
                    goto LABEL_28;
                }
                else
                {
                  *a10 = 0;
                }
                v17 = GetLastError() == 1797;
              }
              else
              {
                v17 = GetLastError() == -2146500076;
              }
              if ( v17 && (unsigned int)RetryGetInf(hWnd, a8) )
              {
                SetupDiDestroyDriverInfoList((HDEVINFO)v10, 0, 1u);
                while ( (unsigned int)PSetupGetPathToSearch(hWnd, StringFromRcFile, v15, L"*.inf", 1, a4) )
                {
                  if ( (unsigned int)CheckInfPath(hWnd, a4, a7, a6) )
                    goto LABEL_11;
                }
              }
              break;
            }
          }
        }
        LastError = GetLastError();
        DestroyOnlyPrinterDeviceInfoList(v10);
        SetLastError(LastError);
        v10 = -1;
      }
    }
LABEL_28:
    LocalFree(StringFromRcFile);
    if ( v15 )
      LocalFree(v15);
  }
  return v10;
}

```

## disassembly

```asm
0x18001de14  push    rbx
0x18001de16  push    rbp
0x18001de17  push    rsi
0x18001de18  push    rdi
0x18001de19  push    r12
0x18001de1b  push    r13
0x18001de1d  push    r14
0x18001de1f  sub     rsp, 30h
0x18001de23  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001de27  mov     rbp, r9
0x18001de2a  mov     rbx, rcx
0x18001de2d  test    edx, edx
0x18001de2f  jz      loc_18001E059
0x18001de35  test    [rsp+68h+arg_20], 8
0x18001de3d  jz      short loc_18001DE47
0x18001de3f  lea     ecx, [rdi+3]
0x18001de42  jmp     loc_18001E05E
0x18001de47  mov     ecx, edx; uID
0x18001de49  call    GetStringFromRcFile
0x18001de4e  mov     r14, rax
0x18001de51  test    rax, rax
0x18001de54  jz      loc_18001E064
0x18001de5a  mov     ecx, 403h; uID
0x18001de5f  call    GetStringFromRcFile
0x18001de64  mov     rsi, rax
0x18001de67  test    rax, rax
0x18001de6a  jz      loc_18001E040
0x18001de70  mov     rdx, rbx; hwndParent
0x18001de73  lea     rcx, GUID_DEVCLASS_PRINTER; ClassGuid
0x18001de7a  call    cs:__imp_SetupDiCreateDeviceInfoList
0x18001de80  mov     rdi, rax
0x18001de83  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001de87  jz      loc_18001E040
0x18001de8d  mov     r12d, [rsp+68h+arg_28]
0x18001de95  xor     r8d, r8d
0x18001de98  mov     r9, [rsp+68h+arg_40]
0x18001dea0  mov     edx, r12d
0x18001dea3  mov     [rsp+68h+var_40], 0; int
0x18001deab  mov     rcx, rax; DeviceInfoSet
0x18001deae  mov     [rsp+68h+var_48], 0; int
0x18001deb6  call    PSetupSetDriverPlatform
0x18001debb  test    eax, eax
0x18001debd  jz      loc_18001E024
0x18001dec3  mov     r13, [rsp+68h+arg_48]
0x18001decb  mov     rcx, rbp; lpRootPathName
0x18001dece  call    GetCDRomDrive
0x18001ded3  mov     qword ptr [rsp+68h+var_40], rbp
0x18001ded8  lea     r9, aInf_3; "*.inf"
0x18001dedf  mov     r8, rsi
0x18001dee2  mov     [rsp+68h+var_48], 1
0x18001deea  mov     rdx, r14
0x18001deed  mov     rcx, rbx
0x18001def0  call    PSetupGetPathToSearch
0x18001def5  test    eax, eax
0x18001def7  jz      loc_18001E024
0x18001defd  mov     r8d, [rsp+68h+arg_30]
0x18001df05  mov     r9d, r12d
0x18001df08  mov     rdx, rbp
0x18001df0b  mov     rcx, rbx
0x18001df0e  call    ?CheckInfPath@@YAHPEAUHWND__@@PEAGKW4PLATFORM@@@Z; CheckInfPath(HWND__ *,ushort *,ulong,PLATFORM)
0x18001df13  test    eax, eax
0x18001df15  jz      short loc_18001DED3
0x18001df17  mov     r8, rbp; unsigned __int16 *
0x18001df1a  xor     edx, edx; DeviceInfoData
0x18001df1c  mov     rcx, rdi; DeviceInfoSet
0x18001df1f  call    SetDevInstallParams
0x18001df24  test    eax, eax
0x18001df26  jz      loc_18001E024
0x18001df2c  mov     rcx, rdi; DeviceInfoSet
0x18001df2f  call    BuildClassDriverList
0x18001df34  test    eax, eax
0x18001df36  jnz     short loc_18001DF45
0x18001df38  call    cs:__imp_GetLastError
0x18001df3e  cmp     eax, 800F0214h
0x18001df43  jmp     short loc_18001DFBA
0x18001df45  cmp     [rsp+68h+arg_38], 0
0x18001df4e  jz      loc_18001E040
0x18001df54  test    r13, r13
0x18001df57  jz      loc_18001E040
0x18001df5d  mov     rcx, rbp
0x18001df60  call    IsInInfDir
0x18001df65  mov     r8, [rsp+68h+arg_38]; LPCWSTR
0x18001df6d  mov     r9d, eax
0x18001df70  xor     edx, edx; lpString1
0x18001df72  mov     [rsp+68h+var_40], 0; int
0x18001df7a  mov     rcx, rdi; int
0x18001df7d  mov     [rsp+68h+var_48], r12d; int
0x18001df82  call    PreSelectDriverEx
0x18001df87  test    eax, eax
0x18001df89  jz      short loc_18001DFA7
0x18001df8b  mov     r8d, r12d
0x18001df8e  xor     edx, edx; int
0x18001df90  mov     rcx, rdi; int
0x18001df93  call    BuildInternalData
0x18001df98  mov     [r13+0], rax
0x18001df9c  test    rax, rax
0x18001df9f  jnz     loc_18001E040
0x18001dfa5  jmp     short loc_18001DFAF
0x18001dfa7  mov     qword ptr [r13+0], 0
0x18001dfaf  call    cs:__imp_GetLastError
0x18001dfb5  cmp     eax, 705h
0x18001dfba  jnz     short loc_18001E024
0x18001dfbc  mov     rdx, [rsp+68h+arg_38]; unsigned __int16 *
0x18001dfc4  mov     rcx, rbx; hWnd
0x18001dfc7  call    ?RetryGetInf@@YAHPEAUHWND__@@PEBG@Z; RetryGetInf(HWND__ *,ushort const *)
0x18001dfcc  test    eax, eax
0x18001dfce  jz      short loc_18001E024
0x18001dfd0  xor     edx, edx; DeviceInfoData
0x18001dfd2  mov     rcx, rdi; DeviceInfoSet
0x18001dfd5  lea     r8d, [rdx+1]; DriverType
0x18001dfd9  call    cs:__imp_SetupDiDestroyDriverInfoList
0x18001dfdf  mov     qword ptr [rsp+68h+var_40], rbp
0x18001dfe4  lea     r9, aInf_3; "*.inf"
0x18001dfeb  mov     r8, rsi
0x18001dfee  mov     [rsp+68h+var_48], 1
0x18001dff6  mov     rdx, r14
0x18001dff9  mov     rcx, rbx
0x18001dffc  call    PSetupGetPathToSearch
0x18001e001  test    eax, eax
0x18001e003  jz      short loc_18001E024
0x18001e005  mov     r8d, [rsp+68h+arg_30]
0x18001e00d  mov     r9d, r12d
0x18001e010  mov     rdx, rbp
0x18001e013  mov     rcx, rbx
0x18001e016  call    ?CheckInfPath@@YAHPEAUHWND__@@PEAGKW4PLATFORM@@@Z; CheckInfPath(HWND__ *,ushort *,ulong,PLATFORM)
0x18001e01b  test    eax, eax
0x18001e01d  jz      short loc_18001DFDF
0x18001e01f  jmp     loc_18001DF17
0x18001e024  call    cs:__imp_GetLastError
0x18001e02a  mov     rcx, rdi
0x18001e02d  mov     ebx, eax
0x18001e02f  call    DestroyOnlyPrinterDeviceInfoList
0x18001e034  mov     ecx, ebx; dwErrCode
0x18001e036  call    cs:__imp_SetLastError
0x18001e03c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001e040  mov     rcx, r14; hMem
0x18001e043  call    cs:__imp_LocalFree
0x18001e049  test    rsi, rsi
0x18001e04c  jz      short loc_18001E064
0x18001e04e  mov     rcx, rsi; hMem
0x18001e051  call    cs:__imp_LocalFree
0x18001e057  jmp     short loc_18001E064
0x18001e059  mov     ecx, 57h ; 'W'; dwErrCode
0x18001e05e  call    cs:__imp_SetLastError
0x18001e064  mov     rax, rdi
0x18001e067  add     rsp, 30h
0x18001e06b  pop     r14
0x18001e06d  pop     r13
0x18001e06f  pop     r12
0x18001e071  pop     rdi
0x18001e072  pop     rsi
0x18001e073  pop     rbp
0x18001e074  pop     rbx
0x18001e075  retn
```
