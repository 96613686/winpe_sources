# SetupOneAutoLog(Microsoft::WRL::ComPtr<IConfigManager2>,ushort const *,ushort const *,bool,int)

- ea: `0x1800064dc`
- end: `0x180006922`
- name: `?SetupOneAutoLog@@YAJV?$ComPtr@UIConfigManager2@@@WRL@Microsoft@@PEBG1_NH@Z`
- size: `1094`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, char, LONG)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180005f0c`
- `0x180006250`

## callees

- `0x1800017e0`
- `0x180003490`
- `0x180003714`
- `0x180003b10`
- `0x180003b68`
- `0x180004f58`
- `0x180005a14`
- `0x1800064dc`
- `0x180007350`
- `0x180007368`
- `0x180026010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000663b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800067ab`
- `OLEAUT32!__imp_SysAllocString` at `0x18000663b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800067ab`
- `OLEAUT32!__imp_VariantInit` at `0x180006536`
- `OLEAUT32!__imp_VariantInit` at `0x180006804`
- `OLEAUT32!__imp_VariantInit` at `0x180006536`
- `OLEAUT32!__imp_VariantInit` at `0x180006804`
- `OLEAUT32!__imp_VariantClear` at `0x1800067f9`
- `OLEAUT32!__imp_VariantClear` at `0x1800068ea`
- `OLEAUT32!__imp_VariantClear` at `0x1800067f9`
- `OLEAUT32!__imp_VariantClear` at `0x1800068ea`

## string_xrefs

- `0x180006664`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x1800066bc`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x1800067d5`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`

## pseudocode

```c
__int64 __fastcall SetupOneAutoLog(_QWORD *a1, __int64 a2, __int64 a3, char a4, LONG a5)
{
  const OLECHAR *v9; // rcx
  BSTR v10; // rax
  __int64 v11; // rbx
  unsigned int v12; // ebx
  __int64 v13; // rsi
  __int64 (__fastcall *v14)(__int64, __int64, int *); // rdi
  int v15; // eax
  __int64 v16; // rdx
  const OLECHAR *v17; // rcx
  BSTR v18; // rax
  __int64 v19; // rbx
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // rsi
  __int64 (__fastcall *v23)(__int64, __int64, int *); // rdi
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v28[2]; // [rsp+20h] [rbp-91h] BYREF
  __int64 v29; // [rsp+28h] [rbp-89h] BYREF
  VARIANTARG pvarg; // [rsp+30h] [rbp-81h] BYREF
  VARIANTARG v31; // [rsp+50h] [rbp-61h] BYREF
  _QWORD *v32; // [rsp+70h] [rbp-41h]
  VARIANTARG *p_pvarg; // [rsp+78h] [rbp-39h]
  char v34; // [rsp+80h] [rbp-31h]
  OLECHAR *Src[4]; // [rsp+88h] [rbp-29h] BYREF
  OLECHAR *psz[4]; // [rsp+A8h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]

  v32 = a1;
  memset(&pvarg, 0, sizeof(pvarg));
  p_pvarg = &pvarg;
  v34 = 1;
  VariantInit(&pvarg);
  pvarg.vt = 3;
  pvarg.lVal = a5;
  std::wstring::wstring(psz, L"./Vendor/MSFT/DiagnosticLog/EtwLog/Collectors");
  std::_WChar_traits<unsigned short>::length(L"/");
  std::wstring::_Append<unsigned short>(psz);
  std::_WChar_traits<unsigned short>::length(a2);
  std::wstring::_Append<unsigned short>(psz);
  std::_WChar_traits<unsigned short>::length(L"/");
  std::wstring::_Append<unsigned short>(psz);
  std::_WChar_traits<unsigned short>::length(L"Providers");
  std::wstring::_Append<unsigned short>(psz);
  std::_WChar_traits<unsigned short>::length(L"/");
  std::wstring::_Append<unsigned short>(psz);
  std::_WChar_traits<unsigned short>::length(a3);
  std::wstring::_Append<unsigned short>(psz);
  std::_WChar_traits<unsigned short>::length(L"/");
  std::wstring::_Append<unsigned short>(psz);
  std::_WChar_traits<unsigned short>::length(L"TraceLevel");
  std::wstring::_Append<unsigned short>(psz);
  v29 = 0;
  v9 = (const OLECHAR *)psz;
  if ( psz[3] > (OLECHAR *)7 )
    v9 = psz[0];
  v10 = SysAllocString(v9);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v29,
    v10);
  v11 = v29;
  if ( v29 )
  {
    *(_QWORD *)v28 = 0;
    v13 = *a1;
    v14 = *(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)*a1 + 80LL);
    Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(v28);
    v15 = v14(v13, v11, v28);
    v12 = v15;
    if ( v15 >= 0 )
    {
      v31 = pvarg;
      v15 = (*(__int64 (__fastcall **)(_QWORD, VARIANTARG *, _QWORD))(**(_QWORD **)v28 + 96LL))(*(_QWORD *)v28, &v31, 0);
      v12 = v15;
      if ( v15 >= 0 )
      {
        v15 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 24LL))(*a1);
        v12 = v15;
        if ( v15 >= 0 )
        {
          std::wstring::wstring(Src, L"./Vendor/MSFT/DiagnosticLog/EtwLog/Collectors");
          std::_WChar_traits<unsigned short>::length(L"/");
          std::wstring::_Append<unsigned short>(Src);
          std::_WChar_traits<unsigned short>::length(a2);
          std::wstring::_Append<unsigned short>(Src);
          std::_WChar_traits<unsigned short>::length(L"/");
          std::wstring::_Append<unsigned short>(Src);
          std::_WChar_traits<unsigned short>::length(L"TraceLogFileMode");
          std::wstring::_Append<unsigned short>(Src);
          v17 = (const OLECHAR *)Src;
          if ( Src[3] > (OLECHAR *)7 )
            v17 = Src[0];
          v18 = SysAllocString(v17);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &v29,
            v18);
          v19 = v29;
          if ( v29 )
          {
            VariantClear(&pvarg);
            VariantInit(&pvarg);
            pvarg.vt = 3;
            pvarg.lVal = (a4 != 0) + 1;
            v22 = *a1;
            v23 = *(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)*a1 + 80LL);
            Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(v28);
            v24 = v23(v22, v19, v28);
            v12 = v24;
            if ( v24 >= 0 )
            {
              v31 = pvarg;
              v25 = (*(__int64 (__fastcall **)(_QWORD, VARIANTARG *, _QWORD))(**(_QWORD **)v28 + 96LL))(
                      *(_QWORD *)v28,
                      &v31,
                      0);
              v12 = v25;
              if ( v25 >= 0 )
              {
                v26 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 24LL))(*a1);
                v12 = v26;
                if ( v26 >= 0 )
                {
                  std::wstring::~wstring(Src);
                  Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(v28);
                  v12 = 0;
                  goto LABEL_25;
                }
                v20 = (unsigned int)v26;
                v21 = 239;
              }
              else
              {
                v20 = (unsigned int)v25;
                v21 = 238;
              }
            }
            else
            {
              v20 = (unsigned int)v24;
              v21 = 237;
            }
          }
          else
          {
            v12 = -2147024882;
            v20 = 2147942414LL;
            v21 = 230;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v21,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp",
            (const char *)v20,
            v28[0]);
          std::wstring::~wstring(Src);
          goto LABEL_8;
        }
        v16 = 220;
      }
      else
      {
        v16 = 219;
      }
    }
    else
    {
      v16 = 218;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp",
      (const char *)(unsigned int)v15,
      v28[0]);
LABEL_8:
    Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(v28);
    goto LABEL_25;
  }
  v12 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD7,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp",
    (const char *)0x8007000ELL,
    v28[0]);
LABEL_25:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
  std::wstring::~wstring(psz);
  VariantClear(&pvarg);
  Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(a1);
  return v12;
}

```

## disassembly

```asm
0x1800064dc  mov     [rsp-8+arg_18], rbx
0x1800064e1  push    rbp
0x1800064e2  push    rsi
0x1800064e3  push    rdi
0x1800064e4  push    r12
0x1800064e6  push    r13
0x1800064e8  push    r14
0x1800064ea  push    r15
0x1800064ec  lea     rbp, [rsp-1Fh]
0x1800064f1  sub     rsp, 0D0h
0x1800064f8  mov     rax, cs:__security_cookie
0x1800064ff  xor     rax, rsp
0x180006502  mov     [rbp+4Fh+var_38], rax
0x180006506  mov     r15b, r9b
0x180006509  mov     rbx, r8
0x18000650c  mov     r12, rdx
0x18000650f  mov     r14, rcx
0x180006512  mov     [rbp+4Fh+var_90], rcx
0x180006516  xorps   xmm0, xmm0
0x180006519  xor     eax, eax
0x18000651b  movups  xmmword ptr [rsp+100h+pvarg], xmm0
0x180006520  mov     qword ptr [rbp+4Fh+pvarg+10h], rax
0x180006524  lea     rax, [rsp+100h+pvarg]
0x180006529  mov     [rbp+4Fh+var_88], rax
0x18000652d  mov     [rbp+4Fh+var_80], 1
0x180006531  lea     rcx, [rsp+100h+pvarg]; pvarg
0x180006536  call    cs:__imp_VariantInit
0x18000653c  mov     eax, 3
0x180006541  mov     word ptr [rsp+100h+pvarg], ax
0x180006546  mov     eax, [rbp+4Fh+arg_20]
0x180006549  mov     dword ptr [rbp+4Fh+pvarg+8], eax
0x18000654c  lea     rdx, aVendorMsftDiag; "./Vendor/MSFT/DiagnosticLog/EtwLog/Coll"...
0x180006553  lea     rcx, [rbp+4Fh+psz]
0x180006557  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000655c  nop
0x18000655d  lea     r13, asc_18002992C; "/"
0x180006564  mov     rcx, r13
0x180006567  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000656c  mov     r8, rax
0x18000656f  mov     rdx, r13
0x180006572  lea     rcx, [rbp+4Fh+psz]; Src
0x180006576  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000657b  mov     rcx, r12
0x18000657e  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180006583  mov     r8, rax
0x180006586  mov     rdx, r12
0x180006589  lea     rcx, [rbp+4Fh+psz]; Src
0x18000658d  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180006592  mov     rcx, r13
0x180006595  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000659a  mov     r8, rax
0x18000659d  mov     rdx, r13
0x1800065a0  lea     rcx, [rbp+4Fh+psz]; Src
0x1800065a4  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800065a9  lea     rcx, aProviders; "Providers"
0x1800065b0  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800065b5  mov     r8, rax
0x1800065b8  mov     rdx, rcx
0x1800065bb  lea     rcx, [rbp+4Fh+psz]; Src
0x1800065bf  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800065c4  mov     rcx, r13
0x1800065c7  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800065cc  mov     r8, rax
0x1800065cf  mov     rdx, r13
0x1800065d2  lea     rcx, [rbp+4Fh+psz]; Src
0x1800065d6  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800065db  mov     rcx, rbx
0x1800065de  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800065e3  mov     r8, rax
0x1800065e6  mov     rdx, rbx
0x1800065e9  lea     rcx, [rbp+4Fh+psz]; Src
0x1800065ed  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800065f2  mov     rcx, r13
0x1800065f5  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800065fa  mov     r8, rax
0x1800065fd  mov     rdx, r13
0x180006600  lea     rcx, [rbp+4Fh+psz]; Src
0x180006604  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180006609  lea     rcx, aTracelevel; "TraceLevel"
0x180006610  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180006615  mov     r8, rax
0x180006618  mov     rdx, rcx
0x18000661b  lea     rcx, [rbp+4Fh+psz]; Src
0x18000661f  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180006624  mov     [rsp+100h+var_D8], 0
0x18000662d  lea     rcx, [rbp+4Fh+psz]
0x180006631  cmp     [rbp+4Fh+var_40], 7
0x180006636  cmova   rcx, [rbp+4Fh+psz]; psz
0x18000663b  call    cs:__imp_SysAllocString
0x180006641  mov     rdx, rax
0x180006644  lea     rcx, [rsp+100h+var_D8]
0x180006649  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000664e  mov     rbx, [rsp+100h+var_D8]
0x180006653  test    rbx, rbx
0x180006656  jnz     short loc_18000667A
0x180006658  mov     rcx, [rbp+57h]; this
0x18000665c  mov     ebx, 8007000Eh
0x180006661  mov     r9d, ebx; char *
0x180006664  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18000666b  mov     edx, 0D7h; void *
0x180006670  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006675  jmp     loc_1800068D0
0x18000667a  mov     qword ptr [rsp+100h+var_E0], 0; int
0x180006683  mov     rsi, [r14]
0x180006686  mov     rax, [rsi]
0x180006689  mov     rdi, [rax+50h]
0x18000668d  lea     rcx, [rsp+100h+var_E0]
0x180006692  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006697  lea     r8, [rsp+100h+var_E0]
0x18000669c  mov     rdx, rbx
0x18000669f  mov     rcx, rsi
0x1800066a2  mov     rax, rdi
0x1800066a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066aa  mov     ebx, eax
0x1800066ac  test    eax, eax
0x1800066ae  jns     short loc_1800066D8
0x1800066b0  mov     edx, 0DAh; void *
0x1800066b5  mov     rcx, [rbp+57h]; this
0x1800066b9  mov     r9d, eax; char *
0x1800066bc  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800066c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800066c8  nop
0x1800066c9  lea     rcx, [rsp+100h+var_E0]
0x1800066ce  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x1800066d3  jmp     loc_1800068D0
0x1800066d8  mov     rcx, qword ptr [rsp+100h+var_E0]
0x1800066dd  movups  xmm0, xmmword ptr [rsp+100h+pvarg]
0x1800066e2  movaps  [rbp+4Fh+var_B0], xmm0
0x1800066e6  movsd   xmm1, qword ptr [rbp+4Fh+pvarg+10h]
0x1800066eb  movsd   [rbp+4Fh+var_A0], xmm1
0x1800066f0  mov     rax, [rcx]
0x1800066f3  xor     r8d, r8d
0x1800066f6  lea     rdx, [rbp+4Fh+var_B0]
0x1800066fa  mov     rax, [rax+60h]
0x1800066fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006703  mov     ebx, eax
0x180006705  test    eax, eax
0x180006707  jns     short loc_180006710
0x180006709  mov     edx, 0DBh
0x18000670e  jmp     short loc_1800066B5
0x180006710  mov     rcx, [r14]
0x180006713  mov     rax, [rcx]
0x180006716  mov     rax, [rax+18h]
0x18000671a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000671f  mov     ebx, eax
0x180006721  test    eax, eax
0x180006723  jns     short loc_18000672C
0x180006725  mov     edx, 0DCh
0x18000672a  jmp     short loc_1800066B5
0x18000672c  lea     rdx, aVendorMsftDiag; "./Vendor/MSFT/DiagnosticLog/EtwLog/Coll"...
0x180006733  lea     rcx, [rbp+4Fh+Src]
0x180006737  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000673c  nop
0x18000673d  mov     rcx, r13
0x180006740  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180006745  mov     r8, rax
0x180006748  mov     rdx, r13
0x18000674b  lea     rcx, [rbp+4Fh+Src]; Src
0x18000674f  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180006754  mov     rcx, r12
0x180006757  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000675c  mov     r8, rax
0x18000675f  mov     rdx, r12
0x180006762  lea     rcx, [rbp+4Fh+Src]; Src
0x180006766  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000676b  mov     rcx, r13
0x18000676e  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180006773  mov     r8, rax
0x180006776  mov     rdx, r13
0x180006779  lea     rcx, [rbp+4Fh+Src]; Src
0x18000677d  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180006782  lea     rcx, aTracelogfilemo; "TraceLogFileMode"
0x180006789  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000678e  mov     r8, rax
0x180006791  mov     rdx, rcx
0x180006794  lea     rcx, [rbp+4Fh+Src]; Src
0x180006798  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000679d  lea     rcx, [rbp+4Fh+Src]
0x1800067a1  cmp     [rbp+4Fh+var_60], 7
0x1800067a6  cmova   rcx, [rbp+4Fh+Src]; psz
0x1800067ab  call    cs:__imp_SysAllocString
0x1800067b1  mov     rdx, rax
0x1800067b4  lea     rcx, [rsp+100h+var_D8]
0x1800067b9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800067be  mov     rbx, [rsp+100h+var_D8]
0x1800067c3  test    rbx, rbx
0x1800067c6  jnz     short loc_1800067F4
0x1800067c8  mov     ebx, 8007000Eh
0x1800067cd  mov     r9d, ebx; char *
0x1800067d0  mov     edx, 0E6h; void *
0x1800067d5  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800067dc  mov     rcx, [rbp+57h]; this
0x1800067e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800067e5  nop
0x1800067e6  lea     rcx, [rbp+4Fh+Src]
0x1800067ea  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800067ef  jmp     loc_1800066C9
0x1800067f4  lea     rcx, [rsp+100h+pvarg]; pvarg
0x1800067f9  call    cs:__imp_VariantClear
0x1800067ff  lea     rcx, [rsp+100h+pvarg]; pvarg
0x180006804  call    cs:__imp_VariantInit
0x18000680a  mov     eax, 3
0x18000680f  mov     word ptr [rsp+100h+pvarg], ax
0x180006814  neg     r15b
0x180006817  sbb     eax, eax
0x180006819  neg     eax
0x18000681b  inc     eax
0x18000681d  mov     dword ptr [rbp+4Fh+pvarg+8], eax
0x180006820  mov     rsi, [r14]
0x180006823  mov     rax, [rsi]
0x180006826  mov     rdi, [rax+50h]
0x18000682a  lea     rcx, [rsp+100h+var_E0]
0x18000682f  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006834  lea     r8, [rsp+100h+var_E0]
0x180006839  mov     rdx, rbx
0x18000683c  mov     rcx, rsi
0x18000683f  mov     rax, rdi
0x180006842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006847  mov     ebx, eax
0x180006849  test    eax, eax
0x18000684b  jns     short loc_18000685A
0x18000684d  mov     r9d, eax
0x180006850  mov     edx, 0EDh
0x180006855  jmp     loc_1800067D5
0x18000685a  mov     rcx, qword ptr [rsp+100h+var_E0]
0x18000685f  movups  xmm0, xmmword ptr [rsp+100h+pvarg]
0x180006864  movaps  [rbp+4Fh+var_B0], xmm0
0x180006868  movsd   xmm1, qword ptr [rbp+4Fh+pvarg+10h]
0x18000686d  movsd   [rbp+4Fh+var_A0], xmm1
0x180006872  mov     rax, [rcx]
0x180006875  xor     r8d, r8d
0x180006878  lea     rdx, [rbp+4Fh+var_B0]
0x18000687c  mov     rax, [rax+60h]
0x180006880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006885  mov     ebx, eax
0x180006887  test    eax, eax
0x180006889  jns     short loc_180006898
0x18000688b  mov     r9d, eax
0x18000688e  mov     edx, 0EEh
0x180006893  jmp     loc_1800067D5
0x180006898  mov     rcx, [r14]
0x18000689b  mov     rax, [rcx]
0x18000689e  mov     rax, [rax+18h]
0x1800068a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068a7  mov     ebx, eax
0x1800068a9  test    eax, eax
0x1800068ab  jns     short loc_1800068BA
0x1800068ad  mov     r9d, eax
0x1800068b0  mov     edx, 0EFh
0x1800068b5  jmp     loc_1800067D5
0x1800068ba  lea     rcx, [rbp+4Fh+Src]
0x1800068be  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800068c3  nop
0x1800068c4  lea     rcx, [rsp+100h+var_E0]
0x1800068c9  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x1800068ce  xor     ebx, ebx
0x1800068d0  lea     rcx, [rsp+100h+var_D8]
0x1800068d5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800068da  nop
0x1800068db  lea     rcx, [rbp+4Fh+psz]
0x1800068df  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800068e4  nop
0x1800068e5  lea     rcx, [rsp+100h+pvarg]; pvarg
0x1800068ea  call    cs:__imp_VariantClear
0x1800068f0  nop
0x1800068f1  mov     rcx, r14
0x1800068f4  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x1800068f9  mov     eax, ebx
0x1800068fb  mov     rcx, [rbp+4Fh+var_38]
0x1800068ff  xor     rcx, rsp; StackCookie
0x180006902  call    __security_check_cookie
0x180006907  mov     rbx, [rsp+100h+arg_18]
0x18000690f  add     rsp, 0D0h
0x180006916  pop     r15
0x180006918  pop     r14
0x18000691a  pop     r13
0x18000691c  pop     r12
0x18000691e  pop     rdi
0x18000691f  pop     rsi
0x180006920  pop     rbp
0x180006921  retn
```
