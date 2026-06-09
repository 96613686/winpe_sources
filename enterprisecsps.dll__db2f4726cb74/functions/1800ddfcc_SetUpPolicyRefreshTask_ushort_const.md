# SetUpPolicyRefreshTask(ushort const *)

- ea: `0x1800ddfcc`
- end: `0x1800de38d`
- name: `?SetUpPolicyRefreshTask@@YAJPEBG@Z`
- size: `961`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180045a50`

## callees

- `0x180008de0`
- `0x18000d4d4`
- `0x18000db4c`
- `0x18001a4fc`
- `0x180039900`
- `0x180039928`
- `0x180039950`
- `0x1800637f4`
- `0x1800639d0`
- `0x1800645fc`
- `0x1800d7e58`
- `0x1800db400`
- `0x1800ddfcc`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800de142`
- `OLEAUT32!__imp_VariantInit` at `0x1800de15d`
- `OLEAUT32!__imp_VariantInit` at `0x1800de178`
- `OLEAUT32!__imp_VariantInit` at `0x1800de192`
- `OLEAUT32!__imp_VariantInit` at `0x1800de142`
- `OLEAUT32!__imp_VariantInit` at `0x1800de15d`
- `OLEAUT32!__imp_VariantInit` at `0x1800de178`
- `OLEAUT32!__imp_VariantInit` at `0x1800de192`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800de07d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800de2f8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800de337`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800de07d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800de2f8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800de337`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800de11e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800de11e`

## pseudocode

```c
int __fastcall SetUpPolicyRefreshTask(const unsigned __int16 *a1)
{
  int result; // eax
  unsigned int v3; // edx
  int v4; // eax
  int v5; // ebx
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v8; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v10; // xmm8
  IRecordInfo *v11; // xmm9_8
  __int128 v12; // xmm6
  IRecordInfo *v13; // xmm7_8
  LPVOID v14; // rbx
  int (__fastcall *v15)(LPVOID, __int64, __int64 *); // rdi
  _bstr_t *v16; // rax
  __int64 v17; // rdx
  bool v18; // bl
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, _QWORD *, __int64 *); // rdi
  _QWORD *v21; // rdx
  int v22; // ebx
  int v23; // r8d
  int v24; // r9d
  LPVOID *ppv; // [rsp+28h] [rbp-E0h]
  __int64 v26; // [rsp+38h] [rbp-D0h] BYREF
  LPVOID v27; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B8h] BYREF
  _bstr_t::Data_t *v30; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int16 *v31[2]; // [rsp+60h] [rbp-A8h] BYREF
  __int16 v32; // [rsp+70h] [rbp-98h] BYREF
  VARIANTARG v33; // [rsp+78h] [rbp-90h] BYREF
  __int64 v34; // [rsp+90h] [rbp-78h]
  VARIANTARG v35; // [rsp+98h] [rbp-70h] BYREF
  VARIANTARG v36; // [rsp+B0h] [rbp-58h] BYREF
  VARIANTARG pvarg; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v38; // [rsp+E8h] [rbp-20h] BYREF
  IRecordInfo *v39; // [rsp+F8h] [rbp-10h]
  __int128 v40; // [rsp+108h] [rbp+0h] BYREF
  IRecordInfo *v41; // [rsp+118h] [rbp+10h]
  __int128 v42; // [rsp+128h] [rbp+20h] BYREF
  IRecordInfo *v43; // [rsp+138h] [rbp+30h]
  __int128 v44; // [rsp+148h] [rbp+40h] BYREF
  __int64 v45; // [rsp+158h] [rbp+50h]
  unsigned __int16 v46[264]; // [rsp+168h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+410h] [rbp+308h]

  if ( !a1 )
    return -2147024809;
  result = StringCchPrintfW(v46, 0x104u, L"/o \"%s\" /c /PolicyManagerRefreshOnLogin", a1);
  if ( result >= 0 )
  {
    LODWORD(v26) = 0;
    v4 = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v26, v3);
    v5 = v4;
    if ( v4 >= 0 )
    {
      v27 = 0;
      v31[0] = (unsigned __int16 *)&v32;
      v28 = 0;
      v31[1] = (unsigned __int16 *)&v32;
      v29 = 0;
      v32 = 0;
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
        v31,
        L"\\Microsoft\\Windows\\EnterpriseMgmt\\",
        34);
      if ( !v31[0] )
        goto LABEL_26;
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(v31, a1);
      if ( !v31[0] )
        goto LABEL_26;
      if ( CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v27) < 0 )
        goto LABEL_26;
      v6 = v27;
      v7 = *(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *))(*(_QWORD *)v27 + 80LL);
      VariantInit(&pvarg);
      v8 = *(_OWORD *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      VariantInit(&v36);
      v10 = *(_OWORD *)&v36.vt;
      v11 = v36.pRecInfo;
      VariantInit(&v35);
      v12 = *(_OWORD *)&v35.vt;
      v13 = v35.pRecInfo;
      VariantInit((VARIANTARG *)&v33.decVal.8);
      ppv = (LPVOID *)&v38;
      v44 = *(_OWORD *)&v33.decVal.Lo32;
      v38 = v8;
      v39 = pRecInfo;
      v40 = v10;
      v41 = v11;
      v42 = v12;
      v43 = v13;
      v45 = v34;
      LODWORD(v7) = v7(v6, &v44, &v42, &v40);
      _variant_t::~_variant_t((_variant_t *)&v33.decVal.8);
      _variant_t::~_variant_t((_variant_t *)&v35);
      _variant_t::~_variant_t((_variant_t *)&v36);
      _variant_t::~_variant_t((_variant_t *)&pvarg);
      if ( (int)v7 < 0 )
        goto LABEL_26;
      v14 = v27;
      v15 = *(int (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v27 + 56LL);
      v16 = _bstr_t::_bstr_t((_bstr_t *)&v30, v31[0]);
      if ( *(_QWORD *)v16 )
        v17 = **(_QWORD **)v16;
      else
        v17 = 0;
      v18 = v15(v14, v17, &v28) >= 0;
      if ( v30 )
        _bstr_t::Data_t::Release(v30);
      if ( !v18 )
        goto LABEL_26;
      v19 = v28;
      v20 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64 *))(*(_QWORD *)v28 + 104LL);
      v21 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v30, L"Policy Manager Login Refresh Schedule");
      if ( v21 )
        v21 = (_QWORD *)*v21;
      v22 = v20(v19, v21, &v29);
      if ( v30 )
        _bstr_t::Data_t::Release(v30);
      if ( v22 >= 0 )
      {
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v31);
        ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v29);
        ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v28);
        ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v27);
        if ( (_DWORD)v26 )
          CoUninitialize();
        return 0;
      }
      else
      {
LABEL_26:
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v31);
        ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v29);
        ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v28);
        ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v27);
        if ( (_DWORD)v26 )
          CoUninitialize();
        return ScheduleDeviceEnrollerOnLogin((_DWORD)a1, (unsigned int)v46, v23, v24, (__int64)ppv);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1952,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
        (const char *)(unsigned int)v4,
        (int)ppv);
      if ( (_DWORD)v26 )
        CoUninitialize();
      return v5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800ddfcc  mov     rax, rsp
0x1800ddfcf  push    rbp
0x1800ddfd0  push    rbx
0x1800ddfd1  push    rsi
0x1800ddfd2  push    rdi
0x1800ddfd3  lea     rbp, [rax-308h]
0x1800ddfda  sub     rsp, 3E8h
0x1800ddfe1  movaps  xmmword ptr [rax-38h], xmm6
0x1800ddfe5  movaps  xmmword ptr [rax-48h], xmm7
0x1800ddfe9  movaps  xmmword ptr [rax-58h], xmm8
0x1800ddfee  movaps  xmmword ptr [rax-68h], xmm9
0x1800ddff3  movaps  xmmword ptr [rax-78h], xmm10
0x1800ddff8  movaps  xmmword ptr [rax-88h], xmm11
0x1800de000  mov     rax, cs:__security_cookie
0x1800de007  xor     rax, rsp
0x1800de00a  mov     [rbp+300h+var_90], rax
0x1800de011  mov     rsi, rcx
0x1800de014  test    rcx, rcx
0x1800de017  jnz     short loc_1800DE023
0x1800de019  mov     eax, 80070057h
0x1800de01e  jmp     loc_1800DE34F
0x1800de023  mov     r9, rsi
0x1800de026  lea     r8, aOSCPolicymanag; "/o \"%s\" /c /PolicyManagerRefreshOnLog"...
0x1800de02d  mov     edx, 104h; unsigned __int64
0x1800de032  lea     rcx, [rbp+300h+var_2A0]; unsigned __int16 *
0x1800de036  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800de03b  test    eax, eax
0x1800de03d  js      loc_1800DE34F
0x1800de043  lea     rcx, [rsp+400h+var_3D0]; this
0x1800de048  mov     dword ptr [rsp+400h+var_3D0], 0
0x1800de050  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x1800de055  mov     ebx, eax
0x1800de057  test    eax, eax
0x1800de059  jns     short loc_1800DE090
0x1800de05b  mov     rcx, [rbp+308h]; this
0x1800de062  lea     r8, aOnecoreuapAdmi_82; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800de069  mov     r9d, eax; char *
0x1800de06c  mov     edx, 1952h; void *
0x1800de071  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800de076  cmp     dword ptr [rsp+400h+var_3D0], 0
0x1800de07b  jz      short loc_1800DE089
0x1800de07d  call    cs:__imp_CoUninitialize
0x1800de084  nop     dword ptr [rax+rax+00h]
0x1800de089  mov     eax, ebx
0x1800de08b  jmp     loc_1800DE34F
0x1800de090  lea     rax, [rsp+400h+var_398]
0x1800de095  mov     [rsp+400h+var_3C8], 0
0x1800de09e  mov     [rsp+400h+var_3A8], rax
0x1800de0a3  lea     rdx, aMicrosoftWindo_2; "\\Microsoft\\Windows\\EnterpriseMgmt\\"
0x1800de0aa  lea     rax, [rsp+400h+var_398]
0x1800de0af  mov     [rsp+400h+var_3C0], 0
0x1800de0b8  mov     qword ptr [rsp+400h+var_3A0], rax
0x1800de0bd  lea     rcx, [rsp+400h+var_3A8]
0x1800de0c2  xor     eax, eax
0x1800de0c4  mov     [rsp+400h+var_3B8], 0
0x1800de0cd  mov     [rsp+400h+var_398], ax
0x1800de0d2  lea     r8d, [rax+22h]
0x1800de0d6  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800de0db  cmp     [rsp+400h+var_3A8], 0
0x1800de0e1  jz      loc_1800DE308
0x1800de0e7  mov     rdx, rsi
0x1800de0ea  lea     rcx, [rsp+400h+var_3A8]
0x1800de0ef  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800de0f4  cmp     [rsp+400h+var_3A8], 0
0x1800de0fa  jz      loc_1800DE308
0x1800de100  xor     edx, edx; pUnkOuter
0x1800de102  lea     rax, [rsp+400h+var_3C8]
0x1800de107  lea     r9, IID_ITaskService; riid
0x1800de10e  mov     [rsp+400h+ppv], rax; ppv
0x1800de113  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800de11a  lea     r8d, [rdx+1]; dwClsContext
0x1800de11e  call    cs:__imp_CoCreateInstance
0x1800de125  nop     dword ptr [rax+rax+00h]
0x1800de12a  test    eax, eax
0x1800de12c  js      loc_1800DE308
0x1800de132  mov     rdi, [rsp+400h+var_3C8]
0x1800de137  lea     rcx, [rbp+300h+pvarg]; pvarg
0x1800de13b  mov     rax, [rdi]
0x1800de13e  mov     rbx, [rax+50h]
0x1800de142  call    cs:__imp_VariantInit
0x1800de149  nop     dword ptr [rax+rax+00h]
0x1800de14e  movups  xmm10, xmmword ptr [rbp+300h+pvarg]
0x1800de153  lea     rcx, [rbp+300h+var_358]; pvarg
0x1800de157  movsd   xmm11, qword ptr [rbp+300h+pvarg+10h]
0x1800de15d  call    cs:__imp_VariantInit
0x1800de164  nop     dword ptr [rax+rax+00h]
0x1800de169  movups  xmm8, xmmword ptr [rbp+300h+var_358]
0x1800de16e  lea     rcx, [rbp+300h+var_370]; pvarg
0x1800de172  movsd   xmm9, qword ptr [rbp+300h+var_358+10h]
0x1800de178  call    cs:__imp_VariantInit
0x1800de17f  nop     dword ptr [rax+rax+00h]
0x1800de184  movups  xmm6, xmmword ptr [rbp+300h+var_370]
0x1800de188  lea     rcx, [rsp+400h+var_390+8]; pvarg
0x1800de18d  movsd   xmm7, qword ptr [rbp+300h+var_370+10h]
0x1800de192  call    cs:__imp_VariantInit
0x1800de199  nop     dword ptr [rax+rax+00h]
0x1800de19e  movups  xmm0, xmmword ptr [rsp+400h+var_390+8]
0x1800de1a3  lea     rax, [rbp+300h+var_320]
0x1800de1a7  mov     rcx, rdi
0x1800de1aa  movsd   xmm1, [rbp+300h+var_378]
0x1800de1af  lea     r9, [rbp+300h+var_300]
0x1800de1b3  mov     [rsp+400h+ppv], rax
0x1800de1b8  lea     r8, [rbp+300h+var_2E0]
0x1800de1bc  mov     rax, rbx
0x1800de1bf  movaps  [rbp+300h+var_2C0], xmm0
0x1800de1c3  lea     rdx, [rbp+300h+var_2C0]
0x1800de1c7  movaps  [rbp+300h+var_320], xmm10
0x1800de1cc  movsd   [rbp+300h+var_310], xmm11
0x1800de1d2  movaps  [rbp+300h+var_300], xmm8
0x1800de1d7  movsd   [rbp+300h+var_2F0], xmm9
0x1800de1dd  movaps  [rbp+300h+var_2E0], xmm6
0x1800de1e1  movsd   [rbp+300h+var_2D0], xmm7
0x1800de1e6  movsd   [rbp+300h+var_2B0], xmm1
0x1800de1eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de1f0  lea     rcx, [rsp+400h+var_390+8]; this
0x1800de1f5  mov     ebx, eax
0x1800de1f7  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800de1fc  lea     rcx, [rbp+300h+var_370]; this
0x1800de200  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800de205  lea     rcx, [rbp+300h+var_358]; this
0x1800de209  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800de20e  lea     rcx, [rbp+300h+pvarg]; this
0x1800de212  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800de217  shr     ebx, 1Fh
0x1800de21a  xor     bl, 1
0x1800de21d  jz      loc_1800DE308
0x1800de223  mov     rbx, [rsp+400h+var_3C8]
0x1800de228  lea     rcx, [rsp+400h+var_3B0]; this
0x1800de22d  mov     rdx, [rsp+400h+var_3A8]; unsigned __int16 *
0x1800de232  mov     rax, [rbx]
0x1800de235  mov     rdi, [rax+38h]
0x1800de239  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800de23e  mov     rcx, [rax]
0x1800de241  test    rcx, rcx
0x1800de244  jz      short loc_1800DE24B
0x1800de246  mov     rdx, [rcx]
0x1800de249  jmp     short loc_1800DE24D
0x1800de24b  xor     edx, edx
0x1800de24d  lea     r8, [rsp+400h+var_3C0]
0x1800de252  mov     rcx, rbx
0x1800de255  mov     rax, rdi
0x1800de258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de25d  mov     rcx, [rsp+400h+var_3B0]; this
0x1800de262  mov     ebx, eax
0x1800de264  shr     ebx, 1Fh
0x1800de267  xor     bl, 1
0x1800de26a  test    rcx, rcx
0x1800de26d  jz      short loc_1800DE274
0x1800de26f  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x1800de274  test    bl, bl
0x1800de276  jz      loc_1800DE308
0x1800de27c  mov     rbx, [rsp+400h+var_3C0]
0x1800de281  lea     rdx, aPolicyManagerL; "Policy Manager Login Refresh Schedule"
0x1800de288  lea     rcx, [rsp+400h+var_3B0]; this
0x1800de28d  mov     rax, [rbx]
0x1800de290  mov     rdi, [rax+68h]
0x1800de294  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800de299  mov     rdx, [rax]
0x1800de29c  test    rdx, rdx
0x1800de29f  jz      short loc_1800DE2A4
0x1800de2a1  mov     rdx, [rdx]
0x1800de2a4  lea     r8, [rsp+400h+var_3B8]
0x1800de2a9  mov     rcx, rbx
0x1800de2ac  mov     rax, rdi
0x1800de2af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de2b4  mov     rcx, [rsp+400h+var_3B0]; this
0x1800de2b9  mov     ebx, eax
0x1800de2bb  test    rcx, rcx
0x1800de2be  jz      short loc_1800DE2C5
0x1800de2c0  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x1800de2c5  test    ebx, ebx
0x1800de2c7  js      short loc_1800DE308
0x1800de2c9  lea     rcx, [rsp+400h+var_3A8]
0x1800de2ce  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800de2d3  lea     rcx, [rsp+400h+var_3B8]
0x1800de2d8  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800de2dd  lea     rcx, [rsp+400h+var_3C0]
0x1800de2e2  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800de2e7  lea     rcx, [rsp+400h+var_3C8]
0x1800de2ec  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800de2f1  cmp     dword ptr [rsp+400h+var_3D0], 0
0x1800de2f6  jz      short loc_1800DE304
0x1800de2f8  call    cs:__imp_CoUninitialize
0x1800de2ff  nop     dword ptr [rax+rax+00h]
0x1800de304  xor     eax, eax
0x1800de306  jmp     short loc_1800DE34F
0x1800de308  lea     rcx, [rsp+400h+var_3A8]
0x1800de30d  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800de312  lea     rcx, [rsp+400h+var_3B8]
0x1800de317  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800de31c  lea     rcx, [rsp+400h+var_3C0]
0x1800de321  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800de326  lea     rcx, [rsp+400h+var_3C8]
0x1800de32b  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800de330  cmp     dword ptr [rsp+400h+var_3D0], 0
0x1800de335  jz      short loc_1800DE343
0x1800de337  call    cs:__imp_CoUninitialize
0x1800de33e  nop     dword ptr [rax+rax+00h]
0x1800de343  lea     rdx, [rbp+300h+var_2A0]
0x1800de347  mov     rcx, rsi
0x1800de34a  call    ScheduleDeviceEnrollerOnLogin
0x1800de34f  mov     rcx, [rbp+300h+var_90]
0x1800de356  xor     rcx, rsp; StackCookie
0x1800de359  call    __security_check_cookie
0x1800de35e  lea     r11, [rsp+400h+var_18]
0x1800de366  movaps  xmm6, xmmword ptr [r11-18h]
0x1800de36b  movaps  xmm7, xmmword ptr [r11-28h]
0x1800de370  movaps  xmm8, xmmword ptr [r11-38h]
0x1800de375  movaps  xmm9, xmmword ptr [r11-48h]
0x1800de37a  movaps  xmm10, xmmword ptr [r11-58h]
0x1800de37f  movaps  xmm11, xmmword ptr [r11-68h]
0x1800de384  mov     rsp, r11
0x1800de387  pop     rdi
0x1800de388  pop     rsi
0x1800de389  pop     rbx
0x1800de38a  pop     rbp
0x1800de38b  retn
```
