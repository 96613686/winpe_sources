# DriverPackageReaderDrvStore::InitDriverPackageHardwareIds(ushort const *,CDriverPackage &)

- ea: `0x180051ee8`
- end: `0x1800521f7`
- name: `?InitDriverPackageHardwareIds@DriverPackageReaderDrvStore@@QEAAJPEBGAEAVCDriverPackage@@@Z`
- size: `783`
- prototype: `__int64 __fastcall(DriverPackageReaderDrvStore *__hidden this, const unsigned __int16 *, struct CDriverPackage *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180052200`

## callees

- `0x180006d02`
- `0x180007014`
- `0x180016598`
- `0x18001f684`
- `0x180051ee8`
- `0x1800538cc`
- `0x18005c8f8`
- `0x18005cc40`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `drvstore!DriverPackageClose` at `0x1800521df`
- `drvstore!DriverPackageClose` at `0x1800521df`
- `drvstore!DriverPackageOpenW` at `0x180051f4b`
- `drvstore!DriverPackageOpenW` at `0x180051f4b`
- `drvstore!DriverPackageEnumDriversW` at `0x18005207b`
- `drvstore!DriverPackageEnumDriversW` at `0x18005218c`
- `drvstore!DriverPackageEnumDriversW` at `0x18005207b`
- `drvstore!DriverPackageEnumDriversW` at `0x18005218c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051f81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051fcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005200c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052089`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800520e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052122`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052138`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051f81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051fcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005200c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052089`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800520e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052122`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052138`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052196`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180051f2f`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180051f2f`

## string_xrefs

- `0x180051f65`: `Failed to Open Driver Package [%d]`
- `0x180051f6c`: `DriverPackageReaderDrvStore::InitDriverPackageHardwareIds`
- `0x1800520a3`: `DriverPackageReaderDrvStore::InitDriverPackageHardwareIds`
- `0x1800521ad`: `DriverPackageReaderDrvStore::InitDriverPackageHardwareIds`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DriverPackageReaderDrvStore::InitDriverPackageHardwareIds(
        DriverPackageReaderDrvStore *this,
        const unsigned __int16 *a2,
        struct CDriverPackage *a3)
{
  __int64 wProcessorArchitecture; // rdx
  __int64 v7; // r15
  __int64 v8; // rsi
  DWORD v9; // eax
  FILE *v10; // rax
  DWORD v11; // ebx
  FILE *v12; // rax
  FILE *v13; // rax
  DWORD v14; // eax
  DWORD v15; // eax
  unsigned int v17; // r12d
  char IsEnabled; // al
  DWORD v19; // eax
  FILE *v20; // rax
  DWORD v21; // ebx
  FILE *v22; // rax
  FILE *v23; // rax
  DWORD v24; // eax
  DWORD v25; // eax
  DWORD LastError; // eax
  struct _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-30h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
  {
    wProcessorArchitecture = *((unsigned __int16 *)this + 12);
  }
  else
  {
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetNativeSystemInfo(&SystemInfo);
    wProcessorArchitecture = SystemInfo.wProcessorArchitecture;
  }
  v7 = DriverPackageOpenW(a2, wProcessorArchitecture, 0, 0, 0);
  if ( v7 )
  {
    v17 = 0;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl);
    memset(&SystemInfo, 0, 24);
    if ( IsEnabled )
    {
      if ( (unsigned int)DriverPackageEnumDriversW(
                           v7,
                           1,
                           DriverPackageReaderDrvStore::DriverHardwareIdsEnumCallback,
                           &SystemInfo) )
      {
        v17 = ConvertListToStr(&SystemInfo, (char *)a3 + 416);
      }
      else
      {
        LastError = GetLastError();
        AslLogCallPrintf(
          1,
          "DriverPackageReaderDrvStore::InitDriverPackageHardwareIds",
          456,
          "Failed to Enum Drivers [%d]",
          LastError);
      }
      std::vector<std::wstring>::~vector<std::wstring>(&SystemInfo);
    }
    else
    {
      if ( (unsigned int)DriverPackageEnumDriversW(
                           v7,
                           1,
                           DriverPackageReaderDrvStore::DriverHardwareIdsEnumCallback,
                           &SystemInfo) )
      {
        v17 = ConvertListToStr(&SystemInfo, (char *)a3 + 416);
      }
      else
      {
        v19 = GetLastError();
        AslLogCallPrintf(
          2,
          "DriverPackageReaderDrvStore::InitDriverPackageHardwareIds",
          471,
          "Failed to Enum Drivers [%d]",
          v19);
        if ( EnableDevInvStdErrLog )
        {
          v20 = o___acrt_iob_func_0(2u);
          fprintf(v20, "Error: %s, %u: ", "DriverPackageReaderDrvStore::InitDriverPackageHardwareIds", 471);
          v21 = GetLastError();
          v22 = o___acrt_iob_func_0(2u);
          fprintf(v22, "Failed to Enum Drivers [%d]", v21);
          v23 = o___acrt_iob_func_0(2u);
          fprintf(v23, "\n");
        }
        if ( g_DeviceMapLogFunction )
        {
          v24 = GetLastError();
          TraceMessageCallback(0x2000000, "Failed to Enum Drivers [%d]", v24);
        }
        v25 = GetLastError();
        AslLogCallPrintf(
          1,
          "DriverPackageReaderDrvStore::InitDriverPackageHardwareIds",
          471,
          "Failed to Enum Drivers [%d]",
          v25);
      }
      std::vector<CDriverPackageDetailed *>::~vector<CDriverPackageDetailed *>(&SystemInfo);
    }
    DriverPackageClose(v7);
    return v17;
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
    {
      v8 = 438;
    }
    else
    {
      v9 = GetLastError();
      v8 = 442;
      AslLogCallPrintf(
        2,
        "DriverPackageReaderDrvStore::InitDriverPackageHardwareIds",
        442,
        "Failed to Open Driver Package [%d]",
        v9);
      if ( EnableDevInvStdErrLog )
      {
        v10 = o___acrt_iob_func_0(2u);
        fprintf(v10, "Error: %s, %u: ", "DriverPackageReaderDrvStore::InitDriverPackageHardwareIds", 442);
        v11 = GetLastError();
        v12 = o___acrt_iob_func_0(2u);
        fprintf(v12, "Failed to Open Driver Package [%d]", v11);
        v13 = o___acrt_iob_func_0(2u);
        fprintf(v13, "\n");
      }
      if ( g_DeviceMapLogFunction )
      {
        v14 = GetLastError();
        TraceMessageCallback(0x2000000, "Failed to Open Driver Package [%d]", v14);
      }
    }
    v15 = GetLastError();
    AslLogCallPrintf(
      1,
      "DriverPackageReaderDrvStore::InitDriverPackageHardwareIds",
      v8,
      "Failed to Open Driver Package [%d]",
      v15);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180051ee8  push    rbp
0x180051eea  push    rbx
0x180051eeb  push    rsi
0x180051eec  push    rdi
0x180051eed  push    r12
0x180051eef  push    r14
0x180051ef1  push    r15
0x180051ef3  mov     rbp, rsp
0x180051ef6  sub     rsp, 60h
0x180051efa  mov     rbx, r8
0x180051efd  mov     rsi, rdx
0x180051f00  mov     rdi, rcx
0x180051f03  lea     r14, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x180051f0a  mov     rcx, r14
0x180051f0d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x180051f12  test    al, al
0x180051f14  jz      short loc_180051F1C
0x180051f16  movzx   edx, word ptr [rdi+18h]
0x180051f1a  jmp     short loc_180051F39
0x180051f1c  xorps   xmm0, xmm0
0x180051f1f  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x180051f23  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180051f27  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x180051f2b  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x180051f2f  call    cs:__imp_GetNativeSystemInfo
0x180051f35  movzx   edx, word ptr [rbp+SystemInfo]
0x180051f39  mov     [rsp+60h+var_40], 0
0x180051f42  xor     r9d, r9d
0x180051f45  xor     r8d, r8d
0x180051f48  mov     rcx, rsi
0x180051f4b  call    cs:__imp_DriverPackageOpenW
0x180051f51  mov     r15, rax
0x180051f54  test    rax, rax
0x180051f57  jnz     loc_180052049
0x180051f5d  mov     rcx, r14
0x180051f60  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x180051f65  lea     r15, aFailedToOpenDr; "Failed to Open Driver Package [%d]"
0x180051f6c  lea     rdi, aDriverpackager_19; "DriverPackageReaderDrvStore::InitDriver"...
0x180051f73  test    al, al
0x180051f75  jz      short loc_180051F81
0x180051f77  mov     esi, 1B6h
0x180051f7c  jmp     loc_180052022
0x180051f81  call    cs:__imp_GetLastError
0x180051f87  mov     dword ptr [rsp+60h+var_40], eax
0x180051f8b  mov     r9, r15
0x180051f8e  mov     esi, 1BAh
0x180051f93  mov     r8d, esi
0x180051f96  mov     rdx, rdi
0x180051f99  mov     r14d, 2
0x180051f9f  mov     ecx, r14d
0x180051fa2  call    AslLogCallPrintf
0x180051fa7  cmp     cs:EnableDevInvStdErrLog, 0
0x180051fae  jz      short loc_180052002
0x180051fb0  mov     ecx, r14d; Ix
0x180051fb3  call    _o___acrt_iob_func_0
0x180051fb8  mov     rcx, rax; Stream
0x180051fbb  mov     r9d, esi
0x180051fbe  mov     r8, rdi
0x180051fc1  lea     rdx, Format; "Error: %s, %u: "
0x180051fc8  call    fprintf
0x180051fcd  call    cs:__imp_GetLastError
0x180051fd3  mov     ebx, eax
0x180051fd5  mov     ecx, r14d; Ix
0x180051fd8  call    _o___acrt_iob_func_0
0x180051fdd  mov     r8d, ebx
0x180051fe0  mov     rdx, r15; Format
0x180051fe3  mov     rcx, rax; Stream
0x180051fe6  call    fprintf
0x180051feb  mov     ecx, r14d; Ix
0x180051fee  call    _o___acrt_iob_func_0
0x180051ff3  mov     rcx, rax; Stream
0x180051ff6  lea     rdx, asc_18011EAD8; "\n"
0x180051ffd  call    fprintf
0x180052002  cmp     cs:g_DeviceMapLogFunction, 0
0x18005200a  jz      short loc_180052022
0x18005200c  call    cs:__imp_GetLastError
0x180052012  mov     r8d, eax
0x180052015  mov     rdx, r15
0x180052018  mov     ecx, 2000000h
0x18005201d  call    TraceMessageCallback
0x180052022  call    cs:__imp_GetLastError
0x180052028  mov     dword ptr [rsp+60h+var_40], eax
0x18005202c  mov     r9, r15
0x18005202f  mov     r8, rsi
0x180052032  mov     rdx, rdi
0x180052035  mov     ecx, 1
0x18005203a  call    AslLogCallPrintf
0x18005203f  mov     eax, 80004005h
0x180052044  jmp     loc_1800521E8
0x180052049  xor     r12d, r12d
0x18005204c  mov     rcx, r14
0x18005204f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x180052054  xorps   xmm0, xmm0
0x180052057  mov     [rbp+SystemInfo.lpMaximumApplicationAddress], r12
0x18005205b  movdqu  xmmword ptr [rbp+SystemInfo], xmm0
0x180052060  test    al, al
0x180052062  jnz     loc_180052179
0x180052068  lea     r9, [rbp+SystemInfo]
0x18005206c  lea     r8, ?DriverHardwareIdsEnumCallback@DriverPackageReaderDrvStore@@SAHPEAUHDRIVERPACKAGE__@@PEAU_DRIVER_INFOW@@_J@Z; DriverPackageReaderDrvStore::DriverHardwareIdsEnumCallback(HDRIVERPACKAGE__ *,_DRIVER_INFOW *,__int64)
0x180052073  lea     edx, [r12+1]
0x180052078  mov     rcx, r15
0x18005207b  call    cs:__imp_DriverPackageEnumDriversW
0x180052081  test    eax, eax
0x180052083  jnz     loc_180052164
0x180052089  call    cs:__imp_GetLastError
0x18005208f  mov     dword ptr [rsp+60h+var_40], eax
0x180052093  lea     rsi, aFailedToEnumDr; "Failed to Enum Drivers [%d]"
0x18005209a  mov     r9, rsi
0x18005209d  mov     r8d, 1D7h
0x1800520a3  lea     rdi, aDriverpackager_19; "DriverPackageReaderDrvStore::InitDriver"...
0x1800520aa  mov     rdx, rdi
0x1800520ad  lea     r14d, [r12+2]
0x1800520b2  mov     ecx, r14d
0x1800520b5  call    AslLogCallPrintf
0x1800520ba  cmp     cs:EnableDevInvStdErrLog, r12d
0x1800520c1  jz      short loc_180052118
0x1800520c3  mov     ecx, r14d; Ix
0x1800520c6  call    _o___acrt_iob_func_0
0x1800520cb  mov     rcx, rax; Stream
0x1800520ce  mov     r9d, 1D7h
0x1800520d4  mov     r8, rdi
0x1800520d7  lea     rdx, Format; "Error: %s, %u: "
0x1800520de  call    fprintf
0x1800520e3  call    cs:__imp_GetLastError
0x1800520e9  mov     ebx, eax
0x1800520eb  mov     ecx, r14d; Ix
0x1800520ee  call    _o___acrt_iob_func_0
0x1800520f3  mov     r8d, ebx
0x1800520f6  mov     rdx, rsi; Format
0x1800520f9  mov     rcx, rax; Stream
0x1800520fc  call    fprintf
0x180052101  mov     ecx, r14d; Ix
0x180052104  call    _o___acrt_iob_func_0
0x180052109  mov     rcx, rax; Stream
0x18005210c  lea     rdx, asc_18011EAD8; "\n"
0x180052113  call    fprintf
0x180052118  cmp     cs:g_DeviceMapLogFunction, 0
0x180052120  jz      short loc_180052138
0x180052122  call    cs:__imp_GetLastError
0x180052128  mov     r8d, eax
0x18005212b  mov     rdx, rsi
0x18005212e  mov     ecx, 2000000h
0x180052133  call    TraceMessageCallback
0x180052138  call    cs:__imp_GetLastError
0x18005213e  mov     dword ptr [rsp+60h+var_40], eax
0x180052142  mov     r9, rsi
0x180052145  mov     r8d, 1D7h
0x18005214b  mov     rdx, rdi
0x18005214e  mov     ecx, 1
0x180052153  call    AslLogCallPrintf
0x180052158  nop
0x180052159  lea     rcx, [rbp+SystemInfo]
0x18005215d  call    ??1?$vector@PEAVCDriverPackageDetailed@@V?$allocator@PEAVCDriverPackageDetailed@@@std@@@std@@QEAA@XZ; std::vector<CDriverPackageDetailed *>::~vector<CDriverPackageDetailed *>(void)
0x180052162  jmp     short loc_1800521DC
0x180052164  lea     rdx, [rbx+1A0h]
0x18005216b  lea     rcx, [rbp+SystemInfo]
0x18005216f  call    ?ConvertListToStr@@YAJAEBV?$vector@PEBGV?$allocator@PEBG@std@@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; ConvertListToStr(std::vector<ushort const *> const &,std::wstring &)
0x180052174  mov     r12d, eax
0x180052177  jmp     short loc_180052159
0x180052179  lea     r9, [rbp+SystemInfo]
0x18005217d  lea     r8, ?DriverHardwareIdsEnumCallback@DriverPackageReaderDrvStore@@SAHPEAUHDRIVERPACKAGE__@@PEAU_DRIVER_INFOW@@_J@Z; DriverPackageReaderDrvStore::DriverHardwareIdsEnumCallback(HDRIVERPACKAGE__ *,_DRIVER_INFOW *,__int64)
0x180052184  mov     edx, 1
0x180052189  mov     rcx, r15
0x18005218c  call    cs:__imp_DriverPackageEnumDriversW
0x180052192  test    eax, eax
0x180052194  jnz     short loc_1800521C0
0x180052196  call    cs:__imp_GetLastError
0x18005219c  mov     dword ptr [rsp+60h+var_40], eax
0x1800521a0  lea     r9, aFailedToEnumDr; "Failed to Enum Drivers [%d]"
0x1800521a7  mov     r8d, 1C8h
0x1800521ad  lea     rdx, aDriverpackager_19; "DriverPackageReaderDrvStore::InitDriver"...
0x1800521b4  mov     ecx, 1
0x1800521b9  call    AslLogCallPrintf
0x1800521be  jmp     short loc_1800521D3
0x1800521c0  lea     rdx, [rbx+1A0h]
0x1800521c7  lea     rcx, [rbp+SystemInfo]
0x1800521cb  call    ?ConvertListToStr@@YAJAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; ConvertListToStr(std::vector<std::wstring> const &,std::wstring &)
0x1800521d0  mov     r12d, eax
0x1800521d3  lea     rcx, [rbp+SystemInfo]
0x1800521d7  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x1800521dc  mov     rcx, r15
0x1800521df  call    cs:__imp_DriverPackageClose
0x1800521e5  mov     eax, r12d
0x1800521e8  add     rsp, 60h
0x1800521ec  pop     r15
0x1800521ee  pop     r14
0x1800521f0  pop     r12
0x1800521f2  pop     rdi
0x1800521f3  pop     rsi
0x1800521f4  pop     rbx
0x1800521f5  pop     rbp
0x1800521f6  retn
```
