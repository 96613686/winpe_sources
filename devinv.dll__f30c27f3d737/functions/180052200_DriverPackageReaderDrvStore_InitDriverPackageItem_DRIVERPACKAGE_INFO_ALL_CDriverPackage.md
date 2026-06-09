# DriverPackageReaderDrvStore::InitDriverPackageItem(_DRIVERPACKAGE_INFO_ALL &,CDriverPackage &)

- ea: `0x180052200`
- end: `0x180052b27`
- name: `?InitDriverPackageItem@DriverPackageReaderDrvStore@@QEAAJAEAU_DRIVERPACKAGE_INFO_ALL@@AEAVCDriverPackage@@@Z`
- size: `2343`
- prototype: `int(DriverPackageReaderDrvStore *__hidden this, struct _DRIVERPACKAGE_INFO_ALL *, struct CDriverPackage *)`
- caller_count: `2`
- callee_count: `24`
- tags: ``

## callers

- `0x180051bc0`
- `0x180052b30`

## callees

- `0x180005e40`
- `0x180006d02`
- `0x180006eb8`
- `0x180006ec4`
- `0x180007014`
- `0x18000fa50`
- `0x1800103e0`
- `0x180010a9c`
- `0x180014b80`
- `0x180016440`
- `0x18001ae20`
- `0x1800316a0`
- `0x18003690c`
- `0x18004c8ac`
- `0x18004ce48`
- `0x180050f2c`
- `0x18005155c`
- `0x180051ee8`
- `0x180052200`
- `0x1800538cc`
- `0x1800601cc`
- `0x18006041c`
- `0x180061910`
- `0x180066c10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180052506`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180052506`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180052515`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180052515`
- `DEVOBJ!DevObjClassNameFromGuid` at `0x1800526af`
- `DEVOBJ!DevObjClassNameFromGuid` at `0x1800526af`

## string_xrefs

- `0x180052262`: `DriverPackageReaderDrvStore::InitDriverPackageItem`
- `0x180052339`: `DriverPackageReaderDrvStore::InitDriverPackageItem`
- `0x1800523a8`: `DriverPackageReaderDrvStore::InitDriverPackageItem`
- `0x180052546`: `DriverPackageReaderDrvStore::InitDriverPackageItem`
- `0x18005255f`: `DriverPackageReaderDrvStore::InitDriverPackageItem`
- `0x18005272e`: `DriverPackageReaderDrvStore::InitDriverPackageItem`
- `0x180052530`: `Invalid path`
- `0x1800525a0`: `Invalid path`
- `0x1800525cc`: `Invalid path`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DriverPackageReaderDrvStore::InitDriverPackageItem(
        DriverPackageReaderDrvStore *this,
        struct _DRIVERPACKAGE_INFO_ALL *a2,
        struct CDriverPackage *a3)
{
  unsigned int v5; // ebx
  const char *v6; // r12
  __int64 v7; // rsi
  FILE *v8; // rax
  FILE *v9; // rax
  FILE *v10; // rax
  const unsigned __int16 *v11; // r13
  __int64 v12; // rsi
  FILE *v13; // rax
  FILE *v14; // rax
  FILE *v15; // rax
  __int64 v16; // rsi
  __int64 v17; // rdi
  __int64 v18; // rbx
  __int64 DriverStoreProperty; // rax
  wchar_t *v20; // rax
  __int64 v21; // r8
  FILE *v22; // rax
  FILE *v23; // rax
  FILE *v24; // rax
  unsigned __int64 v25; // r12
  unsigned __int64 v26; // rdx
  char *v27; // rsi
  __int64 v28; // rbx
  const unsigned __int16 *v29; // rcx
  __int64 v30; // r8
  unsigned __int64 v31; // rdx
  char *v32; // rsi
  __int64 v33; // rbx
  FILE *v34; // rax
  FILE *v35; // rax
  FILE *v36; // rax
  FILE *v37; // rax
  FILE *v38; // rax
  FILE *v39; // rax
  __int64 v40; // rcx
  _DWORD **v41; // rbx
  __int64 FirstDeviceByInf; // rax
  __int64 v43; // r8
  unsigned __int64 v44; // rcx
  _DWORD *v45; // rcx
  const wchar_t *v46; // r9
  _WORD *v47; // rcx
  FILE *v48; // rax
  FILE *v49; // rax
  FILE *v50; // rax
  _WORD *v51; // rcx
  _WORD **v52; // rcx
  _WORD *v53; // rdx
  const unsigned __int16 *v54; // rdi
  char *v55; // rsi
  __int64 v57; // [rsp+20h] [rbp-E0h]
  int Item; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v59; // [rsp+48h] [rbp-B8h]
  struct _GUID v61; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v62[32]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v63[40]; // [rsp+88h] [rbp-78h] BYREF
  wchar_t Str[264]; // [rsp+B0h] [rbp-50h] BYREF
  _WORD Src[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v5 = 0;
  if ( qword_1801572C8 )
  {
    if ( !*((_QWORD *)this + 1) )
    {
      v5 = -2147467259;
      v6 = "m_DriverMap is NULL [%#x]";
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
      {
        v7 = 556;
        goto LABEL_9;
      }
      v7 = 560;
LABEL_5:
      AslLogCallPrintf(2, "DriverPackageReaderDrvStore::InitDriverPackageItem", v7, v6, -2147467259);
      if ( EnableDevInvStdErrLog )
      {
        v8 = o___acrt_iob_func_0(2u);
        fprintf(v8, "Error: %s, %u: ", "DriverPackageReaderDrvStore::InitDriverPackageItem", v7);
        v9 = o___acrt_iob_func_0(2u);
        fprintf(v9, v6, 2147500037LL);
        v10 = o___acrt_iob_func_0(2u);
        fprintf(v10, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x2000000, v6, 2147500037LL);
      goto LABEL_9;
    }
    v11 = (const unsigned __int16 *)((char *)a2 + 696);
    v59 = (unsigned __int16 *)((char *)a2 + 696);
    DriverPackageReaderDrvStore::GetStrongNameFromInfPath(this, v62, (char *)a2 + 696);
    std::wstring::operator=((char *)a3 + 128, v62);
    if ( !*((_QWORD *)a3 + 18) )
    {
      v5 = -2147467259;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
      {
        v12 = 571;
      }
      else
      {
        v12 = 575;
        AslLogCallPrintf(
          2,
          "DriverPackageReaderDrvStore::InitDriverPackageItem",
          575,
          "Invalid Driver Strong Name [%#x]",
          -2147467259);
        if ( EnableDevInvStdErrLog )
        {
          v13 = o___acrt_iob_func_0(2u);
          fprintf(v13, "Error: %s, %u: ", "DriverPackageReaderDrvStore::InitDriverPackageItem", 575);
          v14 = o___acrt_iob_func_0(2u);
          fprintf(v14, "Invalid Driver Strong Name [%#x]", -2147467259);
          v15 = o___acrt_iob_func_0(2u);
          fprintf(v15, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "Invalid Driver Strong Name [%#x]", -2147467259);
      }
      AslLogCallPrintf(
        1,
        "DriverPackageReaderDrvStore::InitDriverPackageItem",
        v12,
        "Invalid Driver Strong Name [%#x]",
        -2147467259);
      goto LABEL_112;
    }
    Item = TelCacheProvider::GetItem((TelCacheProvider *)g_DriverPackageStore, a3, 0);
    v16 = *((_QWORD *)a3 + 84);
    v17 = *((_QWORD *)a3 + 83);
    if ( v17 != v16 )
    {
      do
      {
        v18 = *(_QWORD *)(v17 + 16);
        DriverStoreProperty = DriverPackageReaderDrvStore::GetDriverStoreProperty(
                                (_DWORD)this,
                                (unsigned int)v63,
                                *((_QWORD *)this + 2),
                                2,
                                (__int64)v11,
                                *(_QWORD *)v17,
                                *(_DWORD *)(v17 + 8));
        std::wstring::operator=(v18, DriverStoreProperty);
        std::wstring::~wstring(v63);
        v17 += 24;
      }
      while ( v17 != v16 );
      v5 = 0;
    }
    memset_0(Str, 0, 0x208u);
    _o_wcscpy_s(Str, 260, v11);
    v20 = wcsrchr(Str, 0x5Cu);
    if ( !v20 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
      {
        AslLogCallPrintf(3, "DriverPackageReaderDrvStore::InitDriverPackageItem", 597, "Invalid path");
      }
      else
      {
        AslLogCallPrintf(3, "DriverPackageReaderDrvStore::InitDriverPackageItem", 601, "Invalid path");
        if ( EnableDevInvStdErrLog )
        {
          v22 = o___acrt_iob_func_0(2u);
          fprintf(v22, "Info: %s, %u: ", "DriverPackageReaderDrvStore::InitDriverPackageItem", 601);
          v23 = o___acrt_iob_func_0(2u);
          fprintf(v23, "Invalid path");
          v24 = o___acrt_iob_func_0(2u);
          fprintf(v24, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x4000000, "Invalid path");
      }
      v5 = -2147467259;
      goto LABEL_112;
    }
    *v20 = 0;
    v25 = -1;
    v26 = -1;
    do
      ++v26;
    while ( Str[v26] );
    if ( v26 > *((_QWORD *)a3 + 71) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char *)a3 + 544,
        v26,
        v21,
        Str);
    }
    else
    {
      if ( *((_QWORD *)a3 + 71) <= 7u )
        v27 = (char *)a3 + 544;
      else
        v27 = (char *)*((_QWORD *)a3 + 68);
      *((_QWORD *)a3 + 70) = v26;
      v28 = 2 * v26;
      memmove_0(v27, Str, 2 * v26);
      *(_WORD *)&v27[v28] = 0;
      v5 = 0;
    }
    ToLowerCase((char *)a3 + 544);
    if ( !Item )
    {
LABEL_112:
      std::wstring::~wstring(v62);
      return v5;
    }
    v61 = 0;
    memset_0(Src, 0, 0x208u);
    v29 = (const unsigned __int16 *)((char *)a3 + 320);
    if ( *((_QWORD *)a3 + 43) > 7u )
      v29 = *(const unsigned __int16 **)v29;
    WStringUtil::GuidFromString(v29, &v61);
    DevObjClassNameFromGuid(&v61, Src, 260, 0, 0, 0);
    v31 = -1;
    do
      ++v31;
    while ( Src[v31] );
    if ( v31 > *((_QWORD *)a3 + 47) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char *)a3 + 352,
        v31,
        v30,
        Src);
    }
    else
    {
      if ( *((_QWORD *)a3 + 47) <= 7u )
        v32 = (char *)a3 + 352;
      else
        v32 = (char *)*((_QWORD *)a3 + 44);
      *((_QWORD *)a3 + 46) = v31;
      v33 = 2 * v31;
      memmove_0(v32, Src, 2 * v31);
      *(_WORD *)&v32[v33] = 0;
    }
    ToLowerCase((char *)a3 + 352);
    if ( (int)CDriverPackage::InitializeSysFiles(a3, v11) < 0 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
      {
        AslLogCallPrintf(3, "DriverPackageReaderDrvStore::InitDriverPackageItem", 636, "Failed to Initialize sys files");
      }
      else
      {
        AslLogCallPrintf(3, "DriverPackageReaderDrvStore::InitDriverPackageItem", 640, "Failed to Initialize sys files");
        if ( EnableDevInvStdErrLog )
        {
          v34 = o___acrt_iob_func_0(2u);
          fprintf(v34, "Info: %s, %u: ", "DriverPackageReaderDrvStore::InitDriverPackageItem", 640);
          v35 = o___acrt_iob_func_0(2u);
          fprintf(v35, "Failed to Initialize sys files");
          v36 = o___acrt_iob_func_0(2u);
          fprintf(v36, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x4000000, "Failed to Initialize sys files");
      }
    }
    if ( (int)DriverPackageReaderDrvStore::InitDriverPackageHardwareIds(this, v59, a3) < 0 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
      {
        AslLogCallPrintf(
          3,
          "DriverPackageReaderDrvStore::InitDriverPackageItem",
          649,
          "Failed to Initialize hardware ids");
      }
      else
      {
        AslLogCallPrintf(
          3,
          "DriverPackageReaderDrvStore::InitDriverPackageItem",
          653,
          "Failed to Initialize hardware ids");
        if ( EnableDevInvStdErrLog )
        {
          v37 = o___acrt_iob_func_0(2u);
          fprintf(v37, "Info: %s, %u: ", "DriverPackageReaderDrvStore::InitDriverPackageItem", 653);
          v38 = o___acrt_iob_func_0(2u);
          fprintf(v38, "Failed to Initialize hardware ids");
          v39 = o___acrt_iob_func_0(2u);
          fprintf(v39, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x4000000, "Failed to Initialize hardware ids");
      }
    }
    v40 = *(_QWORD *)(*((_QWORD *)this + 1) + 768LL);
    if ( !v40 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
      {
        AslLogCallPrintf(3, "DriverPackageReaderDrvStore::InitDriverPackageItem", 672, "DeviceMap is NULL");
        v5 = 0;
      }
      else
      {
        AslLogCallPrintf(3, "DriverPackageReaderDrvStore::InitDriverPackageItem", 676, "DeviceMap is NULL");
        v5 = 0;
        if ( EnableDevInvStdErrLog )
        {
          v48 = o___acrt_iob_func_0(2u);
          fprintf(v48, "Info: %s, %u: ", "DriverPackageReaderDrvStore::InitDriverPackageItem", 676);
          v49 = o___acrt_iob_func_0(2u);
          fprintf(v49, "DeviceMap is NULL");
          v50 = o___acrt_iob_func_0(2u);
          fprintf(v50, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x4000000, "DeviceMap is NULL");
      }
      if ( *((_QWORD *)a3 + 63) <= 7u )
        v51 = (_WORD *)((char *)a3 + 480);
      else
        v51 = (_WORD *)*((_QWORD *)a3 + 60);
      *((_QWORD *)a3 + 62) = 0;
      *v51 = 0;
      goto LABEL_92;
    }
    v41 = (_DWORD **)((char *)a3 + 480);
    FirstDeviceByInf = CDeviceMap::GetFirstDeviceByInf(v40, (char *)a3 + 56);
    v44 = *((_QWORD *)a3 + 63);
    if ( FirstDeviceByInf )
    {
      if ( v44 )
      {
        if ( v44 <= 7 )
          v45 = (_DWORD *)((char *)a3 + 480);
        else
          v45 = *v41;
        *((_QWORD *)a3 + 62) = 1;
        *v45 = 49;
        goto LABEL_81;
      }
      v46 = L"1";
    }
    else
    {
      if ( v44 )
      {
        if ( v44 <= 7 )
          v47 = (_WORD *)((char *)a3 + 480);
        else
          v47 = *v41;
        *((_QWORD *)a3 + 62) = 1;
        *v47 = a0_0[0];
        v5 = 0;
        v47[1] = 0;
        goto LABEL_92;
      }
      v46 = L"0";
    }
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      (char *)a3 + 480,
      1,
      v43,
      v46);
LABEL_81:
    v5 = 0;
LABEL_92:
    if ( !*((_QWORD *)a3 + 5) )
    {
      v52 = (_WORD **)((char *)a3 + 24);
      if ( *((_QWORD *)a3 + 6) )
      {
        if ( *((_QWORD *)a3 + 6) <= 7u )
          v53 = (_WORD *)((char *)a3 + 24);
        else
          v53 = *v52;
        *((_QWORD *)a3 + 5) = 1;
        *v53 = a0_0[0];
        v53[1] = 0;
      }
      else
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v52,
          1,
          v43,
          L"0");
      }
    }
    if ( !*((_QWORD *)a3 + 30) && *((_QWORD *)a3 + 22) )
    {
      v54 = (const unsigned __int16 *)((char *)a3 + 192);
      do
        ++v25;
      while ( Str[v25] );
      if ( v25 > *((_QWORD *)a3 + 27) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          (char *)a3 + 192,
          v25,
          v43,
          Str);
      }
      else
      {
        if ( *((_QWORD *)a3 + 27) <= 7u )
          v55 = (char *)a3 + 192;
        else
          v55 = *(char **)v54;
        *((_QWORD *)a3 + 26) = v25;
        memmove_0(v55, Str, 2 * v25);
        *(_WORD *)&v55[2 * v25] = 0;
        v5 = 0;
      }
      std::wstring::append((char *)a3 + 192, (void *)L"\\");
      std::wstring::append((char *)a3 + 192);
      if ( *((_QWORD *)a3 + 27) > 7u )
        v54 = *(const unsigned __int16 **)v54;
      CDriverPackage::ParseCatFile(a3, v54);
    }
    goto LABEL_112;
  }
  v5 = -2147467259;
  v6 = "g_DriverPackageStore is NULL [%#x]";
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
  {
    v7 = 547;
    goto LABEL_5;
  }
  v7 = 543;
LABEL_9:
  LODWORD(v57) = -2147467259;
  AslLogCallPrintf(1, "DriverPackageReaderDrvStore::InitDriverPackageItem", v7, v6, v57);
  return v5;
}

```

## disassembly

```asm
0x180052200  mov     [rsp-8+arg_18], rbx
0x180052205  push    rbp
0x180052206  push    rsi
0x180052207  push    rdi
0x180052208  push    r12
0x18005220a  push    r13
0x18005220c  push    r14
0x18005220e  push    r15
0x180052210  lea     rbp, [rsp-3E0h]
0x180052218  sub     rsp, 4E0h
0x18005221f  mov     rax, cs:__security_cookie
0x180052226  xor     rax, rsp
0x180052229  mov     [rbp+410h+var_40], rax
0x180052230  mov     r14, r8
0x180052233  mov     r12, rcx
0x180052236  mov     [rsp+510h+var_4C0], rcx
0x18005223b  xor     ebx, ebx
0x18005223d  cmp     cs:qword_1801572C8, rbx
0x180052244  jnz     loc_180052322
0x18005224a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x180052251  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x180052256  mov     ebx, 80004005h
0x18005225b  lea     r12, aGDriverpackage; "g_DriverPackageStore is NULL [%#x]"
0x180052262  lea     rdi, aDriverpackager_9; "DriverPackageReaderDrvStore::InitDriver"...
0x180052269  xor     r14d, r14d
0x18005226c  test    al, al
0x18005226e  jz      short loc_18005227A
0x180052270  mov     esi, 21Fh
0x180052275  jmp     loc_180052306
0x18005227a  mov     esi, 223h
0x18005227f  mov     r15d, 2
0x180052285  mov     dword ptr [rsp+510h+var_4F0], ebx
0x180052289  mov     r9, r12
0x18005228c  mov     r8, rsi
0x18005228f  mov     rdx, rdi
0x180052292  mov     ecx, r15d
0x180052295  call    AslLogCallPrintf
0x18005229a  cmp     cs:EnableDevInvStdErrLog, r14d
0x1800522a1  jz      short loc_1800522ED
0x1800522a3  mov     ecx, r15d; Ix
0x1800522a6  call    _o___acrt_iob_func_0
0x1800522ab  mov     r9d, esi
0x1800522ae  mov     r8, rdi
0x1800522b1  lea     rdx, Format; "Error: %s, %u: "
0x1800522b8  mov     rcx, rax; Stream
0x1800522bb  call    fprintf
0x1800522c0  mov     ecx, r15d; Ix
0x1800522c3  call    _o___acrt_iob_func_0
0x1800522c8  mov     r8d, ebx
0x1800522cb  mov     rdx, r12; Format
0x1800522ce  mov     rcx, rax; Stream
0x1800522d1  call    fprintf
0x1800522d6  mov     ecx, r15d; Ix
0x1800522d9  call    _o___acrt_iob_func_0
0x1800522de  lea     rdx, asc_18011EAD8; "\n"
0x1800522e5  mov     rcx, rax; Stream
0x1800522e8  call    fprintf
0x1800522ed  cmp     cs:g_DeviceMapLogFunction, r14
0x1800522f4  jz      short loc_180052306
0x1800522f6  mov     r8d, ebx
0x1800522f9  mov     rdx, r12
0x1800522fc  mov     ecx, 2000000h
0x180052301  call    TraceMessageCallback
0x180052306  mov     dword ptr [rsp+510h+var_4F0], ebx
0x18005230a  mov     r9, r12
0x18005230d  mov     r8, rsi
0x180052310  mov     rdx, rdi
0x180052313  mov     ecx, 1
0x180052318  call    AslLogCallPrintf
0x18005231d  jmp     loc_180052AFB
0x180052322  cmp     [rcx+8], rbx
0x180052326  jnz     short loc_18005235F
0x180052328  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x18005232f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x180052334  mov     ebx, 80004005h
0x180052339  lea     rdi, aDriverpackager_9; "DriverPackageReaderDrvStore::InitDriver"...
0x180052340  lea     r12, aMDrivermapIsNu; "m_DriverMap is NULL [%#x]"
0x180052347  xor     r14d, r14d
0x18005234a  test    al, al
0x18005234c  jz      short loc_180052355
0x18005234e  mov     esi, 22Ch
0x180052353  jmp     short loc_180052306
0x180052355  mov     esi, 230h
0x18005235a  jmp     loc_18005227F
0x18005235f  lea     r13, [rdx+2B8h]
0x180052366  mov     [rsp+510h+var_4C8], r13
0x18005236b  mov     r8, r13
0x18005236e  lea     rdx, [rsp+510h+var_4A8]
0x180052373  call    ?GetStrongNameFromInfPath@DriverPackageReaderDrvStore@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; DriverPackageReaderDrvStore::GetStrongNameFromInfPath(ushort const *)
0x180052378  nop
0x180052379  lea     rcx, [r14+80h]
0x180052380  lea     rdx, [rsp+510h+var_4A8]
0x180052385  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18005238a  cmp     [r14+90h], rbx
0x180052391  jnz     loc_18005246F
0x180052397  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x18005239e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x1800523a3  mov     ebx, 80004005h
0x1800523a8  lea     rdi, aDriverpackager_9; "DriverPackageReaderDrvStore::InitDriver"...
0x1800523af  lea     r12, aInvalidDriverS; "Invalid Driver Strong Name [%#x]"
0x1800523b6  xor     r14d, r14d
0x1800523b9  test    al, al
0x1800523bb  jz      short loc_1800523C7
0x1800523bd  mov     esi, 23Bh
0x1800523c2  jmp     loc_180052453
0x1800523c7  mov     dword ptr [rsp+510h+var_4F0], ebx
0x1800523cb  mov     r9, r12
0x1800523ce  mov     esi, 23Fh
0x1800523d3  mov     r8d, esi
0x1800523d6  mov     rdx, rdi
0x1800523d9  mov     r15d, 2
0x1800523df  mov     ecx, r15d
0x1800523e2  call    AslLogCallPrintf
0x1800523e7  cmp     cs:EnableDevInvStdErrLog, r14d
0x1800523ee  jz      short loc_18005243A
0x1800523f0  mov     ecx, r15d; Ix
0x1800523f3  call    _o___acrt_iob_func_0
0x1800523f8  mov     rcx, rax; Stream
0x1800523fb  mov     r9d, esi
0x1800523fe  mov     r8, rdi
0x180052401  lea     rdx, Format; "Error: %s, %u: "
0x180052408  call    fprintf
0x18005240d  mov     ecx, r15d; Ix
0x180052410  call    _o___acrt_iob_func_0
0x180052415  mov     rcx, rax; Stream
0x180052418  mov     r8d, ebx
0x18005241b  mov     rdx, r12; Format
0x18005241e  call    fprintf
0x180052423  mov     ecx, r15d; Ix
0x180052426  call    _o___acrt_iob_func_0
0x18005242b  mov     rcx, rax; Stream
0x18005242e  lea     rdx, asc_18011EAD8; "\n"
0x180052435  call    fprintf
0x18005243a  cmp     cs:g_DeviceMapLogFunction, r14
0x180052441  jz      short loc_180052453
0x180052443  mov     r8d, ebx
0x180052446  mov     rdx, r12
0x180052449  mov     ecx, 2000000h
0x18005244e  call    TraceMessageCallback
0x180052453  mov     dword ptr [rsp+510h+var_4F0], ebx
0x180052457  mov     r9, r12
0x18005245a  mov     r8, rsi
0x18005245d  mov     rdx, rdi
0x180052460  mov     ecx, 1
0x180052465  call    AslLogCallPrintf
0x18005246a  jmp     loc_180052AF1
0x18005246f  xor     r8d, r8d; bool
0x180052472  mov     rdx, r14; struct IAmiInventoryItem *
0x180052475  lea     rcx, ?g_DriverPackageStore@@3VTelCacheProvider@@A; this
0x18005247c  call    ?GetItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@_N@Z; TelCacheProvider::GetItem(IAmiInventoryItem *,bool)
0x180052481  mov     [rsp+510h+var_4D0], eax
0x180052485  mov     rsi, [r14+2A0h]
0x18005248c  mov     rdi, [r14+298h]
0x180052493  mov     r15d, 2
0x180052499  cmp     rdi, rsi
0x18005249c  jz      short loc_1800524E9
0x18005249e  mov     rbx, [rdi+10h]
0x1800524a2  mov     ecx, [rdi+8]
0x1800524a5  mov     [rsp+510h+var_4E0], ecx
0x1800524a9  mov     rax, [rdi]
0x1800524ac  mov     [rsp+510h+var_4E8], rax
0x1800524b1  mov     [rsp+510h+var_4F0], r13
0x1800524b6  mov     r9d, r15d
0x1800524b9  mov     r8, [r12+10h]
0x1800524be  lea     rdx, [rbp+410h+var_488]
0x1800524c2  mov     rcx, r12
0x1800524c5  call    ?GetDriverStoreProperty@DriverPackageReaderDrvStore@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHDRIVERSTORE__@@W4_DRIVERSTORE_OBJECT_TYPE@@PEBGPEBU_DEVPROPKEY@@K@Z; DriverPackageReaderDrvStore::GetDriverStoreProperty(HDRIVERSTORE__ *,_DRIVERSTORE_OBJECT_TYPE,ushort const *,_DEVPROPKEY const *,ulong)
0x1800524ca  mov     rdx, rax
0x1800524cd  mov     rcx, rbx
0x1800524d0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800524d5  lea     rcx, [rbp+410h+var_488]; void *
0x1800524d9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800524de  add     rdi, 18h
0x1800524e2  cmp     rdi, rsi
0x1800524e5  jnz     short loc_18005249E
0x1800524e7  xor     ebx, ebx
0x1800524e9  xor     edx, edx; Val
0x1800524eb  mov     r8d, 208h; Size
0x1800524f1  lea     rcx, [rbp+410h+Str]; void *
0x1800524f5  call    memset_0
0x1800524fa  mov     r8, r13
0x1800524fd  mov     edx, 104h
0x180052502  lea     rcx, [rbp+410h+Str]
0x180052506  call    cs:__imp__o_wcscpy_s
0x18005250c  mov     edx, 5Ch ; '\'; Ch
0x180052511  lea     rcx, [rbp+410h+Str]; Str
0x180052515  call    cs:__imp_wcsrchr
0x18005251b  test    rax, rax
0x18005251e  jnz     loc_1800525E7
0x180052524  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x18005252b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x180052530  lea     r9, aInvalidPath; "Invalid path"
0x180052537  mov     ecx, 3
0x18005253c  test    al, al
0x18005253e  jz      short loc_180052557
0x180052540  mov     r8d, 255h
0x180052546  lea     rdx, aDriverpackager_9; "DriverPackageReaderDrvStore::InitDriver"...
0x18005254d  call    AslLogCallPrintf
0x180052552  jmp     loc_1800525DD
0x180052557  mov     esi, 259h
0x18005255c  mov     r8d, esi
0x18005255f  lea     rdi, aDriverpackager_9; "DriverPackageReaderDrvStore::InitDriver"...
0x180052566  mov     rdx, rdi
0x180052569  call    AslLogCallPrintf
0x18005256e  xor     ebx, ebx
0x180052570  cmp     cs:EnableDevInvStdErrLog, ebx
0x180052576  jz      short loc_1800525C3
0x180052578  mov     ecx, r15d; Ix
0x18005257b  call    _o___acrt_iob_func_0
0x180052580  mov     rcx, rax; Stream
0x180052583  mov     r9d, esi
0x180052586  mov     r8, rdi
0x180052589  lea     rdx, aInfoSU; "Info: %s, %u: "
0x180052590  call    fprintf
0x180052595  mov     ecx, r15d; Ix
0x180052598  call    _o___acrt_iob_func_0
0x18005259d  mov     rcx, rax; Stream
0x1800525a0  lea     rdx, aInvalidPath; "Invalid path"
0x1800525a7  call    fprintf
0x1800525ac  mov     ecx, r15d; Ix
0x1800525af  call    _o___acrt_iob_func_0
0x1800525b4  mov     rcx, rax; Stream
0x1800525b7  lea     rdx, asc_18011EAD8; "\n"
0x1800525be  call    fprintf
0x1800525c3  cmp     cs:g_DeviceMapLogFunction, rbx
0x1800525ca  jz      short loc_1800525DD
0x1800525cc  lea     rdx, aInvalidPath; "Invalid path"
0x1800525d3  mov     ecx, 4000000h
0x1800525d8  call    TraceMessageCallback
0x1800525dd  mov     ebx, 80004005h
0x1800525e2  jmp     loc_180052AF1
0x1800525e7  mov     [rax], bx
0x1800525ea  lea     rdi, [r14+220h]
0x1800525f1  lea     rax, [rbp+410h+Str]
0x1800525f5  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800525f9  mov     rdx, r12
0x1800525fc  inc     rdx
0x1800525ff  cmp     [rax+rdx*2], bx
0x180052603  jnz     short loc_1800525FC
0x180052605  cmp     rdx, [rdi+18h]
0x180052609  ja      short loc_18005263B
0x18005260b  cmp     qword ptr [rdi+18h], 7
0x180052610  jbe     short loc_180052617
0x180052612  mov     rsi, [rdi]
0x180052615  jmp     short loc_18005261A
0x180052617  mov     rsi, rdi
0x18005261a  mov     [rdi+10h], rdx
0x18005261e  lea     rbx, [rdx+rdx]
0x180052622  mov     r8, rbx; Size
0x180052625  lea     rdx, [rbp+410h+Str]; Src
0x180052629  mov     rcx, rsi; void *
0x18005262c  call    memmove_0
0x180052631  xor     eax, eax
0x180052633  mov     [rbx+rsi], ax
0x180052637  xor     ebx, ebx
0x180052639  jmp     short loc_180052647
0x18005263b  lea     r9, [rbp+410h+Str]
0x18005263f  mov     rcx, rdi
0x180052642  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180052647  mov     rcx, rdi
0x18005264a  call    ?ToLowerCase@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ToLowerCase(std::wstring &)
0x18005264f  cmp     [rsp+510h+var_4D0], ebx
0x180052653  jz      loc_180052AF1
0x180052659  xorps   xmm0, xmm0
0x18005265c  movups  xmmword ptr [rsp+510h+var_4B8.Data1], xmm0
0x180052661  xor     edx, edx; Val
0x180052663  mov     r8d, 208h; Size
0x180052669  lea     rcx, [rbp+410h+Src]; void *
0x180052670  call    memset_0
0x180052675  lea     rcx, [r14+140h]
0x18005267c  cmp     qword ptr [rcx+18h], 7
0x180052681  jbe     short loc_180052686
0x180052683  mov     rcx, [rcx]; unsigned __int16 *
0x180052686  lea     rdx, [rsp+510h+var_4B8]; struct _GUID *
0x18005268b  call    ?GuidFromString@WStringUtil@@SAJPEBGAEAU_GUID@@@Z; WStringUtil::GuidFromString(ushort const *,_GUID &)
0x180052690  mov     [rsp+510h+var_4E8], rbx
0x180052695  mov     [rsp+510h+var_4F0], rbx
0x18005269a  xor     r9d, r9d
0x18005269d  mov     r8d, 104h
0x1800526a3  lea     rdx, [rbp+410h+Src]
0x1800526aa  lea     rcx, [rsp+510h+var_4B8]
0x1800526af  call    cs:__imp_DevObjClassNameFromGuid
0x1800526b5  lea     rdi, [r14+160h]
0x1800526bc  lea     rax, [rbp+410h+Src]
0x1800526c3  mov     rdx, r12
0x1800526c6  inc     rdx
0x1800526c9  cmp     [rax+rdx*2], bx
0x1800526cd  jnz     short loc_1800526C6
0x1800526cf  cmp     rdx, [rdi+18h]
0x1800526d3  ja      short loc_180052706
0x1800526d5  cmp     qword ptr [rdi+18h], 7
0x1800526da  jbe     short loc_1800526E1
0x1800526dc  mov     rsi, [rdi]
0x1800526df  jmp     short loc_1800526E4
0x1800526e1  mov     rsi, rdi
0x1800526e4  mov     [rdi+10h], rdx
0x1800526e8  lea     rbx, [rdx+rdx]
0x1800526ec  mov     r8, rbx; Size
0x1800526ef  lea     rdx, [rbp+410h+Src]; Src
0x1800526f6  mov     rcx, rsi; void *
  ... truncated ...
```
