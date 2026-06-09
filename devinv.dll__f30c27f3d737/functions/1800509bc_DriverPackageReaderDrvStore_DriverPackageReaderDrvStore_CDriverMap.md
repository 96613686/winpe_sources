# DriverPackageReaderDrvStore::DriverPackageReaderDrvStore(CDriverMap *)

- ea: `0x1800509bc`
- end: `0x180050b46`
- name: `??0DriverPackageReaderDrvStore@@QEAA@PEAVCDriverMap@@@Z`
- size: `394`
- prototype: `DriverPackageReaderDrvStore *__fastcall(DriverPackageReaderDrvStore *__hidden this, struct CDriverMap *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180046388`

## callees

- `0x180006d02`
- `0x180007014`
- `0x1800509bc`
- `0x1800538cc`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `drvstore!DriverStoreOpenW` at `0x180050a25`
- `drvstore!DriverStoreOpenW` at `0x180050a25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050a48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050a59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050aaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050af6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050b10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050a48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050a59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050aaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050af6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050b10`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180050a0c`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180050a0c`

## string_xrefs

- `0x180050a65`: `DriverStoreOpen failed [%d]`
- `0x180050ac4`: `DriverStoreOpen failed [%d]`
- `0x180050afc`: `DriverStoreOpen failed [%d]`
- `0x180050b1c`: `DriverStoreOpen failed [%d]`
- `0x180050a6c`: `DriverPackageReaderDrvStore::DriverPackageReaderDrvStore`
- `0x180050a96`: `DriverPackageReaderDrvStore::DriverPackageReaderDrvStore`
- `0x180050b27`: `DriverPackageReaderDrvStore::DriverPackageReaderDrvStore`

## pseudocode

```c
DriverPackageReaderDrvStore *__fastcall DriverPackageReaderDrvStore::DriverPackageReaderDrvStore(
        DriverPackageReaderDrvStore *this,
        struct CDriverMap *a2)
{
  __int64 v3; // rax
  DWORD LastError; // eax
  __int64 v5; // r8
  DWORD v6; // eax
  FILE *v7; // rax
  DWORD v8; // ebx
  FILE *v9; // rax
  FILE *v10; // rax
  DWORD v11; // eax
  _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-38h] BYREF

  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &DriverPackageReaderDrvStore::`vftable';
  *((_QWORD *)this + 1) = a2;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
  {
    *((_WORD *)this + 12) = -1;
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetNativeSystemInfo(&SystemInfo);
    *((_WORD *)this + 12) = SystemInfo.wProcessorArchitecture;
  }
  v3 = DriverStoreOpenW(0, 0, 0, 0);
  *((_QWORD *)this + 2) = v3;
  if ( !v3 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
    {
      LastError = GetLastError();
      v5 = 36;
    }
    else
    {
      v6 = GetLastError();
      AslLogCallPrintf(
        2,
        "DriverPackageReaderDrvStore::DriverPackageReaderDrvStore",
        40,
        "DriverStoreOpen failed [%d]",
        v6);
      if ( EnableDevInvStdErrLog )
      {
        v7 = o___acrt_iob_func_0(2u);
        fprintf(v7, "Error: %s, %u: ", "DriverPackageReaderDrvStore::DriverPackageReaderDrvStore", 40);
        v8 = GetLastError();
        v9 = o___acrt_iob_func_0(2u);
        fprintf(v9, "DriverStoreOpen failed [%d]", v8);
        v10 = o___acrt_iob_func_0(2u);
        fprintf(v10, "\n");
      }
      if ( g_DeviceMapLogFunction )
      {
        v11 = GetLastError();
        TraceMessageCallback(0x2000000, "DriverStoreOpen failed [%d]", v11);
      }
      LastError = GetLastError();
      v5 = 40;
    }
    AslLogCallPrintf(
      1,
      "DriverPackageReaderDrvStore::DriverPackageReaderDrvStore",
      v5,
      "DriverStoreOpen failed [%d]",
      LastError);
  }
  return this;
}

```

## disassembly

```asm
0x1800509bc  mov     [rsp+arg_0], rbx
0x1800509c1  push    rdi
0x1800509c2  sub     rsp, 60h
0x1800509c6  lea     rax, ??_7DriverPackageReaderDrvStore@@6B@; const DriverPackageReaderDrvStore::`vftable'
0x1800509cd  mov     qword ptr [rcx+10h], 0
0x1800509d5  mov     [rcx], rax
0x1800509d8  mov     rdi, rcx
0x1800509db  mov     [rcx+8], rdx
0x1800509df  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x1800509e6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x1800509eb  test    al, al
0x1800509ed  jz      short loc_180050A1B
0x1800509ef  xorps   xmm0, xmm0
0x1800509f2  mov     word ptr [rdi+18h], 0FFFFh
0x1800509f8  lea     rcx, [rsp+68h+SystemInfo]; lpSystemInfo
0x1800509fd  movups  xmmword ptr [rsp+68h+SystemInfo], xmm0
0x180050a02  movups  xmmword ptr [rsp+68h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180050a07  movups  xmmword ptr [rsp+68h+SystemInfo.dwNumberOfProcessors], xmm0
0x180050a0c  call    cs:__imp_GetNativeSystemInfo
0x180050a12  movzx   eax, word ptr [rsp+68h+SystemInfo]
0x180050a17  mov     [rdi+18h], ax
0x180050a1b  xor     r9d, r9d
0x180050a1e  xor     r8d, r8d
0x180050a21  xor     edx, edx
0x180050a23  xor     ecx, ecx
0x180050a25  call    cs:__imp_DriverStoreOpenW
0x180050a2b  mov     [rdi+10h], rax
0x180050a2f  test    rax, rax
0x180050a32  jnz     loc_180050B38
0x180050a38  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x180050a3f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x180050a44  test    al, al
0x180050a46  jz      short loc_180050A59
0x180050a48  call    cs:__imp_GetLastError
0x180050a4e  mov     r8d, 24h ; '$'
0x180050a54  jmp     loc_180050B1C
0x180050a59  call    cs:__imp_GetLastError
0x180050a5f  mov     r8d, 28h ; '('
0x180050a65  lea     r9, aDriverstoreope; "DriverStoreOpen failed [%d]"
0x180050a6c  lea     rdx, aDriverpackager_20; "DriverPackageReaderDrvStore::DriverPack"...
0x180050a73  mov     [rsp+68h+var_48], eax
0x180050a77  lea     ecx, [r8-26h]
0x180050a7b  call    AslLogCallPrintf
0x180050a80  cmp     cs:EnableDevInvStdErrLog, 0
0x180050a87  jz      short loc_180050AEC
0x180050a89  mov     ecx, 2; Ix
0x180050a8e  call    _o___acrt_iob_func_0
0x180050a93  mov     rcx, rax; Stream
0x180050a96  lea     r8, aDriverpackager_20; "DriverPackageReaderDrvStore::DriverPack"...
0x180050a9d  mov     r9d, 28h ; '('
0x180050aa3  lea     rdx, Format; "Error: %s, %u: "
0x180050aaa  call    fprintf
0x180050aaf  call    cs:__imp_GetLastError
0x180050ab5  mov     ecx, 2; Ix
0x180050aba  mov     ebx, eax
0x180050abc  call    _o___acrt_iob_func_0
0x180050ac1  mov     r8d, ebx
0x180050ac4  lea     rdx, aDriverstoreope; "DriverStoreOpen failed [%d]"
0x180050acb  mov     rcx, rax; Stream
0x180050ace  call    fprintf
0x180050ad3  mov     ecx, 2; Ix
0x180050ad8  call    _o___acrt_iob_func_0
0x180050add  mov     rcx, rax; Stream
0x180050ae0  lea     rdx, asc_18011EAD8; "\n"
0x180050ae7  call    fprintf
0x180050aec  cmp     cs:g_DeviceMapLogFunction, 0
0x180050af4  jz      short loc_180050B10
0x180050af6  call    cs:__imp_GetLastError
0x180050afc  lea     rdx, aDriverstoreope; "DriverStoreOpen failed [%d]"
0x180050b03  mov     ecx, 2000000h
0x180050b08  mov     r8d, eax
0x180050b0b  call    TraceMessageCallback
0x180050b10  call    cs:__imp_GetLastError
0x180050b16  mov     r8d, 28h ; '('
0x180050b1c  lea     r9, aDriverstoreope; "DriverStoreOpen failed [%d]"
0x180050b23  mov     [rsp+68h+var_48], eax
0x180050b27  lea     rdx, aDriverpackager_20; "DriverPackageReaderDrvStore::DriverPack"...
0x180050b2e  mov     ecx, 1
0x180050b33  call    AslLogCallPrintf
0x180050b38  mov     rbx, [rsp+68h+arg_0]
0x180050b3d  mov     rax, rdi
0x180050b40  add     rsp, 60h
0x180050b44  pop     rdi
0x180050b45  retn
```
