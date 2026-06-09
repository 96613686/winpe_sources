# ExpeditedUpdateUSOTask::GetUpdatesList(Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *> * *)

- ea: `0x180079ce0`
- end: `0x18007a10d`
- name: `?GetUpdatesList@ExpeditedUpdateUSOTask@@UEAAJPEAPEAU?$IMap@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Z`
- size: `1069`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800068f4`
- `0x180006bb8`
- `0x180008544`
- `0x18001ad08`
- `0x1800230b0`
- `0x18002f39c`
- `0x1800418d8`
- `0x180043c58`
- `0x1800698e0`
- `0x180078004`
- `0x180079ce0`
- `0x18007b510`
- `0x18007ce48`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180079e29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180079f26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180079e29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180079f26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180079f49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180079f58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007a000`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180079f49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180079f58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007a000`
- `OLEAUT32!__imp_SysFreeString` at `0x180079ed4`
- `OLEAUT32!__imp_SysFreeString` at `0x180079ed4`
- `OLEAUT32!__imp_SysStringLen` at `0x180079e19`
- `OLEAUT32!__imp_SysStringLen` at `0x180079f16`
- `OLEAUT32!__imp_SysStringLen` at `0x180079e19`
- `OLEAUT32!__imp_SysStringLen` at `0x180079f16`

## string_xrefs

- `0x180079d1f`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x180079d67`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x180079fe9`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x18007a03c`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x18007a065`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x18007a089`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x18007a0ad`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x180079f64`: `ExpeditedUpdateUSOTask GetUpdatesList ID [%s], Properties [%s]`
- `0x180079cff`: `ExpeditedUpdateUSOTask collecting updates list`
- `0x18007a00c`: `ExpeditedUpdateUSOTask Failed to build update properties for ID [%s], failed HResult code [hr=0x%08X]`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall ExpeditedUpdateUSOTask::GetUpdatesList(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  unsigned int v6; // ebx
  int v7; // eax
  __int64 (__fastcall ***v8)(__int64, GUID *, __int64 **); // rcx
  unsigned int v9; // esi
  __int64 v10; // r13
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64, _QWORD, _QWORD); // r15
  int v13; // eax
  __int64 (__fastcall **v14)(__int64, GUID *, __int64 **); // rax
  int v15; // eax
  UINT v16; // eax
  HRESULT v17; // eax
  __int64 (__fastcall ***v18)(__int64, GUID *, __int64 **); // rbx
  __int64 (__fastcall *v19)(_QWORD, GUID *, __int64 *); // r15
  __int64 v20; // rcx
  HRESULT v21; // eax
  __int64 v22; // r15
  __int64 (__fastcall *v23)(__int64, BSTR *); // r13
  OLECHAR *v24; // rbx
  UINT v25; // eax
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v27; // rax
  int updated; // eax
  unsigned int v29; // ebx
  PCWSTR v30; // rax
  __int64 v31; // rdx
  int v33; // [rsp+20h] [rbp-50h]
  __int64 v34; // [rsp+30h] [rbp-40h] BYREF
  HSTRING v35; // [rsp+38h] [rbp-38h] BYREF
  BSTR pbstr; // [rsp+40h] [rbp-30h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-28h] BYREF
  __int64 v38; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v39[8]; // [rsp+58h] [rbp-18h] BYREF
  __int64 v40; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  char v42; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v43; // [rsp+B8h] [rbp+48h] BYREF
  __int64 (__fastcall ***v44)(__int64, GUID *, __int64 **); // [rsp+C0h] [rbp+50h] BYREF
  HSTRING string; // [rsp+C8h] [rbp+58h] BYREF

  *a2 = 0;
  UnattendLogW(0, L"ExpeditedUpdateUSOTask collecting updates list");
  if ( !*(_QWORD *)(a1 + 104) )
  {
    v6 = -2147023728;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x144,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
      (const char *)0x80070490LL,
      v33);
    return v6;
  }
  v38 = 0;
  Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Make(
    v5,
    v4,
    &v38);
  v43 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(a1 + 104) + 32LL))(*(_QWORD *)(a1 + 104), &v43);
  v6 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14B,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
      (const char *)(unsigned int)v7,
      v33);
    goto LABEL_37;
  }
  v8 = 0;
  v44 = 0;
  v34 = 0;
  v9 = 0;
  v10 = v38;
  v40 = v38;
  if ( !v43 )
  {
LABEL_36:
    v38 = 0;
    *a2 = v10;
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v34);
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v44);
    v6 = 0;
    goto LABEL_37;
  }
  while ( 1 )
  {
    v11 = *(_QWORD *)(a1 + 104);
    v12 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v11 + 24LL);
    v44 = 0;
    if ( v8 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 **)))(*v8)[2])(v8);
    v13 = v12(v11, v9, &v44);
    v6 = v13;
    if ( v13 < 0 )
      break;
    pbstr = 0;
    v14 = *v44;
    pbstr = 0;
    v15 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 **), BSTR *))v14[14])(v44, &pbstr);
    v6 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x155,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
        (const char *)(unsigned int)v15,
        v33);
      goto LABEL_33;
    }
    string = 0;
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &string,
      0);
    v16 = SysStringLen(pbstr);
    v17 = WindowsCreateString(pbstr, v16, &string);
    v6 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x158,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
        (const char *)(unsigned int)v17,
        v33);
      goto LABEL_31;
    }
    v35 = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExpeditedUpdatePILess>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ExpeditedUpdatePILess>::GetImpl'::`2'::impl)
      && !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus>::GetImpl'::`2'::impl) )
    {
      bstrString = 0;
      v18 = v44;
      v19 = (__int64 (__fastcall *)(_QWORD, GUID *, __int64 *))**v44;
      v20 = v34;
      v34 = 0;
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      v21 = v19(v18, &GUID_094c3761_2220_471d_9830_3baa13cea544, &v34);
      v6 = v21;
      if ( v21 < 0 )
      {
        v31 = 360;
LABEL_29:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v31,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
          (const char *)(unsigned int)v21,
          v33);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrString);
        Windows::Internal::String::~String((Windows::Internal::String *)&v35);
LABEL_31:
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
LABEL_33:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pbstr);
        goto LABEL_35;
      }
      v22 = v34;
      v23 = *(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v34 + 328LL);
      v24 = bstrString;
      if ( bstrString )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v39);
        SysFreeString(v24);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v39);
      }
      bstrString = 0;
      v21 = v23(v22, &bstrString);
      v6 = v21;
      if ( v21 < 0 )
      {
        v31 = 361;
        goto LABEL_29;
      }
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &v35,
        0);
      v25 = SysStringLen(bstrString);
      v21 = WindowsCreateString(bstrString, v25, &v35);
      v6 = v21;
      if ( v21 < 0 )
      {
        v31 = 362;
        goto LABEL_29;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrString);
      v10 = v40;
LABEL_21:
      StringRawBuffer = WindowsGetStringRawBuffer(v35, 0);
      v27 = WindowsGetStringRawBuffer(string, 0);
      UnattendLogW(0, L"ExpeditedUpdateUSOTask GetUpdatesList ID [%s], Properties [%s]", v27, StringRawBuffer);
      v42 = 0;
      (*(void (__fastcall **)(__int64, HSTRING, HSTRING, char *))(*(_QWORD *)v10 + 80LL))(v10, string, v35, &v42);
      goto LABEL_22;
    }
    updated = ExpeditedUpdateUSOTask::_BuildUpdateProperties(a1 - 568, v44, (__int64)&v35);
    v29 = updated;
    if ( updated >= 0 )
      goto LABEL_21;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x15F,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
      (const char *)(unsigned int)updated,
      v33);
    v30 = WindowsGetStringRawBuffer(string, 0);
    UnattendLogW(
      1,
      L"ExpeditedUpdateUSOTask Failed to build update properties for ID [%s], failed HResult code [hr=0x%08X]",
      v30,
      v29);
LABEL_22:
    Windows::Internal::String::~String((Windows::Internal::String *)&v35);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pbstr);
    if ( ++v9 >= v43 )
      goto LABEL_36;
    v8 = v44;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x152,
    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
    (const char *)(unsigned int)v13,
    v33);
LABEL_35:
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v34);
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v44);
LABEL_37:
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v38);
  return v6;
}

```

## disassembly

```asm
0x180079ce0  push    rbp
0x180079ce2  push    rbx
0x180079ce3  push    rsi
0x180079ce4  push    r12
0x180079ce6  push    r13
0x180079ce8  push    r14
0x180079cea  push    r15
0x180079cec  mov     rbp, rsp
0x180079cef  sub     rsp, 70h
0x180079cf3  mov     r12, rdx
0x180079cf6  mov     r14, rcx
0x180079cf9  xor     r15d, r15d
0x180079cfc  mov     [rdx], r15
0x180079cff  lea     rdx, aExpeditedupdat_44; "ExpeditedUpdateUSOTask collecting updat"...
0x180079d06  xor     ecx, ecx
0x180079d08  call    UnattendLogW
0x180079d0d  cmp     [r14+68h], r15
0x180079d11  jnz     short loc_180079D35
0x180079d13  mov     rcx, [rbp+38h]; this
0x180079d17  mov     ebx, 80070490h
0x180079d1c  mov     r9d, ebx; char *
0x180079d1f  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x180079d26  mov     edx, 144h; void *
0x180079d2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079d30  jmp     loc_18007A0FB
0x180079d35  mov     [rbp+var_20], r15
0x180079d39  lea     r8, [rbp+var_20]
0x180079d3d  call    ?Make@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@SAJAEBU?$DefaultHash@PEAUHSTRING__@@@2345@AEBU?$DefaultEqualityPredicate@PEAUHSTRING__@@@2345@PEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Make(Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>> * *)
0x180079d42  mov     [rbp+arg_8], r15d
0x180079d46  mov     rcx, [r14+68h]
0x180079d4a  mov     rax, [rcx]
0x180079d4d  lea     rdx, [rbp+arg_8]
0x180079d51  mov     rax, [rax+20h]
0x180079d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079d5a  mov     ebx, eax
0x180079d5c  test    eax, eax
0x180079d5e  jns     short loc_180079D7D
0x180079d60  mov     rcx, [rbp+38h]; this
0x180079d64  mov     r9d, eax; char *
0x180079d67  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x180079d6e  mov     edx, 14Bh; void *
0x180079d73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079d78  jmp     loc_18007A0F2
0x180079d7d  mov     rcx, r15
0x180079d80  mov     [rbp+arg_10], rcx
0x180079d84  mov     [rbp+var_40], r15
0x180079d88  mov     esi, r15d
0x180079d8b  mov     r13, [rbp+var_20]
0x180079d8f  mov     [rbp+var_10], r13
0x180079d93  cmp     [rbp+arg_8], r15d
0x180079d97  jbe     loc_18007A0D4
0x180079d9d  mov     rbx, [r14+68h]
0x180079da1  mov     rax, [rbx]
0x180079da4  mov     r15, [rax+18h]
0x180079da8  mov     [rbp+arg_10], 0
0x180079db0  test    rcx, rcx
0x180079db3  jz      short loc_180079DC2
0x180079db5  mov     rdx, [rcx]
0x180079db8  mov     rax, [rdx+10h]
0x180079dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079dc1  nop
0x180079dc2  lea     r8, [rbp+arg_10]
0x180079dc6  mov     edx, esi
0x180079dc8  mov     rcx, rbx
0x180079dcb  mov     rax, r15
0x180079dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079dd3  mov     ebx, eax
0x180079dd5  xor     r15d, r15d
0x180079dd8  test    eax, eax
0x180079dda  js      loc_18007A0A6
0x180079de0  mov     [rbp+pbstr], r15
0x180079de4  mov     rcx, [rbp+arg_10]
0x180079de8  mov     rax, [rcx]
0x180079deb  mov     [rbp+pbstr], r15
0x180079def  lea     rdx, [rbp+pbstr]
0x180079df3  mov     rax, [rax+70h]
0x180079df7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079dfc  mov     ebx, eax
0x180079dfe  test    eax, eax
0x180079e00  js      loc_18007A082
0x180079e06  mov     [rbp+string], r15
0x180079e0a  xor     edx, edx
0x180079e0c  lea     rcx, [rbp+string]
0x180079e10  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180079e15  mov     rcx, [rbp+pbstr]; pbstr
0x180079e19  call    cs:__imp_SysStringLen
0x180079e1f  lea     r8, [rbp+string]; string
0x180079e23  mov     edx, eax; length
0x180079e25  mov     rcx, [rbp+pbstr]; sourceString
0x180079e29  call    cs:__imp_WindowsCreateString
0x180079e2f  mov     ebx, eax
0x180079e31  test    eax, eax
0x180079e33  js      loc_18007A05E
0x180079e39  mov     [rbp+var_38], r15
0x180079e3d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ExpeditedUpdatePILess@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ExpeditedUpdatePILess@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExpeditedUpdatePILess> `wil::Feature<__WilFeatureTraits_Feature_ExpeditedUpdatePILess>::GetImpl(void)'::`2'::impl
0x180079e44  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ExpeditedUpdatePILess@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExpeditedUpdatePILess>::__private_IsEnabled(void)
0x180079e49  test    al, al
0x180079e4b  jnz     loc_180079FC4
0x180079e51  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus> `wil::Feature<__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus>::GetImpl(void)'::`2'::impl
0x180079e58  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus>::__private_IsEnabled(void)
0x180079e5d  test    al, al
0x180079e5f  jnz     loc_180079FC4
0x180079e65  mov     [rbp+bstrString], r15
0x180079e69  mov     rbx, [rbp+arg_10]
0x180079e6d  mov     rax, [rbx]
0x180079e70  mov     r15, [rax]
0x180079e73  mov     rcx, [rbp+var_40]
0x180079e77  mov     [rbp+var_40], 0
0x180079e7f  test    rcx, rcx
0x180079e82  jz      short loc_180079E91
0x180079e84  mov     rdx, [rcx]
0x180079e87  mov     rax, [rdx+10h]
0x180079e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079e90  nop
0x180079e91  lea     r8, [rbp+var_40]
0x180079e95  lea     rdx, _GUID_094c3761_2220_471d_9830_3baa13cea544
0x180079e9c  mov     rcx, rbx
0x180079e9f  mov     rax, r15
0x180079ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079ea7  mov     ebx, eax
0x180079ea9  test    eax, eax
0x180079eab  js      loc_18007A030
0x180079eb1  mov     r15, [rbp+var_40]
0x180079eb5  mov     rax, [r15]
0x180079eb8  mov     r13, [rax+148h]
0x180079ebf  mov     rbx, [rbp+bstrString]
0x180079ec3  test    rbx, rbx
0x180079ec6  jz      short loc_180079EE3
0x180079ec8  lea     rcx, [rbp+var_18]; this
0x180079ecc  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180079ed1  mov     rcx, rbx; bstrString
0x180079ed4  call    cs:__imp_SysFreeString
0x180079eda  lea     rcx, [rbp+var_18]; this
0x180079ede  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180079ee3  mov     [rbp+bstrString], 0
0x180079eeb  lea     rdx, [rbp+bstrString]
0x180079eef  mov     rcx, r15
0x180079ef2  mov     rax, r13
0x180079ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079efa  mov     ebx, eax
0x180079efc  xor     r15d, r15d
0x180079eff  test    eax, eax
0x180079f01  js      loc_18007A029
0x180079f07  xor     edx, edx
0x180079f09  lea     rcx, [rbp+var_38]
0x180079f0d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180079f12  mov     rcx, [rbp+bstrString]; pbstr
0x180079f16  call    cs:__imp_SysStringLen
0x180079f1c  lea     r8, [rbp+var_38]; string
0x180079f20  mov     edx, eax; length
0x180079f22  mov     rcx, [rbp+bstrString]; sourceString
0x180079f26  call    cs:__imp_WindowsCreateString
0x180079f2c  mov     ebx, eax
0x180079f2e  test    eax, eax
0x180079f30  js      loc_18007A022
0x180079f36  lea     rcx, [rbp+bstrString]
0x180079f3a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180079f3f  mov     r13, [rbp+var_10]
0x180079f43  xor     edx, edx; length
0x180079f45  mov     rcx, [rbp+var_38]; string
0x180079f49  call    cs:__imp_WindowsGetStringRawBuffer
0x180079f4f  mov     rbx, rax
0x180079f52  xor     edx, edx; length
0x180079f54  mov     rcx, [rbp+string]; string
0x180079f58  call    cs:__imp_WindowsGetStringRawBuffer
0x180079f5e  mov     r9, rbx
0x180079f61  mov     r8, rax
0x180079f64  lea     rdx, aExpeditedupdat_13; "ExpeditedUpdateUSOTask GetUpdatesList I"...
0x180079f6b  xor     ecx, ecx
0x180079f6d  call    UnattendLogW
0x180079f72  mov     [rbp+arg_0], r15b
0x180079f76  mov     rax, [r13+0]
0x180079f7a  lea     r9, [rbp+arg_0]
0x180079f7e  mov     r8, [rbp+var_38]
0x180079f82  mov     rdx, [rbp+string]
0x180079f86  mov     rcx, r13
0x180079f89  mov     rax, [rax+50h]
0x180079f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079f92  nop
0x180079f93  lea     rcx, [rbp+var_38]; this
0x180079f97  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180079f9c  nop
0x180079f9d  lea     rcx, [rbp+string]; this
0x180079fa1  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180079fa6  nop
0x180079fa7  lea     rcx, [rbp+pbstr]
0x180079fab  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180079fb0  inc     esi
0x180079fb2  cmp     esi, [rbp+arg_8]
0x180079fb5  jnb     loc_18007A0D4
0x180079fbb  mov     rcx, [rbp+arg_10]
0x180079fbf  jmp     loc_180079D9D
0x180079fc4  lea     rcx, [r14-238h]
0x180079fcb  lea     r8, [rbp+var_38]
0x180079fcf  mov     rdx, [rbp+arg_10]
0x180079fd3  call    ?_BuildUpdateProperties@ExpeditedUpdateUSOTask@@AEAAJPEAUIMoUsoUpdate@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; ExpeditedUpdateUSOTask::_BuildUpdateProperties(IMoUsoUpdate *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x180079fd8  mov     ebx, eax
0x180079fda  mov     rcx, [rbp+38h]; this
0x180079fde  test    eax, eax
0x180079fe0  jns     loc_180079F43
0x180079fe6  mov     r9d, eax; char *
0x180079fe9  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x180079ff0  mov     edx, 15Fh; void *
0x180079ff5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180079ffa  xor     edx, edx; length
0x180079ffc  mov     rcx, [rbp+string]; string
0x18007a000  call    cs:__imp_WindowsGetStringRawBuffer
0x18007a006  mov     r9d, ebx
0x18007a009  mov     r8, rax
0x18007a00c  lea     rdx, aExpeditedupdat_51; "ExpeditedUpdateUSOTask Failed to build "...
0x18007a013  mov     ecx, 1
0x18007a018  call    UnattendLogW
0x18007a01d  jmp     loc_180079F93
0x18007a022  mov     edx, 16Ah
0x18007a027  jmp     short loc_18007A035
0x18007a029  mov     edx, 169h
0x18007a02e  jmp     short loc_18007A035
0x18007a030  mov     edx, 168h; void *
0x18007a035  mov     rcx, [rbp+38h]; this
0x18007a039  mov     r9d, eax; char *
0x18007a03c  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007a043  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a048  nop
0x18007a049  lea     rcx, [rbp+bstrString]
0x18007a04d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007a052  nop
0x18007a053  lea     rcx, [rbp+var_38]; this
0x18007a057  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18007a05c  jmp     short loc_18007A077
0x18007a05e  mov     rcx, [rbp+38h]; this
0x18007a062  mov     r9d, eax; char *
0x18007a065  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007a06c  mov     edx, 158h; void *
0x18007a071  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a076  nop
0x18007a077  lea     rcx, [rbp+string]; this
0x18007a07b  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18007a080  jmp     short loc_18007A09B
0x18007a082  mov     rcx, [rbp+38h]; this
0x18007a086  mov     r9d, eax; char *
0x18007a089  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007a090  mov     edx, 155h; void *
0x18007a095  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a09a  nop
0x18007a09b  lea     rcx, [rbp+pbstr]
0x18007a09f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007a0a4  jmp     short loc_18007A0BF
0x18007a0a6  mov     rcx, [rbp+38h]; this
0x18007a0aa  mov     r9d, eax; char *
0x18007a0ad  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007a0b4  mov     edx, 152h; void *
0x18007a0b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a0be  nop
0x18007a0bf  lea     rcx, [rbp+var_40]
0x18007a0c3  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18007a0c8  nop
0x18007a0c9  lea     rcx, [rbp+arg_10]
0x18007a0cd  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18007a0d2  jmp     short loc_18007A0F2
0x18007a0d4  mov     [rbp+var_20], r15
0x18007a0d8  mov     [r12], r13
0x18007a0dc  lea     rcx, [rbp+var_40]
0x18007a0e0  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18007a0e5  nop
0x18007a0e6  lea     rcx, [rbp+arg_10]
0x18007a0ea  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18007a0ef  mov     ebx, r15d
0x18007a0f2  lea     rcx, [rbp+var_20]
0x18007a0f6  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18007a0fb  mov     eax, ebx
0x18007a0fd  add     rsp, 70h
0x18007a101  pop     r15
0x18007a103  pop     r14
0x18007a105  pop     r13
0x18007a107  pop     r12
0x18007a109  pop     rsi
0x18007a10a  pop     rbx
0x18007a10b  pop     rbp
0x18007a10c  retn
```
