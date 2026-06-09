# Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::QueryEnterpriseModernAppNames(std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::vector<AppStatus,std::allocator<AppStatus>> &)

- ea: `0x1801393c8`
- end: `0x180139a04`
- name: `?QueryEnterpriseModernAppNames@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@0AEAV?$vector@UAppStatus@@V?$allocator@UAppStatus@@@std@@@7@@Z`
- size: `1596`
- prototype: ``
- caller_count: `1`
- callee_count: `36`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18012fa78`

## callees

- `0x180019000`
- `0x1800e4444`
- `0x1800e5594`
- `0x1800e6664`
- `0x1800e66b8`
- `0x1800e66dc`
- `0x1800e680c`
- `0x1800e87e8`
- `0x1800ead14`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef900`
- `0x1800f3f8c`
- `0x1800f8a0c`
- `0x1800f97d0`
- `0x1800f9a0c`
- `0x180104460`
- `0x1801044a8`
- `0x180105fec`
- `0x180108060`
- `0x18011129c`
- `0x1801271ec`
- `0x180127820`
- `0x1801278d0`
- `0x180127e64`
- `0x180128238`
- `0x18012a4fc`
- `0x180137220`
- `0x180137388`
- `0x180137840`
- `0x18013850c`
- `0x1801389ec`
- `0x1801393c8`
- `0x18013a320`
- `0x18013a370`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x1801395a8`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x1801395a8`
- `OLEAUT32!__imp_VariantInit` at `0x180139499`
- `OLEAUT32!__imp_VariantInit` at `0x1801394c0`
- `OLEAUT32!__imp_VariantInit` at `0x180139499`
- `OLEAUT32!__imp_VariantInit` at `0x1801394c0`
- `OLEAUT32!__imp_VariantClear` at `0x1801398e3`
- `OLEAUT32!__imp_VariantClear` at `0x1801398fc`
- `OLEAUT32!__imp_VariantClear` at `0x18013995f`
- `OLEAUT32!__imp_VariantClear` at `0x180139978`
- `OLEAUT32!__imp_VariantClear` at `0x1801398e3`
- `OLEAUT32!__imp_VariantClear` at `0x1801398fc`
- `OLEAUT32!__imp_VariantClear` at `0x18013995f`
- `OLEAUT32!__imp_VariantClear` at `0x180139978`

## string_xrefs

- `0x18013960a`: `Not Installed`
- `0x180139601`: `Installing`
- `0x1801395ef`: `Installed`

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
  const wchar_t *v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rsi
  __int64 v25; // rax
  WCHAR *v26; // rax
  unsigned int v27; // esi
  __int64 v28; // rsi
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rcx
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  int v35[2]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v36[2]; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG v38; // [rsp+60h] [rbp-A0h] BYREF
  char v39; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v40[16]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v41[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v42[232]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v43[16]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v44; // [rsp+190h] [rbp+90h]
  _BYTE v45[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v46[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v47[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v48[32]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v49[16]; // [rsp+220h] [rbp+120h] BYREF
  __int64 v50; // [rsp+230h] [rbp+130h]
  _BYTE v51[16]; // [rsp+240h] [rbp+140h] BYREF
  __int64 v52; // [rsp+250h] [rbp+150h]
  _BYTE v53[32]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v54[32]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v55[32]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v56[32]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v57[32]; // [rsp+2E0h] [rbp+1E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  *(_QWORD *)v35 = 0;
  ConfigManager2 = Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::CreateConfigManager2((LPVOID *)v35);
  v8 = ConfigManager2;
  if ( ConfigManager2 >= 0 )
  {
    std::list<std::wstring>::list<std::wstring>(v36, a2);
    std::list<std::wstring>::insert<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>,0>(
      (unsigned int)v36,
      (unsigned int)&v39,
      v36[0],
      *(_QWORD *)*a3,
      *a3);
    v10 = (_QWORD *)v36[0];
    for ( i = *(_QWORD **)v36[0]; ; i = (_QWORD *)*i )
    {
      if ( i == v10 )
      {
        std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
          v9,
          v36[0]);
        std::_Deallocate<16>(v36[0], 48);
        v8 = 0;
        goto LABEL_36;
      }
      std::wstring::wstring(v45, i + 2);
      std::wstring::wstring(v43);
      VariantInit(&pvarg);
      std::operator+<unsigned short>(v46, v45, L"/Status");
      VariantInit(&v38);
      std::operator+<unsigned short>(v47, v45, L"/LastError");
      AppStatus::AppStatus((AppStatus *)v55);
      std::wstring::operator=(v57, qword_1802665D0);
      v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v46);
      v13 = Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::QueryCspNodeValue(v35, v12, &pvarg);
      v14 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x263,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
          (const char *)(unsigned int)v13,
          v34);
        AppStatus::~AppStatus((AppStatus *)v55);
        std::wstring::_Tidy_deallocate(v47);
        VariantClear(&v38);
        std::wstring::_Tidy_deallocate(v46);
        VariantClear(&pvarg);
        std::wstring::_Tidy_deallocate(v43);
        std::wstring::_Tidy_deallocate(v45);
        std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
          v31,
          v36[0]);
        std::_Deallocate<16>(v36[0], 48);
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
              v19 = L"Installing";
              break;
            case 2:
              v19 = L"Failed";
              break;
            case 3:
              v19 = L"Installed";
              break;
            default:
              std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v40);
              v15 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                      v41,
                      L"Unrecognized status received for ");
              v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v46);
              std::operator<<<unsigned short,std::char_traits<unsigned short>>(v15, v16);
              v17 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v41, L". Status: ");
              std::basic_ostream<unsigned short>::operator<<(v17, pvarg.cyVal.Lo);
              v18 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
              std::basic_stringbuf<unsigned short>::str(v42, v48);
              Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v18, v48);
              std::wstring::_Tidy_deallocate(v48);
              std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v40);
              goto LABEL_17;
          }
        }
        else
        {
          v19 = L"Not Installed";
        }
        std::wstring::assign(v43, v19);
      }
LABEL_17:
      if ( !v44 )
        goto LABEL_33;
      if ( !(unsigned int)std::wstring::compare(v43, L"Failed") )
      {
        v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v47);
        if ( (int)Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::QueryCspNodeValue(v35, v20, &v38) < 0 )
        {
          std::wstring::operator=(v57, qword_1802665B0);
          goto LABEL_33;
        }
        if ( v38.vt == 3 )
        {
          v21 = std::to_wstring(v53, v38.cyVal.Lo);
          std::wstring::operator=(v57, v21);
          std::wstring::_Tidy_deallocate(v53);
        }
      }
      std::wstring::operator=(v56, v43);
      std::wstring::wstring(v51, L"/EnterpriseModernAppManagement/");
      v22 = std::wstring::find(v45, v51, 0);
      if ( v22 != -1 )
      {
        std::wstring::substr(v45, v54, 0, v22 + v52);
        std::wstring::append(v54, L"AppManagement");
        std::wstring::wstring(v49);
        if ( (int)Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::GetModernAppName(
                    v23,
                    v35,
                    v54,
                    v49) >= 0 )
        {
          if ( v50 )
          {
            std::wstring::operator=(v55, v49);
            std::vector<AppStatus>::emplace_back<AppStatus &>(a4, v55);
          }
          else
          {
            v24 = std::wstring::rfind(v45, 47, -1);
            if ( v24 != -1 )
            {
              std::wstring::wstring(v48);
              v25 = std::wstring::substr(v45, v53, v24 + 1, -1);
              v26 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v25);
              v27 = (unsigned int)UrlUnEscapeWrapper(v26) >> 31;
              std::wstring::_Tidy_deallocate(v53);
              if ( !(_BYTE)v27 )
              {
                std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v40);
                v28 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v41, L"Modern App(");
                v29 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v48);
                v30 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v28, v29);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(v30, L")");
                std::basic_stringbuf<unsigned short>::str(v42, v53);
                std::wstring::operator=(v55, v53);
                std::wstring::_Tidy_deallocate(v53);
                std::vector<AppStatus>::emplace_back<AppStatus &>(a4, v55);
                std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v40);
              }
              std::wstring::_Tidy_deallocate(v48);
            }
          }
        }
        std::wstring::_Tidy_deallocate(v49);
        std::wstring::_Tidy_deallocate(v54);
      }
      std::wstring::_Tidy_deallocate(v51);
LABEL_33:
      AppStatus::~AppStatus((AppStatus *)v55);
      std::wstring::_Tidy_deallocate(v47);
      VariantClear(&v38);
      std::wstring::_Tidy_deallocate(v46);
      VariantClear(&pvarg);
      std::wstring::_Tidy_deallocate(v43);
      std::wstring::_Tidy_deallocate(v45);
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x254,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
    (const char *)(unsigned int)ConfigManager2,
    v33);
LABEL_36:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(v35);
  return v8;
}

```

## disassembly

```asm
0x1801393c8  mov     [rsp-8+arg_0], rbx
0x1801393cd  mov     [rsp-8+arg_10], rsi
0x1801393d2  push    rbp
0x1801393d3  push    rdi
0x1801393d4  push    r14
0x1801393d6  lea     rbp, [rsp-210h]
0x1801393de  sub     rsp, 310h
0x1801393e5  mov     rax, cs:__security_cookie
0x1801393ec  xor     rax, rsp
0x1801393ef  mov     [rbp+220h+var_20], rax
0x1801393f6  mov     r14, r9
0x1801393f9  mov     rdi, r8
0x1801393fc  mov     rsi, rdx
0x1801393ff  mov     qword ptr [rsp+320h+var_2F0], 0
0x180139408  lea     rcx, [rsp+320h+var_2F0]; int
0x18013940d  call    ?CreateConfigManager2@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAJAEAV?$ComPtr@UIConfigManager2@@@WRL@5@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::CreateConfigManager2(Microsoft::WRL::ComPtr<IConfigManager2> &)
0x180139412  mov     ebx, eax
0x180139414  test    eax, eax
0x180139416  jns     short loc_180139438
0x180139418  mov     rcx, [rbp+228h]; this
0x18013941f  mov     r9d, eax; char *
0x180139422  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180139429  mov     edx, 254h; void *
0x18013942e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180139433  jmp     loc_1801399D1
0x180139438  mov     rdx, rsi
0x18013943b  lea     rcx, [rsp+320h+var_2E8]
0x180139440  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::list<std::wstring>::list<std::wstring>(std::list<std::wstring> const &)
0x180139445  nop
0x180139446  mov     r9, [rdi]
0x180139449  mov     qword ptr [rsp+320h+var_300], r9; int
0x18013944e  mov     r9, [r9]
0x180139451  mov     r8, [rsp+320h+var_2E8]
0x180139456  lea     rdx, [rsp+320h+var_2A8]
0x18013945b  lea     rcx, [rsp+320h+var_2E8]
0x180139460  call    ??$insert@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@$0A@@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@V21@1@Z; std::list<std::wstring>::insert<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>,0>(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>,std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>,std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>)
0x180139465  mov     rdi, [rsp+320h+var_2E8]
0x18013946a  mov     rbx, [rdi]
0x18013946d  cmp     rbx, rdi
0x180139470  jz      loc_1801399B6
0x180139476  lea     rdx, [rbx+10h]
0x18013947a  lea     rcx, [rbp+220h+var_180]
0x180139481  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180139486  nop
0x180139487  lea     rcx, [rbp+220h+var_1A0]
0x18013948e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180139493  nop
0x180139494  lea     rcx, [rsp+320h+pvarg]; pvarg
0x180139499  call    cs:__imp_VariantInit
0x18013949f  nop
0x1801394a0  lea     r8, aStatus_1; "/Status"
0x1801394a7  lea     rdx, [rbp+220h+var_180]
0x1801394ae  lea     rcx, [rbp+220h+var_160]
0x1801394b5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1801394ba  nop
0x1801394bb  lea     rcx, [rsp+320h+var_2C0]; pvarg
0x1801394c0  call    cs:__imp_VariantInit
0x1801394c6  nop
0x1801394c7  lea     r8, aLasterror; "/LastError"
0x1801394ce  lea     rdx, [rbp+220h+var_180]
0x1801394d5  lea     rcx, [rbp+220h+var_140]
0x1801394dc  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1801394e1  nop
0x1801394e2  lea     rcx, [rbp+220h+var_80]; this
0x1801394e9  call    ??0AppStatus@@QEAA@XZ; AppStatus::AppStatus(void)
0x1801394ee  nop
0x1801394ef  lea     rdx, qword_1802665D0
0x1801394f6  lea     rcx, [rbp+220h+var_40]
0x1801394fd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180139502  lea     rcx, [rbp+220h+var_160]
0x180139509  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013950e  mov     rdx, rax
0x180139511  lea     r8, [rsp+320h+pvarg]
0x180139516  lea     rcx, [rsp+320h+var_2F0]
0x18013951b  call    ?QueryCspNodeValue@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAJAEAV?$ComPtr@UIConfigManager2@@@WRL@5@PEBGAEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::QueryCspNodeValue(Microsoft::WRL::ComPtr<IConfigManager2> &,ushort const *,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &)
0x180139520  mov     esi, eax
0x180139522  test    eax, eax
0x180139524  js      loc_180139924
0x18013952a  cmp     word ptr [rsp+320h+pvarg], 3
0x180139530  jnz     loc_18013961D
0x180139536  mov     ecx, dword ptr [rsp+320h+pvarg+8]
0x18013953a  test    ecx, ecx
0x18013953c  jz      loc_18013960A
0x180139542  sub     ecx, 1
0x180139545  jz      loc_180139601
0x18013954b  sub     ecx, 1
0x18013954e  jz      loc_1801395F8
0x180139554  cmp     ecx, 1
0x180139557  jz      loc_1801395EF
0x18013955d  lea     rcx, [rbp+220h+var_2A0]
0x180139561  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180139566  nop
0x180139567  lea     rdx, aUnrecognizedSt; "Unrecognized status received for "
0x18013956e  lea     rcx, [rbp+220h+var_290]
0x180139572  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180139577  mov     rsi, rax
0x18013957a  lea     rcx, [rbp+220h+var_160]
0x180139581  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180139586  mov     rdx, rax
0x180139589  mov     rcx, rsi
0x18013958c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180139591  lea     rdx, aStatus_0; ". Status: "
0x180139598  lea     rcx, [rbp+220h+var_290]
0x18013959c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1801395a1  mov     edx, dword ptr [rsp+320h+pvarg+8]
0x1801395a5  mov     rcx, rax
0x1801395a8  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z; std::basic_ostream<ushort>::operator<<(long)
0x1801395ae  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x1801395b3  mov     rsi, rax
0x1801395b6  lea     rdx, [rbp+220h+var_120]
0x1801395bd  lea     rcx, [rbp+220h+var_288]
0x1801395c1  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x1801395c6  nop
0x1801395c7  lea     rdx, [rbp+220h+var_120]
0x1801395ce  mov     rcx, rsi
0x1801395d1  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(std::wstring const &)
0x1801395d6  nop
0x1801395d7  lea     rcx, [rbp+220h+var_120]
0x1801395de  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801395e3  nop
0x1801395e4  lea     rcx, [rbp+220h+var_2A0]
0x1801395e8  call    ??_D?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
0x1801395ed  jmp     short loc_18013961D
0x1801395ef  lea     rdx, aInstalled; "Installed"
0x1801395f6  jmp     short loc_180139611
0x1801395f8  lea     rdx, aFailed_0; "Failed"
0x1801395ff  jmp     short loc_180139611
0x180139601  lea     rdx, aInstalling; "Installing"
0x180139608  jmp     short loc_180139611
0x18013960a  lea     rdx, aNotInstalled; "Not Installed"
0x180139611  lea     rcx, [rbp+220h+var_1A0]
0x180139618  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18013961d  cmp     [rbp+220h+var_190], 0
0x180139625  jz      loc_1801398C4
0x18013962b  lea     rdx, aFailed_0; "Failed"
0x180139632  lea     rcx, [rbp+220h+var_1A0]
0x180139639  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x18013963e  test    eax, eax
0x180139640  jnz     short loc_1801396AF
0x180139642  lea     rcx, [rbp+220h+var_140]
0x180139649  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013964e  mov     rdx, rax
0x180139651  lea     r8, [rsp+320h+var_2C0]
0x180139656  lea     rcx, [rsp+320h+var_2F0]
0x18013965b  call    ?QueryCspNodeValue@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAJAEAV?$ComPtr@UIConfigManager2@@@WRL@5@PEBGAEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::QueryCspNodeValue(Microsoft::WRL::ComPtr<IConfigManager2> &,ushort const *,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &)
0x180139660  test    eax, eax
0x180139662  jns     short loc_18013967C
0x180139664  lea     rdx, qword_1802665B0
0x18013966b  lea     rcx, [rbp+220h+var_40]
0x180139672  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180139677  jmp     loc_1801398C4
0x18013967c  cmp     word ptr [rsp+320h+var_2C0], 3
0x180139682  jnz     short loc_1801396AF
0x180139684  mov     edx, dword ptr [rsp+320h+var_2C0+8]
0x180139688  lea     rcx, [rbp+220h+var_C0]
0x18013968f  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@J@Z; std::to_wstring(long)
0x180139694  mov     rdx, rax
0x180139697  lea     rcx, [rbp+220h+var_40]
0x18013969e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801396a3  lea     rcx, [rbp+220h+var_C0]
0x1801396aa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801396af  lea     rdx, [rbp+220h+var_1A0]
0x1801396b6  lea     rcx, [rbp+220h+var_60]
0x1801396bd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1801396c2  lea     rdx, aEnterprisemode; "/EnterpriseModernAppManagement/"
0x1801396c9  lea     rcx, [rbp+220h+var_E0]
0x1801396d0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801396d5  nop
0x1801396d6  xor     r8d, r8d
0x1801396d9  lea     rdx, [rbp+220h+var_E0]
0x1801396e0  lea     rcx, [rbp+220h+var_180]
0x1801396e7  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x1801396ec  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801396f0  jz      loc_1801398B7
0x1801396f6  mov     r9, [rbp+220h+var_D0]
0x1801396fd  add     r9, rax
0x180139700  xor     r8d, r8d
0x180139703  lea     rdx, [rbp+220h+var_A0]
0x18013970a  lea     rcx, [rbp+220h+var_180]
0x180139711  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180139716  nop
0x180139717  lea     rdx, aAppmanagement; "AppManagement"
0x18013971e  lea     rcx, [rbp+220h+var_A0]
0x180139725  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18013972a  lea     rcx, [rbp+220h+var_100]
0x180139731  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180139736  nop
0x180139737  lea     r9, [rbp+220h+var_100]
0x18013973e  lea     r8, [rbp+220h+var_A0]
0x180139745  lea     rdx, [rsp+320h+var_2F0]
0x18013974a  call    ?GetModernAppName@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJAEAV?$ComPtr@UIConfigManager2@@@WRL@5@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::GetModernAppName(Microsoft::WRL::ComPtr<IConfigManager2> &,std::wstring &,std::wstring &)
0x18013974f  test    eax, eax
0x180139751  js      loc_18013989D
0x180139757  cmp     [rbp+220h+var_F0], 0
0x18013975f  jnz     loc_18013987A
0x180139765  mov     edx, 2Fh ; '/'
0x18013976a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18013976e  lea     rcx, [rbp+220h+var_180]
0x180139775  call    ?rfind@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::rfind(ushort,unsigned __int64)
0x18013977a  mov     rsi, rax
0x18013977d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180139781  jz      loc_18013989D
0x180139787  lea     rcx, [rbp+220h+var_120]
0x18013978e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180139793  nop
0x180139794  lea     r8, [rsi+1]
0x180139798  or      r9, 0FFFFFFFFFFFFFFFFh
0x18013979c  lea     rdx, [rbp+220h+var_C0]
0x1801397a3  lea     rcx, [rbp+220h+var_180]
0x1801397aa  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1801397af  mov     rcx, rax
0x1801397b2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801397b7  lea     rdx, [rbp+220h+var_120]
0x1801397be  mov     rcx, rax; pszUrl
0x1801397c1  call    ?UrlUnEscapeWrapper@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; UrlUnEscapeWrapper(ushort const *,std::wstring &)
0x1801397c6  mov     esi, eax
0x1801397c8  shr     esi, 1Fh
0x1801397cb  lea     rcx, [rbp+220h+var_C0]
0x1801397d2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801397d7  test    sil, sil
0x1801397da  jnz     loc_18013986C
0x1801397e0  lea     rcx, [rbp+220h+var_2A0]
0x1801397e4  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x1801397e9  nop
0x1801397ea  lea     rdx, aModernApp; "Modern App("
0x1801397f1  lea     rcx, [rbp+220h+var_290]
0x1801397f5  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1801397fa  mov     rsi, rax
0x1801397fd  lea     rcx, [rbp+220h+var_120]
0x180139804  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180139809  mov     rdx, rax
0x18013980c  mov     rcx, rsi
0x18013980f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180139814  mov     rcx, rax
0x180139817  lea     rdx, asc_1801EC8F0; ")"
0x18013981e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180139823  lea     rdx, [rbp+220h+var_C0]
0x18013982a  lea     rcx, [rbp+220h+var_288]
0x18013982e  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x180139833  lea     rdx, [rbp+220h+var_C0]
0x18013983a  lea     rcx, [rbp+220h+var_80]
0x180139841  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180139846  lea     rcx, [rbp+220h+var_C0]
0x18013984d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180139852  lea     rdx, [rbp+220h+var_80]
0x180139859  mov     rcx, r14
0x18013985c  call    ??$emplace_back@AEAUAppStatus@@@?$vector@UAppStatus@@V?$allocator@UAppStatus@@@std@@@std@@QEAAAEAUAppStatus@@AEAU2@@Z; std::vector<AppStatus>::emplace_back<AppStatus &>(AppStatus &)
0x180139861  nop
0x180139862  lea     rcx, [rbp+220h+var_2A0]
0x180139866  call    ??_D?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
0x18013986b  nop
0x18013986c  lea     rcx, [rbp+220h+var_120]
0x180139873  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180139878  jmp     short loc_18013989D
0x18013987a  lea     rdx, [rbp+220h+var_100]
0x180139881  lea     rcx, [rbp+220h+var_80]
0x180139888  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18013988d  lea     rdx, [rbp+220h+var_80]
0x180139894  mov     rcx, r14
0x180139897  call    ??$emplace_back@AEAUAppStatus@@@?$vector@UAppStatus@@V?$allocator@UAppStatus@@@std@@@std@@QEAAAEAUAppStatus@@AEAU2@@Z; std::vector<AppStatus>::emplace_back<AppStatus &>(AppStatus &)
0x18013989c  nop
0x18013989d  lea     rcx, [rbp+220h+var_100]
0x1801398a4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801398a9  nop
0x1801398aa  lea     rcx, [rbp+220h+var_A0]
0x1801398b1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801398b6  nop
0x1801398b7  lea     rcx, [rbp+220h+var_E0]
0x1801398be  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801398c3  nop
0x1801398c4  lea     rcx, [rbp+220h+var_80]; this
0x1801398cb  call    ??1AppStatus@@QEAA@XZ; AppStatus::~AppStatus(void)
0x1801398d0  nop
0x1801398d1  lea     rcx, [rbp+220h+var_140]
0x1801398d8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801398dd  nop
0x1801398de  lea     rcx, [rsp+320h+var_2C0]; pvarg
0x1801398e3  call    cs:__imp_VariantClear
0x1801398e9  nop
0x1801398ea  lea     rcx, [rbp+220h+var_160]
0x1801398f1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801398f6  nop
0x1801398f7  lea     rcx, [rsp+320h+pvarg]; pvarg
0x1801398fc  call    cs:__imp_VariantClear
0x180139902  nop
0x180139903  lea     rcx, [rbp+220h+var_1A0]
0x18013990a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013990f  nop
0x180139910  lea     rcx, [rbp+220h+var_180]
0x180139917  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013991c  mov     rbx, [rbx]
0x18013991f  jmp     loc_18013946D
0x180139924  mov     rcx, [rbp+228h]; this
0x18013992b  mov     r9d, esi; char *
0x18013992e  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180139935  mov     edx, 263h; void *
0x18013993a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013993f  nop
0x180139940  lea     rcx, [rbp+220h+var_80]; this
0x180139947  call    ??1AppStatus@@QEAA@XZ; AppStatus::~AppStatus(void)
  ... truncated ...
```
