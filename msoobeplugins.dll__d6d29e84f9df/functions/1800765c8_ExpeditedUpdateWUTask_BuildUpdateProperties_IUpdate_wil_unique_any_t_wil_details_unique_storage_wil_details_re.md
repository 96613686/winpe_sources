# ExpeditedUpdateWUTask::_BuildUpdateProperties(IUpdate *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)

- ea: `0x1800765c8`
- end: `0x180076be1`
- name: `?_BuildUpdateProperties@ExpeditedUpdateWUTask@@AEAAJPEAUIUpdate@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `1561`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180074930`

## callees

- `0x180003470`
- `0x180008544`
- `0x18001ad08`
- `0x1800230b0`
- `0x18002f39c`
- `0x180040918`
- `0x1800418d8`
- `0x180042068`
- `0x180043c58`
- `0x1800765c8`
- `0x180076be8`
- `0x180077cdc`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180076716`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180076716`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007667f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007667f`
- `OLEAUT32!__imp_SysStringLen` at `0x180076706`
- `OLEAUT32!__imp_SysStringLen` at `0x180076706`

## string_xrefs

- `0x18007660e`: `Windows.Data.Json.JsonObject`
- `0x180076660`: `Windows.Data.Json.JsonValue`
- `0x180076639`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180076692`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x1800766d6`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180076729`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180076771`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x1800767cb`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x1800767a4`: `UpdateTitle`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall ExpeditedUpdateWUTask::_BuildUpdateProperties(
        __int64 a1,
        __int64 (__fastcall ***a2)(__int64, GUID *, __int64 **),
        __int64 a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  int ActivationFactory; // eax
  int v8; // eax
  UINT v9; // eax
  HRESULT v10; // eax
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rsi
  __int64 (__fastcall *v14)(__int64, __int64, __int64); // rdi
  __int64 v15; // rbx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 *v20; // rbx
  __int64 (__fastcall *v21)(__int64 *, __int64, __int64 *); // rdi
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rsi
  __int64 (__fastcall *v25)(__int64, __int64, __int64); // rdi
  __int64 v26; // rbx
  int v27; // eax
  __int64 v28; // rdx
  __int64 *v29; // rbx
  __int64 (__fastcall *v30)(__int64 *, __int64, __int64 *); // rdi
  __int64 v31; // rcx
  int v32; // eax
  __int64 v33; // rsi
  __int64 (__fastcall *v34)(__int64, __int64, __int64); // rdi
  __int64 v35; // rbx
  int v36; // eax
  __int64 (__fastcall **v37)(__int64, GUID *, __int64 **); // rax
  int v38; // eax
  __int64 v39; // rax
  int v40; // eax
  __int64 v41; // rcx
  __int64 v42; // rsi
  __int64 (__fastcall *v43)(__int64, __int64, __int64); // rdi
  __int64 v44; // rbx
  int v45; // eax
  __int64 *v46; // rcx
  int v47; // eax
  int v48; // eax
  __int64 v49; // rdx
  __int64 v50; // rdi
  __int64 (__fastcall *v51)(__int64, __int64); // rbx
  __int64 v53; // [rsp+20h] [rbp-59h] BYREF
  __int64 *v54; // [rsp+28h] [rbp-51h] BYREF
  BSTR pbstr; // [rsp+30h] [rbp-49h] BYREF
  HSTRING string; // [rsp+38h] [rbp-41h] BYREF
  __int64 v57; // [rsp+40h] [rbp-39h] BYREF
  __int64 v58; // [rsp+48h] [rbp-31h] BYREF
  __int64 *v59; // [rsp+50h] [rbp-29h] BYREF
  int v60; // [rsp+58h] [rbp-21h] BYREF
  int v61; // [rsp+5Ch] [rbp-1Dh] BYREF
  __int64 v62; // [rsp+60h] [rbp-19h] BYREF
  __int64 *v63; // [rsp+68h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-9h] BYREF
  __int64 v65; // [rsp+88h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v57 = 0;
  v65 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v5 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v65, &v57);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v54 = 0;
    v65 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonValue",
      0x1Cu,
      0x1Bu);
    ActivationFactory = RoGetActivationFactory(v65, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v54);
    v6 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41D,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v53);
LABEL_5:
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v54);
      goto LABEL_53;
    }
    pbstr = 0;
    v8 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 **), BSTR *))(*a2)[7])(a2, &pbstr);
    v6 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x426,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
        (const char *)(unsigned int)v8,
        v53);
LABEL_8:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pbstr);
      goto LABEL_5;
    }
    string = 0;
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &string,
      0);
    v9 = SysStringLen(pbstr);
    v10 = WindowsCreateString(pbstr, v9, &string);
    v6 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x428,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
        (const char *)(unsigned int)v10,
        v53);
LABEL_11:
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      goto LABEL_8;
    }
    v53 = 0;
    v11 = *v54;
    v53 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v11 + 80))(v54, string, &v53);
    if ( v12 >= 0 )
    {
      v13 = v57;
      v14 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v57 + 56LL);
      v15 = v53;
      v65 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UpdateTitle", 0xCu, 0xBu);
      v16 = v14(v13, v65, v15);
      if ( v16 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x42C,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
          (const char *)(unsigned int)v16,
          v53);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x42A,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
        (const char *)(unsigned int)v12,
        v53);
    }
    v60 = 0;
    v17 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 **), int *))(*a2)[48])(a2, &v60);
    v6 = v17;
    if ( v17 >= 0 )
    {
      v20 = v54;
      v21 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(*v54 + 72);
      v22 = v53;
      v53 = 0;
      if ( v22 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      v23 = v21(v20, v18, &v53);
      if ( v23 >= 0 )
      {
        v24 = v57;
        v25 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v57 + 56LL);
        v26 = v53;
        v65 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"DeploymentAction", 0x11u, 0x10u);
        v27 = v25(v24, v65, v26);
        if ( v27 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x433,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
            (const char *)(unsigned int)v27,
            v53);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x431,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
          (const char *)(unsigned int)v23,
          v53);
      }
      v61 = 0;
      v17 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 **), int *))(*a2)[50])(a2, &v61);
      v6 = v17;
      if ( v17 >= 0 )
      {
        v29 = v54;
        v30 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(*v54 + 72);
        v31 = v53;
        v53 = 0;
        if ( v31 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        v32 = v30(v29, v28, &v53);
        if ( v32 >= 0 )
        {
          v33 = v57;
          v34 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v57 + 56LL);
          v35 = v53;
          v65 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"DownloadPriority", 0x11u, 0x10u);
          v36 = v34(v33, v65, v35);
          if ( v36 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x43A,
              (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
              (const char *)(unsigned int)v36,
              v53);
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x438,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
            (const char *)(unsigned int)v32,
            v53);
        }
        v37 = *a2;
        v59 = 0;
        v38 = (*v37)((__int64)a2, &GUID_59d344a2_d3b4_49d5_9486_31462e1974c9, &v59);
        v6 = v38;
        if ( v38 >= 0 )
        {
          v58 = 0;
          v39 = *v59;
          v58 = 0;
          v40 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64 *))(v39 + 104))(v59, L"Audience", &v58);
          v6 = v40;
          if ( v40 >= 0 )
          {
            if ( (int)ExpeditedUpdateWUTask::_ParseStringToJson(v41, &v58, &v53) >= 0 )
            {
              v42 = v57;
              v43 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v57 + 56LL);
              v44 = v53;
              v65 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ClientMetadata", 0xFu, 0xEu);
              v45 = v43(v42, v65, v44);
              if ( v45 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x444,
                  (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
                  (const char *)(unsigned int)v45,
                  v53);
            }
            v46 = v54;
            v63 = v54;
            if ( v54 )
              (*(void (__fastcall **)(__int64 *))(*v54 + 8))(v54);
            v47 = ExpeditedUpdateWUTask::_BuildingInternalProperties(v46, a2, &v63, &v57);
            if ( v47 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x447,
                (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
                (const char *)(unsigned int)v47,
                v53);
            v62 = 0;
            v48 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v57)(
                    v57,
                    &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e,
                    &v62);
            v6 = v48;
            if ( v48 >= 0 )
            {
              v50 = v62;
              v51 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v62 + 56LL);
              wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
                a3,
                0);
              v48 = v51(v50, a3);
              v6 = v48;
              if ( v48 >= 0 )
              {
                wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v62);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v58);
                wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v59);
                wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v53);
                Windows::Internal::String::~String((Windows::Internal::String *)&string);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pbstr);
                wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v54);
                v6 = 0;
                goto LABEL_53;
              }
              v49 = 1099;
            }
            else
            {
              v49 = 1098;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v49,
              (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
              (const char *)(unsigned int)v48,
              v53);
            wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v62);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x441,
              (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
              (const char *)(unsigned int)v40,
              v53);
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v58);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x43E,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
            (const char *)(unsigned int)v38,
            v53);
        }
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v59);
        goto LABEL_19;
      }
      v19 = 1079;
    }
    else
    {
      v19 = 1072;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
      (const char *)(unsigned int)v17,
      v53);
LABEL_19:
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v53);
    goto LABEL_11;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x41B,
    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
    (const char *)(unsigned int)v5,
    v53);
LABEL_53:
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v57);
  return v6;
}

```

## disassembly

```asm
0x1800765c8  mov     [rsp-8+arg_0], rbx
0x1800765cd  push    rbp
0x1800765ce  push    rsi
0x1800765cf  push    rdi
0x1800765d0  push    r12
0x1800765d2  push    r13
0x1800765d4  push    r14
0x1800765d6  push    r15
0x1800765d8  lea     rbp, [rsp-27h]
0x1800765dd  sub     rsp, 0A0h
0x1800765e4  mov     rax, cs:__security_cookie
0x1800765eb  xor     rax, rsp
0x1800765ee  mov     [rbp+57h+var_40], rax
0x1800765f2  mov     r12, r8
0x1800765f5  mov     r15, rdx
0x1800765f8  xor     r13d, r13d
0x1800765fb  mov     [rbp+57h+var_90], r13
0x1800765ff  mov     [rbp+57h+var_48], r13
0x180076603  lea     edi, [r13+1Ch]
0x180076607  mov     r9d, edi; unsigned int
0x18007660a  lea     r8d, [r13+1Dh]; unsigned int
0x18007660e  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180076615  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180076619  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007661e  nop
0x18007661f  lea     rdx, [rbp+57h+var_90]
0x180076623  mov     rcx, [rbp+57h+var_48]
0x180076627  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x18007662c  mov     ebx, eax
0x18007662e  test    eax, eax
0x180076630  jns     short loc_18007664F
0x180076632  mov     rcx, [rbp+5Fh]; this
0x180076636  mov     r9d, eax; char *
0x180076639  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180076640  mov     edx, 41Bh; void *
0x180076645  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007664a  jmp     loc_180076BAF
0x18007664f  mov     [rbp+57h+var_A8], r13
0x180076653  mov     [rbp+57h+var_48], r13
0x180076657  mov     r9d, 1Bh; unsigned int
0x18007665d  mov     r8d, edi; unsigned int
0x180076660  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180076667  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18007666b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180076670  lea     r8, [rbp+57h+var_A8]
0x180076674  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18007667b  mov     rcx, [rbp+57h+var_48]
0x18007667f  call    cs:__imp_RoGetActivationFactory
0x180076685  mov     ebx, eax
0x180076687  test    eax, eax
0x180076689  jns     short loc_1800766B2
0x18007668b  mov     rcx, [rbp+5Fh]; this
0x18007668f  mov     r9d, eax; char *
0x180076692  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180076699  mov     edx, 41Dh; void *
0x18007669e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800766a3  nop
0x1800766a4  lea     rcx, [rbp+57h+var_A8]
0x1800766a8  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800766ad  jmp     loc_180076BAF
0x1800766b2  mov     [rbp+57h+pbstr], r13
0x1800766b6  mov     rax, [r15]
0x1800766b9  lea     rdx, [rbp+57h+pbstr]
0x1800766bd  mov     rcx, r15
0x1800766c0  mov     rax, [rax+38h]
0x1800766c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800766c9  mov     ebx, eax
0x1800766cb  test    eax, eax
0x1800766cd  jns     short loc_1800766F3
0x1800766cf  mov     rcx, [rbp+5Fh]; this
0x1800766d3  mov     r9d, eax; char *
0x1800766d6  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x1800766dd  mov     edx, 426h; void *
0x1800766e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800766e7  nop
0x1800766e8  lea     rcx, [rbp+57h+pbstr]
0x1800766ec  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800766f1  jmp     short loc_1800766A4
0x1800766f3  mov     [rbp+57h+string], r13
0x1800766f7  xor     edx, edx
0x1800766f9  lea     rcx, [rbp+57h+string]
0x1800766fd  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180076702  mov     rcx, [rbp+57h+pbstr]; pbstr
0x180076706  call    cs:__imp_SysStringLen
0x18007670c  lea     r8, [rbp+57h+string]; string
0x180076710  mov     edx, eax; length
0x180076712  mov     rcx, [rbp+57h+pbstr]; sourceString
0x180076716  call    cs:__imp_WindowsCreateString
0x18007671c  mov     ebx, eax
0x18007671e  test    eax, eax
0x180076720  jns     short loc_180076746
0x180076722  mov     rcx, [rbp+5Fh]; this
0x180076726  mov     r9d, eax; char *
0x180076729  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180076730  mov     edx, 428h; void *
0x180076735  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007673a  nop
0x18007673b  lea     rcx, [rbp+57h+string]; this
0x18007673f  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180076744  jmp     short loc_1800766E8
0x180076746  mov     [rbp+57h+var_B0], r13
0x18007674a  mov     rcx, [rbp+57h+var_A8]
0x18007674e  mov     rax, [rcx]
0x180076751  mov     [rbp+57h+var_B0], r13
0x180076755  lea     r8, [rbp+57h+var_B0]
0x180076759  mov     rdx, [rbp+57h+string]
0x18007675d  mov     rax, [rax+50h]
0x180076761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076766  mov     rcx, [rbp+5Fh]; this
0x18007676a  test    eax, eax
0x18007676c  jns     short loc_180076787
0x18007676e  mov     r9d, eax; char *
0x180076771  lea     r14, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180076778  mov     r8, r14; unsigned int
0x18007677b  mov     edx, 42Ah; void *
0x180076780  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180076785  jmp     short loc_1800767E7
0x180076787  mov     rsi, [rbp+57h+var_90]
0x18007678b  mov     rax, [rsi]
0x18007678e  mov     rdi, [rax+38h]
0x180076792  mov     rbx, [rbp+57h+var_B0]
0x180076796  mov     [rbp+57h+var_48], r13
0x18007679a  mov     r9d, 0Bh; unsigned int
0x1800767a0  lea     r8d, [r9+1]; unsigned int
0x1800767a4  lea     rdx, aUpdatetitle; "UpdateTitle"
0x1800767ab  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800767af  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800767b4  nop
0x1800767b5  mov     r8, rbx
0x1800767b8  mov     rdx, [rbp+57h+var_48]
0x1800767bc  mov     rcx, rsi
0x1800767bf  mov     rax, rdi
0x1800767c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800767c7  mov     rcx, [rbp+5Fh]; this
0x1800767cb  lea     r14, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x1800767d2  test    eax, eax
0x1800767d4  jns     short loc_1800767E7
0x1800767d6  mov     r9d, eax; char *
0x1800767d9  mov     r8, r14; unsigned int
0x1800767dc  mov     edx, 42Ch; void *
0x1800767e1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800767e6  nop
0x1800767e7  mov     [rbp+57h+var_78], r13d
0x1800767eb  mov     rax, [r15]
0x1800767ee  lea     rdx, [rbp+57h+var_78]
0x1800767f2  mov     rcx, r15
0x1800767f5  mov     rax, [rax+180h]
0x1800767fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076801  mov     ebx, eax
0x180076803  test    eax, eax
0x180076805  jns     short loc_18007682A
0x180076807  mov     edx, 430h; void *
0x18007680c  mov     r8, r14; unsigned int
0x18007680f  mov     r9d, eax; char *
0x180076812  mov     rcx, [rbp+5Fh]; this
0x180076816  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007681b  nop
0x18007681c  lea     rcx, [rbp+57h+var_B0]
0x180076820  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180076825  jmp     loc_18007673B
0x18007682a  mov     rbx, [rbp+57h+var_A8]
0x18007682e  mov     rax, [rbx]
0x180076831  mov     rdi, [rax+48h]
0x180076835  mov     rcx, [rbp+57h+var_B0]
0x180076839  mov     [rbp+57h+var_B0], r13
0x18007683d  test    rcx, rcx
0x180076840  jz      short loc_18007684F
0x180076842  mov     rdx, [rcx]
0x180076845  mov     rax, [rdx+10h]
0x180076849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007684e  nop
0x18007684f  movd    xmm1, [rbp+57h+var_78]
0x180076854  cvtdq2pd xmm1, xmm1
0x180076858  lea     r8, [rbp+57h+var_B0]
0x18007685c  mov     rcx, rbx
0x18007685f  mov     rax, rdi
0x180076862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076867  mov     rcx, [rbp+5Fh]; this
0x18007686b  test    eax, eax
0x18007686d  jns     short loc_180076881
0x18007686f  mov     r9d, eax; char *
0x180076872  mov     r8, r14; unsigned int
0x180076875  mov     edx, 431h; void *
0x18007687a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007687f  jmp     short loc_1800768DA
0x180076881  mov     rsi, [rbp+57h+var_90]
0x180076885  mov     rax, [rsi]
0x180076888  mov     rdi, [rax+38h]
0x18007688c  mov     rbx, [rbp+57h+var_B0]
0x180076890  mov     [rbp+57h+var_48], r13
0x180076894  mov     r9d, 10h; unsigned int
0x18007689a  lea     r8d, [r9+1]; unsigned int
0x18007689e  lea     rdx, aDeploymentacti; "DeploymentAction"
0x1800768a5  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800768a9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800768ae  nop
0x1800768af  mov     r8, rbx
0x1800768b2  mov     rdx, [rbp+57h+var_48]
0x1800768b6  mov     rcx, rsi
0x1800768b9  mov     rax, rdi
0x1800768bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800768c1  mov     rcx, [rbp+5Fh]; this
0x1800768c5  test    eax, eax
0x1800768c7  jns     short loc_1800768DA
0x1800768c9  mov     r9d, eax; char *
0x1800768cc  mov     r8, r14; unsigned int
0x1800768cf  mov     edx, 433h; void *
0x1800768d4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800768d9  nop
0x1800768da  mov     [rbp+57h+var_74], r13d
0x1800768de  mov     rax, [r15]
0x1800768e1  lea     rdx, [rbp+57h+var_74]
0x1800768e5  mov     rcx, r15
0x1800768e8  mov     rax, [rax+190h]
0x1800768ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800768f4  mov     ebx, eax
0x1800768f6  test    eax, eax
0x1800768f8  jns     short loc_180076904
0x1800768fa  mov     edx, 437h
0x1800768ff  jmp     loc_18007680C
0x180076904  mov     rbx, [rbp+57h+var_A8]
0x180076908  mov     rax, [rbx]
0x18007690b  mov     rdi, [rax+48h]
0x18007690f  mov     rcx, [rbp+57h+var_B0]
0x180076913  mov     [rbp+57h+var_B0], r13
0x180076917  test    rcx, rcx
0x18007691a  jz      short loc_180076929
0x18007691c  mov     rdx, [rcx]
0x18007691f  mov     rax, [rdx+10h]
0x180076923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076928  nop
0x180076929  movd    xmm1, [rbp+57h+var_74]
0x18007692e  cvtdq2pd xmm1, xmm1
0x180076932  lea     r8, [rbp+57h+var_B0]
0x180076936  mov     rcx, rbx
0x180076939  mov     rax, rdi
0x18007693c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076941  mov     rcx, [rbp+5Fh]; this
0x180076945  test    eax, eax
0x180076947  jns     short loc_18007695B
0x180076949  mov     r9d, eax; char *
0x18007694c  mov     r8, r14; unsigned int
0x18007694f  mov     edx, 438h; void *
0x180076954  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180076959  jmp     short loc_1800769B4
0x18007695b  mov     rsi, [rbp+57h+var_90]
0x18007695f  mov     rax, [rsi]
0x180076962  mov     rdi, [rax+38h]
0x180076966  mov     rbx, [rbp+57h+var_B0]
0x18007696a  mov     [rbp+57h+var_48], r13
0x18007696e  mov     r9d, 10h; unsigned int
0x180076974  lea     r8d, [r9+1]; unsigned int
0x180076978  lea     rdx, aDownloadpriori; "DownloadPriority"
0x18007697f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180076983  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180076988  nop
0x180076989  mov     r8, rbx
0x18007698c  mov     rdx, [rbp+57h+var_48]
0x180076990  mov     rcx, rsi
0x180076993  mov     rax, rdi
0x180076996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007699b  mov     rcx, [rbp+5Fh]; this
0x18007699f  test    eax, eax
0x1800769a1  jns     short loc_1800769B4
0x1800769a3  mov     r9d, eax; char *
0x1800769a6  mov     r8, r14; unsigned int
0x1800769a9  mov     edx, 43Ah; void *
0x1800769ae  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800769b3  nop
0x1800769b4  mov     rax, [r15]
0x1800769b7  mov     [rbp+57h+var_80], r13
0x1800769bb  lea     r8, [rbp+57h+var_80]
0x1800769bf  lea     rdx, _GUID_59d344a2_d3b4_49d5_9486_31462e1974c9
0x1800769c6  mov     rcx, r15
0x1800769c9  mov     rax, [rax]
0x1800769cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800769d1  mov     ebx, eax
0x1800769d3  test    eax, eax
0x1800769d5  jns     short loc_1800769FA
0x1800769d7  mov     rcx, [rbp+5Fh]; this
0x1800769db  mov     r9d, eax; char *
0x1800769de  mov     r8, r14; unsigned int
0x1800769e1  mov     edx, 43Eh; void *
0x1800769e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800769eb  nop
0x1800769ec  lea     rcx, [rbp+57h+var_80]
0x1800769f0  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800769f5  jmp     loc_18007681C
0x1800769fa  mov     [rbp+57h+var_88], r13
0x1800769fe  mov     rcx, [rbp+57h+var_80]
0x180076a02  mov     rax, [rcx]
0x180076a05  mov     [rbp+57h+var_88], r13
0x180076a09  lea     r8, [rbp+57h+var_88]
0x180076a0d  lea     rdx, aAudience; "Audience"
0x180076a14  mov     rax, [rax+68h]
0x180076a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076a1d  mov     ebx, eax
0x180076a1f  test    eax, eax
0x180076a21  jns     short loc_180076A43
0x180076a23  mov     rcx, [rbp+5Fh]; this
  ... truncated ...
```
