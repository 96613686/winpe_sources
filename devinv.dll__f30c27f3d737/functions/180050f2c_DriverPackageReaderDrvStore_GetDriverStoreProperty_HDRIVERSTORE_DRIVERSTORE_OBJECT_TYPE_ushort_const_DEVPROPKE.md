# DriverPackageReaderDrvStore::GetDriverStoreProperty(HDRIVERSTORE__ *,_DRIVERSTORE_OBJECT_TYPE,ushort const *,_DEVPROPKEY const *,ulong)

- ea: `0x180050f2c`
- end: `0x180051554`
- name: `?GetDriverStoreProperty@DriverPackageReaderDrvStore@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHDRIVERSTORE__@@W4_DRIVERSTORE_OBJECT_TYPE@@PEBGPEBU_DEVPROPKEY@@K@Z`
- size: `1576`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops`

## callers

- `0x18005164c`
- `0x180052200`

## callees

- `0x180005e40`
- `0x180006210`
- `0x18000624c`
- `0x1800066f0`
- `0x180006d02`
- `0x180006eb8`
- `0x180007014`
- `0x18000fa50`
- `0x1800103e0`
- `0x180016598`
- `0x180017600`
- `0x180018934`
- `0x180050f2c`
- `0x1800538cc`
- `0x18005c6c0`
- `0x18005c8f8`
- `0x18005dc44`
- `0x18005dd34`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `drvstore!DriverStoreGetObjectPropertyW` at `0x180050fd6`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x1800511bb`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x180050fd6`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x1800511bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050fe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800513dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051409`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005145c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005149e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050fe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800513dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051409`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005145c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005149e`

## string_xrefs

- `0x1800510b3`: `DriverPackageReaderDrvStore::GetDriverStoreProperty`
- `0x1800510de`: `DriverPackageReaderDrvStore::GetDriverStoreProperty`
- `0x18005114d`: `DriverPackageReaderDrvStore::GetDriverStoreProperty`
- `0x1800513f3`: `DriverPackageReaderDrvStore::GetDriverStoreProperty`
- `0x180051422`: `DriverPackageReaderDrvStore::GetDriverStoreProperty`
- `0x180051449`: `DriverPackageReaderDrvStore::GetDriverStoreProperty`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DriverPackageReaderDrvStore::GetDriverStoreProperty(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7)
{
  __int64 v8; // r15
  _BYTE *v9; // r14
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rbx
  _BYTE *v13; // rax
  unsigned __int64 v14; // rcx
  __int64 v15; // rdi
  FILE *v16; // rax
  FILE *v17; // rax
  FILE *v18; // rax
  __int64 v19; // r8
  _WORD *i; // rax
  __int64 v21; // rcx
  void **v22; // rdi
  size_t v23; // rbx
  const wchar_t *v24; // r9
  __int64 v25; // rdx
  void **v26; // rax
  void **v27; // rcx
  DWORD LastError; // eax
  DWORD v29; // eax
  FILE *v30; // rax
  DWORD v31; // ebx
  FILE *v32; // rax
  FILE *v33; // rax
  DWORD v34; // eax
  FILE *v36; // rax
  FILE *v37; // rax
  FILE *v38; // rax
  int v39; // [rsp+50h] [rbp-98h] BYREF
  unsigned int v40; // [rsp+54h] [rbp-94h] BYREF
  _BYTE *v41; // [rsp+58h] [rbp-90h]
  _WORD *v42; // [rsp+60h] [rbp-88h] BYREF
  __int128 v43; // [rsp+68h] [rbp-80h] BYREF
  __int64 v44; // [rsp+78h] [rbp-70h]
  __int64 v45; // [rsp+88h] [rbp-60h]
  void *v46[2]; // [rsp+90h] [rbp-58h] BYREF
  __int128 v47; // [rsp+A0h] [rbp-48h]

  v8 = a2;
  v45 = a2;
  *(_OWORD *)v46 = 0;
  *(_QWORD *)&v47 = 0;
  *((_QWORD *)&v47 + 1) = 7;
  LOWORD(v46[0]) = 0;
  v9 = 0;
  v39 = 0;
  v40 = 0;
  v43 = 0;
  v44 = 0;
  if ( (unsigned int)DriverStoreGetObjectPropertyW(a3, 2, a5, a6, &v39, 0, 0, &v40, 0)
    || GetLastError() != 122
    || v39 != a7 )
  {
LABEL_70:
    operator delete(v9);
    *(_OWORD *)v8 = *(_OWORD *)v46;
    *(_OWORD *)(v8 + 16) = v47;
    *(_QWORD *)&v47 = 0;
    *((_QWORD *)&v47 + 1) = 7;
    LOWORD(v46[0]) = 0;
    goto LABEL_71;
  }
  switch ( v39 )
  {
    case 9:
      goto LABEL_15;
    case 13:
      v14 = 16;
      goto LABEL_16;
    case 16:
LABEL_15:
      v14 = 8;
      goto LABEL_16;
    case 17:
      v14 = 1;
LABEL_16:
      v13 = operator new(v14, (const struct std::nothrow_t *)std::nothrow);
      v12 = -1;
      goto LABEL_17;
  }
  if ( v39 != 18 && v39 != 8210 )
    goto LABEL_18;
  v10 = (unsigned __int64)v40 >> 1;
  v11 = 2 * v10;
  v12 = -1;
  if ( !is_mul_ok(v10, 2u) )
    v11 = -1;
  v13 = operator new[](v11, (const struct std::nothrow_t *)std::nothrow);
LABEL_17:
  v9 = v13;
  v41 = v13;
  if ( v13 )
  {
    if ( !(unsigned int)DriverStoreGetObjectPropertyW(a3, 2, a5, a6, &v39, v13, v40, &v40, 0) || v39 != a7 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
      {
        LastError = GetLastError();
        AslLogCallPrintf(
          3,
          "DriverPackageReaderDrvStore::GetDriverStoreProperty",
          999,
          "Failed to get DriverStore Object Property %#x",
          LastError);
      }
      else
      {
        v29 = GetLastError();
        AslLogCallPrintf(
          3,
          "DriverPackageReaderDrvStore::GetDriverStoreProperty",
          1003,
          "Failed to get DriverStore Object Property %#x",
          v29);
        if ( EnableDevInvStdErrLog )
        {
          v30 = o___acrt_iob_func_0(2u);
          fprintf(v30, "Info: %s, %u: ", "DriverPackageReaderDrvStore::GetDriverStoreProperty", 1003);
          v31 = GetLastError();
          v32 = o___acrt_iob_func_0(2u);
          fprintf(v32, "Failed to get DriverStore Object Property %#x", v31);
          v33 = o___acrt_iob_func_0(2u);
          fprintf(v33, "\n");
        }
        if ( g_DeviceMapLogFunction )
        {
          v34 = GetLastError();
          TraceMessageCallback(0x4000000, "Failed to get DriverStore Object Property %#x", v34);
        }
      }
      goto LABEL_70;
    }
    try
    {
      if ( v39 == 9 )
      {
        GetVersionFromUlong64(v9, v46);
      }
      else if ( v39 == 13 )
      {
        GuidToString(v9, v46);
      }
      else if ( v39 == 16 )
      {
        ConvertFileTimeToDateStrYearFirst(v9, v46);
      }
      else
      {
        if ( v39 == 17 )
        {
          if ( *v9 == 0xFF )
          {
            if ( *((_QWORD *)&v47 + 1) )
            {
              v26 = v46;
              if ( *((_QWORD *)&v47 + 1) > 7u )
                v26 = (void **)v46[0];
              *(_QWORD *)&v47 = 1;
              *(_DWORD *)v26 = 49;
              goto LABEL_81;
            }
            v24 = L"1";
            v25 = 1;
          }
          else
          {
            v27 = v46;
            if ( *((_QWORD *)&v47 + 1) )
            {
              if ( *((_QWORD *)&v47 + 1) > 7u )
                v27 = (void **)v46[0];
              *(_QWORD *)&v47 = 1;
              *(_WORD *)v27 = a0_0[0];
              *((_WORD *)v27 + 1) = 0;
              goto LABEL_81;
            }
            v24 = L"0";
            v25 = 1;
          }
        }
        else
        {
          if ( v39 != 18 )
          {
            if ( v39 == 8210 )
            {
              for ( i = v9; ; i += v21 + 1 )
              {
                v42 = i;
                if ( !*i )
                  break;
                if ( *((_QWORD *)&v43 + 1) == v44 )
                {
                  std::vector<CDevice *>::_Emplace_reallocate<CDevice * const &>(&v43, *((_QWORD *)&v43 + 1), &v42);
                  i = v42;
                }
                else
                {
                  **((_QWORD **)&v43 + 1) = i;
                  *((_QWORD *)&v43 + 1) += 8LL;
                }
                v21 = -1;
                do
                  ++v21;
                while ( i[v21] );
              }
              ConvertListToStr(&v43, v46);
            }
            goto LABEL_81;
          }
          do
            ++v12;
          while ( *(_WORD *)&v9[2 * v12] );
          if ( v12 <= *((_QWORD *)&v47 + 1) )
          {
            v22 = v46;
            if ( *((_QWORD *)&v47 + 1) > 7u )
              v22 = (void **)v46[0];
            *(_QWORD *)&v47 = v12;
            v23 = 2 * v12;
            memmove_0(v22, v9, v23);
            *(_WORD *)((char *)v22 + v23) = 0;
            goto LABEL_81;
          }
          v24 = (const wchar_t *)v9;
          v25 = v12;
        }
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v46,
          v25,
          v19,
          v24);
      }
    }
    catch ( std::bad_alloc )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
      {
        AslLogCallPrintf(1, "DriverPackageReaderDrvStore::GetDriverStoreProperty", 1048, "Out of memory");
      }
      else
      {
        AslLogCallPrintf(2, "DriverPackageReaderDrvStore::GetDriverStoreProperty", 1052, "Out of memory");
        if ( EnableDevInvStdErrLog )
        {
          v36 = o___acrt_iob_func_0(2u);
          fprintf(v36, "Error: %s, %u: ", "DriverPackageReaderDrvStore::GetDriverStoreProperty", 1052);
          v37 = o___acrt_iob_func_0(2u);
          fprintf(v37, "Out of memory");
          v38 = o___acrt_iob_func_0(2u);
          fprintf(v38, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "Out of memory");
      }
      v9 = v41;
      v8 = v45;
      goto LABEL_70;
    }
LABEL_81:
    goto LABEL_70;
  }
LABEL_18:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
  {
    v15 = 974;
  }
  else
  {
    v15 = 978;
    AslLogCallPrintf(2, "DriverPackageReaderDrvStore::GetDriverStoreProperty", 978, "Out of memory [%#x]", -2147024882);
    if ( EnableDevInvStdErrLog )
    {
      v16 = o___acrt_iob_func_0(2u);
      fprintf(v16, "Error: %s, %u: ", "DriverPackageReaderDrvStore::GetDriverStoreProperty", 978);
      v17 = o___acrt_iob_func_0(2u);
      fprintf(v17, "Out of memory [%#x]", -2147024882);
      v18 = o___acrt_iob_func_0(2u);
      fprintf(v18, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "Out of memory [%#x]", -2147024882);
  }
  AslLogCallPrintf(1, "DriverPackageReaderDrvStore::GetDriverStoreProperty", v15, "Out of memory [%#x]", -2147024882);
  *(_OWORD *)v8 = 0;
  *(_QWORD *)(v8 + 16) = 0;
  *(_QWORD *)(v8 + 24) = 0;
  std::wstring::_Construct<1,unsigned short const *>(v8, &S2, 0);
LABEL_71:
  std::vector<CDriverPackageDetailed *>::~vector<CDriverPackageDetailed *>(&v43);
  std::wstring::~wstring(v46);
  return v8;
}

```

## disassembly

```asm
0x180050f2c  mov     r11, rsp
0x180050f2f  mov     [r11+8], rbx
0x180050f33  mov     [r11+20h], rsi
0x180050f37  push    rdi
0x180050f38  push    r12
0x180050f3a  push    r13
0x180050f3c  push    r14
0x180050f3e  push    r15
0x180050f40  sub     rsp, 0C0h
0x180050f47  mov     rax, cs:__security_cookie
0x180050f4e  xor     rax, rsp
0x180050f51  mov     [rsp+0E8h+var_38], rax
0x180050f59  mov     rdi, r8
0x180050f5c  mov     r15, rdx
0x180050f5f  mov     [rsp+0E8h+var_60], rdx
0x180050f67  mov     r12, [rsp+0E8h+arg_20]
0x180050f6f  mov     r13, [rsp+0E8h+arg_28]
0x180050f77  xor     esi, esi
0x180050f79  xorps   xmm0, xmm0
0x180050f7c  movups  xmmword ptr [r11-58h], xmm0
0x180050f81  mov     [r11-48h], rsi
0x180050f85  mov     qword ptr [r11-40h], 7
0x180050f8d  mov     [r11-58h], si
0x180050f92  mov     r14d, esi
0x180050f95  mov     [rsp+0E8h+var_98], esi
0x180050f99  mov     [rsp+0E8h+var_94], esi
0x180050f9d  movdqu  [rsp+0E8h+var_80], xmm0
0x180050fa3  mov     [r11-70h], rsi
0x180050fa7  mov     [rsp+0E8h+var_A8], esi
0x180050fab  lea     rax, [rsp+0E8h+var_94]
0x180050fb0  mov     [rsp+0E8h+var_B0], rax
0x180050fb5  mov     [rsp+0E8h+var_B8], esi
0x180050fb9  mov     [rsp+0E8h+var_C0], rsi
0x180050fbe  lea     rax, [rsp+0E8h+var_98]
0x180050fc3  mov     [rsp+0E8h+var_C8], rax
0x180050fc8  mov     r9, r13
0x180050fcb  mov     r8, r12
0x180050fce  lea     ebx, [rsi+2]
0x180050fd1  mov     edx, ebx
0x180050fd3  mov     rcx, rdi
0x180050fd6  call    cs:__imp_DriverStoreGetObjectPropertyW
0x180050fdc  test    eax, eax
0x180050fde  jnz     loc_1800514B8
0x180050fe4  call    cs:__imp_GetLastError
0x180050fea  cmp     eax, 7Ah ; 'z'
0x180050fed  jnz     loc_1800514B8
0x180050ff3  mov     eax, [rsp+0E8h+var_98]
0x180050ff7  cmp     eax, [rsp+0E8h+arg_30]
0x180050ffe  jnz     loc_1800514B8
0x180051004  sub     eax, 9
0x180051007  jz      short loc_18005105B
0x180051009  sub     eax, 4
0x18005100c  jz      short loc_180051054
0x18005100e  sub     eax, 3
0x180051011  jz      short loc_18005105B
0x180051013  sub     eax, 1
0x180051016  jz      short loc_18005104D
0x180051018  sub     eax, 1
0x18005101b  jz      short loc_180051024
0x18005101d  cmp     eax, 2000h
0x180051022  jnz     short loc_180051081
0x180051024  mov     ecx, [rsp+0E8h+var_94]
0x180051028  shr     rcx, 1
0x18005102b  mov     rax, rbx
0x18005102e  mul     rcx
0x180051031  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180051038  cmovb   rax, rbx
0x18005103c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180051043  mov     rcx, rax; unsigned __int64
0x180051046  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18005104b  jmp     short loc_180051070
0x18005104d  mov     ecx, 1
0x180051052  jmp     short loc_180051060
0x180051054  mov     ecx, 10h
0x180051059  jmp     short loc_180051060
0x18005105b  mov     ecx, 8; unsigned __int64
0x180051060  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180051067  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005106c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180051070  mov     r14, rax
0x180051073  mov     [rsp+0E8h+var_90], rax
0x180051078  test    rax, rax
0x18005107b  jnz     loc_180051184
0x180051081  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x180051088  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x18005108d  mov     ebx, 8007000Eh
0x180051092  test    al, al
0x180051094  jz      short loc_1800510A0
0x180051096  mov     edi, 3CEh
0x18005109b  jmp     loc_18005113F
0x1800510a0  mov     dword ptr [rsp+0E8h+var_C8], ebx
0x1800510a4  lea     r9, aOutOfMemoryX; "Out of memory [%#x]"
0x1800510ab  mov     edi, 3D2h
0x1800510b0  mov     r8d, edi
0x1800510b3  lea     rdx, aDriverpackager_16; "DriverPackageReaderDrvStore::GetDriverS"...
0x1800510ba  mov     r12d, 2
0x1800510c0  mov     ecx, r12d
0x1800510c3  call    AslLogCallPrintf
0x1800510c8  cmp     cs:EnableDevInvStdErrLog, esi
0x1800510ce  jz      short loc_180051122
0x1800510d0  mov     ecx, r12d; Ix
0x1800510d3  call    _o___acrt_iob_func_0
0x1800510d8  mov     rcx, rax; Stream
0x1800510db  mov     r9d, edi
0x1800510de  lea     r8, aDriverpackager_16; "DriverPackageReaderDrvStore::GetDriverS"...
0x1800510e5  lea     rdx, Format; "Error: %s, %u: "
0x1800510ec  call    fprintf
0x1800510f1  mov     ecx, r12d; Ix
0x1800510f4  call    _o___acrt_iob_func_0
0x1800510f9  mov     rcx, rax; Stream
0x1800510fc  mov     r8d, ebx
0x1800510ff  lea     rdx, aOutOfMemoryX; "Out of memory [%#x]"
0x180051106  call    fprintf
0x18005110b  mov     ecx, r12d; Ix
0x18005110e  call    _o___acrt_iob_func_0
0x180051113  mov     rcx, rax; Stream
0x180051116  lea     rdx, asc_18011EAD8; "\n"
0x18005111d  call    fprintf
0x180051122  cmp     cs:g_DeviceMapLogFunction, rsi
0x180051129  jz      short loc_18005113F
0x18005112b  mov     r8d, ebx
0x18005112e  lea     rdx, aOutOfMemoryX; "Out of memory [%#x]"
0x180051135  mov     ecx, 2000000h
0x18005113a  call    TraceMessageCallback
0x18005113f  mov     dword ptr [rsp+0E8h+var_C8], ebx
0x180051143  lea     r9, aOutOfMemoryX; "Out of memory [%#x]"
0x18005114a  mov     r8, rdi
0x18005114d  lea     rdx, aDriverpackager_16; "DriverPackageReaderDrvStore::GetDriverS"...
0x180051154  mov     ecx, 1
0x180051159  call    AslLogCallPrintf
0x18005115e  xorps   xmm0, xmm0
0x180051161  movups  xmmword ptr [r15], xmm0
0x180051165  mov     [r15+10h], rsi
0x180051169  mov     [r15+18h], rsi
0x18005116d  xor     r8d, r8d
0x180051170  lea     rdx, S2
0x180051177  mov     rcx, r15
0x18005117a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005117f  jmp     loc_18005150C
0x180051184  mov     [rsp+0E8h+var_A8], esi
0x180051188  lea     rax, [rsp+0E8h+var_94]
0x18005118d  mov     [rsp+0E8h+var_B0], rax
0x180051192  mov     eax, [rsp+0E8h+var_94]
0x180051196  mov     [rsp+0E8h+var_B8], eax
0x18005119a  mov     [rsp+0E8h+var_C0], r14
0x18005119f  lea     rax, [rsp+0E8h+var_98]
0x1800511a4  mov     [rsp+0E8h+var_C8], rax
0x1800511a9  mov     r9, r13
0x1800511ac  mov     r8, r12
0x1800511af  mov     r12d, 2
0x1800511b5  mov     edx, r12d
0x1800511b8  mov     rcx, rdi
0x1800511bb  call    cs:__imp_DriverStoreGetObjectPropertyW
0x1800511c1  test    eax, eax
0x1800511c3  jz      loc_1800513CC
0x1800511c9  mov     eax, [rsp+0E8h+var_98]
0x1800511cd  cmp     eax, [rsp+0E8h+arg_30]
0x1800511d4  jnz     loc_1800513CC
0x1800511da  sub     eax, 9
0x1800511dd  jz      loc_1800513A2
0x1800511e3  sub     eax, 4
0x1800511e6  jz      loc_18005138D
0x1800511ec  sub     eax, 3
0x1800511ef  jz      loc_180051378
0x1800511f5  sub     eax, 1
0x1800511f8  jz      loc_1800512D8
0x1800511fe  sub     eax, 1
0x180051201  jz      short loc_180051270
0x180051203  cmp     eax, 2000h
0x180051208  jnz     loc_1800513B3
0x18005120e  mov     rax, r14
0x180051211  mov     [rsp+0E8h+var_88], rax
0x180051216  cmp     [rax], si
0x180051219  jz      short loc_18005125C
0x18005121b  mov     rdx, qword ptr [rsp+0E8h+var_80+8]
0x180051220  cmp     rdx, [rsp+0E8h+var_70]
0x180051225  jz      short loc_180051232
0x180051227  mov     [rdx], rax
0x18005122a  add     qword ptr [rsp+0E8h+var_80+8], 8
0x180051230  jmp     short loc_180051246
0x180051232  lea     r8, [rsp+0E8h+var_88]
0x180051237  lea     rcx, [rsp+0E8h+var_80]
0x18005123c  call    ??$_Emplace_reallocate@AEBQEAVCDevice@@@?$vector@PEAVCDevice@@V?$allocator@PEAVCDevice@@@std@@@std@@AEAAPEAPEAVCDevice@@QEAPEAV2@AEBQEAV2@@Z; std::vector<CDevice *>::_Emplace_reallocate<CDevice * const &>(CDevice * * const,CDevice * const &)
0x180051241  mov     rax, [rsp+0E8h+var_88]
0x180051246  mov     rcx, rbx
0x180051249  inc     rcx
0x18005124c  cmp     [rax+rcx*2], si
0x180051250  jnz     short loc_180051249
0x180051252  lea     rax, [rax+rcx*2]
0x180051256  add     rax, 2
0x18005125a  jmp     short loc_180051211
0x18005125c  lea     rdx, [rsp+0E8h+var_58]
0x180051264  lea     rcx, [rsp+0E8h+var_80]
0x180051269  call    ?ConvertListToStr@@YAJAEBV?$vector@PEBGV?$allocator@PEBG@std@@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; ConvertListToStr(std::vector<ushort const *> const &,std::wstring &)
0x18005126e  jmp     short loc_1800512D3
0x180051270  inc     rbx
0x180051273  cmp     [r14+rbx*2], si
0x180051278  jnz     short loc_180051270
0x18005127a  cmp     rbx, qword ptr [rsp+0E8h+var_48+8]
0x180051282  ja      short loc_1800512C0
0x180051284  lea     rdi, [rsp+0E8h+var_58]
0x18005128c  cmp     qword ptr [rsp+0E8h+var_48+8], 7
0x180051295  cmova   rdi, [rsp+0E8h+var_58]
0x18005129e  mov     qword ptr [rsp+0E8h+var_48], rbx
0x1800512a6  add     rbx, rbx
0x1800512a9  mov     r8, rbx; Size
0x1800512ac  mov     rdx, r14; Src
0x1800512af  mov     rcx, rdi; void *
0x1800512b2  call    memmove_0
0x1800512b7  mov     [rdi+rbx], si
0x1800512bb  jmp     loc_1800513B3
0x1800512c0  mov     r9, r14
0x1800512c3  mov     rdx, rbx
0x1800512c6  lea     rcx, [rsp+0E8h+var_58]
0x1800512ce  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800512d3  jmp     loc_1800513B3
0x1800512d8  cmp     [r14], bl
0x1800512db  jnz     short loc_180051327
0x1800512dd  cmp     qword ptr [rsp+0E8h+var_48+8], 1
0x1800512e6  jb      short loc_180051319
0x1800512e8  lea     rax, [rsp+0E8h+var_58]
0x1800512f0  cmp     qword ptr [rsp+0E8h+var_48+8], 7
0x1800512f9  cmova   rax, [rsp+0E8h+var_58]
0x180051302  mov     qword ptr [rsp+0E8h+var_48], 1
0x18005130e  mov     dword ptr [rax], 31h ; '1'
0x180051314  jmp     loc_1800513B3
0x180051319  lea     r9, a1; "1"
0x180051320  mov     edx, 1
0x180051325  jmp     short loc_1800512C6
0x180051327  lea     rcx, [rsp+0E8h+var_58]
0x18005132f  cmp     qword ptr [rsp+0E8h+var_48+8], 1
0x180051338  jb      short loc_180051367
0x18005133a  cmp     qword ptr [rsp+0E8h+var_48+8], 7
0x180051343  cmova   rcx, [rsp+0E8h+var_58]
0x18005134c  mov     qword ptr [rsp+0E8h+var_48], 1
0x180051358  mov     eax, dword ptr cs:a0_0; "0"
0x18005135e  mov     [rcx], ax
0x180051361  mov     [rcx+2], si
0x180051365  jmp     short loc_1800513B3
0x180051367  lea     r9, a0_0; "0"
0x18005136e  mov     edx, 1
0x180051373  jmp     loc_1800512CE
0x180051378  lea     rdx, [rsp+0E8h+var_58]
0x180051380  mov     rcx, r14
0x180051383  call    ?ConvertFileTimeToDateStrYearFirst@@YAJAEBU_FILETIME@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConvertFileTimeToDateStrYearFirst(_FILETIME const &,std::wstring &)
0x180051388  jmp     loc_1800512D3
0x18005138d  lea     rdx, [rsp+0E8h+var_58]
0x180051395  mov     rcx, r14
0x180051398  call    ?GuidToString@@YAJPEAU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GuidToString(_GUID *,std::wstring &)
0x18005139d  jmp     loc_1800512D3
0x1800513a2  lea     rdx, [rsp+0E8h+var_58]
0x1800513aa  mov     rcx, r14
0x1800513ad  call    ?GetVersionFromUlong64@@YAHPEA_KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetVersionFromUlong64(unsigned __int64 *,std::wstring &)
0x1800513b2  nop
0x1800513b3  jmp     loc_1800514B8
0x1800513b8  xor     esi, esi
0x1800513ba  mov     r14, [rsp+0E8h+var_90]
0x1800513bf  mov     r15, [rsp+0E8h+var_60]
0x1800513c7  jmp     loc_1800514B8
0x1800513cc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x1800513d3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x1800513d8  test    al, al
0x1800513da  jz      short loc_180051409
0x1800513dc  call    cs:__imp_GetLastError
0x1800513e2  mov     dword ptr [rsp+0E8h+var_C8], eax
0x1800513e6  lea     r9, aFailedToGetDri; "Failed to get DriverStore Object Proper"...
0x1800513ed  mov     r8d, 3E7h
0x1800513f3  lea     rdx, aDriverpackager_16; "DriverPackageReaderDrvStore::GetDriverS"...
0x1800513fa  mov     ecx, 3
0x1800513ff  call    AslLogCallPrintf
0x180051404  jmp     loc_1800514B8
0x180051409  call    cs:__imp_GetLastError
0x18005140f  mov     dword ptr [rsp+0E8h+var_C8], eax
0x180051413  lea     r9, aFailedToGetDri; "Failed to get DriverStore Object Proper"...
0x18005141a  mov     ebx, 3EBh
0x18005141f  mov     r8d, ebx
0x180051422  lea     rdx, aDriverpackager_16; "DriverPackageReaderDrvStore::GetDriverS"...
0x180051429  mov     ecx, 3
0x18005142e  call    AslLogCallPrintf
0x180051433  cmp     cs:EnableDevInvStdErrLog, esi
0x180051439  jz      short loc_180051495
0x18005143b  mov     ecx, r12d; Ix
0x18005143e  call    _o___acrt_iob_func_0
0x180051443  mov     rcx, rax; Stream
0x180051446  mov     r9d, ebx
0x180051449  lea     r8, aDriverpackager_16; "DriverPackageReaderDrvStore::GetDriverS"...
0x180051450  lea     rdx, aInfoSU; "Info: %s, %u: "
0x180051457  call    fprintf
0x18005145c  call    cs:__imp_GetLastError
0x180051462  mov     ebx, eax
0x180051464  mov     ecx, r12d; Ix
0x180051467  call    _o___acrt_iob_func_0
0x18005146c  mov     r8d, ebx
0x18005146f  lea     rdx, aFailedToGetDri; "Failed to get DriverStore Object Proper"...
0x180051476  mov     rcx, rax; Stream
0x180051479  call    fprintf
0x18005147e  mov     ecx, r12d; Ix
0x180051481  call    _o___acrt_iob_func_0
0x180051486  mov     rcx, rax; Stream
0x180051489  lea     rdx, asc_18011EAD8; "\n"
  ... truncated ...
```
