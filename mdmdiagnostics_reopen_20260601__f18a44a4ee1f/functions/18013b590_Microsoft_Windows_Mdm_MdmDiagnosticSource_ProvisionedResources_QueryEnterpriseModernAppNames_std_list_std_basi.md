# Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::QueryEnterpriseModernAppNames(std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::vector<AppStatus,std::allocator<AppStatus>> &)

- ea: `0x18013b590`
- end: `0x18013bbef`
- name: `?QueryEnterpriseModernAppNames@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@0AEAV?$vector@UAppStatus@@V?$allocator@UAppStatus@@@std@@@7@@Z`
- size: `1631`
- prototype: ``
- caller_count: `1`
- callee_count: `36`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18013184c`

## callees

- `0x180019080`
- `0x1800e4508`
- `0x1800e5744`
- `0x1800e6838`
- `0x1800e688c`
- `0x1800e68b0`
- `0x1800e69f4`
- `0x1800e8a44`
- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00e4`
- `0x1800f4b2c`
- `0x1800f9a08`
- `0x1800fa7d4`
- `0x1800faa0c`
- `0x180105688`
- `0x1801056d0`
- `0x180107298`
- `0x180109344`
- `0x18011273c`
- `0x180128c50`
- `0x180129304`
- `0x1801293b4`
- `0x180129960`
- `0x180129d4c`
- `0x18012c10c`
- `0x1801392a4`
- `0x18013941c`
- `0x1801398f4`
- `0x18013a658`
- `0x18013ab74`
- `0x18013b590`
- `0x18013c524`
- `0x18013c574`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x18013b77c`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x18013b77c`
- `OLEAUT32!__imp_VariantInit` at `0x18013b661`
- `OLEAUT32!__imp_VariantInit` at `0x18013b68e`
- `OLEAUT32!__imp_VariantInit` at `0x18013b661`
- `OLEAUT32!__imp_VariantInit` at `0x18013b68e`
- `OLEAUT32!__imp_VariantClear` at `0x18013bab5`
- `OLEAUT32!__imp_VariantClear` at `0x18013bad4`
- `OLEAUT32!__imp_VariantClear` at `0x18013bb3d`
- `OLEAUT32!__imp_VariantClear` at `0x18013bb5c`
- `OLEAUT32!__imp_VariantClear` at `0x18013bab5`
- `OLEAUT32!__imp_VariantClear` at `0x18013bad4`
- `OLEAUT32!__imp_VariantClear` at `0x18013bb3d`
- `OLEAUT32!__imp_VariantClear` at `0x18013bb5c`

## string_xrefs

- `0x18013b7e0`: `Not Installed`
- `0x18013b7d7`: `Installing`
- `0x18013b7c5`: `Installed`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::QueryEnterpriseModernAppNames(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4)
{
  int ConfigManager2; // eax
  unsigned int v8; // ebx
  __int64 v9; // rcx
  _QWORD *v10; // rdi
  _QWORD *i; // rbx
  __int64 v12; // rax
  int v13; // eax
  int v14; // esi
  __int64 v15; // rsi
  __int64 v16; // rax
  __int64 v17; // rax
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v18; // rsi
  __int64 v19; // rax
  const wchar_t *v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rsi
  __int64 v26; // rax
  WCHAR *v27; // rax
  unsigned int v28; // esi
  __int64 v29; // rsi
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rcx
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+20h] [rbp-E0h]
  int v37[2]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v38[2]; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG v40; // [rsp+60h] [rbp-A0h] BYREF
  char v41; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v42[16]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v43[240]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v44[16]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v45; // [rsp+190h] [rbp+90h]
  _BYTE v46[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v47[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v48[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v49[32]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v50[16]; // [rsp+220h] [rbp+120h] BYREF
  __int64 v51; // [rsp+230h] [rbp+130h]
  _BYTE v52[16]; // [rsp+240h] [rbp+140h] BYREF
  __int64 v53; // [rsp+250h] [rbp+150h]
  _BYTE v54[32]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v55[32]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v56[32]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v57[32]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v58[32]; // [rsp+2E0h] [rbp+1E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  *(_QWORD *)v37 = 0;
  ConfigManager2 = Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::CreateConfigManager2((LPVOID *)v37);
  v8 = ConfigManager2;
  if ( ConfigManager2 >= 0 )
  {
    std::list<std::wstring>::list<std::wstring>(v38, a2);
    std::list<std::wstring>::insert<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>,0>(
      (unsigned int)v38,
      (unsigned int)&v41,
      v38[0],
      *(_QWORD *)*a3,
      *a3);
    v10 = (_QWORD *)v38[0];
    for ( i = *(_QWORD **)v38[0]; ; i = (_QWORD *)*i )
    {
      if ( i == v10 )
      {
        std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
          v9,
          v38[0]);
        std::_Deallocate<16>(v38[0], 48);
        v8 = 0;
        goto LABEL_36;
      }
      std::wstring::wstring(v46, i + 2);
      std::wstring::wstring(v44);
      VariantInit(&pvarg);
      std::operator+<unsigned short>(v47, v46, L"/Status");
      VariantInit(&v40);
      std::operator+<unsigned short>(v48, v46, L"/LastError");
      AppStatus::AppStatus((AppStatus *)v55);
      std::wstring::operator=(v57, qword_1802687F0);
      v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v47);
      v13 = Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::QueryCspNodeValue(v37, v12, &pvarg);
      v14 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x263,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
          (const char *)(unsigned int)v13,
          v36);
        AppStatus::~AppStatus((AppStatus *)v55);
        std::wstring::_Tidy_deallocate(v48);
        VariantClear(&v40);
        std::wstring::_Tidy_deallocate(v47);
        VariantClear(&pvarg);
        std::wstring::_Tidy_deallocate(v44);
        std::wstring::_Tidy_deallocate(v46);
        std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
          v33,
          v38[0]);
        std::_Deallocate<16>(v38[0], 48);
        v8 = v14;
        goto LABEL_36;
      }
      if ( pvarg.vt == 3 )
      {
        if ( pvarg.lVal )
        {
          switch ( pvarg.lVal )
          {
            case 1:
              v20 = L"Installing";
              break;
            case 2:
              v20 = L"Failed";
              break;
            case 3:
              v20 = L"Installed";
              break;
            default:
              std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v42);
              v15 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                      v43,
                      L"Unrecognized status received for ");
              v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v47);
              std::operator<<<unsigned short,std::char_traits<unsigned short>>(v15, v16);
              v17 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v43, L". Status: ");
              std::basic_ostream<unsigned short>::operator<<(v17, pvarg.cyVal.Lo);
              v18 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
              v19 = std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
                      v42,
                      v49);
              Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v18, v19);
              std::wstring::_Tidy_deallocate(v49);
              std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v42);
              goto LABEL_17;
          }
        }
        else
        {
          v20 = L"Not Installed";
        }
        std::wstring::assign(v44, v20);
      }
LABEL_17:
      if ( !v45 )
        goto LABEL_33;
      if ( !(unsigned int)std::wstring::compare(v44, L"Failed") )
      {
        v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v48);
        if ( (int)Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::QueryCspNodeValue(v37, v21, &v40) < 0 )
        {
          std::wstring::operator=(v57, qword_1802687D0);
          goto LABEL_33;
        }
        if ( v40.vt == 3 )
        {
          v22 = std::to_wstring(v49, v40.cyVal.Lo);
          std::wstring::operator=(v57, v22);
          std::wstring::_Tidy_deallocate(v49);
        }
      }
      std::wstring::operator=(v56, v44);
      std::wstring::wstring(v52, L"/EnterpriseModernAppManagement/");
      v23 = std::wstring::find(v46, v52, 0);
      if ( v23 != -1 )
      {
        std::wstring::substr(v46, v54, 0, v23 + v53);
        std::wstring::append(v54, L"AppManagement");
        std::wstring::wstring(v50);
        if ( (int)Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::GetModernAppName(
                    v24,
                    v37,
                    v54,
                    v50) >= 0 )
        {
          if ( v51 )
          {
            std::wstring::operator=(v55, v50);
            std::vector<AppStatus>::emplace_back<AppStatus &>(a4, v55);
          }
          else
          {
            v25 = std::wstring::rfind(v46, 47, -1);
            if ( v25 != -1 )
            {
              std::wstring::wstring(v49);
              v26 = std::wstring::substr(v46, v58, v25 + 1, -1);
              v27 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
              v28 = (unsigned int)UrlUnEscapeWrapper(v27) >> 31;
              std::wstring::_Tidy_deallocate(v58);
              if ( !(_BYTE)v28 )
              {
                std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v42);
                v29 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v43, L"Modern App(");
                v30 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v49);
                v31 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v29, v30);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(v31, L")");
                v32 = std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
                        v42,
                        v58);
                std::wstring::operator=(v55, v32);
                std::wstring::_Tidy_deallocate(v58);
                std::vector<AppStatus>::emplace_back<AppStatus &>(a4, v55);
                std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v42);
              }
              std::wstring::_Tidy_deallocate(v49);
            }
          }
        }
        std::wstring::_Tidy_deallocate(v50);
        std::wstring::_Tidy_deallocate(v54);
      }
      std::wstring::_Tidy_deallocate(v52);
LABEL_33:
      AppStatus::~AppStatus((AppStatus *)v55);
      std::wstring::_Tidy_deallocate(v48);
      VariantClear(&v40);
      std::wstring::_Tidy_deallocate(v47);
      VariantClear(&pvarg);
      std::wstring::_Tidy_deallocate(v44);
      std::wstring::_Tidy_deallocate(v46);
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x254,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
    (const char *)(unsigned int)ConfigManager2,
    v35);
LABEL_36:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(v37);
  return v8;
}

```

## disassembly

```asm
0x18013b590  mov     [rsp-8+arg_0], rbx
0x18013b595  mov     [rsp-8+arg_10], rsi
0x18013b59a  push    rbp
0x18013b59b  push    rdi
0x18013b59c  push    r14
0x18013b59e  lea     rbp, [rsp-210h]
0x18013b5a6  sub     rsp, 310h
0x18013b5ad  mov     rax, cs:__security_cookie
0x18013b5b4  xor     rax, rsp
0x18013b5b7  mov     [rbp+220h+var_20], rax
0x18013b5be  mov     r14, r9
0x18013b5c1  mov     rdi, r8
0x18013b5c4  mov     rsi, rdx
0x18013b5c7  mov     qword ptr [rsp+320h+var_2F0], 0
0x18013b5d0  lea     rcx, [rsp+320h+var_2F0]; int
0x18013b5d5  call    ?CreateConfigManager2@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAJAEAV?$ComPtr@UIConfigManager2@@@WRL@5@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::CreateConfigManager2(Microsoft::WRL::ComPtr<IConfigManager2> &)
0x18013b5da  mov     ebx, eax
0x18013b5dc  test    eax, eax
0x18013b5de  jns     short loc_18013B600
0x18013b5e0  mov     rcx, [rbp+228h]; this
0x18013b5e7  mov     r9d, eax; char *
0x18013b5ea  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013b5f1  mov     edx, 254h; void *
0x18013b5f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b5fb  jmp     loc_18013BBBB
0x18013b600  mov     rdx, rsi
0x18013b603  lea     rcx, [rsp+320h+var_2E8]
0x18013b608  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::list<std::wstring>::list<std::wstring>(std::list<std::wstring> const &)
0x18013b60d  nop
0x18013b60e  mov     r9, [rdi]
0x18013b611  mov     qword ptr [rsp+320h+var_300], r9; int
0x18013b616  mov     r9, [r9]
0x18013b619  mov     r8, [rsp+320h+var_2E8]
0x18013b61e  lea     rdx, [rsp+320h+var_2A8]
0x18013b623  lea     rcx, [rsp+320h+var_2E8]
0x18013b628  call    ??$insert@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@$0A@@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@V21@1@Z; std::list<std::wstring>::insert<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>,0>(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>,std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>,std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>)
0x18013b62d  mov     rdi, [rsp+320h+var_2E8]
0x18013b632  mov     rbx, [rdi]
0x18013b635  cmp     rbx, rdi
0x18013b638  jz      loc_18013BBA0
0x18013b63e  lea     rdx, [rbx+10h]
0x18013b642  lea     rcx, [rbp+220h+var_180]
0x18013b649  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18013b64e  nop
0x18013b64f  lea     rcx, [rbp+220h+var_1A0]
0x18013b656  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18013b65b  nop
0x18013b65c  lea     rcx, [rsp+320h+pvarg]; pvarg
0x18013b661  call    cs:__imp_VariantInit
0x18013b668  nop     dword ptr [rax+rax+00h]
0x18013b66d  nop
0x18013b66e  lea     r8, aStatus_1; "/Status"
0x18013b675  lea     rdx, [rbp+220h+var_180]
0x18013b67c  lea     rcx, [rbp+220h+var_160]
0x18013b683  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18013b688  nop
0x18013b689  lea     rcx, [rsp+320h+var_2C0]; pvarg
0x18013b68e  call    cs:__imp_VariantInit
0x18013b695  nop     dword ptr [rax+rax+00h]
0x18013b69a  nop
0x18013b69b  lea     r8, aLasterror; "/LastError"
0x18013b6a2  lea     rdx, [rbp+220h+var_180]
0x18013b6a9  lea     rcx, [rbp+220h+var_140]
0x18013b6b0  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18013b6b5  nop
0x18013b6b6  lea     rcx, [rbp+220h+var_A0]; this
0x18013b6bd  call    ??0AppStatus@@QEAA@XZ; AppStatus::AppStatus(void)
0x18013b6c2  nop
0x18013b6c3  lea     rdx, qword_1802687F0
0x18013b6ca  lea     rcx, [rbp+220h+var_60]
0x18013b6d1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18013b6d6  lea     rcx, [rbp+220h+var_160]
0x18013b6dd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013b6e2  mov     rdx, rax
0x18013b6e5  lea     r8, [rsp+320h+pvarg]
0x18013b6ea  lea     rcx, [rsp+320h+var_2F0]
0x18013b6ef  call    ?QueryCspNodeValue@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAJAEAV?$ComPtr@UIConfigManager2@@@WRL@5@PEBGAEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::QueryCspNodeValue(Microsoft::WRL::ComPtr<IConfigManager2> &,ushort const *,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &)
0x18013b6f4  mov     esi, eax
0x18013b6f6  test    eax, eax
0x18013b6f8  js      loc_18013BB02
0x18013b6fe  cmp     word ptr [rsp+320h+pvarg], 3
0x18013b704  jnz     loc_18013B7F3
0x18013b70a  mov     ecx, dword ptr [rsp+320h+pvarg+8]
0x18013b70e  test    ecx, ecx
0x18013b710  jz      loc_18013B7E0
0x18013b716  sub     ecx, 1
0x18013b719  jz      loc_18013B7D7
0x18013b71f  sub     ecx, 1
0x18013b722  jz      loc_18013B7CE
0x18013b728  cmp     ecx, 1
0x18013b72b  jz      loc_18013B7C5
0x18013b731  lea     rcx, [rbp+220h+var_2A0]
0x18013b735  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x18013b73a  nop
0x18013b73b  lea     rdx, aUnrecognizedSt; "Unrecognized status received for "
0x18013b742  lea     rcx, [rbp+220h+var_290]
0x18013b746  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18013b74b  mov     rsi, rax
0x18013b74e  lea     rcx, [rbp+220h+var_160]
0x18013b755  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013b75a  mov     rdx, rax
0x18013b75d  mov     rcx, rsi
0x18013b760  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18013b765  lea     rdx, aStatus_0; ". Status: "
0x18013b76c  lea     rcx, [rbp+220h+var_290]
0x18013b770  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18013b775  mov     edx, dword ptr [rsp+320h+pvarg+8]
0x18013b779  mov     rcx, rax
0x18013b77c  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z; std::basic_ostream<ushort>::operator<<(long)
0x18013b783  nop     dword ptr [rax+rax+00h]
0x18013b788  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013b78d  mov     rsi, rax
0x18013b790  lea     rdx, [rbp+220h+var_120]
0x18013b797  lea     rcx, [rbp+220h+var_2A0]
0x18013b79b  call    ?str@?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::str(void)
0x18013b7a0  nop
0x18013b7a1  mov     rdx, rax
0x18013b7a4  mov     rcx, rsi
0x18013b7a7  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(std::wstring const &)
0x18013b7ac  nop
0x18013b7ad  lea     rcx, [rbp+220h+var_120]
0x18013b7b4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013b7b9  nop
0x18013b7ba  lea     rcx, [rbp+220h+var_2A0]
0x18013b7be  call    ??_D?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
0x18013b7c3  jmp     short loc_18013B7F3
0x18013b7c5  lea     rdx, aInstalled; "Installed"
0x18013b7cc  jmp     short loc_18013B7E7
0x18013b7ce  lea     rdx, aFailed_0; "Failed"
0x18013b7d5  jmp     short loc_18013B7E7
0x18013b7d7  lea     rdx, aInstalling; "Installing"
0x18013b7de  jmp     short loc_18013B7E7
0x18013b7e0  lea     rdx, aNotInstalled; "Not Installed"
0x18013b7e7  lea     rcx, [rbp+220h+var_1A0]
0x18013b7ee  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18013b7f3  cmp     [rbp+220h+var_190], 0
0x18013b7fb  jz      loc_18013BA96
0x18013b801  lea     rdx, aFailed_0; "Failed"
0x18013b808  lea     rcx, [rbp+220h+var_1A0]
0x18013b80f  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x18013b814  test    eax, eax
0x18013b816  jnz     short loc_18013B885
0x18013b818  lea     rcx, [rbp+220h+var_140]
0x18013b81f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013b824  mov     rdx, rax
0x18013b827  lea     r8, [rsp+320h+var_2C0]
0x18013b82c  lea     rcx, [rsp+320h+var_2F0]
0x18013b831  call    ?QueryCspNodeValue@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAJAEAV?$ComPtr@UIConfigManager2@@@WRL@5@PEBGAEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::QueryCspNodeValue(Microsoft::WRL::ComPtr<IConfigManager2> &,ushort const *,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &)
0x18013b836  test    eax, eax
0x18013b838  jns     short loc_18013B852
0x18013b83a  lea     rdx, qword_1802687D0
0x18013b841  lea     rcx, [rbp+220h+var_60]
0x18013b848  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18013b84d  jmp     loc_18013BA96
0x18013b852  cmp     word ptr [rsp+320h+var_2C0], 3
0x18013b858  jnz     short loc_18013B885
0x18013b85a  mov     edx, dword ptr [rsp+320h+var_2C0+8]
0x18013b85e  lea     rcx, [rbp+220h+var_120]
0x18013b865  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@J@Z; std::to_wstring(long)
0x18013b86a  mov     rdx, rax
0x18013b86d  lea     rcx, [rbp+220h+var_60]
0x18013b874  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18013b879  lea     rcx, [rbp+220h+var_120]
0x18013b880  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013b885  lea     rdx, [rbp+220h+var_1A0]
0x18013b88c  lea     rcx, [rbp+220h+var_80]
0x18013b893  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18013b898  lea     rdx, aEnterprisemode; "/EnterpriseModernAppManagement/"
0x18013b89f  lea     rcx, [rbp+220h+var_E0]
0x18013b8a6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013b8ab  nop
0x18013b8ac  xor     r8d, r8d
0x18013b8af  lea     rdx, [rbp+220h+var_E0]
0x18013b8b6  lea     rcx, [rbp+220h+var_180]
0x18013b8bd  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x18013b8c2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18013b8c6  jz      loc_18013BA89
0x18013b8cc  mov     r9, [rbp+220h+var_D0]
0x18013b8d3  add     r9, rax
0x18013b8d6  xor     r8d, r8d
0x18013b8d9  lea     rdx, [rbp+220h+var_C0]
0x18013b8e0  lea     rcx, [rbp+220h+var_180]
0x18013b8e7  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18013b8ec  nop
0x18013b8ed  lea     rdx, aAppmanagement; "AppManagement"
0x18013b8f4  lea     rcx, [rbp+220h+var_C0]
0x18013b8fb  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18013b900  lea     rcx, [rbp+220h+var_100]
0x18013b907  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18013b90c  nop
0x18013b90d  lea     r9, [rbp+220h+var_100]
0x18013b914  lea     r8, [rbp+220h+var_C0]
0x18013b91b  lea     rdx, [rsp+320h+var_2F0]
0x18013b920  call    ?GetModernAppName@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJAEAV?$ComPtr@UIConfigManager2@@@WRL@5@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::GetModernAppName(Microsoft::WRL::ComPtr<IConfigManager2> &,std::wstring &,std::wstring &)
0x18013b925  test    eax, eax
0x18013b927  js      loc_18013BA6F
0x18013b92d  cmp     [rbp+220h+var_F0], 0
0x18013b935  jnz     loc_18013BA4C
0x18013b93b  mov     edx, 2Fh ; '/'
0x18013b940  or      r8, 0FFFFFFFFFFFFFFFFh
0x18013b944  lea     rcx, [rbp+220h+var_180]
0x18013b94b  call    ?rfind@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::rfind(ushort,unsigned __int64)
0x18013b950  mov     rsi, rax
0x18013b953  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18013b957  jz      loc_18013BA6F
0x18013b95d  lea     rcx, [rbp+220h+var_120]
0x18013b964  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18013b969  nop
0x18013b96a  lea     r8, [rsi+1]
0x18013b96e  or      r9, 0FFFFFFFFFFFFFFFFh
0x18013b972  lea     rdx, [rbp+220h+var_40]
0x18013b979  lea     rcx, [rbp+220h+var_180]
0x18013b980  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18013b985  mov     rcx, rax
0x18013b988  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013b98d  lea     rdx, [rbp+220h+var_120]
0x18013b994  mov     rcx, rax; pszUrl
0x18013b997  call    ?UrlUnEscapeWrapper@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; UrlUnEscapeWrapper(ushort const *,std::wstring &)
0x18013b99c  mov     esi, eax
0x18013b99e  shr     esi, 1Fh
0x18013b9a1  lea     rcx, [rbp+220h+var_40]
0x18013b9a8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013b9ad  test    sil, sil
0x18013b9b0  jnz     loc_18013BA3E
0x18013b9b6  lea     rcx, [rbp+220h+var_2A0]
0x18013b9ba  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x18013b9bf  nop
0x18013b9c0  lea     rdx, aModernApp; "Modern App("
0x18013b9c7  lea     rcx, [rbp+220h+var_290]
0x18013b9cb  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18013b9d0  mov     rsi, rax
0x18013b9d3  lea     rcx, [rbp+220h+var_120]
0x18013b9da  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013b9df  mov     rdx, rax
0x18013b9e2  mov     rcx, rsi
0x18013b9e5  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18013b9ea  mov     rcx, rax
0x18013b9ed  lea     rdx, asc_1801EE8B0; ")"
0x18013b9f4  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18013b9f9  lea     rdx, [rbp+220h+var_40]
0x18013ba00  lea     rcx, [rbp+220h+var_2A0]
0x18013ba04  call    ?str@?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::str(void)
0x18013ba09  mov     rdx, rax
0x18013ba0c  lea     rcx, [rbp+220h+var_A0]
0x18013ba13  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18013ba18  lea     rcx, [rbp+220h+var_40]
0x18013ba1f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ba24  lea     rdx, [rbp+220h+var_A0]
0x18013ba2b  mov     rcx, r14
0x18013ba2e  call    ??$emplace_back@AEAUAppStatus@@@?$vector@UAppStatus@@V?$allocator@UAppStatus@@@std@@@std@@QEAAAEAUAppStatus@@AEAU2@@Z; std::vector<AppStatus>::emplace_back<AppStatus &>(AppStatus &)
0x18013ba33  nop
0x18013ba34  lea     rcx, [rbp+220h+var_2A0]
0x18013ba38  call    ??_D?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
0x18013ba3d  nop
0x18013ba3e  lea     rcx, [rbp+220h+var_120]
0x18013ba45  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ba4a  jmp     short loc_18013BA6F
0x18013ba4c  lea     rdx, [rbp+220h+var_100]
0x18013ba53  lea     rcx, [rbp+220h+var_A0]
0x18013ba5a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18013ba5f  lea     rdx, [rbp+220h+var_A0]
0x18013ba66  mov     rcx, r14
0x18013ba69  call    ??$emplace_back@AEAUAppStatus@@@?$vector@UAppStatus@@V?$allocator@UAppStatus@@@std@@@std@@QEAAAEAUAppStatus@@AEAU2@@Z; std::vector<AppStatus>::emplace_back<AppStatus &>(AppStatus &)
0x18013ba6e  nop
0x18013ba6f  lea     rcx, [rbp+220h+var_100]
0x18013ba76  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ba7b  nop
0x18013ba7c  lea     rcx, [rbp+220h+var_C0]
0x18013ba83  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ba88  nop
0x18013ba89  lea     rcx, [rbp+220h+var_E0]
0x18013ba90  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ba95  nop
0x18013ba96  lea     rcx, [rbp+220h+var_A0]; this
0x18013ba9d  call    ??1AppStatus@@QEAA@XZ; AppStatus::~AppStatus(void)
0x18013baa2  nop
0x18013baa3  lea     rcx, [rbp+220h+var_140]
0x18013baaa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013baaf  nop
0x18013bab0  lea     rcx, [rsp+320h+var_2C0]; pvarg
0x18013bab5  call    cs:__imp_VariantClear
0x18013babc  nop     dword ptr [rax+rax+00h]
0x18013bac1  nop
0x18013bac2  lea     rcx, [rbp+220h+var_160]
0x18013bac9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013bace  nop
0x18013bacf  lea     rcx, [rsp+320h+pvarg]; pvarg
0x18013bad4  call    cs:__imp_VariantClear
0x18013badb  nop     dword ptr [rax+rax+00h]
0x18013bae0  nop
0x18013bae1  lea     rcx, [rbp+220h+var_1A0]
0x18013bae8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013baed  nop
0x18013baee  lea     rcx, [rbp+220h+var_180]
0x18013baf5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013bafa  mov     rbx, [rbx]
0x18013bafd  jmp     loc_18013B635
0x18013bb02  mov     rcx, [rbp+228h]; this
0x18013bb09  mov     r9d, esi; char *
0x18013bb0c  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
  ... truncated ...
```
