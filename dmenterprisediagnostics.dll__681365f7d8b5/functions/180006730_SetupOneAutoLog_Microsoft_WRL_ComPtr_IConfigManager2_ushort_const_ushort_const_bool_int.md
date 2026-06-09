# SetupOneAutoLog(Microsoft::WRL::ComPtr<IConfigManager2>,ushort const *,ushort const *,bool,int)

- ea: `0x180006730`
- end: `0x180006b9b`
- name: `?SetupOneAutoLog@@YAJV?$ComPtr@UIConfigManager2@@@WRL@Microsoft@@PEBG1_NH@Z`
- size: `1131`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006138`
- `0x1800064a0`

## callees

- `0x180001800`
- `0x1800034e4`
- `0x180003768`
- `0x180003b14`
- `0x180003b70`
- `0x1800050e0`
- `0x180005c14`
- `0x180006730`
- `0x180007618`
- `0x180007630`
- `0x180027010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180006895`
- `OLEAUT32!__imp_SysAllocString` at `0x180006a0b`
- `OLEAUT32!__imp_SysAllocString` at `0x180006895`
- `OLEAUT32!__imp_SysAllocString` at `0x180006a0b`
- `OLEAUT32!__imp_VariantInit` at `0x18000678a`
- `OLEAUT32!__imp_VariantInit` at `0x180006a70`
- `OLEAUT32!__imp_VariantInit` at `0x18000678a`
- `OLEAUT32!__imp_VariantInit` at `0x180006a70`
- `OLEAUT32!__imp_VariantClear` at `0x180006a5f`
- `OLEAUT32!__imp_VariantClear` at `0x180006b5c`
- `OLEAUT32!__imp_VariantClear` at `0x180006a5f`
- `OLEAUT32!__imp_VariantClear` at `0x180006b5c`

## string_xrefs

- `0x1800068c4`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x18000691c`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x180006a3b`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x180006730  mov     [rsp-8+arg_18], rbx
0x180006735  push    rbp
0x180006736  push    rsi
0x180006737  push    rdi
0x180006738  push    r12
0x18000673a  push    r13
0x18000673c  push    r14
0x18000673e  push    r15
0x180006740  lea     rbp, [rsp-1Fh]
0x180006745  sub     rsp, 0D0h
0x18000674c  mov     rax, cs:__security_cookie
0x180006753  xor     rax, rsp
0x180006756  mov     [rbp+4Fh+var_38], rax
0x18000675a  mov     r15b, r9b
0x18000675d  mov     rbx, r8
0x180006760  mov     r12, rdx
0x180006763  mov     r14, rcx
0x180006766  mov     [rbp+4Fh+var_90], rcx
0x18000676a  xorps   xmm0, xmm0
0x18000676d  xor     eax, eax
0x18000676f  movups  xmmword ptr [rsp+100h+pvarg], xmm0
0x180006774  mov     qword ptr [rbp+4Fh+pvarg+10h], rax
0x180006778  lea     rax, [rsp+100h+pvarg]
0x18000677d  mov     [rbp+4Fh+var_88], rax
0x180006781  mov     [rbp+4Fh+var_80], 1
0x180006785  lea     rcx, [rsp+100h+pvarg]; pvarg
0x18000678a  call    cs:__imp_VariantInit
0x180006791  nop     dword ptr [rax+rax+00h]
0x180006796  mov     eax, 3
0x18000679b  mov     word ptr [rsp+100h+pvarg], ax
0x1800067a0  mov     eax, [rbp+4Fh+arg_20]
0x1800067a3  mov     dword ptr [rbp+4Fh+pvarg+8], eax
0x1800067a6  lea     rdx, aVendorMsftDiag; "./Vendor/MSFT/DiagnosticLog/EtwLog/Coll"...
0x1800067ad  lea     rcx, [rbp+4Fh+psz]
0x1800067b1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800067b6  nop
0x1800067b7  lea     r13, asc_18002A92C; "/"
0x1800067be  mov     rcx, r13
0x1800067c1  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800067c6  mov     r8, rax
0x1800067c9  mov     rdx, r13
0x1800067cc  lea     rcx, [rbp+4Fh+psz]; Src
0x1800067d0  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800067d5  mov     rcx, r12
0x1800067d8  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800067dd  mov     r8, rax
0x1800067e0  mov     rdx, r12
0x1800067e3  lea     rcx, [rbp+4Fh+psz]; Src
0x1800067e7  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800067ec  mov     rcx, r13
0x1800067ef  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800067f4  mov     r8, rax
0x1800067f7  mov     rdx, r13
0x1800067fa  lea     rcx, [rbp+4Fh+psz]; Src
0x1800067fe  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180006803  lea     rcx, aProviders; "Providers"
0x18000680a  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000680f  mov     r8, rax
0x180006812  mov     rdx, rcx
0x180006815  lea     rcx, [rbp+4Fh+psz]; Src
0x180006819  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000681e  mov     rcx, r13
0x180006821  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180006826  mov     r8, rax
0x180006829  mov     rdx, r13
0x18000682c  lea     rcx, [rbp+4Fh+psz]; Src
0x180006830  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180006835  mov     rcx, rbx
0x180006838  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000683d  mov     r8, rax
0x180006840  mov     rdx, rbx
0x180006843  lea     rcx, [rbp+4Fh+psz]; Src
0x180006847  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000684c  mov     rcx, r13
0x18000684f  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180006854  mov     r8, rax
0x180006857  mov     rdx, r13
0x18000685a  lea     rcx, [rbp+4Fh+psz]; Src
0x18000685e  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180006863  lea     rcx, aTracelevel; "TraceLevel"
0x18000686a  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000686f  mov     r8, rax
0x180006872  mov     rdx, rcx
0x180006875  lea     rcx, [rbp+4Fh+psz]; Src
0x180006879  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000687e  mov     [rsp+100h+var_D8], 0
0x180006887  lea     rcx, [rbp+4Fh+psz]
0x18000688b  cmp     [rbp+4Fh+var_40], 7
0x180006890  cmova   rcx, [rbp+4Fh+psz]; psz
0x180006895  call    cs:__imp_SysAllocString
0x18000689c  nop     dword ptr [rax+rax+00h]
0x1800068a1  mov     rdx, rax
0x1800068a4  lea     rcx, [rsp+100h+var_D8]
0x1800068a9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800068ae  mov     rbx, [rsp+100h+var_D8]
0x1800068b3  test    rbx, rbx
0x1800068b6  jnz     short loc_1800068DA
0x1800068b8  mov     rcx, [rbp+57h]; this
0x1800068bc  mov     ebx, 8007000Eh
0x1800068c1  mov     r9d, ebx; char *
0x1800068c4  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800068cb  mov     edx, 0D7h; void *
0x1800068d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800068d5  jmp     loc_180006B42
0x1800068da  mov     qword ptr [rsp+100h+var_E0], 0; int
0x1800068e3  mov     rsi, [r14]
0x1800068e6  mov     rax, [rsi]
0x1800068e9  mov     rdi, [rax+50h]
0x1800068ed  lea     rcx, [rsp+100h+var_E0]
0x1800068f2  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x1800068f7  lea     r8, [rsp+100h+var_E0]
0x1800068fc  mov     rdx, rbx
0x1800068ff  mov     rcx, rsi
0x180006902  mov     rax, rdi
0x180006905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000690a  mov     ebx, eax
0x18000690c  test    eax, eax
0x18000690e  jns     short loc_180006938
0x180006910  mov     edx, 0DAh; void *
0x180006915  mov     rcx, [rbp+57h]; this
0x180006919  mov     r9d, eax; char *
0x18000691c  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180006923  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006928  nop
0x180006929  lea     rcx, [rsp+100h+var_E0]
0x18000692e  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006933  jmp     loc_180006B42
0x180006938  mov     rcx, qword ptr [rsp+100h+var_E0]
0x18000693d  movups  xmm0, xmmword ptr [rsp+100h+pvarg]
0x180006942  movaps  [rbp+4Fh+var_B0], xmm0
0x180006946  movsd   xmm1, qword ptr [rbp+4Fh+pvarg+10h]
0x18000694b  movsd   [rbp+4Fh+var_A0], xmm1
0x180006950  mov     rax, [rcx]
0x180006953  xor     r8d, r8d
0x180006956  lea     rdx, [rbp+4Fh+var_B0]
0x18000695a  mov     rax, [rax+60h]
0x18000695e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006963  mov     ebx, eax
0x180006965  test    eax, eax
0x180006967  jns     short loc_180006970
0x180006969  mov     edx, 0DBh
0x18000696e  jmp     short loc_180006915
0x180006970  mov     rcx, [r14]
0x180006973  mov     rax, [rcx]
0x180006976  mov     rax, [rax+18h]
0x18000697a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000697f  mov     ebx, eax
0x180006981  test    eax, eax
0x180006983  jns     short loc_18000698C
0x180006985  mov     edx, 0DCh
0x18000698a  jmp     short loc_180006915
0x18000698c  lea     rdx, aVendorMsftDiag; "./Vendor/MSFT/DiagnosticLog/EtwLog/Coll"...
0x180006993  lea     rcx, [rbp+4Fh+Src]
0x180006997  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000699c  nop
0x18000699d  mov     rcx, r13
0x1800069a0  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800069a5  mov     r8, rax
0x1800069a8  mov     rdx, r13
0x1800069ab  lea     rcx, [rbp+4Fh+Src]; Src
0x1800069af  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800069b4  mov     rcx, r12
0x1800069b7  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800069bc  mov     r8, rax
0x1800069bf  mov     rdx, r12
0x1800069c2  lea     rcx, [rbp+4Fh+Src]; Src
0x1800069c6  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800069cb  mov     rcx, r13
0x1800069ce  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800069d3  mov     r8, rax
0x1800069d6  mov     rdx, r13
0x1800069d9  lea     rcx, [rbp+4Fh+Src]; Src
0x1800069dd  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800069e2  lea     rcx, aTracelogfilemo; "TraceLogFileMode"
0x1800069e9  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800069ee  mov     r8, rax
0x1800069f1  mov     rdx, rcx
0x1800069f4  lea     rcx, [rbp+4Fh+Src]; Src
0x1800069f8  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800069fd  lea     rcx, [rbp+4Fh+Src]
0x180006a01  cmp     [rbp+4Fh+var_60], 7
0x180006a06  cmova   rcx, [rbp+4Fh+Src]; psz
0x180006a0b  call    cs:__imp_SysAllocString
0x180006a12  nop     dword ptr [rax+rax+00h]
0x180006a17  mov     rdx, rax
0x180006a1a  lea     rcx, [rsp+100h+var_D8]
0x180006a1f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180006a24  mov     rbx, [rsp+100h+var_D8]
0x180006a29  test    rbx, rbx
0x180006a2c  jnz     short loc_180006A5A
0x180006a2e  mov     ebx, 8007000Eh
0x180006a33  mov     r9d, ebx; char *
0x180006a36  mov     edx, 0E6h; void *
0x180006a3b  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180006a42  mov     rcx, [rbp+57h]; this
0x180006a46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006a4b  nop
0x180006a4c  lea     rcx, [rbp+4Fh+Src]
0x180006a50  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006a55  jmp     loc_180006929
0x180006a5a  lea     rcx, [rsp+100h+pvarg]; pvarg
0x180006a5f  call    cs:__imp_VariantClear
0x180006a66  nop     dword ptr [rax+rax+00h]
0x180006a6b  lea     rcx, [rsp+100h+pvarg]; pvarg
0x180006a70  call    cs:__imp_VariantInit
0x180006a77  nop     dword ptr [rax+rax+00h]
0x180006a7c  mov     eax, 3
0x180006a81  mov     word ptr [rsp+100h+pvarg], ax
0x180006a86  neg     r15b
0x180006a89  sbb     eax, eax
0x180006a8b  neg     eax
0x180006a8d  inc     eax
0x180006a8f  mov     dword ptr [rbp+4Fh+pvarg+8], eax
0x180006a92  mov     rsi, [r14]
0x180006a95  mov     rax, [rsi]
0x180006a98  mov     rdi, [rax+50h]
0x180006a9c  lea     rcx, [rsp+100h+var_E0]
0x180006aa1  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006aa6  lea     r8, [rsp+100h+var_E0]
0x180006aab  mov     rdx, rbx
0x180006aae  mov     rcx, rsi
0x180006ab1  mov     rax, rdi
0x180006ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ab9  mov     ebx, eax
0x180006abb  test    eax, eax
0x180006abd  jns     short loc_180006ACC
0x180006abf  mov     r9d, eax
0x180006ac2  mov     edx, 0EDh
0x180006ac7  jmp     loc_180006A3B
0x180006acc  mov     rcx, qword ptr [rsp+100h+var_E0]
0x180006ad1  movups  xmm0, xmmword ptr [rsp+100h+pvarg]
0x180006ad6  movaps  [rbp+4Fh+var_B0], xmm0
0x180006ada  movsd   xmm1, qword ptr [rbp+4Fh+pvarg+10h]
0x180006adf  movsd   [rbp+4Fh+var_A0], xmm1
0x180006ae4  mov     rax, [rcx]
0x180006ae7  xor     r8d, r8d
0x180006aea  lea     rdx, [rbp+4Fh+var_B0]
0x180006aee  mov     rax, [rax+60h]
0x180006af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006af7  mov     ebx, eax
0x180006af9  test    eax, eax
0x180006afb  jns     short loc_180006B0A
0x180006afd  mov     r9d, eax
0x180006b00  mov     edx, 0EEh
0x180006b05  jmp     loc_180006A3B
0x180006b0a  mov     rcx, [r14]
0x180006b0d  mov     rax, [rcx]
0x180006b10  mov     rax, [rax+18h]
0x180006b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b19  mov     ebx, eax
0x180006b1b  test    eax, eax
0x180006b1d  jns     short loc_180006B2C
0x180006b1f  mov     r9d, eax
0x180006b22  mov     edx, 0EFh
0x180006b27  jmp     loc_180006A3B
0x180006b2c  lea     rcx, [rbp+4Fh+Src]
0x180006b30  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006b35  nop
0x180006b36  lea     rcx, [rsp+100h+var_E0]
0x180006b3b  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006b40  xor     ebx, ebx
0x180006b42  lea     rcx, [rsp+100h+var_D8]
0x180006b47  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180006b4c  nop
0x180006b4d  lea     rcx, [rbp+4Fh+psz]
0x180006b51  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006b56  nop
0x180006b57  lea     rcx, [rsp+100h+pvarg]; pvarg
0x180006b5c  call    cs:__imp_VariantClear
0x180006b63  nop     dword ptr [rax+rax+00h]
0x180006b68  nop
0x180006b69  mov     rcx, r14
0x180006b6c  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006b71  mov     eax, ebx
0x180006b73  mov     rcx, [rbp+4Fh+var_38]
0x180006b77  xor     rcx, rsp; StackCookie
0x180006b7a  call    __security_check_cookie
0x180006b7f  mov     rbx, [rsp+100h+arg_18]
0x180006b87  add     rsp, 0D0h
0x180006b8e  pop     r15
0x180006b90  pop     r14
0x180006b92  pop     r13
0x180006b94  pop     r12
0x180006b96  pop     rdi
0x180006b97  pop     rsi
0x180006b98  pop     rbp
0x180006b99  retn
```
