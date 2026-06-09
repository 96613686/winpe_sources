# DriverPackageReaderDrvStore::InitDriverPackageFromInf(ushort const *,CDriverPackage &)

- ea: `0x180051bc0`
- end: `0x180051edf`
- name: `?InitDriverPackageFromInf@DriverPackageReaderDrvStore@@UEAAJPEBGAEAVCDriverPackage@@@Z`
- size: `799`
- prototype: `__int64 __fastcall(DriverPackageReaderDrvStore *__hidden this, const unsigned __int16 *, struct CDriverPackage *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x180006210`
- `0x1800066f0`
- `0x180006d02`
- `0x180007014`
- `0x180051bc0`
- `0x180052200`
- `0x1800538cc`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `drvstore!DriverStoreFindW` at `0x180051de0`
- `drvstore!DriverStoreFindW` at `0x180051de0`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180051ccb`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180051ccb`

## string_xrefs

- `0x180051bf7`: `DriverPackageReaderDrvStore::InitDriverPackageFromInf`
- `0x180051c37`: `DriverPackageReaderDrvStore::InitDriverPackageFromInf`
- `0x180051d06`: `DriverPackageReaderDrvStore::InitDriverPackageFromInf`
- `0x180051d4b`: `DriverPackageReaderDrvStore::InitDriverPackageFromInf`
- `0x180051e06`: `DriverPackageReaderDrvStore::InitDriverPackageFromInf`
- `0x180051e4b`: `DriverPackageReaderDrvStore::InitDriverPackageFromInf`

## pseudocode

```c
__int64 __fastcall DriverPackageReaderDrvStore::InitDriverPackageFromInf(
        DriverPackageReaderDrvStore *this,
        const unsigned __int16 *a2,
        struct CDriverPackage *a3)
{
  FILE *v6; // rax
  FILE *v7; // rax
  FILE *v8; // rax
  WORD wProcessorArchitecture; // bp
  struct _DRIVERPACKAGE_INFO_ALL *v11; // rax
  struct _DRIVERPACKAGE_INFO_ALL *v12; // rdi
  FILE *v13; // rax
  FILE *v14; // rax
  FILE *v15; // rax
  FILE *v16; // rax
  FILE *v17; // rax
  FILE *v18; // rax
  unsigned int inited; // ebx
  struct _SYSTEM_INFO SystemInfo; // [rsp+40h] [rbp-58h] BYREF

  if ( *((_QWORD *)this + 2) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
    {
      wProcessorArchitecture = *((_WORD *)this + 12);
    }
    else
    {
      memset(&SystemInfo, 0, sizeof(SystemInfo));
      GetNativeSystemInfo(&SystemInfo);
      wProcessorArchitecture = SystemInfo.wProcessorArchitecture;
    }
    v11 = (struct _DRIVERPACKAGE_INFO_ALL *)operator new(0x4C0u, (const struct std::nothrow_t *)std::nothrow);
    v12 = v11;
    if ( v11 )
    {
      if ( (unsigned int)DriverStoreFindW(
                           *((_QWORD *)this + 2),
                           a2,
                           wProcessorArchitecture,
                           0,
                           1,
                           (char *)v11 + 696,
                           260,
                           v11) )
      {
        inited = DriverPackageReaderDrvStore::InitDriverPackageItem(this, v12, a3);
      }
      else
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
        {
          AslLogCallPrintf(
            3,
            "DriverPackageReaderDrvStore::InitDriverPackageFromInf",
            317,
            "Failed to find driver for %ws",
            a2);
        }
        else
        {
          AslLogCallPrintf(
            3,
            "DriverPackageReaderDrvStore::InitDriverPackageFromInf",
            321,
            "Failed to find driver for %ws",
            a2);
          if ( EnableDevInvStdErrLog )
          {
            v16 = o___acrt_iob_func_0(2u);
            fprintf(v16, "Info: %s, %u: ", "DriverPackageReaderDrvStore::InitDriverPackageFromInf", 321);
            v17 = o___acrt_iob_func_0(2u);
            fprintf(v17, "Failed to find driver for %ws", a2);
            v18 = o___acrt_iob_func_0(2u);
            fprintf(v18, "\n");
          }
          if ( g_DeviceMapLogFunction )
            TraceMessageCallback(0x4000000, "Failed to find driver for %ws", a2);
        }
        inited = -2147467259;
      }
      operator delete(v12);
      return inited;
    }
    else
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
      {
        AslLogCallPrintf(1, "DriverPackageReaderDrvStore::InitDriverPackageFromInf", 297, "Out of memory");
      }
      else
      {
        AslLogCallPrintf(2, "DriverPackageReaderDrvStore::InitDriverPackageFromInf", 301, "Out of memory");
        if ( EnableDevInvStdErrLog )
        {
          v13 = o___acrt_iob_func_0(2u);
          fprintf(v13, "Error: %s, %u: ", "DriverPackageReaderDrvStore::InitDriverPackageFromInf", 301);
          v14 = o___acrt_iob_func_0(2u);
          fprintf(v14, "Out of memory");
          v15 = o___acrt_iob_func_0(2u);
          fprintf(v15, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "Out of memory");
      }
      return 2147942408LL;
    }
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
    {
      AslLogCallPrintf(3, "DriverPackageReaderDrvStore::InitDriverPackageFromInf", 270, "DriverStore isn't initialized");
    }
    else
    {
      AslLogCallPrintf(3, "DriverPackageReaderDrvStore::InitDriverPackageFromInf", 274, "DriverStore isn't initialized");
      if ( EnableDevInvStdErrLog )
      {
        v6 = o___acrt_iob_func_0(2u);
        fprintf(v6, "Info: %s, %u: ", "DriverPackageReaderDrvStore::InitDriverPackageFromInf", 274);
        v7 = o___acrt_iob_func_0(2u);
        fprintf(v7, "DriverStore isn't initialized");
        v8 = o___acrt_iob_func_0(2u);
        fprintf(v8, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x4000000, "DriverStore isn't initialized");
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180051bc0  push    rbx
0x180051bc2  push    rbp
0x180051bc3  push    rsi
0x180051bc4  push    rdi
0x180051bc5  push    r14
0x180051bc7  sub     rsp, 70h
0x180051bcb  cmp     qword ptr [rcx+10h], 0
0x180051bd0  mov     r14, r8
0x180051bd3  mov     rsi, rdx
0x180051bd6  mov     rbx, rcx
0x180051bd9  jnz     loc_180051C9E
0x180051bdf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x180051be6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x180051beb  lea     r9, aDriverstoreIsn; "DriverStore isn't initialized"
0x180051bf2  mov     ecx, 3
0x180051bf7  lea     rdx, aDriverpackager_3; "DriverPackageReaderDrvStore::InitDriver"...
0x180051bfe  test    al, al
0x180051c00  jz      short loc_180051C12
0x180051c02  mov     r8d, 10Eh
0x180051c08  call    AslLogCallPrintf
0x180051c0d  jmp     loc_180051C94
0x180051c12  mov     edi, 112h
0x180051c17  mov     r8d, edi
0x180051c1a  call    AslLogCallPrintf
0x180051c1f  cmp     cs:EnableDevInvStdErrLog, 0
0x180051c26  jz      short loc_180051C79
0x180051c28  mov     ebx, 2
0x180051c2d  mov     ecx, ebx; Ix
0x180051c2f  call    _o___acrt_iob_func_0
0x180051c34  mov     rcx, rax; Stream
0x180051c37  lea     r8, aDriverpackager_3; "DriverPackageReaderDrvStore::InitDriver"...
0x180051c3e  mov     r9d, edi
0x180051c41  lea     rdx, aInfoSU; "Info: %s, %u: "
0x180051c48  call    fprintf
0x180051c4d  mov     ecx, ebx; Ix
0x180051c4f  call    _o___acrt_iob_func_0
0x180051c54  mov     rcx, rax; Stream
0x180051c57  lea     rdx, aDriverstoreIsn; "DriverStore isn't initialized"
0x180051c5e  call    fprintf
0x180051c63  mov     ecx, ebx; Ix
0x180051c65  call    _o___acrt_iob_func_0
0x180051c6a  mov     rcx, rax; Stream
0x180051c6d  lea     rdx, asc_18011EAD8; "\n"
0x180051c74  call    fprintf
0x180051c79  cmp     cs:g_DeviceMapLogFunction, 0
0x180051c81  jz      short loc_180051C94
0x180051c83  lea     rdx, aDriverstoreIsn; "DriverStore isn't initialized"
0x180051c8a  mov     ecx, 4000000h
0x180051c8f  call    TraceMessageCallback
0x180051c94  mov     eax, 80004005h
0x180051c99  jmp     loc_180051ED4
0x180051c9e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x180051ca5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x180051caa  test    al, al
0x180051cac  jz      short loc_180051CB4
0x180051cae  movzx   ebp, word ptr [rbx+18h]
0x180051cb2  jmp     short loc_180051CD6
0x180051cb4  xorps   xmm0, xmm0
0x180051cb7  lea     rcx, [rsp+98h+SystemInfo]; lpSystemInfo
0x180051cbc  movups  xmmword ptr [rsp+98h+SystemInfo], xmm0
0x180051cc1  movups  xmmword ptr [rsp+98h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180051cc6  movups  xmmword ptr [rsp+98h+SystemInfo.dwNumberOfProcessors], xmm0
0x180051ccb  call    cs:__imp_GetNativeSystemInfo
0x180051cd1  movzx   ebp, word ptr [rsp+98h+SystemInfo]
0x180051cd6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180051cdd  mov     ecx, 4C0h; unsigned __int64
0x180051ce2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180051ce7  mov     rdi, rax
0x180051cea  test    rax, rax
0x180051ced  jnz     loc_180051DB2
0x180051cf3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x180051cfa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x180051cff  lea     r9, aOutOfMemory_0; "Out of memory"
0x180051d06  lea     rdx, aDriverpackager_3; "DriverPackageReaderDrvStore::InitDriver"...
0x180051d0d  test    al, al
0x180051d0f  jz      short loc_180051D24
0x180051d11  mov     r8d, 129h
0x180051d17  lea     ecx, [rdi+1]
0x180051d1a  call    AslLogCallPrintf
0x180051d1f  jmp     loc_180051DA8
0x180051d24  mov     edi, 12Dh
0x180051d29  mov     ebx, 2
0x180051d2e  mov     r8d, edi
0x180051d31  mov     ecx, ebx
0x180051d33  call    AslLogCallPrintf
0x180051d38  cmp     cs:EnableDevInvStdErrLog, 0
0x180051d3f  jz      short loc_180051D8D
0x180051d41  mov     ecx, ebx; Ix
0x180051d43  call    _o___acrt_iob_func_0
0x180051d48  mov     rcx, rax; Stream
0x180051d4b  lea     r8, aDriverpackager_3; "DriverPackageReaderDrvStore::InitDriver"...
0x180051d52  mov     r9d, edi
0x180051d55  lea     rdx, Format; "Error: %s, %u: "
0x180051d5c  call    fprintf
0x180051d61  mov     ecx, ebx; Ix
0x180051d63  call    _o___acrt_iob_func_0
0x180051d68  mov     rcx, rax; Stream
0x180051d6b  lea     rdx, aOutOfMemory_0; "Out of memory"
0x180051d72  call    fprintf
0x180051d77  mov     ecx, ebx; Ix
0x180051d79  call    _o___acrt_iob_func_0
0x180051d7e  mov     rcx, rax; Stream
0x180051d81  lea     rdx, asc_18011EAD8; "\n"
0x180051d88  call    fprintf
0x180051d8d  cmp     cs:g_DeviceMapLogFunction, 0
0x180051d95  jz      short loc_180051DA8
0x180051d97  lea     rdx, aOutOfMemory_0; "Out of memory"
0x180051d9e  mov     ecx, 2000000h
0x180051da3  call    TraceMessageCallback
0x180051da8  mov     eax, 80070008h
0x180051dad  jmp     loc_180051ED4
0x180051db2  mov     rcx, [rbx+10h]
0x180051db6  add     rax, 2B8h
0x180051dbc  mov     [rsp+98h+var_60], rdi
0x180051dc1  xor     r9d, r9d
0x180051dc4  mov     [rsp+98h+var_68], 104h
0x180051dcc  movzx   r8d, bp
0x180051dd0  mov     [rsp+98h+var_70], rax
0x180051dd5  mov     rdx, rsi
0x180051dd8  mov     dword ptr [rsp+98h+var_78], 1
0x180051de0  call    cs:__imp_DriverStoreFindW
0x180051de6  test    eax, eax
0x180051de8  jnz     loc_180051EB5
0x180051dee  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x180051df5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x180051dfa  mov     [rsp+98h+var_78], rsi
0x180051dff  lea     r9, aFailedToFindDr; "Failed to find driver for %ws"
0x180051e06  lea     rdx, aDriverpackager_3; "DriverPackageReaderDrvStore::InitDriver"...
0x180051e0d  mov     ecx, 3
0x180051e12  test    al, al
0x180051e14  jz      short loc_180051E26
0x180051e16  mov     r8d, 13Dh
0x180051e1c  call    AslLogCallPrintf
0x180051e21  jmp     loc_180051EAE
0x180051e26  mov     ebp, 141h
0x180051e2b  mov     r8d, ebp
0x180051e2e  call    AslLogCallPrintf
0x180051e33  cmp     cs:EnableDevInvStdErrLog, 0
0x180051e3a  jz      short loc_180051E90
0x180051e3c  mov     ebx, 2
0x180051e41  mov     ecx, ebx; Ix
0x180051e43  call    _o___acrt_iob_func_0
0x180051e48  mov     rcx, rax; Stream
0x180051e4b  lea     r8, aDriverpackager_3; "DriverPackageReaderDrvStore::InitDriver"...
0x180051e52  mov     r9d, ebp
0x180051e55  lea     rdx, aInfoSU; "Info: %s, %u: "
0x180051e5c  call    fprintf
0x180051e61  mov     ecx, ebx; Ix
0x180051e63  call    _o___acrt_iob_func_0
0x180051e68  mov     rcx, rax; Stream
0x180051e6b  lea     rdx, aFailedToFindDr; "Failed to find driver for %ws"
0x180051e72  mov     r8, rsi
0x180051e75  call    fprintf
0x180051e7a  mov     ecx, ebx; Ix
0x180051e7c  call    _o___acrt_iob_func_0
0x180051e81  mov     rcx, rax; Stream
0x180051e84  lea     rdx, asc_18011EAD8; "\n"
0x180051e8b  call    fprintf
0x180051e90  cmp     cs:g_DeviceMapLogFunction, 0
0x180051e98  jz      short loc_180051EAE
0x180051e9a  mov     r8, rsi
0x180051e9d  lea     rdx, aFailedToFindDr; "Failed to find driver for %ws"
0x180051ea4  mov     ecx, 4000000h
0x180051ea9  call    TraceMessageCallback
0x180051eae  mov     ebx, 80004005h
0x180051eb3  jmp     short loc_180051EC5
0x180051eb5  mov     r8, r14; struct CDriverPackage *
0x180051eb8  mov     rdx, rdi; struct _DRIVERPACKAGE_INFO_ALL *
0x180051ebb  mov     rcx, rbx; this
0x180051ebe  call    ?InitDriverPackageItem@DriverPackageReaderDrvStore@@QEAAJAEAU_DRIVERPACKAGE_INFO_ALL@@AEAVCDriverPackage@@@Z; DriverPackageReaderDrvStore::InitDriverPackageItem(_DRIVERPACKAGE_INFO_ALL &,CDriverPackage &)
0x180051ec3  mov     ebx, eax
0x180051ec5  mov     edx, 4C0h
0x180051eca  mov     rcx, rdi; Block
0x180051ecd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180051ed2  mov     eax, ebx
0x180051ed4  add     rsp, 70h
0x180051ed8  pop     r14
0x180051eda  pop     rdi
0x180051edb  pop     rsi
0x180051edc  pop     rbp
0x180051edd  pop     rbx
0x180051ede  retn
```
