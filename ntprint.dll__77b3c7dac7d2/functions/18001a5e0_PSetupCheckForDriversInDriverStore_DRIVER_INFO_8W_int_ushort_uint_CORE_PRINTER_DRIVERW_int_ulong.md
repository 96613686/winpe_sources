# PSetupCheckForDriversInDriverStore(_DRIVER_INFO_8W *,int *,ushort *,uint,_CORE_PRINTER_DRIVERW *,int *,ulong)

- ea: `0x18001a5e0`
- end: `0x18001a90b`
- name: `?PSetupCheckForDriversInDriverStore@@YAJPEAU_DRIVER_INFO_8W@@PEAHPEAGIPEAU_CORE_PRINTER_DRIVERW@@1K@Z`
- size: `811`
- prototype: `__int64 __fastcall(struct _DRIVER_INFO_8W *, int *, unsigned __int16 *, unsigned int, struct _CORE_PRINTER_DRIVERW *, int *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000b200`
- `0x1800180f0`
- `0x18001a5e0`
- `0x18001e264`
- `0x180026c04`
- `0x180026ed4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a8c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a8c9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a6ee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a6ee`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x18001a781`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x18001a781`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a8b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a8b9`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18001a73e`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18001a73e`

## pseudocode

```c
__int64 __fastcall PSetupCheckForDriversInDriverStore(
        struct _DRIVER_INFO_8W *a1,
        int *a2,
        unsigned __int16 *a3,
        int a4,
        struct _CORE_PRINTER_DRIVERW *a5,
        int *a6,
        unsigned int a7)
{
  int *v7; // rdi
  const WCHAR *pEnvironment; // rcx
  int PlatformFromEnvironmentString; // ebx
  HLOCAL v10; // rsi
  NCoreLibrary *v11; // rcx
  __int64 v12; // rdi
  DWORD v13; // r12d
  int v14; // r15d
  __int64 v15; // rdi
  int *v16; // r12
  __int64 i; // rdi
  void *v18; // rcx
  unsigned int v20; // [rsp+50h] [rbp-B0h] BYREF
  HDEVINFO DeviceInfoSet; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v22; // [rsp+60h] [rbp-A0h]
  int v23; // [rsp+64h] [rbp-9Ch]
  int *v24; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v25; // [rsp+70h] [rbp-90h]
  struct _DRIVER_INFO_8W *v26; // [rsp+78h] [rbp-88h]
  int *v27; // [rsp+80h] [rbp-80h]
  struct _CORE_PRINTER_DRIVERW *v28; // [rsp+88h] [rbp-78h]
  struct _SP_DRVINFO_DATA_V2_W DriverInfoData; // [rsp+90h] [rbp-70h] BYREF

  v7 = a2;
  v28 = a5;
  v27 = a6;
  v23 = a4;
  v25 = a3;
  v24 = a2;
  v26 = a1;
  DeviceInfoSet = (HDEVINFO)-1LL;
  v20 = 1;
  if ( !a1 || (pEnvironment = a1->pEnvironment) == 0 || !a2 || !a3 || !a4 || a7 && (!a5 || !a6) )
    return (unsigned int)-2147024809;
  PlatformFromEnvironmentString = GetPlatformFromEnvironmentString(pEnvironment, &v20);
  if ( PlatformFromEnvironmentString >= 0 )
  {
    PlatformFromEnvironmentString = CreateAndBuildDriverList(v20, (__int64 *)&DeviceInfoSet);
    if ( PlatformFromEnvironmentString >= 0 )
    {
      memset_0(&DriverInfoData.DriverType, 0, 0x61Cu);
      v10 = 0;
      DriverInfoData.cbSize = 1568;
      if ( !a7 )
        goto LABEL_21;
      v10 = LocalAlloc(0x40u, 8 * a7);
      if ( v10 )
      {
        PlatformFromEnvironmentString = 0;
        goto LABEL_15;
      }
      PlatformFromEnvironmentString = NCoreLibrary::GetLastErrorAsFailHR(v11);
      if ( PlatformFromEnvironmentString >= 0 )
      {
LABEL_15:
        memset_0(v10, 0, 8LL * a7);
        v12 = 0;
        do
        {
          if ( (unsigned int)v12 >= a7 )
            break;
          if ( !a6[v12] )
            PlatformFromEnvironmentString = StringFromIID(&a5[(unsigned int)v12].CoreDriverGUID, (LPOLESTR *)v10 + v12);
          v12 = (unsigned int)(v12 + 1);
        }
        while ( PlatformFromEnvironmentString >= 0 );
        v7 = v24;
LABEL_21:
        v13 = 0;
        v14 = 0;
        while ( 1 )
        {
          v22 = v13;
          if ( PlatformFromEnvironmentString < 0 )
            break;
          if ( v14 )
            break;
          v14 = 1;
          if ( !SetupDiEnumDriverInfoW(DeviceInfoSet, 0, 1u, v13, &DriverInfoData) )
            break;
          if ( !*v7 )
          {
            PlatformFromEnvironmentString = DriverFoundInDriverStore(
                                              DeviceInfoSet,
                                              v26->pName,
                                              v20,
                                              *(_QWORD *)&v26->ftDriverDate,
                                              v26->dwlDriverVersion,
                                              &DriverInfoData,
                                              v25,
                                              v23,
                                              v7);
            if ( PlatformFromEnvironmentString >= 0 && !*v7 )
            {
              v14 = 0;
              v15 = 0;
              goto LABEL_29;
            }
          }
          v15 = 0;
          if ( PlatformFromEnvironmentString >= 0 )
          {
LABEL_29:
            while ( (unsigned int)v15 < a7 )
            {
              v16 = &v27[v15];
              if ( *v16
                || (PlatformFromEnvironmentString = DriverFoundInDriverStore(
                                                      DeviceInfoSet,
                                                      *((_QWORD *)v10 + v15),
                                                      v20,
                                                      *(_QWORD *)&v28[(unsigned int)v15].ftDriverDate,
                                                      v28[(unsigned int)v15].dwlDriverVersion,
                                                      &DriverInfoData,
                                                      v28[(unsigned int)v15].szPackageID,
                                                      260,
                                                      &v27[v15]),
                    PlatformFromEnvironmentString < 0)
                || *v16 )
              {
                v15 = (unsigned int)(v15 + 1);
                if ( PlatformFromEnvironmentString < 0 )
                  break;
              }
              else
              {
                v14 = 0;
                v15 = (unsigned int)(v15 + 1);
              }
            }
            v13 = v22;
          }
          v7 = v24;
          ++v13;
          DriverInfoData.cbSize = 1568;
        }
        if ( v10 )
        {
          for ( i = 0; (unsigned int)i < a7; i = (unsigned int)(i + 1) )
          {
            v18 = (void *)*((_QWORD *)v10 + i);
            if ( v18 )
              CoTaskMemFree(v18);
          }
          LocalFree(v10);
        }
      }
    }
    if ( DeviceInfoSet != (HDEVINFO)-1LL )
      DestroyOnlyPrinterDeviceInfoList(DeviceInfoSet);
  }
  return (unsigned int)PlatformFromEnvironmentString;
}

```

## disassembly

```asm
0x18001a5e0  push    rbp
0x18001a5e2  push    rbx
0x18001a5e3  push    rsi
0x18001a5e4  push    rdi
0x18001a5e5  push    r12
0x18001a5e7  push    r14
0x18001a5e9  push    r15
0x18001a5eb  lea     rbp, [rsp-5C0h]
0x18001a5f3  sub     rsp, 6C0h
0x18001a5fa  mov     rax, cs:__security_cookie
0x18001a601  xor     rax, rsp
0x18001a604  mov     [rbp+5F0h+var_40], rax
0x18001a60b  mov     r12, [rbp+5F0h+arg_20]
0x18001a612  mov     rdi, rdx
0x18001a615  mov     r15, [rbp+5F0h+arg_28]
0x18001a61c  mov     r14d, [rbp+5F0h+arg_30]
0x18001a623  mov     [rbp+5F0h+var_668], r12
0x18001a627  mov     [rbp+5F0h+var_670], r15
0x18001a62b  mov     [rsp+6F0h+var_68C], r9d
0x18001a630  mov     [rsp+6F0h+var_680], r8
0x18001a635  mov     [rsp+6F0h+var_688], rdx
0x18001a63a  mov     [rsp+6F0h+var_678], rcx
0x18001a63f  mov     [rsp+6F0h+DeviceInfoSet], 0FFFFFFFFFFFFFFFFh
0x18001a648  mov     [rsp+6F0h+var_6A0], 1
0x18001a650  test    rcx, rcx
0x18001a653  jz      loc_18001A8E3
0x18001a659  mov     rcx, [rcx+10h]; lpString1
0x18001a65d  test    rcx, rcx
0x18001a660  jz      loc_18001A8E3
0x18001a666  test    rdx, rdx
0x18001a669  jz      loc_18001A8E3
0x18001a66f  test    r8, r8
0x18001a672  jz      loc_18001A8E3
0x18001a678  test    r9d, r9d
0x18001a67b  jz      loc_18001A8E3
0x18001a681  test    r14d, r14d
0x18001a684  jz      short loc_18001A698
0x18001a686  test    r12, r12
0x18001a689  jz      loc_18001A8E3
0x18001a68f  test    r15, r15
0x18001a692  jz      loc_18001A8E3
0x18001a698  lea     rdx, [rsp+6F0h+var_6A0]
0x18001a69d  call    GetPlatformFromEnvironmentString
0x18001a6a2  mov     ebx, eax
0x18001a6a4  test    eax, eax
0x18001a6a6  js      loc_18001A8E8
0x18001a6ac  mov     ecx, [rsp+6F0h+var_6A0]
0x18001a6b0  lea     rdx, [rsp+6F0h+DeviceInfoSet]
0x18001a6b5  call    CreateAndBuildDriverList
0x18001a6ba  mov     ebx, eax
0x18001a6bc  test    eax, eax
0x18001a6be  js      loc_18001A8CF
0x18001a6c4  xor     edx, edx; Val
0x18001a6c6  lea     rcx, [rbp+5F0h+var_660.DriverType]; void *
0x18001a6ca  mov     r8d, 61Ch; Size
0x18001a6d0  call    memset_0
0x18001a6d5  xor     esi, esi
0x18001a6d7  mov     [rbp+5F0h+var_660.cbSize], 620h
0x18001a6de  test    r14d, r14d
0x18001a6e1  jz      short loc_18001A751
0x18001a6e3  lea     edx, ds:0[r14*8]; uBytes
0x18001a6eb  lea     ecx, [rsi+40h]; uFlags
0x18001a6ee  call    cs:__imp_LocalAlloc
0x18001a6f4  mov     rsi, rax
0x18001a6f7  test    rax, rax
0x18001a6fa  jz      short loc_18001A700
0x18001a6fc  xor     ebx, ebx
0x18001a6fe  jmp     short loc_18001A70F
0x18001a700  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18001a705  mov     ebx, eax
0x18001a707  test    eax, eax
0x18001a709  js      loc_18001A8CF
0x18001a70f  mov     r8, r14
0x18001a712  xor     edx, edx; Val
0x18001a714  shl     r8, 3; Size
0x18001a718  mov     rcx, rsi; void *
0x18001a71b  call    memset_0
0x18001a720  xor     edi, edi
0x18001a722  cmp     edi, r14d
0x18001a725  jnb     short loc_18001A74C
0x18001a727  cmp     dword ptr [r15+rdi*4], 0
0x18001a72c  mov     eax, edi
0x18001a72e  jnz     short loc_18001A746
0x18001a730  imul    rcx, rax, 228h
0x18001a737  lea     rdx, [rsi+rdi*8]; lplpsz
0x18001a73b  add     rcx, r12; rclsid
0x18001a73e  call    cs:__imp_StringFromIID
0x18001a744  mov     ebx, eax
0x18001a746  inc     edi
0x18001a748  test    ebx, ebx
0x18001a74a  jns     short loc_18001A722
0x18001a74c  mov     rdi, [rsp+6F0h+var_688]
0x18001a751  xor     r12d, r12d
0x18001a754  xor     r15d, r15d
0x18001a757  jmp     loc_18001A897
0x18001a75c  test    r15d, r15d
0x18001a75f  jnz     loc_18001A8A4
0x18001a765  mov     rcx, [rsp+6F0h+DeviceInfoSet]; DeviceInfoSet
0x18001a76a  lea     rax, [rbp+5F0h+var_660]
0x18001a76e  mov     r15d, 1
0x18001a774  mov     [rsp+6F0h+DriverInfoData], rax; DriverInfoData
0x18001a779  mov     r8d, r15d; DriverType
0x18001a77c  mov     r9d, r12d; MemberIndex
0x18001a77f  xor     edx, edx; DeviceInfoData
0x18001a781  call    cs:__imp_SetupDiEnumDriverInfoW
0x18001a787  test    eax, eax
0x18001a789  jz      loc_18001A8A4
0x18001a78f  cmp     dword ptr [rdi], 0
0x18001a792  jnz     short loc_18001A7EB
0x18001a794  mov     rcx, [rsp+6F0h+var_678]
0x18001a799  mov     eax, [rsp+6F0h+var_68C]
0x18001a79d  mov     r8d, [rsp+6F0h+var_6A0]
0x18001a7a2  mov     [rsp+6F0h+var_6B0], rdi
0x18001a7a7  mov     r9, [rcx+58h]
0x18001a7ab  mov     rdx, [rcx+8]
0x18001a7af  mov     [rsp+6F0h+var_6B8], eax
0x18001a7b3  mov     rax, [rsp+6F0h+var_680]
0x18001a7b8  mov     [rsp+6F0h+var_6C0], rax
0x18001a7bd  lea     rax, [rbp+5F0h+var_660]
0x18001a7c1  mov     [rsp+6F0h+var_6C8], rax
0x18001a7c6  mov     rax, [rcx+60h]
0x18001a7ca  mov     rcx, [rsp+6F0h+DeviceInfoSet]
0x18001a7cf  mov     [rsp+6F0h+DriverInfoData], rax
0x18001a7d4  call    ?DriverFoundInDriverStore@@YAJPEAXPEAGW4PLATFORM@@U_FILETIME@@_KPEAU_SP_DRVINFO_DATA_V2_W@@1KPEAH@Z; DriverFoundInDriverStore(void *,ushort *,PLATFORM,_FILETIME,unsigned __int64,_SP_DRVINFO_DATA_V2_W *,ushort *,ulong,int *)
0x18001a7d9  mov     ebx, eax
0x18001a7db  test    eax, eax
0x18001a7dd  js      short loc_18001A7EB
0x18001a7df  cmp     dword ptr [rdi], 0
0x18001a7e2  jnz     short loc_18001A7EB
0x18001a7e4  xor     r15d, r15d
0x18001a7e7  xor     edi, edi
0x18001a7e9  jmp     short loc_18001A7F5
0x18001a7eb  xor     edi, edi
0x18001a7ed  test    ebx, ebx
0x18001a7ef  js      loc_18001A888
0x18001a7f5  cmp     edi, r14d
0x18001a7f8  jnb     loc_18001A883
0x18001a7fe  mov     rax, [rbp+5F0h+var_670]
0x18001a802  mov     edx, edi
0x18001a804  lea     r12, [rax+rdi*4]
0x18001a808  cmp     dword ptr [r12], 0
0x18001a80d  jnz     short loc_18001A879
0x18001a80f  test    ebx, ebx
0x18001a811  js      short loc_18001A879
0x18001a813  mov     rcx, [rbp+5F0h+var_668]
0x18001a817  mov     r8d, [rsp+6F0h+var_6A0]
0x18001a81c  imul    r9, rdx, 228h
0x18001a823  mov     rdx, [rsi+rdi*8]
0x18001a827  lea     rax, [rcx+20h]
0x18001a82b  add     rax, r9
0x18001a82e  mov     [rsp+6F0h+var_6B0], r12
0x18001a833  mov     [rsp+6F0h+var_6B8], 104h
0x18001a83b  mov     [rsp+6F0h+var_6C0], rax
0x18001a840  lea     rax, [rbp+5F0h+var_660]
0x18001a844  mov     [rsp+6F0h+var_6C8], rax
0x18001a849  mov     rax, [r9+rcx+18h]
0x18001a84e  mov     r9, [r9+rcx+10h]
0x18001a853  mov     rcx, [rsp+6F0h+DeviceInfoSet]
0x18001a858  mov     [rsp+6F0h+DriverInfoData], rax
0x18001a85d  call    ?DriverFoundInDriverStore@@YAJPEAXPEAGW4PLATFORM@@U_FILETIME@@_KPEAU_SP_DRVINFO_DATA_V2_W@@1KPEAH@Z; DriverFoundInDriverStore(void *,ushort *,PLATFORM,_FILETIME,unsigned __int64,_SP_DRVINFO_DATA_V2_W *,ushort *,ulong,int *)
0x18001a862  mov     ebx, eax
0x18001a864  test    eax, eax
0x18001a866  js      short loc_18001A879
0x18001a868  cmp     dword ptr [r12], 0
0x18001a86d  jnz     short loc_18001A879
0x18001a86f  xor     r15d, r15d
0x18001a872  inc     edi
0x18001a874  jmp     loc_18001A7F5
0x18001a879  inc     edi
0x18001a87b  test    ebx, ebx
0x18001a87d  jns     loc_18001A7F5
0x18001a883  mov     r12d, [rsp+6F0h+var_690]
0x18001a888  mov     rdi, [rsp+6F0h+var_688]
0x18001a88d  inc     r12d
0x18001a890  mov     [rbp+5F0h+var_660.cbSize], 620h
0x18001a897  mov     [rsp+6F0h+var_690], r12d
0x18001a89c  test    ebx, ebx
0x18001a89e  jns     loc_18001A75C
0x18001a8a4  test    rsi, rsi
0x18001a8a7  jz      short loc_18001A8CF
0x18001a8a9  xor     edi, edi
0x18001a8ab  test    r14d, r14d
0x18001a8ae  jz      short loc_18001A8C6
0x18001a8b0  mov     rcx, [rsi+rdi*8]; pv
0x18001a8b4  test    rcx, rcx
0x18001a8b7  jz      short loc_18001A8BF
0x18001a8b9  call    cs:__imp_CoTaskMemFree
0x18001a8bf  inc     edi
0x18001a8c1  cmp     edi, r14d
0x18001a8c4  jb      short loc_18001A8B0
0x18001a8c6  mov     rcx, rsi; hMem
0x18001a8c9  call    cs:__imp_LocalFree
0x18001a8cf  cmp     [rsp+6F0h+DeviceInfoSet], 0FFFFFFFFFFFFFFFFh
0x18001a8d5  jz      short loc_18001A8E8
0x18001a8d7  mov     rcx, [rsp+6F0h+DeviceInfoSet]
0x18001a8dc  call    DestroyOnlyPrinterDeviceInfoList
0x18001a8e1  jmp     short loc_18001A8E8
0x18001a8e3  mov     ebx, 80070057h
0x18001a8e8  mov     eax, ebx
0x18001a8ea  mov     rcx, [rbp+5F0h+var_40]
0x18001a8f1  xor     rcx, rsp; StackCookie
0x18001a8f4  call    __security_check_cookie
0x18001a8f9  add     rsp, 6C0h
0x18001a900  pop     r15
0x18001a902  pop     r14
0x18001a904  pop     r12
0x18001a906  pop     rdi
0x18001a907  pop     rsi
0x18001a908  pop     rbx
0x18001a909  pop     rbp
0x18001a90a  retn
```
