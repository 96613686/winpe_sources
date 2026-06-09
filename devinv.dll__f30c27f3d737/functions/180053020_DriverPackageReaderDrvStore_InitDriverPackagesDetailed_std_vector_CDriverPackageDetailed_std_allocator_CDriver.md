# DriverPackageReaderDrvStore::InitDriverPackagesDetailed(std::vector<CDriverPackageDetailed *,std::allocator<CDriverPackageDetailed *>> &)

- ea: `0x180053020`
- end: `0x1800536ae`
- name: `?InitDriverPackagesDetailed@DriverPackageReaderDrvStore@@UEAAJAEAV?$vector@PEAVCDriverPackageDetailed@@V?$allocator@PEAVCDriverPackageDetailed@@@std@@@std@@@Z`
- size: `1678`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005e40`
- `0x180006210`
- `0x180006270`
- `0x180006d02`
- `0x180007014`
- `0x180016598`
- `0x180018934`
- `0x18004d314`
- `0x18005164c`
- `0x180053020`
- `0x1800538cc`
- `0x18006041c`
- `0x180066c10`
- `0x180116010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800534ba`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800534ba`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800534cd`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800534e8`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800534cd`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800534e8`
- `drvstore!DriverStoreEnumW` at `0x180053200`
- `drvstore!DriverStoreEnumW` at `0x180053200`

## string_xrefs

- `0x180053085`: `DriverPackageReaderDrvStore::InitDriverPackagesDetailed`
- `0x18005309e`: `DriverPackageReaderDrvStore::InitDriverPackagesDetailed`
- `0x18005314b`: `DriverPackageReaderDrvStore::InitDriverPackagesDetailed`
- `0x1800533c2`: `DriverPackageReaderDrvStore::IsPackageInTelecommand`
- `0x180053409`: `DriverPackageReaderDrvStore::IsPackageInTelecommand`
- `0x180053469`: `DriverPackageReaderDrvStore::IsPackageInTelecommand`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall DriverPackageReaderDrvStore::InitDriverPackagesDetailed(DriverPackageReaderDrvStore *a1, __int64 a2)
{
  FILE *v2; // rax
  FILE *v3; // rax
  FILE *v4; // rax
  FILE *v6; // rax
  FILE *v7; // rax
  FILE *v8; // rax
  unsigned int v9; // r13d
  __int64 v10; // r15
  FILE *v11; // rax
  FILE *v12; // rax
  FILE *v13; // rax
  void **v14; // rdi
  void **i; // rbx
  FILE *v16; // rax
  FILE *v17; // rax
  FILE *v18; // rax
  unsigned __int128 v19; // kr10_16
  __int64 v20; // r8
  FILE *v21; // rax
  FILE *v22; // rax
  FILE *v23; // rax
  wchar_t *v24; // rax
  wchar_t *v25; // rax
  wchar_t *v26; // r8
  char *v27; // rax
  signed __int64 v28; // r8
  int v29; // ecx
  int v30; // edx
  CDriverPackageDetailed *v31; // r13
  FILE *v32; // rax
  FILE *v33; // rax
  FILE *v34; // rax
  __int64 v35; // rax
  CDriverPackageDetailed **v36; // rdx
  __int64 v37; // [rsp+20h] [rbp-2A8h]
  struct _DRIVERPACKAGE_INFO_ALL *v38; // [rsp+30h] [rbp-298h]
  int inited; // [rsp+30h] [rbp-298h]
  CDriverPackageDetailed *v41; // [rsp+48h] [rbp-280h] BYREF
  unsigned __int128 v42; // [rsp+50h] [rbp-278h] BYREF
  __int64 v43; // [rsp+60h] [rbp-268h]
  __int64 v44; // [rsp+68h] [rbp-260h]
  unsigned __int64 v45; // [rsp+70h] [rbp-258h]
  wchar_t Str[264]; // [rsp+80h] [rbp-248h] BYREF

  v44 = a2;
  if ( *((_QWORD *)a1 + 2) )
  {
    v42 = 0;
    v43 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
    {
      AslLogCallPrintf(3, "DriverPackageReaderDrvStore::InitDriverPackagesDetailed", 177, "Begin DriverStoreEnum");
    }
    else
    {
      AslLogCallPrintf(3, "DriverPackageReaderDrvStore::InitDriverPackagesDetailed", 181, "Begin DriverStoreEnum");
      if ( EnableDevInvStdErrLog )
      {
        v6 = o___acrt_iob_func_0(2u);
        fprintf(v6, "Info: %s, %u: ", "DriverPackageReaderDrvStore::InitDriverPackagesDetailed", 181);
        v7 = o___acrt_iob_func_0(2u);
        fprintf(v7, "Begin DriverStoreEnum");
        v8 = o___acrt_iob_func_0(2u);
        fprintf(v8, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x4000000, "Begin DriverStoreEnum");
    }
    if ( (unsigned int)DriverStoreEnumW(0, 2, DriverPackageReaderDrvStore::PackagesEnumCallback, &v42) )
    {
      v9 = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
      {
        AslLogCallPrintf(3, "DriverPackageReaderDrvStore::InitDriverPackagesDetailed", 202, "End DriverStoreEnum");
      }
      else
      {
        AslLogCallPrintf(3, "DriverPackageReaderDrvStore::InitDriverPackagesDetailed", 206, "End DriverStoreEnum");
        if ( EnableDevInvStdErrLog )
        {
          v16 = o___acrt_iob_func_0(2u);
          fprintf(v16, "Info: %s, %u: ", "DriverPackageReaderDrvStore::InitDriverPackagesDetailed", 206);
          v17 = o___acrt_iob_func_0(2u);
          fprintf(v17, "End DriverStoreEnum");
          v18 = o___acrt_iob_func_0(2u);
          fprintf(v18, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x4000000, "End DriverStoreEnum");
      }
      v19 = v42;
      v45 = *((_QWORD *)&v42 + 1);
      while ( (_QWORD)v19 != *((_QWORD *)&v19 + 1) )
      {
        if ( *((_QWORD *)a1 + 1) )
        {
          v38 = *(struct _DRIVERPACKAGE_INFO_ALL **)v19;
          _o_wcscpy_s(Str, 260, *(_QWORD *)v19 + 696LL);
          v24 = wcsrchr(Str, 0x5Cu);
          if ( v24 )
          {
            *v24 = 0;
            v25 = wcsrchr(Str, 0x5Cu);
            if ( v25 )
            {
              v26 = v25 + 1;
              v27 = (char *)(*((_QWORD *)a1 + 1) + 240LL);
              v28 = (char *)v26 - v27;
              do
              {
                v29 = *(unsigned __int16 *)&v27[v28];
                v30 = *(unsigned __int16 *)v27 - v29;
                if ( v30 )
                  break;
                v27 += 2;
              }
              while ( v29 );
              if ( !v30 )
              {
                v41 = (CDriverPackageDetailed *)operator new(0x268u);
                v31 = CDriverPackageDetailed::CDriverPackageDetailed(v41);
                v41 = v31;
                inited = DriverPackageReaderDrvStore::InitDriverPackageDetailedItem(a1, v38, v31);
                if ( inited >= 0 )
                {
                  v35 = v44;
                  v36 = *(CDriverPackageDetailed ***)(v44 + 8);
                  if ( v36 == *(CDriverPackageDetailed ***)(v44 + 16) )
                  {
                    std::vector<CDevice *>::_Emplace_reallocate<CDevice * const &>(v44, v36, &v41);
                  }
                  else
                  {
                    *v36 = v31;
                    *(_QWORD *)(v35 + 8) += 8LL;
                  }
                  v9 = inited;
                }
                else
                {
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
                  {
                    AslLogCallPrintf(
                      3,
                      "DriverPackageReaderDrvStore::InitDriverPackagesDetailed",
                      224,
                      "Failed to Initialize DriverPackageDetailed item");
                  }
                  else
                  {
                    AslLogCallPrintf(
                      3,
                      "DriverPackageReaderDrvStore::InitDriverPackagesDetailed",
                      228,
                      "Failed to Initialize DriverPackageDetailed item");
                    if ( EnableDevInvStdErrLog )
                    {
                      v32 = o___acrt_iob_func_0(2u);
                      fprintf(v32, "Info: %s, %u: ", "DriverPackageReaderDrvStore::InitDriverPackagesDetailed", 228);
                      v33 = o___acrt_iob_func_0(2u);
                      fprintf(v33, "Failed to Initialize DriverPackageDetailed item");
                      v34 = o___acrt_iob_func_0(2u);
                      fprintf(v34, "\n");
                    }
                    if ( g_DeviceMapLogFunction )
                      TraceMessageCallback(0x4000000, "Failed to Initialize DriverPackageDetailed item");
                  }
                  if ( v31 )
                    (**(void (__fastcall ***)(CDriverPackageDetailed *, __int64))v31)(v31, 1);
                  v9 = inited;
                }
              }
            }
          }
        }
        else
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
          {
            v20 = 876;
          }
          else
          {
            AslLogCallPrintf(
              2,
              "DriverPackageReaderDrvStore::IsPackageInTelecommand",
              880,
              "m_DriverMap is NULL [%#x]",
              -2147467259);
            if ( EnableDevInvStdErrLog )
            {
              v21 = o___acrt_iob_func_0(2u);
              fprintf(v21, "Error: %s, %u: ", "DriverPackageReaderDrvStore::IsPackageInTelecommand", 880);
              v22 = o___acrt_iob_func_0(2u);
              fprintf(v22, "m_DriverMap is NULL [%#x]", -2147467259);
              v23 = o___acrt_iob_func_0(2u);
              fprintf(v23, "\n");
            }
            if ( g_DeviceMapLogFunction )
              TraceMessageCallback(0x2000000, "m_DriverMap is NULL [%#x]", -2147467259);
            v20 = 880;
          }
          LODWORD(v37) = -2147467259;
          AslLogCallPrintf(
            1,
            "DriverPackageReaderDrvStore::IsPackageInTelecommand",
            v20,
            "m_DriverMap is NULL [%#x]",
            v37);
        }
        v19 = __PAIR128__(v45, (__int64)v19 + 8);
      }
    }
    else
    {
      v9 = -2147467259;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
      {
        v10 = 192;
      }
      else
      {
        v10 = 196;
        AslLogCallPrintf(
          2,
          "DriverPackageReaderDrvStore::InitDriverPackagesDetailed",
          196,
          "Failed to enumerate DriverStore packages [%#x]",
          -2147467259);
        if ( EnableDevInvStdErrLog )
        {
          v11 = o___acrt_iob_func_0(2u);
          fprintf(v11, "Error: %s, %u: ", "DriverPackageReaderDrvStore::InitDriverPackagesDetailed", 196);
          v12 = o___acrt_iob_func_0(2u);
          fprintf(v12, "Failed to enumerate DriverStore packages [%#x]", -2147467259);
          v13 = o___acrt_iob_func_0(2u);
          fprintf(v13, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "Failed to enumerate DriverStore packages [%#x]", -2147467259);
      }
      AslLogCallPrintf(
        1,
        "DriverPackageReaderDrvStore::InitDriverPackagesDetailed",
        v10,
        "Failed to enumerate DriverStore packages [%#x]",
        -2147467259);
    }
    v14 = (void **)*((_QWORD *)&v42 + 1);
    for ( i = (void **)v42; i != v14; ++i )
      operator delete(*i);
    std::vector<CDriverPackageDetailed *>::~vector<CDriverPackageDetailed *>(&v42);
    return v9;
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
    {
      AslLogCallPrintf(
        3,
        "DriverPackageReaderDrvStore::InitDriverPackagesDetailed",
        163,
        "DriverStore isn't initialized");
    }
    else
    {
      AslLogCallPrintf(
        3,
        "DriverPackageReaderDrvStore::InitDriverPackagesDetailed",
        167,
        "DriverStore isn't initialized");
      if ( EnableDevInvStdErrLog )
      {
        v2 = o___acrt_iob_func_0(2u);
        fprintf(v2, "Info: %s, %u: ", "DriverPackageReaderDrvStore::InitDriverPackagesDetailed", 167);
        v3 = o___acrt_iob_func_0(2u);
        fprintf(v3, "DriverStore isn't initialized");
        v4 = o___acrt_iob_func_0(2u);
        fprintf(v4, "\n");
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
0x180053020  mov     [rsp+arg_10], rbx
0x180053025  mov     [rsp+arg_18], rsi
0x18005302a  push    rdi
0x18005302b  push    r12
0x18005302d  push    r13
0x18005302f  push    r14
0x180053031  push    r15
0x180053033  sub     rsp, 2A0h
0x18005303a  mov     rax, cs:__security_cookie
0x180053041  xor     rax, rsp
0x180053044  mov     [rsp+2C8h+var_38], rax
0x18005304c  mov     [rsp+2C8h+var_260], rdx
0x180053051  mov     [rsp+2C8h+var_290], rcx
0x180053056  xor     r12d, r12d
0x180053059  cmp     [rcx+10h], r12
0x18005305d  jnz     loc_180053127
0x180053063  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x18005306a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x18005306f  lea     r9, aDriverstoreIsn; "DriverStore isn't initialized"
0x180053076  lea     ecx, [r12+3]
0x18005307b  test    al, al
0x18005307d  jz      short loc_180053096
0x18005307f  mov     r8d, 0A3h
0x180053085  lea     rdx, aDriverpackager_2; "DriverPackageReaderDrvStore::InitDriver"...
0x18005308c  call    AslLogCallPrintf
0x180053091  jmp     loc_18005311D
0x180053096  mov     esi, 0A7h
0x18005309b  mov     r8d, esi
0x18005309e  lea     rbx, aDriverpackager_2; "DriverPackageReaderDrvStore::InitDriver"...
0x1800530a5  mov     rdx, rbx
0x1800530a8  call    AslLogCallPrintf
0x1800530ad  cmp     cs:EnableDevInvStdErrLog, r12d
0x1800530b4  jz      short loc_180053103
0x1800530b6  mov     edi, 2
0x1800530bb  mov     ecx, edi; Ix
0x1800530bd  call    _o___acrt_iob_func_0
0x1800530c2  mov     rcx, rax; Stream
0x1800530c5  mov     r9d, esi
0x1800530c8  mov     r8, rbx
0x1800530cb  lea     rdx, aInfoSU; "Info: %s, %u: "
0x1800530d2  call    fprintf
0x1800530d7  mov     ecx, edi; Ix
0x1800530d9  call    _o___acrt_iob_func_0
0x1800530de  mov     rcx, rax; Stream
0x1800530e1  lea     rdx, aDriverstoreIsn; "DriverStore isn't initialized"
0x1800530e8  call    fprintf
0x1800530ed  mov     ecx, edi; Ix
0x1800530ef  call    _o___acrt_iob_func_0
0x1800530f4  mov     rcx, rax; Stream
0x1800530f7  lea     rdx, asc_18011EAD8; "\n"
0x1800530fe  call    fprintf
0x180053103  cmp     cs:g_DeviceMapLogFunction, r12
0x18005310a  jz      short loc_18005311D
0x18005310c  lea     rdx, aDriverstoreIsn; "DriverStore isn't initialized"
0x180053113  mov     ecx, 4000000h
0x180053118  call    TraceMessageCallback
0x18005311d  mov     eax, 80004005h
0x180053122  jmp     loc_180053681
0x180053127  xorps   xmm0, xmm0
0x18005312a  movdqu  [rsp+2C8h+var_278], xmm0
0x180053130  mov     [rsp+2C8h+var_268], r12
0x180053135  lea     r15, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x18005313c  mov     rcx, r15
0x18005313f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x180053144  lea     r9, aBeginDriversto; "Begin DriverStoreEnum"
0x18005314b  lea     rbx, aDriverpackager_2; "DriverPackageReaderDrvStore::InitDriver"...
0x180053152  mov     r14d, 3
0x180053158  mov     rdx, rbx
0x18005315b  mov     ecx, r14d
0x18005315e  test    al, al
0x180053160  jz      short loc_180053173
0x180053162  mov     r8d, 0B1h
0x180053168  call    AslLogCallPrintf
0x18005316d  lea     edi, [r14-1]
0x180053171  jmp     short loc_1800531F0
0x180053173  mov     esi, 0B5h
0x180053178  mov     r8d, esi
0x18005317b  call    AslLogCallPrintf
0x180053180  mov     edi, 2
0x180053185  cmp     cs:EnableDevInvStdErrLog, r12d
0x18005318c  jz      short loc_1800531D6
0x18005318e  mov     ecx, edi; Ix
0x180053190  call    _o___acrt_iob_func_0
0x180053195  mov     rcx, rax; Stream
0x180053198  mov     r9d, esi
0x18005319b  mov     r8, rbx
0x18005319e  lea     rdx, aInfoSU; "Info: %s, %u: "
0x1800531a5  call    fprintf
0x1800531aa  mov     ecx, edi; Ix
0x1800531ac  call    _o___acrt_iob_func_0
0x1800531b1  mov     rcx, rax; Stream
0x1800531b4  lea     rdx, aBeginDriversto; "Begin DriverStoreEnum"
0x1800531bb  call    fprintf
0x1800531c0  mov     ecx, edi; Ix
0x1800531c2  call    _o___acrt_iob_func_0
0x1800531c7  mov     rcx, rax; Stream
0x1800531ca  lea     rdx, asc_18011EAD8; "\n"
0x1800531d1  call    fprintf
0x1800531d6  cmp     cs:g_DeviceMapLogFunction, r12
0x1800531dd  jz      short loc_1800531F0
0x1800531df  lea     rdx, aBeginDriversto; "Begin DriverStoreEnum"
0x1800531e6  mov     ecx, 4000000h
0x1800531eb  call    TraceMessageCallback
0x1800531f0  lea     r9, [rsp+2C8h+var_278]
0x1800531f5  lea     r8, ?PackagesEnumCallback@DriverPackageReaderDrvStore@@SAHPEAUHDRIVERSTORE__@@PEBGPEAU_DRIVERSTORE_DRIVERPACKAGE_INFOW@@_J@Z; DriverPackageReaderDrvStore::PackagesEnumCallback(HDRIVERSTORE__ *,ushort const *,_DRIVERSTORE_DRIVERPACKAGE_INFOW *,__int64)
0x1800531fc  mov     edx, edi
0x1800531fe  xor     ecx, ecx
0x180053200  call    cs:__imp_DriverStoreEnumW
0x180053206  test    eax, eax
0x180053208  jnz     loc_1800532E1
0x18005320e  mov     esi, 80004005h
0x180053213  mov     r13d, esi
0x180053216  mov     rcx, r15
0x180053219  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x18005321e  lea     r14, aFailedToEnumer; "Failed to enumerate DriverStore package"...
0x180053225  test    al, al
0x180053227  jz      short loc_180053234
0x180053229  mov     r15d, 0C0h
0x18005322f  jmp     loc_1800532B7
0x180053234  mov     [rsp+2C8h+var_2A8], esi
0x180053238  mov     r9, r14
0x18005323b  mov     r15d, 0C4h
0x180053241  mov     r8d, r15d
0x180053244  mov     rdx, rbx
0x180053247  mov     ecx, edi
0x180053249  call    AslLogCallPrintf
0x18005324e  cmp     cs:EnableDevInvStdErrLog, r12d
0x180053255  jz      short loc_18005329E
0x180053257  mov     ecx, edi; Ix
0x180053259  call    _o___acrt_iob_func_0
0x18005325e  mov     rcx, rax; Stream
0x180053261  mov     r9d, r15d
0x180053264  mov     r8, rbx
0x180053267  lea     rdx, Format; "Error: %s, %u: "
0x18005326e  call    fprintf
0x180053273  mov     ecx, edi; Ix
0x180053275  call    _o___acrt_iob_func_0
0x18005327a  mov     rcx, rax; Stream
0x18005327d  mov     r8d, esi
0x180053280  mov     rdx, r14; Format
0x180053283  call    fprintf
0x180053288  mov     ecx, edi; Ix
0x18005328a  call    _o___acrt_iob_func_0
0x18005328f  mov     rcx, rax; Stream
0x180053292  lea     rdx, asc_18011EAD8; "\n"
0x180053299  call    fprintf
0x18005329e  cmp     cs:g_DeviceMapLogFunction, r12
0x1800532a5  jz      short loc_1800532B7
0x1800532a7  mov     r8d, esi
0x1800532aa  mov     rdx, r14
0x1800532ad  mov     ecx, 2000000h
0x1800532b2  call    TraceMessageCallback
0x1800532b7  mov     r12d, 1
0x1800532bd  mov     [rsp+2C8h+var_2A8], esi
0x1800532c1  mov     r9, r14
0x1800532c4  mov     r8, r15
0x1800532c7  mov     rdx, rbx
0x1800532ca  mov     ecx, r12d
0x1800532cd  call    AslLogCallPrintf
0x1800532d2  mov     rdi, qword ptr [rsp+2C8h+var_278+8]
0x1800532d7  mov     rbx, qword ptr [rsp+2C8h+var_278]
0x1800532dc  jmp     loc_18005366F
0x1800532e1  mov     r13d, r12d
0x1800532e4  mov     rcx, r15
0x1800532e7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x1800532ec  lea     r9, aEndDriverstore; "End DriverStoreEnum"
0x1800532f3  mov     rdx, rbx
0x1800532f6  mov     ecx, r14d
0x1800532f9  test    al, al
0x1800532fb  jz      short loc_18005330A
0x1800532fd  mov     r8d, 0CAh
0x180053303  call    AslLogCallPrintf
0x180053308  jmp     short loc_180053382
0x18005330a  mov     esi, 0CEh
0x18005330f  mov     r8d, esi
0x180053312  call    AslLogCallPrintf
0x180053317  cmp     cs:EnableDevInvStdErrLog, r12d
0x18005331e  jz      short loc_180053368
0x180053320  mov     ecx, edi; Ix
0x180053322  call    _o___acrt_iob_func_0
0x180053327  mov     rcx, rax; Stream
0x18005332a  mov     r9d, esi
0x18005332d  mov     r8, rbx
0x180053330  lea     rdx, aInfoSU; "Info: %s, %u: "
0x180053337  call    fprintf
0x18005333c  mov     ecx, edi; Ix
0x18005333e  call    _o___acrt_iob_func_0
0x180053343  mov     rcx, rax; Stream
0x180053346  lea     rdx, aEndDriverstore; "End DriverStoreEnum"
0x18005334d  call    fprintf
0x180053352  mov     ecx, edi; Ix
0x180053354  call    _o___acrt_iob_func_0
0x180053359  mov     rcx, rax; Stream
0x18005335c  lea     rdx, asc_18011EAD8; "\n"
0x180053363  call    fprintf
0x180053368  cmp     cs:g_DeviceMapLogFunction, r12
0x18005336f  jz      short loc_180053382
0x180053371  lea     rdx, aEndDriverstore; "End DriverStoreEnum"
0x180053378  mov     ecx, 4000000h
0x18005337d  call    TraceMessageCallback
0x180053382  mov     rax, qword ptr [rsp+2C8h+var_278]
0x180053387  mov     rcx, qword ptr [rsp+2C8h+var_278+8]
0x18005338c  mov     [rsp+2C8h+var_258], rcx
0x180053391  mov     esi, 80004005h
0x180053396  mov     r12d, 1
0x18005339c  mov     [rsp+2C8h+var_288], rax
0x1800533a1  cmp     rax, rcx
0x1800533a4  jz      loc_1800532D2
0x1800533aa  mov     rcx, [rsp+2C8h+var_290]
0x1800533af  cmp     qword ptr [rcx+8], 0
0x1800533b4  jnz     loc_18005349E
0x1800533ba  mov     rcx, r15
0x1800533bd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x1800533c2  lea     rdx, aDriverpackager_13; "DriverPackageReaderDrvStore::IsPackageI"...
0x1800533c9  lea     r9, aMDrivermapIsNu; "m_DriverMap is NULL [%#x]"
0x1800533d0  test    al, al
0x1800533d2  jz      short loc_1800533DF
0x1800533d4  mov     r8d, 36Ch
0x1800533da  jmp     loc_18005347D
0x1800533df  mov     [rsp+2C8h+var_2A8], esi
0x1800533e3  mov     r8d, 370h
0x1800533e9  mov     ecx, edi
0x1800533eb  call    AslLogCallPrintf
0x1800533f0  cmp     cs:EnableDevInvStdErrLog, 0
0x1800533f7  jz      short loc_18005344B
0x1800533f9  mov     ecx, edi; Ix
0x1800533fb  call    _o___acrt_iob_func_0
0x180053400  mov     rcx, rax; Stream
0x180053403  mov     r9d, 370h
0x180053409  lea     r8, aDriverpackager_13; "DriverPackageReaderDrvStore::IsPackageI"...
0x180053410  lea     rdx, Format; "Error: %s, %u: "
0x180053417  call    fprintf
0x18005341c  mov     ecx, edi; Ix
0x18005341e  call    _o___acrt_iob_func_0
0x180053423  mov     rcx, rax; Stream
0x180053426  mov     r8d, esi
0x180053429  lea     rdx, aMDrivermapIsNu; "m_DriverMap is NULL [%#x]"
0x180053430  call    fprintf
0x180053435  mov     ecx, edi; Ix
0x180053437  call    _o___acrt_iob_func_0
0x18005343c  mov     rcx, rax; Stream
0x18005343f  lea     rdx, asc_18011EAD8; "\n"
0x180053446  call    fprintf
0x18005344b  cmp     cs:g_DeviceMapLogFunction, 0
0x180053453  jz      short loc_180053469
0x180053455  mov     r8d, esi
0x180053458  lea     rdx, aMDrivermapIsNu; "m_DriverMap is NULL [%#x]"
0x18005345f  mov     ecx, 2000000h
0x180053464  call    TraceMessageCallback
0x180053469  lea     rdx, aDriverpackager_13; "DriverPackageReaderDrvStore::IsPackageI"...
0x180053470  mov     r8d, 370h
0x180053476  lea     r9, aMDrivermapIsNu; "m_DriverMap is NULL [%#x]"
0x18005347d  mov     eax, esi
0x18005347f  mov     ecx, r12d
0x180053482  mov     [rsp+2C8h+var_2A8], eax
0x180053486  call    AslLogCallPrintf
0x18005348b  mov     rax, [rsp+2C8h+var_288]
0x180053490  add     rax, 8
0x180053494  mov     rcx, [rsp+2C8h+var_258]
0x180053499  jmp     loc_18005339C
0x18005349e  mov     rax, [rax]
0x1800534a1  mov     [rsp+2C8h+var_298], rax
0x1800534a6  lea     r8, [rax+2B8h]
0x1800534ad  mov     edx, 104h
0x1800534b2  lea     rcx, [rsp+2C8h+Str]
0x1800534ba  call    cs:__imp__o_wcscpy_s
0x1800534c0  mov     edx, 5Ch ; '\'; Ch
0x1800534c5  lea     rcx, [rsp+2C8h+Str]; Str
0x1800534cd  call    cs:__imp_wcsrchr
0x1800534d3  test    rax, rax
0x1800534d6  jz      short loc_18005348B
0x1800534d8  xor     ecx, ecx
0x1800534da  mov     [rax], cx
0x1800534dd  lea     edx, [rcx+5Ch]; Ch
0x1800534e0  lea     rcx, [rsp+2C8h+Str]; Str
0x1800534e8  call    cs:__imp_wcsrchr
0x1800534ee  test    rax, rax
0x1800534f1  jz      short loc_18005348B
0x1800534f3  lea     r8, [rax+2]
0x1800534f7  mov     rax, [rsp+2C8h+var_290]
0x1800534fc  mov     rax, [rax+8]
0x180053500  add     rax, 0F0h
0x180053506  sub     r8, rax
0x180053509  movzx   edx, word ptr [rax]
0x18005350c  movzx   ecx, word ptr [rax+r8]
0x180053511  sub     edx, ecx
0x180053513  jnz     short loc_18005351C
0x180053515  add     rax, rdi
0x180053518  test    ecx, ecx
0x18005351a  jnz     short loc_180053509
0x18005351c  test    edx, edx
0x18005351e  jnz     loc_18005348B
0x180053524  mov     ecx, 268h; Size
0x180053529  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005352e  mov     [rsp+2C8h+var_280], rax
0x180053533  mov     rcx, rax; this
0x180053536  call    ??0CDriverPackageDetailed@@QEAA@XZ; CDriverPackageDetailed::CDriverPackageDetailed(void)
0x18005353b  mov     r13, rax
0x18005353e  mov     [rsp+2C8h+var_280], rax
0x180053543  mov     r8, rax; struct CDriverPackageDetailed *
  ... truncated ...
```
