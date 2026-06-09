# DriverPackageReaderDrvStore::InitDriverPackageDetailedItem(_DRIVERPACKAGE_INFO_ALL &,CDriverPackageDetailed &)

- ea: `0x18005164c`
- end: `0x180051bac`
- name: `?InitDriverPackageDetailedItem@DriverPackageReaderDrvStore@@QEAAJAEAU_DRIVERPACKAGE_INFO_ALL@@AEAVCDriverPackageDetailed@@@Z`
- size: `1376`
- prototype: `int(DriverPackageReaderDrvStore *__hidden this, struct _DRIVERPACKAGE_INFO_ALL *, struct CDriverPackageDetailed *)`
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x180053020`

## callees

- `0x180005e40`
- `0x180006d02`
- `0x180006eb8`
- `0x180006ec4`
- `0x180007014`
- `0x18000fa50`
- `0x1800103e0`
- `0x180010a9c`
- `0x180013f50`
- `0x180014b80`
- `0x180016440`
- `0x1800316a0`
- `0x18004ddcc`
- `0x18004df24`
- `0x180050f2c`
- `0x18005164c`
- `0x1800538cc`
- `0x18005e264`
- `0x18006041c`
- `0x180061910`
- `0x180066c10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180051989`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180051989`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005174f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005174f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18005175e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18005175e`
- `DEVOBJ!DevObjClassNameFromGuid` at `0x1800518da`
- `DEVOBJ!DevObjClassNameFromGuid` at `0x1800518da`

## string_xrefs

- `0x18005177c`: `Invalid path`
- `0x1800517df`: `Invalid path`
- `0x18005180a`: `Invalid path`
- `0x180051783`: `DriverPackageReaderDrvStore::InitDriverPackageDetailedItem`
- `0x1800517bf`: `DriverPackageReaderDrvStore::InitDriverPackageDetailedItem`
- `0x180051a9c`: `DriverPackageReaderDrvStore::InitDriverPackageDetailedItem`
- `0x180051ae6`: `DriverPackageReaderDrvStore::InitDriverPackageDetailedItem`
- `0x180051b0b`: `DriverPackageReaderDrvStore::InitDriverPackageDetailedItem`
- `0x180051b6f`: `DriverPackageReaderDrvStore::InitDriverPackageDetailedItem`

## pseudocode

```c
__int64 __fastcall DriverPackageReaderDrvStore::InitDriverPackageDetailedItem(
        DriverPackageReaderDrvStore *this,
        struct _DRIVERPACKAGE_INFO_ALL *a2,
        struct CDriverPackageDetailed *a3)
{
  struct CDriverPackageDetailed *v3; // rdi
  const char *v6; // r15
  __int64 v7; // rdi
  __int64 v8; // r12
  unsigned int v9; // esi
  __int64 v10; // r14
  char *v11; // rdi
  __int64 v12; // rbx
  __int64 DriverStoreProperty; // rax
  wchar_t *v14; // rax
  __int64 v15; // r8
  FILE *v16; // rax
  FILE *v17; // rax
  FILE *v18; // rax
  __int64 result; // rax
  unsigned __int64 v20; // r14
  unsigned __int64 v21; // rdx
  char *v22; // r12
  __int64 v23; // rbx
  const unsigned __int16 *v24; // rcx
  __int64 v25; // r8
  void **v26; // rcx
  void *v27; // r12
  const wchar_t *v28; // rcx
  _QWORD *v29; // rcx
  const unsigned __int16 *v30; // rdx
  __int64 v31; // rdx
  unsigned int v32; // ebx
  __int64 v33; // rsi
  int SysSigningInfo; // eax
  unsigned int v35; // r14d
  _QWORD *v36; // rcx
  FILE *v37; // rax
  FILE *v38; // rax
  FILE *v39; // rax
  __int64 v40; // [rsp+20h] [rbp-E0h]
  __int64 v41; // [rsp+20h] [rbp-E0h]
  struct _GUID v43; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v44[40]; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t Str[264]; // [rsp+80h] [rbp-80h] BYREF
  _WORD Src[264]; // [rsp+290h] [rbp+190h] BYREF

  v3 = a3;
  if ( !qword_1801572C8 )
  {
    v6 = "g_DriverPackageStore is NULL [%#x]";
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
    {
      v7 = 711;
      goto LABEL_67;
    }
    v7 = 715;
LABEL_63:
    AslLogCallPrintf(2, "DriverPackageReaderDrvStore::InitDriverPackageDetailedItem", v7, v6, -2147467259);
    if ( EnableDevInvStdErrLog )
    {
      v37 = o___acrt_iob_func_0(2u);
      fprintf(v37, "Error: %s, %u: ", "DriverPackageReaderDrvStore::InitDriverPackageDetailedItem", v7);
      v38 = o___acrt_iob_func_0(2u);
      fprintf(v38, v6, 2147500037LL);
      v39 = o___acrt_iob_func_0(2u);
      fprintf(v39, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, v6, 2147500037LL);
    goto LABEL_67;
  }
  if ( !*((_QWORD *)this + 1) )
  {
    v6 = "m_DriverMap is NULL [%#x]";
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
    {
      v7 = 724;
LABEL_67:
      LODWORD(v40) = -2147467259;
      AslLogCallPrintf(1, "DriverPackageReaderDrvStore::InitDriverPackageDetailedItem", v7, v6, v40);
      return 2147500037LL;
    }
    v7 = 728;
    goto LABEL_63;
  }
  v8 = *((_QWORD *)a3 + 75);
  v9 = 2;
  v10 = *((_QWORD *)a3 + 74);
  if ( v10 != v8 )
  {
    v11 = (char *)a2 + 696;
    do
    {
      v12 = *(_QWORD *)(v10 + 16);
      DriverStoreProperty = DriverPackageReaderDrvStore::GetDriverStoreProperty(
                              (_DWORD)this,
                              (unsigned int)v44,
                              *((_QWORD *)this + 2),
                              2,
                              (__int64)v11,
                              *(_QWORD *)v10,
                              *(_DWORD *)(v10 + 8));
      std::wstring::operator=(v12, DriverStoreProperty);
      std::wstring::~wstring(v44);
      v10 += 24;
    }
    while ( v10 != v8 );
    v3 = a3;
  }
  _o_wcscpy_s(Str, 260, (char *)a2 + 696);
  v14 = wcsrchr(Str, 0x5Cu);
  if ( !v14 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
    {
      AslLogCallPrintf(3, "DriverPackageReaderDrvStore::InitDriverPackageDetailedItem", 749, "Invalid path");
    }
    else
    {
      AslLogCallPrintf(3, "DriverPackageReaderDrvStore::InitDriverPackageDetailedItem", 753, "Invalid path");
      if ( EnableDevInvStdErrLog )
      {
        v16 = o___acrt_iob_func_0(2u);
        fprintf(v16, "Info: %s, %u: ", "DriverPackageReaderDrvStore::InitDriverPackageDetailedItem", 753);
        v17 = o___acrt_iob_func_0(2u);
        fprintf(v17, "Invalid path");
        v18 = o___acrt_iob_func_0(2u);
        fprintf(v18, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x4000000, "Invalid path");
    }
    return 2147500037LL;
  }
  v20 = -1;
  *v14 = 0;
  v21 = -1;
  do
    ++v21;
  while ( Str[v21] );
  if ( v21 > *((_QWORD *)v3 + 58) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      (char *)v3 + 440,
      v21,
      v15,
      Str);
  }
  else
  {
    if ( *((_QWORD *)v3 + 58) <= 7u )
      v22 = (char *)v3 + 440;
    else
      v22 = (char *)*((_QWORD *)v3 + 55);
    v23 = 2 * v21;
    *((_QWORD *)v3 + 57) = v21;
    memmove_0(v22, Str, 2 * v21);
    *(_WORD *)&v22[v23] = 0;
  }
  v43 = 0;
  memset_0(Src, 0, 0x208u);
  v24 = (const unsigned __int16 *)((char *)v3 + 312);
  if ( *((_QWORD *)v3 + 42) > 7u )
    v24 = *(const unsigned __int16 **)v24;
  WStringUtil::GuidFromString(v24, &v43);
  DevObjClassNameFromGuid(&v43, Src, 260, 0, 0, 0);
  v26 = (void **)((char *)v3 + 344);
  do
    ++v20;
  while ( Src[v20] );
  if ( v20 > *((_QWORD *)v3 + 46) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v26, v20, v25, Src);
  }
  else
  {
    if ( *((_QWORD *)v3 + 46) <= 7u )
      v27 = (char *)v3 + 344;
    else
      v27 = *v26;
    *((_QWORD *)v3 + 45) = v20;
    memmove_0(v27, Src, 2 * v20);
    *((_WORD *)v27 + v20) = 0;
  }
  v28 = (const wchar_t *)((char *)v3 + 472);
  if ( *((_QWORD *)v3 + 62) > 7u )
    v28 = *(const wchar_t **)v28;
  if ( *((_QWORD *)v3 + 61) == 1 && !wmemcmp(v28, L"1", 1u) )
    goto LABEL_44;
  v29 = (_QWORD *)((char *)v3 + 376);
  if ( *((_QWORD *)v3 + 50) > 7u )
    v29 = (_QWORD *)*v29;
  if ( !(unsigned int)_o__wcsnicmp(v29, L"Microsoft", 9) )
  {
    v9 = 4;
LABEL_44:
    *((_DWORD *)v3 + 4) = v9;
    goto LABEL_46;
  }
  *((_DWORD *)v3 + 4) = 1;
  v9 = 1;
LABEL_46:
  IntToStr(v9, (char *)v3 + 24);
  v30 = (const unsigned __int16 *)((char *)v3 + 88);
  if ( *((_QWORD *)v3 + 14) > 7u )
    v30 = *(const unsigned __int16 **)v30;
  result = CDriverPackageDetailed::InitializeSysFiles(v3, v30);
  if ( (int)result >= 0 )
  {
    if ( *((_QWORD *)v3 + 21) && *((_QWORD *)v3 + 57) )
    {
      std::wstring::operator=((char *)v3 + 184, (char *)v3 + 440);
      std::wstring::append((char *)v3 + 184, (void *)L"\\");
      std::wstring::append((char *)v3 + 184);
    }
    v31 = *((_QWORD *)v3 + 71);
    if ( (*((_QWORD *)v3 + 72) - v31) >> 5 )
    {
      v32 = 0;
      while ( 1 )
      {
        v33 = 32LL * v32;
        SysSigningInfo = CDriverPackageDetailed::GetSysSigningInfo(v3, v33 + v31);
        v35 = SysSigningInfo;
        if ( SysSigningInfo < 0 )
          break;
        v31 = *((_QWORD *)v3 + 71);
        if ( ++v32 >= (unsigned __int64)((*((_QWORD *)v3 + 72) - v31) >> 5) )
          return 0;
      }
      v36 = (_QWORD *)(v33 + *((_QWORD *)v3 + 71));
      if ( v36[3] > 7u )
        v36 = (_QWORD *)*v36;
      LODWORD(v41) = SysSigningInfo;
      AslLogCallPrintf(
        3,
        "DriverPackageReaderDrvStore::InitDriverPackageDetailedItem",
        810,
        "0x%08x Failed to get sys signing info for %ws",
        v41,
        v36);
      return v35;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005164c  mov     [rsp-8+arg_18], rbx
0x180051651  push    rbp
0x180051652  push    rsi
0x180051653  push    rdi
0x180051654  push    r12
0x180051656  push    r13
0x180051658  push    r14
0x18005165a  push    r15
0x18005165c  lea     rbp, [rsp-3B0h]
0x180051664  sub     rsp, 4B0h
0x18005166b  mov     rax, cs:__security_cookie
0x180051672  xor     rax, rsp
0x180051675  mov     [rbp+3E0h+var_40], rax
0x18005167c  xor     r14d, r14d
0x18005167f  mov     [rsp+4E0h+var_4A0], r8
0x180051684  cmp     cs:qword_1801572C8, r14
0x18005168b  mov     rdi, r8
0x18005168e  mov     r13, rdx
0x180051691  mov     r15, rcx
0x180051694  jz      loc_180051AB0
0x18005169a  cmp     [rcx+8], r14
0x18005169e  jnz     short loc_1800516D0
0x1800516a0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x1800516a7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x1800516ac  lea     r15, aMDrivermapIsNu; "m_DriverMap is NULL [%#x]"
0x1800516b3  mov     ebx, 80004005h
0x1800516b8  test    al, al
0x1800516ba  jz      short loc_1800516C6
0x1800516bc  mov     edi, 2D4h
0x1800516c1  jmp     loc_180051B65
0x1800516c6  mov     edi, 2D8h
0x1800516cb  jmp     loc_180051ADB
0x1800516d0  mov     r12, [r8+258h]
0x1800516d7  mov     esi, 2
0x1800516dc  mov     r14, [r8+250h]
0x1800516e3  cmp     r14, r12
0x1800516e6  jz      short loc_18005173F
0x1800516e8  lea     rdi, [rdx+2B8h]
0x1800516ef  mov     eax, [r14+8]
0x1800516f3  lea     rdx, [rsp+4E0h+var_488]
0x1800516f8  mov     r8, [r15+10h]
0x1800516fc  mov     r9d, esi
0x1800516ff  mov     rbx, [r14+10h]
0x180051703  mov     rcx, r15
0x180051706  mov     [rsp+4E0h+var_4B0], eax
0x18005170a  mov     rax, [r14]
0x18005170d  mov     [rsp+4E0h+var_4B8], rax
0x180051712  mov     [rsp+4E0h+var_4C0], rdi
0x180051717  call    ?GetDriverStoreProperty@DriverPackageReaderDrvStore@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHDRIVERSTORE__@@W4_DRIVERSTORE_OBJECT_TYPE@@PEBGPEBU_DEVPROPKEY@@K@Z; DriverPackageReaderDrvStore::GetDriverStoreProperty(HDRIVERSTORE__ *,_DRIVERSTORE_OBJECT_TYPE,ushort const *,_DEVPROPKEY const *,ulong)
0x18005171c  mov     rdx, rax
0x18005171f  mov     rcx, rbx
0x180051722  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180051727  lea     rcx, [rsp+4E0h+var_488]; void *
0x18005172c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180051731  add     r14, 18h
0x180051735  cmp     r14, r12
0x180051738  jnz     short loc_1800516EF
0x18005173a  mov     rdi, [rsp+4E0h+var_4A0]
0x18005173f  lea     r8, [r13+2B8h]
0x180051746  mov     edx, 104h
0x18005174b  lea     rcx, [rbp+3E0h+Str]
0x18005174f  call    cs:__imp__o_wcscpy_s
0x180051755  mov     edx, 5Ch ; '\'; Ch
0x18005175a  lea     rcx, [rbp+3E0h+Str]; Str
0x18005175e  call    cs:__imp_wcsrchr
0x180051764  xor     r13d, r13d
0x180051767  test    rax, rax
0x18005176a  jnz     loc_180051825
0x180051770  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x180051777  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x18005177c  lea     r9, aInvalidPath; "Invalid path"
0x180051783  lea     rdx, aDriverpackager_0; "DriverPackageReaderDrvStore::InitDriver"...
0x18005178a  lea     ecx, [r13+3]
0x18005178e  test    al, al
0x180051790  jz      short loc_18005179F
0x180051792  mov     r8d, 2EDh
0x180051798  call    AslLogCallPrintf
0x18005179d  jmp     short loc_18005181B
0x18005179f  mov     ebx, 2F1h
0x1800517a4  mov     r8d, ebx
0x1800517a7  call    AslLogCallPrintf
0x1800517ac  cmp     cs:EnableDevInvStdErrLog, r13d
0x1800517b3  jz      short loc_180051801
0x1800517b5  mov     ecx, esi; Ix
0x1800517b7  call    _o___acrt_iob_func_0
0x1800517bc  mov     rcx, rax; Stream
0x1800517bf  lea     r8, aDriverpackager_0; "DriverPackageReaderDrvStore::InitDriver"...
0x1800517c6  mov     r9d, ebx
0x1800517c9  lea     rdx, aInfoSU; "Info: %s, %u: "
0x1800517d0  call    fprintf
0x1800517d5  mov     ecx, esi; Ix
0x1800517d7  call    _o___acrt_iob_func_0
0x1800517dc  mov     rcx, rax; Stream
0x1800517df  lea     rdx, aInvalidPath; "Invalid path"
0x1800517e6  call    fprintf
0x1800517eb  mov     ecx, esi; Ix
0x1800517ed  call    _o___acrt_iob_func_0
0x1800517f2  mov     rcx, rax; Stream
0x1800517f5  lea     rdx, asc_18011EAD8; "\n"
0x1800517fc  call    fprintf
0x180051801  cmp     cs:g_DeviceMapLogFunction, r13
0x180051808  jz      short loc_18005181B
0x18005180a  lea     rdx, aInvalidPath; "Invalid path"
0x180051811  mov     ecx, 4000000h
0x180051816  call    TraceMessageCallback
0x18005181b  mov     eax, 80004005h
0x180051820  jmp     loc_180051B82
0x180051825  or      r14, 0FFFFFFFFFFFFFFFFh
0x180051829  mov     [rax], r13w
0x18005182d  mov     rdx, r14
0x180051830  lea     r15, [rdi+1B8h]
0x180051837  lea     rax, [rbp+3E0h+Str]
0x18005183b  inc     rdx
0x18005183e  cmp     [rax+rdx*2], r13w
0x180051843  jnz     short loc_18005183B
0x180051845  cmp     rdx, [r15+18h]
0x180051849  ja      short loc_180051878
0x18005184b  cmp     qword ptr [r15+18h], 7
0x180051850  jbe     short loc_180051857
0x180051852  mov     r12, [r15]
0x180051855  jmp     short loc_18005185A
0x180051857  mov     r12, r15
0x18005185a  lea     rbx, [rdx+rdx]
0x18005185e  mov     [r15+10h], rdx
0x180051862  mov     r8, rbx; Size
0x180051865  lea     rdx, [rbp+3E0h+Str]; Src
0x180051869  mov     rcx, r12; void *
0x18005186c  call    memmove_0
0x180051871  mov     [rbx+r12], r13w
0x180051876  jmp     short loc_180051884
0x180051878  lea     r9, [rbp+3E0h+Str]
0x18005187c  mov     rcx, r15
0x18005187f  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180051884  xorps   xmm0, xmm0
0x180051887  lea     rcx, [rbp+3E0h+Src]; void *
0x18005188e  xor     edx, edx; Val
0x180051890  mov     r8d, 208h; Size
0x180051896  movups  xmmword ptr [rsp+4E0h+var_498.Data1], xmm0
0x18005189b  call    memset_0
0x1800518a0  lea     rcx, [rdi+138h]
0x1800518a7  cmp     qword ptr [rcx+18h], 7
0x1800518ac  jbe     short loc_1800518B1
0x1800518ae  mov     rcx, [rcx]; unsigned __int16 *
0x1800518b1  lea     rdx, [rsp+4E0h+var_498]; struct _GUID *
0x1800518b6  call    ?GuidFromString@WStringUtil@@SAJPEBGAEAU_GUID@@@Z; WStringUtil::GuidFromString(ushort const *,_GUID &)
0x1800518bb  xor     r9d, r9d
0x1800518be  mov     [rsp+4E0h+var_4B8], r13
0x1800518c3  mov     r8d, 104h
0x1800518c9  mov     [rsp+4E0h+var_4C0], r13
0x1800518ce  lea     rdx, [rbp+3E0h+Src]
0x1800518d5  lea     rcx, [rsp+4E0h+var_498]
0x1800518da  call    cs:__imp_DevObjClassNameFromGuid
0x1800518e0  lea     rcx, [rdi+158h]
0x1800518e7  lea     rax, [rbp+3E0h+Src]
0x1800518ee  inc     r14
0x1800518f1  cmp     [rax+r14*2], r13w
0x1800518f6  jnz     short loc_1800518EE
0x1800518f8  cmp     r14, [rcx+18h]
0x1800518fc  ja      short loc_18005192E
0x1800518fe  cmp     qword ptr [rcx+18h], 7
0x180051903  jbe     short loc_18005190A
0x180051905  mov     r12, [rcx]
0x180051908  jmp     short loc_18005190D
0x18005190a  mov     r12, rcx
0x18005190d  mov     [rcx+10h], r14
0x180051911  lea     rbx, [r14+r14]
0x180051915  mov     r8, rbx; Size
0x180051918  lea     rdx, [rbp+3E0h+Src]; Src
0x18005191f  mov     rcx, r12; void *
0x180051922  call    memmove_0
0x180051927  mov     [rbx+r12], r13w
0x18005192c  jmp     short loc_18005193D
0x18005192e  lea     r9, [rbp+3E0h+Src]
0x180051935  mov     rdx, r14
0x180051938  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18005193d  lea     rcx, [rdi+1D8h]
0x180051944  cmp     qword ptr [rcx+18h], 7
0x180051949  mov     rax, [rcx+10h]
0x18005194d  jbe     short loc_180051952
0x18005194f  mov     rcx, [rcx]; S1
0x180051952  cmp     rax, 1
0x180051956  jnz     short loc_18005196B
0x180051958  mov     r8, rax; N
0x18005195b  lea     rdx, a1; "1"
0x180051962  call    wmemcmp
0x180051967  test    eax, eax
0x180051969  jz      short loc_180051996
0x18005196b  lea     rcx, [rdi+178h]
0x180051972  cmp     qword ptr [rcx+18h], 7
0x180051977  jbe     short loc_18005197C
0x180051979  mov     rcx, [rcx]
0x18005197c  mov     r8d, 9
0x180051982  lea     rdx, aMicrosoft; "Microsoft"
0x180051989  call    cs:__imp__o__wcsnicmp
0x18005198f  test    eax, eax
0x180051991  jnz     short loc_18005199B
0x180051993  lea     esi, [rax+4]
0x180051996  mov     [rdi+10h], esi
0x180051999  jmp     short loc_1800519A7
0x18005199b  mov     dword ptr [rdi+10h], 1
0x1800519a2  mov     esi, 1
0x1800519a7  lea     rdx, [rdi+18h]
0x1800519ab  mov     ecx, esi
0x1800519ad  call    ?IntToStr@@YAKKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IntToStr(ulong,std::wstring &)
0x1800519b2  lea     rdx, [rdi+58h]
0x1800519b6  cmp     qword ptr [rdx+18h], 7
0x1800519bb  jbe     short loc_1800519C0
0x1800519bd  mov     rdx, [rdx]; unsigned __int16 *
0x1800519c0  mov     rcx, rdi; this
0x1800519c3  call    ?InitializeSysFiles@CDriverPackageDetailed@@AEAAJPEBG@Z; CDriverPackageDetailed::InitializeSysFiles(ushort const *)
0x1800519c8  test    eax, eax
0x1800519ca  js      loc_180051B82
0x1800519d0  lea     rsi, [rdi+98h]
0x1800519d7  cmp     [rsi+10h], r13
0x1800519db  jz      short loc_180051A12
0x1800519dd  cmp     [rdi+1C8h], r13
0x1800519e4  jz      short loc_180051A12
0x1800519e6  lea     rbx, [rdi+0B8h]
0x1800519ed  mov     rdx, r15
0x1800519f0  mov     rcx, rbx
0x1800519f3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800519f8  lea     rdx, SubBlock; "\\"
0x1800519ff  mov     rcx, rbx; Src
0x180051a02  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180051a07  mov     rdx, rsi
0x180051a0a  mov     rcx, rbx; Src
0x180051a0d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180051a12  mov     rdx, [rdi+238h]
0x180051a19  mov     rax, [rdi+240h]
0x180051a20  sub     rax, rdx
0x180051a23  sar     rax, 5
0x180051a27  test    rax, rax
0x180051a2a  jz      short loc_180051A65
0x180051a2c  mov     ebx, r13d
0x180051a2f  mov     esi, ebx
0x180051a31  mov     rcx, rdi
0x180051a34  shl     rsi, 5
0x180051a38  add     rdx, rsi
0x180051a3b  call    ?GetSysSigningInfo@CDriverPackageDetailed@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CDriverPackageDetailed::GetSysSigningInfo(std::wstring const &)
0x180051a40  mov     r14d, eax
0x180051a43  test    eax, eax
0x180051a45  js      short loc_180051A6C
0x180051a47  mov     rdx, [rdi+238h]
0x180051a4e  inc     ebx
0x180051a50  mov     rcx, [rdi+240h]
0x180051a57  sub     rcx, rdx
0x180051a5a  mov     eax, ebx
0x180051a5c  sar     rcx, 5
0x180051a60  cmp     rax, rcx
0x180051a63  jb      short loc_180051A2F
0x180051a65  xor     eax, eax
0x180051a67  jmp     loc_180051B82
0x180051a6c  mov     rcx, [rdi+238h]
0x180051a73  add     rcx, rsi
0x180051a76  cmp     qword ptr [rcx+18h], 7
0x180051a7b  jbe     short loc_180051A80
0x180051a7d  mov     rcx, [rcx]
0x180051a80  mov     [rsp+4E0h+var_4B8], rcx
0x180051a85  lea     r9, a0x08xFailedToG_2; "0x%08x Failed to get sys signing info f"...
0x180051a8c  mov     ecx, 3
0x180051a91  mov     dword ptr [rsp+4E0h+var_4C0], r14d
0x180051a96  mov     r8d, 32Ah
0x180051a9c  lea     rdx, aDriverpackager_0; "DriverPackageReaderDrvStore::InitDriver"...
0x180051aa3  call    AslLogCallPrintf
0x180051aa8  mov     eax, r14d
0x180051aab  jmp     loc_180051B82
0x180051ab0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x180051ab7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x180051abc  lea     r15, aGDriverpackage; "g_DriverPackageStore is NULL [%#x]"
0x180051ac3  mov     ebx, 80004005h
0x180051ac8  test    al, al
0x180051aca  jz      short loc_180051AD6
0x180051acc  mov     edi, 2C7h
0x180051ad1  jmp     loc_180051B65
0x180051ad6  mov     edi, 2CBh
0x180051adb  mov     esi, 2
0x180051ae0  mov     dword ptr [rsp+4E0h+var_4C0], ebx
0x180051ae4  mov     ecx, esi
0x180051ae6  lea     rdx, aDriverpackager_0; "DriverPackageReaderDrvStore::InitDriver"...
0x180051aed  mov     r9, r15
0x180051af0  mov     r8, rdi
0x180051af3  call    AslLogCallPrintf
0x180051af8  cmp     cs:EnableDevInvStdErrLog, r14d
0x180051aff  jz      short loc_180051B4C
0x180051b01  mov     ecx, esi; Ix
0x180051b03  call    _o___acrt_iob_func_0
0x180051b08  mov     r9d, edi
0x180051b0b  lea     r8, aDriverpackager_0; "DriverPackageReaderDrvStore::InitDriver"...
0x180051b12  lea     rdx, Format; "Error: %s, %u: "
0x180051b19  mov     rcx, rax; Stream
0x180051b1c  call    fprintf
0x180051b21  mov     ecx, esi; Ix
0x180051b23  call    _o___acrt_iob_func_0
0x180051b28  mov     r8d, ebx
0x180051b2b  mov     rdx, r15; Format
0x180051b2e  mov     rcx, rax; Stream
0x180051b31  call    fprintf
0x180051b36  mov     ecx, esi; Ix
0x180051b38  call    _o___acrt_iob_func_0
0x180051b3d  lea     rdx, asc_18011EAD8; "\n"
  ... truncated ...
```
