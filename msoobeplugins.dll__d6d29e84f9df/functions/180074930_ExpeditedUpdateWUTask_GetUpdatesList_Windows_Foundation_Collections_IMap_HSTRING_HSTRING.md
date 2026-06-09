# ExpeditedUpdateWUTask::GetUpdatesList(Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *> * *)

- ea: `0x180074930`
- end: `0x180074d1e`
- name: `?GetUpdatesList@ExpeditedUpdateWUTask@@UEAAJPEAPEAU?$IMap@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Z`
- size: `1006`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180008544`
- `0x18001ad08`
- `0x18002f39c`
- `0x1800418d8`
- `0x180043c58`
- `0x1800698e0`
- `0x180074930`
- `0x1800765c8`
- `0x180078004`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180074ad4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180074b5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180074ad4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180074b5f`
- `OLEAUT32!__imp_SysStringLen` at `0x180074ac4`
- `OLEAUT32!__imp_SysStringLen` at `0x180074b4f`
- `OLEAUT32!__imp_SysStringLen` at `0x180074ac4`
- `OLEAUT32!__imp_SysStringLen` at `0x180074b4f`

## string_xrefs

- `0x18007498c`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180074bd8`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180074c27`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180074c45`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180074c5f`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180074c79`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180074c96`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180074cb3`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall ExpeditedUpdateWUTask::GetUpdatesList(__int64 a1, _QWORD *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  void (__fastcall ***v6)(_QWORD, _QWORD, _QWORD); // rcx
  unsigned int v7; // r14d
  __int64 v8; // rbx
  __int64 v9; // rsi
  __int64 (__fastcall *v10)(__int64, _QWORD, _QWORD); // r12
  int v11; // eax
  int v12; // esi
  void (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rsi
  void (__fastcall *v14)(_QWORD, GUID *, _QWORD **); // r12
  _QWORD *v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  void (__fastcall **v18)(_QWORD, _QWORD, _QWORD); // rax
  int v19; // eax
  __int64 v20; // rax
  int v21; // eax
  UINT v22; // eax
  HRESULT v23; // eax
  int updated; // eax
  HSTRING *v25; // rcx
  UINT v26; // eax
  HRESULT v27; // eax
  HSTRING *v28; // rcx
  int v30; // [rsp+20h] [rbp-58h]
  BSTR v31; // [rsp+30h] [rbp-48h] BYREF
  BSTR pbstr; // [rsp+38h] [rbp-40h] BYREF
  __int64 *v33; // [rsp+40h] [rbp-38h] BYREF
  HSTRING string; // [rsp+48h] [rbp-30h] BYREF
  HSTRING v35; // [rsp+50h] [rbp-28h] BYREF
  __int64 v36; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v37[3]; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  char v39; // [rsp+C0h] [rbp+48h] BYREF
  int v40; // [rsp+C8h] [rbp+50h] BYREF
  void (__fastcall ***v41)(_QWORD, GUID *, _QWORD **); // [rsp+D0h] [rbp+58h] BYREF
  _QWORD *v42; // [rsp+D8h] [rbp+60h] BYREF

  *a2 = 0;
  if ( *(_QWORD *)(a1 + 48) )
  {
    v36 = 0;
    Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Make(
      a1,
      a2,
      &v36);
    v40 = 0;
    v4 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)(a1 + 48) + 80LL))(*(_QWORD *)(a1 + 48), &v40);
    v5 = v4;
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15B,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
        (const char *)(unsigned int)v4,
        v30);
LABEL_34:
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v36);
      return v5;
    }
    v6 = 0;
    v41 = 0;
    v42 = 0;
    v7 = 0;
    v8 = v36;
    if ( v40 > 0 )
    {
      while ( 1 )
      {
        v9 = *(_QWORD *)(a1 + 48);
        v10 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v9 + 56LL);
        v41 = 0;
        if ( v6 )
          ((void (__fastcall *)(void (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v6)[2])(v6);
        v11 = v10(v9, v7, &v41);
        v12 = v11;
        if ( v11 < 0 )
          break;
        v13 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v41;
        v14 = **v41;
        v15 = v42;
        v42 = 0;
        if ( v15 )
          (*(void (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
        v14(v13, &GUID_59d344a2_d3b4_49d5_9486_31462e1974c9, &v42);
        v31 = 0;
        v16 = *v42;
        v31 = 0;
        v17 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, BSTR *))(v16 + 104))(v42, L"Audience", &v31);
        v12 = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x166,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
            (const char *)(unsigned int)v17,
            v30);
          goto LABEL_26;
        }
        v33 = 0;
        v18 = (void (__fastcall **)(_QWORD, _QWORD, _QWORD))*v41;
        v33 = 0;
        v19 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD **), __int64 **))v18[19])(v41, &v33);
        v12 = v19;
        if ( v19 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x169,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
            (const char *)(unsigned int)v19,
            v30);
          goto LABEL_25;
        }
        pbstr = 0;
        v20 = *v33;
        pbstr = 0;
        v21 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v20 + 64))(v33, &pbstr);
        v12 = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x16B,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
            (const char *)(unsigned int)v21,
            v30);
          goto LABEL_24;
        }
        string = 0;
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
          &string,
          0);
        v22 = SysStringLen(pbstr);
        v23 = WindowsCreateString(pbstr, v22, &string);
        v12 = v23;
        if ( v23 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x16E,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
            (const char *)(unsigned int)v23,
            v30);
          goto LABEL_23;
        }
        v39 = 0;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExpeditedUpdatePILess>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ExpeditedUpdatePILess>::GetImpl'::`2'::impl) )
        {
          v37[0] = 0;
          updated = ExpeditedUpdateWUTask::_BuildUpdateProperties(a1 - 568, v41, v37);
          v12 = updated;
          if ( updated < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x173,
              (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
              (const char *)(unsigned int)updated,
              v30);
            v28 = (HSTRING *)v37;
LABEL_22:
            Windows::Internal::String::~String((Windows::Internal::String *)v28);
LABEL_23:
            Windows::Internal::String::~String((Windows::Internal::String *)&string);
LABEL_24:
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pbstr);
LABEL_25:
            wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v33);
LABEL_26:
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v31);
            goto LABEL_33;
          }
          (*(void (__fastcall **)(__int64, HSTRING, _QWORD, char *))(*(_QWORD *)v8 + 80LL))(v8, string, v37[0], &v39);
          v25 = (HSTRING *)v37;
        }
        else
        {
          v35 = 0;
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
            &v35,
            0);
          v26 = SysStringLen(v31);
          v27 = WindowsCreateString(v31, v26, &v35);
          v12 = v27;
          if ( v27 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x179,
              (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
              (const char *)(unsigned int)v27,
              v30);
            v28 = &v35;
            goto LABEL_22;
          }
          (*(void (__fastcall **)(__int64, HSTRING, HSTRING, char *))(*(_QWORD *)v8 + 80LL))(v8, string, v35, &v39);
          v25 = &v35;
        }
        Windows::Internal::String::~String((Windows::Internal::String *)v25);
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pbstr);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v33);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v31);
        if ( (int)++v7 >= v40 )
          goto LABEL_35;
        v6 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v41;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x162,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
        (const char *)(unsigned int)v11,
        v30);
LABEL_33:
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v42);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v41);
      v5 = v12;
      goto LABEL_34;
    }
LABEL_35:
    v36 = 0;
    *a2 = v8;
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v42);
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v41);
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v36);
  }
  return 0;
}

```

## disassembly

```asm
0x180074930  push    rbp
0x180074932  push    rbx
0x180074933  push    rsi
0x180074934  push    rdi
0x180074935  push    r12
0x180074937  push    r13
0x180074939  push    r14
0x18007493b  push    r15
0x18007493d  mov     rbp, rsp
0x180074940  sub     rsp, 78h
0x180074944  mov     r15, rdx
0x180074947  mov     rdi, rcx
0x18007494a  xor     r13d, r13d
0x18007494d  mov     [rdx], r13
0x180074950  cmp     [rcx+30h], r13
0x180074954  jz      loc_180074D0B
0x18007495a  mov     [rbp+var_20], r13
0x18007495e  lea     r8, [rbp+var_20]
0x180074962  call    ?Make@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@SAJAEBU?$DefaultHash@PEAUHSTRING__@@@2345@AEBU?$DefaultEqualityPredicate@PEAUHSTRING__@@@2345@PEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Make(Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>> * *)
0x180074967  mov     [rbp+arg_8], r13d
0x18007496b  mov     rcx, [rdi+30h]
0x18007496f  mov     rax, [rcx]
0x180074972  lea     rdx, [rbp+arg_8]
0x180074976  mov     rax, [rax+50h]
0x18007497a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007497f  mov     ebx, eax
0x180074981  test    eax, eax
0x180074983  jns     short loc_1800749A2
0x180074985  mov     rcx, [rbp+40h]; this
0x180074989  mov     r9d, eax; char *
0x18007498c  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180074993  mov     edx, 15Bh; void *
0x180074998  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007499d  jmp     loc_180074CDA
0x1800749a2  mov     rcx, r13
0x1800749a5  mov     [rbp+arg_10], rcx
0x1800749a9  mov     [rbp+arg_18], r13
0x1800749ad  mov     r14d, r13d
0x1800749b0  mov     rbx, [rbp+var_20]
0x1800749b4  cmp     [rbp+arg_8], r13d
0x1800749b8  jle     loc_180074CE7
0x1800749be  mov     rsi, [rdi+30h]
0x1800749c2  mov     rax, [rsi]
0x1800749c5  mov     r12, [rax+38h]
0x1800749c9  mov     [rbp+arg_10], r13
0x1800749cd  test    rcx, rcx
0x1800749d0  jz      short loc_1800749DF
0x1800749d2  mov     rdx, [rcx]
0x1800749d5  mov     rax, [rdx+10h]
0x1800749d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800749de  nop
0x1800749df  lea     r8, [rbp+arg_10]
0x1800749e3  mov     edx, r14d
0x1800749e6  mov     rcx, rsi
0x1800749e9  mov     rax, r12
0x1800749ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800749f1  mov     esi, eax
0x1800749f3  test    eax, eax
0x1800749f5  js      loc_180074CAC
0x1800749fb  mov     rsi, [rbp+arg_10]
0x1800749ff  mov     rax, [rsi]
0x180074a02  mov     r12, [rax]
0x180074a05  mov     rcx, [rbp+arg_18]
0x180074a09  mov     [rbp+arg_18], r13
0x180074a0d  test    rcx, rcx
0x180074a10  jz      short loc_180074A1F
0x180074a12  mov     rdx, [rcx]
0x180074a15  mov     rax, [rdx+10h]
0x180074a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074a1e  nop
0x180074a1f  lea     r8, [rbp+arg_18]
0x180074a23  lea     rdx, _GUID_59d344a2_d3b4_49d5_9486_31462e1974c9
0x180074a2a  mov     rcx, rsi
0x180074a2d  mov     rax, r12
0x180074a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074a35  mov     [rbp+var_48], r13
0x180074a39  mov     rcx, [rbp+arg_18]
0x180074a3d  mov     rax, [rcx]
0x180074a40  mov     [rbp+var_48], r13
0x180074a44  lea     r8, [rbp+var_48]
0x180074a48  lea     rdx, aAudience; "Audience"
0x180074a4f  mov     rax, [rax+68h]
0x180074a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074a58  mov     esi, eax
0x180074a5a  test    eax, eax
0x180074a5c  js      loc_180074C8F
0x180074a62  mov     [rbp+var_38], r13
0x180074a66  mov     rcx, [rbp+arg_10]
0x180074a6a  mov     rax, [rcx]
0x180074a6d  mov     [rbp+var_38], r13
0x180074a71  lea     rdx, [rbp+var_38]
0x180074a75  mov     rax, [rax+98h]
0x180074a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074a81  mov     esi, eax
0x180074a83  test    eax, eax
0x180074a85  js      loc_180074C72
0x180074a8b  mov     [rbp+pbstr], r13
0x180074a8f  mov     rcx, [rbp+var_38]
0x180074a93  mov     rax, [rcx]
0x180074a96  mov     [rbp+pbstr], r13
0x180074a9a  lea     rdx, [rbp+pbstr]
0x180074a9e  mov     rax, [rax+40h]
0x180074aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074aa7  mov     esi, eax
0x180074aa9  test    eax, eax
0x180074aab  js      loc_180074C58
0x180074ab1  mov     [rbp+string], r13
0x180074ab5  xor     edx, edx
0x180074ab7  lea     rcx, [rbp+string]
0x180074abb  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180074ac0  mov     rcx, [rbp+pbstr]; pbstr
0x180074ac4  call    cs:__imp_SysStringLen
0x180074aca  lea     r8, [rbp+string]; string
0x180074ace  mov     edx, eax; length
0x180074ad0  mov     rcx, [rbp+pbstr]; sourceString
0x180074ad4  call    cs:__imp_WindowsCreateString
0x180074ada  mov     esi, eax
0x180074adc  test    eax, eax
0x180074ade  js      loc_180074C3E
0x180074ae4  mov     [rbp+arg_0], r13b
0x180074ae8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ExpeditedUpdatePILess@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ExpeditedUpdatePILess@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExpeditedUpdatePILess> `wil::Feature<__WilFeatureTraits_Feature_ExpeditedUpdatePILess>::GetImpl(void)'::`2'::impl
0x180074aef  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ExpeditedUpdatePILess@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExpeditedUpdatePILess>::__private_IsEnabled(void)
0x180074af4  test    al, al
0x180074af6  jz      short loc_180074B3C
0x180074af8  mov     [rbp+var_18], r13
0x180074afc  lea     rcx, [rdi-238h]
0x180074b03  lea     r8, [rbp+var_18]
0x180074b07  mov     rdx, [rbp+arg_10]
0x180074b0b  call    ?_BuildUpdateProperties@ExpeditedUpdateWUTask@@AEAAJPEAUIUpdate@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; ExpeditedUpdateWUTask::_BuildUpdateProperties(IUpdate *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x180074b10  mov     esi, eax
0x180074b12  test    eax, eax
0x180074b14  js      loc_180074BD1
0x180074b1a  mov     rax, [rbx]
0x180074b1d  lea     r9, [rbp+arg_0]
0x180074b21  mov     r8, [rbp+var_18]
0x180074b25  mov     rdx, [rbp+string]
0x180074b29  mov     rcx, rbx
0x180074b2c  mov     rax, [rax+50h]
0x180074b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074b35  nop
0x180074b36  lea     rcx, [rbp+var_18]
0x180074b3a  jmp     short loc_180074B8E
0x180074b3c  mov     [rbp+var_28], r13
0x180074b40  xor     edx, edx
0x180074b42  lea     rcx, [rbp+var_28]
0x180074b46  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180074b4b  mov     rcx, [rbp+var_48]; pbstr
0x180074b4f  call    cs:__imp_SysStringLen
0x180074b55  lea     r8, [rbp+var_28]; string
0x180074b59  mov     edx, eax; length
0x180074b5b  mov     rcx, [rbp+var_48]; sourceString
0x180074b5f  call    cs:__imp_WindowsCreateString
0x180074b65  mov     esi, eax
0x180074b67  test    eax, eax
0x180074b69  js      loc_180074C20
0x180074b6f  mov     rax, [rbx]
0x180074b72  lea     r9, [rbp+arg_0]
0x180074b76  mov     r8, [rbp+var_28]
0x180074b7a  mov     rdx, [rbp+string]
0x180074b7e  mov     rcx, rbx
0x180074b81  mov     rax, [rax+50h]
0x180074b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074b8a  lea     rcx, [rbp+var_28]; this
0x180074b8e  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180074b93  nop
0x180074b94  lea     rcx, [rbp+string]; this
0x180074b98  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180074b9d  nop
0x180074b9e  lea     rcx, [rbp+pbstr]
0x180074ba2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180074ba7  nop
0x180074ba8  lea     rcx, [rbp+var_38]
0x180074bac  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180074bb1  nop
0x180074bb2  lea     rcx, [rbp+var_48]
0x180074bb6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180074bbb  inc     r14d
0x180074bbe  cmp     r14d, [rbp+arg_8]
0x180074bc2  jge     loc_180074CE7
0x180074bc8  mov     rcx, [rbp+arg_10]
0x180074bcc  jmp     loc_1800749BE
0x180074bd1  mov     rcx, [rbp+40h]; this
0x180074bd5  mov     r9d, esi; char *
0x180074bd8  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180074bdf  mov     edx, 173h; void *
0x180074be4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074be9  nop
0x180074bea  lea     rcx, [rbp+var_18]; this
0x180074bee  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180074bf3  nop
0x180074bf4  lea     rcx, [rbp+string]; this
0x180074bf8  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180074bfd  nop
0x180074bfe  lea     rcx, [rbp+pbstr]
0x180074c02  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180074c07  nop
0x180074c08  lea     rcx, [rbp+var_38]
0x180074c0c  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180074c11  nop
0x180074c12  lea     rcx, [rbp+var_48]
0x180074c16  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180074c1b  jmp     loc_180074CC5
0x180074c20  mov     rcx, [rbp+40h]; this
0x180074c24  mov     r9d, esi; char *
0x180074c27  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180074c2e  mov     edx, 179h; void *
0x180074c33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074c38  lea     rcx, [rbp+var_28]
0x180074c3c  jmp     short loc_180074BEE
0x180074c3e  mov     rcx, [rbp+40h]; this
0x180074c42  mov     r9d, esi; char *
0x180074c45  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180074c4c  mov     edx, 16Eh; void *
0x180074c51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074c56  jmp     short loc_180074BF4
0x180074c58  mov     rcx, [rbp+40h]; this
0x180074c5c  mov     r9d, esi; char *
0x180074c5f  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180074c66  mov     edx, 16Bh; void *
0x180074c6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074c70  jmp     short loc_180074BFE
0x180074c72  mov     rcx, [rbp+40h]; this
0x180074c76  mov     r9d, esi; char *
0x180074c79  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180074c80  mov     edx, 169h; void *
0x180074c85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074c8a  jmp     loc_180074C08
0x180074c8f  mov     rcx, [rbp+40h]; this
0x180074c93  mov     r9d, esi; char *
0x180074c96  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180074c9d  mov     edx, 166h; void *
0x180074ca2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074ca7  jmp     loc_180074C12
0x180074cac  mov     rcx, [rbp+40h]; this
0x180074cb0  mov     r9d, esi; char *
0x180074cb3  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180074cba  mov     edx, 162h; void *
0x180074cbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074cc4  nop
0x180074cc5  lea     rcx, [rbp+arg_18]
0x180074cc9  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180074cce  nop
0x180074ccf  lea     rcx, [rbp+arg_10]
0x180074cd3  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180074cd8  mov     ebx, esi
0x180074cda  lea     rcx, [rbp+var_20]
0x180074cde  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180074ce3  mov     eax, ebx
0x180074ce5  jmp     short loc_180074D0D
0x180074ce7  mov     [rbp+var_20], r13
0x180074ceb  mov     [r15], rbx
0x180074cee  lea     rcx, [rbp+arg_18]
0x180074cf2  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180074cf7  nop
0x180074cf8  lea     rcx, [rbp+arg_10]
0x180074cfc  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180074d01  nop
0x180074d02  lea     rcx, [rbp+var_20]
0x180074d06  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180074d0b  xor     eax, eax
0x180074d0d  add     rsp, 78h
0x180074d11  pop     r15
0x180074d13  pop     r14
0x180074d15  pop     r13
0x180074d17  pop     r12
0x180074d19  pop     rdi
0x180074d1a  pop     rsi
0x180074d1b  pop     rbx
0x180074d1c  pop     rbp
0x180074d1d  retn
```
